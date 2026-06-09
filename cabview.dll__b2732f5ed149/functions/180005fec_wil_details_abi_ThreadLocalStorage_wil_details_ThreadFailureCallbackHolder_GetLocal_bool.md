# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180005fec`
- end: `0x18000608a`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `158`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005b14`
- `0x180011488`

## callees

- `0x180005fec`
- `0x180007460`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005fff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005fff`

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
0x180005fec  push    rbx
0x180005fee  push    rbp
0x180005fef  push    rsi
0x180005ff0  push    rdi
0x180005ff1  sub     rsp, 28h
0x180005ff5  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180005ffc  mov     bpl, dl
0x180005fff  call    cs:__imp_GetCurrentThreadId
0x180006005  mov     ebx, eax
0x180006007  mov     esi, eax
0x180006009  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180006013  shr     rbx, 2
0x180006017  mul     rbx
0x18000601a  shr     rdx, 3
0x18000601e  lea     rcx, [rdx+rdx*4]
0x180006022  add     rcx, rcx
0x180006025  sub     rbx, rcx
0x180006028  mov     rax, [rdi+rbx*8]
0x18000602c  test    rax, rax
0x18000602f  jz      short loc_180006041
0x180006031  cmp     [rax], esi
0x180006033  jz      short loc_18000603B
0x180006035  mov     rax, [rax+8]
0x180006039  jmp     short loc_18000602C
0x18000603b  add     rax, 10h
0x18000603f  jmp     short loc_180006081
0x180006041  test    bpl, bpl
0x180006044  jz      short loc_18000607F
0x180006046  mov     edx, 18h; dwBytes
0x18000604b  xor     ecx, ecx; dwFlags
0x18000604d  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180006052  mov     rcx, rax
0x180006055  test    rax, rax
0x180006058  jz      short loc_18000607F
0x18000605a  mov     [rax], esi
0x18000605c  xor     eax, eax
0x18000605e  mov     [rcx+4], eax
0x180006061  mov     [rcx+8], rax
0x180006065  mov     [rcx+10h], rax
0x180006069  mov     rax, [rdi+rbx*8]
0x18000606d  mov     [rcx+8], rax
0x180006071  lock cmpxchg [rdi+rbx*8], rcx
0x180006077  jnz     short loc_180006069
0x180006079  lea     rax, [rcx+10h]
0x18000607d  jmp     short loc_180006081
0x18000607f  xor     eax, eax
0x180006081  add     rsp, 28h
0x180006085  pop     rdi
0x180006086  pop     rsi
0x180006087  pop     rbp
0x180006088  pop     rbx
0x180006089  retn
```
