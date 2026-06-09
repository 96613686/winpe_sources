# CQualifierSet::GetNames(long,tagSAFEARRAY * *)

- ea: `0x180008f60`
- end: `0x1800092ca`
- name: `?GetNames@CQualifierSet@@UEAAJJPEAPEAUtagSAFEARRAY@@@Z`
- size: `874`
- prototype: `__int64 __fastcall(CQualifierSet *__hidden this, int, struct tagSAFEARRAY **)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180008950`
- `0x180008f20`
- `0x180008f60`
- `0x1800097b0`
- `0x180009c0c`
- `0x180037120`
- `0x180050490`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x1800090ea`
- `wbemcomn!GetMemLogObject` at `0x18000912b`
- `wbemcomn!GetMemLogObject` at `0x1800091c5`
- `wbemcomn!GetMemLogObject` at `0x18000925b`
- `wbemcomn!GetMemLogObject` at `0x1800090ea`
- `wbemcomn!GetMemLogObject` at `0x18000912b`
- `wbemcomn!GetMemLogObject` at `0x1800091c5`
- `wbemcomn!GetMemLogObject` at `0x18000925b`
- `wbemcomn!??0CSafeArray@@QEAA@HHHH@Z` at `0x180009025`
- `wbemcomn!??0CSafeArray@@QEAA@HHHH@Z` at `0x180009025`
- `wbemcomn!??1CSafeArray@@QEAA@XZ` at `0x18000909d`
- `wbemcomn!??1CSafeArray@@QEAA@XZ` at `0x18000909d`
- `wbemcomn!?AddBSTR@CSafeArray@@QEAAHPEAG@Z` at `0x180009066`
- `wbemcomn!?AddBSTR@CSafeArray@@QEAAHPEAG@Z` at `0x180009066`
- `wbemcomn!?Empty@CSafeArray@@QEAAXXZ` at `0x18000902c`
- `wbemcomn!?GetArray@CSafeArray@@QEAAPEAUtagSAFEARRAY@@XZ` at `0x180009075`
- `wbemcomn!?GetArray@CSafeArray@@QEAAPEAUtagSAFEARRAY@@XZ` at `0x180009075`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800090fa`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180009136`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800091d5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000926b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800090fa`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180009136`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800091d5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000926b`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800090c0`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000916f`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800090c0`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000916f`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CQualifierSet::GetNames(CQualifierSet *this, int a2, struct tagSAFEARRAY **a3)
{
  __int64 v6; // rbx
  int v7; // edi
  int i; // edi
  __int64 result; // rax
  CMemoryLog *v10; // rax
  CMemoryLog *v11; // rax
  CMemoryLog *v12; // rax
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v14; // rax
  int v15; // [rsp+30h] [rbp-A8h] BYREF
  void *v16; // [rsp+34h] [rbp-A4h]
  int v17; // [rsp+40h] [rbp-98h]
  _BYTE v18[8]; // [rsp+48h] [rbp-90h] BYREF
  __int64 v19; // [rsp+50h] [rbp-88h]
  void (__fastcall *v20)(__int64); // [rsp+58h] [rbp-80h]
  char v21[8]; // [rsp+68h] [rbp-70h] BYREF
  __int64 v22; // [rsp+70h] [rbp-68h]
  void (__fastcall *v23)(__int64); // [rsp+78h] [rbp-60h]
  _BYTE v24[88]; // [rsp+80h] [rbp-58h] BYREF
  __int64 v25; // [rsp+F8h] [rbp+20h] BYREF

  try
  {
    v6 = *((_QWORD *)this + 5);
    v25 = v6;
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v6 + 280LL))(v6, 0);
    if ( a3 )
    {
      *a3 = 0;
      if ( (a2 & 0xFFFFFFCF) != 0 || a2 == 48 )
      {
        MemLogObject = GetMemLogObject();
        CMemoryLog::Write(MemLogObject, -2147217400);
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            98,
            WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids,
            2147749896LL);
        }
        CWbemObject::CLock::~CLock((CWbemObject::CLock *)&v25);
        result = 2147749896LL;
      }
      else if ( (unsigned int)CQualifierSet::SelfRebase(this) )
      {
        v15 = 0;
        v16 = 0;
        MakeObjGuard<CFixedBSTRArray,void (CFixedBSTRArray::*)(void)>(v18, &v15);
        v7 = CQualifierSet::EnumQualifiers(this, a2, 0, (struct CFixedBSTRArray *)&v15);
        if ( v7 < 0 )
        {
          v11 = GetMemLogObject();
          CMemoryLog::Write(v11, v7);
          if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              100,
              WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids,
              (unsigned int)v7);
          }
          if ( !v18[0] )
            v20(v19);
          CWin32DefaultArena::WbemMemFree(v16);
          (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v6 + 288LL))(v6, 0);
          result = (unsigned int)v7;
        }
        else
        {
          CSafeArray::CSafeArray((CSafeArray *)v24, 8, 1, v15, 32);
          MakeObjGuard<CSafeArray,void (CSafeArray::*)(void)>(v21, v24, CSafeArray::Empty);
          for ( i = 0; ; ++i )
          {
            v17 = i;
            if ( i >= v15 )
              break;
            CSafeArray::AddBSTR((CSafeArray *)v24, *((unsigned __int16 **)v16 + i));
          }
          v21[0] = 1;
          *a3 = CSafeArray::GetArray((CSafeArray *)v24);
          if ( !v21[0] )
            v23(v22);
          CSafeArray::~CSafeArray((CSafeArray *)v24);
          if ( !v18[0] )
            v20(v19);
          CWin32DefaultArena::WbemMemFree(v16);
          (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v6 + 288LL))(v6, 0);
          result = 0;
        }
      }
      else
      {
        v12 = GetMemLogObject();
        CMemoryLog::Write(v12, -2147217359);
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            99,
            WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids,
            2147749937LL);
        }
        CWbemObject::CLock::~CLock((CWbemObject::CLock *)&v25);
        result = 2147749937LL;
      }
    }
    else
    {
      v10 = GetMemLogObject();
      CMemoryLog::Write(v10, -2147217400);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 97, WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids, 2147749896LL);
      }
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v6 + 288LL))(v6, 0);
      result = 2147749896LL;
    }
  }
  catch ( CX_MemoryException )
  {
    v14 = GetMemLogObject();
    CMemoryLog::Write(v14, -2147217402);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 101, WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids, 2147749894LL);
    }
    return 2147749894LL;
  }
  return result;
}

```

## disassembly

```asm
0x180008f60  mov     rax, rsp
0x180008f63  push    rbx
0x180008f64  push    rsi
0x180008f65  push    rdi
0x180008f66  push    r14
0x180008f68  sub     rsp, 0B8h
0x180008f6f  mov     rsi, r8
0x180008f72  mov     edi, edx
0x180008f74  mov     r14, rcx
0x180008f77  mov     rbx, [rcx+28h]
0x180008f7b  mov     [rax+20h], rbx
0x180008f7f  mov     rax, [rbx]
0x180008f82  xor     edx, edx
0x180008f84  mov     rcx, rbx
0x180008f87  mov     rax, [rax+118h]
0x180008f8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f93  nop
0x180008f94  test    rsi, rsi
0x180008f97  jz      loc_1800090EA
0x180008f9d  mov     qword ptr [rsi], 0
0x180008fa4  test    edi, 0FFFFFFCFh
0x180008faa  jnz     loc_18000925B
0x180008fb0  cmp     edi, 30h ; '0'
0x180008fb3  jz      loc_18000925B
0x180008fb9  mov     rcx, r14; this
0x180008fbc  call    ?SelfRebase@CQualifierSet@@QEAAHXZ; CQualifierSet::SelfRebase(void)
0x180008fc1  test    eax, eax
0x180008fc3  jz      loc_1800091C5
0x180008fc9  mov     [rsp+0D8h+var_A8], 0
0x180008fd1  mov     [rsp+0D8h+var_A4], 0
0x180008fda  lea     rdx, [rsp+0D8h+var_A8]
0x180008fdf  lea     rcx, [rsp+0D8h+var_90]
0x180008fe4  call    ??$MakeObjGuard@VCFixedBSTRArray@@P81@EAAXXZ@@YA?AV?$ObjScopeGuardImpl0@VCFixedBSTRArray@@P81@EAAXXZ@@AEAVCFixedBSTRArray@@P81@EAAXXZ@Z; MakeObjGuard<CFixedBSTRArray,void (CFixedBSTRArray::*)(void)>(CFixedBSTRArray &,void (CFixedBSTRArray::*)(void))
0x180008fe9  nop
0x180008fea  mov     dl, dil; unsigned __int8
0x180008fed  lea     r9, [rsp+0D8h+var_A8]; struct CFixedBSTRArray *
0x180008ff2  xor     r8d, r8d; unsigned __int8
0x180008ff5  mov     rcx, r14; this
0x180008ff8  call    ?EnumQualifiers@CQualifierSet@@QEAAJEEAEAVCFixedBSTRArray@@@Z; CQualifierSet::EnumQualifiers(uchar,uchar,CFixedBSTRArray &)
0x180008ffd  mov     edi, eax
0x180008fff  test    eax, eax
0x180009001  js      loc_18000912B
0x180009007  mov     [rsp+0D8h+var_B8], 20h ; ' '
0x18000900f  mov     r9d, [rsp+0D8h+var_A8]
0x180009014  mov     edx, 8
0x180009019  lea     r8d, [rdx-7]
0x18000901d  lea     rcx, [rsp+0D8h+var_58]
0x180009025  call    cs:__imp_??0CSafeArray@@QEAA@HHHH@Z; CSafeArray::CSafeArray(int,int,int,int)
0x18000902b  nop
0x18000902c  mov     r8, cs:__imp_?Empty@CSafeArray@@QEAAXXZ; CSafeArray::Empty(void)
0x180009033  lea     rdx, [rsp+0D8h+var_58]
0x18000903b  lea     rcx, [rsp+0D8h+var_70]
0x180009040  call    ??$MakeObjGuard@VCSafeArray@@P81@EAAXXZ@@YA?AV?$ObjScopeGuardImpl0@VCSafeArray@@P81@EAAXXZ@@AEAVCSafeArray@@P81@EAAXXZ@Z; MakeObjGuard<CSafeArray,void (CSafeArray::*)(void)>(CSafeArray &,void (CSafeArray::*)(void))
0x180009045  nop
0x180009046  xor     edi, edi
0x180009048  mov     [rsp+0D8h+var_98], edi
0x18000904c  lea     rcx, [rsp+0D8h+var_58]
0x180009054  cmp     edi, [rsp+0D8h+var_A8]
0x180009058  jge     short loc_180009070
0x18000905a  movsxd  rax, edi
0x18000905d  mov     rdx, [rsp+0D8h+var_A4]
0x180009062  mov     rdx, [rdx+rax*8]
0x180009066  call    cs:__imp_?AddBSTR@CSafeArray@@QEAAHPEAG@Z; CSafeArray::AddBSTR(ushort *)
0x18000906c  inc     edi
0x18000906e  jmp     short loc_180009048
0x180009070  mov     [rsp+0D8h+var_70], 1
0x180009075  call    cs:__imp_?GetArray@CSafeArray@@QEAAPEAUtagSAFEARRAY@@XZ; CSafeArray::GetArray(void)
0x18000907b  mov     [rsi], rax
0x18000907e  cmp     [rsp+0D8h+var_70], 0
0x180009083  jnz     short loc_180009095
0x180009085  mov     rcx, [rsp+0D8h+var_68]
0x18000908a  mov     rax, [rsp+0D8h+var_60]
0x18000908f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009094  nop
0x180009095  lea     rcx, [rsp+0D8h+var_58]
0x18000909d  call    cs:__imp_??1CSafeArray@@QEAA@XZ; CSafeArray::~CSafeArray(void)
0x1800090a3  nop
0x1800090a4  cmp     [rsp+0D8h+var_90], 0
0x1800090a9  jnz     short loc_1800090BB
0x1800090ab  mov     rcx, [rsp+0D8h+var_88]
0x1800090b0  mov     rax, [rsp+0D8h+var_80]
0x1800090b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090ba  nop
0x1800090bb  mov     rcx, [rsp+0D8h+var_A4]
0x1800090c0  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800090c6  nop
0x1800090c7  mov     rax, [rbx]
0x1800090ca  xor     edx, edx
0x1800090cc  mov     rcx, rbx
0x1800090cf  mov     rax, [rax+120h]
0x1800090d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090db  xor     eax, eax
0x1800090dd  add     rsp, 0B8h
0x1800090e4  pop     r14
0x1800090e6  pop     rdi
0x1800090e7  pop     rsi
0x1800090e8  pop     rbx
0x1800090e9  retn
0x1800090ea  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800090f0  mov     edi, 80041008h
0x1800090f5  mov     edx, edi
0x1800090f7  mov     rcx, rax
0x1800090fa  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180009100  lea     rax, WPP_GLOBAL_Control
0x180009107  mov     rcx, cs:WPP_GLOBAL_Control
0x18000910e  cmp     rcx, rax
0x180009111  jnz     short loc_180009191
0x180009113  mov     rcx, [rbx]
0x180009116  mov     rax, [rcx+120h]
0x18000911d  xor     edx, edx
0x18000911f  mov     rcx, rbx
0x180009122  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009127  mov     eax, edi
0x180009129  jmp     short loc_1800090DD
0x18000912b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180009131  mov     edx, edi
0x180009133  mov     rcx, rax
0x180009136  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000913c  lea     rax, WPP_GLOBAL_Control
0x180009143  mov     rcx, cs:WPP_GLOBAL_Control
0x18000914a  cmp     rcx, rax
0x18000914d  jnz     loc_18000922A
0x180009153  cmp     [rsp+0D8h+var_90], 0
0x180009158  jnz     short loc_18000916A
0x18000915a  mov     rcx, [rsp+0D8h+var_88]
0x18000915f  mov     rax, [rsp+0D8h+var_80]
0x180009164  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009169  nop
0x18000916a  mov     rcx, [rsp+0D8h+var_A4]
0x18000916f  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180009175  nop
0x180009176  mov     rax, [rbx]
0x180009179  xor     edx, edx
0x18000917b  mov     rcx, rbx
0x18000917e  mov     rax, [rax+120h]
0x180009185  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000918a  mov     eax, edi
0x18000918c  jmp     loc_1800090DD
0x180009191  test    byte ptr [rcx+1Ch], 1
0x180009195  jz      loc_180009113
0x18000919b  cmp     byte ptr [rcx+19h], 2
0x18000919f  jb      loc_180009113
0x1800091a5  mov     edx, 61h ; 'a'
0x1800091aa  mov     r9d, 80041008h
0x1800091b0  lea     r8, WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids
0x1800091b7  mov     rcx, [rcx+10h]
0x1800091bb  call    WPP_SF_d
0x1800091c0  jmp     loc_180009113
0x1800091c5  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800091cb  mov     ebx, 80041031h
0x1800091d0  mov     edx, ebx
0x1800091d2  mov     rcx, rax
0x1800091d5  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800091db  lea     rax, WPP_GLOBAL_Control
0x1800091e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800091e9  cmp     rcx, rax
0x1800091ec  jz      short loc_180009216
0x1800091ee  test    byte ptr [rcx+1Ch], 1
0x1800091f2  jz      short loc_180009216
0x1800091f4  cmp     byte ptr [rcx+19h], 2
0x1800091f8  jb      short loc_180009216
0x1800091fa  mov     edx, 63h ; 'c'
0x1800091ff  mov     r9d, 80041031h
0x180009205  lea     r8, WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids
0x18000920c  mov     rcx, [rcx+10h]
0x180009210  call    WPP_SF_d
0x180009215  nop
0x180009216  lea     rcx, [rsp+0D8h+arg_18]; this
0x18000921e  call    ??1CLock@CWbemObject@@QEAA@XZ; CWbemObject::CLock::~CLock(void)
0x180009223  mov     eax, ebx
0x180009225  jmp     loc_1800090DD
0x18000922a  test    byte ptr [rcx+1Ch], 1
0x18000922e  jz      loc_180009153
0x180009234  cmp     byte ptr [rcx+19h], 2
0x180009238  jb      loc_180009153
0x18000923e  mov     edx, 64h ; 'd'
0x180009243  mov     r9d, edi
0x180009246  lea     r8, WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids
0x18000924d  mov     rcx, [rcx+10h]
0x180009251  call    WPP_SF_d
0x180009256  jmp     loc_180009153
0x18000925b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180009261  mov     edi, 80041008h
0x180009266  mov     edx, edi
0x180009268  mov     rcx, rax
0x18000926b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180009271  lea     rax, WPP_GLOBAL_Control
0x180009278  mov     rcx, cs:WPP_GLOBAL_Control
0x18000927f  cmp     rcx, rax
0x180009282  jz      short loc_1800092AC
0x180009284  test    byte ptr [rcx+1Ch], 1
0x180009288  jz      short loc_1800092AC
0x18000928a  cmp     byte ptr [rcx+19h], 2
0x18000928e  jb      short loc_1800092AC
0x180009290  mov     edx, 62h ; 'b'
0x180009295  mov     r9d, 80041008h
0x18000929b  lea     r8, WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids
0x1800092a2  mov     rcx, [rcx+10h]
0x1800092a6  call    WPP_SF_d
0x1800092ab  nop
0x1800092ac  lea     rcx, [rsp+0D8h+arg_18]; this
0x1800092b4  call    ??1CLock@CWbemObject@@QEAA@XZ; CWbemObject::CLock::~CLock(void)
0x1800092b9  mov     eax, edi
0x1800092bb  jmp     loc_1800090DD
0x1800092c0  mov     eax, 80041006h
0x1800092c5  jmp     loc_1800090DD
```
