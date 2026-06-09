# DsRolepCheckClientAccess

- ea: `0x1800150cc`
- end: `0x180015303`
- name: `DsRolepCheckClientAccess`
- size: `567`
- prototype: `__int64 __fastcall(__int64 *pSecurityDescriptor, __int64, char)`
- caller_count: `9`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180005400`
- `0x1800058a0`
- `0x180005e40`
- `0x1800065a0`
- `0x1800068d0`
- `0x180006ad0`
- `0x180006bf0`
- `0x180006c30`
- `0x18001feb0`

## callees

- `0x1800150cc`
- `0x180015670`
- `0x1800159a0`
- `0x18002c050`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800152c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800152d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800152c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800152d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015298`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015298`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18001528c`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18001528c`
- `api-ms-win-security-base-l1-1-0!AccessCheckAndAuditAlarmW` at `0x180015241`
- `api-ms-win-security-base-l1-1-0!AccessCheckAndAuditAlarmW` at `0x180015241`
- `RPCRT4!RpcRevertToSelf` at `0x180015249`
- `RPCRT4!RpcRevertToSelf` at `0x180015249`
- `RPCRT4!RpcImpersonateClient` at `0x1800151e6`
- `RPCRT4!RpcImpersonateClient` at `0x1800151e6`
- `ntdll!NtClose` at `0x1800152b8`
- `ntdll!NtClose` at `0x1800152b8`

## string_xrefs

- `0x180015218`: `Security Account Manager`

## pseudocode

```c
__int64 __fastcall DsRolepCheckClientAccess(__int64 *pSecurityDescriptor, __int64 a2, char a3)
{
  int v4; // r14d
  int v5; // r15d
  DWORD ImpersonationToken; // ebx
  __int64 v8; // rbx
  __int64 v9; // rcx
  WCHAR *v10; // rax
  BOOL v11; // edi
  WINBOOL AccessStatus; // [rsp+60h] [rbp-A0h] BYREF
  DWORD GrantedAccess; // [rsp+64h] [rbp-9Ch] BYREF
  LPWSTR ObjectName; // [rsp+68h] [rbp-98h]
  LPWSTR ObjectTypeName; // [rsp+70h] [rbp-90h]
  WINBOOL pfGenerateOnClose; // [rsp+78h] [rbp-88h] BYREF
  DWORD PrivilegeSetLength; // [rsp+7Ch] [rbp-84h] BYREF
  HANDLE ClientToken; // [rsp+80h] [rbp-80h] BYREF
  _PRIVILEGE_SET PrivilegeSet; // [rsp+90h] [rbp-70h] BYREF

  PrivilegeSetLength = 500;
  AccessStatus = 0;
  ClientToken = 0;
  GrantedAccess = 0;
  v4 = 0;
  pfGenerateOnClose = 0;
  v5 = 0;
  ObjectName = 0;
  ObjectTypeName = 0;
  ImpersonationToken = DsRolepGetImpersonationToken(&ClientToken);
  if ( !ImpersonationToken )
  {
    if ( a3 )
    {
      v8 = -1;
      if ( (unsigned int)DsRolepFormatOperationString(0x703Bu) )
      {
        ObjectTypeName = L"DsRole Interface";
      }
      else
      {
        v9 = -1;
        do
          ++v9;
        while ( ObjectTypeName[v9] );
        ObjectTypeName[v9 - 2] = 0;
        v5 = 1;
      }
      if ( (unsigned int)DsRolepFormatOperationString((unsigned int)(pSecurityDescriptor != DsRolepPromoteSD) + 28729) )
      {
        v10 = L"Domain Controller Promotion";
        if ( pSecurityDescriptor != DsRolepPromoteSD )
          v10 = L"Domain Controller Demotion";
        ObjectName = v10;
      }
      else
      {
        do
          ++v8;
        while ( ObjectName[v8] );
        ObjectName[v8 - 2] = 0;
        v4 = 1;
      }
      ImpersonationToken = RpcImpersonateClient(0);
      if ( ImpersonationToken )
        goto LABEL_18;
      v11 = AccessCheckAndAuditAlarmW(
              L"Security Account Manager",
              0,
              ObjectTypeName,
              ObjectName,
              pSecurityDescriptor,
              1u,
              &DsRolepInfoMapping,
              0,
              &GrantedAccess,
              &AccessStatus,
              &pfGenerateOnClose);
      RpcRevertToSelf();
    }
    else
    {
      v11 = AccessCheck(
              pSecurityDescriptor,
              ClientToken,
              1u,
              &DsRolepInfoMapping,
              &PrivilegeSet,
              &PrivilegeSetLength,
              &GrantedAccess,
              &AccessStatus);
    }
    if ( !v11 )
    {
LABEL_18:
      ImpersonationToken = GetLastError();
      goto LABEL_21;
    }
    if ( !AccessStatus )
      ImpersonationToken = 5;
  }
LABEL_21:
  if ( ClientToken )
    NtClose(ClientToken);
  if ( v4 )
    LocalFree(ObjectName);
  if ( v5 )
    LocalFree(ObjectTypeName);
  return ImpersonationToken;
}

```

## disassembly

```asm
0x1800150cc  push    rbp
0x1800150ce  push    rbx
0x1800150cf  push    rsi
0x1800150d0  push    rdi
0x1800150d1  push    r12
0x1800150d3  push    r13
0x1800150d5  push    r14
0x1800150d7  push    r15
0x1800150d9  lea     rbp, [rsp-1A8h]
0x1800150e1  sub     rsp, 2A8h
0x1800150e8  mov     rax, cs:__security_cookie
0x1800150ef  xor     rax, rsp
0x1800150f2  mov     [rbp+1E0h+var_50], rax
0x1800150f9  xor     r12d, r12d
0x1800150fc  mov     [rsp+2E0h+PrivilegeSetLength], 1F4h
0x180015104  mov     rsi, rcx
0x180015107  mov     [rsp+2E0h+var_280], r12d
0x18001510c  lea     rcx, [rbp+1E0h+ClientToken]; NewTokenHandle
0x180015110  mov     [rbp+1E0h+ClientToken], r12
0x180015114  mov     [rsp+2E0h+var_27C], r12d
0x180015119  mov     r14d, r12d
0x18001511c  mov     [rsp+2E0h+var_268], r12d
0x180015121  mov     r15d, r12d
0x180015124  mov     [rsp+2E0h+ObjectName], r12
0x180015129  mov     dil, r8b
0x18001512c  mov     [rsp+2E0h+ObjectTypeName], r12
0x180015131  call    DsRolepGetImpersonationToken
0x180015136  mov     ebx, eax
0x180015138  test    eax, eax
0x18001513a  jnz     loc_1800152AF
0x180015140  test    dil, dil
0x180015143  jz      loc_180015251
0x180015149  lea     rdx, [rsp+2E0h+ObjectTypeName]
0x18001514e  mov     ecx, 703Bh; dwMessageId
0x180015153  call    DsRolepFormatOperationString
0x180015158  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001515c  lea     edi, [rbx+2]
0x18001515f  test    eax, eax
0x180015161  jz      short loc_180015171
0x180015163  lea     rax, aDsroleInterfac; "DsRole Interface"
0x18001516a  mov     [rsp+2E0h+ObjectTypeName], rax
0x18001516f  jmp     short loc_18001518C
0x180015171  mov     rdx, [rsp+2E0h+ObjectTypeName]
0x180015176  mov     rcx, rbx
0x180015179  inc     rcx
0x18001517c  cmp     [rdx+rcx*2], r12w
0x180015181  jnz     short loc_180015179
0x180015183  mov     [rdx+rcx*2-4], r12w
0x180015189  mov     r15d, edi
0x18001518c  mov     ecx, r12d
0x18001518f  lea     r13, DsRolepPromoteSD
0x180015196  cmp     rsi, r13
0x180015199  lea     rdx, [rsp+2E0h+ObjectName]
0x18001519e  setnz   cl
0x1800151a1  add     ecx, 7039h; dwMessageId
0x1800151a7  call    DsRolepFormatOperationString
0x1800151ac  test    eax, eax
0x1800151ae  jz      short loc_1800151CC
0x1800151b0  cmp     rsi, r13
0x1800151b3  lea     rcx, aDomainControll; "Domain Controller Demotion"
0x1800151ba  lea     rax, aDomainControll_0; "Domain Controller Promotion"
0x1800151c1  cmovnz  rax, rcx
0x1800151c5  mov     [rsp+2E0h+ObjectName], rax
0x1800151ca  jmp     short loc_1800151E4
0x1800151cc  mov     rcx, [rsp+2E0h+ObjectName]
0x1800151d1  inc     rbx
0x1800151d4  cmp     [rcx+rbx*2], r12w
0x1800151d9  jnz     short loc_1800151D1
0x1800151db  mov     [rcx+rbx*2-4], r12w
0x1800151e1  mov     r14d, edi
0x1800151e4  xor     ecx, ecx; BindingHandle
0x1800151e6  call    cs:__imp_RpcImpersonateClient
0x1800151ec  mov     ebx, eax
0x1800151ee  test    eax, eax
0x1800151f0  jnz     loc_180015298
0x1800151f6  mov     r8, [rsp+2E0h+ObjectTypeName]; ObjectTypeName
0x1800151fb  lea     rax, [rsp+2E0h+var_268]
0x180015200  mov     [rsp+2E0h+pfGenerateOnClose], rax; pfGenerateOnClose
0x180015205  lea     r9, DsRolepInfoMapping
0x18001520c  lea     rax, [rsp+2E0h+var_280]
0x180015211  xor     edx, edx; HandleId
0x180015213  mov     [rsp+2E0h+AccessStatus], rax; AccessStatus
0x180015218  lea     rcx, SubsystemName; "Security Account Manager"
0x18001521f  lea     rax, [rsp+2E0h+var_27C]
0x180015224  mov     [rsp+2E0h+GrantedAccess], rax; GrantedAccess
0x180015229  mov     [rsp+2E0h+ObjectCreation], r12d; ObjectCreation
0x18001522e  mov     [rsp+2E0h+GenericMapping], r9; GenericMapping
0x180015233  mov     r9, [rsp+2E0h+ObjectName]; ObjectName
0x180015238  mov     [rsp+2E0h+DesiredAccess], edi; DesiredAccess
0x18001523c  mov     [rsp+2E0h+SecurityDescriptor], rsi; SecurityDescriptor
0x180015241  call    cs:__imp_AccessCheckAndAuditAlarmW
0x180015247  mov     edi, eax
0x180015249  call    cs:__imp_RpcRevertToSelf
0x18001524f  jmp     short loc_180015294
0x180015251  mov     rdx, [rbp+1E0h+ClientToken]; ClientToken
0x180015255  lea     rax, [rsp+2E0h+var_280]
0x18001525a  mov     qword ptr [rsp+2E0h+ObjectCreation], rax; AccessStatus
0x18001525f  lea     r9, DsRolepInfoMapping; GenericMapping
0x180015266  lea     rax, [rsp+2E0h+var_27C]
0x18001526b  mov     r8d, 1; DesiredAccess
0x180015271  mov     [rsp+2E0h+GenericMapping], rax; GrantedAccess
0x180015276  mov     rcx, rsi; pSecurityDescriptor
0x180015279  lea     rax, [rsp+2E0h+PrivilegeSetLength]
0x18001527e  mov     qword ptr [rsp+2E0h+DesiredAccess], rax; PrivilegeSetLength
0x180015283  lea     rax, [rbp+1E0h+PrivilegeSet]
0x180015287  mov     [rsp+2E0h+SecurityDescriptor], rax; PrivilegeSet
0x18001528c  call    cs:__imp_AccessCheck
0x180015292  mov     edi, eax
0x180015294  test    edi, edi
0x180015296  jnz     short loc_1800152A2
0x180015298  call    cs:__imp_GetLastError
0x18001529e  mov     ebx, eax
0x1800152a0  jmp     short loc_1800152AF
0x1800152a2  cmp     [rsp+2E0h+var_280], r12d
0x1800152a7  mov     eax, 5
0x1800152ac  cmovz   ebx, eax
0x1800152af  mov     rcx, [rbp+1E0h+ClientToken]; Handle
0x1800152b3  test    rcx, rcx
0x1800152b6  jz      short loc_1800152BE
0x1800152b8  call    cs:__imp_NtClose
0x1800152be  test    r14d, r14d
0x1800152c1  jz      short loc_1800152CE
0x1800152c3  mov     rcx, [rsp+2E0h+ObjectName]; hMem
0x1800152c8  call    cs:__imp_LocalFree
0x1800152ce  test    r15d, r15d
0x1800152d1  jz      short loc_1800152DE
0x1800152d3  mov     rcx, [rsp+2E0h+ObjectTypeName]; hMem
0x1800152d8  call    cs:__imp_LocalFree
0x1800152de  mov     eax, ebx
0x1800152e0  mov     rcx, [rbp+1E0h+var_50]
0x1800152e7  xor     rcx, rsp; StackCookie
0x1800152ea  call    __security_check_cookie
0x1800152ef  add     rsp, 2A8h
0x1800152f6  pop     r15
0x1800152f8  pop     r14
0x1800152fa  pop     r13
0x1800152fc  pop     r12
0x1800152fe  pop     rdi
0x1800152ff  pop     rsi
0x180015300  pop     rbx
0x180015301  pop     rbp
0x180015302  retn
```
