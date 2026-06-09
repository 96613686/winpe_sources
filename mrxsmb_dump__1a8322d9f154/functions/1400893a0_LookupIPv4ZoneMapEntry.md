# LookupIPv4ZoneMapEntry

- ea: `0x1400893a0`
- end: `0x1400896f3`
- name: `LookupIPv4ZoneMapEntry`
- size: `851`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400898e4`

## callees

- `0x14003838c`
- `0x14005a200`
- `0x140088538`
- `0x140088950`
- `0x1400893a0`
- `0x14008a448`
- `0x14008a73c`
- `0x14008b070`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x140089436`
- `ntoskrnl!ZwOpenKey` at `0x140089586`
- `ntoskrnl!ZwOpenKey` at `0x140089436`
- `ntoskrnl!ZwOpenKey` at `0x140089586`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400893f3`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400893f3`
- `ntoskrnl!ExAllocatePool2` at `0x1400894e1`
- `ntoskrnl!ExAllocatePool2` at `0x1400894e1`
- `ntoskrnl!ZwClose` at `0x1400895b0`
- `ntoskrnl!ZwClose` at `0x1400896c8`
- `ntoskrnl!ZwClose` at `0x1400895b0`
- `ntoskrnl!ZwClose` at `0x1400896c8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008963a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400896b2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008963a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400896b2`
- `ntoskrnl!ZwEnumerateKey` at `0x1400894ad`
- `ntoskrnl!ZwEnumerateKey` at `0x140089517`
- `ntoskrnl!ZwEnumerateKey` at `0x1400894ad`
- `ntoskrnl!ZwEnumerateKey` at `0x140089517`

## pseudocode

```c
__int64 __fastcall LookupIPv4ZoneMapEntry(__int64 a1, const WCHAR *a2, int *a3)
{
  int v5; // esi
  ULONG i; // r14d
  NTSTATUS v7; // eax
  _WORD *Pool2; // rdi
  int StringValueByHandle; // ebx
  bool v10; // zf
  int v11; // eax
  void *KeyHandle; // [rsp+30h] [rbp-D0h] BYREF
  int v14; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE Handle; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v16; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v17; // [rsp+58h] [rbp-A8h] BYREF
  UNICODE_STRING DestinationString; // [rsp+68h] [rbp-98h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-88h] BYREF
  struct _OBJECT_ATTRIBUTES v20; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v21[64]; // [rsp+E0h] [rbp-20h] BYREF
  char v22; // [rsp+160h] [rbp+60h] BYREF
  ULONG ResultLength; // [rsp+168h] [rbp+68h] BYREF

  KeyHandle = 0;
  v14 = 3;
  *(_OWORD *)&ObjectAttributes.Length = 0;
  *a3 = 3;
  memset(&ObjectAttributes.ObjectName, 0, 32);
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, a2);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) < 0 )
  {
    Pool2 = 0;
    goto LABEL_29;
  }
  v5 = 0;
  for ( i = 0; ; ++i )
  {
    ResultLength = 0;
    Handle = 0;
    v16 = 0;
    memset(&v20, 0, sizeof(v20));
    v17 = 0;
    memset(v21, 0, sizeof(v21));
    v22 = 0;
    v7 = ZwEnumerateKey(KeyHandle, i, KeyBasicInformation, 0, 0, &ResultLength);
    if ( v7 >= 0 || v7 != -1073741789 && v7 != -2147483643 )
      break;
    Pool2 = (_WORD *)ExAllocatePool2(258, ResultLength, 2051894611);
    if ( !Pool2 )
    {
      v5 = -1073741670;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 41, WPP_318b97441ad5316ed29d4021e7d37a6e_Traceguids, i);
      }
      goto LABEL_32;
    }
    if ( ZwEnumerateKey(KeyHandle, i, KeyBasicInformation, Pool2, ResultLength, &ResultLength) < 0 )
      goto LABEL_26;
    if ( *((_DWORD *)Pool2 + 3) >= 2u )
    {
      *((_QWORD *)&v16 + 1) = Pool2 + 8;
      LOWORD(v16) = Pool2[6];
      WORD1(v16) = Pool2[6];
      v20.RootDirectory = KeyHandle;
      v20.ObjectName = (PUNICODE_STRING)&v16;
      v20.Length = 48;
      v20.Attributes = 576;
      *(_OWORD *)&v20.SecurityDescriptor = 0;
      if ( ZwOpenKey(&Handle, 0x20019u, &v20) >= 0 )
      {
        StringValueByHandle = RegQueryStringValueByHandle(Handle);
        ZwClose(Handle);
        Handle = 0;
        if ( StringValueByHandle >= 0 )
        {
          v5 = ValidateAndParseIPv4Range(&v17, v21);
          FreeUnicodeString(&v17);
          if ( v5 < 0 )
          {
            v10 = v5 == -1073741811;
LABEL_13:
            if ( !v10 )
              goto LABEL_31;
            v5 = 0;
            goto LABEL_19;
          }
          v11 = CheckIPv4AddressInRange(a1, v21, &v22);
          v5 = v11;
          if ( v11 < 0 )
          {
            v10 = v11 == -1073741811;
            goto LABEL_13;
          }
          if ( v22 && (int)RegQueryZoneFromKey(KeyHandle, &v16, &v14) >= 0 )
          {
            *a3 = v14;
            goto LABEL_31;
          }
        }
      }
    }
LABEL_19:
    ExFreePoolWithTag(Pool2, 0x7A4D6D53u);
  }
  Pool2 = 0;
LABEL_26:
  if ( v5 < 0 )
    goto LABEL_30;
LABEL_29:
  v5 = -1073741772;
LABEL_30:
  if ( Pool2 )
LABEL_31:
    ExFreePoolWithTag(Pool2, 0x7A4D6D53u);
LABEL_32:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1400893a0  mov     [rsp-8+arg_0], rbx
0x1400893a5  mov     [rsp-8+arg_8], rsi
0x1400893aa  push    rbp
0x1400893ab  push    rdi
0x1400893ac  push    r12
0x1400893ae  push    r14
0x1400893b0  push    r15
0x1400893b2  lea     rbp, [rsp-20h]
0x1400893b7  sub     rsp, 120h
0x1400893be  xorps   xmm0, xmm0
0x1400893c1  mov     [rsp+140h+KeyHandle], 0
0x1400893ca  mov     eax, 3
0x1400893cf  mov     r12, rcx
0x1400893d2  lea     rcx, [rsp+140h+DestinationString]; DestinationString
0x1400893d7  mov     [rsp+140h+var_108], eax
0x1400893db  movups  xmmword ptr [rsp+140h+ObjectAttributes.Length], xmm0
0x1400893e0  mov     [r8], eax
0x1400893e3  mov     r15, r8
0x1400893e6  movups  xmmword ptr [rbp+40h+ObjectAttributes.ObjectName], xmm0
0x1400893ea  movups  xmmword ptr [rbp+40h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400893ee  movups  xmmword ptr [rsp+140h+DestinationString.Length], xmm0
0x1400893f3  call    cs:__imp_RtlInitUnicodeString
0x1400893fa  nop     dword ptr [rax+rax+00h]
0x1400893ff  lea     rax, [rsp+140h+DestinationString]
0x140089404  mov     [rsp+140h+ObjectAttributes.Length], 30h ; '0'
0x14008940c  xorps   xmm0, xmm0
0x14008940f  mov     [rbp+40h+ObjectAttributes.ObjectName], rax
0x140089413  lea     r8, [rsp+140h+ObjectAttributes]; ObjectAttributes
0x140089418  mov     [rbp+40h+ObjectAttributes.RootDirectory], 0
0x140089420  mov     edx, 20019h; DesiredAccess
0x140089425  mov     [rbp+40h+ObjectAttributes.Attributes], 240h
0x14008942c  lea     rcx, [rsp+140h+KeyHandle]; KeyHandle
0x140089431  movdqu  xmmword ptr [rbp+40h+ObjectAttributes.SecurityDescriptor], xmm0
0x140089436  call    cs:__imp_ZwOpenKey
0x14008943d  nop     dword ptr [rax+rax+00h]
0x140089442  test    eax, eax
0x140089444  js      loc_14008969E
0x14008944a  xor     esi, esi
0x14008944c  xor     r14d, r14d
0x14008944f  xorps   xmm1, xmm1
0x140089452  mov     [rbp+40h+arg_18], 0
0x140089459  xorps   xmm0, xmm0
0x14008945c  mov     [rsp+140h+Handle], 0
0x140089465  xor     edx, edx; Val
0x140089467  lea     rcx, [rbp+40h+var_60]; void *
0x14008946b  movups  [rsp+140h+var_F8], xmm0
0x140089470  movups  xmmword ptr [rbp+40h+var_98.Length], xmm1
0x140089474  lea     r8d, [rdx+40h]; Size
0x140089478  movups  xmmword ptr [rbp+40h+var_98.ObjectName], xmm1
0x14008947c  movups  xmmword ptr [rbp+40h+var_98.SecurityDescriptor], xmm1
0x140089480  movups  [rsp+140h+var_E8], xmm0
0x140089485  call    memset
0x14008948a  mov     rcx, [rsp+140h+KeyHandle]; KeyHandle
0x14008948f  lea     rax, [rbp+40h+arg_18]
0x140089493  mov     [rsp+140h+ResultLength], rax; ResultLength
0x140089498  xor     r9d, r9d; KeyInformation
0x14008949b  xor     r8d, r8d; KeyInformationClass
0x14008949e  mov     [rsp+140h+Length], 0; Length
0x1400894a6  mov     edx, r14d; Index
0x1400894a9  mov     [rbp+40h+arg_10], 0
0x1400894ad  call    cs:__imp_ZwEnumerateKey
0x1400894b4  nop     dword ptr [rax+rax+00h]
0x1400894b9  test    eax, eax
0x1400894bb  jns     loc_140089696
0x1400894c1  cmp     eax, 0C0000023h
0x1400894c6  jz      short loc_1400894D3
0x1400894c8  cmp     eax, 80000005h
0x1400894cd  jnz     loc_140089696
0x1400894d3  mov     edx, [rbp+40h+arg_18]
0x1400894d6  mov     ecx, 102h
0x1400894db  mov     r8d, 7A4D6D53h
0x1400894e1  call    cs:__imp_ExAllocatePool2
0x1400894e8  nop     dword ptr [rax+rax+00h]
0x1400894ed  mov     rdi, rax
0x1400894f0  test    rax, rax
0x1400894f3  jz      loc_140089657
0x1400894f9  mov     ecx, [rbp+40h+arg_18]
0x1400894fc  lea     rax, [rbp+40h+arg_18]
0x140089500  mov     [rsp+140h+ResultLength], rax; ResultLength
0x140089505  mov     r9, rdi; KeyInformation
0x140089508  mov     [rsp+140h+Length], ecx; Length
0x14008950c  xor     r8d, r8d; KeyInformationClass
0x14008950f  mov     rcx, [rsp+140h+KeyHandle]; KeyHandle
0x140089514  mov     edx, r14d; Index
0x140089517  call    cs:__imp_ZwEnumerateKey
0x14008951e  nop     dword ptr [rax+rax+00h]
0x140089523  test    eax, eax
0x140089525  js      loc_140089698
0x14008952b  cmp     dword ptr [rdi+0Ch], 2
0x14008952f  jb      loc_140089632
0x140089535  lea     rax, [rdi+10h]
0x140089539  xorps   xmm0, xmm0
0x14008953c  mov     qword ptr [rsp+140h+var_F8+8], rax
0x140089541  lea     r8, [rbp+40h+var_98]; ObjectAttributes
0x140089545  movzx   eax, word ptr [rdi+0Ch]
0x140089549  lea     rcx, [rsp+140h+Handle]; KeyHandle
0x14008954e  mov     word ptr [rsp+140h+var_F8], ax
0x140089553  mov     edx, 20019h; DesiredAccess
0x140089558  movzx   eax, word ptr [rdi+0Ch]
0x14008955c  mov     word ptr [rsp+140h+var_F8+2], ax
0x140089561  mov     rax, [rsp+140h+KeyHandle]
0x140089566  mov     [rbp+40h+var_98.RootDirectory], rax
0x14008956a  lea     rax, [rsp+140h+var_F8]
0x14008956f  mov     [rbp+40h+var_98.ObjectName], rax
0x140089573  mov     [rbp+40h+var_98.Length], 30h ; '0'
0x14008957a  mov     [rbp+40h+var_98.Attributes], 240h
0x140089581  movdqu  xmmword ptr [rbp+40h+var_98.SecurityDescriptor], xmm0
0x140089586  call    cs:__imp_ZwOpenKey
0x14008958d  nop     dword ptr [rax+rax+00h]
0x140089592  test    eax, eax
0x140089594  js      loc_140089632
0x14008959a  mov     rcx, [rsp+140h+Handle]; KeyHandle
0x14008959f  lea     r8, [rsp+140h+var_E8]
0x1400895a4  call    RegQueryStringValueByHandle
0x1400895a9  mov     rcx, [rsp+140h+Handle]; Handle
0x1400895ae  mov     ebx, eax
0x1400895b0  call    cs:__imp_ZwClose
0x1400895b7  nop     dword ptr [rax+rax+00h]
0x1400895bc  mov     [rsp+140h+Handle], 0
0x1400895c5  test    ebx, ebx
0x1400895c7  js      short loc_140089632
0x1400895c9  lea     rdx, [rbp+40h+var_60]
0x1400895cd  lea     rcx, [rsp+140h+var_E8]
0x1400895d2  call    ValidateAndParseIPv4Range
0x1400895d7  lea     rcx, [rsp+140h+var_E8]
0x1400895dc  mov     esi, eax
0x1400895de  call    FreeUnicodeString
0x1400895e3  test    esi, esi
0x1400895e5  jns     short loc_1400895F7
0x1400895e7  cmp     esi, 0C000000Dh
0x1400895ed  jnz     loc_1400896AA
0x1400895f3  xor     esi, esi
0x1400895f5  jmp     short loc_140089632
0x1400895f7  lea     r8, [rbp+40h+arg_10]
0x1400895fb  mov     rcx, r12
0x1400895fe  lea     rdx, [rbp+40h+var_60]
0x140089602  call    CheckIPv4AddressInRange
0x140089607  mov     esi, eax
0x140089609  test    eax, eax
0x14008960b  jns     short loc_140089614
0x14008960d  cmp     eax, 0C000000Dh
0x140089612  jmp     short loc_1400895ED
0x140089614  cmp     [rbp+40h+arg_10], 0
0x140089618  jz      short loc_140089632
0x14008961a  mov     rcx, [rsp+140h+KeyHandle]
0x14008961f  lea     r8, [rsp+140h+var_108]
0x140089624  lea     rdx, [rsp+140h+var_F8]
0x140089629  call    RegQueryZoneFromKey
0x14008962e  test    eax, eax
0x140089630  jns     short loc_14008964E
0x140089632  mov     edx, 7A4D6D53h; Tag
0x140089637  mov     rcx, rdi; P
0x14008963a  call    cs:__imp_ExFreePoolWithTag
0x140089641  nop     dword ptr [rax+rax+00h]
0x140089646  inc     r14d
0x140089649  jmp     loc_14008944F
0x14008964e  mov     eax, [rsp+140h+var_108]
0x140089652  mov     [r15], eax
0x140089655  jmp     short loc_1400896AA
0x140089657  mov     esi, 0C000009Ah
0x14008965c  mov     rcx, cs:WPP_GLOBAL_Control
0x140089663  lea     rax, WPP_GLOBAL_Control
0x14008966a  cmp     rcx, rax
0x14008966d  jz      short loc_1400896BE
0x14008966f  mov     eax, [rcx+2Ch]
0x140089672  test    al, 1
0x140089674  jz      short loc_1400896BE
0x140089676  cmp     byte ptr [rcx+29h], 1
0x14008967a  jb      short loc_1400896BE
0x14008967c  mov     rcx, [rcx+18h]
0x140089680  lea     r8, WPP_318b97441ad5316ed29d4021e7d37a6e_Traceguids
0x140089687  mov     edx, 29h ; ')'
0x14008968c  mov     r9d, r14d
0x14008968f  call    WPP_SF_d
0x140089694  jmp     short loc_1400896BE
0x140089696  xor     edi, edi
0x140089698  test    esi, esi
0x14008969a  js      short loc_1400896A5
0x14008969c  jmp     short loc_1400896A0
0x14008969e  xor     edi, edi
0x1400896a0  mov     esi, 0C0000034h
0x1400896a5  test    rdi, rdi
0x1400896a8  jz      short loc_1400896BE
0x1400896aa  mov     edx, 7A4D6D53h; Tag
0x1400896af  mov     rcx, rdi; P
0x1400896b2  call    cs:__imp_ExFreePoolWithTag
0x1400896b9  nop     dword ptr [rax+rax+00h]
0x1400896be  mov     rcx, [rsp+140h+KeyHandle]; Handle
0x1400896c3  test    rcx, rcx
0x1400896c6  jz      short loc_1400896D4
0x1400896c8  call    cs:__imp_ZwClose
0x1400896cf  nop     dword ptr [rax+rax+00h]
0x1400896d4  lea     r11, [rsp+140h+var_20]
0x1400896dc  mov     eax, esi
0x1400896de  mov     rbx, [r11+30h]
0x1400896e2  mov     rsi, [r11+38h]
0x1400896e6  mov     rsp, r11
0x1400896e9  pop     r15
0x1400896eb  pop     r14
0x1400896ed  pop     r12
0x1400896ef  pop     rdi
0x1400896f0  pop     rbp
0x1400896f1  retn
```
