# HsmiCreateEnsureDirectoryFullyPopulated

- ea: `0x14006474c`
- end: `0x140064ef7`
- name: `HsmiCreateEnsureDirectoryFullyPopulated`
- size: `1963`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140063dd8`

## callees

- `0x140001d00`
- `0x140003c50`
- `0x140006da0`
- `0x140007ddc`
- `0x1400090b4`
- `0x140009300`
- `0x14000abb8`
- `0x14000c8c0`
- `0x14001e280`
- `0x14004c5e0`
- `0x1400516f0`
- `0x14005aaf0`
- `0x14006474c`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140064e89`
- `ntoskrnl!ObfDereferenceObject` at `0x140064e89`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064ecd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064ecd`
- `ntoskrnl!ExAllocatePool2` at `0x140064861`
- `ntoskrnl!ExAllocatePool2` at `0x1400649ba`
- `ntoskrnl!ExAllocatePool2` at `0x140064861`
- `ntoskrnl!ExAllocatePool2` at `0x1400649ba`
- `FLTMGR!FltCreateFileEx` at `0x140064bfc`
- `FLTMGR!FltCreateFileEx` at `0x140064bfc`
- `FLTMGR!FltClose` at `0x140064e9e`
- `FLTMGR!FltClose` at `0x140064e9e`
- `FLTMGR!FltGetRequestorProcess` at `0x1400647bf`
- `FLTMGR!FltGetRequestorProcess` at `0x1400647bf`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x14006491d`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x14006491d`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140064eb3`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140064eb3`
- `FLTMGR!FltReleaseContext` at `0x140064e29`
- `FLTMGR!FltReleaseContext` at `0x140064e29`

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
  signed int FileNameInformationUnsafe; // edi
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
    HsmDbgBreakOnStatus((unsigned int)FileNameInformationUnsafe);
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
    HsmDbgBreakOnStatus((unsigned int)FileNameInformationUnsafe);
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
    HsmDbgBreakOnStatus((unsigned int)FileNameInformationUnsafe);
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
    HsmDbgBreakOnStatus((unsigned int)FileNameInformationUnsafe);
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
    HsmDbgBreakOnStatus((unsigned int)FileNameInformationUnsafe);
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
      WPP_SF_qqd(v26->AttachedDevice, v27, WPP_666dd97b4df534fdc194a0db3f3e286d_Traceguids, TargetInstance, a1);
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
    HsmDbgBreakOnStatus((unsigned int)FileNameInformationUnsafe);
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
      HsmDbgBreakOnStatus((unsigned int)FileNameInformationUnsafe);
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
    WPP_SF_qqd(v37->AttachedDevice, v38, WPP_666dd97b4df534fdc194a0db3f3e286d_Traceguids, TargetInstance, a1);
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
  HsmDbgBreakOnStatus((unsigned int)FileNameInformationUnsafe);
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
0x14006474c  mov     rax, rsp
0x14006474f  mov     [rax+8], rbx
0x140064753  mov     [rax+20h], r9w
0x140064758  mov     [rax+18h], r8b
0x14006475c  mov     [rax+10h], rdx
0x140064760  push    rbp
0x140064761  push    rsi
0x140064762  push    rdi
0x140064763  push    r12
0x140064765  push    r13
0x140064767  push    r14
0x140064769  push    r15
0x14006476b  lea     rbp, [rax-68h]
0x14006476f  sub     rsp, 130h
0x140064776  mov     rax, [rdx+10h]
0x14006477a  xorps   xmm0, xmm0
0x14006477d  xor     ebx, ebx
0x14006477f  xorps   xmm1, xmm1
0x140064782  mov     r14, rcx
0x140064785  mov     [rbp+60h+var_D0], ebx
0x140064788  mov     rcx, rdx; CallbackData
0x14006478b  mov     r12, [rax+10h]
0x14006478f  mov     r15, [rax+8]
0x140064793  mov     [rbp+60h+FileNameInformation], rbx
0x140064797  movups  [rbp+60h+var_90], xmm1
0x14006479b  mov     [rbp+60h+FileHandle], rbx
0x14006479f  movups  [rbp+60h+var_C0], xmm0
0x1400647a3  mov     [rbp+60h+FileObject], rbx
0x1400647a7  movups  [rbp+60h+var_A8], xmm1
0x1400647ab  movups  xmmword ptr [rbp+60h+var_78.Length], xmm0
0x1400647af  movups  xmmword ptr [rbp+60h+var_78.ObjectName], xmm0
0x1400647b3  movups  xmmword ptr [rbp+60h+var_78.SecurityDescriptor], xmm0
0x1400647b7  movups  xmmword ptr [rbp+60h+var_48], xmm0
0x1400647bb  movups  xmmword ptr [rbp+60h+pusResult], xmm0
0x1400647bf  call    cs:__imp_FltGetRequestorProcess
0x1400647c6  nop     dword ptr [rax+rax+00h]
0x1400647cb  mov     rcx, rax
0x1400647ce  call    HsmOsIsSyncProviderProcess
0x1400647d3  test    al, al
0x1400647d5  mov     rax, [rbp+60h+arg_20]
0x1400647dc  jz      short loc_1400647E8
0x1400647de  mov     edi, ebx
0x1400647e0  mov     byte ptr [rax], 1
0x1400647e3  jmp     loc_140064E80
0x1400647e8  mov     rcx, [r15+40h]; FileObject
0x1400647ec  mov     [rax], bl
0x1400647ee  test    rcx, rcx
0x1400647f1  jnz     loc_140064911
0x1400647f7  movzx   ecx, word ptr [r14+40h]; usAugend
0x1400647fc  lea     r8, [rbp+60h+pusResult+2]; pusResult
0x140064800  movzx   edx, word ptr [r15+58h]; usAddend
0x140064805  mov     [rbp+60h+pusResult+2], cx
0x140064809  call    RtlUShortAdd
0x14006480e  mov     edi, eax
0x140064810  test    eax, eax
0x140064812  jns     short loc_14006484E
0x140064814  mov     rcx, cs:WPP_GLOBAL_Control
0x14006481b  lea     rax, WPP_GLOBAL_Control
0x140064822  cmp     rcx, rax
0x140064825  jz      loc_140064E80
0x14006482b  mov     edx, [rcx+2Ch]
0x14006482e  test    dl, 1
0x140064831  jz      loc_140064E80
0x140064837  mov     esi, 2
0x14006483c  cmp     [rcx+29h], sil
0x140064840  jb      loc_140064E80
0x140064846  lea     edx, [rsi+0Ah]
0x140064849  jmp     loc_140064E5F
0x14006484e  movzx   edx, [rbp+60h+pusResult+2]
0x140064852  mov     ecx, 100h
0x140064857  mov     r8d, 73557348h
0x14006485d  mov     [rbp+60h+pusResult], bx
0x140064861  call    cs:__imp_ExAllocatePool2
0x140064868  nop     dword ptr [rax+rax+00h]
0x14006486d  mov     rcx, rax
0x140064870  mov     qword ptr [rbp+60h+pusResult+8], rax
0x140064874  neg     rcx
0x140064877  mov     r13, rax
0x14006487a  sbb     edi, edi
0x14006487c  not     edi
0x14006487e  and     edi, 0C000009Ah
0x140064884  mov     ecx, edi
0x140064886  call    HsmDbgBreakOnStatus
0x14006488b  test    r13, r13
0x14006488e  jnz     short loc_1400648C8
0x140064890  mov     rcx, cs:WPP_GLOBAL_Control
0x140064897  lea     rax, WPP_GLOBAL_Control
0x14006489e  cmp     rcx, rax
0x1400648a1  jz      loc_140064E80
0x1400648a7  mov     eax, [rcx+2Ch]
0x1400648aa  test    al, 1
0x1400648ac  jz      loc_140064E80
0x1400648b2  lea     esi, [r13+2]
0x1400648b6  cmp     [rcx+29h], sil
0x1400648ba  jb      loc_140064E80
0x1400648c0  lea     edx, [rsi+0Bh]
0x1400648c3  jmp     loc_140064E5F
0x1400648c8  movzx   r8d, word ptr [r14+40h]; Size
0x1400648cd  mov     rcx, r13; void *
0x1400648d0  mov     rdx, [r14+48h]; Src
0x1400648d4  call    memmove
0x1400648d9  movzx   eax, word ptr [r14+40h]
0x1400648de  mov     esi, 2
0x1400648e3  movzx   r8d, word ptr [r15+58h]; Size
0x1400648e8  sub     ax, si
0x1400648eb  mov     rdx, [r15+60h]; Src
0x1400648ef  movzx   ebx, ax
0x1400648f2  lea     rcx, [rbx+r13]; void *
0x1400648f6  call    memmove
0x1400648fb  add     bx, [r15+58h]
0x140064900  movzx   r9d, bx
0x140064904  mov     [rbp+60h+pusResult], r9w
0x140064909  mov     ecx, r9d
0x14006490c  jmp     loc_140064A7A
0x140064911  lea     r9, [rbp+60h+FileNameInformation]; FileNameInformation
0x140064915  xor     edx, edx; Instance
0x140064917  mov     r8d, 101h; NameOptions
0x14006491d  call    cs:__imp_FltGetFileNameInformationUnsafe
0x140064924  nop     dword ptr [rax+rax+00h]
0x140064929  mov     ecx, eax
0x14006492b  mov     edi, eax
0x14006492d  call    HsmDbgBreakOnStatus
0x140064932  test    edi, edi
0x140064934  jns     short loc_14006496F
0x140064936  mov     rcx, cs:WPP_GLOBAL_Control
0x14006493d  lea     rax, WPP_GLOBAL_Control
0x140064944  cmp     rcx, rax
0x140064947  jz      loc_140064E80
0x14006494d  mov     eax, [rcx+2Ch]
0x140064950  test    al, 1
0x140064952  jz      loc_140064E80
0x140064958  mov     esi, 2
0x14006495d  cmp     [rcx+29h], sil
0x140064961  jb      loc_140064E80
0x140064967  lea     edx, [rsi+0Ch]
0x14006496a  jmp     loc_140064E5F
0x14006496f  mov     rdx, [rbp+60h+FileNameInformation]
0x140064973  lea     r8, [rbp+60h+pusResult+2]; pusResult
0x140064977  movzx   ecx, word ptr [r15+58h]; usAugend
0x14006497c  movzx   edx, word ptr [rdx+8]; usAddend
0x140064980  call    RtlUShortAdd
0x140064985  test    eax, eax
0x140064987  js      loc_140064E37
0x14006498d  movzx   ecx, [rbp+60h+pusResult+2]; usAugend
0x140064991  lea     r8, [rbp+60h+pusResult+2]; pusResult
0x140064995  mov     edx, 4; usAddend
0x14006499a  call    RtlUShortAdd
0x14006499f  test    eax, eax
0x1400649a1  js      loc_140064E37
0x1400649a7  movzx   edx, [rbp+60h+pusResult+2]
0x1400649ab  mov     ecx, 100h
0x1400649b0  mov     r8d, 73557348h
0x1400649b6  mov     [rbp+60h+pusResult], bx
0x1400649ba  call    cs:__imp_ExAllocatePool2
0x1400649c1  nop     dword ptr [rax+rax+00h]
0x1400649c6  mov     rcx, rax
0x1400649c9  mov     qword ptr [rbp+60h+pusResult+8], rax
0x1400649cd  neg     rcx
0x1400649d0  mov     r13, rax
0x1400649d3  sbb     edi, edi
0x1400649d5  not     edi
0x1400649d7  and     edi, 0C000009Ah
0x1400649dd  mov     ecx, edi
0x1400649df  call    HsmDbgBreakOnStatus
0x1400649e4  test    r13, r13
0x1400649e7  jnz     short loc_140064A21
0x1400649e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400649f0  lea     rax, WPP_GLOBAL_Control
0x1400649f7  cmp     rcx, rax
0x1400649fa  jz      loc_140064E80
0x140064a00  mov     eax, [rcx+2Ch]
0x140064a03  test    al, 1
0x140064a05  jz      loc_140064E80
0x140064a0b  lea     esi, [r13+2]
0x140064a0f  cmp     [rcx+29h], sil
0x140064a13  jb      loc_140064E80
0x140064a19  lea     edx, [rsi+0Eh]
0x140064a1c  jmp     loc_140064E5F
0x140064a21  mov     rdx, [rbp+60h+FileNameInformation]
0x140064a25  mov     rcx, r13; void *
0x140064a28  movzx   r8d, word ptr [rdx+8]; Size
0x140064a2d  mov     rdx, [rdx+10h]; Src
0x140064a31  call    memmove
0x140064a36  mov     rax, [rbp+60h+FileNameInformation]
0x140064a3a  mov     esi, 2
0x140064a3f  movzx   ecx, word ptr [rax+8]
0x140064a43  mov     eax, ecx
0x140064a45  add     cx, si
0x140064a48  shr     rax, 1
0x140064a4b  movzx   ebx, cx
0x140064a4e  mov     word ptr [r13+rax*2+0], 5Ch ; '\'
0x140064a56  movzx   r8d, word ptr [r15+58h]; Size
0x140064a5b  lea     rcx, [rbx+r13]; void *
0x140064a5f  mov     rdx, [r15+60h]; Src
0x140064a63  call    memmove
0x140064a68  add     bx, [r15+58h]
0x140064a6d  movzx   edx, bx
0x140064a70  mov     [rbp+60h+pusResult], dx
0x140064a74  mov     ecx, edx
0x140064a76  movzx   r9d, dx
0x140064a7a  sub     r9w, [rbp+60h+arg_18]
0x140064a82  xor     ebx, ebx
0x140064a84  movaps  xmm0, xmmword ptr [rbp+60h+pusResult]
0x140064a88  shr     rcx, 1
0x140064a8b  mov     [r13+rcx*2+0], bx
0x140064a91  movzx   edx, word ptr [r14+40h]
0x140064a96  movdqa  [rbp+60h+var_90], xmm0
0x140064a9b  movzx   r8d, word ptr [rbp+60h+var_90+2]
0x140064aa0  sub     r8w, [rbp+60h+arg_18]
0x140064aa8  mov     word ptr [rbp+60h+var_90+2], r8w
0x140064aad  sub     r8w, dx
0x140064ab1  mov     word ptr [rbp+60h+var_90], r9w
0x140064ab6  add     r8w, si
0x140064aba  movaps  xmm0, [rbp+60h+var_90]
0x140064abe  sub     r9w, dx
0x140064ac2  movdqa  [rbp+60h+var_C0], xmm0
0x140064ac7  add     r9w, si
0x140064acb  psrldq  xmm0, 8
0x140064ad0  movq    rcx, xmm0
0x140064ad5  mov     word ptr [rbp+60h+var_C0+2], r8w
0x140064ada  add     rcx, 0FFFFFFFFFFFFFFFEh
0x140064ade  mov     word ptr [rbp+60h+var_C0], r9w
0x140064ae3  add     rcx, rdx
0x140064ae6  lea     r8, [rbp+60h+var_D0]
0x140064aea  mov     qword ptr [rbp+60h+var_C0+8], rcx
0x140064aee  lea     rdx, [rbp+60h+var_C0]
0x140064af2  mov     rcx, r14
0x140064af5  call    HsmpCldGetSyncPolicyByPath
0x140064afa  mov     ecx, eax
0x140064afc  mov     edi, eax
0x140064afe  call    HsmDbgBreakOnStatus
0x140064b03  test    edi, edi
0x140064b05  jns     short loc_140064B57
0x140064b07  mov     rcx, cs:WPP_GLOBAL_Control
0x140064b0e  lea     rax, WPP_GLOBAL_Control
0x140064b15  cmp     rcx, rax
0x140064b18  jz      loc_140064E80
0x140064b1e  mov     eax, [rcx+2Ch]
0x140064b21  test    al, 1
0x140064b23  jz      loc_140064E80
0x140064b29  cmp     [rcx+29h], sil
0x140064b2d  jb      loc_140064E80
0x140064b33  lea     edx, [rbx+11h]
0x140064b36  mov     rcx, [rcx+18h]
0x140064b3a  lea     r8, WPP_666dd97b4df534fdc194a0db3f3e286d_Traceguids
0x140064b41  mov     dword ptr [rsp+160h+ObjectAttributes], edi
0x140064b45  mov     r9, r12
0x140064b48  mov     qword ptr [rsp+160h+DesiredAccess], r14
0x140064b4d  call    WPP_SF_qqd
0x140064b52  jmp     loc_140064E80
0x140064b57  mov     ebx, [rbp+60h+var_D0]
0x140064b5a  xor     r15d, r15d
0x140064b5d  cmp     [rbp+60h+arg_10], r15b
0x140064b64  jz      short loc_140064B7A
0x140064b66  mov     eax, ebx
0x140064b68  and     al, 0F0h
0x140064b6a  cmp     al, 10h
0x140064b6c  jnz     short loc_140064B7A
0x140064b6e  mov     rax, [rbp+60h+arg_28]
0x140064b75  jmp     loc_1400647E0
0x140064b7a  mov     rcx, cs:Filter; Filter
0x140064b81  lea     rax, [rbp+60h+var_90]
0x140064b85  mov     dword ptr [rsp+70h], 800h; Flags
0x140064b8d  lea     r9, [rbp+60h+FileObject]; FileObject
0x140064b91  mov     [rsp+160h+EaLength], r15d; EaLength
0x140064b96  lea     r8, [rbp+60h+FileHandle]; FileHandle
0x140064b9a  mov     [rsp+160h+EaBuffer], r15; EaBuffer
0x140064b9f  xorps   xmm0, xmm0
0x140064ba2  mov     [rsp+160h+CreateOptions], 200020h; CreateOptions
0x140064baa  mov     rdx, r12; Instance
0x140064bad  mov     [rsp+160h+CreateDisposition], 1; CreateDisposition
0x140064bb5  mov     [rsp+160h+ShareAccess], 7; ShareAccess
0x140064bbd  mov     [rsp+160h+FileAttributes], r15d; FileAttributes
0x140064bc2  mov     [rbp+60h+var_78.ObjectName], rax
0x140064bc6  lea     rax, [rbp+60h+var_48]
0x140064bca  mov     [rsp+160h+AllocationSize], r15; AllocationSize
0x140064bcf  mov     [rsp+160h+IoStatusBlock], rax; IoStatusBlock
0x140064bd4  lea     rax, [rbp+60h+var_78]
0x140064bd8  mov     [rsp+160h+ObjectAttributes], rax; ObjectAttributes
0x140064bdd  mov     [rsp+160h+DesiredAccess], 100180h; DesiredAccess
0x140064be5  mov     [rbp+60h+var_78.Length], 30h ; '0'
0x140064bec  mov     [rbp+60h+var_78.RootDirectory], r15
0x140064bf0  mov     [rbp+60h+var_78.Attributes], 240h
0x140064bf7  movdqu  xmmword ptr [rbp+60h+var_78.SecurityDescriptor], xmm0
0x140064bfc  call    cs:__imp_FltCreateFileEx
0x140064c03  nop     dword ptr [rax+rax+00h]
0x140064c08  mov     ecx, eax
0x140064c0a  mov     edi, eax
0x140064c0c  call    HsmDbgBreakOnStatus
0x140064c11  test    edi, edi
0x140064c13  jns     short loc_140064C4B
0x140064c15  mov     rcx, cs:WPP_GLOBAL_Control
0x140064c1c  lea     rax, WPP_GLOBAL_Control
0x140064c23  cmp     rcx, rax
0x140064c26  jz      loc_140064E80
0x140064c2c  mov     eax, [rcx+2Ch]
0x140064c2f  test    al, 1
0x140064c31  jz      loc_140064E80
0x140064c37  cmp     [rcx+29h], sil
0x140064c3b  jb      loc_140064E80
  ... truncated ...
```
