# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1800073a8`
- end: `0x18000746e`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `198`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180006ba0`

## callees

- `0x180005a1c`
- `0x1800073a8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007402`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007402`

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
0x1800073a8  mov     [rsp+arg_0], rbx
0x1800073ad  push    rdi
0x1800073ae  sub     rsp, 20h
0x1800073b2  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1800073b9  xor     ebx, ebx
0x1800073bb  test    rdi, rdi
0x1800073be  jz      loc_180007448
0x1800073c4  cmp     [rdi+8], rbx
0x1800073c8  jnz     short loc_1800073EF
0x1800073ca  mov     rcx, [rdi]
0x1800073cd  lea     rdx, [rsp+28h+arg_8]
0x1800073d2  mov     [rsp+28h+arg_8], rbx
0x1800073d7  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1800073dc  test    eax, eax
0x1800073de  js      short loc_1800073EF
0x1800073e0  cmp     [rdi+8], rbx
0x1800073e4  jnz     short loc_1800073EF
0x1800073e6  mov     rax, [rsp+28h+arg_8]
0x1800073eb  mov     [rdi+8], rax
0x1800073ef  mov     rax, [rdi+8]
0x1800073f3  lea     rcx, [rax+20h]
0x1800073f7  neg     rax
0x1800073fa  sbb     rdi, rdi
0x1800073fd  and     rdi, rcx
0x180007400  jz      short loc_180007448
0x180007402  call    cs:__imp_GetCurrentThreadId
0x180007409  nop     dword ptr [rax+rax+00h]
0x18000740e  mov     r8d, eax
0x180007411  mov     r9d, eax
0x180007414  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000741e  shr     r8, 2
0x180007422  mul     r8
0x180007425  shr     rdx, 3
0x180007429  lea     rcx, [rdx+rdx*4]
0x18000742d  add     rcx, rcx
0x180007430  sub     r8, rcx
0x180007433  mov     rbx, [rdi+r8*8+8]
0x180007438  jmp     short loc_180007443
0x18000743a  cmp     [rbx], r9d
0x18000743d  jz      short loc_180007457
0x18000743f  mov     rbx, [rbx+8]
0x180007443  test    rbx, rbx
0x180007446  jnz     short loc_18000743A
0x180007448  mov     rax, rbx
0x18000744b  mov     rbx, [rsp+28h+arg_0]
0x180007450  add     rsp, 20h
0x180007454  pop     rdi
0x180007455  retn
0x180007457  add     rbx, 10h
0x18000745b  jz      short loc_180007448
0x18000745d  cmp     qword ptr [rbx+8], 0
0x180007462  jnz     short loc_180007448
0x180007464  lea     rax, [rdi+4]
0x180007468  mov     [rbx+8], rax
0x18000746c  jmp     short loc_180007448
```
