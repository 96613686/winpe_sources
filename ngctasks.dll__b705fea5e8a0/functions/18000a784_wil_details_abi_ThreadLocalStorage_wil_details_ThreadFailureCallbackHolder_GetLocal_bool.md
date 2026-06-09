# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18000a784`
- end: `0x18000a822`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `158`
- prototype: `signed __int64 __fastcall(__int64, char)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a020`
- `0x18000d444`

## callees

- `0x18000a784`
- `0x18000c2d8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a797`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a797`

## pseudocode

```c
signed __int64 __fastcall wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
        __int64 a1,
        char a2)
{
  __int64 v3; // rdi
  DWORD CurrentThreadId; // esi
  unsigned __int64 v5; // r8
  unsigned __int64 v6; // rbx
  __int64 i; // rax
  DWORD *v9; // rax
  signed __int64 v10; // rcx
  signed __int64 v11; // rax

  v3 = wil::details::g_pThreadFailureCallbacks;
  CurrentThreadId = GetCurrentThreadId();
  v6 = ((unsigned __int64)CurrentThreadId >> 2) % 0xA;
  for ( i = *(_QWORD *)(v3 + 8 * v6); i; i = *(_QWORD *)(i + 8) )
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
    v11 = *(_QWORD *)(v3 + 8 * v6);
    *(_QWORD *)(v10 + 8) = v11;
  }
  while ( v11 != _InterlockedCompareExchange64((volatile signed __int64 *)(v3 + 8 * v6), v10, v11) );
  return v10 + 16;
}

```

## disassembly

```asm
0x18000a784  push    rbx
0x18000a786  push    rbp
0x18000a787  push    rsi
0x18000a788  push    rdi
0x18000a789  sub     rsp, 28h
0x18000a78d  mov     bpl, dl
0x18000a790  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000a797  call    cs:__imp_GetCurrentThreadId
0x18000a79d  mov     esi, eax
0x18000a79f  mov     ebx, eax
0x18000a7a1  shr     rbx, 2
0x18000a7a5  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000a7af  mul     rbx
0x18000a7b2  shr     rdx, 3
0x18000a7b6  lea     rcx, [rdx+rdx*4]
0x18000a7ba  add     rcx, rcx
0x18000a7bd  sub     rbx, rcx
0x18000a7c0  mov     rax, [rdi+rbx*8]
0x18000a7c4  test    rax, rax
0x18000a7c7  jz      short loc_18000A7D9
0x18000a7c9  cmp     [rax], esi
0x18000a7cb  jz      short loc_18000A7D3
0x18000a7cd  mov     rax, [rax+8]
0x18000a7d1  jmp     short loc_18000A7C4
0x18000a7d3  add     rax, 10h
0x18000a7d7  jmp     short loc_18000A819
0x18000a7d9  test    bpl, bpl
0x18000a7dc  jz      short loc_18000A817
0x18000a7de  mov     edx, 18h; dwBytes
0x18000a7e3  xor     ecx, ecx; dwFlags
0x18000a7e5  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000a7ea  mov     rcx, rax
0x18000a7ed  test    rax, rax
0x18000a7f0  jz      short loc_18000A817
0x18000a7f2  mov     [rax], esi
0x18000a7f4  xor     eax, eax
0x18000a7f6  mov     [rcx+4], eax
0x18000a7f9  mov     [rcx+8], rax
0x18000a7fd  mov     [rcx+10h], rax
0x18000a801  mov     rax, [rdi+rbx*8]
0x18000a805  mov     [rcx+8], rax
0x18000a809  lock cmpxchg [rdi+rbx*8], rcx
0x18000a80f  jnz     short loc_18000A801
0x18000a811  lea     rax, [rcx+10h]
0x18000a815  jmp     short loc_18000A819
0x18000a817  xor     eax, eax
0x18000a819  add     rsp, 28h
0x18000a81d  pop     rdi
0x18000a81e  pop     rsi
0x18000a81f  pop     rbp
0x18000a820  pop     rbx
0x18000a821  retn
```
