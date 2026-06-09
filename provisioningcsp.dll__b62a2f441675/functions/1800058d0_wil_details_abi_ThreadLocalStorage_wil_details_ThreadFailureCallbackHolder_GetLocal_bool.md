# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x1800058d0`
- end: `0x180005973`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `163`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000c8f4`
- `0x18000ca5c`
- `0x18000cbc4`

## callees

- `0x1800058d0`
- `0x1800064c4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800058e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800058e3`

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
0x1800058d0  push    rbx
0x1800058d2  push    rbp
0x1800058d3  push    rsi
0x1800058d4  push    rdi
0x1800058d5  sub     rsp, 28h
0x1800058d9  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800058e0  mov     bpl, dl
0x1800058e3  call    cs:__imp_GetCurrentThreadId
0x1800058ea  nop     dword ptr [rax+rax+00h]
0x1800058ef  mov     ebx, eax
0x1800058f1  mov     esi, eax
0x1800058f3  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800058fd  shr     rbx, 2
0x180005901  mul     rbx
0x180005904  shr     rdx, 3
0x180005908  lea     rcx, [rdx+rdx*4]
0x18000590c  add     rcx, rcx
0x18000590f  sub     rbx, rcx
0x180005912  mov     rax, [rdi+rbx*8]
0x180005916  jmp     short loc_180005920
0x180005918  cmp     [rax], esi
0x18000591a  jz      short loc_180005961
0x18000591c  mov     rax, [rax+8]
0x180005920  test    rax, rax
0x180005923  jnz     short loc_180005918
0x180005925  test    bpl, bpl
0x180005928  jz      short loc_180005967
0x18000592a  lea     edx, [rax+18h]; dwBytes
0x18000592d  xor     ecx, ecx; dwFlags
0x18000592f  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180005934  mov     rcx, rax
0x180005937  test    rax, rax
0x18000593a  jz      short loc_180005967
0x18000593c  mov     [rax], esi
0x18000593e  xor     eax, eax
0x180005940  mov     [rcx+4], eax
0x180005943  mov     [rcx+8], rax
0x180005947  mov     [rcx+10h], rax
0x18000594b  mov     rax, [rdi+rbx*8]
0x18000594f  mov     [rcx+8], rax
0x180005953  lock cmpxchg [rdi+rbx*8], rcx
0x180005959  jnz     short loc_18000594B
0x18000595b  lea     rax, [rcx+10h]
0x18000595f  jmp     short loc_180005969
0x180005961  add     rax, 10h
0x180005965  jmp     short loc_180005969
0x180005967  xor     eax, eax
0x180005969  add     rsp, 28h
0x18000596d  pop     rdi
0x18000596e  pop     rsi
0x18000596f  pop     rbp
0x180005970  pop     rbx
0x180005971  retn
```
