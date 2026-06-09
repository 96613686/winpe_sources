# BwcGetQoSParameters

- ea: `0x1400127f0`
- end: `0x140012b06`
- name: `BwcGetQoSParameters`
- size: `790`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, registry_config, service_task`

## callers

- `0x140013570`

## callees

- `0x1400127f0`
- `0x1400161f0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14001285e`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400128b8`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001291d`
- `ntoskrnl!RtlInitUnicodeString` at `0x140012986`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001285e`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400128b8`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001291d`
- `ntoskrnl!RtlInitUnicodeString` at `0x140012986`
- `ntoskrnl!ZwQueryValueKey` at `0x1400128e6`
- `ntoskrnl!ZwQueryValueKey` at `0x14001294c`
- `ntoskrnl!ZwQueryValueKey` at `0x1400129af`
- `ntoskrnl!ZwQueryValueKey` at `0x140012a14`
- `ntoskrnl!ZwQueryValueKey` at `0x1400128e6`
- `ntoskrnl!ZwQueryValueKey` at `0x14001294c`
- `ntoskrnl!ZwQueryValueKey` at `0x1400129af`
- `ntoskrnl!ZwQueryValueKey` at `0x140012a14`
- `ntoskrnl!ZwClose` at `0x140012ac0`
- `ntoskrnl!ZwClose` at `0x140012ac0`
- `ntoskrnl!ZwOpenKey` at `0x140012899`
- `ntoskrnl!ZwOpenKey` at `0x140012899`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012ad9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012ad9`
- `ntoskrnl!ExAllocatePool2` at `0x1400129db`
- `ntoskrnl!ExAllocatePool2` at `0x1400129db`

## string_xrefs

- `0x14001282c`: `\Registry\Machine\SYSTEM\CurrentControlSet\Services\RemoteAccess\Parameters`
- `0x1400128ad`: `QosTokenSizeFactor`

## pseudocode

```c
__int64 __fastcall BwcGetQoSParameters(unsigned __int64 a1, __int64 *a2, _DWORD *a3, _DWORD *a4)
{
  unsigned __int16 *Pool2; // rbx
  unsigned int v9; // eax
  unsigned int v10; // eax
  NTSTATUS v11; // eax
  unsigned __int16 *v12; // rdx
  unsigned __int64 v13; // r9
  unsigned __int64 v14; // r10
  __int64 v15; // rax
  __int64 i; // rax
  unsigned __int16 v17; // cx
  __int64 v18; // r8
  ULONG ResultLength; // [rsp+30h] [rbp-59h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-51h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+40h] [rbp-49h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-39h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-9h] BYREF
  __int128 KeyValueInformation; // [rsp+90h] [rbp+7h] BYREF
  __int64 v26; // [rsp+A0h] [rbp+17h]

  ResultLength = 0;
  KeyHandle = 0;
  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  Pool2 = 0;
  v26 = 0;
  DestinationString = 0;
  ValueName = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  KeyValueInformation = 0;
  RtlInitUnicodeString(
    &DestinationString,
    L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Services\\RemoteAccess\\Parameters");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  if ( ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) < 0 )
    goto LABEL_33;
  RtlInitUnicodeString(&ValueName, L"QosTokenSizeFactor");
  if ( ZwQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, &KeyValueInformation, 0x18u, &ResultLength) >= 0
    && (v9 = HIDWORD(KeyValueInformation), *a3 = HIDWORD(KeyValueInformation), v9) )
  {
    if ( v9 > 0x14 )
      *a3 = 20;
  }
  else
  {
    *a3 = 4;
  }
  RtlInitUnicodeString(&ValueName, L"QosPeakRateFactor");
  if ( ZwQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, &KeyValueInformation, 0x18u, &ResultLength) >= 0
    && (v10 = HIDWORD(KeyValueInformation), *a4 = HIDWORD(KeyValueInformation), v10) )
  {
    if ( v10 > 0x14 )
      *a4 = 20;
  }
  else
  {
    *a4 = 4;
  }
  RtlInitUnicodeString(&ValueName, L"QosQueueLengths");
  v11 = ZwQueryValueKey(KeyHandle, &ValueName, KeyValueFullInformation, 0, 0, &ResultLength);
  if ( v11 != -1073741789 && v11 != -2147483643 )
    goto LABEL_33;
  Pool2 = (unsigned __int16 *)ExAllocatePool2(64, ResultLength, 1835235138);
  if ( !Pool2
    || ZwQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, Pool2, ResultLength, &ResultLength) < 0 )
  {
    goto LABEL_33;
  }
  v12 = Pool2 + 6;
  v13 = 0;
  v14 = 0;
  while ( 2 )
  {
    v15 = -1;
    do
      ++v15;
    while ( v12[v15] );
    if ( !(_DWORD)v15 )
    {
LABEL_33:
      i = 250000;
      if ( a1 > 0x1400 )
        i = 125000;
      break;
    }
    for ( i = 0; ; i = v18 + 2 * (5 * i - 24) )
    {
      v17 = *v12;
      if ( !*v12 )
        break;
      if ( v17 == 45 )
      {
        v14 = i;
LABEL_25:
        ++v12;
        i = 0;
        v17 = *v12;
        goto LABEL_26;
      }
      if ( v17 == 58 )
      {
        v13 = i;
        goto LABEL_25;
      }
LABEL_26:
      if ( v17 < 0x30u )
        break;
      v18 = *v12;
      if ( (unsigned int)v18 > 0x39 )
        break;
      ++v12;
    }
    if ( a1 < v14 || a1 > v13 )
    {
      ++v12;
      continue;
    }
    break;
  }
  *a2 = i;
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0x6D637742u);
  return 0;
}

```

## disassembly

```asm
0x1400127f0  push    rbp
0x1400127f2  push    rbx
0x1400127f3  push    rsi
0x1400127f4  push    rdi
0x1400127f5  push    r12
0x1400127f7  push    r14
0x1400127f9  push    r15
0x1400127fb  lea     rbp, [rsp-27h]
0x140012800  sub     rsp, 0B0h
0x140012807  mov     rax, cs:__security_cookie
0x14001280e  xor     rax, rsp
0x140012811  mov     [rbp+57h+var_38], rax
0x140012815  xorps   xmm0, xmm0
0x140012818  xor     r12d, r12d
0x14001281b  mov     rdi, rdx
0x14001281e  mov     [rbp+57h+var_B0], r12d
0x140012822  mov     r15, rcx
0x140012825  mov     [rbp+57h+KeyHandle], r12
0x140012829  xorps   xmm1, xmm1
0x14001282c  lea     rdx, SourceString; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x140012833  xor     eax, eax
0x140012835  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140012839  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14001283d  mov     r14, r9
0x140012840  mov     rsi, r8
0x140012843  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x140012847  mov     ebx, r12d
0x14001284a  mov     [rbp+57h+var_40], rax
0x14001284e  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140012852  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm1
0x140012856  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14001285a  movups  [rbp+57h+KeyValueInformation], xmm0
0x14001285e  call    cs:__imp_RtlInitUnicodeString
0x140012865  nop     dword ptr [rax+rax+00h]
0x14001286a  lea     rax, [rbp+57h+DestinationString]
0x14001286e  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140012875  xorps   xmm0, xmm0
0x140012878  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14001287c  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140012880  mov     [rbp+57h+ObjectAttributes.RootDirectory], r12
0x140012884  mov     edx, 20019h; DesiredAccess
0x140012889  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140012890  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140012894  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140012899  call    cs:__imp_ZwOpenKey
0x1400128a0  nop     dword ptr [rax+rax+00h]
0x1400128a5  test    eax, eax
0x1400128a7  js      loc_140012AA1
0x1400128ad  lea     rdx, aQostokensizefa; "QosTokenSizeFactor"
0x1400128b4  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x1400128b8  call    cs:__imp_RtlInitUnicodeString
0x1400128bf  nop     dword ptr [rax+rax+00h]
0x1400128c4  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1400128c8  lea     rax, [rbp+57h+var_B0]
0x1400128cc  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x1400128d1  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x1400128d5  lea     r8d, [r12+2]; KeyValueInformationClass
0x1400128da  mov     [rsp+0E0h+Length], 18h; Length
0x1400128e2  lea     rdx, [rbp+57h+ValueName]; ValueName
0x1400128e6  call    cs:__imp_ZwQueryValueKey
0x1400128ed  nop     dword ptr [rax+rax+00h]
0x1400128f2  test    eax, eax
0x1400128f4  js      short loc_14001290C
0x1400128f6  mov     eax, dword ptr [rbp+57h+KeyValueInformation+0Ch]
0x1400128f9  mov     [rsi], eax
0x1400128fb  test    eax, eax
0x1400128fd  jz      short loc_14001290C
0x1400128ff  cmp     eax, 14h
0x140012902  jbe     short loc_140012912
0x140012904  mov     dword ptr [rsi], 14h
0x14001290a  jmp     short loc_140012912
0x14001290c  mov     dword ptr [rsi], 4
0x140012912  lea     rdx, aQospeakratefac; "QosPeakRateFactor"
0x140012919  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x14001291d  call    cs:__imp_RtlInitUnicodeString
0x140012924  nop     dword ptr [rax+rax+00h]
0x140012929  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14001292d  lea     rax, [rbp+57h+var_B0]
0x140012931  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x140012936  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x14001293a  mov     r8d, 2; KeyValueInformationClass
0x140012940  mov     [rsp+0E0h+Length], 18h; Length
0x140012948  lea     rdx, [rbp+57h+ValueName]; ValueName
0x14001294c  call    cs:__imp_ZwQueryValueKey
0x140012953  nop     dword ptr [rax+rax+00h]
0x140012958  test    eax, eax
0x14001295a  js      short loc_140012974
0x14001295c  mov     eax, dword ptr [rbp+57h+KeyValueInformation+0Ch]
0x14001295f  mov     [r14], eax
0x140012962  test    eax, eax
0x140012964  jz      short loc_140012974
0x140012966  cmp     eax, 14h
0x140012969  jbe     short loc_14001297B
0x14001296b  mov     dword ptr [r14], 14h
0x140012972  jmp     short loc_14001297B
0x140012974  mov     dword ptr [r14], 4
0x14001297b  lea     rdx, aQosqueuelength; "QosQueueLengths"
0x140012982  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x140012986  call    cs:__imp_RtlInitUnicodeString
0x14001298d  nop     dword ptr [rax+rax+00h]
0x140012992  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140012996  lea     rax, [rbp+57h+var_B0]
0x14001299a  xor     r9d, r9d; KeyValueInformation
0x14001299d  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x1400129a2  lea     rdx, [rbp+57h+ValueName]; ValueName
0x1400129a6  mov     [rsp+0E0h+Length], r12d; Length
0x1400129ab  lea     r8d, [r9+1]; KeyValueInformationClass
0x1400129af  call    cs:__imp_ZwQueryValueKey
0x1400129b6  nop     dword ptr [rax+rax+00h]
0x1400129bb  cmp     eax, 0C0000023h
0x1400129c0  jz      short loc_1400129CD
0x1400129c2  cmp     eax, 80000005h
0x1400129c7  jnz     loc_140012AA1
0x1400129cd  mov     edx, [rbp+57h+var_B0]
0x1400129d0  mov     ecx, 40h ; '@'
0x1400129d5  mov     r8d, 6D637742h
0x1400129db  call    cs:__imp_ExAllocatePool2
0x1400129e2  nop     dword ptr [rax+rax+00h]
0x1400129e7  mov     rbx, rax
0x1400129ea  test    rax, rax
0x1400129ed  jz      loc_140012AA1
0x1400129f3  mov     ecx, [rbp+57h+var_B0]
0x1400129f6  lea     rax, [rbp+57h+var_B0]
0x1400129fa  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x1400129ff  lea     rdx, [rbp+57h+ValueName]; ValueName
0x140012a03  mov     [rsp+0E0h+Length], ecx; Length
0x140012a07  mov     r9, rbx; KeyValueInformation
0x140012a0a  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140012a0e  mov     r8d, 2; KeyValueInformationClass
0x140012a14  call    cs:__imp_ZwQueryValueKey
0x140012a1b  nop     dword ptr [rax+rax+00h]
0x140012a20  test    eax, eax
0x140012a22  js      short loc_140012AA1
0x140012a24  lea     rdx, [rbx+0Ch]
0x140012a28  mov     r9, r12
0x140012a2b  mov     r10, r12
0x140012a2e  mov     r11d, 30h ; '0'
0x140012a34  or      rax, 0FFFFFFFFFFFFFFFFh
0x140012a38  inc     rax
0x140012a3b  cmp     [rdx+rax*2], r12w
0x140012a40  jnz     short loc_140012A38
0x140012a42  test    eax, eax
0x140012a44  jz      short loc_140012AA1
0x140012a46  mov     rax, r12
0x140012a49  jmp     short loc_140012A89
0x140012a4b  cmp     cx, 2Dh ; '-'
0x140012a4f  jnz     short loc_140012A56
0x140012a51  mov     r10, rax
0x140012a54  jmp     short loc_140012A5F
0x140012a56  cmp     cx, 3Ah ; ':'
0x140012a5a  jnz     short loc_140012A69
0x140012a5c  mov     r9, rax
0x140012a5f  add     rdx, 2
0x140012a63  mov     rax, r12
0x140012a66  movzx   ecx, word ptr [rdx]
0x140012a69  cmp     cx, r11w
0x140012a6d  jb      short loc_140012A91
0x140012a6f  movzx   r8d, word ptr [rdx]
0x140012a73  cmp     r8d, 39h ; '9'
0x140012a77  ja      short loc_140012A91
0x140012a79  lea     rax, [rax+rax*4]
0x140012a7d  add     rdx, 2
0x140012a81  lea     rax, [rax-18h]
0x140012a85  lea     rax, [r8+rax*2]
0x140012a89  movzx   ecx, word ptr [rdx]
0x140012a8c  test    cx, cx
0x140012a8f  jnz     short loc_140012A4B
0x140012a91  cmp     r15, r10
0x140012a94  jb      short loc_140012A9B
0x140012a96  cmp     r15, r9
0x140012a99  jbe     short loc_140012AB4
0x140012a9b  add     rdx, 2
0x140012a9f  jmp     short loc_140012A34
0x140012aa1  mov     eax, 3D090h
0x140012aa6  cmp     r15, 1400h
0x140012aad  jbe     short loc_140012AB4
0x140012aaf  mov     eax, 1E848h
0x140012ab4  mov     [rdi], rax
0x140012ab7  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x140012abb  test    rcx, rcx
0x140012abe  jz      short loc_140012ACC
0x140012ac0  call    cs:__imp_ZwClose
0x140012ac7  nop     dword ptr [rax+rax+00h]
0x140012acc  test    rbx, rbx
0x140012acf  jz      short loc_140012AE5
0x140012ad1  mov     edx, 6D637742h; Tag
0x140012ad6  mov     rcx, rbx; P
0x140012ad9  call    cs:__imp_ExFreePoolWithTag
0x140012ae0  nop     dword ptr [rax+rax+00h]
0x140012ae5  xor     eax, eax
0x140012ae7  mov     rcx, [rbp+57h+var_38]
0x140012aeb  xor     rcx, rsp; StackCookie
0x140012aee  call    __security_check_cookie
0x140012af3  add     rsp, 0B0h
0x140012afa  pop     r15
0x140012afc  pop     r14
0x140012afe  pop     r12
0x140012b00  pop     rdi
0x140012b01  pop     rsi
0x140012b02  pop     rbx
0x140012b03  pop     rbp
0x140012b04  retn
```
