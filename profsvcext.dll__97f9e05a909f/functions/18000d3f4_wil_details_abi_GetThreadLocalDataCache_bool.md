# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000d3f4`
- end: `0x18000d4b1`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000cdf0`

## callees

- `0x18000c928`
- `0x18000d3f4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d44e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d44e`

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
0x18000d3f4  mov     [rsp+arg_0], rbx
0x18000d3f9  push    rdi
0x18000d3fa  sub     rsp, 20h
0x18000d3fe  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000d405  xor     ebx, ebx
0x18000d407  test    rdi, rdi
0x18000d40a  jz      loc_18000D4A3
0x18000d410  cmp     [rdi+8], rbx
0x18000d414  jnz     short loc_18000D43B
0x18000d416  mov     rcx, [rdi]
0x18000d419  lea     rdx, [rsp+28h+arg_8]
0x18000d41e  mov     [rsp+28h+arg_8], rbx
0x18000d423  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18000d428  test    eax, eax
0x18000d42a  js      short loc_18000D43B
0x18000d42c  cmp     [rdi+8], rbx
0x18000d430  jnz     short loc_18000D43B
0x18000d432  mov     rax, [rsp+28h+arg_8]
0x18000d437  mov     [rdi+8], rax
0x18000d43b  mov     rax, [rdi+8]
0x18000d43f  lea     rcx, [rax+20h]
0x18000d443  neg     rax
0x18000d446  sbb     rdi, rdi
0x18000d449  and     rdi, rcx
0x18000d44c  jz      short loc_18000D4A3
0x18000d44e  call    cs:__imp_GetCurrentThreadId
0x18000d454  mov     r8d, eax
0x18000d457  mov     r9d, eax
0x18000d45a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000d464  shr     r8, 2
0x18000d468  mul     r8
0x18000d46b  shr     rdx, 3
0x18000d46f  lea     rcx, [rdx+rdx*4]
0x18000d473  add     rcx, rcx
0x18000d476  sub     r8, rcx
0x18000d479  mov     rbx, [rdi+r8*8+8]
0x18000d47e  test    rbx, rbx
0x18000d481  jz      short loc_18000D4A3
0x18000d483  cmp     [rbx], r9d
0x18000d486  jz      short loc_18000D48E
0x18000d488  mov     rbx, [rbx+8]
0x18000d48c  jmp     short loc_18000D47E
0x18000d48e  add     rbx, 10h
0x18000d492  jz      short loc_18000D4A3
0x18000d494  cmp     qword ptr [rbx+8], 0
0x18000d499  jnz     short loc_18000D4A3
0x18000d49b  lea     rax, [rdi+4]
0x18000d49f  mov     [rbx+8], rax
0x18000d4a3  mov     rax, rbx
0x18000d4a6  mov     rbx, [rsp+28h+arg_0]
0x18000d4ab  add     rsp, 20h
0x18000d4af  pop     rdi
0x18000d4b0  retn
```
