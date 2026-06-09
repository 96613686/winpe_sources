# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18000490c`
- end: `0x180004962`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180004438`

## callees

- `0x18000490c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004919`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004919`

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
0x18000490c  push    rbx
0x18000490e  sub     rsp, 20h
0x180004912  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180004919  call    cs:__imp_GetCurrentThreadId
0x18000491f  mov     r8d, eax
0x180004922  mov     r9d, eax
0x180004925  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000492f  shr     r8, 2
0x180004933  mul     r8
0x180004936  shr     rdx, 3
0x18000493a  lea     rcx, [rdx+rdx*4]
0x18000493e  add     rcx, rcx
0x180004941  sub     r8, rcx
0x180004944  mov     rax, [rbx+r8*8]
0x180004948  test    rax, rax
0x18000494b  jz      short loc_18000495C
0x18000494d  cmp     [rax], r9d
0x180004950  jz      short loc_180004958
0x180004952  mov     rax, [rax+8]
0x180004956  jmp     short loc_180004948
0x180004958  add     rax, 10h
0x18000495c  add     rsp, 20h
0x180004960  pop     rbx
0x180004961  retn
```
