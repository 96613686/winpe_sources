# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x1800059fc`
- end: `0x180005a9a`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `158`
- prototype: `signed __int64 __fastcall(__int64, char)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180004010`
- `0x1800054b4`

## callees

- `0x1800059fc`
- `0x180006854`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005a0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005a0f`

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
0x1800059fc  push    rbx
0x1800059fe  push    rbp
0x1800059ff  push    rsi
0x180005a00  push    rdi
0x180005a01  sub     rsp, 28h
0x180005a05  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180005a0c  mov     bpl, dl
0x180005a0f  call    cs:__imp_GetCurrentThreadId
0x180005a15  mov     ebx, eax
0x180005a17  mov     esi, eax
0x180005a19  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180005a23  shr     rbx, 2
0x180005a27  mul     rbx
0x180005a2a  shr     rdx, 3
0x180005a2e  lea     rcx, [rdx+rdx*4]
0x180005a32  add     rcx, rcx
0x180005a35  sub     rbx, rcx
0x180005a38  mov     rax, [rdi+rbx*8]
0x180005a3c  test    rax, rax
0x180005a3f  jz      short loc_180005A51
0x180005a41  cmp     [rax], esi
0x180005a43  jz      short loc_180005A4B
0x180005a45  mov     rax, [rax+8]
0x180005a49  jmp     short loc_180005A3C
0x180005a4b  add     rax, 10h
0x180005a4f  jmp     short loc_180005A91
0x180005a51  test    bpl, bpl
0x180005a54  jz      short loc_180005A8F
0x180005a56  mov     edx, 18h; dwBytes
0x180005a5b  xor     ecx, ecx; dwFlags
0x180005a5d  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180005a62  mov     rcx, rax
0x180005a65  test    rax, rax
0x180005a68  jz      short loc_180005A8F
0x180005a6a  mov     [rax], esi
0x180005a6c  xor     eax, eax
0x180005a6e  mov     [rcx+4], eax
0x180005a71  mov     [rcx+8], rax
0x180005a75  mov     [rcx+10h], rax
0x180005a79  mov     rax, [rdi+rbx*8]
0x180005a7d  mov     [rcx+8], rax
0x180005a81  lock cmpxchg [rdi+rbx*8], rcx
0x180005a87  jnz     short loc_180005A79
0x180005a89  lea     rax, [rcx+10h]
0x180005a8d  jmp     short loc_180005A91
0x180005a8f  xor     eax, eax
0x180005a91  add     rsp, 28h
0x180005a95  pop     rdi
0x180005a96  pop     rsi
0x180005a97  pop     rbp
0x180005a98  pop     rbx
0x180005a99  retn
```
