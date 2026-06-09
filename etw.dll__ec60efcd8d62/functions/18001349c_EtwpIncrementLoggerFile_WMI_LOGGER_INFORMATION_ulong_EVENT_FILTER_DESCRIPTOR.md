# EtwpIncrementLoggerFile(_WMI_LOGGER_INFORMATION *,ulong,_EVENT_FILTER_DESCRIPTOR *)

- ea: `0x18001349c`
- end: `0x1800134fe`
- name: `?EtwpIncrementLoggerFile@@YAKPEAU_WMI_LOGGER_INFORMATION@@KPEAU_EVENT_FILTER_DESCRIPTOR@@@Z`
- size: `98`
- prototype: `unsigned int __fastcall(struct _WMI_LOGGER_INFORMATION *, unsigned int, struct _EVENT_FILTER_DESCRIPTOR *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800099c0`
- `0x18000a300`

## callees

- `0x180001eca`
- `0x180001ee2`
- `0x18001349c`
- `0x18001356c`

## pseudocode

```c
NTSTATUS __fastcall EtwpIncrementLoggerFile(
        struct _WMI_LOGGER_INFORMATION *a1,
        unsigned int a2,
        struct _EVENT_FILTER_DESCRIPTOR *a3)
{
  bool v3; // zf
  NTSTATUS result; // eax
  int v5; // [rsp+40h] [rbp+8h] BYREF

  v3 = (*((_DWORD *)a1 + 16) & 0x800) == 0;
  v5 = 0;
  if ( !v3 || (*((_BYTE *)a1 + 11) & 1) != 0 )
    return EtwpSendUmLogRequest(6, (__int64)a1, a2, (__int64)a3);
  result = NtTraceControl_0(6, a1, *(unsigned int *)a1, a1, *(_DWORD *)a1, &v5);
  if ( result )
    return RtlNtStatusToDosError_0(result);
  return result;
}

```

## disassembly

```asm
0x18001349c  sub     rsp, 38h
0x1800134a0  test    dword ptr [rcx+40h], 800h
0x1800134a7  mov     [rsp+38h+arg_0], 0
0x1800134af  jnz     short loc_1800134E6
0x1800134b1  test    byte ptr [rcx+0Bh], 1
0x1800134b5  jnz     short loc_1800134E6
0x1800134b7  mov     r8d, [rcx]
0x1800134ba  lea     rax, [rsp+38h+arg_0]
0x1800134bf  mov     r9, rcx
0x1800134c2  mov     [rsp+38h+var_10], rax
0x1800134c7  mov     rdx, rcx
0x1800134ca  mov     [rsp+38h+var_18], r8d
0x1800134cf  mov     ecx, 6
0x1800134d4  call    NtTraceControl_0
0x1800134d9  test    eax, eax
0x1800134db  jz      short loc_1800134F9
0x1800134dd  mov     ecx, eax; Status
0x1800134df  call    RtlNtStatusToDosError_0
0x1800134e4  jmp     short loc_1800134F9
0x1800134e6  mov     r9, r8
0x1800134e9  mov     r8d, edx
0x1800134ec  mov     rdx, rcx
0x1800134ef  mov     ecx, 6
0x1800134f4  call    ?EtwpSendUmLogRequest@@YAKW4ETWTRACECONTROLCODE@@PEAU_WMI_LOGGER_INFORMATION@@KPEAU_EVENT_FILTER_DESCRIPTOR@@@Z; EtwpSendUmLogRequest(ETWTRACECONTROLCODE,_WMI_LOGGER_INFORMATION *,ulong,_EVENT_FILTER_DESCRIPTOR *)
0x1800134f9  add     rsp, 38h
0x1800134fd  retn
```
