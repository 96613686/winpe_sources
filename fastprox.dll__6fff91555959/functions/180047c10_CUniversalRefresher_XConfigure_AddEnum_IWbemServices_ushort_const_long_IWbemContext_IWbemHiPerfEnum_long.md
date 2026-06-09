# CUniversalRefresher::XConfigure::AddEnum(IWbemServices *,ushort const *,long,IWbemContext *,IWbemHiPerfEnum * *,long *)

- ea: `0x180047c10`
- end: `0x1800482b2`
- name: `?AddEnum@XConfigure@CUniversalRefresher@@UEAAJPEAUIWbemServices@@PEBGJPEAUIWbemContext@@PEAPEAUIWbemHiPerfEnum@@PEAJ@Z`
- size: `1698`
- prototype: `__int64 __fastcall(CUniversalRefresher::XConfigure *this, struct IWbemServices *, unsigned __int16 *, unsigned int, struct IWbemContext *, struct IWbemHiPerfEnum **, int *)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180037120`
- `0x180047c10`
- `0x180048df0`
- `0x180048f08`
- `0x180048f30`
- `0x180049704`
- `0x180049840`
- `0x180049900`
- `0x1800868d8`
- `0x180087178`
- `0x180087d0c`
- `0x1800919b0`
- `0x18009e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800481f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800481f4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180048099`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180048099`
- `wbemcomn!GetMemLogObject` at `0x180047e5e`
- `wbemcomn!GetMemLogObject` at `0x180047f01`
- `wbemcomn!GetMemLogObject` at `0x180047f33`
- `wbemcomn!GetMemLogObject` at `0x180047f83`
- `wbemcomn!GetMemLogObject` at `0x180047fba`
- `wbemcomn!GetMemLogObject` at `0x180047ff4`
- `wbemcomn!GetMemLogObject` at `0x18004803a`
- `wbemcomn!GetMemLogObject` at `0x1800480cd`
- `wbemcomn!GetMemLogObject` at `0x18004811e`
- `wbemcomn!GetMemLogObject` at `0x180048179`
- `wbemcomn!GetMemLogObject` at `0x180047e5e`
- `wbemcomn!GetMemLogObject` at `0x180047f01`
- `wbemcomn!GetMemLogObject` at `0x180047f33`
- `wbemcomn!GetMemLogObject` at `0x180047f83`
- `wbemcomn!GetMemLogObject` at `0x180047fba`
- `wbemcomn!GetMemLogObject` at `0x180047ff4`
- `wbemcomn!GetMemLogObject` at `0x18004803a`
- `wbemcomn!GetMemLogObject` at `0x1800480cd`
- `wbemcomn!GetMemLogObject` at `0x18004811e`
- `wbemcomn!GetMemLogObject` at `0x180048179`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180047e69`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180047f0f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180047f41`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180047f8e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180047fc5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180047fff`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180048045`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800480dd`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180048129`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180048189`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180047e69`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180047f0f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180047f41`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180047f8e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180047fc5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180047fff`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180048045`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800480dd`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180048129`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180048189`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CUniversalRefresher::XConfigure::AddEnum(
        CUniversalRefresher::XConfigure *this,
        struct IWbemServices *a2,
        unsigned __int16 *a3,
        unsigned int a4,
        struct IWbemContext *a5,
        struct IWbemHiPerfEnum **a6,
        int *a7)
{
  struct IWbemContext *v10; // rsi
  CSharedLock *v11; // r15
  int RefreshingServices; // ebx
  struct IWbemRefreshingServices *v13; // rbx
  LPWSTR pwszServerPrincName; // rdi
  HRESULT Instance; // esi
  int v16; // eax
  CMemoryLog *v17; // rax
  CWbemRefreshingSvc *v18; // rcx
  __int64 v20; // rdx
  CMemoryLog *v21; // rax
  CWbemRefreshingSvc *v22; // rcx
  CMemoryLog *MemLogObject; // rax
  __int64 v24; // rdx
  CMemoryLog *v25; // rax
  CWbemRefreshingSvc *v26; // rcx
  CMemoryLog *v27; // rax
  __int64 v28; // rdx
  CMemoryLog *v29; // rax
  CMemoryLog *v30; // rax
  CMemoryLog *v31; // rax
  CWbemRefreshingSvc *v32; // rcx
  __int64 v33; // rdx
  __int64 v34; // r9
  CMemoryLog *v35; // rax
  CMemoryLog *v36; // rax
  struct IWbemContext *ppv; // [rsp+20h] [rbp-E0h]
  struct IWbemHiPerfEnum **v38; // [rsp+28h] [rbp-D8h]
  struct IWbemRefreshingServices *v39; // [rsp+50h] [rbp-B0h] BYREF
  int *v40; // [rsp+58h] [rbp-A8h]
  int v41; // [rsp+60h] [rbp-A0h]
  unsigned int v42; // [rsp+64h] [rbp-9Ch]
  struct IWbemContext *v43; // [rsp+68h] [rbp-98h]
  struct IWbemServices *v44; // [rsp+70h] [rbp-90h]
  __int64 v45; // [rsp+78h] [rbp-88h] BYREF
  struct IWbemRefreshingServices *v46; // [rsp+80h] [rbp-80h]
  __int64 v47; // [rsp+88h] [rbp-78h] BYREF
  struct _COAUTHINFO pv; // [rsp+98h] [rbp-68h] BYREF
  LPWSTR v50; // [rsp+C0h] [rbp-40h]
  _OWORD v51[3]; // [rsp+C8h] [rbp-38h] BYREF
  int v52[2]; // [rsp+F8h] [rbp-8h]

  v42 = a4;
  v44 = a2;
  v10 = a5;
  v43 = a5;
  v40 = a7;
  if ( !a2 || !a3 || !a6 || !*a3 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2147217400);
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 2147749896LL;
    }
    v24 = 26;
    goto LABEL_35;
  }
  if ( (a4 & 0xFFFDFFFF) != 0 )
  {
    v21 = GetMemLogObject();
    CMemoryLog::Write(v21, -2147217400);
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 2147749896LL;
    }
    v24 = 27;
LABEL_35:
    WPP_SF_d(*((_QWORD *)v22 + 2), v24, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids, 2147749896LL);
    return 2147749896LL;
  }
  v47 = *((_QWORD *)this + 1) + 448LL;
  v11 = (CSharedLock *)(v47 + 16);
  if ( !(unsigned int)CSharedLock::Lock((CSharedLock *)(v47 + 16), 0x2710u) )
  {
    v31 = GetMemLogObject();
    Instance = -2147217321;
    CMemoryLog::Write(v31, -2147217321);
    v32 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_69;
    }
    v33 = 28;
    v34 = 2147749975LL;
    goto LABEL_68;
  }
  if ( !*(_QWORD *)(*((_QWORD *)this + 1) + 472LL) )
  {
    Instance = CoCreateInstance(&CLSID_WbemDefPath, 0, 1u, &IID_IWbemPath, (LPVOID *)(*((_QWORD *)this + 1) + 472LL));
    if ( Instance < 0 )
    {
      v35 = GetMemLogObject();
      CMemoryLog::Write(v35, Instance);
      v32 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_69;
      }
      v33 = 29;
      v34 = (unsigned int)Instance;
      goto LABEL_68;
    }
    v10 = v43;
  }
  RefreshingServices = (*(__int64 (__fastcall **)(_QWORD, __int64, unsigned __int16 *))(**(_QWORD **)(*((_QWORD *)this + 1) + 472LL)
                                                                                      + 24LL))(
                         *(_QWORD *)(*((_QWORD *)this + 1) + 472LL),
                         4,
                         a3);
  if ( RefreshingServices < 0 )
  {
    v30 = GetMemLogObject();
    CMemoryLog::Write(v30, RefreshingServices);
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_37;
    }
    v28 = 30;
    goto LABEL_63;
  }
  v45 = 0;
  RefreshingServices = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *))(**(_QWORD **)(*((_QWORD *)this + 1) + 472LL)
                                                                            + 40LL))(
                         *(_QWORD *)(*((_QWORD *)this + 1) + 472LL),
                         0,
                         &v45);
  if ( RefreshingServices >= 0 )
  {
    if ( (v45 & 4) != 0 )
    {
      (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(*((_QWORD *)this + 1) + 472LL) + 24LL))(
        *(_QWORD *)(*((_QWORD *)this + 1) + 472LL),
        4);
      v39 = 0;
      memset(&pv, 0, sizeof(pv));
      RefreshingServices = CUniversalRefresher::GetRefreshingServices((IUnknown *)a2, &v39, &pv);
      if ( RefreshingServices >= 0 )
      {
        v13 = v39;
        v46 = v39;
        pwszServerPrincName = pv.pwszServerPrincName;
        v50 = pv.pwszServerPrincName;
        memset(v51, 0, sizeof(v51));
        *(_QWORD *)v52 = 0;
        LODWORD(v51[0]) = 0;
        v41 = 0;
        LODWORD(v38) = 2;
        ppv = v10;
        Instance = (*(__int64 (__fastcall **)(struct IWbemRefreshingServices *, __int64, unsigned __int16 *, _QWORD))(*(_QWORD *)v39 + 40LL))(
                     v39,
                     *((_QWORD *)this + 1) + 416LL,
                     a3,
                     v42);
        if ( Instance < 0 )
        {
          v29 = GetMemLogObject();
          CMemoryLog::Write(v29, Instance);
          v18 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_19;
          }
          v20 = 34;
          goto LABEL_28;
        }
        switch ( LODWORD(v51[0]) )
        {
          case 1:
            v16 = CUniversalRefresher::AddDirectEnum(
                    *((CUniversalRefresher **)this + 1),
                    (const struct _WBEM_REFRESH_INFO_DIRECT *)((char *)v51 + 8),
                    v44,
                    a3,
                    v43,
                    a6,
                    v40);
            break;
          case 2:
            v16 = CUniversalRefresher::AddClientLoadableEnum(
                    *((CUniversalRefresher **)this + 1),
                    (const struct _WBEM_REFRESH_INFO_CLIENT_LOADABLE *)((char *)v51 + 8),
                    (struct IUnknown *)v44,
                    a3,
                    v43,
                    a6,
                    v40);
            break;
          case 3:
            v16 = CUniversalRefresher::AddRemoteEnum(
                    *((CUniversalRefresher **)this + 1),
                    v39,
                    (const struct _WBEM_REFRESH_INFO_REMOTE *)((char *)v51 + 8),
                    a3,
                    v52[0],
                    (struct IWbemContext *)v38,
                    a6,
                    v40,
                    &pv);
            break;
          case 6:
            v16 = CUniversalRefresher::AddNonHiPerfEnum(
                    *((CUniversalRefresher **)this + 1),
                    (const struct _WBEM_REFRESH_INFO_NON_HIPERF *)((char *)v51 + 8),
                    v44,
                    a3,
                    ppv,
                    a6,
                    v40,
                    &pv);
            break;
          default:
            Instance = -2147217386;
LABEL_17:
            v17 = GetMemLogObject();
            CMemoryLog::Write(v17, Instance);
LABEL_18:
            v18 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_19;
            }
            v20 = 35;
LABEL_28:
            WPP_SF_d(*((_QWORD *)v18 + 2), v20, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids, (unsigned int)Instance);
LABEL_19:
            CRefreshInfo::~CRefreshInfo((CRefreshInfo *)v51);
            if ( pwszServerPrincName )
              CoTaskMemFree(pwszServerPrincName);
            if ( v13 )
              (*(void (__fastcall **)(struct IWbemRefreshingServices *))(*(_QWORD *)v13 + 16LL))(v13);
            v46 = 0;
            CSharedLock::Unlock(v11);
            return (unsigned int)Instance;
        }
        Instance = v16;
        if ( v16 >= 0 )
          goto LABEL_18;
        goto LABEL_17;
      }
      v25 = GetMemLogObject();
      CMemoryLog::Write(v25, RefreshingServices);
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_37;
      }
      v28 = 33;
      goto LABEL_63;
    }
    v36 = GetMemLogObject();
    Instance = -2147217386;
    CMemoryLog::Write(v36, -2147217386);
    v32 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
LABEL_69:
      CHiPerfLockAccess::~CHiPerfLockAccess((CHiPerfLockAccess *)&v47);
      return (unsigned int)Instance;
    }
    v33 = 32;
    v34 = 2147749910LL;
LABEL_68:
    WPP_SF_d(*((_QWORD *)v32 + 2), v33, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids, v34);
    goto LABEL_69;
  }
  v27 = GetMemLogObject();
  CMemoryLog::Write(v27, RefreshingServices);
  v26 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
  {
    goto LABEL_37;
  }
  v28 = 31;
LABEL_63:
  WPP_SF_d(*((_QWORD *)v26 + 2), v28, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids, (unsigned int)RefreshingServices);
LABEL_37:
  CSharedLock::Unlock(v11);
  return (unsigned int)RefreshingServices;
}

```

## disassembly

```asm
0x180047c10  push    rbp
0x180047c12  push    rbx
0x180047c13  push    rsi
0x180047c14  push    rdi
0x180047c15  push    r12
0x180047c17  push    r13
0x180047c19  push    r14
0x180047c1b  push    r15
0x180047c1d  lea     rbp, [rsp-18h]
0x180047c22  sub     rsp, 118h
0x180047c29  mov     rax, cs:__security_cookie
0x180047c30  xor     rax, rsp
0x180047c33  mov     [rbp+50h+var_50], rax
0x180047c37  mov     [rsp+150h+var_EC], r9d
0x180047c3c  mov     r12, r8
0x180047c3f  mov     rdi, rdx
0x180047c42  mov     [rsp+150h+var_E0], rdx
0x180047c47  mov     r14, rcx
0x180047c4a  mov     rsi, [rbp+50h+arg_20]
0x180047c51  mov     [rsp+150h+var_E8], rsi
0x180047c56  mov     r13, [rbp+50h+arg_28]
0x180047c5d  mov     rax, [rbp+50h+arg_30]
0x180047c64  mov     [rsp+150h+var_F8], rax
0x180047c69  test    rdx, rdx
0x180047c6c  jz      loc_180047F33
0x180047c72  test    r8, r8
0x180047c75  jz      loc_180047F33
0x180047c7b  test    r13, r13
0x180047c7e  jz      loc_180047F33
0x180047c84  xor     eax, eax
0x180047c86  cmp     ax, [r8]
0x180047c8a  jz      loc_180047F33
0x180047c90  test    r9d, 0FFFDFFFFh
0x180047c97  jnz     loc_180047F01
0x180047c9d  mov     rax, [rcx+8]
0x180047ca1  add     rax, 1C0h
0x180047ca7  mov     [rbp+50h+var_C8], rax
0x180047cab  mov     [rbp+50h+var_C0], 0
0x180047cb2  lea     r15, [rax+10h]
0x180047cb6  mov     edx, 2710h; unsigned int
0x180047cbb  mov     rcx, r15; this
0x180047cbe  call    ?Lock@CSharedLock@@QEAAHK@Z; CSharedLock::Lock(ulong)
0x180047cc3  mov     [rbp+50h+var_C0], eax
0x180047cc6  test    eax, eax
0x180047cc8  jz      loc_1800480CD
0x180047cce  mov     rax, [r14+8]
0x180047cd2  add     rax, 1D8h
0x180047cd8  cmp     qword ptr [rax], 0
0x180047cdc  jz      loc_180048080
0x180047ce2  mov     rax, [r14+8]
0x180047ce6  mov     rcx, [rax+1D8h]
0x180047ced  mov     rax, [rcx]
0x180047cf0  mov     r8, r12
0x180047cf3  mov     edx, 4
0x180047cf8  mov     rax, [rax+18h]
0x180047cfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047d01  mov     ebx, eax
0x180047d03  test    eax, eax
0x180047d05  js      loc_18004803A
0x180047d0b  mov     [rsp+150h+var_D8], 0
0x180047d14  mov     rax, [r14+8]
0x180047d18  mov     rcx, [rax+1D8h]
0x180047d1f  mov     rax, [rcx]
0x180047d22  lea     r8, [rsp+150h+var_D8]
0x180047d27  xor     edx, edx
0x180047d29  mov     rax, [rax+28h]
0x180047d2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047d32  mov     ebx, eax
0x180047d34  test    eax, eax
0x180047d36  js      loc_180047FBA
0x180047d3c  test    byte ptr [rsp+150h+var_D8], 4
0x180047d41  jz      loc_180048179
0x180047d47  mov     rax, [r14+8]
0x180047d4b  mov     rcx, [rax+1D8h]
0x180047d52  mov     rax, [rcx]
0x180047d55  xor     r8d, r8d
0x180047d58  lea     edx, [r8+4]
0x180047d5c  mov     rax, [rax+18h]
0x180047d60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047d65  mov     [rsp+150h+var_100], 0
0x180047d6e  xorps   xmm0, xmm0
0x180047d71  xor     eax, eax
0x180047d73  movups  xmmword ptr [rbp+50h+pv], xmm0
0x180047d77  movups  [rbp+50h+var_A8], xmm0
0x180047d7b  mov     [rbp+50h+var_98], rax
0x180047d7f  lea     r8, [rbp+50h+pv]; struct _COAUTHINFO *
0x180047d83  lea     rdx, [rsp+150h+var_100]; struct IWbemRefreshingServices **
0x180047d88  mov     rcx, rdi; pProxy
0x180047d8b  call    ?GetRefreshingServices@CUniversalRefresher@@SAJPEAUIWbemServices@@PEAPEAUIWbemRefreshingServices@@PEAU_COAUTHINFO@@@Z; CUniversalRefresher::GetRefreshingServices(IWbemServices *,IWbemRefreshingServices * *,_COAUTHINFO *)
0x180047d90  mov     ebx, eax
0x180047d92  test    eax, eax
0x180047d94  js      loc_180047F83
0x180047d9a  mov     rbx, [rsp+150h+var_100]
0x180047d9f  mov     [rbp+50h+var_D0], rbx
0x180047da3  mov     rdi, [rbp+50h+pv+8]
0x180047da7  mov     [rbp+50h+var_90], rdi
0x180047dab  xorps   xmm0, xmm0
0x180047dae  xor     eax, eax
0x180047db0  movups  [rbp+50h+var_88], xmm0
0x180047db4  movups  [rbp+50h+var_78], xmm0
0x180047db8  movups  [rbp+50h+var_68], xmm0
0x180047dbc  mov     qword ptr [rbp+50h+var_58], rax
0x180047dc0  mov     dword ptr [rbp+50h+var_88], eax
0x180047dc3  mov     [rsp+150h+var_F0], eax
0x180047dc7  mov     rcx, [rsp+150h+var_100]
0x180047dcc  mov     rax, [rcx]
0x180047dcf  mov     rdx, [r14+8]
0x180047dd3  add     rdx, 1A0h
0x180047dda  lea     r8, [rsp+150h+var_F0]
0x180047ddf  mov     [rsp+150h+var_118], r8
0x180047de4  lea     r8, [rbp+50h+var_88]
0x180047de8  mov     [rsp+150h+var_120], r8
0x180047ded  mov     dword ptr [rsp+150h+var_128], 2; struct IWbemContext *
0x180047df5  mov     [rsp+150h+ppv], rsi; struct IWbemContext *
0x180047dfa  mov     r9d, [rsp+150h+var_EC]
0x180047dff  mov     r8, r12
0x180047e02  mov     rax, [rax+28h]
0x180047e06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047e0b  mov     esi, eax
0x180047e0d  test    eax, eax
0x180047e0f  js      loc_180047FF4
0x180047e15  mov     ecx, dword ptr [rbp+50h+var_88]
0x180047e18  sub     ecx, 1
0x180047e1b  jz      loc_18004827E
0x180047e21  sub     ecx, 1
0x180047e24  jnz     loc_1800481FF
0x180047e2a  mov     rax, [rsp+150h+var_F8]
0x180047e2f  mov     [rsp+150h+var_120], rax; int *
0x180047e34  mov     [rsp+150h+var_128], r13; struct IWbemHiPerfEnum **
0x180047e39  mov     rax, [rsp+150h+var_E8]
0x180047e3e  mov     [rsp+150h+ppv], rax; struct IWbemContext *
0x180047e43  mov     r9, r12; unsigned __int16 *
0x180047e46  mov     r8, [rsp+150h+var_E0]; struct IWbemServices *
0x180047e4b  lea     rdx, [rbp+50h+var_88+8]; struct _WBEM_REFRESH_INFO_CLIENT_LOADABLE *
0x180047e4f  mov     rcx, [r14+8]; this
0x180047e53  call    ?AddClientLoadableEnum@CUniversalRefresher@@IEAAJAEBU_WBEM_REFRESH_INFO_CLIENT_LOADABLE@@PEAUIWbemServices@@PEBGPEAUIWbemContext@@PEAPEAUIWbemHiPerfEnum@@PEAJ@Z; CUniversalRefresher::AddClientLoadableEnum(_WBEM_REFRESH_INFO_CLIENT_LOADABLE const &,IWbemServices *,ushort const *,IWbemContext *,IWbemHiPerfEnum * *,long *)
0x180047e58  mov     esi, eax
0x180047e5a  test    eax, eax
0x180047e5c  jns     short loc_180047E6F
0x180047e5e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180047e64  mov     edx, esi
0x180047e66  mov     rcx, rax
0x180047e69  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180047e6f  lea     rax, WPP_GLOBAL_Control
0x180047e76  mov     rcx, cs:WPP_GLOBAL_Control
0x180047e7d  cmp     rcx, rax
0x180047e80  jnz     short loc_180047EDB
0x180047e82  lea     rcx, [rbp+50h+var_88]; this
0x180047e86  call    ??1CRefreshInfo@@QEAA@XZ; CRefreshInfo::~CRefreshInfo(void)
0x180047e8b  nop
0x180047e8c  test    rdi, rdi
0x180047e8f  jnz     loc_1800481F1
0x180047e95  test    rbx, rbx
0x180047e98  jz      short loc_180047EA9
0x180047e9a  mov     rax, [rbx]
0x180047e9d  mov     rcx, rbx
0x180047ea0  mov     rax, [rax+10h]
0x180047ea4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047ea9  mov     [rbp+50h+var_D0], 0
0x180047eb1  mov     rcx, r15; this
0x180047eb4  call    ?Unlock@CSharedLock@@QEAAHXZ; CSharedLock::Unlock(void)
0x180047eb9  mov     eax, esi
0x180047ebb  mov     rcx, [rbp+50h+var_50]
0x180047ebf  xor     rcx, rsp; StackCookie
0x180047ec2  call    __security_check_cookie
0x180047ec7  add     rsp, 118h
0x180047ece  pop     r15
0x180047ed0  pop     r14
0x180047ed2  pop     r13
0x180047ed4  pop     r12
0x180047ed6  pop     rdi
0x180047ed7  pop     rsi
0x180047ed8  pop     rbx
0x180047ed9  pop     rbp
0x180047eda  retn
0x180047edb  test    byte ptr [rcx+1Ch], 1
0x180047edf  jz      short loc_180047E82
0x180047ee1  cmp     byte ptr [rcx+19h], 2
0x180047ee5  jb      short loc_180047E82
0x180047ee7  mov     edx, 23h ; '#'
0x180047eec  mov     r9d, esi
0x180047eef  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x180047ef6  mov     rcx, [rcx+10h]
0x180047efa  call    WPP_SF_d
0x180047eff  jmp     short loc_180047E82
0x180047f01  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180047f07  mov     edx, 80041008h
0x180047f0c  mov     rcx, rax
0x180047f0f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180047f15  lea     rax, WPP_GLOBAL_Control
0x180047f1c  mov     rcx, cs:WPP_GLOBAL_Control
0x180047f23  cmp     rcx, rax
0x180047f26  jnz     loc_1800480AF
0x180047f2c  mov     eax, 80041008h
0x180047f31  jmp     short loc_180047EBB
0x180047f33  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180047f39  mov     edx, 80041008h
0x180047f3e  mov     rcx, rax
0x180047f41  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180047f47  lea     rax, WPP_GLOBAL_Control
0x180047f4e  mov     rcx, cs:WPP_GLOBAL_Control
0x180047f55  cmp     rcx, rax
0x180047f58  jz      short loc_180047F2C
0x180047f5a  test    byte ptr [rcx+1Ch], 1
0x180047f5e  jz      short loc_180047F2C
0x180047f60  cmp     byte ptr [rcx+19h], 2
0x180047f64  jb      short loc_180047F2C
0x180047f66  mov     edx, 1Ah
0x180047f6b  mov     r9d, 80041008h
0x180047f71  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x180047f78  mov     rcx, [rcx+10h]
0x180047f7c  call    WPP_SF_d
0x180047f81  jmp     short loc_180047F2C
0x180047f83  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180047f89  mov     edx, ebx
0x180047f8b  mov     rcx, rax
0x180047f8e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180047f94  lea     rax, WPP_GLOBAL_Control
0x180047f9b  mov     rcx, cs:WPP_GLOBAL_Control
0x180047fa2  cmp     rcx, rax
0x180047fa5  jnz     loc_1800481D8
0x180047fab  mov     rcx, r15; this
0x180047fae  call    ?Unlock@CSharedLock@@QEAAHXZ; CSharedLock::Unlock(void)
0x180047fb3  mov     eax, ebx
0x180047fb5  jmp     loc_180047EBB
0x180047fba  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180047fc0  mov     edx, ebx
0x180047fc2  mov     rcx, rax
0x180047fc5  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180047fcb  lea     rax, WPP_GLOBAL_Control
0x180047fd2  mov     rcx, cs:WPP_GLOBAL_Control
0x180047fd9  cmp     rcx, rax
0x180047fdc  jz      short loc_180047FAB
0x180047fde  test    byte ptr [rcx+1Ch], 1
0x180047fe2  jz      short loc_180047FAB
0x180047fe4  cmp     byte ptr [rcx+19h], 2
0x180047fe8  jb      short loc_180047FAB
0x180047fea  mov     edx, 1Fh
0x180047fef  jmp     loc_180048161
0x180047ff4  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180047ffa  mov     edx, esi
0x180047ffc  mov     rcx, rax
0x180047fff  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180048005  lea     rax, WPP_GLOBAL_Control
0x18004800c  mov     rcx, cs:WPP_GLOBAL_Control
0x180048013  cmp     rcx, rax
0x180048016  jz      loc_180047E82
0x18004801c  test    byte ptr [rcx+1Ch], 1
0x180048020  jz      loc_180047E82
0x180048026  cmp     byte ptr [rcx+19h], 2
0x18004802a  jb      loc_180047E82
0x180048030  mov     edx, 22h ; '"'
0x180048035  jmp     loc_180047EEC
0x18004803a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180048040  mov     edx, ebx
0x180048042  mov     rcx, rax
0x180048045  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004804b  lea     rax, WPP_GLOBAL_Control
0x180048052  mov     rcx, cs:WPP_GLOBAL_Control
0x180048059  cmp     rcx, rax
0x18004805c  jz      loc_180047FAB
0x180048062  test    byte ptr [rcx+1Ch], 1
0x180048066  jz      loc_180047FAB
0x18004806c  cmp     byte ptr [rcx+19h], 2
0x180048070  jb      loc_180047FAB
0x180048076  mov     edx, 1Eh
0x18004807b  jmp     loc_180048161
0x180048080  mov     [rsp+150h+ppv], rax; ppv
0x180048085  lea     r9, IID_IWbemPath; riid
0x18004808c  xor     edx, edx; pUnkOuter
0x18004808e  lea     r8d, [rdx+1]; dwClsContext
0x180048092  lea     rcx, CLSID_WbemDefPath; rclsid
0x180048099  call    cs:__imp_CoCreateInstance
0x18004809f  mov     esi, eax
0x1800480a1  test    eax, eax
0x1800480a3  js      short loc_18004811E
0x1800480a5  mov     rsi, [rsp+150h+var_E8]
0x1800480aa  jmp     loc_180047CE2
0x1800480af  test    byte ptr [rcx+1Ch], 1
0x1800480b3  jz      loc_180047F2C
0x1800480b9  cmp     byte ptr [rcx+19h], 2
0x1800480bd  jb      loc_180047F2C
0x1800480c3  mov     edx, 1Bh
0x1800480c8  jmp     loc_180047F6B
0x1800480cd  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800480d3  mov     esi, 80041057h
0x1800480d8  mov     edx, esi
0x1800480da  mov     rcx, rax
0x1800480dd  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800480e3  lea     rax, WPP_GLOBAL_Control
0x1800480ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800480f1  cmp     rcx, rax
0x1800480f4  jz      loc_1800481CA
0x1800480fa  test    byte ptr [rcx+1Ch], 1
0x1800480fe  jz      loc_1800481CA
0x180048104  cmp     byte ptr [rcx+19h], 2
0x180048108  jb      loc_1800481CA
0x18004810e  mov     edx, 1Ch
0x180048113  mov     r9d, 80041057h
0x180048119  jmp     loc_1800481B9
  ... truncated ...
```
