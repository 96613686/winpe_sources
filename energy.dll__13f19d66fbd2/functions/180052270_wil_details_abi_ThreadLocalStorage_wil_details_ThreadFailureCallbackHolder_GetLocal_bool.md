# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180052270`
- end: `0x1800522c6`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180051e38`

## callees

- `0x180052270`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005227d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005227d`

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
0x180052270  push    rbx
0x180052272  sub     rsp, 20h
0x180052276  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18005227d  call    cs:__imp_GetCurrentThreadId
0x180052283  mov     r8d, eax
0x180052286  mov     r9d, eax
0x180052289  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180052293  shr     r8, 2
0x180052297  mul     r8
0x18005229a  shr     rdx, 3
0x18005229e  lea     rcx, [rdx+rdx*4]
0x1800522a2  add     rcx, rcx
0x1800522a5  sub     r8, rcx
0x1800522a8  mov     rax, [rbx+r8*8]
0x1800522ac  test    rax, rax
0x1800522af  jz      short loc_1800522C0
0x1800522b1  cmp     [rax], r9d
0x1800522b4  jz      short loc_1800522BC
0x1800522b6  mov     rax, [rax+8]
0x1800522ba  jmp     short loc_1800522AC
0x1800522bc  add     rax, 10h
0x1800522c0  add     rsp, 20h
0x1800522c4  pop     rbx
0x1800522c5  retn
```
