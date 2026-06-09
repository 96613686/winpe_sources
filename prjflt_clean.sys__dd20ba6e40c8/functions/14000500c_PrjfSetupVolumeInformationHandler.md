# PrjfSetupVolumeInformationHandler

- ea: `0x14000500c`
- end: `0x1400057aa`
- name: `PrjfSetupVolumeInformationHandler`
- size: `1950`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140031a00`

## callees

- `0x14000500c`
- `0x14000b1d0`
- `0x14000ba20`
- `0x14000bb80`
- `0x14000be80`
- `0x14000d128`
- `0x140010154`
- `0x14002fe60`
- `0x14003775c`
- `0x14003e624`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400056fb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400056fb`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400054a8`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400054a8`
- `ntoskrnl!RtlInitUnicodeString` at `0x140005084`
- `ntoskrnl!RtlInitUnicodeString` at `0x140005084`
- `ntoskrnl!ObfDereferenceObject` at `0x140005710`
- `ntoskrnl!ObfDereferenceObject` at `0x140005710`
- `FLTMGR!FltFreePoolAlignedWithTag` at `0x140005774`
- `FLTMGR!FltFreePoolAlignedWithTag` at `0x140005774`
- `FLTMGR!FltWriteFile` at `0x140005680`
- `FLTMGR!FltWriteFile` at `0x140005680`
- `FLTMGR!FltAllocatePoolAlignedWithTag` at `0x14000561a`
- `FLTMGR!FltAllocatePoolAlignedWithTag` at `0x14000561a`
- `FLTMGR!FltGetVolumeName` at `0x140005405`
- `FLTMGR!FltGetVolumeName` at `0x140005487`
- `FLTMGR!FltGetVolumeName` at `0x140005405`
- `FLTMGR!FltGetVolumeName` at `0x140005487`
- `FLTMGR!FltCreateSystemVolumeInformationFolder` at `0x14000529b`
- `FLTMGR!FltCreateSystemVolumeInformationFolder` at `0x14000529b`
- `FLTMGR!FltCreateFileEx` at `0x140005590`
- `FLTMGR!FltCreateFileEx` at `0x140005590`
- `FLTMGR!FltObjectDereference` at `0x14000573a`
- `FLTMGR!FltObjectDereference` at `0x140005756`
- `FLTMGR!FltObjectDereference` at `0x14000573a`
- `FLTMGR!FltObjectDereference` at `0x140005756`
- `FLTMGR!FltGetVolumeFromName` at `0x140005393`
- `FLTMGR!FltGetVolumeFromName` at `0x140005393`
- `FLTMGR!FltClose` at `0x140005725`
- `FLTMGR!FltClose` at `0x140005725`

## pseudocode

```c
__int64 __fastcall PrjfSetupVolumeInformationHandler(__int64 a1, unsigned int a2)
{
  void *v4; // rsi
  int v5; // r8d
  unsigned int v6; // edx
  int v7; // edx
  NTSTATUS InstanceFromVolumeName; // ebx
  char v9; // r10
  int v10; // ecx
  int v11; // edx
  int v12; // r8d
  int v13; // edx
  int v14; // r8d
  int v15; // edx
  int v16; // r8d
  int v17; // edx
  int v18; // r8d
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // r8
  __int64 v22; // r9
  unsigned __int16 v23; // ax
  unsigned int v24; // eax
  int v25; // edx
  int v26; // r8d
  int v27; // edx
  int v28; // r8d
  PVOID PoolAlignedWithTag; // rax
  int v30; // edx
  int v31; // r8d
  struct _FLT_INSTANCE *v32; // rcx
  __int16 IoStatusBlock; // [rsp+30h] [rbp-D0h]
  char ShareAccess; // [rsp+48h] [rbp-B8h]
  ULONG BufferSizeNeeded; // [rsp+80h] [rbp-80h] BYREF
  PFLT_INSTANCE Instance; // [rsp+88h] [rbp-78h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+90h] [rbp-70h] BYREF
  PFLT_VOLUME RetVolume; // [rsp+A0h] [rbp-60h] BYREF
  PFILE_OBJECT FileObject; // [rsp+A8h] [rbp-58h] BYREF
  UNICODE_STRING String2; // [rsp+B0h] [rbp-50h] BYREF
  union _LARGE_INTEGER ByteOffset; // [rsp+C0h] [rbp-40h] BYREF
  void *FileHandle; // [rsp+C8h] [rbp-38h] BYREF
  UNICODE_STRING VolumeName; // [rsp+D0h] [rbp-30h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+E0h] [rbp-20h] BYREF
  struct _IO_STATUS_BLOCK v46; // [rsp+110h] [rbp+10h] BYREF
  char v47; // [rsp+120h] [rbp+20h] BYREF

  Instance = 0;
  FileHandle = 0;
  FileObject = 0;
  BufferSizeNeeded = 0;
  RetVolume = 0;
  ByteOffset.QuadPart = 0;
  v4 = 0;
  String2 = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  v46 = 0;
  VolumeName = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  v6 = *(_DWORD *)a1;
  if ( *(_DWORD *)a1 <= a2 )
  {
    if ( v6 >= 0xC )
    {
      v10 = *(unsigned __int16 *)(a1 + 4);
      if ( v6 >= v10 + 12 )
      {
        String2.Length = *(_WORD *)(a1 + 4);
        String2.MaximumLength = v10;
        String2.Buffer = (PWSTR)(a1 + 12);
        InstanceFromVolumeName = PrjfGetInstanceFromVolumeName(&String2, &Instance);
        if ( InstanceFromVolumeName >= 0 )
        {
          InstanceFromVolumeName = FltCreateSystemVolumeInformationFolder(Instance);
          if ( InstanceFromVolumeName >= 0 )
          {
            *(_QWORD *)&VolumeName.Length = 7864320;
            VolumeName.Buffer = (PWSTR)&v47;
            InstanceFromVolumeName = PrjfValidateAndGetGlobalVolumePath(&String2);
            if ( InstanceFromVolumeName >= 0 )
            {
              InstanceFromVolumeName = FltGetVolumeFromName(Globals, &VolumeName, &RetVolume);
              if ( InstanceFromVolumeName >= 0 )
              {
                if ( FltGetVolumeName(RetVolume, 0, &BufferSizeNeeded) == -1073741789 )
                {
                  v23 = BufferSizeNeeded;
                  if ( BufferSizeNeeded > 0xFFFF )
                  {
                    MicrosoftTelemetryAssertTriggeredNoArgsKM(v20, v19, v21, v22);
                    v23 = BufferSizeNeeded;
                  }
                  v24 = 2 * v23;
                  if ( v24 > 0xFFFF
                    || (unsigned __int16)(v24 + 8) < (unsigned __int16)v24
                    || (unsigned __int16)(v24 + 80) < (unsigned __int16)(v24 + 8) )
                  {
                    DestinationString.MaximumLength = -1;
                    InstanceFromVolumeName = -1073741675;
                  }
                  else
                  {
                    DestinationString.MaximumLength = v24 + 80;
                    InstanceFromVolumeName = PrjfAllocateUnicodeString(1852197456, &DestinationString, v21, v22);
                    if ( InstanceFromVolumeName >= 0 )
                    {
                      InstanceFromVolumeName = FltGetVolumeName(RetVolume, &DestinationString, &BufferSizeNeeded);
                      if ( InstanceFromVolumeName >= 0 )
                      {
                        InstanceFromVolumeName = RtlAppendUnicodeToString(
                                                   &DestinationString,
                                                   L"\\System Volume Information\\Gvflt.md");
                        if ( InstanceFromVolumeName >= 0 )
                        {
                          ObjectAttributes.ObjectName = &DestinationString;
                          ObjectAttributes.Length = 48;
                          ObjectAttributes.RootDirectory = 0;
                          ObjectAttributes.Attributes = 512;
                          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
                          InstanceFromVolumeName = FltCreateFileEx(
                                                     Globals,
                                                     Instance,
                                                     &FileHandle,
                                                     &FileObject,
                                                     0x1F01FFu,
                                                     &ObjectAttributes,
                                                     &v46,
                                                     0,
                                                     6u,
                                                     1u,
                                                     3u,
                                                     0,
                                                     0,
                                                     0,
                                                     0);
                          if ( InstanceFromVolumeName >= 0 )
                          {
                            ByteOffset.QuadPart = 0;
                            BufferSizeNeeded = 4;
                            PoolAlignedWithTag = FltAllocatePoolAlignedWithTag(
                                                   Instance,
                                                   (POOL_TYPE)512,
                                                   0x1000u,
                                                   0x69764A50u);
                            v4 = PoolAlignedWithTag;
                            if ( PoolAlignedWithTag )
                            {
                              memset(PoolAlignedWithTag, 0, 0x1000u);
                              memmove(v4, (const void *)(a1 + 8), BufferSizeNeeded);
                              InstanceFromVolumeName = FltWriteFile(
                                                         Instance,
                                                         FileObject,
                                                         &ByteOffset,
                                                         0x1000u,
                                                         v4,
                                                         1u,
                                                         0,
                                                         0,
                                                         0);
                              if ( InstanceFromVolumeName < 0
                                && ((BYTE1(xmmword_14001A3D0) & 0x40) != 0
                                 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED) )
                              {
                                LOBYTE(v30) = BYTE1(xmmword_14001A3D0) & 0x40;
                                LOBYTE(v31) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
                                WPP_RECORDER_AND_TRACE_SF_sDL(
                                  526,
                                  v30,
                                  v31,
                                  *((_QWORD *)WPP_GLOBAL_Control + 8),
                                  2,
                                  14,
                                  80,
                                  (__int64)&WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
                                  (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
                                  82,
                                  InstanceFromVolumeName);
                              }
                            }
                            else
                            {
                              InstanceFromVolumeName = -1073741670;
                            }
                          }
                          else if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0
                                 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                          {
                            LOBYTE(v27) = BYTE1(xmmword_14001A3D0) & 0x40;
                            LOBYTE(v28) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
                            WPP_RECORDER_AND_TRACE_SF_sDL(
                              526,
                              v27,
                              v28,
                              *((_QWORD *)WPP_GLOBAL_Control + 8),
                              2,
                              14,
                              79,
                              (__int64)&WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
                              (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
                              48,
                              InstanceFromVolumeName);
                          }
                        }
                        else if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0
                               || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                        {
                          LOBYTE(v25) = BYTE1(xmmword_14001A3D0) & 0x40;
                          LOBYTE(v26) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
                          WPP_RECORDER_AND_TRACE_SF_sDL(
                            526,
                            v25,
                            v26,
                            *((_QWORD *)WPP_GLOBAL_Control + 8),
                            2,
                            14,
                            78,
                            (__int64)&WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
                            (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
                            20,
                            InstanceFromVolumeName);
                        }
                      }
                    }
                  }
                }
                else
                {
                  InstanceFromVolumeName = -1073741808;
                }
              }
              else if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0
                     || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                LOBYTE(v17) = BYTE1(xmmword_14001A3D0) & 0x40;
                LOBYTE(v18) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
                WPP_RECORDER_AND_TRACE_SF_sDL(
                  526,
                  v17,
                  v18,
                  *((_QWORD *)WPP_GLOBAL_Control + 8),
                  2,
                  14,
                  77,
                  (__int64)&WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
                  (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
                  224,
                  InstanceFromVolumeName);
              }
            }
            else if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0
                   || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v15) = BYTE1(xmmword_14001A3D0) & 0x40;
              LOBYTE(v16) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
              WPP_RECORDER_AND_TRACE_SF_sDL(
                526,
                v15,
                v16,
                *((_QWORD *)WPP_GLOBAL_Control + 8),
                2,
                14,
                76,
                (__int64)&WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
                (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
                212,
                InstanceFromVolumeName);
            }
          }
          else if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0
                 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v13) = BYTE1(xmmword_14001A3D0) & 0x40;
            LOBYTE(v14) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            WPP_RECORDER_AND_TRACE_SF_sDL(
              526,
              v13,
              v14,
              *((_QWORD *)WPP_GLOBAL_Control + 8),
              2,
              14,
              75,
              (__int64)&WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
              (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
              201,
              InstanceFromVolumeName);
          }
        }
        else if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0
               || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v11) = BYTE1(xmmword_14001A3D0) & 0x40;
          LOBYTE(v12) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_sDZd(
            526,
            v11,
            v12,
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            2,
            14,
            74,
            (__int64)&WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
            (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
            193,
            (__int64)&String2,
            InstanceFromVolumeName);
        }
      }
      else
      {
        v7 = -1073741811;
        InstanceFromVolumeName = -1073741811;
        LOBYTE(v5) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        v9 = BYTE1(xmmword_14001A3D0) & 0x40;
        if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          ShareAccess = -76;
          IoStatusBlock = 73;
          goto LABEL_5;
        }
      }
    }
    else
    {
      v7 = -1073741811;
      InstanceFromVolumeName = -1073741811;
      v9 = BYTE1(xmmword_14001A3D0) & 0x40;
      if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        ShareAccess = -84;
        LOBYTE(v5) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        IoStatusBlock = 72;
        goto LABEL_5;
      }
    }
  }
  else
  {
    v7 = -1073741811;
    InstanceFromVolumeName = -1073741811;
    LOBYTE(v5) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    v9 = BYTE1(xmmword_14001A3D0) & 0x40;
    if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      ShareAccess = -91;
      IoStatusBlock = 71;
LABEL_5:
      LOBYTE(v7) = v9;
      WPP_RECORDER_AND_TRACE_SF_sDL(
        526,
        v7,
        v5,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        14,
        IoStatusBlock,
        (__int64)&WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
        ShareAccess,
        13);
    }
  }
  if ( DestinationString.Buffer )
    ExFreePoolWithTag(DestinationString.Buffer, 0x6E664A50u);
  if ( FileObject )
    ObfDereferenceObject(FileObject);
  if ( FileHandle )
    FltClose(FileHandle);
  v32 = Instance;
  if ( Instance )
  {
    FltObjectDereference(Instance);
    v32 = Instance;
  }
  if ( RetVolume )
  {
    FltObjectDereference(RetVolume);
    v32 = Instance;
  }
  if ( v4 )
    FltFreePoolAlignedWithTag(v32, v4, 0x69764A50u);
  return (unsigned int)InstanceFromVolumeName;
}

```

## disassembly

```asm
0x14000500c  mov     [rsp-8+arg_8], rbx
0x140005011  mov     [rsp-8+arg_10], rsi
0x140005016  push    rbp
0x140005017  push    rdi
0x140005018  push    r14
0x14000501a  lea     rbp, [rsp-0B0h]
0x140005022  sub     rsp, 1B0h
0x140005029  mov     rax, cs:__security_cookie
0x140005030  xor     rax, rsp
0x140005033  mov     [rbp+0C0h+var_20], rax
0x14000503a  xorps   xmm0, xmm0
0x14000503d  xor     r14d, r14d
0x140005040  mov     ebx, edx
0x140005042  mov     [rbp+0C0h+Instance], r14
0x140005046  mov     rdi, rcx
0x140005049  mov     [rbp+0C0h+FileHandle], r14
0x14000504d  movups  xmmword ptr [rbp+0C0h+var_E0.ObjectName], xmm0
0x140005051  xor     eax, eax
0x140005053  mov     [rbp+0C0h+FileObject], r14
0x140005057  xor     edx, edx; SourceString
0x140005059  mov     [rbp+0C0h+BufferSizeNeeded], r14d
0x14000505d  lea     rcx, [rbp+0C0h+DestinationString]; DestinationString
0x140005061  mov     [rbp+0C0h+RetVolume], r14
0x140005065  movups  xmmword ptr [rbp+0C0h+var_E0+1Ch], xmm0
0x140005069  mov     qword ptr [rbp+0C0h+ByteOffset], r14
0x14000506d  mov     esi, r14d
0x140005070  movups  xmmword ptr [rbp+0C0h+String2.Length], xmm0
0x140005074  movups  xmmword ptr [rbp+0C0h+DestinationString.Length], xmm0
0x140005078  movups  xmmword ptr [rbp+0C0h+var_E0.Length], xmm0
0x14000507c  movups  xmmword ptr [rbp+0C0h+var_B0], xmm0
0x140005080  movups  xmmword ptr [rbp+0C0h+VolumeName.Length], xmm0
0x140005084  call    cs:__imp_RtlInitUnicodeString
0x14000508b  nop     dword ptr [rax+rax+00h]
0x140005090  mov     edx, [rdi]
0x140005092  cmp     edx, ebx
0x140005094  jbe     loc_14000511E
0x14000509a  mov     edx, 0C000000Dh
0x14000509f  mov     ebx, edx
0x1400050a1  mov     r10b, byte ptr cs:xmmword_14001A3D0+1
0x1400050a8  lea     rax, WPP_RECORDER_INITIALIZED
0x1400050af  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400050b6  setnz   r8b
0x1400050ba  and     r10b, 40h
0x1400050be  jnz     short loc_1400050C9
0x1400050c0  test    r8b, r8b
0x1400050c3  jz      loc_1400056ED
0x1400050c9  mov     [rsp+1C0h+CreateDisposition], edx
0x1400050cd  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400050d4  mov     dword ptr [rsp+1C0h+ShareAccess], 7A5h
0x1400050dc  mov     qword ptr [rsp+1C0h+FileAttributes], rax
0x1400050e1  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x1400050e8  mov     [rsp+1C0h+AllocationSize], rax
0x1400050ed  mov     word ptr [rsp+1C0h+IoStatusBlock], 47h ; 'G'
0x1400050f4  mov     dl, r10b
0x1400050f7  mov     r9, cs:WPP_GLOBAL_Control
0x1400050fe  mov     ecx, 20Eh
0x140005103  mov     dword ptr [rsp+1C0h+ObjectAttributes], 0Eh
0x14000510b  mov     byte ptr [rsp+1C0h+DesiredAccess], 2
0x140005110  mov     r9, [r9+40h]
0x140005114  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140005119  jmp     loc_1400056ED
0x14000511e  cmp     edx, 0Ch
0x140005121  jnb     short loc_140005185
0x140005123  mov     edx, 0C000000Dh
0x140005128  mov     ebx, edx
0x14000512a  mov     r10b, byte ptr cs:xmmword_14001A3D0+1
0x140005131  lea     rax, WPP_RECORDER_INITIALIZED
0x140005138  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000513f  setnz   r11b
0x140005143  and     r10b, 40h
0x140005147  jnz     short loc_140005152
0x140005149  test    r11b, r11b
0x14000514c  jz      loc_1400056ED
0x140005152  mov     [rsp+1C0h+CreateDisposition], edx
0x140005156  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14000515d  mov     dword ptr [rsp+1C0h+ShareAccess], 7ACh
0x140005165  mov     r8b, r11b
0x140005168  mov     qword ptr [rsp+1C0h+FileAttributes], rax
0x14000516d  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x140005174  mov     [rsp+1C0h+AllocationSize], rax
0x140005179  mov     word ptr [rsp+1C0h+IoStatusBlock], 48h ; 'H'
0x140005180  jmp     loc_1400050F4
0x140005185  movzx   ecx, word ptr [rdi+4]
0x140005189  lea     eax, [rcx+0Ch]
0x14000518c  cmp     edx, eax
0x14000518e  jnb     short loc_1400051EF
0x140005190  mov     edx, 0C000000Dh
0x140005195  mov     ebx, edx
0x140005197  mov     r10b, byte ptr cs:xmmword_14001A3D0+1
0x14000519e  lea     rax, WPP_RECORDER_INITIALIZED
0x1400051a5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400051ac  setnz   r8b
0x1400051b0  and     r10b, 40h
0x1400051b4  jnz     short loc_1400051BF
0x1400051b6  test    r8b, r8b
0x1400051b9  jz      loc_1400056ED
0x1400051bf  mov     [rsp+1C0h+CreateDisposition], edx
0x1400051c3  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400051ca  mov     dword ptr [rsp+1C0h+ShareAccess], 7B4h
0x1400051d2  mov     qword ptr [rsp+1C0h+FileAttributes], rax
0x1400051d7  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x1400051de  mov     [rsp+1C0h+AllocationSize], rax
0x1400051e3  mov     word ptr [rsp+1C0h+IoStatusBlock], 49h ; 'I'
0x1400051ea  jmp     loc_1400050F4
0x1400051ef  mov     [rbp+0C0h+String2.Length], cx
0x1400051f3  lea     rax, [rdi+0Ch]
0x1400051f7  mov     [rbp+0C0h+String2.MaximumLength], cx
0x1400051fb  lea     rdx, [rbp+0C0h+Instance]
0x1400051ff  lea     rcx, [rbp+0C0h+String2]
0x140005203  mov     [rbp+0C0h+String2.Buffer], rax
0x140005207  call    PrjfGetInstanceFromVolumeName
0x14000520c  mov     ebx, eax
0x14000520e  test    eax, eax
0x140005210  jns     loc_140005297
0x140005216  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14000521c  lea     rax, WPP_RECORDER_INITIALIZED
0x140005223  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000522a  setnz   r8b
0x14000522e  and     dl, 40h
0x140005231  jnz     short loc_14000523C
0x140005233  test    r8b, r8b
0x140005236  jz      loc_1400056ED
0x14000523c  mov     r9, cs:WPP_GLOBAL_Control
0x140005243  lea     rax, [rbp+0C0h+String2]
0x140005247  mov     [rsp+1C0h+CreateOptions], ebx
0x14000524b  mov     ecx, 20Eh
0x140005250  mov     qword ptr [rsp+1C0h+CreateDisposition], rax
0x140005255  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14000525c  mov     dword ptr [rsp+1C0h+ShareAccess], 7C1h
0x140005264  mov     r9, [r9+40h]
0x140005268  mov     qword ptr [rsp+1C0h+FileAttributes], rax
0x14000526d  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x140005274  mov     [rsp+1C0h+AllocationSize], rax
0x140005279  mov     word ptr [rsp+1C0h+IoStatusBlock], 4Ah ; 'J'
0x140005280  mov     dword ptr [rsp+1C0h+ObjectAttributes], 0Eh
0x140005288  mov     byte ptr [rsp+1C0h+DesiredAccess], 2
0x14000528d  call    WPP_RECORDER_AND_TRACE_SF_sDZd
0x140005292  jmp     loc_1400056ED
0x140005297  mov     rcx, [rbp+0C0h+Instance]; Instance
0x14000529b  call    cs:__imp_FltCreateSystemVolumeInformationFolder
0x1400052a2  nop     dword ptr [rax+rax+00h]
0x1400052a7  mov     ebx, eax
0x1400052a9  test    eax, eax
0x1400052ab  jns     short loc_140005303
0x1400052ad  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x1400052b3  lea     rax, WPP_RECORDER_INITIALIZED
0x1400052ba  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400052c1  setnz   r8b
0x1400052c5  and     dl, 40h
0x1400052c8  jnz     short loc_1400052D3
0x1400052ca  test    r8b, r8b
0x1400052cd  jz      loc_1400056ED
0x1400052d3  mov     [rsp+1C0h+CreateDisposition], ebx
0x1400052d7  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400052de  mov     dword ptr [rsp+1C0h+ShareAccess], 7C9h
0x1400052e6  mov     qword ptr [rsp+1C0h+FileAttributes], rax
0x1400052eb  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x1400052f2  mov     [rsp+1C0h+AllocationSize], rax
0x1400052f7  mov     word ptr [rsp+1C0h+IoStatusBlock], 4Bh ; 'K'
0x1400052fe  jmp     loc_1400050F7
0x140005303  xorps   xmm0, xmm0
0x140005306  lea     rdx, [rbp+0C0h+VolumeName]
0x14000530a  movups  xmmword ptr [rbp+0C0h+VolumeName.Length], xmm0
0x14000530e  mov     eax, 78h ; 'x'
0x140005313  lea     rcx, [rbp+0C0h+String2]; String2
0x140005317  mov     [rbp+0C0h+VolumeName.MaximumLength], ax
0x14000531b  lea     rax, [rbp+0C0h+var_A0]
0x14000531f  mov     [rbp+0C0h+VolumeName.Buffer], rax
0x140005323  call    PrjfValidateAndGetGlobalVolumePath
0x140005328  mov     ebx, eax
0x14000532a  test    eax, eax
0x14000532c  jns     short loc_140005384
0x14000532e  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140005334  lea     rax, WPP_RECORDER_INITIALIZED
0x14000533b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140005342  setnz   r8b
0x140005346  and     dl, 40h
0x140005349  jnz     short loc_140005354
0x14000534b  test    r8b, r8b
0x14000534e  jz      loc_1400056ED
0x140005354  mov     [rsp+1C0h+CreateDisposition], ebx
0x140005358  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14000535f  mov     dword ptr [rsp+1C0h+ShareAccess], 7D4h
0x140005367  mov     qword ptr [rsp+1C0h+FileAttributes], rax
0x14000536c  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x140005373  mov     [rsp+1C0h+AllocationSize], rax
0x140005378  mov     word ptr [rsp+1C0h+IoStatusBlock], 4Ch ; 'L'
0x14000537f  jmp     loc_1400050F7
0x140005384  mov     rcx, cs:Globals; Filter
0x14000538b  lea     r8, [rbp+0C0h+RetVolume]; RetVolume
0x14000538f  lea     rdx, [rbp+0C0h+VolumeName]; VolumeName
0x140005393  call    cs:__imp_FltGetVolumeFromName
0x14000539a  nop     dword ptr [rax+rax+00h]
0x14000539f  mov     ebx, eax
0x1400053a1  test    eax, eax
0x1400053a3  jns     short loc_1400053FB
0x1400053a5  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x1400053ab  lea     rax, WPP_RECORDER_INITIALIZED
0x1400053b2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400053b9  setnz   r8b
0x1400053bd  and     dl, 40h
0x1400053c0  jnz     short loc_1400053CB
0x1400053c2  test    r8b, r8b
0x1400053c5  jz      loc_1400056ED
0x1400053cb  mov     [rsp+1C0h+CreateDisposition], ebx
0x1400053cf  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400053d6  mov     dword ptr [rsp+1C0h+ShareAccess], 7E0h
0x1400053de  mov     qword ptr [rsp+1C0h+FileAttributes], rax
0x1400053e3  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x1400053ea  mov     [rsp+1C0h+AllocationSize], rax
0x1400053ef  mov     word ptr [rsp+1C0h+IoStatusBlock], 4Dh ; 'M'
0x1400053f6  jmp     loc_1400050F7
0x1400053fb  mov     rcx, [rbp+0C0h+RetVolume]; Volume
0x1400053ff  lea     r8, [rbp+0C0h+BufferSizeNeeded]; BufferSizeNeeded
0x140005403  xor     edx, edx; VolumeName
0x140005405  call    cs:__imp_FltGetVolumeName
0x14000540c  nop     dword ptr [rax+rax+00h]
0x140005411  cmp     eax, 0C0000023h
0x140005416  jz      short loc_140005422
0x140005418  mov     ebx, 0C0000010h
0x14000541d  jmp     loc_1400056ED
0x140005422  mov     eax, [rbp+0C0h+BufferSizeNeeded]
0x140005425  mov     ebx, 0FFFFh
0x14000542a  cmp     eax, ebx
0x14000542c  jbe     short loc_140005436
0x14000542e  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140005433  mov     eax, [rbp+0C0h+BufferSizeNeeded]
0x140005436  movzx   eax, ax
0x140005439  add     eax, eax
0x14000543b  cmp     eax, ebx
0x14000543d  ja      loc_1400056E4
0x140005443  lea     ecx, [rax+8]
0x140005446  cmp     cx, ax
0x140005449  jb      loc_1400056E4
0x14000544f  mov     eax, 48h ; 'H'
0x140005454  add     eax, ecx
0x140005456  cmp     ax, cx
0x140005459  jb      loc_1400056E4
0x14000545f  lea     rdx, [rbp+0C0h+DestinationString]
0x140005463  mov     [rbp+0C0h+DestinationString.MaximumLength], ax
0x140005467  mov     ecx, 6E664A50h
0x14000546c  call    PrjfAllocateUnicodeString
0x140005471  mov     ebx, eax
0x140005473  test    eax, eax
0x140005475  js      loc_1400056ED
0x14000547b  mov     rcx, [rbp+0C0h+RetVolume]; Volume
0x14000547f  lea     r8, [rbp+0C0h+BufferSizeNeeded]; BufferSizeNeeded
0x140005483  lea     rdx, [rbp+0C0h+DestinationString]; VolumeName
0x140005487  call    cs:__imp_FltGetVolumeName
0x14000548e  nop     dword ptr [rax+rax+00h]
0x140005493  mov     ebx, eax
0x140005495  test    eax, eax
0x140005497  js      loc_1400056ED
0x14000549d  lea     rdx, Source; "\\System Volume Information\\Gvflt.md"
0x1400054a4  lea     rcx, [rbp+0C0h+DestinationString]; Destination
0x1400054a8  call    cs:__imp_RtlAppendUnicodeToString
0x1400054af  nop     dword ptr [rax+rax+00h]
0x1400054b4  mov     ebx, eax
0x1400054b6  test    eax, eax
0x1400054b8  jns     short loc_140005510
0x1400054ba  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x1400054c0  lea     rax, WPP_RECORDER_INITIALIZED
0x1400054c7  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400054ce  setnz   r8b
0x1400054d2  and     dl, 40h
0x1400054d5  jnz     short loc_1400054E0
0x1400054d7  test    r8b, r8b
0x1400054da  jz      loc_1400056ED
0x1400054e0  mov     [rsp+1C0h+CreateDisposition], ebx
0x1400054e4  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400054eb  mov     dword ptr [rsp+1C0h+ShareAccess], 814h
0x1400054f3  mov     qword ptr [rsp+1C0h+FileAttributes], rax
0x1400054f8  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x1400054ff  mov     [rsp+1C0h+AllocationSize], rax
0x140005504  mov     word ptr [rsp+1C0h+IoStatusBlock], 4Eh ; 'N'
0x14000550b  jmp     loc_1400050F7
0x140005510  mov     rdx, [rbp+0C0h+Instance]; Instance
0x140005514  lea     rax, [rbp+0C0h+DestinationString]
0x140005518  mov     rcx, cs:Globals; Filter
0x14000551f  lea     r9, [rbp+0C0h+FileObject]; FileObject
0x140005523  mov     [rsp+1C0h+Flags], r14d; Flags
0x140005528  lea     r8, [rbp+0C0h+FileHandle]; FileHandle
0x14000552c  mov     [rsp+1C0h+EaLength], r14d; EaLength
0x140005531  xorps   xmm0, xmm0
0x140005534  mov     [rsp+1C0h+EaBuffer], r14; EaBuffer
0x140005539  mov     [rsp+1C0h+CreateOptions], r14d; CreateOptions
0x14000553e  mov     [rsp+1C0h+CreateDisposition], 3; CreateDisposition
0x140005546  mov     dword ptr [rsp+1C0h+ShareAccess], 1; ShareAccess
0x14000554e  mov     [rsp+1C0h+FileAttributes], 6; FileAttributes
0x140005556  mov     [rbp+0C0h+var_E0.ObjectName], rax
0x14000555a  lea     rax, [rbp+0C0h+var_B0]
0x14000555e  mov     [rsp+1C0h+AllocationSize], r14; AllocationSize
0x140005563  mov     [rsp+1C0h+IoStatusBlock], rax; IoStatusBlock
0x140005568  lea     rax, [rbp+0C0h+var_E0]
0x14000556c  mov     [rsp+1C0h+ObjectAttributes], rax; ObjectAttributes
0x140005571  mov     [rsp+1C0h+DesiredAccess], 1F01FFh; DesiredAccess
0x140005579  mov     [rbp+0C0h+var_E0.Length], 30h ; '0'
0x140005580  mov     [rbp+0C0h+var_E0.RootDirectory], r14
0x140005584  mov     [rbp+0C0h+var_E0.Attributes], 200h
0x14000558b  movdqu  xmmword ptr [rbp+0C0h+var_E0.SecurityDescriptor], xmm0
  ... truncated ...
```
