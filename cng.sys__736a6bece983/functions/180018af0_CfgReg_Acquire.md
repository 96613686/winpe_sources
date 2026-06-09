# CfgReg_Acquire

- ea: `0x180018af0`
- end: `0x180018e30`
- name: `CfgReg_Acquire`
- size: `832`
- prototype: `__int64 __fastcall(PERESOURCE Resource, __int64, ACCESS_MASK)`
- caller_count: `17`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002160c`
- `0x180021b60`
- `0x18006a720`
- `0x18006a950`
- `0x18006accc`
- `0x18006ae80`
- `0x18006b19c`
- `0x18006b40c`
- `0x18006b64c`
- `0x18006ba8c`
- `0x18006bbe4`
- `0x18006bd74`
- `0x18006bf70`
- `0x18006c46c`
- `0x18006c6a0`
- `0x18006c9b4`
- `0x18006ce40`

## callees

- `0x180018af0`
- `0x180018e40`
- `0x180025810`
- `0x18003701c`
- `0x18009f650`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180018bea`
- `ntoskrnl!ExAllocatePool2` at `0x180018bea`
- `ntoskrnl!ZwClose` at `0x180018ce7`
- `ntoskrnl!ZwClose` at `0x180018ce7`
- `ntoskrnl!ObfDereferenceObject` at `0x180018cd8`
- `ntoskrnl!ObfDereferenceObject` at `0x180018cd8`
- `ntoskrnl!ZwOpenKey` at `0x180018c70`
- `ntoskrnl!ZwOpenKey` at `0x180018c70`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180018cfe`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180018d64`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180018cfe`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180018d64`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180018d75`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180018e1f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180018d75`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180018e1f`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x180018d1c`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x180018d1c`
- `ntoskrnl!ExReleaseResourceLite` at `0x180018d8b`
- `ntoskrnl!ExReleaseResourceLite` at `0x180018dec`
- `ntoskrnl!ExReleaseResourceLite` at `0x180018d8b`
- `ntoskrnl!ExReleaseResourceLite` at `0x180018dec`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180018d97`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180018df8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180018d97`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180018df8`
- `ntoskrnl!SkIsSecureKernel` at `0x180018da8`
- `ntoskrnl!SkIsSecureKernel` at `0x180018da8`
- `ntoskrnl!SkAllocatePool` at `0x180018dca`
- `ntoskrnl!SkAllocatePool` at `0x180018dca`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x180018cc4`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x180018cc4`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180018c14`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180018c27`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180018c14`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180018c27`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x180018c89`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x180018c89`

## string_xrefs

- `0x180018b28`: `System\CurrentControlSet\Control\Cryptography\Configuration\Local`
- `0x180018b45`: `System\CurrentControlSet\Control\Cryptography\Configuration\Domain`
- `0x180018b16`: `System\CurrentControlSet\Control\Cryptography\Configuration`
- `0x180018b85`: `\Registry\Machine\`

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
0x180018af0  mov     [rsp-8+arg_8], rbx
0x180018af5  push    rbp
0x180018af6  push    rsi
0x180018af7  push    rdi
0x180018af8  push    r14
0x180018afa  push    r15
0x180018afc  lea     rbp, [rsp-37h]
0x180018b01  sub     rsp, 0C0h
0x180018b08  mov     rax, cs:__security_cookie
0x180018b0f  xor     rax, rsp
0x180018b12  mov     [rbp+57h+var_30], rax
0x180018b16  lea     rax, aSystemCurrentc_5; "System\\CurrentControlSet\\Control\\Cry"...
0x180018b1d  mov     dword ptr [rbp+57h+Source+8], 3Ch ; '<'
0x180018b24  mov     qword ptr [rbp+57h+Source], rax
0x180018b28  lea     rdi, aSystemCurrentc_3; "System\\CurrentControlSet\\Control\\Cry"...
0x180018b2f  xor     eax, eax
0x180018b31  mov     qword ptr [rbp+57h+Source+0Ch], 3Bh ; ';'
0x180018b39  mov     [rbp+57h+var_9C], eax
0x180018b3c  xor     r15d, r15d
0x180018b3f  mov     [rbp+57h+var_44], eax
0x180018b42  mov     r14d, r8d
0x180018b45  lea     rax, aSystemCurrentc_0; "System\\CurrentControlSet\\Control\\Cry"...
0x180018b4c  mov     dword ptr [rbp+57h+Destination+8], 43h ; 'C'
0x180018b53  mov     qword ptr [rbp+57h+Destination], rax
0x180018b57  mov     rsi, rcx
0x180018b5a  xor     eax, eax
0x180018b5c  mov     qword ptr [rbp+57h+Destination+0Ch], 42h ; 'B'
0x180018b64  mov     [rbp+57h+var_9C], eax
0x180018b67  cmp     edx, 1
0x180018b6a  jnz     loc_180018D4E
0x180018b70  xorps   xmm1, xmm1
0x180018b73  mov     [rbp+57h+KeyHandle], r15
0x180018b77  xorps   xmm0, xmm0
0x180018b7a  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180018b81  movups  xmmword ptr [rbp+57h+Destination], xmm0
0x180018b85  movups  xmm0, xmmword ptr cs:aRegistryMachin_1; "\\Registry\\Machine\\"
0x180018b8c  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x180018b90  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x180018b94  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x180018b98  movups  xmm1, xmmword ptr cs:aRegistryMachin_1+10h; "y\\Machine\\"
0x180018b9f  movups  xmmword ptr [rbp+57h+Source], xmm0
0x180018ba3  movsd   xmm0, qword ptr cs:aRegistryMachin_1+1Eh; "ne\\"
0x180018bab  movups  xmmword ptr [rbp+0Fh], xmm1
0x180018baf  movsd   [rbp+57h+var_3A], xmm0
0x180018bb4  cmp     [rdi+rax*2+2], r15w
0x180018bba  lea     rax, [rax+1]
0x180018bbe  jnz     short loc_180018BB4
0x180018bc0  lea     ebx, ds:26h[rax*2]
0x180018bc7  mov     eax, cs:g_TrustedEnvironment
0x180018bcd  test    eax, eax
0x180018bcf  jz      loc_180018DA8
0x180018bd5  mov     edx, ebx
0x180018bd7  mov     r8d, 62676E43h
0x180018bdd  test    al, 2
0x180018bdf  jnz     loc_180018DC5
0x180018be5  mov     ecx, 40h ; '@'
0x180018bea  call    cs:__imp_ExAllocatePool2
0x180018bf1  nop     dword ptr [rax+rax+00h]
0x180018bf6  mov     qword ptr [rbp+57h+Destination+8], rax
0x180018bfa  test    rax, rax
0x180018bfd  jz      loc_180018E09
0x180018c03  lea     rdx, [rbp+57h+Source]; Source
0x180018c07  mov     word ptr [rbp+57h+Destination], r15w
0x180018c0c  lea     rcx, [rbp+57h+Destination]; Destination
0x180018c10  mov     word ptr [rbp+57h+Destination+2], bx
0x180018c14  call    cs:__imp_RtlAppendUnicodeToString
0x180018c1b  nop     dword ptr [rax+rax+00h]
0x180018c20  mov     rdx, rdi; Source
0x180018c23  lea     rcx, [rbp+57h+Destination]; Destination
0x180018c27  call    cs:__imp_RtlAppendUnicodeToString
0x180018c2e  nop     dword ptr [rax+rax+00h]
0x180018c33  mov     eax, 240h
0x180018c38  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180018c3f  mov     ecx, 640h
0x180018c44  mov     [rbp+57h+ObjectAttributes.RootDirectory], r15
0x180018c48  xorps   xmm0, xmm0
0x180018c4b  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180018c4f  cmp     r14d, 20019h
0x180018c56  mov     edx, r14d; DesiredAccess
0x180018c59  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180018c5e  cmovnz  eax, ecx
0x180018c61  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180018c65  mov     [rbp+57h+ObjectAttributes.Attributes], eax
0x180018c68  lea     rax, [rbp+57h+Destination]
0x180018c6c  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180018c70  call    cs:__imp_ZwOpenKey
0x180018c77  nop     dword ptr [rax+rax+00h]
0x180018c7c  mov     rcx, qword ptr [rbp+57h+Destination+8]; P
0x180018c80  mov     ebx, eax
0x180018c82  call    BCryptFree
0x180018c87  mov     ecx, ebx; Status
0x180018c89  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180018c90  nop     dword ptr [rax+rax+00h]
0x180018c95  mov     ebx, eax
0x180018c97  test    eax, eax
0x180018c99  jnz     short loc_180018CF3
0x180018c9b  mov     rdi, [rbp+57h+KeyHandle]
0x180018c9f  lea     rax, [rbp+57h+Destination]
0x180018ca3  mov     [rsp+0E0h+HandleInformation], rax; HandleInformation
0x180018ca8  xor     r9d, r9d; AccessMode
0x180018cab  lea     rax, [rbp+57h+var_90]
0x180018caf  mov     qword ptr [rbp+57h+Destination], r15
0x180018cb3  xor     r8d, r8d; ObjectType
0x180018cb6  mov     [rsp+0E0h+Object], rax; Object
0x180018cbb  xor     edx, edx; DesiredAccess
0x180018cbd  mov     [rbp+57h+var_90], r15
0x180018cc1  mov     rcx, rdi; Handle
0x180018cc4  call    cs:__imp_ObReferenceObjectByHandle
0x180018ccb  nop     dword ptr [rax+rax+00h]
0x180018cd0  test    eax, eax
0x180018cd2  js      short loc_180018CF3
0x180018cd4  mov     rcx, [rbp+57h+var_90]; Object
0x180018cd8  call    cs:__imp_ObfDereferenceObject
0x180018cdf  nop     dword ptr [rax+rax+00h]
0x180018ce4  mov     rcx, rdi; Handle
0x180018ce7  call    cs:__imp_ZwClose
0x180018cee  nop     dword ptr [rax+rax+00h]
0x180018cf3  test    ebx, ebx
0x180018cf5  jnz     short loc_180018D28
0x180018cf7  mov     eax, [rsi+78h]
0x180018cfa  test    eax, eax
0x180018cfc  jz      short loc_180018D64
0x180018cfe  call    cs:__imp_KeEnterCriticalRegion
0x180018d05  nop     dword ptr [rax+rax+00h]
0x180018d0a  mov     dl, 1; Wait
0x180018d0c  mov     rcx, rsi; Resource
0x180018d0f  cmp     r14d, 3001Fh
0x180018d16  jz      loc_180018E1F
0x180018d1c  call    cs:__imp_ExAcquireResourceSharedLite
0x180018d23  nop     dword ptr [rax+rax+00h]
0x180018d28  mov     eax, ebx
0x180018d2a  mov     rcx, [rbp+57h+var_30]
0x180018d2e  xor     rcx, rsp; StackCookie
0x180018d31  call    __security_check_cookie
0x180018d36  mov     rbx, [rsp+0E0h+arg_8]
0x180018d3e  add     rsp, 0C0h
0x180018d45  pop     r15
0x180018d47  pop     r14
0x180018d49  pop     rdi
0x180018d4a  pop     rsi
0x180018d4b  pop     rbp
0x180018d4c  retn
0x180018d4e  cmp     edx, 2
0x180018d51  lea     rdx, [rbp+57h+Destination]
0x180018d55  jz      short loc_180018D5B
0x180018d57  lea     rdx, [rbp+57h+Source]
0x180018d5b  call    VerifyRegistryAccess
0x180018d60  mov     ebx, eax
0x180018d62  jmp     short loc_180018CF3
0x180018d64  call    cs:__imp_KeEnterCriticalRegion
0x180018d6b  nop     dword ptr [rax+rax+00h]
0x180018d70  mov     dl, 1; Wait
0x180018d72  mov     rcx, rsi; Resource
0x180018d75  call    cs:__imp_ExAcquireResourceExclusiveLite
0x180018d7c  nop     dword ptr [rax+rax+00h]
0x180018d81  mov     eax, [rsi+78h]
0x180018d84  test    eax, eax
0x180018d86  jz      short loc_180018DDB
0x180018d88  mov     rcx, rsi; Resource
0x180018d8b  call    cs:__imp_ExReleaseResourceLite
0x180018d92  nop     dword ptr [rax+rax+00h]
0x180018d97  call    cs:__imp_KeLeaveCriticalRegion
0x180018d9e  nop     dword ptr [rax+rax+00h]
0x180018da3  jmp     loc_180018CFE
0x180018da8  call    cs:__imp_SkIsSecureKernel
0x180018daf  nop     dword ptr [rax+rax+00h]
0x180018db4  sar     eax, 1Fh
0x180018db7  add     eax, 2
0x180018dba  mov     cs:g_TrustedEnvironment, eax
0x180018dc0  jmp     loc_180018BD5
0x180018dc5  mov     ecx, 200h
0x180018dca  call    cs:__imp_SkAllocatePool
0x180018dd1  nop     dword ptr [rax+rax+00h]
0x180018dd6  jmp     loc_180018BF6
0x180018ddb  mov     rcx, rsi
0x180018dde  call    _CfgReg_LoadRoot
0x180018de3  mov     ebx, eax
0x180018de5  test    eax, eax
0x180018de7  jz      short loc_180018E13
0x180018de9  mov     rcx, rsi; Resource
0x180018dec  call    cs:__imp_ExReleaseResourceLite
0x180018df3  nop     dword ptr [rax+rax+00h]
0x180018df8  call    cs:__imp_KeLeaveCriticalRegion
0x180018dff  nop     dword ptr [rax+rax+00h]
0x180018e04  jmp     loc_180018D28
0x180018e09  mov     ebx, 8
0x180018e0e  jmp     loc_180018CF3
0x180018e13  mov     dword ptr [rsi+78h], 1
0x180018e1a  jmp     loc_180018D88
0x180018e1f  call    cs:__imp_ExAcquireResourceExclusiveLite
0x180018e26  nop     dword ptr [rax+rax+00h]
0x180018e2b  jmp     loc_180018D28
```
