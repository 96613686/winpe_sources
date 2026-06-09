# __GSHandlerCheck_SEH

- ea: `0x180002d0c`
- end: `0x180002d74`
- name: `__GSHandlerCheck_SEH`
- size: `104`
- prototype: `__int64 __fastcall(struct _EXCEPTION_RECORD *ExceptionRecord, void *EstablisherFrame, struct _CONTEXT *ContextRecord, struct _DISPATCHER_CONTEXT *DispatcherContext)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180002ca0`
- `0x180002d0c`

## import_xrefs

- `msvcrt!__C_specific_handler` at `0x180002d63`
- `msvcrt!__C_specific_handler` at `0x180002d63`

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
0x180002d0c  push    rbx
0x180002d0e  push    rbp
0x180002d0f  push    rsi
0x180002d10  push    rdi
0x180002d11  push    r14
0x180002d13  sub     rsp, 20h
0x180002d17  mov     r10, [r9+38h]
0x180002d1b  mov     rsi, rdx
0x180002d1e  mov     r14, r8
0x180002d21  mov     rbp, rcx
0x180002d24  mov     rdx, r9
0x180002d27  mov     rcx, rsi
0x180002d2a  mov     rdi, r9
0x180002d2d  mov     ebx, [r10]
0x180002d30  shl     rbx, 4
0x180002d34  add     rbx, r10
0x180002d37  lea     r8, [rbx+4]
0x180002d3b  call    __GSHandlerCheckCommon
0x180002d40  mov     eax, [rbp+4]
0x180002d43  and     al, 66h
0x180002d45  neg     al
0x180002d47  mov     eax, 1
0x180002d4c  sbb     edx, edx
0x180002d4e  neg     edx
0x180002d50  add     edx, eax
0x180002d52  test    [rbx+4], edx
0x180002d55  jz      short loc_180002D69
0x180002d57  mov     r9, rdi; DispatcherContext
0x180002d5a  mov     r8, r14; ContextRecord
0x180002d5d  mov     rdx, rsi; EstablisherFrame
0x180002d60  mov     rcx, rbp; ExceptionRecord
0x180002d63  call    cs:__imp___C_specific_handler
0x180002d69  add     rsp, 20h
0x180002d6d  pop     r14
0x180002d6f  pop     rdi
0x180002d70  pop     rsi
0x180002d71  pop     rbp
0x180002d72  pop     rbx
0x180002d73  retn
```
