# ClfsRegistryInitializeExemptionKey

- ea: `0x14004ddb4`
- end: `0x14004df21`
- name: `ClfsRegistryInitializeExemptionKey`
- size: `365`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14004d968`

## callees

- `0x14004ddb4`
- `0x140071e8c`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14004ded7`
- `ntoskrnl!ZwClose` at `0x140080738`
- `ntoskrnl!ZwClose` at `0x14004ded7`
- `ntoskrnl!ZwClose` at `0x140080738`
- `ntoskrnl!ZwCreateKey` at `0x14004de8a`
- `ntoskrnl!ZwCreateKey` at `0x14004de8a`
- `ntoskrnl!ZwSetSecurityObject` at `0x14004deb6`
- `ntoskrnl!ZwSetSecurityObject` at `0x14004deb6`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004ddfb`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004ddfb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004df01`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008075d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004df01`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008075d`

## pseudocode

```c
__int64 __fastcall ClfsRegistryInitializeExemptionKey(HANDLE *a1)
{
  __int64 v2; // rcx
  int v3; // ebx
  PSECURITY_DESCRIPTOR v4; // rdi
  UNICODE_STRING v6; // [rsp+40h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-38h] BYREF
  ULONG Disposition; // [rsp+98h] [rbp+10h] BYREF
  void *KeyHandle; // [rsp+A0h] [rbp+18h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+A8h] [rbp+20h] BYREF

  KeyHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v6 = 0;
  SecurityDescriptor = 0;
  Disposition = 0;
  RtlInitUnicodeString(&v6, L"Exemptions");
  v3 = ClfsCreateAuthRegistrySecurityDescriptor(v2, &SecurityDescriptor);
  if ( v3 >= 0 )
  {
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = *a1;
    ObjectAttributes.Attributes = 576;
    ObjectAttributes.ObjectName = &v6;
    v4 = SecurityDescriptor;
    ObjectAttributes.SecurityDescriptor = SecurityDescriptor;
    ObjectAttributes.SecurityQualityOfService = 0;
    v3 = ZwCreateKey(&KeyHandle, 0xF003Fu, &ObjectAttributes, 0, 0, 0, &Disposition);
    if ( v3 >= 0 )
    {
      if ( Disposition != 2 || (v3 = ZwSetSecurityObject(KeyHandle, 0xFu, v4), v3 >= 0) )
        v3 = 0;
    }
  }
  if ( KeyHandle )
  {
    ZwClose(KeyHandle);
    KeyHandle = 0;
  }
  if ( SecurityDescriptor )
    ExFreePoolWithTag(SecurityDescriptor, 0);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14004ddb4  mov     rax, rsp
0x14004ddb7  mov     [rax+8], rbx
0x14004ddbb  push    rdi
0x14004ddbc  sub     rsp, 80h
0x14004ddc3  mov     rdi, rcx
0x14004ddc6  mov     qword ptr [rax+18h], 0
0x14004ddce  xorps   xmm0, xmm0
0x14004ddd1  movups  xmmword ptr [rax-38h], xmm0
0x14004ddd5  movups  xmmword ptr [rax-28h], xmm0
0x14004ddd9  movups  xmmword ptr [rax-18h], xmm0
0x14004dddd  movups  xmmword ptr [rax-48h], xmm0
0x14004dde1  mov     qword ptr [rax+20h], 0
0x14004dde9  mov     dword ptr [rax+10h], 0
0x14004ddf0  lea     rdx, aExemptions; "Exemptions"
0x14004ddf7  lea     rcx, [rax-48h]; DestinationString
0x14004ddfb  call    cs:__imp_RtlInitUnicodeString
0x14004de02  nop     dword ptr [rax+rax+00h]
0x14004de07  nop
0x14004de08  lea     rdx, [rsp+88h+SecurityDescriptor]
0x14004de10  call    ClfsCreateAuthRegistrySecurityDescriptor
0x14004de15  mov     ebx, eax
0x14004de17  test    eax, eax
0x14004de19  js      loc_14004DECA
0x14004de1f  mov     [rsp+88h+ObjectAttributes.Length], 30h ; '0'
0x14004de27  mov     rax, [rdi]
0x14004de2a  mov     [rsp+88h+ObjectAttributes.RootDirectory], rax
0x14004de2f  mov     [rsp+88h+ObjectAttributes.Attributes], 240h
0x14004de37  lea     rax, [rsp+88h+var_48]
0x14004de3c  mov     [rsp+88h+ObjectAttributes.ObjectName], rax
0x14004de41  mov     rdi, [rsp+88h+SecurityDescriptor]
0x14004de49  mov     [rsp+88h+ObjectAttributes.SecurityDescriptor], rdi
0x14004de4e  mov     [rsp+88h+ObjectAttributes.SecurityQualityOfService], 0
0x14004de57  lea     rax, [rsp+88h+arg_8]
0x14004de5f  mov     [rsp+88h+Disposition], rax; Disposition
0x14004de64  mov     [rsp+88h+CreateOptions], 0; CreateOptions
0x14004de6c  mov     [rsp+88h+Class], 0; Class
0x14004de75  xor     r9d, r9d; TitleIndex
0x14004de78  lea     r8, [rsp+88h+ObjectAttributes]; ObjectAttributes
0x14004de7d  mov     edx, 0F003Fh; DesiredAccess
0x14004de82  lea     rcx, [rsp+88h+KeyHandle]; KeyHandle
0x14004de8a  call    cs:__imp_ZwCreateKey
0x14004de91  nop     dword ptr [rax+rax+00h]
0x14004de96  mov     ebx, eax
0x14004de98  test    eax, eax
0x14004de9a  js      short loc_14004DECA
0x14004de9c  cmp     [rsp+88h+arg_8], 2
0x14004dea4  jnz     short loc_14004DEC8
0x14004dea6  mov     r8, rdi; SecurityDescriptor
0x14004dea9  mov     edx, 0Fh; SecurityInformation
0x14004deae  mov     rcx, [rsp+88h+KeyHandle]; Handle
0x14004deb6  call    cs:__imp_ZwSetSecurityObject
0x14004debd  nop     dword ptr [rax+rax+00h]
0x14004dec2  mov     ebx, eax
0x14004dec4  test    eax, eax
0x14004dec6  js      short loc_14004DECA
0x14004dec8  xor     ebx, ebx
0x14004deca  mov     rcx, [rsp+88h+KeyHandle]; Handle
0x14004ded2  test    rcx, rcx
0x14004ded5  jz      short loc_14004DEEF
0x14004ded7  call    cs:__imp_ZwClose
0x14004dede  nop     dword ptr [rax+rax+00h]
0x14004dee3  mov     [rsp+88h+KeyHandle], 0
0x14004deef  mov     rdi, [rsp+88h+SecurityDescriptor]
0x14004def7  test    rdi, rdi
0x14004defa  jz      short loc_14004DF0D
0x14004defc  xor     edx, edx; Tag
0x14004defe  mov     rcx, rdi; P
0x14004df01  call    cs:__imp_ExFreePoolWithTag
0x14004df08  nop     dword ptr [rax+rax+00h]
0x14004df0d  mov     eax, ebx
0x14004df0f  mov     rbx, [rsp+88h+arg_0]
0x14004df17  add     rsp, 80h
0x14004df1e  pop     rdi
0x14004df1f  retn
0x140080723  push    rbp
0x140080725  sub     rsp, 40h
0x140080729  mov     rbp, rdx
0x14008072c  mov     rcx, [rbp+0A0h]; Handle
0x140080733  test    rcx, rcx
0x140080736  jz      short loc_14008074F
0x140080738  call    cs:__imp_ZwClose
0x14008073f  nop     dword ptr [rax+rax+00h]
0x140080744  mov     qword ptr [rbp+0A0h], 0
0x14008074f  mov     rcx, [rbp+0A8h]; P
0x140080756  test    rcx, rcx
0x140080759  jz      short loc_14008076A
0x14008075b  xor     edx, edx; Tag
0x14008075d  call    cs:__imp_ExFreePoolWithTag
0x140080764  nop     dword ptr [rax+rax+00h]
0x140080769  nop
0x14008076a  add     rsp, 40h
0x14008076e  pop     rbp
0x14008076f  retn
```
