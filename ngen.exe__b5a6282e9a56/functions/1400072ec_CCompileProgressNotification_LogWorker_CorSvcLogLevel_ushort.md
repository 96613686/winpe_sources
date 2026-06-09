# CCompileProgressNotification::LogWorker(CorSvcLogLevel,ushort *,...)

- ea: `0x1400072ec`
- end: `0x140007335`
- name: `?LogWorker@CCompileProgressNotification@@AEAAXW4CorSvcLogLevel@@PEAGZZ`
- size: `73`
- prototype: `void(__int64, int, unsigned __int16 *, ...)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140007100`
- `0x140007240`
- `0x140007388`
- `0x1400081f8`

## callees

- `0x1400068ec`
- `0x140006ee4`
- `0x1400072ec`

## pseudocode

```c
void CCompileProgressNotification::LogWorker(__int64 a1, int a2, unsigned __int16 *a3, ...)
{
  va_list va; // [rsp+58h] [rbp+20h] BYREF

  va_start(va, a3);
  if ( a2 <= *(_DWORD *)(a1 + 24) )
  {
    Outputv(a3, va);
    if ( *(_DWORD *)(a1 + 40) )
      MachineWideLogger::LogV((MachineWideLogger *)&g_MachineWideLogger, a3, va);
  }
}

```

## disassembly

```asm
0x1400072ec  mov     [rsp+arg_10], r8
0x1400072f1  mov     qword ptr [rsp+arg_18], r9
0x1400072f6  push    rbx
0x1400072f7  push    rdi
0x1400072f8  sub     rsp, 28h
0x1400072fc  lea     rdi, [rsp+38h+arg_18]
0x140007301  mov     rbx, rcx
0x140007304  cmp     edx, [rcx+18h]
0x140007307  jg      short loc_14000732E
0x140007309  mov     rdx, rdi; char *
0x14000730c  mov     rcx, r8; unsigned __int16 *
0x14000730f  call    ?Outputv@@YAXPEAGPEAD@Z; Outputv(ushort *,char *)
0x140007314  cmp     dword ptr [rbx+28h], 0
0x140007318  jz      short loc_14000732E
0x14000731a  mov     rdx, [rsp+38h+arg_10]; unsigned __int16 *
0x14000731f  lea     rcx, ?g_MachineWideLogger@@3VMachineWideLogger@@A; this
0x140007326  mov     r8, rdi; char *
0x140007329  call    ?LogV@MachineWideLogger@@QEAAXPEBGPEAD@Z; MachineWideLogger::LogV(ushort const *,char *)
0x14000732e  add     rsp, 28h
0x140007332  pop     rdi
0x140007333  pop     rbx
0x140007334  retn
```
