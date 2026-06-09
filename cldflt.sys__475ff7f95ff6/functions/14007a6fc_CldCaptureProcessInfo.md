# CldCaptureProcessInfo

- ea: `0x14007a6fc`
- end: `0x14007aabf`
- name: `CldCaptureProcessInfo`
- size: `963`
- prototype: `__int64 __fastcall(PEPROCESS Process, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140038e00`
- `0x14003bb10`

## callees

- `0x140003c50`
- `0x140008d1c`
- `0x14000dd64`
- `0x14001e300`
- `0x14007a6fc`

## import_xrefs

- `ntoskrnl!SeLocateProcessImageName` at `0x14007a750`
- `ntoskrnl!SeLocateProcessImageName` at `0x14007a750`
- `ntoskrnl!PsGetProcessImageFileName` at `0x14007a78b`
- `ntoskrnl!PsGetProcessImageFileName` at `0x14007a78b`
- `ntoskrnl!RtlInitAnsiString` at `0x14007a79e`
- `ntoskrnl!RtlInitAnsiString` at `0x14007a79e`
- `ntoskrnl!PsGetProcessId` at `0x14007a737`
- `ntoskrnl!PsGetProcessId` at `0x14007a7fa`
- `ntoskrnl!PsGetProcessId` at `0x14007a932`
- `ntoskrnl!PsGetProcessId` at `0x14007a984`
- `ntoskrnl!PsGetProcessId` at `0x14007aa39`
- `ntoskrnl!PsGetProcessId` at `0x14007aa95`
- `ntoskrnl!PsGetProcessId` at `0x14007a737`
- `ntoskrnl!PsGetProcessId` at `0x14007a7fa`
- `ntoskrnl!PsGetProcessId` at `0x14007a932`
- `ntoskrnl!PsGetProcessId` at `0x14007a984`
- `ntoskrnl!PsGetProcessId` at `0x14007aa39`
- `ntoskrnl!PsGetProcessId` at `0x14007aa95`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14007a84c`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14007a84c`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x14007a7b5`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x14007a7b5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a863`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a87c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a895`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a863`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a87c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a895`
- `ntoskrnl!ExAllocatePool2` at `0x14007a8e2`
- `ntoskrnl!ExAllocatePool2` at `0x14007a9f0`
- `ntoskrnl!ExAllocatePool2` at `0x14007a8e2`
- `ntoskrnl!ExAllocatePool2` at `0x14007a9f0`

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
0x14007a6fc  mov     [rsp-40h+arg_8], rdx
0x14007a701  push    rbp
0x14007a702  push    rbx
0x14007a703  push    rsi
0x14007a704  push    rdi
0x14007a705  push    r12
0x14007a707  push    r13
0x14007a709  push    r14
0x14007a70b  push    r15
0x14007a70d  mov     rbp, rsp
0x14007a710  sub     rsp, 58h
0x14007a714  xor     eax, eax
0x14007a716  mov     [rbp+pImageFileName], 0
0x14007a71e  xorps   xmm0, xmm0
0x14007a721  mov     dword ptr [rbp+DestinationString+4], eax
0x14007a724  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x14007a728  mov     [rbp+arg_0], eax
0x14007a72b  mov     rdi, rdx
0x14007a72e  mov     rsi, rcx
0x14007a731  xor     r12d, r12d
0x14007a734  xor     r13d, r13d
0x14007a737  call    cs:__imp_PsGetProcessId
0x14007a73e  nop     dword ptr [rax+rax+00h]
0x14007a743  lea     rdx, [rbp+pImageFileName]; pImageFileName
0x14007a747  mov     [rdi], rsi
0x14007a74a  mov     rcx, rsi; Process
0x14007a74d  mov     [rdi+18h], eax
0x14007a750  call    cs:__imp_SeLocateProcessImageName
0x14007a757  nop     dword ptr [rax+rax+00h]
0x14007a75c  mov     r14d, 100h
0x14007a762  lea     r15, WPP_GLOBAL_Control
0x14007a769  mov     ebx, eax
0x14007a76b  test    eax, eax
0x14007a76d  js      loc_14007A969
0x14007a773  mov     rax, [rbp+pImageFileName]
0x14007a777  cmp     [rax+8], r12
0x14007a77b  jnz     loc_14007A8C3
0x14007a781  xorps   xmm0, xmm0
0x14007a784  mov     rcx, rsi
0x14007a787  movups  xmmword ptr [rbp-18h], xmm0
0x14007a78b  call    cs:__imp_PsGetProcessImageFileName
0x14007a792  nop     dword ptr [rax+rax+00h]
0x14007a797  mov     rdx, rax; SourceString
0x14007a79a  lea     rcx, [rbp+DestinationString]; DestinationString
0x14007a79e  call    cs:__imp_RtlInitAnsiString
0x14007a7a5  nop     dword ptr [rax+rax+00h]
0x14007a7aa  mov     r8b, 1; AllocateDestinationString
0x14007a7ad  lea     rdx, [rbp+DestinationString]; SourceString
0x14007a7b1  lea     rcx, [rbp+UnicodeString]; DestinationString
0x14007a7b5  call    cs:__imp_RtlAnsiStringToUnicodeString
0x14007a7bc  nop     dword ptr [rax+rax+00h]
0x14007a7c1  test    eax, eax
0x14007a7c3  jns     loc_14007A8B5
0x14007a7c9  mov     ebx, 0C000009Ah
0x14007a7ce  mov     ecx, ebx
0x14007a7d0  mov     edi, ebx
0x14007a7d2  call    HsmDbgBreakOnStatus
0x14007a7d7  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a7de  lea     r15, WPP_GLOBAL_Control
0x14007a7e5  cmp     rcx, r15
0x14007a7e8  jz      short loc_14007A82D
0x14007a7ea  bt      dword ptr [rcx+2Ch], 8
0x14007a7ef  jnb     short loc_14007A82D
0x14007a7f1  cmp     byte ptr [rcx+29h], 2
0x14007a7f5  jb      short loc_14007A82D
0x14007a7f7  mov     rcx, rsi; Process
0x14007a7fa  call    cs:__imp_PsGetProcessId
0x14007a801  nop     dword ptr [rax+rax+00h]
0x14007a806  lea     edx, [r12+0Ah]
0x14007a80b  mov     [rsp+58h+var_30], ebx
0x14007a80f  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a816  lea     r8, WPP_5cc63c495e593b7f4331b4ca8c37f042_Traceguids
0x14007a81d  mov     r9, rsi
0x14007a820  mov     [rsp+58h+var_38], eax
0x14007a824  mov     rcx, [rcx+18h]
0x14007a828  call    WPP_SF_qDd
0x14007a82d  mov     rax, [rbp+arg_8]
0x14007a831  cmp     qword ptr [rax+8], 0
0x14007a836  jnz     short loc_14007A83F
0x14007a838  cmp     qword ptr [rax+10h], 0
0x14007a83d  jz      short loc_14007A841
0x14007a83f  xor     edi, edi
0x14007a841  cmp     [rbp+UnicodeString.Buffer], 0
0x14007a846  jz      short loc_14007A858
0x14007a848  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x14007a84c  call    cs:__imp_RtlFreeUnicodeString
0x14007a853  nop     dword ptr [rax+rax+00h]
0x14007a858  mov     rcx, [rbp+pImageFileName]; P
0x14007a85c  test    rcx, rcx
0x14007a85f  jz      short loc_14007A86F
0x14007a861  xor     edx, edx; Tag
0x14007a863  call    cs:__imp_ExFreePoolWithTag
0x14007a86a  nop     dword ptr [rax+rax+00h]
0x14007a86f  test    r13, r13
0x14007a872  jz      short loc_14007A888
0x14007a874  mov     edx, 69506C43h; Tag
0x14007a879  mov     rcx, r13; P
0x14007a87c  call    cs:__imp_ExFreePoolWithTag
0x14007a883  nop     dword ptr [rax+rax+00h]
0x14007a888  test    r12, r12
0x14007a88b  jz      short loc_14007A8A1
0x14007a88d  mov     edx, 69506C43h; Tag
0x14007a892  mov     rcx, r12; P
0x14007a895  call    cs:__imp_ExFreePoolWithTag
0x14007a89c  nop     dword ptr [rax+rax+00h]
0x14007a8a1  mov     eax, edi
0x14007a8a3  add     rsp, 58h
0x14007a8a7  pop     r15
0x14007a8a9  pop     r14
0x14007a8ab  pop     r13
0x14007a8ad  pop     r12
0x14007a8af  pop     rdi
0x14007a8b0  pop     rsi
0x14007a8b1  pop     rbx
0x14007a8b2  pop     rbp
0x14007a8b3  retn
0x14007a8b5  movzx   edi, [rbp+UnicodeString.Length]
0x14007a8b9  movzx   ebx, [rbp+UnicodeString.MaximumLength]
0x14007a8bd  mov     rax, [rbp+UnicodeString.Buffer]
0x14007a8c1  jmp     short loc_14007A8CE
0x14007a8c3  movzx   edi, word ptr [rax]
0x14007a8c6  movzx   ebx, word ptr [rax+2]
0x14007a8ca  mov     rax, [rax+8]
0x14007a8ce  movzx   edx, bx
0x14007a8d1  mov     r8d, 69506C43h
0x14007a8d7  add     rdx, 10h
0x14007a8db  mov     [rbp+Src], rax
0x14007a8df  mov     rcx, r14
0x14007a8e2  call    cs:__imp_ExAllocatePool2
0x14007a8e9  nop     dword ptr [rax+rax+00h]
0x14007a8ee  mov     r13, rax
0x14007a8f1  test    rax, rax
0x14007a8f4  jnz     short loc_14007A947
0x14007a8f6  mov     ebx, 0C000009Ah
0x14007a8fb  mov     ecx, ebx
0x14007a8fd  mov     edi, ebx
0x14007a8ff  call    HsmDbgBreakOnStatus
0x14007a904  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a90b  lea     r15, WPP_GLOBAL_Control
0x14007a912  cmp     rcx, r15
0x14007a915  jz      loc_14007A82D
0x14007a91b  test    [rcx+2Ch], r14d
0x14007a91f  jz      loc_14007A82D
0x14007a925  cmp     byte ptr [rcx+29h], 2
0x14007a929  jb      loc_14007A82D
0x14007a92f  mov     rcx, rsi; Process
0x14007a932  call    cs:__imp_PsGetProcessId
0x14007a939  nop     dword ptr [rax+rax+00h]
0x14007a93e  lea     edx, [r13+0Ch]
0x14007a942  jmp     loc_14007A80B
0x14007a947  mov     rdx, [rbp+Src]; Src
0x14007a94b  lea     rcx, [rax+10h]; void *
0x14007a94f  movzx   r8d, bx; Size
0x14007a953  mov     [rax+8], rcx
0x14007a957  mov     [rax], di
0x14007a95a  mov     [rax+2], bx
0x14007a95e  call    memmove
0x14007a963  mov     rdi, [rbp+arg_8]
0x14007a967  jmp     short loc_14007A9B7
0x14007a969  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a970  cmp     rcx, r15
0x14007a973  jz      short loc_14007A9B7
0x14007a975  test    [rcx+2Ch], r14d
0x14007a979  jz      short loc_14007A9B7
0x14007a97b  cmp     byte ptr [rcx+29h], 3
0x14007a97f  jb      short loc_14007A9B7
0x14007a981  mov     rcx, rsi; Process
0x14007a984  call    cs:__imp_PsGetProcessId
0x14007a98b  nop     dword ptr [rax+rax+00h]
0x14007a990  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a997  lea     r8, WPP_5cc63c495e593b7f4331b4ca8c37f042_Traceguids
0x14007a99e  mov     edx, 0Bh
0x14007a9a3  mov     [rsp+58h+var_30], ebx
0x14007a9a7  mov     r9, rsi
0x14007a9aa  mov     [rsp+58h+var_38], eax
0x14007a9ae  mov     rcx, [rcx+18h]
0x14007a9b2  call    WPP_SF_qDd
0x14007a9b7  mov     [rdi+8], r13
0x14007a9bb  lea     r9, [rbp+arg_0]
0x14007a9bf  xor     r8d, r8d
0x14007a9c2  xor     edx, edx
0x14007a9c4  mov     rcx, rsi
0x14007a9c7  xor     r13d, r13d
0x14007a9ca  call    HsmOsGetProcessCommandLine
0x14007a9cf  mov     ecx, eax
0x14007a9d1  mov     edi, eax
0x14007a9d3  call    HsmDbgBreakOnStatus
0x14007a9d8  cmp     edi, 0C0000004h
0x14007a9de  jnz     loc_14007AAAF
0x14007a9e4  mov     edx, [rbp+arg_0]
0x14007a9e7  mov     r8d, 69506C43h
0x14007a9ed  mov     rcx, r14
0x14007a9f0  call    cs:__imp_ExAllocatePool2
0x14007a9f7  nop     dword ptr [rax+rax+00h]
0x14007a9fc  mov     r12, rax
0x14007a9ff  test    rax, rax
0x14007aa02  jnz     short loc_14007AA4E
0x14007aa04  mov     ebx, 0C000009Ah
0x14007aa09  mov     ecx, ebx
0x14007aa0b  mov     edi, ebx
0x14007aa0d  call    HsmDbgBreakOnStatus
0x14007aa12  mov     rax, cs:WPP_GLOBAL_Control
0x14007aa19  cmp     rax, r15
0x14007aa1c  jz      loc_14007A82D
0x14007aa22  test    [rax+2Ch], r14d
0x14007aa26  jz      loc_14007A82D
0x14007aa2c  cmp     byte ptr [rax+29h], 2
0x14007aa30  jb      loc_14007A82D
0x14007aa36  mov     rcx, rsi; Process
0x14007aa39  call    cs:__imp_PsGetProcessId
0x14007aa40  nop     dword ptr [rax+rax+00h]
0x14007aa45  lea     edx, [r13+0Dh]
0x14007aa49  jmp     loc_14007A80B
0x14007aa4e  mov     r8d, [rbp+arg_0]
0x14007aa52  lea     r9, [rbp+arg_0]
0x14007aa56  mov     rdx, rax
0x14007aa59  mov     rcx, rsi
0x14007aa5c  call    HsmOsGetProcessCommandLine
0x14007aa61  mov     ecx, eax
0x14007aa63  mov     edi, eax
0x14007aa65  call    HsmDbgBreakOnStatus
0x14007aa6a  test    edi, edi
0x14007aa6c  jns     short loc_14007AAAF
0x14007aa6e  mov     rcx, cs:WPP_GLOBAL_Control
0x14007aa75  cmp     rcx, r15
0x14007aa78  jz      loc_14007A82D
0x14007aa7e  test    [rcx+2Ch], r14d
0x14007aa82  jz      loc_14007A82D
0x14007aa88  cmp     byte ptr [rcx+29h], 2
0x14007aa8c  jb      loc_14007A82D
0x14007aa92  mov     rcx, rsi; Process
0x14007aa95  call    cs:__imp_PsGetProcessId
0x14007aa9c  nop     dword ptr [rax+rax+00h]
0x14007aaa1  mov     edx, 0Eh
0x14007aaa6  mov     [rsp+58h+var_30], edi
0x14007aaaa  jmp     loc_14007A80F
0x14007aaaf  mov     rax, [rbp+arg_8]
0x14007aab3  mov     [rax+10h], r12
0x14007aab7  xor     r12d, r12d
0x14007aaba  jmp     loc_14007A831
```
