# PmGetSnapshotInfo(_DEVICE_EXTENSION *,_DISK_SNAPSHOT_INFO * *)

- ea: `0x140021970`
- end: `0x140021ab3`
- name: `?PmGetSnapshotInfo@@YAJPEAU_DEVICE_EXTENSION@@PEAPEAU_DISK_SNAPSHOT_INFO@@@Z`
- size: `323`
- prototype: `__int64 __fastcall(KSPIN_LOCK *, struct _DISK_SNAPSHOT_INFO **)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x14001e19c`

## callees

- `0x140007bcc`
- `0x14000d878`
- `0x140011140`
- `0x140021970`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140021a7b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021a96`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021a7b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021a96`
- `ntoskrnl!ExAllocatePool2` at `0x1400219fe`
- `ntoskrnl!ExAllocatePool2` at `0x1400219fe`

## pseudocode

```c
__int64 __fastcall PmGetSnapshotInfo(KSPIN_LOCK *a1, struct _DISK_SNAPSHOT_INFO **a2)
{
  int DriveLayout; // ebx
  int SnapshotData; // eax
  _DWORD *v6; // rdi
  __int64 Pool2; // rax
  struct _DISK_SNAPSHOT_INFO *v8; // rsi
  void *v9; // rcx
  ULONG v10; // eax
  unsigned int v12; // [rsp+48h] [rbp+10h] BYREF
  PVOID v13; // [rsp+50h] [rbp+18h] BYREF
  PVOID P; // [rsp+58h] [rbp+20h] BYREF

  *a2 = 0;
  v13 = 0;
  v12 = 0;
  P = 0;
  DriveLayout = PmGetDriveLayoutEx(a1, (struct _DRIVE_LAYOUT_INFORMATION_EX **)&v13);
  if ( DriveLayout >= 0 )
  {
    SnapshotData = PmGetSnapshotData(
                     (struct _DEVICE_EXTENSION *)a1,
                     (struct _DRIVE_LAYOUT_INFORMATION_EX *)v13,
                     (struct _DISK_SNAPSHOT_DATA **)&P,
                     &v12);
    v6 = P;
    DriveLayout = SnapshotData;
    if ( SnapshotData >= 0 )
    {
      if ( *((_DWORD *)P + 27) < 0xFFFFFFB4 )
      {
        Pool2 = ExAllocatePool2(64, (unsigned int)(*((_DWORD *)P + 27) + 76), 1146318160);
        v8 = (struct _DISK_SNAPSHOT_INFO *)Pool2;
        if ( Pool2 )
        {
          *(_DWORD *)Pool2 = 80;
          v9 = (void *)(Pool2 + 76);
          DriveLayout = 0;
          *(_DWORD *)(Pool2 + 4) = v6[5];
          *(_OWORD *)(Pool2 + 8) = *((_OWORD *)v6 + 2);
          *(_OWORD *)(Pool2 + 24) = *((_OWORD *)v6 + 3);
          *(_OWORD *)(Pool2 + 40) = *((_OWORD *)v6 + 4);
          *(_QWORD *)(Pool2 + 56) = *((_QWORD *)v6 + 10);
          *(_DWORD *)(Pool2 + 64) = v6[22];
          *(_DWORD *)(Pool2 + 68) = v6[23];
          v10 = v6[27];
          v8->AdditionalDataSize = v10;
          memmove(v9, (char *)v6 + (unsigned int)v6[26], v10);
          *a2 = v8;
        }
        else
        {
          DriveLayout = -1073741670;
        }
      }
      else
      {
        DriveLayout = -1073741675;
      }
    }
    if ( v6 )
      ExFreePoolWithTag(v6, 0);
  }
  if ( v13 )
    ExFreePoolWithTag(v13, 0);
  return (unsigned int)DriveLayout;
}

```

## disassembly

```asm
0x140021970  mov     rax, rsp
0x140021973  mov     [rax+8], rbx
0x140021977  push    rsi
0x140021978  push    rdi
0x140021979  push    r14
0x14002197b  sub     rsp, 20h
0x14002197f  mov     r14, rdx
0x140021982  mov     qword ptr [rdx], 0
0x140021989  lea     rdx, [rax+18h]; struct _DRIVE_LAYOUT_INFORMATION_EX **
0x14002198d  mov     qword ptr [rax+18h], 0
0x140021995  mov     rdi, rcx
0x140021998  mov     dword ptr [rax+10h], 0
0x14002199f  mov     qword ptr [rax+20h], 0
0x1400219a7  call    ?PmGetDriveLayoutEx@@YAJPEAU_DEVICE_EXTENSION@@PEAPEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; PmGetDriveLayoutEx(_DEVICE_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX * *)
0x1400219ac  mov     ebx, eax
0x1400219ae  test    eax, eax
0x1400219b0  js      loc_140021A87
0x1400219b6  mov     rdx, [rsp+38h+arg_10]; struct _DRIVE_LAYOUT_INFORMATION_EX *
0x1400219bb  lea     r9, [rsp+38h+arg_8]; unsigned int *
0x1400219c0  lea     r8, [rsp+38h+P]; struct _DISK_SNAPSHOT_DATA **
0x1400219c5  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x1400219c8  call    ?PmGetSnapshotData@@YAJPEAU_DEVICE_EXTENSION@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@PEAPEAU_DISK_SNAPSHOT_DATA@@PEAK@Z; PmGetSnapshotData(_DEVICE_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX *,_DISK_SNAPSHOT_DATA * *,ulong *)
0x1400219cd  mov     rdi, [rsp+38h+P]
0x1400219d2  mov     ebx, eax
0x1400219d4  test    eax, eax
0x1400219d6  js      loc_140021A71
0x1400219dc  mov     eax, [rdi+6Ch]
0x1400219df  add     eax, 4Ch ; 'L'
0x1400219e2  cmp     eax, 4Ch ; 'L'
0x1400219e5  jnb     short loc_1400219F1
0x1400219e7  mov     ebx, 0C0000095h
0x1400219ec  jmp     loc_140021A71
0x1400219f1  mov     edx, eax
0x1400219f3  mov     ecx, 40h ; '@'
0x1400219f8  mov     r8d, 44536D50h
0x1400219fe  call    cs:__imp_ExAllocatePool2
0x140021a05  nop     dword ptr [rax+rax+00h]
0x140021a0a  mov     rsi, rax
0x140021a0d  test    rax, rax
0x140021a10  jnz     short loc_140021A19
0x140021a12  mov     ebx, 0C000009Ah
0x140021a17  jmp     short loc_140021A71
0x140021a19  mov     dword ptr [rax], 50h ; 'P'
0x140021a1f  lea     rcx, [rsi+4Ch]; void *
0x140021a23  mov     eax, [rdi+14h]
0x140021a26  xor     ebx, ebx
0x140021a28  mov     [rsi+4], eax
0x140021a2b  movups  xmm0, xmmword ptr [rdi+20h]
0x140021a2f  movdqu  xmmword ptr [rsi+8], xmm0
0x140021a34  movups  xmm1, xmmword ptr [rdi+30h]
0x140021a38  movdqu  xmmword ptr [rsi+18h], xmm1
0x140021a3d  movups  xmm0, xmmword ptr [rdi+40h]
0x140021a41  movdqu  xmmword ptr [rsi+28h], xmm0
0x140021a46  mov     rax, [rdi+50h]
0x140021a4a  mov     [rsi+38h], rax
0x140021a4e  mov     eax, [rdi+58h]
0x140021a51  mov     [rsi+40h], eax
0x140021a54  mov     eax, [rdi+5Ch]
0x140021a57  mov     [rsi+44h], eax
0x140021a5a  mov     eax, [rdi+6Ch]
0x140021a5d  mov     [rsi+48h], eax
0x140021a60  mov     r8d, eax; Size
0x140021a63  mov     edx, [rdi+68h]
0x140021a66  add     rdx, rdi; Src
0x140021a69  call    memmove
0x140021a6e  mov     [r14], rsi
0x140021a71  test    rdi, rdi
0x140021a74  jz      short loc_140021A87
0x140021a76  xor     edx, edx; Tag
0x140021a78  mov     rcx, rdi; P
0x140021a7b  call    cs:__imp_ExFreePoolWithTag
0x140021a82  nop     dword ptr [rax+rax+00h]
0x140021a87  cmp     [rsp+38h+arg_10], 0
0x140021a8d  jz      short loc_140021AA2
0x140021a8f  mov     rcx, [rsp+38h+arg_10]; P
0x140021a94  xor     edx, edx; Tag
0x140021a96  call    cs:__imp_ExFreePoolWithTag
0x140021a9d  nop     dword ptr [rax+rax+00h]
0x140021aa2  mov     eax, ebx
0x140021aa4  mov     rbx, [rsp+38h+arg_0]
0x140021aa9  add     rsp, 20h
0x140021aad  pop     r14
0x140021aaf  pop     rdi
0x140021ab0  pop     rsi
0x140021ab1  retn
```
