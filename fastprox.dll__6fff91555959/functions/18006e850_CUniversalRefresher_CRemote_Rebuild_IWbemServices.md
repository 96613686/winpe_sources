# CUniversalRefresher::CRemote::Rebuild(IWbemServices *)

- ea: `0x18006e850`
- end: `0x18006ec1f`
- name: `?Rebuild@CRemote@CUniversalRefresher@@QEAAJPEAUIWbemServices@@@Z`
- size: `975`
- prototype: `int(CUniversalRefresher::CRemote *__hidden this, struct IWbemServices *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18006ec48`

## callees

- `0x180037120`
- `0x180049704`
- `0x1800695fc`
- `0x18006e850`
- `0x18006ec28`
- `0x1800919b0`
- `0x18009e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x18006ea4a`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x18006ead0`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x18006ea4a`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x18006ead0`
- `wbemcomn!GetMemLogObject` at `0x18006e8b2`
- `wbemcomn!GetMemLogObject` at `0x18006e97d`
- `wbemcomn!GetMemLogObject` at `0x18006ea56`
- `wbemcomn!GetMemLogObject` at `0x18006eadc`
- `wbemcomn!GetMemLogObject` at `0x18006e8b2`
- `wbemcomn!GetMemLogObject` at `0x18006e97d`
- `wbemcomn!GetMemLogObject` at `0x18006ea56`
- `wbemcomn!GetMemLogObject` at `0x18006eadc`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18006e9f2`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18006ebb9`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18006e9f2`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18006ebb9`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18006e9e1`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18006e9e1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006e8bd`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006e988`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006ea61`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006eae7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006e8bd`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006e988`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006ea61`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006eae7`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CUniversalRefresher::CRemote::Rebuild(struct _RTL_CRITICAL_SECTION *this, IUnknown *a2)
{
  int RefreshingServices; // edi
  LPUNKNOWN v4; // rbx
  CMemoryLog *v5; // rax
  HRESULT v7; // esi
  LPUNKNOWN v8; // rdi
  CMemoryLog *v9; // rax
  CMemoryLog *v10; // rax
  CMemoryLog *MemLogObject; // rax
  LPWSTR pwszServerPrincName; // [rsp+48h] [rbp-71h] BYREF
  LPUNKNOWN v13; // [rsp+50h] [rbp-69h] BYREF
  _BYTE v14[8]; // [rsp+58h] [rbp-61h] BYREF
  int v15; // [rsp+60h] [rbp-59h] BYREF
  LPUNKNOWN pUnk; // [rsp+68h] [rbp-51h] BYREF
  LPSTREAM ppStm; // [rsp+70h] [rbp-49h] BYREF
  LPSTREAM v18[2]; // [rsp+78h] [rbp-41h] BYREF
  LPSTREAM v19; // [rsp+88h] [rbp-31h] BYREF
  char v20; // [rsp+90h] [rbp-29h]
  LPSTREAM v21; // [rsp+98h] [rbp-21h] BYREF
  char v22; // [rsp+A0h] [rbp-19h]
  _COAUTHINFO v23; // [rsp+A8h] [rbp-11h] BYREF
  __int128 v24; // [rsp+D0h] [rbp+17h] BYREF

  memset(&v23, 0, sizeof(v23));
  v13 = 0;
  RefreshingServices = CUniversalRefresher::GetRefreshingServices(a2, (struct IWbemRefreshingServices **)&v13, &v23);
  v4 = v13;
  v18[1] = (LPSTREAM)v13;
  if ( RefreshingServices >= 0 )
  {
    pwszServerPrincName = v23.pwszServerPrincName;
    pUnk = 0;
    v24 = 0;
    v15 = 0;
    v7 = ((__int64 (__fastcall *)(LPUNKNOWN, ULONG_PTR, _QWORD, __int64, LPUNKNOWN *, __int128 *, int *))v13->lpVtbl[2].AddRef)(
           v13,
           this[6].SpinCount + 416,
           0,
           2,
           &pUnk,
           &v24,
           &v15);
    v8 = pUnk;
    if ( v7 >= 0 )
    {
      CInCritSec::CInCritSec((CInCritSec *)v14, this + 7);
      if ( LODWORD(this[2].DebugInfo) )
      {
        CInCritSec::~CInCritSec((CInCritSec *)v14);
        if ( v8 )
          ((void (__fastcall *)(LPUNKNOWN))v8->lpVtbl->Release)(v8);
        CMemFreeMe::~CMemFreeMe((void **)&pwszServerPrincName);
        if ( v4 )
          ((void (__fastcall *)(LPUNKNOWN))v4->lpVtbl->Release)(v4);
        return 0;
      }
      ppStm = 0;
      v7 = CoMarshalInterThreadInterfaceInStream(&IID_IWbemRemoteRefresher, pUnk, &ppStm);
      if ( v7 >= 0 )
      {
        v19 = ppStm;
        v20 = 0;
        v18[0] = 0;
        v7 = CoMarshalInterThreadInterfaceInStream(&IID_IWbemRefreshingServices, v13, v18);
        if ( v7 >= 0 )
        {
          v21 = v18[0];
          *(_OWORD *)&this[8].OwningThread = v24;
          v20 = 1;
          this[8].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)ppStm;
          v22 = 1;
          *(LPSTREAM *)&this[8].LockCount = v18[0];
          if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              154,
              WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids,
              (unsigned int)v7);
          }
          OnDeleteIf<IStream *,long (*)(IStream *),&long CleanupStreamWithInterface(IStream *)>::~OnDeleteIf<IStream *,long (*)(IStream *),&long CleanupStreamWithInterface(IStream *)>((__int64)&v21);
        }
        else
        {
          MemLogObject = GetMemLogObject();
          CMemoryLog::Write(MemLogObject, v7);
          if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              153,
              WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids,
              (unsigned int)v7);
          }
        }
        OnDeleteIf<IStream *,long (*)(IStream *),&long CleanupStreamWithInterface(IStream *)>::~OnDeleteIf<IStream *,long (*)(IStream *),&long CleanupStreamWithInterface(IStream *)>((__int64)&v19);
      }
      else
      {
        v10 = GetMemLogObject();
        CMemoryLog::Write(v10, v7);
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            152,
            WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids,
            (unsigned int)v7);
        }
      }
      CInCritSec::~CInCritSec((CInCritSec *)v14);
    }
    else
    {
      v9 = GetMemLogObject();
      CMemoryLog::Write(v9, v7);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          151,
          WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids,
          (unsigned int)v7);
      }
    }
    if ( v8 )
      ((void (__fastcall *)(LPUNKNOWN))v8->lpVtbl->Release)(v8);
    CMemFreeMe::~CMemFreeMe((void **)&pwszServerPrincName);
    if ( v4 )
      ((void (__fastcall *)(LPUNKNOWN))v4->lpVtbl->Release)(v4);
    return (unsigned int)v7;
  }
  v5 = GetMemLogObject();
  CMemoryLog::Write(v5, RefreshingServices);
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      150,
      WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids,
      (unsigned int)RefreshingServices);
  }
  if ( v4 )
    ((void (__fastcall *)(LPUNKNOWN))v4->lpVtbl->Release)(v4);
  return (unsigned int)RefreshingServices;
}

```

## disassembly

```asm
0x18006e850  mov     [rsp-8+arg_10], rbx
0x18006e855  push    rbp
0x18006e856  push    rsi
0x18006e857  push    rdi
0x18006e858  push    r14
0x18006e85a  push    r15
0x18006e85c  lea     rbp, [rsp-37h]
0x18006e861  sub     rsp, 0F0h
0x18006e868  mov     rax, cs:__security_cookie
0x18006e86f  xor     rax, rsp
0x18006e872  mov     [rbp+57h+var_30], rax
0x18006e876  mov     rax, rdx
0x18006e879  mov     r14, rcx
0x18006e87c  xorps   xmm0, xmm0
0x18006e87f  xor     ecx, ecx
0x18006e881  movups  xmmword ptr [rbp+57h+var_68.dwAuthnSvc], xmm0
0x18006e885  movups  xmmword ptr [rbp+57h+var_68.dwAuthnLevel], xmm0
0x18006e889  mov     qword ptr [rbp+57h+var_68.dwCapabilities], rcx
0x18006e88d  xor     r15d, r15d
0x18006e890  mov     [rbp+57h+var_C0], r15
0x18006e894  lea     r8, [rbp+57h+var_68]; struct _COAUTHINFO *
0x18006e898  lea     rdx, [rbp+57h+var_C0]; struct IWbemRefreshingServices **
0x18006e89c  mov     rcx, rax; pProxy
0x18006e89f  call    ?GetRefreshingServices@CUniversalRefresher@@SAJPEAUIWbemServices@@PEAPEAUIWbemRefreshingServices@@PEAU_COAUTHINFO@@@Z; CUniversalRefresher::GetRefreshingServices(IWbemServices *,IWbemRefreshingServices * *,_COAUTHINFO *)
0x18006e8a4  mov     edi, eax
0x18006e8a6  mov     rbx, [rbp+57h+var_C0]
0x18006e8aa  mov     [rbp+57h+var_90], rbx
0x18006e8ae  test    eax, eax
0x18006e8b0  jns     short loc_18006E916
0x18006e8b2  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18006e8b8  mov     edx, edi
0x18006e8ba  mov     rcx, rax
0x18006e8bd  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18006e8c3  lea     rcx, WPP_GLOBAL_Control
0x18006e8ca  mov     rax, cs:WPP_GLOBAL_Control
0x18006e8d1  cmp     rax, rcx
0x18006e8d4  jz      short loc_18006E8FB
0x18006e8d6  test    byte ptr [rax+1Ch], 1
0x18006e8da  jz      short loc_18006E8FB
0x18006e8dc  cmp     byte ptr [rax+19h], 2
0x18006e8e0  jb      short loc_18006E8FB
0x18006e8e2  mov     edx, 96h
0x18006e8e7  mov     r9d, edi
0x18006e8ea  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x18006e8f1  mov     rcx, [rax+10h]
0x18006e8f5  call    WPP_SF_d
0x18006e8fa  nop
0x18006e8fb  test    rbx, rbx
0x18006e8fe  jz      short loc_18006E90F
0x18006e900  mov     rax, [rbx]
0x18006e903  mov     rcx, rbx
0x18006e906  mov     rax, [rax+10h]
0x18006e90a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e90f  mov     eax, edi
0x18006e911  jmp     loc_18006EBF8
0x18006e916  mov     rax, [rbp+57h+var_68.pwszServerPrincName]
0x18006e91a  mov     [rbp+57h+var_C8], rax
0x18006e91e  mov     [rbp+57h+pUnk], r15
0x18006e922  xorps   xmm0, xmm0
0x18006e925  movups  [rbp+57h+var_40], xmm0
0x18006e929  mov     [rbp+57h+var_B0], r15d
0x18006e92d  mov     rcx, [rbp+57h+var_C0]
0x18006e931  mov     rax, [rcx]
0x18006e934  mov     rdx, [r14+110h]
0x18006e93b  add     rdx, 1A0h
0x18006e942  lea     r8, [rbp+57h+var_B0]
0x18006e946  mov     [rsp+110h+var_E0], r8
0x18006e94b  lea     r8, [rbp+57h+var_40]
0x18006e94f  mov     [rsp+110h+var_E8], r8
0x18006e954  lea     r8, [rbp+57h+pUnk]
0x18006e958  mov     [rsp+110h+var_F0], r8
0x18006e95d  mov     r9d, 2
0x18006e963  xor     r8d, r8d
0x18006e966  mov     rax, [rax+38h]
0x18006e96a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e96f  mov     esi, eax
0x18006e971  mov     rdi, [rbp+57h+pUnk]
0x18006e975  mov     [rbp+57h+var_D0], rdi
0x18006e979  test    eax, eax
0x18006e97b  jns     short loc_18006E9D6
0x18006e97d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18006e983  mov     edx, esi
0x18006e985  mov     rcx, rax
0x18006e988  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18006e98e  lea     rcx, WPP_GLOBAL_Control
0x18006e995  mov     rax, cs:WPP_GLOBAL_Control
0x18006e99c  cmp     rax, rcx
0x18006e99f  jz      loc_18006EBC0
0x18006e9a5  test    byte ptr [rax+1Ch], 1
0x18006e9a9  jz      loc_18006EBC0
0x18006e9af  cmp     byte ptr [rax+19h], 2
0x18006e9b3  jb      loc_18006EBC0
0x18006e9b9  mov     edx, 97h
0x18006e9be  mov     r9d, esi
0x18006e9c1  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x18006e9c8  mov     rcx, [rax+10h]
0x18006e9cc  call    WPP_SF_d
0x18006e9d1  jmp     loc_18006EBC0
0x18006e9d6  lea     rdx, [r14+118h]
0x18006e9dd  lea     rcx, [rbp+57h+var_B8]
0x18006e9e1  call    cs:__imp_??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x18006e9e7  nop
0x18006e9e8  cmp     [r14+50h], r15d
0x18006e9ec  jz      short loc_18006EA37
0x18006e9ee  lea     rcx, [rbp+57h+var_B8]
0x18006e9f2  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x18006e9f8  nop
0x18006e9f9  test    rdi, rdi
0x18006e9fc  jz      short loc_18006EA0D
0x18006e9fe  mov     rax, [rdi]
0x18006ea01  mov     rcx, rdi
0x18006ea04  mov     rax, [rax+10h]
0x18006ea08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ea0d  mov     [rbp+57h+var_D0], r15
0x18006ea11  lea     rcx, [rbp+57h+var_C8]; this
0x18006ea15  call    ??1CMemFreeMe@@QEAA@XZ; CMemFreeMe::~CMemFreeMe(void)
0x18006ea1a  nop
0x18006ea1b  test    rbx, rbx
0x18006ea1e  jz      short loc_18006EA2F
0x18006ea20  mov     rax, [rbx]
0x18006ea23  mov     rcx, rbx
0x18006ea26  mov     rax, [rax+10h]
0x18006ea2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ea2f  mov     esi, r15d
0x18006ea32  jmp     loc_18006EBF6
0x18006ea37  mov     [rbp+57h+ppStm], r15
0x18006ea3b  lea     r8, [rbp+57h+ppStm]; ppStm
0x18006ea3f  mov     rdx, [rbp+57h+pUnk]; pUnk
0x18006ea43  lea     rcx, IID_IWbemRemoteRefresher; riid
0x18006ea4a  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x18006ea50  mov     esi, eax
0x18006ea52  test    eax, eax
0x18006ea54  jns     short loc_18006EAB1
0x18006ea56  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18006ea5c  mov     edx, esi
0x18006ea5e  mov     rcx, rax
0x18006ea61  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18006ea67  lea     rcx, WPP_GLOBAL_Control
0x18006ea6e  mov     r10, cs:WPP_GLOBAL_Control
0x18006ea75  cmp     r10, rcx
0x18006ea78  jz      loc_18006EBB5
0x18006ea7e  test    byte ptr [r10+1Ch], 1
0x18006ea83  jz      loc_18006EBB5
0x18006ea89  cmp     byte ptr [r10+19h], 2
0x18006ea8e  jb      loc_18006EBB5
0x18006ea94  mov     edx, 98h
0x18006ea99  mov     r9d, esi
0x18006ea9c  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x18006eaa3  mov     rcx, [r10+10h]
0x18006eaa7  call    WPP_SF_d
0x18006eaac  jmp     loc_18006EBB5
0x18006eab1  mov     rax, [rbp+57h+ppStm]
0x18006eab5  mov     [rbp+57h+var_88], rax
0x18006eab9  mov     [rbp+57h+var_80], r15b
0x18006eabd  mov     [rbp+57h+var_98], r15
0x18006eac1  lea     r8, [rbp+57h+var_98]; ppStm
0x18006eac5  mov     rdx, [rbp+57h+var_C0]; pUnk
0x18006eac9  lea     rcx, IID_IWbemRefreshingServices; riid
0x18006ead0  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x18006ead6  mov     esi, eax
0x18006ead8  test    eax, eax
0x18006eada  jns     short loc_18006EB32
0x18006eadc  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18006eae2  mov     edx, esi
0x18006eae4  mov     rcx, rax
0x18006eae7  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18006eaed  lea     rcx, WPP_GLOBAL_Control
0x18006eaf4  mov     rax, cs:WPP_GLOBAL_Control
0x18006eafb  cmp     rax, rcx
0x18006eafe  jz      loc_18006EBAB
0x18006eb04  test    byte ptr [rax+1Ch], 1
0x18006eb08  jz      loc_18006EBAB
0x18006eb0e  cmp     byte ptr [rax+19h], 2
0x18006eb12  jb      loc_18006EBAB
0x18006eb18  mov     edx, 99h
0x18006eb1d  mov     r9d, esi
0x18006eb20  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x18006eb27  mov     rcx, [rax+10h]
0x18006eb2b  call    WPP_SF_d
0x18006eb30  jmp     short loc_18006EBAB
0x18006eb32  mov     rax, [rbp+57h+var_98]
0x18006eb36  mov     [rbp+57h+var_78], rax
0x18006eb3a  mov     [rbp+57h+var_70], r15b
0x18006eb3e  movups  xmm0, [rbp+57h+var_40]
0x18006eb42  movdqu  xmmword ptr [r14+150h], xmm0
0x18006eb4b  mov     [rbp+57h+var_80], 1
0x18006eb4f  mov     rax, [rbp+57h+ppStm]
0x18006eb53  mov     [r14+140h], rax
0x18006eb5a  mov     [rbp+57h+var_70], 1
0x18006eb5e  mov     rax, [rbp+57h+var_98]
0x18006eb62  mov     [r14+148h], rax
0x18006eb69  lea     rcx, WPP_GLOBAL_Control
0x18006eb70  mov     rax, cs:WPP_GLOBAL_Control
0x18006eb77  cmp     rax, rcx
0x18006eb7a  jz      short loc_18006EBA1
0x18006eb7c  test    byte ptr [rax+1Ch], 1
0x18006eb80  jz      short loc_18006EBA1
0x18006eb82  cmp     byte ptr [rax+19h], 2
0x18006eb86  jb      short loc_18006EBA1
0x18006eb88  mov     edx, 9Ah
0x18006eb8d  mov     r9d, esi
0x18006eb90  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x18006eb97  mov     rcx, [rax+10h]
0x18006eb9b  call    WPP_SF_d
0x18006eba0  nop
0x18006eba1  lea     rcx, [rbp+57h+var_78]
0x18006eba5  call    ??1?$OnDeleteIf@PEAUIStream@@P6AJPEAU1@@Z$1?CleanupStreamWithInterface@@YAJ0@Z@@QEAA@XZ; OnDeleteIf<IStream *,long (*)(IStream *),&CleanupStreamWithInterface(IStream *)>::~OnDeleteIf<IStream *,long (*)(IStream *),&CleanupStreamWithInterface(IStream *)>(void)
0x18006ebaa  nop
0x18006ebab  lea     rcx, [rbp+57h+var_88]
0x18006ebaf  call    ??1?$OnDeleteIf@PEAUIStream@@P6AJPEAU1@@Z$1?CleanupStreamWithInterface@@YAJ0@Z@@QEAA@XZ; OnDeleteIf<IStream *,long (*)(IStream *),&CleanupStreamWithInterface(IStream *)>::~OnDeleteIf<IStream *,long (*)(IStream *),&CleanupStreamWithInterface(IStream *)>(void)
0x18006ebb4  nop
0x18006ebb5  lea     rcx, [rbp+57h+var_B8]
0x18006ebb9  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x18006ebbf  nop
0x18006ebc0  test    rdi, rdi
0x18006ebc3  jz      short loc_18006EBD4
0x18006ebc5  mov     rax, [rdi]
0x18006ebc8  mov     rcx, rdi
0x18006ebcb  mov     rax, [rax+10h]
0x18006ebcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ebd4  mov     [rbp+57h+var_D0], r15
0x18006ebd8  lea     rcx, [rbp+57h+var_C8]; this
0x18006ebdc  call    ??1CMemFreeMe@@QEAA@XZ; CMemFreeMe::~CMemFreeMe(void)
0x18006ebe1  nop
0x18006ebe2  test    rbx, rbx
0x18006ebe5  jz      short loc_18006EBF6
0x18006ebe7  mov     rax, [rbx]
0x18006ebea  mov     rcx, rbx
0x18006ebed  mov     rax, [rax+10h]
0x18006ebf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ebf6  mov     eax, esi
0x18006ebf8  mov     [rbp+57h+var_90], r15
0x18006ebfc  mov     rcx, [rbp+57h+var_30]
0x18006ec00  xor     rcx, rsp; StackCookie
0x18006ec03  call    __security_check_cookie
0x18006ec08  mov     rbx, [rsp+110h+arg_10]
0x18006ec10  add     rsp, 0F0h
0x18006ec17  pop     r15
0x18006ec19  pop     r14
0x18006ec1b  pop     rdi
0x18006ec1c  pop     rsi
0x18006ec1d  pop     rbp
0x18006ec1e  retn
```
