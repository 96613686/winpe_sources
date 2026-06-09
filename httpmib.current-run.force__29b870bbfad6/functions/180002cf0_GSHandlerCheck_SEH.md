# __GSHandlerCheck_SEH

- ea: `0x180002cf0`
- end: `0x180002d58`
- name: `__GSHandlerCheck_SEH`
- size: `104`
- prototype: `__int64 __fastcall(struct _EXCEPTION_RECORD *ExceptionRecord, void *EstablisherFrame, struct _CONTEXT *ContextRecord, struct _DISPATCHER_CONTEXT *DispatcherContext)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180002c84`
- `0x180002cf0`

## import_xrefs

- `msvcrt!__C_specific_handler` at `0x180002d47`
- `msvcrt!__C_specific_handler` at `0x180002d47`

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
    return __C_specific_handler(ExceptionRecord, EstablisherFrame, ContextRecord, DispatcherContext);
  return result;
}

```

## disassembly

```asm
0x180002cf0  push    rbx
0x180002cf2  push    rbp
0x180002cf3  push    rsi
0x180002cf4  push    rdi
0x180002cf5  push    r14
0x180002cf7  sub     rsp, 20h
0x180002cfb  mov     r10, [r9+38h]
0x180002cff  mov     rsi, rdx
0x180002d02  mov     r14, r8
0x180002d05  mov     rbp, rcx
0x180002d08  mov     rdx, r9
0x180002d0b  mov     rcx, rsi
0x180002d0e  mov     rdi, r9
0x180002d11  mov     ebx, [r10]
0x180002d14  shl     rbx, 4
0x180002d18  add     rbx, r10
0x180002d1b  lea     r8, [rbx+4]
0x180002d1f  call    __GSHandlerCheckCommon
0x180002d24  mov     eax, [rbp+4]
0x180002d27  and     al, 66h
0x180002d29  neg     al
0x180002d2b  mov     eax, 1
0x180002d30  sbb     edx, edx
0x180002d32  neg     edx
0x180002d34  add     edx, eax
0x180002d36  test    [rbx+4], edx
0x180002d39  jz      short loc_180002D4D
0x180002d3b  mov     r9, rdi; DispatcherContext
0x180002d3e  mov     r8, r14; ContextRecord
0x180002d41  mov     rdx, rsi; EstablisherFrame
0x180002d44  mov     rcx, rbp; ExceptionRecord
0x180002d47  call    cs:__imp___C_specific_handler
0x180002d4d  add     rsp, 20h
0x180002d51  pop     r14
0x180002d53  pop     rdi
0x180002d54  pop     rsi
0x180002d55  pop     rbp
0x180002d56  pop     rbx
0x180002d57  retn
```
