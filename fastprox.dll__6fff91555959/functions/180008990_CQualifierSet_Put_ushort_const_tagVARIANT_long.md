# CQualifierSet::Put(ushort const *,tagVARIANT *,long)

- ea: `0x180008990`
- end: `0x180008f14`
- name: `?Put@CQualifierSet@@UEAAJPEBGPEAUtagVARIANT@@J@Z`
- size: `1412`
- prototype: `__int64 __fastcall(CQualifierSet *__hidden this, const unsigned __int16 *, struct tagVARIANT *, int)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180007530`
- `0x180008910`
- `0x180008990`
- `0x180008f20`
- `0x18000e720`
- `0x180037120`
- `0x180050490`
- `0x1800919b0`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180008bca`
- `wbemcomn!GetMemLogObject` at `0x180008bdd`
- `wbemcomn!GetMemLogObject` at `0x180008c22`
- `wbemcomn!GetMemLogObject` at `0x180008c6a`
- `wbemcomn!GetMemLogObject` at `0x180008ccc`
- `wbemcomn!GetMemLogObject` at `0x180008d62`
- `wbemcomn!GetMemLogObject` at `0x180008dc4`
- `wbemcomn!GetMemLogObject` at `0x180008e26`
- `wbemcomn!GetMemLogObject` at `0x180008bca`
- `wbemcomn!GetMemLogObject` at `0x180008bdd`
- `wbemcomn!GetMemLogObject` at `0x180008c22`
- `wbemcomn!GetMemLogObject` at `0x180008c6a`
- `wbemcomn!GetMemLogObject` at `0x180008ccc`
- `wbemcomn!GetMemLogObject` at `0x180008d62`
- `wbemcomn!GetMemLogObject` at `0x180008dc4`
- `wbemcomn!GetMemLogObject` at `0x180008e26`
- `wbemcomn!?SetVariant@CVar@@QEAAHPEAUtagVARIANT@@H@Z` at `0x180008a49`
- `wbemcomn!?SetVariant@CVar@@QEAAHPEAUtagVARIANT@@H@Z` at `0x180008a49`
- `wbemcomn!?IsDataNull@CVar@@QEAAHXZ` at `0x180008a54`
- `wbemcomn!?IsDataNull@CVar@@QEAAHXZ` at `0x180008a54`
- `wbemcomn!?GetOleType@CVar@@QEAAHXZ` at `0x180008ac2`
- `wbemcomn!?GetOleType@CVar@@QEAAHXZ` at `0x180008ac2`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x180008a34`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x180008a34`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180008bd5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180008bed`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180008c32`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180008c7a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180008cdc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180008d72`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180008dd4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180008e36`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180008bd5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180008bed`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180008c32`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180008c7a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180008cdc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180008d72`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180008dd4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180008e36`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180008b8e`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180008e7c`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180008b8e`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180008e7c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CQualifierSet::Put(CQualifierSet *this, const unsigned __int16 *a2, struct tagVARIANT *a3, int a4)
{
  __int64 v8; // rdi
  struct CFastHeap *v9; // rbx
  unsigned int OleType; // eax
  int v11; // ebx
  unsigned int v12; // ebx
  __int64 result; // rax
  CMemoryLog *v14; // rax
  CMemoryLog *v15; // rax
  CMemoryLog *v16; // rax
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v18; // rax
  CMemoryLog *v19; // rax
  CMemoryLog *v20; // rax
  CMemoryLog *v21; // rax
  CMemoryLog *v22; // rax
  CMemoryLog *v23; // rax
  unsigned int v24; // [rsp+30h] [rbp-A8h] BYREF
  __int64 v25; // [rsp+38h] [rbp-A0h] BYREF
  _QWORD v26[2]; // [rsp+40h] [rbp-98h] BYREF
  unsigned int v27; // [rsp+50h] [rbp-88h]
  _QWORD v28[2]; // [rsp+58h] [rbp-80h] BYREF
  int v29; // [rsp+68h] [rbp-70h]
  _BYTE v30[32]; // [rsp+70h] [rbp-68h] BYREF
  _DWORD v31[6]; // [rsp+90h] [rbp-48h] BYREF

  try
  {
    v8 = *((_QWORD *)this + 5);
    v25 = v8;
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v8 + 280LL))(v8, 0);
    if ( a2 && a3 )
    {
      if ( (a4 & 0xFFFFFF6C) != 0 )
      {
        MemLogObject = GetMemLogObject();
        CMemoryLog::Write(MemLogObject, -2147217400);
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            79,
            WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids,
            2147749896LL);
        }
        goto LABEL_26;
      }
      if ( !(unsigned int)CBasicQualifierSet::IsValidQualifierType(a3->vt) )
      {
        v18 = GetMemLogObject();
        CMemoryLog::Write(v18, -2147217367);
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            80,
            WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids,
            2147749929LL);
        }
        CWbemObject::CLock::~CLock((CWbemObject::CLock *)&v25);
        return 2147749929LL;
      }
      if ( *a2 != 95 )
      {
        if ( !(unsigned int)CQualifierSet::SelfRebase(this) )
        {
          v19 = GetMemLogObject();
          CMemoryLog::Write(v19, -2147217359);
          if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              82,
              WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids,
              2147749937LL);
          }
          CWbemObject::CLock::~CLock((CWbemObject::CLock *)&v25);
          return 2147749937LL;
        }
        if ( (a4 & 0x60) == 0 )
        {
          CVar::CVar((CVar *)v30);
          CVar::SetVariant((CVar *)v30, a3, 1);
          if ( !CVar::IsDataNull((CVar *)v30) )
          {
            v31[0] = 0;
            v26[0] = &CStaticPtr::`vftable';
            v26[1] = v31;
            v9 = (struct CFastHeap *)*((_QWORD *)this + 3);
            v28[0] = &CShiftedPtr::`vftable';
            v28[1] = v26;
            v29 = 4;
            v24 = 0;
            OleType = CVar::GetOleType((CVar *)v30);
            v11 = CUntypedValue::LoadFromCVar((struct CPtrSource *)v28, (struct CVar *)v30, OleType, v9, &v24, 0);
            if ( v11 >= 0 )
            {
              v12 = v24;
              if ( v24 == 4095 )
              {
                v11 = -2147217403;
              }
              else
              {
                v27 = v24;
                *(_DWORD *)(*(__int64 (__fastcall **)(_QWORD *))v26[0])(v26) = v12;
                if ( (unsigned int)CQualifierSet::SelfRebase(this) )
                {
                  v11 = CQualifierSet::SetQualifierValue(this, a2, a4, (struct CTypedValue *)v31, 1, 1);
                  (*(void (__fastcall **)(CQualifierSet *))(*(_QWORD *)this + 72LL))(this);
                  if ( v11 >= 0 )
                    goto LABEL_14;
                }
                else
                {
                  v11 = -2147217359;
                }
              }
            }
            v14 = GetMemLogObject();
            CMemoryLog::Write(v14, v11);
LABEL_14:
            if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                85,
                WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids,
                (unsigned int)v11);
            }
            CVar::~CVar((CVar *)v30);
            (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v8 + 288LL))(v8, 0);
            return (unsigned int)v11;
          }
          v21 = GetMemLogObject();
          CMemoryLog::Write(v21, -2147217400);
          if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              84,
              WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids,
              2147749896LL);
          }
          CVar::~CVar((CVar *)v30);
          CWbemObject::CLock::~CLock((CWbemObject::CLock *)&v25);
          return 2147749896LL;
        }
        v20 = GetMemLogObject();
        CMemoryLog::Write(v20, -2147217400);
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            83,
            WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids,
            2147749896LL);
        }
LABEL_26:
        CWbemObject::CLock::~CLock((CWbemObject::CLock *)&v25);
        return 2147749896LL;
      }
      v15 = GetMemLogObject();
      CMemoryLog::Write(v15, -2147217400);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids, 2147749896LL);
      }
    }
    else
    {
      v16 = GetMemLogObject();
      CMemoryLog::Write(v16, -2147217400);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids, 2147749896LL);
      }
    }
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v8 + 288LL))(v8, 0);
    result = 2147749896LL;
  }
  catch ( CX_MemoryException )
  {
    v22 = GetMemLogObject();
    CMemoryLog::Write(v22, -2147217402);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids, 2147749894LL);
    }
    return 2147749894LL;
  }
  catch ( CX_Exception )
  {
    v23 = GetMemLogObject();
    CMemoryLog::Write(v23, -2147217407);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids, 2147749889LL);
    }
    return 2147749889LL;
  }
  v8 = *((_QWORD *)this + 5);
}

```

## disassembly

```asm
0x180008990  push    rbx
0x180008992  push    rsi
0x180008993  push    rdi
0x180008994  push    r14
0x180008996  push    r15
0x180008998  sub     rsp, 0B0h
0x18000899f  mov     rax, cs:__security_cookie
0x1800089a6  xor     rax, rsp
0x1800089a9  mov     [rsp+0D8h+var_30], rax
0x1800089b1  mov     r14d, r9d
0x1800089b4  mov     rbx, r8
0x1800089b7  mov     r15, rdx
0x1800089ba  mov     rsi, rcx
0x1800089bd  mov     rdi, [rcx+28h]
0x1800089c1  mov     [rsp+0D8h+var_A0], rdi
0x1800089c6  mov     rax, [rdi]
0x1800089c9  xor     edx, edx
0x1800089cb  mov     rcx, rdi
0x1800089ce  mov     rax, [rax+118h]
0x1800089d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089da  nop
0x1800089db  test    r15, r15
0x1800089de  jz      loc_180008C22
0x1800089e4  test    rbx, rbx
0x1800089e7  jz      loc_180008C22
0x1800089ed  test    r14d, 0FFFFFF6Ch
0x1800089f4  jnz     loc_180008C6A
0x1800089fa  movzx   ecx, word ptr [rbx]; unsigned __int16
0x1800089fd  call    ?IsValidQualifierType@CBasicQualifierSet@@SAHG@Z; CBasicQualifierSet::IsValidQualifierType(ushort)
0x180008a02  test    eax, eax
0x180008a04  jz      loc_180008CCC
0x180008a0a  cmp     word ptr [r15], 5Fh ; '_'
0x180008a0f  jz      loc_180008BDD
0x180008a15  mov     rcx, rsi; this
0x180008a18  call    ?SelfRebase@CQualifierSet@@QEAAHXZ; CQualifierSet::SelfRebase(void)
0x180008a1d  test    eax, eax
0x180008a1f  jz      loc_180008D62
0x180008a25  test    r14b, 60h
0x180008a29  jnz     loc_180008DC4
0x180008a2f  lea     rcx, [rsp+0D8h+var_68]
0x180008a34  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x180008a3a  nop
0x180008a3b  mov     r8d, 1
0x180008a41  mov     rdx, rbx
0x180008a44  lea     rcx, [rsp+0D8h+var_68]
0x180008a49  call    cs:__imp_?SetVariant@CVar@@QEAAHPEAUtagVARIANT@@H@Z; CVar::SetVariant(tagVARIANT *,int)
0x180008a4f  lea     rcx, [rsp+0D8h+var_68]
0x180008a54  call    cs:__imp_?IsDataNull@CVar@@QEAAHXZ; CVar::IsDataNull(void)
0x180008a5a  test    eax, eax
0x180008a5c  jnz     loc_180008E26
0x180008a62  mov     [rsp+0D8h+var_48], eax
0x180008a69  lea     rcx, ??_7CPtrSource@@6B@; const CPtrSource::`vftable'
0x180008a70  mov     [rsp+0D8h+var_98], rcx
0x180008a75  lea     rax, ??_7CStaticPtr@@6B@; const CStaticPtr::`vftable'
0x180008a7c  mov     [rsp+0D8h+var_98], rax
0x180008a81  lea     rax, [rsp+0D8h+var_48]
0x180008a89  mov     [rsp+0D8h+var_90], rax
0x180008a8e  mov     rbx, [rsi+18h]
0x180008a92  mov     [rsp+0D8h+var_80], rcx
0x180008a97  lea     rax, ??_7CShiftedPtr@@6B@; const CShiftedPtr::`vftable'
0x180008a9e  mov     [rsp+0D8h+var_80], rax
0x180008aa3  lea     rax, [rsp+0D8h+var_98]
0x180008aa8  mov     [rsp+0D8h+var_78], rax
0x180008aad  mov     [rsp+0D8h+var_70], 4
0x180008ab5  mov     [rsp+0D8h+var_A8], 0
0x180008abd  lea     rcx, [rsp+0D8h+var_68]
0x180008ac2  call    cs:__imp_?GetOleType@CVar@@QEAAHXZ; CVar::GetOleType(void)
0x180008ac8  mov     r8d, eax; unsigned int
0x180008acb  mov     [rsp+0D8h+var_B0], 0; int
0x180008ad3  lea     rax, [rsp+0D8h+var_A8]
0x180008ad8  mov     [rsp+0D8h+var_B8], rax; unsigned int *
0x180008add  mov     r9, rbx; struct CFastHeap *
0x180008ae0  lea     rdx, [rsp+0D8h+var_68]; struct CVar *
0x180008ae5  lea     rcx, [rsp+0D8h+var_80]; struct CPtrSource *
0x180008aea  call    ?LoadFromCVar@CUntypedValue@@SAJPEAVCPtrSource@@AEAVCVar@@KPEAVCFastHeap@@AEAKH@Z; CUntypedValue::LoadFromCVar(CPtrSource *,CVar &,ulong,CFastHeap *,ulong &,int)
0x180008aef  mov     ebx, eax
0x180008af1  test    eax, eax
0x180008af3  js      loc_180008BCA
0x180008af9  mov     ebx, [rsp+0D8h+var_A8]
0x180008afd  cmp     ebx, 0FFFh
0x180008b03  jz      loc_180008E94
0x180008b09  mov     [rsp+0D8h+var_88], ebx
0x180008b0d  mov     rax, [rsp+0D8h+var_98]
0x180008b12  lea     rcx, [rsp+0D8h+var_98]
0x180008b17  mov     rax, [rax]
0x180008b1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b1f  mov     [rax], ebx
0x180008b21  mov     rcx, rsi; this
0x180008b24  call    ?SelfRebase@CQualifierSet@@QEAAHXZ; CQualifierSet::SelfRebase(void)
0x180008b29  test    eax, eax
0x180008b2b  jz      loc_180008E9E
0x180008b31  mov     [rsp+0D8h+var_B0], 1; int
0x180008b39  mov     dword ptr [rsp+0D8h+var_B8], 1; int
0x180008b41  lea     r9, [rsp+0D8h+var_48]; struct CTypedValue *
0x180008b49  mov     r8b, r14b; unsigned __int8
0x180008b4c  mov     rdx, r15; unsigned __int16 *
0x180008b4f  mov     rcx, rsi; this
0x180008b52  call    ?SetQualifierValue@CQualifierSet@@QEAAJPEBGEPEAVCTypedValue@@HH@Z; CQualifierSet::SetQualifierValue(ushort const *,uchar,CTypedValue *,int,int)
0x180008b57  mov     ebx, eax
0x180008b59  mov     rax, [rsi]
0x180008b5c  mov     rcx, rsi
0x180008b5f  mov     rax, [rax+48h]
0x180008b63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b68  test    ebx, ebx
0x180008b6a  js      short loc_180008BCA
0x180008b6c  lea     rax, WPP_GLOBAL_Control
0x180008b73  mov     rcx, cs:WPP_GLOBAL_Control
0x180008b7a  cmp     rcx, rax
0x180008b7d  jz      short loc_180008B89
0x180008b7f  test    byte ptr [rcx+1Ch], 1
0x180008b83  jnz     loc_180008EA8
0x180008b89  lea     rcx, [rsp+0D8h+var_68]
0x180008b8e  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x180008b94  nop
0x180008b95  mov     rcx, [rdi]
0x180008b98  mov     rax, [rcx+120h]
0x180008b9f  xor     edx, edx
0x180008ba1  mov     rcx, rdi
0x180008ba4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ba9  mov     eax, ebx
0x180008bab  mov     rcx, [rsp+0D8h+var_30]
0x180008bb3  xor     rcx, rsp; StackCookie
0x180008bb6  call    __security_check_cookie
0x180008bbb  add     rsp, 0B0h
0x180008bc2  pop     r15
0x180008bc4  pop     r14
0x180008bc6  pop     rdi
0x180008bc7  pop     rsi
0x180008bc8  pop     rbx
0x180008bc9  retn
0x180008bca  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180008bd0  mov     edx, ebx
0x180008bd2  mov     rcx, rax
0x180008bd5  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180008bdb  jmp     short loc_180008B6C
0x180008bdd  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180008be3  mov     ebx, 80041008h
0x180008be8  mov     edx, ebx
0x180008bea  mov     rcx, rax
0x180008bed  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180008bf3  lea     rax, WPP_GLOBAL_Control
0x180008bfa  mov     rcx, cs:WPP_GLOBAL_Control
0x180008c01  cmp     rcx, rax
0x180008c04  jnz     loc_180008D2E
0x180008c0a  mov     rax, [rdi]
0x180008c0d  xor     edx, edx
0x180008c0f  mov     rcx, rdi
0x180008c12  mov     rax, [rax+120h]
0x180008c19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c1e  mov     eax, ebx
0x180008c20  jmp     short loc_180008BAB
0x180008c22  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180008c28  mov     ebx, 80041008h
0x180008c2d  mov     edx, ebx
0x180008c2f  mov     rcx, rax
0x180008c32  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180008c38  lea     rax, WPP_GLOBAL_Control
0x180008c3f  mov     rcx, cs:WPP_GLOBAL_Control
0x180008c46  cmp     rcx, rax
0x180008c49  jnz     loc_180008ECF
0x180008c4f  mov     rax, [rdi]
0x180008c52  xor     edx, edx
0x180008c54  mov     rcx, rdi
0x180008c57  mov     rax, [rax+120h]
0x180008c5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c63  mov     eax, ebx
0x180008c65  jmp     loc_180008BAB
0x180008c6a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180008c70  mov     ebx, 80041008h
0x180008c75  mov     edx, ebx
0x180008c77  mov     rcx, rax
0x180008c7a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180008c80  lea     rax, WPP_GLOBAL_Control
0x180008c87  mov     rcx, cs:WPP_GLOBAL_Control
0x180008c8e  cmp     rcx, rax
0x180008c91  jz      short loc_180008CBB
0x180008c93  test    byte ptr [rcx+1Ch], 1
0x180008c97  jz      short loc_180008CBB
0x180008c99  cmp     byte ptr [rcx+19h], 2
0x180008c9d  jb      short loc_180008CBB
0x180008c9f  mov     edx, 4Fh ; 'O'
0x180008ca4  mov     r9d, 80041008h
0x180008caa  lea     r8, WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids
0x180008cb1  mov     rcx, [rcx+10h]
0x180008cb5  call    WPP_SF_d
0x180008cba  nop
0x180008cbb  lea     rcx, [rsp+0D8h+var_A0]; this
0x180008cc0  call    ??1CLock@CWbemObject@@QEAA@XZ; CWbemObject::CLock::~CLock(void)
0x180008cc5  mov     eax, ebx
0x180008cc7  jmp     loc_180008BAB
0x180008ccc  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180008cd2  mov     ebx, 80041029h
0x180008cd7  mov     edx, ebx
0x180008cd9  mov     rcx, rax
0x180008cdc  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180008ce2  lea     rax, WPP_GLOBAL_Control
0x180008ce9  mov     rcx, cs:WPP_GLOBAL_Control
0x180008cf0  cmp     rcx, rax
0x180008cf3  jz      short loc_180008D1D
0x180008cf5  test    byte ptr [rcx+1Ch], 1
0x180008cf9  jz      short loc_180008D1D
0x180008cfb  cmp     byte ptr [rcx+19h], 2
0x180008cff  jb      short loc_180008D1D
0x180008d01  mov     edx, 50h ; 'P'
0x180008d06  mov     r9d, 80041029h
0x180008d0c  lea     r8, WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids
0x180008d13  mov     rcx, [rcx+10h]
0x180008d17  call    WPP_SF_d
0x180008d1c  nop
0x180008d1d  lea     rcx, [rsp+0D8h+var_A0]; this
0x180008d22  call    ??1CLock@CWbemObject@@QEAA@XZ; CWbemObject::CLock::~CLock(void)
0x180008d27  mov     eax, ebx
0x180008d29  jmp     loc_180008BAB
0x180008d2e  test    byte ptr [rcx+1Ch], 1
0x180008d32  jz      loc_180008C0A
0x180008d38  cmp     byte ptr [rcx+19h], 2
0x180008d3c  jb      loc_180008C0A
0x180008d42  mov     edx, 51h ; 'Q'
0x180008d47  mov     r9d, 80041008h
0x180008d4d  lea     r8, WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids
0x180008d54  mov     rcx, [rcx+10h]
0x180008d58  call    WPP_SF_d
0x180008d5d  jmp     loc_180008C0A
0x180008d62  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180008d68  mov     ebx, 80041031h
0x180008d6d  mov     edx, ebx
0x180008d6f  mov     rcx, rax
0x180008d72  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180008d78  lea     rax, WPP_GLOBAL_Control
0x180008d7f  mov     rcx, cs:WPP_GLOBAL_Control
0x180008d86  cmp     rcx, rax
0x180008d89  jz      short loc_180008DB3
0x180008d8b  test    byte ptr [rcx+1Ch], 1
0x180008d8f  jz      short loc_180008DB3
0x180008d91  cmp     byte ptr [rcx+19h], 2
0x180008d95  jb      short loc_180008DB3
0x180008d97  mov     edx, 52h ; 'R'
0x180008d9c  mov     r9d, 80041031h
0x180008da2  lea     r8, WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids
0x180008da9  mov     rcx, [rcx+10h]
0x180008dad  call    WPP_SF_d
0x180008db2  nop
0x180008db3  lea     rcx, [rsp+0D8h+var_A0]; this
0x180008db8  call    ??1CLock@CWbemObject@@QEAA@XZ; CWbemObject::CLock::~CLock(void)
0x180008dbd  mov     eax, ebx
0x180008dbf  jmp     loc_180008BAB
0x180008dc4  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180008dca  mov     ebx, 80041008h
0x180008dcf  mov     edx, ebx
0x180008dd1  mov     rcx, rax
0x180008dd4  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180008dda  lea     rax, WPP_GLOBAL_Control
0x180008de1  mov     rcx, cs:WPP_GLOBAL_Control
0x180008de8  cmp     rcx, rax
0x180008deb  jz      short loc_180008E15
0x180008ded  test    byte ptr [rcx+1Ch], 1
0x180008df1  jz      short loc_180008E15
0x180008df3  cmp     byte ptr [rcx+19h], 2
0x180008df7  jb      short loc_180008E15
0x180008df9  mov     edx, 53h ; 'S'
0x180008dfe  mov     r9d, 80041008h
0x180008e04  lea     r8, WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids
0x180008e0b  mov     rcx, [rcx+10h]
0x180008e0f  call    WPP_SF_d
0x180008e14  nop
0x180008e15  lea     rcx, [rsp+0D8h+var_A0]; this
0x180008e1a  call    ??1CLock@CWbemObject@@QEAA@XZ; CWbemObject::CLock::~CLock(void)
0x180008e1f  mov     eax, ebx
0x180008e21  jmp     loc_180008BAB
0x180008e26  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180008e2c  mov     ebx, 80041008h
0x180008e31  mov     edx, ebx
0x180008e33  mov     rcx, rax
0x180008e36  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180008e3c  lea     rax, WPP_GLOBAL_Control
0x180008e43  mov     rcx, cs:WPP_GLOBAL_Control
0x180008e4a  cmp     rcx, rax
0x180008e4d  jz      short loc_180008E77
0x180008e4f  test    byte ptr [rcx+1Ch], 1
0x180008e53  jz      short loc_180008E77
0x180008e55  cmp     byte ptr [rcx+19h], 2
0x180008e59  jb      short loc_180008E77
0x180008e5b  mov     edx, 54h ; 'T'
0x180008e60  mov     r9d, 80041008h
0x180008e66  lea     r8, WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids
0x180008e6d  mov     rcx, [rcx+10h]
0x180008e71  call    WPP_SF_d
0x180008e76  nop
0x180008e77  lea     rcx, [rsp+0D8h+var_68]
0x180008e7c  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x180008e82  nop
0x180008e83  lea     rcx, [rsp+0D8h+var_A0]; this
0x180008e88  call    ??1CLock@CWbemObject@@QEAA@XZ; CWbemObject::CLock::~CLock(void)
0x180008e8d  mov     eax, ebx
0x180008e8f  jmp     loc_180008BAB
0x180008e94  mov     ebx, 80041005h
0x180008e99  jmp     loc_180008BCA
0x180008e9e  mov     ebx, 80041031h
0x180008ea3  jmp     loc_180008BCA
0x180008ea8  cmp     byte ptr [rcx+19h], 2
  ... truncated ...
```
