# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x140004ed0`
- end: `0x140004f73`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `163`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140007798`
- `0x1400078e4`
- `0x140007a84`
- `0x140007bd0`

## callees

- `0x140004ed0`
- `0x1400067d4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004ee3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004ee3`

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
0x140004ed0  push    rbx
0x140004ed2  push    rbp
0x140004ed3  push    rsi
0x140004ed4  push    rdi
0x140004ed5  sub     rsp, 28h
0x140004ed9  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140004ee0  mov     bpl, dl
0x140004ee3  call    cs:__imp_GetCurrentThreadId
0x140004eea  nop     dword ptr [rax+rax+00h]
0x140004eef  mov     ebx, eax
0x140004ef1  mov     esi, eax
0x140004ef3  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140004efd  shr     rbx, 2
0x140004f01  mul     rbx
0x140004f04  shr     rdx, 3
0x140004f08  lea     rcx, [rdx+rdx*4]
0x140004f0c  add     rcx, rcx
0x140004f0f  sub     rbx, rcx
0x140004f12  mov     rax, [rdi+rbx*8]
0x140004f16  jmp     short loc_140004F20
0x140004f18  cmp     [rax], esi
0x140004f1a  jz      short loc_140004F61
0x140004f1c  mov     rax, [rax+8]
0x140004f20  test    rax, rax
0x140004f23  jnz     short loc_140004F18
0x140004f25  test    bpl, bpl
0x140004f28  jz      short loc_140004F67
0x140004f2a  lea     edx, [rax+18h]; dwBytes
0x140004f2d  xor     ecx, ecx; dwFlags
0x140004f2f  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140004f34  mov     rcx, rax
0x140004f37  test    rax, rax
0x140004f3a  jz      short loc_140004F67
0x140004f3c  mov     [rax], esi
0x140004f3e  xor     eax, eax
0x140004f40  mov     [rcx+4], eax
0x140004f43  mov     [rcx+8], rax
0x140004f47  mov     [rcx+10h], rax
0x140004f4b  mov     rax, [rdi+rbx*8]
0x140004f4f  mov     [rcx+8], rax
0x140004f53  lock cmpxchg [rdi+rbx*8], rcx
0x140004f59  jnz     short loc_140004F4B
0x140004f5b  lea     rax, [rcx+10h]
0x140004f5f  jmp     short loc_140004F69
0x140004f61  add     rax, 10h
0x140004f65  jmp     short loc_140004F69
0x140004f67  xor     eax, eax
0x140004f69  add     rsp, 28h
0x140004f6d  pop     rdi
0x140004f6e  pop     rsi
0x140004f6f  pop     rbp
0x140004f70  pop     rbx
0x140004f71  retn
```
