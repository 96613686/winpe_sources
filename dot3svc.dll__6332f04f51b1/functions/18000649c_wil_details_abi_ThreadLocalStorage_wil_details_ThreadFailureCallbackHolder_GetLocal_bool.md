# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18000649c`
- end: `0x1800064f2`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180005fc4`

## callees

- `0x18000649c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800064a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800064a9`

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
0x18000649c  push    rbx
0x18000649e  sub     rsp, 20h
0x1800064a2  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800064a9  call    cs:__imp_GetCurrentThreadId
0x1800064af  mov     r8d, eax
0x1800064b2  mov     r9d, eax
0x1800064b5  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800064bf  shr     r8, 2
0x1800064c3  mul     r8
0x1800064c6  shr     rdx, 3
0x1800064ca  lea     rcx, [rdx+rdx*4]
0x1800064ce  add     rcx, rcx
0x1800064d1  sub     r8, rcx
0x1800064d4  mov     rax, [rbx+r8*8]
0x1800064d8  test    rax, rax
0x1800064db  jz      short loc_1800064EC
0x1800064dd  cmp     [rax], r9d
0x1800064e0  jz      short loc_1800064E8
0x1800064e2  mov     rax, [rax+8]
0x1800064e6  jmp     short loc_1800064D8
0x1800064e8  add     rax, 10h
0x1800064ec  add     rsp, 20h
0x1800064f0  pop     rbx
0x1800064f1  retn
```
