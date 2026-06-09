# PmSetPartitionInformationEx(_PARTITION_EXTENSION *,_SET_PARTITION_INFORMATION_EX *)

- ea: `0x140020ba8`
- end: `0x140020c3a`
- name: `?PmSetPartitionInformationEx@@YAJPEAU_PARTITION_EXTENSION@@PEAU_SET_PARTITION_INFORMATION_EX@@@Z`
- size: `146`
- prototype: `__int64 __fastcall(struct _PARTITION_EXTENSION *, struct _SET_PARTITION_INFORMATION_EX *)`
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14001d370`
- `0x14001d538`
- `0x14001d604`

## callees

- `0x140007bcc`
- `0x14000ae88`
- `0x14000c238`
- `0x14000cb34`
- `0x14001cff4`
- `0x140020ba8`

## pseudocode

```c
int __fastcall PmSetPartitionInformationEx(struct _PARTITION_EXTENSION *a1, struct _SET_PARTITION_INFORMATION_EX *a2)
{
  __int64 v2; // rbx
  __int64 v3; // rdx
  __int64 v4; // rcx
  struct _SET_PARTITION_INFORMATION_EX *v5; // r8
  int result; // eax

  v2 = *((_QWORD *)a1 + 3);
  if ( (ScReadNoFence((unsigned int *)a1 + 10) & 4) != 0 )
    return -1073741810;
  if ( *(_BYTE *)(v2 + 604) && *(_BYTE *)(v3 + 197) )
  {
    if ( (Microsoft_Windows_PartitionEnableBits & 1) != 0 )
      McTemplateK0qq_EtwWriteTransfer(
        v4,
        ServiceSetPartitionError,
        0,
        *(unsigned int *)(v2 + 168),
        *(_DWORD *)(v3 + 192));
    return -1073741790;
  }
  else
  {
    result = PmSetPartition(*(struct _DEVICE_OBJECT **)(v2 + 8), *(_DWORD *)(v3 + 160), v5);
    if ( result >= 0 )
    {
      PmInvalidatePartitionTableCache((KSPIN_LOCK *)v2);
      return PmGetDriveLayoutEx((KSPIN_LOCK *)v2, 0);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140020ba8  push    rbx
0x140020baa  sub     rsp, 30h
0x140020bae  mov     rbx, [rcx+18h]
0x140020bb2  mov     r8, rdx
0x140020bb5  mov     rdx, rcx
0x140020bb8  add     rcx, 28h ; '('; unsigned int *
0x140020bbc  call    ?ScReadNoFence@@YAKPEAK@Z; ScReadNoFence(ulong *)
0x140020bc1  test    al, 4
0x140020bc3  jz      short loc_140020BCC
0x140020bc5  mov     eax, 0C000000Eh
0x140020bca  jmp     short loc_140020C33
0x140020bcc  cmp     byte ptr [rbx+25Ch], 0
0x140020bd3  jz      short loc_140020C0E
0x140020bd5  cmp     byte ptr [rdx+0C5h], 0
0x140020bdc  jz      short loc_140020C0E
0x140020bde  test    cs:Microsoft_Windows_PartitionEnableBits, 1
0x140020be5  jz      short loc_140020C07
0x140020be7  mov     eax, [rdx+0C0h]
0x140020bed  xor     r8d, r8d
0x140020bf0  mov     r9d, [rbx+0A8h]
0x140020bf7  lea     rdx, ServiceSetPartitionError
0x140020bfe  mov     [rsp+38h+var_18], eax
0x140020c02  call    McTemplateK0qq_EtwWriteTransfer
0x140020c07  mov     eax, 0C0000022h
0x140020c0c  jmp     short loc_140020C33
0x140020c0e  mov     edx, [rdx+0A0h]; unsigned int
0x140020c14  mov     rcx, [rbx+8]; struct _DEVICE_OBJECT *
0x140020c18  call    ?PmSetPartition@@YAJPEAU_DEVICE_OBJECT@@KPEAU_SET_PARTITION_INFORMATION_EX@@@Z; PmSetPartition(_DEVICE_OBJECT *,ulong,_SET_PARTITION_INFORMATION_EX *)
0x140020c1d  test    eax, eax
0x140020c1f  js      short loc_140020C33
0x140020c21  mov     rcx, rbx; struct _DEVICE_EXTENSION *
0x140020c24  call    ?PmInvalidatePartitionTableCache@@YAXPEAU_DEVICE_EXTENSION@@@Z; PmInvalidatePartitionTableCache(_DEVICE_EXTENSION *)
0x140020c29  xor     edx, edx; struct _DRIVE_LAYOUT_INFORMATION_EX **
0x140020c2b  mov     rcx, rbx; struct _DEVICE_EXTENSION *
0x140020c2e  call    ?PmGetDriveLayoutEx@@YAJPEAU_DEVICE_EXTENSION@@PEAPEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; PmGetDriveLayoutEx(_DEVICE_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX * *)
0x140020c33  add     rsp, 30h
0x140020c37  pop     rbx
0x140020c38  retn
```
