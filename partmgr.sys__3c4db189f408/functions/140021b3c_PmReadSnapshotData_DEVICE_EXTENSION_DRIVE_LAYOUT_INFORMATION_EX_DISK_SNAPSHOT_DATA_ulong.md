# PmReadSnapshotData(_DEVICE_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX *,_DISK_SNAPSHOT_DATA * *,ulong *)

- ea: `0x140021b3c`
- end: `0x140021c88`
- name: `?PmReadSnapshotData@@YAJPEAU_DEVICE_EXTENSION@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@PEAPEAU_DISK_SNAPSHOT_DATA@@PEAK@Z`
- size: `332`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *, struct _DRIVE_LAYOUT_INFORMATION_EX *, struct _DISK_SNAPSHOT_DATA **, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x14000d878`

## callees

- `0x140005ad0`
- `0x14000ec2c`
- `0x14000eea8`
- `0x140010f20`
- `0x14001ff00`
- `0x140020240`
- `0x140021b3c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140021c5f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021c5f`
- `ntoskrnl!ExAllocatePool2` at `0x140021bea`
- `ntoskrnl!ExAllocatePool2` at `0x140021bea`

## pseudocode

```c
__int64 __fastcall PmReadSnapshotData(
        struct _DEVICE_EXTENSION *a1,
        struct _DRIVE_LAYOUT_INFORMATION_EX *a2,
        struct _DISK_SNAPSHOT_DATA **a3,
        unsigned int *a4)
{
  struct _DEVICE_OBJECT *v6; // rcx
  int DriveGeometry; // ebx
  unsigned int PartitionGpt; // eax
  union _LARGE_INTEGER *Entry; // rax
  ULONG LowPart; // esi
  void *Pool2; // rdi
  union _LARGE_INTEGER v15; // [rsp+30h] [rbp-78h] BYREF
  struct _GUID v16; // [rsp+40h] [rbp-68h] BYREF
  struct _DISK_GEOMETRY v17; // [rsp+50h] [rbp-58h] BYREF

  v17.Cylinders.LowPart = 0;
  *a3 = 0;
  *a4 = 0;
  v6 = (struct _DEVICE_OBJECT *)*((_QWORD *)a1 + 1);
  v15.QuadPart = 0;
  memset((char *)&v17.Cylinders.QuadPart + 4, 0, 20);
  DriveGeometry = PmGetDriveGeometry(v6, &v17);
  if ( DriveGeometry >= 0 )
  {
    if ( a2->PartitionStyle )
    {
      if ( a2->PartitionStyle == 1 )
      {
        v16 = PARTITION_MSFT_SNAPSHOT_GUID;
        PartitionGpt = SC_DISK_LAYOUT::FindPartitionGpt((SC_DISK_LAYOUT *)a2, &v16);
        if ( PartitionGpt != -1 )
        {
          Entry = (union _LARGE_INTEGER *)SC_DISK_LAYOUT::GetEntry((SC_DISK_LAYOUT *)a2, PartitionGpt);
          v15 = Entry[1];
          LowPart = Entry[2].LowPart;
          goto LABEL_6;
        }
      }
    }
    else
    {
      LowPart = 4 * v17.BytesPerSector;
      v15.QuadPart = 7 * v17.BytesPerSector;
      if ( SC_DISK_LAYOUT::IsRegionFree((SC_DISK_LAYOUT *)a2, v15.QuadPart, 4 * v17.BytesPerSector) )
      {
LABEL_6:
        Pool2 = (void *)ExAllocatePool2(74, LowPart, 1146318160);
        if ( Pool2 )
        {
          DriveGeometry = PmSendIO(*((PDEVICE_OBJECT *)a1 + 1), 3u, Pool2, LowPart, &v15);
          if ( DriveGeometry < 0 )
          {
            ExFreePoolWithTag(Pool2, 0);
          }
          else
          {
            *a3 = (struct _DISK_SNAPSHOT_DATA *)Pool2;
            *a4 = LowPart;
          }
        }
        else
        {
          return (unsigned int)-1073741670;
        }
        return (unsigned int)DriveGeometry;
      }
    }
    return (unsigned int)-1073741275;
  }
  return (unsigned int)DriveGeometry;
}

```

## disassembly

```asm
0x140021b3c  push    rbx
0x140021b3e  push    rbp
0x140021b3f  push    rsi
0x140021b40  push    rdi
0x140021b41  push    r14
0x140021b43  push    r15
0x140021b45  sub     rsp, 78h
0x140021b49  mov     rax, cs:__security_cookie
0x140021b50  xor     rax, rsp
0x140021b53  mov     [rsp+0A8h+var_40], rax
0x140021b58  xor     eax, eax
0x140021b5a  mov     dword ptr [rsp+0A8h+var_58.Cylinders], 0
0x140021b62  mov     [r8], rax
0x140021b65  mov     rdi, rdx
0x140021b68  mov     [r9], eax
0x140021b6b  lea     rdx, [rsp+0A8h+var_58]; struct _DISK_GEOMETRY *
0x140021b70  mov     rbp, rcx
0x140021b73  mov     [rsp+0A8h+var_58.BytesPerSector], eax
0x140021b77  mov     rcx, [rcx+8]; struct _DEVICE_OBJECT *
0x140021b7b  xorps   xmm0, xmm0
0x140021b7e  mov     r15, r9
0x140021b81  mov     qword ptr [rsp+0A8h+var_78], rax
0x140021b86  mov     r14, r8
0x140021b89  movups  xmmword ptr [rsp+0A8h+var_58.Cylinders+4], xmm0
0x140021b8e  call    ?PmGetDriveGeometry@@YAJPEAU_DEVICE_OBJECT@@PEAU_DISK_GEOMETRY@@@Z; PmGetDriveGeometry(_DEVICE_OBJECT *,_DISK_GEOMETRY *)
0x140021b93  mov     ebx, eax
0x140021b95  test    eax, eax
0x140021b97  js      loc_140021C6B
0x140021b9d  mov     ecx, [rdi]
0x140021b9f  test    ecx, ecx
0x140021ba1  jz      short loc_140021C05
0x140021ba3  cmp     ecx, 1
0x140021ba6  jnz     short loc_140021C27
0x140021ba8  movups  xmm0, xmmword ptr cs:PARTITION_MSFT_SNAPSHOT_GUID.Data1
0x140021baf  lea     rdx, [rsp+0A8h+var_68]; struct _GUID
0x140021bb4  mov     rcx, rdi; this
0x140021bb7  movdqu  xmmword ptr [rsp+0A8h+var_68.Data1], xmm0
0x140021bbd  call    ?FindPartitionGpt@SC_DISK_LAYOUT@@QEAAKU_GUID@@@Z; SC_DISK_LAYOUT::FindPartitionGpt(_GUID)
0x140021bc2  cmp     eax, 0FFFFFFFFh
0x140021bc5  jz      short loc_140021C27
0x140021bc7  mov     edx, eax; unsigned int
0x140021bc9  mov     rcx, rdi; this
0x140021bcc  call    ?GetEntry@SC_DISK_LAYOUT@@QEAAPEAVSC_PART_ENTRY@@K@Z; SC_DISK_LAYOUT::GetEntry(ulong)
0x140021bd1  mov     rcx, [rax+8]
0x140021bd5  mov     qword ptr [rsp+0A8h+var_78], rcx
0x140021bda  mov     esi, [rax+10h]
0x140021bdd  mov     edx, esi
0x140021bdf  mov     ecx, 4Ah ; 'J'
0x140021be4  mov     r8d, 44536D50h
0x140021bea  call    cs:__imp_ExAllocatePool2
0x140021bf1  nop     dword ptr [rax+rax+00h]
0x140021bf6  mov     rdi, rax
0x140021bf9  test    rax, rax
0x140021bfc  jnz     short loc_140021C2E
0x140021bfe  mov     ebx, 0C000009Ah
0x140021c03  jmp     short loc_140021C6B
0x140021c05  mov     ecx, [rsp+0A8h+var_58.BytesPerSector]
0x140021c09  imul    edx, ecx, 7; unsigned __int64
0x140021c0c  lea     esi, ds:0[rcx*4]
0x140021c13  mov     rcx, rdi; this
0x140021c16  mov     r8d, esi; unsigned int
0x140021c19  mov     qword ptr [rsp+0A8h+var_78], rdx
0x140021c1e  call    ?IsRegionFree@SC_DISK_LAYOUT@@QEAAE_KK@Z; SC_DISK_LAYOUT::IsRegionFree(unsigned __int64,ulong)
0x140021c23  test    al, al
0x140021c25  jnz     short loc_140021BDD
0x140021c27  mov     ebx, 0C0000225h
0x140021c2c  jmp     short loc_140021C6B
0x140021c2e  mov     rcx, [rbp+8]; DeviceObject
0x140021c32  lea     rax, [rsp+0A8h+var_78]
0x140021c37  mov     r9d, esi; Length
0x140021c3a  mov     [rsp+0A8h+var_88], rax; PLARGE_INTEGER
0x140021c3f  mov     r8, rdi; Buffer
0x140021c42  mov     edx, 3; MajorFunction
0x140021c47  call    ?PmSendIO@@YAJPEAU_DEVICE_OBJECT@@KPEAXKPEAT_LARGE_INTEGER@@@Z; PmSendIO(_DEVICE_OBJECT *,ulong,void *,ulong,_LARGE_INTEGER *)
0x140021c4c  mov     ebx, eax
0x140021c4e  test    eax, eax
0x140021c50  js      short loc_140021C5A
0x140021c52  mov     [r14], rdi
0x140021c55  mov     [r15], esi
0x140021c58  jmp     short loc_140021C6B
0x140021c5a  xor     edx, edx; Tag
0x140021c5c  mov     rcx, rdi; P
0x140021c5f  call    cs:__imp_ExFreePoolWithTag
0x140021c66  nop     dword ptr [rax+rax+00h]
0x140021c6b  mov     eax, ebx
0x140021c6d  mov     rcx, [rsp+0A8h+var_40]
0x140021c72  xor     rcx, rsp; StackCookie
0x140021c75  call    __security_check_cookie
0x140021c7a  add     rsp, 78h
0x140021c7e  pop     r15
0x140021c80  pop     r14
0x140021c82  pop     rdi
0x140021c83  pop     rsi
0x140021c84  pop     rbp
0x140021c85  pop     rbx
0x140021c86  retn
```
