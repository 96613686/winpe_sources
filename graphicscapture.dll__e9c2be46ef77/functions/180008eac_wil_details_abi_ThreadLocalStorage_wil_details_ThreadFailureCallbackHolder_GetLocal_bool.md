# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180008eac`
- end: `0x180008f02`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800089d4`

## callees

- `0x180008eac`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008eb9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008eb9`

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
0x180008eac  push    rbx
0x180008eae  sub     rsp, 20h
0x180008eb2  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180008eb9  call    cs:__imp_GetCurrentThreadId
0x180008ebf  mov     r8d, eax
0x180008ec2  mov     r9d, eax
0x180008ec5  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180008ecf  shr     r8, 2
0x180008ed3  mul     r8
0x180008ed6  shr     rdx, 3
0x180008eda  lea     rcx, [rdx+rdx*4]
0x180008ede  add     rcx, rcx
0x180008ee1  sub     r8, rcx
0x180008ee4  mov     rax, [rbx+r8*8]
0x180008ee8  test    rax, rax
0x180008eeb  jz      short loc_180008EFC
0x180008eed  cmp     [rax], r9d
0x180008ef0  jz      short loc_180008EF8
0x180008ef2  mov     rax, [rax+8]
0x180008ef6  jmp     short loc_180008EE8
0x180008ef8  add     rax, 10h
0x180008efc  add     rsp, 20h
0x180008f00  pop     rbx
0x180008f01  retn
```
