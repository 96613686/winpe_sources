# Microsoft::VisualStudio::PkgDef::CPkgDefManagement::StartCache(void)

- ea: `0x140016668`
- end: `0x140016974`
- name: `?StartCache@CPkgDefManagement@PkgDef@VisualStudio@Microsoft@@AEAAJXZ`
- size: `780`
- prototype: `__int64 __fastcall(Microsoft::VisualStudio::PkgDef::CPkgDefManagement *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14001d17c`

## callees

- `0x140001020`
- `0x140002c10`
- `0x140003070`
- `0x140003160`
- `0x140004950`
- `0x1400095f4`
- `0x140014220`
- `0x140016668`
- `0x140016980`
- `0x14002ae80`
- `0x14002b618`
- `0x140033ab0`
- `0x140046514`

## import_xrefs

- `ADVAPI32!ImpersonateLoggedOnUser` at `0x14001686e`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x14001686e`
- `ADVAPI32!RevertToSelf` at `0x1400168a7`
- `ADVAPI32!RevertToSelf` at `0x1400168a7`

## string_xrefs

- `0x1400166be`: `Registry root was never specified`
- `0x140016896`: `Failed to initialize Registry Root Hive`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Microsoft::VisualStudio::PkgDef::CPkgDefManagement::StartCache(
        Microsoft::VisualStudio::PkgDef::CPkgDefManagement *this)
{
  __int64 v2; // rcx
  struct ATL::IAtlStringMgr *Instance; // rax
  int v5; // edi
  _QWORD *v6; // rdx
  struct ATL::IAtlStringMgr *v7; // rax
  _QWORD *v8; // rdx
  __int64 v9; // rdi
  _QWORD *v10; // rdx
  bool v11; // di
  __int64 v12; // r14
  bool v13; // bl
  RegistryDetouring *v14; // rcx
  const unsigned __int16 *v15; // r8
  int v16; // eax
  _QWORD *v17; // rdx
  _QWORD *v18; // rdx
  __int64 v19; // [rsp+20h] [rbp-30h] BYREF
  bool v20; // [rsp+28h] [rbp-28h]
  __int64 v21; // [rsp+30h] [rbp-20h] BYREF
  __int64 v22; // [rsp+38h] [rbp-18h] BYREF

  v2 = *((_QWORD *)this + 2);
  if ( !v2 )
    return 2147549183LL;
  if ( *(_DWORD *)(*((_QWORD *)this + 14) - 16LL) )
  {
    CPkgDefCache::CalculateRegKeyPaths(v2, (char *)this + 112, *((_QWORD *)this + 6));
    v22 = 0;
    Instance = ATL::CAtlStringMgr::GetInstance();
    if ( !Instance )
      ATL::AtlThrowImpl(-2147467259);
    v22 = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance) + 24;
    v5 = (*(__int64 (__fastcall **)(Microsoft::VisualStudio::PkgDef::CPkgDefManagement *, _QWORD, __int64 *))(*(_QWORD *)this + 8LL))(
           this,
           0,
           &v22);
    if ( v5 >= 0 )
    {
      _mm_lfence();
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &v19,
        v22);
      ATL::CSimpleStringT<unsigned short,0>::operator=(*((_QWORD *)this + 2) + 120LL, &v19);
      v6 = (_QWORD *)(v19 - 24);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v19 - 24 + 16)) <= 0 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v6 + 8LL))(*v6);
      }
      v21 = 0;
      v7 = ATL::CAtlStringMgr::GetInstance();
      if ( !v7 )
        ATL::AtlThrowImpl(-2147467259);
      _mm_lfence();
      v21 = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v7 + 24LL))(v7) + 24;
      v5 = (*(__int64 (__fastcall **)(Microsoft::VisualStudio::PkgDef::CPkgDefManagement *, __int64, __int64 *))(*(_QWORD *)this + 8LL))(
             this,
             4,
             &v21);
      if ( v5 >= 0 )
      {
        _mm_lfence();
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          &v19,
          v21);
        ATL::CSimpleStringT<unsigned short,0>::operator=(*((_QWORD *)this + 2) + 128LL, &v19);
        v8 = (_QWORD *)(v19 - 24);
        if ( _InterlockedDecrement((volatile signed __int32 *)(v19 - 24 + 16)) <= 0 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v8 + 8LL))(*v8);
        }
        v9 = *((_QWORD *)this + 2);
        ATL::CSimpleStringT<unsigned short,0>::operator=(v9 + 88, (char *)this + 400);
        v19 = ATL::CSimpleStringT<unsigned short,0>::CloneData(*((_QWORD *)this + 50) - 24LL) + 24;
        ATL::CPathT<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::StripPath(&v19);
        ATL::CSimpleStringT<unsigned short,0>::operator=(v9 + 80, &v19);
        v10 = (_QWORD *)(v19 - 24);
        if ( _InterlockedDecrement((volatile signed __int32 *)(v19 - 24 + 16)) <= 0 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v10 + 8LL))(*v10);
        }
        v11 = (*((_DWORD *)this + 15) & 0x2000) != 0;
        v12 = *((_QWORD *)this + 2);
        if ( *(_QWORD *)(v12 + 232) )
          goto LABEL_21;
        v13 = ImpersonateLoggedOnUser(*(HANDLE *)(v12 + 224));
        v20 = v13;
        LOBYTE(v14) = v11;
        v16 = RegistryDetouring::InitializeRegRootHive(v14, *(_QWORD *)(v12 + 120), v15);
        v5 = v16;
        if ( v16 < 0 )
        {
          _mm_lfence();
          CLogger::LogError(L"Failed to initialize Registry Root Hive", v16, 0);
        }
        if ( v13 )
          RevertToSelf();
        if ( v5 >= 0 )
        {
LABEL_21:
          v5 = Microsoft::VisualStudio::PkgDef::CPkgDefManagement::EnsureMasterPkgDefSettingsAreSet(this);
          if ( v5 >= 0 )
          {
            if ( (*((_DWORD *)this + 15) & 0x800) != 0 )
            {
              v5 = 0;
            }
            else
            {
              _mm_lfence();
              v5 = (*(__int64 (__fastcall **)(Microsoft::VisualStudio::PkgDef::CPkgDefManagement *, _QWORD))(*(_QWORD *)this + 200LL))(
                     this,
                     0);
            }
          }
        }
      }
      v17 = (_QWORD *)(v21 - 24);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v21 - 24 + 16)) <= 0 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v17 + 8LL))(*v17);
      }
    }
    v18 = (_QWORD *)(v22 - 24);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v22 - 24 + 16)) <= 0 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v18 + 8LL))(*v18);
    }
    return (unsigned int)v5;
  }
  else
  {
    CLogger::LogInfo(L"Registry root was never specified", -2147024809, 0);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x140016668  mov     [rsp-18h+arg_8], rbx
0x14001666d  mov     [rsp-18h+arg_10], rsi
0x140016672  mov     [rsp-18h+arg_18], rdi
0x140016677  push    rbp
0x140016678  push    r12
0x14001667a  push    r14
0x14001667c  mov     rbp, rsp
0x14001667f  sub     rsp, 50h
0x140016683  mov     rax, cs:__security_cookie
0x14001668a  xor     rax, rsp
0x14001668d  mov     [rbp+var_10], rax
0x140016691  mov     rsi, rcx
0x140016694  mov     rcx, [rcx+10h]
0x140016698  test    rcx, rcx
0x14001669b  jnz     short loc_1400166A7
0x14001669d  mov     eax, 8000FFFFh
0x1400166a2  jmp     loc_140016935
0x1400166a7  lea     rdx, [rsi+70h]
0x1400166ab  mov     rax, [rdx]
0x1400166ae  cmp     dword ptr [rax-10h], 0
0x1400166b2  jnz     short loc_1400166D1
0x1400166b4  xor     r8d, r8d; unsigned __int16 *
0x1400166b7  mov     ebx, 80070057h
0x1400166bc  mov     edx, ebx; int
0x1400166be  lea     rcx, aRegistryRootWa; "Registry root was never specified"
0x1400166c5  call    ?LogInfo@CLogger@@SAXPEBGJ0@Z; CLogger::LogInfo(ushort const *,long,ushort const *)
0x1400166ca  mov     eax, ebx
0x1400166cc  jmp     loc_140016935
0x1400166d1  mov     r8, [rsi+30h]
0x1400166d5  call    ?CalculateRegKeyPaths@CPkgDefCache@@QEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBG@Z; CPkgDefCache::CalculateRegKeyPaths(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *)
0x1400166da  and     [rbp+var_18], 0
0x1400166df  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x1400166e4  mov     rcx, rax
0x1400166e7  test    rax, rax
0x1400166ea  jz      loc_140016969
0x1400166f0  mov     rax, [rax]
0x1400166f3  call    qword ptr [rax+18h]
0x1400166f6  add     rax, 18h
0x1400166fa  mov     [rbp+var_18], rax
0x1400166fe  mov     rax, [rsi]
0x140016701  lea     r8, [rbp+var_18]
0x140016705  xor     edx, edx
0x140016707  mov     rcx, rsi
0x14001670a  call    qword ptr [rax+8]
0x14001670d  mov     edi, eax
0x14001670f  or      r12d, 0FFFFFFFFh
0x140016713  test    eax, eax
0x140016715  js      loc_140016910
0x14001671b  lfence
0x14001671e  mov     rdx, [rbp+var_18]
0x140016722  lea     rcx, [rbp+var_30]
0x140016726  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14001672b  nop
0x14001672c  mov     rcx, [rsi+10h]
0x140016730  add     rcx, 78h ; 'x'
0x140016734  lea     rdx, [rbp+var_30]
0x140016738  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x14001673d  nop
0x14001673e  mov     rdx, [rbp+var_30]
0x140016742  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140016746  mov     eax, r12d
0x140016749  lock xadd [rdx+10h], eax
0x14001674e  add     eax, r12d
0x140016751  test    eax, eax
0x140016753  jg      short loc_140016761
0x140016755  lfence
0x140016758  mov     rcx, [rdx]
0x14001675b  mov     rax, [rcx]
0x14001675e  call    qword ptr [rax+8]
0x140016761  and     [rbp+var_20], 0
0x140016766  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14001676b  mov     rcx, rax
0x14001676e  test    rax, rax
0x140016771  jz      loc_14001695B
0x140016777  lfence
0x14001677a  mov     rax, [rax]
0x14001677d  call    qword ptr [rax+18h]
0x140016780  add     rax, 18h
0x140016784  mov     [rbp+var_20], rax
0x140016788  mov     rax, [rsi]
0x14001678b  lea     r8, [rbp+var_20]
0x14001678f  mov     edx, 4
0x140016794  mov     rcx, rsi
0x140016797  call    qword ptr [rax+8]
0x14001679a  mov     edi, eax
0x14001679c  test    eax, eax
0x14001679e  js      loc_1400168E0
0x1400167a4  lfence
0x1400167a7  mov     rdx, [rbp+var_20]
0x1400167ab  lea     rcx, [rbp+var_30]
0x1400167af  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1400167b4  nop
0x1400167b5  mov     rcx, [rsi+10h]
0x1400167b9  sub     rcx, 0FFFFFFFFFFFFFF80h
0x1400167bd  lea     rdx, [rbp+var_30]
0x1400167c1  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x1400167c6  nop
0x1400167c7  mov     rdx, [rbp+var_30]
0x1400167cb  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1400167cf  mov     eax, r12d
0x1400167d2  lock xadd [rdx+10h], eax
0x1400167d7  add     eax, r12d
0x1400167da  test    eax, eax
0x1400167dc  jg      short loc_1400167EA
0x1400167de  lfence
0x1400167e1  mov     rcx, [rdx]
0x1400167e4  mov     rax, [rcx]
0x1400167e7  call    qword ptr [rax+8]
0x1400167ea  lea     rbx, [rsi+190h]
0x1400167f1  mov     rdi, [rsi+10h]
0x1400167f5  lea     rcx, [rdi+58h]
0x1400167f9  mov     rdx, rbx
0x1400167fc  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x140016801  mov     rcx, [rbx]
0x140016804  sub     rcx, 18h
0x140016808  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x14001680d  add     rax, 18h
0x140016811  mov     [rbp+var_30], rax
0x140016815  lea     rcx, [rbp+var_30]
0x140016819  call    ?StripPath@?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@QEAAXXZ; ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::StripPath(void)
0x14001681e  lea     rcx, [rdi+50h]
0x140016822  lea     rdx, [rbp+var_30]
0x140016826  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x14001682b  nop
0x14001682c  mov     rdx, [rbp+var_30]
0x140016830  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140016834  mov     eax, r12d
0x140016837  lock xadd [rdx+10h], eax
0x14001683c  add     eax, r12d
0x14001683f  test    eax, eax
0x140016841  jg      short loc_14001684F
0x140016843  lfence
0x140016846  mov     rcx, [rdx]
0x140016849  mov     rax, [rcx]
0x14001684c  call    qword ptr [rax+8]
0x14001684f  mov     edi, [rsi+3Ch]
0x140016852  shr     edi, 0Dh
0x140016855  and     dil, 1
0x140016859  mov     r14, [rsi+10h]
0x14001685d  cmp     qword ptr [r14+0E8h], 0
0x140016865  jnz     short loc_1400168B1
0x140016867  mov     rcx, [r14+0E0h]; hToken
0x14001686e  call    cs:__imp_ImpersonateLoggedOnUser
0x140016874  test    eax, eax
0x140016876  setnz   bl
0x140016879  mov     [rbp+var_28], bl
0x14001687c  mov     rdx, [r14+78h]; bool
0x140016880  mov     cl, dil; this
0x140016883  call    ?InitializeRegRootHive@RegistryDetouring@@YAJ_NPEBG@Z; RegistryDetouring::InitializeRegRootHive(bool,ushort const *)
0x140016888  mov     edi, eax
0x14001688a  test    eax, eax
0x14001688c  jns     short loc_1400168A3
0x14001688e  lfence
0x140016891  xor     r8d, r8d; unsigned __int16 *
0x140016894  mov     edx, eax; int
0x140016896  lea     rcx, aFailedToInitia; "Failed to initialize Registry Root Hive"
0x14001689d  call    ?LogError@CLogger@@SAXPEBGJ0@Z; CLogger::LogError(ushort const *,long,ushort const *)
0x1400168a2  nop
0x1400168a3  test    bl, bl
0x1400168a5  jz      short loc_1400168AD
0x1400168a7  call    cs:__imp_RevertToSelf
0x1400168ad  test    edi, edi
0x1400168af  js      short loc_1400168E0
0x1400168b1  mov     rcx, rsi; this
0x1400168b4  call    ?EnsureMasterPkgDefSettingsAreSet@CPkgDefManagement@PkgDef@VisualStudio@Microsoft@@AEAAJXZ; Microsoft::VisualStudio::PkgDef::CPkgDefManagement::EnsureMasterPkgDefSettingsAreSet(void)
0x1400168b9  mov     edi, eax
0x1400168bb  test    eax, eax
0x1400168bd  js      short loc_1400168E0
0x1400168bf  mov     eax, [rsi+3Ch]
0x1400168c2  shr     eax, 0Bh
0x1400168c5  test    al, 1
0x1400168c7  jz      short loc_1400168CD
0x1400168c9  xor     edi, edi
0x1400168cb  jmp     short loc_1400168E0
0x1400168cd  lfence
0x1400168d0  mov     rax, [rsi]
0x1400168d3  xor     edx, edx
0x1400168d5  mov     rcx, rsi
0x1400168d8  call    qword ptr [rax+0C8h]
0x1400168de  mov     edi, eax
0x1400168e0  mov     rdx, [rbp+var_20]
0x1400168e4  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1400168e8  mov     ecx, r12d
0x1400168eb  lock xadd [rdx+10h], ecx
0x1400168f0  add     ecx, r12d
0x1400168f3  test    ecx, ecx
0x1400168f5  jg      short loc_140016910
0x1400168f7  lfence
0x1400168fa  mov     rcx, [rdx]
0x1400168fd  mov     rax, [rcx]
0x140016900  call    qword ptr [rax+8]
0x140016903  nop
0x140016904  nop     dword ptr [rax+00h]
0x140016908  nop     dword ptr [rax+rax+00000000h]
0x140016910  mov     rdx, [rbp+var_18]
0x140016914  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140016918  mov     eax, r12d
0x14001691b  lock xadd [rdx+10h], eax
0x140016920  add     eax, r12d
0x140016923  test    eax, eax
0x140016925  jg      short loc_140016933
0x140016927  lfence
0x14001692a  mov     rcx, [rdx]
0x14001692d  mov     rax, [rcx]
0x140016930  call    qword ptr [rax+8]
0x140016933  mov     eax, edi
0x140016935  mov     rcx, [rbp+var_10]
0x140016939  xor     rcx, rsp; StackCookie
0x14001693c  call    __security_check_cookie
0x140016941  lea     r11, [rsp+50h+var_s0]
0x140016946  mov     rbx, [r11+28h]
0x14001694a  mov     rsi, [r11+30h]
0x14001694e  mov     rdi, [r11+38h]
0x140016952  mov     rsp, r11
0x140016955  pop     r14
0x140016957  pop     r12
0x140016959  pop     rbp
0x14001695a  retn
0x14001695b  mov     ecx, 80004005h; int
0x140016960  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140016966  jmp     short $+2
0x140016968  nop
0x140016969  mov     ecx, 80004005h; int
0x14001696e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
