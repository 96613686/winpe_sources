# CBasicQualifierSet::CompareLocalizedSet(CBasicQualifierSet &)

- ea: `0x1800808b0`
- end: `0x180080bb9`
- name: `?CompareLocalizedSet@CBasicQualifierSet@@QEAAHAEAV1@@Z`
- size: `777`
- prototype: `__int64 __fastcall(CBasicQualifierSet *__hidden this, struct CBasicQualifierSet *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800459b0`

## callees

- `0x180004060`
- `0x180009c0c`
- `0x18000a6c0`
- `0x18000c770`
- `0x180035b08`
- `0x18005b010`
- `0x180066260`
- `0x18006fa4c`
- `0x1800808b0`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18008094c`
- `wbemcomn!GetMemLogObject` at `0x180080ad0`
- `wbemcomn!GetMemLogObject` at `0x18008094c`
- `wbemcomn!GetMemLogObject` at `0x180080ad0`
- `wbemcomn!?Add@CWStringArray@@QEAAHPEBG@Z` at `0x180080ac6`
- `wbemcomn!?Add@CWStringArray@@QEAAHPEBG@Z` at `0x180080ac6`
- `wbemcomn!??0CWStringArray@@QEAA@HH@Z` at `0x1800808de`
- `wbemcomn!??0CWStringArray@@QEAA@HH@Z` at `0x1800808de`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x1800809db`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x180080b95`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x1800809db`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x180080b95`
- `wbemcomn!?Size@CWStringArray@@QEBAHXZ` at `0x180080b3d`
- `wbemcomn!?Size@CWStringArray@@QEBAHXZ` at `0x180080b3d`
- `wbemcomn!?GetArrayPtr@CWStringArray@@QEAAPEAPEBGXZ` at `0x180080b49`
- `wbemcomn!?GetArrayPtr@CWStringArray@@QEAAPEAPEBGXZ` at `0x180080b49`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008095a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180080ade`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008095a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180080ade`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800809c4`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800809d0`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180080b7e`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180080b8a`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800809c4`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800809d0`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180080b7e`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180080b8a`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CBasicQualifierSet::CompareLocalizedSet(CBasicQualifierSet *this, CFastHeap **a2)
{
  int v4; // eax
  CMemoryLog *v5; // rax
  unsigned int v7; // ebx
  int i; // edi
  struct CQualifier *QualifierLocally; // r14
  struct CQualifier *v10; // rax
  int v11; // eax
  CMemoryLog *MemLogObject; // rax
  unsigned int v13; // ebx
  const unsigned __int16 **ArrayPtr; // rax
  int v15; // [rsp+30h] [rbp-89h] BYREF
  void *v16; // [rsp+34h] [rbp-85h]
  int v17; // [rsp+40h] [rbp-79h] BYREF
  void *v18; // [rsp+44h] [rbp-75h]
  _BYTE v19[24]; // [rsp+58h] [rbp-61h] BYREF
  _BYTE v20[32]; // [rsp+70h] [rbp-49h] BYREF
  _BYTE v21[96]; // [rsp+90h] [rbp-29h] BYREF
  int pExceptionObject; // [rsp+130h] [rbp+77h] BYREF

  CWStringArray::CWStringArray((CWStringArray *)v21, 0, 100);
  v15 = 0;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  MakeObjGuard<CFixedBSTRArray,void (CFixedBSTRArray::*)(void)>(v20, &v15);
  MakeObjGuard<CFixedBSTRArray,void (CFixedBSTRArray::*)(void)>(v19, &v17);
  v4 = CBasicQualifierSet::EnumPrimaryQualifiers(
         this,
         0,
         0,
         (struct CFixedBSTRArray *)&v15,
         (struct CFixedBSTRArray *)&v17);
  if ( v4 >= 0 )
  {
    v7 = 1;
    for ( i = 0; ; ++i )
    {
      if ( !v7 )
      {
LABEL_31:
        ObjScopeGuardImpl0<CFixedBSTRArray,void (CFixedBSTRArray::*)(void)>::~ObjScopeGuardImpl0<CFixedBSTRArray,void (CFixedBSTRArray::*)(void)>((__int64)v19);
        ObjScopeGuardImpl0<CFixedBSTRArray,void (CFixedBSTRArray::*)(void)>::~ObjScopeGuardImpl0<CFixedBSTRArray,void (CFixedBSTRArray::*)(void)>((__int64)v20);
        CWin32DefaultArena::WbemMemFree(v18);
        CWin32DefaultArena::WbemMemFree(v16);
        CWStringArray::~CWStringArray((CWStringArray *)v21);
        return v7;
      }
      if ( i >= v15 )
      {
        v13 = CWStringArray::Size((CWStringArray *)v21);
        ArrayPtr = CWStringArray::GetArrayPtr((CWStringArray *)v21);
        v7 = CBasicQualifierSet::Compare((CFastHeap **)this, a2, 0, ArrayPtr, v13);
        goto LABEL_31;
      }
      pExceptionObject = 0;
      QualifierLocally = CBasicQualifierSet::GetQualifierLocally(
                           this,
                           *((const unsigned __int16 **)v16 + i),
                           &pExceptionObject);
      if ( !QualifierLocally )
        break;
      if ( !(unsigned int)wbem_wcsicmp(*((const unsigned __int16 **)v16 + i), L"amendment")
        || !(unsigned int)wbem_wcsicmp(*((const unsigned __int16 **)v16 + i), L"locale")
        || *((char *)QualifierLocally + 4) < 0 )
      {
        pExceptionObject = 0;
        v10 = CBasicQualifierSet::GetQualifierLocally(
                (CBasicQualifierSet *)a2,
                *((const unsigned __int16 **)v16 + i),
                &pExceptionObject);
        if ( v10 )
        {
          if ( *(_DWORD *)((char *)QualifierLocally + 5) != *(_DWORD *)((char *)v10 + 5) )
            break;
          v7 = ((*((_BYTE *)QualifierLocally + 4) ^ *((_BYTE *)v10 + 4)) & 0x1F) == 0;
          v11 = v7;
        }
        else
        {
          v11 = 1;
        }
        if ( v11 && v7 && CWStringArray::Add((CWStringArray *)v21, *((const unsigned __int16 **)v16 + i)) )
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
              WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids,
              "CX_MemoryException()");
          }
          throw (CX_MemoryException *)&pExceptionObject;
        }
      }
LABEL_29:
      ;
    }
    v7 = 0;
    goto LABEL_29;
  }
  if ( v4 == -2147217402 )
  {
    v5 = GetMemLogObject();
    CMemoryLog::Write(v5, -2);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        29,
        WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  ObjScopeGuardImpl0<CFixedBSTRArray,void (CFixedBSTRArray::*)(void)>::~ObjScopeGuardImpl0<CFixedBSTRArray,void (CFixedBSTRArray::*)(void)>((__int64)v19);
  ObjScopeGuardImpl0<CFixedBSTRArray,void (CFixedBSTRArray::*)(void)>::~ObjScopeGuardImpl0<CFixedBSTRArray,void (CFixedBSTRArray::*)(void)>((__int64)v20);
  CWin32DefaultArena::WbemMemFree(v18);
  CWin32DefaultArena::WbemMemFree(v16);
  CWStringArray::~CWStringArray((CWStringArray *)v21);
  return 0;
}

```

## disassembly

```asm
0x1800808b0  mov     [rsp-8+arg_0], rbx
0x1800808b5  mov     [rsp-8+arg_8], rsi
0x1800808ba  push    rbp
0x1800808bb  push    rdi
0x1800808bc  push    r12
0x1800808be  push    r14
0x1800808c0  push    r15
0x1800808c2  lea     rbp, [rsp-37h]
0x1800808c7  sub     rsp, 0F0h
0x1800808ce  mov     r12, rdx
0x1800808d1  mov     r15, rcx
0x1800808d4  xor     edx, edx
0x1800808d6  lea     r8d, [rdx+64h]
0x1800808da  lea     rcx, [rbp+57h+var_80]
0x1800808de  call    cs:__imp_??0CWStringArray@@QEAA@HH@Z; CWStringArray::CWStringArray(int,int)
0x1800808e4  nop
0x1800808e5  mov     [rsp+110h+var_E0], 0
0x1800808ed  mov     [rsp+110h+var_DC], 0
0x1800808f6  mov     [rbp+57h+var_D0], 0
0x1800808fd  mov     [rbp+57h+var_CC], 0
0x180080905  lea     rdx, [rsp+110h+var_E0]
0x18008090a  lea     rcx, [rbp+57h+var_A0]
0x18008090e  call    ??$MakeObjGuard@VCFixedBSTRArray@@P81@EAAXXZ@@YA?AV?$ObjScopeGuardImpl0@VCFixedBSTRArray@@P81@EAAXXZ@@AEAVCFixedBSTRArray@@P81@EAAXXZ@Z; MakeObjGuard<CFixedBSTRArray,void (CFixedBSTRArray::*)(void)>(CFixedBSTRArray &,void (CFixedBSTRArray::*)(void))
0x180080913  nop
0x180080914  lea     rdx, [rbp+57h+var_D0]
0x180080918  lea     rcx, [rbp+57h+var_B8]
0x18008091c  call    ??$MakeObjGuard@VCFixedBSTRArray@@P81@EAAXXZ@@YA?AV?$ObjScopeGuardImpl0@VCFixedBSTRArray@@P81@EAAXXZ@@AEAVCFixedBSTRArray@@P81@EAAXXZ@Z; MakeObjGuard<CFixedBSTRArray,void (CFixedBSTRArray::*)(void)>(CFixedBSTRArray &,void (CFixedBSTRArray::*)(void))
0x180080921  nop
0x180080922  lea     rax, [rbp+57h+var_D0]
0x180080926  mov     [rsp+110h+var_F0], rax; struct CFixedBSTRArray *
0x18008092b  lea     r9, [rsp+110h+var_E0]; struct CFixedBSTRArray *
0x180080930  xor     r8d, r8d; unsigned __int8
0x180080933  xor     edx, edx; unsigned __int8
0x180080935  mov     rcx, r15; this
0x180080938  call    ?EnumPrimaryQualifiers@CBasicQualifierSet@@QEAAJEEAEAVCFixedBSTRArray@@0@Z; CBasicQualifierSet::EnumPrimaryQualifiers(uchar,uchar,CFixedBSTRArray &,CFixedBSTRArray &)
0x18008093d  test    eax, eax
0x18008093f  jns     loc_1800809E8
0x180080945  cmp     eax, 80041006h
0x18008094a  jnz     short loc_1800809AC
0x18008094c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180080952  mov     edx, 0FFFFFFFEh
0x180080957  mov     rcx, rax
0x18008095a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180080960  lea     rax, WPP_GLOBAL_Control
0x180080967  mov     rcx, cs:WPP_GLOBAL_Control
0x18008096e  cmp     rcx, rax
0x180080971  jz      short loc_18008099B
0x180080973  test    byte ptr [rcx+1Ch], 1
0x180080977  jz      short loc_18008099B
0x180080979  cmp     byte ptr [rcx+19h], 2
0x18008097d  jb      short loc_18008099B
0x18008097f  mov     edx, 1Dh
0x180080984  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x18008098b  lea     r8, WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids
0x180080992  mov     rcx, [rcx+10h]
0x180080996  call    WPP_SF_s
0x18008099b  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800809a2  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800809a6  call    _CxxThrowException_0
0x1800809ac  lea     rcx, [rbp+57h+var_B8]
0x1800809b0  call    ??1?$ObjScopeGuardImpl0@VCFixedBSTRArray@@P81@EAAXXZ@@QEAA@XZ; ObjScopeGuardImpl0<CFixedBSTRArray,void (CFixedBSTRArray::*)(void)>::~ObjScopeGuardImpl0<CFixedBSTRArray,void (CFixedBSTRArray::*)(void)>(void)
0x1800809b5  nop
0x1800809b6  lea     rcx, [rbp+57h+var_A0]
0x1800809ba  call    ??1?$ObjScopeGuardImpl0@VCFixedBSTRArray@@P81@EAAXXZ@@QEAA@XZ; ObjScopeGuardImpl0<CFixedBSTRArray,void (CFixedBSTRArray::*)(void)>::~ObjScopeGuardImpl0<CFixedBSTRArray,void (CFixedBSTRArray::*)(void)>(void)
0x1800809bf  nop
0x1800809c0  mov     rcx, [rbp+57h+var_CC]
0x1800809c4  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800809ca  nop
0x1800809cb  mov     rcx, [rsp+110h+var_DC]
0x1800809d0  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800809d6  nop
0x1800809d7  lea     rcx, [rbp+57h+var_80]
0x1800809db  call    cs:__imp_??1CWStringArray@@QEAA@XZ; CWStringArray::~CWStringArray(void)
0x1800809e1  xor     eax, eax
0x1800809e3  jmp     loc_180080B9D
0x1800809e8  mov     ebx, 1
0x1800809ed  xor     edi, edi
0x1800809ef  test    ebx, ebx
0x1800809f1  jz      loc_180080B66
0x1800809f7  cmp     edi, [rsp+110h+var_E0]
0x1800809fb  jge     loc_180080B39
0x180080a01  movsxd  rsi, edi
0x180080a04  mov     [rbp+57h+pExceptionObject], 0
0x180080a0b  lea     r8, [rbp+57h+pExceptionObject]; int *
0x180080a0f  mov     rdx, [rsp+110h+var_DC]
0x180080a14  mov     rdx, [rdx+rsi*8]; unsigned __int16 *
0x180080a18  mov     rcx, r15; this
0x180080a1b  call    ?GetQualifierLocally@CBasicQualifierSet@@QEAAPEAUCQualifier@@PEBGAEAH@Z; CBasicQualifierSet::GetQualifierLocally(ushort const *,int &)
0x180080a20  mov     r14, rax
0x180080a23  test    rax, rax
0x180080a26  jz      loc_180080B30
0x180080a2c  lea     rdx, aAmendment; "amendment"
0x180080a33  mov     rcx, [rsp+110h+var_DC]
0x180080a38  mov     rcx, [rcx+rsi*8]; unsigned __int16 *
0x180080a3c  call    ?wbem_wcsicmp@@YAHPEBG0@Z; wbem_wcsicmp(ushort const *,ushort const *)
0x180080a41  test    eax, eax
0x180080a43  jz      short loc_180080A69
0x180080a45  lea     rdx, aLocale; "locale"
0x180080a4c  mov     rcx, [rsp+110h+var_DC]
0x180080a51  mov     rcx, [rcx+rsi*8]; unsigned __int16 *
0x180080a55  call    ?wbem_wcsicmp@@YAHPEBG0@Z; wbem_wcsicmp(ushort const *,ushort const *)
0x180080a5a  test    eax, eax
0x180080a5c  jz      short loc_180080A69
0x180080a5e  test    byte ptr [r14+4], 80h
0x180080a63  jz      loc_180080B32
0x180080a69  mov     [rbp+57h+pExceptionObject], 0
0x180080a70  lea     r8, [rbp+57h+pExceptionObject]; int *
0x180080a74  mov     rdx, [rsp+110h+var_DC]
0x180080a79  mov     rdx, [rdx+rsi*8]; unsigned __int16 *
0x180080a7d  mov     rcx, r12; this
0x180080a80  call    ?GetQualifierLocally@CBasicQualifierSet@@QEAAPEAUCQualifier@@PEBGAEAH@Z; CBasicQualifierSet::GetQualifierLocally(ushort const *,int &)
0x180080a85  test    rax, rax
0x180080a88  jz      short loc_180080AAC
0x180080a8a  mov     ecx, [rax+5]
0x180080a8d  cmp     [r14+5], ecx
0x180080a91  jnz     loc_180080B30
0x180080a97  mov     al, [rax+4]
0x180080a9a  xor     al, [r14+4]
0x180080a9e  test    al, 1Fh
0x180080aa0  mov     ebx, 0
0x180080aa5  setz    bl
0x180080aa8  mov     eax, ebx
0x180080aaa  jmp     short loc_180080AB1
0x180080aac  mov     eax, 1
0x180080ab1  test    eax, eax
0x180080ab3  jz      short loc_180080B32
0x180080ab5  test    ebx, ebx
0x180080ab7  jz      short loc_180080B32
0x180080ab9  mov     rdx, [rsp+110h+var_DC]
0x180080abe  mov     rdx, [rdx+rsi*8]
0x180080ac2  lea     rcx, [rbp+57h+var_80]
0x180080ac6  call    cs:__imp_?Add@CWStringArray@@QEAAHPEBG@Z; CWStringArray::Add(ushort const *)
0x180080acc  test    eax, eax
0x180080ace  jz      short loc_180080B32
0x180080ad0  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180080ad6  mov     edx, 0FFFFFFFEh
0x180080adb  mov     rcx, rax
0x180080ade  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180080ae4  lea     rax, WPP_GLOBAL_Control
0x180080aeb  mov     rcx, cs:WPP_GLOBAL_Control
0x180080af2  cmp     rcx, rax
0x180080af5  jz      short loc_180080B1F
0x180080af7  test    byte ptr [rcx+1Ch], 1
0x180080afb  jz      short loc_180080B1F
0x180080afd  cmp     byte ptr [rcx+19h], 2
0x180080b01  jb      short loc_180080B1F
0x180080b03  mov     edx, 1Eh
0x180080b08  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x180080b0f  lea     r8, WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids
0x180080b16  mov     rcx, [rcx+10h]
0x180080b1a  call    WPP_SF_s
0x180080b1f  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x180080b26  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180080b2a  call    _CxxThrowException_0
0x180080b30  xor     ebx, ebx
0x180080b32  inc     edi
0x180080b34  jmp     loc_1800809EF
0x180080b39  lea     rcx, [rbp+57h+var_80]
0x180080b3d  call    cs:__imp_?Size@CWStringArray@@QEBAHXZ; CWStringArray::Size(void)
0x180080b43  mov     ebx, eax
0x180080b45  lea     rcx, [rbp+57h+var_80]
0x180080b49  call    cs:__imp_?GetArrayPtr@CWStringArray@@QEAAPEAPEBGXZ; CWStringArray::GetArrayPtr(void)
0x180080b4f  mov     dword ptr [rsp+110h+var_F0], ebx; unsigned int
0x180080b53  mov     r9, rax; unsigned __int16 **
0x180080b56  xor     r8d, r8d; unsigned __int8
0x180080b59  mov     rdx, r12; struct CBasicQualifierSet *
0x180080b5c  mov     rcx, r15; this
0x180080b5f  call    ?Compare@CBasicQualifierSet@@QEAAHAEAV1@EPEAPEBGK@Z; CBasicQualifierSet::Compare(CBasicQualifierSet &,uchar,ushort const * *,ulong)
0x180080b64  mov     ebx, eax
0x180080b66  lea     rcx, [rbp+57h+var_B8]
0x180080b6a  call    ??1?$ObjScopeGuardImpl0@VCFixedBSTRArray@@P81@EAAXXZ@@QEAA@XZ; ObjScopeGuardImpl0<CFixedBSTRArray,void (CFixedBSTRArray::*)(void)>::~ObjScopeGuardImpl0<CFixedBSTRArray,void (CFixedBSTRArray::*)(void)>(void)
0x180080b6f  nop
0x180080b70  lea     rcx, [rbp+57h+var_A0]
0x180080b74  call    ??1?$ObjScopeGuardImpl0@VCFixedBSTRArray@@P81@EAAXXZ@@QEAA@XZ; ObjScopeGuardImpl0<CFixedBSTRArray,void (CFixedBSTRArray::*)(void)>::~ObjScopeGuardImpl0<CFixedBSTRArray,void (CFixedBSTRArray::*)(void)>(void)
0x180080b79  nop
0x180080b7a  mov     rcx, [rbp+57h+var_CC]
0x180080b7e  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180080b84  nop
0x180080b85  mov     rcx, [rsp+110h+var_DC]
0x180080b8a  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180080b90  nop
0x180080b91  lea     rcx, [rbp+57h+var_80]
0x180080b95  call    cs:__imp_??1CWStringArray@@QEAA@XZ; CWStringArray::~CWStringArray(void)
0x180080b9b  mov     eax, ebx
0x180080b9d  lea     r11, [rsp+110h+var_20]
0x180080ba5  mov     rbx, [r11+30h]
0x180080ba9  mov     rsi, [r11+38h]
0x180080bad  mov     rsp, r11
0x180080bb0  pop     r15
0x180080bb2  pop     r14
0x180080bb4  pop     r12
0x180080bb6  pop     rdi
0x180080bb7  pop     rbp
0x180080bb8  retn
```
