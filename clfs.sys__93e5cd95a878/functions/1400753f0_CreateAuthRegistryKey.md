# CreateAuthRegistryKey

- ea: `0x1400753f0`
- end: `0x140075626`
- name: `CreateAuthRegistryKey`
- size: `566`
- prototype: `__int64 __fastcall(PHANDLE KeyHandle)`
- caller_count: `4`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1400320b8`
- `0x14003d11c`
- `0x14004d968`
- `0x14004e294`

## callees

- `0x140071e8c`
- `0x1400753f0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1400755bd`
- `ntoskrnl!ZwClose` at `0x1400755fc`
- `ntoskrnl!ZwClose` at `0x14007c4ff`
- `ntoskrnl!ZwClose` at `0x14007c544`
- `ntoskrnl!ZwClose` at `0x1400755bd`
- `ntoskrnl!ZwClose` at `0x1400755fc`
- `ntoskrnl!ZwClose` at `0x14007c4ff`
- `ntoskrnl!ZwClose` at `0x14007c544`
- `ntoskrnl!ZwOpenKey` at `0x1400754c2`
- `ntoskrnl!ZwOpenKey` at `0x1400754c2`
- `ntoskrnl!ZwCreateKey` at `0x140075564`
- `ntoskrnl!ZwCreateKey` at `0x140075564`
- `ntoskrnl!ZwSetSecurityObject` at `0x140075594`
- `ntoskrnl!ZwSetSecurityObject` at `0x140075594`
- `ntoskrnl!RtlInitUnicodeString` at `0x14007544f`
- `ntoskrnl!RtlInitUnicodeString` at `0x140075467`
- `ntoskrnl!RtlInitUnicodeString` at `0x14007544f`
- `ntoskrnl!RtlInitUnicodeString` at `0x140075467`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400755e4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007c521`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400755e4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007c521`

## string_xrefs

- `0x140075444`: `\Registry\Machine\System\CurrentControlSet\Services\CLFS`

## pseudocode

```c
__int64 __fastcall CreateAuthRegistryKey(PHANDLE KeyHandle, char a2)
{
  __int64 v4; // rcx
  int v5; // ebx
  PSECURITY_DESCRIPTOR v6; // rdi
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+48h] [rbp-70h] BYREF
  UNICODE_STRING v9; // [rsp+50h] [rbp-68h] BYREF
  UNICODE_STRING DestinationString; // [rsp+60h] [rbp-58h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-48h] BYREF
  ULONG Disposition; // [rsp+D0h] [rbp+18h] BYREF
  void *KeyHandlea; // [rsp+D8h] [rbp+20h] BYREF

  KeyHandlea = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v9 = 0;
  DestinationString = 0;
  SecurityDescriptor = 0;
  Disposition = 0;
  RtlInitUnicodeString(&v9, L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\CLFS");
  RtlInitUnicodeString(&DestinationString, L"Authentication");
  *KeyHandle = 0;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = &v9;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v5 = ZwOpenKey(&KeyHandlea, 0x20006u, &ObjectAttributes);
  if ( v5 >= 0 )
  {
    v5 = ClfsCreateAuthRegistrySecurityDescriptor(v4, &SecurityDescriptor);
    if ( v5 >= 0 )
    {
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = KeyHandlea;
      ObjectAttributes.Attributes = 576;
      ObjectAttributes.ObjectName = &DestinationString;
      v6 = SecurityDescriptor;
      ObjectAttributes.SecurityDescriptor = SecurityDescriptor;
      ObjectAttributes.SecurityQualityOfService = 0;
      v5 = ZwCreateKey(KeyHandle, 0xF003Fu, &ObjectAttributes, 0, 0, 0, &Disposition);
      if ( v5 >= 0 )
      {
        if ( Disposition != 2 || !a2 || (v5 = ZwSetSecurityObject(*KeyHandle, 0xFu, v6), v5 >= 0) )
          v5 = 0;
      }
    }
  }
  if ( KeyHandlea )
  {
    ZwClose(KeyHandlea);
    KeyHandlea = 0;
  }
  if ( SecurityDescriptor )
    ExFreePoolWithTag(SecurityDescriptor, 0);
  if ( v5 < 0 && *KeyHandle )
  {
    ZwClose(*KeyHandle);
    *KeyHandle = 0;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1400753f0  mov     rax, rsp
0x1400753f3  mov     [rax+10h], rbx
0x1400753f7  mov     [rax+8], rcx
0x1400753fb  push    rsi
0x1400753fc  push    rdi
0x1400753fd  push    r14
0x1400753ff  sub     rsp, 0A0h
0x140075406  mov     r14b, dl
0x140075409  mov     rsi, rcx
0x14007540c  mov     dword ptr [rax-78h], 0
0x140075413  mov     qword ptr [rax+20h], 0
0x14007541b  xorps   xmm0, xmm0
0x14007541e  movups  xmmword ptr [rax-48h], xmm0
0x140075422  movups  xmmword ptr [rax-38h], xmm0
0x140075426  movups  xmmword ptr [rax-28h], xmm0
0x14007542a  movups  xmmword ptr [rax-68h], xmm0
0x14007542e  xorps   xmm1, xmm1
0x140075431  movups  xmmword ptr [rax-58h], xmm1
0x140075435  mov     qword ptr [rax-70h], 0
0x14007543d  mov     dword ptr [rax+18h], 0
0x140075444  lea     rdx, aRegistryMachin_0; "\\Registry\\Machine\\System\\CurrentCon"...
0x14007544b  lea     rcx, [rax-68h]; DestinationString
0x14007544f  call    cs:__imp_RtlInitUnicodeString
0x140075456  nop     dword ptr [rax+rax+00h]
0x14007545b  lea     rdx, aAuthentication; "Authentication"
0x140075462  lea     rcx, [rsp+0B8h+DestinationString]; DestinationString
0x140075467  call    cs:__imp_RtlInitUnicodeString
0x14007546e  nop     dword ptr [rax+rax+00h]
0x140075473  mov     qword ptr [rsi], 0
0x14007547a  mov     edi, 30h ; '0'
0x14007547f  mov     [rsp+0B8h+ObjectAttributes.Length], edi
0x140075483  mov     [rsp+0B8h+ObjectAttributes.RootDirectory], 0
0x14007548c  mov     [rsp+0B8h+ObjectAttributes.Attributes], 240h
0x140075497  lea     rax, [rsp+0B8h+var_68]
0x14007549c  mov     [rsp+0B8h+ObjectAttributes.ObjectName], rax
0x1400754a4  xorps   xmm0, xmm0
0x1400754a7  movdqu  xmmword ptr [rsp+0B8h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400754b0  lea     r8, [rsp+0B8h+ObjectAttributes]; ObjectAttributes
0x1400754b5  mov     edx, 20006h; DesiredAccess
0x1400754ba  lea     rcx, [rsp+0B8h+KeyHandle]; KeyHandle
0x1400754c2  call    cs:__imp_ZwOpenKey
0x1400754c9  nop     dword ptr [rax+rax+00h]
0x1400754ce  mov     ebx, eax
0x1400754d0  mov     [rsp+0B8h+var_78], eax
0x1400754d4  test    eax, eax
0x1400754d6  js      loc_1400755B0
0x1400754dc  lea     rdx, [rsp+0B8h+SecurityDescriptor]
0x1400754e1  call    ClfsCreateAuthRegistrySecurityDescriptor
0x1400754e6  mov     ebx, eax
0x1400754e8  mov     [rsp+0B8h+var_78], eax
0x1400754ec  test    eax, eax
0x1400754ee  js      loc_1400755B0
0x1400754f4  mov     [rsp+0B8h+ObjectAttributes.Length], edi
0x1400754f8  mov     rax, [rsp+0B8h+KeyHandle]
0x140075500  mov     [rsp+0B8h+ObjectAttributes.RootDirectory], rax
0x140075505  mov     [rsp+0B8h+ObjectAttributes.Attributes], 240h
0x140075510  lea     rax, [rsp+0B8h+DestinationString]
0x140075515  mov     [rsp+0B8h+ObjectAttributes.ObjectName], rax
0x14007551d  mov     rdi, [rsp+0B8h+SecurityDescriptor]
0x140075522  mov     [rsp+0B8h+ObjectAttributes.SecurityDescriptor], rdi
0x14007552a  mov     [rsp+0B8h+ObjectAttributes.SecurityQualityOfService], 0
0x140075536  lea     rax, [rsp+0B8h+arg_10]
0x14007553e  mov     [rsp+0B8h+Disposition], rax; Disposition
0x140075543  mov     [rsp+0B8h+CreateOptions], 0; CreateOptions
0x14007554b  mov     [rsp+0B8h+Class], 0; Class
0x140075554  xor     r9d, r9d; TitleIndex
0x140075557  lea     r8, [rsp+0B8h+ObjectAttributes]; ObjectAttributes
0x14007555c  mov     edx, 0F003Fh; DesiredAccess
0x140075561  mov     rcx, rsi; KeyHandle
0x140075564  call    cs:__imp_ZwCreateKey
0x14007556b  nop     dword ptr [rax+rax+00h]
0x140075570  mov     ebx, eax
0x140075572  mov     [rsp+0B8h+var_78], eax
0x140075576  test    eax, eax
0x140075578  js      short loc_1400755B0
0x14007557a  cmp     [rsp+0B8h+arg_10], 2
0x140075582  jnz     short loc_1400755AA
0x140075584  test    r14b, r14b
0x140075587  jz      short loc_1400755AA
0x140075589  mov     r8, rdi; SecurityDescriptor
0x14007558c  mov     edx, 0Fh; SecurityInformation
0x140075591  mov     rcx, [rsi]; Handle
0x140075594  call    cs:__imp_ZwSetSecurityObject
0x14007559b  nop     dword ptr [rax+rax+00h]
0x1400755a0  mov     ebx, eax
0x1400755a2  mov     [rsp+0B8h+var_78], eax
0x1400755a6  test    eax, eax
0x1400755a8  js      short loc_1400755B0
0x1400755aa  xor     ebx, ebx
0x1400755ac  mov     [rsp+0B8h+var_78], ebx
0x1400755b0  mov     rcx, [rsp+0B8h+KeyHandle]; Handle
0x1400755b8  test    rcx, rcx
0x1400755bb  jz      short loc_1400755D5
0x1400755bd  call    cs:__imp_ZwClose
0x1400755c4  nop     dword ptr [rax+rax+00h]
0x1400755c9  mov     [rsp+0B8h+KeyHandle], 0
0x1400755d5  mov     rdi, [rsp+0B8h+SecurityDescriptor]
0x1400755da  test    rdi, rdi
0x1400755dd  jz      short loc_1400755F0
0x1400755df  xor     edx, edx; Tag
0x1400755e1  mov     rcx, rdi; P
0x1400755e4  call    cs:__imp_ExFreePoolWithTag
0x1400755eb  nop     dword ptr [rax+rax+00h]
0x1400755f0  test    ebx, ebx
0x1400755f2  jns     short loc_14007560F
0x1400755f4  mov     rcx, [rsi]; Handle
0x1400755f7  test    rcx, rcx
0x1400755fa  jz      short loc_14007560F
0x1400755fc  call    cs:__imp_ZwClose
0x140075603  nop     dword ptr [rax+rax+00h]
0x140075608  mov     qword ptr [rsi], 0
0x14007560f  mov     eax, ebx
0x140075611  mov     rbx, [rsp+0B8h+arg_8]
0x140075619  add     rsp, 0A0h
0x140075620  pop     r14
0x140075622  pop     rdi
0x140075623  pop     rsi
0x140075624  retn
0x14007c4e9  push    rbx
0x14007c4eb  push    rbp
0x14007c4ec  sub     rsp, 48h
0x14007c4f0  mov     rbp, rdx
0x14007c4f3  mov     rcx, [rbp+0D8h]; Handle
0x14007c4fa  test    rcx, rcx
0x14007c4fd  jz      short loc_14007C516
0x14007c4ff  call    cs:__imp_ZwClose
0x14007c506  nop     dword ptr [rax+rax+00h]
0x14007c50b  mov     qword ptr [rbp+0D8h], 0
0x14007c516  mov     rcx, [rbp+48h]; P
0x14007c51a  test    rcx, rcx
0x14007c51d  jz      short loc_14007C52E
0x14007c51f  xor     edx, edx; Tag
0x14007c521  call    cs:__imp_ExFreePoolWithTag
0x14007c528  nop     dword ptr [rax+rax+00h]
0x14007c52d  nop
0x14007c52e  cmp     dword ptr [rbp+40h], 0
0x14007c532  jge     short loc_14007C557
0x14007c534  mov     rbx, [rbp+0C0h]
0x14007c53b  cmp     qword ptr [rbx], 0
0x14007c53f  jz      short loc_14007C557
0x14007c541  mov     rcx, [rbx]; Handle
0x14007c544  call    cs:__imp_ZwClose
0x14007c54b  nop     dword ptr [rax+rax+00h]
0x14007c550  mov     qword ptr [rbx], 0
0x14007c557  add     rsp, 48h
0x14007c55b  pop     rbp
0x14007c55c  pop     rbx
0x14007c55d  retn
```
