# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180009580`
- end: `0x18000961c`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `156`
- prototype: `signed __int64 __fastcall(__int64, char)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002dfe0`

## callees

- `0x180009580`
- `0x18000a2b8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009593`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009593`

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
0x180009580  push    rbx
0x180009582  push    rbp
0x180009583  push    rsi
0x180009584  push    rdi
0x180009585  sub     rsp, 28h
0x180009589  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180009590  mov     bpl, dl
0x180009593  call    cs:__imp_GetCurrentThreadId
0x180009599  mov     ebx, eax
0x18000959b  mov     esi, eax
0x18000959d  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800095a7  shr     rbx, 2
0x1800095ab  mul     rbx
0x1800095ae  shr     rdx, 3
0x1800095b2  lea     rcx, [rdx+rdx*4]
0x1800095b6  add     rcx, rcx
0x1800095b9  sub     rbx, rcx
0x1800095bc  mov     rax, [rdi+rbx*8]
0x1800095c0  jmp     short loc_1800095CA
0x1800095c2  cmp     [rax], esi
0x1800095c4  jz      short loc_18000960B
0x1800095c6  mov     rax, [rax+8]
0x1800095ca  test    rax, rax
0x1800095cd  jnz     short loc_1800095C2
0x1800095cf  test    bpl, bpl
0x1800095d2  jz      short loc_180009611
0x1800095d4  lea     edx, [rax+18h]; dwBytes
0x1800095d7  xor     ecx, ecx; dwFlags
0x1800095d9  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800095de  mov     rcx, rax
0x1800095e1  test    rax, rax
0x1800095e4  jz      short loc_180009611
0x1800095e6  mov     [rax], esi
0x1800095e8  xor     eax, eax
0x1800095ea  mov     [rcx+4], eax
0x1800095ed  mov     [rcx+8], rax
0x1800095f1  mov     [rcx+10h], rax
0x1800095f5  mov     rax, [rdi+rbx*8]
0x1800095f9  mov     [rcx+8], rax
0x1800095fd  lock cmpxchg [rdi+rbx*8], rcx
0x180009603  jnz     short loc_1800095F5
0x180009605  lea     rax, [rcx+10h]
0x180009609  jmp     short loc_180009613
0x18000960b  add     rax, 10h
0x18000960f  jmp     short loc_180009613
0x180009611  xor     eax, eax
0x180009613  add     rsp, 28h
0x180009617  pop     rdi
0x180009618  pop     rsi
0x180009619  pop     rbp
0x18000961a  pop     rbx
0x18000961b  retn
```
