# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18000cff0`
- end: `0x18000d046`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000cbbc`

## callees

- `0x18000cff0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cffd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cffd`

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
0x18000cff0  push    rbx
0x18000cff2  sub     rsp, 20h
0x18000cff6  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000cffd  call    cs:__imp_GetCurrentThreadId
0x18000d003  mov     r8d, eax
0x18000d006  mov     r9d, eax
0x18000d009  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000d013  shr     r8, 2
0x18000d017  mul     r8
0x18000d01a  shr     rdx, 3
0x18000d01e  lea     rcx, [rdx+rdx*4]
0x18000d022  add     rcx, rcx
0x18000d025  sub     r8, rcx
0x18000d028  mov     rax, [rbx+r8*8]
0x18000d02c  test    rax, rax
0x18000d02f  jz      short loc_18000D040
0x18000d031  cmp     [rax], r9d
0x18000d034  jz      short loc_18000D03C
0x18000d036  mov     rax, [rax+8]
0x18000d03a  jmp     short loc_18000D02C
0x18000d03c  add     rax, 10h
0x18000d040  add     rsp, 20h
0x18000d044  pop     rbx
0x18000d045  retn
```
