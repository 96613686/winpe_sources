# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180009908`
- end: `0x18000995e`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180008e24`

## callees

- `0x180009908`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009915`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009915`

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
0x180009908  push    rbx
0x18000990a  sub     rsp, 20h
0x18000990e  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180009915  call    cs:__imp_GetCurrentThreadId
0x18000991b  mov     r8d, eax
0x18000991e  mov     r9d, eax
0x180009921  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000992b  shr     r8, 2
0x18000992f  mul     r8
0x180009932  shr     rdx, 3
0x180009936  lea     rcx, [rdx+rdx*4]
0x18000993a  add     rcx, rcx
0x18000993d  sub     r8, rcx
0x180009940  mov     rax, [rbx+r8*8]
0x180009944  test    rax, rax
0x180009947  jz      short loc_180009958
0x180009949  cmp     [rax], r9d
0x18000994c  jz      short loc_180009954
0x18000994e  mov     rax, [rax+8]
0x180009952  jmp     short loc_180009944
0x180009954  add     rax, 10h
0x180009958  add     rsp, 20h
0x18000995c  pop     rbx
0x18000995d  retn
```
