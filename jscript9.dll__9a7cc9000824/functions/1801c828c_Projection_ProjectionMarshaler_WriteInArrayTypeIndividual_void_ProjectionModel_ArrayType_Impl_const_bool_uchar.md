# Projection::ProjectionMarshaler::WriteInArrayTypeIndividual(void *,ProjectionModel::ArrayType::Impl const *,bool,uchar *,uchar *,bool,bool,uint)

- ea: `0x1801c828c`
- end: `0x1801c8908`
- name: `?WriteInArrayTypeIndividual@ProjectionMarshaler@Projection@@QEAAXPEAXPEBUImpl@ArrayType@ProjectionModel@@_NPEAE322I@Z`
- size: `1660`
- prototype: `void __fastcall(Projection::ProjectionMarshaler *this, unsigned int *, const struct ProjectionModel::Type **, char, unsigned __int8 *, unsigned __int8 *, bool, bool, unsigned int)`
- caller_count: `4`
- callee_count: `25`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180229574`
- `0x180246a00`
- `0x18024b710`
- `0x18024b91c`

## callees

- `0x180037618`
- `0x180053c00`
- `0x180053ca0`
- `0x1800d5580`
- `0x18012dca4`
- `0x1801312b0`
- `0x180150f70`
- `0x180175764`
- `0x1801ab38c`
- `0x1801c0704`
- `0x1801c1f78`
- `0x1801c828c`
- `0x1801cab18`
- `0x1801cc26b`
- `0x18022a144`
- `0x180230858`
- `0x180231364`
- `0x180231590`
- `0x180232808`
- `0x180245788`
- `0x18024a820`
- `0x18024a918`
- `0x18024b710`
- `0x180336cf8`
- `0x180364010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x1801c863a`
- `KERNEL32!LoadLibraryExW` at `0x1801c8774`
- `KERNEL32!LoadLibraryExW` at `0x1801c863a`
- `KERNEL32!LoadLibraryExW` at `0x1801c8774`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x1801c87df`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x1801c87df`

## pseudocode

```c
void __fastcall Projection::ProjectionMarshaler::WriteInArrayTypeIndividual(
        Projection::ProjectionMarshaler *this,
        unsigned int *a2,
        const struct ProjectionModel::Type **a3,
        char a4,
        unsigned __int8 *a5,
        unsigned __int8 *a6,
        bool a7,
        bool a8,
        unsigned int a9)
{
  bool IsArrayInstance; // di
  int TypeId; // eax
  int v13; // edx
  int v14; // r8d
  struct Js::ScriptContext *v15; // r15
  unsigned int v16; // edi
  unsigned int v17; // r14d
  const struct ProjectionModel::ConcreteType *v18; // rax
  const struct ProjectionModel::ConcreteType *v19; // rsi
  size_t v20; // r14
  double v21; // xmm0_8
  bool v22; // r12
  void **v23; // r15
  __int64 v24; // rdx
  __int64 v25; // rax
  __int64 v26; // rbx
  unsigned int v27; // r12d
  __int64 v28; // r15
  unsigned int v29; // r14d
  _QWORD *v30; // rbx
  __int64 v31; // rax
  __int64 v32; // r12
  const WCHAR *v33; // rax
  void *v34; // rax
  __int64 v35; // rdi
  _QWORD *v36; // rbx
  _BYTE *v37; // rdx
  const WCHAR *v38; // rax
  HMODULE Library; // rax
  LPVOID v40; // rax
  __int64 v41; // r14
  _QWORD *v42; // rax
  unsigned int *v43; // rbx
  struct Js::ScriptContext *v44; // rdx
  unsigned __int8 *v45; // rdi
  unsigned int v46; // r14d
  __int64 v47; // r12
  void *v48; // rax
  void *ElementI; // rax
  unsigned int v50; // [rsp+38h] [rbp-C1h]
  __int64 v51; // [rsp+48h] [rbp-B1h] BYREF
  int v52; // [rsp+50h] [rbp-A9h]
  int v53; // [rsp+54h] [rbp-A5h]
  struct Js::ScriptContext *v54; // [rsp+58h] [rbp-A1h]
  int v55; // [rsp+60h] [rbp-99h]
  BOOL v56; // [rsp+64h] [rbp-95h]
  __int64 v57; // [rsp+68h] [rbp-91h]
  __int64 v58; // [rsp+70h] [rbp-89h]
  int v59; // [rsp+7Ch] [rbp-7Dh]
  __int64 v60; // [rsp+80h] [rbp-79h]
  _BYTE v61[176]; // [rsp+88h] [rbp-71h] BYREF

  v60 = -2;
  Projection::ProjectionMarshaler::RecordRecyclerVar(this, a2, 0);
  LODWORD(v51) = (unsigned int)Js::JavascriptOperators::GetTypeId(a2) <= 1;
  IsArrayInstance = Projection::ArrayAsCollection::IsArrayInstance(a2);
  v55 = Projection::ArrayProjection::Is(a2);
  v56 = (unsigned int)Js::JavascriptOperators::GetTypeId(a2) - 33 <= 0xC;
  TypeId = Js::JavascriptOperators::GetTypeId(a2);
  LODWORD(v57) = TypeId;
  v15 = *(struct Js::ScriptContext **)(*((_QWORD *)this + 2) + 112LL);
  v54 = v15;
  if ( (_DWORD)v51 )
  {
    if ( !IsArrayInstance )
      goto LABEL_9;
LABEL_8:
    v16 = a2[8];
    goto LABEL_15;
  }
  if ( IsArrayInstance )
    goto LABEL_8;
  if ( !v14 )
  {
    if ( !v13 )
    {
      if ( TypeId != 31 )
        Js::JavascriptError::ThrowTypeError(v15, -2146823257, 0);
      goto LABEL_12;
    }
LABEL_10:
    v16 = a2[12];
    goto LABEL_15;
  }
LABEL_9:
  if ( v13 )
    goto LABEL_10;
  if ( TypeId == 31 )
  {
LABEL_12:
    v16 = a2[10];
    goto LABEL_15;
  }
  v16 = 0;
  if ( v14 )
    v16 = *(_DWORD *)(*((_QWORD *)a2 + 6) + 16LL);
LABEL_15:
  v17 = v16;
  if ( a8 )
    v17 = a9;
  v50 = v17;
  v18 = ProjectionModel::ConcreteType::From(a3[5]);
  v19 = v18;
  if ( a8 && v17 > v16 )
    Js::JavascriptError::ThrowTypeError(v15, -2146823177, 0);
  v58 = *((_QWORD *)v18 + 3);
  v20 = v58 * v16;
  if ( v20 < v16
    || ((v20 & 0x8000000000000000uLL) != 0LL
      ? (v21 = (double)(int)(v20 & 1 | (v20 >> 1)) + (double)(int)(v20 & 1 | (v20 >> 1)))
      : (v21 = (double)(int)v20),
        (unsigned int)Js::JavascriptMath::ToInt32Core(v21, v15) < v16) )
  {
LABEL_79:
    Js::JavascriptError::MapAndThrowError(v15, -2147024882);
  }
  *(_DWORD *)a5 = v16;
  v22 = 1;
  v23 = (void **)a6;
  if ( !*((_DWORD *)this + 24) )
  {
    if ( v55 )
    {
      v24 = *((_QWORD *)a2 + 6);
      if ( *(_DWORD *)(*(_QWORD *)(v24 + 8) + 4LL) == *((_DWORD *)v19 + 1) )
      {
        v25 = *(_QWORD *)(v24 + 24);
        v22 = 0;
LABEL_38:
        *(_QWORD *)a6 = v25;
        if ( a7 )
        {
          v26 = v25;
          v27 = 0;
          if ( v16 )
          {
            do
            {
              Projection::ProjectionMarshaler::RecordTypeToUndo(
                (_DWORD)this,
                (unsigned int)Projection::ProjectionMarshaler::ClearString,
                (unsigned int)Projection::ProjectionMarshaler::ClearUnknown,
                (_DWORD)v19,
                v26,
                v58);
              v26 += v58;
              ++v27;
            }
            while ( v27 < v16 );
            v23 = (void **)a6;
          }
          memset_0(*v23, 0, v20);
          return;
        }
        if ( v50 >= v16 )
          return;
        v51 = v58 * v50;
        v28 = v51 + *(_QWORD *)a6;
        v29 = v50;
        do
        {
          Projection::ProjectionMarshaler::RecordTypeToUndo(
            (_DWORD)this,
            (unsigned int)Projection::ProjectionMarshaler::ClearString,
            (unsigned int)Projection::ProjectionMarshaler::ClearUnknown,
            (_DWORD)v19,
            v28,
            v58);
          v28 += v58;
          ++v29;
        }
        while ( v29 < v16 );
        v23 = (void **)a6;
        memset_0((void *)(*(_QWORD *)a6 + v51), 0, v58 * (v16 - v50));
        goto LABEL_71;
      }
      goto LABEL_48;
    }
    v22 = 0;
    if ( v56 )
    {
      if ( *(_DWORD *)v19 == 15
        && *((int *)ProjectionModel::BasicType::From(v19) + 10) <= 13
        && !(unsigned int)Projection::ArrayProjection::NeedConversion(v19, a2) )
      {
        v25 = *((_QWORD *)a2 + 7);
        goto LABEL_38;
      }
LABEL_48:
      Js::JavascriptError::ThrowTypeError(v54, -2146828275, 0);
    }
    if ( (_DWORD)v57 == 31 )
    {
      if ( *(_DWORD *)v19 == 15 && *((_DWORD *)ProjectionModel::BasicType::From(v19) + 10) == 5 )
      {
        v25 = *((_QWORD *)a2 + 4);
        goto LABEL_38;
      }
      goto LABEL_48;
    }
    if ( (_DWORD)v51 || ProjectionModel::ConcreteType::IsBlittable(v19) )
    {
      v51 = (__int64)ArenaAllocator::AllocZero;
      v52 = 0;
      v53 = v59;
      v35 = AllocateArray<ArenaAllocator,unsigned char,0>(*((_QWORD *)this + 1), &v51, v20);
      goto LABEL_59;
    }
    v51 = *((_QWORD *)v54 + 285);
    v30 = (_QWORD *)operator new<HeapAllocator>(72, v51, Recycler::AllocFinalized);
    if ( v30 )
    {
      v31 = *((_QWORD *)this + 2);
      v32 = *(_QWORD *)(v31 + 96) + 8408LL;
      if ( !*(_BYTE *)(*(_QWORD *)(v31 + 96) + 8424LL) )
      {
        v33 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v32 + 8LL))(*(_QWORD *)(v31 + 96) + 8408LL);
        *(_QWORD *)(v32 + 8) = LoadLibraryExW(v33, 0, 0x800u);
        *(_BYTE *)(v32 + 16) = 1;
      }
      *v30 = &Projection::FinalizableTypedArrayContents::`vftable';
      v30[1] = v19;
      *((_DWORD *)v30 + 4) = v16;
      v30[3] = 0;
      v30[4] = v51;
      v30[5] = v32;
      v30[6] = *((_QWORD *)v19 + 3);
      v30[7] = 0;
      *((_DWORD *)v30 + 16) = 0;
    }
    else
    {
      v30 = 0;
    }
    Projection::ProjectionMarshaler::RecordRecyclerVar(this, v30, 1);
    v34 = operator new[](v20);
    v35 = (__int64)v34;
    if ( v34 )
    {
      memset_0(v34, 0, v20);
      v30[3] = v35;
      Projection::FinalizableTypedArrayContents::Initialize((Projection::FinalizableTypedArrayContents *)v30);
LABEL_59:
      v22 = !a7;
LABEL_70:
      *(_QWORD *)a6 = v35;
LABEL_71:
      v43 = a2;
      if ( !v22 )
        return;
      goto LABEL_74;
    }
    goto LABEL_78;
  }
  if ( a4 )
  {
    v57 = *((_QWORD *)v54 + 285);
    v36 = (_QWORD *)operator new<HeapAllocator>(72, v57, Recycler::AllocFinalized);
    if ( v36 )
    {
      v37 = (_BYTE *)(*(_QWORD *)(*((_QWORD *)this + 2) + 96LL) + 8408LL);
      v51 = (__int64)v37;
      if ( !v37[16] )
      {
        v38 = (const WCHAR *)(*(__int64 (__fastcall **)(_BYTE *))(*(_QWORD *)v37 + 8LL))(v37);
        Library = LoadLibraryExW(v38, 0, 0x800u);
        v37 = (_BYTE *)v51;
        *(_QWORD *)(v51 + 8) = Library;
        v37[16] = 1;
      }
      *v36 = &Projection::FinalizableTypedArrayContents::`vftable';
      v36[1] = v19;
      *((_DWORD *)v36 + 4) = v16;
      v36[3] = 0;
      v36[4] = v57;
      v36[5] = v37;
      v36[6] = *((_QWORD *)v19 + 3);
      v36[7] = 0;
      *((_DWORD *)v36 + 16) = 1;
    }
    else
    {
      v36 = 0;
    }
    Projection::ProjectionMarshaler::RecordRecyclerVar(this, v36, 1);
    v40 = CoTaskMemAlloc(v20);
    v35 = (__int64)v40;
    if ( v40 )
    {
      v36[3] = v40;
      Projection::FinalizableTypedArrayContents::Initialize((Projection::FinalizableTypedArrayContents *)v36);
      v41 = *((_QWORD *)this + 11);
      v51 = (__int64)ArenaAllocator::Alloc;
      v52 = 0;
      v53 = v59;
      v42 = (_QWORD *)operator new<ArenaAllocator>(16, *((_QWORD *)this + 1), &v51);
      if ( v42 )
      {
        *v42 = v36;
        v42[1] = v41;
      }
      *((_QWORD *)this + 11) = v42;
      goto LABEL_70;
    }
LABEL_78:
    v15 = v54;
    goto LABEL_79;
  }
  v43 = a2;
LABEL_74:
  Projection::ProjectionMarshaler::ProjectionMarshaler(v61, 1, *((_QWORD *)this + 2));
  v45 = (unsigned __int8 *)*v23;
  v46 = 0;
  if ( v50 )
  {
    v47 = v58;
    do
    {
      v48 = Js::JavascriptNumber::ToVar(v46, v44);
      ElementI = Js::JavascriptOperators::OP_GetElementI(v43, (unsigned __int64)v48, v54);
      Projection::ProjectionMarshaler::WriteInType((Projection::ProjectionMarshaler *)v61, ElementI, v19, v45, v47, 1);
      Projection::ProjectionMarshaler::RecordTypeToUndo(
        (_DWORD)this,
        (unsigned int)Projection::ProjectionMarshaler::RecordDelegateOutString,
        (unsigned int)Projection::ProjectionMarshaler::RecordDelegateOutUnknown,
        (_DWORD)v19,
        (__int64)v45,
        v47);
      v45 += v47;
      ++v46;
    }
    while ( v46 < v50 );
  }
  Projection::ProjectionMarshaler::~ProjectionMarshaler((Projection::ProjectionMarshaler *)v61);
}

```

## disassembly

```asm
0x1801c828c  mov     rax, rsp
0x1801c828f  mov     [rax+20h], r9b
0x1801c8293  mov     [rax+18h], r8
0x1801c8297  mov     [rax+10h], rdx
0x1801c829b  mov     [rax+8], rcx
0x1801c829f  push    rbp
0x1801c82a0  push    rbx
0x1801c82a1  push    rsi
0x1801c82a2  push    rdi
0x1801c82a3  push    r12
0x1801c82a5  push    r13
0x1801c82a7  push    r14
0x1801c82a9  push    r15
0x1801c82ab  lea     rbp, [rax-47h]
0x1801c82af  sub     rsp, 0F8h
0x1801c82b6  mov     [rbp+3Fh+var_B8], 0FFFFFFFFFFFFFFFEh
0x1801c82be  xor     r8d, r8d; bool
0x1801c82c1  mov     rbx, [rbp+3Fh+arg_8]
0x1801c82c5  mov     rdx, rbx; void *
0x1801c82c8  mov     r13, [rbp+3Fh+arg_0]
0x1801c82cc  mov     rcx, r13; this
0x1801c82cf  call    ?RecordRecyclerVar@ProjectionMarshaler@Projection@@AEAAXPEAX_N@Z; Projection::ProjectionMarshaler::RecordRecyclerVar(void *,bool)
0x1801c82d4  mov     rcx, rbx
0x1801c82d7  call    ?GetTypeId@JavascriptOperators@Js@@SA?AW4TypeId@2@PEAX@Z; Js::JavascriptOperators::GetTypeId(void *)
0x1801c82dc  xor     esi, esi
0x1801c82de  cmp     eax, 1
0x1801c82e1  setbe   sil
0x1801c82e5  mov     [rsp+130h+var_F0], esi
0x1801c82e9  mov     rcx, rbx; void *
0x1801c82ec  call    ?IsArrayInstance@ArrayAsCollection@Projection@@SA_NPEAX@Z; Projection::ArrayAsCollection::IsArrayInstance(void *)
0x1801c82f1  mov     dil, al
0x1801c82f4  mov     rcx, rbx; void *
0x1801c82f7  call    ?Is@ArrayProjection@Projection@@SAHPEAX@Z; Projection::ArrayProjection::Is(void *)
0x1801c82fc  mov     r8d, eax
0x1801c82ff  mov     dword ptr [rsp+130h+var_D8], eax
0x1801c8303  mov     rcx, rbx
0x1801c8306  call    ?GetTypeId@JavascriptOperators@Js@@SA?AW4TypeId@2@PEAX@Z; Js::JavascriptOperators::GetTypeId(void *)
0x1801c830b  add     eax, 0FFFFFFDFh
0x1801c830e  xor     edx, edx
0x1801c8310  cmp     eax, 0Ch
0x1801c8313  setbe   dl
0x1801c8316  mov     dword ptr [rsp+130h+var_D8+4], edx
0x1801c831a  mov     rcx, rbx
0x1801c831d  call    ?GetTypeId@JavascriptOperators@Js@@SA?AW4TypeId@2@PEAX@Z; Js::JavascriptOperators::GetTypeId(void *)
0x1801c8322  mov     dword ptr [rsp+130h+var_D0], eax
0x1801c8326  mov     rcx, [r13+10h]
0x1801c832a  mov     r15, [rcx+70h]
0x1801c832e  mov     [rsp+130h+var_E0], r15
0x1801c8333  test    esi, esi
0x1801c8335  jnz     short loc_1801C835B
0x1801c8337  test    dil, dil
0x1801c833a  jnz     short loc_1801C8360
0x1801c833c  test    r8d, r8d
0x1801c833f  jnz     short loc_1801C8365
0x1801c8341  test    edx, edx
0x1801c8343  jnz     short loc_1801C8369
0x1801c8345  cmp     eax, 1Fh
0x1801c8348  jz      short loc_1801C8373
0x1801c834a  xor     r8d, r8d; unsigned __int16 *
0x1801c834d  mov     edx, 800A13A7h; int
0x1801c8352  mov     rcx, r15; struct Js::ScriptContext *
0x1801c8355  call    ?ThrowTypeError@JavascriptError@Js@@SAXPEAVScriptContext@2@JPEBG@Z; Js::JavascriptError::ThrowTypeError(Js::ScriptContext *,long,ushort const *)
0x1801c835b  test    dil, dil
0x1801c835e  jz      short loc_1801C8365
0x1801c8360  mov     edi, [rbx+20h]
0x1801c8363  jmp     short loc_1801C8386
0x1801c8365  test    edx, edx
0x1801c8367  jz      short loc_1801C836E
0x1801c8369  mov     edi, [rbx+30h]
0x1801c836c  jmp     short loc_1801C8386
0x1801c836e  cmp     eax, 1Fh
0x1801c8371  jnz     short loc_1801C8378
0x1801c8373  mov     edi, [rbx+28h]
0x1801c8376  jmp     short loc_1801C8386
0x1801c8378  xor     edi, edi
0x1801c837a  test    r8d, r8d
0x1801c837d  jz      short loc_1801C8386
0x1801c837f  mov     rax, [rbx+30h]
0x1801c8383  mov     edi, [rax+10h]
0x1801c8386  mov     r14d, edi
0x1801c8389  mov     bl, [rbp+3Fh+arg_38]
0x1801c838f  test    bl, bl
0x1801c8391  cmovnz  r14d, [rbp+3Fh+arg_40]
0x1801c8399  mov     [rsp+30h], r14d
0x1801c839e  mov     rcx, [rbp+3Fh+arg_10]
0x1801c83a2  mov     rcx, [rcx+28h]; struct ProjectionModel::Type *
0x1801c83a6  call    ?From@ConcreteType@ProjectionModel@@SAPEBU12@PEBUType@2@@Z; ProjectionModel::ConcreteType::From(ProjectionModel::Type const *)
0x1801c83ab  mov     rsi, rax
0x1801c83ae  test    bl, bl
0x1801c83b0  jz      short loc_1801C83C8
0x1801c83b2  cmp     r14d, edi
0x1801c83b5  jbe     short loc_1801C83C8
0x1801c83b7  xor     r8d, r8d; unsigned __int16 *
0x1801c83ba  mov     edx, 800A13F7h; int
0x1801c83bf  mov     rcx, r15; struct Js::ScriptContext *
0x1801c83c2  call    ?ThrowTypeError@JavascriptError@Js@@SAXPEAVScriptContext@2@JPEBG@Z; Js::JavascriptError::ThrowTypeError(Js::ScriptContext *,long,ushort const *)
0x1801c83c8  mov     rcx, [rax+18h]
0x1801c83cc  mov     [rsp+130h+var_C8], rcx
0x1801c83d1  mov     eax, edi
0x1801c83d3  mov     r14d, edi
0x1801c83d6  imul    r14, rcx
0x1801c83da  cmp     r14, rax
0x1801c83dd  jb      loc_1801C88FA
0x1801c83e3  xorps   xmm0, xmm0
0x1801c83e6  test    r14, r14
0x1801c83e9  js      short loc_1801C83F2
0x1801c83eb  cvtsi2sd xmm0, r14
0x1801c83f0  jmp     short loc_1801C840A
0x1801c83f2  mov     rcx, r14
0x1801c83f5  shr     rcx, 1
0x1801c83f8  mov     rax, r14
0x1801c83fb  and     eax, 1
0x1801c83fe  or      rcx, rax
0x1801c8401  cvtsi2sd xmm0, rcx
0x1801c8406  addsd   xmm0, xmm0; double
0x1801c840a  mov     rdx, r15; struct Js::ScriptContext *
0x1801c840d  call    ?ToInt32Core@JavascriptMath@Js@@SAHNPEAVScriptContext@2@@Z; Js::JavascriptMath::ToInt32Core(double,Js::ScriptContext *)
0x1801c8412  cmp     eax, edi
0x1801c8414  jb      loc_1801C88FA
0x1801c841a  mov     rax, [rbp+3Fh+arg_20]
0x1801c841e  mov     [rax], edi
0x1801c8420  mov     r12b, 1
0x1801c8423  mov     r15, [rbp+3Fh+arg_28]
0x1801c8427  cmp     dword ptr [r13+60h], 0
0x1801c842c  jnz     loc_1801C8705
0x1801c8432  cmp     dword ptr [rsp+130h+var_D8], 0
0x1801c8437  jz      short loc_1801C845A
0x1801c8439  mov     rbx, [rbp+3Fh+arg_8]
0x1801c843d  mov     rdx, [rbx+30h]
0x1801c8441  mov     rcx, [rdx+8]
0x1801c8445  mov     eax, [rsi+4]
0x1801c8448  cmp     [rcx+4], eax
0x1801c844b  jnz     loc_1801C85A9
0x1801c8451  mov     rax, [rdx+18h]
0x1801c8455  xor     r12b, r12b
0x1801c8458  jmp     short loc_1801C84CA
0x1801c845a  xor     r12d, r12d
0x1801c845d  cmp     dword ptr [rsp+130h+var_D8+4], r12d
0x1801c8462  jz      short loc_1801C849C
0x1801c8464  cmp     dword ptr [rsi], 0Fh
0x1801c8467  jnz     loc_1801C85A9
0x1801c846d  mov     rcx, rsi; struct ProjectionModel::Type *
0x1801c8470  call    ?From@BasicType@ProjectionModel@@SAPEBUImpl@12@PEBUType@2@@Z; ProjectionModel::BasicType::From(ProjectionModel::Type const *)
0x1801c8475  cmp     dword ptr [rax+28h], 0Dh
0x1801c8479  jg      loc_1801C85A9
0x1801c847f  mov     rbx, [rbp+3Fh+arg_8]
0x1801c8483  mov     rdx, rbx; void *
0x1801c8486  mov     rcx, rsi; struct ProjectionModel::ConcreteType *
0x1801c8489  call    ?NeedConversion@ArrayProjection@Projection@@SAHPEBUConcreteType@ProjectionModel@@PEAX@Z; Projection::ArrayProjection::NeedConversion(ProjectionModel::ConcreteType const *,void *)
0x1801c848e  test    eax, eax
0x1801c8490  jnz     loc_1801C85A9
0x1801c8496  mov     rax, [rbx+38h]
0x1801c849a  jmp     short loc_1801C84CA
0x1801c849c  cmp     dword ptr [rsp+130h+var_D0], 1Fh
0x1801c84a1  jnz     loc_1801C85BC
0x1801c84a7  cmp     dword ptr [rsi], 0Fh
0x1801c84aa  jnz     loc_1801C85A9
0x1801c84b0  mov     rcx, rsi; struct ProjectionModel::Type *
0x1801c84b3  call    ?From@BasicType@ProjectionModel@@SAPEBUImpl@12@PEBUType@2@@Z; ProjectionModel::BasicType::From(ProjectionModel::Type const *)
0x1801c84b8  cmp     dword ptr [rax+28h], 5
0x1801c84bc  jnz     loc_1801C85A9
0x1801c84c2  mov     rbx, [rbp+3Fh+arg_8]
0x1801c84c6  mov     rax, [rbx+20h]
0x1801c84ca  mov     [r15], rax
0x1801c84cd  cmp     [rbp+3Fh+arg_30], 0
0x1801c84d1  jz      short loc_1801C8536
0x1801c84d3  mov     rbx, rax
0x1801c84d6  xor     r12d, r12d
0x1801c84d9  test    edi, edi
0x1801c84db  jz      short loc_1801C8514
0x1801c84dd  mov     r15, [rsp+130h+var_C8]
0x1801c84e2  mov     qword ptr [rsp+130h+var_108], r15
0x1801c84e7  mov     [rsp+130h+var_110], rbx
0x1801c84ec  mov     r9, rsi
0x1801c84ef  lea     r8, ?ClearUnknown@ProjectionMarshaler@Projection@@AEAAXPEAPEAUIUnknown@@@Z; Projection::ProjectionMarshaler::ClearUnknown(IUnknown * *)
0x1801c84f6  lea     rdx, ?ClearString@ProjectionMarshaler@Projection@@AEAAXPEAPEAUHSTRING__@@@Z; Projection::ProjectionMarshaler::ClearString(HSTRING__ * *)
0x1801c84fd  mov     rcx, r13
0x1801c8500  call    ?RecordTypeToUndo@ProjectionMarshaler@Projection@@AEAAXP812@EAAXPEAPEAUHSTRING__@@@ZP812@EAAXPEAPEAUIUnknown@@@ZPEBUConcreteType@ProjectionModel@@PEAE_K@Z; Projection::ProjectionMarshaler::RecordTypeToUndo(void (Projection::ProjectionMarshaler::*)(HSTRING__ * *),void (Projection::ProjectionMarshaler::*)(IUnknown * *),ProjectionModel::ConcreteType const *,uchar *,unsigned __int64)
0x1801c8505  add     rbx, r15
0x1801c8508  inc     r12d
0x1801c850b  cmp     r12d, edi
0x1801c850e  jb      short loc_1801C84E2
0x1801c8510  mov     r15, [rbp+3Fh+arg_28]
0x1801c8514  mov     r8, r14; Size
0x1801c8517  xor     edx, edx; Val
0x1801c8519  mov     rcx, [r15]; void *
0x1801c851c  call    memset_0
0x1801c8521  add     rsp, 0F8h
0x1801c8528  pop     r15
0x1801c852a  pop     r14
0x1801c852c  pop     r13
0x1801c852e  pop     r12
0x1801c8530  pop     rdi
0x1801c8531  pop     rsi
0x1801c8532  pop     rbx
0x1801c8533  pop     rbp
0x1801c8534  retn
0x1801c8536  mov     ecx, [rsp+30h]
0x1801c853a  cmp     ecx, edi
0x1801c853c  jnb     short loc_1801C8521
0x1801c853e  mov     r14d, ecx
0x1801c8541  mov     rbx, [rsp+130h+var_C8]
0x1801c8546  imul    r14, rbx
0x1801c854a  mov     qword ptr [rsp+130h+var_F0], r14
0x1801c854f  mov     r15, [r15]
0x1801c8552  add     r15, r14
0x1801c8555  mov     r14d, ecx
0x1801c8558  mov     qword ptr [rsp+130h+var_108], rbx
0x1801c855d  mov     [rsp+130h+var_110], r15
0x1801c8562  mov     r9, rsi
0x1801c8565  lea     r8, ?ClearUnknown@ProjectionMarshaler@Projection@@AEAAXPEAPEAUIUnknown@@@Z; Projection::ProjectionMarshaler::ClearUnknown(IUnknown * *)
0x1801c856c  lea     rdx, ?ClearString@ProjectionMarshaler@Projection@@AEAAXPEAPEAUHSTRING__@@@Z; Projection::ProjectionMarshaler::ClearString(HSTRING__ * *)
0x1801c8573  mov     rcx, r13
0x1801c8576  call    ?RecordTypeToUndo@ProjectionMarshaler@Projection@@AEAAXP812@EAAXPEAPEAUHSTRING__@@@ZP812@EAAXPEAPEAUIUnknown@@@ZPEBUConcreteType@ProjectionModel@@PEAE_K@Z; Projection::ProjectionMarshaler::RecordTypeToUndo(void (Projection::ProjectionMarshaler::*)(HSTRING__ * *),void (Projection::ProjectionMarshaler::*)(IUnknown * *),ProjectionModel::ConcreteType const *,uchar *,unsigned __int64)
0x1801c857b  add     r15, rbx
0x1801c857e  inc     r14d
0x1801c8581  cmp     r14d, edi
0x1801c8584  jb      short loc_1801C8558
0x1801c8586  sub     edi, [rsp+30h]
0x1801c858a  mov     r8d, edi
0x1801c858d  imul    r8, rbx; Size
0x1801c8591  mov     r15, [rbp+3Fh+arg_28]
0x1801c8595  mov     rcx, qword ptr [rsp+130h+var_F0]
0x1801c859a  add     rcx, [r15]; void *
0x1801c859d  xor     edx, edx; Val
0x1801c859f  call    memset_0
0x1801c85a4  jmp     loc_1801C8848
0x1801c85a9  xor     r8d, r8d; unsigned __int16 *
0x1801c85ac  mov     edx, 800A000Dh; int
0x1801c85b1  mov     rcx, [rsp+130h+var_E0]; struct Js::ScriptContext *
0x1801c85b6  call    ?ThrowTypeError@JavascriptError@Js@@SAXPEAVScriptContext@2@JPEBG@Z; Js::JavascriptError::ThrowTypeError(Js::ScriptContext *,long,ushort const *)
0x1801c85bc  cmp     [rsp+130h+var_F0], r12d
0x1801c85c1  jnz     loc_1801C86CC
0x1801c85c7  mov     rcx, rsi; struct ProjectionModel::Type *
0x1801c85ca  call    ?IsBlittable@ConcreteType@ProjectionModel@@SA_NPEBUType@2@@Z; ProjectionModel::ConcreteType::IsBlittable(ProjectionModel::Type const *)
0x1801c85cf  test    al, al
0x1801c85d1  jnz     loc_1801C86CC
0x1801c85d7  mov     rax, [rsp+130h+var_E0]
0x1801c85dc  mov     rax, [rax+8E8h]
0x1801c85e3  mov     qword ptr [rsp+130h+var_F0], rax
0x1801c85e8  lea     r8, ?AllocFinalized@Recycler@@QEAAPEAD_K@Z; Recycler::AllocFinalized(unsigned __int64)
0x1801c85ef  mov     rdx, rax
0x1801c85f2  mov     ecx, 48h ; 'H'
0x1801c85f7  call    ??$?2UHeapAllocator@@@@YAPEAX_KPEAUHeapAllocator@@P80@EAAPEAD0@Z@Z; operator new<HeapAllocator>(unsigned __int64,HeapAllocator *,char * (HeapAllocator::*)(unsigned __int64))
0x1801c85fc  mov     rbx, rax
0x1801c85ff  test    rax, rax
0x1801c8602  jz      loc_1801C868C
0x1801c8608  mov     rax, [r13+10h]
0x1801c860c  mov     r12, [rax+60h]
0x1801c8610  add     r12, 20D8h
0x1801c8617  cmp     byte ptr [r12+10h], 0
0x1801c861d  jnz     short loc_1801C8651
0x1801c861f  mov     rax, [r12]
0x1801c8623  mov     rcx, r12
0x1801c8626  mov     rax, [rax+8]
0x1801c862a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c862f  mov     rcx, rax; lpLibFileName
0x1801c8632  xor     edx, edx; hFile
0x1801c8634  mov     r8d, 800h; dwFlags
0x1801c863a  call    cs:__imp_LoadLibraryExW
0x1801c8641  nop     dword ptr [rax+rax+00h]
0x1801c8646  mov     [r12+8], rax
0x1801c864b  mov     byte ptr [r12+10h], 1
0x1801c8651  lea     rax, ??_7FinalizableTypedArrayContents@Projection@@6B@; const Projection::FinalizableTypedArrayContents::`vftable'
0x1801c8658  mov     [rbx], rax
0x1801c865b  mov     [rbx+8], rsi
0x1801c865f  mov     [rbx+10h], edi
0x1801c8662  mov     qword ptr [rbx+18h], 0
0x1801c866a  mov     rax, qword ptr [rsp+130h+var_F0]
0x1801c866f  mov     [rbx+20h], rax
0x1801c8673  mov     [rbx+28h], r12
0x1801c8677  mov     rax, [rsi+18h]
0x1801c867b  mov     [rbx+30h], rax
0x1801c867f  xor     r12d, r12d
0x1801c8682  mov     [rbx+38h], r12
0x1801c8686  mov     [rbx+40h], r12d
0x1801c868a  jmp     short loc_1801C868F
0x1801c868c  mov     rbx, r12
0x1801c868f  mov     r8b, 1; bool
0x1801c8692  mov     rdx, rbx; void *
0x1801c8695  mov     rcx, r13; this
0x1801c8698  call    ?RecordRecyclerVar@ProjectionMarshaler@Projection@@AEAAXPEAX_N@Z; Projection::ProjectionMarshaler::RecordRecyclerVar(void *,bool)
0x1801c869d  mov     rcx, r14; unsigned __int64
0x1801c86a0  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1801c86a5  mov     rdi, rax
0x1801c86a8  test    rax, rax
0x1801c86ab  jz      loc_1801C88F5
0x1801c86b1  mov     r8, r14; Size
0x1801c86b4  xor     edx, edx; Val
0x1801c86b6  mov     rcx, rax; void *
0x1801c86b9  call    memset_0
0x1801c86be  mov     [rbx+18h], rdi
0x1801c86c2  mov     rcx, rbx; this
0x1801c86c5  call    ?Initialize@FinalizableTypedArrayContents@Projection@@QEAAXXZ; Projection::FinalizableTypedArrayContents::Initialize(void)
0x1801c86ca  jmp     short loc_1801C86F8
0x1801c86cc  lea     rax, ?AllocZero@ArenaAllocator@@QEAAPEAD_K@Z; ArenaAllocator::AllocZero(unsigned __int64)
0x1801c86d3  mov     qword ptr [rsp+130h+var_F0], rax
0x1801c86d8  mov     dword ptr [rsp+130h+var_E8], r12d
0x1801c86dd  mov     eax, [rbp+3Fh+var_BC]
0x1801c86e0  mov     dword ptr [rsp+130h+var_E8+4], eax
  ... truncated ...
```
