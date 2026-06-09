# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18000783c`
- end: `0x180007892`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180007364`

## callees

- `0x18000783c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007849`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007849`

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
0x18000783c  push    rbx
0x18000783e  sub     rsp, 20h
0x180007842  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180007849  call    cs:__imp_GetCurrentThreadId
0x18000784f  mov     r8d, eax
0x180007852  mov     r9d, eax
0x180007855  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000785f  shr     r8, 2
0x180007863  mul     r8
0x180007866  shr     rdx, 3
0x18000786a  lea     rcx, [rdx+rdx*4]
0x18000786e  add     rcx, rcx
0x180007871  sub     r8, rcx
0x180007874  mov     rax, [rbx+r8*8]
0x180007878  test    rax, rax
0x18000787b  jz      short loc_18000788C
0x18000787d  cmp     [rax], r9d
0x180007880  jz      short loc_180007888
0x180007882  mov     rax, [rax+8]
0x180007886  jmp     short loc_180007878
0x180007888  add     rax, 10h
0x18000788c  add     rsp, 20h
0x180007890  pop     rbx
0x180007891  retn
```
