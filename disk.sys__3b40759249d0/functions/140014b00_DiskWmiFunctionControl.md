# DiskWmiFunctionControl

- ea: `0x140014b00`
- end: `0x140014d03`
- name: `DiskWmiFunctionControl`
- size: `515`
- prototype: `__int64 __usercall@<rax>(PDEVICE_OBJECT DeviceObject@<rcx>, PIRP Irp@<rdx>, char)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400028b0`
- `0x140005244`
- `0x140005460`
- `0x140005520`
- `0x14001016c`
- `0x140014b00`

## import_xrefs

- `CLASSPNP!ClassWmiCompleteRequest` at `0x140014ce9`
- `CLASSPNP!ClassWmiCompleteRequest` at `0x140014ce9`

## pseudocode

```c
NTSTATUS __fastcall DiskWmiFunctionControl(PDEVICE_OBJECT DeviceObject, PIRP Irp, __int64 a3, int a4, char a5)
{
  struct _FUNCTIONAL_DEVICE_EXTENSION *DeviceExtension; // rsi
  NTSTATUS v6; // edi
  int v7; // r14d
  _DWORD *DriverData; // rbx
  int v11; // ecx
  int v12; // ecx
  const char *v13; // rax
  NTSTATUS v14; // eax
  int v15; // r8d
  int Timer_high; // edx

  DeviceExtension = (struct _FUNCTIONAL_DEVICE_EXTENSION *)DeviceObject->DeviceExtension;
  v6 = 0;
  v7 = a3;
  if ( a4 == 1 )
  {
    if ( a5 )
    {
      if ( (unsigned int)(a3 - 1) <= 2 || (_DWORD)a3 == 5 )
      {
        DriverData = DeviceExtension->CommonExtension.DriverData;
        v11 = DriverData[4];
        if ( v11 == 2 )
        {
          v6 = DiskEnableSmart(DeviceExtension);
          if ( v6 >= 0 )
            *((_BYTE *)DriverData + 22) = 1;
        }
        else
        {
          v12 = v11 - 1;
          if ( v12 && v12 != 2 )
            v6 = -1073741808;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_qqL(WPP_GLOBAL_Control->AttachedDevice, 33, a3, DeviceObject, Irp, v6);
        }
      }
      else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
             && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_qqds(WPP_GLOBAL_Control->AttachedDevice, 34, a3, (_DWORD)DeviceObject, (char)Irp, a3, (__int64)"Enabled");
      }
    }
  }
  else if ( !a4 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      v13 = "Enabled";
      if ( !a5 )
        v13 = "Disabled";
      WPP_SF_qqds(WPP_GLOBAL_Control->AttachedDevice, 35, a3, (_DWORD)DeviceObject, (char)Irp, a3, (__int64)v13);
    }
    if ( v7 == 4 )
    {
      if ( a5 )
      {
        v14 = DiskEnableDisableFailurePredictPolling(DeviceExtension);
        v6 = v14;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          Timer_high = HIDWORD(WPP_GLOBAL_Control->Timer);
          if ( (Timer_high & 0x40) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            WPP_SF_qqsL(
              WPP_GLOBAL_Control->AttachedDevice,
              Timer_high,
              v15,
              (_DWORD)DeviceObject,
              (char)Irp,
              (__int64)"DiskEnableSmartPolling",
              v14);
        }
      }
    }
  }
  return ClassWmiCompleteRequest(DeviceObject, Irp, v6, 0, 0);
}

```

## disassembly

```asm
0x140014b00  push    rbx
0x140014b02  push    rbp
0x140014b03  push    rsi
0x140014b04  push    rdi
0x140014b05  push    r14
0x140014b07  push    r15
0x140014b09  sub     rsp, 48h
0x140014b0d  mov     rsi, [rcx+40h]
0x140014b11  xor     edi, edi
0x140014b13  mov     r14d, r8d
0x140014b16  mov     r15, rdx
0x140014b19  mov     rbp, rcx
0x140014b1c  cmp     r9d, 1
0x140014b20  jnz     loc_140014C15
0x140014b26  cmp     [rsp+78h+arg_20], dil
0x140014b2e  jz      loc_140014CD8
0x140014b34  lea     eax, [r8-1]
0x140014b38  cmp     eax, 2
0x140014b3b  jbe     short loc_140014B9B
0x140014b3d  cmp     r8d, 5
0x140014b41  jz      short loc_140014B9B
0x140014b43  mov     rcx, cs:WPP_GLOBAL_Control
0x140014b4a  lea     rbx, WPP_GLOBAL_Control
0x140014b51  cmp     rcx, rbx
0x140014b54  jz      loc_140014CD8
0x140014b5a  mov     eax, [rcx+2Ch]
0x140014b5d  test    al, 40h
0x140014b5f  jz      loc_140014CD8
0x140014b65  cmp     byte ptr [rcx+29h], 4
0x140014b69  jb      loc_140014CD8
0x140014b6f  mov     rcx, [rcx+18h]
0x140014b73  lea     rax, aEnabled; "Enabled"
0x140014b7a  mov     [rsp+78h+var_48], rax
0x140014b7f  mov     edx, 22h ; '"'
0x140014b84  mov     dword ptr [rsp+78h+var_50], r8d
0x140014b89  mov     r9, rbp
0x140014b8c  mov     qword ptr [rsp+78h+PriorityBoost], r15
0x140014b91  call    WPP_SF_qqds
0x140014b96  jmp     loc_140014CD8
0x140014b9b  mov     rbx, [rsi+60h]
0x140014b9f  mov     ecx, [rbx+10h]
0x140014ba2  cmp     ecx, 2
0x140014ba5  jz      short loc_140014BB8
0x140014ba7  sub     ecx, 1
0x140014baa  jz      short loc_140014BCA
0x140014bac  cmp     ecx, 2
0x140014baf  jz      short loc_140014BCA
0x140014bb1  mov     edi, 0C0000010h
0x140014bb6  jmp     short loc_140014BCA
0x140014bb8  mov     rcx, rsi
0x140014bbb  call    DiskEnableSmart
0x140014bc0  mov     edi, eax
0x140014bc2  test    eax, eax
0x140014bc4  js      short loc_140014BCA
0x140014bc6  mov     byte ptr [rbx+16h], 1
0x140014bca  mov     rcx, cs:WPP_GLOBAL_Control
0x140014bd1  lea     rbx, WPP_GLOBAL_Control
0x140014bd8  cmp     rcx, rbx
0x140014bdb  jz      loc_140014CD8
0x140014be1  mov     eax, [rcx+2Ch]
0x140014be4  test    al, 40h
0x140014be6  jz      loc_140014CD8
0x140014bec  cmp     byte ptr [rcx+29h], 4
0x140014bf0  jb      loc_140014CD8
0x140014bf6  mov     rcx, [rcx+18h]
0x140014bfa  mov     edx, 21h ; '!'
0x140014bff  mov     dword ptr [rsp+78h+var_50], edi
0x140014c03  mov     r9, rbp
0x140014c06  mov     qword ptr [rsp+78h+PriorityBoost], r15
0x140014c0b  call    WPP_SF_qqL
0x140014c10  jmp     loc_140014CD8
0x140014c15  test    r9d, r9d
0x140014c18  jnz     loc_140014CD8
0x140014c1e  mov     rcx, cs:WPP_GLOBAL_Control
0x140014c25  lea     rbx, WPP_GLOBAL_Control
0x140014c2c  cmp     rcx, rbx
0x140014c2f  jz      short loc_140014C78
0x140014c31  mov     eax, [rcx+2Ch]
0x140014c34  test    al, 40h
0x140014c36  jz      short loc_140014C78
0x140014c38  cmp     byte ptr [rcx+29h], 4
0x140014c3c  jb      short loc_140014C78
0x140014c3e  cmp     [rsp+78h+arg_20], dil
0x140014c46  lea     rdx, aDisabled; "Disabled"
0x140014c4d  mov     rcx, [rcx+18h]
0x140014c51  lea     rax, aEnabled; "Enabled"
0x140014c58  cmovz   rax, rdx
0x140014c5c  mov     r9, rbp
0x140014c5f  mov     [rsp+78h+var_48], rax
0x140014c64  mov     edx, 23h ; '#'
0x140014c69  mov     dword ptr [rsp+78h+var_50], r14d
0x140014c6e  mov     qword ptr [rsp+78h+PriorityBoost], r15
0x140014c73  call    WPP_SF_qqds
0x140014c78  cmp     r14d, 4
0x140014c7c  jnz     short loc_140014CD8
0x140014c7e  cmp     [rsp+78h+arg_20], dil
0x140014c86  jz      short loc_140014CD8
0x140014c88  movzx   edx, [rsp+78h+arg_20]
0x140014c90  xor     r8d, r8d
0x140014c93  mov     rcx, rsi; FdoExtension
0x140014c96  call    DiskEnableDisableFailurePredictPolling
0x140014c9b  mov     edi, eax
0x140014c9d  mov     rcx, cs:WPP_GLOBAL_Control
0x140014ca4  cmp     rcx, rbx
0x140014ca7  jz      short loc_140014CD8
0x140014ca9  mov     edx, [rcx+2Ch]
0x140014cac  test    dl, 40h
0x140014caf  jz      short loc_140014CD8
0x140014cb1  cmp     [rcx+29h], r14b
0x140014cb5  jb      short loc_140014CD8
0x140014cb7  mov     rcx, [rcx+18h]
0x140014cbb  mov     r9, rbp
0x140014cbe  mov     dword ptr [rsp+78h+var_48], eax
0x140014cc2  lea     rax, aDiskenablesmar; "DiskEnableSmartPolling"
0x140014cc9  mov     [rsp+78h+var_50], rax
0x140014cce  mov     qword ptr [rsp+78h+PriorityBoost], r15
0x140014cd3  call    WPP_SF_qqsL
0x140014cd8  xor     r9d, r9d; BufferUsed
0x140014cdb  mov     [rsp+78h+PriorityBoost], 0; PriorityBoost
0x140014ce0  mov     r8d, edi; Status
0x140014ce3  mov     rdx, r15; Irp
0x140014ce6  mov     rcx, rbp; DeviceObject
0x140014ce9  call    cs:__imp_ClassWmiCompleteRequest
0x140014cf0  nop     dword ptr [rax+rax+00h]
0x140014cf5  add     rsp, 48h
0x140014cf9  pop     r15
0x140014cfb  pop     r14
0x140014cfd  pop     rdi
0x140014cfe  pop     rsi
0x140014cff  pop     rbp
0x140014d00  pop     rbx
0x140014d01  retn
```
