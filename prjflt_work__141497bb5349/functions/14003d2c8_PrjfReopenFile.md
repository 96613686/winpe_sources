# PrjfReopenFile

- ea: `0x14003d2c8`
- end: `0x14003d618`
- name: `PrjfReopenFile`
- size: `848`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject, ACCESS_MASK DesiredAccess, PHANDLE FileHandle, PFILE_OBJECT *)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140007694`
- `0x14002a260`
- `0x140043b24`

## callees

- `0x14000f984`
- `0x14003775c`
- `0x14003d2c8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14003d5f7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003d5f7`
- `ntoskrnl!PsGetHostSilo` at `0x14003d488`
- `ntoskrnl!PsGetHostSilo` at `0x14003d488`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14003d458`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14003d458`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14003d42b`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14003d42b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003d33b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003d33b`
- `FLTMGR!FltGetVolumeFromInstance` at `0x14003d385`
- `FLTMGR!FltGetVolumeFromInstance` at `0x14003d385`
- `FLTMGR!FltGetVolumeName` at `0x14003d3a5`
- `FLTMGR!FltGetVolumeName` at `0x14003d40a`
- `FLTMGR!FltGetVolumeName` at `0x14003d3a5`
- `FLTMGR!FltGetVolumeName` at `0x14003d40a`
- `FLTMGR!FltObjectDereference` at `0x14003d5dd`
- `FLTMGR!FltObjectDereference` at `0x14003d5dd`
- `FLTMGR!FltCreateFileEx2` at `0x14003d530`
- `FLTMGR!FltCreateFileEx2` at `0x14003d530`
- `FLTMGR!FltQueryInformationFile` at `0x14003d368`
- `FLTMGR!FltQueryInformationFile` at `0x14003d368`

## pseudocode

```c
__int64 __fastcall PrjfReopenFile(
        PFLT_INSTANCE Instance,
        PFILE_OBJECT FileObject,
        ACCESS_MASK DesiredAccess,
        PHANDLE FileHandle,
        PFILE_OBJECT *FileObjecta)
{
  int VolumeFromInstance; // ebx
  int v10; // edx
  int v11; // r8d
  ULONG BufferSizeNeeded; // [rsp+80h] [rbp-80h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-78h] BYREF
  PFLT_VOLUME RetVolume; // [rsp+98h] [rbp-68h] BYREF
  ULONG LengthReturned; // [rsp+A0h] [rbp-60h] BYREF
  __int64 FileInformation; // [rsp+A8h] [rbp-58h] BYREF
  UNICODE_STRING Source; // [rsp+B0h] [rbp-50h] BYREF
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+C0h] [rbp-40h] BYREF
  __int64 HostSilo; // [rsp+E0h] [rbp-20h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+E8h] [rbp-18h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+118h] [rbp+18h] BYREF

  FileInformation = 0;
  LengthReturned = 0;
  RetVolume = 0;
  BufferSizeNeeded = 0;
  LOWORD(HostSilo) = 0;
  DestinationString = 0;
  Source = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  memset(&DriverContext, 0, sizeof(DriverContext));
  RtlInitUnicodeString(&DestinationString, 0);
  VolumeFromInstance = FltQueryInformationFile(
                         Instance,
                         FileObject,
                         &FileInformation,
                         8u,
                         FileInternalInformation,
                         &LengthReturned);
  if ( VolumeFromInstance >= 0 )
  {
    VolumeFromInstance = FltGetVolumeFromInstance(Instance, &RetVolume);
    if ( VolumeFromInstance >= 0 )
    {
      VolumeFromInstance = FltGetVolumeName(RetVolume, 0, &BufferSizeNeeded);
      if ( (int)(VolumeFromInstance + 0x80000000) < 0 || VolumeFromInstance == -1073741789 )
      {
        if ( (unsigned __int16)(BufferSizeNeeded + 10) < (unsigned __int16)BufferSizeNeeded )
        {
          VolumeFromInstance = -1073741675;
          DestinationString.MaximumLength = -1;
        }
        else
        {
          DestinationString.MaximumLength = BufferSizeNeeded + 10;
          VolumeFromInstance = PrjfAllocateUnicodeString(1852197456, (__int64)&DestinationString);
          if ( VolumeFromInstance >= 0 )
          {
            VolumeFromInstance = FltGetVolumeName(RetVolume, &DestinationString, &BufferSizeNeeded);
            if ( VolumeFromInstance >= 0 )
            {
              VolumeFromInstance = RtlAppendUnicodeToString(&DestinationString, L"\\");
              if ( VolumeFromInstance >= 0 )
              {
                *(_DWORD *)&Source.Length = 524296;
                Source.Buffer = (PWSTR)&FileInformation;
                VolumeFromInstance = RtlAppendUnicodeStringToString(&DestinationString, &Source);
                if ( VolumeFromInstance >= 0 )
                {
                  memset(&DriverContext, 0, sizeof(DriverContext));
                  HostSilo = 1;
                  DriverContext.Size = 40;
                  HostSilo = PsGetHostSilo();
                  ObjectAttributes.Length = 48;
                  ObjectAttributes.ObjectName = &DestinationString;
                  ObjectAttributes.RootDirectory = 0;
                  ObjectAttributes.Attributes = 512;
                  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
                  VolumeFromInstance = FltCreateFileEx2(
                                         Globals,
                                         Instance,
                                         FileHandle,
                                         FileObjecta,
                                         DesiredAccess,
                                         &ObjectAttributes,
                                         &IoStatusBlock,
                                         0,
                                         0,
                                         7u,
                                         1u,
                                         0x202028u,
                                         0,
                                         0,
                                         0x800u,
                                         &DriverContext);
                  if ( VolumeFromInstance < 0
                    && ((BYTE1(xmmword_14001A3D0) & 4) != 0
                     || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED) )
                  {
                    LOBYTE(v10) = BYTE1(xmmword_14001A3D0) & 4;
                    LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
                    WPP_RECORDER_AND_TRACE_SF_sDdZZ(
                      522,
                      v10,
                      v11,
                      *((_QWORD *)WPP_GLOBAL_Control + 8),
                      2,
                      10,
                      156,
                      (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
                      (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
                      185,
                      VolumeFromInstance,
                      (__int64)&FileObject->FileName,
                      (__int64)&DestinationString);
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  if ( RetVolume )
    FltObjectDereference(RetVolume);
  if ( DestinationString.Buffer )
    ExFreePoolWithTag(DestinationString.Buffer, 0x6E664A50u);
  return (unsigned int)VolumeFromInstance;
}

```

## disassembly

```asm
0x14003d2c8  push    rbp
0x14003d2ca  push    rbx
0x14003d2cb  push    rsi
0x14003d2cc  push    rdi
0x14003d2cd  push    r13
0x14003d2cf  push    r14
0x14003d2d1  push    r15
0x14003d2d3  lea     rbp, [rsp-30h]
0x14003d2d8  sub     rsp, 130h
0x14003d2df  xorps   xmm0, xmm0
0x14003d2e2  mov     [rbp+60h+FileInformation], 0
0x14003d2ea  mov     rsi, rdx
0x14003d2ed  mov     [rbp+60h+var_C0], 0
0x14003d2f4  mov     rdi, rcx
0x14003d2f7  mov     [rbp+60h+RetVolume], 0
0x14003d2ff  xorps   xmm1, xmm1
0x14003d302  mov     [rbp+60h+BufferSizeNeeded], 0
0x14003d309  xor     eax, eax
0x14003d30b  lea     rcx, [rbp+60h+DestinationString]; DestinationString
0x14003d30f  movups  xmmword ptr [rbp+60h+ObjectAttributes.ObjectName], xmm0
0x14003d313  xor     edx, edx; SourceString
0x14003d315  mov     word ptr [rbp+60h+var_80], ax
0x14003d319  movups  xmmword ptr [rbp+60h+ObjectAttributes+1Ch], xmm0
0x14003d31d  mov     r14, r9
0x14003d320  mov     r15d, r8d
0x14003d323  movups  xmmword ptr [rbp+60h+DestinationString.Length], xmm0
0x14003d327  movups  xmmword ptr [rbp+60h+Source.Length], xmm0
0x14003d32b  movups  xmmword ptr [rbp+60h+var_48], xmm1
0x14003d32f  movups  xmmword ptr [rbp+60h+ObjectAttributes.Length], xmm0
0x14003d333  movups  xmmword ptr [rbp+60h+var_A0.Size], xmm0
0x14003d337  movups  xmmword ptr [rbp+60h+var_A0.DeviceObjectHint], xmm0
0x14003d33b  call    cs:__imp_RtlInitUnicodeString
0x14003d342  nop     dword ptr [rax+rax+00h]
0x14003d347  lea     rax, [rbp+60h+var_C0]
0x14003d34b  mov     r9d, 8; Length
0x14003d351  mov     [rsp+160h+LengthReturned], rax; LengthReturned
0x14003d356  lea     r8, [rbp+60h+FileInformation]; FileInformation
0x14003d35a  mov     rdx, rsi; FileObject
0x14003d35d  mov     [rsp+160h+FileInformationClass], 6; FileInformationClass
0x14003d365  mov     rcx, rdi; Instance
0x14003d368  call    cs:__imp_FltQueryInformationFile
0x14003d36f  nop     dword ptr [rax+rax+00h]
0x14003d374  mov     ebx, eax
0x14003d376  test    eax, eax
0x14003d378  js      loc_14003D5D4
0x14003d37e  lea     rdx, [rbp+60h+RetVolume]; RetVolume
0x14003d382  mov     rcx, rdi; Instance
0x14003d385  call    cs:__imp_FltGetVolumeFromInstance
0x14003d38c  nop     dword ptr [rax+rax+00h]
0x14003d391  mov     ebx, eax
0x14003d393  test    eax, eax
0x14003d395  js      loc_14003D5D4
0x14003d39b  mov     rcx, [rbp+60h+RetVolume]; Volume
0x14003d39f  lea     r8, [rbp+60h+BufferSizeNeeded]; BufferSizeNeeded
0x14003d3a3  xor     edx, edx; VolumeName
0x14003d3a5  call    cs:__imp_FltGetVolumeName
0x14003d3ac  nop     dword ptr [rax+rax+00h]
0x14003d3b1  mov     ecx, 80000000h
0x14003d3b6  mov     ebx, eax
0x14003d3b8  add     eax, ecx
0x14003d3ba  test    ecx, eax
0x14003d3bc  jnz     short loc_14003D3CA
0x14003d3be  cmp     ebx, 0C0000023h
0x14003d3c4  jnz     loc_14003D5D4
0x14003d3ca  movzx   eax, word ptr [rbp+60h+BufferSizeNeeded]
0x14003d3ce  mov     r13d, 0Ah
0x14003d3d4  add     ax, r13w
0x14003d3d8  cmp     ax, word ptr [rbp+60h+BufferSizeNeeded]
0x14003d3dc  jb      loc_14003D5C6
0x14003d3e2  lea     rdx, [rbp+60h+DestinationString]
0x14003d3e6  mov     [rbp+60h+DestinationString.MaximumLength], ax
0x14003d3ea  mov     ecx, 6E664A50h
0x14003d3ef  call    PrjfAllocateUnicodeString
0x14003d3f4  mov     ebx, eax
0x14003d3f6  test    eax, eax
0x14003d3f8  js      loc_14003D5D4
0x14003d3fe  mov     rcx, [rbp+60h+RetVolume]; Volume
0x14003d402  lea     r8, [rbp+60h+BufferSizeNeeded]; BufferSizeNeeded
0x14003d406  lea     rdx, [rbp+60h+DestinationString]; VolumeName
0x14003d40a  call    cs:__imp_FltGetVolumeName
0x14003d411  nop     dword ptr [rax+rax+00h]
0x14003d416  mov     ebx, eax
0x14003d418  test    eax, eax
0x14003d41a  js      loc_14003D5D4
0x14003d420  lea     rdx, asc_14001595C; "\\"
0x14003d427  lea     rcx, [rbp+60h+DestinationString]; Destination
0x14003d42b  call    cs:__imp_RtlAppendUnicodeToString
0x14003d432  nop     dword ptr [rax+rax+00h]
0x14003d437  mov     ebx, eax
0x14003d439  test    eax, eax
0x14003d43b  js      loc_14003D5D4
0x14003d441  lea     rax, [rbp+60h+FileInformation]
0x14003d445  mov     dword ptr [rbp+60h+Source.Length], 80008h
0x14003d44c  lea     rdx, [rbp+60h+Source]; Source
0x14003d450  mov     [rbp+60h+Source.Buffer], rax
0x14003d454  lea     rcx, [rbp+60h+DestinationString]; Destination
0x14003d458  call    cs:__imp_RtlAppendUnicodeStringToString
0x14003d45f  nop     dword ptr [rax+rax+00h]
0x14003d464  mov     ebx, eax
0x14003d466  test    eax, eax
0x14003d468  js      loc_14003D5D4
0x14003d46e  lea     eax, [r13+1Eh]
0x14003d472  xorps   xmm0, xmm0
0x14003d475  lea     ebx, [rax-27h]
0x14003d478  movups  xmmword ptr [rbp+60h+var_A0.Size], xmm0
0x14003d47c  mov     [rbp+60h+var_80], rbx
0x14003d480  movups  xmmword ptr [rbp+60h+var_A0.DeviceObjectHint], xmm0
0x14003d484  mov     [rbp+60h+var_A0.Size], ax
0x14003d488  call    cs:__imp_PsGetHostSilo
0x14003d48f  nop     dword ptr [rax+rax+00h]
0x14003d494  mov     r9, [rbp+60h+FileObject]; FileObject
0x14003d49b  xorps   xmm0, xmm0
0x14003d49e  mov     rcx, cs:Globals; Filter
0x14003d4a5  mov     r8, r14; FileHandle
0x14003d4a8  mov     [rbp+60h+var_80], rax
0x14003d4ac  mov     rdx, rdi; Instance
0x14003d4af  lea     rax, [rbp+60h+DestinationString]
0x14003d4b3  mov     [rbp+60h+ObjectAttributes.Length], 30h ; '0'
0x14003d4ba  mov     [rbp+60h+ObjectAttributes.ObjectName], rax
0x14003d4be  lea     rax, [rbp+60h+var_A0]
0x14003d4c2  mov     [rsp+160h+DriverContext], rax; DriverContext
0x14003d4c7  lea     rax, [rbp+60h+var_48]
0x14003d4cb  mov     [rsp+160h+Flags], 800h; Flags
0x14003d4d3  mov     [rsp+160h+EaLength], 0; EaLength
0x14003d4db  mov     [rsp+160h+EaBuffer], 0; EaBuffer
0x14003d4e4  mov     [rsp+160h+CreateOptions], 202028h; CreateOptions
0x14003d4ec  mov     [rsp+160h+CreateDisposition], ebx; CreateDisposition
0x14003d4f0  mov     [rsp+160h+ShareAccess], 7; ShareAccess
0x14003d4f8  mov     [rsp+160h+FileAttributes], 0; FileAttributes
0x14003d500  mov     [rsp+160h+AllocationSize], 0; AllocationSize
0x14003d509  mov     [rsp+160h+IoStatusBlock], rax; IoStatusBlock
0x14003d50e  lea     rax, [rbp+60h+ObjectAttributes]
0x14003d512  mov     [rsp+160h+LengthReturned], rax; ObjectAttributes
0x14003d517  mov     [rsp+160h+FileInformationClass], r15d; DesiredAccess
0x14003d51c  mov     [rbp+60h+ObjectAttributes.RootDirectory], 0
0x14003d524  mov     [rbp+60h+ObjectAttributes.Attributes], 200h
0x14003d52b  movdqu  xmmword ptr [rbp+60h+ObjectAttributes.SecurityDescriptor], xmm0
0x14003d530  call    cs:__imp_FltCreateFileEx2
0x14003d537  nop     dword ptr [rax+rax+00h]
0x14003d53c  mov     ebx, eax
0x14003d53e  test    eax, eax
0x14003d540  jns     loc_14003D5D4
0x14003d546  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14003d54c  lea     rax, WPP_RECORDER_INITIALIZED
0x14003d553  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003d55a  setnz   r8b
0x14003d55e  and     dl, 4
0x14003d561  jnz     short loc_14003D568
0x14003d563  test    r8b, r8b
0x14003d566  jz      short loc_14003D5D4
0x14003d568  lea     r9, [rbp+60h+DestinationString]
0x14003d56c  mov     ecx, 20Ah
0x14003d571  mov     [rsp+160h+EaBuffer], r9
0x14003d576  lea     rax, [rsi+58h]
0x14003d57a  mov     r9, cs:WPP_GLOBAL_Control
0x14003d581  mov     qword ptr [rsp+160h+CreateOptions], rax
0x14003d586  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14003d58d  mov     [rsp+160h+CreateDisposition], ebx
0x14003d591  mov     [rsp+160h+ShareAccess], 18B9h
0x14003d599  mov     r9, [r9+40h]
0x14003d59d  mov     qword ptr [rsp+160h+FileAttributes], rax
0x14003d5a2  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x14003d5a9  mov     [rsp+160h+AllocationSize], rax
0x14003d5ae  mov     word ptr [rsp+160h+IoStatusBlock], 9Ch
0x14003d5b5  mov     dword ptr [rsp+160h+LengthReturned], r13d
0x14003d5ba  mov     byte ptr [rsp+160h+FileInformationClass], 2
0x14003d5bf  call    WPP_RECORDER_AND_TRACE_SF_sDdZZ
0x14003d5c4  jmp     short loc_14003D5D4
0x14003d5c6  mov     eax, 0FFFFh
0x14003d5cb  mov     ebx, 0C0000095h
0x14003d5d0  mov     [rbp+60h+DestinationString.MaximumLength], ax
0x14003d5d4  mov     rcx, [rbp+60h+RetVolume]; FltObject
0x14003d5d8  test    rcx, rcx
0x14003d5db  jz      short loc_14003D5E9
0x14003d5dd  call    cs:__imp_FltObjectDereference
0x14003d5e4  nop     dword ptr [rax+rax+00h]
0x14003d5e9  mov     rcx, [rbp+60h+DestinationString.Buffer]; P
0x14003d5ed  test    rcx, rcx
0x14003d5f0  jz      short loc_14003D603
0x14003d5f2  mov     edx, 6E664A50h; Tag
0x14003d5f7  call    cs:__imp_ExFreePoolWithTag
0x14003d5fe  nop     dword ptr [rax+rax+00h]
0x14003d603  mov     eax, ebx
0x14003d605  add     rsp, 130h
0x14003d60c  pop     r15
0x14003d60e  pop     r14
0x14003d610  pop     r13
0x14003d612  pop     rdi
0x14003d613  pop     rsi
0x14003d614  pop     rbx
0x14003d615  pop     rbp
0x14003d616  retn
```
