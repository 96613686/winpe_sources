# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x1400120d0`
- end: `0x140012126`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140011c98`

## callees

- `0x1400120d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400120dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400120dd`

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
0x1400120d0  push    rbx
0x1400120d2  sub     rsp, 20h
0x1400120d6  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1400120dd  call    cs:__imp_GetCurrentThreadId
0x1400120e3  mov     r8d, eax
0x1400120e6  mov     r9d, eax
0x1400120e9  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1400120f3  shr     r8, 2
0x1400120f7  mul     r8
0x1400120fa  shr     rdx, 3
0x1400120fe  lea     rcx, [rdx+rdx*4]
0x140012102  add     rcx, rcx
0x140012105  sub     r8, rcx
0x140012108  mov     rax, [rbx+r8*8]
0x14001210c  test    rax, rax
0x14001210f  jz      short loc_140012120
0x140012111  cmp     [rax], r9d
0x140012114  jz      short loc_14001211C
0x140012116  mov     rax, [rax+8]
0x14001211a  jmp     short loc_14001210C
0x14001211c  add     rax, 10h
0x140012120  add     rsp, 20h
0x140012124  pop     rbx
0x140012125  retn
```
