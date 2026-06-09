# MupInitUncProviderModule

- ea: `0x140012560`
- end: `0x14001274a`
- name: `MupInitUncProviderModule`
- size: `490`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140010f18`

## callees

- `0x14000f2a0`
- `0x140012560`
- `0x140012c28`
- `0x140013b34`
- `0x140017238`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400126c9`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400126c9`
- `ntoskrnl!ExReleaseResourceLite` at `0x140012704`
- `ntoskrnl!ExReleaseResourceLite` at `0x140012704`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400125fc`
- `ntoskrnl!RtlInitUnicodeString` at `0x140012663`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400125fc`
- `ntoskrnl!RtlInitUnicodeString` at `0x140012663`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400126f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400126f1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400126b4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400126b4`
- `ntoskrnl!ZwOpenKey` at `0x14001263d`
- `ntoskrnl!ZwOpenKey` at `0x14001269f`
- `ntoskrnl!ZwOpenKey` at `0x14001263d`
- `ntoskrnl!ZwOpenKey` at `0x14001269f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140012710`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140012710`
- `ntoskrnl!ExInitializeRundownProtection` at `0x140012589`
- `ntoskrnl!ExInitializeRundownProtection` at `0x140012589`
- `ntoskrnl!FsRtlRegisterMupCalls` at `0x140012730`
- `ntoskrnl!FsRtlRegisterMupCalls` at `0x140012730`
- `ntoskrnl!ExInitializeResourceLite` at `0x1400125db`
- `ntoskrnl!ExInitializeResourceLite` at `0x1400125db`

## string_xrefs

- `0x1400125e7`: `\Registry\Machine\System\CurrentControlSet\Control\Networkprovider\Order`
- `0x140012651`: `\Registry\Machine\System\CurrentControlSet\Control\Networkprovider\ProviderOrder`

## pseudocode

```c
__int64 MupInitUncProviderModule()
{
  __int64 v0; // rdx
  __int64 v1; // rcx
  __int64 v2; // rdx
  __int64 v3; // rcx
  const WCHAR *ProviderOrderFromRegistry; // rax
  WCHAR *v5; // rbx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF

  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  ExInitializeRundownProtection(&UncProviderModuleRundownRef);
  RfsTimerInitialize(ProviderOrderRefreshTimer);
  MupProviderTable = 9466116;
  qword_14000A770 = (__int64)&qword_14000A768;
  qword_14000A768 = (__int64)&qword_14000A768;
  dword_14000A764 = 1;
  ExInitializeResourceLite(&Resource);
  dword_14000A778 = 0;
  RtlInitUnicodeString(
    &DestinationString,
    L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Networkprovider\\Order");
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Length = 48;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenKey(&MupiOrderKeyHandle, 0x10u, &ObjectAttributes) < 0
    || (MupiOrderKeyHandleValid = 1,
        RtlInitUnicodeString(
          &DestinationString,
          L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Networkprovider\\ProviderOrder"),
        ObjectAttributes.Length = 48,
        ObjectAttributes.ObjectName = &DestinationString,
        ObjectAttributes.RootDirectory = 0,
        ObjectAttributes.Attributes = 576,
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0,
        ZwOpenKey(&MupiNetworkProviderOrderKeyHandle, 0x10u, &ObjectAttributes) < 0) )
  {
    MupiNetworkProviderOrderKeyHandle = 0;
  }
  else
  {
    MupiCleanupOrphanProviderOrderRegValues(v1, v0);
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite(&Resource, 1u);
    ProviderOrderFromRegistry = (const WCHAR *)MupiReadProviderOrderFromRegistry(v3, v2);
    v5 = (WCHAR *)ProviderOrderFromRegistry;
    if ( ProviderOrderFromRegistry )
    {
      MupiSetupKnownProviderList(ProviderOrderFromRegistry);
      ExFreePoolWithTag(v5, 0);
    }
    ExReleaseResourceLite(&Resource);
    KeLeaveCriticalRegion();
  }
  FsRtlRegisterMupCalls(&MupiFsRtlMupCalls);
  return 0;
}

```

## disassembly

```asm
0x140012560  mov     [rsp-8+arg_0], rbx
0x140012565  push    rbp
0x140012566  mov     rbp, rsp
0x140012569  sub     rsp, 60h
0x14001256d  xorps   xmm0, xmm0
0x140012570  lea     rcx, UncProviderModuleRundownRef; RunRef
0x140012577  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14001257b  xor     eax, eax
0x14001257d  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x140012581  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x140012585  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140012589  call    cs:__imp_ExInitializeRundownProtection
0x140012590  nop     dword ptr [rax+rax+00h]
0x140012595  xor     r9d, r9d
0x140012598  lea     r8, MupiProviderOrderChangeHandler
0x14001259f  lea     rcx, ProviderOrderRefreshTimer; DeferredContext
0x1400125a6  call    RfsTimerInitialize
0x1400125ab  lea     rax, qword_14000A768
0x1400125b2  mov     cs:MupProviderTable, 907104h
0x1400125bc  lea     rcx, Resource; Resource
0x1400125c3  mov     cs:qword_14000A770, rax
0x1400125ca  mov     cs:qword_14000A768, rax
0x1400125d1  mov     cs:dword_14000A764, 1
0x1400125db  call    cs:__imp_ExInitializeResourceLite
0x1400125e2  nop     dword ptr [rax+rax+00h]
0x1400125e7  lea     rdx, aRegistryMachin_0; "\\Registry\\Machine\\System\\CurrentCon"...
0x1400125ee  mov     cs:dword_14000A778, 0
0x1400125f8  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400125fc  call    cs:__imp_RtlInitUnicodeString
0x140012603  nop     dword ptr [rax+rax+00h]
0x140012608  mov     ebx, 30h ; '0'
0x14001260d  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x140012615  lea     rax, [rbp+DestinationString]
0x140012619  mov     [rbp+ObjectAttributes.Length], ebx
0x14001261c  xorps   xmm0, xmm0
0x14001261f  mov     [rbp+ObjectAttributes.Attributes], 240h
0x140012626  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14001262a  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14001262e  lea     edx, [rbx-20h]; DesiredAccess
0x140012631  lea     rcx, MupiOrderKeyHandle; KeyHandle
0x140012638  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14001263d  call    cs:__imp_ZwOpenKey
0x140012644  nop     dword ptr [rax+rax+00h]
0x140012649  test    eax, eax
0x14001264b  js      loc_14001271E
0x140012651  lea     rdx, aRegistryMachin_1; "\\Registry\\Machine\\System\\CurrentCon"...
0x140012658  mov     cs:MupiOrderKeyHandleValid, 1
0x14001265f  lea     rcx, [rbp+DestinationString]; DestinationString
0x140012663  call    cs:__imp_RtlInitUnicodeString
0x14001266a  nop     dword ptr [rax+rax+00h]
0x14001266f  lea     rax, [rbp+DestinationString]
0x140012673  mov     [rbp+ObjectAttributes.Length], ebx
0x140012676  xorps   xmm0, xmm0
0x140012679  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14001267d  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140012681  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x140012689  lea     edx, [rbx-20h]; DesiredAccess
0x14001268c  mov     [rbp+ObjectAttributes.Attributes], 240h
0x140012693  lea     rcx, MupiNetworkProviderOrderKeyHandle; KeyHandle
0x14001269a  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14001269f  call    cs:__imp_ZwOpenKey
0x1400126a6  nop     dword ptr [rax+rax+00h]
0x1400126ab  test    eax, eax
0x1400126ad  js      short loc_14001271E
0x1400126af  call    MupiCleanupOrphanProviderOrderRegValues
0x1400126b4  call    cs:__imp_KeEnterCriticalRegion
0x1400126bb  nop     dword ptr [rax+rax+00h]
0x1400126c0  mov     dl, 1; Wait
0x1400126c2  lea     rcx, Resource; Resource
0x1400126c9  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400126d0  nop     dword ptr [rax+rax+00h]
0x1400126d5  call    MupiReadProviderOrderFromRegistry
0x1400126da  mov     rbx, rax
0x1400126dd  test    rax, rax
0x1400126e0  jz      short loc_1400126FD
0x1400126e2  xor     edx, edx
0x1400126e4  mov     rcx, rax; SourceString
0x1400126e7  call    MupiSetupKnownProviderList
0x1400126ec  xor     edx, edx; Tag
0x1400126ee  mov     rcx, rbx; P
0x1400126f1  call    cs:__imp_ExFreePoolWithTag
0x1400126f8  nop     dword ptr [rax+rax+00h]
0x1400126fd  lea     rcx, Resource; Resource
0x140012704  call    cs:__imp_ExReleaseResourceLite
0x14001270b  nop     dword ptr [rax+rax+00h]
0x140012710  call    cs:__imp_KeLeaveCriticalRegion
0x140012717  nop     dword ptr [rax+rax+00h]
0x14001271c  jmp     short loc_140012729
0x14001271e  mov     cs:MupiNetworkProviderOrderKeyHandle, 0
0x140012729  lea     rcx, MupiFsRtlMupCalls
0x140012730  call    cs:__imp_FsRtlRegisterMupCalls
0x140012737  nop     dword ptr [rax+rax+00h]
0x14001273c  mov     rbx, [rsp+60h+arg_0]
0x140012741  xor     eax, eax
0x140012743  add     rsp, 60h
0x140012747  pop     rbp
0x140012748  retn
```
