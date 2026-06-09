# HsmiOsOpenAppPolicyKey

- ea: `0x140014200`
- end: `0x140014719`
- name: `HsmiOsOpenAppPolicyKey`
- size: `1305`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, const WCHAR *, char, char, _QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140007944`
- `0x1400126ec`

## callees

- `0x140013818`
- `0x140014200`

## import_xrefs

- `ntoskrnl!ZwOpenThreadTokenEx` at `0x1400144d7`
- `ntoskrnl!ZwOpenThreadTokenEx` at `0x1400144d7`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x1400144fb`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x1400144fb`
- `ntoskrnl!ZwCreateKey` at `0x140014389`
- `ntoskrnl!ZwCreateKey` at `0x14001440e`
- `ntoskrnl!ZwCreateKey` at `0x14001462f`
- `ntoskrnl!ZwCreateKey` at `0x140014389`
- `ntoskrnl!ZwCreateKey` at `0x14001440e`
- `ntoskrnl!ZwCreateKey` at `0x14001462f`
- `ntoskrnl!ZwQueryInformationToken` at `0x140014536`
- `ntoskrnl!ZwQueryInformationToken` at `0x140014536`
- `ntoskrnl!RtlOpenCurrentUser` at `0x14001427e`
- `ntoskrnl!RtlOpenCurrentUser` at `0x14001427e`
- `ntoskrnl!ZwOpenKey` at `0x1400142fb`
- `ntoskrnl!ZwOpenKey` at `0x140014348`
- `ntoskrnl!ZwOpenKey` at `0x1400143cd`
- `ntoskrnl!ZwOpenKey` at `0x14001446b`
- `ntoskrnl!ZwOpenKey` at `0x1400142fb`
- `ntoskrnl!ZwOpenKey` at `0x140014348`
- `ntoskrnl!ZwOpenKey` at `0x1400143cd`
- `ntoskrnl!ZwOpenKey` at `0x14001446b`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400145a1`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400145a1`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1400145c8`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1400145c8`
- `ntoskrnl!ZwClose` at `0x140014695`
- `ntoskrnl!ZwClose` at `0x1400146ab`
- `ntoskrnl!ZwClose` at `0x1400146c1`
- `ntoskrnl!ZwClose` at `0x1400146d7`
- `ntoskrnl!ZwClose` at `0x1400146ed`
- `ntoskrnl!ZwClose` at `0x140014695`
- `ntoskrnl!ZwClose` at `0x1400146ab`
- `ntoskrnl!ZwClose` at `0x1400146c1`
- `ntoskrnl!ZwClose` at `0x1400146d7`
- `ntoskrnl!ZwClose` at `0x1400146ed`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001442d`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001442d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014666`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001467f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014666`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001467f`
- `ntoskrnl!ExAllocatePool2` at `0x14001455a`
- `ntoskrnl!ExAllocatePool2` at `0x14001455a`

## string_xrefs

- `0x1400142b5`: `\Registry\Machine`

## pseudocode

```c
__int64 __fastcall HsmiOsOpenAppPolicyKey(struct _UNICODE_STRING *a1, const WCHAR *a2, char a3, char a4, _QWORD *a5)
{
  PACL v8; // r14
  NTSTATUS v9; // eax
  ULONG v10; // r12d
  ACCESS_MASK v11; // edi
  NTSTATUS v12; // ebx
  PSID *Pool2; // rsi
  int i; // ebx
  HANDLE v15; // rax
  ULONG Disposition; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE Handle; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE v19; // [rsp+50h] [rbp-B0h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE v21; // [rsp+60h] [rbp-A0h] BYREF
  void *KeyHandle; // [rsp+68h] [rbp-98h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-90h] BYREF
  PACL Dacl; // [rsp+A0h] [rbp-60h]
  _QWORD v25[2]; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v26[2]; // [rsp+B8h] [rbp-48h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+C8h] [rbp-38h] BYREF
  struct _OBJECT_ATTRIBUTES v28; // [rsp+D8h] [rbp-28h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+108h] [rbp+8h] BYREF
  __int64 v30; // [rsp+128h] [rbp+28h]
  ULONG ReturnLength; // [rsp+190h] [rbp+90h] BYREF

  v26[0] = 5111884;
  v26[1] = L"SOFTWARE\\Policies\\Microsoft\\CloudFiles";
  Disposition = 0;
  KeyHandle = 0;
  v21 = 0;
  v8 = 0;
  v19 = 0;
  Handle = 0;
  TokenHandle = 0;
  Dacl = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  if ( a3 )
  {
    v9 = RtlOpenCurrentUser(0x20019u, &KeyHandle);
    v10 = a4 != 0 ? 576 : 1600;
    v11 = a4 != 0 ? 983103 : 131097;
  }
  else
  {
    ObjectAttributes.RootDirectory = 0;
    v25[1] = L"\\Registry\\Machine";
    v25[0] = 2359330;
    v10 = 576;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)v25;
    ObjectAttributes.Length = 48;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v9 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
    v11 = 983103;
  }
  v12 = v9;
  if ( v9 < 0 )
    goto LABEL_35;
  ObjectAttributes.RootDirectory = KeyHandle;
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v26;
  ObjectAttributes.Attributes = v10;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v12 = ZwOpenKey(&v21, v11, &ObjectAttributes);
  if ( v12 == -1073741772 )
  {
    if ( !a4 )
      goto LABEL_23;
    v12 = ZwCreateKey(&v21, v11, &ObjectAttributes, 0, 0, 0, &Disposition);
  }
  if ( v12 < 0 )
    goto LABEL_35;
  ObjectAttributes.RootDirectory = v21;
  ObjectAttributes.Length = 48;
  ObjectAttributes.Attributes = v10;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  ObjectAttributes.ObjectName = a1;
  v12 = ZwOpenKey(&v19, v11, &ObjectAttributes);
  if ( v12 == -1073741772 )
  {
    if ( !a4 )
      goto LABEL_23;
    v12 = ZwCreateKey(&v19, v11, &ObjectAttributes, 0, 0, 0, &Disposition);
  }
  if ( v12 < 0 )
    goto LABEL_35;
  Pool2 = 0;
  RtlInitUnicodeString(&DestinationString, a2);
  ObjectAttributes.RootDirectory = v19;
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Attributes = v10;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v12 = ZwOpenKey(&Handle, v11, &ObjectAttributes);
  if ( v12 != -1073741772 )
    goto LABEL_29;
  if ( !a4 )
  {
LABEL_23:
    v12 = 0;
    goto LABEL_35;
  }
  ReturnLength = 0;
  v30 = 0;
  memset(&v28, 0, 44);
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  v12 = ZwOpenThreadTokenEx((HANDLE)0xFFFFFFFFFFFFFFFELL, 0x20008u, 1u, 0x200u, &TokenHandle);
  if ( v12 == -1073741700 )
    v12 = ZwOpenProcessTokenEx((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0x20008u, 0x200u, &TokenHandle);
  if ( v12 >= 0 )
  {
    for ( i = 0; i < 2; ++i )
    {
      if ( ZwQueryInformationToken(TokenHandle, TokenUser, Pool2, ReturnLength, &ReturnLength) == -1073741789 )
      {
        Pool2 = (PSID *)ExAllocatePool2(256, ReturnLength, 1802466376);
        if ( !Pool2 )
        {
          v12 = -1073741670;
          goto LABEL_35;
        }
      }
    }
    v12 = HsmiOsBuildAppPolicyKeyAcl(*Pool2);
    if ( v12 < 0 || (v12 = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u), v12 < 0) )
    {
      v8 = Dacl;
    }
    else
    {
      v8 = Dacl;
      v12 = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, Dacl, 0);
      if ( v12 >= 0 )
      {
        v28.RootDirectory = v19;
        v28.Length = 48;
        v28.ObjectName = &DestinationString;
        v28.Attributes = v10;
        v28.SecurityDescriptor = SecurityDescriptor;
        v28.SecurityQualityOfService = 0;
        v12 = ZwCreateKey(&Handle, v11, &v28, 0, 0, 0, &Disposition);
LABEL_29:
        if ( v12 >= 0 )
        {
          v15 = Handle;
          Handle = 0;
          *a5 = v15;
        }
      }
    }
    if ( v8 )
      ExFreePoolWithTag(v8, 0x636C6148u);
    if ( Pool2 )
      ExFreePoolWithTag(Pool2, 0x6B6F7448u);
  }
LABEL_35:
  if ( TokenHandle )
    ZwClose(TokenHandle);
  if ( Handle )
    ZwClose(Handle);
  if ( v19 )
    ZwClose(v19);
  if ( v21 )
    ZwClose(v21);
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140014200  push    rbp
0x140014202  push    rbx
0x140014203  push    rsi
0x140014204  push    rdi
0x140014205  push    r12
0x140014207  push    r13
0x140014209  push    r14
0x14001420b  push    r15
0x14001420d  lea     rbp, [rsp-38h]
0x140014212  sub     rsp, 138h
0x140014219  xorps   xmm0, xmm0
0x14001421c  mov     [rbp+70h+var_B8], 4E004Ch
0x140014224  mov     rsi, rcx
0x140014227  lea     rax, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\CloudFil"...
0x14001422e  xor     ecx, ecx
0x140014230  mov     [rbp+70h+var_B0], rax
0x140014234  mov     [rsp+170h+var_130], ecx
0x140014238  mov     r15b, r9b
0x14001423b  mov     [rsp+170h+KeyHandle], rcx
0x140014240  mov     r13, rdx
0x140014243  mov     [rsp+170h+var_110], rcx
0x140014248  mov     r14d, ecx
0x14001424b  mov     [rsp+170h+var_120], rcx
0x140014250  mov     [rsp+170h+Handle], rcx
0x140014255  mov     [rsp+170h+TokenHandle], rcx
0x14001425a  mov     [rbp+70h+Dacl], rcx
0x14001425e  movups  xmmword ptr [rsp+170h+ObjectAttributes.Length], xmm0
0x140014263  movups  xmmword ptr [rbp+70h+ObjectAttributes.ObjectName], xmm0
0x140014267  movups  xmmword ptr [rbp+70h+ObjectAttributes.SecurityDescriptor], xmm0
0x14001426b  movups  xmmword ptr [rbp+70h+DestinationString.Length], xmm0
0x14001426f  test    r8b, r8b
0x140014272  jz      short loc_1400142B5
0x140014274  lea     rdx, [rsp+170h+KeyHandle]; KeyHandle
0x140014279  mov     ecx, 20019h; DesiredAccess
0x14001427e  call    cs:__imp_RtlOpenCurrentUser
0x140014285  nop     dword ptr [rax+rax+00h]
0x14001428a  mov     cl, r15b
0x14001428d  neg     cl
0x14001428f  mov     cl, r15b
0x140014292  sbb     r12d, r12d
0x140014295  and     r12d, 0FFFFFC00h
0x14001429c  add     r12d, 640h
0x1400142a3  neg     cl
0x1400142a5  sbb     edi, edi
0x1400142a7  and     edi, 0D0026h
0x1400142ad  add     edi, 20019h
0x1400142b3  jmp     short loc_14001430C
0x1400142b5  lea     rax, aRegistryMachin_1; "\\Registry\\Machine"
0x1400142bc  mov     [rsp+170h+ObjectAttributes.RootDirectory], rcx
0x1400142c1  mov     [rbp+70h+var_C0], rax
0x1400142c5  lea     r8, [rsp+170h+ObjectAttributes]; ObjectAttributes
0x1400142ca  lea     rax, [rbp+70h+var_C8]
0x1400142ce  mov     [rbp+70h+var_C8], 240022h
0x1400142d6  mov     r12d, 240h
0x1400142dc  mov     [rbp+70h+ObjectAttributes.ObjectName], rax
0x1400142e0  mov     edx, 20019h; DesiredAccess
0x1400142e5  mov     [rsp+170h+ObjectAttributes.Length], 30h ; '0'
0x1400142ed  lea     rcx, [rsp+170h+KeyHandle]; KeyHandle
0x1400142f2  mov     [rbp+70h+ObjectAttributes.Attributes], r12d
0x1400142f6  movdqu  xmmword ptr [rbp+70h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400142fb  call    cs:__imp_ZwOpenKey
0x140014302  nop     dword ptr [rax+rax+00h]
0x140014307  mov     edi, 0F003Fh
0x14001430c  mov     ebx, eax
0x14001430e  test    eax, eax
0x140014310  js      loc_14001468B
0x140014316  mov     rax, [rsp+170h+KeyHandle]
0x14001431b  lea     r8, [rsp+170h+ObjectAttributes]; ObjectAttributes
0x140014320  mov     [rsp+170h+ObjectAttributes.RootDirectory], rax
0x140014325  lea     rcx, [rsp+170h+var_110]; KeyHandle
0x14001432a  lea     rax, [rbp+70h+var_B8]
0x14001432e  mov     [rsp+170h+ObjectAttributes.Length], 30h ; '0'
0x140014336  xorps   xmm0, xmm0
0x140014339  mov     [rbp+70h+ObjectAttributes.ObjectName], rax
0x14001433d  mov     edx, edi; DesiredAccess
0x14001433f  mov     [rbp+70h+ObjectAttributes.Attributes], r12d
0x140014343  movdqu  xmmword ptr [rbp+70h+ObjectAttributes.SecurityDescriptor], xmm0
0x140014348  call    cs:__imp_ZwOpenKey
0x14001434f  nop     dword ptr [rax+rax+00h]
0x140014354  mov     ebx, eax
0x140014356  cmp     eax, 0C0000034h
0x14001435b  jnz     short loc_140014397
0x14001435d  test    r15b, r15b
0x140014360  jz      loc_140014573
0x140014366  lea     rax, [rsp+170h+var_130]
0x14001436b  xor     r9d, r9d; TitleIndex
0x14001436e  mov     [rsp+170h+Disposition], rax; Disposition
0x140014373  lea     r8, [rsp+170h+ObjectAttributes]; ObjectAttributes
0x140014378  mov     [rsp+170h+CreateOptions], r14d; CreateOptions
0x14001437d  lea     rcx, [rsp+170h+var_110]; KeyHandle
0x140014382  mov     edx, edi; DesiredAccess
0x140014384  mov     [rsp+170h+Class], r14; Class
0x140014389  call    cs:__imp_ZwCreateKey
0x140014390  nop     dword ptr [rax+rax+00h]
0x140014395  mov     ebx, eax
0x140014397  test    ebx, ebx
0x140014399  js      loc_14001468B
0x14001439f  mov     rax, [rsp+170h+var_110]
0x1400143a4  lea     r8, [rsp+170h+ObjectAttributes]; ObjectAttributes
0x1400143a9  xorps   xmm0, xmm0
0x1400143ac  mov     [rsp+170h+ObjectAttributes.RootDirectory], rax
0x1400143b1  mov     edx, edi; DesiredAccess
0x1400143b3  mov     [rsp+170h+ObjectAttributes.Length], 30h ; '0'
0x1400143bb  lea     rcx, [rsp+170h+var_120]; KeyHandle
0x1400143c0  mov     [rbp+70h+ObjectAttributes.Attributes], r12d
0x1400143c4  movdqu  xmmword ptr [rbp+70h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400143c9  mov     [rbp+70h+ObjectAttributes.ObjectName], rsi
0x1400143cd  call    cs:__imp_ZwOpenKey
0x1400143d4  nop     dword ptr [rax+rax+00h]
0x1400143d9  mov     ebx, eax
0x1400143db  cmp     eax, 0C0000034h
0x1400143e0  jnz     short loc_14001441C
0x1400143e2  test    r15b, r15b
0x1400143e5  jz      loc_140014573
0x1400143eb  lea     rax, [rsp+170h+var_130]
0x1400143f0  xor     r9d, r9d; TitleIndex
0x1400143f3  mov     [rsp+170h+Disposition], rax; Disposition
0x1400143f8  lea     r8, [rsp+170h+ObjectAttributes]; ObjectAttributes
0x1400143fd  mov     [rsp+170h+CreateOptions], r14d; CreateOptions
0x140014402  lea     rcx, [rsp+170h+var_120]; KeyHandle
0x140014407  mov     edx, edi; DesiredAccess
0x140014409  mov     [rsp+170h+Class], r14; Class
0x14001440e  call    cs:__imp_ZwCreateKey
0x140014415  nop     dword ptr [rax+rax+00h]
0x14001441a  mov     ebx, eax
0x14001441c  test    ebx, ebx
0x14001441e  js      loc_14001468B
0x140014424  mov     rdx, r13; SourceString
0x140014427  lea     rcx, [rbp+70h+DestinationString]; DestinationString
0x14001442b  xor     esi, esi
0x14001442d  call    cs:__imp_RtlInitUnicodeString
0x140014434  nop     dword ptr [rax+rax+00h]
0x140014439  mov     rax, [rsp+170h+var_120]
0x14001443e  lea     r8, [rsp+170h+ObjectAttributes]; ObjectAttributes
0x140014443  mov     [rsp+170h+ObjectAttributes.RootDirectory], rax
0x140014448  lea     rcx, [rsp+170h+Handle]; KeyHandle
0x14001444d  lea     rax, [rbp+70h+DestinationString]
0x140014451  mov     [rsp+170h+ObjectAttributes.Length], 30h ; '0'
0x140014459  xorps   xmm0, xmm0
0x14001445c  mov     [rbp+70h+ObjectAttributes.ObjectName], rax
0x140014460  mov     edx, edi; DesiredAccess
0x140014462  mov     [rbp+70h+ObjectAttributes.Attributes], r12d
0x140014466  movdqu  xmmword ptr [rbp+70h+ObjectAttributes.SecurityDescriptor], xmm0
0x14001446b  call    cs:__imp_ZwOpenKey
0x140014472  nop     dword ptr [rax+rax+00h]
0x140014477  mov     ebx, eax
0x140014479  cmp     eax, 0C0000034h
0x14001447e  jnz     loc_14001463D
0x140014484  test    r15b, r15b
0x140014487  jz      loc_140014573
0x14001448d  xorps   xmm0, xmm0
0x140014490  lea     r15d, [rsi+1]
0x140014494  xor     eax, eax
0x140014496  lea     rcx, [rsi-2]; ThreadHandle
0x14001449a  mov     [rbp+70h+ReturnLength], eax
0x1400144a0  mov     r14d, 200h
0x1400144a6  mov     [rbp+70h+var_48], rax
0x1400144aa  mov     r13d, 20008h
0x1400144b0  lea     rax, [rsp+170h+TokenHandle]
0x1400144b5  mov     r9d, r14d; HandleAttributes
0x1400144b8  movups  xmmword ptr [rbp+70h+var_98.ObjectName], xmm0
0x1400144bc  mov     r8b, r15b; OpenAsSelf
0x1400144bf  mov     [rsp+170h+Class], rax; TokenHandle
0x1400144c4  mov     edx, r13d; DesiredAccess
0x1400144c7  movups  xmmword ptr [rbp+70h+var_98.Length], xmm0
0x1400144cb  movups  xmmword ptr [rbp+70h+var_98+1Ch], xmm0
0x1400144cf  movups  [rbp+70h+SecurityDescriptor], xmm0
0x1400144d3  movups  [rbp+70h+var_58], xmm0
0x1400144d7  call    cs:__imp_ZwOpenThreadTokenEx
0x1400144de  nop     dword ptr [rax+rax+00h]
0x1400144e3  mov     ebx, eax
0x1400144e5  cmp     eax, 0C000007Ch
0x1400144ea  jnz     short loc_140014509
0x1400144ec  lea     r9, [rsp+170h+TokenHandle]; TokenHandle
0x1400144f1  mov     r8d, r14d; HandleAttributes
0x1400144f4  mov     edx, r13d; DesiredAccess
0x1400144f7  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1400144fb  call    cs:__imp_ZwOpenProcessTokenEx
0x140014502  nop     dword ptr [rax+rax+00h]
0x140014507  mov     ebx, eax
0x140014509  test    ebx, ebx
0x14001450b  js      loc_14001468B
0x140014511  xor     ebx, ebx
0x140014513  cmp     ebx, 2
0x140014516  jge     short loc_140014584
0x140014518  mov     r9d, [rbp+70h+ReturnLength]; TokenInformationLength
0x14001451f  lea     rax, [rbp+70h+ReturnLength]
0x140014526  mov     rcx, [rsp+170h+TokenHandle]; TokenHandle
0x14001452b  mov     r8, rsi; TokenInformation
0x14001452e  mov     edx, r15d; TokenInformationClass
0x140014531  mov     [rsp+170h+Class], rax; ReturnLength
0x140014536  call    cs:__imp_ZwQueryInformationToken
0x14001453d  nop     dword ptr [rax+rax+00h]
0x140014542  cmp     eax, 0C0000023h
0x140014547  jnz     short loc_14001456E
0x140014549  mov     edx, [rbp+70h+ReturnLength]
0x14001454f  mov     ecx, 100h
0x140014554  mov     r8d, 6B6F7448h
0x14001455a  call    cs:__imp_ExAllocatePool2
0x140014561  nop     dword ptr [rax+rax+00h]
0x140014566  mov     rsi, rax
0x140014569  test    rax, rax
0x14001456c  jz      short loc_14001457A
0x14001456e  add     ebx, r15d
0x140014571  jmp     short loc_140014513
0x140014573  xor     ebx, ebx
0x140014575  jmp     loc_14001468B
0x14001457a  mov     ebx, 0C000009Ah
0x14001457f  jmp     loc_14001468B
0x140014584  mov     rcx, [rsi]; Sid
0x140014587  lea     rdx, [rbp+70h+Dacl]
0x14001458b  call    HsmiOsBuildAppPolicyKeyAcl
0x140014590  mov     ebx, eax
0x140014592  test    eax, eax
0x140014594  js      loc_140014710
0x14001459a  mov     edx, r15d; Revision
0x14001459d  lea     rcx, [rbp+70h+SecurityDescriptor]; SecurityDescriptor
0x1400145a1  call    cs:__imp_RtlCreateSecurityDescriptor
0x1400145a8  nop     dword ptr [rax+rax+00h]
0x1400145ad  mov     ebx, eax
0x1400145af  test    eax, eax
0x1400145b1  js      loc_140014710
0x1400145b7  mov     r14, [rbp+70h+Dacl]
0x1400145bb  lea     rcx, [rbp+70h+SecurityDescriptor]; SecurityDescriptor
0x1400145bf  mov     r8, r14; Dacl
0x1400145c2  xor     r9d, r9d; DaclDefaulted
0x1400145c5  mov     dl, r15b; DaclPresent
0x1400145c8  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1400145cf  nop     dword ptr [rax+rax+00h]
0x1400145d4  mov     ebx, eax
0x1400145d6  test    eax, eax
0x1400145d8  js      short loc_140014659
0x1400145da  mov     rax, [rsp+170h+var_120]
0x1400145df  lea     r8, [rbp+70h+var_98]; ObjectAttributes
0x1400145e3  mov     [rbp+70h+var_98.RootDirectory], rax
0x1400145e7  lea     rcx, [rsp+170h+Handle]; KeyHandle
0x1400145ec  lea     rax, [rbp+70h+DestinationString]
0x1400145f0  mov     [rbp+70h+var_98.Length], 30h ; '0'
0x1400145f7  mov     [rbp+70h+var_98.ObjectName], rax
0x1400145fb  xor     r9d, r9d; TitleIndex
0x1400145fe  lea     rax, [rbp+70h+SecurityDescriptor]
0x140014602  mov     [rbp+70h+var_98.Attributes], r12d
0x140014606  mov     [rbp+70h+var_98.SecurityDescriptor], rax
0x14001460a  mov     edx, edi; DesiredAccess
0x14001460c  lea     rax, [rsp+170h+var_130]
0x140014611  mov     [rbp+70h+var_98.SecurityQualityOfService], 0
0x140014619  mov     [rsp+170h+Disposition], rax; Disposition
0x14001461e  mov     [rsp+170h+CreateOptions], 0; CreateOptions
0x140014626  mov     [rsp+170h+Class], 0; Class
0x14001462f  call    cs:__imp_ZwCreateKey
0x140014636  nop     dword ptr [rax+rax+00h]
0x14001463b  mov     ebx, eax
0x14001463d  test    ebx, ebx
0x14001463f  js      short loc_140014659
0x140014641  mov     rax, [rsp+170h+Handle]
0x140014646  mov     rdx, [rbp+70h+arg_20]
0x14001464d  mov     [rsp+170h+Handle], 0
0x140014656  mov     [rdx], rax
0x140014659  test    r14, r14
0x14001465c  jz      short loc_140014672
0x14001465e  mov     edx, 636C6148h; Tag
0x140014663  mov     rcx, r14; P
0x140014666  call    cs:__imp_ExFreePoolWithTag
0x14001466d  nop     dword ptr [rax+rax+00h]
0x140014672  test    rsi, rsi
0x140014675  jz      short loc_14001468B
0x140014677  mov     edx, 6B6F7448h; Tag
0x14001467c  mov     rcx, rsi; P
0x14001467f  call    cs:__imp_ExFreePoolWithTag
0x140014686  nop     dword ptr [rax+rax+00h]
0x14001468b  mov     rcx, [rsp+170h+TokenHandle]; Handle
0x140014690  test    rcx, rcx
0x140014693  jz      short loc_1400146A1
0x140014695  call    cs:__imp_ZwClose
0x14001469c  nop     dword ptr [rax+rax+00h]
0x1400146a1  mov     rcx, [rsp+170h+Handle]; Handle
0x1400146a6  test    rcx, rcx
0x1400146a9  jz      short loc_1400146B7
0x1400146ab  call    cs:__imp_ZwClose
0x1400146b2  nop     dword ptr [rax+rax+00h]
0x1400146b7  mov     rcx, [rsp+170h+var_120]; Handle
0x1400146bc  test    rcx, rcx
0x1400146bf  jz      short loc_1400146CD
0x1400146c1  call    cs:__imp_ZwClose
0x1400146c8  nop     dword ptr [rax+rax+00h]
0x1400146cd  mov     rcx, [rsp+170h+var_110]; Handle
0x1400146d2  test    rcx, rcx
0x1400146d5  jz      short loc_1400146E3
0x1400146d7  call    cs:__imp_ZwClose
0x1400146de  nop     dword ptr [rax+rax+00h]
0x1400146e3  mov     rcx, [rsp+170h+KeyHandle]; Handle
0x1400146e8  test    rcx, rcx
0x1400146eb  jz      short loc_1400146F9
0x1400146ed  call    cs:__imp_ZwClose
0x1400146f4  nop     dword ptr [rax+rax+00h]
0x1400146f9  mov     eax, ebx
0x1400146fb  add     rsp, 138h
0x140014702  pop     r15
0x140014704  pop     r14
0x140014706  pop     r13
  ... truncated ...
```
