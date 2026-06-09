# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180004734`
- end: `0x180004791`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `93`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180004234`

## callees

- `0x180004734`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004741`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004741`

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
0x180004734  push    rbx
0x180004736  sub     rsp, 20h
0x18000473a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180004741  call    cs:__imp_GetCurrentThreadId
0x180004748  nop     dword ptr [rax+rax+00h]
0x18000474d  mov     r8d, eax
0x180004750  mov     r9d, eax
0x180004753  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000475d  shr     r8, 2
0x180004761  mul     r8
0x180004764  shr     rdx, 3
0x180004768  lea     rcx, [rdx+rdx*4]
0x18000476c  add     rcx, rcx
0x18000476f  sub     r8, rcx
0x180004772  mov     rax, [rbx+r8*8]
0x180004776  test    rax, rax
0x180004779  jz      short loc_18000478A
0x18000477b  cmp     [rax], r9d
0x18000477e  jz      short loc_180004786
0x180004780  mov     rax, [rax+8]
0x180004784  jmp     short loc_180004776
0x180004786  add     rax, 10h
0x18000478a  add     rsp, 20h
0x18000478e  pop     rbx
0x18000478f  retn
```
