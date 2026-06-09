# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180004a44`
- end: `0x180004aa1`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `93`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180004544`

## callees

- `0x180004a44`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004a51`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004a51`

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
0x180004a44  push    rbx
0x180004a46  sub     rsp, 20h
0x180004a4a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180004a51  call    cs:__imp_GetCurrentThreadId
0x180004a58  nop     dword ptr [rax+rax+00h]
0x180004a5d  mov     r8d, eax
0x180004a60  mov     r9d, eax
0x180004a63  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004a6d  shr     r8, 2
0x180004a71  mul     r8
0x180004a74  shr     rdx, 3
0x180004a78  lea     rcx, [rdx+rdx*4]
0x180004a7c  add     rcx, rcx
0x180004a7f  sub     r8, rcx
0x180004a82  mov     rax, [rbx+r8*8]
0x180004a86  test    rax, rax
0x180004a89  jz      short loc_180004A9A
0x180004a8b  cmp     [rax], r9d
0x180004a8e  jz      short loc_180004A96
0x180004a90  mov     rax, [rax+8]
0x180004a94  jmp     short loc_180004A86
0x180004a96  add     rax, 10h
0x180004a9a  add     rsp, 20h
0x180004a9e  pop     rbx
0x180004a9f  retn
```
