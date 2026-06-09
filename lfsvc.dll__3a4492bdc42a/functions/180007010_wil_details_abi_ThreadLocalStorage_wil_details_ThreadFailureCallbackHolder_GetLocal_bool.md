# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180007010`
- end: `0x180007066`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180006bd4`

## callees

- `0x180007010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000701d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000701d`

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
0x180007010  push    rbx
0x180007012  sub     rsp, 20h
0x180007016  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000701d  call    cs:__imp_GetCurrentThreadId
0x180007023  mov     r8d, eax
0x180007026  mov     r9d, eax
0x180007029  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180007033  shr     r8, 2
0x180007037  mul     r8
0x18000703a  shr     rdx, 3
0x18000703e  lea     rcx, [rdx+rdx*4]
0x180007042  add     rcx, rcx
0x180007045  sub     r8, rcx
0x180007048  mov     rax, [rbx+r8*8]
0x18000704c  test    rax, rax
0x18000704f  jz      short loc_180007060
0x180007051  cmp     [rax], r9d
0x180007054  jz      short loc_18000705C
0x180007056  mov     rax, [rax+8]
0x18000705a  jmp     short loc_18000704C
0x18000705c  add     rax, 10h
0x180007060  add     rsp, 20h
0x180007064  pop     rbx
0x180007065  retn
```
