# KsUnserializeObjectPropertiesFromRegistry

- ea: `0x180034840`
- end: `0x180034a84`
- name: `KsUnserializeObjectPropertiesFromRegistry`
- size: `580`
- prototype: `NTSTATUS __stdcall(PFILE_OBJECT FileObject, HANDLE ParentKey, PUNICODE_STRING RegistryPath)`
- caller_count: `0`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180019b80`
- `0x180019fc0`
- `0x180034840`
- `0x1800511c0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x180034a52`
- `ntoskrnl!ZwClose` at `0x180034a52`
- `ntoskrnl!ZwOpenKey` at `0x1800348b2`
- `ntoskrnl!ZwOpenKey` at `0x1800348b2`
- `ntoskrnl!ZwEnumerateValueKey` at `0x180034910`
- `ntoskrnl!ZwEnumerateValueKey` at `0x18003498d`
- `ntoskrnl!ZwEnumerateValueKey` at `0x180034910`
- `ntoskrnl!ZwEnumerateValueKey` at `0x18003498d`
- `ntoskrnl!ExFreePoolWithTag` at `0x180034a22`
- `ntoskrnl!ExFreePoolWithTag` at `0x180034a22`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180034940`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180034940`

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
0x180034840  mov     [rsp-8+arg_18], rbx
0x180034845  push    rbp
0x180034846  push    rsi
0x180034847  push    rdi
0x180034848  push    r14
0x18003484a  push    r15
0x18003484c  lea     rbp, [rsp-37h]
0x180034851  sub     rsp, 0B0h
0x180034858  mov     rax, cs:__security_cookie
0x18003485f  xor     rax, rsp
0x180034862  mov     [rbp+57h+var_28], rax
0x180034866  xorps   xmm0, xmm0
0x180034869  xor     eax, eax
0x18003486b  mov     [rbp+57h+KeyHandle], rax
0x18003486f  mov     r14, r8
0x180034872  mov     r15, rcx
0x180034875  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180034879  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18003487d  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180034881  movups  [rbp+57h+KeyValueInformation], xmm0
0x180034885  test    r8, r8
0x180034888  jz      short loc_1800348C7
0x18003488a  mov     [rbp+57h+ObjectAttributes.RootDirectory], rdx
0x18003488e  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180034892  mov     [rbp+57h+ObjectAttributes.ObjectName], r8
0x180034896  mov     edx, 20019h; DesiredAccess
0x18003489b  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18003489f  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800348a6  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x1800348ad  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800348b2  call    cs:__imp_ZwOpenKey
0x1800348b9  nop     dword ptr [rax+rax+00h]
0x1800348be  test    eax, eax
0x1800348c0  jns     short loc_1800348DA
0x1800348c2  jmp     loc_180034A60
0x1800348c7  test    rdx, rdx
0x1800348ca  jnz     short loc_1800348D6
0x1800348cc  mov     eax, 0C0000030h
0x1800348d1  jmp     loc_180034A60
0x1800348d6  mov     [rbp+57h+KeyHandle], rdx
0x1800348da  xor     esi, esi
0x1800348dc  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800348e0  lea     rax, [rbp+57h+var_90]
0x1800348e4  mov     [rsp+0D0h+ResultLength], rax; ResultLength
0x1800348e9  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x1800348ed  mov     r8d, 2; KeyValueInformationClass
0x1800348f3  mov     [rsp+0D0h+Length], 10h; Length
0x1800348fb  mov     edx, esi; Index
0x1800348fd  mov     [rbp+57h+var_8C], 0
0x180034904  mov     edi, 80000000h
0x180034909  mov     [rbp+57h+var_90], 0
0x180034910  call    cs:__imp_ZwEnumerateValueKey
0x180034917  nop     dword ptr [rax+rax+00h]
0x18003491c  mov     ebx, eax
0x18003491e  lea     ecx, [rax+rdi]
0x180034921  test    edi, ecx
0x180034923  jnz     short loc_180034930
0x180034925  cmp     eax, 80000005h
0x18003492a  jnz     loc_180034A39
0x180034930  mov     ebx, [rbp+57h+var_90]
0x180034933  mov     r8d, 7073534Bh; Tag
0x180034939  mov     edx, ebx; NumberOfBytes
0x18003493b  mov     ecx, 401h; PoolType
0x180034940  call    cs:__imp_ExAllocatePoolWithTag
0x180034947  nop     dword ptr [rax+rax+00h]
0x18003494c  mov     rdi, rax
0x18003494f  test    rax, rax
0x180034952  jz      loc_180034A44
0x180034958  cmp     cs:ExPoolZeroingNativelySupported, 0
0x18003495f  jnz     short loc_18003496E
0x180034961  mov     r8d, ebx; Size
0x180034964  xor     edx, edx; Val
0x180034966  mov     rcx, rax; void *
0x180034969  call    memset
0x18003496e  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180034972  lea     rax, [rbp+57h+var_8C]
0x180034976  mov     [rsp+0D0h+ResultLength], rax; ResultLength
0x18003497b  mov     r9, rdi; KeyValueInformation
0x18003497e  mov     eax, [rbp+57h+var_90]
0x180034981  mov     r8d, 2; KeyValueInformationClass
0x180034987  mov     edx, esi; Index
0x180034989  mov     [rsp+0D0h+Length], eax; Length
0x18003498d  call    cs:__imp_ZwEnumerateValueKey
0x180034994  nop     dword ptr [rax+rax+00h]
0x180034999  mov     ebx, eax
0x18003499b  test    eax, eax
0x18003499d  js      short loc_180034A12
0x18003499f  mov     eax, [rbp+57h+var_8C]
0x1800349a2  cmp     eax, [rbp+57h+var_90]
0x1800349a5  ja      short loc_180034A0B
0x1800349a7  cmp     eax, 20h ; ' '
0x1800349aa  jb      short loc_180034A0B
0x1800349ac  lea     rax, [rbp+57h+var_8C]
0x1800349b0  mov     qword ptr [rbp+57h+InBuffer], 0
0x1800349b8  mov     [rsp+0D0h+BytesReturned], rax; BytesReturned
0x1800349bd  lea     rcx, [rdi+0Ch]
0x1800349c1  movups  xmm0, xmmword ptr [rcx]
0x1800349c4  mov     eax, [rdi+8]
0x1800349c7  lea     r9, [rbp+57h+InBuffer]; InBuffer
0x1800349cb  mov     [rsp+0D0h+OutSize], eax; OutSize
0x1800349cf  xor     edx, edx; RequestorMode
0x1800349d1  mov     [rsp+0D0h+ResultLength], rcx; OutBuffer
0x1800349d6  mov     r8d, 2F0003h; IoControl
0x1800349dc  mov     qword ptr [rbp+57h+InBuffer+8], 0
0x1800349e4  mov     rcx, r15; FileObject
0x1800349e7  movdqu  [rbp+57h+InBuffer], xmm0
0x1800349ec  mov     [rbp+57h+var_70], 0
0x1800349f3  mov     [rbp+57h+var_6C], 1000h
0x1800349fa  mov     [rsp+0D0h+Length], 18h; InSize
0x180034a02  call    KsSynchronousIoControlDevice
0x180034a07  mov     ebx, eax
0x180034a09  jmp     short loc_180034A1D
0x180034a0b  mov     ebx, 0C0000206h
0x180034a10  jmp     short loc_180034A1D
0x180034a12  xor     eax, eax
0x180034a14  cmp     ebx, 8000001Ah
0x180034a1a  cmovz   ebx, eax
0x180034a1d  xor     edx, edx; Tag
0x180034a1f  mov     rcx, rdi; P
0x180034a22  call    cs:__imp_ExFreePoolWithTag
0x180034a29  nop     dword ptr [rax+rax+00h]
0x180034a2e  test    ebx, ebx
0x180034a30  js      short loc_180034A49
0x180034a32  inc     esi
0x180034a34  jmp     loc_1800348DC
0x180034a39  cmp     eax, 8000001Ah
0x180034a3e  jnz     short loc_180034A49
0x180034a40  xor     ebx, ebx
0x180034a42  jmp     short loc_180034A49
0x180034a44  mov     ebx, 0C000009Ah
0x180034a49  test    r14, r14
0x180034a4c  jz      short loc_180034A5E
0x180034a4e  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x180034a52  call    cs:__imp_ZwClose
0x180034a59  nop     dword ptr [rax+rax+00h]
0x180034a5e  mov     eax, ebx
0x180034a60  mov     rcx, [rbp+57h+var_28]
0x180034a64  xor     rcx, rsp; StackCookie
0x180034a67  call    __security_check_cookie
0x180034a6c  mov     rbx, [rsp+0D0h+arg_18]
0x180034a74  add     rsp, 0B0h
0x180034a7b  pop     r15
0x180034a7d  pop     r14
0x180034a7f  pop     rdi
0x180034a80  pop     rsi
0x180034a81  pop     rbp
0x180034a82  retn
```
