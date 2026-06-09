# CUniversalRefresher::AddNonHiPerfEnum(_WBEM_REFRESH_INFO_NON_HIPERF const &,IWbemServices *,ushort const *,IWbemContext *,IWbemHiPerfEnum * *,long *,_COAUTHINFO &)

- ea: `0x180087178`
- end: `0x180087678`
- name: `?AddNonHiPerfEnum@CUniversalRefresher@@IEAAJAEBU_WBEM_REFRESH_INFO_NON_HIPERF@@PEAUIWbemServices@@PEBGPEAUIWbemContext@@PEAPEAUIWbemHiPerfEnum@@PEAJAEAU_COAUTHINFO@@@Z`
- size: `1280`
- prototype: `__int64 __fastcall(struct CLifeControl **this, const unsigned __int16 **, struct IWbemServices *, unsigned __int16 *, struct IUnknown *, struct IWbemHiPerfEnum **, int *, struct _COAUTHINFO *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180047c10`

## callees

- `0x180004060`
- `0x180037120`
- `0x180039d04`
- `0x180046a38`
- `0x18004a7c8`
- `0x18004a8b4`
- `0x18006ce40`
- `0x1800700c8`
- `0x18007212c`
- `0x180086544`
- `0x180086d1c`
- `0x180087178`
- `0x18009e010`

## import_xrefs

- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x1800871b8`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x1800871b8`
- `wbemcomn!GetMemLogObject` at `0x180087237`
- `wbemcomn!GetMemLogObject` at `0x180087334`
- `wbemcomn!GetMemLogObject` at `0x1800873c8`
- `wbemcomn!GetMemLogObject` at `0x1800874bb`
- `wbemcomn!GetMemLogObject` at `0x180087539`
- `wbemcomn!GetMemLogObject` at `0x1800875db`
- `wbemcomn!GetMemLogObject` at `0x180087237`
- `wbemcomn!GetMemLogObject` at `0x180087334`
- `wbemcomn!GetMemLogObject` at `0x1800873c8`
- `wbemcomn!GetMemLogObject` at `0x1800874bb`
- `wbemcomn!GetMemLogObject` at `0x180087539`
- `wbemcomn!GetMemLogObject` at `0x1800875db`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x1800871a9`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x1800871a9`
- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x1800871c7`
- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x1800871c7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180087242`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180087344`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800873d8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800874cb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180087544`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800875e6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180087242`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180087344`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800873d8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800874cb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180087544`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800875e6`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800872e3`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180087490`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800872e3`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180087490`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CUniversalRefresher::AddNonHiPerfEnum(
        struct CLifeControl **this,
        const unsigned __int16 **a2,
        struct IWbemServices *a3,
        unsigned __int16 *a4,
        struct IUnknown *a5,
        struct IWbemHiPerfEnum **a6,
        int *a7,
        struct _COAUTHINFO *a8)
{
  const unsigned __int16 **v9; // rbx
  int v11; // esi
  CFlexArray *v12; // r15
  CUniversalRefresher::CNonHiPerf *v13; // r14
  const unsigned __int16 *v14; // rbx
  const unsigned __int16 *v15; // rax
  const unsigned __int16 **v16; // rsi
  int v17; // esi
  struct IUnknown *v18; // rbx
  CMemoryLog *v19; // rax
  CUniversalRefresher::CNonHiPerf *v21; // rax
  CMemoryLog *v22; // rax
  unsigned int v23; // edx
  CMemoryLog *v24; // rax
  unsigned int v25; // edx
  unsigned int v26; // edx
  CUniversalRefresher::CNonHiPerf *v27; // rax
  CUniversalRefresher::CNonHiPerf *v28; // rbx
  CMemoryLog *MemLogObject; // rax
  int v30; // esi
  CMemoryLog *v31; // rax
  CWbemRefreshingSvc *v32; // r10
  __int64 v33; // rdx
  CMemoryLog *v34; // rax
  CUniversalRefresher::CNonHiPerf *v35; // [rsp+A0h] [rbp+8h] BYREF
  const unsigned __int16 **v36; // [rsp+A8h] [rbp+10h]
  unsigned __int16 *v37; // [rsp+B8h] [rbp+20h]

  v37 = a4;
  v36 = a2;
  v9 = a2;
  v11 = 0;
  v12 = (CFlexArray *)(this + 16);
  while ( 1 )
  {
    if ( v11 >= CFlexArray::Size(v12) )
      goto LABEL_7;
    v13 = (CUniversalRefresher::CNonHiPerf *)CFlexArray::GetAt(v12, v11);
    v14 = *v9;
    v15 = (const unsigned __int16 *)WString::operator unsigned short *(v13);
    if ( !(unsigned int)wbem_wcsicmp(v15, v14) )
      break;
    ++v11;
    v9 = v36;
  }
  if ( v13 )
  {
    v16 = v36;
    goto LABEL_35;
  }
LABEL_7:
  a5 = 0;
  v17 = ((__int64 (__fastcall *)(struct IWbemServices *, GUID *, struct IUnknown **))a3->lpVtbl->QueryInterface)(
          a3,
          &IID_IWbemServices,
          &a5);
  v18 = a5;
  if ( v17 >= 0 )
  {
    WbemSetProxyBlanket(
      a5,
      a8->dwAuthnSvc,
      a8->dwAuthzSvc,
      (unsigned __int16 *)0xFFFFFFFFFFFFFFFFLL,
      a8->dwAuthnLevel,
      a8->dwImpersonationLevel,
      a8->pAuthIdentityData,
      a8->dwCapabilities,
      0);
    v21 = (CUniversalRefresher::CNonHiPerf *)CWin32DefaultArena::WbemMemAlloc(0x70u);
    v35 = v21;
    v16 = v36;
    if ( v21 )
      v21 = CUniversalRefresher::CNonHiPerf::CNonHiPerf(v21, *v36, (struct IWbemServices *)a5);
    std::unique_ptr<CClassInfo>::unique_ptr<CClassInfo>(&v35, (__int64)v21);
    if ( v35 )
    {
      if ( (unsigned int)CPointerArray<CUniversalRefresher::CRemote::CObjectRequest,CUniqueManager<CUniversalRefresher::CRemote::CObjectRequest>,CFlexArray>::Add(
                           v12,
                           v35) != -1 )
      {
        v13 = (CUniversalRefresher::CNonHiPerf *)std::unique_ptr<CUniversalRefresher::CRemote::CEnumRequest>::release(&v35);
        std::unique_ptr<CUniversalRefresher::CNonHiPerf>::~unique_ptr<CUniversalRefresher::CNonHiPerf>(&v35, v26);
        if ( v18 )
          ((void (__fastcall *)(struct IUnknown *))v18->lpVtbl->Release)(v18);
LABEL_35:
        v27 = (CUniversalRefresher::CNonHiPerf *)CWin32DefaultArena::WbemMemAlloc(0x188u);
        v35 = v27;
        if ( v27 )
          v28 = CClientLoadableHiPerfEnum::CClientLoadableHiPerfEnum(v27, this[2]);
        else
          v28 = 0;
        if ( !v28 )
        {
          MemLogObject = GetMemLogObject();
          v30 = -2147217402;
          CMemoryLog::Write(MemLogObject, -2147217402);
          if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              74,
              WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids,
              2147749894LL);
          }
          return (unsigned int)v30;
        }
        (*(void (__fastcall **)(CUniversalRefresher::CNonHiPerf *))(*(_QWORD *)v28 + 8LL))(v28);
        v35 = v28;
        v30 = CHiPerfEnum::SetInstanceTemplate(v28, (struct CWbemInstance *)v16[1]);
        if ( v30 >= 0 )
        {
          v30 = CUniversalRefresher::CNonHiPerf::AddEnumRequest(v13, v28, v37, a6, a7, this[2]);
          if ( v30 < 0 )
          {
            v34 = GetMemLogObject();
            CMemoryLog::Write(v34, v30);
          }
          v32 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_50;
          }
          v33 = 76;
        }
        else
        {
          v31 = GetMemLogObject();
          CMemoryLog::Write(v31, v30);
          v32 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_50;
          }
          v33 = 75;
        }
        WPP_SF_d(*((_QWORD *)v32 + 2), v33, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids, (unsigned int)v30);
LABEL_50:
        (*(void (__fastcall **)(CUniversalRefresher::CNonHiPerf *))(*(_QWORD *)v28 + 16LL))(v28);
        v35 = 0;
        return (unsigned int)v30;
      }
      v24 = GetMemLogObject();
      CMemoryLog::Write(v24, -2147217402);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids, 2147749894LL);
      }
      std::unique_ptr<CUniversalRefresher::CNonHiPerf>::~unique_ptr<CUniversalRefresher::CNonHiPerf>(&v35, v25);
      if ( v18 )
        ((void (__fastcall *)(struct IUnknown *))v18->lpVtbl->Release)(v18);
      return 2147749894LL;
    }
    else
    {
      v22 = GetMemLogObject();
      CMemoryLog::Write(v22, -2147217402);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids, 2147749894LL);
      }
      std::unique_ptr<CUniversalRefresher::CNonHiPerf>::~unique_ptr<CUniversalRefresher::CNonHiPerf>(&v35, v23);
      if ( v18 )
        ((void (__fastcall *)(struct IUnknown *))v18->lpVtbl->Release)(v18);
      return 2147749894LL;
    }
  }
  else
  {
    v19 = GetMemLogObject();
    CMemoryLog::Write(v19, v17);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        70,
        WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids,
        (unsigned int)v17);
    }
    if ( v18 )
      ((void (__fastcall *)(struct IUnknown *))v18->lpVtbl->Release)(v18);
    return (unsigned int)v17;
  }
}

```

## disassembly

```asm
0x180087178  mov     [rsp+arg_10], rbx
0x18008717d  mov     [rsp+arg_18], r9
0x180087182  mov     [rsp+arg_8], rdx
0x180087187  push    rsi
0x180087188  push    r12
0x18008718a  push    r13
0x18008718c  push    r14
0x18008718e  push    r15
0x180087190  sub     rsp, 70h
0x180087194  mov     r12, r8
0x180087197  mov     rbx, rdx
0x18008719a  mov     r13, rcx
0x18008719d  xor     esi, esi
0x18008719f  lea     r15, [rcx+80h]
0x1800871a6  mov     rcx, r15
0x1800871a9  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x1800871af  cmp     esi, eax
0x1800871b1  jge     short loc_1800871FA
0x1800871b3  mov     edx, esi
0x1800871b5  mov     rcx, r15
0x1800871b8  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x1800871be  mov     r14, rax
0x1800871c1  mov     rbx, [rbx]
0x1800871c4  mov     rcx, rax
0x1800871c7  call    cs:__imp_??BWString@@QEAAPEAGXZ; WString::operator ushort *(void)
0x1800871cd  mov     rdx, rbx; unsigned __int16 *
0x1800871d0  mov     rcx, rax; unsigned __int16 *
0x1800871d3  call    ?wbem_wcsicmp@@YAHPEBG0@Z; wbem_wcsicmp(ushort const *,ushort const *)
0x1800871d8  test    eax, eax
0x1800871da  jz      short loc_1800871E8
0x1800871dc  inc     esi
0x1800871de  mov     rbx, [rsp+98h+arg_8]
0x1800871e6  jmp     short loc_1800871A6
0x1800871e8  test    r14, r14
0x1800871eb  jz      short loc_1800871FA
0x1800871ed  mov     rsi, [rsp+98h+arg_8]
0x1800871f5  jmp     loc_18008748B
0x1800871fa  mov     [rsp+98h+arg_20], 0
0x180087206  mov     rax, [r12]
0x18008720a  lea     r8, [rsp+98h+arg_20]
0x180087212  lea     rdx, IID_IWbemServices
0x180087219  mov     rcx, r12
0x18008721c  mov     rax, [rax]
0x18008721f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087224  mov     esi, eax
0x180087226  mov     rbx, [rsp+98h+arg_20]
0x18008722e  mov     [rsp+98h+var_48], rbx
0x180087233  test    eax, eax
0x180087235  jns     short loc_18008729B
0x180087237  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18008723d  mov     edx, esi
0x18008723f  mov     rcx, rax
0x180087242  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180087248  lea     rcx, WPP_GLOBAL_Control
0x18008724f  mov     rax, cs:WPP_GLOBAL_Control
0x180087256  cmp     rax, rcx
0x180087259  jz      short loc_180087280
0x18008725b  test    byte ptr [rax+1Ch], 1
0x18008725f  jz      short loc_180087280
0x180087261  cmp     byte ptr [rax+19h], 2
0x180087265  jb      short loc_180087280
0x180087267  mov     edx, 46h ; 'F'
0x18008726c  mov     r9d, esi
0x18008726f  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x180087276  mov     rcx, [rax+10h]
0x18008727a  call    WPP_SF_d
0x18008727f  nop
0x180087280  test    rbx, rbx
0x180087283  jz      short loc_180087294
0x180087285  mov     rax, [rbx]
0x180087288  mov     rcx, rbx
0x18008728b  mov     rax, [rax+10h]
0x18008728f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087294  mov     eax, esi
0x180087296  jmp     loc_180087659
0x18008729b  mov     [rsp+98h+var_58], 0; bool
0x1800872a0  mov     rdx, [rsp+98h+arg_38]
0x1800872a8  mov     eax, [rdx+20h]
0x1800872ab  mov     [rsp+98h+var_60], eax; unsigned int
0x1800872af  mov     rax, [rdx+18h]
0x1800872b3  mov     [rsp+98h+var_68], rax; struct _COAUTHIDENTITY *
0x1800872b8  mov     eax, [rdx+14h]
0x1800872bb  mov     dword ptr [rsp+98h+var_70], eax; unsigned int
0x1800872bf  mov     eax, [rdx+10h]
0x1800872c2  mov     dword ptr [rsp+98h+var_78], eax; unsigned int
0x1800872c6  or      r9, 0FFFFFFFFFFFFFFFFh; unsigned __int16 *
0x1800872ca  mov     r8d, [rdx+4]; unsigned int
0x1800872ce  mov     edx, [rdx]; unsigned int
0x1800872d0  mov     rcx, [rsp+98h+arg_20]; struct IUnknown *
0x1800872d8  call    ?WbemSetProxyBlanket@@YAJPEAUIUnknown@@KKPEAGKKPEAXK_N@Z; WbemSetProxyBlanket(IUnknown *,ulong,ulong,ushort *,ulong,ulong,void *,ulong,bool)
0x1800872dd  nop
0x1800872de  mov     ecx, 70h ; 'p'
0x1800872e3  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800872e9  mov     [rsp+98h+arg_0], rax
0x1800872f1  mov     rsi, [rsp+98h+arg_8]
0x1800872f9  test    rax, rax
0x1800872fc  jz      short loc_180087312
0x1800872fe  mov     r8, [rsp+98h+arg_20]; struct IWbemServices *
0x180087306  mov     rdx, [rsi]; unsigned __int16 *
0x180087309  mov     rcx, rax; this
0x18008730c  call    ??0CNonHiPerf@CUniversalRefresher@@QEAA@PEBGPEAUIWbemServices@@@Z; CUniversalRefresher::CNonHiPerf::CNonHiPerf(ushort const *,IWbemServices *)
0x180087311  nop
0x180087312  mov     rdx, rax
0x180087315  lea     rcx, [rsp+98h+arg_0]
0x18008731d  call    ??0?$unique_ptr@UCClassInfo@@U?$default_delete@UCClassInfo@@@std@@@std@@QEAA@PEAUCClassInfo@@@Z; std::unique_ptr<CClassInfo>::unique_ptr<CClassInfo>(CClassInfo *)
0x180087322  nop
0x180087323  mov     rdx, [rsp+98h+arg_0]
0x18008732b  test    rdx, rdx
0x18008732e  jnz     loc_1800873B7
0x180087334  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18008733a  mov     esi, 80041006h
0x18008733f  mov     edx, esi
0x180087341  mov     rcx, rax
0x180087344  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18008734a  lea     rcx, WPP_GLOBAL_Control
0x180087351  mov     rax, cs:WPP_GLOBAL_Control
0x180087358  cmp     rax, rcx
0x18008735b  jz      short loc_180087385
0x18008735d  test    byte ptr [rax+1Ch], 1
0x180087361  jz      short loc_180087385
0x180087363  cmp     byte ptr [rax+19h], 2
0x180087367  jb      short loc_180087385
0x180087369  mov     edx, 47h ; 'G'
0x18008736e  mov     r9d, 80041006h
0x180087374  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x18008737b  mov     rcx, [rax+10h]
0x18008737f  call    WPP_SF_d
0x180087384  nop
0x180087385  lea     rcx, [rsp+98h+arg_0]
0x18008738d  call    ??1?$unique_ptr@VCNonHiPerf@CUniversalRefresher@@U?$default_delete@VCNonHiPerf@CUniversalRefresher@@@std@@@std@@QEAA@XZ; std::unique_ptr<CUniversalRefresher::CNonHiPerf>::~unique_ptr<CUniversalRefresher::CNonHiPerf>(void)
0x180087392  nop
0x180087393  test    rbx, rbx
0x180087396  jz      short loc_1800873A7
0x180087398  mov     rcx, [rbx]
0x18008739b  mov     rax, [rcx+10h]
0x18008739f  mov     rcx, rbx
0x1800873a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800873a7  mov     [rsp+98h+var_48], 0
0x1800873b0  mov     eax, esi
0x1800873b2  jmp     loc_180087662
0x1800873b7  mov     rcx, r15
0x1800873ba  call    ?Add@?$CPointerArray@VCObjectRequest@CRemote@CUniversalRefresher@@V?$CUniqueManager@VCObjectRequest@CRemote@CUniversalRefresher@@@@VCFlexArray@@@@QEAAHPEAVCObjectRequest@CRemote@CUniversalRefresher@@@Z; CPointerArray<CUniversalRefresher::CRemote::CObjectRequest,CUniqueManager<CUniversalRefresher::CRemote::CObjectRequest>,CFlexArray>::Add(CUniversalRefresher::CRemote::CObjectRequest *)
0x1800873bf  cmp     eax, 0FFFFFFFFh
0x1800873c2  jnz     loc_18008744B
0x1800873c8  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800873ce  mov     esi, 80041006h
0x1800873d3  mov     edx, esi
0x1800873d5  mov     rcx, rax
0x1800873d8  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800873de  lea     rcx, WPP_GLOBAL_Control
0x1800873e5  mov     rax, cs:WPP_GLOBAL_Control
0x1800873ec  cmp     rax, rcx
0x1800873ef  jz      short loc_180087419
0x1800873f1  test    byte ptr [rax+1Ch], 1
0x1800873f5  jz      short loc_180087419
0x1800873f7  cmp     byte ptr [rax+19h], 2
0x1800873fb  jb      short loc_180087419
0x1800873fd  mov     edx, 48h ; 'H'
0x180087402  mov     r9d, 80041006h
0x180087408  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x18008740f  mov     rcx, [rax+10h]
0x180087413  call    WPP_SF_d
0x180087418  nop
0x180087419  lea     rcx, [rsp+98h+arg_0]
0x180087421  call    ??1?$unique_ptr@VCNonHiPerf@CUniversalRefresher@@U?$default_delete@VCNonHiPerf@CUniversalRefresher@@@std@@@std@@QEAA@XZ; std::unique_ptr<CUniversalRefresher::CNonHiPerf>::~unique_ptr<CUniversalRefresher::CNonHiPerf>(void)
0x180087426  nop
0x180087427  test    rbx, rbx
0x18008742a  jz      short loc_18008743B
0x18008742c  mov     rax, [rbx]
0x18008742f  mov     rcx, rbx
0x180087432  mov     rax, [rax+10h]
0x180087436  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008743b  mov     [rsp+98h+var_48], 0
0x180087444  mov     eax, esi
0x180087446  jmp     loc_180087662
0x18008744b  lea     rcx, [rsp+98h+arg_0]
0x180087453  call    ?release@?$unique_ptr@VCEnumRequest@CRemote@CUniversalRefresher@@U?$default_delete@VCEnumRequest@CRemote@CUniversalRefresher@@@std@@@std@@QEAAPEAVCEnumRequest@CRemote@CUniversalRefresher@@XZ; std::unique_ptr<CUniversalRefresher::CRemote::CEnumRequest>::release(void)
0x180087458  mov     r14, rax
0x18008745b  mov     [rsp+98h+var_40], rax
0x180087460  lea     rcx, [rsp+98h+arg_0]
0x180087468  call    ??1?$unique_ptr@VCNonHiPerf@CUniversalRefresher@@U?$default_delete@VCNonHiPerf@CUniversalRefresher@@@std@@@std@@QEAA@XZ; std::unique_ptr<CUniversalRefresher::CNonHiPerf>::~unique_ptr<CUniversalRefresher::CNonHiPerf>(void)
0x18008746d  nop
0x18008746e  test    rbx, rbx
0x180087471  jz      short loc_180087482
0x180087473  mov     rax, [rbx]
0x180087476  mov     rcx, rbx
0x180087479  mov     rax, [rax+10h]
0x18008747d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087482  mov     [rsp+98h+var_48], 0
0x18008748b  mov     ecx, 188h
0x180087490  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180087496  mov     [rsp+98h+arg_0], rax
0x18008749e  test    rax, rax
0x1800874a1  jz      short loc_1800874B4
0x1800874a3  mov     rdx, [r13+10h]; struct CLifeControl *
0x1800874a7  mov     rcx, rax; this
0x1800874aa  call    ??0CClientLoadableHiPerfEnum@@QEAA@PEAVCLifeControl@@@Z; CClientLoadableHiPerfEnum::CClientLoadableHiPerfEnum(CLifeControl *)
0x1800874af  mov     rbx, rax
0x1800874b2  jmp     short loc_1800874B6
0x1800874b4  xor     ebx, ebx
0x1800874b6  test    rbx, rbx
0x1800874b9  jnz     short loc_180087510
0x1800874bb  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800874c1  mov     esi, 80041006h
0x1800874c6  mov     edx, esi
0x1800874c8  mov     rcx, rax
0x1800874cb  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800874d1  lea     rcx, WPP_GLOBAL_Control
0x1800874d8  mov     rax, cs:WPP_GLOBAL_Control
0x1800874df  cmp     rax, rcx
0x1800874e2  jz      short loc_180087509
0x1800874e4  test    byte ptr [rax+1Ch], 1
0x1800874e8  jz      short loc_180087509
0x1800874ea  cmp     byte ptr [rax+19h], 2
0x1800874ee  jb      short loc_180087509
0x1800874f0  lea     edx, [rbx+4Ah]
0x1800874f3  mov     r9d, 80041006h
0x1800874f9  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x180087500  mov     rcx, [rax+10h]
0x180087504  call    WPP_SF_d
0x180087509  mov     eax, esi
0x18008750b  jmp     loc_180087662
0x180087510  mov     rax, [rbx]
0x180087513  mov     rcx, rbx
0x180087516  mov     rax, [rax+8]
0x18008751a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008751f  mov     [rsp+98h+arg_0], rbx
0x180087527  mov     rdx, [rsi+8]; struct CWbemInstance *
0x18008752b  mov     rcx, rbx; this
0x18008752e  call    ?SetInstanceTemplate@CHiPerfEnum@@QEAAJPEAVCWbemInstance@@@Z; CHiPerfEnum::SetInstanceTemplate(CWbemInstance *)
0x180087533  mov     esi, eax
0x180087535  test    eax, eax
0x180087537  jns     short loc_1800875A4
0x180087539  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18008753f  mov     edx, esi
0x180087541  mov     rcx, rax
0x180087544  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18008754a  lea     rcx, WPP_GLOBAL_Control
0x180087551  mov     r10, cs:WPP_GLOBAL_Control
0x180087558  cmp     r10, rcx
0x18008755b  jz      short loc_180087584
0x18008755d  test    byte ptr [r10+1Ch], 1
0x180087562  jz      short loc_180087584
0x180087564  cmp     byte ptr [r10+19h], 2
0x180087569  jb      short loc_180087584
0x18008756b  mov     edx, 4Bh ; 'K'
0x180087570  mov     r9d, esi
0x180087573  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x18008757a  mov     rcx, [r10+10h]
0x18008757e  call    WPP_SF_d
0x180087583  nop
0x180087584  mov     rax, [rbx]
0x180087587  mov     rcx, rbx
0x18008758a  mov     rax, [rax+10h]
0x18008758e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087593  mov     [rsp+98h+arg_0], 0
0x18008759f  jmp     loc_180087509
0x1800875a4  mov     rax, [r13+10h]
0x1800875a8  mov     [rsp+98h+var_70], rax; struct CLifeControl *
0x1800875ad  mov     rax, [rsp+98h+arg_30]
0x1800875b5  mov     [rsp+98h+var_78], rax; int *
0x1800875ba  mov     r9, [rsp+98h+arg_28]; struct IWbemHiPerfEnum **
0x1800875c2  mov     r8, [rsp+98h+arg_18]; unsigned __int16 *
0x1800875ca  mov     rdx, rbx; struct CClientLoadableHiPerfEnum *
0x1800875cd  mov     rcx, r14; this
0x1800875d0  call    ?AddEnumRequest@CNonHiPerf@CUniversalRefresher@@QEAAJPEAVCClientLoadableHiPerfEnum@@PEBGPEAPEAUIWbemHiPerfEnum@@PEAJPEAVCLifeControl@@@Z; CUniversalRefresher::CNonHiPerf::AddEnumRequest(CClientLoadableHiPerfEnum *,ushort const *,IWbemHiPerfEnum * *,long *,CLifeControl *)
0x1800875d5  mov     esi, eax
0x1800875d7  test    eax, eax
0x1800875d9  jns     short loc_1800875EC
0x1800875db  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800875e1  mov     edx, esi
0x1800875e3  mov     rcx, rax
0x1800875e6  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800875ec  lea     rcx, WPP_GLOBAL_Control
0x1800875f3  mov     r10, cs:WPP_GLOBAL_Control
0x1800875fa  cmp     r10, rcx
0x1800875fd  jz      short loc_180087584
0x1800875ff  test    byte ptr [r10+1Ch], 1
0x180087604  jz      loc_180087584
0x18008760a  cmp     byte ptr [r10+19h], 2
0x18008760f  jb      loc_180087584
0x180087615  mov     edx, 4Ch ; 'L'
0x18008761a  jmp     loc_180087570
0x18008761f  mov     rcx, [rsp+98h+var_48]
0x180087624  test    rcx, rcx
0x180087627  jz      short loc_180087635
0x180087629  mov     rax, [rcx]
0x18008762c  mov     rax, [rax+10h]
0x180087630  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087635  mov     eax, 80041006h
0x18008763a  jmp     short loc_180087659
0x18008763c  mov     rcx, [rsp+98h+var_48]
0x180087641  test    rcx, rcx
0x180087644  jz      short loc_180087652
0x180087646  mov     rax, [rcx]
0x180087649  mov     rax, [rax+10h]
0x18008764d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087652  mov     eax, dword ptr [rsp+98h+arg_0]
0x180087659  mov     [rsp+98h+var_48], 0
0x180087662  mov     rbx, [rsp+98h+arg_10]
  ... truncated ...
```
