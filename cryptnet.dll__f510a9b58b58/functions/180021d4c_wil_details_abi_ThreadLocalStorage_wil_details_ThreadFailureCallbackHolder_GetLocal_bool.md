# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180021d4c`
- end: `0x180021da2`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180021874`

## callees

- `0x180021d4c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021d59`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021d59`

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
0x180021d4c  push    rbx
0x180021d4e  sub     rsp, 20h
0x180021d52  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180021d59  call    cs:__imp_GetCurrentThreadId
0x180021d5f  mov     r8d, eax
0x180021d62  mov     r9d, eax
0x180021d65  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180021d6f  shr     r8, 2
0x180021d73  mul     r8
0x180021d76  shr     rdx, 3
0x180021d7a  lea     rcx, [rdx+rdx*4]
0x180021d7e  add     rcx, rcx
0x180021d81  sub     r8, rcx
0x180021d84  mov     rax, [rbx+r8*8]
0x180021d88  test    rax, rax
0x180021d8b  jz      short loc_180021D9C
0x180021d8d  cmp     [rax], r9d
0x180021d90  jz      short loc_180021D98
0x180021d92  mov     rax, [rax+8]
0x180021d96  jmp     short loc_180021D88
0x180021d98  add     rax, 10h
0x180021d9c  add     rsp, 20h
0x180021da0  pop     rbx
0x180021da1  retn
```
