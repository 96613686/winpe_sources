# HsmiCreateEnsureDirectoryFullyPopulated

- ea: `0x14006486c`
- end: `0x140065017`
- name: `HsmiCreateEnsureDirectoryFullyPopulated`
- size: `1963`
- prototype: `__int64 __fastcall(__int64, struct _FLT_CALLBACK_DATA *, char, unsigned __int16, _BYTE *, _BYTE *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140063ef8`

## callees

- `0x140001d00`
- `0x140003c50`
- `0x140006da0`
- `0x140007ddc`
- `0x1400090b4`
- `0x140009300`
- `0x14000abb8`
- `0x14000c8c0`
- `0x14001e300`
- `0x14004c6d0`
- `0x140051810`
- `0x14005ac10`
- `0x14006486c`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140064fa9`
- `ntoskrnl!ObfDereferenceObject` at `0x140064fa9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064fed`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064fed`
- `ntoskrnl!ExAllocatePool2` at `0x140064981`
- `ntoskrnl!ExAllocatePool2` at `0x140064ada`
- `ntoskrnl!ExAllocatePool2` at `0x140064981`
- `ntoskrnl!ExAllocatePool2` at `0x140064ada`
- `FLTMGR!FltCreateFileEx` at `0x140064d1c`
- `FLTMGR!FltCreateFileEx` at `0x140064d1c`
- `FLTMGR!FltClose` at `0x140064fbe`
- `FLTMGR!FltClose` at `0x140064fbe`
- `FLTMGR!FltGetRequestorProcess` at `0x1400648df`
- `FLTMGR!FltGetRequestorProcess` at `0x1400648df`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x140064a3d`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x140064a3d`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140064fd3`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140064fd3`
- `FLTMGR!FltReleaseContext` at `0x140064f49`
- `FLTMGR!FltReleaseContext` at `0x140064f49`

## pseudocode

```c
__int64 __fastcall HsmiCreateEnsureDirectoryFullyPopulated(
        __int64 a1,
        struct _FLT_CALLBACK_DATA *a2,
        char a3,
        unsigned __int16 a4,
        _BYTE *a5,
        _BYTE *a6)
{
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  struct _FLT_INSTANCE *TargetInstance; // r12
  PFILE_OBJECT TargetFileObject; // r15
  PEPROCESS RequestorProcess; // rax
  bool v11; // zf
  _BYTE *v12; // rax
  NTSTATUS FileNameInformationUnsafe; // edi
  struct _FILE_OBJECT *RelatedFileObject; // rcx
  USHORT v15; // dx
  PDEVICE_OBJECT v16; // rcx
  __int64 v17; // rdx
  char *v18; // r13
  __int64 v19; // rbx
  USHORT v20; // r9
  unsigned __int64 v21; // rcx
  unsigned __int64 Length; // rax
  __int16 v23; // bx
  __m128i v24; // xmm0
  __int64 v25; // rdx
  PDEVICE_OBJECT v26; // rcx
  __int64 v27; // rdx
  char v28; // bl
  struct _FLT_CALLBACK_DATA *v29; // r13
  __int64 StreamHandleContext; // rax
  void *v31; // r15
  unsigned __int16 v32; // dx
  void *v33; // r10
  __int64 v34; // r8
  unsigned __int16 v35; // cx
  __int16 v36; // r9
  PDEVICE_OBJECT v37; // rcx
  __int64 v38; // rdx
  USHORT pusResult[8]; // [rsp+88h] [rbp-80h] BYREF
  int v41; // [rsp+98h] [rbp-70h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+A0h] [rbp-68h] BYREF
  __int128 v43; // [rsp+A8h] [rbp-60h] BYREF
  PFILE_OBJECT FileObject; // [rsp+B8h] [rbp-50h] BYREF
  __int128 v45; // [rsp+C0h] [rbp-48h] BYREF
  __m128i v46; // [rsp+D8h] [rbp-30h] BYREF
  void *FileHandle; // [rsp+E8h] [rbp-20h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+F0h] [rbp-18h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+120h] [rbp+18h] BYREF
  PFLT_CONTEXT Contexta; // [rsp+180h] [rbp+78h]

  Iopb = a2->Iopb;
  v41 = 0;
  TargetInstance = Iopb->TargetInstance;
  TargetFileObject = Iopb->TargetFileObject;
  FileNameInformation = 0;
  v46 = 0;
  FileHandle = 0;
  v43 = 0;
  FileObject = 0;
  v45 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  IoStatusBlock = 0;
  *(_OWORD *)pusResult = 0;
  RequestorProcess = FltGetRequestorProcess(a2);
  v11 = (unsigned __int8)HsmOsIsSyncProviderProcess(RequestorProcess) == 0;
  v12 = a5;
  if ( !v11 )
  {
    FileNameInformationUnsafe = 0;
LABEL_3:
    *v12 = 1;
    goto LABEL_74;
  }
  RelatedFileObject = TargetFileObject->RelatedFileObject;
  *a5 = 0;
  if ( RelatedFileObject )
  {
    FileNameInformationUnsafe = FltGetFileNameInformationUnsafe(RelatedFileObject, 0, 0x101u, &FileNameInformation);
    HsmDbgBreakOnStatus(FileNameInformationUnsafe);
    if ( FileNameInformationUnsafe < 0 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v17 = 14;
        goto LABEL_73;
      }
      goto LABEL_74;
    }
    if ( RtlUShortAdd(TargetFileObject->FileName.Length, FileNameInformation->Name.Length, &pusResult[1]) < 0
      || RtlUShortAdd(pusResult[1], 4u, &pusResult[1]) < 0 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v17 = 15;
        goto LABEL_73;
      }
      goto LABEL_74;
    }
    *(_QWORD *)&pusResult[4] = ExAllocatePool2(256, pusResult[1], 1934979912);
    v18 = *(char **)&pusResult[4];
    FileNameInformationUnsafe = *(_QWORD *)&pusResult[4] == 0 ? 0xC000009A : 0;
    HsmDbgBreakOnStatus(FileNameInformationUnsafe);
    if ( !v18 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v17 = 16;
        goto LABEL_73;
      }
      goto LABEL_74;
    }
    memmove(v18, FileNameInformation->Name.Buffer, FileNameInformation->Name.Length);
    Length = FileNameInformation->Name.Length;
    v23 = Length + 2;
    *(_WORD *)&v18[2 * (Length >> 1)] = 92;
    memmove(&v18[(unsigned __int16)(Length + 2)], TargetFileObject->FileName.Buffer, TargetFileObject->FileName.Length);
    pusResult[0] = TargetFileObject->FileName.Length + v23;
    v21 = pusResult[0];
    v20 = pusResult[0];
LABEL_29:
    v24 = *(__m128i *)pusResult;
    *(_WORD *)&v18[2 * (v21 >> 1)] = 0;
    v25 = *(unsigned __int16 *)(a1 + 64);
    v46 = v24;
    v46.m128i_i16[1] = v24.m128i_i16[1] - a4;
    v46.m128i_i16[0] = v20 - a4;
    DWORD1(v43) = v24.m128i_i32[1];
    WORD1(v43) = v24.m128i_i16[1] - a4 - v25 + 2;
    LOWORD(v43) = v20 - a4 - v25 + 2;
    *((_QWORD *)&v43 + 1) = v25 + _mm_srli_si128(v46, 8).m128i_u64[0] - 2;
    FileNameInformationUnsafe = HsmpCldGetSyncPolicyByPath(a1, &v43, &v41);
    HsmDbgBreakOnStatus(FileNameInformationUnsafe);
    if ( FileNameInformationUnsafe < 0 )
    {
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_74;
      }
      v27 = 17;
      goto LABEL_34;
    }
    v28 = v41;
    if ( a3 && (v41 & 0xF0) == 0x10 )
    {
      v12 = a6;
      goto LABEL_3;
    }
    ObjectAttributes.ObjectName = (PUNICODE_STRING)&v46;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    FileNameInformationUnsafe = FltCreateFileEx(
                                  Filter,
                                  TargetInstance,
                                  &FileHandle,
                                  &FileObject,
                                  0x100180u,
                                  &ObjectAttributes,
                                  &IoStatusBlock,
                                  0,
                                  0,
                                  7u,
                                  1u,
                                  0x200020u,
                                  0,
                                  0,
                                  0x800u);
    HsmDbgBreakOnStatus(FileNameInformationUnsafe);
    if ( FileNameInformationUnsafe < 0 )
    {
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_74;
      }
      v27 = 18;
      goto LABEL_34;
    }
    FileNameInformationUnsafe = HsmpSetupContexts(a1, FileObject, 0, 0);
    HsmDbgBreakOnStatus(FileNameInformationUnsafe);
    if ( FileNameInformationUnsafe < 0 )
    {
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_74;
      }
      v27 = 19;
LABEL_34:
      WPP_SF_qqd(
        v26->AttachedDevice,
        v27,
        WPP_666dd97b4df534fdc194a0db3f3e286d_Traceguids,
        TargetInstance,
        a1,
        FileNameInformationUnsafe);
      goto LABEL_74;
    }
    v29 = a2;
    StreamHandleContext = HsmpGetStreamHandleContext(a2, TargetInstance, FileObject);
    v31 = (void *)StreamHandleContext;
    if ( !StreamHandleContext )
      goto LABEL_74;
    v32 = 0;
    v33 = *(void **)(StreamHandleContext + 16);
    Contexta = v33;
    *(_WORD *)(*((_QWORD *)&v43 + 1) + 2 * ((unsigned __int64)(unsigned __int16)v43 >> 1)) = 0;
    if ( (v28 & 0xF0) == 0x10 )
    {
      v34 = *((_QWORD *)&v43 + 1) + WORD1(v43);
      v35 = 2;
      *((_QWORD *)&v45 + 1) = v34;
      LODWORD(v45) = 0x20000;
      if ( a4 <= 2u )
        goto LABEL_56;
      do
      {
        v36 = *(_WORD *)(v32 + v34);
        if ( !v36 )
          break;
        if ( v36 == 92 )
          break;
        v32 += 2;
        v35 += 2;
        LOWORD(v45) = v32;
        WORD1(v45) = v35;
      }
      while ( v35 < a4 );
      if ( v35 >= a4 )
LABEL_56:
        LOWORD(v45) = 0;
      else
        *(_WORD *)(v34 + 2 * ((unsigned __int64)v32 >> 1)) = 0;
    }
    FileNameInformationUnsafe = HsmpAcquireUserRequestRundownProtection(v33, v29);
    HsmDbgBreakOnStatus(FileNameInformationUnsafe);
    if ( FileNameInformationUnsafe >= 0 )
    {
      HsmpRecallInitiatePopulation(
        (_DWORD)v31,
        (_DWORD)Contexta,
        v29->Iopb->TargetFileObject,
        (_DWORD)v29,
        (__int64)&v43,
        (unsigned __int64)&v45 & -(__int64)((_WORD)v45 != 0));
      HsmpReleaseUserRequestRundownProtection(Contexta);
      FileNameInformationUnsafe = v29->IoStatus.Status;
      HsmDbgBreakOnStatus(FileNameInformationUnsafe);
      if ( FileNameInformationUnsafe >= 0 )
        goto LABEL_68;
      v37 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_68;
      }
      v38 = 21;
    }
    else
    {
      v37 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_68;
      }
      v38 = 20;
    }
    WPP_SF_qqd(
      v37->AttachedDevice,
      v38,
      WPP_666dd97b4df534fdc194a0db3f3e286d_Traceguids,
      TargetInstance,
      a1,
      FileNameInformationUnsafe);
LABEL_68:
    FltReleaseContext(v31);
    goto LABEL_74;
  }
  v15 = TargetFileObject->FileName.Length;
  pusResult[1] = *(_WORD *)(a1 + 64);
  FileNameInformationUnsafe = RtlUShortAdd(pusResult[1], v15, &pusResult[1]);
  if ( FileNameInformationUnsafe < 0 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v17 = 12;
LABEL_73:
      WPP_SF_qqqd(
        v16->AttachedDevice,
        v17,
        WPP_666dd97b4df534fdc194a0db3f3e286d_Traceguids,
        TargetInstance,
        a1,
        TargetFileObject,
        FileNameInformationUnsafe);
      goto LABEL_74;
    }
    goto LABEL_74;
  }
  *(_QWORD *)&pusResult[4] = ExAllocatePool2(256, pusResult[1], 1934979912);
  v18 = *(char **)&pusResult[4];
  FileNameInformationUnsafe = *(_QWORD *)&pusResult[4] == 0 ? 0xC000009A : 0;
  HsmDbgBreakOnStatus(FileNameInformationUnsafe);
  if ( v18 )
  {
    memmove(v18, *(const void **)(a1 + 72), *(unsigned __int16 *)(a1 + 64));
    v19 = (unsigned __int16)(*(_WORD *)(a1 + 64) - 2);
    memmove(&v18[v19], TargetFileObject->FileName.Buffer, TargetFileObject->FileName.Length);
    v20 = TargetFileObject->FileName.Length + v19;
    pusResult[0] = v20;
    v21 = v20;
    goto LABEL_29;
  }
  v16 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v17 = 13;
    goto LABEL_73;
  }
LABEL_74:
  if ( FileObject )
    ObfDereferenceObject(FileObject);
  if ( FileHandle )
    FltClose(FileHandle);
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  if ( *(_QWORD *)&pusResult[4] )
    ExFreePoolWithTag(*(PVOID *)&pusResult[4], 0x73557348u);
  return (unsigned int)FileNameInformationUnsafe;
}

```

## disassembly

```asm
0x14006486c  mov     rax, rsp
0x14006486f  mov     [rax+8], rbx
0x140064873  mov     [rax+20h], r9w
0x140064878  mov     [rax+18h], r8b
0x14006487c  mov     [rax+10h], rdx
0x140064880  push    rbp
0x140064881  push    rsi
0x140064882  push    rdi
0x140064883  push    r12
0x140064885  push    r13
0x140064887  push    r14
0x140064889  push    r15
0x14006488b  lea     rbp, [rax-68h]
0x14006488f  sub     rsp, 130h
0x140064896  mov     rax, [rdx+10h]
0x14006489a  xorps   xmm0, xmm0
0x14006489d  xor     ebx, ebx
0x14006489f  xorps   xmm1, xmm1
0x1400648a2  mov     r14, rcx
0x1400648a5  mov     [rbp+60h+var_D0], ebx
0x1400648a8  mov     rcx, rdx; CallbackData
0x1400648ab  mov     r12, [rax+10h]
0x1400648af  mov     r15, [rax+8]
0x1400648b3  mov     [rbp+60h+FileNameInformation], rbx
0x1400648b7  movups  [rbp+60h+var_90], xmm1
0x1400648bb  mov     [rbp+60h+FileHandle], rbx
0x1400648bf  movups  [rbp+60h+var_C0], xmm0
0x1400648c3  mov     [rbp+60h+FileObject], rbx
0x1400648c7  movups  [rbp+60h+var_A8], xmm1
0x1400648cb  movups  xmmword ptr [rbp+60h+var_78.Length], xmm0
0x1400648cf  movups  xmmword ptr [rbp+60h+var_78.ObjectName], xmm0
0x1400648d3  movups  xmmword ptr [rbp+60h+var_78.SecurityDescriptor], xmm0
0x1400648d7  movups  xmmword ptr [rbp+60h+var_48], xmm0
0x1400648db  movups  xmmword ptr [rbp+60h+pusResult], xmm0
0x1400648df  call    cs:__imp_FltGetRequestorProcess
0x1400648e6  nop     dword ptr [rax+rax+00h]
0x1400648eb  mov     rcx, rax
0x1400648ee  call    HsmOsIsSyncProviderProcess
0x1400648f3  test    al, al
0x1400648f5  mov     rax, [rbp+60h+arg_20]
0x1400648fc  jz      short loc_140064908
0x1400648fe  mov     edi, ebx
0x140064900  mov     byte ptr [rax], 1
0x140064903  jmp     loc_140064FA0
0x140064908  mov     rcx, [r15+40h]; FileObject
0x14006490c  mov     [rax], bl
0x14006490e  test    rcx, rcx
0x140064911  jnz     loc_140064A31
0x140064917  movzx   ecx, word ptr [r14+40h]; usAugend
0x14006491c  lea     r8, [rbp+60h+pusResult+2]; pusResult
0x140064920  movzx   edx, word ptr [r15+58h]; usAddend
0x140064925  mov     [rbp+60h+pusResult+2], cx
0x140064929  call    RtlUShortAdd
0x14006492e  mov     edi, eax
0x140064930  test    eax, eax
0x140064932  jns     short loc_14006496E
0x140064934  mov     rcx, cs:WPP_GLOBAL_Control
0x14006493b  lea     rax, WPP_GLOBAL_Control
0x140064942  cmp     rcx, rax
0x140064945  jz      loc_140064FA0
0x14006494b  mov     edx, [rcx+2Ch]
0x14006494e  test    dl, 1
0x140064951  jz      loc_140064FA0
0x140064957  mov     esi, 2
0x14006495c  cmp     [rcx+29h], sil
0x140064960  jb      loc_140064FA0
0x140064966  lea     edx, [rsi+0Ah]
0x140064969  jmp     loc_140064F7F
0x14006496e  movzx   edx, [rbp+60h+pusResult+2]
0x140064972  mov     ecx, 100h
0x140064977  mov     r8d, 73557348h
0x14006497d  mov     [rbp+60h+pusResult], bx
0x140064981  call    cs:__imp_ExAllocatePool2
0x140064988  nop     dword ptr [rax+rax+00h]
0x14006498d  mov     rcx, rax
0x140064990  mov     qword ptr [rbp+60h+pusResult+8], rax
0x140064994  neg     rcx
0x140064997  mov     r13, rax
0x14006499a  sbb     edi, edi
0x14006499c  not     edi
0x14006499e  and     edi, 0C000009Ah
0x1400649a4  mov     ecx, edi
0x1400649a6  call    HsmDbgBreakOnStatus
0x1400649ab  test    r13, r13
0x1400649ae  jnz     short loc_1400649E8
0x1400649b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400649b7  lea     rax, WPP_GLOBAL_Control
0x1400649be  cmp     rcx, rax
0x1400649c1  jz      loc_140064FA0
0x1400649c7  mov     eax, [rcx+2Ch]
0x1400649ca  test    al, 1
0x1400649cc  jz      loc_140064FA0
0x1400649d2  lea     esi, [r13+2]
0x1400649d6  cmp     [rcx+29h], sil
0x1400649da  jb      loc_140064FA0
0x1400649e0  lea     edx, [rsi+0Bh]
0x1400649e3  jmp     loc_140064F7F
0x1400649e8  movzx   r8d, word ptr [r14+40h]; Size
0x1400649ed  mov     rcx, r13; void *
0x1400649f0  mov     rdx, [r14+48h]; Src
0x1400649f4  call    memmove
0x1400649f9  movzx   eax, word ptr [r14+40h]
0x1400649fe  mov     esi, 2
0x140064a03  movzx   r8d, word ptr [r15+58h]; Size
0x140064a08  sub     ax, si
0x140064a0b  mov     rdx, [r15+60h]; Src
0x140064a0f  movzx   ebx, ax
0x140064a12  lea     rcx, [rbx+r13]; void *
0x140064a16  call    memmove
0x140064a1b  add     bx, [r15+58h]
0x140064a20  movzx   r9d, bx
0x140064a24  mov     [rbp+60h+pusResult], r9w
0x140064a29  mov     ecx, r9d
0x140064a2c  jmp     loc_140064B9A
0x140064a31  lea     r9, [rbp+60h+FileNameInformation]; FileNameInformation
0x140064a35  xor     edx, edx; Instance
0x140064a37  mov     r8d, 101h; NameOptions
0x140064a3d  call    cs:__imp_FltGetFileNameInformationUnsafe
0x140064a44  nop     dword ptr [rax+rax+00h]
0x140064a49  mov     ecx, eax
0x140064a4b  mov     edi, eax
0x140064a4d  call    HsmDbgBreakOnStatus
0x140064a52  test    edi, edi
0x140064a54  jns     short loc_140064A8F
0x140064a56  mov     rcx, cs:WPP_GLOBAL_Control
0x140064a5d  lea     rax, WPP_GLOBAL_Control
0x140064a64  cmp     rcx, rax
0x140064a67  jz      loc_140064FA0
0x140064a6d  mov     eax, [rcx+2Ch]
0x140064a70  test    al, 1
0x140064a72  jz      loc_140064FA0
0x140064a78  mov     esi, 2
0x140064a7d  cmp     [rcx+29h], sil
0x140064a81  jb      loc_140064FA0
0x140064a87  lea     edx, [rsi+0Ch]
0x140064a8a  jmp     loc_140064F7F
0x140064a8f  mov     rdx, [rbp+60h+FileNameInformation]
0x140064a93  lea     r8, [rbp+60h+pusResult+2]; pusResult
0x140064a97  movzx   ecx, word ptr [r15+58h]; usAugend
0x140064a9c  movzx   edx, word ptr [rdx+8]; usAddend
0x140064aa0  call    RtlUShortAdd
0x140064aa5  test    eax, eax
0x140064aa7  js      loc_140064F57
0x140064aad  movzx   ecx, [rbp+60h+pusResult+2]; usAugend
0x140064ab1  lea     r8, [rbp+60h+pusResult+2]; pusResult
0x140064ab5  mov     edx, 4; usAddend
0x140064aba  call    RtlUShortAdd
0x140064abf  test    eax, eax
0x140064ac1  js      loc_140064F57
0x140064ac7  movzx   edx, [rbp+60h+pusResult+2]
0x140064acb  mov     ecx, 100h
0x140064ad0  mov     r8d, 73557348h
0x140064ad6  mov     [rbp+60h+pusResult], bx
0x140064ada  call    cs:__imp_ExAllocatePool2
0x140064ae1  nop     dword ptr [rax+rax+00h]
0x140064ae6  mov     rcx, rax
0x140064ae9  mov     qword ptr [rbp+60h+pusResult+8], rax
0x140064aed  neg     rcx
0x140064af0  mov     r13, rax
0x140064af3  sbb     edi, edi
0x140064af5  not     edi
0x140064af7  and     edi, 0C000009Ah
0x140064afd  mov     ecx, edi
0x140064aff  call    HsmDbgBreakOnStatus
0x140064b04  test    r13, r13
0x140064b07  jnz     short loc_140064B41
0x140064b09  mov     rcx, cs:WPP_GLOBAL_Control
0x140064b10  lea     rax, WPP_GLOBAL_Control
0x140064b17  cmp     rcx, rax
0x140064b1a  jz      loc_140064FA0
0x140064b20  mov     eax, [rcx+2Ch]
0x140064b23  test    al, 1
0x140064b25  jz      loc_140064FA0
0x140064b2b  lea     esi, [r13+2]
0x140064b2f  cmp     [rcx+29h], sil
0x140064b33  jb      loc_140064FA0
0x140064b39  lea     edx, [rsi+0Eh]
0x140064b3c  jmp     loc_140064F7F
0x140064b41  mov     rdx, [rbp+60h+FileNameInformation]
0x140064b45  mov     rcx, r13; void *
0x140064b48  movzx   r8d, word ptr [rdx+8]; Size
0x140064b4d  mov     rdx, [rdx+10h]; Src
0x140064b51  call    memmove
0x140064b56  mov     rax, [rbp+60h+FileNameInformation]
0x140064b5a  mov     esi, 2
0x140064b5f  movzx   ecx, word ptr [rax+8]
0x140064b63  mov     eax, ecx
0x140064b65  add     cx, si
0x140064b68  shr     rax, 1
0x140064b6b  movzx   ebx, cx
0x140064b6e  mov     word ptr [r13+rax*2+0], 5Ch ; '\'
0x140064b76  movzx   r8d, word ptr [r15+58h]; Size
0x140064b7b  lea     rcx, [rbx+r13]; void *
0x140064b7f  mov     rdx, [r15+60h]; Src
0x140064b83  call    memmove
0x140064b88  add     bx, [r15+58h]
0x140064b8d  movzx   edx, bx
0x140064b90  mov     [rbp+60h+pusResult], dx
0x140064b94  mov     ecx, edx
0x140064b96  movzx   r9d, dx
0x140064b9a  sub     r9w, [rbp+60h+arg_18]
0x140064ba2  xor     ebx, ebx
0x140064ba4  movaps  xmm0, xmmword ptr [rbp+60h+pusResult]
0x140064ba8  shr     rcx, 1
0x140064bab  mov     [r13+rcx*2+0], bx
0x140064bb1  movzx   edx, word ptr [r14+40h]
0x140064bb6  movdqa  [rbp+60h+var_90], xmm0
0x140064bbb  movzx   r8d, word ptr [rbp+60h+var_90+2]
0x140064bc0  sub     r8w, [rbp+60h+arg_18]
0x140064bc8  mov     word ptr [rbp+60h+var_90+2], r8w
0x140064bcd  sub     r8w, dx
0x140064bd1  mov     word ptr [rbp+60h+var_90], r9w
0x140064bd6  add     r8w, si
0x140064bda  movaps  xmm0, [rbp+60h+var_90]
0x140064bde  sub     r9w, dx
0x140064be2  movdqa  [rbp+60h+var_C0], xmm0
0x140064be7  add     r9w, si
0x140064beb  psrldq  xmm0, 8
0x140064bf0  movq    rcx, xmm0
0x140064bf5  mov     word ptr [rbp+60h+var_C0+2], r8w
0x140064bfa  add     rcx, 0FFFFFFFFFFFFFFFEh
0x140064bfe  mov     word ptr [rbp+60h+var_C0], r9w
0x140064c03  add     rcx, rdx
0x140064c06  lea     r8, [rbp+60h+var_D0]
0x140064c0a  mov     qword ptr [rbp+60h+var_C0+8], rcx
0x140064c0e  lea     rdx, [rbp+60h+var_C0]
0x140064c12  mov     rcx, r14
0x140064c15  call    HsmpCldGetSyncPolicyByPath
0x140064c1a  mov     ecx, eax
0x140064c1c  mov     edi, eax
0x140064c1e  call    HsmDbgBreakOnStatus
0x140064c23  test    edi, edi
0x140064c25  jns     short loc_140064C77
0x140064c27  mov     rcx, cs:WPP_GLOBAL_Control
0x140064c2e  lea     rax, WPP_GLOBAL_Control
0x140064c35  cmp     rcx, rax
0x140064c38  jz      loc_140064FA0
0x140064c3e  mov     eax, [rcx+2Ch]
0x140064c41  test    al, 1
0x140064c43  jz      loc_140064FA0
0x140064c49  cmp     [rcx+29h], sil
0x140064c4d  jb      loc_140064FA0
0x140064c53  lea     edx, [rbx+11h]
0x140064c56  mov     rcx, [rcx+18h]
0x140064c5a  lea     r8, WPP_666dd97b4df534fdc194a0db3f3e286d_Traceguids
0x140064c61  mov     dword ptr [rsp+160h+ObjectAttributes], edi
0x140064c65  mov     r9, r12
0x140064c68  mov     qword ptr [rsp+160h+DesiredAccess], r14
0x140064c6d  call    WPP_SF_qqd
0x140064c72  jmp     loc_140064FA0
0x140064c77  mov     ebx, [rbp+60h+var_D0]
0x140064c7a  xor     r15d, r15d
0x140064c7d  cmp     [rbp+60h+arg_10], r15b
0x140064c84  jz      short loc_140064C9A
0x140064c86  mov     eax, ebx
0x140064c88  and     al, 0F0h
0x140064c8a  cmp     al, 10h
0x140064c8c  jnz     short loc_140064C9A
0x140064c8e  mov     rax, [rbp+60h+arg_28]
0x140064c95  jmp     loc_140064900
0x140064c9a  mov     rcx, cs:Filter; Filter
0x140064ca1  lea     rax, [rbp+60h+var_90]
0x140064ca5  mov     dword ptr [rsp+70h], 800h; Flags
0x140064cad  lea     r9, [rbp+60h+FileObject]; FileObject
0x140064cb1  mov     [rsp+160h+EaLength], r15d; EaLength
0x140064cb6  lea     r8, [rbp+60h+FileHandle]; FileHandle
0x140064cba  mov     [rsp+160h+EaBuffer], r15; EaBuffer
0x140064cbf  xorps   xmm0, xmm0
0x140064cc2  mov     [rsp+160h+CreateOptions], 200020h; CreateOptions
0x140064cca  mov     rdx, r12; Instance
0x140064ccd  mov     [rsp+160h+CreateDisposition], 1; CreateDisposition
0x140064cd5  mov     [rsp+160h+ShareAccess], 7; ShareAccess
0x140064cdd  mov     [rsp+160h+FileAttributes], r15d; FileAttributes
0x140064ce2  mov     [rbp+60h+var_78.ObjectName], rax
0x140064ce6  lea     rax, [rbp+60h+var_48]
0x140064cea  mov     [rsp+160h+AllocationSize], r15; AllocationSize
0x140064cef  mov     [rsp+160h+IoStatusBlock], rax; IoStatusBlock
0x140064cf4  lea     rax, [rbp+60h+var_78]
0x140064cf8  mov     [rsp+160h+ObjectAttributes], rax; ObjectAttributes
0x140064cfd  mov     [rsp+160h+DesiredAccess], 100180h; DesiredAccess
0x140064d05  mov     [rbp+60h+var_78.Length], 30h ; '0'
0x140064d0c  mov     [rbp+60h+var_78.RootDirectory], r15
0x140064d10  mov     [rbp+60h+var_78.Attributes], 240h
0x140064d17  movdqu  xmmword ptr [rbp+60h+var_78.SecurityDescriptor], xmm0
0x140064d1c  call    cs:__imp_FltCreateFileEx
0x140064d23  nop     dword ptr [rax+rax+00h]
0x140064d28  mov     ecx, eax
0x140064d2a  mov     edi, eax
0x140064d2c  call    HsmDbgBreakOnStatus
0x140064d31  test    edi, edi
0x140064d33  jns     short loc_140064D6B
0x140064d35  mov     rcx, cs:WPP_GLOBAL_Control
0x140064d3c  lea     rax, WPP_GLOBAL_Control
0x140064d43  cmp     rcx, rax
0x140064d46  jz      loc_140064FA0
0x140064d4c  mov     eax, [rcx+2Ch]
0x140064d4f  test    al, 1
0x140064d51  jz      loc_140064FA0
0x140064d57  cmp     [rcx+29h], sil
0x140064d5b  jb      loc_140064FA0
  ... truncated ...
```
