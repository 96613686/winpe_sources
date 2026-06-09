# LookupDnsZoneMapEntry

- ea: `0x140088e28`
- end: `0x1400893e9`
- name: `LookupDnsZoneMapEntry`
- size: `1473`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140089934`

## callees

- `0x140010f94`
- `0x14003838c`
- `0x140039fa8`
- `0x14004f874`
- `0x140059dc0`
- `0x140088b50`
- `0x140088e28`
- `0x14008a78c`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x140089130`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140089130`
- `ntoskrnl!ZwOpenKey` at `0x140088ed8`
- `ntoskrnl!ZwOpenKey` at `0x14008921c`
- `ntoskrnl!ZwOpenKey` at `0x140088ed8`
- `ntoskrnl!ZwOpenKey` at `0x14008921c`
- `ntoskrnl!RtlInitUnicodeString` at `0x140088e9d`
- `ntoskrnl!RtlInitUnicodeString` at `0x140089199`
- `ntoskrnl!RtlInitUnicodeString` at `0x140088e9d`
- `ntoskrnl!RtlInitUnicodeString` at `0x140089199`
- `ntoskrnl!ExAllocatePool2` at `0x140088fdc`
- `ntoskrnl!ExAllocatePool2` at `0x140089158`
- `ntoskrnl!ExAllocatePool2` at `0x140088fdc`
- `ntoskrnl!ExAllocatePool2` at `0x140089158`
- `ntoskrnl!ZwClose` at `0x14008924c`
- `ntoskrnl!ZwClose` at `0x1400893bc`
- `ntoskrnl!ZwClose` at `0x14008924c`
- `ntoskrnl!ZwClose` at `0x1400893bc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008903a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400891c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008929d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400892c8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400893a6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008903a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400891c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008929d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400892c8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400893a6`
- `ntoskrnl!ZwQueryKey` at `0x140088f0f`
- `ntoskrnl!ZwQueryKey` at `0x140088f0f`
- `ntoskrnl!ZwEnumerateKey` at `0x140088faa`
- `ntoskrnl!ZwEnumerateKey` at `0x140089014`
- `ntoskrnl!ZwEnumerateKey` at `0x140088faa`
- `ntoskrnl!ZwEnumerateKey` at `0x140089014`
- `ntoskrnl!RtlSuffixUnicodeString` at `0x1400890e6`
- `ntoskrnl!RtlSuffixUnicodeString` at `0x1400891b1`
- `ntoskrnl!RtlSuffixUnicodeString` at `0x1400890e6`
- `ntoskrnl!RtlSuffixUnicodeString` at `0x1400891b1`

## pseudocode

```c
__int64 __fastcall LookupDnsZoneMapEntry(UNICODE_STRING *a1, const WCHAR *a2, int *a3)
{
  __int64 Pool2; // rdi
  NTSTATUS v6; // ecx
  NTSTATUS v7; // esi
  ULONG v8; // r15d
  NTSTATUS v9; // eax
  wchar_t *Buffer; // r8
  unsigned __int16 v11; // dx
  unsigned __int16 MaximumLength; // r9
  __int64 v13; // rbx
  wchar_t *v14; // rax
  wchar_t *v15; // r14
  BOOLEAN v16; // bl
  int v18; // [rsp+30h] [rbp-D0h] BYREF
  ULONG Length; // [rsp+34h] [rbp-CCh] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-C8h] BYREF
  UNICODE_STRING v21; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE Handle; // [rsp+50h] [rbp-B0h] BYREF
  ULONG ResultLength; // [rsp+58h] [rbp-A8h] BYREF
  UNICODE_STRING String2; // [rsp+60h] [rbp-A0h] BYREF
  UNICODE_STRING String1; // [rsp+70h] [rbp-90h] BYREF
  UNICODE_STRING DestinationString; // [rsp+80h] [rbp-80h] BYREF
  UNICODE_STRING v27; // [rsp+90h] [rbp-70h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp-60h] BYREF
  struct _OBJECT_ATTRIBUTES v29; // [rsp+D0h] [rbp-30h] BYREF
  __int128 KeyInformation; // [rsp+100h] [rbp+0h] BYREF
  __int128 v31; // [rsp+110h] [rbp+10h]
  __int128 v32; // [rsp+120h] [rbp+20h]

  KeyHandle = 0;
  ResultLength = 0;
  v18 = 3;
  String2 = 0;
  *a3 = 3;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  Pool2 = 0;
  DestinationString = 0;
  KeyInformation = 0;
  v31 = 0;
  v32 = 0;
  RtlInitUnicodeString(&DestinationString, a2);
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.Length = 48;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) < 0 )
    goto LABEL_47;
  v6 = ZwQueryKey(KeyHandle, KeyFullInformation, &KeyInformation, 0x30u, &ResultLength);
  if ( (int)(v6 + 0x80000000) >= 0 && v6 != -2147483643 )
    goto LABEL_47;
  v7 = 0;
  String2 = *a1;
  if ( String2.Length >= 2u && a1->Buffer[((unsigned __int64)String2.Length >> 1) - 1] == 46 )
    String2.Length -= 2;
  v8 = DWORD1(v31);
  if ( !DWORD1(v31) )
    goto LABEL_47;
  while ( 1 )
  {
    --v8;
    Length = 0;
    v21 = 0;
    v9 = ZwEnumerateKey(KeyHandle, v8, KeyBasicInformation, 0, 0, &Length);
    if ( v9 >= 0 || v9 != -1073741789 && v9 != -2147483643 )
      break;
    Pool2 = ExAllocatePool2(258, Length, 2051894611);
    if ( !Pool2 )
    {
      v7 = -1073741670;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_318b97441ad5316ed29d4021e7d37a6e_Traceguids);
      }
      goto LABEL_50;
    }
    if ( ZwEnumerateKey(KeyHandle, v8, KeyBasicInformation, (PVOID)Pool2, Length, &Length) < 0 )
      goto LABEL_46;
    if ( *(_DWORD *)(Pool2 + 12) < 2u )
      goto LABEL_31;
    Buffer = (wchar_t *)(Pool2 + 16);
    v21.Buffer = (wchar_t *)(Pool2 + 16);
    v11 = *(_WORD *)(Pool2 + 12);
    v21.Length = v11;
    MaximumLength = *(_WORD *)(Pool2 + 12);
    v21.MaximumLength = MaximumLength;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_318b97441ad5316ed29d4021e7d37a6e_Traceguids, &v21);
      Buffer = v21.Buffer;
      MaximumLength = v21.MaximumLength;
      v11 = v21.Length;
    }
    if ( *Buffer != 42 )
    {
      if ( RtlCompareUnicodeString(&String2, &v21, 1u) )
      {
        v13 = v21.Length;
        v27 = 0;
        v14 = (wchar_t *)ExAllocatePool2(258, v21.Length + 6LL, 2051894611);
        v15 = v14;
        if ( !v14 )
        {
          v7 = -1073741670;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_318b97441ad5316ed29d4021e7d37a6e_Traceguids);
          }
          goto LABEL_49;
        }
        v7 = RtlStringCbPrintfW(v14, v13 + 6, L".%wZ", &v21);
        if ( v7 < 0 )
        {
          ExFreePoolWithTag(v15, 0x7A4D6D53u);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              36,
              WPP_318b97441ad5316ed29d4021e7d37a6e_Traceguids,
              (unsigned int)v7);
          }
          goto LABEL_49;
        }
        RtlInitUnicodeString(&v27, v15);
        v16 = RtlSuffixUnicodeString(&v27, &String2, 1u);
        ExFreePoolWithTag(v15, 0x7A4D6D53u);
        if ( v16 )
        {
          v29.RootDirectory = KeyHandle;
          Handle = 0;
          v29.ObjectName = &v21;
          *(_QWORD *)&v29.Length = 48;
          *(_QWORD *)&v29.Attributes = 576;
          *(_OWORD *)&v29.SecurityDescriptor = 0;
          if ( ZwOpenKey(&Handle, 0x20019u, &v29) >= 0 )
          {
            v7 = LookupDnsSiteEntry(&String2, Handle);
            ZwClose(Handle);
            Handle = 0;
            if ( v7 >= 0 )
              goto LABEL_22;
            if ( v7 != -1073741772 )
              goto LABEL_49;
            if ( (int)RegQueryZoneFromKey(KeyHandle, &v21, &v18) >= 0 )
            {
LABEL_22:
              *a3 = v18;
              goto LABEL_49;
            }
          }
        }
        goto LABEL_31;
      }
LABEL_21:
      if ( (int)RegQueryZoneFromKey(KeyHandle, &v21, &v18) >= 0 )
        goto LABEL_22;
      goto LABEL_31;
    }
    *(_DWORD *)(&String1.MaximumLength + 1) = 0;
    String1.Length = v11 - 2;
    String1.Buffer = Buffer + 1;
    String1.MaximumLength = MaximumLength;
    if ( RtlSuffixUnicodeString(&String1, &String2, 1u) )
      goto LABEL_21;
LABEL_31:
    ExFreePoolWithTag((PVOID)Pool2, 0x7A4D6D53u);
    Pool2 = 0;
    if ( !v8 )
      goto LABEL_46;
  }
  Pool2 = 0;
LABEL_46:
  if ( v7 < 0 )
    goto LABEL_48;
LABEL_47:
  v7 = -1073741772;
LABEL_48:
  if ( Pool2 )
LABEL_49:
    ExFreePoolWithTag((PVOID)Pool2, 0x7A4D6D53u);
LABEL_50:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140088e28  push    rbp
0x140088e2a  push    rbx
0x140088e2b  push    rsi
0x140088e2c  push    rdi
0x140088e2d  push    r12
0x140088e2f  push    r14
0x140088e31  push    r15
0x140088e33  lea     rbp, [rsp-40h]
0x140088e38  sub     rsp, 140h
0x140088e3f  mov     rax, cs:__security_cookie
0x140088e46  xor     rax, rsp
0x140088e49  mov     [rbp+70h+var_40], rax
0x140088e4d  xorps   xmm0, xmm0
0x140088e50  mov     [rsp+170h+KeyHandle], 0
0x140088e59  xorps   xmm1, xmm1
0x140088e5c  mov     [rsp+170h+var_118], 0
0x140088e64  mov     eax, 3
0x140088e69  mov     rbx, rcx
0x140088e6c  lea     rcx, [rbp+70h+DestinationString]; DestinationString
0x140088e70  mov     [rsp+170h+var_140], eax
0x140088e74  movups  xmmword ptr [rsp+170h+String2.Length], xmm0
0x140088e79  mov     [r8], eax
0x140088e7c  mov     r12, r8
0x140088e7f  movups  xmmword ptr [rbp+70h+ObjectAttributes.Length], xmm0
0x140088e83  xor     edi, edi
0x140088e85  movups  xmmword ptr [rbp+70h+ObjectAttributes.ObjectName], xmm0
0x140088e89  movups  xmmword ptr [rbp+70h+ObjectAttributes.SecurityDescriptor], xmm0
0x140088e8d  movups  xmmword ptr [rbp+70h+DestinationString.Length], xmm0
0x140088e91  movups  [rbp+70h+KeyInformation], xmm1
0x140088e95  movups  [rbp+70h+var_60], xmm1
0x140088e99  movups  [rbp+70h+var_50], xmm1
0x140088e9d  call    cs:__imp_RtlInitUnicodeString
0x140088ea4  nop     dword ptr [rax+rax+00h]
0x140088ea9  lea     rax, [rbp+70h+DestinationString]
0x140088ead  mov     [rbp+70h+ObjectAttributes.RootDirectory], rdi
0x140088eb1  xorps   xmm0, xmm0
0x140088eb4  mov     [rbp+70h+ObjectAttributes.ObjectName], rax
0x140088eb8  lea     esi, [rdi+30h]
0x140088ebb  mov     [rbp+70h+ObjectAttributes.Attributes], 240h
0x140088ec2  lea     r8, [rbp+70h+ObjectAttributes]; ObjectAttributes
0x140088ec6  mov     [rbp+70h+ObjectAttributes.Length], esi
0x140088ec9  mov     edx, 20019h; DesiredAccess
0x140088ece  lea     rcx, [rsp+170h+KeyHandle]; KeyHandle
0x140088ed3  movdqu  xmmword ptr [rbp+70h+ObjectAttributes.SecurityDescriptor], xmm0
0x140088ed8  call    cs:__imp_ZwOpenKey
0x140088edf  nop     dword ptr [rax+rax+00h]
0x140088ee4  mov     r14d, 7A4D6D53h
0x140088eea  test    eax, eax
0x140088eec  js      loc_140089394
0x140088ef2  mov     rcx, [rsp+170h+KeyHandle]; KeyHandle
0x140088ef7  lea     rax, [rsp+170h+var_118]
0x140088efc  lea     r15d, [rdi+2]
0x140088f00  mov     [rsp+170h+ResultLength], rax; ResultLength
0x140088f05  mov     edx, r15d; KeyInformationClass
0x140088f08  lea     r8, [rbp+70h+KeyInformation]; KeyInformation
0x140088f0c  mov     r9d, esi; Length
0x140088f0f  call    cs:__imp_ZwQueryKey
0x140088f16  nop     dword ptr [rax+rax+00h]
0x140088f1b  mov     edx, 80000000h
0x140088f20  mov     ecx, eax
0x140088f22  add     eax, edx
0x140088f24  test    edx, eax
0x140088f26  jnz     short loc_140088F34
0x140088f28  cmp     ecx, 80000005h
0x140088f2e  jnz     loc_140089394
0x140088f34  movups  xmm0, xmmword ptr [rbx]
0x140088f37  movzx   eax, word ptr [rbx]
0x140088f3a  xor     esi, esi
0x140088f3c  movdqu  xmmword ptr [rsp+170h+String2.Length], xmm0
0x140088f42  cmp     ax, r15w
0x140088f46  jb      short loc_140088F63
0x140088f48  mov     ecx, eax
0x140088f4a  mov     rax, [rbx+8]
0x140088f4e  shr     rcx, 1
0x140088f51  cmp     word ptr [rax+rcx*2-2], 2Eh ; '.'
0x140088f57  jnz     short loc_140088F63
0x140088f59  mov     eax, 0FFFEh
0x140088f5e  add     [rsp+170h+String2.Length], ax
0x140088f63  mov     r15d, dword ptr [rbp+70h+var_60+4]
0x140088f67  test    r15d, r15d
0x140088f6a  jz      loc_140089394
0x140088f70  lea     rbx, WPP_GLOBAL_Control
0x140088f77  mov     rcx, [rsp+170h+KeyHandle]; KeyHandle
0x140088f7c  lea     rax, [rsp+170h+Length]
0x140088f81  xorps   xmm0, xmm0
0x140088f84  mov     [rsp+170h+var_148], rax; ResultLength
0x140088f89  dec     r15d
0x140088f8c  mov     dword ptr [rsp+170h+ResultLength], 0; Length
0x140088f94  mov     edx, r15d; Index
0x140088f97  mov     [rsp+170h+Length], 0
0x140088f9f  xor     r9d, r9d; KeyInformation
0x140088fa2  xor     r8d, r8d; KeyInformationClass
0x140088fa5  movups  xmmword ptr [rsp+170h+var_130.Length], xmm0
0x140088faa  call    cs:__imp_ZwEnumerateKey
0x140088fb1  nop     dword ptr [rax+rax+00h]
0x140088fb6  test    eax, eax
0x140088fb8  jns     loc_14008938E
0x140088fbe  cmp     eax, 0C0000023h
0x140088fc3  jz      short loc_140088FD0
0x140088fc5  cmp     eax, 80000005h
0x140088fca  jnz     loc_14008938E
0x140088fd0  mov     edx, [rsp+170h+Length]
0x140088fd4  mov     r8d, r14d
0x140088fd7  mov     ecx, 102h
0x140088fdc  call    cs:__imp_ExAllocatePool2
0x140088fe3  nop     dword ptr [rax+rax+00h]
0x140088fe8  mov     rdi, rax
0x140088feb  test    rax, rax
0x140088fee  jz      loc_140089359
0x140088ff4  mov     ecx, [rsp+170h+Length]
0x140088ff8  lea     rax, [rsp+170h+Length]
0x140088ffd  mov     [rsp+170h+var_148], rax; ResultLength
0x140089002  mov     r9, rdi; KeyInformation
0x140089005  mov     dword ptr [rsp+170h+ResultLength], ecx; Length
0x140089009  xor     r8d, r8d; KeyInformationClass
0x14008900c  mov     rcx, [rsp+170h+KeyHandle]; KeyHandle
0x140089011  mov     edx, r15d; Index
0x140089014  call    cs:__imp_ZwEnumerateKey
0x14008901b  nop     dword ptr [rax+rax+00h]
0x140089020  test    eax, eax
0x140089022  js      loc_140089390
0x140089028  mov     r10d, 2
0x14008902e  cmp     [rdi+0Ch], r10d
0x140089032  jnb     short loc_14008904B
0x140089034  mov     edx, r14d; Tag
0x140089037  mov     rcx, rdi; P
0x14008903a  call    cs:__imp_ExFreePoolWithTag
0x140089041  nop     dword ptr [rax+rax+00h]
0x140089046  jmp     loc_1400892B0
0x14008904b  lea     r8, [rdi+10h]
0x14008904f  mov     [rsp+170h+var_130.Buffer], r8
0x140089054  movzx   edx, word ptr [rdi+0Ch]
0x140089058  mov     [rsp+170h+var_130.Length], dx
0x14008905d  movzx   r9d, word ptr [rdi+0Ch]
0x140089062  mov     [rsp+170h+var_130.MaximumLength], r9w
0x140089068  mov     rcx, cs:WPP_GLOBAL_Control
0x14008906f  cmp     rcx, rbx
0x140089072  jz      short loc_1400890B2
0x140089074  mov     eax, [rcx+2Ch]
0x140089077  test    r10b, al
0x14008907a  jz      short loc_1400890B2
0x14008907c  cmp     [rcx+29h], r10b
0x140089080  jb      short loc_1400890B2
0x140089082  mov     rcx, [rcx+18h]
0x140089086  lea     r9, [rsp+170h+var_130]
0x14008908b  mov     edx, 22h ; '"'
0x140089090  lea     r8, WPP_318b97441ad5316ed29d4021e7d37a6e_Traceguids
0x140089097  call    WPP_SF_Z
0x14008909c  mov     r8, [rsp+170h+var_130.Buffer]
0x1400890a1  mov     r10d, 2
0x1400890a7  movzx   r9d, [rsp+170h+var_130.MaximumLength]
0x1400890ad  movzx   edx, [rsp+170h+var_130.Length]
0x1400890b2  cmp     word ptr [r8], 2Ah ; '*'
0x1400890b7  jnz     short loc_140089123
0x1400890b9  sub     dx, r10w
0x1400890bd  mov     dword ptr [rsp+170h+String1+4], 0
0x1400890c5  lea     rax, [r8+2]
0x1400890c9  mov     [rsp+170h+String1.Length], dx
0x1400890ce  lea     rdx, [rsp+170h+String2]; String2
0x1400890d3  mov     [rsp+170h+String1.Buffer], rax
0x1400890d8  mov     r8b, 1; CaseInSensitive
0x1400890db  mov     [rsp+170h+String1.MaximumLength], r9w
0x1400890e1  lea     rcx, [rsp+170h+String1]; String1
0x1400890e6  call    cs:__imp_RtlSuffixUnicodeString
0x1400890ed  nop     dword ptr [rax+rax+00h]
0x1400890f2  test    al, al
0x1400890f4  jz      loc_140089034
0x1400890fa  mov     rcx, [rsp+170h+KeyHandle]
0x1400890ff  lea     r8, [rsp+170h+var_140]
0x140089104  lea     rdx, [rsp+170h+var_130]
0x140089109  call    RegQueryZoneFromKey
0x14008910e  test    eax, eax
0x140089110  js      loc_140089034
0x140089116  mov     eax, [rsp+170h+var_140]
0x14008911a  mov     [r12], eax
0x14008911e  jmp     loc_14008939E
0x140089123  mov     r8b, 1; CaseInSensitive
0x140089126  lea     rdx, [rsp+170h+var_130]; String2
0x14008912b  lea     rcx, [rsp+170h+String2]; String1
0x140089130  call    cs:__imp_RtlCompareUnicodeString
0x140089137  nop     dword ptr [rax+rax+00h]
0x14008913c  test    eax, eax
0x14008913e  jz      short loc_1400890FA
0x140089140  movzx   ebx, [rsp+170h+var_130.Length]
0x140089145  xorps   xmm0, xmm0
0x140089148  mov     r8d, r14d
0x14008914b  mov     ecx, 102h
0x140089150  movups  xmmword ptr [rbp+70h+var_E0.Length], xmm0
0x140089154  lea     rdx, [rbx+6]
0x140089158  call    cs:__imp_ExAllocatePool2
0x14008915f  nop     dword ptr [rax+rax+00h]
0x140089164  mov     r14, rax
0x140089167  test    rax, rax
0x14008916a  jz      loc_14008931D
0x140089170  lea     r9, [rsp+170h+var_130]
0x140089175  mov     rcx, rax; pszDest
0x140089178  lea     r8, aWz; ".%wZ"
0x14008917f  lea     rdx, [rbx+6]; cbDest
0x140089183  call    RtlStringCbPrintfW
0x140089188  mov     esi, eax
0x14008918a  test    eax, eax
0x14008918c  js      loc_1400892C0
0x140089192  mov     rdx, r14; SourceString
0x140089195  lea     rcx, [rbp+70h+var_E0]; DestinationString
0x140089199  call    cs:__imp_RtlInitUnicodeString
0x1400891a0  nop     dword ptr [rax+rax+00h]
0x1400891a5  mov     r8b, 1; CaseInSensitive
0x1400891a8  lea     rdx, [rsp+170h+String2]; String2
0x1400891ad  lea     rcx, [rbp+70h+var_E0]; String1
0x1400891b1  call    cs:__imp_RtlSuffixUnicodeString
0x1400891b8  nop     dword ptr [rax+rax+00h]
0x1400891bd  mov     edx, 7A4D6D53h; Tag
0x1400891c2  mov     rcx, r14; P
0x1400891c5  mov     bl, al
0x1400891c7  call    cs:__imp_ExFreePoolWithTag
0x1400891ce  nop     dword ptr [rax+rax+00h]
0x1400891d3  test    bl, bl
0x1400891d5  jz      loc_140089291
0x1400891db  mov     rax, [rsp+170h+KeyHandle]
0x1400891e0  lea     r8, [rbp+70h+var_A0]; ObjectAttributes
0x1400891e4  mov     [rbp+70h+var_A0.RootDirectory], rax
0x1400891e8  lea     rcx, [rsp+170h+Handle]; KeyHandle
0x1400891ed  lea     rax, [rsp+170h+var_130]
0x1400891f2  mov     [rsp+170h+Handle], 0
0x1400891fb  xorps   xmm0, xmm0
0x1400891fe  mov     [rbp+70h+var_A0.ObjectName], rax
0x140089202  mov     edx, 20019h; DesiredAccess
0x140089207  mov     qword ptr [rbp+70h+var_A0.Length], 30h ; '0'
0x14008920f  mov     qword ptr [rbp+70h+var_A0.Attributes], 240h
0x140089217  movdqu  xmmword ptr [rbp+70h+var_A0.SecurityDescriptor], xmm0
0x14008921c  call    cs:__imp_ZwOpenKey
0x140089223  nop     dword ptr [rax+rax+00h]
0x140089228  test    eax, eax
0x14008922a  js      short loc_140089291
0x14008922c  mov     rdx, [rsp+170h+Handle]; KeyHandle
0x140089231  lea     r9, [rsp+170h+var_140]
0x140089236  lea     r8, [rsp+170h+var_130]
0x14008923b  lea     rcx, [rsp+170h+String2]; String1
0x140089240  call    LookupDnsSiteEntry
0x140089245  mov     rcx, [rsp+170h+Handle]; Handle
0x14008924a  mov     esi, eax
0x14008924c  call    cs:__imp_ZwClose
0x140089253  nop     dword ptr [rax+rax+00h]
0x140089258  mov     [rsp+170h+Handle], 0
0x140089261  test    esi, esi
0x140089263  jns     loc_140089116
0x140089269  cmp     esi, 0C0000034h
0x14008926f  jnz     loc_14008939E
0x140089275  mov     rcx, [rsp+170h+KeyHandle]
0x14008927a  lea     r8, [rsp+170h+var_140]
0x14008927f  lea     rdx, [rsp+170h+var_130]
0x140089284  call    RegQueryZoneFromKey
0x140089289  test    eax, eax
0x14008928b  jns     loc_140089116
0x140089291  mov     r14d, 7A4D6D53h
0x140089297  mov     rcx, rdi; P
0x14008929a  mov     edx, r14d; Tag
0x14008929d  call    cs:__imp_ExFreePoolWithTag
0x1400892a4  nop     dword ptr [rax+rax+00h]
0x1400892a9  lea     rbx, WPP_GLOBAL_Control
0x1400892b0  xor     edi, edi
0x1400892b2  test    r15d, r15d
0x1400892b5  jnz     loc_140088F77
0x1400892bb  jmp     loc_140089390
0x1400892c0  mov     edx, 7A4D6D53h; Tag
0x1400892c5  mov     rcx, r14; P
0x1400892c8  call    cs:__imp_ExFreePoolWithTag
0x1400892cf  nop     dword ptr [rax+rax+00h]
0x1400892d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400892db  lea     rax, WPP_GLOBAL_Control
0x1400892e2  cmp     rcx, rax
0x1400892e5  jz      loc_14008939E
0x1400892eb  mov     eax, [rcx+2Ch]
0x1400892ee  test    al, 1
0x1400892f0  jz      loc_14008939E
0x1400892f6  cmp     byte ptr [rcx+29h], 1
0x1400892fa  jb      loc_14008939E
0x140089300  mov     rcx, [rcx+18h]
0x140089304  lea     r8, WPP_318b97441ad5316ed29d4021e7d37a6e_Traceguids
0x14008930b  mov     edx, 24h ; '$'
0x140089310  mov     r9d, esi
0x140089313  call    WPP_SF_d
0x140089318  jmp     loc_14008939E
0x14008931d  mov     esi, 0C000009Ah
0x140089322  mov     rcx, cs:WPP_GLOBAL_Control
0x140089329  lea     rax, WPP_GLOBAL_Control
0x140089330  cmp     rcx, rax
0x140089333  jz      short loc_14008939E
0x140089335  mov     eax, [rcx+2Ch]
0x140089338  test    al, 1
0x14008933a  jz      short loc_14008939E
0x14008933c  cmp     byte ptr [rcx+29h], 1
0x140089340  jb      short loc_14008939E
0x140089342  mov     rcx, [rcx+18h]
0x140089346  lea     r8, WPP_318b97441ad5316ed29d4021e7d37a6e_Traceguids
0x14008934d  mov     edx, 23h ; '#'
0x140089352  call    WPP_SF_
0x140089357  jmp     short loc_14008939E
0x140089359  mov     esi, 0C000009Ah
0x14008935e  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
