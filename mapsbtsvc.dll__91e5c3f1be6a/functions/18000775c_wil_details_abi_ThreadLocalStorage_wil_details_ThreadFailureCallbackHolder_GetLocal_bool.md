# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18000775c`
- end: `0x1800077b2`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180007284`

## callees

- `0x18000775c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007769`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007769`

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
0x18000775c  push    rbx
0x18000775e  sub     rsp, 20h
0x180007762  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180007769  call    cs:__imp_GetCurrentThreadId
0x18000776f  mov     r8d, eax
0x180007772  mov     r9d, eax
0x180007775  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000777f  shr     r8, 2
0x180007783  mul     r8
0x180007786  shr     rdx, 3
0x18000778a  lea     rcx, [rdx+rdx*4]
0x18000778e  add     rcx, rcx
0x180007791  sub     r8, rcx
0x180007794  mov     rax, [rbx+r8*8]
0x180007798  test    rax, rax
0x18000779b  jz      short loc_1800077AC
0x18000779d  cmp     [rax], r9d
0x1800077a0  jz      short loc_1800077A8
0x1800077a2  mov     rax, [rax+8]
0x1800077a6  jmp     short loc_180007798
0x1800077a8  add     rax, 10h
0x1800077ac  add     rsp, 20h
0x1800077b0  pop     rbx
0x1800077b1  retn
```
