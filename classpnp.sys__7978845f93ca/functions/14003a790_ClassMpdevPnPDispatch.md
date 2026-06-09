# ClassMpdevPnPDispatch

- ea: `0x14003a790`
- end: `0x14003ab08`
- name: `ClassMpdevPnPDispatch`
- size: `888`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `0`
- callee_count: `16`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x14001fc38`
- `0x14002249c`
- `0x140022614`
- `0x14002675c`
- `0x14003a790`
- `0x14003abd0`
- `0x14003ac04`
- `0x14003ae28`
- `0x14003af24`
- `0x14003b148`
- `0x14003b364`
- `0x14003b63c`
- `0x14003e430`
- `0x14003e470`
- `0x14005c620`
- `0x14005cce4`

## import_xrefs

- `ntoskrnl!IoGetActivityIdIrp` at `0x14003a822`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14003a822`
- `ntoskrnl!IofCompleteRequest` at `0x14003a8ec`
- `ntoskrnl!IofCompleteRequest` at `0x14003a8ec`

## pseudocode

```c
NTSTATUS __fastcall ClassMpdevPnPDispatch(PDEVICE_OBJECT DeviceObject, PIRP Irp, __int64 a3)
{
  _QWORD *DeviceExtension; // rsi
  _IO_STACK_LOCATION *CurrentStackLocation; // r14
  int v7; // ebp
  int v8; // edx
  int v9; // ecx
  int v10; // ecx
  int v12; // ecx
  void (__fastcall *v13)(_QWORD, PDEVICE_OBJECT, __int64); // rax
  __int128 v14; // [rsp+40h] [rbp-38h] BYREF

  DeviceExtension = DeviceObject->DeviceExtension;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v14 = 0;
  v7 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qqDq(
      WPP_GLOBAL_Control->AttachedDevice,
      WPP_GLOBAL_Control,
      a3,
      DeviceObject,
      Irp,
      CurrentStackLocation->MinorFunction,
      DeviceExtension[66]);
  }
  if ( ClassPnPETWEnabled )
  {
    if ( (int)IoGetActivityIdIrp(Irp, &v14) >= 0 )
    {
      v7 = 1;
      if ( (BYTE2(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) & 0x10) != 0 )
        McTemplateK0qpddp_EtwWriteTransfer(
          v9,
          v8,
          (unsigned int)&v14,
          *((_DWORD *)DeviceExtension + 144),
          (char)Irp,
          CurrentStackLocation->MinorFunction,
          0,
          DeviceObject,
          v14);
    }
  }
  if ( *((_BYTE *)DeviceExtension + 582) == 2 )
  {
    v10 = (int)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_a63e98891b663a71e40facba1bb231b0_Traceguids, DeviceObject);
    }
    Irp->IoStatus.Status = -1073741632;
    if ( v7 )
    {
      if ( (BYTE2(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) & 0x10) != 0 )
        McTemplateK0qpd_EtwWriteTransfer(
          v10,
          (unsigned int)EventPnpRequestComplete,
          (unsigned int)&v14,
          *((_DWORD *)DeviceExtension + 144),
          (char)Irp,
          192);
    }
    IofCompleteRequest(Irp, 0);
    return -1073741632;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_Dq(
      WPP_GLOBAL_Control->AttachedDevice,
      15,
      WPP_a63e98891b663a71e40facba1bb231b0_Traceguids,
      CurrentStackLocation->MinorFunction,
      DeviceObject);
  }
  switch ( CurrentStackLocation->MinorFunction )
  {
    case 0u:
      return ClasspMpdevStartDevice(DeviceObject, Irp);
    case 1u:
      return ClasspMpdevQueryRemove((__int64)DeviceObject, Irp, a3);
    case 2u:
      return ClasspMpdevRemoveDevice(DeviceObject, Irp);
    case 3u:
      Irp->IoStatus.Status = 0;
      if ( *((_BYTE *)DeviceExtension + 580) == 1 )
        return ClasspMpdevCancelRemove((__int64)DeviceObject, Irp);
      if ( v7 && (BYTE2(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) & 0x10) != 0 )
        McTemplateK0qpd_EtwWriteTransfer(
          0,
          (unsigned int)EventPnpRequestComplete,
          (unsigned int)&v14,
          *((_DWORD *)DeviceExtension + 144),
          (char)Irp,
          0);
      return ClassMpdevSendToNextDevice(DeviceObject, Irp);
    case 9u:
      return ClasspMpdevQueryCapabilities(DeviceObject, Irp);
    case 0x14u:
      return ClassMpdevQueryPnpDeviceState(DeviceObject, Irp);
    case 0x17u:
      v12 = (int)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_a63e98891b663a71e40facba1bb231b0_Traceguids, DeviceObject);
      }
      *((_BYTE *)DeviceExtension + 582) = 23;
      Irp->IoStatus.Status = 0;
      if ( *((_BYTE *)DeviceExtension + 583) )
      {
        if ( *((_DWORD *)DeviceExtension + 136) )
        {
          v13 = (void (__fastcall *)(_QWORD, PDEVICE_OBJECT, __int64))DeviceExtension[70];
          if ( v13 )
          {
            LOBYTE(a3) = 23;
            v13(DeviceExtension[67], DeviceObject, a3);
          }
        }
      }
      if ( v7 && (BYTE2(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) & 0x10) != 0 )
        McTemplateK0qpd_EtwWriteTransfer(
          v12,
          (unsigned int)EventPnpRequestComplete,
          (unsigned int)&v14,
          *((_DWORD *)DeviceExtension + 144),
          (char)Irp,
          Irp->IoStatus.Status);
      return ClassMpdevSendToNextDevice(DeviceObject, Irp);
  }
  if ( v7 && (BYTE2(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) & 0x10) != 0 )
    McTemplateK0qpd_EtwWriteTransfer(
      CurrentStackLocation->MinorFunction - 20,
      (unsigned int)EventPnpRequestComplete,
      (unsigned int)&v14,
      *((_DWORD *)DeviceExtension + 144),
      (char)Irp,
      Irp->IoStatus.Status);
  return ClasspMpdevDefaultDispatch(DeviceObject, Irp);
}

```

## disassembly

```asm
0x14003a790  mov     r11, rsp
0x14003a793  mov     [r11+18h], rbx
0x14003a797  mov     [r11+20h], rbp
0x14003a79b  push    rsi
0x14003a79c  push    rdi
0x14003a79d  push    r14
0x14003a79f  sub     rsp, 60h
0x14003a7a3  mov     rax, cs:__security_cookie
0x14003a7aa  xor     rax, rsp
0x14003a7ad  mov     [rsp+78h+var_28], rax
0x14003a7b2  mov     rsi, [rcx+40h]
0x14003a7b6  xorps   xmm0, xmm0
0x14003a7b9  mov     r14, [rdx+0B8h]
0x14003a7c0  mov     rbx, rdx
0x14003a7c3  movups  [rsp+78h+var_38], xmm0
0x14003a7c8  mov     rdi, rcx
0x14003a7cb  xor     ebp, ebp
0x14003a7cd  mov     rdx, cs:WPP_GLOBAL_Control
0x14003a7d4  lea     rax, WPP_GLOBAL_Control
0x14003a7db  cmp     rdx, rax
0x14003a7de  jz      short loc_14003A811
0x14003a7e0  mov     eax, [rdx+2Ch]
0x14003a7e3  test    al, 2
0x14003a7e5  jz      short loc_14003A811
0x14003a7e7  cmp     byte ptr [rdx+29h], 4
0x14003a7eb  jb      short loc_14003A811
0x14003a7ed  movzx   ecx, byte ptr [r14+1]
0x14003a7f2  mov     r9, rdi
0x14003a7f5  mov     rax, [rsi+210h]
0x14003a7fc  mov     [r11-48h], rax
0x14003a800  mov     [rsp+78h+var_50], ecx
0x14003a804  mov     rcx, [rdx+18h]
0x14003a808  mov     [r11-58h], rbx
0x14003a80c  call    WPP_SF_qqDq
0x14003a811  cmp     cs:ClassPnPETWEnabled, bpl
0x14003a818  jz      short loc_14003A86C
0x14003a81a  lea     rdx, [rsp+78h+var_38]
0x14003a81f  mov     rcx, rbx
0x14003a822  call    cs:__imp_IoGetActivityIdIrp
0x14003a829  nop     dword ptr [rax+rax+00h]
0x14003a82e  test    eax, eax
0x14003a830  js      short loc_14003A86C
0x14003a832  test    byte ptr cs:WPP_MAIN_CB.Queue+3Ah, 10h
0x14003a839  mov     ebp, 1
0x14003a83e  jz      short loc_14003A86C
0x14003a840  movzx   eax, byte ptr [r14+1]
0x14003a845  lea     r8, [rsp+78h+var_38]
0x14003a84a  mov     r9d, [rsi+240h]
0x14003a851  mov     [rsp+78h+var_40], rdi
0x14003a856  mov     [rsp+78h+var_48], 0
0x14003a85e  mov     [rsp+78h+var_50], eax
0x14003a862  mov     [rsp+78h+var_58], rbx
0x14003a867  call    McTemplateK0qpddp_EtwWriteTransfer
0x14003a86c  cmp     byte ptr [rsi+246h], 2
0x14003a873  jnz     loc_14003A8FF
0x14003a879  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a880  lea     rax, WPP_GLOBAL_Control
0x14003a887  cmp     rcx, rax
0x14003a88a  jz      short loc_14003A8B1
0x14003a88c  mov     eax, [rcx+2Ch]
0x14003a88f  test    al, 2
0x14003a891  jz      short loc_14003A8B1
0x14003a893  cmp     byte ptr [rcx+29h], 3
0x14003a897  jb      short loc_14003A8B1
0x14003a899  mov     rcx, [rcx+18h]
0x14003a89d  lea     r8, WPP_a63e98891b663a71e40facba1bb231b0_Traceguids
0x14003a8a4  mov     edx, 0Eh
0x14003a8a9  mov     r9, rdi
0x14003a8ac  call    WPP_SF_q
0x14003a8b1  mov     edi, 0C00000C0h
0x14003a8b6  mov     [rbx+30h], edi
0x14003a8b9  test    ebp, ebp
0x14003a8bb  jz      short loc_14003A8E7
0x14003a8bd  test    byte ptr cs:WPP_MAIN_CB.Queue+3Ah, 10h
0x14003a8c4  jz      short loc_14003A8E7
0x14003a8c6  mov     r9d, [rsi+240h]
0x14003a8cd  lea     r8, [rsp+78h+var_38]
0x14003a8d2  mov     [rsp+78h+var_50], edi
0x14003a8d6  lea     rdx, EventPnpRequestComplete
0x14003a8dd  mov     [rsp+78h+var_58], rbx
0x14003a8e2  call    McTemplateK0qpd_EtwWriteTransfer
0x14003a8e7  xor     edx, edx; PriorityBoost
0x14003a8e9  mov     rcx, rbx; Irp
0x14003a8ec  call    cs:__imp_IofCompleteRequest
0x14003a8f3  nop     dword ptr [rax+rax+00h]
0x14003a8f8  mov     eax, edi
0x14003a8fa  jmp     loc_14003AAE5
0x14003a8ff  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a906  lea     rdx, WPP_GLOBAL_Control
0x14003a90d  cmp     rcx, rdx
0x14003a910  jz      short loc_14003A945
0x14003a912  mov     eax, [rcx+2Ch]
0x14003a915  test    al, 2
0x14003a917  jz      short loc_14003A945
0x14003a919  cmp     byte ptr [rcx+29h], 4
0x14003a91d  jb      short loc_14003A945
0x14003a91f  movzx   r9d, byte ptr [r14+1]
0x14003a924  lea     r8, WPP_a63e98891b663a71e40facba1bb231b0_Traceguids
0x14003a92b  mov     rcx, [rcx+18h]
0x14003a92f  mov     edx, 0Fh
0x14003a934  mov     [rsp+78h+var_58], rdi
0x14003a939  call    WPP_SF_Dq
0x14003a93e  lea     rdx, WPP_GLOBAL_Control
0x14003a945  movzx   ecx, byte ptr [r14+1]
0x14003a94a  test    ecx, ecx
0x14003a94c  jz      loc_14003AADA
0x14003a952  sub     ecx, 1
0x14003a955  jz      loc_14003AACD
0x14003a95b  sub     ecx, 1
0x14003a95e  jz      loc_14003AAC0
0x14003a964  sub     ecx, 1
0x14003a967  jz      loc_14003AA8C
0x14003a96d  sub     ecx, 6
0x14003a970  jz      loc_14003AA7F
0x14003a976  sub     ecx, 0Bh
0x14003a979  jz      loc_14003AA72
0x14003a97f  cmp     ecx, 3
0x14003a982  jz      short loc_14003A9C5
0x14003a984  test    ebp, ebp
0x14003a986  jz      short loc_14003A9B5
0x14003a988  test    byte ptr cs:WPP_MAIN_CB.Queue+3Ah, 10h
0x14003a98f  jz      short loc_14003A9B5
0x14003a991  mov     eax, [rbx+30h]
0x14003a994  lea     r8, [rsp+78h+var_38]
0x14003a999  mov     r9d, [rsi+240h]
0x14003a9a0  lea     rdx, EventPnpRequestComplete
0x14003a9a7  mov     [rsp+78h+var_50], eax
0x14003a9ab  mov     [rsp+78h+var_58], rbx
0x14003a9b0  call    McTemplateK0qpd_EtwWriteTransfer
0x14003a9b5  mov     rdx, rbx
0x14003a9b8  mov     rcx, rdi
0x14003a9bb  call    ClasspMpdevDefaultDispatch
0x14003a9c0  jmp     loc_14003AAE5
0x14003a9c5  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a9cc  cmp     rcx, rdx
0x14003a9cf  jz      short loc_14003A9F6
0x14003a9d1  mov     eax, [rcx+2Ch]
0x14003a9d4  test    al, 2
0x14003a9d6  jz      short loc_14003A9F6
0x14003a9d8  cmp     byte ptr [rcx+29h], 4
0x14003a9dc  jb      short loc_14003A9F6
0x14003a9de  mov     rcx, [rcx+18h]
0x14003a9e2  lea     r8, WPP_a63e98891b663a71e40facba1bb231b0_Traceguids
0x14003a9e9  mov     edx, 10h
0x14003a9ee  mov     r9, rdi
0x14003a9f1  call    WPP_SF_q
0x14003a9f6  mov     byte ptr [rsi+246h], 17h
0x14003a9fd  mov     dword ptr [rbx+30h], 0
0x14003aa04  cmp     byte ptr [rsi+247h], 0
0x14003aa0b  jz      short loc_14003AA34
0x14003aa0d  cmp     dword ptr [rsi+220h], 0
0x14003aa14  jz      short loc_14003AA34
0x14003aa16  mov     rax, [rsi+230h]
0x14003aa1d  test    rax, rax
0x14003aa20  jz      short loc_14003AA34
0x14003aa22  mov     rcx, [rsi+218h]
0x14003aa29  mov     r8b, 17h
0x14003aa2c  mov     rdx, rdi
0x14003aa2f  call    _guard_dispatch_icall
0x14003aa34  test    ebp, ebp
0x14003aa36  jz      short loc_14003AA65
0x14003aa38  test    byte ptr cs:WPP_MAIN_CB.Queue+3Ah, 10h
0x14003aa3f  jz      short loc_14003AA65
0x14003aa41  mov     eax, [rbx+30h]
0x14003aa44  mov     [rsp+78h+var_50], eax
0x14003aa48  mov     r9d, [rsi+240h]
0x14003aa4f  lea     r8, [rsp+78h+var_38]
0x14003aa54  lea     rdx, EventPnpRequestComplete
0x14003aa5b  mov     [rsp+78h+var_58], rbx
0x14003aa60  call    McTemplateK0qpd_EtwWriteTransfer
0x14003aa65  mov     rdx, rbx
0x14003aa68  mov     rcx, rdi
0x14003aa6b  call    ClassMpdevSendToNextDevice
0x14003aa70  jmp     short loc_14003AAE5
0x14003aa72  mov     rdx, rbx
0x14003aa75  mov     rcx, rdi
0x14003aa78  call    ClassMpdevQueryPnpDeviceState
0x14003aa7d  jmp     short loc_14003AAE5
0x14003aa7f  mov     rdx, rbx
0x14003aa82  mov     rcx, rdi
0x14003aa85  call    ClasspMpdevQueryCapabilities
0x14003aa8a  jmp     short loc_14003AAE5
0x14003aa8c  mov     dword ptr [rbx+30h], 0
0x14003aa93  cmp     byte ptr [rsi+244h], 1
0x14003aa9a  jnz     short loc_14003AAA9
0x14003aa9c  mov     rdx, rbx
0x14003aa9f  mov     rcx, rdi
0x14003aaa2  call    ClasspMpdevCancelRemove
0x14003aaa7  jmp     short loc_14003AAE5
0x14003aaa9  test    ebp, ebp
0x14003aaab  jz      short loc_14003AA65
0x14003aaad  test    byte ptr cs:WPP_MAIN_CB.Queue+3Ah, 10h
0x14003aab4  jz      short loc_14003AA65
0x14003aab6  mov     [rsp+78h+var_50], 0
0x14003aabe  jmp     short loc_14003AA48
0x14003aac0  mov     rdx, rbx; Irp
0x14003aac3  mov     rcx, rdi; DeviceObject
0x14003aac6  call    ClasspMpdevRemoveDevice
0x14003aacb  jmp     short loc_14003AAE5
0x14003aacd  mov     rdx, rbx
0x14003aad0  mov     rcx, rdi
0x14003aad3  call    ClasspMpdevQueryRemove
0x14003aad8  jmp     short loc_14003AAE5
0x14003aada  mov     rdx, rbx
0x14003aadd  mov     rcx, rdi
0x14003aae0  call    ClasspMpdevStartDevice
0x14003aae5  mov     rcx, [rsp+78h+var_28]
0x14003aaea  xor     rcx, rsp; StackCookie
0x14003aaed  call    __security_check_cookie
0x14003aaf2  lea     r11, [rsp+78h+var_18]
0x14003aaf7  mov     rbx, [r11+30h]
0x14003aafb  mov     rbp, [r11+38h]
0x14003aaff  mov     rsp, r11
0x14003ab02  pop     r14
0x14003ab04  pop     rdi
0x14003ab05  pop     rsi
0x14003ab06  retn
```
