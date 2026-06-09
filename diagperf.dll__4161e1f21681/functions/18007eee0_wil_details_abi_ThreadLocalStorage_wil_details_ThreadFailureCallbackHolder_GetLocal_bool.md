# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18007eee0`
- end: `0x18007ef36`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18007e73c`

## callees

- `0x18007eee0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007eeed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007eeed`

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
0x18007eee0  push    rbx
0x18007eee2  sub     rsp, 20h
0x18007eee6  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18007eeed  call    cs:__imp_GetCurrentThreadId
0x18007eef3  mov     r8d, eax
0x18007eef6  mov     r9d, eax
0x18007eef9  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18007ef03  shr     r8, 2
0x18007ef07  mul     r8
0x18007ef0a  shr     rdx, 3
0x18007ef0e  lea     rcx, [rdx+rdx*4]
0x18007ef12  add     rcx, rcx
0x18007ef15  sub     r8, rcx
0x18007ef18  mov     rax, [rbx+r8*8]
0x18007ef1c  test    rax, rax
0x18007ef1f  jz      short loc_18007EF30
0x18007ef21  cmp     [rax], r9d
0x18007ef24  jz      short loc_18007EF2C
0x18007ef26  mov     rax, [rax+8]
0x18007ef2a  jmp     short loc_18007EF1C
0x18007ef2c  add     rax, 10h
0x18007ef30  add     rsp, 20h
0x18007ef34  pop     rbx
0x18007ef35  retn
```
