# HsmFltPreSetLinkInformation

- ea: `0x140055308`
- end: `0x1400558d0`
- name: `HsmFltPreSetLinkInformation`
- size: `1480`
- prototype: `__int64 __usercall@<rax>(PFLT_CONTEXT Context@<rcx>, PFLT_CONTEXT@<rdx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400525b0`

## callees

- `0x140001ab4`
- `0x140001d00`
- `0x140003c50`
- `0x140007ddc`
- `0x14000abb8`
- `0x14000d388`
- `0x140052454`
- `0x1400547b0`
- `0x1400547cc`
- `0x140054a04`
- `0x140055250`
- `0x140055308`
- `0x140057a00`
- `0x140058f70`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400554e6`
- `ntoskrnl!ExAllocatePool2` at `0x1400554e6`
- `FLTMGR!FltGetDestinationFileNameInformation` at `0x14005540f`
- `FLTMGR!FltGetDestinationFileNameInformation` at `0x14005540f`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140055549`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140055549`
- `FLTMGR!FltReleaseContext` at `0x1400558a8`
- `FLTMGR!FltReleaseContext` at `0x1400558a8`

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
  char v16; // dl
  void *v17; // rcx
  __int64 Pool2; // rax
  unsigned int v20; // eax
  __int64 v21; // r12
  void *v22; // rdx
  PDEVICE_OBJECT v23; // rcx
  __int64 v24; // rdx
  PDEVICE_OBJECT v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // [rsp+50h] [rbp-49h]
  PFLT_CONTEXT Contexta; // [rsp+58h] [rbp-41h]
  int v29; // [rsp+60h] [rbp-39h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+68h] [rbp-31h] BYREF
  __int64 v31; // [rsp+70h] [rbp-29h] BYREF
  __int64 v32; // [rsp+78h] [rbp-21h] BYREF
  __int128 v33; // [rsp+80h] [rbp-19h] BYREF
  PVOID EaBuffer; // [rsp+90h] [rbp-9h]
  PFLT_INSTANCE Instance; // [rsp+98h] [rbp-1h]
  __int64 v37; // [rsp+F8h] [rbp+5Fh] BYREF
  __int64 v38; // [rsp+100h] [rbp+67h]
  int v39; // [rsp+108h] [rbp+6Fh] BYREF

  v38 = a3;
  StreamContext = a2;
  SyncPolicy = 0;
  v10 = *(struct _FLT_INSTANCE **)(a5 + 24);
  v11 = *(struct _FILE_OBJECT **)(a5 + 32);
  Instance = v10;
  if ( a2 )
    v27 = *(_QWORD *)(a2[2] + 32LL);
  else
    v27 = 0;
  Iopb = a4->Iopb;
  LODWORD(v37) = 0;
  v29 = 0;
  v39 = 0;
  EaBuffer = Iopb->Parameters.Create.EaBuffer;
  FileNameInformation = 0;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  Contexta = (PFLT_CONTEXT)HsmpAcquireFileNameLock(Context);
  if ( !Contexta )
  {
    v13 = 4;
    goto LABEL_17;
  }
  LOBYTE(a5) = 0;
  if ( !StreamContext )
  {
    StreamContext = HsmpGetStreamContext(a4, v10, v11);
    if ( !StreamContext )
    {
      v13 = 0;
      *a6 = (__int64)Contexta;
      goto LABEL_17;
    }
    v21 = HsmpAcquireFileNameLock(Context);
    if ( !v21 )
    {
      v22 = Contexta;
      v13 = 4;
      LOBYTE(a5) = 1;
LABEL_73:
      HsmpReleaseFileNameLock(v22);
      goto LABEL_15;
    }
    HsmpReleaseFileNameLock(Contexta);
    Contexta = (PFLT_CONTEXT)v21;
    LOBYTE(a5) = 1;
  }
  v13 = 1;
  SyncPolicy = HsmpCldGetSyncPolicy((_DWORD)Context, (_DWORD)StreamContext, (_DWORD)v11, 0, (__int64)&v37);
  HsmDbgBreakOnStatus((unsigned int)SyncPolicy);
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
        v27,
        StreamContext,
        SyncPolicy);
    }
    goto LABEL_72;
  }
  if ( (v37 & 0x200000) == 0 )
  {
    SyncPolicy = -1073688807;
    HsmDbgBreakOnStatus(3221278489LL);
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_72;
    }
    v24 = 55;
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
  HsmDbgBreakOnStatus((unsigned int)SyncPolicy);
  if ( SyncPolicy < 0 )
  {
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_72;
    }
    v24 = 56;
    goto LABEL_48;
  }
  Length = FileNameInformation->Volume.Length;
  v15 = FileNameInformation->Name.Length - Length;
  *((_QWORD *)&v33 + 1) = (char *)FileNameInformation->Name.Buffer + Length;
  LOWORD(v33) = v15;
  WORD1(v33) = v15;
  SyncPolicy = HsmiCldGetSyncRootFileIdByPath(Context, &v33, &v31);
  HsmDbgBreakOnStatus((unsigned int)SyncPolicy);
  if ( SyncPolicy != -1073688813 )
  {
    if ( SyncPolicy >= 0 )
    {
      v37 = v31;
      goto LABEL_10;
    }
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_72;
    }
    v24 = 57;
LABEL_48:
    WPP_SF_qiqiid(
      v23->AttachedDevice,
      v24,
      WPP_e26ac64b2c40307be864d687cc32cd5d_Traceguids,
      a4,
      Context,
      v11,
      v27,
      StreamContext,
      SyncPolicy);
LABEL_72:
    v22 = Contexta;
    goto LABEL_73;
  }
  v37 = 0;
LABEL_10:
  SyncPolicy = HsmiCldGetSyncRootFileIdByFileObject(Context, v11, &v32, &v29, &v39);
  HsmDbgBreakOnStatus((unsigned int)SyncPolicy);
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
  HsmDbgBreakOnStatus((unsigned int)SyncPolicy);
  if ( SyncPolicy < 0 )
  {
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_72;
    }
    v26 = 58;
    goto LABEL_71;
  }
  if ( !(unsigned __int8)HsmpIsPlaceholder(StreamContext) || v39 || !v16 )
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
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_72;
    }
    v26 = 60;
LABEL_71:
    WPP_SF_qiqiid(
      v25->AttachedDevice,
      v26,
      WPP_e26ac64b2c40307be864d687cc32cd5d_Traceguids,
      a4,
      Context,
      v11,
      v27,
      StreamContext,
      SyncPolicy);
    goto LABEL_72;
  }
  SyncPolicy = HsmpAcquireUserRequestRundownProtection(v17, a4);
  HsmDbgBreakOnStatus((unsigned int)SyncPolicy);
  if ( SyncPolicy < 0 )
  {
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_72;
    }
    v26 = 59;
    goto LABEL_71;
  }
  v20 = HsmpRecallInitiateHydration(v38, (_DWORD)StreamContext, (_DWORD)v11, 7, (__int64)a4, 0, -1);
  v13 = v20;
  if ( !v20 )
  {
    *a6 = (__int64)StreamContext;
    goto LABEL_15;
  }
  if ( v20 != 2 )
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
0x140055308  mov     [rsp-8+arg_10], r8
0x14005530d  mov     [rsp-8+arg_0], rcx
0x140055312  push    rbp
0x140055313  push    rbx
0x140055314  push    rsi
0x140055315  push    rdi
0x140055316  push    r12
0x140055318  push    r13
0x14005531a  push    r14
0x14005531c  push    r15
0x14005531e  lea     rbp, [rsp-0Fh]
0x140055323  sub     rsp, 0A8h
0x14005532a  mov     rax, [rbp+47h+arg_20]
0x14005532e  mov     rdi, rdx
0x140055331  xor     edx, edx
0x140055333  mov     r15, r9
0x140055336  mov     rsi, rcx
0x140055339  mov     ebx, edx
0x14005533b  mov     r12, [rax+18h]
0x14005533f  mov     r13, [rax+20h]
0x140055343  mov     [rbp+47h+Instance], r12
0x140055347  test    rdi, rdi
0x14005534a  jnz     loc_14005555F
0x140055350  mov     [rbp+47h+var_90], rdx
0x140055354  mov     rax, [r9+10h]
0x140055358  xorps   xmm0, xmm0
0x14005535b  mov     dword ptr [rbp+47h+arg_8], edx
0x14005535e  mov     r8, r15
0x140055361  mov     [rbp+47h+var_80], edx
0x140055364  mov     [rbp+47h+arg_18], edx
0x140055367  mov     rcx, [rax+38h]
0x14005536b  mov     [rbp+47h+var_50], rcx
0x14005536f  mov     rcx, rsi; Context
0x140055372  mov     [rbp+47h+FileNameInformation], rdx
0x140055376  mov     [rbp+47h+var_70], rdx
0x14005537a  mov     [rbp+47h+var_68], rdx
0x14005537e  mov     rdx, rdi
0x140055381  movups  [rbp+47h+var_60], xmm0
0x140055385  call    HsmpAcquireFileNameLock
0x14005538a  mov     [rbp+47h+Context], rax
0x14005538e  test    rax, rax
0x140055391  jz      loc_140055557
0x140055397  mov     byte ptr [rbp+47h+arg_20], bl
0x14005539a  mov     r14d, 1
0x1400553a0  test    rdi, rdi
0x1400553a3  jz      loc_140055630
0x1400553a9  lea     rax, [rbp+47h+arg_8]
0x1400553ad  xor     r9d, r9d
0x1400553b0  mov     r8, r13
0x1400553b3  mov     qword ptr [rsp+0E0h+FileNameLength], rax
0x1400553b8  mov     rdx, rdi
0x1400553bb  mov     rcx, rsi
0x1400553be  mov     r12d, r14d
0x1400553c1  call    HsmpCldGetSyncPolicy
0x1400553c6  mov     ecx, eax
0x1400553c8  mov     ebx, eax
0x1400553ca  call    HsmDbgBreakOnStatus
0x1400553cf  test    ebx, ebx
0x1400553d1  js      loc_1400556AB
0x1400553d7  test    dword ptr [rbp+47h+arg_8], 200000h
0x1400553de  jz      loc_140055708
0x1400553e4  mov     rcx, [rbp+47h+var_50]
0x1400553e8  lea     rax, [rbp+47h+FileNameInformation]
0x1400553ec  mov     [rsp+0E0h+RetFileNameInformation], rax; RetFileNameInformation
0x1400553f1  mov     rdx, r13; FileObject
0x1400553f4  mov     [rsp+0E0h+NameOptions], 101h; NameOptions
0x1400553fc  mov     eax, [rcx+10h]
0x1400553ff  lea     r9, [rcx+14h]; FileName
0x140055403  mov     r8, [rcx+8]; RootDirectory
0x140055407  mov     rcx, [rbp+47h+Instance]; Instance
0x14005540b  mov     [rsp+0E0h+FileNameLength], eax; FileNameLength
0x14005540f  call    cs:__imp_FltGetDestinationFileNameInformation
0x140055416  nop     dword ptr [rax+rax+00h]
0x14005541b  mov     ecx, eax
0x14005541d  mov     ebx, eax
0x14005541f  call    HsmDbgBreakOnStatus
0x140055424  test    ebx, ebx
0x140055426  js      loc_140055772
0x14005542c  mov     rax, [rbp+47h+FileNameInformation]
0x140055430  lea     r8, [rbp+47h+var_70]
0x140055434  movzx   edx, word ptr [rax+18h]
0x140055438  movzx   ecx, word ptr [rax+8]
0x14005543c  sub     cx, dx
0x14005543f  add     rdx, [rax+10h]
0x140055443  mov     qword ptr [rbp+47h+var_60+8], rdx
0x140055447  lea     rdx, [rbp+47h+var_60]
0x14005544b  mov     word ptr [rbp+47h+var_60], cx
0x14005544f  mov     word ptr [rbp+47h+var_60+2], cx
0x140055453  mov     rcx, rsi
0x140055456  call    HsmiCldGetSyncRootFileIdByPath
0x14005545b  mov     ecx, eax
0x14005545d  mov     ebx, eax
0x14005545f  call    HsmDbgBreakOnStatus
0x140055464  cmp     ebx, 0C000CF13h
0x14005546a  jnz     loc_140055659
0x140055470  mov     [rbp+47h+arg_8], 0
0x140055478  lea     rax, [rbp+47h+arg_18]
0x14005547c  mov     rdx, r13
0x14005547f  lea     r9, [rbp+47h+var_80]
0x140055483  mov     qword ptr [rsp+0E0h+FileNameLength], rax
0x140055488  lea     r8, [rbp+47h+var_68]
0x14005548c  mov     rcx, rsi
0x14005548f  call    HsmiCldGetSyncRootFileIdByFileObject
0x140055494  mov     ecx, eax
0x140055496  mov     ebx, eax
0x140055498  call    HsmDbgBreakOnStatus
0x14005549d  lea     rsi, WPP_GLOBAL_Control
0x1400554a4  test    ebx, ebx
0x1400554a6  js      loc_140055570
0x1400554ac  mov     ecx, ebx
0x1400554ae  call    HsmDbgBreakOnStatus
0x1400554b3  test    ebx, ebx
0x1400554b5  js      loc_1400557D8
0x1400554bb  mov     rax, [rbp+47h+arg_8]
0x1400554bf  mov     rcx, rdi
0x1400554c2  cmp     [rbp+47h+var_68], rax
0x1400554c6  setnz   dl
0x1400554c9  call    HsmpIsPlaceholder
0x1400554ce  test    al, al
0x1400554d0  jnz     loc_1400555C2
0x1400554d6  mov     edx, 10h
0x1400554db  mov     ecx, 100h
0x1400554e0  mov     r8d, 634C7348h
0x1400554e6  call    cs:__imp_ExAllocatePool2
0x1400554ed  nop     dword ptr [rax+rax+00h]
0x1400554f2  mov     rcx, rax
0x1400554f5  test    rax, rax
0x1400554f8  jz      loc_140055839
0x1400554fe  mov     rdx, [rbp+47h+Context]
0x140055502  xor     r12d, r12d
0x140055505  mov     [rax+8], rdx
0x140055509  mov     dword ptr [rax], 634C7348h
0x14005550f  mov     rax, [rbp+47h+arg_28]
0x140055513  mov     [rax], rcx
0x140055516  cmp     byte ptr [rbp+47h+arg_20], 0
0x14005551a  jnz     loc_1400558A5
0x140055520  mov     rcx, [rbp+47h+FileNameInformation]; FileNameInformation
0x140055524  test    rcx, rcx
0x140055527  jnz     short loc_140055549
0x140055529  test    ebx, ebx
0x14005552b  js      loc_1400558B9
0x140055531  mov     eax, r12d
0x140055534  add     rsp, 0A8h
0x14005553b  pop     r15
0x14005553d  pop     r14
0x14005553f  pop     r13
0x140055541  pop     r12
0x140055543  pop     rdi
0x140055544  pop     rsi
0x140055545  pop     rbx
0x140055546  pop     rbp
0x140055547  retn
0x140055549  call    cs:__imp_FltReleaseFileNameInformation
0x140055550  nop     dword ptr [rax+rax+00h]
0x140055555  jmp     short loc_140055529
0x140055557  mov     r12d, 4
0x14005555d  jmp     short loc_140055520
0x14005555f  mov     rax, [rdi+10h]
0x140055563  mov     r14, [rax+20h]
0x140055567  mov     [rbp+47h+var_90], r14
0x14005556b  jmp     loc_140055354
0x140055570  mov     rcx, cs:WPP_GLOBAL_Control
0x140055577  cmp     rcx, rsi
0x14005557a  jz      loc_1400554AC
0x140055580  mov     eax, [rcx+2Ch]
0x140055583  test    r14b, al
0x140055586  jz      loc_1400554AC
0x14005558c  cmp     byte ptr [rcx+29h], 3
0x140055590  jb      loc_1400554AC
0x140055596  mov     r9, [rbp+47h+arg_0]
0x14005559a  lea     r8, WPP_6e1e33f79617319dc28b4de987ec2fe8_Traceguids
0x1400555a1  mov     rcx, [rcx+18h]
0x1400555a5  mov     edx, 37h ; '7'
0x1400555aa  mov     dword ptr [rsp+0E0h+RetFileNameInformation], ebx
0x1400555ae  mov     qword ptr [rsp+0E0h+NameOptions], r13
0x1400555b3  mov     qword ptr [rsp+0E0h+FileNameLength], rdi
0x1400555b8  call    WPP_SF_qqqd
0x1400555bd  jmp     loc_1400554AC
0x1400555c2  cmp     [rbp+47h+arg_18], 0
0x1400555c6  jnz     loc_1400554D6
0x1400555cc  test    dl, dl
0x1400555ce  jz      loc_1400554D6
0x1400555d4  mov     rdx, r15; CallbackData
0x1400555d7  call    HsmpAcquireUserRequestRundownProtection
0x1400555dc  mov     ecx, eax
0x1400555de  mov     ebx, eax
0x1400555e0  call    HsmDbgBreakOnStatus
0x1400555e5  test    ebx, ebx
0x1400555e7  js      loc_140055805
0x1400555ed  mov     rcx, [rbp+47h+arg_10]
0x1400555f1  mov     r9d, 7
0x1400555f7  mov     [rsp+0E0h+RetFileNameInformation], 0FFFFFFFFFFFFFFFFh
0x140055600  mov     r8, r13
0x140055603  mov     qword ptr [rsp+0E0h+NameOptions], 0
0x14005560c  mov     rdx, rdi
0x14005560f  mov     qword ptr [rsp+0E0h+FileNameLength], r15
0x140055614  call    HsmpRecallInitiateHydration
0x140055619  mov     r12d, eax
0x14005561c  test    eax, eax
0x14005561e  jnz     loc_140055826
0x140055624  mov     rcx, [rbp+47h+arg_28]
0x140055628  mov     [rcx], rdi
0x14005562b  jmp     loc_140055516
0x140055630  mov     r8, r13; FileObject
0x140055633  mov     rdx, r12; Instance
0x140055636  mov     rcx, r15; CallbackData
0x140055639  call    HsmpGetStreamContext
0x14005563e  mov     rdi, rax
0x140055641  test    rax, rax
0x140055644  jnz     short loc_14005566E
0x140055646  mov     rax, [rbp+47h+arg_28]
0x14005564a  xor     r12d, r12d
0x14005564d  mov     rdx, [rbp+47h+Context]
0x140055651  mov     [rax], rdx
0x140055654  jmp     loc_140055520
0x140055659  test    ebx, ebx
0x14005565b  js      loc_1400557A6
0x140055661  mov     rax, [rbp+47h+var_70]
0x140055665  mov     [rbp+47h+arg_8], rax
0x140055669  jmp     loc_140055478
0x14005566e  mov     r8, r15
0x140055671  mov     rdx, rax
0x140055674  mov     rcx, rsi; Context
0x140055677  call    HsmpAcquireFileNameLock
0x14005567c  mov     r12, rax
0x14005567f  test    rax, rax
0x140055682  jnz     short loc_140055695
0x140055684  mov     rdx, [rbp+47h+Context]
0x140055688  lea     r12d, [rax+4]
0x14005568c  mov     byte ptr [rbp+47h+arg_20], r14b
0x140055690  jmp     loc_140055898
0x140055695  mov     rcx, [rbp+47h+Context]; Context
0x140055699  call    HsmpReleaseFileNameLock
0x14005569e  mov     [rbp+47h+Context], r12
0x1400556a2  mov     byte ptr [rbp+47h+arg_20], r14b
0x1400556a6  jmp     loc_1400553A9
0x1400556ab  mov     r10, cs:WPP_GLOBAL_Control
0x1400556b2  lea     rsi, WPP_GLOBAL_Control
0x1400556b9  cmp     r10, rsi
0x1400556bc  jz      loc_14005588B
0x1400556c2  mov     ecx, [r10+2Ch]
0x1400556c6  test    r14b, cl
0x1400556c9  jz      loc_14005588B
0x1400556cf  cmp     byte ptr [r10+29h], 2
0x1400556d4  jb      loc_14005588B
0x1400556da  mov     rax, [rbp+47h+var_90]
0x1400556de  mov     edx, 36h ; '6'
0x1400556e3  mov     r9, [rbp+47h+arg_0]
0x1400556e7  mov     rcx, [r10+18h]
0x1400556eb  mov     [rsp+0E0h+var_A0], ebx
0x1400556ef  mov     [rsp+0E0h+var_A8], rdi
0x1400556f4  mov     [rsp+0E0h+RetFileNameInformation], rax
0x1400556f9  mov     qword ptr [rsp+0E0h+NameOptions], r13
0x1400556fe  mov     qword ptr [rsp+0E0h+FileNameLength], r9
0x140055703  jmp     loc_14005587C
0x140055708  mov     ebx, 0C000CF19h
0x14005570d  mov     ecx, ebx
0x14005570f  call    HsmDbgBreakOnStatus
0x140055714  mov     rcx, cs:WPP_GLOBAL_Control
0x14005571b  lea     rsi, WPP_GLOBAL_Control
0x140055722  cmp     rcx, rsi
0x140055725  jz      loc_14005588B
0x14005572b  mov     eax, [rcx+2Ch]
0x14005572e  test    r14b, al
0x140055731  jz      loc_14005588B
0x140055737  cmp     byte ptr [rcx+29h], 2
0x14005573b  jb      loc_14005588B
0x140055741  mov     edx, 37h ; '7'
0x140055746  jmp     short loc_14005574D
0x140055748  mov     edx, 39h ; '9'
0x14005574d  mov     rax, [rbp+47h+var_90]
0x140055751  mov     r9, [rbp+47h+arg_0]
0x140055755  mov     [rsp+0E0h+var_A0], ebx
0x140055759  mov     [rsp+0E0h+var_A8], rdi
0x14005575e  mov     [rsp+0E0h+RetFileNameInformation], rax
0x140055763  mov     qword ptr [rsp+0E0h+NameOptions], r13
0x140055768  mov     qword ptr [rsp+0E0h+FileNameLength], r9
0x14005576d  jmp     loc_140055878
0x140055772  mov     rcx, cs:WPP_GLOBAL_Control
0x140055779  lea     rsi, WPP_GLOBAL_Control
0x140055780  cmp     rcx, rsi
0x140055783  jz      loc_14005588B
0x140055789  mov     eax, [rcx+2Ch]
0x14005578c  test    r14b, al
0x14005578f  jz      loc_14005588B
0x140055795  cmp     byte ptr [rcx+29h], 2
0x140055799  jb      loc_14005588B
0x14005579f  mov     edx, 38h ; '8'
0x1400557a4  jmp     short loc_14005574D
0x1400557a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400557ad  lea     rsi, WPP_GLOBAL_Control
0x1400557b4  cmp     rcx, rsi
0x1400557b7  jz      loc_14005588B
0x1400557bd  mov     eax, [rcx+2Ch]
0x1400557c0  test    r14b, al
0x1400557c3  jz      loc_14005588B
0x1400557c9  cmp     byte ptr [rcx+29h], 2
0x1400557cd  jb      loc_14005588B
0x1400557d3  jmp     loc_140055748
0x1400557d8  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
