# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180005b90`
- end: `0x180005c55`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `197`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005400`

## callees

- `0x1800043ec`
- `0x180005b90`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005bea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005bea`

## pseudocode

```c
struct wil::details_abi::ThreadLocalData *__fastcall wil::details_abi::GetThreadLocalDataCache(wil::details_abi *this)
{
  __int64 v1; // rbx
  __int64 v2; // rdi
  __int64 v3; // rcx
  __int64 v4; // rbx
  DWORD CurrentThreadId; // r9d
  __int64 i; // rcx
  bool v7; // zf
  __int64 v8; // rcx
  __int64 v10; // [rsp+38h] [rbp+10h] BYREF

  v1 = wil::details_abi::g_pProcessLocalData;
  v2 = 0;
  if ( wil::details_abi::g_pProcessLocalData )
  {
    if ( !*(_QWORD *)(wil::details_abi::g_pProcessLocalData + 8) )
    {
      v3 = *(_QWORD *)wil::details_abi::g_pProcessLocalData;
      v10 = 0;
      if ( (int)wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(v3, &v10) >= 0
        && !*(_QWORD *)(v1 + 8) )
      {
        *(_QWORD *)(v1 + 8) = v10;
      }
    }
    v4 = (*(_QWORD *)(v1 + 8) + 32LL) & -(__int64)(*(_QWORD *)(v1 + 8) != 0);
    if ( v4 )
    {
      CurrentThreadId = GetCurrentThreadId();
      for ( i = *(_QWORD *)(v4 + 8 * (CurrentThreadId % 0xAuLL) + 8); i; i = *(_QWORD *)(i + 8) )
      {
        if ( *(_DWORD *)i == CurrentThreadId )
        {
          v7 = i == -16;
          v8 = i + 16;
          v2 = v8;
          if ( !v7 && !*(_QWORD *)(v8 + 8) )
            *(_QWORD *)(v8 + 8) = v4 + 4;
          return (struct wil::details_abi::ThreadLocalData *)v2;
        }
      }
    }
  }
  return (struct wil::details_abi::ThreadLocalData *)v2;
}

```

## disassembly

```asm
0x180005b90  mov     [rsp+arg_0], rbx
0x180005b95  push    rdi
0x180005b96  sub     rsp, 20h
0x180005b9a  mov     rbx, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180005ba1  xor     edi, edi
0x180005ba3  test    rbx, rbx
0x180005ba6  jz      loc_180005C46
0x180005bac  cmp     [rbx+8], rdi
0x180005bb0  jnz     short loc_180005BD7
0x180005bb2  mov     rcx, [rbx]
0x180005bb5  lea     rdx, [rsp+28h+arg_8]
0x180005bba  and     [rsp+28h+arg_8], rdi
0x180005bbf  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180005bc4  test    eax, eax
0x180005bc6  js      short loc_180005BD7
0x180005bc8  cmp     [rbx+8], rdi
0x180005bcc  jnz     short loc_180005BD7
0x180005bce  mov     rax, [rsp+28h+arg_8]
0x180005bd3  mov     [rbx+8], rax
0x180005bd7  mov     rax, [rbx+8]
0x180005bdb  lea     rcx, [rax+20h]
0x180005bdf  neg     rax
0x180005be2  sbb     rbx, rbx
0x180005be5  and     rbx, rcx
0x180005be8  jz      short loc_180005C46
0x180005bea  call    cs:__imp_GetCurrentThreadId
0x180005bf1  nop     dword ptr [rax+rax+00h]
0x180005bf6  mov     r8d, eax
0x180005bf9  mov     r9d, eax
0x180005bfc  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180005c06  mul     r9
0x180005c09  shr     rdx, 3
0x180005c0d  lea     rcx, [rdx+rdx*4]
0x180005c11  add     rcx, rcx
0x180005c14  sub     r8, rcx
0x180005c17  mov     rcx, [rbx+r8*8+8]
0x180005c1c  jmp     short loc_180005C27
0x180005c1e  cmp     [rcx], r9d
0x180005c21  jz      short loc_180005C2E
0x180005c23  mov     rcx, [rcx+8]
0x180005c27  test    rcx, rcx
0x180005c2a  jnz     short loc_180005C1E
0x180005c2c  jmp     short loc_180005C46
0x180005c2e  add     rcx, 10h
0x180005c32  mov     rdi, rcx
0x180005c35  jz      short loc_180005C46
0x180005c37  cmp     qword ptr [rcx+8], 0
0x180005c3c  jnz     short loc_180005C46
0x180005c3e  lea     rax, [rbx+4]
0x180005c42  mov     [rcx+8], rax
0x180005c46  mov     rbx, [rsp+28h+arg_0]
0x180005c4b  mov     rax, rdi
0x180005c4e  add     rsp, 20h
0x180005c52  pop     rdi
0x180005c53  retn
```
