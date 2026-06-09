# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,uint)

- ea: `0x10008050`
- end: `0x100080af`
- name: `?GetContextAndNotifyFailure@details@wil@@YGXPAUFailureInfo@2@PADI@Z`
- size: `95`
- prototype: `void(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x10007d55`
- `0x10007e10`
- `0x10007f59`
- `0x10008050`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x10008063`
- `KERNEL32!GetCurrentThreadId` at `0x10008063`

## pseudocode

```c

```

## disassembly

```asm
0x10008050  mov     edi, edi
0x10008052  push    ebp; this
0x10008053  mov     ebp, esp
0x10008055  push    [ebp+arg_8]; struct wil::FailureInfo *
0x10008058  mov     edx, [ebp+arg_4]
0x1000805b  mov     ecx, [ebp+arg_0]
0x1000805e  call    ?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SGXPAUFailureInfo@3@PADI@Z; wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,uint)
0x10008063  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x10008069  cmp     ?lastThread@?1??SetLastError@wil@@YGXABUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1000806f  jz      short loc_100080AB
0x10008071  xor     ecx, ecx
0x10008073  inc     ecx
0x10008074  lock xadd ?depth@?4??SetLastError@wil@@YGXABUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1000807c  inc     ecx
0x1000807d  cmp     ecx, 4
0x10008080  jge     short loc_100080A4
0x10008082  mov     ?lastThread@?1??SetLastError@wil@@YGXABUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x10008087  call    ?GetThreadLocalDataCache@details_abi@wil@@YGPAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x1000808c  test    eax, eax
0x1000808e  jz      short loc_1000809A
0x10008090  push    [ebp+arg_0]; struct wil::FailureInfo *
0x10008093  mov     ecx, eax; this
0x10008095  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QAEXABUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x1000809a  mov     ?lastThread@?1??SetLastError@wil@@YGXABUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x100080a4  lock dec ?depth@?4??SetLastError@wil@@YGXABUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x100080ab  pop     ebp
0x100080ac  retn    0Ch
```
