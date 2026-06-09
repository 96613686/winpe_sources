# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180006340`
- end: `0x1800063dc`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `156`
- prototype: `signed __int64 __fastcall(__int64, char)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180018e0c`

## callees

- `0x180006340`
- `0x180006eac`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006353`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006353`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
signed __int64 __fastcall wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
        __int64 a1,
        char a2)
{
  __int64 v2; // rdi
  DWORD CurrentThreadId; // esi
  unsigned __int64 v5; // r8
  unsigned __int64 v6; // rbx
  __int64 i; // rax
  DWORD *v8; // rax
  signed __int64 v9; // rcx
  signed __int64 v10; // rax

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
  v8 = (DWORD *)wil::details::ProcessHeapAlloc(0, 0x18u, v5);
  v9 = (signed __int64)v8;
  if ( !v8 )
    return 0;
  *v8 = CurrentThreadId;
  v8[1] = 0;
  *((_QWORD *)v8 + 1) = 0;
  *((_QWORD *)v8 + 2) = 0;
  do
  {
    v10 = *(_QWORD *)(v2 + 8 * v6);
    *(_QWORD *)(v9 + 8) = v10;
  }
  while ( v10 != _InterlockedCompareExchange64((volatile signed __int64 *)(v2 + 8 * v6), v9, v10) );
  return v9 + 16;
}

```

## disassembly

```asm
0x180006340  push    rbx
0x180006342  push    rbp
0x180006343  push    rsi
0x180006344  push    rdi
0x180006345  sub     rsp, 28h
0x180006349  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180006350  mov     bpl, dl
0x180006353  call    cs:__imp_GetCurrentThreadId
0x180006359  mov     ebx, eax
0x18000635b  mov     esi, eax
0x18000635d  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180006367  shr     rbx, 2
0x18000636b  mul     rbx
0x18000636e  shr     rdx, 3
0x180006372  lea     rcx, [rdx+rdx*4]
0x180006376  add     rcx, rcx
0x180006379  sub     rbx, rcx
0x18000637c  mov     rax, [rdi+rbx*8]
0x180006380  jmp     short loc_18000638A
0x180006382  cmp     [rax], esi
0x180006384  jz      short loc_1800063CB
0x180006386  mov     rax, [rax+8]
0x18000638a  test    rax, rax
0x18000638d  jnz     short loc_180006382
0x18000638f  test    bpl, bpl
0x180006392  jz      short loc_1800063D1
0x180006394  lea     edx, [rax+18h]; dwBytes
0x180006397  xor     ecx, ecx; dwFlags
0x180006399  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000639e  mov     rcx, rax
0x1800063a1  test    rax, rax
0x1800063a4  jz      short loc_1800063D1
0x1800063a6  mov     [rax], esi
0x1800063a8  xor     eax, eax
0x1800063aa  mov     [rcx+4], eax
0x1800063ad  mov     [rcx+8], rax
0x1800063b1  mov     [rcx+10h], rax
0x1800063b5  mov     rax, [rdi+rbx*8]
0x1800063b9  mov     [rcx+8], rax
0x1800063bd  lock cmpxchg [rdi+rbx*8], rcx
0x1800063c3  jnz     short loc_1800063B5
0x1800063c5  lea     rax, [rcx+10h]
0x1800063c9  jmp     short loc_1800063D3
0x1800063cb  add     rax, 10h
0x1800063cf  jmp     short loc_1800063D3
0x1800063d1  xor     eax, eax
0x1800063d3  add     rsp, 28h
0x1800063d7  pop     rdi
0x1800063d8  pop     rsi
0x1800063d9  pop     rbp
0x1800063da  pop     rbx
0x1800063db  retn
```
