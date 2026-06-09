# StSecpGetFolderPropertyPolicy

- ea: `0x140013160`
- end: `0x140013644`
- name: `StSecpGetFolderPropertyPolicy`
- size: `1252`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000ddd0`
- `0x140013160`

## callees

- `0x140001110`
- `0x140003540`
- `0x140013160`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140013321`
- `ntoskrnl!RtlInitUnicodeString` at `0x140013321`
- `ntoskrnl!ZwQueryValueKey` at `0x1400132d9`
- `ntoskrnl!ZwQueryValueKey` at `0x140013351`
- `ntoskrnl!ZwQueryValueKey` at `0x1400133be`
- `ntoskrnl!ZwQueryValueKey` at `0x1400132d9`
- `ntoskrnl!ZwQueryValueKey` at `0x140013351`
- `ntoskrnl!ZwQueryValueKey` at `0x1400133be`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400135b6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400135cf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400135e8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400135b6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400135cf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400135e8`
- `ntoskrnl!ExAllocatePool2` at `0x14001337d`
- `ntoskrnl!ExAllocatePool2` at `0x1400133e3`
- `ntoskrnl!ExAllocatePool2` at `0x140013482`
- `ntoskrnl!ExAllocatePool2` at `0x14001351a`
- `ntoskrnl!ExAllocatePool2` at `0x14001337d`
- `ntoskrnl!ExAllocatePool2` at `0x1400133e3`
- `ntoskrnl!ExAllocatePool2` at `0x140013482`
- `ntoskrnl!ExAllocatePool2` at `0x14001351a`
- `ntoskrnl!ZwEnumerateKey` at `0x140013209`
- `ntoskrnl!ZwEnumerateKey` at `0x140013209`
- `ntoskrnl!ZwQueryKey` at `0x140013437`
- `ntoskrnl!ZwQueryKey` at `0x1400134b7`
- `ntoskrnl!ZwQueryKey` at `0x140013437`
- `ntoskrnl!ZwQueryKey` at `0x1400134b7`
- `ntoskrnl!RtlCreateUnicodeString` at `0x1400134f0`
- `ntoskrnl!RtlCreateUnicodeString` at `0x1400134f0`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400132ff`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140013453`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14001357b`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14001359d`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400132ff`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140013453`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14001357b`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14001359d`
- `ntoskrnl!ZwOpenKey` at `0x14001326a`
- `ntoskrnl!ZwOpenKey` at `0x14001326a`
- `ntoskrnl!ZwClose` at `0x140013291`
- `ntoskrnl!ZwClose` at `0x1400135fe`
- `ntoskrnl!ZwClose` at `0x140013291`
- `ntoskrnl!ZwClose` at `0x1400135fe`

## pseudocode

```c
__int64 __fastcall StSecpGetFolderPropertyPolicy(void *a1)
{
  ULONG v2; // edi
  NTSTATUS v3; // eax
  NTSTATUS FolderPropertyPolicy; // ebx
  wchar_t *v5; // r14
  WCHAR *v6; // rsi
  wchar_t *v7; // rdi
  NTSTATUS v8; // eax
  int v9; // r12d
  NTSTATUS v10; // eax
  wchar_t *Pool2; // rax
  wchar_t *v12; // rax
  NTSTATUS v13; // eax
  __int64 v14; // rax
  struct _UNICODE_STRING v15; // xmm0
  __int64 *v16; // rdx
  ULONG ResultLength; // [rsp+38h] [rbp-D0h] BYREF
  struct _UNICODE_STRING v19; // [rsp+40h] [rbp-C8h] BYREF
  HANDLE KeyHandle; // [rsp+50h] [rbp-B8h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+58h] [rbp-B0h] BYREF
  __int128 v22; // [rsp+68h] [rbp-A0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes_8; // [rsp+78h] [rbp-90h] BYREF
  __int128 KeyValueInformation; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v25; // [rsp+B8h] [rbp-50h] BYREF
  char KeyInformation[12]; // [rsp+C8h] [rbp-40h] BYREF
  __int16 v27; // [rsp+D4h] [rbp-34h]
  char v28; // [rsp+D8h] [rbp-30h] BYREF

  *(_QWORD *)&ValueName.Length = 1179664;
  ResultLength = 0;
  ValueName.Buffer = L"FolderId";
  v25 = 0;
  v22 = 0;
  v2 = 0;
  KeyValueInformation = 0;
  v19 = 0;
  memset(&ObjectAttributes_8, 0, 44);
  while ( 1 )
  {
    KeyHandle = 0;
    v3 = ZwEnumerateKey(a1, v2, KeyBasicInformation, KeyInformation, 0x222u, &ResultLength);
    FolderPropertyPolicy = v3;
    if ( v3 < 0 )
      break;
    ObjectAttributes_8.Length = 48;
    *((_QWORD *)&v22 + 1) = &v28;
    LOWORD(v22) = v27;
    WORD1(v22) = v27;
    ObjectAttributes_8.RootDirectory = a1;
    ObjectAttributes_8.ObjectName = (PUNICODE_STRING)&v22;
    ObjectAttributes_8.Attributes = 576;
    *(_OWORD *)&ObjectAttributes_8.SecurityDescriptor = 0;
    FolderPropertyPolicy = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes_8);
    if ( FolderPropertyPolicy < 0 )
      goto LABEL_10;
    FolderPropertyPolicy = StSecpGetFolderPropertyPolicy(KeyHandle);
    if ( FolderPropertyPolicy < 0 )
      goto LABEL_10;
    ZwClose(KeyHandle);
    ++v2;
  }
  v5 = 0;
  v6 = 0;
  v7 = 0;
  if ( v3 != -2147483622 )
    goto LABEL_36;
  v8 = ZwQueryValueKey(a1, &ValueName, KeyValuePartialInformation, &KeyValueInformation, 0x10u, &ResultLength);
  FolderPropertyPolicy = v8;
  if ( v8 < 0 )
  {
    if ( v8 == -1073741772 )
    {
      FolderPropertyPolicy = 0;
      goto LABEL_10;
    }
    goto LABEL_36;
  }
  if ( DWORD2(KeyValueInformation) != 4
    || (v9 = BYTE12(KeyValueInformation),
        RtlInitUnicodeString(&ValueName, L"ChamberId"),
        v10 = ZwQueryValueKey(a1, &ValueName, KeyValuePartialInformation, &KeyValueInformation, 0x10u, &ResultLength),
        FolderPropertyPolicy = v10,
        v10 >= 0) )
  {
    FolderPropertyPolicy = -1073739509;
LABEL_10:
    RtlFreeUnicodeString(&v19);
    goto LABEL_42;
  }
  if ( v10 != -2147483643 )
    goto LABEL_36;
  Pool2 = (wchar_t *)ExAllocatePool2(256, ResultLength, 1884517459);
  v5 = Pool2;
  if ( !Pool2 )
  {
    FolderPropertyPolicy = -1073741801;
    goto LABEL_10;
  }
  FolderPropertyPolicy = ZwQueryValueKey(a1, &ValueName, KeyValuePartialInformation, Pool2, ResultLength, &ResultLength);
  if ( FolderPropertyPolicy < 0 )
  {
LABEL_36:
    RtlFreeUnicodeString(&v19);
    if ( !v7 )
      goto LABEL_38;
    goto LABEL_37;
  }
  v12 = (wchar_t *)ExAllocatePool2(256, *((unsigned int *)v5 + 2), 1884517459);
  v7 = v12;
  if ( v12 )
  {
    FolderPropertyPolicy = RtlStringCbCopyW(v12, *((unsigned int *)v5 + 2), v5 + 6);
    if ( FolderPropertyPolicy >= 0 )
    {
      v13 = ZwQueryKey(a1, KeyNameInformation, &v25, 8u, &ResultLength);
      FolderPropertyPolicy = v13;
      if ( v13 >= 0 )
      {
        FolderPropertyPolicy = -1073739509;
LABEL_21:
        RtlFreeUnicodeString(&v19);
LABEL_37:
        ExFreePoolWithTag(v7, 0x70537453u);
LABEL_38:
        if ( !v5 )
          goto LABEL_40;
        goto LABEL_39;
      }
      if ( v13 == -2147483643 )
      {
        v6 = (WCHAR *)ExAllocatePool2(256, ResultLength + 4LL, 1884517459);
        if ( !v6 )
        {
          FolderPropertyPolicy = -1073741801;
          goto LABEL_21;
        }
        FolderPropertyPolicy = ZwQueryKey(a1, KeyNameInformation, v6, ResultLength, &ResultLength);
        if ( FolderPropertyPolicy >= 0 )
        {
          v6[((unsigned __int64)*(unsigned int *)v6 >> 1) + 2] = 92;
          v6[((unsigned __int64)*(unsigned int *)v6 >> 1) + 3] = 0;
          if ( RtlCreateUnicodeString(&v19, v6 + 71) )
          {
            v14 = ExAllocatePool2(256, 48, 1884517459);
            if ( v14 )
            {
              v15 = v19;
              *(_DWORD *)(v14 + 32) = v9;
              *(_QWORD *)(v14 + 40) = v7;
              *(struct _UNICODE_STRING *)(v14 + 16) = v15;
              v16 = (__int64 *)qword_1400096B8;
              if ( *(__int64 **)qword_1400096B8 != &g_StSecFolderPropertyCacheListHead )
                __fastfail(3u);
              *(_QWORD *)v14 = &g_StSecFolderPropertyCacheListHead;
              *(_QWORD *)(v14 + 8) = v16;
              *v16 = v14;
              qword_1400096B8 = v14;
              v19.Buffer = 0;
              goto LABEL_33;
            }
            FolderPropertyPolicy = -1073741801;
          }
          else
          {
            FolderPropertyPolicy = -1073741801;
          }
          goto LABEL_21;
        }
      }
    }
    goto LABEL_36;
  }
  FolderPropertyPolicy = -1073741801;
LABEL_33:
  RtlFreeUnicodeString(&v19);
LABEL_39:
  ExFreePoolWithTag(v5, 0x70537453u);
LABEL_40:
  if ( v6 )
    ExFreePoolWithTag(v6, 0x70537453u);
LABEL_42:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)FolderPropertyPolicy;
}

```

## disassembly

```asm
0x140013160  mov     r11, rsp
0x140013163  mov     [r11+20h], rbx
0x140013167  push    rbp
0x140013168  push    rdi
0x140013169  push    r12
0x14001316b  push    r13
0x14001316d  push    r15
0x14001316f  lea     rbp, [r11-228h]
0x140013176  sub     rsp, 300h
0x14001317d  mov     rax, cs:__security_cookie
0x140013184  xor     rax, rsp
0x140013187  mov     [rbp+220h+var_30], rax
0x14001318e  xorps   xmm0, xmm0
0x140013191  mov     [r11+10h], rsi
0x140013195  xor     r13d, r13d
0x140013198  mov     qword ptr [rsp+320h+ValueName.Length], 120010h
0x1400131a1  lea     rax, aFolderid; "FolderId"
0x1400131a8  mov     [rsp+320h+var_2F0], r13d
0x1400131ad  xorps   xmm1, xmm1
0x1400131b0  mov     [rsp+320h+ValueName.Buffer], rax
0x1400131b5  movups  xmmword ptr [rbp+220h+ObjectAttributes+18h], xmm0
0x1400131b9  xor     eax, eax
0x1400131bb  mov     [rbp+220h+var_270], r13
0x1400131bf  movups  xmmword ptr [rbp+220h+ObjectAttributes+24h], xmm0
0x1400131c3  mov     r15, rcx
0x1400131c6  mov     [r11+18h], r14
0x1400131ca  movups  xmmword ptr [rsp+60h], xmm0
0x1400131cf  mov     r12d, 10h
0x1400131d5  mov     edi, r13d
0x1400131d8  movups  [rbp+220h+KeyValueInformation], xmm0
0x1400131dc  movups  xmmword ptr [rsp+320h+var_2F0+8], xmm1
0x1400131e1  movups  xmmword ptr [rsp+320h+ObjectAttributes+8], xmm0
0x1400131e6  lea     rax, [rsp+320h+var_2F0]
0x1400131eb  mov     [rsp+320h+KeyHandle], r13
0x1400131f0  mov     [rsp+320h+ResultLength], rax; ResultLength
0x1400131f5  lea     r9, [rbp+220h+KeyInformation]; KeyInformation
0x1400131f9  xor     r8d, r8d; KeyInformationClass
0x1400131fc  mov     [rsp+320h+Length], 222h; Length
0x140013204  mov     edx, edi; Index
0x140013206  mov     rcx, r15; KeyHandle
0x140013209  call    cs:__imp_ZwEnumerateKey
0x140013210  nop     dword ptr [rax+rax+00h]
0x140013215  mov     ebx, eax
0x140013217  test    eax, eax
0x140013219  js      loc_1400132A4
0x14001321f  lea     rax, [rbp+220h+var_250]
0x140013223  mov     dword ptr [rsp+320h+ObjectAttributes+8], 30h ; '0'
0x14001322b  mov     qword ptr [rsp+320h+ObjectAttributes], rax
0x140013230  lea     r8, [rsp+320h+ObjectAttributes+8]; ObjectAttributes
0x140013235  mov     rax, [rbp-34h]
0x140013239  lea     rcx, [rsp+320h+KeyHandle]; KeyHandle
0x14001323e  mov     [rsp+60h], ax
0x140013243  xorps   xmm0, xmm0
0x140013246  mov     [rsp+62h], ax
0x14001324b  mov     edx, 20019h; DesiredAccess
0x140013250  lea     rax, [rsp+60h]
0x140013255  mov     qword ptr [rsp+320h+ObjectAttributes+10h], r15
0x14001325a  mov     qword ptr [rbp+220h+ObjectAttributes+18h], rax
0x14001325e  mov     dword ptr [rbp+220h+ObjectAttributes+20h], 240h
0x140013265  movdqu  xmmword ptr [rbp+220h+ObjectAttributes+28h], xmm0
0x14001326a  call    cs:__imp_ZwOpenKey
0x140013271  nop     dword ptr [rax+rax+00h]
0x140013276  mov     ebx, eax
0x140013278  test    eax, eax
0x14001327a  js      short loc_1400132FA
0x14001327c  mov     rcx, [rsp+320h+KeyHandle]
0x140013281  call    StSecpGetFolderPropertyPolicy
0x140013286  mov     ebx, eax
0x140013288  test    eax, eax
0x14001328a  js      short loc_1400132FA
0x14001328c  mov     rcx, [rsp+320h+KeyHandle]; Handle
0x140013291  call    cs:__imp_ZwClose
0x140013298  nop     dword ptr [rax+rax+00h]
0x14001329d  inc     edi
0x14001329f  jmp     loc_1400131E6
0x1400132a4  mov     r14, r13
0x1400132a7  mov     rsi, r13
0x1400132aa  mov     rdi, r13
0x1400132ad  cmp     eax, 8000001Ah
0x1400132b2  jnz     loc_140013598
0x1400132b8  lea     rax, [rsp+320h+var_2F0]
0x1400132bd  mov     r8d, 2; KeyValueInformationClass
0x1400132c3  mov     [rsp+320h+ResultLength], rax; ResultLength
0x1400132c8  lea     r9, [rbp+220h+KeyValueInformation]; KeyValueInformation
0x1400132cc  lea     rdx, [rsp+320h+ValueName]; ValueName
0x1400132d1  mov     [rsp+320h+Length], r12d; Length
0x1400132d6  mov     rcx, r15; KeyHandle
0x1400132d9  call    cs:__imp_ZwQueryValueKey
0x1400132e0  nop     dword ptr [rax+rax+00h]
0x1400132e5  mov     ebx, eax
0x1400132e7  test    eax, eax
0x1400132e9  js      loc_140013589
0x1400132ef  cmp     dword ptr [rbp+220h+KeyValueInformation+8], 4
0x1400132f3  jz      short loc_140013310
0x1400132f5  mov     ebx, 0C000090Bh
0x1400132fa  lea     rcx, [rsp+320h+var_2F0+8]; UnicodeString
0x1400132ff  call    cs:__imp_RtlFreeUnicodeString
0x140013306  nop     dword ptr [rax+rax+00h]
0x14001330b  jmp     loc_1400135F4
0x140013310  movzx   r12d, byte ptr [rbp+220h+KeyValueInformation+0Ch]
0x140013315  lea     rdx, aChamberid; "ChamberId"
0x14001331c  lea     rcx, [rsp+320h+ValueName]; DestinationString
0x140013321  call    cs:__imp_RtlInitUnicodeString
0x140013328  nop     dword ptr [rax+rax+00h]
0x14001332d  lea     rax, [rsp+320h+var_2F0]
0x140013332  mov     r8d, 2; KeyValueInformationClass
0x140013338  mov     [rsp+320h+ResultLength], rax; ResultLength
0x14001333d  lea     r9, [rbp+220h+KeyValueInformation]; KeyValueInformation
0x140013341  lea     rdx, [rsp+320h+ValueName]; ValueName
0x140013346  mov     [rsp+320h+Length], 10h; Length
0x14001334e  mov     rcx, r15; KeyHandle
0x140013351  call    cs:__imp_ZwQueryValueKey
0x140013358  nop     dword ptr [rax+rax+00h]
0x14001335d  mov     ebx, eax
0x14001335f  test    eax, eax
0x140013361  jns     short loc_1400132F5
0x140013363  cmp     eax, 80000005h
0x140013368  jnz     loc_140013598
0x14001336e  mov     edx, [rsp+320h+var_2F0]
0x140013372  mov     ecx, 100h
0x140013377  mov     r8d, 70537453h
0x14001337d  call    cs:__imp_ExAllocatePool2
0x140013384  nop     dword ptr [rax+rax+00h]
0x140013389  mov     r14, rax
0x14001338c  test    rax, rax
0x14001338f  jnz     short loc_14001339B
0x140013391  mov     ebx, 0C0000017h
0x140013396  jmp     loc_1400132FA
0x14001339b  lea     rax, [rsp+320h+var_2F0]
0x1400133a0  mov     r9, r14; KeyValueInformation
0x1400133a3  mov     [rsp+320h+ResultLength], rax; ResultLength
0x1400133a8  lea     rdx, [rsp+320h+ValueName]; ValueName
0x1400133ad  mov     eax, [rsp+320h+var_2F0]
0x1400133b1  mov     r8d, 2; KeyValueInformationClass
0x1400133b7  mov     rcx, r15; KeyHandle
0x1400133ba  mov     [rsp+320h+Length], eax; Length
0x1400133be  call    cs:__imp_ZwQueryValueKey
0x1400133c5  nop     dword ptr [rax+rax+00h]
0x1400133ca  mov     ebx, eax
0x1400133cc  test    eax, eax
0x1400133ce  js      loc_140013598
0x1400133d4  mov     edx, [r14+8]
0x1400133d8  mov     ecx, 100h
0x1400133dd  mov     r8d, 70537453h
0x1400133e3  call    cs:__imp_ExAllocatePool2
0x1400133ea  nop     dword ptr [rax+rax+00h]
0x1400133ef  mov     rdi, rax
0x1400133f2  test    rax, rax
0x1400133f5  jnz     short loc_140013401
0x1400133f7  mov     ebx, 0C0000017h
0x1400133fc  jmp     loc_140013576
0x140013401  mov     edx, [r14+8]; cbDest
0x140013405  lea     r8, [r14+0Ch]; pszSrc
0x140013409  mov     rcx, rdi; pszDest
0x14001340c  call    RtlStringCbCopyW
0x140013411  mov     ebx, eax
0x140013413  test    eax, eax
0x140013415  js      loc_140013598
0x14001341b  lea     rax, [rsp+320h+var_2F0]
0x140013420  mov     r9d, 8; Length
0x140013426  lea     r8, [rbp+220h+var_270]; KeyInformation
0x14001342a  mov     qword ptr [rsp+320h+Length], rax; ResultLength
0x14001342f  mov     edx, 3; KeyInformationClass
0x140013434  mov     rcx, r15; KeyHandle
0x140013437  call    cs:__imp_ZwQueryKey
0x14001343e  nop     dword ptr [rax+rax+00h]
0x140013443  mov     ebx, eax
0x140013445  test    eax, eax
0x140013447  js      short loc_140013464
0x140013449  mov     ebx, 0C000090Bh
0x14001344e  lea     rcx, [rsp+320h+var_2F0+8]; UnicodeString
0x140013453  call    cs:__imp_RtlFreeUnicodeString
0x14001345a  nop     dword ptr [rax+rax+00h]
0x14001345f  jmp     loc_1400135AE
0x140013464  cmp     eax, 80000005h
0x140013469  jnz     loc_140013598
0x14001346f  mov     edx, [rsp+320h+var_2F0]
0x140013473  mov     ecx, 100h
0x140013478  add     rdx, 4
0x14001347c  mov     r8d, 70537453h
0x140013482  call    cs:__imp_ExAllocatePool2
0x140013489  nop     dword ptr [rax+rax+00h]
0x14001348e  mov     rsi, rax
0x140013491  test    rax, rax
0x140013494  jnz     short loc_14001349D
0x140013496  mov     ebx, 0C0000017h
0x14001349b  jmp     short loc_14001344E
0x14001349d  mov     r9d, [rsp+320h+var_2F0]; Length
0x1400134a2  lea     rax, [rsp+320h+var_2F0]
0x1400134a7  mov     r8, rsi; KeyInformation
0x1400134aa  mov     qword ptr [rsp+320h+Length], rax; ResultLength
0x1400134af  mov     edx, 3; KeyInformationClass
0x1400134b4  mov     rcx, r15; KeyHandle
0x1400134b7  call    cs:__imp_ZwQueryKey
0x1400134be  nop     dword ptr [rax+rax+00h]
0x1400134c3  mov     ebx, eax
0x1400134c5  test    eax, eax
0x1400134c7  js      loc_140013598
0x1400134cd  mov     eax, [rsi]
0x1400134cf  lea     rdx, [rsi+8Eh]; SourceString
0x1400134d6  shr     rax, 1
0x1400134d9  mov     word ptr [rsi+rax*2+4], 5Ch ; '\'
0x1400134e0  mov     ecx, [rsi]
0x1400134e2  shr     rcx, 1
0x1400134e5  mov     [rsi+rcx*2+6], r13w
0x1400134eb  lea     rcx, [rsp+320h+var_2F0+8]; DestinationString
0x1400134f0  call    cs:__imp_RtlCreateUnicodeString
0x1400134f7  nop     dword ptr [rax+rax+00h]
0x1400134fc  test    al, al
0x1400134fe  jnz     short loc_14001350A
0x140013500  mov     ebx, 0C0000017h
0x140013505  jmp     loc_14001344E
0x14001350a  mov     edx, 30h ; '0'
0x14001350f  mov     ecx, 100h
0x140013514  mov     r8d, 70537453h
0x14001351a  call    cs:__imp_ExAllocatePool2
0x140013521  nop     dword ptr [rax+rax+00h]
0x140013526  test    rax, rax
0x140013529  jnz     short loc_140013535
0x14001352b  mov     ebx, 0C0000017h
0x140013530  jmp     loc_14001344E
0x140013535  movups  xmm0, xmmword ptr [rsp+320h+var_2F0+8]
0x14001353a  mov     [rax+20h], r12d
0x14001353e  lea     rcx, g_StSecFolderPropertyCacheListHead
0x140013545  mov     [rax+28h], rdi
0x140013549  movups  xmmword ptr [rax+10h], xmm0
0x14001354d  mov     rdx, cs:qword_1400096B8
0x140013554  cmp     [rdx], rcx
0x140013557  jz      short loc_140013560
0x140013559  mov     ecx, 3
0x14001355e  int     29h; Win8: RtlFailFast(ecx)
0x140013560  mov     [rax], rcx
0x140013563  mov     [rax+8], rdx
0x140013567  mov     [rdx], rax
0x14001356a  mov     cs:qword_1400096B8, rax
0x140013571  mov     [rsp+320h+var_2E0], r13
0x140013576  lea     rcx, [rsp+320h+var_2F0+8]; UnicodeString
0x14001357b  call    cs:__imp_RtlFreeUnicodeString
0x140013582  nop     dword ptr [rax+rax+00h]
0x140013587  jmp     short loc_1400135C7
0x140013589  cmp     eax, 0C0000034h
0x14001358e  jnz     short loc_140013598
0x140013590  mov     ebx, r13d
0x140013593  jmp     loc_1400132FA
0x140013598  lea     rcx, [rsp+320h+var_2F0+8]; UnicodeString
0x14001359d  call    cs:__imp_RtlFreeUnicodeString
0x1400135a4  nop     dword ptr [rax+rax+00h]
0x1400135a9  test    rdi, rdi
0x1400135ac  jz      short loc_1400135C2
0x1400135ae  mov     edx, 70537453h; Tag
0x1400135b3  mov     rcx, rdi; P
0x1400135b6  call    cs:__imp_ExFreePoolWithTag
0x1400135bd  nop     dword ptr [rax+rax+00h]
0x1400135c2  test    r14, r14
0x1400135c5  jz      short loc_1400135DB
0x1400135c7  mov     edx, 70537453h; Tag
0x1400135cc  mov     rcx, r14; P
0x1400135cf  call    cs:__imp_ExFreePoolWithTag
0x1400135d6  nop     dword ptr [rax+rax+00h]
0x1400135db  test    rsi, rsi
0x1400135de  jz      short loc_1400135F4
0x1400135e0  mov     edx, 70537453h; Tag
0x1400135e5  mov     rcx, rsi; P
0x1400135e8  call    cs:__imp_ExFreePoolWithTag
0x1400135ef  nop     dword ptr [rax+rax+00h]
0x1400135f4  mov     rcx, [rsp+320h+KeyHandle]; Handle
0x1400135f9  test    rcx, rcx
0x1400135fc  jz      short loc_14001360A
0x1400135fe  call    cs:__imp_ZwClose
0x140013605  nop     dword ptr [rax+rax+00h]
0x14001360a  mov     r14, [rsp+320h+arg_10]
0x140013612  mov     eax, ebx
0x140013614  mov     rsi, [rsp+320h+arg_8]
0x14001361c  mov     rcx, [rbp+220h+var_30]
0x140013623  xor     rcx, rsp; StackCookie
0x140013626  call    __security_check_cookie
0x14001362b  mov     rbx, [rsp+320h+arg_18]
0x140013633  add     rsp, 300h
0x14001363a  pop     r15
0x14001363c  pop     r13
0x14001363e  pop     r12
0x140013640  pop     rdi
0x140013641  pop     rbp
0x140013642  retn
```
