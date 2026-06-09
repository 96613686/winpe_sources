# LsaDbpIsAccessControlGranted(_DSNAME *,ulong,_GUID *,_LSAP_DB_OBJECT_TYPE_ID)

- ea: `0x180036750`
- end: `0x180036939`
- name: `?LsaDbpIsAccessControlGranted@@YAJPEAU_DSNAME@@KPEAU_GUID@@W4_LSAP_DB_OBJECT_TYPE_ID@@@Z`
- size: `489`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180015830`

## callees

- `0x180001670`
- `0x180012120`
- `0x180036750`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x180036859`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x180036859`
- `RPCRT4!RpcImpersonateClient` at `0x180036832`
- `RPCRT4!RpcImpersonateClient` at `0x180036832`
- `RPCRT4!I_RpcMapWin32Status` at `0x18003683a`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800368e4`
- `RPCRT4!I_RpcMapWin32Status` at `0x18003683a`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800368e4`
- `RPCRT4!RpcRevertToSelf` at `0x1800368dc`
- `RPCRT4!RpcRevertToSelf` at `0x1800368dc`
- `LSASRV!LsapDbGetDbObjectTypeName` at `0x180036865`
- `LSASRV!LsapDbGetDbObjectTypeName` at `0x180036865`
- `LSASRV!LsapFreeLsaHeap` at `0x18003690e`
- `LSASRV!LsapFreeLsaHeap` at `0x18003690e`
- `ntdll!NtAccessCheckByTypeResultListAndAuditAlarm` at `0x1800368d4`
- `ntdll!NtAccessCheckByTypeResultListAndAuditAlarm` at `0x1800368d4`
- `NTDSA!SampGetClassAttribute` at `0x1800367fd`
- `NTDSA!SampGetClassAttribute` at `0x1800367fd`

## pseudocode

```c
__int64 __fastcall LsaDbpIsAccessControlGranted(__int64 a1, __int64 a2, __int64 a3, unsigned int a4)
{
  __int16 v4; // ax
  int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  PSECURITY_DESCRIPTOR SecurityDescriptor; // rdi
  int ClassAttribute; // ebx
  RPC_STATUS v12; // eax
  ACCESS_MASK DesiredAccess; // ebx
  struct _UNICODE_STRING *DbObjectTypeName; // rax
  RPC_STATUS v15; // eax
  int v16; // eax
  unsigned __int8 GenerateOnClose[4]; // [rsp+80h] [rbp-49h] BYREF
  DWORD AccessMask; // [rsp+84h] [rbp-45h] BYREF
  int AccessStatusList[2]; // [rsp+88h] [rbp-41h] BYREF
  int v21; // [rsp+90h] [rbp-39h] BYREF
  PSECURITY_DESCRIPTOR v22; // [rsp+98h] [rbp-31h] BYREF
  struct _UNICODE_STRING ObjectName; // [rsp+A0h] [rbp-29h] BYREF
  struct _OBJECT_TYPE_LIST ObjectTypeList; // [rsp+B0h] [rbp-19h] BYREF
  int v25; // [rsp+C0h] [rbp-9h]
  __int64 v26; // [rsp+C8h] [rbp-1h]
  DWORD GrantedAccessList; // [rsp+D0h] [rbp+7h] BYREF
  struct _GENERIC_MAPPING GenericMapping; // [rsp+D8h] [rbp+Fh] BYREF
  __int128 v29; // [rsp+E8h] [rbp+1Fh] BYREF

  v4 = *(_WORD *)(a1 + 52);
  v22 = 0;
  GenericMapping.GenericRead = 131220;
  *(&ObjectName.MaximumLength + 2) = 0;
  *(_DWORD *)&ObjectName.MaximumLength = (unsigned __int16)(2 * v4);
  ObjectName.Length = 2 * v4;
  GenericMapping.GenericWrite = 131112;
  ObjectName.Buffer = (PWSTR)(a1 + 56);
  GenericMapping.GenericExecute = 131076;
  GenericMapping.GenericAll = 983551;
  AccessMask = 0;
  v29 = 0;
  v21 = 16;
  GenerateOnClose[0] = 0;
  v7 = LsaDbpDsReadObjectSDByDsName((struct _DSNAME *)a1, &v22);
  SecurityDescriptor = v22;
  ClassAttribute = v7;
  if ( v7 >= 0 )
  {
    ClassAttribute = SampGetClassAttribute(655427, 589972, &v21, &v29);
    if ( ClassAttribute >= 0 )
    {
      v26 = a3;
      *(_DWORD *)&ObjectTypeList.Level = 0;
      v25 = 1;
      ObjectTypeList.ObjectType = (GUID *)&v29;
      *(_QWORD *)AccessStatusList = 0;
      v12 = RpcImpersonateClient(0);
      ClassAttribute = I_RpcMapWin32Status(v12);
      if ( ClassAttribute >= 0 )
      {
        AccessMask = 256;
        MapGenericMask(&AccessMask, &GenericMapping);
        DesiredAccess = AccessMask;
        DbObjectTypeName = (struct _UNICODE_STRING *)LsapDbGetDbObjectTypeName(a4);
        ClassAttribute = NtAccessCheckByTypeResultListAndAuditAlarm(
                           &LsaDbpSubsystemName,
                           0,
                           DbObjectTypeName,
                           &ObjectName,
                           SecurityDescriptor,
                           0,
                           DesiredAccess,
                           AuditEventDirectoryServiceAccess,
                           0,
                           &ObjectTypeList,
                           2u,
                           &GenericMapping,
                           0,
                           &GrantedAccessList,
                           AccessStatusList,
                           GenerateOnClose);
        v15 = RpcRevertToSelf();
        v16 = I_RpcMapWin32Status(v15);
        if ( ClassAttribute >= 0 )
        {
          ClassAttribute = v16;
          if ( v16 >= 0 && AccessStatusList[0] && AccessStatusList[1] )
            ClassAttribute = -1073741790;
        }
      }
    }
  }
  if ( SecurityDescriptor )
    LsapFreeLsaHeap(SecurityDescriptor, v8, v9);
  return (unsigned int)ClassAttribute;
}

```

## disassembly

```asm
0x180036750  mov     [rsp-8+arg_8], rbx
0x180036755  push    rbp
0x180036756  push    rsi
0x180036757  push    rdi
0x180036758  push    r12
0x18003675a  push    r14
0x18003675c  lea     rbp, [rsp-37h]
0x180036761  sub     rsp, 100h
0x180036768  mov     rax, cs:__security_cookie
0x18003676f  xor     rax, rsp
0x180036772  mov     [rbp+57h+var_28], rax
0x180036776  movzx   eax, word ptr [rcx+34h]
0x18003677a  lea     rdx, [rbp+57h+var_88]; void **
0x18003677e  add     ax, ax
0x180036781  mov     [rbp+57h+var_88], 0
0x180036789  xorps   xmm0, xmm0
0x18003678c  mov     [rbp+57h+GenericMapping.GenericRead], 20094h
0x180036793  movups  xmmword ptr [rbp+57h+ObjectName.Length], xmm0
0x180036797  mov     [rbp+57h+ObjectName.MaximumLength], ax
0x18003679b  mov     r14d, r9d
0x18003679e  mov     [rbp+57h+ObjectName.Length], ax
0x1800367a2  mov     rsi, r8
0x1800367a5  lea     rax, [rcx+38h]
0x1800367a9  mov     [rbp+57h+GenericMapping.GenericWrite], 20028h
0x1800367b0  mov     [rbp+57h+ObjectName.Buffer], rax
0x1800367b4  mov     [rbp+57h+GenericMapping.GenericExecute], 20004h
0x1800367bb  mov     [rbp+57h+GenericMapping.GenericAll], 0F01FFh
0x1800367c2  mov     [rbp+57h+AccessMask], 0
0x1800367c9  movups  [rbp+57h+var_38], xmm0
0x1800367cd  mov     [rbp+57h+var_90], 10h
0x1800367d4  mov     [rbp+57h+var_A0], 0
0x1800367d8  call    ?LsaDbpDsReadObjectSDByDsName@@YAJPEAU_DSNAME@@PEAPEAX@Z; LsaDbpDsReadObjectSDByDsName(_DSNAME *,void * *)
0x1800367dd  mov     rdi, [rbp+57h+var_88]
0x1800367e1  mov     ebx, eax
0x1800367e3  test    eax, eax
0x1800367e5  js      loc_180036906
0x1800367eb  lea     r9, [rbp+57h+var_38]
0x1800367ef  mov     edx, 90094h
0x1800367f4  lea     r8, [rbp+57h+var_90]
0x1800367f8  mov     ecx, 0A0043h
0x1800367fd  call    cs:__imp_SampGetClassAttribute
0x180036803  mov     ebx, eax
0x180036805  test    eax, eax
0x180036807  js      loc_180036906
0x18003680d  xor     eax, eax
0x18003680f  mov     [rbp+57h+var_58], rsi
0x180036813  mov     dword ptr [rbp+57h+var_70.Level], eax
0x180036816  mov     r12d, 1
0x18003681c  lea     rax, [rbp+57h+var_38]
0x180036820  mov     [rbp+57h+var_60], r12d
0x180036824  xor     ecx, ecx; BindingHandle
0x180036826  mov     [rbp+57h+var_70.ObjectType], rax
0x18003682a  mov     qword ptr [rbp+57h+var_98], 0
0x180036832  call    cs:__imp_RpcImpersonateClient
0x180036838  mov     ecx, eax; Status
0x18003683a  call    cs:__imp_I_RpcMapWin32Status
0x180036840  mov     ebx, eax
0x180036842  test    eax, eax
0x180036844  js      loc_180036906
0x18003684a  lea     rdx, [rbp+57h+GenericMapping]; GenericMapping
0x18003684e  mov     [rbp+57h+AccessMask], 100h
0x180036855  lea     rcx, [rbp+57h+AccessMask]; AccessMask
0x180036859  call    cs:__imp_MapGenericMask
0x18003685f  mov     ebx, [rbp+57h+AccessMask]
0x180036862  mov     ecx, r14d
0x180036865  call    cs:__imp_LsapDbGetDbObjectTypeName
0x18003686b  lea     rcx, [rbp+57h+var_A0]
0x18003686f  xor     edx, edx; HandleId
0x180036871  mov     [rsp+120h+GenerateOnClose], rcx; GenerateOnClose
0x180036876  lea     r9, [rbp+57h+ObjectName]; ObjectName
0x18003687a  lea     rcx, [rbp+57h+var_98]
0x18003687e  mov     r8, rax; ObjectTypeName
0x180036881  mov     [rsp+120h+AccessStatusList], rcx; AccessStatusList
0x180036886  lea     rcx, [rbp+57h+var_50]
0x18003688a  mov     [rsp+120h+GrantedAccessList], rcx; GrantedAccessList
0x18003688f  lea     rcx, [rbp+57h+GenericMapping]
0x180036893  mov     [rsp+120h+ObjectCreation], 0; ObjectCreation
0x180036898  mov     [rsp+120h+var_C8], rcx; GenericMapping
0x18003689d  lea     rcx, [rbp+57h+var_70]
0x1800368a1  mov     [rsp+120h+ObjectTypeListLength], 2; ObjectTypeListLength
0x1800368a9  mov     [rsp+120h+ObjectTypeList], rcx; ObjectTypeList
0x1800368ae  lea     rcx, ?LsaDbpSubsystemName@@3U_UNICODE_STRING@@A; SubsystemName
0x1800368b5  mov     [rsp+120h+Flags], 0; Flags
0x1800368bd  mov     [rsp+120h+AuditType], r12d; AuditType
0x1800368c2  mov     [rsp+120h+DesiredAccess], ebx; DesiredAccess
0x1800368c6  mov     [rsp+120h+PrincipalSelfSid], 0; PrincipalSelfSid
0x1800368cf  mov     [rsp+120h+SecurityDescriptor], rdi; SecurityDescriptor
0x1800368d4  call    cs:__imp_NtAccessCheckByTypeResultListAndAuditAlarm
0x1800368da  mov     ebx, eax
0x1800368dc  call    cs:__imp_RpcRevertToSelf
0x1800368e2  mov     ecx, eax; Status
0x1800368e4  call    cs:__imp_I_RpcMapWin32Status
0x1800368ea  test    ebx, ebx
0x1800368ec  js      short loc_180036906
0x1800368ee  mov     ebx, eax
0x1800368f0  test    eax, eax
0x1800368f2  js      short loc_180036906
0x1800368f4  cmp     [rbp+57h+var_98], 0
0x1800368f8  jz      short loc_180036906
0x1800368fa  cmp     [rbp+57h+var_98+4], 0
0x1800368fe  mov     eax, 0C0000022h
0x180036903  cmovnz  ebx, eax
0x180036906  test    rdi, rdi
0x180036909  jz      short loc_180036914
0x18003690b  mov     rcx, rdi
0x18003690e  call    cs:__imp_LsapFreeLsaHeap
0x180036914  mov     eax, ebx
0x180036916  mov     rcx, [rbp+57h+var_28]
0x18003691a  xor     rcx, rsp; StackCookie
0x18003691d  call    __security_check_cookie
0x180036922  mov     rbx, [rsp+120h+arg_8]
0x18003692a  add     rsp, 100h
0x180036931  pop     r14
0x180036933  pop     r12
0x180036935  pop     rdi
0x180036936  pop     rsi
0x180036937  pop     rbp
0x180036938  retn
```
