# KsUnserializeObjectPropertiesFromRegistry

- ea: `0x180034890`
- end: `0x180034ad4`
- name: `KsUnserializeObjectPropertiesFromRegistry`
- size: `580`
- prototype: `NTSTATUS __stdcall(PFILE_OBJECT FileObject, HANDLE ParentKey, PUNICODE_STRING RegistryPath)`
- caller_count: `0`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180019bd0`
- `0x18001a000`
- `0x180034890`
- `0x180051360`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x180034aa2`
- `ntoskrnl!ZwClose` at `0x180034aa2`
- `ntoskrnl!ZwOpenKey` at `0x180034902`
- `ntoskrnl!ZwOpenKey` at `0x180034902`
- `ntoskrnl!ZwEnumerateValueKey` at `0x180034960`
- `ntoskrnl!ZwEnumerateValueKey` at `0x1800349dd`
- `ntoskrnl!ZwEnumerateValueKey` at `0x180034960`
- `ntoskrnl!ZwEnumerateValueKey` at `0x1800349dd`
- `ntoskrnl!ExFreePoolWithTag` at `0x180034a72`
- `ntoskrnl!ExFreePoolWithTag` at `0x180034a72`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180034990`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180034990`

## pseudocode

```c
NTSTATUS __stdcall KsUnserializeObjectPropertiesFromRegistry(
        PFILE_OBJECT FileObject,
        HANDLE ParentKey,
        PUNICODE_STRING RegistryPath)
{
  NTSTATUS result; // eax
  ULONG i; // esi
  NTSTATUS v7; // eax
  int v8; // ebx
  ULONG v9; // ebx
  char *PoolWithTag; // rax
  char *v11; // rdi
  ULONG OutSize; // [rsp+30h] [rbp-49h]
  ULONG ResultLength; // [rsp+40h] [rbp-39h] BYREF
  ULONG BytesReturned; // [rsp+44h] [rbp-35h] BYREF
  void *KeyHandle; // [rsp+48h] [rbp-31h] BYREF
  __int128 InBuffer; // [rsp+50h] [rbp-29h] BYREF
  int v17; // [rsp+60h] [rbp-19h]
  int v18; // [rsp+64h] [rbp-15h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-11h] BYREF
  __int128 KeyValueInformation; // [rsp+98h] [rbp+1Fh] BYREF

  KeyHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  KeyValueInformation = 0;
  if ( RegistryPath )
  {
    ObjectAttributes.RootDirectory = ParentKey;
    ObjectAttributes.ObjectName = RegistryPath;
    ObjectAttributes.Length = 48;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    result = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
    if ( result < 0 )
      return result;
  }
  else
  {
    if ( !ParentKey )
      return -1073741776;
    KeyHandle = ParentKey;
  }
  for ( i = 0; ; ++i )
  {
    BytesReturned = 0;
    ResultLength = 0;
    v7 = ZwEnumerateValueKey(KeyHandle, i, KeyValuePartialInformation, &KeyValueInformation, 0x10u, &ResultLength);
    v8 = v7;
    if ( ((v7 + 0x80000000) & 0x80000000) == 0 && v7 != -2147483643 )
      break;
    v9 = ResultLength;
    PoolWithTag = (char *)ExAllocatePoolWithTag((POOL_TYPE)1025, ResultLength, 0x7073534Bu);
    v11 = PoolWithTag;
    if ( !PoolWithTag )
    {
      v8 = -1073741670;
      goto LABEL_25;
    }
    if ( !ExPoolZeroingNativelySupported )
      memset(PoolWithTag, 0, v9);
    v8 = ZwEnumerateValueKey(KeyHandle, i, KeyValuePartialInformation, v11, ResultLength, &BytesReturned);
    if ( v8 < 0 )
    {
      if ( v8 == -2147483622 )
        v8 = 0;
    }
    else if ( BytesReturned > ResultLength || BytesReturned < 0x20 )
    {
      v8 = -1073741306;
    }
    else
    {
      *(_QWORD *)&InBuffer = 0;
      OutSize = *((_DWORD *)v11 + 2);
      InBuffer = *(_OWORD *)(v11 + 12);
      v17 = 0;
      v18 = 4096;
      v8 = KsSynchronousIoControlDevice(FileObject, 0, 0x2F0003u, &InBuffer, 0x18u, v11 + 12, OutSize, &BytesReturned);
    }
    ExFreePoolWithTag(v11, 0);
    if ( v8 < 0 )
      goto LABEL_25;
  }
  if ( v7 == -2147483622 )
    v8 = 0;
LABEL_25:
  if ( RegistryPath )
    ZwClose(KeyHandle);
  return v8;
}

```

## disassembly

```asm
0x180034890  mov     [rsp-8+arg_18], rbx
0x180034895  push    rbp
0x180034896  push    rsi
0x180034897  push    rdi
0x180034898  push    r14
0x18003489a  push    r15
0x18003489c  lea     rbp, [rsp-37h]
0x1800348a1  sub     rsp, 0B0h
0x1800348a8  mov     rax, cs:__security_cookie
0x1800348af  xor     rax, rsp
0x1800348b2  mov     [rbp+57h+var_28], rax
0x1800348b6  xorps   xmm0, xmm0
0x1800348b9  xor     eax, eax
0x1800348bb  mov     [rbp+57h+KeyHandle], rax
0x1800348bf  mov     r14, r8
0x1800348c2  mov     r15, rcx
0x1800348c5  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800348c9  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1800348cd  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800348d1  movups  [rbp+57h+KeyValueInformation], xmm0
0x1800348d5  test    r8, r8
0x1800348d8  jz      short loc_180034917
0x1800348da  mov     [rbp+57h+ObjectAttributes.RootDirectory], rdx
0x1800348de  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800348e2  mov     [rbp+57h+ObjectAttributes.ObjectName], r8
0x1800348e6  mov     edx, 20019h; DesiredAccess
0x1800348eb  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800348ef  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800348f6  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x1800348fd  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180034902  call    cs:__imp_ZwOpenKey
0x180034909  nop     dword ptr [rax+rax+00h]
0x18003490e  test    eax, eax
0x180034910  jns     short loc_18003492A
0x180034912  jmp     loc_180034AB0
0x180034917  test    rdx, rdx
0x18003491a  jnz     short loc_180034926
0x18003491c  mov     eax, 0C0000030h
0x180034921  jmp     loc_180034AB0
0x180034926  mov     [rbp+57h+KeyHandle], rdx
0x18003492a  xor     esi, esi
0x18003492c  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180034930  lea     rax, [rbp+57h+var_90]
0x180034934  mov     [rsp+0D0h+ResultLength], rax; ResultLength
0x180034939  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x18003493d  mov     r8d, 2; KeyValueInformationClass
0x180034943  mov     [rsp+0D0h+Length], 10h; Length
0x18003494b  mov     edx, esi; Index
0x18003494d  mov     [rbp+57h+var_8C], 0
0x180034954  mov     edi, 80000000h
0x180034959  mov     [rbp+57h+var_90], 0
0x180034960  call    cs:__imp_ZwEnumerateValueKey
0x180034967  nop     dword ptr [rax+rax+00h]
0x18003496c  mov     ebx, eax
0x18003496e  lea     ecx, [rax+rdi]
0x180034971  test    edi, ecx
0x180034973  jnz     short loc_180034980
0x180034975  cmp     eax, 80000005h
0x18003497a  jnz     loc_180034A89
0x180034980  mov     ebx, [rbp+57h+var_90]
0x180034983  mov     r8d, 7073534Bh; Tag
0x180034989  mov     edx, ebx; NumberOfBytes
0x18003498b  mov     ecx, 401h; PoolType
0x180034990  call    cs:__imp_ExAllocatePoolWithTag
0x180034997  nop     dword ptr [rax+rax+00h]
0x18003499c  mov     rdi, rax
0x18003499f  test    rax, rax
0x1800349a2  jz      loc_180034A94
0x1800349a8  cmp     cs:ExPoolZeroingNativelySupported, 0
0x1800349af  jnz     short loc_1800349BE
0x1800349b1  mov     r8d, ebx; Size
0x1800349b4  xor     edx, edx; Val
0x1800349b6  mov     rcx, rax; void *
0x1800349b9  call    memset
0x1800349be  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800349c2  lea     rax, [rbp+57h+var_8C]
0x1800349c6  mov     [rsp+0D0h+ResultLength], rax; ResultLength
0x1800349cb  mov     r9, rdi; KeyValueInformation
0x1800349ce  mov     eax, [rbp+57h+var_90]
0x1800349d1  mov     r8d, 2; KeyValueInformationClass
0x1800349d7  mov     edx, esi; Index
0x1800349d9  mov     [rsp+0D0h+Length], eax; Length
0x1800349dd  call    cs:__imp_ZwEnumerateValueKey
0x1800349e4  nop     dword ptr [rax+rax+00h]
0x1800349e9  mov     ebx, eax
0x1800349eb  test    eax, eax
0x1800349ed  js      short loc_180034A62
0x1800349ef  mov     eax, [rbp+57h+var_8C]
0x1800349f2  cmp     eax, [rbp+57h+var_90]
0x1800349f5  ja      short loc_180034A5B
0x1800349f7  cmp     eax, 20h ; ' '
0x1800349fa  jb      short loc_180034A5B
0x1800349fc  lea     rax, [rbp+57h+var_8C]
0x180034a00  mov     qword ptr [rbp+57h+InBuffer], 0
0x180034a08  mov     [rsp+0D0h+BytesReturned], rax; BytesReturned
0x180034a0d  lea     rcx, [rdi+0Ch]
0x180034a11  movups  xmm0, xmmword ptr [rcx]
0x180034a14  mov     eax, [rdi+8]
0x180034a17  lea     r9, [rbp+57h+InBuffer]; InBuffer
0x180034a1b  mov     [rsp+0D0h+OutSize], eax; OutSize
0x180034a1f  xor     edx, edx; RequestorMode
0x180034a21  mov     [rsp+0D0h+ResultLength], rcx; OutBuffer
0x180034a26  mov     r8d, 2F0003h; IoControl
0x180034a2c  mov     qword ptr [rbp+57h+InBuffer+8], 0
0x180034a34  mov     rcx, r15; FileObject
0x180034a37  movdqu  [rbp+57h+InBuffer], xmm0
0x180034a3c  mov     [rbp+57h+var_70], 0
0x180034a43  mov     [rbp+57h+var_6C], 1000h
0x180034a4a  mov     [rsp+0D0h+Length], 18h; InSize
0x180034a52  call    KsSynchronousIoControlDevice
0x180034a57  mov     ebx, eax
0x180034a59  jmp     short loc_180034A6D
0x180034a5b  mov     ebx, 0C0000206h
0x180034a60  jmp     short loc_180034A6D
0x180034a62  xor     eax, eax
0x180034a64  cmp     ebx, 8000001Ah
0x180034a6a  cmovz   ebx, eax
0x180034a6d  xor     edx, edx; Tag
0x180034a6f  mov     rcx, rdi; P
0x180034a72  call    cs:__imp_ExFreePoolWithTag
0x180034a79  nop     dword ptr [rax+rax+00h]
0x180034a7e  test    ebx, ebx
0x180034a80  js      short loc_180034A99
0x180034a82  inc     esi
0x180034a84  jmp     loc_18003492C
0x180034a89  cmp     eax, 8000001Ah
0x180034a8e  jnz     short loc_180034A99
0x180034a90  xor     ebx, ebx
0x180034a92  jmp     short loc_180034A99
0x180034a94  mov     ebx, 0C000009Ah
0x180034a99  test    r14, r14
0x180034a9c  jz      short loc_180034AAE
0x180034a9e  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x180034aa2  call    cs:__imp_ZwClose
0x180034aa9  nop     dword ptr [rax+rax+00h]
0x180034aae  mov     eax, ebx
0x180034ab0  mov     rcx, [rbp+57h+var_28]
0x180034ab4  xor     rcx, rsp; StackCookie
0x180034ab7  call    __security_check_cookie
0x180034abc  mov     rbx, [rsp+0D0h+arg_18]
0x180034ac4  add     rsp, 0B0h
0x180034acb  pop     r15
0x180034acd  pop     r14
0x180034acf  pop     rdi
0x180034ad0  pop     rsi
0x180034ad1  pop     rbp
0x180034ad2  retn
```
