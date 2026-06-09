# Projection::ProjectionMarshaler::WriteInArrayTypeIndividual(void *,ProjectionModel::ArrayType::Impl const *,bool,uchar *,uchar *,bool,bool,uint)

- ea: `0x180159350`
- end: `0x1801599fb`
- name: `?WriteInArrayTypeIndividual@ProjectionMarshaler@Projection@@QEAAXPEAXPEBUImpl@ArrayType@ProjectionModel@@_NPEAE322I@Z`
- size: `1707`
- prototype: `void __fastcall(Projection::ProjectionMarshaler *__hidden this, void *, const struct ProjectionModel::ArrayType::Impl *, bool, unsigned __int8 *, unsigned __int8 *, bool, bool, unsigned int)`
- caller_count: `4`
- callee_count: `26`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18008a50c`
- `0x180149998`
- `0x180159a04`
- `0x18047e354`

## callees

- `0x180006c14`
- `0x18002e3d0`
- `0x1800731f0`
- `0x1800891a4`
- `0x18008b6a8`
- `0x180149998`
- `0x18014e864`
- `0x180159350`
- `0x180159b90`
- `0x180159c48`
- `0x180159d10`
- `0x18019d4d0`
- `0x1801dc3f0`
- `0x1801dc434`
- `0x1801e0640`
- `0x18022d8b0`
- `0x1802401b0`
- `0x180283588`
- `0x1802b4b58`
- `0x1802e99f0`
- `0x1803d37a0`
- `0x1803f4c94`
- `0x180471f54`
- `0x180481574`
- `0x1805a9c5a`
- `0x1805cd010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1801596fd`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180159863`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1801596fd`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180159863`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801598ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801598ce`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Projection::ProjectionMarshaler::WriteInArrayTypeIndividual(
        Projection::ProjectionMarshaler *this,
        void *a2,
        const struct ProjectionModel::Type **a3,
        char a4,
        unsigned __int8 *a5,
        unsigned __int8 *a6,
        bool a7,
        bool a8,
        unsigned int a9)
{
  unsigned __int64 v9; // rsi
  BOOL v11; // edi
  bool IsArrayInstance; // bl
  int v13; // edx
  int v14; // r8d
  struct Js::ScriptContext *v15; // rax
  unsigned int v16; // edi
  unsigned int v17; // r14d
  const struct ProjectionModel::ConcreteType *v18; // rax
  const struct ProjectionModel::ConcreteType *v19; // r13
  size_t v20; // r14
  double v21; // xmm0_8
  char v22; // dl
  void **v23; // r12
  char v24; // bl
  __int64 v25; // r8
  __int64 v26; // rbx
  unsigned int v27; // esi
  unsigned int v28; // r14d
  unsigned __int64 v29; // r12
  unsigned int v30; // r14d
  _QWORD *v31; // rbx
  char *(*v32)(Memory::ArenaAllocator *__hidden, unsigned __int64); // rcx
  const WCHAR *v33; // rax
  HMODULE Library; // rax
  __int64 v35; // rdx
  __int64 v36; // rcx
  void *v37; // rax
  __int64 v38; // rdi
  _QWORD *v39; // rbx
  char *(*v40)(Memory::ArenaAllocator *__hidden, unsigned __int64); // rdx
  const WCHAR *v41; // rax
  HMODULE v42; // rax
  LPVOID v43; // rax
  LPVOID v44; // rdi
  __int64 v45; // r14
  _QWORD *v46; // rax
  struct Js::ScriptContext *v47; // rdx
  unsigned __int8 *v48; // rdi
  unsigned int v49; // r12d
  unsigned __int64 v50; // rbx
  void *v51; // rax
  void *ElementI; // rax
  unsigned int v53; // [rsp+3Ch] [rbp-CCh]
  char *(*v54)(Memory::ArenaAllocator *__hidden, unsigned __int64); // [rsp+48h] [rbp-C0h] BYREF
  __int64 v55; // [rsp+50h] [rbp-B8h]
  int v56; // [rsp+58h] [rbp-B0h]
  int v57; // [rsp+5Ch] [rbp-ACh]
  unsigned __int64 v58; // [rsp+68h] [rbp-A0h]
  struct Js::ScriptContext *v59; // [rsp+70h] [rbp-98h]
  __int64 v60; // [rsp+78h] [rbp-90h]
  unsigned __int64 v61; // [rsp+80h] [rbp-88h]
  int v62; // [rsp+8Ch] [rbp-7Ch]
  int v63; // [rsp+94h] [rbp-74h]
  __int64 v64; // [rsp+98h] [rbp-70h]
  _BYTE v65[176]; // [rsp+A8h] [rbp-60h] BYREF

  v64 = -2;
  v9 = (unsigned __int64)a2;
  Projection::ProjectionMarshaler::RecordRecyclerVar(this, a2, 0);
  v11 = HIWORD(v9) != 1 && v9 < 0x4000000000000LL && **(_DWORD **)(v9 + 8) <= 1u;
  LODWORD(v60) = v11;
  IsArrayInstance = Projection::ArrayAsCollection::IsArrayInstance((void *)v9);
  LODWORD(v58) = Projection::ArrayProjection::Is((void *)v9);
  v13 = Js::TypedArrayBase::Is((void *)v9);
  LODWORD(v54) = v13;
  v15 = *(struct Js::ScriptContext **)(*((_QWORD *)this + 2) + 112LL);
  v59 = v15;
  if ( v11 )
  {
    if ( !IsArrayInstance )
      goto LABEL_13;
LABEL_12:
    v16 = *(_DWORD *)(v9 + 32);
    goto LABEL_17;
  }
  if ( IsArrayInstance )
    goto LABEL_12;
  if ( !v14 )
  {
    if ( !v13 )
      Js::JavascriptError::ThrowTypeError(v15, -2146823257, 0);
    goto LABEL_14;
  }
LABEL_13:
  if ( v13 )
  {
LABEL_14:
    v16 = *((_DWORD *)Js::TypedArrayBase::FromVar((void *)v9) + 8);
    goto LABEL_17;
  }
  v16 = 0;
  if ( v14 )
    v16 = *(_DWORD *)(*(_QWORD *)(v9 + 48) + 16LL);
LABEL_17:
  v17 = v16;
  if ( a8 )
    v17 = a9;
  v53 = v17;
  v18 = ProjectionModel::ConcreteType::From(a3[5]);
  v19 = v18;
  if ( a8 && v17 > v16 )
    Js::JavascriptError::ThrowTypeError(v59, -2146823177, 0);
  v61 = *((_QWORD *)v18 + 3);
  v20 = v61 * v16;
  if ( v20 < v16 )
    goto LABEL_76;
  v21 = (v20 & 0x8000000000000000uLL) != 0LL
      ? (double)(int)(v20 & 1 | (v20 >> 1)) + (double)(int)(v20 & 1 | (v20 >> 1))
      : (double)(int)v20;
  if ( (unsigned int)Js::JavascriptMath::ToInt32Core(v21) < v16 )
    goto LABEL_76;
  *(_DWORD *)a5 = v16;
  v22 = 1;
  v23 = (void **)a6;
  v24 = 0;
  if ( !*((_DWORD *)this + 24) )
  {
    if ( (_DWORD)v58 )
    {
      v25 = *(_QWORD *)(v9 + 48);
      if ( *(_DWORD *)(*(_QWORD *)(v25 + 8) + 4LL) == *((_DWORD *)v19 + 1) )
      {
        *(_QWORD *)a6 = *(_QWORD *)(v25 + 24);
        v22 = 0;
      }
      if ( !v22 )
      {
        v24 = 0;
LABEL_37:
        if ( a7 )
        {
          v26 = *(_QWORD *)a6;
          v27 = 0;
          if ( v16 )
          {
            do
            {
              Projection::ProjectionMarshaler::RecordTypeToUndo(
                this,
                Projection::ProjectionMarshaler::ClearString,
                Projection::ProjectionMarshaler::ClearUnknown,
                v19,
                v26,
                v61);
              v26 += v61;
              ++v27;
            }
            while ( v27 < v16 );
            v23 = (void **)a6;
          }
          memset_0(*v23, 0, v20);
          return;
        }
        v28 = v53;
        if ( v53 >= v16 )
          return;
        v58 = v61 * v53;
        v29 = v58 + *(_QWORD *)a6;
        do
        {
          Projection::ProjectionMarshaler::RecordTypeToUndo(
            this,
            Projection::ProjectionMarshaler::ClearString,
            Projection::ProjectionMarshaler::ClearUnknown,
            v19,
            v29,
            v61);
          v29 += v61;
          ++v28;
        }
        while ( v28 < v16 );
        v30 = v53;
        v23 = (void **)a6;
        memset_0((void *)(*(_QWORD *)a6 + v58), 0, v61 * (v16 - v53));
        v9 = (unsigned __int64)a2;
        goto LABEL_70;
      }
      goto LABEL_47;
    }
    if ( (_DWORD)v54 )
    {
      if ( (unsigned int)Projection::ArrayProjection::SupportTypedArray(v19)
        && !(unsigned int)Projection::ArrayProjection::NeedConversion(v19, (void *)v9) )
      {
        *(_QWORD *)a6 = *((_QWORD *)Js::TypedArrayBase::FromVar((void *)v9) + 7);
        goto LABEL_37;
      }
LABEL_47:
      Js::JavascriptError::ThrowTypeError(v59, -2146828275, 0);
    }
    if ( (_DWORD)v60 || ProjectionModel::ConcreteType::IsBlittable(v19) )
    {
      v54 = Memory::ArenaAllocator::AllocZero;
      LODWORD(v55) = 0;
      HIDWORD(v55) = v62;
      v38 = Memory::AllocateArray<Memory::Recycler,unsigned char,0>(*((_QWORD *)this + 1), &v54, v20);
LABEL_58:
      *(_QWORD *)a6 = v38;
      v30 = v53;
      if ( !a7 )
        goto LABEL_71;
LABEL_70:
      if ( !v24 )
        return;
      goto LABEL_71;
    }
    v58 = *((_QWORD *)v59 + 126);
    v54 = (char *(*)(Memory::ArenaAllocator *__hidden, unsigned __int64))Memory::Recycler::AllocFinalizedInlined;
    v55 = 0;
    v56 = 0;
    v57 = v63;
    v31 = (_QWORD *)operator new[]<Memory::JitArenaAllocator>(72, v58, &v54);
    if ( v31 )
    {
      v32 = (char *(*)(Memory::ArenaAllocator *__hidden, unsigned __int64))(*(_QWORD *)(*((_QWORD *)this + 2) + 96LL)
                                                                          + 7920LL);
      v54 = v32;
      if ( !*((_BYTE *)v32 + 16) )
      {
        v33 = (const WCHAR *)(*(__int64 (__fastcall **)(char *(*)(Memory::ArenaAllocator *__hidden, unsigned __int64)))(*(_QWORD *)v32 + 8LL))(v32);
        Library = LoadLibraryExW(v33, 0, 0x800u);
        v32 = v54;
        *((_QWORD *)v54 + 1) = Library;
        *((_BYTE *)v32 + 16) = 1;
      }
      *v31 = &Projection::FinalizableTypedArrayContents::`vftable';
      v31[1] = v19;
      *((_DWORD *)v31 + 4) = v16;
      v31[3] = 0;
      v31[4] = v58;
      v31[5] = v32;
      v31[6] = *((_QWORD *)v19 + 3);
      v31[7] = 0;
      *((_DWORD *)v31 + 16) = 0;
    }
    else
    {
      v31 = 0;
    }
    Projection::ProjectionMarshaler::RecordRecyclerVar(this, v31, 1);
    v37 = (void *)Memory::AllocateArray<Memory::HeapAllocator,char,1>(v36, v35, v20);
    v38 = (__int64)v37;
    if ( v37 )
    {
      memset_0(v37, 0, v20);
      v31[3] = v38;
      Projection::FinalizableTypedArrayContents::Initialize((Projection::FinalizableTypedArrayContents *)v31);
      v24 = 0;
      goto LABEL_58;
    }
LABEL_76:
    Js::JavascriptError::MapAndThrowError(v59, -2147024882);
  }
  if ( a4 )
  {
    v58 = *((_QWORD *)v59 + 126);
    v54 = (char *(*)(Memory::ArenaAllocator *__hidden, unsigned __int64))Memory::Recycler::AllocFinalizedInlined;
    v55 = 0;
    v56 = 0;
    v57 = v63;
    v39 = (_QWORD *)operator new[]<Memory::JitArenaAllocator>(72, v58, &v54);
    if ( v39 )
    {
      v40 = (char *(*)(Memory::ArenaAllocator *__hidden, unsigned __int64))(*(_QWORD *)(*((_QWORD *)this + 2) + 96LL)
                                                                          + 7920LL);
      v54 = v40;
      if ( !*((_BYTE *)v40 + 16) )
      {
        v41 = (const WCHAR *)(*(__int64 (__fastcall **)(char *(*)(Memory::ArenaAllocator *__hidden, unsigned __int64)))(*(_QWORD *)v40 + 8LL))(v40);
        v42 = LoadLibraryExW(v41, 0, 0x800u);
        v40 = v54;
        *((_QWORD *)v54 + 1) = v42;
        *((_BYTE *)v40 + 16) = 1;
      }
      *v39 = &Projection::FinalizableTypedArrayContents::`vftable';
      v39[1] = v19;
      *((_DWORD *)v39 + 4) = v16;
      v39[3] = 0;
      v39[4] = v58;
      v39[5] = v40;
      v39[6] = *((_QWORD *)v19 + 3);
      v39[7] = 0;
      *((_DWORD *)v39 + 16) = 1;
    }
    else
    {
      v39 = 0;
    }
    Projection::ProjectionMarshaler::RecordRecyclerVar(this, v39, 1);
    v43 = CoTaskMemAlloc(v20);
    v44 = v43;
    if ( v43 )
    {
      v39[3] = v43;
      Projection::FinalizableTypedArrayContents::Initialize((Projection::FinalizableTypedArrayContents *)v39);
      v45 = *((_QWORD *)this + 11);
      v54 = (char *(*)(Memory::ArenaAllocator *__hidden, unsigned __int64))Memory::ArenaAllocator::Alloc;
      LODWORD(v55) = 0;
      HIDWORD(v55) = v62;
      v46 = (_QWORD *)operator new<Memory::JitArenaAllocator>(16, *((_QWORD *)this + 1), &v54);
      if ( v46 )
      {
        *v46 = v39;
        v46[1] = v45;
      }
      *((_QWORD *)this + 11) = v46;
      *(_QWORD *)a6 = v44;
      v24 = 1;
      v30 = v53;
      goto LABEL_70;
    }
    goto LABEL_76;
  }
  v30 = v53;
LABEL_71:
  Projection::ProjectionMarshaler::ProjectionMarshaler(v65, 1, *((_QWORD *)this + 2));
  v48 = (unsigned __int8 *)*v23;
  v49 = 0;
  if ( v30 )
  {
    v50 = v61;
    do
    {
      v51 = Js::JavascriptNumber::ToVar(v49, v47);
      ElementI = Js::JavascriptOperators::OP_GetElementI((void *)v9, v51, v59);
      Projection::ProjectionMarshaler::WriteInType((Projection::ProjectionMarshaler *)v65, ElementI, v19, v48, v50, 1);
      Projection::ProjectionMarshaler::RecordTypeToUndo(
        this,
        Projection::ProjectionMarshaler::RecordDelegateOutString,
        Projection::ProjectionMarshaler::RecordDelegateOutUnknown,
        v19,
        v48,
        v50);
      v48 += v50;
      ++v49;
    }
    while ( v49 < v30 );
  }
  Projection::ProjectionMarshaler::~ProjectionMarshaler((Projection::ProjectionMarshaler *)v65);
}

```

## disassembly

```asm
0x180159350  mov     rax, rsp
0x180159353  mov     [rax+20h], r9b
0x180159357  mov     [rax+18h], r8
0x18015935b  mov     [rax+10h], rdx
0x18015935f  mov     [rax+8], rcx
0x180159363  push    rbp
0x180159364  push    rbx
0x180159365  push    rsi
0x180159366  push    rdi
0x180159367  push    r12
0x180159369  push    r13
0x18015936b  push    r14
0x18015936d  push    r15
0x18015936f  lea     rbp, [rax-58h]
0x180159373  sub     rsp, 118h
0x18015937a  mov     [rbp+50h+var_C0], 0FFFFFFFFFFFFFFFEh
0x180159382  xor     r8d, r8d; bool
0x180159385  mov     rsi, [rbp+50h+arg_8]
0x180159389  mov     rdx, rsi; void *
0x18015938c  mov     r15, [rbp+50h+arg_0]
0x180159390  mov     rcx, r15; this
0x180159393  call    ?RecordRecyclerVar@ProjectionMarshaler@Projection@@AEAAXPEAX_N@Z; Projection::ProjectionMarshaler::RecordRecyclerVar(void *,bool)
0x180159398  mov     rax, rsi
0x18015939b  shr     rax, 30h
0x18015939f  cmp     rax, 1
0x1801593a3  jz      short loc_1801593C4
0x1801593a5  mov     rax, 4000000000000h
0x1801593af  cmp     rsi, rax
0x1801593b2  jnb     short loc_1801593C4
0x1801593b4  mov     rax, [rsi+8]
0x1801593b8  cmp     dword ptr [rax], 1
0x1801593bb  ja      short loc_1801593C4
0x1801593bd  mov     edi, 1
0x1801593c2  jmp     short loc_1801593C6
0x1801593c4  xor     edi, edi
0x1801593c6  mov     dword ptr [rsp+150h+var_E0], edi
0x1801593ca  mov     rcx, rsi; void *
0x1801593cd  call    ?IsArrayInstance@ArrayAsCollection@Projection@@SA_NPEAX@Z; Projection::ArrayAsCollection::IsArrayInstance(void *)
0x1801593d2  mov     bl, al
0x1801593d4  mov     rcx, rsi; void *
0x1801593d7  call    ?Is@ArrayProjection@Projection@@SAHPEAX@Z; Projection::ArrayProjection::Is(void *)
0x1801593dc  mov     r8d, eax
0x1801593df  mov     dword ptr [rsp+150h+var_F0], eax
0x1801593e3  mov     rcx, rsi; void *
0x1801593e6  call    ?Is@TypedArrayBase@Js@@SAHPEAX@Z; Js::TypedArrayBase::Is(void *)
0x1801593eb  mov     edx, eax
0x1801593ed  mov     dword ptr [rsp+150h+var_110], eax
0x1801593f1  mov     rcx, [r15+10h]
0x1801593f5  mov     rax, [rcx+70h]
0x1801593f9  mov     [rsp+150h+var_E8], rax
0x1801593fe  test    edi, edi
0x180159400  jnz     short loc_180159420
0x180159402  test    bl, bl
0x180159404  jnz     short loc_180159424
0x180159406  test    r8d, r8d
0x180159409  jnz     short loc_180159429
0x18015940b  test    edx, edx
0x18015940d  jnz     short loc_18015942D
0x18015940f  xor     r8d, r8d; unsigned __int16 *
0x180159412  mov     edx, 800A13A7h; int
0x180159417  mov     rcx, rax; struct Js::ScriptContext *
0x18015941a  call    ?ThrowTypeError@JavascriptError@Js@@SAXPEAVScriptContext@2@HPEBG@Z; Js::JavascriptError::ThrowTypeError(Js::ScriptContext *,int,ushort const *)
0x180159420  test    bl, bl
0x180159422  jz      short loc_180159429
0x180159424  mov     edi, [rsi+20h]
0x180159427  jmp     short loc_180159448
0x180159429  test    edx, edx
0x18015942b  jz      short loc_18015943A
0x18015942d  mov     rcx, rsi; void *
0x180159430  call    ?FromVar@TypedArrayBase@Js@@SAPEAV12@PEAX@Z; Js::TypedArrayBase::FromVar(void *)
0x180159435  mov     edi, [rax+20h]
0x180159438  jmp     short loc_180159448
0x18015943a  xor     edi, edi
0x18015943c  test    r8d, r8d
0x18015943f  jz      short loc_180159448
0x180159441  mov     rax, [rsi+30h]
0x180159445  mov     edi, [rax+10h]
0x180159448  mov     r14d, edi
0x18015944b  mov     bl, [rbp+50h+arg_38]
0x180159451  test    bl, bl
0x180159453  cmovnz  r14d, [rbp+50h+arg_40]
0x18015945b  mov     [rsp+34h], r14d
0x180159460  mov     rcx, [rbp+50h+arg_10]
0x180159464  mov     rcx, [rcx+28h]; struct ProjectionModel::Type *
0x180159468  call    ?From@ConcreteType@ProjectionModel@@SAPEBU12@PEBUType@2@@Z; ProjectionModel::ConcreteType::From(ProjectionModel::Type const *)
0x18015946d  mov     r13, rax
0x180159470  test    bl, bl
0x180159472  jz      short loc_18015948C
0x180159474  cmp     r14d, edi
0x180159477  jbe     short loc_18015948C
0x180159479  xor     r8d, r8d; unsigned __int16 *
0x18015947c  mov     edx, 800A13F7h; int
0x180159481  mov     rcx, [rsp+150h+var_E8]; struct Js::ScriptContext *
0x180159486  call    ?ThrowTypeError@JavascriptError@Js@@SAXPEAVScriptContext@2@HPEBG@Z; Js::JavascriptError::ThrowTypeError(Js::ScriptContext *,int,ushort const *)
0x18015948c  mov     rcx, [rax+18h]
0x180159490  mov     [rsp+150h+var_D8], rcx
0x180159495  mov     eax, edi
0x180159497  mov     r14d, edi
0x18015949a  imul    r14, rcx
0x18015949e  cmp     r14, rax
0x1801594a1  jb      loc_1801599EB
0x1801594a7  xorps   xmm0, xmm0
0x1801594aa  test    r14, r14
0x1801594ad  js      short loc_1801594B6
0x1801594af  cvtsi2sd xmm0, r14
0x1801594b4  jmp     short loc_1801594CE
0x1801594b6  mov     rcx, r14
0x1801594b9  shr     rcx, 1
0x1801594bc  mov     rax, r14
0x1801594bf  and     eax, 1
0x1801594c2  or      rcx, rax
0x1801594c5  cvtsi2sd xmm0, rcx
0x1801594ca  addsd   xmm0, xmm0; double
0x1801594ce  call    ?ToInt32Core@JavascriptMath@Js@@SAHN@Z; Js::JavascriptMath::ToInt32Core(double)
0x1801594d3  cmp     eax, edi
0x1801594d5  jb      loc_1801599EB
0x1801594db  mov     rax, [rbp+50h+arg_20]
0x1801594e2  mov     [rax], edi
0x1801594e4  mov     dl, 1
0x1801594e6  mov     [rsp+30h], dl
0x1801594ea  mov     r12, [rbp+50h+arg_28]
0x1801594f1  xor     ebx, ebx
0x1801594f3  cmp     [r15+60h], ebx
0x1801594f7  jnz     loc_1801597DB
0x1801594fd  cmp     dword ptr [rsp+150h+var_F0], ebx
0x180159501  jz      short loc_18015952A
0x180159503  mov     r8, [rsi+30h]
0x180159507  mov     rcx, [r8+8]
0x18015950b  mov     eax, [r13+4]
0x18015950f  cmp     [rcx+4], eax
0x180159512  jnz     short loc_18015951E
0x180159514  mov     rax, [r8+18h]
0x180159518  mov     [r12], rax
0x18015951c  mov     dl, bl
0x18015951e  test    dl, dl
0x180159520  jnz     loc_180159654
0x180159526  mov     bl, dl
0x180159528  jmp     short loc_180159567
0x18015952a  cmp     dword ptr [rsp+150h+var_110], ebx
0x18015952e  jz      loc_180159667
0x180159534  mov     rcx, r13; struct ProjectionModel::ConcreteType *
0x180159537  call    ?SupportTypedArray@ArrayProjection@Projection@@SAHPEBUConcreteType@ProjectionModel@@@Z; Projection::ArrayProjection::SupportTypedArray(ProjectionModel::ConcreteType const *)
0x18015953c  test    eax, eax
0x18015953e  jz      loc_180159654
0x180159544  mov     rdx, rsi; void *
0x180159547  mov     rcx, r13; struct ProjectionModel::ConcreteType *
0x18015954a  call    ?NeedConversion@ArrayProjection@Projection@@SAHPEBUConcreteType@ProjectionModel@@PEAX@Z; Projection::ArrayProjection::NeedConversion(ProjectionModel::ConcreteType const *,void *)
0x18015954f  test    eax, eax
0x180159551  jnz     loc_180159654
0x180159557  mov     rcx, rsi; void *
0x18015955a  call    ?FromVar@TypedArrayBase@Js@@SAPEAV12@PEAX@Z; Js::TypedArrayBase::FromVar(void *)
0x18015955f  mov     rcx, [rax+38h]
0x180159563  mov     [r12], rcx
0x180159567  cmp     [rbp+50h+arg_30], 0
0x18015956e  jz      short loc_1801595D5
0x180159570  mov     rbx, [r12]
0x180159574  xor     esi, esi
0x180159576  test    edi, edi
0x180159578  jz      short loc_1801595B2
0x18015957a  mov     r12, [rsp+150h+var_D8]
0x18015957f  mov     qword ptr [rsp+150h+var_128], r12
0x180159584  mov     [rsp+150h+var_130], rbx
0x180159589  mov     r9, r13
0x18015958c  lea     r8, ?ClearUnknown@ProjectionMarshaler@Projection@@AEAAXPEAPEAUIUnknown@@@Z; Projection::ProjectionMarshaler::ClearUnknown(IUnknown * *)
0x180159593  lea     rdx, ?ClearString@ProjectionMarshaler@Projection@@AEAAXPEAPEAUHSTRING__@@@Z; Projection::ProjectionMarshaler::ClearString(HSTRING__ * *)
0x18015959a  mov     rcx, r15
0x18015959d  call    ?RecordTypeToUndo@ProjectionMarshaler@Projection@@AEAAXP812@EAAXPEAPEAUHSTRING__@@@ZP812@EAAXPEAPEAUIUnknown@@@ZPEBUConcreteType@ProjectionModel@@PEAE_K@Z; Projection::ProjectionMarshaler::RecordTypeToUndo(void (Projection::ProjectionMarshaler::*)(HSTRING__ * *),void (Projection::ProjectionMarshaler::*)(IUnknown * *),ProjectionModel::ConcreteType const *,uchar *,unsigned __int64)
0x1801595a2  add     rbx, r12
0x1801595a5  inc     esi
0x1801595a7  cmp     esi, edi
0x1801595a9  jb      short loc_18015957F
0x1801595ab  mov     r12, [rbp+50h+arg_28]
0x1801595b2  mov     r8, r14; Size
0x1801595b5  xor     edx, edx; Val
0x1801595b7  mov     rcx, [r12]; void *
0x1801595bb  call    memset_0
0x1801595c0  add     rsp, 118h
0x1801595c7  pop     r15
0x1801595c9  pop     r14
0x1801595cb  pop     r13
0x1801595cd  pop     r12
0x1801595cf  pop     rdi
0x1801595d0  pop     rsi
0x1801595d1  pop     rbx
0x1801595d2  pop     rbp
0x1801595d3  retn
0x1801595d5  mov     r14d, [rsp+34h]
0x1801595da  cmp     r14d, edi
0x1801595dd  jnb     short loc_1801595C0
0x1801595df  mov     ecx, r14d
0x1801595e2  mov     rsi, [rsp+150h+var_D8]
0x1801595e7  imul    rcx, rsi
0x1801595eb  mov     [rsp+150h+var_F0], rcx
0x1801595f0  mov     r12, [r12]
0x1801595f4  add     r12, rcx
0x1801595f7  mov     qword ptr [rsp+150h+var_128], rsi
0x1801595fc  mov     [rsp+150h+var_130], r12
0x180159601  mov     r9, r13
0x180159604  lea     r8, ?ClearUnknown@ProjectionMarshaler@Projection@@AEAAXPEAPEAUIUnknown@@@Z; Projection::ProjectionMarshaler::ClearUnknown(IUnknown * *)
0x18015960b  lea     rdx, ?ClearString@ProjectionMarshaler@Projection@@AEAAXPEAPEAUHSTRING__@@@Z; Projection::ProjectionMarshaler::ClearString(HSTRING__ * *)
0x180159612  mov     rcx, r15
0x180159615  call    ?RecordTypeToUndo@ProjectionMarshaler@Projection@@AEAAXP812@EAAXPEAPEAUHSTRING__@@@ZP812@EAAXPEAPEAUIUnknown@@@ZPEBUConcreteType@ProjectionModel@@PEAE_K@Z; Projection::ProjectionMarshaler::RecordTypeToUndo(void (Projection::ProjectionMarshaler::*)(HSTRING__ * *),void (Projection::ProjectionMarshaler::*)(IUnknown * *),ProjectionModel::ConcreteType const *,uchar *,unsigned __int64)
0x18015961a  add     r12, rsi
0x18015961d  inc     r14d
0x180159620  cmp     r14d, edi
0x180159623  jb      short loc_1801595F7
0x180159625  mov     r14d, [rsp+34h]
0x18015962a  sub     edi, r14d
0x18015962d  mov     r8d, edi
0x180159630  imul    r8, rsi; Size
0x180159634  mov     r12, [rbp+50h+arg_28]
0x18015963b  mov     rcx, [rsp+150h+var_F0]
0x180159640  add     rcx, [r12]; void *
0x180159644  xor     edx, edx; Val
0x180159646  call    memset_0
0x18015964b  mov     rsi, [rbp+50h+arg_8]
0x18015964f  jmp     loc_180159941
0x180159654  xor     r8d, r8d; unsigned __int16 *
0x180159657  mov     edx, 800A000Dh; int
0x18015965c  mov     rcx, [rsp+150h+var_E8]; struct Js::ScriptContext *
0x180159661  call    ?ThrowTypeError@JavascriptError@Js@@SAXPEAVScriptContext@2@HPEBG@Z; Js::JavascriptError::ThrowTypeError(Js::ScriptContext *,int,ushort const *)
0x180159667  cmp     dword ptr [rsp+150h+var_E0], ebx
0x18015966b  jnz     loc_180159796
0x180159671  mov     rcx, r13; struct ProjectionModel::Type *
0x180159674  call    ?IsBlittable@ConcreteType@ProjectionModel@@SA_NPEBUType@2@@Z; ProjectionModel::ConcreteType::IsBlittable(ProjectionModel::Type const *)
0x180159679  test    al, al
0x18015967b  jnz     loc_180159796
0x180159681  mov     rax, [rsp+150h+var_E8]
0x180159686  mov     rcx, [rax+3F0h]
0x18015968d  mov     [rsp+150h+var_F0], rcx
0x180159692  lea     rax, ?AllocFinalizedInlined@Recycler@Memory@@QEAAPEAD_K@Z; Memory::Recycler::AllocFinalizedInlined(unsigned __int64)
0x180159699  mov     [rsp+150h+var_110], rax
0x18015969e  mov     qword ptr [rsp+150h+var_108], rbx
0x1801596a3  mov     [rsp+150h+var_100], ebx
0x1801596a7  mov     eax, [rbp+50h+var_C4]
0x1801596aa  mov     [rsp+150h+var_FC], eax
0x1801596ae  lea     r8, [rsp+150h+var_110]
0x1801596b3  mov     rdx, rcx
0x1801596b6  mov     ecx, 48h ; 'H'
0x1801596bb  call    ??$?_UVJitArenaAllocator@Memory@@@@YAPEAX_KPEAVJitArenaAllocator@Memory@@P801@EAAPEAD0@Z@Z; operator new[]<Memory::JitArenaAllocator>(unsigned __int64,Memory::JitArenaAllocator *,char * (Memory::JitArenaAllocator::*)(unsigned __int64))
0x1801596c0  mov     rbx, rax
0x1801596c3  test    rax, rax
0x1801596c6  jz      loc_180159755
0x1801596cc  mov     rax, [r15+10h]
0x1801596d0  mov     rcx, [rax+60h]
0x1801596d4  add     rcx, 1EF0h
0x1801596db  mov     [rsp+150h+var_110], rcx
0x1801596e0  cmp     byte ptr [rcx+10h], 0
0x1801596e4  jnz     short loc_180159716
0x1801596e6  mov     rax, [rcx]
0x1801596e9  mov     rax, [rax+8]
0x1801596ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801596f2  mov     rcx, rax; lpLibFileName
0x1801596f5  xor     edx, edx; hFile
0x1801596f7  mov     r8d, 800h; dwFlags
0x1801596fd  call    cs:__imp_LoadLibraryExW
0x180159704  nop     dword ptr [rax+rax+00h]
0x180159709  mov     rcx, [rsp+150h+var_110]
0x18015970e  mov     [rcx+8], rax
0x180159712  mov     byte ptr [rcx+10h], 1
0x180159716  lea     rax, ??_7FinalizableTypedArrayContents@Projection@@6B@; const Projection::FinalizableTypedArrayContents::`vftable'
0x18015971d  mov     [rbx], rax
0x180159720  mov     [rbx+8], r13
0x180159724  mov     [rbx+10h], edi
0x180159727  mov     qword ptr [rbx+18h], 0
0x18015972f  mov     rax, [rsp+150h+var_F0]
0x180159734  mov     [rbx+20h], rax
0x180159738  mov     [rbx+28h], rcx
0x18015973c  mov     rax, [r13+18h]
0x180159740  mov     [rbx+30h], rax
0x180159744  mov     qword ptr [rbx+38h], 0
0x18015974c  mov     dword ptr [rbx+40h], 0
0x180159753  jmp     short loc_180159757
0x180159755  xor     ebx, ebx
0x180159757  mov     r8b, 1; bool
0x18015975a  mov     rdx, rbx; void *
0x18015975d  mov     rcx, r15; this
0x180159760  call    ?RecordRecyclerVar@ProjectionMarshaler@Projection@@AEAAXPEAX_N@Z; Projection::ProjectionMarshaler::RecordRecyclerVar(void *,bool)
0x180159765  mov     r8, r14
0x180159768  call    ??$AllocateArray@UHeapAllocator@Memory@@D$00@Memory@@YAPEADPEAUHeapAllocator@0@P810@EAAPEAD_K@Z1@Z; Memory::AllocateArray<Memory::HeapAllocator,char,1>(Memory::HeapAllocator *,char * (Memory::HeapAllocator::*)(unsigned __int64),unsigned __int64)
0x18015976d  mov     rdi, rax
0x180159770  test    rax, rax
0x180159773  jz      loc_1801599EB
0x180159779  mov     r8, r14; Size
0x18015977c  xor     edx, edx; Val
0x18015977e  mov     rcx, rax; void *
0x180159781  call    memset_0
0x180159786  mov     [rbx+18h], rdi
0x18015978a  mov     rcx, rbx; this
0x18015978d  call    ?Initialize@FinalizableTypedArrayContents@Projection@@QEAAXXZ; Projection::FinalizableTypedArrayContents::Initialize(void)
0x180159792  xor     ebx, ebx
0x180159794  jmp     short loc_1801597C1
0x180159796  lea     rax, ?AllocZero@ArenaAllocator@Memory@@QEAAPEAD_K@Z; Memory::ArenaAllocator::AllocZero(unsigned __int64)
0x18015979d  mov     [rsp+150h+var_110], rax
0x1801597a2  mov     [rsp+150h+var_108], ebx
0x1801597a6  mov     eax, [rbp+50h+var_CC]
0x1801597a9  mov     [rsp+150h+var_104], eax
0x1801597ad  mov     r8, r14
0x1801597b0  lea     rdx, [rsp+150h+var_110]
0x1801597b5  mov     rcx, [r15+8]
  ... truncated ...
```
