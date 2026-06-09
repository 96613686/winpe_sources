# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x1800046ec`
- end: `0x180004742`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180004220`

## callees

- `0x1800046ec`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800046f9`
- `KERNEL32!GetCurrentThreadId` at `0x1800046f9`

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
0x1800046ec  push    rbx
0x1800046ee  sub     rsp, 20h
0x1800046f2  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800046f9  call    cs:__imp_GetCurrentThreadId
0x1800046ff  mov     r8d, eax
0x180004702  mov     r9d, eax
0x180004705  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000470f  shr     r8, 2
0x180004713  mul     r8
0x180004716  shr     rdx, 3
0x18000471a  lea     rcx, [rdx+rdx*4]
0x18000471e  add     rcx, rcx
0x180004721  sub     r8, rcx
0x180004724  mov     rax, [rbx+r8*8]
0x180004728  test    rax, rax
0x18000472b  jz      short loc_18000473C
0x18000472d  cmp     [rax], r9d
0x180004730  jz      short loc_180004738
0x180004732  mov     rax, [rax+8]
0x180004736  jmp     short loc_180004728
0x180004738  add     rax, 10h
0x18000473c  add     rsp, 20h
0x180004740  pop     rbx
0x180004741  retn
```
