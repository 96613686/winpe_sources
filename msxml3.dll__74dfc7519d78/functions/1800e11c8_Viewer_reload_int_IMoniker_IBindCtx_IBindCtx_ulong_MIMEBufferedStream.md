# Viewer::reload(int,IMoniker *,IBindCtx *,IBindCtx *,ulong,MIMEBufferedStream *)

- ea: `0x1800e11c8`
- end: `0x1800e18ca`
- name: `?reload@Viewer@@QEAAJHPEAUIMoniker@@PEAUIBindCtx@@1KPEAVMIMEBufferedStream@@@Z`
- size: `1794`
- prototype: `__int64 __usercall@<rax>(Viewer *__hidden this@<rcx>, int@<edx>, struct IMoniker *@<r8>, struct IBindCtx *@<r9>, struct IBindCtx *, unsigned int, struct MIMEBufferedStream *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800dfa60`

## callees

- `0x18001ad40`
- `0x18002505c`
- `0x18002d8d0`
- `0x18003cbc0`
- `0x1800de914`
- `0x1800e082c`
- `0x1800e0b84`
- `0x1800e0e74`
- `0x1800e0ff8`
- `0x1800e11c8`
- `0x1800e33c0`
- `0x1800e3ed8`
- `0x1800e4d50`
- `0x1800e51e0`
- `0x1800e7e68`
- `0x180107010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800e129e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800e129e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e12ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e12ad`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e18a6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e18a6`
- `OLEAUT32!__imp_VariantInit` at `0x1800e123d`
- `OLEAUT32!__imp_VariantInit` at `0x1800e123d`
- `OLEAUT32!__imp_VariantClear` at `0x1800e127f`
- `OLEAUT32!__imp_VariantClear` at `0x1800e127f`
- `urlmon!RegisterBindStatusCallback` at `0x1800e130a`
- `urlmon!RegisterBindStatusCallback` at `0x1800e1466`
- `urlmon!RegisterBindStatusCallback` at `0x1800e130a`
- `urlmon!RegisterBindStatusCallback` at `0x1800e1466`

## pseudocode

```c
__int64 __fastcall Viewer::reload(
        Viewer *this,
        int a2,
        struct IMoniker *a3,
        struct IBindCtx *a4,
        LPBC pBC,
        unsigned int a6,
        struct MIMEBufferedStream *a7)
{
  ViewerFactory *v7; // r15
  __int64 v9; // rcx
  struct MIMEBufferedStream *v11; // r12
  HANDLE EventW; // rax
  int LastError; // r14d
  CallbackWrapper *v14; // rdi
  CallbackWrapper *v15; // rsi
  CallbackWrapper *v16; // rax
  IBindStatusCallback *v17; // rax
  _QWORD *v18; // r14
  CallbackWrapper *v19; // rax
  __int64 v20; // rbx
  IBindCtx *v21; // rcx
  __int64 v22; // rcx
  struct IXMLDOMDocument2 **v23; // rbx
  __int64 v24; // rcx
  MimeviewerSite *v25; // rax
  struct IUnknown *v26; // rax
  struct IUnknown *v27; // r14
  BSTR v28; // r11
  int v29; // eax
  __int64 v30; // r8
  __int64 v31; // r11
  __int64 v32; // rax
  ViewerFactory *v33; // rax
  ViewerFactory *v34; // rax
  __int64 v35; // rax
  __int64 v36; // rbx
  int v37; // eax
  struct IXMLNodeFactory *v39; // [rsp+58h] [rbp-41h] BYREF
  IBindStatusCallback *ppBSCBPrev; // [rsp+60h] [rbp-39h] BYREF
  IBindStatusCallback *v41; // [rsp+68h] [rbp-31h] BYREF
  __int64 v42; // [rsp+70h] [rbp-29h] BYREF
  BSTR bstrString; // [rsp+78h] [rbp-21h]
  struct IUnknown *v44; // [rsp+80h] [rbp-19h]
  VARIANTARG pvarg; // [rsp+88h] [rbp-11h] BYREF
  __int64 *v46; // [rsp+E8h] [rbp+4Fh] BYREF
  int v47; // [rsp+F0h] [rbp+57h] BYREF
  struct IMoniker *v48; // [rsp+F8h] [rbp+5Fh]

  v48 = a3;
  v47 = a2;
  v7 = 0;
  v46 = 0;
  v9 = *((_QWORD *)this + 9);
  v39 = 0;
  ppBSCBPrev = 0;
  v41 = 0;
  v42 = 0;
  bstrString = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  if ( v9 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    *((_QWORD *)this + 9) = 0;
  }
  if ( *((_QWORD *)this + 14) )
  {
    VariantInit(&pvarg);
    if ( (*(unsigned int (__fastcall **)(_QWORD, const wchar_t *, VARIANTARG *, _QWORD))(**((_QWORD **)this + 14) + 24LL))(
           *((_QWORD *)this + 14),
           L"msoHTMLBody",
           &pvarg,
           0)
      || pvarg.vt != 8 )
    {
      VariantClear(&pvarg);
    }
    else
    {
      bstrString = pvarg.bstrVal;
      pvarg.vt = 0;
    }
  }
  v11 = a7;
  if ( !*((_QWORD *)this + 11) )
  {
    EventW = CreateEventW(0, 1, 1, 0);
    *((_QWORD *)this + 11) = EventW;
    if ( !EventW )
    {
      LastError = GetLastError();
      if ( LastError >= 0 )
      {
        v14 = 0;
        v15 = 0;
        goto LABEL_64;
      }
      v14 = 0;
      v15 = 0;
      goto LABEL_62;
    }
  }
  v15 = 0;
  v16 = (CallbackWrapper *)_MemAlloc(0x38u, 0);
  if ( !v16 )
  {
    v14 = 0;
    goto LABEL_61;
  }
  v17 = (IBindStatusCallback *)CallbackWrapper::CallbackWrapper(v16);
  v14 = (CallbackWrapper *)v17;
  if ( !v17 )
    goto LABEL_61;
  LastError = RegisterBindStatusCallback(a4, v17, &ppBSCBPrev, 0);
  if ( LastError < 0 )
    goto LABEL_62;
  CallbackWrapper::SetPreviousCallback(v14, ppBSCBPrev);
  if ( ppBSCBPrev )
  {
    ((void (__fastcall *)(IBindStatusCallback *))ppBSCBPrev->lpVtbl->Release)(ppBSCBPrev);
    ppBSCBPrev = 0;
  }
  Viewer::cleanupBinding(this);
  v18 = _MemAlloc(0x40u, 0);
  if ( v18 )
  {
    _xunknown::_xunknown((_xunknown *)(v18 + 1));
    v18[3] = &IID_IBinding;
    _InterlockedIncrement(&g_cComponents);
    *v18 = &CBinding::`vftable'{for `IBinding'};
    v18[1] = &CBinding::`vftable'{for `__unknown'};
    v18[4] = &CBinding::`vftable';
    v18[6] = 0;
    v18[5] = 0;
    *((_DWORD *)v18 + 14) = 0;
  }
  else
  {
    v18 = 0;
  }
  *((_QWORD *)this + 12) = v18;
  if ( !v18 )
    goto LABEL_61;
  *((_QWORD *)v11 + 7) = v14;
  (*(void (__fastcall **)(CallbackWrapper *))(*(_QWORD *)v14 + 8LL))(v14);
  *((_QWORD *)v11 + 8) = v18;
  (*(void (__fastcall **)(_QWORD *))(*v18 + 8LL))(v18);
  (*(void (__fastcall **)(CallbackWrapper *, _QWORD, _QWORD))(*(_QWORD *)v14 + 24LL))(v14, 0, *((_QWORD *)v11 + 8));
  v19 = (CallbackWrapper *)_MemAlloc(0x50u, 0);
  v15 = v19;
  if ( !v19 )
  {
    v15 = 0;
    goto LABEL_61;
  }
  v20 = *((_QWORD *)this + 12);
  CallbackWrapper::CallbackWrapper(v19);
  v21 = pBC;
  *(_QWORD *)v15 = &CallbackMonitor::`vftable'{for `IBindStatusCallback'};
  *((_QWORD *)v15 + 6) = 0;
  *((_QWORD *)v15 + 1) = &CallbackMonitor::`vftable'{for `__unknown'};
  *((_DWORD *)v15 + 14) = 0;
  *((_QWORD *)v15 + 4) = &CallbackMonitor::`vftable'{for `IHttpNegotiate'};
  *((_QWORD *)v15 + 8) = 0;
  *((_QWORD *)v15 + 5) = &CallbackMonitor::`vftable'{for `IInternetBindInfo'};
  *((_QWORD *)v15 + 9) = v20;
  LastError = RegisterBindStatusCallback(v21, (IBindStatusCallback *)v15, &v41, 0);
  if ( LastError < 0 )
    goto LABEL_62;
  CallbackWrapper::SetPreviousCallback(v15, (struct IBindStatusCallback *)v14);
  if ( v41 )
  {
    ((void (__fastcall *)(IBindStatusCallback *))v41->lpVtbl->Release)(v41);
    v41 = 0;
  }
  v22 = *((_QWORD *)this + 16);
  if ( v22 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    *((_QWORD *)this + 16) = 0;
  }
  LastError = ErrMsgCallback::New(*((struct IUnknown **)this + 7), (struct ErrMsgCallback **)this + 16);
  if ( LastError < 0 )
    goto LABEL_62;
  v23 = (struct IXMLDOMDocument2 **)((char *)this + 64);
  v24 = *((_QWORD *)this + 8);
  if ( v24 )
  {
    LastError = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v24 + 512LL))(v24);
    if ( LastError < 0 )
      goto LABEL_62;
    SetSiteForDocument(*v23, 0);
    if ( *v23 )
    {
      ((void (__fastcall *)(struct IXMLDOMDocument2 *))(*v23)->lpVtbl->Release)(*v23);
      *v23 = 0;
    }
  }
  LastError = CreateDOMDocument10(&IID_IXMLDOMDocument2, (void **)this + 8);
  if ( LastError < 0 )
  {
LABEL_62:
    (*(void (__fastcall **)(struct MIMEBufferedStream *, _QWORD))(*(_QWORD *)v11 + 64LL))(v11, 0);
    if ( !v7 )
      goto LABEL_64;
    goto LABEL_63;
  }
  SetDocumentSafety(*v23);
  v25 = (MimeviewerSite *)_MemAlloc(0x38u, 0);
  if ( !v25 || (v26 = (struct IUnknown *)MimeviewerSite::MimeviewerSite(v25), (v44 = v26) == 0) )
  {
LABEL_61:
    LastError = -2147024882;
    goto LABEL_62;
  }
  LastError = MimeviewerSite::init((MimeviewerSite *)v26, *((struct IUnknown **)this + 7));
  if ( LastError < 0 )
    goto LABEL_62;
  v27 = v44;
  SetSiteForDocument(*v23, v44);
  v28 = bstrString;
  *((_QWORD *)this + 9) = v27;
  if ( !v28 || !*v28 )
  {
    LastError = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, _QWORD))(*v23)->lpVtbl->put_validateOnParse)(
                  *v23,
                  0);
    if ( LastError < 0 )
      goto LABEL_62;
    LastError = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, __int64))(*v23)->lpVtbl->put_resolveExternals)(
                  *v23,
                  0xFFFFFFFFLL);
    if ( LastError < 0 )
      goto LABEL_62;
    LastError = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, GUID *, __int64 **))(*v23)->lpVtbl->QueryInterface)(
                  *v23,
                  &IID_IXMLParser,
                  &v46);
    if ( LastError < 0 )
      goto LABEL_62;
    LastError = (*(__int64 (__fastcall **)(__int64 *, struct IXMLNodeFactory **))(*v46 + 32))(v46, &v39);
    if ( LastError < 0 )
      goto LABEL_62;
    v33 = (ViewerFactory *)_MemAlloc(0x180u, 0);
    if ( v33 )
    {
      v34 = ViewerFactory::ViewerFactory(
              v33,
              v11,
              v39,
              *v23,
              v48,
              v15,
              *((void **)this + 11),
              *((struct IPropertyBag **)this + 14),
              *((struct ErrMsgCallback **)this + 16));
      v7 = v34;
      if ( v34 )
      {
        LastError = (*(__int64 (__fastcall **)(__int64 *, ViewerFactory *))(*v46 + 24))(v46, v34);
        if ( LastError < 0 )
          goto LABEL_81;
        if ( v39 )
        {
          (*(void (__fastcall **)(struct IXMLNodeFactory *))(*(_QWORD *)v39 + 16LL))(v39);
          v39 = 0;
        }
        v35 = *((_QWORD *)v11 + 8);
        if ( v35 )
        {
          *(_QWORD *)(v35 + 48) = v7;
          *(_QWORD *)(v35 + 40) = this;
        }
        LastError = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, GUID *, __int64 *))(*v23)->lpVtbl->QueryInterface)(
                      *v23,
                      &IID_IPersistMoniker,
                      &v42);
        if ( LastError < 0
          || (LastError = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IMoniker *, LPBC, unsigned int))(*(_QWORD *)v42 + 40LL))(
                            v42,
                            0,
                            v48,
                            pBC,
                            a6),
              LastError < 0) )
        {
LABEL_81:
          if ( !*((_BYTE *)v7 + 208) )
            ViewerFactory::reportError(v7, LastError, 0);
          LastError = 0;
        }
        else
        {
          v36 = *v46;
          v37 = (*(__int64 (__fastcall **)(__int64 *))(*v46 + 96))(v46);
          (*(void (__fastcall **)(__int64 *, _QWORD))(v36 + 224))(v46, v37 | 0x2000u);
        }
LABEL_63:
        (*(void (__fastcall **)(ViewerFactory *))(*(_QWORD *)v7 + 16LL))(v7);
        goto LABEL_64;
      }
    }
    goto LABEL_61;
  }
  v47 = 0;
  v29 = xstrlenw(v28, 0x7FFFFFFFu);
  LastError = (*(__int64 (__fastcall **)(struct MIMEBufferedStream *, __int64, _QWORD, int *))(v30 + 32))(
                v11,
                v31,
                (unsigned int)(2 * v29),
                &v47);
  if ( LastError < 0 )
    goto LABEL_62;
  v32 = *(_QWORD *)v11;
  *((_BYTE *)v11 + 41) = 1;
  LastError = (*(__int64 (__fastcall **)(struct MIMEBufferedStream *, _QWORD))(v32 + 64))(v11, 0);
  if ( LastError < 0 )
    goto LABEL_62;
LABEL_64:
  if ( v39 )
  {
    (*(void (__fastcall **)(struct IXMLNodeFactory *))(*(_QWORD *)v39 + 16LL))(v39);
    v39 = 0;
  }
  if ( v46 )
  {
    (*(void (__fastcall **)(__int64 *))(*v46 + 16))(v46);
    v46 = 0;
  }
  if ( v41 )
  {
    ((void (__fastcall *)(IBindStatusCallback *))v41->lpVtbl->Release)(v41);
    v41 = 0;
  }
  if ( ppBSCBPrev )
  {
    ((void (__fastcall *)(IBindStatusCallback *))ppBSCBPrev->lpVtbl->Release)(ppBSCBPrev);
    ppBSCBPrev = 0;
  }
  if ( v42 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    v42 = 0;
  }
  if ( v14 )
    (*(void (__fastcall **)(CallbackWrapper *))(*(_QWORD *)v14 + 16LL))(v14);
  if ( v15 )
    (*(void (__fastcall **)(CallbackWrapper *))(*(_QWORD *)v15 + 16LL))(v15);
  SysFreeString(bstrString);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800e11c8  mov     rax, rsp
0x1800e11cb  mov     [rax+20h], rbx
0x1800e11cf  mov     [rax+18h], r8
0x1800e11d3  mov     [rax+10h], edx
0x1800e11d6  push    rbp
0x1800e11d7  push    rsi
0x1800e11d8  push    rdi
0x1800e11d9  push    r12
0x1800e11db  push    r13
0x1800e11dd  push    r14
0x1800e11df  push    r15
0x1800e11e1  lea     rbp, [rax-47h]
0x1800e11e5  sub     rsp, 0A0h
0x1800e11ec  xor     r15d, r15d
0x1800e11ef  xor     eax, eax
0x1800e11f1  mov     r13, rcx
0x1800e11f4  mov     [rbp+3Fh+arg_0], r15
0x1800e11f8  mov     rcx, [rcx+48h]
0x1800e11fc  xorps   xmm0, xmm0
0x1800e11ff  mov     [rbp+3Fh+var_80], r15
0x1800e1203  mov     rbx, r9
0x1800e1206  mov     [rbp+3Fh+ppBSCBPrev], r15
0x1800e120a  mov     [rbp+3Fh+var_70], r15
0x1800e120e  mov     [rbp+3Fh+var_68], r15
0x1800e1212  mov     qword ptr [rbp+3Fh+pvarg+10h], rax
0x1800e1216  mov     [rbp+3Fh+bstrString], r15
0x1800e121a  movups  xmmword ptr [rbp+3Fh+pvarg], xmm0
0x1800e121e  test    rcx, rcx
0x1800e1221  jz      short loc_1800E1233
0x1800e1223  mov     rax, [rcx]
0x1800e1226  mov     rax, [rax+10h]
0x1800e122a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e122f  mov     [r13+48h], r15
0x1800e1233  cmp     [r13+70h], r15
0x1800e1237  jz      short loc_1800E1285
0x1800e1239  lea     rcx, [rbp+3Fh+pvarg]; pvarg
0x1800e123d  call    cs:__imp_VariantInit
0x1800e1243  mov     rcx, [r13+70h]
0x1800e1247  lea     r8, [rbp+3Fh+pvarg]
0x1800e124b  xor     r9d, r9d
0x1800e124e  lea     rdx, aMsohtmlbody; "msoHTMLBody"
0x1800e1255  mov     rax, [rcx]
0x1800e1258  mov     rax, [rax+18h]
0x1800e125c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1261  test    eax, eax
0x1800e1263  jnz     short loc_1800E127B
0x1800e1265  cmp     word ptr [rbp+3Fh+pvarg], 8
0x1800e126a  jnz     short loc_1800E127B
0x1800e126c  mov     rax, qword ptr [rbp+3Fh+pvarg+8]
0x1800e1270  mov     [rbp+3Fh+bstrString], rax
0x1800e1274  mov     word ptr [rbp+3Fh+pvarg], r15w
0x1800e1279  jmp     short loc_1800E1285
0x1800e127b  lea     rcx, [rbp+3Fh+pvarg]; pvarg
0x1800e127f  call    cs:__imp_VariantClear
0x1800e1285  mov     eax, 1
0x1800e128a  mov     r12, [rbp+3Fh+arg_30]
0x1800e128e  cmp     [r13+58h], r15
0x1800e1292  jnz     short loc_1800E12D0
0x1800e1294  xor     r9d, r9d; lpName
0x1800e1297  mov     r8d, eax; bInitialState
0x1800e129a  mov     edx, eax; bManualReset
0x1800e129c  xor     ecx, ecx; lpEventAttributes
0x1800e129e  call    cs:__imp_CreateEventW
0x1800e12a4  mov     [r13+58h], rax
0x1800e12a8  test    rax, rax
0x1800e12ab  jnz     short loc_1800E12D0
0x1800e12ad  call    cs:__imp_GetLastError
0x1800e12b3  mov     r14d, eax
0x1800e12b6  test    eax, eax
0x1800e12b8  jns     short loc_1800E12C5
0x1800e12ba  xor     eax, eax
0x1800e12bc  mov     edi, eax
0x1800e12be  mov     esi, eax
0x1800e12c0  jmp     loc_1800E17D4
0x1800e12c5  mov     rdi, r15
0x1800e12c8  mov     rsi, r15
0x1800e12cb  jmp     loc_1800E17FD
0x1800e12d0  xor     edx, edx; unsigned int
0x1800e12d2  xor     r14d, r14d
0x1800e12d5  mov     esi, r14d
0x1800e12d8  lea     ecx, [rdx+38h]; unsigned __int64
0x1800e12db  call    ?_MemAlloc@@YAPEAX_KK@Z; _MemAlloc(unsigned __int64,ulong)
0x1800e12e0  test    rax, rax
0x1800e12e3  jz      loc_1800E17CB
0x1800e12e9  mov     rcx, rax; this
0x1800e12ec  call    ??0CallbackWrapper@@QEAA@XZ; CallbackWrapper::CallbackWrapper(void)
0x1800e12f1  mov     rdi, rax
0x1800e12f4  test    rax, rax
0x1800e12f7  jz      loc_1800E17CE
0x1800e12fd  xor     r9d, r9d; dwReserved
0x1800e1300  lea     r8, [rbp+3Fh+ppBSCBPrev]; ppBSCBPrev
0x1800e1304  mov     rdx, rax; pBSCb
0x1800e1307  mov     rcx, rbx; pBC
0x1800e130a  call    cs:__imp_RegisterBindStatusCallback
0x1800e1310  mov     r14d, eax
0x1800e1313  test    eax, eax
0x1800e1315  js      loc_1800E17D4
0x1800e131b  mov     rdx, [rbp+3Fh+ppBSCBPrev]; struct IBindStatusCallback *
0x1800e131f  mov     rcx, rdi; this
0x1800e1322  call    ?SetPreviousCallback@CallbackWrapper@@QEAAXPEAUIBindStatusCallback@@@Z; CallbackWrapper::SetPreviousCallback(IBindStatusCallback *)
0x1800e1327  mov     rcx, [rbp+3Fh+ppBSCBPrev]
0x1800e132b  xor     r14d, r14d
0x1800e132e  test    rcx, rcx
0x1800e1331  jz      short loc_1800E1343
0x1800e1333  mov     rax, [rcx]
0x1800e1336  mov     rax, [rax+10h]
0x1800e133a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e133f  mov     [rbp+3Fh+ppBSCBPrev], r14
0x1800e1343  mov     rcx, r13; this
0x1800e1346  call    ?cleanupBinding@Viewer@@AEAAXXZ; Viewer::cleanupBinding(void)
0x1800e134b  xor     edx, edx; unsigned int
0x1800e134d  lea     ecx, [rdx+40h]; unsigned __int64
0x1800e1350  call    ?_MemAlloc@@YAPEAX_KK@Z; _MemAlloc(unsigned __int64,ulong)
0x1800e1355  mov     r14, rax
0x1800e1358  xor     eax, eax
0x1800e135a  test    r14, r14
0x1800e135d  jz      short loc_1800E13AA
0x1800e135f  lea     rcx, [r14+8]; this
0x1800e1363  call    ??0_xunknown@@QEAA@XZ; _xunknown::_xunknown(void)
0x1800e1368  lea     rax, IID_IBinding
0x1800e136f  mov     [r14+18h], rax
0x1800e1373  lock inc cs:?g_cComponents@@3JC; long volatile g_cComponents
0x1800e137a  lea     rax, ??_7CBinding@@6BIBinding@@@; const CBinding::`vftable'{for `IBinding'}
0x1800e1381  mov     [r14], rax
0x1800e1384  lea     rax, ??_7CBinding@@6B__unknown@@@; const CBinding::`vftable'{for `__unknown'}
0x1800e138b  mov     [r14+8], rax
0x1800e138f  lea     rax, ??_7CBinding@@6B@; const CBinding::`vftable'
0x1800e1396  mov     [r14+20h], rax
0x1800e139a  xor     eax, eax
0x1800e139c  mov     [r14+30h], rax
0x1800e13a0  mov     [r14+28h], rax
0x1800e13a4  mov     [r14+38h], eax
0x1800e13a8  jmp     short loc_1800E13AD
0x1800e13aa  mov     r14, rax
0x1800e13ad  mov     [r13+60h], r14
0x1800e13b1  test    r14, r14
0x1800e13b4  jz      loc_1800E17CE
0x1800e13ba  mov     [r12+38h], rdi
0x1800e13bf  mov     rcx, rdi
0x1800e13c2  mov     rax, [rdi]
0x1800e13c5  mov     rax, [rax+8]
0x1800e13c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e13ce  mov     [r12+40h], r14
0x1800e13d3  mov     rcx, r14
0x1800e13d6  mov     rax, [r14]
0x1800e13d9  mov     rax, [rax+8]
0x1800e13dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e13e2  mov     rax, [rdi]
0x1800e13e5  xor     edx, edx
0x1800e13e7  mov     r8, [r12+40h]
0x1800e13ec  mov     rcx, rdi
0x1800e13ef  mov     rax, [rax+18h]
0x1800e13f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e13f8  xor     edx, edx; unsigned int
0x1800e13fa  lea     ecx, [rdx+50h]; unsigned __int64
0x1800e13fd  call    ?_MemAlloc@@YAPEAX_KK@Z; _MemAlloc(unsigned __int64,ulong)
0x1800e1402  xor     r14d, r14d
0x1800e1405  mov     rsi, rax
0x1800e1408  test    rax, rax
0x1800e140b  jz      loc_1800E17C7
0x1800e1411  mov     rbx, [r13+60h]
0x1800e1415  mov     rcx, rax; this
0x1800e1418  call    ??0CallbackWrapper@@QEAA@XZ; CallbackWrapper::CallbackWrapper(void)
0x1800e141d  mov     rcx, [rbp+3Fh+pBC]; pBC
0x1800e1421  lea     rax, ??_7CallbackMonitor@@6BIBindStatusCallback@@@; const CallbackMonitor::`vftable'{for `IBindStatusCallback'}
0x1800e1428  mov     [rsi], rax
0x1800e142b  lea     r8, [rbp+3Fh+var_70]; ppBSCBPrev
0x1800e142f  lea     rax, ??_7CallbackMonitor@@6B__unknown@@@; const CallbackMonitor::`vftable'{for `__unknown'}
0x1800e1436  mov     [rsi+30h], r14
0x1800e143a  mov     [rsi+8], rax
0x1800e143e  xor     r9d, r9d; dwReserved
0x1800e1441  lea     rax, ??_7CallbackMonitor@@6BIHttpNegotiate@@@; const CallbackMonitor::`vftable'{for `IHttpNegotiate'}
0x1800e1448  mov     [rsi+38h], r14d
0x1800e144c  mov     [rsi+20h], rax
0x1800e1450  mov     rdx, rsi; pBSCb
0x1800e1453  lea     rax, ??_7CallbackMonitor@@6BIInternetBindInfo@@@; const CallbackMonitor::`vftable'{for `IInternetBindInfo'}
0x1800e145a  mov     [rsi+40h], r14
0x1800e145e  mov     [rsi+28h], rax
0x1800e1462  mov     [rsi+48h], rbx
0x1800e1466  call    cs:__imp_RegisterBindStatusCallback
0x1800e146c  mov     r14d, eax
0x1800e146f  test    eax, eax
0x1800e1471  js      loc_1800E17D4
0x1800e1477  mov     rdx, rdi; struct IBindStatusCallback *
0x1800e147a  mov     rcx, rsi; this
0x1800e147d  call    ?SetPreviousCallback@CallbackWrapper@@QEAAXPEAUIBindStatusCallback@@@Z; CallbackWrapper::SetPreviousCallback(IBindStatusCallback *)
0x1800e1482  mov     rcx, [rbp+3Fh+var_70]
0x1800e1486  xor     r14d, r14d
0x1800e1489  test    rcx, rcx
0x1800e148c  jz      short loc_1800E149E
0x1800e148e  mov     rax, [rcx]
0x1800e1491  mov     rax, [rax+10h]
0x1800e1495  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e149a  mov     [rbp+3Fh+var_70], r14
0x1800e149e  lea     rbx, [r13+80h]
0x1800e14a5  mov     rcx, [rbx]
0x1800e14a8  test    rcx, rcx
0x1800e14ab  jz      short loc_1800E14BC
0x1800e14ad  mov     rax, [rcx]
0x1800e14b0  mov     rax, [rax+10h]
0x1800e14b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e14b9  mov     [rbx], r14
0x1800e14bc  mov     rcx, [r13+38h]; struct IUnknown *
0x1800e14c0  mov     rdx, rbx; struct ErrMsgCallback **
0x1800e14c3  call    ?New@ErrMsgCallback@@SAJPEAUIUnknown@@PEAPEAV1@@Z; ErrMsgCallback::New(IUnknown *,ErrMsgCallback * *)
0x1800e14c8  mov     r14d, eax
0x1800e14cb  test    eax, eax
0x1800e14cd  js      loc_1800E17D4
0x1800e14d3  lea     rbx, [r13+40h]
0x1800e14d7  mov     rcx, [rbx]
0x1800e14da  test    rcx, rcx
0x1800e14dd  jz      short loc_1800E151D
0x1800e14df  mov     rax, [rcx]
0x1800e14e2  mov     rax, [rax+200h]
0x1800e14e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e14ee  mov     r14d, eax
0x1800e14f1  test    eax, eax
0x1800e14f3  js      loc_1800E17D4
0x1800e14f9  mov     rcx, [rbx]; struct IXMLDOMDocument2 *
0x1800e14fc  xor     edx, edx; struct IUnknown *
0x1800e14fe  call    ?SetSiteForDocument@@YAXPEAUIXMLDOMDocument2@@PEAUIUnknown@@@Z; SetSiteForDocument(IXMLDOMDocument2 *,IUnknown *)
0x1800e1503  mov     rcx, [rbx]
0x1800e1506  xor     r14d, r14d
0x1800e1509  test    rcx, rcx
0x1800e150c  jz      short loc_1800E151D
0x1800e150e  mov     rax, [rcx]
0x1800e1511  mov     rax, [rax+10h]
0x1800e1515  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e151a  mov     [rbx], r14
0x1800e151d  mov     rdx, rbx; void **
0x1800e1520  lea     rcx, IID_IXMLDOMDocument2; struct _GUID *
0x1800e1527  call    ?CreateDOMDocument10@@YAJAEBU_GUID@@PEAPEAX@Z; CreateDOMDocument10(_GUID const &,void * *)
0x1800e152c  mov     r14d, eax
0x1800e152f  test    eax, eax
0x1800e1531  js      loc_1800E17D4
0x1800e1537  mov     rcx, [rbx]; struct IXMLDOMDocument2 *
0x1800e153a  call    ?SetDocumentSafety@@YAXPEAUIXMLDOMDocument2@@@Z; SetDocumentSafety(IXMLDOMDocument2 *)
0x1800e153f  xor     edx, edx; unsigned int
0x1800e1541  lea     ecx, [rdx+38h]; unsigned __int64
0x1800e1544  call    ?_MemAlloc@@YAPEAX_KK@Z; _MemAlloc(unsigned __int64,ulong)
0x1800e1549  test    rax, rax
0x1800e154c  jz      loc_1800E17CE
0x1800e1552  mov     rcx, rax; this
0x1800e1555  call    ??0MimeviewerSite@@QEAA@XZ; MimeviewerSite::MimeviewerSite(void)
0x1800e155a  mov     [rbp+3Fh+var_58], rax
0x1800e155e  test    rax, rax
0x1800e1561  jz      loc_1800E17CE
0x1800e1567  mov     rdx, [r13+38h]; struct IUnknown *
0x1800e156b  mov     rcx, rax; this
0x1800e156e  call    ?init@MimeviewerSite@@QEAAJPEAUIUnknown@@@Z; MimeviewerSite::init(IUnknown *)
0x1800e1573  mov     r14d, eax
0x1800e1576  test    eax, eax
0x1800e1578  js      loc_1800E17D4
0x1800e157e  mov     r14, [rbp+3Fh+var_58]
0x1800e1582  mov     rcx, [rbx]; struct IXMLDOMDocument2 *
0x1800e1585  mov     rdx, r14; struct IUnknown *
0x1800e1588  call    ?SetSiteForDocument@@YAXPEAUIXMLDOMDocument2@@PEAUIUnknown@@@Z; SetSiteForDocument(IXMLDOMDocument2 *,IUnknown *)
0x1800e158d  mov     r11, [rbp+3Fh+bstrString]
0x1800e1591  xor     eax, eax
0x1800e1593  mov     [r13+48h], r14
0x1800e1597  test    r11, r11
0x1800e159a  jz      short loc_1800E1604
0x1800e159c  cmp     [r11], ax
0x1800e15a0  jz      short loc_1800E1604
0x1800e15a2  mov     r8, [r12]
0x1800e15a6  mov     edx, 7FFFFFFFh; unsigned __int64
0x1800e15ab  mov     rcx, r11; unsigned __int16 *
0x1800e15ae  mov     [rbp+3Fh+arg_8], eax
0x1800e15b1  call    ?xstrlenw@@YAHPEBG_K@Z; xstrlenw(ushort const *,unsigned __int64)
0x1800e15b6  mov     r10, [r8+20h]
0x1800e15ba  lea     r9, [rbp+3Fh+arg_8]
0x1800e15be  add     eax, eax
0x1800e15c0  mov     rdx, r11
0x1800e15c3  mov     r8d, eax
0x1800e15c6  mov     rcx, r12
0x1800e15c9  mov     rax, r10
0x1800e15cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e15d1  mov     r14d, eax
0x1800e15d4  test    eax, eax
0x1800e15d6  js      loc_1800E17D4
0x1800e15dc  mov     rax, [r12]
0x1800e15e0  xor     edx, edx
0x1800e15e2  mov     rcx, r12
0x1800e15e5  mov     byte ptr [r12+29h], 1
0x1800e15eb  mov     rax, [rax+40h]
0x1800e15ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e15f4  mov     r14d, eax
0x1800e15f7  test    eax, eax
0x1800e15f9  jns     loc_1800E17FD
0x1800e15ff  jmp     loc_1800E17D4
0x1800e1604  mov     rcx, [rbx]
0x1800e1607  xor     edx, edx
0x1800e1609  mov     rax, [rcx]
0x1800e160c  mov     rax, [rax+220h]
0x1800e1613  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1618  mov     r14d, eax
0x1800e161b  test    eax, eax
0x1800e161d  js      loc_1800E17D4
0x1800e1623  mov     rcx, [rbx]
0x1800e1626  or      edx, 0FFFFFFFFh
  ... truncated ...
```
