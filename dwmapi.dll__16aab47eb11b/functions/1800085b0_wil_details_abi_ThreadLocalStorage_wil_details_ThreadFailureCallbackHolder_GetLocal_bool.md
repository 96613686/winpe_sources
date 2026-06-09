# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x1800085b0`
- end: `0x180008608`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `88`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000635c`

## callees

- `0x1800085b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800085bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800085bd`

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
0x1800085b0  push    rbx
0x1800085b2  sub     rsp, 20h
0x1800085b6  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800085bd  call    cs:__imp_GetCurrentThreadId
0x1800085c3  mov     r8d, eax
0x1800085c6  mov     r9d, eax
0x1800085c9  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800085d3  shr     r8, 2
0x1800085d7  mul     r8
0x1800085da  shr     rdx, 3
0x1800085de  lea     rcx, [rdx+rdx*4]
0x1800085e2  add     rcx, rcx
0x1800085e5  sub     r8, rcx
0x1800085e8  mov     rax, [rbx+r8*8]
0x1800085ec  test    rax, rax
0x1800085ef  jnz     short loc_1800085F7
0x1800085f1  add     rsp, 20h
0x1800085f5  pop     rbx
0x1800085f6  retn
0x1800085f7  cmp     [rax], r9d
0x1800085fa  jz      short loc_180008602
0x1800085fc  mov     rax, [rax+8]
0x180008600  jmp     short loc_1800085EC
0x180008602  add     rax, 10h
0x180008606  jmp     short loc_1800085F1
```
