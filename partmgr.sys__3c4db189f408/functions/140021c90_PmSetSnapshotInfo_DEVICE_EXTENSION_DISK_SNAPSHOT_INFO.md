# PmSetSnapshotInfo(_DEVICE_EXTENSION *,_DISK_SNAPSHOT_INFO *)

- ea: `0x140021c90`
- end: `0x140021ec0`
- name: `?PmSetSnapshotInfo@@YAJPEAU_DEVICE_EXTENSION@@PEAU_DISK_SNAPSHOT_INFO@@@Z`
- size: `560`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *, struct _DISK_SNAPSHOT_INFO *)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x14001ef94`
- `0x14001f510`

## callees

- `0x140007bcc`
- `0x14000d878`
- `0x14000dbd0`
- `0x14000e62c`
- `0x140011140`
- `0x14001c3d8`
- `0x140021c90`
- `0x1400241b8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140021e69`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021e7f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021e9a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021e69`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021e7f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021e9a`
- `ntoskrnl!ExAllocatePool2` at `0x140021da2`
- `ntoskrnl!ExAllocatePool2` at `0x140021da2`

## pseudocode

```c
__int64 __fastcall PmSetSnapshotInfo(struct _DEVICE_EXTENSION *a1, struct _DISK_SNAPSHOT_INFO *a2)
{
  signed int SnapshotPartition; // ebx
  int SnapshotData; // eax
  PVOID v6; // rdi
  DISK_SNAPSHOT_STATE State; // ecx
  unsigned int v8; // r15d
  char *v9; // rsi
  __int64 BestStorageDeviceId; // rax
  int v11; // eax
  ULONG AdditionalDataSize; // edx
  unsigned int v13; // r8d
  ULONG v14; // ecx
  UCHAR *Pool2; // rax
  UCHAR *v16; // r13
  unsigned int v17; // ebx
  GUID SnapshotSetId; // xmm0
  GUID SnapshotId; // xmm1
  ULONG ImportCount; // eax
  ULONG Flags; // eax
  size_t v22; // r8
  UCHAR *v23; // rcx
  PVOID P; // [rsp+20h] [rbp-38h] BYREF
  size_t Size; // [rsp+70h] [rbp+18h] BYREF
  PVOID v27; // [rsp+78h] [rbp+20h] BYREF

  v27 = 0;
  LODWORD(Size) = 0;
  P = 0;
  SnapshotPartition = PmCreateSnapshotPartition(a1);
  if ( SnapshotPartition < 0 )
    return (unsigned int)SnapshotPartition;
  SnapshotPartition = PmGetDriveLayoutEx((KSPIN_LOCK *)a1, (struct _DRIVE_LAYOUT_INFORMATION_EX **)&v27);
  if ( SnapshotPartition >= 0 )
  {
    SnapshotData = PmGetSnapshotData(
                     a1,
                     (struct _DRIVE_LAYOUT_INFORMATION_EX *)v27,
                     (struct _DISK_SNAPSHOT_DATA **)&P,
                     (unsigned int *)&Size);
    v6 = P;
    SnapshotPartition = SnapshotData;
    if ( SnapshotData < 0 )
      goto LABEL_20;
    State = a2->State;
    if ( State )
    {
      if ( State == DiskSnapshotSnapshotCheckRequired )
      {
        if ( !*((_QWORD *)a1 + 31) || (BestStorageDeviceId = StRtlFindBestStorageDeviceId()) == 0 )
        {
          SnapshotPartition = -1073741275;
          goto LABEL_20;
        }
        v8 = *(unsigned __int16 *)(BestStorageDeviceId + 8);
        v9 = (char *)(BestStorageDeviceId + 16);
      }
      else
      {
        v8 = *((_DWORD *)P + 25);
        v9 = (char *)P + *((unsigned int *)P + 24);
      }
      v11 = v8 + 112;
      if ( v8 >= 0xFFFFFF90 )
      {
        SnapshotPartition = -1073741675;
LABEL_20:
        if ( v6 )
          ExFreePoolWithTag(v6, 0);
        goto LABEL_22;
      }
    }
    else
    {
      v9 = 0;
      v8 = 0;
      v11 = 112;
    }
    AdditionalDataSize = a2->AdditionalDataSize;
    v13 = -1;
    v14 = AdditionalDataSize + v11;
    if ( AdditionalDataSize + v11 >= AdditionalDataSize )
      v13 = AdditionalDataSize + v11;
    SnapshotPartition = v14 < AdditionalDataSize ? 0xC0000095 : 0;
    LODWORD(Size) = v13;
    if ( v14 >= AdditionalDataSize )
    {
      Pool2 = (UCHAR *)ExAllocatePool2(66, v13, 1146318160);
      v16 = Pool2;
      if ( Pool2 )
      {
        v17 = Size;
        PmInitializeSnapshotData(Pool2, (unsigned int)Size);
        SnapshotSetId = a2->SnapshotSetId;
        SnapshotId = a2->SnapshotId;
        *((_DWORD *)v16 + 5) = a2->State;
        *((_QWORD *)v16 + 10) = a2->CreationTimeStamp.QuadPart;
        ImportCount = a2->ImportCount;
        *((GUID *)v16 + 2) = SnapshotSetId;
        *((_DWORD *)v16 + 22) = ImportCount;
        Flags = a2->Flags;
        *((_OWORD *)v16 + 4) = a2->LunId;
        *((_DWORD *)v16 + 3) = v17;
        *((GUID *)v16 + 3) = SnapshotId;
        *((_DWORD *)v16 + 23) = Flags;
        *((_DWORD *)v16 + 24) = 112;
        *((_DWORD *)v16 + 25) = v8;
        memmove(v16 + 112, v9, v8);
        v22 = a2->AdditionalDataSize;
        v23 = &v16[*((_DWORD *)v16 + 25) + 112];
        *((_DWORD *)v16 + 26) = *((_DWORD *)v16 + 25) + 112;
        *((_DWORD *)v16 + 27) = v22;
        memmove(v23, a2->AdditionalData, v22);
        SnapshotPartition = PmSetSnapshotData(
                              a1,
                              (struct _DRIVE_LAYOUT_INFORMATION_EX *)v27,
                              (struct _DISK_SNAPSHOT_DATA *)v16,
                              v17);
        ExFreePoolWithTag(v16, 0);
      }
      else
      {
        SnapshotPartition = -1073741670;
      }
    }
    goto LABEL_20;
  }
LABEL_22:
  if ( v27 )
    ExFreePoolWithTag(v27, 0);
  return (unsigned int)SnapshotPartition;
}

```

## disassembly

```asm
0x140021c90  mov     rax, rsp
0x140021c93  mov     [rax+8], rbx
0x140021c97  mov     [rax+10h], rbp
0x140021c9b  push    rsi
0x140021c9c  push    rdi
0x140021c9d  push    r13
0x140021c9f  push    r14
0x140021ca1  push    r15
0x140021ca3  sub     rsp, 30h
0x140021ca7  mov     r14, rdx
0x140021caa  mov     qword ptr [rax+20h], 0
0x140021cb2  mov     rbp, rcx
0x140021cb5  mov     dword ptr [rax+18h], 0
0x140021cbc  mov     qword ptr [rax-38h], 0
0x140021cc4  call    ?PmCreateSnapshotPartition@@YAJPEAU_DEVICE_EXTENSION@@@Z; PmCreateSnapshotPartition(_DEVICE_EXTENSION *)
0x140021cc9  mov     ebx, eax
0x140021ccb  test    eax, eax
0x140021ccd  js      loc_140021EA6
0x140021cd3  lea     rdx, [rsp+58h+arg_18]; struct _DRIVE_LAYOUT_INFORMATION_EX **
0x140021cd8  mov     rcx, rbp; struct _DEVICE_EXTENSION *
0x140021cdb  call    ?PmGetDriveLayoutEx@@YAJPEAU_DEVICE_EXTENSION@@PEAPEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; PmGetDriveLayoutEx(_DEVICE_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX * *)
0x140021ce0  mov     ebx, eax
0x140021ce2  test    eax, eax
0x140021ce4  js      loc_140021E8B
0x140021cea  mov     rdx, [rsp+58h+arg_18]; struct _DRIVE_LAYOUT_INFORMATION_EX *
0x140021cef  lea     r9, [rsp+58h+Size]; unsigned int *
0x140021cf4  lea     r8, [rsp+58h+P]; struct _DISK_SNAPSHOT_DATA **
0x140021cf9  mov     rcx, rbp; struct _DEVICE_EXTENSION *
0x140021cfc  call    ?PmGetSnapshotData@@YAJPEAU_DEVICE_EXTENSION@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@PEAPEAU_DISK_SNAPSHOT_DATA@@PEAK@Z; PmGetSnapshotData(_DEVICE_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX *,_DISK_SNAPSHOT_DATA * *,ulong *)
0x140021d01  mov     rdi, [rsp+58h+P]
0x140021d06  mov     ebx, eax
0x140021d08  test    eax, eax
0x140021d0a  js      loc_140021E75
0x140021d10  mov     ecx, [r14+4]
0x140021d14  test    ecx, ecx
0x140021d16  jz      short loc_140021D65
0x140021d18  cmp     ecx, 1
0x140021d1b  jz      short loc_140021D29
0x140021d1d  mov     esi, [rdi+60h]
0x140021d20  mov     r15d, [rdi+64h]
0x140021d24  add     rsi, rdi
0x140021d27  jmp     short loc_140021D52
0x140021d29  mov     rcx, [rbp+0F8h]
0x140021d30  test    rcx, rcx
0x140021d33  jnz     short loc_140021D3F
0x140021d35  mov     ebx, 0C0000225h
0x140021d3a  jmp     loc_140021E75
0x140021d3f  call    StRtlFindBestStorageDeviceId
0x140021d44  test    rax, rax
0x140021d47  jz      short loc_140021D35
0x140021d49  movzx   r15d, word ptr [rax+8]
0x140021d4e  lea     rsi, [rax+10h]
0x140021d52  lea     eax, [r15+70h]
0x140021d56  cmp     eax, 70h ; 'p'
0x140021d59  jnb     short loc_140021D6D
0x140021d5b  mov     ebx, 0C0000095h
0x140021d60  jmp     loc_140021E75
0x140021d65  xor     esi, esi
0x140021d67  xor     r15d, r15d
0x140021d6a  lea     eax, [rsi+70h]
0x140021d6d  mov     edx, [r14+48h]
0x140021d71  or      r8d, 0FFFFFFFFh
0x140021d75  mov     ebx, 0C0000095h
0x140021d7a  lea     ecx, [rdx+rax]
0x140021d7d  cmp     ecx, edx
0x140021d7f  cmovnb  r8d, ecx
0x140021d83  sbb     eax, eax
0x140021d85  and     ebx, eax
0x140021d87  mov     dword ptr [rsp+58h+Size], r8d
0x140021d8c  cmp     ecx, edx
0x140021d8e  jb      loc_140021E75
0x140021d94  mov     edx, r8d
0x140021d97  mov     ecx, 42h ; 'B'
0x140021d9c  mov     r8d, 44536D50h
0x140021da2  call    cs:__imp_ExAllocatePool2
0x140021da9  nop     dword ptr [rax+rax+00h]
0x140021dae  mov     r13, rax
0x140021db1  test    rax, rax
0x140021db4  jnz     short loc_140021DC0
0x140021db6  mov     ebx, 0C000009Ah
0x140021dbb  jmp     loc_140021E75
0x140021dc0  mov     ebx, dword ptr [rsp+58h+Size]
0x140021dc4  mov     rcx, r13; Buffer
0x140021dc7  mov     edx, ebx; Size
0x140021dc9  call    ?PmInitializeSnapshotData@@YAXPEAU_DISK_SNAPSHOT_DATA@@K@Z; PmInitializeSnapshotData(_DISK_SNAPSHOT_DATA *,ulong)
0x140021dce  movups  xmm0, xmmword ptr [r14+8]
0x140021dd3  mov     eax, [r14+4]
0x140021dd7  lea     rcx, [r13+70h]; void *
0x140021ddb  movups  xmm1, xmmword ptr [r14+18h]
0x140021de0  mov     [r13+14h], eax
0x140021de4  mov     rdx, rsi; Src
0x140021de7  mov     rax, [r14+38h]
0x140021deb  mov     [r13+50h], rax
0x140021def  mov     eax, [r14+40h]
0x140021df3  movdqu  xmmword ptr [r13+20h], xmm0
0x140021df9  mov     [r13+58h], eax
0x140021dfd  movups  xmm0, xmmword ptr [r14+28h]
0x140021e02  mov     eax, [r14+44h]
0x140021e06  mov     r8d, r15d; Size
0x140021e09  movdqu  xmmword ptr [r13+40h], xmm0
0x140021e0f  mov     [r13+0Ch], ebx
0x140021e13  movdqu  xmmword ptr [r13+30h], xmm1
0x140021e19  mov     [r13+5Ch], eax
0x140021e1d  mov     dword ptr [r13+60h], 70h ; 'p'
0x140021e25  mov     [r13+64h], r15d
0x140021e29  call    memmove
0x140021e2e  mov     eax, [r13+64h]
0x140021e32  lea     rdx, [r14+4Ch]; Src
0x140021e36  mov     r8d, [r14+48h]; Size
0x140021e3a  add     eax, 70h ; 'p'
0x140021e3d  mov     ecx, eax
0x140021e3f  add     rcx, r13; void *
0x140021e42  mov     [r13+68h], eax
0x140021e46  mov     [r13+6Ch], r8d
0x140021e4a  call    memmove
0x140021e4f  mov     rdx, [rsp+58h+arg_18]; struct _DRIVE_LAYOUT_INFORMATION_EX *
0x140021e54  mov     r9d, ebx; unsigned int
0x140021e57  mov     r8, r13; struct _DISK_SNAPSHOT_DATA *
0x140021e5a  mov     rcx, rbp; struct _DEVICE_EXTENSION *
0x140021e5d  call    ?PmSetSnapshotData@@YAJPEAU_DEVICE_EXTENSION@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@PEAU_DISK_SNAPSHOT_DATA@@K@Z; PmSetSnapshotData(_DEVICE_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX *,_DISK_SNAPSHOT_DATA *,ulong)
0x140021e62  mov     ebx, eax
0x140021e64  xor     edx, edx; Tag
0x140021e66  mov     rcx, r13; P
0x140021e69  call    cs:__imp_ExFreePoolWithTag
0x140021e70  nop     dword ptr [rax+rax+00h]
0x140021e75  test    rdi, rdi
0x140021e78  jz      short loc_140021E8B
0x140021e7a  xor     edx, edx; Tag
0x140021e7c  mov     rcx, rdi; P
0x140021e7f  call    cs:__imp_ExFreePoolWithTag
0x140021e86  nop     dword ptr [rax+rax+00h]
0x140021e8b  cmp     [rsp+58h+arg_18], 0
0x140021e91  jz      short loc_140021EA6
0x140021e93  mov     rcx, [rsp+58h+arg_18]; P
0x140021e98  xor     edx, edx; Tag
0x140021e9a  call    cs:__imp_ExFreePoolWithTag
0x140021ea1  nop     dword ptr [rax+rax+00h]
0x140021ea6  mov     rbp, [rsp+58h+arg_8]
0x140021eab  mov     eax, ebx
0x140021ead  mov     rbx, [rsp+58h+arg_0]
0x140021eb2  add     rsp, 30h
0x140021eb6  pop     r15
0x140021eb8  pop     r14
0x140021eba  pop     r13
0x140021ebc  pop     rdi
0x140021ebd  pop     rsi
0x140021ebe  retn
```
