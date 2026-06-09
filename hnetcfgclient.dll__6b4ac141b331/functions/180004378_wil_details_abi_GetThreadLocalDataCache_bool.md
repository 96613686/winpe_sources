# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180004378`
- end: `0x180004435`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003d00`

## callees

- `0x180003860`
- `0x180004378`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800043d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800043d2`

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
0x180004378  mov     [rsp+arg_0], rbx
0x18000437d  push    rdi
0x18000437e  sub     rsp, 20h
0x180004382  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180004389  xor     ebx, ebx
0x18000438b  test    rdi, rdi
0x18000438e  jz      loc_180004427
0x180004394  cmp     [rdi+8], rbx
0x180004398  jnz     short loc_1800043BF
0x18000439a  mov     rcx, [rdi]
0x18000439d  lea     rdx, [rsp+28h+arg_8]
0x1800043a2  mov     [rsp+28h+arg_8], rbx
0x1800043a7  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1800043ac  test    eax, eax
0x1800043ae  js      short loc_1800043BF
0x1800043b0  cmp     [rdi+8], rbx
0x1800043b4  jnz     short loc_1800043BF
0x1800043b6  mov     rax, [rsp+28h+arg_8]
0x1800043bb  mov     [rdi+8], rax
0x1800043bf  mov     rax, [rdi+8]
0x1800043c3  lea     rcx, [rax+20h]
0x1800043c7  neg     rax
0x1800043ca  sbb     rdi, rdi
0x1800043cd  and     rdi, rcx
0x1800043d0  jz      short loc_180004427
0x1800043d2  call    cs:__imp_GetCurrentThreadId
0x1800043d8  mov     r8d, eax
0x1800043db  mov     r9d, eax
0x1800043de  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800043e8  shr     r8, 2
0x1800043ec  mul     r8
0x1800043ef  shr     rdx, 3
0x1800043f3  lea     rcx, [rdx+rdx*4]
0x1800043f7  add     rcx, rcx
0x1800043fa  sub     r8, rcx
0x1800043fd  mov     rbx, [rdi+r8*8+8]
0x180004402  test    rbx, rbx
0x180004405  jz      short loc_180004427
0x180004407  cmp     [rbx], r9d
0x18000440a  jz      short loc_180004412
0x18000440c  mov     rbx, [rbx+8]
0x180004410  jmp     short loc_180004402
0x180004412  add     rbx, 10h
0x180004416  jz      short loc_180004427
0x180004418  cmp     qword ptr [rbx+8], 0
0x18000441d  jnz     short loc_180004427
0x18000441f  lea     rax, [rdi+4]
0x180004423  mov     [rbx+8], rax
0x180004427  mov     rax, rbx
0x18000442a  mov     rbx, [rsp+28h+arg_0]
0x18000442f  add     rsp, 20h
0x180004433  pop     rdi
0x180004434  retn
```
