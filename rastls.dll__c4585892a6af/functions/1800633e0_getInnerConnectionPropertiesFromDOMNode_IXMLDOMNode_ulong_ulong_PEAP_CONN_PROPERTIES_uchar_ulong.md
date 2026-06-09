# getInnerConnectionPropertiesFromDOMNode(IXMLDOMNode *,ulong,ulong *,_PEAP_CONN_PROPERTIES *,uchar * *,ulong *)

- ea: `0x1800633e0`
- end: `0x1800637f6`
- name: `?getInnerConnectionPropertiesFromDOMNode@@YAKPEAUIXMLDOMNode@@KPEAKPEAU_PEAP_CONN_PROPERTIES@@PEAPEAE1@Z`
- size: `1046`
- prototype: `unsigned int(struct IXMLDOMNode *, unsigned int, unsigned int *, struct _PEAP_CONN_PROPERTIES *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180062a50`

## callees

- `0x180005010`
- `0x180007d00`
- `0x180010140`
- `0x1800104b0`
- `0x180013330`
- `0x1800201a0`
- `0x180020d80`
- `0x180021e74`
- `0x180025294`
- `0x1800633e0`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180063547`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180063547`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800635a7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180063608`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800635a7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180063608`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180063787`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180063787`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006355b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800635bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006361c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006355b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800635bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006361c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180063710`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180063710`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006379d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006379d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800637ad`
- `OLEAUT32!__imp_SysFreeString` at `0x1800637ad`

## string_xrefs

- `0x18006359d`: `RasEapCreateConnectionProperties`
- `0x180063446`: `//EapHostConfig:Config`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall getInnerConnectionPropertiesFromDOMNode(
        struct IXMLDOMNode *a1,
        unsigned int a2,
        unsigned int *a3,
        struct _PEAP_CONN_PROPERTIES *a4,
        unsigned __int8 **a5,
        unsigned int *a6)
{
  unsigned __int16 *v7; // rbx
  unsigned int SingleNode; // edi
  struct _EAPTLS_CONTROL_BLOCK *v9; // rcx
  __int64 v10; // rdx
  int v11; // eax
  HMODULE Library; // rax
  HMODULE v13; // r15
  DWORD LastError; // eax
  FARPROC ProcAddress; // rdi
  void (*v16)(void); // r13
  unsigned int FirstEntryConnProp; // eax
  char *v18; // r9
  unsigned int v19; // r12d
  unsigned __int8 *v20; // rax
  int v22; // [rsp+20h] [rbp-60h]
  SIZE_T uBytes; // [rsp+40h] [rbp-40h] BYREF
  LPCWSTR lpLibFileName; // [rsp+48h] [rbp-38h] BYREF
  struct IXMLDOMNode *v25; // [rsp+50h] [rbp-30h] BYREF
  void *Source; // [rsp+58h] [rbp-28h] BYREF
  unsigned __int16 *v27; // [rsp+60h] [rbp-20h] BYREF
  struct IXMLDOMNode *v28; // [rsp+68h] [rbp-18h] BYREF
  struct IXMLDOMNode *v29; // [rsp+70h] [rbp-10h] BYREF
  struct _PEAP_ENTRY_CONN_PROPERTIES *v30; // [rsp+78h] [rbp-8h] BYREF

  lpLibFileName = 0;
  v30 = 0;
  Source = 0;
  uBytes = 0;
  v29 = 0;
  v25 = 0;
  v28 = 0;
  v7 = 0;
  v27 = 0;
  *a6 = 0;
  *a5 = 0;
  *a3 = 0;
  SingleNode = getSingleNode(a1, L"//EapHostConfig:Config", &v29);
  if ( SingleNode )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_5;
    v10 = 240;
    goto LABEL_4;
  }
  SingleNode = getSingleNode(v29, L"baseeapconnectionpropertiesv1:Eap[1]", &v25);
  if ( SingleNode )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      v10 = 241;
LABEL_4:
      WPP_SF_(*((_QWORD *)v9 + 2), v10, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids);
      goto LABEL_5;
    }
    goto LABEL_5;
  }
  SingleNode = getSingleNode(v25, L"baseeapconnectionpropertiesv1:Type[1]", &v28);
  if ( SingleNode )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      v10 = 242;
      goto LABEL_4;
    }
LABEL_5:
    if ( (SingleNode & 0x1FFF0000) == 0x70000 )
      SingleNode = (unsigned __int16)SingleNode;
    goto LABEL_43;
  }
  v11 = ReadDWORDFromXMLNode(v28, (unsigned int *)&uBytes + 1, &v27);
  v7 = v27;
  if ( v11 )
  {
    SingleNode = 87;
    goto LABEL_43;
  }
  SingleNode = getLibraryPathForEapTypeId(v27, (unsigned __int16 **)&lpLibFileName);
  if ( !SingleNode )
  {
    Library = LoadLibraryExW(lpLibFileName, 0, 0);
    v13 = Library;
    if ( !Library )
    {
      LastError = GetLastError();
      SingleNode = LastError;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 243, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, LastError);
      goto LABEL_41;
    }
    ProcAddress = GetProcAddress(Library, "RasEapCreateConnectionProperties");
    if ( !ProcAddress )
    {
      SingleNode = GetLastError();
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          244,
          WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids,
          lpLibFileName);
LABEL_40:
      FreeLibrary(v13);
      goto LABEL_41;
    }
    v16 = (void (*)(void))GetProcAddress(v13, "RasEapFreeMemory");
    if ( !v16 )
    {
      SingleNode = GetLastError();
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          245,
          WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids,
          lpLibFileName);
      goto LABEL_40;
    }
    if ( a4 )
    {
      FirstEntryConnProp = PeapGetFirstEntryConnProp(a4, &v30);
      if ( !FirstEntryConnProp && v30 )
      {
        v18 = (char *)v30 + 12;
        v22 = *((_DWORD *)v30 + 1) - 15;
        goto LABEL_32;
      }
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          246,
          WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids,
          FirstEntryConnProp);
    }
    v22 = 0;
    v18 = 0;
LABEL_32:
    v19 = HIDWORD(uBytes);
    SingleNode = ((__int64 (__fastcall *)(_QWORD, _QWORD, struct IXMLDOMNode *, char *, int, void **, SIZE_T *))ProcAddress)(
                   HIDWORD(uBytes),
                   a2,
                   v25,
                   v18,
                   v22,
                   &Source,
                   &uBytes);
    if ( !SingleNode && (_DWORD)uBytes )
    {
      v20 = (unsigned __int8 *)LocalAlloc(SingleNode + 64, (unsigned int)uBytes);
      *a5 = v20;
      if ( v20 )
      {
        memcpy_s_0(v20, (unsigned int)uBytes, Source, (unsigned int)uBytes);
        *a6 = uBytes;
        *a3 = v19;
      }
      else
      {
        SingleNode = 14;
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 247, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids);
      }
    }
    if ( Source )
      v16();
    goto LABEL_40;
  }
LABEL_41:
  if ( lpLibFileName )
    LocalFree((HLOCAL)lpLibFileName);
LABEL_43:
  SysFreeString(v7);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v28);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v25);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v29);
  return SingleNode;
}

```

## disassembly

```asm
0x1800633e0  mov     rax, rsp
0x1800633e3  mov     [rax+8], rbx
0x1800633e7  mov     [rax+20h], rsi
0x1800633eb  mov     [rax+18h], r8
0x1800633ef  mov     [rax+10h], edx
0x1800633f2  push    rbp
0x1800633f3  push    rdi
0x1800633f4  push    r12
0x1800633f6  push    r13
0x1800633f8  push    r15
0x1800633fa  mov     rbp, rsp
0x1800633fd  sub     rsp, 80h
0x180063404  mov     r12, r9
0x180063407  xor     r13d, r13d
0x18006340a  mov     [rbp+lpLibFileName], r13
0x18006340e  mov     dword ptr [rbp+uBytes+4], r13d
0x180063412  mov     [rbp+var_8], r13
0x180063416  mov     [rbp+Source], r13
0x18006341a  mov     dword ptr [rbp+uBytes], r13d
0x18006341e  mov     [rbp+var_10], r13
0x180063422  mov     [rbp+var_30], r13
0x180063426  mov     [rbp+var_18], r13
0x18006342a  mov     ebx, r13d
0x18006342d  mov     [rbp+var_20], rbx
0x180063431  mov     rax, [rbp+arg_28]
0x180063435  mov     [rax], r13d
0x180063438  mov     rax, [rbp+arg_20]
0x18006343c  mov     [rax], r13
0x18006343f  mov     [r8], r13d
0x180063442  lea     r8, [rbp+var_10]; struct IXMLDOMNode **
0x180063446  lea     rdx, aEaphostconfigC; "//EapHostConfig:Config"
0x18006344d  call    ?getSingleNode@@YAJPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; getSingleNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x180063452  mov     edi, eax
0x180063454  test    eax, eax
0x180063456  jz      short loc_18006349A
0x180063458  lea     rsi, WPP_GLOBAL_Control
0x18006345f  mov     rcx, cs:WPP_GLOBAL_Control
0x180063466  cmp     rcx, rsi
0x180063469  jz      short loc_180063480
0x18006346b  mov     edx, 0F0h
0x180063470  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180063477  mov     rcx, [rcx+10h]
0x18006347b  call    WPP_SF_
0x180063480  mov     eax, edi
0x180063482  and     eax, 1FFF0000h
0x180063487  cmp     eax, 70000h
0x18006348c  jnz     loc_1800637AA
0x180063492  movzx   edi, di
0x180063495  jmp     loc_1800637AA
0x18006349a  lea     r8, [rbp+var_30]; struct IXMLDOMNode **
0x18006349e  lea     rdx, aBaseeapconnect_4; "baseeapconnectionpropertiesv1:Eap[1]"
0x1800634a5  mov     rcx, [rbp+var_10]; struct IXMLDOMNode *
0x1800634a9  call    ?getSingleNode@@YAJPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; getSingleNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x1800634ae  mov     edi, eax
0x1800634b0  test    eax, eax
0x1800634b2  jz      short loc_1800634CE
0x1800634b4  lea     rsi, WPP_GLOBAL_Control
0x1800634bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800634c2  cmp     rcx, rsi
0x1800634c5  jz      short loc_180063480
0x1800634c7  mov     edx, 0F1h
0x1800634cc  jmp     short loc_180063470
0x1800634ce  lea     r8, [rbp+var_18]; struct IXMLDOMNode **
0x1800634d2  lea     rdx, aBaseeapconnect_0; "baseeapconnectionpropertiesv1:Type[1]"
0x1800634d9  mov     rcx, [rbp+var_30]; struct IXMLDOMNode *
0x1800634dd  call    ?getSingleNode@@YAJPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; getSingleNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x1800634e2  mov     edi, eax
0x1800634e4  test    eax, eax
0x1800634e6  jz      short loc_180063505
0x1800634e8  lea     rsi, WPP_GLOBAL_Control
0x1800634ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800634f6  cmp     rcx, rsi
0x1800634f9  jz      short loc_180063480
0x1800634fb  mov     edx, 0F2h
0x180063500  jmp     loc_180063470
0x180063505  lea     r8, [rbp+var_20]; unsigned __int16 **
0x180063509  lea     rdx, [rbp+uBytes+4]; unsigned int *
0x18006350d  mov     rcx, [rbp+var_18]; struct IXMLDOMNode *
0x180063511  call    ?ReadDWORDFromXMLNode@@YAJPEAUIXMLDOMNode@@PEAKPEAPEAG@Z; ReadDWORDFromXMLNode(IXMLDOMNode *,ulong *,ushort * *)
0x180063516  mov     rbx, [rbp+var_20]
0x18006351a  test    eax, eax
0x18006351c  jz      short loc_180063528
0x18006351e  mov     edi, 57h ; 'W'
0x180063523  jmp     loc_1800637AA
0x180063528  lea     rdx, [rbp+lpLibFileName]; unsigned __int16 **
0x18006352c  mov     rcx, rbx; unsigned __int16 *
0x18006352f  call    ?getLibraryPathForEapTypeId@@YAKPEBGPEAPEAG@Z; getLibraryPathForEapTypeId(ushort const *,ushort * *)
0x180063534  mov     edi, eax
0x180063536  test    eax, eax
0x180063538  jnz     loc_180063793
0x18006353e  xor     r8d, r8d; dwFlags
0x180063541  xor     edx, edx; hFile
0x180063543  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x180063547  call    cs:__imp_LoadLibraryExW
0x18006354e  nop     dword ptr [rax+rax+00h]
0x180063553  mov     r15, rax
0x180063556  test    rax, rax
0x180063559  jnz     short loc_18006359D
0x18006355b  call    cs:__imp_GetLastError
0x180063562  nop     dword ptr [rax+rax+00h]
0x180063567  mov     edi, eax
0x180063569  lea     rsi, WPP_GLOBAL_Control
0x180063570  mov     rcx, cs:WPP_GLOBAL_Control
0x180063577  cmp     rcx, rsi
0x18006357a  jz      loc_180063793
0x180063580  mov     edx, 0F3h
0x180063585  mov     r9d, eax
0x180063588  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18006358f  mov     rcx, [rcx+10h]
0x180063593  call    WPP_SF_d
0x180063598  jmp     loc_180063793
0x18006359d  lea     rdx, aRaseapcreateco_2; "RasEapCreateConnectionProperties"
0x1800635a4  mov     rcx, r15; hModule
0x1800635a7  call    cs:__imp_GetProcAddress
0x1800635ae  nop     dword ptr [rax+rax+00h]
0x1800635b3  mov     rdi, rax
0x1800635b6  test    rax, rax
0x1800635b9  jnz     short loc_1800635FE
0x1800635bb  call    cs:__imp_GetLastError
0x1800635c2  nop     dword ptr [rax+rax+00h]
0x1800635c7  mov     edi, eax
0x1800635c9  lea     rsi, WPP_GLOBAL_Control
0x1800635d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800635d7  cmp     rcx, rsi
0x1800635da  jz      loc_180063784
0x1800635e0  mov     edx, 0F4h
0x1800635e5  mov     r9, [rbp+lpLibFileName]
0x1800635e9  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x1800635f0  mov     rcx, [rcx+10h]
0x1800635f4  call    WPP_SF_S
0x1800635f9  jmp     loc_180063784
0x1800635fe  lea     rdx, ProcName; "RasEapFreeMemory"
0x180063605  mov     rcx, r15; hModule
0x180063608  call    cs:__imp_GetProcAddress
0x18006360f  nop     dword ptr [rax+rax+00h]
0x180063614  mov     r13, rax
0x180063617  test    rax, rax
0x18006361a  jnz     short loc_18006365F
0x18006361c  call    cs:__imp_GetLastError
0x180063623  nop     dword ptr [rax+rax+00h]
0x180063628  mov     edi, eax
0x18006362a  lea     rsi, WPP_GLOBAL_Control
0x180063631  mov     rcx, cs:WPP_GLOBAL_Control
0x180063638  cmp     rcx, rsi
0x18006363b  jz      loc_180063781
0x180063641  mov     edx, 0F5h
0x180063646  mov     r9, [rbp+lpLibFileName]
0x18006364a  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180063651  mov     rcx, [rcx+10h]
0x180063655  call    WPP_SF_S
0x18006365a  jmp     loc_180063781
0x18006365f  lea     rsi, WPP_GLOBAL_Control
0x180063666  test    r12, r12
0x180063669  jz      short loc_1800636CB
0x18006366b  lea     rdx, [rbp+var_8]; struct _PEAP_ENTRY_CONN_PROPERTIES **
0x18006366f  mov     rcx, r12; struct _PEAP_CONN_PROPERTIES *
0x180063672  call    ?PeapGetFirstEntryConnProp@@YAKPEAU_PEAP_CONN_PROPERTIES@@PEAPEFAU_PEAP_ENTRY_CONN_PROPERTIES@@@Z; PeapGetFirstEntryConnProp(_PEAP_CONN_PROPERTIES *,_PEAP_ENTRY_CONN_PROPERTIES * *)
0x180063677  test    eax, eax
0x180063679  jnz     short loc_1800636A7
0x18006367b  mov     r9, [rbp+var_8]
0x18006367f  test    r9, r9
0x180063682  jz      short loc_1800636A7
0x180063684  mov     eax, [r9+4]
0x180063688  sub     eax, 0Fh
0x18006368b  add     r9, 0Ch
0x18006368f  lea     rcx, [rbp+uBytes]
0x180063693  mov     [rsp+80h+var_50], rcx
0x180063698  lea     rcx, [rbp+Source]
0x18006369c  mov     [rsp+80h+var_58], rcx
0x1800636a1  mov     [rsp+80h+var_60], eax
0x1800636a5  jmp     short loc_1800636E8
0x1800636a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800636ae  cmp     rcx, rsi
0x1800636b1  jz      short loc_1800636CB
0x1800636b3  mov     edx, 0F6h
0x1800636b8  mov     r9d, eax
0x1800636bb  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x1800636c2  mov     rcx, [rcx+10h]
0x1800636c6  call    WPP_SF_d
0x1800636cb  lea     rax, [rbp+uBytes]
0x1800636cf  mov     [rsp+80h+var_50], rax
0x1800636d4  lea     rax, [rbp+Source]
0x1800636d8  mov     [rsp+80h+var_58], rax
0x1800636dd  mov     [rsp+80h+var_60], 0
0x1800636e5  xor     r9d, r9d
0x1800636e8  mov     r12d, dword ptr [rbp+uBytes+4]
0x1800636ec  mov     r8, [rbp+var_30]
0x1800636f0  mov     edx, [rbp+arg_8]
0x1800636f3  mov     ecx, r12d
0x1800636f6  mov     rax, rdi
0x1800636f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800636fe  mov     edi, eax
0x180063700  test    eax, eax
0x180063702  jnz     short loc_180063770
0x180063704  mov     eax, dword ptr [rbp+uBytes]
0x180063707  test    eax, eax
0x180063709  jz      short loc_180063770
0x18006370b  mov     edx, eax; uBytes
0x18006370d  lea     ecx, [rdi+40h]; uFlags
0x180063710  call    cs:__imp_LocalAlloc
0x180063717  nop     dword ptr [rax+rax+00h]
0x18006371c  mov     rcx, [rbp+arg_20]
0x180063720  mov     [rcx], rax
0x180063723  test    rax, rax
0x180063726  jnz     short loc_18006374E
0x180063728  lea     edi, [rax+0Eh]
0x18006372b  mov     rcx, cs:WPP_GLOBAL_Control
0x180063732  cmp     rcx, rsi
0x180063735  jz      short loc_180063770
0x180063737  mov     edx, 0F7h
0x18006373c  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180063743  mov     rcx, [rcx+10h]
0x180063747  call    WPP_SF_
0x18006374c  jmp     short loc_180063770
0x18006374e  mov     edx, dword ptr [rbp+uBytes]; DestinationSize
0x180063751  mov     r9d, edx; SourceSize
0x180063754  mov     r8, [rbp+Source]; Source
0x180063758  mov     rcx, rax; Destination
0x18006375b  call    memcpy_s_0
0x180063760  mov     eax, dword ptr [rbp+uBytes]
0x180063763  mov     rcx, [rbp+arg_28]
0x180063767  mov     [rcx], eax
0x180063769  mov     rax, [rbp+arg_10]
0x18006376d  mov     [rax], r12d
0x180063770  mov     rcx, [rbp+Source]
0x180063774  test    rcx, rcx
0x180063777  jz      short loc_180063781
0x180063779  mov     rax, r13
0x18006377c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063781  xor     r13d, r13d
0x180063784  mov     rcx, r15; hLibModule
0x180063787  call    cs:__imp_FreeLibrary
0x18006378e  nop     dword ptr [rax+rax+00h]
0x180063793  cmp     [rbp+lpLibFileName], r13
0x180063797  jz      short loc_1800637AA
0x180063799  mov     rcx, [rbp+lpLibFileName]; hMem
0x18006379d  call    cs:__imp_LocalFree
0x1800637a4  nop     dword ptr [rax+rax+00h]
0x1800637a9  nop
0x1800637aa  mov     rcx, rbx; bstrString
0x1800637ad  call    cs:__imp_SysFreeString
0x1800637b4  nop     dword ptr [rax+rax+00h]
0x1800637b9  nop
0x1800637ba  lea     rcx, [rbp+var_18]
0x1800637be  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x1800637c3  nop
0x1800637c4  lea     rcx, [rbp+var_30]
0x1800637c8  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x1800637cd  nop
0x1800637ce  lea     rcx, [rbp+var_10]
0x1800637d2  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x1800637d7  mov     eax, edi
0x1800637d9  lea     r11, [rsp+80h+var_s0]
0x1800637e1  mov     rbx, [r11+30h]
0x1800637e5  mov     rsi, [r11+48h]
0x1800637e9  mov     rsp, r11
0x1800637ec  pop     r15
0x1800637ee  pop     r13
0x1800637f0  pop     r12
0x1800637f2  pop     rdi
0x1800637f3  pop     rbp
0x1800637f4  retn
```
