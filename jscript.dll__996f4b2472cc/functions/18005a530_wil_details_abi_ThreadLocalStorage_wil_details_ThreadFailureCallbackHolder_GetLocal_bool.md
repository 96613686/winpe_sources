# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18005a530`
- end: `0x18005a58d`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `93`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18005a0d4`

## callees

- `0x18005a530`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18005a53d`
- `KERNEL32!GetCurrentThreadId` at `0x18005a53d`

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
0x18005a530  push    rbx
0x18005a532  sub     rsp, 20h
0x18005a536  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18005a53d  call    cs:__imp_GetCurrentThreadId
0x18005a544  nop     dword ptr [rax+rax+00h]
0x18005a549  mov     r8d, eax
0x18005a54c  mov     r9d, eax
0x18005a54f  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18005a559  shr     r8, 2
0x18005a55d  mul     r8
0x18005a560  shr     rdx, 3
0x18005a564  lea     rcx, [rdx+rdx*4]
0x18005a568  add     rcx, rcx
0x18005a56b  sub     r8, rcx
0x18005a56e  mov     rax, [rbx+r8*8]
0x18005a572  test    rax, rax
0x18005a575  jz      short loc_18005A586
0x18005a577  cmp     [rax], r9d
0x18005a57a  jz      short loc_18005A582
0x18005a57c  mov     rax, [rax+8]
0x18005a580  jmp     short loc_18005A572
0x18005a582  add     rax, 10h
0x18005a586  add     rsp, 20h
0x18005a58a  pop     rbx
0x18005a58b  retn
```
