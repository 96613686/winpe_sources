# CRefresherRecord::AddProvider(CHiPerfPrvRecord *,IWbemHiPerfProvider *,IWbemRefresher *,_IWmiProviderStack *,CProviderRecord * *)

- ea: `0x18008b5d8`
- end: `0x18008b7b3`
- name: `?AddProvider@CRefresherRecord@@QEAAJPEAVCHiPerfPrvRecord@@PEAUIWbemHiPerfProvider@@PEAUIWbemRefresher@@PEAU_IWmiProviderStack@@PEAPEAVCProviderRecord@@@Z`
- size: `475`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this, struct CHiPerfPrvRecord *, struct IWbemHiPerfProvider *, struct IWbemRefresher *, struct _IWmiProviderStack *, struct CProviderRecord **)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18008acf0`
- `0x18008b190`

## callees

- `0x180037120`
- `0x1800700c8`
- `0x18007212c`
- `0x18008a65c`
- `0x18008a984`
- `0x18008b5d8`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18008b5fc`
- `wbemcomn!GetMemLogObject` at `0x18008b6c3`
- `wbemcomn!GetMemLogObject` at `0x18008b73c`
- `wbemcomn!GetMemLogObject` at `0x18008b5fc`
- `wbemcomn!GetMemLogObject` at `0x18008b6c3`
- `wbemcomn!GetMemLogObject` at `0x18008b73c`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x18008b71d`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x18008b71d`
- `wbemcomn!?Add@CFlexArray@@QEAAHPEAX@Z` at `0x18008b70f`
- `wbemcomn!?Add@CFlexArray@@QEAAHPEAX@Z` at `0x18008b70f`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18008b7a0`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18008b7a0`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18008b667`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18008b667`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008b60c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008b6d3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008b74c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008b60c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008b6d3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008b74c`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18008b673`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18008b673`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRefresherRecord::AddProvider(
        struct _RTL_CRITICAL_SECTION *this,
        struct CHiPerfPrvRecord *a2,
        struct IWbemHiPerfProvider *a3,
        struct IWbemRefresher *a4,
        struct _IWmiProviderStack *a5,
        struct CProviderRecord **a6)
{
  struct CProviderRecord **v10; // rdi
  CMemoryLog *v11; // rax
  unsigned int v12; // ebx
  struct CProviderRecord **v13; // rax
  CMemoryLog *v14; // rax
  CWbemRefreshingSvc *v15; // rcx
  __int64 v16; // rdx
  CMemoryLog *MemLogObject; // rax
  _BYTE v19[56]; // [rsp+30h] [rbp-38h] BYREF

  v10 = a6;
  if ( a6 )
  {
    CInCritSec::CInCritSec((CInCritSec *)v19, this + 5);
    v13 = (struct CProviderRecord **)CWin32DefaultArena::WbemMemAlloc(0x118u);
    a6 = v13;
    if ( v13 )
      v13 = (struct CProviderRecord **)CProviderRecord::CProviderRecord((CProviderRecord *)v13, a2, a3, a4, a5);
    std::unique_ptr<CClassInfo>::unique_ptr<CClassInfo>(&a6, (__int64)v13);
    if ( a6 )
    {
      if ( !CFlexArray::Add((CFlexArray *)&this[1].OwningThread, a6)
        && CFlexArray::Size((CFlexArray *)&this[1].OwningThread) - 1 >= 0 )
      {
        *v10 = (struct CProviderRecord *)std::unique_ptr<CUniversalRefresher::CRemote::CEnumRequest>::release(&a6);
        v12 = 0;
LABEL_21:
        std::unique_ptr<CProviderRecord>::~unique_ptr<CProviderRecord>((CProviderRecord **)&a6);
        CInCritSec::~CInCritSec((CInCritSec *)v19);
        return v12;
      }
      MemLogObject = GetMemLogObject();
      v12 = -2147217402;
      CMemoryLog::Write(MemLogObject, -2147217402);
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_21;
      }
      v16 = 20;
    }
    else
    {
      v14 = GetMemLogObject();
      v12 = -2147217402;
      CMemoryLog::Write(v14, -2147217402);
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_21;
      }
      v16 = 19;
    }
    WPP_SF_d(*((_QWORD *)v15 + 2), v16, WPP_03c64eaa4d8c32ecfb51fbe2c30fec97_Traceguids, 2147749894LL);
    goto LABEL_21;
  }
  v11 = GetMemLogObject();
  v12 = -2147217400;
  CMemoryLog::Write(v11, -2147217400);
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_03c64eaa4d8c32ecfb51fbe2c30fec97_Traceguids, 2147749896LL);
  }
  return v12;
}

```

## disassembly

```asm
0x18008b5d8  push    rbx
0x18008b5da  push    rbp
0x18008b5db  push    rsi
0x18008b5dc  push    rdi
0x18008b5dd  push    r14
0x18008b5df  sub     rsp, 40h
0x18008b5e3  mov     rsi, r9
0x18008b5e6  mov     rbp, r8
0x18008b5e9  mov     r14, rdx
0x18008b5ec  mov     rbx, rcx
0x18008b5ef  mov     rdi, [rsp+68h+arg_28]
0x18008b5f7  test    rdi, rdi
0x18008b5fa  jnz     short loc_18008B65B
0x18008b5fc  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18008b602  mov     ebx, 80041008h
0x18008b607  mov     edx, ebx
0x18008b609  mov     rcx, rax
0x18008b60c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18008b612  lea     rax, WPP_GLOBAL_Control
0x18008b619  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b620  cmp     rcx, rax
0x18008b623  jz      loc_18008B7A6
0x18008b629  test    byte ptr [rcx+1Ch], 1
0x18008b62d  jz      loc_18008B7A6
0x18008b633  cmp     byte ptr [rcx+19h], 2
0x18008b637  jb      loc_18008B7A6
0x18008b63d  lea     edx, [rdi+12h]
0x18008b640  mov     r9d, 80041008h
0x18008b646  lea     r8, WPP_03c64eaa4d8c32ecfb51fbe2c30fec97_Traceguids
0x18008b64d  mov     rcx, [rcx+10h]
0x18008b651  call    WPP_SF_d
0x18008b656  jmp     loc_18008B7A6
0x18008b65b  lea     rdx, [rcx+0C8h]
0x18008b662  lea     rcx, [rsp+68h+var_38]
0x18008b667  call    cs:__imp_??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x18008b66d  nop
0x18008b66e  mov     ecx, 118h
0x18008b673  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18008b679  mov     [rsp+68h+arg_28], rax
0x18008b681  test    rax, rax
0x18008b684  jz      short loc_18008B6A5
0x18008b686  mov     rcx, [rsp+68h+arg_20]
0x18008b68e  mov     [rsp+68h+var_48], rcx; struct _IWmiProviderStack *
0x18008b693  mov     r9, rsi; struct IWbemRefresher *
0x18008b696  mov     r8, rbp; struct IWbemHiPerfProvider *
0x18008b699  mov     rdx, r14; struct CHiPerfPrvRecord *
0x18008b69c  mov     rcx, rax; this
0x18008b69f  call    ??0CProviderRecord@@QEAA@PEAVCHiPerfPrvRecord@@PEAUIWbemHiPerfProvider@@PEAUIWbemRefresher@@PEAU_IWmiProviderStack@@@Z; CProviderRecord::CProviderRecord(CHiPerfPrvRecord *,IWbemHiPerfProvider *,IWbemRefresher *,_IWmiProviderStack *)
0x18008b6a4  nop
0x18008b6a5  mov     rdx, rax
0x18008b6a8  lea     rcx, [rsp+68h+arg_28]
0x18008b6b0  call    ??0?$unique_ptr@UCClassInfo@@U?$default_delete@UCClassInfo@@@std@@@std@@QEAA@PEAUCClassInfo@@@Z; std::unique_ptr<CClassInfo>::unique_ptr<CClassInfo>(CClassInfo *)
0x18008b6b5  nop
0x18008b6b6  mov     rdx, [rsp+68h+arg_28]
0x18008b6be  test    rdx, rdx
0x18008b6c1  jnz     short loc_18008B70B
0x18008b6c3  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18008b6c9  mov     ebx, 80041006h
0x18008b6ce  mov     edx, ebx
0x18008b6d0  mov     rcx, rax
0x18008b6d3  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18008b6d9  lea     rax, WPP_GLOBAL_Control
0x18008b6e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b6e7  cmp     rcx, rax
0x18008b6ea  jz      loc_18008B78D
0x18008b6f0  test    byte ptr [rcx+1Ch], 1
0x18008b6f4  jz      loc_18008B78D
0x18008b6fa  cmp     byte ptr [rcx+19h], 2
0x18008b6fe  jb      loc_18008B78D
0x18008b704  mov     edx, 13h
0x18008b709  jmp     short loc_18008B776
0x18008b70b  lea     rcx, [rbx+38h]
0x18008b70f  call    cs:__imp_?Add@CFlexArray@@QEAAHPEAX@Z; CFlexArray::Add(void *)
0x18008b715  test    eax, eax
0x18008b717  jnz     short loc_18008B73C
0x18008b719  lea     rcx, [rbx+38h]
0x18008b71d  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x18008b723  cmp     eax, 1
0x18008b726  js      short loc_18008B73C
0x18008b728  lea     rcx, [rsp+68h+arg_28]
0x18008b730  call    ?release@?$unique_ptr@VCEnumRequest@CRemote@CUniversalRefresher@@U?$default_delete@VCEnumRequest@CRemote@CUniversalRefresher@@@std@@@std@@QEAAPEAVCEnumRequest@CRemote@CUniversalRefresher@@XZ; std::unique_ptr<CUniversalRefresher::CRemote::CEnumRequest>::release(void)
0x18008b735  mov     [rdi], rax
0x18008b738  xor     ebx, ebx
0x18008b73a  jmp     short loc_18008B78D
0x18008b73c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18008b742  mov     ebx, 80041006h
0x18008b747  mov     edx, ebx
0x18008b749  mov     rcx, rax
0x18008b74c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18008b752  lea     rax, WPP_GLOBAL_Control
0x18008b759  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b760  cmp     rcx, rax
0x18008b763  jz      short loc_18008B78D
0x18008b765  test    byte ptr [rcx+1Ch], 1
0x18008b769  jz      short loc_18008B78D
0x18008b76b  cmp     byte ptr [rcx+19h], 2
0x18008b76f  jb      short loc_18008B78D
0x18008b771  mov     edx, 14h
0x18008b776  mov     r9d, 80041006h
0x18008b77c  lea     r8, WPP_03c64eaa4d8c32ecfb51fbe2c30fec97_Traceguids
0x18008b783  mov     rcx, [rcx+10h]
0x18008b787  call    WPP_SF_d
0x18008b78c  nop
0x18008b78d  lea     rcx, [rsp+68h+arg_28]
0x18008b795  call    ??1?$unique_ptr@VCProviderRecord@@U?$default_delete@VCProviderRecord@@@std@@@std@@QEAA@XZ; std::unique_ptr<CProviderRecord>::~unique_ptr<CProviderRecord>(void)
0x18008b79a  nop
0x18008b79b  lea     rcx, [rsp+68h+var_38]
0x18008b7a0  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x18008b7a6  mov     eax, ebx
0x18008b7a8  add     rsp, 40h
0x18008b7ac  pop     r14
0x18008b7ae  pop     rdi
0x18008b7af  pop     rsi
0x18008b7b0  pop     rbp
0x18008b7b1  pop     rbx
0x18008b7b2  retn
```
