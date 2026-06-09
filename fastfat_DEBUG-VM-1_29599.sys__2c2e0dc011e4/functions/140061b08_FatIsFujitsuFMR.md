# FatIsFujitsuFMR

- ea: `0x140061b08`
- end: `0x140061cfb`
- name: `FatIsFujitsuFMR`
- size: `499`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140061078`

## callees

- `0x14000c230`
- `0x14000c680`
- `0x140061b08`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x140061b8d`
- `ntoskrnl!ZwOpenKey` at `0x140061b8d`
- `ntoskrnl!ZwQueryValueKey` at `0x140061c51`
- `ntoskrnl!ZwQueryValueKey` at `0x140061c51`
- `ntoskrnl!ZwClose` at `0x140061c6f`
- `ntoskrnl!ZwClose` at `0x140061cea`
- `ntoskrnl!ZwClose` at `0x140061c6f`
- `ntoskrnl!ZwClose` at `0x140061cea`
- `ntoskrnl!RtlCompareMemory` at `0x140061c98`
- `ntoskrnl!RtlCompareMemory` at `0x140061c98`
- `ntoskrnl!ExFreePoolWithTag` at `0x140061bd6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140061cbb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140061bd6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140061cbb`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140061bf7`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140061bf7`

## string_xrefs

- `0x140061b35`: `\Registry\Machine\Hardware\DESCRIPTION\System`

## pseudocode

```c
char FatIsFujitsuFMR()
{
  ULONG Length; // esi
  unsigned int *v2; // rbx
  unsigned int *v3; // r9
  char v4; // r14
  unsigned int *PoolWithTag; // rax
  unsigned int *v6; // rdi
  NTSTATUS v7; // edi
  ULONG ResultLength; // [rsp+30h] [rbp-99h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-91h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+40h] [rbp-89h] BYREF
  _QWORD v11[2]; // [rsp+50h] [rbp-79h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-69h] BYREF
  _BYTE P[96]; // [rsp+90h] [rbp-39h] BYREF

  KeyHandle = 0;
  ResultLength = 0;
  v11[1] = L"\\Registry\\Machine\\Hardware\\DESCRIPTION\\System";
  v11[0] = 6029402;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v11;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ValueName = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  Length = 92;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) < 0 )
    return 0;
  *(_DWORD *)&ValueName.Length = 1441812;
  ValueName.Buffer = L"Identifier";
  v2 = (unsigned int *)P;
  v3 = (unsigned int *)P;
  v4 = 1;
  while ( 1 )
  {
    v7 = ZwQueryValueKey(KeyHandle, &ValueName, KeyValueFullInformation, v3, Length, &ResultLength);
    if ( v7 != -2147483643 )
      break;
    if ( v2 != (unsigned int *)P )
      ExFreePoolWithTag(v2, 0);
    Length += 256;
    PoolWithTag = (unsigned int *)ExAllocatePoolWithTag((POOL_TYPE)1025, Length, 0x20746146u);
    v6 = PoolWithTag;
    if ( ExPoolZeroingNativelySupported )
    {
      if ( !PoolWithTag )
      {
LABEL_19:
        ZwClose(KeyHandle);
        return 0;
      }
    }
    else
    {
      if ( !PoolWithTag )
        goto LABEL_19;
      memset(PoolWithTag, 0, Length);
    }
    v2 = v6;
    v3 = v6;
  }
  ZwClose(KeyHandle);
  if ( v7 < 0 || v2[3] < 0x1A || RtlCompareMemory((char *)v2 + v2[2], L"FUJITSU FMR-", 0x18u) != 24 )
    v4 = 0;
  if ( v2 != (unsigned int *)P )
    ExFreePoolWithTag(v2, 0);
  return v4;
}

```

## disassembly

```asm
0x140061b08  push    rbp
0x140061b0a  push    rbx
0x140061b0b  push    rsi
0x140061b0c  push    rdi
0x140061b0d  push    r14
0x140061b0f  lea     rbp, [rsp-37h]
0x140061b14  sub     rsp, 100h
0x140061b1b  mov     rax, cs:__security_cookie
0x140061b22  xor     rax, rsp
0x140061b25  mov     [rbp+57h+var_30], rax
0x140061b29  xorps   xmm0, xmm0
0x140061b2c  mov     [rsp+120h+KeyHandle], 0
0x140061b35  lea     rax, aRegistryMachin_4; "\\Registry\\Machine\\Hardware\\DESCRIPT"...
0x140061b3c  mov     [rsp+120h+var_F0], 0
0x140061b44  mov     [rbp+57h+var_C8], rax
0x140061b48  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140061b4c  lea     rax, [rbp+57h+var_D0]
0x140061b50  mov     [rbp+57h+var_D0], 5C005Ah
0x140061b58  mov     edx, 20019h; DesiredAccess
0x140061b5d  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140061b61  lea     rcx, [rsp+120h+KeyHandle]; KeyHandle
0x140061b66  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140061b6e  movups  xmmword ptr [rsp+120h+ValueName.Length], xmm0
0x140061b73  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x140061b7b  mov     esi, 5Ch ; '\'
0x140061b80  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x140061b88  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140061b8d  call    cs:__imp_ZwOpenKey
0x140061b94  nop     dword ptr [rax+rax+00h]
0x140061b99  test    eax, eax
0x140061b9b  jns     short loc_140061BA4
0x140061b9d  xor     al, al
0x140061b9f  jmp     loc_140061CCA
0x140061ba4  lea     rax, aIdentifier; "Identifier"
0x140061bab  mov     dword ptr [rsp+120h+ValueName.Length], 160014h
0x140061bb3  mov     [rsp+120h+ValueName.Buffer], rax
0x140061bb8  lea     rbx, [rbp+57h+P]
0x140061bbc  lea     r9, [rbp+57h+P]
0x140061bc0  mov     r14d, 1
0x140061bc6  jmp     short loc_140061C36
0x140061bc8  lea     rax, [rbp+57h+P]
0x140061bcc  cmp     rbx, rax
0x140061bcf  jz      short loc_140061BE2
0x140061bd1  xor     edx, edx; Tag
0x140061bd3  mov     rcx, rbx; P
0x140061bd6  call    cs:__imp_ExFreePoolWithTag
0x140061bdd  nop     dword ptr [rax+rax+00h]
0x140061be2  add     esi, 100h
0x140061be8  mov     r8d, 20746146h; Tag
0x140061bee  mov     edx, esi; NumberOfBytes
0x140061bf0  mov     ecx, 401h; PoolType
0x140061bf5  mov     ebx, esi
0x140061bf7  call    cs:__imp_ExAllocatePoolWithTag
0x140061bfe  nop     dword ptr [rax+rax+00h]
0x140061c03  cmp     cs:ExPoolZeroingNativelySupported, 0
0x140061c0a  mov     rdi, rax
0x140061c0d  jnz     short loc_140061C27
0x140061c0f  test    rax, rax
0x140061c12  jz      loc_140061CE5
0x140061c18  mov     r8d, ebx; Size
0x140061c1b  xor     edx, edx; Val
0x140061c1d  mov     rcx, rax; void *
0x140061c20  call    memset
0x140061c25  jmp     short loc_140061C30
0x140061c27  test    rdi, rdi
0x140061c2a  jz      loc_140061CE5
0x140061c30  mov     rbx, rdi
0x140061c33  mov     r9, rdi; KeyValueInformation
0x140061c36  mov     rcx, [rsp+120h+KeyHandle]; KeyHandle
0x140061c3b  lea     rax, [rsp+120h+var_F0]
0x140061c40  mov     [rsp+120h+ResultLength], rax; ResultLength
0x140061c45  lea     rdx, [rsp+120h+ValueName]; ValueName
0x140061c4a  mov     r8d, r14d; KeyValueInformationClass
0x140061c4d  mov     [rsp+120h+Length], esi; Length
0x140061c51  call    cs:__imp_ZwQueryValueKey
0x140061c58  nop     dword ptr [rax+rax+00h]
0x140061c5d  mov     edi, eax
0x140061c5f  cmp     eax, 80000005h
0x140061c64  jz      loc_140061BC8
0x140061c6a  mov     rcx, [rsp+120h+KeyHandle]; Handle
0x140061c6f  call    cs:__imp_ZwClose
0x140061c76  nop     dword ptr [rax+rax+00h]
0x140061c7b  test    edi, edi
0x140061c7d  js      short loc_140061CAA
0x140061c7f  cmp     dword ptr [rbx+0Ch], 1Ah
0x140061c83  jb      short loc_140061CAA
0x140061c85  mov     ecx, [rbx+8]
0x140061c88  lea     rdx, aFujitsuFmr; "FUJITSU FMR-"
0x140061c8f  add     rcx, rbx; Source1
0x140061c92  mov     r8d, 18h; Length
0x140061c98  call    cs:__imp_RtlCompareMemory
0x140061c9f  nop     dword ptr [rax+rax+00h]
0x140061ca4  cmp     rax, 18h
0x140061ca8  jz      short loc_140061CAD
0x140061caa  xor     r14b, r14b
0x140061cad  lea     rax, [rbp+57h+P]
0x140061cb1  cmp     rbx, rax
0x140061cb4  jz      short loc_140061CC7
0x140061cb6  xor     edx, edx; Tag
0x140061cb8  mov     rcx, rbx; P
0x140061cbb  call    cs:__imp_ExFreePoolWithTag
0x140061cc2  nop     dword ptr [rax+rax+00h]
0x140061cc7  mov     al, r14b
0x140061cca  mov     rcx, [rbp+57h+var_30]
0x140061cce  xor     rcx, rsp; StackCookie
0x140061cd1  call    __security_check_cookie
0x140061cd6  add     rsp, 100h
0x140061cdd  pop     r14
0x140061cdf  pop     rdi
0x140061ce0  pop     rsi
0x140061ce1  pop     rbx
0x140061ce2  pop     rbp
0x140061ce3  retn
0x140061ce5  mov     rcx, [rsp+120h+KeyHandle]; Handle
0x140061cea  call    cs:__imp_ZwClose
0x140061cf1  nop     dword ptr [rax+rax+00h]
0x140061cf6  jmp     loc_140061B9D
```
