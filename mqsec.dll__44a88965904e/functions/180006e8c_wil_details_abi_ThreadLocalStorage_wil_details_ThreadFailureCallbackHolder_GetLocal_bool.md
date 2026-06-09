# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180006e8c`
- end: `0x180006ee4`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `88`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800069b4`

## callees

- `0x180006e8c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180006e99`
- `KERNEL32!GetCurrentThreadId` at `0x180006e99`

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
0x180006e8c  push    rbx
0x180006e8e  sub     rsp, 20h
0x180006e92  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180006e99  call    cs:__imp_GetCurrentThreadId
0x180006e9f  mov     r9d, eax
0x180006ea2  mov     r8d, eax
0x180006ea5  shr     r8, 2
0x180006ea9  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180006eb3  mul     r8
0x180006eb6  shr     rdx, 3
0x180006eba  lea     rcx, [rdx+rdx*4]
0x180006ebe  add     rcx, rcx
0x180006ec1  sub     r8, rcx
0x180006ec4  mov     rax, [rbx+r8*8]
0x180006ec8  jmp     short loc_180006ED3
0x180006eca  cmp     [rax], r9d
0x180006ecd  jz      short loc_180006EDE
0x180006ecf  mov     rax, [rax+8]
0x180006ed3  test    rax, rax
0x180006ed6  jnz     short loc_180006ECA
0x180006ed8  add     rsp, 20h
0x180006edc  pop     rbx
0x180006edd  retn
0x180006ede  add     rax, 10h
0x180006ee2  jmp     short loc_180006ED8
```
