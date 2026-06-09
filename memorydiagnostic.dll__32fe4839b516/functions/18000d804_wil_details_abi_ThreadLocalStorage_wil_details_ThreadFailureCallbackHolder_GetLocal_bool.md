# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18000d804`
- end: `0x18000d8ba`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `182`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180015cd0`

## callees

- `0x18000d804`
- `0x18000efd0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000d822`
- `KERNEL32!GetCurrentThreadId` at `0x18000d822`

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
  v6 = CurrentThreadId % 0xAuLL;
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
0x18000d804  mov     [rsp+arg_0], rbx
0x18000d809  mov     [rsp+arg_8], rbp
0x18000d80e  mov     [rsp+arg_10], rsi
0x18000d813  push    rdi
0x18000d814  sub     rsp, 20h
0x18000d818  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000d81f  mov     bpl, dl
0x18000d822  call    cs:__imp_GetCurrentThreadId
0x18000d829  nop     dword ptr [rax+rax+00h]
0x18000d82e  mov     ebx, eax
0x18000d830  mov     esi, eax
0x18000d832  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000d83c  mul     rsi
0x18000d83f  shr     rdx, 3
0x18000d843  lea     rcx, [rdx+rdx*4]
0x18000d847  add     rcx, rcx
0x18000d84a  sub     rbx, rcx
0x18000d84d  mov     rax, [rdi+rbx*8]
0x18000d851  jmp     short loc_18000D85B
0x18000d853  cmp     [rax], esi
0x18000d855  jz      short loc_18000D89C
0x18000d857  mov     rax, [rax+8]
0x18000d85b  test    rax, rax
0x18000d85e  jnz     short loc_18000D853
0x18000d860  test    bpl, bpl
0x18000d863  jz      short loc_18000D8A2
0x18000d865  lea     edx, [rax+18h]; dwBytes
0x18000d868  xor     ecx, ecx; dwFlags
0x18000d86a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000d86f  mov     rcx, rax
0x18000d872  test    rax, rax
0x18000d875  jz      short loc_18000D8A2
0x18000d877  mov     [rax], esi
0x18000d879  xor     eax, eax
0x18000d87b  mov     [rcx+4], eax
0x18000d87e  and     [rcx+8], rax
0x18000d882  and     [rcx+10h], rax
0x18000d886  mov     rax, [rdi+rbx*8]
0x18000d88a  mov     [rcx+8], rax
0x18000d88e  lock cmpxchg [rdi+rbx*8], rcx
0x18000d894  jnz     short loc_18000D886
0x18000d896  lea     rax, [rcx+10h]
0x18000d89a  jmp     short loc_18000D8A4
0x18000d89c  add     rax, 10h
0x18000d8a0  jmp     short loc_18000D8A4
0x18000d8a2  xor     eax, eax
0x18000d8a4  mov     rbx, [rsp+28h+arg_0]
0x18000d8a9  mov     rbp, [rsp+28h+arg_8]
0x18000d8ae  mov     rsi, [rsp+28h+arg_10]
0x18000d8b3  add     rsp, 20h
0x18000d8b7  pop     rdi
0x18000d8b8  retn
```
