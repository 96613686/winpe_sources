# LoadCurveInKernelMode

- ea: `0x18003dc20`
- end: `0x18003dffe`
- name: `LoadCurveInKernelMode`
- size: `990`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180041b20`

## callees

- `0x180003f70`
- `0x180006470`
- `0x1800082b0`
- `0x18003dc20`
- `0x18003e004`
- `0x1800496a4`
- `0x18009fa80`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18003dcfe`
- `ntoskrnl!RtlInitUnicodeString` at `0x18003dcfe`
- `ntoskrnl!ZwQueryValueKey` at `0x18003dd67`
- `ntoskrnl!ZwQueryValueKey` at `0x18003ddc0`
- `ntoskrnl!ZwQueryValueKey` at `0x18003dd67`
- `ntoskrnl!ZwQueryValueKey` at `0x18003ddc0`
- `ntoskrnl!ZwClose` at `0x18003de60`
- `ntoskrnl!ZwClose` at `0x18003de60`
- `ntoskrnl!ZwOpenKey` at `0x18003dd35`
- `ntoskrnl!ZwOpenKey` at `0x18003dd35`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18003dca9`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18003dcbf`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18003dcd5`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18003dce7`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18003dca9`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18003dcbf`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18003dcd5`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18003dce7`

## string_xrefs

- `0x18003de2f`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x18003dec7`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x18003df6b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x18003dfd1`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x18003dc97`: `\Registry\MACHINE\`

## pseudocode

```c
__int64 __fastcall LoadCurveInKernelMode(_QWORD *a1, __int64 a2, const WCHAR *a3, __int64 a4)
{
  USHORT v4; // bx
  void *v6; // rsi
  int v7; // r15d
  _DWORD *v9; // rdi
  struct _UNICODE_STRING *v10; // rax
  int v11; // edx
  int v12; // r8d
  struct _UNICODE_STRING *v13; // r14
  __int64 v14; // rdx
  NTSTATUS v15; // ebx
  __int64 v16; // r8
  __int64 v17; // r9
  _DWORD *v18; // rax
  int v19; // r8d
  int v20; // edx
  int v21; // r8d
  _QWORD *v22; // rcx
  int v24; // edx
  char v25; // [rsp+30h] [rbp-39h]
  void *v26; // [rsp+40h] [rbp-29h] BYREF
  void *KeyHandle; // [rsp+48h] [rbp-21h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-19h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-9h] BYREF
  int v30; // [rsp+D8h] [rbp+6Fh]
  ULONG ResultLength; // [rsp+E8h] [rbp+7Fh] BYREF

  v30 = a2;
  v4 = a4 + 160;
  v6 = 0;
  v26 = 0;
  v7 = a4;
  KeyHandle = 0;
  ResultLength = 0;
  DestinationString = 0;
  v9 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v10 = (struct _UNICODE_STRING *)MSCryptAlloc((unsigned int)(a4 + 160) + 16LL, a2, a3, a4);
  v13 = v10;
  if ( v10 )
  {
    v10->MaximumLength = v4;
    v10->Length = 0;
    v10->Buffer = &v10[1].Length;
    RtlAppendUnicodeToString(v10, L"\\Registry\\MACHINE\\");
    RtlAppendUnicodeToString(v13, L"SYSTEM\\CurrentControlSet\\Control\\Cryptography\\ECCParameters");
    RtlAppendUnicodeToString(v13, L"\\");
    RtlAppendUnicodeToString(v13, a3);
    RtlInitUnicodeString(&DestinationString, L"Parameters");
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    ObjectAttributes.ObjectName = v13;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v15 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
    if ( v15 < 0 )
    {
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0 )
        goto LABEL_12;
      v25 = -63;
    }
    else
    {
      v15 = ZwQueryValueKey(KeyHandle, &DestinationString, KeyValueFullInformation, 0, 0, &ResultLength);
      if ( v15 >= 0 || v15 == -1073741789 || v15 == -2147483643 )
      {
        v18 = (_DWORD *)MSCryptAlloc(ResultLength, v14, v16, v17);
        v9 = v18;
        if ( !v18 )
        {
          v15 = -1073741801;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
          {
            v24 = *((_DWORD *)WPP_GLOBAL_Control + 11);
            if ( (v24 & 1) != 0 )
              WPP_SF_sDsd(
                *((_QWORD *)WPP_GLOBAL_Control + 3),
                v24,
                v19,
                (unsigned int)"Status",
                23,
                (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
                209);
          }
          goto LABEL_12;
        }
        memset(v18, 0, ResultLength);
        v15 = ZwQueryValueKey(KeyHandle, &DestinationString, KeyValueFullInformation, v9, ResultLength, &ResultLength);
        if ( v15 >= 0 )
        {
          v15 = AssignGenericDomainParameters((unsigned int)&v26, v30, (int)v9 + v9[2], v9[3], (__int64)a3, v7);
          if ( v15 < 0 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
            {
              WPP_SF_sDsd(
                *((_QWORD *)WPP_GLOBAL_Control + 3),
                v20,
                v21,
                (unsigned int)"Status",
                v15,
                (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
                236);
            }
            v6 = v26;
          }
          else
          {
            v15 = 0;
            *a1 = v26;
          }
          goto LABEL_12;
        }
        v22 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0 )
        {
LABEL_12:
          MSCryptFree(v13);
          goto LABEL_13;
        }
        v25 = -33;
      }
      else
      {
        v22 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0 )
          goto LABEL_12;
        v25 = -27;
      }
    }
    WPP_SF_sDsd(
      v22[3],
      v14,
      v16,
      (unsigned int)"Status",
      v15,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
      v25);
    goto LABEL_12;
  }
  v15 = -1073741801;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v11,
      v12,
      (unsigned int)"Status",
      23,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
      169);
LABEL_13:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( v9 )
    MSCryptFree(v9);
  if ( v6 )
    FreeGenericEccKeyParameters(v6);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18003dc20  mov     [rsp-8+arg_0], rbx
0x18003dc25  mov     [rsp-8+arg_8], edx
0x18003dc29  push    rbp
0x18003dc2a  push    rsi
0x18003dc2b  push    rdi
0x18003dc2c  push    r12
0x18003dc2e  push    r13
0x18003dc30  push    r14
0x18003dc32  push    r15
0x18003dc34  lea     rbp, [rsp-27h]
0x18003dc39  sub     rsp, 90h
0x18003dc40  xorps   xmm1, xmm1
0x18003dc43  lea     ebx, [r9+0A0h]
0x18003dc4a  mov     r13, rcx
0x18003dc4d  xor     esi, esi
0x18003dc4f  xorps   xmm0, xmm0
0x18003dc52  mov     ecx, ebx
0x18003dc54  add     rcx, 10h
0x18003dc58  mov     [rbp+57h+var_80], rsi
0x18003dc5c  mov     r15d, r9d
0x18003dc5f  mov     [rbp+57h+KeyHandle], rsi
0x18003dc63  mov     r12, r8
0x18003dc66  mov     [rbp+57h+arg_18], esi
0x18003dc69  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18003dc6d  xor     edi, edi
0x18003dc6f  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x18003dc73  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x18003dc77  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x18003dc7b  call    MSCryptAlloc
0x18003dc80  mov     r14, rax
0x18003dc83  test    rax, rax
0x18003dc86  jz      loc_18003DEA4
0x18003dc8c  xor     eax, eax
0x18003dc8e  mov     [r14+2], bx
0x18003dc93  mov     [r14], ax
0x18003dc97  lea     rdx, aRegistryMachin_16; "\\Registry\\MACHINE\\"
0x18003dc9e  lea     rax, [r14+10h]
0x18003dca2  mov     rcx, r14; Destination
0x18003dca5  mov     [r14+8], rax
0x18003dca9  call    cs:__imp_RtlAppendUnicodeToString
0x18003dcb0  nop     dword ptr [rax+rax+00h]
0x18003dcb5  lea     rdx, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Control\\Cry"...
0x18003dcbc  mov     rcx, r14; Destination
0x18003dcbf  call    cs:__imp_RtlAppendUnicodeToString
0x18003dcc6  nop     dword ptr [rax+rax+00h]
0x18003dccb  lea     rdx, asc_1800B0C40; "\\"
0x18003dcd2  mov     rcx, r14; Destination
0x18003dcd5  call    cs:__imp_RtlAppendUnicodeToString
0x18003dcdc  nop     dword ptr [rax+rax+00h]
0x18003dce1  mov     rdx, r12; Source
0x18003dce4  mov     rcx, r14; Destination
0x18003dce7  call    cs:__imp_RtlAppendUnicodeToString
0x18003dcee  nop     dword ptr [rax+rax+00h]
0x18003dcf3  lea     rdx, aParameters; "Parameters"
0x18003dcfa  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18003dcfe  call    cs:__imp_RtlInitUnicodeString
0x18003dd05  nop     dword ptr [rax+rax+00h]
0x18003dd0a  xorps   xmm0, xmm0
0x18003dd0d  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18003dd14  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18003dd18  mov     [rbp+57h+ObjectAttributes.RootDirectory], rsi
0x18003dd1c  mov     edx, 20019h; DesiredAccess
0x18003dd21  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x18003dd28  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18003dd2c  mov     [rbp+57h+ObjectAttributes.ObjectName], r14
0x18003dd30  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18003dd35  call    cs:__imp_ZwOpenKey
0x18003dd3c  nop     dword ptr [rax+rax+00h]
0x18003dd41  mov     ebx, eax
0x18003dd43  test    eax, eax
0x18003dd45  js      loc_18003DE0D
0x18003dd4b  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18003dd4f  lea     rax, [rbp+57h+arg_18]
0x18003dd53  mov     [rsp+0C0h+ResultLength], rax; ResultLength
0x18003dd58  lea     r8d, [rsi+1]; KeyValueInformationClass
0x18003dd5c  xor     r9d, r9d; KeyValueInformation
0x18003dd5f  mov     [rsp+0C0h+Length], esi; Length
0x18003dd63  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x18003dd67  call    cs:__imp_ZwQueryValueKey
0x18003dd6e  nop     dword ptr [rax+rax+00h]
0x18003dd73  mov     ebx, eax
0x18003dd75  test    eax, eax
0x18003dd77  js      loc_18003DEF4
0x18003dd7d  mov     ecx, [rbp+57h+arg_18]
0x18003dd80  call    MSCryptAlloc
0x18003dd85  mov     rdi, rax
0x18003dd88  test    rax, rax
0x18003dd8b  jz      loc_18003DF3B
0x18003dd91  mov     r8d, [rbp+57h+arg_18]; Size
0x18003dd95  xor     edx, edx; Val
0x18003dd97  mov     rcx, rax; void *
0x18003dd9a  call    memset
0x18003dd9f  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18003dda3  lea     rax, [rbp+57h+arg_18]
0x18003dda7  mov     [rsp+0C0h+ResultLength], rax; ResultLength
0x18003ddac  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x18003ddb0  mov     eax, [rbp+57h+arg_18]
0x18003ddb3  mov     r9, rdi; KeyValueInformation
0x18003ddb6  mov     r8d, 1; KeyValueInformationClass
0x18003ddbc  mov     [rsp+0C0h+Length], eax; Length
0x18003ddc0  call    cs:__imp_ZwQueryValueKey
0x18003ddc7  nop     dword ptr [rax+rax+00h]
0x18003ddcc  mov     ebx, eax
0x18003ddce  test    eax, eax
0x18003ddd0  js      loc_18003DF84
0x18003ddd6  mov     r8d, [rdi+8]
0x18003ddda  lea     rcx, [rbp+57h+var_80]
0x18003ddde  mov     r9d, [rdi+0Ch]
0x18003dde2  add     r8, rdi
0x18003dde5  mov     edx, [rbp+57h+arg_8]
0x18003dde8  mov     dword ptr [rsp+0C0h+ResultLength], r15d
0x18003dded  mov     qword ptr [rsp+0C0h+Length], r12
0x18003ddf2  call    AssignGenericDomainParameters
0x18003ddf7  mov     ebx, eax
0x18003ddf9  test    eax, eax
0x18003ddfb  js      loc_18003DFB3
0x18003de01  mov     rax, [rbp+57h+var_80]
0x18003de05  xor     ebx, ebx
0x18003de07  mov     [r13+0], rax
0x18003de0b  jmp     short loc_18003DE4F
0x18003de0d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003de14  lea     rax, WPP_GLOBAL_Control
0x18003de1b  cmp     rcx, rax
0x18003de1e  jz      short loc_18003DE4F
0x18003de20  mov     eax, [rcx+2Ch]
0x18003de23  test    al, 1
0x18003de25  jz      short loc_18003DE4F
0x18003de27  mov     dword ptr [rsp+0C0h+var_90], 4C1h
0x18003de2f  lea     rax, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003de36  mov     [rsp+0C0h+ResultLength], rax
0x18003de3b  mov     [rsp+0C0h+Length], ebx
0x18003de3f  mov     rcx, [rcx+18h]
0x18003de43  lea     r9, aStatus; "Status"
0x18003de4a  call    WPP_SF_sDsd
0x18003de4f  mov     rcx, r14; P
0x18003de52  call    MSCryptFree
0x18003de57  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x18003de5b  test    rcx, rcx
0x18003de5e  jz      short loc_18003DE6C
0x18003de60  call    cs:__imp_ZwClose
0x18003de67  nop     dword ptr [rax+rax+00h]
0x18003de6c  test    rdi, rdi
0x18003de6f  jz      short loc_18003DE79
0x18003de71  mov     rcx, rdi; P
0x18003de74  call    MSCryptFree
0x18003de79  test    rsi, rsi
0x18003de7c  jz      short loc_18003DE86
0x18003de7e  mov     rcx, rsi; P
0x18003de81  call    FreeGenericEccKeyParameters
0x18003de86  mov     eax, ebx
0x18003de88  mov     rbx, [rsp+0C0h+arg_0]
0x18003de90  add     rsp, 90h
0x18003de97  pop     r15
0x18003de99  pop     r14
0x18003de9b  pop     r13
0x18003de9d  pop     r12
0x18003de9f  pop     rdi
0x18003dea0  pop     rsi
0x18003dea1  pop     rbp
0x18003dea2  retn
0x18003dea4  mov     ebx, 0C0000017h
0x18003dea9  mov     rcx, cs:WPP_GLOBAL_Control
0x18003deb0  lea     rax, WPP_GLOBAL_Control
0x18003deb7  cmp     rcx, rax
0x18003deba  jz      short loc_18003DE57
0x18003debc  mov     eax, [rcx+2Ch]
0x18003debf  test    al, 1
0x18003dec1  jz      short loc_18003DE57
0x18003dec3  mov     rcx, [rcx+18h]
0x18003dec7  lea     rax, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003dece  mov     dword ptr [rsp+0C0h+var_90], 4A9h
0x18003ded6  lea     r9, aStatus; "Status"
0x18003dedd  mov     [rsp+0C0h+ResultLength], rax
0x18003dee2  mov     [rsp+0C0h+Length], 0C0000017h
0x18003deea  call    WPP_SF_sDsd
0x18003deef  jmp     loc_18003DE57
0x18003def4  cmp     ebx, 0C0000023h
0x18003defa  jz      loc_18003DD7D
0x18003df00  cmp     ebx, 80000005h
0x18003df06  jz      loc_18003DD7D
0x18003df0c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003df13  lea     rax, WPP_GLOBAL_Control
0x18003df1a  cmp     rcx, rax
0x18003df1d  jz      loc_18003DE4F
0x18003df23  mov     eax, [rcx+2Ch]
0x18003df26  test    al, 1
0x18003df28  jz      loc_18003DE4F
0x18003df2e  mov     dword ptr [rsp+0C0h+var_90], 4E5h
0x18003df36  jmp     loc_18003DE2F
0x18003df3b  mov     ebx, 0C0000017h
0x18003df40  mov     rcx, cs:WPP_GLOBAL_Control
0x18003df47  lea     rax, WPP_GLOBAL_Control
0x18003df4e  cmp     rcx, rax
0x18003df51  jz      loc_18003DE4F
0x18003df57  mov     edx, [rcx+2Ch]
0x18003df5a  test    dl, 1
0x18003df5d  jz      loc_18003DE4F
0x18003df63  mov     dword ptr [rsp+0C0h+var_90], 4D1h
0x18003df6b  lea     rax, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003df72  mov     [rsp+0C0h+ResultLength], rax
0x18003df77  mov     [rsp+0C0h+Length], 0C0000017h
0x18003df7f  jmp     loc_18003DE3F
0x18003df84  mov     rcx, cs:WPP_GLOBAL_Control
0x18003df8b  lea     rax, WPP_GLOBAL_Control
0x18003df92  cmp     rcx, rax
0x18003df95  jz      loc_18003DE4F
0x18003df9b  mov     eax, [rcx+2Ch]
0x18003df9e  test    al, 1
0x18003dfa0  jz      loc_18003DE4F
0x18003dfa6  mov     dword ptr [rsp+0C0h+var_90], 4DFh
0x18003dfae  jmp     loc_18003DE2F
0x18003dfb3  mov     rcx, cs:WPP_GLOBAL_Control
0x18003dfba  lea     rax, WPP_GLOBAL_Control
0x18003dfc1  cmp     rcx, rax
0x18003dfc4  jz      short loc_18003DFF5
0x18003dfc6  mov     eax, [rcx+2Ch]
0x18003dfc9  test    al, 1
0x18003dfcb  jz      short loc_18003DFF5
0x18003dfcd  mov     rcx, [rcx+18h]
0x18003dfd1  lea     rax, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003dfd8  mov     dword ptr [rsp+0C0h+var_90], 4ECh
0x18003dfe0  lea     r9, aStatus; "Status"
0x18003dfe7  mov     [rsp+0C0h+ResultLength], rax
0x18003dfec  mov     [rsp+0C0h+Length], ebx
0x18003dff0  call    WPP_SF_sDsd
0x18003dff5  mov     rsi, [rbp+57h+var_80]
0x18003dff9  jmp     loc_18003DE4F
```
