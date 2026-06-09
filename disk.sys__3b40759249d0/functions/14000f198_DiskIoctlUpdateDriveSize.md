# DiskIoctlUpdateDriveSize

- ea: `0x14000f198`
- end: `0x14000f323`
- name: `DiskIoctlUpdateDriveSize`
- size: `395`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1400014a0`

## callees

- `0x140004078`
- `0x14000431c`
- `0x140005bf0`
- `0x140005d00`
- `0x14000f198`

## import_xrefs

- `ntoskrnl!IoReportTargetDeviceChangeAsynchronous` at `0x14000f2f3`
- `ntoskrnl!IoReportTargetDeviceChangeAsynchronous` at `0x14000f2f3`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000f1e0`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000f1e0`
- `CLASSPNP!ClassReadDriveCapacity` at `0x14000f278`
- `CLASSPNP!ClassReadDriveCapacity` at `0x14000f278`

## pseudocode

```c
__int64 __fastcall DiskIoctlUpdateDriveSize(PDEVICE_OBJECT DeviceObject, __int64 a2)
{
  char *DeviceExtension; // rsi
  __int64 v3; // rbp
  __int64 v6; // r14
  NTSTATUS DriveCapacity; // eax
  unsigned int v9; // ebx
  __int64 v10; // rax
  _OWORD NotificationStructure[2]; // [rsp+30h] [rbp-58h] BYREF
  __int64 v12; // [rsp+50h] [rbp-38h]

  DeviceExtension = (char *)DeviceObject->DeviceExtension;
  v3 = *(_QWORD *)(a2 + 184);
  v6 = *((_QWORD *)DeviceExtension + 12);
  memset(NotificationStructure, 0, sizeof(NotificationStructure));
  v12 = 0;
  if ( KeGetCurrentIrql() >= 2u )
    return 3221225800LL;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 96, WPP_0d021951613e35be7880fae860fb7f50_Traceguids, DeviceObject, a2);
  }
  if ( *(_DWORD *)(v3 + 8) >= 0x18u )
  {
    DriveCapacity = ClassReadDriveCapacity(DeviceObject);
    *(_DWORD *)(v6 + 4) = DriveCapacity;
    v9 = DriveCapacity;
    if ( DriveCapacity >= 0 )
    {
      memmove(*(void **)(a2 + 24), DeviceExtension + 552, 0x18u);
      v10 = *(_QWORD *)(a2 + 24);
      if ( !*(_DWORD *)(v10 + 20) )
        *(_DWORD *)(v10 + 20) = 512;
      v9 = 0;
      *(_QWORD *)(a2 + 56) = 24;
      LODWORD(NotificationStructure[0]) = 2359297;
      *(GUID *)((char *)NotificationStructure + 4) = GUID_IO_DISK_LAYOUT_CHANGE;
      *((_QWORD *)&NotificationStructure[1] + 1) = 0;
      LODWORD(v12) = -1;
      IoReportTargetDeviceChangeAsynchronous(*((PDEVICE_OBJECT *)DeviceExtension + 64), NotificationStructure, 0, 0);
    }
    return v9;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 97, WPP_0d021951613e35be7880fae860fb7f50_Traceguids);
    }
    return 3221225507LL;
  }
}

```

## disassembly

```asm
0x14000f198  mov     [rsp+arg_10], rbx
0x14000f19d  push    rbp
0x14000f19e  push    rsi
0x14000f19f  push    rdi
0x14000f1a0  push    r12
0x14000f1a2  push    r14
0x14000f1a4  sub     rsp, 60h
0x14000f1a8  mov     rax, cs:__security_cookie
0x14000f1af  xor     rax, rsp
0x14000f1b2  mov     [rsp+88h+var_30], rax
0x14000f1b7  mov     rsi, [rcx+40h]
0x14000f1bb  xorps   xmm0, xmm0
0x14000f1be  mov     rbp, [rdx+0B8h]
0x14000f1c5  xor     eax, eax
0x14000f1c7  mov     rdi, rdx
0x14000f1ca  mov     rbx, rcx
0x14000f1cd  mov     r14, [rsi+60h]
0x14000f1d1  movups  [rsp+88h+NotificationStructure], xmm0
0x14000f1d6  mov     [rsp+88h+var_38], rax
0x14000f1db  movups  [rsp+88h+var_48], xmm0
0x14000f1e0  call    cs:__imp_KeGetCurrentIrql
0x14000f1e7  nop     dword ptr [rax+rax+00h]
0x14000f1ec  cmp     al, 2
0x14000f1ee  jb      short loc_14000F1FA
0x14000f1f0  mov     eax, 0C0000148h
0x14000f1f5  jmp     loc_14000F301
0x14000f1fa  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f201  lea     r12, WPP_GLOBAL_Control
0x14000f208  cmp     rcx, r12
0x14000f20b  jz      short loc_14000F237
0x14000f20d  mov     eax, [rcx+2Ch]
0x14000f210  test    al, 10h
0x14000f212  jz      short loc_14000F237
0x14000f214  cmp     byte ptr [rcx+29h], 4
0x14000f218  jb      short loc_14000F237
0x14000f21a  mov     rcx, [rcx+18h]
0x14000f21e  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x14000f225  mov     edx, 60h ; '`'
0x14000f22a  mov     [rsp+88h+var_68], rdi
0x14000f22f  mov     r9, rbx
0x14000f232  call    WPP_SF_qq
0x14000f237  cmp     dword ptr [rbp+8], 18h
0x14000f23b  jnb     short loc_14000F275
0x14000f23d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f244  cmp     rcx, r12
0x14000f247  jz      short loc_14000F26B
0x14000f249  mov     eax, [rcx+2Ch]
0x14000f24c  test    al, 10h
0x14000f24e  jz      short loc_14000F26B
0x14000f250  cmp     byte ptr [rcx+29h], 2
0x14000f254  jb      short loc_14000F26B
0x14000f256  mov     rcx, [rcx+18h]
0x14000f25a  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x14000f261  mov     edx, 61h ; 'a'
0x14000f266  call    WPP_SF_
0x14000f26b  mov     eax, 0C0000023h
0x14000f270  jmp     loc_14000F301
0x14000f275  mov     rcx, rbx; DeviceObject
0x14000f278  call    cs:__imp_ClassReadDriveCapacity
0x14000f27f  nop     dword ptr [rax+rax+00h]
0x14000f284  mov     [r14+4], eax
0x14000f288  mov     ebx, eax
0x14000f28a  test    eax, eax
0x14000f28c  js      short loc_14000F2FF
0x14000f28e  mov     rcx, [rdi+18h]; void *
0x14000f292  lea     rdx, [rsi+228h]; Src
0x14000f299  mov     r8d, 18h; Size
0x14000f29f  call    memmove
0x14000f2a4  mov     rax, [rdi+18h]
0x14000f2a8  cmp     dword ptr [rax+14h], 0
0x14000f2ac  jnz     short loc_14000F2B5
0x14000f2ae  mov     dword ptr [rax+14h], 200h
0x14000f2b5  movups  xmm0, xmmword ptr cs:GUID_IO_DISK_LAYOUT_CHANGE.Data1
0x14000f2bc  xor     ebx, ebx
0x14000f2be  mov     qword ptr [rdi+38h], 18h
0x14000f2c6  mov     dword ptr [rsp+88h+NotificationStructure], 240001h
0x14000f2ce  lea     rdx, [rsp+88h+NotificationStructure]; NotificationStructure
0x14000f2d3  movdqu  [rsp+88h+NotificationStructure+4], xmm0
0x14000f2d9  mov     qword ptr [rsp+88h+var_48+8], rbx
0x14000f2de  xor     r9d, r9d; Context
0x14000f2e1  mov     dword ptr [rsp+88h+var_38], 0FFFFFFFFh
0x14000f2e9  xor     r8d, r8d; Callback
0x14000f2ec  mov     rcx, [rsi+200h]; PhysicalDeviceObject
0x14000f2f3  call    cs:__imp_IoReportTargetDeviceChangeAsynchronous
0x14000f2fa  nop     dword ptr [rax+rax+00h]
0x14000f2ff  mov     eax, ebx
0x14000f301  mov     rcx, [rsp+88h+var_30]
0x14000f306  xor     rcx, rsp; StackCookie
0x14000f309  call    __security_check_cookie
0x14000f30e  mov     rbx, [rsp+88h+arg_10]
0x14000f316  add     rsp, 60h
0x14000f31a  pop     r14
0x14000f31c  pop     r12
0x14000f31e  pop     rdi
0x14000f31f  pop     rsi
0x14000f320  pop     rbp
0x14000f321  retn
```
