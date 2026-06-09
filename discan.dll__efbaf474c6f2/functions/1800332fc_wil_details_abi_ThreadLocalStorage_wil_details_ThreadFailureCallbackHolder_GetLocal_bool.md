# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x1800332fc`
- end: `0x180033352`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180032e24`

## callees

- `0x1800332fc`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180033309`
- `KERNEL32!GetCurrentThreadId` at `0x180033309`

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
0x1800332fc  push    rbx
0x1800332fe  sub     rsp, 20h
0x180033302  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180033309  call    cs:__imp_GetCurrentThreadId
0x18003330f  mov     r8d, eax
0x180033312  mov     r9d, eax
0x180033315  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18003331f  shr     r8, 2
0x180033323  mul     r8
0x180033326  shr     rdx, 3
0x18003332a  lea     rcx, [rdx+rdx*4]
0x18003332e  add     rcx, rcx
0x180033331  sub     r8, rcx
0x180033334  mov     rax, [rbx+r8*8]
0x180033338  test    rax, rax
0x18003333b  jz      short loc_18003334C
0x18003333d  cmp     [rax], r9d
0x180033340  jz      short loc_180033348
0x180033342  mov     rax, [rax+8]
0x180033346  jmp     short loc_180033338
0x180033348  add     rax, 10h
0x18003334c  add     rsp, 20h
0x180033350  pop     rbx
0x180033351  retn
```
