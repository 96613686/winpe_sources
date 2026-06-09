# HsmFltPreSET_EA

- ea: `0x1400801f0`
- end: `0x1400804bf`
- name: `HsmFltPreSET_EA`
- size: `719`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x140001910`
- `0x140003c50`
- `0x1400044f0`
- `0x14000abb8`
- `0x14001663c`
- `0x14004c5e0`
- `0x1400801f0`

## import_xrefs

- `ntoskrnl!RtlEqualString` at `0x140080300`
- `ntoskrnl!RtlEqualString` at `0x140080300`
- `ntoskrnl!RtlPrefixString` at `0x1400802dd`
- `ntoskrnl!RtlPrefixString` at `0x1400802dd`
- `ntoskrnl!IoCheckEaBufferValidity` at `0x14008028f`
- `ntoskrnl!IoCheckEaBufferValidity` at `0x14008028f`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140080356`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140080356`
- `FLTMGR!FltReleaseContext` at `0x140080489`
- `FLTMGR!FltReleaseContext` at `0x140080489`

## pseudocode

```c
__int64 __fastcall HsmFltPreSET_EA(struct _FLT_CALLBACK_DATA *a1, __int64 a2)
{
  unsigned int v3; // edi
  __int64 *StreamHandleContext; // rax
  int v5; // r8d
  __int64 *v6; // rbp
  __int64 v7; // rax
  char v8; // r15
  PFLT_IO_PARAMETER_BLOCK Iopb; // rsi
  LARGE_INTEGER ByteOffset; // rcx
  struct _FILE_FULL_EA_INFORMATION *EaList; // rsi
  __int64 v12; // rax
  __int64 v13; // r14
  int v14; // esi
  STRING String2; // [rsp+40h] [rbp-48h] BYREF
  ULONG ErrorOffset; // [rsp+90h] [rbp+8h] BYREF

  ErrorOffset = 0;
  String2 = 0;
  v3 = 1;
  if ( a1->Iopb->MinorFunction != 4 )
    return v3;
  StreamHandleContext = (__int64 *)HsmpGetStreamHandleContext(
                                     a1,
                                     *(PFLT_INSTANCE *)(a2 + 24),
                                     *(PFILE_OBJECT *)(a2 + 32));
  v6 = StreamHandleContext;
  if ( !StreamHandleContext )
    return v3;
  v7 = StreamHandleContext[2];
  if ( (*(_DWORD *)(v7 + 28) & 2) != 0 )
  {
    v8 = 0;
    goto LABEL_32;
  }
  LOBYTE(v5) = 1;
  v8 = 1;
  HsmpTracePreCallbackEnter((_DWORD)a1, 0, v5, (_DWORD)v6, v7);
  Iopb = a1->Iopb;
  ByteOffset = Iopb->Parameters.Read.ByteOffset;
  if ( ByteOffset.QuadPart )
  {
    if ( (*(_BYTE *)(ByteOffset.QuadPart + 10) & 5) != 0 )
      EaList = *(struct _FILE_FULL_EA_INFORMATION **)(ByteOffset.QuadPart + 24);
    else
      EaList = (struct _FILE_FULL_EA_INFORMATION *)MmMapLockedPagesSpecifyCache(
                                                     (PMDL)ByteOffset.QuadPart,
                                                     0,
                                                     MmCached,
                                                     0,
                                                     0,
                                                     0x40000010u);
    if ( !EaList )
    {
      v14 = -1073741670;
      HsmDbgBreakOnStatus(3221225626LL);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qqqd(
          WPP_GLOBAL_Control->AttachedDevice,
          63,
          WPP_e26ac64b2c40307be864d687cc32cd5d_Traceguids,
          a1,
          v6,
          a1->Iopb->TargetFileObject,
          -1073741670);
      }
      goto LABEL_31;
    }
  }
  else
  {
    EaList = (struct _FILE_FULL_EA_INFORMATION *)Iopb->Parameters.QueryEa.EaList;
  }
  if ( IoCheckEaBufferValidity(EaList, a1->Iopb->Parameters.Read.Length, &ErrorOffset) < 0 )
    goto LABEL_32;
  ErrorOffset = 0;
  v12 = 0;
  while ( 1 )
  {
    v13 = (unsigned int)v12;
    String2.Length = *(&EaList->EaNameLength + v12);
    String2.MaximumLength = String2.Length;
    String2.Buffer = &EaList->EaName[(unsigned int)v12];
    if ( RtlPrefixString(&KernelPurgeableEaNamePrefix, &String2, 1u) )
      break;
    if ( RtlEqualString(&DoNotConvertToCloudFilesEA, &String2, 1u) )
    {
      v14 = -1073741745;
      HsmDbgBreakOnStatus(3221225551LL);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_qqqd(
          WPP_GLOBAL_Control->AttachedDevice,
          65,
          WPP_e26ac64b2c40307be864d687cc32cd5d_Traceguids,
          a1,
          v6,
          a1->Iopb->TargetFileObject,
          -1073741745);
      }
      goto LABEL_31;
    }
    v12 = *(ULONG *)((char *)&EaList->NextEntryOffset + v13) + ErrorOffset;
    ErrorOffset += *(ULONG *)((char *)&EaList->NextEntryOffset + v13);
    if ( !*(ULONG *)((char *)&EaList->NextEntryOffset + v13) )
      goto LABEL_32;
  }
  v14 = -1073741745;
  HsmDbgBreakOnStatus(3221225551LL);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qqqd(
      WPP_GLOBAL_Control->AttachedDevice,
      64,
      WPP_e26ac64b2c40307be864d687cc32cd5d_Traceguids,
      a1,
      v6,
      a1->Iopb->TargetFileObject,
      -1073741745);
  }
  TlmWriteDisallowPurgeableKernelEA();
LABEL_31:
  a1->IoStatus.Status = v14;
  v3 = 4;
  a1->IoStatus.Information = 0;
LABEL_32:
  FltReleaseContext(v6);
  if ( v8 )
    HsmpTracePreCallbackExit(v3, (_DWORD)a1, 0, 0, 1);
  return v3;
}

```

## disassembly

```asm
0x1400801f0  mov     rax, rsp
0x1400801f3  push    rbx
0x1400801f4  push    rbp
0x1400801f5  push    rsi
0x1400801f6  push    rdi
0x1400801f7  push    r14
0x1400801f9  push    r15
0x1400801fb  sub     rsp, 58h
0x1400801ff  mov     dword ptr [rax+8], 0
0x140080206  xorps   xmm0, xmm0
0x140080209  movups  xmmword ptr [rax-48h], xmm0
0x14008020d  mov     rax, [rcx+10h]
0x140080211  mov     rbx, rcx
0x140080214  mov     edi, 1
0x140080219  cmp     byte ptr [rax+5], 4
0x14008021d  jnz     loc_1400804AF
0x140080223  mov     r8, [rdx+20h]; FileObject
0x140080227  mov     rdx, [rdx+18h]; Instance
0x14008022b  call    HsmpGetStreamHandleContext
0x140080230  mov     rbp, rax
0x140080233  test    rax, rax
0x140080236  jz      loc_1400804AF
0x14008023c  mov     rax, [rax+10h]
0x140080240  mov     ecx, [rax+1Ch]
0x140080243  test    cl, 2
0x140080246  jz      short loc_140080250
0x140080248  xor     r15b, r15b
0x14008024b  jmp     loc_140080486
0x140080250  mov     r9, rbp
0x140080253  mov     qword ptr [rsp+88h+BugCheckOnFailure], rax
0x140080258  mov     r8b, dil
0x14008025b  xor     edx, edx
0x14008025d  mov     rcx, rbx
0x140080260  mov     r15b, dil
0x140080263  call    HsmpTracePreCallbackEnter
0x140080268  mov     rsi, [rbx+10h]
0x14008026c  mov     rcx, [rsi+28h]; MemoryDescriptorList
0x140080270  test    rcx, rcx
0x140080273  jnz     loc_140080332
0x140080279  mov     rsi, [rsi+20h]
0x14008027d  mov     rdx, [rbx+10h]
0x140080281  lea     r8, [rsp+88h+ErrorOffset]; ErrorOffset
0x140080289  mov     rcx, rsi; EaBuffer
0x14008028c  mov     edx, [rdx+18h]; EaLength
0x14008028f  call    cs:__imp_IoCheckEaBufferValidity
0x140080296  nop     dword ptr [rax+rax+00h]
0x14008029b  test    eax, eax
0x14008029d  js      loc_140080486
0x1400802a3  mov     [rsp+88h+ErrorOffset], 0
0x1400802ae  xor     eax, eax
0x1400802b0  mov     r14d, eax
0x1400802b3  lea     rdx, [rsp+88h+String2]; String2
0x1400802b8  movzx   eax, byte ptr [rax+rsi+5]
0x1400802bd  lea     rcx, KernelPurgeableEaNamePrefix; String1
0x1400802c4  mov     [rsp+88h+String2.Length], ax
0x1400802c9  mov     r8b, dil; CaseInSensitive
0x1400802cc  mov     [rsp+88h+String2.MaximumLength], ax
0x1400802d1  lea     rax, [r14+8]
0x1400802d5  add     rax, rsi
0x1400802d8  mov     [rsp+88h+String2.Buffer], rax
0x1400802dd  call    cs:__imp_RtlPrefixString
0x1400802e4  nop     dword ptr [rax+rax+00h]
0x1400802e9  test    al, al
0x1400802eb  jnz     loc_140080414
0x1400802f1  mov     r8b, dil; CaseInSensitive
0x1400802f4  lea     rdx, [rsp+88h+String2]; String2
0x1400802f9  lea     rcx, DoNotConvertToCloudFilesEA; String1
0x140080300  call    cs:__imp_RtlEqualString
0x140080307  nop     dword ptr [rax+rax+00h]
0x14008030c  test    al, al
0x14008030e  jnz     loc_1400803DA
0x140080314  mov     eax, [rsp+88h+ErrorOffset]
0x14008031b  add     eax, [r14+rsi]
0x14008031f  mov     [rsp+88h+ErrorOffset], eax
0x140080326  cmp     dword ptr [r14+rsi], 0
0x14008032b  jnz     short loc_1400802B0
0x14008032d  jmp     loc_140080486
0x140080332  test    byte ptr [rcx+0Ah], 5
0x140080336  jz      short loc_14008033E
0x140080338  mov     rsi, [rcx+18h]
0x14008033c  jmp     short loc_140080365
0x14008033e  mov     [rsp+88h+Priority], 40000010h; Priority
0x140080346  xor     r9d, r9d; RequestedAddress
0x140080349  xor     edx, edx; AccessMode
0x14008034b  mov     [rsp+88h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140080353  mov     r8d, edi; CacheType
0x140080356  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14008035d  nop     dword ptr [rax+rax+00h]
0x140080362  mov     rsi, rax
0x140080365  test    rsi, rsi
0x140080368  jnz     loc_14008027D
0x14008036e  mov     esi, 0C000009Ah
0x140080373  mov     ecx, esi
0x140080375  call    HsmDbgBreakOnStatus
0x14008037a  mov     rcx, cs:WPP_GLOBAL_Control
0x140080381  lea     rax, WPP_GLOBAL_Control
0x140080388  cmp     rcx, rax
0x14008038b  jz      loc_140080476
0x140080391  mov     eax, [rcx+2Ch]
0x140080394  test    dil, al
0x140080397  jz      loc_140080476
0x14008039d  cmp     byte ptr [rcx+29h], 2
0x1400803a1  jb      loc_140080476
0x1400803a7  mov     edx, 3Fh ; '?'
0x1400803ac  mov     [rsp+88h+var_58], esi
0x1400803b0  mov     rax, [rbx+10h]
0x1400803b4  lea     r8, WPP_e26ac64b2c40307be864d687cc32cd5d_Traceguids
0x1400803bb  mov     rcx, [rcx+18h]
0x1400803bf  mov     r9, rbx
0x1400803c2  mov     rax, [rax+8]
0x1400803c6  mov     qword ptr [rsp+88h+Priority], rax
0x1400803cb  mov     qword ptr [rsp+88h+BugCheckOnFailure], rbp
0x1400803d0  call    WPP_SF_qqqd
0x1400803d5  jmp     loc_140080476
0x1400803da  mov     edi, 0C000004Fh
0x1400803df  mov     ecx, edi
0x1400803e1  mov     esi, edi
0x1400803e3  call    HsmDbgBreakOnStatus
0x1400803e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400803ef  lea     rax, WPP_GLOBAL_Control
0x1400803f6  cmp     rcx, rax
0x1400803f9  jz      short loc_140080476
0x1400803fb  mov     eax, [rcx+2Ch]
0x1400803fe  test    r15b, al
0x140080401  jz      short loc_140080476
0x140080403  cmp     byte ptr [rcx+29h], 4
0x140080407  jb      short loc_140080476
0x140080409  mov     edx, 41h ; 'A'
0x14008040e  mov     [rsp+88h+var_58], edi
0x140080412  jmp     short loc_1400803B0
0x140080414  mov     edi, 0C000004Fh
0x140080419  mov     ecx, edi
0x14008041b  mov     esi, edi
0x14008041d  call    HsmDbgBreakOnStatus
0x140080422  mov     rcx, cs:WPP_GLOBAL_Control
0x140080429  lea     rax, WPP_GLOBAL_Control
0x140080430  cmp     rcx, rax
0x140080433  jz      short loc_140080471
0x140080435  mov     eax, [rcx+2Ch]
0x140080438  test    r15b, al
0x14008043b  jz      short loc_140080471
0x14008043d  cmp     byte ptr [rcx+29h], 4
0x140080441  jb      short loc_140080471
0x140080443  mov     rax, [rbx+10h]
0x140080447  lea     r8, WPP_e26ac64b2c40307be864d687cc32cd5d_Traceguids
0x14008044e  mov     rcx, [rcx+18h]
0x140080452  mov     edx, 40h ; '@'
0x140080457  mov     [rsp+88h+var_58], edi
0x14008045b  mov     r9, rbx
0x14008045e  mov     rax, [rax+8]
0x140080462  mov     qword ptr [rsp+88h+Priority], rax
0x140080467  mov     qword ptr [rsp+88h+BugCheckOnFailure], rbp
0x14008046c  call    WPP_SF_qqqd
0x140080471  call    TlmWriteDisallowPurgeableKernelEA
0x140080476  mov     [rbx+18h], esi
0x140080479  mov     edi, 4
0x14008047e  mov     qword ptr [rbx+20h], 0
0x140080486  mov     rcx, rbp; Context
0x140080489  call    cs:__imp_FltReleaseContext
0x140080490  nop     dword ptr [rax+rax+00h]
0x140080495  test    r15b, r15b
0x140080498  jz      short loc_1400804AF
0x14008049a  xor     r9d, r9d
0x14008049d  mov     byte ptr [rsp+88h+BugCheckOnFailure], 1
0x1400804a2  xor     r8d, r8d
0x1400804a5  mov     rdx, rbx
0x1400804a8  mov     ecx, edi
0x1400804aa  call    HsmpTracePreCallbackExit
0x1400804af  mov     eax, edi
0x1400804b1  add     rsp, 58h
0x1400804b5  pop     r15
0x1400804b7  pop     r14
0x1400804b9  pop     rdi
0x1400804ba  pop     rsi
0x1400804bb  pop     rbp
0x1400804bc  pop     rbx
0x1400804bd  retn
```
