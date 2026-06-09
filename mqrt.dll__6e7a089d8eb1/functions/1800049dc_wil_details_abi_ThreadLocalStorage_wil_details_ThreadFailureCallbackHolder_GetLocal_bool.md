# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x1800049dc`
- end: `0x180004a32`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180004504`

## callees

- `0x1800049dc`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800049e9`
- `KERNEL32!GetCurrentThreadId` at `0x1800049e9`

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
0x1800049dc  push    rbx
0x1800049de  sub     rsp, 20h
0x1800049e2  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800049e9  call    cs:__imp_GetCurrentThreadId
0x1800049ef  mov     r9d, eax
0x1800049f2  mov     r8d, eax
0x1800049f5  shr     r8, 2
0x1800049f9  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004a03  mul     r8
0x180004a06  shr     rdx, 3
0x180004a0a  lea     rcx, [rdx+rdx*4]
0x180004a0e  add     rcx, rcx
0x180004a11  sub     r8, rcx
0x180004a14  mov     rax, [rbx+r8*8]
0x180004a18  test    rax, rax
0x180004a1b  jz      short loc_180004A2C
0x180004a1d  cmp     [rax], r9d
0x180004a20  jz      short loc_180004A28
0x180004a22  mov     rax, [rax+8]
0x180004a26  jmp     short loc_180004A18
0x180004a28  add     rax, 10h
0x180004a2c  add     rsp, 20h
0x180004a30  pop     rbx
0x180004a31  retn
```
