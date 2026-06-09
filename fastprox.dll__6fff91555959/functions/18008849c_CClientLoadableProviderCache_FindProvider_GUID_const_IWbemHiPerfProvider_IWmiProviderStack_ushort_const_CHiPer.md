# CClientLoadableProviderCache::FindProvider(_GUID const &,IWbemHiPerfProvider *,_IWmiProviderStack *,ushort const *,CHiPerfProviderRecord * *)

- ea: `0x18008849c`
- end: `0x18008866b`
- name: `?FindProvider@CClientLoadableProviderCache@@QEAAJAEBU_GUID@@PEAUIWbemHiPerfProvider@@PEAU_IWmiProviderStack@@PEBGPEAPEAVCHiPerfProviderRecord@@@Z`
- size: `463`
- prototype: `int(CClientLoadableProviderCache *__hidden this, const struct _GUID *, struct IWbemHiPerfProvider *, struct _IWmiProviderStack *, const unsigned __int16 *, struct CHiPerfProviderRecord **)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800868d8`
- `0x180086af8`

## callees

- `0x180037120`
- `0x180046a38`
- `0x18004b520`
- `0x1800700c8`
- `0x18007212c`
- `0x180086528`
- `0x18008849c`

## import_xrefs

- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x1800884ea`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x1800884ea`
- `wbemcomn!GetMemLogObject` at `0x180088581`
- `wbemcomn!GetMemLogObject` at `0x1800885cd`
- `wbemcomn!GetMemLogObject` at `0x180088581`
- `wbemcomn!GetMemLogObject` at `0x1800885cd`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x1800884db`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x1800884db`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180088654`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180088654`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x1800884c0`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x1800884c0`
- `wbemcomn!?EqualNoCase@WString@@QEBAHPEBG@Z` at `0x180088516`
- `wbemcomn!?EqualNoCase@WString@@QEBAHPEBG@Z` at `0x180088516`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180088591`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800885dd`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180088591`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800885dd`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180088534`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180088534`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CClientLoadableProviderCache::FindProvider(
        CClientLoadableProviderCache *this,
        const struct _GUID *a2,
        struct IWbemHiPerfProvider *a3,
        struct _IWmiProviderStack *a4,
        unsigned __int16 *a5,
        struct CHiPerfProviderRecord **a6)
{
  struct CHiPerfProviderRecord **v10; // r14
  int i; // edi
  char *v12; // rbx
  __int64 v13; // rax
  struct CHiPerfProviderRecord **v14; // rax
  volatile signed __int32 *v15; // rbx
  CMemoryLog *v16; // rax
  unsigned int v17; // ebx
  unsigned int v18; // edx
  CWbemRefreshingSvc *v19; // rcx
  __int64 v20; // rdx
  CMemoryLog *MemLogObject; // rax
  unsigned int v22; // edx
  _BYTE v24[72]; // [rsp+30h] [rbp-48h] BYREF

  CInCritSec::CInCritSec((CInCritSec *)v24, (struct _RTL_CRITICAL_SECTION *)((char *)this + 96));
  v10 = a6;
  *a6 = 0;
  for ( i = 0; ; ++i )
  {
    if ( i >= CFlexArray::Size(this) )
    {
      v14 = (struct CHiPerfProviderRecord **)CWin32DefaultArena::WbemMemAlloc(0x30u);
      a6 = v14;
      if ( v14 )
        v14 = (struct CHiPerfProviderRecord **)CHiPerfProviderRecord::CHiPerfProviderRecord(
                                                 (CHiPerfProviderRecord *)v14,
                                                 a2,
                                                 a5,
                                                 a3,
                                                 a4);
      std::unique_ptr<CClassInfo>::unique_ptr<CClassInfo>(&a6, (__int64)v14);
      v15 = (volatile signed __int32 *)a6;
      if ( a6 )
      {
        if ( (unsigned int)CPointerArray<CUniversalRefresher::CRemote::CObjectRequest,CUniqueManager<CUniversalRefresher::CRemote::CObjectRequest>,CFlexArray>::Add(
                             this,
                             a6) != -1 )
        {
          _InterlockedIncrement(v15);
          *v10 = (struct CHiPerfProviderRecord *)std::unique_ptr<CUniversalRefresher::CRemote::CEnumRequest>::release(&a6);
          std::unique_ptr<CHiPerfProviderRecord>::~unique_ptr<CHiPerfProviderRecord>((CHiPerfProviderRecord **)&a6, v22);
          goto LABEL_24;
        }
        MemLogObject = GetMemLogObject();
        v17 = -2147217402;
        CMemoryLog::Write(MemLogObject, -2147217402);
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
LABEL_22:
          std::unique_ptr<CHiPerfProviderRecord>::~unique_ptr<CHiPerfProviderRecord>((CHiPerfProviderRecord **)&a6, v18);
          goto LABEL_25;
        }
        v20 = 174;
      }
      else
      {
        v16 = GetMemLogObject();
        v17 = -2147217402;
        CMemoryLog::Write(v16, -2147217402);
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_22;
        }
        v20 = 173;
      }
      WPP_SF_d(*((_QWORD *)v19 + 2), v20, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids, 2147749894LL);
      goto LABEL_22;
    }
    v12 = (char *)CFlexArray::GetAt(this, i);
    v13 = *(_QWORD *)(v12 + 4) - *(_QWORD *)&a2->Data1;
    if ( !v13 )
      v13 = *(_QWORD *)(v12 + 12) - *(_QWORD *)a2->Data4;
    if ( !v13 && WString::EqualNoCase((WString *)(v12 + 24), a5) )
      break;
  }
  *v10 = (struct CHiPerfProviderRecord *)v12;
  _InterlockedIncrement((volatile signed __int32 *)v12);
LABEL_24:
  v17 = 0;
LABEL_25:
  CInCritSec::~CInCritSec((CInCritSec *)v24);
  return v17;
}

```

## disassembly

```asm
0x18008849c  push    rbx
0x18008849e  push    rbp
0x18008849f  push    rsi
0x1800884a0  push    rdi
0x1800884a1  push    r12
0x1800884a3  push    r14
0x1800884a5  push    r15
0x1800884a7  sub     rsp, 40h
0x1800884ab  mov     r15, r9
0x1800884ae  mov     r12, r8
0x1800884b1  mov     rbp, rdx
0x1800884b4  mov     rsi, rcx
0x1800884b7  lea     rdx, [rcx+60h]
0x1800884bb  lea     rcx, [rsp+78h+var_48]
0x1800884c0  call    cs:__imp_??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x1800884c6  nop
0x1800884c7  mov     r14, [rsp+78h+arg_28]
0x1800884cf  mov     qword ptr [r14], 0
0x1800884d6  xor     edi, edi
0x1800884d8  mov     rcx, rsi
0x1800884db  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x1800884e1  cmp     edi, eax
0x1800884e3  jge     short loc_18008852F
0x1800884e5  mov     edx, edi
0x1800884e7  mov     rcx, rsi
0x1800884ea  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x1800884f0  mov     rbx, rax
0x1800884f3  mov     rax, [rax+4]
0x1800884f7  sub     rax, [rbp+0]
0x1800884fb  jnz     short loc_180088505
0x1800884fd  mov     rax, [rbx+0Ch]
0x180088501  sub     rax, [rbp+8]
0x180088505  test    rax, rax
0x180088508  jnz     short loc_180088520
0x18008850a  lea     rcx, [rbx+18h]
0x18008850e  mov     rdx, [rsp+78h+arg_20]
0x180088516  call    cs:__imp_?EqualNoCase@WString@@QEBAHPEBG@Z; WString::EqualNoCase(ushort const *)
0x18008851c  test    eax, eax
0x18008851e  jnz     short loc_180088524
0x180088520  inc     edi
0x180088522  jmp     short loc_1800884D8
0x180088524  mov     [r14], rbx
0x180088527  lock inc dword ptr [rbx]
0x18008852a  jmp     loc_18008864D
0x18008852f  mov     ecx, 30h ; '0'
0x180088534  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18008853a  mov     [rsp+78h+arg_28], rax
0x180088542  test    rax, rax
0x180088545  jz      short loc_180088563
0x180088547  mov     [rsp+78h+var_58], r15; struct _IWmiProviderStack *
0x18008854c  mov     r9, r12; struct IWbemHiPerfProvider *
0x18008854f  mov     r8, [rsp+78h+arg_20]; unsigned __int16 *
0x180088557  mov     rdx, rbp; struct _GUID *
0x18008855a  mov     rcx, rax; this
0x18008855d  call    ??0CHiPerfProviderRecord@@QEAA@AEBU_GUID@@PEBGPEAUIWbemHiPerfProvider@@PEAU_IWmiProviderStack@@@Z; CHiPerfProviderRecord::CHiPerfProviderRecord(_GUID const &,ushort const *,IWbemHiPerfProvider *,_IWmiProviderStack *)
0x180088562  nop
0x180088563  mov     rdx, rax
0x180088566  lea     rcx, [rsp+78h+arg_28]
0x18008856e  call    ??0?$unique_ptr@UCClassInfo@@U?$default_delete@UCClassInfo@@@std@@@std@@QEAA@PEAUCClassInfo@@@Z; std::unique_ptr<CClassInfo>::unique_ptr<CClassInfo>(CClassInfo *)
0x180088573  nop
0x180088574  mov     rbx, [rsp+78h+arg_28]
0x18008857c  test    rbx, rbx
0x18008857f  jnz     short loc_1800885BD
0x180088581  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180088587  mov     ebx, 80041006h
0x18008858c  mov     edx, ebx
0x18008858e  mov     rcx, rax
0x180088591  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180088597  lea     rax, WPP_GLOBAL_Control
0x18008859e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800885a5  cmp     rcx, rax
0x1800885a8  jz      short loc_18008861E
0x1800885aa  test    byte ptr [rcx+1Ch], 1
0x1800885ae  jz      short loc_18008861E
0x1800885b0  cmp     byte ptr [rcx+19h], 2
0x1800885b4  jb      short loc_18008861E
0x1800885b6  mov     edx, 0ADh
0x1800885bb  jmp     short loc_180088607
0x1800885bd  mov     rdx, rbx
0x1800885c0  mov     rcx, rsi
0x1800885c3  call    ?Add@?$CPointerArray@VCObjectRequest@CRemote@CUniversalRefresher@@V?$CUniqueManager@VCObjectRequest@CRemote@CUniversalRefresher@@@@VCFlexArray@@@@QEAAHPEAVCObjectRequest@CRemote@CUniversalRefresher@@@Z; CPointerArray<CUniversalRefresher::CRemote::CObjectRequest,CUniqueManager<CUniversalRefresher::CRemote::CObjectRequest>,CFlexArray>::Add(CUniversalRefresher::CRemote::CObjectRequest *)
0x1800885c8  cmp     eax, 0FFFFFFFFh
0x1800885cb  jnz     short loc_18008862D
0x1800885cd  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800885d3  mov     ebx, 80041006h
0x1800885d8  mov     edx, ebx
0x1800885da  mov     rcx, rax
0x1800885dd  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800885e3  lea     rax, WPP_GLOBAL_Control
0x1800885ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800885f1  cmp     rcx, rax
0x1800885f4  jz      short loc_18008861E
0x1800885f6  test    byte ptr [rcx+1Ch], 1
0x1800885fa  jz      short loc_18008861E
0x1800885fc  cmp     byte ptr [rcx+19h], 2
0x180088600  jb      short loc_18008861E
0x180088602  mov     edx, 0AEh
0x180088607  mov     r9d, 80041006h
0x18008860d  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x180088614  mov     rcx, [rcx+10h]
0x180088618  call    WPP_SF_d
0x18008861d  nop
0x18008861e  lea     rcx, [rsp+78h+arg_28]
0x180088626  call    ??1?$unique_ptr@VCHiPerfProviderRecord@@U?$default_delete@VCHiPerfProviderRecord@@@std@@@std@@QEAA@XZ; std::unique_ptr<CHiPerfProviderRecord>::~unique_ptr<CHiPerfProviderRecord>(void)
0x18008862b  jmp     short loc_18008864F
0x18008862d  lock inc dword ptr [rbx]
0x180088630  lea     rcx, [rsp+78h+arg_28]
0x180088638  call    ?release@?$unique_ptr@VCEnumRequest@CRemote@CUniversalRefresher@@U?$default_delete@VCEnumRequest@CRemote@CUniversalRefresher@@@std@@@std@@QEAAPEAVCEnumRequest@CRemote@CUniversalRefresher@@XZ; std::unique_ptr<CUniversalRefresher::CRemote::CEnumRequest>::release(void)
0x18008863d  mov     [r14], rax
0x180088640  lea     rcx, [rsp+78h+arg_28]
0x180088648  call    ??1?$unique_ptr@VCHiPerfProviderRecord@@U?$default_delete@VCHiPerfProviderRecord@@@std@@@std@@QEAA@XZ; std::unique_ptr<CHiPerfProviderRecord>::~unique_ptr<CHiPerfProviderRecord>(void)
0x18008864d  xor     ebx, ebx
0x18008864f  lea     rcx, [rsp+78h+var_48]
0x180088654  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x18008865a  mov     eax, ebx
0x18008865c  add     rsp, 40h
0x180088660  pop     r15
0x180088662  pop     r14
0x180088664  pop     r12
0x180088666  pop     rdi
0x180088667  pop     rsi
0x180088668  pop     rbp
0x180088669  pop     rbx
0x18008866a  retn
```
