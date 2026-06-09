# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18000550c`
- end: `0x1800055aa`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `158`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005034`
- `0x18000adac`

## callees

- `0x18000550c`
- `0x1800060f8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000551f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000551f`

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
0x18000550c  push    rbx
0x18000550e  push    rbp
0x18000550f  push    rsi
0x180005510  push    rdi
0x180005511  sub     rsp, 28h
0x180005515  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000551c  mov     bpl, dl
0x18000551f  call    cs:__imp_GetCurrentThreadId
0x180005525  mov     ebx, eax
0x180005527  mov     esi, eax
0x180005529  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180005533  shr     rbx, 2
0x180005537  mul     rbx
0x18000553a  shr     rdx, 3
0x18000553e  lea     rcx, [rdx+rdx*4]
0x180005542  add     rcx, rcx
0x180005545  sub     rbx, rcx
0x180005548  mov     rax, [rdi+rbx*8]
0x18000554c  test    rax, rax
0x18000554f  jz      short loc_180005561
0x180005551  cmp     [rax], esi
0x180005553  jz      short loc_18000555B
0x180005555  mov     rax, [rax+8]
0x180005559  jmp     short loc_18000554C
0x18000555b  add     rax, 10h
0x18000555f  jmp     short loc_1800055A1
0x180005561  test    bpl, bpl
0x180005564  jz      short loc_18000559F
0x180005566  mov     edx, 18h; dwBytes
0x18000556b  xor     ecx, ecx; dwFlags
0x18000556d  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180005572  mov     rcx, rax
0x180005575  test    rax, rax
0x180005578  jz      short loc_18000559F
0x18000557a  mov     [rax], esi
0x18000557c  xor     eax, eax
0x18000557e  mov     [rcx+4], eax
0x180005581  mov     [rcx+8], rax
0x180005585  mov     [rcx+10h], rax
0x180005589  mov     rax, [rdi+rbx*8]
0x18000558d  mov     [rcx+8], rax
0x180005591  lock cmpxchg [rdi+rbx*8], rcx
0x180005597  jnz     short loc_180005589
0x180005599  lea     rax, [rcx+10h]
0x18000559d  jmp     short loc_1800055A1
0x18000559f  xor     eax, eax
0x1800055a1  add     rsp, 28h
0x1800055a5  pop     rdi
0x1800055a6  pop     rsi
0x1800055a7  pop     rbp
0x1800055a8  pop     rbx
0x1800055a9  retn
```
