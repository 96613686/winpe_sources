# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180019cc0`
- end: `0x180019d1d`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `93`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180019868`

## callees

- `0x180019cc0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019ccd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019ccd`

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
0x180019cc0  push    rbx
0x180019cc2  sub     rsp, 20h
0x180019cc6  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180019ccd  call    cs:__imp_GetCurrentThreadId
0x180019cd4  nop     dword ptr [rax+rax+00h]
0x180019cd9  mov     r8d, eax
0x180019cdc  mov     r9d, eax
0x180019cdf  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180019ce9  shr     r8, 2
0x180019ced  mul     r8
0x180019cf0  shr     rdx, 3
0x180019cf4  lea     rcx, [rdx+rdx*4]
0x180019cf8  add     rcx, rcx
0x180019cfb  sub     r8, rcx
0x180019cfe  mov     rax, [rbx+r8*8]
0x180019d02  test    rax, rax
0x180019d05  jz      short loc_180019D16
0x180019d07  cmp     [rax], r9d
0x180019d0a  jz      short loc_180019D12
0x180019d0c  mov     rax, [rax+8]
0x180019d10  jmp     short loc_180019D02
0x180019d12  add     rax, 10h
0x180019d16  add     rsp, 20h
0x180019d1a  pop     rbx
0x180019d1b  retn
```
