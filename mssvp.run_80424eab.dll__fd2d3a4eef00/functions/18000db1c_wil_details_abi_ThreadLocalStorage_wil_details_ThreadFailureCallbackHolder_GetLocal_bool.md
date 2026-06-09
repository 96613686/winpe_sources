# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18000db1c`
- end: `0x18000db72`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d970`

## callees

- `0x18000db1c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000db29`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000db29`

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
0x18000db1c  push    rbx
0x18000db1e  sub     rsp, 20h
0x18000db22  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000db29  call    cs:__imp_GetCurrentThreadId
0x18000db2f  mov     r8d, eax
0x18000db32  mov     r9d, eax
0x18000db35  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000db3f  shr     r8, 2
0x18000db43  mul     r8
0x18000db46  shr     rdx, 3
0x18000db4a  lea     rcx, [rdx+rdx*4]
0x18000db4e  add     rcx, rcx
0x18000db51  sub     r8, rcx
0x18000db54  mov     rax, [rbx+r8*8]
0x18000db58  test    rax, rax
0x18000db5b  jz      short loc_18000DB6C
0x18000db5d  cmp     [rax], r9d
0x18000db60  jz      short loc_18000DB68
0x18000db62  mov     rax, [rax+8]
0x18000db66  jmp     short loc_18000DB58
0x18000db68  add     rax, 10h
0x18000db6c  add     rsp, 20h
0x18000db70  pop     rbx
0x18000db71  retn
```
