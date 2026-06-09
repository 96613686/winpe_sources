# DiskSetSpecialHacks

- ea: `0x14000fb50`
- end: `0x14000fc41`
- name: `DiskSetSpecialHacks`
- size: `241`
- prototype: `void __fastcall(PFUNCTIONAL_DEVICE_EXTENSION FdoExtension, ULONG_PTR Data)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1400034a0`
- `0x14000fb50`

## pseudocode

```c
void __fastcall DiskSetSpecialHacks(PFUNCTIONAL_DEVICE_EXTENSION FdoExtension, ULONG_PTR Data)
{
  PDEVICE_OBJECT DeviceObject; // rsi
  char v3; // di

  DeviceObject = FdoExtension->DeviceObject;
  v3 = Data;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 42, WPP_0d021951613e35be7880fae860fb7f50_Traceguids, Data);
  }
  if ( (v3 & 1) != 0 )
    FdoExtension->SrbFlags &= ~2u;
  if ( (v3 & 2) != 0 )
    FdoExtension->SrbFlags |= 8u;
  if ( (v3 & 4) != 0 )
    FdoExtension->ScanForSpecialFlags |= 1u;
  if ( (v3 & 8) != 0 )
    FdoExtension->ScanForSpecialFlags |= 0x10u;
  if ( (v3 & 0x10) != 0 )
    FdoExtension->ScanForSpecialFlags |= 0x20u;
  if ( (DeviceObject->Characteristics & 1) != 0 && (v3 & 0x20) != 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 43, WPP_0d021951613e35be7880fae860fb7f50_Traceguids, DeviceObject);
    }
    FdoExtension->DeviceFlags |= 4u;
  }
}

```

## disassembly

```asm
0x14000fb50  push    rbx
0x14000fb52  push    rsi
0x14000fb53  push    rdi
0x14000fb54  push    r15
0x14000fb56  sub     rsp, 28h
0x14000fb5a  mov     rsi, [rcx+8]
0x14000fb5e  mov     rdi, rdx
0x14000fb61  mov     rbx, rcx
0x14000fb64  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fb6b  lea     r15, WPP_GLOBAL_Control
0x14000fb72  cmp     rcx, r15
0x14000fb75  jz      short loc_14000FB9E
0x14000fb77  test    dword ptr [rcx+2Ch], 100h
0x14000fb7e  jz      short loc_14000FB9E
0x14000fb80  cmp     byte ptr [rcx+29h], 4
0x14000fb84  jb      short loc_14000FB9E
0x14000fb86  mov     rcx, [rcx+18h]
0x14000fb8a  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x14000fb91  mov     edx, 2Ah ; '*'
0x14000fb96  mov     r9, rdi
0x14000fb99  call    WPP_SF_q
0x14000fb9e  test    dil, 1
0x14000fba2  jz      short loc_14000FBAB
0x14000fba4  and     dword ptr [rbx+250h], 0FFFFFFFDh
0x14000fbab  test    dil, 2
0x14000fbaf  jz      short loc_14000FBB8
0x14000fbb1  or      dword ptr [rbx+250h], 8
0x14000fbb8  test    dil, 4
0x14000fbbc  jz      short loc_14000FBC5
0x14000fbbe  or      dword ptr [rbx+36Ch], 1
0x14000fbc5  test    dil, 8
0x14000fbc9  jz      short loc_14000FBD2
0x14000fbcb  or      dword ptr [rbx+36Ch], 10h
0x14000fbd2  test    dil, 10h
0x14000fbd6  jz      short loc_14000FBDF
0x14000fbd8  or      dword ptr [rbx+36Ch], 20h
0x14000fbdf  test    byte ptr [rsi+34h], 1
0x14000fbe3  setnz   cl
0x14000fbe6  test    dil, 20h
0x14000fbea  setnz   al
0x14000fbed  test    al, cl
0x14000fbef  jz      short loc_14000FC36
0x14000fbf1  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fbf8  cmp     rcx, r15
0x14000fbfb  jz      short loc_14000FC24
0x14000fbfd  test    dword ptr [rcx+2Ch], 100h
0x14000fc04  jz      short loc_14000FC24
0x14000fc06  cmp     byte ptr [rcx+29h], 4
0x14000fc0a  jb      short loc_14000FC24
0x14000fc0c  mov     rcx, [rcx+18h]
0x14000fc10  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x14000fc17  mov     edx, 2Bh ; '+'
0x14000fc1c  mov     r9, rsi
0x14000fc1f  call    WPP_SF_q
0x14000fc24  movzx   eax, word ptr [rbx+280h]
0x14000fc2b  or      ax, 4
0x14000fc2f  mov     [rbx+280h], ax
0x14000fc36  add     rsp, 28h
0x14000fc3a  pop     r15
0x14000fc3c  pop     rdi
0x14000fc3d  pop     rsi
0x14000fc3e  pop     rbx
0x14000fc3f  retn
```
