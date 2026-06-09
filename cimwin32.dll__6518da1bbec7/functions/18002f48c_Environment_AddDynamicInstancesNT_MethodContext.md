# Environment::AddDynamicInstancesNT(MethodContext *)

- ea: `0x18002f48c`
- end: `0x18002f88a`
- name: `?AddDynamicInstancesNT@Environment@@IEAAJPEAVMethodContext@@@Z`
- size: `1022`
- prototype: `__int64 __fastcall(Environment *__hidden this, struct MethodContext *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800a1200`

## callees

- `0x18001a298`
- `0x18002e910`
- `0x18002f48c`
- `0x180030a04`
- `0x180030c98`
- `0x1800311e8`
- `0x1800474a0`
- `0x1800676fc`
- `0x1800fc980`

## import_xrefs

- `msvcrt!wcschr` at `0x18002f65e`
- `msvcrt!wcschr` at `0x18002f65e`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18002f4d1`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18002f4d1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f855`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f855`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18002f4f7`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18002f4f7`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x18002f62e`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x18002f62e`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18002f567`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18002f639`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18002f567`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18002f639`
- `framedynos!?GetInstancesByQuery@CWbemProviderGlue@@SAJPEBGPEAV?$TRefPointerCollection@VCInstance@@@@PEAVMethodContext@@0@Z` at `0x18002f57f`
- `framedynos!?GetInstancesByQuery@CWbemProviderGlue@@SAJPEBGPEAV?$TRefPointerCollection@VCInstance@@@@PEAVMethodContext@@0@Z` at `0x18002f57f`
- `framedynos!?GetNamespace@Provider@@IEAAAEBVCHString@@XZ` at `0x18002f55e`
- `framedynos!?GetNamespace@Provider@@IEAAAEBVCHString@@XZ` at `0x18002f55e`
- `framedynos!??0CThreadBase@@QEAA@W4THREAD_SAFETY_MECHANISM@0@@Z` at `0x18002f531`
- `framedynos!??0CThreadBase@@QEAA@W4THREAD_SAFETY_MECHANISM@0@@Z` at `0x18002f531`
- `framedynos!??1CThreadBase@@UEAA@XZ` at `0x18002f81e`
- `framedynos!??1CThreadBase@@UEAA@XZ` at `0x18002f81e`
- `framedynos!??0CHPtrArray@@QEAA@XZ` at `0x18002f54c`
- `framedynos!??0CHPtrArray@@QEAA@XZ` at `0x18002f54c`
- `framedynos!??1CHPtrArray@@QEAA@XZ` at `0x18002f812`
- `framedynos!??1CHPtrArray@@QEAA@XZ` at `0x18002f812`
- `framedynos!?BeginRead@CThreadBase@@QEAAHK@Z` at `0x18002f5a1`
- `framedynos!?BeginRead@CThreadBase@@QEAAHK@Z` at `0x18002f5b9`
- `framedynos!?BeginRead@CThreadBase@@QEAAHK@Z` at `0x18002f776`
- `framedynos!?BeginRead@CThreadBase@@QEAAHK@Z` at `0x18002f5a1`
- `framedynos!?BeginRead@CThreadBase@@QEAAHK@Z` at `0x18002f5b9`
- `framedynos!?BeginRead@CThreadBase@@QEAAHK@Z` at `0x18002f776`
- `framedynos!?GetSize@CHPtrArray@@QEBAHXZ` at `0x18002f5ce`
- `framedynos!?GetSize@CHPtrArray@@QEBAHXZ` at `0x18002f78b`
- `framedynos!?GetSize@CHPtrArray@@QEBAHXZ` at `0x18002f5ce`
- `framedynos!?GetSize@CHPtrArray@@QEBAHXZ` at `0x18002f78b`
- `framedynos!?GetAt@CHPtrArray@@QEBAPEAXH@Z` at `0x18002f5e2`
- `framedynos!?GetAt@CHPtrArray@@QEBAPEAXH@Z` at `0x18002f7a1`
- `framedynos!?GetAt@CHPtrArray@@QEBAPEAXH@Z` at `0x18002f5e2`
- `framedynos!?GetAt@CHPtrArray@@QEBAPEAXH@Z` at `0x18002f7a1`
- `framedynos!?AddRef@CInstance@@QEAAJXZ` at `0x18002f5f3`
- `framedynos!?AddRef@CInstance@@QEAAJXZ` at `0x18002f7b2`
- `framedynos!?AddRef@CInstance@@QEAAJXZ` at `0x18002f5f3`
- `framedynos!?AddRef@CInstance@@QEAAJXZ` at `0x18002f7b2`
- `framedynos!?EndRead@CThreadBase@@QEAAXXZ` at `0x18002f5fe`
- `framedynos!?EndRead@CThreadBase@@QEAAXXZ` at `0x18002f7bd`
- `framedynos!?EndRead@CThreadBase@@QEAAXXZ` at `0x18002f7de`
- `framedynos!?EndRead@CThreadBase@@QEAAXXZ` at `0x18002f5fe`
- `framedynos!?EndRead@CThreadBase@@QEAAXXZ` at `0x18002f7bd`
- `framedynos!?EndRead@CThreadBase@@QEAAXXZ` at `0x18002f7de`
- `framedynos!?Release@CInstance@@QEAAJXZ` at `0x18002f7cb`
- `framedynos!?Release@CInstance@@QEAAJXZ` at `0x18002f7f3`
- `framedynos!?Release@CInstance@@QEAAJXZ` at `0x18002f7cb`
- `framedynos!?Release@CInstance@@QEAAJXZ` at `0x18002f7f3`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18002f82a`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18002f82a`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Environment::AddDynamicInstancesNT(Environment *this, struct MethodContext *a2)
{
  int EnvInstances; // edi
  const struct CHString *Namespace; // rax
  __int64 v6; // rax
  CInstance *v7; // rbx
  int v8; // r14d
  CInstance *v9; // rax
  const wchar_t *v10; // rax
  size_t *v11; // r8
  size_t *v12; // r8
  size_t *v13; // r8
  wchar_t *v14; // rax
  size_t v15; // rdx
  CInstance *v16; // rsi
  CInstance *v17; // rax
  size_t cchToCopy; // [rsp+20h] [rbp-838h]
  _BYTE v20[8]; // [rsp+38h] [rbp-820h] BYREF
  size_t v21; // [rsp+40h] [rbp-818h]
  CInstance *v22; // [rsp+48h] [rbp-810h]
  int v23; // [rsp+50h] [rbp-808h]
  wchar_t *v24; // [rsp+58h] [rbp-800h]
  __int64 v25; // [rsp+60h] [rbp-7F8h]
  _QWORD v26[7]; // [rsp+70h] [rbp-7E8h] BYREF
  _BYTE v27[24]; // [rsp+A8h] [rbp-7B0h] BYREF
  struct _OSVERSIONINFOW VersionInformation; // [rsp+C0h] [rbp-798h] BYREF
  __int64 v29; // [rsp+1D8h] [rbp-680h]
  HKEY hKey; // [rsp+1E0h] [rbp-678h]
  int v31; // [rsp+1E8h] [rbp-670h]
  WCHAR pszSrc[264]; // [rsp+1F0h] [rbp-668h] BYREF
  wchar_t pszDest[264]; // [rsp+400h] [rbp-458h] BYREF
  wchar_t SubKey[264]; // [rsp+610h] [rbp-248h] BYREF

  VersionInformation.dwOSVersionInfoSize = 276;
  GetVersionExW(&VersionInformation);
  v29 = 0;
  v31 = 0;
  hKey = 0;
  CHString::CHString((CHString *)v20);
  EnvInstances = Environment::CreateEnvInstances(
                   this,
                   a2,
                   L"<SYSTEM>",
                   HKEY_LOCAL_MACHINE,
                   (LPCWSTR)L"System\\CurrentControlSet\\Control\\Session Manager\\Environment",
                   1);
  CThreadBase::CThreadBase(v26, 0);
  v26[0] = &TRefPointerCollection<CInstance>::`vftable';
  CHPtrArray::CHPtrArray((CHPtrArray *)v27);
  if ( EnvInstances >= 0 )
  {
    Namespace = Provider::GetNamespace(this);
    v6 = CHString::operator unsigned short const *(Namespace);
    EnvInstances = CWbemProviderGlue::GetInstancesByQuery(L"SELECT Name FROM Win32_Desktop", v26, a2, v6);
    if ( EnvInstances >= 0 )
    {
      v7 = 0;
      v22 = 0;
      if ( CThreadBase::BeginRead((CThreadBase *)v26, 0xFFFFFFFF) )
      {
        v8 = -1;
        if ( CThreadBase::BeginRead((CThreadBase *)v26, 0xFFFFFFFF) )
        {
          v8 = 0;
          if ( CHPtrArray::GetSize((CHPtrArray *)v27) )
          {
            v9 = (CInstance *)CHPtrArray::GetAt((CHPtrArray *)v27, 0);
            v7 = v9;
            if ( v9 )
              CInstance::AddRef(v9);
          }
          CThreadBase::EndRead((CThreadBase *)v26);
        }
        while ( 1 )
        {
          v22 = v7;
          if ( EnvInstances < 0 || !v7 )
            break;
          CInstance::GetCHString(v7, L"Name", (struct CHString *)v20);
          v10 = (const wchar_t *)CHString::operator unsigned short const *(v20);
          StringCopyWorkerW(pszDest, 0x104u, v11, v10, cchToCopy);
          if ( wcschr(pszDest, 0x5Cu)
            && !(unsigned int)CUserHive::LoadNT(&VersionInformation.dwOSVersionInfoSize, pszDest, pszSrc, 0x104u) )
          {
            try
            {
              StringCopyWorkerW(SubKey, 0x104u, v12, pszSrc, cchToCopy);
              v21 = 0;
              v15 = 260;
              v25 = 260;
              v14 = pszSrc;
              v24 = pszSrc;
              while ( v15 )
              {
                if ( !*v14 )
                {
                  v21 = 260 - v15;
                  StringCopyWorkerW_0(&pszSrc[260 - v15], v15, v13, L"\\Environment", 0x7FFFFFFEu);
                  goto LABEL_19;
                }
                v24 = ++v14;
                v25 = --v15;
              }
              v21 = 0;
LABEL_19:
              EnvInstances = Environment::CreateEnvInstances(this, a2, pszDest, HKEY_USERS, pszSrc, 0);
              v23 = EnvInstances;
            }
            catch ( ... )
            {
              CUserHive::Unload((CUserHive *)&VersionInformation, SubKey);
              throw;
            }
            CUserHive::Unload((CUserHive *)&VersionInformation, SubKey);
          }
          v16 = 0;
          if ( CThreadBase::BeginRead((CThreadBase *)v26, 0xFFFFFFFF) )
          {
            if ( (unsigned int)++v8 < CHPtrArray::GetSize((CHPtrArray *)v27) )
            {
              v17 = (CInstance *)CHPtrArray::GetAt((CHPtrArray *)v27, v8);
              v16 = v17;
              if ( v17 )
                CInstance::AddRef(v17);
            }
            CThreadBase::EndRead((CThreadBase *)v26);
          }
          CInstance::Release(v7);
          v7 = v16;
        }
        CThreadBase::EndRead((CThreadBase *)v26);
      }
      if ( v7 )
        CInstance::Release(v7);
    }
  }
  v26[0] = &TRefPointerCollection<CInstance>::`vftable';
  TRefPointerCollection<CInstance>::Empty(v26);
  CHPtrArray::~CHPtrArray((CHPtrArray *)v27);
  CThreadBase::~CThreadBase((CThreadBase *)v26);
  CHString::~CHString((CHString *)v20);
  if ( v29 )
    CUserHive::RestorePrivilege((CUserHive *)&VersionInformation);
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)EnvInstances;
}

```

## disassembly

```asm
0x18002f48c  mov     [rsp+arg_10], rbx
0x18002f491  mov     [rsp+arg_18], rsi
0x18002f496  push    rdi
0x18002f497  push    r12
0x18002f499  push    r13
0x18002f49b  push    r14
0x18002f49d  push    r15
0x18002f49f  sub     rsp, 830h
0x18002f4a6  mov     rax, cs:__security_cookie
0x18002f4ad  xor     rax, rsp
0x18002f4b0  mov     [rsp+858h+var_38], rax
0x18002f4b8  mov     r12, rdx
0x18002f4bb  mov     r15, rcx
0x18002f4be  mov     [rsp+858h+VersionInformation.dwOSVersionInfoSize], 114h
0x18002f4c9  lea     rcx, [rsp+858h+VersionInformation]; lpVersionInformation
0x18002f4d1  call    cs:__imp_GetVersionExW
0x18002f4d7  xor     r13d, r13d
0x18002f4da  mov     [rsp+858h+var_680], r13
0x18002f4e2  mov     [rsp+858h+var_670], r13d
0x18002f4ea  mov     [rsp+858h+hKey], r13
0x18002f4f2  lea     rcx, [rsp+858h+var_820]
0x18002f4f7  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x18002f4fd  nop
0x18002f4fe  mov     [rsp+858h+var_830], 1; bool
0x18002f503  lea     rax, cchToCopy; "System\\CurrentControlSet\\Control\\Ses"...
0x18002f50a  mov     [rsp+858h+cchToCopy], rax; lpSubKey
0x18002f50f  mov     r9, 0FFFFFFFF80000002h; HKEY
0x18002f516  lea     r8, aSystem; "<SYSTEM>"
0x18002f51d  mov     rdx, r12; struct MethodContext *
0x18002f520  mov     rcx, r15; this
0x18002f523  call    ?CreateEnvInstances@Environment@@IEAAJPEAVMethodContext@@PEBGPEAUHKEY__@@1_N@Z; Environment::CreateEnvInstances(MethodContext *,ushort const *,HKEY__ *,ushort const *,bool)
0x18002f528  mov     edi, eax
0x18002f52a  xor     edx, edx
0x18002f52c  lea     rcx, [rsp+858h+var_7E8]
0x18002f531  call    cs:__imp_??0CThreadBase@@QEAA@W4THREAD_SAFETY_MECHANISM@0@@Z; CThreadBase::CThreadBase(CThreadBase::THREAD_SAFETY_MECHANISM)
0x18002f537  nop
0x18002f538  lea     r14, ??_7?$TRefPointerCollection@VCInstance@@@@6B@; const TRefPointerCollection<CInstance>::`vftable'
0x18002f53f  mov     [rsp+858h+var_7E8], r14
0x18002f544  lea     rcx, [rsp+858h+var_7B0]
0x18002f54c  call    cs:__imp_??0CHPtrArray@@QEAA@XZ; CHPtrArray::CHPtrArray(void)
0x18002f552  nop
0x18002f553  test    edi, edi
0x18002f555  js      loc_18002F7FA
0x18002f55b  mov     rcx, r15
0x18002f55e  call    cs:__imp_?GetNamespace@Provider@@IEAAAEBVCHString@@XZ; Provider::GetNamespace(void)
0x18002f564  mov     rcx, rax
0x18002f567  call    cs:__imp_??BCHString@@QEBAPEBGXZ; CHString::operator ushort const *(void)
0x18002f56d  mov     r9, rax
0x18002f570  mov     r8, r12
0x18002f573  lea     rdx, [rsp+858h+var_7E8]
0x18002f578  lea     rcx, aSelectNameFrom_2; "SELECT Name FROM Win32_Desktop"
0x18002f57f  call    cs:__imp_?GetInstancesByQuery@CWbemProviderGlue@@SAJPEBGPEAV?$TRefPointerCollection@VCInstance@@@@PEAVMethodContext@@0@Z; CWbemProviderGlue::GetInstancesByQuery(ushort const *,TRefPointerCollection<CInstance> *,MethodContext *,ushort const *)
0x18002f585  mov     edi, eax
0x18002f587  test    eax, eax
0x18002f589  js      loc_18002F7FA
0x18002f58f  mov     ebx, r13d
0x18002f592  mov     [rsp+858h+var_810], rbx
0x18002f597  or      esi, 0FFFFFFFFh
0x18002f59a  mov     edx, esi
0x18002f59c  lea     rcx, [rsp+858h+var_7E8]
0x18002f5a1  call    cs:__imp_?BeginRead@CThreadBase@@QEAAHK@Z; CThreadBase::BeginRead(ulong)
0x18002f5a7  test    eax, eax
0x18002f5a9  jz      loc_18002F7EB
0x18002f5af  mov     r14d, esi
0x18002f5b2  mov     edx, esi
0x18002f5b4  lea     rcx, [rsp+858h+var_7E8]
0x18002f5b9  call    cs:__imp_?BeginRead@CThreadBase@@QEAAHK@Z; CThreadBase::BeginRead(ulong)
0x18002f5bf  test    eax, eax
0x18002f5c1  jz      short loc_18002F604
0x18002f5c3  mov     r14d, r13d
0x18002f5c6  lea     rcx, [rsp+858h+var_7B0]
0x18002f5ce  call    cs:__imp_?GetSize@CHPtrArray@@QEBAHXZ; CHPtrArray::GetSize(void)
0x18002f5d4  test    eax, eax
0x18002f5d6  jz      short loc_18002F5F9
0x18002f5d8  xor     edx, edx
0x18002f5da  lea     rcx, [rsp+858h+var_7B0]
0x18002f5e2  call    cs:__imp_?GetAt@CHPtrArray@@QEBAPEAXH@Z; CHPtrArray::GetAt(int)
0x18002f5e8  mov     rbx, rax
0x18002f5eb  test    rax, rax
0x18002f5ee  jz      short loc_18002F5F9
0x18002f5f0  mov     rcx, rax
0x18002f5f3  call    cs:__imp_?AddRef@CInstance@@QEAAJXZ; CInstance::AddRef(void)
0x18002f5f9  lea     rcx, [rsp+858h+var_7E8]
0x18002f5fe  call    cs:__imp_?EndRead@CThreadBase@@QEAAXXZ; CThreadBase::EndRead(void)
0x18002f604  mov     esi, 104h
0x18002f609  mov     [rsp+858h+var_810], rbx
0x18002f60e  test    edi, edi
0x18002f610  js      loc_18002F7D9
0x18002f616  test    rbx, rbx
0x18002f619  jz      loc_18002F7D9
0x18002f61f  lea     r8, [rsp+858h+var_820]
0x18002f624  lea     rdx, aName; "Name"
0x18002f62b  mov     rcx, rbx
0x18002f62e  call    cs:__imp_?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z; CInstance::GetCHString(ushort const *,CHString &)
0x18002f634  lea     rcx, [rsp+858h+var_820]
0x18002f639  call    cs:__imp_??BCHString@@QEBAPEBGXZ; CHString::operator ushort const *(void)
0x18002f63f  mov     r9, rax; pszSrc
0x18002f642  mov     edx, esi; cchDest
0x18002f644  lea     rcx, [rsp+858h+pszDest]; pszDest
0x18002f64c  call    StringCopyWorkerW
0x18002f651  mov     edx, 5Ch ; '\'; Ch
0x18002f656  lea     rcx, [rsp+858h+pszDest]; Str
0x18002f65e  call    cs:__imp_wcschr
0x18002f664  test    rax, rax
0x18002f667  jz      loc_18002F76B
0x18002f66d  mov     r9d, esi; unsigned __int64
0x18002f670  lea     r8, [rsp+858h+pszSrc]; unsigned __int16 *
0x18002f678  lea     rdx, [rsp+858h+pszDest]; lpAccountName
0x18002f680  lea     rcx, [rsp+858h+VersionInformation]; this
0x18002f688  call    ?LoadNT@CUserHive@@AEAAKPEBGPEAG_K@Z; CUserHive::LoadNT(ushort const *,ushort *,unsigned __int64)
0x18002f68d  test    eax, eax
0x18002f68f  jnz     loc_18002F76B
0x18002f695  mov     [rsp+858h+var_824], r13d
0x18002f69a  mov     [rsp+858h+var_824], r13d
0x18002f69f  lea     r9, [rsp+858h+pszSrc]; pszSrc
0x18002f6a7  mov     edx, esi; cchDest
0x18002f6a9  lea     rcx, [rsp+858h+SubKey]; pszDest
0x18002f6b1  call    StringCopyWorkerW
0x18002f6b6  mov     [rsp+858h+var_824], eax
0x18002f6ba  mov     [rsp+858h+var_818], r13
0x18002f6bf  mov     edx, esi; cchDest
0x18002f6c1  mov     [rsp+858h+var_7F8], rdx
0x18002f6c6  lea     rax, [rsp+858h+pszSrc]
0x18002f6ce  mov     [rsp+858h+var_800], rax
0x18002f6d3  test    rdx, rdx
0x18002f6d6  jz      short loc_18002F71F
0x18002f6d8  cmp     [rax], r13w
0x18002f6dc  jz      short loc_18002F6F1
0x18002f6de  add     rax, 2
0x18002f6e2  mov     [rsp+858h+var_800], rax
0x18002f6e7  dec     rdx
0x18002f6ea  mov     [rsp+858h+var_7F8], rdx
0x18002f6ef  jmp     short loc_18002F6D3
0x18002f6f1  mov     rax, rsi
0x18002f6f4  sub     rax, rdx
0x18002f6f7  mov     [rsp+858h+var_818], rax
0x18002f6fc  lea     rcx, [rsp+858h+pszSrc]
0x18002f704  lea     rcx, [rcx+rax*2]; pszDest
0x18002f708  mov     [rsp+858h+cchToCopy], 7FFFFFFEh; cchToCopy
0x18002f711  lea     r9, aEnvironment; "\\Environment"
0x18002f718  call    StringCopyWorkerW_0
0x18002f71d  jmp     short loc_18002F724
0x18002f71f  mov     [rsp+858h+var_818], r13
0x18002f724  mov     [rsp+858h+var_830], r13b; bool
0x18002f729  lea     rax, [rsp+858h+pszSrc]
0x18002f731  mov     [rsp+858h+cchToCopy], rax; lpSubKey
0x18002f736  mov     r9, 0FFFFFFFF80000003h; HKEY
0x18002f73d  lea     r8, [rsp+858h+pszDest]; unsigned __int16 *
0x18002f745  mov     rdx, r12; struct MethodContext *
0x18002f748  mov     rcx, r15; this
0x18002f74b  call    ?CreateEnvInstances@Environment@@IEAAJPEAVMethodContext@@PEBGPEAUHKEY__@@1_N@Z; Environment::CreateEnvInstances(MethodContext *,ushort const *,HKEY__ *,ushort const *,bool)
0x18002f750  mov     edi, eax
0x18002f752  mov     [rsp+858h+var_808], eax
0x18002f756  lea     rdx, [rsp+858h+SubKey]; lpSubKey
0x18002f75e  lea     rcx, [rsp+858h+VersionInformation]; this
0x18002f766  call    ?Unload@CUserHive@@QEAAKPEBG@Z; CUserHive::Unload(ushort const *)
0x18002f76b  mov     rsi, r13
0x18002f76e  or      edx, 0FFFFFFFFh
0x18002f771  lea     rcx, [rsp+858h+var_7E8]
0x18002f776  call    cs:__imp_?BeginRead@CThreadBase@@QEAAHK@Z; CThreadBase::BeginRead(ulong)
0x18002f77c  test    eax, eax
0x18002f77e  jz      short loc_18002F7C3
0x18002f780  inc     r14d
0x18002f783  lea     rcx, [rsp+858h+var_7B0]
0x18002f78b  call    cs:__imp_?GetSize@CHPtrArray@@QEBAHXZ; CHPtrArray::GetSize(void)
0x18002f791  cmp     r14d, eax
0x18002f794  jnb     short loc_18002F7B8
0x18002f796  mov     edx, r14d
0x18002f799  lea     rcx, [rsp+858h+var_7B0]
0x18002f7a1  call    cs:__imp_?GetAt@CHPtrArray@@QEBAPEAXH@Z; CHPtrArray::GetAt(int)
0x18002f7a7  mov     rsi, rax
0x18002f7aa  test    rax, rax
0x18002f7ad  jz      short loc_18002F7B8
0x18002f7af  mov     rcx, rax
0x18002f7b2  call    cs:__imp_?AddRef@CInstance@@QEAAJXZ; CInstance::AddRef(void)
0x18002f7b8  lea     rcx, [rsp+858h+var_7E8]
0x18002f7bd  call    cs:__imp_?EndRead@CThreadBase@@QEAAXXZ; CThreadBase::EndRead(void)
0x18002f7c3  test    rbx, rbx
0x18002f7c6  jz      short loc_18002F7D1
0x18002f7c8  mov     rcx, rbx
0x18002f7cb  call    cs:__imp_?Release@CInstance@@QEAAJXZ; CInstance::Release(void)
0x18002f7d1  mov     rbx, rsi
0x18002f7d4  jmp     loc_18002F604
0x18002f7d9  lea     rcx, [rsp+858h+var_7E8]
0x18002f7de  call    cs:__imp_?EndRead@CThreadBase@@QEAAXXZ; CThreadBase::EndRead(void)
0x18002f7e4  lea     r14, ??_7?$TRefPointerCollection@VCInstance@@@@6B@; const TRefPointerCollection<CInstance>::`vftable'
0x18002f7eb  test    rbx, rbx
0x18002f7ee  jz      short loc_18002F7FA
0x18002f7f0  mov     rcx, rbx
0x18002f7f3  call    cs:__imp_?Release@CInstance@@QEAAJXZ; CInstance::Release(void)
0x18002f7f9  nop
0x18002f7fa  mov     [rsp+858h+var_7E8], r14
0x18002f7ff  lea     rcx, [rsp+858h+var_7E8]
0x18002f804  call    ?Empty@?$TRefPointerCollection@VCInstance@@@@QEAAXXZ; TRefPointerCollection<CInstance>::Empty(void)
0x18002f809  nop
0x18002f80a  lea     rcx, [rsp+858h+var_7B0]
0x18002f812  call    cs:__imp_??1CHPtrArray@@QEAA@XZ; CHPtrArray::~CHPtrArray(void)
0x18002f818  nop
0x18002f819  lea     rcx, [rsp+858h+var_7E8]
0x18002f81e  call    cs:__imp_??1CThreadBase@@UEAA@XZ; CThreadBase::~CThreadBase(void)
0x18002f824  nop
0x18002f825  lea     rcx, [rsp+858h+var_820]
0x18002f82a  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x18002f830  nop
0x18002f831  cmp     [rsp+858h+var_680], r13
0x18002f839  jz      short loc_18002F848
0x18002f83b  lea     rcx, [rsp+858h+VersionInformation]; this
0x18002f843  call    ?RestorePrivilege@CUserHive@@AEAAXXZ; CUserHive::RestorePrivilege(void)
0x18002f848  mov     rcx, [rsp+858h+hKey]; hKey
0x18002f850  test    rcx, rcx
0x18002f853  jz      short loc_18002F85B
0x18002f855  call    cs:__imp_RegCloseKey
0x18002f85b  mov     eax, edi
0x18002f85d  mov     rcx, [rsp+858h+var_38]
0x18002f865  xor     rcx, rsp; StackCookie
0x18002f868  call    __security_check_cookie
0x18002f86d  lea     r11, [rsp+858h+var_28]
0x18002f875  mov     rbx, [r11+40h]
0x18002f879  mov     rsi, [r11+48h]
0x18002f87d  mov     rsp, r11
0x18002f880  pop     r15
0x18002f882  pop     r14
0x18002f884  pop     r13
0x18002f886  pop     r12
0x18002f888  pop     rdi
0x18002f889  retn
```
