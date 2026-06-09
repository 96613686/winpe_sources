# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x140007760`
- end: `0x1400077fc`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `156`
- prototype: `signed __int64 __fastcall(__int64, char)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000b358`

## callees

- `0x140007760`
- `0x140009080`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140007773`
- `KERNEL32!GetCurrentThreadId` at `0x140007773`

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
0x140007760  push    rbx
0x140007762  push    rbp
0x140007763  push    rsi
0x140007764  push    rdi
0x140007765  sub     rsp, 28h
0x140007769  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140007770  mov     bpl, dl
0x140007773  call    cs:__imp_GetCurrentThreadId
0x140007779  mov     ebx, eax
0x14000777b  mov     esi, eax
0x14000777d  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140007787  shr     rbx, 2
0x14000778b  mul     rbx
0x14000778e  shr     rdx, 3
0x140007792  lea     rcx, [rdx+rdx*4]
0x140007796  add     rcx, rcx
0x140007799  sub     rbx, rcx
0x14000779c  mov     rax, [rdi+rbx*8]
0x1400077a0  jmp     short loc_1400077AA
0x1400077a2  cmp     [rax], esi
0x1400077a4  jz      short loc_1400077EB
0x1400077a6  mov     rax, [rax+8]
0x1400077aa  test    rax, rax
0x1400077ad  jnz     short loc_1400077A2
0x1400077af  test    bpl, bpl
0x1400077b2  jz      short loc_1400077F1
0x1400077b4  lea     edx, [rax+18h]; dwBytes
0x1400077b7  xor     ecx, ecx; dwFlags
0x1400077b9  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1400077be  mov     rcx, rax
0x1400077c1  test    rax, rax
0x1400077c4  jz      short loc_1400077F1
0x1400077c6  mov     [rax], esi
0x1400077c8  xor     eax, eax
0x1400077ca  mov     [rcx+4], eax
0x1400077cd  mov     [rcx+8], rax
0x1400077d1  mov     [rcx+10h], rax
0x1400077d5  mov     rax, [rdi+rbx*8]
0x1400077d9  mov     [rcx+8], rax
0x1400077dd  lock cmpxchg [rdi+rbx*8], rcx
0x1400077e3  jnz     short loc_1400077D5
0x1400077e5  lea     rax, [rcx+10h]
0x1400077e9  jmp     short loc_1400077F3
0x1400077eb  add     rax, 10h
0x1400077ef  jmp     short loc_1400077F3
0x1400077f1  xor     eax, eax
0x1400077f3  add     rsp, 28h
0x1400077f7  pop     rdi
0x1400077f8  pop     rsi
0x1400077f9  pop     rbp
0x1400077fa  pop     rbx
0x1400077fb  retn
```
