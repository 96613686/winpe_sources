# LookupDnsZoneMapEntry

- ea: `0x140088dd8`
- end: `0x140089399`
- name: `LookupDnsZoneMapEntry`
- size: `1473`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400898e4`

## callees

- `0x140010f94`
- `0x14003838c`
- `0x140039fa8`
- `0x14004f874`
- `0x140059dc0`
- `0x140088b00`
- `0x140088dd8`
- `0x14008a73c`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x1400890e0`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400890e0`
- `ntoskrnl!ZwOpenKey` at `0x140088e88`
- `ntoskrnl!ZwOpenKey` at `0x1400891cc`
- `ntoskrnl!ZwOpenKey` at `0x140088e88`
- `ntoskrnl!ZwOpenKey` at `0x1400891cc`
- `ntoskrnl!RtlInitUnicodeString` at `0x140088e4d`
- `ntoskrnl!RtlInitUnicodeString` at `0x140089149`
- `ntoskrnl!RtlInitUnicodeString` at `0x140088e4d`
- `ntoskrnl!RtlInitUnicodeString` at `0x140089149`
- `ntoskrnl!ExAllocatePool2` at `0x140088f8c`
- `ntoskrnl!ExAllocatePool2` at `0x140089108`
- `ntoskrnl!ExAllocatePool2` at `0x140088f8c`
- `ntoskrnl!ExAllocatePool2` at `0x140089108`
- `ntoskrnl!ZwClose` at `0x1400891fc`
- `ntoskrnl!ZwClose` at `0x14008936c`
- `ntoskrnl!ZwClose` at `0x1400891fc`
- `ntoskrnl!ZwClose` at `0x14008936c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088fea`
- `ntoskrnl!ExFreePoolWithTag` at `0x140089177`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008924d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140089278`
- `ntoskrnl!ExFreePoolWithTag` at `0x140089356`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088fea`
- `ntoskrnl!ExFreePoolWithTag` at `0x140089177`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008924d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140089278`
- `ntoskrnl!ExFreePoolWithTag` at `0x140089356`
- `ntoskrnl!ZwQueryKey` at `0x140088ebf`
- `ntoskrnl!ZwQueryKey` at `0x140088ebf`
- `ntoskrnl!ZwEnumerateKey` at `0x140088f5a`
- `ntoskrnl!ZwEnumerateKey` at `0x140088fc4`
- `ntoskrnl!ZwEnumerateKey` at `0x140088f5a`
- `ntoskrnl!ZwEnumerateKey` at `0x140088fc4`
- `ntoskrnl!RtlSuffixUnicodeString` at `0x140089096`
- `ntoskrnl!RtlSuffixUnicodeString` at `0x140089161`
- `ntoskrnl!RtlSuffixUnicodeString` at `0x140089096`
- `ntoskrnl!RtlSuffixUnicodeString` at `0x140089161`

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
0x140088dd8  push    rbp
0x140088dda  push    rbx
0x140088ddb  push    rsi
0x140088ddc  push    rdi
0x140088ddd  push    r12
0x140088ddf  push    r14
0x140088de1  push    r15
0x140088de3  lea     rbp, [rsp-40h]
0x140088de8  sub     rsp, 140h
0x140088def  mov     rax, cs:__security_cookie
0x140088df6  xor     rax, rsp
0x140088df9  mov     [rbp+70h+var_40], rax
0x140088dfd  xorps   xmm0, xmm0
0x140088e00  mov     [rsp+170h+KeyHandle], 0
0x140088e09  xorps   xmm1, xmm1
0x140088e0c  mov     [rsp+170h+var_118], 0
0x140088e14  mov     eax, 3
0x140088e19  mov     rbx, rcx
0x140088e1c  lea     rcx, [rbp+70h+DestinationString]; DestinationString
0x140088e20  mov     [rsp+170h+var_140], eax
0x140088e24  movups  xmmword ptr [rsp+170h+String2.Length], xmm0
0x140088e29  mov     [r8], eax
0x140088e2c  mov     r12, r8
0x140088e2f  movups  xmmword ptr [rbp+70h+ObjectAttributes.Length], xmm0
0x140088e33  xor     edi, edi
0x140088e35  movups  xmmword ptr [rbp+70h+ObjectAttributes.ObjectName], xmm0
0x140088e39  movups  xmmword ptr [rbp+70h+ObjectAttributes.SecurityDescriptor], xmm0
0x140088e3d  movups  xmmword ptr [rbp+70h+DestinationString.Length], xmm0
0x140088e41  movups  [rbp+70h+KeyInformation], xmm1
0x140088e45  movups  [rbp+70h+var_60], xmm1
0x140088e49  movups  [rbp+70h+var_50], xmm1
0x140088e4d  call    cs:__imp_RtlInitUnicodeString
0x140088e54  nop     dword ptr [rax+rax+00h]
0x140088e59  lea     rax, [rbp+70h+DestinationString]
0x140088e5d  mov     [rbp+70h+ObjectAttributes.RootDirectory], rdi
0x140088e61  xorps   xmm0, xmm0
0x140088e64  mov     [rbp+70h+ObjectAttributes.ObjectName], rax
0x140088e68  lea     esi, [rdi+30h]
0x140088e6b  mov     [rbp+70h+ObjectAttributes.Attributes], 240h
0x140088e72  lea     r8, [rbp+70h+ObjectAttributes]; ObjectAttributes
0x140088e76  mov     [rbp+70h+ObjectAttributes.Length], esi
0x140088e79  mov     edx, 20019h; DesiredAccess
0x140088e7e  lea     rcx, [rsp+170h+KeyHandle]; KeyHandle
0x140088e83  movdqu  xmmword ptr [rbp+70h+ObjectAttributes.SecurityDescriptor], xmm0
0x140088e88  call    cs:__imp_ZwOpenKey
0x140088e8f  nop     dword ptr [rax+rax+00h]
0x140088e94  mov     r14d, 7A4D6D53h
0x140088e9a  test    eax, eax
0x140088e9c  js      loc_140089344
0x140088ea2  mov     rcx, [rsp+170h+KeyHandle]; KeyHandle
0x140088ea7  lea     rax, [rsp+170h+var_118]
0x140088eac  lea     r15d, [rdi+2]
0x140088eb0  mov     [rsp+170h+ResultLength], rax; ResultLength
0x140088eb5  mov     edx, r15d; KeyInformationClass
0x140088eb8  lea     r8, [rbp+70h+KeyInformation]; KeyInformation
0x140088ebc  mov     r9d, esi; Length
0x140088ebf  call    cs:__imp_ZwQueryKey
0x140088ec6  nop     dword ptr [rax+rax+00h]
0x140088ecb  mov     edx, 80000000h
0x140088ed0  mov     ecx, eax
0x140088ed2  add     eax, edx
0x140088ed4  test    edx, eax
0x140088ed6  jnz     short loc_140088EE4
0x140088ed8  cmp     ecx, 80000005h
0x140088ede  jnz     loc_140089344
0x140088ee4  movups  xmm0, xmmword ptr [rbx]
0x140088ee7  movzx   eax, word ptr [rbx]
0x140088eea  xor     esi, esi
0x140088eec  movdqu  xmmword ptr [rsp+170h+String2.Length], xmm0
0x140088ef2  cmp     ax, r15w
0x140088ef6  jb      short loc_140088F13
0x140088ef8  mov     ecx, eax
0x140088efa  mov     rax, [rbx+8]
0x140088efe  shr     rcx, 1
0x140088f01  cmp     word ptr [rax+rcx*2-2], 2Eh ; '.'
0x140088f07  jnz     short loc_140088F13
0x140088f09  mov     eax, 0FFFEh
0x140088f0e  add     [rsp+170h+String2.Length], ax
0x140088f13  mov     r15d, dword ptr [rbp+70h+var_60+4]
0x140088f17  test    r15d, r15d
0x140088f1a  jz      loc_140089344
0x140088f20  lea     rbx, WPP_GLOBAL_Control
0x140088f27  mov     rcx, [rsp+170h+KeyHandle]; KeyHandle
0x140088f2c  lea     rax, [rsp+170h+Length]
0x140088f31  xorps   xmm0, xmm0
0x140088f34  mov     [rsp+170h+var_148], rax; ResultLength
0x140088f39  dec     r15d
0x140088f3c  mov     dword ptr [rsp+170h+ResultLength], 0; Length
0x140088f44  mov     edx, r15d; Index
0x140088f47  mov     [rsp+170h+Length], 0
0x140088f4f  xor     r9d, r9d; KeyInformation
0x140088f52  xor     r8d, r8d; KeyInformationClass
0x140088f55  movups  xmmword ptr [rsp+170h+var_130.Length], xmm0
0x140088f5a  call    cs:__imp_ZwEnumerateKey
0x140088f61  nop     dword ptr [rax+rax+00h]
0x140088f66  test    eax, eax
0x140088f68  jns     loc_14008933E
0x140088f6e  cmp     eax, 0C0000023h
0x140088f73  jz      short loc_140088F80
0x140088f75  cmp     eax, 80000005h
0x140088f7a  jnz     loc_14008933E
0x140088f80  mov     edx, [rsp+170h+Length]
0x140088f84  mov     r8d, r14d
0x140088f87  mov     ecx, 102h
0x140088f8c  call    cs:__imp_ExAllocatePool2
0x140088f93  nop     dword ptr [rax+rax+00h]
0x140088f98  mov     rdi, rax
0x140088f9b  test    rax, rax
0x140088f9e  jz      loc_140089309
0x140088fa4  mov     ecx, [rsp+170h+Length]
0x140088fa8  lea     rax, [rsp+170h+Length]
0x140088fad  mov     [rsp+170h+var_148], rax; ResultLength
0x140088fb2  mov     r9, rdi; KeyInformation
0x140088fb5  mov     dword ptr [rsp+170h+ResultLength], ecx; Length
0x140088fb9  xor     r8d, r8d; KeyInformationClass
0x140088fbc  mov     rcx, [rsp+170h+KeyHandle]; KeyHandle
0x140088fc1  mov     edx, r15d; Index
0x140088fc4  call    cs:__imp_ZwEnumerateKey
0x140088fcb  nop     dword ptr [rax+rax+00h]
0x140088fd0  test    eax, eax
0x140088fd2  js      loc_140089340
0x140088fd8  mov     r10d, 2
0x140088fde  cmp     [rdi+0Ch], r10d
0x140088fe2  jnb     short loc_140088FFB
0x140088fe4  mov     edx, r14d; Tag
0x140088fe7  mov     rcx, rdi; P
0x140088fea  call    cs:__imp_ExFreePoolWithTag
0x140088ff1  nop     dword ptr [rax+rax+00h]
0x140088ff6  jmp     loc_140089260
0x140088ffb  lea     r8, [rdi+10h]
0x140088fff  mov     [rsp+170h+var_130.Buffer], r8
0x140089004  movzx   edx, word ptr [rdi+0Ch]
0x140089008  mov     [rsp+170h+var_130.Length], dx
0x14008900d  movzx   r9d, word ptr [rdi+0Ch]
0x140089012  mov     [rsp+170h+var_130.MaximumLength], r9w
0x140089018  mov     rcx, cs:WPP_GLOBAL_Control
0x14008901f  cmp     rcx, rbx
0x140089022  jz      short loc_140089062
0x140089024  mov     eax, [rcx+2Ch]
0x140089027  test    r10b, al
0x14008902a  jz      short loc_140089062
0x14008902c  cmp     [rcx+29h], r10b
0x140089030  jb      short loc_140089062
0x140089032  mov     rcx, [rcx+18h]
0x140089036  lea     r9, [rsp+170h+var_130]
0x14008903b  mov     edx, 22h ; '"'
0x140089040  lea     r8, WPP_318b97441ad5316ed29d4021e7d37a6e_Traceguids
0x140089047  call    WPP_SF_Z
0x14008904c  mov     r8, [rsp+170h+var_130.Buffer]
0x140089051  mov     r10d, 2
0x140089057  movzx   r9d, [rsp+170h+var_130.MaximumLength]
0x14008905d  movzx   edx, [rsp+170h+var_130.Length]
0x140089062  cmp     word ptr [r8], 2Ah ; '*'
0x140089067  jnz     short loc_1400890D3
0x140089069  sub     dx, r10w
0x14008906d  mov     dword ptr [rsp+170h+String1+4], 0
0x140089075  lea     rax, [r8+2]
0x140089079  mov     [rsp+170h+String1.Length], dx
0x14008907e  lea     rdx, [rsp+170h+String2]; String2
0x140089083  mov     [rsp+170h+String1.Buffer], rax
0x140089088  mov     r8b, 1; CaseInSensitive
0x14008908b  mov     [rsp+170h+String1.MaximumLength], r9w
0x140089091  lea     rcx, [rsp+170h+String1]; String1
0x140089096  call    cs:__imp_RtlSuffixUnicodeString
0x14008909d  nop     dword ptr [rax+rax+00h]
0x1400890a2  test    al, al
0x1400890a4  jz      loc_140088FE4
0x1400890aa  mov     rcx, [rsp+170h+KeyHandle]
0x1400890af  lea     r8, [rsp+170h+var_140]
0x1400890b4  lea     rdx, [rsp+170h+var_130]
0x1400890b9  call    RegQueryZoneFromKey
0x1400890be  test    eax, eax
0x1400890c0  js      loc_140088FE4
0x1400890c6  mov     eax, [rsp+170h+var_140]
0x1400890ca  mov     [r12], eax
0x1400890ce  jmp     loc_14008934E
0x1400890d3  mov     r8b, 1; CaseInSensitive
0x1400890d6  lea     rdx, [rsp+170h+var_130]; String2
0x1400890db  lea     rcx, [rsp+170h+String2]; String1
0x1400890e0  call    cs:__imp_RtlCompareUnicodeString
0x1400890e7  nop     dword ptr [rax+rax+00h]
0x1400890ec  test    eax, eax
0x1400890ee  jz      short loc_1400890AA
0x1400890f0  movzx   ebx, [rsp+170h+var_130.Length]
0x1400890f5  xorps   xmm0, xmm0
0x1400890f8  mov     r8d, r14d
0x1400890fb  mov     ecx, 102h
0x140089100  movups  xmmword ptr [rbp+70h+var_E0.Length], xmm0
0x140089104  lea     rdx, [rbx+6]
0x140089108  call    cs:__imp_ExAllocatePool2
0x14008910f  nop     dword ptr [rax+rax+00h]
0x140089114  mov     r14, rax
0x140089117  test    rax, rax
0x14008911a  jz      loc_1400892CD
0x140089120  lea     r9, [rsp+170h+var_130]
0x140089125  mov     rcx, rax; pszDest
0x140089128  lea     r8, aWz; ".%wZ"
0x14008912f  lea     rdx, [rbx+6]; cbDest
0x140089133  call    RtlStringCbPrintfW
0x140089138  mov     esi, eax
0x14008913a  test    eax, eax
0x14008913c  js      loc_140089270
0x140089142  mov     rdx, r14; SourceString
0x140089145  lea     rcx, [rbp+70h+var_E0]; DestinationString
0x140089149  call    cs:__imp_RtlInitUnicodeString
0x140089150  nop     dword ptr [rax+rax+00h]
0x140089155  mov     r8b, 1; CaseInSensitive
0x140089158  lea     rdx, [rsp+170h+String2]; String2
0x14008915d  lea     rcx, [rbp+70h+var_E0]; String1
0x140089161  call    cs:__imp_RtlSuffixUnicodeString
0x140089168  nop     dword ptr [rax+rax+00h]
0x14008916d  mov     edx, 7A4D6D53h; Tag
0x140089172  mov     rcx, r14; P
0x140089175  mov     bl, al
0x140089177  call    cs:__imp_ExFreePoolWithTag
0x14008917e  nop     dword ptr [rax+rax+00h]
0x140089183  test    bl, bl
0x140089185  jz      loc_140089241
0x14008918b  mov     rax, [rsp+170h+KeyHandle]
0x140089190  lea     r8, [rbp+70h+var_A0]; ObjectAttributes
0x140089194  mov     [rbp+70h+var_A0.RootDirectory], rax
0x140089198  lea     rcx, [rsp+170h+Handle]; KeyHandle
0x14008919d  lea     rax, [rsp+170h+var_130]
0x1400891a2  mov     [rsp+170h+Handle], 0
0x1400891ab  xorps   xmm0, xmm0
0x1400891ae  mov     [rbp+70h+var_A0.ObjectName], rax
0x1400891b2  mov     edx, 20019h; DesiredAccess
0x1400891b7  mov     qword ptr [rbp+70h+var_A0.Length], 30h ; '0'
0x1400891bf  mov     qword ptr [rbp+70h+var_A0.Attributes], 240h
0x1400891c7  movdqu  xmmword ptr [rbp+70h+var_A0.SecurityDescriptor], xmm0
0x1400891cc  call    cs:__imp_ZwOpenKey
0x1400891d3  nop     dword ptr [rax+rax+00h]
0x1400891d8  test    eax, eax
0x1400891da  js      short loc_140089241
0x1400891dc  mov     rdx, [rsp+170h+Handle]; KeyHandle
0x1400891e1  lea     r9, [rsp+170h+var_140]
0x1400891e6  lea     r8, [rsp+170h+var_130]
0x1400891eb  lea     rcx, [rsp+170h+String2]; String1
0x1400891f0  call    LookupDnsSiteEntry
0x1400891f5  mov     rcx, [rsp+170h+Handle]; Handle
0x1400891fa  mov     esi, eax
0x1400891fc  call    cs:__imp_ZwClose
0x140089203  nop     dword ptr [rax+rax+00h]
0x140089208  mov     [rsp+170h+Handle], 0
0x140089211  test    esi, esi
0x140089213  jns     loc_1400890C6
0x140089219  cmp     esi, 0C0000034h
0x14008921f  jnz     loc_14008934E
0x140089225  mov     rcx, [rsp+170h+KeyHandle]
0x14008922a  lea     r8, [rsp+170h+var_140]
0x14008922f  lea     rdx, [rsp+170h+var_130]
0x140089234  call    RegQueryZoneFromKey
0x140089239  test    eax, eax
0x14008923b  jns     loc_1400890C6
0x140089241  mov     r14d, 7A4D6D53h
0x140089247  mov     rcx, rdi; P
0x14008924a  mov     edx, r14d; Tag
0x14008924d  call    cs:__imp_ExFreePoolWithTag
0x140089254  nop     dword ptr [rax+rax+00h]
0x140089259  lea     rbx, WPP_GLOBAL_Control
0x140089260  xor     edi, edi
0x140089262  test    r15d, r15d
0x140089265  jnz     loc_140088F27
0x14008926b  jmp     loc_140089340
0x140089270  mov     edx, 7A4D6D53h; Tag
0x140089275  mov     rcx, r14; P
0x140089278  call    cs:__imp_ExFreePoolWithTag
0x14008927f  nop     dword ptr [rax+rax+00h]
0x140089284  mov     rcx, cs:WPP_GLOBAL_Control
0x14008928b  lea     rax, WPP_GLOBAL_Control
0x140089292  cmp     rcx, rax
0x140089295  jz      loc_14008934E
0x14008929b  mov     eax, [rcx+2Ch]
0x14008929e  test    al, 1
0x1400892a0  jz      loc_14008934E
0x1400892a6  cmp     byte ptr [rcx+29h], 1
0x1400892aa  jb      loc_14008934E
0x1400892b0  mov     rcx, [rcx+18h]
0x1400892b4  lea     r8, WPP_318b97441ad5316ed29d4021e7d37a6e_Traceguids
0x1400892bb  mov     edx, 24h ; '$'
0x1400892c0  mov     r9d, esi
0x1400892c3  call    WPP_SF_d
0x1400892c8  jmp     loc_14008934E
0x1400892cd  mov     esi, 0C000009Ah
0x1400892d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400892d9  lea     rax, WPP_GLOBAL_Control
0x1400892e0  cmp     rcx, rax
0x1400892e3  jz      short loc_14008934E
0x1400892e5  mov     eax, [rcx+2Ch]
0x1400892e8  test    al, 1
0x1400892ea  jz      short loc_14008934E
0x1400892ec  cmp     byte ptr [rcx+29h], 1
0x1400892f0  jb      short loc_14008934E
0x1400892f2  mov     rcx, [rcx+18h]
0x1400892f6  lea     r8, WPP_318b97441ad5316ed29d4021e7d37a6e_Traceguids
0x1400892fd  mov     edx, 23h ; '#'
0x140089302  call    WPP_SF_
0x140089307  jmp     short loc_14008934E
0x140089309  mov     esi, 0C000009Ah
0x14008930e  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
