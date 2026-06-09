# DrDevice::CreateReferenceString(_UNICODE_STRING *)

- ea: `0x140029aa8`
- end: `0x140029c7e`
- name: `?CreateReferenceString@DrDevice@@QEAAXPEAU_UNICODE_STRING@@@Z`
- size: `470`
- prototype: `void __fastcall(DrDevice *this, struct _UNICODE_STRING *)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x14001e5d0`
- `0x14001ede0`
- `0x140029174`
- `0x140029228`

## callees

- `0x1400035a0`
- `0x140006480`
- `0x140029aa8`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeToString` at `0x140029b27`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140029b8a`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140029bdd`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140029bf3`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140029c09`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140029b27`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140029b8a`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140029bdd`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140029bf3`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140029c09`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x140029bb4`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x140029bb4`
- `ntoskrnl!RtlInitAnsiString` at `0x140029b4a`
- `ntoskrnl!RtlInitAnsiString` at `0x140029b4a`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x140029b61`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x140029b61`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140029b74`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140029bc7`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140029c1c`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140029b74`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140029bc7`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140029c1c`

## pseudocode

```c
void __fastcall DrDevice::CreateReferenceString(DrDevice *this, struct _UNICODE_STRING *a2)
{
  __int64 v3; // rax
  ULONG v5; // esi
  bool v6; // cc
  UNICODE_STRING Source; // [rsp+20h] [rbp-49h] BYREF
  struct _UNICODE_STRING String; // [rsp+30h] [rbp-39h] BYREF
  _STRING DestinationString; // [rsp+40h] [rbp-29h] BYREF
  _DWORD v10[10]; // [rsp+50h] [rbp-19h] BYREF
  _DWORD v11[10]; // [rsp+78h] [rbp+Fh] BYREF

  memset(v10, 0, 34);
  memset(v11, 0, 34);
  v3 = *((_QWORD *)this + 4);
  DestinationString = 0;
  Source = 0;
  String = 0;
  v5 = *(_DWORD *)(v3 + 1128);
  v6 = a2->MaximumLength <= 2u;
  a2->Length = 0;
  if ( !v6 )
    *a2->Buffer = 0;
  RtlAppendUnicodeToString(a2, L"\\;");
  *(_DWORD *)&Source.Length = 0x200000;
  Source.Buffer = (wchar_t *)v11;
  RtlInitAnsiString(&DestinationString, (PCSZ)this + 48);
  RtlAnsiStringToUnicodeString(&Source, &DestinationString, 0);
  RtlAppendUnicodeStringToString(a2, &Source);
  RtlAppendUnicodeToString(a2, L":");
  *(_DWORD *)&String.Length = 0x200000;
  String.Buffer = (wchar_t *)v10;
  LOWORD(v10[0]) = 0;
  RtlIntegerToUnicodeString(v5, 0xAu, &String);
  RtlAppendUnicodeStringToString(a2, &String);
  RtlAppendUnicodeToString(a2, L"\\");
  RtlAppendUnicodeToString(a2, L"tsclient");
  RtlAppendUnicodeToString(a2, L"\\");
  RtlAppendUnicodeStringToString(a2, &Source);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids, a2);
}

```

## disassembly

```asm
0x140029aa8  mov     [rsp-8+arg_10], rbx
0x140029aad  mov     [rsp-8+arg_18], rsi
0x140029ab2  push    rbp
0x140029ab3  push    rdi
0x140029ab4  push    r14
0x140029ab6  lea     rbp, [rsp-47h]
0x140029abb  sub     rsp, 0B0h
0x140029ac2  mov     rax, cs:__security_cookie
0x140029ac9  xor     rax, rsp
0x140029acc  mov     [rbp+57h+var_20], rax
0x140029ad0  xorps   xmm0, xmm0
0x140029ad3  xor     eax, eax
0x140029ad5  mov     [rbp+57h+var_70], eax
0x140029ad8  xorps   xmm1, xmm1
0x140029adb  mov     [rbp+57h+var_48], eax
0x140029ade  mov     rbx, rdx
0x140029ae1  mov     rax, [rcx+20h]
0x140029ae5  mov     rdi, rcx
0x140029ae8  movups  xmmword ptr [rbp+57h+var_6C], xmm0
0x140029aec  movups  xmmword ptr [rbp+57h+var_44], xmm0
0x140029af0  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140029af4  movups  xmmword ptr [rbp+57h+var_6C+0Eh], xmm0
0x140029af8  movups  xmmword ptr [rbp+57h+var_44+0Eh], xmm0
0x140029afc  movups  xmmword ptr [rbp+57h+Source.Length], xmm0
0x140029b00  movups  xmmword ptr [rbp+57h+String.Length], xmm1
0x140029b04  mov     esi, [rax+468h]
0x140029b0a  xor     eax, eax
0x140029b0c  cmp     word ptr [rdx+2], 2
0x140029b11  mov     [rdx], ax
0x140029b14  jbe     short loc_140029B1D
0x140029b16  mov     rcx, [rdx+8]
0x140029b1a  mov     [rcx], ax
0x140029b1d  lea     rdx, asc_140008D18; "\\;"
0x140029b24  mov     rcx, rbx; Destination
0x140029b27  call    cs:__imp_RtlAppendUnicodeToString
0x140029b2e  nop     dword ptr [rax+rax+00h]
0x140029b33  lea     rax, [rbp+57h+var_48]
0x140029b37  mov     dword ptr [rbp+57h+Source.Length], 200000h
0x140029b3e  lea     rdx, [rdi+30h]; SourceString
0x140029b42  mov     [rbp+57h+Source.Buffer], rax
0x140029b46  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140029b4a  call    cs:__imp_RtlInitAnsiString
0x140029b51  nop     dword ptr [rax+rax+00h]
0x140029b56  xor     r8d, r8d; AllocateDestinationString
0x140029b59  lea     rdx, [rbp+57h+DestinationString]; SourceString
0x140029b5d  lea     rcx, [rbp+57h+Source]; DestinationString
0x140029b61  call    cs:__imp_RtlAnsiStringToUnicodeString
0x140029b68  nop     dword ptr [rax+rax+00h]
0x140029b6d  lea     rdx, [rbp+57h+Source]; Source
0x140029b71  mov     rcx, rbx; Destination
0x140029b74  call    cs:__imp_RtlAppendUnicodeStringToString
0x140029b7b  nop     dword ptr [rax+rax+00h]
0x140029b80  lea     rdx, asc_140008D14; ":"
0x140029b87  mov     rcx, rbx; Destination
0x140029b8a  call    cs:__imp_RtlAppendUnicodeToString
0x140029b91  nop     dword ptr [rax+rax+00h]
0x140029b96  lea     rax, [rbp+57h+var_70]
0x140029b9a  mov     dword ptr [rbp+57h+String.Length], 200000h
0x140029ba1  mov     [rbp+57h+String.Buffer], rax
0x140029ba5  lea     r8, [rbp+57h+String]; String
0x140029ba9  xor     eax, eax
0x140029bab  mov     ecx, esi; Value
0x140029bad  mov     word ptr [rbp+57h+var_70], ax
0x140029bb1  lea     edx, [rax+0Ah]; Base
0x140029bb4  call    cs:__imp_RtlIntegerToUnicodeString
0x140029bbb  nop     dword ptr [rax+rax+00h]
0x140029bc0  lea     rdx, [rbp+57h+String]; Source
0x140029bc4  mov     rcx, rbx; Destination
0x140029bc7  call    cs:__imp_RtlAppendUnicodeStringToString
0x140029bce  nop     dword ptr [rax+rax+00h]
0x140029bd3  lea     rdx, asc_140008CF8; "\\"
0x140029bda  mov     rcx, rbx; Destination
0x140029bdd  call    cs:__imp_RtlAppendUnicodeToString
0x140029be4  nop     dword ptr [rax+rax+00h]
0x140029be9  lea     rdx, aTsclient; "tsclient"
0x140029bf0  mov     rcx, rbx; Destination
0x140029bf3  call    cs:__imp_RtlAppendUnicodeToString
0x140029bfa  nop     dword ptr [rax+rax+00h]
0x140029bff  lea     rdx, asc_140008CF8; "\\"
0x140029c06  mov     rcx, rbx; Destination
0x140029c09  call    cs:__imp_RtlAppendUnicodeToString
0x140029c10  nop     dword ptr [rax+rax+00h]
0x140029c15  lea     rdx, [rbp+57h+Source]; Source
0x140029c19  mov     rcx, rbx; Destination
0x140029c1c  call    cs:__imp_RtlAppendUnicodeStringToString
0x140029c23  nop     dword ptr [rax+rax+00h]
0x140029c28  mov     rcx, cs:WPP_GLOBAL_Control
0x140029c2f  lea     rax, WPP_GLOBAL_Control
0x140029c36  cmp     rcx, rax
0x140029c39  jz      short loc_140029C59
0x140029c3b  cmp     byte ptr [rcx+29h], 4
0x140029c3f  jb      short loc_140029C59
0x140029c41  mov     rcx, [rcx+18h]
0x140029c45  lea     r8, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids
0x140029c4c  mov     edx, 0Dh
0x140029c51  mov     r9, rbx
0x140029c54  call    WPP_SF_Z
0x140029c59  mov     rcx, [rbp+57h+var_20]
0x140029c5d  xor     rcx, rsp; StackCookie
0x140029c60  call    __security_check_cookie
0x140029c65  lea     r11, [rsp+0C0h+var_10]
0x140029c6d  mov     rbx, [r11+30h]
0x140029c71  mov     rsi, [r11+38h]
0x140029c75  mov     rsp, r11
0x140029c78  pop     r14
0x140029c7a  pop     rdi
0x140029c7b  pop     rbp
0x140029c7c  retn
```
