# __GSHandlerCheck_SEH

- ea: `0x1400033e4`
- end: `0x14000344c`
- name: `__GSHandlerCheck_SEH`
- size: `104`
- prototype: `__int64 __fastcall(struct _EXCEPTION_RECORD *ExceptionRecord, void *EstablisherFrame, struct _CONTEXT *ContextRecord, struct _DISPATCHER_CONTEXT *DispatcherContext)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x14000101d`
- `0x14000336c`
- `0x1400033e4`

## pseudocode

```c
EXCEPTION_DISPOSITION __fastcall _GSHandlerCheck_SEH(
        struct _EXCEPTION_RECORD *ExceptionRecord,
        void *EstablisherFrame,
        struct _CONTEXT *ContextRecord,
        struct _DISPATCHER_CONTEXT *DispatcherContext)
{
  char *v8; // rbx
  EXCEPTION_DISPOSITION result; // eax

  v8 = (char *)DispatcherContext->HandlerData + 16 * *(unsigned int *)DispatcherContext->HandlerData;
  _GSHandlerCheckCommon((__int64)EstablisherFrame, (__int64)DispatcherContext);
  result = ExceptionContinueSearch;
  if ( ((((ExceptionRecord->ExceptionFlags & 0x66) != 0) + 1) & *((_DWORD *)v8 + 1)) != 0 )
    return _C_specific_handler_0(ExceptionRecord, EstablisherFrame, ContextRecord, DispatcherContext);
  return result;
}

```

## disassembly

```asm
0x1400033e4  push    rbx
0x1400033e6  push    rbp
0x1400033e7  push    rsi
0x1400033e8  push    rdi
0x1400033e9  push    r14
0x1400033eb  sub     rsp, 20h
0x1400033ef  mov     r10, [r9+38h]
0x1400033f3  mov     rsi, rdx
0x1400033f6  mov     r14, r8
0x1400033f9  mov     rbp, rcx
0x1400033fc  mov     rdx, r9
0x1400033ff  mov     rcx, rsi
0x140003402  mov     rdi, r9
0x140003405  mov     ebx, [r10]
0x140003408  shl     rbx, 4
0x14000340c  add     rbx, r10
0x14000340f  lea     r8, [rbx+4]
0x140003413  call    __GSHandlerCheckCommon
0x140003418  mov     eax, [rbp+4]
0x14000341b  and     al, 66h
0x14000341d  neg     al
0x14000341f  mov     eax, 1
0x140003424  sbb     edx, edx
0x140003426  neg     edx
0x140003428  add     edx, eax
0x14000342a  test    [rbx+4], edx
0x14000342d  jz      short loc_140003440
0x14000342f  mov     r9, rdi; DispatcherContext
0x140003432  mov     r8, r14; ContextRecord
0x140003435  mov     rdx, rsi; EstablisherFrame
0x140003438  mov     rcx, rbp; ExceptionRecord
0x14000343b  call    __C_specific_handler_0
0x140003440  add     rsp, 20h
0x140003444  pop     r14
0x140003446  pop     rdi
0x140003447  pop     rsi
0x140003448  pop     rbp
0x140003449  pop     rbx
0x14000344a  retn
```
