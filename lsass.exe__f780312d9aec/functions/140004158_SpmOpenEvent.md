# SpmOpenEvent

- ea: `0x140004158`
- end: `0x1400041ea`
- name: `SpmOpenEvent`
- size: `146`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400031bc`
- `0x140003ce8`

## callees

- `0x140004158`

## import_xrefs

- `ntdll!NtOpenEvent` at `0x1400041c2`
- `ntdll!NtOpenEvent` at `0x1400041c2`
- `ntdll!RtlNtStatusToDosError` at `0x1400041ce`
- `ntdll!RtlNtStatusToDosError` at `0x1400041ce`
- `ntdll!RtlInitUnicodeString` at `0x140004189`
- `ntdll!RtlInitUnicodeString` at `0x140004189`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400041d6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400041d6`

## string_xrefs

- `0x140004168`: `\SECURITY\LSA_AUTHENTICATION_INITIALIZED`

## pseudocode

```c
void *SpmOpenEvent()
{
  int v0; // eax
  ULONG v1; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF
  void *EventHandle; // [rsp+80h] [rbp+20h] BYREF

  EventHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\SECURITY\\LSA_AUTHENTICATION_INITIALIZED");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v0 = NtOpenEvent(&EventHandle, 0x1F0003u, &ObjectAttributes);
  if ( v0 >= 0 )
    return EventHandle;
  v1 = RtlNtStatusToDosError(v0);
  SetLastError(v1);
  return 0;
}

```

## disassembly

```asm
0x140004158  mov     [rsp-8+EventHandle], r8
0x14000415d  push    rbp
0x14000415e  mov     rbp, rsp
0x140004161  sub     rsp, 60h
0x140004165  xorps   xmm0, xmm0
0x140004168  lea     rdx, aSecurityLsaAut; "\\SECURITY\\LSA_AUTHENTICATION_INITIALI"...
0x14000416f  xor     eax, eax
0x140004171  lea     rcx, [rbp+DestinationString]; DestinationString
0x140004175  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x140004179  mov     [rbp+EventHandle], rax
0x14000417d  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x140004181  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x140004185  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140004189  call    cs:__imp_RtlInitUnicodeString
0x14000418f  lea     rax, [rbp+DestinationString]
0x140004193  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x14000419a  xorps   xmm0, xmm0
0x14000419d  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1400041a1  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1400041a5  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1400041ad  mov     edx, 1F0003h; DesiredAccess
0x1400041b2  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x1400041b9  lea     rcx, [rbp+EventHandle]; EventHandle
0x1400041bd  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1400041c2  call    cs:__imp_NtOpenEvent
0x1400041c8  test    eax, eax
0x1400041ca  jns     short loc_1400041E0
0x1400041cc  mov     ecx, eax; Status
0x1400041ce  call    cs:__imp_RtlNtStatusToDosError
0x1400041d4  mov     ecx, eax; dwErrCode
0x1400041d6  call    cs:__imp_SetLastError
0x1400041dc  xor     eax, eax
0x1400041de  jmp     short loc_1400041E4
0x1400041e0  mov     rax, [rbp+EventHandle]
0x1400041e4  add     rsp, 60h
0x1400041e8  pop     rbp
0x1400041e9  retn
```
