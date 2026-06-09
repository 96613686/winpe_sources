# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180059520`
- end: `0x180059576`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800590ec`

## callees

- `0x180059520`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18005952d`
- `KERNEL32!GetCurrentThreadId` at `0x18005952d`

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
0x180059520  push    rbx
0x180059522  sub     rsp, 20h
0x180059526  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18005952d  call    cs:__imp_GetCurrentThreadId
0x180059533  mov     r8d, eax
0x180059536  mov     r9d, eax
0x180059539  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180059543  shr     r8, 2
0x180059547  mul     r8
0x18005954a  shr     rdx, 3
0x18005954e  lea     rcx, [rdx+rdx*4]
0x180059552  add     rcx, rcx
0x180059555  sub     r8, rcx
0x180059558  mov     rax, [rbx+r8*8]
0x18005955c  test    rax, rax
0x18005955f  jz      short loc_180059570
0x180059561  cmp     [rax], r9d
0x180059564  jz      short loc_18005956C
0x180059566  mov     rax, [rax+8]
0x18005956a  jmp     short loc_18005955C
0x18005956c  add     rax, 10h
0x180059570  add     rsp, 20h
0x180059574  pop     rbx
0x180059575  retn
```
