# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180008c30`
- end: `0x180008ce6`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `182`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006074`
- `0x180008bb0`

## callees

- `0x180008c30`
- `0x18000f78c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008c43`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008c43`

## pseudocode

```c
signed __int64 __fastcall wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
        __int64 a1,
        char a2)
{
  __int64 v2; // rdi
  DWORD CurrentThreadId; // ebx
  unsigned __int64 v5; // r8
  __int64 v6; // rsi
  __int64 i; // rax
  DWORD *v9; // rax
  signed __int64 v10; // rcx
  signed __int64 v11; // rax

  v2 = wil::details::g_pThreadFailureCallbacks;
  CurrentThreadId = GetCurrentThreadId();
  v5 = ((unsigned __int64)CurrentThreadId >> 2) % 0xA;
  v6 = 8 * v5;
  for ( i = *(_QWORD *)(8 * v5 + v2); i; i = *(_QWORD *)(i + 8) )
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
    v11 = *(_QWORD *)(v6 + v2);
    *(_QWORD *)(v10 + 8) = v11;
  }
  while ( v11 != _InterlockedCompareExchange64((volatile signed __int64 *)(v6 + v2), v10, v11) );
  return v10 + 16;
}

```

## disassembly

```asm
0x180008c30  push    rbx
0x180008c32  push    rbp
0x180008c33  push    rsi
0x180008c34  push    rdi
0x180008c35  sub     rsp, 28h
0x180008c39  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180008c40  movzx   ebp, dl
0x180008c43  call    cs:__imp_GetCurrentThreadId
0x180008c4a  nop     dword ptr [rax+rax+00h]
0x180008c4f  mov     r8d, eax
0x180008c52  mov     ebx, eax
0x180008c54  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180008c5e  shr     r8, 2
0x180008c62  mul     r8
0x180008c65  shr     rdx, 3
0x180008c69  lea     rcx, [rdx+rdx*4]
0x180008c6d  add     rcx, rcx
0x180008c70  sub     r8, rcx; unsigned __int64
0x180008c73  lea     rsi, ds:0[r8*8]
0x180008c7b  mov     rax, [rsi+rdi]
0x180008c7f  test    rax, rax
0x180008c82  jz      short loc_180008C9C
0x180008c84  cmp     [rax], ebx
0x180008c86  jz      short loc_180008C8E
0x180008c88  mov     rax, [rax+8]
0x180008c8c  jmp     short loc_180008C7F
0x180008c8e  add     rax, 10h
0x180008c92  add     rsp, 28h
0x180008c96  pop     rdi
0x180008c97  pop     rsi
0x180008c98  pop     rbp
0x180008c99  pop     rbx
0x180008c9a  retn
0x180008c9c  test    bpl, bpl
0x180008c9f  jnz     short loc_180008CA5
0x180008ca1  xor     eax, eax
0x180008ca3  jmp     short loc_180008C92
0x180008ca5  mov     edx, 18h; dwBytes
0x180008caa  xor     ecx, ecx; dwFlags
0x180008cac  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180008cb1  mov     rcx, rax
0x180008cb4  test    rax, rax
0x180008cb7  jz      short loc_180008CA1
0x180008cb9  mov     [rax], ebx
0x180008cbb  xor     eax, eax
0x180008cbd  mov     [rcx+4], eax
0x180008cc0  mov     [rcx+8], rax
0x180008cc4  mov     [rcx+10h], rax
0x180008cc8  mov     rax, [rsi+rdi]
0x180008ccc  mov     [rcx+8], rax
0x180008cd0  lock cmpxchg [rsi+rdi], rcx
0x180008cd6  jnz     short loc_180008CC8
0x180008cd8  lea     rax, [rcx+10h]
0x180008cdc  add     rsp, 28h
0x180008ce0  pop     rdi
0x180008ce1  pop     rsi
0x180008ce2  pop     rbp
0x180008ce3  pop     rbx
0x180008ce4  retn
```
