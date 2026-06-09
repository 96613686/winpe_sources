# CRemoteRecord::AddEnumRefresher(CHiPerfPrvRecord *,IWbemHiPerfProvider *,_IWmiProviderStack *,IWbemServices *,CWbemObject *,ushort const *,long,IWbemContext *,CRefreshInfo *)

- ea: `0x18008acf0`
- end: `0x18008afeb`
- name: `?AddEnumRefresher@CRemoteRecord@@UEAAJPEAVCHiPerfPrvRecord@@PEAUIWbemHiPerfProvider@@PEAU_IWmiProviderStack@@PEAUIWbemServices@@PEAVCWbemObject@@PEBGJPEAUIWbemContext@@PEAVCRefreshInfo@@@Z`
- size: `763`
- prototype: `__int64 __fastcall(CRemoteRecord *__hidden this, struct CHiPerfPrvRecord *, struct IWbemHiPerfProvider *, struct _IWmiProviderStack *, struct IWbemServices *, struct IWbemObjectAccess *, const unsigned __int16 *, int, struct IWbemContext *, struct CRefreshInfo *)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x180037120`
- `0x18004a7c8`
- `0x18004a9d8`
- `0x18008985c`
- `0x18008acf0`
- `0x18008aff4`
- `0x18008b5d8`
- `0x18008b96c`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18008ada0`
- `wbemcomn!GetMemLogObject` at `0x18008ae14`
- `wbemcomn!GetMemLogObject` at `0x18008af66`
- `wbemcomn!GetMemLogObject` at `0x18008ada0`
- `wbemcomn!GetMemLogObject` at `0x18008ae14`
- `wbemcomn!GetMemLogObject` at `0x18008af66`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18008afcf`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18008afcf`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18008ad20`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18008ad20`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008adb0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008ae1f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008af71`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008adb0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008ae1f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008af71`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18008ad72`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18008ad72`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall CRemoteRecord::AddEnumRefresher(
        CRemoteRecord *this,
        struct CHiPerfPrvRecord *a2,
        struct IWbemHiPerfProvider *a3,
        struct _IWmiProviderStack *a4,
        struct IWbemServices *a5,
        struct IWbemObjectAccess *a6,
        const unsigned __int16 *a7,
        int a8,
        struct IWbemContext *a9,
        struct CRefreshInfo *a10)
{
  int ProviderRefreshInfo; // esi
  struct IWbemRefresher *v15; // rbx
  CHiPerfEnum *v16; // rax
  CHiPerfEnum *v17; // rdi
  CMemoryLog *MemLogObject; // rax
  CWbemRefreshingSvc *v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // r9
  CMemoryLog *v22; // rax
  CProviderRecord *v23; // rcx
  signed __int32 v24; // r15d
  CMemoryLog *v25; // rax
  struct IWbemRefresher *v27; // [rsp+50h] [rbp-31h] BYREF
  CProviderRecord *v28; // [rsp+58h] [rbp-29h] BYREF
  CHiPerfEnum *v29; // [rsp+60h] [rbp-21h]
  struct IWbemRefresher *v30; // [rsp+68h] [rbp-19h]
  _BYTE v31[80]; // [rsp+70h] [rbp-11h] BYREF
  int v32; // [rsp+D0h] [rbp+4Fh] BYREF

  CInCritSec::CInCritSec((CInCritSec *)v31, (struct _RTL_CRITICAL_SECTION *)this + 5);
  v27 = 0;
  v28 = 0;
  ProviderRefreshInfo = CRemoteRecord::GetProviderRefreshInfo(this, a2, a3, a5, &v28, &v27);
  v15 = v27;
  v30 = v27;
  if ( ProviderRefreshInfo < 0 )
    goto LABEL_23;
  v16 = (CHiPerfEnum *)CWin32DefaultArena::WbemMemAlloc(0x110u);
  v17 = v16;
  v29 = v16;
  if ( v16 )
  {
    CHiPerfEnum::CHiPerfEnum(v16);
    *(_QWORD *)v17 = &CRemoteHiPerfEnum::`vftable';
  }
  else
  {
    v17 = 0;
  }
  if ( !v17 )
  {
    MemLogObject = GetMemLogObject();
    ProviderRefreshInfo = -2147217402;
    CMemoryLog::Write(MemLogObject, -2147217402);
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v20 = 30;
      v21 = 2147749894LL;
LABEL_28:
      WPP_SF_d(*((_QWORD *)v19 + 2), v20, WPP_03c64eaa4d8c32ecfb51fbe2c30fec97_Traceguids, v21);
      goto LABEL_29;
    }
    goto LABEL_29;
  }
  (*(void (__fastcall **)(CHiPerfEnum *))(*(_QWORD *)v17 + 8LL))(v17);
  v29 = v17;
  ProviderRefreshInfo = CHiPerfEnum::SetInstanceTemplate(v17, (struct CWbemInstance *)a6);
  if ( ProviderRefreshInfo < 0 )
  {
    v22 = GetMemLogObject();
    CMemoryLog::Write(v22, ProviderRefreshInfo);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        31,
        WPP_03c64eaa4d8c32ecfb51fbe2c30fec97_Traceguids,
        (unsigned int)ProviderRefreshInfo);
    }
    (*(void (__fastcall **)(CHiPerfEnum *))(*(_QWORD *)v17 + 16LL))(v17);
    v29 = 0;
    goto LABEL_29;
  }
  v32 = 0;
  ProviderRefreshInfo = ((__int64 (__fastcall *)(struct IWbemHiPerfProvider *, struct IWbemServices *, const unsigned __int16 *, struct IWbemRefresher *, _DWORD, struct IWbemContext *, CHiPerfEnum *, int *))a3->lpVtbl->CreateRefreshableEnum)(
                          a3,
                          a5,
                          a7,
                          v27,
                          0,
                          a9,
                          v17,
                          &v32);
  if ( ProviderRefreshInfo < 0 )
    goto LABEL_22;
  v23 = v28;
  if ( !v28 )
  {
    ProviderRefreshInfo = CRefresherRecord::AddProvider(this, a2, a3, v27, a4, &v28);
    if ( ProviderRefreshInfo < 0 )
      goto LABEL_22;
    v23 = v28;
  }
  v24 = _InterlockedExchangeAdd((volatile signed __int32 *)this + 40, 1u);
  ProviderRefreshInfo = CProviderRecord::AddEnumRequest(v23, v17, v32, v24 + 1);
  if ( ProviderRefreshInfo >= 0 )
  {
    ++*((_DWORD *)this + 39);
    ProviderRefreshInfo = CRefreshInfo::SetRemote(a10, this, v24 + 1, a6, (struct _GUID *)((char *)this + 164));
  }
LABEL_22:
  (*(void (__fastcall **)(CHiPerfEnum *))(*(_QWORD *)v17 + 16LL))(v17);
  v29 = 0;
  if ( ProviderRefreshInfo < 0 )
  {
LABEL_23:
    v25 = GetMemLogObject();
    CMemoryLog::Write(v25, ProviderRefreshInfo);
  }
  v19 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v20 = 32;
    v21 = (unsigned int)ProviderRefreshInfo;
    goto LABEL_28;
  }
LABEL_29:
  if ( v15 )
    ((void (__fastcall *)(struct IWbemRefresher *))v15->lpVtbl->Release)(v15);
  v30 = 0;
  CInCritSec::~CInCritSec((CInCritSec *)v31);
  return (unsigned int)ProviderRefreshInfo;
}

```

## disassembly

```asm
0x18008acf0  push    rbp
0x18008acf2  push    rbx
0x18008acf3  push    rsi
0x18008acf4  push    rdi
0x18008acf5  push    r12
0x18008acf7  push    r13
0x18008acf9  push    r14
0x18008acfb  push    r15
0x18008acfd  lea     rbp, [rsp-7]
0x18008ad02  sub     rsp, 88h
0x18008ad09  mov     r13, r9
0x18008ad0c  mov     r15, r8
0x18008ad0f  mov     r12, rdx
0x18008ad12  mov     r14, rcx
0x18008ad15  lea     rdx, [rcx+0C8h]
0x18008ad1c  lea     rcx, [rbp+3Fh+var_50]
0x18008ad20  call    cs:__imp_??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x18008ad26  nop
0x18008ad27  mov     [rbp+3Fh+var_70], 0
0x18008ad2f  mov     [rbp+3Fh+var_68], 0
0x18008ad37  lea     rax, [rbp+3Fh+var_70]
0x18008ad3b  mov     [rsp+0C0h+var_98], rax; struct IWbemRefresher **
0x18008ad40  lea     rax, [rbp+3Fh+var_68]
0x18008ad44  mov     [rsp+0C0h+var_A0], rax; struct CProviderRecord **
0x18008ad49  mov     r9, [rbp+3Fh+arg_20]; struct IWbemServices *
0x18008ad4d  mov     r8, r15; struct IWbemHiPerfProvider *
0x18008ad50  mov     rdx, r12; struct CHiPerfPrvRecord *
0x18008ad53  mov     rcx, r14; this
0x18008ad56  call    ?GetProviderRefreshInfo@CRemoteRecord@@IEAAJPEAVCHiPerfPrvRecord@@PEAUIWbemHiPerfProvider@@PEAUIWbemServices@@PEAPEAVCProviderRecord@@PEAPEAUIWbemRefresher@@@Z; CRemoteRecord::GetProviderRefreshInfo(CHiPerfPrvRecord *,IWbemHiPerfProvider *,IWbemServices *,CProviderRecord * *,IWbemRefresher * *)
0x18008ad5b  mov     esi, eax
0x18008ad5d  mov     rbx, [rbp+3Fh+var_70]
0x18008ad61  mov     [rbp+3Fh+var_58], rbx
0x18008ad65  test    eax, eax
0x18008ad67  js      loc_18008AF66
0x18008ad6d  mov     ecx, 110h
0x18008ad72  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18008ad78  mov     rdi, rax
0x18008ad7b  mov     [rbp+3Fh+var_60], rax
0x18008ad7f  test    rax, rax
0x18008ad82  jz      short loc_18008AD99
0x18008ad84  mov     rcx, rax; this
0x18008ad87  call    ??0CHiPerfEnum@@IEAA@XZ; CHiPerfEnum::CHiPerfEnum(void)
0x18008ad8c  nop
0x18008ad8d  lea     rax, ??_7CRemoteHiPerfEnum@@6B@; const CRemoteHiPerfEnum::`vftable'
0x18008ad94  mov     [rdi], rax
0x18008ad97  jmp     short loc_18008AD9B
0x18008ad99  xor     edi, edi
0x18008ad9b  test    rdi, rdi
0x18008ad9e  jnz     short loc_18008ADEF
0x18008ada0  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18008ada6  mov     esi, 80041006h
0x18008adab  mov     edx, esi
0x18008adad  mov     rcx, rax
0x18008adb0  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18008adb6  lea     rax, WPP_GLOBAL_Control
0x18008adbd  mov     rcx, cs:WPP_GLOBAL_Control
0x18008adc4  cmp     rcx, rax
0x18008adc7  jz      loc_18008AFAF
0x18008adcd  test    byte ptr [rcx+1Ch], 1
0x18008add1  jz      loc_18008AFAF
0x18008add7  cmp     byte ptr [rcx+19h], 2
0x18008addb  jb      loc_18008AFAF
0x18008ade1  lea     edx, [rdi+1Eh]
0x18008ade4  mov     r9d, 80041006h
0x18008adea  jmp     loc_18008AF9E
0x18008adef  mov     rax, [rdi]
0x18008adf2  mov     rcx, rdi
0x18008adf5  mov     rax, [rax+8]
0x18008adf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008adfe  mov     [rbp+3Fh+var_60], rdi
0x18008ae02  mov     rdx, [rbp+3Fh+arg_28]; struct CWbemInstance *
0x18008ae06  mov     rcx, rdi; this
0x18008ae09  call    ?SetInstanceTemplate@CHiPerfEnum@@QEAAJPEAVCWbemInstance@@@Z; CHiPerfEnum::SetInstanceTemplate(CWbemInstance *)
0x18008ae0e  mov     esi, eax
0x18008ae10  test    eax, eax
0x18008ae12  jns     short loc_18008AE79
0x18008ae14  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18008ae1a  mov     edx, esi
0x18008ae1c  mov     rcx, rax
0x18008ae1f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18008ae25  lea     rax, WPP_GLOBAL_Control
0x18008ae2c  mov     rcx, cs:WPP_GLOBAL_Control
0x18008ae33  cmp     rcx, rax
0x18008ae36  jz      short loc_18008AE5D
0x18008ae38  test    byte ptr [rcx+1Ch], 1
0x18008ae3c  jz      short loc_18008AE5D
0x18008ae3e  cmp     byte ptr [rcx+19h], 2
0x18008ae42  jb      short loc_18008AE5D
0x18008ae44  mov     edx, 1Fh
0x18008ae49  mov     r9d, esi
0x18008ae4c  lea     r8, WPP_03c64eaa4d8c32ecfb51fbe2c30fec97_Traceguids
0x18008ae53  mov     rcx, [rcx+10h]
0x18008ae57  call    WPP_SF_d
0x18008ae5c  nop
0x18008ae5d  mov     rax, [rdi]
0x18008ae60  mov     rcx, rdi
0x18008ae63  mov     rax, [rax+10h]
0x18008ae67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ae6c  mov     [rbp+3Fh+var_60], 0
0x18008ae74  jmp     loc_18008AFAF
0x18008ae79  mov     [rbp+3Fh+arg_0], 0
0x18008ae80  mov     rax, [r15]
0x18008ae83  lea     rcx, [rbp+3Fh+arg_0]
0x18008ae87  mov     [rsp+0C0h+var_88], rcx
0x18008ae8c  mov     [rsp+0C0h+var_90], rdi
0x18008ae91  mov     rcx, [rbp+3Fh+arg_40]
0x18008ae98  mov     [rsp+0C0h+var_98], rcx
0x18008ae9d  mov     dword ptr [rsp+0C0h+var_A0], 0
0x18008aea5  mov     r9, [rbp+3Fh+var_70]
0x18008aea9  mov     r8, [rbp+3Fh+arg_30]
0x18008aead  mov     rdx, [rbp+3Fh+arg_20]
0x18008aeb1  mov     rcx, r15
0x18008aeb4  mov     rax, [rax+38h]
0x18008aeb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008aebd  mov     esi, eax
0x18008aebf  test    eax, eax
0x18008aec1  js      loc_18008AF4B
0x18008aec7  mov     rcx, [rbp+3Fh+var_68]
0x18008aecb  test    rcx, rcx
0x18008aece  jnz     short loc_18008AEFA
0x18008aed0  lea     rax, [rbp+3Fh+var_68]
0x18008aed4  mov     [rsp+0C0h+var_98], rax; struct CProviderRecord **
0x18008aed9  mov     [rsp+0C0h+var_A0], r13; struct _IWmiProviderStack *
0x18008aede  mov     r9, [rbp+3Fh+var_70]; struct IWbemRefresher *
0x18008aee2  mov     r8, r15; struct IWbemHiPerfProvider *
0x18008aee5  mov     rdx, r12; struct CHiPerfPrvRecord *
0x18008aee8  mov     rcx, r14; this
0x18008aeeb  call    ?AddProvider@CRefresherRecord@@QEAAJPEAVCHiPerfPrvRecord@@PEAUIWbemHiPerfProvider@@PEAUIWbemRefresher@@PEAU_IWmiProviderStack@@PEAPEAVCProviderRecord@@@Z; CRefresherRecord::AddProvider(CHiPerfPrvRecord *,IWbemHiPerfProvider *,IWbemRefresher *,_IWmiProviderStack *,CProviderRecord * *)
0x18008aef0  mov     esi, eax
0x18008aef2  test    eax, eax
0x18008aef4  js      short loc_18008AF4B
0x18008aef6  mov     rcx, [rbp+3Fh+var_68]; this
0x18008aefa  mov     r15d, 1
0x18008af00  lock xadd [r14+0A0h], r15d
0x18008af09  lea     r9d, [r15+1]; int
0x18008af0d  mov     r8d, [rbp+3Fh+arg_0]; int
0x18008af11  mov     rdx, rdi; struct CRemoteHiPerfEnum *
0x18008af14  call    ?AddEnumRequest@CProviderRecord@@QEAAJPEAVCRemoteHiPerfEnum@@JJ@Z; CProviderRecord::AddEnumRequest(CRemoteHiPerfEnum *,long,long)
0x18008af19  mov     esi, eax
0x18008af1b  test    eax, eax
0x18008af1d  js      short loc_18008AF4B
0x18008af1f  inc     dword ptr [r14+9Ch]
0x18008af26  lea     rax, [r14+0A4h]
0x18008af2d  mov     [rsp+0C0h+var_A0], rax; struct _GUID *
0x18008af32  mov     r9, [rbp+3Fh+arg_28]; struct IWbemObjectAccess *
0x18008af36  lea     r8d, [r15+1]; int
0x18008af3a  mov     rdx, r14; struct IWbemRemoteRefresher *
0x18008af3d  mov     rcx, [rbp+3Fh+arg_48]; this
0x18008af44  call    ?SetRemote@CRefreshInfo@@QEAAJPEAUIWbemRemoteRefresher@@JPEAUIWbemObjectAccess@@PEAU_GUID@@@Z; CRefreshInfo::SetRemote(IWbemRemoteRefresher *,long,IWbemObjectAccess *,_GUID *)
0x18008af49  mov     esi, eax
0x18008af4b  mov     rax, [rdi]
0x18008af4e  mov     rcx, rdi
0x18008af51  mov     rax, [rax+10h]
0x18008af55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008af5a  mov     [rbp+3Fh+var_60], 0
0x18008af62  test    esi, esi
0x18008af64  jns     short loc_18008AF77
0x18008af66  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18008af6c  mov     edx, esi
0x18008af6e  mov     rcx, rax
0x18008af71  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18008af77  lea     rax, WPP_GLOBAL_Control
0x18008af7e  mov     rcx, cs:WPP_GLOBAL_Control
0x18008af85  cmp     rcx, rax
0x18008af88  jz      short loc_18008AFAF
0x18008af8a  test    byte ptr [rcx+1Ch], 1
0x18008af8e  jz      short loc_18008AFAF
0x18008af90  cmp     byte ptr [rcx+19h], 2
0x18008af94  jb      short loc_18008AFAF
0x18008af96  mov     edx, 20h ; ' '
0x18008af9b  mov     r9d, esi
0x18008af9e  lea     r8, WPP_03c64eaa4d8c32ecfb51fbe2c30fec97_Traceguids
0x18008afa5  mov     rcx, [rcx+10h]
0x18008afa9  call    WPP_SF_d
0x18008afae  nop
0x18008afaf  test    rbx, rbx
0x18008afb2  jz      short loc_18008AFC3
0x18008afb4  mov     rax, [rbx]
0x18008afb7  mov     rcx, rbx
0x18008afba  mov     rax, [rax+10h]
0x18008afbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008afc3  mov     [rbp+3Fh+var_58], 0
0x18008afcb  lea     rcx, [rbp+3Fh+var_50]
0x18008afcf  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x18008afd5  mov     eax, esi
0x18008afd7  add     rsp, 88h
0x18008afde  pop     r15
0x18008afe0  pop     r14
0x18008afe2  pop     r13
0x18008afe4  pop     r12
0x18008afe6  pop     rdi
0x18008afe7  pop     rsi
0x18008afe8  pop     rbx
0x18008afe9  pop     rbp
0x18008afea  retn
```
