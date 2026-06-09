# SC_DRIVE::CreateMetadata(ushort *,SC_DRIVE_HEADER *,unsigned __int64,uchar)

- ea: `0x14000f430`
- end: `0x14000f5a4`
- name: `?CreateMetadata@SC_DRIVE@@QEAAJPEAGPEAVSC_DRIVE_HEADER@@_KE@Z`
- size: `372`
- prototype: `__int64 __fastcall(SC_DRIVE *__hidden this, unsigned __int16 *, struct SC_DRIVE_HEADER *, unsigned __int64, unsigned __int8)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x14002208c`

## callees

- `0x14000a33c`
- `0x14000e864`
- `0x14000ebc8`
- `0x14000f180`
- `0x14000f430`
- `0x14000f7f8`
- `0x14000f98c`
- `0x14000fa54`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000f47b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f588`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f47b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f588`

## pseudocode

```c
__int64 __fastcall SC_DRIVE::CreateMetadata(SC_DRIVE *this, unsigned __int16 *a2, struct SC_DRIVE_HEADER *a3)
{
  int PartitionTable; // ebx
  unsigned __int8 v7; // r8
  struct _GUID v8; // xmm1
  struct SC_DISK_LAYOUT *v9; // rdi
  unsigned int Partition; // eax
  unsigned __int64 v12; // [rsp+20h] [rbp-38h]
  unsigned __int8 v13; // [rsp+28h] [rbp-30h]
  struct _GUID v14; // [rsp+40h] [rbp-18h] BYREF
  PVOID P; // [rsp+A8h] [rbp+50h] BYREF

  P = 0;
  PartitionTable = SC_DISK::ReadPartitionTable(this, (struct SC_DISK_LAYOUT **)&P);
  if ( PartitionTable < 0 )
    goto LABEL_11;
  if ( *((_DWORD *)this + 64) == 2 )
  {
    ExFreePoolWithTag(P, 0);
    P = 0;
    PartitionTable = SC_DRIVE::InitializePartitionTable(this, (struct SC_DISK_LAYOUT **)&P);
    if ( PartitionTable < 0 )
    {
LABEL_11:
      v9 = (struct SC_DISK_LAYOUT *)P;
      goto LABEL_12;
    }
    v8 = PARTITION_SPACES_GUID;
  }
  else
  {
    v8 = PARTITION_SPACES_GUID;
    v9 = (struct SC_DISK_LAYOUT *)P;
    v14 = PARTITION_SPACES_GUID;
    if ( SC_DISK_LAYOUT::FindPartition((SC_DISK_LAYOUT *)P, &v14, 0xE7u) != -1 )
    {
      PartitionTable = -1073741771;
      goto LABEL_12;
    }
  }
  v14 = v8;
  PartitionTable = SC_DISK::AddPartition(this, &v14, v7, a2, v12, v13, (struct SC_DISK_LAYOUT **)&P);
  if ( PartitionTable < 0 )
    goto LABEL_11;
  v9 = (struct SC_DISK_LAYOUT *)P;
  v14 = PARTITION_SPACES_GUID;
  Partition = SC_DISK_LAYOUT::FindPartition((SC_DISK_LAYOUT *)P, &v14, 0xE7u);
  *((_DWORD *)this + 112) = *((_DWORD *)v9 + 36 * Partition + 18);
  *((_QWORD *)this + 57) = *((_QWORD *)v9 + 18 * Partition + 7);
  *((_QWORD *)this + 58) = *((_QWORD *)v9 + 18 * Partition + 8);
  PartitionTable = SC_DRIVE::ZeroMetadata(this);
  if ( PartitionTable >= 0 )
  {
    PartitionTable = SC_DRIVE::WriteHeader(this, a3);
    if ( PartitionTable >= 0 )
      PartitionTable = SC_DISK::WritePartitionTable(this, v9);
  }
LABEL_12:
  if ( v9 )
    ExFreePoolWithTag(v9, 0);
  return (unsigned int)PartitionTable;
}

```

## disassembly

```asm
0x14000f430  mov     [rsp-30h+P], r9
0x14000f435  push    rbp
0x14000f436  push    rbx
0x14000f437  push    rsi
0x14000f438  push    rdi
0x14000f439  push    r14
0x14000f43b  push    r15
0x14000f43d  mov     rbp, rsp
0x14000f440  sub     rsp, 58h
0x14000f444  mov     r15, rdx
0x14000f447  mov     [rbp+P], 0
0x14000f44f  lea     rdx, [rbp+P]; struct SC_DISK_LAYOUT **
0x14000f453  mov     r14, r8
0x14000f456  mov     rsi, rcx
0x14000f459  call    ?ReadPartitionTable@SC_DISK@@QEAAJPEAPEAVSC_DISK_LAYOUT@@@Z; SC_DISK::ReadPartitionTable(SC_DISK_LAYOUT * *)
0x14000f45e  mov     ebx, eax
0x14000f460  test    eax, eax
0x14000f462  js      loc_14000F57A
0x14000f468  cmp     dword ptr [rsi+100h], 2
0x14000f46f  jnz     loc_14000F54B
0x14000f475  mov     rcx, [rbp+P]; P
0x14000f479  xor     edx, edx; Tag
0x14000f47b  call    cs:__imp_ExFreePoolWithTag
0x14000f482  nop     dword ptr [rax+rax+00h]
0x14000f487  lea     rdx, [rbp+P]; struct SC_DISK_LAYOUT **
0x14000f48b  mov     [rbp+P], 0
0x14000f493  mov     rcx, rsi; this
0x14000f496  call    ?InitializePartitionTable@SC_DRIVE@@AEAAJPEAPEAVSC_DISK_LAYOUT@@@Z; SC_DRIVE::InitializePartitionTable(SC_DISK_LAYOUT * *)
0x14000f49b  mov     ebx, eax
0x14000f49d  test    eax, eax
0x14000f49f  js      loc_14000F57A
0x14000f4a5  movups  xmm1, xmmword ptr cs:PARTITION_SPACES_GUID.Data1
0x14000f4ac  lea     rax, [rbp+P]
0x14000f4b0  mov     r9, r15; unsigned __int16 *
0x14000f4b3  lea     rdx, [rbp+var_18]; struct _GUID
0x14000f4b7  mov     [rsp+58h+var_28], rax; struct SC_DISK_LAYOUT **
0x14000f4bc  mov     rcx, rsi; this
0x14000f4bf  movdqu  xmmword ptr [rbp+var_18.Data1], xmm1
0x14000f4c4  call    ?AddPartition@SC_DISK@@QEAAJU_GUID@@EPEBG_KEPEAPEAVSC_DISK_LAYOUT@@@Z; SC_DISK::AddPartition(_GUID,uchar,ushort const *,unsigned __int64,uchar,SC_DISK_LAYOUT * *)
0x14000f4c9  mov     ebx, eax
0x14000f4cb  test    eax, eax
0x14000f4cd  js      loc_14000F57A
0x14000f4d3  movups  xmm0, xmmword ptr cs:PARTITION_SPACES_GUID.Data1
0x14000f4da  mov     rdi, [rbp+P]
0x14000f4de  lea     rdx, [rbp+var_18]; struct _GUID
0x14000f4e2  mov     r8b, 0E7h; unsigned __int8
0x14000f4e5  mov     rcx, rdi; this
0x14000f4e8  movdqu  xmmword ptr [rbp+var_18.Data1], xmm0
0x14000f4ed  call    ?FindPartition@SC_DISK_LAYOUT@@QEAAKU_GUID@@E@Z; SC_DISK_LAYOUT::FindPartition(_GUID,uchar)
0x14000f4f2  mov     eax, eax
0x14000f4f4  lea     rcx, [rax+rax*8]
0x14000f4f8  add     rcx, rcx
0x14000f4fb  mov     eax, [rdi+rcx*8+48h]
0x14000f4ff  mov     [rsi+1C0h], eax
0x14000f505  mov     rax, [rdi+rcx*8+38h]
0x14000f50a  mov     [rsi+1C8h], rax
0x14000f511  mov     rax, [rdi+rcx*8+40h]
0x14000f516  mov     rcx, rsi; this
0x14000f519  mov     [rsi+1D0h], rax
0x14000f520  call    ?ZeroMetadata@SC_DRIVE@@QEAAJXZ; SC_DRIVE::ZeroMetadata(void)
0x14000f525  mov     ebx, eax
0x14000f527  test    eax, eax
0x14000f529  js      short loc_14000F57E
0x14000f52b  mov     rdx, r14; struct SC_DRIVE_HEADER *
0x14000f52e  mov     rcx, rsi; this
0x14000f531  call    ?WriteHeader@SC_DRIVE@@QEAAJPEAVSC_DRIVE_HEADER@@@Z; SC_DRIVE::WriteHeader(SC_DRIVE_HEADER *)
0x14000f536  mov     ebx, eax
0x14000f538  test    eax, eax
0x14000f53a  js      short loc_14000F57E
0x14000f53c  mov     rdx, rdi; struct SC_DISK_LAYOUT *
0x14000f53f  mov     rcx, rsi; this
0x14000f542  call    ?WritePartitionTable@SC_DISK@@QEAAJPEAVSC_DISK_LAYOUT@@@Z; SC_DISK::WritePartitionTable(SC_DISK_LAYOUT *)
0x14000f547  mov     ebx, eax
0x14000f549  jmp     short loc_14000F57E
0x14000f54b  movups  xmm1, xmmword ptr cs:PARTITION_SPACES_GUID.Data1
0x14000f552  mov     rdi, [rbp+P]
0x14000f556  lea     rdx, [rbp+var_18]; struct _GUID
0x14000f55a  mov     r8b, 0E7h; unsigned __int8
0x14000f55d  mov     rcx, rdi; this
0x14000f560  movdqu  xmmword ptr [rbp+var_18.Data1], xmm1
0x14000f565  call    ?FindPartition@SC_DISK_LAYOUT@@QEAAKU_GUID@@E@Z; SC_DISK_LAYOUT::FindPartition(_GUID,uchar)
0x14000f56a  cmp     eax, 0FFFFFFFFh
0x14000f56d  jz      loc_14000F4AC
0x14000f573  mov     ebx, 0C0000035h
0x14000f578  jmp     short loc_14000F57E
0x14000f57a  mov     rdi, [rbp+P]
0x14000f57e  test    rdi, rdi
0x14000f581  jz      short loc_14000F594
0x14000f583  xor     edx, edx; Tag
0x14000f585  mov     rcx, rdi; P
0x14000f588  call    cs:__imp_ExFreePoolWithTag
0x14000f58f  nop     dword ptr [rax+rax+00h]
0x14000f594  mov     eax, ebx
0x14000f596  add     rsp, 58h
0x14000f59a  pop     r15
0x14000f59c  pop     r14
0x14000f59e  pop     rdi
0x14000f59f  pop     rsi
0x14000f5a0  pop     rbx
0x14000f5a1  pop     rbp
0x14000f5a2  retn
```
