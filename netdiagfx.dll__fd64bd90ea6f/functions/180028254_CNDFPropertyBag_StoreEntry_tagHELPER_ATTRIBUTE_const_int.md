# CNDFPropertyBag::StoreEntry(tagHELPER_ATTRIBUTE const *,int)

- ea: `0x180028254`
- end: `0x18002872f`
- name: `?StoreEntry@CNDFPropertyBag@@AEAAJPEBUtagHELPER_ATTRIBUTE@@H@Z`
- size: `1243`
- prototype: `__int64 __fastcall(CNDFPropertyBag *__hidden this, const struct tagHELPER_ATTRIBUTE *, int)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800281e0`
- `0x180028220`

## callees

- `0x1800035a8`
- `0x180006d58`
- `0x180008ca8`
- `0x180009f54`
- `0x18000bda4`
- `0x18001006c`
- `0x180011af0`
- `0x1800264ec`
- `0x180027b80`
- `0x180027e18`
- `0x180028254`
- `0x18002c802`
- `0x18002c840`
- `0x18002f010`

## import_xrefs

- `KERNEL32!lstrcmpW` at `0x1800284c1`
- `KERNEL32!lstrcmpW` at `0x1800284c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800284fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800284fe`

## string_xrefs

- `0x1800283e4`: `Property Bag: '%s' was denied access to Request the already requested entry '%s'`
- `0x1800283b0`: `Property Bag: '%s' was denied access to overwrite writable entry '%s' because of a type mismatch. Original Type: %i, New Type: %i`
- `0x180028633`: `commited the requested`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CNDFPropertyBag::StoreEntry(CNDFPropertyBag *this, struct tagHELPER_ATTRIBUTE *a2, int a3)
{
  struct tagHELPER_ATTRIBUTE *v4; // r15
  CNDFPropertyBag *v5; // rsi
  int v6; // r14d
  int v7; // eax
  int v8; // edi
  __int64 v9; // r12
  _OWORD *v10; // rbx
  int v11; // r9d
  unsigned int v12; // r8d
  _DWORD *v13; // rax
  _OWORD *v14; // rdx
  _OWORD *i; // rax
  int v16; // edx
  __int64 **v17; // rax
  __int64 v18; // r9
  __int64 **v19; // rax
  __int64 v20; // r9
  __int64 v21; // rcx
  unsigned __int64 v22; // rbx
  unsigned int v23; // esi
  __int64 v24; // rax
  __int64 v25; // rax
  LPCWSTR ***v26; // r13
  LPCWSTR **v27; // rdi
  LPCWSTR **v28; // r14
  LPCWSTR **v29; // r15
  struct tagHELPER_ATTRIBUTE *v30; // rax
  struct tagHELPER_ATTRIBUTE *v31; // rdi
  LPCWSTR **v32; // rax
  LPCWSTR **v33; // rax
  LPCWSTR **v34; // rcx
  const wchar_t *v35; // rcx
  __int64 **v36; // rax
  __int64 v37; // r9
  int v38; // ebx
  __int64 *v39; // rcx
  __int64 v40; // rax
  int v42; // [rsp+40h] [rbp-C0h]
  struct tagHELPER_ATTRIBUTE *v43; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR **v44; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR **v45; // [rsp+58h] [rbp-A8h]
  LPCWSTR **v46; // [rsp+60h] [rbp-A0h]
  int v47; // [rsp+68h] [rbp-98h]
  __int128 v48; // [rsp+70h] [rbp-90h] BYREF
  __int64 v49; // [rsp+80h] [rbp-80h]
  struct tagHELPER_ATTRIBUTE *v50; // [rsp+88h] [rbp-78h] BYREF
  __int64 v51; // [rsp+90h] [rbp-70h]
  __int128 v52; // [rsp+98h] [rbp-68h] BYREF
  struct tagHELPER_ATTRIBUTE **v53; // [rsp+A8h] [rbp-58h]
  CNDFPropertyBag *v54; // [rsp+B0h] [rbp-50h]
  unsigned __int16 v55[264]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 v56[264]; // [rsp+2D0h] [rbp+1D0h] BYREF

  v47 = a3;
  v4 = a2;
  v43 = a2;
  v5 = this;
  v54 = this;
  v48 = 0;
  v49 = 0;
  v6 = 1;
  v42 = 1;
  v7 = CNDFPropertyBag::QueryEntry(this, a2->pwszName, &v48);
  v8 = v7;
  v9 = v48;
  if ( v7 >= 0 )
  {
    memset_0(v55, 0, 0x208u);
    v10 = (_OWORD *)*((_QWORD *)&v48 + 1);
    if ( *((_QWORD *)&v48 + 1) == v9 )
    {
      v42 = 1;
LABEL_31:
      *(_QWORD *)&v52 = 0;
      *((_QWORD *)&v52 + 1) = *((_QWORD *)v5 + 8);
      std::vector<PropertyBagEntry>::push_back(&v48, &v52);
      v10 = (_OWORD *)*((_QWORD *)&v48 + 1);
      v9 = v48;
LABEL_32:
      v22 = ((__int64)v10 - v9) >> 4;
      if ( v22 )
      {
        v23 = 0;
        v24 = 0;
        do
        {
          v25 = 2 * v24;
          v53 = *(struct tagHELPER_ATTRIBUTE ***)(v9 + 8 * v25);
          v26 = (LPCWSTR ***)(*(_QWORD *)(v9 + 8 * v25 + 8) + 104LL);
          std::vector<PropertyBagEntry>::vector<PropertyBagEntry>(&v44, (__int64)v26);
          v27 = v44;
          v28 = v45;
          while ( v27 != v28 )
          {
            v29 = v27 + 2;
            if ( !lstrcmpW(**v27, v43->pwszName) )
            {
              while ( v29 != v28 )
              {
                *(_OWORD *)v27 = *(_OWORD *)v29;
                v27 += 2;
                v29 += 2;
              }
              v28 -= 2;
              v45 = v28;
              break;
            }
            v27 += 2;
          }
          v52 = 0;
          v30 = (struct tagHELPER_ATTRIBUTE *)CoTaskMemAlloc(0x90u);
          v31 = v30;
          *(_QWORD *)&v52 = v30;
          if ( v30 )
          {
            memset_0(v30, 0, sizeof(struct tagHELPER_ATTRIBUTE));
            v50 = v31;
            v51 = 0x100000001LL;
            v4 = v43;
            v8 = CopyHelperAttribute(v31, v43);
            if ( v8 >= 0 )
            {
              DWORD2(v52) = v47;
              v50 = 0;
              v51 = 0;
              std::vector<PropertyBagEntry>::push_back(&v44, &v52);
              v28 = v45;
            }
            TNDFDeallocator<tagHELPER_ATTRIBUTE *,&void FreeHelperAttributes(tagHELPER_ATTRIBUTE *,unsigned long,int)>::~TNDFDeallocator<tagHELPER_ATTRIBUTE *,&void FreeHelperAttributes(tagHELPER_ATTRIBUTE *,unsigned long,int)>(&v50);
            if ( v8 >= 0 )
            {
              if ( v26 != &v44 )
              {
                v32 = *v26;
                *v26 = v44;
                v44 = v32;
                v33 = v26[1];
                v26[1] = v28;
                v45 = v33;
                v34 = v26[2];
                v26[2] = v46;
                v46 = v34;
              }
              if ( v53 && *v53 )
                FreeHelperAttributes(*v53, 1u, 1);
            }
          }
          else
          {
            v8 = -2147024882;
            v4 = v43;
          }
          std::vector<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> *,std::allocator<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> *>>::~vector<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> *,std::allocator<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> *>>((__int64)&v44);
          v24 = ++v23;
        }
        while ( v23 < v22 );
        v5 = v54;
        v6 = v42;
      }
      goto LABEL_53;
    }
    if ( *((_QWORD *)&v48 + 1) - v9 == 16 && *(_QWORD *)(v9 + 8) == *((_QWORD *)v5 + 8) )
    {
      v6 = 0;
      v42 = 0;
      goto LABEL_32;
    }
    v11 = 1;
    v12 = 0;
    while ( v12 < (unsigned __int64)(((__int64)v10 - v9) >> 4) )
    {
      _mm_lfence();
      v13 = *(_DWORD **)(v9 + 16LL * v12);
      if ( v13[2] )
      {
        if ( a3 )
        {
          v19 = (__int64 **)*((_QWORD *)v5 + 8);
          v20 = (*v19)[2];
          if ( !*(_DWORD *)(v20 - 16) )
            v20 = **v19;
          StringCchPrintfW(
            v55,
            0x104u,
            L"Property Bag: '%s' was denied access to Request the already requested entry '%s'",
            v20,
            v4->pwszName);
          goto LABEL_23;
        }
        v16 = *(_DWORD *)(*(_QWORD *)v13 + 8LL);
        if ( v16 != v4->type )
        {
          v17 = (__int64 **)*((_QWORD *)v5 + 8);
          v18 = (*v17)[2];
          if ( !*(_DWORD *)(v18 - 16) )
            v18 = **v17;
          StringCchPrintfW(
            v55,
            0x104u,
            L"Property Bag: '%s' was denied access to overwrite writable entry '%s' because of a type mismatch. Original T"
             "ype: %i, New Type: %i",
            v18,
            v4->pwszName,
            v16,
            v4->type);
LABEL_23:
          v21 = *((_QWORD *)v5 + 9);
          if ( v21 )
            (*(void (__fastcall **)(__int64, _QWORD, unsigned __int16 *))(*(_QWORD *)v21 + 96LL))(v21, 0, v55);
          v8 = -2147024891;
          goto LABEL_66;
        }
        ++v12;
      }
      else
      {
        v14 = (_OWORD *)(v9 + 16LL * v12);
        for ( i = v14 + 1; i != v10; ++i )
          *v14++ = *i;
        *((_QWORD *)&v48 + 1) = --v10;
        v11 = 0;
      }
    }
    if ( !v11 )
      goto LABEL_31;
    v6 = 0;
    v42 = 0;
LABEL_30:
    if ( !v6 )
      goto LABEL_32;
    goto LABEL_31;
  }
  if ( v7 == -2147024894 )
  {
    v10 = (_OWORD *)*((_QWORD *)&v48 + 1);
    goto LABEL_30;
  }
LABEL_53:
  if ( *((_QWORD *)v5 + 9) )
  {
    memset_0(v56, 0, 0x208u);
    if ( v8 < 0 )
    {
      v39 = (__int64 *)**((_QWORD **)v5 + 8);
      v40 = v39[2];
      if ( !*(_DWORD *)(v40 - 16) )
        v40 = *v39;
      v38 = StringCchPrintfW(
              v56,
              0x104u,
              L"Property Bag: Failed to add property bag entry '%s' requested by '%s'. HR:0x%x",
              v4->pwszName,
              v40,
              v8);
    }
    else
    {
      AttributeConverter::ToString(&v43, v4);
      v35 = L"added";
      if ( !v6 )
        v35 = L"commited the requested";
      v36 = (__int64 **)*((_QWORD *)v5 + 8);
      v37 = (*v36)[2];
      if ( !*(_DWORD *)(v37 - 16) )
        v37 = **v36;
      v38 = StringCchPrintfW(v56, 0x104u, L"Property Bag: '%s' %s property bag entry '%s'", v37, v35, v43);
      ATL::CStringData::Release((ATL::CStringData *)((char *)&v43[-1].OctetString + 104));
    }
    if ( (int)(v38 + 0x80000000) < 0 || v38 == -2147024774 )
      (*(void (__fastcall **)(_QWORD, _QWORD, unsigned __int16 *))(**((_QWORD **)v5 + 9) + 96LL))(
        *((_QWORD *)v5 + 9),
        0,
        v56);
  }
LABEL_66:
  std::vector<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> *,std::allocator<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> *>>::~vector<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> *,std::allocator<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> *>>((__int64)&v48);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180028254  mov     [rsp-8+arg_10], rbx
0x180028259  push    rbp
0x18002825a  push    rsi
0x18002825b  push    rdi
0x18002825c  push    r12
0x18002825e  push    r13
0x180028260  push    r14
0x180028262  push    r15
0x180028264  lea     rbp, [rsp-3F0h]
0x18002826c  sub     rsp, 4F0h
0x180028273  mov     rax, cs:__security_cookie
0x18002827a  xor     rax, rsp
0x18002827d  mov     [rbp+420h+var_40], rax
0x180028284  mov     r13d, r8d
0x180028287  mov     [rsp+520h+var_4B8], r8d
0x18002828c  mov     r15, rdx
0x18002828f  mov     [rsp+520h+var_4D8], rdx
0x180028294  mov     rsi, rcx
0x180028297  mov     [rbp+420h+var_470], rcx
0x18002829b  xorps   xmm0, xmm0
0x18002829e  movdqu  [rsp+520h+var_4B0], xmm0
0x1800282a4  mov     [rbp+420h+var_4A0], 0
0x1800282ac  mov     r14d, 1
0x1800282b2  mov     [rsp+520h+var_4E0], r14d
0x1800282b7  lea     r8, [rsp+520h+var_4B0]
0x1800282bc  mov     rdx, [rdx]
0x1800282bf  call    ?QueryEntry@CNDFPropertyBag@@AEAAJPEBGAEAV?$vector@UPropertyBagEntryItem@@V?$allocator@UPropertyBagEntryItem@@@std@@@std@@@Z; CNDFPropertyBag::QueryEntry(ushort const *,std::vector<PropertyBagEntryItem> &)
0x1800282c4  mov     edi, eax
0x1800282c6  mov     r12, qword ptr [rsp+520h+var_4B0]
0x1800282cb  test    eax, eax
0x1800282cd  js      loc_18002842D
0x1800282d3  xor     edx, edx; Val
0x1800282d5  mov     r8d, 208h; Size
0x1800282db  lea     rcx, [rbp+420h+var_460]; void *
0x1800282df  call    memset_0
0x1800282e4  mov     rbx, qword ptr [rsp+520h+var_4B0+8]
0x1800282e9  mov     rax, rbx
0x1800282ec  sub     rax, r12
0x1800282ef  jnz     short loc_1800282FB
0x1800282f1  mov     [rsp+520h+var_4E0], r14d
0x1800282f6  jmp     loc_180028442
0x1800282fb  cmp     rax, 10h
0x1800282ff  jnz     short loc_180028319
0x180028301  mov     rax, [rsi+40h]
0x180028305  cmp     [r12+8], rax
0x18002830a  jnz     short loc_180028319
0x18002830c  xor     r14d, r14d
0x18002830f  mov     [rsp+520h+var_4E0], r14d
0x180028314  jmp     loc_18002846A
0x180028319  mov     r9d, r14d
0x18002831c  xor     r8d, r8d
0x18002831f  mov     ecx, r8d
0x180028322  mov     rax, rbx
0x180028325  sub     rax, r12
0x180028328  sar     rax, 4
0x18002832c  cmp     rcx, rax
0x18002832f  jnb     loc_18002841E
0x180028335  lfence
0x180028338  add     rcx, rcx
0x18002833b  mov     rax, [r12+rcx*8]
0x18002833f  cmp     dword ptr [rax+8], 0
0x180028343  jnz     short loc_180028371
0x180028345  lea     rdx, [r12+rcx*8]
0x180028349  lea     rax, [rdx+10h]
0x18002834d  jmp     short loc_18002835E
0x18002834f  movups  xmm0, xmmword ptr [rax]
0x180028352  movdqu  xmmword ptr [rdx], xmm0
0x180028356  lea     rdx, [rdx+10h]
0x18002835a  add     rax, 10h
0x18002835e  cmp     rax, rbx
0x180028361  jnz     short loc_18002834F
0x180028363  sub     rbx, 10h
0x180028367  mov     qword ptr [rsp+520h+var_4B0+8], rbx
0x18002836c  xor     r9d, r9d
0x18002836f  jmp     short loc_18002831F
0x180028371  test    r13d, r13d
0x180028374  jnz     short loc_1800283C7
0x180028376  mov     rax, [rax]
0x180028379  mov     edx, [rax+8]
0x18002837c  mov     r10d, [r15+8]
0x180028380  cmp     edx, r10d
0x180028383  jnz     short loc_18002838A
0x180028385  inc     r8d
0x180028388  jmp     short loc_18002831F
0x18002838a  mov     r8, [r15]
0x18002838d  mov     rax, [rsi+40h]
0x180028391  mov     rcx, [rax]
0x180028394  mov     r9, [rcx+10h]
0x180028398  cmp     dword ptr [r9-10h], 0
0x18002839d  jnz     short loc_1800283A2
0x18002839f  mov     r9, [rcx]
0x1800283a2  mov     [rsp+520h+var_4F0], r10d
0x1800283a7  mov     dword ptr [rsp+520h+var_4F8], edx
0x1800283ab  mov     [rsp+520h+var_500], r8
0x1800283b0  lea     r8, aPropertyBagSWa_0; "Property Bag: '%s' was denied access to"...
0x1800283b7  mov     edx, 104h; unsigned __int64
0x1800283bc  lea     rcx, [rbp+420h+var_460]; unsigned __int16 *
0x1800283c0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800283c5  jmp     short loc_1800283F9
0x1800283c7  mov     rdx, [r15]
0x1800283ca  mov     rax, [rsi+40h]
0x1800283ce  mov     rcx, [rax]
0x1800283d1  mov     r9, [rcx+10h]
0x1800283d5  cmp     dword ptr [r9-10h], 0
0x1800283da  jnz     short loc_1800283DF
0x1800283dc  mov     r9, [rcx]
0x1800283df  mov     [rsp+520h+var_500], rdx
0x1800283e4  lea     r8, aPropertyBagSWa; "Property Bag: '%s' was denied access to"...
0x1800283eb  mov     edx, 104h; unsigned __int64
0x1800283f0  lea     rcx, [rbp+420h+var_460]; unsigned __int16 *
0x1800283f4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800283f9  mov     rcx, [rsi+48h]
0x1800283fd  test    rcx, rcx
0x180028400  jz      short loc_180028414
0x180028402  mov     rax, [rcx]
0x180028405  lea     r8, [rbp+420h+var_460]
0x180028409  xor     edx, edx
0x18002840b  mov     rax, [rax+60h]
0x18002840f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028414  mov     edi, 80070005h
0x180028419  jmp     loc_1800286F9
0x18002841e  test    r9d, r9d
0x180028421  jz      short loc_180028442
0x180028423  xor     r14d, r14d
0x180028426  mov     [rsp+520h+var_4E0], r14d
0x18002842b  jmp     short loc_18002843D
0x18002842d  cmp     eax, 80070002h
0x180028432  jnz     loc_1800285FE
0x180028438  mov     rbx, qword ptr [rsp+520h+var_4B0+8]
0x18002843d  test    r14d, r14d
0x180028440  jz      short loc_18002846A
0x180028442  mov     qword ptr [rbp+420h+var_488], 0
0x18002844a  mov     rax, [rsi+40h]
0x18002844e  mov     qword ptr [rbp+420h+var_488+8], rax
0x180028452  lea     rdx, [rbp+420h+var_488]
0x180028456  lea     rcx, [rsp+520h+var_4B0]
0x18002845b  call    ?push_back@?$vector@UPropertyBagEntry@@V?$allocator@UPropertyBagEntry@@@std@@@std@@QEAAXAEBUPropertyBagEntry@@@Z; std::vector<PropertyBagEntry>::push_back(PropertyBagEntry const &)
0x180028460  mov     rbx, qword ptr [rsp+520h+var_4B0+8]
0x180028465  mov     r12, qword ptr [rsp+520h+var_4B0]
0x18002846a  sub     rbx, r12
0x18002846d  sar     rbx, 4
0x180028471  test    rbx, rbx
0x180028474  jz      loc_1800285FE
0x18002847a  xor     esi, esi
0x18002847c  xor     eax, eax
0x18002847e  add     rax, rax
0x180028481  mov     rcx, [r12+rax*8]
0x180028485  mov     [rbp+420h+var_478], rcx
0x180028489  mov     r13, [r12+rax*8+8]
0x18002848e  add     r13, 68h ; 'h'
0x180028492  mov     rdx, r13
0x180028495  lea     rcx, [rsp+520h+var_4D0]
0x18002849a  call    ??0?$vector@UPropertyBagEntry@@V?$allocator@UPropertyBagEntry@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<PropertyBagEntry>::vector<PropertyBagEntry>(std::vector<PropertyBagEntry> const &)
0x18002849f  nop
0x1800284a0  mov     rdi, [rsp+520h+var_4D0]
0x1800284a5  mov     r14, [rsp+520h+var_4C8]
0x1800284aa  cmp     rdi, r14
0x1800284ad  jz      short loc_1800284EE
0x1800284af  lea     r15, [rdi+10h]
0x1800284b3  mov     rcx, [rdi]
0x1800284b6  mov     rax, [rsp+520h+var_4D8]
0x1800284bb  mov     rdx, [rax]; lpString2
0x1800284be  mov     rcx, [rcx]; lpString1
0x1800284c1  call    cs:__imp_lstrcmpW
0x1800284c7  test    eax, eax
0x1800284c9  jz      short loc_1800284E0
0x1800284cb  mov     rdi, r15
0x1800284ce  jmp     short loc_1800284AA
0x1800284d0  movups  xmm0, xmmword ptr [r15]
0x1800284d4  movdqu  xmmword ptr [rdi], xmm0
0x1800284d8  lea     rdi, [rdi+10h]
0x1800284dc  add     r15, 10h
0x1800284e0  cmp     r15, r14
0x1800284e3  jnz     short loc_1800284D0
0x1800284e5  sub     r14, 10h
0x1800284e9  mov     [rsp+520h+var_4C8], r14
0x1800284ee  xorps   xmm0, xmm0
0x1800284f1  movups  [rbp+420h+var_488], xmm0
0x1800284f5  mov     r15d, 90h
0x1800284fb  mov     ecx, r15d; cb
0x1800284fe  call    cs:__imp_CoTaskMemAlloc
0x180028504  mov     rdi, rax
0x180028507  mov     qword ptr [rbp+420h+var_488], rax
0x18002850b  test    rax, rax
0x18002850e  jnz     short loc_18002851F
0x180028510  mov     edi, 8007000Eh
0x180028515  mov     r15, [rsp+520h+var_4D8]
0x18002851a  jmp     loc_1800285DE
0x18002851f  mov     r8, r15; Size
0x180028522  xor     edx, edx; Val
0x180028524  mov     rcx, rdi; void *
0x180028527  call    memset_0
0x18002852c  mov     [rbp+420h+var_498], rdi
0x180028530  mov     eax, 1
0x180028535  mov     dword ptr [rbp+420h+var_490], eax
0x180028538  mov     dword ptr [rbp+420h+var_490+4], eax
0x18002853b  mov     r15, [rsp+520h+var_4D8]
0x180028540  mov     rdx, r15; struct tagHELPER_ATTRIBUTE *
0x180028543  mov     rcx, rdi; struct tagHELPER_ATTRIBUTE *
0x180028546  call    ?CopyHelperAttribute@@YAJPEAUtagHELPER_ATTRIBUTE@@PEBU1@@Z; CopyHelperAttribute(tagHELPER_ATTRIBUTE *,tagHELPER_ATTRIBUTE const *)
0x18002854b  mov     edi, eax
0x18002854d  xor     ecx, ecx
0x18002854f  test    eax, eax
0x180028551  js      short loc_180028575
0x180028553  mov     eax, [rsp+520h+var_4B8]
0x180028557  mov     dword ptr [rbp+420h+var_488+8], eax
0x18002855a  mov     [rbp+420h+var_498], rcx
0x18002855e  mov     [rbp+420h+var_490], rcx
0x180028562  lea     rdx, [rbp+420h+var_488]
0x180028566  lea     rcx, [rsp+520h+var_4D0]
0x18002856b  call    ?push_back@?$vector@UPropertyBagEntry@@V?$allocator@UPropertyBagEntry@@@std@@@std@@QEAAXAEBUPropertyBagEntry@@@Z; std::vector<PropertyBagEntry>::push_back(PropertyBagEntry const &)
0x180028570  mov     r14, [rsp+520h+var_4C8]
0x180028575  lea     rcx, [rbp+420h+var_498]
0x180028579  call    ??1?$TNDFDeallocator@PEAUtagHELPER_ATTRIBUTE@@$1?FreeHelperAttributes@@YAXPEAU1@KH@Z@@QEAA@XZ; TNDFDeallocator<tagHELPER_ATTRIBUTE *,&FreeHelperAttributes(tagHELPER_ATTRIBUTE *,ulong,int)>::~TNDFDeallocator<tagHELPER_ATTRIBUTE *,&FreeHelperAttributes(tagHELPER_ATTRIBUTE *,ulong,int)>(void)
0x18002857e  test    edi, edi
0x180028580  js      short loc_1800285DE
0x180028582  lea     rax, [rsp+520h+var_4D0]
0x180028587  cmp     r13, rax
0x18002858a  jz      short loc_1800285BD
0x18002858c  mov     rax, [r13+0]
0x180028590  mov     rcx, [rsp+520h+var_4D0]
0x180028595  mov     [r13+0], rcx
0x180028599  mov     [rsp+520h+var_4D0], rax
0x18002859e  mov     rax, [r13+8]
0x1800285a2  mov     [r13+8], r14
0x1800285a6  mov     [rsp+520h+var_4C8], rax
0x1800285ab  mov     rcx, [r13+10h]
0x1800285af  mov     rax, [rsp+520h+var_4C0]
0x1800285b4  mov     [r13+10h], rax
0x1800285b8  mov     [rsp+520h+var_4C0], rcx
0x1800285bd  mov     rax, [rbp+420h+var_478]
0x1800285c1  test    rax, rax
0x1800285c4  jz      short loc_1800285DE
0x1800285c6  mov     rcx, [rax]; pv
0x1800285c9  test    rcx, rcx
0x1800285cc  jz      short loc_1800285DE
0x1800285ce  mov     eax, 1
0x1800285d3  mov     r8d, eax; int
0x1800285d6  mov     edx, eax; unsigned int
0x1800285d8  call    ?FreeHelperAttributes@@YAXPEAUtagHELPER_ATTRIBUTE@@KH@Z; FreeHelperAttributes(tagHELPER_ATTRIBUTE *,ulong,int)
0x1800285dd  nop
0x1800285de  lea     rcx, [rsp+520h+var_4D0]
0x1800285e3  call    ??1?$vector@PEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$allocator@PEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@@std@@QEAA@XZ; std::vector<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *,std::allocator<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *>>::~vector<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *,std::allocator<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *>>(void)
0x1800285e8  inc     esi
0x1800285ea  mov     eax, esi
0x1800285ec  cmp     rax, rbx
0x1800285ef  jb      loc_18002847E
0x1800285f5  mov     rsi, [rbp+420h+var_470]
0x1800285f9  mov     r14d, [rsp+520h+var_4E0]
0x1800285fe  cmp     qword ptr [rsi+48h], 0
0x180028603  jz      loc_1800286F9
0x180028609  xor     edx, edx; Val
0x18002860b  mov     r8d, 208h; Size
0x180028611  lea     rcx, [rbp+420h+var_250]; void *
0x180028618  call    memset_0
0x18002861d  test    edi, edi
0x18002861f  js      short loc_180028691
0x180028621  mov     rdx, r15
0x180028624  lea     rcx, [rsp+520h+var_4D8]
0x180028629  call    ?ToString@AttributeConverter@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBUtagHELPER_ATTRIBUTE@@@Z; AttributeConverter::ToString(tagHELPER_ATTRIBUTE const *)
0x18002862e  mov     r8, [rsp+520h+var_4D8]
0x180028633  lea     rax, aCommitedTheReq; "commited the requested"
0x18002863a  lea     rcx, aAdded; "added"
0x180028641  test    r14d, r14d
0x180028644  cmovz   rcx, rax
0x180028648  mov     rax, [rsi+40h]
0x18002864c  mov     rdx, [rax]
0x18002864f  mov     r9, [rdx+10h]
0x180028653  cmp     dword ptr [r9-10h], 0
0x180028658  jnz     short loc_18002865D
0x18002865a  mov     r9, [rdx]
0x18002865d  mov     [rsp+520h+var_4F8], r8
0x180028662  mov     [rsp+520h+var_500], rcx
0x180028667  lea     r8, aPropertyBagSSP; "Property Bag: '%s' %s property bag entr"...
0x18002866e  mov     edx, 104h; unsigned __int64
0x180028673  lea     rcx, [rbp+420h+var_250]; unsigned __int16 *
0x18002867a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002867f  mov     ebx, eax
0x180028681  mov     rcx, [rsp+520h+var_4D8]
0x180028686  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002868a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002868f  jmp     short loc_1800286CB
0x180028691  mov     rax, [rsi+40h]
0x180028695  mov     rcx, [rax]
0x180028698  mov     rax, [rcx+10h]
0x18002869c  cmp     dword ptr [rax-10h], 0
0x1800286a0  jnz     short loc_1800286A5
0x1800286a2  mov     rax, [rcx]
0x1800286a5  mov     dword ptr [rsp+520h+var_4F8], edi
0x1800286a9  mov     [rsp+520h+var_500], rax
0x1800286ae  mov     r9, [r15]
0x1800286b1  lea     r8, aPropertyBagFai; "Property Bag: Failed to add property ba"...
0x1800286b8  mov     edx, 104h; unsigned __int64
0x1800286bd  lea     rcx, [rbp+420h+var_250]; unsigned __int16 *
0x1800286c4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800286c9  mov     ebx, eax
0x1800286cb  mov     ecx, 80000000h
0x1800286d0  lea     eax, [rbx+rcx]
0x1800286d3  test    ecx, eax
0x1800286d5  jnz     short loc_1800286DF
  ... truncated ...
```
