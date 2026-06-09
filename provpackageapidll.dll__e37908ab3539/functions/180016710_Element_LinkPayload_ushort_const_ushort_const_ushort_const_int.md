# Element::LinkPayload(ushort const *,ushort const *,ushort const *,int)

- ea: `0x180016710`
- end: `0x180016c49`
- name: `?LinkPayload@Element@@EEAAJPEBG00H@Z`
- size: `1337`
- prototype: `__int64 __fastcall(Element *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, reparse_path, installer_update, broker_com_uri`

## callees

- `0x180001510`
- `0x180001e66`
- `0x1800020a8`
- `0x1800020ec`
- `0x180006014`
- `0x18000741c`
- `0x18000fc10`
- `0x18000fc8c`
- `0x180016710`
- `0x180018440`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016901`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016952`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016ab6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016b07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016901`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016952`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016ab6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016b07`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016be9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016bfc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016be9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016bfc`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180016b9a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180016b9a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180016aa2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180016aa2`
- `WIMGAPI!WIMFindFirstImageFileEx` at `0x1800168ee`
- `WIMGAPI!WIMFindFirstImageFileEx` at `0x1800168ee`
- `WIMGAPI!WIMCloseHandle` at `0x1800169fe`
- `WIMGAPI!WIMCloseHandle` at `0x180016a6d`
- `WIMGAPI!WIMCloseHandle` at `0x180016c0c`
- `WIMGAPI!WIMCloseHandle` at `0x1800169fe`
- `WIMGAPI!WIMCloseHandle` at `0x180016a6d`
- `WIMGAPI!WIMCloseHandle` at `0x180016c0c`
- `WOFUTIL!WofSetFileDataLocation` at `0x180016b8a`
- `WOFUTIL!WofSetFileDataLocation` at `0x180016b8a`

## string_xrefs

- `0x1800167e2`: `    Failed to allocate spSourcePath.get()`
- `0x1800167ca`: `Element::LinkPayload`
- `0x180016822`: `Element::LinkPayload`
- `0x18001686c`: `Element::LinkPayload`
- `0x18001692a`: `Element::LinkPayload`
- `0x1800169cc`: `Element::LinkPayload`
- `0x180016a3b`: `Element::LinkPayload`
- `0x180016adf`: `Element::LinkPayload`
- `0x180016bb4`: `Element::LinkPayload`
- `0x18001683c`: `    Failed to assemble source path (index)`
- `0x180016886`: `    Failed to assemble source path (path key)`
- `0x180016989`: `Cannot link this payload; will copy instead`
- `0x180016af9`: `    Failed to create reparse point`

## pseudocode

```c
__int64 __fastcall Element::LinkPayload(
        Element *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int a5)
{
  __int64 v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rdx
  unsigned __int64 v11; // rsi
  unsigned __int64 v12; // rax
  WCHAR *v13; // rax
  WCHAR *v14; // r15
  unsigned int v15; // ebx
  HRESULT v16; // eax
  ULONG v17; // r9d
  const struct std::nothrow_t *v18; // rdx
  HRESULT v19; // eax
  __int64 ImageFile; // rbx
  signed int LastError; // eax
  signed int v22; // eax
  int v23; // eax
  HRESULT v24; // r14d
  int DataSourceId; // eax
  unsigned int v26; // edi
  HANDLE FileW; // rdi
  signed int v28; // eax
  signed int v29; // eax
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  __int64 dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  __int64 dwCreationDispositionb; // [rsp+20h] [rbp-E0h]
  __int64 dwFlagsAndAttributes; // [rsp+28h] [rbp-D8h]
  union _LARGE_INTEGER v35; // [rsp+40h] [rbp-C0h] BYREF
  __int128 Buf2; // [rsp+48h] [rbp-B8h] BYREF
  int v37; // [rsp+58h] [rbp-A8h]
  WCHAR *v38; // [rsp+60h] [rbp-A0h]
  __int64 v39; // [rsp+68h] [rbp-98h]
  HANDLE v40; // [rsp+70h] [rbp-90h]
  _BYTE v41[592]; // [rsp+80h] [rbp-80h] BYREF
  __int128 Buf1; // [rsp+2D0h] [rbp+1D0h] BYREF
  __int64 v43; // [rsp+2E0h] [rbp+1E0h]
  __int128 v44; // [rsp+2E8h] [rbp+1E8h]
  __int128 v45; // [rsp+2F8h] [rbp+1F8h]
  __int128 v46; // [rsp+308h] [rbp+208h]
  __int64 v47; // [rsp+318h] [rbp+218h]
  union _LARGE_INTEGER ExternalFileInfo; // [rsp+320h] [rbp+220h] BYREF
  __int128 v49; // [rsp+328h] [rbp+228h]
  int v50; // [rsp+338h] [rbp+238h]
  int v51; // [rsp+33Ch] [rbp+23Ch]

  v8 = -1;
  do
    ++v8;
  while ( a3[v8] );
  v9 = -1;
  do
    ++v9;
  while ( *(_WORD *)(*((_QWORD *)this + 3) + 2 * v9) );
  v10 = -1;
  do
    ++v10;
  while ( *(_WORD *)(*((_QWORD *)this + 4) + 2 * v10) );
  v11 = v8 + 7 + v10 + v9;
  v12 = 2 * v11;
  if ( !is_mul_ok(v11, 2u) )
    v12 = -1;
  v13 = (WCHAR *)operator new[](v12, (const struct std::nothrow_t *)&std::nothrow);
  v14 = v13;
  v38 = v13;
  if ( v13 )
  {
    v16 = PathCchCombineEx(v13, v11, *((PCWSTR *)this + 3), *((PCWSTR *)this + 4), dwCreationDisposition);
    v15 = v16;
    if ( v16 < 0 )
    {
      LODWORD(dwCreationDispositiona) = 386;
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "Element::LinkPayload",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
        dwCreationDispositiona,
        v16);
      ProvPackageLog(3, L"    Failed to assemble source path (index)");
LABEL_49:
      operator delete(v14, v18);
      return v15;
    }
    v19 = PathCchAppendEx(v14, v11, a3, v17);
    v15 = v19;
    if ( v19 < 0 )
    {
      LODWORD(dwCreationDispositiona) = 389;
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "Element::LinkPayload",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
        dwCreationDispositiona,
        v19);
      ProvPackageLog(3, L"    Failed to assemble source path (path key)");
      goto LABEL_49;
    }
    memset_0(v41, 0, sizeof(v41));
    Buf1 = 0;
    v43 = 0;
    v44 = 0;
    v45 = 0;
    v46 = 0;
    v47 = 0;
    ImageFile = WIMFindFirstImageFileEx(*(_QWORD *)(*((_QWORD *)this + 1) + 16LL), v14, 672, v41);
    v39 = ImageFile;
    if ( !ImageFile )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      LODWORD(dwCreationDispositiona) = 394;
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "Element::LinkPayload",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
        dwCreationDispositiona,
        LastError);
      ProvPackageLog(3, L"    Failed to find payload file");
      v22 = GetLastError();
      if ( v22 > 0 )
        v22 = (unsigned __int16)v22 | 0x80070000;
      v15 = v22;
      goto LABEL_49;
    }
    if ( DWORD2(v45) )
    {
      if ( (_QWORD)v45 )
      {
        ProvPackageLog(2, L"Cannot link this payload; will copy instead");
        v23 = (*(__int64 (__fastcall **)(Element *, const unsigned __int16 *, const unsigned __int16 *, _QWORD))(*(_QWORD *)this + 48LL))(
                this,
                a3,
                a4,
                a5);
        v24 = v23;
        if ( v23 < 0 )
        {
          LODWORD(dwCreationDispositiona) = 401;
          ProvPackageLog(
            3,
            L"%hs (%hs:%d) - 0x%08x:",
            "Element::LinkPayload",
            "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
            dwCreationDispositiona,
            v23);
          ProvPackageLog(3, L"    Failed to retrieve payload");
LABEL_26:
          if ( ImageFile != -1 )
            WIMCloseHandle(ImageFile);
          v15 = v24;
          goto LABEL_49;
        }
      }
    }
    v35.QuadPart = 0;
    DataSourceId = ProvisioningPackage::GetDataSourceId(*((char **)this + 1), a4, &v35);
    v26 = DataSourceId;
    if ( DataSourceId >= 0 )
    {
      FileW = CreateFileW(a4, 0x12019Fu, 7u, 0, (unsigned int)(a5 != 0) + 1, 0x2200000u, 0);
      v40 = FileW;
      if ( FileW != (HANDLE)-1LL )
      {
        Buf2 = 0;
        v37 = 0;
        if ( !memcmp_0(&Buf1, &Buf2, 0x14u)
          || (ExternalFileInfo = v35,
              v49 = Buf1,
              v50 = v43,
              v51 = 0,
              v24 = WofSetFileDataLocation(FileW, 1u, &ExternalFileInfo, 0x20u),
              v24 >= 0) )
        {
          if ( FileW )
            CloseHandle(FileW);
          if ( ImageFile != -1 )
            WIMCloseHandle(ImageFile);
          v15 = 0;
          goto LABEL_49;
        }
        DeleteFileW(a4);
        LODWORD(dwFlagsAndAttributes) = v24;
        LODWORD(dwCreationDispositionb) = 435;
        ProvPackageLog(
          3,
          L"%hs (%hs:%d) - 0x%08x:",
          "Element::LinkPayload",
          "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
          dwCreationDispositionb,
          dwFlagsAndAttributes);
        ProvPackageLog(3, L"    Failed to set file data location");
        if ( FileW )
          CloseHandle(FileW);
        goto LABEL_26;
      }
      v28 = GetLastError();
      if ( v28 > 0 )
        v28 = (unsigned __int16)v28 | 0x80070000;
      LODWORD(dwFlagsAndAttributes) = v28;
      LODWORD(dwCreationDispositionb) = 413;
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "Element::LinkPayload",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
        dwCreationDispositionb,
        dwFlagsAndAttributes);
      ProvPackageLog(3, L"    Failed to create reparse point");
      v29 = GetLastError();
      v26 = v29;
      if ( v29 > 0 )
        v26 = (unsigned __int16)v29 | 0x80070000;
    }
    else
    {
      LODWORD(dwCreationDispositiona) = 406;
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "Element::LinkPayload",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
        dwCreationDispositiona,
        DataSourceId);
      ProvPackageLog(3, L"    Failed to get data source ID");
    }
    if ( ImageFile != -1 )
      WIMCloseHandle(ImageFile);
    v15 = v26;
    goto LABEL_49;
  }
  v15 = -2147024882;
  ProvPackageLog(
    3,
    L"%hs (%hs:%d) - 0x%08x:",
    "Element::LinkPayload",
    "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
    382,
    -2147024882);
  ProvPackageLog(3, L"    Failed to allocate spSourcePath.get()");
  return v15;
}

```

## disassembly

```asm
0x180016710  mov     [rsp-8+arg_8], rbx
0x180016715  push    rbp
0x180016716  push    rsi
0x180016717  push    rdi
0x180016718  push    r12
0x18001671a  push    r13
0x18001671c  push    r14
0x18001671e  push    r15
0x180016720  lea     rbp, [rsp-250h]
0x180016728  sub     rsp, 350h
0x18001672f  mov     rax, cs:__security_cookie
0x180016736  xor     rax, rsp
0x180016739  mov     [rbp+280h+var_40], rax
0x180016740  mov     r12, r9
0x180016743  mov     r14, r8
0x180016746  mov     rdi, rcx
0x180016749  or      r9, 0FFFFFFFFFFFFFFFFh
0x18001674d  mov     rcx, r9
0x180016750  xor     r13d, r13d
0x180016753  inc     rcx
0x180016756  cmp     [r8+rcx*2], r13w
0x18001675b  jnz     short loc_180016753
0x18001675d  mov     rdx, [rdi+18h]
0x180016761  mov     rax, r9
0x180016764  inc     rax
0x180016767  cmp     [rdx+rax*2], r13w
0x18001676c  jnz     short loc_180016764
0x18001676e  mov     r8, [rdi+20h]
0x180016772  mov     rdx, r9
0x180016775  inc     rdx
0x180016778  cmp     [r8+rdx*2], r13w
0x18001677d  jnz     short loc_180016775
0x18001677f  lea     rsi, [rdx+rax]
0x180016783  add     rcx, 7
0x180016787  add     rsi, rcx
0x18001678a  mov     eax, 2
0x18001678f  mul     rsi
0x180016792  cmovb   rax, r9
0x180016796  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001679d  mov     rcx, rax; unsigned __int64
0x1800167a0  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800167a5  mov     r15, rax
0x1800167a8  mov     [rsp+380h+var_320], rax
0x1800167ad  test    rax, rax
0x1800167b0  jnz     short loc_1800167F6
0x1800167b2  mov     ebx, 8007000Eh
0x1800167b7  mov     dword ptr [rsp+380h+dwFlagsAndAttributes], ebx
0x1800167bb  mov     dword ptr [rsp+380h+dwCreationDisposition], 17Eh
0x1800167c3  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x1800167ca  lea     r8, aElementLinkpay; "Element::LinkPayload"
0x1800167d1  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x1800167d8  lea     esi, [rax+3]
0x1800167db  mov     ecx, esi
0x1800167dd  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800167e2  lea     rdx, aFailedToAlloca_3; "    Failed to allocate spSourcePath.get"...
0x1800167e9  mov     ecx, esi
0x1800167eb  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800167f0  nop
0x1800167f1  jmp     loc_180016C1D
0x1800167f6  mov     r9, [rdi+20h]; pszMore
0x1800167fa  mov     r8, [rdi+18h]; pszPathIn
0x1800167fe  mov     rdx, rsi; cchPathOut
0x180016801  mov     rcx, r15; pszPathOut
0x180016804  call    PathCchCombineEx
0x180016809  mov     ebx, eax
0x18001680b  test    eax, eax
0x18001680d  jns     short loc_180016845
0x18001680f  mov     dword ptr [rsp+380h+dwFlagsAndAttributes], eax
0x180016813  mov     dword ptr [rsp+380h+dwCreationDisposition], 182h
0x18001681b  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x180016822  lea     r8, aElementLinkpay; "Element::LinkPayload"
0x180016829  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180016830  mov     esi, 3
0x180016835  mov     ecx, esi
0x180016837  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18001683c  lea     rdx, aFailedToAssemb_16; "    Failed to assemble source path (ind"...
0x180016843  jmp     short loc_18001688D
0x180016845  mov     r8, r14; pszMore
0x180016848  mov     rdx, rsi; cchPath
0x18001684b  mov     rcx, r15; pszPath
0x18001684e  call    PathCchAppendEx
0x180016853  mov     ebx, eax
0x180016855  test    eax, eax
0x180016857  jns     short loc_180016899
0x180016859  mov     dword ptr [rsp+380h+dwFlagsAndAttributes], eax
0x18001685d  mov     dword ptr [rsp+380h+dwCreationDisposition], 185h
0x180016865  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x18001686c  lea     r8, aElementLinkpay; "Element::LinkPayload"
0x180016873  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18001687a  mov     esi, 3
0x18001687f  mov     ecx, esi
0x180016881  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180016886  lea     rdx, aFailedToAssemb_4; "    Failed to assemble source path (pat"...
0x18001688d  mov     ecx, esi
0x18001688f  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180016894  jmp     loc_180016C15
0x180016899  xor     edx, edx; Val
0x18001689b  mov     r8d, 250h; Size
0x1800168a1  lea     rcx, [rbp+280h+var_300]; void *
0x1800168a5  call    memset_0
0x1800168aa  xorps   xmm0, xmm0
0x1800168ad  xor     eax, eax
0x1800168af  movups  [rbp+280h+Buf1], xmm0
0x1800168b6  mov     [rbp+280h+var_A0], rax
0x1800168bd  movups  [rbp+280h+var_98], xmm0
0x1800168c4  movups  [rbp+280h+var_88], xmm0
0x1800168cb  movups  [rbp+280h+var_78], xmm0
0x1800168d2  mov     [rbp+280h+var_68], rax
0x1800168d9  mov     rcx, [rdi+8]
0x1800168dd  lea     r9, [rbp+280h+var_300]
0x1800168e1  mov     r8d, 2A0h
0x1800168e7  mov     rdx, r15
0x1800168ea  mov     rcx, [rcx+10h]
0x1800168ee  call    cs:__imp_WIMFindFirstImageFileEx
0x1800168f4  mov     rbx, rax
0x1800168f7  mov     [rsp+380h+var_318], rax
0x1800168fc  test    rax, rax
0x1800168ff  jnz     short loc_180016969
0x180016901  call    cs:__imp_GetLastError
0x180016907  mov     r14d, 80070000h
0x18001690d  test    eax, eax
0x18001690f  jle     short loc_180016917
0x180016911  movzx   eax, ax
0x180016914  or      eax, r14d
0x180016917  mov     dword ptr [rsp+380h+dwFlagsAndAttributes], eax
0x18001691b  mov     dword ptr [rsp+380h+dwCreationDisposition], 18Ah
0x180016923  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x18001692a  lea     r8, aElementLinkpay; "Element::LinkPayload"
0x180016931  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180016938  mov     esi, 3
0x18001693d  mov     ecx, esi
0x18001693f  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180016944  lea     rdx, aFailedToFindPa; "    Failed to find payload file"
0x18001694b  mov     ecx, esi
0x18001694d  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180016952  call    cs:__imp_GetLastError
0x180016958  test    eax, eax
0x18001695a  jle     short loc_180016962
0x18001695c  movzx   eax, ax
0x18001695f  or      eax, r14d
0x180016962  mov     ebx, eax
0x180016964  jmp     loc_180016C15
0x180016969  mov     esi, [rbp+280h+arg_20]
0x18001696f  cmp     dword ptr [rbp+280h+var_88+8], r13d
0x180016976  jbe     loc_180016A0C
0x18001697c  cmp     qword ptr [rbp+280h+var_88], r13
0x180016983  jz      loc_180016A0C
0x180016989  lea     rdx, aCannotLinkThis; "Cannot link this payload; will copy ins"...
0x180016990  mov     ecx, 2
0x180016995  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18001699a  mov     rax, [rdi]
0x18001699d  mov     r9d, esi
0x1800169a0  mov     r8, r12
0x1800169a3  mov     rdx, r14
0x1800169a6  mov     rcx, rdi
0x1800169a9  mov     rax, [rax+30h]
0x1800169ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169b2  mov     r14d, eax
0x1800169b5  test    eax, eax
0x1800169b7  jns     short loc_180016A0C
0x1800169b9  mov     dword ptr [rsp+380h+dwFlagsAndAttributes], eax
0x1800169bd  mov     dword ptr [rsp+380h+dwCreationDisposition], 191h
0x1800169c5  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x1800169cc  lea     r8, aElementLinkpay; "Element::LinkPayload"
0x1800169d3  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x1800169da  mov     esi, 3
0x1800169df  mov     ecx, esi
0x1800169e1  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800169e6  lea     rdx, aFailedToRetrie_1; "    Failed to retrieve payload"
0x1800169ed  mov     ecx, esi
0x1800169ef  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800169f4  nop
0x1800169f5  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800169f9  jz      short loc_180016A04
0x1800169fb  mov     rcx, rbx
0x1800169fe  call    cs:__imp_WIMCloseHandle
0x180016a04  mov     ebx, r14d
0x180016a07  jmp     loc_180016C15
0x180016a0c  mov     qword ptr [rsp+380h+var_340], r13
0x180016a11  lea     r8, [rsp+380h+var_340]; union _LARGE_INTEGER *
0x180016a16  mov     rdx, r12; unsigned __int16 *
0x180016a19  mov     rcx, [rdi+8]; UserData
0x180016a1d  call    ?GetDataSourceId@ProvisioningPackage@@QEAAJPEBGPEAT_LARGE_INTEGER@@@Z; ProvisioningPackage::GetDataSourceId(ushort const *,_LARGE_INTEGER *)
0x180016a22  mov     edi, eax
0x180016a24  test    eax, eax
0x180016a26  jns     short loc_180016A7A
0x180016a28  mov     dword ptr [rsp+380h+dwFlagsAndAttributes], eax
0x180016a2c  mov     dword ptr [rsp+380h+dwCreationDisposition], 196h
0x180016a34  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x180016a3b  lea     r8, aElementLinkpay; "Element::LinkPayload"
0x180016a42  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180016a49  mov     esi, 3
0x180016a4e  mov     ecx, esi
0x180016a50  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180016a55  lea     rdx, aFailedToGetDat; "    Failed to get data source ID"
0x180016a5c  mov     ecx, esi
0x180016a5e  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180016a63  nop
0x180016a64  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180016a68  jz      short loc_180016A73
0x180016a6a  mov     rcx, rbx
0x180016a6d  call    cs:__imp_WIMCloseHandle
0x180016a73  mov     ebx, edi
0x180016a75  jmp     loc_180016C15
0x180016a7a  neg     esi
0x180016a7c  sbb     eax, eax
0x180016a7e  neg     eax
0x180016a80  inc     eax
0x180016a82  mov     [rsp+380h+hTemplateFile], r13; hTemplateFile
0x180016a87  mov     dword ptr [rsp+380h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x180016a8f  mov     dword ptr [rsp+380h+dwCreationDisposition], eax; dwCreationDisposition
0x180016a93  xor     r9d, r9d; lpSecurityAttributes
0x180016a96  mov     edx, 12019Fh; dwDesiredAccess
0x180016a9b  lea     r8d, [r9+7]; dwShareMode
0x180016a9f  mov     rcx, r12; lpFileName
0x180016aa2  call    cs:__imp_CreateFileW
0x180016aa8  mov     rdi, rax
0x180016aab  mov     [rsp+380h+var_310], rax
0x180016ab0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180016ab4  jnz     short loc_180016B1E
0x180016ab6  call    cs:__imp_GetLastError
0x180016abc  mov     r14d, 80070000h
0x180016ac2  test    eax, eax
0x180016ac4  jle     short loc_180016ACC
0x180016ac6  movzx   eax, ax
0x180016ac9  or      eax, r14d
0x180016acc  mov     dword ptr [rsp+380h+dwFlagsAndAttributes], eax
0x180016ad0  mov     dword ptr [rsp+380h+dwCreationDisposition], 19Dh
0x180016ad8  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x180016adf  lea     r8, aElementLinkpay; "Element::LinkPayload"
0x180016ae6  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180016aed  mov     esi, 3
0x180016af2  mov     ecx, esi
0x180016af4  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180016af9  lea     rdx, aFailedToCreate_13; "    Failed to create reparse point"
0x180016b00  mov     ecx, esi
0x180016b02  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180016b07  call    cs:__imp_GetLastError
0x180016b0d  mov     edi, eax
0x180016b0f  test    eax, eax
0x180016b11  jle     short loc_180016B19
0x180016b13  movzx   edi, ax
0x180016b16  or      edi, r14d
0x180016b19  jmp     loc_180016A64
0x180016b1e  xorps   xmm0, xmm0
0x180016b21  xor     eax, eax
0x180016b23  movups  [rsp+380h+Buf2], xmm0
0x180016b28  mov     [rsp+380h+var_328], eax
0x180016b2c  lea     r8d, [rax+14h]; Size
0x180016b30  lea     rdx, [rsp+380h+Buf2]; Buf2
0x180016b35  lea     rcx, [rbp+280h+Buf1]; Buf1
0x180016b3c  call    memcmp_0
0x180016b41  test    eax, eax
0x180016b43  jz      loc_180016BF4
0x180016b49  mov     rax, qword ptr [rsp+380h+var_340]
0x180016b4e  mov     [rbp+280h+ExternalFileInfo], rax
0x180016b55  movaps  xmm0, [rbp+280h+Buf1]
0x180016b5c  movups  [rbp+280h+var_58], xmm0
0x180016b63  mov     eax, dword ptr [rbp+280h+var_A0]
0x180016b69  mov     [rbp+280h+var_48], eax
0x180016b6f  mov     [rbp+280h+var_44], r13d
0x180016b76  mov     r9d, 20h ; ' '; Length
0x180016b7c  lea     r8, [rbp+280h+ExternalFileInfo]; ExternalFileInfo
0x180016b83  lea     edx, [r9-1Fh]; Provider
0x180016b87  mov     rcx, rdi; FileHandle
0x180016b8a  call    cs:__imp_WofSetFileDataLocation
0x180016b90  mov     r14d, eax
0x180016b93  test    eax, eax
0x180016b95  jns     short loc_180016BF4
0x180016b97  mov     rcx, r12; lpFileName
0x180016b9a  call    cs:__imp_DeleteFileW
0x180016ba0  mov     dword ptr [rsp+380h+dwFlagsAndAttributes], r14d
0x180016ba5  mov     dword ptr [rsp+380h+dwCreationDisposition], 1B3h
0x180016bad  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x180016bb4  lea     r8, aElementLinkpay; "Element::LinkPayload"
0x180016bbb  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180016bc2  mov     esi, 3
0x180016bc7  mov     ecx, esi
0x180016bc9  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180016bce  lea     rdx, aFailedToSetFil; "    Failed to set file data location"
0x180016bd5  mov     ecx, esi
0x180016bd7  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180016bdc  nop
0x180016bdd  test    rdi, rdi
0x180016be0  jz      loc_1800169F5
0x180016be6  mov     rcx, rdi; hObject
0x180016be9  call    cs:__imp_CloseHandle
0x180016bef  jmp     loc_1800169F5
0x180016bf4  test    rdi, rdi
0x180016bf7  jz      short loc_180016C03
0x180016bf9  mov     rcx, rdi; hObject
0x180016bfc  call    cs:__imp_CloseHandle
0x180016c02  nop
0x180016c03  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180016c07  jz      short loc_180016C12
0x180016c09  mov     rcx, rbx
0x180016c0c  call    cs:__imp_WIMCloseHandle
0x180016c12  mov     ebx, r13d
0x180016c15  mov     rcx, r15; void *
0x180016c18  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
  ... truncated ...
```
