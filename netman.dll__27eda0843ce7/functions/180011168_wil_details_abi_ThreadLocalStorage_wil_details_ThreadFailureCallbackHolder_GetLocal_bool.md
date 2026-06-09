# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180011168`
- end: `0x1800111c0`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `88`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800109e8`

## callees

- `0x180011168`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180011175`
- `KERNEL32!GetCurrentThreadId` at `0x180011175`

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
0x180011168  push    rbx
0x18001116a  sub     rsp, 20h
0x18001116e  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180011175  call    cs:__imp_GetCurrentThreadId
0x18001117b  mov     r8d, eax
0x18001117e  mov     r9d, eax
0x180011181  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18001118b  shr     r8, 2
0x18001118f  mul     r8
0x180011192  shr     rdx, 3
0x180011196  lea     rcx, [rdx+rdx*4]
0x18001119a  add     rcx, rcx
0x18001119d  sub     r8, rcx
0x1800111a0  mov     rax, [rbx+r8*8]
0x1800111a4  jmp     short loc_1800111AF
0x1800111a6  cmp     [rax], r9d
0x1800111a9  jz      short loc_1800111BA
0x1800111ab  mov     rax, [rax+8]
0x1800111af  test    rax, rax
0x1800111b2  jnz     short loc_1800111A6
0x1800111b4  add     rsp, 20h
0x1800111b8  pop     rbx
0x1800111b9  retn
0x1800111ba  add     rax, 10h
0x1800111be  jmp     short loc_1800111B4
```
