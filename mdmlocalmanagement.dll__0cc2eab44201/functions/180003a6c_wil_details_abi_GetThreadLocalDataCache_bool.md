# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180003a6c`
- end: `0x180003b32`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `198`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003310`

## callees

- `0x180002f5c`
- `0x180003a6c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003ac6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003ac6`

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
0x180003a6c  mov     [rsp+arg_0], rbx
0x180003a71  push    rdi
0x180003a72  sub     rsp, 20h
0x180003a76  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180003a7d  xor     ebx, ebx
0x180003a7f  test    rdi, rdi
0x180003a82  jz      loc_180003B0C
0x180003a88  cmp     [rdi+8], rbx
0x180003a8c  jnz     short loc_180003AB3
0x180003a8e  mov     rcx, [rdi]
0x180003a91  lea     rdx, [rsp+28h+arg_8]
0x180003a96  mov     [rsp+28h+arg_8], rbx
0x180003a9b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180003aa0  test    eax, eax
0x180003aa2  js      short loc_180003AB3
0x180003aa4  cmp     [rdi+8], rbx
0x180003aa8  jnz     short loc_180003AB3
0x180003aaa  mov     rax, [rsp+28h+arg_8]
0x180003aaf  mov     [rdi+8], rax
0x180003ab3  mov     rax, [rdi+8]
0x180003ab7  lea     rcx, [rax+20h]
0x180003abb  neg     rax
0x180003abe  sbb     rdi, rdi
0x180003ac1  and     rdi, rcx
0x180003ac4  jz      short loc_180003B0C
0x180003ac6  call    cs:__imp_GetCurrentThreadId
0x180003acd  nop     dword ptr [rax+rax+00h]
0x180003ad2  mov     r8d, eax
0x180003ad5  mov     r9d, eax
0x180003ad8  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180003ae2  shr     r8, 2
0x180003ae6  mul     r8
0x180003ae9  shr     rdx, 3
0x180003aed  lea     rcx, [rdx+rdx*4]
0x180003af1  add     rcx, rcx
0x180003af4  sub     r8, rcx
0x180003af7  mov     rbx, [rdi+r8*8+8]
0x180003afc  jmp     short loc_180003B07
0x180003afe  cmp     [rbx], r9d
0x180003b01  jz      short loc_180003B1B
0x180003b03  mov     rbx, [rbx+8]
0x180003b07  test    rbx, rbx
0x180003b0a  jnz     short loc_180003AFE
0x180003b0c  mov     rax, rbx
0x180003b0f  mov     rbx, [rsp+28h+arg_0]
0x180003b14  add     rsp, 20h
0x180003b18  pop     rdi
0x180003b19  retn
0x180003b1b  add     rbx, 10h
0x180003b1f  jz      short loc_180003B0C
0x180003b21  cmp     qword ptr [rbx+8], 0
0x180003b26  jnz     short loc_180003B0C
0x180003b28  lea     rax, [rdi+4]
0x180003b2c  mov     [rbx+8], rax
0x180003b30  jmp     short loc_180003B0C
```
