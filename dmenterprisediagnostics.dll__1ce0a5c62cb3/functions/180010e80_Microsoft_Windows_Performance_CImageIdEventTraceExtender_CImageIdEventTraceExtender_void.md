# Microsoft::Windows::Performance::CImageIdEventTraceExtender::CImageIdEventTraceExtender(void)

- ea: `0x180010e80`
- end: `0x18001138c`
- name: `??0CImageIdEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ`
- size: `1292`
- prototype: `Microsoft::Windows::Performance::CImageIdEventTraceExtender *__fastcall(Microsoft::Windows::Performance::CImageIdEventTraceExtender *this)`
- caller_count: `1`
- callee_count: `31`
- tags: `broker_com_uri`

## callers

- `0x180014198`

## callees

- `0x1800017e0`
- `0x180007cc4`
- `0x180008e80`
- `0x180008f10`
- `0x18000958c`
- `0x18000977c`
- `0x18000a5d4`
- `0x18000a75c`
- `0x18000bc80`
- `0x18000c120`
- `0x18000c3d8`
- `0x1800107ec`
- `0x180010a30`
- `0x180010dc8`
- `0x180010e80`
- `0x180011394`
- `0x1800113ec`
- `0x18001140c`
- `0x180013a4c`
- `0x180013d00`
- `0x180013dac`
- `0x180014550`
- `0x18001457c`
- `0x18001495c`
- `0x1800155d8`
- `0x180016230`
- `0x180017518`
- `0x180017b04`
- `0x180017bc0`
- `0x180017c28`
- `0x180017c5c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800111bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800111bb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1800111b1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1800111b1`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18001122f`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180011268`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18001122f`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180011268`

## string_xrefs

- `0x180011021`: `XPERF_EmbeddedPdbPath`
- `0x180011050`: `_NT_SYMBOL_PATH`

## pseudocode

```c
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
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)this + 192);
  *((_WORD *)this + 100) = 0;
  *((_BYTE *)this + 202) = 0;
  *(_QWORD *)&v28 = (char *)this + 208;
  *((_QWORD *)this + 26) = 0;
  *((_QWORD *)this + 27) = 0;
  std::list<Microsoft::Windows::Performance::CCvDDCache::CCvDD>::_Alloc_sentinel_and_proxy((char *)this + 208);
  *((_QWORD *)this + 28) = 0;
  *((_QWORD *)this + 29) = 0;
  std::_Tree<std::_Tmap_traits<unsigned long,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>,0>>::_Alloc_sentinel_and_proxy();
  std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>((_QWORD *)this + 30);
  *((_QWORD *)this + 32) = 0;
  *((_QWORD *)this + 33) = 0;
  std::_Tree<std::_Tset_traits<unsigned short const *,std::less<unsigned short const *>,std::allocator<unsigned short const *>,0>>::_Alloc_sentinel_and_proxy();
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)this + 272);
  *((_QWORD *)this + 35) = 0;
  *((_DWORD *)this + 72) = 0;
  *((_BYTE *)this + 296) = 0;
  *((_QWORD *)this + 38) = 0;
  *((_QWORD *)this + 39) = 0;
  *((_QWORD *)this + 40) = 0;
  v2 = (LPCWSTR *)((char *)this + 328);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)this + 328);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)this + 336);
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
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v25);
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
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v26);
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
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v24);
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
0x180010e80  push    rbp
0x180010e82  push    rbx
0x180010e83  push    rsi
0x180010e84  push    rdi
0x180010e85  push    r12
0x180010e87  push    r13
0x180010e89  push    r14
0x180010e8b  push    r15
0x180010e8d  lea     rbp, [rsp-218h]
0x180010e95  sub     rsp, 318h
0x180010e9c  mov     rax, cs:__security_cookie
0x180010ea3  xor     rax, rsp
0x180010ea6  mov     [rbp+250h+var_50], rax
0x180010ead  mov     r14, rcx
0x180010eb0  mov     [rbp+250h+var_2B8], rcx
0x180010eb4  xor     r13d, r13d
0x180010eb7  mov     [rsp+350h+var_308], r13d
0x180010ebc  mov     [rcx+18h], r13d
0x180010ec0  mov     [rcx+8], r13
0x180010ec4  mov     [rcx+10h], r13
0x180010ec8  lea     rax, ??_7CImageIdEventTraceExtender@Performance@Windows@Microsoft@@6B@; const Microsoft::Windows::Performance::CImageIdEventTraceExtender::`vftable'
0x180010ecf  mov     [rcx], rax
0x180010ed2  mov     [rcx+20h], r13d
0x180010ed6  mov     [rcx+28h], r13
0x180010eda  mov     [rcx+30h], r13d
0x180010ede  mov     [rcx+38h], r13
0x180010ee2  add     rcx, 40h ; '@'; this
0x180010ee6  call    ??0CLocalNtImagePathDecoder@NtImagePathDecoder@Performance@@QEAA@XZ; Performance::NtImagePathDecoder::CLocalNtImagePathDecoder::CLocalNtImagePathDecoder(void)
0x180010eeb  nop
0x180010eec  mov     [r14+0B8h], r13
0x180010ef3  lea     rcx, [r14+0C0h]
0x180010efa  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180010eff  nop
0x180010f00  mov     [r14+0C8h], r13w
0x180010f08  mov     [r14+0CAh], r13b
0x180010f0f  lea     rbx, [r14+0D0h]
0x180010f16  mov     qword ptr [rsp+350h+var_300], rbx
0x180010f1b  mov     [rbx], r13
0x180010f1e  mov     [rbx+8], r13
0x180010f22  mov     rcx, rbx
0x180010f25  call    ?_Alloc_sentinel_and_proxy@?$list@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@V?$allocator@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@AEAAXXZ; std::list<Microsoft::Windows::Performance::CCvDDCache::CCvDD>::_Alloc_sentinel_and_proxy(void)
0x180010f2a  nop
0x180010f2b  lea     rcx, [rbx+10h]
0x180010f2f  mov     [rcx], r13
0x180010f32  mov     [rcx+8], r13
0x180010f36  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@KV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@@2@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<ulong,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>,std::less<ulong>,std::allocator<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>,0>>::_Alloc_sentinel_and_proxy(void)
0x180010f3b  nop
0x180010f3c  lea     rcx, [rbx+20h]
0x180010f40  call    ??0?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@QEAA@XZ; std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>(void)
0x180010f45  nop
0x180010f46  lea     rcx, [rbx+30h]
0x180010f4a  mov     [rcx], r13
0x180010f4d  mov     [rcx+8], r13
0x180010f51  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tset_traits@PEBGU?$less@PEBG@std@@V?$allocator@PEBG@2@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tset_traits<ushort const *,std::less<ushort const *>,std::allocator<ushort const *>,0>>::_Alloc_sentinel_and_proxy(void)
0x180010f56  nop
0x180010f57  lea     rcx, [r14+110h]
0x180010f5e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180010f63  nop
0x180010f64  mov     [r14+118h], r13
0x180010f6b  mov     [r14+120h], r13d
0x180010f72  mov     [r14+128h], r13b
0x180010f79  mov     [r14+130h], r13
0x180010f80  mov     [r14+138h], r13
0x180010f87  mov     [r14+140h], r13
0x180010f8e  lea     rsi, [r14+148h]
0x180010f95  mov     rcx, rsi
0x180010f98  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180010f9d  nop
0x180010f9e  lea     rcx, [r14+150h]
0x180010fa5  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180010faa  nop
0x180010fab  lea     rbx, [r14+158h]
0x180010fb2  mov     [rbx], r13
0x180010fb5  lea     rdi, [r14+160h]
0x180010fbc  mov     [rdi], r13
0x180010fbf  lea     r15, [r14+168h]
0x180010fc6  mov     [r15], r13
0x180010fc9  mov     [r14+170h], r13
0x180010fd0  lea     rcx, [r14+178h]; this
0x180010fd7  call    ??0CErrorEvent@Performance@Windows@Microsoft@@QEAA@K@Z; Microsoft::Windows::Performance::CErrorEvent::CErrorEvent(ulong)
0x180010fdc  nop
0x180010fdd  lea     r12d, [r13+2]
0x180010fe1  mov     edx, r12d
0x180010fe4  mov     rcx, rbx
0x180010fe7  call    ?Allocate@?$CAutoVectorPtr@T_CVDD@@@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<_CVDD>::Allocate(unsigned __int64)
0x180010fec  test    al, al
0x180010fee  jz      loc_180011381
0x180010ff4  mov     edx, r12d
0x180010ff7  mov     rcx, rdi
0x180010ffa  call    ?Allocate@?$CAutoVectorPtr@K@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<ulong>::Allocate(unsigned __int64)
0x180010fff  test    al, al
0x180011001  jz      loc_180011381
0x180011007  mov     edx, r12d
0x18001100a  mov     rcx, r15
0x18001100d  call    ?Allocate@?$CAutoVectorPtr@_K@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<unsigned __int64>::Allocate(unsigned __int64)
0x180011012  test    al, al
0x180011014  jz      loc_180011381
0x18001101a  mov     [r14+170h], r12d
0x180011021  lea     rdx, aXperfEmbeddedp; "XPERF_EmbeddedPdbPath"
0x180011028  mov     rcx, rsi
0x18001102b  call    ?GetEnvironmentVariableW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::GetEnvironmentVariableW(ushort const *)
0x180011030  lea     r15d, [r13+1]
0x180011034  test    eax, eax
0x180011036  jz      short loc_180011045
0x180011038  mov     rax, [rsi]
0x18001103b  cmp     [rax-10h], r13d
0x18001103f  jnz     loc_18001121E
0x180011045  lea     rcx, [rsp+350h+var_318]
0x18001104a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18001104f  nop
0x180011050  lea     rdx, aNtSymbolPath; "_NT_SYMBOL_PATH"
0x180011057  lea     rcx, [rsp+350h+var_318]
0x18001105c  call    ?GetEnvironmentVariableW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::GetEnvironmentVariableW(ushort const *)
0x180011061  test    eax, eax
0x180011063  jz      loc_18001119F
0x180011069  xorps   xmm0, xmm0
0x18001106c  movdqu  [rsp+350h+var_2E8], xmm0
0x180011072  mov     [rsp+350h+var_2D8], r13
0x180011077  mov     [rbp+250h+var_2D0], r13d
0x18001107b  mov     [rbp+250h+var_2C8], r13
0x18001107f  mov     [rbp+250h+var_2C0], r15d
0x180011083  mov     [rsp+350h+var_2F0], r13d
0x180011088  lea     rcx, [rsp+350h+var_2F0]
0x18001108d  call    ?Parse@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@QEAA?AW4REParseError@2@PEBGH@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Parse(ushort const *,int)
0x180011092  test    eax, eax
0x180011094  jz      short loc_1800110A1
0x180011096  mov     ecx, 8007000Eh; int
0x18001109b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800110a1  lea     rcx, [rbp+250h+var_2B0]
0x1800110a5  call    ??0?$CAtlREMatchContext@VCAtlRECharTraitsW@ATL@@@ATL@@QEAA@_K@Z; ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW>::CAtlREMatchContext<ATL::CAtlRECharTraitsW>(unsigned __int64)
0x1800110aa  nop
0x1800110ab  mov     dword ptr [rsp+350h+var_320], r13d
0x1800110b0  lea     rcx, [rsp+350h+var_310]
0x1800110b5  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800110ba  nop
0x1800110bb  mov     rbx, [rsp+350h+var_310]
0x1800110c0  lea     r9, [rsp+350h+var_320]
0x1800110c5  lea     rdx, [rsp+350h+var_300]
0x1800110ca  lea     rcx, [rsp+350h+var_318]
0x1800110cf  call    ?Tokenize@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@PEBGAEAH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Tokenize(ushort const *,int &)
0x1800110d4  nop
0x1800110d5  mov     rdx, [rax]
0x1800110d8  lea     rcx, [rdx-18h]
0x1800110dc  lea     rdi, [rbx-18h]
0x1800110e0  cmp     rcx, rdi
0x1800110e3  jz      short loc_180011121
0x1800110e5  cmp     [rdi+10h], r13d
0x1800110e9  jl      short loc_18001110E
0x1800110eb  mov     rax, [rdi]
0x1800110ee  cmp     [rcx], rax
0x1800110f1  jnz     short loc_18001110E
0x1800110f3  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x1800110f8  mov     rbx, rax
0x1800110fb  mov     rcx, rdi; this
0x1800110fe  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180011103  add     rbx, 18h
0x180011107  mov     [rsp+350h+var_310], rbx
0x18001110c  jmp     short loc_180011121
0x18001110e  mov     r8d, [rdx-10h]
0x180011112  lea     rcx, [rsp+350h+var_310]
0x180011117  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18001111c  mov     rbx, [rsp+350h+var_310]
0x180011121  mov     edi, [rbx-10h]
0x180011124  mov     rcx, qword ptr [rsp+350h+var_300]
0x180011129  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001112d  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180011132  test    edi, edi
0x180011134  jz      short loc_180011181
0x180011136  xor     r9d, r9d
0x180011139  lea     r8, [rbp+250h+var_2B0]
0x18001113d  mov     rdx, rbx
0x180011140  lea     rcx, [rsp+350h+var_2F0]
0x180011145  call    ?Match@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@QEAAHPEBGPEAV?$CAtlREMatchContext@VCAtlRECharTraitsW@ATL@@@2@PEAPEBG@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Match(ushort const *,ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW> *,ushort const * *)
0x18001114a  test    eax, eax
0x18001114c  jz      loc_1800110C0
0x180011152  xorps   xmm0, xmm0
0x180011155  movups  [rsp+350h+var_300], xmm0
0x18001115a  lea     r8, [rsp+350h+var_300]
0x18001115f  lea     rcx, [rbp+250h+var_2B0]
0x180011163  call    ?GetMatch@?$CAtlREMatchContext@VCAtlRECharTraitsW@ATL@@@ATL@@QEAAXIPEAUMatchGroup@12@@Z; ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW>::GetMatch(uint,ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW>::MatchGroup *)
0x180011168  mov     r8, qword ptr [rsp+350h+var_300+8]
0x18001116d  mov     rdx, qword ptr [rsp+350h+var_300]
0x180011172  sub     r8, rdx
0x180011175  sar     r8, 1
0x180011178  mov     rcx, rsi
0x18001117b  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180011180  nop
0x180011181  lea     rcx, [rbx-18h]; this
0x180011185  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001118a  nop
0x18001118b  lea     rcx, [rbp+250h+var_2B0]
0x18001118f  call    ??1?$CAtlREMatchContext@VCAtlRECharTraitsW@ATL@@@ATL@@QEAA@XZ; ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW>::~CAtlREMatchContext<ATL::CAtlRECharTraitsW>(void)
0x180011194  nop
0x180011195  lea     rcx, [rsp+350h+var_2E8]
0x18001119a  call    ??1?$CAtlArray@UINSTRUCTION@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@V?$CElementTraits@UINSTRUCTION@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@@3@@ATL@@QEAA@XZ; ATL::CAtlArray<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION,ATL::CElementTraits<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION>>::~CAtlArray<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION,ATL::CElementTraits<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION>>(void)
0x18001119f  mov     rax, [rsi]
0x1800111a2  cmp     [rax-10h], r13d
0x1800111a6  jnz     short loc_180011210
0x1800111a8  mov     edx, 105h; uSize
0x1800111ad  lea     rcx, [rbp+250h+Buffer]; lpBuffer
0x1800111b1  call    cs:__imp_GetSystemWindowsDirectoryW
0x1800111b7  test    eax, eax
0x1800111b9  jnz     short loc_1800111D5
0x1800111bb  call    cs:__imp_GetLastError
0x1800111c1  test    eax, eax
0x1800111c3  jle     short loc_1800111CD
0x1800111c5  movzx   eax, ax
0x1800111c8  or      eax, 80070000h
0x1800111cd  mov     ecx, eax; int
0x1800111cf  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800111d5  lea     rcx, [rbp+250h+Buffer]
0x1800111d9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800111dd  inc     rax
0x1800111e0  cmp     [rcx+rax*2], r13w
0x1800111e5  jnz     short loc_1800111DD
0x1800111e7  cmp     rax, r12
0x1800111ea  jb      loc_1800112A7
0x1800111f0  cmp     [rbp+250h+var_25E], 3Ah ; ':'
0x1800111f5  jnz     loc_1800112A7
0x1800111fb  movzx   r8d, [rbp+250h+Buffer]
0x180011200  lea     rdx, aWcSymbols; "%wc:\\Symbols"
0x180011207  mov     rcx, rsi
0x18001120a  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18001120f  nop
0x180011210  mov     rcx, [rsp+350h+var_318]
0x180011215  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180011219  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001121e  mov     rcx, [rsi]; lpFileName
0x180011221  cmp     [rcx-10h], r13d
0x180011225  jz      short loc_180011281
0x180011227  xor     r9d, r9d; lpFilePart
0x18001122a  xor     r8d, r8d; lpBuffer
0x18001122d  xor     edx, edx; nBufferLength
0x18001122f  call    cs:__imp_GetFullPathNameW
0x180011235  test    eax, eax
0x180011237  jz      short loc_180011281
0x180011239  lea     ebx, [rax+1]
0x18001123c  lea     rcx, [rsp+350h+var_320]
0x180011241  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180011246  nop
0x180011247  mov     edx, ebx
0x180011249  lea     rcx, [rsp+350h+var_320]
0x18001124e  call    ?PrepareWrite@?$CSimpleStringT@G$0A@@ATL@@AEAAPEAGH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite(int)
0x180011253  lea     rcx, [rsp+350h+var_320]
0x180011258  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x18001125d  xor     r9d, r9d; lpFilePart
0x180011260  mov     r8, rax; lpBuffer
0x180011263  mov     edx, ebx; nBufferLength
0x180011265  mov     rcx, [rsi]; lpFileName
0x180011268  call    cs:__imp_GetFullPathNameW
0x18001126e  test    eax, eax
0x180011270  jnz     short loc_1800112B2
0x180011272  mov     rcx, [rsp+350h+var_320]
0x180011277  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001127b  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180011280  nop
0x180011281  mov     rax, r14
0x180011284  mov     rcx, [rbp+250h+var_50]
0x18001128b  xor     rcx, rsp; StackCookie
0x18001128e  call    __security_check_cookie
0x180011293  add     rsp, 318h
0x18001129a  pop     r15
0x18001129c  pop     r14
0x18001129e  pop     r13
0x1800112a0  pop     r12
0x1800112a2  pop     rdi
0x1800112a3  pop     rsi
0x1800112a4  pop     rbx
0x1800112a5  pop     rbp
0x1800112a6  retn
0x1800112a7  mov     ecx, 8000FFFFh; int
0x1800112ac  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800112b2  lea     rcx, [rsp+350h+var_320]
0x1800112b7  call    ?ReleaseBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::ReleaseBuffer(int)
0x1800112bc  mov     rbx, [rsp+350h+var_320]
0x1800112c1  lea     r12, [rbx-18h]
0x1800112c5  cmp     [r12+8], r13d
0x1800112ca  jl      loc_180011376
0x1800112d0  cmp     word ptr [rbx], 5Ch ; '\'
0x1800112d4  jz      loc_18001136E
0x1800112da  lea     rcx, [rsp+350h+var_320]
0x1800112df  call    ?GetManager@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAPEAUIAtlStringMgr@2@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::GetManager(void)
0x1800112e4  nop
0x1800112e5  mov     rdx, rax
0x1800112e8  lea     rcx, [rsp+350h+var_318]
0x1800112ed  call    ??0?$CSimpleStringT@G$0A@@ATL@@QEAA@PEAUIAtlStringMgr@1@@Z; ATL::CSimpleStringT<ushort,0>::CSimpleStringT<ushort,0>(ATL::IAtlStringMgr *)
0x1800112f2  nop
0x1800112f3  mov     [rsp+350h+var_308], r15d
0x1800112f8  mov     eax, [rbx-10h]
0x1800112fb  mov     [rsp+350h+var_330], eax
0x1800112ff  mov     r9, rbx
0x180011302  mov     r8d, 4
0x180011308  lea     rdx, asc_18002ADF0; "\\\\?\\"
0x18001130f  lea     rcx, [rsp+350h+var_318]
0x180011314  call    ?Concatenate@?$CSimpleStringT@G$0A@@ATL@@KAXAEAV12@PEBGH1H@Z; ATL::CSimpleStringT<ushort,0>::Concatenate(ATL::CSimpleStringT<ushort,0> &,ushort const *,int,ushort const *,int)
0x180011319  mov     rdx, [rsp+350h+var_318]
0x18001131e  lea     rdi, [rdx-18h]
0x180011322  mov     r15, [rsi]
0x180011325  add     r15, 0FFFFFFFFFFFFFFE8h
0x180011329  cmp     rdi, r15
  ... truncated ...
```
