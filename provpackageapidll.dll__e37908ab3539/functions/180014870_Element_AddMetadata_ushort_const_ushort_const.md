# Element::AddMetadata(ushort const *,ushort const *)

- ea: `0x180014870`
- end: `0x180014c5c`
- name: `?AddMetadata@Element@@EEAAJPEBG0@Z`
- size: `1004`
- prototype: `__int64 __fastcall(Element *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, installer_update`

## callees

- `0x180001510`
- `0x1800020a8`
- `0x180006014`
- `0x18000e060`
- `0x18000e4b0`
- `0x180010438`
- `0x180011e38`
- `0x180014870`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014b39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014b55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014b9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014b39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014b55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014b9f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180014a00`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180014a0b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180014bb5`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180014bc0`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180014bf9`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180014c04`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180014a00`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180014a0b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180014bb5`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180014bc0`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180014bf9`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180014c04`
- `WIMGAPI!WIMAddImagePath` at `0x180014b2b`
- `WIMGAPI!WIMAddImagePath` at `0x180014b2b`

## string_xrefs

- `0x1800148f5`: `    Failed to get metadata read temporary file`
- `0x180014978`: `    Failed to get meatdata write temporary file`
- `0x180014a69`: `    Element metadata already exists`

## pseudocode

```c
__int64 __fastcall Element::AddMetadata(Element *this, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  int TemporaryFile; // eax
  int v7; // edi
  const struct std::nothrow_t *v8; // rdx
  WCHAR *v9; // rcx
  bool v10; // zf
  WCHAR *v11; // rcx
  int v13; // eax
  int File; // eax
  int ElementMetadata; // eax
  int v16; // eax
  signed int LastError; // eax
  bool v18; // sf
  signed int v19; // eax
  signed int v20; // eax
  unsigned int v21; // ebx
  const struct std::nothrow_t *v22; // rdx
  WCHAR *v23; // rcx
  WCHAR *v24; // rcx
  const struct std::nothrow_t *v25; // rdx
  WCHAR *v26; // rcx
  WCHAR *v27; // rcx
  int v28; // [rsp+20h] [rbp-E0h]
  int v29; // [rsp+20h] [rbp-E0h]
  int v30; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v31; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v32; // [rsp+20h] [rbp-E0h]
  int v33; // [rsp+28h] [rbp-D8h]
  int v34; // [rsp+28h] [rbp-D8h]
  int v35; // [rsp+28h] [rbp-D8h]
  int v36; // [rsp+28h] [rbp-D8h]
  int v37; // [rsp+28h] [rbp-D8h]
  int v38; // [rsp+28h] [rbp-D8h]
  signed int v39; // [rsp+28h] [rbp-D8h]
  LPCWSTR lpFileName; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR v41[3]; // [rsp+38h] [rbp-C8h] BYREF
  char v42; // [rsp+50h] [rbp-B0h]
  unsigned __int16 v43[264]; // [rsp+60h] [rbp-A0h] BYREF

  lpFileName = 0;
  v41[0] = 0;
  TemporaryFile = GetTemporaryFile((__int64)L"tem", &lpFileName);
  v7 = TemporaryFile;
  if ( TemporaryFile < 0 )
  {
    v33 = TemporaryFile;
    v28 = 214;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "Element::AddMetadata",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
      v28,
      v33);
    ProvPackageLog(3, L"    Failed to get metadata read temporary file");
LABEL_3:
    v9 = (WCHAR *)v41[0];
    v10 = v41[0] == 0;
    v41[0] = 0;
    if ( !v10 )
      operator delete(v9, v8);
    v11 = (WCHAR *)lpFileName;
    lpFileName = 0;
    if ( v11 )
      operator delete(v11, v8);
    return (unsigned int)v7;
  }
  v13 = GetTemporaryFile((__int64)L"tem", v41);
  v7 = v13;
  if ( v13 < 0 )
  {
    v34 = v13;
    v29 = 216;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "Element::AddMetadata",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
      v29,
      v34);
    ProvPackageLog(3, L"    Failed to get meatdata write temporary file");
    goto LABEL_3;
  }
  v41[1] = (LPCWSTR)&lpFileName;
  v41[2] = (LPCWSTR)v41;
  v42 = 1;
  File = ExtractFile(*(void **)(*((_QWORD *)this + 1) + 16LL), *((const unsigned __int16 **)this + 5), lpFileName, 1);
  v7 = File;
  if ( File < 0 )
  {
    v35 = File;
    v30 = 227;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "Element::AddMetadata",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
      v30,
      v35);
    ProvPackageLog(3, L"    Failed to retrieve metadata file");
LABEL_12:
    DeleteFileW(lpFileName);
    DeleteFileW(v41[0]);
    goto LABEL_3;
  }
  ElementMetadata = GetElementMetadata(lpFileName, *((const unsigned __int16 **)this + 4), a2, v43, 0x104u);
  if ( !ElementMetadata )
  {
    v7 = -2147024713;
    v36 = -2147024713;
    LODWORD(v31) = 234;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "Element::AddMetadata",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
      v31,
      v36);
    ProvPackageLog(3, L"    Element metadata already exists");
    goto LABEL_12;
  }
  v7 = 0;
  if ( ElementMetadata != -2147023728 )
    v7 = ElementMetadata;
  if ( v7 < 0 )
  {
    v37 = v7;
    LODWORD(v31) = 240;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "Element::AddMetadata",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
      v31,
      v37);
    ProvPackageLog(3, L"    Failed to get element metadata");
    goto LABEL_12;
  }
  v16 = AddElementMetadata(lpFileName, v41[0], *((const unsigned __int16 **)this + 4), a2, a3);
  v7 = v16;
  if ( v16 < 0 )
  {
    v38 = v16;
    LODWORD(v32) = 243;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "Element::AddMetadata",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
      v32,
      v38);
    ProvPackageLog(3, L"    Failed to add element metadata");
    goto LABEL_12;
  }
  if ( (unsigned int)WIMAddImagePath(*(_QWORD *)(*((_QWORD *)this + 1) + 16LL), v41[0], *((_QWORD *)this + 5), 67108866) )
    goto LABEL_34;
  LastError = GetLastError();
  v18 = LastError < 0;
  if ( LastError > 0 )
    v18 = 1;
  if ( !v18 )
  {
LABEL_34:
    DeleteFileW(lpFileName);
    DeleteFileW(v41[0]);
    v26 = (WCHAR *)v41[0];
    v41[0] = 0;
    if ( v26 )
      operator delete(v26, v25);
    v27 = (WCHAR *)lpFileName;
    lpFileName = 0;
    if ( v27 )
      operator delete(v27, v25);
    return 0;
  }
  else
  {
    v19 = GetLastError();
    if ( v19 > 0 )
      v19 = (unsigned __int16)v19 | 0x80070000;
    v39 = v19;
    LODWORD(v32) = 248;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "Element::AddMetadata",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
      v32,
      v39);
    ProvPackageLog(3, L"    Failed to re-add metadata file");
    v20 = GetLastError();
    v21 = v20;
    if ( v20 > 0 )
      v21 = (unsigned __int16)v20 | 0x80070000;
    DeleteFileW(lpFileName);
    DeleteFileW(v41[0]);
    v23 = (WCHAR *)v41[0];
    v41[0] = 0;
    if ( v23 )
      operator delete(v23, v22);
    v24 = (WCHAR *)lpFileName;
    lpFileName = 0;
    if ( v24 )
      operator delete(v24, v22);
    return v21;
  }
}

```

## disassembly

```asm
0x180014870  mov     [rsp-8+arg_18], rbx
0x180014875  push    rbp
0x180014876  push    rsi
0x180014877  push    rdi
0x180014878  push    r14
0x18001487a  push    r15
0x18001487c  lea     rbp, [rsp-180h]
0x180014884  sub     rsp, 280h
0x18001488b  mov     rax, cs:__security_cookie
0x180014892  xor     rax, rsp
0x180014895  mov     [rbp+1A0h+var_30], rax
0x18001489c  mov     r14, r8
0x18001489f  mov     rsi, rdx
0x1800148a2  mov     rbx, rcx
0x1800148a5  xor     r15d, r15d
0x1800148a8  mov     [rsp+2A0h+lpFileName], r15
0x1800148ad  mov     [rsp+2A0h+var_268], r15
0x1800148b2  lea     rdx, [rsp+2A0h+lpFileName]
0x1800148b7  lea     rcx, aTem; "tem"
0x1800148be  call    ?GetTemporaryFile@@YAJPEBGPEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@@Z; GetTemporaryFile(ushort const *,wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> *)
0x1800148c3  mov     edi, eax
0x1800148c5  test    eax, eax
0x1800148c7  jns     short loc_180014934
0x1800148c9  mov     [rsp+2A0h+var_278], eax
0x1800148cd  mov     dword ptr [rsp+2A0h+var_280], 0D6h
0x1800148d5  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x1800148dc  lea     r8, aElementAddmeta; "Element::AddMetadata"
0x1800148e3  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x1800148ea  lea     ebx, [r15+3]
0x1800148ee  mov     ecx, ebx
0x1800148f0  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800148f5  lea     rdx, aFailedToGetMet_0; "    Failed to get metadata read tempora"...
0x1800148fc  mov     ecx, ebx
0x1800148fe  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180014903  nop
0x180014904  mov     rcx, [rsp+2A0h+var_268]; void *
0x180014909  test    rcx, rcx
0x18001490c  mov     [rsp+2A0h+var_268], r15
0x180014911  jz      short loc_180014919
0x180014913  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180014918  nop
0x180014919  mov     rcx, [rsp+2A0h+lpFileName]; void *
0x18001491e  mov     [rsp+2A0h+lpFileName], r15
0x180014923  test    rcx, rcx
0x180014926  jz      short loc_18001492D
0x180014928  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001492d  mov     eax, edi
0x18001492f  jmp     loc_180014C36
0x180014934  lea     rdx, [rsp+2A0h+var_268]
0x180014939  lea     rcx, aTem; "tem"
0x180014940  call    ?GetTemporaryFile@@YAJPEBGPEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@@Z; GetTemporaryFile(ushort const *,wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> *)
0x180014945  mov     edi, eax
0x180014947  test    eax, eax
0x180014949  jns     short loc_180014984
0x18001494b  mov     [rsp+2A0h+var_278], eax
0x18001494f  mov     dword ptr [rsp+2A0h+var_280], 0D8h
0x180014957  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x18001495e  lea     r8, aElementAddmeta; "Element::AddMetadata"
0x180014965  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18001496c  mov     ebx, 3
0x180014971  mov     ecx, ebx
0x180014973  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180014978  lea     rdx, aFailedToGetMea; "    Failed to get meatdata write tempor"...
0x18001497f  jmp     loc_1800148FC
0x180014984  lea     rax, [rsp+2A0h+lpFileName]
0x180014989  mov     [rsp+2A0h+var_260], rax
0x18001498e  lea     rax, [rsp+2A0h+var_268]
0x180014993  mov     [rsp+2A0h+var_258], rax
0x180014998  mov     [rsp+2A0h+var_250], 1
0x18001499d  mov     rcx, [rbx+8]
0x1800149a1  mov     r9d, 1; int
0x1800149a7  mov     r8, [rsp+2A0h+lpFileName]; unsigned __int16 *
0x1800149ac  mov     rdx, [rbx+28h]; unsigned __int16 *
0x1800149b0  mov     rcx, [rcx+10h]; void *
0x1800149b4  call    ?ExtractFile@@YAJPEAXPEBG1H@Z; ExtractFile(void *,ushort const *,ushort const *,int)
0x1800149b9  mov     edi, eax
0x1800149bb  test    eax, eax
0x1800149bd  jns     short loc_180014A16
0x1800149bf  mov     [rsp+2A0h+var_278], eax
0x1800149c3  mov     dword ptr [rsp+2A0h+var_280], 0E3h
0x1800149cb  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x1800149d2  lea     r8, aElementAddmeta; "Element::AddMetadata"
0x1800149d9  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x1800149e0  mov     ebx, 3
0x1800149e5  mov     ecx, ebx
0x1800149e7  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800149ec  lea     rdx, aFailedToRetrie; "    Failed to retrieve metadata file"
0x1800149f3  mov     ecx, ebx
0x1800149f5  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800149fa  nop
0x1800149fb  mov     rcx, [rsp+2A0h+lpFileName]; lpFileName
0x180014a00  call    cs:__imp_DeleteFileW
0x180014a06  mov     rcx, [rsp+2A0h+var_268]; lpFileName
0x180014a0b  call    cs:__imp_DeleteFileW
0x180014a11  jmp     loc_180014904
0x180014a16  mov     [rsp+2A0h+var_280], 104h; unsigned __int64
0x180014a1f  lea     r9, [rsp+2A0h+var_240]; unsigned __int16 *
0x180014a24  mov     r8, rsi; unsigned __int16 *
0x180014a27  mov     rdx, [rbx+20h]; unsigned __int16 *
0x180014a2b  mov     rcx, [rsp+2A0h+lpFileName]; unsigned __int16 *
0x180014a30  call    ?GetElementMetadata@@YAJPEBG00PEAG_K@Z; GetElementMetadata(ushort const *,ushort const *,ushort const *,ushort *,unsigned __int64)
0x180014a35  test    eax, eax
0x180014a37  jnz     short loc_180014A72
0x180014a39  mov     edi, 800700B7h
0x180014a3e  mov     [rsp+2A0h+var_278], edi
0x180014a42  mov     dword ptr [rsp+2A0h+var_280], 0EAh
0x180014a4a  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x180014a51  lea     r8, aElementAddmeta; "Element::AddMetadata"
0x180014a58  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180014a5f  lea     ebx, [rax+3]
0x180014a62  mov     ecx, ebx
0x180014a64  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180014a69  lea     rdx, aElementMetadat; "    Element metadata already exists"
0x180014a70  jmp     short loc_1800149F3
0x180014a72  mov     edi, r15d
0x180014a75  cmp     eax, 80070490h
0x180014a7a  cmovnz  edi, eax
0x180014a7d  test    edi, edi
0x180014a7f  jns     short loc_180014ABA
0x180014a81  mov     [rsp+2A0h+var_278], edi
0x180014a85  mov     dword ptr [rsp+2A0h+var_280], 0F0h
0x180014a8d  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x180014a94  lea     r8, aElementAddmeta; "Element::AddMetadata"
0x180014a9b  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180014aa2  mov     ebx, 3
0x180014aa7  mov     ecx, ebx
0x180014aa9  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180014aae  lea     rdx, aFailedToGetEle_1; "    Failed to get element metadata"
0x180014ab5  jmp     loc_1800149F3
0x180014aba  mov     [rsp+2A0h+var_280], r14; unsigned __int16 *
0x180014abf  mov     r9, rsi; unsigned __int16 *
0x180014ac2  mov     r8, [rbx+20h]; unsigned __int16 *
0x180014ac6  mov     rdx, [rsp+2A0h+var_268]; unsigned __int16 *
0x180014acb  mov     rcx, [rsp+2A0h+lpFileName]; unsigned __int16 *
0x180014ad0  call    ?AddElementMetadata@@YAJPEBG0000@Z; AddElementMetadata(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180014ad5  mov     edi, eax
0x180014ad7  test    eax, eax
0x180014ad9  jns     short loc_180014B14
0x180014adb  mov     [rsp+2A0h+var_278], eax
0x180014adf  mov     dword ptr [rsp+2A0h+var_280], 0F3h
0x180014ae7  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x180014aee  lea     r8, aElementAddmeta; "Element::AddMetadata"
0x180014af5  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180014afc  mov     ebx, 3
0x180014b01  mov     ecx, ebx
0x180014b03  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180014b08  lea     rdx, aFailedToAddEle; "    Failed to add element metadata"
0x180014b0f  jmp     loc_1800149F3
0x180014b14  mov     rcx, [rbx+8]
0x180014b18  mov     r9d, 4000002h
0x180014b1e  mov     r8, [rbx+28h]
0x180014b22  mov     rdx, [rsp+2A0h+var_268]
0x180014b27  mov     rcx, [rcx+10h]
0x180014b2b  call    cs:__imp_WIMAddImagePath
0x180014b31  test    eax, eax
0x180014b33  jnz     loc_180014BF4
0x180014b39  call    cs:__imp_GetLastError
0x180014b3f  mov     edi, 80070000h
0x180014b44  test    eax, eax
0x180014b46  jle     short loc_180014B4F
0x180014b48  movzx   eax, ax
0x180014b4b  or      eax, edi
0x180014b4d  test    eax, eax
0x180014b4f  jns     loc_180014BF4
0x180014b55  call    cs:__imp_GetLastError
0x180014b5b  test    eax, eax
0x180014b5d  jle     short loc_180014B64
0x180014b5f  movzx   eax, ax
0x180014b62  or      eax, edi
0x180014b64  mov     [rsp+2A0h+var_278], eax
0x180014b68  mov     dword ptr [rsp+2A0h+var_280], 0F8h
0x180014b70  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x180014b77  lea     r8, aElementAddmeta; "Element::AddMetadata"
0x180014b7e  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180014b85  mov     ebx, 3
0x180014b8a  mov     ecx, ebx
0x180014b8c  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180014b91  lea     rdx, aFailedToReAddM; "    Failed to re-add metadata file"
0x180014b98  mov     ecx, ebx
0x180014b9a  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180014b9f  call    cs:__imp_GetLastError
0x180014ba5  mov     ebx, eax
0x180014ba7  test    eax, eax
0x180014ba9  jle     short loc_180014BB0
0x180014bab  movzx   ebx, ax
0x180014bae  or      ebx, edi
0x180014bb0  mov     rcx, [rsp+2A0h+lpFileName]; lpFileName
0x180014bb5  call    cs:__imp_DeleteFileW
0x180014bbb  mov     rcx, [rsp+2A0h+var_268]; lpFileName
0x180014bc0  call    cs:__imp_DeleteFileW
0x180014bc6  nop
0x180014bc7  mov     rcx, [rsp+2A0h+var_268]; void *
0x180014bcc  mov     [rsp+2A0h+var_268], r15
0x180014bd1  test    rcx, rcx
0x180014bd4  jz      short loc_180014BDC
0x180014bd6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180014bdb  nop
0x180014bdc  mov     rcx, [rsp+2A0h+lpFileName]; void *
0x180014be1  mov     [rsp+2A0h+lpFileName], r15
0x180014be6  test    rcx, rcx
0x180014be9  jz      short loc_180014BF0
0x180014beb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180014bf0  mov     eax, ebx
0x180014bf2  jmp     short loc_180014C36
0x180014bf4  mov     rcx, [rsp+2A0h+lpFileName]; lpFileName
0x180014bf9  call    cs:__imp_DeleteFileW
0x180014bff  mov     rcx, [rsp+2A0h+var_268]; lpFileName
0x180014c04  call    cs:__imp_DeleteFileW
0x180014c0a  nop
0x180014c0b  mov     rcx, [rsp+2A0h+var_268]; void *
0x180014c10  mov     [rsp+2A0h+var_268], r15
0x180014c15  test    rcx, rcx
0x180014c18  jz      short loc_180014C20
0x180014c1a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180014c1f  nop
0x180014c20  mov     rcx, [rsp+2A0h+lpFileName]; void *
0x180014c25  mov     [rsp+2A0h+lpFileName], r15
0x180014c2a  test    rcx, rcx
0x180014c2d  jz      short loc_180014C34
0x180014c2f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180014c34  xor     eax, eax
0x180014c36  mov     rcx, [rbp+1A0h+var_30]
0x180014c3d  xor     rcx, rsp; StackCookie
0x180014c40  call    __security_check_cookie
0x180014c45  mov     rbx, [rsp+2A0h+arg_18]
0x180014c4d  add     rsp, 280h
0x180014c54  pop     r15
0x180014c56  pop     r14
0x180014c58  pop     rdi
0x180014c59  pop     rsi
0x180014c5a  pop     rbp
0x180014c5b  retn
```
