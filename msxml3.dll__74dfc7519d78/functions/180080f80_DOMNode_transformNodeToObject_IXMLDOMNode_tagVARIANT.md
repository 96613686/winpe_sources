# DOMNode::transformNodeToObject(IXMLDOMNode *,tagVARIANT)

- ea: `0x180080f80`
- end: `0x180081405`
- name: `?transformNodeToObject@DOMNode@@UEAAJPEAUIXMLDOMNode@@UtagVARIANT@@@Z`
- size: `1157`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *this, struct IXMLDOMNode *, struct tagVARIANT *__struct_ptr)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config`

## callers

- `0x180088b30`

## callees

- `0x18002378c`
- `0x1800238d8`
- `0x180026c28`
- `0x180036da8`
- `0x18003e230`
- `0x18004a8fc`
- `0x18004fa6c`
- `0x18005f9b8`
- `0x180064034`
- `0x180078194`
- `0x18007c780`
- `0x180080f80`
- `0x180089228`
- `0x180089318`
- `0x180107010`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x18008128d`
- `msvcrt!_resetstkoflw` at `0x18008128d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800812e0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800812e0`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18008127b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18008130c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18008127b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18008130c`

## pseudocode

```c
__int64 __fastcall DOMNode::transformNodeToObject(
        struct IXMLDOMNode *this,
        struct IXMLDOMNode *a2,
        struct tagVARIANT *a3)
{
  struct TLSDATA *v6; // rbx
  char v8; // r12
  struct IUnknown *Unknown; // rax
  struct IUnknown *v10; // r14
  int v11; // esi
  struct Document *ObjectFromIUnk; // r15
  int v13; // eax
  struct ISequentialStream *v14; // [rsp+38h] [rbp-80h] BYREF
  struct IResponse *v15; // [rsp+40h] [rbp-78h] BYREF
  struct IUnknown *v16; // [rsp+48h] [rbp-70h] BYREF
  __int64 v17; // [rsp+50h] [rbp-68h] BYREF
  struct CachingStream *v18[2]; // [rsp+58h] [rbp-60h] BYREF
  struct TLSDATA *v19; // [rsp+68h] [rbp-50h] BYREF
  _BYTE v20[32]; // [rsp+70h] [rbp-48h] BYREF
  struct IStream *v22; // [rsp+D8h] [rbp+20h] BYREF

  EnsureTls::EnsureTls((EnsureTls *)&v19);
  v6 = v19;
  if ( !v19 )
  {
    ((void (__fastcall *)(_QWORD))g_pfnExit)(0);
    return 2147500037LL;
  }
  OMReadLock::OMReadLock((OMReadLock *)v20, v19, (struct DOMNode *)this);
  v22 = 0;
  v14 = 0;
  v15 = 0;
  v17 = 0;
  v16 = 0;
  if ( !a2 )
  {
    OMReadLock::~OMReadLock((OMReadLock *)v20);
    ((void (__fastcall *)(struct TLSDATA *))g_pfnExit)(v6);
    return 2147942487LL;
  }
  v8 = 0;
  Unknown = Variant::getUnknown(a3, 0);
  v10 = Unknown;
  if ( Unknown )
  {
    if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))Unknown->lpVtbl->QueryInterface)(
           Unknown,
           &IID_IHTMLObjectElement,
           &v17) >= 0 )
    {
      if ( v17 )
      {
        v11 = (*(__int64 (__fastcall **)(__int64, struct IUnknown **))(*(_QWORD *)v17 + 56LL))(v17, &v16);
        if ( v11 < 0 )
          goto LABEL_33;
        v10 = v16;
        if ( !v16 )
          goto LABEL_33;
      }
    }
    ObjectFromIUnk = (struct Document *)Object::getObjectFromIUnk(v10, &IID_Document);
    if ( ObjectFromIUnk )
    {
      if ( ObjectFromIUnk == (struct Document *)(*((__int64 (__fastcall **)(struct IXMLDOMNodeVtbl *))this[7].lpVtbl->QueryInterface
                                                 + 50))(this[7].lpVtbl) )
      {
        v18[0] = 0;
        v11 = CachingStream::New(v18);
        v22 = v18[0];
        if ( v11 < 0 )
          goto LABEL_33;
        v8 = 1;
      }
      else
      {
        v11 = DocStream::New(ObjectFromIUnk, &v22);
        if ( v11 < 0 )
          goto LABEL_33;
      }
    }
    else if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IStream **))v10->lpVtbl->QueryInterface)(
                v10,
                &IID_IStream,
                &v22) < 0 )
    {
      if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct ISequentialStream **))v10->lpVtbl->QueryInterface)(
             v10,
             &IID_ISequentialStream,
             &v14) < 0 )
      {
        if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IResponse **))v10->lpVtbl->QueryInterface)(
               v10,
               &IID_IResponse,
               &v15) < 0 )
        {
          v11 = -2147024809;
          goto LABEL_33;
        }
        v11 = DocStream::New(v15, &v22);
        if ( v11 < 0 )
          goto LABEL_33;
      }
      else
      {
        v11 = StreamWrapper::New(v14, &v22);
        if ( v11 < 0 )
          goto LABEL_33;
      }
    }
    TransformNode(a2, this, v22, 0);
    if ( v8 )
    {
      v18[1] = 0;
      (*(void (__fastcall **)(struct IStream *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v22 + 40LL))(v22, 0, 0, 0);
      ((void (__fastcall *)(struct Document *, struct IStream *))ObjectFromIUnk[11].lpVtbl->GetIDsOfNames)(
        &ObjectFromIUnk[11],
        v22);
    }
    v13 = (*(__int64 (__fastcall **)(struct IStream *, _QWORD))(*(_QWORD *)v22 + 64LL))(v22, 0);
    v11 = v13;
    if ( v13 == -2147287039 || v13 == -2147467263 )
    {
      v11 = 0;
    }
    else if ( v13 < 0 )
    {
      Exception::throwHR(v13);
    }
    goto LABEL_33;
  }
  v11 = -2147024809;
LABEL_33:
  if ( v22 )
  {
    (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v22 + 16LL))(v22);
    v22 = 0;
  }
  if ( v14 )
  {
    ((void (__fastcall *)(struct ISequentialStream *))v14->lpVtbl->Release)(v14);
    v14 = 0;
  }
  if ( v15 )
  {
    ((void (__fastcall *)(struct IResponse *))v15->lpVtbl->Release)(v15);
    v15 = 0;
  }
  if ( v16 )
  {
    ((void (__fastcall *)(struct IUnknown *))v16->lpVtbl->Release)(v16);
    v16 = 0;
  }
  if ( v17 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    v17 = 0;
  }
  OMReadLock::~OMReadLock((OMReadLock *)v20);
  ((void (__fastcall *)(struct TLSDATA *))g_pfnExit)(v6);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180080f80  mov     rax, rsp
0x180080f83  mov     [rax+8], rbx
0x180080f87  mov     [rax+18h], rsi
0x180080f8b  mov     [rax+10h], rdx
0x180080f8f  push    rdi
0x180080f90  push    r12
0x180080f92  push    r13
0x180080f94  push    r14
0x180080f96  push    r15
0x180080f98  sub     rsp, 90h
0x180080f9f  mov     rsi, r8
0x180080fa2  mov     r14, rdx
0x180080fa5  mov     r13, rcx
0x180080fa8  lea     rcx, [rax-50h]; this
0x180080fac  call    ??0EnsureTls@@QEAA@XZ; EnsureTls::EnsureTls(void)
0x180080fb1  mov     rbx, [rsp+0B8h+var_50]
0x180080fb6  xor     edi, edi
0x180080fb8  test    rbx, rbx
0x180080fbb  jnz     short loc_180080FD5
0x180080fbd  xor     ecx, ecx
0x180080fbf  mov     rax, cs:?g_pfnExit@@3P6AXPEAUTLSDATA@@@ZEA; void (*g_pfnExit)(TLSDATA *)
0x180080fc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080fcb  mov     eax, 80004005h
0x180080fd0  jmp     loc_1800813E8
0x180080fd5  mov     r8, r13; struct DOMNode *
0x180080fd8  mov     rdx, rbx; struct TLSDATA *
0x180080fdb  lea     rcx, [rsp+0B8h+var_48]; this
0x180080fe0  call    ??0OMReadLock@@QEAA@PEAUTLSDATA@@PEAVDOMNode@@@Z; OMReadLock::OMReadLock(TLSDATA *,DOMNode *)
0x180080fe5  mov     [rsp+0B8h+arg_18], rdi
0x180080fed  mov     [rsp+0B8h+var_80], rdi
0x180080ff2  mov     [rsp+0B8h+var_78], rdi
0x180080ff7  mov     [rsp+0B8h+var_68], rdi
0x180080ffc  mov     [rsp+0B8h+var_70], rdi
0x180081001  test    r14, r14
0x180081004  jnz     short loc_180081029
0x180081006  lea     rcx, [rsp+0B8h+var_48]; this
0x18008100b  call    ??1OMReadLock@@QEAA@XZ; OMReadLock::~OMReadLock(void)
0x180081010  mov     rcx, rbx
0x180081013  mov     rax, cs:?g_pfnExit@@3P6AXPEAUTLSDATA@@@ZEA; void (*g_pfnExit)(TLSDATA *)
0x18008101a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008101f  mov     eax, 80070057h
0x180081024  jmp     loc_1800813E8
0x180081029  mov     r12b, dil
0x18008102c  xor     edx, edx; bool
0x18008102e  mov     rcx, rsi; struct tagVARIANT *
0x180081031  call    ?getUnknown@Variant@@SAPEAUIUnknown@@PEAUtagVARIANT@@_N@Z; Variant::getUnknown(tagVARIANT *,bool)
0x180081036  mov     r14, rax
0x180081039  test    rax, rax
0x18008103c  jnz     short loc_180081048
0x18008103e  mov     esi, 80070057h
0x180081043  jmp     loc_18008133D
0x180081048  mov     rax, [rax]
0x18008104b  lea     r8, [rsp+0B8h+var_68]
0x180081050  lea     rdx, IID_IHTMLObjectElement
0x180081057  mov     rcx, r14
0x18008105a  mov     rax, [rax]
0x18008105d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081062  mov     [rsp+0B8h+var_88], eax
0x180081066  test    eax, eax
0x180081068  js      short loc_18008109E
0x18008106a  mov     rcx, [rsp+0B8h+var_68]
0x18008106f  test    rcx, rcx
0x180081072  jz      short loc_18008109E
0x180081074  mov     rax, [rcx]
0x180081077  lea     rdx, [rsp+0B8h+var_70]
0x18008107c  mov     rax, [rax+38h]
0x180081080  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081085  mov     esi, eax
0x180081087  mov     [rsp+0B8h+var_88], eax
0x18008108b  test    eax, eax
0x18008108d  js      short loc_180081099
0x18008108f  mov     r14, [rsp+0B8h+var_70]
0x180081094  test    r14, r14
0x180081097  jnz     short loc_18008109E
0x180081099  jmp     loc_18008133D
0x18008109e  lea     rdx, ?IID_Document@@3U_GUID@@B; struct _GUID *
0x1800810a5  mov     rcx, r14; struct IUnknown *
0x1800810a8  call    ?getObjectFromIUnk@Object@@SAPEAV1@PEAUIUnknown@@AEBU_GUID@@@Z; Object::getObjectFromIUnk(IUnknown *,_GUID const &)
0x1800810ad  mov     r15, rax
0x1800810b0  test    rax, rax
0x1800810b3  jz      short loc_180081122
0x1800810b5  mov     rcx, [r13+38h]
0x1800810b9  mov     rdx, [rcx]
0x1800810bc  mov     rax, [rdx+190h]
0x1800810c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800810c8  cmp     r15, rax
0x1800810cb  jz      short loc_1800810F0
0x1800810cd  lea     rdx, [rsp+0B8h+arg_18]; struct IStream **
0x1800810d5  mov     rcx, r15; struct Document *
0x1800810d8  call    ?New@DocStream@@SAJPEAVDocument@@PEAPEAUIStream@@@Z; DocStream::New(Document *,IStream * *)
0x1800810dd  mov     esi, eax
0x1800810df  mov     [rsp+0B8h+var_88], eax
0x1800810e3  test    eax, eax
0x1800810e5  jns     loc_1800811D3
0x1800810eb  jmp     loc_18008133D
0x1800810f0  mov     [rsp+0B8h+var_60], rdi
0x1800810f5  lea     rcx, [rsp+0B8h+var_60]; struct CachingStream **
0x1800810fa  call    ?New@CachingStream@@SAJPEAPEAV1@@Z; CachingStream::New(CachingStream * *)
0x1800810ff  mov     esi, eax
0x180081101  mov     rax, [rsp+0B8h+var_60]
0x180081106  mov     [rsp+0B8h+arg_18], rax
0x18008110e  mov     [rsp+0B8h+var_88], esi
0x180081112  test    esi, esi
0x180081114  js      loc_18008133D
0x18008111a  mov     r12b, 1
0x18008111d  jmp     loc_1800811D3
0x180081122  mov     rax, [r14]
0x180081125  lea     r8, [rsp+0B8h+arg_18]
0x18008112d  lea     rdx, IID_IStream
0x180081134  mov     rcx, r14
0x180081137  mov     rax, [rax]
0x18008113a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008113f  test    eax, eax
0x180081141  jns     loc_1800811D3
0x180081147  mov     rax, [r14]
0x18008114a  lea     r8, [rsp+0B8h+var_80]
0x18008114f  lea     rdx, IID_ISequentialStream
0x180081156  mov     rcx, r14
0x180081159  mov     rax, [rax]
0x18008115c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081161  test    eax, eax
0x180081163  js      short loc_180081186
0x180081165  lea     rdx, [rsp+0B8h+arg_18]; struct IStream **
0x18008116d  mov     rcx, [rsp+0B8h+var_80]; struct ISequentialStream *
0x180081172  call    ?New@StreamWrapper@@SAJPEAUISequentialStream@@PEAPEAUIStream@@@Z; StreamWrapper::New(ISequentialStream *,IStream * *)
0x180081177  mov     esi, eax
0x180081179  mov     [rsp+0B8h+var_88], eax
0x18008117d  test    eax, eax
0x18008117f  jns     short loc_1800811D3
0x180081181  jmp     loc_18008133D
0x180081186  mov     rax, [r14]
0x180081189  lea     r8, [rsp+0B8h+var_78]
0x18008118e  lea     rdx, IID_IResponse
0x180081195  mov     rcx, r14
0x180081198  mov     rax, [rax]
0x18008119b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800811a0  test    eax, eax
0x1800811a2  js      short loc_1800811C5
0x1800811a4  lea     rdx, [rsp+0B8h+arg_18]; struct IStream **
0x1800811ac  mov     rcx, [rsp+0B8h+var_78]; struct IResponse *
0x1800811b1  call    ?New@DocStream@@SAJPEAUIResponse@@PEAPEAUIStream@@@Z; DocStream::New(IResponse *,IStream * *)
0x1800811b6  mov     esi, eax
0x1800811b8  mov     [rsp+0B8h+var_88], eax
0x1800811bc  test    eax, eax
0x1800811be  jns     short loc_1800811D3
0x1800811c0  jmp     loc_18008133D
0x1800811c5  mov     esi, 80070057h
0x1800811ca  mov     [rsp+0B8h+var_88], esi
0x1800811ce  jmp     loc_18008133D
0x1800811d3  xor     r9d, r9d; bool
0x1800811d6  mov     r8, [rsp+0B8h+arg_18]; struct IStream *
0x1800811de  mov     rdx, r13; struct IXMLDOMNode *
0x1800811e1  mov     rcx, [rsp+0B8h+arg_8]; struct IXMLDOMNode *
0x1800811e9  call    ?TransformNode@@YAXPEAUIXMLDOMNode@@0PEAUIStream@@_N@Z; TransformNode(IXMLDOMNode *,IXMLDOMNode *,IStream *,bool)
0x1800811ee  mov     [rsp+0B8h+var_88], edi
0x1800811f2  test    r12b, r12b
0x1800811f5  jz      short loc_180081231
0x1800811f7  mov     [rsp+0B8h+var_58], rdi
0x1800811fc  mov     rcx, [rsp+0B8h+arg_18]
0x180081204  mov     rax, [rcx]
0x180081207  xor     r9d, r9d
0x18008120a  xor     r8d, r8d
0x18008120d  mov     rdx, rdi
0x180081210  mov     rax, [rax+28h]
0x180081214  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081219  lea     rcx, [r15+58h]
0x18008121d  mov     rax, [rcx]
0x180081220  mov     rdx, [rsp+0B8h+arg_18]
0x180081228  mov     rax, [rax+28h]
0x18008122c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081231  mov     rcx, [rsp+0B8h+arg_18]
0x180081239  mov     rax, [rcx]
0x18008123c  xor     edx, edx
0x18008123e  mov     rax, [rax+40h]
0x180081242  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081247  mov     esi, eax
0x180081249  mov     [rsp+0B8h+var_88], eax
0x18008124d  cmp     eax, 80030001h
0x180081252  jz      short loc_18008126A
0x180081254  cmp     eax, 80004001h
0x180081259  jz      short loc_18008126A
0x18008125b  mov     [rsp+0B8h+var_88], eax
0x18008125f  test    eax, eax
0x180081261  jns     short loc_180081270
0x180081263  mov     ecx, eax; int
0x180081265  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x18008126a  mov     esi, edi
0x18008126c  mov     [rsp+0B8h+var_88], edi
0x180081270  jmp     loc_18008133D
0x180081275  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x18008127b  call    cs:__imp_TlsGetValue
0x180081281  mov     rbx, rax
0x180081284  cmp     dword ptr [rax+54h], 0C00000FDh
0x18008128b  jnz     short loc_180081306
0x18008128d  call    cs:__imp__resetstkoflw
0x180081293  test    eax, eax
0x180081295  jnz     short loc_1800812E8
0x180081297  mov     rcx, cs:?g_pMutexGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexGC
0x18008129e  test    rcx, rcx
0x1800812a1  jz      short loc_1800812B5
0x1800812a3  cmp     [rcx+50h], rbx
0x1800812a7  jnz     short loc_1800812B5
0x1800812a9  mov     rax, [rcx]
0x1800812ac  mov     rax, [rax+20h]
0x1800812b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800812b5  mov     rcx, cs:?g_pMutexFullGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexFullGC
0x1800812bc  test    rcx, rcx
0x1800812bf  jz      short loc_1800812D3
0x1800812c1  cmp     [rcx+50h], rbx
0x1800812c5  jnz     short loc_1800812D3
0x1800812c7  mov     rax, [rcx]
0x1800812ca  mov     rax, [rax+20h]
0x1800812ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800812d3  xor     r9d, r9d; lpArguments
0x1800812d6  xor     r8d, r8d; nNumberOfArguments
0x1800812d9  xor     edx, edx; dwExceptionFlags
0x1800812db  mov     ecx, 0C00000FDh; dwExceptionCode
0x1800812e0  call    cs:__imp_RaiseException
0x1800812e6  jmp     short loc_180081306
0x1800812e8  mov     rax, [rbx+60h]
0x1800812ec  mov     [rbx+68h], rax
0x1800812f0  lea     rax, ?s_cexpOutOfStack@Exception@@2V_CodebaseException@@B; _CodebaseException const Exception::s_cexpOutOfStack
0x1800812f7  mov     [rbx+60h], rax
0x1800812fb  mov     dword ptr [rbx+54h], 800703E9h
0x180081302  mov     byte ptr [rbx+78h], 0
0x180081306  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x18008130c  call    cs:__imp_TlsGetValue
0x180081312  mov     rcx, [rax+60h]; struct Exception *
0x180081316  call    ?setErrorInfo@_dispatchImpl@@SAPEAVException@@PEAV2@@Z; _dispatchImpl::setErrorInfo(Exception *)
0x18008131b  mov     rdx, rax
0x18008131e  mov     rcx, [rax]
0x180081321  mov     rax, [rcx+80h]
0x180081328  mov     rcx, rdx
0x18008132b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081330  mov     esi, eax
0x180081332  mov     [rsp+0B8h+var_88], eax
0x180081336  xor     edi, edi
0x180081338  mov     rbx, [rsp+0B8h+var_50]
0x18008133d  mov     rcx, [rsp+0B8h+arg_18]
0x180081345  test    rcx, rcx
0x180081348  jz      short loc_18008135E
0x18008134a  mov     rax, [rcx]
0x18008134d  mov     rax, [rax+10h]
0x180081351  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081356  mov     [rsp+0B8h+arg_18], rdi
0x18008135e  mov     rcx, [rsp+0B8h+var_80]
0x180081363  test    rcx, rcx
0x180081366  jz      short loc_180081379
0x180081368  mov     rax, [rcx]
0x18008136b  mov     rax, [rax+10h]
0x18008136f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081374  mov     [rsp+0B8h+var_80], rdi
0x180081379  mov     rcx, [rsp+0B8h+var_78]
0x18008137e  test    rcx, rcx
0x180081381  jz      short loc_180081394
0x180081383  mov     rax, [rcx]
0x180081386  mov     rax, [rax+10h]
0x18008138a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008138f  mov     [rsp+0B8h+var_78], rdi
0x180081394  mov     r14, [rsp+0B8h+var_70]
0x180081399  test    r14, r14
0x18008139c  jz      short loc_1800813B2
0x18008139e  mov     rax, [r14]
0x1800813a1  mov     rcx, r14
0x1800813a4  mov     rax, [rax+10h]
0x1800813a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800813ad  mov     [rsp+0B8h+var_70], rdi
0x1800813b2  mov     rcx, [rsp+0B8h+var_68]
0x1800813b7  test    rcx, rcx
0x1800813ba  jz      short loc_1800813CD
0x1800813bc  mov     rax, [rcx]
0x1800813bf  mov     rax, [rax+10h]
0x1800813c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800813c8  mov     [rsp+0B8h+var_68], rdi
0x1800813cd  lea     rcx, [rsp+0B8h+var_48]; this
0x1800813d2  call    ??1OMReadLock@@QEAA@XZ; OMReadLock::~OMReadLock(void)
0x1800813d7  mov     rcx, rbx
0x1800813da  mov     rax, cs:?g_pfnExit@@3P6AXPEAUTLSDATA@@@ZEA; void (*g_pfnExit)(TLSDATA *)
0x1800813e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800813e6  mov     eax, esi
0x1800813e8  lea     r11, [rsp+0B8h+var_28]
0x1800813f0  mov     rbx, [r11+30h]
0x1800813f4  mov     rsi, [r11+40h]
0x1800813f8  mov     rsp, r11
0x1800813fb  pop     r15
0x1800813fd  pop     r14
0x1800813ff  pop     r13
0x180081401  pop     r12
0x180081403  pop     rdi
0x180081404  retn
0x180103974  push    rbp
0x180103976  sub     rsp, 30h
0x18010397a  mov     rbp, rdx
0x18010397d  xor     edx, edx; bool
0x18010397f  call    ?fillException@Exception@@SAHPEAU_EXCEPTION_POINTERS@@_N@Z
0x180103984  nop
0x180103985  add     rsp, 30h
0x180103989  pop     rbp
0x18010398a  retn
```
