# CUniversalRefresher::AddNonHiPerfObject(_WBEM_REFRESH_INFO_NON_HIPERF const &,IWbemServices *,ushort const *,IWbemClassObject * *,long *,_COAUTHINFO &)

- ea: `0x1800465c0`
- end: `0x180046a32`
- name: `?AddNonHiPerfObject@CUniversalRefresher@@IEAAJAEBU_WBEM_REFRESH_INFO_NON_HIPERF@@PEAUIWbemServices@@PEBGPEAPEAUIWbemClassObject@@PEAJAEAU_COAUTHINFO@@@Z`
- size: `1138`
- prototype: `__int64 __fastcall(CUniversalRefresher *this, const struct _WBEM_REFRESH_INFO_NON_HIPERF *, struct IWbemServices *, unsigned __int16 *, struct IWbemClassObject **, int *, struct _COAUTHINFO *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180046ee0`

## callees

- `0x180004060`
- `0x180037120`
- `0x180039d04`
- `0x1800465c0`
- `0x180046a38`
- `0x18006ce40`
- `0x1800700c8`
- `0x18007212c`
- `0x180086544`
- `0x180087680`
- `0x18009e010`

## import_xrefs

- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x1800465fb`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x1800465fb`
- `wbemcomn!GetMemLogObject` at `0x180046661`
- `wbemcomn!GetMemLogObject` at `0x180046751`
- `wbemcomn!GetMemLogObject` at `0x1800467e6`
- `wbemcomn!GetMemLogObject` at `0x1800468cf`
- `wbemcomn!GetMemLogObject` at `0x180046967`
- `wbemcomn!GetMemLogObject` at `0x180046661`
- `wbemcomn!GetMemLogObject` at `0x180046751`
- `wbemcomn!GetMemLogObject` at `0x1800467e6`
- `wbemcomn!GetMemLogObject` at `0x1800468cf`
- `wbemcomn!GetMemLogObject` at `0x180046967`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x1800465ec`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x1800465ec`
- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x18004660b`
- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x18004660b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004666c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004675f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800467f4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800468da`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180046972`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004666c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004675f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800467f4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800468da`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180046972`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18004670a`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18004670a`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CUniversalRefresher::AddNonHiPerfObject(
        CUniversalRefresher *this,
        const struct _WBEM_REFRESH_INFO_NON_HIPERF *a2,
        struct IWbemServices *a3,
        unsigned __int16 *a4,
        struct IWbemClassObject **a5,
        int *a6,
        struct _COAUTHINFO *a7)
{
  int v9; // esi
  CFlexArray *v10; // r15
  struct CWbemObject *v11; // r14
  const unsigned __int16 *v12; // rbx
  const unsigned __int16 *v13; // rax
  int v14; // esi
  struct IUnknown *v15; // rbx
  CMemoryLog *MemLogObject; // rax
  CUniversalRefresher::CNonHiPerf *v18; // rax
  CMemoryLog *v19; // rax
  unsigned int v20; // edx
  CMemoryLog *v21; // rax
  unsigned int v22; // edx
  unsigned int v23; // edx
  int v24; // ebx
  CMemoryLog *v25; // rax
  struct CWbemObject *v26; // rbx
  int v27; // esi
  CMemoryLog *v28; // rax
  struct IUnknown *v29; // [rsp+58h] [rbp-50h] BYREF
  struct CWbemObject *v30[9]; // [rsp+60h] [rbp-48h] BYREF
  CUniversalRefresher::CNonHiPerf *v31; // [rsp+B0h] [rbp+8h] BYREF
  unsigned __int16 *v32; // [rsp+C8h] [rbp+20h]

  v32 = a4;
  v9 = 0;
  v10 = (CUniversalRefresher *)((char *)this + 128);
  while ( v9 < CFlexArray::Size(v10) )
  {
    v11 = (struct CWbemObject *)CFlexArray::GetAt(v10, v9);
    v12 = *(const unsigned __int16 **)a2;
    v13 = (const unsigned __int16 *)WString::operator unsigned short *(v11);
    if ( !(unsigned int)wbem_wcsicmp(v13, v12) )
    {
      if ( v11 )
        goto LABEL_34;
      break;
    }
    ++v9;
  }
  v29 = 0;
  v14 = ((__int64 (__fastcall *)(struct IWbemServices *, GUID *, struct IUnknown **))a3->lpVtbl->QueryInterface)(
          a3,
          &IID_IWbemServices,
          &v29);
  v15 = v29;
  if ( v14 < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v14);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        64,
        WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids,
        (unsigned int)v14);
    }
    if ( v15 )
      ((void (__fastcall *)(struct IUnknown *))v15->lpVtbl->Release)(v15);
    return (unsigned int)v14;
  }
  WbemSetProxyBlanket(
    v29,
    a7->dwAuthnSvc,
    a7->dwAuthzSvc,
    (unsigned __int16 *)0xFFFFFFFFFFFFFFFFLL,
    a7->dwAuthnLevel,
    a7->dwImpersonationLevel,
    a7->pAuthIdentityData,
    a7->dwCapabilities,
    0);
  v18 = (CUniversalRefresher::CNonHiPerf *)CWin32DefaultArena::WbemMemAlloc(0x70u);
  v31 = v18;
  if ( v18 )
    v18 = CUniversalRefresher::CNonHiPerf::CNonHiPerf(v18, *(const unsigned __int16 **)a2, (struct IWbemServices *)v29);
  std::unique_ptr<CClassInfo>::unique_ptr<CClassInfo>(&v31, (__int64)v18);
  if ( !v31 )
  {
    v19 = GetMemLogObject();
    CMemoryLog::Write(v19, -2147217402);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids, 2147749894LL);
    }
    std::unique_ptr<CUniversalRefresher::CNonHiPerf>::~unique_ptr<CUniversalRefresher::CNonHiPerf>(&v31, v20);
    if ( v15 )
      ((void (__fastcall *)(struct IUnknown *))v15->lpVtbl->Release)(v15);
    return 2147749894LL;
  }
  if ( (unsigned int)CPointerArray<CUniversalRefresher::CRemote::CObjectRequest,CUniqueManager<CUniversalRefresher::CRemote::CObjectRequest>,CFlexArray>::Add(
                       v10,
                       v31) == -1 )
  {
    v21 = GetMemLogObject();
    CMemoryLog::Write(v21, -2147217402);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids, 2147749894LL);
    }
    std::unique_ptr<CUniversalRefresher::CNonHiPerf>::~unique_ptr<CUniversalRefresher::CNonHiPerf>(&v31, v22);
    if ( v15 )
      ((void (__fastcall *)(struct IUnknown *))v15->lpVtbl->Release)(v15);
    return 2147749894LL;
  }
  v11 = (struct CWbemObject *)std::unique_ptr<CUniversalRefresher::CRemote::CEnumRequest>::release(&v31);
  v30[1] = v11;
  std::unique_ptr<CUniversalRefresher::CNonHiPerf>::~unique_ptr<CUniversalRefresher::CNonHiPerf>(&v31, v23);
  if ( v15 )
    ((void (__fastcall *)(struct IUnknown *))v15->lpVtbl->Release)(v15);
LABEL_34:
  v30[0] = 0;
  v24 = (*(__int64 (__fastcall **)(_QWORD, struct CWbemObject **))(**((_QWORD **)a2 + 1) + 96LL))(
          *((_QWORD *)a2 + 1),
          v30);
  if ( v24 >= 0 )
  {
    v26 = v30[0];
    v31 = v30[0];
    v27 = CUniversalRefresher::CNonHiPerf::AddObjectRequest(v11, *((struct CWbemObject **)a2 + 1), v30[0], v32, a5, a6);
    if ( v27 < 0 )
    {
      v28 = GetMemLogObject();
      CMemoryLog::Write(v28, v27);
    }
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        69,
        WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids,
        (unsigned int)v27);
    }
    if ( v26 )
      (*(void (__fastcall **)(struct CWbemObject *))(*(_QWORD *)v26 + 16LL))(v26);
    return (unsigned int)v27;
  }
  else
  {
    v25 = GetMemLogObject();
    CMemoryLog::Write(v25, v24);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        68,
        WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids,
        (unsigned int)v24);
    }
    return (unsigned int)v24;
  }
}

```

## disassembly

```asm
0x1800465c0  mov     [rsp+arg_8], rbx
0x1800465c5  mov     [rsp+arg_18], r9
0x1800465ca  push    rsi
0x1800465cb  push    r12
0x1800465cd  push    r13
0x1800465cf  push    r14
0x1800465d1  push    r15
0x1800465d3  sub     rsp, 80h
0x1800465da  mov     r13, r8
0x1800465dd  mov     r12, rdx
0x1800465e0  xor     esi, esi
0x1800465e2  lea     r15, [rcx+80h]
0x1800465e9  mov     rcx, r15
0x1800465ec  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x1800465f2  cmp     esi, eax
0x1800465f4  jge     short loc_18004662D
0x1800465f6  mov     edx, esi
0x1800465f8  mov     rcx, r15
0x1800465fb  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x180046601  mov     r14, rax
0x180046604  mov     rbx, [r12]
0x180046608  mov     rcx, rax
0x18004660b  call    cs:__imp_??BWString@@QEAAPEAGXZ; WString::operator ushort *(void)
0x180046611  mov     rdx, rbx; unsigned __int16 *
0x180046614  mov     rcx, rax; unsigned __int16 *
0x180046617  call    ?wbem_wcsicmp@@YAHPEBG0@Z; wbem_wcsicmp(ushort const *,ushort const *)
0x18004661c  test    eax, eax
0x18004661e  jz      short loc_180046624
0x180046620  inc     esi
0x180046622  jmp     short loc_1800465E9
0x180046624  test    r14, r14
0x180046627  jnz     loc_1800468AA
0x18004662d  mov     [rsp+0A8h+var_50], 0
0x180046636  mov     rax, [r13+0]
0x18004663a  lea     r8, [rsp+0A8h+var_50]
0x18004663f  lea     rdx, IID_IWbemServices
0x180046646  mov     rcx, r13
0x180046649  mov     rax, [rax]
0x18004664c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046651  mov     esi, eax
0x180046653  mov     rbx, [rsp+0A8h+var_50]
0x180046658  mov     [rsp+0A8h+var_58], rbx
0x18004665d  test    eax, eax
0x18004665f  jns     short loc_1800466C5
0x180046661  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180046667  mov     edx, esi
0x180046669  mov     rcx, rax
0x18004666c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180046672  lea     rcx, WPP_GLOBAL_Control
0x180046679  mov     rax, cs:WPP_GLOBAL_Control
0x180046680  cmp     rax, rcx
0x180046683  jz      short loc_1800466AA
0x180046685  test    byte ptr [rax+1Ch], 1
0x180046689  jz      short loc_1800466AA
0x18004668b  cmp     byte ptr [rax+19h], 2
0x18004668f  jb      short loc_1800466AA
0x180046691  mov     edx, 40h ; '@'
0x180046696  mov     r9d, esi
0x180046699  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x1800466a0  mov     rcx, [rax+10h]
0x1800466a4  call    WPP_SF_d
0x1800466a9  nop
0x1800466aa  test    rbx, rbx
0x1800466ad  jz      short loc_1800466BE
0x1800466af  mov     rax, [rbx]
0x1800466b2  mov     rcx, rbx
0x1800466b5  mov     rax, [rax+10h]
0x1800466b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800466be  mov     eax, esi
0x1800466c0  jmp     loc_180046A10
0x1800466c5  mov     [rsp+0A8h+var_68], 0; bool
0x1800466ca  mov     rdx, [rsp+0A8h+arg_30]
0x1800466d2  mov     eax, [rdx+20h]
0x1800466d5  mov     [rsp+0A8h+var_70], eax; unsigned int
0x1800466d9  mov     rax, [rdx+18h]
0x1800466dd  mov     [rsp+0A8h+var_78], rax; struct _COAUTHIDENTITY *
0x1800466e2  mov     eax, [rdx+14h]
0x1800466e5  mov     dword ptr [rsp+0A8h+var_80], eax; unsigned int
0x1800466e9  mov     eax, [rdx+10h]
0x1800466ec  mov     dword ptr [rsp+0A8h+var_88], eax; unsigned int
0x1800466f0  or      r9, 0FFFFFFFFFFFFFFFFh; unsigned __int16 *
0x1800466f4  mov     r8d, [rdx+4]; unsigned int
0x1800466f8  mov     edx, [rdx]; unsigned int
0x1800466fa  mov     rcx, [rsp+0A8h+var_50]; struct IUnknown *
0x1800466ff  call    ?WbemSetProxyBlanket@@YAJPEAUIUnknown@@KKPEAGKKPEAXK_N@Z; WbemSetProxyBlanket(IUnknown *,ulong,ulong,ushort *,ulong,ulong,void *,ulong,bool)
0x180046704  nop
0x180046705  mov     ecx, 70h ; 'p'
0x18004670a  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180046710  mov     [rsp+0A8h+arg_0], rax
0x180046718  test    rax, rax
0x18004671b  jz      short loc_18004672F
0x18004671d  mov     r8, [rsp+0A8h+var_50]; struct IWbemServices *
0x180046722  mov     rdx, [r12]; unsigned __int16 *
0x180046726  mov     rcx, rax; this
0x180046729  call    ??0CNonHiPerf@CUniversalRefresher@@QEAA@PEBGPEAUIWbemServices@@@Z; CUniversalRefresher::CNonHiPerf::CNonHiPerf(ushort const *,IWbemServices *)
0x18004672e  nop
0x18004672f  mov     rdx, rax
0x180046732  lea     rcx, [rsp+0A8h+arg_0]
0x18004673a  call    ??0?$unique_ptr@UCClassInfo@@U?$default_delete@UCClassInfo@@@std@@@std@@QEAA@PEAUCClassInfo@@@Z; std::unique_ptr<CClassInfo>::unique_ptr<CClassInfo>(CClassInfo *)
0x18004673f  nop
0x180046740  mov     rdx, [rsp+0A8h+arg_0]
0x180046748  test    rdx, rdx
0x18004674b  jnz     loc_1800467D5
0x180046751  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180046757  mov     edx, 80041006h
0x18004675c  mov     rcx, rax
0x18004675f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180046765  lea     rcx, WPP_GLOBAL_Control
0x18004676c  mov     rax, cs:WPP_GLOBAL_Control
0x180046773  cmp     rax, rcx
0x180046776  jz      short loc_1800467A0
0x180046778  test    byte ptr [rax+1Ch], 1
0x18004677c  jz      short loc_1800467A0
0x18004677e  cmp     byte ptr [rax+19h], 2
0x180046782  jb      short loc_1800467A0
0x180046784  mov     edx, 41h ; 'A'
0x180046789  mov     r9d, 80041006h
0x18004678f  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x180046796  mov     rcx, [rax+10h]
0x18004679a  call    WPP_SF_d
0x18004679f  nop
0x1800467a0  lea     rcx, [rsp+0A8h+arg_0]
0x1800467a8  call    ??1?$unique_ptr@VCNonHiPerf@CUniversalRefresher@@U?$default_delete@VCNonHiPerf@CUniversalRefresher@@@std@@@std@@QEAA@XZ; std::unique_ptr<CUniversalRefresher::CNonHiPerf>::~unique_ptr<CUniversalRefresher::CNonHiPerf>(void)
0x1800467ad  nop
0x1800467ae  test    rbx, rbx
0x1800467b1  jz      short loc_1800467C2
0x1800467b3  mov     rcx, [rbx]
0x1800467b6  mov     rax, [rcx+10h]
0x1800467ba  mov     rcx, rbx
0x1800467bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800467c2  mov     [rsp+0A8h+var_58], 0
0x1800467cb  mov     eax, 80041006h
0x1800467d0  jmp     loc_180046A19
0x1800467d5  mov     rcx, r15
0x1800467d8  call    ?Add@?$CPointerArray@VCObjectRequest@CRemote@CUniversalRefresher@@V?$CUniqueManager@VCObjectRequest@CRemote@CUniversalRefresher@@@@VCFlexArray@@@@QEAAHPEAVCObjectRequest@CRemote@CUniversalRefresher@@@Z; CPointerArray<CUniversalRefresher::CRemote::CObjectRequest,CUniqueManager<CUniversalRefresher::CRemote::CObjectRequest>,CFlexArray>::Add(CUniversalRefresher::CRemote::CObjectRequest *)
0x1800467dd  cmp     eax, 0FFFFFFFFh
0x1800467e0  jnz     loc_18004686A
0x1800467e6  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800467ec  mov     edx, 80041006h
0x1800467f1  mov     rcx, rax
0x1800467f4  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800467fa  lea     rcx, WPP_GLOBAL_Control
0x180046801  mov     rax, cs:WPP_GLOBAL_Control
0x180046808  cmp     rax, rcx
0x18004680b  jz      short loc_180046835
0x18004680d  test    byte ptr [rax+1Ch], 1
0x180046811  jz      short loc_180046835
0x180046813  cmp     byte ptr [rax+19h], 2
0x180046817  jb      short loc_180046835
0x180046819  mov     edx, 42h ; 'B'
0x18004681e  mov     r9d, 80041006h
0x180046824  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x18004682b  mov     rcx, [rax+10h]
0x18004682f  call    WPP_SF_d
0x180046834  nop
0x180046835  lea     rcx, [rsp+0A8h+arg_0]
0x18004683d  call    ??1?$unique_ptr@VCNonHiPerf@CUniversalRefresher@@U?$default_delete@VCNonHiPerf@CUniversalRefresher@@@std@@@std@@QEAA@XZ; std::unique_ptr<CUniversalRefresher::CNonHiPerf>::~unique_ptr<CUniversalRefresher::CNonHiPerf>(void)
0x180046842  nop
0x180046843  test    rbx, rbx
0x180046846  jz      short loc_180046857
0x180046848  mov     rax, [rbx]
0x18004684b  mov     rcx, rbx
0x18004684e  mov     rax, [rax+10h]
0x180046852  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046857  mov     [rsp+0A8h+var_58], 0
0x180046860  mov     eax, 80041006h
0x180046865  jmp     loc_180046A19
0x18004686a  lea     rcx, [rsp+0A8h+arg_0]
0x180046872  call    ?release@?$unique_ptr@VCEnumRequest@CRemote@CUniversalRefresher@@U?$default_delete@VCEnumRequest@CRemote@CUniversalRefresher@@@std@@@std@@QEAAPEAVCEnumRequest@CRemote@CUniversalRefresher@@XZ; std::unique_ptr<CUniversalRefresher::CRemote::CEnumRequest>::release(void)
0x180046877  mov     r14, rax
0x18004687a  mov     [rsp+0A8h+var_40], rax
0x18004687f  lea     rcx, [rsp+0A8h+arg_0]
0x180046887  call    ??1?$unique_ptr@VCNonHiPerf@CUniversalRefresher@@U?$default_delete@VCNonHiPerf@CUniversalRefresher@@@std@@@std@@QEAA@XZ; std::unique_ptr<CUniversalRefresher::CNonHiPerf>::~unique_ptr<CUniversalRefresher::CNonHiPerf>(void)
0x18004688c  nop
0x18004688d  test    rbx, rbx
0x180046890  jz      short loc_1800468A1
0x180046892  mov     rax, [rbx]
0x180046895  mov     rcx, rbx
0x180046898  mov     rax, [rax+10h]
0x18004689c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800468a1  mov     [rsp+0A8h+var_58], 0
0x1800468aa  mov     [rsp+0A8h+var_48], 0
0x1800468b3  mov     rcx, [r12+8]
0x1800468b8  mov     rax, [rcx]
0x1800468bb  lea     rdx, [rsp+0A8h+var_48]
0x1800468c0  mov     rax, [rax+60h]
0x1800468c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800468c9  mov     ebx, eax
0x1800468cb  test    eax, eax
0x1800468cd  jns     short loc_180046920
0x1800468cf  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800468d5  mov     edx, ebx
0x1800468d7  mov     rcx, rax
0x1800468da  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800468e0  lea     rcx, WPP_GLOBAL_Control
0x1800468e7  mov     r10, cs:WPP_GLOBAL_Control
0x1800468ee  cmp     r10, rcx
0x1800468f1  jz      short loc_180046919
0x1800468f3  test    byte ptr [r10+1Ch], 1
0x1800468f8  jz      short loc_180046919
0x1800468fa  cmp     byte ptr [r10+19h], 2
0x1800468ff  jb      short loc_180046919
0x180046901  mov     edx, 44h ; 'D'
0x180046906  mov     r9d, ebx
0x180046909  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x180046910  mov     rcx, [r10+10h]
0x180046914  call    WPP_SF_d
0x180046919  mov     eax, ebx
0x18004691b  jmp     loc_180046A19
0x180046920  mov     rbx, [rsp+0A8h+var_48]
0x180046925  mov     [rsp+0A8h+arg_0], rbx
0x18004692d  mov     rax, [rsp+0A8h+arg_28]
0x180046935  mov     [rsp+0A8h+var_80], rax; int *
0x18004693a  mov     rax, [rsp+0A8h+arg_20]
0x180046942  mov     [rsp+0A8h+var_88], rax; struct IWbemClassObject **
0x180046947  mov     r9, [rsp+0A8h+arg_18]; unsigned __int16 *
0x18004694f  mov     r8, [rsp+0A8h+var_48]; struct CWbemObject *
0x180046954  mov     rdx, [r12+8]; struct CWbemObject *
0x180046959  mov     rcx, r14; this
0x18004695c  call    ?AddObjectRequest@CNonHiPerf@CUniversalRefresher@@QEAAJPEAVCWbemObject@@0PEBGPEAPEAUIWbemClassObject@@PEAJ@Z; CUniversalRefresher::CNonHiPerf::AddObjectRequest(CWbemObject *,CWbemObject *,ushort const *,IWbemClassObject * *,long *)
0x180046961  mov     esi, eax
0x180046963  test    eax, eax
0x180046965  jns     short loc_180046978
0x180046967  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004696d  mov     edx, esi
0x18004696f  mov     rcx, rax
0x180046972  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180046978  lea     rcx, WPP_GLOBAL_Control
0x18004697f  mov     r10, cs:WPP_GLOBAL_Control
0x180046986  cmp     r10, rcx
0x180046989  jz      short loc_1800469B2
0x18004698b  test    byte ptr [r10+1Ch], 1
0x180046990  jz      short loc_1800469B2
0x180046992  cmp     byte ptr [r10+19h], 2
0x180046997  jb      short loc_1800469B2
0x180046999  mov     edx, 45h ; 'E'
0x18004699e  mov     r9d, esi
0x1800469a1  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x1800469a8  mov     rcx, [r10+10h]
0x1800469ac  call    WPP_SF_d
0x1800469b1  nop
0x1800469b2  test    rbx, rbx
0x1800469b5  jz      short loc_1800469C6
0x1800469b7  mov     rax, [rbx]
0x1800469ba  mov     rcx, rbx
0x1800469bd  mov     rax, [rax+10h]
0x1800469c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800469c6  mov     [rsp+0A8h+arg_0], 0
0x1800469d2  mov     eax, esi
0x1800469d4  jmp     short loc_180046A19
0x1800469d6  mov     rcx, [rsp+0A8h+var_58]
0x1800469db  test    rcx, rcx
0x1800469de  jz      short loc_1800469EC
0x1800469e0  mov     rax, [rcx]
0x1800469e3  mov     rax, [rax+10h]
0x1800469e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800469ec  mov     eax, 80041006h
0x1800469f1  jmp     short loc_180046A10
0x1800469f3  mov     rcx, [rsp+0A8h+var_58]
0x1800469f8  test    rcx, rcx
0x1800469fb  jz      short loc_180046A09
0x1800469fd  mov     rax, [rcx]
0x180046a00  mov     rax, [rax+10h]
0x180046a04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046a09  mov     eax, dword ptr [rsp+0A8h+arg_0]
0x180046a10  mov     [rsp+0A8h+var_58], 0
0x180046a19  mov     rbx, [rsp+0A8h+arg_8]
0x180046a21  add     rsp, 80h
0x180046a28  pop     r15
0x180046a2a  pop     r14
0x180046a2c  pop     r13
0x180046a2e  pop     r12
0x180046a30  pop     rsi
0x180046a31  retn
```
