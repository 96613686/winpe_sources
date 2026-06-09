# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180005ad0`
- end: `0x180005b26`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180005694`

## callees

- `0x180005ad0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005add`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005add`

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
0x180005ad0  push    rbx
0x180005ad2  sub     rsp, 20h
0x180005ad6  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180005add  call    cs:__imp_GetCurrentThreadId
0x180005ae3  mov     r8d, eax
0x180005ae6  mov     r9d, eax
0x180005ae9  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180005af3  shr     r8, 2
0x180005af7  mul     r8
0x180005afa  shr     rdx, 3
0x180005afe  lea     rcx, [rdx+rdx*4]
0x180005b02  add     rcx, rcx
0x180005b05  sub     r8, rcx
0x180005b08  mov     rax, [rbx+r8*8]
0x180005b0c  test    rax, rax
0x180005b0f  jz      short loc_180005B20
0x180005b11  cmp     [rax], r9d
0x180005b14  jz      short loc_180005B1C
0x180005b16  mov     rax, [rax+8]
0x180005b1a  jmp     short loc_180005B0C
0x180005b1c  add     rax, 10h
0x180005b20  add     rsp, 20h
0x180005b24  pop     rbx
0x180005b25  retn
```
