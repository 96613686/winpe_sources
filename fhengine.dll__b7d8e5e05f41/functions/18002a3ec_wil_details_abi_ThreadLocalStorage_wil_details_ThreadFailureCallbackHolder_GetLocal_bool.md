# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18002a3ec`
- end: `0x18002a444`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `88`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180029848`

## callees

- `0x18002a3ec`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18002a3f9`
- `KERNEL32!GetCurrentThreadId` at `0x18002a3f9`

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
0x18002a3ec  push    rbx
0x18002a3ee  sub     rsp, 20h
0x18002a3f2  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18002a3f9  call    cs:__imp_GetCurrentThreadId
0x18002a3ff  mov     r8d, eax
0x18002a402  mov     r9d, eax
0x18002a405  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18002a40f  shr     r8, 2
0x18002a413  mul     r8
0x18002a416  shr     rdx, 3
0x18002a41a  lea     rcx, [rdx+rdx*4]
0x18002a41e  add     rcx, rcx
0x18002a421  sub     r8, rcx
0x18002a424  mov     rax, [rbx+r8*8]
0x18002a428  jmp     short loc_18002A433
0x18002a42a  cmp     [rax], r9d
0x18002a42d  jz      short loc_18002A43E
0x18002a42f  mov     rax, [rax+8]
0x18002a433  test    rax, rax
0x18002a436  jnz     short loc_18002A42A
0x18002a438  add     rsp, 20h
0x18002a43c  pop     rbx
0x18002a43d  retn
0x18002a43e  add     rax, 10h
0x18002a442  jmp     short loc_18002A438
```
