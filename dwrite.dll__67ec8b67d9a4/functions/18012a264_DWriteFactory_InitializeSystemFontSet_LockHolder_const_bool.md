# DWriteFactory::InitializeSystemFontSet(LockHolder const &,bool)

- ea: `0x18012a264`
- end: `0x18012a6ac`
- name: `?InitializeSystemFontSet@DWriteFactory@@QEAAXAEBVLockHolder@@_N@Z`
- size: `1096`
- prototype: `void __fastcall(DWriteFactory *__hidden this, const struct LockHolder *, bool)`
- caller_count: `6`
- callee_count: `27`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180128ee8`
- `0x1801292b0`
- `0x1801298e0`
- `0x180129f80`
- `0x18012a128`
- `0x1801d5570`

## callees

- `0x18011f670`
- `0x18012775c`
- `0x1801279a4`
- `0x180128ff0`
- `0x18012a264`
- `0x18012a734`
- `0x18012a8c0`
- `0x18012f530`
- `0x1801409e0`
- `0x180142940`
- `0x180142a64`
- `0x1801537f8`
- `0x180154068`
- `0x180159844`
- `0x18017a5c4`
- `0x1801dd7c0`
- `0x1801e453c`
- `0x1801e5a78`
- `0x1801e7ba8`
- `0x1802068ac`
- `0x18020a6ac`
- `0x18020d668`
- `0x18021deb8`
- `0x18021e1c2`
- `0x18022a960`
- `0x18022c6e8`
- `0x180330010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18012a313`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18012a313`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18012a332`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18012a332`

## string_xrefs

- `0x18012a4e7`: `fcUpdate`
- `0x18012a515`: `syscache`
- `0x18012a61c`: `fcCreate`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall DWriteFactory::InitializeSystemFontSet(DWriteFactory *this, const struct LockHolder *a2, char a3)
{
  char v3; // bl
  char *v5; // rsi
  char v6; // r12
  __int64 *v7; // r15
  void *v8; // r13
  _DWORD *v9; // r12
  __int64 v10; // rdx
  unsigned int v11; // eax
  _DWORD *v12; // rbx
  unsigned int v13; // edi
  const struct LockHolder *v14; // rsi
  unsigned __int8 MissingRequiredFonts; // al
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // r9
  __int64 v19; // rbx
  unsigned __int64 v20; // rdi
  __int64 v21; // rbx
  int v22; // eax
  FontCollectionBuilder *v23; // rdi
  __int64 *v24; // rax
  _DWORD *v25; // rbx
  unsigned int v26; // edx
  int v27; // [rsp+28h] [rbp-91h]
  _DWORD *pExceptionObject; // [rsp+40h] [rbp-79h] BYREF
  unsigned __int64 pExceptionObject_8; // [rsp+48h] [rbp-71h]
  __int64 v30; // [rsp+50h] [rbp-69h] BYREF
  int v31; // [rsp+58h] [rbp-61h]
  _DWORD *v32; // [rsp+60h] [rbp-59h]
  unsigned int v33; // [rsp+68h] [rbp-51h]
  unsigned int v34; // [rsp+6Ch] [rbp-4Dh]
  __int64 v35; // [rsp+70h] [rbp-49h]
  int v36; // [rsp+78h] [rbp-41h]
  __int64 v37; // [rsp+80h] [rbp-39h] BYREF
  __int16 v38; // [rsp+88h] [rbp-31h]
  void **v39; // [rsp+90h] [rbp-29h] BYREF
  unsigned int v40; // [rsp+98h] [rbp-21h]
  int v41; // [rsp+9Ch] [rbp-1Dh]
  const wchar_t *v42; // [rsp+A0h] [rbp-19h]
  int v43; // [rsp+A8h] [rbp-11h]
  __int64 v44; // [rsp+B0h] [rbp-9h]
  DWriteFactory *v45; // [rsp+B8h] [rbp-1h]
  __int64 v46; // [rsp+C0h] [rbp+7h]
  void *Block; // [rsp+120h] [rbp+67h] BYREF
  const struct LockHolder *v48; // [rsp+128h] [rbp+6Fh] BYREF
  char v49; // [rsp+130h] [rbp+77h]
  FontCollectionBuilder *v50; // [rsp+138h] [rbp+7Fh] BYREF

  v49 = a3;
  v48 = a2;
  v3 = a3;
  v5 = (char *)this + 8;
  ClientSideCacheContext::TryGetSystemCache((char *)this + 8, &Block);
  v6 = 0;
  LOBYTE(v48) = 0;
  v7 = (__int64 *)((char *)this + 648);
  v8 = Block;
  if ( Block )
  {
    v9 = (_DWORD *)((char *)this + 720);
    if ( *v7 && *v9 == *(_DWORD *)(*((_QWORD *)Block + 6) + 32LL) )
    {
      v6 = (char)v48;
    }
    else
    {
      if ( *v7 )
        v10 = *(_QWORD *)EventTag::EventTag((EventTag *)&v48, (const char (*)[9])"fcUpdate");
      else
        v10 = 0x74696E496366LL;
      EventSource<ComInterfaceList<DWriteFactory,IBaseCacheContext,IDWritePrivateFactory1,IDWritePrivateFactoryForGdi,IDWritePrivateFactoryForSettings,IDWriteOldPrivateFactory,IDWriteDebugFactory,IDWriteFactory8,IDWriteFactory7,IDWriteFactory6,IDWriteFactory5,IDWriteFactory4,IDWriteFactory3,IDWriteFactory2,IDWriteFactory1,IDWriteFactory>,IDWriteFactory8,ClientSideCacheContext,IDWritePrivateFactory1,IDWritePrivateFactoryForGdi,IDWritePrivateFactoryForSettings,IDWriteOldPrivateFactory,IDWriteDebugFactory>::LogEvent<>(
        (__int64)this,
        v10);
      v48 = 0;
      v11 = HashBlob(&qword_180374320, 0, 4u);
      v40 = HashWords((const unsigned int *)&v48, 2u, v11);
      v41 = 4;
      v39 = &FontCollectionElementKey::`vftable';
      v42 = &qword_180374320;
      v43 = 0;
      v44 = 0;
      v45 = this;
      v46 = 0;
      v30 = 0;
      v31 = 0;
      v32 = 0;
      v33 = 0;
      v35 = 0;
      v36 = 0;
      v37 = 0;
      v38 = 0;
      if ( !FindElementCommon(
              (struct ICacheReference *)v8,
              0,
              *((const struct CacheHeader **)v8 + 6),
              *((const unsigned int **)v8 + 7),
              *((const struct HashElement **)v8 + 8),
              *((const void **)v8 + 2),
              (const struct IElementKey *)&v39,
              (struct CachedElementData *)&v30) )
      {
        v19 = *(_QWORD *)EventTag::EventTag((EventTag *)&v48, (const char (*)[9])"syscache");
        v20 = *((_QWORD *)v8 + 2);
        Exception::Exception((Exception *)&pExceptionObject, -2003283961, 0);
        pExceptionObject_8 = v20;
        EventLogger::LogEvent<long,EventTag,unsigned int>(
          (_DWORD)this + 520,
          1952670022,
          1869771365,
          (_DWORD)pExceptionObject,
          v19,
          410);
        throw (InvalidCacheDataException *)&pExceptionObject;
      }
      v12 = v32;
      v13 = v33;
      v14 = (const struct LockHolder *)operator new(0x78u);
      v48 = v14;
      pExceptionObject = v12;
      pExceptionObject_8 = __PAIR64__(v34, v13);
      FontSet::FontSet((char *)v14 + 8, &pExceptionObject, v37);
      *((_QWORD *)v14 + 13) = this;
      *((_DWORD *)v14 + 29) = 0;
      *(_QWORD *)v14 = &ChildComObject<DWriteFontSet>::`vftable';
      ChildComPtr<DWriteFontSet>::operator=((char *)this + 648, v14);
      *v9 = *(_DWORD *)(*((_QWORD *)v8 + 6) + 32LL);
      v6 = 1;
      MissingRequiredFonts = FontSetCache::GetMissingRequiredFonts(*v7 + 8);
      v18 = MissingRequiredFonts;
      if ( MissingRequiredFonts )
      {
        EventLogger::LogEvent<long,EventTag,unsigned int,unsigned int>(
          (_DWORD)this + 520,
          1952670022,
          1869771365,
          MissingRequiredFonts,
          0x746E6F46737973LL,
          v27,
          MissingRequiredFonts);
        RegisterMemoryForCrashDumps(*((PVOID *)v8 + 2), *((_DWORD *)v8 + 10));
      }
      IntrusivePtr<ICacheReference>::~IntrusivePtr<ICacheReference>(&v37, v16, v17, v18);
      v5 = (char *)this + 8;
      v3 = v49;
    }
  }
  if ( !*v7 || v3 )
  {
    EventSource<ComInterfaceList<DWriteFactory,IBaseCacheContext,IDWritePrivateFactory1,IDWritePrivateFactoryForGdi,IDWritePrivateFactoryForSettings,IDWriteOldPrivateFactory,IDWriteDebugFactory,IDWriteFactory8,IDWriteFactory7,IDWriteFactory6,IDWriteFactory5,IDWriteFactory4,IDWriteFactory3,IDWriteFactory2,IDWriteFactory1,IDWriteFactory>,IDWriteFactory8,ClientSideCacheContext,IDWritePrivateFactory1,IDWritePrivateFactoryForGdi,IDWritePrivateFactoryForSettings,IDWriteOldPrivateFactory,IDWriteDebugFactory>::LogEvent<>(
      (__int64)this,
      0x6D756E456366LL);
    v21 = *v7;
    v22 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v5 + 40LL))(v5);
    SystemFontCollectionLoader::CreateFontCollectionBuilderIfNeeded(
      (int)&v50,
      (int)v5,
      v22,
      (FontSet *)((v21 + 8) & -(__int64)(v21 != 0)));
    v23 = v50;
    if ( v50 )
    {
      v24 = (__int64 *)EventTag::EventTag((EventTag *)&pExceptionObject, (const char (*)[9])"fcCreate");
      EventSource<ComInterfaceList<DWriteFactory,IBaseCacheContext,IDWritePrivateFactory1,IDWritePrivateFactoryForGdi,IDWritePrivateFactoryForSettings,IDWriteOldPrivateFactory,IDWriteDebugFactory,IDWriteFactory8,IDWriteFactory7,IDWriteFactory6,IDWriteFactory5,IDWriteFactory4,IDWriteFactory3,IDWriteFactory2,IDWriteFactory1,IDWriteFactory>,IDWriteFactory8,ClientSideCacheContext,IDWritePrivateFactory1,IDWritePrivateFactoryForGdi,IDWritePrivateFactoryForSettings,IDWriteOldPrivateFactory,IDWriteDebugFactory>::LogEvent<>(
        (__int64)this,
        *v24);
      FontSetBuilder::CreateFontSetRegionInMemory(v23, &v48, v5);
      v25 = operator new(0x78u);
      pExceptionObject = v25;
      DWriteFontSet::DWriteFontSet(v25, this, &v48);
      v25[29] = 0;
      *(_QWORD *)v25 = &ChildComObject<DWriteFontSet>::`vftable';
      ChildComPtr<DWriteFontSet>::operator=((char *)this + 648, v25);
      v6 = 1;
      RefCountedArrayImpl::~RefCountedArrayImpl((RefCountedArrayImpl *)&v48);
    }
    else
    {
      EventSource<ComInterfaceList<DWriteFactory,IBaseCacheContext,IDWritePrivateFactory1,IDWritePrivateFactoryForGdi,IDWritePrivateFactoryForSettings,IDWriteOldPrivateFactory,IDWriteDebugFactory,IDWriteFactory8,IDWriteFactory7,IDWriteFactory6,IDWriteFactory5,IDWriteFactory4,IDWriteFactory3,IDWriteFactory2,IDWriteFactory1,IDWriteFactory>,IDWriteFactory8,ClientSideCacheContext,IDWritePrivateFactory1,IDWritePrivateFactoryForGdi,IDWritePrivateFactoryForSettings,IDWriteOldPrivateFactory,IDWriteDebugFactory>::LogEvent<>(
        (__int64)this,
        0x656D61536366LL);
    }
    if ( v23 )
      FontCollectionBuilder::`scalar deleting destructor'(v23, v26);
  }
  if ( v6 )
  {
    EnterCriticalSection(&RecentFontCache::globalLock_);
    List<RecentFontCache::FontList,RecentFontCache::FontInstance>::DeleteElements(&RecentFontCache::globalFonts_);
    ++RecentFontCache::globalInvalidCount_;
    LeaveCriticalSection(&RecentFontCache::globalLock_);
    ChildComPtr<DWriteFontSet>::Clear((char *)this + 656);
    ChildComPtr<DWriteFontCollection>::Clear((char *)this + 664);
    ChildComPtr<DWriteFontCollection>::Clear((char *)this + 672);
    ChildComPtr<DWriteFontCollection>::Clear((char *)this + 680);
    ChildComPtr<DWriteFontCollection>::Clear((char *)this + 688);
    ChildComPtr<DWriteFontCollection>::Clear((char *)this + 696);
  }
  ReleaseReference<CacheReader>(v8);
}

```

## disassembly

```asm
0x18012a264  mov     [rsp-8+arg_10], r8b
0x18012a269  mov     [rsp-8+arg_8], rdx
0x18012a26e  push    rbp
0x18012a26f  push    rbx
0x18012a270  push    rsi
0x18012a271  push    rdi
0x18012a272  push    r12
0x18012a274  push    r13
0x18012a276  push    r14
0x18012a278  push    r15
0x18012a27a  lea     rbp, [rsp-1Fh]
0x18012a27f  sub     rsp, 0D8h
0x18012a286  mov     bl, r8b
0x18012a289  mov     r14, rcx
0x18012a28c  lea     rsi, [rcx+8]
0x18012a290  lea     rdx, [rbp+57h+Block]
0x18012a294  mov     rcx, rsi
0x18012a297  call    ?TryGetSystemCache@ClientSideCacheContext@@QEAA?AV?$IntrusivePtr@VCacheReader@@@@XZ; ClientSideCacheContext::TryGetSystemCache(void)
0x18012a29c  nop
0x18012a29d  xor     r12b, r12b
0x18012a2a0  mov     byte ptr [rbp+57h+arg_8], r12b
0x18012a2a4  lea     r15, [r14+288h]
0x18012a2ab  mov     r13, [rbp+57h+Block]
0x18012a2af  test    r13, r13
0x18012a2b2  jz      short loc_18012A2DA
0x18012a2b4  lea     r12, [r14+2D0h]
0x18012a2bb  cmp     qword ptr [r15], 0
0x18012a2bf  jz      loc_18012A385
0x18012a2c5  mov     rax, [r13+30h]
0x18012a2c9  mov     ecx, [rax+20h]
0x18012a2cc  cmp     [r12], ecx
0x18012a2d0  jnz     loc_18012A385
0x18012a2d6  mov     r12b, byte ptr [rbp+57h+arg_8]
0x18012a2da  cmp     qword ptr [r15], 0
0x18012a2de  jz      loc_18012A5D2
0x18012a2e4  test    bl, bl
0x18012a2e6  jnz     loc_18012A5D2
0x18012a2ec  test    r12b, r12b
0x18012a2ef  jnz     short loc_18012A30C
0x18012a2f1  mov     rcx, r13; Block
0x18012a2f4  add     rsp, 0D8h
0x18012a2fb  pop     r15
0x18012a2fd  pop     r14
0x18012a2ff  pop     r13
0x18012a301  pop     r12
0x18012a303  pop     rdi
0x18012a304  pop     rsi
0x18012a305  pop     rbx
0x18012a306  pop     rbp
0x18012a307  jmp     ??$ReleaseReference@VCacheReader@@@@YAXPEAVCacheReader@@@Z; ReleaseReference<CacheReader>(CacheReader *)
0x18012a30c  lea     rcx, ?globalLock_@RecentFontCache@@0VLock@@A; lpCriticalSection
0x18012a313  call    cs:__imp_EnterCriticalSection
0x18012a319  lea     rcx, ?globalFonts_@RecentFontCache@@0VFontList@1@A; RecentFontCache::FontList RecentFontCache::globalFonts_
0x18012a320  call    ?DeleteElements@?$List@VFontList@RecentFontCache@@UFontInstance@2@@@QEAAXXZ; List<RecentFontCache::FontList,RecentFontCache::FontInstance>::DeleteElements(void)
0x18012a325  inc     cs:?globalInvalidCount_@RecentFontCache@@0IA; uint RecentFontCache::globalInvalidCount_
0x18012a32b  lea     rcx, ?globalLock_@RecentFontCache@@0VLock@@A; lpCriticalSection
0x18012a332  call    cs:__imp_LeaveCriticalSection
0x18012a338  lea     rcx, [r14+290h]
0x18012a33f  call    ?Clear@?$ChildComPtr@VDWriteFontSet@@@@QEAAXXZ; ChildComPtr<DWriteFontSet>::Clear(void)
0x18012a344  lea     rcx, [r14+298h]
0x18012a34b  call    ?Clear@?$ChildComPtr@VDWriteFontCollection@@@@QEAAXXZ; ChildComPtr<DWriteFontCollection>::Clear(void)
0x18012a350  lea     rcx, [r14+2A0h]
0x18012a357  call    ?Clear@?$ChildComPtr@VDWriteFontCollection@@@@QEAAXXZ; ChildComPtr<DWriteFontCollection>::Clear(void)
0x18012a35c  lea     rcx, [r14+2A8h]
0x18012a363  call    ?Clear@?$ChildComPtr@VDWriteFontCollection@@@@QEAAXXZ; ChildComPtr<DWriteFontCollection>::Clear(void)
0x18012a368  lea     rcx, [r14+2B0h]
0x18012a36f  call    ?Clear@?$ChildComPtr@VDWriteFontCollection@@@@QEAAXXZ; ChildComPtr<DWriteFontCollection>::Clear(void)
0x18012a374  lea     rcx, [r14+2B8h]
0x18012a37b  call    ?Clear@?$ChildComPtr@VDWriteFontCollection@@@@QEAAXXZ; ChildComPtr<DWriteFontCollection>::Clear(void)
0x18012a380  jmp     loc_18012A2F1
0x18012a385  xor     esi, esi
0x18012a387  cmp     [r15], rsi
0x18012a38a  jnz     loc_18012A4E7
0x18012a390  mov     rdx, 74696E496366h
0x18012a39a  mov     rcx, r14
0x18012a39d  call    ??$LogEvent@$$V@?$EventSource@V?$ComInterfaceList@VDWriteFactory@@UIBaseCacheContext@@UIDWritePrivateFactory1@@UIDWritePrivateFactoryForGdi@@UIDWritePrivateFactoryForSettings@@UIDWriteOldPrivateFactory@@UIDWriteDebugFactory@@UIDWriteFactory8@@UIDWriteFactory7@@UIDWriteFactory6@@UIDWriteFactory5@@UIDWriteFactory4@@UIDWriteFactory3@@UIDWriteFactory2@@UIDWriteFactory1@@UIDWriteFactory@@@@UIDWriteFactory8@@VClientSideCacheContext@@UIDWritePrivateFactory1@@UIDWritePrivateFactoryForGdi@@UIDWritePrivateFactoryForSettings@@UIDWriteOldPrivateFactory@@UIDWriteDebugFactory@@@@QEBAXVEventTag@@@Z; EventSource<ComInterfaceList<DWriteFactory,IBaseCacheContext,IDWritePrivateFactory1,IDWritePrivateFactoryForGdi,IDWritePrivateFactoryForSettings,IDWriteOldPrivateFactory,IDWriteDebugFactory,IDWriteFactory8,IDWriteFactory7,IDWriteFactory6,IDWriteFactory5,IDWriteFactory4,IDWriteFactory3,IDWriteFactory2,IDWriteFactory1,IDWriteFactory>,IDWriteFactory8,ClientSideCacheContext,IDWritePrivateFactory1,IDWritePrivateFactoryForGdi,IDWritePrivateFactoryForSettings,IDWriteOldPrivateFactory,IDWriteDebugFactory>::LogEvent<>(EventTag)
0x18012a3a2  mov     [rbp+57h+arg_8], rsi
0x18012a3a6  mov     ebx, 4
0x18012a3ab  mov     r8d, ebx; unsigned int
0x18012a3ae  xor     edx, edx; unsigned __int64
0x18012a3b0  lea     rdi, qword_180374320
0x18012a3b7  mov     rcx, rdi; void *
0x18012a3ba  call    ?HashBlob@@YAIPEBX_KI@Z; HashBlob(void const *,unsigned __int64,uint)
0x18012a3bf  mov     r8d, eax; unsigned int
0x18012a3c2  lea     edx, [rbx-2]; unsigned __int64
0x18012a3c5  lea     rcx, [rbp+57h+arg_8]; unsigned int *
0x18012a3c9  call    ?HashWords@@YAIPEBI_KI@Z; HashWords(uint const *,unsigned __int64,uint)
0x18012a3ce  mov     [rbp+57h+var_78], eax
0x18012a3d1  mov     [rbp+57h+var_74], ebx
0x18012a3d4  lea     rax, ??_7FontCollectionElementKey@@6B@; const FontCollectionElementKey::`vftable'
0x18012a3db  mov     [rbp+57h+var_80], rax
0x18012a3df  mov     [rbp+57h+var_70], rdi
0x18012a3e3  mov     [rbp+57h+var_68], esi
0x18012a3e6  mov     [rbp+57h+var_60], rsi
0x18012a3ea  mov     [rbp+57h+var_58], r14
0x18012a3ee  mov     [rbp+57h+var_50], rsi
0x18012a3f2  mov     [rbp+57h+var_C0], rsi
0x18012a3f6  mov     [rbp+57h+var_B8], esi
0x18012a3f9  mov     [rbp+57h+var_B0], rsi
0x18012a3fd  mov     [rbp+57h+var_A8], esi
0x18012a400  mov     [rbp+57h+var_A0], rsi
0x18012a404  mov     [rbp+57h+var_98], esi
0x18012a407  mov     [rbp+57h+var_90], rsi
0x18012a40b  mov     [rbp+57h+var_88], si
0x18012a40f  lea     rax, [rbp+57h+var_C0]
0x18012a413  mov     [rsp+110h+var_D8], rax; struct CachedElementData *
0x18012a418  lea     rax, [rbp+57h+var_80]
0x18012a41c  mov     [rsp+110h+var_E0], rax; struct IElementKey *
0x18012a421  mov     rax, [r13+10h]
0x18012a425  mov     [rsp+110h+var_E8], rax; void *
0x18012a42a  mov     rax, [r13+40h]
0x18012a42e  mov     [rsp+110h+var_F0], rax; struct HashElement *
0x18012a433  mov     r9, [r13+38h]; unsigned int *
0x18012a437  mov     r8, [r13+30h]; struct CacheHeader *
0x18012a43b  xor     edx, edx; bool
0x18012a43d  mov     rcx, r13; struct ICacheReference *
0x18012a440  call    ?FindElementCommon@@YA_NPEAVICacheReference@@_NAEBUCacheHeader@@PEBIPEBUHashElement@@PEBXAEBVIElementKey@@PEAUCachedElementData@@@Z; FindElementCommon(ICacheReference *,bool,CacheHeader const &,uint const *,HashElement const *,void const *,IElementKey const &,CachedElementData *)
0x18012a445  test    al, al
0x18012a447  jz      loc_18012A515
0x18012a44d  mov     rbx, [rbp+57h+var_B0]
0x18012a451  mov     edi, [rbp+57h+var_A8]
0x18012a454  mov     ecx, 78h ; 'x'; Size
0x18012a459  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18012a45e  mov     rsi, rax
0x18012a461  mov     [rbp+57h+arg_8], rax
0x18012a465  mov     qword ptr [rbp+57h+pExceptionObject], rbx
0x18012a469  mov     dword ptr [rbp+57h+pExceptionObject+8], edi
0x18012a46c  mov     ecx, [rbp+57h+var_A4]
0x18012a46f  mov     dword ptr [rbp+57h+pExceptionObject+0Ch], ecx
0x18012a472  movaps  xmm0, [rbp+57h+pExceptionObject]
0x18012a476  movdqa  [rbp+57h+pExceptionObject], xmm0
0x18012a47b  lea     rcx, [rax+8]
0x18012a47f  mov     r8, [rbp+57h+var_90]
0x18012a483  lea     rdx, [rbp+57h+pExceptionObject]
0x18012a487  call    ??0FontSet@@QEAA@VFontSetRegion@@PEAVICacheReference@@@Z; FontSet::FontSet(FontSetRegion,ICacheReference *)
0x18012a48c  mov     [rsi+68h], r14
0x18012a490  mov     dword ptr [rsi+74h], 0
0x18012a497  lea     rax, ??_7?$ChildComObject@VDWriteFontSet@@@@6B@; const ChildComObject<DWriteFontSet>::`vftable'
0x18012a49e  mov     [rsi], rax
0x18012a4a1  mov     rdx, rsi
0x18012a4a4  mov     rcx, r15
0x18012a4a7  call    ??4?$ChildComPtr@VDWriteFontSet@@@@QEAAAEAV0@PEAV?$ChildComObject@VDWriteFontSet@@@@@Z; ChildComPtr<DWriteFontSet>::operator=(ChildComObject<DWriteFontSet> *)
0x18012a4ac  mov     rax, [r13+30h]
0x18012a4b0  mov     ecx, [rax+20h]
0x18012a4b3  mov     [r12], ecx
0x18012a4b7  mov     r12b, 1
0x18012a4ba  mov     rcx, [r15]
0x18012a4bd  add     rcx, 8
0x18012a4c1  call    ?GetMissingRequiredFonts@FontSetCache@@SA?AW4RequiredFonts@1@AEBVFontSet@@@Z; FontSetCache::GetMissingRequiredFonts(FontSet const &)
0x18012a4c6  movzx   r9d, al
0x18012a4ca  test    al, al
0x18012a4cc  jnz     loc_18012A58C
0x18012a4d2  lea     rcx, [rbp+57h+var_90]
0x18012a4d6  call    ??1?$IntrusivePtr@VICacheReference@@@@QEAA@XZ; IntrusivePtr<ICacheReference>::~IntrusivePtr<ICacheReference>(void)
0x18012a4db  lea     rsi, [r14+8]
0x18012a4df  mov     bl, [rbp+57h+arg_10]
0x18012a4e2  jmp     loc_18012A2DA
0x18012a4e7  lea     rdx, aFcupdate; "fcUpdate"
0x18012a4ee  lea     rcx, [rbp+57h+arg_8]; this
0x18012a4f2  call    ??0EventTag@@QEAA@AEAY08$$CBD@Z; EventTag::EventTag(char const (&)[9])
0x18012a4f7  mov     rdx, [rax]
0x18012a4fa  jmp     loc_18012A39A
0x18012a4ff  test    rdi, rdi
0x18012a502  jz      loc_18012A2EC
0x18012a508  mov     rcx, rdi; this
0x18012a50b  call    ??_GFontCollectionBuilder@@QEAAPEAXI@Z; FontCollectionBuilder::`scalar deleting destructor'(uint)
0x18012a510  jmp     loc_18012A2EC
0x18012a515  lea     rdx, aSyscache; "syscache"
0x18012a51c  lea     rcx, [rbp+57h+arg_8]; this
0x18012a520  call    ??0EventTag@@QEAA@AEAY08$$CBD@Z; EventTag::EventTag(char const (&)[9])
0x18012a525  mov     rbx, [rax]
0x18012a528  mov     rdi, [r13+10h]
0x18012a52c  xor     r8d, r8d; unsigned int
0x18012a52f  mov     edx, 88985007h; int
0x18012a534  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18012a538  call    ??0Exception@@IEAA@HI@Z; Exception::Exception(int,uint)
0x18012a53d  mov     qword ptr [rbp+57h+pExceptionObject+8], rdi
0x18012a541  mov     rdx, 79726F74636146h
0x18012a54b  mov     r8, 726F727265h
0x18012a555  lea     rcx, [r14+208h]
0x18012a55c  mov     dword ptr [rsp+110h+var_E8], 19Ah
0x18012a564  mov     [rsp+110h+var_F0], rbx
0x18012a569  mov     r9d, dword ptr [rbp+57h+pExceptionObject]
0x18012a56d  call    ??$LogEvent@JVEventTag@@I@EventLogger@@QEBAXVEventTag@@0J0I@Z; EventLogger::LogEvent<long,EventTag,uint>(EventTag,EventTag,long,EventTag,uint)
0x18012a572  movaps  xmm0, [rbp+57h+pExceptionObject]
0x18012a576  movdqa  [rbp+57h+pExceptionObject], xmm0
0x18012a57b  lea     rdx, _TI2?AVInvalidCacheDataException@@; pThrowInfo
0x18012a582  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18012a586  call    _CxxThrowException_0
0x18012a58c  mov     rax, 746E6F46737973h
0x18012a596  mov     rdx, 79726F74636146h
0x18012a5a0  mov     r8, 726F727265h
0x18012a5aa  lea     rcx, [r14+208h]
0x18012a5b1  mov     dword ptr [rsp+110h+var_E0], r9d
0x18012a5b6  mov     [rsp+110h+var_F0], rax
0x18012a5bb  call    ??$LogEvent@JVEventTag@@II@EventLogger@@QEBAXVEventTag@@0J0II@Z; EventLogger::LogEvent<long,EventTag,uint,uint>(EventTag,EventTag,long,EventTag,uint,uint)
0x18012a5c0  mov     edx, [r13+28h]; unsigned int
0x18012a5c4  mov     rcx, [r13+10h]; pvAddress
0x18012a5c8  call    ?RegisterMemoryForCrashDumps@@YAXPEAXI@Z; RegisterMemoryForCrashDumps(void *,uint)
0x18012a5cd  jmp     loc_18012A4D2
0x18012a5d2  mov     rdx, 6D756E456366h
0x18012a5dc  mov     rcx, r14
0x18012a5df  call    ??$LogEvent@$$V@?$EventSource@V?$ComInterfaceList@VDWriteFactory@@UIBaseCacheContext@@UIDWritePrivateFactory1@@UIDWritePrivateFactoryForGdi@@UIDWritePrivateFactoryForSettings@@UIDWriteOldPrivateFactory@@UIDWriteDebugFactory@@UIDWriteFactory8@@UIDWriteFactory7@@UIDWriteFactory6@@UIDWriteFactory5@@UIDWriteFactory4@@UIDWriteFactory3@@UIDWriteFactory2@@UIDWriteFactory1@@UIDWriteFactory@@@@UIDWriteFactory8@@VClientSideCacheContext@@UIDWritePrivateFactory1@@UIDWritePrivateFactoryForGdi@@UIDWritePrivateFactoryForSettings@@UIDWriteOldPrivateFactory@@UIDWriteDebugFactory@@@@QEBAXVEventTag@@@Z; EventSource<ComInterfaceList<DWriteFactory,IBaseCacheContext,IDWritePrivateFactory1,IDWritePrivateFactoryForGdi,IDWritePrivateFactoryForSettings,IDWriteOldPrivateFactory,IDWriteDebugFactory,IDWriteFactory8,IDWriteFactory7,IDWriteFactory6,IDWriteFactory5,IDWriteFactory4,IDWriteFactory3,IDWriteFactory2,IDWriteFactory1,IDWriteFactory>,IDWriteFactory8,ClientSideCacheContext,IDWritePrivateFactory1,IDWritePrivateFactoryForGdi,IDWritePrivateFactoryForSettings,IDWriteOldPrivateFactory,IDWriteDebugFactory>::LogEvent<>(EventTag)
0x18012a5e4  mov     rbx, [r15]
0x18012a5e7  mov     rax, [rsi]
0x18012a5ea  mov     rcx, rsi
0x18012a5ed  mov     rax, [rax+28h]
0x18012a5f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012a5f6  lea     rcx, [rbx+8]
0x18012a5fa  neg     rbx
0x18012a5fd  sbb     r9, r9
0x18012a600  and     r9, rcx; FontSet *
0x18012a603  mov     r8, rax; int
0x18012a606  mov     rdx, rsi; int
0x18012a609  lea     rcx, [rbp+57h+arg_18]; int
0x18012a60d  call    ?CreateFontCollectionBuilderIfNeeded@SystemFontCollectionLoader@@SA?AV?$ScopedPtr@VFontCollectionBuilder@@@@PEAUIBaseCacheContext@@AEBVFontFileLoaderManager@@PEBVFontSet@@@Z; SystemFontCollectionLoader::CreateFontCollectionBuilderIfNeeded(IBaseCacheContext *,FontFileLoaderManager const &,FontSet const *)
0x18012a612  nop
0x18012a613  mov     rdi, [rbp+57h+arg_18]
0x18012a617  test    rdi, rdi
0x18012a61a  jz      short loc_18012A694
0x18012a61c  lea     rdx, aFccreate; "fcCreate"
0x18012a623  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18012a627  call    ??0EventTag@@QEAA@AEAY08$$CBD@Z; EventTag::EventTag(char const (&)[9])
0x18012a62c  mov     rdx, [rax]
0x18012a62f  mov     rcx, r14
0x18012a632  call    ??$LogEvent@$$V@?$EventSource@V?$ComInterfaceList@VDWriteFactory@@UIBaseCacheContext@@UIDWritePrivateFactory1@@UIDWritePrivateFactoryForGdi@@UIDWritePrivateFactoryForSettings@@UIDWriteOldPrivateFactory@@UIDWriteDebugFactory@@UIDWriteFactory8@@UIDWriteFactory7@@UIDWriteFactory6@@UIDWriteFactory5@@UIDWriteFactory4@@UIDWriteFactory3@@UIDWriteFactory2@@UIDWriteFactory1@@UIDWriteFactory@@@@UIDWriteFactory8@@VClientSideCacheContext@@UIDWritePrivateFactory1@@UIDWritePrivateFactoryForGdi@@UIDWritePrivateFactoryForSettings@@UIDWriteOldPrivateFactory@@UIDWriteDebugFactory@@@@QEBAXVEventTag@@@Z; EventSource<ComInterfaceList<DWriteFactory,IBaseCacheContext,IDWritePrivateFactory1,IDWritePrivateFactoryForGdi,IDWritePrivateFactoryForSettings,IDWriteOldPrivateFactory,IDWriteDebugFactory,IDWriteFactory8,IDWriteFactory7,IDWriteFactory6,IDWriteFactory5,IDWriteFactory4,IDWriteFactory3,IDWriteFactory2,IDWriteFactory1,IDWriteFactory>,IDWriteFactory8,ClientSideCacheContext,IDWritePrivateFactory1,IDWritePrivateFactoryForGdi,IDWritePrivateFactoryForSettings,IDWriteOldPrivateFactory,IDWriteDebugFactory>::LogEvent<>(EventTag)
0x18012a637  mov     r8, rsi
0x18012a63a  lea     rdx, [rbp+57h+arg_8]
0x18012a63e  mov     rcx, rdi
0x18012a641  call    ?CreateFontSetRegionInMemory@FontSetBuilder@@QEAA?AV?$RefCountedArray@E@@PEAUIBaseCacheContext@@@Z; FontSetBuilder::CreateFontSetRegionInMemory(IBaseCacheContext *)
0x18012a646  nop
0x18012a647  mov     ecx, 78h ; 'x'; Size
0x18012a64c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18012a651  mov     rbx, rax
0x18012a654  mov     qword ptr [rbp+57h+pExceptionObject], rax
0x18012a658  lea     r8, [rbp+57h+arg_8]
0x18012a65c  mov     rdx, r14
0x18012a65f  mov     rcx, rax
0x18012a662  call    ??0DWriteFontSet@@IEAA@PEAVDWriteFactory@@PEAV?$RefCountedArray@E@@@Z; DWriteFontSet::DWriteFontSet(DWriteFactory *,RefCountedArray<uchar> *)
0x18012a667  mov     dword ptr [rbx+74h], 0
0x18012a66e  lea     rax, ??_7?$ChildComObject@VDWriteFontSet@@@@6B@; const ChildComObject<DWriteFontSet>::`vftable'
0x18012a675  mov     [rbx], rax
0x18012a678  mov     rdx, rbx
0x18012a67b  mov     rcx, r15
0x18012a67e  call    ??4?$ChildComPtr@VDWriteFontSet@@@@QEAAAEAV0@PEAV?$ChildComObject@VDWriteFontSet@@@@@Z; ChildComPtr<DWriteFontSet>::operator=(ChildComObject<DWriteFontSet> *)
0x18012a683  mov     r12b, 1
0x18012a686  lea     rcx, [rbp+57h+arg_8]; this
0x18012a68a  call    ??1RefCountedArrayImpl@@QEAA@XZ; RefCountedArrayImpl::~RefCountedArrayImpl(void)
0x18012a68f  jmp     loc_18012A4FF
0x18012a694  mov     rdx, 656D61536366h
0x18012a69e  mov     rcx, r14
0x18012a6a1  call    ??$LogEvent@$$V@?$EventSource@V?$ComInterfaceList@VDWriteFactory@@UIBaseCacheContext@@UIDWritePrivateFactory1@@UIDWritePrivateFactoryForGdi@@UIDWritePrivateFactoryForSettings@@UIDWriteOldPrivateFactory@@UIDWriteDebugFactory@@UIDWriteFactory8@@UIDWriteFactory7@@UIDWriteFactory6@@UIDWriteFactory5@@UIDWriteFactory4@@UIDWriteFactory3@@UIDWriteFactory2@@UIDWriteFactory1@@UIDWriteFactory@@@@UIDWriteFactory8@@VClientSideCacheContext@@UIDWritePrivateFactory1@@UIDWritePrivateFactoryForGdi@@UIDWritePrivateFactoryForSettings@@UIDWriteOldPrivateFactory@@UIDWriteDebugFactory@@@@QEBAXVEventTag@@@Z; EventSource<ComInterfaceList<DWriteFactory,IBaseCacheContext,IDWritePrivateFactory1,IDWritePrivateFactoryForGdi,IDWritePrivateFactoryForSettings,IDWriteOldPrivateFactory,IDWriteDebugFactory,IDWriteFactory8,IDWriteFactory7,IDWriteFactory6,IDWriteFactory5,IDWriteFactory4,IDWriteFactory3,IDWriteFactory2,IDWriteFactory1,IDWriteFactory>,IDWriteFactory8,ClientSideCacheContext,IDWritePrivateFactory1,IDWritePrivateFactoryForGdi,IDWritePrivateFactoryForSettings,IDWriteOldPrivateFactory,IDWriteDebugFactory>::LogEvent<>(EventTag)
0x18012a6a6  jmp     loc_18012A4FF
```
