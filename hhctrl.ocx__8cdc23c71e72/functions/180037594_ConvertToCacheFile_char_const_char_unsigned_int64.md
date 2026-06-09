# ConvertToCacheFile(char const *,char *,unsigned __int64)

- ea: `0x180037594`
- end: `0x1800378fa`
- name: `?ConvertToCacheFile@@YAHPEBDPEAD_K@Z`
- size: `870`
- prototype: `__int64 __fastcall(const char *, char *, unsigned __int64)`
- caller_count: `6`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800197c8`
- `0x18001dd04`
- `0x18004feb4`
- `0x180050a70`
- `0x180056b00`
- `0x18006c9d0`

## callees

- `0x1800029b8`
- `0x180003fc0`
- `0x180004224`
- `0x1800095c8`
- `0x1800269d0`
- `0x180037594`
- `0x18004eea0`
- `0x18004f65c`
- `0x180051e98`
- `0x180063bd8`
- `0x180065230`
- `0x180065310`
- `0x1800678a0`
- `0x180068090`
- `0x180068a30`
- `0x180069b90`
- `0x18006ac20`
- `0x180075c90`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180037602`
- `KERNEL32!LeaveCriticalSection` at `0x180037602`
- `KERNEL32!EnterCriticalSection` at `0x1800375db`
- `KERNEL32!EnterCriticalSection` at `0x1800375db`
- `SHLWAPI!StrStrA` at `0x18003776b`
- `SHLWAPI!StrStrA` at `0x18003776b`
- `urlmon!URLDownloadToCacheFileA` at `0x18003780e`
- `urlmon!URLDownloadToCacheFileA` at `0x1800378ee`
- `urlmon!URLDownloadToCacheFileA` at `0x18003780e`
- `urlmon!URLDownloadToCacheFileA` at `0x1800378ee`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ConvertToCacheFile(const char *a1, char *a2, unsigned __int64 a3)
{
  const CHAR *v5; // rdi
  HHUrlSecurityManager::InternalSecurityManager *v7; // rcx
  unsigned int v8; // esi
  const CHAR *v9; // rbx
  __int64 v10; // r15
  HWND v11; // rcx
  CExCollection *CurrentCollection; // rax
  struct CExTitle *v13; // r15
  char *v14; // rax
  char *v15; // rcx
  const char *v16; // r8
  HRESULT v17; // eax
  __int64 v18; // rcx
  PSTR v19; // r15
  int v20; // r15d
  unsigned __int16 v21; // r8
  unsigned __int16 v22; // r8
  struct CExTitle *v23; // [rsp+30h] [rbp-D0h] BYREF
  const CHAR *v24; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v25[48]; // [rsp+40h] [rbp-C0h] BYREF
  char *v26; // [rsp+70h] [rbp-90h]
  BYTE Data[272]; // [rsp+90h] [rbp-70h] BYREF

  v5 = a1;
  if ( !a1 )
    return 0;
  EnterCriticalSection(&CriticalSection);
  v8 = 1;
  if ( !byte_18008C2E4 )
  {
    HHUrlSecurityManager::InternalSecurityManager::ReadRegistryData(v7);
    byte_18008C2E4 = 1;
  }
  LeaveCriticalSection(&CriticalSection);
  v9 = 0;
  v24 = 0;
  v10 = HHStrStrIA(v5, "%SystemRoot%");
  if ( v10 )
  {
    HHGetWindowsDirectory(Data, 0x104u, 0);
    StringCchCatA((char *)Data, 0x104u, (const char *)(v10 + 12));
    CStr::operator=(&v24);
    v9 = v24;
    v5 = v24;
  }
  if ( !(unsigned int)IsCompiledURL(v5) )
    goto LABEL_24;
  if ( StringCchCopyA(a2, a3, v5) < 0 )
  {
LABEL_22:
    v8 = 0;
    goto LABEL_23;
  }
  if ( GetURLType(a2) == 2 )
  {
    v23 = 0;
    CurrentCollection = GetCurrentCollection(v11, a2);
    if ( CurrentCollection )
    {
      if ( CExCollection::URL2ExTitle(CurrentCollection, a2, &v23) >= 0 )
      {
        v13 = v23;
        if ( v23 )
        {
          v14 = (char *)HHStrStrIA(a2, "::");
          if ( v14 )
          {
            while ( 1 )
            {
              v15 = v14--;
              if ( *v14 == 58 )
                break;
              if ( v14 == a2 )
                goto LABEL_18;
            }
            *v15 = 0;
LABEL_18:
            if ( (int)StringCchCatA(a2, a3, *((const char **)v13 + 7)) < 0 )
              goto LABEL_22;
            v16 = (const char *)HHStrStrIA(v5, "::");
            goto LABEL_20;
          }
        }
      }
    }
LABEL_24:
    v19 = StrStrA(v5, "::");
    if ( v19 )
    {
      if ( v5 != v9 )
      {
        CStr::operator=(&v24);
        v20 = (_DWORD)v19 - (_DWORD)v5;
        v5 = v24;
        v19 = (PSTR)&v24[v20];
      }
      *v19 = 0;
      if ( (unsigned __int8)HHUrlSecurityManager::IsUrlUnSafe(v18, 1, v5, 0) )
      {
        HHEventManager::HHEventManager((HHEventManager *)v25);
        HHEventManager::HHReportEvent((HHEventManager *)v25, 0x771u, v21, v5, v26);
        HHEventManager::~HHEventManager((HHEventManager *)v25);
        CWStr::~CWStr((CWStr *)&v24);
        return 0;
      }
      if ( URLDownloadToCacheFileA(0, v5, a2, a3, 0, 0) >= 0 )
      {
        *v19 = 58;
        v16 = v19;
LABEL_20:
        v17 = StringCchCatA(a2, a3, v16);
        goto LABEL_21;
      }
      v23 = 0;
      if ( (unsigned int)FindThisFile(0, v5, (struct CStr *)&v23, 0) )
      {
        if ( StringCchCopyA(a2, a3, (const char *)v23) < 0 || (*v19 = 58, (int)StringCchCatA(a2, a3, v19) < 0) )
          v8 = 0;
        CWStr::~CWStr((CWStr *)&v23);
        goto LABEL_23;
      }
      CWStr::~CWStr((CWStr *)&v23);
    }
    if ( (unsigned __int8)HHUrlSecurityManager::IsUrlUnSafe(v18, 1, v5, 0) )
    {
      HHEventManager::HHEventManager((HHEventManager *)v25);
      HHEventManager::HHReportEvent((HHEventManager *)v25, 0x771u, v22, v5, v26);
      HHEventManager::~HHEventManager((HHEventManager *)v25);
      goto LABEL_22;
    }
    v17 = URLDownloadToCacheFileA(0, v5, a2, a3, 0, 0);
LABEL_21:
    if ( v17 < 0 )
      goto LABEL_22;
  }
LABEL_23:
  CWStr::~CWStr((CWStr *)&v24);
  return v8;
}

```

## disassembly

```asm
0x180037594  push    rbp
0x180037596  push    rbx
0x180037597  push    rsi
0x180037598  push    rdi
0x180037599  push    r12
0x18003759b  push    r14
0x18003759d  push    r15
0x18003759f  lea     rbp, [rsp-0B0h]
0x1800375a7  sub     rsp, 1B0h
0x1800375ae  mov     rax, cs:__security_cookie
0x1800375b5  xor     rax, rsp
0x1800375b8  mov     [rbp+0E0h+var_40], rax
0x1800375bf  mov     r12, r8
0x1800375c2  mov     r14, rdx
0x1800375c5  mov     rdi, rcx
0x1800375c8  test    rcx, rcx
0x1800375cb  jnz     short loc_1800375D4
0x1800375cd  xor     eax, eax
0x1800375cf  jmp     loc_180037740
0x1800375d4  lea     rcx, CriticalSection; lpCriticalSection
0x1800375db  call    cs:__imp_EnterCriticalSection
0x1800375e1  mov     esi, 1
0x1800375e6  cmp     cs:byte_18008C2E4, 0
0x1800375ed  jnz     short loc_1800375FB
0x1800375ef  call    ?ReadRegistryData@InternalSecurityManager@HHUrlSecurityManager@@AEAAXXZ; HHUrlSecurityManager::InternalSecurityManager::ReadRegistryData(void)
0x1800375f4  mov     cs:byte_18008C2E4, sil
0x1800375fb  lea     rcx, CriticalSection; lpCriticalSection
0x180037602  call    cs:__imp_LeaveCriticalSection
0x180037608  xor     ebx, ebx
0x18003760a  mov     [rsp+1E0h+var_1A8], rbx
0x18003760f  lea     rdx, ?txtSysRoot@@3QBDB; "%SystemRoot%"
0x180037616  mov     rcx, rdi; pszStart
0x180037619  call    HHStrStrIA
0x18003761e  mov     r15, rax
0x180037621  test    rax, rax
0x180037624  jz      short loc_18003765E
0x180037626  xor     r8d, r8d; unsigned int
0x180037629  mov     ebx, 104h
0x18003762e  mov     edx, ebx; unsigned __int64
0x180037630  lea     rcx, [rbp+0E0h+Data]; lpData
0x180037634  call    ?HHGetWindowsDirectory@@YAKPEAD_KI@Z; HHGetWindowsDirectory(char *,unsigned __int64,uint)
0x180037639  lea     r8, [r15+0Ch]; char *
0x18003763d  mov     edx, ebx; unsigned __int64
0x18003763f  lea     rcx, [rbp+0E0h+Data]; char *
0x180037643  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x180037648  lea     rdx, [rbp+0E0h+Data]
0x18003764c  lea     rcx, [rsp+1E0h+var_1A8]
0x180037651  call    ??4CStr@@QEAAXPEBD@Z; CStr::operator=(char const *)
0x180037656  mov     rbx, [rsp+1E0h+var_1A8]
0x18003765b  mov     rdi, rbx
0x18003765e  mov     rcx, rdi; char *
0x180037661  call    ?IsCompiledURL@@YAHPEBD@Z; IsCompiledURL(char const *)
0x180037666  test    eax, eax
0x180037668  jz      loc_180037761
0x18003766e  mov     r8, rdi; char *
0x180037671  mov     rdx, r12; unsigned __int64
0x180037674  mov     rcx, r14; char *
0x180037677  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18003767c  test    eax, eax
0x18003767e  js      loc_180037732
0x180037684  mov     rcx, r14; pszStart
0x180037687  call    ?GetURLType@@YAIPEBD@Z; GetURLType(char const *)
0x18003768c  cmp     eax, 2
0x18003768f  jnz     loc_180037734
0x180037695  mov     [rsp+1E0h+var_1B0], 0
0x18003769e  mov     rdx, r14; char *
0x1800376a1  call    ?GetCurrentCollection@@YAPEAVCExCollection@@PEAUHWND__@@PEBD@Z; GetCurrentCollection(HWND__ *,char const *)
0x1800376a6  test    rax, rax
0x1800376a9  jz      loc_180037761
0x1800376af  lea     r8, [rsp+1E0h+var_1B0]; struct CExTitle **
0x1800376b4  mov     rdx, r14; char *
0x1800376b7  mov     rcx, rax; this
0x1800376ba  call    ?URL2ExTitle@CExCollection@@QEAAJPEBDPEAPEAVCExTitle@@@Z; CExCollection::URL2ExTitle(char const *,CExTitle * *)
0x1800376bf  test    eax, eax
0x1800376c1  js      loc_180037761
0x1800376c7  mov     r15, [rsp+1E0h+var_1B0]
0x1800376cc  test    r15, r15
0x1800376cf  jz      loc_180037761
0x1800376d5  lea     rdx, ?txtDoubleColonSep@@3QBDB; "::"
0x1800376dc  mov     rcx, r14; pszStart
0x1800376df  call    HHStrStrIA
0x1800376e4  test    rax, rax
0x1800376e7  jz      short loc_180037761
0x1800376e9  mov     rcx, rax
0x1800376ec  sub     rax, rsi
0x1800376ef  cmp     byte ptr [rax], 3Ah ; ':'
0x1800376f2  jz      short loc_1800376FB
0x1800376f4  cmp     rax, r14
0x1800376f7  jnz     short loc_1800376E9
0x1800376f9  jmp     short loc_1800376FE
0x1800376fb  mov     byte ptr [rcx], 0
0x1800376fe  mov     r8, [r15+38h]; char *
0x180037702  mov     rdx, r12; unsigned __int64
0x180037705  mov     rcx, r14; char *
0x180037708  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x18003770d  test    eax, eax
0x18003770f  js      short loc_180037732
0x180037711  lea     rdx, ?txtDoubleColonSep@@3QBDB; "::"
0x180037718  mov     rcx, rdi; pszStart
0x18003771b  call    HHStrStrIA
0x180037720  mov     r8, rax; char *
0x180037723  mov     rdx, r12; unsigned __int64
0x180037726  mov     rcx, r14; char *
0x180037729  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x18003772e  test    eax, eax
0x180037730  jns     short loc_180037734
0x180037732  xor     esi, esi
0x180037734  lea     rcx, [rsp+1E0h+var_1A8]; this
0x180037739  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x18003773e  mov     eax, esi
0x180037740  mov     rcx, [rbp+0E0h+var_40]
0x180037747  xor     rcx, rsp; StackCookie
0x18003774a  call    __security_check_cookie
0x18003774f  add     rsp, 1B0h
0x180037756  pop     r15
0x180037758  pop     r14
0x18003775a  pop     r12
0x18003775c  pop     rdi
0x18003775d  pop     rsi
0x18003775e  pop     rbx
0x18003775f  pop     rbp
0x180037760  retn
0x180037761  lea     rdx, ?txtDoubleColonSep@@3QBDB; "::"
0x180037768  mov     rcx, rdi; pszFirst
0x18003776b  call    cs:__imp_StrStrA
0x180037771  mov     r15, rax
0x180037774  test    rax, rax
0x180037777  jz      loc_180037880
0x18003777d  cmp     rdi, rbx
0x180037780  jz      short loc_18003779D
0x180037782  mov     rdx, rdi
0x180037785  lea     rcx, [rsp+1E0h+var_1A8]
0x18003778a  call    ??4CStr@@QEAAXPEBD@Z; CStr::operator=(char const *)
0x18003778f  sub     r15d, edi
0x180037792  mov     rdi, [rsp+1E0h+var_1A8]
0x180037797  movsxd  r15, r15d
0x18003779a  add     r15, rdi
0x18003779d  mov     byte ptr [r15], 0
0x1800377a1  xor     r9d, r9d
0x1800377a4  mov     r8, rdi
0x1800377a7  mov     edx, esi
0x1800377a9  call    ?IsUrlUnSafe@HHUrlSecurityManager@@QEAA_NW4SAFEURLTYPE@1@PEBDPEAVCHtmlHelpControl@@@Z; HHUrlSecurityManager::IsUrlUnSafe(HHUrlSecurityManager::SAFEURLTYPE,char const *,CHtmlHelpControl *)
0x1800377ae  test    al, al
0x1800377b0  jz      short loc_1800377F2
0x1800377b2  lea     rcx, [rsp+1E0h+var_1A0]; this
0x1800377b7  call    ??0HHEventManager@@QEAA@XZ; HHEventManager::HHEventManager(void)
0x1800377bc  mov     rax, [rsp+1E0h+var_170]
0x1800377c1  mov     qword ptr [rsp+1E0h+var_1C0], rax; char *
0x1800377c6  mov     r9, rdi; char *
0x1800377c9  mov     edx, 771h; unsigned int
0x1800377ce  lea     rcx, [rsp+1E0h+var_1A0]; this
0x1800377d3  call    ?HHReportEvent@HHEventManager@@QEAAXKGPEBD0@Z; HHEventManager::HHReportEvent(ulong,ushort,char const *,char const *)
0x1800377d8  lea     rcx, [rsp+1E0h+var_1A0]; this
0x1800377dd  call    ??1HHEventManager@@QEAA@XZ; HHEventManager::~HHEventManager(void)
0x1800377e2  nop
0x1800377e3  lea     rcx, [rsp+1E0h+var_1A8]; this
0x1800377e8  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x1800377ed  jmp     loc_1800375CD
0x1800377f2  mov     r9d, r12d; cchFileName
0x1800377f5  mov     [rsp+1E0h+var_1B8], 0; LPBINDSTATUSCALLBACK
0x1800377fe  mov     [rsp+1E0h+var_1C0], 0; DWORD
0x180037806  mov     r8, r14; LPSTR
0x180037809  mov     rdx, rdi; LPCSTR
0x18003780c  xor     ecx, ecx; LPUNKNOWN
0x18003780e  call    cs:__imp_URLDownloadToCacheFileA
0x180037814  test    eax, eax
0x180037816  jns     loc_1800378C6
0x18003781c  mov     [rsp+1E0h+var_1B0], 0
0x180037825  xor     r9d, r9d; int
0x180037828  lea     r8, [rsp+1E0h+var_1B0]; struct CStr *
0x18003782d  mov     rdx, rdi; char *
0x180037830  xor     ecx, ecx; HWND
0x180037832  call    ?FindThisFile@@YAHPEAUHWND__@@PEBDPEAVCStr@@H@Z; FindThisFile(HWND__ *,char const *,CStr *,int)
0x180037837  test    eax, eax
0x180037839  jz      short loc_180037876
0x18003783b  mov     r8, [rsp+1E0h+var_1B0]; char *
0x180037840  mov     rdx, r12; unsigned __int64
0x180037843  mov     rcx, r14; char *
0x180037846  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18003784b  test    eax, eax
0x18003784d  js      short loc_180037865
0x18003784f  mov     byte ptr [r15], 3Ah ; ':'
0x180037853  mov     r8, r15; char *
0x180037856  mov     rdx, r12; unsigned __int64
0x180037859  mov     rcx, r14; char *
0x18003785c  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x180037861  test    eax, eax
0x180037863  jns     short loc_180037867
0x180037865  xor     esi, esi
0x180037867  lea     rcx, [rsp+1E0h+var_1B0]; this
0x18003786c  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x180037871  jmp     loc_180037734
0x180037876  lea     rcx, [rsp+1E0h+var_1B0]; this
0x18003787b  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x180037880  xor     r9d, r9d
0x180037883  mov     r8, rdi
0x180037886  mov     edx, esi
0x180037888  call    ?IsUrlUnSafe@HHUrlSecurityManager@@QEAA_NW4SAFEURLTYPE@1@PEBDPEAVCHtmlHelpControl@@@Z; HHUrlSecurityManager::IsUrlUnSafe(HHUrlSecurityManager::SAFEURLTYPE,char const *,CHtmlHelpControl *)
0x18003788d  test    al, al
0x18003788f  jz      short loc_1800378D2
0x180037891  lea     rcx, [rsp+1E0h+var_1A0]; this
0x180037896  call    ??0HHEventManager@@QEAA@XZ; HHEventManager::HHEventManager(void)
0x18003789b  mov     rax, [rsp+1E0h+var_170]
0x1800378a0  mov     qword ptr [rsp+1E0h+var_1C0], rax; char *
0x1800378a5  mov     r9, rdi; char *
0x1800378a8  mov     edx, 771h; unsigned int
0x1800378ad  lea     rcx, [rsp+1E0h+var_1A0]; this
0x1800378b2  call    ?HHReportEvent@HHEventManager@@QEAAXKGPEBD0@Z; HHEventManager::HHReportEvent(ulong,ushort,char const *,char const *)
0x1800378b7  lea     rcx, [rsp+1E0h+var_1A0]; this
0x1800378bc  call    ??1HHEventManager@@QEAA@XZ; HHEventManager::~HHEventManager(void)
0x1800378c1  jmp     loc_180037732
0x1800378c6  mov     byte ptr [r15], 3Ah ; ':'
0x1800378ca  mov     r8, r15
0x1800378cd  jmp     loc_180037723
0x1800378d2  mov     r9d, r12d; cchFileName
0x1800378d5  mov     [rsp+1E0h+var_1B8], 0; LPBINDSTATUSCALLBACK
0x1800378de  mov     [rsp+1E0h+var_1C0], 0; DWORD
0x1800378e6  mov     r8, r14; LPSTR
0x1800378e9  mov     rdx, rdi; LPCSTR
0x1800378ec  xor     ecx, ecx; LPUNKNOWN
0x1800378ee  call    cs:__imp_URLDownloadToCacheFileA
0x1800378f4  jmp     loc_18003772E
```
