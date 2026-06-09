# DfscInitializeAndRegisterDAKeyChangeNotification

- ea: `0x140018544`
- end: `0x1400186b5`
- name: `DfscInitializeAndRegisterDAKeyChangeNotification`
- size: `369`
- prototype: `void()`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14002a488`

## callees

- `0x140011760`
- `0x140018544`
- `0x1400186bc`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x1400185a2`
- `ntoskrnl!ZwOpenKey` at `0x1400185a2`
- `ntoskrnl!ZwNotifyChangeKey` at `0x14001862d`
- `ntoskrnl!ZwNotifyChangeKey` at `0x14001862d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140018697`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140018697`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001868b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001868b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400185e7`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400185e7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400185d2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400185d2`

## pseudocode

```c
void DfscInitializeAndRegisterDAKeyChangeNotification()
{
  struct _UNICODE_STRING v0; // [rsp+50h] [rbp+17h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp+27h] BYREF
  int v2; // [rsp+A0h] [rbp+67h] BYREF

  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  v2 = 0;
  DAConnectivityMonitor = 0;
  SiteNameRegKeyMonitor = 0;
  ObjectAttributes.RootDirectory = 0;
  v0 = 0;
  ObjectAttributes.ObjectName = &Destination;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenKey(&DAConnectivityMonitor, 0x10u, &ObjectAttributes) >= 0 )
  {
    qword_14000C400 = 0;
    qword_14000C3F8 = (__int64)DfscDAConnectivityChangeHandler;
    *(_QWORD *)ApcRoutine = 0;
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite(&Resource, 1u);
    ZwNotifyChangeKey(DAConnectivityMonitor, 0, ApcRoutine, (PVOID)1, &IoStatusBlock, 4u, 0, 0, 0, 1u);
    v0.Buffer = L"UseDcLocatorSiteName";
    *(_DWORD *)&v0.Length = 2621480;
    if ( DfscGetUlongRegistryParameter(DAConnectivityMonitor, &v0, &v2) >= 0 )
    {
      if ( v2 )
      {
        byte_14000C76E = 1;
        goto LABEL_7;
      }
      byte_14000C76E = 0;
    }
    if ( !byte_14000C76E )
    {
LABEL_8:
      ExReleaseResourceLite(&Resource);
      KeLeaveCriticalRegion();
      return;
    }
LABEL_7:
    DfscInitializeSiteNameAndRegisterChangeNotification();
    goto LABEL_8;
  }
}

```

## disassembly

```asm
0x140018544  mov     [rsp-8+arg_8], rbx
0x140018549  push    rbp
0x14001854a  lea     rbp, [rsp-57h]
0x14001854f  sub     rsp, 90h
0x140018556  xor     ebx, ebx
0x140018558  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140018560  xorps   xmm0, xmm0
0x140018563  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x14001856b  lea     rax, Destination
0x140018572  mov     [rbp+57h+arg_0], ebx
0x140018575  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140018579  mov     cs:DAConnectivityMonitor, rbx
0x140018580  lea     edx, [rbx+10h]; DesiredAccess
0x140018583  mov     cs:SiteNameRegKeyMonitor, rbx
0x14001858a  lea     rcx, DAConnectivityMonitor; KeyHandle
0x140018591  mov     [rbp+57h+ObjectAttributes.RootDirectory], rbx
0x140018595  movups  [rbp+57h+var_40], xmm0
0x140018599  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14001859d  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400185a2  call    cs:__imp_ZwOpenKey
0x1400185a9  nop     dword ptr [rax+rax+00h]
0x1400185ae  test    eax, eax
0x1400185b0  js      loc_1400186A3
0x1400185b6  lea     rax, DfscDAConnectivityChangeHandler
0x1400185bd  mov     cs:qword_14000C400, rbx
0x1400185c4  mov     cs:qword_14000C3F8, rax
0x1400185cb  mov     cs:ApcRoutine, rbx
0x1400185d2  call    cs:__imp_KeEnterCriticalRegion
0x1400185d9  nop     dword ptr [rax+rax+00h]
0x1400185de  mov     dl, 1; Wait
0x1400185e0  lea     rcx, Resource; Resource
0x1400185e7  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400185ee  nop     dword ptr [rax+rax+00h]
0x1400185f3  mov     rcx, cs:DAConnectivityMonitor; KeyHandle
0x1400185fa  lea     rax, IoStatusBlock
0x140018601  mov     [rsp+90h+Asynchronous], 1; Asynchronous
0x140018606  lea     r9d, [rbx+1]; ApcContext
0x14001860a  mov     [rsp+90h+BufferSize], ebx; BufferSize
0x14001860e  lea     r8, ApcRoutine; ApcRoutine
0x140018615  mov     [rsp+90h+Buffer], rbx; Buffer
0x14001861a  xor     edx, edx; Event
0x14001861c  mov     [rsp+90h+WatchTree], bl; WatchTree
0x140018620  mov     [rsp+90h+CompletionFilter], 4; CompletionFilter
0x140018628  mov     [rsp+90h+IoStatusBlock], rax; IoStatusBlock
0x14001862d  call    cs:__imp_ZwNotifyChangeKey
0x140018634  nop     dword ptr [rax+rax+00h]
0x140018639  mov     rcx, cs:DAConnectivityMonitor
0x140018640  lea     rax, aUsedclocatorsi; "UseDcLocatorSiteName"
0x140018647  lea     r8, [rbp+57h+arg_0]
0x14001864b  mov     qword ptr [rbp+57h+var_40+8], rax
0x14001864f  lea     rdx, [rbp+57h+var_40]
0x140018653  mov     dword ptr [rbp+57h+var_40], 280028h
0x14001865a  call    DfscGetUlongRegistryParameter
0x14001865f  test    eax, eax
0x140018661  js      short loc_140018677
0x140018663  cmp     [rbp+57h+arg_0], ebx
0x140018666  jz      short loc_140018671
0x140018668  mov     cs:byte_14000C76E, 1
0x14001866f  jmp     short loc_14001867F
0x140018671  mov     cs:byte_14000C76E, bl
0x140018677  cmp     cs:byte_14000C76E, bl
0x14001867d  jz      short loc_140018684
0x14001867f  call    DfscInitializeSiteNameAndRegisterChangeNotification
0x140018684  lea     rcx, Resource; Resource
0x14001868b  call    cs:__imp_ExReleaseResourceLite
0x140018692  nop     dword ptr [rax+rax+00h]
0x140018697  call    cs:__imp_KeLeaveCriticalRegion
0x14001869e  nop     dword ptr [rax+rax+00h]
0x1400186a3  mov     rbx, [rsp+90h+arg_8]
0x1400186ab  add     rsp, 90h
0x1400186b2  pop     rbp
0x1400186b3  retn
```
