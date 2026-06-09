# PrjfCreateSymbolicLink

- ea: `0x140038f1c`
- end: `0x14003959b`
- name: `PrjfCreateSymbolicLink`
- size: `1663`
- prototype: `__int64 __fastcall(struct _FLT_INSTANCE *, __int64, struct _UNICODE_STRING *, __int64, const void **, const void **, char)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400395a4`

## callees

- `0x14000b1d0`
- `0x14000ba20`
- `0x14000bb80`
- `0x14000be80`
- `0x14000d128`
- `0x14000d754`
- `0x140038f1c`
- `0x14003ac68`
- `0x14003e548`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400394e4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400394e4`
- `ntoskrnl!ObfDereferenceObject` at `0x1400394cb`
- `ntoskrnl!ObfDereferenceObject` at `0x1400394cb`
- `ntoskrnl!ExAllocatePool2` at `0x1400391c5`
- `ntoskrnl!ExAllocatePool2` at `0x1400391c5`
- `FLTMGR!FltIsEcpAcknowledged` at `0x140039498`
- `FLTMGR!FltIsEcpAcknowledged` at `0x140039498`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x140039500`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x140039500`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x1400390cf`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x1400390cf`
- `FLTMGR!FltAllocateExtraCreateParameterFromLookasideList` at `0x140039043`
- `FLTMGR!FltAllocateExtraCreateParameterFromLookasideList` at `0x140039043`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x140038f87`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x140038f87`
- `FLTMGR!FltCreateFileEx2` at `0x14003945b`
- `FLTMGR!FltCreateFileEx2` at `0x14003945b`
- `FLTMGR!FltClose` at `0x1400394b6`
- `FLTMGR!FltClose` at `0x1400394b6`

## pseudocode

```c
__int64 __fastcall PrjfCreateSymbolicLink(
        struct _FLT_INSTANCE *a1,
        __int64 a2,
        struct _UNICODE_STRING *a3,
        __int64 a4,
        const void **a5,
        const void **a6,
        char a7)
{
  _WORD *v7; // r12
  NTSTATUS v9; // eax
  int v10; // edx
  int v11; // r8d
  NTSTATUS v12; // ebx
  NTSTATUS v13; // eax
  int v14; // edx
  int v15; // r8d
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  unsigned __int16 v19; // ax
  unsigned __int16 v20; // di
  __int64 Pool2; // rax
  int v22; // edx
  int v23; // r8d
  __int64 v24; // rbx
  char v25; // r13
  __int64 v26; // rcx
  bool v27; // cf
  ULONG CreateOptions; // ebx
  int v29; // eax
  int v30; // edx
  int v31; // r8d
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 v34; // rdx
  __int64 v35; // rcx
  __int64 v36; // r8
  ULONG FileAttributes; // [rsp+40h] [rbp-C0h]
  PVOID EcpContext; // [rsp+80h] [rbp-80h] BYREF
  PECP_LIST EcpList; // [rsp+88h] [rbp-78h] BYREF
  __int64 v41; // [rsp+90h] [rbp-70h]
  struct _UNICODE_STRING *v42; // [rsp+98h] [rbp-68h]
  void *FileHandle; // [rsp+A0h] [rbp-60h] BYREF
  PFILE_OBJECT FileObject; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v45; // [rsp+B0h] [rbp-50h]
  PFLT_INSTANCE Instance; // [rsp+B8h] [rbp-48h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+C0h] [rbp-40h] BYREF
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v49; // [rsp+110h] [rbp+10h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+118h] [rbp+18h] BYREF
  _QWORD v51[4]; // [rsp+128h] [rbp+28h] BYREF

  v7 = 0;
  v42 = a3;
  v41 = a2;
  Instance = a1;
  EcpList = 0;
  EcpContext = 0;
  FileHandle = 0;
  FileObject = 0;
  v45 = a4;
  v9 = FltAllocateExtraCreateParameterList(Globals, 0, &EcpList);
  v12 = v9;
  if ( v9 < 0 )
  {
    if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = xmmword_14001A3D0 & 0x20;
      LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDL(
        517,
        v10,
        v11,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        5,
        214,
        (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
        115,
        v9);
    }
    goto LABEL_35;
  }
  v13 = FltAllocateExtraCreateParameterFromLookasideList(
          Globals,
          &GUID_ECP_ATOMIC_CREATE,
          0x58u,
          0,
          0,
          qword_14001A5C0,
          &EcpContext);
  v12 = v13;
  if ( v13 < 0 )
  {
    if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v14) = xmmword_14001A3D0 & 0x20;
      LOBYTE(v15) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDL(
        517,
        v14,
        v15,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        5,
        215,
        (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
        129,
        v13);
    }
    goto LABEL_35;
  }
  memset(EcpContext, 0, 0x58u);
  *(_WORD *)EcpContext = 88;
  if ( FltInsertExtraCreateParameter(Globals, EcpList, EcpContext) < 0 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v17, v16, v18);
  v19 = *(_WORD *)a5 + 20;
  if ( v19 < 0x14u )
  {
    v12 = -1073741675;
    if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v16) = xmmword_14001A3D0 & 0x20;
      LOBYTE(v18) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDL(
        517,
        v16,
        v18,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        5,
        216,
        (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
        157,
        149);
    }
    goto LABEL_35;
  }
  v20 = *(_WORD *)a6 + v19;
  if ( v20 < v19 )
  {
    v12 = -1073741675;
    if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v16) = xmmword_14001A3D0 & 0x20;
      LOBYTE(v18) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDL(
        517,
        v16,
        v18,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        5,
        217,
        (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
        165,
        149);
    }
    goto LABEL_35;
  }
  Pool2 = ExAllocatePool2(256, v20, 1919109712);
  v7 = (_WORD *)Pool2;
  if ( !Pool2 )
  {
    v12 = -1073741670;
    if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v22) = xmmword_14001A3D0 & 0x20;
      LOBYTE(v23) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDL(
        517,
        v22,
        v23,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        5,
        218,
        (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
        176,
        154);
    }
    goto LABEL_35;
  }
  *(_DWORD *)Pool2 = -1610612724;
  v24 = Pool2 + 20;
  *(_WORD *)(Pool2 + 4) = v20 - 8;
  v25 = 1;
  *(_DWORD *)(Pool2 + 16) |= a7 & 1;
  *(_WORD *)(Pool2 + 12) = 0;
  *(_WORD *)(Pool2 + 14) = *(_WORD *)a6;
  memmove((void *)(Pool2 + 20), a6[1], *(unsigned __int16 *)a6);
  v26 = (unsigned __int16)v7[7];
  v7[4] = v26;
  v7[5] = *(_WORD *)a5;
  memmove((void *)(v24 + v26), a5[1], *(unsigned __int16 *)a5);
  *((_QWORD *)EcpContext + 1) = v7;
  *((_WORD *)EcpContext + 3) = v20;
  *((_WORD *)EcpContext + 1) |= 2u;
  v51[3] = *(_QWORD *)(a4 + 40);
  v51[0] = *(_QWORD *)(a4 + 16);
  v51[1] = *(_QWORD *)(a4 + 24);
  v51[2] = *(_QWORD *)(a4 + 32);
  *((_QWORD *)EcpContext + 4) = v51;
  *((_WORD *)EcpContext + 1) |= 0x600u;
  *((_DWORD *)EcpContext + 10) = *(_DWORD *)(a4 + 48);
  *((_WORD *)EcpContext + 1) |= 0x20u;
  DriverContext.Size = 40;
  DriverContext.ExtraCreateParameter = EcpList;
  ObjectAttributes.ObjectName = v42;
  v27 = *(_BYTE *)a4 != 0;
  *(_DWORD *)(&DriverContext.Size + 1) = 0;
  *(&DriverContext.Size + 3) = 0;
  ObjectAttributes.RootDirectory = 0;
  CreateOptions = v27 + 2097192;
  v49 = 1;
  *(_OWORD *)&DriverContext.DeviceObjectHint = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v29 = PrjfImpersonateAndAddSymlinkPrivilege(v41);
  if ( v29 < 0 )
  {
    v25 = 0;
    if ( (BYTE8(xmmword_14001A3D0) & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v30) = BYTE8(xmmword_14001A3D0) & 0x20;
      LOBYTE(v31) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDL(
        773,
        v30,
        v31,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        3,
        5,
        219,
        (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
        27,
        v29);
    }
  }
  FileAttributes = *(_DWORD *)(v45 + 48);
  IoStatusBlock = 0;
  v12 = FltCreateFileEx2(
          Globals,
          Instance,
          &FileHandle,
          &FileObject,
          0x100u,
          &ObjectAttributes,
          &IoStatusBlock,
          0,
          FileAttributes,
          7u,
          2u,
          CreateOptions,
          0,
          0,
          1u,
          &DriverContext);
  if ( v25 )
    PrjfStopImpersonating(v41, v32, v33);
  if ( v12 >= 0 )
    goto LABEL_33;
  if ( v12 == -1073741771 )
  {
    v12 = 0;
LABEL_33:
    if ( !FltIsEcpAcknowledged(Globals, EcpContext) )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v35, v34, v36);
    goto LABEL_35;
  }
  if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v32) = xmmword_14001A3D0 & 0x20;
    LOBYTE(v33) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sDdZ(
      517,
      v32,
      v33,
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      2,
      5,
      220,
      (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
      (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
      71,
      v12,
      (__int64)v42);
  }
LABEL_35:
  if ( FileHandle )
    FltClose(FileHandle);
  if ( FileObject )
    ObfDereferenceObject(FileObject);
  if ( v7 )
    ExFreePoolWithTag(v7, 0x72634A50u);
  if ( EcpList )
    FltFreeExtraCreateParameterList(Globals, EcpList);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140038f1c  push    rbp
0x140038f1e  push    rbx
0x140038f1f  push    rsi
0x140038f20  push    rdi
0x140038f21  push    r12
0x140038f23  push    r13
0x140038f25  push    r14
0x140038f27  push    r15
0x140038f29  lea     rbp, [rsp-58h]
0x140038f2e  sub     rsp, 158h
0x140038f35  mov     rax, cs:__security_cookie
0x140038f3c  xor     rax, rsp
0x140038f3f  mov     [rbp+90h+var_48], rax
0x140038f43  mov     r14, [rbp+90h+arg_28]
0x140038f4a  xor     r13d, r13d
0x140038f4d  mov     rsi, [rbp+90h+arg_20]
0x140038f54  mov     r12d, r13d
0x140038f57  mov     [rbp+90h+var_F8], r8
0x140038f5b  mov     r15, r9
0x140038f5e  mov     [rbp+90h+var_100], rdx
0x140038f62  lea     r8, [rbp+90h+EcpList]; EcpList
0x140038f66  mov     [rbp+90h+Instance], rcx
0x140038f6a  xor     edx, edx; Flags
0x140038f6c  mov     rcx, cs:Globals; Filter
0x140038f73  mov     [rbp+90h+EcpList], r13
0x140038f77  mov     [rbp+90h+var_110], r13
0x140038f7b  mov     [rbp+90h+FileHandle], r13
0x140038f7f  mov     [rbp+90h+FileObject], r13
0x140038f83  mov     [rbp+90h+var_E0], r9
0x140038f87  call    cs:__imp_FltAllocateExtraCreateParameterList
0x140038f8e  nop     dword ptr [rax+rax+00h]
0x140038f93  mov     ebx, eax
0x140038f95  test    eax, eax
0x140038f97  jns     short loc_140039011
0x140038f99  mov     dl, byte ptr cs:xmmword_14001A3D0
0x140038f9f  lea     rdi, WPP_RECORDER_INITIALIZED
0x140038fa6  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140038fad  setnz   r8b
0x140038fb1  and     dl, 20h
0x140038fb4  jnz     short loc_140038FBF
0x140038fb6  test    r8b, r8b
0x140038fb9  jz      loc_1400394AD
0x140038fbf  mov     [rsp+190h+CreateDisposition], eax
0x140038fc3  lea     r14, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140038fca  mov     [rsp+190h+ShareAccess], 2373h
0x140038fd2  lea     r15, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x140038fd9  mov     qword ptr [rsp+190h+FileAttributes], r14
0x140038fde  mov     [rsp+190h+AllocationSize], r15
0x140038fe3  mov     word ptr [rsp+190h+EcpContext], 0D6h
0x140038fea  mov     r9, cs:WPP_GLOBAL_Control
0x140038ff1  mov     ecx, 205h
0x140038ff6  mov     dword ptr [rsp+190h+LookasideList], 5
0x140038ffe  mov     byte ptr [rsp+190h+CleanupCallback], 2
0x140039003  mov     r9, [r9+40h]
0x140039007  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x14003900c  jmp     loc_1400394AD
0x140039011  mov     rcx, cs:Globals; Filter
0x140039018  lea     rax, [rbp+90h+var_110]
0x14003901c  mov     [rsp+190h+EcpContext], rax; EcpContext
0x140039021  lea     rdx, GUID_ECP_ATOMIC_CREATE; EcpType
0x140039028  xor     r9d, r9d; Flags
0x14003902b  lea     rax, qword_14001A5C0
0x140039032  mov     [rsp+190h+LookasideList], rax; LookasideList
0x140039037  mov     [rsp+190h+CleanupCallback], r13; CleanupCallback
0x14003903c  lea     edi, [r9+58h]
0x140039040  mov     r8d, edi; SizeOfContext
0x140039043  call    cs:__imp_FltAllocateExtraCreateParameterFromLookasideList
0x14003904a  nop     dword ptr [rax+rax+00h]
0x14003904f  mov     ebx, eax
0x140039051  test    eax, eax
0x140039053  jns     short loc_1400390AB
0x140039055  mov     dl, byte ptr cs:xmmword_14001A3D0
0x14003905b  lea     rdi, WPP_RECORDER_INITIALIZED
0x140039062  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140039069  setnz   r8b
0x14003906d  and     dl, 20h
0x140039070  jnz     short loc_14003907B
0x140039072  test    r8b, r8b
0x140039075  jz      loc_1400394AD
0x14003907b  mov     [rsp+190h+CreateDisposition], eax
0x14003907f  lea     r14, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140039086  mov     [rsp+190h+ShareAccess], 2381h
0x14003908e  lea     r15, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x140039095  mov     qword ptr [rsp+190h+FileAttributes], r14
0x14003909a  mov     [rsp+190h+AllocationSize], r15
0x14003909f  mov     word ptr [rsp+190h+EcpContext], 0D7h
0x1400390a6  jmp     loc_140038FEA
0x1400390ab  mov     rcx, [rbp+90h+var_110]; void *
0x1400390af  mov     r8, rdi; Size
0x1400390b2  xor     edx, edx; Val
0x1400390b4  call    memset
0x1400390b9  mov     rax, [rbp+90h+var_110]
0x1400390bd  mov     [rax], di
0x1400390c0  mov     r8, [rbp+90h+var_110]; EcpContext
0x1400390c4  mov     rdx, [rbp+90h+EcpList]; EcpList
0x1400390c8  mov     rcx, cs:Globals; Filter
0x1400390cf  call    cs:__imp_FltInsertExtraCreateParameter
0x1400390d6  nop     dword ptr [rax+rax+00h]
0x1400390db  test    eax, eax
0x1400390dd  jns     short loc_1400390E4
0x1400390df  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400390e4  movzx   eax, word ptr [rsi]
0x1400390e7  add     ax, 14h
0x1400390eb  cmp     ax, 14h
0x1400390ef  jnb     short loc_14003914E
0x1400390f1  mov     eax, 0C0000095h
0x1400390f6  mov     ebx, eax
0x1400390f8  mov     dl, byte ptr cs:xmmword_14001A3D0
0x1400390fe  lea     rdi, WPP_RECORDER_INITIALIZED
0x140039105  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14003910c  setnz   r8b
0x140039110  and     dl, 20h
0x140039113  jnz     short loc_14003911E
0x140039115  test    r8b, r8b
0x140039118  jz      loc_1400394AD
0x14003911e  mov     [rsp+190h+CreateDisposition], eax
0x140039122  lea     r14, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140039129  mov     [rsp+190h+ShareAccess], 239Dh
0x140039131  lea     r15, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x140039138  mov     qword ptr [rsp+190h+FileAttributes], r14
0x14003913d  mov     [rsp+190h+AllocationSize], r15
0x140039142  mov     word ptr [rsp+190h+EcpContext], 0D8h
0x140039149  jmp     loc_140038FEA
0x14003914e  movzx   edi, ax
0x140039151  add     di, [r14]
0x140039155  cmp     di, ax
0x140039158  jnb     short loc_1400391B7
0x14003915a  mov     eax, 0C0000095h
0x14003915f  mov     ebx, eax
0x140039161  mov     dl, byte ptr cs:xmmword_14001A3D0
0x140039167  lea     rdi, WPP_RECORDER_INITIALIZED
0x14003916e  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140039175  setnz   r8b
0x140039179  and     dl, 20h
0x14003917c  jnz     short loc_140039187
0x14003917e  test    r8b, r8b
0x140039181  jz      loc_1400394AD
0x140039187  mov     [rsp+190h+CreateDisposition], eax
0x14003918b  lea     r14, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140039192  mov     [rsp+190h+ShareAccess], 23A5h
0x14003919a  lea     r15, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x1400391a1  mov     qword ptr [rsp+190h+FileAttributes], r14
0x1400391a6  mov     [rsp+190h+AllocationSize], r15
0x1400391ab  mov     word ptr [rsp+190h+EcpContext], 0D9h
0x1400391b2  jmp     loc_140038FEA
0x1400391b7  movzx   edx, di
0x1400391ba  mov     ecx, 100h
0x1400391bf  mov     r8d, 72634A50h
0x1400391c5  call    cs:__imp_ExAllocatePool2
0x1400391cc  nop     dword ptr [rax+rax+00h]
0x1400391d1  mov     r12, rax
0x1400391d4  test    rax, rax
0x1400391d7  jnz     short loc_140039234
0x1400391d9  mov     ebx, 0C000009Ah
0x1400391de  mov     dl, byte ptr cs:xmmword_14001A3D0
0x1400391e4  lea     rdi, WPP_RECORDER_INITIALIZED
0x1400391eb  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400391f2  setnz   r8b
0x1400391f6  and     dl, 20h
0x1400391f9  jnz     short loc_140039204
0x1400391fb  test    r8b, r8b
0x1400391fe  jz      loc_1400394AD
0x140039204  mov     [rsp+190h+CreateDisposition], ebx
0x140039208  lea     r14, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14003920f  mov     [rsp+190h+ShareAccess], 23B0h
0x140039217  lea     r15, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x14003921e  mov     qword ptr [rsp+190h+FileAttributes], r14
0x140039223  mov     [rsp+190h+AllocationSize], r15
0x140039228  mov     word ptr [rsp+190h+EcpContext], 0DAh
0x14003922f  jmp     loc_140038FEA
0x140039234  mov     dword ptr [rax], 0A000000Ch
0x14003923a  lea     rbx, [r12+14h]
0x14003923f  lea     eax, [rdi-8]
0x140039242  mov     rcx, rbx; void *
0x140039245  mov     [r12+4], ax
0x14003924b  mov     r13b, 1
0x14003924e  mov     eax, [rbp+90h+arg_30]
0x140039254  and     eax, 1
0x140039257  or      [r12+10h], eax
0x14003925c  xor     eax, eax
0x14003925e  mov     [r12+0Ch], ax
0x140039264  movzx   eax, word ptr [r14]
0x140039268  mov     [r12+0Eh], ax
0x14003926e  movzx   r8d, word ptr [r14]; Size
0x140039272  mov     rdx, [r14+8]; Src
0x140039276  call    memmove
0x14003927b  movzx   ecx, word ptr [r12+0Eh]
0x140039281  mov     [r12+8], cx
0x140039287  add     rcx, rbx; void *
0x14003928a  movzx   eax, word ptr [rsi]
0x14003928d  mov     [r12+0Ah], ax
0x140039293  movzx   r8d, word ptr [rsi]; Size
0x140039297  mov     rdx, [rsi+8]; Src
0x14003929b  call    memmove
0x1400392a0  mov     rax, [rbp+90h+var_110]
0x1400392a4  lea     rcx, [rbp+90h+var_68]
0x1400392a8  mov     esi, 2
0x1400392ad  xorps   xmm0, xmm0
0x1400392b0  mov     [rax+8], r12
0x1400392b4  mov     rax, [rbp+90h+var_110]
0x1400392b8  mov     [rax+6], di
0x1400392bc  mov     rax, [rbp+90h+var_110]
0x1400392c0  or      [rax+2], si
0x1400392c4  mov     rax, [r15+28h]
0x1400392c8  mov     [rbp+90h+var_50], rax
0x1400392cc  mov     rax, [r15+10h]
0x1400392d0  mov     [rbp+90h+var_68], rax
0x1400392d4  mov     rax, [r15+18h]
0x1400392d8  mov     [rbp+90h+var_60], rax
0x1400392dc  mov     rax, [r15+20h]
0x1400392e0  mov     [rbp+90h+var_58], rax
0x1400392e4  mov     rax, [rbp+90h+var_110]
0x1400392e8  mov     [rax+20h], rcx
0x1400392ec  mov     ecx, 600h
0x1400392f1  mov     rax, [rbp+90h+var_110]
0x1400392f5  or      [rax+2], cx
0x1400392f9  mov     rax, [rbp+90h+var_110]
0x1400392fd  mov     ecx, [r15+30h]
0x140039301  mov     [rax+28h], ecx
0x140039304  xor     ecx, ecx
0x140039306  mov     rax, [rbp+90h+var_110]
0x14003930a  or      word ptr [rax+2], 20h
0x14003930f  lea     eax, [rsi+26h]
0x140039312  mov     [rbp+90h+var_A0.Size], ax
0x140039316  mov     rax, [rbp+90h+EcpList]
0x14003931a  mov     [rbp+90h+var_A0.ExtraCreateParameter], rax
0x14003931e  mov     rax, [rbp+90h+var_F8]
0x140039322  mov     [rbp+90h+ObjectAttributes.ObjectName], rax
0x140039326  mov     al, [r15]
0x140039329  neg     al
0x14003932b  mov     dword ptr [rbp+90h+var_A0+2], ecx
0x14003932e  mov     word ptr [rbp+90h+var_A0+6], cx
0x140039332  sbb     ebx, ebx
0x140039334  mov     [rbp+90h+ObjectAttributes.RootDirectory], rcx
0x140039338  mov     rcx, [rbp+90h+var_100]
0x14003933c  neg     ebx
0x14003933e  add     ebx, 200028h
0x140039344  mov     [rbp+90h+var_80], 1
0x14003934c  movdqu  xmmword ptr [rbp+90h+var_A0.DeviceObjectHint], xmm0
0x140039351  mov     qword ptr [rbp+90h+ObjectAttributes.Length], 30h ; '0'
0x140039359  mov     qword ptr [rbp+90h+ObjectAttributes.Attributes], 240h
0x140039361  movdqu  xmmword ptr [rbp+90h+ObjectAttributes.SecurityDescriptor], xmm0
0x140039366  call    PrjfImpersonateAndAddSymlinkPrivilege
0x14003936b  lea     r14, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140039372  lea     r15, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x140039379  lea     rdi, WPP_RECORDER_INITIALIZED
0x140039380  test    eax, eax
0x140039382  jns     short loc_1400393E1
0x140039384  xor     r13b, r13b
0x140039387  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14003938e  mov     dl, byte ptr cs:xmmword_14001A3D0+8
0x140039394  setnz   r8b
0x140039398  and     dl, 20h
0x14003939b  jnz     short loc_1400393A2
0x14003939d  test    r8b, r8b
0x1400393a0  jz      short loc_1400393E1
0x1400393a2  mov     r9, cs:WPP_GLOBAL_Control
0x1400393a9  mov     ecx, 305h
0x1400393ae  mov     [rsp+190h+CreateDisposition], eax
0x1400393b2  mov     [rsp+190h+ShareAccess], 241Bh
0x1400393ba  mov     qword ptr [rsp+190h+FileAttributes], r14
0x1400393bf  mov     r9, [r9+40h]
0x1400393c3  mov     [rsp+190h+AllocationSize], r15
0x1400393c8  mov     word ptr [rsp+190h+EcpContext], 0DBh
0x1400393cf  mov     dword ptr [rsp+190h+LookasideList], 5
0x1400393d7  mov     byte ptr [rsp+190h+CleanupCallback], 3
0x1400393dc  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x1400393e1  mov     rdx, [rbp+90h+Instance]; Instance
0x1400393e5  lea     rax, [rbp+90h+var_A0]
0x1400393e9  mov     rcx, cs:Globals; Filter
0x1400393f0  lea     r9, [rbp+90h+FileObject]; FileObject
0x1400393f4  mov     [rsp+190h+DriverContext], rax; DriverContext
0x1400393f9  lea     r8, [rbp+90h+FileHandle]; FileHandle
0x1400393fd  mov     rax, [rbp+90h+var_E0]
0x140039401  xorps   xmm0, xmm0
0x140039404  mov     [rsp+190h+Flags], 1; Flags
0x14003940c  mov     [rsp+190h+EaLength], 0; EaLength
0x140039414  mov     [rsp+190h+EaBuffer], 0; EaBuffer
0x14003941d  mov     eax, [rax+30h]
0x140039420  mov     [rsp+190h+CreateOptions], ebx; CreateOptions
0x140039424  mov     [rsp+190h+CreateDisposition], esi; CreateDisposition
0x140039428  mov     [rsp+190h+ShareAccess], 7; ShareAccess
0x140039430  mov     [rsp+190h+FileAttributes], eax; FileAttributes
0x140039434  lea     rax, [rbp+90h+IoStatusBlock]
0x140039438  mov     [rsp+190h+AllocationSize], 0; AllocationSize
0x140039441  mov     [rsp+190h+EcpContext], rax; IoStatusBlock
0x140039446  lea     rax, [rbp+90h+ObjectAttributes]
0x14003944a  mov     [rsp+190h+LookasideList], rax; ObjectAttributes
0x14003944f  mov     dword ptr [rsp+190h+CleanupCallback], 100h; DesiredAccess
0x140039457  movups  xmmword ptr [rbp+90h+IoStatusBlock], xmm0
0x14003945b  call    cs:__imp_FltCreateFileEx2
0x140039462  nop     dword ptr [rax+rax+00h]
0x140039467  mov     ebx, eax
0x140039469  test    r13b, r13b
0x14003946c  jz      short loc_140039477
0x14003946e  mov     rcx, [rbp+90h+var_100]
0x140039472  call    PrjfStopImpersonating
0x140039477  xor     r13d, r13d
0x14003947a  test    ebx, ebx
0x14003947c  jns     short loc_14003948D
  ... truncated ...
```
