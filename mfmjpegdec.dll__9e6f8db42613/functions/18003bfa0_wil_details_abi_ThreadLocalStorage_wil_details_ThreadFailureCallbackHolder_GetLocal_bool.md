# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18003bfa0`
- end: `0x18003bff6`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18003b7fc`

## callees

- `0x18003bfa0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003bfad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003bfad`

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
0x18003bfa0  push    rbx
0x18003bfa2  sub     rsp, 20h
0x18003bfa6  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18003bfad  call    cs:__imp_GetCurrentThreadId
0x18003bfb3  mov     r8d, eax
0x18003bfb6  mov     r9d, eax
0x18003bfb9  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18003bfc3  shr     r8, 2
0x18003bfc7  mul     r8
0x18003bfca  shr     rdx, 3
0x18003bfce  lea     rcx, [rdx+rdx*4]
0x18003bfd2  add     rcx, rcx
0x18003bfd5  sub     r8, rcx
0x18003bfd8  mov     rax, [rbx+r8*8]
0x18003bfdc  test    rax, rax
0x18003bfdf  jz      short loc_18003BFF0
0x18003bfe1  cmp     [rax], r9d
0x18003bfe4  jz      short loc_18003BFEC
0x18003bfe6  mov     rax, [rax+8]
0x18003bfea  jmp     short loc_18003BFDC
0x18003bfec  add     rax, 10h
0x18003bff0  add     rsp, 20h
0x18003bff4  pop     rbx
0x18003bff5  retn
```
