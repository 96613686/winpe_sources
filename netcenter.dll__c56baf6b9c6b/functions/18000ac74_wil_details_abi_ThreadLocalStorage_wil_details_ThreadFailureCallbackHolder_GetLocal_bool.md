# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18000ac74`
- end: `0x18000ad12`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `158`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a55c`
- `0x180011e4c`

## callees

- `0x18000ac74`
- `0x18000f700`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ac87`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ac87`

## pseudocode

```c
signed __int64 __fastcall wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
        __int64 a1,
        char a2)
{
  __int64 v2; // rdi
  DWORD CurrentThreadId; // esi
  unsigned __int64 v5; // r8
  unsigned __int64 v6; // rbx
  __int64 i; // rax
  DWORD *v9; // rax
  signed __int64 v10; // rcx
  signed __int64 v11; // rax

  v2 = wil::details::g_pThreadFailureCallbacks;
  CurrentThreadId = GetCurrentThreadId();
  v6 = ((unsigned __int64)CurrentThreadId >> 2) % 0xA;
  for ( i = *(_QWORD *)(v2 + 8 * v6); i; i = *(_QWORD *)(i + 8) )
  {
    if ( *(_DWORD *)i == CurrentThreadId )
      return i + 16;
  }
  if ( !a2 )
    return 0;
  v9 = (DWORD *)wil::details::ProcessHeapAlloc(0, 0x18u, v5);
  v10 = (signed __int64)v9;
  if ( !v9 )
    return 0;
  *v9 = CurrentThreadId;
  v9[1] = 0;
  *((_QWORD *)v9 + 1) = 0;
  *((_QWORD *)v9 + 2) = 0;
  do
  {
    v11 = *(_QWORD *)(v2 + 8 * v6);
    *(_QWORD *)(v10 + 8) = v11;
  }
  while ( v11 != _InterlockedCompareExchange64((volatile signed __int64 *)(v2 + 8 * v6), v10, v11) );
  return v10 + 16;
}

```

## disassembly

```asm
0x18000ac74  push    rbx
0x18000ac76  push    rbp
0x18000ac77  push    rsi
0x18000ac78  push    rdi
0x18000ac79  sub     rsp, 28h
0x18000ac7d  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000ac84  mov     bpl, dl
0x18000ac87  call    cs:__imp_GetCurrentThreadId
0x18000ac8d  mov     ebx, eax
0x18000ac8f  mov     esi, eax
0x18000ac91  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000ac9b  shr     rbx, 2
0x18000ac9f  mul     rbx
0x18000aca2  shr     rdx, 3
0x18000aca6  lea     rcx, [rdx+rdx*4]
0x18000acaa  add     rcx, rcx
0x18000acad  sub     rbx, rcx
0x18000acb0  mov     rax, [rdi+rbx*8]
0x18000acb4  test    rax, rax
0x18000acb7  jz      short loc_18000ACC9
0x18000acb9  cmp     [rax], esi
0x18000acbb  jz      short loc_18000ACC3
0x18000acbd  mov     rax, [rax+8]
0x18000acc1  jmp     short loc_18000ACB4
0x18000acc3  add     rax, 10h
0x18000acc7  jmp     short loc_18000AD09
0x18000acc9  test    bpl, bpl
0x18000accc  jz      short loc_18000AD07
0x18000acce  mov     edx, 18h; dwBytes
0x18000acd3  xor     ecx, ecx; dwFlags
0x18000acd5  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000acda  mov     rcx, rax
0x18000acdd  test    rax, rax
0x18000ace0  jz      short loc_18000AD07
0x18000ace2  mov     [rax], esi
0x18000ace4  xor     eax, eax
0x18000ace6  mov     [rcx+4], eax
0x18000ace9  mov     [rcx+8], rax
0x18000aced  mov     [rcx+10h], rax
0x18000acf1  mov     rax, [rdi+rbx*8]
0x18000acf5  mov     [rcx+8], rax
0x18000acf9  lock cmpxchg [rdi+rbx*8], rcx
0x18000acff  jnz     short loc_18000ACF1
0x18000ad01  lea     rax, [rcx+10h]
0x18000ad05  jmp     short loc_18000AD09
0x18000ad07  xor     eax, eax
0x18000ad09  add     rsp, 28h
0x18000ad0d  pop     rdi
0x18000ad0e  pop     rsi
0x18000ad0f  pop     rbp
0x18000ad10  pop     rbx
0x18000ad11  retn
```
