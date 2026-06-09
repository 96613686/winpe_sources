# EfsTriggerServiceStart

- ea: `0x14004e16c`
- end: `0x14004e1da`
- name: `EfsTriggerServiceStart`
- size: `110`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, installer_update`

## callers

- `0x14004e230`
- `0x1400501d0`
- `0x140053420`
- `0x140053460`

## callees

- `0x14004e16c`

## import_xrefs

- `ntoskrnl!ZwWaitForSingleObject` at `0x14004e190`
- `ntoskrnl!ZwWaitForSingleObject` at `0x14004e190`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x14004e1c8`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x14004e1c8`

## pseudocode

```c
NTSTATUS EfsTriggerServiceStart()
{
  NTSTATUS result; // eax
  union _LARGE_INTEGER Timeout; // [rsp+50h] [rbp+8h] BYREF

  Timeout.QuadPart = 0;
  if ( byte_140017924 != 1 )
    return ZwUpdateWnfStateData(&WNF_EFS_SERVICE_START, 0, 0, 0, 0, 0, 0);
  result = ZwWaitForSingleObject(Handle, 0, &Timeout);
  if ( result )
    return ZwUpdateWnfStateData(&WNF_EFS_SERVICE_START, 0, 0, 0, 0, 0, 0);
  return result;
}

```

## disassembly

```asm
0x14004e16c  sub     rsp, 48h
0x14004e170  cmp     cs:byte_140017924, 1
0x14004e177  mov     qword ptr [rsp+48h+Timeout], 0
0x14004e180  jnz     short loc_14004E1A0
0x14004e182  mov     rcx, cs:Handle; Handle
0x14004e189  lea     r8, [rsp+48h+Timeout]; Timeout
0x14004e18e  xor     edx, edx; Alertable
0x14004e190  call    cs:__imp_ZwWaitForSingleObject
0x14004e197  nop     dword ptr [rax+rax+00h]
0x14004e19c  test    eax, eax
0x14004e19e  jz      short loc_14004E1D4
0x14004e1a0  mov     [rsp+48h+var_18], 0
0x14004e1a8  lea     rcx, WNF_EFS_SERVICE_START
0x14004e1af  mov     [rsp+48h+var_20], 0
0x14004e1b7  xor     r9d, r9d
0x14004e1ba  xor     r8d, r8d
0x14004e1bd  mov     [rsp+48h+var_28], 0
0x14004e1c6  xor     edx, edx
0x14004e1c8  call    cs:__imp_ZwUpdateWnfStateData
0x14004e1cf  nop     dword ptr [rax+rax+00h]
0x14004e1d4  add     rsp, 48h
0x14004e1d8  retn
```
