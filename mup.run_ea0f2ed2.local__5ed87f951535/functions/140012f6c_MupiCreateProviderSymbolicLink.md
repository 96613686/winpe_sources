# MupiCreateProviderSymbolicLink

- ea: `0x140012f6c`
- end: `0x140013120`
- name: `MupiCreateProviderSymbolicLink`
- size: `436`
- prototype: `__int64 __fastcall(PUNICODE_STRING SymbolicLinkName)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path`

## callers

- `0x1400134a0`

## callees

- `0x140001040`
- `0x140002e74`
- `0x140003608`
- `0x140012f6c`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140013054`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140013054`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140013012`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140013029`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140013040`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140013012`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140013029`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140013040`
- `ntoskrnl!ExAllocatePool2` at `0x140012fda`
- `ntoskrnl!ExAllocatePool2` at `0x140012fda`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400130ce`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400130ce`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140013063`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140013063`
- `ntoskrnl!IoCreateSymbolicLink` at `0x140013083`
- `ntoskrnl!IoCreateSymbolicLink` at `0x140013083`

## pseudocode

```c
__int64 __fastcall MupiCreateProviderSymbolicLink(PUNICODE_STRING SymbolicLinkName)
{
  __int64 v2; // r8
  PWSTR v3; // rcx
  __int64 v4; // rdx
  __int16 v5; // r9
  WCHAR *Pool2; // rax
  WCHAR *v7; // rsi
  NTSTATUS v8; // eax
  unsigned int v9; // ebx
  struct _UNICODE_STRING Destination; // [rsp+30h] [rbp-20h] BYREF
  UNICODE_STRING Source; // [rsp+40h] [rbp-10h] BYREF

  v2 = (SymbolicLinkName->Length >> 1) - 1;
  v3 = SymbolicLinkName->Buffer + 1;
  Destination = 0;
  *(_DWORD *)(&Source.MaximumLength + 1) = 0;
  Source.Buffer = (PWSTR)(MupFindMatchingChar(v3, v3, v2) + 2);
  Source.Length = 2 * (v5 - (((__int64)Source.Buffer - v4) >> 1));
  Source.MaximumLength = Source.Length;
  Pool2 = (WCHAR *)ExAllocatePool2(258, (unsigned int)Source.Length + 26, 544240973);
  v7 = Pool2;
  if ( !Pool2 )
  {
    v9 = -1073741670;
LABEL_11:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_b8ec61bc8b283db232150b702b34e2f1_Traceguids, v9);
    }
    return v9;
  }
  Destination.Buffer = Pool2;
  Destination.Length = 0;
  Destination.MaximumLength = Source.Length + 26;
  RtlAppendUnicodeToString(&Destination, L"\\Device\\Mup");
  RtlAppendUnicodeToString(&Destination, L"\\");
  RtlAppendUnicodeToString(&Destination, L";");
  RtlAppendUnicodeStringToString(&Destination, &Source);
  v8 = IoDeleteSymbolicLink(SymbolicLinkName);
  v9 = v8;
  if ( !v8 || v8 == -1073741772 )
  {
    v9 = IoCreateSymbolicLink(SymbolicLinkName, &Destination);
    if ( !v9
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0 )
    {
      WPP_SF_ZZ(
        WPP_GLOBAL_Control->AttachedDevice,
        22,
        (unsigned int)WPP_b8ec61bc8b283db232150b702b34e2f1_Traceguids,
        (_DWORD)SymbolicLinkName,
        (__int64)&Destination);
    }
  }
  ExFreePoolWithTag(v7, 0);
  if ( v9 )
    goto LABEL_11;
  return v9;
}

```

## disassembly

```asm
0x140012f6c  push    rbp
0x140012f6e  push    rbx
0x140012f6f  push    rsi
0x140012f70  push    rdi
0x140012f71  push    r15
0x140012f73  mov     rbp, rsp
0x140012f76  sub     rsp, 50h
0x140012f7a  movzx   r9d, word ptr [rcx]
0x140012f7e  mov     rdi, rcx
0x140012f81  mov     rdx, [rcx+8]
0x140012f85  xorps   xmm0, xmm0
0x140012f88  shr     r9d, 1
0x140012f8b  add     rdx, 2
0x140012f8f  dec     r9d
0x140012f92  xorps   xmm1, xmm1
0x140012f95  mov     r8d, r9d
0x140012f98  mov     rcx, rdx
0x140012f9b  movups  xmmword ptr [rbp+Destination.Length], xmm0
0x140012f9f  movups  xmmword ptr [rbp+Source.Length], xmm1
0x140012fa3  call    MupFindMatchingChar
0x140012fa8  add     rax, 2
0x140012fac  mov     ecx, 102h
0x140012fb1  mov     [rbp+Source.Buffer], rax
0x140012fb5  mov     r8d, 2070754Dh
0x140012fbb  sub     rax, rdx
0x140012fbe  sar     rax, 1
0x140012fc1  sub     r9w, ax
0x140012fc5  add     r9w, r9w
0x140012fc9  movzx   eax, r9w
0x140012fcd  mov     [rbp+Source.Length], ax
0x140012fd1  mov     [rbp+Source.MaximumLength], ax
0x140012fd5  lea     ebx, [rax+1Ah]
0x140012fd8  mov     edx, ebx
0x140012fda  call    cs:__imp_ExAllocatePool2
0x140012fe1  nop     dword ptr [rax+rax+00h]
0x140012fe6  lea     r15, WPP_GLOBAL_Control
0x140012fed  mov     rsi, rax
0x140012ff0  test    rax, rax
0x140012ff3  jz      loc_1400130E0
0x140012ff9  xor     ecx, ecx
0x140012ffb  mov     [rbp+Destination.Buffer], rax
0x140012fff  mov     [rbp+Destination.Length], cx
0x140013003  lea     rdx, aDeviceMup; "\\Device\\Mup"
0x14001300a  lea     rcx, [rbp+Destination]; Destination
0x14001300e  mov     [rbp+Destination.MaximumLength], bx
0x140013012  call    cs:__imp_RtlAppendUnicodeToString
0x140013019  nop     dword ptr [rax+rax+00h]
0x14001301e  lea     rdx, asc_140007964; "\\"
0x140013025  lea     rcx, [rbp+Destination]; Destination
0x140013029  call    cs:__imp_RtlAppendUnicodeToString
0x140013030  nop     dword ptr [rax+rax+00h]
0x140013035  lea     rdx, asc_140007968; ";"
0x14001303c  lea     rcx, [rbp+Destination]; Destination
0x140013040  call    cs:__imp_RtlAppendUnicodeToString
0x140013047  nop     dword ptr [rax+rax+00h]
0x14001304c  lea     rdx, [rbp+Source]; Source
0x140013050  lea     rcx, [rbp+Destination]; Destination
0x140013054  call    cs:__imp_RtlAppendUnicodeStringToString
0x14001305b  nop     dword ptr [rax+rax+00h]
0x140013060  mov     rcx, rdi; SymbolicLinkName
0x140013063  call    cs:__imp_IoDeleteSymbolicLink
0x14001306a  nop     dword ptr [rax+rax+00h]
0x14001306f  mov     ebx, eax
0x140013071  test    eax, eax
0x140013073  jz      short loc_14001307C
0x140013075  cmp     eax, 0C0000034h
0x14001307a  jnz     short loc_1400130C9
0x14001307c  lea     rdx, [rbp+Destination]; DeviceName
0x140013080  mov     rcx, rdi; SymbolicLinkName
0x140013083  call    cs:__imp_IoCreateSymbolicLink
0x14001308a  nop     dword ptr [rax+rax+00h]
0x14001308f  mov     ebx, eax
0x140013091  test    eax, eax
0x140013093  jnz     short loc_1400130C9
0x140013095  mov     rcx, cs:WPP_GLOBAL_Control
0x14001309c  cmp     rcx, r15
0x14001309f  jz      short loc_1400130C9
0x1400130a1  test    dword ptr [rcx+2Ch], 4000000h
0x1400130a8  jz      short loc_1400130C9
0x1400130aa  mov     rcx, [rcx+18h]
0x1400130ae  lea     edx, [rax+16h]
0x1400130b1  lea     rax, [rbp+Destination]
0x1400130b5  mov     r9, rdi
0x1400130b8  lea     r8, WPP_b8ec61bc8b283db232150b702b34e2f1_Traceguids
0x1400130bf  mov     [rsp+50h+var_30], rax
0x1400130c4  call    WPP_SF_ZZ
0x1400130c9  xor     edx, edx; Tag
0x1400130cb  mov     rcx, rsi; P
0x1400130ce  call    cs:__imp_ExFreePoolWithTag
0x1400130d5  nop     dword ptr [rax+rax+00h]
0x1400130da  test    ebx, ebx
0x1400130dc  jz      short loc_140013112
0x1400130de  jmp     short loc_1400130E5
0x1400130e0  mov     ebx, 0C000009Ah
0x1400130e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400130ec  cmp     rcx, r15
0x1400130ef  jz      short loc_140013112
0x1400130f1  test    dword ptr [rcx+2Ch], 4000000h
0x1400130f8  jz      short loc_140013112
0x1400130fa  mov     rcx, [rcx+18h]
0x1400130fe  lea     r8, WPP_b8ec61bc8b283db232150b702b34e2f1_Traceguids
0x140013105  mov     edx, 17h
0x14001310a  mov     r9d, ebx
0x14001310d  call    WPP_SF_d
0x140013112  mov     eax, ebx
0x140013114  add     rsp, 50h
0x140013118  pop     r15
0x14001311a  pop     rdi
0x14001311b  pop     rsi
0x14001311c  pop     rbx
0x14001311d  pop     rbp
0x14001311e  retn
```
