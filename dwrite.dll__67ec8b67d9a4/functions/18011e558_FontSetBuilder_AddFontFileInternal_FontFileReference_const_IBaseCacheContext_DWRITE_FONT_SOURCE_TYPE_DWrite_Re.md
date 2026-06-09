# FontSetBuilder::AddFontFileInternal(FontFileReference const &,IBaseCacheContext *,DWRITE_FONT_SOURCE_TYPE,DWrite::RefString const &)

- ea: `0x18011e558`
- end: `0x18011e93a`
- name: `?AddFontFileInternal@FontSetBuilder@@AEAAJAEBVFontFileReference@@PEAUIBaseCacheContext@@W4DWRITE_FONT_SOURCE_TYPE@@AEBVRefString@DWrite@@@Z`
- size: `994`
- prototype: `int __high(const struct FontFileReference *, struct IBaseCacheContext *, enum DWRITE_FONT_SOURCE_TYPE, const struct DWrite::RefString *)`
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180132b84`

## callees

- `0x18011e500`
- `0x18011e558`
- `0x18011e940`
- `0x18011ed18`
- `0x18011ee34`
- `0x18011ef04`
- `0x18011ef30`
- `0x18011ef48`
- `0x18011f048`
- `0x18011f978`
- `0x18011fe78`
- `0x18014519c`
- `0x180149278`
- `0x18014d27c`
- `0x180150590`
- `0x180152858`
- `0x18016968c`
- `0x1801dab18`
- `0x1801efaac`
- `0x1801f0018`
- `0x1801fec30`
- `0x180212490`
- `0x180212f4c`

## import_xrefs

- `ntdll!NtSetInformationThread` at `0x18011e896`
- `ntdll!NtSetInformationThread` at `0x18011e929`
- `ntdll!NtSetInformationThread` at `0x18011e896`
- `ntdll!NtSetInformationThread` at `0x18011e929`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18011e87e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18011e911`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18011e87e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18011e911`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall FontSetBuilder::AddFontFileInternal(
        __int64 a1,
        __int64 a2,
        struct IBaseCacheContext *a3,
        unsigned int a4,
        __int64 a5)
{
  __int64 v6; // r15
  unsigned __int16 v7; // r14
  unsigned int v8; // esi
  unsigned int v9; // edi
  unsigned int v10; // r12d
  unsigned __int16 InstanceCount; // r13
  __int64 v12; // rsi
  unsigned int v13; // edi
  __int64 v14; // rax
  HANDLE v15; // rax
  HANDLE CurrentThread; // rax
  unsigned int i; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int ThreadInformation; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int v20; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v21; // [rsp+3Ch] [rbp-C4h]
  __int64 v22; // [rsp+40h] [rbp-C0h]
  __int64 v23; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v24; // [rsp+50h] [rbp-B0h]
  unsigned int v25; // [rsp+58h] [rbp-A8h]
  int v26; // [rsp+5Ch] [rbp-A4h]
  __int64 v27; // [rsp+60h] [rbp-A0h]
  __int64 v28; // [rsp+68h] [rbp-98h]
  __int128 v29; // [rsp+70h] [rbp-90h] BYREF
  __int64 v30; // [rsp+80h] [rbp-80h]
  struct IBaseCacheContext *v31; // [rsp+88h] [rbp-78h]
  __int64 v32; // [rsp+90h] [rbp-70h]
  _QWORD v33[3]; // [rsp+98h] [rbp-68h] BYREF
  char v34[8]; // [rsp+B0h] [rbp-50h] BYREF
  char v35[8]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v36; // [rsp+C0h] [rbp-40h] BYREF
  int v37; // [rsp+C8h] [rbp-38h]
  int v38; // [rsp+CCh] [rbp-34h]
  int v39; // [rsp+D0h] [rbp-30h]
  char v40; // [rsp+D4h] [rbp-2Ch]
  char v41; // [rsp+D5h] [rbp-2Bh]
  __int16 v42; // [rsp+D6h] [rbp-2Ah]
  __int64 v43; // [rsp+D8h] [rbp-28h]
  __int64 v44; // [rsp+E0h] [rbp-20h]
  _BYTE v45[56]; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v46; // [rsp+120h] [rbp+20h] BYREF
  int v47; // [rsp+128h] [rbp+28h]
  int v48; // [rsp+12Ch] [rbp+2Ch]
  int v49; // [rsp+130h] [rbp+30h]
  char v50; // [rsp+134h] [rbp+34h]
  char v51; // [rsp+135h] [rbp+35h]
  __int16 v52; // [rsp+136h] [rbp+36h]
  __int64 v53; // [rsp+138h] [rbp+38h]
  __int64 v54; // [rsp+140h] [rbp+40h]
  __int64 v55; // [rsp+148h] [rbp+48h] BYREF
  __int64 v56; // [rsp+150h] [rbp+50h] BYREF
  char v57[112]; // [rsp+158h] [rbp+58h] BYREF
  __int64 v58; // [rsp+1C8h] [rbp+C8h]
  _BYTE v59[32]; // [rsp+1D0h] [rbp+D0h] BYREF
  _BYTE v60[144]; // [rsp+1F0h] [rbp+F0h] BYREF

  v21 = a4;
  v31 = a3;
  v6 = a1;
  v22 = a1;
  v32 = a5;
  LowMemoryPriority::LowMemoryPriority((LowMemoryPriority *)&v20);
  v23 = a2;
  v24 = 6;
  v7 = 0;
  v25 = 0;
  v26 = -1;
  v27 = 0;
  v28 = 0;
  FontFileAnalyzer::Analyze((FontFileAnalyzer *)&v23);
  if ( (_DWORD)v24 && (unsigned int)(v24 - 1) > 1 )
  {
    if ( v20 )
    {
      i = v20;
      CurrentThread = GetCurrentThread();
      NtSetInformationThread(CurrentThread, ThreadPagePriority, &i, 4u);
    }
    return 2291683328LL;
  }
  else
  {
    v43 = *(_QWORD *)(a2 + 24);
    v44 = 0;
    v36 = *(_QWORD *)(a2 + 8);
    v40 = v24;
    v41 = v24;
    v37 = 0;
    v42 = 0;
    v38 = *(_DWORD *)(a2 + 32);
    v39 = 0;
    FontFaceKey::Validate((FontFaceKey *)&v36);
    FontFileReference::FontFileReference((FontFileReference *)v45, (const struct FontFileReference *)a2);
    v8 = v25;
    if ( v25 > 0xFFFF )
      v8 = 0xFFFF;
    ThreadInformation = v8;
    v9 = 0;
    for ( i = 0; (unsigned __int16)v9 < v8; i = v9 )
    {
      v10 = (unsigned __int16)v9;
      v37 = (unsigned __int16)v9;
      InstanceCount = FontFileAnalyzer::GetInstanceCount((FontFileAnalyzer *)&v23, (unsigned __int16)v9);
      std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(&v29);
      if ( InstanceCount )
      {
        v12 = v22;
        v13 = v21;
        do
        {
          if ( (unsigned __int8)FontFileAnalyzer::GetInstanceParameters(&v23, v10, v7, &v29) )
          {
            HIWORD(v39) = 1;
            v14 = v29;
            LOWORD(v39) = (__int64)(*((_QWORD *)&v29 + 1) - v29) >> 3;
          }
          else
          {
            v14 = 0;
            v39 = 0;
          }
          v44 = v14;
          FontFaceElementKeyBase::FontFaceElementKeyBase(v33, &v36, a2, 2);
          v33[0] = &FontFaceElementKey::`vftable';
          FontFaceLight::FontFaceLight((FontFaceLight *)v60, v31, (const struct FontFaceElementKey *)v33);
          v46 = v36;
          v47 = v37;
          v48 = v38;
          v49 = v39;
          v50 = v40;
          v51 = v41;
          v52 = v42;
          v53 = v43;
          v54 = v44;
          RefCountedArray<unsigned char>::RefCountedArray<unsigned char>(&v55);
          RefCountedArray<DWRITE_FONT_AXIS_VALUE_FIXED>::RefCountedArray<DWRITE_FONT_AXIS_VALUE_FIXED>(
            &v56,
            v54,
            (unsigned __int16)v49);
          v53 = v55 + 8;
          v54 = v56 + 8;
          memset_0(v57, 0, sizeof(v57));
          v58 = 0;
          std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(v59);
          FontSetBuilder::AddFontInformation(v12, &v46, v60, v13, v32);
          if ( *(_QWORD *)(v6 + 32) == *(_QWORD *)(v6 + 40) )
          {
            std::vector<FontSetBuilder::FontEntryWithProperties>::_Emplace_reallocate<FontSetBuilder::FontEntryWithProperties const &>(
              v6 + 24,
              *(_QWORD *)(v6 + 32),
              &v46);
          }
          else
          {
            FontSetBuilder::FontEntryWithProperties::FontEntryWithProperties(
              *(FontSetBuilder::FontEntryWithProperties **)(v6 + 32),
              (const struct FontSetBuilder::FontEntryWithProperties *)&v46);
            *(_QWORD *)(v6 + 32) += 200LL;
          }
          std::vector<FontFeatureCoverageRegionBuilder::Feature>::_Tidy(v59);
          FontFaceKeyWithStorage::~FontFaceKeyWithStorage((FontFaceKeyWithStorage *)&v46);
          FontFaceLight::~FontFaceLight((FontFaceLight *)v60);
          ComPtr<ClientSideRemoteFileStream>::~ComPtr<ClientSideRemoteFileStream>(v35);
          ComPtr<ClientSideRemoteFileStream>::~ComPtr<ClientSideRemoteFileStream>(v34);
          ++v7;
        }
        while ( v7 < InstanceCount );
        v9 = i;
        v8 = ThreadInformation;
        v6 = v22;
      }
      v7 = 0;
      if ( (_QWORD)v29 )
      {
        std::_Deallocate<16>(v29, (v30 - v29) & 0xFFFFFFFFFFFFFFF8uLL);
        v29 = 0;
        v30 = 0;
      }
      LOWORD(v9) = v9 + 1;
    }
    FontFileReference::~FontFileReference((FontFileReference *)v45);
    if ( v20 )
    {
      ThreadInformation = v20;
      v15 = GetCurrentThread();
      NtSetInformationThread(v15, ThreadPagePriority, &ThreadInformation, 4u);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x18011e558  mov     [rsp-8+arg_18], rbx
0x18011e55d  push    rbp
0x18011e55e  push    rsi
0x18011e55f  push    rdi
0x18011e560  push    r12
0x18011e562  push    r13
0x18011e564  push    r14
0x18011e566  push    r15
0x18011e568  lea     rbp, [rsp-190h]
0x18011e570  sub     rsp, 290h
0x18011e577  mov     rax, cs:__security_cookie
0x18011e57e  xor     rax, rsp
0x18011e581  mov     [rbp+1C0h+var_40], rax
0x18011e588  mov     [rsp+2C0h+var_284], r9d
0x18011e58d  mov     [rbp+1C0h+var_238], r8
0x18011e591  mov     rbx, rdx
0x18011e594  mov     r15, rcx
0x18011e597  mov     [rsp+2C0h+var_280], rcx
0x18011e59c  mov     rax, [rbp+1C0h+arg_20]
0x18011e5a3  mov     [rbp+1C0h+var_230], rax
0x18011e5a7  lea     rcx, [rsp+2C0h+var_288]; this
0x18011e5ac  call    ??0LowMemoryPriority@@QEAA@XZ; LowMemoryPriority::LowMemoryPriority(void)
0x18011e5b1  nop
0x18011e5b2  mov     [rsp+2C0h+var_278], rbx
0x18011e5b7  mov     [rsp+2C0h+var_270], 6
0x18011e5c0  xor     r14d, r14d
0x18011e5c3  mov     [rsp+2C0h+var_268], r14d
0x18011e5c8  mov     [rsp+2C0h+var_264], 0FFFFFFFFh
0x18011e5d0  mov     [rsp+2C0h+var_260], r14
0x18011e5d5  mov     [rsp+2C0h+var_258], r14
0x18011e5da  lea     rcx, [rsp+2C0h+var_278]; this
0x18011e5df  call    ?Analyze@FontFileAnalyzer@@AEAAXXZ; FontFileAnalyzer::Analyze(void)
0x18011e5e4  mov     edx, dword ptr [rsp+2C0h+var_270]
0x18011e5e8  mov     ecx, edx
0x18011e5ea  test    edx, edx
0x18011e5ec  jz      short loc_18011E5FC
0x18011e5ee  sub     ecx, 1
0x18011e5f1  jz      short loc_18011E5FC
0x18011e5f3  cmp     ecx, 1
0x18011e5f6  jnz     loc_18011E905
0x18011e5fc  mov     rax, [rbx+18h]
0x18011e600  mov     [rbp+1C0h+var_1E8], rax
0x18011e604  mov     [rbp+1C0h+var_1E0], r14
0x18011e608  mov     rax, [rbx+8]
0x18011e60c  mov     [rbp+1C0h+var_200], rax
0x18011e610  mov     [rbp+1C0h+var_1EC], dl
0x18011e613  mov     [rbp+1C0h+var_1EB], dl
0x18011e616  mov     [rbp+1C0h+var_1F8], r14d
0x18011e61a  mov     [rbp+1C0h+var_1EA], r14w
0x18011e61f  mov     eax, [rbx+20h]
0x18011e622  mov     [rbp+1C0h+var_1F4], eax
0x18011e625  mov     [rbp+1C0h+var_1F0], r14d
0x18011e629  lea     rcx, [rbp+1C0h+var_200]; this
0x18011e62d  call    ?Validate@FontFaceKey@@IEBAXXZ; FontFaceKey::Validate(void)
0x18011e632  mov     rdx, rbx; struct FontFileReference *
0x18011e635  lea     rcx, [rbp+1C0h+var_1D8]; this
0x18011e639  call    ??0FontFileReference@@QEAA@AEBV0@@Z; FontFileReference::FontFileReference(FontFileReference const &)
0x18011e63e  nop
0x18011e63f  mov     esi, [rsp+2C0h+var_268]
0x18011e643  mov     eax, 0FFFFh
0x18011e648  cmp     esi, eax
0x18011e64a  cmova   esi, eax
0x18011e64d  mov     [rsp+2C0h+ThreadInformation], esi
0x18011e651  mov     edi, r14d
0x18011e654  mov     [rsp+2C0h+var_290], r14d
0x18011e659  test    esi, esi
0x18011e65b  jz      loc_18011E868
0x18011e661  movzx   r12d, di
0x18011e665  mov     [rbp+1C0h+var_1F8], r12d
0x18011e669  mov     edx, r12d; unsigned int
0x18011e66c  lea     rcx, [rsp+2C0h+var_278]; this
0x18011e671  call    ?GetInstanceCount@FontFileAnalyzer@@QEAAGI@Z; FontFileAnalyzer::GetInstanceCount(uint)
0x18011e676  movzx   r13d, ax
0x18011e67a  lea     rcx, [rsp+2C0h+var_250]; void *
0x18011e67f  call    ??0?$vector@V?$KeyValuePair@HVOpenTypeName@@@@V?$allocator@V?$KeyValuePair@HVOpenTypeName@@@@@std@@@std@@QEAA@XZ; std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(void)
0x18011e684  nop
0x18011e685  xor     ecx, ecx
0x18011e687  cmp     cx, r13w
0x18011e68b  jnb     loc_18011E82C
0x18011e691  mov     rsi, [rsp+2C0h+var_280]
0x18011e696  mov     edi, [rsp+2C0h+var_284]
0x18011e69a  lea     r9, [rsp+2C0h+var_250]
0x18011e69f  movzx   r8d, r14w
0x18011e6a3  mov     edx, r12d
0x18011e6a6  lea     rcx, [rsp+2C0h+var_278]
0x18011e6ab  call    ?GetInstanceParameters@FontFileAnalyzer@@QEAA_NIGAEAV?$vector@UDWRITE_FONT_AXIS_VALUE_FIXED@@V?$allocator@UDWRITE_FONT_AXIS_VALUE_FIXED@@@std@@@std@@@Z; FontFileAnalyzer::GetInstanceParameters(uint,ushort,std::vector<DWRITE_FONT_AXIS_VALUE_FIXED> &)
0x18011e6b0  test    al, al
0x18011e6b2  jnz     loc_18011E8E2
0x18011e6b8  xor     eax, eax
0x18011e6ba  mov     [rbp+1C0h+var_1F0], eax
0x18011e6bd  mov     [rbp+1C0h+var_1E0], rax
0x18011e6c1  mov     r9d, 2
0x18011e6c7  mov     r8, rbx
0x18011e6ca  lea     rdx, [rbp+1C0h+var_200]
0x18011e6ce  lea     rcx, [rbp+1C0h+var_228]
0x18011e6d2  call    ??0FontFaceElementKeyBase@@QEAA@AEBVFontFaceKey@@AEBVFontFileReference@@W4CacheElementType@@@Z; FontFaceElementKeyBase::FontFaceElementKeyBase(FontFaceKey const &,FontFileReference const &,CacheElementType)
0x18011e6d7  lea     rax, ??_7FontFaceElementKey@@6B@; const FontFaceElementKey::`vftable'
0x18011e6de  mov     [rbp+1C0h+var_228], rax
0x18011e6e2  lea     r8, [rbp+1C0h+var_228]; struct FontFaceElementKey *
0x18011e6e6  mov     rdx, [rbp+1C0h+var_238]; struct IBaseCacheContext *
0x18011e6ea  lea     rcx, [rbp+1C0h+var_D0]; this
0x18011e6f1  call    ??0FontFaceLight@@QEAA@PEAUIBaseCacheContext@@AEBVFontFaceElementKey@@@Z; FontFaceLight::FontFaceLight(IBaseCacheContext *,FontFaceElementKey const &)
0x18011e6f6  nop
0x18011e6f7  mov     rax, [rbp+1C0h+var_200]
0x18011e6fb  mov     [rbp+1C0h+var_1A0], rax
0x18011e6ff  mov     eax, [rbp+1C0h+var_1F8]
0x18011e702  mov     [rbp+1C0h+var_198], eax
0x18011e705  mov     r8d, [rbp+1C0h+var_1F4]
0x18011e709  mov     [rbp+1C0h+var_194], r8d
0x18011e70d  movzx   eax, word ptr [rbp+1C0h+var_1F0]
0x18011e711  mov     word ptr [rbp+1C0h+var_190], ax
0x18011e715  movzx   eax, word ptr [rbp+1C0h+var_1F0+2]
0x18011e719  mov     word ptr [rbp+1C0h+var_190+2], ax
0x18011e71d  mov     al, [rbp+1C0h+var_1EC]
0x18011e720  mov     [rbp+1C0h+var_18C], al
0x18011e723  mov     al, [rbp+1C0h+var_1EB]
0x18011e726  mov     [rbp+1C0h+var_18B], al
0x18011e729  movzx   eax, [rbp+1C0h+var_1EA]
0x18011e72d  mov     [rbp+1C0h+var_18A], ax
0x18011e731  mov     rdx, [rbp+1C0h+var_1E8]
0x18011e735  mov     [rbp+1C0h+var_188], rdx
0x18011e739  mov     rax, [rbp+1C0h+var_1E0]
0x18011e73d  mov     [rbp+1C0h+var_180], rax
0x18011e741  lea     rcx, [rbp+1C0h+var_178]
0x18011e745  call    ??0?$RefCountedArray@E@@QEAA@PEBXI@Z; RefCountedArray<uchar>::RefCountedArray<uchar>(void const *,uint)
0x18011e74a  nop
0x18011e74b  movzx   r8d, word ptr [rbp+1C0h+var_190]
0x18011e750  mov     rdx, [rbp+1C0h+var_180]
0x18011e754  lea     rcx, [rbp+1C0h+var_170]
0x18011e758  call    ??0?$RefCountedArray@UDWRITE_FONT_AXIS_VALUE_FIXED@@@@QEAA@PEBXI@Z; RefCountedArray<DWRITE_FONT_AXIS_VALUE_FIXED>::RefCountedArray<DWRITE_FONT_AXIS_VALUE_FIXED>(void const *,uint)
0x18011e75d  nop
0x18011e75e  mov     rax, [rbp+1C0h+var_178]
0x18011e762  add     rax, 8
0x18011e766  mov     [rbp+1C0h+var_188], rax
0x18011e76a  mov     rax, [rbp+1C0h+var_170]
0x18011e76e  add     rax, 8
0x18011e772  mov     [rbp+1C0h+var_180], rax
0x18011e776  xor     edx, edx; Val
0x18011e778  lea     r8d, [rdx+70h]; Size
0x18011e77c  lea     rcx, [rbp+1C0h+var_168]; void *
0x18011e780  call    memset_0
0x18011e785  mov     [rbp+1C0h+var_F8], 0
0x18011e790  lea     rcx, [rbp+1C0h+var_F0]; void *
0x18011e797  call    ??0?$vector@V?$KeyValuePair@HVOpenTypeName@@@@V?$allocator@V?$KeyValuePair@HVOpenTypeName@@@@@std@@@std@@QEAA@XZ; std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(void)
0x18011e79c  nop
0x18011e79d  mov     rax, [rbp+1C0h+var_230]
0x18011e7a1  mov     [rsp+2C0h+var_2A0], rax
0x18011e7a6  mov     r9d, edi
0x18011e7a9  lea     r8, [rbp+1C0h+var_D0]
0x18011e7b0  lea     rdx, [rbp+1C0h+var_1A0]
0x18011e7b4  mov     rcx, rsi
0x18011e7b7  call    ?AddFontInformation@FontSetBuilder@@IEAAXAEAUFontEntryWithProperties@1@AEBVFontFaceLight@@W4DWRITE_FONT_SOURCE_TYPE@@AEBVRefString@DWrite@@@Z; FontSetBuilder::AddFontInformation(FontSetBuilder::FontEntryWithProperties &,FontFaceLight const &,DWRITE_FONT_SOURCE_TYPE,DWrite::RefString const &)
0x18011e7bc  mov     rax, [r15+20h]
0x18011e7c0  cmp     rax, [r15+28h]
0x18011e7c4  jnz     loc_18011E8C9
0x18011e7ca  lea     r8, [rbp+1C0h+var_1A0]
0x18011e7ce  mov     rdx, rax
0x18011e7d1  lea     rcx, [r15+18h]
0x18011e7d5  call    ??$_Emplace_reallocate@AEBUFontEntryWithProperties@FontSetBuilder@@@?$vector@UFontEntryWithProperties@FontSetBuilder@@V?$allocator@UFontEntryWithProperties@FontSetBuilder@@@std@@@std@@AEAAPEAUFontEntryWithProperties@FontSetBuilder@@QEAU23@AEBU23@@Z; std::vector<FontSetBuilder::FontEntryWithProperties>::_Emplace_reallocate<FontSetBuilder::FontEntryWithProperties const &>(FontSetBuilder::FontEntryWithProperties * const,FontSetBuilder::FontEntryWithProperties const &)
0x18011e7da  nop
0x18011e7db  lea     rcx, [rbp+1C0h+var_F0]
0x18011e7e2  call    ?_Tidy@?$vector@UFeature@FontFeatureCoverageRegionBuilder@@V?$allocator@UFeature@FontFeatureCoverageRegionBuilder@@@std@@@std@@AEAAXXZ; std::vector<FontFeatureCoverageRegionBuilder::Feature>::_Tidy(void)
0x18011e7e7  lea     rcx, [rbp+1C0h+var_1A0]; this
0x18011e7eb  call    ??1FontFaceKeyWithStorage@@QEAA@XZ; FontFaceKeyWithStorage::~FontFaceKeyWithStorage(void)
0x18011e7f0  nop
0x18011e7f1  lea     rcx, [rbp+1C0h+var_D0]; this
0x18011e7f8  call    ??1FontFaceLight@@QEAA@XZ; FontFaceLight::~FontFaceLight(void)
0x18011e7fd  nop
0x18011e7fe  lea     rcx, [rbp+1C0h+var_208]
0x18011e802  call    ??1?$ComPtr@VClientSideRemoteFileStream@@@@QEAA@XZ; ComPtr<ClientSideRemoteFileStream>::~ComPtr<ClientSideRemoteFileStream>(void)
0x18011e807  lea     rcx, [rbp+1C0h+var_210]
0x18011e80b  call    ??1?$ComPtr@VClientSideRemoteFileStream@@@@QEAA@XZ; ComPtr<ClientSideRemoteFileStream>::~ComPtr<ClientSideRemoteFileStream>(void)
0x18011e810  nop
0x18011e811  inc     r14w
0x18011e815  cmp     r14w, r13w
0x18011e819  jb      loc_18011E69A
0x18011e81f  mov     edi, [rsp+2C0h+var_290]
0x18011e823  mov     esi, [rsp+2C0h+ThreadInformation]
0x18011e827  mov     r15, [rsp+2C0h+var_280]
0x18011e82c  mov     rcx, qword ptr [rsp+2C0h+var_250]
0x18011e831  xor     r14d, r14d
0x18011e834  test    rcx, rcx
0x18011e837  jz      short loc_18011E856
0x18011e839  mov     rdx, [rbp+1C0h+var_240]
0x18011e83d  sub     rdx, rcx
0x18011e840  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18011e844  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18011e849  xorps   xmm0, xmm0
0x18011e84c  movdqu  [rsp+2C0h+var_250], xmm0
0x18011e852  mov     [rbp+1C0h+var_240], r14
0x18011e856  inc     di
0x18011e859  mov     [rsp+2C0h+var_290], edi
0x18011e85d  movzx   eax, di
0x18011e860  cmp     eax, esi
0x18011e862  jb      loc_18011E661
0x18011e868  lea     rcx, [rbp+1C0h+var_1D8]; this
0x18011e86c  call    ??1FontFileReference@@QEAA@XZ; FontFileReference::~FontFileReference(void)
0x18011e871  nop
0x18011e872  mov     eax, [rsp+2C0h+var_288]
0x18011e876  test    eax, eax
0x18011e878  jz      short loc_18011E89D
0x18011e87a  mov     [rsp+2C0h+ThreadInformation], eax
0x18011e87e  call    cs:__imp_GetCurrentThread
0x18011e884  mov     rcx, rax; ThreadHandle
0x18011e887  mov     r9d, 4; ThreadInformationLength
0x18011e88d  lea     r8, [rsp+2C0h+ThreadInformation]; ThreadInformation
0x18011e892  lea     edx, [r9+14h]; ThreadInformationClass
0x18011e896  call    cs:__imp_NtSetInformationThread
0x18011e89c  nop
0x18011e89d  xor     eax, eax
0x18011e89f  mov     rcx, [rbp+1C0h+var_40]
0x18011e8a6  xor     rcx, rsp; StackCookie
0x18011e8a9  call    __security_check_cookie
0x18011e8ae  mov     rbx, [rsp+2C0h+arg_18]
0x18011e8b6  add     rsp, 290h
0x18011e8bd  pop     r15
0x18011e8bf  pop     r14
0x18011e8c1  pop     r13
0x18011e8c3  pop     r12
0x18011e8c5  pop     rdi
0x18011e8c6  pop     rsi
0x18011e8c7  pop     rbp
0x18011e8c8  retn
0x18011e8c9  lea     rdx, [rbp+1C0h+var_1A0]; struct FontSetBuilder::FontEntryWithProperties *
0x18011e8cd  mov     rcx, rax; this
0x18011e8d0  call    ??0FontEntryWithProperties@FontSetBuilder@@QEAA@AEBU01@@Z; FontSetBuilder::FontEntryWithProperties::FontEntryWithProperties(FontSetBuilder::FontEntryWithProperties const &)
0x18011e8d5  add     qword ptr [r15+20h], 0C8h
0x18011e8dd  jmp     loc_18011E7DB
0x18011e8e2  mov     eax, 1
0x18011e8e7  mov     word ptr [rbp+1C0h+var_1F0+2], ax
0x18011e8eb  mov     rcx, qword ptr [rsp+2C0h+var_250+8]
0x18011e8f0  mov     rax, qword ptr [rsp+2C0h+var_250]
0x18011e8f5  sub     rcx, rax
0x18011e8f8  sar     rcx, 3
0x18011e8fc  mov     word ptr [rbp+1C0h+var_1F0], cx
0x18011e900  jmp     loc_18011E6BD
0x18011e905  mov     eax, [rsp+2C0h+var_288]
0x18011e909  test    eax, eax
0x18011e90b  jz      short loc_18011E930
0x18011e90d  mov     [rsp+2C0h+var_290], eax
0x18011e911  call    cs:__imp_GetCurrentThread
0x18011e917  mov     rcx, rax; ThreadHandle
0x18011e91a  mov     r9d, 4; ThreadInformationLength
0x18011e920  lea     r8, [rsp+2C0h+var_290]; ThreadInformation
0x18011e925  lea     edx, [r9+14h]; ThreadInformationClass
0x18011e929  call    cs:__imp_NtSetInformationThread
0x18011e92f  nop
0x18011e930  mov     eax, 88985000h
0x18011e935  jmp     loc_18011E89F
```
