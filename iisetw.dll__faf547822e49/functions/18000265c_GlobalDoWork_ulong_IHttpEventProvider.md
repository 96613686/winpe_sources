# GlobalDoWork(ulong,IHttpEventProvider *)

- ea: `0x18000265c`
- end: `0x1800026b5`
- name: `?GlobalDoWork@@YA?AW4GLOBAL_NOTIFICATION_STATUS@@KPEAVIHttpEventProvider@@@Z`
- size: `89`
- prototype: `__int64 __fastcall(int, struct IGlobalTraceEventProvider *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002fd0`

## callees

- `0x180002238`
- `0x18000265c`
- `0x1800026bc`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall GlobalDoWork(int a1, struct IGlobalTraceEventProvider *a2)
{
  unsigned int *v3; // rdx
  unsigned int *v4; // r8
  const unsigned __int16 *v5; // rax

  if ( a1 == 64 )
  {
    v5 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(struct IGlobalTraceEventProvider *))(*(_QWORD *)a2 + 8LL))(a2);
    ETW_TRACE_HANDLER::DeleteTraceUrlList(v5);
  }
  else if ( a1 == 0x2000
         && (*(unsigned int (__fastcall **)(struct IGlobalTraceEventProvider *, void *))(*(_QWORD *)a2 + 16LL))(
              a2,
              s_pModuleContext) )
  {
    ETW_TRACE_HANDLER::HandleRaisedEvent(a2, v3, v4);
  }
  return 0;
}

```

## disassembly

```asm
0x18000265c  push    rbx
0x18000265e  sub     rsp, 20h
0x180002662  mov     rbx, rdx
0x180002665  cmp     ecx, 40h ; '@'
0x180002668  jz      short loc_180002696
0x18000266a  cmp     ecx, 2000h
0x180002670  jnz     short loc_1800026AD
0x180002672  mov     rax, [rdx]
0x180002675  mov     rcx, rbx
0x180002678  mov     rdx, cs:?s_pModuleContext@@3PEAXEA; void * s_pModuleContext
0x18000267f  mov     rax, [rax+10h]
0x180002683  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002688  test    eax, eax
0x18000268a  jz      short loc_1800026AD
0x18000268c  mov     rcx, rbx; struct IGlobalTraceEventProvider *
0x18000268f  call    ?HandleRaisedEvent@ETW_TRACE_HANDLER@@SAJPEAVIGlobalTraceEventProvider@@PEAK1@Z; ETW_TRACE_HANDLER::HandleRaisedEvent(IGlobalTraceEventProvider *,ulong *,ulong *)
0x180002694  jmp     short loc_1800026AD
0x180002696  mov     rax, [rdx]
0x180002699  mov     rcx, rbx
0x18000269c  mov     rax, [rax+8]
0x1800026a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026a5  mov     rcx, rax; unsigned __int16 *
0x1800026a8  call    ?DeleteTraceUrlList@ETW_TRACE_HANDLER@@SAJPEBG@Z; ETW_TRACE_HANDLER::DeleteTraceUrlList(ushort const *)
0x1800026ad  xor     eax, eax
0x1800026af  add     rsp, 20h
0x1800026b3  pop     rbx
0x1800026b4  retn
```
