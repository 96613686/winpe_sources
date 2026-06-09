# FTPreOpCallback

- ea: `0x140002110`
- end: `0x140002926`
- name: `FTPreOpCallback`
- size: `2070`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140002110`
- `0x140003510`
- `0x140003550`
- `0x140003600`
- `0x140003900`
- `0x14000bcd8`
- `0x14000c8b8`
- `0x14000c95c`
- `0x14000cecc`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x14000218f`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14000218f`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400021df`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140002729`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400021df`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140002729`
- `ntoskrnl!PsGetProcessWin32WindowStation` at `0x1400023d3`
- `ntoskrnl!PsGetProcessWin32WindowStation` at `0x1400023d3`
- `ntoskrnl!PsGetProcessSessionId` at `0x140002383`
- `ntoskrnl!PsGetProcessSessionId` at `0x140002383`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400028f9`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000290f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140003fb3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140003fca`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400028f9`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000290f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140003fb3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140003fca`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14000261f`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140002814`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14000261f`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140002814`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400026c7`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000282c`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400026c7`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000282c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002881`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000289a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400028bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400028e1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003f24`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003f3f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003f76`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003f9b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002881`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000289a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400028bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400028e1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003f24`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003f3f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003f76`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003f9b`
- `ntoskrnl!ExAllocatePool2` at `0x1400026fd`
- `ntoskrnl!ExAllocatePool2` at `0x1400026fd`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400027fe`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400027fe`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140002847`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140003ee9`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140002847`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140003ee9`
- `FLTMGR!FltGetFileNameInformation` at `0x1400025e3`
- `FLTMGR!FltGetFileNameInformation` at `0x1400025e3`
- `FLTMGR!FltIsDirectory` at `0x1400027b4`
- `FLTMGR!FltIsDirectory` at `0x1400027b4`
- `FLTMGR!FltReleaseContext` at `0x140002866`
- `FLTMGR!FltReleaseContext` at `0x140003f09`
- `FLTMGR!FltReleaseContext` at `0x140002866`
- `FLTMGR!FltReleaseContext` at `0x140003f09`
- `FLTMGR!FltGetRequestorProcess` at `0x14000236f`
- `FLTMGR!FltGetRequestorProcess` at `0x1400023bf`
- `FLTMGR!FltGetRequestorProcess` at `0x14000236f`
- `FLTMGR!FltGetRequestorProcess` at `0x1400023bf`
- `FLTMGR!FltGetVolumeContext` at `0x140002239`
- `FLTMGR!FltGetVolumeContext` at `0x140002239`

## pseudocode

```c
__int64 __fastcall FTPreOpCallback(PFLT_CALLBACK_DATA CallbackData, __int64 a2, PUNICODE_STRING *a3)
{
  int v6; // r12d
  unsigned int v7; // r14d
  char v8; // r15
  void *v9; // rbx
  struct _UNICODE_STRING *v11; // rax
  int v12; // r10d
  int v13; // r9d
  _DWORD *v14; // rdx
  int v15; // eax
  int v16; // r8d
  int ProcessSessionId; // r15d
  PEPROCESS RequestorProcess; // rax
  PEPROCESS v19; // rax
  ULONG IrpFlags; // edx
  PVOID v21; // rcx
  _DWORD *v22; // r8
  int v23; // edx
  __int64 v24; // r15
  NTSTATUS v25; // ebx
  PWSTR v26; // rcx
  unsigned __int16 v27; // ax
  WCHAR v28; // ax
  int v29; // eax
  __int64 Length; // rcx
  PUNICODE_STRING v31; // rbx
  _BYTE *v32; // rcx
  _BYTE *v33; // rcx
  PFLT_IO_PARAMETER_BLOCK Iopb; // rcx
  bool v35; // sf
  unsigned __int8 v36; // al
  void *v37; // rcx
  _BYTE *v38; // rcx
  unsigned __int8 IsDirectory[4]; // [rsp+20h] [rbp-108h] BYREF
  int v40; // [rsp+24h] [rbp-104h]
  void *v41; // [rsp+28h] [rbp-100h] BYREF
  char v42; // [rsp+30h] [rbp-F8h]
  int v43; // [rsp+34h] [rbp-F4h]
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+38h] [rbp-F0h] BYREF
  UNICODE_STRING Source; // [rsp+40h] [rbp-E8h] BYREF
  int v46; // [rsp+50h] [rbp-D8h] BYREF
  int v47; // [rsp+54h] [rbp-D4h] BYREF
  int v48; // [rsp+58h] [rbp-D0h]
  PFLT_CONTEXT Context; // [rsp+60h] [rbp-C8h] BYREF
  PVOID P; // [rsp+68h] [rbp-C0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-B8h] BYREF
  unsigned int MajorFunction; // [rsp+80h] [rbp-A8h]
  int v53; // [rsp+84h] [rbp-A4h]
  NTSTATUS v54; // [rsp+88h] [rbp-A0h]
  WCHAR *v55; // [rsp+90h] [rbp-98h] BYREF
  PWSTR v56; // [rsp+98h] [rbp-90h]
  int v57; // [rsp+A0h] [rbp-88h]
  PUNICODE_STRING *v58; // [rsp+A8h] [rbp-80h]
  __int64 v59; // [rsp+B0h] [rbp-78h]
  char v60; // [rsp+B8h] [rbp-70h] BYREF
  char v61; // [rsp+D0h] [rbp-58h] BYREF

  *(_QWORD *)&Source.Length = a2;
  v58 = a3;
  v43 = -1;
  v6 = 0;
  *(_QWORD *)&DestinationString.Length = 0;
  v7 = 0;
  v40 = 0;
  v8 = 0;
  Context = 0;
  FileNameInformation = 0;
  v55 = 0;
  v46 = 0;
  P = 0;
  v47 = 0;
  v9 = 0;
  v41 = 0;
  if ( IoGetTopLevelIrp() )
    return 1;
  MajorFunction = CallbackData->Iopb->MajorFunction;
  v11 = (struct _UNICODE_STRING *)ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)&WmiRegistrationContext.Reserved);
  *a3 = v11;
  if ( !v11
    || (memset(v11, 0, 0x110u),
        (*a3)->Buffer = &(*a3)[1].Length,
        (*a3)->MaximumLength = 48,
        FltGetVolumeContext((PFLT_FILTER)WmiRegistrationContext.SecurityDescriptor, *(PFLT_VOLUME *)(a2 + 16), &Context) < 0) )
  {
    v7 = 1;
    v40 = 1;
    goto LABEL_92;
  }
  v12 = 0;
  v48 = 0;
  while ( 1 )
  {
    v53 = v6;
    if ( v6 >= 8 )
      break;
    v13 = *((_DWORD *)LogSessions + 10 * v6 + 3);
    if ( !v13 )
      goto LABEL_59;
    v14 = LogSessions;
    v15 = *((_DWORD *)LogSessions + 10 * v6 + 5);
    if ( !_bittest(&v15, MajorFunction) )
      goto LABEL_59;
    v16 = *((_DWORD *)LogSessions + 10 * v6 + 8);
    if ( (v16 & 0x4000000) == 0 && (v16 & *((_DWORD *)Context + 120)) == 0 )
      goto LABEL_59;
    if ( (CallbackData->Iopb->IrpFlags & 2) != 0 && (*((_DWORD *)LogSessions + 10 * v6 + 7) & 0x100) != 0 )
      goto LABEL_59;
    *((_DWORD *)&(*a3)[13].Length + 2 * v12) = v6;
    *((_DWORD *)&(*a3)[12].Buffer + 2 * v12 + 1) = v13;
    v48 = v12 + 1;
    LODWORD((*a3)[12].Buffer) = v12 + 1;
    if ( (CallbackData->Iopb->IrpFlags & 2) == 0 && (v14[10 * v6 + 7] & 4) != 0 )
    {
      if ( !v55 )
        GetLastAccessTime(CallbackData, *(_QWORD *)&Source.Length, &v55);
      (*a3)[5].Buffer = v55;
    }
    if ( (*((_DWORD *)LogSessions + 10 * v6 + 7) & 2) != 0 )
    {
      ProcessSessionId = v43;
      if ( v43 == -1 )
      {
        ProcessSessionId = -1;
        v43 = -1;
        RequestorProcess = FltGetRequestorProcess(CallbackData);
        if ( RequestorProcess )
        {
          ProcessSessionId = PsGetProcessSessionId(RequestorProcess);
          v43 = ProcessSessionId;
        }
        v57 = ProcessSessionId;
      }
      LODWORD((*a3)[6].Buffer) = ProcessSessionId;
    }
    if ( (*((_DWORD *)LogSessions + 10 * v6 + 7) & 0x80u) != 0 )
    {
      if ( !*(_QWORD *)&DestinationString.Length )
      {
        v19 = FltGetRequestorProcess(CallbackData);
        if ( v19 )
        {
          *(_QWORD *)&DestinationString.Length = PsGetProcessWin32WindowStation(v19);
          v59 = *(_QWORD *)&DestinationString.Length;
        }
      }
      *(_QWORD *)&(*a3)[7].Length = *(_QWORD *)&DestinationString.Length;
    }
    IrpFlags = CallbackData->Iopb->IrpFlags;
    if ( (IrpFlags & 2) == 0 )
    {
      if ( GlobalLateBoundFunctions )
      {
        if ( !(unsigned __int8)GlobalLateBoundFunctions() )
          goto LABEL_35;
        IrpFlags = CallbackData->Iopb->IrpFlags;
      }
      if ( (IrpFlags & 2) == 0 )
      {
LABEL_35:
        if ( (*((_DWORD *)LogSessions + 10 * v6 + 7) & 1) != 0 )
        {
          if ( !*(_QWORD *)&(*a3)[8].Length )
            GetUserSidAndAcessToken(CallbackData);
          LODWORD((*a3)[9].Buffer) |= 1 << v6;
        }
      }
    }
    if ( (*((_DWORD *)LogSessions + 10 * v6 + 7) & 8) != 0 )
    {
      v21 = P;
      if ( !P )
      {
        CreateParameterBlob(CallbackData, &v46, &P);
        v21 = P;
      }
      *(_QWORD *)&(*a3)[10].Length = v21;
      LODWORD((*a3)[10].Buffer) = v46;
    }
    if ( (CallbackData->Iopb->IrpFlags & 2) == 0 && (*((_DWORD *)LogSessions + 10 * v6 + 7) & 0x20) != 0 )
    {
      if ( !v41 )
        GetPreviousValue(CallbackData, *(_QWORD *)&Source.Length, &v47, &v41);
      *(_QWORD *)&(*a3)[11].Length = v41;
      LODWORD((*a3)[11].Buffer) = v47;
    }
    v22 = LogSessions;
    v23 = 1 << v6;
    if ( (*((_DWORD *)LogSessions + 10 * v6 + 7) & 4) != 0 )
      *(_DWORD *)&(*a3)[6].Length |= v23;
    if ( (v22[10 * v6 + 7] & 2) != 0 )
    {
      v23 = 1 << v6;
      HIDWORD((*a3)[6].Buffer) |= 1 << v6;
    }
    if ( (v22[10 * v6 + 7] & 0x80u) != 0 )
      LODWORD((*a3)[7].Buffer) |= v23;
    if ( (v22[10 * v6 + 7] & 8) != 0 )
      HIDWORD((*a3)[10].Buffer) |= v23;
    if ( (v22[10 * v6 + 7] & 0x20) != 0 )
      HIDWORD((*a3)[11].Buffer) |= v23;
    v8 = 1;
    v42 = 1;
    v12 = v48;
LABEL_59:
    ++v6;
  }
  if ( !v8 )
    goto LABEL_61;
  *(_QWORD *)&(*a3)[12].Length = Context;
  LOBYTE((*a3)[4].Buffer) = 2;
  *(_QWORD *)&(*a3)[4].Length = MEMORY[0xFFFFF78000000014];
  v24 = *(_QWORD *)&Source.Length;
  if ( !*(_QWORD *)(*(_QWORD *)&Source.Length + 32LL) )
  {
    *(_QWORD *)&DestinationString.Length = 0;
    DestinationString.Buffer = (PWSTR)&v61;
    RtlInitUnicodeString(&DestinationString, L"0x00000000");
    if ( RtlAppendUnicodeToString(*a3, L":00000001-") >= 0 )
      RtlAppendUnicodeStringToString(*a3, &DestinationString);
    goto LABEL_91;
  }
  v25 = FltGetFileNameInformation(CallbackData, dword_140007244 | 1, &FileNameInformation);
  if ( v25 >= 0 )
  {
    Length = FileNameInformation->Name.Length;
    v31 = *a3;
    if ( (unsigned __int16)Length <= 0x7FFu )
    {
      *(_QWORD *)&v31[5].Length = ExAllocateFromNPagedLookasideList(&Lookaside);
      v33 = *(_BYTE **)&(*a3)[5].Length;
      if ( v33 )
      {
        *v33 = 0;
        goto LABEL_82;
      }
    }
    else
    {
      *(_QWORD *)&v31[5].Length = ExAllocatePool2(66, Length + 24, 1920224326);
      v32 = *(_BYTE **)&(*a3)[5].Length;
      if ( v32 )
      {
        *v32 = 1;
LABEL_82:
        *(UNICODE_STRING *)(*(_QWORD *)&(*a3)[5].Length + 8LL) = FileNameInformation->Name;
        memmove(
          (void *)(*(_QWORD *)&(*a3)[5].Length + 24LL),
          FileNameInformation->Name.Buffer,
          FileNameInformation->Name.Length);
        *(_QWORD *)(*(_QWORD *)&(*a3)[5].Length + 16LL) = *(_QWORD *)&(*a3)[5].Length + 24LL;
        goto LABEL_83;
      }
    }
LABEL_61:
    v7 = 1;
    v40 = 1;
    goto LABEL_91;
  }
  *(_QWORD *)&Source.Length = 1179648;
  Source.Buffer = (PWSTR)&v60;
  if ( RtlAppendUnicodeToString(*a3, L":00000000-") >= 0 )
  {
    v54 = v25;
    v56 = 0;
    if ( !Source.Buffer || Source.Length || Source.MaximumLength < 0x12u )
    {
      v29 = -1073741811;
    }
    else
    {
      v26 = Source.Buffer + 8;
      v56 = Source.Buffer + 8;
      Source.Buffer[8] = 0;
      do
      {
        v27 = v25 & 0xF;
        if ( v27 <= 9u )
          v28 = v27 + 48;
        else
          v28 = v27 + 55;
        v56 = --v26;
        *v26 = v28;
        v25 = (unsigned int)v25 >> 4;
        v54 = v25;
      }
      while ( v25 );
      Source.Length = 18;
      v29 = 0;
    }
    if ( v29 >= 0 )
      RtlAppendUnicodeStringToString(*a3, &Source);
  }
LABEL_83:
  Iopb = CallbackData->Iopb;
  if ( (Iopb->IrpFlags & 2) != 0 || !*(_QWORD *)(*(_QWORD *)(v24 + 32) + 24LL) )
  {
    LOBYTE((*a3)[4].Buffer) = 3;
  }
  else
  {
    IsDirectory[0] = 0;
    v35 = FltIsDirectory(Iopb->TargetFileObject, *(PFLT_INSTANCE *)(v24 + 24), IsDirectory) < 0;
    v36 = 4;
    if ( !v35 )
      v36 = IsDirectory[0];
    LOBYTE((*a3)[4].Buffer) = v36;
  }
LABEL_91:
  v9 = v41;
LABEL_92:
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  if ( v7 == 1 )
  {
    if ( Context )
      FltReleaseContext(Context);
    if ( P )
      ExFreePoolWithTag(P, 0x72744C46u);
    if ( v9 )
      ExFreePoolWithTag(v9, 0x72744C46u);
    if ( *a3 )
    {
      v37 = *(void **)&(*a3)[9].Length;
      if ( v37 )
        ExFreePoolWithTag(v37, 0x72744C46u);
      v38 = *(_BYTE **)&(*a3)[5].Length;
      if ( v38 )
      {
        if ( *v38 == 1 )
          ExFreePoolWithTag(v38, 0x72744C46u);
        else
          ExFreeToNPagedLookasideList(&Lookaside, *(PVOID *)&(*a3)[5].Length);
      }
      ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)&WmiRegistrationContext.Reserved, *a3);
      *a3 = 0;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x140002110  push    rbx
0x140002112  push    rsi
0x140002113  push    rdi
0x140002114  push    r12
0x140002116  push    r13
0x140002118  push    r14
0x14000211a  push    r15
0x14000211c  sub     rsp, 0F0h
0x140002123  mov     rax, cs:WmiRegistrationContext.DeviceExtension
0x14000212a  xor     rax, rsp
0x14000212d  mov     [rsp+128h+var_40], rax
0x140002135  mov     rdi, r8
0x140002138  mov     rsi, rdx
0x14000213b  mov     qword ptr [rsp+128h+Source.Length], rdx
0x140002140  mov     r13, rcx
0x140002143  mov     [rsp+128h+var_80], r8
0x14000214b  mov     [rsp+128h+var_F4], 0FFFFFFFFh
0x140002153  xor     r12d, r12d
0x140002156  mov     qword ptr [rsp+128h+DestinationString.Length], r12
0x14000215b  mov     r14d, r12d
0x14000215e  mov     [rsp+128h+var_104], r12d
0x140002163  mov     r15b, r12b
0x140002166  mov     [rsp+128h+Context], r12
0x14000216b  mov     [rsp+128h+FileNameInformation], r12
0x140002170  mov     [rsp+128h+var_98], r12
0x140002178  mov     [rsp+128h+var_D8], r12d
0x14000217d  mov     [rsp+128h+P], r12
0x140002182  mov     [rsp+128h+var_D4], r12d
0x140002187  mov     ebx, r12d
0x14000218a  mov     [rsp+128h+var_100], rbx
0x14000218f  call    cs:__imp_IoGetTopLevelIrp
0x140002196  nop     dword ptr [rax+rax+00h]
0x14000219b  test    rax, rax
0x14000219e  jz      short loc_1400021C9
0x1400021a0  lea     eax, [r12+1]
0x1400021a5  mov     rcx, [rsp+128h+var_40]
0x1400021ad  xor     rcx, rsp; StackCookie
0x1400021b0  call    __security_check_cookie
0x1400021b5  add     rsp, 0F0h
0x1400021bc  pop     r15
0x1400021be  pop     r14
0x1400021c0  pop     r13
0x1400021c2  pop     r12
0x1400021c4  pop     rdi
0x1400021c5  pop     rsi
0x1400021c6  pop     rbx
0x1400021c7  retn
0x1400021c9  mov     rax, [r13+10h]
0x1400021cd  movzx   eax, byte ptr [rax+4]
0x1400021d1  mov     [rsp+128h+var_A8], eax
0x1400021d8  lea     rcx, WmiRegistrationContext.Reserved; Lookaside
0x1400021df  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400021e6  nop     dword ptr [rax+rax+00h]
0x1400021eb  mov     [rdi], rax
0x1400021ee  test    rax, rax
0x1400021f1  jnz     short loc_140002202
0x1400021f3  lea     esi, [rax+1]
0x1400021f6  mov     r14d, esi
0x1400021f9  mov     [rsp+128h+var_104], esi
0x1400021fd  jmp     loc_14000283D
0x140002202  xor     edx, edx; Val
0x140002204  mov     r8d, 110h; Size
0x14000220a  mov     rcx, rax; void *
0x14000220d  call    memset
0x140002212  mov     rcx, [rdi]
0x140002215  lea     rax, [rcx+10h]
0x140002219  mov     [rcx+8], rax
0x14000221d  mov     rax, [rdi]
0x140002220  mov     ecx, 30h ; '0'
0x140002225  mov     [rax+2], cx
0x140002229  lea     r8, [rsp+128h+Context]; Context
0x14000222e  mov     rdx, [rsi+10h]; Volume
0x140002232  mov     rcx, cs:WmiRegistrationContext.SecurityDescriptor; Filter
0x140002239  call    cs:__imp_FltGetVolumeContext
0x140002240  nop     dword ptr [rax+rax+00h]
0x140002245  mov     esi, 1
0x14000224a  test    eax, eax
0x14000224c  js      short loc_1400021F6
0x14000224e  mov     r10d, r12d
0x140002251  mov     [rsp+128h+var_D0], r12d
0x140002256  lea     r11d, [rsi+3]
0x14000225a  mov     [rsp+128h+var_A4], r12d
0x140002262  cmp     r12d, 8
0x140002266  jge     loc_140002586
0x14000226c  movsxd  rax, r12d
0x14000226f  lea     rbx, [rax+rax*4]
0x140002273  mov     rax, cs:LogSessions
0x14000227a  mov     r9d, [rax+rbx*8+0Ch]
0x14000227f  test    r9d, r9d
0x140002282  jz      loc_14000257E
0x140002288  mov     rdx, cs:LogSessions
0x14000228f  mov     eax, [rdx+rbx*8+14h]
0x140002293  mov     ecx, [rsp+128h+var_A8]
0x14000229a  bt      eax, ecx
0x14000229d  jnb     loc_14000257E
0x1400022a3  mov     r8d, [rdx+rbx*8+20h]
0x1400022a8  bt      r8d, 1Ah
0x1400022ad  jb      short loc_1400022C1
0x1400022af  mov     rax, [rsp+128h+Context]
0x1400022b4  test    [rax+1E0h], r8d
0x1400022bb  jz      loc_14000257E
0x1400022c1  mov     rax, [r13+10h]
0x1400022c5  mov     ecx, [rax]
0x1400022c7  test    cl, 2
0x1400022ca  jz      short loc_1400022DA
0x1400022cc  mov     eax, [rdx+rbx*8+1Ch]
0x1400022d0  bt      eax, 8
0x1400022d4  jb      loc_14000257E
0x1400022da  movsxd  rcx, r10d
0x1400022dd  mov     rax, [rdi]
0x1400022e0  mov     [rax+rcx*8+0D0h], r12d
0x1400022e8  mov     rax, [rdi]
0x1400022eb  mov     [rax+rcx*8+0CCh], r9d
0x1400022f3  add     r10d, esi
0x1400022f6  mov     [rsp+128h+var_D0], r10d
0x1400022fb  mov     rax, [rdi]
0x1400022fe  mov     [rax+0C8h], r10d
0x140002305  mov     rax, [r13+10h]
0x140002309  mov     ecx, [rax]
0x14000230b  test    cl, 2
0x14000230e  jnz     short loc_140002348
0x140002310  mov     eax, [rdx+rbx*8+1Ch]
0x140002314  test    r11b, al
0x140002317  jz      short loc_140002348
0x140002319  cmp     [rsp+128h+var_98], 0
0x140002322  jnz     short loc_140002339
0x140002324  lea     r8, [rsp+128h+var_98]
0x14000232c  mov     rdx, qword ptr [rsp+128h+Source.Length]
0x140002331  mov     rcx, r13
0x140002334  call    GetLastAccessTime
0x140002339  mov     rax, [rdi]
0x14000233c  mov     rcx, [rsp+128h+var_98]
0x140002344  mov     [rax+58h], rcx
0x140002348  mov     rax, cs:LogSessions
0x14000234f  mov     ecx, [rax+rbx*8+1Ch]
0x140002353  test    cl, 2
0x140002356  jz      short loc_1400023A5
0x140002358  mov     r15d, [rsp+128h+var_F4]
0x14000235d  or      eax, 0FFFFFFFFh
0x140002360  cmp     r15d, eax
0x140002363  jnz     short loc_14000239E
0x140002365  mov     r15d, eax
0x140002368  mov     [rsp+128h+var_F4], eax
0x14000236c  mov     rcx, r13; CallbackData
0x14000236f  call    cs:__imp_FltGetRequestorProcess
0x140002376  nop     dword ptr [rax+rax+00h]
0x14000237b  test    rax, rax
0x14000237e  jz      short loc_140002396
0x140002380  mov     rcx, rax
0x140002383  call    cs:__imp_PsGetProcessSessionId
0x14000238a  nop     dword ptr [rax+rax+00h]
0x14000238f  mov     r15d, eax
0x140002392  mov     [rsp+128h+var_F4], eax
0x140002396  mov     [rsp+128h+var_88], r15d
0x14000239e  mov     rcx, [rdi]
0x1400023a1  mov     [rcx+68h], r15d
0x1400023a5  mov     rcx, cs:LogSessions
0x1400023ac  mov     edx, [rcx+rbx*8+1Ch]
0x1400023b0  test    dl, dl
0x1400023b2  jns     short loc_1400023F8
0x1400023b4  cmp     qword ptr [rsp+128h+DestinationString.Length], 0
0x1400023ba  jnz     short loc_1400023EC
0x1400023bc  mov     rcx, r13; CallbackData
0x1400023bf  call    cs:__imp_FltGetRequestorProcess
0x1400023c6  nop     dword ptr [rax+rax+00h]
0x1400023cb  test    rax, rax
0x1400023ce  jz      short loc_1400023EC
0x1400023d0  mov     rcx, rax
0x1400023d3  call    cs:__imp_PsGetProcessWin32WindowStation
0x1400023da  nop     dword ptr [rax+rax+00h]
0x1400023df  mov     qword ptr [rsp+128h+DestinationString.Length], rax
0x1400023e4  mov     [rsp+128h+var_78], rax
0x1400023ec  mov     rcx, [rdi]
0x1400023ef  mov     rax, qword ptr [rsp+128h+DestinationString.Length]
0x1400023f4  mov     [rcx+70h], rax
0x1400023f8  mov     rcx, [r13+10h]
0x1400023fc  mov     edx, [rcx]
0x1400023fe  test    dl, 2
0x140002401  jnz     short loc_140002469
0x140002403  mov     rax, cs:GlobalLateBoundFunctions
0x14000240a  test    rax, rax
0x14000240d  jz      short loc_14000241E
0x14000240f  call    _guard_dispatch_icall
0x140002414  test    al, al
0x140002416  jz      short loc_140002423
0x140002418  mov     rax, [r13+10h]
0x14000241c  mov     edx, [rax]
0x14000241e  test    dl, 2
0x140002421  jnz     short loc_140002469
0x140002423  mov     rax, cs:LogSessions
0x14000242a  mov     ecx, [rax+rbx*8+1Ch]
0x14000242e  test    sil, cl
0x140002431  jz      short loc_140002469
0x140002433  mov     rdx, [rdi]
0x140002436  lea     r9, [rdx+80h]
0x14000243d  cmp     qword ptr [r9], 0
0x140002441  jnz     short loc_140002459
0x140002443  lea     r8, [rdx+90h]
0x14000244a  add     rdx, 88h
0x140002451  mov     rcx, r13; CallbackData
0x140002454  call    GetUserSidAndAcessToken
0x140002459  mov     rdx, [rdi]
0x14000245c  mov     ecx, r12d
0x14000245f  mov     eax, esi
0x140002461  shl     eax, cl
0x140002463  or      [rdx+98h], eax
0x140002469  mov     rax, cs:LogSessions
0x140002470  mov     ecx, [rax+rbx*8+1Ch]
0x140002474  test    cl, 8
0x140002477  jz      short loc_1400024B1
0x140002479  mov     rcx, [rsp+128h+P]
0x14000247e  test    rcx, rcx
0x140002481  jnz     short loc_14000249A
0x140002483  lea     r8, [rsp+128h+P]
0x140002488  lea     rdx, [rsp+128h+var_D8]
0x14000248d  mov     rcx, r13
0x140002490  call    CreateParameterBlob
0x140002495  mov     rcx, [rsp+128h+P]
0x14000249a  mov     rax, [rdi]
0x14000249d  mov     [rax+0A0h], rcx
0x1400024a4  mov     rcx, [rdi]
0x1400024a7  mov     eax, [rsp+128h+var_D8]
0x1400024ab  mov     [rcx+0A8h], eax
0x1400024b1  mov     rax, [r13+10h]
0x1400024b5  mov     ecx, [rax]
0x1400024b7  test    cl, 2
0x1400024ba  jnz     short loc_140002507
0x1400024bc  mov     rax, cs:LogSessions
0x1400024c3  mov     ecx, [rax+rbx*8+1Ch]
0x1400024c7  test    cl, 20h
0x1400024ca  jz      short loc_140002507
0x1400024cc  cmp     [rsp+128h+var_100], 0
0x1400024d2  jnz     short loc_1400024EB
0x1400024d4  lea     r9, [rsp+128h+var_100]
0x1400024d9  lea     r8, [rsp+128h+var_D4]
0x1400024de  mov     rdx, qword ptr [rsp+128h+Source.Length]
0x1400024e3  mov     rcx, r13
0x1400024e6  call    GetPreviousValue
0x1400024eb  mov     rax, [rdi]
0x1400024ee  mov     rcx, [rsp+128h+var_100]
0x1400024f3  mov     [rax+0B0h], rcx
0x1400024fa  mov     rax, [rdi]
0x1400024fd  mov     ecx, [rsp+128h+var_D4]
0x140002501  mov     [rax+0B8h], ecx
0x140002507  mov     r8, cs:LogSessions
0x14000250e  mov     ecx, r12d
0x140002511  mov     edx, esi
0x140002513  shl     edx, cl
0x140002515  mov     eax, [r8+rbx*8+1Ch]
0x14000251a  mov     r11d, 4
0x140002520  test    r11b, al
0x140002523  jz      short loc_14000252B
0x140002525  mov     rax, [rdi]
0x140002528  or      [rax+60h], edx
0x14000252b  mov     eax, [r8+rbx*8+1Ch]
0x140002530  test    al, 2
0x140002532  jz      short loc_14000253E
0x140002534  mov     edx, esi
0x140002536  shl     edx, cl
0x140002538  mov     rax, [rdi]
0x14000253b  or      [rax+6Ch], edx
0x14000253e  mov     eax, [r8+rbx*8+1Ch]
0x140002543  test    al, al
0x140002545  jns     short loc_14000254D
0x140002547  mov     rax, [rdi]
0x14000254a  or      [rax+78h], edx
0x14000254d  mov     eax, [r8+rbx*8+1Ch]
0x140002552  test    al, 8
0x140002554  jz      short loc_14000255F
0x140002556  mov     rax, [rdi]
0x140002559  or      [rax+0ACh], edx
0x14000255f  mov     eax, [r8+rbx*8+1Ch]
0x140002564  test    al, 20h
0x140002566  jz      short loc_140002571
0x140002568  mov     rax, [rdi]
0x14000256b  or      [rax+0BCh], edx
0x140002571  mov     r15b, sil
0x140002574  mov     [rsp+128h+var_F8], sil
0x140002579  mov     r10d, [rsp+128h+var_D0]
0x14000257e  add     r12d, esi
0x140002581  jmp     loc_14000225A
0x140002586  xor     r12d, r12d
0x140002589  test    r15b, r15b
0x14000258c  jnz     short loc_14000259A
0x14000258e  mov     r14d, esi
0x140002591  mov     [rsp+128h+var_104], esi
0x140002595  jmp     loc_140002838
0x14000259a  mov     rcx, [rdi]
0x14000259d  mov     rax, [rsp+128h+Context]
0x1400025a2  mov     [rcx+0C0h], rax
0x1400025a9  mov     rax, [rdi]
0x1400025ac  mov     byte ptr [rax+48h], 2
0x1400025b0  mov     rax, 0FFFFF78000000014h
0x1400025ba  mov     rax, [rax]
0x1400025bd  mov     rcx, [rdi]
0x1400025c0  mov     [rcx+40h], rax
0x1400025c4  mov     r15, qword ptr [rsp+128h+Source.Length]
0x1400025c9  cmp     [r15+20h], r12
0x1400025cd  jz      loc_1400027E0
0x1400025d3  mov     edx, cs:dword_140007244
  ... truncated ...
```
