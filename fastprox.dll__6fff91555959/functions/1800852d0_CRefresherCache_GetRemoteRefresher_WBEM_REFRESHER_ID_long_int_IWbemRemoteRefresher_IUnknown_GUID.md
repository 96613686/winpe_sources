# CRefresherCache::GetRemoteRefresher(_WBEM_REFRESHER_ID *,long,int,IWbemRemoteRefresher * *,IUnknown *,_GUID *)

- ea: `0x1800852d0`
- end: `0x18008551a`
- name: `?GetRemoteRefresher@CRefresherCache@@MEAAJPEAU_WBEM_REFRESHER_ID@@JHPEAPEAUIWbemRemoteRefresher@@PEAUIUnknown@@PEAU_GUID@@@Z`
- size: `586`
- prototype: `int(CRefresherCache *__hidden this, struct _WBEM_REFRESHER_ID *, int, int, struct IWbemRemoteRefresher **, struct IUnknown *, struct _GUID *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180085520`

## callees

- `0x180037120`
- `0x180072230`
- `0x180084fdc`
- `0x1800852d0`
- `0x18008f600`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x1800853c2`
- `wbemcomn!GetMemLogObject` at `0x18008546e`
- `wbemcomn!GetMemLogObject` at `0x1800854b8`
- `wbemcomn!GetMemLogObject` at `0x1800853c2`
- `wbemcomn!GetMemLogObject` at `0x18008546e`
- `wbemcomn!GetMemLogObject` at `0x1800854b8`
- `wbemcomn!??1CNtSid@@QEAA@XZ` at `0x180085386`
- `wbemcomn!??1CNtSid@@QEAA@XZ` at `0x180085434`
- `wbemcomn!??1CNtSid@@QEAA@XZ` at `0x180085386`
- `wbemcomn!??1CNtSid@@QEAA@XZ` at `0x180085434`
- `wbemcomn!??0CNtSid@@QEAA@XZ` at `0x180085338`
- `wbemcomn!??0CNtSid@@QEAA@XZ` at `0x180085338`
- `wbemcomn!??8CNtSid@@QEAAHAEAV0@@Z` at `0x180085360`
- `wbemcomn!??8CNtSid@@QEAAHAEAV0@@Z` at `0x180085373`
- `wbemcomn!??8CNtSid@@QEAAHAEAV0@@Z` at `0x180085360`
- `wbemcomn!??8CNtSid@@QEAAHAEAV0@@Z` at `0x180085373`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800853cd`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008547e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800854c8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800853cd`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008547e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800854c8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CRefresherCache::GetRemoteRefresher(
        CRefresherCache *this,
        struct _WBEM_REFRESHER_ID *a2,
        __int64 a3,
        int a4,
        struct IWbemRemoteRefresher **a5,
        struct IUnknown *a6,
        struct _GUID *a7)
{
  int RefresherRecord; // esi
  struct CRefresherRecord *v8; // rbx
  CIdentitySec *v9; // rcx
  CMemoryLog *v10; // rax
  CWbemRefreshingSvc *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v16; // rax
  _BYTE v17[32]; // [rsp+38h] [rbp-20h] BYREF
  struct CRefresherRecord *v18; // [rsp+68h] [rbp+10h] BYREF

  if ( a2 && *(_QWORD *)a2 )
  {
    v18 = 0;
    RefresherRecord = CRefresherCache::FindRefresherRecord(this, a2, a4, a6, &v18);
    v8 = v18;
    if ( RefresherRecord < 0 )
      goto LABEL_9;
    if ( v18 )
    {
      CNtSid::CNtSid((CNtSid *)v17);
      if ( CIdentitySec::RetrieveSidFromCall(v9, (struct CNtSid *)v17) < 0
        || !(unsigned int)CNtSid::operator==(v17, (char *)v8 + 240)
        && !(unsigned int)CNtSid::operator==(v17, (char *)v8 + 256) )
      {
        CNtSid::~CNtSid((CNtSid *)v17);
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_583a410948f0357245c15279aca1a26e_Traceguids);
        }
        MemLogObject = GetMemLogObject();
        RefresherRecord = -2147217405;
        CMemoryLog::Write(MemLogObject, -2147217405);
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_15;
        }
        v12 = 16;
        v13 = 2147749891LL;
        goto LABEL_14;
      }
      CNtSid::~CNtSid((CNtSid *)v17);
      RefresherRecord = (**(__int64 (__fastcall ***)(struct CRefresherRecord *, GUID *, struct IWbemRemoteRefresher **))v8)(
                          v8,
                          &IID_IWbemRemoteRefresher,
                          a5);
      *a7 = *(struct _GUID *)((char *)v8 + 164);
      if ( RefresherRecord < 0 )
      {
LABEL_9:
        v10 = GetMemLogObject();
        CMemoryLog::Write(v10, RefresherRecord);
      }
    }
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
LABEL_15:
      if ( v8 )
        (*(void (__fastcall **)(struct CRefresherRecord *))(*(_QWORD *)v8 + 16LL))(v8);
      return (unsigned int)RefresherRecord;
    }
    v12 = 17;
    v13 = (unsigned int)RefresherRecord;
LABEL_14:
    WPP_SF_d(*((_QWORD *)v11 + 2), v12, WPP_583a410948f0357245c15279aca1a26e_Traceguids, v13);
    goto LABEL_15;
  }
  v16 = GetMemLogObject();
  CMemoryLog::Write(v16, -2147217400);
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_583a410948f0357245c15279aca1a26e_Traceguids, 2147749896LL);
  }
  return 2147749896LL;
}

```

## disassembly

```asm
0x1800852d0  mov     r11, rsp
0x1800852d3  mov     [r11+8], rbx
0x1800852d7  mov     [r11+18h], rsi
0x1800852db  push    rdi
0x1800852dc  sub     rsp, 50h
0x1800852e0  mov     eax, r9d
0x1800852e3  test    rdx, rdx
0x1800852e6  jz      loc_1800854B8
0x1800852ec  cmp     qword ptr [rdx], 0
0x1800852f0  jz      loc_1800854B8
0x1800852f6  mov     qword ptr [r11+10h], 0
0x1800852fe  lea     r8, [r11+10h]
0x180085302  mov     [r11-38h], r8
0x180085306  mov     r9, [rsp+58h+arg_28]; struct IUnknown *
0x18008530e  mov     r8d, eax; int
0x180085311  call    ?FindRefresherRecord@CRefresherCache@@QEAAJPEAVCRefresherId@@HPEAUIUnknown@@PEAPEAVCRefresherRecord@@@Z; CRefresherCache::FindRefresherRecord(CRefresherId *,int,IUnknown *,CRefresherRecord * *)
0x180085316  mov     esi, eax
0x180085318  mov     rbx, [rsp+58h+arg_8]
0x18008531d  mov     [rsp+58h+var_28], rbx
0x180085322  test    eax, eax
0x180085324  js      loc_1800853C2
0x18008532a  test    rbx, rbx
0x18008532d  jz      loc_1800853D3
0x180085333  lea     rcx, [rsp+58h+var_20]
0x180085338  call    cs:__imp_??0CNtSid@@QEAA@XZ; CNtSid::CNtSid(void)
0x18008533e  nop
0x18008533f  lea     rdx, [rsp+58h+var_20]; struct CNtSid *
0x180085344  call    ?RetrieveSidFromCall@CIdentitySec@@AEAAJAEAVCNtSid@@@Z; CIdentitySec::RetrieveSidFromCall(CNtSid &)
0x180085349  test    eax, eax
0x18008534b  js      loc_18008542F
0x180085351  lea     rdi, [rbx+0F0h]
0x180085358  mov     rdx, rdi
0x18008535b  lea     rcx, [rsp+58h+var_20]
0x180085360  call    cs:__imp_??8CNtSid@@QEAAHAEAV0@@Z; CNtSid::operator==(CNtSid &)
0x180085366  test    eax, eax
0x180085368  jnz     short loc_180085381
0x18008536a  lea     rdx, [rdi+10h]
0x18008536e  lea     rcx, [rsp+58h+var_20]
0x180085373  call    cs:__imp_??8CNtSid@@QEAAHAEAV0@@Z; CNtSid::operator==(CNtSid &)
0x180085379  test    eax, eax
0x18008537b  jz      loc_18008542F
0x180085381  lea     rcx, [rsp+58h+var_20]
0x180085386  call    cs:__imp_??1CNtSid@@QEAA@XZ; CNtSid::~CNtSid(void)
0x18008538c  mov     rax, [rbx]
0x18008538f  mov     r8, [rsp+58h+arg_20]
0x180085397  lea     rdx, IID_IWbemRemoteRefresher
0x18008539e  mov     rcx, rbx
0x1800853a1  mov     rax, [rax]
0x1800853a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800853a9  mov     esi, eax
0x1800853ab  movups  xmm0, xmmword ptr [rbx+0A4h]
0x1800853b2  mov     rax, [rsp+58h+arg_30]
0x1800853ba  movdqu  xmmword ptr [rax], xmm0
0x1800853be  test    esi, esi
0x1800853c0  jns     short loc_1800853D3
0x1800853c2  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800853c8  mov     edx, esi
0x1800853ca  mov     rcx, rax
0x1800853cd  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800853d3  lea     rdi, WPP_GLOBAL_Control
0x1800853da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800853e1  cmp     rcx, rdi
0x1800853e4  jz      short loc_18008540B
0x1800853e6  test    byte ptr [rcx+1Ch], 1
0x1800853ea  jz      short loc_18008540B
0x1800853ec  cmp     byte ptr [rcx+19h], 2
0x1800853f0  jb      short loc_18008540B
0x1800853f2  mov     edx, 11h
0x1800853f7  mov     r9d, esi
0x1800853fa  lea     r8, WPP_583a410948f0357245c15279aca1a26e_Traceguids
0x180085401  mov     rcx, [rcx+10h]
0x180085405  call    WPP_SF_d
0x18008540a  nop
0x18008540b  test    rbx, rbx
0x18008540e  jz      short loc_18008541F
0x180085410  mov     rax, [rbx]
0x180085413  mov     rcx, rbx
0x180085416  mov     rax, [rax+10h]
0x18008541a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008541f  mov     [rsp+58h+var_28], 0
0x180085428  mov     eax, esi
0x18008542a  jmp     loc_18008550A
0x18008542f  lea     rcx, [rsp+58h+var_20]
0x180085434  call    cs:__imp_??1CNtSid@@QEAA@XZ; CNtSid::~CNtSid(void)
0x18008543a  lea     rdi, WPP_GLOBAL_Control
0x180085441  mov     rcx, cs:WPP_GLOBAL_Control
0x180085448  cmp     rcx, rdi
0x18008544b  jz      short loc_18008546E
0x18008544d  test    byte ptr [rcx+1Ch], 1
0x180085451  jz      short loc_18008546E
0x180085453  cmp     byte ptr [rcx+19h], 5
0x180085457  jb      short loc_18008546E
0x180085459  mov     edx, 0Fh
0x18008545e  lea     r8, WPP_583a410948f0357245c15279aca1a26e_Traceguids
0x180085465  mov     rcx, [rcx+10h]
0x180085469  call    WPP_SF_
0x18008546e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180085474  mov     esi, 80041003h
0x180085479  mov     edx, esi
0x18008547b  mov     rcx, rax
0x18008547e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180085484  mov     rcx, cs:WPP_GLOBAL_Control
0x18008548b  cmp     rcx, rdi
0x18008548e  jz      loc_18008540B
0x180085494  test    byte ptr [rcx+1Ch], 1
0x180085498  jz      loc_18008540B
0x18008549e  cmp     byte ptr [rcx+19h], 2
0x1800854a2  jb      loc_18008540B
0x1800854a8  mov     edx, 10h
0x1800854ad  mov     r9d, 80041003h
0x1800854b3  jmp     loc_1800853FA
0x1800854b8  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800854be  mov     ebx, 80041008h
0x1800854c3  mov     edx, ebx
0x1800854c5  mov     rcx, rax
0x1800854c8  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800854ce  lea     rdi, WPP_GLOBAL_Control
0x1800854d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800854dc  cmp     rcx, rdi
0x1800854df  jz      short loc_180085508
0x1800854e1  test    byte ptr [rcx+1Ch], 1
0x1800854e5  jz      short loc_180085508
0x1800854e7  cmp     byte ptr [rcx+19h], 2
0x1800854eb  jb      short loc_180085508
0x1800854ed  mov     edx, 0Eh
0x1800854f2  mov     r9d, 80041008h
0x1800854f8  lea     r8, WPP_583a410948f0357245c15279aca1a26e_Traceguids
0x1800854ff  mov     rcx, [rcx+10h]
0x180085503  call    WPP_SF_d
0x180085508  mov     eax, ebx
0x18008550a  mov     rbx, [rsp+58h+arg_0]
0x18008550f  mov     rsi, [rsp+58h+arg_10]
0x180085514  add     rsp, 50h
0x180085518  pop     rdi
0x180085519  retn
```
