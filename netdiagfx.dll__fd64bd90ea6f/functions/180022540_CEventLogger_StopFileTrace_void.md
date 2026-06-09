# CEventLogger::StopFileTrace(void)

- ea: `0x180022540`
- end: `0x18002259a`
- name: `?StopFileTrace@CEventLogger@@UEAAJXZ`
- size: `90`
- prototype: `__int64 __fastcall(CEventLogger *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800221a4`
- `0x180022540`

## import_xrefs

- `ADVAPI32!StopTraceW` at `0x18002256f`
- `ADVAPI32!StopTraceW` at `0x18002256f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002257a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002257a`

## pseudocode

```c
__int64 __fastcall CEventLogger::StopFileTrace(CEventLogger *this)
{
  struct _EVENT_TRACE_PROPERTIES *v2; // rax
  struct _EVENT_TRACE_PROPERTIES *v3; // rdi
  signed int v5; // ebx

  v2 = AllocProperties();
  v3 = v2;
  if ( !v2 )
    return 2147942414LL;
  v5 = StopTraceW(*((_QWORD *)this + 1), *((LPCWSTR *)this + 67), v2);
  CoTaskMemFree(v3);
  if ( v5 > 0 )
    return (unsigned __int16)v5 | 0x80070000;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180022540  mov     [rsp+arg_0], rbx
0x180022545  push    rdi
0x180022546  sub     rsp, 20h
0x18002254a  mov     rbx, rcx
0x18002254d  call    ?AllocProperties@@YAPEAU_EVENT_TRACE_PROPERTIES@@XZ; AllocProperties(void)
0x180022552  mov     rdi, rax
0x180022555  test    rax, rax
0x180022558  jnz     short loc_180022561
0x18002255a  mov     eax, 8007000Eh
0x18002255f  jmp     short loc_18002258F
0x180022561  mov     rdx, [rbx+218h]; InstanceName
0x180022568  mov     r8, rdi; Properties
0x18002256b  mov     rcx, [rbx+8]; TraceHandle
0x18002256f  call    cs:__imp_StopTraceW
0x180022575  mov     rcx, rdi; pv
0x180022578  mov     ebx, eax
0x18002257a  call    cs:__imp_CoTaskMemFree
0x180022580  test    ebx, ebx
0x180022582  jle     short loc_18002258D
0x180022584  movzx   ebx, bx
0x180022587  or      ebx, 80070000h
0x18002258d  mov     eax, ebx
0x18002258f  mov     rbx, [rsp+28h+arg_0]
0x180022594  add     rsp, 20h
0x180022598  pop     rdi
0x180022599  retn
```
