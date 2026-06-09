# NcsiSuspectStateMonitor::Uninitialize(void)

- ea: `0x1800430bc`
- end: `0x1800430e0`
- name: `?Uninitialize@NcsiSuspectStateMonitor@@QEAAXXZ`
- size: `36`
- prototype: `void __fastcall(NcsiSuspectStateMonitor *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180050300`
- `0x18007b980`

## callees

- `0x1800430bc`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800430cd`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800430cd`

## pseudocode

```c
void __fastcall NcsiSuspectStateMonitor::Uninitialize(NcsiSuspectStateMonitor *this)
{
  __int64 v2; // rcx

  v2 = *(_QWORD *)this;
  if ( v2 )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion(v2);
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x1800430bc  push    rbx
0x1800430be  sub     rsp, 20h
0x1800430c2  mov     rbx, rcx
0x1800430c5  mov     rcx, [rcx]
0x1800430c8  test    rcx, rcx
0x1800430cb  jz      short loc_1800430DA
0x1800430cd  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x1800430d3  mov     qword ptr [rbx], 0
0x1800430da  add     rsp, 20h
0x1800430de  pop     rbx
0x1800430df  retn
```
