# DiskCreateFdo

- ea: `0x140015350`
- end: `0x14001575a`
- name: `DiskCreateFdo`
- size: `1034`
- prototype: `__int64 __fastcall(PDRIVER_OBJECT DriverObject, PDEVICE_OBJECT TargetDevice)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140015030`

## callees

- `0x1400031a0`
- `0x1400040a8`
- `0x1400041c0`
- `0x140004370`
- `0x140005bf0`
- `0x140006000`
- `0x1400115e0`
- `0x140015350`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1400154ec`
- `ntoskrnl!ZwClose` at `0x1400156d9`
- `ntoskrnl!ZwClose` at `0x1400154ec`
- `ntoskrnl!ZwClose` at `0x1400156d9`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x1400154b0`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x1400154b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015602`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400156a8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015602`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400156a8`
- `ntoskrnl!ZwCreateDirectoryObject` at `0x140015438`
- `ntoskrnl!ZwCreateDirectoryObject` at `0x140015438`
- `ntoskrnl!IoAttachDeviceToDeviceStack` at `0x14001566d`
- `ntoskrnl!IoAttachDeviceToDeviceStack` at `0x14001566d`
- `ntoskrnl!IoDeleteDevice` at `0x140015692`
- `ntoskrnl!IoDeleteDevice` at `0x140015692`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400153f5`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400153f5`
- `ntoskrnl!ObfDereferenceObject` at `0x1400154fb`
- `ntoskrnl!ObfDereferenceObject` at `0x1400156b7`
- `ntoskrnl!ObfDereferenceObject` at `0x140015708`
- `ntoskrnl!ObfDereferenceObject` at `0x1400154fb`
- `ntoskrnl!ObfDereferenceObject` at `0x1400156b7`
- `ntoskrnl!ObfDereferenceObject` at `0x140015708`
- `ntoskrnl!ZwMakeTemporaryObject` at `0x1400154db`
- `ntoskrnl!ZwMakeTemporaryObject` at `0x1400156c8`
- `ntoskrnl!ZwMakeTemporaryObject` at `0x1400154db`
- `ntoskrnl!ZwMakeTemporaryObject` at `0x1400156c8`
- `CLASSPNP!ClassCreateDeviceObject` at `0x14001559c`
- `CLASSPNP!ClassCreateDeviceObject` at `0x14001559c`
- `CLASSPNP!ClassClaimDevice` at `0x1400154c4`
- `CLASSPNP!ClassClaimDevice` at `0x1400154c4`

## pseudocode

```c
__int64 __fastcall DiskCreateFdo(PDRIVER_OBJECT DriverObject, PDEVICE_OBJECT TargetDevice, int *a3, char a4)
{
  unsigned int v5; // ebx
  NTSTATUS v9; // ebx
  __int64 v10; // r8
  NTSTATUS v11; // r12d
  int v12; // eax
  PDEVICE_OBJECT AttachedDeviceReference; // r13
  NTSTATUS v15; // ebx
  int DeviceName; // r12d
  PCCHAR v17; // rbx
  _DWORD *DeviceExtension; // r15
  ULONG AlignmentRequirement; // eax
  PDEVICE_OBJECT v20; // rax
  PDEVICE_OBJECT SourceDevice; // [rsp+30h] [rbp-D0h] BYREF
  void *DirectoryHandle; // [rsp+38h] [rbp-C8h] BYREF
  PCCHAR ObjectNameBuffer; // [rsp+40h] [rbp-C0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+48h] [rbp-B8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-88h] BYREF
  wchar_t pszDest[64]; // [rsp+90h] [rbp-70h] BYREF

  ObjectNameBuffer = 0;
  v5 = 0;
  DirectoryHandle = 0;
  SourceDevice = 0;
  *a3 = 0;
  do
  {
    memset(pszDest, 0, sizeof(pszDest));
    DestinationString = 0;
    memset(&ObjectAttributes, 0, 44);
    v9 = RtlStringCchPrintfW(pszDest, 0x3Fu, L"\\Device\\Harddisk%d", v5);
    if ( v9 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_D(
          WPP_GLOBAL_Control->AttachedDevice,
          10,
          WPP_0d021951613e35be7880fae860fb7f50_Traceguids,
          (unsigned int)v9);
      }
      return (unsigned int)v9;
    }
    RtlInitUnicodeString(&DestinationString, pszDest);
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 592;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v11 = ZwCreateDirectoryObject(&DirectoryHandle, 0xF000Fu, &ObjectAttributes);
    v12 = *a3;
    v5 = *a3 + 1;
    *a3 = v5;
  }
  while ( v11 == -1073741771 || v11 == 0x40000000 );
  if ( v11 >= 0 )
  {
    *a3 = v12;
    AttachedDeviceReference = IoGetAttachedDeviceReference(TargetDevice);
    v15 = ClassClaimDevice(AttachedDeviceReference, 0);
    if ( v15 < 0 )
    {
      ZwMakeTemporaryObject(DirectoryHandle);
      ZwClose(DirectoryHandle);
      ObfDereferenceObject(AttachedDeviceReference);
      return (unsigned int)v15;
    }
    DeviceName = DiskGenerateDeviceName(*a3, (PVOID *)&ObjectNameBuffer);
    if ( DeviceName >= 0 )
    {
      v17 = ObjectNameBuffer;
      DeviceName = ClassCreateDeviceObject(DriverObject, ObjectNameBuffer, TargetDevice, 1u, &SourceDevice);
      if ( DeviceName >= 0 )
      {
        if ( v17 )
        {
          ExFreePoolWithTag(v17, 0);
          v17 = 0;
        }
        SourceDevice->Flags |= 0x10u;
        DeviceExtension = SourceDevice->DeviceExtension;
        if ( a4 )
          SourceDevice->Vpb->Flags |= 0x10u;
        DeviceExtension[150] = 0;
        DeviceExtension[147] = *a3;
        AlignmentRequirement = AttachedDeviceReference->AlignmentRequirement;
        if ( AlignmentRequirement > SourceDevice->AlignmentRequirement )
          SourceDevice->AlignmentRequirement = AlignmentRequirement;
        *((_QWORD *)DeviceExtension + 64) = TargetDevice;
        v20 = IoAttachDeviceToDeviceStack(SourceDevice, TargetDevice);
        *((_QWORD *)DeviceExtension + 2) = v20;
        if ( v20 )
        {
          SourceDevice->Flags &= ~0x80u;
          *((_QWORD *)DeviceExtension + 88) = DirectoryHandle;
          ObfDereferenceObject(AttachedDeviceReference);
          return 0;
        }
        DeviceName = -1073741823;
      }
      else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
             && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_s(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_0d021951613e35be7880fae860fb7f50_Traceguids, v17);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_GLOBAL_Control, (unsigned int)DeviceName);
      }
      v17 = ObjectNameBuffer;
    }
    if ( SourceDevice )
      IoDeleteDevice(SourceDevice);
    if ( v17 )
      ExFreePoolWithTag(v17, 0);
    ObfDereferenceObject(AttachedDeviceReference);
    ZwMakeTemporaryObject(DirectoryHandle);
    ZwClose(DirectoryHandle);
    return (unsigned int)DeviceName;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) )
        WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 11, v10, (unsigned int)v11);
    }
    return (unsigned int)v11;
  }
}

```

## disassembly

```asm
0x140015350  push    rbp
0x140015352  push    rbx
0x140015353  push    rsi
0x140015354  push    rdi
0x140015355  push    r12
0x140015357  push    r14
0x140015359  push    r15
0x14001535b  lea     rbp, [rsp-20h]
0x140015360  sub     rsp, 120h
0x140015367  mov     rax, cs:__security_cookie
0x14001536e  xor     rax, rsp
0x140015371  mov     [rbp+50h+var_40], rax
0x140015375  xor     r12d, r12d
0x140015378  movzx   r14d, r9b
0x14001537c  mov     [rsp+150h+ObjectNameBuffer], r12
0x140015381  mov     ebx, r12d
0x140015384  mov     [rsp+150h+DirectoryHandle], r12
0x140015389  mov     rdi, r8
0x14001538c  mov     [rsp+150h+SourceDevice], r12
0x140015391  mov     rsi, rdx
0x140015394  mov     [r8], r12d
0x140015397  mov     r15, rcx
0x14001539a  jmp     short loc_1400153A0
0x14001539c  xor     r12d, r12d
0x14001539f  nop
0x1400153a0  xor     edx, edx; Val
0x1400153a2  lea     rcx, [rbp+50h+pszDest]; void *
0x1400153a6  mov     r8d, 80h; Size
0x1400153ac  call    memset
0x1400153b1  xorps   xmm0, xmm0
0x1400153b4  lea     r8, aDeviceHarddisk; "\\Device\\Harddisk%d"
0x1400153bb  movups  xmmword ptr [rsp+150h+ObjectAttributes.ObjectName], xmm0
0x1400153c0  xor     eax, eax
0x1400153c2  lea     rcx, [rbp+50h+pszDest]; pszDest
0x1400153c6  mov     r9d, ebx
0x1400153c9  mov     edx, 3Fh ; '?'; cchDest
0x1400153ce  movups  xmmword ptr [rsp+150h+ObjectAttributes+1Ch], xmm0
0x1400153d3  movups  xmmword ptr [rsp+150h+DestinationString.Length], xmm0
0x1400153d8  movups  xmmword ptr [rsp+150h+ObjectAttributes.Length], xmm0
0x1400153dd  call    RtlStringCchPrintfW
0x1400153e2  mov     ebx, eax
0x1400153e4  test    eax, eax
0x1400153e6  js      loc_14001571B
0x1400153ec  lea     rdx, [rbp+50h+pszDest]; SourceString
0x1400153f0  lea     rcx, [rsp+150h+DestinationString]; DestinationString
0x1400153f5  call    cs:__imp_RtlInitUnicodeString
0x1400153fc  nop     dword ptr [rax+rax+00h]
0x140015401  lea     rax, [rsp+150h+DestinationString]
0x140015406  mov     [rsp+150h+ObjectAttributes.Length], 30h ; '0'
0x14001540e  xorps   xmm0, xmm0
0x140015411  mov     [rsp+150h+ObjectAttributes.ObjectName], rax
0x140015416  lea     r8, [rsp+150h+ObjectAttributes]; ObjectAttributes
0x14001541b  mov     [rsp+150h+ObjectAttributes.RootDirectory], r12
0x140015420  mov     edx, 0F000Fh; DesiredAccess
0x140015425  mov     [rsp+150h+ObjectAttributes.Attributes], 250h
0x14001542d  lea     rcx, [rsp+150h+DirectoryHandle]; DirectoryHandle
0x140015432  movdqu  xmmword ptr [rsp+150h+ObjectAttributes.SecurityDescriptor], xmm0
0x140015438  call    cs:__imp_ZwCreateDirectoryObject
0x14001543f  nop     dword ptr [rax+rax+00h]
0x140015444  mov     r12d, eax
0x140015447  mov     eax, [rdi]
0x140015449  lea     ebx, [rax+1]
0x14001544c  mov     [rdi], ebx
0x14001544e  cmp     r12d, 0C0000035h
0x140015455  jz      loc_14001539C
0x14001545b  cmp     r12d, 40000000h
0x140015462  jz      loc_14001539C
0x140015468  test    r12d, r12d
0x14001546b  jns     short loc_1400154A3
0x14001546d  mov     rcx, cs:WPP_GLOBAL_Control
0x140015474  lea     rax, WPP_GLOBAL_Control
0x14001547b  cmp     rcx, rax
0x14001547e  jz      short loc_14001549E
0x140015480  mov     eax, [rcx+2Ch]
0x140015483  test    al, 2
0x140015485  jz      short loc_14001549E
0x140015487  cmp     byte ptr [rcx+29h], 1
0x14001548b  jb      short loc_14001549E
0x14001548d  mov     rcx, [rcx+18h]
0x140015491  mov     edx, 0Bh
0x140015496  mov     r9d, r12d
0x140015499  call    WPP_SF_L
0x14001549e  mov     eax, r12d
0x1400154a1  jmp     short loc_140015511
0x1400154a3  mov     rcx, rsi; DeviceObject
0x1400154a6  mov     [rsp+150h+arg_18], r13
0x1400154ae  mov     [rdi], eax
0x1400154b0  call    cs:__imp_IoGetAttachedDeviceReference
0x1400154b7  nop     dword ptr [rax+rax+00h]
0x1400154bc  mov     rcx, rax; LowerDeviceObject
0x1400154bf  xor     edx, edx; Release
0x1400154c1  mov     r13, rax
0x1400154c4  call    cs:__imp_ClassClaimDevice
0x1400154cb  nop     dword ptr [rax+rax+00h]
0x1400154d0  mov     ebx, eax
0x1400154d2  test    eax, eax
0x1400154d4  jns     short loc_140015530
0x1400154d6  mov     rcx, [rsp+150h+DirectoryHandle]; Handle
0x1400154db  call    cs:__imp_ZwMakeTemporaryObject
0x1400154e2  nop     dword ptr [rax+rax+00h]
0x1400154e7  mov     rcx, [rsp+150h+DirectoryHandle]; Handle
0x1400154ec  call    cs:__imp_ZwClose
0x1400154f3  nop     dword ptr [rax+rax+00h]
0x1400154f8  mov     rcx, r13; Object
0x1400154fb  call    cs:__imp_ObfDereferenceObject
0x140015502  nop     dword ptr [rax+rax+00h]
0x140015507  mov     eax, ebx
0x140015509  mov     r13, [rsp+150h+arg_18]
0x140015511  mov     rcx, [rbp+50h+var_40]
0x140015515  xor     rcx, rsp; StackCookie
0x140015518  call    __security_check_cookie
0x14001551d  add     rsp, 120h
0x140015524  pop     r15
0x140015526  pop     r14
0x140015528  pop     r12
0x14001552a  pop     rdi
0x14001552b  pop     rsi
0x14001552c  pop     rbx
0x14001552d  pop     rbp
0x14001552e  retn
0x140015530  mov     ecx, [rdi]
0x140015532  lea     rdx, [rsp+150h+ObjectNameBuffer]
0x140015537  call    DiskGenerateDeviceName
0x14001553c  mov     r12d, eax
0x14001553f  test    eax, eax
0x140015541  jns     short loc_140015581
0x140015543  mov     r8, cs:WPP_GLOBAL_Control
0x14001554a  lea     rax, WPP_GLOBAL_Control
0x140015551  cmp     r8, rax
0x140015554  jz      short loc_140015577
0x140015556  mov     ecx, [r8+2Ch]
0x14001555a  test    cl, 2
0x14001555d  jz      short loc_140015577
0x14001555f  cmp     byte ptr [r8+29h], 1
0x140015564  jb      short loc_140015577
0x140015566  mov     rcx, [r8+18h]
0x14001556a  mov     edx, 0Ch
0x14001556f  mov     r9d, r12d
0x140015572  call    WPP_SF_L
0x140015577  mov     rbx, [rsp+150h+ObjectNameBuffer]
0x14001557c  jmp     loc_140015688
0x140015581  mov     rbx, [rsp+150h+ObjectNameBuffer]
0x140015586  lea     rax, [rsp+150h+SourceDevice]
0x14001558b  mov     rdx, rbx; ObjectNameBuffer
0x14001558e  mov     [rsp+150h+DeviceObject], rax; DeviceObject
0x140015593  mov     r9b, 1; IsFdo
0x140015596  mov     r8, rsi; LowerDeviceObject
0x140015599  mov     rcx, r15; DriverObject
0x14001559c  call    cs:__imp_ClassCreateDeviceObject
0x1400155a3  nop     dword ptr [rax+rax+00h]
0x1400155a8  mov     r12d, eax
0x1400155ab  test    eax, eax
0x1400155ad  jns     short loc_1400155F8
0x1400155af  mov     rcx, cs:WPP_GLOBAL_Control
0x1400155b6  lea     rax, WPP_GLOBAL_Control
0x1400155bd  cmp     rcx, rax
0x1400155c0  jz      loc_140015688
0x1400155c6  mov     eax, [rcx+2Ch]
0x1400155c9  test    al, 2
0x1400155cb  jz      loc_140015688
0x1400155d1  cmp     byte ptr [rcx+29h], 1
0x1400155d5  jb      loc_140015688
0x1400155db  mov     rcx, [rcx+18h]
0x1400155df  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x1400155e6  mov     edx, 0Dh
0x1400155eb  mov     r9, rbx
0x1400155ee  call    WPP_SF_s
0x1400155f3  jmp     loc_140015688
0x1400155f8  test    rbx, rbx
0x1400155fb  jz      short loc_140015610
0x1400155fd  xor     edx, edx; Tag
0x1400155ff  mov     rcx, rbx; P
0x140015602  call    cs:__imp_ExFreePoolWithTag
0x140015609  nop     dword ptr [rax+rax+00h]
0x14001560e  xor     ebx, ebx
0x140015610  mov     rax, [rsp+150h+SourceDevice]
0x140015615  or      dword ptr [rax+30h], 10h
0x140015619  mov     rax, [rsp+150h+SourceDevice]
0x14001561e  mov     r15, [rax+40h]
0x140015622  test    r14b, r14b
0x140015625  jz      short loc_140015630
0x140015627  mov     rax, [rax+38h]
0x14001562b  or      word ptr [rax+4], 10h
0x140015630  mov     dword ptr [r15+258h], 0
0x14001563b  mov     eax, [rdi]
0x14001563d  mov     [r15+24Ch], eax
0x140015644  mov     rcx, [rsp+150h+SourceDevice]
0x140015649  mov     eax, [r13+98h]
0x140015650  cmp     eax, [rcx+98h]
0x140015656  jbe     short loc_14001565E
0x140015658  mov     [rcx+98h], eax
0x14001565e  mov     [r15+200h], rsi
0x140015665  mov     rdx, rsi; TargetDevice
0x140015668  mov     rcx, [rsp+150h+SourceDevice]; SourceDevice
0x14001566d  call    cs:__imp_IoAttachDeviceToDeviceStack
0x140015674  nop     dword ptr [rax+rax+00h]
0x140015679  mov     [r15+10h], rax
0x14001567d  test    rax, rax
0x140015680  jnz     short loc_1400156ED
0x140015682  mov     r12d, 0C0000001h
0x140015688  mov     rcx, [rsp+150h+SourceDevice]; DeviceObject
0x14001568d  test    rcx, rcx
0x140015690  jz      short loc_14001569E
0x140015692  call    cs:__imp_IoDeleteDevice
0x140015699  nop     dword ptr [rax+rax+00h]
0x14001569e  test    rbx, rbx
0x1400156a1  jz      short loc_1400156B4
0x1400156a3  xor     edx, edx; Tag
0x1400156a5  mov     rcx, rbx; P
0x1400156a8  call    cs:__imp_ExFreePoolWithTag
0x1400156af  nop     dword ptr [rax+rax+00h]
0x1400156b4  mov     rcx, r13; Object
0x1400156b7  call    cs:__imp_ObfDereferenceObject
0x1400156be  nop     dword ptr [rax+rax+00h]
0x1400156c3  mov     rcx, [rsp+150h+DirectoryHandle]; Handle
0x1400156c8  call    cs:__imp_ZwMakeTemporaryObject
0x1400156cf  nop     dword ptr [rax+rax+00h]
0x1400156d4  mov     rcx, [rsp+150h+DirectoryHandle]; Handle
0x1400156d9  call    cs:__imp_ZwClose
0x1400156e0  nop     dword ptr [rax+rax+00h]
0x1400156e5  mov     eax, r12d
0x1400156e8  jmp     loc_140015509
0x1400156ed  mov     rax, [rsp+150h+SourceDevice]
0x1400156f2  mov     rcx, r13; Object
0x1400156f5  and     dword ptr [rax+30h], 0FFFFFF7Fh
0x1400156fc  mov     rax, [rsp+150h+DirectoryHandle]
0x140015701  mov     [r15+2C0h], rax
0x140015708  call    cs:__imp_ObfDereferenceObject
0x14001570f  nop     dword ptr [rax+rax+00h]
0x140015714  xor     eax, eax
0x140015716  jmp     loc_140015509
0x14001571b  mov     rcx, cs:WPP_GLOBAL_Control
0x140015722  lea     rax, WPP_GLOBAL_Control
0x140015729  cmp     rcx, rax
0x14001572c  jz      short loc_140015753
0x14001572e  mov     eax, [rcx+2Ch]
0x140015731  test    al, 2
0x140015733  jz      short loc_140015753
0x140015735  cmp     byte ptr [rcx+29h], 1
0x140015739  jb      short loc_140015753
0x14001573b  mov     rcx, [rcx+18h]
0x14001573f  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x140015746  mov     edx, 0Ah
0x14001574b  mov     r9d, ebx
0x14001574e  call    WPP_SF_D
0x140015753  mov     eax, ebx
0x140015755  jmp     loc_140015511
```
