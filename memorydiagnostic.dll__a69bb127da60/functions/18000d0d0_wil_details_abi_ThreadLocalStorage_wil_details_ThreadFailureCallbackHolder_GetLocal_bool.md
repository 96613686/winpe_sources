# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18000d0d0`
- end: `0x18000d16c`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `156`
- prototype: `signed __int64 __fastcall(__int64, char)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180015010`

## callees

- `0x18000d0d0`
- `0x18000e6ac`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000d0e3`
- `KERNEL32!GetCurrentThreadId` at `0x18000d0e3`

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
0x18000d0d0  push    rbx
0x18000d0d2  push    rbp
0x18000d0d3  push    rsi
0x18000d0d4  push    rdi
0x18000d0d5  sub     rsp, 28h
0x18000d0d9  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000d0e0  mov     bpl, dl
0x18000d0e3  call    cs:__imp_GetCurrentThreadId
0x18000d0e9  mov     ebx, eax
0x18000d0eb  mov     esi, eax
0x18000d0ed  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000d0f7  shr     rbx, 2
0x18000d0fb  mul     rbx
0x18000d0fe  shr     rdx, 3
0x18000d102  lea     rcx, [rdx+rdx*4]
0x18000d106  add     rcx, rcx
0x18000d109  sub     rbx, rcx
0x18000d10c  mov     rax, [rdi+rbx*8]
0x18000d110  jmp     short loc_18000D11A
0x18000d112  cmp     [rax], esi
0x18000d114  jz      short loc_18000D15B
0x18000d116  mov     rax, [rax+8]
0x18000d11a  test    rax, rax
0x18000d11d  jnz     short loc_18000D112
0x18000d11f  test    bpl, bpl
0x18000d122  jz      short loc_18000D161
0x18000d124  lea     edx, [rax+18h]; dwBytes
0x18000d127  xor     ecx, ecx; dwFlags
0x18000d129  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000d12e  mov     rcx, rax
0x18000d131  test    rax, rax
0x18000d134  jz      short loc_18000D161
0x18000d136  mov     [rax], esi
0x18000d138  xor     eax, eax
0x18000d13a  mov     [rcx+4], eax
0x18000d13d  mov     [rcx+8], rax
0x18000d141  mov     [rcx+10h], rax
0x18000d145  mov     rax, [rdi+rbx*8]
0x18000d149  mov     [rcx+8], rax
0x18000d14d  lock cmpxchg [rdi+rbx*8], rcx
0x18000d153  jnz     short loc_18000D145
0x18000d155  lea     rax, [rcx+10h]
0x18000d159  jmp     short loc_18000D163
0x18000d15b  add     rax, 10h
0x18000d15f  jmp     short loc_18000D163
0x18000d161  xor     eax, eax
0x18000d163  add     rsp, 28h
0x18000d167  pop     rdi
0x18000d168  pop     rsi
0x18000d169  pop     rbp
0x18000d16a  pop     rbx
0x18000d16b  retn
```
