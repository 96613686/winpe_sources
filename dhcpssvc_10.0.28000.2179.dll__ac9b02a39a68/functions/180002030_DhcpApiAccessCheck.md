# DhcpApiAccessCheck

- ea: `0x180002030`
- end: `0x1800021ae`
- name: `DhcpApiAccessCheck`
- size: `382`
- prototype: ``
- caller_count: `64`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180008f90`
- `0x180009040`
- `0x180009100`
- `0x1800092e0`
- `0x180009c10`
- `0x18000a000`
- `0x18000a390`
- `0x18000a780`
- `0x18000ac50`
- `0x18000ae00`
- `0x18000b090`
- `0x18000b350`
- `0x18000b490`
- `0x18000b580`
- `0x18000bac0`
- `0x18000bf80`
- `0x18000c020`
- `0x18002d050`
- `0x18002d760`
- `0x18002dae0`
- `0x18002f170`
- `0x18002f230`
- `0x18002f2d0`
- `0x18002f320`
- `0x18002f370`
- `0x18002f3c0`
- `0x18002f5c0`
- `0x18002f890`
- `0x1800417c0`
- `0x1800422a0`
- `0x180042f20`
- `0x1800434b0`
- `0x180044100`
- `0x180044e10`
- `0x1800458d0`
- `0x18004b800`
- `0x18004bb00`
- `0x18004c170`
- `0x18004d330`
- `0x18004d610`
- `0x18004d690`
- `0x18004d780`
- `0x18004d9d0`
- `0x18004db80`
- `0x18004de80`
- `0x18004df00`
- `0x18004df90`
- `0x18004e020`
- `0x18005da30`
- `0x18005dbf0`

## callees

- `0x180002030`
- `0x18000282c`

## import_xrefs

- `ntdll!NtAccessCheckAndAuditAlarm` at `0x18000213d`
- `ntdll!NtAccessCheckAndAuditAlarm` at `0x18000213d`
- `ntdll!RtlAdjustPrivilege` at `0x1800020e3`
- `ntdll!RtlAdjustPrivilege` at `0x1800020e3`
- `ntdll!RtlInitUnicodeString` at `0x18000209c`
- `ntdll!RtlInitUnicodeString` at `0x1800020b3`
- `ntdll!RtlInitUnicodeString` at `0x1800020ca`
- `ntdll!RtlInitUnicodeString` at `0x18000209c`
- `ntdll!RtlInitUnicodeString` at `0x1800020b3`
- `ntdll!RtlInitUnicodeString` at `0x1800020ca`
- `ADVAPI32!MapGenericMask` at `0x180002053`
- `ADVAPI32!MapGenericMask` at `0x180002053`
- `RPCRT4!RpcImpersonateClient` at `0x1800020f1`
- `RPCRT4!RpcImpersonateClient` at `0x1800020f1`
- `RPCRT4!RpcRevertToSelf` at `0x18000214b`
- `RPCRT4!RpcRevertToSelf` at `0x18000214b`

## string_xrefs

- `0x1800020a8`: `DhcpServerService`

## pseudocode

```c
__int64 __fastcall DhcpApiAccessCheck(DWORD a1)
{
  ACCESS_MASK DesiredAccess; // ebx
  PSECURITY_DESCRIPTOR SecurityDescriptor; // rdi
  unsigned int v3; // eax
  NTSTATUS v4; // ebx
  DWORD GrantedAccess; // [rsp+60h] [rbp-9h] BYREF
  struct _UNICODE_STRING ObjectName; // [rsp+68h] [rbp-1h] BYREF
  struct _UNICODE_STRING ObjectTypeName; // [rsp+78h] [rbp+Fh] BYREF
  _UNICODE_STRING DestinationString; // [rsp+88h] [rbp+1Fh] BYREF
  DWORD AccessMask; // [rsp+D0h] [rbp+67h] BYREF
  unsigned __int8 OldValue; // [rsp+D8h] [rbp+6Fh] BYREF
  unsigned __int8 GenerateOnClose; // [rsp+E0h] [rbp+77h] BYREF
  int AccessStatus; // [rsp+E8h] [rbp+7Fh] BYREF

  AccessMask = a1;
  MapGenericMask(&AccessMask, &DhcpGlobalServiceGenericInfoMapping);
  DesiredAccess = AccessMask;
  SecurityDescriptor = DhcpGlobalServiceSecurityDescriptor;
  OldValue = 0;
  GrantedAccess = 0;
  DestinationString = 0;
  GenerateOnClose = 0;
  ObjectTypeName = 0;
  AccessStatus = 0;
  ObjectName = 0;
  RtlInitUnicodeString(&DestinationString, L"DhcpServer");
  RtlInitUnicodeString(&ObjectTypeName, L"DhcpServerService");
  RtlInitUnicodeString(&ObjectName, L"-");
  RtlAdjustPrivilege(0x15u, 1u, 0, &OldValue);
  v3 = RpcImpersonateClient(0);
  if ( !v3 )
  {
    v4 = NtAccessCheckAndAuditAlarm(
           &DestinationString,
           0,
           &ObjectTypeName,
           &ObjectName,
           SecurityDescriptor,
           DesiredAccess,
           &DhcpGlobalServiceGenericInfoMapping,
           0,
           &GrantedAccess,
           &AccessStatus,
           &GenerateOnClose);
    RpcRevertToSelf();
    if ( v4 >= 0 && !AccessStatus )
      return 0;
    v3 = 5;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_96c1c8f0f5ee380f4a6130aeff8779e4_Traceguids, v3);
  return 5;
}

```

## disassembly

```asm
0x180002030  mov     [rsp-8+AccessMask], ecx
0x180002034  push    rbp
0x180002035  push    rbx
0x180002036  push    rdi
0x180002037  push    r15
0x180002039  lea     rbp, [rsp-3Fh]
0x18000203e  sub     rsp, 0A8h
0x180002045  lea     r15, DhcpGlobalServiceGenericInfoMapping
0x18000204c  mov     rdx, r15; GenericMapping
0x18000204f  lea     rcx, [rbp+57h+AccessMask]; AccessMask
0x180002053  call    cs:__imp_MapGenericMask
0x18000205a  nop     dword ptr [rax+rax+00h]
0x18000205f  mov     ebx, [rbp+57h+AccessMask]
0x180002062  lea     rdx, SourceName; "DhcpServer"
0x180002069  mov     rdi, cs:DhcpGlobalServiceSecurityDescriptor
0x180002070  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180002074  xorps   xmm0, xmm0
0x180002077  mov     [rbp+57h+OldValue], 0
0x18000207b  xorps   xmm1, xmm1
0x18000207e  mov     [rbp+57h+var_60], 0
0x180002085  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180002089  mov     [rbp+57h+arg_10], 0
0x18000208d  movups  xmmword ptr [rbp+57h+ObjectTypeName.Length], xmm1
0x180002091  mov     [rbp+57h+arg_18], 0
0x180002098  movups  xmmword ptr [rbp+57h+ObjectName.Length], xmm0
0x18000209c  call    cs:__imp_RtlInitUnicodeString
0x1800020a3  nop     dword ptr [rax+rax+00h]
0x1800020a8  lea     rdx, aDhcpserverserv; "DhcpServerService"
0x1800020af  lea     rcx, [rbp+57h+ObjectTypeName]; DestinationString
0x1800020b3  call    cs:__imp_RtlInitUnicodeString
0x1800020ba  nop     dword ptr [rax+rax+00h]
0x1800020bf  lea     rdx, asc_1800E70C8; "-"
0x1800020c6  lea     rcx, [rbp+57h+ObjectName]; DestinationString
0x1800020ca  call    cs:__imp_RtlInitUnicodeString
0x1800020d1  nop     dword ptr [rax+rax+00h]
0x1800020d6  xor     r8d, r8d; ForThread
0x1800020d9  lea     r9, [rbp+57h+OldValue]; OldValue
0x1800020dd  mov     dl, 1; NewValue
0x1800020df  lea     ecx, [r8+15h]; Privilege
0x1800020e3  call    cs:__imp_RtlAdjustPrivilege
0x1800020ea  nop     dword ptr [rax+rax+00h]
0x1800020ef  xor     ecx, ecx; BindingHandle
0x1800020f1  call    cs:__imp_RpcImpersonateClient
0x1800020f8  nop     dword ptr [rax+rax+00h]
0x1800020fd  test    eax, eax
0x1800020ff  jnz     short loc_180002166
0x180002101  lea     rax, [rbp+57h+arg_10]
0x180002105  xor     edx, edx; HandleId
0x180002107  mov     [rsp+0C0h+GenerateOnClose], rax; GenerateOnClose
0x18000210c  lea     r9, [rbp+57h+ObjectName]; ObjectName
0x180002110  lea     rax, [rbp+57h+arg_18]
0x180002114  mov     [rsp+0C0h+AccessStatus], rax; AccessStatus
0x180002119  lea     r8, [rbp+57h+ObjectTypeName]; ObjectTypeName
0x18000211d  lea     rax, [rbp+57h+var_60]
0x180002121  mov     [rsp+0C0h+GrantedAccess], rax; GrantedAccess
0x180002126  lea     rcx, [rbp+57h+DestinationString]; SubsystemName
0x18000212a  mov     [rsp+0C0h+ObjectCreation], 0; ObjectCreation
0x18000212f  mov     [rsp+0C0h+GenericMapping], r15; GenericMapping
0x180002134  mov     [rsp+0C0h+DesiredAccess], ebx; DesiredAccess
0x180002138  mov     [rsp+0C0h+SecurityDescriptor], rdi; SecurityDescriptor
0x18000213d  call    cs:__imp_NtAccessCheckAndAuditAlarm
0x180002144  nop     dword ptr [rax+rax+00h]
0x180002149  mov     ebx, eax
0x18000214b  call    cs:__imp_RpcRevertToSelf
0x180002152  nop     dword ptr [rax+rax+00h]
0x180002157  test    ebx, ebx
0x180002159  js      short loc_180002161
0x18000215b  cmp     [rbp+57h+arg_18], 0
0x18000215f  jz      short loc_18000219E
0x180002161  mov     eax, 5
0x180002166  mov     rcx, cs:WPP_GLOBAL_Control
0x18000216d  lea     rdx, WPP_GLOBAL_Control
0x180002174  cmp     rcx, rdx
0x180002177  jz      short loc_180002197
0x180002179  test    byte ptr [rcx+1Ch], 10h
0x18000217d  jz      short loc_180002197
0x18000217f  mov     rcx, [rcx+10h]
0x180002183  lea     r8, WPP_96c1c8f0f5ee380f4a6130aeff8779e4_Traceguids
0x18000218a  mov     edx, 0Ch
0x18000218f  mov     r9d, eax
0x180002192  call    WPP_SF_D
0x180002197  mov     eax, 5
0x18000219c  jmp     short loc_1800021A0
0x18000219e  xor     eax, eax
0x1800021a0  add     rsp, 0A8h
0x1800021a7  pop     r15
0x1800021a9  pop     rdi
0x1800021aa  pop     rbx
0x1800021ab  pop     rbp
0x1800021ac  retn
```
