# EtwpQueryLogger(_WMI_LOGGER_INFORMATION *,ulong,_EVENT_FILTER_DESCRIPTOR *)

- ea: `0x180013504`
- end: `0x180013566`
- name: `?EtwpQueryLogger@@YAKPEAU_WMI_LOGGER_INFORMATION@@KPEAU_EVENT_FILTER_DESCRIPTOR@@@Z`
- size: `98`
- prototype: `unsigned int __fastcall(struct _WMI_LOGGER_INFORMATION *, unsigned int, struct _EVENT_FILTER_DESCRIPTOR *)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x1800099c0`
- `0x18000a300`
- `0x180013284`
- `0x1800138d0`

## callees

- `0x180001eca`
- `0x180001ee2`
- `0x180013504`
- `0x18001356c`

## pseudocode

```c
NTSTATUS __fastcall EtwpQueryLogger(
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
    return EtwpSendUmLogRequest(3, (__int64)a1, a2, (__int64)a3);
  result = NtTraceControl_0(3, a1, *(unsigned int *)a1, a1, *(_DWORD *)a1, &v5);
  if ( result )
    return RtlNtStatusToDosError_0(result);
  return result;
}

```

## disassembly

```asm
0x180013504  sub     rsp, 38h
0x180013508  test    dword ptr [rcx+40h], 800h
0x18001350f  mov     [rsp+38h+arg_0], 0
0x180013517  jnz     short loc_18001354E
0x180013519  test    byte ptr [rcx+0Bh], 1
0x18001351d  jnz     short loc_18001354E
0x18001351f  mov     r8d, [rcx]
0x180013522  lea     rax, [rsp+38h+arg_0]
0x180013527  mov     r9, rcx
0x18001352a  mov     [rsp+38h+var_10], rax
0x18001352f  mov     rdx, rcx
0x180013532  mov     [rsp+38h+var_18], r8d
0x180013537  mov     ecx, 3
0x18001353c  call    NtTraceControl_0
0x180013541  test    eax, eax
0x180013543  jz      short loc_180013561
0x180013545  mov     ecx, eax; Status
0x180013547  call    RtlNtStatusToDosError_0
0x18001354c  jmp     short loc_180013561
0x18001354e  mov     r9, r8
0x180013551  mov     r8d, edx
0x180013554  mov     rdx, rcx
0x180013557  mov     ecx, 3
0x18001355c  call    ?EtwpSendUmLogRequest@@YAKW4ETWTRACECONTROLCODE@@PEAU_WMI_LOGGER_INFORMATION@@KPEAU_EVENT_FILTER_DESCRIPTOR@@@Z; EtwpSendUmLogRequest(ETWTRACECONTROLCODE,_WMI_LOGGER_INFORMATION *,ulong,_EVENT_FILTER_DESCRIPTOR *)
0x180013561  add     rsp, 38h
0x180013565  retn
```
