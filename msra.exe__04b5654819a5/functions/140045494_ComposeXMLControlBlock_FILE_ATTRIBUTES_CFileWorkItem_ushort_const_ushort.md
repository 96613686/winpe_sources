# ComposeXMLControlBlock(FILE_ATTRIBUTES *,CFileWorkItem *,ushort const *,ushort * *)

- ea: `0x140045494`
- end: `0x140045bdf`
- name: `?ComposeXMLControlBlock@@YAJPEAUFILE_ATTRIBUTES@@PEAVCFileWorkItem@@PEBGPEAPEAG@Z`
- size: `1867`
- prototype: `__int64 __fastcall(unsigned __int16 **, struct CFileWorkItem *, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140046bc4`

## callees

- `0x140002463`
- `0x140007fc4`
- `0x1400080fc`
- `0x140034ce4`
- `0x1400350b0`
- `0x140045494`
- `0x14004ad80`
- `0x14004d010`

## import_xrefs

- `KERNEL32!GetSystemTime` at `0x1400459f0`
- `KERNEL32!GetSystemTime` at `0x1400459f0`
- `msvcrt!malloc` at `0x1400459fe`
- `msvcrt!malloc` at `0x1400459fe`
- `msvcrt!free` at `0x140045b5e`
- `msvcrt!free` at `0x140045b5e`
- `ole32!CoCreateInstance` at `0x14004565d`
- `ole32!CoCreateInstance` at `0x14004565d`
- `OLEAUT32!__imp_SysAllocString` at `0x1400455a2`
- `OLEAUT32!__imp_SysAllocString` at `0x1400455b8`
- `OLEAUT32!__imp_SysAllocString` at `0x1400455a2`
- `OLEAUT32!__imp_SysAllocString` at `0x1400455b8`
- `OLEAUT32!__imp_SysFreeString` at `0x140045b2e`
- `OLEAUT32!__imp_SysFreeString` at `0x140045b45`
- `OLEAUT32!__imp_SysFreeString` at `0x140045b2e`
- `OLEAUT32!__imp_SysFreeString` at `0x140045b45`
- `OLEAUT32!__imp_VariantClear` at `0x1400456c5`
- `OLEAUT32!__imp_VariantClear` at `0x140045730`
- `OLEAUT32!__imp_VariantClear` at `0x14004579b`
- `OLEAUT32!__imp_VariantClear` at `0x1400456c5`
- `OLEAUT32!__imp_VariantClear` at `0x140045730`
- `OLEAUT32!__imp_VariantClear` at `0x14004579b`

## string_xrefs

- `0x14004551b`: `ComposeXMLControlBlock`
- `0x140045558`: `ComposeXMLControlBlock`
- `0x1400455d9`: `ComposeXMLControlBlock`
- `0x14004561b`: `ComposeXMLControlBlock`
- `0x14004559b`: `<?xml version="1.0" ?><RCCOMMAND></RCCOMMAND>`
- `0x1400455b1`: `RCCOMMAND`
- `0x140045a7f`: `\ra_ftp_XML_%d_%d_%d_%d_%d_%d_%d_%d`

## pseudocode

```c
__int64 __fastcall ComposeXMLControlBlock(
        unsigned __int16 **a1,
        struct CFileWorkItem *a2,
        unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  CEventLogger *v8; // rcx
  signed int v9; // ebx
  unsigned int v10; // r9d
  OLECHAR *v11; // r13
  BSTR v12; // rax
  CEventLogger *v13; // rcx
  OLECHAR *v14; // r15
  unsigned int v15; // r9d
  HRESULT Instance; // eax
  CEventLogger *v17; // rcx
  struct IXMLDOMDocumentVtbl *lpVtbl; // rax
  CEventLogger *v19; // rcx
  struct IXMLDOMDocumentVtbl *v20; // rax
  CEventLogger *v21; // rcx
  struct IXMLDOMDocumentVtbl *v22; // rax
  CEventLogger *v23; // rcx
  signed int v24; // eax
  CEventLogger *v25; // rcx
  signed int v26; // eax
  CEventLogger *v27; // rcx
  signed int v28; // eax
  CEventLogger *v29; // rcx
  signed int v30; // eax
  CEventLogger *v31; // rcx
  signed int v32; // eax
  CEventLogger *v33; // rcx
  signed int v34; // eax
  CEventLogger *v35; // rcx
  signed int v36; // eax
  CEventLogger *v37; // rcx
  signed int v38; // eax
  CEventLogger *v39; // rcx
  signed int v40; // eax
  CEventLogger *v41; // rcx
  void *v42; // rax
  __int64 v43; // rax
  __int64 v44; // rdx
  unsigned __int16 *v45; // r8
  unsigned __int16 v46; // cx
  CEventLogger *v47; // rcx
  signed int v48; // eax
  CEventLogger *v49; // rcx
  signed int v50; // eax
  CEventLogger *v51; // rcx
  void *v52; // rcx
  LPVOID *ppv; // [rsp+20h] [rbp-E0h]
  struct IXMLDOMDocument *v55; // [rsp+60h] [rbp-A0h] BYREF
  struct IXMLDOMNamedNodeMap *v56; // [rsp+68h] [rbp-98h] BYREF
  __int16 v57; // [rsp+70h] [rbp-90h] BYREF
  VARIANTARG pvarg; // [rsp+78h] [rbp-88h] BYREF
  __int64 v59; // [rsp+90h] [rbp-70h] BYREF
  VARIANTARG v60; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v61; // [rsp+C0h] [rbp-40h]
  __int64 v62; // [rsp+C8h] [rbp-38h]
  struct _SYSTEMTIME SystemTime; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 v64[264]; // [rsp+E0h] [rbp-20h] BYREF

  v55 = 0;
  v57 = -1;
  v61 = 0;
  v59 = 0;
  v62 = 0;
  v56 = 0;
  SystemTime = 0;
  memset_0(v64, 0, 0x20Au);
  if ( !a2 )
  {
    v9 = -2147467261;
    CEventLogger::LogError(
      v8,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\core\\lib\\raftp.cpp",
      0x1A8u,
      L"ComposeXMLControlBlock",
      0x80004003);
    goto LABEL_67;
  }
  if ( !a1 )
  {
    v10 = 425;
LABEL_5:
    v9 = -2147467261;
    CEventLogger::LogError(
      v8,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\core\\lib\\raftp.cpp",
      v10,
      L"ComposeXMLControlBlock",
      0x80004003);
LABEL_65:
    v52 = (void *)*((_QWORD *)a2 + 8);
    if ( v52 )
    {
      free(v52);
      *((_QWORD *)a2 + 8) = 0;
    }
    goto LABEL_67;
  }
  if ( !a3 )
  {
    v10 = 426;
    goto LABEL_5;
  }
  if ( !a4 )
  {
    v10 = 427;
    goto LABEL_5;
  }
  v11 = SysAllocString(L"<?xml version=\"1.0\" ?><RCCOMMAND></RCCOMMAND>");
  v12 = SysAllocString(L"RCCOMMAND");
  v14 = v12;
  if ( !v11 )
  {
    v9 = -2147024882;
    CEventLogger::LogError(
      v13,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\core\\lib\\raftp.cpp",
      0x1AFu,
      L"ComposeXMLControlBlock",
      0x8007000E);
    goto LABEL_62;
  }
  if ( !v12 )
  {
    v15 = 432;
LABEL_14:
    v9 = -2147024882;
    CEventLogger::LogError(
      v13,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\core\\lib\\raftp.cpp",
      v15,
      L"ComposeXMLControlBlock",
      0x8007000E);
    goto LABEL_61;
  }
  Instance = CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &IID_IXMLDOMDocument, (LPVOID *)&v55);
  v9 = Instance;
  if ( Instance >= 0 )
  {
    lpVtbl = v55->lpVtbl;
    pvarg.vt = 11;
    pvarg.iVal = -1;
    v60 = pvarg;
    v9 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, const wchar_t *, VARIANTARG *))lpVtbl[1].GetTypeInfo)(
           v55,
           L"ProhibitDTD",
           &v60);
    VariantClear(&pvarg);
    if ( v9 >= 0 )
    {
      v20 = v55->lpVtbl;
      pvarg.vt = 11;
      pvarg.iVal = 0;
      v60 = pvarg;
      v9 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, const wchar_t *, VARIANTARG *))v20[1].GetTypeInfo)(
             v55,
             L"AllowXsltScript",
             &v60);
      VariantClear(&pvarg);
      if ( v9 >= 0 )
      {
        v22 = v55->lpVtbl;
        pvarg.vt = 11;
        pvarg.iVal = 0;
        v60 = pvarg;
        v9 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, const wchar_t *, VARIANTARG *))v22[1].GetTypeInfo)(
               v55,
               L"AllowDocumentFunction",
               &v60);
        VariantClear(&pvarg);
        if ( v9 >= 0 )
        {
          v24 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, OLECHAR *, __int16 *))v55->lpVtbl->loadXML)(
                  v55,
                  v11,
                  &v57);
          v9 = v24;
          if ( v24 >= 0 )
          {
            v9 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, OLECHAR *, __int64 *))v55->lpVtbl->selectSingleNode)(
                   v55,
                   v14,
                   &v59);
            if ( v9 < 0 )
              goto LABEL_61;
            if ( !v59 )
              goto LABEL_61;
            v9 = (*(__int64 (__fastcall **)(__int64, struct IXMLDOMNamedNodeMap **))(*(_QWORD *)v59 + 136LL))(v59, &v56);
            if ( v9 < 0 || !v56 )
              goto LABEL_61;
            v26 = AddAttributeToAttributeList(v55, v56, L"NAME", L"FILEXFER");
            v9 = v26;
            if ( v26 >= 0 )
            {
              v28 = AddAttributeToAttributeList(v55, v56, L"FILENAME", *a1);
              v9 = v28;
              if ( v28 >= 0 )
              {
                v30 = StringCchPrintfW(v64, 0x105u, L"%I64d", a1[1]);
                v9 = v30;
                if ( v30 >= 0 )
                {
                  v32 = AddAttributeToAttributeList(v55, v56, L"FILESIZE", v64);
                  v9 = v32;
                  if ( v32 >= 0 )
                  {
                    memset_0(v64, 0, 0x20Au);
                    v34 = AddAttributeToAttributeList(v55, v56, L"CHANNELID", a1[2]);
                    v9 = v34;
                    if ( v34 >= 0 )
                    {
                      v36 = AddAttributeToAttributeList(v55, v56, L"CHANNELID", a1[2]);
                      v9 = v36;
                      if ( v36 >= 0 )
                      {
                        v38 = StringCchPrintfW(v64, 0x105u, L"%d", *((unsigned int *)a1 + 6));
                        v9 = v38;
                        if ( v38 >= 0 )
                        {
                          v40 = AddAttributeToAttributeList(v55, v56, L"INTERNALDATA", v64);
                          v9 = v40;
                          if ( v40 >= 0 )
                          {
                            memset_0(v64, 0, 0x20Au);
                            GetSystemTime(&SystemTime);
                            v42 = malloc(0x20Au);
                            *((_QWORD *)a2 + 8) = v42;
                            if ( v42 )
                            {
                              v43 = 2147483646;
                              v44 = 261;
                              v45 = v64;
                              do
                              {
                                if ( !v43 )
                                  break;
                                v46 = *a3;
                                if ( !*a3 )
                                  break;
                                ++a3;
                                *v45++ = v46;
                                --v43;
                                --v44;
                              }
                              while ( v44 );
                              v9 = v44 == 0 ? 0x8007007A : 0;
                              v47 = (CEventLogger *)(v45 - 1);
                              if ( v44 )
                                v47 = (CEventLogger *)v45;
                              *(_WORD *)v47 = 0;
                              if ( v44 )
                              {
                                v48 = StringCchCatW(v64, 0x105u, L"\\ra_ftp_XML_%d_%d_%d_%d_%d_%d_%d_%d");
                                v9 = v48;
                                if ( v48 >= 0 )
                                {
                                  LODWORD(ppv) = SystemTime.wYear;
                                  v50 = StringCchPrintfW(
                                          *((unsigned __int16 **)a2 + 8),
                                          0x104u,
                                          v64,
                                          *((unsigned int *)a2 + 8),
                                          ppv,
                                          SystemTime.wMonth,
                                          SystemTime.wDay,
                                          SystemTime.wHour,
                                          SystemTime.wMinute,
                                          SystemTime.wSecond,
                                          SystemTime.wMilliseconds);
                                  v9 = v50;
                                  if ( v50 >= 0 )
                                    v9 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, unsigned __int16 **))v55->lpVtbl->get_xml)(
                                           v55,
                                           a4);
                                  else
                                    CEventLogger::LogError(
                                      v51,
                                      &Recoverable_Error,
                                      L"base\\diagnosis\\ra\\core\\lib\\raftp.cpp",
                                      0x223u,
                                      L"ComposeXMLControlBlock",
                                      v50);
                                }
                                else
                                {
                                  CEventLogger::LogError(
                                    v49,
                                    &Recoverable_Error,
                                    L"base\\diagnosis\\ra\\core\\lib\\raftp.cpp",
                                    0x216u,
                                    L"ComposeXMLControlBlock",
                                    v48);
                                }
                              }
                              else
                              {
                                CEventLogger::LogError(
                                  v47,
                                  &Recoverable_Error,
                                  L"base\\diagnosis\\ra\\core\\lib\\raftp.cpp",
                                  0x212u,
                                  L"ComposeXMLControlBlock",
                                  v9);
                              }
                              goto LABEL_61;
                            }
                            v15 = 528;
                            goto LABEL_14;
                          }
                          CEventLogger::LogError(
                            v41,
                            &Recoverable_Error,
                            L"base\\diagnosis\\ra\\core\\lib\\raftp.cpp",
                            0x205u,
                            L"ComposeXMLControlBlock",
                            v40);
                        }
                        else
                        {
                          CEventLogger::LogError(
                            v39,
                            &Recoverable_Error,
                            L"base\\diagnosis\\ra\\core\\lib\\raftp.cpp",
                            0x1FFu,
                            L"ComposeXMLControlBlock",
                            v38);
                        }
                      }
                      else
                      {
                        CEventLogger::LogError(
                          v37,
                          &Recoverable_Error,
                          L"base\\diagnosis\\ra\\core\\lib\\raftp.cpp",
                          0x1F9u,
                          L"ComposeXMLControlBlock",
                          v36);
                      }
                    }
                    else
                    {
                      CEventLogger::LogError(
                        v35,
                        &Recoverable_Error,
                        L"base\\diagnosis\\ra\\core\\lib\\raftp.cpp",
                        0x1F3u,
                        L"ComposeXMLControlBlock",
                        v34);
                    }
                  }
                  else
                  {
                    CEventLogger::LogError(
                      v33,
                      &Recoverable_Error,
                      L"base\\diagnosis\\ra\\core\\lib\\raftp.cpp",
                      0x1EBu,
                      L"ComposeXMLControlBlock",
                      v32);
                  }
                }
                else
                {
                  CEventLogger::LogError(
                    v31,
                    &Recoverable_Error,
                    L"base\\diagnosis\\ra\\core\\lib\\raftp.cpp",
                    0x1E5u,
                    L"ComposeXMLControlBlock",
                    v30);
                }
              }
              else
              {
                CEventLogger::LogError(
                  v29,
                  &Recoverable_Error,
                  L"base\\diagnosis\\ra\\core\\lib\\raftp.cpp",
                  0x1DFu,
                  L"ComposeXMLControlBlock",
                  v28);
              }
            }
            else
            {
              CEventLogger::LogError(
                v27,
                &Recoverable_Error,
                L"base\\diagnosis\\ra\\core\\lib\\raftp.cpp",
                0x1D9u,
                L"ComposeXMLControlBlock",
                v26);
            }
          }
          else
          {
            CEventLogger::LogError(
              v25,
              &Recoverable_Error,
              L"base\\diagnosis\\ra\\core\\lib\\raftp.cpp",
              0x1BEu,
              L"ComposeXMLControlBlock",
              v24);
          }
        }
        else
        {
          CEventLogger::LogError(
            v23,
            &Recoverable_Error,
            L"base\\diagnosis\\ra\\core\\lib\\raftp.cpp",
            0x1BCu,
            L"ComposeXMLControlBlock",
            v9);
        }
      }
      else
      {
        CEventLogger::LogError(
          v21,
          &Recoverable_Error,
          L"base\\diagnosis\\ra\\core\\lib\\raftp.cpp",
          0x1BBu,
          L"ComposeXMLControlBlock",
          v9);
      }
    }
    else
    {
      CEventLogger::LogError(
        v19,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\core\\lib\\raftp.cpp",
        0x1BAu,
        L"ComposeXMLControlBlock",
        v9);
    }
  }
  else
  {
    CEventLogger::LogError(
      v17,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\core\\lib\\raftp.cpp",
      0x1B8u,
      L"ComposeXMLControlBlock",
      Instance);
  }
LABEL_61:
  SysFreeString(v11);
LABEL_62:
  if ( v14 )
    SysFreeString(v14);
  if ( v9 < 0 )
    goto LABEL_65;
LABEL_67:
  if ( v56 )
    ((void (__fastcall *)(struct IXMLDOMNamedNodeMap *))v56->lpVtbl->Release)(v56);
  if ( v59 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
  if ( v55 )
    ((void (__fastcall *)(struct IXMLDOMDocument *))v55->lpVtbl->Release)(v55);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140045494  mov     [rsp-8+arg_10], rbx
0x140045499  push    rbp
0x14004549a  push    rsi
0x14004549b  push    rdi
0x14004549c  push    r12
0x14004549e  push    r13
0x1400454a0  push    r14
0x1400454a2  push    r15
0x1400454a4  lea     rbp, [rsp-200h]
0x1400454ac  sub     rsp, 300h
0x1400454b3  mov     rax, cs:__security_cookie
0x1400454ba  xor     rax, rsp
0x1400454bd  mov     [rbp+230h+var_40], rax
0x1400454c4  mov     r12, r9
0x1400454c7  mov     rsi, r8
0x1400454ca  mov     r14, rdx
0x1400454cd  mov     rdi, rcx
0x1400454d0  xor     r13d, r13d
0x1400454d3  mov     [rsp+330h+var_2D0], r13
0x1400454d8  or      eax, 0FFFFFFFFh
0x1400454db  mov     [rsp+330h+var_2C0], ax
0x1400454e0  mov     [rbp+230h+var_270], r13
0x1400454e4  mov     [rbp+230h+var_2A0], r13
0x1400454e8  mov     [rbp+230h+var_268], r13
0x1400454ec  mov     [rsp+330h+var_2C8], r13
0x1400454f1  xorps   xmm0, xmm0
0x1400454f4  movups  xmmword ptr [rbp+230h+SystemTime.wYear], xmm0
0x1400454f8  xor     edx, edx; Val
0x1400454fa  mov     r8d, 20Ah; Size
0x140045500  lea     rcx, [rbp+230h+var_250]; void *
0x140045504  call    memset_0
0x140045509  test    r14, r14
0x14004550c  jnz     short loc_140045545
0x14004550e  mov     ebx, 80004003h
0x140045513  mov     [rsp+330h+var_308], 80004003h; unsigned int
0x14004551b  lea     rax, aComposexmlcont; "ComposeXMLControlBlock"
0x140045522  mov     [rsp+330h+ppv], rax; unsigned __int16 *
0x140045527  mov     r9d, 1A8h; unsigned int
0x14004552d  lea     r8, aBaseDiagnosisR_15; "base\\diagnosis\\ra\\core\\lib\\raftp.c"...
0x140045534  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14004553b  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140045540  jmp     loc_140045B6E
0x140045545  test    rdi, rdi
0x140045548  jnz     short loc_140045581
0x14004554a  mov     r9d, 1A9h; unsigned int
0x140045550  mov     [rsp+330h+var_308], 80004003h; unsigned int
0x140045558  lea     rax, aComposexmlcont; "ComposeXMLControlBlock"
0x14004555f  mov     ebx, 80004003h
0x140045564  mov     [rsp+330h+ppv], rax; unsigned __int16 *
0x140045569  lea     r8, aBaseDiagnosisR_15; "base\\diagnosis\\ra\\core\\lib\\raftp.c"...
0x140045570  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140045577  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14004557c  jmp     loc_140045B55
0x140045581  test    rsi, rsi
0x140045584  jnz     short loc_14004558E
0x140045586  mov     r9d, 1AAh
0x14004558c  jmp     short loc_140045550
0x14004558e  test    r12, r12
0x140045591  jnz     short loc_14004559B
0x140045593  mov     r9d, 1ABh
0x140045599  jmp     short loc_140045550
0x14004559b  lea     rcx, aXmlVersion10Rc; "<?xml version=\"1.0\" ?><RCCOMMAND></RC"...
0x1400455a2  call    cs:__imp_SysAllocString
0x1400455a9  nop     dword ptr [rax+rax+00h]
0x1400455ae  mov     r13, rax
0x1400455b1  lea     rcx, aRccommand; "RCCOMMAND"
0x1400455b8  call    cs:__imp_SysAllocString
0x1400455bf  nop     dword ptr [rax+rax+00h]
0x1400455c4  mov     r15, rax
0x1400455c7  test    r13, r13
0x1400455ca  jnz     short loc_140045603
0x1400455cc  mov     ebx, 8007000Eh
0x1400455d1  mov     [rsp+330h+var_308], 8007000Eh; unsigned int
0x1400455d9  lea     rax, aComposexmlcont; "ComposeXMLControlBlock"
0x1400455e0  mov     [rsp+330h+ppv], rax; unsigned __int16 *
0x1400455e5  mov     r9d, 1AFh; unsigned int
0x1400455eb  lea     r8, aBaseDiagnosisR_15; "base\\diagnosis\\ra\\core\\lib\\raftp.c"...
0x1400455f2  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x1400455f9  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1400455fe  jmp     loc_140045B3A
0x140045603  test    r15, r15
0x140045606  jnz     short loc_14004563F
0x140045608  mov     r9d, 1B0h; unsigned int
0x14004560e  mov     [rsp+330h+var_308], 8007000Eh; unsigned int
0x140045616  mov     ebx, 8007000Eh
0x14004561b  lea     rax, aComposexmlcont; "ComposeXMLControlBlock"
0x140045622  mov     [rsp+330h+ppv], rax; unsigned __int16 *
0x140045627  lea     r8, aBaseDiagnosisR_15; "base\\diagnosis\\ra\\core\\lib\\raftp.c"...
0x14004562e  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140045635  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14004563a  jmp     loc_140045B2B
0x14004563f  lea     rax, [rsp+330h+var_2D0]
0x140045644  mov     [rsp+330h+ppv], rax; ppv
0x140045649  lea     r9, IID_IXMLDOMDocument; riid
0x140045650  xor     edx, edx; pUnkOuter
0x140045652  lea     r8d, [rdx+1]; dwClsContext
0x140045656  lea     rcx, CLSID_DOMDocument60; rclsid
0x14004565d  call    cs:__imp_CoCreateInstance
0x140045664  nop     dword ptr [rax+rax+00h]
0x140045669  mov     ebx, eax
0x14004566b  test    eax, eax
0x14004566d  jns     short loc_14004567B
0x14004566f  mov     [rsp+330h+var_308], eax
0x140045673  mov     r9d, 1B8h
0x140045679  jmp     short loc_14004561B
0x14004567b  mov     rcx, [rsp+330h+var_2D0]
0x140045680  mov     rax, [rcx]
0x140045683  mov     edx, 0Bh
0x140045688  mov     word ptr [rsp+330h+pvarg], dx
0x14004568d  or      edx, 0FFFFFFFFh
0x140045690  mov     word ptr [rbp+230h+pvarg+8], dx
0x140045694  movups  xmm0, xmmword ptr [rsp+330h+pvarg]
0x140045699  movaps  [rbp+230h+var_290], xmm0
0x14004569d  movsd   xmm1, qword ptr [rbp+230h+pvarg+10h]
0x1400456a2  movsd   [rbp+230h+var_280], xmm1
0x1400456a7  lea     r8, [rbp+230h+var_290]
0x1400456ab  lea     rdx, aProhibitdtd; "ProhibitDTD"
0x1400456b2  mov     rax, [rax+280h]
0x1400456b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400456be  mov     ebx, eax
0x1400456c0  lea     rcx, [rsp+330h+pvarg]; pvarg
0x1400456c5  call    cs:__imp_VariantClear
0x1400456cc  nop     dword ptr [rax+rax+00h]
0x1400456d1  test    ebx, ebx
0x1400456d3  jns     short loc_1400456E4
0x1400456d5  mov     [rsp+330h+var_308], ebx
0x1400456d9  mov     r9d, 1BAh
0x1400456df  jmp     loc_14004561B
0x1400456e4  mov     r9, [rsp+330h+var_2D0]
0x1400456e9  mov     rax, [r9]
0x1400456ec  mov     ecx, 0Bh
0x1400456f1  mov     word ptr [rsp+330h+pvarg], cx
0x1400456f6  xor     ecx, ecx
0x1400456f8  mov     word ptr [rbp+230h+pvarg+8], cx
0x1400456fc  movups  xmm0, xmmword ptr [rsp+330h+pvarg]
0x140045701  movaps  [rbp+230h+var_290], xmm0
0x140045705  movsd   xmm1, qword ptr [rbp+230h+pvarg+10h]
0x14004570a  movsd   [rbp+230h+var_280], xmm1
0x14004570f  lea     r8, [rbp+230h+var_290]
0x140045713  lea     rdx, aAllowxsltscrip; "AllowXsltScript"
0x14004571a  mov     rcx, r9
0x14004571d  mov     rax, [rax+280h]
0x140045724  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045729  mov     ebx, eax
0x14004572b  lea     rcx, [rsp+330h+pvarg]; pvarg
0x140045730  call    cs:__imp_VariantClear
0x140045737  nop     dword ptr [rax+rax+00h]
0x14004573c  test    ebx, ebx
0x14004573e  jns     short loc_14004574F
0x140045740  mov     [rsp+330h+var_308], ebx
0x140045744  mov     r9d, 1BBh
0x14004574a  jmp     loc_14004561B
0x14004574f  mov     r9, [rsp+330h+var_2D0]
0x140045754  mov     rax, [r9]
0x140045757  mov     ecx, 0Bh
0x14004575c  mov     word ptr [rsp+330h+pvarg], cx
0x140045761  xor     ecx, ecx
0x140045763  mov     word ptr [rbp+230h+pvarg+8], cx
0x140045767  movups  xmm0, xmmword ptr [rsp+330h+pvarg]
0x14004576c  movaps  [rbp+230h+var_290], xmm0
0x140045770  movsd   xmm1, qword ptr [rbp+230h+pvarg+10h]
0x140045775  movsd   [rbp+230h+var_280], xmm1
0x14004577a  lea     r8, [rbp+230h+var_290]
0x14004577e  lea     rdx, aAllowdocumentf; "AllowDocumentFunction"
0x140045785  mov     rcx, r9
0x140045788  mov     rax, [rax+280h]
0x14004578f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045794  mov     ebx, eax
0x140045796  lea     rcx, [rsp+330h+pvarg]; pvarg
0x14004579b  call    cs:__imp_VariantClear
0x1400457a2  nop     dword ptr [rax+rax+00h]
0x1400457a7  test    ebx, ebx
0x1400457a9  jns     short loc_1400457BA
0x1400457ab  mov     [rsp+330h+var_308], ebx
0x1400457af  mov     r9d, 1BCh
0x1400457b5  jmp     loc_14004561B
0x1400457ba  mov     rcx, [rsp+330h+var_2D0]
0x1400457bf  mov     rax, [rcx]
0x1400457c2  lea     r8, [rsp+330h+var_2C0]
0x1400457c7  mov     rdx, r13
0x1400457ca  mov     rax, [rax+208h]
0x1400457d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400457d6  mov     ebx, eax
0x1400457d8  test    eax, eax
0x1400457da  jns     short loc_1400457EB
0x1400457dc  mov     [rsp+330h+var_308], eax
0x1400457e0  mov     r9d, 1BEh
0x1400457e6  jmp     loc_14004561B
0x1400457eb  mov     rcx, [rsp+330h+var_2D0]
0x1400457f0  mov     rax, [rcx]
0x1400457f3  lea     r8, [rbp+230h+var_2A0]
0x1400457f7  mov     rdx, r15
0x1400457fa  mov     rax, [rax+128h]
0x140045801  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045806  mov     ebx, eax
0x140045808  test    eax, eax
0x14004580a  js      loc_140045B2B
0x140045810  mov     rcx, [rbp+230h+var_2A0]
0x140045814  test    rcx, rcx
0x140045817  setz    al
0x14004581a  test    al, al
0x14004581c  jnz     loc_140045B2B
0x140045822  mov     rax, [rcx]
0x140045825  lea     rdx, [rsp+330h+var_2C8]
0x14004582a  mov     rax, [rax+88h]
0x140045831  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045836  mov     ebx, eax
0x140045838  test    eax, eax
0x14004583a  js      loc_140045B2B
0x140045840  mov     rdx, [rsp+330h+var_2C8]; struct IXMLDOMNamedNodeMap *
0x140045845  test    rdx, rdx
0x140045848  setz    al
0x14004584b  test    al, al
0x14004584d  jnz     loc_140045B2B
0x140045853  lea     r9, aFilexfer; "FILEXFER"
0x14004585a  lea     r8, aName; "NAME"
0x140045861  mov     rcx, [rsp+330h+var_2D0]; struct IXMLDOMDocument *
0x140045866  call    ?AddAttributeToAttributeList@@YAJPEAUIXMLDOMDocument@@PEAUIXMLDOMNamedNodeMap@@PEAG2@Z; AddAttributeToAttributeList(IXMLDOMDocument *,IXMLDOMNamedNodeMap *,ushort *,ushort *)
0x14004586b  mov     ebx, eax
0x14004586d  test    eax, eax
0x14004586f  jns     short loc_140045880
0x140045871  mov     [rsp+330h+var_308], eax
0x140045875  mov     r9d, 1D9h
0x14004587b  jmp     loc_14004561B
0x140045880  mov     r9, [rdi]; unsigned __int16 *
0x140045883  lea     r8, aFilename; "FILENAME"
0x14004588a  mov     rdx, [rsp+330h+var_2C8]; struct IXMLDOMNamedNodeMap *
0x14004588f  mov     rcx, [rsp+330h+var_2D0]; struct IXMLDOMDocument *
0x140045894  call    ?AddAttributeToAttributeList@@YAJPEAUIXMLDOMDocument@@PEAUIXMLDOMNamedNodeMap@@PEAG2@Z; AddAttributeToAttributeList(IXMLDOMDocument *,IXMLDOMNamedNodeMap *,ushort *,ushort *)
0x140045899  mov     ebx, eax
0x14004589b  test    eax, eax
0x14004589d  jns     short loc_1400458AE
0x14004589f  mov     [rsp+330h+var_308], eax
0x1400458a3  mov     r9d, 1DFh
0x1400458a9  jmp     loc_14004561B
0x1400458ae  mov     r9, [rdi+8]
0x1400458b2  lea     r8, aI64d; "%I64d"
0x1400458b9  mov     edx, 105h; unsigned __int64
0x1400458be  lea     rcx, [rbp+230h+var_250]; unsigned __int16 *
0x1400458c2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400458c7  mov     ebx, eax
0x1400458c9  test    eax, eax
0x1400458cb  jns     short loc_1400458DC
0x1400458cd  mov     [rsp+330h+var_308], eax
0x1400458d1  mov     r9d, 1E5h
0x1400458d7  jmp     loc_14004561B
0x1400458dc  lea     r9, [rbp+230h+var_250]; unsigned __int16 *
0x1400458e0  lea     r8, aFilesize; "FILESIZE"
0x1400458e7  mov     rdx, [rsp+330h+var_2C8]; struct IXMLDOMNamedNodeMap *
0x1400458ec  mov     rcx, [rsp+330h+var_2D0]; struct IXMLDOMDocument *
0x1400458f1  call    ?AddAttributeToAttributeList@@YAJPEAUIXMLDOMDocument@@PEAUIXMLDOMNamedNodeMap@@PEAG2@Z; AddAttributeToAttributeList(IXMLDOMDocument *,IXMLDOMNamedNodeMap *,ushort *,ushort *)
0x1400458f6  mov     ebx, eax
0x1400458f8  test    eax, eax
0x1400458fa  jns     short loc_14004590B
0x1400458fc  mov     [rsp+330h+var_308], eax
0x140045900  mov     r9d, 1EBh
0x140045906  jmp     loc_14004561B
0x14004590b  xor     edx, edx; Val
0x14004590d  mov     r8d, 20Ah; Size
0x140045913  lea     rcx, [rbp+230h+var_250]; void *
0x140045917  call    memset_0
0x14004591c  mov     r9, [rdi+10h]; unsigned __int16 *
0x140045920  lea     r8, aChannelid; "CHANNELID"
0x140045927  mov     rdx, [rsp+330h+var_2C8]; struct IXMLDOMNamedNodeMap *
0x14004592c  mov     rcx, [rsp+330h+var_2D0]; struct IXMLDOMDocument *
0x140045931  call    ?AddAttributeToAttributeList@@YAJPEAUIXMLDOMDocument@@PEAUIXMLDOMNamedNodeMap@@PEAG2@Z; AddAttributeToAttributeList(IXMLDOMDocument *,IXMLDOMNamedNodeMap *,ushort *,ushort *)
0x140045936  mov     ebx, eax
0x140045938  test    eax, eax
0x14004593a  jns     short loc_14004594B
0x14004593c  mov     [rsp+330h+var_308], eax
0x140045940  mov     r9d, 1F3h
0x140045946  jmp     loc_14004561B
0x14004594b  mov     r9, [rdi+10h]; unsigned __int16 *
0x14004594f  lea     r8, aChannelid; "CHANNELID"
0x140045956  mov     rdx, [rsp+330h+var_2C8]; struct IXMLDOMNamedNodeMap *
0x14004595b  mov     rcx, [rsp+330h+var_2D0]; struct IXMLDOMDocument *
0x140045960  call    ?AddAttributeToAttributeList@@YAJPEAUIXMLDOMDocument@@PEAUIXMLDOMNamedNodeMap@@PEAG2@Z; AddAttributeToAttributeList(IXMLDOMDocument *,IXMLDOMNamedNodeMap *,ushort *,ushort *)
0x140045965  mov     ebx, eax
0x140045967  test    eax, eax
0x140045969  jns     short loc_14004597A
0x14004596b  mov     [rsp+330h+var_308], eax
0x14004596f  mov     r9d, 1F9h
0x140045975  jmp     loc_14004561B
0x14004597a  mov     r9d, [rdi+18h]
0x14004597e  lea     r8, aD; "%d"
0x140045985  mov     edx, 105h; unsigned __int64
0x14004598a  lea     rcx, [rbp+230h+var_250]; unsigned __int16 *
0x14004598e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140045993  mov     ebx, eax
0x140045995  xor     edi, edi
0x140045997  test    eax, eax
0x140045999  jns     short loc_1400459AA
0x14004599b  mov     [rsp+330h+var_308], eax
0x14004599f  mov     r9d, 1FFh
0x1400459a5  jmp     loc_14004561B
0x1400459aa  lea     r9, [rbp+230h+var_250]; unsigned __int16 *
0x1400459ae  lea     r8, aInternaldata; "INTERNALDATA"
0x1400459b5  mov     rdx, [rsp+330h+var_2C8]; struct IXMLDOMNamedNodeMap *
0x1400459ba  mov     rcx, [rsp+330h+var_2D0]; struct IXMLDOMDocument *
0x1400459bf  call    ?AddAttributeToAttributeList@@YAJPEAUIXMLDOMDocument@@PEAUIXMLDOMNamedNodeMap@@PEAG2@Z; AddAttributeToAttributeList(IXMLDOMDocument *,IXMLDOMNamedNodeMap *,ushort *,ushort *)
  ... truncated ...
```
