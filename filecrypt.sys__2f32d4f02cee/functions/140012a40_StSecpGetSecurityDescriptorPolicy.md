# StSecpGetSecurityDescriptorPolicy

- ea: `0x140012a40`
- end: `0x14001315a`
- name: `StSecpGetSecurityDescriptorPolicy`
- size: `1818`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000ddd0`
- `0x140012a40`

## callees

- `0x140001010`
- `0x140001110`
- `0x140003540`
- `0x140012a40`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140012c4b`
- `ntoskrnl!RtlInitUnicodeString` at `0x140012dc8`
- `ntoskrnl!RtlInitUnicodeString` at `0x140012c4b`
- `ntoskrnl!RtlInitUnicodeString` at `0x140012dc8`
- `ntoskrnl!ZwQueryValueKey` at `0x140012cd9`
- `ntoskrnl!ZwQueryValueKey` at `0x140012d50`
- `ntoskrnl!ZwQueryValueKey` at `0x140012df8`
- `ntoskrnl!ZwQueryValueKey` at `0x140012e91`
- `ntoskrnl!ZwQueryValueKey` at `0x140012cd9`
- `ntoskrnl!ZwQueryValueKey` at `0x140012d50`
- `ntoskrnl!ZwQueryValueKey` at `0x140012df8`
- `ntoskrnl!ZwQueryValueKey` at `0x140012e91`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012e38`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012f06`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012f1f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012f38`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012f51`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012f6a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012e38`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012f06`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012f1f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012f38`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012f51`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012f6a`
- `ntoskrnl!ExAllocatePool2` at `0x140012b3f`
- `ntoskrnl!ExAllocatePool2` at `0x140012d0f`
- `ntoskrnl!ExAllocatePool2` at `0x140012d74`
- `ntoskrnl!ExAllocatePool2` at `0x140012e53`
- `ntoskrnl!ExAllocatePool2` at `0x140012eb1`
- `ntoskrnl!ExAllocatePool2` at `0x140013021`
- `ntoskrnl!ExAllocatePool2` at `0x1400130c1`
- `ntoskrnl!ExAllocatePool2` at `0x140012b3f`
- `ntoskrnl!ExAllocatePool2` at `0x140012d0f`
- `ntoskrnl!ExAllocatePool2` at `0x140012d74`
- `ntoskrnl!ExAllocatePool2` at `0x140012e53`
- `ntoskrnl!ExAllocatePool2` at `0x140012eb1`
- `ntoskrnl!ExAllocatePool2` at `0x140013021`
- `ntoskrnl!ExAllocatePool2` at `0x1400130c1`
- `ntoskrnl!ZwEnumerateKey` at `0x140012ae6`
- `ntoskrnl!ZwEnumerateKey` at `0x140012ae6`
- `ntoskrnl!ZwQueryKey` at `0x140012fed`
- `ntoskrnl!ZwQueryKey` at `0x140013059`
- `ntoskrnl!ZwQueryKey` at `0x140012fed`
- `ntoskrnl!ZwQueryKey` at `0x140013059`
- `ntoskrnl!RtlCreateUnicodeString` at `0x140013097`
- `ntoskrnl!RtlCreateUnicodeString` at `0x140013097`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140012bfe`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140012c19`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140012d92`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140012e14`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140012eed`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140013126`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140013149`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140012bfe`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140012c19`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140012d92`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140012e14`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140012eed`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140013126`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140013149`
- `ntoskrnl!ZwOpenKey` at `0x140012bad`
- `ntoskrnl!ZwOpenKey` at `0x140012c8b`
- `ntoskrnl!ZwOpenKey` at `0x140012bad`
- `ntoskrnl!ZwOpenKey` at `0x140012c8b`
- `ntoskrnl!ZwClose` at `0x140012bdc`
- `ntoskrnl!ZwClose` at `0x140012f80`
- `ntoskrnl!ZwClose` at `0x140012bdc`
- `ntoskrnl!ZwClose` at `0x140012f80`

## string_xrefs

- `0x140012a7d`: `SecurityDescriptor`

## pseudocode

```c
__int64 __fastcall StSecpGetSecurityDescriptorPolicy(void *a1)
{
  wchar_t *v1; // r12
  WCHAR *v3; // r14
  ULONG v4; // edi
  NTSTATUS v5; // eax
  NTSTATUS SecurityDescriptorPolicy; // ebx
  wchar_t *Pool2; // rax
  wchar_t *v8; // rsi
  WCHAR *v9; // r15
  wchar_t *v10; // rdi
  NTSTATUS v11; // eax
  wchar_t *v12; // rax
  wchar_t *v13; // rax
  NTSTATUS v14; // eax
  wchar_t *v15; // rax
  wchar_t *v16; // rax
  NTSTATUS v18; // eax
  __int64 v19; // rax
  struct _UNICODE_STRING v20; // xmm0
  __int64 *v21; // rdx
  ULONG ResultLength; // [rsp+38h] [rbp-D0h] BYREF
  struct _UNICODE_STRING v23; // [rsp+40h] [rbp-C8h] BYREF
  void *KeyHandle; // [rsp+50h] [rbp-B8h] BYREF
  struct _UNICODE_STRING KeyHandle_8; // [rsp+58h] [rbp-B0h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+68h] [rbp-A0h] BYREF
  struct _OBJECT_ATTRIBUTES v27; // [rsp+78h] [rbp-90h] BYREF
  __int64 v28; // [rsp+A8h] [rbp-60h] BYREF
  __int128 KeyValueInformation; // [rsp+B0h] [rbp-58h] BYREF
  char KeyInformation[12]; // [rsp+C8h] [rbp-40h] BYREF
  USHORT v31; // [rsp+D4h] [rbp-34h]
  __int16 v32; // [rsp+D6h] [rbp-32h]
  __int16 v33; // [rsp+D8h] [rbp-30h] BYREF

  v1 = 0;
  ResultLength = 0;
  *(_QWORD *)&ValueName.Length = 2490404;
  ValueName.Buffer = L"SecurityDescriptor";
  v28 = 0;
  KeyHandle = 0;
  KeyHandle_8 = 0;
  v3 = 0;
  KeyValueInformation = 0;
  v4 = 0;
  v23 = 0;
  memset(&v27, 0, 44);
  while ( 1 )
  {
    v5 = ZwEnumerateKey(a1, v4, KeyBasicInformation, KeyInformation, 0x222u, &ResultLength);
    SecurityDescriptorPolicy = v5;
    if ( v5 < 0 )
      break;
    KeyHandle_8.Buffer = (PWSTR)&v33;
    KeyHandle_8.Length = v31;
    KeyHandle_8.MaximumLength = v31;
    if ( v33 == 60 && *(&v32 + ((unsigned __int64)v31 >> 1)) == 62 )
    {
      if ( v3 )
      {
        SecurityDescriptorPolicy = -1073739509;
LABEL_15:
        RtlFreeUnicodeString(&v23);
        goto LABEL_48;
      }
      Pool2 = (wchar_t *)ExAllocatePool2(256, v31 + 2LL, 1884517459);
      v3 = Pool2;
      if ( !Pool2 )
      {
        SecurityDescriptorPolicy = -1073741801;
        RtlFreeUnicodeString(&v23);
        goto LABEL_49;
      }
      SecurityDescriptorPolicy = RtlStringCbCopyNW(
                                   Pool2,
                                   KeyHandle_8.Length + 2LL,
                                   KeyHandle_8.Buffer,
                                   KeyHandle_8.Length);
      if ( SecurityDescriptorPolicy < 0 )
        goto LABEL_15;
    }
    else
    {
      v27.Length = 48;
      v27.ObjectName = &KeyHandle_8;
      v27.RootDirectory = a1;
      v27.Attributes = 576;
      *(_OWORD *)&v27.SecurityDescriptor = 0;
      SecurityDescriptorPolicy = ZwOpenKey(&KeyHandle, 0x20019u, &v27);
      if ( SecurityDescriptorPolicy < 0 )
        goto LABEL_67;
      SecurityDescriptorPolicy = StSecpGetSecurityDescriptorPolicy(KeyHandle);
      if ( SecurityDescriptorPolicy < 0 )
        goto LABEL_67;
      ZwClose(KeyHandle);
      KeyHandle = 0;
    }
    ++v4;
  }
  v8 = 0;
  v9 = 0;
  v10 = 0;
  if ( v5 != -2147483622 )
    goto LABEL_39;
  if ( v3 )
  {
    RtlInitUnicodeString(&KeyHandle_8, v3);
    v27.Length = 48;
    v27.ObjectName = &KeyHandle_8;
    v27.RootDirectory = a1;
    v27.Attributes = 576;
    *(_OWORD *)&v27.SecurityDescriptor = 0;
    SecurityDescriptorPolicy = ZwOpenKey(&KeyHandle, 0x20019u, &v27);
    if ( SecurityDescriptorPolicy < 0 )
      goto LABEL_39;
    SecurityDescriptorPolicy = StSecpGetSecurityDescriptorPolicy(KeyHandle);
    if ( SecurityDescriptorPolicy < 0 )
      goto LABEL_39;
  }
  v11 = ZwQueryValueKey(a1, &ValueName, KeyValuePartialInformation, &KeyValueInformation, 0x10u, &ResultLength);
  SecurityDescriptorPolicy = v11;
  if ( v11 >= 0 )
  {
    SecurityDescriptorPolicy = -1073739509;
LABEL_67:
    RtlFreeUnicodeString(&v23);
    goto LABEL_47;
  }
  if ( v11 != -2147483643 )
  {
    if ( v11 == -1073741772 )
    {
      SecurityDescriptorPolicy = 0;
      goto LABEL_67;
    }
    goto LABEL_39;
  }
  v12 = (wchar_t *)ExAllocatePool2(256, ResultLength, 1884517459);
  v8 = v12;
  if ( !v12 )
  {
    SecurityDescriptorPolicy = -1073741801;
    goto LABEL_67;
  }
  SecurityDescriptorPolicy = ZwQueryValueKey(
                               a1,
                               &ValueName,
                               KeyValuePartialInformation,
                               v12,
                               ResultLength,
                               &ResultLength);
  if ( SecurityDescriptorPolicy < 0 )
    goto LABEL_39;
  v13 = (wchar_t *)ExAllocatePool2(256, *((unsigned int *)v8 + 2), 1884517459);
  v10 = v13;
  if ( v13 )
  {
    SecurityDescriptorPolicy = RtlStringCbCopyW(v13, *((unsigned int *)v8 + 2), v8 + 6);
    if ( SecurityDescriptorPolicy < 0 )
      goto LABEL_39;
    RtlInitUnicodeString(&ValueName, L"Debug");
    v14 = ZwQueryValueKey(a1, &ValueName, KeyValuePartialInformation, &KeyValueInformation, 0x10u, &ResultLength);
    SecurityDescriptorPolicy = v14;
    if ( v14 >= 0 )
    {
LABEL_30:
      SecurityDescriptorPolicy = -1073739509;
LABEL_31:
      RtlFreeUnicodeString(&v23);
LABEL_40:
      ExFreePoolWithTag(v10, 0x70537453u);
LABEL_41:
      if ( v1 )
        ExFreePoolWithTag(v1, 0x70537453u);
      goto LABEL_43;
    }
    if ( v14 == -2147483643 )
    {
      ExFreePoolWithTag(v8, 0x70537453u);
      v15 = (wchar_t *)ExAllocatePool2(256, ResultLength, 1884517459);
      v8 = v15;
      if ( !v15 )
      {
        SecurityDescriptorPolicy = -1073741801;
        goto LABEL_31;
      }
      SecurityDescriptorPolicy = ZwQueryValueKey(
                                   a1,
                                   &ValueName,
                                   KeyValuePartialInformation,
                                   v15,
                                   ResultLength,
                                   &ResultLength);
      if ( SecurityDescriptorPolicy < 0 )
        goto LABEL_39;
      v16 = (wchar_t *)ExAllocatePool2(256, *((unsigned int *)v8 + 2), 1884517459);
      v1 = v16;
      if ( !v16 )
      {
        SecurityDescriptorPolicy = -1073741801;
        goto LABEL_31;
      }
      SecurityDescriptorPolicy = RtlStringCbCopyW(v16, *((unsigned int *)v8 + 2), v8 + 6);
      if ( SecurityDescriptorPolicy < 0 )
        goto LABEL_39;
    }
    else if ( v14 != -1073741772 )
    {
      goto LABEL_39;
    }
    v18 = ZwQueryKey(a1, KeyNameInformation, &v28, 8u, &ResultLength);
    SecurityDescriptorPolicy = v18;
    if ( v18 >= 0 )
      goto LABEL_30;
    if ( v18 == -2147483643 )
    {
      v9 = (WCHAR *)ExAllocatePool2(256, ResultLength + 4LL, 1884517459);
      if ( !v9 )
      {
        SecurityDescriptorPolicy = -1073741801;
        goto LABEL_31;
      }
      SecurityDescriptorPolicy = ZwQueryKey(a1, KeyNameInformation, v9, ResultLength, &ResultLength);
      if ( SecurityDescriptorPolicy >= 0 )
      {
        v9[((unsigned __int64)*(unsigned int *)v9 >> 1) + 2] = 92;
        v9[((unsigned __int64)*(unsigned int *)v9 >> 1) + 3] = 0;
        if ( RtlCreateUnicodeString(&v23, v9 + 74) )
        {
          v19 = ExAllocatePool2(256, 48, 1884517459);
          if ( v19 )
          {
            v20 = v23;
            *(_QWORD *)(v19 + 32) = v10;
            *(_QWORD *)(v19 + 40) = v1;
            *(struct _UNICODE_STRING *)(v19 + 16) = v20;
            v21 = (__int64 *)qword_1400096A8;
            if ( *(__int64 **)qword_1400096A8 != &g_StSecSecurityDescriptorCacheListHead )
              __fastfail(3u);
            *(_QWORD *)v19 = &g_StSecSecurityDescriptorCacheListHead;
            *(_QWORD *)(v19 + 8) = v21;
            *v21 = v19;
            qword_1400096A8 = v19;
            v23.Buffer = 0;
            RtlFreeUnicodeString(&v23);
LABEL_43:
            if ( !v8 )
              goto LABEL_45;
            goto LABEL_44;
          }
          SecurityDescriptorPolicy = -1073741801;
        }
        else
        {
          SecurityDescriptorPolicy = -1073741801;
        }
        goto LABEL_31;
      }
    }
LABEL_39:
    RtlFreeUnicodeString(&v23);
    if ( !v10 )
      goto LABEL_41;
    goto LABEL_40;
  }
  SecurityDescriptorPolicy = -1073741801;
  RtlFreeUnicodeString(&v23);
LABEL_44:
  ExFreePoolWithTag(v8, 0x70537453u);
LABEL_45:
  if ( v9 )
    ExFreePoolWithTag(v9, 0x70537453u);
LABEL_47:
  if ( !v3 )
    goto LABEL_49;
LABEL_48:
  ExFreePoolWithTag(v3, 0x70537453u);
LABEL_49:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)SecurityDescriptorPolicy;
}

```

## disassembly

```asm
0x140012a40  mov     r11, rsp
0x140012a43  mov     [r11+20h], rbx
0x140012a47  push    rbp
0x140012a48  push    rdi
0x140012a49  push    r12
0x140012a4b  push    r13
0x140012a4d  push    r14
0x140012a4f  lea     rbp, [r11-228h]
0x140012a56  sub     rsp, 300h
0x140012a5d  mov     rax, cs:__security_cookie
0x140012a64  xor     rax, rsp
0x140012a67  mov     [rbp+220h+var_30], rax
0x140012a6e  xor     r12d, r12d
0x140012a71  mov     [r11+10h], rsi
0x140012a75  xorps   xmm0, xmm0
0x140012a78  mov     [rsp+320h+var_2F0], r12d
0x140012a7d  lea     rax, aSecuritydescri; "SecurityDescriptor"
0x140012a84  mov     qword ptr [rsp+320h+ValueName.Length], 260024h
0x140012a8d  xorps   xmm1, xmm1
0x140012a90  mov     [rsp+320h+ValueName.Buffer], rax
0x140012a95  movups  xmmword ptr [rbp+220h+var_2B0+10h], xmm0
0x140012a99  xor     eax, eax
0x140012a9b  mov     [rbp+220h+var_280], r12
0x140012a9f  movups  xmmword ptr [rbp+220h+var_2B0+1Ch], xmm0
0x140012aa3  mov     r13, rcx
0x140012aa6  mov     [rsp+320h+KeyHandle], r12
0x140012aab  movups  xmmword ptr [rsp+320h+KeyHandle+8], xmm0
0x140012ab0  mov     r14d, r12d
0x140012ab3  mov     [r11+18h], r15
0x140012ab7  movups  [rbp+220h+KeyValueInformation], xmm0
0x140012abb  mov     edi, r12d
0x140012abe  movups  xmmword ptr [rsp+320h+var_2F0+8], xmm1
0x140012ac3  movups  xmmword ptr [rsp+320h+var_2B0], xmm0
0x140012ac8  lea     rax, [rsp+320h+var_2F0]
0x140012acd  xor     r8d, r8d; KeyInformationClass
0x140012ad0  mov     [rsp+320h+ResultLength], rax; ResultLength
0x140012ad5  lea     r9, [rbp+220h+KeyInformation]; KeyInformation
0x140012ad9  mov     edx, edi; Index
0x140012adb  mov     [rsp+320h+Length], 222h; Length
0x140012ae3  mov     rcx, r13; KeyHandle
0x140012ae6  call    cs:__imp_ZwEnumerateKey
0x140012aed  nop     dword ptr [rax+rax+00h]
0x140012af2  mov     ebx, eax
0x140012af4  test    eax, eax
0x140012af6  js      loc_140012C2A
0x140012afc  cmp     [rbp+220h+var_250], 3Ch ; '<'
0x140012b01  lea     rax, [rbp+220h+var_250]
0x140012b05  mov     [rsp+320h+pszSrc], rax
0x140012b0a  movzx   eax, [rbp+220h+var_254]
0x140012b0e  mov     word ptr [rsp+320h+KeyHandle+8], ax
0x140012b13  mov     word ptr [rsp+320h+KeyHandle+0Ah], ax
0x140012b18  jnz     short loc_140012B79
0x140012b1a  mov     edx, eax
0x140012b1c  shr     rax, 1
0x140012b1f  cmp     [rbp+rax*2+220h+var_252], 3Eh ; '>'
0x140012b25  jnz     short loc_140012B79
0x140012b27  test    r14, r14
0x140012b2a  jnz     loc_140012C0F
0x140012b30  add     rdx, 2
0x140012b34  mov     ecx, 100h
0x140012b39  mov     r8d, 70537453h
0x140012b3f  call    cs:__imp_ExAllocatePool2
0x140012b46  nop     dword ptr [rax+rax+00h]
0x140012b4b  mov     r14, rax
0x140012b4e  test    rax, rax
0x140012b51  jz      loc_140012BF4
0x140012b57  movzx   r9d, word ptr [rsp+320h+KeyHandle+8]; cbToCopy
0x140012b5d  mov     rcx, rax; pszDest
0x140012b60  mov     r8, [rsp+320h+pszSrc]; pszSrc
0x140012b65  lea     rdx, [r9+2]; cbDest
0x140012b69  call    RtlStringCbCopyNW
0x140012b6e  mov     ebx, eax
0x140012b70  test    eax, eax
0x140012b72  jns     short loc_140012BED
0x140012b74  jmp     loc_140012C14
0x140012b79  lea     rax, [rsp+320h+KeyHandle+8]
0x140012b7e  mov     dword ptr [rsp+320h+var_2B0], 30h ; '0'
0x140012b86  xorps   xmm0, xmm0
0x140012b89  mov     qword ptr [rbp+220h+var_2B0+10h], rax
0x140012b8d  lea     r8, [rsp+320h+var_2B0]; ObjectAttributes
0x140012b92  mov     qword ptr [rsp+320h+var_2B0+8], r13
0x140012b97  mov     edx, 20019h; DesiredAccess
0x140012b9c  mov     dword ptr [rbp+220h+var_2B0+18h], 240h
0x140012ba3  lea     rcx, [rsp+320h+KeyHandle]; KeyHandle
0x140012ba8  movdqu  xmmword ptr [rbp+220h+var_2B0+20h], xmm0
0x140012bad  call    cs:__imp_ZwOpenKey
0x140012bb4  nop     dword ptr [rax+rax+00h]
0x140012bb9  mov     ebx, eax
0x140012bbb  test    eax, eax
0x140012bbd  js      loc_140013144
0x140012bc3  mov     rcx, [rsp+320h+KeyHandle]
0x140012bc8  call    StSecpGetSecurityDescriptorPolicy
0x140012bcd  mov     ebx, eax
0x140012bcf  test    eax, eax
0x140012bd1  js      loc_140013144
0x140012bd7  mov     rcx, [rsp+320h+KeyHandle]; Handle
0x140012bdc  call    cs:__imp_ZwClose
0x140012be3  nop     dword ptr [rax+rax+00h]
0x140012be8  mov     [rsp+320h+KeyHandle], r12
0x140012bed  inc     edi
0x140012bef  jmp     loc_140012AC8
0x140012bf4  lea     rcx, [rsp+320h+var_2F0+8]; UnicodeString
0x140012bf9  mov     ebx, 0C0000017h
0x140012bfe  call    cs:__imp_RtlFreeUnicodeString
0x140012c05  nop     dword ptr [rax+rax+00h]
0x140012c0a  jmp     loc_140012F76
0x140012c0f  mov     ebx, 0C000090Bh
0x140012c14  lea     rcx, [rsp+320h+var_2F0+8]; UnicodeString
0x140012c19  call    cs:__imp_RtlFreeUnicodeString
0x140012c20  nop     dword ptr [rax+rax+00h]
0x140012c25  jmp     loc_140012F62
0x140012c2a  mov     rsi, r12
0x140012c2d  mov     r15, r12
0x140012c30  mov     rdi, r12
0x140012c33  cmp     eax, 8000001Ah
0x140012c38  jnz     loc_140012EE8
0x140012c3e  test    r14, r14
0x140012c41  jz      short loc_140012CB5
0x140012c43  mov     rdx, r14; SourceString
0x140012c46  lea     rcx, [rsp+320h+KeyHandle+8]; DestinationString
0x140012c4b  call    cs:__imp_RtlInitUnicodeString
0x140012c52  nop     dword ptr [rax+rax+00h]
0x140012c57  lea     rax, [rsp+320h+KeyHandle+8]
0x140012c5c  mov     dword ptr [rsp+320h+var_2B0], 30h ; '0'
0x140012c64  xorps   xmm0, xmm0
0x140012c67  mov     qword ptr [rbp+220h+var_2B0+10h], rax
0x140012c6b  lea     r8, [rsp+320h+var_2B0]; ObjectAttributes
0x140012c70  mov     qword ptr [rsp+320h+var_2B0+8], r13
0x140012c75  mov     edx, 20019h; DesiredAccess
0x140012c7a  mov     dword ptr [rbp+220h+var_2B0+18h], 240h
0x140012c81  lea     rcx, [rsp+320h+KeyHandle]; KeyHandle
0x140012c86  movdqu  xmmword ptr [rbp+220h+var_2B0+20h], xmm0
0x140012c8b  call    cs:__imp_ZwOpenKey
0x140012c92  nop     dword ptr [rax+rax+00h]
0x140012c97  mov     ebx, eax
0x140012c99  test    eax, eax
0x140012c9b  js      loc_140012EE8
0x140012ca1  mov     rcx, [rsp+320h+KeyHandle]
0x140012ca6  call    StSecpGetSecurityDescriptorPolicy
0x140012cab  mov     ebx, eax
0x140012cad  test    eax, eax
0x140012caf  js      loc_140012EE8
0x140012cb5  lea     rax, [rsp+320h+var_2F0]
0x140012cba  mov     r8d, 2; KeyValueInformationClass
0x140012cc0  mov     [rsp+320h+ResultLength], rax; ResultLength
0x140012cc5  lea     r9, [rbp+220h+KeyValueInformation]; KeyValueInformation
0x140012cc9  lea     rdx, [rsp+320h+ValueName]; ValueName
0x140012cce  mov     [rsp+320h+Length], 10h; Length
0x140012cd6  mov     rcx, r13; KeyHandle
0x140012cd9  call    cs:__imp_ZwQueryValueKey
0x140012ce0  nop     dword ptr [rax+rax+00h]
0x140012ce5  mov     ebx, eax
0x140012ce7  test    eax, eax
0x140012ce9  js      short loc_140012CF5
0x140012ceb  mov     ebx, 0C000090Bh
0x140012cf0  jmp     loc_140013144
0x140012cf5  cmp     eax, 80000005h
0x140012cfa  jnz     loc_140013137
0x140012d00  mov     edx, [rsp+320h+var_2F0]
0x140012d04  mov     ecx, 100h
0x140012d09  mov     r8d, 70537453h
0x140012d0f  call    cs:__imp_ExAllocatePool2
0x140012d16  nop     dword ptr [rax+rax+00h]
0x140012d1b  mov     rsi, rax
0x140012d1e  test    rax, rax
0x140012d21  jnz     short loc_140012D2D
0x140012d23  mov     ebx, 0C0000017h
0x140012d28  jmp     loc_140013144
0x140012d2d  lea     rax, [rsp+320h+var_2F0]
0x140012d32  mov     r9, rsi; KeyValueInformation
0x140012d35  mov     [rsp+320h+ResultLength], rax; ResultLength
0x140012d3a  lea     rdx, [rsp+320h+ValueName]; ValueName
0x140012d3f  mov     eax, [rsp+320h+var_2F0]
0x140012d43  mov     r8d, 2; KeyValueInformationClass
0x140012d49  mov     rcx, r13; KeyHandle
0x140012d4c  mov     [rsp+320h+Length], eax; Length
0x140012d50  call    cs:__imp_ZwQueryValueKey
0x140012d57  nop     dword ptr [rax+rax+00h]
0x140012d5c  mov     ebx, eax
0x140012d5e  test    eax, eax
0x140012d60  js      loc_140012EE8
0x140012d66  mov     edx, [rsi+8]
0x140012d69  mov     ecx, 100h
0x140012d6e  mov     r8d, 70537453h
0x140012d74  call    cs:__imp_ExAllocatePool2
0x140012d7b  nop     dword ptr [rax+rax+00h]
0x140012d80  mov     rdi, rax
0x140012d83  test    rax, rax
0x140012d86  jnz     short loc_140012DA3
0x140012d88  lea     rcx, [rsp+320h+var_2F0+8]; UnicodeString
0x140012d8d  mov     ebx, 0C0000017h
0x140012d92  call    cs:__imp_RtlFreeUnicodeString
0x140012d99  nop     dword ptr [rax+rax+00h]
0x140012d9e  jmp     loc_140012F30
0x140012da3  mov     edx, [rsi+8]; cbDest
0x140012da6  lea     r8, [rsi+0Ch]; pszSrc
0x140012daa  mov     rcx, rdi; pszDest
0x140012dad  call    RtlStringCbCopyW
0x140012db2  mov     ebx, eax
0x140012db4  test    eax, eax
0x140012db6  js      loc_140012EE8
0x140012dbc  lea     rdx, aDebug; "Debug"
0x140012dc3  lea     rcx, [rsp+320h+ValueName]; DestinationString
0x140012dc8  call    cs:__imp_RtlInitUnicodeString
0x140012dcf  nop     dword ptr [rax+rax+00h]
0x140012dd4  lea     rax, [rsp+320h+var_2F0]
0x140012dd9  mov     r8d, 2; KeyValueInformationClass
0x140012ddf  mov     [rsp+320h+ResultLength], rax; ResultLength
0x140012de4  lea     r9, [rbp+220h+KeyValueInformation]; KeyValueInformation
0x140012de8  lea     rdx, [rsp+320h+ValueName]; ValueName
0x140012ded  mov     [rsp+320h+Length], 10h; Length
0x140012df5  mov     rcx, r13; KeyHandle
0x140012df8  call    cs:__imp_ZwQueryValueKey
0x140012dff  nop     dword ptr [rax+rax+00h]
0x140012e04  mov     ebx, eax
0x140012e06  test    eax, eax
0x140012e08  js      short loc_140012E25
0x140012e0a  mov     ebx, 0C000090Bh
0x140012e0f  lea     rcx, [rsp+320h+var_2F0+8]; UnicodeString
0x140012e14  call    cs:__imp_RtlFreeUnicodeString
0x140012e1b  nop     dword ptr [rax+rax+00h]
0x140012e20  jmp     loc_140012EFE
0x140012e25  cmp     eax, 80000005h
0x140012e2a  jnz     loc_140012FC6
0x140012e30  mov     edx, 70537453h; Tag
0x140012e35  mov     rcx, rsi; P
0x140012e38  call    cs:__imp_ExFreePoolWithTag
0x140012e3f  nop     dword ptr [rax+rax+00h]
0x140012e44  mov     edx, [rsp+320h+var_2F0]
0x140012e48  mov     ecx, 100h
0x140012e4d  mov     r8d, 70537453h
0x140012e53  call    cs:__imp_ExAllocatePool2
0x140012e5a  nop     dword ptr [rax+rax+00h]
0x140012e5f  mov     rsi, rax
0x140012e62  test    rax, rax
0x140012e65  jnz     short loc_140012E6E
0x140012e67  mov     ebx, 0C0000017h
0x140012e6c  jmp     short loc_140012E0F
0x140012e6e  lea     rax, [rsp+320h+var_2F0]
0x140012e73  mov     r9, rsi; KeyValueInformation
0x140012e76  mov     [rsp+320h+ResultLength], rax; ResultLength
0x140012e7b  lea     rdx, [rsp+320h+ValueName]; ValueName
0x140012e80  mov     eax, [rsp+320h+var_2F0]
0x140012e84  mov     r8d, 2; KeyValueInformationClass
0x140012e8a  mov     rcx, r13; KeyHandle
0x140012e8d  mov     [rsp+320h+Length], eax; Length
0x140012e91  call    cs:__imp_ZwQueryValueKey
0x140012e98  nop     dword ptr [rax+rax+00h]
0x140012e9d  mov     ebx, eax
0x140012e9f  test    eax, eax
0x140012ea1  js      short loc_140012EE8
0x140012ea3  mov     edx, [rsi+8]
0x140012ea6  mov     ecx, 100h
0x140012eab  mov     r8d, 70537453h
0x140012eb1  call    cs:__imp_ExAllocatePool2
0x140012eb8  nop     dword ptr [rax+rax+00h]
0x140012ebd  mov     r12, rax
0x140012ec0  test    rax, rax
0x140012ec3  jnz     short loc_140012ECF
0x140012ec5  mov     ebx, 0C0000017h
0x140012eca  jmp     loc_140012E0F
0x140012ecf  mov     edx, [rsi+8]; cbDest
0x140012ed2  lea     r8, [rsi+0Ch]; pszSrc
0x140012ed6  mov     rcx, rax; pszDest
0x140012ed9  call    RtlStringCbCopyW
0x140012ede  mov     ebx, eax
0x140012ee0  test    eax, eax
0x140012ee2  jns     loc_140012FD1
0x140012ee8  lea     rcx, [rsp+320h+var_2F0+8]; UnicodeString
0x140012eed  call    cs:__imp_RtlFreeUnicodeString
0x140012ef4  nop     dword ptr [rax+rax+00h]
0x140012ef9  test    rdi, rdi
0x140012efc  jz      short loc_140012F12
0x140012efe  mov     edx, 70537453h; Tag
0x140012f03  mov     rcx, rdi; P
0x140012f06  call    cs:__imp_ExFreePoolWithTag
0x140012f0d  nop     dword ptr [rax+rax+00h]
0x140012f12  test    r12, r12
0x140012f15  jz      short loc_140012F2B
0x140012f17  mov     edx, 70537453h; Tag
0x140012f1c  mov     rcx, r12; P
0x140012f1f  call    cs:__imp_ExFreePoolWithTag
0x140012f26  nop     dword ptr [rax+rax+00h]
0x140012f2b  test    rsi, rsi
0x140012f2e  jz      short loc_140012F44
0x140012f30  mov     edx, 70537453h; Tag
0x140012f35  mov     rcx, rsi; P
0x140012f38  call    cs:__imp_ExFreePoolWithTag
0x140012f3f  nop     dword ptr [rax+rax+00h]
0x140012f44  test    r15, r15
0x140012f47  jz      short loc_140012F5D
0x140012f49  mov     edx, 70537453h; Tag
0x140012f4e  mov     rcx, r15; P
0x140012f51  call    cs:__imp_ExFreePoolWithTag
0x140012f58  nop     dword ptr [rax+rax+00h]
0x140012f5d  test    r14, r14
0x140012f60  jz      short loc_140012F76
0x140012f62  mov     edx, 70537453h; Tag
0x140012f67  mov     rcx, r14; P
0x140012f6a  call    cs:__imp_ExFreePoolWithTag
  ... truncated ...
```
