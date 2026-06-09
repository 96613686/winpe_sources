# SC_DISK::ReadPartitionTable(SC_DISK_LAYOUT * *)

- ea: `0x14000a33c`
- end: `0x14000a3c8`
- name: `?ReadPartitionTable@SC_DISK@@QEAAJPEAPEAVSC_DISK_LAYOUT@@@Z`
- size: `140`
- prototype: `__int64 __fastcall(SC_DISK *__hidden this, struct SC_DISK_LAYOUT **)`
- caller_count: `5`
- callee_count: `6`
- tags: ``

## callers

- `0x14000efb8`
- `0x14000f430`
- `0x14000f5ac`
- `0x14000f7f8`
- `0x14001d13c`

## callees

- `0x14000510c`
- `0x1400058a4`
- `0x140006190`
- `0x140006384`
- `0x14000a33c`
- `0x1400100ac`

## pseudocode

```c
__int64 __fastcall SC_DISK::ReadPartitionTable(SC_DISK *this, struct SC_DISK_LAYOUT **a2)
{
  int v2; // r8d
  int v5; // r8d
  __int64 result; // rax
  unsigned __int8 v7; // r8
  SC_DISK *v8; // [rsp+30h] [rbp+8h] BYREF

  v2 = *((_DWORD *)this + 64);
  *a2 = 0;
  if ( !v2 )
    goto LABEL_8;
  v5 = v2 - 1;
  if ( v5 )
  {
    if ( v5 != 1 )
      return 3221225659LL;
    v8 = this;
    return SC_RAW::ReadPartitionTable((SC_RAW *)&v8, a2, 1u);
  }
  v8 = this;
  result = SC_GPT::ReadPartitionTable((SC_GPT *)&v8, a2);
  if ( (int)result < 0 )
  {
    result = SC_DISK::ResetPartitionCache(this);
    if ( (int)result >= 0 )
    {
LABEL_8:
      SC_MBR::Initialize((SC_MBR *)&v8, this);
      return SC_MBR::ReadPartitionTable(&v8, a2, v7);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000a33c  mov     [rsp+arg_8], rbx
0x14000a341  push    rdi
0x14000a342  sub     rsp, 20h
0x14000a346  mov     r8d, [rcx+100h]
0x14000a34d  mov     rdi, rdx
0x14000a350  mov     qword ptr [rdx], 0
0x14000a357  mov     rbx, rcx
0x14000a35a  test    r8d, r8d
0x14000a35d  jz      short loc_14000A3A2
0x14000a35f  sub     r8d, 1
0x14000a363  jz      short loc_14000A383
0x14000a365  cmp     r8d, 1
0x14000a369  jz      short loc_14000A372
0x14000a36b  mov     eax, 0C00000BBh
0x14000a370  jmp     short loc_14000A3BC
0x14000a372  lea     rcx, [rsp+28h+arg_0]; this
0x14000a377  mov     [rsp+28h+arg_0], rbx
0x14000a37c  call    ?ReadPartitionTable@SC_RAW@@QEAAJPEAPEAVSC_DISK_LAYOUT@@@Z; SC_RAW::ReadPartitionTable(SC_DISK_LAYOUT * *)
0x14000a381  jmp     short loc_14000A3BC
0x14000a383  lea     rcx, [rsp+28h+arg_0]; this
0x14000a388  mov     [rsp+28h+arg_0], rbx
0x14000a38d  call    ?ReadPartitionTable@SC_GPT@@QEAAJPEAPEAVSC_DISK_LAYOUT@@@Z; SC_GPT::ReadPartitionTable(SC_DISK_LAYOUT * *)
0x14000a392  test    eax, eax
0x14000a394  jns     short loc_14000A3BC
0x14000a396  mov     rcx, rbx; this
0x14000a399  call    ?ResetPartitionCache@SC_DISK@@QEAAJXZ; SC_DISK::ResetPartitionCache(void)
0x14000a39e  test    eax, eax
0x14000a3a0  js      short loc_14000A3BC
0x14000a3a2  mov     rdx, rbx; struct SC_DISK *
0x14000a3a5  lea     rcx, [rsp+28h+arg_0]; this
0x14000a3aa  call    ?Initialize@SC_MBR@@QEAAXPEAVSC_DISK@@@Z; SC_MBR::Initialize(SC_DISK *)
0x14000a3af  lea     rcx, [rsp+28h+arg_0]; this
0x14000a3b4  mov     rdx, rdi; struct SC_DISK_LAYOUT **
0x14000a3b7  call    ?ReadPartitionTable@SC_MBR@@QEAAJPEAPEAVSC_DISK_LAYOUT@@@Z; SC_MBR::ReadPartitionTable(SC_DISK_LAYOUT * *)
0x14000a3bc  mov     rbx, [rsp+28h+arg_8]
0x14000a3c1  add     rsp, 20h
0x14000a3c5  pop     rdi
0x14000a3c6  retn
```
