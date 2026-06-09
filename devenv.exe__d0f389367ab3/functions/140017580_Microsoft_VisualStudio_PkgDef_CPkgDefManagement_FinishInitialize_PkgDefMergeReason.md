# Microsoft::VisualStudio::PkgDef::CPkgDefManagement::FinishInitialize(PkgDefMergeReason *)

- ea: `0x140017580`
- end: `0x140017a38`
- name: `?FinishInitialize@CPkgDefManagement@PkgDef@VisualStudio@Microsoft@@UEAAJPEAW4PkgDefMergeReason@@@Z`
- size: `1208`
- prototype: `__int64 __fastcall(Microsoft::VisualStudio::PkgDef::CPkgDefManagement *__hidden this, enum PkgDefMergeReason *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14001b3f0`

## callees

- `0x140001020`
- `0x140001040`
- `0x140002c10`
- `0x140008120`
- `0x1400084f4`
- `0x1400095f4`
- `0x14001398c`
- `0x14001405c`
- `0x140017580`
- `0x140017a38`
- `0x14001b484`
- `0x14001bb90`
- `0x140033ab0`
- `0x140045420`
- `0x1400457bc`
- `0x1400464b0`
- `0x140046514`

## import_xrefs

- `KERNEL32!GetFileAttributesExW` at `0x140017690`
- `KERNEL32!GetFileAttributesExW` at `0x1400176d6`
- `KERNEL32!GetFileAttributesExW` at `0x140017690`
- `KERNEL32!GetFileAttributesExW` at `0x1400176d6`
- `KERNEL32!GetTickCount` at `0x14001779f`
- `KERNEL32!GetTickCount` at `0x140017898`
- `KERNEL32!GetTickCount` at `0x140017915`
- `KERNEL32!GetTickCount` at `0x140017924`
- `KERNEL32!GetTickCount` at `0x140017967`
- `KERNEL32!GetTickCount` at `0x140017973`
- `KERNEL32!GetTickCount` at `0x14001779f`
- `KERNEL32!GetTickCount` at `0x140017898`
- `KERNEL32!GetTickCount` at `0x140017915`
- `KERNEL32!GetTickCount` at `0x140017924`
- `KERNEL32!GetTickCount` at `0x140017967`
- `KERNEL32!GetTickCount` at `0x140017973`
- `KERNEL32!CompareFileTime` at `0x1400176f2`
- `KERNEL32!CompareFileTime` at `0x1400176f2`

## string_xrefs

- `0x140017656`: `extensions.configurationchanged`
- `0x1400176af`: `extensions.configurationchanged`
- `0x1400179a1`: `PkgDefManagement startup complete`
- `0x1400177fa`: `PkgDefManagement: Could not obtain cache lock; cache will be regenerated.`
- `0x14001783d`: `PkgDefManagement: PkgDef cache fast check returned false; cache will be regenerated.`
- `0x1400178d3`: `PkgDefManagement: FindConfigPkgDefs failed.`
- `0x1400178ae`: `PkgDefManagement: PkgDef cache fast check is disabled; cache will be regenerated.`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall Microsoft::VisualStudio::PkgDef::CPkgDefManagement::FinishInitialize(
        Microsoft::VisualStudio::PkgDef::CPkgDefManagement *this,
        enum PkgDefMergeReason *a2)
{
  int DirectoryScanDepthLimit; // r13d
  int v6; // edx
  int v7; // esi
  int v8; // r8d
  struct ATL::IAtlStringMgr *Instance; // rax
  LPCWSTR v10; // rbx
  BOOL FileAttributes; // r12d
  bool v12; // r15
  int v13; // r8d
  int v14; // edx
  int v15; // ebx
  DWORD TickCount; // r15d
  int ConfigPkgDefs; // ebx
  const unsigned __int16 *v18; // rcx
  int v19; // eax
  int v20; // edx
  int appended; // eax
  DWORD v22; // ebx
  LPCWSTR lpFileName; // [rsp+48h] [rbp-B8h] BYREF
  __int128 FileInformation; // [rsp+50h] [rbp-B0h] BYREF
  FILETIME FileTime1[2]; // [rsp+60h] [rbp-A0h] BYREF
  int v26; // [rsp+70h] [rbp-90h]
  __int128 v27; // [rsp+78h] [rbp-88h] BYREF
  __int128 v28; // [rsp+88h] [rbp-78h] BYREF
  int v29; // [rsp+98h] [rbp-68h]
  _BYTE v30[160]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v31[160]; // [rsp+140h] [rbp+40h] BYREF

  if ( a2 )
    *(_DWORD *)a2 = 0;
  if ( *((_DWORD *)this + 18) != -2147483638 )
    return 2147549183LL;
  DirectoryScanDepthLimit = Microsoft::VisualStudio::PkgDef::CPkgDefManagement::GetDirectoryScanDepthLimit(this);
  memset_0(v30, 0, sizeof(v30));
  v6 = (_DWORD)this + 296;
  v7 = 1;
  LOBYTE(v8) = 1;
  LOBYTE(v6) = 1;
  CFileDiscovery::CFileDiscovery(
    (unsigned int)v30,
    v6,
    v8,
    (_DWORD)this + 248,
    (__int64)this + 296,
    (__int64)this + 344,
    DirectoryScanDepthLimit);
  if ( (*(unsigned __int8 (__fastcall **)(Microsoft::VisualStudio::PkgDef::CPkgDefManagement *))(*(_QWORD *)this + 232LL))(this) )
  {
    Instance = ATL::CAtlStringMgr::GetInstance();
    if ( !Instance )
      ATL::AtlThrowImpl(-2147467259);
    lpFileName = (LPCWSTR)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance)
                         + 24);
    ATL::CPathT<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::Combine(
      &lpFileName,
      *((_QWORD *)this + 20),
      L"extensions.configurationchanged");
    FileInformation = 0;
    *(_OWORD *)&FileTime1[0].dwLowDateTime = 0;
    v26 = 0;
    v10 = lpFileName;
    FileAttributes = GetFileAttributesExW(lpFileName, GetFileExInfoStandard, &FileInformation);
    v12 = FileAttributes;
    if ( (*(unsigned __int8 (__fastcall **)(Microsoft::VisualStudio::PkgDef::CPkgDefManagement *))(*(_QWORD *)this
                                                                                                 + 296LL))(this) )
    {
      ATL::CPathT<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::Combine(
        &lpFileName,
        *((_QWORD *)this + 23),
        L"extensions.configurationchanged");
      v10 = lpFileName;
      if ( GetFileAttributesExW(lpFileName, GetFileExInfoStandard, &v27) )
      {
        if ( !FileAttributes )
        {
          FileInformation = v27;
          *(_OWORD *)&FileTime1[0].dwLowDateTime = v28;
          v26 = v29;
LABEL_13:
          *(FILETIME *)(*((_QWORD *)this + 2) + 52LL) = *(FILETIME *)&FileTime1[0].dwHighDateTime;
LABEL_14:
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v10 - 2, 0xFFFFFFFF) <= 1 )
          {
            _mm_lfence();
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v10 - 3) + 8LL))(*((_QWORD *)v10 - 3));
          }
          goto LABEL_16;
        }
        if ( CompareFileTime((const FILETIME *)&FileTime1[0].dwHighDateTime, (const FILETIME *)((char *)&v28 + 4)) == -1 )
        {
          v12 = 1;
          FileInformation = v27;
          *(_OWORD *)&FileTime1[0].dwLowDateTime = v28;
          v26 = v29;
        }
      }
    }
    if ( !v12 )
      goto LABEL_14;
    goto LABEL_13;
  }
LABEL_16:
  memset_0(v31, 0, sizeof(v31));
  LOBYTE(v13) = 1;
  LOBYTE(v14) = 1;
  CFileDiscovery::CFileDiscovery(
    (unsigned int)v31,
    v14,
    v13,
    (_DWORD)this + 448,
    (__int64)this + 496,
    (__int64)this + 544,
    DirectoryScanDepthLimit);
  v15 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 8LL))(*((_QWORD *)this + 2));
  lpFileName = (LPCWSTR)this;
  TickCount = GetTickCount();
  if ( (*((_DWORD *)this + 15) & 4) != 0 )
  {
LABEL_41:
    v22 = GetTickCount();
    *((_DWORD *)this + 18) = (*(__int64 (__fastcall **)(_QWORD, _BYTE *, _QWORD, _QWORD, _QWORD, _DWORD, enum PkgDefMergeReason *))(**((_QWORD **)this + 2) + 56LL))(
                               *((_QWORD *)this + 2),
                               v30,
                               *((_QWORD *)this + 52),
                               *((unsigned int *)this + 106),
                               *((_QWORD *)this + 54),
                               *((_DWORD *)this + 110),
                               a2);
    if ( GetTickCount() != v22 )
      v7 = GetTickCount() - v22;
    *((_DWORD *)this + 103) = v7;
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 16LL))(*((_QWORD *)this + 2));
    Microsoft::VisualStudio::PkgDef::CPkgDefManagement::SaveConfigInitializationToRegistry(
      this,
      *((const struct CPkgDefCache **)this + 2),
      0);
    CLogger::LogInfo(L"PkgDefManagement startup complete", 0, 0);
    CodeMarker(9210);
    if ( (*(unsigned __int8 (__fastcall **)(Microsoft::VisualStudio::PkgDef::CPkgDefManagement *))(*(_QWORD *)this
                                                                                                 + 240LL))(this)
      || (ConfigPkgDefs = (*(__int64 (__fastcall **)(Microsoft::VisualStudio::PkgDef::CPkgDefManagement *))(*(_QWORD *)this + 208LL))(this),
          ConfigPkgDefs >= 0)
      || (_mm_lfence(),
          !(*(unsigned __int8 (__fastcall **)(Microsoft::VisualStudio::PkgDef::CPkgDefManagement *))(*(_QWORD *)this + 248LL))(this)) )
    {
      ConfigPkgDefs = *((_DWORD *)this + 18);
    }
    goto LABEL_47;
  }
  if ( !(*(unsigned __int8 (__fastcall **)(Microsoft::VisualStudio::PkgDef::CPkgDefManagement *))(*(_QWORD *)this + 232LL))(this)
    || (*(unsigned __int8 (__fastcall **)(Microsoft::VisualStudio::PkgDef::CPkgDefManagement *))(*(_QWORD *)this + 264LL))(this) )
  {
    CLogger::LogInfo(L"PkgDefManagement: PkgDef cache fast check is disabled; cache will be regenerated.", 0, 0);
    ConfigPkgDefs = Microsoft::VisualStudio::PkgDef::CPkgDefManagement::FindConfigPkgDefs(
                      this,
                      (struct CFileDiscovery *)v30,
                      (struct CFileDiscovery *)v31);
    _mm_lfence();
    if ( ConfigPkgDefs >= 0 )
    {
      appended = Microsoft::VisualStudio::PkgDef::CPkgDefManagement::AppendPkgUnDefIfExists(
                   this,
                   (struct CFileDiscovery *)v30);
      ConfigPkgDefs = appended;
      if ( appended < 0 )
      {
        _mm_lfence();
        v20 = appended;
        v18 = L"PkgDefManagement: AppendPkgUnDefIfExists failed.";
        goto LABEL_38;
      }
      goto LABEL_31;
    }
    goto LABEL_34;
  }
  if ( v15 >= 0 )
  {
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD, enum PkgDefMergeReason *))(**((_QWORD **)this + 2) + 72LL))(
           *((_QWORD *)this + 2),
           a2) )
    {
      goto LABEL_29;
    }
    CLogger::LogInfo(L"PkgDefManagement: PkgDef cache fast check returned false; cache will be regenerated.", 0, 0);
  }
  else
  {
    if ( a2 )
      *(_DWORD *)a2 = 3;
    CLogger::LogWarn(L"PkgDefManagement: Could not obtain cache lock; cache will be regenerated.", v15, 0);
  }
  ConfigPkgDefs = Microsoft::VisualStudio::PkgDef::CPkgDefManagement::FindConfigPkgDefs(
                    this,
                    (struct CFileDiscovery *)v30,
                    (struct CFileDiscovery *)v31);
  _mm_lfence();
  if ( ConfigPkgDefs < 0 )
  {
LABEL_34:
    v18 = L"PkgDefManagement: FindConfigPkgDefs failed.";
    goto LABEL_35;
  }
  ConfigPkgDefs = Microsoft::VisualStudio::PkgDef::CPkgDefManagement::AppendPkgUnDefIfExists(
                    this,
                    (struct CFileDiscovery *)v30);
  if ( ConfigPkgDefs >= 0 )
  {
LABEL_29:
    if ( (*(unsigned __int8 (__fastcall **)(Microsoft::VisualStudio::PkgDef::CPkgDefManagement *))(*(_QWORD *)this
                                                                                                 + 112LL))(this) )
      Microsoft::VisualStudio::PkgDef::CPkgDefManagement::InitUserExtensionPaths(this, 1);
LABEL_31:
    if ( GetTickCount() == TickCount )
      v19 = 1;
    else
      v19 = GetTickCount() - TickCount;
    *((_DWORD *)this + 102) = v19;
    goto LABEL_41;
  }
  _mm_lfence();
  v18 = L"PkgDefManagement: AppendPkgUnDefIfExists failed.";
LABEL_35:
  v20 = ConfigPkgDefs;
LABEL_38:
  CLogger::LogError(v18, v20, 0);
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 16LL))(*((_QWORD *)this + 2));
LABEL_47:
  CFileDiscovery::~CFileDiscovery((CFileDiscovery *)v31);
  CFileDiscovery::~CFileDiscovery((CFileDiscovery *)v30);
  return (unsigned int)ConfigPkgDefs;
}

```

## disassembly

```asm
0x140017580  mov     [rsp-8+arg_10], rbx
0x140017585  push    rbp
0x140017586  push    rsi
0x140017587  push    rdi
0x140017588  push    r12
0x14001758a  push    r13
0x14001758c  push    r14
0x14001758e  push    r15
0x140017590  lea     rbp, [rsp-0F0h]
0x140017598  sub     rsp, 1F0h
0x14001759f  mov     rax, cs:__security_cookie
0x1400175a6  xor     rax, rsp
0x1400175a9  mov     [rbp+120h+var_40], rax
0x1400175b0  mov     r14, rdx
0x1400175b3  mov     rdi, rcx
0x1400175b6  test    rdx, rdx
0x1400175b9  jz      short loc_1400175BE
0x1400175bb  and     dword ptr [rdx], 0
0x1400175be  cmp     dword ptr [rcx+48h], 8000000Ah
0x1400175c5  jz      short loc_1400175D1
0x1400175c7  mov     eax, 8000FFFFh
0x1400175cc  jmp     loc_140017A03
0x1400175d1  call    ?GetDirectoryScanDepthLimit@CPkgDefManagement@PkgDef@VisualStudio@Microsoft@@AEAAHXZ; Microsoft::VisualStudio::PkgDef::CPkgDefManagement::GetDirectoryScanDepthLimit(void)
0x1400175d6  mov     r13d, eax
0x1400175d9  xor     edx, edx; Val
0x1400175db  mov     r8d, 0A0h; Size
0x1400175e1  lea     rcx, [rbp+120h+var_180]; void *
0x1400175e5  call    memset_0
0x1400175ea  lea     rcx, [rdi+158h]
0x1400175f1  lea     rdx, [rdi+128h]
0x1400175f8  lea     r9, [rdi+0F8h]
0x1400175ff  mov     dword ptr [rsp+220h+var_1F0], r13d
0x140017604  mov     [rsp+220h+var_1F8], rcx
0x140017609  mov     [rsp+220h+var_200], rdx
0x14001760e  mov     esi, 1
0x140017613  mov     r8b, sil
0x140017616  mov     dl, sil
0x140017619  lea     rcx, [rbp+120h+var_180]
0x14001761d  call    ??0CFileDiscovery@@QEAA@_N0AEAV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@AEBV12@2H@Z; CFileDiscovery::CFileDiscovery(bool,bool,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> &,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> const &,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> const &,int)
0x140017622  mov     rax, [rdi]
0x140017625  mov     rcx, rdi
0x140017628  call    qword ptr [rax+0E8h]
0x14001762e  test    al, al
0x140017630  jz      loc_140017749
0x140017636  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14001763b  mov     rcx, rax
0x14001763e  test    rax, rax
0x140017641  jz      loc_140017A2D
0x140017647  mov     rax, [rax]
0x14001764a  call    qword ptr [rax+18h]
0x14001764d  add     rax, 18h
0x140017651  mov     [rsp+220h+lpFileName], rax
0x140017656  lea     r8, aExtensionsConf; "extensions.configurationchanged"
0x14001765d  mov     rdx, [rdi+0A0h]
0x140017664  lea     rcx, [rsp+220h+lpFileName]
0x140017669  call    ?Combine@?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@QEAAXPEBG0@Z; ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::Combine(ushort const *,ushort const *)
0x14001766e  xorps   xmm0, xmm0
0x140017671  xor     eax, eax
0x140017673  movups  [rsp+220h+FileInformation], xmm0
0x140017678  movups  xmmword ptr [rsp+220h+FileTime1.dwLowDateTime], xmm0
0x14001767d  mov     [rsp+220h+var_1B0], eax
0x140017681  lea     r8, [rsp+220h+FileInformation]; lpFileInformation
0x140017686  xor     edx, edx; fInfoLevelId
0x140017688  mov     rbx, [rsp+220h+lpFileName]
0x14001768d  mov     rcx, rbx; lpFileName
0x140017690  call    cs:__imp_GetFileAttributesExW
0x140017696  mov     r12d, eax
0x140017699  test    eax, eax
0x14001769b  setnz   r15b
0x14001769f  mov     rdx, [rdi]
0x1400176a2  mov     rcx, rdi
0x1400176a5  call    qword ptr [rdx+128h]
0x1400176ab  test    al, al
0x1400176ad  jz      short loc_14001771A
0x1400176af  lea     r8, aExtensionsConf; "extensions.configurationchanged"
0x1400176b6  mov     rdx, [rdi+0B8h]
0x1400176bd  lea     rcx, [rsp+220h+lpFileName]
0x1400176c2  call    ?Combine@?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@QEAAXPEBG0@Z; ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::Combine(ushort const *,ushort const *)
0x1400176c7  lea     r8, [rsp+220h+var_1A8]; lpFileInformation
0x1400176cc  xor     edx, edx; fInfoLevelId
0x1400176ce  mov     rbx, [rsp+220h+lpFileName]
0x1400176d3  mov     rcx, rbx; lpFileName
0x1400176d6  call    cs:__imp_GetFileAttributesExW
0x1400176dc  test    eax, eax
0x1400176de  jz      short loc_14001771A
0x1400176e0  test    r12d, r12d
0x1400176e3  jz      loc_140017808
0x1400176e9  lea     rdx, [rbp+120h+FileTime2]; lpFileTime2
0x1400176ed  lea     rcx, [rsp+220h+FileTime1.dwHighDateTime]; lpFileTime1
0x1400176f2  call    cs:__imp_CompareFileTime
0x1400176f8  cmp     eax, 0FFFFFFFFh
0x1400176fb  jnz     short loc_14001771A
0x1400176fd  mov     r15b, sil
0x140017700  movups  xmm0, [rsp+220h+var_1A8]
0x140017705  movups  [rsp+220h+FileInformation], xmm0
0x14001770a  movups  xmm1, xmmword ptr [rbp-78h]
0x14001770e  movups  xmmword ptr [rsp+220h+FileTime1.dwLowDateTime], xmm1
0x140017713  mov     eax, [rbp+120h+var_188]
0x140017716  mov     [rsp+220h+var_1B0], eax
0x14001771a  test    r15b, r15b
0x14001771d  jz      short loc_14001772C
0x14001771f  mov     rcx, [rdi+10h]
0x140017723  mov     rax, qword ptr [rsp+220h+FileTime1.dwHighDateTime]
0x140017728  mov     [rcx+34h], rax
0x14001772c  lea     rdx, [rbx-18h]
0x140017730  or      eax, 0FFFFFFFFh
0x140017733  lock xadd [rdx+10h], eax
0x140017738  sub     eax, 1
0x14001773b  jg      short loc_140017749
0x14001773d  lfence
0x140017740  mov     rcx, [rdx]
0x140017743  mov     rax, [rcx]
0x140017746  call    qword ptr [rax+8]
0x140017749  xor     edx, edx; Val
0x14001774b  mov     r8d, 0A0h; Size
0x140017751  lea     rcx, [rbp+120h+var_E0]; void *
0x140017755  call    memset_0
0x14001775a  lea     rax, [rdi+220h]
0x140017761  lea     rcx, [rdi+1F0h]
0x140017768  lea     r9, [rdi+1C0h]
0x14001776f  mov     dword ptr [rsp+220h+var_1F0], r13d
0x140017774  mov     [rsp+220h+var_1F8], rax
0x140017779  mov     [rsp+220h+var_200], rcx
0x14001777e  mov     r8b, sil
0x140017781  mov     dl, sil
0x140017784  lea     rcx, [rbp+120h+var_E0]
0x140017788  call    ??0CFileDiscovery@@QEAA@_N0AEAV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@AEBV12@2H@Z; CFileDiscovery::CFileDiscovery(bool,bool,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> &,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> const &,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> const &,int)
0x14001778d  nop
0x14001778e  mov     rcx, [rdi+10h]
0x140017792  mov     rax, [rcx]
0x140017795  call    qword ptr [rax+8]
0x140017798  mov     ebx, eax
0x14001779a  mov     [rsp+220h+lpFileName], rdi
0x14001779f  call    cs:__imp_GetTickCount
0x1400177a5  mov     r15d, eax
0x1400177a8  mov     ecx, [rdi+3Ch]
0x1400177ab  shr     ecx, 2
0x1400177ae  test    sil, cl
0x1400177b1  jnz     loc_140017924
0x1400177b7  mov     rdx, [rdi]
0x1400177ba  mov     rcx, rdi
0x1400177bd  call    qword ptr [rdx+0E8h]
0x1400177c3  test    al, al
0x1400177c5  jz      loc_1400178A9
0x1400177cb  mov     rdx, [rdi]
0x1400177ce  mov     rcx, rdi
0x1400177d1  call    qword ptr [rdx+108h]
0x1400177d7  test    al, al
0x1400177d9  jnz     loc_1400178A9
0x1400177df  mov     eax, ebx
0x1400177e1  shr     eax, 1Fh
0x1400177e4  xor     al, sil
0x1400177e7  jnz     short loc_140017827
0x1400177e9  test    r14, r14
0x1400177ec  jz      short loc_1400177F5
0x1400177ee  mov     dword ptr [r14], 3
0x1400177f5  xor     r8d, r8d; unsigned __int16 *
0x1400177f8  mov     edx, ebx; int
0x1400177fa  lea     rcx, aPkgdefmanageme_4; "PkgDefManagement: Could not obtain cach"...
0x140017801  call    ?LogWarn@CLogger@@SAXPEBGJ0@Z; CLogger::LogWarn(ushort const *,long,ushort const *)
0x140017806  jmp     short loc_140017849
0x140017808  movups  xmm0, [rsp+220h+var_1A8]
0x14001780d  movups  [rsp+220h+FileInformation], xmm0
0x140017812  movups  xmm1, xmmword ptr [rbp-78h]
0x140017816  movups  xmmword ptr [rsp+220h+FileTime1.dwLowDateTime], xmm1
0x14001781b  mov     eax, [rbp+120h+var_188]
0x14001781e  mov     [rsp+220h+var_1B0], eax
0x140017822  jmp     loc_14001771F
0x140017827  mov     rcx, [rdi+10h]
0x14001782b  mov     rax, [rcx]
0x14001782e  mov     rdx, r14
0x140017831  call    qword ptr [rax+48h]
0x140017834  test    al, al
0x140017836  jnz     short loc_140017880
0x140017838  xor     r8d, r8d; unsigned __int16 *
0x14001783b  xor     edx, edx; int
0x14001783d  lea     rcx, aPkgdefmanageme_5; "PkgDefManagement: PkgDef cache fast che"...
0x140017844  call    ?LogInfo@CLogger@@SAXPEBGJ0@Z; CLogger::LogInfo(ushort const *,long,ushort const *)
0x140017849  lea     r8, [rbp+120h+var_E0]; struct CFileDiscovery *
0x14001784d  lea     rdx, [rbp+120h+var_180]; struct CFileDiscovery *
0x140017851  mov     rcx, rdi; this
0x140017854  call    ?FindConfigPkgDefs@CPkgDefManagement@PkgDef@VisualStudio@Microsoft@@AEAAJAEAVCFileDiscovery@@0@Z; Microsoft::VisualStudio::PkgDef::CPkgDefManagement::FindConfigPkgDefs(CFileDiscovery &,CFileDiscovery &)
0x140017859  mov     ebx, eax
0x14001785b  lfence
0x14001785e  test    eax, eax
0x140017860  js      short loc_1400178D3
0x140017862  lea     rdx, [rbp+120h+var_180]; struct CFileDiscovery *
0x140017866  mov     rcx, rdi; this
0x140017869  call    ?AppendPkgUnDefIfExists@CPkgDefManagement@PkgDef@VisualStudio@Microsoft@@AEAAJAEAVCFileDiscovery@@@Z; Microsoft::VisualStudio::PkgDef::CPkgDefManagement::AppendPkgUnDefIfExists(CFileDiscovery &)
0x14001786e  mov     ebx, eax
0x140017870  test    eax, eax
0x140017872  jns     short loc_140017880
0x140017874  lfence
0x140017877  lea     rcx, aPkgdefmanageme_1; "PkgDefManagement: AppendPkgUnDefIfExist"...
0x14001787e  jmp     short loc_1400178DA
0x140017880  mov     rax, [rdi]
0x140017883  mov     rcx, rdi
0x140017886  call    qword ptr [rax+70h]
0x140017889  test    al, al
0x14001788b  jz      short loc_140017898
0x14001788d  mov     dl, sil; bool
0x140017890  mov     rcx, rdi; this
0x140017893  call    ?InitUserExtensionPaths@CPkgDefManagement@PkgDef@VisualStudio@Microsoft@@AEAAX_N@Z; Microsoft::VisualStudio::PkgDef::CPkgDefManagement::InitUserExtensionPaths(bool)
0x140017898  call    cs:__imp_GetTickCount
0x14001789e  sub     eax, r15d
0x1400178a1  cmp     eax, esi
0x1400178a3  jnb     short loc_140017915
0x1400178a5  mov     eax, esi
0x1400178a7  jmp     short loc_14001791E
0x1400178a9  xor     r8d, r8d; unsigned __int16 *
0x1400178ac  xor     edx, edx; int
0x1400178ae  lea     rcx, aPkgdefmanageme_6; "PkgDefManagement: PkgDef cache fast che"...
0x1400178b5  call    ?LogInfo@CLogger@@SAXPEBGJ0@Z; CLogger::LogInfo(ushort const *,long,ushort const *)
0x1400178ba  lea     r8, [rbp+120h+var_E0]; struct CFileDiscovery *
0x1400178be  lea     rdx, [rbp+120h+var_180]; struct CFileDiscovery *
0x1400178c2  mov     rcx, rdi; this
0x1400178c5  call    ?FindConfigPkgDefs@CPkgDefManagement@PkgDef@VisualStudio@Microsoft@@AEAAJAEAVCFileDiscovery@@0@Z; Microsoft::VisualStudio::PkgDef::CPkgDefManagement::FindConfigPkgDefs(CFileDiscovery &,CFileDiscovery &)
0x1400178ca  mov     ebx, eax
0x1400178cc  lfence
0x1400178cf  test    eax, eax
0x1400178d1  jns     short loc_1400178DE
0x1400178d3  lea     rcx, aPkgdefmanageme_9; "PkgDefManagement: FindConfigPkgDefs fai"...
0x1400178da  mov     edx, ebx
0x1400178dc  jmp     short loc_1400178FC
0x1400178de  lea     rdx, [rbp+120h+var_180]; struct CFileDiscovery *
0x1400178e2  mov     rcx, rdi; this
0x1400178e5  call    ?AppendPkgUnDefIfExists@CPkgDefManagement@PkgDef@VisualStudio@Microsoft@@AEAAJAEAVCFileDiscovery@@@Z; Microsoft::VisualStudio::PkgDef::CPkgDefManagement::AppendPkgUnDefIfExists(CFileDiscovery &)
0x1400178ea  mov     ebx, eax
0x1400178ec  test    eax, eax
0x1400178ee  jns     short loc_140017898
0x1400178f0  lfence
0x1400178f3  mov     edx, eax; int
0x1400178f5  lea     rcx, aPkgdefmanageme_1; "PkgDefManagement: AppendPkgUnDefIfExist"...
0x1400178fc  xor     r8d, r8d; unsigned __int16 *
0x1400178ff  call    ?LogError@CLogger@@SAXPEBGJ0@Z; CLogger::LogError(ushort const *,long,ushort const *)
0x140017904  nop
0x140017905  mov     rcx, [rdi+10h]
0x140017909  mov     rax, [rcx]
0x14001790c  call    qword ptr [rax+10h]
0x14001790f  nop
0x140017910  jmp     loc_1400179EF
0x140017915  call    cs:__imp_GetTickCount
0x14001791b  sub     eax, r15d
0x14001791e  mov     [rdi+198h], eax
0x140017924  call    cs:__imp_GetTickCount
0x14001792a  mov     ebx, eax
0x14001792c  mov     rcx, [rdi+10h]
0x140017930  mov     r10, [rcx]
0x140017933  mov     [rsp+220h+var_1F0], r14
0x140017938  mov     edx, [rdi+1B8h]
0x14001793e  mov     dword ptr [rsp+220h+var_1F8], edx
0x140017942  mov     rdx, [rdi+1B0h]
0x140017949  mov     [rsp+220h+var_200], rdx
0x14001794e  mov     r9d, [rdi+1A8h]
0x140017955  mov     r8, [rdi+1A0h]
0x14001795c  lea     rdx, [rbp+120h+var_180]
0x140017960  call    qword ptr [r10+38h]
0x140017964  mov     [rdi+48h], eax
0x140017967  call    cs:__imp_GetTickCount
0x14001796d  sub     eax, ebx
0x14001796f  cmp     eax, esi
0x140017971  jb      short loc_14001797D
0x140017973  call    cs:__imp_GetTickCount
0x140017979  mov     esi, eax
0x14001797b  sub     esi, ebx
0x14001797d  mov     [rdi+19Ch], esi
0x140017983  mov     rcx, [rdi+10h]
0x140017987  mov     rax, [rcx]
0x14001798a  call    qword ptr [rax+10h]
0x14001798d  xor     r8d, r8d; bool
0x140017990  mov     rdx, [rdi+10h]; struct CPkgDefCache *
0x140017994  mov     rcx, rdi; this
0x140017997  call    ?SaveConfigInitializationToRegistry@CPkgDefManagement@PkgDef@VisualStudio@Microsoft@@AEBAJAEBVCPkgDefCache@@_N@Z; Microsoft::VisualStudio::PkgDef::CPkgDefManagement::SaveConfigInitializationToRegistry(CPkgDefCache const &,bool)
0x14001799c  xor     r8d, r8d; unsigned __int16 *
0x14001799f  xor     edx, edx; int
0x1400179a1  lea     rcx, aPkgdefmanageme_3; "PkgDefManagement startup complete"
0x1400179a8  call    ?LogInfo@CLogger@@SAXPEBGJ0@Z; CLogger::LogInfo(ushort const *,long,ushort const *)
0x1400179ad  mov     ecx, 23FAh
0x1400179b2  call    ?CodeMarker@@YAXW4CodeMarkerEvent@Performance@Internal@Microsoft@@@Z; CodeMarker(Microsoft::Internal::Performance::CodeMarkerEvent)
0x1400179b7  mov     rax, [rdi]
0x1400179ba  mov     rcx, rdi
0x1400179bd  call    qword ptr [rax+0F0h]
0x1400179c3  test    al, al
0x1400179c5  jnz     short loc_1400179EC
0x1400179c7  mov     rax, [rdi]
0x1400179ca  mov     rcx, rdi
0x1400179cd  call    qword ptr [rax+0D0h]
0x1400179d3  mov     ebx, eax
0x1400179d5  test    eax, eax
0x1400179d7  jns     short loc_1400179EC
0x1400179d9  lfence
0x1400179dc  mov     rax, [rdi]
0x1400179df  mov     rcx, rdi
0x1400179e2  call    qword ptr [rax+0F8h]
0x1400179e8  test    al, al
0x1400179ea  jnz     short loc_1400179EF
0x1400179ec  mov     ebx, [rdi+48h]
0x1400179ef  lea     rcx, [rbp+120h+var_E0]; this
0x1400179f3  call    ??1CFileDiscovery@@UEAA@XZ; CFileDiscovery::~CFileDiscovery(void)
0x1400179f8  lea     rcx, [rbp+120h+var_180]; this
  ... truncated ...
```
