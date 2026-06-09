# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180004efc`
- end: `0x180004f9a`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `158`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180004a24`
- `0x180009150`

## callees

- `0x180004efc`
- `0x180005ba8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004f0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004f0f`

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
0x180004efc  push    rbx
0x180004efe  push    rbp
0x180004eff  push    rsi
0x180004f00  push    rdi
0x180004f01  sub     rsp, 28h
0x180004f05  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180004f0c  mov     bpl, dl
0x180004f0f  call    cs:__imp_GetCurrentThreadId
0x180004f15  mov     ebx, eax
0x180004f17  mov     esi, eax
0x180004f19  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004f23  shr     rbx, 2
0x180004f27  mul     rbx
0x180004f2a  shr     rdx, 3
0x180004f2e  lea     rcx, [rdx+rdx*4]
0x180004f32  add     rcx, rcx
0x180004f35  sub     rbx, rcx
0x180004f38  mov     rax, [rdi+rbx*8]
0x180004f3c  test    rax, rax
0x180004f3f  jz      short loc_180004F51
0x180004f41  cmp     [rax], esi
0x180004f43  jz      short loc_180004F4B
0x180004f45  mov     rax, [rax+8]
0x180004f49  jmp     short loc_180004F3C
0x180004f4b  add     rax, 10h
0x180004f4f  jmp     short loc_180004F91
0x180004f51  test    bpl, bpl
0x180004f54  jz      short loc_180004F8F
0x180004f56  mov     edx, 18h; dwBytes
0x180004f5b  xor     ecx, ecx; dwFlags
0x180004f5d  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004f62  mov     rcx, rax
0x180004f65  test    rax, rax
0x180004f68  jz      short loc_180004F8F
0x180004f6a  mov     [rax], esi
0x180004f6c  xor     eax, eax
0x180004f6e  mov     [rcx+4], eax
0x180004f71  mov     [rcx+8], rax
0x180004f75  mov     [rcx+10h], rax
0x180004f79  mov     rax, [rdi+rbx*8]
0x180004f7d  mov     [rcx+8], rax
0x180004f81  lock cmpxchg [rdi+rbx*8], rcx
0x180004f87  jnz     short loc_180004F79
0x180004f89  lea     rax, [rcx+10h]
0x180004f8d  jmp     short loc_180004F91
0x180004f8f  xor     eax, eax
0x180004f91  add     rsp, 28h
0x180004f95  pop     rdi
0x180004f96  pop     rsi
0x180004f97  pop     rbp
0x180004f98  pop     rbx
0x180004f99  retn
```
