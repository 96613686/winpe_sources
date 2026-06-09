# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180009164`
- end: `0x180009221`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180008a60`

## callees

- `0x180008058`
- `0x180009164`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800091be`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800091be`

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
0x180009164  mov     [rsp+arg_0], rbx
0x180009169  push    rdi
0x18000916a  sub     rsp, 20h
0x18000916e  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180009175  xor     ebx, ebx
0x180009177  test    rdi, rdi
0x18000917a  jz      loc_180009213
0x180009180  cmp     [rdi+8], rbx
0x180009184  jnz     short loc_1800091AB
0x180009186  mov     rcx, [rdi]
0x180009189  lea     rdx, [rsp+28h+arg_8]
0x18000918e  mov     [rsp+28h+arg_8], rbx
0x180009193  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180009198  test    eax, eax
0x18000919a  js      short loc_1800091AB
0x18000919c  cmp     [rdi+8], rbx
0x1800091a0  jnz     short loc_1800091AB
0x1800091a2  mov     rax, [rsp+28h+arg_8]
0x1800091a7  mov     [rdi+8], rax
0x1800091ab  mov     rax, [rdi+8]
0x1800091af  lea     rcx, [rax+20h]
0x1800091b3  neg     rax
0x1800091b6  sbb     rdi, rdi
0x1800091b9  and     rdi, rcx
0x1800091bc  jz      short loc_180009213
0x1800091be  call    cs:__imp_GetCurrentThreadId
0x1800091c4  mov     r8d, eax
0x1800091c7  mov     r9d, eax
0x1800091ca  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800091d4  shr     r8, 2
0x1800091d8  mul     r8
0x1800091db  shr     rdx, 3
0x1800091df  lea     rcx, [rdx+rdx*4]
0x1800091e3  add     rcx, rcx
0x1800091e6  sub     r8, rcx
0x1800091e9  mov     rbx, [rdi+r8*8+8]
0x1800091ee  test    rbx, rbx
0x1800091f1  jz      short loc_180009213
0x1800091f3  cmp     [rbx], r9d
0x1800091f6  jz      short loc_1800091FE
0x1800091f8  mov     rbx, [rbx+8]
0x1800091fc  jmp     short loc_1800091EE
0x1800091fe  add     rbx, 10h
0x180009202  jz      short loc_180009213
0x180009204  cmp     qword ptr [rbx+8], 0
0x180009209  jnz     short loc_180009213
0x18000920b  lea     rax, [rdi+4]
0x18000920f  mov     [rbx+8], rax
0x180009213  mov     rax, rbx
0x180009216  mov     rbx, [rsp+28h+arg_0]
0x18000921b  add     rsp, 20h
0x18000921f  pop     rdi
0x180009220  retn
```
