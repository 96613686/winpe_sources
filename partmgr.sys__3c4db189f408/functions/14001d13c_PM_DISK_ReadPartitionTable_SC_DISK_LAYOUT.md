# PM_DISK::ReadPartitionTable(SC_DISK_LAYOUT * *)

- ea: `0x14001d13c`
- end: `0x14001d199`
- name: `?ReadPartitionTable@PM_DISK@@QEAAJPEAPEAVSC_DISK_LAYOUT@@@Z`
- size: `93`
- prototype: `__int64 __fastcall(PM_DISK *__hidden this, struct SC_DISK_LAYOUT **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400066a0`

## callees

- `0x14000a33c`
- `0x14000f180`
- `0x14001d13c`

## pseudocode

```c
__int64 __fastcall PM_DISK::ReadPartitionTable(PM_DISK *this, struct SC_DISK_LAYOUT **a2)
{
  int v4; // esi
  struct SC_DISK_LAYOUT *v5; // rbx
  struct SC_DISK_LAYOUT *v7; // [rsp+58h] [rbp+10h] BYREF

  *a2 = 0;
  v7 = 0;
  v4 = SC_DISK::ReadPartitionTable(this, &v7);
  if ( v4 >= 0 )
  {
    v5 = v7;
    if ( (*((_DWORD *)this + 50) & 2) != 0 )
      SC_DISK::WritePartitionTable(this, v7);
    *a2 = v5;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14001d13c  push    rbx
0x14001d13e  push    rsi
0x14001d13f  push    rdi
0x14001d140  push    r14
0x14001d142  sub     rsp, 28h
0x14001d146  mov     r14, rdx
0x14001d149  mov     qword ptr [rdx], 0
0x14001d150  lea     rdx, [rsp+48h+arg_8]; struct SC_DISK_LAYOUT **
0x14001d155  mov     [rsp+48h+arg_8], 0
0x14001d15e  mov     rdi, rcx
0x14001d161  call    ?ReadPartitionTable@SC_DISK@@QEAAJPEAPEAVSC_DISK_LAYOUT@@@Z; SC_DISK::ReadPartitionTable(SC_DISK_LAYOUT * *)
0x14001d166  mov     esi, eax
0x14001d168  test    eax, eax
0x14001d16a  js      short loc_14001D18C
0x14001d16c  mov     r8d, [rdi+0C8h]
0x14001d173  mov     rbx, [rsp+48h+arg_8]
0x14001d178  test    r8b, 2
0x14001d17c  jz      short loc_14001D189
0x14001d17e  mov     rdx, rbx; struct SC_DISK_LAYOUT *
0x14001d181  mov     rcx, rdi; this
0x14001d184  call    ?WritePartitionTable@SC_DISK@@QEAAJPEAVSC_DISK_LAYOUT@@@Z; SC_DISK::WritePartitionTable(SC_DISK_LAYOUT *)
0x14001d189  mov     [r14], rbx
0x14001d18c  mov     eax, esi
0x14001d18e  add     rsp, 28h
0x14001d192  pop     r14
0x14001d194  pop     rdi
0x14001d195  pop     rsi
0x14001d196  pop     rbx
0x14001d197  retn
```
