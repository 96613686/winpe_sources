# DfscInitializeSiteNameAndRegisterChangeNotification

- ea: `0x1400186bc`
- end: `0x1400187dd`
- name: `DfscInitializeSiteNameAndRegisterChangeNotification`
- size: `289`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140018320`
- `0x140018544`

## callees

- `0x1400186bc`
- `0x140018994`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400186f7`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400186f7`
- `ntoskrnl!ZwOpenKey` at `0x140018739`
- `ntoskrnl!ZwOpenKey` at `0x140018739`
- `ntoskrnl!ZwNotifyChangeKey` at `0x1400187c2`
- `ntoskrnl!ZwNotifyChangeKey` at `0x1400187c2`

## string_xrefs

- `0x1400186ec`: `\Registry\Machine\System\CurrentControlSet\Services\Netlogon\Parameters`

## pseudocode

```c
NTSTATUS DfscInitializeSiteNameAndRegisterChangeNotification()
{
  NTSTATUS result; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp+17h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp+27h] BYREF

  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  if ( SiteNameRegKeyMonitor )
    return DfscUpdateSiteNameFromRegistry();
  RtlInitUnicodeString(
    &DestinationString,
    L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\Netlogon\\Parameters");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = ZwOpenKey(&SiteNameRegKeyMonitor, 0x10u, &ObjectAttributes);
  if ( result < 0 )
    SiteNameRegKeyMonitor = 0;
  if ( SiteNameRegKeyMonitor )
  {
    qword_14000C558 = (__int64)DfscSiteNameChangeHandler;
    qword_14000C560 = 0;
    *(_QWORD *)qword_14000C548 = 0;
    ZwNotifyChangeKey(SiteNameRegKeyMonitor, 0, qword_14000C548, (PVOID)1, &stru_14000C568, 4u, 0, 0, 0, 1u);
    return DfscUpdateSiteNameFromRegistry();
  }
  return result;
}

```

## disassembly

```asm
0x1400186bc  push    rbp
0x1400186be  lea     rbp, [rsp-57h]
0x1400186c3  sub     rsp, 90h
0x1400186ca  xorps   xmm0, xmm0
0x1400186cd  xor     eax, eax
0x1400186cf  cmp     cs:SiteNameRegKeyMonitor, rax
0x1400186d6  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1400186da  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1400186de  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1400186e2  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1400186e6  jnz     loc_1400187CE
0x1400186ec  lea     rdx, aRegistryMachin_1; "\\Registry\\Machine\\System\\CurrentCon"...
0x1400186f3  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400186f7  call    cs:__imp_RtlInitUnicodeString
0x1400186fe  nop     dword ptr [rax+rax+00h]
0x140018703  lea     rax, [rbp+57h+DestinationString]
0x140018707  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14001870e  xorps   xmm0, xmm0
0x140018711  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140018715  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140018719  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x140018721  mov     edx, 10h; DesiredAccess
0x140018726  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x14001872d  lea     rcx, SiteNameRegKeyMonitor; KeyHandle
0x140018734  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140018739  call    cs:__imp_ZwOpenKey
0x140018740  nop     dword ptr [rax+rax+00h]
0x140018745  test    eax, eax
0x140018747  jns     short loc_140018754
0x140018749  mov     cs:SiteNameRegKeyMonitor, 0
0x140018754  mov     rcx, cs:SiteNameRegKeyMonitor; KeyHandle
0x14001875b  test    rcx, rcx
0x14001875e  jz      short loc_1400187D3
0x140018760  mov     [rsp+90h+Asynchronous], 1; Asynchronous
0x140018765  lea     rax, DfscSiteNameChangeHandler
0x14001876c  mov     [rsp+90h+BufferSize], 0; BufferSize
0x140018774  lea     r8, qword_14000C548; ApcRoutine
0x14001877b  mov     [rsp+90h+Buffer], 0; Buffer
0x140018784  mov     r9d, 1; ApcContext
0x14001878a  mov     cs:qword_14000C558, rax
0x140018791  xor     edx, edx; Event
0x140018793  mov     [rsp+90h+WatchTree], 0; WatchTree
0x140018798  lea     rax, stru_14000C568
0x14001879f  mov     [rsp+90h+CompletionFilter], 4; CompletionFilter
0x1400187a7  mov     [rsp+90h+IoStatusBlock], rax; IoStatusBlock
0x1400187ac  mov     cs:qword_14000C560, 0
0x1400187b7  mov     cs:qword_14000C548, 0
0x1400187c2  call    cs:__imp_ZwNotifyChangeKey
0x1400187c9  nop     dword ptr [rax+rax+00h]
0x1400187ce  call    DfscUpdateSiteNameFromRegistry
0x1400187d3  add     rsp, 90h
0x1400187da  pop     rbp
0x1400187db  retn
```
