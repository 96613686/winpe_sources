# CipPrepareDynamicDeveloperSigners

- ea: `0x180062bc8`
- end: `0x1800630ba`
- name: `CipPrepareDynamicDeveloperSigners`
- size: `1266`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180070834`

## callees

- `0x18000cf38`
- `0x18002bf20`
- `0x18002c080`
- `0x18002c380`
- `0x180062bc8`
- `0x180079740`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180062db4`
- `ntoskrnl!ExAllocatePool2` at `0x180062e63`
- `ntoskrnl!ExAllocatePool2` at `0x180062f0a`
- `ntoskrnl!ExAllocatePool2` at `0x180062f96`
- `ntoskrnl!ExAllocatePool2` at `0x180062db4`
- `ntoskrnl!ExAllocatePool2` at `0x180062e63`
- `ntoskrnl!ExAllocatePool2` at `0x180062f0a`
- `ntoskrnl!ExAllocatePool2` at `0x180062f96`
- `ntoskrnl!ExFreePoolWithTag` at `0x180062d99`
- `ntoskrnl!ExFreePoolWithTag` at `0x180062eef`
- `ntoskrnl!ExFreePoolWithTag` at `0x180063036`
- `ntoskrnl!ExFreePoolWithTag` at `0x180063052`
- `ntoskrnl!ExFreePoolWithTag` at `0x180063081`
- `ntoskrnl!ExFreePoolWithTag` at `0x180062d99`
- `ntoskrnl!ExFreePoolWithTag` at `0x180062eef`
- `ntoskrnl!ExFreePoolWithTag` at `0x180063036`
- `ntoskrnl!ExFreePoolWithTag` at `0x180063052`
- `ntoskrnl!ExFreePoolWithTag` at `0x180063081`
- `ntoskrnl!ZwClose` at `0x180063068`
- `ntoskrnl!ZwClose` at `0x180063068`
- `ntoskrnl!ZwOpenKey` at `0x180062d19`
- `ntoskrnl!ZwOpenKey` at `0x180062d19`
- `ntoskrnl!ZwEnumerateValueKey` at `0x180062d59`
- `ntoskrnl!ZwEnumerateValueKey` at `0x180062dea`
- `ntoskrnl!ZwEnumerateValueKey` at `0x180062eaf`
- `ntoskrnl!ZwEnumerateValueKey` at `0x180062f45`
- `ntoskrnl!ZwEnumerateValueKey` at `0x180062d59`
- `ntoskrnl!ZwEnumerateValueKey` at `0x180062dea`
- `ntoskrnl!ZwEnumerateValueKey` at `0x180062eaf`
- `ntoskrnl!ZwEnumerateValueKey` at `0x180062f45`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x180062c74`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x180062c74`

## string_xrefs

- `0x180062c18`: `\Registry\Machine\SYSTEM\CurrentControlSet\Control\CI\Developer\DeveloperUnlockCertificates`

## pseudocode

```c
__int64 __fastcall CipPrepareDynamicDeveloperSigners(unsigned int *a1, _QWORD *a2)
{
  _DWORD *v2; // rdi
  NTSTATUS PersistedStateLocation; // ebx
  _WORD *v4; // rax
  __int64 v5; // rcx
  unsigned int v6; // r12d
  ULONG i; // esi
  NTSTATUS v8; // eax
  _DWORD *Pool2; // rax
  __int64 v10; // rcx
  _QWORD *v11; // rsi
  ULONG v12; // r15d
  ULONG v13; // r14d
  NTSTATUS v14; // eax
  _DWORD *v15; // rax
  unsigned int v16; // ebx
  void *v17; // rax
  __int64 v18; // r15
  unsigned int j; // r14d
  void *v20; // rcx
  ULONG Length; // [rsp+40h] [rbp-C0h] BYREF
  ULONG pulResult; // [rsp+44h] [rbp-BCh] BYREF
  int v24; // [rsp+48h] [rbp-B8h] BYREF
  void *KeyHandle; // [rsp+50h] [rbp-B0h] BYREF
  int v26; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v27; // [rsp+5Ch] [rbp-A4h]
  __int128 v28; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int *v29; // [rsp+70h] [rbp-90h]
  _QWORD *v30; // [rsp+78h] [rbp-88h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v32[528]; // [rsp+B0h] [rbp-50h] BYREF

  v30 = a2;
  v29 = a1;
  memset(v32, 0, 0x20Au);
  v26 = 0;
  KeyHandle = 0;
  v24 = 0;
  pulResult = 0;
  v28 = 0;
  v2 = 0;
  Length = 0;
  memset(&ObjectAttributes, 0, 44);
  PersistedStateLocation = RtlGetPersistedStateLocation(
                             L"CIDeveloperCerts",
                             0,
                             L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Control\\CI\\Developer\\DeveloperUnlockCertificates",
                             0,
                             v32,
                             522,
                             &v26);
  if ( PersistedStateLocation < 0 )
    goto LABEL_51;
  v4 = v32;
  v28 = 0;
  v5 = 0x7FFF;
  do
  {
    if ( !*v4 )
      break;
    ++v4;
    --v5;
  }
  while ( v5 );
  PersistedStateLocation = v5 == 0 ? 0xC000000D : 0;
  if ( !v5 )
    goto LABEL_51;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  LOWORD(v28) = -2 - 2 * v5;
  WORD1(v28) = -2 * v5;
  *((_QWORD *)&v28 + 1) = v32;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v28;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) < 0 )
  {
    PersistedStateLocation = 0;
    goto LABEL_51;
  }
  v6 = 0;
  for ( i = 0; ; ++i )
  {
    v8 = ZwEnumerateValueKey(KeyHandle, i, KeyValueFullInformation, v2, Length, &Length);
    PersistedStateLocation = v8;
    if ( v8 >= 0 )
      goto LABEL_17;
    if ( v8 == -2147483622 )
      break;
    if ( v8 != -1073741789 && v8 != -2147483643 )
      goto LABEL_51;
    if ( v2 )
      ExFreePoolWithTag(v2, 0x63734943u);
    Pool2 = (_DWORD *)ExAllocatePool2(258, Length, 1668499779);
    v2 = Pool2;
    if ( !Pool2 )
    {
      PersistedStateLocation = -1073741670;
      goto LABEL_51;
    }
    PersistedStateLocation = ZwEnumerateValueKey(KeyHandle, i, KeyValueFullInformation, Pool2, Length, &Length);
    if ( PersistedStateLocation < 0 )
      goto LABEL_51;
LABEL_17:
    if ( v2[1] == 3 )
    {
      if ( v2[4] )
      {
        v10 = (unsigned int)v2[3];
        if ( (_DWORD)v10 )
        {
          if ( (int)SIPolicyHashSizeToAlgorithm(v10, &v24) >= 0 )
            ++v6;
        }
      }
    }
  }
  PersistedStateLocation = RtlULongLongToULong(144LL * v6, &pulResult);
  if ( PersistedStateLocation < 0 )
    goto LABEL_51;
  v11 = (_QWORD *)ExAllocatePool2(256, pulResult, 1668499779);
  if ( !v11 )
  {
    PersistedStateLocation = -1073741801;
    goto LABEL_51;
  }
  v12 = 0;
  pulResult = 0;
  v13 = 0;
  while ( 2 )
  {
    v14 = ZwEnumerateValueKey(KeyHandle, v13, KeyValueFullInformation, v2, Length, &Length);
    PersistedStateLocation = v14;
    if ( v14 < 0 )
    {
      if ( v14 == -2147483622 )
      {
        PersistedStateLocation = 0;
        *v29 = v6;
        *v30 = v11;
        goto LABEL_51;
      }
      if ( v14 != -1073741789 && v14 != -2147483643 )
        goto LABEL_46;
      if ( v2 )
        ExFreePoolWithTag(v2, 0x63734943u);
      v15 = (_DWORD *)ExAllocatePool2(258, Length, 1668499779);
      v2 = v15;
      if ( !v15 )
      {
        PersistedStateLocation = -1073741670;
        goto LABEL_46;
      }
      PersistedStateLocation = ZwEnumerateValueKey(KeyHandle, v13, KeyValueFullInformation, v15, Length, &Length);
      if ( PersistedStateLocation < 0 )
        goto LABEL_46;
    }
    if ( v2[1] != 3 || !v2[4] || (v16 = v2[3]) == 0 || (int)SIPolicyHashSizeToAlgorithm(v16, &v24) < 0 )
    {
LABEL_42:
      ++v13;
      continue;
    }
    break;
  }
  v27 = v2[2];
  v17 = (void *)ExAllocatePool2(256, v16, 1668499779);
  v18 = 18LL * v12;
  v11[v18 + 2] = v17;
  if ( v17 )
  {
    memmove(v17, (char *)v2 + v27, v16);
    HIDWORD(v11[v18]) = v24;
    LODWORD(v11[v18 + 1]) = v16;
    v12 = ++pulResult;
    goto LABEL_42;
  }
  PersistedStateLocation = -1073741801;
LABEL_46:
  for ( j = 0; j < v6; ++j )
  {
    v20 = (void *)v11[18 * j + 2];
    if ( v20 )
      ExFreePoolWithTag(v20, 0x63734943u);
  }
  ExFreePoolWithTag(v11, 0x63734943u);
LABEL_51:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( v2 )
    ExFreePoolWithTag(v2, 0x63734943u);
  return (unsigned int)PersistedStateLocation;
}

```

## disassembly

```asm
0x180062bc8  mov     [rsp-8+arg_10], rbx
0x180062bcd  push    rbp
0x180062bce  push    rsi
0x180062bcf  push    rdi
0x180062bd0  push    r12
0x180062bd2  push    r13
0x180062bd4  push    r14
0x180062bd6  push    r15
0x180062bd8  lea     rbp, [rsp-1D0h]
0x180062be0  sub     rsp, 2D0h
0x180062be7  mov     rax, cs:__security_cookie
0x180062bee  xor     rax, rsp
0x180062bf1  mov     [rbp+200h+var_40], rax
0x180062bf8  mov     [rsp+300h+var_288], rdx
0x180062bfd  mov     ebx, 20Ah
0x180062c02  mov     [rsp+300h+var_290], rcx
0x180062c07  mov     r8d, ebx; Size
0x180062c0a  xor     edx, edx; Val
0x180062c0c  lea     rcx, [rbp+200h+var_250]; void *
0x180062c10  call    memset
0x180062c15  xor     r13d, r13d
0x180062c18  lea     r8, aRegistryMachin_5; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x180062c1f  xorps   xmm0, xmm0
0x180062c22  mov     [rsp+300h+var_2A8], r13d
0x180062c27  xor     eax, eax
0x180062c29  mov     [rsp+300h+KeyHandle], r13
0x180062c2e  lea     rax, [rsp+300h+var_2A8]
0x180062c33  mov     [rsp+300h+var_2B8], r13d
0x180062c38  mov     [rsp+300h+var_2D0], rax
0x180062c3d  lea     rcx, aCidevelopercer; "CIDeveloperCerts"
0x180062c44  lea     rax, [rbp+200h+var_250]
0x180062c48  mov     dword ptr [rsp+300h+ResultLength], ebx
0x180062c4c  movups  xmmword ptr [rbp+200h+ObjectAttributes.ObjectName], xmm0
0x180062c50  xor     r9d, r9d
0x180062c53  mov     qword ptr [rsp+300h+Length], rax
0x180062c58  xor     edx, edx
0x180062c5a  mov     [rsp+300h+pulResult], r13d
0x180062c5f  movups  [rsp+300h+var_2A0], xmm0
0x180062c64  mov     edi, r13d
0x180062c67  mov     [rsp+300h+var_2C0], r13d
0x180062c6c  movups  xmmword ptr [rbp+200h+ObjectAttributes.Length], xmm0
0x180062c70  movups  xmmword ptr [rbp+200h+ObjectAttributes+1Ch], xmm0
0x180062c74  call    cs:__imp_RtlGetPersistedStateLocation
0x180062c7b  nop     dword ptr [rax+rax+00h]
0x180062c80  mov     ebx, eax
0x180062c82  test    eax, eax
0x180062c84  js      loc_18006305E
0x180062c8a  xorps   xmm0, xmm0
0x180062c8d  lea     rax, [rbp+200h+var_250]
0x180062c91  movups  [rsp+300h+var_2A0], xmm0
0x180062c96  mov     ecx, 7FFFh
0x180062c9b  lea     edx, [r13+2]
0x180062c9f  cmp     [rax], r13w
0x180062ca3  jz      short loc_180062CAE
0x180062ca5  add     rax, rdx
0x180062ca8  sub     rcx, 1
0x180062cac  jnz     short loc_180062C9F
0x180062cae  mov     rax, rcx
0x180062cb1  neg     rax
0x180062cb4  sbb     ebx, ebx
0x180062cb6  not     ebx
0x180062cb8  and     ebx, 0C000000Dh
0x180062cbe  test    rcx, rcx
0x180062cc1  jz      loc_18006305E
0x180062cc7  add     cx, cx
0x180062cca  mov     [rbp+200h+ObjectAttributes.Length], 30h ; '0'
0x180062cd1  mov     eax, 0FFFEh
0x180062cd6  mov     [rbp+200h+ObjectAttributes.RootDirectory], r13
0x180062cda  sub     ax, cx
0x180062cdd  mov     [rbp+200h+ObjectAttributes.Attributes], 240h
0x180062ce4  mov     word ptr [rsp+300h+var_2A0], ax
0x180062ce9  lea     r8, [rbp+200h+ObjectAttributes]; ObjectAttributes
0x180062ced  add     ax, dx
0x180062cf0  lea     rcx, [rsp+300h+KeyHandle]; KeyHandle
0x180062cf5  mov     word ptr [rsp+300h+var_2A0+2], ax
0x180062cfa  xorps   xmm0, xmm0
0x180062cfd  lea     rax, [rbp+200h+var_250]
0x180062d01  mov     edx, 20019h; DesiredAccess
0x180062d06  mov     qword ptr [rsp+300h+var_2A0+8], rax
0x180062d0b  lea     rax, [rsp+300h+var_2A0]
0x180062d10  mov     [rbp+200h+ObjectAttributes.ObjectName], rax
0x180062d14  movdqu  xmmword ptr [rbp+200h+ObjectAttributes.SecurityDescriptor], xmm0
0x180062d19  call    cs:__imp_ZwOpenKey
0x180062d20  nop     dword ptr [rax+rax+00h]
0x180062d25  test    eax, eax
0x180062d27  jns     short loc_180062D31
0x180062d29  mov     ebx, r13d
0x180062d2c  jmp     loc_18006305E
0x180062d31  mov     r12d, r13d
0x180062d34  mov     esi, r13d
0x180062d37  mov     rcx, [rsp+300h+KeyHandle]; KeyHandle
0x180062d3c  lea     rax, [rsp+300h+var_2C0]
0x180062d41  mov     [rsp+300h+ResultLength], rax; ResultLength
0x180062d46  mov     r9, rdi; KeyValueInformation
0x180062d49  mov     eax, [rsp+300h+var_2C0]
0x180062d4d  mov     r8d, 1; KeyValueInformationClass
0x180062d53  mov     edx, esi; Index
0x180062d55  mov     [rsp+300h+Length], eax; Length
0x180062d59  call    cs:__imp_ZwEnumerateValueKey
0x180062d60  nop     dword ptr [rax+rax+00h]
0x180062d65  mov     ebx, eax
0x180062d67  test    eax, eax
0x180062d69  jns     loc_180062E00
0x180062d6f  cmp     eax, 8000001Ah
0x180062d74  jz      loc_180062E35
0x180062d7a  cmp     eax, 0C0000023h
0x180062d7f  jz      short loc_180062D8C
0x180062d81  cmp     eax, 80000005h
0x180062d86  jnz     loc_18006305E
0x180062d8c  test    rdi, rdi
0x180062d8f  jz      short loc_180062DA5
0x180062d91  mov     edx, 63734943h; Tag
0x180062d96  mov     rcx, rdi; P
0x180062d99  call    cs:__imp_ExFreePoolWithTag
0x180062da0  nop     dword ptr [rax+rax+00h]
0x180062da5  mov     edx, [rsp+300h+var_2C0]
0x180062da9  mov     ecx, 102h
0x180062dae  mov     r8d, 63734943h
0x180062db4  call    cs:__imp_ExAllocatePool2
0x180062dbb  nop     dword ptr [rax+rax+00h]
0x180062dc0  mov     rdi, rax
0x180062dc3  test    rax, rax
0x180062dc6  jz      short loc_180062E2B
0x180062dc8  mov     rcx, [rsp+300h+KeyHandle]; KeyHandle
0x180062dcd  lea     rax, [rsp+300h+var_2C0]
0x180062dd2  mov     [rsp+300h+ResultLength], rax; ResultLength
0x180062dd7  mov     r9, rdi; KeyValueInformation
0x180062dda  mov     eax, [rsp+300h+var_2C0]
0x180062dde  mov     r8d, 1; KeyValueInformationClass
0x180062de4  mov     edx, esi; Index
0x180062de6  mov     [rsp+300h+Length], eax; Length
0x180062dea  call    cs:__imp_ZwEnumerateValueKey
0x180062df1  nop     dword ptr [rax+rax+00h]
0x180062df6  mov     ebx, eax
0x180062df8  test    eax, eax
0x180062dfa  js      loc_18006305E
0x180062e00  cmp     dword ptr [rdi+4], 3
0x180062e04  jnz     short loc_180062E24
0x180062e06  cmp     [rdi+10h], r13d
0x180062e0a  jbe     short loc_180062E24
0x180062e0c  mov     ecx, [rdi+0Ch]
0x180062e0f  test    ecx, ecx
0x180062e11  jz      short loc_180062E24
0x180062e13  lea     rdx, [rsp+300h+var_2B8]
0x180062e18  call    SIPolicyHashSizeToAlgorithm
0x180062e1d  test    eax, eax
0x180062e1f  js      short loc_180062E24
0x180062e21  inc     r12d
0x180062e24  inc     esi
0x180062e26  jmp     loc_180062D37
0x180062e2b  mov     ebx, 0C000009Ah
0x180062e30  jmp     loc_18006305E
0x180062e35  mov     eax, r12d
0x180062e38  lea     rdx, [rsp+300h+pulResult]; pulResult
0x180062e3d  lea     rcx, [rax+rax*8]
0x180062e41  shl     rcx, 4; ullOperand
0x180062e45  call    RtlULongLongToULong
0x180062e4a  mov     ebx, eax
0x180062e4c  test    eax, eax
0x180062e4e  js      loc_18006305E
0x180062e54  mov     edx, [rsp+300h+pulResult]
0x180062e58  mov     ecx, 100h
0x180062e5d  mov     r8d, 63734943h
0x180062e63  call    cs:__imp_ExAllocatePool2
0x180062e6a  nop     dword ptr [rax+rax+00h]
0x180062e6f  mov     rsi, rax
0x180062e72  test    rax, rax
0x180062e75  jnz     short loc_180062E81
0x180062e77  mov     ebx, 0C0000017h
0x180062e7c  jmp     loc_18006305E
0x180062e81  mov     r15d, r13d
0x180062e84  mov     [rsp+300h+pulResult], r13d
0x180062e89  mov     r14d, r13d
0x180062e8c  mov     rcx, [rsp+300h+KeyHandle]; KeyHandle
0x180062e91  lea     rax, [rsp+300h+var_2C0]
0x180062e96  mov     [rsp+300h+ResultLength], rax; ResultLength
0x180062e9b  mov     r9, rdi; KeyValueInformation
0x180062e9e  mov     eax, [rsp+300h+var_2C0]
0x180062ea2  mov     r8d, 1; KeyValueInformationClass
0x180062ea8  mov     edx, r14d; Index
0x180062eab  mov     [rsp+300h+Length], eax; Length
0x180062eaf  call    cs:__imp_ZwEnumerateValueKey
0x180062eb6  nop     dword ptr [rax+rax+00h]
0x180062ebb  mov     ebx, eax
0x180062ebd  test    eax, eax
0x180062ebf  jns     loc_180062F5B
0x180062ec5  cmp     eax, 8000001Ah
0x180062eca  jz      loc_180062FF5
0x180062ed0  cmp     eax, 0C0000023h
0x180062ed5  jz      short loc_180062EE2
0x180062ed7  cmp     eax, 80000005h
0x180062edc  jnz     loc_180063012
0x180062ee2  test    rdi, rdi
0x180062ee5  jz      short loc_180062EFB
0x180062ee7  mov     edx, 63734943h; Tag
0x180062eec  mov     rcx, rdi; P
0x180062eef  call    cs:__imp_ExFreePoolWithTag
0x180062ef6  nop     dword ptr [rax+rax+00h]
0x180062efb  mov     edx, [rsp+300h+var_2C0]
0x180062eff  mov     ecx, 102h
0x180062f04  mov     r8d, 63734943h
0x180062f0a  call    cs:__imp_ExAllocatePool2
0x180062f11  nop     dword ptr [rax+rax+00h]
0x180062f16  mov     rdi, rax
0x180062f19  test    rax, rax
0x180062f1c  jz      loc_180062FEE
0x180062f22  mov     rcx, [rsp+300h+KeyHandle]; KeyHandle
0x180062f27  lea     rax, [rsp+300h+var_2C0]
0x180062f2c  mov     [rsp+300h+ResultLength], rax; ResultLength
0x180062f31  mov     r9, rdi; KeyValueInformation
0x180062f34  mov     eax, [rsp+300h+var_2C0]
0x180062f38  mov     r8d, 1; KeyValueInformationClass
0x180062f3e  mov     edx, r14d; Index
0x180062f41  mov     [rsp+300h+Length], eax; Length
0x180062f45  call    cs:__imp_ZwEnumerateValueKey
0x180062f4c  nop     dword ptr [rax+rax+00h]
0x180062f51  mov     ebx, eax
0x180062f53  test    eax, eax
0x180062f55  js      loc_180063012
0x180062f5b  cmp     dword ptr [rdi+4], 3
0x180062f5f  jnz     loc_180062FE6
0x180062f65  cmp     [rdi+10h], r13d
0x180062f69  jbe     short loc_180062FE6
0x180062f6b  mov     ebx, [rdi+0Ch]
0x180062f6e  test    ebx, ebx
0x180062f70  jz      short loc_180062FE6
0x180062f72  lea     rdx, [rsp+300h+var_2B8]
0x180062f77  mov     ecx, ebx
0x180062f79  call    SIPolicyHashSizeToAlgorithm
0x180062f7e  test    eax, eax
0x180062f80  js      short loc_180062FE6
0x180062f82  mov     eax, [rdi+8]
0x180062f85  mov     r8d, 63734943h
0x180062f8b  mov     edx, ebx
0x180062f8d  mov     [rsp+300h+var_2A4], eax
0x180062f91  mov     ecx, 100h
0x180062f96  call    cs:__imp_ExAllocatePool2
0x180062f9d  nop     dword ptr [rax+rax+00h]
0x180062fa2  mov     ecx, r15d
0x180062fa5  lea     r15, [rcx+rcx*8]
0x180062fa9  add     r15, r15
0x180062fac  mov     [rsi+r15*8+10h], rax
0x180062fb1  test    rax, rax
0x180062fb4  jz      short loc_18006300A
0x180062fb6  mov     edx, [rsp+300h+var_2A4]
0x180062fba  mov     r8d, ebx; Size
0x180062fbd  add     rdx, rdi; Src
0x180062fc0  mov     rcx, rax; void *
0x180062fc3  call    memmove
0x180062fc8  mov     eax, [rsp+300h+var_2B8]
0x180062fcc  mov     [rsi+r15*8+4], eax
0x180062fd1  mov     [rsi+r15*8+8], ebx
0x180062fd6  mov     r15d, [rsp+300h+pulResult]
0x180062fdb  inc     r15d
0x180062fde  mov     [rsp+300h+pulResult], r15d
0x180062fe3  xor     r13d, r13d
0x180062fe6  inc     r14d
0x180062fe9  jmp     loc_180062E8C
0x180062fee  mov     ebx, 0C000009Ah
0x180062ff3  jmp     short loc_180063012
0x180062ff5  mov     rax, [rsp+300h+var_290]
0x180062ffa  mov     ebx, r13d
0x180062ffd  mov     [rax], r12d
0x180063000  mov     rax, [rsp+300h+var_288]
0x180063005  mov     [rax], rsi
0x180063008  jmp     short loc_18006305E
0x18006300a  mov     ebx, 0C0000017h
0x18006300f  xor     r13d, r13d
0x180063012  mov     r15, rsi
0x180063015  mov     r14d, r13d
0x180063018  test    r12d, r12d
0x18006301b  jz      short loc_18006304A
0x18006301d  mov     eax, r14d
0x180063020  lea     rcx, [rax+rax*8]
0x180063024  add     rcx, rcx
0x180063027  mov     rcx, [r15+rcx*8+10h]; P
0x18006302c  test    rcx, rcx
0x18006302f  jz      short loc_180063042
0x180063031  mov     edx, 63734943h; Tag
0x180063036  call    cs:__imp_ExFreePoolWithTag
0x18006303d  nop     dword ptr [rax+rax+00h]
0x180063042  inc     r14d
0x180063045  cmp     r14d, r12d
0x180063048  jb      short loc_18006301D
0x18006304a  mov     edx, 63734943h; Tag
0x18006304f  mov     rcx, rsi; P
0x180063052  call    cs:__imp_ExFreePoolWithTag
0x180063059  nop     dword ptr [rax+rax+00h]
0x18006305e  mov     rcx, [rsp+300h+KeyHandle]; Handle
0x180063063  test    rcx, rcx
0x180063066  jz      short loc_180063074
0x180063068  call    cs:__imp_ZwClose
0x18006306f  nop     dword ptr [rax+rax+00h]
0x180063074  test    rdi, rdi
0x180063077  jz      short loc_18006308D
0x180063079  mov     edx, 63734943h; Tag
0x18006307e  mov     rcx, rdi; P
0x180063081  call    cs:__imp_ExFreePoolWithTag
0x180063088  nop     dword ptr [rax+rax+00h]
0x18006308d  mov     eax, ebx
  ... truncated ...
```
