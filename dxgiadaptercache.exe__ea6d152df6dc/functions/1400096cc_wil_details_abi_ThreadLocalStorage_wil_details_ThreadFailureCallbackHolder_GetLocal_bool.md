# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x1400096cc`
- end: `0x140009768`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `156`
- prototype: `signed __int64 __fastcall(__int64, char)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000d358`

## callees

- `0x1400096cc`
- `0x14000a910`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400096df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400096df`

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
0x1400096cc  push    rbx
0x1400096ce  push    rbp
0x1400096cf  push    rsi
0x1400096d0  push    rdi
0x1400096d1  sub     rsp, 28h
0x1400096d5  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1400096dc  mov     bpl, dl
0x1400096df  call    cs:__imp_GetCurrentThreadId
0x1400096e5  mov     ebx, eax
0x1400096e7  mov     esi, eax
0x1400096e9  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1400096f3  shr     rbx, 2
0x1400096f7  mul     rbx
0x1400096fa  shr     rdx, 3
0x1400096fe  lea     rcx, [rdx+rdx*4]
0x140009702  add     rcx, rcx
0x140009705  sub     rbx, rcx
0x140009708  mov     rax, [rdi+rbx*8]
0x14000970c  jmp     short loc_140009716
0x14000970e  cmp     [rax], esi
0x140009710  jz      short loc_140009757
0x140009712  mov     rax, [rax+8]
0x140009716  test    rax, rax
0x140009719  jnz     short loc_14000970E
0x14000971b  test    bpl, bpl
0x14000971e  jz      short loc_14000975D
0x140009720  lea     edx, [rax+18h]; dwBytes
0x140009723  xor     ecx, ecx; dwFlags
0x140009725  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000972a  mov     rcx, rax
0x14000972d  test    rax, rax
0x140009730  jz      short loc_14000975D
0x140009732  mov     [rax], esi
0x140009734  xor     eax, eax
0x140009736  mov     [rcx+4], eax
0x140009739  mov     [rcx+8], rax
0x14000973d  mov     [rcx+10h], rax
0x140009741  mov     rax, [rdi+rbx*8]
0x140009745  mov     [rcx+8], rax
0x140009749  lock cmpxchg [rdi+rbx*8], rcx
0x14000974f  jnz     short loc_140009741
0x140009751  lea     rax, [rcx+10h]
0x140009755  jmp     short loc_14000975F
0x140009757  add     rax, 10h
0x14000975b  jmp     short loc_14000975F
0x14000975d  xor     eax, eax
0x14000975f  add     rsp, 28h
0x140009763  pop     rdi
0x140009764  pop     rsi
0x140009765  pop     rbp
0x140009766  pop     rbx
0x140009767  retn
```
