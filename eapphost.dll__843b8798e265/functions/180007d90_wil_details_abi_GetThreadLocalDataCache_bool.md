# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180007d90`
- end: `0x180007e54`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `196`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800076d0`

## callees

- `0x18000529c`
- `0x180007d90`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007dea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007dea`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct wil::details_abi::ThreadLocalData *__fastcall wil::details_abi::GetThreadLocalDataCache(wil::details_abi *this)
{
  __int64 i; // rbx
  __int64 v2; // rdi
  __int64 v3; // rdi
  DWORD CurrentThreadId; // r9d
  void *v6; // [rsp+38h] [rbp+10h] BYREF

  i = 0;
  v2 = wil::details_abi::g_pProcessLocalData;
  if ( wil::details_abi::g_pProcessLocalData )
  {
    if ( !*(_QWORD *)(wil::details_abi::g_pProcessLocalData + 8) )
    {
      v6 = 0;
      if ( (int)wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
                  *(_QWORD *)wil::details_abi::g_pProcessLocalData,
                  &v6) >= 0
        && !*(_QWORD *)(v2 + 8) )
      {
        *(_QWORD *)(v2 + 8) = v6;
      }
    }
    v3 = (*(_QWORD *)(v2 + 8) + 32LL) & -(__int64)(*(_QWORD *)(v2 + 8) != 0);
    if ( v3 )
    {
      CurrentThreadId = GetCurrentThreadId();
      for ( i = *(_QWORD *)(v3 + 8 * (((unsigned __int64)CurrentThreadId >> 2) % 0xA) + 8); i; i = *(_QWORD *)(i + 8) )
      {
        if ( *(_DWORD *)i == CurrentThreadId )
        {
          i += 16;
          if ( i && !*(_QWORD *)(i + 8) )
            *(_QWORD *)(i + 8) = v3 + 4;
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
0x180007d90  mov     [rsp+arg_0], rbx
0x180007d95  push    rdi
0x180007d96  sub     rsp, 20h
0x180007d9a  xor     ebx, ebx
0x180007d9c  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180007da3  test    rdi, rdi
0x180007da6  jz      loc_180007E45
0x180007dac  cmp     [rdi+8], rbx
0x180007db0  jnz     short loc_180007DD7
0x180007db2  mov     [rsp+28h+arg_8], rbx
0x180007db7  lea     rdx, [rsp+28h+arg_8]
0x180007dbc  mov     rcx, [rdi]
0x180007dbf  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180007dc4  test    eax, eax
0x180007dc6  js      short loc_180007DD7
0x180007dc8  cmp     [rdi+8], rbx
0x180007dcc  jnz     short loc_180007DD7
0x180007dce  mov     rax, [rsp+28h+arg_8]
0x180007dd3  mov     [rdi+8], rax
0x180007dd7  mov     rcx, [rdi+8]
0x180007ddb  lea     rax, [rcx+20h]
0x180007ddf  neg     rcx
0x180007de2  sbb     rdi, rdi
0x180007de5  and     rdi, rax
0x180007de8  jz      short loc_180007E45
0x180007dea  call    cs:__imp_GetCurrentThreadId
0x180007df1  nop     dword ptr [rax+rax+00h]
0x180007df6  mov     r9d, eax
0x180007df9  mov     r8d, eax
0x180007dfc  shr     r8, 2
0x180007e00  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180007e0a  mul     r8
0x180007e0d  shr     rdx, 3
0x180007e11  lea     rcx, [rdx+rdx*4]
0x180007e15  add     rcx, rcx
0x180007e18  sub     r8, rcx
0x180007e1b  mov     rbx, [rdi+r8*8+8]
0x180007e20  test    rbx, rbx
0x180007e23  jz      short loc_180007E45
0x180007e25  cmp     [rbx], r9d
0x180007e28  jz      short loc_180007E30
0x180007e2a  mov     rbx, [rbx+8]
0x180007e2e  jmp     short loc_180007E20
0x180007e30  add     rbx, 10h
0x180007e34  jz      short loc_180007E45
0x180007e36  cmp     qword ptr [rbx+8], 0
0x180007e3b  jnz     short loc_180007E45
0x180007e3d  lea     rax, [rdi+4]
0x180007e41  mov     [rbx+8], rax
0x180007e45  mov     rax, rbx
0x180007e48  mov     rbx, [rsp+28h+arg_0]
0x180007e4d  add     rsp, 20h
0x180007e51  pop     rdi
0x180007e52  retn
```
