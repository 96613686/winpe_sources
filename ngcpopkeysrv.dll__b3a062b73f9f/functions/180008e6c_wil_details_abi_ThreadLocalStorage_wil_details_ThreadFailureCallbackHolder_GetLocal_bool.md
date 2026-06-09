# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180008e6c`
- end: `0x180008ec2`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180008994`

## callees

- `0x180008e6c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008e79`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008e79`

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
0x180008e6c  push    rbx
0x180008e6e  sub     rsp, 20h
0x180008e72  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180008e79  call    cs:__imp_GetCurrentThreadId
0x180008e7f  mov     r9d, eax
0x180008e82  mov     r8d, eax
0x180008e85  shr     r8, 2
0x180008e89  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180008e93  mul     r8
0x180008e96  shr     rdx, 3
0x180008e9a  lea     rcx, [rdx+rdx*4]
0x180008e9e  add     rcx, rcx
0x180008ea1  sub     r8, rcx
0x180008ea4  mov     rax, [rbx+r8*8]
0x180008ea8  test    rax, rax
0x180008eab  jz      short loc_180008EBC
0x180008ead  cmp     [rax], r9d
0x180008eb0  jz      short loc_180008EB8
0x180008eb2  mov     rax, [rax+8]
0x180008eb6  jmp     short loc_180008EA8
0x180008eb8  add     rax, 10h
0x180008ebc  add     rsp, 20h
0x180008ec0  pop     rbx
0x180008ec1  retn
```
