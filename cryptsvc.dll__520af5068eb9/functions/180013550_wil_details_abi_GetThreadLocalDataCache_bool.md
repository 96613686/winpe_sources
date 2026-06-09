# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180013550`
- end: `0x18001360d`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180012cf0`

## callees

- `0x18001217c`
- `0x180013550`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800135aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800135aa`

## pseudocode

```c
struct wil::details_abi::ThreadLocalData *__fastcall wil::details_abi::GetThreadLocalDataCache(wil::details_abi *this)
{
  __int64 v1; // rdi
  __int64 i; // rbx
  __int64 v3; // rcx
  __int64 v4; // rdi
  DWORD CurrentThreadId; // r9d
  void *v7; // [rsp+38h] [rbp+10h] BYREF

  v1 = wil::details_abi::g_pProcessLocalData;
  i = 0;
  if ( wil::details_abi::g_pProcessLocalData )
  {
    if ( !*(_QWORD *)(wil::details_abi::g_pProcessLocalData + 8) )
    {
      v3 = *(_QWORD *)wil::details_abi::g_pProcessLocalData;
      v7 = 0;
      if ( (int)wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(v3, &v7) >= 0
        && !*(_QWORD *)(v1 + 8) )
      {
        *(_QWORD *)(v1 + 8) = v7;
      }
    }
    v4 = (*(_QWORD *)(v1 + 8) + 32LL) & -(__int64)(*(_QWORD *)(v1 + 8) != 0);
    if ( v4 )
    {
      CurrentThreadId = GetCurrentThreadId();
      for ( i = *(_QWORD *)(v4 + 8 * (((unsigned __int64)CurrentThreadId >> 2) % 0xA) + 8); i; i = *(_QWORD *)(i + 8) )
      {
        if ( *(_DWORD *)i == CurrentThreadId )
        {
          i += 16;
          if ( i && !*(_QWORD *)(i + 8) )
            *(_QWORD *)(i + 8) = v4 + 4;
          return (struct wil::details_abi::ThreadLocalData *)i;
        }
      }
    }
  }
  return (struct wil::details_abi::ThreadLocalData *)i;
}

```

## disassembly

```asm
0x180013550  mov     [rsp+arg_0], rbx
0x180013555  push    rdi
0x180013556  sub     rsp, 20h
0x18001355a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180013561  xor     ebx, ebx
0x180013563  test    rdi, rdi
0x180013566  jz      loc_1800135FF
0x18001356c  cmp     [rdi+8], rbx
0x180013570  jnz     short loc_180013597
0x180013572  mov     rcx, [rdi]
0x180013575  lea     rdx, [rsp+28h+arg_8]
0x18001357a  mov     [rsp+28h+arg_8], rbx
0x18001357f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180013584  test    eax, eax
0x180013586  js      short loc_180013597
0x180013588  cmp     [rdi+8], rbx
0x18001358c  jnz     short loc_180013597
0x18001358e  mov     rax, [rsp+28h+arg_8]
0x180013593  mov     [rdi+8], rax
0x180013597  mov     rax, [rdi+8]
0x18001359b  lea     rcx, [rax+20h]
0x18001359f  neg     rax
0x1800135a2  sbb     rdi, rdi
0x1800135a5  and     rdi, rcx
0x1800135a8  jz      short loc_1800135FF
0x1800135aa  call    cs:__imp_GetCurrentThreadId
0x1800135b0  mov     r8d, eax
0x1800135b3  mov     r9d, eax
0x1800135b6  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800135c0  shr     r8, 2
0x1800135c4  mul     r8
0x1800135c7  shr     rdx, 3
0x1800135cb  lea     rcx, [rdx+rdx*4]
0x1800135cf  add     rcx, rcx
0x1800135d2  sub     r8, rcx
0x1800135d5  mov     rbx, [rdi+r8*8+8]
0x1800135da  test    rbx, rbx
0x1800135dd  jz      short loc_1800135FF
0x1800135df  cmp     [rbx], r9d
0x1800135e2  jz      short loc_1800135EA
0x1800135e4  mov     rbx, [rbx+8]
0x1800135e8  jmp     short loc_1800135DA
0x1800135ea  add     rbx, 10h
0x1800135ee  jz      short loc_1800135FF
0x1800135f0  cmp     qword ptr [rbx+8], 0
0x1800135f5  jnz     short loc_1800135FF
0x1800135f7  lea     rax, [rdi+4]
0x1800135fb  mov     [rbx+8], rax
0x1800135ff  mov     rax, rbx
0x180013602  mov     rbx, [rsp+28h+arg_0]
0x180013607  add     rsp, 20h
0x18001360b  pop     rdi
0x18001360c  retn
```
