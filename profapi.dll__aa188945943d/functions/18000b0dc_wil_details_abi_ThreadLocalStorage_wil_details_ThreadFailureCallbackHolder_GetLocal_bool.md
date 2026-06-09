# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18000b0dc`
- end: `0x18000b134`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `88`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000204c`

## callees

- `0x18000b0dc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b0e9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b0e9`

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
0x18000b0dc  push    rbx
0x18000b0de  sub     rsp, 20h
0x18000b0e2  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000b0e9  call    cs:__imp_GetCurrentThreadId
0x18000b0ef  mov     r8d, eax
0x18000b0f2  mov     r9d, eax
0x18000b0f5  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000b0ff  shr     r8, 2
0x18000b103  mul     r8
0x18000b106  shr     rdx, 3
0x18000b10a  lea     rcx, [rdx+rdx*4]
0x18000b10e  add     rcx, rcx
0x18000b111  sub     r8, rcx
0x18000b114  mov     rax, [rbx+r8*8]
0x18000b118  test    rax, rax
0x18000b11b  jnz     short loc_18000B123
0x18000b11d  add     rsp, 20h
0x18000b121  pop     rbx
0x18000b122  retn
0x18000b123  cmp     [rax], r9d
0x18000b126  jz      short loc_18000B12E
0x18000b128  mov     rax, [rax+8]
0x18000b12c  jmp     short loc_18000B118
0x18000b12e  add     rax, 10h
0x18000b132  jmp     short loc_18000B11D
```
