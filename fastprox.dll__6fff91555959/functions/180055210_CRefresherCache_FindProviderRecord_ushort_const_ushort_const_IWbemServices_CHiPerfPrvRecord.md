# CRefresherCache::FindProviderRecord(ushort const *,ushort const *,IWbemServices *,CHiPerfPrvRecord * *)

- ea: `0x180055210`
- end: `0x1800555ca`
- name: `?FindProviderRecord@CRefresherCache@@QEAAJPEBG0PEAUIWbemServices@@PEAPEAVCHiPerfPrvRecord@@@Z`
- size: `954`
- prototype: `int(CRefresherCache *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct IWbemServices *, struct CHiPerfPrvRecord **)`
- caller_count: `2`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180054c00`
- `0x180054e80`

## callees

- `0x180037120`
- `0x180055210`
- `0x1800555d0`
- `0x1800700c8`
- `0x18007212c`
- `0x180084f90`
- `0x180091966`
- `0x1800919b0`

## import_xrefs

- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x1800553cb`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x1800554bc`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x1800553cb`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x1800554bc`
- `wbemcomn!GetMemLogObject` at `0x180055357`
- `wbemcomn!GetMemLogObject` at `0x180055465`
- `wbemcomn!GetMemLogObject` at `0x18005551a`
- `wbemcomn!GetMemLogObject` at `0x18005558c`
- `wbemcomn!GetMemLogObject` at `0x180055357`
- `wbemcomn!GetMemLogObject` at `0x180055465`
- `wbemcomn!GetMemLogObject` at `0x18005551a`
- `wbemcomn!GetMemLogObject` at `0x18005558c`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x1800552ac`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x1800553fe`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x1800552ac`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x1800553fe`
- `wbemcomn!?Add@CFlexArray@@QEAAHPEAX@Z` at `0x1800553ed`
- `wbemcomn!?Add@CFlexArray@@QEAAHPEAX@Z` at `0x1800553ed`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180055394`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x1800553dd`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180055451`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18005557b`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180055394`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x1800553dd`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180055451`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18005557b`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x180055291`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x180055291`
- `wbemcomn!?AddRef@CUnk@@UEAAKXZ` at `0x180055334`
- `wbemcomn!?AddRef@CUnk@@UEAAKXZ` at `0x180055334`
- `wbemcomn!??0WString@@QEAA@PEBG@Z` at `0x180055317`
- `wbemcomn!??0WString@@QEAA@PEBG@Z` at `0x180055317`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180055367`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180055475`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005552a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180055597`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180055367`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180055475`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005552a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180055597`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800552de`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800552de`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall CRefresherCache::FindProviderRecord(
        CRefresherCache *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct IWbemServices *a4,
        struct CHiPerfPrvRecord **a5)
{
  unsigned int ProviderInfo; // ebx
  int i; // ebx
  char *v9; // rbx
  struct _GUID v10; // xmm7
  struct _GUID v11; // xmm6
  CHiPerfPrvRecord *v12; // rbx
  CMemoryLog *v13; // rax
  volatile signed __int32 *v15; // rax
  CMemoryLog *MemLogObject; // rax
  _QWORD *v17; // rax
  __int64 v18; // rcx
  CMemoryLog *v19; // rax
  CMemoryLog *v20; // rax
  CHiPerfPrvRecord *v21; // [rsp+30h] [rbp-98h] BYREF
  int v22; // [rsp+38h] [rbp-90h]
  _BYTE v23[16]; // [rsp+40h] [rbp-88h] BYREF
  struct _GUID v24; // [rsp+50h] [rbp-78h] BYREF
  struct _GUID Buf2; // [rsp+60h] [rbp-68h] BYREF

  if ( !a5 )
  {
    MemLogObject = GetMemLogObject();
    ProviderInfo = -2147217400;
    CMemoryLog::Write(MemLogObject, -2147217400);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_583a410948f0357245c15279aca1a26e_Traceguids, 2147749896LL);
    }
    return ProviderInfo;
  }
  *a5 = 0;
  v24 = 0;
  Buf2 = 0;
  ProviderInfo = CRefresherCache::GetProviderInfo((CRefresherCache *)&Buf2, a4, a2, &v24, &Buf2);
  CInCritSec::CInCritSec((CInCritSec *)v23, (struct _RTL_CRITICAL_SECTION *)((char *)this + 232));
  if ( (ProviderInfo & 0x80000000) != 0 )
  {
    v20 = GetMemLogObject();
    CMemoryLog::Write(v20, ProviderInfo);
LABEL_17:
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_583a410948f0357245c15279aca1a26e_Traceguids, ProviderInfo);
    }
    CInCritSec::~CInCritSec((CInCritSec *)v23);
    return ProviderInfo;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= CFlexArray::Size((CRefresherCache *)((char *)this + 136)) )
    {
      if ( !memcmp_0(&GUID_NULL, &Buf2, 0x10u) )
        goto LABEL_13;
      v9 = (char *)CWin32DefaultArena::WbemMemAlloc(0x40u);
      v21 = (CHiPerfPrvRecord *)v9;
      if ( v9 )
      {
        v10 = Buf2;
        v11 = v24;
        *(_QWORD *)v9 = &CHiPerfPrvRecord::`vftable';
        *((_DWORD *)v9 + 2) = 0;
        WString::WString((WString *)(v9 + 16), a2);
        *(struct _GUID *)(v9 + 24) = v11;
        *(struct _GUID *)(v9 + 40) = v10;
        *((_QWORD *)v9 + 7) = this;
        if ( this )
          CUnk::AddRef(this);
      }
      else
      {
        v9 = 0;
      }
      std::unique_ptr<CClassInfo>::unique_ptr<CClassInfo>(&v21, (__int64)v9);
      v12 = v21;
      if ( !v21 )
      {
        v13 = GetMemLogObject();
        CMemoryLog::Write(v13, -2147217402);
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            30,
            WPP_583a410948f0357245c15279aca1a26e_Traceguids,
            2147749894LL);
        }
LABEL_11:
        std::unique_ptr<CHiPerfPrvRecord>::~unique_ptr<CHiPerfPrvRecord>(&v21);
        CInCritSec::~CInCritSec((CInCritSec *)v23);
        return 2147749894LL;
      }
      if ( CFlexArray::Add((CRefresherCache *)((char *)this + 136), v21)
        || CFlexArray::Size((CRefresherCache *)((char *)this + 136)) - 1 < 0 )
      {
        v19 = GetMemLogObject();
        CMemoryLog::Write(v19, -2147217402);
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            31,
            WPP_583a410948f0357245c15279aca1a26e_Traceguids,
            2147749894LL);
        }
        goto LABEL_11;
      }
      _InterlockedIncrement((volatile signed __int32 *)v12 + 2);
      *a5 = (struct CHiPerfPrvRecord *)std::unique_ptr<CUniversalRefresher::CRemote::CEnumRequest>::release(&v21);
      ProviderInfo = 0;
      v22 = 0;
      std::unique_ptr<CHiPerfPrvRecord>::~unique_ptr<CHiPerfPrvRecord>(&v21);
      goto LABEL_17;
    }
    v17 = CFlexArray::GetAt((CRefresherCache *)((char *)this + 136), i);
    v18 = v17[3] - *(_QWORD *)&v24.Data1;
    if ( !v18 )
      v18 = v17[4] - *(_QWORD *)v24.Data4;
    if ( !v18 )
      break;
  }
  v15 = (volatile signed __int32 *)CFlexArray::GetAt((CRefresherCache *)((char *)this + 136), i);
  *a5 = (struct CHiPerfPrvRecord *)v15;
  _InterlockedIncrement(v15 + 2);
LABEL_13:
  CInCritSec::~CInCritSec((CInCritSec *)v23);
  return 0;
}

```

## disassembly

```asm
0x180055210  mov     rax, rsp
0x180055213  push    rbx
0x180055214  push    rsi
0x180055215  push    rdi
0x180055216  push    r14
0x180055218  push    r15
0x18005521a  sub     rsp, 0A0h
0x180055221  movaps  xmmword ptr [rax-38h], xmm6
0x180055225  movaps  xmmword ptr [rax-48h], xmm7
0x180055229  mov     rax, cs:__security_cookie
0x180055230  xor     rax, rsp
0x180055233  mov     [rsp+0C8h+var_58], rax
0x180055238  mov     rax, r9
0x18005523b  mov     r15, rdx
0x18005523e  mov     rsi, rcx
0x180055241  mov     r14, [rsp+0C8h+arg_20]
0x180055249  test    r14, r14
0x18005524c  jz      loc_180055465
0x180055252  mov     qword ptr [r14], 0
0x180055259  xorps   xmm0, xmm0
0x18005525c  movups  xmmword ptr [rsp+0C8h+var_78.Data1], xmm0
0x180055261  xorps   xmm1, xmm1
0x180055264  movups  [rsp+0C8h+Buf2], xmm1
0x180055269  lea     rcx, [rsp+0C8h+Buf2]; this
0x18005526e  mov     [rsp+0C8h+var_A8], rcx; struct _GUID *
0x180055273  lea     r9, [rsp+0C8h+var_78]; struct _GUID *
0x180055278  mov     r8, rdx; unsigned __int16 *
0x18005527b  mov     rdx, rax; struct IWbemServices *
0x18005527e  call    ?GetProviderInfo@CRefresherCache@@QEAAJPEAUIWbemServices@@PEBGAEAU_GUID@@2@Z; CRefresherCache::GetProviderInfo(IWbemServices *,ushort const *,_GUID &,_GUID &)
0x180055283  mov     ebx, eax
0x180055285  lea     rdx, [rsi+0E8h]
0x18005528c  lea     rcx, [rsp+0C8h+var_88]
0x180055291  call    cs:__imp_??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x180055297  nop
0x180055298  test    ebx, ebx
0x18005529a  js      loc_18005558C
0x1800552a0  xor     ebx, ebx
0x1800552a2  lea     rdi, [rsi+88h]
0x1800552a9  mov     rcx, rdi
0x1800552ac  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x1800552b2  cmp     ebx, eax
0x1800552b4  jl      loc_1800554B7
0x1800552ba  mov     r8d, 10h; Size
0x1800552c0  lea     rdx, [rsp+0C8h+Buf2]; Buf2
0x1800552c5  lea     rcx, GUID_NULL; Buf1
0x1800552cc  call    memcmp_0
0x1800552d1  test    eax, eax
0x1800552d3  jz      loc_1800553D8
0x1800552d9  mov     ecx, 40h ; '@'
0x1800552de  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800552e4  mov     rbx, rax
0x1800552e7  mov     [rsp+0C8h+var_98], rax
0x1800552ec  test    rax, rax
0x1800552ef  jz      loc_18005545E
0x1800552f5  movaps  xmm7, [rsp+0C8h+Buf2]
0x1800552fa  movaps  xmm6, xmmword ptr [rsp+0C8h+var_78.Data1]
0x1800552ff  lea     rax, ??_7CHiPerfPrvRecord@@6B@; const CHiPerfPrvRecord::`vftable'
0x180055306  mov     [rbx], rax
0x180055309  mov     dword ptr [rbx+8], 0
0x180055310  lea     rcx, [rbx+10h]
0x180055314  mov     rdx, r15
0x180055317  call    cs:__imp_??0WString@@QEAA@PEBG@Z; WString::WString(ushort const *)
0x18005531d  nop
0x18005531e  movdqu  xmmword ptr [rbx+18h], xmm6
0x180055323  movdqu  xmmword ptr [rbx+28h], xmm7
0x180055328  mov     [rbx+38h], rsi
0x18005532c  test    rsi, rsi
0x18005532f  jz      short loc_18005533B
0x180055331  mov     rcx, rsi
0x180055334  call    cs:__imp_?AddRef@CUnk@@UEAAKXZ; CUnk::AddRef(void)
0x18005533a  nop
0x18005533b  mov     rdx, rbx
0x18005533e  lea     rcx, [rsp+0C8h+var_98]
0x180055343  call    ??0?$unique_ptr@UCClassInfo@@U?$default_delete@UCClassInfo@@@std@@@std@@QEAA@PEAUCClassInfo@@@Z; std::unique_ptr<CClassInfo>::unique_ptr<CClassInfo>(CClassInfo *)
0x180055348  nop
0x180055349  mov     rbx, [rsp+0C8h+var_98]
0x18005534e  test    rbx, rbx
0x180055351  jnz     loc_1800553E7
0x180055357  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18005535d  mov     ebx, 80041006h
0x180055362  mov     edx, ebx
0x180055364  mov     rcx, rax
0x180055367  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18005536d  lea     rax, WPP_GLOBAL_Control
0x180055374  mov     rcx, cs:WPP_GLOBAL_Control
0x18005537b  cmp     rcx, rax
0x18005537e  jnz     loc_1800554E6
0x180055384  lea     rcx, [rsp+0C8h+var_98]
0x180055389  call    ??1?$unique_ptr@VCHiPerfPrvRecord@@U?$default_delete@VCHiPerfPrvRecord@@@std@@@std@@QEAA@XZ; std::unique_ptr<CHiPerfPrvRecord>::~unique_ptr<CHiPerfPrvRecord>(void)
0x18005538e  nop
0x18005538f  lea     rcx, [rsp+0C8h+var_88]
0x180055394  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x18005539a  mov     eax, ebx
0x18005539c  mov     rcx, [rsp+0C8h+var_58]
0x1800553a1  xor     rcx, rsp; StackCookie
0x1800553a4  call    __security_check_cookie
0x1800553a9  lea     r11, [rsp+0C8h+var_28]
0x1800553b1  movaps  xmm6, xmmword ptr [r11-10h]
0x1800553b6  movaps  xmm7, xmmword ptr [r11-20h]
0x1800553bb  mov     rsp, r11
0x1800553be  pop     r15
0x1800553c0  pop     r14
0x1800553c2  pop     rdi
0x1800553c3  pop     rsi
0x1800553c4  pop     rbx
0x1800553c5  retn
0x1800553c6  mov     edx, ebx
0x1800553c8  mov     rcx, rdi
0x1800553cb  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x1800553d1  mov     [r14], rax
0x1800553d4  lock inc dword ptr [rax+8]
0x1800553d8  lea     rcx, [rsp+0C8h+var_88]
0x1800553dd  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x1800553e3  xor     eax, eax
0x1800553e5  jmp     short loc_18005539C
0x1800553e7  mov     rdx, rbx
0x1800553ea  mov     rcx, rdi
0x1800553ed  call    cs:__imp_?Add@CFlexArray@@QEAAHPEAX@Z; CFlexArray::Add(void *)
0x1800553f3  test    eax, eax
0x1800553f5  jnz     loc_18005551A
0x1800553fb  mov     rcx, rdi
0x1800553fe  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x180055404  cmp     eax, 1
0x180055407  js      loc_18005551A
0x18005540d  lock inc dword ptr [rbx+8]
0x180055411  lea     rcx, [rsp+0C8h+var_98]
0x180055416  call    ?release@?$unique_ptr@VCEnumRequest@CRemote@CUniversalRefresher@@U?$default_delete@VCEnumRequest@CRemote@CUniversalRefresher@@@std@@@std@@QEAAPEAVCEnumRequest@CRemote@CUniversalRefresher@@XZ; std::unique_ptr<CUniversalRefresher::CRemote::CEnumRequest>::release(void)
0x18005541b  mov     [r14], rax
0x18005541e  xor     ebx, ebx
0x180055420  mov     [rsp+0C8h+var_90], ebx
0x180055424  lea     rcx, [rsp+0C8h+var_98]
0x180055429  call    ??1?$unique_ptr@VCHiPerfPrvRecord@@U?$default_delete@VCHiPerfPrvRecord@@@std@@@std@@QEAA@XZ; std::unique_ptr<CHiPerfPrvRecord>::~unique_ptr<CHiPerfPrvRecord>(void)
0x18005542e  nop
0x18005542f  lea     rax, WPP_GLOBAL_Control
0x180055436  mov     rcx, cs:WPP_GLOBAL_Control
0x18005543d  cmp     rcx, rax
0x180055440  jz      short loc_18005544C
0x180055442  test    byte ptr [rcx+1Ch], 1
0x180055446  jnz     loc_1800555A2
0x18005544c  lea     rcx, [rsp+0C8h+var_88]
0x180055451  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x180055457  mov     eax, ebx
0x180055459  jmp     loc_18005539C
0x18005545e  xor     ebx, ebx
0x180055460  jmp     loc_18005533B
0x180055465  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18005546b  mov     ebx, 80041008h
0x180055470  mov     edx, ebx
0x180055472  mov     rcx, rax
0x180055475  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18005547b  lea     rax, WPP_GLOBAL_Control
0x180055482  mov     rcx, cs:WPP_GLOBAL_Control
0x180055489  cmp     rcx, rax
0x18005548c  jz      short loc_180055457
0x18005548e  test    byte ptr [rcx+1Ch], 1
0x180055492  jz      short loc_180055457
0x180055494  cmp     byte ptr [rcx+19h], 2
0x180055498  jb      short loc_180055457
0x18005549a  mov     edx, 1Dh
0x18005549f  mov     r9d, 80041008h
0x1800554a5  lea     r8, WPP_583a410948f0357245c15279aca1a26e_Traceguids
0x1800554ac  mov     rcx, [rcx+10h]
0x1800554b0  call    WPP_SF_d
0x1800554b5  jmp     short loc_180055457
0x1800554b7  mov     edx, ebx
0x1800554b9  mov     rcx, rdi
0x1800554bc  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x1800554c2  mov     rcx, [rax+18h]
0x1800554c6  sub     rcx, qword ptr [rsp+0C8h+var_78.Data1]
0x1800554cb  jnz     short loc_1800554D6
0x1800554cd  mov     rcx, [rax+20h]
0x1800554d1  sub     rcx, qword ptr [rsp+0C8h+var_78.Data4]
0x1800554d6  test    rcx, rcx
0x1800554d9  jz      loc_1800553C6
0x1800554df  inc     ebx
0x1800554e1  jmp     loc_1800552A9
0x1800554e6  test    byte ptr [rcx+1Ch], 1
0x1800554ea  jz      loc_180055384
0x1800554f0  cmp     byte ptr [rcx+19h], 2
0x1800554f4  jb      loc_180055384
0x1800554fa  mov     edx, 1Eh
0x1800554ff  mov     r9d, 80041006h
0x180055505  lea     r8, WPP_583a410948f0357245c15279aca1a26e_Traceguids
0x18005550c  mov     rcx, [rcx+10h]
0x180055510  call    WPP_SF_d
0x180055515  jmp     loc_180055384
0x18005551a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180055520  mov     ebx, 80041006h
0x180055525  mov     edx, ebx
0x180055527  mov     rcx, rax
0x18005552a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180055530  lea     rax, WPP_GLOBAL_Control
0x180055537  mov     rcx, cs:WPP_GLOBAL_Control
0x18005553e  cmp     rcx, rax
0x180055541  jz      short loc_18005556B
0x180055543  test    byte ptr [rcx+1Ch], 1
0x180055547  jz      short loc_18005556B
0x180055549  cmp     byte ptr [rcx+19h], 2
0x18005554d  jb      short loc_18005556B
0x18005554f  mov     edx, 1Fh
0x180055554  mov     r9d, 80041006h
0x18005555a  lea     r8, WPP_583a410948f0357245c15279aca1a26e_Traceguids
0x180055561  mov     rcx, [rcx+10h]
0x180055565  call    WPP_SF_d
0x18005556a  nop
0x18005556b  lea     rcx, [rsp+0C8h+var_98]
0x180055570  call    ??1?$unique_ptr@VCHiPerfPrvRecord@@U?$default_delete@VCHiPerfPrvRecord@@@std@@@std@@QEAA@XZ; std::unique_ptr<CHiPerfPrvRecord>::~unique_ptr<CHiPerfPrvRecord>(void)
0x180055575  nop
0x180055576  lea     rcx, [rsp+0C8h+var_88]
0x18005557b  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x180055581  mov     eax, ebx
0x180055583  jmp     loc_18005539C
0x180055588  mov     ebx, [rsp+0C8h+var_90]
0x18005558c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180055592  mov     edx, ebx
0x180055594  mov     rcx, rax
0x180055597  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18005559d  jmp     loc_18005542F
0x1800555a2  cmp     byte ptr [rcx+19h], 2
0x1800555a6  jb      loc_18005544C
0x1800555ac  mov     edx, 20h ; ' '
0x1800555b1  mov     r9d, ebx
0x1800555b4  lea     r8, WPP_583a410948f0357245c15279aca1a26e_Traceguids
0x1800555bb  mov     rcx, [rcx+10h]
0x1800555bf  call    WPP_SF_d
0x1800555c4  jmp     loc_18005544C
```
