# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18007755c`
- end: `0x1800775b4`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `88`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180076fe0`

## callees

- `0x18007755c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180077569`
- `KERNEL32!GetCurrentThreadId` at `0x180077569`

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
0x18007755c  push    rbx
0x18007755e  sub     rsp, 20h
0x180077562  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180077569  call    cs:__imp_GetCurrentThreadId
0x18007756f  mov     r8d, eax
0x180077572  mov     r9d, eax
0x180077575  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18007757f  shr     r8, 2
0x180077583  mul     r8
0x180077586  shr     rdx, 3
0x18007758a  lea     rcx, [rdx+rdx*4]
0x18007758e  add     rcx, rcx
0x180077591  sub     r8, rcx
0x180077594  mov     rax, [rbx+r8*8]
0x180077598  jmp     short loc_1800775A3
0x18007759a  cmp     [rax], r9d
0x18007759d  jz      short loc_1800775AE
0x18007759f  mov     rax, [rax+8]
0x1800775a3  test    rax, rax
0x1800775a6  jnz     short loc_18007759A
0x1800775a8  add     rsp, 20h
0x1800775ac  pop     rbx
0x1800775ad  retn
0x1800775ae  add     rax, 10h
0x1800775b2  jmp     short loc_1800775A8
```
