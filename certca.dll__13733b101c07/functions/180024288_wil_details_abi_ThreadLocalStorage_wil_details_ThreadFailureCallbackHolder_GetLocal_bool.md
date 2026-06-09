# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180024288`
- end: `0x1800242e0`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `88`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800240b4`

## callees

- `0x180024288`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180024295`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180024295`

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
0x180024288  push    rbx
0x18002428a  sub     rsp, 20h
0x18002428e  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180024295  call    cs:__imp_GetCurrentThreadId
0x18002429b  mov     r9d, eax
0x18002429e  mov     r8d, eax
0x1800242a1  shr     r8, 2
0x1800242a5  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800242af  mul     r8
0x1800242b2  shr     rdx, 3
0x1800242b6  lea     rcx, [rdx+rdx*4]
0x1800242ba  add     rcx, rcx
0x1800242bd  sub     r8, rcx
0x1800242c0  mov     rax, [rbx+r8*8]
0x1800242c4  jmp     short loc_1800242CF
0x1800242c6  cmp     [rax], r9d
0x1800242c9  jz      short loc_1800242DA
0x1800242cb  mov     rax, [rax+8]
0x1800242cf  test    rax, rax
0x1800242d2  jnz     short loc_1800242C6
0x1800242d4  add     rsp, 20h
0x1800242d8  pop     rbx
0x1800242d9  retn
0x1800242da  add     rax, 10h
0x1800242de  jmp     short loc_1800242D4
```
