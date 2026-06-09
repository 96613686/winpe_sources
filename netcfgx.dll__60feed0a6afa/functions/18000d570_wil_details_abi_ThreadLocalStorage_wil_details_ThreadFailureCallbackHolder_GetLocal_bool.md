# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18000d570`
- end: `0x18000d60c`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000f814`

## callees

- `0x18000d570`
- `0x18000e8cc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d583`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d583`

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
0x18000d570  push    rbx
0x18000d572  push    rbp
0x18000d573  push    rsi
0x18000d574  push    rdi
0x18000d575  sub     rsp, 28h
0x18000d579  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000d580  mov     bpl, dl
0x18000d583  call    cs:__imp_GetCurrentThreadId
0x18000d589  mov     ebx, eax
0x18000d58b  mov     esi, eax
0x18000d58d  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000d597  shr     rbx, 2
0x18000d59b  mul     rbx
0x18000d59e  shr     rdx, 3
0x18000d5a2  lea     rcx, [rdx+rdx*4]
0x18000d5a6  add     rcx, rcx
0x18000d5a9  sub     rbx, rcx
0x18000d5ac  mov     rax, [rdi+rbx*8]
0x18000d5b0  jmp     short loc_18000D5BA
0x18000d5b2  cmp     [rax], esi
0x18000d5b4  jz      short loc_18000D5FB
0x18000d5b6  mov     rax, [rax+8]
0x18000d5ba  test    rax, rax
0x18000d5bd  jnz     short loc_18000D5B2
0x18000d5bf  test    bpl, bpl
0x18000d5c2  jz      short loc_18000D601
0x18000d5c4  lea     edx, [rax+18h]; dwBytes
0x18000d5c7  xor     ecx, ecx; dwFlags
0x18000d5c9  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000d5ce  mov     rcx, rax
0x18000d5d1  test    rax, rax
0x18000d5d4  jz      short loc_18000D601
0x18000d5d6  mov     [rax], esi
0x18000d5d8  xor     eax, eax
0x18000d5da  mov     [rcx+4], eax
0x18000d5dd  mov     [rcx+8], rax
0x18000d5e1  mov     [rcx+10h], rax
0x18000d5e5  mov     rax, [rdi+rbx*8]
0x18000d5e9  mov     [rcx+8], rax
0x18000d5ed  lock cmpxchg [rdi+rbx*8], rcx
0x18000d5f3  jnz     short loc_18000D5E5
0x18000d5f5  lea     rax, [rcx+10h]
0x18000d5f9  jmp     short loc_18000D603
0x18000d5fb  add     rax, 10h
0x18000d5ff  jmp     short loc_18000D603
0x18000d601  xor     eax, eax
0x18000d603  add     rsp, 28h
0x18000d607  pop     rdi
0x18000d608  pop     rsi
0x18000d609  pop     rbp
0x18000d60a  pop     rbx
0x18000d60b  retn
```
