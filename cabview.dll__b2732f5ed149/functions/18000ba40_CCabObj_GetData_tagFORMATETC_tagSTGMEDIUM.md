# CCabObj::GetData(tagFORMATETC *,tagSTGMEDIUM *)

- ea: `0x18000ba40`
- end: `0x18000be6d`
- name: `?GetData@CCabObj@@UEAAJPEAUtagFORMATETC@@PEAUtagSTGMEDIUM@@@Z`
- size: `1069`
- prototype: `__int64 __fastcall(CCabObj *this, struct tagFORMATETC *, struct tagSTGMEDIUM *)`
- caller_count: `0`
- callee_count: `17`
- tags: `loader_planting`

## callees

- `0x180002620`
- `0x180008c48`
- `0x18000b42c`
- `0x18000b884`
- `0x18000ba40`
- `0x18000bec8`
- `0x18000bfa4`
- `0x18000c080`
- `0x18000c0bc`
- `0x18000c0f8`
- `0x18000c134`
- `0x18000c714`
- `0x18000cf00`
- `0x18000d0c0`
- `0x180011e00`
- `0x1800127d0`
- `0x180013010`

## import_xrefs

- `SHELL32!__imp_ILFree` at `0x18000be32`
- `SHELL32!__imp_ILFree` at `0x18000be32`
- `SHLWAPI!PathFindFileNameW` at `0x18000bb84`
- `SHLWAPI!PathFindFileNameW` at `0x18000bb84`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000bb01`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000bb01`
- `api-ms-win-core-file-l1-1-0!LocalFileTimeToFileTime` at `0x18000bb6e`
- `api-ms-win-core-file-l1-1-0!LocalFileTimeToFileTime` at `0x18000bb6e`
- `KERNEL32!DosDateTimeToFileTime` at `0x18000bb5c`
- `KERNEL32!DosDateTimeToFileTime` at `0x18000bb5c`
- `USER32!RegisterClipboardFormatW` at `0x18000bd4f`
- `USER32!RegisterClipboardFormatW` at `0x18000bd4f`

## pseudocode

```c
__int64 __fastcall CCabObj::GetData(CCabObj *this, struct tagFORMATETC *a2, struct tagSTGMEDIUM *a3)
{
  CCabObj *v6; // rcx
  int Count; // eax
  int v8; // edi
  int v9; // r15d
  __int64 v10; // r12
  UINT v11; // ecx
  _DWORD *v12; // rax
  HBITMAP v13; // rbx
  WORD *Ptr; // rax
  __int64 v15; // rdi
  WORD *v16; // rbp
  const unsigned __int16 *FileNameW; // rax
  __int64 result; // rax
  CCabObj *v19; // rcx
  int v20; // eax
  INT_PTR v21; // rdx
  HBITMAP v22; // rdi
  _DWORD *v23; // rax
  __int64 v24; // rcx
  unsigned int v25; // edx
  unsigned int v26; // eax
  INT_PTR v27; // rdx
  unsigned __int64 v28; // r8
  UINT v29; // eax
  CCabObj *cfFormat; // rcx
  int v31; // edi
  __int64 v32; // rcx
  CCabItemList *v33; // rcx
  unsigned int v34; // eax
  const struct _ITEMIDLIST **v35; // r8
  HBITMAP v36; // rax
  struct _FILETIME FileTime; // [rsp+20h] [rbp-48h] BYREF

  *(_OWORD *)&a3->tymed = 0;
  a3->pUnkForRelease = 0;
  if ( !(unsigned int)CCabObj::InitFileGroupDesc(this) )
    return 2147549183LL;
  if ( a2->cfFormat == CCabObj::s_uFileGroupDesc )
  {
    if ( !a2->ptd && (a2->dwAspect & 1) != 0 && a2->lindex == -1 && (a2->tymed & 1) != 0 )
    {
      Count = CCabItemList::GetCount((CCabObj *)((char *)this + 24));
      v8 = Count;
      if ( Count >= 1 )
      {
        v9 = Count - 1;
        v10 = Count - 1;
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ZeroInitGAlloc>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ZeroInitGAlloc>::GetImpl'::`2'::impl) )
          v11 = 64;
        else
          v11 = 0;
        v12 = GlobalAlloc(v11, 592LL * v9 + 596);
        v13 = (HBITMAP)v12;
        if ( v12 )
        {
          *v12 = v8;
          do
          {
            Ptr = (WORD *)DPA_GetPtr(*((HDPA *)this + 4), (unsigned int)v9);
            v15 = 592 * v10;
            FileTime = 0;
            v16 = Ptr;
            *(_DWORD *)((char *)v13 + v15 + 4) = 16452;
            *(_DWORD *)((char *)v13 + v15 + 40) = Ptr[6];
            if ( Ptr[4] )
            {
              *(_DWORD *)((char *)v13 + v15 + 4) = 16484;
              DosDateTimeToFileTime(Ptr[4], Ptr[5], &FileTime);
              LocalFileTimeToFileTime(&FileTime, (LPFILETIME)((char *)v13 + v15 + 60));
            }
            *(_DWORD *)((char *)v13 + v15 + 68) = 0;
            *(_DWORD *)(HBITMAP)((char *)v13 + v15 + 72) = *(_DWORD *)(HBITMAP)(v16 + 2);
            FileNameW = PathFindFileNameW(v16 + 8);
            StringCchCopyW((unsigned __int16 *)((char *)v13 + v15 + 76), 0x104u, FileNameW);
            --v10;
            --v9;
          }
          while ( v9 >= 0 );
          a3->tymed = 1;
          a3->hBitmap = v13;
          a3->pUnkForRelease = 0;
          return 0;
        }
        return 2147942414LL;
      }
      return 2147549183LL;
    }
    return 2147942487LL;
  }
  if ( !(unsigned int)CCabObj::InitFileContents(v6) )
    return 2147549183LL;
  if ( a2->cfFormat == CCabObj::s_uFileContents )
  {
    if ( a2->ptd || (a2->dwAspect & 1) == 0 )
      return 2147942487LL;
    if ( (a2->tymed & 4) != 0 )
    {
      if ( a2->lindex < 0 )
        return 2147942487LL;
      v20 = CCabItemList::GetCount((CCabObj *)((char *)this + 24));
      if ( (int)v21 >= v20 )
        return 2147942487LL;
      result = CCabObj::InitCurrent((CCabObj *)((char *)this - 16), v21);
      if ( (int)result < 0 )
        return result;
      if ( !*((_QWORD *)this + 6) )
      {
        if ( *((_DWORD *)this + 18) )
          return 2147943623LL;
        return 2147942414LL;
      }
      v22 = (HBITMAP)operator new(0x20u);
      if ( !v22 )
        return 2147942414LL;
      v23 = DPA_GetPtr(*((HDPA *)this + 4), (unsigned int)a2->lindex);
      v24 = *((_QWORD *)this + 6);
      v25 = v23[1];
      *(_QWORD *)v22 = &CCabStream::`vftable';
      *((_DWORD *)v22 + 2) = 1;
      _InterlockedIncrement(&g_cRefThisDll);
      *((_QWORD *)v22 + 2) = v24;
      *((_QWORD *)v22 + 3) = v25;
      a3->tymed = 4;
      a3->hBitmap = v22;
    }
    else
    {
      if ( (a2->tymed & 1) == 0 )
        return 2147942487LL;
      v26 = CCabItemList::GetCount((CCabObj *)((char *)this + 24));
      if ( (unsigned int)v27 >= v26 )
        return 2147942487LL;
      result = CCabObj::InitCurrent((CCabObj *)((char *)this - 16), v27);
      if ( (int)result < 0 )
        return result;
      if ( !*((_QWORD *)this + 6) )
        return 2147942414LL;
      a3->tymed = 1;
      a3->hBitmap = (HBITMAP)*((_QWORD *)this + 6);
    }
    a3->pUnkForRelease = 0;
    *((_QWORD *)this + 6) = 0;
    return 0;
  }
  if ( !(unsigned int)CCabObj::InitPersistedDataObject(v19) )
    return 2147549183LL;
  if ( a2->cfFormat == CCabObj::s_uPersistedDataObject )
  {
    if ( !a2->ptd && (a2->dwAspect & 1) != 0 && a2->lindex == -1 && (a2->tymed & 1) != 0 )
    {
      FileTime.dwLowDateTime = 0;
      return StgMediumWriteHGlobal(&a3->hMetaFilePict, &FileTime, v28);
    }
    return 2147942487LL;
  }
  v29 = CCabObj::s_ZoneIdentifier;
  if ( !CCabObj::s_ZoneIdentifier )
  {
    v29 = RegisterClipboardFormatW(L"ZoneIdentifier");
    CCabObj::s_ZoneIdentifier = v29;
    if ( !v29 )
      return 2147549183LL;
  }
  cfFormat = (CCabObj *)a2->cfFormat;
  if ( (_DWORD)cfFormat == v29 )
  {
    if ( !a2->ptd && (a2->dwAspect & 1) != 0 && a2->lindex == -1 && (a2->tymed & 1) != 0 )
      return CCabObj::RenderZoneIdentifier((CCabObj *)((char *)this - 16), a3);
    return 2147942487LL;
  }
  if ( !(unsigned int)CCabObj::InitHIDA(cfFormat) )
    return 2147549183LL;
  if ( a2->cfFormat != CCabObj::s_uHIDA )
    return 2147500033LL;
  v31 = -2147024809;
  if ( !a2->ptd && (a2->dwAspect & 1) != 0 && a2->lindex == -1 && (a2->tymed & 1) != 0 )
  {
    v32 = *((_QWORD *)this + 7);
    FileTime = 0;
    v31 = (*(__int64 (__fastcall **)(__int64, struct _FILETIME *))(*(_QWORD *)v32 + 40LL))(v32, &FileTime);
    if ( v31 >= 0 )
    {
      CCabItemList::GetArray((CCabObj *)((char *)this + 24));
      v34 = CCabItemList::GetCount(v33);
      v36 = (HBITMAP)HIDA_Create(*(const struct _ITEMIDLIST **)&FileTime, v34, v35);
      if ( v36 )
      {
        a3->tymed = 1;
        v31 = 0;
        a3->hBitmap = v36;
      }
      else
      {
        v31 = -2147024882;
      }
      ILFree(*(LPITEMIDLIST *)&FileTime);
    }
  }
  return (unsigned int)v31;
}

```

## disassembly

```asm
0x18000ba40  mov     [rsp+arg_18], rbx
0x18000ba45  push    rbp
0x18000ba46  push    rsi
0x18000ba47  push    rdi
0x18000ba48  push    r12
0x18000ba4a  push    r13
0x18000ba4c  push    r14
0x18000ba4e  push    r15
0x18000ba50  sub     rsp, 30h
0x18000ba54  mov     rax, cs:__security_cookie
0x18000ba5b  xor     rax, rsp
0x18000ba5e  mov     [rsp+68h+var_40], rax
0x18000ba63  xorps   xmm0, xmm0
0x18000ba66  xor     eax, eax
0x18000ba68  movups  xmmword ptr [r8], xmm0
0x18000ba6c  mov     [r8+10h], rax
0x18000ba70  mov     r14, r8
0x18000ba73  mov     rbx, rdx
0x18000ba76  mov     rsi, rcx
0x18000ba79  call    ?InitFileGroupDesc@CCabObj@@AEAAHXZ; CCabObj::InitFileGroupDesc(void)
0x18000ba7e  xor     r13d, r13d
0x18000ba81  test    eax, eax
0x18000ba83  jz      loc_18000BE43
0x18000ba89  movzx   eax, word ptr [rbx]
0x18000ba8c  cmp     eax, cs:?s_uFileGroupDesc@CCabObj@@0IA; uint CCabObj::s_uFileGroupDesc
0x18000ba92  jnz     loc_18000BBC1
0x18000ba98  cmp     [rbx+8], r13
0x18000ba9c  jnz     loc_18000BD93
0x18000baa2  test    byte ptr [rbx+10h], 1
0x18000baa6  jz      loc_18000BD93
0x18000baac  cmp     dword ptr [rbx+14h], 0FFFFFFFFh
0x18000bab0  jnz     loc_18000BD93
0x18000bab6  test    byte ptr [rbx+18h], 1
0x18000baba  jz      loc_18000BD93
0x18000bac0  lea     rcx, [rsi+18h]; this
0x18000bac4  call    ?GetCount@CCabItemList@@QEAAIXZ; CCabItemList::GetCount(void)
0x18000bac9  mov     edi, eax
0x18000bacb  cmp     eax, 1
0x18000bace  jl      loc_18000BE43
0x18000bad4  lea     r15d, [rax-1]
0x18000bad8  movsxd  r12, r15d
0x18000badb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ZeroInitGAlloc@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ZeroInitGAlloc@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ZeroInitGAlloc> `wil::Feature<__WilFeatureTraits_Feature_ZeroInitGAlloc>::GetImpl(void)'::`2'::impl
0x18000bae2  imul    rbx, r12, 250h
0x18000bae9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ZeroInitGAlloc@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ZeroInitGAlloc>::__private_IsEnabled(void)
0x18000baee  lea     rdx, [rbx+254h]; dwBytes
0x18000baf5  test    al, al
0x18000baf7  jz      short loc_18000BAFF
0x18000baf9  lea     ecx, [r13+40h]
0x18000bafd  jmp     short loc_18000BB01
0x18000baff  xor     ecx, ecx; uFlags
0x18000bb01  call    cs:__imp_GlobalAlloc
0x18000bb07  mov     rbx, rax
0x18000bb0a  test    rax, rax
0x18000bb0d  jz      loc_18000BCDB
0x18000bb13  mov     [rax], edi
0x18000bb15  mov     rcx, [rsi+20h]; hdpa
0x18000bb19  mov     edx, r15d; i
0x18000bb1c  call    DPA_GetPtr
0x18000bb21  imul    rdi, r12, 250h
0x18000bb28  mov     qword ptr [rsp+68h+FileTime.dwLowDateTime], r13
0x18000bb2d  mov     rbp, rax
0x18000bb30  mov     dword ptr [rdi+rbx+4], 4044h
0x18000bb38  movzx   ecx, word ptr [rax+0Ch]
0x18000bb3c  mov     [rdi+rbx+28h], ecx
0x18000bb40  cmp     [rax+8], r13w
0x18000bb45  jz      short loc_18000BB74
0x18000bb47  mov     dword ptr [rdi+rbx+4], 4064h
0x18000bb4f  lea     r8, [rsp+68h+FileTime]; lpFileTime
0x18000bb54  movzx   edx, word ptr [rax+0Ah]; wFatTime
0x18000bb58  movzx   ecx, word ptr [rax+8]; wFatDate
0x18000bb5c  call    cs:__imp_DosDateTimeToFileTime
0x18000bb62  lea     rdx, [rbx+3Ch]
0x18000bb66  add     rdx, rdi; lpFileTime
0x18000bb69  lea     rcx, [rsp+68h+FileTime]; lpLocalFileTime
0x18000bb6e  call    cs:__imp_LocalFileTimeToFileTime
0x18000bb74  mov     [rdi+rbx+44h], r13d
0x18000bb79  lea     rcx, [rbp+10h]; pszPath
0x18000bb7d  mov     eax, [rbp+4]
0x18000bb80  mov     [rdi+rbx+48h], eax
0x18000bb84  call    cs:__imp_PathFindFileNameW
0x18000bb8a  lea     rcx, [rbx+4Ch]
0x18000bb8e  mov     edx, 104h; unsigned __int64
0x18000bb93  add     rcx, rdi; unsigned __int16 *
0x18000bb96  mov     r8, rax; unsigned __int16 *
0x18000bb99  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000bb9e  dec     r12
0x18000bba1  sub     r15d, 1
0x18000bba5  jns     loc_18000BB15
0x18000bbab  mov     dword ptr [r14], 1
0x18000bbb2  mov     [r14+8], rbx
0x18000bbb6  mov     [r14+10h], r13
0x18000bbba  xor     eax, eax
0x18000bbbc  jmp     loc_18000BE48
0x18000bbc1  call    ?InitFileContents@CCabObj@@AEAAHXZ; CCabObj::InitFileContents(void)
0x18000bbc6  test    eax, eax
0x18000bbc8  jz      loc_18000BE43
0x18000bbce  movzx   eax, word ptr [rbx]
0x18000bbd1  cmp     eax, cs:?s_uFileContents@CCabObj@@0IA; uint CCabObj::s_uFileContents
0x18000bbd7  jnz     loc_18000BCF6
0x18000bbdd  cmp     [rbx+8], r13
0x18000bbe1  jnz     loc_18000BD93
0x18000bbe7  test    byte ptr [rbx+10h], 1
0x18000bbeb  jz      loc_18000BD93
0x18000bbf1  test    byte ptr [rbx+18h], 4
0x18000bbf5  jz      loc_18000BCA6
0x18000bbfb  mov     edx, [rbx+14h]
0x18000bbfe  test    edx, edx
0x18000bc00  js      loc_18000BD93
0x18000bc06  lea     rcx, [rsi+18h]; this
0x18000bc0a  call    ?GetCount@CCabItemList@@QEAAIXZ; CCabItemList::GetCount(void)
0x18000bc0f  cmp     edx, eax
0x18000bc11  jge     loc_18000BD93
0x18000bc17  lea     rcx, [rsi-10h]; this
0x18000bc1b  call    ?InitCurrent@CCabObj@@AEAAJI@Z; CCabObj::InitCurrent(uint)
0x18000bc20  test    eax, eax
0x18000bc22  js      loc_18000BE48
0x18000bc28  cmp     [rsi+30h], r13
0x18000bc2c  jnz     short loc_18000BC42
0x18000bc2e  cmp     [rsi+48h], r13d
0x18000bc32  jz      loc_18000BCDB
0x18000bc38  mov     eax, 800704C7h
0x18000bc3d  jmp     loc_18000BE48
0x18000bc42  mov     ecx, 20h ; ' '; unsigned __int64
0x18000bc47  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000bc4c  mov     rdi, rax
0x18000bc4f  test    rax, rax
0x18000bc52  jz      loc_18000BCDB
0x18000bc58  mov     edx, [rbx+14h]; i
0x18000bc5b  mov     rcx, [rsi+20h]; hdpa
0x18000bc5f  call    DPA_GetPtr
0x18000bc64  mov     rcx, [rsi+30h]
0x18000bc68  mov     edx, [rax+4]
0x18000bc6b  lea     rax, ??_7CCabStream@@6B@; const CCabStream::`vftable'
0x18000bc72  mov     [rdi], rax
0x18000bc75  mov     dword ptr [rdi+8], 1
0x18000bc7c  lock inc cs:?g_cRefThisDll@@3JA; long g_cRefThisDll
0x18000bc83  mov     [rdi+10h], rcx
0x18000bc87  mov     [rdi+18h], edx
0x18000bc8a  mov     [rdi+1Ch], r13d
0x18000bc8e  mov     dword ptr [r14], 4
0x18000bc95  mov     [r14+8], rdi
0x18000bc99  mov     [r14+10h], r13
0x18000bc9d  mov     [rsi+30h], r13
0x18000bca1  jmp     loc_18000BBBA
0x18000bca6  test    byte ptr [rbx+18h], 1
0x18000bcaa  jz      loc_18000BD93
0x18000bcb0  mov     edx, [rbx+14h]
0x18000bcb3  lea     rcx, [rsi+18h]; this
0x18000bcb7  call    ?GetCount@CCabItemList@@QEAAIXZ; CCabItemList::GetCount(void)
0x18000bcbc  cmp     edx, eax
0x18000bcbe  jnb     loc_18000BD93
0x18000bcc4  lea     rcx, [rsi-10h]; this
0x18000bcc8  call    ?InitCurrent@CCabObj@@AEAAJI@Z; CCabObj::InitCurrent(uint)
0x18000bccd  test    eax, eax
0x18000bccf  js      loc_18000BE48
0x18000bcd5  cmp     [rsi+30h], r13
0x18000bcd9  jnz     short loc_18000BCE5
0x18000bcdb  mov     eax, 8007000Eh
0x18000bce0  jmp     loc_18000BE48
0x18000bce5  mov     dword ptr [r14], 1
0x18000bcec  mov     rax, [rsi+30h]
0x18000bcf0  mov     [r14+8], rax
0x18000bcf4  jmp     short loc_18000BC99
0x18000bcf6  call    ?InitPersistedDataObject@CCabObj@@AEAAHXZ; CCabObj::InitPersistedDataObject(void)
0x18000bcfb  test    eax, eax
0x18000bcfd  jz      loc_18000BE43
0x18000bd03  movzx   eax, word ptr [rbx]
0x18000bd06  cmp     eax, cs:?s_uPersistedDataObject@CCabObj@@0IA; uint CCabObj::s_uPersistedDataObject
0x18000bd0c  jnz     short loc_18000BD3E
0x18000bd0e  cmp     [rbx+8], r13
0x18000bd12  jnz     short loc_18000BD93
0x18000bd14  test    byte ptr [rbx+10h], 1
0x18000bd18  jz      short loc_18000BD93
0x18000bd1a  cmp     dword ptr [rbx+14h], 0FFFFFFFFh
0x18000bd1e  jnz     short loc_18000BD93
0x18000bd20  test    byte ptr [rbx+18h], 1
0x18000bd24  jz      short loc_18000BD93
0x18000bd26  lea     rcx, [r14+8]; void **
0x18000bd2a  mov     [rsp+68h+FileTime.dwLowDateTime], r13d
0x18000bd2f  lea     rdx, [rsp+68h+FileTime]; void *
0x18000bd34  call    ?StgMediumWriteHGlobal@@YAJPEAPEAXPEBX_K@Z; StgMediumWriteHGlobal(void * *,void const *,unsigned __int64)
0x18000bd39  jmp     loc_18000BE48
0x18000bd3e  mov     eax, cs:?s_ZoneIdentifier@CCabObj@@0IA; uint CCabObj::s_ZoneIdentifier
0x18000bd44  test    eax, eax
0x18000bd46  jnz     short loc_18000BD63
0x18000bd48  lea     rcx, szFormat; "ZoneIdentifier"
0x18000bd4f  call    cs:__imp_RegisterClipboardFormatW
0x18000bd55  mov     cs:?s_ZoneIdentifier@CCabObj@@0IA, eax; uint CCabObj::s_ZoneIdentifier
0x18000bd5b  test    eax, eax
0x18000bd5d  jz      loc_18000BE43
0x18000bd63  movzx   ecx, word ptr [rbx]; this
0x18000bd66  cmp     ecx, eax
0x18000bd68  jnz     short loc_18000BD9D
0x18000bd6a  cmp     [rbx+8], r13
0x18000bd6e  jnz     short loc_18000BD93
0x18000bd70  test    byte ptr [rbx+10h], 1
0x18000bd74  jz      short loc_18000BD93
0x18000bd76  cmp     dword ptr [rbx+14h], 0FFFFFFFFh
0x18000bd7a  jnz     short loc_18000BD93
0x18000bd7c  test    byte ptr [rbx+18h], 1
0x18000bd80  jz      short loc_18000BD93
0x18000bd82  lea     rcx, [rsi-10h]; this
0x18000bd86  mov     rdx, r14; struct tagSTGMEDIUM *
0x18000bd89  call    ?RenderZoneIdentifier@CCabObj@@AEAAJPEAUtagSTGMEDIUM@@@Z; CCabObj::RenderZoneIdentifier(tagSTGMEDIUM *)
0x18000bd8e  jmp     loc_18000BE48
0x18000bd93  mov     eax, 80070057h
0x18000bd98  jmp     loc_18000BE48
0x18000bd9d  call    ?InitHIDA@CCabObj@@AEAAHXZ; CCabObj::InitHIDA(void)
0x18000bda2  test    eax, eax
0x18000bda4  jz      loc_18000BE43
0x18000bdaa  movzx   eax, word ptr [rbx]
0x18000bdad  cmp     eax, cs:?s_uHIDA@CCabObj@@0IA; uint CCabObj::s_uHIDA
0x18000bdb3  jnz     loc_18000BE3C
0x18000bdb9  mov     edi, 80070057h
0x18000bdbe  cmp     [rbx+8], r13
0x18000bdc2  jnz     short loc_18000BE38
0x18000bdc4  test    byte ptr [rbx+10h], 1
0x18000bdc8  jz      short loc_18000BE38
0x18000bdca  cmp     dword ptr [rbx+14h], 0FFFFFFFFh
0x18000bdce  jnz     short loc_18000BE38
0x18000bdd0  test    byte ptr [rbx+18h], 1
0x18000bdd4  jz      short loc_18000BE38
0x18000bdd6  mov     rcx, [rsi+38h]
0x18000bdda  lea     rdx, [rsp+68h+FileTime]
0x18000bddf  mov     qword ptr [rsp+68h+FileTime.dwLowDateTime], r13
0x18000bde4  mov     rax, [rcx]
0x18000bde7  mov     rax, [rax+28h]
0x18000bdeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bdf0  mov     edi, eax
0x18000bdf2  test    eax, eax
0x18000bdf4  js      short loc_18000BE38
0x18000bdf6  lea     rcx, [rsi+18h]; this
0x18000bdfa  call    ?GetArray@CCabItemList@@QEAAPEAPEFAU_CABITEM@@XZ; CCabItemList::GetArray(void)
0x18000bdff  mov     r8, rax
0x18000be02  call    ?GetCount@CCabItemList@@QEAAIXZ; CCabItemList::GetCount(void)
0x18000be07  mov     rcx, qword ptr [rsp+68h+FileTime.dwLowDateTime]; Src
0x18000be0c  mov     edx, eax; unsigned int
0x18000be0e  call    ?HIDA_Create@@YAPEAXPEFBU_ITEMIDLIST@@IPEAPEFBU1@@Z; HIDA_Create(_ITEMIDLIST const *,uint,_ITEMIDLIST const * *)
0x18000be13  test    rax, rax
0x18000be16  jz      short loc_18000BE28
0x18000be18  mov     dword ptr [r14], 1
0x18000be1f  mov     edi, r13d
0x18000be22  mov     [r14+8], rax
0x18000be26  jmp     short loc_18000BE2D
0x18000be28  mov     edi, 8007000Eh
0x18000be2d  mov     rcx, qword ptr [rsp+68h+FileTime.dwLowDateTime]; pidl
0x18000be32  call    cs:__imp_ILFree
0x18000be38  mov     eax, edi
0x18000be3a  jmp     short loc_18000BE48
0x18000be3c  mov     eax, 80004001h
0x18000be41  jmp     short loc_18000BE48
0x18000be43  mov     eax, 8000FFFFh
0x18000be48  mov     rcx, [rsp+68h+var_40]
0x18000be4d  xor     rcx, rsp; StackCookie
0x18000be50  call    __security_check_cookie
0x18000be55  mov     rbx, [rsp+68h+arg_18]
0x18000be5d  add     rsp, 30h
0x18000be61  pop     r15
0x18000be63  pop     r14
0x18000be65  pop     r13
0x18000be67  pop     r12
0x18000be69  pop     rdi
0x18000be6a  pop     rsi
0x18000be6b  pop     rbp
0x18000be6c  retn
```
