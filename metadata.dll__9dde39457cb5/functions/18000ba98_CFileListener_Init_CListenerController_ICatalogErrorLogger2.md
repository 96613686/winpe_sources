# CFileListener::Init(CListenerController *,ICatalogErrorLogger2 *)

- ea: `0x18000ba98`
- end: `0x18000c23e`
- name: `?Init@CFileListener@@AEAAJPEAVCListenerController@@PEAUICatalogErrorLogger2@@@Z`
- size: `1958`
- prototype: `__int64 __fastcall(CFileListener *__hidden this, struct CListenerController *, struct ICatalogErrorLogger2 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000f128`

## callees

- `0x180008a14`
- `0x18000ba98`
- `0x18000c244`
- `0x18000ea7c`
- `0x18000eb08`
- `0x180031010`

## import_xrefs

- `IisRTL!PuDbgPrintW` at `0x18000bb64`
- `IisRTL!PuDbgPrintW` at `0x18000bb64`
- `IISCFG!DllGetSimpleObjectByIDEx` at `0x18000bb20`
- `IISCFG!DllGetSimpleObjectByIDEx` at `0x18000bb20`

## string_xrefs

- `0x18000bb52`: `[CFileListener::Init] Unable to get the dispenser. DllGetSimpleObjectByIDEx failed with hr = 0x%x.\n`
- `0x18000c0cb`: `EditWhileRunning_Metabase.xml`
- `0x18000c14d`: `EditWhileRunning_MBSchema.xml`
- `0x18000c1c5`: `MetaBase.xml`

## pseudocode

```c
__int64 __fastcall CFileListener::Init(
        CFileListener *this,
        struct CListenerController *a2,
        struct ICatalogErrorLogger2 *a3)
{
  struct CMDCOMSrvFactory *v5; // rcx
  int v6; // ebx
  int SimpleObjectByIDEx; // eax
  unsigned __int64 v8; // rcx
  unsigned __int16 *v9; // rax
  unsigned __int64 v10; // rcx
  unsigned __int16 *v11; // rax
  unsigned __int64 v12; // rcx
  unsigned __int16 *v13; // rax
  unsigned __int64 v14; // rcx
  unsigned __int16 *v15; // rax
  bool v16; // zf
  unsigned __int64 v17; // rcx
  unsigned __int16 *v18; // rax
  unsigned __int64 v19; // rcx
  unsigned __int16 *v20; // rax
  unsigned __int64 v21; // rcx
  unsigned __int16 *v22; // rax
  unsigned __int64 v23; // rcx
  unsigned __int16 *v24; // rax
  unsigned __int64 v25; // rcx
  unsigned __int16 *v26; // rax
  unsigned __int64 v27; // rcx
  unsigned __int16 *v28; // rax
  unsigned __int64 v29; // rcx
  unsigned __int16 *v30; // rax
  unsigned __int64 v31; // rcx
  unsigned __int16 *v32; // rax
  unsigned int v33; // eax
  unsigned __int64 v34; // rcx
  unsigned __int16 *v35; // rax
  unsigned int v36; // eax
  unsigned __int64 v37; // rcx
  unsigned __int16 *v38; // rax
  unsigned int v39; // eax
  unsigned __int64 v40; // rcx
  unsigned __int16 *v41; // rax
  int v43; // [rsp+28h] [rbp-30h]

  if ( !a3 || !a2 )
    return (unsigned int)-2147024809;
  *((_QWORD *)this + 70) = a3;
  (*(void (__fastcall **)(struct ICatalogErrorLogger2 *))(*(_QWORD *)a3 + 8LL))(a3);
  v5 = g_pFactory;
  *((_QWORD *)this + 75) = a2;
  v6 = (*(__int64 (__fastcall **)(struct CMDCOMSrvFactory *, _QWORD, GUID *, char *))(*(_QWORD *)v5 + 24LL))(
         v5,
         0,
         &IID_IMDCOM3,
         (char *)this + 568);
  if ( v6 < 0 )
    return (unsigned int)v6;
  SimpleObjectByIDEx = DllGetSimpleObjectByIDEx(1, &IID_ISimpleTableDispenser2, (char *)this + 16, L"IIS");
  v6 = SimpleObjectByIDEx;
  if ( SimpleObjectByIDEx < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      v43 = SimpleObjectByIDEx;
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\listener.cpp",
        235,
        "CFileListener::Init",
        L"[CFileListener::Init] Unable to get the dispenser. DllGetSimpleObjectByIDEx failed with hr = 0x%x.\n",
        v43);
    }
    return (unsigned int)v6;
  }
  if ( !g_wszHistoryFileDir
    || !g_wszRealFileName
    || !g_wszRealFileNameWithoutPath
    || !g_wszRealFileNameWithoutPathWithoutExtension
    || !g_wszSchemaFileName
    || !g_wszSchemaFileNameWithoutPath
    || !g_wszSchemaFileNameWithoutPathWithoutExtension
    || !g_wszErrorFileSearchString
    || !g_wszHistoryFileSearchString )
  {
    return (unsigned int)-2147024809;
  }
  v8 = g_cchHistoryFileDir + 1;
  if ( (unsigned int)v8 < g_cchHistoryFileDir )
    return (unsigned int)-2147024362;
  v9 = (unsigned __int16 *)operator new[](saturated_mul(v8, 2u));
  *((_QWORD *)this + 3) = v9;
  if ( !v9 )
    return (unsigned int)-2147024882;
  v6 = StringCchCopyW(v9, g_cchHistoryFileDir + 1, g_wszHistoryFileDir);
  if ( v6 < 0 )
    return (unsigned int)v6;
  *((_DWORD *)this + 8) = g_cchHistoryFileDir;
  v10 = g_cchRealFileName + 1;
  if ( (unsigned int)v10 < g_cchRealFileName )
    return (unsigned int)-2147024362;
  v11 = (unsigned __int16 *)operator new[](saturated_mul(v10, 2u));
  *((_QWORD *)this + 5) = v11;
  if ( !v11 )
    return (unsigned int)-2147024882;
  v6 = StringCchCopyW(v11, g_cchRealFileName + 1, g_wszRealFileName);
  if ( v6 < 0 )
    return (unsigned int)v6;
  *((_DWORD *)this + 12) = g_cchRealFileName;
  v12 = g_cchRealFileNameWithoutPath + 1;
  if ( (unsigned int)v12 < g_cchRealFileNameWithoutPath )
    return (unsigned int)-2147024362;
  v13 = (unsigned __int16 *)operator new[](saturated_mul(v12, 2u));
  *((_QWORD *)this + 7) = v13;
  if ( !v13 )
    return (unsigned int)-2147024882;
  v6 = StringCchCopyW(v13, g_cchRealFileNameWithoutPath + 1, g_wszRealFileNameWithoutPath);
  if ( v6 < 0 )
    return (unsigned int)v6;
  *((_DWORD *)this + 16) = g_cchRealFileNameWithoutPath;
  v14 = g_cchRealFileNameWithoutPathWithoutExtension + 1;
  if ( (unsigned int)v14 < g_cchRealFileNameWithoutPathWithoutExtension )
    return (unsigned int)-2147024362;
  v15 = (unsigned __int16 *)operator new[](saturated_mul(v14, 2u));
  *((_QWORD *)this + 9) = v15;
  if ( !v15 )
    return (unsigned int)-2147024882;
  v6 = StringCchCopyW(
         v15,
         g_cchRealFileNameWithoutPathWithoutExtension + 1,
         g_wszRealFileNameWithoutPathWithoutExtension);
  if ( v6 < 0 )
    return (unsigned int)v6;
  v16 = g_wszRealFileNameExtension == 0;
  *((_DWORD *)this + 20) = g_cchRealFileNameWithoutPathWithoutExtension;
  if ( !v16 )
  {
    v17 = g_cchRealFileNameExtension + 1;
    if ( (unsigned int)v17 < g_cchRealFileNameExtension )
      return (unsigned int)-2147024362;
    v18 = (unsigned __int16 *)operator new[](saturated_mul(v17, 2u));
    *((_QWORD *)this + 11) = v18;
    if ( !v18 )
      return (unsigned int)-2147024882;
    v6 = StringCchCopyW(v18, g_cchRealFileNameExtension + 1, g_wszRealFileNameExtension);
    if ( v6 < 0 )
      return (unsigned int)v6;
    *((_DWORD *)this + 24) = g_cchRealFileNameExtension;
  }
  v19 = g_cchSchemaFileName + 1;
  if ( (unsigned int)v19 < g_cchSchemaFileName )
    return (unsigned int)-2147024362;
  v20 = (unsigned __int16 *)operator new[](saturated_mul(v19, 2u));
  *((_QWORD *)this + 13) = v20;
  if ( !v20 )
    return (unsigned int)-2147024882;
  v6 = StringCchCopyW(v20, g_cchSchemaFileName + 1, g_wszSchemaFileName);
  if ( v6 < 0 )
    return (unsigned int)v6;
  *((_DWORD *)this + 28) = g_cchSchemaFileName;
  v21 = g_cchSchemaFileNameWithoutPath + 1;
  if ( (unsigned int)v21 < g_cchSchemaFileNameWithoutPath )
    return (unsigned int)-2147024362;
  v22 = (unsigned __int16 *)operator new[](saturated_mul(v21, 2u));
  *((_QWORD *)this + 15) = v22;
  if ( !v22 )
    return (unsigned int)-2147024882;
  v6 = StringCchCopyW(v22, g_cchSchemaFileNameWithoutPath + 1, g_wszSchemaFileNameWithoutPath);
  if ( v6 < 0 )
    return (unsigned int)v6;
  *((_DWORD *)this + 32) = g_cchSchemaFileNameWithoutPath;
  v23 = g_cchSchemaFileNameWithoutPathWithoutExtension + 1;
  if ( (unsigned int)v23 < g_cchSchemaFileNameWithoutPathWithoutExtension )
    return (unsigned int)-2147024362;
  v24 = (unsigned __int16 *)operator new[](saturated_mul(v23, 2u));
  *((_QWORD *)this + 17) = v24;
  if ( !v24 )
    return (unsigned int)-2147024882;
  v6 = StringCchCopyW(
         v24,
         g_cchSchemaFileNameWithoutPathWithoutExtension + 1,
         g_wszSchemaFileNameWithoutPathWithoutExtension);
  if ( v6 < 0 )
    return (unsigned int)v6;
  v16 = g_wszSchemaFileNameExtension == 0;
  *((_DWORD *)this + 36) = g_cchSchemaFileNameWithoutPathWithoutExtension;
  if ( !v16 )
  {
    v25 = g_cchSchemaFileNameExtension + 1;
    if ( (unsigned int)v25 < g_cchSchemaFileNameExtension )
      return (unsigned int)-2147024362;
    v26 = (unsigned __int16 *)operator new[](saturated_mul(v25, 2u));
    *((_QWORD *)this + 19) = v26;
    if ( !v26 )
      return (unsigned int)-2147024882;
    v6 = StringCchCopyW(v26, g_cchSchemaFileNameExtension + 1, g_wszSchemaFileNameExtension);
    if ( v6 < 0 )
      return (unsigned int)v6;
    *((_DWORD *)this + 40) = g_cchSchemaFileNameExtension;
  }
  v27 = g_cchErrorFileSearchString + 1;
  if ( (unsigned int)v27 < g_cchErrorFileSearchString )
    return (unsigned int)-2147024362;
  v28 = (unsigned __int16 *)operator new[](saturated_mul(v27, 2u));
  *((_QWORD *)this + 21) = v28;
  if ( !v28 )
    return (unsigned int)-2147024882;
  v6 = StringCchCopyW(v28, g_cchErrorFileSearchString + 1, g_wszErrorFileSearchString);
  if ( v6 < 0 )
    return (unsigned int)v6;
  *((_DWORD *)this + 44) = g_cchErrorFileSearchString;
  v29 = g_cchMetabaseDir + 1;
  if ( (unsigned int)v29 < g_cchMetabaseDir )
    return (unsigned int)-2147024362;
  v30 = (unsigned __int16 *)operator new[](saturated_mul(v29, 2u));
  *((_QWORD *)this + 23) = v30;
  if ( !v30 )
    return (unsigned int)-2147024882;
  v6 = StringCchCopyW(v30, g_cchMetabaseDir + 1, g_wszMetabaseDir);
  if ( v6 < 0 )
    return (unsigned int)v6;
  *((_DWORD *)this + 48) = g_cchMetabaseDir;
  v31 = g_cchHistoryFileSearchString + 1;
  if ( (unsigned int)v31 < g_cchHistoryFileSearchString )
    return (unsigned int)-2147024362;
  v32 = (unsigned __int16 *)operator new[](saturated_mul(v31, 2u));
  *((_QWORD *)this + 25) = v32;
  if ( !v32 )
    return (unsigned int)-2147024882;
  v6 = StringCchCopyW(v32, g_cchHistoryFileSearchString + 1, g_wszHistoryFileSearchString);
  if ( v6 < 0 )
    return (unsigned int)v6;
  *((_DWORD *)this + 52) = g_cchHistoryFileSearchString;
  v33 = *((_DWORD *)this + 48) + 30;
  *((_DWORD *)this + 56) = v33;
  v34 = v33 + 1;
  if ( (unsigned int)v34 < v33 )
    return (unsigned int)-2147024362;
  v35 = (unsigned __int16 *)operator new[](saturated_mul(v34, 2u));
  *((_QWORD *)this + 27) = v35;
  if ( !v35 )
    return (unsigned int)-2147024882;
  v6 = StringCchCopyW(v35, (unsigned int)(*((_DWORD *)this + 56) + 1), *((const unsigned __int16 **)this + 23));
  if ( v6 < 0 )
    return (unsigned int)v6;
  v6 = StringCchCatW(
         *((unsigned __int16 **)this + 27),
         (unsigned int)(*((_DWORD *)this + 56) + 1),
         L"EditWhileRunning_Metabase.xml");
  if ( v6 < 0 )
    return (unsigned int)v6;
  v36 = *((_DWORD *)this + 48) + 30;
  *((_DWORD *)this + 60) = v36;
  v37 = v36 + 1;
  if ( (unsigned int)v37 < v36 )
    return (unsigned int)-2147024362;
  v38 = (unsigned __int16 *)operator new[](saturated_mul(v37, 2u));
  *((_QWORD *)this + 29) = v38;
  if ( !v38 )
    return (unsigned int)-2147024882;
  v6 = StringCchCopyW(v38, (unsigned int)(*((_DWORD *)this + 60) + 1), *((const unsigned __int16 **)this + 23));
  if ( v6 < 0 )
    return (unsigned int)v6;
  v6 = StringCchCatW(
         *((unsigned __int16 **)this + 29),
         (unsigned int)(*((_DWORD *)this + 60) + 1),
         L"EditWhileRunning_MBSchema.xml");
  if ( v6 < 0 )
    return (unsigned int)v6;
  v39 = *((_DWORD *)this + 8) + 18;
  *((_DWORD *)this + 64) = v39;
  v40 = v39 + 1;
  if ( (unsigned int)v40 < v39 )
    return (unsigned int)-2147024362;
  v41 = (unsigned __int16 *)operator new[](saturated_mul(v40, 2u));
  *((_QWORD *)this + 31) = v41;
  if ( !v41 )
    return (unsigned int)-2147024882;
  v6 = StringCchCopyW(v41, (unsigned int)(*((_DWORD *)this + 64) + 1), *((const unsigned __int16 **)this + 3));
  if ( v6 >= 0 )
  {
    v6 = StringCchCatW(*((unsigned __int16 **)this + 31), (unsigned int)(*((_DWORD *)this + 64) + 1), L"MetaBase.xml");
    if ( v6 >= 0 )
    {
      v6 = StringCchCatW(*((unsigned __int16 **)this + 31), (unsigned int)(*((_DWORD *)this + 64) + 1), L".tmp");
      if ( v6 >= 0 )
      {
        v6 = CFileListener::InitChangeNotificationData(this);
        if ( v6 >= 0 )
        {
          (***((void (__fastcall ****)(_QWORD, GUID *, _QWORD))this + 71))(
            *((_QWORD *)this + 71),
            &IID_IMSAdminBase_EWR,
            0);
          return 0;
        }
      }
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000ba98  push    rbx
0x18000ba9a  push    rsi
0x18000ba9b  push    rdi
0x18000ba9c  push    r14
0x18000ba9e  push    r15
0x18000baa0  sub     rsp, 30h
0x18000baa4  mov     rbx, rdx
0x18000baa7  mov     rdi, rcx
0x18000baaa  test    r8, r8
0x18000baad  jz      loc_18000C22B
0x18000bab3  test    rdx, rdx
0x18000bab6  jz      loc_18000C22B
0x18000babc  mov     [rcx+230h], r8
0x18000bac3  mov     rcx, r8
0x18000bac6  mov     rax, [r8]
0x18000bac9  mov     rax, [rax+8]
0x18000bacd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bad2  mov     rcx, cs:?g_pFactory@@3PEAVCMDCOMSrvFactory@@EA; CMDCOMSrvFactory * g_pFactory
0x18000bad9  lea     rsi, [rdi+238h]
0x18000bae0  mov     [rdi+258h], rbx
0x18000bae7  lea     r8, IID_IMDCOM3
0x18000baee  mov     r9, rsi
0x18000baf1  xor     edx, edx
0x18000baf3  mov     rax, [rcx]
0x18000baf6  mov     rax, [rax+18h]
0x18000bafa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000baff  mov     ebx, eax
0x18000bb01  test    eax, eax
0x18000bb03  js      loc_18000C230
0x18000bb09  lea     r8, [rdi+10h]
0x18000bb0d  mov     ecx, 1
0x18000bb12  lea     r9, aIis; "IIS"
0x18000bb19  lea     rdx, IID_ISimpleTableDispenser2
0x18000bb20  call    cs:__imp_DllGetSimpleObjectByIDEx
0x18000bb26  mov     ebx, eax
0x18000bb28  test    eax, eax
0x18000bb2a  jns     short loc_18000BB6F
0x18000bb2c  test    byte ptr cs:g_dwDebugFlags, 3
0x18000bb33  jz      loc_18000C230
0x18000bb39  mov     rcx, cs:g_pDebug
0x18000bb40  lea     r9, aCfilelistenerI; "CFileListener::Init"
0x18000bb47  mov     [rsp+58h+var_30], eax
0x18000bb4b  lea     rdx, aInetsrvIisMbMe_5; "inetsrv\\iis\\mb\\metadata\\listener.cp"...
0x18000bb52  lea     rax, aCfilelistenerI_0; "[CFileListener::Init] Unable to get the"...
0x18000bb59  mov     r8d, 0EBh
0x18000bb5f  mov     [rsp+58h+var_38], rax
0x18000bb64  call    cs:__imp_PuDbgPrintW
0x18000bb6a  jmp     loc_18000C230
0x18000bb6f  cmp     cs:?g_wszHistoryFileDir@@3PEAGEA, 0; ushort * g_wszHistoryFileDir
0x18000bb77  jz      loc_18000C22B
0x18000bb7d  cmp     cs:?g_wszRealFileName@@3PEAGEA, 0; ushort * g_wszRealFileName
0x18000bb85  jz      loc_18000C22B
0x18000bb8b  cmp     cs:?g_wszRealFileNameWithoutPath@@3PEAGEA, 0; ushort * g_wszRealFileNameWithoutPath
0x18000bb93  jz      loc_18000C22B
0x18000bb99  cmp     cs:?g_wszRealFileNameWithoutPathWithoutExtension@@3PEAGEA, 0; ushort * g_wszRealFileNameWithoutPathWithoutExtension
0x18000bba1  jz      loc_18000C22B
0x18000bba7  cmp     cs:?g_wszSchemaFileName@@3PEAGEA, 0; ushort * g_wszSchemaFileName
0x18000bbaf  jz      loc_18000C22B
0x18000bbb5  cmp     cs:?g_wszSchemaFileNameWithoutPath@@3PEAGEA, 0; ushort * g_wszSchemaFileNameWithoutPath
0x18000bbbd  jz      loc_18000C22B
0x18000bbc3  cmp     cs:?g_wszSchemaFileNameWithoutPathWithoutExtension@@3PEAGEA, 0; ushort * g_wszSchemaFileNameWithoutPathWithoutExtension
0x18000bbcb  jz      loc_18000C22B
0x18000bbd1  cmp     cs:?g_wszErrorFileSearchString@@3PEAGEA, 0; ushort * g_wszErrorFileSearchString
0x18000bbd9  jz      loc_18000C22B
0x18000bbdf  cmp     cs:?g_wszHistoryFileSearchString@@3PEAGEA, 0; ushort * g_wszHistoryFileSearchString
0x18000bbe7  jz      loc_18000C22B
0x18000bbed  mov     eax, cs:?g_cchHistoryFileDir@@3KA; ulong g_cchHistoryFileDir
0x18000bbf3  lea     ecx, [rax+1]
0x18000bbf6  cmp     ecx, eax
0x18000bbf8  jnb     short loc_18000BC04
0x18000bbfa  mov     ebx, 80070216h
0x18000bbff  jmp     loc_18000C230
0x18000bc04  mov     r14d, 2
0x18000bc0a  mov     eax, r14d
0x18000bc0d  mul     rcx
0x18000bc10  lea     r15, [r14-3]
0x18000bc14  cmovb   rax, r15
0x18000bc18  mov     rcx, rax; unsigned __int64
0x18000bc1b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000bc20  mov     [rdi+18h], rax
0x18000bc24  mov     rcx, rax; unsigned __int16 *
0x18000bc27  test    rax, rax
0x18000bc2a  jnz     short loc_18000BC36
0x18000bc2c  mov     ebx, 8007000Eh
0x18000bc31  jmp     loc_18000C230
0x18000bc36  mov     edx, cs:?g_cchHistoryFileDir@@3KA; ulong g_cchHistoryFileDir
0x18000bc3c  mov     r8, cs:?g_wszHistoryFileDir@@3PEAGEA; unsigned __int16 *
0x18000bc43  inc     edx; unsigned __int64
0x18000bc45  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000bc4a  mov     ebx, eax
0x18000bc4c  test    eax, eax
0x18000bc4e  js      loc_18000C230
0x18000bc54  mov     eax, cs:?g_cchHistoryFileDir@@3KA; ulong g_cchHistoryFileDir
0x18000bc5a  mov     [rdi+20h], eax
0x18000bc5d  mov     eax, cs:?g_cchRealFileName@@3KA; ulong g_cchRealFileName
0x18000bc63  lea     ecx, [rax+1]
0x18000bc66  cmp     ecx, eax
0x18000bc68  jb      short loc_18000BBFA
0x18000bc6a  mov     rax, r14
0x18000bc6d  mul     rcx
0x18000bc70  cmovb   rax, r15
0x18000bc74  mov     rcx, rax; unsigned __int64
0x18000bc77  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000bc7c  mov     [rdi+28h], rax
0x18000bc80  mov     rcx, rax; unsigned __int16 *
0x18000bc83  test    rax, rax
0x18000bc86  jz      short loc_18000BC2C
0x18000bc88  mov     edx, cs:?g_cchRealFileName@@3KA; ulong g_cchRealFileName
0x18000bc8e  mov     r8, cs:?g_wszRealFileName@@3PEAGEA; unsigned __int16 *
0x18000bc95  inc     edx; unsigned __int64
0x18000bc97  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000bc9c  mov     ebx, eax
0x18000bc9e  test    eax, eax
0x18000bca0  js      loc_18000C230
0x18000bca6  mov     eax, cs:?g_cchRealFileName@@3KA; ulong g_cchRealFileName
0x18000bcac  mov     [rdi+30h], eax
0x18000bcaf  mov     eax, cs:?g_cchRealFileNameWithoutPath@@3KA; ulong g_cchRealFileNameWithoutPath
0x18000bcb5  lea     ecx, [rax+1]
0x18000bcb8  cmp     ecx, eax
0x18000bcba  jb      loc_18000BBFA
0x18000bcc0  mov     rax, r14
0x18000bcc3  mul     rcx
0x18000bcc6  cmovb   rax, r15
0x18000bcca  mov     rcx, rax; unsigned __int64
0x18000bccd  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000bcd2  mov     [rdi+38h], rax
0x18000bcd6  mov     rcx, rax; unsigned __int16 *
0x18000bcd9  test    rax, rax
0x18000bcdc  jz      loc_18000BC2C
0x18000bce2  mov     edx, cs:?g_cchRealFileNameWithoutPath@@3KA; ulong g_cchRealFileNameWithoutPath
0x18000bce8  mov     r8, cs:?g_wszRealFileNameWithoutPath@@3PEAGEA; unsigned __int16 *
0x18000bcef  inc     edx; unsigned __int64
0x18000bcf1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000bcf6  mov     ebx, eax
0x18000bcf8  test    eax, eax
0x18000bcfa  js      loc_18000C230
0x18000bd00  mov     eax, cs:?g_cchRealFileNameWithoutPath@@3KA; ulong g_cchRealFileNameWithoutPath
0x18000bd06  mov     [rdi+40h], eax
0x18000bd09  mov     eax, cs:?g_cchRealFileNameWithoutPathWithoutExtension@@3KA; ulong g_cchRealFileNameWithoutPathWithoutExtension
0x18000bd0f  lea     ecx, [rax+1]
0x18000bd12  cmp     ecx, eax
0x18000bd14  jb      loc_18000BBFA
0x18000bd1a  mov     rax, r14
0x18000bd1d  mul     rcx
0x18000bd20  cmovb   rax, r15
0x18000bd24  mov     rcx, rax; unsigned __int64
0x18000bd27  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000bd2c  mov     [rdi+48h], rax
0x18000bd30  mov     rcx, rax; unsigned __int16 *
0x18000bd33  test    rax, rax
0x18000bd36  jz      loc_18000BC2C
0x18000bd3c  mov     edx, cs:?g_cchRealFileNameWithoutPathWithoutExtension@@3KA; ulong g_cchRealFileNameWithoutPathWithoutExtension
0x18000bd42  mov     r8, cs:?g_wszRealFileNameWithoutPathWithoutExtension@@3PEAGEA; unsigned __int16 *
0x18000bd49  inc     edx; unsigned __int64
0x18000bd4b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000bd50  mov     ebx, eax
0x18000bd52  test    eax, eax
0x18000bd54  js      loc_18000C230
0x18000bd5a  cmp     cs:?g_wszRealFileNameExtension@@3PEAGEA, 0; ushort * g_wszRealFileNameExtension
0x18000bd62  mov     eax, cs:?g_cchRealFileNameWithoutPathWithoutExtension@@3KA; ulong g_cchRealFileNameWithoutPathWithoutExtension
0x18000bd68  mov     [rdi+50h], eax
0x18000bd6b  jz      short loc_18000BDC7
0x18000bd6d  mov     eax, cs:?g_cchRealFileNameExtension@@3KA; ulong g_cchRealFileNameExtension
0x18000bd73  lea     ecx, [rax+1]
0x18000bd76  cmp     ecx, eax
0x18000bd78  jb      loc_18000BBFA
0x18000bd7e  mov     rax, r14
0x18000bd81  mul     rcx
0x18000bd84  cmovb   rax, r15
0x18000bd88  mov     rcx, rax; unsigned __int64
0x18000bd8b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000bd90  mov     [rdi+58h], rax
0x18000bd94  mov     rcx, rax; unsigned __int16 *
0x18000bd97  test    rax, rax
0x18000bd9a  jz      loc_18000BC2C
0x18000bda0  mov     edx, cs:?g_cchRealFileNameExtension@@3KA; ulong g_cchRealFileNameExtension
0x18000bda6  mov     r8, cs:?g_wszRealFileNameExtension@@3PEAGEA; unsigned __int16 *
0x18000bdad  inc     edx; unsigned __int64
0x18000bdaf  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000bdb4  mov     ebx, eax
0x18000bdb6  test    eax, eax
0x18000bdb8  js      loc_18000C230
0x18000bdbe  mov     eax, cs:?g_cchRealFileNameExtension@@3KA; ulong g_cchRealFileNameExtension
0x18000bdc4  mov     [rdi+60h], eax
0x18000bdc7  mov     eax, cs:?g_cchSchemaFileName@@3KA; ulong g_cchSchemaFileName
0x18000bdcd  lea     ecx, [rax+1]
0x18000bdd0  cmp     ecx, eax
0x18000bdd2  jb      loc_18000BBFA
0x18000bdd8  mov     rax, r14
0x18000bddb  mul     rcx
0x18000bdde  cmovb   rax, r15
0x18000bde2  mov     rcx, rax; unsigned __int64
0x18000bde5  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000bdea  mov     [rdi+68h], rax
0x18000bdee  mov     rcx, rax; unsigned __int16 *
0x18000bdf1  test    rax, rax
0x18000bdf4  jz      loc_18000BC2C
0x18000bdfa  mov     edx, cs:?g_cchSchemaFileName@@3KA; ulong g_cchSchemaFileName
0x18000be00  mov     r8, cs:?g_wszSchemaFileName@@3PEAGEA; unsigned __int16 *
0x18000be07  inc     edx; unsigned __int64
0x18000be09  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000be0e  mov     ebx, eax
0x18000be10  test    eax, eax
0x18000be12  js      loc_18000C230
0x18000be18  mov     eax, cs:?g_cchSchemaFileName@@3KA; ulong g_cchSchemaFileName
0x18000be1e  mov     [rdi+70h], eax
0x18000be21  mov     eax, cs:?g_cchSchemaFileNameWithoutPath@@3KA; ulong g_cchSchemaFileNameWithoutPath
0x18000be27  lea     ecx, [rax+1]
0x18000be2a  cmp     ecx, eax
0x18000be2c  jb      loc_18000BBFA
0x18000be32  mov     rax, r14
0x18000be35  mul     rcx
0x18000be38  cmovb   rax, r15
0x18000be3c  mov     rcx, rax; unsigned __int64
0x18000be3f  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000be44  mov     [rdi+78h], rax
0x18000be48  mov     rcx, rax; unsigned __int16 *
0x18000be4b  test    rax, rax
0x18000be4e  jz      loc_18000BC2C
0x18000be54  mov     edx, cs:?g_cchSchemaFileNameWithoutPath@@3KA; ulong g_cchSchemaFileNameWithoutPath
0x18000be5a  mov     r8, cs:?g_wszSchemaFileNameWithoutPath@@3PEAGEA; unsigned __int16 *
0x18000be61  inc     edx; unsigned __int64
0x18000be63  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000be68  mov     ebx, eax
0x18000be6a  test    eax, eax
0x18000be6c  js      loc_18000C230
0x18000be72  mov     eax, cs:?g_cchSchemaFileNameWithoutPath@@3KA; ulong g_cchSchemaFileNameWithoutPath
0x18000be78  mov     [rdi+80h], eax
0x18000be7e  mov     eax, cs:?g_cchSchemaFileNameWithoutPathWithoutExtension@@3KA; ulong g_cchSchemaFileNameWithoutPathWithoutExtension
0x18000be84  lea     ecx, [rax+1]
0x18000be87  cmp     ecx, eax
0x18000be89  jb      loc_18000BBFA
0x18000be8f  mov     rax, r14
0x18000be92  mul     rcx
0x18000be95  cmovb   rax, r15
0x18000be99  mov     rcx, rax; unsigned __int64
0x18000be9c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000bea1  mov     [rdi+88h], rax
0x18000bea8  mov     rcx, rax; unsigned __int16 *
0x18000beab  test    rax, rax
0x18000beae  jz      loc_18000BC2C
0x18000beb4  mov     edx, cs:?g_cchSchemaFileNameWithoutPathWithoutExtension@@3KA; ulong g_cchSchemaFileNameWithoutPathWithoutExtension
0x18000beba  mov     r8, cs:?g_wszSchemaFileNameWithoutPathWithoutExtension@@3PEAGEA; unsigned __int16 *
0x18000bec1  inc     edx; unsigned __int64
0x18000bec3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000bec8  mov     ebx, eax
0x18000beca  test    eax, eax
0x18000becc  js      loc_18000C230
0x18000bed2  cmp     cs:?g_wszSchemaFileNameExtension@@3PEAGEA, 0; ushort * g_wszSchemaFileNameExtension
0x18000beda  mov     eax, cs:?g_cchSchemaFileNameWithoutPathWithoutExtension@@3KA; ulong g_cchSchemaFileNameWithoutPathWithoutExtension
0x18000bee0  mov     [rdi+90h], eax
0x18000bee6  jz      short loc_18000BF48
0x18000bee8  mov     eax, cs:?g_cchSchemaFileNameExtension@@3KA; ulong g_cchSchemaFileNameExtension
0x18000beee  lea     ecx, [rax+1]
0x18000bef1  cmp     ecx, eax
0x18000bef3  jb      loc_18000BBFA
0x18000bef9  mov     rax, r14
0x18000befc  mul     rcx
0x18000beff  cmovb   rax, r15
0x18000bf03  mov     rcx, rax; unsigned __int64
0x18000bf06  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000bf0b  mov     [rdi+98h], rax
0x18000bf12  mov     rcx, rax; unsigned __int16 *
0x18000bf15  test    rax, rax
0x18000bf18  jz      loc_18000BC2C
0x18000bf1e  mov     edx, cs:?g_cchSchemaFileNameExtension@@3KA; ulong g_cchSchemaFileNameExtension
0x18000bf24  mov     r8, cs:?g_wszSchemaFileNameExtension@@3PEAGEA; unsigned __int16 *
0x18000bf2b  inc     edx; unsigned __int64
0x18000bf2d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000bf32  mov     ebx, eax
0x18000bf34  test    eax, eax
0x18000bf36  js      loc_18000C230
0x18000bf3c  mov     eax, cs:?g_cchSchemaFileNameExtension@@3KA; ulong g_cchSchemaFileNameExtension
0x18000bf42  mov     [rdi+0A0h], eax
0x18000bf48  mov     eax, cs:?g_cchErrorFileSearchString@@3KA; ulong g_cchErrorFileSearchString
0x18000bf4e  lea     ecx, [rax+1]
0x18000bf51  cmp     ecx, eax
0x18000bf53  jb      loc_18000BBFA
0x18000bf59  mov     rax, r14
0x18000bf5c  mul     rcx
0x18000bf5f  cmovb   rax, r15
0x18000bf63  mov     rcx, rax; unsigned __int64
0x18000bf66  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000bf6b  mov     [rdi+0A8h], rax
0x18000bf72  mov     rcx, rax; unsigned __int16 *
0x18000bf75  test    rax, rax
0x18000bf78  jz      loc_18000BC2C
0x18000bf7e  mov     edx, cs:?g_cchErrorFileSearchString@@3KA; ulong g_cchErrorFileSearchString
0x18000bf84  mov     r8, cs:?g_wszErrorFileSearchString@@3PEAGEA; unsigned __int16 *
0x18000bf8b  inc     edx; unsigned __int64
0x18000bf8d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000bf92  mov     ebx, eax
0x18000bf94  test    eax, eax
0x18000bf96  js      loc_18000C230
0x18000bf9c  mov     eax, cs:?g_cchErrorFileSearchString@@3KA; ulong g_cchErrorFileSearchString
0x18000bfa2  mov     [rdi+0B0h], eax
0x18000bfa8  mov     eax, cs:?g_cchMetabaseDir@@3KA; ulong g_cchMetabaseDir
0x18000bfae  lea     ecx, [rax+1]
0x18000bfb1  cmp     ecx, eax
0x18000bfb3  jb      loc_18000BBFA
  ... truncated ...
```
