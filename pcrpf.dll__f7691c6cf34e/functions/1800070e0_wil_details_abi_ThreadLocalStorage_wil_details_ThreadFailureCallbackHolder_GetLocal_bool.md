# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x1800070e0`
- end: `0x180007183`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `163`
- prototype: `signed __int64 __fastcall(__int64, char)`
- caller_count: `10`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000e008`
- `0x180018224`
- `0x18001838c`
- `0x1800184f4`
- `0x18001865c`
- `0x1800187c4`
- `0x18001892c`
- `0x180050c3c`
- `0x180050da4`
- `0x180053970`

## callees

- `0x1800070e0`
- `0x1800080d8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800070f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800070f3`

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
0x1800070e0  push    rbx
0x1800070e2  push    rbp
0x1800070e3  push    rsi
0x1800070e4  push    rdi
0x1800070e5  sub     rsp, 28h
0x1800070e9  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800070f0  mov     bpl, dl
0x1800070f3  call    cs:__imp_GetCurrentThreadId
0x1800070fa  nop     dword ptr [rax+rax+00h]
0x1800070ff  mov     ebx, eax
0x180007101  mov     esi, eax
0x180007103  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000710d  shr     rbx, 2
0x180007111  mul     rbx
0x180007114  shr     rdx, 3
0x180007118  lea     rcx, [rdx+rdx*4]
0x18000711c  add     rcx, rcx
0x18000711f  sub     rbx, rcx
0x180007122  mov     rax, [rdi+rbx*8]
0x180007126  jmp     short loc_180007130
0x180007128  cmp     [rax], esi
0x18000712a  jz      short loc_180007171
0x18000712c  mov     rax, [rax+8]
0x180007130  test    rax, rax
0x180007133  jnz     short loc_180007128
0x180007135  test    bpl, bpl
0x180007138  jz      short loc_180007177
0x18000713a  lea     edx, [rax+18h]; dwBytes
0x18000713d  xor     ecx, ecx; dwFlags
0x18000713f  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180007144  mov     rcx, rax
0x180007147  test    rax, rax
0x18000714a  jz      short loc_180007177
0x18000714c  mov     [rax], esi
0x18000714e  xor     eax, eax
0x180007150  mov     [rcx+4], eax
0x180007153  mov     [rcx+8], rax
0x180007157  mov     [rcx+10h], rax
0x18000715b  mov     rax, [rdi+rbx*8]
0x18000715f  mov     [rcx+8], rax
0x180007163  lock cmpxchg [rdi+rbx*8], rcx
0x180007169  jnz     short loc_18000715B
0x18000716b  lea     rax, [rcx+10h]
0x18000716f  jmp     short loc_180007179
0x180007171  add     rax, 10h
0x180007175  jmp     short loc_180007179
0x180007177  xor     eax, eax
0x180007179  add     rsp, 28h
0x18000717d  pop     rdi
0x18000717e  pop     rsi
0x18000717f  pop     rbp
0x180007180  pop     rbx
0x180007181  retn
```
