# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18000410c`
- end: `0x180004162`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003c34`

## callees

- `0x18000410c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004119`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004119`

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
0x18000410c  push    rbx
0x18000410e  sub     rsp, 20h
0x180004112  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180004119  call    cs:__imp_GetCurrentThreadId
0x18000411f  mov     r8d, eax
0x180004122  mov     r9d, eax
0x180004125  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000412f  shr     r8, 2
0x180004133  mul     r8
0x180004136  shr     rdx, 3
0x18000413a  lea     rcx, [rdx+rdx*4]
0x18000413e  add     rcx, rcx
0x180004141  sub     r8, rcx
0x180004144  mov     rax, [rbx+r8*8]
0x180004148  test    rax, rax
0x18000414b  jz      short loc_18000415C
0x18000414d  cmp     [rax], r9d
0x180004150  jz      short loc_180004158
0x180004152  mov     rax, [rax+8]
0x180004156  jmp     short loc_180004148
0x180004158  add     rax, 10h
0x18000415c  add     rsp, 20h
0x180004160  pop     rbx
0x180004161  retn
```
