# PmSetDriveLayoutEx(_DEVICE_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX *)

- ea: `0x140020afc`
- end: `0x140020ba0`
- name: `?PmSetDriveLayoutEx@@YAJPEAU_DEVICE_EXTENSION@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z`
- size: `164`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *, struct _DRIVE_LAYOUT_INFORMATION_EX *)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x14001f120`
- `0x14001f304`

## callees

- `0x140007bcc`
- `0x14000cb34`
- `0x14001d090`
- `0x140020778`
- `0x1400208c8`
- `0x140020afc`

## pseudocode

```c
__int64 __fastcall PmSetDriveLayoutEx(struct _DEVICE_EXTENSION *a1, struct _DRIVE_LAYOUT_INFORMATION_EX *a2)
{
  __int64 result; // rax
  PARTITION_STYLE PartitionStyle; // ecx
  __int64 v6; // xmm0_8
  struct _CREATE_DISK v7; // [rsp+20h] [rbp-28h] BYREF

  result = PmCheckCriticalPartitions(a1, (struct SC_DISK_LAYOUT *)a2);
  if ( (int)result >= 0 )
  {
    if ( a2->PartitionCount )
    {
      result = PmWritePartitionTable(*((struct _DEVICE_OBJECT **)a1 + 1), a2);
      if ( (int)result >= 0 )
      {
        PmInvalidatePartitionTableCache((KSPIN_LOCK *)a1);
        return PmGetDriveLayoutEx((KSPIN_LOCK *)a1, 0);
      }
    }
    else
    {
      PartitionStyle = a2->PartitionStyle;
      memset(&v7, 0, sizeof(v7));
      v7.PartitionStyle = PartitionStyle;
      if ( PartitionStyle )
      {
        if ( PartitionStyle == PARTITION_STYLE_GPT )
        {
          v6 = *(_QWORD *)&a2->Gpt.DiskId.Data2;
          v7.Mbr.Signature = a2->Mbr.Signature;
          *(_QWORD *)&v7.Gpt.DiskId.Data4[4] = *(unsigned int *)&a2->Gpt.DiskId.Data4[4];
          *(_QWORD *)&v7.Gpt.DiskId.Data2 = v6;
        }
      }
      else
      {
        v7.Mbr.Signature = a2->Mbr.Signature;
      }
      return PmCreateDisk(a1, &v7);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140020afc  mov     [rsp+arg_0], rbx
0x140020b01  push    rdi
0x140020b02  sub     rsp, 40h
0x140020b06  mov     rbx, rdx
0x140020b09  mov     rdi, rcx
0x140020b0c  call    ?PmCheckCriticalPartitions@@YAJPEAU_DEVICE_EXTENSION@@PEAVSC_DISK_LAYOUT@@@Z; PmCheckCriticalPartitions(_DEVICE_EXTENSION *,SC_DISK_LAYOUT *)
0x140020b11  test    eax, eax
0x140020b13  js      short loc_140020B94
0x140020b15  cmp     dword ptr [rbx+4], 0
0x140020b19  jnz     short loc_140020B72
0x140020b1b  mov     ecx, [rbx]
0x140020b1d  xor     eax, eax
0x140020b1f  mov     qword ptr [rsp+48h+var_28.4+0Ch], rax
0x140020b24  xorps   xmm0, xmm0
0x140020b27  movups  xmmword ptr [rsp+48h+var_28.PartitionStyle], xmm0
0x140020b2c  mov     [rsp+48h+var_28.PartitionStyle], ecx
0x140020b30  test    ecx, ecx
0x140020b32  jz      short loc_140020B5C
0x140020b34  cmp     ecx, 1
0x140020b37  jnz     short loc_140020B63
0x140020b39  mov     eax, [rbx+8]
0x140020b3c  movsd   xmm0, qword ptr [rbx+0Ch]
0x140020b41  mov     dword ptr [rsp+48h+var_28.4], eax
0x140020b45  mov     eax, [rbx+14h]
0x140020b48  mov     dword ptr [rsp+48h+var_28.4+0Ch], eax
0x140020b4c  movsd   qword ptr [rsp+48h+var_28.4+4], xmm0
0x140020b52  mov     dword ptr [rsp+48h+var_28.4+10h], 0
0x140020b5a  jmp     short loc_140020B63
0x140020b5c  mov     eax, [rbx+8]
0x140020b5f  mov     dword ptr [rsp+48h+var_28.4], eax
0x140020b63  lea     rdx, [rsp+48h+var_28]; struct _CREATE_DISK *
0x140020b68  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x140020b6b  call    ?PmCreateDisk@@YAJPEAU_DEVICE_EXTENSION@@PEAU_CREATE_DISK@@@Z; PmCreateDisk(_DEVICE_EXTENSION *,_CREATE_DISK *)
0x140020b70  jmp     short loc_140020B94
0x140020b72  mov     rcx, [rdi+8]; struct _DEVICE_OBJECT *
0x140020b76  mov     rdx, rbx; struct _DRIVE_LAYOUT_INFORMATION_EX *
0x140020b79  call    ?PmWritePartitionTable@@YAJPEAU_DEVICE_OBJECT@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; PmWritePartitionTable(_DEVICE_OBJECT *,_DRIVE_LAYOUT_INFORMATION_EX *)
0x140020b7e  test    eax, eax
0x140020b80  js      short loc_140020B94
0x140020b82  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x140020b85  call    ?PmInvalidatePartitionTableCache@@YAXPEAU_DEVICE_EXTENSION@@@Z; PmInvalidatePartitionTableCache(_DEVICE_EXTENSION *)
0x140020b8a  xor     edx, edx; struct _DRIVE_LAYOUT_INFORMATION_EX **
0x140020b8c  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x140020b8f  call    ?PmGetDriveLayoutEx@@YAJPEAU_DEVICE_EXTENSION@@PEAPEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; PmGetDriveLayoutEx(_DEVICE_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX * *)
0x140020b94  mov     rbx, [rsp+48h+arg_0]
0x140020b99  add     rsp, 40h
0x140020b9d  pop     rdi
0x140020b9e  retn
```
