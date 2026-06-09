# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x14000690c`
- end: `0x1400069aa`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `158`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140006434`

## callees

- `0x14000690c`
- `0x140008894`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14000691f`
- `KERNEL32!GetCurrentThreadId` at `0x14000691f`

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
0x14000690c  push    rbx
0x14000690e  push    rbp
0x14000690f  push    rsi
0x140006910  push    rdi
0x140006911  sub     rsp, 28h
0x140006915  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x14000691c  mov     bpl, dl
0x14000691f  call    cs:__imp_GetCurrentThreadId
0x140006925  mov     ebx, eax
0x140006927  mov     esi, eax
0x140006929  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140006933  shr     rbx, 2
0x140006937  mul     rbx
0x14000693a  shr     rdx, 3
0x14000693e  lea     rcx, [rdx+rdx*4]
0x140006942  add     rcx, rcx
0x140006945  sub     rbx, rcx
0x140006948  mov     rax, [rdi+rbx*8]
0x14000694c  test    rax, rax
0x14000694f  jz      short loc_140006961
0x140006951  cmp     [rax], esi
0x140006953  jz      short loc_14000695B
0x140006955  mov     rax, [rax+8]
0x140006959  jmp     short loc_14000694C
0x14000695b  add     rax, 10h
0x14000695f  jmp     short loc_1400069A1
0x140006961  test    bpl, bpl
0x140006964  jz      short loc_14000699F
0x140006966  mov     edx, 18h; dwBytes
0x14000696b  xor     ecx, ecx; dwFlags
0x14000696d  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140006972  mov     rcx, rax
0x140006975  test    rax, rax
0x140006978  jz      short loc_14000699F
0x14000697a  mov     [rax], esi
0x14000697c  xor     eax, eax
0x14000697e  mov     [rcx+4], eax
0x140006981  mov     [rcx+8], rax
0x140006985  mov     [rcx+10h], rax
0x140006989  mov     rax, [rdi+rbx*8]
0x14000698d  mov     [rcx+8], rax
0x140006991  lock cmpxchg [rdi+rbx*8], rcx
0x140006997  jnz     short loc_140006989
0x140006999  lea     rax, [rcx+10h]
0x14000699d  jmp     short loc_1400069A1
0x14000699f  xor     eax, eax
0x1400069a1  add     rsp, 28h
0x1400069a5  pop     rdi
0x1400069a6  pop     rsi
0x1400069a7  pop     rbp
0x1400069a8  pop     rbx
0x1400069a9  retn
```
