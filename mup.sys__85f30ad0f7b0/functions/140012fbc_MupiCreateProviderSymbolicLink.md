# MupiCreateProviderSymbolicLink

- ea: `0x140012fbc`
- end: `0x140013170`
- name: `MupiCreateProviderSymbolicLink`
- size: `436`
- prototype: `__int64 __fastcall(PUNICODE_STRING SymbolicLinkName)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path`

## callers

- `0x1400134f0`

## callees

- `0x140001040`
- `0x140002e74`
- `0x140003608`
- `0x140012fbc`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400130a4`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400130a4`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140013062`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140013079`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140013090`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140013062`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140013079`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140013090`
- `ntoskrnl!ExAllocatePool2` at `0x14001302a`
- `ntoskrnl!ExAllocatePool2` at `0x14001302a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001311e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001311e`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x1400130b3`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x1400130b3`
- `ntoskrnl!IoCreateSymbolicLink` at `0x1400130d3`
- `ntoskrnl!IoCreateSymbolicLink` at `0x1400130d3`

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
0x140012fbc  push    rbp
0x140012fbe  push    rbx
0x140012fbf  push    rsi
0x140012fc0  push    rdi
0x140012fc1  push    r15
0x140012fc3  mov     rbp, rsp
0x140012fc6  sub     rsp, 50h
0x140012fca  movzx   r9d, word ptr [rcx]
0x140012fce  mov     rdi, rcx
0x140012fd1  mov     rdx, [rcx+8]
0x140012fd5  xorps   xmm0, xmm0
0x140012fd8  shr     r9d, 1
0x140012fdb  add     rdx, 2
0x140012fdf  dec     r9d
0x140012fe2  xorps   xmm1, xmm1
0x140012fe5  mov     r8d, r9d
0x140012fe8  mov     rcx, rdx
0x140012feb  movups  xmmword ptr [rbp+Destination.Length], xmm0
0x140012fef  movups  xmmword ptr [rbp+Source.Length], xmm1
0x140012ff3  call    MupFindMatchingChar
0x140012ff8  add     rax, 2
0x140012ffc  mov     ecx, 102h
0x140013001  mov     [rbp+Source.Buffer], rax
0x140013005  mov     r8d, 2070754Dh
0x14001300b  sub     rax, rdx
0x14001300e  sar     rax, 1
0x140013011  sub     r9w, ax
0x140013015  add     r9w, r9w
0x140013019  movzx   eax, r9w
0x14001301d  mov     [rbp+Source.Length], ax
0x140013021  mov     [rbp+Source.MaximumLength], ax
0x140013025  lea     ebx, [rax+1Ah]
0x140013028  mov     edx, ebx
0x14001302a  call    cs:__imp_ExAllocatePool2
0x140013031  nop     dword ptr [rax+rax+00h]
0x140013036  lea     r15, WPP_GLOBAL_Control
0x14001303d  mov     rsi, rax
0x140013040  test    rax, rax
0x140013043  jz      loc_140013130
0x140013049  xor     ecx, ecx
0x14001304b  mov     [rbp+Destination.Buffer], rax
0x14001304f  mov     [rbp+Destination.Length], cx
0x140013053  lea     rdx, aDeviceMup; "\\Device\\Mup"
0x14001305a  lea     rcx, [rbp+Destination]; Destination
0x14001305e  mov     [rbp+Destination.MaximumLength], bx
0x140013062  call    cs:__imp_RtlAppendUnicodeToString
0x140013069  nop     dword ptr [rax+rax+00h]
0x14001306e  lea     rdx, asc_140007964; "\\"
0x140013075  lea     rcx, [rbp+Destination]; Destination
0x140013079  call    cs:__imp_RtlAppendUnicodeToString
0x140013080  nop     dword ptr [rax+rax+00h]
0x140013085  lea     rdx, asc_140007968; ";"
0x14001308c  lea     rcx, [rbp+Destination]; Destination
0x140013090  call    cs:__imp_RtlAppendUnicodeToString
0x140013097  nop     dword ptr [rax+rax+00h]
0x14001309c  lea     rdx, [rbp+Source]; Source
0x1400130a0  lea     rcx, [rbp+Destination]; Destination
0x1400130a4  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400130ab  nop     dword ptr [rax+rax+00h]
0x1400130b0  mov     rcx, rdi; SymbolicLinkName
0x1400130b3  call    cs:__imp_IoDeleteSymbolicLink
0x1400130ba  nop     dword ptr [rax+rax+00h]
0x1400130bf  mov     ebx, eax
0x1400130c1  test    eax, eax
0x1400130c3  jz      short loc_1400130CC
0x1400130c5  cmp     eax, 0C0000034h
0x1400130ca  jnz     short loc_140013119
0x1400130cc  lea     rdx, [rbp+Destination]; DeviceName
0x1400130d0  mov     rcx, rdi; SymbolicLinkName
0x1400130d3  call    cs:__imp_IoCreateSymbolicLink
0x1400130da  nop     dword ptr [rax+rax+00h]
0x1400130df  mov     ebx, eax
0x1400130e1  test    eax, eax
0x1400130e3  jnz     short loc_140013119
0x1400130e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400130ec  cmp     rcx, r15
0x1400130ef  jz      short loc_140013119
0x1400130f1  test    dword ptr [rcx+2Ch], 4000000h
0x1400130f8  jz      short loc_140013119
0x1400130fa  mov     rcx, [rcx+18h]
0x1400130fe  lea     edx, [rax+16h]
0x140013101  lea     rax, [rbp+Destination]
0x140013105  mov     r9, rdi
0x140013108  lea     r8, WPP_b8ec61bc8b283db232150b702b34e2f1_Traceguids
0x14001310f  mov     [rsp+50h+var_30], rax
0x140013114  call    WPP_SF_ZZ
0x140013119  xor     edx, edx; Tag
0x14001311b  mov     rcx, rsi; P
0x14001311e  call    cs:__imp_ExFreePoolWithTag
0x140013125  nop     dword ptr [rax+rax+00h]
0x14001312a  test    ebx, ebx
0x14001312c  jz      short loc_140013162
0x14001312e  jmp     short loc_140013135
0x140013130  mov     ebx, 0C000009Ah
0x140013135  mov     rcx, cs:WPP_GLOBAL_Control
0x14001313c  cmp     rcx, r15
0x14001313f  jz      short loc_140013162
0x140013141  test    dword ptr [rcx+2Ch], 4000000h
0x140013148  jz      short loc_140013162
0x14001314a  mov     rcx, [rcx+18h]
0x14001314e  lea     r8, WPP_b8ec61bc8b283db232150b702b34e2f1_Traceguids
0x140013155  mov     edx, 17h
0x14001315a  mov     r9d, ebx
0x14001315d  call    WPP_SF_d
0x140013162  mov     eax, ebx
0x140013164  add     rsp, 50h
0x140013168  pop     r15
0x14001316a  pop     rdi
0x14001316b  pop     rsi
0x14001316c  pop     rbx
0x14001316d  pop     rbp
0x14001316e  retn
```
