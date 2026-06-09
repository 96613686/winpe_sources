# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180015c38`
- end: `0x180015c95`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `93`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180011404`

## callees

- `0x180015c38`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180015c45`
- `KERNEL32!GetCurrentThreadId` at `0x180015c45`

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
0x180015c38  push    rbx
0x180015c3a  sub     rsp, 20h
0x180015c3e  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180015c45  call    cs:__imp_GetCurrentThreadId
0x180015c4c  nop     dword ptr [rax+rax+00h]
0x180015c51  mov     r8d, eax
0x180015c54  mov     r9d, eax
0x180015c57  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180015c61  shr     r8, 2
0x180015c65  mul     r8
0x180015c68  shr     rdx, 3
0x180015c6c  lea     rcx, [rdx+rdx*4]
0x180015c70  add     rcx, rcx
0x180015c73  sub     r8, rcx
0x180015c76  mov     rax, [rbx+r8*8]
0x180015c7a  test    rax, rax
0x180015c7d  jz      short loc_180015C8E
0x180015c7f  cmp     [rax], r9d
0x180015c82  jz      short loc_180015C8A
0x180015c84  mov     rax, [rax+8]
0x180015c88  jmp     short loc_180015C7A
0x180015c8a  add     rax, 10h
0x180015c8e  add     rsp, 20h
0x180015c92  pop     rbx
0x180015c93  retn
```
