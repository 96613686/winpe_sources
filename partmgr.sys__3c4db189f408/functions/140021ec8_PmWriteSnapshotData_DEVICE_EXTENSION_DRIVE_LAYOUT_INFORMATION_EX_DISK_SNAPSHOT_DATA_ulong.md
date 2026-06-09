# PmWriteSnapshotData(_DEVICE_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX *,_DISK_SNAPSHOT_DATA *,ulong)

- ea: `0x140021ec8`
- end: `0x140022013`
- name: `?PmWriteSnapshotData@@YAJPEAU_DEVICE_EXTENSION@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@PEAU_DISK_SNAPSHOT_DATA@@K@Z`
- size: `331`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *, struct _DRIVE_LAYOUT_INFORMATION_EX *, struct _DISK_SNAPSHOT_DATA *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x14000dbd0`

## callees

- `0x140005ad0`
- `0x14000ec2c`
- `0x14000eea8`
- `0x140010f20`
- `0x140011140`
- `0x14001ff00`
- `0x140020240`
- `0x140021ec8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140021fec`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021fec`
- `ntoskrnl!ExAllocatePool2` at `0x140021fa5`
- `ntoskrnl!ExAllocatePool2` at `0x140021fa5`

## pseudocode

```c
__int64 __fastcall PmWriteSnapshotData(
        struct _DEVICE_EXTENSION *a1,
        struct _DRIVE_LAYOUT_INFORMATION_EX *a2,
        struct _DISK_SNAPSHOT_DATA *a3,
        unsigned int a4)
{
  size_t v4; // rsi
  struct _DEVICE_OBJECT *v7; // rcx
  int DriveGeometry; // ebx
  unsigned int PartitionGpt; // eax
  union _LARGE_INTEGER *Entry; // rax
  ULONG LowPart; // ebx
  void *Pool2; // rax
  void *v14; // rdi
  union _LARGE_INTEGER v16; // [rsp+30h] [rbp-68h] BYREF
  struct _GUID v17; // [rsp+40h] [rbp-58h] BYREF
  struct _DISK_GEOMETRY v18; // [rsp+50h] [rbp-48h] BYREF

  v4 = a4;
  v16.QuadPart = 0;
  v7 = (struct _DEVICE_OBJECT *)*((_QWORD *)a1 + 1);
  memset(&v18, 0, sizeof(v18));
  DriveGeometry = PmGetDriveGeometry(v7, &v18);
  if ( DriveGeometry < 0 )
    return (unsigned int)DriveGeometry;
  if ( !a2->PartitionStyle )
  {
    LowPart = 4 * v18.BytesPerSector;
    v16.QuadPart = 7 * v18.BytesPerSector;
    if ( SC_DISK_LAYOUT::IsRegionFree((SC_DISK_LAYOUT *)a2, v16.QuadPart, 4 * v18.BytesPerSector) )
      goto LABEL_6;
    return (unsigned int)-1073741275;
  }
  if ( a2->PartitionStyle != 1 )
    return (unsigned int)-1073741275;
  v17 = PARTITION_MSFT_SNAPSHOT_GUID;
  PartitionGpt = SC_DISK_LAYOUT::FindPartitionGpt((SC_DISK_LAYOUT *)a2, &v17);
  if ( PartitionGpt == -1 )
    return (unsigned int)-1073741275;
  Entry = (union _LARGE_INTEGER *)SC_DISK_LAYOUT::GetEntry((SC_DISK_LAYOUT *)a2, PartitionGpt);
  v16 = Entry[1];
  LowPart = Entry[2].LowPart;
LABEL_6:
  if ( (unsigned int)v4 <= LowPart && (Pool2 = (void *)ExAllocatePool2(72, LowPart, 1146318160), (v14 = Pool2) != 0) )
  {
    memmove(Pool2, a3, v4);
    DriveGeometry = PmSendIO(*((PDEVICE_OBJECT *)a1 + 1), 4u, v14, LowPart, &v16);
    ExFreePoolWithTag(v14, 0);
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return (unsigned int)DriveGeometry;
}

```

## disassembly

```asm
0x140021ec8  push    rbx
0x140021eca  push    rbp
0x140021ecb  push    rsi
0x140021ecc  push    rdi
0x140021ecd  push    r14
0x140021ecf  sub     rsp, 70h
0x140021ed3  mov     rax, cs:__security_cookie
0x140021eda  xor     rax, rsp
0x140021edd  mov     [rsp+98h+var_30], rax
0x140021ee2  xor     eax, eax
0x140021ee4  mov     esi, r9d
0x140021ee7  mov     rdi, rdx
0x140021eea  mov     [rsp+98h+var_48.BytesPerSector], eax
0x140021eee  mov     rbp, rcx
0x140021ef1  mov     qword ptr [rsp+98h+var_68], rax
0x140021ef6  mov     rcx, [rcx+8]; struct _DEVICE_OBJECT *
0x140021efa  lea     rdx, [rsp+98h+var_48]; struct _DISK_GEOMETRY *
0x140021eff  xorps   xmm0, xmm0
0x140021f02  mov     dword ptr [rsp+98h+var_48.Cylinders], 0
0x140021f0a  movups  xmmword ptr [rsp+98h+var_48.Cylinders+4], xmm0
0x140021f0f  mov     r14, r8
0x140021f12  call    ?PmGetDriveGeometry@@YAJPEAU_DEVICE_OBJECT@@PEAU_DISK_GEOMETRY@@@Z; PmGetDriveGeometry(_DEVICE_OBJECT *,_DISK_GEOMETRY *)
0x140021f17  mov     ebx, eax
0x140021f19  test    eax, eax
0x140021f1b  js      loc_140021FF8
0x140021f21  mov     ecx, [rdi]
0x140021f23  test    ecx, ecx
0x140021f25  jz      short loc_140021F6F
0x140021f27  cmp     ecx, 1
0x140021f2a  jnz     short loc_140021F91
0x140021f2c  movups  xmm0, xmmword ptr cs:PARTITION_MSFT_SNAPSHOT_GUID.Data1
0x140021f33  lea     rdx, [rsp+98h+var_58]; struct _GUID
0x140021f38  mov     rcx, rdi; this
0x140021f3b  movdqu  xmmword ptr [rsp+98h+var_58.Data1], xmm0
0x140021f41  call    ?FindPartitionGpt@SC_DISK_LAYOUT@@QEAAKU_GUID@@@Z; SC_DISK_LAYOUT::FindPartitionGpt(_GUID)
0x140021f46  cmp     eax, 0FFFFFFFFh
0x140021f49  jz      short loc_140021F91
0x140021f4b  mov     edx, eax; unsigned int
0x140021f4d  mov     rcx, rdi; this
0x140021f50  call    ?GetEntry@SC_DISK_LAYOUT@@QEAAPEAVSC_PART_ENTRY@@K@Z; SC_DISK_LAYOUT::GetEntry(ulong)
0x140021f55  mov     rcx, [rax+8]
0x140021f59  mov     qword ptr [rsp+98h+var_68], rcx
0x140021f5e  mov     ebx, [rax+10h]
0x140021f61  cmp     esi, ebx
0x140021f63  jbe     short loc_140021F98
0x140021f65  mov     ebx, 0C000009Ah
0x140021f6a  jmp     loc_140021FF8
0x140021f6f  mov     ecx, [rsp+98h+var_48.BytesPerSector]
0x140021f73  imul    edx, ecx, 7; unsigned __int64
0x140021f76  lea     ebx, ds:0[rcx*4]
0x140021f7d  mov     rcx, rdi; this
0x140021f80  mov     r8d, ebx; unsigned int
0x140021f83  mov     qword ptr [rsp+98h+var_68], rdx
0x140021f88  call    ?IsRegionFree@SC_DISK_LAYOUT@@QEAAE_KK@Z; SC_DISK_LAYOUT::IsRegionFree(unsigned __int64,ulong)
0x140021f8d  test    al, al
0x140021f8f  jnz     short loc_140021F61
0x140021f91  mov     ebx, 0C0000225h
0x140021f96  jmp     short loc_140021FF8
0x140021f98  mov     edx, ebx
0x140021f9a  mov     ecx, 48h ; 'H'
0x140021f9f  mov     r8d, 44536D50h
0x140021fa5  call    cs:__imp_ExAllocatePool2
0x140021fac  nop     dword ptr [rax+rax+00h]
0x140021fb1  mov     rdi, rax
0x140021fb4  test    rax, rax
0x140021fb7  jz      short loc_140021F65
0x140021fb9  mov     r8, rsi; Size
0x140021fbc  mov     rdx, r14; Src
0x140021fbf  mov     rcx, rax; void *
0x140021fc2  call    memmove
0x140021fc7  mov     rcx, [rbp+8]; DeviceObject
0x140021fcb  lea     rax, [rsp+98h+var_68]
0x140021fd0  mov     r9d, ebx; Length
0x140021fd3  mov     [rsp+98h+var_78], rax; PLARGE_INTEGER
0x140021fd8  mov     r8, rdi; Buffer
0x140021fdb  mov     edx, 4; MajorFunction
0x140021fe0  call    ?PmSendIO@@YAJPEAU_DEVICE_OBJECT@@KPEAXKPEAT_LARGE_INTEGER@@@Z; PmSendIO(_DEVICE_OBJECT *,ulong,void *,ulong,_LARGE_INTEGER *)
0x140021fe5  mov     ebx, eax
0x140021fe7  xor     edx, edx; Tag
0x140021fe9  mov     rcx, rdi; P
0x140021fec  call    cs:__imp_ExFreePoolWithTag
0x140021ff3  nop     dword ptr [rax+rax+00h]
0x140021ff8  mov     eax, ebx
0x140021ffa  mov     rcx, [rsp+98h+var_30]
0x140021fff  xor     rcx, rsp; StackCookie
0x140022002  call    __security_check_cookie
0x140022007  add     rsp, 70h
0x14002200b  pop     r14
0x14002200d  pop     rdi
0x14002200e  pop     rsi
0x14002200f  pop     rbp
0x140022010  pop     rbx
0x140022011  retn
```
