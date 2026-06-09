# HsmiFileCacheIrpRead

- ea: `0x140006440`
- end: `0x140006b6f`
- name: `HsmiFileCacheIrpRead`
- size: `1839`
- prototype: `__int64 __fastcall(__int64, IRP *, __int64)`
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x140003c50`
- `0x1400054c0`
- `0x140006440`
- `0x140009300`
- `0x14000c12c`
- `0x14000d95c`
- `0x14000dd64`
- `0x140010644`
- `0x14001c8d8`
- `0x14001c988`
- `0x14001ca30`
- `0x14001caa4`
- `0x14001cb00`
- `0x14001d024`
- `0x14001d214`
- `0x14001e2a0`

## import_xrefs

- `ntoskrnl!IoIsOperationSynchronous` at `0x14000656d`
- `ntoskrnl!IoIsOperationSynchronous` at `0x14000656d`
- `ntoskrnl!IofCompleteRequest` at `0x14000670d`
- `ntoskrnl!IofCompleteRequest` at `0x14000670d`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140006a93`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140006a93`
- `FLTMGR!FltPerformSynchronousIo` at `0x1400068b7`
- `FLTMGR!FltPerformSynchronousIo` at `0x1400068b7`
- `FLTMGR!FltFreeCallbackData` at `0x1400066ed`
- `FLTMGR!FltFreeCallbackData` at `0x1400066ed`
- `FLTMGR!FltAllocateCallbackData` at `0x1400067d8`
- `FLTMGR!FltAllocateCallbackData` at `0x1400067d8`

## pseudocode

```c
__int64 __fastcall HsmiFileCacheIrpRead(__int64 a1, IRP *a2, __int64 a3)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r15
  unsigned int Information; // r13d
  PFILE_OBJECT FileObject; // rbx
  NTSTATUS Status; // edi
  PDEVICE_OBJECT v8; // rcx
  __int64 v9; // rdx
  PMDL MdlAddress; // r9
  __int64 v11; // r8
  BOOLEAN IsOperationSynchronous; // al
  ULONG Flags; // r9d
  LARGE_INTEGER *v14; // r14
  int v15; // edi
  LARGE_INTEGER ByteOffset; // rbx
  __int64 Length; // r15
  char v18; // cl
  LARGE_INTEGER v19; // r12
  __int64 v20; // r9
  __int64 v21; // r8
  DWORD v23; // r12d
  __int64 v24; // r8
  PDEVICE_OBJECT v25; // rcx
  __int64 v26; // rdx
  PMDL v27; // rcx
  PVOID MappedSystemVa; // r9
  __int64 v29; // r8
  __int64 v30; // r9
  int BugCheckOnFailure; // [rsp+20h] [rbp-40h]
  int Priority; // [rsp+28h] [rbp-38h]
  int v33; // [rsp+30h] [rbp-30h]
  LARGE_INTEGER *v34; // [rsp+50h] [rbp-10h] BYREF
  bool v35; // [rsp+A8h] [rbp+48h]
  char v36; // [rsp+B0h] [rbp+50h]
  PFLT_CALLBACK_DATA CallbackData; // [rsp+B8h] [rbp+58h] BYREF

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  Information = 0;
  v34 = 0;
  FileObject = CurrentStackLocation->FileObject;
  CallbackData = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_qqLq(WPP_GLOBAL_Control->AttachedDevice, 66, a3, a1, a2, CurrentStackLocation->MinorFunction, FileObject);
  }
  Status = HsmiFileCacheValidateFileObject(FileObject, 0, &v34);
  HsmDbgBreakOnStatus(Status);
  if ( Status < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v9 = 67;
      MdlAddress = (PMDL)FileObject;
LABEL_10:
      WPP_SF_qd(v8->AttachedDevice, v9, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids, MdlAddress, Status);
      goto LABEL_34;
    }
    goto LABEL_34;
  }
  if ( CurrentStackLocation->MinorFunction )
  {
    Status = -1073741808;
    HsmDbgBreakOnStatus(-1073741808);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_Ld(WPP_GLOBAL_Control->AttachedDevice, 68, v11, CurrentStackLocation->MinorFunction);
    }
    goto LABEL_34;
  }
  IsOperationSynchronous = IoIsOperationSynchronous(a2);
  Flags = FileObject->Flags;
  v14 = v34;
  v15 = a2->Flags & 2;
  ByteOffset = CurrentStackLocation->Parameters.Read.ByteOffset;
  Length = CurrentStackLocation->Parameters.Read.Length;
  v18 = a2->Flags & 1;
  v20 = Flags >> 1;
  v19 = v34[4];
  LOBYTE(v20) = v20 & 1;
  v36 = v18;
  v35 = v15 != 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    LOBYTE(v33) = v20;
    LOBYTE(v20) = IsOperationSynchronous;
    LOBYTE(Priority) = a2->Flags & 1;
    LOBYTE(BugCheckOnFailure) = (a2->Flags & 2) != 0;
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _DWORD, _QWORD, _DWORD, _QWORD))WPP_SF_cccciDi)(
      WPP_GLOBAL_Control->AttachedDevice,
      69,
      WPP_GLOBAL_Control,
      v20,
      BugCheckOnFailure,
      Priority,
      v33,
      (LARGE_INTEGER)ByteOffset.QuadPart,
      Length,
      (LARGE_INTEGER)v19.QuadPart);
    v18 = v36;
  }
  if ( !v15 || !v18 )
  {
    Status = -1073741808;
    HsmDbgBreakOnStatus(-1073741808);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      LOBYTE(v30) = v35;
      LOBYTE(BugCheckOnFailure) = v36;
      WPP_SF_ccd(WPP_GLOBAL_Control->AttachedDevice, 70, v29, v30, BugCheckOnFailure);
    }
    goto LABEL_34;
  }
  if ( !a2->MdlAddress )
  {
    Status = -1073741808;
    HsmDbgBreakOnStatus(-1073741808);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 71, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids, 3221225488LL);
    }
    goto LABEL_34;
  }
  if ( 0x7FFFFFFFFFFFFFFFLL - ByteOffset.QuadPart < Length )
  {
    Status = -1073741811;
    HsmDbgBreakOnStatus(-1073741811);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))WPP_SF_qDd)(
        WPP_GLOBAL_Control->AttachedDevice,
        72,
        WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids,
        (LARGE_INTEGER)ByteOffset.QuadPart,
        Length,
        -1073741811);
    }
    goto LABEL_34;
  }
  if ( !(_DWORD)Length )
  {
    Status = 0;
    a2->IoStatus.Information = 0;
    goto LABEL_34;
  }
  if ( ByteOffset.QuadPart >= v19.QuadPart )
  {
    Status = -1073741807;
    HsmDbgBreakOnStatus(-1073741807);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD))WPP_SF_qqd)(
        WPP_GLOBAL_Control->AttachedDevice,
        73,
        WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids,
        (LARGE_INTEGER)ByteOffset.QuadPart,
        (LARGE_INTEGER)v19.QuadPart,
        -1073741807);
    }
    goto LABEL_34;
  }
  Status = FltAllocateCallbackData((PFLT_INSTANCE)v14[35].QuadPart, (PFILE_OBJECT)v14[36].QuadPart, &CallbackData);
  HsmDbgBreakOnStatus(Status);
  if ( Status < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD))WPP_SF_qqd)(
        WPP_GLOBAL_Control->AttachedDevice,
        74,
        WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids,
        (LARGE_INTEGER)v14[35].QuadPart,
        (LARGE_INTEGER)v14[36].QuadPart,
        Status);
    }
    goto LABEL_34;
  }
  CallbackData->Iopb->MajorFunction = 3;
  CallbackData->Iopb->MinorFunction = 0;
  CallbackData->Iopb->Parameters.Read.ByteOffset = ByteOffset;
  CallbackData->Iopb->Parameters.Read.Length = Length;
  CallbackData->Iopb->Parameters.Create.EaBuffer = a2->MdlAddress;
  CallbackData->Iopb->Parameters.Create.Options = 0;
  CallbackData->Iopb->Parameters.CreatePipe.Parameters = 0;
  CallbackData->Iopb->IrpFlags |= 0x47u;
  FltPerformSynchronousIo(CallbackData);
  CallbackData->Iopb->Parameters.Create.EaBuffer = 0;
  Status = CallbackData->IoStatus.Status;
  HsmDbgBreakOnStatus(Status);
  Information = CallbackData->IoStatus.Information;
  if ( Status < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))WPP_SF_qqqiDd)(
        WPP_GLOBAL_Control->AttachedDevice,
        75,
        CallbackData,
        (LARGE_INTEGER)v14[35].QuadPart,
        (LARGE_INTEGER)v14[36].QuadPart,
        CallbackData,
        (LARGE_INTEGER)ByteOffset.QuadPart,
        Length,
        Status);
    }
    goto LABEL_34;
  }
  if ( Status == 259 )
  {
    Status = -1073741595;
    HsmDbgBreakOnStatus(-1073741595);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 76, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids);
    }
    goto LABEL_34;
  }
  if ( ByteOffset.QuadPart + Length <= v19.QuadPart )
  {
    if ( (_DWORD)Length != Information )
    {
      Status = -1073741595;
      HsmDbgBreakOnStatus(-1073741595);
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_34;
      }
      v26 = 78;
LABEL_69:
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))WPP_SF_iDDd)(
        v25->AttachedDevice,
        v26,
        v24,
        (LARGE_INTEGER)ByteOffset.QuadPart,
        Length,
        Information);
      goto LABEL_34;
    }
  }
  else
  {
    v23 = v19.LowPart - ByteOffset.LowPart;
    if ( v23 > Information )
    {
      Status = -1073741595;
      HsmDbgBreakOnStatus(-1073741595);
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_34;
      }
      v26 = 77;
      goto LABEL_69;
    }
    Information = v23;
  }
  if ( v14[38].QuadPart
    && ((v27 = a2->MdlAddress, (v27->MdlFlags & 5) == 0)
      ? (MappedSystemVa = MmMapLockedPagesSpecifyCache(v27, 0, MmCached, 0, 0, 0x40000010u))
      : (MappedSystemVa = v27->MappedSystemVa),
        Status = ((__int64 (__fastcall *)(_QWORD, _QWORD, LARGE_INTEGER, PVOID, unsigned int))v14[38].QuadPart)(
                   (LARGE_INTEGER)v14[36].QuadPart,
                   (LARGE_INTEGER)v14[37].QuadPart,
                   ByteOffset,
                   MappedSystemVa,
                   Information),
        HsmDbgBreakOnStatus(Status),
        Status < 0) )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      MdlAddress = a2->MdlAddress;
      v9 = 79;
      goto LABEL_10;
    }
  }
  else
  {
    a2->IoStatus.Information = Information;
  }
LABEL_34:
  if ( CallbackData )
    FltFreeCallbackData(CallbackData);
  a2->IoStatus.Status = Status;
  if ( Status < 0 )
    a2->IoStatus.Information = 0;
  IofCompleteRequest(a2, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_dD(WPP_GLOBAL_Control->AttachedDevice, 80, v21, (unsigned int)Status, Information);
  }
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x140006440  mov     [rsp-38h+arg_0], rbx
0x140006445  push    rbp
0x140006446  push    rsi
0x140006447  push    rdi
0x140006448  push    r12
0x14000644a  push    r13
0x14000644c  push    r14
0x14000644e  push    r15
0x140006450  mov     rbp, rsp
0x140006453  sub     rsp, 60h
0x140006457  mov     r15, [rdx+0B8h]
0x14000645e  xor     r13d, r13d
0x140006461  mov     rsi, rdx
0x140006464  mov     [rbp+var_10], 0
0x14000646c  mov     r9, rcx
0x14000646f  mov     rbx, [r15+30h]
0x140006473  mov     [rbp+CallbackData], r13
0x140006477  mov     rcx, cs:WPP_GLOBAL_Control
0x14000647e  lea     r14, WPP_GLOBAL_Control
0x140006485  cmp     rcx, r14
0x140006488  jz      short loc_1400064B7
0x14000648a  mov     eax, [rcx+2Ch]
0x14000648d  test    al, 8
0x14000648f  jz      short loc_1400064B7
0x140006491  cmp     byte ptr [rcx+29h], 5
0x140006495  jb      short loc_1400064B7
0x140006497  movzx   eax, byte ptr [r15+1]
0x14000649c  lea     edx, [r13+42h]
0x1400064a0  mov     rcx, [rcx+18h]
0x1400064a4  mov     [rsp+60h+var_30], rbx
0x1400064a9  mov     [rsp+60h+Priority], eax
0x1400064ad  mov     qword ptr [rsp+60h+BugCheckOnFailure], rsi
0x1400064b2  call    WPP_SF_qqLq
0x1400064b7  lea     r8, [rbp+var_10]
0x1400064bb  xor     edx, edx
0x1400064bd  mov     rcx, rbx
0x1400064c0  call    HsmiFileCacheValidateFileObject
0x1400064c5  mov     ecx, eax
0x1400064c7  mov     edi, eax
0x1400064c9  call    HsmDbgBreakOnStatus
0x1400064ce  test    edi, edi
0x1400064d0  jns     short loc_140006519
0x1400064d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400064d9  cmp     rcx, r14
0x1400064dc  jz      loc_1400066E1
0x1400064e2  mov     edx, [rcx+2Ch]
0x1400064e5  test    dl, 8
0x1400064e8  jz      loc_1400066E1
0x1400064ee  cmp     byte ptr [rcx+29h], 2
0x1400064f2  jb      loc_1400066E1
0x1400064f8  mov     edx, 43h ; 'C'
0x1400064fd  mov     r9, rbx
0x140006500  mov     rcx, [rcx+18h]
0x140006504  lea     r8, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids
0x14000650b  mov     [rsp+60h+BugCheckOnFailure], edi
0x14000650f  call    WPP_SF_qd
0x140006514  jmp     loc_1400066E1
0x140006519  cmp     [r15+1], r13b
0x14000651d  jz      short loc_14000656A
0x14000651f  mov     ebx, 0C0000010h
0x140006524  mov     ecx, ebx
0x140006526  mov     edi, ebx
0x140006528  call    HsmDbgBreakOnStatus
0x14000652d  mov     rcx, cs:WPP_GLOBAL_Control
0x140006534  cmp     rcx, r14
0x140006537  jz      loc_1400066E1
0x14000653d  mov     eax, [rcx+2Ch]
0x140006540  test    al, 8
0x140006542  jz      loc_1400066E1
0x140006548  cmp     byte ptr [rcx+29h], 2
0x14000654c  jb      loc_1400066E1
0x140006552  movzx   r9d, byte ptr [r15+1]
0x140006557  mov     edx, 44h ; 'D'
0x14000655c  mov     rcx, [rcx+18h]
0x140006560  call    WPP_SF_Ld
0x140006565  jmp     loc_1400066E1
0x14000656a  mov     rcx, rsi; Irp
0x14000656d  call    cs:__imp_IoIsOperationSynchronous
0x140006574  nop     dword ptr [rax+rax+00h]
0x140006579  mov     ecx, [rsi+10h]
0x14000657c  mov     edi, ecx
0x14000657e  mov     r9d, [rbx+50h]
0x140006582  mov     r11b, al
0x140006585  mov     r14, [rbp+var_10]
0x140006589  and     edi, 2
0x14000658c  mov     rbx, [r15+18h]
0x140006590  mov     r15d, [r15+8]
0x140006594  setnz   r10b
0x140006598  and     cl, 1
0x14000659b  shr     r9d, 1
0x14000659e  mov     r12, [r14+20h]
0x1400065a2  and     r9b, 1
0x1400065a6  mov     [rbp+arg_10], ecx
0x1400065a9  mov     [rbp+arg_8], r10b
0x1400065ad  mov     r8, cs:WPP_GLOBAL_Control
0x1400065b4  lea     rax, WPP_GLOBAL_Control
0x1400065bb  cmp     r8, rax
0x1400065be  jz      short loc_140006600
0x1400065c0  mov     eax, [r8+2Ch]
0x1400065c4  test    al, 8
0x1400065c6  jz      short loc_140006600
0x1400065c8  cmp     byte ptr [r8+29h], 4
0x1400065cd  jb      short loc_140006600
0x1400065cf  mov     [rsp+60h+var_18], r12
0x1400065d4  mov     edx, 45h ; 'E'
0x1400065d9  mov     [rsp+60h+var_20], r15d
0x1400065de  mov     [rsp+60h+var_28], rbx
0x1400065e3  mov     byte ptr [rsp+60h+var_30], r9b
0x1400065e8  mov     r9b, r11b
0x1400065eb  mov     byte ptr [rsp+60h+Priority], cl
0x1400065ef  mov     rcx, [r8+18h]
0x1400065f3  mov     byte ptr [rsp+60h+BugCheckOnFailure], r10b
0x1400065f8  call    WPP_SF_cccciDi
0x1400065fd  mov     ecx, [rbp+arg_10]
0x140006600  test    edi, edi
0x140006602  jz      loc_140006B17
0x140006608  test    cl, cl
0x14000660a  jz      loc_140006B17
0x140006610  cmp     [rsi+8], r13
0x140006614  jnz     short loc_14000666A
0x140006616  mov     ebx, 0C0000010h
0x14000661b  mov     ecx, ebx
0x14000661d  mov     edi, ebx
0x14000661f  call    HsmDbgBreakOnStatus
0x140006624  mov     rcx, cs:WPP_GLOBAL_Control
0x14000662b  lea     r14, WPP_GLOBAL_Control
0x140006632  cmp     rcx, r14
0x140006635  jz      loc_1400066E1
0x14000663b  mov     eax, [rcx+2Ch]
0x14000663e  test    al, 8
0x140006640  jz      loc_1400066E1
0x140006646  cmp     byte ptr [rcx+29h], 2
0x14000664a  jb      loc_1400066E1
0x140006650  mov     rcx, [rcx+18h]
0x140006654  lea     r8, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids
0x14000665b  mov     edx, 47h ; 'G'
0x140006660  mov     r9d, ebx
0x140006663  call    WPP_SF_d
0x140006668  jmp     short loc_1400066E1
0x14000666a  mov     rax, 7FFFFFFFFFFFFFFFh
0x140006674  sub     rax, rbx
0x140006677  cmp     rax, r15
0x14000667a  jge     short loc_1400066CB
0x14000667c  mov     edi, 0C000000Dh
0x140006681  mov     ecx, edi
0x140006683  call    HsmDbgBreakOnStatus
0x140006688  mov     rcx, cs:WPP_GLOBAL_Control
0x14000668f  lea     r14, WPP_GLOBAL_Control
0x140006696  cmp     rcx, r14
0x140006699  jz      short loc_1400066E1
0x14000669b  mov     eax, [rcx+2Ch]
0x14000669e  test    al, 8
0x1400066a0  jz      short loc_1400066E1
0x1400066a2  cmp     byte ptr [rcx+29h], 2
0x1400066a6  jb      short loc_1400066E1
0x1400066a8  mov     rcx, [rcx+18h]
0x1400066ac  lea     r8, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids
0x1400066b3  mov     edx, 48h ; 'H'
0x1400066b8  mov     [rsp+60h+Priority], edi
0x1400066bc  mov     r9, rbx
0x1400066bf  mov     [rsp+60h+BugCheckOnFailure], r15d
0x1400066c4  call    WPP_SF_qDd
0x1400066c9  jmp     short loc_1400066E1
0x1400066cb  test    r15d, r15d
0x1400066ce  jnz     loc_140006763
0x1400066d4  xor     edi, edi
0x1400066d6  mov     [rsi+38h], rdi
0x1400066da  lea     r14, WPP_GLOBAL_Control
0x1400066e1  mov     r8, [rbp+CallbackData]
0x1400066e5  test    r8, r8
0x1400066e8  jz      short loc_1400066F9
0x1400066ea  mov     rcx, r8; CallbackData
0x1400066ed  call    cs:__imp_FltFreeCallbackData
0x1400066f4  nop     dword ptr [rax+rax+00h]
0x1400066f9  mov     [rsi+30h], edi
0x1400066fc  test    edi, edi
0x1400066fe  jns     short loc_140006708
0x140006700  mov     qword ptr [rsi+38h], 0
0x140006708  xor     edx, edx; PriorityBoost
0x14000670a  mov     rcx, rsi; Irp
0x14000670d  call    cs:__imp_IofCompleteRequest
0x140006714  nop     dword ptr [rax+rax+00h]
0x140006719  mov     rcx, cs:WPP_GLOBAL_Control
0x140006720  cmp     rcx, r14
0x140006723  jz      short loc_140006748
0x140006725  mov     eax, [rcx+2Ch]
0x140006728  test    al, 8
0x14000672a  jz      short loc_140006748
0x14000672c  cmp     byte ptr [rcx+29h], 5
0x140006730  jb      short loc_140006748
0x140006732  mov     rcx, [rcx+18h]
0x140006736  mov     edx, 50h ; 'P'
0x14000673b  mov     r9d, edi
0x14000673e  mov     [rsp+60h+BugCheckOnFailure], r13d
0x140006743  call    WPP_SF_dD
0x140006748  mov     rbx, [rsp+60h+arg_0]
0x140006750  mov     eax, edi
0x140006752  add     rsp, 60h
0x140006756  pop     r15
0x140006758  pop     r14
0x14000675a  pop     r13
0x14000675c  pop     r12
0x14000675e  pop     rdi
0x14000675f  pop     rsi
0x140006760  pop     rbp
0x140006761  retn
0x140006763  cmp     rbx, r12
0x140006766  jl      short loc_1400067C6
0x140006768  mov     edi, 0C0000011h
0x14000676d  mov     ecx, edi
0x14000676f  call    HsmDbgBreakOnStatus
0x140006774  mov     rcx, cs:WPP_GLOBAL_Control
0x14000677b  lea     r14, WPP_GLOBAL_Control
0x140006782  cmp     rcx, r14
0x140006785  jz      loc_1400066E1
0x14000678b  mov     eax, [rcx+2Ch]
0x14000678e  test    al, 8
0x140006790  jz      loc_1400066E1
0x140006796  cmp     byte ptr [rcx+29h], 4
0x14000679a  jb      loc_1400066E1
0x1400067a0  mov     rcx, [rcx+18h]
0x1400067a4  lea     r8, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids
0x1400067ab  mov     edx, 49h ; 'I'
0x1400067b0  mov     [rsp+60h+Priority], edi
0x1400067b4  mov     r9, rbx
0x1400067b7  mov     qword ptr [rsp+60h+BugCheckOnFailure], r12
0x1400067bc  call    WPP_SF_qqd
0x1400067c1  jmp     loc_1400066E1
0x1400067c6  mov     rdx, [r14+120h]; FileObject
0x1400067cd  lea     r8, [rbp+CallbackData]; RetNewCallbackData
0x1400067d1  mov     rcx, [r14+118h]; Instance
0x1400067d8  call    cs:__imp_FltAllocateCallbackData
0x1400067df  nop     dword ptr [rax+rax+00h]
0x1400067e4  mov     ecx, eax
0x1400067e6  mov     edi, eax
0x1400067e8  call    HsmDbgBreakOnStatus
0x1400067ed  xor     r8d, r8d
0x1400067f0  test    edi, edi
0x1400067f2  jns     short loc_140006850
0x1400067f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400067fb  lea     rax, WPP_GLOBAL_Control
0x140006802  cmp     rcx, rax
0x140006805  jz      loc_1400066DA
0x14000680b  mov     eax, [rcx+2Ch]
0x14000680e  test    al, 8
0x140006810  jz      loc_1400066DA
0x140006816  cmp     byte ptr [rcx+29h], 2
0x14000681a  jb      loc_1400066DA
0x140006820  mov     rax, [r14+120h]
0x140006827  lea     edx, [r8+4Ah]
0x14000682b  mov     r9, [r14+118h]
0x140006832  lea     r8, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids
0x140006839  mov     rcx, [rcx+18h]
0x14000683d  mov     [rsp+60h+Priority], edi
0x140006841  mov     qword ptr [rsp+60h+BugCheckOnFailure], rax
0x140006846  call    WPP_SF_qqd
0x14000684b  jmp     loc_1400066DA
0x140006850  mov     rax, [rbp+CallbackData]
0x140006854  mov     rcx, [rax+10h]
0x140006858  mov     byte ptr [rcx+4], 3
0x14000685c  mov     rax, [rbp+CallbackData]
0x140006860  mov     rcx, [rax+10h]
0x140006864  mov     [rcx+5], r8b
0x140006868  mov     rax, [rbp+CallbackData]
0x14000686c  mov     rcx, [rax+10h]
0x140006870  mov     [rcx+28h], rbx
0x140006874  mov     rax, [rbp+CallbackData]
0x140006878  mov     rcx, [rax+10h]
0x14000687c  mov     [rcx+18h], r15d
0x140006880  mov     rax, [rbp+CallbackData]
0x140006884  mov     rcx, [rax+10h]
0x140006888  mov     rax, [rsi+8]
0x14000688c  mov     [rcx+38h], rax
0x140006890  mov     rax, [rbp+CallbackData]
0x140006894  mov     rcx, [rax+10h]
0x140006898  mov     [rcx+20h], r8d
0x14000689c  mov     rax, [rbp+CallbackData]
0x1400068a0  mov     rcx, [rax+10h]
0x1400068a4  mov     [rcx+30h], r8
0x1400068a8  mov     rax, [rbp+CallbackData]
0x1400068ac  mov     rcx, [rax+10h]
0x1400068b0  or      dword ptr [rcx], 47h
0x1400068b3  mov     rcx, [rbp+CallbackData]; CallbackData
0x1400068b7  call    cs:__imp_FltPerformSynchronousIo
0x1400068be  nop     dword ptr [rax+rax+00h]
0x1400068c3  mov     rax, [rbp+CallbackData]
0x1400068c7  mov     rcx, [rax+10h]
0x1400068cb  mov     [rcx+38h], r13
0x1400068cf  mov     rax, [rbp+CallbackData]
0x1400068d3  mov     edi, [rax+18h]
0x1400068d6  mov     ecx, edi
0x1400068d8  call    HsmDbgBreakOnStatus
0x1400068dd  mov     r8, [rbp+CallbackData]
0x1400068e1  mov     r13d, [r8+20h]
0x1400068e5  test    edi, edi
0x1400068e7  jns     short loc_14000694E
0x1400068e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400068f0  lea     rax, WPP_GLOBAL_Control
0x1400068f7  cmp     rcx, rax
0x1400068fa  jz      loc_1400066DA
  ... truncated ...
```
