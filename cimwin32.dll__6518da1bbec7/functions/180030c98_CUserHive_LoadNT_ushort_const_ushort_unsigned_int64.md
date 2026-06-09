# CUserHive::LoadNT(ushort const *,ushort *,unsigned __int64)

- ea: `0x180030c98`
- end: `0x1800311e1`
- name: `?LoadNT@CUserHive@@AEAAKPEBGPEAG_K@Z`
- size: `1353`
- prototype: `unsigned int __fastcall(CUserHive *__hidden this, LPCWSTR lpAccountName, unsigned __int16 *, unsigned __int64)`
- caller_count: `12`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002f48c`
- `0x18002fda4`
- `0x180090b94`
- `0x1800a1220`
- `0x1800a1718`
- `0x1800a5cc4`
- `0x1800d3af4`
- `0x1800dfe1c`
- `0x1800e06a0`
- `0x1800e17c0`
- `0x1800e1e8c`
- `0x1800e3170`

## callees

- `0x180016900`
- `0x180030a9c`
- `0x180030c98`
- `0x1800311e8`
- `0x1800798d8`
- `0x1800fc902`
- `0x1800fc980`

## import_xrefs

- `msvcrt!free` at `0x180030dd8`
- `msvcrt!free` at `0x180030f68`
- `msvcrt!free` at `0x180030dd8`
- `msvcrt!free` at `0x180030f68`
- `msvcrt!malloc` at `0x180030d75`
- `msvcrt!malloc` at `0x180030d75`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x180031132`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x180031132`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030d66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031077`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030d66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031077`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180030dff`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180030dff`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180030f16`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180030f16`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x180030df3`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x180030df3`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18003104f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18003104f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180031178`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180031178`
- `framedynos!?captainsLog@@3VProviderLog@@A` at `0x1800310ba`
- `framedynos!?captainsLog@@3VProviderLog@@A` at `0x1800310f8`
- `framedynos!?LocalLogMessage@ProviderLog@@QEAAXPEBG0HW4LogLevel@1@@Z` at `0x1800310c1`
- `framedynos!?LocalLogMessage@ProviderLog@@QEAAXPEBG0HW4LogLevel@1@@Z` at `0x1800310ff`
- `framedynos!?LocalLogMessage@ProviderLog@@QEAAXPEBG0HW4LogLevel@1@@Z` at `0x1800310c1`
- `framedynos!?LocalLogMessage@ProviderLog@@QEAAXPEBG0HW4LogLevel@1@@Z` at `0x1800310ff`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180030cf7`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180031070`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180030cf7`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180031070`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180031038`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18003109c`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180031038`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18003109c`
- `framedynos!?Format@CHString@@QEAAXPEBGZZ` at `0x180031091`
- `framedynos!?Format@CHString@@QEAAXPEBGZZ` at `0x180031091`
- `framedynos!??0CRegistry@@QEAA@XZ` at `0x180030d06`
- `framedynos!??0CRegistry@@QEAA@XZ` at `0x180030d06`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x1800311aa`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x1800311aa`
- `framedynos!?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z` at `0x180030f8d`
- `framedynos!?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z` at `0x180030fd8`
- `framedynos!?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z` at `0x180030f8d`
- `framedynos!?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z` at `0x180030fd8`
- `framedynos!??YCHString@@QEAAAEBV0@PEBG@Z` at `0x18003102d`
- `framedynos!??YCHString@@QEAAAEBV0@PEBG@Z` at `0x18003102d`
- `framedynos!?BeginWrite@CThreadBase@@QEAAHK@Z` at `0x180031114`
- `framedynos!?BeginWrite@CThreadBase@@QEAAHK@Z` at `0x180031114`
- `framedynos!?EndWrite@CThreadBase@@QEAAXXZ` at `0x18003115c`
- `framedynos!?EndWrite@CThreadBase@@QEAAXXZ` at `0x18003115c`
- `framedynos!?Close@CRegistry@@QEAAXXZ` at `0x18003100c`
- `framedynos!?Close@CRegistry@@QEAAXXZ` at `0x18003100c`
- `framedynos!?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z` at `0x180030ffc`
- `framedynos!?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z` at `0x180030ffc`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800310cd`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800311b6`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800310cd`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800311b6`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18003105d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18003105d`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x180030d4e`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x180030daa`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x180030d4e`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x180030daa`

## string_xrefs

- `0x180030fed`: `ProfileImagePath`
- `0x180031085`: `Profile cannot be loaded since local NTUSER.DAT file for Profile SID is missing : Error %lxH (%ld)\n`
- `0x1800310b0`: `onecore\admin\wmi\wbem\providers\win32provider\common\userhive.cpp`
- `0x1800310ea`: `onecore\admin\wmi\wbem\providers\win32provider\common\userhive.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CUserHive::LoadNT(DWORD *this, LPCWSTR lpAccountName, unsigned __int16 *a3, unsigned __int64 a4)
{
  __int64 LastError; // rbx
  BOOL v9; // ebx
  void *v10; // rsi
  int v11; // edi
  PSID_IDENTIFIER_AUTHORITY SidIdentifierAuthority; // rbx
  DWORD v13; // r15d
  __int64 v14; // rcx
  __int64 v15; // rax
  DWORD i; // ebx
  PDWORD SidSubAuthority; // rax
  __int64 v18; // rax
  const WCHAR *v19; // rax
  __int64 v20; // rax
  DWORD cbSid; // [rsp+50h] [rbp-B08h] BYREF
  DWORD cchReferencedDomainName; // [rsp+54h] [rbp-B04h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+58h] [rbp-B00h] BYREF
  _BYTE v25[8]; // [rsp+60h] [rbp-AF8h] BYREF
  _BYTE v26[8]; // [rsp+68h] [rbp-AF0h] BYREF
  int v27; // [rsp+70h] [rbp-AE8h]
  _BYTE v28[608]; // [rsp+80h] [rbp-AD8h] BYREF
  WCHAR SubKey[264]; // [rsp+2E0h] [rbp-878h] BYREF
  WCHAR Dst[264]; // [rsp+4F0h] [rbp-668h] BYREF
  WCHAR ReferencedDomainName[520]; // [rsp+700h] [rbp-458h] BYREF

  cbSid = 0;
  cchReferencedDomainName = 0;
  memset_0(Dst, 0, 0x208u);
  peUse = 0;
  CHString::CHString((CHString *)v25);
  CRegistry::CRegistry((CRegistry *)v28);
  LODWORD(LastError) = CUserHive::AcquirePrivilege(this);
  if ( !(_DWORD)LastError )
  {
    cbSid = 0;
    cchReferencedDomainName = 520;
    v9 = LookupAccountNameLocalW(lpAccountName, 0, &cbSid, ReferencedDomainName, &cchReferencedDomainName, &peUse);
    if ( cchReferencedDomainName <= 0x208 )
    {
      if ( GetLastError() == 122 )
      {
        v10 = malloc(cbSid);
        if ( !v10 )
        {
          CUserHive::RestorePrivilege((CUserHive *)this);
          LODWORD(LastError) = 8;
          goto LABEL_41;
        }
        v9 = LookupAccountNameLocalW(lpAccountName, v10, &cbSid, ReferencedDomainName, &cchReferencedDomainName, &peUse);
        v11 = 0;
      }
      else
      {
        v11 = 0;
        v10 = 0;
      }
      if ( v9 )
      {
        SidIdentifierAuthority = GetSidIdentifierAuthority(v10);
        v13 = *GetSidSubAuthorityCount(v10);
        StringCbPrintfW(SubKey, 0x208u, L"S-%lu-", 1);
        v14 = -1;
        do
          ++v14;
        while ( SubKey[v14] );
        cbSid = v14;
        if ( SidIdentifierAuthority->Value[0] || SidIdentifierAuthority->Value[1] )
        {
          StringCbPrintfW(
            &SubKey[(unsigned int)v14],
            520 - 2LL * (unsigned int)v14,
            L"0x%02hx%02hx%02hx%02hx%02hx%02hx");
          v11 = 0;
        }
        else
        {
          StringCbPrintfW(
            &SubKey[(unsigned int)v14],
            520 - 2LL * (unsigned int)v14,
            L"%lu",
            SidIdentifierAuthority->Value[5]
          + (SidIdentifierAuthority->Value[4] << 8)
          + (SidIdentifierAuthority->Value[3] << 16)
          + (SidIdentifierAuthority->Value[2] << 24));
        }
        v15 = -1;
        do
          ++v15;
        while ( SubKey[v15] );
        cbSid = v15;
        for ( i = 0; i < v13; ++i )
        {
          SidSubAuthority = GetSidSubAuthority(v10, i);
          StringCbPrintfW(&SubKey[cbSid], 520 - 2LL * cbSid, L"-%lu", *SidSubAuthority);
          v18 = -1;
          do
            ++v18;
          while ( SubKey[v18] );
          cbSid = v18;
        }
        free(v10);
        LODWORD(LastError) = CRegistry::Open((CRegistry *)v28, HKEY_USERS, SubKey, 0x20019u);
        if ( (_DWORD)LastError )
        {
          StringCbPrintfW(Dst, 0x208u, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList\\%s", SubKey);
          LODWORD(LastError) = CRegistry::Open((CRegistry *)v28, HKEY_LOCAL_MACHINE, Dst, 0x20019u);
          if ( !(_DWORD)LastError )
          {
            LODWORD(LastError) = CRegistry::GetCurrentKeyValue(
                                   (CRegistry *)v28,
                                   L"ProfileImagePath",
                                   (struct CHString *)v25);
            CRegistry::Close((CRegistry *)v28);
            if ( !(_DWORD)LastError )
            {
              if ( this[1] >= 4 )
                CHString::operator+=(v25, L"\\NTUSER.DAT");
              v19 = (const WCHAR *)CHString::operator unsigned short const *(v25);
              ExpandEnvironmentStringsW(v19, Dst, 0x104u);
              while ( PathFileExistsW(Dst) )
              {
                CThreadBase::BeginWrite((CThreadBase *)CUserHive::m_criticalSection, 0xFFFFFFFF);
                try
                {
                  LODWORD(LastError) = RegLoadKeyW(HKEY_USERS, SubKey, Dst);
                  v27 = LastError;
                  CUserHive::OpenSoftwareSubKey((CUserHive *)this, SubKey, a3, a4);
                }
                catch ( ... )
                {
                  CThreadBase::EndWrite((CThreadBase *)CUserHive::m_criticalSection);
                  throw;
                }
                CThreadBase::EndWrite((CThreadBase *)CUserHive::m_criticalSection);
                if ( (_DWORD)LastError != 32 )
                  goto LABEL_40;
                if ( ++v11 >= 11 )
                  goto LABEL_33;
                Sleep(20 * v11);
              }
              CHString::CHString((CHString *)v26);
              LastError = GetLastError();
              CHString::Format(
                (CHString *)v26,
                L"Profile cannot be loaded since local NTUSER.DAT file for Profile SID is missing : Error %lxH (%ld)\n",
                LastError,
                LastError);
              v20 = CHString::operator unsigned short const *(v26);
              ProviderLog::LocalLogMessage(
                captainsLog,
                v20,
                L"onecore\\admin\\wmi\\wbem\\providers\\win32provider\\common\\userhive.cpp",
                406,
                1);
              CHString::~CHString((CHString *)v26);
LABEL_33:
              if ( (_DWORD)LastError == 32 )
                ProviderLog::LocalLogMessage(
                  captainsLog,
                  L"Sharing violation on NTUSER.DAT (Load)",
                  L"onecore\\admin\\wmi\\wbem\\providers\\win32provider\\common\\userhive.cpp",
                  441,
                  1);
            }
          }
        }
        else
        {
          CUserHive::OpenSoftwareSubKey((CUserHive *)this, SubKey, a3, a4);
        }
LABEL_40:
        CUserHive::RestorePrivilege((CUserHive *)this);
      }
      else
      {
        if ( v10 )
          free(v10);
        CUserHive::RestorePrivilege((CUserHive *)this);
        LODWORD(LastError) = 2202;
      }
    }
    else
    {
      LODWORD(LastError) = -2147217407;
    }
  }
LABEL_41:
  CRegistry::~CRegistry((CRegistry *)v28);
  CHString::~CHString((CHString *)v25);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180030c98  push    rbx
0x180030c9a  push    rsi
0x180030c9b  push    rdi
0x180030c9c  push    r12
0x180030c9e  push    r13
0x180030ca0  push    r14
0x180030ca2  push    r15
0x180030ca4  sub     rsp, 0B20h
0x180030cab  mov     rax, cs:__security_cookie
0x180030cb2  xor     rax, rsp
0x180030cb5  mov     [rsp+0B58h+var_48], rax
0x180030cbd  mov     r13, r9
0x180030cc0  mov     r12, r8
0x180030cc3  mov     rdi, rdx
0x180030cc6  mov     r14, rcx
0x180030cc9  xor     r15d, r15d
0x180030ccc  mov     [rsp+0B58h+cbSid], r15d
0x180030cd1  mov     [rsp+0B58h+var_B04], r15d
0x180030cd6  mov     esi, 208h
0x180030cdb  mov     r8d, esi; Size
0x180030cde  xor     edx, edx; Val
0x180030ce0  lea     rcx, [rsp+0B58h+Dst]; void *
0x180030ce8  call    memset_0
0x180030ced  mov     [rsp+0B58h+var_B00], r15d
0x180030cf2  lea     rcx, [rsp+0B58h+var_AF8]
0x180030cf7  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x180030cfd  nop
0x180030cfe  lea     rcx, [rsp+0B58h+var_AD8]
0x180030d06  call    cs:__imp_??0CRegistry@@QEAA@XZ; CRegistry::CRegistry(void)
0x180030d0c  nop
0x180030d0d  mov     rcx, r14; this
0x180030d10  call    ?AcquirePrivilege@CUserHive@@AEAAKXZ; CUserHive::AcquirePrivilege(void)
0x180030d15  mov     ebx, eax
0x180030d17  test    eax, eax
0x180030d19  jnz     loc_1800311A2
0x180030d1f  mov     [rsp+0B58h+cbSid], r15d
0x180030d24  mov     [rsp+0B58h+var_B04], esi
0x180030d28  lea     rax, [rsp+0B58h+var_B00]
0x180030d2d  mov     [rsp+0B58h+peUse], rax; peUse
0x180030d32  lea     rax, [rsp+0B58h+var_B04]
0x180030d37  mov     [rsp+0B58h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180030d3c  lea     r9, [rsp+0B58h+ReferencedDomainName]; ReferencedDomainName
0x180030d44  lea     r8, [rsp+0B58h+cbSid]; cbSid
0x180030d49  xor     edx, edx; Sid
0x180030d4b  mov     rcx, rdi; lpAccountName
0x180030d4e  call    cs:__imp_LookupAccountNameLocalW
0x180030d54  mov     ebx, eax
0x180030d56  cmp     [rsp+0B58h+var_B04], esi
0x180030d5a  jbe     short loc_180030D66
0x180030d5c  mov     ebx, 80041001h
0x180030d61  jmp     loc_1800311A2
0x180030d66  call    cs:__imp_GetLastError
0x180030d6c  cmp     eax, 7Ah ; 'z'
0x180030d6f  jnz     short loc_180030DC8
0x180030d71  mov     ecx, [rsp+0B58h+cbSid]; Size
0x180030d75  call    cs:__imp_malloc
0x180030d7b  mov     rsi, rax
0x180030d7e  test    rax, rax
0x180030d81  jz      short loc_180030DB6
0x180030d83  lea     rax, [rsp+0B58h+var_B00]
0x180030d88  mov     [rsp+0B58h+peUse], rax; peUse
0x180030d8d  lea     rax, [rsp+0B58h+var_B04]
0x180030d92  mov     [rsp+0B58h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180030d97  lea     r9, [rsp+0B58h+ReferencedDomainName]; ReferencedDomainName
0x180030d9f  lea     r8, [rsp+0B58h+cbSid]; cbSid
0x180030da4  mov     rdx, rsi; Sid
0x180030da7  mov     rcx, rdi; lpAccountName
0x180030daa  call    cs:__imp_LookupAccountNameLocalW
0x180030db0  mov     ebx, eax
0x180030db2  xor     edi, edi
0x180030db4  jmp     short loc_180030DCC
0x180030db6  mov     rcx, r14; this
0x180030db9  call    ?RestorePrivilege@CUserHive@@AEAAXXZ; CUserHive::RestorePrivilege(void)
0x180030dbe  mov     ebx, 8
0x180030dc3  jmp     loc_1800311A2
0x180030dc8  xor     edi, edi
0x180030dca  mov     esi, edi
0x180030dcc  test    ebx, ebx
0x180030dce  jnz     short loc_180030DF0
0x180030dd0  test    rsi, rsi
0x180030dd3  jz      short loc_180030DDE
0x180030dd5  mov     rcx, rsi; Block
0x180030dd8  call    cs:__imp_free
0x180030dde  mov     rcx, r14; this
0x180030de1  call    ?RestorePrivilege@CUserHive@@AEAAXXZ; CUserHive::RestorePrivilege(void)
0x180030de6  mov     ebx, 89Ah
0x180030deb  jmp     loc_1800311A2
0x180030df0  mov     rcx, rsi; pSid
0x180030df3  call    cs:__imp_GetSidIdentifierAuthority
0x180030df9  mov     rbx, rax
0x180030dfc  mov     rcx, rsi; pSid
0x180030dff  call    cs:__imp_GetSidSubAuthorityCount
0x180030e05  movzx   r15d, byte ptr [rax]
0x180030e09  mov     r9d, 1
0x180030e0f  lea     r8, aSLu; "S-%lu-"
0x180030e16  mov     edx, 208h; unsigned __int64
0x180030e1b  lea     rcx, [rsp+0B58h+SubKey]; unsigned __int16 *
0x180030e23  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180030e28  lea     rax, [rsp+0B58h+SubKey]
0x180030e30  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180030e34  inc     rcx
0x180030e37  cmp     [rax+rcx*2], di
0x180030e3b  jnz     short loc_180030E34
0x180030e3d  mov     [rsp+0B58h+cbSid], ecx
0x180030e41  movzx   r9d, byte ptr [rbx]
0x180030e45  lea     rdx, [rbx+1]
0x180030e49  test    r9b, r9b
0x180030e4c  jnz     short loc_180030E9E
0x180030e4e  cmp     [rdx], dil
0x180030e51  jnz     short loc_180030E9E
0x180030e53  mov     eax, ecx
0x180030e55  lea     rcx, [rax+rax]
0x180030e59  movzx   r9d, byte ptr [rbx+2]
0x180030e5e  shl     r9d, 18h
0x180030e62  movzx   eax, byte ptr [rbx+3]
0x180030e66  shl     eax, 10h
0x180030e69  add     r9d, eax
0x180030e6c  movzx   eax, byte ptr [rbx+4]
0x180030e70  shl     eax, 8
0x180030e73  add     r9d, eax
0x180030e76  movzx   eax, byte ptr [rbx+5]
0x180030e7a  add     r9d, eax
0x180030e7d  mov     edx, 208h
0x180030e82  sub     rdx, rcx; unsigned __int64
0x180030e85  lea     rax, [rsp+0B58h+SubKey]
0x180030e8d  add     rcx, rax; unsigned __int16 *
0x180030e90  lea     r8, Format; "%lu"
0x180030e97  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180030e9c  jmp     short loc_180030EF1
0x180030e9e  mov     eax, ecx
0x180030ea0  add     rax, rax
0x180030ea3  movzx   r8d, byte ptr [rbx+5]
0x180030ea8  movzx   r10d, byte ptr [rbx+4]
0x180030ead  movzx   r11d, byte ptr [rbx+3]
0x180030eb2  movzx   ebx, byte ptr [rbx+2]
0x180030eb6  movzx   edi, byte ptr [rdx]
0x180030eb9  mov     edx, 208h
0x180030ebe  sub     rdx, rax; unsigned __int64
0x180030ec1  lea     rcx, [rsp+0B58h+SubKey]
0x180030ec9  add     rcx, rax; unsigned __int16 *
0x180030ecc  mov     [rsp+0B58h+var_B18], r8d
0x180030ed1  mov     [rsp+0B58h+var_B20], r10d
0x180030ed6  mov     [rsp+0B58h+var_B28], r11d
0x180030edb  mov     dword ptr [rsp+0B58h+peUse], ebx
0x180030edf  mov     dword ptr [rsp+0B58h+cchReferencedDomainName], edi
0x180030ee3  lea     r8, a0x02hx02hx02hx; "0x%02hx%02hx%02hx%02hx%02hx%02hx"
0x180030eea  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180030eef  xor     edi, edi
0x180030ef1  lea     rcx, [rsp+0B58h+SubKey]
0x180030ef9  or      rax, 0FFFFFFFFFFFFFFFFh
0x180030efd  inc     rax
0x180030f00  cmp     [rcx+rax*2], di
0x180030f04  jnz     short loc_180030EFD
0x180030f06  mov     [rsp+0B58h+cbSid], eax
0x180030f0a  mov     ebx, edi
0x180030f0c  test    r15d, r15d
0x180030f0f  jz      short loc_180030F65
0x180030f11  mov     edx, ebx; nSubAuthority
0x180030f13  mov     rcx, rsi; pSid
0x180030f16  call    cs:__imp_GetSidSubAuthority
0x180030f1c  mov     ecx, [rsp+0B58h+cbSid]
0x180030f20  add     rcx, rcx
0x180030f23  mov     edx, 208h
0x180030f28  sub     rdx, rcx; unsigned __int64
0x180030f2b  lea     r8, [rsp+0B58h+SubKey]
0x180030f33  add     rcx, r8; unsigned __int16 *
0x180030f36  mov     r9d, [rax]
0x180030f39  lea     r8, aLu; "-%lu"
0x180030f40  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180030f45  lea     rcx, [rsp+0B58h+SubKey]
0x180030f4d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180030f51  inc     rax
0x180030f54  cmp     [rcx+rax*2], di
0x180030f58  jnz     short loc_180030F51
0x180030f5a  mov     [rsp+0B58h+cbSid], eax
0x180030f5e  inc     ebx
0x180030f60  cmp     ebx, r15d
0x180030f63  jb      short loc_180030F11
0x180030f65  mov     rcx, rsi; Block
0x180030f68  call    cs:__imp_free
0x180030f6e  mov     esi, 20019h
0x180030f73  mov     r9d, esi
0x180030f76  lea     r8, [rsp+0B58h+SubKey]
0x180030f7e  mov     rdx, 0FFFFFFFF80000003h
0x180030f85  lea     rcx, [rsp+0B58h+var_AD8]
0x180030f8d  call    cs:__imp_?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z; CRegistry::Open(HKEY__ *,ushort const *,ulong)
0x180030f93  mov     ebx, eax
0x180030f95  test    eax, eax
0x180030f97  jz      loc_180031183
0x180030f9d  lea     r9, [rsp+0B58h+SubKey]
0x180030fa5  lea     r8, aSoftwareMicros_15; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180030fac  mov     edx, 208h; unsigned __int64
0x180030fb1  lea     rcx, [rsp+0B58h+Dst]; unsigned __int16 *
0x180030fb9  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180030fbe  mov     r9d, esi
0x180030fc1  lea     r8, [rsp+0B58h+Dst]
0x180030fc9  mov     rdx, 0FFFFFFFF80000002h
0x180030fd0  lea     rcx, [rsp+0B58h+var_AD8]
0x180030fd8  call    cs:__imp_?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z; CRegistry::Open(HKEY__ *,ushort const *,ulong)
0x180030fde  mov     ebx, eax
0x180030fe0  test    eax, eax
0x180030fe2  jnz     loc_180031199
0x180030fe8  lea     r8, [rsp+0B58h+var_AF8]
0x180030fed  lea     rdx, aProfileimagepa; "ProfileImagePath"
0x180030ff4  lea     rcx, [rsp+0B58h+var_AD8]
0x180030ffc  call    cs:__imp_?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z; CRegistry::GetCurrentKeyValue(ushort const *,CHString &)
0x180031002  mov     ebx, eax
0x180031004  lea     rcx, [rsp+0B58h+var_AD8]
0x18003100c  call    cs:__imp_?Close@CRegistry@@QEAAXXZ; CRegistry::Close(void)
0x180031012  test    ebx, ebx
0x180031014  jnz     loc_180031199
0x18003101a  cmp     dword ptr [r14+4], 4
0x18003101f  jb      short loc_180031033
0x180031021  lea     rdx, aNtuserDat; "\\NTUSER.DAT"
0x180031028  lea     rcx, [rsp+0B58h+var_AF8]
0x18003102d  call    cs:__imp_??YCHString@@QEAAAEBV0@PEBG@Z; CHString::operator+=(ushort const *)
0x180031033  lea     rcx, [rsp+0B58h+var_AF8]
0x180031038  call    cs:__imp_??BCHString@@QEBAPEBGXZ; CHString::operator ushort const *(void)
0x18003103e  mov     rcx, rax; lpSrc
0x180031041  mov     r8d, 104h; nSize
0x180031047  lea     rdx, [rsp+0B58h+Dst]; lpDst
0x18003104f  call    cs:__imp_ExpandEnvironmentStringsW
0x180031055  lea     rcx, [rsp+0B58h+Dst]; pszPath
0x18003105d  call    cs:__imp_PathFileExistsW
0x180031063  test    eax, eax
0x180031065  jnz     loc_18003110A
0x18003106b  lea     rcx, [rsp+0B58h+var_AF0]
0x180031070  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x180031076  nop
0x180031077  call    cs:__imp_GetLastError
0x18003107d  mov     ebx, eax
0x18003107f  mov     r9d, eax
0x180031082  mov     r8d, eax
0x180031085  lea     rdx, aProfileCannotB; "Profile cannot be loaded since local NT"...
0x18003108c  lea     rcx, [rsp+0B58h+var_AF0]
0x180031091  call    cs:__imp_?Format@CHString@@QEAAXPEBGZZ; CHString::Format(ushort const *,...)
0x180031097  lea     rcx, [rsp+0B58h+var_AF0]
0x18003109c  call    cs:__imp_??BCHString@@QEBAPEBGXZ; CHString::operator ushort const *(void)
0x1800310a2  mov     dword ptr [rsp+0B58h+cchReferencedDomainName], 1
0x1800310aa  mov     r9d, 196h
0x1800310b0  lea     r8, aOnecoreAdminWm_39; "onecore\\admin\\wmi\\wbem\\providers\\w"...
0x1800310b7  mov     rdx, rax
0x1800310ba  mov     rcx, cs:__imp_?captainsLog@@3VProviderLog@@A; ProviderLog captainsLog
0x1800310c1  call    cs:__imp_?LocalLogMessage@ProviderLog@@QEAAXPEBG0HW4LogLevel@1@@Z; ProviderLog::LocalLogMessage(ushort const *,ushort const *,int,ProviderLog::LogLevel)
0x1800310c7  nop
0x1800310c8  lea     rcx, [rsp+0B58h+var_AF0]
0x1800310cd  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x1800310d3  cmp     ebx, 20h ; ' '
0x1800310d6  jnz     loc_180031199
0x1800310dc  mov     dword ptr [rsp+0B58h+cchReferencedDomainName], 1
0x1800310e4  mov     r9d, 1B9h
0x1800310ea  lea     r8, aOnecoreAdminWm_39; "onecore\\admin\\wmi\\wbem\\providers\\w"...
0x1800310f1  lea     rdx, aSharingViolati; "Sharing violation on NTUSER.DAT (Load)"
0x1800310f8  mov     rcx, cs:__imp_?captainsLog@@3VProviderLog@@A; ProviderLog captainsLog
0x1800310ff  call    cs:__imp_?LocalLogMessage@ProviderLog@@QEAAXPEBG0HW4LogLevel@1@@Z; ProviderLog::LocalLogMessage(ushort const *,ushort const *,int,ProviderLog::LogLevel)
0x180031105  jmp     loc_180031199
0x18003110a  or      edx, 0FFFFFFFFh
0x18003110d  lea     rcx, ?m_criticalSection@CUserHive@@0VCThreadBase@@A; CThreadBase CUserHive::m_criticalSection
0x180031114  call    cs:__imp_?BeginWrite@CThreadBase@@QEAAHK@Z; CThreadBase::BeginWrite(ulong)
0x18003111a  nop
0x18003111b  lea     r8, [rsp+0B58h+Dst]; lpFile
0x180031123  lea     rdx, [rsp+0B58h+SubKey]; lpSubKey
0x18003112b  mov     rcx, 0FFFFFFFF80000003h; hKey
0x180031132  call    cs:__imp_RegLoadKeyW
0x180031138  mov     ebx, eax
0x18003113a  mov     [rsp+0B58h+var_AE8], eax
0x18003113e  mov     r9, r13; unsigned __int64
0x180031141  mov     r8, r12; unsigned __int16 *
0x180031144  lea     rdx, [rsp+0B58h+SubKey]; unsigned __int16 *
0x18003114c  mov     rcx, r14; this
0x18003114f  call    ?OpenSoftwareSubKey@CUserHive@@AEAAXPEBGPEAG_K@Z; CUserHive::OpenSoftwareSubKey(ushort const *,ushort *,unsigned __int64)
0x180031154  nop
0x180031155  lea     rcx, ?m_criticalSection@CUserHive@@0VCThreadBase@@A; CThreadBase CUserHive::m_criticalSection
0x18003115c  call    cs:__imp_?EndWrite@CThreadBase@@QEAAXXZ; CThreadBase::EndWrite(void)
0x180031162  cmp     ebx, 20h ; ' '
0x180031165  jnz     short loc_180031199
0x180031167  inc     edi
0x180031169  cmp     edi, 0Bh
0x18003116c  jge     loc_1800310D3
0x180031172  lea     ecx, [rdi+rdi*4]
0x180031175  shl     ecx, 2; dwMilliseconds
0x180031178  call    cs:__imp_Sleep
0x18003117e  jmp     loc_180031055
0x180031183  mov     r9, r13; unsigned __int64
0x180031186  mov     r8, r12; unsigned __int16 *
0x180031189  lea     rdx, [rsp+0B58h+SubKey]; unsigned __int16 *
0x180031191  mov     rcx, r14; this
0x180031194  call    ?OpenSoftwareSubKey@CUserHive@@AEAAXPEBGPEAG_K@Z; CUserHive::OpenSoftwareSubKey(ushort const *,ushort *,unsigned __int64)
0x180031199  mov     rcx, r14; this
0x18003119c  call    ?RestorePrivilege@CUserHive@@AEAAXXZ; CUserHive::RestorePrivilege(void)
0x1800311a1  nop
0x1800311a2  lea     rcx, [rsp+0B58h+var_AD8]
0x1800311aa  call    cs:__imp_??1CRegistry@@QEAA@XZ; CRegistry::~CRegistry(void)
0x1800311b0  nop
0x1800311b1  lea     rcx, [rsp+0B58h+var_AF8]
0x1800311b6  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x1800311bc  mov     eax, ebx
0x1800311be  mov     rcx, [rsp+0B58h+var_48]
0x1800311c6  xor     rcx, rsp; StackCookie
0x1800311c9  call    __security_check_cookie
  ... truncated ...
```
