# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180013550`
- end: `0x1800135a6`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180013080`

## callees

- `0x180013550`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001355d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001355d`

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
0x180013550  push    rbx
0x180013552  sub     rsp, 20h
0x180013556  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18001355d  call    cs:__imp_GetCurrentThreadId
0x180013563  mov     r8d, eax
0x180013566  mov     r9d, eax
0x180013569  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180013573  shr     r8, 2
0x180013577  mul     r8
0x18001357a  shr     rdx, 3
0x18001357e  lea     rcx, [rdx+rdx*4]
0x180013582  add     rcx, rcx
0x180013585  sub     r8, rcx
0x180013588  mov     rax, [rbx+r8*8]
0x18001358c  test    rax, rax
0x18001358f  jz      short loc_1800135A0
0x180013591  cmp     [rax], r9d
0x180013594  jz      short loc_18001359C
0x180013596  mov     rax, [rax+8]
0x18001359a  jmp     short loc_18001358C
0x18001359c  add     rax, 10h
0x1800135a0  add     rsp, 20h
0x1800135a4  pop     rbx
0x1800135a5  retn
```
