# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18000430c`
- end: `0x180004362`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003e34`

## callees

- `0x18000430c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004319`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004319`

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
0x18000430c  push    rbx
0x18000430e  sub     rsp, 20h
0x180004312  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180004319  call    cs:__imp_GetCurrentThreadId
0x18000431f  mov     r8d, eax
0x180004322  mov     r9d, eax
0x180004325  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000432f  shr     r8, 2
0x180004333  mul     r8
0x180004336  shr     rdx, 3
0x18000433a  lea     rcx, [rdx+rdx*4]
0x18000433e  add     rcx, rcx
0x180004341  sub     r8, rcx
0x180004344  mov     rax, [rbx+r8*8]
0x180004348  test    rax, rax
0x18000434b  jz      short loc_18000435C
0x18000434d  cmp     [rax], r9d
0x180004350  jz      short loc_180004358
0x180004352  mov     rax, [rax+8]
0x180004356  jmp     short loc_180004348
0x180004358  add     rax, 10h
0x18000435c  add     rsp, 20h
0x180004360  pop     rbx
0x180004361  retn
```
