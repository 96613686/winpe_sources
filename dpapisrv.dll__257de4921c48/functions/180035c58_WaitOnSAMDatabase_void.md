# WaitOnSAMDatabase(void)

- ea: `0x180035c58`
- end: `0x180035d9b`
- name: `?WaitOnSAMDatabase@@YAHXZ`
- size: `323`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800328dc`
- `0x180035460`
- `0x1800354c8`

## callees

- `0x180007f10`
- `0x180035c58`
- `0x1800367a4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180035d67`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180035d67`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180035d50`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180035d50`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035d7e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035d7e`
- `ntdll!NtOpenEvent` at `0x180035cc6`
- `ntdll!NtOpenEvent` at `0x180035d21`
- `ntdll!NtOpenEvent` at `0x180035cc6`
- `ntdll!NtOpenEvent` at `0x180035d21`
- `ntdll!NtCreateEvent` at `0x180035cf8`
- `ntdll!NtCreateEvent` at `0x180035cf8`

## string_xrefs

- `0x180035d39`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`
- `0x180035c73`: `\SAM_SERVICE_STARTED`

## pseudocode

```c
_BOOL8 WaitOnSAMDatabase(void)
{
  NTSTATUS v0; // eax
  NTSTATUS v1; // ebx
  NTSTATUS v2; // eax
  BOOL v4; // ebx
  struct _UNICODE_STRING v5; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  void *EventHandle; // [rsp+80h] [rbp+10h] BYREF

  EventHandle = 0;
  v5 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  InitLsaString(&v5, L"\\SAM_SERVICE_STARTED");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &v5;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v0 = NtOpenEvent(&EventHandle, 0x100002u, &ObjectAttributes);
  v1 = v0;
  if ( v0 >= 0 )
    goto LABEL_8;
  if ( v0 != -1073741772 )
    goto LABEL_7;
  v2 = NtCreateEvent(&EventHandle, 0x100002u, &ObjectAttributes, NotificationEvent, 0);
  v1 = v2;
  if ( v2 == 0x40000000 || v2 == -1073741771 )
    v1 = NtOpenEvent(&EventHandle, 0x100002u, &ObjectAttributes);
  if ( v1 >= 0 )
  {
LABEL_8:
    v4 = WaitForSingleObject(EventHandle, 0xFFFFFFFF) == 0;
    CloseHandle(EventHandle);
    return v4;
  }
  else
  {
LABEL_7:
    DebugTraceError((unsigned int)v1, "Status", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", 2703);
    SetLastError(v1);
    return 0;
  }
}

```

## disassembly

```asm
0x180035c58  mov     [rsp-8+arg_8], rbx
0x180035c5d  push    rbp
0x180035c5e  mov     rbp, rsp
0x180035c61  sub     rsp, 70h
0x180035c65  xorps   xmm1, xmm1
0x180035c68  mov     [rbp+EventHandle], 0
0x180035c70  xorps   xmm0, xmm0
0x180035c73  lea     rdx, aSamServiceStar; "\\SAM_SERVICE_STARTED"
0x180035c7a  lea     rcx, [rbp+var_40]; struct _UNICODE_STRING *
0x180035c7e  movups  xmmword ptr [rbp+var_40.Length], xmm0
0x180035c82  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm1
0x180035c86  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm1
0x180035c8a  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm1
0x180035c8e  call    ?InitLsaString@@YAXPEAU_UNICODE_STRING@@PEAG@Z; InitLsaString(_UNICODE_STRING *,ushort *)
0x180035c93  lea     rax, [rbp+var_40]
0x180035c97  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180035c9e  xorps   xmm0, xmm0
0x180035ca1  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180035ca5  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180035ca9  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x180035cb1  mov     edx, 100002h; DesiredAccess
0x180035cb6  mov     [rbp+ObjectAttributes.Attributes], 0
0x180035cbd  lea     rcx, [rbp+EventHandle]; EventHandle
0x180035cc1  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180035cc6  call    cs:__imp_NtOpenEvent
0x180035ccd  nop     dword ptr [rax+rax+00h]
0x180035cd2  mov     ebx, eax
0x180035cd4  test    eax, eax
0x180035cd6  jns     loc_180035D60
0x180035cdc  cmp     eax, 0C0000034h
0x180035ce1  jnz     short loc_180035D33
0x180035ce3  xor     r9d, r9d; EventType
0x180035ce6  mov     [rsp+70h+InitialState], 0; InitialState
0x180035ceb  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180035cef  mov     edx, 100002h; DesiredAccess
0x180035cf4  lea     rcx, [rbp+EventHandle]; EventHandle
0x180035cf8  call    cs:__imp_NtCreateEvent
0x180035cff  nop     dword ptr [rax+rax+00h]
0x180035d04  mov     ebx, eax
0x180035d06  cmp     eax, 40000000h
0x180035d0b  jz      short loc_180035D14
0x180035d0d  cmp     eax, 0C0000035h
0x180035d12  jnz     short loc_180035D2F
0x180035d14  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180035d18  mov     edx, 100002h; DesiredAccess
0x180035d1d  lea     rcx, [rbp+EventHandle]; EventHandle
0x180035d21  call    cs:__imp_NtOpenEvent
0x180035d28  nop     dword ptr [rax+rax+00h]
0x180035d2d  mov     ebx, eax
0x180035d2f  test    ebx, ebx
0x180035d31  jns     short loc_180035D60
0x180035d33  mov     r9d, 0A8Fh
0x180035d39  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180035d40  lea     rdx, aStatus; "Status"
0x180035d47  mov     ecx, ebx
0x180035d49  call    DebugTraceError
0x180035d4e  mov     ecx, ebx; dwErrCode
0x180035d50  call    cs:__imp_SetLastError
0x180035d57  nop     dword ptr [rax+rax+00h]
0x180035d5c  xor     eax, eax
0x180035d5e  jmp     short loc_180035D8C
0x180035d60  mov     rcx, [rbp+EventHandle]; hHandle
0x180035d64  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180035d67  call    cs:__imp_WaitForSingleObject
0x180035d6e  nop     dword ptr [rax+rax+00h]
0x180035d73  mov     rcx, [rbp+EventHandle]; hObject
0x180035d77  xor     ebx, ebx
0x180035d79  test    eax, eax
0x180035d7b  setz    bl
0x180035d7e  call    cs:__imp_CloseHandle
0x180035d85  nop     dword ptr [rax+rax+00h]
0x180035d8a  mov     eax, ebx
0x180035d8c  mov     rbx, [rsp+70h+arg_8]
0x180035d94  add     rsp, 70h
0x180035d98  pop     rbp
0x180035d99  retn
```
