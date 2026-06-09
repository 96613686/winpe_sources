# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x1800153bc`
- end: `0x18001545a`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `158`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180014ee4`
- `0x18001723c`

## callees

- `0x1800153bc`
- `0x180016624`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800153cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800153cf`

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
0x1800153bc  push    rbx
0x1800153be  push    rbp
0x1800153bf  push    rsi
0x1800153c0  push    rdi
0x1800153c1  sub     rsp, 28h
0x1800153c5  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800153cc  mov     bpl, dl
0x1800153cf  call    cs:__imp_GetCurrentThreadId
0x1800153d5  mov     ebx, eax
0x1800153d7  mov     esi, eax
0x1800153d9  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800153e3  shr     rbx, 2
0x1800153e7  mul     rbx
0x1800153ea  shr     rdx, 3
0x1800153ee  lea     rcx, [rdx+rdx*4]
0x1800153f2  add     rcx, rcx
0x1800153f5  sub     rbx, rcx
0x1800153f8  mov     rax, [rdi+rbx*8]
0x1800153fc  test    rax, rax
0x1800153ff  jz      short loc_180015411
0x180015401  cmp     [rax], esi
0x180015403  jz      short loc_18001540B
0x180015405  mov     rax, [rax+8]
0x180015409  jmp     short loc_1800153FC
0x18001540b  add     rax, 10h
0x18001540f  jmp     short loc_180015451
0x180015411  test    bpl, bpl
0x180015414  jz      short loc_18001544F
0x180015416  mov     edx, 18h; dwBytes
0x18001541b  xor     ecx, ecx; dwFlags
0x18001541d  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180015422  mov     rcx, rax
0x180015425  test    rax, rax
0x180015428  jz      short loc_18001544F
0x18001542a  mov     [rax], esi
0x18001542c  xor     eax, eax
0x18001542e  mov     [rcx+4], eax
0x180015431  mov     [rcx+8], rax
0x180015435  mov     [rcx+10h], rax
0x180015439  mov     rax, [rdi+rbx*8]
0x18001543d  mov     [rcx+8], rax
0x180015441  lock cmpxchg [rdi+rbx*8], rcx
0x180015447  jnz     short loc_180015439
0x180015449  lea     rax, [rcx+10h]
0x18001544d  jmp     short loc_180015451
0x18001544f  xor     eax, eax
0x180015451  add     rsp, 28h
0x180015455  pop     rdi
0x180015456  pop     rsi
0x180015457  pop     rbp
0x180015458  pop     rbx
0x180015459  retn
```
