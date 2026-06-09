# DRMRepair

- ea: `0x18001c610`
- end: `0x18001cc90`
- name: `DRMRepair`
- size: `1664`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `21`
- tags: `file_ops, installer_update`

## callees

- `0x180001244`
- `0x180001284`
- `0x1800046c8`
- `0x1800196f8`
- `0x180019a30`
- `0x18001b250`
- `0x18001b2a0`
- `0x18001b800`
- `0x18001c610`
- `0x18001f610`
- `0x18002d044`
- `0x180034bb0`
- `0x1800356f8`
- `0x180036b9c`
- `0x1800370d8`
- `0x180039904`
- `0x180039de0`
- `0x18003a29c`
- `0x18003d994`
- `0x18004033c`
- `0x18005bd72`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001c970`
- `msvcrt!_wcsicmp` at `0x18001c981`
- `msvcrt!_wcsicmp` at `0x18001c970`
- `msvcrt!_wcsicmp` at `0x18001c981`

## string_xrefs

- `0x18001c629`: `[msdrm]:+DRMRepair\n`
- `0x18001c650`: `msdrm_DRMRepair`
- `0x18001cc21`: `[msdrm]:-DRMRepair HR=%x\n`

## pseudocode

```c
HRESULT __stdcall DRMRepair()
{
  int PrinicipalTypeAndID; // ebx
  CDRMLicense *v1; // rdi
  CDRMLicense *v2; // r14
  wchar_t *v3; // r15
  PWSTR v4; // rsi
  struct CDRMLicense **v5; // r12
  __int64 v6; // rdx
  int PersistedLicense; // eax
  int v8; // eax
  __int64 v9; // rdx
  int v10; // eax
  int v11; // eax
  DRMHSESSION v12; // r14d
  __int64 v13; // rdx
  unsigned __int64 v14; // r14
  _DWORD *v15; // rax
  _DWORD *v16; // r13
  struct CDRMLicense **v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rdi
  unsigned __int16 **v20; // r12
  struct CDRMLicense **v21; // r15
  int v22; // eax
  wchar_t *v23; // rbx
  int LicenseID; // eax
  HRESULT v25; // eax
  __int64 v26; // rcx
  unsigned int v27; // r15d
  __int64 v28; // rsi
  unsigned __int16 **v29; // r12
  struct CDRMLicense *v30; // rax
  __int64 v31; // rdi
  PWSTR v32; // rdi
  HRESULT v33; // eax
  __int64 v34; // rdi
  CDRMLicense *v35; // rcx
  PWSTR wszLicenseId; // [rsp+40h] [rbp-79h] BYREF
  struct CDRMLicense *v38; // [rsp+48h] [rbp-71h] BYREF
  unsigned __int16 *v39; // [rsp+50h] [rbp-69h] BYREF
  struct CDRMLicense **v40; // [rsp+58h] [rbp-61h] BYREF
  wchar_t *String2; // [rsp+60h] [rbp-59h] BYREF
  struct CDRMLicense *v42; // [rsp+68h] [rbp-51h] BYREF
  void *Block; // [rsp+70h] [rbp-49h] BYREF
  struct CDRMLicense *v44; // [rsp+78h] [rbp-41h] BYREF
  unsigned __int16 **v45; // [rsp+80h] [rbp-39h] BYREF
  unsigned __int16 **v46; // [rsp+88h] [rbp-31h] BYREF
  unsigned __int16 **v47; // [rsp+90h] [rbp-29h] BYREF
  unsigned __int16 **v48; // [rsp+98h] [rbp-21h] BYREF
  wchar_t *v49; // [rsp+A0h] [rbp-19h] BYREF
  wchar_t *String1; // [rsp+A8h] [rbp-11h] BYREF
  unsigned __int16 *v51; // [rsp+B0h] [rbp-9h] BYREF
  unsigned __int16 *v52; // [rsp+B8h] [rbp-1h] BYREF
  _QWORD v53[10]; // [rsp+C0h] [rbp+7h] BYREF
  DRMHSESSION hSession; // [rsp+120h] [rbp+67h] BYREF
  unsigned int v55; // [rsp+128h] [rbp+6Fh] BYREF
  unsigned int v56; // [rsp+130h] [rbp+77h] BYREF
  unsigned int v57; // [rsp+138h] [rbp+7Fh] BYREF

  PrinicipalTypeAndID = 0;
  _RTLTRACE("[msdrm]:+DRMRepair\n");
  v1 = 0;
  v55 = 0;
  v2 = 0;
  v42 = 0;
  v3 = 0;
  v38 = 0;
  v4 = 0;
  String2 = 0;
  wszLicenseId = 0;
  LODWORD(v40) = 0;
  v46 = 0;
  v5 = 0;
  v45 = 0;
  v56 = 0;
  v47 = 0;
  v57 = 0;
  v48 = 0;
  hSession = 0;
  v44 = 0;
  v52 = 0;
  v51 = 0;
  String1 = 0;
  v49 = 0;
  Block = 0;
  v39 = 0;
  v53[0] = 0;
  if ( (int)CDRMCLock::Lock((CDRMCLock *)v53, L"msdrm_DRMRepair") >= 0 )
  {
    if ( (int)IsActivated(0, 1u) < 0 )
      goto LABEL_3;
    PersistedLicense = GetPersistedLicenseEx(0, v6, 0, 0, 0, &v55, 0, &v46);
    PrinicipalTypeAndID = PersistedLicense;
    if ( PersistedLicense == -2147168454 )
      goto LABEL_3;
    if ( PersistedLicense < 0 )
      goto LABEL_68;
    v8 = ParseAndValidateCertificate(*v46, &v42, 1);
    PrinicipalTypeAndID = v8;
    if ( v8 == -2147168512 )
    {
      PrinicipalTypeAndID = DeActivateMachine();
LABEL_67:
      v1 = v42;
      goto LABEL_68;
    }
    if ( v8 < 0 )
      goto LABEL_67;
    v1 = v42;
    PrinicipalTypeAndID = GetPrinicipalTypeAndID(v42, L"issued-principal", &v52, &String1);
    if ( PrinicipalTypeAndID < 0 )
      goto LABEL_68;
    v10 = GetPersistedLicenseEx(6, v9, 0, 0, 0, &v40, 0, &v45);
    PrinicipalTypeAndID = v10;
    if ( v10 == -2147168454 )
      goto LABEL_3;
    if ( v10 < 0 )
      goto LABEL_68;
    v11 = ParseAndValidateCertificate(*v45, &v44, 0);
    PrinicipalTypeAndID = v11;
    if ( v11 == -2147168512 )
    {
LABEL_3:
      PrinicipalTypeAndID = DeActivateMachine();
      goto LABEL_68;
    }
    if ( v11 >= 0 )
    {
      PrinicipalTypeAndID = GetPrinicipalTypeAndID(v44, L"issued-principal", &v51, &v49);
      if ( PrinicipalTypeAndID >= 0 )
      {
        PrinicipalTypeAndID = DRMCreateClientSession(
                                CWebBrowser::RequestBorderSpace,
                                1u,
                                (PWSTR)L"WindowsAuthProvider",
                                0,
                                &hSession);
        if ( PrinicipalTypeAndID >= 0 )
        {
          v12 = hSession;
          PrinicipalTypeAndID = EnumAndDeleteLicense(hSession, 0x1008u);
          if ( PrinicipalTypeAndID < 0 )
            goto LABEL_20;
          PrinicipalTypeAndID = EnumAndDeleteLicense(v12, 0x1100u);
          if ( PrinicipalTypeAndID < 0 )
            goto LABEL_20;
          if ( (unsigned int)GetPersistedLicenseEx(1, v13, 0, 0, 0, &v56, 0, &v47) == -2147168454 )
          {
            DeleteAllLicense(3);
            PrinicipalTypeAndID = 0;
LABEL_20:
            v2 = v38;
            goto LABEL_68;
          }
          v14 = v56;
          if ( v56 > 0x8000000
            || (v15 = operator new(saturated_mul(v56, 4u)), (v16 = v15) == 0)
            || (memset_0(v15, 0, 4 * v14),
                v17 = (struct CDRMLicense **)operator new(saturated_mul(v14, 8u)),
                v40 = v17,
                (v5 = v17) == 0) )
          {
            PrinicipalTypeAndID = -2147024882;
            goto LABEL_20;
          }
          memset_0(v17, 0, 8 * v14);
          v19 = 0;
          if ( (_DWORD)v14 )
          {
            v20 = v47;
            do
            {
              v21 = &v40[v19];
              v22 = ParseAndValidateCertificate(v20[v19], v21, 0);
              if ( *v21 )
              {
                if ( v22 == -2147168512 )
                  goto LABEL_34;
                PrinicipalTypeAndID = GetPrinicipalTypeAndID(
                                        *v21,
                                        L"group-identity-principal",
                                        (unsigned __int16 **)&Block,
                                        &String2);
                if ( PrinicipalTypeAndID < 0 )
                  goto LABEL_60;
                v23 = String2;
                if ( _wcsicmp(String1, String2) && _wcsicmp(v49, v23) )
                {
LABEL_34:
                  v16[v19] = 1;
                  LicenseID = CDRMLicense::GetLicenseID(*v21, &v39, &wszLicenseId);
                  v4 = wszLicenseId;
                  PrinicipalTypeAndID = LicenseID;
                  if ( LicenseID < 0 )
                    goto LABEL_61;
                  v25 = DRMDeleteLicense(hSession, wszLicenseId);
                  PrinicipalTypeAndID = 0;
                  if ( v25 != -2147168454 )
                    PrinicipalTypeAndID = v25;
                  if ( PrinicipalTypeAndID < 0 )
                    goto LABEL_61;
                  v23 = String2;
                }
                else
                {
                  v4 = wszLicenseId;
                }
                operator delete(Block);
                Block = 0;
                operator delete(v23);
                String2 = 0;
                operator delete(v39);
                v39 = 0;
                operator delete(v4);
                v4 = 0;
                wszLicenseId = 0;
              }
              else
              {
                v4 = wszLicenseId;
                v16[v19] = 1;
              }
              v19 = (unsigned int)(v19 + 1);
            }
            while ( (unsigned int)v19 < (unsigned int)v14 );
          }
          v26 = 0;
          if ( (_DWORD)v14 )
          {
            while ( v16[v26] )
            {
              v26 = (unsigned int)(v26 + 1);
              if ( (unsigned int)v26 >= (unsigned int)v14 )
                goto LABEL_44;
            }
            PrinicipalTypeAndID = GetPersistedLicenseEx(3, v18, 0, 0, 0, &v57, 0, &v48);
            if ( PrinicipalTypeAndID != -2147168454 )
            {
              v27 = v57;
              v28 = 0;
              if ( v57 )
              {
                v29 = v48;
                do
                {
                  PrinicipalTypeAndID = ParseAndValidateCertificate(v29[v28], &v38, 0);
                  v30 = v38;
                  if ( v38 )
                  {
                    if ( PrinicipalTypeAndID != -2147168512 )
                    {
                      v31 = 0;
                      do
                      {
                        if ( !v16[v31] )
                        {
                          if ( (unsigned int)MatchIssuedPrinicipal(v30, v40[v31]) == 1 )
                          {
                            v32 = wszLicenseId;
                            goto LABEL_76;
                          }
                          v30 = v38;
                        }
                        v31 = (unsigned int)(v31 + 1);
                      }
                      while ( (unsigned int)v31 < (unsigned int)v14 );
                    }
                    PrinicipalTypeAndID = CDRMLicense::GetLicenseID(v30, &v39, &wszLicenseId);
                    if ( PrinicipalTypeAndID < 0 )
                      break;
                    v32 = wszLicenseId;
                    v33 = DRMDeleteLicense(hSession, wszLicenseId);
                    PrinicipalTypeAndID = 0;
                    if ( v33 != -2147168454 )
                      PrinicipalTypeAndID = v33;
                    if ( PrinicipalTypeAndID < 0 )
                      break;
LABEL_76:
                    operator delete(v39);
                    v39 = 0;
                    operator delete(v32);
                    wszLicenseId = 0;
                    CDRMLicense::Release(v38);
                    v38 = 0;
                  }
                  v28 = (unsigned int)(v28 + 1);
                }
                while ( (unsigned int)v28 < v27 );
              }
LABEL_60:
              v4 = wszLicenseId;
              goto LABEL_61;
            }
          }
          else
          {
LABEL_44:
            DeleteAllLicense(3);
          }
          PrinicipalTypeAndID = 0;
LABEL_61:
          v5 = v40;
          v34 = 0;
          if ( (_DWORD)v14 )
          {
            do
            {
              v35 = v5[v34];
              if ( v35 )
              {
                CDRMLicense::Release(v35);
                v5[v34] = 0;
              }
              v34 = (unsigned int)(v34 + 1);
            }
            while ( (unsigned int)v34 < (unsigned int)v14 );
            v4 = wszLicenseId;
          }
          v2 = v38;
          v3 = String2;
          goto LABEL_67;
        }
      }
    }
  }
LABEL_68:
  DRMCloseSession(hSession);
  if ( v44 )
    CDRMLicense::Release(v44);
  if ( v1 )
    CDRMLicense::Release(v1);
  if ( v2 )
    CDRMLicense::Release(v2);
  operator delete(v5);
  CDRMCBase::DeleteArrayofString(&v45, &v55);
  CDRMCBase::DeleteArrayofString(&v46, &v55);
  CDRMCBase::DeleteArrayofString(&v47, &v56);
  CDRMCBase::DeleteArrayofString(&v48, &v57);
  operator delete(v4);
  operator delete(v51);
  operator delete(v49);
  operator delete(v52);
  operator delete(String1);
  operator delete(Block);
  operator delete(v3);
  operator delete(v39);
  operator delete(0);
  _RTLTRACE("[msdrm]:-DRMRepair HR=%x\n", PrinicipalTypeAndID);
  CDRMCLock::~CDRMCLock((CDRMCLock *)v53);
  return PrinicipalTypeAndID;
}

```

## disassembly

```asm
0x18001c610  push    rbp
0x18001c612  push    rbx
0x18001c613  push    rsi
0x18001c614  push    rdi
0x18001c615  push    r12
0x18001c617  push    r13
0x18001c619  push    r14
0x18001c61b  push    r15
0x18001c61d  lea     rbp, [rsp-1Fh]
0x18001c622  sub     rsp, 0D8h
0x18001c629  lea     rcx, aMsdrmDrmrepair; "[msdrm]:+DRMRepair\n"
0x18001c630  xor     ebx, ebx
0x18001c632  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x18001c637  xor     edi, edi
0x18001c639  mov     [rbp+57h+arg_8], ebx
0x18001c63c  xor     r14d, r14d
0x18001c63f  mov     [rbp+57h+var_A8], rdi
0x18001c643  xor     r15d, r15d
0x18001c646  mov     [rbp+57h+var_C8], r14
0x18001c64a  xor     esi, esi
0x18001c64c  mov     [rbp+57h+String2], r15
0x18001c650  lea     rdx, aMsdrmDrmrepair_0; "msdrm_DRMRepair"
0x18001c657  mov     [rbp+57h+wszLicenseId], rsi
0x18001c65b  lea     rcx, [rbp+57h+var_50]; this
0x18001c65f  mov     dword ptr [rbp+57h+var_B8], ebx
0x18001c662  mov     [rbp+57h+var_88], rbx
0x18001c666  xor     r12d, r12d
0x18001c669  mov     [rbp+57h+var_90], rbx
0x18001c66d  mov     [rbp+57h+arg_10], ebx
0x18001c670  mov     [rbp+57h+var_80], rbx
0x18001c674  mov     [rbp+57h+arg_18], ebx
0x18001c677  mov     [rbp+57h+var_78], rbx
0x18001c67b  mov     [rbp+57h+hSession], ebx
0x18001c67e  mov     [rbp+57h+var_98], rbx
0x18001c682  mov     [rbp+57h+var_58], rbx
0x18001c686  mov     [rbp+57h+var_60], rbx
0x18001c68a  mov     [rbp+57h+String1], rbx
0x18001c68e  mov     [rbp+57h+var_70], rbx
0x18001c692  mov     [rbp+57h+Block], rbx
0x18001c696  mov     [rbp+57h+var_C0], rbx
0x18001c69a  mov     [rbp+57h+var_50], rbx
0x18001c69e  call    ?Lock@CDRMCLock@@QEAAJPEAG@Z; CDRMCLock::Lock(ushort *)
0x18001c6a3  test    eax, eax
0x18001c6a5  js      loc_18001CB63
0x18001c6ab  lea     r13d, [rbx+1]
0x18001c6af  xor     ecx, ecx; unsigned __int16 *
0x18001c6b1  mov     edx, r13d; unsigned int
0x18001c6b4  call    ?IsActivated@@YAJPEAGI@Z; IsActivated(ushort *,uint)
0x18001c6b9  test    eax, eax
0x18001c6bb  jns     short loc_18001C6C9
0x18001c6bd  call    ?DeActivateMachine@@YAJXZ; DeActivateMachine(void)
0x18001c6c2  mov     ebx, eax
0x18001c6c4  jmp     loc_18001CB63
0x18001c6c9  lea     rax, [rbp+57h+var_88]
0x18001c6cd  xor     r9d, r9d
0x18001c6d0  mov     [rsp+110h+var_D8], rax
0x18001c6d5  xor     r8d, r8d
0x18001c6d8  lea     rax, [rbp+57h+arg_8]
0x18001c6dc  mov     [rsp+110h+var_E0], rbx
0x18001c6e1  mov     [rsp+110h+var_E8], rax
0x18001c6e6  xor     ecx, ecx
0x18001c6e8  mov     dword ptr [rsp+110h+phClient], ebx
0x18001c6ec  call    ?GetPersistedLicenseEx@@YAJW4DRM_LICENSE_TYPE@@HIPEAPEAGIPEAIPEAPEAPEAG3@Z; GetPersistedLicenseEx(DRM_LICENSE_TYPE,int,uint,ushort * *,uint,uint *,ushort * * *,ushort * * *)
0x18001c6f1  mov     ebx, eax
0x18001c6f3  cmp     eax, 8004CF3Ah
0x18001c6f8  jz      short loc_18001C6BD
0x18001c6fa  test    eax, eax
0x18001c6fc  js      loc_18001CB63
0x18001c702  mov     rcx, [rbp+57h+var_88]
0x18001c706  lea     rdx, [rbp+57h+var_A8]; struct CDRMLicense **
0x18001c70a  mov     r8b, r13b; bool
0x18001c70d  mov     rcx, [rcx]; unsigned __int16 *
0x18001c710  call    ?ParseAndValidateCertificate@@YAJPEAGPEAPEAVCDRMLicense@@_N@Z; ParseAndValidateCertificate(ushort *,CDRMLicense * *,bool)
0x18001c715  mov     ebx, eax
0x18001c717  cmp     eax, 8004CF00h
0x18001c71c  jnz     short loc_18001C72A
0x18001c71e  call    ?DeActivateMachine@@YAJXZ; DeActivateMachine(void)
0x18001c723  mov     ebx, eax
0x18001c725  jmp     loc_18001CB5F
0x18001c72a  test    eax, eax
0x18001c72c  js      loc_18001CB5F
0x18001c732  mov     rdi, [rbp+57h+var_A8]
0x18001c736  lea     r9, [rbp+57h+String1]; unsigned __int16 **
0x18001c73a  mov     rcx, rdi; struct CDRMLicense *
0x18001c73d  lea     r8, [rbp+57h+var_58]; unsigned __int16 **
0x18001c741  lea     rdx, aIssuedPrincipa; "issued-principal"
0x18001c748  call    ?GetPrinicipalTypeAndID@@YAJPEAVCDRMLicense@@PEAGPEAPEAG2@Z; GetPrinicipalTypeAndID(CDRMLicense *,ushort *,ushort * *,ushort * *)
0x18001c74d  mov     ebx, eax
0x18001c74f  test    eax, eax
0x18001c751  js      loc_18001CB63
0x18001c757  lea     rax, [rbp+57h+var_90]
0x18001c75b  xor     r9d, r9d
0x18001c75e  mov     [rsp+110h+var_D8], rax
0x18001c763  xor     r8d, r8d
0x18001c766  lea     rax, [rbp+57h+var_B8]
0x18001c76a  mov     [rsp+110h+var_E0], rsi
0x18001c76f  mov     [rsp+110h+var_E8], rax
0x18001c774  lea     ecx, [r9+6]
0x18001c778  mov     dword ptr [rsp+110h+phClient], esi
0x18001c77c  call    ?GetPersistedLicenseEx@@YAJW4DRM_LICENSE_TYPE@@HIPEAPEAGIPEAIPEAPEAPEAG3@Z; GetPersistedLicenseEx(DRM_LICENSE_TYPE,int,uint,ushort * *,uint,uint *,ushort * * *,ushort * * *)
0x18001c781  mov     ebx, eax
0x18001c783  cmp     eax, 8004CF3Ah
0x18001c788  jz      loc_18001C6BD
0x18001c78e  test    eax, eax
0x18001c790  js      loc_18001CB63
0x18001c796  mov     rcx, [rbp+57h+var_90]
0x18001c79a  lea     rdx, [rbp+57h+var_98]; struct CDRMLicense **
0x18001c79e  xor     r8d, r8d; bool
0x18001c7a1  mov     rcx, [rcx]; unsigned __int16 *
0x18001c7a4  call    ?ParseAndValidateCertificate@@YAJPEAGPEAPEAVCDRMLicense@@_N@Z; ParseAndValidateCertificate(ushort *,CDRMLicense * *,bool)
0x18001c7a9  mov     ebx, eax
0x18001c7ab  cmp     eax, 8004CF00h
0x18001c7b0  jz      loc_18001C6BD
0x18001c7b6  test    eax, eax
0x18001c7b8  js      loc_18001CB63
0x18001c7be  mov     rcx, [rbp+57h+var_98]; struct CDRMLicense *
0x18001c7c2  lea     r9, [rbp+57h+var_70]; unsigned __int16 **
0x18001c7c6  lea     r8, [rbp+57h+var_60]; unsigned __int16 **
0x18001c7ca  lea     rdx, aIssuedPrincipa; "issued-principal"
0x18001c7d1  call    ?GetPrinicipalTypeAndID@@YAJPEAVCDRMLicense@@PEAGPEAPEAG2@Z; GetPrinicipalTypeAndID(CDRMLicense *,ushort *,ushort * *,ushort * *)
0x18001c7d6  mov     ebx, eax
0x18001c7d8  test    eax, eax
0x18001c7da  js      loc_18001CB63
0x18001c7e0  lea     rax, [rbp+57h+hSession]
0x18001c7e4  xor     r9d, r9d; wszGroupID
0x18001c7e7  lea     r8, aWindowsauthpro; "WindowsAuthProvider"
0x18001c7ee  mov     [rsp+110h+phClient], rax; phClient
0x18001c7f3  mov     edx, r13d; uCallbackVersion
0x18001c7f6  lea     rcx, ?RequestBorderSpace@CWebBrowser@@UEAAJPEBUtagRECT@@@Z; pfnCallback
0x18001c7fd  call    DRMCreateClientSession
0x18001c802  mov     ebx, eax
0x18001c804  test    eax, eax
0x18001c806  js      loc_18001CB63
0x18001c80c  mov     r14d, [rbp+57h+hSession]
0x18001c810  mov     edx, 1008h; uFlags
0x18001c815  mov     ecx, r14d; hSession
0x18001c818  call    ?EnumAndDeleteLicense@@YAJKI@Z; EnumAndDeleteLicense(ulong,uint)
0x18001c81d  mov     ebx, eax
0x18001c81f  test    eax, eax
0x18001c821  js      short loc_18001C872
0x18001c823  mov     edx, 1100h; uFlags
0x18001c828  mov     ecx, r14d; hSession
0x18001c82b  call    ?EnumAndDeleteLicense@@YAJKI@Z; EnumAndDeleteLicense(ulong,uint)
0x18001c830  mov     ebx, eax
0x18001c832  test    eax, eax
0x18001c834  js      short loc_18001C872
0x18001c836  lea     rax, [rbp+57h+var_80]
0x18001c83a  xor     r9d, r9d
0x18001c83d  mov     [rsp+110h+var_D8], rax
0x18001c842  xor     r8d, r8d
0x18001c845  lea     rax, [rbp+57h+arg_10]
0x18001c849  mov     [rsp+110h+var_E0], rsi
0x18001c84e  mov     [rsp+110h+var_E8], rax
0x18001c853  mov     ecx, r13d
0x18001c856  mov     dword ptr [rsp+110h+phClient], esi
0x18001c85a  call    ?GetPersistedLicenseEx@@YAJW4DRM_LICENSE_TYPE@@HIPEAPEAGIPEAIPEAPEAPEAG3@Z; GetPersistedLicenseEx(DRM_LICENSE_TYPE,int,uint,ushort * *,uint,uint *,ushort * * *,ushort * * *)
0x18001c85f  cmp     eax, 8004CF3Ah
0x18001c864  jnz     short loc_18001C87B
0x18001c866  mov     ecx, 3
0x18001c86b  call    ?DeleteAllLicense@@YAJW4DRM_LICENSE_TYPE@@@Z; DeleteAllLicense(DRM_LICENSE_TYPE)
0x18001c870  xor     ebx, ebx
0x18001c872  mov     r14, [rbp+57h+var_C8]
0x18001c876  jmp     loc_18001CB63
0x18001c87b  mov     r14d, [rbp+57h+arg_10]
0x18001c87f  cmp     r14d, 8000000h
0x18001c886  jbe     short loc_18001C88F
0x18001c888  mov     ebx, 8007000Eh
0x18001c88d  jmp     short loc_18001C872
0x18001c88f  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001c896  mov     eax, 4
0x18001c89b  mul     r14
0x18001c89e  mov     rbx, r14
0x18001c8a1  cmovb   rax, rcx
0x18001c8a5  mov     rcx, rax; Size
0x18001c8a8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001c8ad  mov     r13, rax
0x18001c8b0  test    rax, rax
0x18001c8b3  jz      short loc_18001C888
0x18001c8b5  lea     r8, ds:0[r14*4]; Size
0x18001c8bd  xor     edx, edx; Val
0x18001c8bf  mov     rcx, rax; void *
0x18001c8c2  call    memset_0
0x18001c8c7  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001c8ce  mov     eax, 8
0x18001c8d3  mul     rbx
0x18001c8d6  cmovb   rax, rcx
0x18001c8da  mov     rcx, rax; Size
0x18001c8dd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001c8e2  mov     [rbp+57h+var_B8], rax
0x18001c8e6  mov     r12, rax
0x18001c8e9  test    rax, rax
0x18001c8ec  jz      short loc_18001C888
0x18001c8ee  lea     r8, ds:0[r14*8]; Size
0x18001c8f6  xor     edx, edx; Val
0x18001c8f8  mov     rcx, rax; void *
0x18001c8fb  call    memset_0
0x18001c900  xor     edi, edi
0x18001c902  test    r14d, r14d
0x18001c905  jz      loc_18001CA24
0x18001c90b  mov     r12, [rbp+57h+var_80]
0x18001c90f  mov     rax, [rbp+57h+var_B8]
0x18001c913  xor     r8d, r8d; bool
0x18001c916  mov     rcx, [r12+rdi*8]; unsigned __int16 *
0x18001c91a  lea     r15, [rax+rdi*8]
0x18001c91e  mov     rdx, r15; struct CDRMLicense **
0x18001c921  call    ?ParseAndValidateCertificate@@YAJPEAGPEAPEAVCDRMLicense@@_N@Z; ParseAndValidateCertificate(ushort *,CDRMLicense * *,bool)
0x18001c926  mov     rcx, [r15]; struct CDRMLicense *
0x18001c929  test    rcx, rcx
0x18001c92c  jnz     short loc_18001C940
0x18001c92e  mov     rsi, [rbp+57h+wszLicenseId]
0x18001c932  mov     dword ptr [r13+rdi*4+0], 1
0x18001c93b  jmp     loc_18001CA19
0x18001c940  cmp     eax, 8004CF00h
0x18001c945  jz      short loc_18001C991
0x18001c947  lea     r9, [rbp+57h+String2]; unsigned __int16 **
0x18001c94b  lea     r8, [rbp+57h+Block]; unsigned __int16 **
0x18001c94f  lea     rdx, aGroupIdentityP; "group-identity-principal"
0x18001c956  call    ?GetPrinicipalTypeAndID@@YAJPEAVCDRMLicense@@PEAGPEAPEAG2@Z; GetPrinicipalTypeAndID(CDRMLicense *,ushort *,ushort * *,ushort * *)
0x18001c95b  mov     ebx, eax
0x18001c95d  test    eax, eax
0x18001c95f  js      loc_18001CB27
0x18001c965  mov     rbx, [rbp+57h+String2]
0x18001c969  mov     rcx, [rbp+57h+String1]; String1
0x18001c96d  mov     rdx, rbx; String2
0x18001c970  call    cs:__imp__wcsicmp
0x18001c976  test    eax, eax
0x18001c978  jz      short loc_18001C98B
0x18001c97a  mov     rcx, [rbp+57h+var_70]; String1
0x18001c97e  mov     rdx, rbx; String2
0x18001c981  call    cs:__imp__wcsicmp
0x18001c987  test    eax, eax
0x18001c989  jnz     short loc_18001C991
0x18001c98b  mov     rsi, [rbp+57h+wszLicenseId]
0x18001c98f  jmp     short loc_18001C9D9
0x18001c991  mov     dword ptr [r13+rdi*4+0], 1
0x18001c99a  lea     r8, [rbp+57h+wszLicenseId]; unsigned __int16 **
0x18001c99e  mov     rcx, [r15]; this
0x18001c9a1  lea     rdx, [rbp+57h+var_C0]; unsigned __int16 **
0x18001c9a5  call    ?GetLicenseID@CDRMLicense@@QEAAJPEAPEAG0@Z; CDRMLicense::GetLicenseID(ushort * *,ushort * *)
0x18001c9aa  mov     rsi, [rbp+57h+wszLicenseId]
0x18001c9ae  mov     ebx, eax
0x18001c9b0  test    eax, eax
0x18001c9b2  js      loc_18001CB2B
0x18001c9b8  mov     ecx, [rbp+57h+hSession]; hSession
0x18001c9bb  mov     rdx, rsi; wszLicenseId
0x18001c9be  call    DRMDeleteLicense
0x18001c9c3  xor     ebx, ebx
0x18001c9c5  cmp     eax, 8004CF3Ah
0x18001c9ca  cmovnz  ebx, eax
0x18001c9cd  test    ebx, ebx
0x18001c9cf  js      loc_18001CB2B
0x18001c9d5  mov     rbx, [rbp+57h+String2]
0x18001c9d9  mov     rcx, [rbp+57h+Block]; Block
0x18001c9dd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001c9e2  mov     rcx, rbx; Block
0x18001c9e5  mov     [rbp+57h+Block], 0
0x18001c9ed  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001c9f2  mov     rcx, [rbp+57h+var_C0]; Block
0x18001c9f6  mov     [rbp+57h+String2], 0
0x18001c9fe  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001ca03  mov     rcx, rsi; Block
0x18001ca06  mov     [rbp+57h+var_C0], 0
0x18001ca0e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001ca13  xor     esi, esi
0x18001ca15  mov     [rbp+57h+wszLicenseId], rsi
0x18001ca19  inc     edi
0x18001ca1b  cmp     edi, r14d
0x18001ca1e  jb      loc_18001C90F
0x18001ca24  xor     ecx, ecx
0x18001ca26  test    r14d, r14d
0x18001ca29  jz      short loc_18001CA3A
0x18001ca2b  cmp     dword ptr [r13+rcx*4+0], 0
0x18001ca31  jz      short loc_18001CA46
0x18001ca33  inc     ecx
0x18001ca35  cmp     ecx, r14d
0x18001ca38  jb      short loc_18001CA2B
0x18001ca3a  mov     ecx, 3
0x18001ca3f  call    ?DeleteAllLicense@@YAJW4DRM_LICENSE_TYPE@@@Z; DeleteAllLicense(DRM_LICENSE_TYPE)
0x18001ca44  jmp     short loc_18001CA81
0x18001ca46  lea     rax, [rbp+57h+var_78]
0x18001ca4a  xor     r9d, r9d
0x18001ca4d  mov     [rsp+110h+var_D8], rax
0x18001ca52  xor     r8d, r8d
0x18001ca55  lea     rax, [rbp+57h+arg_18]
0x18001ca59  mov     [rsp+110h+var_E0], 0
0x18001ca62  mov     [rsp+110h+var_E8], rax
0x18001ca67  lea     ecx, [r9+3]
0x18001ca6b  mov     dword ptr [rsp+110h+phClient], 0
0x18001ca73  call    ?GetPersistedLicenseEx@@YAJW4DRM_LICENSE_TYPE@@HIPEAPEAGIPEAIPEAPEAPEAG3@Z; GetPersistedLicenseEx(DRM_LICENSE_TYPE,int,uint,ushort * *,uint,uint *,ushort * * *,ushort * * *)
0x18001ca78  mov     ebx, eax
0x18001ca7a  cmp     eax, 8004CF3Ah
0x18001ca7f  jnz     short loc_18001CA88
0x18001ca81  xor     ebx, ebx
0x18001ca83  jmp     loc_18001CB2B
0x18001ca88  mov     r15d, [rbp+57h+arg_18]
0x18001ca8c  xor     esi, esi
0x18001ca8e  test    r15d, r15d
0x18001ca91  jz      loc_18001CB27
0x18001ca97  mov     r12, [rbp+57h+var_78]
0x18001ca9b  mov     rcx, [r12+rsi*8]; unsigned __int16 *
  ... truncated ...
```
