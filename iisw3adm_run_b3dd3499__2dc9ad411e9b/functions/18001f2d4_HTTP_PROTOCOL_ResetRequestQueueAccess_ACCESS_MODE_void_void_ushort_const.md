# HTTP_PROTOCOL::ResetRequestQueueAccess(_ACCESS_MODE,void *,void *,ushort const *)

- ea: `0x18001f2d4`
- end: `0x18001f511`
- name: `?ResetRequestQueueAccess@HTTP_PROTOCOL@@AEAAXW4_ACCESS_MODE@@PEAX1PEBG@Z`
- size: `573`
- prototype: `void(HTTP_PROTOCOL *__hidden this, enum _ACCESS_MODE, void *, void *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18001d6cc`

## callees

- `0x1800058e4`
- `0x18001f2d4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001f35b`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001f35b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f4bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f4cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f4bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f4cb`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x18001f3c4`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x18001f3c4`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18001f40b`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18001f40b`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18001f460`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18001f460`
- `iisutil!PuDbgPrintError` at `0x18001f4ad`
- `iisutil!PuDbgPrintError` at `0x18001f4ad`
- `iisutil!?GetSID@CSecurityDispenser@@QEAAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z` at `0x18001f34a`
- `iisutil!?GetSID@CSecurityDispenser@@QEAAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z` at `0x18001f34a`

## string_xrefs

- `0x18001f4a2`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\http_protocol.cxx`
- `0x18001f3e8`: `Could not get security info for the app pool handle \n`
- `0x18001f42f`: `Setting ACE's into ACL failed.\n`
- `0x18001f482`: `Could not set new security info \n`
- `0x18001f496`: `HTTP_PROTOCOL::ResetRequestQueueAccess`

## pseudocode

```c
void __fastcall HTTP_PROTOCOL::ResetRequestQueueAccess(
        HTTP_PROTOCOL *this,
        enum _ACCESS_MODE a2,
        WCHAR *a3,
        void *a4,
        unsigned __int16 *a5)
{
  signed int v7; // ebx
  __int64 v8; // rcx
  struct _EXPLICIT_ACCESS_W *p_pListOfExplicitEntries; // rax
  signed int SecurityInfo; // eax
  signed int v11; // eax
  signed int v12; // eax
  PACL OldAcl; // [rsp+48h] [rbp-1h] BYREF
  PSECURITY_DESCRIPTOR hMem; // [rsp+50h] [rbp+7h] BYREF
  unsigned __int16 *v15; // [rsp+58h] [rbp+Fh] BYREF
  struct _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+60h] [rbp+17h] BYREF
  PACL NewAcl; // [rsp+A8h] [rbp+5Fh] BYREF
  PSID pSid2; // [rsp+B8h] [rbp+6Fh] BYREF

  NewAcl = 0;
  OldAcl = 0;
  pSid2 = 0;
  hMem = 0;
  memset(&pListOfExplicitEntries, 0, sizeof(pListOfExplicitEntries));
  if ( !a3 )
  {
    v7 = -2147024809;
LABEL_28:
    v15 = a5;
    WEB_ADMIN_SERVICE::LogW3svcEvent(g_pWebAdminService, 0xC0000402, 1u, (const unsigned __int16 **const)&v15, v7);
    return;
  }
  if ( CSecurityDispenser::GetSID((WEB_ADMIN_SERVICE *)((char *)g_pWebAdminService + 1416), WinLocalSystemSid, &pSid2)
    || !EqualSid(a3, pSid2) )
  {
    v8 = 48;
    p_pListOfExplicitEntries = &pListOfExplicitEntries;
    do
    {
      LOBYTE(p_pListOfExplicitEntries->grfAccessPermissions) = 0;
      p_pListOfExplicitEntries = (struct _EXPLICIT_ACCESS_W *)((char *)p_pListOfExplicitEntries + 1);
      --v8;
    }
    while ( v8 );
    pListOfExplicitEntries.Trustee.TrusteeForm = TRUSTEE_IS_SID;
    pListOfExplicitEntries.grfAccessPermissions = -2146435072;
    *(_QWORD *)&pListOfExplicitEntries.grfAccessMode = 2;
    pListOfExplicitEntries.Trustee.TrusteeType = TRUSTEE_IS_USER;
    pListOfExplicitEntries.Trustee.ptstrName = a3;
    SecurityInfo = GetSecurityInfo(a4, SE_FILE_OBJECT, 4u, 0, 0, &OldAcl, 0, &hMem);
    v7 = SecurityInfo;
    if ( SecurityInfo )
    {
      if ( SecurityInfo > 0 )
        v7 = (unsigned __int16)SecurityInfo | 0x80070000;
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\http_protocol.cxx",
          4457,
          "HTTP_PROTOCOL::ResetRequestQueueAccess",
          v7,
          "Could not get security info for the app pool handle \n");
    }
    else
    {
      v11 = SetEntriesInAclW(1u, &pListOfExplicitEntries, OldAcl, &NewAcl);
      v7 = v11;
      if ( v11 )
      {
        if ( v11 > 0 )
          v7 = (unsigned __int16)v11 | 0x80070000;
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\http_protocol.cxx",
            4473,
            "HTTP_PROTOCOL::ResetRequestQueueAccess",
            v7,
            "Setting ACE's into ACL failed.\n");
      }
      else
      {
        v7 = 0;
        v12 = SetSecurityInfo(a4, SE_FILE_OBJECT, 4u, 0, 0, NewAcl, 0);
        if ( v12 )
        {
          v7 = v12 > 0 ? (unsigned __int16)v12 | 0x80070000 : v12;
          if ( (g_dwDebugFlags & 0xF) != 0 )
            PuDbgPrintError(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\http_protocol.cxx",
              4492,
              "HTTP_PROTOCOL::ResetRequestQueueAccess",
              v7,
              "Could not set new security info \n");
        }
      }
    }
    if ( hMem )
      LocalFree(hMem);
    if ( NewAcl )
      LocalFree(NewAcl);
    if ( v7 < 0 )
      goto LABEL_28;
  }
}

```

## disassembly

```asm
0x18001f2d4  mov     rax, rsp
0x18001f2d7  mov     [rax+10h], rbx
0x18001f2db  mov     [rax+20h], rdi
0x18001f2df  mov     [rax+8], rcx
0x18001f2e3  push    rbp
0x18001f2e4  lea     rbp, [rax-57h]
0x18001f2e8  sub     rsp, 90h
0x18001f2ef  mov     [rbp+4Fh+NewAcl], 0
0x18001f2f7  xorps   xmm0, xmm0
0x18001f2fa  mov     [rbp+4Fh+OldAcl], 0
0x18001f302  mov     rdi, r9
0x18001f305  mov     [rbp+4Fh+pSid2], 0
0x18001f30d  mov     rbx, r8
0x18001f310  mov     [rbp+4Fh+hMem], 0
0x18001f318  movups  xmmword ptr [rbp+4Fh+pListOfExplicitEntries.grfAccessPermissions], xmm0
0x18001f31c  movups  xmmword ptr [rbp+4Fh+pListOfExplicitEntries.Trustee.pMultipleTrustee], xmm0
0x18001f320  movups  xmmword ptr [rbp+4Fh+pListOfExplicitEntries.Trustee.TrusteeType], xmm0
0x18001f324  test    r8, r8
0x18001f327  jnz     short loc_18001F333
0x18001f329  mov     ebx, 80070057h
0x18001f32e  jmp     loc_18001F4D5
0x18001f333  mov     rcx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x18001f33a  lea     r8, [rbp+4Fh+pSid2]
0x18001f33e  add     rcx, 588h
0x18001f345  mov     edx, 16h
0x18001f34a  call    cs:__imp_?GetSID@CSecurityDispenser@@QEAAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; CSecurityDispenser::GetSID(WELL_KNOWN_SID_TYPE,void * *)
0x18001f350  test    eax, eax
0x18001f352  jnz     short loc_18001F369
0x18001f354  mov     rdx, [rbp+4Fh+pSid2]; pSid2
0x18001f358  mov     rcx, rbx; pSid1
0x18001f35b  call    cs:__imp_EqualSid
0x18001f361  test    eax, eax
0x18001f363  jnz     loc_18001F4FC
0x18001f369  mov     ecx, 30h ; '0'
0x18001f36e  lea     rax, [rbp+4Fh+pListOfExplicitEntries]
0x18001f372  mov     byte ptr [rax], 0
0x18001f375  inc     rax
0x18001f378  sub     rcx, 1
0x18001f37c  jnz     short loc_18001F372
0x18001f37e  lea     rax, [rbp+4Fh+hMem]
0x18001f382  mov     [rbp+4Fh+pListOfExplicitEntries.Trustee.TrusteeForm], ecx
0x18001f385  mov     [rsp+90h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x18001f38a  lea     edx, [rcx+1]; ObjectType
0x18001f38d  mov     [rsp+90h+ppSacl], rcx; ppSacl
0x18001f392  lea     rax, [rbp+4Fh+OldAcl]
0x18001f396  mov     [rsp+90h+ppDacl], rax; ppDacl
0x18001f39b  lea     r8d, [rcx+4]; SecurityInfo
0x18001f39f  mov     [rsp+90h+ppsidGroup], rcx; ppsidGroup
0x18001f3a4  xor     r9d, r9d; ppsidOwner
0x18001f3a7  mov     rcx, rdi; handle
0x18001f3aa  mov     [rbp+4Fh+pListOfExplicitEntries.grfAccessPermissions], 80100000h
0x18001f3b1  mov     qword ptr [rbp+4Fh+pListOfExplicitEntries.grfAccessMode], 2
0x18001f3b9  mov     [rbp+4Fh+pListOfExplicitEntries.Trustee.TrusteeType], 1
0x18001f3c0  mov     [rbp+4Fh+pListOfExplicitEntries.Trustee.ptstrName], rbx
0x18001f3c4  call    cs:__imp_GetSecurityInfo
0x18001f3ca  mov     ebx, eax
0x18001f3cc  test    eax, eax
0x18001f3ce  jz      short loc_18001F3FA
0x18001f3d0  jle     short loc_18001F3DB
0x18001f3d2  movzx   ebx, ax
0x18001f3d5  or      ebx, 80070000h
0x18001f3db  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001f3e2  jz      loc_18001F4B3
0x18001f3e8  lea     rax, aCouldNotGetSec_0; "Could not get security info for the app"...
0x18001f3ef  mov     r8d, 1169h
0x18001f3f5  jmp     loc_18001F48F
0x18001f3fa  mov     r8, [rbp+4Fh+OldAcl]; OldAcl
0x18001f3fe  lea     r9, [rbp+4Fh+NewAcl]; NewAcl
0x18001f402  lea     rdx, [rbp+4Fh+pListOfExplicitEntries]; pListOfExplicitEntries
0x18001f406  mov     ecx, 1; cCountOfExplicitEntries
0x18001f40b  call    cs:__imp_SetEntriesInAclW
0x18001f411  mov     ebx, eax
0x18001f413  test    eax, eax
0x18001f415  jz      short loc_18001F43E
0x18001f417  jle     short loc_18001F422
0x18001f419  movzx   ebx, ax
0x18001f41c  or      ebx, 80070000h
0x18001f422  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001f429  jz      loc_18001F4B3
0x18001f42f  lea     rax, aSettingAceSInt; "Setting ACE's into ACL failed.\n"
0x18001f436  mov     r8d, 1179h
0x18001f43c  jmp     short loc_18001F48F
0x18001f43e  mov     rax, [rbp+4Fh+NewAcl]
0x18001f442  xor     ebx, ebx
0x18001f444  mov     [rsp+90h+ppSacl], rbx; pSacl
0x18001f449  xor     r9d, r9d; psidOwner
0x18001f44c  mov     [rsp+90h+ppDacl], rax; pDacl
0x18001f451  mov     rcx, rdi; handle
0x18001f454  mov     [rsp+90h+ppsidGroup], rbx; psidGroup
0x18001f459  lea     edx, [rbx+1]; ObjectType
0x18001f45c  lea     r8d, [rbx+4]; SecurityInfo
0x18001f460  call    cs:__imp_SetSecurityInfo
0x18001f466  test    eax, eax
0x18001f468  jz      short loc_18001F4B3
0x18001f46a  jg      short loc_18001F470
0x18001f46c  mov     ebx, eax
0x18001f46e  jmp     short loc_18001F479
0x18001f470  movzx   ebx, ax
0x18001f473  or      ebx, 80070000h
0x18001f479  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001f480  jz      short loc_18001F4B3
0x18001f482  lea     rax, aCouldNotSetNew; "Could not set new security info \n"
0x18001f489  mov     r8d, 118Ch
0x18001f48f  mov     rcx, cs:g_pDebug
0x18001f496  lea     r9, aHttpProtocolRe_0; "HTTP_PROTOCOL::ResetRequestQueueAccess"
0x18001f49d  mov     [rsp+90h+ppDacl], rax
0x18001f4a2  lea     rdx, aServercommonIn_29; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18001f4a9  mov     dword ptr [rsp+90h+ppsidGroup], ebx
0x18001f4ad  call    cs:__imp_PuDbgPrintError
0x18001f4b3  mov     rcx, [rbp+4Fh+hMem]; hMem
0x18001f4b7  test    rcx, rcx
0x18001f4ba  jz      short loc_18001F4C2
0x18001f4bc  call    cs:__imp_LocalFree
0x18001f4c2  mov     rcx, [rbp+4Fh+NewAcl]; hMem
0x18001f4c6  test    rcx, rcx
0x18001f4c9  jz      short loc_18001F4D1
0x18001f4cb  call    cs:__imp_LocalFree
0x18001f4d1  test    ebx, ebx
0x18001f4d3  jns     short loc_18001F4FC
0x18001f4d5  mov     rax, [rbp+4Fh+arg_20]
0x18001f4d9  lea     r9, [rbp+4Fh+var_40]; unsigned __int16 **
0x18001f4dd  mov     rcx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; this
0x18001f4e4  mov     r8d, 1; unsigned __int16
0x18001f4ea  mov     edx, 0C0000402h; unsigned int
0x18001f4ef  mov     [rbp+4Fh+var_40], rax
0x18001f4f3  mov     dword ptr [rsp+90h+ppsidGroup], ebx; unsigned int
0x18001f4f7  call    ?LogW3svcEvent@WEB_ADMIN_SERVICE@@QEAAXKGQEAPEBGK@Z; WEB_ADMIN_SERVICE::LogW3svcEvent(ulong,ushort,ushort const * * const,ulong)
0x18001f4fc  lea     r11, [rsp+90h+var_s0]
0x18001f504  mov     rbx, [r11+18h]
0x18001f508  mov     rdi, [r11+28h]
0x18001f50c  mov     rsp, r11
0x18001f50f  pop     rbp
0x18001f510  retn
```
