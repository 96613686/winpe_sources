# CUniversalRefresher::XConfigure::AddObjectByPath(IWbemServices *,ushort const *,long,IWbemContext *,IWbemClassObject * *,long *)

- ea: `0x180046ee0`
- end: `0x180047365`
- name: `?AddObjectByPath@XConfigure@CUniversalRefresher@@UEAAJPEAUIWbemServices@@PEBGJPEAUIWbemContext@@PEAPEAUIWbemClassObject@@PEAJ@Z`
- size: `1157`
- prototype: `__int64 __fastcall(CUniversalRefresher::XConfigure *this, IUnknown *, unsigned __int16 *, unsigned int, struct IWbemContext *, struct IWbemClassObject **, int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180046a70`

## callees

- `0x180037120`
- `0x1800465c0`
- `0x180046d48`
- `0x180046ee0`
- `0x180048df0`
- `0x180048f08`
- `0x180048f30`
- `0x180049704`
- `0x180049840`
- `0x180086af8`
- `0x180087e14`
- `0x1800919b0`
- `0x18009e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004719e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004719e`
- `wbemcomn!GetMemLogObject` at `0x180046f5e`
- `wbemcomn!GetMemLogObject` at `0x180046fd4`
- `wbemcomn!GetMemLogObject` at `0x180047066`
- `wbemcomn!GetMemLogObject` at `0x18004713f`
- `wbemcomn!GetMemLogObject` at `0x1800472ac`
- `wbemcomn!GetMemLogObject` at `0x1800472f2`
- `wbemcomn!GetMemLogObject` at `0x180046f5e`
- `wbemcomn!GetMemLogObject` at `0x180046fd4`
- `wbemcomn!GetMemLogObject` at `0x180047066`
- `wbemcomn!GetMemLogObject` at `0x18004713f`
- `wbemcomn!GetMemLogObject` at `0x1800472ac`
- `wbemcomn!GetMemLogObject` at `0x1800472f2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180046f6c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180046fe4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180047071`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004714e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800472b7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180047300`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180046f6c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180046fe4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180047071`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004714e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800472b7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180047300`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CUniversalRefresher::XConfigure::AddObjectByPath(
        CUniversalRefresher::XConfigure *this,
        IUnknown *a2,
        unsigned __int16 *a3,
        unsigned int a4,
        struct IWbemContext *a5,
        struct IWbemClassObject **a6,
        int *a7)
{
  CMemoryLog *v10; // rax
  CWbemRefreshingSvc *v11; // rcx
  __int64 v12; // rdx
  CSharedLock *v13; // r13
  CMemoryLog *v14; // rax
  unsigned int RefreshingServices; // ebx
  CMemoryLog *v17; // rax
  struct IWbemRefreshingServices *v18; // rbx
  LPWSTR pwszServerPrincName; // rdi
  CMemoryLog *v20; // rax
  unsigned int v21; // esi
  CWbemRefreshingSvc *v22; // rcx
  __int64 v23; // rdx
  int v24; // eax
  CMemoryLog *v25; // rax
  CMemoryLog *MemLogObject; // rax
  int v28; // [rsp+50h] [rbp-B0h]
  struct IWbemRefreshingServices *v29; // [rsp+58h] [rbp-A8h] BYREF
  int *v30; // [rsp+60h] [rbp-A0h]
  int v31; // [rsp+68h] [rbp-98h] BYREF
  struct IWbemContext *v32; // [rsp+70h] [rbp-90h]
  struct IWbemRefreshingServices *v33; // [rsp+78h] [rbp-88h]
  __int64 v34; // [rsp+80h] [rbp-80h] BYREF
  struct _COAUTHINFO pv; // [rsp+90h] [rbp-70h] BYREF
  LPWSTR v37; // [rsp+B8h] [rbp-48h]
  _OWORD v38[3]; // [rsp+C0h] [rbp-40h] BYREF
  int v39[2]; // [rsp+F0h] [rbp-10h]

  v32 = a5;
  v30 = a7;
  if ( !a2 || !a3 || !a6 || !*a3 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2147217400);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 2147749896LL;
    }
    v12 = 10;
    goto LABEL_53;
  }
  if ( (a4 & 0xFFFDFFFF) != 0 )
  {
    v10 = GetMemLogObject();
    CMemoryLog::Write(v10, -2147217400);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 2147749896LL;
    }
    v12 = 11;
LABEL_53:
    WPP_SF_d(*((_QWORD *)v11 + 2), v12, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids, 2147749896LL);
    return 2147749896LL;
  }
  v34 = *((_QWORD *)this + 1) + 448LL;
  v13 = (CSharedLock *)(v34 + 16);
  if ( !(unsigned int)CSharedLock::Lock((CSharedLock *)(v34 + 16), 0x2710u) )
  {
    v14 = GetMemLogObject();
    RefreshingServices = -2147217321;
    CMemoryLog::Write(v14, -2147217321);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids, 2147749975LL);
    }
    CHiPerfLockAccess::~CHiPerfLockAccess((CHiPerfLockAccess *)&v34);
    return RefreshingServices;
  }
  v29 = 0;
  memset(&pv, 0, sizeof(pv));
  RefreshingServices = CUniversalRefresher::GetRefreshingServices(a2, &v29, &pv);
  if ( (RefreshingServices & 0x80000000) != 0 )
  {
    v17 = GetMemLogObject();
    CMemoryLog::Write(v17, RefreshingServices);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids,
        RefreshingServices);
    }
    CSharedLock::Unlock(v13);
    return RefreshingServices;
  }
  v18 = v29;
  v33 = v29;
  pwszServerPrincName = pv.pwszServerPrincName;
  v37 = pv.pwszServerPrincName;
  memset(v38, 0, sizeof(v38));
  *(_QWORD *)v39 = 0;
  LODWORD(v38[0]) = 0;
  v31 = 0;
  v28 = (*(__int64 (__fastcall **)(struct IWbemRefreshingServices *, __int64, unsigned __int16 *, _QWORD, struct IWbemContext *, int, _OWORD *, int *))(*(_QWORD *)v29 + 24LL))(
          v29,
          *((_QWORD *)this + 1) + 416LL,
          a3,
          a4,
          v32,
          2,
          v38,
          &v31);
  if ( v28 >= 0 )
  {
    switch ( LODWORD(v38[0]) )
    {
      case 1:
        v24 = CUniversalRefresher::AddDirectObject(
                *((CUniversalRefresher **)this + 1),
                (const struct _WBEM_REFRESH_INFO_DIRECT *)((char *)v38 + 8),
                (struct IWbemServices *)a2,
                v32,
                a6,
                v30);
        break;
      case 2:
        v24 = CUniversalRefresher::AddClientLoadableObject(
                *((CUniversalRefresher **)this + 1),
                (const struct _WBEM_REFRESH_INFO_CLIENT_LOADABLE *)((char *)v38 + 8),
                a2,
                v32,
                a6,
                v30);
        break;
      case 3:
        v24 = CUniversalRefresher::AddRemoteObject(
                *((CUniversalRefresher **)this + 1),
                v29,
                (const struct _WBEM_REFRESH_INFO_REMOTE *)((char *)v38 + 8),
                a3,
                v39[0],
                a6,
                v30,
                &pv);
        break;
      case 6:
        v24 = CUniversalRefresher::AddNonHiPerfObject(
                *((CUniversalRefresher **)this + 1),
                (const struct _WBEM_REFRESH_INFO_NON_HIPERF *)((char *)v38 + 8),
                (struct IWbemServices *)a2,
                a3,
                a6,
                v30,
                &pv);
        break;
      default:
        v21 = -2147217386;
LABEL_44:
        v25 = GetMemLogObject();
        CMemoryLog::Write(v25, v21);
LABEL_45:
        v22 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_29;
        }
        v23 = 15;
        goto LABEL_28;
    }
    v21 = v24;
    if ( v24 >= 0 )
      goto LABEL_45;
    goto LABEL_44;
  }
  v20 = GetMemLogObject();
  v21 = v28;
  CMemoryLog::Write(v20, v28);
  v22 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
  {
    goto LABEL_29;
  }
  v23 = 14;
LABEL_28:
  WPP_SF_d(*((_QWORD *)v22 + 2), v23, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids, v21);
LABEL_29:
  CRefreshInfo::~CRefreshInfo((CRefreshInfo *)v38);
  if ( pwszServerPrincName )
    CoTaskMemFree(pwszServerPrincName);
  if ( v18 )
    (*(void (__fastcall **)(struct IWbemRefreshingServices *))(*(_QWORD *)v18 + 16LL))(v18);
  v33 = 0;
  CSharedLock::Unlock(v13);
  return v21;
}

```

## disassembly

```asm
0x180046ee0  push    rbp
0x180046ee2  push    rbx
0x180046ee3  push    rsi
0x180046ee4  push    rdi
0x180046ee5  push    r12
0x180046ee7  push    r13
0x180046ee9  push    r14
0x180046eeb  push    r15
0x180046eed  lea     rbp, [rsp-8]
0x180046ef2  sub     rsp, 108h
0x180046ef9  mov     rax, cs:__security_cookie
0x180046f00  xor     rax, rsp
0x180046f03  mov     [rbp+40h+var_48], rax
0x180046f07  mov     [rsp+140h+var_F0], r9d
0x180046f0c  mov     r15, r8
0x180046f0f  mov     r12, rdx
0x180046f12  mov     rsi, rcx
0x180046f15  mov     rax, [rbp+40h+arg_20]
0x180046f19  mov     [rsp+140h+var_D0], rax
0x180046f1e  mov     r14, [rbp+40h+arg_28]
0x180046f22  mov     rax, [rbp+40h+arg_30]
0x180046f29  mov     [rsp+140h+var_E0], rax
0x180046f2e  test    rdx, rdx
0x180046f31  jz      loc_1800472F2
0x180046f37  test    r8, r8
0x180046f3a  jz      loc_1800472F2
0x180046f40  test    r14, r14
0x180046f43  jz      loc_1800472F2
0x180046f49  xor     eax, eax
0x180046f4b  cmp     ax, [r8]
0x180046f4f  jz      loc_1800472F2
0x180046f55  test    r9d, 0FFFDFFFFh
0x180046f5c  jz      short loc_180046FA7
0x180046f5e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180046f64  mov     edx, 80041008h
0x180046f69  mov     rcx, rax
0x180046f6c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180046f72  lea     rax, WPP_GLOBAL_Control
0x180046f79  mov     rcx, cs:WPP_GLOBAL_Control
0x180046f80  cmp     rcx, rax
0x180046f83  jz      loc_180047340
0x180046f89  test    byte ptr [rcx+1Ch], 1
0x180046f8d  jz      loc_180047340
0x180046f93  cmp     byte ptr [rcx+19h], 2
0x180046f97  jb      loc_180047340
0x180046f9d  mov     edx, 0Bh
0x180046fa2  jmp     loc_18004732A
0x180046fa7  mov     rax, [rcx+8]
0x180046fab  add     rax, 1C0h
0x180046fb1  mov     [rbp+40h+var_C0], rax
0x180046fb5  mov     [rbp+40h+var_B8], 0
0x180046fbc  lea     r13, [rax+10h]
0x180046fc0  mov     edx, 2710h; unsigned int
0x180046fc5  mov     rcx, r13; this
0x180046fc8  call    ?Lock@CSharedLock@@QEAAHK@Z; CSharedLock::Lock(ulong)
0x180046fcd  mov     [rbp+40h+var_B8], eax
0x180046fd0  test    eax, eax
0x180046fd2  jnz     short loc_180047035
0x180046fd4  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180046fda  mov     ebx, 80041057h
0x180046fdf  mov     edx, ebx
0x180046fe1  mov     rcx, rax
0x180046fe4  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180046fea  lea     rax, WPP_GLOBAL_Control
0x180046ff1  mov     rcx, cs:WPP_GLOBAL_Control
0x180046ff8  cmp     rcx, rax
0x180046ffb  jz      short loc_180047025
0x180046ffd  test    byte ptr [rcx+1Ch], 1
0x180047001  jz      short loc_180047025
0x180047003  cmp     byte ptr [rcx+19h], 2
0x180047007  jb      short loc_180047025
0x180047009  mov     edx, 0Ch
0x18004700e  mov     r9d, 80041057h
0x180047014  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x18004701b  mov     rcx, [rcx+10h]
0x18004701f  call    WPP_SF_d
0x180047024  nop
0x180047025  lea     rcx, [rbp+40h+var_C0]; this
0x180047029  call    ??1CHiPerfLockAccess@@QEAA@XZ; CHiPerfLockAccess::~CHiPerfLockAccess(void)
0x18004702e  mov     eax, ebx
0x180047030  jmp     loc_180047345
0x180047035  mov     [rsp+140h+var_E8], 0
0x18004703e  xorps   xmm0, xmm0
0x180047041  xor     eax, eax
0x180047043  movups  xmmword ptr [rbp+40h+pv], xmm0
0x180047047  movups  [rbp+40h+var_A0], xmm0
0x18004704b  mov     [rbp+40h+var_90], rax
0x18004704f  lea     r8, [rbp+40h+pv]; struct _COAUTHINFO *
0x180047053  lea     rdx, [rsp+140h+var_E8]; struct IWbemRefreshingServices **
0x180047058  mov     rcx, r12; pProxy
0x18004705b  call    ?GetRefreshingServices@CUniversalRefresher@@SAJPEAUIWbemServices@@PEAPEAUIWbemRefreshingServices@@PEAU_COAUTHINFO@@@Z; CUniversalRefresher::GetRefreshingServices(IWbemServices *,IWbemRefreshingServices * *,_COAUTHINFO *)
0x180047060  mov     ebx, eax
0x180047062  test    eax, eax
0x180047064  jns     short loc_1800470BC
0x180047066  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004706c  mov     edx, ebx
0x18004706e  mov     rcx, rax
0x180047071  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180047077  lea     rax, WPP_GLOBAL_Control
0x18004707e  mov     rcx, cs:WPP_GLOBAL_Control
0x180047085  cmp     rcx, rax
0x180047088  jz      short loc_1800470AF
0x18004708a  test    byte ptr [rcx+1Ch], 1
0x18004708e  jz      short loc_1800470AF
0x180047090  cmp     byte ptr [rcx+19h], 2
0x180047094  jb      short loc_1800470AF
0x180047096  mov     edx, 0Dh
0x18004709b  mov     r9d, ebx
0x18004709e  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x1800470a5  mov     rcx, [rcx+10h]
0x1800470a9  call    WPP_SF_d
0x1800470ae  nop
0x1800470af  mov     rcx, r13; this
0x1800470b2  call    ?Unlock@CSharedLock@@QEAAHXZ; CSharedLock::Unlock(void)
0x1800470b7  jmp     loc_18004702E
0x1800470bc  mov     rbx, [rsp+140h+var_E8]
0x1800470c1  mov     [rsp+140h+var_C8], rbx
0x1800470c6  mov     rdi, [rbp+40h+pv+8]
0x1800470ca  mov     [rbp+40h+var_88], rdi
0x1800470ce  xorps   xmm0, xmm0
0x1800470d1  xor     eax, eax
0x1800470d3  movups  [rbp+40h+var_80], xmm0
0x1800470d7  movups  [rbp+40h+var_70], xmm0
0x1800470db  movups  [rbp+40h+var_60], xmm0
0x1800470df  mov     qword ptr [rbp+40h+var_50], rax
0x1800470e3  mov     dword ptr [rbp+40h+var_80], eax
0x1800470e6  mov     [rsp+140h+var_D8], eax
0x1800470ea  mov     rcx, [rsp+140h+var_E8]
0x1800470ef  mov     rax, [rcx]
0x1800470f2  mov     rdx, [rsi+8]
0x1800470f6  add     rdx, 1A0h
0x1800470fd  lea     r8, [rsp+140h+var_D8]
0x180047102  mov     [rsp+140h+var_108], r8
0x180047107  lea     r8, [rbp+40h+var_80]
0x18004710b  mov     [rsp+140h+var_110], r8
0x180047110  mov     dword ptr [rsp+140h+var_118], 2
0x180047118  mov     r8, [rsp+140h+var_D0]
0x18004711d  mov     [rsp+140h+var_120], r8
0x180047122  mov     r9d, [rsp+140h+var_F0]
0x180047127  mov     r8, r15
0x18004712a  mov     rax, [rax+18h]
0x18004712e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047133  mov     [rsp+140h+var_F0], eax
0x180047137  test    eax, eax
0x180047139  jns     loc_1800471D1
0x18004713f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180047145  mov     esi, [rsp+140h+var_F0]
0x180047149  mov     edx, esi
0x18004714b  mov     rcx, rax
0x18004714e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180047154  lea     rax, WPP_GLOBAL_Control
0x18004715b  mov     rcx, cs:WPP_GLOBAL_Control
0x180047162  cmp     rcx, rax
0x180047165  jz      short loc_18004718C
0x180047167  test    byte ptr [rcx+1Ch], 1
0x18004716b  jz      short loc_18004718C
0x18004716d  cmp     byte ptr [rcx+19h], 2
0x180047171  jb      short loc_18004718C
0x180047173  mov     edx, 0Eh
0x180047178  mov     r9d, esi
0x18004717b  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x180047182  mov     rcx, [rcx+10h]
0x180047186  call    WPP_SF_d
0x18004718b  nop
0x18004718c  lea     rcx, [rbp+40h+var_80]; this
0x180047190  call    ??1CRefreshInfo@@QEAA@XZ; CRefreshInfo::~CRefreshInfo(void)
0x180047195  nop
0x180047196  test    rdi, rdi
0x180047199  jz      short loc_1800471A5
0x18004719b  mov     rcx, rdi; pv
0x18004719e  call    cs:__imp_CoTaskMemFree
0x1800471a4  nop
0x1800471a5  test    rbx, rbx
0x1800471a8  jz      short loc_1800471B9
0x1800471aa  mov     rax, [rbx]
0x1800471ad  mov     rcx, rbx
0x1800471b0  mov     rax, [rax+10h]
0x1800471b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800471b9  mov     [rsp+140h+var_C8], 0
0x1800471c2  mov     rcx, r13; this
0x1800471c5  call    ?Unlock@CSharedLock@@QEAAHXZ; CSharedLock::Unlock(void)
0x1800471ca  mov     eax, esi
0x1800471cc  jmp     loc_180047345
0x1800471d1  mov     ecx, dword ptr [rbp+40h+var_80]
0x1800471d4  sub     ecx, 1
0x1800471d7  jz      loc_180047282
0x1800471dd  sub     ecx, 1
0x1800471e0  jz      short loc_18004725C
0x1800471e2  sub     ecx, 1
0x1800471e5  jz      short loc_180047226
0x1800471e7  cmp     ecx, 3
0x1800471ea  jz      short loc_1800471F6
0x1800471ec  mov     esi, 80041016h
0x1800471f1  jmp     loc_1800472AC
0x1800471f6  lea     rax, [rbp+40h+pv]
0x1800471fa  mov     [rsp+140h+var_110], rax; struct _COAUTHINFO *
0x1800471ff  mov     rax, [rsp+140h+var_E0]
0x180047204  mov     [rsp+140h+var_118], rax; int *
0x180047209  mov     [rsp+140h+var_120], r14; struct IWbemClassObject **
0x18004720e  mov     r9, r15; unsigned __int16 *
0x180047211  mov     r8, r12; struct IWbemServices *
0x180047214  lea     rdx, [rbp+40h+var_80+8]; struct _WBEM_REFRESH_INFO_NON_HIPERF *
0x180047218  mov     rcx, [rsi+8]; this
0x18004721c  call    ?AddNonHiPerfObject@CUniversalRefresher@@IEAAJAEBU_WBEM_REFRESH_INFO_NON_HIPERF@@PEAUIWbemServices@@PEBGPEAPEAUIWbemClassObject@@PEAJAEAU_COAUTHINFO@@@Z; CUniversalRefresher::AddNonHiPerfObject(_WBEM_REFRESH_INFO_NON_HIPERF const &,IWbemServices *,ushort const *,IWbemClassObject * *,long *,_COAUTHINFO &)
0x180047221  jmp     loc_1800472A6
0x180047226  lea     rax, [rbp+40h+pv]
0x18004722a  mov     [rsp+140h+var_108], rax; struct _COAUTHINFO *
0x18004722f  mov     rax, [rsp+140h+var_E0]
0x180047234  mov     [rsp+140h+var_110], rax; int *
0x180047239  mov     [rsp+140h+var_118], r14; struct IWbemClassObject **
0x18004723e  mov     eax, [rbp+40h+var_50]
0x180047241  mov     dword ptr [rsp+140h+var_120], eax; int
0x180047245  mov     r9, r15; unsigned __int16 *
0x180047248  lea     r8, [rbp+40h+var_80+8]; struct _WBEM_REFRESH_INFO_REMOTE *
0x18004724c  mov     rdx, [rsp+140h+var_E8]; struct IWbemRefreshingServices *
0x180047251  mov     rcx, [rsi+8]; this
0x180047255  call    ?AddRemoteObject@CUniversalRefresher@@IEAAJPEAUIWbemRefreshingServices@@AEBU_WBEM_REFRESH_INFO_REMOTE@@PEBGJPEAPEAUIWbemClassObject@@PEAJPEAU_COAUTHINFO@@@Z; CUniversalRefresher::AddRemoteObject(IWbemRefreshingServices *,_WBEM_REFRESH_INFO_REMOTE const &,ushort const *,long,IWbemClassObject * *,long *,_COAUTHINFO *)
0x18004725a  jmp     short loc_1800472A6
0x18004725c  mov     rax, [rsp+140h+var_E0]
0x180047261  mov     [rsp+140h+var_118], rax; int *
0x180047266  mov     [rsp+140h+var_120], r14; struct IWbemClassObject **
0x18004726b  mov     r9, [rsp+140h+var_D0]; struct IWbemContext *
0x180047270  mov     r8, r12; struct IWbemServices *
0x180047273  lea     rdx, [rbp+40h+var_80+8]; struct _WBEM_REFRESH_INFO_CLIENT_LOADABLE *
0x180047277  mov     rcx, [rsi+8]; this
0x18004727b  call    ?AddClientLoadableObject@CUniversalRefresher@@IEAAJAEBU_WBEM_REFRESH_INFO_CLIENT_LOADABLE@@PEAUIWbemServices@@PEAUIWbemContext@@PEAPEAUIWbemClassObject@@PEAJ@Z; CUniversalRefresher::AddClientLoadableObject(_WBEM_REFRESH_INFO_CLIENT_LOADABLE const &,IWbemServices *,IWbemContext *,IWbemClassObject * *,long *)
0x180047280  jmp     short loc_1800472A6
0x180047282  mov     rax, [rsp+140h+var_E0]
0x180047287  mov     [rsp+140h+var_118], rax; int *
0x18004728c  mov     [rsp+140h+var_120], r14; struct IWbemClassObject **
0x180047291  mov     r9, [rsp+140h+var_D0]; struct IWbemContext *
0x180047296  mov     r8, r12; struct IWbemServices *
0x180047299  lea     rdx, [rbp+40h+var_80+8]; struct _WBEM_REFRESH_INFO_DIRECT *
0x18004729d  mov     rcx, [rsi+8]; this
0x1800472a1  call    ?AddDirectObject@CUniversalRefresher@@IEAAJAEBU_WBEM_REFRESH_INFO_DIRECT@@PEAUIWbemServices@@PEAUIWbemContext@@PEAPEAUIWbemClassObject@@PEAJ@Z; CUniversalRefresher::AddDirectObject(_WBEM_REFRESH_INFO_DIRECT const &,IWbemServices *,IWbemContext *,IWbemClassObject * *,long *)
0x1800472a6  mov     esi, eax
0x1800472a8  test    eax, eax
0x1800472aa  jns     short loc_1800472BD
0x1800472ac  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800472b2  mov     edx, esi
0x1800472b4  mov     rcx, rax
0x1800472b7  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800472bd  lea     rax, WPP_GLOBAL_Control
0x1800472c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800472cb  cmp     rcx, rax
0x1800472ce  jz      loc_18004718C
0x1800472d4  test    byte ptr [rcx+1Ch], 1
0x1800472d8  jz      loc_18004718C
0x1800472de  cmp     byte ptr [rcx+19h], 2
0x1800472e2  jb      loc_18004718C
0x1800472e8  mov     edx, 0Fh
0x1800472ed  jmp     loc_180047178
0x1800472f2  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800472f8  mov     edx, 80041008h
0x1800472fd  mov     rcx, rax
0x180047300  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180047306  lea     rax, WPP_GLOBAL_Control
0x18004730d  mov     rcx, cs:WPP_GLOBAL_Control
0x180047314  cmp     rcx, rax
0x180047317  jz      short loc_180047340
0x180047319  test    byte ptr [rcx+1Ch], 1
0x18004731d  jz      short loc_180047340
0x18004731f  cmp     byte ptr [rcx+19h], 2
0x180047323  jb      short loc_180047340
0x180047325  mov     edx, 0Ah
0x18004732a  mov     r9d, 80041008h
0x180047330  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x180047337  mov     rcx, [rcx+10h]
0x18004733b  call    WPP_SF_d
0x180047340  mov     eax, 80041008h
0x180047345  mov     rcx, [rbp+40h+var_48]
0x180047349  xor     rcx, rsp; StackCookie
0x18004734c  call    __security_check_cookie
0x180047351  add     rsp, 108h
0x180047358  pop     r15
0x18004735a  pop     r14
0x18004735c  pop     r13
0x18004735e  pop     r12
0x180047360  pop     rdi
0x180047361  pop     rsi
0x180047362  pop     rbx
0x180047363  pop     rbp
0x180047364  retn
```
