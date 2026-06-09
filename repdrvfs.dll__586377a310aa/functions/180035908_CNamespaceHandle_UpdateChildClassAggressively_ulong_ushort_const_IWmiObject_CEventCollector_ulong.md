# CNamespaceHandle::UpdateChildClassAggressively(ulong,ushort const *,_IWmiObject *,CEventCollector &,ulong)

- ea: `0x180035908`
- end: `0x180035f13`
- name: `?UpdateChildClassAggressively@CNamespaceHandle@@IEAAJKPEBGPEAU_IWmiObject@@AEAVCEventCollector@@K@Z`
- size: `1547`
- prototype: `__int64 __fastcall(CNamespaceHandle *__hidden this, unsigned int, const unsigned __int16 *, struct _IWmiObject *, struct CEventCollector *, unsigned int)`
- caller_count: `2`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180035908`
- `0x180035f1c`

## callees

- `0x1800012b8`
- `0x1800013a0`
- `0x18000a350`
- `0x18001dba8`
- `0x180027150`
- `0x180031c08`
- `0x1800332dc`
- `0x180035908`
- `0x180048010`

## import_xrefs

- `wbemcomn!??ACWStringArray@@QEBAPEAGH@Z` at `0x180035d5e`
- `wbemcomn!??ACWStringArray@@QEBAPEAGH@Z` at `0x180035d5e`
- `wbemcomn!?Size@CWStringArray@@QEBAHXZ` at `0x180035d43`
- `wbemcomn!?Size@CWStringArray@@QEBAHXZ` at `0x180035d43`
- `wbemcomn!??0CWStringArray@@QEAA@HH@Z` at `0x180035c97`
- `wbemcomn!??0CWStringArray@@QEAA@HH@Z` at `0x180035c97`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x180035d07`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x180035dde`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x180035e92`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x180035ecc`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x180035d07`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x180035dde`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x180035e92`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x180035ecc`
- `wbemcomn!GetMemLogObject` at `0x180035989`
- `wbemcomn!GetMemLogObject` at `0x1800359dc`
- `wbemcomn!GetMemLogObject` at `0x180035a50`
- `wbemcomn!GetMemLogObject` at `0x180035af3`
- `wbemcomn!GetMemLogObject` at `0x180035b7d`
- `wbemcomn!GetMemLogObject` at `0x180035c21`
- `wbemcomn!GetMemLogObject` at `0x180035cba`
- `wbemcomn!GetMemLogObject` at `0x180035d91`
- `wbemcomn!GetMemLogObject` at `0x180035e45`
- `wbemcomn!GetMemLogObject` at `0x180035989`
- `wbemcomn!GetMemLogObject` at `0x1800359dc`
- `wbemcomn!GetMemLogObject` at `0x180035a50`
- `wbemcomn!GetMemLogObject` at `0x180035af3`
- `wbemcomn!GetMemLogObject` at `0x180035b7d`
- `wbemcomn!GetMemLogObject` at `0x180035c21`
- `wbemcomn!GetMemLogObject` at `0x180035cba`
- `wbemcomn!GetMemLogObject` at `0x180035d91`
- `wbemcomn!GetMemLogObject` at `0x180035e45`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180035994`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800359ec`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180035a5b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180035afe`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180035b88`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180035c2c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180035cc5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180035d9c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180035e50`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180035994`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800359ec`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180035a5b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180035afe`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180035b88`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180035c2c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180035cc5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180035d9c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180035e50`
- `OLEAUT32!__imp_VariantInit` at `0x180035abd`
- `OLEAUT32!__imp_VariantInit` at `0x180035abd`
- `OLEAUT32!__imp_VariantClear` at `0x180035bcb`
- `OLEAUT32!__imp_VariantClear` at `0x180035bf1`
- `OLEAUT32!__imp_VariantClear` at `0x180035bcb`
- `OLEAUT32!__imp_VariantClear` at `0x180035bf1`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CNamespaceHandle::UpdateChildClassAggressively(
        const unsigned __int16 **this,
        char a2,
        unsigned __int16 *a3,
        struct _IWmiObject *a4,
        struct CEventCollector *a5)
{
  unsigned int v9; // r12d
  unsigned int v10; // r14d
  unsigned int HasInstancesFromClassHash; // ebx
  CMemoryLog *MemLogObject; // rax
  CVarObjHeap *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r9
  CMemoryLog *v17; // rax
  CMemoryLog *v18; // rax
  struct _IWmiObject *v19; // rdx
  struct _IWmiObject *v20; // rbx
  int v21; // edi
  CMemoryLog *v22; // rax
  CMemoryLog *v23; // rax
  CMemoryLog *v24; // rax
  struct _IWmiObject *v25; // rdi
  int ChildHashesByHash; // esi
  CMemoryLog *v27; // rax
  struct _IWmiObject *v28; // rsi
  const unsigned __int16 *v29; // rax
  CMemoryLog *v30; // rax
  CMemoryLog *v31; // rax
  struct _IWmiObject *v32; // [rsp+40h] [rbp-99h] BYREF
  struct _IWmiObject *v33; // [rsp+48h] [rbp-91h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-89h] BYREF
  void *p_pvarg; // [rsp+68h] [rbp-71h]
  struct _IWmiObject *v36; // [rsp+70h] [rbp-69h]
  _BYTE v37[160]; // [rsp+80h] [rbp-59h] BYREF

  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 271, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids);
  }
  v9 = a2 & 0x60;
  v10 = 0;
  if ( (v9 & 0x40) == 0 )
  {
    HasInstancesFromClassHash = CNamespaceHandle::ClassHasInstancesFromClassHash(this, a3);
    if ( (HasInstancesFromClassHash & 0x80000000) != 0 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, HasInstancesFromClassHash);
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return HasInstancesFromClassHash;
      }
      v14 = 272;
      goto LABEL_11;
    }
    if ( !HasInstancesFromClassHash )
    {
      v17 = GetMemLogObject();
      HasInstancesFromClassHash = -2147217370;
      CMemoryLog::Write(v17, -2147217370);
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return HasInstancesFromClassHash;
      }
      v14 = 273;
      v15 = 2147749926LL;
      goto LABEL_12;
    }
  }
  v32 = 0;
  HasInstancesFromClassHash = CNamespaceHandle::GetClassByHash(
                                (CNamespaceHandle *)this,
                                (char *)a3,
                                1,
                                &v32,
                                0,
                                0,
                                0,
                                0);
  if ( (HasInstancesFromClassHash & 0x80000000) != 0 )
  {
    v18 = GetMemLogObject();
    CMemoryLog::Write(v18, HasInstancesFromClassHash);
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return HasInstancesFromClassHash;
    }
    v14 = 274;
LABEL_11:
    v15 = HasInstancesFromClassHash;
LABEL_12:
    WPP_SF_d(*((_QWORD *)v13 + 2), v14, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, v15);
    return HasInstancesFromClassHash;
  }
  v19 = v32;
  v20 = v32;
  v36 = v32;
  if ( (v9 & 0x40) != 0 )
  {
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    v21 = (*(__int64 (__fastcall **)(struct _IWmiObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v32 + 32LL))(
            v32,
            L"__CLASS",
            0,
            &pvarg,
            0,
            0);
    if ( v21 < 0 )
    {
      v22 = GetMemLogObject();
      CMemoryLog::Write(v22, v21);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          275,
          WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
          (unsigned int)v21);
      }
      if ( v20 )
        (*(void (__fastcall **)(struct _IWmiObject *))(*(_QWORD *)v20 + 16LL))(v20);
      return (unsigned int)v21;
    }
    p_pvarg = &pvarg;
    v21 = CNamespaceHandle::DeleteClassInstances((CNamespaceHandle *)this, pvarg.bstrVal, v32, a5);
    if ( v21 < 0 )
    {
      v23 = GetMemLogObject();
      CMemoryLog::Write(v23, v21);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          276,
          WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
          (unsigned int)v21);
      }
      VariantClear(&pvarg);
      if ( v20 )
        (*(void (__fastcall **)(struct _IWmiObject *))(*(_QWORD *)v20 + 16LL))(v20);
      return (unsigned int)v21;
    }
    VariantClear(&pvarg);
    v19 = v32;
  }
  v33 = 0;
  v21 = (*(__int64 (__fastcall **)(struct _IWmiObject *, struct _IWmiObject *, _QWORD, struct _IWmiObject **))(*(_QWORD *)a4 + 712LL))(
          a4,
          v19,
          v9,
          &v33);
  if ( v21 < 0 )
  {
    v24 = GetMemLogObject();
    CMemoryLog::Write(v24, v21);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        277,
        WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
        (unsigned int)v21);
    }
    if ( v20 )
      (*(void (__fastcall **)(struct _IWmiObject *))(*(_QWORD *)v20 + 16LL))(v20);
    return (unsigned int)v21;
  }
  v25 = v33;
  p_pvarg = v33;
  CWStringArray::CWStringArray((CWStringArray *)v37, 0, 100);
  ChildHashesByHash = CNamespaceHandle::GetChildHashesByHash(
                        (CNamespaceHandle *)this,
                        a3,
                        (struct CWStringArray *)v37,
                        0);
  if ( ChildHashesByHash < 0 )
  {
    v27 = GetMemLogObject();
    CMemoryLog::Write(v27, ChildHashesByHash);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        278,
        WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
        (unsigned int)ChildHashesByHash);
    }
    CWStringArray::~CWStringArray((CWStringArray *)v37);
    if ( v25 )
      (*(void (__fastcall **)(struct _IWmiObject *))(*(_QWORD *)v25 + 16LL))(v25);
    if ( v20 )
      (*(void (__fastcall **)(struct _IWmiObject *))(*(_QWORD *)v20 + 16LL))(v20);
    return (unsigned int)ChildHashesByHash;
  }
  while ( v10 != CWStringArray::Size((CWStringArray *)v37) )
  {
    v28 = v33;
    v29 = (const unsigned __int16 *)CWStringArray::operator[](v37, v10);
    ChildHashesByHash = CNamespaceHandle::UpdateChildClassAggressively((CNamespaceHandle *)this, v9, v29, v28, a5, 0);
    if ( ChildHashesByHash < 0 )
    {
      v30 = GetMemLogObject();
      CMemoryLog::Write(v30, ChildHashesByHash);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          279,
          WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
          (unsigned int)ChildHashesByHash);
      }
      CWStringArray::~CWStringArray((CWStringArray *)v37);
      if ( v25 )
        (*(void (__fastcall **)(struct _IWmiObject *))(*(_QWORD *)v25 + 16LL))(v25);
      if ( v20 )
        (*(void (__fastcall **)(struct _IWmiObject *))(*(_QWORD *)v20 + 16LL))(v20);
      return (unsigned int)ChildHashesByHash;
    }
    ++v10;
  }
  ChildHashesByHash = CNamespaceHandle::UpdateClassCompatibleHash(this, a4, a3, v33, v32, 0);
  if ( ChildHashesByHash < 0 )
  {
    v31 = GetMemLogObject();
    CMemoryLog::Write(v31, ChildHashesByHash);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        280,
        WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
        (unsigned int)ChildHashesByHash);
    }
    CWStringArray::~CWStringArray((CWStringArray *)v37);
    if ( v25 )
      (*(void (__fastcall **)(struct _IWmiObject *))(*(_QWORD *)v25 + 16LL))(v25);
    if ( v20 )
      (*(void (__fastcall **)(struct _IWmiObject *))(*(_QWORD *)v20 + 16LL))(v20);
    return (unsigned int)ChildHashesByHash;
  }
  CWStringArray::~CWStringArray((CWStringArray *)v37);
  if ( v25 )
    (*(void (__fastcall **)(struct _IWmiObject *))(*(_QWORD *)v25 + 16LL))(v25);
  if ( v20 )
    (*(void (__fastcall **)(struct _IWmiObject *))(*(_QWORD *)v20 + 16LL))(v20);
  return 0;
}

```

## disassembly

```asm
0x180035908  mov     [rsp-8+arg_18], r9
0x18003590d  push    rbp
0x18003590e  push    rbx
0x18003590f  push    rsi
0x180035910  push    rdi
0x180035911  push    r12
0x180035913  push    r13
0x180035915  push    r14
0x180035917  push    r15
0x180035919  lea     rbp, [rsp-0Fh]
0x18003591e  sub     rsp, 0E8h
0x180035925  mov     rsi, r9
0x180035928  mov     r13, r8
0x18003592b  mov     r12d, edx
0x18003592e  mov     r15, rcx
0x180035931  lea     rax, WPP_GLOBAL_Control
0x180035938  mov     rcx, cs:WPP_GLOBAL_Control
0x18003593f  cmp     rcx, rax
0x180035942  jz      short loc_180035965
0x180035944  test    byte ptr [rcx+1Ch], 1
0x180035948  jz      short loc_180035965
0x18003594a  cmp     byte ptr [rcx+19h], 5
0x18003594e  jb      short loc_180035965
0x180035950  mov     edx, 10Fh
0x180035955  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x18003595c  mov     rcx, [rcx+10h]
0x180035960  call    WPP_SF_
0x180035965  and     r12d, 60h
0x180035969  mov     edi, r12d
0x18003596c  xor     r14d, r14d
0x18003596f  and     edi, 40h
0x180035972  jnz     loc_180035A1E
0x180035978  mov     rdx, r13; unsigned __int16 *
0x18003597b  mov     rcx, r15; this
0x18003597e  call    ?ClassHasInstancesFromClassHash@CNamespaceHandle@@IEAAJPEBG@Z; CNamespaceHandle::ClassHasInstancesFromClassHash(ushort const *)
0x180035983  mov     ebx, eax
0x180035985  test    eax, eax
0x180035987  jns     short loc_1800359D8
0x180035989  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003598f  mov     edx, ebx
0x180035991  mov     rcx, rax
0x180035994  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003599a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800359a1  lea     rax, WPP_GLOBAL_Control
0x1800359a8  cmp     rcx, rax
0x1800359ab  jz      short loc_1800359D1
0x1800359ad  test    byte ptr [rcx+1Ch], 1
0x1800359b1  jz      short loc_1800359D1
0x1800359b3  cmp     byte ptr [rcx+19h], 2
0x1800359b7  jb      short loc_1800359D1
0x1800359b9  mov     edx, 110h
0x1800359be  mov     r9d, ebx
0x1800359c1  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x1800359c8  mov     rcx, [rcx+10h]
0x1800359cc  call    WPP_SF_d
0x1800359d1  mov     eax, ebx
0x1800359d3  jmp     loc_180035EFF
0x1800359d8  test    ebx, ebx
0x1800359da  jnz     short loc_180035A1E
0x1800359dc  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800359e2  mov     ebx, 80041026h
0x1800359e7  mov     edx, ebx
0x1800359e9  mov     rcx, rax
0x1800359ec  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800359f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800359f9  lea     rax, WPP_GLOBAL_Control
0x180035a00  cmp     rcx, rax
0x180035a03  jz      short loc_1800359D1
0x180035a05  test    byte ptr [rcx+1Ch], 1
0x180035a09  jz      short loc_1800359D1
0x180035a0b  cmp     byte ptr [rcx+19h], 2
0x180035a0f  jb      short loc_1800359D1
0x180035a11  mov     edx, 111h
0x180035a16  mov     r9d, 80041026h
0x180035a1c  jmp     short loc_1800359C1
0x180035a1e  mov     [rsp+120h+var_E0], r14
0x180035a23  mov     [rsp+120h+var_E8], r14d; unsigned int
0x180035a28  mov     [rsp+120h+var_F0], r14; bool *
0x180035a2d  mov     [rsp+120h+var_F8], r14; bool *
0x180035a32  mov     [rsp+120h+var_100], r14; __int64 *
0x180035a37  lea     r9, [rsp+120h+var_E0]; struct _IWmiObject **
0x180035a3c  mov     r8b, 1; bool
0x180035a3f  mov     rdx, r13; unsigned __int16 *
0x180035a42  mov     rcx, r15; this
0x180035a45  call    ?GetClassByHash@CNamespaceHandle@@IEAAJPEBG_NPEAPEAU_IWmiObject@@PEA_JPEA_N4K@Z; CNamespaceHandle::GetClassByHash(ushort const *,bool,_IWmiObject * *,__int64 *,bool *,bool *,ulong)
0x180035a4a  mov     ebx, eax
0x180035a4c  test    eax, eax
0x180035a4e  jns     short loc_180035A96
0x180035a50  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180035a56  mov     edx, ebx
0x180035a58  mov     rcx, rax
0x180035a5b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180035a61  mov     rcx, cs:WPP_GLOBAL_Control
0x180035a68  lea     rax, WPP_GLOBAL_Control
0x180035a6f  cmp     rcx, rax
0x180035a72  jz      loc_1800359D1
0x180035a78  test    byte ptr [rcx+1Ch], 1
0x180035a7c  jz      loc_1800359D1
0x180035a82  cmp     byte ptr [rcx+19h], 2
0x180035a86  jb      loc_1800359D1
0x180035a8c  mov     edx, 112h
0x180035a91  jmp     loc_1800359BE
0x180035a96  mov     rdx, [rsp+120h+var_E0]
0x180035a9b  mov     rbx, rdx
0x180035a9e  mov     [rbp+47h+var_B0], rdx
0x180035aa2  test    edi, edi
0x180035aa4  jz      loc_180035BFC
0x180035aaa  xorps   xmm0, xmm0
0x180035aad  xor     eax, eax
0x180035aaf  movups  xmmword ptr [rsp+120h+pvarg], xmm0
0x180035ab4  mov     qword ptr [rbp+47h+pvarg+10h], rax
0x180035ab8  lea     rcx, [rsp+120h+pvarg]; pvarg
0x180035abd  call    cs:__imp_VariantInit
0x180035ac3  mov     rcx, [rsp+120h+var_E0]
0x180035ac8  mov     rax, [rcx]
0x180035acb  mov     [rsp+120h+var_F8], r14
0x180035ad0  mov     [rsp+120h+var_100], r14
0x180035ad5  lea     r9, [rsp+120h+pvarg]
0x180035ada  xor     r8d, r8d
0x180035add  lea     rdx, aClass; "__CLASS"
0x180035ae4  mov     rax, [rax+20h]
0x180035ae8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035aed  mov     edi, eax
0x180035aef  test    eax, eax
0x180035af1  jns     short loc_180035B58
0x180035af3  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180035af9  mov     edx, edi
0x180035afb  mov     rcx, rax
0x180035afe  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180035b04  mov     rcx, cs:WPP_GLOBAL_Control
0x180035b0b  lea     rax, WPP_GLOBAL_Control
0x180035b12  cmp     rcx, rax
0x180035b15  jz      short loc_180035B3C
0x180035b17  test    byte ptr [rcx+1Ch], 1
0x180035b1b  jz      short loc_180035B3C
0x180035b1d  cmp     byte ptr [rcx+19h], 2
0x180035b21  jb      short loc_180035B3C
0x180035b23  mov     edx, 113h
0x180035b28  mov     r9d, edi
0x180035b2b  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180035b32  mov     rcx, [rcx+10h]
0x180035b36  call    WPP_SF_d
0x180035b3b  nop
0x180035b3c  test    rbx, rbx
0x180035b3f  jz      short loc_180035B51
0x180035b41  mov     rax, [rbx]
0x180035b44  mov     rcx, rbx
0x180035b47  mov     rax, [rax+10h]
0x180035b4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035b50  nop
0x180035b51  mov     eax, edi
0x180035b53  jmp     loc_180035EFF
0x180035b58  lea     rax, [rsp+120h+pvarg]
0x180035b5d  mov     [rbp+47h+var_B8], rax
0x180035b61  mov     r9, [rbp+47h+arg_20]; struct CEventCollector *
0x180035b65  mov     r8, [rsp+120h+var_E0]; struct _IWmiObject *
0x180035b6a  mov     rdx, qword ptr [rsp+120h+pvarg+8]; unsigned __int16 *
0x180035b6f  mov     rcx, r15; this
0x180035b72  call    ?DeleteClassInstances@CNamespaceHandle@@IEAAJPEBGPEAU_IWmiObject@@AEAVCEventCollector@@@Z; CNamespaceHandle::DeleteClassInstances(ushort const *,_IWmiObject *,CEventCollector &)
0x180035b77  mov     edi, eax
0x180035b79  test    eax, eax
0x180035b7b  jns     short loc_180035BEC
0x180035b7d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180035b83  mov     edx, edi
0x180035b85  mov     rcx, rax
0x180035b88  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180035b8e  mov     rcx, cs:WPP_GLOBAL_Control
0x180035b95  lea     rax, WPP_GLOBAL_Control
0x180035b9c  cmp     rcx, rax
0x180035b9f  jz      short loc_180035BC6
0x180035ba1  test    byte ptr [rcx+1Ch], 1
0x180035ba5  jz      short loc_180035BC6
0x180035ba7  cmp     byte ptr [rcx+19h], 2
0x180035bab  jb      short loc_180035BC6
0x180035bad  mov     edx, 114h
0x180035bb2  mov     r9d, edi
0x180035bb5  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180035bbc  mov     rcx, [rcx+10h]
0x180035bc0  call    WPP_SF_d
0x180035bc5  nop
0x180035bc6  lea     rcx, [rsp+120h+pvarg]; pvarg
0x180035bcb  call    cs:__imp_VariantClear
0x180035bd1  nop
0x180035bd2  test    rbx, rbx
0x180035bd5  jz      short loc_180035BE7
0x180035bd7  mov     rax, [rbx]
0x180035bda  mov     rcx, rbx
0x180035bdd  mov     rax, [rax+10h]
0x180035be1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035be6  nop
0x180035be7  jmp     loc_180035B51
0x180035bec  lea     rcx, [rsp+120h+pvarg]; pvarg
0x180035bf1  call    cs:__imp_VariantClear
0x180035bf7  mov     rdx, [rsp+120h+var_E0]
0x180035bfc  mov     [rsp+120h+var_D8], r14
0x180035c01  mov     rax, [rsi]
0x180035c04  lea     r9, [rsp+120h+var_D8]
0x180035c09  mov     r8d, r12d
0x180035c0c  mov     rcx, rsi
0x180035c0f  mov     rax, [rax+2C8h]
0x180035c16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035c1b  mov     edi, eax
0x180035c1d  test    eax, eax
0x180035c1f  jns     short loc_180035C84
0x180035c21  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180035c27  mov     edx, edi
0x180035c29  mov     rcx, rax
0x180035c2c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180035c32  mov     rcx, cs:WPP_GLOBAL_Control
0x180035c39  lea     rax, WPP_GLOBAL_Control
0x180035c40  cmp     rcx, rax
0x180035c43  jz      short loc_180035C6A
0x180035c45  test    byte ptr [rcx+1Ch], 1
0x180035c49  jz      short loc_180035C6A
0x180035c4b  cmp     byte ptr [rcx+19h], 2
0x180035c4f  jb      short loc_180035C6A
0x180035c51  mov     edx, 115h
0x180035c56  mov     r9d, edi
0x180035c59  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180035c60  mov     rcx, [rcx+10h]
0x180035c64  call    WPP_SF_d
0x180035c69  nop
0x180035c6a  test    rbx, rbx
0x180035c6d  jz      short loc_180035C7F
0x180035c6f  mov     rax, [rbx]
0x180035c72  mov     rcx, rbx
0x180035c75  mov     rax, [rax+10h]
0x180035c79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035c7e  nop
0x180035c7f  jmp     loc_180035B51
0x180035c84  mov     rdi, [rsp+120h+var_D8]
0x180035c89  mov     [rbp+47h+var_B8], rdi
0x180035c8d  xor     edx, edx
0x180035c8f  lea     r8d, [rdx+64h]
0x180035c93  lea     rcx, [rbp+47h+var_A0]
0x180035c97  call    cs:__imp_??0CWStringArray@@QEAA@HH@Z; CWStringArray::CWStringArray(int,int)
0x180035c9d  nop
0x180035c9e  xor     r9d, r9d; unsigned int
0x180035ca1  lea     r8, [rbp+47h+var_A0]; struct CWStringArray *
0x180035ca5  mov     rdx, r13; unsigned __int16 *
0x180035ca8  mov     rcx, r15; this
0x180035cab  call    ?GetChildHashesByHash@CNamespaceHandle@@IEAAJPEBGAEAVCWStringArray@@K@Z; CNamespaceHandle::GetChildHashesByHash(ushort const *,CWStringArray &,ulong)
0x180035cb0  mov     esi, eax
0x180035cb2  test    eax, eax
0x180035cb4  jns     loc_180035D3F
0x180035cba  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180035cc0  mov     edx, esi
0x180035cc2  mov     rcx, rax
0x180035cc5  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180035ccb  mov     rcx, cs:WPP_GLOBAL_Control
0x180035cd2  lea     rax, WPP_GLOBAL_Control
0x180035cd9  cmp     rcx, rax
0x180035cdc  jz      short loc_180035D03
0x180035cde  test    byte ptr [rcx+1Ch], 1
0x180035ce2  jz      short loc_180035D03
0x180035ce4  cmp     byte ptr [rcx+19h], 2
0x180035ce8  jb      short loc_180035D03
0x180035cea  mov     edx, 116h
0x180035cef  mov     r9d, esi
0x180035cf2  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180035cf9  mov     rcx, [rcx+10h]
0x180035cfd  call    WPP_SF_d
0x180035d02  nop
0x180035d03  lea     rcx, [rbp+47h+var_A0]
0x180035d07  call    cs:__imp_??1CWStringArray@@QEAA@XZ; CWStringArray::~CWStringArray(void)
0x180035d0d  nop
0x180035d0e  test    rdi, rdi
0x180035d11  jz      short loc_180035D23
0x180035d13  mov     rax, [rdi]
0x180035d16  mov     rcx, rdi
0x180035d19  mov     rax, [rax+10h]
0x180035d1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035d22  nop
0x180035d23  test    rbx, rbx
0x180035d26  jz      short loc_180035D38
0x180035d28  mov     rax, [rbx]
0x180035d2b  mov     rcx, rbx
0x180035d2e  mov     rax, [rax+10h]
0x180035d32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035d37  nop
0x180035d38  mov     eax, esi
0x180035d3a  jmp     loc_180035EFF
0x180035d3f  lea     rcx, [rbp+47h+var_A0]
0x180035d43  call    cs:__imp_?Size@CWStringArray@@QEBAHXZ; CWStringArray::Size(void)
0x180035d49  cmp     r14d, eax
0x180035d4c  jz      loc_180035E14
0x180035d52  mov     rsi, [rsp+120h+var_D8]
0x180035d57  mov     edx, r14d
0x180035d5a  lea     rcx, [rbp+47h+var_A0]
0x180035d5e  call    cs:__imp_??ACWStringArray@@QEBAPEAGH@Z; CWStringArray::operator[](int)
0x180035d64  mov     dword ptr [rsp+120h+var_F8], 0; unsigned int
0x180035d6c  mov     rcx, [rbp+47h+arg_20]
0x180035d70  mov     [rsp+120h+var_100], rcx; struct CEventCollector *
0x180035d75  mov     r9, rsi; struct _IWmiObject *
0x180035d78  mov     r8, rax; unsigned __int16 *
0x180035d7b  mov     edx, r12d; unsigned int
0x180035d7e  mov     rcx, r15; this
0x180035d81  call    ?UpdateChildClassAggressively@CNamespaceHandle@@IEAAJKPEBGPEAU_IWmiObject@@AEAVCEventCollector@@K@Z; CNamespaceHandle::UpdateChildClassAggressively(ulong,ushort const *,_IWmiObject *,CEventCollector &,ulong)
0x180035d86  mov     esi, eax
0x180035d88  test    eax, eax
  ... truncated ...
```
