# LookupIPv4ZoneMapEntry

- ea: `0x1400893f0`
- end: `0x140089743`
- name: `LookupIPv4ZoneMapEntry`
- size: `851`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140089934`

## callees

- `0x14003838c`
- `0x14005a200`
- `0x140088588`
- `0x1400889a0`
- `0x1400893f0`
- `0x14008a498`
- `0x14008a78c`
- `0x14008b0c0`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x140089486`
- `ntoskrnl!ZwOpenKey` at `0x1400895d6`
- `ntoskrnl!ZwOpenKey` at `0x140089486`
- `ntoskrnl!ZwOpenKey` at `0x1400895d6`
- `ntoskrnl!RtlInitUnicodeString` at `0x140089443`
- `ntoskrnl!RtlInitUnicodeString` at `0x140089443`
- `ntoskrnl!ExAllocatePool2` at `0x140089531`
- `ntoskrnl!ExAllocatePool2` at `0x140089531`
- `ntoskrnl!ZwClose` at `0x140089600`
- `ntoskrnl!ZwClose` at `0x140089718`
- `ntoskrnl!ZwClose` at `0x140089600`
- `ntoskrnl!ZwClose` at `0x140089718`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008968a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140089702`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008968a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140089702`
- `ntoskrnl!ZwEnumerateKey` at `0x1400894fd`
- `ntoskrnl!ZwEnumerateKey` at `0x140089567`
- `ntoskrnl!ZwEnumerateKey` at `0x1400894fd`
- `ntoskrnl!ZwEnumerateKey` at `0x140089567`

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
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 41, &WPP_318b97441ad5316ed29d4021e7d37a6e_Traceguids, i);
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
0x1400893f0  mov     [rsp-8+arg_0], rbx
0x1400893f5  mov     [rsp-8+arg_8], rsi
0x1400893fa  push    rbp
0x1400893fb  push    rdi
0x1400893fc  push    r12
0x1400893fe  push    r14
0x140089400  push    r15
0x140089402  lea     rbp, [rsp-20h]
0x140089407  sub     rsp, 120h
0x14008940e  xorps   xmm0, xmm0
0x140089411  mov     [rsp+140h+KeyHandle], 0
0x14008941a  mov     eax, 3
0x14008941f  mov     r12, rcx
0x140089422  lea     rcx, [rsp+140h+DestinationString]; DestinationString
0x140089427  mov     [rsp+140h+var_108], eax
0x14008942b  movups  xmmword ptr [rsp+140h+ObjectAttributes.Length], xmm0
0x140089430  mov     [r8], eax
0x140089433  mov     r15, r8
0x140089436  movups  xmmword ptr [rbp+40h+ObjectAttributes.ObjectName], xmm0
0x14008943a  movups  xmmword ptr [rbp+40h+ObjectAttributes.SecurityDescriptor], xmm0
0x14008943e  movups  xmmword ptr [rsp+140h+DestinationString.Length], xmm0
0x140089443  call    cs:__imp_RtlInitUnicodeString
0x14008944a  nop     dword ptr [rax+rax+00h]
0x14008944f  lea     rax, [rsp+140h+DestinationString]
0x140089454  mov     [rsp+140h+ObjectAttributes.Length], 30h ; '0'
0x14008945c  xorps   xmm0, xmm0
0x14008945f  mov     [rbp+40h+ObjectAttributes.ObjectName], rax
0x140089463  lea     r8, [rsp+140h+ObjectAttributes]; ObjectAttributes
0x140089468  mov     [rbp+40h+ObjectAttributes.RootDirectory], 0
0x140089470  mov     edx, 20019h; DesiredAccess
0x140089475  mov     [rbp+40h+ObjectAttributes.Attributes], 240h
0x14008947c  lea     rcx, [rsp+140h+KeyHandle]; KeyHandle
0x140089481  movdqu  xmmword ptr [rbp+40h+ObjectAttributes.SecurityDescriptor], xmm0
0x140089486  call    cs:__imp_ZwOpenKey
0x14008948d  nop     dword ptr [rax+rax+00h]
0x140089492  test    eax, eax
0x140089494  js      loc_1400896EE
0x14008949a  xor     esi, esi
0x14008949c  xor     r14d, r14d
0x14008949f  xorps   xmm1, xmm1
0x1400894a2  mov     [rbp+40h+arg_18], 0
0x1400894a9  xorps   xmm0, xmm0
0x1400894ac  mov     [rsp+140h+Handle], 0
0x1400894b5  xor     edx, edx; Val
0x1400894b7  lea     rcx, [rbp+40h+var_60]; void *
0x1400894bb  movups  [rsp+140h+var_F8], xmm0
0x1400894c0  movups  xmmword ptr [rbp+40h+var_98.Length], xmm1
0x1400894c4  lea     r8d, [rdx+40h]; Size
0x1400894c8  movups  xmmword ptr [rbp+40h+var_98.ObjectName], xmm1
0x1400894cc  movups  xmmword ptr [rbp+40h+var_98.SecurityDescriptor], xmm1
0x1400894d0  movups  [rsp+140h+var_E8], xmm0
0x1400894d5  call    memset
0x1400894da  mov     rcx, [rsp+140h+KeyHandle]; KeyHandle
0x1400894df  lea     rax, [rbp+40h+arg_18]
0x1400894e3  mov     [rsp+140h+ResultLength], rax; ResultLength
0x1400894e8  xor     r9d, r9d; KeyInformation
0x1400894eb  xor     r8d, r8d; KeyInformationClass
0x1400894ee  mov     [rsp+140h+Length], 0; Length
0x1400894f6  mov     edx, r14d; Index
0x1400894f9  mov     [rbp+40h+arg_10], 0
0x1400894fd  call    cs:__imp_ZwEnumerateKey
0x140089504  nop     dword ptr [rax+rax+00h]
0x140089509  test    eax, eax
0x14008950b  jns     loc_1400896E6
0x140089511  cmp     eax, 0C0000023h
0x140089516  jz      short loc_140089523
0x140089518  cmp     eax, 80000005h
0x14008951d  jnz     loc_1400896E6
0x140089523  mov     edx, [rbp+40h+arg_18]
0x140089526  mov     ecx, 102h
0x14008952b  mov     r8d, 7A4D6D53h
0x140089531  call    cs:__imp_ExAllocatePool2
0x140089538  nop     dword ptr [rax+rax+00h]
0x14008953d  mov     rdi, rax
0x140089540  test    rax, rax
0x140089543  jz      loc_1400896A7
0x140089549  mov     ecx, [rbp+40h+arg_18]
0x14008954c  lea     rax, [rbp+40h+arg_18]
0x140089550  mov     [rsp+140h+ResultLength], rax; ResultLength
0x140089555  mov     r9, rdi; KeyInformation
0x140089558  mov     [rsp+140h+Length], ecx; Length
0x14008955c  xor     r8d, r8d; KeyInformationClass
0x14008955f  mov     rcx, [rsp+140h+KeyHandle]; KeyHandle
0x140089564  mov     edx, r14d; Index
0x140089567  call    cs:__imp_ZwEnumerateKey
0x14008956e  nop     dword ptr [rax+rax+00h]
0x140089573  test    eax, eax
0x140089575  js      loc_1400896E8
0x14008957b  cmp     dword ptr [rdi+0Ch], 2
0x14008957f  jb      loc_140089682
0x140089585  lea     rax, [rdi+10h]
0x140089589  xorps   xmm0, xmm0
0x14008958c  mov     qword ptr [rsp+140h+var_F8+8], rax
0x140089591  lea     r8, [rbp+40h+var_98]; ObjectAttributes
0x140089595  movzx   eax, word ptr [rdi+0Ch]
0x140089599  lea     rcx, [rsp+140h+Handle]; KeyHandle
0x14008959e  mov     word ptr [rsp+140h+var_F8], ax
0x1400895a3  mov     edx, 20019h; DesiredAccess
0x1400895a8  movzx   eax, word ptr [rdi+0Ch]
0x1400895ac  mov     word ptr [rsp+140h+var_F8+2], ax
0x1400895b1  mov     rax, [rsp+140h+KeyHandle]
0x1400895b6  mov     [rbp+40h+var_98.RootDirectory], rax
0x1400895ba  lea     rax, [rsp+140h+var_F8]
0x1400895bf  mov     [rbp+40h+var_98.ObjectName], rax
0x1400895c3  mov     [rbp+40h+var_98.Length], 30h ; '0'
0x1400895ca  mov     [rbp+40h+var_98.Attributes], 240h
0x1400895d1  movdqu  xmmword ptr [rbp+40h+var_98.SecurityDescriptor], xmm0
0x1400895d6  call    cs:__imp_ZwOpenKey
0x1400895dd  nop     dword ptr [rax+rax+00h]
0x1400895e2  test    eax, eax
0x1400895e4  js      loc_140089682
0x1400895ea  mov     rcx, [rsp+140h+Handle]; KeyHandle
0x1400895ef  lea     r8, [rsp+140h+var_E8]
0x1400895f4  call    RegQueryStringValueByHandle
0x1400895f9  mov     rcx, [rsp+140h+Handle]; Handle
0x1400895fe  mov     ebx, eax
0x140089600  call    cs:__imp_ZwClose
0x140089607  nop     dword ptr [rax+rax+00h]
0x14008960c  mov     [rsp+140h+Handle], 0
0x140089615  test    ebx, ebx
0x140089617  js      short loc_140089682
0x140089619  lea     rdx, [rbp+40h+var_60]
0x14008961d  lea     rcx, [rsp+140h+var_E8]
0x140089622  call    ValidateAndParseIPv4Range
0x140089627  lea     rcx, [rsp+140h+var_E8]
0x14008962c  mov     esi, eax
0x14008962e  call    FreeUnicodeString
0x140089633  test    esi, esi
0x140089635  jns     short loc_140089647
0x140089637  cmp     esi, 0C000000Dh
0x14008963d  jnz     loc_1400896FA
0x140089643  xor     esi, esi
0x140089645  jmp     short loc_140089682
0x140089647  lea     r8, [rbp+40h+arg_10]
0x14008964b  mov     rcx, r12
0x14008964e  lea     rdx, [rbp+40h+var_60]
0x140089652  call    CheckIPv4AddressInRange
0x140089657  mov     esi, eax
0x140089659  test    eax, eax
0x14008965b  jns     short loc_140089664
0x14008965d  cmp     eax, 0C000000Dh
0x140089662  jmp     short loc_14008963D
0x140089664  cmp     [rbp+40h+arg_10], 0
0x140089668  jz      short loc_140089682
0x14008966a  mov     rcx, [rsp+140h+KeyHandle]
0x14008966f  lea     r8, [rsp+140h+var_108]
0x140089674  lea     rdx, [rsp+140h+var_F8]
0x140089679  call    RegQueryZoneFromKey
0x14008967e  test    eax, eax
0x140089680  jns     short loc_14008969E
0x140089682  mov     edx, 7A4D6D53h; Tag
0x140089687  mov     rcx, rdi; P
0x14008968a  call    cs:__imp_ExFreePoolWithTag
0x140089691  nop     dword ptr [rax+rax+00h]
0x140089696  inc     r14d
0x140089699  jmp     loc_14008949F
0x14008969e  mov     eax, [rsp+140h+var_108]
0x1400896a2  mov     [r15], eax
0x1400896a5  jmp     short loc_1400896FA
0x1400896a7  mov     esi, 0C000009Ah
0x1400896ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1400896b3  lea     rax, WPP_GLOBAL_Control
0x1400896ba  cmp     rcx, rax
0x1400896bd  jz      short loc_14008970E
0x1400896bf  mov     eax, [rcx+2Ch]
0x1400896c2  test    al, 1
0x1400896c4  jz      short loc_14008970E
0x1400896c6  cmp     byte ptr [rcx+29h], 1
0x1400896ca  jb      short loc_14008970E
0x1400896cc  mov     rcx, [rcx+18h]
0x1400896d0  lea     r8, WPP_318b97441ad5316ed29d4021e7d37a6e_Traceguids
0x1400896d7  mov     edx, 29h ; ')'
0x1400896dc  mov     r9d, r14d
0x1400896df  call    WPP_SF_d
0x1400896e4  jmp     short loc_14008970E
0x1400896e6  xor     edi, edi
0x1400896e8  test    esi, esi
0x1400896ea  js      short loc_1400896F5
0x1400896ec  jmp     short loc_1400896F0
0x1400896ee  xor     edi, edi
0x1400896f0  mov     esi, 0C0000034h
0x1400896f5  test    rdi, rdi
0x1400896f8  jz      short loc_14008970E
0x1400896fa  mov     edx, 7A4D6D53h; Tag
0x1400896ff  mov     rcx, rdi; P
0x140089702  call    cs:__imp_ExFreePoolWithTag
0x140089709  nop     dword ptr [rax+rax+00h]
0x14008970e  mov     rcx, [rsp+140h+KeyHandle]; Handle
0x140089713  test    rcx, rcx
0x140089716  jz      short loc_140089724
0x140089718  call    cs:__imp_ZwClose
0x14008971f  nop     dword ptr [rax+rax+00h]
0x140089724  lea     r11, [rsp+140h+var_20]
0x14008972c  mov     eax, esi
0x14008972e  mov     rbx, [r11+30h]
0x140089732  mov     rsi, [r11+38h]
0x140089736  mov     rsp, r11
0x140089739  pop     r15
0x14008973b  pop     r14
0x14008973d  pop     r12
0x14008973f  pop     rdi
0x140089740  pop     rbp
0x140089741  retn
```
