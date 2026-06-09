# HsmFltPreSetLinkInformation

- ea: `0x140055428`
- end: `0x1400559f0`
- name: `HsmFltPreSetLinkInformation`
- size: `1480`
- prototype: `__int64 __fastcall(PFLT_CONTEXT Context, _QWORD *, __int64, struct _FLT_CALLBACK_DATA *, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400526d0`

## callees

- `0x140001ab4`
- `0x140001d00`
- `0x140003c50`
- `0x140007ddc`
- `0x14000abb8`
- `0x14000d388`
- `0x140052574`
- `0x1400548d0`
- `0x1400548ec`
- `0x140054b24`
- `0x140055370`
- `0x140055428`
- `0x140057b20`
- `0x140059090`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140055606`
- `ntoskrnl!ExAllocatePool2` at `0x140055606`
- `FLTMGR!FltGetDestinationFileNameInformation` at `0x14005552f`
- `FLTMGR!FltGetDestinationFileNameInformation` at `0x14005552f`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140055669`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140055669`
- `FLTMGR!FltReleaseContext` at `0x1400559c8`
- `FLTMGR!FltReleaseContext` at `0x1400559c8`

## pseudocode

```c
__int64 __fastcall HsmFltPreSetLinkInformation(
        PFLT_CONTEXT Context,
        _QWORD *a2,
        __int64 a3,
        struct _FLT_CALLBACK_DATA *a4,
        __int64 a5,
        __int64 *a6)
{
  PFLT_CONTEXT StreamContext; // rdi
  NTSTATUS SyncPolicy; // ebx
  struct _FLT_INSTANCE *v10; // r12
  struct _FILE_OBJECT *v11; // r13
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  unsigned int v13; // r12d
  __int64 Length; // rdx
  __int16 v15; // cx
  __int64 v16; // rdx
  char v17; // dl
  void *v18; // rcx
  __int64 Pool2; // rax
  unsigned int v21; // eax
  __int64 v22; // r12
  void *v23; // rdx
  PDEVICE_OBJECT v24; // rcx
  __int64 v25; // rdx
  PDEVICE_OBJECT v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // [rsp+50h] [rbp-49h]
  PFLT_CONTEXT Contexta; // [rsp+58h] [rbp-41h]
  int v30; // [rsp+60h] [rbp-39h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+68h] [rbp-31h] BYREF
  __int64 v32; // [rsp+70h] [rbp-29h] BYREF
  __int64 v33; // [rsp+78h] [rbp-21h] BYREF
  __int128 v34; // [rsp+80h] [rbp-19h] BYREF
  PVOID EaBuffer; // [rsp+90h] [rbp-9h]
  PFLT_INSTANCE Instance; // [rsp+98h] [rbp-1h]
  __int64 v38; // [rsp+F8h] [rbp+5Fh] BYREF
  __int64 v39; // [rsp+100h] [rbp+67h]
  int v40; // [rsp+108h] [rbp+6Fh] BYREF

  v39 = a3;
  StreamContext = a2;
  SyncPolicy = 0;
  v10 = *(struct _FLT_INSTANCE **)(a5 + 24);
  v11 = *(struct _FILE_OBJECT **)(a5 + 32);
  Instance = v10;
  if ( a2 )
    v28 = *(_QWORD *)(a2[2] + 32LL);
  else
    v28 = 0;
  Iopb = a4->Iopb;
  LODWORD(v38) = 0;
  v30 = 0;
  v40 = 0;
  EaBuffer = Iopb->Parameters.Create.EaBuffer;
  FileNameInformation = 0;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  Contexta = (PFLT_CONTEXT)HsmpAcquireFileNameLock(Context);
  if ( !Contexta )
  {
    v13 = 4;
    goto LABEL_17;
  }
  LOBYTE(a5) = 0;
  if ( !StreamContext )
  {
    StreamContext = (PFLT_CONTEXT)HsmpGetStreamContext(a4, v10, v11);
    if ( !StreamContext )
    {
      v13 = 0;
      *a6 = (__int64)Contexta;
      goto LABEL_17;
    }
    v22 = HsmpAcquireFileNameLock(Context);
    if ( !v22 )
    {
      v23 = Contexta;
      v13 = 4;
      LOBYTE(a5) = 1;
LABEL_73:
      HsmpReleaseFileNameLock(v23);
      goto LABEL_15;
    }
    HsmpReleaseFileNameLock(Contexta);
    Contexta = (PFLT_CONTEXT)v22;
    LOBYTE(a5) = 1;
  }
  v13 = 1;
  SyncPolicy = HsmpCldGetSyncPolicy((_DWORD)Context, (_DWORD)StreamContext, (_DWORD)v11, 0, (__int64)&v38);
  HsmDbgBreakOnStatus(SyncPolicy);
  if ( SyncPolicy < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qiqiid(
        WPP_GLOBAL_Control->AttachedDevice,
        54,
        WPP_e26ac64b2c40307be864d687cc32cd5d_Traceguids,
        a4,
        Context,
        v11,
        v28,
        StreamContext,
        SyncPolicy);
    }
    goto LABEL_72;
  }
  if ( (v38 & 0x200000) == 0 )
  {
    SyncPolicy = -1073688807;
    HsmDbgBreakOnStatus(-1073688807);
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_72;
    }
    v25 = 55;
    goto LABEL_48;
  }
  SyncPolicy = FltGetDestinationFileNameInformation(
                 Instance,
                 v11,
                 *((HANDLE *)EaBuffer + 1),
                 (PWSTR)EaBuffer + 10,
                 *((_DWORD *)EaBuffer + 4),
                 0x101u,
                 &FileNameInformation);
  HsmDbgBreakOnStatus(SyncPolicy);
  if ( SyncPolicy < 0 )
  {
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_72;
    }
    v25 = 56;
    goto LABEL_48;
  }
  Length = FileNameInformation->Volume.Length;
  v15 = FileNameInformation->Name.Length - Length;
  *((_QWORD *)&v34 + 1) = (char *)FileNameInformation->Name.Buffer + Length;
  LOWORD(v34) = v15;
  WORD1(v34) = v15;
  SyncPolicy = HsmiCldGetSyncRootFileIdByPath(Context, &v34, &v32);
  HsmDbgBreakOnStatus(SyncPolicy);
  if ( SyncPolicy != -1073688813 )
  {
    if ( SyncPolicy >= 0 )
    {
      v38 = v32;
      goto LABEL_10;
    }
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_72;
    }
    v25 = 57;
LABEL_48:
    WPP_SF_qiqiid(
      v24->AttachedDevice,
      v25,
      WPP_e26ac64b2c40307be864d687cc32cd5d_Traceguids,
      a4,
      Context,
      v11,
      v28,
      StreamContext,
      SyncPolicy);
LABEL_72:
    v23 = Contexta;
    goto LABEL_73;
  }
  v38 = 0;
LABEL_10:
  SyncPolicy = HsmiCldGetSyncRootFileIdByFileObject(Context, v11, &v33, &v30, &v40);
  HsmDbgBreakOnStatus(SyncPolicy);
  if ( SyncPolicy < 0
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_qqqd(
      WPP_GLOBAL_Control->AttachedDevice,
      55,
      WPP_6e1e33f79617319dc28b4de987ec2fe8_Traceguids,
      Context,
      StreamContext,
      v11,
      SyncPolicy);
  }
  HsmDbgBreakOnStatus(SyncPolicy);
  if ( SyncPolicy < 0 )
  {
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_72;
    }
    v27 = 58;
    goto LABEL_71;
  }
  LOBYTE(v16) = v33 != v38;
  if ( !(unsigned __int8)HsmpIsPlaceholder(StreamContext, v16) || v40 || !v17 )
  {
    Pool2 = ExAllocatePool2(256, 16, 1665954632);
    if ( Pool2 )
    {
      v13 = 0;
      *(_QWORD *)(Pool2 + 8) = Contexta;
      *(_DWORD *)Pool2 = 1665954632;
      *a6 = Pool2;
      goto LABEL_15;
    }
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_72;
    }
    v27 = 60;
LABEL_71:
    WPP_SF_qiqiid(
      v26->AttachedDevice,
      v27,
      WPP_e26ac64b2c40307be864d687cc32cd5d_Traceguids,
      a4,
      Context,
      v11,
      v28,
      StreamContext,
      SyncPolicy);
    goto LABEL_72;
  }
  SyncPolicy = HsmpAcquireUserRequestRundownProtection(v18, a4);
  HsmDbgBreakOnStatus(SyncPolicy);
  if ( SyncPolicy < 0 )
  {
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_72;
    }
    v27 = 59;
    goto LABEL_71;
  }
  v21 = HsmpRecallInitiateHydration(v39, (_DWORD)StreamContext, (_DWORD)v11, 7, (__int64)a4, 0, -1);
  v13 = v21;
  if ( !v21 )
  {
    *a6 = (__int64)StreamContext;
    goto LABEL_15;
  }
  if ( v21 != 2 )
  {
    HsmpReleaseUserRequestRundownProtection(StreamContext);
    goto LABEL_72;
  }
LABEL_15:
  if ( (_BYTE)a5 )
    FltReleaseContext(StreamContext);
LABEL_17:
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  if ( SyncPolicy < 0 )
  {
    a4->IoStatus.Status = SyncPolicy;
    v13 = 4;
    a4->IoStatus.Information = 0;
  }
  return v13;
}

```

## disassembly

```asm
0x140055428  mov     [rsp-8+arg_10], r8
0x14005542d  mov     [rsp-8+arg_0], rcx
0x140055432  push    rbp
0x140055433  push    rbx
0x140055434  push    rsi
0x140055435  push    rdi
0x140055436  push    r12
0x140055438  push    r13
0x14005543a  push    r14
0x14005543c  push    r15
0x14005543e  lea     rbp, [rsp-0Fh]
0x140055443  sub     rsp, 0A8h
0x14005544a  mov     rax, [rbp+47h+arg_20]
0x14005544e  mov     rdi, rdx
0x140055451  xor     edx, edx
0x140055453  mov     r15, r9
0x140055456  mov     rsi, rcx
0x140055459  mov     ebx, edx
0x14005545b  mov     r12, [rax+18h]
0x14005545f  mov     r13, [rax+20h]
0x140055463  mov     [rbp+47h+Instance], r12
0x140055467  test    rdi, rdi
0x14005546a  jnz     loc_14005567F
0x140055470  mov     [rbp+47h+var_90], rdx
0x140055474  mov     rax, [r9+10h]
0x140055478  xorps   xmm0, xmm0
0x14005547b  mov     dword ptr [rbp+47h+arg_8], edx
0x14005547e  mov     r8, r15
0x140055481  mov     [rbp+47h+var_80], edx
0x140055484  mov     [rbp+47h+arg_18], edx
0x140055487  mov     rcx, [rax+38h]
0x14005548b  mov     [rbp+47h+var_50], rcx
0x14005548f  mov     rcx, rsi; Context
0x140055492  mov     [rbp+47h+FileNameInformation], rdx
0x140055496  mov     [rbp+47h+var_70], rdx
0x14005549a  mov     [rbp+47h+var_68], rdx
0x14005549e  mov     rdx, rdi
0x1400554a1  movups  [rbp+47h+var_60], xmm0
0x1400554a5  call    HsmpAcquireFileNameLock
0x1400554aa  mov     [rbp+47h+Context], rax
0x1400554ae  test    rax, rax
0x1400554b1  jz      loc_140055677
0x1400554b7  mov     byte ptr [rbp+47h+arg_20], bl
0x1400554ba  mov     r14d, 1
0x1400554c0  test    rdi, rdi
0x1400554c3  jz      loc_140055750
0x1400554c9  lea     rax, [rbp+47h+arg_8]
0x1400554cd  xor     r9d, r9d
0x1400554d0  mov     r8, r13
0x1400554d3  mov     qword ptr [rsp+0E0h+FileNameLength], rax
0x1400554d8  mov     rdx, rdi
0x1400554db  mov     rcx, rsi
0x1400554de  mov     r12d, r14d
0x1400554e1  call    HsmpCldGetSyncPolicy
0x1400554e6  mov     ecx, eax
0x1400554e8  mov     ebx, eax
0x1400554ea  call    HsmDbgBreakOnStatus
0x1400554ef  test    ebx, ebx
0x1400554f1  js      loc_1400557CB
0x1400554f7  test    dword ptr [rbp+47h+arg_8], 200000h
0x1400554fe  jz      loc_140055828
0x140055504  mov     rcx, [rbp+47h+var_50]
0x140055508  lea     rax, [rbp+47h+FileNameInformation]
0x14005550c  mov     [rsp+0E0h+RetFileNameInformation], rax; RetFileNameInformation
0x140055511  mov     rdx, r13; FileObject
0x140055514  mov     [rsp+0E0h+NameOptions], 101h; NameOptions
0x14005551c  mov     eax, [rcx+10h]
0x14005551f  lea     r9, [rcx+14h]; FileName
0x140055523  mov     r8, [rcx+8]; RootDirectory
0x140055527  mov     rcx, [rbp+47h+Instance]; Instance
0x14005552b  mov     [rsp+0E0h+FileNameLength], eax; FileNameLength
0x14005552f  call    cs:__imp_FltGetDestinationFileNameInformation
0x140055536  nop     dword ptr [rax+rax+00h]
0x14005553b  mov     ecx, eax
0x14005553d  mov     ebx, eax
0x14005553f  call    HsmDbgBreakOnStatus
0x140055544  test    ebx, ebx
0x140055546  js      loc_140055892
0x14005554c  mov     rax, [rbp+47h+FileNameInformation]
0x140055550  lea     r8, [rbp+47h+var_70]
0x140055554  movzx   edx, word ptr [rax+18h]
0x140055558  movzx   ecx, word ptr [rax+8]
0x14005555c  sub     cx, dx
0x14005555f  add     rdx, [rax+10h]
0x140055563  mov     qword ptr [rbp+47h+var_60+8], rdx
0x140055567  lea     rdx, [rbp+47h+var_60]
0x14005556b  mov     word ptr [rbp+47h+var_60], cx
0x14005556f  mov     word ptr [rbp+47h+var_60+2], cx
0x140055573  mov     rcx, rsi
0x140055576  call    HsmiCldGetSyncRootFileIdByPath
0x14005557b  mov     ecx, eax
0x14005557d  mov     ebx, eax
0x14005557f  call    HsmDbgBreakOnStatus
0x140055584  cmp     ebx, 0C000CF13h
0x14005558a  jnz     loc_140055779
0x140055590  mov     [rbp+47h+arg_8], 0
0x140055598  lea     rax, [rbp+47h+arg_18]
0x14005559c  mov     rdx, r13
0x14005559f  lea     r9, [rbp+47h+var_80]
0x1400555a3  mov     qword ptr [rsp+0E0h+FileNameLength], rax
0x1400555a8  lea     r8, [rbp+47h+var_68]
0x1400555ac  mov     rcx, rsi
0x1400555af  call    HsmiCldGetSyncRootFileIdByFileObject
0x1400555b4  mov     ecx, eax
0x1400555b6  mov     ebx, eax
0x1400555b8  call    HsmDbgBreakOnStatus
0x1400555bd  lea     rsi, WPP_GLOBAL_Control
0x1400555c4  test    ebx, ebx
0x1400555c6  js      loc_140055690
0x1400555cc  mov     ecx, ebx
0x1400555ce  call    HsmDbgBreakOnStatus
0x1400555d3  test    ebx, ebx
0x1400555d5  js      loc_1400558F8
0x1400555db  mov     rax, [rbp+47h+arg_8]
0x1400555df  mov     rcx, rdi
0x1400555e2  cmp     [rbp+47h+var_68], rax
0x1400555e6  setnz   dl
0x1400555e9  call    HsmpIsPlaceholder
0x1400555ee  test    al, al
0x1400555f0  jnz     loc_1400556E2
0x1400555f6  mov     edx, 10h
0x1400555fb  mov     ecx, 100h
0x140055600  mov     r8d, 634C7348h
0x140055606  call    cs:__imp_ExAllocatePool2
0x14005560d  nop     dword ptr [rax+rax+00h]
0x140055612  mov     rcx, rax
0x140055615  test    rax, rax
0x140055618  jz      loc_140055959
0x14005561e  mov     rdx, [rbp+47h+Context]
0x140055622  xor     r12d, r12d
0x140055625  mov     [rax+8], rdx
0x140055629  mov     dword ptr [rax], 634C7348h
0x14005562f  mov     rax, [rbp+47h+arg_28]
0x140055633  mov     [rax], rcx
0x140055636  cmp     byte ptr [rbp+47h+arg_20], 0
0x14005563a  jnz     loc_1400559C5
0x140055640  mov     rcx, [rbp+47h+FileNameInformation]; FileNameInformation
0x140055644  test    rcx, rcx
0x140055647  jnz     short loc_140055669
0x140055649  test    ebx, ebx
0x14005564b  js      loc_1400559D9
0x140055651  mov     eax, r12d
0x140055654  add     rsp, 0A8h
0x14005565b  pop     r15
0x14005565d  pop     r14
0x14005565f  pop     r13
0x140055661  pop     r12
0x140055663  pop     rdi
0x140055664  pop     rsi
0x140055665  pop     rbx
0x140055666  pop     rbp
0x140055667  retn
0x140055669  call    cs:__imp_FltReleaseFileNameInformation
0x140055670  nop     dword ptr [rax+rax+00h]
0x140055675  jmp     short loc_140055649
0x140055677  mov     r12d, 4
0x14005567d  jmp     short loc_140055640
0x14005567f  mov     rax, [rdi+10h]
0x140055683  mov     r14, [rax+20h]
0x140055687  mov     [rbp+47h+var_90], r14
0x14005568b  jmp     loc_140055474
0x140055690  mov     rcx, cs:WPP_GLOBAL_Control
0x140055697  cmp     rcx, rsi
0x14005569a  jz      loc_1400555CC
0x1400556a0  mov     eax, [rcx+2Ch]
0x1400556a3  test    r14b, al
0x1400556a6  jz      loc_1400555CC
0x1400556ac  cmp     byte ptr [rcx+29h], 3
0x1400556b0  jb      loc_1400555CC
0x1400556b6  mov     r9, [rbp+47h+arg_0]
0x1400556ba  lea     r8, WPP_6e1e33f79617319dc28b4de987ec2fe8_Traceguids
0x1400556c1  mov     rcx, [rcx+18h]
0x1400556c5  mov     edx, 37h ; '7'
0x1400556ca  mov     dword ptr [rsp+0E0h+RetFileNameInformation], ebx
0x1400556ce  mov     qword ptr [rsp+0E0h+NameOptions], r13
0x1400556d3  mov     qword ptr [rsp+0E0h+FileNameLength], rdi
0x1400556d8  call    WPP_SF_qqqd
0x1400556dd  jmp     loc_1400555CC
0x1400556e2  cmp     [rbp+47h+arg_18], 0
0x1400556e6  jnz     loc_1400555F6
0x1400556ec  test    dl, dl
0x1400556ee  jz      loc_1400555F6
0x1400556f4  mov     rdx, r15; CallbackData
0x1400556f7  call    HsmpAcquireUserRequestRundownProtection
0x1400556fc  mov     ecx, eax
0x1400556fe  mov     ebx, eax
0x140055700  call    HsmDbgBreakOnStatus
0x140055705  test    ebx, ebx
0x140055707  js      loc_140055925
0x14005570d  mov     rcx, [rbp+47h+arg_10]
0x140055711  mov     r9d, 7
0x140055717  mov     [rsp+0E0h+RetFileNameInformation], 0FFFFFFFFFFFFFFFFh
0x140055720  mov     r8, r13
0x140055723  mov     qword ptr [rsp+0E0h+NameOptions], 0
0x14005572c  mov     rdx, rdi
0x14005572f  mov     qword ptr [rsp+0E0h+FileNameLength], r15
0x140055734  call    HsmpRecallInitiateHydration
0x140055739  mov     r12d, eax
0x14005573c  test    eax, eax
0x14005573e  jnz     loc_140055946
0x140055744  mov     rcx, [rbp+47h+arg_28]
0x140055748  mov     [rcx], rdi
0x14005574b  jmp     loc_140055636
0x140055750  mov     r8, r13; FileObject
0x140055753  mov     rdx, r12; Instance
0x140055756  mov     rcx, r15; CallbackData
0x140055759  call    HsmpGetStreamContext
0x14005575e  mov     rdi, rax
0x140055761  test    rax, rax
0x140055764  jnz     short loc_14005578E
0x140055766  mov     rax, [rbp+47h+arg_28]
0x14005576a  xor     r12d, r12d
0x14005576d  mov     rdx, [rbp+47h+Context]
0x140055771  mov     [rax], rdx
0x140055774  jmp     loc_140055640
0x140055779  test    ebx, ebx
0x14005577b  js      loc_1400558C6
0x140055781  mov     rax, [rbp+47h+var_70]
0x140055785  mov     [rbp+47h+arg_8], rax
0x140055789  jmp     loc_140055598
0x14005578e  mov     r8, r15
0x140055791  mov     rdx, rax
0x140055794  mov     rcx, rsi; Context
0x140055797  call    HsmpAcquireFileNameLock
0x14005579c  mov     r12, rax
0x14005579f  test    rax, rax
0x1400557a2  jnz     short loc_1400557B5
0x1400557a4  mov     rdx, [rbp+47h+Context]
0x1400557a8  lea     r12d, [rax+4]
0x1400557ac  mov     byte ptr [rbp+47h+arg_20], r14b
0x1400557b0  jmp     loc_1400559B8
0x1400557b5  mov     rcx, [rbp+47h+Context]; Context
0x1400557b9  call    HsmpReleaseFileNameLock
0x1400557be  mov     [rbp+47h+Context], r12
0x1400557c2  mov     byte ptr [rbp+47h+arg_20], r14b
0x1400557c6  jmp     loc_1400554C9
0x1400557cb  mov     r10, cs:WPP_GLOBAL_Control
0x1400557d2  lea     rsi, WPP_GLOBAL_Control
0x1400557d9  cmp     r10, rsi
0x1400557dc  jz      loc_1400559AB
0x1400557e2  mov     ecx, [r10+2Ch]
0x1400557e6  test    r14b, cl
0x1400557e9  jz      loc_1400559AB
0x1400557ef  cmp     byte ptr [r10+29h], 2
0x1400557f4  jb      loc_1400559AB
0x1400557fa  mov     rax, [rbp+47h+var_90]
0x1400557fe  mov     edx, 36h ; '6'
0x140055803  mov     r9, [rbp+47h+arg_0]
0x140055807  mov     rcx, [r10+18h]
0x14005580b  mov     [rsp+0E0h+var_A0], ebx
0x14005580f  mov     [rsp+0E0h+var_A8], rdi
0x140055814  mov     [rsp+0E0h+RetFileNameInformation], rax
0x140055819  mov     qword ptr [rsp+0E0h+NameOptions], r13
0x14005581e  mov     qword ptr [rsp+0E0h+FileNameLength], r9
0x140055823  jmp     loc_14005599C
0x140055828  mov     ebx, 0C000CF19h
0x14005582d  mov     ecx, ebx
0x14005582f  call    HsmDbgBreakOnStatus
0x140055834  mov     rcx, cs:WPP_GLOBAL_Control
0x14005583b  lea     rsi, WPP_GLOBAL_Control
0x140055842  cmp     rcx, rsi
0x140055845  jz      loc_1400559AB
0x14005584b  mov     eax, [rcx+2Ch]
0x14005584e  test    r14b, al
0x140055851  jz      loc_1400559AB
0x140055857  cmp     byte ptr [rcx+29h], 2
0x14005585b  jb      loc_1400559AB
0x140055861  mov     edx, 37h ; '7'
0x140055866  jmp     short loc_14005586D
0x140055868  mov     edx, 39h ; '9'
0x14005586d  mov     rax, [rbp+47h+var_90]
0x140055871  mov     r9, [rbp+47h+arg_0]
0x140055875  mov     [rsp+0E0h+var_A0], ebx
0x140055879  mov     [rsp+0E0h+var_A8], rdi
0x14005587e  mov     [rsp+0E0h+RetFileNameInformation], rax
0x140055883  mov     qword ptr [rsp+0E0h+NameOptions], r13
0x140055888  mov     qword ptr [rsp+0E0h+FileNameLength], r9
0x14005588d  jmp     loc_140055998
0x140055892  mov     rcx, cs:WPP_GLOBAL_Control
0x140055899  lea     rsi, WPP_GLOBAL_Control
0x1400558a0  cmp     rcx, rsi
0x1400558a3  jz      loc_1400559AB
0x1400558a9  mov     eax, [rcx+2Ch]
0x1400558ac  test    r14b, al
0x1400558af  jz      loc_1400559AB
0x1400558b5  cmp     byte ptr [rcx+29h], 2
0x1400558b9  jb      loc_1400559AB
0x1400558bf  mov     edx, 38h ; '8'
0x1400558c4  jmp     short loc_14005586D
0x1400558c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400558cd  lea     rsi, WPP_GLOBAL_Control
0x1400558d4  cmp     rcx, rsi
0x1400558d7  jz      loc_1400559AB
0x1400558dd  mov     eax, [rcx+2Ch]
0x1400558e0  test    r14b, al
0x1400558e3  jz      loc_1400559AB
0x1400558e9  cmp     byte ptr [rcx+29h], 2
0x1400558ed  jb      loc_1400559AB
0x1400558f3  jmp     loc_140055868
0x1400558f8  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
