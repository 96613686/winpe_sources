# HsmFltPreSET_EA

- ea: `0x140080390`
- end: `0x14008065f`
- name: `HsmFltPreSET_EA`
- size: `719`
- prototype: `__int64 __fastcall(struct _FLT_CALLBACK_DATA *, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x140001910`
- `0x140003c50`
- `0x1400044f0`
- `0x14000abb8`
- `0x1400166bc`
- `0x14004c6d0`
- `0x140080390`

## import_xrefs

- `ntoskrnl!RtlEqualString` at `0x1400804a0`
- `ntoskrnl!RtlEqualString` at `0x1400804a0`
- `ntoskrnl!RtlPrefixString` at `0x14008047d`
- `ntoskrnl!RtlPrefixString` at `0x14008047d`
- `ntoskrnl!IoCheckEaBufferValidity` at `0x14008042f`
- `ntoskrnl!IoCheckEaBufferValidity` at `0x14008042f`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400804f6`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400804f6`
- `FLTMGR!FltReleaseContext` at `0x140080629`
- `FLTMGR!FltReleaseContext` at `0x140080629`

## pseudocode

```c
__int64 __fastcall HsmFltPreSET_EA(struct _FLT_CALLBACK_DATA *a1, __int64 a2)
{
  unsigned int v3; // edi
  __int64 StreamHandleContext; // rax
  int v5; // r8d
  void *v6; // rbp
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
  StreamHandleContext = HsmpGetStreamHandleContext(a1, *(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32));
  v6 = (void *)StreamHandleContext;
  if ( !StreamHandleContext )
    return v3;
  v7 = *(_QWORD *)(StreamHandleContext + 16);
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
      HsmDbgBreakOnStatus(-1073741670);
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
      HsmDbgBreakOnStatus(-1073741745);
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
  HsmDbgBreakOnStatus(-1073741745);
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
0x140080390  mov     rax, rsp
0x140080393  push    rbx
0x140080394  push    rbp
0x140080395  push    rsi
0x140080396  push    rdi
0x140080397  push    r14
0x140080399  push    r15
0x14008039b  sub     rsp, 58h
0x14008039f  mov     dword ptr [rax+8], 0
0x1400803a6  xorps   xmm0, xmm0
0x1400803a9  movups  xmmword ptr [rax-48h], xmm0
0x1400803ad  mov     rax, [rcx+10h]
0x1400803b1  mov     rbx, rcx
0x1400803b4  mov     edi, 1
0x1400803b9  cmp     byte ptr [rax+5], 4
0x1400803bd  jnz     loc_14008064F
0x1400803c3  mov     r8, [rdx+20h]; FileObject
0x1400803c7  mov     rdx, [rdx+18h]; Instance
0x1400803cb  call    HsmpGetStreamHandleContext
0x1400803d0  mov     rbp, rax
0x1400803d3  test    rax, rax
0x1400803d6  jz      loc_14008064F
0x1400803dc  mov     rax, [rax+10h]
0x1400803e0  mov     ecx, [rax+1Ch]
0x1400803e3  test    cl, 2
0x1400803e6  jz      short loc_1400803F0
0x1400803e8  xor     r15b, r15b
0x1400803eb  jmp     loc_140080626
0x1400803f0  mov     r9, rbp
0x1400803f3  mov     qword ptr [rsp+88h+BugCheckOnFailure], rax
0x1400803f8  mov     r8b, dil
0x1400803fb  xor     edx, edx
0x1400803fd  mov     rcx, rbx
0x140080400  mov     r15b, dil
0x140080403  call    HsmpTracePreCallbackEnter
0x140080408  mov     rsi, [rbx+10h]
0x14008040c  mov     rcx, [rsi+28h]; MemoryDescriptorList
0x140080410  test    rcx, rcx
0x140080413  jnz     loc_1400804D2
0x140080419  mov     rsi, [rsi+20h]
0x14008041d  mov     rdx, [rbx+10h]
0x140080421  lea     r8, [rsp+88h+ErrorOffset]; ErrorOffset
0x140080429  mov     rcx, rsi; EaBuffer
0x14008042c  mov     edx, [rdx+18h]; EaLength
0x14008042f  call    cs:__imp_IoCheckEaBufferValidity
0x140080436  nop     dword ptr [rax+rax+00h]
0x14008043b  test    eax, eax
0x14008043d  js      loc_140080626
0x140080443  mov     [rsp+88h+ErrorOffset], 0
0x14008044e  xor     eax, eax
0x140080450  mov     r14d, eax
0x140080453  lea     rdx, [rsp+88h+String2]; String2
0x140080458  movzx   eax, byte ptr [rax+rsi+5]
0x14008045d  lea     rcx, KernelPurgeableEaNamePrefix; String1
0x140080464  mov     [rsp+88h+String2.Length], ax
0x140080469  mov     r8b, dil; CaseInSensitive
0x14008046c  mov     [rsp+88h+String2.MaximumLength], ax
0x140080471  lea     rax, [r14+8]
0x140080475  add     rax, rsi
0x140080478  mov     [rsp+88h+String2.Buffer], rax
0x14008047d  call    cs:__imp_RtlPrefixString
0x140080484  nop     dword ptr [rax+rax+00h]
0x140080489  test    al, al
0x14008048b  jnz     loc_1400805B4
0x140080491  mov     r8b, dil; CaseInSensitive
0x140080494  lea     rdx, [rsp+88h+String2]; String2
0x140080499  lea     rcx, DoNotConvertToCloudFilesEA; String1
0x1400804a0  call    cs:__imp_RtlEqualString
0x1400804a7  nop     dword ptr [rax+rax+00h]
0x1400804ac  test    al, al
0x1400804ae  jnz     loc_14008057A
0x1400804b4  mov     eax, [rsp+88h+ErrorOffset]
0x1400804bb  add     eax, [r14+rsi]
0x1400804bf  mov     [rsp+88h+ErrorOffset], eax
0x1400804c6  cmp     dword ptr [r14+rsi], 0
0x1400804cb  jnz     short loc_140080450
0x1400804cd  jmp     loc_140080626
0x1400804d2  test    byte ptr [rcx+0Ah], 5
0x1400804d6  jz      short loc_1400804DE
0x1400804d8  mov     rsi, [rcx+18h]
0x1400804dc  jmp     short loc_140080505
0x1400804de  mov     [rsp+88h+Priority], 40000010h; Priority
0x1400804e6  xor     r9d, r9d; RequestedAddress
0x1400804e9  xor     edx, edx; AccessMode
0x1400804eb  mov     [rsp+88h+BugCheckOnFailure], 0; BugCheckOnFailure
0x1400804f3  mov     r8d, edi; CacheType
0x1400804f6  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400804fd  nop     dword ptr [rax+rax+00h]
0x140080502  mov     rsi, rax
0x140080505  test    rsi, rsi
0x140080508  jnz     loc_14008041D
0x14008050e  mov     esi, 0C000009Ah
0x140080513  mov     ecx, esi
0x140080515  call    HsmDbgBreakOnStatus
0x14008051a  mov     rcx, cs:WPP_GLOBAL_Control
0x140080521  lea     rax, WPP_GLOBAL_Control
0x140080528  cmp     rcx, rax
0x14008052b  jz      loc_140080616
0x140080531  mov     eax, [rcx+2Ch]
0x140080534  test    dil, al
0x140080537  jz      loc_140080616
0x14008053d  cmp     byte ptr [rcx+29h], 2
0x140080541  jb      loc_140080616
0x140080547  mov     edx, 3Fh ; '?'
0x14008054c  mov     [rsp+88h+var_58], esi
0x140080550  mov     rax, [rbx+10h]
0x140080554  lea     r8, WPP_e26ac64b2c40307be864d687cc32cd5d_Traceguids
0x14008055b  mov     rcx, [rcx+18h]
0x14008055f  mov     r9, rbx
0x140080562  mov     rax, [rax+8]
0x140080566  mov     qword ptr [rsp+88h+Priority], rax
0x14008056b  mov     qword ptr [rsp+88h+BugCheckOnFailure], rbp
0x140080570  call    WPP_SF_qqqd
0x140080575  jmp     loc_140080616
0x14008057a  mov     edi, 0C000004Fh
0x14008057f  mov     ecx, edi
0x140080581  mov     esi, edi
0x140080583  call    HsmDbgBreakOnStatus
0x140080588  mov     rcx, cs:WPP_GLOBAL_Control
0x14008058f  lea     rax, WPP_GLOBAL_Control
0x140080596  cmp     rcx, rax
0x140080599  jz      short loc_140080616
0x14008059b  mov     eax, [rcx+2Ch]
0x14008059e  test    r15b, al
0x1400805a1  jz      short loc_140080616
0x1400805a3  cmp     byte ptr [rcx+29h], 4
0x1400805a7  jb      short loc_140080616
0x1400805a9  mov     edx, 41h ; 'A'
0x1400805ae  mov     [rsp+88h+var_58], edi
0x1400805b2  jmp     short loc_140080550
0x1400805b4  mov     edi, 0C000004Fh
0x1400805b9  mov     ecx, edi
0x1400805bb  mov     esi, edi
0x1400805bd  call    HsmDbgBreakOnStatus
0x1400805c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400805c9  lea     rax, WPP_GLOBAL_Control
0x1400805d0  cmp     rcx, rax
0x1400805d3  jz      short loc_140080611
0x1400805d5  mov     eax, [rcx+2Ch]
0x1400805d8  test    r15b, al
0x1400805db  jz      short loc_140080611
0x1400805dd  cmp     byte ptr [rcx+29h], 4
0x1400805e1  jb      short loc_140080611
0x1400805e3  mov     rax, [rbx+10h]
0x1400805e7  lea     r8, WPP_e26ac64b2c40307be864d687cc32cd5d_Traceguids
0x1400805ee  mov     rcx, [rcx+18h]
0x1400805f2  mov     edx, 40h ; '@'
0x1400805f7  mov     [rsp+88h+var_58], edi
0x1400805fb  mov     r9, rbx
0x1400805fe  mov     rax, [rax+8]
0x140080602  mov     qword ptr [rsp+88h+Priority], rax
0x140080607  mov     qword ptr [rsp+88h+BugCheckOnFailure], rbp
0x14008060c  call    WPP_SF_qqqd
0x140080611  call    TlmWriteDisallowPurgeableKernelEA
0x140080616  mov     [rbx+18h], esi
0x140080619  mov     edi, 4
0x14008061e  mov     qword ptr [rbx+20h], 0
0x140080626  mov     rcx, rbp; Context
0x140080629  call    cs:__imp_FltReleaseContext
0x140080630  nop     dword ptr [rax+rax+00h]
0x140080635  test    r15b, r15b
0x140080638  jz      short loc_14008064F
0x14008063a  xor     r9d, r9d
0x14008063d  mov     byte ptr [rsp+88h+BugCheckOnFailure], 1
0x140080642  xor     r8d, r8d
0x140080645  mov     rdx, rbx
0x140080648  mov     ecx, edi
0x14008064a  call    HsmpTracePreCallbackExit
0x14008064f  mov     eax, edi
0x140080651  add     rsp, 58h
0x140080655  pop     r15
0x140080657  pop     r14
0x140080659  pop     rdi
0x14008065a  pop     rsi
0x14008065b  pop     rbp
0x14008065c  pop     rbx
0x14008065d  retn
```
