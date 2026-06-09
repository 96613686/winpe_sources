# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180007490`
- end: `0x180007533`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `163`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000abe4`

## callees

- `0x180007490`
- `0x18000889c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800074a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800074a3`

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
0x180007490  push    rbx
0x180007492  push    rbp
0x180007493  push    rsi
0x180007494  push    rdi
0x180007495  sub     rsp, 28h
0x180007499  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800074a0  mov     bpl, dl
0x1800074a3  call    cs:__imp_GetCurrentThreadId
0x1800074aa  nop     dword ptr [rax+rax+00h]
0x1800074af  mov     ebx, eax
0x1800074b1  mov     esi, eax
0x1800074b3  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800074bd  shr     rbx, 2
0x1800074c1  mul     rbx
0x1800074c4  shr     rdx, 3
0x1800074c8  lea     rcx, [rdx+rdx*4]
0x1800074cc  add     rcx, rcx
0x1800074cf  sub     rbx, rcx
0x1800074d2  mov     rax, [rdi+rbx*8]
0x1800074d6  jmp     short loc_1800074E0
0x1800074d8  cmp     [rax], esi
0x1800074da  jz      short loc_180007521
0x1800074dc  mov     rax, [rax+8]
0x1800074e0  test    rax, rax
0x1800074e3  jnz     short loc_1800074D8
0x1800074e5  test    bpl, bpl
0x1800074e8  jz      short loc_180007527
0x1800074ea  lea     edx, [rax+18h]; dwBytes
0x1800074ed  xor     ecx, ecx; dwFlags
0x1800074ef  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800074f4  mov     rcx, rax
0x1800074f7  test    rax, rax
0x1800074fa  jz      short loc_180007527
0x1800074fc  mov     [rax], esi
0x1800074fe  xor     eax, eax
0x180007500  mov     [rcx+4], eax
0x180007503  mov     [rcx+8], rax
0x180007507  mov     [rcx+10h], rax
0x18000750b  mov     rax, [rdi+rbx*8]
0x18000750f  mov     [rcx+8], rax
0x180007513  lock cmpxchg [rdi+rbx*8], rcx
0x180007519  jnz     short loc_18000750B
0x18000751b  lea     rax, [rcx+10h]
0x18000751f  jmp     short loc_180007529
0x180007521  add     rax, 10h
0x180007525  jmp     short loc_180007529
0x180007527  xor     eax, eax
0x180007529  add     rsp, 28h
0x18000752d  pop     rdi
0x18000752e  pop     rsi
0x18000752f  pop     rbp
0x180007530  pop     rbx
0x180007531  retn
```
