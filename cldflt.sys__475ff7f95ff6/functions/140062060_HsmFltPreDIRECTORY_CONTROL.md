# HsmFltPreDIRECTORY_CONTROL

- ea: `0x140062060`
- end: `0x1400626ab`
- name: `HsmFltPreDIRECTORY_CONTROL`
- size: `1611`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x140001910`
- `0x140001d00`
- `0x140003c50`
- `0x140003cf0`
- `0x1400044f0`
- `0x140006da0`
- `0x140006f40`
- `0x140007ddc`
- `0x140009300`
- `0x140009364`
- `0x14000aafc`
- `0x14001e300`
- `0x140062060`
- `0x1400626b4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400620bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140062684`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400620bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140062684`
- `ntoskrnl!ExAllocatePool2` at `0x1400622f9`
- `ntoskrnl!ExAllocatePool2` at `0x1400622f9`
- `FLTMGR!FltGetFileNameInformation` at `0x1400625c8`
- `FLTMGR!FltGetFileNameInformation` at `0x1400625c8`
- `FLTMGR!FltGetStreamHandleContext` at `0x140062131`
- `FLTMGR!FltGetStreamHandleContext` at `0x140062131`
- `FLTMGR!FltDeleteContext` at `0x140062577`
- `FLTMGR!FltDeleteContext` at `0x140062577`
- `FLTMGR!FltGetRequestorProcess` at `0x14006216e`
- `FLTMGR!FltGetRequestorProcess` at `0x1400621de`
- `FLTMGR!FltGetRequestorProcess` at `0x14006216e`
- `FLTMGR!FltGetRequestorProcess` at `0x1400621de`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x1400622ad`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x1400622ad`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400623e5`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400623e5`
- `FLTMGR!FltReleaseContext` at `0x1400620e8`
- `FLTMGR!FltReleaseContext` at `0x14006218e`
- `FLTMGR!FltReleaseContext` at `0x1400620e8`
- `FLTMGR!FltReleaseContext` at `0x14006218e`

## pseudocode

```c
__int64 __fastcall HsmFltPreDIRECTORY_CONTROL(PFLT_CALLBACK_DATA CallbackData, __int64 a2, _QWORD *a3)
{
  unsigned int v4; // ebx
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  char v6; // r14
  int Directory; // edi
  __int64 *v9; // rsi
  void *v10; // r15
  struct _FLT_INSTANCE *v12; // rax
  struct _FILE_OBJECT *v13; // rdx
  __int64 v14; // rcx
  PEPROCESS RequestorProcess; // rax
  PFLT_CONTEXT v16; // rcx
  __int64 v17; // rcx
  PFLT_IO_PARAMETER_BLOCK v18; // rax
  PEPROCESS v19; // rax
  bool v20; // dl
  DWORD LowPart; // ecx
  char PlaceholderCompatMode; // al
  bool v23; // al
  PFLT_IO_PARAMETER_BLOCK v24; // rax
  struct _FILE_OBJECT *TargetFileObject; // rcx
  NTSTATUS FileNameInformationUnsafe; // eax
  __int16 v27; // dx
  __int64 v28; // rdx
  __int64 Length; // rdx
  unsigned __int16 v30; // ax
  char *v31; // rdx
  unsigned __int64 v32; // rdi
  _WORD *v33; // rcx
  __int128 v34; // xmm0
  PFLT_CONTEXT Context; // [rsp+50h] [rbp-39h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+58h] [rbp-31h] BYREF
  struct _FILE_OBJECT *v37; // [rsp+60h] [rbp-29h]
  PFLT_INSTANCE TargetInstance; // [rsp+68h] [rbp-21h]
  __int64 v39; // [rsp+70h] [rbp-19h]
  __int64 v40; // [rsp+78h] [rbp-11h]
  __int128 v41; // [rsp+80h] [rbp-9h]
  PVOID P[2]; // [rsp+90h] [rbp+7h] BYREF
  struct _FLT_INSTANCE *v43; // [rsp+F0h] [rbp+67h]
  bool v44; // [rsp+F0h] [rbp+67h]
  char v45; // [rsp+F8h] [rbp+6Fh]
  bool v46; // [rsp+100h] [rbp+77h]
  PVOID Pool2; // [rsp+100h] [rbp+77h]
  _QWORD *v48; // [rsp+108h] [rbp+7Fh]

  v37 = *(struct _FILE_OBJECT **)(a2 + 32);
  *a3 = 0;
  v4 = 1;
  v45 = 0;
  Iopb = CallbackData->Iopb;
  v6 = 0;
  *(_OWORD *)P = 0;
  Directory = 0;
  if ( Iopb->MinorFunction != 1 )
  {
    v9 = 0;
    v10 = 0;
    goto LABEL_3;
  }
  v12 = *(struct _FLT_INSTANCE **)(a2 + 24);
  v13 = *(struct _FILE_OBJECT **)(a2 + 32);
  Context = 0;
  v43 = v12;
  FltGetStreamHandleContext(v12, v13, &Context);
  v9 = (__int64 *)Context;
  if ( !Context )
    goto LABEL_20;
  v14 = *((_QWORD *)Context + 2);
  if ( (*(_DWORD *)(v14 + 28) & 1) == 0 )
  {
    FltDeleteContext(Context);
    goto LABEL_17;
  }
  if ( *(struct _FLT_INSTANCE **)(*(_QWORD *)(*(_QWORD *)(v14 + 16) + 16LL) + 32LL) != v43 )
  {
    v16 = Context;
    goto LABEL_18;
  }
  RequestorProcess = FltGetRequestorProcess(CallbackData);
  if ( (unsigned __int8)HsmOsIsPassThroughModeEnabled(RequestorProcess) )
  {
LABEL_17:
    v16 = Context;
LABEL_18:
    FltReleaseContext(v16);
    v9 = 0;
    Context = 0;
    goto LABEL_19;
  }
  v9 = (__int64 *)Context;
LABEL_19:
  if ( !v9 )
  {
LABEL_20:
    v10 = 0;
    goto LABEL_3;
  }
  v48 = (_QWORD *)v9[2];
  v40 = v48[2];
  v17 = *(_QWORD *)(v40 + 16);
  TargetInstance = *(PFLT_INSTANCE *)(v40 + 32);
  v18 = CallbackData->Iopb;
  v39 = v17;
  if ( (v18->OperationFlags & 8) != 0 )
  {
    v20 = 0;
  }
  else
  {
    v19 = FltGetRequestorProcess(CallbackData);
    v20 = (unsigned __int8)HsmOsIsSyncProviderProcess(v19) == 0;
  }
  v46 = v20;
  LowPart = CallbackData->Iopb->Parameters.Read.ByteOffset.LowPart;
  if ( LowPart == 81 )
  {
LABEL_24:
    PlaceholderCompatMode = HsmOsGetPlaceholderCompatMode(CallbackData);
    v20 = v46;
    v23 = PlaceholderCompatMode != 2;
  }
  else
  {
    switch ( LowPart )
    {
      case 1u:
      case 2u:
      case 3u:
      case 0x25u:
      case 0x26u:
      case 0x3Cu:
      case 0x3Fu:
      case 0x4Eu:
      case 0x4Fu:
      case 0x50u:
        goto LABEL_24;
      default:
        v23 = 0;
        break;
    }
  }
  v44 = v23;
  if ( !v20 && !v23 )
    goto LABEL_50;
  v6 = 1;
  HsmpTracePreCallbackEnter((_DWORD)CallbackData, 0, 1, (_DWORD)v9, v9[2]);
  if ( v46 )
  {
    Directory = HsmpAcquireUserRequestRundownProtection(v48, CallbackData);
    HsmDbgBreakOnStatus(Directory);
    if ( Directory < 0 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_50;
      v10 = v48;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_qqLqiqd(
          WPP_GLOBAL_Control->AttachedDevice,
          18,
          (unsigned int)WPP_3a0b160e0a683f3dea1866dfb9c0f226_Traceguids,
          v39,
          (char)v48,
          *((_DWORD *)v48 + 7),
          (char)v37,
          (char)TargetInstance,
          CallbackData,
          Directory);
      goto LABEL_3;
    }
    v24 = CallbackData->Iopb;
    v45 = 1;
    FileNameInformation = 0;
    v41 = 0;
    TargetFileObject = v24->TargetFileObject;
    TargetInstance = v24->TargetInstance;
    v37 = TargetFileObject;
    if ( TargetFileObject )
      FileNameInformationUnsafe = FltGetFileNameInformationUnsafe(TargetFileObject, 0, 0x101u, &FileNameInformation);
    else
      FileNameInformationUnsafe = FltGetFileNameInformation(0, 0x101u, &FileNameInformation);
    Directory = FileNameInformationUnsafe;
    HsmDbgBreakOnStatus(FileNameInformationUnsafe);
    if ( Directory < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qqd(
          WPP_GLOBAL_Control->AttachedDevice,
          13,
          WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids,
          TargetInstance,
          v37,
          Directory);
      }
      Pool2 = (PVOID)*((_QWORD *)&v41 + 1);
    }
    else
    {
      v27 = FileNameInformation->Name.Length - FileNameInformation->Volume.Length;
      LOWORD(v41) = 0;
      v28 = (unsigned __int16)(v27 + 2);
      WORD1(v41) = v28;
      Pool2 = (PVOID)ExAllocatePool2(256, v28, 1934979912);
      *((_QWORD *)&v41 + 1) = Pool2;
      if ( Pool2 )
      {
        HsmDbgBreakOnStatus(0);
        Length = FileNameInformation->Volume.Length;
        v30 = FileNameInformation->Name.Length - Length;
        v31 = (char *)FileNameInformation->Name.Buffer + Length;
        v32 = v30;
        LOWORD(v41) = v30;
        memmove(Pool2, v31, v30);
        v33 = Pool2;
        v34 = v41;
        Pool2 = 0;
        v33[v32 >> 1] = 0;
        Directory = 0;
        *(_OWORD *)P = v34;
      }
      else
      {
        Directory = -1073741670;
        HsmDbgBreakOnStatus(-1073741670);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_qqd(
            WPP_GLOBAL_Control->AttachedDevice,
            14,
            WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids,
            TargetInstance,
            v37,
            -1073741670);
        }
      }
    }
    if ( FileNameInformation )
      FltReleaseFileNameInformation(FileNameInformation);
    if ( Pool2 )
      ExFreePoolWithTag(Pool2, 0x73557348u);
    HsmDbgBreakOnStatus(Directory);
    if ( Directory < 0 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_50;
      v10 = v48;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_qqLqiqd(
          WPP_GLOBAL_Control->AttachedDevice,
          19,
          (unsigned int)WPP_3a0b160e0a683f3dea1866dfb9c0f226_Traceguids,
          v39,
          (char)v48,
          *((_DWORD *)v48 + 7),
          (char)CallbackData->Iopb->TargetFileObject,
          *(_QWORD *)(v40 + 32),
          CallbackData,
          Directory);
      goto LABEL_3;
    }
    v4 = HsmpRecallInitiatePopulationEx(v9, v48, CallbackData->Iopb->TargetFileObject, CallbackData, P, 0, 0, v44);
  }
  if ( !v44 )
  {
LABEL_50:
    v10 = v48;
    goto LABEL_3;
  }
  v4 = 4;
  Directory = HsmiMungeQueryDirectory(CallbackData);
  HsmDbgBreakOnStatus(Directory);
  v10 = v48;
LABEL_3:
  if ( P[1] )
    ExFreePoolWithTag(P[1], 0x73557348u);
  if ( Directory < 0 )
  {
    CallbackData->IoStatus.Status = Directory;
    v4 = 4;
    CallbackData->IoStatus.Information = 0;
  }
  else
  {
    if ( !v4 )
    {
      *a3 = v10;
      goto LABEL_8;
    }
    if ( v4 == 2 )
      goto LABEL_8;
  }
  if ( v45 )
    HsmpReleaseUserRequestRundownProtection(v10);
LABEL_8:
  if ( v9 )
    FltReleaseContext(v9);
  if ( v6 && v4 != 2 )
    HsmpTracePreCallbackExit(v4, (_DWORD)CallbackData, *a3, v9 == 0, v9 != 0);
  return v4;
}

```

## disassembly

```asm
0x140062060  push    rbp
0x140062062  push    rbx
0x140062063  push    rsi
0x140062064  push    rdi
0x140062065  push    r12
0x140062067  push    r13
0x140062069  push    r14
0x14006206b  push    r15
0x14006206d  lea     rbp, [rsp-1Fh]
0x140062072  sub     rsp, 0A8h
0x140062079  mov     rax, [rdx+20h]
0x14006207d  mov     r13, rcx
0x140062080  xor     ecx, ecx
0x140062082  mov     [rbp+57h+var_80], rax
0x140062086  mov     [r8], rcx
0x140062089  xorps   xmm0, xmm0
0x14006208c  mov     ebx, 1
0x140062091  mov     [rbp+57h+arg_8], cl
0x140062094  mov     rax, [r13+10h]
0x140062098  xor     r14b, r14b
0x14006209b  movups  xmmword ptr [rbp+57h+P], xmm0
0x14006209f  mov     r12, r8
0x1400620a2  mov     r15, rdx
0x1400620a5  mov     edi, ecx
0x1400620a7  cmp     [rax+5], bl
0x1400620aa  jz      short loc_14006211A
0x1400620ac  mov     esi, ecx
0x1400620ae  mov     r15d, ecx
0x1400620b1  mov     rcx, [rbp+57h+P+8]; P
0x1400620b5  test    rcx, rcx
0x1400620b8  jz      short loc_1400620CB
0x1400620ba  mov     edx, 73557348h; Tag
0x1400620bf  call    cs:__imp_ExFreePoolWithTag
0x1400620c6  nop     dword ptr [rax+rax+00h]
0x1400620cb  test    edi, edi
0x1400620cd  js      loc_140062695
0x1400620d3  test    ebx, ebx
0x1400620d5  jz      short loc_140062114
0x1400620d7  cmp     ebx, 2
0x1400620da  jnz     loc_140062361
0x1400620e0  test    rsi, rsi
0x1400620e3  jz      short loc_1400620F4
0x1400620e5  mov     rcx, rsi; Context
0x1400620e8  call    cs:__imp_FltReleaseContext
0x1400620ef  nop     dword ptr [rax+rax+00h]
0x1400620f4  test    r14b, r14b
0x1400620f7  jnz     loc_140062378
0x1400620fd  mov     eax, ebx
0x1400620ff  add     rsp, 0A8h
0x140062106  pop     r15
0x140062108  pop     r14
0x14006210a  pop     r13
0x14006210c  pop     r12
0x14006210e  pop     rdi
0x14006210f  pop     rsi
0x140062110  pop     rbx
0x140062111  pop     rbp
0x140062112  retn
0x140062114  mov     [r12], r15
0x140062118  jmp     short loc_1400620E0
0x14006211a  mov     rax, [rdx+18h]
0x14006211e  lea     r8, [rbp+57h+Context]; Context
0x140062122  mov     rdx, [rdx+20h]; FileObject
0x140062126  mov     [rbp+57h+Context], rcx
0x14006212a  mov     rcx, rax; Instance
0x14006212d  mov     [rbp+57h+arg_0], rax
0x140062131  call    cs:__imp_FltGetStreamHandleContext
0x140062138  nop     dword ptr [rax+rax+00h]
0x14006213d  mov     rsi, [rbp+57h+Context]
0x140062141  test    rsi, rsi
0x140062144  jz      short loc_1400621A5
0x140062146  mov     rcx, [rsi+10h]
0x14006214a  mov     eax, [rcx+1Ch]
0x14006214d  test    bl, al
0x14006214f  jz      loc_14006256B
0x140062155  mov     rax, [rcx+10h]
0x140062159  mov     rdx, [rax+10h]
0x14006215d  mov     rax, [rbp+57h+arg_0]
0x140062161  cmp     [rdx+20h], rax
0x140062165  jnz     loc_140062588
0x14006216b  mov     rcx, r13; CallbackData
0x14006216e  call    cs:__imp_FltGetRequestorProcess
0x140062175  nop     dword ptr [rax+rax+00h]
0x14006217a  mov     rcx, rax
0x14006217d  call    HsmOsIsPassThroughModeEnabled
0x140062182  test    al, al
0x140062184  jz      loc_140062590
0x14006218a  mov     rcx, [rbp+57h+Context]; Context
0x14006218e  call    cs:__imp_FltReleaseContext
0x140062195  nop     dword ptr [rax+rax+00h]
0x14006219a  xor     esi, esi
0x14006219c  mov     [rbp+57h+Context], rsi
0x1400621a0  test    rsi, rsi
0x1400621a3  jnz     short loc_1400621AD
0x1400621a5  mov     r15, rdi
0x1400621a8  jmp     loc_1400620B1
0x1400621ad  mov     rax, [rsi+10h]
0x1400621b1  mov     [rbp+57h+arg_18], rax
0x1400621b5  mov     rax, [rax+10h]
0x1400621b9  mov     [rbp+57h+var_68], rax
0x1400621bd  mov     rcx, [rax+10h]
0x1400621c1  mov     rax, [rax+20h]
0x1400621c5  mov     [rbp+57h+var_78], rax
0x1400621c9  mov     rax, [r13+10h]
0x1400621cd  mov     [rbp+57h+var_70], rcx
0x1400621d1  test    byte ptr [rax+6], 8
0x1400621d5  jnz     loc_140062454
0x1400621db  mov     rcx, r13; CallbackData
0x1400621de  call    cs:__imp_FltGetRequestorProcess
0x1400621e5  nop     dword ptr [rax+rax+00h]
0x1400621ea  mov     rcx, rax
0x1400621ed  call    HsmOsIsSyncProviderProcess
0x1400621f2  movzx   ecx, bl
0x1400621f5  movzx   edx, bl
0x1400621f8  xor     ecx, ecx
0x1400621fa  test    al, al
0x1400621fc  cmovnz  edx, ecx
0x1400621ff  mov     rax, [r13+10h]
0x140062203  mov     dword ptr [rbp+57h+arg_10], edx
0x140062206  mov     ecx, [rax+28h]
0x140062209  cmp     ecx, 51h ; 'Q'
0x14006220c  jnz     loc_1400623A5
0x140062212  mov     rcx, r13; jumptable 00000001400625B7 cases 1-3,37,38,60,63,78-80
0x140062215  call    HsmOsGetPlaceholderCompatMode
0x14006221a  mov     edx, dword ptr [rbp+57h+arg_10]
0x14006221d  cmp     al, 2
0x14006221f  setnz   al
0x140062222  mov     byte ptr [rbp+57h+arg_0], al
0x140062225  test    dl, dl
0x140062227  jz      loc_1400623B7
0x14006222d  mov     rax, [rsi+10h]
0x140062231  mov     r9, rsi
0x140062234  movzx   r8d, bl
0x140062238  mov     [rsp+0E0h+var_C0], rax
0x14006223d  xor     edx, edx
0x14006223f  mov     rcx, r13
0x140062242  movzx   r14d, bl
0x140062246  call    HsmpTracePreCallbackEnter
0x14006224b  cmp     byte ptr [rbp+57h+arg_10], dil
0x14006224f  jz      loc_140062445
0x140062255  mov     rcx, [rbp+57h+arg_18]; Context
0x140062259  mov     rdx, r13; CallbackData
0x14006225c  call    HsmpAcquireUserRequestRundownProtection
0x140062261  mov     ecx, eax
0x140062263  mov     edi, eax
0x140062265  call    HsmDbgBreakOnStatus
0x14006226a  test    edi, edi
0x14006226c  js      loc_1400624F3
0x140062272  mov     rax, [r13+10h]
0x140062276  xorps   xmm0, xmm0
0x140062279  mov     [rbp+57h+arg_8], bl
0x14006227c  mov     [rbp+57h+FileNameInformation], 0
0x140062284  movups  [rbp+57h+var_60], xmm0
0x140062288  mov     rcx, [rax+8]; FileObject
0x14006228c  mov     rax, [rax+10h]
0x140062290  mov     [rbp+57h+var_78], rax
0x140062294  mov     [rbp+57h+var_80], rcx
0x140062298  test    rcx, rcx
0x14006229b  jz      loc_1400625BD
0x1400622a1  lea     r9, [rbp+57h+FileNameInformation]; FileNameInformation
0x1400622a5  xor     edx, edx; Instance
0x1400622a7  mov     r8d, 101h; NameOptions
0x1400622ad  call    cs:__imp_FltGetFileNameInformationUnsafe
0x1400622b4  nop     dword ptr [rax+rax+00h]
0x1400622b9  mov     ecx, eax
0x1400622bb  mov     edi, eax
0x1400622bd  call    HsmDbgBreakOnStatus
0x1400622c2  lea     rax, WPP_GLOBAL_Control
0x1400622c9  test    edi, edi
0x1400622cb  js      loc_1400623C4
0x1400622d1  mov     rax, [rbp+57h+FileNameInformation]
0x1400622d5  mov     ecx, 100h
0x1400622da  mov     r8d, 73557348h
0x1400622e0  movzx   edx, word ptr [rax+8]
0x1400622e4  sub     dx, [rax+18h]
0x1400622e8  xor     eax, eax
0x1400622ea  add     dx, 2
0x1400622ee  mov     word ptr [rbp+57h+var_60], ax
0x1400622f2  movzx   edx, dx
0x1400622f5  mov     word ptr [rbp+57h+var_60+2], dx
0x1400622f9  call    cs:__imp_ExAllocatePool2
0x140062300  nop     dword ptr [rax+rax+00h]
0x140062305  mov     [rbp+57h+arg_10], rax
0x140062309  mov     qword ptr [rbp+57h+var_60+8], rax
0x14006230d  test    rax, rax
0x140062310  jz      loc_140062619
0x140062316  xor     ecx, ecx
0x140062318  call    HsmDbgBreakOnStatus
0x14006231d  mov     rcx, [rbp+57h+FileNameInformation]
0x140062321  movzx   edx, word ptr [rcx+18h]
0x140062325  movzx   eax, word ptr [rcx+8]
0x140062329  sub     ax, dx
0x14006232c  add     rdx, [rcx+10h]; Src
0x140062330  mov     rcx, [rbp+57h+arg_10]; void *
0x140062334  movzx   edi, ax
0x140062337  mov     r8d, edi; Size
0x14006233a  mov     word ptr [rbp+57h+var_60], di
0x14006233e  call    memmove
0x140062343  mov     rcx, [rbp+57h+arg_10]
0x140062347  xor     eax, eax
0x140062349  movaps  xmm0, [rbp+57h+var_60]
0x14006234d  shr     rdi, 1
0x140062350  mov     [rbp+57h+arg_10], rax
0x140062354  mov     [rcx+rdi*2], ax
0x140062358  xor     edi, edi
0x14006235a  movdqa  xmmword ptr [rbp+57h+P], xmm0
0x14006235f  jmp     short loc_1400623DC
0x140062361  cmp     [rbp+57h+arg_8], 0
0x140062365  jz      loc_1400620E0
0x14006236b  mov     rcx, r15; Context
0x14006236e  call    HsmpReleaseUserRequestRundownProtection
0x140062373  jmp     loc_1400620E0
0x140062378  cmp     ebx, 2
0x14006237b  jz      loc_1400620FD
0x140062381  mov     r8, [r12]
0x140062385  test    rsi, rsi
0x140062388  mov     rdx, r13
0x14006238b  mov     ecx, ebx
0x14006238d  setnz   al
0x140062390  test    rsi, rsi
0x140062393  mov     byte ptr [rsp+0E0h+var_C0], al
0x140062397  setz    r9b
0x14006239b  call    HsmpTracePreCallbackExit
0x1400623a0  jmp     loc_1400620FD
0x1400623a5  dec     ecx; switch 80 cases
0x1400623a7  cmp     ecx, 4Fh
0x1400623aa  jbe     loc_140062599
0x1400623b0  xor     al, al; jumptable 00000001400625B7 default case, cases 4-36,39-59,61,62,64-77
0x1400623b2  jmp     loc_140062222
0x1400623b7  test    al, al
0x1400623b9  jz      loc_14006244B
0x1400623bf  jmp     loc_14006222D
0x1400623c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400623cb  cmp     rcx, rax
0x1400623ce  jnz     loc_1400625D9
0x1400623d4  mov     rax, qword ptr [rbp+57h+var_60+8]
0x1400623d8  mov     [rbp+57h+arg_10], rax
0x1400623dc  mov     rcx, [rbp+57h+FileNameInformation]; FileNameInformation
0x1400623e0  test    rcx, rcx
0x1400623e3  jz      short loc_1400623F1
0x1400623e5  call    cs:__imp_FltReleaseFileNameInformation
0x1400623ec  nop     dword ptr [rax+rax+00h]
0x1400623f1  mov     rax, [rbp+57h+arg_10]
0x1400623f5  test    rax, rax
0x1400623f8  jnz     loc_14006267C
0x1400623fe  mov     ecx, edi
0x140062400  call    HsmDbgBreakOnStatus
0x140062405  test    edi, edi
0x140062407  js      short loc_14006247D
0x140062409  mov     r8, [r13+10h]
0x14006240d  mov     r9, r13
0x140062410  movzx   eax, byte ptr [rbp+57h+arg_0]
0x140062414  mov     rcx, rsi
0x140062417  mov     rdx, [rbp+57h+arg_18]
0x14006241b  mov     dword ptr [rsp+0E0h+var_A8], eax
0x14006241f  lea     rax, [rbp+57h+P]
0x140062423  mov     r8, [r8+8]
0x140062427  mov     [rsp+0E0h+var_B0], 0
0x140062430  mov     [rsp+0E0h+var_B8], 0
0x140062439  mov     [rsp+0E0h+var_C0], rax
0x14006243e  call    HsmpRecallInitiatePopulationEx
0x140062443  mov     ebx, eax
0x140062445  cmp     byte ptr [rbp+57h+arg_0], 0
0x140062449  jnz     short loc_14006245B
0x14006244b  mov     r15, [rbp+57h+arg_18]
0x14006244f  jmp     loc_1400620B1
0x140062454  xor     dl, dl
0x140062456  jmp     loc_1400621FF
0x14006245b  mov     rdx, r15
0x14006245e  mov     rcx, r13; CallbackData
0x140062461  mov     ebx, 4
0x140062466  call    HsmiMungeQueryDirectory
0x14006246b  mov     ecx, eax
0x14006246d  mov     edi, eax
0x14006246f  call    HsmDbgBreakOnStatus
0x140062474  mov     r15, [rbp+57h+arg_18]
0x140062478  jmp     loc_1400620B1
0x14006247d  mov     rcx, cs:WPP_GLOBAL_Control
0x140062484  lea     rax, WPP_GLOBAL_Control
0x14006248b  cmp     rcx, rax
0x14006248e  jz      short loc_14006244B
0x140062490  mov     eax, [rcx+2Ch]
0x140062493  test    bl, al
0x140062495  jz      short loc_14006244B
0x140062497  cmp     byte ptr [rcx+29h], 2
0x14006249b  mov     r15, [rbp+57h+arg_18]
0x14006249f  jb      loc_1400620B1
0x1400624a5  mov     r8, [r13+10h]
0x1400624a9  mov     edx, 13h
0x1400624ae  mov     rax, [rbp+57h+var_68]
0x1400624b2  mov     r9, [rbp+57h+var_70]
0x1400624b6  mov     rcx, [rcx+18h]
0x1400624ba  mov     [rsp+0E0h+var_98], edi
0x1400624be  mov     rax, [rax+20h]
0x1400624c2  mov     [rsp+0E0h+var_A0], r13
0x1400624c7  mov     [rsp+0E0h+var_A8], rax
0x1400624cc  mov     rax, [r8+8]
0x1400624d0  lea     r8, WPP_3a0b160e0a683f3dea1866dfb9c0f226_Traceguids
0x1400624d7  mov     [rsp+0E0h+var_B0], rax
0x1400624dc  mov     eax, [r15+1Ch]
  ... truncated ...
```
