# PrjfPostCleanup

- ea: `0x140009d20`
- end: `0x14000a272`
- name: `PrjfPostCleanup`
- size: `1362`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x1400047cc`
- `0x140006570`
- `0x140009d20`
- `0x14000b1d0`
- `0x14000ba20`
- `0x14000d128`
- `0x14000ef78`
- `0x1400422ec`
- `0x140043844`
- `0x140043d88`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000a1e7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a1e7`
- `ntoskrnl!IoFileObjectType` at `0x140009da0`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140009dc8`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140009dc8`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140009d79`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140009d79`
- `ntoskrnl!KeWaitForSingleObject` at `0x140009fa4`
- `ntoskrnl!KeWaitForSingleObject` at `0x140009fa4`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14000a23c`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14000a23c`
- `ntoskrnl!ObfDereferenceObject` at `0x14000a1b8`
- `ntoskrnl!ObfDereferenceObject` at `0x14000a1fc`
- `ntoskrnl!ObfDereferenceObject` at `0x14000a1b8`
- `ntoskrnl!ObfDereferenceObject` at `0x14000a1fc`
- `FLTMGR!FltSetInformationFile` at `0x140009e6e`
- `FLTMGR!FltSetInformationFile` at `0x140009e6e`
- `FLTMGR!FltClose` at `0x14000a1cd`
- `FLTMGR!FltClose` at `0x14000a1cd`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14000a211`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14000a211`
- `FLTMGR!FltReleaseContext` at `0x14000a226`
- `FLTMGR!FltReleaseContext` at `0x14000a226`

## pseudocode

```c
__int64 __fastcall PrjfPostCleanup(__int64 a1, __int64 a2, void *a3, __int64 a4)
{
  bool v4; // sf
  NTSTATUS v8; // eax
  int v9; // edx
  int v10; // r8d
  struct _FLT_INSTANCE *v11; // rcx
  NTSTATUS v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  char v17; // cl
  int v18; // eax
  int v19; // edx
  int v20; // r8d
  int Tombstone; // eax
  __int64 v22; // rdx
  int v23; // eax
  int v24; // edx
  int v25; // r8d
  unsigned int v26; // edi
  char v27; // cl
  int v28; // edi
  __int64 v29; // rax
  char v30; // al
  struct _FLT_INSTANCE *v31; // rdx
  struct _FILE_OBJECT *v32; // r8
  struct _FLT_CALLBACK_DATA *v33; // rcx
  int v34; // eax
  int v35; // edx
  int v36; // r8d
  void *v37; // rcx
  void *v38; // rcx
  void *v39; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v40; // rcx
  void *v41; // rcx
  char HandleInformation; // [rsp+28h] [rbp-51h]
  __int64 FileInformation; // [rsp+60h] [rbp-19h] BYREF
  PVOID Object; // [rsp+68h] [rbp-11h] BYREF
  __int128 v46; // [rsp+70h] [rbp-9h] BYREF
  __int128 v47; // [rsp+80h] [rbp+7h] BYREF
  __int64 v48; // [rsp+90h] [rbp+17h]

  v4 = *((char *)a3 + 64) < 0;
  HIDWORD(FileInformation) = a4;
  *(_QWORD *)&v46 = a1;
  Object = 0;
  LOBYTE(FileInformation) = 0;
  if ( v4 )
    ExReleaseRundownProtection((PEX_RUNDOWN_REF)(*((_QWORD *)a3 + 6) + 336LL));
  if ( (*((_BYTE *)a3 + 64) & 2) != 0 )
  {
    if ( !*((_QWORD *)a3 + 4) )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, 1, a3, a4);
    v8 = ObReferenceObjectByHandle(*((HANDLE *)a3 + 4), 0x10000u, (POBJECT_TYPE)IoFileObjectType, 0, &Object, 0);
    if ( v8 < 0 )
    {
      if ( (xmmword_14001A3D0 & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v9) = xmmword_14001A3D0 & 0x40;
        LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDL(
          518,
          v9,
          v10,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          6,
          50,
          (__int64)&WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\prjflt.c",
          217,
          v8);
      }
      goto LABEL_52;
    }
    v11 = *(struct _FLT_INSTANCE **)(a2 + 24);
    LOBYTE(FileInformation) = 0;
    v12 = FltSetInformationFile(v11, (PFILE_OBJECT)Object, &FileInformation, 1u, FileDispositionInformation);
    if ( v12 < 0 )
    {
      if ( (xmmword_14001A3D0 & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v13) = xmmword_14001A3D0 & 0x40;
        LOBYTE(v15) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDL(
          518,
          v13,
          v15,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          6,
          51,
          (__int64)&WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\prjflt.c",
          234,
          v12);
      }
      goto LABEL_52;
    }
    if ( (*(_BYTE *)(a1 + 32) & 0xC) != 0 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v14, v13, v15, v16);
  }
  v17 = *((_BYTE *)a3 + 64);
  if ( (v17 & 0x40) != 0 )
  {
    if ( (*(_BYTE *)(a1 + 32) & 0xC) != 0 )
    {
      KeWaitForSingleObject((PVOID)(*((_QWORD *)a3 + 6) + 288LL), Executive, 0, 0, 0);
      if ( !*(_BYTE *)(*((_QWORD *)a3 + 6) + 282LL) )
      {
        Tombstone = PrjfCreateTombstone(
                      *(PFLT_INSTANCE *)(a2 + 24),
                      (struct _UNICODE_STRING *)(*((_QWORD *)a3 + 7) + 8LL),
                      *((_BYTE *)a3 + 64) & 1);
        if ( Tombstone < 0 )
          PrjfTelemetryTombstoneFailureOperation(1, 5, (unsigned int)Tombstone);
      }
    }
    else if ( (v17 & 1) != 0 )
    {
      v18 = PrjfRevertInMemoryTombstonesForDirectory(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32));
      if ( v18 < 0
        && ((BYTE1(xmmword_14001A3D0) & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED) )
      {
        LOBYTE(v19) = BYTE1(xmmword_14001A3D0) & 0x20;
        LOBYTE(v20) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDL(
          525,
          v19,
          v20,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          13,
          52,
          (__int64)&WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\prjflt.c",
          60,
          v18);
      }
    }
    v22 = *((_QWORD *)a3 + 7);
    if ( v22 )
    {
      v23 = PrjfRemoveInMemoryTombstone(*(PFLT_INSTANCE *)(a2 + 24), v22, *((struct _FILE_OBJECT **)a3 + 5));
      v26 = v23;
      if ( v23 < 0 )
      {
        if ( (xmmword_14001A3D0 & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v24) = xmmword_14001A3D0 & 0x40;
          LOBYTE(v25) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_sDL(
            518,
            v24,
            v25,
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            2,
            6,
            53,
            (__int64)&WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids,
            (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\prjflt.c",
            77,
            v23);
        }
        PrjfTelemetryTombstoneFailureOperation(2, 5, v26);
      }
    }
  }
  v27 = *((_BYTE *)a3 + 64);
  if ( (v27 & 0x1C) != 0 && (FileInformation & 0x100000000LL) == 0 )
  {
    v48 = 0;
    v28 = 1024;
    v47 = 0;
    if ( (v27 & 0x30) != 0x30 )
      v28 = 0;
    v29 = *(_QWORD *)(v46 + 32) & 0xCLL;
    if ( (v27 & 8) != 0 )
    {
      if ( v29 )
      {
        v30 = v47;
        v28 = 2048;
        if ( (v27 & 0x30) == 0x30 )
          v30 = 1;
        LOBYTE(v47) = v30;
LABEL_48:
        v31 = *(struct _FLT_INSTANCE **)(a2 + 24);
        v32 = *(struct _FILE_OBJECT **)(a2 + 32);
        HandleInformation = v27 & 1;
        v33 = (struct _FLT_CALLBACK_DATA *)v46;
        v46 = *(_OWORD *)a3;
        v34 = PrjfSendNotifyOperationCommand(
                v33,
                v31,
                v32,
                &v46,
                (__int64)a3 + 16,
                HandleInformation,
                v28,
                0,
                (__int64)&v47,
                0,
                0);
        if ( v34 < 0
          && ((BYTE1(xmmword_14001A3D0) & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED) )
        {
          LOBYTE(v35) = BYTE1(xmmword_14001A3D0) & 0x20;
          LOBYTE(v36) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_sDDd(
            525,
            v35,
            v36,
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            2,
            13,
            54,
            (__int64)&WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids,
            (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\prjflt.c",
            173,
            v28,
            v34,
            FileInformation);
        }
        goto LABEL_52;
      }
    }
    else if ( v29 )
    {
      goto LABEL_47;
    }
    if ( (v27 & 0x20) == 0 )
    {
      if ( !v28 )
      {
        if ( (v27 & 4) == 0 )
          goto LABEL_52;
        v28 = 512;
      }
      goto LABEL_48;
    }
LABEL_47:
    if ( !v28 )
      goto LABEL_52;
    goto LABEL_48;
  }
LABEL_52:
  if ( Object )
    ObfDereferenceObject(Object);
  v37 = (void *)*((_QWORD *)a3 + 4);
  if ( v37 )
    FltClose(v37);
  v38 = (void *)*((_QWORD *)a3 + 3);
  if ( v38 )
    ExFreePoolWithTag(v38, 0x6E664A50u);
  v39 = (void *)*((_QWORD *)a3 + 5);
  if ( v39 )
    ObfDereferenceObject(v39);
  v40 = (struct _FLT_FILE_NAME_INFORMATION *)*((_QWORD *)a3 + 7);
  if ( v40 )
    FltReleaseFileNameInformation(v40);
  v41 = (void *)*((_QWORD *)a3 + 6);
  if ( v41 )
    FltReleaseContext(v41);
  ExFreeToPagedLookasideList(&stru_14001A840, a3);
  return 0;
}

```

## disassembly

```asm
0x140009d20  mov     [rsp-8+arg_18], rbx
0x140009d25  push    rbp
0x140009d26  push    rsi
0x140009d27  push    rdi
0x140009d28  push    r12
0x140009d2a  push    r13
0x140009d2c  push    r14
0x140009d2e  push    r15
0x140009d30  lea     rbp, [rsp-27h]
0x140009d35  sub     rsp, 0A0h
0x140009d3c  mov     rax, cs:__security_cookie
0x140009d43  xor     rax, rsp
0x140009d46  mov     [rbp+57h+var_38], rax
0x140009d4a  cmp     byte ptr [r8+40h], 0
0x140009d4f  mov     rbx, r8
0x140009d52  mov     [rbp+57h+var_6C], r9d
0x140009d56  mov     r13, rdx
0x140009d59  mov     rdi, rcx
0x140009d5c  mov     qword ptr [rbp+57h+var_60], rcx
0x140009d60  mov     [rbp+57h+var_68], 0
0x140009d68  mov     [rbp+57h+FileInformation], 0
0x140009d6c  jge     short loc_140009D85
0x140009d6e  mov     rcx, [r8+30h]
0x140009d72  add     rcx, 150h; RunRef
0x140009d79  call    cs:__imp_ExReleaseRundownProtection
0x140009d80  nop     dword ptr [rax+rax+00h]
0x140009d85  test    byte ptr [rbx+40h], 2
0x140009d89  mov     edx, 1
0x140009d8e  jz      loc_140009EE4
0x140009d94  cmp     qword ptr [rbx+20h], 0
0x140009d99  jnz     short loc_140009DA0
0x140009d9b  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140009da0  mov     r8, cs:__imp_IoFileObjectType
0x140009da7  lea     rax, [rbp+57h+var_68]
0x140009dab  mov     rcx, [rbx+20h]; Handle
0x140009daf  xor     r9d, r9d; AccessMode
0x140009db2  mov     [rsp+0D0h+HandleInformation], 0; HandleInformation
0x140009dbb  mov     edx, 10000h; DesiredAccess
0x140009dc0  mov     [rsp+0D0h+Object], rax; Object
0x140009dc5  mov     r8, [r8]; ObjectType
0x140009dc8  call    cs:__imp_ObReferenceObjectByHandle
0x140009dcf  nop     dword ptr [rax+rax+00h]
0x140009dd4  test    eax, eax
0x140009dd6  jns     short loc_140009E50
0x140009dd8  mov     dl, byte ptr cs:xmmword_14001A3D0
0x140009dde  lea     rsi, WPP_RECORDER_INITIALIZED
0x140009de5  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140009dec  setnz   r8b
0x140009df0  and     dl, 40h
0x140009df3  jnz     short loc_140009DFE
0x140009df5  test    r8b, r8b
0x140009df8  jz      loc_14000A1AF
0x140009dfe  mov     dword ptr [rsp+0D0h+var_80], eax
0x140009e02  lea     r14, aOnecoreBaseFsG_0; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140009e09  mov     [rsp+0D0h+var_88], 8D9h
0x140009e11  lea     r15, WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids
0x140009e18  mov     [rsp+0D0h+var_90], r14
0x140009e1d  mov     [rsp+0D0h+var_98], r15
0x140009e22  mov     word ptr [rsp+0D0h+var_A0], 32h ; '2'
0x140009e29  mov     r9, cs:WPP_GLOBAL_Control
0x140009e30  mov     ecx, 206h
0x140009e35  mov     dword ptr [rsp+0D0h+HandleInformation], 6
0x140009e3d  mov     byte ptr [rsp+0D0h+Object], 2
0x140009e42  mov     r9, [r9+40h]
0x140009e46  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140009e4b  jmp     loc_14000A1AF
0x140009e50  mov     rdx, [rbp+57h+var_68]; FileObject
0x140009e54  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x140009e58  mov     rcx, [r13+18h]; Instance
0x140009e5c  mov     r9d, 1; Length
0x140009e62  mov     [rbp+57h+FileInformation], 0
0x140009e66  mov     dword ptr [rsp+0D0h+Object], 0Dh; FileInformationClass
0x140009e6e  call    cs:__imp_FltSetInformationFile
0x140009e75  nop     dword ptr [rax+rax+00h]
0x140009e7a  test    eax, eax
0x140009e7c  jns     short loc_140009ED4
0x140009e7e  mov     dl, byte ptr cs:xmmword_14001A3D0
0x140009e84  lea     rsi, WPP_RECORDER_INITIALIZED
0x140009e8b  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140009e92  setnz   r8b
0x140009e96  and     dl, 40h
0x140009e99  jnz     short loc_140009EA4
0x140009e9b  test    r8b, r8b
0x140009e9e  jz      loc_14000A1AF
0x140009ea4  mov     dword ptr [rsp+0D0h+var_80], eax
0x140009ea8  lea     r14, aOnecoreBaseFsG_0; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140009eaf  mov     [rsp+0D0h+var_88], 8EAh
0x140009eb7  lea     r15, WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids
0x140009ebe  mov     [rsp+0D0h+var_90], r14
0x140009ec3  mov     [rsp+0D0h+var_98], r15
0x140009ec8  mov     word ptr [rsp+0D0h+var_A0], 33h ; '3'
0x140009ecf  jmp     loc_140009E29
0x140009ed4  test    byte ptr [rdi+20h], 0Ch
0x140009ed8  jz      short loc_140009EDF
0x140009eda  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140009edf  mov     edx, 1
0x140009ee4  mov     cl, [rbx+40h]
0x140009ee7  lea     rsi, WPP_RECORDER_INITIALIZED
0x140009eee  lea     r14, aOnecoreBaseFsG_0; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140009ef5  lea     r15, WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids
0x140009efc  test    cl, 40h
0x140009eff  jz      loc_14000A071
0x140009f05  test    byte ptr [rdi+20h], 0Ch
0x140009f09  jnz     short loc_140009F88
0x140009f0b  test    dl, cl
0x140009f0d  jz      loc_140009FEB
0x140009f13  mov     rdx, [r13+20h]; FileObject
0x140009f17  mov     rcx, [r13+18h]; Instance
0x140009f1b  call    PrjfRevertInMemoryTombstonesForDirectory
0x140009f20  test    eax, eax
0x140009f22  jns     loc_140009FEB
0x140009f28  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140009f2f  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140009f35  setnz   r8b
0x140009f39  and     dl, 20h
0x140009f3c  jnz     short loc_140009F47
0x140009f3e  test    r8b, r8b
0x140009f41  jz      loc_140009FEB
0x140009f47  mov     r9, cs:WPP_GLOBAL_Control
0x140009f4e  mov     ecx, 20Dh
0x140009f53  mov     dword ptr [rsp+0D0h+var_80], eax
0x140009f57  mov     [rsp+0D0h+var_88], 93Ch
0x140009f5f  mov     [rsp+0D0h+var_90], r14
0x140009f64  mov     r9, [r9+40h]
0x140009f68  mov     [rsp+0D0h+var_98], r15
0x140009f6d  mov     word ptr [rsp+0D0h+var_A0], 34h ; '4'
0x140009f74  mov     dword ptr [rsp+0D0h+HandleInformation], 0Dh
0x140009f7c  mov     byte ptr [rsp+0D0h+Object], 2
0x140009f81  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140009f86  jmp     short loc_140009FEB
0x140009f88  mov     rcx, [rbx+30h]
0x140009f8c  xor     r9d, r9d; Alertable
0x140009f8f  add     rcx, 120h; Object
0x140009f96  mov     [rsp+0D0h+Object], 0; Timeout
0x140009f9f  xor     r8d, r8d; WaitMode
0x140009fa2  xor     edx, edx; WaitReason
0x140009fa4  call    cs:__imp_KeWaitForSingleObject
0x140009fab  nop     dword ptr [rax+rax+00h]
0x140009fb0  mov     rax, [rbx+30h]
0x140009fb4  mov     cl, [rax+11Ah]
0x140009fba  test    cl, cl
0x140009fbc  jnz     short loc_140009FEB
0x140009fbe  mov     r8b, [rbx+40h]
0x140009fc2  mov     rdx, [rbx+38h]
0x140009fc6  and     r8b, 1
0x140009fca  mov     rcx, [r13+18h]; Instance
0x140009fce  add     rdx, 8
0x140009fd2  call    PrjfCreateTombstone
0x140009fd7  test    eax, eax
0x140009fd9  jns     short loc_140009FEB
0x140009fdb  mov     edx, 5
0x140009fe0  mov     r8d, eax
0x140009fe3  lea     ecx, [rdx-4]
0x140009fe6  call    PrjfTelemetryTombstoneFailureOperation
0x140009feb  mov     rdx, [rbx+38h]
0x140009fef  test    rdx, rdx
0x140009ff2  jz      short loc_14000A071
0x140009ff4  mov     r8, [rbx+28h]
0x140009ff8  mov     rcx, [r13+18h]; Instance
0x140009ffc  call    PrjfRemoveInMemoryTombstone
0x14000a001  mov     edi, eax
0x14000a003  test    eax, eax
0x14000a005  jns     short loc_14000A071
0x14000a007  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14000a00e  mov     dl, byte ptr cs:xmmword_14001A3D0
0x14000a014  setnz   r8b
0x14000a018  and     dl, 40h
0x14000a01b  jnz     short loc_14000A022
0x14000a01d  test    r8b, r8b
0x14000a020  jz      short loc_14000A061
0x14000a022  mov     r9, cs:WPP_GLOBAL_Control
0x14000a029  mov     ecx, 206h
0x14000a02e  mov     dword ptr [rsp+0D0h+var_80], edi
0x14000a032  mov     [rsp+0D0h+var_88], 94Dh
0x14000a03a  mov     [rsp+0D0h+var_90], r14
0x14000a03f  mov     r9, [r9+40h]
0x14000a043  mov     [rsp+0D0h+var_98], r15
0x14000a048  mov     word ptr [rsp+0D0h+var_A0], 35h ; '5'
0x14000a04f  mov     dword ptr [rsp+0D0h+HandleInformation], 6
0x14000a057  mov     byte ptr [rsp+0D0h+Object], 2
0x14000a05c  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x14000a061  mov     edx, 5
0x14000a066  mov     r8d, edi
0x14000a069  lea     ecx, [rdx-3]
0x14000a06c  call    PrjfTelemetryTombstoneFailureOperation
0x14000a071  mov     cl, [rbx+40h]
0x14000a074  test    cl, 1Ch
0x14000a077  jz      loc_14000A1AF
0x14000a07d  mov     r8d, 1
0x14000a083  test    byte ptr [rbp+57h+var_6C], r8b
0x14000a087  jnz     loc_14000A1AF
0x14000a08d  mov     r10, qword ptr [rbp+57h+var_60]
0x14000a091  xor     eax, eax
0x14000a093  mov     r9b, 30h ; '0'
0x14000a096  mov     [rbp+57h+var_40], rax
0x14000a09a  mov     dl, cl
0x14000a09c  mov     edi, 400h
0x14000a0a1  and     dl, r9b
0x14000a0a4  xorps   xmm0, xmm0
0x14000a0a7  cmp     dl, r9b
0x14000a0aa  movups  [rbp+57h+var_50], xmm0
0x14000a0ae  cmovnz  edi, eax
0x14000a0b1  mov     rax, [r10+20h]
0x14000a0b5  and     eax, 0Ch
0x14000a0b8  test    cl, 8
0x14000a0bb  jz      short loc_14000A0D7
0x14000a0bd  test    rax, rax
0x14000a0c0  jz      short loc_14000A0DC
0x14000a0c2  movzx   eax, byte ptr [rbp+57h+var_50]
0x14000a0c6  cmp     dl, r9b
0x14000a0c9  mov     edi, 800h
0x14000a0ce  cmovz   eax, r8d
0x14000a0d2  mov     byte ptr [rbp+57h+var_50], al
0x14000a0d5  jmp     short loc_14000A0FD
0x14000a0d7  test    rax, rax
0x14000a0da  jnz     short loc_14000A0F5
0x14000a0dc  test    cl, 20h
0x14000a0df  jnz     short loc_14000A0F5
0x14000a0e1  test    edi, edi
0x14000a0e3  jnz     short loc_14000A0FD
0x14000a0e5  test    cl, 4
0x14000a0e8  jz      loc_14000A1AF
0x14000a0ee  mov     edi, 200h
0x14000a0f3  jmp     short loc_14000A0FD
0x14000a0f5  test    edi, edi
0x14000a0f7  jz      loc_14000A1AF
0x14000a0fd  movups  xmm0, xmmword ptr [rbx]
0x14000a100  mov     [rsp+0D0h+var_80], 0
0x14000a109  lea     rdx, [rbp+57h+var_50]
0x14000a10d  mov     byte ptr [rsp+0D0h+var_88], 0
0x14000a112  lea     rax, [rbx+10h]
0x14000a116  mov     [rsp+0D0h+var_90], rdx
0x14000a11b  lea     r9, [rbp+57h+var_60]
0x14000a11f  mov     rdx, [r13+18h]
0x14000a123  and     cl, r8b
0x14000a126  mov     r8, [r13+20h]
0x14000a12a  mov     [rsp+0D0h+var_98], 0
0x14000a133  mov     [rsp+0D0h+var_A0], edi
0x14000a137  mov     byte ptr [rsp+0D0h+HandleInformation], cl
0x14000a13b  mov     rcx, r10
0x14000a13e  movdqu  [rbp+57h+var_60], xmm0
0x14000a143  mov     [rsp+0D0h+Object], rax
0x14000a148  call    PrjfSendNotifyOperationCommand
0x14000a14d  test    eax, eax
0x14000a14f  jns     short loc_14000A1AF
0x14000a151  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14000a158  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14000a15e  setnz   r8b
0x14000a162  and     dl, 20h
0x14000a165  jnz     short loc_14000A16C
0x14000a167  test    r8b, r8b
0x14000a16a  jz      short loc_14000A1AF
0x14000a16c  mov     r9, cs:WPP_GLOBAL_Control
0x14000a173  mov     ecx, 20Dh
0x14000a178  mov     [rsp+0D0h+var_78], eax
0x14000a17c  mov     dword ptr [rsp+0D0h+var_80], edi
0x14000a180  mov     [rsp+0D0h+var_88], 9ADh
0x14000a188  mov     r9, [r9+40h]
0x14000a18c  mov     [rsp+0D0h+var_90], r14
0x14000a191  mov     [rsp+0D0h+var_98], r15
0x14000a196  mov     word ptr [rsp+0D0h+var_A0], 36h ; '6'
0x14000a19d  mov     dword ptr [rsp+0D0h+HandleInformation], 0Dh
0x14000a1a5  mov     byte ptr [rsp+0D0h+Object], 2
0x14000a1aa  call    WPP_RECORDER_AND_TRACE_SF_sDDd
0x14000a1af  mov     rcx, [rbp+57h+var_68]; Object
0x14000a1b3  test    rcx, rcx
0x14000a1b6  jz      short loc_14000A1C4
0x14000a1b8  call    cs:__imp_ObfDereferenceObject
0x14000a1bf  nop     dword ptr [rax+rax+00h]
0x14000a1c4  mov     rcx, [rbx+20h]; FileHandle
0x14000a1c8  test    rcx, rcx
0x14000a1cb  jz      short loc_14000A1D9
0x14000a1cd  call    cs:__imp_FltClose
0x14000a1d4  nop     dword ptr [rax+rax+00h]
0x14000a1d9  mov     rcx, [rbx+18h]; P
0x14000a1dd  test    rcx, rcx
0x14000a1e0  jz      short loc_14000A1F3
0x14000a1e2  mov     edx, 6E664A50h; Tag
0x14000a1e7  call    cs:__imp_ExFreePoolWithTag
0x14000a1ee  nop     dword ptr [rax+rax+00h]
0x14000a1f3  mov     rcx, [rbx+28h]; Object
0x14000a1f7  test    rcx, rcx
0x14000a1fa  jz      short loc_14000A208
0x14000a1fc  call    cs:__imp_ObfDereferenceObject
0x14000a203  nop     dword ptr [rax+rax+00h]
0x14000a208  mov     rcx, [rbx+38h]; FileNameInformation
0x14000a20c  test    rcx, rcx
0x14000a20f  jz      short loc_14000A21D
0x14000a211  call    cs:__imp_FltReleaseFileNameInformation
0x14000a218  nop     dword ptr [rax+rax+00h]
0x14000a21d  mov     rcx, [rbx+30h]; Context
0x14000a221  test    rcx, rcx
0x14000a224  jz      short loc_14000A232
0x14000a226  call    cs:__imp_FltReleaseContext
0x14000a22d  nop     dword ptr [rax+rax+00h]
0x14000a232  mov     rdx, rbx; Entry
0x14000a235  lea     rcx, stru_14001A840; Lookaside
0x14000a23c  call    cs:__imp_ExFreeToPagedLookasideList
0x14000a243  nop     dword ptr [rax+rax+00h]
0x14000a248  xor     eax, eax
  ... truncated ...
```
