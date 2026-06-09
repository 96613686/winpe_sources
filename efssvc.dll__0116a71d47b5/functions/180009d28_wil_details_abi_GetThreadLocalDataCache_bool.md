# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180009d28`
- end: `0x180009de3`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800096c0`

## callees

- `0x180008fc8`
- `0x180009d28`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009d7e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009d7e`

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
0x180009d28  mov     [rsp+arg_0], rbx
0x180009d2d  push    rdi
0x180009d2e  sub     rsp, 20h
0x180009d32  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180009d39  xor     ebx, ebx
0x180009d3b  test    rdi, rdi
0x180009d3e  jz      short loc_180009DBE
0x180009d40  cmp     [rdi+8], rbx
0x180009d44  jnz     short loc_180009D6B
0x180009d46  mov     rcx, [rdi]
0x180009d49  lea     rdx, [rsp+28h+arg_8]
0x180009d4e  mov     [rsp+28h+arg_8], rbx
0x180009d53  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180009d58  test    eax, eax
0x180009d5a  js      short loc_180009D6B
0x180009d5c  cmp     [rdi+8], rbx
0x180009d60  jnz     short loc_180009D6B
0x180009d62  mov     rax, [rsp+28h+arg_8]
0x180009d67  mov     [rdi+8], rax
0x180009d6b  mov     rax, [rdi+8]
0x180009d6f  lea     rcx, [rax+20h]
0x180009d73  neg     rax
0x180009d76  sbb     rdi, rdi
0x180009d79  and     rdi, rcx
0x180009d7c  jz      short loc_180009DBE
0x180009d7e  call    cs:__imp_GetCurrentThreadId
0x180009d84  mov     r8d, eax
0x180009d87  mov     r9d, eax
0x180009d8a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180009d94  shr     r8, 2
0x180009d98  mul     r8
0x180009d9b  shr     rdx, 3
0x180009d9f  lea     rcx, [rdx+rdx*4]
0x180009da3  add     rcx, rcx
0x180009da6  sub     r8, rcx
0x180009da9  mov     rbx, [rdi+r8*8+8]
0x180009dae  jmp     short loc_180009DB9
0x180009db0  cmp     [rbx], r9d
0x180009db3  jz      short loc_180009DCC
0x180009db5  mov     rbx, [rbx+8]
0x180009db9  test    rbx, rbx
0x180009dbc  jnz     short loc_180009DB0
0x180009dbe  mov     rax, rbx
0x180009dc1  mov     rbx, [rsp+28h+arg_0]
0x180009dc6  add     rsp, 20h
0x180009dca  pop     rdi
0x180009dcb  retn
0x180009dcc  add     rbx, 10h
0x180009dd0  jz      short loc_180009DBE
0x180009dd2  cmp     qword ptr [rbx+8], 0
0x180009dd7  jnz     short loc_180009DBE
0x180009dd9  lea     rax, [rdi+4]
0x180009ddd  mov     [rbx+8], rax
0x180009de1  jmp     short loc_180009DBE
```
