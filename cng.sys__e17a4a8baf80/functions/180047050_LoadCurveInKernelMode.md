# LoadCurveInKernelMode

- ea: `0x180047050`
- end: `0x18004742e`
- name: `LoadCurveInKernelMode`
- size: `990`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18004af70`

## callees

- `0x18000e090`
- `0x180010590`
- `0x1800123d0`
- `0x180047050`
- `0x180047434`
- `0x180052d04`
- `0x1800a4380`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18004712e`
- `ntoskrnl!RtlInitUnicodeString` at `0x18004712e`
- `ntoskrnl!ZwQueryValueKey` at `0x180047197`
- `ntoskrnl!ZwQueryValueKey` at `0x1800471f0`
- `ntoskrnl!ZwQueryValueKey` at `0x180047197`
- `ntoskrnl!ZwQueryValueKey` at `0x1800471f0`
- `ntoskrnl!ZwClose` at `0x180047290`
- `ntoskrnl!ZwClose` at `0x180047290`
- `ntoskrnl!ZwOpenKey` at `0x180047165`
- `ntoskrnl!ZwOpenKey` at `0x180047165`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1800470d9`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1800470ef`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180047105`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180047117`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1800470d9`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1800470ef`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180047105`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180047117`

## string_xrefs

- `0x18004725f`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x1800472f7`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x18004739b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180047401`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x1800470c7`: `\Registry\MACHINE\`

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
0x180047050  mov     [rsp-8+arg_0], rbx
0x180047055  mov     [rsp-8+arg_8], edx
0x180047059  push    rbp
0x18004705a  push    rsi
0x18004705b  push    rdi
0x18004705c  push    r12
0x18004705e  push    r13
0x180047060  push    r14
0x180047062  push    r15
0x180047064  lea     rbp, [rsp-27h]
0x180047069  sub     rsp, 90h
0x180047070  xorps   xmm1, xmm1
0x180047073  lea     ebx, [r9+0A0h]
0x18004707a  mov     r13, rcx
0x18004707d  xor     esi, esi
0x18004707f  xorps   xmm0, xmm0
0x180047082  mov     ecx, ebx
0x180047084  add     rcx, 10h
0x180047088  mov     [rbp+57h+var_80], rsi
0x18004708c  mov     r15d, r9d
0x18004708f  mov     [rbp+57h+KeyHandle], rsi
0x180047093  mov     r12, r8
0x180047096  mov     [rbp+57h+arg_18], esi
0x180047099  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18004709d  xor     edi, edi
0x18004709f  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x1800470a3  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x1800470a7  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x1800470ab  call    MSCryptAlloc
0x1800470b0  mov     r14, rax
0x1800470b3  test    rax, rax
0x1800470b6  jz      loc_1800472D4
0x1800470bc  xor     eax, eax
0x1800470be  mov     [r14+2], bx
0x1800470c3  mov     [r14], ax
0x1800470c7  lea     rdx, aRegistryMachin_16; "\\Registry\\MACHINE\\"
0x1800470ce  lea     rax, [r14+10h]
0x1800470d2  mov     rcx, r14; Destination
0x1800470d5  mov     [r14+8], rax
0x1800470d9  call    cs:__imp_RtlAppendUnicodeToString
0x1800470e0  nop     dword ptr [rax+rax+00h]
0x1800470e5  lea     rdx, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Control\\Cry"...
0x1800470ec  mov     rcx, r14; Destination
0x1800470ef  call    cs:__imp_RtlAppendUnicodeToString
0x1800470f6  nop     dword ptr [rax+rax+00h]
0x1800470fb  lea     rdx, asc_1800B5C40; "\\"
0x180047102  mov     rcx, r14; Destination
0x180047105  call    cs:__imp_RtlAppendUnicodeToString
0x18004710c  nop     dword ptr [rax+rax+00h]
0x180047111  mov     rdx, r12; Source
0x180047114  mov     rcx, r14; Destination
0x180047117  call    cs:__imp_RtlAppendUnicodeToString
0x18004711e  nop     dword ptr [rax+rax+00h]
0x180047123  lea     rdx, aParameters; "Parameters"
0x18004712a  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18004712e  call    cs:__imp_RtlInitUnicodeString
0x180047135  nop     dword ptr [rax+rax+00h]
0x18004713a  xorps   xmm0, xmm0
0x18004713d  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180047144  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180047148  mov     [rbp+57h+ObjectAttributes.RootDirectory], rsi
0x18004714c  mov     edx, 20019h; DesiredAccess
0x180047151  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x180047158  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18004715c  mov     [rbp+57h+ObjectAttributes.ObjectName], r14
0x180047160  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180047165  call    cs:__imp_ZwOpenKey
0x18004716c  nop     dword ptr [rax+rax+00h]
0x180047171  mov     ebx, eax
0x180047173  test    eax, eax
0x180047175  js      loc_18004723D
0x18004717b  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18004717f  lea     rax, [rbp+57h+arg_18]
0x180047183  mov     [rsp+0C0h+ResultLength], rax; ResultLength
0x180047188  lea     r8d, [rsi+1]; KeyValueInformationClass
0x18004718c  xor     r9d, r9d; KeyValueInformation
0x18004718f  mov     [rsp+0C0h+Length], esi; Length
0x180047193  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x180047197  call    cs:__imp_ZwQueryValueKey
0x18004719e  nop     dword ptr [rax+rax+00h]
0x1800471a3  mov     ebx, eax
0x1800471a5  test    eax, eax
0x1800471a7  js      loc_180047324
0x1800471ad  mov     ecx, [rbp+57h+arg_18]
0x1800471b0  call    MSCryptAlloc
0x1800471b5  mov     rdi, rax
0x1800471b8  test    rax, rax
0x1800471bb  jz      loc_18004736B
0x1800471c1  mov     r8d, [rbp+57h+arg_18]; Size
0x1800471c5  xor     edx, edx; Val
0x1800471c7  mov     rcx, rax; void *
0x1800471ca  call    memset
0x1800471cf  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800471d3  lea     rax, [rbp+57h+arg_18]
0x1800471d7  mov     [rsp+0C0h+ResultLength], rax; ResultLength
0x1800471dc  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x1800471e0  mov     eax, [rbp+57h+arg_18]
0x1800471e3  mov     r9, rdi; KeyValueInformation
0x1800471e6  mov     r8d, 1; KeyValueInformationClass
0x1800471ec  mov     [rsp+0C0h+Length], eax; Length
0x1800471f0  call    cs:__imp_ZwQueryValueKey
0x1800471f7  nop     dword ptr [rax+rax+00h]
0x1800471fc  mov     ebx, eax
0x1800471fe  test    eax, eax
0x180047200  js      loc_1800473B4
0x180047206  mov     r8d, [rdi+8]
0x18004720a  lea     rcx, [rbp+57h+var_80]
0x18004720e  mov     r9d, [rdi+0Ch]
0x180047212  add     r8, rdi
0x180047215  mov     edx, [rbp+57h+arg_8]
0x180047218  mov     dword ptr [rsp+0C0h+ResultLength], r15d
0x18004721d  mov     qword ptr [rsp+0C0h+Length], r12
0x180047222  call    AssignGenericDomainParameters
0x180047227  mov     ebx, eax
0x180047229  test    eax, eax
0x18004722b  js      loc_1800473E3
0x180047231  mov     rax, [rbp+57h+var_80]
0x180047235  xor     ebx, ebx
0x180047237  mov     [r13+0], rax
0x18004723b  jmp     short loc_18004727F
0x18004723d  mov     rcx, cs:WPP_GLOBAL_Control
0x180047244  lea     rax, WPP_GLOBAL_Control
0x18004724b  cmp     rcx, rax
0x18004724e  jz      short loc_18004727F
0x180047250  mov     eax, [rcx+2Ch]
0x180047253  test    al, 1
0x180047255  jz      short loc_18004727F
0x180047257  mov     dword ptr [rsp+0C0h+var_90], 4C1h
0x18004725f  lea     rax, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180047266  mov     [rsp+0C0h+ResultLength], rax
0x18004726b  mov     [rsp+0C0h+Length], ebx
0x18004726f  mov     rcx, [rcx+18h]
0x180047273  lea     r9, aStatus; "Status"
0x18004727a  call    WPP_SF_sDsd
0x18004727f  mov     rcx, r14; P
0x180047282  call    MSCryptFree
0x180047287  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x18004728b  test    rcx, rcx
0x18004728e  jz      short loc_18004729C
0x180047290  call    cs:__imp_ZwClose
0x180047297  nop     dword ptr [rax+rax+00h]
0x18004729c  test    rdi, rdi
0x18004729f  jz      short loc_1800472A9
0x1800472a1  mov     rcx, rdi; P
0x1800472a4  call    MSCryptFree
0x1800472a9  test    rsi, rsi
0x1800472ac  jz      short loc_1800472B6
0x1800472ae  mov     rcx, rsi; P
0x1800472b1  call    FreeGenericEccKeyParameters
0x1800472b6  mov     eax, ebx
0x1800472b8  mov     rbx, [rsp+0C0h+arg_0]
0x1800472c0  add     rsp, 90h
0x1800472c7  pop     r15
0x1800472c9  pop     r14
0x1800472cb  pop     r13
0x1800472cd  pop     r12
0x1800472cf  pop     rdi
0x1800472d0  pop     rsi
0x1800472d1  pop     rbp
0x1800472d2  retn
0x1800472d4  mov     ebx, 0C0000017h
0x1800472d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800472e0  lea     rax, WPP_GLOBAL_Control
0x1800472e7  cmp     rcx, rax
0x1800472ea  jz      short loc_180047287
0x1800472ec  mov     eax, [rcx+2Ch]
0x1800472ef  test    al, 1
0x1800472f1  jz      short loc_180047287
0x1800472f3  mov     rcx, [rcx+18h]
0x1800472f7  lea     rax, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800472fe  mov     dword ptr [rsp+0C0h+var_90], 4A9h
0x180047306  lea     r9, aStatus; "Status"
0x18004730d  mov     [rsp+0C0h+ResultLength], rax
0x180047312  mov     [rsp+0C0h+Length], 0C0000017h
0x18004731a  call    WPP_SF_sDsd
0x18004731f  jmp     loc_180047287
0x180047324  cmp     ebx, 0C0000023h
0x18004732a  jz      loc_1800471AD
0x180047330  cmp     ebx, 80000005h
0x180047336  jz      loc_1800471AD
0x18004733c  mov     rcx, cs:WPP_GLOBAL_Control
0x180047343  lea     rax, WPP_GLOBAL_Control
0x18004734a  cmp     rcx, rax
0x18004734d  jz      loc_18004727F
0x180047353  mov     eax, [rcx+2Ch]
0x180047356  test    al, 1
0x180047358  jz      loc_18004727F
0x18004735e  mov     dword ptr [rsp+0C0h+var_90], 4E5h
0x180047366  jmp     loc_18004725F
0x18004736b  mov     ebx, 0C0000017h
0x180047370  mov     rcx, cs:WPP_GLOBAL_Control
0x180047377  lea     rax, WPP_GLOBAL_Control
0x18004737e  cmp     rcx, rax
0x180047381  jz      loc_18004727F
0x180047387  mov     edx, [rcx+2Ch]
0x18004738a  test    dl, 1
0x18004738d  jz      loc_18004727F
0x180047393  mov     dword ptr [rsp+0C0h+var_90], 4D1h
0x18004739b  lea     rax, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800473a2  mov     [rsp+0C0h+ResultLength], rax
0x1800473a7  mov     [rsp+0C0h+Length], 0C0000017h
0x1800473af  jmp     loc_18004726F
0x1800473b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800473bb  lea     rax, WPP_GLOBAL_Control
0x1800473c2  cmp     rcx, rax
0x1800473c5  jz      loc_18004727F
0x1800473cb  mov     eax, [rcx+2Ch]
0x1800473ce  test    al, 1
0x1800473d0  jz      loc_18004727F
0x1800473d6  mov     dword ptr [rsp+0C0h+var_90], 4DFh
0x1800473de  jmp     loc_18004725F
0x1800473e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800473ea  lea     rax, WPP_GLOBAL_Control
0x1800473f1  cmp     rcx, rax
0x1800473f4  jz      short loc_180047425
0x1800473f6  mov     eax, [rcx+2Ch]
0x1800473f9  test    al, 1
0x1800473fb  jz      short loc_180047425
0x1800473fd  mov     rcx, [rcx+18h]
0x180047401  lea     rax, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180047408  mov     dword ptr [rsp+0C0h+var_90], 4ECh
0x180047410  lea     r9, aStatus; "Status"
0x180047417  mov     [rsp+0C0h+ResultLength], rax
0x18004741c  mov     [rsp+0C0h+Length], ebx
0x180047420  call    WPP_SF_sDsd
0x180047425  mov     rsi, [rbp+57h+var_80]
0x180047429  jmp     loc_18004727F
```
