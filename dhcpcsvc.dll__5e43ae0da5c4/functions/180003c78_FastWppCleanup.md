# FastWppCleanup

- ea: `0x180003c78`
- end: `0x180003cda`
- name: `FastWppCleanup`
- size: `98`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002f40`

## callees

- `0x180003ce0`

## import_xrefs

- `api-ms-win-downlevel-kernel32-l1-1-0!DeleteCriticalSection` at `0x180003cc5`
- `api-ms-win-downlevel-kernel32-l1-1-0!DeleteCriticalSection` at `0x180003cc5`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180003c83`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180003c83`

## pseudocode

```c
void FastWppCleanup()
{
  EventUnregister(FastWppRegHandle);
  FastWppRegHandle = 0;
  FastWppCallback(0, 0, 0, 0, 0, 0, 0);
  DeleteCriticalSection(&FastWppCallbackLock);
  FastWppInitState = 0;
}

```

## disassembly

```asm
0x180003c78  sub     rsp, 48h
0x180003c7c  mov     rcx, cs:FastWppRegHandle; RegHandle
0x180003c83  call    cs:__imp_EventUnregister
0x180003c89  mov     [rsp+48h+CallbackContext], 0; CallbackContext
0x180003c92  xor     r9d, r9d; MatchAnyKeyword
0x180003c95  mov     [rsp+48h+FilterData], 0; FilterData
0x180003c9e  xor     r8d, r8d; Level
0x180003ca1  xor     edx, edx; IsEnabled
0x180003ca3  mov     [rsp+48h+MatchAllKeyword], 0; MatchAllKeyword
0x180003cac  xor     ecx, ecx; SourceId
0x180003cae  mov     cs:FastWppRegHandle, 0
0x180003cb9  call    FastWppCallback
0x180003cbe  lea     rcx, FastWppCallbackLock; lpCriticalSection
0x180003cc5  call    cs:__imp_DeleteCriticalSection
0x180003ccb  mov     cs:FastWppInitState, 0
0x180003cd5  add     rsp, 48h
0x180003cd9  retn
```
