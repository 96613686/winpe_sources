# CQualifierSet::Compare(CQualifierSet &,CFixedBSTRArray *,int)

- ea: `0x180067b60`
- end: `0x180068019`
- name: `?Compare@CQualifierSet@@QEAAHAEAV1@PEAVCFixedBSTRArray@@H@Z`
- size: `1209`
- prototype: `__int64 __fastcall(CQualifierSet *__hidden this, struct CQualifierSet *, struct CFixedBSTRArray *, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18002d910`
- `0x180071030`

## callees

- `0x180004060`
- `0x1800097b0`
- `0x180009c0c`
- `0x18000b070`
- `0x18000d5a0`
- `0x180035b08`
- `0x18005b010`
- `0x180067b60`
- `0x18006fa4c`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180067bee`
- `wbemcomn!GetMemLogObject` at `0x180067cb3`
- `wbemcomn!GetMemLogObject` at `0x180067efb`
- `wbemcomn!GetMemLogObject` at `0x180067f5c`
- `wbemcomn!GetMemLogObject` at `0x180067bee`
- `wbemcomn!GetMemLogObject` at `0x180067cb3`
- `wbemcomn!GetMemLogObject` at `0x180067efb`
- `wbemcomn!GetMemLogObject` at `0x180067f5c`
- `wbemcomn!??8CVar@@QEAAHAEAV0@@Z` at `0x180067ec3`
- `wbemcomn!??8CVar@@QEAAHAEAV0@@Z` at `0x180067ec3`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x180067e3b`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x180067e46`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x180067e3b`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x180067e46`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180067bfc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180067cc1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180067f09`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180067f6a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180067bfc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180067cc1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180067f09`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180067f6a`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180067ed3`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180067ede`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180067ed3`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180067ede`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180067c7b`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180067c86`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180067feb`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180067ff6`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180067c7b`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180067c86`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180067feb`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180067ff6`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CQualifierSet::Compare(CFastHeap **this, CFastHeap **a2, struct CFixedBSTRArray *a3, int a4)
{
  int v4; // r15d
  CQualifierSet *v7; // r14
  int v8; // eax
  CMemoryLog *MemLogObject; // rax
  int v11; // eax
  CMemoryLog *v12; // rax
  int v13; // eax
  unsigned int v14; // ebx
  int v15; // esi
  int i; // edi
  int v17; // eax
  struct CQualifier *Qualifier; // rdi
  const unsigned __int16 **v19; // rdx
  struct CQualifier *v20; // rax
  struct CQualifier *v21; // rbx
  int v22; // r14d
  int v23; // r15d
  CFastHeap *v24; // r9
  CFastHeap *v25; // r9
  CMemoryLog *v26; // rax
  CMemoryLog *v27; // rax
  int pExceptionObject; // [rsp+38h] [rbp-89h] BYREF
  int v29; // [rsp+40h] [rbp-81h] BYREF
  char *v30; // [rsp+44h] [rbp-7Dh]
  int v31; // [rsp+50h] [rbp-71h] BYREF
  char *v32; // [rsp+54h] [rbp-6Dh]
  int v33; // [rsp+60h] [rbp-61h] BYREF
  int v34; // [rsp+64h] [rbp-5Dh] BYREF
  _BYTE v35[8]; // [rsp+68h] [rbp-59h] BYREF
  __int64 v36; // [rsp+70h] [rbp-51h]
  void (__fastcall *v37)(__int64); // [rsp+78h] [rbp-49h]
  _BYTE v38[8]; // [rsp+80h] [rbp-41h] BYREF
  __int64 v39; // [rsp+88h] [rbp-39h]
  void (__fastcall *v40)(__int64); // [rsp+90h] [rbp-31h]
  _BYTE v41[32]; // [rsp+A0h] [rbp-21h] BYREF
  _BYTE v42[88]; // [rsp+C0h] [rbp-1h] BYREF

  v4 = a4;
  v7 = (CQualifierSet *)this;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  MakeObjGuard<CFixedBSTRArray,void (CFixedBSTRArray::*)(void)>(v38, &v29);
  MakeObjGuard<CFixedBSTRArray,void (CFixedBSTRArray::*)(void)>(v35, &v31);
  v8 = CQualifierSet::EnumQualifiers(v7, 0, 0, (struct CFixedBSTRArray *)&v29);
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
          106,
          WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids,
          "CX_MemoryException()");
      }
      throw (CX_MemoryException *)&pExceptionObject;
    }
    if ( !v35[0] )
      v37(v36);
    if ( !v38[0] )
      v40(v39);
LABEL_12:
    CWin32DefaultArena::WbemMemFree(v32);
    CWin32DefaultArena::WbemMemFree(v30);
    return 0;
  }
  v11 = CQualifierSet::EnumQualifiers((CQualifierSet *)a2, 0, 0, (struct CFixedBSTRArray *)&v31);
  if ( v11 < 0 )
  {
    if ( v11 == -2147217402 )
    {
      v12 = GetMemLogObject();
      CMemoryLog::Write(v12, -2);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          107,
          WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids,
          "CX_MemoryException()");
      }
      throw (CX_MemoryException *)&pExceptionObject;
    }
    ObjScopeGuardImpl0<CFixedBSTRArray,void (CFixedBSTRArray::*)(void)>::~ObjScopeGuardImpl0<CFixedBSTRArray,void (CFixedBSTRArray::*)(void)>((__int64)v35);
    ObjScopeGuardImpl0<CFixedBSTRArray,void (CFixedBSTRArray::*)(void)>::~ObjScopeGuardImpl0<CFixedBSTRArray,void (CFixedBSTRArray::*)(void)>((__int64)v38);
    goto LABEL_12;
  }
  v13 = v29;
  if ( v29 == v31 )
  {
    v14 = 1;
    v15 = 0;
    while ( 1 )
    {
      if ( !v14 || v15 >= v13 )
        goto LABEL_67;
      if ( a3 )
      {
        for ( i = 0; ; ++i )
        {
          v17 = 1;
          if ( i >= *(_DWORD *)a3 )
            break;
          if ( !(unsigned int)wbem_wcsicmp(
                                *(const unsigned __int16 **)&v30[8 * v15],
                                *(const unsigned __int16 **)(*(_QWORD *)((char *)a3 + 4) + 8LL * i)) )
          {
            v17 = 0;
            break;
          }
        }
        if ( !v17 )
          goto LABEL_55;
      }
      else if ( v4
             && (unsigned int)wbem_wcsicmp(
                                *(const unsigned __int16 **)&v30[8 * v15],
                                *(const unsigned __int16 **)&v32[8 * v15]) )
      {
        goto LABEL_54;
      }
      v33 = 0;
      v34 = 0;
      Qualifier = CQualifierSet::GetQualifier(v7, *(const unsigned __int16 **)&v30[8 * v15], &v33);
      if ( v4 )
        v19 = (const unsigned __int16 **)&v32[8 * v15];
      else
        v19 = (const unsigned __int16 **)&v30[8 * v15];
      v20 = CQualifierSet::GetQualifier((CQualifierSet *)a2, *v19, &v34);
      v21 = v20;
      if ( !Qualifier || !v20 || (v22 = v33, v23 = v34, v33 != v34) || *((_BYTE *)Qualifier + 4) != *((_BYTE *)v20 + 4) )
      {
LABEL_54:
        v14 = 0;
        goto LABEL_55;
      }
      CVar::CVar((CVar *)v42);
      CVar::CVar((CVar *)v41);
      if ( v22 )
        v24 = this[3];
      else
        v24 = (CFastHeap *)*((_QWORD *)this[7] + 2);
      if ( !CUntypedValue::StoreToCVar(
              (unsigned int *)((char *)Qualifier + 9),
              *(_DWORD *)((char *)Qualifier + 5),
              (CVar *)v42,
              v24,
              0) )
      {
        v27 = GetMemLogObject();
        CMemoryLog::Write(v27, -2);
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            108,
            WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids,
            "CX_MemoryException()");
        }
        throw (CX_MemoryException *)&pExceptionObject;
      }
      if ( v23 )
        v25 = a2[3];
      else
        v25 = (CFastHeap *)*((_QWORD *)a2[7] + 2);
      if ( !CUntypedValue::StoreToCVar(
              (unsigned int *)((char *)v21 + 9),
              *(_DWORD *)((char *)v21 + 5),
              (CVar *)v41,
              v25,
              0) )
      {
        v26 = GetMemLogObject();
        CMemoryLog::Write(v26, -2);
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            109,
            WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids,
            "CX_MemoryException()");
        }
        throw (CX_MemoryException *)&pExceptionObject;
      }
      if ( *(_DWORD *)((char *)Qualifier + 5) == *(_DWORD *)((char *)v21 + 5) )
        v14 = CVar::operator==(v42, v41);
      else
        v14 = 0;
      CVar::~CVar((CVar *)v41);
      CVar::~CVar((CVar *)v42);
LABEL_55:
      ++v15;
      v13 = v29;
      v7 = (CQualifierSet *)this;
      v4 = a4;
    }
  }
  v14 = 0;
LABEL_67:
  if ( !v35[0] )
    v37(v36);
  if ( !v38[0] )
    v40(v39);
  CWin32DefaultArena::WbemMemFree(v32);
  CWin32DefaultArena::WbemMemFree(v30);
  return v14;
}

```

## disassembly

```asm
0x180067b60  mov     rax, rsp
0x180067b63  mov     [rax+10h], rbx
0x180067b67  mov     [rax+20h], r9d
0x180067b6b  mov     [rax+8], rcx
0x180067b6f  push    rbp
0x180067b70  push    rsi
0x180067b71  push    rdi
0x180067b72  push    r12
0x180067b74  push    r13
0x180067b76  push    r14
0x180067b78  push    r15
0x180067b7a  lea     rbp, [rax-5Fh]
0x180067b7e  sub     rsp, 0E0h
0x180067b85  mov     r15d, r9d
0x180067b88  mov     r12, r8
0x180067b8b  mov     r13, rdx
0x180067b8e  mov     r14, rcx
0x180067b91  mov     [rsp+110h+var_D8], 0
0x180067b99  mov     [rbp+57h+var_D4], 0
0x180067ba1  mov     [rbp+57h+var_C8], 0
0x180067ba8  mov     [rbp+57h+var_C4], 0
0x180067bb0  lea     rdx, [rsp+110h+var_D8]
0x180067bb5  lea     rcx, [rbp+57h+var_98]
0x180067bb9  call    ??$MakeObjGuard@VCFixedBSTRArray@@P81@EAAXXZ@@YA?AV?$ObjScopeGuardImpl0@VCFixedBSTRArray@@P81@EAAXXZ@@AEAVCFixedBSTRArray@@P81@EAAXXZ@Z; MakeObjGuard<CFixedBSTRArray,void (CFixedBSTRArray::*)(void)>(CFixedBSTRArray &,void (CFixedBSTRArray::*)(void))
0x180067bbe  nop
0x180067bbf  lea     rdx, [rbp+57h+var_C8]
0x180067bc3  lea     rcx, [rbp+57h+var_B0]
0x180067bc7  call    ??$MakeObjGuard@VCFixedBSTRArray@@P81@EAAXXZ@@YA?AV?$ObjScopeGuardImpl0@VCFixedBSTRArray@@P81@EAAXXZ@@AEAVCFixedBSTRArray@@P81@EAAXXZ@Z; MakeObjGuard<CFixedBSTRArray,void (CFixedBSTRArray::*)(void)>(CFixedBSTRArray &,void (CFixedBSTRArray::*)(void))
0x180067bcc  nop
0x180067bcd  lea     r9, [rsp+110h+var_D8]; struct CFixedBSTRArray *
0x180067bd2  xor     r8d, r8d; unsigned __int8
0x180067bd5  xor     edx, edx; unsigned __int8
0x180067bd7  mov     rcx, r14; this
0x180067bda  call    ?EnumQualifiers@CQualifierSet@@QEAAJEEAEAVCFixedBSTRArray@@@Z; CQualifierSet::EnumQualifiers(uchar,uchar,CFixedBSTRArray &)
0x180067bdf  test    eax, eax
0x180067be1  jns     loc_180067C93
0x180067be7  cmp     eax, 80041006h
0x180067bec  jnz     short loc_180067C4F
0x180067bee  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180067bf4  mov     edx, 0FFFFFFFEh
0x180067bf9  mov     rcx, rax
0x180067bfc  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180067c02  lea     rax, WPP_GLOBAL_Control
0x180067c09  mov     rcx, cs:WPP_GLOBAL_Control
0x180067c10  cmp     rcx, rax
0x180067c13  jz      short loc_180067C3D
0x180067c15  test    byte ptr [rcx+1Ch], 1
0x180067c19  jz      short loc_180067C3D
0x180067c1b  cmp     byte ptr [rcx+19h], 2
0x180067c1f  jb      short loc_180067C3D
0x180067c21  mov     edx, 6Ah ; 'j'
0x180067c26  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x180067c2d  lea     r8, WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids
0x180067c34  mov     rcx, [rcx+10h]
0x180067c38  call    WPP_SF_s
0x180067c3d  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x180067c44  lea     rcx, [rsp+110h+pExceptionObject]; pExceptionObject
0x180067c49  call    _CxxThrowException_0
0x180067c4f  cmp     [rbp+57h+var_B0], 0
0x180067c53  jnz     short loc_180067C63
0x180067c55  mov     rcx, [rbp+57h+var_A8]
0x180067c59  mov     rax, [rbp+57h+var_A0]
0x180067c5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067c62  nop
0x180067c63  cmp     [rbp+57h+var_98], 0
0x180067c67  jnz     short loc_180067C77
0x180067c69  mov     rcx, [rbp+57h+var_90]
0x180067c6d  mov     rax, [rbp+57h+var_88]
0x180067c71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067c76  nop
0x180067c77  mov     rcx, [rbp+57h+var_C4]
0x180067c7b  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180067c81  nop
0x180067c82  mov     rcx, [rbp+57h+var_D4]
0x180067c86  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180067c8c  xor     eax, eax
0x180067c8e  jmp     loc_180067FFE
0x180067c93  lea     r9, [rbp+57h+var_C8]; struct CFixedBSTRArray *
0x180067c97  xor     r8d, r8d; unsigned __int8
0x180067c9a  xor     edx, edx; unsigned __int8
0x180067c9c  mov     rcx, r13; this
0x180067c9f  call    ?EnumQualifiers@CQualifierSet@@QEAAJEEAEAVCFixedBSTRArray@@@Z; CQualifierSet::EnumQualifiers(uchar,uchar,CFixedBSTRArray &)
0x180067ca4  test    eax, eax
0x180067ca6  jns     loc_180067D2C
0x180067cac  cmp     eax, 80041006h
0x180067cb1  jnz     short loc_180067D14
0x180067cb3  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180067cb9  mov     edx, 0FFFFFFFEh
0x180067cbe  mov     rcx, rax
0x180067cc1  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180067cc7  lea     rax, WPP_GLOBAL_Control
0x180067cce  mov     rcx, cs:WPP_GLOBAL_Control
0x180067cd5  cmp     rcx, rax
0x180067cd8  jz      short loc_180067D02
0x180067cda  test    byte ptr [rcx+1Ch], 1
0x180067cde  jz      short loc_180067D02
0x180067ce0  cmp     byte ptr [rcx+19h], 2
0x180067ce4  jb      short loc_180067D02
0x180067ce6  mov     edx, 6Bh ; 'k'
0x180067ceb  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x180067cf2  lea     r8, WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids
0x180067cf9  mov     rcx, [rcx+10h]
0x180067cfd  call    WPP_SF_s
0x180067d02  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x180067d09  lea     rcx, [rsp+110h+pExceptionObject]; pExceptionObject
0x180067d0e  call    _CxxThrowException_0
0x180067d14  lea     rcx, [rbp+57h+var_B0]
0x180067d18  call    ??1?$ObjScopeGuardImpl0@VCFixedBSTRArray@@P81@EAAXXZ@@QEAA@XZ; ObjScopeGuardImpl0<CFixedBSTRArray,void (CFixedBSTRArray::*)(void)>::~ObjScopeGuardImpl0<CFixedBSTRArray,void (CFixedBSTRArray::*)(void)>(void)
0x180067d1d  nop
0x180067d1e  lea     rcx, [rbp+57h+var_98]
0x180067d22  call    ??1?$ObjScopeGuardImpl0@VCFixedBSTRArray@@P81@EAAXXZ@@QEAA@XZ; ObjScopeGuardImpl0<CFixedBSTRArray,void (CFixedBSTRArray::*)(void)>::~ObjScopeGuardImpl0<CFixedBSTRArray,void (CFixedBSTRArray::*)(void)>(void)
0x180067d27  jmp     loc_180067C77
0x180067d2c  mov     eax, [rsp+110h+var_D8]
0x180067d30  cmp     eax, [rbp+57h+var_C8]
0x180067d33  jnz     loc_180067FBD
0x180067d39  mov     ebx, 1
0x180067d3e  xor     esi, esi
0x180067d40  test    ebx, ebx
0x180067d42  jz      loc_180067FBF
0x180067d48  cmp     esi, eax
0x180067d4a  jge     loc_180067FBF
0x180067d50  test    r12, r12
0x180067d53  jz      short loc_180067D92
0x180067d55  xor     edi, edi
0x180067d57  mov     eax, 1
0x180067d5c  cmp     edi, [r12]
0x180067d60  jge     short loc_180067D88
0x180067d62  movsxd  rax, edi
0x180067d65  mov     rdx, [r12+4]
0x180067d6a  movsxd  r8, esi
0x180067d6d  mov     rdx, [rdx+rax*8]; unsigned __int16 *
0x180067d71  mov     rcx, [rbp+57h+var_D4]
0x180067d75  mov     rcx, [rcx+r8*8]; unsigned __int16 *
0x180067d79  call    ?wbem_wcsicmp@@YAHPEBG0@Z; wbem_wcsicmp(ushort const *,ushort const *)
0x180067d7e  test    eax, eax
0x180067d80  jz      short loc_180067D86
0x180067d82  inc     edi
0x180067d84  jmp     short loc_180067D57
0x180067d86  xor     eax, eax
0x180067d88  test    eax, eax
0x180067d8a  jz      loc_180067EE8
0x180067d90  jmp     short loc_180067DB7
0x180067d92  test    r15d, r15d
0x180067d95  jz      short loc_180067DB7
0x180067d97  movsxd  rax, esi
0x180067d9a  mov     rdx, [rbp+57h+var_C4]
0x180067d9e  mov     rdx, [rdx+rax*8]; unsigned __int16 *
0x180067da2  mov     rcx, [rbp+57h+var_D4]
0x180067da6  mov     rcx, [rcx+rax*8]; unsigned __int16 *
0x180067daa  call    ?wbem_wcsicmp@@YAHPEBG0@Z; wbem_wcsicmp(ushort const *,ushort const *)
0x180067daf  test    eax, eax
0x180067db1  jnz     loc_180067EE6
0x180067db7  mov     [rbp+57h+var_B8], 0
0x180067dbe  mov     [rbp+57h+var_B4], 0
0x180067dc5  movsxd  rbx, esi
0x180067dc8  lea     r8, [rbp+57h+var_B8]; int *
0x180067dcc  mov     rdx, [rbp+57h+var_D4]
0x180067dd0  mov     rdx, [rdx+rbx*8]; unsigned __int16 *
0x180067dd4  mov     rcx, r14; this
0x180067dd7  call    ?GetQualifier@CQualifierSet@@QEAAPEAUCQualifier@@PEBGAEAH@Z; CQualifierSet::GetQualifier(ushort const *,int &)
0x180067ddc  mov     rdi, rax
0x180067ddf  test    r15d, r15d
0x180067de2  jz      short loc_180067DEE
0x180067de4  mov     rcx, [rbp+57h+var_C4]
0x180067de8  lea     rdx, [rcx+rbx*8]
0x180067dec  jmp     short loc_180067DF6
0x180067dee  mov     rax, [rbp+57h+var_D4]
0x180067df2  lea     rdx, [rax+rbx*8]
0x180067df6  lea     r8, [rbp+57h+var_B4]; int *
0x180067dfa  mov     rdx, [rdx]; unsigned __int16 *
0x180067dfd  mov     rcx, r13; this
0x180067e00  call    ?GetQualifier@CQualifierSet@@QEAAPEAUCQualifier@@PEBGAEAH@Z; CQualifierSet::GetQualifier(ushort const *,int &)
0x180067e05  mov     rbx, rax
0x180067e08  test    rdi, rdi
0x180067e0b  jz      loc_180067EE6
0x180067e11  test    rax, rax
0x180067e14  jz      loc_180067EE6
0x180067e1a  mov     r14d, [rbp+57h+var_B8]
0x180067e1e  mov     r15d, [rbp+57h+var_B4]
0x180067e22  cmp     r14d, r15d
0x180067e25  jnz     loc_180067EE6
0x180067e2b  mov     cl, [rax+4]
0x180067e2e  cmp     [rdi+4], cl
0x180067e31  jnz     loc_180067EE6
0x180067e37  lea     rcx, [rbp+57h+var_58]
0x180067e3b  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x180067e41  nop
0x180067e42  lea     rcx, [rbp+57h+var_78]
0x180067e46  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x180067e4c  nop
0x180067e4d  mov     rax, [rbp+57h+arg_0]
0x180067e51  test    r14d, r14d
0x180067e54  jz      short loc_180067E5C
0x180067e56  mov     r9, [rax+18h]
0x180067e5a  jmp     short loc_180067E64
0x180067e5c  mov     rax, [rax+38h]
0x180067e60  mov     r9, [rax+10h]
0x180067e64  lea     rcx, [rdi+9]
0x180067e68  mov     dword ptr [rsp+20h], 0
0x180067e70  lea     r8, [rbp+57h+var_58]
0x180067e74  mov     edx, [rdi+5]
0x180067e77  call    ?StoreToCVar@CUntypedValue@@QEAAHVCType@@AEAVCVar@@PEAVCFastHeap@@H@Z; CUntypedValue::StoreToCVar(CType,CVar &,CFastHeap *,int)
0x180067e7c  test    eax, eax
0x180067e7e  jz      loc_180067F5C
0x180067e84  test    r15d, r15d
0x180067e87  jz      short loc_180067E8F
0x180067e89  mov     r9, [r13+18h]
0x180067e8d  jmp     short loc_180067E97
0x180067e8f  mov     rax, [r13+38h]
0x180067e93  mov     r9, [rax+10h]
0x180067e97  lea     rcx, [rbx+9]
0x180067e9b  mov     dword ptr [rsp+20h], 0
0x180067ea3  lea     r8, [rbp+57h+var_78]
0x180067ea7  mov     edx, [rbx+5]
0x180067eaa  call    ?StoreToCVar@CUntypedValue@@QEAAHVCType@@AEAVCVar@@PEAVCFastHeap@@H@Z; CUntypedValue::StoreToCVar(CType,CVar &,CFastHeap *,int)
0x180067eaf  test    eax, eax
0x180067eb1  jz      short loc_180067EFB
0x180067eb3  mov     eax, [rbx+5]
0x180067eb6  cmp     [rdi+5], eax
0x180067eb9  jnz     short loc_180067ECD
0x180067ebb  lea     rdx, [rbp+57h+var_78]
0x180067ebf  lea     rcx, [rbp+57h+var_58]
0x180067ec3  call    cs:__imp_??8CVar@@QEAAHAEAV0@@Z; CVar::operator==(CVar &)
0x180067ec9  mov     ebx, eax
0x180067ecb  jmp     short loc_180067ECF
0x180067ecd  xor     ebx, ebx
0x180067ecf  lea     rcx, [rbp+57h+var_78]
0x180067ed3  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x180067ed9  nop
0x180067eda  lea     rcx, [rbp+57h+var_58]
0x180067ede  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x180067ee4  jmp     short loc_180067EE8
0x180067ee6  xor     ebx, ebx
0x180067ee8  inc     esi
0x180067eea  mov     eax, [rsp+110h+var_D8]
0x180067eee  mov     r14, [rbp+57h+arg_0]
0x180067ef2  mov     r15d, [rbp+57h+arg_18]
0x180067ef6  jmp     loc_180067D40
0x180067efb  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180067f01  mov     edx, 0FFFFFFFEh
0x180067f06  mov     rcx, rax
0x180067f09  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180067f0f  lea     rax, WPP_GLOBAL_Control
0x180067f16  mov     rcx, cs:WPP_GLOBAL_Control
0x180067f1d  cmp     rcx, rax
0x180067f20  jz      short loc_180067F4A
0x180067f22  test    byte ptr [rcx+1Ch], 1
0x180067f26  jz      short loc_180067F4A
0x180067f28  cmp     byte ptr [rcx+19h], 2
0x180067f2c  jb      short loc_180067F4A
0x180067f2e  mov     edx, 6Dh ; 'm'
0x180067f33  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x180067f3a  lea     r8, WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids
0x180067f41  mov     rcx, [rcx+10h]
0x180067f45  call    WPP_SF_s
0x180067f4a  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x180067f51  lea     rcx, [rsp+110h+pExceptionObject]; pExceptionObject
0x180067f56  call    _CxxThrowException_0
0x180067f5c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180067f62  mov     edx, 0FFFFFFFEh
0x180067f67  mov     rcx, rax
0x180067f6a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180067f70  lea     rax, WPP_GLOBAL_Control
0x180067f77  mov     rcx, cs:WPP_GLOBAL_Control
0x180067f7e  cmp     rcx, rax
0x180067f81  jz      short loc_180067FAB
0x180067f83  test    byte ptr [rcx+1Ch], 1
0x180067f87  jz      short loc_180067FAB
0x180067f89  cmp     byte ptr [rcx+19h], 2
0x180067f8d  jb      short loc_180067FAB
0x180067f8f  mov     edx, 6Ch ; 'l'
0x180067f94  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x180067f9b  lea     r8, WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids
0x180067fa2  mov     rcx, [rcx+10h]
0x180067fa6  call    WPP_SF_s
0x180067fab  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x180067fb2  lea     rcx, [rsp+110h+pExceptionObject]; pExceptionObject
0x180067fb7  call    _CxxThrowException_0
0x180067fbd  xor     ebx, ebx
0x180067fbf  cmp     [rbp+57h+var_B0], 0
0x180067fc3  jnz     short loc_180067FD3
0x180067fc5  mov     rcx, [rbp+57h+var_A8]
0x180067fc9  mov     rax, [rbp+57h+var_A0]
0x180067fcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067fd2  nop
0x180067fd3  cmp     [rbp+57h+var_98], 0
0x180067fd7  jnz     short loc_180067FE7
0x180067fd9  mov     rcx, [rbp+57h+var_90]
0x180067fdd  mov     rax, [rbp+57h+var_88]
0x180067fe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067fe6  nop
0x180067fe7  mov     rcx, [rbp+57h+var_C4]
0x180067feb  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180067ff1  nop
0x180067ff2  mov     rcx, [rbp+57h+var_D4]
0x180067ff6  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180067ffc  mov     eax, ebx
0x180067ffe  mov     rbx, [rsp+110h+arg_8]
0x180068006  add     rsp, 0E0h
0x18006800d  pop     r15
  ... truncated ...
```
