# FwGetService

- ea: `0x180001600`
- end: `0x180001628`
- name: `FwGetService`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180001400`

## callees

- `0x180001600`
- `0x18002f43c`

## pseudocode

```c
__int64 *__fastcall FwGetService(int a1)
{
  __int64 v1; // rbx

  v1 = a1;
  if ( (unsigned __int64)a1 >= 3 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  return &qword_180031250[4 * v1];
}

```

## disassembly

```asm
0x180001600  push    rbx
0x180001602  sub     rsp, 20h
0x180001606  movsxd  rbx, ecx
0x180001609  cmp     rbx, 3
0x18000160d  jb      short loc_180001614
0x18000160f  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "svcType < RTL_NUMBER_OF(FW_BUILTIN_SERVICES)")
0x180001614  shl     rbx, 5
0x180001618  lea     rax, qword_180031250
0x18000161f  add     rax, rbx
0x180001622  add     rsp, 20h
0x180001626  pop     rbx
0x180001627  retn
```
