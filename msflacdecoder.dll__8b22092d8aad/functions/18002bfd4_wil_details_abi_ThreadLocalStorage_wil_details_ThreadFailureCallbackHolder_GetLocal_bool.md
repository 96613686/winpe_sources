# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18002bfd4`
- end: `0x18002c02a`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002b87c`

## callees

- `0x18002bfd4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002bfe1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002bfe1`

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
0x18002bfd4  push    rbx
0x18002bfd6  sub     rsp, 20h
0x18002bfda  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18002bfe1  call    cs:__imp_GetCurrentThreadId
0x18002bfe7  mov     r8d, eax
0x18002bfea  mov     r9d, eax
0x18002bfed  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18002bff7  shr     r8, 2
0x18002bffb  mul     r8
0x18002bffe  shr     rdx, 3
0x18002c002  lea     rcx, [rdx+rdx*4]
0x18002c006  add     rcx, rcx
0x18002c009  sub     r8, rcx
0x18002c00c  mov     rax, [rbx+r8*8]
0x18002c010  test    rax, rax
0x18002c013  jz      short loc_18002C024
0x18002c015  cmp     [rax], r9d
0x18002c018  jz      short loc_18002C020
0x18002c01a  mov     rax, [rax+8]
0x18002c01e  jmp     short loc_18002C010
0x18002c020  add     rax, 10h
0x18002c024  add     rsp, 20h
0x18002c028  pop     rbx
0x18002c029  retn
```
