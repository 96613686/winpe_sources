# CipPrepareDynamicDeveloperSigners

- ea: `0x180062d38`
- end: `0x18006322a`
- name: `CipPrepareDynamicDeveloperSigners`
- size: `1266`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180070b14`

## callees

- `0x18000cf48`
- `0x18002c0d0`
- `0x18002c200`
- `0x18002c500`
- `0x180062d38`
- `0x180079a50`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180062f24`
- `ntoskrnl!ExAllocatePool2` at `0x180062fd3`
- `ntoskrnl!ExAllocatePool2` at `0x18006307a`
- `ntoskrnl!ExAllocatePool2` at `0x180063106`
- `ntoskrnl!ExAllocatePool2` at `0x180062f24`
- `ntoskrnl!ExAllocatePool2` at `0x180062fd3`
- `ntoskrnl!ExAllocatePool2` at `0x18006307a`
- `ntoskrnl!ExAllocatePool2` at `0x180063106`
- `ntoskrnl!ExFreePoolWithTag` at `0x180062f09`
- `ntoskrnl!ExFreePoolWithTag` at `0x18006305f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800631a6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800631c2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800631f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x180062f09`
- `ntoskrnl!ExFreePoolWithTag` at `0x18006305f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800631a6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800631c2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800631f1`
- `ntoskrnl!ZwClose` at `0x1800631d8`
- `ntoskrnl!ZwClose` at `0x1800631d8`
- `ntoskrnl!ZwOpenKey` at `0x180062e89`
- `ntoskrnl!ZwOpenKey` at `0x180062e89`
- `ntoskrnl!ZwEnumerateValueKey` at `0x180062ec9`
- `ntoskrnl!ZwEnumerateValueKey` at `0x180062f5a`
- `ntoskrnl!ZwEnumerateValueKey` at `0x18006301f`
- `ntoskrnl!ZwEnumerateValueKey` at `0x1800630b5`
- `ntoskrnl!ZwEnumerateValueKey` at `0x180062ec9`
- `ntoskrnl!ZwEnumerateValueKey` at `0x180062f5a`
- `ntoskrnl!ZwEnumerateValueKey` at `0x18006301f`
- `ntoskrnl!ZwEnumerateValueKey` at `0x1800630b5`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x180062de4`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x180062de4`

## string_xrefs

- `0x180062d88`: `\Registry\Machine\SYSTEM\CurrentControlSet\Control\CI\Developer\DeveloperUnlockCertificates`

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
0x180062d38  mov     [rsp-8+arg_10], rbx
0x180062d3d  push    rbp
0x180062d3e  push    rsi
0x180062d3f  push    rdi
0x180062d40  push    r12
0x180062d42  push    r13
0x180062d44  push    r14
0x180062d46  push    r15
0x180062d48  lea     rbp, [rsp-1D0h]
0x180062d50  sub     rsp, 2D0h
0x180062d57  mov     rax, cs:__security_cookie
0x180062d5e  xor     rax, rsp
0x180062d61  mov     [rbp+200h+var_40], rax
0x180062d68  mov     [rsp+300h+var_288], rdx
0x180062d6d  mov     ebx, 20Ah
0x180062d72  mov     [rsp+300h+var_290], rcx
0x180062d77  mov     r8d, ebx; Size
0x180062d7a  xor     edx, edx; Val
0x180062d7c  lea     rcx, [rbp+200h+var_250]; void *
0x180062d80  call    memset
0x180062d85  xor     r13d, r13d
0x180062d88  lea     r8, aRegistryMachin_5; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x180062d8f  xorps   xmm0, xmm0
0x180062d92  mov     [rsp+300h+var_2A8], r13d
0x180062d97  xor     eax, eax
0x180062d99  mov     [rsp+300h+KeyHandle], r13
0x180062d9e  lea     rax, [rsp+300h+var_2A8]
0x180062da3  mov     [rsp+300h+var_2B8], r13d
0x180062da8  mov     [rsp+300h+var_2D0], rax
0x180062dad  lea     rcx, aCidevelopercer; "CIDeveloperCerts"
0x180062db4  lea     rax, [rbp+200h+var_250]
0x180062db8  mov     dword ptr [rsp+300h+ResultLength], ebx
0x180062dbc  movups  xmmword ptr [rbp+200h+ObjectAttributes.ObjectName], xmm0
0x180062dc0  xor     r9d, r9d
0x180062dc3  mov     qword ptr [rsp+300h+Length], rax
0x180062dc8  xor     edx, edx
0x180062dca  mov     [rsp+300h+pulResult], r13d
0x180062dcf  movups  [rsp+300h+var_2A0], xmm0
0x180062dd4  mov     edi, r13d
0x180062dd7  mov     [rsp+300h+var_2C0], r13d
0x180062ddc  movups  xmmword ptr [rbp+200h+ObjectAttributes.Length], xmm0
0x180062de0  movups  xmmword ptr [rbp+200h+ObjectAttributes+1Ch], xmm0
0x180062de4  call    cs:__imp_RtlGetPersistedStateLocation
0x180062deb  nop     dword ptr [rax+rax+00h]
0x180062df0  mov     ebx, eax
0x180062df2  test    eax, eax
0x180062df4  js      loc_1800631CE
0x180062dfa  xorps   xmm0, xmm0
0x180062dfd  lea     rax, [rbp+200h+var_250]
0x180062e01  movups  [rsp+300h+var_2A0], xmm0
0x180062e06  mov     ecx, 7FFFh
0x180062e0b  lea     edx, [r13+2]
0x180062e0f  cmp     [rax], r13w
0x180062e13  jz      short loc_180062E1E
0x180062e15  add     rax, rdx
0x180062e18  sub     rcx, 1
0x180062e1c  jnz     short loc_180062E0F
0x180062e1e  mov     rax, rcx
0x180062e21  neg     rax
0x180062e24  sbb     ebx, ebx
0x180062e26  not     ebx
0x180062e28  and     ebx, 0C000000Dh
0x180062e2e  test    rcx, rcx
0x180062e31  jz      loc_1800631CE
0x180062e37  add     cx, cx
0x180062e3a  mov     [rbp+200h+ObjectAttributes.Length], 30h ; '0'
0x180062e41  mov     eax, 0FFFEh
0x180062e46  mov     [rbp+200h+ObjectAttributes.RootDirectory], r13
0x180062e4a  sub     ax, cx
0x180062e4d  mov     [rbp+200h+ObjectAttributes.Attributes], 240h
0x180062e54  mov     word ptr [rsp+300h+var_2A0], ax
0x180062e59  lea     r8, [rbp+200h+ObjectAttributes]; ObjectAttributes
0x180062e5d  add     ax, dx
0x180062e60  lea     rcx, [rsp+300h+KeyHandle]; KeyHandle
0x180062e65  mov     word ptr [rsp+300h+var_2A0+2], ax
0x180062e6a  xorps   xmm0, xmm0
0x180062e6d  lea     rax, [rbp+200h+var_250]
0x180062e71  mov     edx, 20019h; DesiredAccess
0x180062e76  mov     qword ptr [rsp+300h+var_2A0+8], rax
0x180062e7b  lea     rax, [rsp+300h+var_2A0]
0x180062e80  mov     [rbp+200h+ObjectAttributes.ObjectName], rax
0x180062e84  movdqu  xmmword ptr [rbp+200h+ObjectAttributes.SecurityDescriptor], xmm0
0x180062e89  call    cs:__imp_ZwOpenKey
0x180062e90  nop     dword ptr [rax+rax+00h]
0x180062e95  test    eax, eax
0x180062e97  jns     short loc_180062EA1
0x180062e99  mov     ebx, r13d
0x180062e9c  jmp     loc_1800631CE
0x180062ea1  mov     r12d, r13d
0x180062ea4  mov     esi, r13d
0x180062ea7  mov     rcx, [rsp+300h+KeyHandle]; KeyHandle
0x180062eac  lea     rax, [rsp+300h+var_2C0]
0x180062eb1  mov     [rsp+300h+ResultLength], rax; ResultLength
0x180062eb6  mov     r9, rdi; KeyValueInformation
0x180062eb9  mov     eax, [rsp+300h+var_2C0]
0x180062ebd  mov     r8d, 1; KeyValueInformationClass
0x180062ec3  mov     edx, esi; Index
0x180062ec5  mov     [rsp+300h+Length], eax; Length
0x180062ec9  call    cs:__imp_ZwEnumerateValueKey
0x180062ed0  nop     dword ptr [rax+rax+00h]
0x180062ed5  mov     ebx, eax
0x180062ed7  test    eax, eax
0x180062ed9  jns     loc_180062F70
0x180062edf  cmp     eax, 8000001Ah
0x180062ee4  jz      loc_180062FA5
0x180062eea  cmp     eax, 0C0000023h
0x180062eef  jz      short loc_180062EFC
0x180062ef1  cmp     eax, 80000005h
0x180062ef6  jnz     loc_1800631CE
0x180062efc  test    rdi, rdi
0x180062eff  jz      short loc_180062F15
0x180062f01  mov     edx, 63734943h; Tag
0x180062f06  mov     rcx, rdi; P
0x180062f09  call    cs:__imp_ExFreePoolWithTag
0x180062f10  nop     dword ptr [rax+rax+00h]
0x180062f15  mov     edx, [rsp+300h+var_2C0]
0x180062f19  mov     ecx, 102h
0x180062f1e  mov     r8d, 63734943h
0x180062f24  call    cs:__imp_ExAllocatePool2
0x180062f2b  nop     dword ptr [rax+rax+00h]
0x180062f30  mov     rdi, rax
0x180062f33  test    rax, rax
0x180062f36  jz      short loc_180062F9B
0x180062f38  mov     rcx, [rsp+300h+KeyHandle]; KeyHandle
0x180062f3d  lea     rax, [rsp+300h+var_2C0]
0x180062f42  mov     [rsp+300h+ResultLength], rax; ResultLength
0x180062f47  mov     r9, rdi; KeyValueInformation
0x180062f4a  mov     eax, [rsp+300h+var_2C0]
0x180062f4e  mov     r8d, 1; KeyValueInformationClass
0x180062f54  mov     edx, esi; Index
0x180062f56  mov     [rsp+300h+Length], eax; Length
0x180062f5a  call    cs:__imp_ZwEnumerateValueKey
0x180062f61  nop     dword ptr [rax+rax+00h]
0x180062f66  mov     ebx, eax
0x180062f68  test    eax, eax
0x180062f6a  js      loc_1800631CE
0x180062f70  cmp     dword ptr [rdi+4], 3
0x180062f74  jnz     short loc_180062F94
0x180062f76  cmp     [rdi+10h], r13d
0x180062f7a  jbe     short loc_180062F94
0x180062f7c  mov     ecx, [rdi+0Ch]
0x180062f7f  test    ecx, ecx
0x180062f81  jz      short loc_180062F94
0x180062f83  lea     rdx, [rsp+300h+var_2B8]
0x180062f88  call    SIPolicyHashSizeToAlgorithm
0x180062f8d  test    eax, eax
0x180062f8f  js      short loc_180062F94
0x180062f91  inc     r12d
0x180062f94  inc     esi
0x180062f96  jmp     loc_180062EA7
0x180062f9b  mov     ebx, 0C000009Ah
0x180062fa0  jmp     loc_1800631CE
0x180062fa5  mov     eax, r12d
0x180062fa8  lea     rdx, [rsp+300h+pulResult]; pulResult
0x180062fad  lea     rcx, [rax+rax*8]
0x180062fb1  shl     rcx, 4; ullOperand
0x180062fb5  call    RtlULongLongToULong
0x180062fba  mov     ebx, eax
0x180062fbc  test    eax, eax
0x180062fbe  js      loc_1800631CE
0x180062fc4  mov     edx, [rsp+300h+pulResult]
0x180062fc8  mov     ecx, 100h
0x180062fcd  mov     r8d, 63734943h
0x180062fd3  call    cs:__imp_ExAllocatePool2
0x180062fda  nop     dword ptr [rax+rax+00h]
0x180062fdf  mov     rsi, rax
0x180062fe2  test    rax, rax
0x180062fe5  jnz     short loc_180062FF1
0x180062fe7  mov     ebx, 0C0000017h
0x180062fec  jmp     loc_1800631CE
0x180062ff1  mov     r15d, r13d
0x180062ff4  mov     [rsp+300h+pulResult], r13d
0x180062ff9  mov     r14d, r13d
0x180062ffc  mov     rcx, [rsp+300h+KeyHandle]; KeyHandle
0x180063001  lea     rax, [rsp+300h+var_2C0]
0x180063006  mov     [rsp+300h+ResultLength], rax; ResultLength
0x18006300b  mov     r9, rdi; KeyValueInformation
0x18006300e  mov     eax, [rsp+300h+var_2C0]
0x180063012  mov     r8d, 1; KeyValueInformationClass
0x180063018  mov     edx, r14d; Index
0x18006301b  mov     [rsp+300h+Length], eax; Length
0x18006301f  call    cs:__imp_ZwEnumerateValueKey
0x180063026  nop     dword ptr [rax+rax+00h]
0x18006302b  mov     ebx, eax
0x18006302d  test    eax, eax
0x18006302f  jns     loc_1800630CB
0x180063035  cmp     eax, 8000001Ah
0x18006303a  jz      loc_180063165
0x180063040  cmp     eax, 0C0000023h
0x180063045  jz      short loc_180063052
0x180063047  cmp     eax, 80000005h
0x18006304c  jnz     loc_180063182
0x180063052  test    rdi, rdi
0x180063055  jz      short loc_18006306B
0x180063057  mov     edx, 63734943h; Tag
0x18006305c  mov     rcx, rdi; P
0x18006305f  call    cs:__imp_ExFreePoolWithTag
0x180063066  nop     dword ptr [rax+rax+00h]
0x18006306b  mov     edx, [rsp+300h+var_2C0]
0x18006306f  mov     ecx, 102h
0x180063074  mov     r8d, 63734943h
0x18006307a  call    cs:__imp_ExAllocatePool2
0x180063081  nop     dword ptr [rax+rax+00h]
0x180063086  mov     rdi, rax
0x180063089  test    rax, rax
0x18006308c  jz      loc_18006315E
0x180063092  mov     rcx, [rsp+300h+KeyHandle]; KeyHandle
0x180063097  lea     rax, [rsp+300h+var_2C0]
0x18006309c  mov     [rsp+300h+ResultLength], rax; ResultLength
0x1800630a1  mov     r9, rdi; KeyValueInformation
0x1800630a4  mov     eax, [rsp+300h+var_2C0]
0x1800630a8  mov     r8d, 1; KeyValueInformationClass
0x1800630ae  mov     edx, r14d; Index
0x1800630b1  mov     [rsp+300h+Length], eax; Length
0x1800630b5  call    cs:__imp_ZwEnumerateValueKey
0x1800630bc  nop     dword ptr [rax+rax+00h]
0x1800630c1  mov     ebx, eax
0x1800630c3  test    eax, eax
0x1800630c5  js      loc_180063182
0x1800630cb  cmp     dword ptr [rdi+4], 3
0x1800630cf  jnz     loc_180063156
0x1800630d5  cmp     [rdi+10h], r13d
0x1800630d9  jbe     short loc_180063156
0x1800630db  mov     ebx, [rdi+0Ch]
0x1800630de  test    ebx, ebx
0x1800630e0  jz      short loc_180063156
0x1800630e2  lea     rdx, [rsp+300h+var_2B8]
0x1800630e7  mov     ecx, ebx
0x1800630e9  call    SIPolicyHashSizeToAlgorithm
0x1800630ee  test    eax, eax
0x1800630f0  js      short loc_180063156
0x1800630f2  mov     eax, [rdi+8]
0x1800630f5  mov     r8d, 63734943h
0x1800630fb  mov     edx, ebx
0x1800630fd  mov     [rsp+300h+var_2A4], eax
0x180063101  mov     ecx, 100h
0x180063106  call    cs:__imp_ExAllocatePool2
0x18006310d  nop     dword ptr [rax+rax+00h]
0x180063112  mov     ecx, r15d
0x180063115  lea     r15, [rcx+rcx*8]
0x180063119  add     r15, r15
0x18006311c  mov     [rsi+r15*8+10h], rax
0x180063121  test    rax, rax
0x180063124  jz      short loc_18006317A
0x180063126  mov     edx, [rsp+300h+var_2A4]
0x18006312a  mov     r8d, ebx; Size
0x18006312d  add     rdx, rdi; Src
0x180063130  mov     rcx, rax; void *
0x180063133  call    memmove
0x180063138  mov     eax, [rsp+300h+var_2B8]
0x18006313c  mov     [rsi+r15*8+4], eax
0x180063141  mov     [rsi+r15*8+8], ebx
0x180063146  mov     r15d, [rsp+300h+pulResult]
0x18006314b  inc     r15d
0x18006314e  mov     [rsp+300h+pulResult], r15d
0x180063153  xor     r13d, r13d
0x180063156  inc     r14d
0x180063159  jmp     loc_180062FFC
0x18006315e  mov     ebx, 0C000009Ah
0x180063163  jmp     short loc_180063182
0x180063165  mov     rax, [rsp+300h+var_290]
0x18006316a  mov     ebx, r13d
0x18006316d  mov     [rax], r12d
0x180063170  mov     rax, [rsp+300h+var_288]
0x180063175  mov     [rax], rsi
0x180063178  jmp     short loc_1800631CE
0x18006317a  mov     ebx, 0C0000017h
0x18006317f  xor     r13d, r13d
0x180063182  mov     r15, rsi
0x180063185  mov     r14d, r13d
0x180063188  test    r12d, r12d
0x18006318b  jz      short loc_1800631BA
0x18006318d  mov     eax, r14d
0x180063190  lea     rcx, [rax+rax*8]
0x180063194  add     rcx, rcx
0x180063197  mov     rcx, [r15+rcx*8+10h]; P
0x18006319c  test    rcx, rcx
0x18006319f  jz      short loc_1800631B2
0x1800631a1  mov     edx, 63734943h; Tag
0x1800631a6  call    cs:__imp_ExFreePoolWithTag
0x1800631ad  nop     dword ptr [rax+rax+00h]
0x1800631b2  inc     r14d
0x1800631b5  cmp     r14d, r12d
0x1800631b8  jb      short loc_18006318D
0x1800631ba  mov     edx, 63734943h; Tag
0x1800631bf  mov     rcx, rsi; P
0x1800631c2  call    cs:__imp_ExFreePoolWithTag
0x1800631c9  nop     dword ptr [rax+rax+00h]
0x1800631ce  mov     rcx, [rsp+300h+KeyHandle]; Handle
0x1800631d3  test    rcx, rcx
0x1800631d6  jz      short loc_1800631E4
0x1800631d8  call    cs:__imp_ZwClose
0x1800631df  nop     dword ptr [rax+rax+00h]
0x1800631e4  test    rdi, rdi
0x1800631e7  jz      short loc_1800631FD
0x1800631e9  mov     edx, 63734943h; Tag
0x1800631ee  mov     rcx, rdi; P
0x1800631f1  call    cs:__imp_ExFreePoolWithTag
0x1800631f8  nop     dword ptr [rax+rax+00h]
0x1800631fd  mov     eax, ebx
  ... truncated ...
```
