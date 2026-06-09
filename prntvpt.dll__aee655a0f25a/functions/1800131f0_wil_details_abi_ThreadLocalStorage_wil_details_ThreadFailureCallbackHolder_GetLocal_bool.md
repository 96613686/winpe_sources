# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x1800131f0`
- end: `0x180013246`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180012d2c`

## callees

- `0x1800131f0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800131fd`
- `KERNEL32!GetCurrentThreadId` at `0x1800131fd`

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
0x1800131f0  push    rbx
0x1800131f2  sub     rsp, 20h
0x1800131f6  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800131fd  call    cs:__imp_GetCurrentThreadId
0x180013203  mov     r8d, eax
0x180013206  mov     r9d, eax
0x180013209  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180013213  shr     r8, 2
0x180013217  mul     r8
0x18001321a  shr     rdx, 3
0x18001321e  lea     rcx, [rdx+rdx*4]
0x180013222  add     rcx, rcx
0x180013225  sub     r8, rcx
0x180013228  mov     rax, [rbx+r8*8]
0x18001322c  test    rax, rax
0x18001322f  jz      short loc_180013240
0x180013231  cmp     [rax], r9d
0x180013234  jz      short loc_18001323C
0x180013236  mov     rax, [rax+8]
0x18001323a  jmp     short loc_18001322C
0x18001323c  add     rax, 10h
0x180013240  add     rsp, 20h
0x180013244  pop     rbx
0x180013245  retn
```
