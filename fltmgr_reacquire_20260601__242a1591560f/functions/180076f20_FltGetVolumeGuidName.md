# FltGetVolumeGuidName

- ea: `0x180076f20`
- end: `0x180077370`
- name: `FltGetVolumeGuidName`
- size: `1104`
- prototype: `NTSTATUS __stdcall(PFLT_VOLUME Volume, PUNICODE_STRING VolumeGuidName, PULONG BufferSizeNeeded)`
- caller_count: `0`
- callee_count: `4`
- tags: `reparse_path`

## callees

- `0x180003380`
- `0x180009f20`
- `0x180024900`
- `0x180076f20`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x180077147`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800772ee`
- `ntoskrnl!ExFreePoolWithTag` at `0x180077307`
- `ntoskrnl!ExFreePoolWithTag` at `0x180077147`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800772ee`
- `ntoskrnl!ExFreePoolWithTag` at `0x180077307`
- `ntoskrnl!ExAllocatePool2` at `0x180077021`
- `ntoskrnl!ExAllocatePool2` at `0x18007708e`
- `ntoskrnl!ExAllocatePool2` at `0x180077021`
- `ntoskrnl!ExAllocatePool2` at `0x18007708e`
- `ntoskrnl!KeInitializeEvent` at `0x180077075`
- `ntoskrnl!KeInitializeEvent` at `0x180077075`
- `ntoskrnl!KeWaitForSingleObject` at `0x180077125`
- `ntoskrnl!KeWaitForSingleObject` at `0x180077125`
- `ntoskrnl!ObfDereferenceObject` at `0x180077358`
- `ntoskrnl!ObfDereferenceObject` at `0x180077358`
- `ntoskrnl!RtlCopyUnicodeString` at `0x18007728b`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1800772b4`
- `ntoskrnl!RtlCopyUnicodeString` at `0x18007728b`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1800772b4`
- `ntoskrnl!RtlInitUnicodeString` at `0x180076fb7`
- `ntoskrnl!RtlInitUnicodeString` at `0x180076fb7`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x180076fdd`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x180076fdd`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1800770de`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1800770de`

## string_xrefs

- `0x180076fab`: `\Device\MountPointManager`

## pseudocode

```c
NTSTATUS __stdcall FltGetVolumeGuidName(PFLT_VOLUME Volume, PUNICODE_STRING VolumeGuidName, PULONG BufferSizeNeeded)
{
  _FLT_VOLUME_FLAGS Flags; // eax
  unsigned int DeviceObjectPointer; // ebx
  void *v8; // rbp
  ULONG *OutputBuffer; // rsi
  ULONG v10; // r14d
  __int64 Pool2; // rax
  ULONG OutputBufferLength; // ebx
  IRP *v13; // rax
  ULONG i; // r8d
  unsigned __int16 v15; // dx
  wchar_t *v16; // rcx
  wchar_t v17; // ax
  UNICODE_STRING SourceString; // [rsp+50h] [rbp-88h] BYREF
  UNICODE_STRING DestinationString; // [rsp+60h] [rbp-78h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-68h] BYREF
  struct _KEVENT Event; // [rsp+80h] [rbp-58h] BYREF
  PDEVICE_OBJECT DeviceObject; // [rsp+E0h] [rbp+8h] BYREF
  PFILE_OBJECT FileObject; // [rsp+F8h] [rbp+20h] BYREF

  Flags = Volume->Flags;
  DeviceObject = 0;
  FileObject = 0;
  DestinationString = 0;
  memset(&Event, 0, sizeof(Event));
  IoStatusBlock = 0;
  SourceString = 0;
  if ( (Flags & 1) != 0 )
  {
    DeviceObjectPointer = -1073741808;
    goto LABEL_52;
  }
  v8 = 0;
  OutputBuffer = 0;
  if ( Volume->GuidName.Length )
  {
LABEL_41:
    if ( VolumeGuidName && VolumeGuidName->MaximumLength >= Volume->GuidName.Length )
    {
      RtlCopyUnicodeString(VolumeGuidName, &Volume->GuidName);
      DeviceObjectPointer = 0;
    }
    else
    {
      if ( BufferSizeNeeded )
        *BufferSizeNeeded = Volume->GuidName.Length;
      DeviceObjectPointer = -1073741789;
    }
    if ( !v8 )
      goto LABEL_50;
  }
  else
  {
    RtlInitUnicodeString(&DestinationString, L"\\Device\\MountPointManager");
    DeviceObjectPointer = IoGetDeviceObjectPointer(&DestinationString, 0x80u, &FileObject, &DeviceObject);
    if ( (int)FltpDbgStatus(DeviceObjectPointer, "minkernel\\fs\\filtermgr\\filter\\volumesup.c", 1890, 0) < 0 )
      goto LABEL_52;
    v10 = Volume->DeviceName.Length + 24;
    Pool2 = ExAllocatePool2(256, v10, 1870024006);
    v8 = (void *)Pool2;
    if ( !Pool2 )
    {
      DeviceObjectPointer = -1073741670;
      goto LABEL_52;
    }
    *(_DWORD *)(Pool2 + 16) = 24;
    *(_WORD *)(Pool2 + 20) = Volume->DeviceName.Length;
    memmove((void *)(Pool2 + 24), Volume->DeviceName.Buffer, Volume->DeviceName.Length);
    OutputBufferLength = 2048;
    KeInitializeEvent(&Event, SynchronizationEvent, 0);
    while ( 1 )
    {
      OutputBuffer = (ULONG *)ExAllocatePool2(256, OutputBufferLength, 1870024006);
      if ( !OutputBuffer
        || (v13 = IoBuildDeviceIoControlRequest(
                    0x6D0008u,
                    DeviceObject,
                    v8,
                    v10,
                    OutputBuffer,
                    OutputBufferLength,
                    0,
                    &Event,
                    &IoStatusBlock)) == 0 )
      {
        DeviceObjectPointer = -1073741670;
        goto LABEL_49;
      }
      DeviceObjectPointer = FltpCallDriver(DeviceObject, v13);
      if ( DeviceObjectPointer == 259 )
      {
        KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
        DeviceObjectPointer = IoStatusBlock.Status;
      }
      if ( DeviceObjectPointer != -2147483643 )
        break;
      OutputBufferLength = *OutputBuffer;
      ExFreePoolWithTag(OutputBuffer, 0x6F764D46u);
    }
    if ( (int)FltpDbgStatus(DeviceObjectPointer, "minkernel\\fs\\filtermgr\\filter\\volumesup.c", 2029, 3221225488LL) >= 0 )
    {
      DeviceObjectPointer = -1071906796;
      for ( i = 0; i < OutputBuffer[1]; ++i )
      {
        v15 = OutputBuffer[6 * i + 3];
        SourceString.MaximumLength = v15;
        SourceString.Length = v15;
        v16 = (wchar_t *)((char *)OutputBuffer + OutputBuffer[6 * i + 2]);
        SourceString.Buffer = v16;
        if ( (v15 == 96 || v15 == 98 && v16[48] == 92) && *v16 == 92 )
        {
          v17 = v16[1];
          if ( (v17 == 63 || v17 == 92)
            && v16[2] == 63
            && v16[3] == 92
            && v16[4] == 86
            && v16[5] == 111
            && v16[6] == 108
            && v16[7] == 117
            && v16[8] == 109
            && v16[9] == 101
            && v16[10] == 123
            && v16[19] == 45
            && v16[24] == 45
            && v16[29] == 45
            && v16[34] == 45
            && v16[47] == 125 )
          {
            DeviceObjectPointer = 0;
            break;
          }
        }
      }
      if ( (int)FltpDbgStatus(DeviceObjectPointer, "minkernel\\fs\\filtermgr\\filter\\volumesup.c", 2071, 0) >= 0 )
      {
        RtlCopyUnicodeString(&Volume->GuidName, &SourceString);
        goto LABEL_41;
      }
    }
  }
LABEL_49:
  ExFreePoolWithTag(v8, 0x6F764D46u);
LABEL_50:
  if ( OutputBuffer )
    ExFreePoolWithTag(OutputBuffer, 0x6F764D46u);
LABEL_52:
  if ( FileObject )
    ObfDereferenceObject(FileObject);
  return DeviceObjectPointer;
}

```

## disassembly

```asm
0x180076f20  mov     r11, rsp
0x180076f23  push    rbx
0x180076f24  sub     rsp, 0D0h
0x180076f2b  mov     [r11-18h], rdi
0x180076f2f  xor     eax, eax
0x180076f31  mov     [r11-20h], r12
0x180076f35  xorps   xmm0, xmm0
0x180076f38  mov     [r11-30h], r14
0x180076f3c  xorps   xmm1, xmm1
0x180076f3f  xor     r14d, r14d
0x180076f42  mov     [r11-48h], rax
0x180076f46  mov     eax, [rcx+38h]
0x180076f49  mov     r12, r8
0x180076f4c  mov     [r11-38h], r15
0x180076f50  mov     r15, rdx
0x180076f53  mov     [r11+8], r14
0x180076f57  mov     rdi, rcx
0x180076f5a  mov     [r11+20h], r14
0x180076f5e  movups  xmmword ptr [rsp+0D8h+DestinationString.Length], xmm0
0x180076f63  movups  xmmword ptr [r11-58h], xmm0
0x180076f68  movups  xmmword ptr [rsp+0D8h+var_68], xmm0
0x180076f6d  movups  xmmword ptr [rsp+0D8h+SourceString.Length], xmm1
0x180076f72  test    al, 1
0x180076f74  jz      short loc_180076F80
0x180076f76  mov     ebx, 0C0000010h
0x180076f7b  jmp     loc_18007732B
0x180076f80  mov     [rsp+0D8h+arg_8], rbp
0x180076f88  mov     rbp, r14
0x180076f8b  mov     [rsp+0D8h+var_10], rsi
0x180076f93  mov     rsi, r14
0x180076f96  mov     [rsp+0D8h+var_28], r13
0x180076f9e  cmp     [rcx+80h], si
0x180076fa5  jnz     loc_180077297
0x180076fab  lea     rdx, aDeviceMountpoi; "\\Device\\MountPointManager"
0x180076fb2  lea     rcx, [rsp+0D8h+DestinationString]; DestinationString
0x180076fb7  call    cs:__imp_RtlInitUnicodeString
0x180076fbe  nop     dword ptr [rax+rax+00h]
0x180076fc3  lea     r9, [rsp+0D8h+DeviceObject]; DeviceObject
0x180076fcb  mov     edx, 80h; DesiredAccess
0x180076fd0  lea     r8, [rsp+0D8h+FileObject]; FileObject
0x180076fd8  lea     rcx, [rsp+0D8h+DestinationString]; ObjectName
0x180076fdd  call    cs:__imp_IoGetDeviceObjectPointer
0x180076fe4  nop     dword ptr [rax+rax+00h]
0x180076fe9  mov     r8d, 762h
0x180076fef  lea     rdx, aMinkernelFsFil_30; "minkernel\\fs\\filtermgr\\filter\\volum"...
0x180076ff6  mov     ecx, eax
0x180076ff8  xor     r9d, r9d
0x180076ffb  mov     ebx, eax
0x180076ffd  call    FltpDbgStatus
0x180077002  test    eax, eax
0x180077004  js      loc_180077313
0x18007700a  movzx   r14d, word ptr [rdi+70h]
0x18007700f  mov     ecx, 100h
0x180077014  add     r14d, 18h
0x180077018  mov     r8d, 6F764D46h
0x18007701e  mov     edx, r14d
0x180077021  call    cs:__imp_ExAllocatePool2
0x180077028  nop     dword ptr [rax+rax+00h]
0x18007702d  mov     rbp, rax
0x180077030  test    rax, rax
0x180077033  jnz     short loc_18007703F
0x180077035  mov     ebx, 0C000009Ah
0x18007703a  jmp     loc_180077313
0x18007703f  mov     dword ptr [rax+10h], 18h
0x180077046  lea     rcx, [rbp+18h]; void *
0x18007704a  movzx   eax, word ptr [rdi+70h]
0x18007704e  mov     [rbp+14h], ax
0x180077052  movzx   r8d, word ptr [rdi+70h]; Size
0x180077057  mov     rdx, [rdi+78h]; Src
0x18007705b  call    memmove
0x180077060  xor     r8d, r8d; State
0x180077063  lea     rcx, [rsp+0D8h+Event]; Event
0x18007706b  mov     edx, 1; Type
0x180077070  mov     ebx, 800h
0x180077075  call    cs:__imp_KeInitializeEvent
0x18007707c  nop     dword ptr [rax+rax+00h]
0x180077081  mov     edx, ebx
0x180077083  mov     ecx, 100h
0x180077088  mov     r8d, 6F764D46h
0x18007708e  call    cs:__imp_ExAllocatePool2
0x180077095  nop     dword ptr [rax+rax+00h]
0x18007709a  mov     rsi, rax
0x18007709d  test    rax, rax
0x1800770a0  jz      loc_1800772C5
0x1800770a6  mov     rdx, [rsp+0D8h+DeviceObject]; DeviceObject
0x1800770ae  lea     rax, [rsp+0D8h+var_68]
0x1800770b3  mov     [rsp+0D8h+IoStatusBlock], rax; IoStatusBlock
0x1800770b8  mov     r9d, r14d; InputBufferLength
0x1800770bb  lea     rax, [rsp+0D8h+Event]
0x1800770c3  mov     r8, rbp; InputBuffer
0x1800770c6  mov     [rsp+0D8h+var_A0], rax; Event
0x1800770cb  mov     ecx, 6D0008h; IoControlCode
0x1800770d0  mov     [rsp+0D8h+InternalDeviceIoControl], 0; InternalDeviceIoControl
0x1800770d5  mov     [rsp+0D8h+OutputBufferLength], ebx; OutputBufferLength
0x1800770d9  mov     [rsp+0D8h+OutputBuffer], rsi; OutputBuffer
0x1800770de  call    cs:__imp_IoBuildDeviceIoControlRequest
0x1800770e5  nop     dword ptr [rax+rax+00h]
0x1800770ea  test    rax, rax
0x1800770ed  jz      loc_1800772C5
0x1800770f3  mov     rcx, [rsp+0D8h+DeviceObject]; DeviceObject
0x1800770fb  mov     rdx, rax; Irp
0x1800770fe  call    FltpCallDriver
0x180077103  mov     ebx, eax
0x180077105  cmp     eax, 103h
0x18007710a  jnz     short loc_180077135
0x18007710c  xor     r9d, r9d; Alertable
0x18007710f  mov     [rsp+0D8h+OutputBuffer], 0; Timeout
0x180077118  xor     r8d, r8d; WaitMode
0x18007711b  lea     rcx, [rsp+0D8h+Event]; Object
0x180077123  xor     edx, edx; WaitReason
0x180077125  call    cs:__imp_KeWaitForSingleObject
0x18007712c  nop     dword ptr [rax+rax+00h]
0x180077131  mov     ebx, dword ptr [rsp+0D8h+var_68]
0x180077135  cmp     ebx, 80000005h
0x18007713b  jnz     short loc_180077158
0x18007713d  mov     ebx, [rsi]
0x18007713f  mov     edx, 6F764D46h; Tag
0x180077144  mov     rcx, rsi; P
0x180077147  call    cs:__imp_ExFreePoolWithTag
0x18007714e  nop     dword ptr [rax+rax+00h]
0x180077153  jmp     loc_180077081
0x180077158  xor     r14d, r14d
0x18007715b  lea     rdx, aMinkernelFsFil_30; "minkernel\\fs\\filtermgr\\filter\\volum"...
0x180077162  mov     [rsp+0D8h+var_A0], r14
0x180077167  mov     r8d, 7EDh
0x18007716d  mov     dword ptr [rsp+0D8h+InternalDeviceIoControl], 0C0000034h
0x180077175  mov     r9d, 0C0000010h
0x18007717b  mov     [rsp+0D8h+OutputBufferLength], 0C000000Eh
0x180077183  mov     ecx, ebx
0x180077185  mov     dword ptr [rsp+0D8h+OutputBuffer], 0C000000Dh
0x18007718d  call    FltpDbgStatus
0x180077192  test    eax, eax
0x180077194  js      loc_1800772E6
0x18007719a  mov     ebx, 0C01C0014h
0x18007719f  mov     r8d, r14d
0x1800771a2  cmp     r8d, [rsi+4]
0x1800771a6  jnb     loc_180077264
0x1800771ac  mov     eax, r8d
0x1800771af  lea     rcx, [rax+rax*2]
0x1800771b3  movzx   edx, word ptr [rsi+rcx*8+0Ch]
0x1800771b8  mov     [rsp+0D8h+SourceString.MaximumLength], dx
0x1800771bd  mov     [rsp+0D8h+SourceString.Length], dx
0x1800771c2  mov     ecx, [rsi+rcx*8+8]
0x1800771c6  add     rcx, rsi
0x1800771c9  mov     [rsp+0D8h+SourceString.Buffer], rcx
0x1800771ce  cmp     dx, 60h ; '`'
0x1800771d2  jz      short loc_1800771E1
0x1800771d4  cmp     dx, 62h ; 'b'
0x1800771d8  jnz     short loc_180077259
0x1800771da  cmp     word ptr [rcx+60h], 5Ch ; '\'
0x1800771df  jnz     short loc_180077259
0x1800771e1  cmp     word ptr [rcx], 5Ch ; '\'
0x1800771e5  jnz     short loc_180077259
0x1800771e7  movzx   eax, word ptr [rcx+2]
0x1800771eb  cmp     ax, 3Fh ; '?'
0x1800771ef  jz      short loc_1800771F7
0x1800771f1  cmp     ax, 5Ch ; '\'
0x1800771f5  jnz     short loc_180077259
0x1800771f7  cmp     word ptr [rcx+4], 3Fh ; '?'
0x1800771fc  jnz     short loc_180077259
0x1800771fe  cmp     word ptr [rcx+6], 5Ch ; '\'
0x180077203  jnz     short loc_180077259
0x180077205  cmp     word ptr [rcx+8], 56h ; 'V'
0x18007720a  jnz     short loc_180077259
0x18007720c  cmp     word ptr [rcx+0Ah], 6Fh ; 'o'
0x180077211  jnz     short loc_180077259
0x180077213  cmp     word ptr [rcx+0Ch], 6Ch ; 'l'
0x180077218  jnz     short loc_180077259
0x18007721a  cmp     word ptr [rcx+0Eh], 75h ; 'u'
0x18007721f  jnz     short loc_180077259
0x180077221  cmp     word ptr [rcx+10h], 6Dh ; 'm'
0x180077226  jnz     short loc_180077259
0x180077228  cmp     word ptr [rcx+12h], 65h ; 'e'
0x18007722d  jnz     short loc_180077259
0x18007722f  cmp     word ptr [rcx+14h], 7Bh ; '{'
0x180077234  jnz     short loc_180077259
0x180077236  cmp     word ptr [rcx+26h], 2Dh ; '-'
0x18007723b  jnz     short loc_180077259
0x18007723d  cmp     word ptr [rcx+30h], 2Dh ; '-'
0x180077242  jnz     short loc_180077259
0x180077244  cmp     word ptr [rcx+3Ah], 2Dh ; '-'
0x180077249  jnz     short loc_180077259
0x18007724b  cmp     word ptr [rcx+44h], 2Dh ; '-'
0x180077250  jnz     short loc_180077259
0x180077252  cmp     word ptr [rcx+5Eh], 7Dh ; '}'
0x180077257  jz      short loc_180077261
0x180077259  inc     r8d
0x18007725c  jmp     loc_1800771A2
0x180077261  mov     ebx, r14d
0x180077264  mov     r8d, 817h
0x18007726a  lea     rdx, aMinkernelFsFil_30; "minkernel\\fs\\filtermgr\\filter\\volum"...
0x180077271  xor     r9d, r9d
0x180077274  mov     ecx, ebx
0x180077276  call    FltpDbgStatus
0x18007727b  test    eax, eax
0x18007727d  js      short loc_1800772E6
0x18007727f  lea     rdx, [rsp+0D8h+SourceString]; SourceString
0x180077284  lea     rcx, [rdi+80h]; DestinationString
0x18007728b  call    cs:__imp_RtlCopyUnicodeString
0x180077292  nop     dword ptr [rax+rax+00h]
0x180077297  test    r15, r15
0x18007729a  jz      short loc_1800772CC
0x18007729c  movzx   eax, word ptr [rdi+80h]
0x1800772a3  cmp     [r15+2], ax
0x1800772a8  jb      short loc_1800772CC
0x1800772aa  lea     rdx, [rdi+80h]; SourceString
0x1800772b1  mov     rcx, r15; DestinationString
0x1800772b4  call    cs:__imp_RtlCopyUnicodeString
0x1800772bb  nop     dword ptr [rax+rax+00h]
0x1800772c0  mov     ebx, r14d
0x1800772c3  jmp     short loc_1800772E1
0x1800772c5  mov     ebx, 0C000009Ah
0x1800772ca  jmp     short loc_1800772E6
0x1800772cc  test    r12, r12
0x1800772cf  jz      short loc_1800772DC
0x1800772d1  movzx   eax, word ptr [rdi+80h]
0x1800772d8  mov     [r12], eax
0x1800772dc  mov     ebx, 0C0000023h
0x1800772e1  test    rbp, rbp
0x1800772e4  jz      short loc_1800772FA
0x1800772e6  mov     edx, 6F764D46h; Tag
0x1800772eb  mov     rcx, rbp; P
0x1800772ee  call    cs:__imp_ExFreePoolWithTag
0x1800772f5  nop     dword ptr [rax+rax+00h]
0x1800772fa  test    rsi, rsi
0x1800772fd  jz      short loc_180077313
0x1800772ff  mov     edx, 6F764D46h; Tag
0x180077304  mov     rcx, rsi; P
0x180077307  call    cs:__imp_ExFreePoolWithTag
0x18007730e  nop     dword ptr [rax+rax+00h]
0x180077313  mov     rsi, [rsp+0D8h+var_10]
0x18007731b  mov     rbp, [rsp+0D8h+arg_8]
0x180077323  mov     r13, [rsp+0D8h+var_28]
0x18007732b  mov     rcx, [rsp+0D8h+FileObject]; Object
0x180077333  mov     r15, [rsp+0D8h+var_38]
0x18007733b  mov     r14, [rsp+0D8h+var_30]
0x180077343  mov     r12, [rsp+0D8h+var_20]
0x18007734b  mov     rdi, [rsp+0D8h+var_18]
0x180077353  test    rcx, rcx
0x180077356  jz      short loc_180077364
0x180077358  call    cs:__imp_ObfDereferenceObject
0x18007735f  nop     dword ptr [rax+rax+00h]
0x180077364  mov     eax, ebx
0x180077366  add     rsp, 0D0h
0x18007736d  pop     rbx
0x18007736e  retn
```
