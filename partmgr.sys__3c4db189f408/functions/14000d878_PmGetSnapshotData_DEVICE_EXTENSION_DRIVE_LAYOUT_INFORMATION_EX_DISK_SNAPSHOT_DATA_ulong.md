# PmGetSnapshotData(_DEVICE_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX *,_DISK_SNAPSHOT_DATA * *,ulong *)

- ea: `0x14000d878`
- end: `0x14000da95`
- name: `?PmGetSnapshotData@@YAJPEAU_DEVICE_EXTENSION@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@PEAPEAU_DISK_SNAPSHOT_DATA@@PEAK@Z`
- size: `541`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *, struct _DRIVE_LAYOUT_INFORMATION_EX *, struct _DISK_SNAPSHOT_DATA **, unsigned int *)`
- caller_count: `4`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x14001ccb4`
- `0x1400214fc`
- `0x140021970`
- `0x140021c90`

## callees

- `0x14000d878`
- `0x140011140`
- `0x14001c20c`
- `0x140021abc`
- `0x140021b3c`
- `0x140023310`
- `0x1400241b8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000d9d7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000da33`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d9d7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000da33`
- `ntoskrnl!ExAllocatePool2` at `0x14000d91b`
- `ntoskrnl!ExAllocatePool2` at `0x14000d9b0`
- `ntoskrnl!ExAllocatePool2` at `0x14000da10`
- `ntoskrnl!ExAllocatePool2` at `0x14000d91b`
- `ntoskrnl!ExAllocatePool2` at `0x14000d9b0`
- `ntoskrnl!ExAllocatePool2` at `0x14000da10`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d8d8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000da71`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d8d8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000da71`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d8b4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000da59`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d8b4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000da59`

## string_xrefs

- `0x14000d9ee`: `SnapshotDataCache`

## pseudocode

```c
__int64 __fastcall PmGetSnapshotData(
        struct _DEVICE_EXTENSION *a1,
        struct _DRIVE_LAYOUT_INFORMATION_EX *a2,
        struct _DISK_SNAPSHOT_DATA **a3,
        unsigned int *a4)
{
  KSPIN_LOCK *v4; // r12
  unsigned int v6; // ebx
  struct _DISK_SNAPSHOT_DATA **v8; // r15
  KIRQL v10; // al
  unsigned __int16 *v11; // rdi
  int v12; // eax
  unsigned int v13; // esi
  struct _STORAGE_DEVICE_ID_DESCRIPTOR *v14; // rcx
  unsigned int v15; // eax
  unsigned __int16 *v16; // rax
  unsigned __int16 *v17; // rbp
  size_t v18; // rsi
  struct _DISK_SNAPSHOT_DATA *Pool2; // rax
  struct _DISK_SNAPSHOT_DATA *v20; // rbp
  KIRQL v21; // al
  unsigned int v23; // [rsp+60h] [rbp+8h] BYREF
  struct _DISK_SNAPSHOT_DATA **v24; // [rsp+70h] [rbp+18h]
  void *Src; // [rsp+78h] [rbp+20h] BYREF

  v24 = a3;
  v4 = (KSPIN_LOCK *)((char *)a1 + 112);
  v23 = 0;
  v6 = 0;
  *a3 = 0;
  *a4 = 0;
  v8 = a3;
  v10 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 14);
  Src = (void *)*((_QWORD *)a1 + 142);
  v11 = (unsigned __int16 *)Src;
  *((_QWORD *)a1 + 142) = 0;
  KeReleaseSpinLock(v4, v10);
  if ( v11 )
  {
LABEL_17:
    v18 = *((unsigned int *)v11 + 3);
    Pool2 = (struct _DISK_SNAPSHOT_DATA *)ExAllocatePool2(66, v18, 1146318160);
    v20 = Pool2;
    if ( Pool2 )
    {
      memmove(Pool2, v11, v18);
      *v8 = v20;
      *a4 = v18;
      v21 = KeAcquireSpinLockRaiseToDpc(v4);
      *((_QWORD *)a1 + 142) = v11;
      KeReleaseSpinLock(v4, v21);
      return v6;
    }
    goto LABEL_18;
  }
  v12 = PmReadSnapshotData(a1, a2, (struct _DISK_SNAPSHOT_DATA **)&Src, &v23);
  v6 = v12;
  if ( v12 == -1073741275 )
  {
    v13 = 112;
    v11 = (unsigned __int16 *)ExAllocatePool2(66, 112, 1146318160);
    if ( !v11 )
      goto LABEL_18;
    v6 = 0;
  }
  else
  {
    v11 = (unsigned __int16 *)Src;
    if ( v12 < 0 )
      goto LABEL_19;
    v13 = v23;
    if ( PmVerifySnapshotData((PUCHAR)Src, v23, 1u) )
      goto LABEL_8;
  }
  PmInitializeSnapshotData((PUCHAR)v11, v13);
LABEL_8:
  if ( *((_DWORD *)v11 + 5) == 1 )
  {
    v14 = (struct _STORAGE_DEVICE_ID_DESCRIPTOR *)*((_QWORD *)a1 + 31);
    if ( !v14 )
    {
      v6 = -1073741275;
      goto LABEL_19;
    }
    if ( PmLookupId(v14, (char *)v11 + *((unsigned int *)v11 + 24), v11[50]) )
      *((_DWORD *)v11 + 5) = 0;
  }
  v15 = *((_DWORD *)v11 + 3);
  if ( v13 <= v15 )
    goto LABEL_16;
  v13 = *((_DWORD *)v11 + 3);
  v16 = (unsigned __int16 *)ExAllocatePool2(66, v15, 1146318160);
  v17 = v16;
  if ( v16 )
  {
    memmove(v16, v11, v13);
    ExFreePoolWithTag(v11, 0);
    v8 = v24;
    v11 = v17;
LABEL_16:
    PmSetDeviceParameterBinary(a1, L"SnapshotDataCache", v11, v13);
    goto LABEL_17;
  }
LABEL_18:
  v6 = -1073741670;
LABEL_19:
  if ( v11 )
    ExFreePoolWithTag(v11, 0);
  return v6;
}

```

## disassembly

```asm
0x14000d878  mov     [rsp+arg_8], rbx
0x14000d87d  mov     [rsp+arg_10], r8
0x14000d882  push    rbp
0x14000d883  push    rsi
0x14000d884  push    rdi
0x14000d885  push    r12
0x14000d887  push    r13
0x14000d889  push    r14
0x14000d88b  push    r15
0x14000d88d  sub     rsp, 20h
0x14000d891  lea     r12, [rcx+70h]
0x14000d895  mov     [rsp+58h+arg_0], 0
0x14000d89d  mov     r14, rcx
0x14000d8a0  xor     ebx, ebx
0x14000d8a2  mov     rcx, r12; SpinLock
0x14000d8a5  mov     [r8], rbx
0x14000d8a8  mov     r13, r9
0x14000d8ab  mov     [r9], ebx
0x14000d8ae  mov     r15, r8
0x14000d8b1  mov     rsi, rdx
0x14000d8b4  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000d8bb  nop     dword ptr [rax+rax+00h]
0x14000d8c0  mov     rdi, [r14+470h]
0x14000d8c7  mov     rcx, r12; SpinLock
0x14000d8ca  mov     dl, al; NewIrql
0x14000d8cc  mov     [rsp+58h+Src], rdi
0x14000d8d1  mov     [r14+470h], rbx
0x14000d8d8  call    cs:__imp_KeReleaseSpinLock
0x14000d8df  nop     dword ptr [rax+rax+00h]
0x14000d8e4  test    rdi, rdi
0x14000d8e7  jnz     loc_14000DA00
0x14000d8ed  lea     r9, [rsp+58h+arg_0]; unsigned int *
0x14000d8f2  mov     rdx, rsi; struct _DRIVE_LAYOUT_INFORMATION_EX *
0x14000d8f5  lea     r8, [rsp+58h+Src]; struct _DISK_SNAPSHOT_DATA **
0x14000d8fa  mov     rcx, r14; struct _DEVICE_EXTENSION *
0x14000d8fd  call    ?PmReadSnapshotData@@YAJPEAU_DEVICE_EXTENSION@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@PEAPEAU_DISK_SNAPSHOT_DATA@@PEAK@Z; PmReadSnapshotData(_DEVICE_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX *,_DISK_SNAPSHOT_DATA * *,ulong *)
0x14000d902  mov     ebp, 0C0000225h
0x14000d907  mov     ebx, eax
0x14000d909  cmp     eax, ebp
0x14000d90b  jnz     short loc_14000D937
0x14000d90d  lea     esi, [rdi+70h]
0x14000d910  mov     r8d, 44536D50h
0x14000d916  mov     edx, esi
0x14000d918  lea     ecx, [rdi+42h]
0x14000d91b  call    cs:__imp_ExAllocatePool2
0x14000d922  nop     dword ptr [rax+rax+00h]
0x14000d927  mov     rdi, rax
0x14000d92a  test    rax, rax
0x14000d92d  jz      loc_14000DA24
0x14000d933  xor     ebx, ebx
0x14000d935  jmp     short loc_14000D959
0x14000d937  mov     rdi, [rsp+58h+Src]
0x14000d93c  test    eax, eax
0x14000d93e  js      loc_14000DA29
0x14000d944  mov     esi, [rsp+58h+arg_0]
0x14000d948  mov     r8b, 1; unsigned __int8
0x14000d94b  mov     edx, esi; unsigned int
0x14000d94d  mov     rcx, rdi; Buffer
0x14000d950  call    ?PmVerifySnapshotData@@YAEPEAU_DISK_SNAPSHOT_DATA@@KE@Z; PmVerifySnapshotData(_DISK_SNAPSHOT_DATA *,ulong,uchar)
0x14000d955  test    al, al
0x14000d957  jnz     short loc_14000D963
0x14000d959  mov     edx, esi; Size
0x14000d95b  mov     rcx, rdi; Buffer
0x14000d95e  call    ?PmInitializeSnapshotData@@YAXPEAU_DISK_SNAPSHOT_DATA@@K@Z; PmInitializeSnapshotData(_DISK_SNAPSHOT_DATA *,ulong)
0x14000d963  cmp     dword ptr [rdi+14h], 1
0x14000d967  jnz     short loc_14000D997
0x14000d969  mov     rcx, [r14+0F8h]; struct _STORAGE_DEVICE_ID_DESCRIPTOR *
0x14000d970  test    rcx, rcx
0x14000d973  jnz     short loc_14000D97C
0x14000d975  mov     ebx, ebp
0x14000d977  jmp     loc_14000DA29
0x14000d97c  mov     edx, [rdi+60h]
0x14000d97f  movzx   r8d, word ptr [rdi+64h]; unsigned __int16
0x14000d984  add     rdx, rdi; void *
0x14000d987  call    ?PmLookupId@@YAEPEAU_STORAGE_DEVICE_ID_DESCRIPTOR@@PEAXG@Z; PmLookupId(_STORAGE_DEVICE_ID_DESCRIPTOR *,void *,ushort)
0x14000d98c  test    al, al
0x14000d98e  jz      short loc_14000D997
0x14000d990  mov     dword ptr [rdi+14h], 0
0x14000d997  mov     eax, [rdi+0Ch]
0x14000d99a  cmp     esi, eax
0x14000d99c  jbe     short loc_14000D9EB
0x14000d99e  mov     r8d, 44536D50h
0x14000d9a4  mov     edx, eax
0x14000d9a6  mov     ecx, 42h ; 'B'
0x14000d9ab  mov     esi, eax
0x14000d9ad  mov     r15d, eax
0x14000d9b0  call    cs:__imp_ExAllocatePool2
0x14000d9b7  nop     dword ptr [rax+rax+00h]
0x14000d9bc  mov     rbp, rax
0x14000d9bf  test    rax, rax
0x14000d9c2  jz      short loc_14000DA24
0x14000d9c4  mov     r8d, r15d; Size
0x14000d9c7  mov     rdx, rdi; Src
0x14000d9ca  mov     rcx, rax; void *
0x14000d9cd  call    memmove
0x14000d9d2  xor     edx, edx; Tag
0x14000d9d4  mov     rcx, rdi; P
0x14000d9d7  call    cs:__imp_ExFreePoolWithTag
0x14000d9de  nop     dword ptr [rax+rax+00h]
0x14000d9e3  mov     r15, [rsp+58h+arg_10]
0x14000d9e8  mov     rdi, rbp
0x14000d9eb  mov     r9d, esi; unsigned int
0x14000d9ee  lea     rdx, aSnapshotdataca; "SnapshotDataCache"
0x14000d9f5  mov     r8, rdi; void *
0x14000d9f8  mov     rcx, r14; struct _DEVICE_EXTENSION *
0x14000d9fb  call    ?PmSetDeviceParameterBinary@@YAJPEAU_DEVICE_EXTENSION@@PEAGPEAXK@Z; PmSetDeviceParameterBinary(_DEVICE_EXTENSION *,ushort *,void *,ulong)
0x14000da00  mov     esi, [rdi+0Ch]
0x14000da03  mov     r8d, 44536D50h
0x14000da09  mov     edx, esi
0x14000da0b  mov     ecx, 42h ; 'B'
0x14000da10  call    cs:__imp_ExAllocatePool2
0x14000da17  nop     dword ptr [rax+rax+00h]
0x14000da1c  mov     rbp, rax
0x14000da1f  test    rax, rax
0x14000da22  jnz     short loc_14000DA41
0x14000da24  mov     ebx, 0C000009Ah
0x14000da29  test    rdi, rdi
0x14000da2c  jz      short loc_14000DA7D
0x14000da2e  xor     edx, edx; Tag
0x14000da30  mov     rcx, rdi; P
0x14000da33  call    cs:__imp_ExFreePoolWithTag
0x14000da3a  nop     dword ptr [rax+rax+00h]
0x14000da3f  jmp     short loc_14000DA7D
0x14000da41  mov     r8, rsi; Size
0x14000da44  mov     rdx, rdi; Src
0x14000da47  mov     rcx, rbp; void *
0x14000da4a  call    memmove
0x14000da4f  mov     rcx, r12; SpinLock
0x14000da52  mov     [r15], rbp
0x14000da55  mov     [r13+0], esi
0x14000da59  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000da60  nop     dword ptr [rax+rax+00h]
0x14000da65  mov     rcx, r12; SpinLock
0x14000da68  mov     [r14+470h], rdi
0x14000da6f  mov     dl, al; NewIrql
0x14000da71  call    cs:__imp_KeReleaseSpinLock
0x14000da78  nop     dword ptr [rax+rax+00h]
0x14000da7d  mov     eax, ebx
0x14000da7f  mov     rbx, [rsp+58h+arg_8]
0x14000da84  add     rsp, 20h
0x14000da88  pop     r15
0x14000da8a  pop     r14
0x14000da8c  pop     r13
0x14000da8e  pop     r12
0x14000da90  pop     rdi
0x14000da91  pop     rsi
0x14000da92  pop     rbp
0x14000da93  retn
```
