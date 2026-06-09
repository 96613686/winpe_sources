# CWbemClass::GetLimitedVersion(CLimitationMapping *,CWbemClass * *)

- ea: `0x1800015a0`
- end: `0x1800018cc`
- name: `?GetLimitedVersion@CWbemClass@@QEAAJPEAVCLimitationMapping@@PEAPEAV1@@Z`
- size: `812`
- prototype: `int(CWbemClass *__hidden this, struct CLimitationMapping *, struct CWbemClass **)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800018e0`

## callees

- `0x1800015a0`
- `0x1800183f0`
- `0x180020440`
- `0x180037120`
- `0x18006d1b0`
- `0x18006fa66`
- `0x180073a00`
- `0x180091972`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x1800015d5`
- `wbemcomn!GetMemLogObject` at `0x18000167f`
- `wbemcomn!GetMemLogObject` at `0x180001753`
- `wbemcomn!GetMemLogObject` at `0x1800017f4`
- `wbemcomn!GetMemLogObject` at `0x1800015d5`
- `wbemcomn!GetMemLogObject` at `0x18000167f`
- `wbemcomn!GetMemLogObject` at `0x180001753`
- `wbemcomn!GetMemLogObject` at `0x1800017f4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800015e5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000168f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180001763`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180001804`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800015e5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000168f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180001763`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180001804`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800017cd`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800017cd`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CWbemClass::GetLimitedVersion(
        CWbemClass *this,
        struct CLimitationMapping *a2,
        struct CWbemClass **a3)
{
  _BYTE *v6; // rbx
  CMemoryLog *v7; // rax
  __int64 result; // rax
  int v9; // edi
  unsigned __int8 *LimitedRepresentation; // rax
  unsigned __int8 *v11; // r14
  CMemoryLog *v12; // rax
  CMemoryLog *v13; // rax
  CWbemClass *v14; // rax
  struct CWbemClass *v15; // rdi
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v17; // rax
  unsigned __int8 *v18; // [rsp+30h] [rbp-68h]
  _QWORD v19[2]; // [rsp+40h] [rbp-58h] BYREF
  char v20; // [rsp+50h] [rbp-48h]
  CWbemClass *v21; // [rsp+B8h] [rbp+20h] BYREF

  try
  {
    v6 = (_BYTE *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 15) + 8LL))(
                    *((_QWORD *)this + 15),
                    *((unsigned int *)this + 38));
    if ( v6 )
    {
      v19[0] = *((_QWORD *)this + 15);
      v19[1] = v6;
      v20 = 0;
      memset_0(v6, 0, *((unsigned int *)this + 38));
      v9 = (_DWORD)v6 + *((_DWORD *)this + 38);
      LimitedRepresentation = CDecorationPart::CreateLimitedRepresentation((CWbemClass *)((char *)this + 72), a2, v6);
      v11 = LimitedRepresentation;
      if ( LimitedRepresentation )
      {
        memcpy_0(
          LimitedRepresentation,
          *((const void **)this + 28),
          (unsigned int)*((_QWORD *)this + 53) + **((_DWORD **)this + 53) - (unsigned int)*((_QWORD *)this + 28));
        v18 = &v11[(unsigned int)*((_QWORD *)this + 53) + **((_DWORD **)this + 53) - *((_DWORD *)this + 56)];
        LODWORD(v21) = 0;
        if ( CClassAndMethods::CreateLimitedRepresentation(
               (CWbemClass *)((char *)this + 504),
               a2,
               v9 - (int)v18,
               v18,
               (int *)&v21) )
        {
          if ( (_DWORD)v21 )
          {
            *v6 &= ~0x40u;
            *v6 |= 0x40u;
          }
          v14 = (CWbemClass *)CWin32DefaultArena::WbemMemAlloc(0x360u);
          v21 = v14;
          if ( v14 )
            v15 = CWbemClass::CWbemClass(v14);
          else
            v15 = 0;
          if ( v15 )
          {
            v21 = v15;
            v20 = 1;
            (*(void (__fastcall **)(struct CWbemClass *, _BYTE *, _QWORD))(*(_QWORD *)v15 + 1152LL))(
              v15,
              v6,
              *((unsigned int *)this + 38));
            (*(void (__fastcall **)(struct CWbemClass *))(*(_QWORD *)v15 + 8LL))(v15);
            *a3 = v15;
            (*(void (__fastcall **)(struct CWbemClass *))(*(_QWORD *)v15 + 16LL))(v15);
            v21 = 0;
            OnDeleteObjIf<unsigned char *,CBlobControl,void (CBlobControl::*)(unsigned char *),&[thunk]: CBlobControl::`vcall'{24,{flat}}>::~OnDeleteObjIf<unsigned char *,CBlobControl,void (CBlobControl::*)(unsigned char *),&[thunk]: CBlobControl::`vcall'{24,{flat}}>((__int64)v19);
            return 0;
          }
          MemLogObject = GetMemLogObject();
          CMemoryLog::Write(MemLogObject, -2147217402);
          if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              235,
              WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids,
              2147749894LL);
          }
        }
        else
        {
          v13 = GetMemLogObject();
          CMemoryLog::Write(v13, -2147217402);
          if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              234,
              WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids,
              2147749894LL);
          }
        }
      }
      else
      {
        v12 = GetMemLogObject();
        CMemoryLog::Write(v12, -2147217402);
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            233,
            WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids,
            2147749894LL);
        }
      }
      OnDeleteObjIf<unsigned char *,CBlobControl,void (CBlobControl::*)(unsigned char *),&[thunk]: CBlobControl::`vcall'{24,{flat}}>::~OnDeleteObjIf<unsigned char *,CBlobControl,void (CBlobControl::*)(unsigned char *),&[thunk]: CBlobControl::`vcall'{24,{flat}}>((__int64)v19);
      return 2147749894LL;
    }
    v7 = GetMemLogObject();
    CMemoryLog::Write(v7, -2147217402);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 232, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids, 2147749894LL);
    }
    result = 2147749894LL;
  }
  catch ( CX_MemoryException )
  {
    v17 = GetMemLogObject();
    CMemoryLog::Write(v17, -2147217402);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 236, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids, 2147749894LL);
    }
    return 2147749894LL;
  }
  return result;
}

```

## disassembly

```asm
0x1800015a0  push    rbx
0x1800015a2  push    rsi
0x1800015a3  push    rdi
0x1800015a4  push    r12
0x1800015a6  push    r14
0x1800015a8  push    r15
0x1800015aa  sub     rsp, 68h
0x1800015ae  mov     r12, r8
0x1800015b1  mov     r15, rdx
0x1800015b4  mov     rsi, rcx
0x1800015b7  mov     rcx, [rcx+78h]
0x1800015bb  mov     rax, [rcx]
0x1800015be  mov     edx, [rsi+98h]
0x1800015c4  mov     rax, [rax+8]
0x1800015c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800015cd  mov     rbx, rax
0x1800015d0  test    rax, rax
0x1800015d3  jnz     short loc_18000162C
0x1800015d5  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800015db  mov     ebx, 80041006h
0x1800015e0  mov     edx, ebx
0x1800015e2  mov     rcx, rax
0x1800015e5  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800015eb  lea     rax, WPP_GLOBAL_Control
0x1800015f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800015f9  cmp     rcx, rax
0x1800015fc  jz      short loc_180001625
0x1800015fe  test    byte ptr [rcx+1Ch], 1
0x180001602  jz      short loc_180001625
0x180001604  cmp     byte ptr [rcx+19h], 2
0x180001608  jb      short loc_180001625
0x18000160a  mov     edx, 0E8h
0x18000160f  mov     r9d, 80041006h
0x180001615  lea     r8, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids
0x18000161c  mov     rcx, [rcx+10h]
0x180001620  call    WPP_SF_d
0x180001625  mov     eax, ebx
0x180001627  jmp     loc_1800018BD
0x18000162c  mov     rax, [rsi+78h]
0x180001630  mov     [rsp+98h+var_58], rax
0x180001635  mov     [rsp+98h+var_50], rbx
0x18000163a  mov     [rsp+98h+var_48], 0
0x18000163f  mov     r8d, [rsi+98h]; Size
0x180001646  xor     edx, edx; Val
0x180001648  mov     rcx, rbx; void *
0x18000164b  call    memset_0
0x180001650  mov     [rsp+98h+var_68], rbx
0x180001655  mov     edi, [rsi+98h]
0x18000165b  add     rdi, rbx
0x18000165e  mov     [rsp+98h+var_60], rdi
0x180001663  lea     rcx, [rsi+48h]; this
0x180001667  mov     r8, rbx; unsigned __int8 *
0x18000166a  mov     rdx, r15; struct CLimitationMapping *
0x18000166d  call    ?CreateLimitedRepresentation@CDecorationPart@@QEAAPEAEPEAVCLimitationMapping@@PEAE@Z; CDecorationPart::CreateLimitedRepresentation(CLimitationMapping *,uchar *)
0x180001672  mov     r14, rax
0x180001675  mov     [rsp+98h+var_68], rax
0x18000167a  test    rax, rax
0x18000167d  jnz     short loc_1800016E1
0x18000167f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180001685  mov     ebx, 80041006h
0x18000168a  mov     edx, ebx
0x18000168c  mov     rcx, rax
0x18000168f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180001695  lea     rax, WPP_GLOBAL_Control
0x18000169c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800016a3  cmp     rcx, rax
0x1800016a6  jz      short loc_1800016D0
0x1800016a8  test    byte ptr [rcx+1Ch], 1
0x1800016ac  jz      short loc_1800016D0
0x1800016ae  cmp     byte ptr [rcx+19h], 2
0x1800016b2  jb      short loc_1800016D0
0x1800016b4  mov     edx, 0E9h
0x1800016b9  mov     r9d, 80041006h
0x1800016bf  lea     r8, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids
0x1800016c6  mov     rcx, [rcx+10h]
0x1800016ca  call    WPP_SF_d
0x1800016cf  nop
0x1800016d0  lea     rcx, [rsp+98h+var_58]
0x1800016d5  call    ??1?$OnDeleteObjIf@PEAEVCBlobControl@@P81@EAAXPEAE@Z$1??_91@$BBI@AA@@QEAA@XZ; OnDeleteObjIf<uchar *,CBlobControl,void (CBlobControl::*)(uchar *),&[thunk]: CBlobControl::`vcall'{24,{flat}}>::~OnDeleteObjIf<uchar *,CBlobControl,void (CBlobControl::*)(uchar *),&[thunk]: CBlobControl::`vcall'{24,{flat}}>(void)
0x1800016da  mov     eax, ebx
0x1800016dc  jmp     loc_1800018BD
0x1800016e1  mov     rcx, [rsi+1A8h]
0x1800016e8  mov     rdx, [rsi+0E0h]; Src
0x1800016ef  mov     r8d, [rcx]
0x1800016f2  sub     r8d, edx
0x1800016f5  add     r8d, ecx; Size
0x1800016f8  mov     rcx, r14; void *
0x1800016fb  call    memcpy_0
0x180001700  mov     rcx, [rsi+1A8h]
0x180001707  mov     r9d, [rcx]
0x18000170a  sub     r9d, [rsi+0E0h]
0x180001711  add     r9d, ecx
0x180001714  add     r9, r14; unsigned __int8 *
0x180001717  mov     [rsp+98h+var_68], r9
0x18000171c  mov     dword ptr [rsp+98h+arg_18], 0
0x180001727  sub     edi, r9d
0x18000172a  lea     rcx, [rsi+1F8h]; this
0x180001731  lea     rax, [rsp+98h+arg_18]
0x180001739  mov     [rsp+98h+var_78], rax; int *
0x18000173e  mov     r8d, edi; int
0x180001741  mov     rdx, r15; struct CLimitationMapping *
0x180001744  call    ?CreateLimitedRepresentation@CClassAndMethods@@QEAAPEAEPEAVCLimitationMapping@@HPEAEAEAH@Z; CClassAndMethods::CreateLimitedRepresentation(CLimitationMapping *,int,uchar *,int &)
0x180001749  mov     [rsp+98h+var_68], rax
0x18000174e  test    rax, rax
0x180001751  jnz     short loc_1800017B5
0x180001753  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180001759  mov     ebx, 80041006h
0x18000175e  mov     edx, ebx
0x180001760  mov     rcx, rax
0x180001763  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180001769  lea     rax, WPP_GLOBAL_Control
0x180001770  mov     rcx, cs:WPP_GLOBAL_Control
0x180001777  cmp     rcx, rax
0x18000177a  jz      short loc_1800017A4
0x18000177c  test    byte ptr [rcx+1Ch], 1
0x180001780  jz      short loc_1800017A4
0x180001782  cmp     byte ptr [rcx+19h], 2
0x180001786  jb      short loc_1800017A4
0x180001788  mov     edx, 0EAh
0x18000178d  mov     r9d, 80041006h
0x180001793  lea     r8, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids
0x18000179a  mov     rcx, [rcx+10h]
0x18000179e  call    WPP_SF_d
0x1800017a3  nop
0x1800017a4  lea     rcx, [rsp+98h+var_58]
0x1800017a9  call    ??1?$OnDeleteObjIf@PEAEVCBlobControl@@P81@EAAXPEAE@Z$1??_91@$BBI@AA@@QEAA@XZ; OnDeleteObjIf<uchar *,CBlobControl,void (CBlobControl::*)(uchar *),&[thunk]: CBlobControl::`vcall'{24,{flat}}>::~OnDeleteObjIf<uchar *,CBlobControl,void (CBlobControl::*)(uchar *),&[thunk]: CBlobControl::`vcall'{24,{flat}}>(void)
0x1800017ae  mov     eax, ebx
0x1800017b0  jmp     loc_1800018BD
0x1800017b5  cmp     dword ptr [rsp+98h+arg_18], 0
0x1800017bd  jz      short loc_1800017C8
0x1800017bf  and     byte ptr [rbx], 0BFh
0x1800017c2  mov     al, [rbx]
0x1800017c4  or      al, 40h
0x1800017c6  mov     [rbx], al
0x1800017c8  mov     ecx, 360h
0x1800017cd  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800017d3  mov     [rsp+98h+arg_18], rax
0x1800017db  test    rax, rax
0x1800017de  jz      short loc_1800017ED
0x1800017e0  mov     rcx, rax; this
0x1800017e3  call    ??0CWbemClass@@QEAA@XZ; CWbemClass::CWbemClass(void)
0x1800017e8  mov     rdi, rax
0x1800017eb  jmp     short loc_1800017EF
0x1800017ed  xor     edi, edi
0x1800017ef  test    rdi, rdi
0x1800017f2  jnz     short loc_180001853
0x1800017f4  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800017fa  mov     ebx, 80041006h
0x1800017ff  mov     edx, ebx
0x180001801  mov     rcx, rax
0x180001804  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000180a  lea     rax, WPP_GLOBAL_Control
0x180001811  mov     rcx, cs:WPP_GLOBAL_Control
0x180001818  cmp     rcx, rax
0x18000181b  jz      short loc_180001845
0x18000181d  test    byte ptr [rcx+1Ch], 1
0x180001821  jz      short loc_180001845
0x180001823  cmp     byte ptr [rcx+19h], 2
0x180001827  jb      short loc_180001845
0x180001829  mov     edx, 0EBh
0x18000182e  mov     r9d, 80041006h
0x180001834  lea     r8, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids
0x18000183b  mov     rcx, [rcx+10h]
0x18000183f  call    WPP_SF_d
0x180001844  nop
0x180001845  lea     rcx, [rsp+98h+var_58]
0x18000184a  call    ??1?$OnDeleteObjIf@PEAEVCBlobControl@@P81@EAAXPEAE@Z$1??_91@$BBI@AA@@QEAA@XZ; OnDeleteObjIf<uchar *,CBlobControl,void (CBlobControl::*)(uchar *),&[thunk]: CBlobControl::`vcall'{24,{flat}}>::~OnDeleteObjIf<uchar *,CBlobControl,void (CBlobControl::*)(uchar *),&[thunk]: CBlobControl::`vcall'{24,{flat}}>(void)
0x18000184f  mov     eax, ebx
0x180001851  jmp     short loc_1800018BD
0x180001853  mov     [rsp+98h+arg_18], rdi
0x18000185b  mov     [rsp+98h+var_48], 1
0x180001860  mov     rax, [rdi]
0x180001863  mov     r8d, [rsi+98h]
0x18000186a  mov     rdx, rbx
0x18000186d  mov     rcx, rdi
0x180001870  mov     rax, [rax+480h]
0x180001877  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000187c  mov     rax, [rdi]
0x18000187f  mov     rcx, rdi
0x180001882  mov     rax, [rax+8]
0x180001886  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000188b  mov     [r12], rdi
0x18000188f  mov     rax, [rdi]
0x180001892  mov     rcx, rdi
0x180001895  mov     rax, [rax+10h]
0x180001899  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000189e  mov     [rsp+98h+arg_18], 0
0x1800018aa  lea     rcx, [rsp+98h+var_58]
0x1800018af  call    ??1?$OnDeleteObjIf@PEAEVCBlobControl@@P81@EAAXPEAE@Z$1??_91@$BBI@AA@@QEAA@XZ; OnDeleteObjIf<uchar *,CBlobControl,void (CBlobControl::*)(uchar *),&[thunk]: CBlobControl::`vcall'{24,{flat}}>::~OnDeleteObjIf<uchar *,CBlobControl,void (CBlobControl::*)(uchar *),&[thunk]: CBlobControl::`vcall'{24,{flat}}>(void)
0x1800018b4  xor     eax, eax
0x1800018b6  jmp     short loc_1800018BD
0x1800018b8  mov     eax, 80041006h
0x1800018bd  add     rsp, 68h
0x1800018c1  pop     r15
0x1800018c3  pop     r14
0x1800018c5  pop     r12
0x1800018c7  pop     rdi
0x1800018c8  pop     rsi
0x1800018c9  pop     rbx
0x1800018ca  retn
```
