# getInnerConnectionPropertiesFromDOMNode(IXMLDOMNode *,ulong,ulong *,_PEAP_CONN_PROPERTIES *,uchar * *,ulong *)

- ea: `0x18005fb70`
- end: `0x18005ff49`
- name: `?getInnerConnectionPropertiesFromDOMNode@@YAKPEAUIXMLDOMNode@@KPEAKPEAU_PEAP_CONN_PROPERTIES@@PEAPEAE1@Z`
- size: `985`
- prototype: `unsigned int(struct IXMLDOMNode *, unsigned int, unsigned int *, struct _PEAP_CONN_PROPERTIES *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005f230`

## callees

- `0x180004bd0`
- `0x1800075b0`
- `0x18000f350`
- `0x18000f690`
- `0x180012130`
- `0x18001e530`
- `0x18001f020`
- `0x1800200b4`
- `0x1800227ac`
- `0x18005fb70`
- `0x18007c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005fcd7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005fcd7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005fd2b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005fd80`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005fd2b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005fd80`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005feed`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005feed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fce5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fd39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fd8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fce5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fd39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fd8e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005fe7c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005fe7c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005fefd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005fefd`
- `OLEAUT32!__imp_SysFreeString` at `0x18005ff07`
- `OLEAUT32!__imp_SysFreeString` at `0x18005ff07`

## string_xrefs

- `0x18005fd21`: `RasEapCreateConnectionProperties`
- `0x18005fbd6`: `//EapHostConfig:Config`

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
0x18005fb70  mov     rax, rsp
0x18005fb73  mov     [rax+8], rbx
0x18005fb77  mov     [rax+20h], rsi
0x18005fb7b  mov     [rax+18h], r8
0x18005fb7f  mov     [rax+10h], edx
0x18005fb82  push    rbp
0x18005fb83  push    rdi
0x18005fb84  push    r12
0x18005fb86  push    r13
0x18005fb88  push    r15
0x18005fb8a  mov     rbp, rsp
0x18005fb8d  sub     rsp, 80h
0x18005fb94  mov     r12, r9
0x18005fb97  xor     r13d, r13d
0x18005fb9a  mov     [rbp+lpLibFileName], r13
0x18005fb9e  mov     dword ptr [rbp+uBytes+4], r13d
0x18005fba2  mov     [rbp+var_8], r13
0x18005fba6  mov     [rbp+Source], r13
0x18005fbaa  mov     dword ptr [rbp+uBytes], r13d
0x18005fbae  mov     [rbp+var_10], r13
0x18005fbb2  mov     [rbp+var_30], r13
0x18005fbb6  mov     [rbp+var_18], r13
0x18005fbba  mov     ebx, r13d
0x18005fbbd  mov     [rbp+var_20], rbx
0x18005fbc1  mov     rax, [rbp+arg_28]
0x18005fbc5  mov     [rax], r13d
0x18005fbc8  mov     rax, [rbp+arg_20]
0x18005fbcc  mov     [rax], r13
0x18005fbcf  mov     [r8], r13d
0x18005fbd2  lea     r8, [rbp+var_10]; struct IXMLDOMNode **
0x18005fbd6  lea     rdx, aEaphostconfigC; "//EapHostConfig:Config"
0x18005fbdd  call    ?getSingleNode@@YAJPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; getSingleNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x18005fbe2  mov     edi, eax
0x18005fbe4  test    eax, eax
0x18005fbe6  jz      short loc_18005FC2A
0x18005fbe8  lea     rsi, WPP_GLOBAL_Control
0x18005fbef  mov     rcx, cs:WPP_GLOBAL_Control
0x18005fbf6  cmp     rcx, rsi
0x18005fbf9  jz      short loc_18005FC10
0x18005fbfb  mov     edx, 0F0h
0x18005fc00  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18005fc07  mov     rcx, [rcx+10h]
0x18005fc0b  call    WPP_SF_
0x18005fc10  mov     eax, edi
0x18005fc12  and     eax, 1FFF0000h
0x18005fc17  cmp     eax, 70000h
0x18005fc1c  jnz     loc_18005FF04
0x18005fc22  movzx   edi, di
0x18005fc25  jmp     loc_18005FF04
0x18005fc2a  lea     r8, [rbp+var_30]; struct IXMLDOMNode **
0x18005fc2e  lea     rdx, aBaseeapconnect_4; "baseeapconnectionpropertiesv1:Eap[1]"
0x18005fc35  mov     rcx, [rbp+var_10]; struct IXMLDOMNode *
0x18005fc39  call    ?getSingleNode@@YAJPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; getSingleNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x18005fc3e  mov     edi, eax
0x18005fc40  test    eax, eax
0x18005fc42  jz      short loc_18005FC5E
0x18005fc44  lea     rsi, WPP_GLOBAL_Control
0x18005fc4b  mov     rcx, cs:WPP_GLOBAL_Control
0x18005fc52  cmp     rcx, rsi
0x18005fc55  jz      short loc_18005FC10
0x18005fc57  mov     edx, 0F1h
0x18005fc5c  jmp     short loc_18005FC00
0x18005fc5e  lea     r8, [rbp+var_18]; struct IXMLDOMNode **
0x18005fc62  lea     rdx, aBaseeapconnect_0; "baseeapconnectionpropertiesv1:Type[1]"
0x18005fc69  mov     rcx, [rbp+var_30]; struct IXMLDOMNode *
0x18005fc6d  call    ?getSingleNode@@YAJPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; getSingleNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x18005fc72  mov     edi, eax
0x18005fc74  test    eax, eax
0x18005fc76  jz      short loc_18005FC95
0x18005fc78  lea     rsi, WPP_GLOBAL_Control
0x18005fc7f  mov     rcx, cs:WPP_GLOBAL_Control
0x18005fc86  cmp     rcx, rsi
0x18005fc89  jz      short loc_18005FC10
0x18005fc8b  mov     edx, 0F2h
0x18005fc90  jmp     loc_18005FC00
0x18005fc95  lea     r8, [rbp+var_20]; unsigned __int16 **
0x18005fc99  lea     rdx, [rbp+uBytes+4]; unsigned int *
0x18005fc9d  mov     rcx, [rbp+var_18]; struct IXMLDOMNode *
0x18005fca1  call    ?ReadDWORDFromXMLNode@@YAJPEAUIXMLDOMNode@@PEAKPEAPEAG@Z; ReadDWORDFromXMLNode(IXMLDOMNode *,ulong *,ushort * *)
0x18005fca6  mov     rbx, [rbp+var_20]
0x18005fcaa  test    eax, eax
0x18005fcac  jz      short loc_18005FCB8
0x18005fcae  mov     edi, 57h ; 'W'
0x18005fcb3  jmp     loc_18005FF04
0x18005fcb8  lea     rdx, [rbp+lpLibFileName]; unsigned __int16 **
0x18005fcbc  mov     rcx, rbx; unsigned __int16 *
0x18005fcbf  call    ?getLibraryPathForEapTypeId@@YAKPEBGPEAPEAG@Z; getLibraryPathForEapTypeId(ushort const *,ushort * *)
0x18005fcc4  mov     edi, eax
0x18005fcc6  test    eax, eax
0x18005fcc8  jnz     loc_18005FEF3
0x18005fcce  xor     r8d, r8d; dwFlags
0x18005fcd1  xor     edx, edx; hFile
0x18005fcd3  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x18005fcd7  call    cs:__imp_LoadLibraryExW
0x18005fcdd  mov     r15, rax
0x18005fce0  test    rax, rax
0x18005fce3  jnz     short loc_18005FD21
0x18005fce5  call    cs:__imp_GetLastError
0x18005fceb  mov     edi, eax
0x18005fced  lea     rsi, WPP_GLOBAL_Control
0x18005fcf4  mov     rcx, cs:WPP_GLOBAL_Control
0x18005fcfb  cmp     rcx, rsi
0x18005fcfe  jz      loc_18005FEF3
0x18005fd04  mov     edx, 0F3h
0x18005fd09  mov     r9d, eax
0x18005fd0c  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18005fd13  mov     rcx, [rcx+10h]
0x18005fd17  call    WPP_SF_d
0x18005fd1c  jmp     loc_18005FEF3
0x18005fd21  lea     rdx, aRaseapcreateco_2; "RasEapCreateConnectionProperties"
0x18005fd28  mov     rcx, r15; hModule
0x18005fd2b  call    cs:__imp_GetProcAddress
0x18005fd31  mov     rdi, rax
0x18005fd34  test    rax, rax
0x18005fd37  jnz     short loc_18005FD76
0x18005fd39  call    cs:__imp_GetLastError
0x18005fd3f  mov     edi, eax
0x18005fd41  lea     rsi, WPP_GLOBAL_Control
0x18005fd48  mov     rcx, cs:WPP_GLOBAL_Control
0x18005fd4f  cmp     rcx, rsi
0x18005fd52  jz      loc_18005FEEA
0x18005fd58  mov     edx, 0F4h
0x18005fd5d  mov     r9, [rbp+lpLibFileName]
0x18005fd61  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18005fd68  mov     rcx, [rcx+10h]
0x18005fd6c  call    WPP_SF_S
0x18005fd71  jmp     loc_18005FEEA
0x18005fd76  lea     rdx, ProcName; "RasEapFreeMemory"
0x18005fd7d  mov     rcx, r15; hModule
0x18005fd80  call    cs:__imp_GetProcAddress
0x18005fd86  mov     r13, rax
0x18005fd89  test    rax, rax
0x18005fd8c  jnz     short loc_18005FDCB
0x18005fd8e  call    cs:__imp_GetLastError
0x18005fd94  mov     edi, eax
0x18005fd96  lea     rsi, WPP_GLOBAL_Control
0x18005fd9d  mov     rcx, cs:WPP_GLOBAL_Control
0x18005fda4  cmp     rcx, rsi
0x18005fda7  jz      loc_18005FEE7
0x18005fdad  mov     edx, 0F5h
0x18005fdb2  mov     r9, [rbp+lpLibFileName]
0x18005fdb6  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18005fdbd  mov     rcx, [rcx+10h]
0x18005fdc1  call    WPP_SF_S
0x18005fdc6  jmp     loc_18005FEE7
0x18005fdcb  lea     rsi, WPP_GLOBAL_Control
0x18005fdd2  test    r12, r12
0x18005fdd5  jz      short loc_18005FE37
0x18005fdd7  lea     rdx, [rbp+var_8]; struct _PEAP_ENTRY_CONN_PROPERTIES **
0x18005fddb  mov     rcx, r12; struct _PEAP_CONN_PROPERTIES *
0x18005fdde  call    ?PeapGetFirstEntryConnProp@@YAKPEAU_PEAP_CONN_PROPERTIES@@PEAPEFAU_PEAP_ENTRY_CONN_PROPERTIES@@@Z; PeapGetFirstEntryConnProp(_PEAP_CONN_PROPERTIES *,_PEAP_ENTRY_CONN_PROPERTIES * *)
0x18005fde3  test    eax, eax
0x18005fde5  jnz     short loc_18005FE13
0x18005fde7  mov     r9, [rbp+var_8]
0x18005fdeb  test    r9, r9
0x18005fdee  jz      short loc_18005FE13
0x18005fdf0  mov     eax, [r9+4]
0x18005fdf4  sub     eax, 0Fh
0x18005fdf7  add     r9, 0Ch
0x18005fdfb  lea     rcx, [rbp+uBytes]
0x18005fdff  mov     [rsp+80h+var_50], rcx
0x18005fe04  lea     rcx, [rbp+Source]
0x18005fe08  mov     [rsp+80h+var_58], rcx
0x18005fe0d  mov     [rsp+80h+var_60], eax
0x18005fe11  jmp     short loc_18005FE54
0x18005fe13  mov     rcx, cs:WPP_GLOBAL_Control
0x18005fe1a  cmp     rcx, rsi
0x18005fe1d  jz      short loc_18005FE37
0x18005fe1f  mov     edx, 0F6h
0x18005fe24  mov     r9d, eax
0x18005fe27  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18005fe2e  mov     rcx, [rcx+10h]
0x18005fe32  call    WPP_SF_d
0x18005fe37  lea     rax, [rbp+uBytes]
0x18005fe3b  mov     [rsp+80h+var_50], rax
0x18005fe40  lea     rax, [rbp+Source]
0x18005fe44  mov     [rsp+80h+var_58], rax
0x18005fe49  mov     [rsp+80h+var_60], 0
0x18005fe51  xor     r9d, r9d
0x18005fe54  mov     r12d, dword ptr [rbp+uBytes+4]
0x18005fe58  mov     r8, [rbp+var_30]
0x18005fe5c  mov     edx, [rbp+arg_8]
0x18005fe5f  mov     ecx, r12d
0x18005fe62  mov     rax, rdi
0x18005fe65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fe6a  mov     edi, eax
0x18005fe6c  test    eax, eax
0x18005fe6e  jnz     short loc_18005FED6
0x18005fe70  mov     eax, dword ptr [rbp+uBytes]
0x18005fe73  test    eax, eax
0x18005fe75  jz      short loc_18005FED6
0x18005fe77  mov     edx, eax; uBytes
0x18005fe79  lea     ecx, [rdi+40h]; uFlags
0x18005fe7c  call    cs:__imp_LocalAlloc
0x18005fe82  mov     rcx, [rbp+arg_20]
0x18005fe86  mov     [rcx], rax
0x18005fe89  test    rax, rax
0x18005fe8c  jnz     short loc_18005FEB4
0x18005fe8e  lea     edi, [rax+0Eh]
0x18005fe91  mov     rcx, cs:WPP_GLOBAL_Control
0x18005fe98  cmp     rcx, rsi
0x18005fe9b  jz      short loc_18005FED6
0x18005fe9d  mov     edx, 0F7h
0x18005fea2  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18005fea9  mov     rcx, [rcx+10h]
0x18005fead  call    WPP_SF_
0x18005feb2  jmp     short loc_18005FED6
0x18005feb4  mov     edx, dword ptr [rbp+uBytes]; DestinationSize
0x18005feb7  mov     r9d, edx; SourceSize
0x18005feba  mov     r8, [rbp+Source]; Source
0x18005febe  mov     rcx, rax; Destination
0x18005fec1  call    memcpy_s_0
0x18005fec6  mov     eax, dword ptr [rbp+uBytes]
0x18005fec9  mov     rcx, [rbp+arg_28]
0x18005fecd  mov     [rcx], eax
0x18005fecf  mov     rax, [rbp+arg_10]
0x18005fed3  mov     [rax], r12d
0x18005fed6  mov     rcx, [rbp+Source]
0x18005feda  test    rcx, rcx
0x18005fedd  jz      short loc_18005FEE7
0x18005fedf  mov     rax, r13
0x18005fee2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fee7  xor     r13d, r13d
0x18005feea  mov     rcx, r15; hLibModule
0x18005feed  call    cs:__imp_FreeLibrary
0x18005fef3  cmp     [rbp+lpLibFileName], r13
0x18005fef7  jz      short loc_18005FF04
0x18005fef9  mov     rcx, [rbp+lpLibFileName]; hMem
0x18005fefd  call    cs:__imp_LocalFree
0x18005ff03  nop
0x18005ff04  mov     rcx, rbx; bstrString
0x18005ff07  call    cs:__imp_SysFreeString
0x18005ff0d  nop
0x18005ff0e  lea     rcx, [rbp+var_18]
0x18005ff12  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18005ff17  nop
0x18005ff18  lea     rcx, [rbp+var_30]
0x18005ff1c  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18005ff21  nop
0x18005ff22  lea     rcx, [rbp+var_10]
0x18005ff26  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18005ff2b  mov     eax, edi
0x18005ff2d  lea     r11, [rsp+80h+var_s0]
0x18005ff35  mov     rbx, [r11+30h]
0x18005ff39  mov     rsi, [r11+48h]
0x18005ff3d  mov     rsp, r11
0x18005ff40  pop     r15
0x18005ff42  pop     r13
0x18005ff44  pop     r12
0x18005ff46  pop     rdi
0x18005ff47  pop     rbp
0x18005ff48  retn
```
