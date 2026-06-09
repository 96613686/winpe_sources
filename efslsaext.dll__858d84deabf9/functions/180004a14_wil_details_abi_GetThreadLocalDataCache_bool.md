# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180004a14`
- end: `0x180004acf`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004390`

## callees

- `0x180003bf8`
- `0x180004a14`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004a6a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004a6a`

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
0x180004a14  mov     [rsp+arg_0], rbx
0x180004a19  push    rdi
0x180004a1a  sub     rsp, 20h
0x180004a1e  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180004a25  xor     ebx, ebx
0x180004a27  test    rdi, rdi
0x180004a2a  jz      short loc_180004AAA
0x180004a2c  cmp     [rdi+8], rbx
0x180004a30  jnz     short loc_180004A57
0x180004a32  mov     rcx, [rdi]
0x180004a35  lea     rdx, [rsp+28h+arg_8]
0x180004a3a  mov     [rsp+28h+arg_8], rbx
0x180004a3f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180004a44  test    eax, eax
0x180004a46  js      short loc_180004A57
0x180004a48  cmp     [rdi+8], rbx
0x180004a4c  jnz     short loc_180004A57
0x180004a4e  mov     rax, [rsp+28h+arg_8]
0x180004a53  mov     [rdi+8], rax
0x180004a57  mov     rax, [rdi+8]
0x180004a5b  lea     rcx, [rax+20h]
0x180004a5f  neg     rax
0x180004a62  sbb     rdi, rdi
0x180004a65  and     rdi, rcx
0x180004a68  jz      short loc_180004AAA
0x180004a6a  call    cs:__imp_GetCurrentThreadId
0x180004a70  mov     r8d, eax
0x180004a73  mov     r9d, eax
0x180004a76  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004a80  shr     r8, 2
0x180004a84  mul     r8
0x180004a87  shr     rdx, 3
0x180004a8b  lea     rcx, [rdx+rdx*4]
0x180004a8f  add     rcx, rcx
0x180004a92  sub     r8, rcx
0x180004a95  mov     rbx, [rdi+r8*8+8]
0x180004a9a  jmp     short loc_180004AA5
0x180004a9c  cmp     [rbx], r9d
0x180004a9f  jz      short loc_180004AB8
0x180004aa1  mov     rbx, [rbx+8]
0x180004aa5  test    rbx, rbx
0x180004aa8  jnz     short loc_180004A9C
0x180004aaa  mov     rax, rbx
0x180004aad  mov     rbx, [rsp+28h+arg_0]
0x180004ab2  add     rsp, 20h
0x180004ab6  pop     rdi
0x180004ab7  retn
0x180004ab8  add     rbx, 10h
0x180004abc  jz      short loc_180004AAA
0x180004abe  cmp     qword ptr [rbx+8], 0
0x180004ac3  jnz     short loc_180004AAA
0x180004ac5  lea     rax, [rdi+4]
0x180004ac9  mov     [rbx+8], rax
0x180004acd  jmp     short loc_180004AAA
```
