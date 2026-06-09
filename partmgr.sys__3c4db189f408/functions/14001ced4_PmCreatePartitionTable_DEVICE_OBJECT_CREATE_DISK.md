# PmCreatePartitionTable(_DEVICE_OBJECT *,_CREATE_DISK *)

- ea: `0x14001ced4`
- end: `0x14001cf6e`
- name: `?PmCreatePartitionTable@@YAJPEAU_DEVICE_OBJECT@@PEAU_CREATE_DISK@@@Z`
- size: `154`
- prototype: `int(struct _DEVICE_OBJECT *, struct _CREATE_DISK *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1400208c8`

## callees

- `0x140004b28`
- `0x14000ea44`
- `0x140010f20`
- `0x14001ced4`
- `0x140023da8`
- `0x1400246c8`

## pseudocode

```c
__int64 __fastcall PmCreatePartitionTable(struct _DEVICE_OBJECT *a1, struct _CREATE_DISK *a2)
{
  PDEVICE_OBJECT v3; // r9
  int PartitionTable; // ebx
  _QWORD v6[50]; // [rsp+20h] [rbp-1B8h] BYREF
  __int128 v7; // [rsp+1B0h] [rbp-28h]

  SC_DISK::SC_DISK((SC_DISK *)v6);
  v6[0] = &PM_DISK::`vftable';
  v7 = 0;
  PartitionTable = PM_DISK::Initialize((PM_DISK *)v6, v3, 1);
  if ( PartitionTable >= 0 )
    PartitionTable = SC_DISK::CreatePartitionTable((SC_DISK *)v6, a2);
  PM_DISK::~PM_DISK((PM_DISK *)v6);
  return (unsigned int)PartitionTable;
}

```

## disassembly

```asm
0x14001ced4  mov     [rsp+arg_10], rbx
0x14001ced9  push    rdi
0x14001ceda  sub     rsp, 1D0h
0x14001cee1  mov     rax, cs:__security_cookie
0x14001cee8  xor     rax, rsp
0x14001ceeb  mov     [rsp+1D8h+var_18], rax
0x14001cef3  mov     r9, rcx
0x14001cef6  mov     rdi, rdx
0x14001cef9  lea     rcx, [rsp+1D8h+var_1B8]; this
0x14001cefe  call    ??0SC_DISK@@QEAA@XZ; SC_DISK::SC_DISK(void)
0x14001cf03  lea     rcx, ??_7PM_DISK@@6B@; const PM_DISK::`vftable'
0x14001cf0a  xorps   xmm2, xmm2
0x14001cf0d  mov     [rsp+1D8h+var_1B8], rcx
0x14001cf12  mov     r8b, 1; unsigned __int8
0x14001cf15  lea     rcx, [rsp+1D8h+var_1B8]; this
0x14001cf1a  movdqa  [rsp+1D8h+var_28], xmm2
0x14001cf23  mov     rdx, r9; DeviceObject
0x14001cf26  call    ?Initialize@PM_DISK@@QEAAJPEAU_DEVICE_OBJECT@@E@Z; PM_DISK::Initialize(_DEVICE_OBJECT *,uchar)
0x14001cf2b  mov     ebx, eax
0x14001cf2d  test    eax, eax
0x14001cf2f  js      short loc_14001CF40
0x14001cf31  mov     rdx, rdi; struct _CREATE_DISK *
0x14001cf34  lea     rcx, [rsp+1D8h+var_1B8]; this
0x14001cf39  call    ?CreatePartitionTable@SC_DISK@@QEAAJPEAU_CREATE_DISK@@@Z; SC_DISK::CreatePartitionTable(_CREATE_DISK *)
0x14001cf3e  mov     ebx, eax
0x14001cf40  lea     rcx, [rsp+1D8h+var_1B8]; this
0x14001cf45  call    ??1PM_DISK@@UEAA@XZ; PM_DISK::~PM_DISK(void)
0x14001cf4a  mov     eax, ebx
0x14001cf4c  mov     rcx, [rsp+1D8h+var_18]
0x14001cf54  xor     rcx, rsp; StackCookie
0x14001cf57  call    __security_check_cookie
0x14001cf5c  mov     rbx, [rsp+1D8h+arg_10]
0x14001cf64  add     rsp, 1D0h
0x14001cf6b  pop     rdi
0x14001cf6c  retn
```
