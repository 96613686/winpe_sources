# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180025dec`
- end: `0x180025ea9`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001fc80`

## callees

- `0x1800254c8`
- `0x180025dec`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180025e46`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180025e46`

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
0x180025dec  mov     [rsp+arg_0], rbx
0x180025df1  push    rdi
0x180025df2  sub     rsp, 20h
0x180025df6  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180025dfd  xor     ebx, ebx
0x180025dff  test    rdi, rdi
0x180025e02  jz      loc_180025E9B
0x180025e08  cmp     [rdi+8], rbx
0x180025e0c  jnz     short loc_180025E33
0x180025e0e  mov     rcx, [rdi]
0x180025e11  lea     rdx, [rsp+28h+arg_8]
0x180025e16  mov     [rsp+28h+arg_8], rbx
0x180025e1b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180025e20  test    eax, eax
0x180025e22  js      short loc_180025E33
0x180025e24  cmp     [rdi+8], rbx
0x180025e28  jnz     short loc_180025E33
0x180025e2a  mov     rax, [rsp+28h+arg_8]
0x180025e2f  mov     [rdi+8], rax
0x180025e33  mov     rax, [rdi+8]
0x180025e37  lea     rcx, [rax+20h]
0x180025e3b  neg     rax
0x180025e3e  sbb     rdi, rdi
0x180025e41  and     rdi, rcx
0x180025e44  jz      short loc_180025E9B
0x180025e46  call    cs:__imp_GetCurrentThreadId
0x180025e4c  mov     r8d, eax
0x180025e4f  mov     r9d, eax
0x180025e52  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180025e5c  shr     r8, 2
0x180025e60  mul     r8
0x180025e63  shr     rdx, 3
0x180025e67  lea     rcx, [rdx+rdx*4]
0x180025e6b  add     rcx, rcx
0x180025e6e  sub     r8, rcx
0x180025e71  mov     rbx, [rdi+r8*8+8]
0x180025e76  test    rbx, rbx
0x180025e79  jz      short loc_180025E9B
0x180025e7b  cmp     [rbx], r9d
0x180025e7e  jz      short loc_180025E86
0x180025e80  mov     rbx, [rbx+8]
0x180025e84  jmp     short loc_180025E76
0x180025e86  add     rbx, 10h
0x180025e8a  jz      short loc_180025E9B
0x180025e8c  cmp     qword ptr [rbx+8], 0
0x180025e91  jnz     short loc_180025E9B
0x180025e93  lea     rax, [rdi+4]
0x180025e97  mov     [rbx+8], rax
0x180025e9b  mov     rax, rbx
0x180025e9e  mov     rbx, [rsp+28h+arg_0]
0x180025ea3  add     rsp, 20h
0x180025ea7  pop     rdi
0x180025ea8  retn
```
