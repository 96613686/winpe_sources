# Installersp_FindInstallerType(PCA_INSTALLER_TYPE *,_PCA_CHAIN_DATA const *,void *,ushort const *)

- ea: `0x180004634`
- end: `0x180004bc6`
- name: `?Installersp_FindInstallerType@@YAKPEAW4PCA_INSTALLER_TYPE@@PEBU_PCA_CHAIN_DATA@@PEAXPEBG@Z`
- size: `1426`
- prototype: `unsigned int(enum PCA_INSTALLER_TYPE *, const struct _PCA_CHAIN_DATA *, void *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, loader_planting, installer_update`

## callers

- `0x180003af4`

## callees

- `0x180004634`
- `0x180004bcc`
- `0x180004ce0`
- `0x180004de8`
- `0x180005600`
- `0x180012920`
- `0x1800182e0`
- `0x18001859c`
- `0x1800195c8`
- `0x180023e00`
- `0x1800f1f10`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800049b6`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800049d9`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800049b6`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800049d9`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180004712`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180004848`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180004a64`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180004712`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180004848`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180004a64`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800046a3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800046a3`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x18000473c`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x180004830`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x180004a8e`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x18000473c`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x180004830`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x180004a8e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800049ca`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800049ca`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180004721`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180004827`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180004a73`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180004721`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180004827`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180004a73`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x1800046c9`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x1800046c9`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000468b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000468b`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x1800046fa`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x18000480f`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x1800046fa`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x18000480f`

## string_xrefs

- `0x18000479e`: `Installersp_FindInstallerType`
- `0x180004891`: `Installersp_FindInstallerType`
- `0x180004907`: `Installersp_FindInstallerType`
- `0x18000496c`: `Installersp_FindInstallerType`
- `0x180004a04`: `Installersp_FindInstallerType`
- `0x180004a40`: `Installersp_FindInstallerType`
- `0x180004afc`: `Installersp_FindInstallerType`
- `0x180004b7f`: `Installersp_FindInstallerType`
- `0x180004884`: `Installer icon byte hash: %llu`
- `0x1800048fa`: `Installer: Unknown/Other - %ws`
- `0x180004791`: `Manifest: %s`
- `0x18000495f`: `Installer: %s - %ws`
- `0x180004a33`: `IsInstallShield failed [%d]`
- `0x1800049f7`: `Installer: %ws - %ws`
- `0x180004b72`: `Installer: %ws - %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Installersp_FindInstallerType(
        enum PCA_INSTALLER_TYPE *a1,
        const struct _PCA_CHAIN_DATA *a2,
        void *a3,
        const unsigned __int16 *a4)
{
  unsigned int IsInstallShield; // edi
  HMODULE Library; // rsi
  int v7; // r12d
  const unsigned __int16 *v8; // r8
  unsigned __int64 i; // rdi
  HRSRC v10; // rax
  HRSRC v11; // r14
  unsigned __int64 j; // r14
  HRSRC ResourceW; // rax
  HRSRC v14; // rdi
  __int64 v15; // r15
  HGLOBAL Resource; // rax
  _BYTE *v17; // rax
  void **v18; // rax
  unsigned __int64 k; // rdi
  char *v20; // r15
  __int64 v21; // rax
  __int64 v22; // r8
  unsigned __int64 m; // r14
  HRSRC v24; // rax
  HRSRC v25; // rdi
  HGLOBAL v26; // rax
  unsigned __int8 *v27; // r15
  DWORD v28; // eax
  __int64 v29; // rdi
  unsigned __int64 n; // rcx
  __int64 ii; // rax
  DWORD v33; // r15d
  HGLOBAL v34; // rax
  const unsigned __int16 *v35; // rax
  void **v36; // rax
  __int64 v37; // rdx
  unsigned __int64 jj; // r14
  wchar_t *v39; // r15
  __int64 v40; // rax
  __int64 v41; // rdx
  void **v42; // [rsp+20h] [rbp-60h]
  int v43; // [rsp+20h] [rbp-60h]
  void **v44; // [rsp+28h] [rbp-58h]
  int v45; // [rsp+38h] [rbp-48h] BYREF
  void *v46; // [rsp+40h] [rbp-40h]
  enum PCA_INSTALLER_TYPE *v47; // [rsp+48h] [rbp-38h]
  void *v48[2]; // [rsp+50h] [rbp-30h] BYREF
  __int64 v49; // [rsp+60h] [rbp-20h]
  unsigned __int64 v50; // [rsp+68h] [rbp-18h]

  v46 = a3;
  v47 = a1;
  v45 = 0;
  IsInstallShield = 0;
  if ( *((_DWORD *)a2 + 135) == 2 )
  {
    *(_DWORD *)a1 = 1;
  }
  else
  {
    Library = 0;
    v7 = 0;
    if ( GetFileAttributesW(a4) == -1 )
    {
LABEL_35:
      AslLogCallPrintf(
        3,
        (unsigned int)"Installersp_FindInstallerType",
        702,
        (unsigned int)"Installer: Unknown/Other - %ws");
    }
    else
    {
      Library = LoadLibraryExW(a4, 0, 0x22u);
      for ( i = 1; ; ++i )
      {
        if ( i > 0x14 )
        {
          for ( j = 1; j <= 2; ++j )
          {
            ResourceW = FindResourceW(Library, (LPCWSTR)(unsigned __int16)j, (LPCWSTR)0x18);
            v14 = ResourceW;
            if ( ResourceW )
            {
              v15 = SizeofResource(Library, ResourceW);
              Resource = LoadResource(Library, v14);
              if ( Resource )
              {
                if ( (_DWORD)v15 )
                {
                  v17 = LockResource(Resource);
                  if ( v17 )
                  {
                    if ( *v17 )
                    {
                      v8 = (const unsigned __int16 *)&v17[v15];
                      if ( v17 != &v17[v15] )
                      {
                        v50 = 15;
                        v49 = 0;
                        LOBYTE(v48[0]) = 0;
                        std::string::_Construct<char *>(v48, v17);
                        v18 = v48;
                        if ( v50 >= 0x10 )
                          v18 = (void **)v48[0];
                        v42 = v18;
                        AslLogCallPrintf(
                          3,
                          (unsigned int)"Installersp_FindInstallerType",
                          629,
                          (unsigned int)"Manifest: %s");
                        for ( k = 0; k < 0xF; ++k )
                        {
                          v20 = (&off_1800FB900)[3 * k];
                          v21 = std::char_traits<char>::length(v20);
                          if ( std::string::find(v48, v20, v22, v21, v42, v44) != -1 )
                          {
                            AslLogCallPrintf(
                              3,
                              (unsigned int)"Installersp_FindInstallerType",
                              634,
                              (unsigned int)"Installer: %s - %ws");
                            v7 = dword_1800FB910[6 * k];
                            IsInstallShield = 0;
                            if ( v50 >= 0x10 )
                              operator delete(v48[0]);
                            goto LABEL_41;
                          }
                        }
                        if ( v50 >= 0x10 )
                          operator delete(v48[0]);
                      }
                    }
                  }
                }
              }
            }
          }
          for ( m = 1; m <= 0xA; ++m )
          {
            v24 = FindResourceW(Library, (LPCWSTR)(unsigned __int16)m, (LPCWSTR)3);
            v25 = v24;
            if ( v24 )
            {
              v26 = LoadResource(Library, v24);
              v27 = (unsigned __int8 *)LockResource(v26);
              if ( v27 )
              {
                v28 = SizeofResource(Library, v25);
                if ( v28 )
                {
                  v29 = 0xCBF29CE484222325uLL;
                  for ( n = 0; n < v28; v29 = 0x100000001B3LL * (v27[n++] ^ (unsigned __int64)v29) )
                    ;
                  AslLogCallPrintf(
                    3,
                    (unsigned int)"Installersp_FindInstallerType",
                    668,
                    (unsigned int)"Installer icon byte hash: %llu");
                  for ( ii = 0; !ii; ++ii )
                  {
                    if ( v29 == 0xA3DF46F8D3F6E2FFuLL )
                    {
                      AslLogCallPrintf(
                        3,
                        (unsigned int)"Installersp_FindInstallerType",
                        672,
                        (unsigned int)"Installer: %ws - %ws");
                      v7 = 16;
                      IsInstallShield = 0;
                      goto LABEL_41;
                    }
                  }
                }
              }
            }
          }
          IsInstallShield = Installersp_IsInstallShield(&v45, v46, v8);
          if ( IsInstallShield )
          {
            AslLogCallPrintf(
              1,
              (unsigned int)"Installersp_FindInstallerType",
              689,
              (unsigned int)"IsInstallShield failed [%d]");
            goto LABEL_35;
          }
          if ( !v45 )
            goto LABEL_35;
          v7 = 2;
          IsInstallShield = 0;
          goto LABEL_36;
        }
        v10 = FindResourceExW(Library, (LPCWSTR)6, (LPCWSTR)(unsigned __int16)i, 0);
        v11 = v10;
        if ( v10 )
        {
          v33 = SizeofResource(Library, v10);
          v34 = LoadResource(Library, v11);
          if ( v34 )
          {
            if ( v33 )
            {
              v35 = (const unsigned __int16 *)LockResource(v34);
              if ( v35 )
              {
                if ( *v35 )
                {
                  v8 = &v35[(unsigned __int64)v33 >> 1];
                  if ( v35 != v8 )
                    break;
                }
              }
            }
          }
        }
LABEL_6:
        ;
      }
      v50 = 7;
      v49 = 0;
      LOWORD(v48[0]) = 0;
      std::wstring::_Construct<unsigned short *>(v48);
      v36 = v48;
      if ( v50 >= 8 )
        v36 = (void **)v48[0];
      v44 = v36;
      v43 = i;
      AslLogCallPrintf(
        3,
        (unsigned int)"Installersp_FindInstallerType",
        595,
        (unsigned int)"String Table Block %d: %ws");
      for ( jj = 0; ; ++jj )
      {
        if ( jj >= 0xF )
        {
          LOBYTE(v37) = 1;
          std::wstring::_Tidy(v48, v37, 0);
          goto LABEL_6;
        }
        v39 = (&off_1800FB908)[3 * jj];
        v40 = std::char_traits<unsigned short>::length(v39);
        if ( std::wstring::find(v48, v39, 0, v40, v43, v44) != -1 )
          break;
      }
      AslLogCallPrintf(3, (unsigned int)"Installersp_FindInstallerType", 601, (unsigned int)"Installer: %ws - %ws");
      v7 = dword_1800FB910[6 * jj];
      IsInstallShield = 0;
      LOBYTE(v41) = 1;
      std::wstring::_Tidy(v48, v41, 0);
LABEL_41:
      if ( !v7 )
        goto LABEL_35;
    }
LABEL_36:
    *(_DWORD *)v47 = v7;
    if ( Library )
      FreeLibrary(Library);
  }
  return IsInstallShield;
}

```

## disassembly

```asm
0x180004634  mov     [rsp-38h+arg_8], rbx
0x180004639  push    rbp
0x18000463a  push    rsi
0x18000463b  push    rdi
0x18000463c  push    r12
0x18000463e  push    r13
0x180004640  push    r14
0x180004642  push    r15
0x180004644  mov     rbp, rsp
0x180004647  sub     rsp, 80h
0x18000464e  mov     rax, cs:__security_cookie
0x180004655  xor     rax, rsp
0x180004658  mov     [rbp+var_10], rax
0x18000465c  mov     r13, r9
0x18000465f  mov     [rbp+var_50], r9
0x180004663  mov     [rbp+var_40], r8
0x180004667  mov     [rbp+var_38], rcx
0x18000466b  xor     r14d, r14d
0x18000466e  mov     [rbp+var_48], r14d
0x180004672  mov     edi, r14d
0x180004675  cmp     dword ptr [rdx+21Ch], 2
0x18000467c  jz      loc_180004A53
0x180004682  mov     esi, r14d
0x180004685  mov     r12d, r14d
0x180004688  mov     rcx, r9; lpFileName
0x18000468b  call    cs:__imp_GetFileAttributesW
0x180004691  cmp     eax, 0FFFFFFFFh
0x180004694  jz      loc_1800048F5
0x18000469a  xor     edx, edx; hFile
0x18000469c  lea     r8d, [r14+22h]; dwFlags
0x1800046a0  mov     rcx, r13; lpLibFileName
0x1800046a3  call    cs:__imp_LoadLibraryExW
0x1800046a9  mov     rsi, rax
0x1800046ac  lea     ebx, [r14+1]
0x1800046b0  mov     edi, ebx
0x1800046b2  xor     r13d, r13d
0x1800046b5  cmp     rdi, 14h
0x1800046b9  ja      short loc_1800046E0
0x1800046bb  xor     r9d, r9d; wLanguage
0x1800046be  movzx   r8d, di; lpName
0x1800046c2  lea     edx, [r9+6]; lpType
0x1800046c6  mov     rcx, rsi; hModule
0x1800046c9  call    cs:__imp_FindResourceExW
0x1800046cf  mov     r14, rax
0x1800046d2  test    rax, rax
0x1800046d5  jnz     loc_180004A5E
0x1800046db  add     rdi, rbx
0x1800046de  jmp     short loc_1800046B5
0x1800046e0  mov     r14, rbx
0x1800046e3  cmp     r14, 2
0x1800046e7  ja      loc_1800047F5
0x1800046ed  movzx   edx, r14w; lpName
0x1800046f1  mov     r8d, 18h; lpType
0x1800046f7  mov     rcx, rsi; hModule
0x1800046fa  call    cs:__imp_FindResourceW
0x180004700  mov     rdi, rax
0x180004703  test    rax, rax
0x180004706  jz      loc_1800049BF
0x18000470c  mov     rdx, rax; hResInfo
0x18000470f  mov     rcx, rsi; hModule
0x180004712  call    cs:__imp_SizeofResource
0x180004718  mov     r15d, eax
0x18000471b  mov     rdx, rdi; hResInfo
0x18000471e  mov     rcx, rsi; hModule
0x180004721  call    cs:__imp_LoadResource
0x180004727  test    rax, rax
0x18000472a  jz      loc_1800049BF
0x180004730  test    r15d, r15d
0x180004733  jz      loc_1800049BF
0x180004739  mov     rcx, rax; hResData
0x18000473c  call    cs:__imp_LockResource
0x180004742  mov     rdx, rax
0x180004745  test    rax, rax
0x180004748  jz      loc_1800049BF
0x18000474e  cmp     [rax], r13b
0x180004751  jz      loc_1800049BF
0x180004757  lea     r8, [rax+r15]
0x18000475b  cmp     rax, r8
0x18000475e  jz      loc_1800049BF
0x180004764  mov     [rbp+var_18], 0Fh
0x18000476c  mov     [rbp+var_20], r13
0x180004770  mov     byte ptr [rbp+var_30], r13b
0x180004774  lea     rcx, [rbp+var_30]
0x180004778  call    ??$_Construct@PEAD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXPEAD0Uforward_iterator_tag@1@@Z; std::string::_Construct<char *>(char *,char *,std::forward_iterator_tag)
0x18000477d  nop
0x18000477e  lea     rax, [rbp+var_30]
0x180004782  cmp     [rbp+var_18], 10h
0x180004787  cmovnb  rax, [rbp+var_30]
0x18000478c  mov     [rsp+80h+var_60], rax
0x180004791  lea     r9, aManifestS; "Manifest: %s"
0x180004798  mov     r8d, 275h
0x18000479e  lea     rdx, aInstallerspFin; "Installersp_FindInstallerType"
0x1800047a5  mov     ecx, 3
0x1800047aa  call    AslLogCallPrintf
0x1800047af  mov     rdi, r13
0x1800047b2  cmp     rdi, 0Fh
0x1800047b6  jnb     loc_1800049AB
0x1800047bc  lea     r13, [rdi+rdi*2]
0x1800047c0  lea     rax, __ImageBase
0x1800047c7  mov     r15, ds:rva off_1800FB900[rax+r13*8]; "InstallShield" ...
0x1800047cf  mov     rcx, r15
0x1800047d2  call    ?length@?$char_traits@D@std@@SA_KPEBD@Z; std::char_traits<char>::length(char const *)
0x1800047d7  mov     r9, rax
0x1800047da  mov     rdx, r15
0x1800047dd  lea     rcx, [rbp+var_30]
0x1800047e1  call    ?find@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA_KPEBD_K1@Z; std::string::find(char const *,unsigned __int64,unsigned __int64)
0x1800047e6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800047ea  jnz     loc_180004951
0x1800047f0  add     rdi, rbx
0x1800047f3  jmp     short loc_1800047B2
0x1800047f5  mov     r14, rbx
0x1800047f8  cmp     r14, 0Ah
0x1800047fc  ja      loc_1800048D0
0x180004802  movzx   edx, r14w; lpName
0x180004806  mov     r8d, 3; lpType
0x18000480c  mov     rcx, rsi; hModule
0x18000480f  call    cs:__imp_FindResourceW
0x180004815  mov     rdi, rax
0x180004818  test    rax, rax
0x18000481b  jz      loc_1800048C8
0x180004821  mov     rdx, rax; hResInfo
0x180004824  mov     rcx, rsi; hModule
0x180004827  call    cs:__imp_LoadResource
0x18000482d  mov     rcx, rax; hResData
0x180004830  call    cs:__imp_LockResource
0x180004836  mov     r15, rax
0x180004839  test    rax, rax
0x18000483c  jz      loc_1800048C8
0x180004842  mov     rdx, rdi; hResInfo
0x180004845  mov     rcx, rsi; hModule
0x180004848  call    cs:__imp_SizeofResource
0x18000484e  test    eax, eax
0x180004850  jz      short loc_1800048C8
0x180004852  mov     rdi, 0CBF29CE484222325h
0x18000485c  mov     edx, eax
0x18000485e  mov     rcx, r13
0x180004861  movzx   eax, byte ptr [r15+rcx]
0x180004866  xor     rdi, rax
0x180004869  mov     r8, 100000001B3h
0x180004873  imul    rdi, r8
0x180004877  add     rcx, rbx
0x18000487a  cmp     rcx, rdx
0x18000487d  jb      short loc_180004861
0x18000487f  mov     [rsp+80h+var_60], rdi
0x180004884  lea     r9, aInstallerIconB; "Installer icon byte hash: %llu"
0x18000488b  mov     r8d, 29Ch
0x180004891  lea     rdx, aInstallerspFin; "Installersp_FindInstallerType"
0x180004898  mov     ecx, 3
0x18000489d  call    AslLogCallPrintf
0x1800048a2  mov     rax, r13
0x1800048a5  lea     rcx, __ImageBase
0x1800048ac  cmp     rax, rbx
0x1800048af  jnb     short loc_1800048C8
0x1800048b1  lea     r15, [rax+rax*2]
0x1800048b5  cmp     rdi, ds:rva qword_1800FB8E0[rcx+r15*8]
0x1800048bd  jz      loc_1800049E1
0x1800048c3  add     rax, rbx
0x1800048c6  jmp     short loc_1800048AC
0x1800048c8  add     r14, rbx
0x1800048cb  jmp     loc_1800047F8
0x1800048d0  mov     rdx, [rbp+var_40]; void *
0x1800048d4  lea     rcx, [rbp+var_48]; int *
0x1800048d8  call    ?Installersp_IsInstallShield@@YAKPEAHPEAXPEBG@Z; Installersp_IsInstallShield(int *,void *,ushort const *)
0x1800048dd  mov     edi, eax
0x1800048df  test    eax, eax
0x1800048e1  jnz     loc_180004A2F
0x1800048e7  cmp     [rbp+var_48], r13d
0x1800048eb  jnz     loc_180004BB8
0x1800048f1  mov     r13, [rbp+var_50]
0x1800048f5  mov     [rsp+80h+var_60], r13
0x1800048fa  lea     r9, aInstallerUnkno; "Installer: Unknown/Other - %ws"
0x180004901  mov     r8d, 2BEh
0x180004907  lea     rdx, aInstallerspFin; "Installersp_FindInstallerType"
0x18000490e  mov     ecx, 3
0x180004913  call    AslLogCallPrintf
0x180004918  mov     rax, [rbp+var_38]
0x18000491c  mov     [rax], r12d
0x18000491f  test    rsi, rsi
0x180004922  jnz     loc_1800049C7
0x180004928  mov     eax, edi
0x18000492a  mov     rcx, [rbp+var_10]
0x18000492e  xor     rcx, rsp; StackCookie
0x180004931  call    __security_check_cookie
0x180004936  mov     rbx, [rsp+80h+arg_8]
0x18000493e  add     rsp, 80h
0x180004945  pop     r15
0x180004947  pop     r14
0x180004949  pop     r13
0x18000494b  pop     r12
0x18000494d  pop     rdi
0x18000494e  pop     rsi
0x18000494f  pop     rbp
0x180004950  retn
0x180004951  mov     rax, [rbp+var_50]
0x180004955  mov     [rsp+80h+var_58], rax
0x18000495a  mov     [rsp+80h+var_60], r15
0x18000495f  lea     r9, aInstallerSWs; "Installer: %s - %ws"
0x180004966  mov     r8d, 27Ah
0x18000496c  lea     rdx, aInstallerspFin; "Installersp_FindInstallerType"
0x180004973  mov     ecx, 3
0x180004978  call    AslLogCallPrintf
0x18000497d  lea     rax, __ImageBase
0x180004984  mov     r12d, ds:rva dword_1800FB910[rax+r13*8]
0x18000498c  xor     r14d, r14d
0x18000498f  mov     edi, r14d
0x180004992  cmp     [rbp+var_18], 10h
0x180004997  jnb     short loc_1800049D5
0x180004999  mov     r13, [rbp+var_50]
0x18000499d  test    r12d, r12d
0x1800049a0  jz      loc_1800048F5
0x1800049a6  jmp     loc_180004918
0x1800049ab  cmp     [rbp+var_18], 10h
0x1800049b0  jb      short loc_1800049BC
0x1800049b2  mov     rcx, [rbp+var_30]
0x1800049b6  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800049bc  xor     r13d, r13d
0x1800049bf  add     r14, rbx
0x1800049c2  jmp     loc_1800046E3
0x1800049c7  mov     rcx, rsi; hLibModule
0x1800049ca  call    cs:__imp_FreeLibrary
0x1800049d0  jmp     loc_180004928
0x1800049d5  mov     rcx, [rbp+var_30]
0x1800049d9  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800049df  jmp     short loc_180004999
0x1800049e1  mov     r13, [rbp+var_50]
0x1800049e5  mov     [rsp+80h+var_58], r13
0x1800049ea  mov     rax, ds:rva off_1800FB8E8[rcx+r15*8]; "Wise" ...
0x1800049f2  mov     [rsp+80h+var_60], rax
0x1800049f7  lea     r9, aInstallerWsWs; "Installer: %ws - %ws"
0x1800049fe  mov     r8d, 2A0h
0x180004a04  lea     rdx, aInstallerspFin; "Installersp_FindInstallerType"
0x180004a0b  mov     ecx, 3
0x180004a10  call    AslLogCallPrintf
0x180004a15  lea     rax, __ImageBase
0x180004a1c  mov     r12d, ds:rva dword_1800FB8F0[rax+r15*8]
0x180004a24  xor     r14d, r14d
0x180004a27  mov     edi, r14d
0x180004a2a  jmp     loc_18000499D
0x180004a2f  mov     dword ptr [rsp+80h+var_60], eax
0x180004a33  lea     r9, aIsinstallshiel; "IsInstallShield failed [%d]"
0x180004a3a  mov     r8d, 2B1h
0x180004a40  lea     rdx, aInstallerspFin; "Installersp_FindInstallerType"
0x180004a47  mov     ecx, ebx
0x180004a49  call    AslLogCallPrintf
0x180004a4e  jmp     loc_1800048F1
0x180004a53  mov     dword ptr [rcx], 1
0x180004a59  jmp     loc_180004928
0x180004a5e  mov     rdx, r14; hResInfo
0x180004a61  mov     rcx, rsi; hModule
0x180004a64  call    cs:__imp_SizeofResource
0x180004a6a  mov     r15d, eax
0x180004a6d  mov     rdx, r14; hResInfo
0x180004a70  mov     rcx, rsi; hModule
0x180004a73  call    cs:__imp_LoadResource
0x180004a79  test    rax, rax
0x180004a7c  jz      loc_1800046DB
0x180004a82  test    r15d, r15d
0x180004a85  jz      loc_1800046DB
0x180004a8b  mov     rcx, rax; hResData
0x180004a8e  call    cs:__imp_LockResource
0x180004a94  mov     rdx, rax
0x180004a97  test    rax, rax
0x180004a9a  jz      loc_1800046DB
0x180004aa0  cmp     [rax], r13w
0x180004aa4  jz      loc_1800046DB
0x180004aaa  mov     eax, r15d
0x180004aad  shr     rax, 1
0x180004ab0  lea     r8, [rdx+rax*2]
0x180004ab4  cmp     rdx, r8
0x180004ab7  jz      loc_1800046DB
0x180004abd  mov     [rbp+var_18], 7
0x180004ac5  mov     [rbp+var_20], r13
0x180004ac9  mov     word ptr [rbp+var_30], r13w
0x180004ace  lea     rcx, [rbp+var_30]
0x180004ad2  call    ??$_Construct@PEAG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXPEAG0Uforward_iterator_tag@1@@Z; std::wstring::_Construct<ushort *>(ushort *,ushort *,std::forward_iterator_tag)
0x180004ad7  nop
0x180004ad8  lea     rax, [rbp+var_30]
0x180004adc  cmp     [rbp+var_18], 8
0x180004ae1  cmovnb  rax, [rbp+var_30]
0x180004ae6  mov     [rsp+80h+var_58], rax
0x180004aeb  mov     dword ptr [rsp+80h+var_60], edi
0x180004aef  lea     r9, aStringTableBlo; "String Table Block %d: %ws"
0x180004af6  mov     r8d, 253h
0x180004afc  lea     rdx, aInstallerspFin; "Installersp_FindInstallerType"
0x180004b03  mov     ecx, 3
0x180004b08  call    AslLogCallPrintf
0x180004b0d  mov     r14, r13
0x180004b10  cmp     r14, 0Fh
0x180004b14  jnb     short loc_180004B4E
0x180004b16  lea     r13, [r14+r14*2]
0x180004b1a  lea     rax, __ImageBase
0x180004b21  mov     r15, ds:rva off_1800FB908[rax+r13*8]; "InstallShield" ...
0x180004b29  mov     rcx, r15
0x180004b2c  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x180004b31  mov     r9, rax
0x180004b34  xor     r8d, r8d
0x180004b37  mov     rdx, r15
0x180004b3a  lea     rcx, [rbp+var_30]
0x180004b3e  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KPEBG_K1@Z; std::wstring::find(ushort const *,unsigned __int64,unsigned __int64)
0x180004b43  cmp     rax, 0FFFFFFFFFFFFFFFFh
  ... truncated ...
```
