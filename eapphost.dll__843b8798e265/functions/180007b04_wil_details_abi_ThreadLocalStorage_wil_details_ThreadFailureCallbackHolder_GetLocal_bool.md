# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180007b04`
- end: `0x180007b61`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `93`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180007608`

## callees

- `0x180007b04`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007b11`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007b11`

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
0x180007b04  push    rbx
0x180007b06  sub     rsp, 20h
0x180007b0a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180007b11  call    cs:__imp_GetCurrentThreadId
0x180007b18  nop     dword ptr [rax+rax+00h]
0x180007b1d  mov     r8d, eax
0x180007b20  mov     r9d, eax
0x180007b23  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180007b2d  shr     r8, 2
0x180007b31  mul     r8
0x180007b34  shr     rdx, 3
0x180007b38  lea     rcx, [rdx+rdx*4]
0x180007b3c  add     rcx, rcx
0x180007b3f  sub     r8, rcx
0x180007b42  mov     rax, [rbx+r8*8]
0x180007b46  test    rax, rax
0x180007b49  jz      short loc_180007B5A
0x180007b4b  cmp     [rax], r9d
0x180007b4e  jz      short loc_180007B56
0x180007b50  mov     rax, [rax+8]
0x180007b54  jmp     short loc_180007B46
0x180007b56  add     rax, 10h
0x180007b5a  add     rsp, 20h
0x180007b5e  pop     rbx
0x180007b5f  retn
```
