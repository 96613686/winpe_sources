# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18007f1e4`
- end: `0x18007f2a1`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18007e800`

## callees

- `0x18007c158`
- `0x18007f1e4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007f23e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007f23e`

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
0x18007f1e4  mov     [rsp+arg_0], rbx
0x18007f1e9  push    rdi
0x18007f1ea  sub     rsp, 20h
0x18007f1ee  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18007f1f5  xor     ebx, ebx
0x18007f1f7  test    rdi, rdi
0x18007f1fa  jz      loc_18007F293
0x18007f200  cmp     [rdi+8], rbx
0x18007f204  jnz     short loc_18007F22B
0x18007f206  mov     rcx, [rdi]
0x18007f209  lea     rdx, [rsp+28h+arg_8]
0x18007f20e  mov     [rsp+28h+arg_8], rbx
0x18007f213  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18007f218  test    eax, eax
0x18007f21a  js      short loc_18007F22B
0x18007f21c  cmp     [rdi+8], rbx
0x18007f220  jnz     short loc_18007F22B
0x18007f222  mov     rax, [rsp+28h+arg_8]
0x18007f227  mov     [rdi+8], rax
0x18007f22b  mov     rax, [rdi+8]
0x18007f22f  lea     rcx, [rax+20h]
0x18007f233  neg     rax
0x18007f236  sbb     rdi, rdi
0x18007f239  and     rdi, rcx
0x18007f23c  jz      short loc_18007F293
0x18007f23e  call    cs:__imp_GetCurrentThreadId
0x18007f244  mov     r8d, eax
0x18007f247  mov     r9d, eax
0x18007f24a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18007f254  shr     r8, 2
0x18007f258  mul     r8
0x18007f25b  shr     rdx, 3
0x18007f25f  lea     rcx, [rdx+rdx*4]
0x18007f263  add     rcx, rcx
0x18007f266  sub     r8, rcx
0x18007f269  mov     rbx, [rdi+r8*8+8]
0x18007f26e  test    rbx, rbx
0x18007f271  jz      short loc_18007F293
0x18007f273  cmp     [rbx], r9d
0x18007f276  jz      short loc_18007F27E
0x18007f278  mov     rbx, [rbx+8]
0x18007f27c  jmp     short loc_18007F26E
0x18007f27e  add     rbx, 10h
0x18007f282  jz      short loc_18007F293
0x18007f284  cmp     qword ptr [rbx+8], 0
0x18007f289  jnz     short loc_18007F293
0x18007f28b  lea     rax, [rdi+4]
0x18007f28f  mov     [rbx+8], rax
0x18007f293  mov     rax, rbx
0x18007f296  mov     rbx, [rsp+28h+arg_0]
0x18007f29b  add     rsp, 20h
0x18007f29f  pop     rdi
0x18007f2a0  retn
```
