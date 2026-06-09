# HsmFltPreDIRECTORY_CONTROL

- ea: `0x140061f40`
- end: `0x14006258b`
- name: `HsmFltPreDIRECTORY_CONTROL`
- size: `1611`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
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
- `0x14001e280`
- `0x140061f40`
- `0x140062594`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140061f9f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140062564`
- `ntoskrnl!ExFreePoolWithTag` at `0x140061f9f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140062564`
- `ntoskrnl!ExAllocatePool2` at `0x1400621d9`
- `ntoskrnl!ExAllocatePool2` at `0x1400621d9`
- `FLTMGR!FltGetFileNameInformation` at `0x1400624a8`
- `FLTMGR!FltGetFileNameInformation` at `0x1400624a8`
- `FLTMGR!FltGetStreamHandleContext` at `0x140062011`
- `FLTMGR!FltGetStreamHandleContext` at `0x140062011`
- `FLTMGR!FltDeleteContext` at `0x140062457`
- `FLTMGR!FltDeleteContext` at `0x140062457`
- `FLTMGR!FltGetRequestorProcess` at `0x14006204e`
- `FLTMGR!FltGetRequestorProcess` at `0x1400620be`
- `FLTMGR!FltGetRequestorProcess` at `0x14006204e`
- `FLTMGR!FltGetRequestorProcess` at `0x1400620be`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x14006218d`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x14006218d`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400622c5`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400622c5`
- `FLTMGR!FltReleaseContext` at `0x140061fc8`
- `FLTMGR!FltReleaseContext` at `0x14006206e`
- `FLTMGR!FltReleaseContext` at `0x140061fc8`
- `FLTMGR!FltReleaseContext` at `0x14006206e`

## pseudocode

```c
__int64 __fastcall HsmFltPreDIRECTORY_CONTROL(PFLT_CALLBACK_DATA CallbackData, __int64 a2, _QWORD *a3)
{
  unsigned int v4; // ebx
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  char v6; // r14
  unsigned __int64 v9; // rdi
  __int64 *v10; // rsi
  void *v11; // r15
  struct _FLT_INSTANCE *v13; // rax
  struct _FILE_OBJECT *v14; // rdx
  __int64 v15; // rcx
  PEPROCESS RequestorProcess; // rax
  PFLT_CONTEXT v17; // rcx
  __int64 v18; // rcx
  PFLT_IO_PARAMETER_BLOCK v19; // rax
  PEPROCESS v20; // rax
  bool v21; // dl
  DWORD LowPart; // ecx
  char PlaceholderCompatMode; // al
  bool v24; // al
  PFLT_IO_PARAMETER_BLOCK v25; // rax
  struct _FILE_OBJECT *TargetFileObject; // rcx
  unsigned int FileNameInformationUnsafe; // eax
  __int16 v28; // dx
  __int64 v29; // rdx
  __int64 Length; // rdx
  unsigned __int16 v31; // ax
  char *v32; // rdx
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
  LODWORD(v9) = 0;
  if ( Iopb->MinorFunction != 1 )
  {
    v10 = 0;
    v11 = 0;
    goto LABEL_3;
  }
  v13 = *(struct _FLT_INSTANCE **)(a2 + 24);
  v14 = *(struct _FILE_OBJECT **)(a2 + 32);
  Context = 0;
  v43 = v13;
  FltGetStreamHandleContext(v13, v14, &Context);
  v10 = (__int64 *)Context;
  if ( !Context )
    goto LABEL_20;
  v15 = *((_QWORD *)Context + 2);
  if ( (*(_DWORD *)(v15 + 28) & 1) == 0 )
  {
    FltDeleteContext(Context);
    goto LABEL_17;
  }
  if ( *(struct _FLT_INSTANCE **)(*(_QWORD *)(*(_QWORD *)(v15 + 16) + 16LL) + 32LL) != v43 )
  {
    v17 = Context;
    goto LABEL_18;
  }
  RequestorProcess = FltGetRequestorProcess(CallbackData);
  if ( (unsigned __int8)HsmOsIsPassThroughModeEnabled(RequestorProcess) )
  {
LABEL_17:
    v17 = Context;
LABEL_18:
    FltReleaseContext(v17);
    v10 = 0;
    Context = 0;
    goto LABEL_19;
  }
  v10 = (__int64 *)Context;
LABEL_19:
  if ( !v10 )
  {
LABEL_20:
    v11 = 0;
    goto LABEL_3;
  }
  v48 = (_QWORD *)v10[2];
  v40 = v48[2];
  v18 = *(_QWORD *)(v40 + 16);
  TargetInstance = *(PFLT_INSTANCE *)(v40 + 32);
  v19 = CallbackData->Iopb;
  v39 = v18;
  if ( (v19->OperationFlags & 8) != 0 )
  {
    v21 = 0;
  }
  else
  {
    v20 = FltGetRequestorProcess(CallbackData);
    v21 = (unsigned __int8)HsmOsIsSyncProviderProcess(v20) == 0;
  }
  v46 = v21;
  LowPart = CallbackData->Iopb->Parameters.Read.ByteOffset.LowPart;
  if ( LowPart == 81 )
  {
LABEL_24:
    PlaceholderCompatMode = HsmOsGetPlaceholderCompatMode((__int64)CallbackData);
    v21 = v46;
    v24 = PlaceholderCompatMode != 2;
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
        v24 = 0;
        break;
    }
  }
  v44 = v24;
  if ( !v21 && !v24 )
    goto LABEL_50;
  v6 = 1;
  HsmpTracePreCallbackEnter((_DWORD)CallbackData, 0, 1, (_DWORD)v10, v10[2]);
  if ( v46 )
  {
    v9 = (unsigned int)HsmpAcquireUserRequestRundownProtection(v48, CallbackData);
    HsmDbgBreakOnStatus(v9);
    if ( (v9 & 0x80000000) != 0LL )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_50;
      v11 = v48;
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
          v9);
      goto LABEL_3;
    }
    v25 = CallbackData->Iopb;
    v45 = 1;
    FileNameInformation = 0;
    v41 = 0;
    TargetFileObject = v25->TargetFileObject;
    TargetInstance = v25->TargetInstance;
    v37 = TargetFileObject;
    if ( TargetFileObject )
      FileNameInformationUnsafe = FltGetFileNameInformationUnsafe(TargetFileObject, 0, 0x101u, &FileNameInformation);
    else
      FileNameInformationUnsafe = FltGetFileNameInformation(0, 0x101u, &FileNameInformation);
    LODWORD(v9) = FileNameInformationUnsafe;
    HsmDbgBreakOnStatus(FileNameInformationUnsafe);
    if ( (v9 & 0x80000000) != 0LL )
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
          v37);
      }
      Pool2 = (PVOID)*((_QWORD *)&v41 + 1);
    }
    else
    {
      v28 = FileNameInformation->Name.Length - FileNameInformation->Volume.Length;
      LOWORD(v41) = 0;
      v29 = (unsigned __int16)(v28 + 2);
      WORD1(v41) = v29;
      Pool2 = (PVOID)ExAllocatePool2(256, v29, 1934979912);
      *((_QWORD *)&v41 + 1) = Pool2;
      if ( Pool2 )
      {
        HsmDbgBreakOnStatus(0);
        Length = FileNameInformation->Volume.Length;
        v31 = FileNameInformation->Name.Length - Length;
        v32 = (char *)FileNameInformation->Name.Buffer + Length;
        v9 = v31;
        LOWORD(v41) = v31;
        memmove(Pool2, v32, v31);
        v33 = Pool2;
        v34 = v41;
        Pool2 = 0;
        v33[v9 >> 1] = 0;
        LODWORD(v9) = 0;
        *(_OWORD *)P = v34;
      }
      else
      {
        LODWORD(v9) = -1073741670;
        HsmDbgBreakOnStatus(3221225626LL);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_qqd(
            WPP_GLOBAL_Control->AttachedDevice,
            14,
            WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids,
            TargetInstance,
            v37);
        }
      }
    }
    if ( FileNameInformation )
      FltReleaseFileNameInformation(FileNameInformation);
    if ( Pool2 )
      ExFreePoolWithTag(Pool2, 0x73557348u);
    HsmDbgBreakOnStatus((unsigned int)v9);
    if ( (v9 & 0x80000000) != 0LL )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_50;
      v11 = v48;
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
          v9);
      goto LABEL_3;
    }
    v4 = HsmpRecallInitiatePopulationEx(v10, v48, CallbackData->Iopb->TargetFileObject, CallbackData, P, 0, 0, v44);
  }
  if ( !v44 )
  {
LABEL_50:
    v11 = v48;
    goto LABEL_3;
  }
  v4 = 4;
  LODWORD(v9) = HsmiMungeQueryDirectory(CallbackData, a2);
  HsmDbgBreakOnStatus((unsigned int)v9);
  v11 = v48;
LABEL_3:
  if ( P[1] )
    ExFreePoolWithTag(P[1], 0x73557348u);
  if ( (v9 & 0x80000000) != 0LL )
  {
    CallbackData->IoStatus.Status = v9;
    v4 = 4;
    CallbackData->IoStatus.Information = 0;
  }
  else
  {
    if ( !v4 )
    {
      *a3 = v11;
      goto LABEL_8;
    }
    if ( v4 == 2 )
      goto LABEL_8;
  }
  if ( v45 )
    HsmpReleaseUserRequestRundownProtection(v11);
LABEL_8:
  if ( v10 )
    FltReleaseContext(v10);
  if ( v6 && v4 != 2 )
    HsmpTracePreCallbackExit(v4, (_DWORD)CallbackData, *a3, v10 == 0, v10 != 0);
  return v4;
}

```

## disassembly

```asm
0x140061f40  push    rbp
0x140061f42  push    rbx
0x140061f43  push    rsi
0x140061f44  push    rdi
0x140061f45  push    r12
0x140061f47  push    r13
0x140061f49  push    r14
0x140061f4b  push    r15
0x140061f4d  lea     rbp, [rsp-1Fh]
0x140061f52  sub     rsp, 0A8h
0x140061f59  mov     rax, [rdx+20h]
0x140061f5d  mov     r13, rcx
0x140061f60  xor     ecx, ecx
0x140061f62  mov     [rbp+57h+var_80], rax
0x140061f66  mov     [r8], rcx
0x140061f69  xorps   xmm0, xmm0
0x140061f6c  mov     ebx, 1
0x140061f71  mov     [rbp+57h+arg_8], cl
0x140061f74  mov     rax, [r13+10h]
0x140061f78  xor     r14b, r14b
0x140061f7b  movups  xmmword ptr [rbp+57h+P], xmm0
0x140061f7f  mov     r12, r8
0x140061f82  mov     r15, rdx
0x140061f85  mov     edi, ecx
0x140061f87  cmp     [rax+5], bl
0x140061f8a  jz      short loc_140061FFA
0x140061f8c  mov     esi, ecx
0x140061f8e  mov     r15d, ecx
0x140061f91  mov     rcx, [rbp+57h+P+8]; P
0x140061f95  test    rcx, rcx
0x140061f98  jz      short loc_140061FAB
0x140061f9a  mov     edx, 73557348h; Tag
0x140061f9f  call    cs:__imp_ExFreePoolWithTag
0x140061fa6  nop     dword ptr [rax+rax+00h]
0x140061fab  test    edi, edi
0x140061fad  js      loc_140062575
0x140061fb3  test    ebx, ebx
0x140061fb5  jz      short loc_140061FF4
0x140061fb7  cmp     ebx, 2
0x140061fba  jnz     loc_140062241
0x140061fc0  test    rsi, rsi
0x140061fc3  jz      short loc_140061FD4
0x140061fc5  mov     rcx, rsi; Context
0x140061fc8  call    cs:__imp_FltReleaseContext
0x140061fcf  nop     dword ptr [rax+rax+00h]
0x140061fd4  test    r14b, r14b
0x140061fd7  jnz     loc_140062258
0x140061fdd  mov     eax, ebx
0x140061fdf  add     rsp, 0A8h
0x140061fe6  pop     r15
0x140061fe8  pop     r14
0x140061fea  pop     r13
0x140061fec  pop     r12
0x140061fee  pop     rdi
0x140061fef  pop     rsi
0x140061ff0  pop     rbx
0x140061ff1  pop     rbp
0x140061ff2  retn
0x140061ff4  mov     [r12], r15
0x140061ff8  jmp     short loc_140061FC0
0x140061ffa  mov     rax, [rdx+18h]
0x140061ffe  lea     r8, [rbp+57h+Context]; Context
0x140062002  mov     rdx, [rdx+20h]; FileObject
0x140062006  mov     [rbp+57h+Context], rcx
0x14006200a  mov     rcx, rax; Instance
0x14006200d  mov     [rbp+57h+arg_0], rax
0x140062011  call    cs:__imp_FltGetStreamHandleContext
0x140062018  nop     dword ptr [rax+rax+00h]
0x14006201d  mov     rsi, [rbp+57h+Context]
0x140062021  test    rsi, rsi
0x140062024  jz      short loc_140062085
0x140062026  mov     rcx, [rsi+10h]
0x14006202a  mov     eax, [rcx+1Ch]
0x14006202d  test    bl, al
0x14006202f  jz      loc_14006244B
0x140062035  mov     rax, [rcx+10h]
0x140062039  mov     rdx, [rax+10h]
0x14006203d  mov     rax, [rbp+57h+arg_0]
0x140062041  cmp     [rdx+20h], rax
0x140062045  jnz     loc_140062468
0x14006204b  mov     rcx, r13; CallbackData
0x14006204e  call    cs:__imp_FltGetRequestorProcess
0x140062055  nop     dword ptr [rax+rax+00h]
0x14006205a  mov     rcx, rax
0x14006205d  call    HsmOsIsPassThroughModeEnabled
0x140062062  test    al, al
0x140062064  jz      loc_140062470
0x14006206a  mov     rcx, [rbp+57h+Context]; Context
0x14006206e  call    cs:__imp_FltReleaseContext
0x140062075  nop     dword ptr [rax+rax+00h]
0x14006207a  xor     esi, esi
0x14006207c  mov     [rbp+57h+Context], rsi
0x140062080  test    rsi, rsi
0x140062083  jnz     short loc_14006208D
0x140062085  mov     r15, rdi
0x140062088  jmp     loc_140061F91
0x14006208d  mov     rax, [rsi+10h]
0x140062091  mov     [rbp+57h+arg_18], rax
0x140062095  mov     rax, [rax+10h]
0x140062099  mov     [rbp+57h+var_68], rax
0x14006209d  mov     rcx, [rax+10h]
0x1400620a1  mov     rax, [rax+20h]
0x1400620a5  mov     [rbp+57h+var_78], rax
0x1400620a9  mov     rax, [r13+10h]
0x1400620ad  mov     [rbp+57h+var_70], rcx
0x1400620b1  test    byte ptr [rax+6], 8
0x1400620b5  jnz     loc_140062334
0x1400620bb  mov     rcx, r13; CallbackData
0x1400620be  call    cs:__imp_FltGetRequestorProcess
0x1400620c5  nop     dword ptr [rax+rax+00h]
0x1400620ca  mov     rcx, rax
0x1400620cd  call    HsmOsIsSyncProviderProcess
0x1400620d2  movzx   ecx, bl
0x1400620d5  movzx   edx, bl
0x1400620d8  xor     ecx, ecx
0x1400620da  test    al, al
0x1400620dc  cmovnz  edx, ecx
0x1400620df  mov     rax, [r13+10h]
0x1400620e3  mov     dword ptr [rbp+57h+arg_10], edx
0x1400620e6  mov     ecx, [rax+28h]
0x1400620e9  cmp     ecx, 51h ; 'Q'
0x1400620ec  jnz     loc_140062285
0x1400620f2  mov     rcx, r13; jumptable 0000000140062497 cases 1-3,37,38,60,63,78-80
0x1400620f5  call    HsmOsGetPlaceholderCompatMode
0x1400620fa  mov     edx, dword ptr [rbp+57h+arg_10]
0x1400620fd  cmp     al, 2
0x1400620ff  setnz   al
0x140062102  mov     byte ptr [rbp+57h+arg_0], al
0x140062105  test    dl, dl
0x140062107  jz      loc_140062297
0x14006210d  mov     rax, [rsi+10h]
0x140062111  mov     r9, rsi
0x140062114  movzx   r8d, bl
0x140062118  mov     [rsp+0E0h+var_C0], rax
0x14006211d  xor     edx, edx
0x14006211f  mov     rcx, r13
0x140062122  movzx   r14d, bl
0x140062126  call    HsmpTracePreCallbackEnter
0x14006212b  cmp     byte ptr [rbp+57h+arg_10], dil
0x14006212f  jz      loc_140062325
0x140062135  mov     rcx, [rbp+57h+arg_18]; Context
0x140062139  mov     rdx, r13; CallbackData
0x14006213c  call    HsmpAcquireUserRequestRundownProtection
0x140062141  mov     ecx, eax
0x140062143  mov     edi, eax
0x140062145  call    HsmDbgBreakOnStatus
0x14006214a  test    edi, edi
0x14006214c  js      loc_1400623D3
0x140062152  mov     rax, [r13+10h]
0x140062156  xorps   xmm0, xmm0
0x140062159  mov     [rbp+57h+arg_8], bl
0x14006215c  mov     [rbp+57h+FileNameInformation], 0
0x140062164  movups  [rbp+57h+var_60], xmm0
0x140062168  mov     rcx, [rax+8]; FileObject
0x14006216c  mov     rax, [rax+10h]
0x140062170  mov     [rbp+57h+var_78], rax
0x140062174  mov     [rbp+57h+var_80], rcx
0x140062178  test    rcx, rcx
0x14006217b  jz      loc_14006249D
0x140062181  lea     r9, [rbp+57h+FileNameInformation]; FileNameInformation
0x140062185  xor     edx, edx; Instance
0x140062187  mov     r8d, 101h; NameOptions
0x14006218d  call    cs:__imp_FltGetFileNameInformationUnsafe
0x140062194  nop     dword ptr [rax+rax+00h]
0x140062199  mov     ecx, eax
0x14006219b  mov     edi, eax
0x14006219d  call    HsmDbgBreakOnStatus
0x1400621a2  lea     rax, WPP_GLOBAL_Control
0x1400621a9  test    edi, edi
0x1400621ab  js      loc_1400622A4
0x1400621b1  mov     rax, [rbp+57h+FileNameInformation]
0x1400621b5  mov     ecx, 100h
0x1400621ba  mov     r8d, 73557348h
0x1400621c0  movzx   edx, word ptr [rax+8]
0x1400621c4  sub     dx, [rax+18h]
0x1400621c8  xor     eax, eax
0x1400621ca  add     dx, 2
0x1400621ce  mov     word ptr [rbp+57h+var_60], ax
0x1400621d2  movzx   edx, dx
0x1400621d5  mov     word ptr [rbp+57h+var_60+2], dx
0x1400621d9  call    cs:__imp_ExAllocatePool2
0x1400621e0  nop     dword ptr [rax+rax+00h]
0x1400621e5  mov     [rbp+57h+arg_10], rax
0x1400621e9  mov     qword ptr [rbp+57h+var_60+8], rax
0x1400621ed  test    rax, rax
0x1400621f0  jz      loc_1400624F9
0x1400621f6  xor     ecx, ecx
0x1400621f8  call    HsmDbgBreakOnStatus
0x1400621fd  mov     rcx, [rbp+57h+FileNameInformation]
0x140062201  movzx   edx, word ptr [rcx+18h]
0x140062205  movzx   eax, word ptr [rcx+8]
0x140062209  sub     ax, dx
0x14006220c  add     rdx, [rcx+10h]; Src
0x140062210  mov     rcx, [rbp+57h+arg_10]; void *
0x140062214  movzx   edi, ax
0x140062217  mov     r8d, edi; Size
0x14006221a  mov     word ptr [rbp+57h+var_60], di
0x14006221e  call    memmove
0x140062223  mov     rcx, [rbp+57h+arg_10]
0x140062227  xor     eax, eax
0x140062229  movaps  xmm0, [rbp+57h+var_60]
0x14006222d  shr     rdi, 1
0x140062230  mov     [rbp+57h+arg_10], rax
0x140062234  mov     [rcx+rdi*2], ax
0x140062238  xor     edi, edi
0x14006223a  movdqa  xmmword ptr [rbp+57h+P], xmm0
0x14006223f  jmp     short loc_1400622BC
0x140062241  cmp     [rbp+57h+arg_8], 0
0x140062245  jz      loc_140061FC0
0x14006224b  mov     rcx, r15; Context
0x14006224e  call    HsmpReleaseUserRequestRundownProtection
0x140062253  jmp     loc_140061FC0
0x140062258  cmp     ebx, 2
0x14006225b  jz      loc_140061FDD
0x140062261  mov     r8, [r12]
0x140062265  test    rsi, rsi
0x140062268  mov     rdx, r13
0x14006226b  mov     ecx, ebx
0x14006226d  setnz   al
0x140062270  test    rsi, rsi
0x140062273  mov     byte ptr [rsp+0E0h+var_C0], al
0x140062277  setz    r9b
0x14006227b  call    HsmpTracePreCallbackExit
0x140062280  jmp     loc_140061FDD
0x140062285  dec     ecx; switch 80 cases
0x140062287  cmp     ecx, 4Fh
0x14006228a  jbe     loc_140062479
0x140062290  xor     al, al; jumptable 0000000140062497 default case, cases 4-36,39-59,61,62,64-77
0x140062292  jmp     loc_140062102
0x140062297  test    al, al
0x140062299  jz      loc_14006232B
0x14006229f  jmp     loc_14006210D
0x1400622a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400622ab  cmp     rcx, rax
0x1400622ae  jnz     loc_1400624B9
0x1400622b4  mov     rax, qword ptr [rbp+57h+var_60+8]
0x1400622b8  mov     [rbp+57h+arg_10], rax
0x1400622bc  mov     rcx, [rbp+57h+FileNameInformation]; FileNameInformation
0x1400622c0  test    rcx, rcx
0x1400622c3  jz      short loc_1400622D1
0x1400622c5  call    cs:__imp_FltReleaseFileNameInformation
0x1400622cc  nop     dword ptr [rax+rax+00h]
0x1400622d1  mov     rax, [rbp+57h+arg_10]
0x1400622d5  test    rax, rax
0x1400622d8  jnz     loc_14006255C
0x1400622de  mov     ecx, edi
0x1400622e0  call    HsmDbgBreakOnStatus
0x1400622e5  test    edi, edi
0x1400622e7  js      short loc_14006235D
0x1400622e9  mov     r8, [r13+10h]
0x1400622ed  mov     r9, r13
0x1400622f0  movzx   eax, byte ptr [rbp+57h+arg_0]
0x1400622f4  mov     rcx, rsi
0x1400622f7  mov     rdx, [rbp+57h+arg_18]
0x1400622fb  mov     dword ptr [rsp+0E0h+var_A8], eax
0x1400622ff  lea     rax, [rbp+57h+P]
0x140062303  mov     r8, [r8+8]
0x140062307  mov     [rsp+0E0h+var_B0], 0
0x140062310  mov     [rsp+0E0h+var_B8], 0
0x140062319  mov     [rsp+0E0h+var_C0], rax
0x14006231e  call    HsmpRecallInitiatePopulationEx
0x140062323  mov     ebx, eax
0x140062325  cmp     byte ptr [rbp+57h+arg_0], 0
0x140062329  jnz     short loc_14006233B
0x14006232b  mov     r15, [rbp+57h+arg_18]
0x14006232f  jmp     loc_140061F91
0x140062334  xor     dl, dl
0x140062336  jmp     loc_1400620DF
0x14006233b  mov     rdx, r15
0x14006233e  mov     rcx, r13; CallbackData
0x140062341  mov     ebx, 4
0x140062346  call    HsmiMungeQueryDirectory
0x14006234b  mov     ecx, eax
0x14006234d  mov     edi, eax
0x14006234f  call    HsmDbgBreakOnStatus
0x140062354  mov     r15, [rbp+57h+arg_18]
0x140062358  jmp     loc_140061F91
0x14006235d  mov     rcx, cs:WPP_GLOBAL_Control
0x140062364  lea     rax, WPP_GLOBAL_Control
0x14006236b  cmp     rcx, rax
0x14006236e  jz      short loc_14006232B
0x140062370  mov     eax, [rcx+2Ch]
0x140062373  test    bl, al
0x140062375  jz      short loc_14006232B
0x140062377  cmp     byte ptr [rcx+29h], 2
0x14006237b  mov     r15, [rbp+57h+arg_18]
0x14006237f  jb      loc_140061F91
0x140062385  mov     r8, [r13+10h]
0x140062389  mov     edx, 13h
0x14006238e  mov     rax, [rbp+57h+var_68]
0x140062392  mov     r9, [rbp+57h+var_70]
0x140062396  mov     rcx, [rcx+18h]
0x14006239a  mov     [rsp+0E0h+var_98], edi
0x14006239e  mov     rax, [rax+20h]
0x1400623a2  mov     [rsp+0E0h+var_A0], r13
0x1400623a7  mov     [rsp+0E0h+var_A8], rax
0x1400623ac  mov     rax, [r8+8]
0x1400623b0  lea     r8, WPP_3a0b160e0a683f3dea1866dfb9c0f226_Traceguids
0x1400623b7  mov     [rsp+0E0h+var_B0], rax
0x1400623bc  mov     eax, [r15+1Ch]
  ... truncated ...
```
