# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18000464c`
- end: `0x1800046a2`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180004174`

## callees

- `0x18000464c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180004659`
- `KERNEL32!GetCurrentThreadId` at `0x180004659`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18000464c  push    rbx
0x18000464e  sub     rsp, 20h
0x180004652  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180004659  call    cs:__imp_GetCurrentThreadId
0x18000465f  mov     r8d, eax
0x180004662  mov     r9d, eax
0x180004665  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000466f  shr     r8, 2
0x180004673  mul     r8
0x180004676  shr     rdx, 3
0x18000467a  lea     rcx, [rdx+rdx*4]
0x18000467e  add     rcx, rcx
0x180004681  sub     r8, rcx
0x180004684  mov     rax, [rbx+r8*8]
0x180004688  test    rax, rax
0x18000468b  jz      short loc_18000469C
0x18000468d  cmp     [rax], r9d
0x180004690  jz      short loc_180004698
0x180004692  mov     rax, [rax+8]
0x180004696  jmp     short loc_180004688
0x180004698  add     rax, 10h
0x18000469c  add     rsp, 20h
0x1800046a0  pop     rbx
0x1800046a1  retn
```
