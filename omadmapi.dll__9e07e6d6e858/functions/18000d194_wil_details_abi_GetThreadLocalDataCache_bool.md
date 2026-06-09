# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000d194`
- end: `0x18000d25a`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `198`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ccd0`

## callees

- `0x18000a8a4`
- `0x18000d194`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d1ee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d1ee`

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
0x18000d194  mov     [rsp+arg_0], rbx
0x18000d199  push    rdi
0x18000d19a  sub     rsp, 20h
0x18000d19e  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000d1a5  xor     ebx, ebx
0x18000d1a7  test    rdi, rdi
0x18000d1aa  jz      loc_18000D234
0x18000d1b0  cmp     [rdi+8], rbx
0x18000d1b4  jnz     short loc_18000D1DB
0x18000d1b6  mov     rcx, [rdi]
0x18000d1b9  lea     rdx, [rsp+28h+arg_8]
0x18000d1be  mov     [rsp+28h+arg_8], rbx
0x18000d1c3  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18000d1c8  test    eax, eax
0x18000d1ca  js      short loc_18000D1DB
0x18000d1cc  cmp     [rdi+8], rbx
0x18000d1d0  jnz     short loc_18000D1DB
0x18000d1d2  mov     rax, [rsp+28h+arg_8]
0x18000d1d7  mov     [rdi+8], rax
0x18000d1db  mov     rax, [rdi+8]
0x18000d1df  lea     rcx, [rax+20h]
0x18000d1e3  neg     rax
0x18000d1e6  sbb     rdi, rdi
0x18000d1e9  and     rdi, rcx
0x18000d1ec  jz      short loc_18000D234
0x18000d1ee  call    cs:__imp_GetCurrentThreadId
0x18000d1f5  nop     dword ptr [rax+rax+00h]
0x18000d1fa  mov     r8d, eax
0x18000d1fd  mov     r9d, eax
0x18000d200  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000d20a  shr     r8, 2
0x18000d20e  mul     r8
0x18000d211  shr     rdx, 3
0x18000d215  lea     rcx, [rdx+rdx*4]
0x18000d219  add     rcx, rcx
0x18000d21c  sub     r8, rcx
0x18000d21f  mov     rbx, [rdi+r8*8+8]
0x18000d224  jmp     short loc_18000D22F
0x18000d226  cmp     [rbx], r9d
0x18000d229  jz      short loc_18000D243
0x18000d22b  mov     rbx, [rbx+8]
0x18000d22f  test    rbx, rbx
0x18000d232  jnz     short loc_18000D226
0x18000d234  mov     rax, rbx
0x18000d237  mov     rbx, [rsp+28h+arg_0]
0x18000d23c  add     rsp, 20h
0x18000d240  pop     rdi
0x18000d241  retn
0x18000d243  add     rbx, 10h
0x18000d247  jz      short loc_18000D234
0x18000d249  cmp     qword ptr [rbx+8], 0
0x18000d24e  jnz     short loc_18000D234
0x18000d250  lea     rax, [rdi+4]
0x18000d254  mov     [rbx+8], rax
0x18000d258  jmp     short loc_18000D234
```
