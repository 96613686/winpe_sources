# PmCreateSpacesMetadata(_DEVICE_EXTENSION *,_DISK_SPACES_METADATA *)

- ea: `0x14002208c`
- end: `0x1400221de`
- name: `?PmCreateSpacesMetadata@@YAJPEAU_DEVICE_EXTENSION@@PEAU_DISK_SPACES_METADATA@@@Z`
- size: `338`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *, struct _DISK_SPACES_METADATA *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, installer_update`

## callers

- `0x14001d744`

## callees

- `0x14000df60`
- `0x14000f0f8`
- `0x14000f2a8`
- `0x14000f394`
- `0x14000f430`
- `0x14000f96c`
- `0x140010f20`
- `0x140011440`
- `0x140020240`
- `0x14002208c`

## pseudocode

```c
__int64 __fastcall PmCreateSpacesMetadata(struct _DEVICE_EXTENSION *a1, struct _DISK_SPACES_METADATA *a2)
{
  int Metadata; // ebx
  unsigned __int8 DriveHeaderVersion; // al
  __int128 v6; // xmm0
  __int16 v7; // cx
  __int128 v8; // xmm1
  __int64 v9; // rax
  __int128 v10; // xmm0
  __int64 v11; // rax
  unsigned __int64 v12; // r9
  unsigned __int8 v14; // [rsp+20h] [rbp-E0h]
  _QWORD v15[10]; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v16[74]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v17; // [rsp+2D0h] [rbp+1D0h]

  SC_DRIVE::SC_DRIVE((SC_DRIVE *)v16);
  v17 = 0;
  v16[0] = &PM_DRIVE::`vftable';
  memset(v15, 0, 0x48u);
  if ( *((_DWORD *)a2 + 1) < 0x20u )
  {
    Metadata = PM_DRIVE::Initialize((PM_DRIVE *)v16, a1);
    if ( Metadata >= 0 )
    {
      DriveHeaderVersion = ScGetDriveHeaderVersion(*((unsigned int *)a2 + 1));
      v6 = *(_OWORD *)((char *)a2 + 520);
      v7 = DriveHeaderVersion;
      v8 = *(_OWORD *)((char *)a2 + 536);
      WORD2(v15[4]) = *((_WORD *)a2 + 276);
      v9 = *((_QWORD *)a2 + 74);
      *(_OWORD *)((char *)v15 + 4) = v6;
      v15[7] = v9;
      v10 = *(_OWORD *)((char *)a2 + 572);
      v11 = *((_QWORD *)a2 + 75);
      LOWORD(v15[0]) = v7;
      v15[8] = v11;
      *(_OWORD *)((char *)&v15[2] + 4) = v8;
      *(_OWORD *)&v15[5] = v10;
      Metadata = SC_DRIVE::CreateMetadata(
                   (SC_DRIVE *)v16,
                   (unsigned __int16 *)a2 + 4,
                   (struct SC_DRIVE_HEADER *)v15,
                   v12,
                   v14);
      if ( Metadata >= 0 )
      {
        Metadata = SC_DISK::UpdateControl((SC_DISK *)v16);
        if ( Metadata >= 0 )
          Metadata = PmSendIO(*(PDEVICE_OBJECT *)(v17 + 8), 9u, 0, 0, 0);
      }
    }
  }
  else
  {
    Metadata = -1058602987;
  }
  v16[0] = &PM_DRIVE::`vftable';
  SC_DRIVE::~SC_DRIVE((SC_DRIVE *)v16);
  return (unsigned int)Metadata;
}

```

## disassembly

```asm
0x14002208c  push    rbp
0x14002208e  push    rbx
0x14002208f  push    rsi
0x140022090  push    rdi
0x140022091  lea     rbp, [rsp-1F8h]
0x140022099  sub     rsp, 2F8h
0x1400220a0  mov     rax, cs:__security_cookie
0x1400220a7  xor     rax, rsp
0x1400220aa  mov     [rbp+210h+var_30], rax
0x1400220b1  mov     rbx, rcx
0x1400220b4  mov     rdi, rdx
0x1400220b7  lea     rcx, [rbp+210h+var_290]; this
0x1400220bb  call    ??0SC_DRIVE@@QEAA@XZ; SC_DRIVE::SC_DRIVE(void)
0x1400220c0  xor     edx, edx; Val
0x1400220c2  mov     [rbp+210h+var_40], 0
0x1400220cd  lea     rsi, ??_7PM_DRIVE@@6B@; const PM_DRIVE::`vftable'
0x1400220d4  lea     rcx, [rsp+310h+var_2E0]; void *
0x1400220d9  mov     [rbp+210h+var_290], rsi
0x1400220dd  lea     r8d, [rdx+48h]; Size
0x1400220e1  call    memset
0x1400220e6  cmp     dword ptr [rdi+4], 20h ; ' '
0x1400220ea  jb      short loc_1400220F6
0x1400220ec  mov     ebx, 0C0E70015h
0x1400220f1  jmp     loc_1400221B3
0x1400220f6  mov     rdx, rbx; struct _DEVICE_EXTENSION *
0x1400220f9  lea     rcx, [rbp+210h+var_290]; this
0x1400220fd  call    ?Initialize@PM_DRIVE@@QEAAJPEAU_DEVICE_EXTENSION@@@Z; PM_DRIVE::Initialize(_DEVICE_EXTENSION *)
0x140022102  mov     ebx, eax
0x140022104  test    eax, eax
0x140022106  js      loc_1400221B3
0x14002210c  mov     ecx, [rdi+4]
0x14002210f  call    ?ScGetDriveHeaderVersion@@YAEW4_SC_VERSION@@@Z; ScGetDriveHeaderVersion(_SC_VERSION)
0x140022114  movups  xmm0, xmmword ptr [rdi+208h]
0x14002211b  movzx   ecx, al
0x14002211e  lea     rdx, [rdi+8]; unsigned __int16 *
0x140022122  movzx   eax, word ptr [rdi+228h]
0x140022129  lea     r8, [rsp+310h+var_2E0]; struct SC_DRIVE_HEADER *
0x14002212e  movups  xmm1, xmmword ptr [rdi+218h]
0x140022135  mov     [rsp+310h+var_2BC], ax
0x14002213a  mov     rax, [rdi+250h]
0x140022141  movdqu  [rsp+310h+var_2DC], xmm0
0x140022147  mov     [rsp+310h+var_2A8], rax
0x14002214c  movups  xmm0, xmmword ptr [rdi+23Ch]
0x140022153  mov     rax, [rdi+258h]
0x14002215a  mov     [rsp+310h+var_2E0], cx
0x14002215f  lea     rcx, [rbp+210h+var_290]; this
0x140022163  mov     [rsp+310h+var_2A0], rax
0x140022168  movdqu  [rsp+310h+var_2CC], xmm1
0x14002216e  movdqu  [rsp+310h+var_2B8], xmm0
0x140022174  call    ?CreateMetadata@SC_DRIVE@@QEAAJPEAGPEAVSC_DRIVE_HEADER@@_KE@Z; SC_DRIVE::CreateMetadata(ushort *,SC_DRIVE_HEADER *,unsigned __int64,uchar)
0x140022179  mov     ebx, eax
0x14002217b  test    eax, eax
0x14002217d  js      short loc_1400221B3
0x14002217f  lea     rcx, [rbp+210h+var_290]; this
0x140022183  call    ?UpdateControl@SC_DISK@@QEAAJXZ; SC_DISK::UpdateControl(void)
0x140022188  mov     ebx, eax
0x14002218a  test    eax, eax
0x14002218c  js      short loc_1400221B3
0x14002218e  mov     rcx, [rbp+210h+var_40]
0x140022195  xor     r9d, r9d; Length
0x140022198  xor     r8d, r8d; Buffer
0x14002219b  mov     qword ptr [rsp+310h+var_2F0], 0; PLARGE_INTEGER
0x1400221a4  mov     rcx, [rcx+8]; DeviceObject
0x1400221a8  lea     edx, [r9+9]; MajorFunction
0x1400221ac  call    ?PmSendIO@@YAJPEAU_DEVICE_OBJECT@@KPEAXKPEAT_LARGE_INTEGER@@@Z; PmSendIO(_DEVICE_OBJECT *,ulong,void *,ulong,_LARGE_INTEGER *)
0x1400221b1  mov     ebx, eax
0x1400221b3  lea     rcx, [rbp+210h+var_290]; this
0x1400221b7  mov     [rbp+210h+var_290], rsi
0x1400221bb  call    ??1SC_DRIVE@@UEAA@XZ; SC_DRIVE::~SC_DRIVE(void)
0x1400221c0  mov     eax, ebx
0x1400221c2  mov     rcx, [rbp+210h+var_30]
0x1400221c9  xor     rcx, rsp; StackCookie
0x1400221cc  call    __security_check_cookie
0x1400221d1  add     rsp, 2F8h
0x1400221d8  pop     rdi
0x1400221d9  pop     rsi
0x1400221da  pop     rbx
0x1400221db  pop     rbp
0x1400221dc  retn
```
