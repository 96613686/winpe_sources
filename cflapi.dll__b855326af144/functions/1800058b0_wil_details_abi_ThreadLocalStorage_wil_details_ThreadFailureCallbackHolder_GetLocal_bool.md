# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x1800058b0`
- end: `0x18000594c`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `156`
- prototype: ``
- caller_count: `12`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000c85c`
- `0x18000c9bc`
- `0x18000cb1c`
- `0x18000cc7c`
- `0x18000cddc`
- `0x18000cf3c`
- `0x18000d09c`
- `0x18000d31c`
- `0x18000d47c`
- `0x18000d5dc`
- `0x180010700`
- `0x180011130`

## callees

- `0x1800058b0`
- `0x1800063d8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800058c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800058c3`

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
0x1800058b0  push    rbx
0x1800058b2  push    rbp
0x1800058b3  push    rsi
0x1800058b4  push    rdi
0x1800058b5  sub     rsp, 28h
0x1800058b9  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800058c0  mov     bpl, dl
0x1800058c3  call    cs:__imp_GetCurrentThreadId
0x1800058c9  mov     ebx, eax
0x1800058cb  mov     esi, eax
0x1800058cd  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800058d7  shr     rbx, 2
0x1800058db  mul     rbx
0x1800058de  shr     rdx, 3
0x1800058e2  lea     rcx, [rdx+rdx*4]
0x1800058e6  add     rcx, rcx
0x1800058e9  sub     rbx, rcx
0x1800058ec  mov     rax, [rdi+rbx*8]
0x1800058f0  jmp     short loc_1800058FA
0x1800058f2  cmp     [rax], esi
0x1800058f4  jz      short loc_18000593B
0x1800058f6  mov     rax, [rax+8]
0x1800058fa  test    rax, rax
0x1800058fd  jnz     short loc_1800058F2
0x1800058ff  test    bpl, bpl
0x180005902  jz      short loc_180005941
0x180005904  lea     edx, [rax+18h]; dwBytes
0x180005907  xor     ecx, ecx; dwFlags
0x180005909  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000590e  mov     rcx, rax
0x180005911  test    rax, rax
0x180005914  jz      short loc_180005941
0x180005916  mov     [rax], esi
0x180005918  xor     eax, eax
0x18000591a  mov     [rcx+4], eax
0x18000591d  mov     [rcx+8], rax
0x180005921  mov     [rcx+10h], rax
0x180005925  mov     rax, [rdi+rbx*8]
0x180005929  mov     [rcx+8], rax
0x18000592d  lock cmpxchg [rdi+rbx*8], rcx
0x180005933  jnz     short loc_180005925
0x180005935  lea     rax, [rcx+10h]
0x180005939  jmp     short loc_180005943
0x18000593b  add     rax, 10h
0x18000593f  jmp     short loc_180005943
0x180005941  xor     eax, eax
0x180005943  add     rsp, 28h
0x180005947  pop     rdi
0x180005948  pop     rsi
0x180005949  pop     rbp
0x18000594a  pop     rbx
0x18000594b  retn
```
