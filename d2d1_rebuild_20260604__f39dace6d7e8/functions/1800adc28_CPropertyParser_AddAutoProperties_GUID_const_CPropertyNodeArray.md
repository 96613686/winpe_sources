# CPropertyParser::AddAutoProperties(_GUID const &,CPropertyNodeArray *)

- ea: `0x1800adc28`
- end: `0x1800adfe3`
- name: `?AddAutoProperties@CPropertyParser@@AEAAJAEBU_GUID@@PEAVCPropertyNodeArray@@@Z`
- size: `955`
- prototype: `__int64 __fastcall(CPropertyParser *__hidden this, const struct _GUID *, struct CPropertyNodeArray *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800aee68`

## callees

- `0x18001fd58`
- `0x1800389c0`
- `0x1800abb2c`
- `0x1800adc28`
- `0x1800ae71c`
- `0x1800ae788`
- `0x180100670`
- `0x180102004`
- `0x18025b124`
- `0x18025b148`
- `0x180307010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800adf3e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800adf3e`

## string_xrefs

- `0x1800adc4b`: `CLSID`
- `0x1800adc5e`: `Cached`

## pseudocode

```c
__int64 __fastcall CPropertyParser::AddAutoProperties(
        CPropertyParser *this,
        struct _GUID *a2,
        struct CPropertyNodeArray *a3)
{
  int v5; // ebx
  unsigned int v6; // r15d
  _QWORD *v7; // rax
  _QWORD *v8; // rdi
  _QWORD *v9; // rax
  _QWORD *v10; // rbx
  int v11; // r14d
  unsigned int v12; // esi
  __int64 v13; // rcx
  int v14; // eax
  void (__fastcall **v15)(_QWORD *); // rax
  int v16; // r9d
  int v18; // eax
  unsigned int j; // esi
  unsigned int i; // esi
  enum D2D1_PROPERTY_TYPE v21; // [rsp+20h] [rbp-E0h]
  char v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+30h] [rbp-D0h]
  int v24; // [rsp+38h] [rbp-C8h]
  __int64 v25; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD *v26; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD *v27; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD v28[2]; // [rsp+70h] [rbp-90h]
  unsigned __int16 *v29; // [rsp+78h] [rbp-88h]
  unsigned __int8 *v30; // [rsp+80h] [rbp-80h]
  unsigned int v31; // [rsp+88h] [rbp-78h]
  enum D2D1_PROPERTY_TYPE v32[3]; // [rsp+8Ch] [rbp-74h]
  const wchar_t *v33; // [rsp+98h] [rbp-68h]
  int *v34; // [rsp+A0h] [rbp-60h]
  int v35; // [rsp+A8h] [rbp-58h]
  int v36; // [rsp+ACh] [rbp-54h]
  int v37; // [rsp+B0h] [rbp-50h]
  const wchar_t *v38; // [rsp+B8h] [rbp-48h]
  int *v39; // [rsp+C0h] [rbp-40h]
  int v40; // [rsp+C8h] [rbp-38h]
  int v41; // [rsp+CCh] [rbp-34h]
  int v42; // [rsp+D0h] [rbp-30h]
  const wchar_t *v43; // [rsp+D8h] [rbp-28h]
  int *v44; // [rsp+E0h] [rbp-20h]
  int v45; // [rsp+E8h] [rbp-18h]
  int v46; // [rsp+ECh] [rbp-14h]
  int v47; // [rsp+F0h] [rbp-10h]
  const wchar_t *v48; // [rsp+F8h] [rbp-8h]
  int *v49; // [rsp+100h] [rbp+0h]
  int v50; // [rsp+108h] [rbp+8h]
  int v51; // [rsp+10Ch] [rbp+Ch]
  int v52; // [rsp+158h] [rbp+58h] BYREF
  int v53; // [rsp+168h] [rbp+68h] BYREF

  v30 = (unsigned __int8 *)a2;
  v52 = 0;
  v29 = L"CLSID";
  v53 = 0;
  v33 = L"Cached";
  v28[0] = 0x80000000;
  v34 = &v52;
  v31 = 16;
  v38 = L"Precision";
  v32[0] = D2D1_PROPERTY_TYPE_CLSID;
  v39 = &v53;
  v5 = 0;
  v32[1] = D2D1_PROPERTY_TYPE_VECTOR2|0x80000000;
  v43 = L"MinInputs";
  v6 = 0;
  v35 = 4;
  v44 = &v52;
  v48 = L"MaxInputs";
  v49 = &v52;
  v36 = 2;
  v37 = -2147483641;
  v40 = 4;
  v41 = 11;
  v42 = -2147483640;
  v45 = 4;
  v46 = 3;
  v47 = -2147483639;
  v50 = 4;
  v51 = 3;
  while ( 1 )
  {
    if ( v6 >= 5 )
      return (unsigned int)v5;
    v7 = operator new(0x50u, (const struct std::nothrow_t *)&std::nothrow);
    v8 = v7;
    if ( !v7 )
    {
      v5 = -2147024882;
      DoStackCapture(-2147024882);
      return (unsigned int)v5;
    }
    v7[1] = 0;
    *((_BYTE *)v7 + 20) = 0;
    v7[3] = 0;
    v7[6] = 16;
    v7[7] = 0;
    v7[8] = 0;
    *v7 = &RefCountedObject<CPropertyDescription,LockingRequired,DeleteOnZeroReference>::`vftable';
    *((_DWORD *)v7 + 18) = 1;
    v5 = CPropertyDescription::Initialize(
           (CPropertyDescription *)v7,
           (&v29)[4 * v6],
           (&v30)[4 * v6],
           v32[8 * v6 - 1],
           v32[8 * v6]);
    if ( v5 < 0 )
      goto LABEL_16;
    v9 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
    v10 = v9;
    if ( !v9 )
    {
      v5 = -2147024882;
LABEL_16:
      DoStackCapture(v5);
LABEL_17:
      (*(void (__fastcall **)(_QWORD *))(*v8 + 8LL))(v8);
      return (unsigned int)v5;
    }
    *v9 = 0;
    v9[1] = 0;
    v11 = CArray<ATL::CComPtr<CDIProperties<ID2D1Properties>>,CPropertyNodePtrTraits,CDefaultAllocator>::Resize(v9, 7);
    if ( v11 < 0 )
      break;
    v12 = v28[8 * v6];
    v13 = v12;
    LODWORD(v13) = v12 & 0x7FFFFFFF;
    v11 = CArray<ATL::CComPtr<CDIProperties<ID2D1Properties>>,CPropertyNodePtrTraits,CDefaultAllocator>::SetAt<ATL::CComPtr<CDIProperties<ID2D1Properties>>>(
            v10,
            0,
            *((_QWORD *)this + 4) + 8 * v13);
    if ( v11 < 0 )
      break;
    v14 = CArray<ATL::CComPtr<CDIProperties<ID2D1Properties>>,CPropertyNodePtrTraits,CDefaultAllocator>::SetAt<ATL::CComPtr<CDIProperties<ID2D1Properties>>>(
            v10,
            1,
            *(_QWORD *)this + 8LL);
    v11 = v14;
    if ( v14 < 0 )
    {
      DoStackCapture(v14);
      if ( *v10 )
      {
        for ( i = 0; i < *((_DWORD *)v10 + 2); ++i )
          ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>((void *)(*v10 + 8LL * i));
LABEL_23:
        free((void *)*v10);
        *v10 = 0;
        *((_DWORD *)v10 + 3) = 0;
      }
LABEL_24:
      *((_DWORD *)v10 + 2) = 0;
      goto LABEL_27;
    }
    if ( v12 == -2147483641 )
    {
      v18 = CArray<ATL::CComPtr<CDIProperties<ID2D1Properties>>,CPropertyNodePtrTraits,CDefaultAllocator>::SetAt<ATL::CComPtr<CDIProperties<ID2D1Properties>>>(
              v10,
              5,
              *(_QWORD *)this);
      v11 = v18;
      if ( v18 < 0 )
      {
        DoStackCapture(v18);
        if ( *v10 )
        {
          for ( j = 0; j < *((_DWORD *)v10 + 2); ++j )
            ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>((void *)(*v10 + 8LL * j));
          goto LABEL_23;
        }
        goto LABEL_24;
      }
    }
    v15 = (void (__fastcall **)(_QWORD *))*v8;
    v25 = 0;
    v26 = v10;
    v27 = v8;
    (*v15)(v8);
    v5 = CreateComObjectInit<LockingRequired,CDIProperties<ID2D1Properties>,AbstractLock *,CRefCountPtr<RefCountedObject<CPropertyDescription,LockingRequired,DeleteOnZeroReference>>,CAutoPtr<CPropertyNodeArray>,unsigned int,bool,IUnknown *,IUnknown *,bool>(
           *((_QWORD *)this + 3),
           (unsigned int)&v27,
           (unsigned int)&v26,
           v16,
           v21,
           v22,
           v23,
           v24,
           (__int64)&v25);
    if ( v5 < 0
      || (v5 = CArray<ATL::CComPtr<CDIProperties<ID2D1Properties>>,CPropertyNodePtrTraits,CDefaultAllocator>::SetAt<ATL::CComPtr<CDIProperties<ID2D1Properties>>>(
                 a3,
                 v12 & 0x7FFFFFFF,
                 &v25),
          v5 < 0) )
    {
      DoStackCapture(v5);
      ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(&v25);
      goto LABEL_17;
    }
    if ( v25 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    (*(void (__fastcall **)(_QWORD *))(*v8 + 8LL))(v8);
    ++v6;
  }
  DoStackCapture(v11);
  CArray<ATL::CComPtr<CMultistepScaler>,CDefaultTraits<ATL::CComPtr<CMultistepScaler>>,CDefaultAllocator>::RemoveAll(v10);
LABEL_27:
  operator delete(v10);
  (*(void (__fastcall **)(_QWORD *))(*v8 + 8LL))(v8);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800adc28  mov     [rsp-8+arg_0], rbx
0x1800adc2d  push    rbp
0x1800adc2e  push    rsi
0x1800adc2f  push    rdi
0x1800adc30  push    r12
0x1800adc32  push    r13
0x1800adc34  push    r14
0x1800adc36  push    r15
0x1800adc38  lea     rbp, [rsp-10h]
0x1800adc3d  sub     rsp, 110h
0x1800adc44  xor     r14d, r14d
0x1800adc47  mov     [rbp+40h+var_C0], rdx
0x1800adc4b  lea     rax, aClsid_0; "CLSID"
0x1800adc52  mov     [rbp+40h+arg_8], r14d
0x1800adc56  mov     [rsp+140h+var_C8], rax
0x1800adc5b  mov     r12, rcx
0x1800adc5e  lea     rax, aCached; "Cached"
0x1800adc65  mov     [rbp+40h+arg_18], r14d
0x1800adc69  mov     [rbp+40h+var_A8], rax
0x1800adc6d  lea     edx, [r14+4]
0x1800adc71  lea     rax, [rbp+40h+arg_8]
0x1800adc75  mov     [rsp+140h+var_D0], 80000000h
0x1800adc7d  mov     [rbp+40h+var_A0], rax
0x1800adc81  lea     ecx, [rdx-1]
0x1800adc84  lea     rax, aPrecision; "Precision"
0x1800adc8b  mov     [rbp+40h+var_B8], 10h
0x1800adc92  mov     [rbp+40h+var_88], rax
0x1800adc96  mov     r13, r8
0x1800adc99  lea     rax, [rbp+40h+arg_18]
0x1800adc9d  mov     [rbp+40h+var_B4], 0Dh
0x1800adca4  mov     [rbp+40h+var_80], rax
0x1800adca8  mov     ebx, r14d
0x1800adcab  lea     rax, aMininputs; "MinInputs"
0x1800adcb2  mov     [rbp+40h+var_B0], 80000006h
0x1800adcb9  mov     [rbp+40h+var_68], rax
0x1800adcbd  mov     r15d, r14d
0x1800adcc0  lea     rax, [rbp+40h+arg_8]
0x1800adcc4  mov     [rbp+40h+var_98], edx
0x1800adcc7  mov     [rbp+40h+var_60], rax
0x1800adccb  lea     rax, aMaxinputs; "MaxInputs"
0x1800adcd2  mov     [rbp+40h+var_48], rax
0x1800adcd6  lea     rax, [rbp+40h+arg_8]
0x1800adcda  mov     [rbp+40h+var_40], rax
0x1800adcde  mov     [rbp+40h+var_94], 2
0x1800adce5  mov     [rbp+40h+var_90], 80000007h
0x1800adcec  mov     [rbp+40h+var_78], edx
0x1800adcef  mov     [rbp+40h+var_74], 0Bh
0x1800adcf6  mov     [rbp+40h+var_70], 80000008h
0x1800adcfd  mov     [rbp+40h+var_58], edx
0x1800add00  mov     [rbp+40h+var_54], ecx
0x1800add03  mov     [rbp+40h+var_50], 80000009h
0x1800add0a  mov     [rbp+40h+var_38], edx
0x1800add0d  mov     [rbp+40h+var_34], ecx
0x1800add10  cmp     r15d, 5
0x1800add14  jnb     loc_1800ADED5
0x1800add1a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800add21  mov     ecx, 50h ; 'P'; unsigned __int64
0x1800add26  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800add2b  mov     rdi, rax
0x1800add2e  test    rax, rax
0x1800add31  jz      loc_1800ADF51
0x1800add37  mov     [rax+8], r14
0x1800add3b  mov     rcx, rdi; this
0x1800add3e  mov     [rax+14h], r14b
0x1800add42  mov     [rax+18h], r14
0x1800add46  mov     qword ptr [rax+30h], 10h
0x1800add4e  mov     [rax+38h], r14
0x1800add52  mov     [rax+40h], r14
0x1800add56  lea     rax, ??_7?$RefCountedObject@VCPropertyDescription@@ULockingRequired@@UDeleteOnZeroReference@@@@6B@; const RefCountedObject<CPropertyDescription,LockingRequired,DeleteOnZeroReference>::`vftable'
0x1800add5d  mov     [rdi], rax
0x1800add60  mov     esi, r15d
0x1800add63  shl     rsi, 5
0x1800add67  mov     dword ptr [rdi+48h], 1
0x1800add6e  mov     eax, [rbp+rsi+40h+var_B4]
0x1800add72  mov     r9d, [rbp+rsi+40h+var_B8]; unsigned int
0x1800add77  mov     r8, [rbp+rsi+40h+var_C0]; unsigned __int8 *
0x1800add7c  mov     rdx, [rsp+rsi+140h+var_C8]; unsigned __int16 *
0x1800add81  mov     [rsp+140h+var_120], eax; enum D2D1_PROPERTY_TYPE
0x1800add85  call    ?Initialize@CPropertyDescription@@QEAAJPEBGPEBEIW4D2D1_PROPERTY_TYPE@@@Z; CPropertyDescription::Initialize(ushort const *,uchar const *,uint,D2D1_PROPERTY_TYPE)
0x1800add8a  mov     ebx, eax
0x1800add8c  test    eax, eax
0x1800add8e  js      loc_1800ADEBF
0x1800add94  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800add9b  mov     ecx, 18h; unsigned __int64
0x1800adda0  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800adda5  mov     rbx, rax
0x1800adda8  test    rax, rax
0x1800addab  jz      loc_1800ADEBA
0x1800addb1  mov     edx, 7
0x1800addb6  mov     [rax], r14
0x1800addb9  mov     rcx, rax
0x1800addbc  mov     qword ptr [rax+8], 0
0x1800addc4  call    ?Resize@?$CArray@V?$CComPtr@V?$CDIProperties@UID2D1Properties@@@@@ATL@@VCPropertyNodePtrTraits@@VCDefaultAllocator@@@@QEAAJI@Z; CArray<ATL::CComPtr<CDIProperties<ID2D1Properties>>,CPropertyNodePtrTraits,CDefaultAllocator>::Resize(uint)
0x1800addc9  mov     r14d, eax
0x1800addcc  test    eax, eax
0x1800addce  js      loc_1800ADF62
0x1800addd4  mov     rax, [r12+20h]
0x1800addd9  xor     edx, edx
0x1800adddb  mov     esi, [rsp+rsi+140h+var_D0]
0x1800adddf  mov     ecx, esi
0x1800adde1  btr     ecx, 1Fh
0x1800adde5  lea     r8, [rax+rcx*8]
0x1800adde9  mov     rcx, rbx
0x1800addec  call    ??$SetAt@V?$CComPtr@V?$CDIProperties@UID2D1Properties@@@@@ATL@@@?$CArray@V?$CComPtr@V?$CDIProperties@UID2D1Properties@@@@@ATL@@VCPropertyNodePtrTraits@@VCDefaultAllocator@@@@QEAAJIAEBV?$CComPtr@V?$CDIProperties@UID2D1Properties@@@@@ATL@@@Z; CArray<ATL::CComPtr<CDIProperties<ID2D1Properties>>,CPropertyNodePtrTraits,CDefaultAllocator>::SetAt<ATL::CComPtr<CDIProperties<ID2D1Properties>>>(uint,ATL::CComPtr<CDIProperties<ID2D1Properties>> const &)
0x1800addf1  mov     r14d, eax
0x1800addf4  test    eax, eax
0x1800addf6  js      loc_1800ADF62
0x1800addfc  mov     r8, [r12]
0x1800ade00  mov     edx, 1
0x1800ade05  add     r8, 8
0x1800ade09  mov     rcx, rbx
0x1800ade0c  call    ??$SetAt@V?$CComPtr@V?$CDIProperties@UID2D1Properties@@@@@ATL@@@?$CArray@V?$CComPtr@V?$CDIProperties@UID2D1Properties@@@@@ATL@@VCPropertyNodePtrTraits@@VCDefaultAllocator@@@@QEAAJIAEBV?$CComPtr@V?$CDIProperties@UID2D1Properties@@@@@ATL@@@Z; CArray<ATL::CComPtr<CDIProperties<ID2D1Properties>>,CPropertyNodePtrTraits,CDefaultAllocator>::SetAt<ATL::CComPtr<CDIProperties<ID2D1Properties>>>(uint,ATL::CComPtr<CDIProperties<ID2D1Properties>> const &)
0x1800ade11  mov     r14d, eax
0x1800ade14  test    eax, eax
0x1800ade16  js      loc_1800ADFAC
0x1800ade1c  cmp     esi, 80000007h
0x1800ade22  jz      loc_1800ADEF2
0x1800ade28  mov     rax, [rdi]
0x1800ade2b  xor     r14d, r14d
0x1800ade2e  mov     rcx, rdi
0x1800ade31  mov     [rsp+140h+var_F0], r14
0x1800ade36  mov     [rsp+140h+var_E8], rbx
0x1800ade3b  mov     [rsp+140h+var_E0], rdi
0x1800ade40  mov     rax, [rax]
0x1800ade43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ade48  mov     rcx, [r12+18h]
0x1800ade4d  lea     rax, [rsp+140h+var_F0]
0x1800ade52  lea     r8, [rsp+140h+var_E8]
0x1800ade57  mov     [rsp+140h+var_100], rax
0x1800ade5c  lea     rdx, [rsp+140h+var_E0]
0x1800ade61  call    ??$CreateComObjectInit@ULockingRequired@@V?$CDIProperties@UID2D1Properties@@@@PEAVAbstractLock@@V?$CRefCountPtr@V?$RefCountedObject@VCPropertyDescription@@ULockingRequired@@UDeleteOnZeroReference@@@@@@V?$CAutoPtr@VCPropertyNodeArray@@@@I_NPEAUIUnknown@@PEAU6@_N@@YAJPEAVAbstractLock@@V?$CRefCountPtr@V?$RefCountedObject@VCPropertyDescription@@ULockingRequired@@UDeleteOnZeroReference@@@@@@V?$CAutoPtr@VCPropertyNodeArray@@@@I_NPEAUIUnknown@@43PEAPEAV?$CDIProperties@UID2D1Properties@@@@@Z; CreateComObjectInit<LockingRequired,CDIProperties<ID2D1Properties>,AbstractLock *,CRefCountPtr<RefCountedObject<CPropertyDescription,LockingRequired,DeleteOnZeroReference>>,CAutoPtr<CPropertyNodeArray>,uint,bool,IUnknown *,IUnknown *,bool>(AbstractLock *,CRefCountPtr<RefCountedObject<CPropertyDescription,LockingRequired,DeleteOnZeroReference>>,CAutoPtr<CPropertyNodeArray>,uint,bool,IUnknown *,IUnknown *,bool,CDIProperties<ID2D1Properties> * *)
0x1800ade66  mov     ebx, eax
0x1800ade68  test    eax, eax
0x1800ade6a  js      loc_1800ADF96
0x1800ade70  btr     esi, 1Fh
0x1800ade74  lea     r8, [rsp+140h+var_F0]
0x1800ade79  mov     edx, esi
0x1800ade7b  mov     rcx, r13
0x1800ade7e  call    ??$SetAt@V?$CComPtr@V?$CDIProperties@UID2D1Properties@@@@@ATL@@@?$CArray@V?$CComPtr@V?$CDIProperties@UID2D1Properties@@@@@ATL@@VCPropertyNodePtrTraits@@VCDefaultAllocator@@@@QEAAJIAEBV?$CComPtr@V?$CDIProperties@UID2D1Properties@@@@@ATL@@@Z; CArray<ATL::CComPtr<CDIProperties<ID2D1Properties>>,CPropertyNodePtrTraits,CDefaultAllocator>::SetAt<ATL::CComPtr<CDIProperties<ID2D1Properties>>>(uint,ATL::CComPtr<CDIProperties<ID2D1Properties>> const &)
0x1800ade83  mov     ebx, eax
0x1800ade85  test    eax, eax
0x1800ade87  js      loc_1800ADF96
0x1800ade8d  mov     rcx, [rsp+140h+var_F0]
0x1800ade92  test    rcx, rcx
0x1800ade95  jz      short loc_1800ADEA3
0x1800ade97  mov     rax, [rcx]
0x1800ade9a  mov     rax, [rax+10h]
0x1800ade9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800adea3  mov     rax, [rdi]
0x1800adea6  mov     rcx, rdi
0x1800adea9  mov     rax, [rax+8]
0x1800adead  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800adeb2  inc     r15d
0x1800adeb5  jmp     loc_1800ADD10
0x1800adeba  mov     ebx, 8007000Eh
0x1800adebf  mov     ecx, ebx; int
0x1800adec1  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800adec6  mov     rax, [rdi]
0x1800adec9  mov     rcx, rdi
0x1800adecc  mov     rax, [rax+8]
0x1800aded0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aded5  mov     eax, ebx
0x1800aded7  mov     rbx, [rsp+140h+arg_0]
0x1800adedf  add     rsp, 110h
0x1800adee6  pop     r15
0x1800adee8  pop     r14
0x1800adeea  pop     r13
0x1800adeec  pop     r12
0x1800adeee  pop     rdi
0x1800adeef  pop     rsi
0x1800adef0  pop     rbp
0x1800adef1  retn
0x1800adef2  mov     r8, [r12]
0x1800adef6  mov     edx, 5
0x1800adefb  mov     rcx, rbx
0x1800adefe  call    ??$SetAt@V?$CComPtr@V?$CDIProperties@UID2D1Properties@@@@@ATL@@@?$CArray@V?$CComPtr@V?$CDIProperties@UID2D1Properties@@@@@ATL@@VCPropertyNodePtrTraits@@VCDefaultAllocator@@@@QEAAJIAEBV?$CComPtr@V?$CDIProperties@UID2D1Properties@@@@@ATL@@@Z; CArray<ATL::CComPtr<CDIProperties<ID2D1Properties>>,CPropertyNodePtrTraits,CDefaultAllocator>::SetAt<ATL::CComPtr<CDIProperties<ID2D1Properties>>>(uint,ATL::CComPtr<CDIProperties<ID2D1Properties>> const &)
0x1800adf03  mov     r14d, eax
0x1800adf06  test    eax, eax
0x1800adf08  jns     loc_1800ADE28
0x1800adf0e  mov     ecx, eax; int
0x1800adf10  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800adf15  xor     r15d, r15d
0x1800adf18  cmp     [rbx], r15
0x1800adf1b  jz      short loc_1800ADF4B
0x1800adf1d  mov     esi, r15d
0x1800adf20  cmp     [rbx+8], r15d
0x1800adf24  jbe     short loc_1800ADF3B
0x1800adf26  mov     rax, [rbx]
0x1800adf29  mov     ecx, esi
0x1800adf2b  lea     rcx, [rax+rcx*8]; void *
0x1800adf2f  call    ??1?$CComPtr@UIWICBitmap@@@ATL@@QEAA@XZ; ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(void)
0x1800adf34  inc     esi
0x1800adf36  cmp     esi, [rbx+8]
0x1800adf39  jb      short loc_1800ADF26
0x1800adf3b  mov     rcx, [rbx]; Block
0x1800adf3e  call    cs:__imp_free
0x1800adf44  mov     [rbx], r15
0x1800adf47  mov     [rbx+0Ch], r15d
0x1800adf4b  mov     [rbx+8], r15d
0x1800adf4f  jmp     short loc_1800ADF72
0x1800adf51  mov     ebx, 8007000Eh
0x1800adf56  mov     ecx, ebx; int
0x1800adf58  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800adf5d  jmp     loc_1800ADED5
0x1800adf62  mov     ecx, r14d; int
0x1800adf65  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800adf6a  mov     rcx, rbx
0x1800adf6d  call    ?RemoveAll@?$CArray@V?$CComPtr@VCMultistepScaler@@@ATL@@V?$CDefaultTraits@V?$CComPtr@VCMultistepScaler@@@ATL@@@@VCDefaultAllocator@@@@QEAAX_N@Z; CArray<ATL::CComPtr<CMultistepScaler>,CDefaultTraits<ATL::CComPtr<CMultistepScaler>>,CDefaultAllocator>::RemoveAll(bool)
0x1800adf72  mov     edx, 18h
0x1800adf77  mov     rcx, rbx; Block
0x1800adf7a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800adf7f  mov     rax, [rdi]
0x1800adf82  mov     rcx, rdi
0x1800adf85  mov     rax, [rax+8]
0x1800adf89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800adf8e  mov     eax, r14d
0x1800adf91  jmp     loc_1800ADED7
0x1800adf96  mov     ecx, ebx; int
0x1800adf98  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800adf9d  lea     rcx, [rsp+140h+var_F0]; void *
0x1800adfa2  call    ??1?$CComPtr@UIWICBitmap@@@ATL@@QEAA@XZ; ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(void)
0x1800adfa7  jmp     loc_1800ADEC6
0x1800adfac  mov     ecx, r14d; int
0x1800adfaf  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800adfb4  xor     r15d, r15d
0x1800adfb7  cmp     [rbx], r15
0x1800adfba  jz      short loc_1800ADF4B
0x1800adfbc  mov     esi, r15d
0x1800adfbf  cmp     [rbx+8], r15d
0x1800adfc3  jbe     loc_1800ADF3B
0x1800adfc9  mov     rax, [rbx]
0x1800adfcc  mov     ecx, esi
0x1800adfce  lea     rcx, [rax+rcx*8]; void *
0x1800adfd2  call    ??1?$CComPtr@UIWICBitmap@@@ATL@@QEAA@XZ; ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(void)
0x1800adfd7  inc     esi
0x1800adfd9  cmp     esi, [rbx+8]
0x1800adfdc  jb      short loc_1800ADFC9
0x1800adfde  jmp     loc_1800ADF3B
```
