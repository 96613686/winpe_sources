# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180005bcc`
- end: `0x180005c92`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `198`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005340`

## callees

- `0x180004bb0`
- `0x180005bcc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005c26`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005c26`

## pseudocode

```c
struct wil::details_abi::ThreadLocalData *__fastcall wil::details_abi::GetThreadLocalDataCache(wil::details_abi *this)
{
  __int64 v1; // rdi
  __int64 i; // rbx
  __int64 v3; // rcx
  __int64 v4; // rdi
  DWORD CurrentThreadId; // r9d
  __int64 v7; // [rsp+38h] [rbp+10h] BYREF

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
0x180005bcc  mov     [rsp+arg_0], rbx
0x180005bd1  push    rdi
0x180005bd2  sub     rsp, 20h
0x180005bd6  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180005bdd  xor     ebx, ebx
0x180005bdf  test    rdi, rdi
0x180005be2  jz      loc_180005C6C
0x180005be8  cmp     [rdi+8], rbx
0x180005bec  jnz     short loc_180005C13
0x180005bee  mov     rcx, [rdi]
0x180005bf1  lea     rdx, [rsp+28h+arg_8]
0x180005bf6  mov     [rsp+28h+arg_8], rbx
0x180005bfb  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180005c00  test    eax, eax
0x180005c02  js      short loc_180005C13
0x180005c04  cmp     [rdi+8], rbx
0x180005c08  jnz     short loc_180005C13
0x180005c0a  mov     rax, [rsp+28h+arg_8]
0x180005c0f  mov     [rdi+8], rax
0x180005c13  mov     rax, [rdi+8]
0x180005c17  lea     rcx, [rax+20h]
0x180005c1b  neg     rax
0x180005c1e  sbb     rdi, rdi
0x180005c21  and     rdi, rcx
0x180005c24  jz      short loc_180005C6C
0x180005c26  call    cs:__imp_GetCurrentThreadId
0x180005c2d  nop     dword ptr [rax+rax+00h]
0x180005c32  mov     r8d, eax
0x180005c35  mov     r9d, eax
0x180005c38  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180005c42  shr     r8, 2
0x180005c46  mul     r8
0x180005c49  shr     rdx, 3
0x180005c4d  lea     rcx, [rdx+rdx*4]
0x180005c51  add     rcx, rcx
0x180005c54  sub     r8, rcx
0x180005c57  mov     rbx, [rdi+r8*8+8]
0x180005c5c  jmp     short loc_180005C67
0x180005c5e  cmp     [rbx], r9d
0x180005c61  jz      short loc_180005C7B
0x180005c63  mov     rbx, [rbx+8]
0x180005c67  test    rbx, rbx
0x180005c6a  jnz     short loc_180005C5E
0x180005c6c  mov     rax, rbx
0x180005c6f  mov     rbx, [rsp+28h+arg_0]
0x180005c74  add     rsp, 20h
0x180005c78  pop     rdi
0x180005c79  retn
0x180005c7b  add     rbx, 10h
0x180005c7f  jz      short loc_180005C6C
0x180005c81  cmp     qword ptr [rbx+8], 0
0x180005c86  jnz     short loc_180005C6C
0x180005c88  lea     rax, [rdi+4]
0x180005c8c  mov     [rbx+8], rax
0x180005c90  jmp     short loc_180005C6C
```
