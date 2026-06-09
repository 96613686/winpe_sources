# DsRolepInitializeOperationHandle

- ea: `0x180015ff0`
- end: `0x180016166`
- name: `DsRolepInitializeOperationHandle`
- size: `374`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180003ff0`
- `0x180005400`
- `0x1800058a0`
- `0x180005e40`
- `0x1800065a0`
- `0x180006c30`
- `0x180014524`

## callees

- `0x180015670`
- `0x180015ff0`
- `0x1800161a8`
- `0x180020dbc`

## import_xrefs

- `ntdll!NtResetEvent` at `0x1800160d5`
- `ntdll!NtResetEvent` at `0x1800160d5`
- `ntdll!RtlNtStatusToDosError` at `0x18001612f`
- `ntdll!RtlNtStatusToDosError` at `0x18001612f`
- `ntdll!NtCreateEvent` at `0x1800160bd`
- `ntdll!NtCreateEvent` at `0x1800160f8`
- `ntdll!NtCreateEvent` at `0x1800160bd`
- `ntdll!NtCreateEvent` at `0x1800160f8`
- `ntdll!RtlAcquireResourceExclusive` at `0x180016020`
- `ntdll!RtlAcquireResourceExclusive` at `0x180016020`
- `ntdll!RtlReleaseResource` at `0x18001611f`
- `ntdll!RtlReleaseResource` at `0x18001611f`
- `ntdll!RtlInitUnicodeString` at `0x180016079`
- `ntdll!RtlInitUnicodeString` at `0x180016079`

## string_xrefs

- `0x18001605b`: `Cannot get user Token for Format Message: %ul\n`

## pseudocode

```c
__int64 DsRolepInitializeOperationHandle()
{
  int Event; // edi
  ULONG v1; // ebx
  ULONG ImpersonationToken; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF

  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  RtlAcquireResourceExclusive(&DsRolepCurrentOperationHandle, 1u);
  if ( dword_18004E1A0 )
  {
    Event = 0;
    v1 = 8221;
  }
  else
  {
    ImpersonationToken = DsRolepGetImpersonationToken(&NewTokenHandle);
    v1 = ImpersonationToken;
    if ( ImpersonationToken )
    {
      NewTokenHandle = 0;
      DsRolepLogPrintRoutine(2, "Cannot get user Token for Format Message: %ul\n", ImpersonationToken);
      v1 = 0;
    }
    RtlInitUnicodeString(&DestinationString, L"\\DsRoleLsaEventName");
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 0;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    Event = NtCreateEvent(&Handle, 0x1F0003u, &ObjectAttributes, NotificationEvent, 0);
    if ( Event == -1073741771 )
      Event = NtResetEvent(Handle, 0);
    if ( Event >= 0 )
    {
      Event = NtCreateEvent(&qword_18004E1C0, 0x100002u, 0, NotificationEvent, 0);
      if ( Event >= 0 )
      {
        dword_18004E1A0 = 1;
        HIDWORD(qword_18004E1D0) = 1073771049;
      }
    }
  }
  RtlReleaseResource(&DsRolepCurrentOperationHandle);
  if ( v1 )
    goto LABEL_13;
  if ( Event < 0 )
  {
    v1 = RtlNtStatusToDosError(Event);
LABEL_13:
    DsRolepLogPrintRoutine(1, "Internal error trying to initialize operation handle (%lu).\n", v1);
    DsRolepResetOperationHandle(0);
  }
  return v1;
}

```

## disassembly

```asm
0x180015ff0  mov     [rsp-8+arg_0], rbx
0x180015ff5  mov     [rsp-8+arg_8], rdi
0x180015ffa  push    rbp
0x180015ffb  mov     rbp, rsp
0x180015ffe  sub     rsp, 70h
0x180016002  xorps   xmm0, xmm0
0x180016005  lea     rcx, DsRolepCurrentOperationHandle; Resource
0x18001600c  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180016010  xor     eax, eax
0x180016012  mov     dl, 1; Wait
0x180016014  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x180016018  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18001601c  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180016020  call    cs:__imp_RtlAcquireResourceExclusive
0x180016026  cmp     cs:dword_18004E1A0, 0
0x18001602d  jz      short loc_18001603B
0x18001602f  xor     edi, edi
0x180016031  mov     ebx, 201Dh
0x180016036  jmp     loc_180016118
0x18001603b  lea     rcx, NewTokenHandle; NewTokenHandle
0x180016042  call    DsRolepGetImpersonationToken
0x180016047  mov     ebx, eax
0x180016049  test    eax, eax
0x18001604b  jz      short loc_18001606E
0x18001604d  mov     r8d, eax
0x180016050  mov     cs:NewTokenHandle, 0
0x18001605b  lea     rdx, aCannotGetUserT; "Cannot get user Token for Format Messag"...
0x180016062  mov     ecx, 2
0x180016067  call    DsRolepLogPrintRoutine
0x18001606c  xor     ebx, ebx
0x18001606e  lea     rdx, aDsrolelsaevent; "\\DsRoleLsaEventName"
0x180016075  lea     rcx, [rbp+DestinationString]; DestinationString
0x180016079  call    cs:__imp_RtlInitUnicodeString
0x18001607f  lea     rax, [rbp+DestinationString]
0x180016083  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18001608a  xorps   xmm0, xmm0
0x18001608d  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180016091  xor     r9d, r9d; EventType
0x180016094  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x18001609c  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1800160a0  mov     [rbp+ObjectAttributes.Attributes], 0
0x1800160a7  mov     edx, 1F0003h; DesiredAccess
0x1800160ac  mov     [rsp+70h+InitialState], 0; InitialState
0x1800160b1  lea     rcx, Handle; EventHandle
0x1800160b8  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800160bd  call    cs:__imp_NtCreateEvent
0x1800160c3  mov     edi, eax
0x1800160c5  cmp     eax, 0C0000035h
0x1800160ca  jnz     short loc_1800160DD
0x1800160cc  mov     rcx, cs:Handle; EventHandle
0x1800160d3  xor     edx, edx; NumberOfWaitingThreads
0x1800160d5  call    cs:__imp_NtResetEvent
0x1800160db  mov     edi, eax
0x1800160dd  test    edi, edi
0x1800160df  js      short loc_180016118
0x1800160e1  xor     r9d, r9d; EventType
0x1800160e4  mov     [rsp+70h+InitialState], 0; InitialState
0x1800160e9  xor     r8d, r8d; ObjectAttributes
0x1800160ec  lea     rcx, qword_18004E1C0; EventHandle
0x1800160f3  mov     edx, 100002h; DesiredAccess
0x1800160f8  call    cs:__imp_NtCreateEvent
0x1800160fe  mov     edi, eax
0x180016100  test    eax, eax
0x180016102  js      short loc_180016118
0x180016104  mov     cs:dword_18004E1A0, 1
0x18001610e  mov     dword ptr cs:qword_18004E1D0+4, 40007229h
0x180016118  lea     rcx, DsRolepCurrentOperationHandle; Resource
0x18001611f  call    cs:__imp_RtlReleaseResource
0x180016125  test    ebx, ebx
0x180016127  jnz     short loc_180016137
0x180016129  test    edi, edi
0x18001612b  jns     short loc_180016152
0x18001612d  mov     ecx, edi; Status
0x18001612f  call    cs:__imp_RtlNtStatusToDosError
0x180016135  mov     ebx, eax
0x180016137  mov     r8d, ebx
0x18001613a  lea     rdx, aInternalErrorT; "Internal error trying to initialize ope"...
0x180016141  mov     ecx, 1
0x180016146  call    DsRolepLogPrintRoutine
0x18001614b  xor     ecx, ecx
0x18001614d  call    DsRolepResetOperationHandle
0x180016152  lea     r11, [rsp+70h+var_s0]
0x180016157  mov     eax, ebx
0x180016159  mov     rbx, [r11+10h]
0x18001615d  mov     rdi, [r11+18h]
0x180016161  mov     rsp, r11
0x180016164  pop     rbp
0x180016165  retn
```
