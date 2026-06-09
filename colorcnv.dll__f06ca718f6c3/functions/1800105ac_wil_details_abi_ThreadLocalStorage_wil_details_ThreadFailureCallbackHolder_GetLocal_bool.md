# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x1800105ac`
- end: `0x180010602`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800100d4`

## callees

- `0x1800105ac`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800105b9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800105b9`

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
0x1800105ac  push    rbx
0x1800105ae  sub     rsp, 20h
0x1800105b2  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800105b9  call    cs:__imp_GetCurrentThreadId
0x1800105bf  mov     r8d, eax
0x1800105c2  mov     r9d, eax
0x1800105c5  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800105cf  shr     r8, 2
0x1800105d3  mul     r8
0x1800105d6  shr     rdx, 3
0x1800105da  lea     rcx, [rdx+rdx*4]
0x1800105de  add     rcx, rcx
0x1800105e1  sub     r8, rcx
0x1800105e4  mov     rax, [rbx+r8*8]
0x1800105e8  test    rax, rax
0x1800105eb  jz      short loc_1800105FC
0x1800105ed  cmp     [rax], r9d
0x1800105f0  jz      short loc_1800105F8
0x1800105f2  mov     rax, [rax+8]
0x1800105f6  jmp     short loc_1800105E8
0x1800105f8  add     rax, 10h
0x1800105fc  add     rsp, 20h
0x180010600  pop     rbx
0x180010601  retn
```
