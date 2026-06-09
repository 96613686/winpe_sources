# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000ff70`
- end: `0x180010053`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `227`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e640`

## callees

- `0x18000b1b0`
- `0x18000ff70`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ffcd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ffcd`

## pseudocode

```c
struct wil::details_abi::ThreadLocalData *__fastcall wil::details_abi::GetThreadLocalDataCache(wil::details_abi *this)
{
  __int64 v1; // rbx
  __int64 v2; // rcx
  __int64 v3; // rcx
  struct wil::details_abi::ThreadLocalData *result; // rax
  __int64 v5; // rbx
  DWORD CurrentThreadId; // r9d
  __int64 v7; // rax
  __int64 v8; // [rsp+38h] [rbp+10h] BYREF

  v1 = wil::details_abi::g_pProcessLocalData;
  if ( !wil::details_abi::g_pProcessLocalData )
    return 0;
  if ( !*(_QWORD *)(wil::details_abi::g_pProcessLocalData + 8) )
  {
    v2 = *(_QWORD *)wil::details_abi::g_pProcessLocalData;
    v8 = 0;
    if ( (int)wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(v2, &v8) >= 0
      && !*(_QWORD *)(v1 + 8) )
    {
      *(_QWORD *)(v1 + 8) = v8;
    }
  }
  v3 = *(_QWORD *)(v1 + 8);
  result = 0;
  v5 = v3 + 32;
  if ( !v3 )
    v5 = 0;
  if ( v5 )
  {
    CurrentThreadId = GetCurrentThreadId();
    v7 = *(_QWORD *)(v5 + 8 * (((unsigned __int64)CurrentThreadId >> 2) % 0xA) + 8);
    if ( v7 )
    {
      while ( *(_DWORD *)v7 != CurrentThreadId )
      {
        v7 = *(_QWORD *)(v7 + 8);
        if ( !v7 )
          return 0;
      }
      result = (struct wil::details_abi::ThreadLocalData *)(v7 + 16);
      if ( result )
      {
        if ( !*((_QWORD *)result + 1) )
          *((_QWORD *)result + 1) = v5 + 4;
      }
    }
    else
    {
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000ff70  mov     [rsp+arg_0], rbx
0x18000ff75  push    rdi
0x18000ff76  sub     rsp, 20h
0x18000ff7a  mov     rbx, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000ff81  xor     edi, edi
0x18000ff83  test    rbx, rbx
0x18000ff86  jz      loc_180010044
0x18000ff8c  cmp     [rbx+8], rdi
0x18000ff90  jnz     short loc_18000FFB7
0x18000ff92  mov     rcx, [rbx]
0x18000ff95  lea     rdx, [rsp+28h+arg_8]
0x18000ff9a  mov     [rsp+28h+arg_8], rdi
0x18000ff9f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18000ffa4  test    eax, eax
0x18000ffa6  js      short loc_18000FFB7
0x18000ffa8  cmp     [rbx+8], rdi
0x18000ffac  jnz     short loc_18000FFB7
0x18000ffae  mov     rax, [rsp+28h+arg_8]
0x18000ffb3  mov     [rbx+8], rax
0x18000ffb7  mov     rcx, [rbx+8]
0x18000ffbb  xor     eax, eax
0x18000ffbd  test    rcx, rcx
0x18000ffc0  lea     rbx, [rcx+20h]
0x18000ffc4  cmovz   rbx, rax
0x18000ffc8  test    rbx, rbx
0x18000ffcb  jz      short loc_180010047
0x18000ffcd  call    cs:__imp_GetCurrentThreadId
0x18000ffd4  nop     dword ptr [rax+rax+00h]
0x18000ffd9  mov     r8d, eax
0x18000ffdc  mov     r9d, eax
0x18000ffdf  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000ffe9  shr     r8, 2
0x18000ffed  mul     r8
0x18000fff0  shr     rdx, 3
0x18000fff4  lea     rcx, [rdx+rdx*4]
0x18000fff8  add     rcx, rcx
0x18000fffb  sub     r8, rcx
0x18000fffe  mov     rax, [rbx+r8*8+8]
0x180010003  test    rax, rax
0x180010006  jz      short loc_180010016
0x180010008  cmp     [rax], r9d
0x18001000b  jz      short loc_180010024
0x18001000d  mov     rax, [rax+8]
0x180010011  test    rax, rax
0x180010014  jnz     short loc_180010008
0x180010016  xor     eax, eax
0x180010018  mov     rbx, [rsp+28h+arg_0]
0x18001001d  add     rsp, 20h
0x180010021  pop     rdi
0x180010022  retn
0x180010024  add     rax, 10h
0x180010028  jz      short loc_180010047
0x18001002a  cmp     [rax+8], rdi
0x18001002e  jnz     short loc_180010047
0x180010030  lea     rcx, [rbx+4]
0x180010034  mov     [rax+8], rcx
0x180010038  mov     rbx, [rsp+28h+arg_0]
0x18001003d  add     rsp, 20h
0x180010041  pop     rdi
0x180010042  retn
0x180010044  mov     rax, rdi
0x180010047  mov     rbx, [rsp+28h+arg_0]
0x18001004c  add     rsp, 20h
0x180010050  pop     rdi
0x180010051  retn
```
