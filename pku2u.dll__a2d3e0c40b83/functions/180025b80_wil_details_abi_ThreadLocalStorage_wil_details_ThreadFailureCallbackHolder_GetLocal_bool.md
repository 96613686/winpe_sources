# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180025b80`
- end: `0x180025bd6`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001b804`

## callees

- `0x180025b80`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180025b8d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180025b8d`

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
0x180025b80  push    rbx
0x180025b82  sub     rsp, 20h
0x180025b86  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180025b8d  call    cs:__imp_GetCurrentThreadId
0x180025b93  mov     r8d, eax
0x180025b96  mov     r9d, eax
0x180025b99  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180025ba3  shr     r8, 2
0x180025ba7  mul     r8
0x180025baa  shr     rdx, 3
0x180025bae  lea     rcx, [rdx+rdx*4]
0x180025bb2  add     rcx, rcx
0x180025bb5  sub     r8, rcx
0x180025bb8  mov     rax, [rbx+r8*8]
0x180025bbc  test    rax, rax
0x180025bbf  jz      short loc_180025BD0
0x180025bc1  cmp     [rax], r9d
0x180025bc4  jz      short loc_180025BCC
0x180025bc6  mov     rax, [rax+8]
0x180025bca  jmp     short loc_180025BBC
0x180025bcc  add     rax, 10h
0x180025bd0  add     rsp, 20h
0x180025bd4  pop     rbx
0x180025bd5  retn
```
