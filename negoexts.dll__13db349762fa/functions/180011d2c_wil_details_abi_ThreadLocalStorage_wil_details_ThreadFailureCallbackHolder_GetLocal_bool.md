# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180011d2c`
- end: `0x180011d82`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180011708`

## callees

- `0x180011d2c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011d39`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011d39`

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
0x180011d2c  push    rbx
0x180011d2e  sub     rsp, 20h
0x180011d32  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180011d39  call    cs:__imp_GetCurrentThreadId
0x180011d3f  mov     r8d, eax
0x180011d42  mov     r9d, eax
0x180011d45  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180011d4f  shr     r8, 2
0x180011d53  mul     r8
0x180011d56  shr     rdx, 3
0x180011d5a  lea     rcx, [rdx+rdx*4]
0x180011d5e  add     rcx, rcx
0x180011d61  sub     r8, rcx
0x180011d64  mov     rax, [rbx+r8*8]
0x180011d68  test    rax, rax
0x180011d6b  jz      short loc_180011D7C
0x180011d6d  cmp     [rax], r9d
0x180011d70  jz      short loc_180011D78
0x180011d72  mov     rax, [rax+8]
0x180011d76  jmp     short loc_180011D68
0x180011d78  add     rax, 10h
0x180011d7c  add     rsp, 20h
0x180011d80  pop     rbx
0x180011d81  retn
```
