# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18000a944`
- end: `0x18000a99c`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `88`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a27c`

## callees

- `0x18000a944`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a951`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a951`

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
0x18000a944  push    rbx
0x18000a946  sub     rsp, 20h
0x18000a94a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000a951  call    cs:__imp_GetCurrentThreadId
0x18000a957  mov     r8d, eax
0x18000a95a  mov     r9d, eax
0x18000a95d  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000a967  shr     r8, 2
0x18000a96b  mul     r8
0x18000a96e  shr     rdx, 3
0x18000a972  lea     rcx, [rdx+rdx*4]
0x18000a976  add     rcx, rcx
0x18000a979  sub     r8, rcx
0x18000a97c  mov     rax, [rbx+r8*8]
0x18000a980  test    rax, rax
0x18000a983  jnz     short loc_18000A98B
0x18000a985  add     rsp, 20h
0x18000a989  pop     rbx
0x18000a98a  retn
0x18000a98b  cmp     [rax], r9d
0x18000a98e  jz      short loc_18000A996
0x18000a990  mov     rax, [rax+8]
0x18000a994  jmp     short loc_18000A980
0x18000a996  add     rax, 10h
0x18000a99a  jmp     short loc_18000A985
```
