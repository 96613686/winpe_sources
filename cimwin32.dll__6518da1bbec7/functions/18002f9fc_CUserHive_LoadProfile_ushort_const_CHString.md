# CUserHive::LoadProfile(ushort const *,CHString &)

- ea: `0x18002f9fc`
- end: `0x18002fd9b`
- name: `?LoadProfile@CUserHive@@QEAAKPEBGAEAVCHString@@@Z`
- size: `927`
- prototype: `unsigned int __fastcall(CUserHive *__hidden this, LPCWSTR lpSubKey, struct CHString *)`
- caller_count: `7`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002fda4`
- `0x18003158c`
- `0x18003301c`
- `0x18007ac14`
- `0x1800a6f10`
- `0x1800a792c`
- `0x1800a8cc0`

## callees

- `0x18001a310`
- `0x18002f9fc`
- `0x180030a9c`
- `0x1800311e8`
- `0x1800312b4`
- `0x1800fc902`
- `0x1800fc980`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002fb68`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002fb68`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x18002fd33`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x18002fd33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fcb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fcb6`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002fc93`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002fc93`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002fd8f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002fd8f`
- `framedynos!?captainsLog@@3VProviderLog@@A` at `0x18002fcf9`
- `framedynos!?captainsLog@@3VProviderLog@@A` at `0x18002fd7c`
- `framedynos!?LocalLogMessage@ProviderLog@@QEAAXPEBG0HW4LogLevel@1@@Z` at `0x18002fd00`
- `framedynos!?LocalLogMessage@ProviderLog@@QEAAXPEBG0HW4LogLevel@1@@Z` at `0x18002fd83`
- `framedynos!?LocalLogMessage@ProviderLog@@QEAAXPEBG0HW4LogLevel@1@@Z` at `0x18002fd00`
- `framedynos!?LocalLogMessage@ProviderLog@@QEAAXPEBG0HW4LogLevel@1@@Z` at `0x18002fd83`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18002fa30`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18002fcaf`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18002fa30`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18002fcaf`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18002fb50`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18002fc7f`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18002fcdb`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18002fb50`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18002fc7f`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18002fcdb`
- `framedynos!?Format@CHString@@QEAAXPEBGZZ` at `0x18002fcd0`
- `framedynos!?Format@CHString@@QEAAXPEBGZZ` at `0x18002fcd0`
- `framedynos!??0CRegistry@@QEAA@XZ` at `0x18002fa3f`
- `framedynos!??0CRegistry@@QEAA@XZ` at `0x18002fab5`
- `framedynos!??0CRegistry@@QEAA@XZ` at `0x18002fa3f`
- `framedynos!??0CRegistry@@QEAA@XZ` at `0x18002fab5`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x18002fa6c`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x18002fb19`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x18002fb8b`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x18002fa6c`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x18002fb19`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x18002fb8b`
- `framedynos!?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z` at `0x18002faa2`
- `framedynos!?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z` at `0x18002faed`
- `framedynos!?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z` at `0x18002fbfd`
- `framedynos!?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z` at `0x18002faa2`
- `framedynos!?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z` at `0x18002faed`
- `framedynos!?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z` at `0x18002fbfd`
- `framedynos!??YCHString@@QEAAAEBV0@PEBG@Z` at `0x18002fb3e`
- `framedynos!??YCHString@@QEAAAEBV0@PEBG@Z` at `0x18002fc62`
- `framedynos!??YCHString@@QEAAAEBV0@PEBG@Z` at `0x18002fb3e`
- `framedynos!??YCHString@@QEAAAEBV0@PEBG@Z` at `0x18002fc62`
- `framedynos!?BeginWrite@CThreadBase@@QEAAHK@Z` at `0x18002fd21`
- `framedynos!?BeginWrite@CThreadBase@@QEAAHK@Z` at `0x18002fd21`
- `framedynos!?EndWrite@CThreadBase@@QEAAXXZ` at `0x18002fd46`
- `framedynos!?EndWrite@CThreadBase@@QEAAXXZ` at `0x18002fd46`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x18002fb2b`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x18002fb2b`
- `framedynos!?Close@CRegistry@@QEAAXXZ` at `0x18002fb0d`
- `framedynos!?Close@CRegistry@@QEAAXXZ` at `0x18002fc41`
- `framedynos!?Close@CRegistry@@QEAAXXZ` at `0x18002fb0d`
- `framedynos!?Close@CRegistry@@QEAAXXZ` at `0x18002fc41`
- `framedynos!??4CHString@@QEAAAEBV0@PEBG@Z` at `0x18002fa50`
- `framedynos!??4CHString@@QEAAAEBV0@PEBG@Z` at `0x18002fa50`
- `framedynos!?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z` at `0x18002fc31`
- `framedynos!?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z` at `0x18002fc31`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18002fa78`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18002fb74`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18002fb97`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18002fd0c`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18002fa78`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18002fb74`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18002fb97`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18002fd0c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18002fca0`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18002fca0`

## string_xrefs

- `0x18002fc22`: `ProfileImagePath`
- `0x18002fcc4`: `Profile cannot be loaded since local NTUSER.DAT file for Profile SID is missing : Error %lxH (%ld)\n`
- `0x18002fcef`: `onecore\admin\wmi\wbem\providers\win32provider\common\userhive.cpp`
- `0x18002fd6e`: `onecore\admin\wmi\wbem\providers\win32provider\common\userhive.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CUserHive::LoadProfile(CUserHive *this, LPCWSTR lpSubKey, struct CHString *a3)
{
  unsigned int v6; // ebx
  CUserHive *v8; // rcx
  __int64 LastError; // rdi
  const WCHAR *v10; // rax
  CUserHive *v11; // rcx
  const WCHAR *v12; // rax
  int v13; // ebx
  __int64 v14; // rax
  _BYTE v15[8]; // [rsp+30h] [rbp-728h] BYREF
  _BYTE v16[8]; // [rsp+38h] [rbp-720h] BYREF
  int v17; // [rsp+40h] [rbp-718h]
  WCHAR Dst[304]; // [rsp+50h] [rbp-708h] BYREF
  _BYTE v19[608]; // [rsp+2B0h] [rbp-4A8h] BYREF
  unsigned __int16 v20[264]; // [rsp+510h] [rbp-248h] BYREF

  CHString::CHString((CHString *)v16);
  CRegistry::CRegistry((CRegistry *)v19);
  CHString::operator=(a3, &Data);
  v6 = CUserHive::AcquirePrivilege((DWORD *)this);
  if ( v6 )
  {
    CRegistry::~CRegistry((CRegistry *)v19);
    CHString::~CHString((CHString *)v16);
    return v6;
  }
  if ( CRegistry::Open((CRegistry *)v19, HKEY_USERS, lpSubKey, 0x20019u) )
  {
    StringCchPrintfW(v20, 0x104u, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList\\%s", lpSubKey);
    LODWORD(LastError) = CRegistry::Open((CRegistry *)v19, HKEY_LOCAL_MACHINE, v20, 0x20019u);
    if ( (_DWORD)LastError )
      goto LABEL_9;
    CUserHive::UserAccountFromProfile(v11, (struct CRegistry *)v19, a3);
    LODWORD(LastError) = CRegistry::GetCurrentKeyValue((CRegistry *)v19, L"ProfileImagePath", (struct CHString *)v16);
    CRegistry::Close((CRegistry *)v19);
    if ( (_DWORD)LastError )
      goto LABEL_9;
    if ( *((_DWORD *)this + 1) >= 4u )
      CHString::operator+=(v16, L"\\NTUSER.DAT");
    memset_0(Dst, 0, 0x208u);
    v12 = (const WCHAR *)CHString::operator unsigned short const *(v16);
    ExpandEnvironmentStringsW(v12, Dst, 0x104u);
    v13 = 0;
    while ( PathFileExistsW(Dst) )
    {
      CThreadBase::BeginWrite((CThreadBase *)CUserHive::m_criticalSection, 0xFFFFFFFF);
      try
      {
        LODWORD(LastError) = RegLoadKeyW(HKEY_USERS, lpSubKey, Dst);
        v17 = LastError;
      }
      catch ( ... )
      {
        CThreadBase::EndWrite((CThreadBase *)CUserHive::m_criticalSection);
        throw;
      }
      CThreadBase::EndWrite((CThreadBase *)CUserHive::m_criticalSection);
      if ( (_DWORD)LastError != 32 )
        goto LABEL_7;
      if ( ++v13 >= 11 )
        goto LABEL_7;
      ProviderLog::LocalLogMessage(
        captainsLog,
        L"Sharing violation on NTUSER.DAT (LoadProfile)",
        L"onecore\\admin\\wmi\\wbem\\providers\\win32provider\\common\\userhive.cpp",
        589,
        1);
      Sleep(20 * v13);
    }
    CHString::CHString((CHString *)v15);
    LastError = GetLastError();
    CHString::Format(
      (CHString *)v15,
      L"Profile cannot be loaded since local NTUSER.DAT file for Profile SID is missing : Error %lxH (%ld)\n",
      LastError,
      LastError);
    v14 = CHString::operator unsigned short const *(v15);
    ProviderLog::LocalLogMessage(
      captainsLog,
      v14,
      L"onecore\\admin\\wmi\\wbem\\providers\\win32provider\\common\\userhive.cpp",
      567,
      1);
    CHString::~CHString((CHString *)v15);
  }
  else
  {
    CRegistry::CRegistry((CRegistry *)Dst);
    StringCchPrintfW(v20, 0x104u, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList\\%s", lpSubKey);
    LODWORD(LastError) = CRegistry::Open((CRegistry *)Dst, HKEY_LOCAL_MACHINE, v20, 0x20019u);
    if ( !(_DWORD)LastError )
    {
      LODWORD(LastError) = CUserHive::UserAccountFromProfile(v8, (struct CRegistry *)Dst, a3);
      CRegistry::Close((CRegistry *)Dst);
    }
    CRegistry::~CRegistry((CRegistry *)Dst);
  }
LABEL_7:
  if ( !(_DWORD)LastError )
  {
    CHString::CHString((CHString *)v15, lpSubKey);
    CHString::operator+=(v15, L"\\Software");
    v10 = (const WCHAR *)CHString::operator unsigned short const *(v15);
    RegOpenKeyExW(HKEY_USERS, v10, 0, 1u, (PHKEY)this + 36);
    CHString::~CHString((CHString *)v15);
  }
LABEL_9:
  CUserHive::RestorePrivilege(this);
  CRegistry::~CRegistry((CRegistry *)v19);
  CHString::~CHString((CHString *)v16);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18002f9fc  mov     [rsp+arg_18], rbx
0x18002fa01  push    rsi
0x18002fa02  push    rdi
0x18002fa03  push    r12
0x18002fa05  push    r14
0x18002fa07  push    r15
0x18002fa09  sub     rsp, 730h
0x18002fa10  mov     rax, cs:__security_cookie
0x18002fa17  xor     rax, rsp
0x18002fa1a  mov     [rsp+758h+var_38], rax
0x18002fa22  mov     rsi, r8
0x18002fa25  mov     r15, rdx
0x18002fa28  mov     r14, rcx
0x18002fa2b  lea     rcx, [rsp+758h+var_720]
0x18002fa30  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x18002fa36  nop
0x18002fa37  lea     rcx, [rsp+758h+var_4A8]
0x18002fa3f  call    cs:__imp_??0CRegistry@@QEAA@XZ; CRegistry::CRegistry(void)
0x18002fa45  nop
0x18002fa46  lea     rdx, Data
0x18002fa4d  mov     rcx, rsi
0x18002fa50  call    cs:__imp_??4CHString@@QEAAAEBV0@PEBG@Z; CHString::operator=(ushort const *)
0x18002fa56  mov     rcx, r14; this
0x18002fa59  call    ?AcquirePrivilege@CUserHive@@AEAAKXZ; CUserHive::AcquirePrivilege(void)
0x18002fa5e  mov     ebx, eax
0x18002fa60  test    eax, eax
0x18002fa62  jz      short loc_18002FA85
0x18002fa64  lea     rcx, [rsp+758h+var_4A8]
0x18002fa6c  call    cs:__imp_??1CRegistry@@QEAA@XZ; CRegistry::~CRegistry(void)
0x18002fa72  nop
0x18002fa73  lea     rcx, [rsp+758h+var_720]
0x18002fa78  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x18002fa7e  mov     eax, ebx
0x18002fa80  jmp     loc_18002FB9F
0x18002fa85  mov     ebx, 20019h
0x18002fa8a  mov     r9d, ebx
0x18002fa8d  mov     r8, r15
0x18002fa90  mov     r12, 0FFFFFFFF80000003h
0x18002fa97  mov     rdx, r12
0x18002fa9a  lea     rcx, [rsp+758h+var_4A8]
0x18002faa2  call    cs:__imp_?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z; CRegistry::Open(HKEY__ *,ushort const *,ulong)
0x18002faa8  test    eax, eax
0x18002faaa  jnz     loc_18002FBC7
0x18002fab0  lea     rcx, [rsp+758h+Dst]
0x18002fab5  call    cs:__imp_??0CRegistry@@QEAA@XZ; CRegistry::CRegistry(void)
0x18002fabb  nop
0x18002fabc  mov     r9, r15
0x18002fabf  lea     r8, aSoftwareMicros_15; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18002fac6  mov     edx, 104h; unsigned __int64
0x18002facb  lea     rcx, [rsp+758h+var_248]; unsigned __int16 *
0x18002fad3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002fad8  mov     r9d, ebx
0x18002fadb  lea     r8, [rsp+758h+var_248]
0x18002fae3  lea     rdx, [r12-1]
0x18002fae8  lea     rcx, [rsp+758h+Dst]
0x18002faed  call    cs:__imp_?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z; CRegistry::Open(HKEY__ *,ushort const *,ulong)
0x18002faf3  mov     edi, eax
0x18002faf5  test    eax, eax
0x18002faf7  jnz     short loc_18002FB14
0x18002faf9  mov     r8, rsi; struct CHString *
0x18002fafc  lea     rdx, [rsp+758h+Dst]; struct CRegistry *
0x18002fb01  call    ?UserAccountFromProfile@CUserHive@@QEAAKAEAVCRegistry@@AEAVCHString@@@Z; CUserHive::UserAccountFromProfile(CRegistry &,CHString &)
0x18002fb06  mov     edi, eax
0x18002fb08  lea     rcx, [rsp+758h+Dst]
0x18002fb0d  call    cs:__imp_?Close@CRegistry@@QEAAXXZ; CRegistry::Close(void)
0x18002fb13  nop
0x18002fb14  lea     rcx, [rsp+758h+Dst]
0x18002fb19  call    cs:__imp_??1CRegistry@@QEAA@XZ; CRegistry::~CRegistry(void)
0x18002fb1f  test    edi, edi
0x18002fb21  jnz     short loc_18002FB7A
0x18002fb23  mov     rdx, r15
0x18002fb26  lea     rcx, [rsp+758h+var_728]
0x18002fb2b  call    cs:__imp_??0CHString@@QEAA@PEBG@Z; CHString::CHString(ushort const *)
0x18002fb31  nop
0x18002fb32  lea     rdx, aSoftware; "\\Software"
0x18002fb39  lea     rcx, [rsp+758h+var_728]
0x18002fb3e  call    cs:__imp_??YCHString@@QEAAAEBV0@PEBG@Z; CHString::operator+=(ushort const *)
0x18002fb44  lea     rbx, [r14+120h]
0x18002fb4b  lea     rcx, [rsp+758h+var_728]
0x18002fb50  call    cs:__imp_??BCHString@@QEBAPEBGXZ; CHString::operator ushort const *(void)
0x18002fb56  mov     rdx, rax; lpSubKey
0x18002fb59  mov     [rsp+758h+phkResult], rbx; phkResult
0x18002fb5e  lea     r9d, [rdi+1]; samDesired
0x18002fb62  xor     r8d, r8d; ulOptions
0x18002fb65  mov     rcx, r12; hKey
0x18002fb68  call    cs:__imp_RegOpenKeyExW
0x18002fb6e  nop
0x18002fb6f  lea     rcx, [rsp+758h+var_728]
0x18002fb74  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x18002fb7a  mov     rcx, r14; this
0x18002fb7d  call    ?RestorePrivilege@CUserHive@@AEAAXXZ; CUserHive::RestorePrivilege(void)
0x18002fb82  nop
0x18002fb83  lea     rcx, [rsp+758h+var_4A8]
0x18002fb8b  call    cs:__imp_??1CRegistry@@QEAA@XZ; CRegistry::~CRegistry(void)
0x18002fb91  nop
0x18002fb92  lea     rcx, [rsp+758h+var_720]
0x18002fb97  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x18002fb9d  mov     eax, edi
0x18002fb9f  mov     rcx, [rsp+758h+var_38]
0x18002fba7  xor     rcx, rsp; StackCookie
0x18002fbaa  call    __security_check_cookie
0x18002fbaf  mov     rbx, [rsp+758h+arg_18]
0x18002fbb7  add     rsp, 730h
0x18002fbbe  pop     r15
0x18002fbc0  pop     r14
0x18002fbc2  pop     r12
0x18002fbc4  pop     rdi
0x18002fbc5  pop     rsi
0x18002fbc6  retn
0x18002fbc7  mov     r9, r15
0x18002fbca  lea     r8, aSoftwareMicros_15; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18002fbd1  mov     edx, 104h; unsigned __int64
0x18002fbd6  lea     rcx, [rsp+758h+var_248]; unsigned __int16 *
0x18002fbde  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002fbe3  mov     r9d, ebx
0x18002fbe6  lea     r8, [rsp+758h+var_248]
0x18002fbee  mov     rdx, 0FFFFFFFF80000002h
0x18002fbf5  lea     rcx, [rsp+758h+var_4A8]
0x18002fbfd  call    cs:__imp_?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z; CRegistry::Open(HKEY__ *,ushort const *,ulong)
0x18002fc03  mov     edi, eax
0x18002fc05  test    eax, eax
0x18002fc07  jnz     loc_18002FB7A
0x18002fc0d  mov     r8, rsi; struct CHString *
0x18002fc10  lea     rdx, [rsp+758h+var_4A8]; struct CRegistry *
0x18002fc18  call    ?UserAccountFromProfile@CUserHive@@QEAAKAEAVCRegistry@@AEAVCHString@@@Z; CUserHive::UserAccountFromProfile(CRegistry &,CHString &)
0x18002fc1d  lea     r8, [rsp+758h+var_720]
0x18002fc22  lea     rdx, aProfileimagepa; "ProfileImagePath"
0x18002fc29  lea     rcx, [rsp+758h+var_4A8]
0x18002fc31  call    cs:__imp_?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z; CRegistry::GetCurrentKeyValue(ushort const *,CHString &)
0x18002fc37  mov     edi, eax
0x18002fc39  lea     rcx, [rsp+758h+var_4A8]
0x18002fc41  call    cs:__imp_?Close@CRegistry@@QEAAXXZ; CRegistry::Close(void)
0x18002fc47  test    edi, edi
0x18002fc49  jnz     loc_18002FB7A
0x18002fc4f  cmp     dword ptr [r14+4], 4
0x18002fc54  jb      short loc_18002FC68
0x18002fc56  lea     rdx, aNtuserDat; "\\NTUSER.DAT"
0x18002fc5d  lea     rcx, [rsp+758h+var_720]
0x18002fc62  call    cs:__imp_??YCHString@@QEAAAEBV0@PEBG@Z; CHString::operator+=(ushort const *)
0x18002fc68  xor     edx, edx; Val
0x18002fc6a  mov     r8d, 208h; Size
0x18002fc70  lea     rcx, [rsp+758h+Dst]; void *
0x18002fc75  call    memset_0
0x18002fc7a  lea     rcx, [rsp+758h+var_720]
0x18002fc7f  call    cs:__imp_??BCHString@@QEBAPEBGXZ; CHString::operator ushort const *(void)
0x18002fc85  mov     rcx, rax; lpSrc
0x18002fc88  mov     r8d, 104h; nSize
0x18002fc8e  lea     rdx, [rsp+758h+Dst]; lpDst
0x18002fc93  call    cs:__imp_ExpandEnvironmentStringsW
0x18002fc99  xor     ebx, ebx
0x18002fc9b  lea     rcx, [rsp+758h+Dst]; pszPath
0x18002fca0  call    cs:__imp_PathFileExistsW
0x18002fca6  test    eax, eax
0x18002fca8  jnz     short loc_18002FD17
0x18002fcaa  lea     rcx, [rsp+758h+var_728]
0x18002fcaf  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x18002fcb5  nop
0x18002fcb6  call    cs:__imp_GetLastError
0x18002fcbc  mov     edi, eax
0x18002fcbe  mov     r9d, eax
0x18002fcc1  mov     r8d, eax
0x18002fcc4  lea     rdx, aProfileCannotB; "Profile cannot be loaded since local NT"...
0x18002fccb  lea     rcx, [rsp+758h+var_728]
0x18002fcd0  call    cs:__imp_?Format@CHString@@QEAAXPEBGZZ; CHString::Format(ushort const *,...)
0x18002fcd6  lea     rcx, [rsp+758h+var_728]
0x18002fcdb  call    cs:__imp_??BCHString@@QEBAPEBGXZ; CHString::operator ushort const *(void)
0x18002fce1  mov     dword ptr [rsp+758h+phkResult], 1
0x18002fce9  mov     r9d, 237h
0x18002fcef  lea     r8, aOnecoreAdminWm_39; "onecore\\admin\\wmi\\wbem\\providers\\w"...
0x18002fcf6  mov     rdx, rax
0x18002fcf9  mov     rcx, cs:__imp_?captainsLog@@3VProviderLog@@A; ProviderLog captainsLog
0x18002fd00  call    cs:__imp_?LocalLogMessage@ProviderLog@@QEAAXPEBG0HW4LogLevel@1@@Z; ProviderLog::LocalLogMessage(ushort const *,ushort const *,int,ProviderLog::LogLevel)
0x18002fd06  nop
0x18002fd07  lea     rcx, [rsp+758h+var_728]
0x18002fd0c  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x18002fd12  jmp     loc_18002FB1F
0x18002fd17  or      edx, 0FFFFFFFFh
0x18002fd1a  lea     rcx, ?m_criticalSection@CUserHive@@0VCThreadBase@@A; CThreadBase CUserHive::m_criticalSection
0x18002fd21  call    cs:__imp_?BeginWrite@CThreadBase@@QEAAHK@Z; CThreadBase::BeginWrite(ulong)
0x18002fd27  nop
0x18002fd28  lea     r8, [rsp+758h+Dst]; lpFile
0x18002fd2d  mov     rdx, r15; lpSubKey
0x18002fd30  mov     rcx, r12; hKey
0x18002fd33  call    cs:__imp_RegLoadKeyW
0x18002fd39  mov     edi, eax
0x18002fd3b  mov     [rsp+758h+var_718], eax
0x18002fd3f  lea     rcx, ?m_criticalSection@CUserHive@@0VCThreadBase@@A; CThreadBase CUserHive::m_criticalSection
0x18002fd46  call    cs:__imp_?EndWrite@CThreadBase@@QEAAXXZ; CThreadBase::EndWrite(void)
0x18002fd4c  cmp     edi, 20h ; ' '
0x18002fd4f  jnz     loc_18002FB1F
0x18002fd55  inc     ebx
0x18002fd57  cmp     ebx, 0Bh
0x18002fd5a  jge     loc_18002FB1F
0x18002fd60  mov     dword ptr [rsp+758h+phkResult], 1
0x18002fd68  mov     r9d, 24Dh
0x18002fd6e  lea     r8, aOnecoreAdminWm_39; "onecore\\admin\\wmi\\wbem\\providers\\w"...
0x18002fd75  lea     rdx, aSharingViolati_0; "Sharing violation on NTUSER.DAT (LoadPr"...
0x18002fd7c  mov     rcx, cs:__imp_?captainsLog@@3VProviderLog@@A; ProviderLog captainsLog
0x18002fd83  call    cs:__imp_?LocalLogMessage@ProviderLog@@QEAAXPEBG0HW4LogLevel@1@@Z; ProviderLog::LocalLogMessage(ushort const *,ushort const *,int,ProviderLog::LogLevel)
0x18002fd89  lea     ecx, [rbx+rbx*4]
0x18002fd8c  shl     ecx, 2; dwMilliseconds
0x18002fd8f  call    cs:__imp_Sleep
0x18002fd95  jmp     loc_18002FC9B
```
