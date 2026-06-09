# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x1800045dc`
- end: `0x18000467a`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `158`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180004104`
- `0x1800060a8`

## callees

- `0x1800045dc`
- `0x1800054fc`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800045ef`
- `KERNEL32!GetCurrentThreadId` at `0x1800045ef`

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
0x1800045dc  push    rbx
0x1800045de  push    rbp
0x1800045df  push    rsi
0x1800045e0  push    rdi
0x1800045e1  sub     rsp, 28h
0x1800045e5  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800045ec  mov     bpl, dl
0x1800045ef  call    cs:__imp_GetCurrentThreadId
0x1800045f5  mov     ebx, eax
0x1800045f7  mov     esi, eax
0x1800045f9  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004603  shr     rbx, 2
0x180004607  mul     rbx
0x18000460a  shr     rdx, 3
0x18000460e  lea     rcx, [rdx+rdx*4]
0x180004612  add     rcx, rcx
0x180004615  sub     rbx, rcx
0x180004618  mov     rax, [rdi+rbx*8]
0x18000461c  test    rax, rax
0x18000461f  jz      short loc_180004631
0x180004621  cmp     [rax], esi
0x180004623  jz      short loc_18000462B
0x180004625  mov     rax, [rax+8]
0x180004629  jmp     short loc_18000461C
0x18000462b  add     rax, 10h
0x18000462f  jmp     short loc_180004671
0x180004631  test    bpl, bpl
0x180004634  jz      short loc_18000466F
0x180004636  mov     edx, 18h; dwBytes
0x18000463b  xor     ecx, ecx; dwFlags
0x18000463d  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004642  mov     rcx, rax
0x180004645  test    rax, rax
0x180004648  jz      short loc_18000466F
0x18000464a  mov     [rax], esi
0x18000464c  xor     eax, eax
0x18000464e  mov     [rcx+4], eax
0x180004651  mov     [rcx+8], rax
0x180004655  mov     [rcx+10h], rax
0x180004659  mov     rax, [rdi+rbx*8]
0x18000465d  mov     [rcx+8], rax
0x180004661  lock cmpxchg [rdi+rbx*8], rcx
0x180004667  jnz     short loc_180004659
0x180004669  lea     rax, [rcx+10h]
0x18000466d  jmp     short loc_180004671
0x18000466f  xor     eax, eax
0x180004671  add     rsp, 28h
0x180004675  pop     rdi
0x180004676  pop     rsi
0x180004677  pop     rbp
0x180004678  pop     rbx
0x180004679  retn
```
