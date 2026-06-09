# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x140007440`
- end: `0x1400074dc`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140012754`

## callees

- `0x140007440`
- `0x1400083f8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140007453`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140007453`

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
0x140007440  push    rbx
0x140007442  push    rbp
0x140007443  push    rsi
0x140007444  push    rdi
0x140007445  sub     rsp, 28h
0x140007449  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140007450  mov     bpl, dl
0x140007453  call    cs:__imp_GetCurrentThreadId
0x140007459  mov     ebx, eax
0x14000745b  mov     esi, eax
0x14000745d  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140007467  shr     rbx, 2
0x14000746b  mul     rbx
0x14000746e  shr     rdx, 3
0x140007472  lea     rcx, [rdx+rdx*4]
0x140007476  add     rcx, rcx
0x140007479  sub     rbx, rcx
0x14000747c  mov     rax, [rdi+rbx*8]
0x140007480  jmp     short loc_14000748A
0x140007482  cmp     [rax], esi
0x140007484  jz      short loc_1400074CB
0x140007486  mov     rax, [rax+8]
0x14000748a  test    rax, rax
0x14000748d  jnz     short loc_140007482
0x14000748f  test    bpl, bpl
0x140007492  jz      short loc_1400074D1
0x140007494  lea     edx, [rax+18h]; dwBytes
0x140007497  xor     ecx, ecx; dwFlags
0x140007499  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000749e  mov     rcx, rax
0x1400074a1  test    rax, rax
0x1400074a4  jz      short loc_1400074D1
0x1400074a6  mov     [rax], esi
0x1400074a8  xor     eax, eax
0x1400074aa  mov     [rcx+4], eax
0x1400074ad  mov     [rcx+8], rax
0x1400074b1  mov     [rcx+10h], rax
0x1400074b5  mov     rax, [rdi+rbx*8]
0x1400074b9  mov     [rcx+8], rax
0x1400074bd  lock cmpxchg [rdi+rbx*8], rcx
0x1400074c3  jnz     short loc_1400074B5
0x1400074c5  lea     rax, [rcx+10h]
0x1400074c9  jmp     short loc_1400074D3
0x1400074cb  add     rax, 10h
0x1400074cf  jmp     short loc_1400074D3
0x1400074d1  xor     eax, eax
0x1400074d3  add     rsp, 28h
0x1400074d7  pop     rdi
0x1400074d8  pop     rsi
0x1400074d9  pop     rbp
0x1400074da  pop     rbx
0x1400074db  retn
```
