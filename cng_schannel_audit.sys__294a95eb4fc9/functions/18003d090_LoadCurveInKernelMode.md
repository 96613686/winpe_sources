# LoadCurveInKernelMode

- ea: `0x18003d090`
- end: `0x18003d46e`
- name: `LoadCurveInKernelMode`
- size: `990`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180040f90`

## callees

- `0x180003f70`
- `0x180006470`
- `0x1800082b0`
- `0x18003d090`
- `0x18003d474`
- `0x180048c14`
- `0x18009dd40`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18003d16e`
- `ntoskrnl!RtlInitUnicodeString` at `0x18003d16e`
- `ntoskrnl!ZwQueryValueKey` at `0x18003d1d7`
- `ntoskrnl!ZwQueryValueKey` at `0x18003d230`
- `ntoskrnl!ZwQueryValueKey` at `0x18003d1d7`
- `ntoskrnl!ZwQueryValueKey` at `0x18003d230`
- `ntoskrnl!ZwClose` at `0x18003d2d0`
- `ntoskrnl!ZwClose` at `0x18003d2d0`
- `ntoskrnl!ZwOpenKey` at `0x18003d1a5`
- `ntoskrnl!ZwOpenKey` at `0x18003d1a5`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18003d119`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18003d12f`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18003d145`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18003d157`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18003d119`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18003d12f`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18003d145`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18003d157`

## string_xrefs

- `0x18003d29f`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x18003d337`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x18003d3db`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x18003d441`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x18003d107`: `\Registry\MACHINE\`

## pseudocode

```c
__int64 __fastcall LoadCurveInKernelMode(_QWORD *a1, __int64 a2, const WCHAR *a3, int a4)
{
  USHORT v4; // bx
  void *v6; // rsi
  _DWORD *v9; // rdi
  struct _UNICODE_STRING *v10; // rax
  int v11; // edx
  int v12; // r8d
  struct _UNICODE_STRING *v13; // r14
  __int64 v14; // rdx
  NTSTATUS v15; // ebx
  int v16; // r8d
  _DWORD *v17; // rax
  int v18; // r8d
  int v19; // edx
  int v20; // r8d
  _QWORD *v21; // rcx
  int v23; // edx
  char v24; // [rsp+30h] [rbp-39h]
  void *v25; // [rsp+40h] [rbp-29h] BYREF
  void *KeyHandle; // [rsp+48h] [rbp-21h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-19h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-9h] BYREF
  int v29; // [rsp+D8h] [rbp+6Fh]
  ULONG ResultLength; // [rsp+E8h] [rbp+7Fh] BYREF

  v29 = a2;
  v4 = a4 + 160;
  v6 = 0;
  v25 = 0;
  KeyHandle = 0;
  ResultLength = 0;
  DestinationString = 0;
  v9 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v10 = (struct _UNICODE_STRING *)MSCryptAlloc((unsigned int)(a4 + 160) + 16LL, a2);
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
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0 )
        goto LABEL_12;
      v24 = -63;
    }
    else
    {
      v15 = ZwQueryValueKey(KeyHandle, &DestinationString, KeyValueFullInformation, 0, 0, &ResultLength);
      if ( v15 >= 0 || v15 == -1073741789 || v15 == -2147483643 )
      {
        v17 = (_DWORD *)MSCryptAlloc(ResultLength, v14);
        v9 = v17;
        if ( !v17 )
        {
          v15 = -1073741801;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
          {
            v23 = *((_DWORD *)WPP_GLOBAL_Control + 11);
            if ( (v23 & 1) != 0 )
              WPP_SF_sDsd(
                *((_QWORD *)WPP_GLOBAL_Control + 3),
                v23,
                v18,
                (unsigned int)"Status",
                23,
                (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
                209);
          }
          goto LABEL_12;
        }
        memset(v17, 0, ResultLength);
        v15 = ZwQueryValueKey(KeyHandle, &DestinationString, KeyValueFullInformation, v9, ResultLength, &ResultLength);
        if ( v15 >= 0 )
        {
          v15 = AssignGenericDomainParameters((unsigned int)&v25, v29, (int)v9 + v9[2], v9[3], (__int64)a3, a4);
          if ( v15 < 0 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
            {
              WPP_SF_sDsd(
                *((_QWORD *)WPP_GLOBAL_Control + 3),
                v19,
                v20,
                (unsigned int)"Status",
                v15,
                (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
                236);
            }
            v6 = v25;
          }
          else
          {
            v15 = 0;
            *a1 = v25;
          }
          goto LABEL_12;
        }
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0 )
        {
LABEL_12:
          MSCryptFree(v13);
          goto LABEL_13;
        }
        v24 = -33;
      }
      else
      {
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0 )
          goto LABEL_12;
        v24 = -27;
      }
    }
    WPP_SF_sDsd(
      v21[3],
      v14,
      v16,
      (unsigned int)"Status",
      v15,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
      v24);
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
0x18003d090  mov     [rsp-8+arg_0], rbx
0x18003d095  mov     [rsp-8+arg_8], edx
0x18003d099  push    rbp
0x18003d09a  push    rsi
0x18003d09b  push    rdi
0x18003d09c  push    r12
0x18003d09e  push    r13
0x18003d0a0  push    r14
0x18003d0a2  push    r15
0x18003d0a4  lea     rbp, [rsp-27h]
0x18003d0a9  sub     rsp, 90h
0x18003d0b0  xorps   xmm1, xmm1
0x18003d0b3  lea     ebx, [r9+0A0h]
0x18003d0ba  mov     r13, rcx
0x18003d0bd  xor     esi, esi
0x18003d0bf  xorps   xmm0, xmm0
0x18003d0c2  mov     ecx, ebx
0x18003d0c4  add     rcx, 10h
0x18003d0c8  mov     [rbp+57h+var_80], rsi
0x18003d0cc  mov     r15d, r9d
0x18003d0cf  mov     [rbp+57h+KeyHandle], rsi
0x18003d0d3  mov     r12, r8
0x18003d0d6  mov     [rbp+57h+arg_18], esi
0x18003d0d9  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18003d0dd  xor     edi, edi
0x18003d0df  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x18003d0e3  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x18003d0e7  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x18003d0eb  call    MSCryptAlloc
0x18003d0f0  mov     r14, rax
0x18003d0f3  test    rax, rax
0x18003d0f6  jz      loc_18003D314
0x18003d0fc  xor     eax, eax
0x18003d0fe  mov     [r14+2], bx
0x18003d103  mov     [r14], ax
0x18003d107  lea     rdx, aRegistryMachin_16; "\\Registry\\MACHINE\\"
0x18003d10e  lea     rax, [r14+10h]
0x18003d112  mov     rcx, r14; Destination
0x18003d115  mov     [r14+8], rax
0x18003d119  call    cs:__imp_RtlAppendUnicodeToString
0x18003d120  nop     dword ptr [rax+rax+00h]
0x18003d125  lea     rdx, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Control\\Cry"...
0x18003d12c  mov     rcx, r14; Destination
0x18003d12f  call    cs:__imp_RtlAppendUnicodeToString
0x18003d136  nop     dword ptr [rax+rax+00h]
0x18003d13b  lea     rdx, asc_1800AE840; "\\"
0x18003d142  mov     rcx, r14; Destination
0x18003d145  call    cs:__imp_RtlAppendUnicodeToString
0x18003d14c  nop     dword ptr [rax+rax+00h]
0x18003d151  mov     rdx, r12; Source
0x18003d154  mov     rcx, r14; Destination
0x18003d157  call    cs:__imp_RtlAppendUnicodeToString
0x18003d15e  nop     dword ptr [rax+rax+00h]
0x18003d163  lea     rdx, aParameters; "Parameters"
0x18003d16a  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18003d16e  call    cs:__imp_RtlInitUnicodeString
0x18003d175  nop     dword ptr [rax+rax+00h]
0x18003d17a  xorps   xmm0, xmm0
0x18003d17d  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18003d184  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18003d188  mov     [rbp+57h+ObjectAttributes.RootDirectory], rsi
0x18003d18c  mov     edx, 20019h; DesiredAccess
0x18003d191  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x18003d198  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18003d19c  mov     [rbp+57h+ObjectAttributes.ObjectName], r14
0x18003d1a0  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18003d1a5  call    cs:__imp_ZwOpenKey
0x18003d1ac  nop     dword ptr [rax+rax+00h]
0x18003d1b1  mov     ebx, eax
0x18003d1b3  test    eax, eax
0x18003d1b5  js      loc_18003D27D
0x18003d1bb  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18003d1bf  lea     rax, [rbp+57h+arg_18]
0x18003d1c3  mov     [rsp+0C0h+ResultLength], rax; ResultLength
0x18003d1c8  lea     r8d, [rsi+1]; KeyValueInformationClass
0x18003d1cc  xor     r9d, r9d; KeyValueInformation
0x18003d1cf  mov     [rsp+0C0h+Length], esi; Length
0x18003d1d3  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x18003d1d7  call    cs:__imp_ZwQueryValueKey
0x18003d1de  nop     dword ptr [rax+rax+00h]
0x18003d1e3  mov     ebx, eax
0x18003d1e5  test    eax, eax
0x18003d1e7  js      loc_18003D364
0x18003d1ed  mov     ecx, [rbp+57h+arg_18]
0x18003d1f0  call    MSCryptAlloc
0x18003d1f5  mov     rdi, rax
0x18003d1f8  test    rax, rax
0x18003d1fb  jz      loc_18003D3AB
0x18003d201  mov     r8d, [rbp+57h+arg_18]; Size
0x18003d205  xor     edx, edx; Val
0x18003d207  mov     rcx, rax; void *
0x18003d20a  call    memset
0x18003d20f  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18003d213  lea     rax, [rbp+57h+arg_18]
0x18003d217  mov     [rsp+0C0h+ResultLength], rax; ResultLength
0x18003d21c  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x18003d220  mov     eax, [rbp+57h+arg_18]
0x18003d223  mov     r9, rdi; KeyValueInformation
0x18003d226  mov     r8d, 1; KeyValueInformationClass
0x18003d22c  mov     [rsp+0C0h+Length], eax; Length
0x18003d230  call    cs:__imp_ZwQueryValueKey
0x18003d237  nop     dword ptr [rax+rax+00h]
0x18003d23c  mov     ebx, eax
0x18003d23e  test    eax, eax
0x18003d240  js      loc_18003D3F4
0x18003d246  mov     r8d, [rdi+8]
0x18003d24a  lea     rcx, [rbp+57h+var_80]
0x18003d24e  mov     r9d, [rdi+0Ch]
0x18003d252  add     r8, rdi
0x18003d255  mov     edx, [rbp+57h+arg_8]
0x18003d258  mov     dword ptr [rsp+0C0h+ResultLength], r15d
0x18003d25d  mov     qword ptr [rsp+0C0h+Length], r12
0x18003d262  call    AssignGenericDomainParameters
0x18003d267  mov     ebx, eax
0x18003d269  test    eax, eax
0x18003d26b  js      loc_18003D423
0x18003d271  mov     rax, [rbp+57h+var_80]
0x18003d275  xor     ebx, ebx
0x18003d277  mov     [r13+0], rax
0x18003d27b  jmp     short loc_18003D2BF
0x18003d27d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d284  lea     rax, WPP_GLOBAL_Control
0x18003d28b  cmp     rcx, rax
0x18003d28e  jz      short loc_18003D2BF
0x18003d290  mov     eax, [rcx+2Ch]
0x18003d293  test    al, 1
0x18003d295  jz      short loc_18003D2BF
0x18003d297  mov     dword ptr [rsp+0C0h+var_90], 4C1h
0x18003d29f  lea     rax, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003d2a6  mov     [rsp+0C0h+ResultLength], rax
0x18003d2ab  mov     [rsp+0C0h+Length], ebx
0x18003d2af  mov     rcx, [rcx+18h]
0x18003d2b3  lea     r9, aStatus; "Status"
0x18003d2ba  call    WPP_SF_sDsd
0x18003d2bf  mov     rcx, r14; P
0x18003d2c2  call    MSCryptFree
0x18003d2c7  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x18003d2cb  test    rcx, rcx
0x18003d2ce  jz      short loc_18003D2DC
0x18003d2d0  call    cs:__imp_ZwClose
0x18003d2d7  nop     dword ptr [rax+rax+00h]
0x18003d2dc  test    rdi, rdi
0x18003d2df  jz      short loc_18003D2E9
0x18003d2e1  mov     rcx, rdi; P
0x18003d2e4  call    MSCryptFree
0x18003d2e9  test    rsi, rsi
0x18003d2ec  jz      short loc_18003D2F6
0x18003d2ee  mov     rcx, rsi; P
0x18003d2f1  call    FreeGenericEccKeyParameters
0x18003d2f6  mov     eax, ebx
0x18003d2f8  mov     rbx, [rsp+0C0h+arg_0]
0x18003d300  add     rsp, 90h
0x18003d307  pop     r15
0x18003d309  pop     r14
0x18003d30b  pop     r13
0x18003d30d  pop     r12
0x18003d30f  pop     rdi
0x18003d310  pop     rsi
0x18003d311  pop     rbp
0x18003d312  retn
0x18003d314  mov     ebx, 0C0000017h
0x18003d319  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d320  lea     rax, WPP_GLOBAL_Control
0x18003d327  cmp     rcx, rax
0x18003d32a  jz      short loc_18003D2C7
0x18003d32c  mov     eax, [rcx+2Ch]
0x18003d32f  test    al, 1
0x18003d331  jz      short loc_18003D2C7
0x18003d333  mov     rcx, [rcx+18h]
0x18003d337  lea     rax, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003d33e  mov     dword ptr [rsp+0C0h+var_90], 4A9h
0x18003d346  lea     r9, aStatus; "Status"
0x18003d34d  mov     [rsp+0C0h+ResultLength], rax
0x18003d352  mov     [rsp+0C0h+Length], 0C0000017h
0x18003d35a  call    WPP_SF_sDsd
0x18003d35f  jmp     loc_18003D2C7
0x18003d364  cmp     ebx, 0C0000023h
0x18003d36a  jz      loc_18003D1ED
0x18003d370  cmp     ebx, 80000005h
0x18003d376  jz      loc_18003D1ED
0x18003d37c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d383  lea     rax, WPP_GLOBAL_Control
0x18003d38a  cmp     rcx, rax
0x18003d38d  jz      loc_18003D2BF
0x18003d393  mov     eax, [rcx+2Ch]
0x18003d396  test    al, 1
0x18003d398  jz      loc_18003D2BF
0x18003d39e  mov     dword ptr [rsp+0C0h+var_90], 4E5h
0x18003d3a6  jmp     loc_18003D29F
0x18003d3ab  mov     ebx, 0C0000017h
0x18003d3b0  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d3b7  lea     rax, WPP_GLOBAL_Control
0x18003d3be  cmp     rcx, rax
0x18003d3c1  jz      loc_18003D2BF
0x18003d3c7  mov     edx, [rcx+2Ch]
0x18003d3ca  test    dl, 1
0x18003d3cd  jz      loc_18003D2BF
0x18003d3d3  mov     dword ptr [rsp+0C0h+var_90], 4D1h
0x18003d3db  lea     rax, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003d3e2  mov     [rsp+0C0h+ResultLength], rax
0x18003d3e7  mov     [rsp+0C0h+Length], 0C0000017h
0x18003d3ef  jmp     loc_18003D2AF
0x18003d3f4  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d3fb  lea     rax, WPP_GLOBAL_Control
0x18003d402  cmp     rcx, rax
0x18003d405  jz      loc_18003D2BF
0x18003d40b  mov     eax, [rcx+2Ch]
0x18003d40e  test    al, 1
0x18003d410  jz      loc_18003D2BF
0x18003d416  mov     dword ptr [rsp+0C0h+var_90], 4DFh
0x18003d41e  jmp     loc_18003D29F
0x18003d423  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d42a  lea     rax, WPP_GLOBAL_Control
0x18003d431  cmp     rcx, rax
0x18003d434  jz      short loc_18003D465
0x18003d436  mov     eax, [rcx+2Ch]
0x18003d439  test    al, 1
0x18003d43b  jz      short loc_18003D465
0x18003d43d  mov     rcx, [rcx+18h]
0x18003d441  lea     rax, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003d448  mov     dword ptr [rsp+0C0h+var_90], 4ECh
0x18003d450  lea     r9, aStatus; "Status"
0x18003d457  mov     [rsp+0C0h+ResultLength], rax
0x18003d45c  mov     [rsp+0C0h+Length], ebx
0x18003d460  call    WPP_SF_sDsd
0x18003d465  mov     rsi, [rbp+57h+var_80]
0x18003d469  jmp     loc_18003D2BF
```
