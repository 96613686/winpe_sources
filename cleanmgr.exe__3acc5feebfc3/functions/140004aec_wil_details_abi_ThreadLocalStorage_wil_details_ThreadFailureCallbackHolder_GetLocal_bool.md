# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x140004aec`
- end: `0x140004b8a`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `158`
- prototype: `signed __int64 __fastcall(__int64, char)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140004614`

## callees

- `0x140004aec`
- `0x1400056d8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004aff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004aff`

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
0x140004aec  push    rbx
0x140004aee  push    rbp
0x140004aef  push    rsi
0x140004af0  push    rdi
0x140004af1  sub     rsp, 28h
0x140004af5  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140004afc  mov     bpl, dl
0x140004aff  call    cs:__imp_GetCurrentThreadId
0x140004b05  mov     ebx, eax
0x140004b07  mov     esi, eax
0x140004b09  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140004b13  shr     rbx, 2
0x140004b17  mul     rbx
0x140004b1a  shr     rdx, 3
0x140004b1e  lea     rcx, [rdx+rdx*4]
0x140004b22  add     rcx, rcx
0x140004b25  sub     rbx, rcx
0x140004b28  mov     rax, [rdi+rbx*8]
0x140004b2c  test    rax, rax
0x140004b2f  jz      short loc_140004B41
0x140004b31  cmp     [rax], esi
0x140004b33  jz      short loc_140004B3B
0x140004b35  mov     rax, [rax+8]
0x140004b39  jmp     short loc_140004B2C
0x140004b3b  add     rax, 10h
0x140004b3f  jmp     short loc_140004B81
0x140004b41  test    bpl, bpl
0x140004b44  jz      short loc_140004B7F
0x140004b46  mov     edx, 18h; dwBytes
0x140004b4b  xor     ecx, ecx; dwFlags
0x140004b4d  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140004b52  mov     rcx, rax
0x140004b55  test    rax, rax
0x140004b58  jz      short loc_140004B7F
0x140004b5a  mov     [rax], esi
0x140004b5c  xor     eax, eax
0x140004b5e  mov     [rcx+4], eax
0x140004b61  mov     [rcx+8], rax
0x140004b65  mov     [rcx+10h], rax
0x140004b69  mov     rax, [rdi+rbx*8]
0x140004b6d  mov     [rcx+8], rax
0x140004b71  lock cmpxchg [rdi+rbx*8], rcx
0x140004b77  jnz     short loc_140004B69
0x140004b79  lea     rax, [rcx+10h]
0x140004b7d  jmp     short loc_140004B81
0x140004b7f  xor     eax, eax
0x140004b81  add     rsp, 28h
0x140004b85  pop     rdi
0x140004b86  pop     rsi
0x140004b87  pop     rbp
0x140004b88  pop     rbx
0x140004b89  retn
```
