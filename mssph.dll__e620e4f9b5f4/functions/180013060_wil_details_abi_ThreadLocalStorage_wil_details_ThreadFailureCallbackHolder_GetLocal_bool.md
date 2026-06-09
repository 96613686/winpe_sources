# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180013060`
- end: `0x1800130b6`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180012c28`

## callees

- `0x180013060`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001306d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001306d`

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
0x180013060  push    rbx
0x180013062  sub     rsp, 20h
0x180013066  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18001306d  call    cs:__imp_GetCurrentThreadId
0x180013073  mov     r8d, eax
0x180013076  mov     r9d, eax
0x180013079  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180013083  shr     r8, 2
0x180013087  mul     r8
0x18001308a  shr     rdx, 3
0x18001308e  lea     rcx, [rdx+rdx*4]
0x180013092  add     rcx, rcx
0x180013095  sub     r8, rcx
0x180013098  mov     rax, [rbx+r8*8]
0x18001309c  test    rax, rax
0x18001309f  jz      short loc_1800130B0
0x1800130a1  cmp     [rax], r9d
0x1800130a4  jz      short loc_1800130AC
0x1800130a6  mov     rax, [rax+8]
0x1800130aa  jmp     short loc_18001309C
0x1800130ac  add     rax, 10h
0x1800130b0  add     rsp, 20h
0x1800130b4  pop     rbx
0x1800130b5  retn
```
