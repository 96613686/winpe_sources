# Microsoft::Windows::Performance::CImageIdEventTraceExtender::CImageIdEventTraceExtender(void)

- ea: `0x180011618`
- end: `0x180011b3d`
- name: `??0CImageIdEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ`
- size: `1317`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CImageIdEventTraceExtender *__hidden this)`
- caller_count: `1`
- callee_count: `31`
- tags: `broker_com_uri`

## callers

- `0x180014a00`

## callees

- `0x180001800`
- `0x180008044`
- `0x1800092fc`
- `0x18000938c`
- `0x180009a4c`
- `0x180009c3c`
- `0x18000ab4c`
- `0x18000acd0`
- `0x18000c1fc`
- `0x18000c6e4`
- `0x18000c9a8`
- `0x180010f74`
- `0x1800111c0`
- `0x180011560`
- `0x180011618`
- `0x180011b44`
- `0x180011b9c`
- `0x180011bc0`
- `0x180014240`
- `0x180014508`
- `0x1800145bc`
- `0x180014dc0`
- `0x180014dec`
- `0x1800151f8`
- `0x180015f74`
- `0x180016c10`
- `0x180017f18`
- `0x180018514`
- `0x1800185dc`
- `0x180018644`
- `0x180018678`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011959`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011959`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180011949`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180011949`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800119d3`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180011a12`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800119d3`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180011a12`

## string_xrefs

- `0x1800117b9`: `XPERF_EmbeddedPdbPath`
- `0x1800117e8`: `_NT_SYMBOL_PATH`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
Microsoft::Windows::Performance::CImageIdEventTraceExtender *__fastcall Microsoft::Windows::Performance::CImageIdEventTraceExtender::CImageIdEventTraceExtender(
        Microsoft::Windows::Performance::CImageIdEventTraceExtender *this)
{
  LPCWSTR *v2; // rsi
  unsigned int v3; // edx
  __int64 v4; // r8
  __int64 v5; // rbx
  __int64 v6; // rdx
  int *v7; // rdi
  __int64 v8; // rbx
  int v9; // edi
  __int64 v10; // rdx
  signed int LastError; // eax
  unsigned __int64 v12; // rax
  DWORD FullPathNameW; // eax
  DWORD v14; // ebx
  WCHAR *v15; // rax
  ATL::CStringData *v16; // rcx
  int *v18; // rbx
  ATL::CStringData *v19; // r12
  __int64 Manager; // rax
  ATL::CStringData *v21; // rdi
  int *v22; // r15
  __int64 v23; // rbx
  int *v24; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v25; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v26; // [rsp+40h] [rbp-C0h] BYREF
  int v27; // [rsp+48h] [rbp-B8h]
  __int128 v28; // [rsp+50h] [rbp-B0h] BYREF
  int v29; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v30; // [rsp+68h] [rbp-98h] BYREF
  __int64 v31; // [rsp+78h] [rbp-88h]
  int v32; // [rsp+80h] [rbp-80h]
  __int64 v33; // [rsp+88h] [rbp-78h]
  int v34; // [rsp+90h] [rbp-70h]
  Microsoft::Windows::Performance::CImageIdEventTraceExtender *v35; // [rsp+98h] [rbp-68h]
  _BYTE v36[80]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR Buffer[264]; // [rsp+F0h] [rbp-10h] BYREF

  v35 = this;
  v27 = 0;
  *((_DWORD *)this + 6) = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *(_QWORD *)this = &Microsoft::Windows::Performance::CImageIdEventTraceExtender::`vftable';
  *((_DWORD *)this + 8) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_DWORD *)this + 12) = 0;
  *((_QWORD *)this + 7) = 0;
  Performance::NtImagePathDecoder::CLocalNtImagePathDecoder::CLocalNtImagePathDecoder((Microsoft::Windows::Performance::CImageIdEventTraceExtender *)((char *)this + 64));
  *((_QWORD *)this + 23) = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((char *)this + 192);
  *((_WORD *)this + 100) = 0;
  *((_BYTE *)this + 202) = 0;
  *(_QWORD *)&v28 = (char *)this + 208;
  *((_QWORD *)this + 26) = 0;
  *((_QWORD *)this + 27) = 0;
  std::list<Microsoft::Windows::Performance::CCvDDCache::CCvDD>::_Alloc_sentinel_and_proxy((char *)this + 208);
  *((_QWORD *)this + 28) = 0;
  *((_QWORD *)this + 29) = 0;
  std::_Tree<std::_Tmap_traits<unsigned long,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>,0>>::_Alloc_sentinel_and_proxy();
  std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>((char *)this + 240);
  *((_QWORD *)this + 32) = 0;
  *((_QWORD *)this + 33) = 0;
  std::_Tree<std::_Tset_traits<unsigned short const *,std::less<unsigned short const *>,std::allocator<unsigned short const *>,0>>::_Alloc_sentinel_and_proxy();
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((char *)this + 272);
  *((_QWORD *)this + 35) = 0;
  *((_DWORD *)this + 72) = 0;
  *((_BYTE *)this + 296) = 0;
  *((_QWORD *)this + 38) = 0;
  *((_QWORD *)this + 39) = 0;
  *((_QWORD *)this + 40) = 0;
  v2 = (LPCWSTR *)((char *)this + 328);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((char *)this + 328);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((char *)this + 336);
  *((_QWORD *)this + 43) = 0;
  *((_QWORD *)this + 44) = 0;
  *((_QWORD *)this + 45) = 0;
  *((_QWORD *)this + 46) = 0;
  Microsoft::Windows::Performance::CErrorEvent::CErrorEvent(
    (Microsoft::Windows::Performance::CImageIdEventTraceExtender *)((char *)this + 376),
    v3);
  if ( !(unsigned __int8)ATL::CAutoVectorPtr<_CVDD>::Allocate((char *)this + 344, 2)
    || !(unsigned __int8)ATL::CAutoVectorPtr<unsigned long>::Allocate((char *)this + 352, 2)
    || !(unsigned __int8)ATL::CAutoVectorPtr<unsigned __int64>::Allocate((char *)this + 360, 2) )
  {
    ATL::AtlThrowImpl(-2147024882);
  }
  *((_DWORD *)this + 92) = 2;
  if ( !(unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::GetEnvironmentVariableW(
                        (char *)this + 328,
                        L"XPERF_EmbeddedPdbPath")
    || !*((_DWORD *)*v2 - 4) )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v25);
    if ( (unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::GetEnvironmentVariableW(
                         &v25,
                         L"_NT_SYMBOL_PATH") )
    {
      v30 = 0;
      v31 = 0;
      v32 = 0;
      v33 = 0;
      v34 = 1;
      v29 = 0;
      if ( (unsigned int)ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Parse(&v29) )
        ATL::AtlThrowImpl(-2147024882);
      ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW>::CAtlREMatchContext<ATL::CAtlRECharTraitsW>(v36);
      LODWORD(v24) = 0;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v26);
      v5 = v26;
      while ( 1 )
      {
        v6 = *(_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Tokenize(
                          &v25,
                          &v28,
                          v4,
                          &v24);
        v7 = (int *)(v5 - 24);
        if ( v6 - 24 != v5 - 24 )
        {
          if ( v7[4] >= 0 && *(_QWORD *)(v6 - 24) == *(_QWORD *)v7 )
          {
            v8 = ((__int64 (*)(void))ATL::CSimpleStringT<unsigned short,0>::CloneData)();
            ATL::CStringData::Release((ATL::CStringData *)v7);
            v5 = v8 + 24;
            v26 = v5;
          }
          else
          {
            ATL::CSimpleStringT<unsigned short,0>::SetString(&v26, v6, *(unsigned int *)(v6 - 16));
            v5 = v26;
          }
        }
        v9 = *(_DWORD *)(v5 - 16);
        ATL::CStringData::Release((ATL::CStringData *)(v28 - 24));
        if ( !v9 )
          break;
        if ( (unsigned int)ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Match(&v29, v5, v36, 0) )
        {
          v28 = 0;
          ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW>::GetMatch(v36, v10, &v28);
          ATL::CSimpleStringT<unsigned short,0>::SetString(
            (char *)this + 328,
            v28,
            (__int64)(*((_QWORD *)&v28 + 1) - v28) >> 1);
          break;
        }
      }
      ATL::CStringData::Release((ATL::CStringData *)(v5 - 24));
      ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW>::~CAtlREMatchContext<ATL::CAtlRECharTraitsW>(v36);
      ATL::CAtlArray<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION,ATL::CElementTraits<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION>>::~CAtlArray<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION,ATL::CElementTraits<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION>>(&v30);
    }
    if ( !*((_DWORD *)*v2 - 4) )
    {
      if ( !GetSystemWindowsDirectoryW(Buffer, 0x105u) )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        ATL::AtlThrowImpl(LastError);
      }
      v12 = -1;
      do
        ++v12;
      while ( Buffer[v12] );
      if ( v12 < 2 || Buffer[1] != 58 )
        ATL::AtlThrowImpl(-2147418113);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        (char *)this + 328,
        L"%wc:\\Symbols",
        Buffer[0]);
    }
    ATL::CStringData::Release((ATL::CStringData *)(v25 - 24));
  }
  if ( *((_DWORD *)*v2 - 4) )
  {
    FullPathNameW = GetFullPathNameW(*v2, 0, 0, 0);
    if ( FullPathNameW )
    {
      v14 = FullPathNameW + 1;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v24);
      ATL::CSimpleStringT<unsigned short,0>::PrepareWrite(&v24, v14);
      v15 = (WCHAR *)ATL::CSimpleStringT<unsigned short,0>::GetBuffer(&v24);
      if ( GetFullPathNameW(*v2, v14, v15, 0) )
      {
        ATL::CSimpleStringT<unsigned short,0>::ReleaseBuffer(&v24);
        v18 = v24;
        v19 = (ATL::CStringData *)(v24 - 6);
        if ( *(v24 - 4) < 0 )
          ATL::AtlThrowImpl(-2147024809);
        if ( *(_WORD *)v24 != 92 )
        {
          Manager = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::GetManager(&v24);
          ATL::CSimpleStringT<unsigned short,0>::CSimpleStringT<unsigned short,0>(&v25, Manager);
          v27 = 1;
          ATL::CSimpleStringT<unsigned short,0>::Concatenate(&v25, L"\\\\?\\", 4, v18, *(v18 - 4));
          v21 = (ATL::CStringData *)(v25 - 24);
          v22 = (int *)(*v2 - 12);
          if ( (int *)(v25 - 24) != v22 )
          {
            if ( v22[4] >= 0 && *(_QWORD *)v21 == *(_QWORD *)v22 )
            {
              v23 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v25 - 24);
              ATL::CStringData::Release((ATL::CStringData *)v22);
              *v2 = (LPCWSTR)(v23 + 24);
            }
            else
            {
              ATL::CSimpleStringT<unsigned short,0>::SetString((char *)this + 328, v25, *(unsigned int *)(v25 - 16));
            }
          }
          ATL::CStringData::Release(v21);
        }
        v16 = v19;
      }
      else
      {
        v16 = (ATL::CStringData *)(v24 - 6);
      }
      ATL::CStringData::Release(v16);
    }
  }
  return this;
}

```

## disassembly

```asm
0x180011618  push    rbp
0x18001161a  push    rbx
0x18001161b  push    rsi
0x18001161c  push    rdi
0x18001161d  push    r12
0x18001161f  push    r13
0x180011621  push    r14
0x180011623  push    r15
0x180011625  lea     rbp, [rsp-218h]
0x18001162d  sub     rsp, 318h
0x180011634  mov     rax, cs:__security_cookie
0x18001163b  xor     rax, rsp
0x18001163e  mov     [rbp+250h+var_50], rax
0x180011645  mov     r14, rcx
0x180011648  mov     [rbp+250h+var_2B8], rcx
0x18001164c  xor     r13d, r13d
0x18001164f  mov     [rsp+350h+var_308], r13d
0x180011654  mov     [rcx+18h], r13d
0x180011658  mov     [rcx+8], r13
0x18001165c  mov     [rcx+10h], r13
0x180011660  lea     rax, ??_7CImageIdEventTraceExtender@Performance@Windows@Microsoft@@6B@; const Microsoft::Windows::Performance::CImageIdEventTraceExtender::`vftable'
0x180011667  mov     [rcx], rax
0x18001166a  mov     [rcx+20h], r13d
0x18001166e  mov     [rcx+28h], r13
0x180011672  mov     [rcx+30h], r13d
0x180011676  mov     [rcx+38h], r13
0x18001167a  add     rcx, 40h ; '@'; this
0x18001167e  call    ??0CLocalNtImagePathDecoder@NtImagePathDecoder@Performance@@QEAA@XZ; Performance::NtImagePathDecoder::CLocalNtImagePathDecoder::CLocalNtImagePathDecoder(void)
0x180011683  nop
0x180011684  mov     [r14+0B8h], r13
0x18001168b  lea     rcx, [r14+0C0h]
0x180011692  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180011697  nop
0x180011698  mov     [r14+0C8h], r13w
0x1800116a0  mov     [r14+0CAh], r13b
0x1800116a7  lea     rbx, [r14+0D0h]
0x1800116ae  mov     qword ptr [rsp+350h+var_300], rbx
0x1800116b3  mov     [rbx], r13
0x1800116b6  mov     [rbx+8], r13
0x1800116ba  mov     rcx, rbx
0x1800116bd  call    ?_Alloc_sentinel_and_proxy@?$list@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@V?$allocator@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@AEAAXXZ; std::list<Microsoft::Windows::Performance::CCvDDCache::CCvDD>::_Alloc_sentinel_and_proxy(void)
0x1800116c2  nop
0x1800116c3  lea     rcx, [rbx+10h]
0x1800116c7  mov     [rcx], r13
0x1800116ca  mov     [rcx+8], r13
0x1800116ce  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@KV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@@2@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<ulong,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>,std::less<ulong>,std::allocator<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>,0>>::_Alloc_sentinel_and_proxy(void)
0x1800116d3  nop
0x1800116d4  lea     rcx, [rbx+20h]
0x1800116d8  call    ??0?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@QEAA@XZ; std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>(void)
0x1800116dd  nop
0x1800116de  lea     rcx, [rbx+30h]
0x1800116e2  mov     [rcx], r13
0x1800116e5  mov     [rcx+8], r13
0x1800116e9  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tset_traits@PEBGU?$less@PEBG@std@@V?$allocator@PEBG@2@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tset_traits<ushort const *,std::less<ushort const *>,std::allocator<ushort const *>,0>>::_Alloc_sentinel_and_proxy(void)
0x1800116ee  nop
0x1800116ef  lea     rcx, [r14+110h]
0x1800116f6  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800116fb  nop
0x1800116fc  mov     [r14+118h], r13
0x180011703  mov     [r14+120h], r13d
0x18001170a  mov     [r14+128h], r13b
0x180011711  mov     [r14+130h], r13
0x180011718  mov     [r14+138h], r13
0x18001171f  mov     [r14+140h], r13
0x180011726  lea     rsi, [r14+148h]
0x18001172d  mov     rcx, rsi
0x180011730  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180011735  nop
0x180011736  lea     rcx, [r14+150h]
0x18001173d  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180011742  nop
0x180011743  lea     rbx, [r14+158h]
0x18001174a  mov     [rbx], r13
0x18001174d  lea     rdi, [r14+160h]
0x180011754  mov     [rdi], r13
0x180011757  lea     r15, [r14+168h]
0x18001175e  mov     [r15], r13
0x180011761  mov     [r14+170h], r13
0x180011768  lea     rcx, [r14+178h]; this
0x18001176f  call    ??0CErrorEvent@Performance@Windows@Microsoft@@QEAA@K@Z; Microsoft::Windows::Performance::CErrorEvent::CErrorEvent(ulong)
0x180011774  nop
0x180011775  lea     r12d, [r13+2]
0x180011779  mov     edx, r12d
0x18001177c  mov     rcx, rbx
0x18001177f  call    ?Allocate@?$CAutoVectorPtr@T_CVDD@@@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<_CVDD>::Allocate(unsigned __int64)
0x180011784  test    al, al
0x180011786  jz      loc_180011B32
0x18001178c  mov     edx, r12d
0x18001178f  mov     rcx, rdi
0x180011792  call    ?Allocate@?$CAutoVectorPtr@K@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<ulong>::Allocate(unsigned __int64)
0x180011797  test    al, al
0x180011799  jz      loc_180011B32
0x18001179f  mov     edx, r12d
0x1800117a2  mov     rcx, r15
0x1800117a5  call    ?Allocate@?$CAutoVectorPtr@_K@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<unsigned __int64>::Allocate(unsigned __int64)
0x1800117aa  test    al, al
0x1800117ac  jz      loc_180011B32
0x1800117b2  mov     [r14+170h], r12d
0x1800117b9  lea     rdx, aXperfEmbeddedp; "XPERF_EmbeddedPdbPath"
0x1800117c0  mov     rcx, rsi
0x1800117c3  call    ?GetEnvironmentVariableW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::GetEnvironmentVariableW(ushort const *)
0x1800117c8  lea     r15d, [r13+1]
0x1800117cc  test    eax, eax
0x1800117ce  jz      short loc_1800117DD
0x1800117d0  mov     rax, [rsi]
0x1800117d3  cmp     [rax-10h], r13d
0x1800117d7  jnz     loc_1800119C2
0x1800117dd  lea     rcx, [rsp+350h+var_318]
0x1800117e2  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800117e7  nop
0x1800117e8  lea     rdx, aNtSymbolPath; "_NT_SYMBOL_PATH"
0x1800117ef  lea     rcx, [rsp+350h+var_318]
0x1800117f4  call    ?GetEnvironmentVariableW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::GetEnvironmentVariableW(ushort const *)
0x1800117f9  test    eax, eax
0x1800117fb  jz      loc_180011937
0x180011801  xorps   xmm0, xmm0
0x180011804  movdqu  [rsp+350h+var_2E8], xmm0
0x18001180a  mov     [rsp+350h+var_2D8], r13
0x18001180f  mov     [rbp+250h+var_2D0], r13d
0x180011813  mov     [rbp+250h+var_2C8], r13
0x180011817  mov     [rbp+250h+var_2C0], r15d
0x18001181b  mov     [rsp+350h+var_2F0], r13d
0x180011820  lea     rcx, [rsp+350h+var_2F0]
0x180011825  call    ?Parse@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@QEAA?AW4REParseError@2@PEBGH@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Parse(ushort const *,int)
0x18001182a  test    eax, eax
0x18001182c  jz      short loc_180011839
0x18001182e  mov     ecx, 8007000Eh; int
0x180011833  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180011839  lea     rcx, [rbp+250h+var_2B0]
0x18001183d  call    ??0?$CAtlREMatchContext@VCAtlRECharTraitsW@ATL@@@ATL@@QEAA@_K@Z; ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW>::CAtlREMatchContext<ATL::CAtlRECharTraitsW>(unsigned __int64)
0x180011842  nop
0x180011843  mov     dword ptr [rsp+350h+var_320], r13d
0x180011848  lea     rcx, [rsp+350h+var_310]
0x18001184d  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180011852  nop
0x180011853  mov     rbx, [rsp+350h+var_310]
0x180011858  lea     r9, [rsp+350h+var_320]
0x18001185d  lea     rdx, [rsp+350h+var_300]
0x180011862  lea     rcx, [rsp+350h+var_318]
0x180011867  call    ?Tokenize@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@PEBGAEAH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Tokenize(ushort const *,int &)
0x18001186c  nop
0x18001186d  mov     rdx, [rax]
0x180011870  lea     rcx, [rdx-18h]
0x180011874  lea     rdi, [rbx-18h]
0x180011878  cmp     rcx, rdi
0x18001187b  jz      short loc_1800118B9
0x18001187d  cmp     [rdi+10h], r13d
0x180011881  jl      short loc_1800118A6
0x180011883  mov     rax, [rdi]
0x180011886  cmp     [rcx], rax
0x180011889  jnz     short loc_1800118A6
0x18001188b  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x180011890  mov     rbx, rax
0x180011893  mov     rcx, rdi; this
0x180011896  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001189b  add     rbx, 18h
0x18001189f  mov     [rsp+350h+var_310], rbx
0x1800118a4  jmp     short loc_1800118B9
0x1800118a6  mov     r8d, [rdx-10h]
0x1800118aa  lea     rcx, [rsp+350h+var_310]
0x1800118af  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800118b4  mov     rbx, [rsp+350h+var_310]
0x1800118b9  mov     edi, [rbx-10h]
0x1800118bc  mov     rcx, qword ptr [rsp+350h+var_300]
0x1800118c1  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800118c5  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800118ca  test    edi, edi
0x1800118cc  jz      short loc_180011919
0x1800118ce  xor     r9d, r9d
0x1800118d1  lea     r8, [rbp+250h+var_2B0]
0x1800118d5  mov     rdx, rbx
0x1800118d8  lea     rcx, [rsp+350h+var_2F0]
0x1800118dd  call    ?Match@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@QEAAHPEBGPEAV?$CAtlREMatchContext@VCAtlRECharTraitsW@ATL@@@2@PEAPEBG@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Match(ushort const *,ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW> *,ushort const * *)
0x1800118e2  test    eax, eax
0x1800118e4  jz      loc_180011858
0x1800118ea  xorps   xmm0, xmm0
0x1800118ed  movups  [rsp+350h+var_300], xmm0
0x1800118f2  lea     r8, [rsp+350h+var_300]
0x1800118f7  lea     rcx, [rbp+250h+var_2B0]
0x1800118fb  call    ?GetMatch@?$CAtlREMatchContext@VCAtlRECharTraitsW@ATL@@@ATL@@QEAAXIPEAUMatchGroup@12@@Z; ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW>::GetMatch(uint,ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW>::MatchGroup *)
0x180011900  mov     r8, qword ptr [rsp+350h+var_300+8]
0x180011905  mov     rdx, qword ptr [rsp+350h+var_300]
0x18001190a  sub     r8, rdx
0x18001190d  sar     r8, 1
0x180011910  mov     rcx, rsi
0x180011913  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180011918  nop
0x180011919  lea     rcx, [rbx-18h]; this
0x18001191d  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180011922  nop
0x180011923  lea     rcx, [rbp+250h+var_2B0]
0x180011927  call    ??1?$CAtlREMatchContext@VCAtlRECharTraitsW@ATL@@@ATL@@QEAA@XZ; ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW>::~CAtlREMatchContext<ATL::CAtlRECharTraitsW>(void)
0x18001192c  nop
0x18001192d  lea     rcx, [rsp+350h+var_2E8]
0x180011932  call    ??1?$CAtlArray@UINSTRUCTION@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@V?$CElementTraits@UINSTRUCTION@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@@3@@ATL@@QEAA@XZ; ATL::CAtlArray<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION,ATL::CElementTraits<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION>>::~CAtlArray<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION,ATL::CElementTraits<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION>>(void)
0x180011937  mov     rax, [rsi]
0x18001193a  cmp     [rax-10h], r13d
0x18001193e  jnz     short loc_1800119B4
0x180011940  mov     edx, 105h; uSize
0x180011945  lea     rcx, [rbp+250h+Buffer]; lpBuffer
0x180011949  call    cs:__imp_GetSystemWindowsDirectoryW
0x180011950  nop     dword ptr [rax+rax+00h]
0x180011955  test    eax, eax
0x180011957  jnz     short loc_180011979
0x180011959  call    cs:__imp_GetLastError
0x180011960  nop     dword ptr [rax+rax+00h]
0x180011965  test    eax, eax
0x180011967  jle     short loc_180011971
0x180011969  movzx   eax, ax
0x18001196c  or      eax, 80070000h
0x180011971  mov     ecx, eax; int
0x180011973  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180011979  lea     rcx, [rbp+250h+Buffer]
0x18001197d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180011981  inc     rax
0x180011984  cmp     [rcx+rax*2], r13w
0x180011989  jnz     short loc_180011981
0x18001198b  cmp     rax, r12
0x18001198e  jb      loc_180011A58
0x180011994  cmp     [rbp+250h+var_25E], 3Ah ; ':'
0x180011999  jnz     loc_180011A58
0x18001199f  movzx   r8d, [rbp+250h+Buffer]
0x1800119a4  lea     rdx, aWcSymbols; "%wc:\\Symbols"
0x1800119ab  mov     rcx, rsi
0x1800119ae  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x1800119b3  nop
0x1800119b4  mov     rcx, [rsp+350h+var_318]
0x1800119b9  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800119bd  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800119c2  mov     rcx, [rsi]; lpFileName
0x1800119c5  cmp     [rcx-10h], r13d
0x1800119c9  jz      short loc_180011A31
0x1800119cb  xor     r9d, r9d; lpFilePart
0x1800119ce  xor     r8d, r8d; lpBuffer
0x1800119d1  xor     edx, edx; nBufferLength
0x1800119d3  call    cs:__imp_GetFullPathNameW
0x1800119da  nop     dword ptr [rax+rax+00h]
0x1800119df  test    eax, eax
0x1800119e1  jz      short loc_180011A31
0x1800119e3  lea     ebx, [rax+1]
0x1800119e6  lea     rcx, [rsp+350h+var_320]
0x1800119eb  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800119f0  nop
0x1800119f1  mov     edx, ebx
0x1800119f3  lea     rcx, [rsp+350h+var_320]
0x1800119f8  call    ?PrepareWrite@?$CSimpleStringT@G$0A@@ATL@@AEAAPEAGH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite(int)
0x1800119fd  lea     rcx, [rsp+350h+var_320]
0x180011a02  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x180011a07  xor     r9d, r9d; lpFilePart
0x180011a0a  mov     r8, rax; lpBuffer
0x180011a0d  mov     edx, ebx; nBufferLength
0x180011a0f  mov     rcx, [rsi]; lpFileName
0x180011a12  call    cs:__imp_GetFullPathNameW
0x180011a19  nop     dword ptr [rax+rax+00h]
0x180011a1e  test    eax, eax
0x180011a20  jnz     short loc_180011A63
0x180011a22  mov     rcx, [rsp+350h+var_320]
0x180011a27  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180011a2b  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180011a30  nop
0x180011a31  mov     rax, r14
0x180011a34  mov     rcx, [rbp+250h+var_50]
0x180011a3b  xor     rcx, rsp; StackCookie
0x180011a3e  call    __security_check_cookie
0x180011a43  add     rsp, 318h
0x180011a4a  pop     r15
0x180011a4c  pop     r14
0x180011a4e  pop     r13
0x180011a50  pop     r12
0x180011a52  pop     rdi
0x180011a53  pop     rsi
0x180011a54  pop     rbx
0x180011a55  pop     rbp
0x180011a56  retn
0x180011a58  mov     ecx, 8000FFFFh; int
0x180011a5d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180011a63  lea     rcx, [rsp+350h+var_320]
0x180011a68  call    ?ReleaseBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::ReleaseBuffer(int)
0x180011a6d  mov     rbx, [rsp+350h+var_320]
0x180011a72  lea     r12, [rbx-18h]
0x180011a76  cmp     [r12+8], r13d
0x180011a7b  jl      loc_180011B27
0x180011a81  cmp     word ptr [rbx], 5Ch ; '\'
0x180011a85  jz      loc_180011B1F
0x180011a8b  lea     rcx, [rsp+350h+var_320]
0x180011a90  call    ?GetManager@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAPEAUIAtlStringMgr@2@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::GetManager(void)
0x180011a95  nop
0x180011a96  mov     rdx, rax
0x180011a99  lea     rcx, [rsp+350h+var_318]
0x180011a9e  call    ??0?$CSimpleStringT@G$0A@@ATL@@QEAA@PEAUIAtlStringMgr@1@@Z; ATL::CSimpleStringT<ushort,0>::CSimpleStringT<ushort,0>(ATL::IAtlStringMgr *)
0x180011aa3  nop
0x180011aa4  mov     [rsp+350h+var_308], r15d
0x180011aa9  mov     eax, [rbx-10h]
0x180011aac  mov     [rsp+350h+var_330], eax
0x180011ab0  mov     r9, rbx
0x180011ab3  mov     r8d, 4
0x180011ab9  lea     rdx, asc_18002BDF0; "\\\\?\\"
0x180011ac0  lea     rcx, [rsp+350h+var_318]
0x180011ac5  call    ?Concatenate@?$CSimpleStringT@G$0A@@ATL@@KAXAEAV12@PEBGH1H@Z; ATL::CSimpleStringT<ushort,0>::Concatenate(ATL::CSimpleStringT<ushort,0> &,ushort const *,int,ushort const *,int)
0x180011aca  mov     rdx, [rsp+350h+var_318]
  ... truncated ...
```
