# ISAPI_CONTEXT::TryInitAsyncIo(ASYNC_PENDING)

- ea: `0x180005ff4`
- end: `0x18000603b`
- name: `?TryInitAsyncIo@ISAPI_CONTEXT@@QEAAHW4ASYNC_PENDING@@@Z`
- size: `71`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180004b70`
- `0x180006588`
- `0x180006970`
- `0x180009980`
- `0x18000a1ec`
- `0x18000a820`

## callees

- `0x180005e34`
- `0x180005f90`
- `0x180005ff4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006021`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006021`

## pseudocode

```c
__int64 __fastcall ISAPI_CONTEXT::TryInitAsyncIo(volatile signed __int32 *a1, signed __int32 a2)
{
  ISAPI_CONTEXT::ReferenceIsapiContext((ISAPI_CONTEXT *)a1);
  if ( !_InterlockedCompareExchange(a1 + 54, a2, 0) )
    return 1;
  ISAPI_CONTEXT::DereferenceIsapiContext((ISAPI_CONTEXT *)a1);
  SetLastError(0x57u);
  return 0;
}

```

## disassembly

```asm
0x180005ff4  mov     [rsp+arg_8], rbx
0x180005ff9  push    rdi
0x180005ffa  sub     rsp, 20h
0x180005ffe  mov     ebx, edx
0x180006000  mov     rdi, rcx
0x180006003  call    ?ReferenceIsapiContext@ISAPI_CONTEXT@@QEAAXXZ; ISAPI_CONTEXT::ReferenceIsapiContext(void)
0x180006008  xor     eax, eax
0x18000600a  lock cmpxchg [rdi+0D8h], ebx
0x180006012  jz      short loc_18000602B
0x180006014  mov     rcx, rdi; this
0x180006017  call    ?DereferenceIsapiContext@ISAPI_CONTEXT@@QEAAXXZ; ISAPI_CONTEXT::DereferenceIsapiContext(void)
0x18000601c  mov     ecx, 57h ; 'W'; dwErrCode
0x180006021  call    cs:__imp_SetLastError
0x180006027  xor     eax, eax
0x180006029  jmp     short loc_180006030
0x18000602b  mov     eax, 1
0x180006030  mov     rbx, [rsp+28h+arg_8]
0x180006035  add     rsp, 20h
0x180006039  pop     rdi
0x18000603a  retn
```
