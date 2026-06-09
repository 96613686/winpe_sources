# DOMProcessor::put_input(tagVARIANT)

- ea: `0x1800837f0`
- end: `0x180083b6a`
- name: `?put_input@DOMProcessor@@UEAAJUtagVARIANT@@@Z`
- size: `890`
- prototype: `__int64 __fastcall(DOMProcessor *__hidden this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180012000`
- `0x180026de4`
- `0x180027e88`
- `0x1800368b4`
- `0x180036da8`
- `0x18003889c`
- `0x18003c8bc`
- `0x18003e230`
- `0x18004852c`
- `0x18004a8fc`
- `0x180054f54`
- `0x18005e9e8`
- `0x18005f9b8`
- `0x180064034`
- `0x180067080`
- `0x1800780d0`
- `0x180082ad4`
- `0x1800837f0`
- `0x180083e2c`
- `0x180107010`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x180083a71`
- `msvcrt!_resetstkoflw` at `0x180083a71`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180083ac4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180083ac4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180083a5f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180083af0`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180083a5f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180083af0`
- `OLEAUT32!__imp_VariantCopy` at `0x180083a1b`
- `OLEAUT32!__imp_VariantCopy` at `0x180083a1b`

## pseudocode

```c
__int64 __fastcall DOMProcessor::put_input(DOMProcessor *this, struct tagVARIANT *a2)
{
  __int64 v4; // rbx
  struct Document *v6; // rsi
  char v7; // r12
  unsigned int v8; // eax
  int v9; // ecx
  struct IUnknown *Unknown; // rax
  struct Document *v11; // rdx
  unsigned int v12; // ecx
  int v13; // eax
  __int64 v14; // rax
  int v15; // r12d
  int v16; // ecx
  int v17; // ecx
  HRESULT v18; // r15d
  __int64 *v19; // [rsp+28h] [rbp-70h] BYREF
  __int64 v20; // [rsp+30h] [rbp-68h] BYREF
  struct Document *v21; // [rsp+38h] [rbp-60h]
  _BYTE v22[16]; // [rsp+40h] [rbp-58h] BYREF
  __int128 v23; // [rsp+50h] [rbp-48h] BYREF
  IRecordInfo *pRecInfo; // [rsp+60h] [rbp-38h]
  __int16 v25; // [rsp+B0h] [rbp+18h] BYREF
  struct Element *lpVtbl; // [rsp+B8h] [rbp+20h] BYREF

  EnsureTls::EnsureTls((EnsureTls *)&v20);
  v4 = v20;
  if ( !v20 )
  {
    ((void (__fastcall *)(_QWORD))g_pfnExit)(0);
    return 2147500037LL;
  }
  Model::Model(v22, 0);
  lpVtbl = 0;
  v19 = 0;
  v25 = 0;
  v6 = 0;
  v21 = 0;
  v7 = 1;
  LOWORD(v8) = Variant::getBaseType(a2);
  if ( (unsigned __int16)v8 > 0xDu )
    goto LABEL_8;
  v9 = 8707;
  if ( !_bittest(&v9, v8) )
    goto LABEL_8;
  Unknown = Variant::getUnknown(a2, 0);
  if ( Unknown )
  {
    if ( (int)GetElement(Unknown, &lpVtbl) >= 0 )
    {
      (*(void (__fastcall **)(struct Element *))(*(_QWORD *)lpVtbl + 400LL))(lpVtbl);
      v7 = 0;
    }
LABEL_8:
    if ( v7 )
    {
      v6 = Document::newDocument();
      v21 = v6;
      v11 = v6 + 3;
      if ( !v6 )
        v11 = 0;
      COMSafeControlRoot::CloneBase((COMSafeControlRoot *)(*((_QWORD *)this + 7) + 56LL), v11);
      Document::setDOM(v6, 1);
      LODWORD(v6[25].lpVtbl) &= ~0x400u;
      v12 = (__int64)v6[25].lpVtbl & 0xFFFEFFFF;
      LODWORD(v6[25].lpVtbl) = v12;
      v12 &= ~0x800u;
      LODWORD(v6[25].lpVtbl) = v12;
      LODWORD(v6[25].lpVtbl) = v12
                             ^ ((unsigned __int16)v12
                              ^ (unsigned __int16)(*((unsigned __int8 *)this + 184) << 8))
                             & 0x100;
      v13 = ((__int64 (__fastcall *)(struct Document *, GUID *, __int64 **))v6->lpVtbl->QueryInterface)(
              v6,
              &IID_IXMLDOMDocument,
              &v19);
      checkhr(v13);
      v14 = *v19;
      v23 = *(_OWORD *)&a2->vt;
      pRecInfo = a2->pRecInfo;
      v15 = (*(__int64 (__fastcall **)(__int64 *, __int128 *, __int16 *))(v14 + 464))(v19, &v23, &v25);
      (*(void (__fastcall **)(__int64 *))(*v19 + 16))(v19);
      if ( v6[38].lpVtbl )
        Exception::throwAgain();
      checkhr(v15);
      lpVtbl = (struct Element *)v6[34].lpVtbl;
    }
  }
  if ( lpVtbl )
  {
    v16 = *((_DWORD *)this + 40);
    if ( v16 && (v17 = v16 - 1) != 0 )
    {
      if ( v17 != 4 )
        Exception::throwHR(-1072897495);
      DOMProcessor::resetEvent(this);
    }
    else
    {
      *((_DWORD *)this + 40) = 1;
    }
  }
  else
  {
    DOMProcessor::clearRequiredEvent(this);
  }
  DOMProcessor::releaseInput(this);
  v18 = VariantCopy((VARIANTARG *)this + 5, a2);
  if ( v18 < 0 )
  {
    DOMProcessor::clearRequiredEvent(this);
    checkhr(v18);
  }
  assign((struct IUnknown **)this + 14, lpVtbl);
  if ( v6 )
    ((void (__fastcall *)(struct Document *))v6->lpVtbl->Release)(v6);
  Model::~Model((Model *)v22);
  ((void (__fastcall *)(__int64))g_pfnExit)(v4);
  return 0;
}

```

## disassembly

```asm
0x1800837f0  mov     [rsp+arg_0], rbx
0x1800837f5  push    rsi
0x1800837f6  push    rdi
0x1800837f7  push    r12
0x1800837f9  push    r14
0x1800837fb  push    r15
0x1800837fd  sub     rsp, 70h
0x180083801  mov     r15, rdx
0x180083804  mov     r14, rcx
0x180083807  lea     rcx, [rsp+98h+var_68]; this
0x18008380c  call    ??0EnsureTls@@QEAA@XZ; EnsureTls::EnsureTls(void)
0x180083811  mov     rbx, [rsp+98h+var_68]
0x180083816  xor     edi, edi
0x180083818  test    rbx, rbx
0x18008381b  jnz     short loc_180083835
0x18008381d  xor     ecx, ecx
0x18008381f  mov     rax, cs:?g_pfnExit@@3P6AXPEAUTLSDATA@@@ZEA; void (*g_pfnExit)(TLSDATA *)
0x180083826  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008382b  mov     eax, 80004005h
0x180083830  jmp     loc_180083B55
0x180083835  xor     edx, edx
0x180083837  lea     rcx, [rsp+98h+var_58]
0x18008383c  call    ??0Model@@QEAA@W4RentalEnum@@@Z; Model::Model(RentalEnum)
0x180083841  mov     [rsp+98h+arg_18], rdi
0x180083849  mov     [rsp+98h+var_70], rdi
0x18008384e  mov     [rsp+98h+arg_10], di
0x180083856  mov     rsi, rdi
0x180083859  mov     [rsp+98h+var_60], rdi
0x18008385e  mov     r12b, 1
0x180083861  mov     rcx, r15; struct tagVARIANT *
0x180083864  call    ?getBaseType@Variant@@SAGPEAUtagVARIANT@@@Z; Variant::getBaseType(tagVARIANT *)
0x180083869  cmp     ax, 0Dh
0x18008386d  ja      short loc_1800838BA
0x18008386f  mov     ecx, 2203h
0x180083874  bt      ecx, eax
0x180083877  jnb     short loc_1800838BA
0x180083879  xor     edx, edx; bool
0x18008387b  mov     rcx, r15; struct tagVARIANT *
0x18008387e  call    ?getUnknown@Variant@@SAPEAUIUnknown@@PEAUtagVARIANT@@_N@Z; Variant::getUnknown(tagVARIANT *,bool)
0x180083883  test    rax, rax
0x180083886  jz      loc_1800839C3
0x18008388c  lea     rdx, [rsp+98h+arg_18]; struct Element **
0x180083894  mov     rcx, rax; struct IUnknown *
0x180083897  call    ?GetElement@@YAJPEAUIUnknown@@PEAPEAVElement@@@Z; GetElement(IUnknown *,Element * *)
0x18008389c  test    eax, eax
0x18008389e  js      short loc_1800838BA
0x1800838a0  mov     rcx, [rsp+98h+arg_18]
0x1800838a8  mov     rax, [rcx]
0x1800838ab  mov     rax, [rax+190h]
0x1800838b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800838b7  mov     r12b, dil
0x1800838ba  test    r12b, r12b
0x1800838bd  jz      loc_1800839C3
0x1800838c3  call    ?newDocument@Document@@SAPEAV1@XZ; Document::newDocument(void)
0x1800838c8  mov     rsi, rax
0x1800838cb  mov     [rsp+98h+var_60], rax
0x1800838d0  mov     rcx, [r14+38h]
0x1800838d4  test    rax, rax
0x1800838d7  lea     rdx, [rax+18h]
0x1800838db  jnz     short loc_1800838E0
0x1800838dd  mov     rdx, rdi; void *
0x1800838e0  add     rcx, 38h ; '8'; this
0x1800838e4  call    ?CloneBase@COMSafeControlRoot@@IEAAXPEAX@Z; COMSafeControlRoot::CloneBase(void *)
0x1800838e9  mov     dl, 1; bool
0x1800838eb  mov     rcx, rsi; this
0x1800838ee  call    ?setDOM@Document@@QEAAX_N@Z; Document::setDOM(bool)
0x1800838f3  btr     dword ptr [rsi+0C8h], 0Ah
0x1800838fb  mov     ecx, [rsi+0C8h]
0x180083901  btr     ecx, 10h
0x180083905  mov     [rsi+0C8h], ecx
0x18008390b  btr     ecx, 0Bh
0x18008390f  mov     [rsi+0C8h], ecx
0x180083915  movzx   eax, byte ptr [r14+0B8h]
0x18008391d  shl     eax, 8
0x180083920  xor     eax, ecx
0x180083922  and     eax, 100h
0x180083927  xor     eax, ecx
0x180083929  mov     [rsi+0C8h], eax
0x18008392f  mov     rax, [rsi]
0x180083932  lea     r8, [rsp+98h+var_70]
0x180083937  lea     rdx, IID_IXMLDOMDocument
0x18008393e  mov     rcx, rsi
0x180083941  mov     rax, [rax]
0x180083944  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083949  mov     ecx, eax; int
0x18008394b  call    ?checkhr@@YAXJ@Z; checkhr(long)
0x180083950  mov     rcx, [rsp+98h+var_70]
0x180083955  mov     rax, [rcx]
0x180083958  movups  xmm0, xmmword ptr [r15]
0x18008395c  movaps  [rsp+98h+var_48], xmm0
0x180083961  movsd   xmm1, qword ptr [r15+10h]
0x180083967  movsd   [rsp+98h+var_38], xmm1
0x18008396d  lea     r8, [rsp+98h+arg_10]
0x180083975  lea     rdx, [rsp+98h+var_48]
0x18008397a  mov     rax, [rax+1D0h]
0x180083981  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083986  mov     r12d, eax
0x180083989  mov     [rsp+98h+var_78], eax
0x18008398d  mov     rcx, [rsp+98h+var_70]
0x180083992  mov     rdx, [rcx]
0x180083995  mov     rax, [rdx+10h]
0x180083999  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008399e  cmp     [rsi+130h], rdi
0x1800839a5  jz      short loc_1800839AC
0x1800839a7  call    ?throwAgain@Exception@@SAXXZ; Exception::throwAgain(void)
0x1800839ac  mov     ecx, r12d; int
0x1800839af  call    ?checkhr@@YAXJ@Z; checkhr(long)
0x1800839b4  mov     rax, [rsi+110h]
0x1800839bb  mov     [rsp+98h+arg_18], rax
0x1800839c3  cmp     [rsp+98h+arg_18], rdi
0x1800839cb  jz      short loc_180083A04
0x1800839cd  mov     ecx, [r14+0A0h]
0x1800839d4  test    ecx, ecx
0x1800839d6  jz      short loc_1800839F7
0x1800839d8  sub     ecx, 1
0x1800839db  jz      short loc_1800839F7
0x1800839dd  cmp     ecx, 4
0x1800839e0  jz      short loc_1800839ED
0x1800839e2  mov     ecx, 0C00CE229h; int
0x1800839e7  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x1800839ed  mov     rcx, r14; this
0x1800839f0  call    ?resetEvent@DOMProcessor@@IEAAXXZ; DOMProcessor::resetEvent(void)
0x1800839f5  jmp     short loc_180083A0C
0x1800839f7  mov     dword ptr [r14+0A0h], 1
0x180083a02  jmp     short loc_180083A0C
0x180083a04  mov     rcx, r14; this
0x180083a07  call    ?clearRequiredEvent@DOMProcessor@@IEAAXXZ; DOMProcessor::clearRequiredEvent(void)
0x180083a0c  mov     rcx, r14; this
0x180083a0f  call    ?releaseInput@DOMProcessor@@IEAAXXZ; DOMProcessor::releaseInput(void)
0x180083a14  lea     rcx, [r14+78h]; pvargDest
0x180083a18  mov     rdx, r15; pvargSrc
0x180083a1b  call    cs:__imp_VariantCopy
0x180083a21  mov     r15d, eax
0x180083a24  mov     [rsp+98h+var_78], eax
0x180083a28  test    eax, eax
0x180083a2a  jns     short loc_180083A3C
0x180083a2c  mov     rcx, r14; this
0x180083a2f  call    ?clearRequiredEvent@DOMProcessor@@IEAAXXZ; DOMProcessor::clearRequiredEvent(void)
0x180083a34  mov     ecx, r15d; int
0x180083a37  call    ?checkhr@@YAXJ@Z; checkhr(long)
0x180083a3c  lea     rcx, [r14+70h]; struct IUnknown **
0x180083a40  mov     rdx, [rsp+98h+arg_18]; void *
0x180083a48  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x180083a4d  mov     r14d, edi
0x180083a50  mov     [rsp+98h+var_78], edi
0x180083a54  jmp     loc_180083B25
0x180083a59  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x180083a5f  call    cs:__imp_TlsGetValue
0x180083a65  mov     rbx, rax
0x180083a68  cmp     dword ptr [rax+54h], 0C00000FDh
0x180083a6f  jnz     short loc_180083AEA
0x180083a71  call    cs:__imp__resetstkoflw
0x180083a77  test    eax, eax
0x180083a79  jnz     short loc_180083ACC
0x180083a7b  mov     rcx, cs:?g_pMutexGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexGC
0x180083a82  test    rcx, rcx
0x180083a85  jz      short loc_180083A99
0x180083a87  cmp     [rcx+50h], rbx
0x180083a8b  jnz     short loc_180083A99
0x180083a8d  mov     rax, [rcx]
0x180083a90  mov     rax, [rax+20h]
0x180083a94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083a99  mov     rcx, cs:?g_pMutexFullGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexFullGC
0x180083aa0  test    rcx, rcx
0x180083aa3  jz      short loc_180083AB7
0x180083aa5  cmp     [rcx+50h], rbx
0x180083aa9  jnz     short loc_180083AB7
0x180083aab  mov     rax, [rcx]
0x180083aae  mov     rax, [rax+20h]
0x180083ab2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083ab7  xor     r9d, r9d; lpArguments
0x180083aba  xor     r8d, r8d; nNumberOfArguments
0x180083abd  xor     edx, edx; dwExceptionFlags
0x180083abf  mov     ecx, 0C00000FDh; dwExceptionCode
0x180083ac4  call    cs:__imp_RaiseException
0x180083aca  jmp     short loc_180083AEA
0x180083acc  mov     rax, [rbx+60h]
0x180083ad0  mov     [rbx+68h], rax
0x180083ad4  lea     rax, ?s_cexpOutOfStack@Exception@@2V_CodebaseException@@B; _CodebaseException const Exception::s_cexpOutOfStack
0x180083adb  mov     [rbx+60h], rax
0x180083adf  mov     dword ptr [rbx+54h], 800703E9h
0x180083ae6  mov     byte ptr [rbx+78h], 0
0x180083aea  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x180083af0  call    cs:__imp_TlsGetValue
0x180083af6  mov     rcx, [rax+60h]; struct Exception *
0x180083afa  call    ?setErrorInfo@_dispatchImpl@@SAPEAVException@@PEAV2@@Z; _dispatchImpl::setErrorInfo(Exception *)
0x180083aff  mov     rdx, rax
0x180083b02  mov     rcx, [rax]
0x180083b05  mov     rax, [rcx+80h]
0x180083b0c  mov     rcx, rdx
0x180083b0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083b14  mov     r14d, eax
0x180083b17  mov     [rsp+98h+var_78], eax
0x180083b1b  mov     rbx, [rsp+98h+var_68]
0x180083b20  mov     rsi, [rsp+98h+var_60]
0x180083b25  test    rsi, rsi
0x180083b28  jz      short loc_180083B39
0x180083b2a  mov     rcx, [rsi]
0x180083b2d  mov     rax, [rcx+10h]
0x180083b31  mov     rcx, rsi
0x180083b34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083b39  lea     rcx, [rsp+98h+var_58]; this
0x180083b3e  call    ??1Model@@QEAA@XZ; Model::~Model(void)
0x180083b43  mov     rcx, rbx
0x180083b46  mov     rax, cs:?g_pfnExit@@3P6AXPEAUTLSDATA@@@ZEA; void (*g_pfnExit)(TLSDATA *)
0x180083b4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083b52  mov     eax, r14d
0x180083b55  mov     rbx, [rsp+98h+arg_0]
0x180083b5d  add     rsp, 70h
0x180083b61  pop     r15
0x180083b63  pop     r14
0x180083b65  pop     r12
0x180083b67  pop     rdi
0x180083b68  pop     rsi
0x180083b69  retn
0x180103b64  push    rbp
0x180103b66  sub     rsp, 20h
0x180103b6a  mov     rbp, rdx
0x180103b6d  xor     edx, edx; bool
0x180103b6f  call    ?fillException@Exception@@SAHPEAU_EXCEPTION_POINTERS@@_N@Z
0x180103b74  nop
0x180103b75  add     rsp, 20h
0x180103b79  pop     rbp
0x180103b7a  retn
```
