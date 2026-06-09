# CBasicQualifierSet::Compare(CBasicQualifierSet &,uchar,ushort const * *,ulong)

- ea: `0x180066260`
- end: `0x1800667e3`
- name: `?Compare@CBasicQualifierSet@@QEAAHAEAV1@EPEAPEBGK@Z`
- size: `1411`
- prototype: `__int64 __usercall@<rax>(CBasicQualifierSet *__hidden this@<rcx>, struct CBasicQualifierSet *@<rdx>, unsigned __int8@<r8b>, const unsigned __int16 **@<r9>, unsigned int)`
- caller_count: `3`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18002b170`
- `0x1800459b0`
- `0x1800808b0`

## callees

- `0x180004060`
- `0x18000a6c0`
- `0x18000aae0`
- `0x18000b070`
- `0x18000c770`
- `0x180035b08`
- `0x180066260`
- `0x18006fa4c`
- `0x18006fa66`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x1800665d3`
- `wbemcomn!GetMemLogObject` at `0x180066635`
- `wbemcomn!GetMemLogObject` at `0x180066725`
- `wbemcomn!GetMemLogObject` at `0x180066784`
- `wbemcomn!GetMemLogObject` at `0x1800665d3`
- `wbemcomn!GetMemLogObject` at `0x180066635`
- `wbemcomn!GetMemLogObject` at `0x180066725`
- `wbemcomn!GetMemLogObject` at `0x180066784`
- `wbemcomn!??8CVar@@QEAAHAEAV0@@Z` at `0x1800664c0`
- `wbemcomn!??8CVar@@QEAAHAEAV0@@Z` at `0x1800664c0`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x180066450`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x18006645b`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x180066450`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x18006645b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800665e1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180066643`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180066733`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180066792`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800665e1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180066643`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180066733`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180066792`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800664cc`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800664d7`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800664cc`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800664d7`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18006631c`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180066327`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180066332`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18006633d`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800663a6`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800663b1`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800663bc`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800663c7`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800664f3`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18006631c`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180066327`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180066332`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18006633d`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800663a6`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800663b1`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800663bc`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800663c7`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800664f3`
- `OLEAUT32!__imp_SysFreeString` at `0x18006669e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800666e5`
- `OLEAUT32!__imp_SysFreeString` at `0x18006669e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800666e5`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CBasicQualifierSet::Compare(
        CFastHeap **this,
        CFastHeap **a2,
        unsigned __int8 a3,
        const unsigned __int16 **a4,
        unsigned int a5)
{
  const unsigned __int16 **v5; // r13
  int v8; // eax
  int v9; // ebx
  void *v10; // rcx
  int v12; // r14d
  int v13; // esi
  unsigned int v14; // edi
  int v15; // esi
  const unsigned __int16 **v16; // r12
  const unsigned __int16 **v17; // r15
  struct CQualifier *QualifierLocally; // r15
  struct CQualifier *v19; // rax
  struct CQualifier *v20; // rdi
  int v21; // r15d
  __int64 v22; // r12
  const unsigned __int16 *v23; // rax
  int v24; // edi
  char *v25; // r13
  const unsigned __int16 *v26; // r15
  const unsigned __int16 *v27; // rax
  int v28; // edi
  char *v29; // r13
  const unsigned __int16 *v30; // r15
  BSTR *v31; // r12
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v33; // rax
  void *v34; // rcx
  CMemoryLog *v35; // rax
  CMemoryLog *v36; // rax
  _BYTE pExceptionObject[4]; // [rsp+38h] [rbp-71h] BYREF
  int v38; // [rsp+3Ch] [rbp-6Dh] BYREF
  int v39; // [rsp+40h] [rbp-69h] BYREF
  char *v40; // [rsp+44h] [rbp-65h]
  int v41; // [rsp+50h] [rbp-59h] BYREF
  char *v42; // [rsp+54h] [rbp-55h]
  void *v43; // [rsp+60h] [rbp-49h]
  int v44; // [rsp+68h] [rbp-41h] BYREF
  void *v45; // [rsp+6Ch] [rbp-3Dh]
  int v46; // [rsp+78h] [rbp-31h] BYREF
  void *v47; // [rsp+7Ch] [rbp-2Dh]
  _BYTE v48[32]; // [rsp+88h] [rbp-21h] BYREF
  _BYTE v49[80]; // [rsp+A8h] [rbp-1h] BYREF

  v5 = a4;
  v39 = 0;
  v40 = 0;
  v44 = 0;
  v45 = 0;
  v41 = 0;
  v42 = 0;
  v46 = 0;
  v47 = 0;
  v8 = CBasicQualifierSet::EnumPrimaryQualifiers(
         (CBasicQualifierSet *)this,
         a3,
         0,
         (struct CFixedBSTRArray *)&v39,
         (struct CFixedBSTRArray *)&v44);
  if ( v8 < 0 )
  {
    if ( v8 == -2147217402 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, -2);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          25,
          WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids,
          "CX_MemoryException()");
      }
      throw (CX_MemoryException *)pExceptionObject;
    }
    CWin32DefaultArena::WbemMemFree(0);
    v10 = 0;
    goto LABEL_5;
  }
  v9 = CBasicQualifierSet::EnumPrimaryQualifiers(
         (CBasicQualifierSet *)a2,
         a3,
         0,
         (struct CFixedBSTRArray *)&v41,
         (struct CFixedBSTRArray *)&v46);
  if ( v9 < 0 )
  {
    CFixedBSTRArray::Free((CFixedBSTRArray *)&v39);
    CFixedBSTRArray::Free((CFixedBSTRArray *)&v44);
    if ( v9 == -2147217402 )
    {
      v33 = GetMemLogObject();
      CMemoryLog::Write(v33, -2);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          26,
          WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids,
          "CX_MemoryException()");
      }
      throw (CX_MemoryException *)pExceptionObject;
    }
    CWin32DefaultArena::WbemMemFree(v47);
    v10 = v42;
LABEL_5:
    CWin32DefaultArena::WbemMemFree(v10);
    CWin32DefaultArena::WbemMemFree(v45);
    CWin32DefaultArena::WbemMemFree(v40);
    return 0;
  }
  if ( v5 && (v21 = 0, v38 = 0, a5) )
  {
    v12 = v39;
    v13 = v41;
    do
    {
      v22 = v21;
      if ( v40 )
      {
        v23 = v5[v21];
        v24 = 0;
        if ( v12 > 0 )
        {
          v25 = v40;
          v26 = v23;
          do
          {
            v43 = &v25[8 * v24];
            if ( !(unsigned int)wbem_wcsicmp(v26, *(const unsigned __int16 **)v43) )
            {
              SysFreeString(*(BSTR *)v43);
              v34 = v43;
              *(_QWORD *)v43 = 0;
              memcpy_0(v34, &v25[8 * v24 + 8], 8LL * (v12 - v24 - 1));
              v39 = --v12;
              --v24;
            }
            ++v24;
          }
          while ( v24 < v12 );
          v21 = v38;
          v5 = a4;
        }
      }
      if ( v42 )
      {
        v27 = v5[v22];
        v28 = 0;
        if ( v13 > 0 )
        {
          v29 = v42;
          v30 = v27;
          do
          {
            v31 = (BSTR *)&v29[8 * v28];
            if ( !(unsigned int)wbem_wcsicmp(v30, *v31) )
            {
              SysFreeString(*v31);
              *v31 = 0;
              memcpy_0(v31, &v29[8 * v28 + 8], 8LL * (v13 - v28 - 1));
              v41 = --v13;
              --v28;
            }
            ++v28;
          }
          while ( v28 < v13 );
          v21 = v38;
          v5 = a4;
        }
      }
      v38 = ++v21;
    }
    while ( v21 < a5 );
  }
  else
  {
    v12 = v39;
    v13 = v41;
  }
  if ( v12 == v13 )
  {
    v14 = 1;
    v15 = 0;
    v16 = (const unsigned __int16 **)v42;
    while ( v14 && v15 < v12 )
    {
      v17 = (const unsigned __int16 **)v40;
      if ( !(unsigned int)wbem_wcsicmp(*(const unsigned __int16 **)&v40[8 * v15], v16[v15])
        && (v38 = 0,
            QualifierLocally = CBasicQualifierSet::GetQualifierLocally((CBasicQualifierSet *)this, v17[v15], &v38),
            v38 = 0,
            v19 = CBasicQualifierSet::GetQualifierLocally((CBasicQualifierSet *)a2, v16[v15], &v38),
            v20 = v19,
            QualifierLocally)
        && v19
        && *((_BYTE *)QualifierLocally + 4) == *((_BYTE *)v19 + 4) )
      {
        CVar::CVar((CVar *)v49);
        CVar::CVar((CVar *)v48);
        if ( !CUntypedValue::StoreToCVar(
                (unsigned int *)((char *)QualifierLocally + 9),
                *(_DWORD *)((char *)QualifierLocally + 5),
                (CVar *)v49,
                this[2],
                0) )
        {
          v36 = GetMemLogObject();
          CMemoryLog::Write(v36, -2);
          if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_s(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              27,
              WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids,
              "CX_MemoryException()");
          }
          throw (CX_MemoryException *)pExceptionObject;
        }
        if ( !CUntypedValue::StoreToCVar(
                (unsigned int *)((char *)v20 + 9),
                *(_DWORD *)((char *)v20 + 5),
                (CVar *)v48,
                a2[2],
                0) )
        {
          v35 = GetMemLogObject();
          CMemoryLog::Write(v35, -2);
          if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_s(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              28,
              WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids,
              "CX_MemoryException()");
          }
          throw (CX_MemoryException *)pExceptionObject;
        }
        if ( *(_DWORD *)((char *)QualifierLocally + 5) == *(_DWORD *)((char *)v20 + 5) )
          v14 = CVar::operator==(v49, v48);
        else
          v14 = 0;
        CVar::~CVar((CVar *)v48);
        CVar::~CVar((CVar *)v49);
      }
      else
      {
        v14 = 0;
      }
      ++v15;
    }
  }
  else
  {
    v14 = 0;
  }
  CFixedBSTRArray::Free((CFixedBSTRArray *)&v39);
  CFixedBSTRArray::Free((CFixedBSTRArray *)&v44);
  CFixedBSTRArray::Free((CFixedBSTRArray *)&v41);
  CFixedBSTRArray::Free((CFixedBSTRArray *)&v46);
  CWin32DefaultArena::WbemMemFree(v47);
  CWin32DefaultArena::WbemMemFree(v42);
  CWin32DefaultArena::WbemMemFree(v45);
  CWin32DefaultArena::WbemMemFree(v40);
  return v14;
}

```

## disassembly

```asm
0x180066260  mov     rax, rsp
0x180066263  mov     [rax+18h], rbx
0x180066267  mov     [rax+20h], r9
0x18006626b  mov     [rax+10h], rdx
0x18006626f  mov     [rax+8], rcx
0x180066273  push    rbp
0x180066274  push    rsi
0x180066275  push    rdi
0x180066276  push    r12
0x180066278  push    r13
0x18006627a  push    r14
0x18006627c  push    r15
0x18006627e  lea     rbp, [rax-57h]
0x180066282  sub     rsp, 0C0h
0x180066289  mov     r13, r9
0x18006628c  mov     bl, r8b
0x18006628f  mov     rdi, rdx
0x180066292  mov     rax, rcx
0x180066295  xor     r12d, r12d
0x180066298  mov     [rbp+4Fh+var_B8], r12d
0x18006629c  mov     [rbp+4Fh+var_B4], r12
0x1800662a0  mov     [rbp+4Fh+var_90], r12d
0x1800662a4  mov     [rbp+4Fh+var_8C], r12
0x1800662a8  mov     [rbp+4Fh+var_A8], r12d
0x1800662ac  mov     [rbp+4Fh+var_A4], r12
0x1800662b0  mov     [rbp+4Fh+var_80], r12d
0x1800662b4  mov     [rbp+4Fh+var_7C], r12
0x1800662b8  lea     rcx, [rbp+4Fh+var_90]
0x1800662bc  mov     [rsp+20h], rcx; struct CFixedBSTRArray *
0x1800662c1  lea     r9, [rbp+4Fh+var_B8]; struct CFixedBSTRArray *
0x1800662c5  xor     r8d, r8d; unsigned __int8
0x1800662c8  mov     dl, bl; unsigned __int8
0x1800662ca  mov     rcx, rax; this
0x1800662cd  call    ?EnumPrimaryQualifiers@CBasicQualifierSet@@QEAAJEEAEAVCFixedBSTRArray@@0@Z; CBasicQualifierSet::EnumPrimaryQualifiers(uchar,uchar,CFixedBSTRArray &,CFixedBSTRArray &)
0x1800662d2  test    eax, eax
0x1800662d4  js      loc_1800664E6
0x1800662da  lea     rax, [rbp+4Fh+var_80]
0x1800662de  mov     [rsp+20h], rax; struct CFixedBSTRArray *
0x1800662e3  lea     r9, [rbp+4Fh+var_A8]; struct CFixedBSTRArray *
0x1800662e7  xor     r8d, r8d; unsigned __int8
0x1800662ea  mov     dl, bl; unsigned __int8
0x1800662ec  mov     rcx, rdi; this
0x1800662ef  call    ?EnumPrimaryQualifiers@CBasicQualifierSet@@QEAAJEEAEAVCFixedBSTRArray@@0@Z; CBasicQualifierSet::EnumPrimaryQualifiers(uchar,uchar,CFixedBSTRArray &,CFixedBSTRArray &)
0x1800662f4  mov     ebx, eax
0x1800662f6  test    eax, eax
0x1800662f8  jns     short loc_180066360
0x1800662fa  lea     rcx, [rbp+4Fh+var_B8]; this
0x1800662fe  call    ?Free@CFixedBSTRArray@@QEAAXXZ; CFixedBSTRArray::Free(void)
0x180066303  lea     rcx, [rbp+4Fh+var_90]; this
0x180066307  call    ?Free@CFixedBSTRArray@@QEAAXXZ; CFixedBSTRArray::Free(void)
0x18006630c  cmp     ebx, 80041006h
0x180066312  jz      loc_180066635
0x180066318  mov     rcx, [rbp+4Fh+var_7C]
0x18006631c  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180066322  nop
0x180066323  mov     rcx, [rbp+4Fh+var_A4]
0x180066327  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18006632d  nop
0x18006632e  mov     rcx, [rbp+4Fh+var_8C]
0x180066332  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180066338  nop
0x180066339  mov     rcx, [rbp+4Fh+var_B4]
0x18006633d  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180066343  xor     eax, eax
0x180066345  mov     rbx, [rsp+0F0h+arg_10]
0x18006634d  add     rsp, 0C0h
0x180066354  pop     r15
0x180066356  pop     r14
0x180066358  pop     r13
0x18006635a  pop     r12
0x18006635c  pop     rdi
0x18006635d  pop     rsi
0x18006635e  pop     rbp
0x18006635f  retn
0x180066360  mov     ebx, 1
0x180066365  test    r13, r13
0x180066368  jnz     loc_180066501
0x18006636e  mov     r14d, [rbp+4Fh+var_B8]
0x180066372  mov     esi, [rbp+4Fh+var_A8]
0x180066375  cmp     r14d, esi
0x180066378  jz      short loc_1800663D4
0x18006637a  mov     edi, r12d
0x18006637d  lea     rcx, [rbp+4Fh+var_B8]; this
0x180066381  call    ?Free@CFixedBSTRArray@@QEAAXXZ; CFixedBSTRArray::Free(void)
0x180066386  lea     rcx, [rbp+4Fh+var_90]; this
0x18006638a  call    ?Free@CFixedBSTRArray@@QEAAXXZ; CFixedBSTRArray::Free(void)
0x18006638f  lea     rcx, [rbp+4Fh+var_A8]; this
0x180066393  call    ?Free@CFixedBSTRArray@@QEAAXXZ; CFixedBSTRArray::Free(void)
0x180066398  lea     rcx, [rbp+4Fh+var_80]; this
0x18006639c  call    ?Free@CFixedBSTRArray@@QEAAXXZ; CFixedBSTRArray::Free(void)
0x1800663a1  nop
0x1800663a2  mov     rcx, [rbp+4Fh+var_7C]
0x1800663a6  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800663ac  nop
0x1800663ad  mov     rcx, [rbp+4Fh+var_A4]
0x1800663b1  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800663b7  nop
0x1800663b8  mov     rcx, [rbp+4Fh+var_8C]
0x1800663bc  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800663c2  nop
0x1800663c3  mov     rcx, [rbp+4Fh+var_B4]
0x1800663c7  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800663cd  mov     eax, edi
0x1800663cf  jmp     loc_180066345
0x1800663d4  mov     edi, ebx
0x1800663d6  mov     esi, r12d
0x1800663d9  mov     r12, [rbp+4Fh+var_A4]
0x1800663dd  mov     r13, [rbp+4Fh+arg_8]
0x1800663e1  test    edi, edi
0x1800663e3  jz      short loc_18006637D
0x1800663e5  cmp     esi, r14d
0x1800663e8  jge     short loc_18006637D
0x1800663ea  movsxd  rdi, esi
0x1800663ed  mov     rdx, [r12+rdi*8]; unsigned __int16 *
0x1800663f1  mov     r15, [rbp+4Fh+var_B4]
0x1800663f5  mov     rcx, [r15+rdi*8]; unsigned __int16 *
0x1800663f9  call    ?wbem_wcsicmp@@YAHPEBG0@Z; wbem_wcsicmp(ushort const *,ushort const *)
0x1800663fe  test    eax, eax
0x180066400  jnz     short loc_180066446
0x180066402  mov     [rbp+4Fh+var_BC], eax
0x180066405  lea     r8, [rbp+4Fh+var_BC]; int *
0x180066409  mov     rdx, [r15+rdi*8]; unsigned __int16 *
0x18006640d  mov     rcx, [rbp+4Fh+arg_0]; this
0x180066411  call    ?GetQualifierLocally@CBasicQualifierSet@@QEAAPEAUCQualifier@@PEBGAEAH@Z; CBasicQualifierSet::GetQualifierLocally(ushort const *,int &)
0x180066416  mov     r15, rax
0x180066419  mov     [rbp+4Fh+var_BC], 0
0x180066420  lea     r8, [rbp+4Fh+var_BC]; int *
0x180066424  mov     rdx, [r12+rdi*8]; unsigned __int16 *
0x180066428  mov     rcx, r13; this
0x18006642b  call    ?GetQualifierLocally@CBasicQualifierSet@@QEAAPEAUCQualifier@@PEBGAEAH@Z; CBasicQualifierSet::GetQualifierLocally(ushort const *,int &)
0x180066430  mov     rdi, rax
0x180066433  test    r15, r15
0x180066436  jz      short loc_180066446
0x180066438  test    rax, rax
0x18006643b  jz      short loc_180066446
0x18006643d  mov     cl, [rax+4]
0x180066440  cmp     [r15+4], cl
0x180066444  jz      short loc_18006644C
0x180066446  xor     edi, edi
0x180066448  add     esi, ebx
0x18006644a  jmp     short loc_1800663E1
0x18006644c  lea     rcx, [rbp+4Fh+var_50]
0x180066450  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x180066456  nop
0x180066457  lea     rcx, [rbp+4Fh+var_70]
0x18006645b  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x180066461  nop
0x180066462  lea     rcx, [r15+9]
0x180066466  mov     dword ptr [rsp+20h], 0
0x18006646e  mov     rax, [rbp+4Fh+arg_0]
0x180066472  mov     r9, [rax+10h]
0x180066476  lea     r8, [rbp+4Fh+var_50]
0x18006647a  mov     edx, [r15+5]
0x18006647e  call    ?StoreToCVar@CUntypedValue@@QEAAHVCType@@AEAVCVar@@PEAVCFastHeap@@H@Z; CUntypedValue::StoreToCVar(CType,CVar &,CFastHeap *,int)
0x180066483  test    eax, eax
0x180066485  jz      loc_180066784
0x18006648b  lea     rcx, [rdi+9]
0x18006648f  mov     dword ptr [rsp+20h], 0
0x180066497  mov     r9, [r13+10h]
0x18006649b  lea     r8, [rbp+4Fh+var_70]
0x18006649f  mov     edx, [rdi+5]
0x1800664a2  call    ?StoreToCVar@CUntypedValue@@QEAAHVCType@@AEAVCVar@@PEAVCFastHeap@@H@Z; CUntypedValue::StoreToCVar(CType,CVar &,CFastHeap *,int)
0x1800664a7  test    eax, eax
0x1800664a9  jz      loc_180066725
0x1800664af  mov     eax, [rdi+5]
0x1800664b2  cmp     [r15+5], eax
0x1800664b6  jnz     short loc_1800664E2
0x1800664b8  lea     rdx, [rbp+4Fh+var_70]
0x1800664bc  lea     rcx, [rbp+4Fh+var_50]
0x1800664c0  call    cs:__imp_??8CVar@@QEAAHAEAV0@@Z; CVar::operator==(CVar &)
0x1800664c6  mov     edi, eax
0x1800664c8  lea     rcx, [rbp+4Fh+var_70]
0x1800664cc  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800664d2  nop
0x1800664d3  lea     rcx, [rbp+4Fh+var_50]
0x1800664d7  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800664dd  jmp     loc_180066448
0x1800664e2  xor     edi, edi
0x1800664e4  jmp     short loc_1800664C8
0x1800664e6  cmp     eax, 80041006h
0x1800664eb  jz      loc_1800665D3
0x1800664f1  xor     ecx, ecx
0x1800664f3  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800664f9  nop
0x1800664fa  xor     ecx, ecx
0x1800664fc  jmp     loc_180066327
0x180066501  mov     r15d, r12d
0x180066504  mov     [rbp+4Fh+var_BC], r12d
0x180066508  cmp     [rbp+4Fh+arg_20], r12d
0x18006650c  jbe     loc_18006636E
0x180066512  mov     r14d, [rbp+4Fh+var_B8]
0x180066516  mov     esi, [rbp+4Fh+var_A8]
0x180066519  movsxd  r12, r15d
0x18006651c  cmp     [rbp+4Fh+var_B4], 0
0x180066521  jnz     short loc_18006653F
0x180066523  cmp     [rbp+4Fh+var_A4], 0
0x180066528  jnz     short loc_180066588
0x18006652a  xor     r12d, r12d
0x18006652d  add     r15d, ebx
0x180066530  mov     [rbp+4Fh+var_BC], r15d
0x180066534  cmp     r15d, [rbp+4Fh+arg_20]
0x180066538  jb      short loc_180066519
0x18006653a  jmp     loc_180066375
0x18006653f  mov     rax, [r13+r12*8+0]
0x180066544  xor     edi, edi
0x180066546  test    r14d, r14d
0x180066549  jle     short loc_180066523
0x18006654b  mov     r13, [rbp+4Fh+var_B4]
0x18006654f  mov     r15, rax
0x180066552  movsxd  rax, edi
0x180066555  lea     rax, ds:0[rax*8]
0x18006655d  add     rax, r13
0x180066560  mov     [rbp+4Fh+var_98], rax
0x180066564  mov     rdx, [rax]; unsigned __int16 *
0x180066567  mov     rcx, r15; unsigned __int16 *
0x18006656a  call    ?wbem_wcsicmp@@YAHPEBG0@Z; wbem_wcsicmp(ushort const *,ushort const *)
0x18006656f  test    eax, eax
0x180066571  jz      loc_180066697
0x180066577  add     edi, ebx
0x180066579  cmp     edi, r14d
0x18006657c  jl      short loc_180066552
0x18006657e  mov     r15d, [rbp+4Fh+var_BC]
0x180066582  mov     r13, [rbp+4Fh+arg_18]
0x180066586  jmp     short loc_180066523
0x180066588  mov     rax, [r13+r12*8+0]
0x18006658d  xor     r12d, r12d
0x180066590  mov     edi, r12d
0x180066593  test    esi, esi
0x180066595  jle     short loc_18006652D
0x180066597  mov     r13, [rbp+4Fh+var_A4]
0x18006659b  mov     r15, rax
0x18006659e  movsxd  rax, edi
0x1800665a1  lea     r12, ds:0[rax*8]
0x1800665a9  add     r12, r13
0x1800665ac  mov     rdx, [r12]; unsigned __int16 *
0x1800665b0  mov     rcx, r15; unsigned __int16 *
0x1800665b3  call    ?wbem_wcsicmp@@YAHPEBG0@Z; wbem_wcsicmp(ushort const *,ushort const *)
0x1800665b8  test    eax, eax
0x1800665ba  jz      loc_1800666E1
0x1800665c0  add     edi, ebx
0x1800665c2  cmp     edi, esi
0x1800665c4  jl      short loc_18006659E
0x1800665c6  mov     r15d, [rbp+4Fh+var_BC]
0x1800665ca  mov     r13, [rbp+4Fh+arg_18]
0x1800665ce  jmp     loc_18006652A
0x1800665d3  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800665d9  mov     edx, 0FFFFFFFEh
0x1800665de  mov     rcx, rax
0x1800665e1  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800665e7  lea     rax, WPP_GLOBAL_Control
0x1800665ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800665f5  cmp     rcx, rax
0x1800665f8  jz      short loc_180066624
0x1800665fa  mov     ebx, 1
0x1800665ff  test    [rcx+1Ch], bl
0x180066602  jz      short loc_180066624
0x180066604  cmp     byte ptr [rcx+19h], 2
0x180066608  jb      short loc_180066624
0x18006660a  lea     edx, [rbx+18h]
0x18006660d  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x180066614  lea     r8, WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids
0x18006661b  mov     rcx, [rcx+10h]
0x18006661f  call    WPP_SF_s
0x180066624  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x18006662b  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x18006662f  call    _CxxThrowException_0
0x180066635  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18006663b  mov     edx, 0FFFFFFFEh
0x180066640  mov     rcx, rax
0x180066643  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180066649  lea     rax, WPP_GLOBAL_Control
0x180066650  mov     rcx, cs:WPP_GLOBAL_Control
0x180066657  cmp     rcx, rax
0x18006665a  jz      short loc_180066686
0x18006665c  mov     ebx, 1
0x180066661  test    [rcx+1Ch], bl
0x180066664  jz      short loc_180066686
0x180066666  cmp     byte ptr [rcx+19h], 2
0x18006666a  jb      short loc_180066686
0x18006666c  lea     edx, [rbx+19h]
0x18006666f  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x180066676  lea     r8, WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids
0x18006667d  mov     rcx, [rcx+10h]
0x180066681  call    WPP_SF_s
0x180066686  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x18006668d  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x180066691  call    _CxxThrowException_0
0x180066697  mov     rcx, [rbp+4Fh+var_98]
0x18006669b  mov     rcx, [rcx]; bstrString
0x18006669e  call    cs:__imp_SysFreeString
0x1800666a4  mov     rcx, [rbp+4Fh+var_98]; void *
0x1800666a8  mov     qword ptr [rcx], 0
0x1800666af  mov     eax, r14d
0x1800666b2  sub     eax, edi
0x1800666b4  sub     eax, ebx
0x1800666b6  movsxd  r8, eax
0x1800666b9  shl     r8, 3; Size
0x1800666bd  lea     eax, [rdi+1]
0x1800666c0  movsxd  rdx, eax
0x1800666c3  lea     rdx, ds:0[rdx*8]
  ... truncated ...
```
