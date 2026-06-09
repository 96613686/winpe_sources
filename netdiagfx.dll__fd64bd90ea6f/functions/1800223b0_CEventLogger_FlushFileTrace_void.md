# CEventLogger::FlushFileTrace(void)

- ea: `0x1800223b0`
- end: `0x18002240e`
- name: `?FlushFileTrace@CEventLogger@@EEAAJXZ`
- size: `94`
- prototype: `__int64 __fastcall(LPCWSTR *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800221a4`
- `0x1800223b0`

## import_xrefs

- `ADVAPI32!ControlTraceW` at `0x1800223e3`
- `ADVAPI32!ControlTraceW` at `0x1800223e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800223ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800223ee`

## pseudocode

```c
__int64 __fastcall CEventLogger::FlushFileTrace(LPCWSTR *this)
{
  struct _EVENT_TRACE_PROPERTIES *v2; // rax
  struct _EVENT_TRACE_PROPERTIES *v3; // rdi
  signed int v5; // ebx

  v2 = AllocProperties();
  v3 = v2;
  if ( !v2 )
    return 2147942414LL;
  v5 = ControlTraceW(0, this[67], v2, 3u);
  CoTaskMemFree(v3);
  if ( v5 > 0 )
    return (unsigned __int16)v5 | 0x80070000;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800223b0  mov     [rsp+arg_0], rbx
0x1800223b5  push    rdi
0x1800223b6  sub     rsp, 20h
0x1800223ba  mov     rbx, rcx
0x1800223bd  call    ?AllocProperties@@YAPEAU_EVENT_TRACE_PROPERTIES@@XZ; AllocProperties(void)
0x1800223c2  mov     rdi, rax
0x1800223c5  test    rax, rax
0x1800223c8  jnz     short loc_1800223D1
0x1800223ca  mov     eax, 8007000Eh
0x1800223cf  jmp     short loc_180022403
0x1800223d1  mov     rdx, [rbx+218h]; InstanceName
0x1800223d8  mov     r9d, 3; ControlCode
0x1800223de  mov     r8, rdi; Properties
0x1800223e1  xor     ecx, ecx; TraceHandle
0x1800223e3  call    cs:__imp_ControlTraceW
0x1800223e9  mov     rcx, rdi; pv
0x1800223ec  mov     ebx, eax
0x1800223ee  call    cs:__imp_CoTaskMemFree
0x1800223f4  test    ebx, ebx
0x1800223f6  jle     short loc_180022401
0x1800223f8  movzx   ebx, bx
0x1800223fb  or      ebx, 80070000h
0x180022401  mov     eax, ebx
0x180022403  mov     rbx, [rsp+28h+arg_0]
0x180022408  add     rsp, 20h
0x18002240c  pop     rdi
0x18002240d  retn
```
