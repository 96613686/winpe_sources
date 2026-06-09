# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1800048f4`
- end: `0x1800049af`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800040c0`

## callees

- `0x180003518`
- `0x1800048f4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000494a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000494a`

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
0x1800048f4  mov     [rsp+arg_0], rbx
0x1800048f9  push    rdi
0x1800048fa  sub     rsp, 20h
0x1800048fe  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180004905  xor     ebx, ebx
0x180004907  test    rdi, rdi
0x18000490a  jz      short loc_18000498A
0x18000490c  cmp     [rdi+8], rbx
0x180004910  jnz     short loc_180004937
0x180004912  mov     rcx, [rdi]
0x180004915  lea     rdx, [rsp+28h+arg_8]
0x18000491a  mov     [rsp+28h+arg_8], rbx
0x18000491f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180004924  test    eax, eax
0x180004926  js      short loc_180004937
0x180004928  cmp     [rdi+8], rbx
0x18000492c  jnz     short loc_180004937
0x18000492e  mov     rax, [rsp+28h+arg_8]
0x180004933  mov     [rdi+8], rax
0x180004937  mov     rax, [rdi+8]
0x18000493b  lea     rcx, [rax+20h]
0x18000493f  neg     rax
0x180004942  sbb     rdi, rdi
0x180004945  and     rdi, rcx
0x180004948  jz      short loc_18000498A
0x18000494a  call    cs:__imp_GetCurrentThreadId
0x180004950  mov     r8d, eax
0x180004953  mov     r9d, eax
0x180004956  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004960  shr     r8, 2
0x180004964  mul     r8
0x180004967  shr     rdx, 3
0x18000496b  lea     rcx, [rdx+rdx*4]
0x18000496f  add     rcx, rcx
0x180004972  sub     r8, rcx
0x180004975  mov     rbx, [rdi+r8*8+8]
0x18000497a  jmp     short loc_180004985
0x18000497c  cmp     [rbx], r9d
0x18000497f  jz      short loc_180004998
0x180004981  mov     rbx, [rbx+8]
0x180004985  test    rbx, rbx
0x180004988  jnz     short loc_18000497C
0x18000498a  mov     rax, rbx
0x18000498d  mov     rbx, [rsp+28h+arg_0]
0x180004992  add     rsp, 20h
0x180004996  pop     rdi
0x180004997  retn
0x180004998  add     rbx, 10h
0x18000499c  jz      short loc_18000498A
0x18000499e  cmp     qword ptr [rbx+8], 0
0x1800049a3  jnz     short loc_18000498A
0x1800049a5  lea     rax, [rdi+4]
0x1800049a9  mov     [rbx+8], rax
0x1800049ad  jmp     short loc_18000498A
```
