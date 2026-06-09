# CfgReg_Acquire

- ea: `0x180025b70`
- end: `0x180025eb0`
- name: `CfgReg_Acquire`
- size: `832`
- prototype: `__int64 __fastcall(PERESOURCE Resource)`
- caller_count: `17`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002e67c`
- `0x18002ebd0`
- `0x180073ec0`
- `0x1800740f0`
- `0x18007446c`
- `0x180074620`
- `0x18007493c`
- `0x180074bac`
- `0x180074dec`
- `0x18007522c`
- `0x180075384`
- `0x180075514`
- `0x180075710`
- `0x180075c0c`
- `0x180075e40`
- `0x180076154`
- `0x1800765e0`

## callees

- `0x180025b70`
- `0x180025ec0`
- `0x180032880`
- `0x18004058c`
- `0x1800a4260`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180025c6a`
- `ntoskrnl!ExAllocatePool2` at `0x180025c6a`
- `ntoskrnl!ZwClose` at `0x180025d67`
- `ntoskrnl!ZwClose` at `0x180025d67`
- `ntoskrnl!ObfDereferenceObject` at `0x180025d58`
- `ntoskrnl!ObfDereferenceObject` at `0x180025d58`
- `ntoskrnl!ZwOpenKey` at `0x180025cf0`
- `ntoskrnl!ZwOpenKey` at `0x180025cf0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180025d7e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180025de4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180025d7e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180025de4`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180025df5`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180025e9f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180025df5`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180025e9f`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x180025d9c`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x180025d9c`
- `ntoskrnl!ExReleaseResourceLite` at `0x180025e0b`
- `ntoskrnl!ExReleaseResourceLite` at `0x180025e6c`
- `ntoskrnl!ExReleaseResourceLite` at `0x180025e0b`
- `ntoskrnl!ExReleaseResourceLite` at `0x180025e6c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180025e17`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180025e78`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180025e17`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180025e78`
- `ntoskrnl!SkIsSecureKernel` at `0x180025e28`
- `ntoskrnl!SkIsSecureKernel` at `0x180025e28`
- `ntoskrnl!SkAllocatePool` at `0x180025e4a`
- `ntoskrnl!SkAllocatePool` at `0x180025e4a`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x180025d44`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x180025d44`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180025c94`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180025ca7`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180025c94`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180025ca7`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x180025d09`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x180025d09`

## string_xrefs

- `0x180025ba8`: `System\CurrentControlSet\Control\Cryptography\Configuration\Local`
- `0x180025bc5`: `System\CurrentControlSet\Control\Cryptography\Configuration\Domain`
- `0x180025b96`: `System\CurrentControlSet\Control\Cryptography\Configuration`
- `0x180025c05`: `\Registry\Machine\`

## pseudocode

```c
__int64 __fastcall CfgReg_Acquire(PERESOURCE Resource, __int64 a2, ACCESS_MASK a3)
{
  __int64 v5; // rax
  bool v6; // zf
  unsigned int v7; // ebx
  __int64 Pool; // rax
  ULONG v9; // eax
  NTSTATUS v10; // ebx
  ULONG Root; // ebx
  void *v12; // rdi
  WCHAR *v14; // rdx
  _BYTE Destination[20]; // [rsp+30h] [rbp-59h] BYREF
  int v16; // [rsp+44h] [rbp-45h]
  void *KeyHandle; // [rsp+48h] [rbp-41h] BYREF
  PVOID Object; // [rsp+50h] [rbp-39h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-31h] BYREF
  WCHAR Source[20]; // [rsp+88h] [rbp-1h] BYREF

  wcscpy(&Source[4], L"<");
  *(_QWORD *)Source = L"System\\CurrentControlSet\\Control\\Cryptography\\Configuration";
  *(_QWORD *)&Source[6] = 59;
  *(_DWORD *)&Source[10] = 0;
  *(_DWORD *)&Destination[8] = 67;
  *(_QWORD *)Destination = L"System\\CurrentControlSet\\Control\\Cryptography\\Configuration\\Domain";
  *(_QWORD *)&Destination[12] = 66;
  v16 = 0;
  if ( (_DWORD)a2 == 1 )
  {
    KeyHandle = 0;
    v5 = -1;
    *(_OWORD *)Destination = 0;
    memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
    wcscpy(Source, L"\\Registry\\Machne\\");
    do
      v6 = aSystemCurrentc_3[++v5] == 0;
    while ( !v6 );
    v7 = 2 * v5 + 38;
    LOBYTE(v5) = g_TrustedEnvironment;
    if ( !g_TrustedEnvironment )
    {
      LODWORD(v5) = ((int)SkIsSecureKernel(Resource, a2) >> 31) + 2;
      g_TrustedEnvironment = v5;
    }
    if ( (v5 & 2) != 0 )
      Pool = SkAllocatePool(512, v7, 1650945603);
    else
      Pool = ExAllocatePool2(64, v7, 1650945603);
    *(_QWORD *)&Destination[8] = Pool;
    if ( Pool )
    {
      *(_WORD *)Destination = 0;
      *(_WORD *)&Destination[2] = v7;
      RtlAppendUnicodeToString((PUNICODE_STRING)Destination, Source);
      RtlAppendUnicodeToString(
        (PUNICODE_STRING)Destination,
        L"System\\CurrentControlSet\\Control\\Cryptography\\Configuration\\Local");
      v9 = 576;
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      if ( a3 != 131097 )
        v9 = 1600;
      ObjectAttributes.Attributes = v9;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)Destination;
      v10 = ZwOpenKey(&KeyHandle, a3, &ObjectAttributes);
      BCryptFree(*(PVOID *)&Destination[8]);
      Root = RtlNtStatusToDosErrorNoTeb(v10);
      if ( !Root )
      {
        v12 = KeyHandle;
        *(_QWORD *)Destination = 0;
        Object = 0;
        if ( ObReferenceObjectByHandle(KeyHandle, 0, 0, 0, &Object, (POBJECT_HANDLE_INFORMATION)Destination) >= 0 )
        {
          ObfDereferenceObject(Object);
          ZwClose(v12);
        }
      }
    }
    else
    {
      Root = 8;
    }
  }
  else
  {
    v6 = (_DWORD)a2 == 2;
    v14 = (WCHAR *)Destination;
    if ( !v6 )
      v14 = Source;
    Root = VerifyRegistryAccess(Resource, v14);
  }
  if ( !Root )
  {
    if ( !LODWORD(Resource[1].OwnerTable) )
    {
      KeEnterCriticalRegion();
      ExAcquireResourceExclusiveLite(Resource, 1u);
      if ( !LODWORD(Resource[1].OwnerTable) )
      {
        Root = CfgReg_LoadRoot(Resource);
        if ( Root )
        {
          ExReleaseResourceLite(Resource);
          KeLeaveCriticalRegion();
          return Root;
        }
        LODWORD(Resource[1].OwnerTable) = 1;
      }
      ExReleaseResourceLite(Resource);
      KeLeaveCriticalRegion();
    }
    KeEnterCriticalRegion();
    if ( a3 == 196639 )
      ExAcquireResourceExclusiveLite(Resource, 1u);
    else
      ExAcquireResourceSharedLite(Resource, 1u);
  }
  return Root;
}

```

## disassembly

```asm
0x180025b70  mov     [rsp-8+arg_8], rbx
0x180025b75  push    rbp
0x180025b76  push    rsi
0x180025b77  push    rdi
0x180025b78  push    r14
0x180025b7a  push    r15
0x180025b7c  lea     rbp, [rsp-37h]
0x180025b81  sub     rsp, 0C0h
0x180025b88  mov     rax, cs:__security_cookie
0x180025b8f  xor     rax, rsp
0x180025b92  mov     [rbp+57h+var_30], rax
0x180025b96  lea     rax, aSystemCurrentc_5; "System\\CurrentControlSet\\Control\\Cry"...
0x180025b9d  mov     dword ptr [rbp+57h+Source+8], 3Ch ; '<'
0x180025ba4  mov     qword ptr [rbp+57h+Source], rax
0x180025ba8  lea     rdi, aSystemCurrentc_3; "System\\CurrentControlSet\\Control\\Cry"...
0x180025baf  xor     eax, eax
0x180025bb1  mov     qword ptr [rbp+57h+Source+0Ch], 3Bh ; ';'
0x180025bb9  mov     [rbp+57h+var_9C], eax
0x180025bbc  xor     r15d, r15d
0x180025bbf  mov     [rbp+57h+var_44], eax
0x180025bc2  mov     r14d, r8d
0x180025bc5  lea     rax, aSystemCurrentc_0; "System\\CurrentControlSet\\Control\\Cry"...
0x180025bcc  mov     dword ptr [rbp+57h+Destination+8], 43h ; 'C'
0x180025bd3  mov     qword ptr [rbp+57h+Destination], rax
0x180025bd7  mov     rsi, rcx
0x180025bda  xor     eax, eax
0x180025bdc  mov     qword ptr [rbp+57h+Destination+0Ch], 42h ; 'B'
0x180025be4  mov     [rbp+57h+var_9C], eax
0x180025be7  cmp     edx, 1
0x180025bea  jnz     loc_180025DCE
0x180025bf0  xorps   xmm1, xmm1
0x180025bf3  mov     [rbp+57h+KeyHandle], r15
0x180025bf7  xorps   xmm0, xmm0
0x180025bfa  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180025c01  movups  xmmword ptr [rbp+57h+Destination], xmm0
0x180025c05  movups  xmm0, xmmword ptr cs:aRegistryMachin_1; "\\Registry\\Machine\\"
0x180025c0c  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x180025c10  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x180025c14  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x180025c18  movups  xmm1, xmmword ptr cs:aRegistryMachin_1+10h; "y\\Machine\\"
0x180025c1f  movups  xmmword ptr [rbp+57h+Source], xmm0
0x180025c23  movsd   xmm0, qword ptr cs:aRegistryMachin_1+1Eh; "ne\\"
0x180025c2b  movups  xmmword ptr [rbp+0Fh], xmm1
0x180025c2f  movsd   [rbp+57h+var_3A], xmm0
0x180025c34  cmp     [rdi+rax*2+2], r15w
0x180025c3a  lea     rax, [rax+1]
0x180025c3e  jnz     short loc_180025C34
0x180025c40  lea     ebx, ds:26h[rax*2]
0x180025c47  mov     eax, cs:g_TrustedEnvironment
0x180025c4d  test    eax, eax
0x180025c4f  jz      loc_180025E28
0x180025c55  mov     edx, ebx
0x180025c57  mov     r8d, 62676E43h
0x180025c5d  test    al, 2
0x180025c5f  jnz     loc_180025E45
0x180025c65  mov     ecx, 40h ; '@'
0x180025c6a  call    cs:__imp_ExAllocatePool2
0x180025c71  nop     dword ptr [rax+rax+00h]
0x180025c76  mov     qword ptr [rbp+57h+Destination+8], rax
0x180025c7a  test    rax, rax
0x180025c7d  jz      loc_180025E89
0x180025c83  lea     rdx, [rbp+57h+Source]; Source
0x180025c87  mov     word ptr [rbp+57h+Destination], r15w
0x180025c8c  lea     rcx, [rbp+57h+Destination]; Destination
0x180025c90  mov     word ptr [rbp+57h+Destination+2], bx
0x180025c94  call    cs:__imp_RtlAppendUnicodeToString
0x180025c9b  nop     dword ptr [rax+rax+00h]
0x180025ca0  mov     rdx, rdi; Source
0x180025ca3  lea     rcx, [rbp+57h+Destination]; Destination
0x180025ca7  call    cs:__imp_RtlAppendUnicodeToString
0x180025cae  nop     dword ptr [rax+rax+00h]
0x180025cb3  mov     eax, 240h
0x180025cb8  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180025cbf  mov     ecx, 640h
0x180025cc4  mov     [rbp+57h+ObjectAttributes.RootDirectory], r15
0x180025cc8  xorps   xmm0, xmm0
0x180025ccb  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180025ccf  cmp     r14d, 20019h
0x180025cd6  mov     edx, r14d; DesiredAccess
0x180025cd9  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180025cde  cmovnz  eax, ecx
0x180025ce1  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180025ce5  mov     [rbp+57h+ObjectAttributes.Attributes], eax
0x180025ce8  lea     rax, [rbp+57h+Destination]
0x180025cec  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180025cf0  call    cs:__imp_ZwOpenKey
0x180025cf7  nop     dword ptr [rax+rax+00h]
0x180025cfc  mov     rcx, qword ptr [rbp+57h+Destination+8]; P
0x180025d00  mov     ebx, eax
0x180025d02  call    BCryptFree
0x180025d07  mov     ecx, ebx; Status
0x180025d09  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180025d10  nop     dword ptr [rax+rax+00h]
0x180025d15  mov     ebx, eax
0x180025d17  test    eax, eax
0x180025d19  jnz     short loc_180025D73
0x180025d1b  mov     rdi, [rbp+57h+KeyHandle]
0x180025d1f  lea     rax, [rbp+57h+Destination]
0x180025d23  mov     [rsp+0E0h+HandleInformation], rax; HandleInformation
0x180025d28  xor     r9d, r9d; AccessMode
0x180025d2b  lea     rax, [rbp+57h+var_90]
0x180025d2f  mov     qword ptr [rbp+57h+Destination], r15
0x180025d33  xor     r8d, r8d; ObjectType
0x180025d36  mov     [rsp+0E0h+Object], rax; Object
0x180025d3b  xor     edx, edx; DesiredAccess
0x180025d3d  mov     [rbp+57h+var_90], r15
0x180025d41  mov     rcx, rdi; Handle
0x180025d44  call    cs:__imp_ObReferenceObjectByHandle
0x180025d4b  nop     dword ptr [rax+rax+00h]
0x180025d50  test    eax, eax
0x180025d52  js      short loc_180025D73
0x180025d54  mov     rcx, [rbp+57h+var_90]; Object
0x180025d58  call    cs:__imp_ObfDereferenceObject
0x180025d5f  nop     dword ptr [rax+rax+00h]
0x180025d64  mov     rcx, rdi; Handle
0x180025d67  call    cs:__imp_ZwClose
0x180025d6e  nop     dword ptr [rax+rax+00h]
0x180025d73  test    ebx, ebx
0x180025d75  jnz     short loc_180025DA8
0x180025d77  mov     eax, [rsi+78h]
0x180025d7a  test    eax, eax
0x180025d7c  jz      short loc_180025DE4
0x180025d7e  call    cs:__imp_KeEnterCriticalRegion
0x180025d85  nop     dword ptr [rax+rax+00h]
0x180025d8a  mov     dl, 1; Wait
0x180025d8c  mov     rcx, rsi; Resource
0x180025d8f  cmp     r14d, 3001Fh
0x180025d96  jz      loc_180025E9F
0x180025d9c  call    cs:__imp_ExAcquireResourceSharedLite
0x180025da3  nop     dword ptr [rax+rax+00h]
0x180025da8  mov     eax, ebx
0x180025daa  mov     rcx, [rbp+57h+var_30]
0x180025dae  xor     rcx, rsp; StackCookie
0x180025db1  call    __security_check_cookie
0x180025db6  mov     rbx, [rsp+0E0h+arg_8]
0x180025dbe  add     rsp, 0C0h
0x180025dc5  pop     r15
0x180025dc7  pop     r14
0x180025dc9  pop     rdi
0x180025dca  pop     rsi
0x180025dcb  pop     rbp
0x180025dcc  retn
0x180025dce  cmp     edx, 2
0x180025dd1  lea     rdx, [rbp+57h+Destination]
0x180025dd5  jz      short loc_180025DDB
0x180025dd7  lea     rdx, [rbp+57h+Source]
0x180025ddb  call    VerifyRegistryAccess
0x180025de0  mov     ebx, eax
0x180025de2  jmp     short loc_180025D73
0x180025de4  call    cs:__imp_KeEnterCriticalRegion
0x180025deb  nop     dword ptr [rax+rax+00h]
0x180025df0  mov     dl, 1; Wait
0x180025df2  mov     rcx, rsi; Resource
0x180025df5  call    cs:__imp_ExAcquireResourceExclusiveLite
0x180025dfc  nop     dword ptr [rax+rax+00h]
0x180025e01  mov     eax, [rsi+78h]
0x180025e04  test    eax, eax
0x180025e06  jz      short loc_180025E5B
0x180025e08  mov     rcx, rsi; Resource
0x180025e0b  call    cs:__imp_ExReleaseResourceLite
0x180025e12  nop     dword ptr [rax+rax+00h]
0x180025e17  call    cs:__imp_KeLeaveCriticalRegion
0x180025e1e  nop     dword ptr [rax+rax+00h]
0x180025e23  jmp     loc_180025D7E
0x180025e28  call    cs:__imp_SkIsSecureKernel
0x180025e2f  nop     dword ptr [rax+rax+00h]
0x180025e34  sar     eax, 1Fh
0x180025e37  add     eax, 2
0x180025e3a  mov     cs:g_TrustedEnvironment, eax
0x180025e40  jmp     loc_180025C55
0x180025e45  mov     ecx, 200h
0x180025e4a  call    cs:__imp_SkAllocatePool
0x180025e51  nop     dword ptr [rax+rax+00h]
0x180025e56  jmp     loc_180025C76
0x180025e5b  mov     rcx, rsi
0x180025e5e  call    _CfgReg_LoadRoot
0x180025e63  mov     ebx, eax
0x180025e65  test    eax, eax
0x180025e67  jz      short loc_180025E93
0x180025e69  mov     rcx, rsi; Resource
0x180025e6c  call    cs:__imp_ExReleaseResourceLite
0x180025e73  nop     dword ptr [rax+rax+00h]
0x180025e78  call    cs:__imp_KeLeaveCriticalRegion
0x180025e7f  nop     dword ptr [rax+rax+00h]
0x180025e84  jmp     loc_180025DA8
0x180025e89  mov     ebx, 8
0x180025e8e  jmp     loc_180025D73
0x180025e93  mov     dword ptr [rsi+78h], 1
0x180025e9a  jmp     loc_180025E08
0x180025e9f  call    cs:__imp_ExAcquireResourceExclusiveLite
0x180025ea6  nop     dword ptr [rax+rax+00h]
0x180025eab  jmp     loc_180025DA8
```
