# GetSupportDocument(_SUPPORT_RESPONSE *,IXMLDOMDocument * *,ulong *)

- ea: `0x140051164`
- end: `0x14005169b`
- name: `?GetSupportDocument@@YAJPEAU_SUPPORT_RESPONSE@@PEAPEAUIXMLDOMDocument@@PEAK@Z`
- size: `1335`
- prototype: `__int64 __fastcall(struct _SUPPORT_RESPONSE *, struct IXMLDOMDocument **, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400516a4`

## callees

- `0x140050354`
- `0x140050ae0`
- `0x140050ce4`
- `0x140050e84`
- `0x140051164`
- `0x1400521e0`
- `0x140063010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14005149e`
- `KERNEL32!GetLastError` at `0x14005149e`
- `KERNEL32!HeapAlloc` at `0x140051443`
- `KERNEL32!HeapAlloc` at `0x140051443`
- `KERNEL32!HeapFree` at `0x1400515ef`
- `KERNEL32!HeapFree` at `0x1400515ef`
- `KERNEL32!GetProcessHeap` at `0x14005142f`
- `KERNEL32!GetProcessHeap` at `0x1400515db`
- `KERNEL32!GetProcessHeap` at `0x14005142f`
- `KERNEL32!GetProcessHeap` at `0x1400515db`
- `KERNEL32!WideCharToMultiByte` at `0x14005148c`
- `KERNEL32!WideCharToMultiByte` at `0x14005148c`
- `OLEAUT32!__imp_SysFreeString` at `0x1400513eb`
- `OLEAUT32!__imp_SysFreeString` at `0x140051668`
- `OLEAUT32!__imp_SysFreeString` at `0x1400513eb`
- `OLEAUT32!__imp_SysFreeString` at `0x140051668`
- `OLEAUT32!__imp_SysStringLen` at `0x140051420`
- `OLEAUT32!__imp_SysStringLen` at `0x140051420`
- `OLEAUT32!__imp_VariantInit` at `0x1400511b4`
- `OLEAUT32!__imp_VariantInit` at `0x1400511b4`
- `OLEAUT32!__imp_VariantClear` at `0x1400514c5`
- `OLEAUT32!__imp_VariantClear` at `0x1400515ca`
- `OLEAUT32!__imp_VariantClear` at `0x1400514c5`
- `OLEAUT32!__imp_VariantClear` at `0x1400515ca`
- `ole32!CoCreateInstance` at `0x1400511dd`
- `ole32!CoCreateInstance` at `0x1400511dd`
- `ole32!CreateStreamOnHGlobal` at `0x1400514f2`
- `ole32!CreateStreamOnHGlobal` at `0x1400514f2`

## string_xrefs

- `0x14005150c`: `SOAPAction: "http://diagnostics.microsoft.com/QueryQueue"\nContent-Type: text/xml; charset=UTF-8`
- `0x14005121b`: `ENVELOPE.XML`
- `0x1400512cd`: `//token`
- `0x14005134e`: `//cultureName`

## pseudocode

```c
__int64 __fastcall GetSupportDocument(struct _SUPPORT_RESPONSE *a1, struct IXMLDOMDocument **a2, unsigned int *a3)
{
  char *v4; // r14
  unsigned int v7; // esi
  int Instance; // ebx
  const unsigned __int16 *v9; // r8
  struct IXMLDOMDocumentVtbl *lpVtbl; // rax
  int v11; // eax
  int v12; // eax
  unsigned int cbMultiByte; // edi
  HANDLE ProcessHeap; // rax
  CHAR *v15; // rax
  signed int LastError; // eax
  HRESULT (__stdcall *load)(IXMLDOMDocument *, VARIANT, VARIANT_BOOL *); // rax
  HANDLE v18; // rax
  BSTR bstrString; // [rsp+40h] [rbp-49h] BYREF
  struct IXMLDOMDocument *ppv; // [rsp+48h] [rbp-41h] BYREF
  __int64 v22; // [rsp+50h] [rbp-39h] BYREF
  LPSTREAM ppstm; // [rsp+58h] [rbp-31h] BYREF
  __int64 v24; // [rsp+60h] [rbp-29h] BYREF
  VARIANTARG pvarg; // [rsp+68h] [rbp-21h] BYREF
  VARIANTARG v26[4]; // [rsp+80h] [rbp-9h] BYREF
  __int16 v27; // [rsp+108h] [rbp+7Fh] BYREF

  v27 = 0;
  v22 = 0;
  v24 = 0;
  v4 = 0;
  ppv = 0;
  ppstm = 0;
  bstrString = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v7 = 1;
  Instance = CoCreateInstance(&CLSID_FreeThreadedDOMDocument, 0, 0x15u, &IID_IXMLDOMDocument, (LPVOID *)&ppv);
  if ( Instance >= 0 )
  {
    Instance = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, _QWORD))ppv->lpVtbl->put_async)(ppv, 0);
    if ( Instance >= 0 )
    {
      Instance = CreateStreamFromResource(0, L"ENVELOPE.XML", v9, &ppstm);
      if ( Instance >= 0 )
      {
        Instance = (**(__int64 (__fastcall ***)(LPSTREAM, GUID *, ULONG *))ppstm)(
                     ppstm,
                     &IID_IUnknown,
                     (ULONG *)&pvarg.cyVal);
        if ( Instance >= 0 )
        {
          pvarg.vt = 13;
          lpVtbl = ppv->lpVtbl;
          v26[0] = pvarg;
          Instance = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, VARIANTARG *, __int16 *))lpVtbl->load)(
                       ppv,
                       v26,
                       &v27);
          if ( Instance >= 0 )
          {
            if ( v27 || (Instance = DebugXmlParseError(ppv), Instance >= 0) )
            {
              Instance = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, __int64 *))ppv->lpVtbl->get_documentElement)(
                           ppv,
                           &v24);
              if ( Instance >= 0 )
              {
                Instance = AssignString(&bstrString, L"//token");
                if ( Instance >= 0 )
                {
                  if ( v22 )
                  {
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
                    v22 = 0;
                  }
                  v11 = (*(__int64 (__fastcall **)(__int64, BSTR, __int64 *))(*(_QWORD *)v24 + 296LL))(
                          v24,
                          bstrString,
                          &v22);
                  Instance = v11;
                  if ( v11 >= 0 && v11 != 1 )
                  {
                    Instance = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v22 + 216LL))(
                                 v22,
                                 *((_QWORD *)a1 + 2));
                    if ( Instance >= 0 )
                    {
                      Instance = AssignString(&bstrString, L"//cultureName");
                      if ( Instance >= 0 )
                      {
                        if ( v22 )
                        {
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
                          v22 = 0;
                        }
                        v12 = (*(__int64 (__fastcall **)(__int64, BSTR, __int64 *))(*(_QWORD *)v24 + 296LL))(
                                v24,
                                bstrString,
                                &v22);
                        Instance = v12;
                        if ( v12 >= 0 && v12 != 1 )
                        {
                          Instance = GetLanguage(&bstrString);
                          if ( Instance >= 0 )
                          {
                            Instance = (*(__int64 (__fastcall **)(__int64, BSTR))(*(_QWORD *)v22 + 216LL))(
                                         v22,
                                         bstrString);
                            if ( Instance >= 0 )
                            {
                              if ( bstrString )
                              {
                                SysFreeString(bstrString);
                                bstrString = 0;
                              }
                              Instance = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, BSTR *))ppv->lpVtbl->get_xml)(
                                           ppv,
                                           &bstrString);
                              if ( Instance >= 0 )
                              {
                                cbMultiByte = SysStringLen(bstrString) + 1;
                                ProcessHeap = GetProcessHeap();
                                v15 = (CHAR *)HeapAlloc(ProcessHeap, 0, cbMultiByte);
                                v4 = v15;
                                if ( v15 )
                                {
                                  if ( WideCharToMultiByte(0xFDE9u, 0, bstrString, cbMultiByte, v15, cbMultiByte, 0, 0) > 0 )
                                    goto LABEL_31;
                                  LastError = GetLastError();
                                  Instance = LastError;
                                  if ( LastError > 0 )
                                    Instance = (unsigned __int16)LastError | 0x80070000;
                                  if ( Instance >= 0 )
                                  {
LABEL_31:
                                    VariantClear(&pvarg);
                                    if ( ppstm )
                                    {
                                      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
                                      ppstm = 0;
                                    }
                                    Instance = CreateStreamOnHGlobal(0, 1, &ppstm);
                                    if ( Instance >= 0 )
                                    {
                                      Instance = Request(
                                                   *((LPCWSTR *)a1 + 4),
                                                   L"POST",
                                                   L"SOAPAction: \"http://diagnostics.microsoft.com/QueryQueue\"\n"
                                                    "Content-Type: text/xml; charset=UTF-8",
                                                   v4,
                                                   ppstm,
                                                   a3);
                                      if ( Instance >= 0 )
                                      {
                                        Instance = (**(__int64 (__fastcall ***)(LPSTREAM, GUID *, ULONG *))ppstm)(
                                                     ppstm,
                                                     &IID_IUnknown,
                                                     (ULONG *)&pvarg.cyVal);
                                        if ( Instance >= 0 )
                                        {
                                          v26[0].pRecInfo = pvarg.pRecInfo;
                                          pvarg.vt = 13;
                                          load = ppv->lpVtbl->load;
                                          *(_OWORD *)&v26[0].vt = *(_OWORD *)&pvarg.vt;
                                          Instance = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, VARIANTARG *, __int16 *))load)(
                                                       ppv,
                                                       v26,
                                                       &v27);
                                          if ( Instance >= 0 )
                                          {
                                            if ( v27 || (Instance = DebugXmlParseError(ppv), Instance >= 0) )
                                              Instance = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, GUID *, struct IXMLDOMDocument **))ppv->lpVtbl->QueryInterface)(
                                                           ppv,
                                                           &IID_IXMLDOMDocument,
                                                           a2);
                                          }
                                        }
                                      }
                                    }
                                  }
                                }
                                else
                                {
                                  Instance = -2147024882;
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  VariantClear(&pvarg);
  if ( v4 )
  {
    v18 = GetProcessHeap();
    HeapFree(v18, 0, v4);
  }
  if ( ppv )
  {
    ((void (__fastcall *)(struct IXMLDOMDocument *))ppv->lpVtbl->Release)(ppv);
    ppv = 0;
  }
  if ( ppstm )
  {
    (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    ppstm = 0;
  }
  if ( v22 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    v22 = 0;
  }
  if ( v24 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    v24 = 0;
  }
  if ( bstrString )
    SysFreeString(bstrString);
  if ( Instance < 0 || *a3 == 200 )
    return (unsigned int)Instance;
  return v7;
}

```

## disassembly

```asm
0x140051164  push    rbp
0x140051166  push    rbx
0x140051167  push    rsi
0x140051168  push    rdi
0x140051169  push    r12
0x14005116b  push    r13
0x14005116d  push    r14
0x14005116f  push    r15
0x140051171  lea     rbp, [rsp-1Fh]
0x140051176  sub     rsp, 0A8h
0x14005117d  xor     edi, edi
0x14005117f  mov     r15, rcx
0x140051182  xorps   xmm0, xmm0
0x140051185  mov     [rbp+57h+arg_18], di
0x140051189  xor     eax, eax
0x14005118b  mov     [rbp+57h+var_90], rdi
0x14005118f  lea     rcx, [rbp+57h+pvarg]; pvarg
0x140051193  mov     [rbp+57h+var_80], rdi
0x140051197  mov     r14d, edi
0x14005119a  mov     [rbp+57h+var_98], rdi
0x14005119e  mov     [rbp+57h+ppstm], rdi
0x1400511a2  mov     r12, r8
0x1400511a5  mov     [rbp+57h+bstrString], rdi
0x1400511a9  mov     r13, rdx
0x1400511ac  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x1400511b0  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x1400511b4  call    cs:__imp_VariantInit
0x1400511bb  nop     dword ptr [rax+rax+00h]
0x1400511c0  lea     rax, [rbp+57h+var_98]
0x1400511c4  xor     edx, edx; pUnkOuter
0x1400511c6  lea     r9, IID_IXMLDOMDocument; riid
0x1400511cd  mov     [rsp+0E0h+ppv], rax; ppv
0x1400511d2  lea     r8d, [rdi+15h]; dwClsContext
0x1400511d6  lea     rcx, CLSID_FreeThreadedDOMDocument; rclsid
0x1400511dd  call    cs:__imp_CoCreateInstance
0x1400511e4  nop     dword ptr [rax+rax+00h]
0x1400511e9  lea     esi, [rdi+1]
0x1400511ec  mov     ebx, eax
0x1400511ee  test    eax, eax
0x1400511f0  js      loc_1400515C6
0x1400511f6  mov     rcx, [rbp+57h+var_98]
0x1400511fa  xor     edx, edx
0x1400511fc  mov     rax, [rcx]
0x1400511ff  mov     rax, [rax+1F8h]
0x140051206  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005120b  mov     ebx, eax
0x14005120d  test    eax, eax
0x14005120f  js      loc_1400515C6
0x140051215  lea     r9, [rbp+57h+ppstm]; struct IStream **
0x140051219  xor     ecx, ecx; hModule
0x14005121b  lea     rdx, aEnvelopeXml; "ENVELOPE.XML"
0x140051222  call    ?CreateStreamFromResource@@YAJPEAUHINSTANCE__@@PEBG1PEAPEAUIStream@@@Z; CreateStreamFromResource(HINSTANCE__ *,ushort const *,ushort const *,IStream * *)
0x140051227  mov     ebx, eax
0x140051229  test    eax, eax
0x14005122b  js      loc_1400515C6
0x140051231  mov     rcx, [rbp+57h+ppstm]
0x140051235  lea     r8, [rbp+57h+pvarg+8]
0x140051239  lea     rdx, IID_IUnknown
0x140051240  mov     rax, [rcx]
0x140051243  mov     rax, [rax]
0x140051246  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005124b  mov     ebx, eax
0x14005124d  test    eax, eax
0x14005124f  js      loc_1400515C6
0x140051255  mov     rcx, [rbp+57h+var_98]
0x140051259  lea     eax, [rdi+0Dh]
0x14005125c  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x140051261  lea     r8, [rbp+57h+arg_18]
0x140051265  mov     word ptr [rbp+57h+pvarg], ax
0x140051269  lea     rdx, [rbp+57h+var_60]
0x14005126d  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x140051271  mov     rax, [rcx]
0x140051274  movsd   [rbp+57h+var_50], xmm1
0x140051279  movaps  [rbp+57h+var_60], xmm0
0x14005127d  mov     rax, [rax+1D0h]
0x140051284  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140051289  mov     ebx, eax
0x14005128b  test    eax, eax
0x14005128d  js      loc_1400515C6
0x140051293  cmp     di, [rbp+57h+arg_18]
0x140051297  jnz     short loc_1400512AC
0x140051299  mov     rcx, [rbp+57h+var_98]; struct IXMLDOMDocument *
0x14005129d  call    ?DebugXmlParseError@@YAJPEAUIXMLDOMDocument@@@Z; DebugXmlParseError(IXMLDOMDocument *)
0x1400512a2  mov     ebx, eax
0x1400512a4  test    eax, eax
0x1400512a6  js      loc_1400515C6
0x1400512ac  mov     rcx, [rbp+57h+var_98]
0x1400512b0  lea     rdx, [rbp+57h+var_80]
0x1400512b4  mov     rax, [rcx]
0x1400512b7  mov     rax, [rax+168h]
0x1400512be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400512c3  mov     ebx, eax
0x1400512c5  test    eax, eax
0x1400512c7  js      loc_1400515C6
0x1400512cd  lea     rdx, aToken; "//token"
0x1400512d4  lea     rcx, [rbp+57h+bstrString]; unsigned __int16 **
0x1400512d8  call    ?AssignString@@YAJPEAPEAGPEBG@Z; AssignString(ushort * *,ushort const *)
0x1400512dd  mov     ebx, eax
0x1400512df  test    eax, eax
0x1400512e1  js      loc_1400515C6
0x1400512e7  mov     rcx, [rbp+57h+var_90]
0x1400512eb  test    rcx, rcx
0x1400512ee  jz      short loc_140051300
0x1400512f0  mov     rax, [rcx]
0x1400512f3  mov     rax, [rax+10h]
0x1400512f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400512fc  mov     [rbp+57h+var_90], rdi
0x140051300  mov     rcx, [rbp+57h+var_80]
0x140051304  lea     r8, [rbp+57h+var_90]
0x140051308  mov     rdx, [rbp+57h+bstrString]
0x14005130c  mov     rax, [rcx]
0x14005130f  mov     rax, [rax+128h]
0x140051316  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005131b  mov     ebx, eax
0x14005131d  test    eax, eax
0x14005131f  js      loc_1400515C6
0x140051325  cmp     eax, esi
0x140051327  jz      loc_1400515C6
0x14005132d  mov     rcx, [rbp+57h+var_90]
0x140051331  mov     rdx, [r15+10h]
0x140051335  mov     rax, [rcx]
0x140051338  mov     rax, [rax+0D8h]
0x14005133f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140051344  mov     ebx, eax
0x140051346  test    eax, eax
0x140051348  js      loc_1400515C6
0x14005134e  lea     rdx, aCulturename; "//cultureName"
0x140051355  lea     rcx, [rbp+57h+bstrString]; unsigned __int16 **
0x140051359  call    ?AssignString@@YAJPEAPEAGPEBG@Z; AssignString(ushort * *,ushort const *)
0x14005135e  mov     ebx, eax
0x140051360  test    eax, eax
0x140051362  js      loc_1400515C6
0x140051368  mov     rcx, [rbp+57h+var_90]
0x14005136c  test    rcx, rcx
0x14005136f  jz      short loc_140051381
0x140051371  mov     rax, [rcx]
0x140051374  mov     rax, [rax+10h]
0x140051378  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005137d  mov     [rbp+57h+var_90], rdi
0x140051381  mov     rcx, [rbp+57h+var_80]
0x140051385  lea     r8, [rbp+57h+var_90]
0x140051389  mov     rdx, [rbp+57h+bstrString]
0x14005138d  mov     rax, [rcx]
0x140051390  mov     rax, [rax+128h]
0x140051397  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005139c  mov     ebx, eax
0x14005139e  test    eax, eax
0x1400513a0  js      loc_1400515C6
0x1400513a6  cmp     eax, esi
0x1400513a8  jz      loc_1400515C6
0x1400513ae  lea     rcx, [rbp+57h+bstrString]; unsigned __int16 **
0x1400513b2  call    ?GetLanguage@@YAJPEAPEAG@Z; GetLanguage(ushort * *)
0x1400513b7  mov     ebx, eax
0x1400513b9  test    eax, eax
0x1400513bb  js      loc_1400515C6
0x1400513c1  mov     rcx, [rbp+57h+var_90]
0x1400513c5  mov     rdx, [rbp+57h+bstrString]
0x1400513c9  mov     rax, [rcx]
0x1400513cc  mov     rax, [rax+0D8h]
0x1400513d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400513d8  mov     ebx, eax
0x1400513da  test    eax, eax
0x1400513dc  js      loc_1400515C6
0x1400513e2  mov     rcx, [rbp+57h+bstrString]; bstrString
0x1400513e6  test    rcx, rcx
0x1400513e9  jz      short loc_1400513FB
0x1400513eb  call    cs:__imp_SysFreeString
0x1400513f2  nop     dword ptr [rax+rax+00h]
0x1400513f7  mov     [rbp+57h+bstrString], rdi
0x1400513fb  mov     rcx, [rbp+57h+var_98]
0x1400513ff  lea     rdx, [rbp+57h+bstrString]
0x140051403  mov     rax, [rcx]
0x140051406  mov     rax, [rax+110h]
0x14005140d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140051412  mov     ebx, eax
0x140051414  test    eax, eax
0x140051416  js      loc_1400515C6
0x14005141c  mov     rcx, [rbp+57h+bstrString]; pbstr
0x140051420  call    cs:__imp_SysStringLen
0x140051427  nop     dword ptr [rax+rax+00h]
0x14005142c  lea     edi, [rax+1]
0x14005142f  call    cs:__imp_GetProcessHeap
0x140051436  nop     dword ptr [rax+rax+00h]
0x14005143b  mov     r8d, edi; dwBytes
0x14005143e  xor     edx, edx; dwFlags
0x140051440  mov     rcx, rax; hHeap
0x140051443  call    cs:__imp_HeapAlloc
0x14005144a  nop     dword ptr [rax+rax+00h]
0x14005144f  mov     r14, rax
0x140051452  test    rax, rax
0x140051455  jnz     short loc_140051463
0x140051457  mov     ebx, 8007000Eh
0x14005145c  xor     edi, edi
0x14005145e  jmp     loc_1400515C6
0x140051463  mov     r8, [rbp+57h+bstrString]; lpWideCharStr
0x140051467  mov     r9d, edi; cchWideChar
0x14005146a  mov     [rsp+0E0h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x140051473  xor     edx, edx; dwFlags
0x140051475  mov     [rsp+0E0h+lpDefaultChar], 0; lpDefaultChar
0x14005147e  mov     ecx, 0FDE9h; CodePage
0x140051483  mov     [rsp+0E0h+cbMultiByte], edi; cbMultiByte
0x140051487  mov     [rsp+0E0h+ppv], r14; lpMultiByteStr
0x14005148c  call    cs:__imp_WideCharToMultiByte
0x140051493  nop     dword ptr [rax+rax+00h]
0x140051498  xor     edi, edi
0x14005149a  test    eax, eax
0x14005149c  jg      short loc_1400514C1
0x14005149e  call    cs:__imp_GetLastError
0x1400514a5  nop     dword ptr [rax+rax+00h]
0x1400514aa  mov     ebx, eax
0x1400514ac  test    eax, eax
0x1400514ae  jle     short loc_1400514B9
0x1400514b0  movzx   ebx, ax
0x1400514b3  or      ebx, 80070000h
0x1400514b9  test    ebx, ebx
0x1400514bb  js      loc_1400515C6
0x1400514c1  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1400514c5  call    cs:__imp_VariantClear
0x1400514cc  nop     dword ptr [rax+rax+00h]
0x1400514d1  mov     rcx, [rbp+57h+ppstm]
0x1400514d5  test    rcx, rcx
0x1400514d8  jz      short loc_1400514EA
0x1400514da  mov     rax, [rcx]
0x1400514dd  mov     rax, [rax+10h]
0x1400514e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400514e6  mov     [rbp+57h+ppstm], rdi
0x1400514ea  lea     r8, [rbp+57h+ppstm]; ppstm
0x1400514ee  mov     edx, esi; fDeleteOnRelease
0x1400514f0  xor     ecx, ecx; hGlobal
0x1400514f2  call    cs:__imp_CreateStreamOnHGlobal
0x1400514f9  nop     dword ptr [rax+rax+00h]
0x1400514fe  mov     ebx, eax
0x140051500  test    eax, eax
0x140051502  js      loc_1400515C6
0x140051508  mov     rax, [rbp+57h+ppstm]
0x14005150c  lea     r8, aSoapactionHttp; "SOAPAction: \"http://diagnostics.micros"...
0x140051513  mov     rcx, [r15+20h]; lpcwszUrl
0x140051517  lea     rdx, aPost; "POST"
0x14005151e  mov     qword ptr [rsp+0E0h+cbMultiByte], r12; unsigned int *
0x140051523  mov     r9, r14; char *
0x140051526  mov     [rsp+0E0h+ppv], rax; struct IStream *
0x14005152b  call    ?Request@@YAJPEAG00PEBDPEAUIStream@@PEAK@Z; Request(ushort *,ushort *,ushort *,char const *,IStream *,ulong *)
0x140051530  mov     ebx, eax
0x140051532  test    eax, eax
0x140051534  js      loc_1400515C6
0x14005153a  mov     rcx, [rbp+57h+ppstm]
0x14005153e  lea     r8, [rbp+57h+pvarg+8]
0x140051542  lea     rdx, IID_IUnknown
0x140051549  mov     rax, [rcx]
0x14005154c  mov     rax, [rax]
0x14005154f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140051554  mov     ebx, eax
0x140051556  test    eax, eax
0x140051558  js      short loc_1400515C6
0x14005155a  mov     rcx, [rbp+57h+var_98]
0x14005155e  lea     r8, [rbp+57h+arg_18]
0x140051562  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x140051567  lea     rdx, [rbp+57h+var_60]
0x14005156b  mov     eax, 0Dh
0x140051570  movsd   [rbp+57h+var_50], xmm1
0x140051575  mov     word ptr [rbp+57h+pvarg], ax
0x140051579  mov     rax, [rcx]
0x14005157c  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x140051580  mov     rax, [rax+1D0h]
0x140051587  movaps  [rbp+57h+var_60], xmm0
0x14005158b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140051590  mov     ebx, eax
0x140051592  test    eax, eax
0x140051594  js      short loc_1400515C6
0x140051596  cmp     di, [rbp+57h+arg_18]
0x14005159a  jnz     short loc_1400515AB
0x14005159c  mov     rcx, [rbp+57h+var_98]; struct IXMLDOMDocument *
0x1400515a0  call    ?DebugXmlParseError@@YAJPEAUIXMLDOMDocument@@@Z; DebugXmlParseError(IXMLDOMDocument *)
0x1400515a5  mov     ebx, eax
0x1400515a7  test    eax, eax
0x1400515a9  js      short loc_1400515C6
0x1400515ab  mov     rcx, [rbp+57h+var_98]
0x1400515af  lea     rdx, IID_IXMLDOMDocument
0x1400515b6  mov     r8, r13
0x1400515b9  mov     rax, [rcx]
0x1400515bc  mov     rax, [rax]
0x1400515bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400515c4  mov     ebx, eax
0x1400515c6  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1400515ca  call    cs:__imp_VariantClear
0x1400515d1  nop     dword ptr [rax+rax+00h]
0x1400515d6  test    r14, r14
0x1400515d9  jz      short loc_1400515FB
0x1400515db  call    cs:__imp_GetProcessHeap
0x1400515e2  nop     dword ptr [rax+rax+00h]
0x1400515e7  mov     r8, r14; lpMem
0x1400515ea  xor     edx, edx; dwFlags
0x1400515ec  mov     rcx, rax; hHeap
0x1400515ef  call    cs:__imp_HeapFree
0x1400515f6  nop     dword ptr [rax+rax+00h]
0x1400515fb  mov     rcx, [rbp+57h+var_98]
0x1400515ff  test    rcx, rcx
0x140051602  jz      short loc_140051614
0x140051604  mov     rax, [rcx]
0x140051607  mov     rax, [rax+10h]
  ... truncated ...
```
