# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x1800173e0`
- end: `0x180017436`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180016fa8`

## callees

- `0x1800173e0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800173ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800173ed`

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
0x1800173e0  push    rbx
0x1800173e2  sub     rsp, 20h
0x1800173e6  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800173ed  call    cs:__imp_GetCurrentThreadId
0x1800173f3  mov     r8d, eax
0x1800173f6  mov     r9d, eax
0x1800173f9  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180017403  shr     r8, 2
0x180017407  mul     r8
0x18001740a  shr     rdx, 3
0x18001740e  lea     rcx, [rdx+rdx*4]
0x180017412  add     rcx, rcx
0x180017415  sub     r8, rcx
0x180017418  mov     rax, [rbx+r8*8]
0x18001741c  test    rax, rax
0x18001741f  jz      short loc_180017430
0x180017421  cmp     [rax], r9d
0x180017424  jz      short loc_18001742C
0x180017426  mov     rax, [rax+8]
0x18001742a  jmp     short loc_18001741C
0x18001742c  add     rax, 10h
0x180017430  add     rsp, 20h
0x180017434  pop     rbx
0x180017435  retn
```
