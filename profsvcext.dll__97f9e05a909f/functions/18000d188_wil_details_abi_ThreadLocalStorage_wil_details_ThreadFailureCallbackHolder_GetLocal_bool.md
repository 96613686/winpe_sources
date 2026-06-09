# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18000d188`
- end: `0x18000d1de`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000cd28`

## callees

- `0x18000d188`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d195`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d195`

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
0x18000d188  push    rbx
0x18000d18a  sub     rsp, 20h
0x18000d18e  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000d195  call    cs:__imp_GetCurrentThreadId
0x18000d19b  mov     r8d, eax
0x18000d19e  mov     r9d, eax
0x18000d1a1  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000d1ab  shr     r8, 2
0x18000d1af  mul     r8
0x18000d1b2  shr     rdx, 3
0x18000d1b6  lea     rcx, [rdx+rdx*4]
0x18000d1ba  add     rcx, rcx
0x18000d1bd  sub     r8, rcx
0x18000d1c0  mov     rax, [rbx+r8*8]
0x18000d1c4  test    rax, rax
0x18000d1c7  jz      short loc_18000D1D8
0x18000d1c9  cmp     [rax], r9d
0x18000d1cc  jz      short loc_18000D1D4
0x18000d1ce  mov     rax, [rax+8]
0x18000d1d2  jmp     short loc_18000D1C4
0x18000d1d4  add     rax, 10h
0x18000d1d8  add     rsp, 20h
0x18000d1dc  pop     rbx
0x18000d1dd  retn
```
