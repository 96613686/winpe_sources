# SAXReader::parse(tagVARIANT)

- ea: `0x180036290`
- end: `0x1800368ab`
- name: `?parse@SAXReader@@UEAAJUtagVARIANT@@@Z`
- size: `1563`
- prototype: `__int64 __fastcall(SAXReader *__hidden this, struct tagVARIANT *__struct_ptr)`
- caller_count: `0`
- callee_count: `14`
- tags: ``

## callees

- `0x18001c310`
- `0x18001da4c`
- `0x18002d7e0`
- `0x180036290`
- `0x1800368b4`
- `0x180041660`
- `0x18004b488`
- `0x180051abc`
- `0x180051f20`
- `0x18005f9b8`
- `0x180064034`
- `0x180089290`
- `0x1800f66d4`
- `0x180107010`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x180036743`
- `msvcrt!_resetstkoflw` at `0x180036743`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180036451`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180036451`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180036796`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180036796`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180036731`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800367c2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180036731`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800367c2`
- `OLEAUT32!__imp_SysStringLen` at `0x180036691`
- `OLEAUT32!__imp_SysStringLen` at `0x180036691`
- `OLEAUT32!__imp_VariantClear` at `0x18003684d`
- `OLEAUT32!__imp_VariantClear` at `0x18003684d`

## pseudocode

```c
__int64 __fastcall SAXReader::parse(SAXReader *this, struct tagVARIANT *a2)
{
  unsigned __int64 v4; // rax
  __int64 v6; // rbx
  int v7; // edi
  struct tagVARIANT *pvarVal; // r14
  int v9; // eax
  unsigned int v10; // r13d
  unsigned __int16 BaseType; // ax
  BSTR *pbstrVal; // rax
  char *i; // rcx
  __int64 v14; // r9
  struct tagVARIANT *BaseVariant; // rax
  BSTR v16; // rax
  int v17; // r12d
  MemoryStreamForStrings *v18; // rax
  MemoryStreamForStrings *v19; // r14
  BSTR v20; // rax
  SAFEARRAY **pparray; // rax
  struct tagVARIANT *v22; // rax
  __int64 v23; // r9
  int (__fastcall ***llVal)(_QWORD, _QWORD, _QWORD); // r12
  int (__fastcall ****v25)(_QWORD, _QWORD, _QWORD); // rax
  unsigned __int16 v26; // ax
  __int16 v27; // r9
  __int64 v28; // rdi
  UINT v29; // eax
  int v30; // eax
  unsigned __int64 v31; // rcx
  __int64 v32; // [rsp+28h] [rbp-60h] BYREF
  int (__fastcall ***v33)(_QWORD, _QWORD, _QWORD); // [rsp+30h] [rbp-58h]
  BSTR v34; // [rsp+38h] [rbp-50h]
  char *v35; // [rsp+40h] [rbp-48h]
  BSTR v36; // [rsp+48h] [rbp-40h]
  struct IStream *v37; // [rsp+A0h] [rbp+18h] BYREF
  __int64 v38; // [rsp+A8h] [rbp+20h] BYREF

  v4 = (__int64)g_pfnEntry();
  v38 = v4;
  if ( !v4
    || (v6 = v4 | (3LL - (*(_DWORD *)(v4 + 76) != 0)),
        v38 = v6,
        *(_DWORD *)(v4 + 76) = 0,
        v7 = -2147024809,
        v37 = 0,
        v32 = 0,
        (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 15) + 200LL))(*((_QWORD *)this + 15))) )
  {
    ModelInit::~ModelInit((ModelInit *)&v38);
    return 2147500037LL;
  }
  pvarVal = (struct tagVARIANT *)((char *)this + 232);
  if ( *((_WORD *)this + 116) )
  {
    if ( a2->vt > 1u && a2->vt != 10 )
    {
      ModelInit::~ModelInit((ModelInit *)&v38);
      return 2147942487LL;
    }
  }
  else
  {
    pvarVal = a2;
  }
  v9 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 15) + 96LL))(*((_QWORD *)this + 15));
  v10 = v9 & 0xFFFFF7FF;
  if ( *((_BYTE *)this + 225) )
  {
    v10 = v9 & 0xFFEFF7FF | 0x100000;
    *(_BYTE *)(*((_QWORD *)this + 18) + 122LL) = 1;
  }
  BaseType = Variant::getBaseType(pvarVal);
  if ( BaseType == 8 )
  {
    if ( (Variant::getBaseVariant(pvarVal)->vt & 0x4000) != 0 )
    {
      pbstrVal = Variant::getBaseVariant(pvarVal)->pbstrVal;
    }
    else
    {
      BaseVariant = Variant::getBaseVariant(pvarVal);
      pbstrVal = (BSTR *)((char *)BaseVariant + v14);
    }
    v16 = *pbstrVal;
    v36 = v16;
    v34 = v16;
    v17 = 0;
    v35 = 0;
    if ( v16 )
    {
      for ( i = 0; (unsigned __int64)i < 0x7FFFFFFF && *v16; ++i )
      {
        v34 = ++v16;
        v17 = (_DWORD)i + 1;
        v35 = i + 1;
      }
    }
    if ( g_fUseMpHeap )
      v18 = (MemoryStreamForStrings *)MpHeapAlloc(i, v14, 0x40u);
    else
      v18 = (MemoryStreamForStrings *)HeapAlloc(g_hProcessHeap, v14, 0x40u);
    if ( v18 )
    {
      v19 = MemoryStreamForStrings::MemoryStreamForStrings(v18);
    }
    else
    {
      failure_tracing::record();
      v19 = 0;
    }
    if ( v19 )
    {
      v7 = 0;
      *((_BYTE *)v19 + 56) = 1;
      MemoryStream::reset(v19);
      v20 = v36;
      *((_QWORD *)v19 + 3) = v36;
      *((_QWORD *)v19 + 4) = v20;
      *((_QWORD *)v19 + 5) = 2LL * v17;
      *((_BYTE *)v19 + 48) = 0;
    }
    else
    {
      v7 = -2147024882;
    }
    v37 = v19;
    if ( v7 < 0 )
      goto LABEL_66;
    v7 = (*(__int64 (__fastcall **)(_QWORD, MemoryStreamForStrings *))(**((_QWORD **)this + 15) + 128LL))(
           *((_QWORD *)this + 15),
           v19);
    if ( v7 < 0 )
      goto LABEL_66;
    v10 |= 0x800u;
    goto LABEL_60;
  }
  if ( BaseType == 8209 )
  {
    if ( (Variant::getBaseVariant(pvarVal)->vt & 0x4000) != 0 )
    {
      pparray = Variant::getBaseVariant(pvarVal)->pparray;
    }
    else
    {
      v22 = Variant::getBaseVariant(pvarVal);
      pparray = (SAFEARRAY **)((char *)v22 + v23);
    }
    v7 = DocStream::New(*pparray, &v37);
    if ( v7 < 0 )
      goto LABEL_66;
    v7 = (*(__int64 (__fastcall **)(_QWORD, struct IStream *))(**((_QWORD **)this + 15) + 128LL))(
           *((_QWORD *)this + 15),
           v37);
    if ( v7 < 0 )
      goto LABEL_66;
LABEL_60:
    if ( v7 >= 0 )
    {
      v26 = Variant::getBaseType((struct tagVARIANT *)((char *)this + 256));
      if ( v26 == v27 )
      {
        v28 = *((_QWORD *)this + 15);
        v29 = SysStringLen(*((BSTR *)this + 33));
        EncodingStream::SetCharset(
          *(EncodingStream **)(*(_QWORD *)(v28 + 144) + 16LL),
          *((const unsigned __int16 **)this + 33),
          v29);
      }
      v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 15) + 24LL))(
             *((_QWORD *)this + 15),
             *((_QWORD *)this + 18));
      if ( v7 >= 0 )
      {
        v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 15) + 224LL))(*((_QWORD *)this + 15), v10);
        if ( v7 >= 0 )
        {
          *((_BYTE *)this + 224) = 1;
          v7 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 15) + 192LL))(
                 *((_QWORD *)this + 15),
                 0xFFFFFFFFLL);
        }
      }
    }
    goto LABEL_66;
  }
  llVal = 0;
  v33 = 0;
  while ( pvarVal && pvarVal->vt && pvarVal->vt != 1 )
  {
    switch ( pvarVal->vt )
    {
      case 9u:
        goto LABEL_52;
      case 0xAu:
        goto LABEL_54;
      case 0xDu:
LABEL_52:
        llVal = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))pvarVal->llVal;
        goto LABEL_53;
      case 0x4009u:
        goto LABEL_49;
    }
    if ( pvarVal->vt != 16396 )
    {
      if ( pvarVal->vt != 16397 )
        break;
LABEL_49:
      v25 = (int (__fastcall ****)(_QWORD, _QWORD, _QWORD))pvarVal->llVal;
      if ( !v25 )
        break;
      llVal = *v25;
LABEL_53:
      v33 = llVal;
      break;
    }
    pvarVal = pvarVal->pvarVal;
  }
LABEL_54:
  if ( !llVal )
    goto LABEL_60;
  if ( (**llVal)(llVal, &IID_IStream, &v37) < 0 )
  {
    if ( (**llVal)(llVal, &IID_ISequentialStream, &v32) < 0 )
      goto LABEL_60;
    v7 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 15) + 128LL))(*((_QWORD *)this + 15), v32);
    if ( v7 >= 0 )
      goto LABEL_60;
  }
  else
  {
    v7 = (*(__int64 (__fastcall **)(_QWORD, struct IStream *))(**((_QWORD **)this + 15) + 128LL))(
           *((_QWORD *)this + 15),
           v37);
    if ( v7 >= 0 )
      goto LABEL_60;
  }
LABEL_66:
  if ( v37 )
  {
    (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v37 + 16LL))(v37);
    v37 = 0;
  }
  if ( v32 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    v32 = 0;
  }
  *((_BYTE *)this + 224) = 0;
  if ( *((_WORD *)this + 116) )
    VariantClear((VARIANTARG *)((char *)this + 232));
  if ( (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 15) + 200LL))(*((_QWORD *)this + 15)) != 5 )
  {
    v30 = SAXReader::reset(this);
    if ( v30 < 0 && !v7 )
      v7 = v30;
  }
  v31 = v6 & 0xFFFFFFFFFFFFFFFCuLL;
  if ( (v6 & 0xFFFFFFFFFFFFFFFCuLL) != 0 )
  {
    *(_DWORD *)(v31 + 76) = (v6 & 1) == 0;
    ((void (__fastcall *)(unsigned __int64))g_pfnExit)(v31);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180036290  mov     [rsp+arg_0], rcx
0x180036295  push    rbx
0x180036296  push    rsi
0x180036297  push    rdi
0x180036298  push    r12
0x18003629a  push    r13
0x18003629c  push    r14
0x18003629e  push    r15
0x1800362a0  sub     rsp, 50h
0x1800362a4  mov     r12, rdx
0x1800362a7  mov     r15, rcx
0x1800362aa  mov     rax, cs:?g_pfnEntry@@3P6APEAUTLSDATA@@XZEA; TLSDATA * (*g_pfnEntry)(void)
0x1800362b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800362b6  mov     rcx, rax
0x1800362b9  mov     [rsp+88h+arg_18], rax
0x1800362c1  xor     esi, esi
0x1800362c3  test    rax, rax
0x1800362c6  jnz     short loc_1800362DF
0x1800362c8  lea     rcx, [rsp+88h+arg_18]; this
0x1800362d0  call    ??1ModelInit@@QEAA@XZ; ModelInit::~ModelInit(void)
0x1800362d5  mov     eax, 80004005h
0x1800362da  jmp     loc_18003689B
0x1800362df  mov     eax, [rax+4Ch]
0x1800362e2  neg     eax
0x1800362e4  sbb     rbx, rbx
0x1800362e7  add     rbx, 3
0x1800362eb  or      rbx, rcx
0x1800362ee  mov     [rsp+88h+arg_18], rbx
0x1800362f6  mov     [rcx+4Ch], esi
0x1800362f9  mov     edi, 80070057h
0x1800362fe  mov     [rsp+88h+arg_10], rsi
0x180036306  mov     [rsp+88h+var_60], rsi
0x18003630b  mov     rcx, [r15+78h]
0x18003630f  mov     rax, [rcx]
0x180036312  mov     rax, [rax+0C8h]
0x180036319  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003631e  test    eax, eax
0x180036320  jz      short loc_180036339
0x180036322  lea     rcx, [rsp+88h+arg_18]; this
0x18003632a  call    ??1ModelInit@@QEAA@XZ; ModelInit::~ModelInit(void)
0x18003632f  mov     eax, 80004005h
0x180036334  jmp     loc_18003689B
0x180036339  lea     r14, [r15+0E8h]
0x180036340  cmp     [r14], si
0x180036344  jz      short loc_18003636E
0x180036346  mov     eax, 1
0x18003634b  cmp     [r12], ax
0x180036350  jbe     short loc_180036371
0x180036352  cmp     word ptr [r12], 0Ah
0x180036358  jz      short loc_180036371
0x18003635a  lea     rcx, [rsp+88h+arg_18]; this
0x180036362  call    ??1ModelInit@@QEAA@XZ; ModelInit::~ModelInit(void)
0x180036367  mov     eax, edi
0x180036369  jmp     loc_18003689B
0x18003636e  mov     r14, r12
0x180036371  mov     rcx, [r15+78h]
0x180036375  mov     rax, [rcx]
0x180036378  mov     rax, [rax+60h]
0x18003637c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036381  mov     r13d, eax
0x180036384  mov     [rsp+88h+var_64], eax
0x180036388  btr     r13d, 0Bh
0x18003638d  mov     [rsp+88h+var_64], r13d
0x180036392  cmp     [r15+0E1h], sil
0x180036399  jz      short loc_1800363B0
0x18003639b  bts     r13d, 14h
0x1800363a0  mov     [rsp+88h+var_64], r13d
0x1800363a5  mov     rcx, [r15+90h]
0x1800363ac  mov     byte ptr [rcx+7Ah], 1
0x1800363b0  mov     rcx, r14; struct tagVARIANT *
0x1800363b3  call    ?getBaseType@Variant@@SAGPEAUtagVARIANT@@@Z; Variant::getBaseType(tagVARIANT *)
0x1800363b8  mov     r9d, 8
0x1800363be  cmp     ax, r9w
0x1800363c2  jnz     loc_1800364F6
0x1800363c8  mov     rcx, r14; struct tagVARIANT *
0x1800363cb  call    ?getBaseVariant@Variant@@SAPEAUtagVARIANT@@PEAU2@@Z; Variant::getBaseVariant(tagVARIANT *)
0x1800363d0  mov     ecx, 4000h
0x1800363d5  test    [rax], cx
0x1800363d8  mov     rcx, r14; struct tagVARIANT *
0x1800363db  jz      short loc_1800363E8
0x1800363dd  call    ?getBaseVariant@Variant@@SAPEAUtagVARIANT@@PEAU2@@Z; Variant::getBaseVariant(tagVARIANT *)
0x1800363e2  mov     rax, [rax+8]
0x1800363e6  jmp     short loc_1800363F0
0x1800363e8  call    ?getBaseVariant@Variant@@SAPEAUtagVARIANT@@PEAU2@@Z; Variant::getBaseVariant(tagVARIANT *)
0x1800363ed  add     rax, r9
0x1800363f0  mov     rax, [rax]
0x1800363f3  mov     [rsp+88h+var_40], rax
0x1800363f8  mov     [rsp+88h+var_50], rax
0x1800363fd  mov     r12, rsi
0x180036400  mov     [rsp+88h+var_48], rsi
0x180036405  test    rax, rax
0x180036408  jz      short loc_180036432
0x18003640a  mov     rcx, rsi
0x18003640d  cmp     rcx, 7FFFFFFFh
0x180036414  jnb     short loc_180036432
0x180036416  cmp     [rax], si
0x180036419  jz      short loc_180036432
0x18003641b  add     rax, 2
0x18003641f  mov     [rsp+88h+var_50], rax
0x180036424  lea     r12, [rcx+1]
0x180036428  mov     [rsp+88h+var_48], r12
0x18003642d  mov     rcx, r12
0x180036430  jmp     short loc_18003640D
0x180036432  mov     r8d, 40h ; '@'; unsigned __int64
0x180036438  mov     edx, r9d; unsigned int
0x18003643b  cmp     cs:g_fUseMpHeap, esi
0x180036441  jz      short loc_18003644A
0x180036443  call    ?MpHeapAlloc@@YAPEAXPEAXK_K@Z; MpHeapAlloc(void *,ulong,unsigned __int64)
0x180036448  jmp     short loc_180036457
0x18003644a  mov     rcx, cs:g_hProcessHeap; hHeap
0x180036451  call    cs:__imp_HeapAlloc
0x180036457  mov     rdi, rax
0x18003645a  test    rax, rax
0x18003645d  jnz     short loc_180036469
0x18003645f  call    ?record@failure_tracing@@SAXXZ; failure_tracing::record(void)
0x180036464  test    rdi, rdi
0x180036467  jz      short loc_180036476
0x180036469  mov     rcx, rdi; this
0x18003646c  call    ??0MemoryStreamForStrings@@QEAA@XZ; MemoryStreamForStrings::MemoryStreamForStrings(void)
0x180036471  mov     r14, rax
0x180036474  jmp     short loc_180036479
0x180036476  mov     r14, rsi
0x180036479  test    r14, r14
0x18003647c  jz      short loc_1800364AA
0x18003647e  mov     edi, esi
0x180036480  mov     byte ptr [r14+38h], 1
0x180036485  mov     rcx, r14; this
0x180036488  call    ?reset@MemoryStream@@QEAAXXZ; MemoryStream::reset(void)
0x18003648d  mov     rax, [rsp+88h+var_40]
0x180036492  mov     [r14+18h], rax
0x180036496  mov     [r14+20h], rax
0x18003649a  movsxd  rax, r12d
0x18003649d  add     rax, rax
0x1800364a0  mov     [r14+28h], rax
0x1800364a4  mov     [r14+30h], sil
0x1800364a8  jmp     short loc_1800364AF
0x1800364aa  mov     edi, 8007000Eh
0x1800364af  mov     [rsp+88h+arg_10], r14
0x1800364b7  mov     [rsp+88h+var_68], edi
0x1800364bb  test    edi, edi
0x1800364bd  js      loc_1800367FE
0x1800364c3  mov     rcx, [r15+78h]
0x1800364c7  mov     rax, [rcx]
0x1800364ca  mov     rdx, r14
0x1800364cd  mov     rax, [rax+80h]
0x1800364d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800364d9  mov     edi, eax
0x1800364db  mov     [rsp+88h+var_68], eax
0x1800364df  test    eax, eax
0x1800364e1  js      loc_1800367FE
0x1800364e7  bts     r13d, 0Bh
0x1800364ec  mov     [rsp+88h+var_64], r13d
0x1800364f1  jmp     loc_180036666
0x1800364f6  mov     ecx, 2011h
0x1800364fb  cmp     ax, cx
0x1800364fe  jnz     short loc_180036574
0x180036500  mov     rcx, r14; struct tagVARIANT *
0x180036503  call    ?getBaseVariant@Variant@@SAPEAUtagVARIANT@@PEAU2@@Z; Variant::getBaseVariant(tagVARIANT *)
0x180036508  mov     ecx, 4000h
0x18003650d  test    [rax], cx
0x180036510  mov     rcx, r14; struct tagVARIANT *
0x180036513  jz      short loc_180036520
0x180036515  call    ?getBaseVariant@Variant@@SAPEAUtagVARIANT@@PEAU2@@Z; Variant::getBaseVariant(tagVARIANT *)
0x18003651a  mov     rax, [rax+8]
0x18003651e  jmp     short loc_180036528
0x180036520  call    ?getBaseVariant@Variant@@SAPEAUtagVARIANT@@PEAU2@@Z; Variant::getBaseVariant(tagVARIANT *)
0x180036525  add     rax, r9
0x180036528  lea     rdx, [rsp+88h+arg_10]; struct IStream **
0x180036530  mov     rcx, [rax]; psa
0x180036533  call    ?New@DocStream@@SAJPEAUtagSAFEARRAY@@PEAPEAUIStream@@@Z; DocStream::New(tagSAFEARRAY *,IStream * *)
0x180036538  mov     edi, eax
0x18003653a  mov     [rsp+88h+var_68], eax
0x18003653e  test    eax, eax
0x180036540  js      loc_1800367FE
0x180036546  mov     rcx, [r15+78h]
0x18003654a  mov     rax, [rcx]
0x18003654d  mov     rdx, [rsp+88h+arg_10]
0x180036555  mov     rax, [rax+80h]
0x18003655c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036561  mov     edi, eax
0x180036563  mov     [rsp+88h+var_68], eax
0x180036567  test    eax, eax
0x180036569  jns     loc_180036666
0x18003656f  jmp     loc_1800367FE
0x180036574  mov     r12, rsi
0x180036577  mov     [rsp+88h+var_58], rsi
0x18003657c  test    r14, r14
0x18003657f  jz      short loc_1800365CC
0x180036581  movzx   ecx, word ptr [r14]
0x180036585  test    ecx, ecx
0x180036587  jz      short loc_1800365CC
0x180036589  sub     ecx, 1
0x18003658c  jz      short loc_1800365CC
0x18003658e  sub     ecx, r9d
0x180036591  jz      short loc_1800365C3
0x180036593  sub     ecx, 1
0x180036596  jz      short loc_1800365CC
0x180036598  sub     ecx, 3
0x18003659b  jz      short loc_1800365C3
0x18003659d  sub     ecx, 3FFCh
0x1800365a3  jz      short loc_1800365AF
0x1800365a5  sub     ecx, 3
0x1800365a8  jz      short loc_1800365BD
0x1800365aa  cmp     ecx, 1
0x1800365ad  jnz     short loc_1800365CC
0x1800365af  mov     rax, [r14+8]
0x1800365b3  test    rax, rax
0x1800365b6  jz      short loc_1800365CC
0x1800365b8  mov     r12, [rax]
0x1800365bb  jmp     short loc_1800365C7
0x1800365bd  mov     r14, [r14+8]
0x1800365c1  jmp     short loc_18003657C
0x1800365c3  mov     r12, [r14+8]
0x1800365c7  mov     [rsp+88h+var_58], r12
0x1800365cc  test    r12, r12
0x1800365cf  jz      loc_18003666C
0x1800365d5  mov     rax, [r12]
0x1800365d9  lea     r8, [rsp+88h+arg_10]
0x1800365e1  lea     rdx, IID_IStream
0x1800365e8  mov     rcx, r12
0x1800365eb  mov     rax, [rax]
0x1800365ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800365f3  test    eax, eax
0x1800365f5  js      short loc_180036621
0x1800365f7  mov     rcx, [r15+78h]
0x1800365fb  mov     rax, [rcx]
0x1800365fe  mov     rdx, [rsp+88h+arg_10]
0x180036606  mov     rax, [rax+80h]
0x18003660d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036612  mov     edi, eax
0x180036614  mov     [rsp+88h+var_68], eax
0x180036618  test    eax, eax
0x18003661a  jns     short loc_180036666
0x18003661c  jmp     loc_1800367FE
0x180036621  mov     rax, [r12]
0x180036625  lea     r8, [rsp+88h+var_60]
0x18003662a  lea     rdx, IID_ISequentialStream
0x180036631  mov     rcx, r12
0x180036634  mov     rax, [rax]
0x180036637  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003663c  test    eax, eax
0x18003663e  js      short loc_180036666
0x180036640  mov     rcx, [r15+78h]
0x180036644  mov     rax, [rcx]
0x180036647  mov     rdx, [rsp+88h+var_60]
0x18003664c  mov     rax, [rax+80h]
0x180036653  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036658  mov     edi, eax
0x18003665a  mov     [rsp+88h+var_68], eax
0x18003665e  test    eax, eax
0x180036660  js      loc_1800367FE
0x180036666  mov     r9d, 8
0x18003666c  test    edi, edi
0x18003666e  js      loc_180036726
0x180036674  lea     rcx, [r15+100h]; struct tagVARIANT *
0x18003667b  call    ?getBaseType@Variant@@SAGPEAUtagVARIANT@@@Z; Variant::getBaseType(tagVARIANT *)
0x180036680  cmp     ax, r9w
0x180036684  jnz     short loc_1800366B1
0x180036686  mov     rdi, [r15+78h]
0x18003668a  mov     rcx, [r15+108h]; pbstr
0x180036691  call    cs:__imp_SysStringLen
0x180036697  mov     rcx, [rdi+90h]
0x18003669e  mov     r8d, eax; int
0x1800366a1  mov     rdx, [r15+108h]; unsigned __int16 *
0x1800366a8  mov     rcx, [rcx+10h]; this
0x1800366ac  call    ?SetCharset@EncodingStream@@QEAAJPEBGH@Z; EncodingStream::SetCharset(ushort const *,int)
0x1800366b1  mov     rcx, [r15+78h]
0x1800366b5  mov     rax, [rcx]
0x1800366b8  mov     rdx, [r15+90h]
0x1800366bf  mov     rax, [rax+18h]
0x1800366c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800366c8  mov     edi, eax
0x1800366ca  mov     [rsp+88h+var_68], eax
0x1800366ce  test    eax, eax
0x1800366d0  js      loc_1800367FE
0x1800366d6  mov     rcx, [r15+78h]
0x1800366da  mov     rax, [rcx]
0x1800366dd  mov     edx, r13d
0x1800366e0  mov     rax, [rax+0E0h]
0x1800366e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800366ec  mov     edi, eax
0x1800366ee  mov     [rsp+88h+var_68], eax
0x1800366f2  test    eax, eax
0x1800366f4  js      loc_1800367FE
0x1800366fa  mov     byte ptr [r15+0E0h], 1
0x180036702  mov     rcx, [r15+78h]
0x180036706  mov     rax, [rcx]
0x180036709  or      edx, 0FFFFFFFFh
0x18003670c  mov     rax, [rax+0C0h]
0x180036713  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036718  mov     edi, eax
0x18003671a  mov     [rsp+88h+var_68], eax
0x18003671e  test    eax, eax
0x180036720  js      loc_1800367FE
0x180036726  jmp     loc_1800367FE
0x18003672b  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x180036731  call    cs:__imp_TlsGetValue
0x180036737  mov     rbx, rax
0x18003673a  cmp     dword ptr [rax+54h], 0C00000FDh
0x180036741  jnz     short loc_1800367BC
  ... truncated ...
```
