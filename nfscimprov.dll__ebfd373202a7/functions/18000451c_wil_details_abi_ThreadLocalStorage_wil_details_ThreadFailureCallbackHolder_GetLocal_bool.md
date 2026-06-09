# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18000451c`
- end: `0x180004574`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `88`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180004044`

## callees

- `0x18000451c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180004529`
- `KERNEL32!GetCurrentThreadId` at `0x180004529`

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
0x18000451c  push    rbx
0x18000451e  sub     rsp, 20h
0x180004522  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180004529  call    cs:__imp_GetCurrentThreadId
0x18000452f  mov     r8d, eax
0x180004532  mov     r9d, eax
0x180004535  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000453f  shr     r8, 2
0x180004543  mul     r8
0x180004546  shr     rdx, 3
0x18000454a  lea     rcx, [rdx+rdx*4]
0x18000454e  add     rcx, rcx
0x180004551  sub     r8, rcx
0x180004554  mov     rax, [rbx+r8*8]
0x180004558  jmp     short loc_180004563
0x18000455a  cmp     [rax], r9d
0x18000455d  jz      short loc_18000456E
0x18000455f  mov     rax, [rax+8]
0x180004563  test    rax, rax
0x180004566  jnz     short loc_18000455A
0x180004568  add     rsp, 20h
0x18000456c  pop     rbx
0x18000456d  retn
0x18000456e  add     rax, 10h
0x180004572  jmp     short loc_180004568
```
