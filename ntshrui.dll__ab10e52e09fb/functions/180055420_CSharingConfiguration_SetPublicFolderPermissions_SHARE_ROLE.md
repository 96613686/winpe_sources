# CSharingConfiguration::_SetPublicFolderPermissions(SHARE_ROLE)

- ea: `0x180055420`
- end: `0x18005561f`
- name: `?_SetPublicFolderPermissions@CSharingConfiguration@@AEAAJW4SHARE_ROLE@@@Z`
- size: `511`
- prototype: `__int64 __fastcall(CSharingConfiguration *__hidden this, enum SHARE_ROLE)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800541d0`
- `0x1800543b0`

## callees

- `0x1800098dc`
- `0x18000d1f0`
- `0x18000f840`
- `0x18001d260`
- `0x180023adc`
- `0x1800254e0`
- `0x180033fc0`
- `0x1800553a4`
- `0x180055420`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18005551f`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18005551f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800554fb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800554fb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800555d9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800555e2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800555fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800555d9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800555e2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800555fa`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x1800554ab`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x1800554ab`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x1800555c1`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x1800555c1`

## pseudocode

```c
__int64 __fastcall CSharingConfiguration::_SetPublicFolderPermissions(
        CSharingConfiguration *this,
        enum SHARE_ROLE a2,
        __int64 a3,
        unsigned int a4)
{
  signed int SharePath; // ebx
  signed int NamedSecurityInfoW; // eax
  HLOCAL v7; // rax
  unsigned int v8; // edx
  CAceList *v9; // rdi
  void *v10; // rsi
  __int64 v11; // rcx
  __int64 v12; // r8
  int v13; // eax
  void *v14; // rdx
  int v15; // r8d
  PACL v16; // r14
  signed int v17; // eax
  PACL pDacl; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbSid; // [rsp+48h] [rbp-B8h] BYREF
  PACL ppDacl; // [rsp+50h] [rbp-B0h] BYREF
  PSECURITY_DESCRIPTOR hMem; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR pObjectName[264]; // [rsp+60h] [rbp-A0h] BYREF

  SharePath = CSharingConfiguration::_GetSharePath(this, DEFSHAREID_PUBLIC, pObjectName, a4);
  if ( SharePath >= 0 )
  {
    hMem = 0;
    ppDacl = 0;
    NamedSecurityInfoW = GetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 4u, 0, 0, &ppDacl, 0, &hMem);
    SharePath = NamedSecurityInfoW;
    if ( NamedSecurityInfoW > 0 )
      SharePath = (unsigned __int16)NamedSecurityInfoW | 0x80070000;
    if ( SharePath >= 0 )
    {
      pDacl = 0;
      SharePath = CAceList::CreateInstance(ppDacl, (struct CAceList **)&pDacl);
      if ( SharePath >= 0 )
      {
        SharePath = -2147024882;
        cbSid = 68;
        v7 = LocalAlloc(0x40u, 0x44u);
        v9 = (CAceList *)pDacl;
        v10 = v7;
        if ( v7 )
        {
          if ( CreateWellKnownSid(WinWorldSid, 0, v7, &cbSid)
            || (SharePath = ResultFromKnownLastError(), SharePath >= 0) )
          {
            if ( a2 == SHARE_ROLE_INVALID )
            {
              LOBYTE(v12) = 3;
              v13 = CAceList::_RemoveExplicitAcesHelper(v11, v10, v12, (char *)v9 + 8, 0);
            }
            else
            {
              v15 = 1179817;
              if ( a2 )
                v15 = 2032127;
              v13 = CAceList::SetExplicitAllowAce(v9, v10, v15, 3);
            }
            SharePath = v13;
            if ( v13 >= 0 )
            {
              pDacl = 0;
              SharePath = CAceList::GetAclForExplicitEntries(v9, v14, &pDacl);
              if ( SharePath >= 0 )
              {
                v16 = pDacl;
                v17 = SetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 4u, 0, 0, pDacl, 0);
                SharePath = v17;
                if ( v17 > 0 )
                  SharePath = (unsigned __int16)v17 | 0x80070000;
                LocalFree(v16);
              }
            }
          }
          LocalFree(v10);
        }
        if ( v9 )
          CAceList::`scalar deleting destructor'(v9, v8);
      }
      LocalFree(hMem);
    }
  }
  return (unsigned int)SharePath;
}

```

## disassembly

```asm
0x180055420  push    rbp
0x180055422  push    rbx
0x180055423  push    rsi
0x180055424  push    rdi
0x180055425  push    r14
0x180055427  lea     rbp, [rsp-180h]
0x18005542f  sub     rsp, 280h
0x180055436  mov     rax, cs:__security_cookie
0x18005543d  xor     rax, rsp
0x180055440  mov     [rbp+1A0h+var_30], rax
0x180055447  mov     r14d, edx
0x18005544a  lea     r8, [rsp+2A0h+pObjectName]; unsigned __int16 *
0x18005544f  mov     edx, 2; enum DEF_SHARE_ID
0x180055454  call    ?_GetSharePath@CSharingConfiguration@@AEAAJW4DEF_SHARE_ID@@PEAGK@Z; CSharingConfiguration::_GetSharePath(DEF_SHARE_ID,ushort *,ulong)
0x180055459  mov     ebx, eax
0x18005545b  test    eax, eax
0x18005545d  js      loc_180055600
0x180055463  xor     r9d, r9d; ppsidOwner
0x180055466  mov     [rsp+2A0h+hMem], 0
0x18005546f  lea     rax, [rsp+2A0h+hMem]
0x180055474  mov     [rsp+2A0h+var_250], 0
0x18005547d  mov     [rsp+2A0h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x180055482  lea     rcx, [rsp+2A0h+pObjectName]; pObjectName
0x180055487  lea     rax, [rsp+2A0h+var_250]
0x18005548c  mov     [rsp+2A0h+ppSacl], 0; ppSacl
0x180055495  mov     [rsp+2A0h+ppDacl], rax; ppDacl
0x18005549a  lea     edx, [r9+1]; ObjectType
0x18005549e  lea     r8d, [r9+4]; SecurityInfo
0x1800554a2  mov     [rsp+2A0h+ppsidGroup], 0; ppsidGroup
0x1800554ab  call    cs:__imp_GetNamedSecurityInfoW
0x1800554b1  mov     ebx, eax
0x1800554b3  test    eax, eax
0x1800554b5  jle     short loc_1800554C0
0x1800554b7  movzx   ebx, ax
0x1800554ba  or      ebx, 80070000h
0x1800554c0  test    ebx, ebx
0x1800554c2  js      loc_180055600
0x1800554c8  mov     rcx, [rsp+2A0h+var_250]; struct _ACL *
0x1800554cd  lea     rdx, [rsp+2A0h+pDacl]; struct CAceList **
0x1800554d2  mov     [rsp+2A0h+pDacl], 0
0x1800554db  call    ?CreateInstance@CAceList@@SAJPEAU_ACL@@PEAPEAV1@@Z; CAceList::CreateInstance(_ACL *,CAceList * *)
0x1800554e0  mov     ebx, eax
0x1800554e2  test    eax, eax
0x1800554e4  js      loc_1800555F5
0x1800554ea  mov     edx, 44h ; 'D'; uBytes
0x1800554ef  mov     ebx, 8007000Eh
0x1800554f4  mov     [rsp+2A0h+cbSid], edx
0x1800554f8  lea     ecx, [rdx-4]; uFlags
0x1800554fb  call    cs:__imp_LocalAlloc
0x180055501  mov     rdi, [rsp+2A0h+pDacl]
0x180055506  mov     rsi, rax
0x180055509  test    rax, rax
0x18005550c  jz      loc_1800555E8
0x180055512  xor     edx, edx; DomainSid
0x180055514  lea     r9, [rsp+2A0h+cbSid]; cbSid
0x180055519  mov     r8, rax; pSid
0x18005551c  lea     ecx, [rdx+1]; WellKnownSidType
0x18005551f  call    cs:__imp_CreateWellKnownSid
0x180055525  test    eax, eax
0x180055527  jnz     short loc_180055538
0x180055529  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18005552e  mov     ebx, eax
0x180055530  test    eax, eax
0x180055532  js      loc_1800555DF
0x180055538  mov     rdx, rsi; void *
0x18005553b  cmp     r14d, 0FFFFFFFFh
0x18005553f  jnz     short loc_180055557
0x180055541  lea     r9, [rdi+8]
0x180055545  mov     dword ptr [rsp+2A0h+ppsidGroup], 0
0x18005554d  mov     r8b, 3
0x180055550  call    ?_RemoveExplicitAcesHelper@CAceList@@AEAAJPEAXEAEAV?$CDPA@VCAce@@V?$CTContainer_PolicyUnOwned@VCAce@@@@@@H@Z; CAceList::_RemoveExplicitAcesHelper(void *,uchar,CDPA<CAce,CTContainer_PolicyUnOwned<CAce>> &,int)
0x180055555  jmp     short loc_180055573
0x180055557  mov     r9b, 3; unsigned __int8
0x18005555a  mov     rcx, rdi; this
0x18005555d  mov     r8d, 1200A9h
0x180055563  test    r14d, r14d
0x180055566  jz      short loc_18005556E
0x180055568  mov     r8d, 1F01FFh; unsigned int
0x18005556e  call    ?SetExplicitAllowAce@CAceList@@QEAAJPEAXKE@Z; CAceList::SetExplicitAllowAce(void *,ulong,uchar)
0x180055573  mov     ebx, eax
0x180055575  test    eax, eax
0x180055577  js      short loc_1800555DF
0x180055579  lea     r8, [rsp+2A0h+pDacl]; struct _ACL **
0x18005557e  mov     [rsp+2A0h+pDacl], 0
0x180055587  mov     rcx, rdi; this
0x18005558a  call    ?GetAclForExplicitEntries@CAceList@@QEAAJPEAXPEAPEAU_ACL@@@Z; CAceList::GetAclForExplicitEntries(void *,_ACL * *)
0x18005558f  mov     ebx, eax
0x180055591  test    eax, eax
0x180055593  js      short loc_1800555DF
0x180055595  mov     r14, [rsp+2A0h+pDacl]
0x18005559a  lea     rcx, [rsp+2A0h+pObjectName]; pObjectName
0x18005559f  xor     r9d, r9d; psidOwner
0x1800555a2  mov     [rsp+2A0h+ppSacl], 0; pSacl
0x1800555ab  mov     [rsp+2A0h+ppDacl], r14; pDacl
0x1800555b0  mov     [rsp+2A0h+ppsidGroup], 0; psidGroup
0x1800555b9  lea     edx, [r9+1]; ObjectType
0x1800555bd  lea     r8d, [r9+4]; SecurityInfo
0x1800555c1  call    cs:__imp_SetNamedSecurityInfoW
0x1800555c7  mov     ebx, eax
0x1800555c9  test    eax, eax
0x1800555cb  jle     short loc_1800555D6
0x1800555cd  movzx   ebx, ax
0x1800555d0  or      ebx, 80070000h
0x1800555d6  mov     rcx, r14; hMem
0x1800555d9  call    cs:__imp_LocalFree
0x1800555df  mov     rcx, rsi; hMem
0x1800555e2  call    cs:__imp_LocalFree
0x1800555e8  test    rdi, rdi
0x1800555eb  jz      short loc_1800555F5
0x1800555ed  mov     rcx, rdi; this
0x1800555f0  call    ??_GCAceList@@QEAAPEAXI@Z; CAceList::`scalar deleting destructor'(uint)
0x1800555f5  mov     rcx, [rsp+2A0h+hMem]; hMem
0x1800555fa  call    cs:__imp_LocalFree
0x180055600  mov     eax, ebx
0x180055602  mov     rcx, [rbp+1A0h+var_30]
0x180055609  xor     rcx, rsp; StackCookie
0x18005560c  call    __security_check_cookie
0x180055611  add     rsp, 280h
0x180055618  pop     r14
0x18005561a  pop     rdi
0x18005561b  pop     rsi
0x18005561c  pop     rbx
0x18005561d  pop     rbp
0x18005561e  retn
```
