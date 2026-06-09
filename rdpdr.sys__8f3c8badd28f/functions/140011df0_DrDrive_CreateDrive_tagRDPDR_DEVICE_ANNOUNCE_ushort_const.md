# DrDrive::CreateDrive(tagRDPDR_DEVICE_ANNOUNCE *,ushort const *)

- ea: `0x140011df0`
- end: `0x140011ee7`
- name: `?CreateDrive@DrDrive@@QEAAJPEAUtagRDPDR_DEVICE_ANNOUNCE@@PEBG@Z`
- size: `247`
- prototype: `__int64 __fastcall(DrDrive *__hidden this, struct tagRDPDR_DEVICE_ANNOUNCE *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, installer_update`

## callers

- `0x140012020`

## callees

- `0x140001e30`
- `0x1400027b0`
- `0x140003188`
- `0x14000324c`
- `0x140011df0`
- `0x140011ef0`

## pseudocode

```c
__int64 __fastcall DrDrive::CreateDrive(DrDrive *this, struct tagRDPDR_DEVICE_ANNOUNCE *a2, const unsigned __int16 *a3)
{
  unsigned int DriveAnnounceEvent; // ebx
  struct tagRDPDR_DRIVEDEVICE_SUB *v7; // rax
  struct tagRDPDR_DRIVEDEVICE_SUB *v8; // rdi
  unsigned int v10; // [rsp+68h] [rbp+20h] BYREF

  v10 = 0;
  DriveAnnounceEvent = DrDrive::CreateDriveAnnounceEvent(this, a2, 0, 0, &qword_140008DC8, &v10);
  if ( DriveAnnounceEvent == -1073741789 )
  {
    v7 = (struct tagRDPDR_DRIVEDEVICE_SUB *)operator new(v10, 0x40u);
    v8 = v7;
    if ( v7 )
    {
      DriveAnnounceEvent = DrDrive::CreateDriveAnnounceEvent(this, a2, v7, v10, a3, 0);
      if ( DriveAnnounceEvent )
        operator delete(v8);
      else
        return (unsigned int)RDPDYN_DispatchNewDevMgmtEvent(v8, *(_DWORD *)(*((_QWORD *)this + 4) + 1128LL), 6u, 0);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_83886b54412a34bbe371408c37660ab5_Traceguids);
      return (unsigned int)-1073741801;
    }
  }
  return DriveAnnounceEvent;
}

```

## disassembly

```asm
0x140011df0  mov     r11, rsp
0x140011df3  mov     [r11+8], rbx
0x140011df7  mov     [r11+10h], rbp
0x140011dfb  push    rsi
0x140011dfc  push    rdi
0x140011dfd  push    r14
0x140011dff  sub     rsp, 30h
0x140011e03  lea     rax, [r11+20h]
0x140011e07  mov     [rsp+48h+arg_18], 0
0x140011e0f  mov     [r11-20h], rax
0x140011e13  mov     r14, r8
0x140011e16  lea     rax, qword_140008DC8
0x140011e1d  xor     r9d, r9d; unsigned int
0x140011e20  xor     r8d, r8d; struct tagRDPDR_DRIVEDEVICE_SUB *
0x140011e23  mov     [r11-28h], rax
0x140011e27  mov     rbp, rdx
0x140011e2a  mov     rsi, rcx
0x140011e2d  call    ?CreateDriveAnnounceEvent@DrDrive@@QEAAJPEAUtagRDPDR_DEVICE_ANNOUNCE@@PEAUtagRDPDR_DRIVEDEVICE_SUB@@KPEBGPEAK@Z; DrDrive::CreateDriveAnnounceEvent(tagRDPDR_DEVICE_ANNOUNCE *,tagRDPDR_DRIVEDEVICE_SUB *,ulong,ushort const *,ulong *)
0x140011e32  mov     ebx, eax
0x140011e34  cmp     eax, 0C0000023h
0x140011e39  jnz     loc_140011ED1
0x140011e3f  mov     ecx, [rsp+48h+arg_18]; unsigned __int64
0x140011e43  mov     edx, 40h ; '@'; unsigned __int64
0x140011e48  call    ??2@YAPEAX_K0@Z; operator new(unsigned __int64,unsigned __int64)
0x140011e4d  mov     rdi, rax
0x140011e50  test    rax, rax
0x140011e53  jnz     short loc_140011E88
0x140011e55  mov     rcx, cs:WPP_GLOBAL_Control
0x140011e5c  lea     rax, WPP_GLOBAL_Control
0x140011e63  cmp     rcx, rax
0x140011e66  jz      short loc_140011E81
0x140011e68  cmp     byte ptr [rcx+29h], 2
0x140011e6c  jb      short loc_140011E81
0x140011e6e  mov     rcx, [rcx+18h]
0x140011e72  lea     edx, [rdi+0Eh]
0x140011e75  lea     r8, WPP_83886b54412a34bbe371408c37660ab5_Traceguids
0x140011e7c  call    WPP_SF_
0x140011e81  mov     ebx, 0C0000017h
0x140011e86  jmp     short loc_140011ED1
0x140011e88  mov     r9d, [rsp+48h+arg_18]; unsigned int
0x140011e8d  mov     r8, rdi; struct tagRDPDR_DRIVEDEVICE_SUB *
0x140011e90  mov     [rsp+48h+var_20], 0; unsigned int *
0x140011e99  mov     rdx, rbp; struct tagRDPDR_DEVICE_ANNOUNCE *
0x140011e9c  mov     rcx, rsi; this
0x140011e9f  mov     [rsp+48h+var_28], r14; unsigned __int16 *
0x140011ea4  call    ?CreateDriveAnnounceEvent@DrDrive@@QEAAJPEAUtagRDPDR_DEVICE_ANNOUNCE@@PEAUtagRDPDR_DRIVEDEVICE_SUB@@KPEBGPEAK@Z; DrDrive::CreateDriveAnnounceEvent(tagRDPDR_DEVICE_ANNOUNCE *,tagRDPDR_DRIVEDEVICE_SUB *,ulong,ushort const *,ulong *)
0x140011ea9  mov     ebx, eax
0x140011eab  mov     rcx, rdi; void *
0x140011eae  test    eax, eax
0x140011eb0  jz      short loc_140011EB9
0x140011eb2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140011eb7  jmp     short loc_140011ED1
0x140011eb9  mov     rdx, [rsi+20h]
0x140011ebd  xor     r9d, r9d; struct DrDevice *
0x140011ec0  mov     edx, [rdx+468h]; unsigned int
0x140011ec6  lea     r8d, [r9+6]; unsigned int
0x140011eca  call    RDPDYN_DispatchNewDevMgmtEvent
0x140011ecf  mov     ebx, eax
0x140011ed1  mov     rbp, [rsp+48h+arg_8]
0x140011ed6  mov     eax, ebx
0x140011ed8  mov     rbx, [rsp+48h+arg_0]
0x140011edd  add     rsp, 30h
0x140011ee1  pop     r14
0x140011ee3  pop     rdi
0x140011ee4  pop     rsi
0x140011ee5  retn
```
