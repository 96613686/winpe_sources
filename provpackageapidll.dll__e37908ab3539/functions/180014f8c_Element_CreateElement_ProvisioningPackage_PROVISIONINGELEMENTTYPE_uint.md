# Element::CreateElement(ProvisioningPackage *,_PROVISIONINGELEMENTTYPE,uint)

- ea: `0x180014f8c`
- end: `0x180015523`
- name: `?CreateElement@Element@@QEAAJPEAVProvisioningPackage@@W4_PROVISIONINGELEMENTTYPE@@I@Z`
- size: `1431`
- prototype: `__int64 __fastcall(__int64, __int64, int, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, installer_update`

## callers

- `0x180006790`

## callees

- `0x1800020a8`
- `0x1800020ec`
- `0x180006014`
- `0x18000e060`
- `0x18000e4b0`
- `0x18000eecc`
- `0x1800112a4`
- `0x180013688`
- `0x180014f8c`
- `0x180016c50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001526f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015280`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015298`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800152e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800153f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001540c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001546e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015482`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001526f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015280`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015298`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800152e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800153f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001540c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001546e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015482`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800152f9`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180015303`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800154cf`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800154d9`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800152f9`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180015303`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800154cf`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800154d9`
- `WIMGAPI!WIMAddImagePath` at `0x180015205`
- `WIMGAPI!WIMAddImagePath` at `0x1800153ee`
- `WIMGAPI!WIMAddImagePath` at `0x180015464`
- `WIMGAPI!WIMAddImagePath` at `0x180015205`
- `WIMGAPI!WIMAddImagePath` at `0x1800153ee`
- `WIMGAPI!WIMAddImagePath` at `0x180015464`

## string_xrefs

- `0x18001512d`: `    Failed to open element`
- `0x180014fc9`: `Element::CreateElement`
- `0x180015032`: `Element::CreateElement`
- `0x1800150bb`: `Element::CreateElement`
- `0x180015113`: `Element::CreateElement`
- `0x180015167`: `Element::CreateElement`
- `0x1800151bd`: `Element::CreateElement`
- `0x180015242`: `Element::CreateElement`
- `0x1800152bb`: `Element::CreateElement`
- `0x180015367`: `Element::CreateElement`
- `0x1800153b7`: `Element::CreateElement`
- `0x18001542f`: `Element::CreateElement`
- `0x1800154a5`: `Element::CreateElement`
- `0x180015181`: `    Failed to get metadata read temporary file`
- `0x1800151d7`: `    Failed to get metadata write temporary file`
- `0x18001525c`: `    Failed to write new element metadata`
- `0x1800154bf`: `    Failed to create new element folder`

## pseudocode

```c
__int64 __fastcall Element::CreateElement(__int64 a1, __int64 a2, int a3, unsigned int a4)
{
  unsigned int v7; // edi
  void *v8; // r15
  WCHAR *v9; // rsi
  int v10; // eax
  const unsigned __int16 *v11; // r14
  int v12; // eax
  const struct std::nothrow_t *v13; // rdx
  int v14; // eax
  int TemporaryFile; // eax
  int v16; // eax
  int v17; // eax
  signed int LastError; // eax
  bool v19; // sf
  signed int v20; // eax
  signed int v21; // eax
  WCHAR *v22; // rcx
  WCHAR *v23; // rcx
  int File; // eax
  int appended; // eax
  signed int v26; // eax
  bool v27; // sf
  signed int v28; // eax
  signed int v29; // eax
  bool v30; // sf
  signed int v31; // eax
  WCHAR *v32; // rcx
  WCHAR *v33; // rcx
  LPCWSTR lpFileName[4]; // [rsp+30h] [rbp-38h] BYREF
  char v36; // [rsp+50h] [rbp-18h]
  LPCWSTR v37; // [rsp+B8h] [rbp+50h] BYREF

  if ( a2 )
  {
    *(_QWORD *)(a1 + 8) = a2;
    v8 = *(void **)(a2 + 16);
    v9 = (WCHAR *)operator new[](0x14u, (const struct std::nothrow_t *)&std::nothrow);
    lpFileName[1] = v9;
    if ( !v9 )
    {
      v7 = -2147024882;
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "Element::CreateElement",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
        29,
        -2147024882);
      ProvPackageLog(3, L"    Failed to allocate spElementIndex.get()");
      return v7;
    }
    v10 = 1;
    while ( LODWORD(qword_18001A280[2 * v10]) != a3 )
    {
      if ( (unsigned int)++v10 >= 0xC )
      {
        v11 = L"Invalid";
        goto LABEL_10;
      }
    }
    v11 = (const unsigned __int16 *)qword_18001A280[2 * v10 + 1];
LABEL_10:
    v12 = StringCbPrintfW(v9, 0xAu, L"%u", a4);
    v7 = v12;
    if ( v12 < 0 )
    {
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "Element::CreateElement",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
        33,
        v12);
      ProvPackageLog(3, L"    Failed to get element type string");
      goto LABEL_61;
    }
    v14 = Element::OpenElement((Element *)a1, *(struct ProvisioningPackage **)(a1 + 8), v11, v9);
    v7 = v14;
    if ( v14 < 0 )
    {
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "Element::CreateElement",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
        37,
        v14);
      ProvPackageLog(3, L"    Failed to open element");
LABEL_61:
      operator delete(v9, v13);
      return v7;
    }
    lpFileName[0] = 0;
    v37 = 0;
    TemporaryFile = GetTemporaryFile((__int64)L"tem", lpFileName);
    v7 = TemporaryFile;
    if ( TemporaryFile < 0 )
    {
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "Element::CreateElement",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
        42,
        TemporaryFile);
      ProvPackageLog(3, L"    Failed to get metadata read temporary file");
      goto LABEL_34;
    }
    v16 = GetTemporaryFile((__int64)L"tem", &v37);
    v7 = v16;
    if ( v16 < 0 )
    {
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "Element::CreateElement",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
        44,
        v16);
      ProvPackageLog(3, L"    Failed to get metadata write temporary file");
LABEL_34:
      v22 = (WCHAR *)v37;
      v37 = 0;
      if ( v22 )
        operator delete(v22, v13);
      v23 = (WCHAR *)lpFileName[0];
      lpFileName[0] = 0;
      if ( v23 )
        operator delete(v23, v13);
      goto LABEL_61;
    }
    lpFileName[2] = (LPCWSTR)lpFileName;
    lpFileName[3] = (LPCWSTR)&v37;
    v36 = 1;
    if ( (unsigned int)WIMAddImagePath(v8, v37, *(_QWORD *)(a1 + 40), 2) )
    {
      v17 = WriteNewElement(v37, v11, *(const unsigned __int16 **)(a1 + 32));
      v7 = v17;
      if ( v17 < 0 )
      {
        ProvPackageLog(
          3,
          L"%hs (%hs:%d) - 0x%08x:",
          "Element::CreateElement",
          "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
          57,
          v17);
        ProvPackageLog(3, L"    Failed to write new element metadata");
        goto LABEL_33;
      }
      goto LABEL_42;
    }
    if ( GetLastError() != 183 )
    {
      LastError = GetLastError();
      v19 = LastError < 0;
      if ( LastError > 0 )
        v19 = 1;
      if ( v19 )
      {
        v20 = GetLastError();
        if ( v20 > 0 )
          v20 = (unsigned __int16)v20 | 0x80070000;
        ProvPackageLog(
          3,
          L"%hs (%hs:%d) - 0x%08x:",
          "Element::CreateElement",
          "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
          64,
          v20);
        ProvPackageLog(3, L"    Failed to add metadata file");
LABEL_31:
        v21 = GetLastError();
        v7 = v21;
        if ( v21 > 0 )
          v7 = (unsigned __int16)v21 | 0x80070000;
        goto LABEL_33;
      }
    }
    File = ExtractFile(v8, *(const unsigned __int16 **)(a1 + 40), lpFileName[0], 1);
    v7 = File;
    if ( File >= 0 )
    {
      appended = AppendNewElement(lpFileName[0], v37, *(const unsigned __int16 **)(a1 + 32));
      v7 = appended;
      if ( appended >= 0 )
      {
LABEL_42:
        if ( (unsigned int)WIMAddImagePath(v8, v37, *(_QWORD *)(a1 + 40), 67108866) )
          goto LABEL_52;
        v26 = GetLastError();
        v27 = v26 < 0;
        if ( v26 > 0 )
          v27 = 1;
        if ( !v27 )
        {
LABEL_52:
          if ( (unsigned int)WIMAddImagePath(v8, 0, *(_QWORD *)(a1 + 16), 33554434) )
            goto LABEL_56;
          v29 = GetLastError();
          v30 = v29 < 0;
          if ( v29 > 0 )
            v30 = 1;
          if ( !v30 )
          {
LABEL_56:
            DeleteFileW(lpFileName[0]);
            DeleteFileW(v37);
            v32 = (WCHAR *)v37;
            v37 = 0;
            if ( v32 )
              operator delete(v32, v13);
            v33 = (WCHAR *)lpFileName[0];
            lpFileName[0] = 0;
            if ( v33 )
              operator delete(v33, v13);
            v7 = 0;
            goto LABEL_61;
          }
          v31 = GetLastError();
          if ( v31 > 0 )
            v31 = (unsigned __int16)v31 | 0x80070000;
          ProvPackageLog(
            3,
            L"%hs (%hs:%d) - 0x%08x:",
            "Element::CreateElement",
            "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
            81,
            v31);
          ProvPackageLog(3, L"    Failed to create new element folder");
        }
        else
        {
          v28 = GetLastError();
          if ( v28 > 0 )
            v28 = (unsigned __int16)v28 | 0x80070000;
          ProvPackageLog(
            3,
            L"%hs (%hs:%d) - 0x%08x:",
            "Element::CreateElement",
            "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
            77,
            v28);
          ProvPackageLog(3, L"    Failed to re-add metadata file");
        }
        goto LABEL_31;
      }
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "Element::CreateElement",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
        72,
        appended);
      ProvPackageLog(3, L"    Failed to append new element metadata");
    }
    else
    {
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "Element::CreateElement",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
        69,
        File);
      ProvPackageLog(3, L"    Failed to retrieve metadata file");
    }
LABEL_33:
    DeleteFileW(lpFileName[0]);
    DeleteFileW(v37);
    goto LABEL_34;
  }
  v7 = -2147024809;
  ProvPackageLog(
    3,
    L"%hs (%hs:%d) - 0x%08x:",
    "Element::CreateElement",
    "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
    22,
    -2147024809);
  ProvPackageLog(3, L"    pkg: Argument cannot be NULL");
  return v7;
}

```

## disassembly

```asm
0x180014f8c  push    rbp
0x180014f8e  push    rbx
0x180014f8f  push    rsi
0x180014f90  push    rdi
0x180014f91  push    r12
0x180014f93  push    r13
0x180014f95  push    r14
0x180014f97  push    r15
0x180014f99  mov     rbp, rsp
0x180014f9c  sub     rsp, 68h
0x180014fa0  mov     r12d, r9d
0x180014fa3  mov     edi, r8d
0x180014fa6  mov     rbx, rcx
0x180014fa9  xor     r13d, r13d
0x180014fac  test    rdx, rdx
0x180014faf  jnz     short loc_180014FF5
0x180014fb1  mov     edi, 80070057h
0x180014fb6  mov     [rsp+68h+var_40], edi
0x180014fba  mov     [rsp+68h+var_48], 16h
0x180014fc2  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x180014fc9  lea     r8, aElementCreatee; "Element::CreateElement"
0x180014fd0  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180014fd7  lea     ebx, [r13+3]
0x180014fdb  mov     ecx, ebx
0x180014fdd  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180014fe2  lea     rdx, aPkgArgumentCan; "    pkg: Argument cannot be NULL"
0x180014fe9  mov     ecx, ebx
0x180014feb  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180014ff0  jmp     loc_180015510
0x180014ff5  mov     [rcx+8], rdx
0x180014ff9  mov     r15, [rdx+10h]
0x180014ffd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180015004  mov     ecx, 14h; unsigned __int64
0x180015009  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001500e  mov     rsi, rax
0x180015011  mov     [rbp+var_30], rax
0x180015015  test    rax, rax
0x180015018  jnz     short loc_18001505E
0x18001501a  mov     edi, 8007000Eh
0x18001501f  mov     [rsp+68h+var_40], edi
0x180015023  mov     [rsp+68h+var_48], 1Dh
0x18001502b  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x180015032  lea     r8, aElementCreatee; "Element::CreateElement"
0x180015039  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180015040  lea     ebx, [rax+3]
0x180015043  mov     ecx, ebx
0x180015045  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18001504a  lea     rdx, aFailedToAlloca_5; "    Failed to allocate spElementIndex.g"...
0x180015051  mov     ecx, ebx
0x180015053  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180015058  nop
0x180015059  jmp     loc_180015510
0x18001505e  mov     eax, 1
0x180015063  lea     r14, qword_18001A280
0x18001506a  movsxd  rcx, eax
0x18001506d  add     rcx, rcx
0x180015070  cmp     [r14+rcx*8], edi
0x180015074  jz      short loc_180015086
0x180015076  inc     eax
0x180015078  cmp     eax, 0Ch
0x18001507b  jb      short loc_18001506A
0x18001507d  mov     r14, cs:off_18001A288; "Invalid"
0x180015084  jmp     short loc_18001508B
0x180015086  mov     r14, [r14+rcx*8+8]
0x18001508b  mov     r9d, r12d
0x18001508e  lea     r8, aU; "%u"
0x180015095  mov     edx, 0Ah; unsigned __int64
0x18001509a  mov     rcx, rsi; unsigned __int16 *
0x18001509d  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800150a2  mov     edi, eax
0x1800150a4  test    eax, eax
0x1800150a6  jns     short loc_1800150E8
0x1800150a8  mov     [rsp+68h+var_40], eax
0x1800150ac  mov     [rsp+68h+var_48], 21h ; '!'
0x1800150b4  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x1800150bb  lea     r8, aElementCreatee; "Element::CreateElement"
0x1800150c2  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x1800150c9  mov     ebx, 3
0x1800150ce  mov     ecx, ebx
0x1800150d0  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800150d5  lea     rdx, aFailedToGetEle_0; "    Failed to get element type string"
0x1800150dc  mov     ecx, ebx
0x1800150de  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800150e3  jmp     loc_180015508
0x1800150e8  mov     r9, rsi; unsigned __int16 *
0x1800150eb  mov     r8, r14; unsigned __int16 *
0x1800150ee  mov     rdx, [rbx+8]; struct ProvisioningPackage *
0x1800150f2  mov     rcx, rbx; this
0x1800150f5  call    ?OpenElement@Element@@QEAAJPEAVProvisioningPackage@@PEBG1@Z; Element::OpenElement(ProvisioningPackage *,ushort const *,ushort const *)
0x1800150fa  mov     edi, eax
0x1800150fc  test    eax, eax
0x1800150fe  jns     short loc_180015136
0x180015100  mov     [rsp+68h+var_40], eax
0x180015104  mov     [rsp+68h+var_48], 25h ; '%'
0x18001510c  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x180015113  lea     r8, aElementCreatee; "Element::CreateElement"
0x18001511a  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180015121  mov     ebx, 3
0x180015126  mov     ecx, ebx
0x180015128  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18001512d  lea     rdx, aFailedToOpenEl; "    Failed to open element"
0x180015134  jmp     short loc_1800150DC
0x180015136  mov     [rbp+lpFileName], r13
0x18001513a  mov     [rbp+arg_8], r13
0x18001513e  lea     rdx, [rbp+lpFileName]
0x180015142  lea     rcx, aTem; "tem"
0x180015149  call    ?GetTemporaryFile@@YAJPEBGPEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@@Z; GetTemporaryFile(ushort const *,wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> *)
0x18001514e  mov     edi, eax
0x180015150  test    eax, eax
0x180015152  jns     short loc_180015194
0x180015154  mov     [rsp+68h+var_40], eax
0x180015158  mov     [rsp+68h+var_48], 2Ah ; '*'
0x180015160  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x180015167  lea     r8, aElementCreatee; "Element::CreateElement"
0x18001516e  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180015175  mov     ebx, 3
0x18001517a  mov     ecx, ebx
0x18001517c  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180015181  lea     rdx, aFailedToGetMet_0; "    Failed to get metadata read tempora"...
0x180015188  mov     ecx, ebx
0x18001518a  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18001518f  jmp     loc_18001530A
0x180015194  lea     rdx, [rbp+arg_8]
0x180015198  lea     rcx, aTem; "tem"
0x18001519f  call    ?GetTemporaryFile@@YAJPEBGPEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@@Z; GetTemporaryFile(ushort const *,wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> *)
0x1800151a4  mov     edi, eax
0x1800151a6  test    eax, eax
0x1800151a8  jns     short loc_1800151E0
0x1800151aa  mov     [rsp+68h+var_40], eax
0x1800151ae  mov     [rsp+68h+var_48], 2Ch ; ','
0x1800151b6  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x1800151bd  lea     r8, aElementCreatee; "Element::CreateElement"
0x1800151c4  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x1800151cb  mov     ebx, 3
0x1800151d0  mov     ecx, ebx
0x1800151d2  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800151d7  lea     rdx, aFailedToGetMet_1; "    Failed to get metadata write tempor"...
0x1800151de  jmp     short loc_180015188
0x1800151e0  lea     rax, [rbp+lpFileName]
0x1800151e4  mov     [rbp+var_28], rax
0x1800151e8  lea     rax, [rbp+arg_8]
0x1800151ec  mov     [rbp+var_20], rax
0x1800151f0  mov     [rbp+var_18], 1
0x1800151f4  mov     r9d, 2
0x1800151fa  mov     r8, [rbx+28h]
0x1800151fe  mov     rdx, [rbp+arg_8]
0x180015202  mov     rcx, r15
0x180015205  call    cs:__imp_WIMAddImagePath
0x18001520b  mov     r12d, 80070000h
0x180015211  test    eax, eax
0x180015213  jz      short loc_18001526F
0x180015215  mov     r8, [rbx+20h]; unsigned __int16 *
0x180015219  mov     rdx, r14; unsigned __int16 *
0x18001521c  mov     rcx, [rbp+arg_8]; unsigned __int16 *
0x180015220  call    ?WriteNewElement@@YAJPEBG00@Z; WriteNewElement(ushort const *,ushort const *,ushort const *)
0x180015225  mov     edi, eax
0x180015227  test    eax, eax
0x180015229  jns     loc_1800153DD
0x18001522f  mov     [rsp+68h+var_40], eax
0x180015233  mov     [rsp+68h+var_48], 39h ; '9'
0x18001523b  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x180015242  lea     r8, aElementCreatee; "Element::CreateElement"
0x180015249  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180015250  mov     ebx, 3
0x180015255  mov     ecx, ebx
0x180015257  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18001525c  lea     rdx, aFailedToWriteN_0; "    Failed to write new element metadat"...
0x180015263  mov     ecx, ebx
0x180015265  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18001526a  jmp     loc_1800152F5
0x18001526f  call    cs:__imp_GetLastError
0x180015275  cmp     eax, 0B7h
0x18001527a  jz      loc_180015338
0x180015280  call    cs:__imp_GetLastError
0x180015286  test    eax, eax
0x180015288  jle     short loc_180015292
0x18001528a  movzx   eax, ax
0x18001528d  or      eax, r12d
0x180015290  test    eax, eax
0x180015292  jns     loc_180015338
0x180015298  call    cs:__imp_GetLastError
0x18001529e  test    eax, eax
0x1800152a0  jle     short loc_1800152A8
0x1800152a2  movzx   eax, ax
0x1800152a5  or      eax, r12d
0x1800152a8  mov     [rsp+68h+var_40], eax
0x1800152ac  mov     [rsp+68h+var_48], 40h ; '@'
0x1800152b4  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x1800152bb  lea     r8, aElementCreatee; "Element::CreateElement"
0x1800152c2  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x1800152c9  mov     ebx, 3
0x1800152ce  mov     ecx, ebx
0x1800152d0  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800152d5  lea     rdx, aFailedToAddMet; "    Failed to add metadata file"
0x1800152dc  mov     ecx, ebx
0x1800152de  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800152e3  call    cs:__imp_GetLastError
0x1800152e9  test    eax, eax
0x1800152eb  mov     edi, eax
0x1800152ed  jle     short loc_1800152F5
0x1800152ef  movzx   edi, ax
0x1800152f2  or      edi, r12d
0x1800152f5  mov     rcx, [rbp+lpFileName]; lpFileName
0x1800152f9  call    cs:__imp_DeleteFileW
0x1800152ff  mov     rcx, [rbp+arg_8]; lpFileName
0x180015303  call    cs:__imp_DeleteFileW
0x180015309  nop
0x18001530a  mov     rcx, [rbp+arg_8]; void *
0x18001530e  mov     [rbp+arg_8], r13
0x180015312  test    rcx, rcx
0x180015315  jz      short loc_18001531D
0x180015317  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001531c  nop
0x18001531d  mov     rcx, [rbp+lpFileName]; void *
0x180015321  mov     [rbp+lpFileName], r13
0x180015325  test    rcx, rcx
0x180015328  jz      loc_180015508
0x18001532e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180015333  jmp     loc_180015508
0x180015338  mov     r9d, 1; int
0x18001533e  mov     r8, [rbp+lpFileName]; unsigned __int16 *
0x180015342  mov     rdx, [rbx+28h]; unsigned __int16 *
0x180015346  mov     rcx, r15; void *
0x180015349  call    ?ExtractFile@@YAJPEAXPEBG1H@Z; ExtractFile(void *,ushort const *,ushort const *,int)
0x18001534e  mov     edi, eax
0x180015350  test    eax, eax
0x180015352  jns     short loc_18001538D
0x180015354  mov     [rsp+68h+var_40], eax
0x180015358  mov     [rsp+68h+var_48], 45h ; 'E'
0x180015360  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x180015367  lea     r8, aElementCreatee; "Element::CreateElement"
0x18001536e  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180015375  mov     ebx, 3
0x18001537a  mov     ecx, ebx
0x18001537c  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180015381  lea     rdx, aFailedToRetrie; "    Failed to retrieve metadata file"
0x180015388  jmp     loc_180015263
0x18001538d  mov     r8, [rbx+20h]; unsigned __int16 *
0x180015391  mov     rdx, [rbp+arg_8]; unsigned __int16 *
0x180015395  mov     rcx, [rbp+lpFileName]; unsigned __int16 *
0x180015399  call    ?AppendNewElement@@YAJPEBG00@Z; AppendNewElement(ushort const *,ushort const *,ushort const *)
0x18001539e  mov     edi, eax
0x1800153a0  test    eax, eax
0x1800153a2  jns     short loc_1800153DD
0x1800153a4  mov     [rsp+68h+var_40], eax
0x1800153a8  mov     [rsp+68h+var_48], 48h ; 'H'
0x1800153b0  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x1800153b7  lea     r8, aElementCreatee; "Element::CreateElement"
0x1800153be  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x1800153c5  mov     ebx, 3
0x1800153ca  mov     ecx, ebx
0x1800153cc  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800153d1  lea     rdx, aFailedToAppend_1; "    Failed to append new element metada"...
0x1800153d8  jmp     loc_180015263
0x1800153dd  mov     r9d, 4000002h
0x1800153e3  mov     r8, [rbx+28h]
0x1800153e7  mov     rdx, [rbp+arg_8]
0x1800153eb  mov     rcx, r15
0x1800153ee  call    cs:__imp_WIMAddImagePath
0x1800153f4  test    eax, eax
0x1800153f6  jnz     short loc_180015455
0x1800153f8  call    cs:__imp_GetLastError
0x1800153fe  test    eax, eax
0x180015400  jle     short loc_18001540A
0x180015402  movzx   eax, ax
0x180015405  or      eax, r12d
0x180015408  test    eax, eax
0x18001540a  jns     short loc_180015455
0x18001540c  call    cs:__imp_GetLastError
0x180015412  test    eax, eax
0x180015414  jle     short loc_18001541C
0x180015416  movzx   eax, ax
0x180015419  or      eax, r12d
0x18001541c  mov     [rsp+68h+var_40], eax
0x180015420  mov     [rsp+68h+var_48], 4Dh ; 'M'
0x180015428  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x18001542f  lea     r8, aElementCreatee; "Element::CreateElement"
0x180015436  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18001543d  mov     ebx, 3
0x180015442  mov     ecx, ebx
0x180015444  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180015449  lea     rdx, aFailedToReAddM; "    Failed to re-add metadata file"
0x180015450  jmp     loc_1800152DC
0x180015455  mov     r9d, 2000002h
0x18001545b  mov     r8, [rbx+10h]
0x18001545f  xor     edx, edx
0x180015461  mov     rcx, r15
0x180015464  call    cs:__imp_WIMAddImagePath
0x18001546a  test    eax, eax
0x18001546c  jnz     short loc_1800154CB
0x18001546e  call    cs:__imp_GetLastError
0x180015474  test    eax, eax
0x180015476  jle     short loc_180015480
0x180015478  movzx   eax, ax
0x18001547b  or      eax, r12d
0x18001547e  test    eax, eax
0x180015480  jns     short loc_1800154CB
0x180015482  call    cs:__imp_GetLastError
0x180015488  test    eax, eax
0x18001548a  jle     short loc_180015492
  ... truncated ...
```
