# PrjfInitProcessInfo

- ea: `0x14003b380`
- end: `0x14003b5f7`
- name: `PrjfInitProcessInfo`
- size: `631`
- prototype: `__int64 __fastcall(PEPROCESS Process, _DWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1400047cc`
- `0x140021c5c`

## callees

- `0x14000bb80`
- `0x14000d008`
- `0x14003b380`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14003b5cf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003b5cf`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x14003b40b`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x14003b40b`
- `ntoskrnl!PsGetProcessImageFileName` at `0x14003b3e1`
- `ntoskrnl!PsGetProcessImageFileName` at `0x14003b3e1`
- `ntoskrnl!RtlInitAnsiString` at `0x14003b3f4`
- `ntoskrnl!RtlInitAnsiString` at `0x14003b3f4`
- `ntoskrnl!SeLocateProcessImageName` at `0x14003b3b2`
- `ntoskrnl!SeLocateProcessImageName` at `0x14003b3b2`
- `ntoskrnl!PsGetProcessId` at `0x14003b52b`
- `ntoskrnl!PsGetProcessId` at `0x14003b52b`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14003b5b8`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14003b5b8`
- `ntoskrnl!ExAllocatePool2` at `0x14003b49a`
- `ntoskrnl!ExAllocatePool2` at `0x14003b49a`

## pseudocode

```c
__int64 __fastcall PrjfInitProcessInfo(PEPROCESS Process, _DWORD *a2)
{
  int v4; // edx
  NTSTATUS v5; // ebx
  int v6; // r8d
  const char *ProcessImageFileName; // rax
  int v8; // edx
  int v9; // r8d
  USHORT Length; // si
  USHORT MaximumLength; // di
  PWSTR Buffer; // r12
  USHORT *Pool2; // rax
  int v14; // edx
  int v15; // r8d
  struct _UNICODE_STRING UnicodeString; // [rsp+50h] [rbp-20h] BYREF
  _STRING DestinationString; // [rsp+60h] [rbp-10h] BYREF
  PUNICODE_STRING pImageFileName; // [rsp+B0h] [rbp+40h] BYREF

  pImageFileName = 0;
  UnicodeString = 0;
  v5 = SeLocateProcessImageName(Process, &pImageFileName);
  if ( v5 < 0 )
  {
    if ( (BYTE1(xmmword_14001A3D0) & 2) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v4) = BYTE1(xmmword_14001A3D0) & 2;
      LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sD(
        521,
        v4,
        v6,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        9,
        201,
        (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
        195);
    }
    goto LABEL_17;
  }
  if ( pImageFileName->Buffer )
  {
    Length = pImageFileName->Length;
    MaximumLength = pImageFileName->MaximumLength;
    Buffer = pImageFileName->Buffer;
  }
  else
  {
    DestinationString = 0;
    ProcessImageFileName = (const char *)PsGetProcessImageFileName(Process);
    RtlInitAnsiString(&DestinationString, ProcessImageFileName);
    v5 = RtlAnsiStringToUnicodeString(&UnicodeString, &DestinationString, 1u);
    if ( v5 < 0 )
    {
      if ( (BYTE1(xmmword_14001A3D0) & 2) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v8) = BYTE1(xmmword_14001A3D0) & 2;
        LOBYTE(v9) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sD(
          521,
          v8,
          v9,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          9,
          200,
          (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
          178);
      }
      goto LABEL_17;
    }
    Length = UnicodeString.Length;
    MaximumLength = UnicodeString.MaximumLength;
    Buffer = UnicodeString.Buffer;
  }
  Pool2 = (USHORT *)ExAllocatePool2(256, MaximumLength + 16LL, 1752386128);
  *(_QWORD *)a2 = Pool2;
  if ( Pool2 )
  {
    *Pool2 = Length;
    *(_WORD *)(*(_QWORD *)a2 + 2LL) = MaximumLength;
    *(_QWORD *)(*(_QWORD *)a2 + 8LL) = *(_QWORD *)a2 + 16LL;
    memmove(*(void **)(*(_QWORD *)a2 + 8LL), Buffer, Length);
    a2[2] = (unsigned int)PsGetProcessId(Process);
    goto LABEL_18;
  }
  if ( (BYTE1(xmmword_14001A3D0) & 2) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v14) = BYTE1(xmmword_14001A3D0) & 2;
    LOBYTE(v15) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sD(
      521,
      v14,
      v15,
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      2,
      9,
      202,
      (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
      (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
      211);
  }
LABEL_17:
  v5 = -1073741670;
LABEL_18:
  if ( UnicodeString.Buffer )
    RtlFreeUnicodeString(&UnicodeString);
  if ( pImageFileName )
    ExFreePoolWithTag(pImageFileName, 0);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14003b380  mov     [rsp-28h+arg_0], rbx
0x14003b385  mov     [rsp-28h+arg_8], rsi
0x14003b38a  push    rbp
0x14003b38b  push    rdi
0x14003b38c  push    r12
0x14003b38e  push    r14
0x14003b390  push    r15
0x14003b392  mov     rbp, rsp
0x14003b395  sub     rsp, 70h
0x14003b399  mov     r14, rdx
0x14003b39c  mov     [rbp+pImageFileName], 0
0x14003b3a4  xorps   xmm0, xmm0
0x14003b3a7  lea     rdx, [rbp+pImageFileName]; pImageFileName
0x14003b3ab  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x14003b3af  mov     r15, rcx
0x14003b3b2  call    cs:__imp_SeLocateProcessImageName
0x14003b3b9  nop     dword ptr [rax+rax+00h]
0x14003b3be  mov     ebx, eax
0x14003b3c0  test    eax, eax
0x14003b3c2  js      loc_14003B53D
0x14003b3c8  mov     rax, [rbp+pImageFileName]
0x14003b3cc  cmp     qword ptr [rax+8], 0
0x14003b3d1  jnz     loc_14003B47D
0x14003b3d7  xorps   xmm0, xmm0
0x14003b3da  mov     rcx, r15
0x14003b3dd  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14003b3e1  call    cs:__imp_PsGetProcessImageFileName
0x14003b3e8  nop     dword ptr [rax+rax+00h]
0x14003b3ed  mov     rdx, rax; SourceString
0x14003b3f0  lea     rcx, [rbp+DestinationString]; DestinationString
0x14003b3f4  call    cs:__imp_RtlInitAnsiString
0x14003b3fb  nop     dword ptr [rax+rax+00h]
0x14003b400  mov     r8b, 1; AllocateDestinationString
0x14003b403  lea     rdx, [rbp+DestinationString]; SourceString
0x14003b407  lea     rcx, [rbp+UnicodeString]; DestinationString
0x14003b40b  call    cs:__imp_RtlAnsiStringToUnicodeString
0x14003b412  nop     dword ptr [rax+rax+00h]
0x14003b417  mov     ebx, eax
0x14003b419  test    eax, eax
0x14003b41b  jns     short loc_14003B46F
0x14003b41d  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14003b423  lea     rax, WPP_RECORDER_INITIALIZED
0x14003b42a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003b431  setnz   r8b
0x14003b435  and     dl, 2
0x14003b438  jnz     short loc_14003B443
0x14003b43a  test    r8b, r8b
0x14003b43d  jz      loc_14003B5A8
0x14003b443  mov     [rsp+70h+var_28], 21B2h
0x14003b44b  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14003b452  mov     [rsp+70h+var_30], rax
0x14003b457  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x14003b45e  mov     [rsp+70h+var_38], rax
0x14003b463  mov     [rsp+70h+var_40], 0C8h
0x14003b46a  jmp     loc_14003B586
0x14003b46f  movzx   esi, [rbp+UnicodeString.Length]
0x14003b473  movzx   edi, [rbp+UnicodeString.MaximumLength]
0x14003b477  mov     r12, [rbp+UnicodeString.Buffer]
0x14003b47b  jmp     short loc_14003B488
0x14003b47d  movzx   esi, word ptr [rax]
0x14003b480  movzx   edi, word ptr [rax+2]
0x14003b484  mov     r12, [rax+8]
0x14003b488  movzx   edx, di
0x14003b48b  mov     ecx, 100h
0x14003b490  add     rdx, 10h
0x14003b494  mov     r8d, 68734A50h
0x14003b49a  call    cs:__imp_ExAllocatePool2
0x14003b4a1  nop     dword ptr [rax+rax+00h]
0x14003b4a6  mov     [r14], rax
0x14003b4a9  test    rax, rax
0x14003b4ac  jnz     short loc_14003B500
0x14003b4ae  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14003b4b4  lea     rax, WPP_RECORDER_INITIALIZED
0x14003b4bb  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003b4c2  setnz   r8b
0x14003b4c6  and     dl, 2
0x14003b4c9  jnz     short loc_14003B4D4
0x14003b4cb  test    r8b, r8b
0x14003b4ce  jz      loc_14003B5A8
0x14003b4d4  mov     [rsp+70h+var_28], 21D3h
0x14003b4dc  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14003b4e3  mov     [rsp+70h+var_30], rax
0x14003b4e8  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x14003b4ef  mov     [rsp+70h+var_38], rax
0x14003b4f4  mov     [rsp+70h+var_40], 0CAh
0x14003b4fb  jmp     loc_14003B586
0x14003b500  mov     [rax], si
0x14003b503  mov     rdx, r12; Src
0x14003b506  mov     rax, [r14]
0x14003b509  movzx   r8d, si; Size
0x14003b50d  mov     [rax+2], di
0x14003b511  mov     rcx, [r14]
0x14003b514  lea     rax, [rcx+10h]
0x14003b518  mov     [rcx+8], rax
0x14003b51c  mov     rcx, [r14]
0x14003b51f  mov     rcx, [rcx+8]; void *
0x14003b523  call    memmove
0x14003b528  mov     rcx, r15; Process
0x14003b52b  call    cs:__imp_PsGetProcessId
0x14003b532  nop     dword ptr [rax+rax+00h]
0x14003b537  mov     [r14+8], eax
0x14003b53b  jmp     short loc_14003B5AD
0x14003b53d  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14003b543  lea     rax, WPP_RECORDER_INITIALIZED
0x14003b54a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003b551  setnz   r8b
0x14003b555  and     dl, 2
0x14003b558  jnz     short loc_14003B55F
0x14003b55a  test    r8b, r8b
0x14003b55d  jz      short loc_14003B5A8
0x14003b55f  mov     [rsp+70h+var_28], 21C3h
0x14003b567  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14003b56e  mov     [rsp+70h+var_30], rax
0x14003b573  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x14003b57a  mov     [rsp+70h+var_38], rax
0x14003b57f  mov     [rsp+70h+var_40], 0C9h
0x14003b586  mov     r9, cs:WPP_GLOBAL_Control
0x14003b58d  mov     ecx, 209h
0x14003b592  mov     [rsp+70h+var_48], 9
0x14003b59a  mov     [rsp+70h+var_50], 2
0x14003b59f  mov     r9, [r9+40h]
0x14003b5a3  call    WPP_RECORDER_AND_TRACE_SF_sD
0x14003b5a8  mov     ebx, 0C000009Ah
0x14003b5ad  cmp     [rbp+UnicodeString.Buffer], 0
0x14003b5b2  jz      short loc_14003B5C4
0x14003b5b4  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x14003b5b8  call    cs:__imp_RtlFreeUnicodeString
0x14003b5bf  nop     dword ptr [rax+rax+00h]
0x14003b5c4  mov     rcx, [rbp+pImageFileName]; P
0x14003b5c8  test    rcx, rcx
0x14003b5cb  jz      short loc_14003B5DB
0x14003b5cd  xor     edx, edx; Tag
0x14003b5cf  call    cs:__imp_ExFreePoolWithTag
0x14003b5d6  nop     dword ptr [rax+rax+00h]
0x14003b5db  lea     r11, [rsp+70h+var_s0]
0x14003b5e0  mov     eax, ebx
0x14003b5e2  mov     rbx, [r11+30h]
0x14003b5e6  mov     rsi, [r11+38h]
0x14003b5ea  mov     rsp, r11
0x14003b5ed  pop     r15
0x14003b5ef  pop     r14
0x14003b5f1  pop     r12
0x14003b5f3  pop     rdi
0x14003b5f4  pop     rbp
0x14003b5f5  retn
```
