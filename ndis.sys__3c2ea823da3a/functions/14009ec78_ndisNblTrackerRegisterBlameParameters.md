# ndisNblTrackerRegisterBlameParameters

- ea: `0x14009ec78`
- end: `0x14009eea4`
- name: `ndisNblTrackerRegisterBlameParameters`
- size: `556`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x14009eeac`

## callees

- `0x140028e00`
- `0x1400837e0`
- `0x14008c914`
- `0x14009ec78`
- `0x1400e6160`
- `0x1400e65c0`
- `0x14013a1a4`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x14009ee73`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14009ee73`
- `ntoskrnl!ZwQuerySystemInformation` at `0x14009ed4d`
- `ntoskrnl!ZwQuerySystemInformation` at `0x14009ed4d`
- `ntoskrnl!IoQueryFullDriverPath` at `0x14009edee`
- `ntoskrnl!IoQueryFullDriverPath` at `0x14009edee`
- `ntoskrnl!RtlInitAnsiString` at `0x14009ed85`
- `ntoskrnl!RtlInitAnsiString` at `0x14009ed85`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x14009ed9e`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x14009ed9e`

## pseudocode

```c
void __fastcall ndisNblTrackerRegisterBlameParameters(__int64 a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  struct _UNICODE_STRING *p_UnicodeString; // rdx
  __int64 v6; // rax
  __int64 v7; // r8
  __int64 v8; // rbx
  NTSTATUS v9; // eax
  int v10; // edx
  int v11; // r9d
  __int64 v12; // rcx
  __int64 v13; // r9
  __int64 v14; // rax
  _BYTE v15[8]; // [rsp+30h] [rbp-D0h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+38h] [rbp-C8h] BYREF
  struct _STRING DestinationString; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD SystemInformation[42]; // [rsp+60h] [rbp-A0h] BYREF
  char v19; // [rsp+1B0h] [rbp+B0h] BYREF

  if ( a2[6] )
  {
    p_UnicodeString = (struct _UNICODE_STRING *)a2[6];
LABEL_3:
    LOBYTE(a4) = 1;
    v6 = Rtl::DuplicateUnicodeString(v15, p_UnicodeString, 1802781774, a4);
    wistd::unique_ptr<_UNICODE_STRING,KFreePool<_UNICODE_STRING>>::operator=(a1 + 40, v6);
    wistd::unique_ptr<_UNICODE_STRING,KFreePool<_UNICODE_STRING>>::reset(v15, 0);
    return;
  }
  v7 = a2[4];
  if ( v7 || a2[5] )
  {
    v12 = a2[5];
    UnicodeString = 0;
    if ( !v12 )
      v12 = *(_QWORD *)(v7 + 8);
    v9 = IoQueryFullDriverPath(v12, &UnicodeString);
    if ( v9 < 0 )
    {
      if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        return;
      v11 = 15;
      goto LABEL_19;
    }
    LOBYTE(v13) = 1;
    v14 = Rtl::DuplicateUnicodeString(v15, &UnicodeString, 1802781774, v13);
    wistd::unique_ptr<_UNICODE_STRING,KFreePool<_UNICODE_STRING>>::operator=(a1 + 40, v14);
    wistd::unique_ptr<_UNICODE_STRING,KFreePool<_UNICODE_STRING>>::reset(v15, 0);
    RtlFreeUnicodeString(&UnicodeString);
  }
  else
  {
    v8 = a2[3];
    if ( !v8 )
      return;
    *(_QWORD *)&UnicodeString.Length = 0x2000000;
    UnicodeString.Buffer = (wchar_t *)&v19;
    DestinationString = 0;
    memset(&SystemInformation[1], 0, 0x140u);
    SystemInformation[0] = v8;
    v9 = ZwQuerySystemInformation(SystemSingleModuleInformation, SystemInformation, 0x148u, 0);
    if ( v9 < 0 )
    {
      if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        return;
      v11 = 16;
      goto LABEL_19;
    }
    RtlInitAnsiString(&DestinationString, (PCSZ)&SystemInformation[7]);
    v9 = RtlAnsiStringToUnicodeString(&UnicodeString, &DestinationString, 0);
    if ( v9 >= 0 )
    {
      p_UnicodeString = &UnicodeString;
      goto LABEL_3;
    }
    if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v11 = 17;
LABEL_19:
      LOBYTE(v10) = 3;
      WPP_RECORDER_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        v10,
        1,
        v11,
        (struct _GUID *)&WPP_fb5189d909373e0ec25494923af71c39_Traceguids,
        v9);
    }
  }
}

```

## disassembly

```asm
0x14009ec78  mov     [rsp-8+arg_10], rbx
0x14009ec7d  mov     [rsp-8+arg_18], rdi
0x14009ec82  push    rbp
0x14009ec83  lea     rbp, [rsp-2C0h]
0x14009ec8b  sub     rsp, 3C0h
0x14009ec92  mov     rax, cs:__security_cookie
0x14009ec99  xor     rax, rsp
0x14009ec9c  mov     [rbp+2C0h+var_10], rax
0x14009eca3  mov     rax, [rdx+30h]
0x14009eca7  mov     rdi, rcx
0x14009ecaa  test    rax, rax
0x14009ecad  jz      short loc_14009ECE2
0x14009ecaf  mov     rdx, rax
0x14009ecb2  mov     r8d, 6B74444Eh
0x14009ecb8  lea     rcx, [rsp+3C0h+var_390]
0x14009ecbd  mov     r9b, 1
0x14009ecc0  call    ?DuplicateUnicodeString@Rtl@@YA?AV?$unique_ptr@U_UNICODE_STRING@@U?$KFreePool@U_UNICODE_STRING@@@@@wistd@@AEBU_UNICODE_STRING@@K_N@Z; Rtl::DuplicateUnicodeString(_UNICODE_STRING const &,ulong,bool)
0x14009ecc5  mov     rdx, rax
0x14009ecc8  lea     rcx, [rdi+28h]
0x14009eccc  call    ??4?$unique_ptr@U_UNICODE_STRING@@U?$KFreePool@U_UNICODE_STRING@@@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<_UNICODE_STRING,KFreePool<_UNICODE_STRING>>::operator=(wistd::unique_ptr<_UNICODE_STRING,KFreePool<_UNICODE_STRING>> &&)
0x14009ecd1  xor     edx, edx
0x14009ecd3  lea     rcx, [rsp+3C0h+var_390]
0x14009ecd8  call    ?reset@?$unique_ptr@U_UNICODE_STRING@@U?$KFreePool@U_UNICODE_STRING@@@@@wistd@@QEAAXPEAU_UNICODE_STRING@@@Z; wistd::unique_ptr<_UNICODE_STRING,KFreePool<_UNICODE_STRING>>::reset(_UNICODE_STRING *)
0x14009ecdd  jmp     loc_14009EE7F
0x14009ece2  mov     r8, [rdx+20h]
0x14009ece6  test    r8, r8
0x14009ece9  jnz     loc_14009EDD4
0x14009ecef  cmp     [rdx+28h], r8
0x14009ecf3  jnz     loc_14009EDD4
0x14009ecf9  mov     rbx, [rdx+18h]
0x14009ecfd  test    rbx, rbx
0x14009ed00  jz      loc_14009EE7F
0x14009ed06  xorps   xmm0, xmm0
0x14009ed09  mov     qword ptr [rsp+3C0h+UnicodeString.Length], 2000000h
0x14009ed12  lea     rax, [rbp+2C0h+var_210]
0x14009ed19  xor     edx, edx; Val
0x14009ed1b  mov     r8d, 140h; Size
0x14009ed21  mov     [rsp+3C0h+UnicodeString.Buffer], rax
0x14009ed26  lea     rcx, [rsp+3C0h+var_358]; void *
0x14009ed2b  movups  xmmword ptr [rsp+3C0h+DestinationString.Length], xmm0
0x14009ed30  call    memset
0x14009ed35  xor     r9d, r9d; ReturnLength
0x14009ed38  mov     [rsp+3C0h+SystemInformation], rbx
0x14009ed3d  mov     r8d, 148h; SystemInformationLength
0x14009ed43  lea     rdx, [rsp+3C0h+SystemInformation]; SystemInformation
0x14009ed48  mov     ecx, 0A7h; SystemInformationClass
0x14009ed4d  call    cs:__imp_ZwQuerySystemInformation
0x14009ed54  nop     dword ptr [rax+rax+00h]
0x14009ed59  test    eax, eax
0x14009ed5b  jns     short loc_14009ED7C
0x14009ed5d  lea     rcx, WPP_RECORDER_INITIALIZED
0x14009ed64  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14009ed6b  jz      loc_14009EE7F
0x14009ed71  mov     r9d, 10h
0x14009ed77  jmp     loc_14009EE14
0x14009ed7c  lea     rdx, [rbp+2C0h+SourceString]; SourceString
0x14009ed80  lea     rcx, [rsp+3C0h+DestinationString]; DestinationString
0x14009ed85  call    cs:__imp_RtlInitAnsiString
0x14009ed8c  nop     dword ptr [rax+rax+00h]
0x14009ed91  xor     r8d, r8d; AllocateDestinationString
0x14009ed94  lea     rdx, [rsp+3C0h+DestinationString]; SourceString
0x14009ed99  lea     rcx, [rsp+3C0h+UnicodeString]; DestinationString
0x14009ed9e  call    cs:__imp_RtlAnsiStringToUnicodeString
0x14009eda5  nop     dword ptr [rax+rax+00h]
0x14009edaa  test    eax, eax
0x14009edac  jns     short loc_14009EDCA
0x14009edae  lea     rcx, WPP_RECORDER_INITIALIZED
0x14009edb5  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14009edbc  jz      loc_14009EE7F
0x14009edc2  mov     r9d, 11h
0x14009edc8  jmp     short loc_14009EE14
0x14009edca  lea     rdx, [rsp+3C0h+UnicodeString]
0x14009edcf  jmp     loc_14009ECB2
0x14009edd4  mov     rcx, [rdx+28h]
0x14009edd8  xorps   xmm0, xmm0
0x14009eddb  movups  xmmword ptr [rsp+3C0h+UnicodeString.Length], xmm0
0x14009ede0  test    rcx, rcx
0x14009ede3  jnz     short loc_14009EDE9
0x14009ede5  mov     rcx, [r8+8]
0x14009ede9  lea     rdx, [rsp+3C0h+UnicodeString]
0x14009edee  call    cs:__imp_IoQueryFullDriverPath
0x14009edf5  nop     dword ptr [rax+rax+00h]
0x14009edfa  test    eax, eax
0x14009edfc  jns     short loc_14009EE3E
0x14009edfe  lea     rcx, WPP_RECORDER_INITIALIZED
0x14009ee05  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14009ee0c  jz      short loc_14009EE7F
0x14009ee0e  mov     r9d, 0Fh; int
0x14009ee14  mov     rcx, cs:WPP_GLOBAL_Control
0x14009ee1b  mov     r8d, 1; int
0x14009ee21  mov     dword ptr [rsp+3C0h+var_398], eax; char
0x14009ee25  mov     dl, 3; int
0x14009ee27  lea     rax, WPP_fb5189d909373e0ec25494923af71c39_Traceguids
0x14009ee2e  mov     [rsp+3C0h+var_3A0], rax; struct _GUID *
0x14009ee33  mov     rcx, [rcx+40h]; int
0x14009ee37  call    WPP_RECORDER_SF_d
0x14009ee3c  jmp     short loc_14009EE7F
0x14009ee3e  mov     r9b, 1
0x14009ee41  lea     rdx, [rsp+3C0h+UnicodeString]
0x14009ee46  mov     r8d, 6B74444Eh
0x14009ee4c  lea     rcx, [rsp+3C0h+var_390]
0x14009ee51  call    ?DuplicateUnicodeString@Rtl@@YA?AV?$unique_ptr@U_UNICODE_STRING@@U?$KFreePool@U_UNICODE_STRING@@@@@wistd@@AEBU_UNICODE_STRING@@K_N@Z; Rtl::DuplicateUnicodeString(_UNICODE_STRING const &,ulong,bool)
0x14009ee56  mov     rdx, rax
0x14009ee59  lea     rcx, [rdi+28h]
0x14009ee5d  call    ??4?$unique_ptr@U_UNICODE_STRING@@U?$KFreePool@U_UNICODE_STRING@@@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<_UNICODE_STRING,KFreePool<_UNICODE_STRING>>::operator=(wistd::unique_ptr<_UNICODE_STRING,KFreePool<_UNICODE_STRING>> &&)
0x14009ee62  xor     edx, edx
0x14009ee64  lea     rcx, [rsp+3C0h+var_390]
0x14009ee69  call    ?reset@?$unique_ptr@U_UNICODE_STRING@@U?$KFreePool@U_UNICODE_STRING@@@@@wistd@@QEAAXPEAU_UNICODE_STRING@@@Z; wistd::unique_ptr<_UNICODE_STRING,KFreePool<_UNICODE_STRING>>::reset(_UNICODE_STRING *)
0x14009ee6e  lea     rcx, [rsp+3C0h+UnicodeString]; UnicodeString
0x14009ee73  call    cs:__imp_RtlFreeUnicodeString
0x14009ee7a  nop     dword ptr [rax+rax+00h]
0x14009ee7f  mov     rcx, [rbp+2C0h+var_10]
0x14009ee86  xor     rcx, rsp; StackCookie
0x14009ee89  call    __security_check_cookie
0x14009ee8e  lea     r11, [rsp+3C0h+var_s0]
0x14009ee96  mov     rbx, [r11+20h]
0x14009ee9a  mov     rdi, [r11+28h]
0x14009ee9e  mov     rsp, r11
0x14009eea1  pop     rbp
0x14009eea2  retn
```
