# PmWritePartitionTable(_DEVICE_OBJECT *,_DRIVE_LAYOUT_INFORMATION_EX *)

- ea: `0x14001d090`
- end: `0x14001d136`
- name: `?PmWritePartitionTable@@YAJPEAU_DEVICE_OBJECT@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z`
- size: `166`
- prototype: `int(struct _DEVICE_OBJECT *, struct _DRIVE_LAYOUT_INFORMATION_EX *)`
- caller_count: `5`
- callee_count: `6`
- tags: ``

## callers

- `0x14000c730`
- `0x14000dbd0`
- `0x14001c3d8`
- `0x140020afc`
- `0x1400214fc`

## callees

- `0x140004b28`
- `0x14000f180`
- `0x140010f20`
- `0x14001d090`
- `0x140023da8`
- `0x1400246c8`

## pseudocode

```c
__int64 __fastcall PmWritePartitionTable(struct _DEVICE_OBJECT *a1, struct _DRIVE_LAYOUT_INFORMATION_EX *a2)
{
  struct _DEVICE_OBJECT *v3; // r9
  bool v4; // cf
  int v5; // ebx
  _QWORD v7[50]; // [rsp+20h] [rbp-1B8h] BYREF
  __int128 v8; // [rsp+1B0h] [rbp-28h]

  SC_DISK::SC_DISK((SC_DISK *)v7);
  v4 = a2->PartitionStyle < 2;
  v7[0] = &PM_DISK::`vftable';
  v8 = 0;
  if ( v4 )
  {
    v5 = PM_DISK::Initialize((PM_DISK *)v7, v3, 1);
    if ( v5 >= 0 )
      v5 = SC_DISK::WritePartitionTable((SC_DISK *)v7, (struct SC_DISK_LAYOUT *)a2);
  }
  else
  {
    v5 = -1073741637;
  }
  PM_DISK::~PM_DISK((PM_DISK *)v7);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14001d090  mov     [rsp+arg_10], rbx
0x14001d095  push    rdi
0x14001d096  sub     rsp, 1D0h
0x14001d09d  mov     rax, cs:__security_cookie
0x14001d0a4  xor     rax, rsp
0x14001d0a7  mov     [rsp+1D8h+var_18], rax
0x14001d0af  mov     r9, rcx
0x14001d0b2  mov     rdi, rdx
0x14001d0b5  lea     rcx, [rsp+1D8h+var_1B8]; this
0x14001d0ba  call    ??0SC_DISK@@QEAA@XZ; SC_DISK::SC_DISK(void)
0x14001d0bf  cmp     dword ptr [rdi], 2
0x14001d0c2  lea     rcx, ??_7PM_DISK@@6B@; const PM_DISK::`vftable'
0x14001d0c9  xorps   xmm2, xmm2
0x14001d0cc  mov     [rsp+1D8h+var_1B8], rcx
0x14001d0d1  movdqa  [rsp+1D8h+var_28], xmm2
0x14001d0da  jb      short loc_14001D0E3
0x14001d0dc  mov     ebx, 0C00000BBh
0x14001d0e1  jmp     short loc_14001D108
0x14001d0e3  mov     r8b, 1; unsigned __int8
0x14001d0e6  lea     rcx, [rsp+1D8h+var_1B8]; this
0x14001d0eb  mov     rdx, r9; DeviceObject
0x14001d0ee  call    ?Initialize@PM_DISK@@QEAAJPEAU_DEVICE_OBJECT@@E@Z; PM_DISK::Initialize(_DEVICE_OBJECT *,uchar)
0x14001d0f3  mov     ebx, eax
0x14001d0f5  test    eax, eax
0x14001d0f7  js      short loc_14001D108
0x14001d0f9  mov     rdx, rdi; struct SC_DISK_LAYOUT *
0x14001d0fc  lea     rcx, [rsp+1D8h+var_1B8]; this
0x14001d101  call    ?WritePartitionTable@SC_DISK@@QEAAJPEAVSC_DISK_LAYOUT@@@Z; SC_DISK::WritePartitionTable(SC_DISK_LAYOUT *)
0x14001d106  mov     ebx, eax
0x14001d108  lea     rcx, [rsp+1D8h+var_1B8]; this
0x14001d10d  call    ??1PM_DISK@@UEAA@XZ; PM_DISK::~PM_DISK(void)
0x14001d112  mov     eax, ebx
0x14001d114  mov     rcx, [rsp+1D8h+var_18]
0x14001d11c  xor     rcx, rsp; StackCookie
0x14001d11f  call    __security_check_cookie
0x14001d124  mov     rbx, [rsp+1D8h+arg_10]
0x14001d12c  add     rsp, 1D0h
0x14001d133  pop     rdi
0x14001d134  retn
```
