# MupInitUncProviderModule

- ea: `0x140012510`
- end: `0x1400126fa`
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
- `0x140012510`
- `0x140012bd8`
- `0x140013ae4`
- `0x1400171e8`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140012679`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140012679`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400126b4`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400126b4`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400125ac`
- `ntoskrnl!RtlInitUnicodeString` at `0x140012613`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400125ac`
- `ntoskrnl!RtlInitUnicodeString` at `0x140012613`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400126a1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400126a1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140012664`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140012664`
- `ntoskrnl!ZwOpenKey` at `0x1400125ed`
- `ntoskrnl!ZwOpenKey` at `0x14001264f`
- `ntoskrnl!ZwOpenKey` at `0x1400125ed`
- `ntoskrnl!ZwOpenKey` at `0x14001264f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400126c0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400126c0`
- `ntoskrnl!ExInitializeRundownProtection` at `0x140012539`
- `ntoskrnl!ExInitializeRundownProtection` at `0x140012539`
- `ntoskrnl!FsRtlRegisterMupCalls` at `0x1400126e0`
- `ntoskrnl!FsRtlRegisterMupCalls` at `0x1400126e0`
- `ntoskrnl!ExInitializeResourceLite` at `0x14001258b`
- `ntoskrnl!ExInitializeResourceLite` at `0x14001258b`

## string_xrefs

- `0x140012597`: `\Registry\Machine\System\CurrentControlSet\Control\Networkprovider\Order`
- `0x140012601`: `\Registry\Machine\System\CurrentControlSet\Control\Networkprovider\ProviderOrder`

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
0x140012510  mov     [rsp-8+arg_0], rbx
0x140012515  push    rbp
0x140012516  mov     rbp, rsp
0x140012519  sub     rsp, 60h
0x14001251d  xorps   xmm0, xmm0
0x140012520  lea     rcx, UncProviderModuleRundownRef; RunRef
0x140012527  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14001252b  xor     eax, eax
0x14001252d  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x140012531  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x140012535  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140012539  call    cs:__imp_ExInitializeRundownProtection
0x140012540  nop     dword ptr [rax+rax+00h]
0x140012545  xor     r9d, r9d
0x140012548  lea     r8, MupiProviderOrderChangeHandler
0x14001254f  lea     rcx, ProviderOrderRefreshTimer; DeferredContext
0x140012556  call    RfsTimerInitialize
0x14001255b  lea     rax, qword_14000A768
0x140012562  mov     cs:MupProviderTable, 907104h
0x14001256c  lea     rcx, Resource; Resource
0x140012573  mov     cs:qword_14000A770, rax
0x14001257a  mov     cs:qword_14000A768, rax
0x140012581  mov     cs:dword_14000A764, 1
0x14001258b  call    cs:__imp_ExInitializeResourceLite
0x140012592  nop     dword ptr [rax+rax+00h]
0x140012597  lea     rdx, aRegistryMachin_0; "\\Registry\\Machine\\System\\CurrentCon"...
0x14001259e  mov     cs:dword_14000A778, 0
0x1400125a8  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400125ac  call    cs:__imp_RtlInitUnicodeString
0x1400125b3  nop     dword ptr [rax+rax+00h]
0x1400125b8  mov     ebx, 30h ; '0'
0x1400125bd  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1400125c5  lea     rax, [rbp+DestinationString]
0x1400125c9  mov     [rbp+ObjectAttributes.Length], ebx
0x1400125cc  xorps   xmm0, xmm0
0x1400125cf  mov     [rbp+ObjectAttributes.Attributes], 240h
0x1400125d6  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1400125da  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1400125de  lea     edx, [rbx-20h]; DesiredAccess
0x1400125e1  lea     rcx, MupiOrderKeyHandle; KeyHandle
0x1400125e8  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1400125ed  call    cs:__imp_ZwOpenKey
0x1400125f4  nop     dword ptr [rax+rax+00h]
0x1400125f9  test    eax, eax
0x1400125fb  js      loc_1400126CE
0x140012601  lea     rdx, aRegistryMachin_1; "\\Registry\\Machine\\System\\CurrentCon"...
0x140012608  mov     cs:MupiOrderKeyHandleValid, 1
0x14001260f  lea     rcx, [rbp+DestinationString]; DestinationString
0x140012613  call    cs:__imp_RtlInitUnicodeString
0x14001261a  nop     dword ptr [rax+rax+00h]
0x14001261f  lea     rax, [rbp+DestinationString]
0x140012623  mov     [rbp+ObjectAttributes.Length], ebx
0x140012626  xorps   xmm0, xmm0
0x140012629  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14001262d  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140012631  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x140012639  lea     edx, [rbx-20h]; DesiredAccess
0x14001263c  mov     [rbp+ObjectAttributes.Attributes], 240h
0x140012643  lea     rcx, MupiNetworkProviderOrderKeyHandle; KeyHandle
0x14001264a  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14001264f  call    cs:__imp_ZwOpenKey
0x140012656  nop     dword ptr [rax+rax+00h]
0x14001265b  test    eax, eax
0x14001265d  js      short loc_1400126CE
0x14001265f  call    MupiCleanupOrphanProviderOrderRegValues
0x140012664  call    cs:__imp_KeEnterCriticalRegion
0x14001266b  nop     dword ptr [rax+rax+00h]
0x140012670  mov     dl, 1; Wait
0x140012672  lea     rcx, Resource; Resource
0x140012679  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140012680  nop     dword ptr [rax+rax+00h]
0x140012685  call    MupiReadProviderOrderFromRegistry
0x14001268a  mov     rbx, rax
0x14001268d  test    rax, rax
0x140012690  jz      short loc_1400126AD
0x140012692  xor     edx, edx
0x140012694  mov     rcx, rax; SourceString
0x140012697  call    MupiSetupKnownProviderList
0x14001269c  xor     edx, edx; Tag
0x14001269e  mov     rcx, rbx; P
0x1400126a1  call    cs:__imp_ExFreePoolWithTag
0x1400126a8  nop     dword ptr [rax+rax+00h]
0x1400126ad  lea     rcx, Resource; Resource
0x1400126b4  call    cs:__imp_ExReleaseResourceLite
0x1400126bb  nop     dword ptr [rax+rax+00h]
0x1400126c0  call    cs:__imp_KeLeaveCriticalRegion
0x1400126c7  nop     dword ptr [rax+rax+00h]
0x1400126cc  jmp     short loc_1400126D9
0x1400126ce  mov     cs:MupiNetworkProviderOrderKeyHandle, 0
0x1400126d9  lea     rcx, MupiFsRtlMupCalls
0x1400126e0  call    cs:__imp_FsRtlRegisterMupCalls
0x1400126e7  nop     dword ptr [rax+rax+00h]
0x1400126ec  mov     rbx, [rsp+60h+arg_0]
0x1400126f1  xor     eax, eax
0x1400126f3  add     rsp, 60h
0x1400126f7  pop     rbp
0x1400126f8  retn
```
