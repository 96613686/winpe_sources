# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x1800069dc`
- end: `0x180006a32`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180006510`

## callees

- `0x1800069dc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800069e9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800069e9`

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
0x1800069dc  push    rbx
0x1800069de  sub     rsp, 20h
0x1800069e2  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800069e9  call    cs:__imp_GetCurrentThreadId
0x1800069ef  mov     r8d, eax
0x1800069f2  mov     r9d, eax
0x1800069f5  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800069ff  shr     r8, 2
0x180006a03  mul     r8
0x180006a06  shr     rdx, 3
0x180006a0a  lea     rcx, [rdx+rdx*4]
0x180006a0e  add     rcx, rcx
0x180006a11  sub     r8, rcx
0x180006a14  mov     rax, [rbx+r8*8]
0x180006a18  test    rax, rax
0x180006a1b  jz      short loc_180006A2C
0x180006a1d  cmp     [rax], r9d
0x180006a20  jz      short loc_180006A28
0x180006a22  mov     rax, [rax+8]
0x180006a26  jmp     short loc_180006A18
0x180006a28  add     rax, 10h
0x180006a2c  add     rsp, 20h
0x180006a30  pop     rbx
0x180006a31  retn
```
