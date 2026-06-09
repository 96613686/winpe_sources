# CldCaptureProcessInfo

- ea: `0x14007a5bc`
- end: `0x14007a97f`
- name: `CldCaptureProcessInfo`
- size: `963`
- prototype: `__int64 __fastcall(PEPROCESS Process)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140038de0`
- `0x14003baf0`

## callees

- `0x140003c50`
- `0x140008d1c`
- `0x14000dd64`
- `0x14001e280`
- `0x14007a5bc`

## import_xrefs

- `ntoskrnl!SeLocateProcessImageName` at `0x14007a610`
- `ntoskrnl!SeLocateProcessImageName` at `0x14007a610`
- `ntoskrnl!PsGetProcessImageFileName` at `0x14007a64b`
- `ntoskrnl!PsGetProcessImageFileName` at `0x14007a64b`
- `ntoskrnl!RtlInitAnsiString` at `0x14007a65e`
- `ntoskrnl!RtlInitAnsiString` at `0x14007a65e`
- `ntoskrnl!PsGetProcessId` at `0x14007a5f7`
- `ntoskrnl!PsGetProcessId` at `0x14007a6ba`
- `ntoskrnl!PsGetProcessId` at `0x14007a7f2`
- `ntoskrnl!PsGetProcessId` at `0x14007a844`
- `ntoskrnl!PsGetProcessId` at `0x14007a8f9`
- `ntoskrnl!PsGetProcessId` at `0x14007a955`
- `ntoskrnl!PsGetProcessId` at `0x14007a5f7`
- `ntoskrnl!PsGetProcessId` at `0x14007a6ba`
- `ntoskrnl!PsGetProcessId` at `0x14007a7f2`
- `ntoskrnl!PsGetProcessId` at `0x14007a844`
- `ntoskrnl!PsGetProcessId` at `0x14007a8f9`
- `ntoskrnl!PsGetProcessId` at `0x14007a955`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14007a70c`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14007a70c`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x14007a675`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x14007a675`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a723`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a73c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a755`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a723`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a73c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a755`
- `ntoskrnl!ExAllocatePool2` at `0x14007a7a2`
- `ntoskrnl!ExAllocatePool2` at `0x14007a8b0`
- `ntoskrnl!ExAllocatePool2` at `0x14007a7a2`
- `ntoskrnl!ExAllocatePool2` at `0x14007a8b0`

## pseudocode

```c
__int64 __fastcall CldCaptureProcessInfo(PEPROCESS Process, __int64 a2)
{
  __int64 v2; // rdi
  void *v4; // r12
  __int64 v5; // r13
  unsigned int ProcessId; // eax
  NTSTATUS v7; // ebx
  const char *ProcessImageFileName; // rax
  __int64 ProcessCommandLine; // rdi
  unsigned int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // rax
  USHORT Length; // di
  USHORT MaximumLength; // bx
  PWSTR Buffer; // rax
  __int64 Pool2; // rax
  void *v18; // rdx
  unsigned int v19; // eax
  __int64 v20; // rax
  unsigned int v21; // eax
  struct _UNICODE_STRING UnicodeString; // [rsp+30h] [rbp-28h] BYREF
  struct _STRING DestinationString; // [rsp+40h] [rbp-18h] BYREF
  unsigned int v24; // [rsp+A0h] [rbp+48h] BYREF
  __int64 v25; // [rsp+A8h] [rbp+50h]
  PUNICODE_STRING pImageFileName; // [rsp+B0h] [rbp+58h] BYREF
  void *Src; // [rsp+B8h] [rbp+60h]

  v25 = a2;
  pImageFileName = 0;
  *(_DWORD *)(&DestinationString.MaximumLength + 1) = 0;
  UnicodeString = 0;
  v24 = 0;
  v2 = a2;
  v4 = 0;
  v5 = 0;
  ProcessId = (unsigned int)PsGetProcessId(Process);
  *(_QWORD *)v2 = Process;
  *(_DWORD *)(v2 + 24) = ProcessId;
  v7 = SeLocateProcessImageName(Process, &pImageFileName);
  if ( v7 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      v19 = (unsigned int)PsGetProcessId(Process);
      WPP_SF_qDd(
        WPP_GLOBAL_Control->AttachedDevice,
        11,
        WPP_5cc63c495e593b7f4331b4ca8c37f042_Traceguids,
        Process,
        v19,
        v7);
    }
    goto LABEL_32;
  }
  if ( pImageFileName->Buffer )
  {
    Length = pImageFileName->Length;
    MaximumLength = pImageFileName->MaximumLength;
    Buffer = pImageFileName->Buffer;
    goto LABEL_22;
  }
  DestinationString = 0;
  ProcessImageFileName = (const char *)PsGetProcessImageFileName(Process);
  RtlInitAnsiString(&DestinationString, ProcessImageFileName);
  if ( RtlAnsiStringToUnicodeString(&UnicodeString, &DestinationString, 1u) >= 0 )
  {
    Length = UnicodeString.Length;
    MaximumLength = UnicodeString.MaximumLength;
    Buffer = UnicodeString.Buffer;
LABEL_22:
    Src = Buffer;
    Pool2 = ExAllocatePool2(256, MaximumLength + 16LL, 1766878275);
    v5 = Pool2;
    if ( !Pool2 )
    {
      LODWORD(ProcessCommandLine) = -1073741670;
      HsmDbgBreakOnStatus(3221225626LL);
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_9;
      }
      v10 = (unsigned int)PsGetProcessId(Process);
      v11 = 12;
      goto LABEL_8;
    }
    v18 = Src;
    *(_QWORD *)(Pool2 + 8) = Pool2 + 16;
    *(_WORD *)Pool2 = Length;
    *(_WORD *)(Pool2 + 2) = MaximumLength;
    memmove((void *)(Pool2 + 16), v18, MaximumLength);
    v2 = v25;
LABEL_32:
    *(_QWORD *)(v2 + 8) = v5;
    ProcessCommandLine = (unsigned int)HsmOsGetProcessCommandLine(Process, 0, 0, &v24);
    HsmDbgBreakOnStatus(ProcessCommandLine);
    if ( (_DWORD)ProcessCommandLine == -1073741820 )
    {
      v20 = ExAllocatePool2(256, v24, 1766878275);
      v4 = (void *)v20;
      if ( !v20 )
      {
        LODWORD(ProcessCommandLine) = -1073741670;
        HsmDbgBreakOnStatus(3221225626LL);
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_9;
        }
        v10 = (unsigned int)PsGetProcessId(Process);
        v11 = 13;
        goto LABEL_8;
      }
      ProcessCommandLine = (unsigned int)HsmOsGetProcessCommandLine(Process, v20, v24, &v24);
      HsmDbgBreakOnStatus(ProcessCommandLine);
      if ( (int)ProcessCommandLine < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v21 = (unsigned int)PsGetProcessId(Process);
          WPP_SF_qDd(
            WPP_GLOBAL_Control->AttachedDevice,
            14,
            WPP_5cc63c495e593b7f4331b4ca8c37f042_Traceguids,
            Process,
            v21,
            ProcessCommandLine);
        }
        goto LABEL_9;
      }
    }
    v12 = v25;
    *(_QWORD *)(v25 + 16) = v4;
    v4 = 0;
    goto LABEL_10;
  }
  LODWORD(ProcessCommandLine) = -1073741670;
  HsmDbgBreakOnStatus(3221225626LL);
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u)
    || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
  {
    goto LABEL_9;
  }
  v10 = (unsigned int)PsGetProcessId(Process);
  v11 = 10;
LABEL_8:
  WPP_SF_qDd(
    WPP_GLOBAL_Control->AttachedDevice,
    v11,
    WPP_5cc63c495e593b7f4331b4ca8c37f042_Traceguids,
    Process,
    v10,
    -1073741670);
LABEL_9:
  v12 = v25;
LABEL_10:
  if ( *(_QWORD *)(v12 + 8) || *(_QWORD *)(v12 + 16) )
    LODWORD(ProcessCommandLine) = 0;
  if ( UnicodeString.Buffer )
    RtlFreeUnicodeString(&UnicodeString);
  if ( pImageFileName )
    ExFreePoolWithTag(pImageFileName, 0);
  if ( v4 )
    ExFreePoolWithTag(v4, 0x69506C43u);
  return (unsigned int)ProcessCommandLine;
}

```

## disassembly

```asm
0x14007a5bc  mov     [rsp-40h+arg_8], rdx
0x14007a5c1  push    rbp
0x14007a5c2  push    rbx
0x14007a5c3  push    rsi
0x14007a5c4  push    rdi
0x14007a5c5  push    r12
0x14007a5c7  push    r13
0x14007a5c9  push    r14
0x14007a5cb  push    r15
0x14007a5cd  mov     rbp, rsp
0x14007a5d0  sub     rsp, 58h
0x14007a5d4  xor     eax, eax
0x14007a5d6  mov     [rbp+pImageFileName], 0
0x14007a5de  xorps   xmm0, xmm0
0x14007a5e1  mov     dword ptr [rbp+DestinationString+4], eax
0x14007a5e4  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x14007a5e8  mov     [rbp+arg_0], eax
0x14007a5eb  mov     rdi, rdx
0x14007a5ee  mov     rsi, rcx
0x14007a5f1  xor     r12d, r12d
0x14007a5f4  xor     r13d, r13d
0x14007a5f7  call    cs:__imp_PsGetProcessId
0x14007a5fe  nop     dword ptr [rax+rax+00h]
0x14007a603  lea     rdx, [rbp+pImageFileName]; pImageFileName
0x14007a607  mov     [rdi], rsi
0x14007a60a  mov     rcx, rsi; Process
0x14007a60d  mov     [rdi+18h], eax
0x14007a610  call    cs:__imp_SeLocateProcessImageName
0x14007a617  nop     dword ptr [rax+rax+00h]
0x14007a61c  mov     r14d, 100h
0x14007a622  lea     r15, WPP_GLOBAL_Control
0x14007a629  mov     ebx, eax
0x14007a62b  test    eax, eax
0x14007a62d  js      loc_14007A829
0x14007a633  mov     rax, [rbp+pImageFileName]
0x14007a637  cmp     [rax+8], r12
0x14007a63b  jnz     loc_14007A783
0x14007a641  xorps   xmm0, xmm0
0x14007a644  mov     rcx, rsi
0x14007a647  movups  xmmword ptr [rbp-18h], xmm0
0x14007a64b  call    cs:__imp_PsGetProcessImageFileName
0x14007a652  nop     dword ptr [rax+rax+00h]
0x14007a657  mov     rdx, rax; SourceString
0x14007a65a  lea     rcx, [rbp+DestinationString]; DestinationString
0x14007a65e  call    cs:__imp_RtlInitAnsiString
0x14007a665  nop     dword ptr [rax+rax+00h]
0x14007a66a  mov     r8b, 1; AllocateDestinationString
0x14007a66d  lea     rdx, [rbp+DestinationString]; SourceString
0x14007a671  lea     rcx, [rbp+UnicodeString]; DestinationString
0x14007a675  call    cs:__imp_RtlAnsiStringToUnicodeString
0x14007a67c  nop     dword ptr [rax+rax+00h]
0x14007a681  test    eax, eax
0x14007a683  jns     loc_14007A775
0x14007a689  mov     ebx, 0C000009Ah
0x14007a68e  mov     ecx, ebx
0x14007a690  mov     edi, ebx
0x14007a692  call    HsmDbgBreakOnStatus
0x14007a697  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a69e  lea     r15, WPP_GLOBAL_Control
0x14007a6a5  cmp     rcx, r15
0x14007a6a8  jz      short loc_14007A6ED
0x14007a6aa  bt      dword ptr [rcx+2Ch], 8
0x14007a6af  jnb     short loc_14007A6ED
0x14007a6b1  cmp     byte ptr [rcx+29h], 2
0x14007a6b5  jb      short loc_14007A6ED
0x14007a6b7  mov     rcx, rsi; Process
0x14007a6ba  call    cs:__imp_PsGetProcessId
0x14007a6c1  nop     dword ptr [rax+rax+00h]
0x14007a6c6  lea     edx, [r12+0Ah]
0x14007a6cb  mov     [rsp+58h+var_30], ebx
0x14007a6cf  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a6d6  lea     r8, WPP_5cc63c495e593b7f4331b4ca8c37f042_Traceguids
0x14007a6dd  mov     r9, rsi
0x14007a6e0  mov     [rsp+58h+var_38], eax
0x14007a6e4  mov     rcx, [rcx+18h]
0x14007a6e8  call    WPP_SF_qDd
0x14007a6ed  mov     rax, [rbp+arg_8]
0x14007a6f1  cmp     qword ptr [rax+8], 0
0x14007a6f6  jnz     short loc_14007A6FF
0x14007a6f8  cmp     qword ptr [rax+10h], 0
0x14007a6fd  jz      short loc_14007A701
0x14007a6ff  xor     edi, edi
0x14007a701  cmp     [rbp+UnicodeString.Buffer], 0
0x14007a706  jz      short loc_14007A718
0x14007a708  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x14007a70c  call    cs:__imp_RtlFreeUnicodeString
0x14007a713  nop     dword ptr [rax+rax+00h]
0x14007a718  mov     rcx, [rbp+pImageFileName]; P
0x14007a71c  test    rcx, rcx
0x14007a71f  jz      short loc_14007A72F
0x14007a721  xor     edx, edx; Tag
0x14007a723  call    cs:__imp_ExFreePoolWithTag
0x14007a72a  nop     dword ptr [rax+rax+00h]
0x14007a72f  test    r13, r13
0x14007a732  jz      short loc_14007A748
0x14007a734  mov     edx, 69506C43h; Tag
0x14007a739  mov     rcx, r13; P
0x14007a73c  call    cs:__imp_ExFreePoolWithTag
0x14007a743  nop     dword ptr [rax+rax+00h]
0x14007a748  test    r12, r12
0x14007a74b  jz      short loc_14007A761
0x14007a74d  mov     edx, 69506C43h; Tag
0x14007a752  mov     rcx, r12; P
0x14007a755  call    cs:__imp_ExFreePoolWithTag
0x14007a75c  nop     dword ptr [rax+rax+00h]
0x14007a761  mov     eax, edi
0x14007a763  add     rsp, 58h
0x14007a767  pop     r15
0x14007a769  pop     r14
0x14007a76b  pop     r13
0x14007a76d  pop     r12
0x14007a76f  pop     rdi
0x14007a770  pop     rsi
0x14007a771  pop     rbx
0x14007a772  pop     rbp
0x14007a773  retn
0x14007a775  movzx   edi, [rbp+UnicodeString.Length]
0x14007a779  movzx   ebx, [rbp+UnicodeString.MaximumLength]
0x14007a77d  mov     rax, [rbp+UnicodeString.Buffer]
0x14007a781  jmp     short loc_14007A78E
0x14007a783  movzx   edi, word ptr [rax]
0x14007a786  movzx   ebx, word ptr [rax+2]
0x14007a78a  mov     rax, [rax+8]
0x14007a78e  movzx   edx, bx
0x14007a791  mov     r8d, 69506C43h
0x14007a797  add     rdx, 10h
0x14007a79b  mov     [rbp+Src], rax
0x14007a79f  mov     rcx, r14
0x14007a7a2  call    cs:__imp_ExAllocatePool2
0x14007a7a9  nop     dword ptr [rax+rax+00h]
0x14007a7ae  mov     r13, rax
0x14007a7b1  test    rax, rax
0x14007a7b4  jnz     short loc_14007A807
0x14007a7b6  mov     ebx, 0C000009Ah
0x14007a7bb  mov     ecx, ebx
0x14007a7bd  mov     edi, ebx
0x14007a7bf  call    HsmDbgBreakOnStatus
0x14007a7c4  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a7cb  lea     r15, WPP_GLOBAL_Control
0x14007a7d2  cmp     rcx, r15
0x14007a7d5  jz      loc_14007A6ED
0x14007a7db  test    [rcx+2Ch], r14d
0x14007a7df  jz      loc_14007A6ED
0x14007a7e5  cmp     byte ptr [rcx+29h], 2
0x14007a7e9  jb      loc_14007A6ED
0x14007a7ef  mov     rcx, rsi; Process
0x14007a7f2  call    cs:__imp_PsGetProcessId
0x14007a7f9  nop     dword ptr [rax+rax+00h]
0x14007a7fe  lea     edx, [r13+0Ch]
0x14007a802  jmp     loc_14007A6CB
0x14007a807  mov     rdx, [rbp+Src]; Src
0x14007a80b  lea     rcx, [rax+10h]; void *
0x14007a80f  movzx   r8d, bx; Size
0x14007a813  mov     [rax+8], rcx
0x14007a817  mov     [rax], di
0x14007a81a  mov     [rax+2], bx
0x14007a81e  call    memmove
0x14007a823  mov     rdi, [rbp+arg_8]
0x14007a827  jmp     short loc_14007A877
0x14007a829  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a830  cmp     rcx, r15
0x14007a833  jz      short loc_14007A877
0x14007a835  test    [rcx+2Ch], r14d
0x14007a839  jz      short loc_14007A877
0x14007a83b  cmp     byte ptr [rcx+29h], 3
0x14007a83f  jb      short loc_14007A877
0x14007a841  mov     rcx, rsi; Process
0x14007a844  call    cs:__imp_PsGetProcessId
0x14007a84b  nop     dword ptr [rax+rax+00h]
0x14007a850  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a857  lea     r8, WPP_5cc63c495e593b7f4331b4ca8c37f042_Traceguids
0x14007a85e  mov     edx, 0Bh
0x14007a863  mov     [rsp+58h+var_30], ebx
0x14007a867  mov     r9, rsi
0x14007a86a  mov     [rsp+58h+var_38], eax
0x14007a86e  mov     rcx, [rcx+18h]
0x14007a872  call    WPP_SF_qDd
0x14007a877  mov     [rdi+8], r13
0x14007a87b  lea     r9, [rbp+arg_0]
0x14007a87f  xor     r8d, r8d
0x14007a882  xor     edx, edx
0x14007a884  mov     rcx, rsi
0x14007a887  xor     r13d, r13d
0x14007a88a  call    HsmOsGetProcessCommandLine
0x14007a88f  mov     ecx, eax
0x14007a891  mov     edi, eax
0x14007a893  call    HsmDbgBreakOnStatus
0x14007a898  cmp     edi, 0C0000004h
0x14007a89e  jnz     loc_14007A96F
0x14007a8a4  mov     edx, [rbp+arg_0]
0x14007a8a7  mov     r8d, 69506C43h
0x14007a8ad  mov     rcx, r14
0x14007a8b0  call    cs:__imp_ExAllocatePool2
0x14007a8b7  nop     dword ptr [rax+rax+00h]
0x14007a8bc  mov     r12, rax
0x14007a8bf  test    rax, rax
0x14007a8c2  jnz     short loc_14007A90E
0x14007a8c4  mov     ebx, 0C000009Ah
0x14007a8c9  mov     ecx, ebx
0x14007a8cb  mov     edi, ebx
0x14007a8cd  call    HsmDbgBreakOnStatus
0x14007a8d2  mov     rax, cs:WPP_GLOBAL_Control
0x14007a8d9  cmp     rax, r15
0x14007a8dc  jz      loc_14007A6ED
0x14007a8e2  test    [rax+2Ch], r14d
0x14007a8e6  jz      loc_14007A6ED
0x14007a8ec  cmp     byte ptr [rax+29h], 2
0x14007a8f0  jb      loc_14007A6ED
0x14007a8f6  mov     rcx, rsi; Process
0x14007a8f9  call    cs:__imp_PsGetProcessId
0x14007a900  nop     dword ptr [rax+rax+00h]
0x14007a905  lea     edx, [r13+0Dh]
0x14007a909  jmp     loc_14007A6CB
0x14007a90e  mov     r8d, [rbp+arg_0]
0x14007a912  lea     r9, [rbp+arg_0]
0x14007a916  mov     rdx, rax
0x14007a919  mov     rcx, rsi
0x14007a91c  call    HsmOsGetProcessCommandLine
0x14007a921  mov     ecx, eax
0x14007a923  mov     edi, eax
0x14007a925  call    HsmDbgBreakOnStatus
0x14007a92a  test    edi, edi
0x14007a92c  jns     short loc_14007A96F
0x14007a92e  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a935  cmp     rcx, r15
0x14007a938  jz      loc_14007A6ED
0x14007a93e  test    [rcx+2Ch], r14d
0x14007a942  jz      loc_14007A6ED
0x14007a948  cmp     byte ptr [rcx+29h], 2
0x14007a94c  jb      loc_14007A6ED
0x14007a952  mov     rcx, rsi; Process
0x14007a955  call    cs:__imp_PsGetProcessId
0x14007a95c  nop     dword ptr [rax+rax+00h]
0x14007a961  mov     edx, 0Eh
0x14007a966  mov     [rsp+58h+var_30], edi
0x14007a96a  jmp     loc_14007A6CF
0x14007a96f  mov     rax, [rbp+arg_8]
0x14007a973  mov     [rax+10h], r12
0x14007a977  xor     r12d, r12d
0x14007a97a  jmp     loc_14007A6F1
```
