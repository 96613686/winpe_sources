# CQualifierSet::EnumQualifiers(uchar,uchar,CFixedBSTRArray &)

- ea: `0x1800097b0`
- end: `0x180009c05`
- name: `?EnumQualifiers@CQualifierSet@@QEAAJEEAEAVCFixedBSTRArray@@@Z`
- size: `1109`
- prototype: `int(CQualifierSet *__hidden this, unsigned __int8, unsigned __int8, struct CFixedBSTRArray *)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180008f60`
- `0x180060310`
- `0x180067b60`

## callees

- `0x1800092d0`
- `0x1800097b0`
- `0x180009c0c`
- `0x18000a6c0`
- `0x180037120`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180009a04`
- `wbemcomn!GetMemLogObject` at `0x180009ad4`
- `wbemcomn!GetMemLogObject` at `0x180009be5`
- `wbemcomn!GetMemLogObject` at `0x180009a04`
- `wbemcomn!GetMemLogObject` at `0x180009ad4`
- `wbemcomn!GetMemLogObject` at `0x180009be5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180009a0f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180009adf`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180009bf0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180009a0f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180009adf`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180009bf0`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000992f`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000993b`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180009984`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180009990`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800099f1`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180009a51`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180009a5d`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180009aa6`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180009ab2`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180009b5f`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180009b6b`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000992f`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000993b`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180009984`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180009990`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800099f1`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180009a51`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180009a5d`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180009aa6`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180009ab2`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180009b5f`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180009b6b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800099de`
- `OLEAUT32!__imp_SysFreeString` at `0x1800099de`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CQualifierSet::EnumQualifiers(
        CQualifierSet *this,
        char a2,
        unsigned __int8 a3,
        struct CFixedBSTRArray *a4)
{
  BSTR *v8; // rsi
  __int64 v9; // rbx
  unsigned int v10; // edi
  __int64 result; // rax
  int v12; // r14d
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v14; // rax
  CMemoryLog *v15; // rax
  int v16; // [rsp+30h] [rbp-D8h] BYREF
  void *v17; // [rsp+34h] [rbp-D4h]
  int v18; // [rsp+40h] [rbp-C8h] BYREF
  void *v19; // [rsp+44h] [rbp-C4h]
  int v20; // [rsp+50h] [rbp-B8h] BYREF
  void *v21; // [rsp+54h] [rbp-B4h]
  int v22; // [rsp+60h] [rbp-A8h] BYREF
  void *v23; // [rsp+64h] [rbp-A4h]
  unsigned int v24; // [rsp+70h] [rbp-98h]
  int v25; // [rsp+74h] [rbp-94h]
  _BYTE v26[8]; // [rsp+78h] [rbp-90h] BYREF
  __int64 v27; // [rsp+80h] [rbp-88h]
  void (__fastcall *v28)(__int64); // [rsp+88h] [rbp-80h]
  _BYTE v29[8]; // [rsp+90h] [rbp-78h] BYREF
  __int64 v30; // [rsp+98h] [rbp-70h]
  void (__fastcall *v31)(__int64); // [rsp+A0h] [rbp-68h]
  _BYTE v32[8]; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v33; // [rsp+B0h] [rbp-58h]
  void (__fastcall *v34)(__int64); // [rsp+B8h] [rbp-50h]
  __int64 v35; // [rsp+C8h] [rbp-40h]

  v8 = 0;
  try
  {
    v9 = *((_QWORD *)this + 5);
    v35 = v9;
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v9 + 280LL))(v9, 0);
    v20 = 0;
    v21 = 0;
    v18 = 0;
    v19 = 0;
    MakeObjGuard<CFixedBSTRArray,void (CFixedBSTRArray::*)(void)>(v29, &v20);
    MakeObjGuard<CFixedBSTRArray,void (CFixedBSTRArray::*)(void)>(v26, &v18);
    v10 = CBasicQualifierSet::EnumPrimaryQualifiers(
            (CQualifierSet *)((char *)this + 8),
            a2,
            a3,
            (struct CFixedBSTRArray *)&v20,
            (struct CFixedBSTRArray *)&v18);
    v24 = v10;
    if ( (v10 & 0x80000000) == 0 )
    {
      v22 = 0;
      v23 = 0;
      v16 = 0;
      v17 = 0;
      MakeObjGuard<CFixedBSTRArray,void (CFixedBSTRArray::*)(void)>(v32, &v22);
      if ( *((_DWORD *)this + 8) != 2 && a2 != 16 )
      {
        v10 = CBasicQualifierSet::EnumPrimaryQualifiers(
                *((CBasicQualifierSet **)this + 7),
                0,
                *((_BYTE *)this + 32) | a3,
                (struct CFixedBSTRArray *)&v22,
                (struct CFixedBSTRArray *)&v16);
        v24 = v10;
        if ( (v10 & 0x80000000) != 0 )
        {
          MemLogObject = GetMemLogObject();
          CMemoryLog::Write(MemLogObject, v10);
          if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 103, WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids, v10);
          }
          if ( !v32[0] )
            v34(v33);
          CWin32DefaultArena::WbemMemFree(v17);
          CWin32DefaultArena::WbemMemFree(v23);
          if ( !v26[0] )
            v28(v27);
          if ( v29[0] )
            goto LABEL_15;
LABEL_14:
          v31(v30);
LABEL_15:
          CWin32DefaultArena::WbemMemFree(v19);
          CWin32DefaultArena::WbemMemFree(v21);
          (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v9 + 288LL))(v9, 0);
          return v10;
        }
        v8 = (BSTR *)v17;
        if ( v17 )
        {
          v12 = 0;
          v25 = 0;
          while ( v12 < v16 )
          {
            SysFreeString(v8[v12++]);
            v25 = v12;
          }
          CWin32DefaultArena::WbemMemFree(v8);
          v8 = 0;
          v17 = 0;
        }
      }
      v16 = 0;
      CFixedBSTRArray::ThreeWayMergeOrdered(
        a4,
        (struct CFixedBSTRArray *)&v20,
        (struct CFixedBSTRArray *)&v22,
        (struct CFixedBSTRArray *)&v18);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids, v10);
      }
      if ( !v32[0] )
        v34(v33);
      CWin32DefaultArena::WbemMemFree(v8);
      CWin32DefaultArena::WbemMemFree(v23);
      if ( !v26[0] )
        v28(v27);
      if ( v29[0] )
        goto LABEL_15;
      goto LABEL_14;
    }
    v14 = GetMemLogObject();
    CMemoryLog::Write(v14, v10);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 102, WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids, v10);
    }
    if ( !v26[0] )
      v28(v27);
    if ( !v29[0] )
      v31(v30);
    CWin32DefaultArena::WbemMemFree(v19);
    CWin32DefaultArena::WbemMemFree(v21);
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v9 + 288LL))(v9, 0);
    result = v10;
  }
  catch ( CX_MemoryException )
  {
    v15 = GetMemLogObject();
    CMemoryLog::Write(v15, -2147217402);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids, 2147749894LL);
    }
    return 2147749894LL;
  }
  return result;
}

```

## disassembly

```asm
0x1800097b0  mov     rax, rsp
0x1800097b3  push    rbx
0x1800097b4  push    rsi
0x1800097b5  push    rdi
0x1800097b6  push    r12
0x1800097b8  push    r13
0x1800097ba  push    r14
0x1800097bc  push    r15
0x1800097be  sub     rsp, 0D0h
0x1800097c5  mov     r13, r9
0x1800097c8  mov     r15b, r8b
0x1800097cb  mov     r12b, dl
0x1800097ce  mov     r14, rcx
0x1800097d1  xor     esi, esi
0x1800097d3  mov     rbx, [rcx+28h]
0x1800097d7  mov     [rax-40h], rbx
0x1800097db  mov     rax, [rbx]
0x1800097de  xor     edx, edx
0x1800097e0  mov     rcx, rbx
0x1800097e3  mov     rax, [rax+118h]
0x1800097ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097ef  nop
0x1800097f0  mov     [rsp+108h+var_B8], esi
0x1800097f4  mov     [rsp+108h+var_B4], rsi
0x1800097f9  mov     [rsp+108h+var_C8], esi
0x1800097fd  mov     [rsp+108h+var_C4], rsi
0x180009802  lea     rdx, [rsp+108h+var_B8]
0x180009807  lea     rcx, [rsp+108h+var_78]
0x18000980f  call    ??$MakeObjGuard@VCFixedBSTRArray@@P81@EAAXXZ@@YA?AV?$ObjScopeGuardImpl0@VCFixedBSTRArray@@P81@EAAXXZ@@AEAVCFixedBSTRArray@@P81@EAAXXZ@Z; MakeObjGuard<CFixedBSTRArray,void (CFixedBSTRArray::*)(void)>(CFixedBSTRArray &,void (CFixedBSTRArray::*)(void))
0x180009814  nop
0x180009815  lea     rdx, [rsp+108h+var_C8]
0x18000981a  lea     rcx, [rsp+108h+var_90]
0x18000981f  call    ??$MakeObjGuard@VCFixedBSTRArray@@P81@EAAXXZ@@YA?AV?$ObjScopeGuardImpl0@VCFixedBSTRArray@@P81@EAAXXZ@@AEAVCFixedBSTRArray@@P81@EAAXXZ@Z; MakeObjGuard<CFixedBSTRArray,void (CFixedBSTRArray::*)(void)>(CFixedBSTRArray &,void (CFixedBSTRArray::*)(void))
0x180009824  nop
0x180009825  lea     rcx, [r14+8]; this
0x180009829  lea     rax, [rsp+108h+var_C8]
0x18000982e  mov     [rsp+108h+var_E8], rax; struct CFixedBSTRArray *
0x180009833  lea     r9, [rsp+108h+var_B8]; struct CFixedBSTRArray *
0x180009838  mov     r8b, r15b; unsigned __int8
0x18000983b  mov     dl, r12b; unsigned __int8
0x18000983e  call    ?EnumPrimaryQualifiers@CBasicQualifierSet@@QEAAJEEAEAVCFixedBSTRArray@@0@Z; CBasicQualifierSet::EnumPrimaryQualifiers(uchar,uchar,CFixedBSTRArray &,CFixedBSTRArray &)
0x180009843  mov     edi, eax
0x180009845  mov     [rsp+108h+var_98], eax
0x180009849  test    eax, eax
0x18000984b  js      loc_180009AD4
0x180009851  mov     [rsp+108h+var_A8], esi
0x180009855  mov     [rsp+108h+var_A4], rsi
0x18000985a  mov     [rsp+108h+var_D8], esi
0x18000985e  mov     [rsp+108h+var_D4], rsi
0x180009863  lea     rdx, [rsp+108h+var_A8]
0x180009868  lea     rcx, [rsp+108h+var_60]
0x180009870  call    ??$MakeObjGuard@VCFixedBSTRArray@@P81@EAAXXZ@@YA?AV?$ObjScopeGuardImpl0@VCFixedBSTRArray@@P81@EAAXXZ@@AEAVCFixedBSTRArray@@P81@EAAXXZ@Z; MakeObjGuard<CFixedBSTRArray,void (CFixedBSTRArray::*)(void)>(CFixedBSTRArray &,void (CFixedBSTRArray::*)(void))
0x180009875  nop
0x180009876  cmp     dword ptr [r14+20h], 2
0x18000987b  jz      loc_1800099C0
0x180009881  cmp     r12b, 10h
0x180009885  jz      loc_1800099C0
0x18000988b  or      r15b, [r14+20h]
0x18000988f  lea     rax, [rsp+108h+var_D8]
0x180009894  mov     [rsp+108h+var_E8], rax; struct CFixedBSTRArray *
0x180009899  lea     r9, [rsp+108h+var_A8]; struct CFixedBSTRArray *
0x18000989e  mov     r8b, r15b; unsigned __int8
0x1800098a1  xor     edx, edx; unsigned __int8
0x1800098a3  mov     rcx, [r14+38h]; this
0x1800098a7  call    ?EnumPrimaryQualifiers@CBasicQualifierSet@@QEAAJEEAEAVCFixedBSTRArray@@0@Z; CBasicQualifierSet::EnumPrimaryQualifiers(uchar,uchar,CFixedBSTRArray &,CFixedBSTRArray &)
0x1800098ac  mov     edi, eax
0x1800098ae  mov     [rsp+108h+var_98], eax
0x1800098b2  xor     r15d, r15d
0x1800098b5  test    eax, eax
0x1800098b7  js      loc_180009A04
0x1800098bd  mov     rsi, [rsp+108h+var_D4]
0x1800098c2  test    rsi, rsi
0x1800098c5  jnz     loc_1800099C8
0x1800098cb  mov     [rsp+108h+var_D8], r15d
0x1800098d0  lea     r9, [rsp+108h+var_C8]; struct CFixedBSTRArray *
0x1800098d5  lea     r8, [rsp+108h+var_A8]; struct CFixedBSTRArray *
0x1800098da  lea     rdx, [rsp+108h+var_B8]; struct CFixedBSTRArray *
0x1800098df  mov     rcx, r13; this
0x1800098e2  call    ?ThreeWayMergeOrdered@CFixedBSTRArray@@QEAAXAEAV1@00@Z; CFixedBSTRArray::ThreeWayMergeOrdered(CFixedBSTRArray &,CFixedBSTRArray &,CFixedBSTRArray &)
0x1800098e7  test    edi, edi
0x1800098e9  js      loc_180009BE5
0x1800098ef  lea     rax, WPP_GLOBAL_Control
0x1800098f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800098fd  cmp     rcx, rax
0x180009900  jz      short loc_18000990C
0x180009902  test    byte ptr [rcx+1Ch], 1
0x180009906  jnz     loc_180009B8D
0x18000990c  cmp     [rsp+108h+var_60], r15b
0x180009914  jnz     short loc_18000992C
0x180009916  mov     rcx, [rsp+108h+var_58]
0x18000991e  mov     rax, [rsp+108h+var_50]
0x180009926  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000992b  nop
0x18000992c  mov     rcx, rsi
0x18000992f  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180009935  nop
0x180009936  mov     rcx, [rsp+108h+var_A4]
0x18000993b  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180009941  nop
0x180009942  cmp     [rsp+108h+var_90], r15b
0x180009947  jnz     short loc_18000995F
0x180009949  mov     rcx, [rsp+108h+var_88]
0x180009951  mov     rax, [rsp+108h+var_80]
0x180009959  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000995e  nop
0x18000995f  cmp     [rsp+108h+var_78], r15b
0x180009967  jnz     short loc_18000997F
0x180009969  mov     rcx, [rsp+108h+var_70]
0x180009971  mov     rax, [rsp+108h+var_68]
0x180009979  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000997e  nop
0x18000997f  mov     rcx, [rsp+108h+var_C4]
0x180009984  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18000998a  nop
0x18000998b  mov     rcx, [rsp+108h+var_B4]
0x180009990  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180009996  nop
0x180009997  mov     rax, [rbx]
0x18000999a  xor     edx, edx
0x18000999c  mov     rcx, rbx
0x18000999f  mov     rax, [rax+120h]
0x1800099a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099ab  mov     eax, edi
0x1800099ad  add     rsp, 0D0h
0x1800099b4  pop     r15
0x1800099b6  pop     r14
0x1800099b8  pop     r13
0x1800099ba  pop     r12
0x1800099bc  pop     rdi
0x1800099bd  pop     rsi
0x1800099be  pop     rbx
0x1800099bf  retn
0x1800099c0  xor     r15d, r15d
0x1800099c3  jmp     loc_1800098CB
0x1800099c8  mov     r14d, r15d
0x1800099cb  mov     [rsp+108h+var_94], r15d
0x1800099d0  cmp     r14d, [rsp+108h+var_D8]
0x1800099d5  jge     short loc_1800099EE
0x1800099d7  movsxd  rcx, r14d
0x1800099da  mov     rcx, [rsi+rcx*8]; bstrString
0x1800099de  call    cs:__imp_SysFreeString
0x1800099e4  inc     r14d
0x1800099e7  mov     [rsp+108h+var_94], r14d
0x1800099ec  jmp     short loc_1800099D0
0x1800099ee  mov     rcx, rsi
0x1800099f1  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800099f7  mov     rsi, r15
0x1800099fa  mov     [rsp+108h+var_D4], r15
0x1800099ff  jmp     loc_1800098CB
0x180009a04  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180009a0a  mov     edx, edi
0x180009a0c  mov     rcx, rax
0x180009a0f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180009a15  lea     rax, WPP_GLOBAL_Control
0x180009a1c  mov     rcx, cs:WPP_GLOBAL_Control
0x180009a23  cmp     rcx, rax
0x180009a26  jnz     loc_180009BB4
0x180009a2c  cmp     [rsp+108h+var_60], r15b
0x180009a34  jnz     short loc_180009A4C
0x180009a36  mov     rcx, [rsp+108h+var_58]
0x180009a3e  mov     rax, [rsp+108h+var_50]
0x180009a46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a4b  nop
0x180009a4c  mov     rcx, [rsp+108h+var_D4]
0x180009a51  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180009a57  nop
0x180009a58  mov     rcx, [rsp+108h+var_A4]
0x180009a5d  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180009a63  nop
0x180009a64  cmp     [rsp+108h+var_90], r15b
0x180009a69  jnz     short loc_180009A81
0x180009a6b  mov     rcx, [rsp+108h+var_88]
0x180009a73  mov     rax, [rsp+108h+var_80]
0x180009a7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a80  nop
0x180009a81  cmp     [rsp+108h+var_78], r15b
0x180009a89  jnz     short loc_180009AA1
0x180009a8b  mov     rcx, [rsp+108h+var_70]
0x180009a93  mov     rax, [rsp+108h+var_68]
0x180009a9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009aa0  nop
0x180009aa1  mov     rcx, [rsp+108h+var_C4]
0x180009aa6  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180009aac  nop
0x180009aad  mov     rcx, [rsp+108h+var_B4]
0x180009ab2  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180009ab8  nop
0x180009ab9  mov     rax, [rbx]
0x180009abc  xor     edx, edx
0x180009abe  mov     rcx, rbx
0x180009ac1  mov     rax, [rax+120h]
0x180009ac8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009acd  mov     eax, edi
0x180009acf  jmp     loc_1800099AD
0x180009ad4  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180009ada  mov     edx, edi
0x180009adc  mov     rcx, rax
0x180009adf  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180009ae5  lea     rax, WPP_GLOBAL_Control
0x180009aec  mov     rcx, cs:WPP_GLOBAL_Control
0x180009af3  cmp     rcx, rax
0x180009af6  jz      short loc_180009B1D
0x180009af8  test    byte ptr [rcx+1Ch], 1
0x180009afc  jz      short loc_180009B1D
0x180009afe  cmp     byte ptr [rcx+19h], 2
0x180009b02  jb      short loc_180009B1D
0x180009b04  mov     edx, 66h ; 'f'
0x180009b09  mov     r9d, edi
0x180009b0c  lea     r8, WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids
0x180009b13  mov     rcx, [rcx+10h]
0x180009b17  call    WPP_SF_d
0x180009b1c  nop
0x180009b1d  cmp     [rsp+108h+var_90], sil
0x180009b22  jnz     short loc_180009B3A
0x180009b24  mov     rcx, [rsp+108h+var_88]
0x180009b2c  mov     rax, [rsp+108h+var_80]
0x180009b34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b39  nop
0x180009b3a  cmp     [rsp+108h+var_78], sil
0x180009b42  jnz     short loc_180009B5A
0x180009b44  mov     rcx, [rsp+108h+var_70]
0x180009b4c  mov     rax, [rsp+108h+var_68]
0x180009b54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b59  nop
0x180009b5a  mov     rcx, [rsp+108h+var_C4]
0x180009b5f  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180009b65  nop
0x180009b66  mov     rcx, [rsp+108h+var_B4]
0x180009b6b  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180009b71  nop
0x180009b72  mov     rax, [rbx]
0x180009b75  xor     edx, edx
0x180009b77  mov     rcx, rbx
0x180009b7a  mov     rax, [rax+120h]
0x180009b81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b86  mov     eax, edi
0x180009b88  jmp     loc_1800099AD
0x180009b8d  cmp     byte ptr [rcx+19h], 2
0x180009b91  jb      loc_18000990C
0x180009b97  mov     edx, 68h ; 'h'
0x180009b9c  mov     r9d, edi
0x180009b9f  lea     r8, WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids
0x180009ba6  mov     rcx, [rcx+10h]
0x180009baa  call    WPP_SF_d
0x180009baf  jmp     loc_18000990C
0x180009bb4  test    byte ptr [rcx+1Ch], 1
0x180009bb8  jz      loc_180009A2C
0x180009bbe  cmp     byte ptr [rcx+19h], 2
0x180009bc2  jb      loc_180009A2C
0x180009bc8  mov     edx, 67h ; 'g'
0x180009bcd  mov     r9d, edi
0x180009bd0  lea     r8, WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids
0x180009bd7  mov     rcx, [rcx+10h]
0x180009bdb  call    WPP_SF_d
0x180009be0  jmp     loc_180009A2C
0x180009be5  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180009beb  mov     edx, edi
0x180009bed  mov     rcx, rax
0x180009bf0  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180009bf6  jmp     loc_1800098EF
0x180009bfb  mov     eax, 80041006h
0x180009c00  jmp     loc_1800099AD
```
