# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18001aa6c`
- end: `0x18001aac2`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001a594`

## callees

- `0x18001aa6c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001aa79`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001aa79`

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
0x18001aa6c  push    rbx
0x18001aa6e  sub     rsp, 20h
0x18001aa72  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18001aa79  call    cs:__imp_GetCurrentThreadId
0x18001aa7f  mov     r8d, eax
0x18001aa82  mov     r9d, eax
0x18001aa85  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18001aa8f  shr     r8, 2
0x18001aa93  mul     r8
0x18001aa96  shr     rdx, 3
0x18001aa9a  lea     rcx, [rdx+rdx*4]
0x18001aa9e  add     rcx, rcx
0x18001aaa1  sub     r8, rcx
0x18001aaa4  mov     rax, [rbx+r8*8]
0x18001aaa8  test    rax, rax
0x18001aaab  jz      short loc_18001AABC
0x18001aaad  cmp     [rax], r9d
0x18001aab0  jz      short loc_18001AAB8
0x18001aab2  mov     rax, [rax+8]
0x18001aab6  jmp     short loc_18001AAA8
0x18001aab8  add     rax, 10h
0x18001aabc  add     rsp, 20h
0x18001aac0  pop     rbx
0x18001aac1  retn
```
