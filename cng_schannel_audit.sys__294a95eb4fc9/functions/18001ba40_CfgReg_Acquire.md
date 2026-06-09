# CfgReg_Acquire

- ea: `0x18001ba40`
- end: `0x18001bd80`
- name: `CfgReg_Acquire`
- size: `832`
- prototype: `__int64 __fastcall(PERESOURCE Resource)`
- caller_count: `17`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002454c`
- `0x180024aa0`
- `0x180069d20`
- `0x180069f50`
- `0x18006a2cc`
- `0x18006a480`
- `0x18006a79c`
- `0x18006aa0c`
- `0x18006ac4c`
- `0x18006b08c`
- `0x18006b1e4`
- `0x18006b374`
- `0x18006b570`
- `0x18006ba6c`
- `0x18006bca0`
- `0x18006bfb4`
- `0x18006c440`

## callees

- `0x18001ba40`
- `0x18001bd90`
- `0x180028750`
- `0x18003651c`
- `0x18009d820`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18001bb3a`
- `ntoskrnl!ExAllocatePool2` at `0x18001bb3a`
- `ntoskrnl!ZwClose` at `0x18001bc37`
- `ntoskrnl!ZwClose` at `0x18001bc37`
- `ntoskrnl!ObfDereferenceObject` at `0x18001bc28`
- `ntoskrnl!ObfDereferenceObject` at `0x18001bc28`
- `ntoskrnl!ZwOpenKey` at `0x18001bbc0`
- `ntoskrnl!ZwOpenKey` at `0x18001bbc0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18001bc4e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18001bcb4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18001bc4e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18001bcb4`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18001bcc5`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18001bd6f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18001bcc5`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18001bd6f`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x18001bc6c`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x18001bc6c`
- `ntoskrnl!ExReleaseResourceLite` at `0x18001bcdb`
- `ntoskrnl!ExReleaseResourceLite` at `0x18001bd3c`
- `ntoskrnl!ExReleaseResourceLite` at `0x18001bcdb`
- `ntoskrnl!ExReleaseResourceLite` at `0x18001bd3c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18001bce7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18001bd48`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18001bce7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18001bd48`
- `ntoskrnl!SkIsSecureKernel` at `0x18001bcf8`
- `ntoskrnl!SkIsSecureKernel` at `0x18001bcf8`
- `ntoskrnl!SkAllocatePool` at `0x18001bd1a`
- `ntoskrnl!SkAllocatePool` at `0x18001bd1a`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x18001bc14`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x18001bc14`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18001bb64`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18001bb77`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18001bb64`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18001bb77`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x18001bbd9`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x18001bbd9`

## string_xrefs

- `0x18001ba78`: `System\CurrentControlSet\Control\Cryptography\Configuration\Local`
- `0x18001ba95`: `System\CurrentControlSet\Control\Cryptography\Configuration\Domain`
- `0x18001ba66`: `System\CurrentControlSet\Control\Cryptography\Configuration`
- `0x18001bad5`: `\Registry\Machine\`

## pseudocode

```c
__int64 __fastcall CfgReg_Acquire(PERESOURCE Resource, __int64 a2, __int64 a3)
{
  ACCESS_MASK v3; // r14d
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
  v3 = a3;
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
      if ( v3 != 131097 )
        v9 = 1600;
      ObjectAttributes.Attributes = v9;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)Destination;
      v10 = ZwOpenKey(&KeyHandle, v3, &ObjectAttributes);
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
    Root = VerifyRegistryAccess(Resource, v14, a3);
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
    if ( v3 == 196639 )
      ExAcquireResourceExclusiveLite(Resource, 1u);
    else
      ExAcquireResourceSharedLite(Resource, 1u);
  }
  return Root;
}

```

## disassembly

```asm
0x18001ba40  mov     [rsp-8+arg_8], rbx
0x18001ba45  push    rbp
0x18001ba46  push    rsi
0x18001ba47  push    rdi
0x18001ba48  push    r14
0x18001ba4a  push    r15
0x18001ba4c  lea     rbp, [rsp-37h]
0x18001ba51  sub     rsp, 0C0h
0x18001ba58  mov     rax, cs:__security_cookie
0x18001ba5f  xor     rax, rsp
0x18001ba62  mov     [rbp+57h+var_30], rax
0x18001ba66  lea     rax, aSystemCurrentc_5; "System\\CurrentControlSet\\Control\\Cry"...
0x18001ba6d  mov     dword ptr [rbp+57h+Source+8], 3Ch ; '<'
0x18001ba74  mov     qword ptr [rbp+57h+Source], rax
0x18001ba78  lea     rdi, aSystemCurrentc_3; "System\\CurrentControlSet\\Control\\Cry"...
0x18001ba7f  xor     eax, eax
0x18001ba81  mov     qword ptr [rbp+57h+Source+0Ch], 3Bh ; ';'
0x18001ba89  mov     [rbp+57h+var_9C], eax
0x18001ba8c  xor     r15d, r15d
0x18001ba8f  mov     [rbp+57h+var_44], eax
0x18001ba92  mov     r14d, r8d
0x18001ba95  lea     rax, aSystemCurrentc_0; "System\\CurrentControlSet\\Control\\Cry"...
0x18001ba9c  mov     dword ptr [rbp+57h+Destination+8], 43h ; 'C'
0x18001baa3  mov     qword ptr [rbp+57h+Destination], rax
0x18001baa7  mov     rsi, rcx
0x18001baaa  xor     eax, eax
0x18001baac  mov     qword ptr [rbp+57h+Destination+0Ch], 42h ; 'B'
0x18001bab4  mov     [rbp+57h+var_9C], eax
0x18001bab7  cmp     edx, 1
0x18001baba  jnz     loc_18001BC9E
0x18001bac0  xorps   xmm1, xmm1
0x18001bac3  mov     [rbp+57h+KeyHandle], r15
0x18001bac7  xorps   xmm0, xmm0
0x18001baca  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18001bad1  movups  xmmword ptr [rbp+57h+Destination], xmm0
0x18001bad5  movups  xmm0, xmmword ptr cs:aRegistryMachin_1; "\\Registry\\Machine\\"
0x18001badc  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x18001bae0  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x18001bae4  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x18001bae8  movups  xmm1, xmmword ptr cs:aRegistryMachin_1+10h; "y\\Machine\\"
0x18001baef  movups  xmmword ptr [rbp+57h+Source], xmm0
0x18001baf3  movsd   xmm0, qword ptr cs:aRegistryMachin_1+1Eh; "ne\\"
0x18001bafb  movups  xmmword ptr [rbp+0Fh], xmm1
0x18001baff  movsd   [rbp+57h+var_3A], xmm0
0x18001bb04  cmp     [rdi+rax*2+2], r15w
0x18001bb0a  lea     rax, [rax+1]
0x18001bb0e  jnz     short loc_18001BB04
0x18001bb10  lea     ebx, ds:26h[rax*2]
0x18001bb17  mov     eax, cs:g_TrustedEnvironment
0x18001bb1d  test    eax, eax
0x18001bb1f  jz      loc_18001BCF8
0x18001bb25  mov     edx, ebx
0x18001bb27  mov     r8d, 62676E43h
0x18001bb2d  test    al, 2
0x18001bb2f  jnz     loc_18001BD15
0x18001bb35  mov     ecx, 40h ; '@'
0x18001bb3a  call    cs:__imp_ExAllocatePool2
0x18001bb41  nop     dword ptr [rax+rax+00h]
0x18001bb46  mov     qword ptr [rbp+57h+Destination+8], rax
0x18001bb4a  test    rax, rax
0x18001bb4d  jz      loc_18001BD59
0x18001bb53  lea     rdx, [rbp+57h+Source]; Source
0x18001bb57  mov     word ptr [rbp+57h+Destination], r15w
0x18001bb5c  lea     rcx, [rbp+57h+Destination]; Destination
0x18001bb60  mov     word ptr [rbp+57h+Destination+2], bx
0x18001bb64  call    cs:__imp_RtlAppendUnicodeToString
0x18001bb6b  nop     dword ptr [rax+rax+00h]
0x18001bb70  mov     rdx, rdi; Source
0x18001bb73  lea     rcx, [rbp+57h+Destination]; Destination
0x18001bb77  call    cs:__imp_RtlAppendUnicodeToString
0x18001bb7e  nop     dword ptr [rax+rax+00h]
0x18001bb83  mov     eax, 240h
0x18001bb88  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18001bb8f  mov     ecx, 640h
0x18001bb94  mov     [rbp+57h+ObjectAttributes.RootDirectory], r15
0x18001bb98  xorps   xmm0, xmm0
0x18001bb9b  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18001bb9f  cmp     r14d, 20019h
0x18001bba6  mov     edx, r14d; DesiredAccess
0x18001bba9  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18001bbae  cmovnz  eax, ecx
0x18001bbb1  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18001bbb5  mov     [rbp+57h+ObjectAttributes.Attributes], eax
0x18001bbb8  lea     rax, [rbp+57h+Destination]
0x18001bbbc  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18001bbc0  call    cs:__imp_ZwOpenKey
0x18001bbc7  nop     dword ptr [rax+rax+00h]
0x18001bbcc  mov     rcx, qword ptr [rbp+57h+Destination+8]; P
0x18001bbd0  mov     ebx, eax
0x18001bbd2  call    BCryptFree
0x18001bbd7  mov     ecx, ebx; Status
0x18001bbd9  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18001bbe0  nop     dword ptr [rax+rax+00h]
0x18001bbe5  mov     ebx, eax
0x18001bbe7  test    eax, eax
0x18001bbe9  jnz     short loc_18001BC43
0x18001bbeb  mov     rdi, [rbp+57h+KeyHandle]
0x18001bbef  lea     rax, [rbp+57h+Destination]
0x18001bbf3  mov     [rsp+0E0h+HandleInformation], rax; HandleInformation
0x18001bbf8  xor     r9d, r9d; AccessMode
0x18001bbfb  lea     rax, [rbp+57h+var_90]
0x18001bbff  mov     qword ptr [rbp+57h+Destination], r15
0x18001bc03  xor     r8d, r8d; ObjectType
0x18001bc06  mov     [rsp+0E0h+Object], rax; Object
0x18001bc0b  xor     edx, edx; DesiredAccess
0x18001bc0d  mov     [rbp+57h+var_90], r15
0x18001bc11  mov     rcx, rdi; Handle
0x18001bc14  call    cs:__imp_ObReferenceObjectByHandle
0x18001bc1b  nop     dword ptr [rax+rax+00h]
0x18001bc20  test    eax, eax
0x18001bc22  js      short loc_18001BC43
0x18001bc24  mov     rcx, [rbp+57h+var_90]; Object
0x18001bc28  call    cs:__imp_ObfDereferenceObject
0x18001bc2f  nop     dword ptr [rax+rax+00h]
0x18001bc34  mov     rcx, rdi; Handle
0x18001bc37  call    cs:__imp_ZwClose
0x18001bc3e  nop     dword ptr [rax+rax+00h]
0x18001bc43  test    ebx, ebx
0x18001bc45  jnz     short loc_18001BC78
0x18001bc47  mov     eax, [rsi+78h]
0x18001bc4a  test    eax, eax
0x18001bc4c  jz      short loc_18001BCB4
0x18001bc4e  call    cs:__imp_KeEnterCriticalRegion
0x18001bc55  nop     dword ptr [rax+rax+00h]
0x18001bc5a  mov     dl, 1; Wait
0x18001bc5c  mov     rcx, rsi; Resource
0x18001bc5f  cmp     r14d, 3001Fh
0x18001bc66  jz      loc_18001BD6F
0x18001bc6c  call    cs:__imp_ExAcquireResourceSharedLite
0x18001bc73  nop     dword ptr [rax+rax+00h]
0x18001bc78  mov     eax, ebx
0x18001bc7a  mov     rcx, [rbp+57h+var_30]
0x18001bc7e  xor     rcx, rsp; StackCookie
0x18001bc81  call    __security_check_cookie
0x18001bc86  mov     rbx, [rsp+0E0h+arg_8]
0x18001bc8e  add     rsp, 0C0h
0x18001bc95  pop     r15
0x18001bc97  pop     r14
0x18001bc99  pop     rdi
0x18001bc9a  pop     rsi
0x18001bc9b  pop     rbp
0x18001bc9c  retn
0x18001bc9e  cmp     edx, 2
0x18001bca1  lea     rdx, [rbp+57h+Destination]
0x18001bca5  jz      short loc_18001BCAB
0x18001bca7  lea     rdx, [rbp+57h+Source]
0x18001bcab  call    VerifyRegistryAccess
0x18001bcb0  mov     ebx, eax
0x18001bcb2  jmp     short loc_18001BC43
0x18001bcb4  call    cs:__imp_KeEnterCriticalRegion
0x18001bcbb  nop     dword ptr [rax+rax+00h]
0x18001bcc0  mov     dl, 1; Wait
0x18001bcc2  mov     rcx, rsi; Resource
0x18001bcc5  call    cs:__imp_ExAcquireResourceExclusiveLite
0x18001bccc  nop     dword ptr [rax+rax+00h]
0x18001bcd1  mov     eax, [rsi+78h]
0x18001bcd4  test    eax, eax
0x18001bcd6  jz      short loc_18001BD2B
0x18001bcd8  mov     rcx, rsi; Resource
0x18001bcdb  call    cs:__imp_ExReleaseResourceLite
0x18001bce2  nop     dword ptr [rax+rax+00h]
0x18001bce7  call    cs:__imp_KeLeaveCriticalRegion
0x18001bcee  nop     dword ptr [rax+rax+00h]
0x18001bcf3  jmp     loc_18001BC4E
0x18001bcf8  call    cs:__imp_SkIsSecureKernel
0x18001bcff  nop     dword ptr [rax+rax+00h]
0x18001bd04  sar     eax, 1Fh
0x18001bd07  add     eax, 2
0x18001bd0a  mov     cs:g_TrustedEnvironment, eax
0x18001bd10  jmp     loc_18001BB25
0x18001bd15  mov     ecx, 200h
0x18001bd1a  call    cs:__imp_SkAllocatePool
0x18001bd21  nop     dword ptr [rax+rax+00h]
0x18001bd26  jmp     loc_18001BB46
0x18001bd2b  mov     rcx, rsi
0x18001bd2e  call    _CfgReg_LoadRoot
0x18001bd33  mov     ebx, eax
0x18001bd35  test    eax, eax
0x18001bd37  jz      short loc_18001BD63
0x18001bd39  mov     rcx, rsi; Resource
0x18001bd3c  call    cs:__imp_ExReleaseResourceLite
0x18001bd43  nop     dword ptr [rax+rax+00h]
0x18001bd48  call    cs:__imp_KeLeaveCriticalRegion
0x18001bd4f  nop     dword ptr [rax+rax+00h]
0x18001bd54  jmp     loc_18001BC78
0x18001bd59  mov     ebx, 8
0x18001bd5e  jmp     loc_18001BC43
0x18001bd63  mov     dword ptr [rsi+78h], 1
0x18001bd6a  jmp     loc_18001BCD8
0x18001bd6f  call    cs:__imp_ExAcquireResourceExclusiveLite
0x18001bd76  nop     dword ptr [rax+rax+00h]
0x18001bd7b  jmp     loc_18001BC78
```
