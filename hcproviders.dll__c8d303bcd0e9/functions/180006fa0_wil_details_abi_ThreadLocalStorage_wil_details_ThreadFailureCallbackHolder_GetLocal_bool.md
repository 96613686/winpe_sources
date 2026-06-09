# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180006fa0`
- end: `0x180006ffd`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `93`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180006b44`

## callees

- `0x180006fa0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006fad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006fad`

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
0x180006fa0  push    rbx
0x180006fa2  sub     rsp, 20h
0x180006fa6  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180006fad  call    cs:__imp_GetCurrentThreadId
0x180006fb4  nop     dword ptr [rax+rax+00h]
0x180006fb9  mov     r8d, eax
0x180006fbc  mov     r9d, eax
0x180006fbf  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180006fc9  shr     r8, 2
0x180006fcd  mul     r8
0x180006fd0  shr     rdx, 3
0x180006fd4  lea     rcx, [rdx+rdx*4]
0x180006fd8  add     rcx, rcx
0x180006fdb  sub     r8, rcx
0x180006fde  mov     rax, [rbx+r8*8]
0x180006fe2  test    rax, rax
0x180006fe5  jz      short loc_180006FF6
0x180006fe7  cmp     [rax], r9d
0x180006fea  jz      short loc_180006FF2
0x180006fec  mov     rax, [rax+8]
0x180006ff0  jmp     short loc_180006FE2
0x180006ff2  add     rax, 10h
0x180006ff6  add     rsp, 20h
0x180006ffa  pop     rbx
0x180006ffb  retn
```
