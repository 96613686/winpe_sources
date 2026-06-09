# Rdp::Security::EnableIddAccessToTermsrvProcess(void)

- ea: `0x1800c53ec`
- end: `0x1800c571d`
- name: `?EnableIddAccessToTermsrvProcess@Security@Rdp@@YAJXZ`
- size: `817`
- prototype: `__int64 __fastcall(Rdp::Security *this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002b620`
- `0x1800c1df0`

## callees

- `0x1800015f0`
- `0x180033da0`
- `0x1800c53ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c547e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5554`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c55c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5637`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c547e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5554`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c55c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5637`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800c551a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800c5606`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800c551a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800c5606`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c56ec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c56fb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c56ec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c56fb`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800c546a`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800c546a`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800c56dd`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800c56dd`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x1800c5629`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x1800c5629`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x1800c55bc`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x1800c55bc`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x1800c554a`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x1800c554a`

## string_xrefs

- `0x1800c54a7`: `Failed to allocate LOCAL SERVICE sid`
- `0x1800c54ce`: `clientcore\termsrv\rdpplatform\gfxpipe\gfxsource\security.cpp`
- `0x1800c5680`: `clientcore\termsrv\rdpplatform\gfxpipe\gfxsource\security.cpp`
- `0x1800c55eb`: `SetEntriesInAcl failed`
- `0x1800c5579`: `GetSecurityInfo failed`
- `0x1800c54c0`: `EnableIddAccessToTermsrvProcess`
- `0x1800c5675`: `EnableIddAccessToTermsrvProcess`
- `0x1800c565c`: `SetSecurityInfo failed`

## pseudocode

```c
__int64 __fastcall Rdp::Security::EnableIddAccessToTermsrvProcess(Rdp::Security *this)
{
  signed int v1; // edi
  signed int LastError; // eax
  int v3; // ecx
  int v4; // r8d
  int v5; // r9d
  HANDLE CurrentProcess; // rax
  signed int v7; // eax
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  const char *v11; // rax
  char *v12; // rdx
  signed int v13; // eax
  struct _ACL *v14; // rbx
  HANDLE v15; // rax
  signed int v16; // eax
  int v18; // [rsp+60h] [rbp-59h] BYREF
  int v19; // [rsp+64h] [rbp-55h] BYREF
  const char *v20; // [rsp+68h] [rbp-51h] BYREF
  const char *v21; // [rsp+70h] [rbp-49h] BYREF
  const char *v22; // [rsp+78h] [rbp-41h] BYREF
  const char *v23; // [rsp+80h] [rbp-39h] BYREF
  PSID pSid; // [rsp+88h] [rbp-31h] BYREF
  PACL NewAcl; // [rsp+90h] [rbp-29h] BYREF
  PACL ppDacl; // [rsp+98h] [rbp-21h] BYREF
  PSECURITY_DESCRIPTOR ppSecurityDescriptor; // [rsp+A0h] [rbp-19h] BYREF
  struct _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+A8h] [rbp-11h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+D8h] [rbp+1Fh] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  pSid = 0;
  ppDacl = 0;
  v1 = 0;
  NewAcl = 0;
  ppSecurityDescriptor = 0;
  memset(&pListOfExplicitEntries, 0, sizeof(pListOfExplicitEntries));
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x13u, 0, 0, 0, 0, 0, 0, 0, &pSid) )
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      v1 = (unsigned __int16)LastError | 0x80070000;
    if ( v1 < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 > 2 )
      {
        v18 = 184;
        v20 = "Failed to allocate LOCAL SERVICE sid";
        v19 = v1;
        v21 = "EnableIddAccessToTermsrvProcess";
        v22 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\security.cpp";
        v23 = "Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v3,
          (unsigned int)byte_1801A95C5,
          v4,
          v5,
          (__int64)&v23,
          (__int64)&v19,
          (__int64)&v22,
          (__int64)&v18,
          (__int64)&v21,
          (__int64)&v20);
      }
      goto LABEL_26;
    }
  }
  CurrentProcess = GetCurrentProcess();
  if ( GetSecurityInfo(CurrentProcess, SE_KERNEL_OBJECT, 4u, 0, 0, &ppDacl, 0, &ppSecurityDescriptor) )
  {
    v7 = GetLastError();
    v1 = v7;
    if ( v7 > 0 )
      v1 = (unsigned __int16)v7 | 0x80070000;
    if ( v1 < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 <= 2 )
        goto LABEL_26;
      v11 = "GetSecurityInfo failed";
      v19 = 200;
      v12 = byte_1801A9521;
      goto LABEL_25;
    }
  }
  pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)pSid;
  pListOfExplicitEntries.grfAccessMode = GRANT_ACCESS;
  pListOfExplicitEntries.grfAccessPermissions = 4160;
  pListOfExplicitEntries.grfInheritance = 0;
  pListOfExplicitEntries.Trustee.TrusteeForm = TRUSTEE_IS_SID;
  pListOfExplicitEntries.Trustee.TrusteeType = TRUSTEE_IS_USER;
  if ( SetEntriesInAclW(1u, &pListOfExplicitEntries, ppDacl, &NewAcl) )
  {
    v13 = GetLastError();
    v1 = v13;
    if ( v13 > 0 )
      v1 = (unsigned __int16)v13 | 0x80070000;
    if ( v1 < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 <= 2 )
        goto LABEL_26;
      v11 = "SetEntriesInAcl failed";
      v19 = 216;
      v12 = byte_1801A9573;
      goto LABEL_25;
    }
  }
  v14 = NewAcl;
  v15 = GetCurrentProcess();
  if ( SetSecurityInfo(v15, SE_KERNEL_OBJECT, 4u, 0, 0, v14, 0) )
  {
    v16 = GetLastError();
    v1 = v16;
    if ( v16 > 0 )
      v1 = (unsigned __int16)v16 | 0x80070000;
    if ( v1 < 0 && (unsigned int)dword_1801B76C8 > 2 )
    {
      v11 = "SetSecurityInfo failed";
      v19 = 231;
      v12 = &byte_1801A94CF;
LABEL_25:
      v23 = v11;
      v22 = "EnableIddAccessToTermsrvProcess";
      v21 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\security.cpp";
      v20 = "Error HResult failed";
      v18 = v1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v8,
        (_DWORD)v12,
        v9,
        v10,
        (__int64)&v20,
        (__int64)&v18,
        (__int64)&v21,
        (__int64)&v19,
        (__int64)&v22,
        (__int64)&v23);
    }
  }
LABEL_26:
  if ( pSid )
    FreeSid(pSid);
  if ( ppSecurityDescriptor )
    LocalFree(ppSecurityDescriptor);
  if ( NewAcl )
    LocalFree(NewAcl);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x1800c53ec  push    rbp
0x1800c53ee  push    rbx
0x1800c53ef  push    rsi
0x1800c53f0  push    rdi
0x1800c53f1  push    r14
0x1800c53f3  lea     rbp, [rsp-37h]
0x1800c53f8  sub     rsp, 0F0h
0x1800c53ff  mov     rax, cs:__security_cookie
0x1800c5406  xor     rax, rsp
0x1800c5409  mov     [rbp+57h+var_30], rax
0x1800c540d  xor     esi, esi
0x1800c540f  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x1800c5415  xorps   xmm0, xmm0
0x1800c5418  mov     [rbp+57h+var_88], rsi
0x1800c541c  lea     rax, [rbp+57h+var_88]
0x1800c5420  mov     [rbp+57h+ppDacl], rsi
0x1800c5424  mov     [rsp+110h+pSid], rax; pSid
0x1800c5429  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x1800c542d  mov     [rsp+110h+nSubAuthority7], esi; nSubAuthority7
0x1800c5431  lea     ebx, [rsi+1]
0x1800c5434  mov     [rsp+110h+nSubAuthority6], esi; nSubAuthority6
0x1800c5438  lea     r8d, [rsi+13h]; nSubAuthority0
0x1800c543c  mov     [rsp+110h+nSubAuthority5], esi; nSubAuthority5
0x1800c5440  mov     dl, bl; nSubAuthorityCount
0x1800c5442  mov     [rsp+110h+nSubAuthority4], esi; nSubAuthority4
0x1800c5446  xor     r9d, r9d; nSubAuthority1
0x1800c5449  mov     [rsp+110h+nSubAuthority3], esi; nSubAuthority3
0x1800c544d  mov     edi, esi
0x1800c544f  mov     [rsp+110h+nSubAuthority2], esi; nSubAuthority2
0x1800c5453  mov     [rbp+57h+NewAcl], rsi
0x1800c5457  mov     [rbp+57h+ppSecurityDescriptor], rsi
0x1800c545b  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], xmm0
0x1800c545f  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], esi
0x1800c5462  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.pMultipleTrustee], xmm0
0x1800c5466  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], xmm0
0x1800c546a  call    cs:__imp_AllocateAndInitializeSid
0x1800c5470  mov     r14d, 80070000h
0x1800c5476  test    eax, eax
0x1800c5478  jnz     loc_1800C551A
0x1800c547e  call    cs:__imp_GetLastError
0x1800c5484  mov     edi, eax
0x1800c5486  test    eax, eax
0x1800c5488  jle     short loc_1800C5490
0x1800c548a  movzx   edi, ax
0x1800c548d  or      edi, r14d
0x1800c5490  test    edi, edi
0x1800c5492  jns     loc_1800C551A
0x1800c5498  mov     eax, cs:dword_1801B76C8
0x1800c549e  cmp     eax, 2
0x1800c54a1  jbe     loc_1800C56D4
0x1800c54a7  lea     rax, aFailedToAlloca_7; "Failed to allocate LOCAL SERVICE sid"
0x1800c54ae  mov     [rbp+57h+var_B0], 0B8h
0x1800c54b5  mov     [rbp+57h+var_A8], rax
0x1800c54b9  lea     rdx, byte_1801A95C5
0x1800c54c0  lea     rax, aEnableiddacces; "EnableIddAccessToTermsrvProcess"
0x1800c54c7  mov     [rbp+57h+var_AC], edi
0x1800c54ca  mov     [rbp+57h+var_A0], rax
0x1800c54ce  lea     rax, aClientcoreTerm_11; "clientcore\\termsrv\\rdpplatform\\gfxpi"...
0x1800c54d5  mov     [rbp+57h+var_98], rax
0x1800c54d9  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800c54e0  mov     [rbp+57h+var_90], rax
0x1800c54e4  lea     rax, [rbp+57h+var_A8]
0x1800c54e8  mov     qword ptr [rsp+110h+nSubAuthority7], rax
0x1800c54ed  lea     rax, [rbp+57h+var_A0]
0x1800c54f1  mov     qword ptr [rsp+110h+nSubAuthority6], rax
0x1800c54f6  lea     rax, [rbp+57h+var_B0]
0x1800c54fa  mov     qword ptr [rsp+110h+nSubAuthority5], rax
0x1800c54ff  lea     rax, [rbp+57h+var_98]
0x1800c5503  mov     qword ptr [rsp+110h+nSubAuthority4], rax
0x1800c5508  lea     rax, [rbp+57h+var_AC]
0x1800c550c  mov     qword ptr [rsp+110h+nSubAuthority3], rax
0x1800c5511  lea     rax, [rbp+57h+var_90]
0x1800c5515  jmp     loc_1800C56CA
0x1800c551a  call    cs:__imp_GetCurrentProcess
0x1800c5520  mov     rcx, rax; handle
0x1800c5523  xor     r9d, r9d; ppsidOwner
0x1800c5526  lea     rax, [rbp+57h+ppSecurityDescriptor]
0x1800c552a  mov     qword ptr [rsp+110h+nSubAuthority5], rax; ppSecurityDescriptor
0x1800c552f  lea     rax, [rbp+57h+ppDacl]
0x1800c5533  mov     qword ptr [rsp+110h+nSubAuthority4], rsi; ppSacl
0x1800c5538  mov     qword ptr [rsp+110h+nSubAuthority3], rax; ppDacl
0x1800c553d  lea     edx, [r9+6]; ObjectType
0x1800c5541  lea     r8d, [r9+4]; SecurityInfo
0x1800c5545  mov     qword ptr [rsp+110h+nSubAuthority2], rsi; ppsidGroup
0x1800c554a  call    cs:__imp_GetSecurityInfo
0x1800c5550  test    eax, eax
0x1800c5552  jz      short loc_1800C5593
0x1800c5554  call    cs:__imp_GetLastError
0x1800c555a  mov     edi, eax
0x1800c555c  test    eax, eax
0x1800c555e  jle     short loc_1800C5566
0x1800c5560  movzx   edi, ax
0x1800c5563  or      edi, r14d
0x1800c5566  test    edi, edi
0x1800c5568  jns     short loc_1800C5593
0x1800c556a  mov     eax, cs:dword_1801B76C8
0x1800c5570  cmp     eax, 2
0x1800c5573  jbe     loc_1800C56D4
0x1800c5579  lea     rax, aGetsecurityinf_0; "GetSecurityInfo failed"
0x1800c5580  mov     [rbp+57h+var_AC], 0C8h
0x1800c5587  lea     rdx, byte_1801A9521
0x1800c558e  jmp     loc_1800C5671
0x1800c5593  mov     rax, [rbp+57h+var_88]
0x1800c5597  lea     r9, [rbp+57h+NewAcl]; NewAcl
0x1800c559b  mov     r8, [rbp+57h+ppDacl]; OldAcl
0x1800c559f  lea     rdx, [rbp+57h+pListOfExplicitEntries]; pListOfExplicitEntries
0x1800c55a3  mov     ecx, ebx; cCountOfExplicitEntries
0x1800c55a5  mov     [rbp+57h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x1800c55a9  mov     [rbp+57h+pListOfExplicitEntries.grfAccessMode], ebx
0x1800c55ac  mov     [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], 1040h
0x1800c55b3  mov     [rbp+57h+pListOfExplicitEntries.grfInheritance], esi
0x1800c55b6  mov     [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeForm], esi
0x1800c55b9  mov     [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], ebx
0x1800c55bc  call    cs:__imp_SetEntriesInAclW
0x1800c55c2  test    eax, eax
0x1800c55c4  jz      short loc_1800C5602
0x1800c55c6  call    cs:__imp_GetLastError
0x1800c55cc  mov     edi, eax
0x1800c55ce  test    eax, eax
0x1800c55d0  jle     short loc_1800C55D8
0x1800c55d2  movzx   edi, ax
0x1800c55d5  or      edi, r14d
0x1800c55d8  test    edi, edi
0x1800c55da  jns     short loc_1800C5602
0x1800c55dc  mov     eax, cs:dword_1801B76C8
0x1800c55e2  cmp     eax, 2
0x1800c55e5  jbe     loc_1800C56D4
0x1800c55eb  lea     rax, aSetentriesinac_0; "SetEntriesInAcl failed"
0x1800c55f2  mov     [rbp+57h+var_AC], 0D8h
0x1800c55f9  lea     rdx, byte_1801A9573
0x1800c5600  jmp     short loc_1800C5671
0x1800c5602  mov     rbx, [rbp+57h+NewAcl]
0x1800c5606  call    cs:__imp_GetCurrentProcess
0x1800c560c  xor     r9d, r9d; psidOwner
0x1800c560f  mov     qword ptr [rsp+110h+nSubAuthority4], rsi; pSacl
0x1800c5614  mov     qword ptr [rsp+110h+nSubAuthority3], rbx; pDacl
0x1800c5619  mov     rcx, rax; handle
0x1800c561c  mov     qword ptr [rsp+110h+nSubAuthority2], rsi; psidGroup
0x1800c5621  lea     edx, [r9+6]; ObjectType
0x1800c5625  lea     r8d, [r9+4]; SecurityInfo
0x1800c5629  call    cs:__imp_SetSecurityInfo
0x1800c562f  test    eax, eax
0x1800c5631  jz      loc_1800C56D4
0x1800c5637  call    cs:__imp_GetLastError
0x1800c563d  mov     edi, eax
0x1800c563f  test    eax, eax
0x1800c5641  jle     short loc_1800C5649
0x1800c5643  movzx   edi, ax
0x1800c5646  or      edi, r14d
0x1800c5649  test    edi, edi
0x1800c564b  jns     loc_1800C56D4
0x1800c5651  mov     eax, cs:dword_1801B76C8
0x1800c5657  cmp     eax, 2
0x1800c565a  jbe     short loc_1800C56D4
0x1800c565c  lea     rax, aSetsecurityinf_0; "SetSecurityInfo failed"
0x1800c5663  mov     [rbp+57h+var_AC], 0E7h
0x1800c566a  lea     rdx, byte_1801A94CF
0x1800c5671  mov     [rbp+57h+var_90], rax
0x1800c5675  lea     rax, aEnableiddacces; "EnableIddAccessToTermsrvProcess"
0x1800c567c  mov     [rbp+57h+var_98], rax
0x1800c5680  lea     rax, aClientcoreTerm_11; "clientcore\\termsrv\\rdpplatform\\gfxpi"...
0x1800c5687  mov     [rbp+57h+var_A0], rax
0x1800c568b  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800c5692  mov     [rbp+57h+var_A8], rax
0x1800c5696  lea     rax, [rbp+57h+var_90]
0x1800c569a  mov     qword ptr [rsp+110h+nSubAuthority7], rax
0x1800c569f  lea     rax, [rbp+57h+var_98]
0x1800c56a3  mov     qword ptr [rsp+110h+nSubAuthority6], rax
0x1800c56a8  lea     rax, [rbp+57h+var_AC]
0x1800c56ac  mov     qword ptr [rsp+110h+nSubAuthority5], rax
0x1800c56b1  lea     rax, [rbp+57h+var_A0]
0x1800c56b5  mov     qword ptr [rsp+110h+nSubAuthority4], rax
0x1800c56ba  lea     rax, [rbp+57h+var_B0]
0x1800c56be  mov     qword ptr [rsp+110h+nSubAuthority3], rax
0x1800c56c3  lea     rax, [rbp+57h+var_A8]
0x1800c56c7  mov     [rbp+57h+var_B0], edi
0x1800c56ca  mov     qword ptr [rsp+110h+nSubAuthority2], rax
0x1800c56cf  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800c56d4  mov     rcx, [rbp+57h+var_88]; pSid
0x1800c56d8  test    rcx, rcx
0x1800c56db  jz      short loc_1800C56E3
0x1800c56dd  call    cs:__imp_FreeSid
0x1800c56e3  mov     rcx, [rbp+57h+ppSecurityDescriptor]; hMem
0x1800c56e7  test    rcx, rcx
0x1800c56ea  jz      short loc_1800C56F2
0x1800c56ec  call    cs:__imp_LocalFree
0x1800c56f2  mov     rcx, [rbp+57h+NewAcl]; hMem
0x1800c56f6  test    rcx, rcx
0x1800c56f9  jz      short loc_1800C5701
0x1800c56fb  call    cs:__imp_LocalFree
0x1800c5701  mov     eax, edi
0x1800c5703  mov     rcx, [rbp+57h+var_30]
0x1800c5707  xor     rcx, rsp; StackCookie
0x1800c570a  call    __security_check_cookie
0x1800c570f  add     rsp, 0F0h
0x1800c5716  pop     r14
0x1800c5718  pop     rdi
0x1800c5719  pop     rsi
0x1800c571a  pop     rbx
0x1800c571b  pop     rbp
0x1800c571c  retn
```
