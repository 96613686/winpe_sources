# HsmiFileCacheIrpWrite

- ea: `0x1400056d0`
- end: `0x140005e7e`
- name: `HsmiFileCacheIrpWrite`
- size: `1966`
- prototype: `__int64 __fastcall(__int64, IRP *, __int64)`
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x140001b00`
- `0x140003c50`
- `0x1400054c0`
- `0x1400056d0`
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

## import_xrefs

- `ntoskrnl!IoIsOperationSynchronous` at `0x14000576a`
- `ntoskrnl!IoIsOperationSynchronous` at `0x14000576a`
- `ntoskrnl!IofCompleteRequest` at `0x140005938`
- `ntoskrnl!IofCompleteRequest` at `0x140005938`
- `FLTMGR!FltPerformAsynchronousIo` at `0x140005d98`
- `FLTMGR!FltPerformAsynchronousIo` at `0x140005d98`
- `FLTMGR!FltPerformSynchronousIo` at `0x1400058c6`
- `FLTMGR!FltPerformSynchronousIo` at `0x1400058c6`
- `FLTMGR!FltFreeCallbackData` at `0x14000591c`
- `FLTMGR!FltFreeCallbackData` at `0x14000591c`
- `FLTMGR!FltAllocateCallbackData` at `0x14000581a`
- `FLTMGR!FltAllocateCallbackData` at `0x14000581a`

## pseudocode

```c
__int64 __fastcall HsmiFileCacheIrpWrite(__int64 a1, IRP *a2, __int64 a3)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r14
  PFILE_OBJECT FileObject; // rdi
  NTSTATUS Status; // ebx
  BOOLEAN IsOperationSynchronous; // al
  __int64 v8; // r9
  ULONG Flags; // r8d
  LARGE_INTEGER *v10; // rdi
  int v11; // ebx
  LARGE_INTEGER ByteOffset; // r15
  __int64 Length; // r14
  char v14; // r12
  LARGE_INTEGER v15; // r13
  __int64 v16; // r8
  PFLT_IO_PARAMETER_BLOCK Iopb; // rcx
  ULONG_PTR Information_low; // r12
  __int64 v19; // r8
  __int64 v21; // r8
  unsigned int v22; // edi
  PDEVICE_OBJECT v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // r8
  NTSTATUS v26; // ebx
  __int64 v27; // r8
  __int64 v28; // r9
  int v29; // [rsp+20h] [rbp-40h]
  int v30; // [rsp+28h] [rbp-38h]
  int v31; // [rsp+30h] [rbp-30h]
  PFLT_CALLBACK_DATA RetNewCallbackData; // [rsp+50h] [rbp-10h] BYREF
  LARGE_INTEGER *v33; // [rsp+58h] [rbp-8h] BYREF
  BOOLEAN v34; // [rsp+A8h] [rbp+48h]
  bool v35; // [rsp+B0h] [rbp+50h]
  int Information; // [rsp+B8h] [rbp+58h]

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v33 = 0;
  Information = 0;
  FileObject = CurrentStackLocation->FileObject;
  RetNewCallbackData = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_qqLq(WPP_GLOBAL_Control->AttachedDevice, 86, a3, a1, a2, CurrentStackLocation->MinorFunction, FileObject);
  }
  Status = HsmiFileCacheValidateFileObject(FileObject, 0, &v33);
  HsmDbgBreakOnStatus(Status);
  if ( Status < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qd(
        WPP_GLOBAL_Control->AttachedDevice,
        87,
        WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids,
        FileObject,
        Status);
    }
    goto LABEL_21;
  }
  if ( CurrentStackLocation->MinorFunction )
  {
    Status = -1073741808;
    HsmDbgBreakOnStatus(-1073741808);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_Ld(WPP_GLOBAL_Control->AttachedDevice, 88, v21, CurrentStackLocation->MinorFunction);
    }
    goto LABEL_21;
  }
  if ( !FileObject->WriteAccess )
  {
    v22 = -1073741595;
    Status = -1073741595;
    HsmDbgBreakOnStatus(-1073741595);
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_21;
    }
    v24 = 89;
LABEL_49:
    WPP_SF_d(v23->AttachedDevice, v24, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids, v22);
LABEL_21:
    if ( RetNewCallbackData )
      FltFreeCallbackData(RetNewCallbackData);
    a2->IoStatus.Status = Status;
    if ( Status < 0 )
      a2->IoStatus.Information = 0;
    IofCompleteRequest(a2, 0);
    goto LABEL_26;
  }
  IsOperationSynchronous = IoIsOperationSynchronous(a2);
  Flags = FileObject->Flags;
  v10 = v33;
  v11 = a2->Flags & 2;
  ByteOffset = CurrentStackLocation->Parameters.Read.ByteOffset;
  Length = CurrentStackLocation->Parameters.Read.Length;
  v14 = a2->Flags & 1;
  v16 = Flags >> 1;
  v15 = v33[4];
  LOBYTE(v16) = v16 & 1;
  v34 = IsOperationSynchronous;
  v35 = v11 != 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    LOBYTE(v31) = v16;
    LOBYTE(v30) = a2->Flags & 1;
    LOBYTE(v29) = (a2->Flags & 2) != 0;
    LOBYTE(v8) = IsOperationSynchronous;
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _DWORD, _QWORD, _DWORD, _QWORD))WPP_SF_cccciDi)(
      WPP_GLOBAL_Control->AttachedDevice,
      90,
      v16,
      v8,
      v29,
      v30,
      v31,
      (LARGE_INTEGER)ByteOffset.QuadPart,
      Length,
      (LARGE_INTEGER)v15.QuadPart);
  }
  if ( !v11 || !v14 )
  {
    Status = -1073741808;
    HsmDbgBreakOnStatus(-1073741808);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      LOBYTE(v28) = v35;
      LOBYTE(v29) = v14;
      WPP_SF_ccd(WPP_GLOBAL_Control->AttachedDevice, 91, v27, v28, v29);
    }
    goto LABEL_21;
  }
  if ( !a2->MdlAddress )
  {
    v22 = -1073741808;
    Status = -1073741808;
    HsmDbgBreakOnStatus(-1073741808);
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_21;
    }
    v24 = 92;
    goto LABEL_49;
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
        93,
        WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids,
        (LARGE_INTEGER)ByteOffset.QuadPart,
        Length,
        -1073741811);
    }
    goto LABEL_21;
  }
  if ( !(_DWORD)Length )
  {
    Status = 0;
    a2->IoStatus.Information = 0;
    goto LABEL_21;
  }
  if ( ByteOffset.QuadPart >= v15.QuadPart )
  {
    Status = -1073741807;
    HsmDbgBreakOnStatus(-1073741807);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD))WPP_SF_qqd)(
        WPP_GLOBAL_Control->AttachedDevice,
        94,
        WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids,
        (LARGE_INTEGER)ByteOffset.QuadPart,
        (LARGE_INTEGER)v15.QuadPart,
        -1073741807);
    }
    goto LABEL_21;
  }
  Status = FltAllocateCallbackData((PFLT_INSTANCE)v10[35].QuadPart, (PFILE_OBJECT)v10[36].QuadPart, &RetNewCallbackData);
  HsmDbgBreakOnStatus(Status);
  if ( Status < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD))WPP_SF_qqd)(
        WPP_GLOBAL_Control->AttachedDevice,
        95,
        WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids,
        (LARGE_INTEGER)v10[35].QuadPart,
        (LARGE_INTEGER)v10[36].QuadPart,
        Status);
    }
    goto LABEL_21;
  }
  RetNewCallbackData->Iopb->MajorFunction = 4;
  RetNewCallbackData->Iopb->MinorFunction = 0;
  RetNewCallbackData->Iopb->Parameters.Read.ByteOffset = ByteOffset;
  RetNewCallbackData->Iopb->Parameters.Read.Length = Length;
  RetNewCallbackData->Iopb->Parameters.Create.EaBuffer = a2->MdlAddress;
  RetNewCallbackData->Iopb->Parameters.Create.Options = 0;
  RetNewCallbackData->Iopb->Parameters.CreatePipe.Parameters = a2->UserBuffer;
  if ( (*(_DWORD *)(v10[36].QuadPart + 80) & 0x10) != 0 )
    RetNewCallbackData->Iopb->OperationFlags |= 4u;
  Iopb = RetNewCallbackData->Iopb;
  if ( v34 )
  {
    Iopb->IrpFlags |= 0x47u;
    FltPerformSynchronousIo(RetNewCallbackData);
    RetNewCallbackData->Iopb->Parameters.Create.EaBuffer = 0;
    Status = RetNewCallbackData->IoStatus.Status;
    HsmDbgBreakOnStatus(Status);
    Information_low = LODWORD(RetNewCallbackData->IoStatus.Information);
    Information = RetNewCallbackData->IoStatus.Information;
    if ( Status >= 0 )
    {
      if ( Status == 259 )
      {
        Status = -1073741595;
        HsmDbgBreakOnStatus(-1073741595);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 98, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids);
        }
      }
      else if ( (_DWORD)Length == (_DWORD)Information_low )
      {
        a2->IoStatus.Information = Information_low;
      }
      else
      {
        Status = -1073741595;
        HsmDbgBreakOnStatus(-1073741595);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))WPP_SF_iDDd)(
            WPP_GLOBAL_Control->AttachedDevice,
            99,
            v25,
            (LARGE_INTEGER)ByteOffset.QuadPart,
            Length,
            Information_low);
        }
      }
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
           && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))WPP_SF_qqqiDd)(
        WPP_GLOBAL_Control->AttachedDevice,
        97,
        WPP_GLOBAL_Control,
        (LARGE_INTEGER)v10[35].QuadPart,
        (LARGE_INTEGER)v10[36].QuadPart,
        RetNewCallbackData,
        (LARGE_INTEGER)ByteOffset.QuadPart,
        Length,
        Status);
    }
    goto LABEL_21;
  }
  Iopb->IrpFlags |= 3u;
  a2->Tail.Overlay.CurrentStackLocation->Control |= 1u;
  v26 = FltPerformAsynchronousIo(RetNewCallbackData, HsmiFileCacheWriteCompletion, a2);
  HsmDbgBreakOnStatus(v26);
  if ( v26 < 0
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))WPP_SF_qqiDd)(
      WPP_GLOBAL_Control->AttachedDevice,
      96,
      WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids,
      (LARGE_INTEGER)v10[35].QuadPart,
      (LARGE_INTEGER)v10[36].QuadPart,
      (LARGE_INTEGER)ByteOffset.QuadPart,
      Length,
      v26);
  }
  Status = 259;
  HsmDbgBreakOnStatus(259);
LABEL_26:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_dD(WPP_GLOBAL_Control->AttachedDevice, 100, v19, (unsigned int)Status, Information);
  }
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x1400056d0  mov     [rsp-38h+arg_0], rbx
0x1400056d5  push    rbp
0x1400056d6  push    rsi
0x1400056d7  push    rdi
0x1400056d8  push    r12
0x1400056da  push    r13
0x1400056dc  push    r14
0x1400056de  push    r15
0x1400056e0  mov     rbp, rsp
0x1400056e3  sub     rsp, 60h
0x1400056e7  mov     r14, [rdx+0B8h]
0x1400056ee  xor     r12d, r12d
0x1400056f1  mov     rsi, rdx
0x1400056f4  mov     [rbp+var_8], 0
0x1400056fc  mov     r9, rcx
0x1400056ff  mov     [rbp+arg_18], r12d
0x140005703  mov     rdi, [r14+30h]
0x140005707  mov     [rbp+RetNewCallbackData], r12
0x14000570b  mov     rcx, cs:WPP_GLOBAL_Control
0x140005712  lea     r12, WPP_GLOBAL_Control
0x140005719  mov     r15b, 8
0x14000571c  cmp     rcx, r12
0x14000571f  jz      short loc_140005733
0x140005721  mov     eax, [rcx+2Ch]
0x140005724  test    r15b, al
0x140005727  jz      short loc_140005733
0x140005729  cmp     byte ptr [rcx+29h], 5
0x14000572d  jnb     loc_140005A54
0x140005733  lea     r8, [rbp+var_8]
0x140005737  xor     edx, edx
0x140005739  mov     rcx, rdi
0x14000573c  call    HsmiFileCacheValidateFileObject
0x140005741  mov     ecx, eax
0x140005743  mov     ebx, eax
0x140005745  call    HsmDbgBreakOnStatus
0x14000574a  test    ebx, ebx
0x14000574c  js      loc_1400059DB
0x140005752  cmp     byte ptr [r14+1], 0
0x140005757  jnz     loc_140005A7A
0x14000575d  cmp     byte ptr [rdi+4Bh], 0
0x140005761  jz      loc_140005AC6
0x140005767  mov     rcx, rsi; Irp
0x14000576a  call    cs:__imp_IoIsOperationSynchronous
0x140005771  nop     dword ptr [rax+rax+00h]
0x140005776  mov     r12d, [rsi+10h]
0x14000577a  mov     ebx, r12d
0x14000577d  mov     r8d, [rdi+50h]
0x140005781  mov     r10b, al
0x140005784  mov     rdi, [rbp+var_8]
0x140005788  and     ebx, 2
0x14000578b  mov     r15, [r14+18h]
0x14000578f  mov     r14d, [r14+8]
0x140005793  setnz   r9b
0x140005797  and     r12b, 1
0x14000579b  shr     r8d, 1
0x14000579e  mov     r13, [rdi+20h]
0x1400057a2  and     r8b, 1
0x1400057a6  mov     [rbp+arg_8], al
0x1400057a9  mov     [rbp+arg_10], r9b
0x1400057ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1400057b4  lea     rax, WPP_GLOBAL_Control
0x1400057bb  cmp     rcx, rax
0x1400057be  jnz     loc_140005992
0x1400057c4  test    ebx, ebx
0x1400057c6  jz      loc_140005E1B
0x1400057cc  test    r12b, r12b
0x1400057cf  jz      loc_140005E1B
0x1400057d5  cmp     qword ptr [rsi+8], 0
0x1400057da  jz      loc_140005B1E
0x1400057e0  mov     rcx, 7FFFFFFFFFFFFFFFh
0x1400057ea  sub     rcx, r15
0x1400057ed  cmp     rcx, r14
0x1400057f0  jl      loc_140005B5A
0x1400057f6  test    r14d, r14d
0x1400057f9  jz      loc_140005BB8
0x1400057ff  cmp     r15, r13
0x140005802  jge     loc_140005BC3
0x140005808  mov     rdx, [rdi+120h]; FileObject
0x14000580f  lea     r8, [rbp+RetNewCallbackData]; RetNewCallbackData
0x140005813  mov     rcx, [rdi+118h]; Instance
0x14000581a  call    cs:__imp_FltAllocateCallbackData
0x140005821  nop     dword ptr [rax+rax+00h]
0x140005826  mov     ecx, eax
0x140005828  mov     ebx, eax
0x14000582a  call    HsmDbgBreakOnStatus
0x14000582f  test    ebx, ebx
0x140005831  js      loc_140005C21
0x140005837  mov     rax, [rbp+RetNewCallbackData]
0x14000583b  xor     ebx, ebx
0x14000583d  mov     rcx, [rax+10h]
0x140005841  mov     byte ptr [rcx+4], 4
0x140005845  mov     rax, [rbp+RetNewCallbackData]
0x140005849  mov     rcx, [rax+10h]
0x14000584d  mov     [rcx+5], bl
0x140005850  mov     rax, [rbp+RetNewCallbackData]
0x140005854  mov     rcx, [rax+10h]
0x140005858  mov     [rcx+28h], r15
0x14000585c  mov     rax, [rbp+RetNewCallbackData]
0x140005860  mov     rcx, [rax+10h]
0x140005864  mov     [rcx+18h], r14d
0x140005868  mov     rax, [rbp+RetNewCallbackData]
0x14000586c  mov     rcx, [rax+10h]
0x140005870  mov     rax, [rsi+8]
0x140005874  mov     [rcx+38h], rax
0x140005878  mov     rax, [rbp+RetNewCallbackData]
0x14000587c  mov     rcx, [rax+10h]
0x140005880  mov     [rcx+20h], ebx
0x140005883  mov     rax, [rbp+RetNewCallbackData]
0x140005887  mov     rcx, [rax+10h]
0x14000588b  mov     rax, [rsi+70h]
0x14000588f  mov     [rcx+30h], rax
0x140005893  mov     rax, [rdi+120h]
0x14000589a  mov     ecx, [rax+50h]
0x14000589d  test    cl, 10h
0x1400058a0  jz      short loc_1400058AE
0x1400058a2  mov     rax, [rbp+RetNewCallbackData]
0x1400058a6  mov     rcx, [rax+10h]
0x1400058aa  or      byte ptr [rcx+6], 4
0x1400058ae  mov     rax, [rbp+RetNewCallbackData]
0x1400058b2  mov     rcx, [rax+10h]
0x1400058b6  cmp     [rbp+arg_8], bl
0x1400058b9  jz      loc_140005D7C
0x1400058bf  or      dword ptr [rcx], 47h
0x1400058c2  mov     rcx, [rbp+RetNewCallbackData]; CallbackData
0x1400058c6  call    cs:__imp_FltPerformSynchronousIo
0x1400058cd  nop     dword ptr [rax+rax+00h]
0x1400058d2  mov     rax, [rbp+RetNewCallbackData]
0x1400058d6  mov     rcx, [rax+10h]
0x1400058da  mov     [rcx+38h], rbx
0x1400058de  mov     rax, [rbp+RetNewCallbackData]
0x1400058e2  mov     ebx, [rax+18h]
0x1400058e5  mov     ecx, ebx
0x1400058e7  call    HsmDbgBreakOnStatus
0x1400058ec  mov     rcx, [rbp+RetNewCallbackData]
0x1400058f0  mov     r12d, [rcx+20h]
0x1400058f4  mov     [rbp+arg_18], r12d
0x1400058f8  test    ebx, ebx
0x1400058fa  jns     short loc_140005976
0x1400058fc  mov     r8, cs:WPP_GLOBAL_Control
0x140005903  lea     rax, WPP_GLOBAL_Control
0x14000590a  cmp     r8, rax
0x14000590d  jnz     loc_140005C7E
0x140005913  mov     rcx, [rbp+RetNewCallbackData]; CallbackData
0x140005917  test    rcx, rcx
0x14000591a  jz      short loc_140005928
0x14000591c  call    cs:__imp_FltFreeCallbackData
0x140005923  nop     dword ptr [rax+rax+00h]
0x140005928  mov     [rsi+30h], ebx
0x14000592b  test    ebx, ebx
0x14000592d  js      loc_140005E71
0x140005933  xor     edx, edx; PriorityBoost
0x140005935  mov     rcx, rsi; Irp
0x140005938  call    cs:__imp_IofCompleteRequest
0x14000593f  nop     dword ptr [rax+rax+00h]
0x140005944  mov     rcx, cs:WPP_GLOBAL_Control
0x14000594b  lea     rax, WPP_GLOBAL_Control
0x140005952  cmp     rcx, rax
0x140005955  jnz     loc_140005A22
0x14000595b  mov     eax, ebx
0x14000595d  mov     rbx, [rsp+60h+arg_0]
0x140005965  add     rsp, 60h
0x140005969  pop     r15
0x14000596b  pop     r14
0x14000596d  pop     r13
0x14000596f  pop     r12
0x140005971  pop     rdi
0x140005972  pop     rsi
0x140005973  pop     rbp
0x140005974  retn
0x140005976  mov     ecx, 103h
0x14000597b  cmp     ebx, ecx
0x14000597d  jz      loc_140005CCE
0x140005983  cmp     r14d, r12d
0x140005986  jnz     loc_140005D22
0x14000598c  mov     [rsi+38h], r12
0x140005990  jmp     short loc_140005913
0x140005992  mov     eax, [rcx+2Ch]
0x140005995  test    al, 8
0x140005997  jz      loc_1400057C4
0x14000599d  cmp     byte ptr [rcx+29h], 5
0x1400059a1  jb      loc_1400057C4
0x1400059a7  mov     rcx, [rcx+18h]
0x1400059ab  mov     edx, 5Ah ; 'Z'
0x1400059b0  mov     [rsp+60h+var_18], r13
0x1400059b5  mov     [rsp+60h+var_20], r14d
0x1400059ba  mov     [rsp+60h+var_28], r15
0x1400059bf  mov     byte ptr [rsp+60h+var_30], r8b
0x1400059c4  mov     byte ptr [rsp+60h+var_38], r12b
0x1400059c9  mov     byte ptr [rsp+60h+var_40], r9b
0x1400059ce  mov     r9b, r10b
0x1400059d1  call    WPP_SF_cccciDi
0x1400059d6  jmp     loc_1400057C4
0x1400059db  mov     rcx, cs:WPP_GLOBAL_Control
0x1400059e2  cmp     rcx, r12
0x1400059e5  jz      loc_140005913
0x1400059eb  mov     edx, [rcx+2Ch]
0x1400059ee  test    r15b, dl
0x1400059f1  jz      loc_140005913
0x1400059f7  cmp     byte ptr [rcx+29h], 2
0x1400059fb  jb      loc_140005913
0x140005a01  mov     rcx, [rcx+18h]
0x140005a05  lea     r8, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids
0x140005a0c  mov     edx, 57h ; 'W'
0x140005a11  mov     dword ptr [rsp+60h+var_40], ebx
0x140005a15  mov     r9, rdi
0x140005a18  call    WPP_SF_qd
0x140005a1d  jmp     loc_140005913
0x140005a22  mov     eax, [rcx+2Ch]
0x140005a25  test    al, 8
0x140005a27  jz      loc_14000595B
0x140005a2d  cmp     byte ptr [rcx+29h], 5
0x140005a31  jb      loc_14000595B
0x140005a37  mov     eax, [rbp+arg_18]
0x140005a3a  mov     edx, 64h ; 'd'
0x140005a3f  mov     rcx, [rcx+18h]
0x140005a43  mov     r9d, ebx
0x140005a46  mov     dword ptr [rsp+60h+var_40], eax
0x140005a4a  call    WPP_SF_dD
0x140005a4f  jmp     loc_14000595B
0x140005a54  movzx   eax, byte ptr [r14+1]
0x140005a59  mov     edx, 56h ; 'V'
0x140005a5e  mov     rcx, [rcx+18h]
0x140005a62  mov     [rsp+60h+var_30], rdi
0x140005a67  mov     dword ptr [rsp+60h+var_38], eax
0x140005a6b  mov     [rsp+60h+var_40], rsi
0x140005a70  call    WPP_SF_qqLq
0x140005a75  jmp     loc_140005733
0x140005a7a  mov     edi, 0C0000010h
0x140005a7f  mov     ecx, edi
0x140005a81  mov     ebx, edi
0x140005a83  call    HsmDbgBreakOnStatus
0x140005a88  mov     rcx, cs:WPP_GLOBAL_Control
0x140005a8f  cmp     rcx, r12
0x140005a92  jz      loc_140005913
0x140005a98  mov     eax, [rcx+2Ch]
0x140005a9b  test    r15b, al
0x140005a9e  jz      loc_140005913
0x140005aa4  cmp     byte ptr [rcx+29h], 2
0x140005aa8  jb      loc_140005913
0x140005aae  movzx   r9d, byte ptr [r14+1]
0x140005ab3  mov     edx, 58h ; 'X'
0x140005ab8  mov     rcx, [rcx+18h]
0x140005abc  call    WPP_SF_Ld
0x140005ac1  jmp     loc_140005913
0x140005ac6  mov     edi, 0C00000E5h
0x140005acb  mov     ecx, edi
0x140005acd  mov     ebx, edi
0x140005acf  call    HsmDbgBreakOnStatus
0x140005ad4  mov     rcx, cs:WPP_GLOBAL_Control
0x140005adb  cmp     rcx, r12
0x140005ade  jz      loc_140005913
0x140005ae4  mov     eax, [rcx+2Ch]
0x140005ae7  test    r15b, al
0x140005aea  jz      loc_140005913
0x140005af0  cmp     byte ptr [rcx+29h], 2
0x140005af4  jb      loc_140005913
0x140005afa  mov     edx, 59h ; 'Y'
0x140005aff  jmp     short loc_140005B06
0x140005b01  mov     edx, 5Ch ; '\'
0x140005b06  mov     rcx, [rcx+18h]
0x140005b0a  lea     r8, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids
0x140005b11  mov     r9d, edi
0x140005b14  call    WPP_SF_d
0x140005b19  jmp     loc_140005913
0x140005b1e  mov     edi, 0C0000010h
0x140005b23  mov     ecx, edi
0x140005b25  mov     ebx, edi
0x140005b27  call    HsmDbgBreakOnStatus
0x140005b2c  mov     rcx, cs:WPP_GLOBAL_Control
0x140005b33  lea     rax, WPP_GLOBAL_Control
0x140005b3a  cmp     rcx, rax
0x140005b3d  jz      loc_140005913
0x140005b43  mov     eax, [rcx+2Ch]
0x140005b46  test    al, 8
0x140005b48  jz      loc_140005913
0x140005b4e  cmp     byte ptr [rcx+29h], 2
0x140005b52  jb      loc_140005913
0x140005b58  jmp     short loc_140005B01
0x140005b5a  mov     ebx, 0C000000Dh
0x140005b5f  mov     ecx, ebx
0x140005b61  call    HsmDbgBreakOnStatus
0x140005b66  mov     rcx, cs:WPP_GLOBAL_Control
0x140005b6d  lea     rax, WPP_GLOBAL_Control
0x140005b74  cmp     rcx, rax
0x140005b77  jz      loc_140005913
0x140005b7d  mov     eax, [rcx+2Ch]
0x140005b80  test    al, 8
0x140005b82  jz      loc_140005913
0x140005b88  cmp     byte ptr [rcx+29h], 2
0x140005b8c  jb      loc_140005913
0x140005b92  mov     rcx, [rcx+18h]
0x140005b96  lea     r8, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids
0x140005b9d  mov     edx, 5Dh ; ']'
0x140005ba2  mov     dword ptr [rsp+60h+var_38], ebx
0x140005ba6  mov     r9, r15
0x140005ba9  mov     dword ptr [rsp+60h+var_40], r14d
0x140005bae  call    WPP_SF_qDd
0x140005bb3  jmp     loc_140005913
0x140005bb8  xor     ebx, ebx
0x140005bba  mov     [rsi+38h], rbx
  ... truncated ...
```
