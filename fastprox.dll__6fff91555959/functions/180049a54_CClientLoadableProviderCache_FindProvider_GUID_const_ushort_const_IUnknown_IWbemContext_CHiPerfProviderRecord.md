# CClientLoadableProviderCache::FindProvider(_GUID const &,ushort const *,IUnknown *,IWbemContext *,CHiPerfProviderRecord * *)

- ea: `0x180049a54`
- end: `0x18004a268`
- name: `?FindProvider@CClientLoadableProviderCache@@QEAAJAEBU_GUID@@PEBGPEAUIUnknown@@PEAUIWbemContext@@PEAPEAVCHiPerfProviderRecord@@@Z`
- size: `2068`
- prototype: `__int64 __fastcall(CClientLoadableProviderCache *this, const struct _GUID *, const unsigned __int16 *, struct IUnknown *, struct IWbemContext *, struct CHiPerfProviderRecord **)`
- caller_count: `2`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x180046d48`
- `0x180049900`

## callees

- `0x180037120`
- `0x180046a38`
- `0x180049a54`
- `0x18004b3fc`
- `0x18004b47c`
- `0x18004b520`
- `0x1800700c8`
- `0x18007212c`
- `0x180086528`
- `0x18009e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180049b7b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180049b7b`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x180049ab3`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x180049ab3`
- `wbemcomn!GetMemLogObject` at `0x180049dd4`
- `wbemcomn!GetMemLogObject` at `0x180049e3e`
- `wbemcomn!GetMemLogObject` at `0x180049ecf`
- `wbemcomn!GetMemLogObject` at `0x180049eff`
- `wbemcomn!GetMemLogObject` at `0x180049f49`
- `wbemcomn!GetMemLogObject` at `0x180049fad`
- `wbemcomn!GetMemLogObject` at `0x18004a179`
- `wbemcomn!GetMemLogObject` at `0x18004a1c2`
- `wbemcomn!GetMemLogObject` at `0x18004a208`
- `wbemcomn!GetMemLogObject` at `0x180049dd4`
- `wbemcomn!GetMemLogObject` at `0x180049e3e`
- `wbemcomn!GetMemLogObject` at `0x180049ecf`
- `wbemcomn!GetMemLogObject` at `0x180049eff`
- `wbemcomn!GetMemLogObject` at `0x180049f49`
- `wbemcomn!GetMemLogObject` at `0x180049fad`
- `wbemcomn!GetMemLogObject` at `0x18004a179`
- `wbemcomn!GetMemLogObject` at `0x18004a1c2`
- `wbemcomn!GetMemLogObject` at `0x18004a208`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x180049aa4`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x180049aa4`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180049af1`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180049af1`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x180049a89`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x180049a89`
- `wbemcomn!?EqualNoCase@WString@@QEBAHPEBG@Z` at `0x180049ad9`
- `wbemcomn!?EqualNoCase@WString@@QEBAHPEBG@Z` at `0x180049ad9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180049ddf`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180049e4a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180049eda`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180049f0a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180049f55`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180049fbb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004a185`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004a1d0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004a216`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180049ddf`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180049e4a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180049eda`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180049f0a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180049f55`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180049fbb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004a185`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004a1d0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004a216`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180049bde`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180049cc5`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180049bde`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180049cc5`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CClientLoadableProviderCache::FindProvider(
        CClientLoadableProviderCache *this,
        const struct _GUID *a2,
        const unsigned __int16 *a3,
        struct IUnknown *a4,
        struct IWbemContext *a5,
        struct CHiPerfProviderRecord **a6)
{
  const struct _GUID *v8; // r15
  CFlexArray *v9; // rbx
  unsigned int v10; // r12d
  int i; // edi
  char *v12; // rbx
  __int64 v13; // rax
  int v15; // ebx
  __int64 v16; // rbx
  HRESULT v17; // esi
  LPVOID v18; // rdi
  __int64 v19; // rsi
  CProviderInitSink *v20; // rax
  volatile signed __int32 *inited; // r13
  int v22; // r14d
  struct IWbemHiPerfProvider *v23; // r14
  CHiPerfProviderRecord *v24; // rax
  CHiPerfProviderRecord *v25; // rax
  volatile signed __int32 *v26; // r15
  CMemoryLog *v27; // rax
  CMemoryLog *v28; // rax
  CMemoryLog *v29; // rax
  CMemoryLog *MemLogObject; // rax
  __int64 v31; // rdx
  __int64 v32; // rcx
  CMemoryLog *v33; // rax
  CWbemRefreshingSvc *v34; // r10
  __int64 v35; // rdx
  __int64 v36; // rcx
  CMemoryLog *v37; // rax
  CMemoryLog *v38; // rax
  CMemoryLog *v39; // rax
  CWbemRefreshingSvc *v40; // rax
  __int64 v41; // rdx
  CMemoryLog *v42; // rax
  LPVOID v43; // [rsp+58h] [rbp-A0h]
  volatile signed __int32 *v44; // [rsp+60h] [rbp-98h] BYREF
  __int64 v45; // [rsp+68h] [rbp-90h]
  __int64 v46; // [rsp+70h] [rbp-88h]
  volatile signed __int32 *v47; // [rsp+78h] [rbp-80h]
  LPVOID ppv; // [rsp+80h] [rbp-78h] BYREF
  struct IWbemHiPerfProvider *v49; // [rsp+88h] [rbp-70h]
  __int64 v50; // [rsp+90h] [rbp-68h] BYREF
  __int64 v51; // [rsp+98h] [rbp-60h] BYREF
  struct IWbemHiPerfProvider *v52; // [rsp+A0h] [rbp-58h] BYREF
  _BYTE v53[8]; // [rsp+A8h] [rbp-50h] BYREF
  ComException *v54; // [rsp+B0h] [rbp-48h] BYREF

  v8 = a2;
  v9 = this;
  CInCritSec::CInCritSec((CInCritSec *)v53, (struct _RTL_CRITICAL_SECTION *)((char *)this + 96));
  v10 = 0;
  *a6 = 0;
  for ( i = 0; i < CFlexArray::Size(v9); ++i )
  {
    v12 = (char *)CFlexArray::GetAt(v9, i);
    v13 = *(_QWORD *)(v12 + 4) - *(_QWORD *)&v8->Data1;
    if ( !v13 )
      v13 = *(_QWORD *)(v12 + 12) - *(_QWORD *)v8->Data4;
    if ( !v13 && WString::EqualNoCase((WString *)(v12 + 24), a3) )
    {
      *a6 = (struct CHiPerfProviderRecord *)v12;
      _InterlockedIncrement((volatile signed __int32 *)v12);
      goto LABEL_8;
    }
    v9 = this;
  }
  v51 = 0;
  v15 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a4->lpVtbl->QueryInterface)(
          a4,
          &IID_IWbemServices,
          &v51);
  if ( v15 >= 0 )
  {
    v16 = v51;
    v46 = v51;
    ppv = 0;
    v17 = CoCreateInstance(v8, 0, 1u, &IID_IUnknown, &ppv);
    v18 = ppv;
    v43 = ppv;
    if ( v17 < 0 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, v17);
      if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_34;
      }
      v31 = 165;
      v32 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    }
    else
    {
      v50 = 0;
      v17 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(ppv, &IID_IWbemProviderInit, &v50);
      if ( v17 >= 0 )
      {
        v19 = v50;
        v45 = v50;
        v20 = (CProviderInitSink *)CWin32DefaultArena::WbemMemAlloc(0x18u);
        v49 = (struct IWbemHiPerfProvider *)v20;
        if ( v20 )
          inited = (volatile signed __int32 *)CProviderInitSink::CProviderInitSink(v20);
        else
          inited = 0;
        v44 = inited;
        if ( !inited )
        {
          v37 = GetMemLogObject();
          CMemoryLog::Write(v37, -2147217402);
          if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              167,
              WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids,
              2147749894LL);
          }
          goto LABEL_62;
        }
        _InterlockedIncrement(inited + 2);
        v47 = inited;
        try
        {
          v22 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, const unsigned __int16 *, _QWORD, __int64, struct IWbemContext *, volatile signed __int32 *))(*(_QWORD *)v50 + 24LL))(
                  v50,
                  0,
                  0,
                  a3,
                  0,
                  v51,
                  a5,
                  inited);
        }
        catch ( ComException *v54 )
        {
          inited = v44;
          v19 = v45;
          v18 = v43;
          v16 = v46;
          v22 = *((_DWORD *)v54 + 2);
          v8 = a2;
          v10 = 0;
        }
        catch ( CX_MemoryException )
        {
          v22 = -2147217402;
          v16 = v46;
          v18 = v43;
          v19 = v45;
          inited = v44;
          goto LABEL_40;
        }
        catch ( CX_Exception )
        {
          inited = v44;
          v19 = v45;
          v18 = v43;
          v16 = v46;
          v22 = -2147217404;
          v8 = a2;
          v10 = 0;
        }
        if ( v22 < 0 )
        {
LABEL_40:
          v28 = GetMemLogObject();
          CMemoryLog::Write(v28, v22);
          if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_41;
          }
          v35 = 168;
          v36 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        }
        else
        {
          v22 = CProviderInitSink::WaitForCompletion((CProviderInitSink *)inited);
          if ( v22 < 0 )
          {
            v38 = GetMemLogObject();
            CMemoryLog::Write(v38, v22);
            v34 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_41;
            }
            v35 = 169;
          }
          else
          {
            v52 = 0;
            v22 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, struct IWbemHiPerfProvider **))ppv)(
                    ppv,
                    &IID_IWbemHiPerfProvider,
                    &v52);
            if ( v22 >= 0 )
            {
              v23 = v52;
              v49 = v52;
              v24 = (CHiPerfProviderRecord *)CWin32DefaultArena::WbemMemAlloc(0x30u);
              v44 = (volatile signed __int32 *)v24;
              if ( v24 )
                v25 = CHiPerfProviderRecord::CHiPerfProviderRecord(v24, v8, a3, v52, 0);
              else
                v25 = 0;
              std::unique_ptr<CClassInfo>::unique_ptr<CClassInfo>(&v44, (__int64)v25);
              v26 = v44;
              if ( v44 )
              {
                if ( (unsigned int)CPointerArray<CUniversalRefresher::CRemote::CObjectRequest,CUniqueManager<CUniversalRefresher::CRemote::CObjectRequest>,CFlexArray>::Add(
                                     this,
                                     v44) != -1 )
                {
                  _InterlockedIncrement(v26);
                  *a6 = (struct CHiPerfProviderRecord *)std::unique_ptr<CUniversalRefresher::CRemote::CEnumRequest>::release(&v44);
                  ((void (__fastcall *)(volatile signed __int32 **))std::unique_ptr<CHiPerfProviderRecord>::~unique_ptr<CHiPerfProviderRecord>)(&v44);
                  if ( v23 )
                    ((void (__fastcall *)(struct IWbemHiPerfProvider *))v23->lpVtbl->Release)(v23);
                  v49 = 0;
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)inited + 16LL))(inited);
                  v47 = 0;
                  if ( v19 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
                  v45 = 0;
                  if ( v18 )
                    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v18 + 16LL))(v18);
                  if ( v16 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
                  v46 = 0;
                  goto LABEL_8;
                }
                v42 = GetMemLogObject();
                CMemoryLog::Write(v42, -2147217402);
                v40 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_69;
                }
                v41 = 172;
              }
              else
              {
                v39 = GetMemLogObject();
                CMemoryLog::Write(v39, -2147217402);
                v40 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_69;
                }
                v41 = 171;
              }
              WPP_SF_d(*((_QWORD *)v40 + 2), v41, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids, 2147749894LL);
LABEL_69:
              ((void (__fastcall *)(volatile signed __int32 **))std::unique_ptr<CHiPerfProviderRecord>::~unique_ptr<CHiPerfProviderRecord>)(&v44);
              if ( v23 )
                ((void (__fastcall *)(struct IWbemHiPerfProvider *))v23->lpVtbl->Release)(v23);
              v49 = 0;
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)inited + 16LL))(inited);
              v47 = 0;
LABEL_62:
              if ( v19 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
              v45 = 0;
              if ( v18 )
                (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v18 + 16LL))(v18);
              if ( v16 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
              v46 = 0;
              v10 = -2147217402;
              goto LABEL_8;
            }
            v33 = GetMemLogObject();
            CMemoryLog::Write(v33, v22);
            v34 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_41;
            }
            v35 = 170;
          }
          v36 = *((_QWORD *)v34 + 2);
        }
        WPP_SF_d(v36, v35, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids, (unsigned int)v22);
LABEL_41:
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)inited + 16LL))(inited);
        v47 = 0;
        if ( v19 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
        v45 = 0;
        if ( v18 )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v18 + 16LL))(v18);
        if ( v16 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
        v46 = 0;
        v10 = v22;
        goto LABEL_8;
      }
      v27 = GetMemLogObject();
      CMemoryLog::Write(v27, v17);
      if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_34;
      }
      v31 = 166;
      v32 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    }
    WPP_SF_d(v32, v31, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids, (unsigned int)v17);
LABEL_34:
    if ( v18 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v18 + 16LL))(v18);
    if ( v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    v46 = 0;
    v10 = v17;
    goto LABEL_8;
  }
  v29 = GetMemLogObject();
  CMemoryLog::Write(v29, v15);
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      164,
      WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids,
      (unsigned int)v15);
  }
  v10 = v15;
LABEL_8:
  CInCritSec::~CInCritSec((CInCritSec *)v53);
  return v10;
}

```

## disassembly

```asm
0x180049a54  mov     rax, rsp
0x180049a57  mov     [rax+18h], r8
0x180049a5b  mov     [rax+10h], rdx
0x180049a5f  mov     [rax+8], rcx
0x180049a63  push    rbx
0x180049a64  push    rsi
0x180049a65  push    rdi
0x180049a66  push    r12
0x180049a68  push    r13
0x180049a6a  push    r14
0x180049a6c  push    r15
0x180049a6e  sub     rsp, 0C0h
0x180049a75  mov     r13, r9
0x180049a78  mov     r14, r8
0x180049a7b  mov     r15, rdx
0x180049a7e  mov     rbx, rcx
0x180049a81  lea     rdx, [rcx+60h]
0x180049a85  lea     rcx, [rax-50h]
0x180049a89  call    cs:__imp_??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x180049a8f  nop
0x180049a90  xor     r12d, r12d
0x180049a93  mov     rsi, [rsp+0F8h+arg_28]
0x180049a9b  mov     [rsi], r12
0x180049a9e  mov     edi, r12d
0x180049aa1  mov     rcx, rbx
0x180049aa4  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x180049aaa  cmp     edi, eax
0x180049aac  jge     short loc_180049B19
0x180049aae  mov     edx, edi
0x180049ab0  mov     rcx, rbx
0x180049ab3  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x180049ab9  mov     rbx, rax
0x180049abc  mov     rax, [rax+4]
0x180049ac0  sub     rax, [r15]
0x180049ac3  jnz     short loc_180049ACD
0x180049ac5  mov     rax, [rbx+0Ch]
0x180049ac9  sub     rax, [r15+8]
0x180049acd  test    rax, rax
0x180049ad0  jnz     short loc_180049B0D
0x180049ad2  lea     rcx, [rbx+18h]
0x180049ad6  mov     rdx, r14
0x180049ad9  call    cs:__imp_?EqualNoCase@WString@@QEBAHPEBG@Z; WString::EqualNoCase(ushort const *)
0x180049adf  test    eax, eax
0x180049ae1  jz      short loc_180049B0D
0x180049ae3  mov     [rsi], rbx
0x180049ae6  lock inc dword ptr [rbx]
0x180049ae9  lea     rcx, [rsp+0F8h+var_50]
0x180049af1  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x180049af7  mov     eax, r12d
0x180049afa  add     rsp, 0C0h
0x180049b01  pop     r15
0x180049b03  pop     r14
0x180049b05  pop     r13
0x180049b07  pop     r12
0x180049b09  pop     rdi
0x180049b0a  pop     rsi
0x180049b0b  pop     rbx
0x180049b0c  retn
0x180049b0d  inc     edi
0x180049b0f  mov     rbx, [rsp+0F8h+arg_0]
0x180049b17  jmp     short loc_180049AA1
0x180049b19  mov     [rsp+0F8h+var_60], r12
0x180049b21  mov     rax, [r13+0]
0x180049b25  lea     r8, [rsp+0F8h+var_60]
0x180049b2d  lea     rdx, IID_IWbemServices
0x180049b34  mov     rcx, r13
0x180049b37  mov     rax, [rax]
0x180049b3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049b3f  mov     ebx, eax
0x180049b41  test    eax, eax
0x180049b43  js      loc_180049ECF
0x180049b49  mov     rbx, [rsp+0F8h+var_60]
0x180049b51  mov     [rsp+0F8h+var_88], rbx
0x180049b56  mov     [rsp+0F8h+var_78], r12
0x180049b5e  lea     rax, [rsp+0F8h+var_78]
0x180049b66  mov     [rsp+0F8h+ppv], rax; ppv
0x180049b6b  lea     r9, IID_IUnknown; riid
0x180049b72  xor     edx, edx; pUnkOuter
0x180049b74  lea     r8d, [rdx+1]; dwClsContext
0x180049b78  mov     rcx, r15; rclsid
0x180049b7b  call    cs:__imp_CoCreateInstance
0x180049b81  mov     esi, eax
0x180049b83  mov     rdi, [rsp+0F8h+var_78]
0x180049b8b  mov     [rsp+0F8h+var_A0], rdi
0x180049b90  test    eax, eax
0x180049b92  js      loc_180049EFF
0x180049b98  mov     [rsp+0F8h+var_68], r12
0x180049ba0  mov     rcx, [rsp+0F8h+var_78]
0x180049ba8  mov     rax, [rcx]
0x180049bab  lea     r8, [rsp+0F8h+var_68]
0x180049bb3  lea     rdx, IID_IWbemProviderInit
0x180049bba  mov     rax, [rax]
0x180049bbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049bc2  mov     esi, eax
0x180049bc4  test    eax, eax
0x180049bc6  js      loc_180049DD4
0x180049bcc  mov     rsi, [rsp+0F8h+var_68]
0x180049bd4  mov     [rsp+0F8h+var_90], rsi
0x180049bd9  mov     ecx, 18h
0x180049bde  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180049be4  mov     [rsp+0F8h+var_70], rax
0x180049bec  test    rax, rax
0x180049bef  jz      loc_180049E36
0x180049bf5  mov     rcx, rax; this
0x180049bf8  call    ??0CProviderInitSink@@QEAA@XZ; CProviderInitSink::CProviderInitSink(void)
0x180049bfd  mov     r13, rax
0x180049c00  mov     [rsp+0F8h+var_98], r13
0x180049c05  test    r13, r13
0x180049c08  jz      loc_180049FAD
0x180049c0e  lock inc dword ptr [r13+8]
0x180049c13  mov     [rsp+0F8h+var_80], r13
0x180049c18  mov     rcx, [rsp+0F8h+var_68]
0x180049c20  mov     rax, [rcx]
0x180049c23  mov     [rsp+0F8h+var_C0], r13
0x180049c28  mov     rdx, [rsp+0F8h+arg_20]
0x180049c30  mov     [rsp+0F8h+var_C8], rdx
0x180049c35  mov     rdx, [rsp+0F8h+var_60]
0x180049c3d  mov     [rsp+0F8h+var_D0], rdx
0x180049c42  mov     [rsp+0F8h+ppv], r12
0x180049c47  mov     r9, r14
0x180049c4a  xor     r8d, r8d
0x180049c4d  xor     edx, edx
0x180049c4f  mov     rax, [rax+18h]
0x180049c53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049c58  mov     r14d, eax
0x180049c5b  mov     [rsp+0F8h+var_A8], eax
0x180049c5f  test    r14d, r14d
0x180049c62  js      loc_180049E3E
0x180049c68  mov     rcx, r13; this
0x180049c6b  call    ?WaitForCompletion@CProviderInitSink@@QEAAJXZ; CProviderInitSink::WaitForCompletion(void)
0x180049c70  mov     r14d, eax
0x180049c73  test    eax, eax
0x180049c75  js      loc_18004A179
0x180049c7b  mov     [rsp+0F8h+var_58], r12
0x180049c83  mov     rcx, [rsp+0F8h+var_78]
0x180049c8b  mov     rax, [rcx]
0x180049c8e  lea     r8, [rsp+0F8h+var_58]
0x180049c96  lea     rdx, IID_IWbemHiPerfProvider
0x180049c9d  mov     rax, [rax]
0x180049ca0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049ca5  mov     r14d, eax
0x180049ca8  test    eax, eax
0x180049caa  js      loc_180049F49
0x180049cb0  mov     r14, [rsp+0F8h+var_58]
0x180049cb8  mov     [rsp+0F8h+var_70], r14
0x180049cc0  mov     ecx, 30h ; '0'
0x180049cc5  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180049ccb  mov     [rsp+0F8h+var_98], rax
0x180049cd0  test    rax, rax
0x180049cd3  jz      loc_180049FA5
0x180049cd9  mov     [rsp+0F8h+ppv], r12; struct _IWmiProviderStack *
0x180049cde  mov     r9, [rsp+0F8h+var_58]; struct IWbemHiPerfProvider *
0x180049ce6  mov     r8, [rsp+0F8h+arg_10]; unsigned __int16 *
0x180049cee  mov     rdx, r15; struct _GUID *
0x180049cf1  mov     rcx, rax; this
0x180049cf4  call    ??0CHiPerfProviderRecord@@QEAA@AEBU_GUID@@PEBGPEAUIWbemHiPerfProvider@@PEAU_IWmiProviderStack@@@Z; CHiPerfProviderRecord::CHiPerfProviderRecord(_GUID const &,ushort const *,IWbemHiPerfProvider *,_IWmiProviderStack *)
0x180049cf9  nop
0x180049cfa  mov     rdx, rax
0x180049cfd  lea     rcx, [rsp+0F8h+var_98]
0x180049d02  call    ??0?$unique_ptr@UCClassInfo@@U?$default_delete@UCClassInfo@@@std@@@std@@QEAA@PEAUCClassInfo@@@Z; std::unique_ptr<CClassInfo>::unique_ptr<CClassInfo>(CClassInfo *)
0x180049d07  nop
0x180049d08  mov     r15, [rsp+0F8h+var_98]
0x180049d0d  test    r15, r15
0x180049d10  jz      loc_18004A1C2
0x180049d16  mov     rdx, r15
0x180049d19  mov     rcx, [rsp+0F8h+arg_0]
0x180049d21  call    ?Add@?$CPointerArray@VCObjectRequest@CRemote@CUniversalRefresher@@V?$CUniqueManager@VCObjectRequest@CRemote@CUniversalRefresher@@@@VCFlexArray@@@@QEAAHPEAVCObjectRequest@CRemote@CUniversalRefresher@@@Z; CPointerArray<CUniversalRefresher::CRemote::CObjectRequest,CUniqueManager<CUniversalRefresher::CRemote::CObjectRequest>,CFlexArray>::Add(CUniversalRefresher::CRemote::CObjectRequest *)
0x180049d26  cmp     eax, 0FFFFFFFFh
0x180049d29  jz      loc_18004A208
0x180049d2f  lock inc dword ptr [r15]
0x180049d33  lea     rcx, [rsp+0F8h+var_98]
0x180049d38  call    ?release@?$unique_ptr@VCEnumRequest@CRemote@CUniversalRefresher@@U?$default_delete@VCEnumRequest@CRemote@CUniversalRefresher@@@std@@@std@@QEAAPEAVCEnumRequest@CRemote@CUniversalRefresher@@XZ; std::unique_ptr<CUniversalRefresher::CRemote::CEnumRequest>::release(void)
0x180049d3d  mov     rcx, [rsp+0F8h+arg_28]
0x180049d45  mov     [rcx], rax
0x180049d48  lea     rcx, [rsp+0F8h+var_98]
0x180049d4d  call    ??1?$unique_ptr@VCHiPerfProviderRecord@@U?$default_delete@VCHiPerfProviderRecord@@@std@@@std@@QEAA@XZ; std::unique_ptr<CHiPerfProviderRecord>::~unique_ptr<CHiPerfProviderRecord>(void)
0x180049d52  nop
0x180049d53  test    r14, r14
0x180049d56  jz      short loc_180049D67
0x180049d58  mov     rax, [r14]
0x180049d5b  mov     rcx, r14
0x180049d5e  mov     rax, [rax+10h]
0x180049d62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049d67  mov     [rsp+0F8h+var_70], r12
0x180049d6f  mov     rax, [r13+0]
0x180049d73  mov     rcx, r13
0x180049d76  mov     rax, [rax+10h]
0x180049d7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049d7f  mov     [rsp+0F8h+var_80], r12
0x180049d84  test    rsi, rsi
0x180049d87  jz      short loc_180049D98
0x180049d89  mov     rax, [rsi]
0x180049d8c  mov     rcx, rsi
0x180049d8f  mov     rax, [rax+10h]
0x180049d93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049d98  mov     [rsp+0F8h+var_90], r12
0x180049d9d  test    rdi, rdi
0x180049da0  jz      short loc_180049DB1
0x180049da2  mov     rax, [rdi]
0x180049da5  mov     rcx, rdi
0x180049da8  mov     rax, [rax+10h]
0x180049dac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049db1  mov     [rsp+0F8h+var_A0], r12
0x180049db6  test    rbx, rbx
0x180049db9  jz      short loc_180049DCA
0x180049dbb  mov     rcx, [rbx]
0x180049dbe  mov     rax, [rcx+10h]
0x180049dc2  mov     rcx, rbx
0x180049dc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049dca  mov     [rsp+0F8h+var_88], r12
0x180049dcf  jmp     loc_180049AE9
0x180049dd4  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180049dda  mov     edx, esi
0x180049ddc  mov     rcx, rax
0x180049ddf  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180049de5  lea     rcx, WPP_GLOBAL_Control
0x180049dec  mov     r10, cs:WPP_GLOBAL_Control
0x180049df3  cmp     r10, rcx
0x180049df6  jnz     loc_18004A0BF
0x180049dfc  test    rdi, rdi
0x180049dff  jz      short loc_180049E10
0x180049e01  mov     rax, [rdi]
0x180049e04  mov     rcx, rdi
0x180049e07  mov     rax, [rax+10h]
0x180049e0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049e10  mov     [rsp+0F8h+var_A0], r12
0x180049e15  test    rbx, rbx
0x180049e18  jz      short loc_180049E29
0x180049e1a  mov     rax, [rbx]
0x180049e1d  mov     rcx, rbx
0x180049e20  mov     rax, [rax+10h]
0x180049e24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049e29  mov     [rsp+0F8h+var_88], r12
0x180049e2e  mov     r12d, esi
0x180049e31  jmp     loc_180049AE9
0x180049e36  mov     r13, r12
0x180049e39  jmp     loc_180049C00
0x180049e3e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180049e44  mov     edx, r14d
0x180049e47  mov     rcx, rax
0x180049e4a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180049e50  lea     rcx, WPP_GLOBAL_Control
0x180049e57  mov     rax, cs:WPP_GLOBAL_Control
0x180049e5e  cmp     rax, rcx
0x180049e61  jnz     loc_18004A157
0x180049e67  mov     rax, [r13+0]
0x180049e6b  mov     rcx, r13
0x180049e6e  mov     rax, [rax+10h]
0x180049e72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049e77  mov     [rsp+0F8h+var_80], r12
0x180049e7c  test    rsi, rsi
0x180049e7f  jz      short loc_180049E90
0x180049e81  mov     rax, [rsi]
0x180049e84  mov     rcx, rsi
0x180049e87  mov     rax, [rax+10h]
0x180049e8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049e90  mov     [rsp+0F8h+var_90], r12
0x180049e95  test    rdi, rdi
0x180049e98  jz      short loc_180049EA9
0x180049e9a  mov     rax, [rdi]
0x180049e9d  mov     rcx, rdi
0x180049ea0  mov     rax, [rax+10h]
0x180049ea4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049ea9  mov     [rsp+0F8h+var_A0], r12
0x180049eae  test    rbx, rbx
0x180049eb1  jz      short loc_180049EC2
0x180049eb3  mov     rax, [rbx]
0x180049eb6  mov     rcx, rbx
0x180049eb9  mov     rax, [rax+10h]
0x180049ebd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049ec2  mov     [rsp+0F8h+var_88], r12
0x180049ec7  mov     r12d, r14d
0x180049eca  jmp     loc_180049AE9
0x180049ecf  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180049ed5  mov     edx, ebx
0x180049ed7  mov     rcx, rax
0x180049eda  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180049ee0  lea     rcx, WPP_GLOBAL_Control
0x180049ee7  mov     r10, cs:WPP_GLOBAL_Control
0x180049eee  cmp     r10, rcx
0x180049ef1  jnz     loc_18004A06F
0x180049ef7  mov     r12d, ebx
0x180049efa  jmp     loc_180049AE9
0x180049eff  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180049f05  mov     edx, esi
0x180049f07  mov     rcx, rax
0x180049f0a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180049f10  lea     rcx, WPP_GLOBAL_Control
0x180049f17  mov     rax, cs:WPP_GLOBAL_Control
0x180049f1e  cmp     rax, rcx
0x180049f21  jz      loc_180049DFC
0x180049f27  test    byte ptr [rax+1Ch], 1
0x180049f2b  jz      loc_180049DFC
0x180049f31  cmp     byte ptr [rax+19h], 2
0x180049f35  jb      loc_180049DFC
0x180049f3b  mov     edx, 0A5h
0x180049f40  mov     rcx, [rax+10h]
0x180049f44  jmp     loc_18004A0AB
0x180049f49  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180049f4f  mov     edx, r14d
  ... truncated ...
```
