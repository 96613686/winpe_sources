# PrjfProcessTombstoneBounce

- ea: `0x140042eac`
- end: `0x14004383b`
- name: `PrjfProcessTombstoneBounce`
- size: `2447`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA Data, PFLT_INSTANCE Instance, struct _FILE_OBJECT *, __int64, PCWCH *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140022320`

## callees

- `0x140006570`
- `0x140006660`
- `0x14000b1d0`
- `0x14000ba20`
- `0x14000d008`
- `0x14000d128`
- `0x14000d754`
- `0x140013360`
- `0x140021550`
- `0x14003775c`
- `0x140037ac0`
- `0x14003be88`
- `0x140041a3c`
- `0x1400422ec`
- `0x140042eac`
- `0x140043844`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14004304c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004304c`
- `ntoskrnl!KeWaitForSingleObject` at `0x14004351b`
- `ntoskrnl!KeWaitForSingleObject` at `0x14004351b`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140042f6f`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140042f6f`
- `ntoskrnl!ObfDereferenceObject` at `0x140043076`
- `ntoskrnl!ObfDereferenceObject` at `0x1400434af`
- `ntoskrnl!ObfDereferenceObject` at `0x140043076`
- `ntoskrnl!ObfDereferenceObject` at `0x1400434af`
- `FLTMGR!FltSetInformationFile` at `0x140043378`
- `FLTMGR!FltSetInformationFile` at `0x14004340d`
- `FLTMGR!FltSetInformationFile` at `0x140043378`
- `FLTMGR!FltSetInformationFile` at `0x14004340d`
- `FLTMGR!FltRemoveOpenReparseEntry` at `0x140042f58`
- `FLTMGR!FltRemoveOpenReparseEntry` at `0x140042f58`
- `FLTMGR!FltSetCallbackDataDirty` at `0x140042f39`
- `FLTMGR!FltSetCallbackDataDirty` at `0x14004382a`
- `FLTMGR!FltSetCallbackDataDirty` at `0x140042f39`
- `FLTMGR!FltSetCallbackDataDirty` at `0x14004382a`
- `FLTMGR!FltReissueSynchronousIo` at `0x140042f85`
- `FLTMGR!FltReissueSynchronousIo` at `0x1400434d4`
- `FLTMGR!FltReissueSynchronousIo` at `0x140042f85`
- `FLTMGR!FltReissueSynchronousIo` at `0x1400434d4`
- `FLTMGR!FltParseFileNameInformation` at `0x140042fb4`
- `FLTMGR!FltParseFileNameInformation` at `0x140042fb4`
- `FLTMGR!FltClose` at `0x140043061`
- `FLTMGR!FltClose` at `0x140043499`
- `FLTMGR!FltClose` at `0x140043061`
- `FLTMGR!FltClose` at `0x140043499`
- `FLTMGR!FltQueryInformationFile` at `0x14004321c`
- `FLTMGR!FltQueryInformationFile` at `0x14004321c`
- `FLTMGR!FltReleaseContext` at `0x14004308b`
- `FLTMGR!FltReleaseContext` at `0x14004309f`
- `FLTMGR!FltReleaseContext` at `0x14004308b`
- `FLTMGR!FltReleaseContext` at `0x14004309f`

## pseudocode

```c
__int64 __fastcall PrjfProcessTombstoneBounce(
        PFLT_CALLBACK_DATA Data,
        PFLT_INSTANCE Instance,
        struct _FILE_OBJECT *a3,
        __int64 a4,
        PCWCH *a5)
{
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  PFLT_CALLBACK_DATA v7; // rdi
  int SetFileContext; // ebx
  void *v10; // rsi
  __int64 v11; // r8
  struct _FLT_FILE_NAME_INFORMATION *v12; // rcx
  NTSTATUS v13; // eax
  int v14; // edx
  int v15; // r8d
  __int64 v17; // rcx
  unsigned int v18; // ebx
  int v19; // edx
  int v20; // r8d
  int v21; // edx
  __int64 v22; // r8
  __int64 v23; // r9
  int v24; // edx
  int v25; // r8d
  NTSTATUS v26; // eax
  int v27; // edx
  int v28; // ecx
  int v29; // r8d
  int v30; // ebx
  NTSTATUS v31; // eax
  const char *v32; // rax
  char v33; // r15
  __int64 v34; // rdx
  __int64 v35; // rcx
  __int64 v36; // r8
  __int64 v37; // rdx
  __int64 v38; // rcx
  NTSTATUS Status; // eax
  PCWCH *v40; // rbx
  int v41; // edx
  int v42; // r8d
  __int64 v43; // rdx
  __int64 v44; // rcx
  PFILE_OBJECT v45; // rdi
  int v46; // edx
  int v47; // r8d
  int v48; // edx
  int v49; // r8d
  int v50; // eax
  int v51; // edx
  int v52; // r8d
  struct _FLT_TAG_DATA_BUFFER *TagData; // rax
  bool v54; // zf
  int v55; // eax
  __int64 FileInformationClass; // [rsp+20h] [rbp-E0h]
  int FileInformationClassa; // [rsp+20h] [rbp-E0h]
  int LengthReturned; // [rsp+28h] [rbp-D8h]
  int v59; // [rsp+30h] [rbp-D0h]
  int v60; // [rsp+38h] [rbp-C8h]
  int v61; // [rsp+40h] [rbp-C0h]
  int v62; // [rsp+48h] [rbp-B8h]
  char v63; // [rsp+70h] [rbp-90h] BYREF
  char v64; // [rsp+71h] [rbp-8Fh] BYREF
  char v65; // [rsp+72h] [rbp-8Eh]
  char v66; // [rsp+73h] [rbp-8Dh]
  __int64 v67; // [rsp+78h] [rbp-88h]
  PVOID Object; // [rsp+80h] [rbp-80h] BYREF
  int v69; // [rsp+88h] [rbp-78h] BYREF
  HANDLE FileHandle; // [rsp+90h] [rbp-70h] BYREF
  PFLT_CONTEXT Context; // [rsp+98h] [rbp-68h] BYREF
  ULONG v72; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v73; // [rsp+A8h] [rbp-58h] BYREF
  PVOID P[2]; // [rsp+B0h] [rbp-50h] BYREF
  PCWCH *v75; // [rsp+C0h] [rbp-40h]
  PFILE_OBJECT FileObject; // [rsp+C8h] [rbp-38h]
  __int64 v77[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int128 FileInformation; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v79; // [rsp+F0h] [rbp-10h]

  Iopb = Data->Iopb;
  FileObject = a3;
  v67 = 0;
  v73 = 0;
  v7 = Data;
  LOBYTE(Data) = HIBYTE(Iopb->Parameters.SetVolumeInformation.FsInformationClass);
  v69 = 0;
  SetFileContext = 0;
  FileHandle = 0;
  v10 = 0;
  Object = 0;
  v72 = 0;
  v79 = 0;
  v75 = a5;
  Context = 0;
  v63 = 0;
  FileInformation = 0;
  *(_OWORD *)P = 0;
  if ( !a5 )
  {
    Iopb->Parameters.Create.Options |= 0x200000u;
    FltSetCallbackDataDirty(v7);
    v11 = *(_QWORD *)(a4 + 56);
    if ( v11 )
    {
      FltRemoveOpenReparseEntry(Globals, v7, v11);
      ExFreeToPagedLookasideList(&stru_14001A6C0, *(PVOID *)(a4 + 56));
      *(_QWORD *)(a4 + 56) = 0;
    }
    FltReissueSynchronousIo(Instance, v7);
    goto LABEL_12;
  }
  if ( (_BYTE)Data != 1 && (_BYTE)Data != 4 )
  {
    v12 = *(struct _FLT_FILE_NAME_INFORMATION **)(a4 + 48);
    *(_OWORD *)v77 = *(_OWORD *)a5;
    v13 = FltParseFileNameInformation(v12);
    SetFileContext = v13;
    if ( v13 >= 0 )
    {
      v17 = *(_QWORD *)(a4 + 48) + 8LL;
      v64 = 0;
      v65 = 0;
      PrjfOpenAsReparsePoint(
        v17,
        0,
        Instance,
        65664,
        FileInformationClass,
        &FileHandle,
        (PFILE_OBJECT *)&Object,
        0,
        0,
        0,
        &v63,
        0);
      v18 = 0;
      if ( v63 )
      {
        SetFileContext = PrjfGetSetFileContext(Instance, (PFILE_OBJECT)Object, 1, 0, 0, 0, 0, &Context);
        if ( SetFileContext < 0 )
        {
          if ( (BYTE2(xmmword_14001A3D0) & 8) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v19) = BYTE2(xmmword_14001A3D0) & 8;
            LOBYTE(v20) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            WPP_RECORDER_AND_TRACE_SF_sDdZ(
              531,
              v19,
              v20,
              *((_QWORD *)WPP_GLOBAL_Control + 8),
              2,
              19,
              23,
              (__int64)WPP_3f08b24f959433411191d1ccab0ccd17_Traceguids,
              (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\tombstone.c",
              114,
              SetFileContext,
              (__int64)Object + 88);
          }
          goto LABEL_11;
        }
        SetFileContext = FltQueryInformationFile(
                           Instance,
                           (PFILE_OBJECT)Object,
                           &FileInformation,
                           0x18u,
                           FileStandardInformation,
                           &v72);
        if ( SetFileContext < 0 )
        {
          if ( (BYTE2(xmmword_14001A3D0) & 8) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v21) = BYTE2(xmmword_14001A3D0) & 8;
            LOBYTE(v22) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            WPP_RECORDER_AND_TRACE_SF_sDdZ(
              531,
              v21,
              v22,
              *((_QWORD *)WPP_GLOBAL_Control + 8),
              2,
              19,
              24,
              (__int64)WPP_3f08b24f959433411191d1ccab0ccd17_Traceguids,
              (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\tombstone.c",
              134,
              SetFileContext,
              (__int64)Object + 88);
          }
          goto LABEL_11;
        }
        v23 = *(_QWORD *)(a4 + 48);
        LOBYTE(v22) = BYTE5(v79);
        v66 = BYTE5(v79);
        SetFileContext = PrjfAddInMemoryTombstone(Instance, (PCUNICODE_STRING)(v23 + 88), v22, v23, 0, 0);
        if ( SetFileContext < 0 )
        {
          if ( (BYTE2(xmmword_14001A3D0) & 8) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v24) = BYTE2(xmmword_14001A3D0) & 8;
            LOBYTE(v25) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            WPP_RECORDER_AND_TRACE_SF_sDdZ(
              531,
              v24,
              v25,
              *((_QWORD *)WPP_GLOBAL_Control + 8),
              2,
              19,
              25,
              (__int64)WPP_3f08b24f959433411191d1ccab0ccd17_Traceguids,
              (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\tombstone.c",
              163,
              SetFileContext,
              *(_QWORD *)(a4 + 48) + 8LL);
          }
          PrjfTelemetryTombstoneFailureOperation(3, 1, SetFileContext);
          goto LABEL_11;
        }
        v69 = 3;
        v26 = FltSetInformationFile(Instance, (PFILE_OBJECT)Object, &v69, 1u, (FILE_INFORMATION_CLASS)64);
        v30 = v26;
        if ( v26 == -1073741156 || v26 == -1073741811 )
        {
          if ( (BYTE9(xmmword_14001A3D0) & 0x40) != 0
            || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v27) = BYTE9(xmmword_14001A3D0) & 0x40;
            LOBYTE(v29) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            WPP_RECORDER_AND_TRACE_SF_sD(
              782,
              v27,
              v29,
              *((_QWORD *)WPP_GLOBAL_Control + 8),
              3,
              14,
              26,
              (__int64)WPP_3f08b24f959433411191d1ccab0ccd17_Traceguids,
              (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\tombstone.c",
              192);
          }
          v64 = 1;
          v31 = FltSetInformationFile(Instance, (PFILE_OBJECT)Object, &v64, 1u, FileDispositionInformation);
          LOBYTE(v28) = 1;
          v30 = v31;
          v64 = 1;
        }
        else
        {
          LOBYTE(v28) = v64;
        }
        if ( v30 < 0 )
        {
          if ( (BYTE2(xmmword_14001A3D0) & 8) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v32 = "FileDispositionInformation";
            if ( !(_BYTE)v28 )
              v32 = "FileDispositionInformationEx";
            LOBYTE(v27) = BYTE2(xmmword_14001A3D0) & 8;
            LOBYTE(v29) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            WPP_RECORDER_AND_TRACE_SF_sDdsZ(
              v28,
              v27,
              v29,
              *((_QWORD *)WPP_GLOBAL_Control + 8),
              FileInformationClassa,
              LengthReturned,
              v59,
              v60,
              v61,
              v62,
              v30,
              (__int64)v32,
              (__int64)Object + 88);
          }
          PrjfTelemetryTombstoneFailureOperation(5, 1, v30);
          v65 = 1;
        }
        FltClose(FileHandle);
        v18 = 0;
        FileHandle = 0;
        ObfDereferenceObject(Object);
        Object = 0;
      }
      else
      {
        v66 = 0;
      }
      v33 = v64;
      *(_DWORD *)(a4 + 20) = 0;
      do
      {
        FltReissueSynchronousIo(Instance, v7);
        tlgDefineProvider_annotation__TlgProjfsTelemetryProviderProv(v35, v34, v36);
        if ( !v63 || v7->IoStatus.Status != -1073741738 )
          break;
        if ( v33 )
          MicrosoftTelemetryAssertTriggeredNoArgsKM(v38, v37);
        KeWaitForSingleObject((char *)Context + 288, Executive, 0, 0, 0);
        ++v18;
      }
      while ( v18 <= 0x14 );
      Status = v7->IoStatus.Status;
      if ( Status )
      {
        SetFileContext = 0;
        if ( !v63 )
          goto LABEL_11;
        if ( Status == 260 )
          MicrosoftTelemetryAssertTriggeredNoArgsKM(v38, v37);
        if ( !v63 )
          goto LABEL_11;
        if ( !v65 && !*((_BYTE *)Context + 282) )
        {
          SetFileContext = PrjfCreateTombstone(Instance, (struct _UNICODE_STRING *)(*(_QWORD *)(a4 + 48) + 8LL), v66);
          if ( SetFileContext < 0 )
          {
            if ( (BYTE2(xmmword_14001A3D0) & 8) != 0
              || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v48) = BYTE2(xmmword_14001A3D0) & 8;
              LOBYTE(v49) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
              WPP_RECORDER_AND_TRACE_SF_sDdZ(
                531,
                v48,
                v49,
                *((_QWORD *)WPP_GLOBAL_Control + 8),
                2,
                19,
                30,
                (__int64)WPP_3f08b24f959433411191d1ccab0ccd17_Traceguids,
                (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\tombstone.c",
                118,
                SetFileContext,
                *(_QWORD *)(a4 + 48) + 8LL);
            }
            PrjfTelemetryTombstoneFailureOperation(1, 1, SetFileContext);
          }
        }
      }
      else
      {
        v40 = v75;
        WORD1(P[0]) = *(_WORD *)(*(_QWORD *)(a4 + 48) + 8LL) - *((_WORD *)v75 + 20);
        if ( (int)PrjfAllocateUnicodeString(1852197456, (__int64)P) >= 0 )
        {
          if ( (int)PrjfConvertFullPathToRelative(v40 + 5, (PCWCH *)(*(_QWORD *)(a4 + 48) + 8LL), (__int64)P) < 0 )
            MicrosoftTelemetryAssertTriggeredNoArgsKM(v44, v43);
          v45 = FileObject;
          SetFileContext = PrjfGetSetFileContext(Instance, FileObject, 0, 0, (__int128 *)v77, (__int64)P, 0, &v73);
          if ( SetFileContext < 0 )
          {
            if ( (BYTE10(xmmword_14001A3D0) & 8) != 0
              || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v46) = BYTE10(xmmword_14001A3D0) & 8;
              LOBYTE(v47) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
              WPP_RECORDER_AND_TRACE_SF_sDdZ(
                787,
                v46,
                v47,
                *((_QWORD *)WPP_GLOBAL_Control + 8),
                3,
                19,
                29,
                (__int64)WPP_3f08b24f959433411191d1ccab0ccd17_Traceguids,
                (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\tombstone.c",
                82,
                SetFileContext,
                (__int64)&v45->FileName);
            }
            SetFileContext = 0;
          }
          v67 = v73;
        }
        else
        {
          if ( (BYTE2(xmmword_14001A3D0) & 8) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v41) = BYTE2(xmmword_14001A3D0) & 8;
            LOBYTE(v42) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            WPP_RECORDER_AND_TRACE_SF_sD(
              531,
              v41,
              v42,
              *((_QWORD *)WPP_GLOBAL_Control + 8),
              2,
              19,
              28,
              (__int64)WPP_3f08b24f959433411191d1ccab0ccd17_Traceguids,
              (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\tombstone.c",
              55);
          }
          SetFileContext = 0;
        }
      }
      if ( v63 )
      {
        v50 = PrjfRemoveInMemoryTombstone(Instance);
        SetFileContext = v50;
        if ( v50 < 0 )
        {
          if ( (BYTE2(xmmword_14001A3D0) & 8) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v51) = BYTE2(xmmword_14001A3D0) & 8;
            LOBYTE(v52) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            WPP_RECORDER_AND_TRACE_SF_sDL(
              531,
              v51,
              v52,
              *((_QWORD *)WPP_GLOBAL_Control + 8),
              2,
              19,
              31,
              (__int64)WPP_3f08b24f959433411191d1ccab0ccd17_Traceguids,
              (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\tombstone.c",
              136,
              v50);
          }
          PrjfTelemetryTombstoneFailureOperation(2, 1, SetFileContext);
          SetFileContext = 0;
        }
      }
    }
    else if ( (BYTE2(xmmword_14001A3D0) & 8) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v14) = BYTE2(xmmword_14001A3D0) & 8;
      LOBYTE(v15) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDL(
        531,
        v14,
        v15,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        19,
        22,
        (__int64)WPP_3f08b24f959433411191d1ccab0ccd17_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\tombstone.c",
        73,
        v13);
    }
LABEL_11:
    v10 = (void *)v67;
    goto LABEL_12;
  }
  if ( !v7->TagData )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(Data, a5);
  TagData = v7->TagData;
  if ( !TagData || (v54 = TagData->UnparsedNameLength == 0, v55 = -1073741766, v54) )
    v55 = -1073741772;
  v7->IoStatus.Status = v55;
  v7->TagData = 0;
  FltSetCallbackDataDirty(v7);
LABEL_12:
  if ( P[1] )
    ExFreePoolWithTag(P[1], 0x6E664A50u);
  if ( FileHandle )
    FltClose(FileHandle);
  if ( Object )
    ObfDereferenceObject(Object);
  if ( Context )
    FltReleaseContext(Context);
  if ( v10 )
    FltReleaseContext(v10);
  return (unsigned int)SetFileContext;
}

```

## disassembly

```asm
0x140042eac  push    rbp
0x140042eae  push    rbx
0x140042eaf  push    rsi
0x140042eb0  push    rdi
0x140042eb1  push    r12
0x140042eb3  push    r13
0x140042eb5  push    r14
0x140042eb7  push    r15
0x140042eb9  lea     rbp, [rsp-8]
0x140042ebe  sub     rsp, 108h
0x140042ec5  mov     rax, cs:__security_cookie
0x140042ecc  xor     rax, rsp
0x140042ecf  mov     [rbp+40h+var_48], rax
0x140042ed3  mov     rax, [rcx+10h]
0x140042ed7  xor     r15d, r15d
0x140042eda  xorps   xmm0, xmm0
0x140042edd  mov     [rbp+40h+FileObject], r8
0x140042ee1  xor     r8d, r8d
0x140042ee4  mov     [rsp+140h+var_C8], r15
0x140042ee9  mov     r13, rdx
0x140042eec  mov     [rbp+40h+var_98], r15
0x140042ef0  mov     rdx, [rbp+40h+arg_20]
0x140042ef4  mov     rdi, rcx
0x140042ef7  mov     cl, [rax+23h]
0x140042efa  mov     r14, r9
0x140042efd  mov     [rbp+40h+var_B8], r15d
0x140042f01  mov     ebx, r15d
0x140042f04  mov     [rbp+40h+FileHandle], r15
0x140042f08  mov     esi, r15d
0x140042f0b  mov     [rbp+40h+Object], r15
0x140042f0f  mov     [rbp+40h+var_A0], r15d
0x140042f13  mov     [rbp+40h+var_50], r8
0x140042f17  mov     [rbp+40h+var_80], rdx
0x140042f1b  mov     [rbp+40h+Context], r15
0x140042f1f  mov     [rsp+140h+var_D0], r15b
0x140042f24  movups  [rbp+40h+FileInformation], xmm0
0x140042f28  movups  xmmword ptr [rbp+40h+P], xmm0
0x140042f2c  test    rdx, rdx
0x140042f2f  jnz     short loc_140042F96
0x140042f31  bts     dword ptr [rax+20h], 15h
0x140042f36  mov     rcx, rdi; Data
0x140042f39  call    cs:__imp_FltSetCallbackDataDirty
0x140042f40  nop     dword ptr [rax+rax+00h]
0x140042f45  mov     r8, [r14+38h]
0x140042f49  test    r8, r8
0x140042f4c  jz      short loc_140042F7F
0x140042f4e  mov     rcx, cs:Globals
0x140042f55  mov     rdx, rdi
0x140042f58  call    cs:__imp_FltRemoveOpenReparseEntry
0x140042f5f  nop     dword ptr [rax+rax+00h]
0x140042f64  mov     rdx, [r14+38h]; Entry
0x140042f68  lea     rcx, stru_14001A6C0; Lookaside
0x140042f6f  call    cs:__imp_ExFreeToPagedLookasideList
0x140042f76  nop     dword ptr [rax+rax+00h]
0x140042f7b  mov     [r14+38h], r15
0x140042f7f  mov     rdx, rdi; CallbackData
0x140042f82  mov     rcx, r13; InitiatingInstance
0x140042f85  call    cs:__imp_FltReissueSynchronousIo
0x140042f8c  nop     dword ptr [rax+rax+00h]
0x140042f91  jmp     loc_14004303E
0x140042f96  cmp     cl, 1
0x140042f99  jz      loc_1400437FB
0x140042f9f  cmp     cl, 4
0x140042fa2  jz      loc_1400437FB
0x140042fa8  movups  xmm0, xmmword ptr [rdx]
0x140042fab  mov     rcx, [r9+30h]; FileNameInformation
0x140042faf  movdqu  xmmword ptr [rbp+40h+var_70], xmm0
0x140042fb4  call    cs:__imp_FltParseFileNameInformation
0x140042fbb  nop     dword ptr [rax+rax+00h]
0x140042fc0  mov     ebx, eax
0x140042fc2  test    eax, eax
0x140042fc4  jns     loc_1400430CE
0x140042fca  mov     dl, byte ptr cs:xmmword_14001A3D0+2
0x140042fd0  lea     rsi, WPP_RECORDER_INITIALIZED
0x140042fd7  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140042fde  setnz   r8b
0x140042fe2  and     dl, 8
0x140042fe5  jnz     short loc_140042FEC
0x140042fe7  test    r8b, r8b
0x140042fea  jz      short loc_140043039
0x140042fec  mov     r9, cs:WPP_GLOBAL_Control
0x140042ff3  lea     r15, aOnecoreBaseFsG_6; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140042ffa  mov     dword ptr [rsp+140h+var_F0], eax
0x140042ffe  lea     r12, WPP_3f08b24f959433411191d1ccab0ccd17_Traceguids
0x140043005  mov     dword ptr [rsp+140h+var_F8], 449h
0x14004300d  mov     ecx, 213h
0x140043012  mov     [rsp+140h+var_100], r15
0x140043017  mov     r9, [r9+40h]
0x14004301b  mov     [rsp+140h+var_108], r12
0x140043020  mov     word ptr [rsp+140h+var_110], 16h
0x140043027  mov     dword ptr [rsp+140h+LengthReturned], 13h
0x14004302f  mov     byte ptr [rsp+140h+FileInformationClass], 2
0x140043034  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140043039  mov     rsi, [rsp+140h+var_C8]
0x14004303e  mov     rcx, [rbp+40h+P+8]; P
0x140043042  test    rcx, rcx
0x140043045  jz      short loc_140043058
0x140043047  mov     edx, 6E664A50h; Tag
0x14004304c  call    cs:__imp_ExFreePoolWithTag
0x140043053  nop     dword ptr [rax+rax+00h]
0x140043058  mov     rcx, [rbp+40h+FileHandle]; FileHandle
0x14004305c  test    rcx, rcx
0x14004305f  jz      short loc_14004306D
0x140043061  call    cs:__imp_FltClose
0x140043068  nop     dword ptr [rax+rax+00h]
0x14004306d  mov     rcx, [rbp+40h+Object]; Object
0x140043071  test    rcx, rcx
0x140043074  jz      short loc_140043082
0x140043076  call    cs:__imp_ObfDereferenceObject
0x14004307d  nop     dword ptr [rax+rax+00h]
0x140043082  mov     rcx, [rbp+40h+Context]; Context
0x140043086  test    rcx, rcx
0x140043089  jz      short loc_140043097
0x14004308b  call    cs:__imp_FltReleaseContext
0x140043092  nop     dword ptr [rax+rax+00h]
0x140043097  test    rsi, rsi
0x14004309a  jz      short loc_1400430AB
0x14004309c  mov     rcx, rsi; Context
0x14004309f  call    cs:__imp_FltReleaseContext
0x1400430a6  nop     dword ptr [rax+rax+00h]
0x1400430ab  mov     eax, ebx
0x1400430ad  mov     rcx, [rbp+40h+var_48]
0x1400430b1  xor     rcx, rsp; StackCookie
0x1400430b4  call    __security_check_cookie
0x1400430b9  add     rsp, 108h
0x1400430c0  pop     r15
0x1400430c2  pop     r14
0x1400430c4  pop     r13
0x1400430c6  pop     r12
0x1400430c8  pop     rdi
0x1400430c9  pop     rsi
0x1400430ca  pop     rbx
0x1400430cb  pop     rbp
0x1400430cc  retn
0x1400430ce  mov     rcx, [r14+30h]
0x1400430d2  lea     rax, [rsp+140h+var_D0]
0x1400430d7  mov     [rsp+140h+var_E8], r15
0x1400430dc  add     rcx, 8
0x1400430e0  mov     [rsp+140h+var_F0], rax
0x1400430e5  mov     r9d, 10080h
0x1400430eb  mov     [rsp+140h+var_F8], r15
0x1400430f0  lea     rax, [rbp+40h+Object]
0x1400430f4  mov     [rsp+140h+var_100], r15
0x1400430f9  mov     r8, r13
0x1400430fc  mov     [rsp+140h+var_108], r15
0x140043101  xor     edx, edx
0x140043103  mov     [rsp+140h+var_110], rax
0x140043108  lea     rax, [rbp+40h+FileHandle]
0x14004310c  mov     [rsp+140h+LengthReturned], rax
0x140043111  mov     [rsp+140h+var_CF], r15b
0x140043116  mov     [rsp+140h+var_CE], r15b
0x14004311b  call    PrjfOpenAsReparsePoint
0x140043120  xor     ebx, ebx
0x140043122  lea     rsi, WPP_RECORDER_INITIALIZED
0x140043129  lea     r15, aOnecoreBaseFsG_6; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140043130  lea     r12, WPP_3f08b24f959433411191d1ccab0ccd17_Traceguids
0x140043137  cmp     [rsp+140h+var_D0], bl
0x14004313b  jz      loc_1400434C1
0x140043141  mov     rdx, [rbp+40h+Object]; FileObject
0x140043145  lea     rax, [rbp+40h+Context]
0x140043149  mov     [rsp+140h+var_108], rax; __int64
0x14004314e  xor     r9d, r9d
0x140043151  mov     [rsp+140h+var_110], rbx; __int64
0x140043156  mov     r8b, 1
0x140043159  mov     [rsp+140h+LengthReturned], rbx; __int64
0x14004315e  mov     rcx, r13; Instance
0x140043161  mov     qword ptr [rsp+140h+FileInformationClass], rbx; __int64
0x140043166  call    PrjfGetSetFileContext
0x14004316b  mov     ebx, eax
0x14004316d  test    eax, eax
0x14004316f  jns     loc_1400431FA
0x140043175  mov     dl, byte ptr cs:xmmword_14001A3D0+2
0x14004317b  lea     rsi, WPP_RECORDER_INITIALIZED
0x140043182  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140043189  setnz   r8b
0x14004318d  and     dl, 8
0x140043190  jnz     short loc_14004319B
0x140043192  test    r8b, r8b
0x140043195  jz      loc_140043039
0x14004319b  mov     rax, [rbp+40h+Object]
0x14004319f  lea     r15, aOnecoreBaseFsG_6; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400431a6  add     rax, 58h ; 'X'
0x1400431aa  lea     r12, WPP_3f08b24f959433411191d1ccab0ccd17_Traceguids
0x1400431b1  mov     [rsp+140h+var_E8], rax
0x1400431b6  mov     dword ptr [rsp+140h+var_F0], ebx
0x1400431ba  mov     dword ptr [rsp+140h+var_F8], 472h
0x1400431c2  mov     [rsp+140h+var_100], r15
0x1400431c7  mov     [rsp+140h+var_108], r12
0x1400431cc  mov     word ptr [rsp+140h+var_110], 17h
0x1400431d3  mov     r9, cs:WPP_GLOBAL_Control
0x1400431da  mov     ecx, 213h
0x1400431df  mov     dword ptr [rsp+140h+LengthReturned], 13h
0x1400431e7  mov     byte ptr [rsp+140h+FileInformationClass], 2
0x1400431ec  mov     r9, [r9+40h]
0x1400431f0  call    WPP_RECORDER_AND_TRACE_SF_sDdZ
0x1400431f5  jmp     loc_140043039
0x1400431fa  mov     rdx, [rbp+40h+Object]; FileObject
0x1400431fe  lea     rax, [rbp+40h+var_A0]
0x140043202  mov     [rsp+140h+LengthReturned], rax; LengthReturned
0x140043207  lea     r8, [rbp+40h+FileInformation]; FileInformation
0x14004320b  mov     r9d, 18h; Length
0x140043211  mov     [rsp+140h+FileInformationClass], 5; FileInformationClass
0x140043219  mov     rcx, r13; Instance
0x14004321c  call    cs:__imp_FltQueryInformationFile
0x140043223  nop     dword ptr [rax+rax+00h]
0x140043228  mov     ebx, eax
0x14004322a  test    eax, eax
0x14004322c  jns     short loc_140043291
0x14004322e  mov     dl, byte ptr cs:xmmword_14001A3D0+2
0x140043234  lea     rsi, WPP_RECORDER_INITIALIZED
0x14004323b  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140043242  setnz   r8b
0x140043246  and     dl, 8
0x140043249  jnz     short loc_140043254
0x14004324b  test    r8b, r8b
0x14004324e  jz      loc_140043039
0x140043254  mov     rax, [rbp+40h+Object]
0x140043258  lea     r15, aOnecoreBaseFsG_6; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14004325f  add     rax, 58h ; 'X'
0x140043263  lea     r12, WPP_3f08b24f959433411191d1ccab0ccd17_Traceguids
0x14004326a  mov     [rsp+140h+var_E8], rax
0x14004326f  mov     dword ptr [rsp+140h+var_F0], ebx
0x140043273  mov     dword ptr [rsp+140h+var_F8], 486h
0x14004327b  mov     [rsp+140h+var_100], r15
0x140043280  mov     [rsp+140h+var_108], r12
0x140043285  mov     word ptr [rsp+140h+var_110], 18h
0x14004328c  jmp     loc_1400431D3
0x140043291  mov     al, byte ptr [rbp+40h+var_50+5]
0x140043294  mov     rcx, r13; Instance
0x140043297  mov     r9, [r14+30h]
0x14004329b  mov     r8b, al
0x14004329e  mov     [rsp+140h+LengthReturned], 0; __int64
0x1400432a7  mov     [rsp+140h+var_CD], al
0x1400432ab  mov     qword ptr [rsp+140h+FileInformationClass], 0; FileObject
0x1400432b4  lea     rdx, [r9+58h]; SourceString
0x1400432b8  call    PrjfAddInMemoryTombstone
0x1400432bd  mov     ebx, eax
0x1400432bf  test    eax, eax
0x1400432c1  jns     loc_140043358
0x1400432c7  mov     dl, byte ptr cs:xmmword_14001A3D0+2
0x1400432cd  lea     rsi, WPP_RECORDER_INITIALIZED
0x1400432d4  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400432db  setnz   r8b
0x1400432df  and     dl, 8
0x1400432e2  jnz     short loc_1400432E9
0x1400432e4  test    r8b, r8b
0x1400432e7  jz      short loc_140043343
0x1400432e9  mov     rax, [r14+30h]
0x1400432ed  lea     r15, aOnecoreBaseFsG_6; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400432f4  mov     r9, cs:WPP_GLOBAL_Control
0x1400432fb  lea     r12, WPP_3f08b24f959433411191d1ccab0ccd17_Traceguids
0x140043302  add     rax, 8
0x140043306  mov     ecx, 213h
0x14004330b  mov     [rsp+140h+var_E8], rax
0x140043310  mov     dword ptr [rsp+140h+var_F0], ebx
0x140043314  mov     r9, [r9+40h]
0x140043318  mov     dword ptr [rsp+140h+var_F8], 4A3h
0x140043320  mov     [rsp+140h+var_100], r15
0x140043325  mov     [rsp+140h+var_108], r12
0x14004332a  mov     word ptr [rsp+140h+var_110], 19h
0x140043331  mov     dword ptr [rsp+140h+LengthReturned], 13h
0x140043339  mov     byte ptr [rsp+140h+FileInformationClass], 2
0x14004333e  call    WPP_RECORDER_AND_TRACE_SF_sDdZ
0x140043343  mov     edx, 1
0x140043348  mov     r8d, ebx
0x14004334b  lea     ecx, [rdx+2]
0x14004334e  call    PrjfTelemetryTombstoneFailureOperation
0x140043353  jmp     loc_140043039
0x140043358  mov     rdx, [rbp+40h+Object]; FileObject
0x14004335c  lea     r8, [rbp+40h+var_B8]; FileInformation
0x140043360  mov     r9d, 1; Length
0x140043366  mov     [rbp+40h+var_B8], 3
0x14004336d  mov     rcx, r13; Instance
0x140043370  mov     [rsp+140h+FileInformationClass], 40h ; '@'; FileInformationClass
0x140043378  call    cs:__imp_FltSetInformationFile
0x14004337f  nop     dword ptr [rax+rax+00h]
0x140043384  mov     ebx, eax
0x140043386  cmp     eax, 0C000029Ch
0x14004338b  jz      short loc_140043398
0x14004338d  cmp     eax, 0C000000Dh
0x140043392  jnz     loc_140043423
0x140043398  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14004339f  mov     dl, byte ptr cs:xmmword_14001A3D0+9
0x1400433a5  setnz   r8b
0x1400433a9  and     dl, 40h
0x1400433ac  jnz     short loc_1400433B3
0x1400433ae  test    r8b, r8b
0x1400433b1  jz      short loc_1400433EE
0x1400433b3  mov     r9, cs:WPP_GLOBAL_Control
0x1400433ba  mov     ecx, 30Eh
0x1400433bf  mov     dword ptr [rsp+140h+var_F8], 4C0h
0x1400433c7  mov     [rsp+140h+var_100], r15
0x1400433cc  mov     [rsp+140h+var_108], r12
0x1400433d1  mov     r9, [r9+40h]
0x1400433d5  mov     word ptr [rsp+140h+var_110], 1Ah
0x1400433dc  mov     dword ptr [rsp+140h+LengthReturned], 0Eh
0x1400433e4  mov     byte ptr [rsp+140h+FileInformationClass], 3
0x1400433e9  call    WPP_RECORDER_AND_TRACE_SF_sD
0x1400433ee  mov     rdx, [rbp+40h+Object]; FileObject
0x1400433f2  lea     r8, [rsp+140h+var_CF]; FileInformation
  ... truncated ...
```
