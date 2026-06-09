# CWbemObjectArrayPacket::GetClasslessInstanceObject(CWbemObjectPacket &,IWbemClassObject * *,CWbemClassCache &)

- ea: `0x1800150c0`
- end: `0x18001557f`
- name: `?GetClasslessInstanceObject@CWbemObjectArrayPacket@@AEAAJAEAVCWbemObjectPacket@@PEAPEAUIWbemClassObject@@AEAVCWbemClassCache@@@Z`
- size: `1215`
- prototype: `__int64 __fastcall(CWbemObjectArrayPacket *__hidden this, struct CWbemObjectPacket *, struct IWbemClassObject **, struct CWbemClassCache *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1800150c0`
- `0x180015590`
- `0x180035b08`
- `0x180037120`
- `0x18006fa4c`
- `0x180091966`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x1800152ed`
- `wbemcomn!GetMemLogObject` at `0x18001530a`
- `wbemcomn!GetMemLogObject` at `0x18001536e`
- `wbemcomn!GetMemLogObject` at `0x1800153d5`
- `wbemcomn!GetMemLogObject` at `0x18001543c`
- `wbemcomn!GetMemLogObject` at `0x1800154a3`
- `wbemcomn!GetMemLogObject` at `0x18001550a`
- `wbemcomn!GetMemLogObject` at `0x1800152ed`
- `wbemcomn!GetMemLogObject` at `0x18001530a`
- `wbemcomn!GetMemLogObject` at `0x18001536e`
- `wbemcomn!GetMemLogObject` at `0x1800153d5`
- `wbemcomn!GetMemLogObject` at `0x18001543c`
- `wbemcomn!GetMemLogObject` at `0x1800154a3`
- `wbemcomn!GetMemLogObject` at `0x18001550a`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180015225`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180015225`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x1800151a3`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x1800151a3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800152f8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180015315`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001537c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800153e3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001544a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800154b1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180015518`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800152f8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180015315`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001537c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800153e3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001544a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800154b1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180015518`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CWbemObjectArrayPacket::GetClasslessInstanceObject(
        CWbemObjectArrayPacket *this,
        struct CWbemObjectPacket *a2,
        struct IWbemClassObject **a3,
        struct _RTL_CRITICAL_SECTION *a4)
{
  __int64 v6; // r10
  _DWORD *v7; // rax
  int WbemInstanceObject; // ebx
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rsi
  struct _RTL_CRITICAL_SECTION *CriticalSection; // rbx
  PRTL_CRITICAL_SECTION_DEBUG v11; // rdi
  __int64 v12; // rdi
  struct IWbemClassObject *v13; // r14
  CMemoryLog *v15; // rax
  CMemoryLog *v16; // rax
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v18; // rax
  CMemoryLog *v19; // rax
  CMemoryLog *v20; // rax
  CMemoryLog *v21; // rax
  _BYTE v22[16]; // [rsp+20h] [rbp-58h] BYREF
  struct _GUID Buf2; // [rsp+30h] [rbp-48h] BYREF
  void **v24; // [rsp+40h] [rbp-38h] BYREF
  _DWORD *v25; // [rsp+48h] [rbp-30h]
  int v26; // [rsp+50h] [rbp-28h]
  char *v27; // [rsp+58h] [rbp-20h]
  int v28; // [rsp+60h] [rbp-18h]
  struct _RTL_CRITICAL_SECTION *v29; // [rsp+68h] [rbp-10h]
  struct IWbemClassObject *pExceptionObject; // [rsp+C8h] [rbp+50h] BYREF

  v6 = *((unsigned int *)a2 + 2);
  v7 = *(_DWORD **)a2;
  v25 = 0;
  v26 = 0;
  v24 = &CWbemInstancePacket::`vftable';
  if ( v7 )
  {
    if ( (_DWORD *)((char *)v7 + 9) < v7 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, -2);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          30,
          WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids,
          "SafeIntException(ERROR_INVALID_PARAMETER)");
      }
      LODWORD(pExceptionObject) = 87;
      throw (SafeIntException *)&pExceptionObject;
    }
    v27 = (char *)v7 + 9;
    if ( (unsigned int)v6 < 0x21 )
    {
      v18 = GetMemLogObject();
      CMemoryLog::Write(v18, -2);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          31,
          WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids,
          "SafeIntException(ERROR_INVALID_PARAMETER)");
      }
      LODWORD(pExceptionObject) = 87;
      throw (SafeIntException *)&pExceptionObject;
    }
    v28 = v6 - 9;
    if ( *(_DWORD *)((char *)v7 + 9) != 24 || *(_DWORD *)((char *)v7 + 13) > (unsigned int)(v6 - 9) )
    {
      v20 = GetMemLogObject();
      CMemoryLog::Write(v20, -2);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          32,
          WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids,
          "SafeIntException(ERROR_INVALID_DATA)");
      }
      LODWORD(pExceptionObject) = 13;
      throw (SafeIntException *)&pExceptionObject;
    }
    v25 = v7;
    v26 = v6;
    if ( *v7 != 9 || (unsigned int)v7[1] > (unsigned __int64)(v6 - 9) )
    {
      v19 = GetMemLogObject();
      CMemoryLog::Write(v19, -2);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids,
          "SafeIntException(ERROR_INVALID_DATA)");
      }
      LODWORD(pExceptionObject) = 13;
      throw (SafeIntException *)&pExceptionObject;
    }
  }
  else
  {
    v27 = 0;
    v28 = 0;
    v25 = 0;
    v26 = v6;
  }
  v24 = &CWbemClasslessInstancePacket::`vftable';
  if ( !a4 )
  {
    v21 = GetMemLogObject();
    CMemoryLog::Write(v21, -2);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        33,
        WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids,
        "CX_Exception()");
    }
    throw (CX_Exception *)&pExceptionObject;
  }
  v29 = a4;
  pExceptionObject = 0;
  Buf2 = 0;
  WbemInstanceObject = CWbemInstancePacket::GetWbemInstanceObject(
                         (CWbemInstancePacket *)&v24,
                         (struct CWbemInstance **)&pExceptionObject,
                         &Buf2);
  if ( WbemInstanceObject < 0 )
    goto LABEL_31;
  CInCritSec::CInCritSec((CInCritSec *)v22, a4);
  DebugInfo = a4[1].DebugInfo;
  CriticalSection = DebugInfo->CriticalSection;
  v11 = DebugInfo;
  if ( BYTE1(CriticalSection->LockSemaphore) )
    goto LABEL_28;
  do
  {
    if ( memcmp_0(&CriticalSection->SpinCount, &Buf2, 0x10u) < 0 )
    {
      CriticalSection = (struct _RTL_CRITICAL_SECTION *)CriticalSection->OwningThread;
    }
    else
    {
      v11 = (PRTL_CRITICAL_SECTION_DEBUG)CriticalSection;
      CriticalSection = (struct _RTL_CRITICAL_SECTION *)CriticalSection->DebugInfo;
    }
  }
  while ( !BYTE1(CriticalSection->LockSemaphore) );
  if ( v11 == DebugInfo || memcmp_0(&Buf2, &v11->EntryCount, 0x10u) < 0 )
  {
LABEL_28:
    v12 = 0;
    WbemInstanceObject = -2147217406;
  }
  else
  {
    v12 = *(_QWORD *)&v11[1].Type;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
    WbemInstanceObject = 0;
  }
  CInCritSec::~CInCritSec((CInCritSec *)v22);
  if ( WbemInstanceObject < 0 )
  {
    v15 = GetMemLogObject();
    CMemoryLog::Write(v15, WbemInstanceObject);
  }
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      WPP_6039d850a549361afdc48cca3ddd98df_Traceguids,
      (unsigned int)WbemInstanceObject);
  }
  v13 = pExceptionObject;
  if ( WbemInstanceObject < 0 )
    goto LABEL_61;
  WbemInstanceObject = ((__int64 (__fastcall *)(struct IWbemClassObject *, __int64))pExceptionObject->lpVtbl[2].PutMethod)(
                         pExceptionObject,
                         v12);
  if ( WbemInstanceObject >= 0 )
    *a3 = v13;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  if ( WbemInstanceObject < 0 )
  {
LABEL_61:
    ((void (__fastcall *)(struct IWbemClassObject *))v13->lpVtbl->Release)(v13);
LABEL_31:
    v16 = GetMemLogObject();
    CMemoryLog::Write(v16, WbemInstanceObject);
  }
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      21,
      WPP_6737080c1ee93bb283ad4d220f5cef4f_Traceguids,
      (unsigned int)WbemInstanceObject);
  }
  v24 = &CWbemInstancePacket::`vftable';
  return (unsigned int)WbemInstanceObject;
}

```

## disassembly

```asm
0x1800150c0  push    rbp
0x1800150c2  push    rbx
0x1800150c3  push    rsi
0x1800150c4  push    rdi
0x1800150c5  push    r12
0x1800150c7  push    r13
0x1800150c9  push    r14
0x1800150cb  push    r15
0x1800150cd  mov     rbp, rsp
0x1800150d0  sub     rsp, 78h
0x1800150d4  mov     rdi, r9
0x1800150d7  mov     r15, r8
0x1800150da  mov     r10d, [rdx+8]
0x1800150de  mov     rax, [rdx]
0x1800150e1  xor     r14d, r14d
0x1800150e4  mov     [rbp+var_30], r14
0x1800150e8  mov     [rbp+var_28], r14d
0x1800150ec  lea     r13, ??_7CWbemInstancePacket@@6B@; const CWbemInstancePacket::`vftable'
0x1800150f3  mov     [rbp+var_38], r13
0x1800150f7  test    rax, rax
0x1800150fa  jz      loc_1800152D8
0x180015100  lea     rcx, [rax+9]
0x180015104  cmp     rcx, rax
0x180015107  jbe     loc_18001536E
0x18001510d  mov     [rbp+var_20], rcx
0x180015111  cmp     r10d, 21h ; '!'
0x180015115  jb      loc_1800153D5
0x18001511b  lea     edx, [r10-9]
0x18001511f  mov     [rbp+var_18], edx
0x180015122  cmp     dword ptr [rcx], 18h
0x180015125  jnz     loc_1800154A3
0x18001512b  cmp     [rcx+4], edx
0x18001512e  ja      loc_1800154A3
0x180015134  mov     [rbp+var_30], rax
0x180015138  mov     [rbp+var_28], r10d
0x18001513c  cmp     dword ptr [rax], 9
0x18001513f  jnz     loc_18001543C
0x180015145  mov     ecx, [rax+4]
0x180015148  lea     rax, [r10-9]
0x18001514c  cmp     rcx, rax
0x18001514f  ja      loc_18001543C
0x180015155  lea     r12, ??_7CWbemClasslessInstancePacket@@6B@; const CWbemClasslessInstancePacket::`vftable'
0x18001515c  mov     [rbp+var_38], r12
0x180015160  test    rdi, rdi
0x180015163  jz      loc_18001550A
0x180015169  mov     [rbp+var_10], rdi
0x18001516d  mov     [rbp+pExceptionObject], r14
0x180015171  xorps   xmm0, xmm0
0x180015174  movups  [rbp+Buf2], xmm0
0x180015178  lea     r8, [rbp+Buf2]; struct _GUID *
0x18001517c  lea     rdx, [rbp+pExceptionObject]; struct CWbemInstance **
0x180015180  lea     rcx, [rbp+var_38]; this
0x180015184  call    ?GetWbemInstanceObject@CWbemInstancePacket@@QEAAJPEAPEAVCWbemInstance@@AEAU_GUID@@@Z; CWbemInstancePacket::GetWbemInstanceObject(CWbemInstance * *,_GUID &)
0x180015189  mov     ebx, eax
0x18001518b  test    eax, eax
0x18001518d  js      loc_180015303
0x180015193  movaps  xmm0, [rbp+Buf2]
0x180015197  movdqa  [rbp+Buf2], xmm0
0x18001519c  mov     rdx, rdi
0x18001519f  lea     rcx, [rbp+var_58]
0x1800151a3  call    cs:__imp_??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x1800151a9  nop
0x1800151aa  mov     rsi, [rdi+28h]
0x1800151ae  mov     rbx, [rsi+8]
0x1800151b2  mov     rdi, rsi
0x1800151b5  cmp     byte ptr [rbx+19h], 0
0x1800151b9  jnz     loc_1800152C2
0x1800151bf  nop
0x1800151c0  lea     rcx, [rbx+20h]; Buf1
0x1800151c4  mov     r8d, 10h; Size
0x1800151ca  lea     rdx, [rbp+Buf2]; Buf2
0x1800151ce  call    memcmp_0
0x1800151d3  test    eax, eax
0x1800151d5  js      loc_1800152CF
0x1800151db  mov     rdi, rbx
0x1800151de  mov     rbx, [rbx]
0x1800151e1  cmp     byte ptr [rbx+19h], 0
0x1800151e5  jz      short loc_1800151C0
0x1800151e7  cmp     rdi, rsi
0x1800151ea  jz      loc_1800152C2
0x1800151f0  lea     rdx, [rdi+20h]; Buf2
0x1800151f4  mov     r8d, 10h; Size
0x1800151fa  lea     rcx, [rbp+Buf2]; Buf1
0x1800151fe  call    memcmp_0
0x180015203  test    eax, eax
0x180015205  js      loc_1800152C2
0x18001520b  mov     rdi, [rdi+30h]
0x18001520f  mov     rax, [rdi]
0x180015212  mov     rcx, rdi
0x180015215  mov     rax, [rax+8]
0x180015219  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001521e  mov     ebx, r14d
0x180015221  lea     rcx, [rbp+var_58]
0x180015225  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x18001522b  test    ebx, ebx
0x18001522d  js      loc_1800152ED
0x180015233  lea     rsi, WPP_GLOBAL_Control
0x18001523a  mov     rcx, cs:WPP_GLOBAL_Control
0x180015241  cmp     rcx, rsi
0x180015244  jz      short loc_180015250
0x180015246  test    byte ptr [rcx+1Ch], 1
0x18001524a  jnz     loc_180015320
0x180015250  mov     r14, [rbp+pExceptionObject]
0x180015254  test    ebx, ebx
0x180015256  js      loc_18001556A
0x18001525c  mov     rax, [r14]
0x18001525f  mov     rdx, rdi
0x180015262  mov     rcx, r14
0x180015265  mov     rax, [rax+250h]
0x18001526c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015271  mov     ebx, eax
0x180015273  test    eax, eax
0x180015275  js      short loc_18001527A
0x180015277  mov     [r15], r14
0x18001527a  mov     rax, [rdi]
0x18001527d  mov     rcx, rdi
0x180015280  mov     rax, [rax+10h]
0x180015284  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015289  test    ebx, ebx
0x18001528b  js      loc_18001556A
0x180015291  mov     rcx, cs:WPP_GLOBAL_Control
0x180015298  cmp     rcx, rsi
0x18001529b  jz      short loc_1800152A7
0x18001529d  test    byte ptr [rcx+1Ch], 1
0x1800152a1  jnz     loc_180015347
0x1800152a7  mov     [rbp+var_38], r12
0x1800152ab  mov     [rbp+var_38], r13
0x1800152af  mov     eax, ebx
0x1800152b1  add     rsp, 78h
0x1800152b5  pop     r15
0x1800152b7  pop     r14
0x1800152b9  pop     r13
0x1800152bb  pop     r12
0x1800152bd  pop     rdi
0x1800152be  pop     rsi
0x1800152bf  pop     rbx
0x1800152c0  pop     rbp
0x1800152c1  retn
0x1800152c2  mov     rdi, r14
0x1800152c5  mov     ebx, 80041002h
0x1800152ca  jmp     loc_180015221
0x1800152cf  mov     rbx, [rbx+10h]
0x1800152d3  jmp     loc_1800151E1
0x1800152d8  mov     [rbp+var_20], r14
0x1800152dc  mov     [rbp+var_18], r14d
0x1800152e0  mov     [rbp+var_30], rax
0x1800152e4  mov     [rbp+var_28], r10d
0x1800152e8  jmp     loc_180015155
0x1800152ed  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800152f3  mov     edx, ebx
0x1800152f5  mov     rcx, rax
0x1800152f8  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800152fe  jmp     loc_180015233
0x180015303  lea     rsi, WPP_GLOBAL_Control
0x18001530a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180015310  mov     edx, ebx
0x180015312  mov     rcx, rax
0x180015315  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001531b  jmp     loc_180015291
0x180015320  cmp     byte ptr [rcx+19h], 2
0x180015324  jb      loc_180015250
0x18001532a  mov     edx, 0Bh
0x18001532f  mov     r9d, ebx
0x180015332  lea     r8, WPP_6039d850a549361afdc48cca3ddd98df_Traceguids
0x180015339  mov     rcx, [rcx+10h]
0x18001533d  call    WPP_SF_d
0x180015342  jmp     loc_180015250
0x180015347  cmp     byte ptr [rcx+19h], 2
0x18001534b  jb      loc_1800152A7
0x180015351  mov     edx, 15h
0x180015356  mov     r9d, ebx
0x180015359  lea     r8, WPP_6737080c1ee93bb283ad4d220f5cef4f_Traceguids
0x180015360  mov     rcx, [rcx+10h]
0x180015364  call    WPP_SF_d
0x180015369  jmp     loc_1800152A7
0x18001536e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180015374  mov     edx, 0FFFFFFFEh
0x180015379  mov     rcx, rax
0x18001537c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180015382  lea     rsi, WPP_GLOBAL_Control
0x180015389  mov     rcx, cs:WPP_GLOBAL_Control
0x180015390  cmp     rcx, rsi
0x180015393  jz      short loc_1800153BD
0x180015395  test    byte ptr [rcx+1Ch], 1
0x180015399  jz      short loc_1800153BD
0x18001539b  cmp     byte ptr [rcx+19h], 2
0x18001539f  jb      short loc_1800153BD
0x1800153a1  mov     edx, 1Eh
0x1800153a6  lea     r9, aSafeintexcepti_0; "SafeIntException(ERROR_INVALID_PARAMETE"...
0x1800153ad  lea     r8, WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids
0x1800153b4  mov     rcx, [rcx+10h]
0x1800153b8  call    WPP_SF_s
0x1800153bd  mov     dword ptr [rbp+pExceptionObject], 57h ; 'W'
0x1800153c4  lea     rdx, _TI2?AVSafeIntException@@; pThrowInfo
0x1800153cb  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800153cf  call    _CxxThrowException_0
0x1800153d5  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800153db  mov     edx, 0FFFFFFFEh
0x1800153e0  mov     rcx, rax
0x1800153e3  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800153e9  lea     rsi, WPP_GLOBAL_Control
0x1800153f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800153f7  cmp     rcx, rsi
0x1800153fa  jz      short loc_180015424
0x1800153fc  test    byte ptr [rcx+1Ch], 1
0x180015400  jz      short loc_180015424
0x180015402  cmp     byte ptr [rcx+19h], 2
0x180015406  jb      short loc_180015424
0x180015408  mov     edx, 1Fh
0x18001540d  lea     r9, aSafeintexcepti_0; "SafeIntException(ERROR_INVALID_PARAMETE"...
0x180015414  lea     r8, WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids
0x18001541b  mov     rcx, [rcx+10h]
0x18001541f  call    WPP_SF_s
0x180015424  mov     dword ptr [rbp+pExceptionObject], 57h ; 'W'
0x18001542b  lea     rdx, _TI2?AVSafeIntException@@; pThrowInfo
0x180015432  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180015436  call    _CxxThrowException_0
0x18001543c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180015442  mov     edx, 0FFFFFFFEh
0x180015447  mov     rcx, rax
0x18001544a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180015450  lea     rsi, WPP_GLOBAL_Control
0x180015457  mov     rcx, cs:WPP_GLOBAL_Control
0x18001545e  cmp     rcx, rsi
0x180015461  jz      short loc_18001548B
0x180015463  test    byte ptr [rcx+1Ch], 1
0x180015467  jz      short loc_18001548B
0x180015469  cmp     byte ptr [rcx+19h], 2
0x18001546d  jb      short loc_18001548B
0x18001546f  mov     edx, 0Eh
0x180015474  lea     r9, aSafeintexcepti; "SafeIntException(ERROR_INVALID_DATA)"
0x18001547b  lea     r8, WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids
0x180015482  mov     rcx, [rcx+10h]
0x180015486  call    WPP_SF_s
0x18001548b  mov     dword ptr [rbp+pExceptionObject], 0Dh
0x180015492  lea     rdx, _TI2?AVSafeIntException@@; pThrowInfo
0x180015499  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001549d  call    _CxxThrowException_0
0x1800154a3  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800154a9  mov     edx, 0FFFFFFFEh
0x1800154ae  mov     rcx, rax
0x1800154b1  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800154b7  lea     rsi, WPP_GLOBAL_Control
0x1800154be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800154c5  cmp     rcx, rsi
0x1800154c8  jz      short loc_1800154F2
0x1800154ca  test    byte ptr [rcx+1Ch], 1
0x1800154ce  jz      short loc_1800154F2
0x1800154d0  cmp     byte ptr [rcx+19h], 2
0x1800154d4  jb      short loc_1800154F2
0x1800154d6  mov     edx, 20h ; ' '
0x1800154db  lea     r9, aSafeintexcepti; "SafeIntException(ERROR_INVALID_DATA)"
0x1800154e2  lea     r8, WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids
0x1800154e9  mov     rcx, [rcx+10h]
0x1800154ed  call    WPP_SF_s
0x1800154f2  mov     dword ptr [rbp+pExceptionObject], 0Dh
0x1800154f9  lea     rdx, _TI2?AVSafeIntException@@; pThrowInfo
0x180015500  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180015504  call    _CxxThrowException_0
0x18001550a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180015510  mov     edx, 0FFFFFFFEh
0x180015515  mov     rcx, rax
0x180015518  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001551e  lea     rsi, WPP_GLOBAL_Control
0x180015525  mov     rcx, cs:WPP_GLOBAL_Control
0x18001552c  cmp     rcx, rsi
0x18001552f  jz      short loc_180015559
0x180015531  test    byte ptr [rcx+1Ch], 1
0x180015535  jz      short loc_180015559
0x180015537  cmp     byte ptr [rcx+19h], 2
0x18001553b  jb      short loc_180015559
0x18001553d  mov     edx, 21h ; '!'
0x180015542  lea     r9, aCxException; "CX_Exception()"
0x180015549  lea     r8, WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids
0x180015550  mov     rcx, [rcx+10h]
0x180015554  call    WPP_SF_s
0x180015559  lea     rdx, _TI1?AVCX_Exception@@; pThrowInfo
0x180015560  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180015564  call    _CxxThrowException_0
0x18001556a  mov     rax, [r14]
0x18001556d  mov     rcx, r14
0x180015570  mov     rax, [rax+10h]
0x180015574  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015579  jmp     loc_18001530A
```
