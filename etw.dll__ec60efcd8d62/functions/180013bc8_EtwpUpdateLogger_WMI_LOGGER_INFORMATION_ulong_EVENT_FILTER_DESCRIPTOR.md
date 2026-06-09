# EtwpUpdateLogger(_WMI_LOGGER_INFORMATION *,ulong,_EVENT_FILTER_DESCRIPTOR *)

- ea: `0x180013bc8`
- end: `0x180013c2a`
- name: `?EtwpUpdateLogger@@YAKPEAU_WMI_LOGGER_INFORMATION@@KPEAU_EVENT_FILTER_DESCRIPTOR@@@Z`
- size: `98`
- prototype: `unsigned int __fastcall(struct _WMI_LOGGER_INFORMATION *, unsigned int, struct _EVENT_FILTER_DESCRIPTOR *)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1800099c0`
- `0x18000a300`

## callees

- `0x180001eca`
- `0x180001ee2`
- `0x18001356c`
- `0x180013bc8`

## pseudocode

```c
NTSTATUS __fastcall EtwpUpdateLogger(
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
    return EtwpSendUmLogRequest(4, (__int64)a1, a2, (__int64)a3);
  result = NtTraceControl_0(4, a1, *(unsigned int *)a1, a1, *(_DWORD *)a1, &v5);
  if ( result )
    return RtlNtStatusToDosError_0(result);
  return result;
}

```

## disassembly

```asm
0x180013bc8  sub     rsp, 38h
0x180013bcc  test    dword ptr [rcx+40h], 800h
0x180013bd3  mov     [rsp+38h+arg_0], 0
0x180013bdb  jnz     short loc_180013C12
0x180013bdd  test    byte ptr [rcx+0Bh], 1
0x180013be1  jnz     short loc_180013C12
0x180013be3  mov     r8d, [rcx]
0x180013be6  lea     rax, [rsp+38h+arg_0]
0x180013beb  mov     r9, rcx
0x180013bee  mov     [rsp+38h+var_10], rax
0x180013bf3  mov     rdx, rcx
0x180013bf6  mov     [rsp+38h+var_18], r8d
0x180013bfb  mov     ecx, 4
0x180013c00  call    NtTraceControl_0
0x180013c05  test    eax, eax
0x180013c07  jz      short loc_180013C25
0x180013c09  mov     ecx, eax; Status
0x180013c0b  call    RtlNtStatusToDosError_0
0x180013c10  jmp     short loc_180013C25
0x180013c12  mov     r9, r8
0x180013c15  mov     r8d, edx
0x180013c18  mov     rdx, rcx
0x180013c1b  mov     ecx, 4
0x180013c20  call    ?EtwpSendUmLogRequest@@YAKW4ETWTRACECONTROLCODE@@PEAU_WMI_LOGGER_INFORMATION@@KPEAU_EVENT_FILTER_DESCRIPTOR@@@Z; EtwpSendUmLogRequest(ETWTRACECONTROLCODE,_WMI_LOGGER_INFORMATION *,ulong,_EVENT_FILTER_DESCRIPTOR *)
0x180013c25  add     rsp, 38h
0x180013c29  retn
```
