# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18001327c`
- end: `0x1800132d2`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180012c24`

## callees

- `0x18001327c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013289`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013289`

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
0x18001327c  push    rbx
0x18001327e  sub     rsp, 20h
0x180013282  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180013289  call    cs:__imp_GetCurrentThreadId
0x18001328f  mov     r8d, eax
0x180013292  mov     r9d, eax
0x180013295  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18001329f  shr     r8, 2
0x1800132a3  mul     r8
0x1800132a6  shr     rdx, 3
0x1800132aa  lea     rcx, [rdx+rdx*4]
0x1800132ae  add     rcx, rcx
0x1800132b1  sub     r8, rcx
0x1800132b4  mov     rax, [rbx+r8*8]
0x1800132b8  test    rax, rax
0x1800132bb  jz      short loc_1800132CC
0x1800132bd  cmp     [rax], r9d
0x1800132c0  jz      short loc_1800132C8
0x1800132c2  mov     rax, [rax+8]
0x1800132c6  jmp     short loc_1800132B8
0x1800132c8  add     rax, 10h
0x1800132cc  add     rsp, 20h
0x1800132d0  pop     rbx
0x1800132d1  retn
```
