# CWbemClass::Put(ushort const *,long,tagVARIANT *,long)

- ea: `0x1800035c0`
- end: `0x180003be7`
- name: `?Put@CWbemClass@@UEAAJPEBGJPEAUtagVARIANT@@J@Z`
- size: `1575`
- prototype: `__int64 __fastcall(CWbemClass *this, const unsigned __int16 *, int, struct tagVARIANT *, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1800035c0`
- `0x180003f60`
- `0x180004060`
- `0x180005720`
- `0x180037120`
- `0x180050490`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180003789`
- `wbemcomn!GetMemLogObject` at `0x1800037d1`
- `wbemcomn!GetMemLogObject` at `0x180003857`
- `wbemcomn!GetMemLogObject` at `0x18000389f`
- `wbemcomn!GetMemLogObject` at `0x1800038e7`
- `wbemcomn!GetMemLogObject` at `0x1800039cb`
- `wbemcomn!GetMemLogObject` at `0x180003a43`
- `wbemcomn!GetMemLogObject` at `0x180003a97`
- `wbemcomn!GetMemLogObject` at `0x180003b35`
- `wbemcomn!GetMemLogObject` at `0x180003789`
- `wbemcomn!GetMemLogObject` at `0x1800037d1`
- `wbemcomn!GetMemLogObject` at `0x180003857`
- `wbemcomn!GetMemLogObject` at `0x18000389f`
- `wbemcomn!GetMemLogObject` at `0x1800038e7`
- `wbemcomn!GetMemLogObject` at `0x1800039cb`
- `wbemcomn!GetMemLogObject` at `0x180003a43`
- `wbemcomn!GetMemLogObject` at `0x180003a97`
- `wbemcomn!GetMemLogObject` at `0x180003b35`
- `wbemcomn!?SetVariant@CVar@@QEAAHPEAUtagVARIANT@@H@Z` at `0x18000369a`
- `wbemcomn!?SetVariant@CVar@@QEAAHPEAUtagVARIANT@@H@Z` at `0x18000369a`
- `wbemcomn!IsValidElementName2` at `0x18000377b`
- `wbemcomn!IsValidElementName2` at `0x18000377b`
- `wbemcomn!IsValidElementName` at `0x180003675`
- `wbemcomn!IsValidElementName` at `0x180003675`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x180003688`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x18000381e`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x180003688`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x18000381e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180003799`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800037e1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180003867`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800038af`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800038f7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800039db`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180003a53`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180003aa7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180003b40`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180003799`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800037e1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180003867`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800038af`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800038f7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800039db`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180003a53`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180003aa7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180003b40`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18000371c`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18000384c`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180003a21`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180003a75`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18000371c`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18000384c`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180003a21`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180003a75`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CWbemClass::Put(
        CWbemClass *this,
        const unsigned __int16 *a2,
        int a3,
        struct tagVARIANT *a4,
        unsigned int a5)
{
  unsigned int v9; // r15d
  int v10; // esi
  __int64 result; // rax
  const unsigned __int16 *bstrVal; // rcx
  CMemoryLog *v13; // rax
  CMemoryLog *v14; // rax
  CMemoryLog *v15; // rax
  CMemoryLog *v16; // rax
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v18; // rax
  CMemoryLog *v19; // rax
  CMemoryLog *v20; // rax
  CMemoryLog *v21; // rax
  CMemoryLog *v22; // rax
  CWbemClass *v23; // [rsp+30h] [rbp-78h] BYREF
  _BYTE v24[32]; // [rsp+38h] [rbp-70h] BYREF
  _BYTE v25[80]; // [rsp+58h] [rbp-50h] BYREF

  try
  {
    v23 = this;
    (*(void (__fastcall **)(CWbemClass *, _QWORD))(*(_QWORD *)this + 280LL))(this, 0);
    if ( !a2 || (a3 & 0xFFFDFFFF) != 0 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, -2147217400);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 96, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids, 2147749896LL);
      }
      (*(void (__fastcall **)(CWbemClass *, _QWORD))(*(_QWORD *)this + 288LL))(this, 0);
      return 2147749896LL;
    }
    if ( (unsigned int)CReservedWordTable::IsReservedWord(a2) )
    {
      v20 = GetMemLogObject();
      CMemoryLog::Write(v20, -2147217386);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 97, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids, 2147749910LL);
      }
      CWbemObject::CLock::~CLock((CWbemObject::CLock *)&v23);
      return 2147749910LL;
    }
    if ( !a4 || a4->vt == 1 )
    {
      v9 = a5;
      if ( !a5 )
      {
        CVar::CVar((CVar *)v25);
        if ( (*(int (__fastcall **)(CWbemClass *, const unsigned __int16 *, _BYTE *))(*(_QWORD *)this + 776LL))(
               this,
               a2,
               v25) < 0 )
        {
          v19 = GetMemLogObject();
          CMemoryLog::Write(v19, -2147217400);
          if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              98,
              WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids,
              2147749896LL);
          }
          CVar::~CVar((CVar *)v25);
          (*(void (__fastcall **)(CWbemClass *, _QWORD))(*(_QWORD *)this + 288LL))(this, 0);
          return 2147749896LL;
        }
        CVar::~CVar((CVar *)v25);
LABEL_8:
        if ( (unsigned int)wbem_wcsicmp(a2, L"__CLASS") )
        {
          if ( (int)CSystemProperties::FindName(a2) >= 0 )
          {
            v16 = GetMemLogObject();
            CMemoryLog::Write(v16, -2147217373);
            if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                100,
                WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids,
                2147749923LL);
            }
            (*(void (__fastcall **)(CWbemClass *, _QWORD))(*(_QWORD *)this + 288LL))(this, 0);
            return 2147749923LL;
          }
          if ( IsValidElementName(a2, g_IdentifierLimit) )
            goto LABEL_11;
          v14 = GetMemLogObject();
          CMemoryLog::Write(v14, -2147217400);
          if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              101,
              WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids,
              2147749896LL);
          }
        }
        else
        {
          if ( a4 )
          {
            if ( a4->vt == 8 )
            {
              bstrVal = a4->bstrVal;
              if ( bstrVal )
              {
                if ( IsValidElementName2(bstrVal, g_IdentifierLimit, 1) )
                {
LABEL_11:
                  CVar::CVar((CVar *)v24);
                  if ( !CVar::SetVariant((CVar *)v24, a4, 1) )
                  {
                    v10 = (*(__int64 (__fastcall **)(CWbemClass *, const unsigned __int16 *, _BYTE *, _QWORD))(*(_QWORD *)this + 872LL))(
                            this,
                            a2,
                            v24,
                            v9);
                    (*(void (__fastcall **)(CWbemClass *))(*(_QWORD *)this + 80LL))(this);
                    if ( (*(int (__fastcall **)(CWbemClass *, _QWORD))(*(_QWORD *)this + 744LL))(this, 0) < 0 )
                    {
                      v10 = -2147217407;
                    }
                    else if ( v10 >= 0 )
                    {
                      goto LABEL_14;
                    }
                    v21 = GetMemLogObject();
                    CMemoryLog::Write(v21, v10);
LABEL_14:
                    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                    {
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        104,
                        WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids,
                        (unsigned int)v10);
                    }
                    CVar::~CVar((CVar *)v24);
                    (*(void (__fastcall **)(CWbemClass *, _QWORD))(*(_QWORD *)this + 288LL))(this, 0);
                    return (unsigned int)v10;
                  }
                  v18 = GetMemLogObject();
                  CMemoryLog::Write(v18, -2147217403);
                  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      103,
                      WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids,
                      2147749893LL);
                  }
                  CVar::~CVar((CVar *)v24);
                  (*(void (__fastcall **)(CWbemClass *, _QWORD))(*(_QWORD *)this + 288LL))(this, 0);
                  return 2147749893LL;
                }
              }
            }
          }
          v13 = GetMemLogObject();
          CMemoryLog::Write(v13, -2147217400);
          if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              102,
              WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids,
              2147749896LL);
          }
        }
        (*(void (__fastcall **)(CWbemClass *, _QWORD))(*(_QWORD *)this + 288LL))(this, 0);
        return 2147749896LL;
      }
    }
    else
    {
      v9 = a5;
    }
    if ( (v9 & 0x2FFF) != v9 )
    {
      v15 = GetMemLogObject();
      CMemoryLog::Write(v15, -2147217366);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 99, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids, 2147749930LL);
      }
      (*(void (__fastcall **)(CWbemClass *, _QWORD))(*(_QWORD *)this + 288LL))(this, 0);
      return 2147749930LL;
    }
    goto LABEL_8;
  }
  catch ( CX_MemoryException )
  {
    v22 = GetMemLogObject();
    CMemoryLog::Write(v22, -2147217402);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids, 2147749894LL);
    }
    return 2147749894LL;
  }
  v23 = this;
}

```

## disassembly

```asm
0x1800035c0  push    rbx
0x1800035c2  push    rsi
0x1800035c3  push    rdi
0x1800035c4  push    r14
0x1800035c6  push    r15
0x1800035c8  sub     rsp, 80h
0x1800035cf  mov     rsi, r9
0x1800035d2  mov     edi, r8d
0x1800035d5  mov     r14, rdx
0x1800035d8  mov     rbx, rcx
0x1800035db  mov     [rsp+0A8h+var_78], rcx
0x1800035e0  mov     rax, [rcx]
0x1800035e3  xor     edx, edx
0x1800035e5  mov     rax, [rax+118h]
0x1800035ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035f1  nop
0x1800035f2  test    r14, r14
0x1800035f5  jz      loc_1800038E7
0x1800035fb  test    edi, 0FFFDFFFFh
0x180003601  jnz     loc_1800038E7
0x180003607  mov     rcx, r14; unsigned __int16 *
0x18000360a  call    ?IsReservedWord@CReservedWordTable@@SAHPEBG@Z; CReservedWordTable::IsReservedWord(ushort const *)
0x18000360f  test    eax, eax
0x180003611  jnz     loc_180003A97
0x180003617  lea     edi, [rax+1]
0x18000361a  test    rsi, rsi
0x18000361d  jnz     loc_180003748
0x180003623  mov     r15d, [rsp+0A8h+arg_20]
0x18000362b  test    r15d, r15d
0x18000362e  jz      loc_180003819
0x180003634  mov     eax, r15d
0x180003637  and     eax, 2FFFh
0x18000363c  cmp     eax, r15d
0x18000363f  jnz     loc_180003857
0x180003645  lea     rdx, aClass_1; "__CLASS"
0x18000364c  mov     rcx, r14; unsigned __int16 *
0x18000364f  call    ?wbem_wcsicmp@@YAHPEBG0@Z; wbem_wcsicmp(ushort const *,ushort const *)
0x180003654  test    eax, eax
0x180003656  jz      loc_18000375E
0x18000365c  mov     rcx, r14; unsigned __int16 *
0x18000365f  call    ?FindName@CSystemProperties@@SAHPEBG@Z; CSystemProperties::FindName(ushort const *)
0x180003664  test    eax, eax
0x180003666  jns     loc_18000389F
0x18000366c  mov     edx, cs:?g_IdentifierLimit@@3KA; ulong g_IdentifierLimit
0x180003672  mov     rcx, r14
0x180003675  call    cs:__imp_?IsValidElementName@@YAHPEBGK@Z; IsValidElementName(ushort const *,ulong)
0x18000367b  test    eax, eax
0x18000367d  jz      loc_1800037D1
0x180003683  lea     rcx, [rsp+0A8h+var_70]
0x180003688  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x18000368e  nop
0x18000368f  mov     r8d, edi
0x180003692  mov     rdx, rsi
0x180003695  lea     rcx, [rsp+0A8h+var_70]
0x18000369a  call    cs:__imp_?SetVariant@CVar@@QEAAHPEAUtagVARIANT@@H@Z; CVar::SetVariant(tagVARIANT *,int)
0x1800036a0  test    eax, eax
0x1800036a2  jnz     loc_1800039CB
0x1800036a8  mov     rax, [rbx]
0x1800036ab  mov     r9d, r15d
0x1800036ae  lea     r8, [rsp+0A8h+var_70]
0x1800036b3  mov     rdx, r14
0x1800036b6  mov     rcx, rbx
0x1800036b9  mov     rax, [rax+368h]
0x1800036c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036c5  mov     esi, eax
0x1800036c7  mov     rax, [rbx]
0x1800036ca  mov     rcx, rbx
0x1800036cd  mov     rax, [rax+50h]
0x1800036d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036d6  mov     rax, [rbx]
0x1800036d9  xor     edx, edx
0x1800036db  mov     rcx, rbx
0x1800036de  mov     rax, [rax+2E8h]
0x1800036e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036ea  test    eax, eax
0x1800036ec  js      loc_180003B30
0x1800036f2  test    esi, esi
0x1800036f4  js      loc_180003B35
0x1800036fa  lea     rax, WPP_GLOBAL_Control
0x180003701  mov     rcx, cs:WPP_GLOBAL_Control
0x180003708  cmp     rcx, rax
0x18000370b  jz      short loc_180003717
0x18000370d  test    [rcx+1Ch], dil
0x180003711  jnz     loc_180003B4B
0x180003717  lea     rcx, [rsp+0A8h+var_70]
0x18000371c  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x180003722  nop
0x180003723  mov     rcx, [rbx]
0x180003726  mov     rax, [rcx+120h]
0x18000372d  xor     edx, edx
0x18000372f  mov     rcx, rbx
0x180003732  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003737  mov     eax, esi
0x180003739  add     rsp, 80h
0x180003740  pop     r15
0x180003742  pop     r14
0x180003744  pop     rdi
0x180003745  pop     rsi
0x180003746  pop     rbx
0x180003747  retn
0x180003748  cmp     [rsi], di
0x18000374b  jz      loc_180003623
0x180003751  mov     r15d, [rsp+0A8h+arg_20]
0x180003759  jmp     loc_180003634
0x18000375e  test    rsi, rsi
0x180003761  jz      short loc_180003789
0x180003763  cmp     word ptr [rsi], 8
0x180003767  jnz     short loc_180003789
0x180003769  mov     rcx, [rsi+8]
0x18000376d  test    rcx, rcx
0x180003770  jz      short loc_180003789
0x180003772  mov     r8d, edi
0x180003775  mov     edx, cs:?g_IdentifierLimit@@3KA; ulong g_IdentifierLimit
0x18000377b  call    cs:__imp_?IsValidElementName2@@YAHPEBGKH@Z; IsValidElementName2(ushort const *,ulong,int)
0x180003781  test    eax, eax
0x180003783  jnz     loc_180003683
0x180003789  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000378f  mov     esi, 80041008h
0x180003794  mov     edx, esi
0x180003796  mov     rcx, rax
0x180003799  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000379f  lea     rax, WPP_GLOBAL_Control
0x1800037a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800037ad  cmp     rcx, rax
0x1800037b0  jnz     loc_180003B72
0x1800037b6  mov     rax, [rbx]
0x1800037b9  xor     edx, edx
0x1800037bb  mov     rcx, rbx
0x1800037be  mov     rax, [rax+120h]
0x1800037c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037ca  mov     eax, esi
0x1800037cc  jmp     loc_180003739
0x1800037d1  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800037d7  mov     esi, 80041008h
0x1800037dc  mov     edx, esi
0x1800037de  mov     rcx, rax
0x1800037e1  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800037e7  lea     rax, WPP_GLOBAL_Control
0x1800037ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800037f5  cmp     rcx, rax
0x1800037f8  jnz     loc_180003997
0x1800037fe  mov     rax, [rbx]
0x180003801  xor     edx, edx
0x180003803  mov     rcx, rbx
0x180003806  mov     rax, [rax+120h]
0x18000380d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003812  mov     eax, esi
0x180003814  jmp     loc_180003739
0x180003819  lea     rcx, [rsp+0A8h+var_50]
0x18000381e  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x180003824  nop
0x180003825  mov     rax, [rbx]
0x180003828  lea     r8, [rsp+0A8h+var_50]
0x18000382d  mov     rdx, r14
0x180003830  mov     rcx, rbx
0x180003833  mov     rax, [rax+308h]
0x18000383a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000383f  test    eax, eax
0x180003841  js      loc_180003A43
0x180003847  lea     rcx, [rsp+0A8h+var_50]
0x18000384c  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x180003852  jmp     loc_180003645
0x180003857  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000385d  mov     esi, 8004102Ah
0x180003862  mov     edx, esi
0x180003864  mov     rcx, rax
0x180003867  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000386d  lea     rax, WPP_GLOBAL_Control
0x180003874  mov     rcx, cs:WPP_GLOBAL_Control
0x18000387b  cmp     rcx, rax
0x18000387e  jnz     loc_18000392F
0x180003884  mov     rcx, [rbx]
0x180003887  mov     rax, [rcx+120h]
0x18000388e  xor     edx, edx
0x180003890  mov     rcx, rbx
0x180003893  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003898  mov     eax, esi
0x18000389a  jmp     loc_180003739
0x18000389f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800038a5  mov     esi, 80041023h
0x1800038aa  mov     edx, esi
0x1800038ac  mov     rcx, rax
0x1800038af  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800038b5  lea     rax, WPP_GLOBAL_Control
0x1800038bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800038c3  cmp     rcx, rax
0x1800038c6  jnz     loc_180003963
0x1800038cc  mov     rcx, [rbx]
0x1800038cf  mov     rax, [rcx+120h]
0x1800038d6  xor     edx, edx
0x1800038d8  mov     rcx, rbx
0x1800038db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038e0  mov     eax, esi
0x1800038e2  jmp     loc_180003739
0x1800038e7  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800038ed  mov     esi, 80041008h
0x1800038f2  mov     edx, esi
0x1800038f4  mov     rcx, rax
0x1800038f7  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800038fd  lea     rax, WPP_GLOBAL_Control
0x180003904  mov     rcx, cs:WPP_GLOBAL_Control
0x18000390b  cmp     rcx, rax
0x18000390e  jnz     loc_180003BA6
0x180003914  mov     rax, [rbx]
0x180003917  xor     edx, edx
0x180003919  mov     rcx, rbx
0x18000391c  mov     rax, [rax+120h]
0x180003923  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003928  mov     eax, esi
0x18000392a  jmp     loc_180003739
0x18000392f  test    [rcx+1Ch], dil
0x180003933  jz      loc_180003884
0x180003939  cmp     byte ptr [rcx+19h], 2
0x18000393d  jb      loc_180003884
0x180003943  mov     edx, 63h ; 'c'
0x180003948  mov     r9d, 8004102Ah
0x18000394e  lea     r8, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids
0x180003955  mov     rcx, [rcx+10h]
0x180003959  call    WPP_SF_d
0x18000395e  jmp     loc_180003884
0x180003963  test    [rcx+1Ch], dil
0x180003967  jz      loc_1800038CC
0x18000396d  cmp     byte ptr [rcx+19h], 2
0x180003971  jb      loc_1800038CC
0x180003977  mov     edx, 64h ; 'd'
0x18000397c  mov     r9d, 80041023h
0x180003982  lea     r8, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids
0x180003989  mov     rcx, [rcx+10h]
0x18000398d  call    WPP_SF_d
0x180003992  jmp     loc_1800038CC
0x180003997  test    [rcx+1Ch], dil
0x18000399b  jz      loc_1800037FE
0x1800039a1  cmp     byte ptr [rcx+19h], 2
0x1800039a5  jb      loc_1800037FE
0x1800039ab  mov     edx, 65h ; 'e'
0x1800039b0  mov     r9d, 80041008h
0x1800039b6  lea     r8, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids
0x1800039bd  mov     rcx, [rcx+10h]
0x1800039c1  call    WPP_SF_d
0x1800039c6  jmp     loc_1800037FE
0x1800039cb  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800039d1  mov     esi, 80041005h
0x1800039d6  mov     edx, esi
0x1800039d8  mov     rcx, rax
0x1800039db  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800039e1  lea     rax, WPP_GLOBAL_Control
0x1800039e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800039ef  cmp     rcx, rax
0x1800039f2  jz      short loc_180003A1C
0x1800039f4  test    [rcx+1Ch], dil
0x1800039f8  jz      short loc_180003A1C
0x1800039fa  cmp     byte ptr [rcx+19h], 2
0x1800039fe  jb      short loc_180003A1C
0x180003a00  mov     edx, 67h ; 'g'
0x180003a05  mov     r9d, 80041005h
0x180003a0b  lea     r8, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids
0x180003a12  mov     rcx, [rcx+10h]
0x180003a16  call    WPP_SF_d
0x180003a1b  nop
0x180003a1c  lea     rcx, [rsp+0A8h+var_70]
0x180003a21  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x180003a27  nop
0x180003a28  mov     rcx, [rbx]
0x180003a2b  mov     rax, [rcx+120h]
0x180003a32  xor     edx, edx
0x180003a34  mov     rcx, rbx
0x180003a37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a3c  mov     eax, esi
0x180003a3e  jmp     loc_180003739
0x180003a43  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180003a49  mov     esi, 80041008h
0x180003a4e  mov     edx, esi
0x180003a50  mov     rcx, rax
0x180003a53  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180003a59  lea     rax, WPP_GLOBAL_Control
0x180003a60  mov     rcx, cs:WPP_GLOBAL_Control
0x180003a67  cmp     rcx, rax
0x180003a6a  jnz     loc_180003AFC
0x180003a70  lea     rcx, [rsp+0A8h+var_50]
0x180003a75  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x180003a7b  nop
0x180003a7c  mov     rcx, [rbx]
0x180003a7f  mov     rax, [rcx+120h]
0x180003a86  xor     edx, edx
0x180003a88  mov     rcx, rbx
0x180003a8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a90  mov     eax, esi
0x180003a92  jmp     loc_180003739
0x180003a97  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180003a9d  mov     ebx, 80041016h
0x180003aa2  mov     edx, ebx
0x180003aa4  mov     rcx, rax
0x180003aa7  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180003aad  lea     rax, WPP_GLOBAL_Control
0x180003ab4  mov     rcx, cs:WPP_GLOBAL_Control
0x180003abb  cmp     rcx, rax
0x180003abe  jz      short loc_180003AEB
0x180003ac0  mov     edi, 1
0x180003ac5  test    [rcx+1Ch], dil
0x180003ac9  jz      short loc_180003AEB
  ... truncated ...
```
