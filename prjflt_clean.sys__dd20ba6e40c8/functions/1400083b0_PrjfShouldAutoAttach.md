# PrjfShouldAutoAttach

- ea: `0x1400083b0`
- end: `0x1400089cf`
- name: `PrjfShouldAutoAttach`
- size: `1567`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, PFLT_VOLUME Volume)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14003f240`

## callees

- `0x1400083b0`
- `0x14000b1d0`
- `0x14000bb80`
- `0x14000d128`
- `0x14003775c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000895d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000895d`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14000868c`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14000868c`
- `ntoskrnl!RtlInitUnicodeString` at `0x140008416`
- `ntoskrnl!RtlInitUnicodeString` at `0x140008416`
- `ntoskrnl!ObfDereferenceObject` at `0x140008972`
- `ntoskrnl!ObfDereferenceObject` at `0x140008972`
- `FLTMGR!FltFreePoolAlignedWithTag` at `0x1400089a4`
- `FLTMGR!FltFreePoolAlignedWithTag` at `0x1400089a4`
- `FLTMGR!FltAllocatePoolAlignedWithTag` at `0x1400087a5`
- `FLTMGR!FltAllocatePoolAlignedWithTag` at `0x1400087a5`
- `FLTMGR!FltGetVolumeName` at `0x140008498`
- `FLTMGR!FltGetVolumeName` at `0x140008617`
- `FLTMGR!FltGetVolumeName` at `0x140008498`
- `FLTMGR!FltGetVolumeName` at `0x140008617`
- `FLTMGR!FltCreateSystemVolumeInformationFolder` at `0x140008425`
- `FLTMGR!FltCreateSystemVolumeInformationFolder` at `0x140008425`
- `FLTMGR!FltReadFile` at `0x1400087e7`
- `FLTMGR!FltReadFile` at `0x1400087e7`
- `FLTMGR!FltCreateFileEx` at `0x140008772`
- `FLTMGR!FltCreateFileEx` at `0x140008772`
- `FLTMGR!FltClose` at `0x140008987`
- `FLTMGR!FltClose` at `0x140008987`

## pseudocode

```c
char __fastcall PrjfShouldAutoAttach(PFLT_INSTANCE Instance, PFLT_VOLUME Volume)
{
  char v3; // r14
  char v5; // di
  PVOID PoolAlignedWithTag; // rsi
  __int64 v7; // rdx
  __int64 v8; // r8
  NTSTATUS SystemVolumeInformationFolder; // r9d
  __int64 v10; // rcx
  __int64 v11; // r9
  unsigned __int16 v12; // ax
  unsigned int v13; // eax
  int v14; // r9d
  NTSTATUS VolumeName; // r9d
  NTSTATUS appended; // r9d
  int v17; // edx
  int v18; // r8d
  NTSTATUS v19; // r9d
  __int16 IoStatusBlock; // [rsp+30h] [rbp-99h]
  char ShareAccess; // [rsp+48h] [rbp-81h]
  char CreateDisposition; // [rsp+50h] [rbp-79h]
  int v24; // [rsp+80h] [rbp-49h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-41h] BYREF
  PFILE_OBJECT FileObject; // [rsp+98h] [rbp-31h] BYREF
  union _LARGE_INTEGER ByteOffset; // [rsp+A0h] [rbp-29h] BYREF
  void *FileHandle; // [rsp+A8h] [rbp-21h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B0h] [rbp-19h] BYREF
  struct _IO_STATUS_BLOCK v30; // [rsp+E0h] [rbp+17h] BYREF
  ULONG BufferSizeNeeded; // [rsp+140h] [rbp+77h] BYREF
  ULONG BytesRead; // [rsp+148h] [rbp+7Fh] BYREF

  v3 = 0;
  BufferSizeNeeded = 0;
  FileHandle = 0;
  FileObject = 0;
  v24 = 0;
  v5 = 0;
  ByteOffset.QuadPart = 0;
  DestinationString = 0;
  PoolAlignedWithTag = 0;
  BytesRead = 0;
  memset(&ObjectAttributes, 0, 44);
  v30 = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  SystemVolumeInformationFolder = FltCreateSystemVolumeInformationFolder(Instance);
  if ( SystemVolumeInformationFolder >= 0 )
  {
    if ( FltGetVolumeName(Volume, 0, &BufferSizeNeeded) == -1073741789 )
    {
      v12 = BufferSizeNeeded;
      if ( BufferSizeNeeded > 0xFFFF )
      {
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v10, v7, v8, v11);
        v12 = BufferSizeNeeded;
      }
      v13 = 2 * v12;
      if ( v13 > 0xFFFF )
      {
        DestinationString.MaximumLength = -1;
        LOBYTE(v8) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        LOBYTE(v7) = xmmword_14001A3D0 & 2;
        if ( (xmmword_14001A3D0 & 2) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          CreateDisposition = -107;
          ShareAccess = -119;
          IoStatusBlock = 88;
          goto LABEL_46;
        }
      }
      else if ( (unsigned __int16)(v13 + 8) >= (unsigned __int16)v13 )
      {
        if ( (unsigned __int16)(v13 + 80) < (unsigned __int16)(v13 + 8) )
        {
          DestinationString.MaximumLength = -1;
          LOBYTE(v8) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          LOBYTE(v7) = xmmword_14001A3D0 & 2;
          if ( (xmmword_14001A3D0 & 2) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            CreateDisposition = -107;
            ShareAccess = -103;
            IoStatusBlock = 90;
            goto LABEL_46;
          }
        }
        else
        {
          DestinationString.MaximumLength = v13 + 80;
          v14 = PrjfAllocateUnicodeString(1852197456, &DestinationString, v8, v11);
          if ( v14 >= 0 )
          {
            VolumeName = FltGetVolumeName(Volume, &DestinationString, &BufferSizeNeeded);
            if ( VolumeName >= 0 )
            {
              appended = RtlAppendUnicodeToString(&DestinationString, L"\\System Volume Information\\Gvflt.md");
              if ( appended >= 0 )
              {
                ObjectAttributes.ObjectName = &DestinationString;
                ObjectAttributes.Length = 48;
                ObjectAttributes.RootDirectory = 0;
                ObjectAttributes.Attributes = 512;
                *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
                if ( FltCreateFileEx(
                       Globals,
                       Instance,
                       &FileHandle,
                       &FileObject,
                       0x1F01FFu,
                       &ObjectAttributes,
                       &v30,
                       0,
                       6u,
                       1u,
                       1u,
                       0,
                       0,
                       0,
                       0) >= 0 )
                {
                  ByteOffset.QuadPart = 0;
                  BufferSizeNeeded = 4;
                  PoolAlignedWithTag = FltAllocatePoolAlignedWithTag(Instance, PagedPool, 0x1000u, 0x69764A50u);
                  if ( PoolAlignedWithTag )
                  {
                    v19 = FltReadFile(
                            Instance,
                            FileObject,
                            &ByteOffset,
                            0x1000u,
                            PoolAlignedWithTag,
                            1u,
                            &BytesRead,
                            0,
                            0);
                    if ( v19 >= 0 )
                    {
                      if ( BytesRead >= BufferSizeNeeded )
                      {
                        memmove(&v24, PoolAlignedWithTag, BufferSizeNeeded);
                        v5 = v24;
                      }
                      if ( (v5 & 1) != 0 )
                        v3 = 1;
                    }
                    else if ( (xmmword_14001A3D0 & 2) != 0
                           || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                    {
                      LOBYTE(v17) = xmmword_14001A3D0 & 2;
                      LOBYTE(v18) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
                      WPP_RECORDER_AND_TRACE_SF_sDL(
                        513,
                        v17,
                        v18,
                        *((_QWORD *)WPP_GLOBAL_Control + 8),
                        2,
                        1,
                        94,
                        (__int64)&WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
                        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
                        236,
                        v19);
                    }
                  }
                }
              }
              else
              {
                LOBYTE(v8) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
                LOBYTE(v7) = xmmword_14001A3D0 & 2;
                if ( (xmmword_14001A3D0 & 2) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                {
                  CreateDisposition = appended;
                  ShareAccess = -79;
                  IoStatusBlock = 93;
                  goto LABEL_46;
                }
              }
            }
            else
            {
              LOBYTE(v8) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
              LOBYTE(v7) = xmmword_14001A3D0 & 2;
              if ( (xmmword_14001A3D0 & 2) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                CreateDisposition = VolumeName;
                ShareAccess = -87;
                IoStatusBlock = 92;
                goto LABEL_46;
              }
            }
          }
          else
          {
            LOBYTE(v8) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            LOBYTE(v7) = xmmword_14001A3D0 & 2;
            if ( (xmmword_14001A3D0 & 2) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              CreateDisposition = v14;
              ShareAccess = -95;
              IoStatusBlock = 91;
              goto LABEL_46;
            }
          }
        }
      }
      else
      {
        DestinationString.MaximumLength = -1;
        LOBYTE(v8) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        LOBYTE(v7) = xmmword_14001A3D0 & 2;
        if ( (xmmword_14001A3D0 & 2) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          CreateDisposition = -107;
          ShareAccess = -111;
          IoStatusBlock = 89;
          goto LABEL_46;
        }
      }
    }
    else
    {
      LOBYTE(v8) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      LOBYTE(v7) = xmmword_14001A3D0 & 2;
      if ( (xmmword_14001A3D0 & 2) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        CreateDisposition = 16;
        ShareAccess = 0x80;
        IoStatusBlock = 87;
        goto LABEL_46;
      }
    }
  }
  else
  {
    LOBYTE(v8) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    LOBYTE(v7) = xmmword_14001A3D0 & 2;
    if ( (xmmword_14001A3D0 & 2) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      CreateDisposition = SystemVolumeInformationFolder;
      ShareAccess = 119;
      IoStatusBlock = 86;
LABEL_46:
      WPP_RECORDER_AND_TRACE_SF_sDL(
        513,
        v7,
        v8,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        1,
        IoStatusBlock,
        (__int64)&WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
        ShareAccess,
        CreateDisposition);
    }
  }
  if ( DestinationString.Buffer )
    ExFreePoolWithTag(DestinationString.Buffer, 0x6E664A50u);
  if ( FileObject )
    ObfDereferenceObject(FileObject);
  if ( FileHandle )
    FltClose(FileHandle);
  if ( PoolAlignedWithTag )
    FltFreePoolAlignedWithTag(Instance, PoolAlignedWithTag, 0x69764A50u);
  return v3;
}

```

## disassembly

```asm
0x1400083b0  mov     [rsp-8+arg_0], rbx
0x1400083b5  push    rbp
0x1400083b6  push    rsi
0x1400083b7  push    rdi
0x1400083b8  push    r12
0x1400083ba  push    r13
0x1400083bc  push    r14
0x1400083be  push    r15
0x1400083c0  lea     rbp, [rsp-27h]
0x1400083c5  sub     rsp, 0F0h
0x1400083cc  xor     r12d, r12d
0x1400083cf  xorps   xmm0, xmm0
0x1400083d2  mov     rbx, rdx
0x1400083d5  movzx   r14d, r12b
0x1400083d9  mov     r15, rcx
0x1400083dc  mov     [rbp+57h+BufferSizeNeeded], r12d
0x1400083e0  movups  xmmword ptr [rbp+57h+var_70.ObjectName], xmm0
0x1400083e4  xor     eax, eax
0x1400083e6  mov     [rbp+57h+FileHandle], r12
0x1400083ea  xor     edx, edx; SourceString
0x1400083ec  mov     [rbp+57h+FileObject], r12
0x1400083f0  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400083f4  mov     [rbp+57h+var_A0], r12d
0x1400083f8  movups  xmmword ptr [rbp+57h+var_70+1Ch], xmm0
0x1400083fc  mov     edi, r12d
0x1400083ff  mov     qword ptr [rbp+57h+ByteOffset], r12
0x140008403  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140008407  mov     esi, r12d
0x14000840a  mov     [rbp+57h+BytesRead], r12d
0x14000840e  movups  xmmword ptr [rbp+57h+var_70.Length], xmm0
0x140008412  movups  xmmword ptr [rbp+57h+var_40], xmm0
0x140008416  call    cs:__imp_RtlInitUnicodeString
0x14000841d  nop     dword ptr [rax+rax+00h]
0x140008422  mov     rcx, r15; Instance
0x140008425  call    cs:__imp_FltCreateSystemVolumeInformationFolder
0x14000842c  nop     dword ptr [rax+rax+00h]
0x140008431  mov     r9d, eax
0x140008434  test    eax, eax
0x140008436  jns     short loc_14000848F
0x140008438  mov     dl, byte ptr cs:xmmword_14001A3D0
0x14000843e  lea     rax, WPP_RECORDER_INITIALIZED
0x140008445  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000844c  setnz   r8b
0x140008450  and     dl, 2
0x140008453  jnz     short loc_14000845E
0x140008455  test    r8b, r8b
0x140008458  jz      loc_14000894F
0x14000845e  mov     dword ptr [rsp+120h+CreateDisposition], r9d
0x140008463  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14000846a  mov     dword ptr [rsp+120h+ShareAccess], 1077h
0x140008472  mov     qword ptr [rsp+120h+FileAttributes], rax
0x140008477  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x14000847e  mov     [rsp+120h+AllocationSize], rax
0x140008483  mov     word ptr [rsp+120h+IoStatusBlock], 56h ; 'V'
0x14000848a  jmp     loc_14000892D
0x14000848f  lea     r8, [rbp+57h+BufferSizeNeeded]; BufferSizeNeeded
0x140008493  xor     edx, edx; VolumeName
0x140008495  mov     rcx, rbx; Volume
0x140008498  call    cs:__imp_FltGetVolumeName
0x14000849f  nop     dword ptr [rax+rax+00h]
0x1400084a4  cmp     eax, 0C0000023h
0x1400084a9  jz      short loc_140008505
0x1400084ab  mov     dl, byte ptr cs:xmmword_14001A3D0
0x1400084b1  lea     rax, WPP_RECORDER_INITIALIZED
0x1400084b8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400084bf  setnz   r8b
0x1400084c3  and     dl, 2
0x1400084c6  jnz     short loc_1400084D1
0x1400084c8  test    r8b, r8b
0x1400084cb  jz      loc_14000894F
0x1400084d1  mov     dword ptr [rsp+120h+CreateDisposition], 0C0000010h
0x1400084d9  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400084e0  mov     dword ptr [rsp+120h+ShareAccess], 1080h
0x1400084e8  mov     qword ptr [rsp+120h+FileAttributes], rax
0x1400084ed  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x1400084f4  mov     [rsp+120h+AllocationSize], rax
0x1400084f9  mov     word ptr [rsp+120h+IoStatusBlock], 57h ; 'W'
0x140008500  jmp     loc_14000892D
0x140008505  mov     eax, [rbp+57h+BufferSizeNeeded]
0x140008508  mov     r13d, 0FFFFh
0x14000850e  cmp     eax, r13d
0x140008511  jbe     short loc_14000851B
0x140008513  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140008518  mov     eax, [rbp+57h+BufferSizeNeeded]
0x14000851b  movzx   eax, ax
0x14000851e  add     eax, eax
0x140008520  cmp     eax, r13d
0x140008523  ja      loc_1400088D7
0x140008529  lea     ecx, [rax+8]
0x14000852c  cmp     cx, ax
0x14000852f  jnb     short loc_140008590
0x140008531  mov     [rbp+57h+DestinationString.MaximumLength], r13w
0x140008536  mov     dl, byte ptr cs:xmmword_14001A3D0
0x14000853c  lea     rax, WPP_RECORDER_INITIALIZED
0x140008543  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000854a  setnz   r8b
0x14000854e  and     dl, 2
0x140008551  jnz     short loc_14000855C
0x140008553  test    r8b, r8b
0x140008556  jz      loc_14000894F
0x14000855c  mov     dword ptr [rsp+120h+CreateDisposition], 0C0000095h
0x140008564  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14000856b  mov     dword ptr [rsp+120h+ShareAccess], 1091h
0x140008573  mov     qword ptr [rsp+120h+FileAttributes], rax
0x140008578  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x14000857f  mov     [rsp+120h+AllocationSize], rax
0x140008584  mov     word ptr [rsp+120h+IoStatusBlock], 59h ; 'Y'
0x14000858b  jmp     loc_14000892D
0x140008590  lea     eax, [rcx+48h]
0x140008593  cmp     ax, cx
0x140008596  jb      loc_14000887B
0x14000859c  lea     rdx, [rbp+57h+DestinationString]
0x1400085a0  mov     [rbp+57h+DestinationString.MaximumLength], ax
0x1400085a4  mov     ecx, 6E664A50h
0x1400085a9  call    PrjfAllocateUnicodeString
0x1400085ae  mov     r9d, eax
0x1400085b1  test    eax, eax
0x1400085b3  jns     short loc_14000860C
0x1400085b5  mov     dl, byte ptr cs:xmmword_14001A3D0
0x1400085bb  lea     rax, WPP_RECORDER_INITIALIZED
0x1400085c2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400085c9  setnz   r8b
0x1400085cd  and     dl, 2
0x1400085d0  jnz     short loc_1400085DB
0x1400085d2  test    r8b, r8b
0x1400085d5  jz      loc_14000894F
0x1400085db  mov     dword ptr [rsp+120h+CreateDisposition], r9d
0x1400085e0  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400085e7  mov     dword ptr [rsp+120h+ShareAccess], 10A1h
0x1400085ef  mov     qword ptr [rsp+120h+FileAttributes], rax
0x1400085f4  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x1400085fb  mov     [rsp+120h+AllocationSize], rax
0x140008600  mov     word ptr [rsp+120h+IoStatusBlock], 5Bh ; '['
0x140008607  jmp     loc_14000892D
0x14000860c  lea     r8, [rbp+57h+BufferSizeNeeded]; BufferSizeNeeded
0x140008610  mov     rcx, rbx; Volume
0x140008613  lea     rdx, [rbp+57h+DestinationString]; VolumeName
0x140008617  call    cs:__imp_FltGetVolumeName
0x14000861e  nop     dword ptr [rax+rax+00h]
0x140008623  mov     r9d, eax
0x140008626  test    eax, eax
0x140008628  jns     short loc_140008681
0x14000862a  mov     dl, byte ptr cs:xmmword_14001A3D0
0x140008630  lea     rax, WPP_RECORDER_INITIALIZED
0x140008637  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000863e  setnz   r8b
0x140008642  and     dl, 2
0x140008645  jnz     short loc_140008650
0x140008647  test    r8b, r8b
0x14000864a  jz      loc_14000894F
0x140008650  mov     dword ptr [rsp+120h+CreateDisposition], r9d
0x140008655  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14000865c  mov     dword ptr [rsp+120h+ShareAccess], 10A9h
0x140008664  mov     qword ptr [rsp+120h+FileAttributes], rax
0x140008669  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x140008670  mov     [rsp+120h+AllocationSize], rax
0x140008675  mov     word ptr [rsp+120h+IoStatusBlock], 5Ch ; '\'
0x14000867c  jmp     loc_14000892D
0x140008681  lea     rdx, Source; "\\System Volume Information\\Gvflt.md"
0x140008688  lea     rcx, [rbp+57h+DestinationString]; Destination
0x14000868c  call    cs:__imp_RtlAppendUnicodeToString
0x140008693  nop     dword ptr [rax+rax+00h]
0x140008698  mov     r9d, eax
0x14000869b  test    eax, eax
0x14000869d  jns     short loc_1400086F6
0x14000869f  mov     dl, byte ptr cs:xmmword_14001A3D0
0x1400086a5  lea     rax, WPP_RECORDER_INITIALIZED
0x1400086ac  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400086b3  setnz   r8b
0x1400086b7  and     dl, 2
0x1400086ba  jnz     short loc_1400086C5
0x1400086bc  test    r8b, r8b
0x1400086bf  jz      loc_14000894F
0x1400086c5  mov     dword ptr [rsp+120h+CreateDisposition], r9d
0x1400086ca  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400086d1  mov     dword ptr [rsp+120h+ShareAccess], 10B1h
0x1400086d9  mov     qword ptr [rsp+120h+FileAttributes], rax
0x1400086de  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x1400086e5  mov     [rsp+120h+AllocationSize], rax
0x1400086ea  mov     word ptr [rsp+120h+IoStatusBlock], 5Dh ; ']'
0x1400086f1  jmp     loc_14000892D
0x1400086f6  mov     rcx, cs:Globals; Filter
0x1400086fd  lea     rax, [rbp+57h+DestinationString]
0x140008701  mov     [rsp+120h+Flags], r12d; Flags
0x140008706  lea     r9, [rbp+57h+FileObject]; FileObject
0x14000870a  mov     [rsp+120h+EaLength], r12d; EaLength
0x14000870f  lea     r8, [rbp+57h+FileHandle]; FileHandle
0x140008713  mov     [rsp+120h+EaBuffer], r12; EaBuffer
0x140008718  mov     ebx, 1
0x14000871d  mov     [rsp+120h+CreateOptions], r12d; CreateOptions
0x140008722  xorps   xmm0, xmm0
0x140008725  mov     dword ptr [rsp+120h+CreateDisposition], ebx; CreateDisposition
0x140008729  mov     rdx, r15; Instance
0x14000872c  mov     dword ptr [rsp+120h+ShareAccess], ebx; ShareAccess
0x140008730  mov     [rsp+120h+FileAttributes], 6; FileAttributes
0x140008738  mov     [rbp+57h+var_70.ObjectName], rax
0x14000873c  lea     rax, [rbp+57h+var_40]
0x140008740  mov     [rsp+120h+AllocationSize], r12; AllocationSize
0x140008745  mov     [rsp+120h+IoStatusBlock], rax; IoStatusBlock
0x14000874a  lea     rax, [rbp+57h+var_70]
0x14000874e  mov     [rsp+120h+ObjectAttributes], rax; ObjectAttributes
0x140008753  mov     [rsp+120h+DesiredAccess], 1F01FFh; DesiredAccess
0x14000875b  mov     [rbp+57h+var_70.Length], 30h ; '0'
0x140008762  mov     [rbp+57h+var_70.RootDirectory], r12
0x140008766  mov     [rbp+57h+var_70.Attributes], 200h
0x14000876d  movdqu  xmmword ptr [rbp+57h+var_70.SecurityDescriptor], xmm0
0x140008772  call    cs:__imp_FltCreateFileEx
0x140008779  nop     dword ptr [rax+rax+00h]
0x14000877e  test    eax, eax
0x140008780  js      loc_14000894F
0x140008786  mov     r13d, 1000h
0x14000878c  mov     qword ptr [rbp+57h+ByteOffset], r12
0x140008790  mov     r8d, r13d; NumberOfBytes
0x140008793  mov     [rbp+57h+BufferSizeNeeded], 4
0x14000879a  mov     r9d, 69764A50h; Tag
0x1400087a0  mov     edx, ebx; PoolType
0x1400087a2  mov     rcx, r15; Instance
0x1400087a5  call    cs:__imp_FltAllocatePoolAlignedWithTag
0x1400087ac  nop     dword ptr [rax+rax+00h]
0x1400087b1  mov     rsi, rax
0x1400087b4  test    rax, rax
0x1400087b7  jz      loc_14000894F
0x1400087bd  mov     rdx, [rbp+57h+FileObject]; FileObject
0x1400087c1  lea     rax, [rbp+57h+BytesRead]
0x1400087c5  mov     qword ptr [rsp+120h+FileAttributes], r12; CallbackContext
0x1400087ca  lea     r8, [rbp+57h+ByteOffset]; ByteOffset
0x1400087ce  mov     [rsp+120h+AllocationSize], r12; CallbackRoutine
0x1400087d3  mov     r9d, r13d; Length
0x1400087d6  mov     [rsp+120h+IoStatusBlock], rax; BytesRead
0x1400087db  mov     rcx, r15; InitiatingInstance
0x1400087de  mov     dword ptr [rsp+120h+ObjectAttributes], ebx; Flags
0x1400087e2  mov     qword ptr [rsp+120h+DesiredAccess], rsi; Buffer
0x1400087e7  call    cs:__imp_FltReadFile
0x1400087ee  nop     dword ptr [rax+rax+00h]
0x1400087f3  mov     r9d, eax
0x1400087f6  test    eax, eax
0x1400087f8  jns     short loc_140008855
0x1400087fa  mov     dl, byte ptr cs:xmmword_14001A3D0
0x140008800  lea     rax, WPP_RECORDER_INITIALIZED
0x140008807  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000880e  setnz   r8b
0x140008812  and     dl, 2
0x140008815  jnz     short loc_140008820
0x140008817  test    r8b, r8b
0x14000881a  jz      loc_14000894F
0x140008820  mov     dword ptr [rsp+120h+CreateDisposition], r9d
0x140008825  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14000882c  mov     dword ptr [rsp+120h+ShareAccess], 10ECh
0x140008834  mov     qword ptr [rsp+120h+FileAttributes], rax
0x140008839  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x140008840  mov     [rsp+120h+AllocationSize], rax
0x140008845  mov     word ptr [rsp+120h+IoStatusBlock], 5Eh ; '^'
0x14000884c  mov     dword ptr [rsp+120h+ObjectAttributes], ebx
0x140008850  jmp     loc_140008935
0x140008855  mov     eax, [rbp+57h+BufferSizeNeeded]
0x140008858  cmp     [rbp+57h+BytesRead], eax
0x14000885b  jb      short loc_14000886F
0x14000885d  mov     r8d, eax; Size
0x140008860  lea     rcx, [rbp+57h+var_A0]; void *
0x140008864  mov     rdx, rsi; Src
0x140008867  call    memmove
0x14000886c  mov     edi, [rbp+57h+var_A0]
0x14000886f  test    bl, dil
0x140008872  cmovnz  r14d, ebx
0x140008876  jmp     loc_14000894F
0x14000887b  mov     [rbp+57h+DestinationString.MaximumLength], r13w
0x140008880  mov     dl, byte ptr cs:xmmword_14001A3D0
0x140008886  lea     rax, WPP_RECORDER_INITIALIZED
0x14000888d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140008894  setnz   r8b
0x140008898  and     dl, 2
0x14000889b  jnz     short loc_1400088A6
0x14000889d  test    r8b, r8b
0x1400088a0  jz      loc_14000894F
0x1400088a6  mov     dword ptr [rsp+120h+CreateDisposition], 0C0000095h
0x1400088ae  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400088b5  mov     dword ptr [rsp+120h+ShareAccess], 1099h
0x1400088bd  mov     qword ptr [rsp+120h+FileAttributes], rax
0x1400088c2  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x1400088c9  mov     [rsp+120h+AllocationSize], rax
0x1400088ce  mov     word ptr [rsp+120h+IoStatusBlock], 5Ah ; 'Z'
0x1400088d5  jmp     short loc_14000892D
0x1400088d7  mov     [rbp+57h+DestinationString.MaximumLength], r13w
0x1400088dc  mov     dl, byte ptr cs:xmmword_14001A3D0
0x1400088e2  lea     rax, WPP_RECORDER_INITIALIZED
0x1400088e9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400088f0  setnz   r8b
0x1400088f4  and     dl, 2
0x1400088f7  jnz     short loc_1400088FE
0x1400088f9  test    r8b, r8b
0x1400088fc  jz      short loc_14000894F
0x1400088fe  mov     dword ptr [rsp+120h+CreateDisposition], 0C0000095h
0x140008906  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14000890d  mov     dword ptr [rsp+120h+ShareAccess], 1089h
0x140008915  mov     qword ptr [rsp+120h+FileAttributes], rax
0x14000891a  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x140008921  mov     [rsp+120h+AllocationSize], rax
0x140008926  mov     word ptr [rsp+120h+IoStatusBlock], 58h ; 'X'
0x14000892d  mov     dword ptr [rsp+120h+ObjectAttributes], 1
0x140008935  mov     r9, cs:WPP_GLOBAL_Control
  ... truncated ...
```
