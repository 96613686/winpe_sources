# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x140008d00`
- end: `0x140008d56`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400088c4`

## callees

- `0x140008d00`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140008d0d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140008d0d`

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
0x140008d00  push    rbx
0x140008d02  sub     rsp, 20h
0x140008d06  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140008d0d  call    cs:__imp_GetCurrentThreadId
0x140008d13  mov     r8d, eax
0x140008d16  mov     r9d, eax
0x140008d19  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140008d23  shr     r8, 2
0x140008d27  mul     r8
0x140008d2a  shr     rdx, 3
0x140008d2e  lea     rcx, [rdx+rdx*4]
0x140008d32  add     rcx, rcx
0x140008d35  sub     r8, rcx
0x140008d38  mov     rax, [rbx+r8*8]
0x140008d3c  test    rax, rax
0x140008d3f  jz      short loc_140008D50
0x140008d41  cmp     [rax], r9d
0x140008d44  jz      short loc_140008D4C
0x140008d46  mov     rax, [rax+8]
0x140008d4a  jmp     short loc_140008D3C
0x140008d4c  add     rax, 10h
0x140008d50  add     rsp, 20h
0x140008d54  pop     rbx
0x140008d55  retn
```
