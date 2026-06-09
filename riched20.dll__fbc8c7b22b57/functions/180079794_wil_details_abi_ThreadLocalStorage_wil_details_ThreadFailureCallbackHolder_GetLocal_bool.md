# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180079794`
- end: `0x1800797f3`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800791f8`

## callees

- `0x180079794`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800797a1`
- `KERNEL32!GetCurrentThreadId` at `0x1800797a1`

## pseudocode

```c
__int64 wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal()
{
  __int64 v0; // rbx
  DWORD CurrentThreadId; // r9d
  __int64 result; // rax

  v0 = wil::details::g_pThreadFailureCallbacks;
  CurrentThreadId = GetCurrentThreadId();
  for ( result = *(_QWORD *)(v0 + 8 * (((unsigned __int64)CurrentThreadId >> 2) % 0xA));
        result;
        result = *(_QWORD *)(result + 8) )
  {
    if ( *(_DWORD *)result == CurrentThreadId )
    {
      result += 16;
      return result;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180079794  push    rbx
0x180079796  sub     rsp, 20h
0x18007979a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800797a1  call    cs:__imp_GetCurrentThreadId
0x1800797a8  nop     dword ptr [rax+rax+00h]
0x1800797ad  mov     r8d, eax
0x1800797b0  mov     r9d, eax
0x1800797b3  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800797bd  shr     r8, 2
0x1800797c1  mul     r8
0x1800797c4  shr     rdx, 3
0x1800797c8  lea     rcx, [rdx+rdx*4]
0x1800797cc  add     rcx, rcx
0x1800797cf  sub     r8, rcx
0x1800797d2  mov     rax, [rbx+r8*8]
0x1800797d6  jmp     short loc_1800797E1
0x1800797d8  cmp     [rax], r9d
0x1800797db  jz      short loc_1800797ED
0x1800797dd  mov     rax, [rax+8]
0x1800797e1  test    rax, rax
0x1800797e4  jnz     short loc_1800797D8
0x1800797e6  add     rsp, 20h
0x1800797ea  pop     rbx
0x1800797eb  retn
0x1800797ed  add     rax, 10h
0x1800797f1  jmp     short loc_1800797E6
```
