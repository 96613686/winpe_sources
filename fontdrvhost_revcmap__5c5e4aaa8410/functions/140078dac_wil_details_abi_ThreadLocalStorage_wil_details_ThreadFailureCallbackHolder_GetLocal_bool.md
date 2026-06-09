# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x140078dac`
- end: `0x140078e02`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400788d4`

## callees

- `0x140078dac`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140078db9`
- `KERNEL32!GetCurrentThreadId` at `0x140078db9`

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
0x140078dac  push    rbx
0x140078dae  sub     rsp, 20h
0x140078db2  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140078db9  call    cs:__imp_GetCurrentThreadId
0x140078dbf  mov     r8d, eax
0x140078dc2  mov     r9d, eax
0x140078dc5  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140078dcf  shr     r8, 2
0x140078dd3  mul     r8
0x140078dd6  shr     rdx, 3
0x140078dda  lea     rcx, [rdx+rdx*4]
0x140078dde  add     rcx, rcx
0x140078de1  sub     r8, rcx
0x140078de4  mov     rax, [rbx+r8*8]
0x140078de8  test    rax, rax
0x140078deb  jz      short loc_140078DFC
0x140078ded  cmp     [rax], r9d
0x140078df0  jz      short loc_140078DF8
0x140078df2  mov     rax, [rax+8]
0x140078df6  jmp     short loc_140078DE8
0x140078df8  add     rax, 10h
0x140078dfc  add     rsp, 20h
0x140078e00  pop     rbx
0x140078e01  retn
```
