# SampDsControlAccessRightCheck(_SAMP_OBJECT *,void *,_GUID *)

- ea: `0x1804116ec`
- end: `0x1804119ae`
- name: `?SampDsControlAccessRightCheck@@YAJPEAU_SAMP_OBJECT@@PEAXPEAU_GUID@@@Z`
- size: `706`
- prototype: `int(struct _SAMP_OBJECT *, void *, struct _GUID *)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180412300`

## callees

- `0x18001e090`
- `0x18001ea60`
- `0x1803af8f0`
- `0x1803debcc`
- `0x1803e6ee4`
- `0x1803fe620`
- `0x1804116ec`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x180411848`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x180411848`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180411987`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180411987`
- `ntdll!NtAccessCheckByTypeResultList` at `0x1804118b2`
- `ntdll!NtAccessCheckByTypeResultList` at `0x1804118b2`
- `ntdll!NtAccessCheckByTypeResultListAndAuditAlarm` at `0x180411952`
- `ntdll!NtAccessCheckByTypeResultListAndAuditAlarm` at `0x180411952`
- `SAMSRV!SampGetObjectTypeNameFromIndex` at `0x1804118d9`
- `SAMSRV!SampGetObjectTypeNameFromIndex` at `0x1804118d9`
- `SAMSRV!SampGetDomainContextFromIndex` at `0x180411781`
- `SAMSRV!SampGetDomainContextFromIndex` at `0x180411781`
- `SAMSRV!SampImpersonateClient` at `0x1804118c3`
- `SAMSRV!SampImpersonateClient` at `0x1804118c3`
- `SAMSRV!SampGetSamSubsystemName` at `0x1804118e2`
- `SAMSRV!SampGetSamSubsystemName` at `0x1804118e2`
- `SAMSRV!SampRevertToSelf` at `0x18041195d`
- `SAMSRV!SampRevertToSelf` at `0x18041195d`

## pseudocode

```c
__int64 __fastcall SampDsControlAccessRightCheck(struct _SAMP_OBJECT *a1, void *a2, struct _GUID *a3)
{
  __int64 result; // rax
  bool v4; // zf
  __int64 DomainContextFromIndex; // r14
  NTSTATUS ClassAttribute; // ebx
  PSECURITY_DESCRIPTOR v9; // rsi
  ACCESS_MASK v10; // ebx
  struct _UNICODE_STRING *ObjectTypeNameFromIndex; // rdi
  struct _UNICODE_STRING *SamSubsystemName; // rax
  unsigned __int8 GenerateOnClose[4]; // [rsp+80h] [rbp-80h] BYREF
  DWORD AccessMask; // [rsp+84h] [rbp-7Ch] BYREF
  ULONG PrivilegeSetLength; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v16; // [rsp+8Ch] [rbp-74h] BYREF
  int AccessStatus[2]; // [rsp+90h] [rbp-70h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v19[8]; // [rsp+A0h] [rbp-60h] BYREF
  struct _OBJECT_TYPE_LIST ObjectTypeList[2]; // [rsp+A8h] [rbp-58h] BYREF
  struct _UNICODE_STRING ObjectName; // [rsp+C8h] [rbp-38h] BYREF
  DWORD GrantedAccess; // [rsp+D8h] [rbp-28h] BYREF
  struct _GENERIC_MAPPING GenericMapping; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v24; // [rsp+F0h] [rbp-10h] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+100h] [rbp+0h] BYREF

  result = 0;
  GenericMapping.GenericRead = 131220;
  v4 = (*((_BYTE *)a1 + 20) & 0x20) == 0;
  memset(ObjectTypeList, 0, sizeof(ObjectTypeList));
  GenericMapping.GenericWrite = 131112;
  GenericMapping.GenericExecute = 131076;
  GenericMapping.GenericAll = 983551;
  AccessMask = 0;
  PrivilegeSetLength = 16;
  v24 = 0;
  SecurityDescriptor = 0;
  ObjectName = 0;
  GenerateOnClose[0] = 0;
  v16 = 0;
  if ( v4 && (*((_BYTE *)a1 + 192) & 2) != 0 )
  {
    DomainContextFromIndex = SampGetDomainContextFromIndex(3);
    ObjectName.Length = 2 * *(_WORD *)(*(_QWORD *)(DomainContextFromIndex + 176) + 52LL);
    ObjectName.MaximumLength = ObjectName.Length;
    ObjectName.Buffer = (PWSTR)(*(_QWORD *)(DomainContextFromIndex + 176) + 56LL);
    ClassAttribute = SampDoImplicitTransactionStart(0);
    if ( ClassAttribute < 0 )
      return (unsigned int)ClassAttribute;
    if ( (int)SampDsGetCachedObjectSD(DomainContextFromIndex, v19, &SecurityDescriptor) >= 0
      || (ClassAttribute = SampGetDomainObjectSDFromDsName(
                             *(_QWORD *)(DomainContextFromIndex + 176),
                             v19,
                             &SecurityDescriptor),
          ClassAttribute >= 0) )
    {
      ClassAttribute = SampGetClassAttribute(
                         *(unsigned int *)(DomainContextFromIndex + 196),
                         589972,
                         &PrivilegeSetLength,
                         &v24);
      if ( ClassAttribute >= 0 )
      {
        ObjectTypeList[1].ObjectType = a3;
        *(_DWORD *)&ObjectTypeList[0].Level = 0;
        *(_QWORD *)AccessStatus = 0;
        ObjectTypeList[0].ObjectType = (GUID *)&v24;
        *(_DWORD *)&ObjectTypeList[1].Level = 1;
        AccessMask = 256;
        MapGenericMask(&AccessMask, &GenericMapping);
        if ( a2 )
        {
          PrivilegeSetLength = 256;
          memset_0(&PrivilegeSet, 0, 0x100u);
          v9 = SecurityDescriptor;
          ClassAttribute = NtAccessCheckByTypeResultList(
                             SecurityDescriptor,
                             0,
                             a2,
                             AccessMask,
                             ObjectTypeList,
                             2u,
                             &GenericMapping,
                             &PrivilegeSet,
                             &PrivilegeSetLength,
                             &GrantedAccess,
                             AccessStatus);
LABEL_11:
          if ( ClassAttribute >= 0 && AccessStatus[0] && AccessStatus[1] )
            ClassAttribute = -1073741790;
          goto LABEL_17;
        }
        ClassAttribute = SampImpersonateClient(&v16);
        if ( ClassAttribute >= 0 )
        {
          v10 = AccessMask;
          ObjectTypeNameFromIndex = (struct _UNICODE_STRING *)SampGetObjectTypeNameFromIndex(1);
          SamSubsystemName = (struct _UNICODE_STRING *)SampGetSamSubsystemName();
          v9 = SecurityDescriptor;
          ClassAttribute = NtAccessCheckByTypeResultListAndAuditAlarm(
                             SamSubsystemName,
                             (PVOID)DomainContextFromIndex,
                             ObjectTypeNameFromIndex,
                             &ObjectName,
                             SecurityDescriptor,
                             0,
                             v10,
                             AuditEventDirectoryServiceAccess,
                             0,
                             ObjectTypeList,
                             2u,
                             &GenericMapping,
                             0,
                             &GrantedAccess,
                             AccessStatus,
                             GenerateOnClose);
          SampRevertToSelf(v16);
          goto LABEL_11;
        }
      }
    }
    v9 = SecurityDescriptor;
LABEL_17:
    if ( v9 )
      LocalFree(v9);
    return (unsigned int)ClassAttribute;
  }
  return result;
}

```

## disassembly

```asm
0x1804116ec  push    rbp
0x1804116ee  push    rbx
0x1804116ef  push    rsi
0x1804116f0  push    rdi
0x1804116f1  push    r13
0x1804116f3  push    r14
0x1804116f5  lea     rbp, [rsp-118h]
0x1804116fd  sub     rsp, 218h
0x180411704  mov     rax, cs:__security_cookie
0x18041170b  xor     rax, rsp
0x18041170e  mov     [rbp+140h+var_40], rax
0x180411715  xor     eax, eax
0x180411717  mov     [rbp+140h+GenericMapping.GenericRead], 20094h
0x18041171e  test    byte ptr [rcx+14h], 20h
0x180411722  xorps   xmm0, xmm0
0x180411725  xorps   xmm1, xmm1
0x180411728  mov     [rbp+140h+var_198.Level], ax
0x18041172c  movups  xmmword ptr [rbp+140h+var_198.Sbz], xmm0
0x180411730  mov     rsi, r8
0x180411733  mov     rdi, rdx
0x180411736  movups  xmmword ptr [rbp+140h+var_188], xmm0
0x18041173a  mov     [rbp+140h+GenericMapping.GenericWrite], 20028h
0x180411741  mov     [rbp+140h+GenericMapping.GenericExecute], 20004h
0x180411748  mov     [rbp+140h+GenericMapping.GenericAll], 0F01FFh
0x18041174f  mov     [rbp+140h+AccessMask], eax
0x180411752  mov     [rbp+140h+var_1B8], 10h
0x180411759  movups  [rbp+140h+var_150], xmm0
0x18041175d  mov     [rbp+140h+SecurityDescriptor], rax
0x180411761  movups  xmmword ptr [rbp+140h+ObjectName.Length], xmm1
0x180411765  mov     [rbp+140h+var_1C0], al
0x180411768  mov     [rbp+140h+var_1B4], eax
0x18041176b  jnz     loc_18041198F
0x180411771  test    byte ptr [rcx+0C0h], 2
0x180411778  jz      loc_18041198F
0x18041177e  lea     ecx, [rax+3]
0x180411781  call    cs:__imp_SampGetDomainContextFromIndex
0x180411787  mov     r14, rax
0x18041178a  mov     rcx, [rax+0B0h]
0x180411791  movzx   edx, word ptr [rcx+34h]
0x180411795  add     dx, dx
0x180411798  mov     [rbp+140h+ObjectName.Length], dx
0x18041179c  mov     [rbp+140h+ObjectName.MaximumLength], dx
0x1804117a0  mov     rcx, [rax+0B0h]
0x1804117a7  add     rcx, 38h ; '8'
0x1804117ab  mov     [rbp+140h+ObjectName.Buffer], rcx
0x1804117af  xor     ecx, ecx
0x1804117b1  call    SampDoImplicitTransactionStart
0x1804117b6  mov     ebx, eax
0x1804117b8  test    eax, eax
0x1804117ba  js      loc_18041198D
0x1804117c0  lea     r8, [rbp+140h+SecurityDescriptor]
0x1804117c4  mov     rcx, r14
0x1804117c7  lea     rdx, [rbp+140h+var_1A0]
0x1804117cb  call    SampDsGetCachedObjectSD
0x1804117d0  test    eax, eax
0x1804117d2  jns     short loc_1804117F2
0x1804117d4  mov     rcx, [r14+0B0h]
0x1804117db  lea     r8, [rbp+140h+SecurityDescriptor]
0x1804117df  lea     rdx, [rbp+140h+var_1A0]
0x1804117e3  call    SampGetDomainObjectSDFromDsName
0x1804117e8  mov     ebx, eax
0x1804117ea  test    eax, eax
0x1804117ec  js      loc_18041197B
0x1804117f2  mov     ecx, [r14+0C4h]
0x1804117f9  lea     r9, [rbp+140h+var_150]
0x1804117fd  lea     r8, [rbp+140h+var_1B8]
0x180411801  mov     edx, 90094h
0x180411806  call    SampGetClassAttribute
0x18041180b  mov     ebx, eax
0x18041180d  test    eax, eax
0x18041180f  js      loc_18041197B
0x180411815  xor     eax, eax
0x180411817  mov     [rbp+140h+var_180], rsi
0x18041181b  mov     dword ptr [rbp+140h+var_198.Level], eax
0x18041181e  lea     rdx, [rbp+140h+GenericMapping]; GenericMapping
0x180411822  lea     rax, [rbp+140h+var_150]
0x180411826  mov     qword ptr [rbp+140h+var_1B0], 0
0x18041182e  mov     r13d, 1
0x180411834  mov     [rbp+140h+var_198.ObjectType], rax
0x180411838  mov     ebx, 100h
0x18041183d  mov     [rbp+140h+var_188], r13d
0x180411841  lea     rcx, [rbp+140h+AccessMask]; AccessMask
0x180411845  mov     [rbp+140h+AccessMask], ebx
0x180411848  call    cs:__imp_MapGenericMask
0x18041184e  test    rdi, rdi
0x180411851  jz      short loc_1804118BF
0x180411853  mov     r8d, ebx; Size
0x180411856  mov     [rbp+140h+var_1B8], ebx
0x180411859  xor     edx, edx; Val
0x18041185b  lea     rcx, [rbp+140h+var_140]; void *
0x18041185f  call    memset_0
0x180411864  mov     rsi, [rbp+140h+SecurityDescriptor]
0x180411868  lea     rax, [rbp+140h+var_1B0]
0x18041186c  mov     r9d, [rbp+140h+AccessMask]; DesiredAccess
0x180411870  mov     r8, rdi; ClientToken
0x180411873  mov     [rsp+240h+AccessStatus], rax; AccessStatus
0x180411878  xor     edx, edx; PrincipalSelfSid
0x18041187a  lea     rax, [rbp+140h+var_168]
0x18041187e  mov     rcx, rsi; SecurityDescriptor
0x180411881  mov     [rsp+240h+GrantedAccess], rax; GrantedAccess
0x180411886  lea     rax, [rbp+140h+var_1B8]
0x18041188a  mov     [rsp+240h+PrivilegeSetLength], rax; PrivilegeSetLength
0x18041188f  lea     rax, [rbp+140h+var_140]
0x180411893  mov     [rsp+240h+PrivilegeSet], rax; PrivilegeSet
0x180411898  lea     rax, [rbp+140h+GenericMapping]
0x18041189c  mov     [rsp+240h+var_210], rax; GenericMapping
0x1804118a1  lea     rax, [rbp+140h+var_198]
0x1804118a5  mov     [rsp+240h+ObjectTypeLength], 2; ObjectTypeLength
0x1804118ad  mov     [rsp+240h+ObjectTypeList], rax; ObjectTypeList
0x1804118b2  call    cs:__imp_NtAccessCheckByTypeResultList
0x1804118b8  mov     ebx, eax
0x1804118ba  jmp     loc_180411963
0x1804118bf  lea     rcx, [rbp+140h+var_1B4]
0x1804118c3  call    cs:__imp_SampImpersonateClient
0x1804118c9  mov     ebx, eax
0x1804118cb  test    eax, eax
0x1804118cd  js      loc_18041197B
0x1804118d3  mov     ebx, [rbp+140h+AccessMask]
0x1804118d6  mov     ecx, r13d
0x1804118d9  call    cs:__imp_SampGetObjectTypeNameFromIndex
0x1804118df  mov     rdi, rax
0x1804118e2  call    cs:__imp_SampGetSamSubsystemName
0x1804118e8  mov     rsi, [rbp+140h+SecurityDescriptor]
0x1804118ec  lea     rcx, [rbp+140h+var_1C0]
0x1804118f0  mov     [rsp+240h+GenerateOnClose], rcx; GenerateOnClose
0x1804118f5  lea     r9, [rbp+140h+ObjectName]; ObjectName
0x1804118f9  lea     rcx, [rbp+140h+var_1B0]
0x1804118fd  mov     r8, rdi; ObjectTypeName
0x180411900  mov     [rsp+240h+AccessStatusList], rcx; AccessStatusList
0x180411905  mov     rdx, r14; HandleId
0x180411908  lea     rcx, [rbp+140h+var_168]
0x18041190c  mov     [rsp+240h+GrantedAccessList], rcx; GrantedAccessList
0x180411911  lea     rcx, [rbp+140h+GenericMapping]
0x180411915  mov     [rsp+240h+ObjectCreation], 0; ObjectCreation
0x18041191a  mov     [rsp+240h+var_1E8], rcx; GenericMapping
0x18041191f  lea     rcx, [rbp+140h+var_198]
0x180411923  mov     dword ptr [rsp+240h+AccessStatus], 2; ObjectTypeListLength
0x18041192b  mov     [rsp+240h+GrantedAccess], rcx; ObjectTypeList
0x180411930  mov     rcx, rax; SubsystemName
0x180411933  mov     dword ptr [rsp+240h+PrivilegeSetLength], 0; Flags
0x18041193b  mov     dword ptr [rsp+240h+PrivilegeSet], r13d; AuditType
0x180411940  mov     dword ptr [rsp+240h+var_210], ebx; DesiredAccess
0x180411944  mov     qword ptr [rsp+240h+ObjectTypeLength], 0; PrincipalSelfSid
0x18041194d  mov     [rsp+240h+ObjectTypeList], rsi; SecurityDescriptor
0x180411952  call    cs:__imp_NtAccessCheckByTypeResultListAndAuditAlarm
0x180411958  mov     ecx, [rbp+140h+var_1B4]
0x18041195b  mov     ebx, eax
0x18041195d  call    cs:__imp_SampRevertToSelf
0x180411963  test    ebx, ebx
0x180411965  js      short loc_18041197F
0x180411967  cmp     [rbp+140h+var_1B0], 0
0x18041196b  jz      short loc_18041197F
0x18041196d  cmp     [rbp+140h+var_1B0+4], 0
0x180411971  mov     eax, 0C0000022h
0x180411976  cmovnz  ebx, eax
0x180411979  jmp     short loc_18041197F
0x18041197b  mov     rsi, [rbp+140h+SecurityDescriptor]
0x18041197f  test    rsi, rsi
0x180411982  jz      short loc_18041198D
0x180411984  mov     rcx, rsi; hMem
0x180411987  call    cs:__imp_LocalFree
0x18041198d  mov     eax, ebx
0x18041198f  mov     rcx, [rbp+140h+var_40]
0x180411996  xor     rcx, rsp; StackCookie
0x180411999  call    __security_check_cookie
0x18041199e  add     rsp, 218h
0x1804119a5  pop     r14
0x1804119a7  pop     r13
0x1804119a9  pop     rdi
0x1804119aa  pop     rsi
0x1804119ab  pop     rbx
0x1804119ac  pop     rbp
0x1804119ad  retn
```
