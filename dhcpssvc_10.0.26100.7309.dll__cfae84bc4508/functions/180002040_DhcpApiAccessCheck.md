# DhcpApiAccessCheck

- ea: `0x180002040`
- end: `0x1800021b8`
- name: `DhcpApiAccessCheck`
- size: `376`
- prototype: `__int64 __fastcall(DWORD)`
- caller_count: `64`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180009050`
- `0x180009100`
- `0x1800091c0`
- `0x1800093a0`
- `0x180009cb0`
- `0x18000a090`
- `0x18000a410`
- `0x18000a7f0`
- `0x18000acc0`
- `0x18000ae70`
- `0x18000b0f0`
- `0x18000b3a0`
- `0x18000b4e0`
- `0x18000b5c0`
- `0x18000baf0`
- `0x18000bfa0`
- `0x18000c040`
- `0x18002da70`
- `0x18002e170`
- `0x18002e4e0`
- `0x18002fb90`
- `0x18002fc50`
- `0x18002fcf0`
- `0x18002fd40`
- `0x18002fd90`
- `0x18002fde0`
- `0x18002ffe0`
- `0x1800302a0`
- `0x180041ce0`
- `0x1800427f0`
- `0x180043470`
- `0x180043a00`
- `0x180044630`
- `0x180045320`
- `0x180045de0`
- `0x18004bc40`
- `0x18004bf10`
- `0x18004c540`
- `0x18004d6f0`
- `0x18004d9d0`
- `0x18004da50`
- `0x18004db40`
- `0x18004dd90`
- `0x18004df40`
- `0x18004e230`
- `0x18004e2b0`
- `0x18004e340`
- `0x18004e3d0`
- `0x18005ddd0`
- `0x18005df90`

## callees

- `0x180002040`
- `0x180002854`

## import_xrefs

- `ntdll!NtAccessCheckAndAuditAlarm` at `0x180002147`
- `ntdll!NtAccessCheckAndAuditAlarm` at `0x180002147`
- `ntdll!RtlAdjustPrivilege` at `0x1800020ed`
- `ntdll!RtlAdjustPrivilege` at `0x1800020ed`
- `ntdll!RtlInitUnicodeString` at `0x1800020a6`
- `ntdll!RtlInitUnicodeString` at `0x1800020bd`
- `ntdll!RtlInitUnicodeString` at `0x1800020d4`
- `ntdll!RtlInitUnicodeString` at `0x1800020a6`
- `ntdll!RtlInitUnicodeString` at `0x1800020bd`
- `ntdll!RtlInitUnicodeString` at `0x1800020d4`
- `ADVAPI32!MapGenericMask` at `0x180002063`
- `ADVAPI32!MapGenericMask` at `0x180002063`
- `RPCRT4!RpcImpersonateClient` at `0x1800020fb`
- `RPCRT4!RpcImpersonateClient` at `0x1800020fb`
- `RPCRT4!RpcRevertToSelf` at `0x180002155`
- `RPCRT4!RpcRevertToSelf` at `0x180002155`

## string_xrefs

- `0x1800020b2`: `DhcpServerService`

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
  GrantedAccess = 0;
  AccessStatus = 0;
  DestinationString = 0;
  OldValue = 0;
  ObjectTypeName = 0;
  GenerateOnClose = 0;
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
0x180002040  mov     [rsp-8+AccessMask], ecx
0x180002044  push    rbp
0x180002045  push    rbx
0x180002046  push    rdi
0x180002047  push    r15
0x180002049  lea     rbp, [rsp-3Fh]
0x18000204e  sub     rsp, 0A8h
0x180002055  lea     r15, DhcpGlobalServiceGenericInfoMapping
0x18000205c  mov     rdx, r15; GenericMapping
0x18000205f  lea     rcx, [rbp+57h+AccessMask]; AccessMask
0x180002063  call    cs:__imp_MapGenericMask
0x18000206a  nop     dword ptr [rax+rax+00h]
0x18000206f  mov     ebx, [rbp+57h+AccessMask]
0x180002072  lea     rdx, SourceName; "DhcpServer"
0x180002079  mov     rdi, cs:DhcpGlobalServiceSecurityDescriptor
0x180002080  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180002084  and     [rbp+57h+var_60], 0
0x180002088  xorps   xmm0, xmm0
0x18000208b  and     [rbp+57h+arg_18], 0
0x18000208f  xorps   xmm1, xmm1
0x180002092  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180002096  mov     [rbp+57h+OldValue], 0
0x18000209a  movups  xmmword ptr [rbp+57h+ObjectTypeName.Length], xmm1
0x18000209e  mov     [rbp+57h+arg_10], 0
0x1800020a2  movups  xmmword ptr [rbp+57h+ObjectName.Length], xmm0
0x1800020a6  call    cs:__imp_RtlInitUnicodeString
0x1800020ad  nop     dword ptr [rax+rax+00h]
0x1800020b2  lea     rdx, aDhcpserverserv; "DhcpServerService"
0x1800020b9  lea     rcx, [rbp+57h+ObjectTypeName]; DestinationString
0x1800020bd  call    cs:__imp_RtlInitUnicodeString
0x1800020c4  nop     dword ptr [rax+rax+00h]
0x1800020c9  lea     rdx, asc_1800E5118; "-"
0x1800020d0  lea     rcx, [rbp+57h+ObjectName]; DestinationString
0x1800020d4  call    cs:__imp_RtlInitUnicodeString
0x1800020db  nop     dword ptr [rax+rax+00h]
0x1800020e0  xor     r8d, r8d; ForThread
0x1800020e3  lea     r9, [rbp+57h+OldValue]; OldValue
0x1800020e7  mov     dl, 1; NewValue
0x1800020e9  lea     ecx, [r8+15h]; Privilege
0x1800020ed  call    cs:__imp_RtlAdjustPrivilege
0x1800020f4  nop     dword ptr [rax+rax+00h]
0x1800020f9  xor     ecx, ecx; BindingHandle
0x1800020fb  call    cs:__imp_RpcImpersonateClient
0x180002102  nop     dword ptr [rax+rax+00h]
0x180002107  test    eax, eax
0x180002109  jnz     short loc_180002170
0x18000210b  lea     rax, [rbp+57h+arg_10]
0x18000210f  xor     edx, edx; HandleId
0x180002111  mov     [rsp+0C0h+GenerateOnClose], rax; GenerateOnClose
0x180002116  lea     r9, [rbp+57h+ObjectName]; ObjectName
0x18000211a  lea     rax, [rbp+57h+arg_18]
0x18000211e  mov     [rsp+0C0h+AccessStatus], rax; AccessStatus
0x180002123  lea     r8, [rbp+57h+ObjectTypeName]; ObjectTypeName
0x180002127  lea     rax, [rbp+57h+var_60]
0x18000212b  mov     [rsp+0C0h+GrantedAccess], rax; GrantedAccess
0x180002130  lea     rcx, [rbp+57h+DestinationString]; SubsystemName
0x180002134  mov     [rsp+0C0h+ObjectCreation], 0; ObjectCreation
0x180002139  mov     [rsp+0C0h+GenericMapping], r15; GenericMapping
0x18000213e  mov     [rsp+0C0h+DesiredAccess], ebx; DesiredAccess
0x180002142  mov     [rsp+0C0h+SecurityDescriptor], rdi; SecurityDescriptor
0x180002147  call    cs:__imp_NtAccessCheckAndAuditAlarm
0x18000214e  nop     dword ptr [rax+rax+00h]
0x180002153  mov     ebx, eax
0x180002155  call    cs:__imp_RpcRevertToSelf
0x18000215c  nop     dword ptr [rax+rax+00h]
0x180002161  test    ebx, ebx
0x180002163  js      short loc_18000216B
0x180002165  cmp     [rbp+57h+arg_18], 0
0x180002169  jz      short loc_1800021A8
0x18000216b  mov     eax, 5
0x180002170  mov     rcx, cs:WPP_GLOBAL_Control
0x180002177  lea     rdx, WPP_GLOBAL_Control
0x18000217e  cmp     rcx, rdx
0x180002181  jz      short loc_1800021A1
0x180002183  test    byte ptr [rcx+1Ch], 10h
0x180002187  jz      short loc_1800021A1
0x180002189  mov     rcx, [rcx+10h]
0x18000218d  lea     r8, WPP_96c1c8f0f5ee380f4a6130aeff8779e4_Traceguids
0x180002194  mov     edx, 0Ch
0x180002199  mov     r9d, eax
0x18000219c  call    WPP_SF_D
0x1800021a1  mov     eax, 5
0x1800021a6  jmp     short loc_1800021AA
0x1800021a8  xor     eax, eax
0x1800021aa  add     rsp, 0A8h
0x1800021b1  pop     r15
0x1800021b3  pop     rdi
0x1800021b4  pop     rbx
0x1800021b5  pop     rbp
0x1800021b6  retn
```
