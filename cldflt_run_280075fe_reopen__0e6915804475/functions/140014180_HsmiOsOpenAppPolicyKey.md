# HsmiOsOpenAppPolicyKey

- ea: `0x140014180`
- end: `0x140014699`
- name: `HsmiOsOpenAppPolicyKey`
- size: `1305`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140007944`
- `0x14001266c`

## callees

- `0x140013798`
- `0x140014180`

## import_xrefs

- `ntoskrnl!ZwOpenThreadTokenEx` at `0x140014457`
- `ntoskrnl!ZwOpenThreadTokenEx` at `0x140014457`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x14001447b`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x14001447b`
- `ntoskrnl!ZwCreateKey` at `0x140014309`
- `ntoskrnl!ZwCreateKey` at `0x14001438e`
- `ntoskrnl!ZwCreateKey` at `0x1400145af`
- `ntoskrnl!ZwCreateKey` at `0x140014309`
- `ntoskrnl!ZwCreateKey` at `0x14001438e`
- `ntoskrnl!ZwCreateKey` at `0x1400145af`
- `ntoskrnl!ZwQueryInformationToken` at `0x1400144b6`
- `ntoskrnl!ZwQueryInformationToken` at `0x1400144b6`
- `ntoskrnl!RtlOpenCurrentUser` at `0x1400141fe`
- `ntoskrnl!RtlOpenCurrentUser` at `0x1400141fe`
- `ntoskrnl!ZwOpenKey` at `0x14001427b`
- `ntoskrnl!ZwOpenKey` at `0x1400142c8`
- `ntoskrnl!ZwOpenKey` at `0x14001434d`
- `ntoskrnl!ZwOpenKey` at `0x1400143eb`
- `ntoskrnl!ZwOpenKey` at `0x14001427b`
- `ntoskrnl!ZwOpenKey` at `0x1400142c8`
- `ntoskrnl!ZwOpenKey` at `0x14001434d`
- `ntoskrnl!ZwOpenKey` at `0x1400143eb`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140014521`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140014521`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140014548`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140014548`
- `ntoskrnl!ZwClose` at `0x140014615`
- `ntoskrnl!ZwClose` at `0x14001462b`
- `ntoskrnl!ZwClose` at `0x140014641`
- `ntoskrnl!ZwClose` at `0x140014657`
- `ntoskrnl!ZwClose` at `0x14001466d`
- `ntoskrnl!ZwClose` at `0x140014615`
- `ntoskrnl!ZwClose` at `0x14001462b`
- `ntoskrnl!ZwClose` at `0x140014641`
- `ntoskrnl!ZwClose` at `0x140014657`
- `ntoskrnl!ZwClose` at `0x14001466d`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400143ad`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400143ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400145e6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400145ff`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400145e6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400145ff`
- `ntoskrnl!ExAllocatePool2` at `0x1400144da`
- `ntoskrnl!ExAllocatePool2` at `0x1400144da`

## string_xrefs

- `0x140014235`: `\Registry\Machine`

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
0x140014180  push    rbp
0x140014182  push    rbx
0x140014183  push    rsi
0x140014184  push    rdi
0x140014185  push    r12
0x140014187  push    r13
0x140014189  push    r14
0x14001418b  push    r15
0x14001418d  lea     rbp, [rsp-38h]
0x140014192  sub     rsp, 138h
0x140014199  xorps   xmm0, xmm0
0x14001419c  mov     [rbp+70h+var_B8], 4E004Ch
0x1400141a4  mov     rsi, rcx
0x1400141a7  lea     rax, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\CloudFil"...
0x1400141ae  xor     ecx, ecx
0x1400141b0  mov     [rbp+70h+var_B0], rax
0x1400141b4  mov     [rsp+170h+var_130], ecx
0x1400141b8  mov     r15b, r9b
0x1400141bb  mov     [rsp+170h+KeyHandle], rcx
0x1400141c0  mov     r13, rdx
0x1400141c3  mov     [rsp+170h+var_110], rcx
0x1400141c8  mov     r14d, ecx
0x1400141cb  mov     [rsp+170h+var_120], rcx
0x1400141d0  mov     [rsp+170h+Handle], rcx
0x1400141d5  mov     [rsp+170h+TokenHandle], rcx
0x1400141da  mov     [rbp+70h+Dacl], rcx
0x1400141de  movups  xmmword ptr [rsp+170h+ObjectAttributes.Length], xmm0
0x1400141e3  movups  xmmword ptr [rbp+70h+ObjectAttributes.ObjectName], xmm0
0x1400141e7  movups  xmmword ptr [rbp+70h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400141eb  movups  xmmword ptr [rbp+70h+DestinationString.Length], xmm0
0x1400141ef  test    r8b, r8b
0x1400141f2  jz      short loc_140014235
0x1400141f4  lea     rdx, [rsp+170h+KeyHandle]; KeyHandle
0x1400141f9  mov     ecx, 20019h; DesiredAccess
0x1400141fe  call    cs:__imp_RtlOpenCurrentUser
0x140014205  nop     dword ptr [rax+rax+00h]
0x14001420a  mov     cl, r15b
0x14001420d  neg     cl
0x14001420f  mov     cl, r15b
0x140014212  sbb     r12d, r12d
0x140014215  and     r12d, 0FFFFFC00h
0x14001421c  add     r12d, 640h
0x140014223  neg     cl
0x140014225  sbb     edi, edi
0x140014227  and     edi, 0D0026h
0x14001422d  add     edi, 20019h
0x140014233  jmp     short loc_14001428C
0x140014235  lea     rax, aRegistryMachin_1; "\\Registry\\Machine"
0x14001423c  mov     [rsp+170h+ObjectAttributes.RootDirectory], rcx
0x140014241  mov     [rbp+70h+var_C0], rax
0x140014245  lea     r8, [rsp+170h+ObjectAttributes]; ObjectAttributes
0x14001424a  lea     rax, [rbp+70h+var_C8]
0x14001424e  mov     [rbp+70h+var_C8], 240022h
0x140014256  mov     r12d, 240h
0x14001425c  mov     [rbp+70h+ObjectAttributes.ObjectName], rax
0x140014260  mov     edx, 20019h; DesiredAccess
0x140014265  mov     [rsp+170h+ObjectAttributes.Length], 30h ; '0'
0x14001426d  lea     rcx, [rsp+170h+KeyHandle]; KeyHandle
0x140014272  mov     [rbp+70h+ObjectAttributes.Attributes], r12d
0x140014276  movdqu  xmmword ptr [rbp+70h+ObjectAttributes.SecurityDescriptor], xmm0
0x14001427b  call    cs:__imp_ZwOpenKey
0x140014282  nop     dword ptr [rax+rax+00h]
0x140014287  mov     edi, 0F003Fh
0x14001428c  mov     ebx, eax
0x14001428e  test    eax, eax
0x140014290  js      loc_14001460B
0x140014296  mov     rax, [rsp+170h+KeyHandle]
0x14001429b  lea     r8, [rsp+170h+ObjectAttributes]; ObjectAttributes
0x1400142a0  mov     [rsp+170h+ObjectAttributes.RootDirectory], rax
0x1400142a5  lea     rcx, [rsp+170h+var_110]; KeyHandle
0x1400142aa  lea     rax, [rbp+70h+var_B8]
0x1400142ae  mov     [rsp+170h+ObjectAttributes.Length], 30h ; '0'
0x1400142b6  xorps   xmm0, xmm0
0x1400142b9  mov     [rbp+70h+ObjectAttributes.ObjectName], rax
0x1400142bd  mov     edx, edi; DesiredAccess
0x1400142bf  mov     [rbp+70h+ObjectAttributes.Attributes], r12d
0x1400142c3  movdqu  xmmword ptr [rbp+70h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400142c8  call    cs:__imp_ZwOpenKey
0x1400142cf  nop     dword ptr [rax+rax+00h]
0x1400142d4  mov     ebx, eax
0x1400142d6  cmp     eax, 0C0000034h
0x1400142db  jnz     short loc_140014317
0x1400142dd  test    r15b, r15b
0x1400142e0  jz      loc_1400144F3
0x1400142e6  lea     rax, [rsp+170h+var_130]
0x1400142eb  xor     r9d, r9d; TitleIndex
0x1400142ee  mov     [rsp+170h+Disposition], rax; Disposition
0x1400142f3  lea     r8, [rsp+170h+ObjectAttributes]; ObjectAttributes
0x1400142f8  mov     [rsp+170h+CreateOptions], r14d; CreateOptions
0x1400142fd  lea     rcx, [rsp+170h+var_110]; KeyHandle
0x140014302  mov     edx, edi; DesiredAccess
0x140014304  mov     [rsp+170h+Class], r14; Class
0x140014309  call    cs:__imp_ZwCreateKey
0x140014310  nop     dword ptr [rax+rax+00h]
0x140014315  mov     ebx, eax
0x140014317  test    ebx, ebx
0x140014319  js      loc_14001460B
0x14001431f  mov     rax, [rsp+170h+var_110]
0x140014324  lea     r8, [rsp+170h+ObjectAttributes]; ObjectAttributes
0x140014329  xorps   xmm0, xmm0
0x14001432c  mov     [rsp+170h+ObjectAttributes.RootDirectory], rax
0x140014331  mov     edx, edi; DesiredAccess
0x140014333  mov     [rsp+170h+ObjectAttributes.Length], 30h ; '0'
0x14001433b  lea     rcx, [rsp+170h+var_120]; KeyHandle
0x140014340  mov     [rbp+70h+ObjectAttributes.Attributes], r12d
0x140014344  movdqu  xmmword ptr [rbp+70h+ObjectAttributes.SecurityDescriptor], xmm0
0x140014349  mov     [rbp+70h+ObjectAttributes.ObjectName], rsi
0x14001434d  call    cs:__imp_ZwOpenKey
0x140014354  nop     dword ptr [rax+rax+00h]
0x140014359  mov     ebx, eax
0x14001435b  cmp     eax, 0C0000034h
0x140014360  jnz     short loc_14001439C
0x140014362  test    r15b, r15b
0x140014365  jz      loc_1400144F3
0x14001436b  lea     rax, [rsp+170h+var_130]
0x140014370  xor     r9d, r9d; TitleIndex
0x140014373  mov     [rsp+170h+Disposition], rax; Disposition
0x140014378  lea     r8, [rsp+170h+ObjectAttributes]; ObjectAttributes
0x14001437d  mov     [rsp+170h+CreateOptions], r14d; CreateOptions
0x140014382  lea     rcx, [rsp+170h+var_120]; KeyHandle
0x140014387  mov     edx, edi; DesiredAccess
0x140014389  mov     [rsp+170h+Class], r14; Class
0x14001438e  call    cs:__imp_ZwCreateKey
0x140014395  nop     dword ptr [rax+rax+00h]
0x14001439a  mov     ebx, eax
0x14001439c  test    ebx, ebx
0x14001439e  js      loc_14001460B
0x1400143a4  mov     rdx, r13; SourceString
0x1400143a7  lea     rcx, [rbp+70h+DestinationString]; DestinationString
0x1400143ab  xor     esi, esi
0x1400143ad  call    cs:__imp_RtlInitUnicodeString
0x1400143b4  nop     dword ptr [rax+rax+00h]
0x1400143b9  mov     rax, [rsp+170h+var_120]
0x1400143be  lea     r8, [rsp+170h+ObjectAttributes]; ObjectAttributes
0x1400143c3  mov     [rsp+170h+ObjectAttributes.RootDirectory], rax
0x1400143c8  lea     rcx, [rsp+170h+Handle]; KeyHandle
0x1400143cd  lea     rax, [rbp+70h+DestinationString]
0x1400143d1  mov     [rsp+170h+ObjectAttributes.Length], 30h ; '0'
0x1400143d9  xorps   xmm0, xmm0
0x1400143dc  mov     [rbp+70h+ObjectAttributes.ObjectName], rax
0x1400143e0  mov     edx, edi; DesiredAccess
0x1400143e2  mov     [rbp+70h+ObjectAttributes.Attributes], r12d
0x1400143e6  movdqu  xmmword ptr [rbp+70h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400143eb  call    cs:__imp_ZwOpenKey
0x1400143f2  nop     dword ptr [rax+rax+00h]
0x1400143f7  mov     ebx, eax
0x1400143f9  cmp     eax, 0C0000034h
0x1400143fe  jnz     loc_1400145BD
0x140014404  test    r15b, r15b
0x140014407  jz      loc_1400144F3
0x14001440d  xorps   xmm0, xmm0
0x140014410  lea     r15d, [rsi+1]
0x140014414  xor     eax, eax
0x140014416  lea     rcx, [rsi-2]; ThreadHandle
0x14001441a  mov     [rbp+70h+ReturnLength], eax
0x140014420  mov     r14d, 200h
0x140014426  mov     [rbp+70h+var_48], rax
0x14001442a  mov     r13d, 20008h
0x140014430  lea     rax, [rsp+170h+TokenHandle]
0x140014435  mov     r9d, r14d; HandleAttributes
0x140014438  movups  xmmword ptr [rbp+70h+var_98.ObjectName], xmm0
0x14001443c  mov     r8b, r15b; OpenAsSelf
0x14001443f  mov     [rsp+170h+Class], rax; TokenHandle
0x140014444  mov     edx, r13d; DesiredAccess
0x140014447  movups  xmmword ptr [rbp+70h+var_98.Length], xmm0
0x14001444b  movups  xmmword ptr [rbp+70h+var_98+1Ch], xmm0
0x14001444f  movups  [rbp+70h+SecurityDescriptor], xmm0
0x140014453  movups  [rbp+70h+var_58], xmm0
0x140014457  call    cs:__imp_ZwOpenThreadTokenEx
0x14001445e  nop     dword ptr [rax+rax+00h]
0x140014463  mov     ebx, eax
0x140014465  cmp     eax, 0C000007Ch
0x14001446a  jnz     short loc_140014489
0x14001446c  lea     r9, [rsp+170h+TokenHandle]; TokenHandle
0x140014471  mov     r8d, r14d; HandleAttributes
0x140014474  mov     edx, r13d; DesiredAccess
0x140014477  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x14001447b  call    cs:__imp_ZwOpenProcessTokenEx
0x140014482  nop     dword ptr [rax+rax+00h]
0x140014487  mov     ebx, eax
0x140014489  test    ebx, ebx
0x14001448b  js      loc_14001460B
0x140014491  xor     ebx, ebx
0x140014493  cmp     ebx, 2
0x140014496  jge     short loc_140014504
0x140014498  mov     r9d, [rbp+70h+ReturnLength]; TokenInformationLength
0x14001449f  lea     rax, [rbp+70h+ReturnLength]
0x1400144a6  mov     rcx, [rsp+170h+TokenHandle]; TokenHandle
0x1400144ab  mov     r8, rsi; TokenInformation
0x1400144ae  mov     edx, r15d; TokenInformationClass
0x1400144b1  mov     [rsp+170h+Class], rax; ReturnLength
0x1400144b6  call    cs:__imp_ZwQueryInformationToken
0x1400144bd  nop     dword ptr [rax+rax+00h]
0x1400144c2  cmp     eax, 0C0000023h
0x1400144c7  jnz     short loc_1400144EE
0x1400144c9  mov     edx, [rbp+70h+ReturnLength]
0x1400144cf  mov     ecx, 100h
0x1400144d4  mov     r8d, 6B6F7448h
0x1400144da  call    cs:__imp_ExAllocatePool2
0x1400144e1  nop     dword ptr [rax+rax+00h]
0x1400144e6  mov     rsi, rax
0x1400144e9  test    rax, rax
0x1400144ec  jz      short loc_1400144FA
0x1400144ee  add     ebx, r15d
0x1400144f1  jmp     short loc_140014493
0x1400144f3  xor     ebx, ebx
0x1400144f5  jmp     loc_14001460B
0x1400144fa  mov     ebx, 0C000009Ah
0x1400144ff  jmp     loc_14001460B
0x140014504  mov     rcx, [rsi]; Sid
0x140014507  lea     rdx, [rbp+70h+Dacl]
0x14001450b  call    HsmiOsBuildAppPolicyKeyAcl
0x140014510  mov     ebx, eax
0x140014512  test    eax, eax
0x140014514  js      loc_140014690
0x14001451a  mov     edx, r15d; Revision
0x14001451d  lea     rcx, [rbp+70h+SecurityDescriptor]; SecurityDescriptor
0x140014521  call    cs:__imp_RtlCreateSecurityDescriptor
0x140014528  nop     dword ptr [rax+rax+00h]
0x14001452d  mov     ebx, eax
0x14001452f  test    eax, eax
0x140014531  js      loc_140014690
0x140014537  mov     r14, [rbp+70h+Dacl]
0x14001453b  lea     rcx, [rbp+70h+SecurityDescriptor]; SecurityDescriptor
0x14001453f  mov     r8, r14; Dacl
0x140014542  xor     r9d, r9d; DaclDefaulted
0x140014545  mov     dl, r15b; DaclPresent
0x140014548  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14001454f  nop     dword ptr [rax+rax+00h]
0x140014554  mov     ebx, eax
0x140014556  test    eax, eax
0x140014558  js      short loc_1400145D9
0x14001455a  mov     rax, [rsp+170h+var_120]
0x14001455f  lea     r8, [rbp+70h+var_98]; ObjectAttributes
0x140014563  mov     [rbp+70h+var_98.RootDirectory], rax
0x140014567  lea     rcx, [rsp+170h+Handle]; KeyHandle
0x14001456c  lea     rax, [rbp+70h+DestinationString]
0x140014570  mov     [rbp+70h+var_98.Length], 30h ; '0'
0x140014577  mov     [rbp+70h+var_98.ObjectName], rax
0x14001457b  xor     r9d, r9d; TitleIndex
0x14001457e  lea     rax, [rbp+70h+SecurityDescriptor]
0x140014582  mov     [rbp+70h+var_98.Attributes], r12d
0x140014586  mov     [rbp+70h+var_98.SecurityDescriptor], rax
0x14001458a  mov     edx, edi; DesiredAccess
0x14001458c  lea     rax, [rsp+170h+var_130]
0x140014591  mov     [rbp+70h+var_98.SecurityQualityOfService], 0
0x140014599  mov     [rsp+170h+Disposition], rax; Disposition
0x14001459e  mov     [rsp+170h+CreateOptions], 0; CreateOptions
0x1400145a6  mov     [rsp+170h+Class], 0; Class
0x1400145af  call    cs:__imp_ZwCreateKey
0x1400145b6  nop     dword ptr [rax+rax+00h]
0x1400145bb  mov     ebx, eax
0x1400145bd  test    ebx, ebx
0x1400145bf  js      short loc_1400145D9
0x1400145c1  mov     rax, [rsp+170h+Handle]
0x1400145c6  mov     rdx, [rbp+70h+arg_20]
0x1400145cd  mov     [rsp+170h+Handle], 0
0x1400145d6  mov     [rdx], rax
0x1400145d9  test    r14, r14
0x1400145dc  jz      short loc_1400145F2
0x1400145de  mov     edx, 636C6148h; Tag
0x1400145e3  mov     rcx, r14; P
0x1400145e6  call    cs:__imp_ExFreePoolWithTag
0x1400145ed  nop     dword ptr [rax+rax+00h]
0x1400145f2  test    rsi, rsi
0x1400145f5  jz      short loc_14001460B
0x1400145f7  mov     edx, 6B6F7448h; Tag
0x1400145fc  mov     rcx, rsi; P
0x1400145ff  call    cs:__imp_ExFreePoolWithTag
0x140014606  nop     dword ptr [rax+rax+00h]
0x14001460b  mov     rcx, [rsp+170h+TokenHandle]; Handle
0x140014610  test    rcx, rcx
0x140014613  jz      short loc_140014621
0x140014615  call    cs:__imp_ZwClose
0x14001461c  nop     dword ptr [rax+rax+00h]
0x140014621  mov     rcx, [rsp+170h+Handle]; Handle
0x140014626  test    rcx, rcx
0x140014629  jz      short loc_140014637
0x14001462b  call    cs:__imp_ZwClose
0x140014632  nop     dword ptr [rax+rax+00h]
0x140014637  mov     rcx, [rsp+170h+var_120]; Handle
0x14001463c  test    rcx, rcx
0x14001463f  jz      short loc_14001464D
0x140014641  call    cs:__imp_ZwClose
0x140014648  nop     dword ptr [rax+rax+00h]
0x14001464d  mov     rcx, [rsp+170h+var_110]; Handle
0x140014652  test    rcx, rcx
0x140014655  jz      short loc_140014663
0x140014657  call    cs:__imp_ZwClose
0x14001465e  nop     dword ptr [rax+rax+00h]
0x140014663  mov     rcx, [rsp+170h+KeyHandle]; Handle
0x140014668  test    rcx, rcx
0x14001466b  jz      short loc_140014679
0x14001466d  call    cs:__imp_ZwClose
0x140014674  nop     dword ptr [rax+rax+00h]
0x140014679  mov     eax, ebx
0x14001467b  add     rsp, 138h
0x140014682  pop     r15
0x140014684  pop     r14
0x140014686  pop     r13
  ... truncated ...
```
