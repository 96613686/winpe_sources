# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180006970`
- end: `0x180006a0c`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008cf0`

## callees

- `0x180006970`
- `0x180007b60`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180006983`
- `KERNEL32!GetCurrentThreadId` at `0x180006983`

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
0x180006970  push    rbx
0x180006972  push    rbp
0x180006973  push    rsi
0x180006974  push    rdi
0x180006975  sub     rsp, 28h
0x180006979  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180006980  mov     bpl, dl
0x180006983  call    cs:__imp_GetCurrentThreadId
0x180006989  mov     ebx, eax
0x18000698b  mov     esi, eax
0x18000698d  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180006997  shr     rbx, 2
0x18000699b  mul     rbx
0x18000699e  shr     rdx, 3
0x1800069a2  lea     rcx, [rdx+rdx*4]
0x1800069a6  add     rcx, rcx
0x1800069a9  sub     rbx, rcx
0x1800069ac  mov     rax, [rdi+rbx*8]
0x1800069b0  jmp     short loc_1800069BA
0x1800069b2  cmp     [rax], esi
0x1800069b4  jz      short loc_1800069FB
0x1800069b6  mov     rax, [rax+8]
0x1800069ba  test    rax, rax
0x1800069bd  jnz     short loc_1800069B2
0x1800069bf  test    bpl, bpl
0x1800069c2  jz      short loc_180006A01
0x1800069c4  lea     edx, [rax+18h]; dwBytes
0x1800069c7  xor     ecx, ecx; dwFlags
0x1800069c9  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800069ce  mov     rcx, rax
0x1800069d1  test    rax, rax
0x1800069d4  jz      short loc_180006A01
0x1800069d6  mov     [rax], esi
0x1800069d8  xor     eax, eax
0x1800069da  mov     [rcx+4], eax
0x1800069dd  mov     [rcx+8], rax
0x1800069e1  mov     [rcx+10h], rax
0x1800069e5  mov     rax, [rdi+rbx*8]
0x1800069e9  mov     [rcx+8], rax
0x1800069ed  lock cmpxchg [rdi+rbx*8], rcx
0x1800069f3  jnz     short loc_1800069E5
0x1800069f5  lea     rax, [rcx+10h]
0x1800069f9  jmp     short loc_180006A03
0x1800069fb  add     rax, 10h
0x1800069ff  jmp     short loc_180006A03
0x180006a01  xor     eax, eax
0x180006a03  add     rsp, 28h
0x180006a07  pop     rdi
0x180006a08  pop     rsi
0x180006a09  pop     rbp
0x180006a0a  pop     rbx
0x180006a0b  retn
```
