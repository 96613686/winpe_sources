# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180027450`
- end: `0x1800274a6`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180027014`

## callees

- `0x180027450`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002745d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002745d`

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
0x180027450  push    rbx
0x180027452  sub     rsp, 20h
0x180027456  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18002745d  call    cs:__imp_GetCurrentThreadId
0x180027463  mov     r8d, eax
0x180027466  mov     r9d, eax
0x180027469  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180027473  shr     r8, 2
0x180027477  mul     r8
0x18002747a  shr     rdx, 3
0x18002747e  lea     rcx, [rdx+rdx*4]
0x180027482  add     rcx, rcx
0x180027485  sub     r8, rcx
0x180027488  mov     rax, [rbx+r8*8]
0x18002748c  test    rax, rax
0x18002748f  jz      short loc_1800274A0
0x180027491  cmp     [rax], r9d
0x180027494  jz      short loc_18002749C
0x180027496  mov     rax, [rax+8]
0x18002749a  jmp     short loc_18002748C
0x18002749c  add     rax, 10h
0x1800274a0  add     rsp, 20h
0x1800274a4  pop     rbx
0x1800274a5  retn
```
