# DsWaitForSamService

- ea: `0x1800acc30`
- end: `0x1800acd7f`
- name: `DsWaitForSamService`
- size: `335`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800a94a0`
- `0x1800adff0`

## callees

- `0x1800acc30`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800acc87`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800acc87`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800acd36`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800acd42`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800acd36`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800acd42`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800acd51`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800acd51`
- `ntdll!NtClose` at `0x1800acd66`
- `ntdll!NtClose` at `0x1800acd71`
- `ntdll!NtClose` at `0x1800acd66`
- `ntdll!NtClose` at `0x1800acd71`
- `ntdll!NtCreateEvent` at `0x1800acd07`
- `ntdll!NtCreateEvent` at `0x1800acd07`
- `ntdll!NtOpenEvent` at `0x1800acce1`
- `ntdll!NtOpenEvent` at `0x1800acd28`
- `ntdll!NtOpenEvent` at `0x1800acce1`
- `ntdll!NtOpenEvent` at `0x1800acd28`
- `ntdll!RtlInitUnicodeString` at `0x1800acca0`
- `ntdll!RtlInitUnicodeString` at `0x1800acca0`

## string_xrefs

- `0x1800acc95`: `\SAM_SERVICE_STARTED`

## pseudocode

```c
char DsWaitForSamService()
{
  NTSTATUS v1; // eax
  NTSTATUS v2; // eax
  DWORD v3; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  ULONG SecurityDescriptorSize; // [rsp+80h] [rbp+10h] BYREF
  void *EventHandle; // [rsp+88h] [rbp+18h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+90h] [rbp+20h] BYREF

  DestinationString = 0;
  EventHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  SecurityDescriptor = 0;
  SecurityDescriptorSize = 0;
  if ( *(_DWORD *)gfADAM )
    return 1;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         L"D:(A;;0x80100000;;;WD)(A;;RPWPCRCCDCLCLORCWOWDSDDTSW;;;SY)",
         1u,
         &SecurityDescriptor,
         &SecurityDescriptorSize) )
  {
    RtlInitUnicodeString(&DestinationString, L"\\SAM_SERVICE_STARTED");
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.SecurityDescriptor = SecurityDescriptor;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 0;
    ObjectAttributes.SecurityQualityOfService = 0;
    v1 = NtOpenEvent(&EventHandle, 0x100002u, &ObjectAttributes);
    if ( v1 >= 0 )
      goto LABEL_11;
    if ( v1 != -1073741772 )
      goto LABEL_10;
    v2 = NtCreateEvent(&EventHandle, 0x100002u, &ObjectAttributes, NotificationEvent, 0);
    if ( v2 == 0x40000000 || v2 == -1073741771 )
      v2 = NtOpenEvent(&EventHandle, 0x100002u, &ObjectAttributes);
    if ( v2 >= 0 )
    {
LABEL_11:
      LocalFree(SecurityDescriptor);
      do
        v3 = WaitForSingleObject(EventHandle, 0x1388u);
      while ( v3 == 258 );
      if ( !v3 )
      {
        NtClose(EventHandle);
        return 1;
      }
      NtClose(EventHandle);
    }
    else
    {
LABEL_10:
      LocalFree(SecurityDescriptor);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800acc30  push    rbp
0x1800acc32  mov     rbp, rsp
0x1800acc35  sub     rsp, 70h
0x1800acc39  cmp     cs:gfADAM, 0
0x1800acc40  xorps   xmm0, xmm0
0x1800acc43  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1800acc47  mov     [rbp+EventHandle], 0
0x1800acc4f  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1800acc53  mov     [rbp+SecurityDescriptor], 0
0x1800acc5b  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1800acc5f  mov     [rbp+SecurityDescriptorSize], 0
0x1800acc66  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800acc6a  jz      short loc_1800ACC73
0x1800acc6c  mov     al, 1
0x1800acc6e  jmp     loc_1800ACD79
0x1800acc73  lea     r9, [rbp+SecurityDescriptorSize]; SecurityDescriptorSize
0x1800acc77  mov     edx, 1; StringSDRevision
0x1800acc7c  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1800acc80  lea     rcx, aDA0x80100000Wd; "D:(A;;0x80100000;;;WD)(A;;RPWPCRCCDCLCL"...
0x1800acc87  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800acc8d  test    eax, eax
0x1800acc8f  jz      loc_1800ACD77
0x1800acc95  lea     rdx, aSamServiceStar; "\\SAM_SERVICE_STARTED"
0x1800acc9c  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800acca0  call    cs:__imp_RtlInitUnicodeString
0x1800acca6  lea     rax, [rbp+DestinationString]
0x1800accaa  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800accb1  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1800accb5  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1800accb9  mov     rax, [rbp+SecurityDescriptor]
0x1800accbd  lea     rcx, [rbp+EventHandle]; EventHandle
0x1800accc1  mov     edx, 100002h; DesiredAccess
0x1800accc6  mov     [rbp+ObjectAttributes.SecurityDescriptor], rax
0x1800accca  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1800accd2  mov     [rbp+ObjectAttributes.Attributes], 0
0x1800accd9  mov     [rbp+ObjectAttributes.SecurityQualityOfService], 0
0x1800acce1  call    cs:__imp_NtOpenEvent
0x1800acce7  test    eax, eax
0x1800acce9  jns     short loc_1800ACD3E
0x1800acceb  cmp     eax, 0C0000034h
0x1800accf0  jnz     short loc_1800ACD32
0x1800accf2  xor     r9d, r9d; EventType
0x1800accf5  mov     [rsp+70h+InitialState], 0; InitialState
0x1800accfa  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1800accfe  mov     edx, 100002h; DesiredAccess
0x1800acd03  lea     rcx, [rbp+EventHandle]; EventHandle
0x1800acd07  call    cs:__imp_NtCreateEvent
0x1800acd0d  cmp     eax, 40000000h
0x1800acd12  jz      short loc_1800ACD1B
0x1800acd14  cmp     eax, 0C0000035h
0x1800acd19  jnz     short loc_1800ACD2E
0x1800acd1b  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1800acd1f  mov     edx, 100002h; DesiredAccess
0x1800acd24  lea     rcx, [rbp+EventHandle]; EventHandle
0x1800acd28  call    cs:__imp_NtOpenEvent
0x1800acd2e  test    eax, eax
0x1800acd30  jns     short loc_1800ACD3E
0x1800acd32  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x1800acd36  call    cs:__imp_LocalFree
0x1800acd3c  jmp     short loc_1800ACD77
0x1800acd3e  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x1800acd42  call    cs:__imp_LocalFree
0x1800acd48  mov     rcx, [rbp+EventHandle]; hHandle
0x1800acd4c  mov     edx, 1388h; dwMilliseconds
0x1800acd51  call    cs:__imp_WaitForSingleObject
0x1800acd57  cmp     eax, 102h
0x1800acd5c  jz      short loc_1800ACD48
0x1800acd5e  mov     rcx, [rbp+EventHandle]; Handle
0x1800acd62  test    eax, eax
0x1800acd64  jnz     short loc_1800ACD71
0x1800acd66  call    cs:__imp_NtClose
0x1800acd6c  jmp     loc_1800ACC6C
0x1800acd71  call    cs:__imp_NtClose
0x1800acd77  xor     al, al
0x1800acd79  add     rsp, 70h
0x1800acd7d  pop     rbp
0x1800acd7e  retn
```
