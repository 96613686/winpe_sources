# SC_DRIVE::DeleteMetadata(void)

- ea: `0x14000f5ac`
- end: `0x14000f6d9`
- name: `?DeleteMetadata@SC_DRIVE@@QEAAJXZ`
- size: `301`
- prototype: `__int64 __fastcall(SC_DRIVE *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400221e4`

## callees

- `0x14000a33c`
- `0x14000ebc8`
- `0x14000f180`
- `0x14000f5ac`
- `0x140011440`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000f6ba`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f6ba`

## pseudocode

```c
__int64 __fastcall SC_DRIVE::DeleteMetadata(SC_DRIVE *this)
{
  int PartitionTable; // eax
  SC_DISK_LAYOUT *v3; // rdi
  int v4; // ebx
  unsigned int Partition; // eax
  __int64 v6; // rbx
  unsigned int v7; // eax
  __int64 v8; // rbx
  struct _GUID v10; // [rsp+20h] [rbp-18h] BYREF
  PVOID P; // [rsp+48h] [rbp+10h] BYREF

  P = 0;
  PartitionTable = SC_DISK::ReadPartitionTable(this, (struct SC_DISK_LAYOUT **)&P);
  v3 = (SC_DISK_LAYOUT *)P;
  v4 = PartitionTable;
  if ( PartitionTable >= 0 )
  {
    v10 = PARTITION_SPACES_GUID;
    Partition = SC_DISK_LAYOUT::FindPartition((SC_DISK_LAYOUT *)P, &v10, 0xE7u);
    if ( Partition == -1 )
    {
      v4 = -1073741772;
    }
    else
    {
      v6 = 144LL * Partition;
      memset((char *)v3 + v6 + 48, 0, 0x90u);
      *(_DWORD *)((char *)v3 + v6 + 48) = *(_DWORD *)v3;
      *((_BYTE *)v3 + v6 + 76) = 1;
      v10 = (struct _GUID)PARTITION_SPACES_DATA_GUID;
      v7 = SC_DISK_LAYOUT::FindPartition(v3, &v10, 0xD7u);
      if ( v7 != -1 )
      {
        v8 = 144LL * v7;
        memset((char *)v3 + v8 + 48, 0, 0x90u);
        *(_DWORD *)((char *)v3 + v8 + 48) = *(_DWORD *)v3;
        *((_BYTE *)v3 + v8 + 76) = 1;
      }
      v4 = SC_DISK::WritePartitionTable(this, v3);
      if ( v4 >= 0 )
      {
        *((_DWORD *)this + 112) = 0;
        *((_QWORD *)this + 57) = 0;
        *((_QWORD *)this + 58) = 0;
      }
    }
  }
  if ( v3 )
    ExFreePoolWithTag(v3, 0);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14000f5ac  mov     rax, rsp
0x14000f5af  mov     [rax+8], rbx
0x14000f5b3  mov     [rax+18h], rsi
0x14000f5b7  push    rdi
0x14000f5b8  sub     rsp, 30h
0x14000f5bc  lea     rdx, [rax+10h]; struct SC_DISK_LAYOUT **
0x14000f5c0  mov     qword ptr [rax+10h], 0
0x14000f5c8  mov     rsi, rcx
0x14000f5cb  call    ?ReadPartitionTable@SC_DISK@@QEAAJPEAPEAVSC_DISK_LAYOUT@@@Z; SC_DISK::ReadPartitionTable(SC_DISK_LAYOUT * *)
0x14000f5d0  mov     rdi, [rsp+38h+P]
0x14000f5d5  mov     ebx, eax
0x14000f5d7  test    eax, eax
0x14000f5d9  js      loc_14000F6B0
0x14000f5df  movups  xmm0, xmmword ptr cs:PARTITION_SPACES_GUID.Data1
0x14000f5e6  mov     r8b, 0E7h; unsigned __int8
0x14000f5e9  lea     rdx, [rsp+38h+var_18]; struct _GUID
0x14000f5ee  mov     rcx, rdi; this
0x14000f5f1  movdqu  xmmword ptr [rsp+38h+var_18.Data1], xmm0
0x14000f5f7  call    ?FindPartition@SC_DISK_LAYOUT@@QEAAKU_GUID@@E@Z; SC_DISK_LAYOUT::FindPartition(_GUID,uchar)
0x14000f5fc  cmp     eax, 0FFFFFFFFh
0x14000f5ff  jnz     short loc_14000F60B
0x14000f601  mov     ebx, 0C0000034h
0x14000f606  jmp     loc_14000F6B0
0x14000f60b  mov     eax, eax
0x14000f60d  lea     rcx, [rdi+30h]
0x14000f611  xor     edx, edx; Val
0x14000f613  mov     r8d, 90h; Size
0x14000f619  lea     rbx, [rax+rax*8]
0x14000f61d  shl     rbx, 4
0x14000f621  add     rcx, rbx; void *
0x14000f624  call    memset
0x14000f629  mov     eax, [rdi]
0x14000f62b  lea     rdx, [rsp+38h+var_18]; struct _GUID
0x14000f630  mov     [rbx+rdi+30h], eax
0x14000f634  mov     r8b, 0D7h; unsigned __int8
0x14000f637  mov     byte ptr [rbx+rdi+4Ch], 1
0x14000f63c  mov     rcx, rdi; this
0x14000f63f  movups  xmm0, cs:PARTITION_SPACES_DATA_GUID
0x14000f646  movdqu  xmmword ptr [rsp+38h+var_18.Data1], xmm0
0x14000f64c  call    ?FindPartition@SC_DISK_LAYOUT@@QEAAKU_GUID@@E@Z; SC_DISK_LAYOUT::FindPartition(_GUID,uchar)
0x14000f651  cmp     eax, 0FFFFFFFFh
0x14000f654  jz      short loc_14000F67F
0x14000f656  mov     eax, eax
0x14000f658  lea     rcx, [rdi+30h]
0x14000f65c  xor     edx, edx; Val
0x14000f65e  mov     r8d, 90h; Size
0x14000f664  lea     rbx, [rax+rax*8]
0x14000f668  shl     rbx, 4
0x14000f66c  add     rcx, rbx; void *
0x14000f66f  call    memset
0x14000f674  mov     eax, [rdi]
0x14000f676  mov     [rbx+rdi+30h], eax
0x14000f67a  mov     byte ptr [rbx+rdi+4Ch], 1
0x14000f67f  mov     rdx, rdi; struct SC_DISK_LAYOUT *
0x14000f682  mov     rcx, rsi; this
0x14000f685  call    ?WritePartitionTable@SC_DISK@@QEAAJPEAVSC_DISK_LAYOUT@@@Z; SC_DISK::WritePartitionTable(SC_DISK_LAYOUT *)
0x14000f68a  mov     ebx, eax
0x14000f68c  test    eax, eax
0x14000f68e  js      short loc_14000F6B0
0x14000f690  mov     dword ptr [rsi+1C0h], 0
0x14000f69a  mov     qword ptr [rsi+1C8h], 0
0x14000f6a5  mov     qword ptr [rsi+1D0h], 0
0x14000f6b0  test    rdi, rdi
0x14000f6b3  jz      short loc_14000F6C6
0x14000f6b5  xor     edx, edx; Tag
0x14000f6b7  mov     rcx, rdi; P
0x14000f6ba  call    cs:__imp_ExFreePoolWithTag
0x14000f6c1  nop     dword ptr [rax+rax+00h]
0x14000f6c6  mov     rsi, [rsp+38h+arg_10]
0x14000f6cb  mov     eax, ebx
0x14000f6cd  mov     rbx, [rsp+38h+arg_0]
0x14000f6d2  add     rsp, 30h
0x14000f6d6  pop     rdi
0x14000f6d7  retn
```
