# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180009834`
- end: `0x1800098ef`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180008fb0`

## callees

- `0x180007ee8`
- `0x180009834`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000988a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000988a`

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
0x180009834  mov     [rsp+arg_0], rbx
0x180009839  push    rdi
0x18000983a  sub     rsp, 20h
0x18000983e  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180009845  xor     ebx, ebx
0x180009847  test    rdi, rdi
0x18000984a  jz      short loc_1800098CA
0x18000984c  cmp     [rdi+8], rbx
0x180009850  jnz     short loc_180009877
0x180009852  mov     rcx, [rdi]
0x180009855  lea     rdx, [rsp+28h+arg_8]
0x18000985a  mov     [rsp+28h+arg_8], rbx
0x18000985f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180009864  test    eax, eax
0x180009866  js      short loc_180009877
0x180009868  cmp     [rdi+8], rbx
0x18000986c  jnz     short loc_180009877
0x18000986e  mov     rax, [rsp+28h+arg_8]
0x180009873  mov     [rdi+8], rax
0x180009877  mov     rax, [rdi+8]
0x18000987b  lea     rcx, [rax+20h]
0x18000987f  neg     rax
0x180009882  sbb     rdi, rdi
0x180009885  and     rdi, rcx
0x180009888  jz      short loc_1800098CA
0x18000988a  call    cs:__imp_GetCurrentThreadId
0x180009890  mov     r8d, eax
0x180009893  mov     r9d, eax
0x180009896  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800098a0  shr     r8, 2
0x1800098a4  mul     r8
0x1800098a7  shr     rdx, 3
0x1800098ab  lea     rcx, [rdx+rdx*4]
0x1800098af  add     rcx, rcx
0x1800098b2  sub     r8, rcx
0x1800098b5  mov     rbx, [rdi+r8*8+8]
0x1800098ba  jmp     short loc_1800098C5
0x1800098bc  cmp     [rbx], r9d
0x1800098bf  jz      short loc_1800098D8
0x1800098c1  mov     rbx, [rbx+8]
0x1800098c5  test    rbx, rbx
0x1800098c8  jnz     short loc_1800098BC
0x1800098ca  mov     rax, rbx
0x1800098cd  mov     rbx, [rsp+28h+arg_0]
0x1800098d2  add     rsp, 20h
0x1800098d6  pop     rdi
0x1800098d7  retn
0x1800098d8  add     rbx, 10h
0x1800098dc  jz      short loc_1800098CA
0x1800098de  cmp     qword ptr [rbx+8], 0
0x1800098e3  jnz     short loc_1800098CA
0x1800098e5  lea     rax, [rdi+4]
0x1800098e9  mov     [rbx+8], rax
0x1800098ed  jmp     short loc_1800098CA
```
