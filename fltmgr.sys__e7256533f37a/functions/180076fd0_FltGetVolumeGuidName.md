# FltGetVolumeGuidName

- ea: `0x180076fd0`
- end: `0x180077420`
- name: `FltGetVolumeGuidName`
- size: `1104`
- prototype: `NTSTATUS __stdcall(PFLT_VOLUME Volume, PUNICODE_STRING VolumeGuidName, PULONG BufferSizeNeeded)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path`

## callers

- `0x180085aa0`

## callees

- `0x180003380`
- `0x180009f20`
- `0x180024940`
- `0x180076fd0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1800771f7`
- `ntoskrnl!ExFreePoolWithTag` at `0x18007739e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800773b7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800771f7`
- `ntoskrnl!ExFreePoolWithTag` at `0x18007739e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800773b7`
- `ntoskrnl!ExAllocatePool2` at `0x1800770d1`
- `ntoskrnl!ExAllocatePool2` at `0x18007713e`
- `ntoskrnl!ExAllocatePool2` at `0x1800770d1`
- `ntoskrnl!ExAllocatePool2` at `0x18007713e`
- `ntoskrnl!KeInitializeEvent` at `0x180077125`
- `ntoskrnl!KeInitializeEvent` at `0x180077125`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800771d5`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800771d5`
- `ntoskrnl!ObfDereferenceObject` at `0x180077408`
- `ntoskrnl!ObfDereferenceObject` at `0x180077408`
- `ntoskrnl!RtlCopyUnicodeString` at `0x18007733b`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180077364`
- `ntoskrnl!RtlCopyUnicodeString` at `0x18007733b`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180077364`
- `ntoskrnl!RtlInitUnicodeString` at `0x180077067`
- `ntoskrnl!RtlInitUnicodeString` at `0x180077067`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x18007708d`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x18007708d`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x18007718e`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x18007718e`

## string_xrefs

- `0x18007705b`: `\Device\MountPointManager`

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
0x180076fd0  mov     r11, rsp
0x180076fd3  push    rbx
0x180076fd4  sub     rsp, 0D0h
0x180076fdb  mov     [r11-18h], rdi
0x180076fdf  xor     eax, eax
0x180076fe1  mov     [r11-20h], r12
0x180076fe5  xorps   xmm0, xmm0
0x180076fe8  mov     [r11-30h], r14
0x180076fec  xorps   xmm1, xmm1
0x180076fef  xor     r14d, r14d
0x180076ff2  mov     [r11-48h], rax
0x180076ff6  mov     eax, [rcx+38h]
0x180076ff9  mov     r12, r8
0x180076ffc  mov     [r11-38h], r15
0x180077000  mov     r15, rdx
0x180077003  mov     [r11+8], r14
0x180077007  mov     rdi, rcx
0x18007700a  mov     [r11+20h], r14
0x18007700e  movups  xmmword ptr [rsp+0D8h+DestinationString.Length], xmm0
0x180077013  movups  xmmword ptr [r11-58h], xmm0
0x180077018  movups  xmmword ptr [rsp+0D8h+var_68], xmm0
0x18007701d  movups  xmmword ptr [rsp+0D8h+SourceString.Length], xmm1
0x180077022  test    al, 1
0x180077024  jz      short loc_180077030
0x180077026  mov     ebx, 0C0000010h
0x18007702b  jmp     loc_1800773DB
0x180077030  mov     [rsp+0D8h+arg_8], rbp
0x180077038  mov     rbp, r14
0x18007703b  mov     [rsp+0D8h+var_10], rsi
0x180077043  mov     rsi, r14
0x180077046  mov     [rsp+0D8h+var_28], r13
0x18007704e  cmp     [rcx+80h], si
0x180077055  jnz     loc_180077347
0x18007705b  lea     rdx, aDeviceMountpoi; "\\Device\\MountPointManager"
0x180077062  lea     rcx, [rsp+0D8h+DestinationString]; DestinationString
0x180077067  call    cs:__imp_RtlInitUnicodeString
0x18007706e  nop     dword ptr [rax+rax+00h]
0x180077073  lea     r9, [rsp+0D8h+DeviceObject]; DeviceObject
0x18007707b  mov     edx, 80h; DesiredAccess
0x180077080  lea     r8, [rsp+0D8h+FileObject]; FileObject
0x180077088  lea     rcx, [rsp+0D8h+DestinationString]; ObjectName
0x18007708d  call    cs:__imp_IoGetDeviceObjectPointer
0x180077094  nop     dword ptr [rax+rax+00h]
0x180077099  mov     r8d, 762h
0x18007709f  lea     rdx, aMinkernelFsFil_30; "minkernel\\fs\\filtermgr\\filter\\volum"...
0x1800770a6  mov     ecx, eax
0x1800770a8  xor     r9d, r9d
0x1800770ab  mov     ebx, eax
0x1800770ad  call    FltpDbgStatus
0x1800770b2  test    eax, eax
0x1800770b4  js      loc_1800773C3
0x1800770ba  movzx   r14d, word ptr [rdi+70h]
0x1800770bf  mov     ecx, 100h
0x1800770c4  add     r14d, 18h
0x1800770c8  mov     r8d, 6F764D46h
0x1800770ce  mov     edx, r14d
0x1800770d1  call    cs:__imp_ExAllocatePool2
0x1800770d8  nop     dword ptr [rax+rax+00h]
0x1800770dd  mov     rbp, rax
0x1800770e0  test    rax, rax
0x1800770e3  jnz     short loc_1800770EF
0x1800770e5  mov     ebx, 0C000009Ah
0x1800770ea  jmp     loc_1800773C3
0x1800770ef  mov     dword ptr [rax+10h], 18h
0x1800770f6  lea     rcx, [rbp+18h]; void *
0x1800770fa  movzx   eax, word ptr [rdi+70h]
0x1800770fe  mov     [rbp+14h], ax
0x180077102  movzx   r8d, word ptr [rdi+70h]; Size
0x180077107  mov     rdx, [rdi+78h]; Src
0x18007710b  call    memmove
0x180077110  xor     r8d, r8d; State
0x180077113  lea     rcx, [rsp+0D8h+Event]; Event
0x18007711b  mov     edx, 1; Type
0x180077120  mov     ebx, 800h
0x180077125  call    cs:__imp_KeInitializeEvent
0x18007712c  nop     dword ptr [rax+rax+00h]
0x180077131  mov     edx, ebx
0x180077133  mov     ecx, 100h
0x180077138  mov     r8d, 6F764D46h
0x18007713e  call    cs:__imp_ExAllocatePool2
0x180077145  nop     dword ptr [rax+rax+00h]
0x18007714a  mov     rsi, rax
0x18007714d  test    rax, rax
0x180077150  jz      loc_180077375
0x180077156  mov     rdx, [rsp+0D8h+DeviceObject]; DeviceObject
0x18007715e  lea     rax, [rsp+0D8h+var_68]
0x180077163  mov     [rsp+0D8h+IoStatusBlock], rax; IoStatusBlock
0x180077168  mov     r9d, r14d; InputBufferLength
0x18007716b  lea     rax, [rsp+0D8h+Event]
0x180077173  mov     r8, rbp; InputBuffer
0x180077176  mov     [rsp+0D8h+var_A0], rax; Event
0x18007717b  mov     ecx, 6D0008h; IoControlCode
0x180077180  mov     [rsp+0D8h+InternalDeviceIoControl], 0; InternalDeviceIoControl
0x180077185  mov     [rsp+0D8h+OutputBufferLength], ebx; OutputBufferLength
0x180077189  mov     [rsp+0D8h+OutputBuffer], rsi; OutputBuffer
0x18007718e  call    cs:__imp_IoBuildDeviceIoControlRequest
0x180077195  nop     dword ptr [rax+rax+00h]
0x18007719a  test    rax, rax
0x18007719d  jz      loc_180077375
0x1800771a3  mov     rcx, [rsp+0D8h+DeviceObject]; DeviceObject
0x1800771ab  mov     rdx, rax; Irp
0x1800771ae  call    FltpCallDriver
0x1800771b3  mov     ebx, eax
0x1800771b5  cmp     eax, 103h
0x1800771ba  jnz     short loc_1800771E5
0x1800771bc  xor     r9d, r9d; Alertable
0x1800771bf  mov     [rsp+0D8h+OutputBuffer], 0; Timeout
0x1800771c8  xor     r8d, r8d; WaitMode
0x1800771cb  lea     rcx, [rsp+0D8h+Event]; Object
0x1800771d3  xor     edx, edx; WaitReason
0x1800771d5  call    cs:__imp_KeWaitForSingleObject
0x1800771dc  nop     dword ptr [rax+rax+00h]
0x1800771e1  mov     ebx, dword ptr [rsp+0D8h+var_68]
0x1800771e5  cmp     ebx, 80000005h
0x1800771eb  jnz     short loc_180077208
0x1800771ed  mov     ebx, [rsi]
0x1800771ef  mov     edx, 6F764D46h; Tag
0x1800771f4  mov     rcx, rsi; P
0x1800771f7  call    cs:__imp_ExFreePoolWithTag
0x1800771fe  nop     dword ptr [rax+rax+00h]
0x180077203  jmp     loc_180077131
0x180077208  xor     r14d, r14d
0x18007720b  lea     rdx, aMinkernelFsFil_30; "minkernel\\fs\\filtermgr\\filter\\volum"...
0x180077212  mov     [rsp+0D8h+var_A0], r14
0x180077217  mov     r8d, 7EDh
0x18007721d  mov     dword ptr [rsp+0D8h+InternalDeviceIoControl], 0C0000034h
0x180077225  mov     r9d, 0C0000010h
0x18007722b  mov     [rsp+0D8h+OutputBufferLength], 0C000000Eh
0x180077233  mov     ecx, ebx
0x180077235  mov     dword ptr [rsp+0D8h+OutputBuffer], 0C000000Dh
0x18007723d  call    FltpDbgStatus
0x180077242  test    eax, eax
0x180077244  js      loc_180077396
0x18007724a  mov     ebx, 0C01C0014h
0x18007724f  mov     r8d, r14d
0x180077252  cmp     r8d, [rsi+4]
0x180077256  jnb     loc_180077314
0x18007725c  mov     eax, r8d
0x18007725f  lea     rcx, [rax+rax*2]
0x180077263  movzx   edx, word ptr [rsi+rcx*8+0Ch]
0x180077268  mov     [rsp+0D8h+SourceString.MaximumLength], dx
0x18007726d  mov     [rsp+0D8h+SourceString.Length], dx
0x180077272  mov     ecx, [rsi+rcx*8+8]
0x180077276  add     rcx, rsi
0x180077279  mov     [rsp+0D8h+SourceString.Buffer], rcx
0x18007727e  cmp     dx, 60h ; '`'
0x180077282  jz      short loc_180077291
0x180077284  cmp     dx, 62h ; 'b'
0x180077288  jnz     short loc_180077309
0x18007728a  cmp     word ptr [rcx+60h], 5Ch ; '\'
0x18007728f  jnz     short loc_180077309
0x180077291  cmp     word ptr [rcx], 5Ch ; '\'
0x180077295  jnz     short loc_180077309
0x180077297  movzx   eax, word ptr [rcx+2]
0x18007729b  cmp     ax, 3Fh ; '?'
0x18007729f  jz      short loc_1800772A7
0x1800772a1  cmp     ax, 5Ch ; '\'
0x1800772a5  jnz     short loc_180077309
0x1800772a7  cmp     word ptr [rcx+4], 3Fh ; '?'
0x1800772ac  jnz     short loc_180077309
0x1800772ae  cmp     word ptr [rcx+6], 5Ch ; '\'
0x1800772b3  jnz     short loc_180077309
0x1800772b5  cmp     word ptr [rcx+8], 56h ; 'V'
0x1800772ba  jnz     short loc_180077309
0x1800772bc  cmp     word ptr [rcx+0Ah], 6Fh ; 'o'
0x1800772c1  jnz     short loc_180077309
0x1800772c3  cmp     word ptr [rcx+0Ch], 6Ch ; 'l'
0x1800772c8  jnz     short loc_180077309
0x1800772ca  cmp     word ptr [rcx+0Eh], 75h ; 'u'
0x1800772cf  jnz     short loc_180077309
0x1800772d1  cmp     word ptr [rcx+10h], 6Dh ; 'm'
0x1800772d6  jnz     short loc_180077309
0x1800772d8  cmp     word ptr [rcx+12h], 65h ; 'e'
0x1800772dd  jnz     short loc_180077309
0x1800772df  cmp     word ptr [rcx+14h], 7Bh ; '{'
0x1800772e4  jnz     short loc_180077309
0x1800772e6  cmp     word ptr [rcx+26h], 2Dh ; '-'
0x1800772eb  jnz     short loc_180077309
0x1800772ed  cmp     word ptr [rcx+30h], 2Dh ; '-'
0x1800772f2  jnz     short loc_180077309
0x1800772f4  cmp     word ptr [rcx+3Ah], 2Dh ; '-'
0x1800772f9  jnz     short loc_180077309
0x1800772fb  cmp     word ptr [rcx+44h], 2Dh ; '-'
0x180077300  jnz     short loc_180077309
0x180077302  cmp     word ptr [rcx+5Eh], 7Dh ; '}'
0x180077307  jz      short loc_180077311
0x180077309  inc     r8d
0x18007730c  jmp     loc_180077252
0x180077311  mov     ebx, r14d
0x180077314  mov     r8d, 817h
0x18007731a  lea     rdx, aMinkernelFsFil_30; "minkernel\\fs\\filtermgr\\filter\\volum"...
0x180077321  xor     r9d, r9d
0x180077324  mov     ecx, ebx
0x180077326  call    FltpDbgStatus
0x18007732b  test    eax, eax
0x18007732d  js      short loc_180077396
0x18007732f  lea     rdx, [rsp+0D8h+SourceString]; SourceString
0x180077334  lea     rcx, [rdi+80h]; DestinationString
0x18007733b  call    cs:__imp_RtlCopyUnicodeString
0x180077342  nop     dword ptr [rax+rax+00h]
0x180077347  test    r15, r15
0x18007734a  jz      short loc_18007737C
0x18007734c  movzx   eax, word ptr [rdi+80h]
0x180077353  cmp     [r15+2], ax
0x180077358  jb      short loc_18007737C
0x18007735a  lea     rdx, [rdi+80h]; SourceString
0x180077361  mov     rcx, r15; DestinationString
0x180077364  call    cs:__imp_RtlCopyUnicodeString
0x18007736b  nop     dword ptr [rax+rax+00h]
0x180077370  mov     ebx, r14d
0x180077373  jmp     short loc_180077391
0x180077375  mov     ebx, 0C000009Ah
0x18007737a  jmp     short loc_180077396
0x18007737c  test    r12, r12
0x18007737f  jz      short loc_18007738C
0x180077381  movzx   eax, word ptr [rdi+80h]
0x180077388  mov     [r12], eax
0x18007738c  mov     ebx, 0C0000023h
0x180077391  test    rbp, rbp
0x180077394  jz      short loc_1800773AA
0x180077396  mov     edx, 6F764D46h; Tag
0x18007739b  mov     rcx, rbp; P
0x18007739e  call    cs:__imp_ExFreePoolWithTag
0x1800773a5  nop     dword ptr [rax+rax+00h]
0x1800773aa  test    rsi, rsi
0x1800773ad  jz      short loc_1800773C3
0x1800773af  mov     edx, 6F764D46h; Tag
0x1800773b4  mov     rcx, rsi; P
0x1800773b7  call    cs:__imp_ExFreePoolWithTag
0x1800773be  nop     dword ptr [rax+rax+00h]
0x1800773c3  mov     rsi, [rsp+0D8h+var_10]
0x1800773cb  mov     rbp, [rsp+0D8h+arg_8]
0x1800773d3  mov     r13, [rsp+0D8h+var_28]
0x1800773db  mov     rcx, [rsp+0D8h+FileObject]; Object
0x1800773e3  mov     r15, [rsp+0D8h+var_38]
0x1800773eb  mov     r14, [rsp+0D8h+var_30]
0x1800773f3  mov     r12, [rsp+0D8h+var_20]
0x1800773fb  mov     rdi, [rsp+0D8h+var_18]
0x180077403  test    rcx, rcx
0x180077406  jz      short loc_180077414
0x180077408  call    cs:__imp_ObfDereferenceObject
0x18007740f  nop     dword ptr [rax+rax+00h]
0x180077414  mov     eax, ebx
0x180077416  add     rsp, 0D0h
0x18007741d  pop     rbx
0x18007741e  retn
```
