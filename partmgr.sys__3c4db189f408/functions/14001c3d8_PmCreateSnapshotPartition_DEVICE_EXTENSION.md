# PmCreateSnapshotPartition(_DEVICE_EXTENSION *)

- ea: `0x14001c3d8`
- end: `0x14001c652`
- name: `?PmCreateSnapshotPartition@@YAJPEAU_DEVICE_EXTENSION@@@Z`
- size: `634`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x140021c90`

## callees

- `0x140004800`
- `0x140007bcc`
- `0x14000cb34`
- `0x140010f20`
- `0x140011020`
- `0x140011140`
- `0x14001c3d8`
- `0x14001d090`
- `0x14001ff00`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001c60c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c629`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c60c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c629`
- `ntoskrnl!ExUuidCreate` at `0x14001c5ad`
- `ntoskrnl!ExUuidCreate` at `0x14001c5ad`
- `ntoskrnl!ExAllocatePool2` at `0x14001c4d8`
- `ntoskrnl!ExAllocatePool2` at `0x14001c4d8`

## string_xrefs

- `0x14001c5cb`: `Microsoft shadow copy partition`

## pseudocode

```c
__int64 __fastcall PmCreateSnapshotPartition(struct _DEVICE_EXTENSION *a1)
{
  int DriveLayout; // eax
  unsigned int *v3; // rsi
  signed int DriveGeometry; // ebx
  __int64 i; // rcx
  __int64 v6; // rax
  __int64 v7; // rdx
  unsigned __int64 v8; // rcx
  unsigned int v9; // r14d
  unsigned int v10; // eax
  struct _DRIVE_LAYOUT_INFORMATION_EX *Pool2; // rax
  struct _DRIVE_LAYOUT_INFORMATION_EX *v12; // rdi
  unsigned int PartitionCount; // r15d
  __int64 j; // rbx
  __int64 v15; // r14
  LARGE_INTEGER PartitionLength; // r8
  LARGE_INTEGER v17; // rax
  LARGE_INTEGER StartingOffset; // rcx
  __int64 v19; // r14
  struct _DEVICE_OBJECT *v20; // rcx
  void *Src; // [rsp+20h] [rbp-68h] BYREF
  _DISK_GEOMETRY v23; // [rsp+28h] [rbp-60h] BYREF

  memset(&v23, 0, sizeof(v23));
  Src = 0;
  DriveLayout = PmGetDriveLayoutEx((KSPIN_LOCK *)a1, (struct _DRIVE_LAYOUT_INFORMATION_EX **)&Src);
  v3 = (unsigned int *)Src;
  DriveGeometry = DriveLayout;
  if ( DriveLayout >= 0 && *(_DWORD *)Src == 1 )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)Src + 1); i = (unsigned int)(i + 1) )
    {
      v6 = *((_QWORD *)Src + 18 * i + 10) - *(_QWORD *)&PARTITION_MSFT_SNAPSHOT_GUID.Data1;
      if ( !v6 )
        v6 = *((_QWORD *)Src + 18 * i + 11) - *(_QWORD *)PARTITION_MSFT_SNAPSHOT_GUID.Data4;
      if ( !v6 )
        goto LABEL_29;
    }
    DriveGeometry = PmGetDriveGeometry(*((struct _DEVICE_OBJECT **)a1 + 1), &v23);
    if ( DriveGeometry >= 0 )
    {
      v7 = 0xFFFFFFFFLL;
      v8 = 144LL * v3[1];
      if ( v8 > 0xFFFFFFFF || (v9 = v8 + 48, (unsigned int)v8 >= 0xFFFFFFD0) )
      {
        DriveGeometry = -1073741675;
      }
      else
      {
        v10 = v8 + 192;
        if ( v9 < 0xFFFFFF70 )
          v7 = v10;
        DriveGeometry = v9 >= 0xFFFFFF70 ? 0xC0000095 : 0;
        if ( v10 >= 0x90 )
        {
          Pool2 = (struct _DRIVE_LAYOUT_INFORMATION_EX *)ExAllocatePool2(64, v7, 1414557008);
          v12 = Pool2;
          if ( Pool2 )
          {
            memmove(Pool2, v3, v9);
            PartitionCount = v12->PartitionCount;
            for ( j = 0; ; j = (unsigned int)(j + 1) )
            {
              if ( (unsigned int)j >= PartitionCount )
              {
                DriveGeometry = -1073741275;
                goto LABEL_27;
              }
              v15 = j;
              if ( !memcmp(&v12->PartitionEntry[0].Mbr + 18 * j, &PARTITION_MSFT_RESERVED_GUID, 0x10u) )
                break;
            }
            PartitionLength = v12->PartitionEntry[v15].PartitionLength;
            v17.QuadPart = v23.BytesPerSector << 9;
            if ( PartitionLength.QuadPart >= v17.QuadPart )
            {
              StartingOffset = v12->PartitionEntry[v15].StartingOffset;
              v12->PartitionEntry[v15].PartitionLength.QuadPart = PartitionLength.QuadPart - v17.QuadPart;
              v12->PartitionEntry[v15].StartingOffset.QuadPart = StartingOffset.QuadPart + v17.QuadPart;
              v12->PartitionEntry[v15].RewritePartition = 1;
              v19 = 72LL * v12->PartitionCount;
              v12->PartitionEntry[(unsigned __int64)v19 / 0x48].StartingOffset = StartingOffset;
              v12->PartitionEntry[(unsigned __int64)v19 / 0x48].PartitionStyle = PARTITION_STYLE_GPT;
              v12->PartitionEntry[(unsigned __int64)v19 / 0x48].PartitionLength = v17;
              v12->PartitionEntry[(unsigned __int64)v19 / 0x48].RewritePartition = 1;
              v12->PartitionEntry[(unsigned __int64)v19 / 0x48].Gpt.PartitionType = PARTITION_MSFT_SNAPSHOT_GUID;
              DriveGeometry = ExUuidCreate(&v12->PartitionEntry[(unsigned __int64)v19 / 0x48].Gpt.PartitionId);
              if ( DriveGeometry >= 0 )
              {
                RtlStringCbCopyW(&v12->PartitionEntry[0].Gpt.Name[v19], 0x48u, L"Microsoft shadow copy partition");
                v20 = (struct _DEVICE_OBJECT *)*((_QWORD *)a1 + 1);
                ++v12->PartitionCount;
                DriveGeometry = PmWritePartitionTable(v20, v12);
                if ( DriveGeometry >= 0 )
                {
                  PmInvalidatePartitionTableCache(a1);
                  DriveGeometry = PmGetDriveLayoutEx((KSPIN_LOCK *)a1, 0);
                }
              }
            }
            else
            {
              DriveGeometry = -1073741670;
            }
LABEL_27:
            ExFreePoolWithTag(v12, 0);
          }
          else
          {
            DriveGeometry = -1073741670;
          }
        }
      }
    }
  }
LABEL_29:
  if ( v3 )
    ExFreePoolWithTag(v3, 0);
  return (unsigned int)DriveGeometry;
}

```

## disassembly

```asm
0x14001c3d8  push    rbx
0x14001c3da  push    rbp
0x14001c3db  push    rsi
0x14001c3dc  push    rdi
0x14001c3dd  push    r14
0x14001c3df  push    r15
0x14001c3e1  sub     rsp, 58h
0x14001c3e5  mov     rax, cs:__security_cookie
0x14001c3ec  xor     rax, rsp
0x14001c3ef  mov     [rsp+88h+var_48], rax
0x14001c3f4  xor     eax, eax
0x14001c3f6  mov     dword ptr [rsp+88h+var_60.Cylinders], 0
0x14001c3fe  xorps   xmm0, xmm0
0x14001c401  mov     [rsp+88h+var_60.BytesPerSector], eax
0x14001c405  lea     rdx, [rsp+88h+Src]; struct _DRIVE_LAYOUT_INFORMATION_EX **
0x14001c40a  mov     [rsp+88h+Src], rax
0x14001c40f  movups  xmmword ptr [rsp+88h+var_60.Cylinders+4], xmm0
0x14001c414  mov     rbp, rcx
0x14001c417  call    ?PmGetDriveLayoutEx@@YAJPEAU_DEVICE_EXTENSION@@PEAPEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; PmGetDriveLayoutEx(_DEVICE_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX * *)
0x14001c41c  mov     rsi, [rsp+88h+Src]
0x14001c421  mov     ebx, eax
0x14001c423  test    eax, eax
0x14001c425  js      loc_14001C61F
0x14001c42b  cmp     dword ptr [rsi], 1
0x14001c42e  jnz     loc_14001C61F
0x14001c434  mov     r8d, [rsi+4]
0x14001c438  xor     ecx, ecx
0x14001c43a  cmp     ecx, r8d
0x14001c43d  jnb     short loc_14001C46D
0x14001c43f  lea     rdx, [rcx+rcx*8]
0x14001c443  add     rdx, rdx
0x14001c446  mov     rax, [rsi+rdx*8+50h]
0x14001c44b  sub     rax, qword ptr cs:PARTITION_MSFT_SNAPSHOT_GUID.Data1
0x14001c452  jnz     short loc_14001C460
0x14001c454  mov     rax, [rsi+rdx*8+58h]
0x14001c459  sub     rax, qword ptr cs:PARTITION_MSFT_SNAPSHOT_GUID.Data4
0x14001c460  test    rax, rax
0x14001c463  jz      loc_14001C61F
0x14001c469  inc     ecx
0x14001c46b  jmp     short loc_14001C43A
0x14001c46d  mov     rcx, [rbp+8]; struct _DEVICE_OBJECT *
0x14001c471  lea     rdx, [rsp+88h+var_60]; struct _DISK_GEOMETRY *
0x14001c476  call    ?PmGetDriveGeometry@@YAJPEAU_DEVICE_OBJECT@@PEAU_DISK_GEOMETRY@@@Z; PmGetDriveGeometry(_DEVICE_OBJECT *,_DISK_GEOMETRY *)
0x14001c47b  mov     ebx, eax
0x14001c47d  test    eax, eax
0x14001c47f  js      loc_14001C61F
0x14001c485  mov     eax, [rsi+4]
0x14001c488  mov     edx, 0FFFFFFFFh
0x14001c48d  lea     rcx, [rax+rax*8]
0x14001c491  shl     rcx, 4
0x14001c495  cmp     rcx, rdx
0x14001c498  ja      loc_14001C61A
0x14001c49e  lea     r14d, [rcx+30h]
0x14001c4a2  cmp     r14d, 30h ; '0'
0x14001c4a6  jb      loc_14001C61A
0x14001c4ac  lea     eax, [r14+90h]
0x14001c4b3  mov     ecx, 90h
0x14001c4b8  cmp     eax, ecx
0x14001c4ba  cmovnb  edx, eax
0x14001c4bd  sbb     ebx, ebx
0x14001c4bf  and     ebx, 0C0000095h
0x14001c4c5  cmp     eax, ecx
0x14001c4c7  jb      loc_14001C61F
0x14001c4cd  mov     ecx, 40h ; '@'
0x14001c4d2  mov     r8d, 54506D50h
0x14001c4d8  call    cs:__imp_ExAllocatePool2
0x14001c4df  nop     dword ptr [rax+rax+00h]
0x14001c4e4  mov     rdi, rax
0x14001c4e7  test    rax, rax
0x14001c4ea  jnz     short loc_14001C4F6
0x14001c4ec  mov     ebx, 0C000009Ah
0x14001c4f1  jmp     loc_14001C61F
0x14001c4f6  mov     r8d, r14d; Size
0x14001c4f9  mov     rdx, rsi; Src
0x14001c4fc  mov     rcx, rdi; void *
0x14001c4ff  call    memmove
0x14001c504  mov     r15d, [rdi+4]
0x14001c508  xor     ebx, ebx
0x14001c50a  cmp     ebx, r15d
0x14001c50d  jnb     loc_14001C602
0x14001c513  lea     r14, [rbx+rbx*8]
0x14001c517  mov     r8d, 10h; Size
0x14001c51d  shl     r14, 4
0x14001c521  lea     rcx, [rdi+50h]
0x14001c525  add     rcx, r14; Buf1
0x14001c528  lea     rdx, PARTITION_MSFT_RESERVED_GUID; Buf2
0x14001c52f  call    memcmp
0x14001c534  test    eax, eax
0x14001c536  jz      short loc_14001C53C
0x14001c538  inc     ebx
0x14001c53a  jmp     short loc_14001C50A
0x14001c53c  mov     eax, [rsp+88h+var_60.BytesPerSector]
0x14001c540  mov     r8, [r14+rdi+40h]
0x14001c545  shl     eax, 9
0x14001c548  mov     edx, eax
0x14001c54a  cmp     r8, rdx
0x14001c54d  jge     short loc_14001C559
0x14001c54f  mov     ebx, 0C000009Ah
0x14001c554  jmp     loc_14001C607
0x14001c559  mov     rcx, [r14+rdi+38h]
0x14001c55e  sub     r8, rdx
0x14001c561  mov     [r14+rdi+40h], r8
0x14001c566  add     rax, rcx
0x14001c569  mov     [r14+rdi+38h], rax
0x14001c56e  mov     byte ptr [r14+rdi+4Ch], 1
0x14001c574  mov     eax, [rdi+4]
0x14001c577  lea     r14, [rax+rax*8]
0x14001c57b  shl     r14, 4
0x14001c57f  mov     [r14+rdi+38h], rcx
0x14001c584  lea     rcx, [r14+60h]
0x14001c588  mov     dword ptr [r14+rdi+30h], 1
0x14001c591  add     rcx, rdi; Uuid
0x14001c594  mov     [r14+rdi+40h], rdx
0x14001c599  mov     byte ptr [r14+rdi+4Ch], 1
0x14001c59f  movups  xmm0, xmmword ptr cs:PARTITION_MSFT_SNAPSHOT_GUID.Data1
0x14001c5a6  movdqu  xmmword ptr [r14+rdi+50h], xmm0
0x14001c5ad  call    cs:__imp_ExUuidCreate
0x14001c5b4  nop     dword ptr [rax+rax+00h]
0x14001c5b9  mov     ebx, eax
0x14001c5bb  test    eax, eax
0x14001c5bd  js      short loc_14001C607
0x14001c5bf  lea     rcx, [rdi+78h]
0x14001c5c3  mov     edx, 48h ; 'H'; cbDest
0x14001c5c8  add     rcx, r14; pszDest
0x14001c5cb  lea     r8, aMicrosoftShado; "Microsoft shadow copy partition"
0x14001c5d2  call    RtlStringCbCopyW
0x14001c5d7  mov     rcx, [rbp+8]; struct _DEVICE_OBJECT *
0x14001c5db  mov     rdx, rdi; struct _DRIVE_LAYOUT_INFORMATION_EX *
0x14001c5de  inc     dword ptr [rdi+4]
0x14001c5e1  call    ?PmWritePartitionTable@@YAJPEAU_DEVICE_OBJECT@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; PmWritePartitionTable(_DEVICE_OBJECT *,_DRIVE_LAYOUT_INFORMATION_EX *)
0x14001c5e6  mov     ebx, eax
0x14001c5e8  test    eax, eax
0x14001c5ea  js      short loc_14001C607
0x14001c5ec  mov     rcx, rbp; struct _DEVICE_EXTENSION *
0x14001c5ef  call    ?PmInvalidatePartitionTableCache@@YAXPEAU_DEVICE_EXTENSION@@@Z; PmInvalidatePartitionTableCache(_DEVICE_EXTENSION *)
0x14001c5f4  xor     edx, edx; struct _DRIVE_LAYOUT_INFORMATION_EX **
0x14001c5f6  mov     rcx, rbp; struct _DEVICE_EXTENSION *
0x14001c5f9  call    ?PmGetDriveLayoutEx@@YAJPEAU_DEVICE_EXTENSION@@PEAPEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; PmGetDriveLayoutEx(_DEVICE_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX * *)
0x14001c5fe  mov     ebx, eax
0x14001c600  jmp     short loc_14001C607
0x14001c602  mov     ebx, 0C0000225h
0x14001c607  xor     edx, edx; Tag
0x14001c609  mov     rcx, rdi; P
0x14001c60c  call    cs:__imp_ExFreePoolWithTag
0x14001c613  nop     dword ptr [rax+rax+00h]
0x14001c618  jmp     short loc_14001C61F
0x14001c61a  mov     ebx, 0C0000095h
0x14001c61f  test    rsi, rsi
0x14001c622  jz      short loc_14001C635
0x14001c624  xor     edx, edx; Tag
0x14001c626  mov     rcx, rsi; P
0x14001c629  call    cs:__imp_ExFreePoolWithTag
0x14001c630  nop     dword ptr [rax+rax+00h]
0x14001c635  mov     eax, ebx
0x14001c637  mov     rcx, [rsp+88h+var_48]
0x14001c63c  xor     rcx, rsp; StackCookie
0x14001c63f  call    __security_check_cookie
0x14001c644  add     rsp, 58h
0x14001c648  pop     r15
0x14001c64a  pop     r14
0x14001c64c  pop     rdi
0x14001c64d  pop     rsi
0x14001c64e  pop     rbp
0x14001c64f  pop     rbx
0x14001c650  retn
```
