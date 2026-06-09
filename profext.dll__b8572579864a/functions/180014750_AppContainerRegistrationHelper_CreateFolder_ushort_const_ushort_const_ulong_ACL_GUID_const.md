# AppContainerRegistrationHelper::CreateFolder(ushort const *,ushort const *,ulong,_ACL *,_GUID const *)

- ea: `0x180014750`
- end: `0x180014bc9`
- name: `?CreateFolder@AppContainerRegistrationHelper@@CAJPEBG0KPEAU_ACL@@PEBU_GUID@@@Z`
- size: `1145`
- prototype: `__int64 __fastcall(char *, const unsigned __int16 *, DWORD dwFileAttributes, PACL pDacl, const struct _GUID *)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180014480`
- `0x180014d5c`

## callees

- `0x180002030`
- `0x1800040c0`
- `0x1800044e0`
- `0x180006400`
- `0x18000a540`
- `0x18000a7a4`
- `0x18000ee08`
- `0x18000f6cc`
- `0x180014750`
- `0x18001a380`
- `0x180022830`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180014ab7`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180014ab7`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800149b7`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800149b7`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001489a`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001489a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800148b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800149c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014acb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800148b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800149c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014acb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014b17`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014b60`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014b17`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014b60`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180014a51`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180014a51`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x180014b4d`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x180014b4d`

## string_xrefs

- `0x1800147bd`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180014811`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180014861`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x1800148e9`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x18001498f`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x1800149ef`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180014a6f`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180014af3`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180014b82`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180014818`: `Root %ls path %ls`
- `0x180014870`: `Root %ls path %ls append %ls`
- `0x1800149e3`: `Path %ls properties %d`

## pseudocode

```c
__int64 __fastcall AppContainerRegistrationHelper::CreateFolder(
        struct _ACL *a1,
        const unsigned __int16 *a2,
        DWORD dwFileAttributes,
        PACL pDacl,
        const struct _GUID *a5)
{
  struct _ACL *v7; // rdi
  int v9; // eax
  unsigned __int64 v10; // r10
  unsigned int v11; // ebx
  int v13; // eax
  signed int LastError; // eax
  unsigned int v15; // eax
  signed int v16; // eax
  int v17; // eax
  signed int v18; // eax
  signed int v19; // ebx
  PACL pDacla; // [rsp+28h] [rbp-D8h]
  DWORD v21; // [rsp+30h] [rbp-D0h]
  WINBOOL bSaclDefaulted; // [rsp+40h] [rbp-C0h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+48h] [rbp-B8h] BYREF
  PACL pSacl; // [rsp+50h] [rbp-B0h] BYREF
  WINBOOL bSaclPresent; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 v26[264]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  v7 = a1;
  v9 = StringCchCopyW(v26, 0x104u, (const unsigned __int16 *)a1);
  v11 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x335,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)(unsigned int)v9,
      (int)"Root %ls",
      (const char *)v7);
    return v11;
  }
  if ( a2 )
  {
    v11 = StringCchCatW(v26, v10, L"\\");
    if ( (v11 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x33A,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
        (const char *)v11,
        (int)"Root %ls path %ls",
        (const char *)v7,
        v26);
      return v11;
    }
    v13 = StringCchCatW(v26, 0x104u, a2);
    v11 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x33D,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
        (const char *)(unsigned int)v13,
        (int)"Root %ls path %ls append %ls",
        (const char *)v7,
        v26,
        a2);
      return v11;
    }
    v7 = (struct _ACL *)v26;
  }
  if ( !CreateDirectoryW((LPCWSTR)v7, 0) )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    if ( v11 != -2147024713 )
    {
      wil::details::in1diag3::Log_IfFailedMsg(
        retaddr,
        (void *)0x347,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
        (const char *)v11,
        (__int64)"Root %ls",
        (const char *)v7);
      AppContainerRegistrationHelper::LogFailureWithContext(
        &AppModelAppContainerCreateFolderFailure,
        (const unsigned __int16 *)v7,
        v11,
        0);
      if ( (unsigned int)dword_180031038 > 5 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_180031038, 0x400000000000LL) )
        {
          bSaclDefaulted = v11;
          pSacl = v7;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            (unsigned int)&dword_180031038,
            (unsigned int)byte_18002AF51,
            (_DWORD)a5,
            0,
            (__int64)&pSacl,
            (__int64)&bSaclDefaulted);
        }
      }
      v15 = AppContainerRegistrationHelper::ReportACLsOfParentFolderIfNeeded(v11, (const unsigned __int16 *)v7);
      LODWORD(pDacla) = v11;
      wil::details::in1diag3::Log_IfFailedMsg(
        retaddr,
        (void *)0x34C,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
        (const char *)v15,
        (__int64)"Hr 0x%0x for %ls.",
        (const char *)pDacla,
        v7);
      return v11;
    }
  }
  if ( !SetFileAttributesW((LPCWSTR)v7, dwFileAttributes) )
  {
    v16 = GetLastError();
    if ( v16 > 0 )
      v16 = (unsigned __int16)v16 | 0x80070000;
    v21 = dwFileAttributes;
    v17 = wil::details::in1diag3::Log_IfFailedMsg(
            retaddr,
            (void *)0x355,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
            (const char *)(unsigned int)v16,
            (__int64)"Path %ls properties %d",
            (const char *)v7,
            v21);
LABEL_22:
    v11 = v17;
    AppContainerRegistrationHelper::LogFailureWithContext(
      &AppModelAppContainerSetFolderAttributesFailure,
      (const unsigned __int16 *)v7,
      v17,
      a5);
    return v11;
  }
  if ( pDacl )
  {
    SecurityDescriptor = 0;
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(L"S:(ML;OICI;NW;;;LW)", 1u, &SecurityDescriptor, 0) )
      return wil::details::in1diag3::Return_GetLastErrorMsg(
               retaddr,
               (void *)0x363,
               (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
               "Root %ls",
               (const char *)v7);
    pSacl = 0;
    bSaclDefaulted = 0;
    bSaclPresent = 0;
    if ( GetSecurityDescriptorSacl(SecurityDescriptor, &bSaclPresent, &pSacl, &bSaclDefaulted) )
    {
      v18 = 0;
    }
    else
    {
      v18 = GetLastError();
      if ( v18 > 0 )
        v18 = (unsigned __int16)v18 | 0x80070000;
    }
    v11 = wil::details::in1diag3::Log_IfFailedMsg(
            retaddr,
            (void *)0x36D,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
            (const char *)(unsigned int)v18,
            (__int64)"Root %ls",
            (const char *)v7);
    if ( (v11 & 0x80000000) != 0 )
    {
      LocalFree(SecurityDescriptor);
      return v11;
    }
    v19 = SetNamedSecurityInfoW((LPWSTR)v7, SE_FILE_OBJECT, 0x14u, 0, 0, pDacl, pSacl);
    LocalFree(SecurityDescriptor);
    if ( v19 )
    {
      if ( v19 > 0 )
        v19 = (unsigned __int16)v19 | 0x80070000;
      v17 = wil::details::in1diag3::Log_IfFailedMsg(
              retaddr,
              (void *)0x381,
              (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
              (const char *)(unsigned int)v19,
              (__int64)"Root %ls",
              (const char *)v7);
      goto LABEL_22;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180014750  push    rbp
0x180014752  push    rbx
0x180014753  push    rsi
0x180014754  push    rdi
0x180014755  push    r12
0x180014757  push    r14
0x180014759  push    r15
0x18001475b  lea     rbp, [rsp-180h]
0x180014763  sub     rsp, 280h
0x18001476a  mov     rax, cs:__security_cookie
0x180014771  xor     rax, rsp
0x180014774  mov     [rbp+1B0h+var_40], rax
0x18001477b  mov     r12, [rbp+1B0h+arg_20]
0x180014782  mov     r14d, r8d
0x180014785  mov     r8, rcx; unsigned __int16 *
0x180014788  mov     rsi, rdx
0x18001478b  mov     rdi, rcx
0x18001478e  mov     r10d, 104h
0x180014794  mov     edx, r10d; unsigned __int64
0x180014797  lea     rcx, [rsp+2B0h+var_250]; unsigned __int16 *
0x18001479c  mov     r15, r9
0x18001479f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800147a4  mov     ebx, eax
0x1800147a6  test    eax, eax
0x1800147a8  jns     short loc_1800147DD
0x1800147aa  mov     rcx, [rbp+1B8h]; this
0x1800147b1  lea     rsi, aRootLs; "Root %ls"
0x1800147b8  mov     [rsp+2B0h+pDacl], rdi; char *
0x1800147bd  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800147c4  mov     r9d, eax; char *
0x1800147c7  mov     [rsp+2B0h+psidGroup], rsi; int
0x1800147cc  mov     edx, 335h; void *
0x1800147d1  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800147d6  mov     eax, ebx
0x1800147d8  jmp     loc_180014BA7
0x1800147dd  test    rsi, rsi
0x1800147e0  jz      loc_180014895
0x1800147e6  lea     r8, asc_180026BFC; "\\"
0x1800147ed  mov     rdx, r10; unsigned __int64
0x1800147f0  lea     rcx, [rsp+2B0h+var_250]; unsigned __int16 *
0x1800147f5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800147fa  mov     ebx, eax
0x1800147fc  test    eax, eax
0x1800147fe  jns     short loc_180014838
0x180014800  mov     rcx, [rbp+1B8h]; this
0x180014807  lea     rax, [rsp+2B0h+var_250]
0x18001480c  mov     [rsp+2B0h+var_280], rax
0x180014811  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180014818  lea     rax, aRootLsPathLs; "Root %ls path %ls"
0x18001481f  mov     [rsp+2B0h+pDacl], rdi; char *
0x180014824  mov     r9d, ebx; char *
0x180014827  mov     [rsp+2B0h+psidGroup], rax; int
0x18001482c  mov     edx, 33Ah; void *
0x180014831  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180014836  jmp     short loc_1800147D6
0x180014838  mov     r8, rsi; unsigned __int16 *
0x18001483b  lea     rcx, [rsp+2B0h+var_250]; unsigned __int16 *
0x180014840  mov     edx, 104h; unsigned __int64
0x180014845  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001484a  mov     ebx, eax
0x18001484c  test    eax, eax
0x18001484e  jns     short loc_180014890
0x180014850  mov     rcx, [rbp+1B8h]; this
0x180014857  lea     rax, [rsp+2B0h+var_250]
0x18001485c  mov     [rsp+2B0h+var_278], rsi
0x180014861  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180014868  mov     [rsp+2B0h+var_280], rax
0x18001486d  mov     r9d, ebx; char *
0x180014870  lea     rax, aRootLsPathLsAp; "Root %ls path %ls append %ls"
0x180014877  mov     [rsp+2B0h+pDacl], rdi; char *
0x18001487c  mov     edx, 33Dh; void *
0x180014881  mov     [rsp+2B0h+psidGroup], rax; int
0x180014886  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001488b  jmp     loc_1800147D6
0x180014890  lea     rdi, [rsp+2B0h+var_250]
0x180014895  xor     edx, edx; lpSecurityAttributes
0x180014897  mov     rcx, rdi; lpPathName
0x18001489a  call    cs:__imp_CreateDirectoryW
0x1800148a1  nop     dword ptr [rax+rax+00h]
0x1800148a6  mov     esi, 80070000h
0x1800148ab  test    eax, eax
0x1800148ad  jnz     loc_1800149B1
0x1800148b3  call    cs:__imp_GetLastError
0x1800148ba  nop     dword ptr [rax+rax+00h]
0x1800148bf  mov     ebx, eax
0x1800148c1  test    eax, eax
0x1800148c3  jle     short loc_1800148CA
0x1800148c5  movzx   ebx, ax
0x1800148c8  or      ebx, esi
0x1800148ca  cmp     ebx, 800700B7h
0x1800148d0  jz      loc_1800149B1
0x1800148d6  mov     rcx, [rbp+1B8h]; this
0x1800148dd  lea     rsi, aRootLs; "Root %ls"
0x1800148e4  mov     [rsp+2B0h+pDacl], rdi; char *
0x1800148e9  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800148f0  mov     r9d, ebx; char *
0x1800148f3  mov     [rsp+2B0h+psidGroup], rsi; __int64
0x1800148f8  mov     edx, 347h; void *
0x1800148fd  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180014902  xor     r9d, r9d; struct _GUID *
0x180014905  lea     rcx, AppModelAppContainerCreateFolderFailure; struct _EVENT_DESCRIPTOR *
0x18001490c  mov     r8d, ebx; int
0x18001490f  mov     rdx, rdi; unsigned __int16 *
0x180014912  call    ?LogFailureWithContext@AppContainerRegistrationHelper@@CAXPEBU_EVENT_DESCRIPTOR@@PEBGJPEBU_GUID@@@Z; AppContainerRegistrationHelper::LogFailureWithContext(_EVENT_DESCRIPTOR const *,ushort const *,long,_GUID const *)
0x180014917  mov     eax, cs:dword_180031038
0x18001491d  cmp     eax, 5
0x180014920  jbe     short loc_180014972
0x180014922  mov     rdx, 400000000000h
0x18001492c  lea     rcx, dword_180031038
0x180014933  call    _tlgKeywordOn
0x180014938  test    al, al
0x18001493a  jz      short loc_180014972
0x18001493c  lea     rax, [rsp+2B0h+bSaclDefaulted]
0x180014941  mov     [rsp+2B0h+bSaclDefaulted], ebx
0x180014945  mov     [rsp+2B0h+pDacl], rax
0x18001494a  lea     rdx, byte_18002AF51
0x180014951  lea     rax, [rsp+2B0h+pSacl]
0x180014956  mov     [rsp+2B0h+pSacl], rdi
0x18001495b  xor     r9d, r9d
0x18001495e  mov     [rsp+2B0h+psidGroup], rax
0x180014963  mov     r8, r12
0x180014966  lea     rcx, dword_180031038
0x18001496d  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180014972  mov     rdx, rdi; unsigned __int16 *
0x180014975  mov     ecx, ebx; int
0x180014977  call    ?ReportACLsOfParentFolderIfNeeded@AppContainerRegistrationHelper@@CAJJPEBG@Z; AppContainerRegistrationHelper::ReportACLsOfParentFolderIfNeeded(long,ushort const *)
0x18001497c  mov     rcx, [rbp+1B8h]; this
0x180014983  lea     rdx, aHr0x0xForLs; "Hr 0x%0x for %ls."
0x18001498a  mov     [rsp+2B0h+var_280], rdi
0x18001498f  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180014996  mov     dword ptr [rsp+2B0h+pDacl], ebx; char *
0x18001499a  mov     r9d, eax; char *
0x18001499d  mov     [rsp+2B0h+psidGroup], rdx; __int64
0x1800149a2  mov     edx, 34Ch; void *
0x1800149a7  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800149ac  jmp     loc_1800147D6
0x1800149b1  mov     edx, r14d; dwFileAttributes
0x1800149b4  mov     rcx, rdi; lpFileName
0x1800149b7  call    cs:__imp_SetFileAttributesW
0x1800149be  nop     dword ptr [rax+rax+00h]
0x1800149c3  test    eax, eax
0x1800149c5  jnz     short loc_180014A29
0x1800149c7  call    cs:__imp_GetLastError
0x1800149ce  nop     dword ptr [rax+rax+00h]
0x1800149d3  test    eax, eax
0x1800149d5  jle     short loc_1800149DC
0x1800149d7  movzx   eax, ax
0x1800149da  or      eax, esi
0x1800149dc  mov     rcx, [rbp+1B8h]; this
0x1800149e3  lea     rdx, aPathLsProperti; "Path %ls properties %d"
0x1800149ea  mov     dword ptr [rsp+2B0h+var_280], r14d
0x1800149ef  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800149f6  mov     [rsp+2B0h+pDacl], rdi; char *
0x1800149fb  mov     r9d, eax; char *
0x1800149fe  mov     [rsp+2B0h+psidGroup], rdx; __int64
0x180014a03  mov     edx, 355h; void *
0x180014a08  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180014a0d  mov     r9, r12; struct _GUID *
0x180014a10  lea     rcx, AppModelAppContainerSetFolderAttributesFailure; struct _EVENT_DESCRIPTOR *
0x180014a17  mov     r8d, eax; int
0x180014a1a  mov     rdx, rdi; unsigned __int16 *
0x180014a1d  mov     ebx, eax
0x180014a1f  call    ?LogFailureWithContext@AppContainerRegistrationHelper@@CAXPEBU_EVENT_DESCRIPTOR@@PEBGJPEBU_GUID@@@Z; AppContainerRegistrationHelper::LogFailureWithContext(_EVENT_DESCRIPTOR const *,ushort const *,long,_GUID const *)
0x180014a24  jmp     loc_1800147D6
0x180014a29  test    r15, r15
0x180014a2c  jz      loc_180014BA5
0x180014a32  xor     r9d, r9d; SecurityDescriptorSize
0x180014a35  mov     [rsp+2B0h+SecurityDescriptor], 0
0x180014a3e  lea     r8, [rsp+2B0h+SecurityDescriptor]; SecurityDescriptor
0x180014a43  lea     rcx, StringSecurityDescriptor; "S:(ML;OICI;NW;;;LW)"
0x180014a4a  lea     r14d, [r9+1]
0x180014a4e  mov     edx, r14d; StringSDRevision
0x180014a51  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180014a58  nop     dword ptr [rax+rax+00h]
0x180014a5d  test    eax, eax
0x180014a5f  jnz     short loc_180014A8A
0x180014a61  mov     rcx, [rbp+1B8h]; this
0x180014a68  lea     r9, aRootLs; "Root %ls"
0x180014a6f  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180014a76  mov     [rsp+2B0h+psidGroup], rdi; char *
0x180014a7b  mov     edx, 363h; void *
0x180014a80  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x180014a85  jmp     loc_180014BA7
0x180014a8a  mov     rcx, [rsp+2B0h+SecurityDescriptor]; pSecurityDescriptor
0x180014a8f  lea     r9, [rsp+2B0h+bSaclDefaulted]; lpbSaclDefaulted
0x180014a94  lea     r8, [rsp+2B0h+pSacl]; pSacl
0x180014a99  mov     [rsp+2B0h+pSacl], 0
0x180014aa2  lea     rdx, [rsp+2B0h+bSaclPresent]; lpbSaclPresent
0x180014aa7  mov     [rsp+2B0h+bSaclDefaulted], 0
0x180014aaf  mov     [rsp+2B0h+bSaclPresent], 0
0x180014ab7  call    cs:__imp_GetSecurityDescriptorSacl
0x180014abe  nop     dword ptr [rax+rax+00h]
0x180014ac3  test    eax, eax
0x180014ac5  jz      short loc_180014ACB
0x180014ac7  xor     eax, eax
0x180014ac9  jmp     short loc_180014AE0
0x180014acb  call    cs:__imp_GetLastError
0x180014ad2  nop     dword ptr [rax+rax+00h]
0x180014ad7  test    eax, eax
0x180014ad9  jle     short loc_180014AE0
0x180014adb  movzx   eax, ax
0x180014ade  or      eax, esi
0x180014ae0  mov     rcx, [rbp+1B8h]; this
0x180014ae7  lea     rsi, aRootLs; "Root %ls"
0x180014aee  mov     [rsp+2B0h+pDacl], rdi; char *
0x180014af3  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180014afa  mov     r9d, eax; char *
0x180014afd  mov     [rsp+2B0h+psidGroup], rsi; __int64
0x180014b02  mov     edx, 36Dh; void *
0x180014b07  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180014b0c  mov     ebx, eax
0x180014b0e  test    eax, eax
0x180014b10  jns     short loc_180014B28
0x180014b12  mov     rcx, [rsp+2B0h+SecurityDescriptor]; hMem
0x180014b17  call    cs:__imp_LocalFree
0x180014b1e  nop     dword ptr [rax+rax+00h]
0x180014b23  jmp     loc_1800147D6
0x180014b28  mov     rax, [rsp+2B0h+pSacl]
0x180014b2d  xor     r9d, r9d; psidOwner
0x180014b30  mov     [rsp+2B0h+var_280], rax; pSacl
0x180014b35  mov     edx, r14d; ObjectType
0x180014b38  mov     [rsp+2B0h+pDacl], r15; pDacl
0x180014b3d  mov     rcx, rdi; pObjectName
0x180014b40  mov     [rsp+2B0h+psidGroup], 0; psidGroup
0x180014b49  lea     r8d, [r9+14h]; SecurityInfo
0x180014b4d  call    cs:__imp_SetNamedSecurityInfoW
0x180014b54  nop     dword ptr [rax+rax+00h]
0x180014b59  mov     rcx, [rsp+2B0h+SecurityDescriptor]; hMem
0x180014b5e  mov     ebx, eax
0x180014b60  call    cs:__imp_LocalFree
0x180014b67  nop     dword ptr [rax+rax+00h]
0x180014b6c  test    ebx, ebx
0x180014b6e  jz      short loc_180014BA5
0x180014b70  jle     short loc_180014B7B
0x180014b72  movzx   ebx, bx
0x180014b75  or      ebx, 80070000h
0x180014b7b  mov     rcx, [rbp+1B8h]; this
0x180014b82  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180014b89  mov     [rsp+2B0h+pDacl], rdi; char *
0x180014b8e  mov     r9d, ebx; char *
0x180014b91  mov     edx, 381h; void *
0x180014b96  mov     [rsp+2B0h+psidGroup], rsi; __int64
0x180014b9b  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180014ba0  jmp     loc_180014A0D
0x180014ba5  xor     eax, eax
0x180014ba7  mov     rcx, [rbp+1B0h+var_40]
0x180014bae  xor     rcx, rsp; StackCookie
0x180014bb1  call    __security_check_cookie
0x180014bb6  add     rsp, 280h
0x180014bbd  pop     r15
0x180014bbf  pop     r14
0x180014bc1  pop     r12
0x180014bc3  pop     rdi
0x180014bc4  pop     rsi
0x180014bc5  pop     rbx
0x180014bc6  pop     rbp
0x180014bc7  retn
```
