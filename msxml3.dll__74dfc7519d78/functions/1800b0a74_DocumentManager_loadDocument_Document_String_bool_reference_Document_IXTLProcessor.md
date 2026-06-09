# DocumentManager::loadDocument(Document *,String *,bool,_reference<Document> &,IXTLProcessor *)

- ea: `0x1800b0a74`
- end: `0x1800b0ea4`
- name: `?loadDocument@DocumentManager@@SAXPEAVDocument@@PEAVString@@_NAEAV?$_reference@VDocument@@@@PEAVIXTLProcessor@@@Z`
- size: `1072`
- prototype: `__int64 __usercall@<rax>(Document *this@<rcx>, struct Object *@<rdx>, __int64)`
- caller_count: `2`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x1800accc4`
- `0x1800b0968`

## callees

- `0x180012000`
- `0x18001ad40`
- `0x1800251a4`
- `0x180026de4`
- `0x18003c8bc`
- `0x18004a8fc`
- `0x180051efc`
- `0x180052cb4`
- `0x1800542ac`
- `0x18005e9e8`
- `0x180064034`
- `0x180064b90`
- `0x1800b0328`
- `0x1800b0a74`
- `0x180102cde`
- `0x180102d20`
- `0x180107010`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x1800b0d91`
- `msvcrt!_resetstkoflw` at `0x1800b0d91`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b0de4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b0de4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800b0d7f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800b0d7f`
- `ext-ms-win-ole32-bindctx-l1-1-0!CreateBindCtx` at `0x1800b0bb3`
- `ext-ms-win-ole32-bindctx-l1-1-0!CreateBindCtx` at `0x1800b0bb3`
- `urlmon!CreateURLMonikerEx` at `0x1800b0b82`
- `urlmon!CreateURLMonikerEx` at `0x1800b0b82`
- `urlmon!RegisterBindStatusCallback` at `0x1800b0c2a`
- `urlmon!RegisterBindStatusCallback` at `0x1800b0c2a`

## pseudocode

```c
void __fastcall DocumentManager::loadDocument(
        Document *this,
        struct Object *a2,
        __int64 a3,
        struct IUnknown **a4,
        __int64 a5)
{
  HRESULT v8; // ebx
  IBindStatusCallback *v9; // rdi
  const struct String *v10; // rcx
  XSLCallback *v11; // rax
  __int64 v12; // rdx
  struct IUnknownVtbl *lpVtbl; // rcx
  struct Object *v14; // rax
  unsigned int v15; // [rsp+30h] [rbp-F8h] BYREF
  int v16; // [rsp+34h] [rbp-F4h]
  LPBC ppbc; // [rsp+38h] [rbp-F0h] BYREF
  LPMONIKER ppmk; // [rsp+40h] [rbp-E8h] BYREF
  IBindStatusCallback *ppBSCBPrev; // [rsp+48h] [rbp-E0h] BYREF
  IBindStatusCallback *v20; // [rsp+50h] [rbp-D8h]
  __int64 v21; // [rsp+58h] [rbp-D0h] BYREF
  int v22; // [rsp+60h] [rbp-C8h]
  int v23; // [rsp+64h] [rbp-C4h]
  struct IUnknown **v24; // [rsp+68h] [rbp-C0h]
  _tagBINDINFO v25; // [rsp+70h] [rbp-B8h] BYREF

  v24 = a4;
  Model::Model(&v21, ((__int64)this[1].lpVtbl & 4LL) == 0);
  v8 = 0;
  v15 = 0;
  memset_0(&v25, 0, sizeof(v25));
  ppmk = 0;
  ppbc = 0;
  ppBSCBPrev = 0;
  v9 = 0;
  v20 = 0;
  assign(a4, 0);
  Document::_clone(this, 0, 0, (struct Document **)a4);
  assign((struct IUnknown **)&(*a4)[50], this[50].lpVtbl);
  if ( v23 == 1 && !(unsigned int)Base::model(a2) )
    a2 = String::newString(v10);
  if ( !a5
    || (*(unsigned int (__fastcall **)(__int64, unsigned int *, _tagBINDINFO *))(*(_QWORD *)a5 + 56LL))(a5, &v15, &v25)
    || !v15 )
  {
    ((void (__fastcall *)(struct IUnknown *, struct Object *, _QWORD))(*a4)->lpVtbl[7].AddRef)(*a4, a2, 0);
LABEL_19:
    lpVtbl = (*a4)[38].lpVtbl;
    if ( lpVtbl )
    {
      v14 = (struct Object *)(*((__int64 (__fastcall **)(struct IUnknownVtbl *))lpVtbl->QueryInterface + 17))(lpVtbl);
      Processor::Error(-1072897262, a2, v14, 0);
    }
    goto LABEL_21;
  }
  v8 = CreateURLMonikerEx(0, *((LPCWSTR *)a2 + 3), &ppmk, 1u);
  v16 = v8;
  if ( v8 < 0 )
    goto LABEL_21;
  if ( !ppmk )
  {
    v8 = -2147467261;
    v16 = -2147467261;
    goto LABEL_21;
  }
  v8 = CreateBindCtx(0, &ppbc);
  v16 = v8;
  if ( v8 >= 0 )
  {
    v15 &= 0xFFFFFFFC;
    v11 = (XSLCallback *)_MemAlloc(0xD0u, 0);
    if ( v11 )
      v9 = (IBindStatusCallback *)XSLCallback::XSLCallback(v11, &v15, &v25, 0, 0);
    else
      v9 = 0;
    v20 = v9;
    if ( !v9 )
    {
      v8 = -2147024882;
      v16 = -2147024882;
      goto LABEL_21;
    }
    v8 = RegisterBindStatusCallback(ppbc, v9, &ppBSCBPrev, 0);
    v16 = v8;
    if ( v8 >= 0 )
    {
      LOBYTE(v12) = 1;
      ((void (__fastcall *)(struct IUnknown *, __int64, LPMONIKER, LPBC, _DWORD))(*a4)->lpVtbl[6].Release)(
        *a4,
        v12,
        ppmk,
        ppbc,
        0);
      Document::throwLastError((Document *)*a4);
      goto LABEL_19;
    }
  }
LABEL_21:
  if ( ppbc )
  {
    ((void (__fastcall *)(LPBC))ppbc->lpVtbl->Release)(ppbc);
    ppbc = 0;
  }
  if ( ppBSCBPrev )
  {
    ((void (__fastcall *)(IBindStatusCallback *))ppBSCBPrev->lpVtbl->Release)(ppBSCBPrev);
    ppBSCBPrev = 0;
  }
  if ( v9 )
    ((void (__fastcall *)(IBindStatusCallback *))v9->lpVtbl->Release)(v9);
  if ( ppmk )
  {
    ((void (__fastcall *)(LPMONIKER))ppmk->lpVtbl->Release)(ppmk);
    ppmk = 0;
  }
  if ( v8 < 0 )
  {
    *(_DWORD *)(v21 + 76) = v22;
    assign(a4, 0);
    Exception::throwHR(v8);
  }
  Model::~Model((Model *)&v21);
}

```

## disassembly

```asm
0x1800b0a74  mov     [rsp+arg_10], rbx
0x1800b0a79  push    rsi
0x1800b0a7a  push    rdi
0x1800b0a7b  push    r13
0x1800b0a7d  push    r14
0x1800b0a7f  push    r15
0x1800b0a81  sub     rsp, 100h
0x1800b0a88  mov     rax, cs:__security_cookie
0x1800b0a8f  xor     rax, rsp
0x1800b0a92  mov     [rsp+128h+var_38], rax
0x1800b0a9a  mov     r14, r9
0x1800b0a9d  mov     rsi, rdx
0x1800b0aa0  mov     r13, rcx
0x1800b0aa3  mov     [rsp+128h+var_C0], r9
0x1800b0aa8  mov     r15, [rsp+128h+arg_20]
0x1800b0ab0  mov     edx, [rcx+8]
0x1800b0ab3  shr     rdx, 2
0x1800b0ab7  not     edx
0x1800b0ab9  and     edx, 1
0x1800b0abc  lea     rcx, [rsp+128h+var_D0]
0x1800b0ac1  call    ??0Model@@QEAA@W4RentalEnum@@@Z; Model::Model(RentalEnum)
0x1800b0ac6  xor     ebx, ebx
0x1800b0ac8  mov     [rsp+128h+var_F8], ebx
0x1800b0acc  xor     edx, edx; Val
0x1800b0ace  mov     r8d, 80h; Size
0x1800b0ad4  lea     rcx, [rsp+128h+var_B8]; void *
0x1800b0ad9  call    memset_0
0x1800b0ade  mov     [rsp+128h+ppmk], rbx
0x1800b0ae3  mov     [rsp+128h+ppbc], rbx
0x1800b0ae8  mov     [rsp+128h+ppBSCBPrev], rbx
0x1800b0aed  xor     edi, edi
0x1800b0aef  mov     [rsp+128h+var_D8], rdi
0x1800b0af4  xor     edx, edx; void *
0x1800b0af6  mov     rcx, r14; struct IUnknown **
0x1800b0af9  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800b0afe  mov     r9, r14; struct Document **
0x1800b0b01  xor     r8d, r8d; struct Node **
0x1800b0b04  xor     edx, edx; bool
0x1800b0b06  mov     rcx, r13; this
0x1800b0b09  call    ?_clone@Document@@QEAAX_NPEAPEAVNode@@PEAPEAV1@@Z; Document::_clone(bool,Node * *,Document * *)
0x1800b0b0e  mov     rcx, [r14]
0x1800b0b11  add     rcx, 190h; struct IUnknown **
0x1800b0b18  mov     rdx, [r13+190h]; void *
0x1800b0b1f  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800b0b24  cmp     [rsp+128h+var_C4], 1
0x1800b0b29  jnz     short loc_1800B0B3F
0x1800b0b2b  mov     rcx, rsi
0x1800b0b2e  call    ?model@Base@@QEAA?AW4RentalEnum@@XZ; Base::model(void)
0x1800b0b33  test    eax, eax
0x1800b0b35  jnz     short loc_1800B0B3F
0x1800b0b37  call    ?newString@String@@SAPEAV1@PEBV1@@Z; String::newString(String const *)
0x1800b0b3c  mov     rsi, rax
0x1800b0b3f  test    r15, r15
0x1800b0b42  jz      loc_1800B0C6A
0x1800b0b48  mov     rax, [r15]
0x1800b0b4b  lea     r8, [rsp+128h+var_B8]
0x1800b0b50  lea     rdx, [rsp+128h+var_F8]
0x1800b0b55  mov     rcx, r15
0x1800b0b58  mov     rax, [rax+38h]
0x1800b0b5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0b61  test    eax, eax
0x1800b0b63  jnz     loc_1800B0C6A
0x1800b0b69  cmp     [rsp+128h+var_F8], eax
0x1800b0b6d  jz      loc_1800B0C6A
0x1800b0b73  lea     r9d, [rax+1]; dwFlags
0x1800b0b77  lea     r8, [rsp+128h+ppmk]; ppmk
0x1800b0b7c  mov     rdx, [rsi+18h]; szURL
0x1800b0b80  xor     ecx, ecx; pMkCtx
0x1800b0b82  call    cs:__imp_CreateURLMonikerEx
0x1800b0b88  mov     ebx, eax
0x1800b0b8a  mov     [rsp+128h+var_F4], eax
0x1800b0b8e  test    eax, eax
0x1800b0b90  js      loc_1800B0CB4
0x1800b0b96  cmp     [rsp+128h+ppmk], 0
0x1800b0b9c  jnz     short loc_1800B0BAC
0x1800b0b9e  mov     ebx, 80004003h
0x1800b0ba3  mov     [rsp+128h+var_F4], ebx
0x1800b0ba7  jmp     loc_1800B0CB4
0x1800b0bac  lea     rdx, [rsp+128h+ppbc]; ppbc
0x1800b0bb1  xor     ecx, ecx; reserved
0x1800b0bb3  call    cs:__imp_CreateBindCtx
0x1800b0bb9  mov     ebx, eax
0x1800b0bbb  mov     [rsp+128h+var_F4], eax
0x1800b0bbf  test    eax, eax
0x1800b0bc1  js      loc_1800B0CB4
0x1800b0bc7  and     [rsp+128h+var_F8], 0FFFFFFFCh
0x1800b0bcc  xor     edx, edx; unsigned int
0x1800b0bce  mov     ecx, 0D0h; unsigned __int64
0x1800b0bd3  call    ?_MemAlloc@@YAPEAX_KK@Z; _MemAlloc(unsigned __int64,ulong)
0x1800b0bd8  test    rax, rax
0x1800b0bdb  jz      short loc_1800B0C00
0x1800b0bdd  mov     [rsp+128h+var_108], 0; struct IXMLNodeSource *
0x1800b0be6  xor     r9d, r9d; struct ViewerFactory *
0x1800b0be9  lea     r8, [rsp+128h+var_B8]; struct _tagBINDINFO *
0x1800b0bee  lea     rdx, [rsp+128h+var_F8]; unsigned int *
0x1800b0bf3  mov     rcx, rax; this
0x1800b0bf6  call    ??0XSLCallback@@QEAA@PEAKPEAU_tagBINDINFO@@PEAVViewerFactory@@PEAUIXMLNodeSource@@@Z; XSLCallback::XSLCallback(ulong *,_tagBINDINFO *,ViewerFactory *,IXMLNodeSource *)
0x1800b0bfb  mov     rdi, rax
0x1800b0bfe  jmp     short loc_1800B0C02
0x1800b0c00  xor     edi, edi
0x1800b0c02  mov     [rsp+128h+var_D8], rdi
0x1800b0c07  test    rdi, rdi
0x1800b0c0a  jnz     short loc_1800B0C1A
0x1800b0c0c  mov     ebx, 8007000Eh
0x1800b0c11  mov     [rsp+128h+var_F4], ebx
0x1800b0c15  jmp     loc_1800B0CB4
0x1800b0c1a  xor     r9d, r9d; dwReserved
0x1800b0c1d  lea     r8, [rsp+128h+ppBSCBPrev]; ppBSCBPrev
0x1800b0c22  mov     rdx, rdi; pBSCb
0x1800b0c25  mov     rcx, [rsp+128h+ppbc]; pBC
0x1800b0c2a  call    cs:__imp_RegisterBindStatusCallback
0x1800b0c30  mov     ebx, eax
0x1800b0c32  mov     [rsp+128h+var_F4], eax
0x1800b0c36  test    eax, eax
0x1800b0c38  js      short loc_1800B0CB4
0x1800b0c3a  mov     rcx, [r14]
0x1800b0c3d  mov     rax, [rcx]
0x1800b0c40  mov     dword ptr [rsp+128h+var_108], 0
0x1800b0c48  mov     r9, [rsp+128h+ppbc]
0x1800b0c4d  mov     r8, [rsp+128h+ppmk]
0x1800b0c52  mov     dl, 1
0x1800b0c54  mov     rax, [rax+0A0h]
0x1800b0c5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0c60  mov     rcx, [r14]; this
0x1800b0c63  call    ?throwLastError@Document@@QEAAXXZ; Document::throwLastError(void)
0x1800b0c68  jmp     short loc_1800B0C82
0x1800b0c6a  mov     rcx, [r14]
0x1800b0c6d  mov     rax, [rcx]
0x1800b0c70  xor     r8d, r8d
0x1800b0c73  mov     rdx, rsi
0x1800b0c76  mov     rax, [rax+0B0h]
0x1800b0c7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0c82  mov     rax, [r14]
0x1800b0c85  mov     rcx, [rax+130h]
0x1800b0c8c  test    rcx, rcx
0x1800b0c8f  jz      short loc_1800B0CB4
0x1800b0c91  mov     rax, [rcx]
0x1800b0c94  mov     rax, [rax+88h]
0x1800b0c9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0ca0  mov     r8, rax; struct Object *
0x1800b0ca3  xor     r9d, r9d; struct Object *
0x1800b0ca6  mov     rdx, rsi; struct Object *
0x1800b0ca9  mov     ecx, 0C00CE312h; int
0x1800b0cae  call    ?Error@Processor@@SAXJPEAVObject@@00@Z; Processor::Error(long,Object *,Object *,Object *)
0x1800b0cb4  mov     rcx, [rsp+128h+ppbc]
0x1800b0cb9  test    rcx, rcx
0x1800b0cbc  jz      short loc_1800B0CD3
0x1800b0cbe  mov     rax, [rcx]
0x1800b0cc1  mov     rax, [rax+10h]
0x1800b0cc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0cca  mov     [rsp+128h+ppbc], 0
0x1800b0cd3  mov     rcx, [rsp+128h+ppBSCBPrev]
0x1800b0cd8  test    rcx, rcx
0x1800b0cdb  jz      short loc_1800B0CF2
0x1800b0cdd  mov     rax, [rcx]
0x1800b0ce0  mov     rax, [rax+10h]
0x1800b0ce4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0ce9  mov     [rsp+128h+ppBSCBPrev], 0
0x1800b0cf2  test    rdi, rdi
0x1800b0cf5  jz      short loc_1800B0D06
0x1800b0cf7  mov     rax, [rdi]
0x1800b0cfa  mov     rcx, rdi
0x1800b0cfd  mov     rax, [rax+10h]
0x1800b0d01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0d06  mov     rcx, [rsp+128h+ppmk]
0x1800b0d0b  test    rcx, rcx
0x1800b0d0e  jz      short loc_1800B0D25
0x1800b0d10  mov     rax, [rcx]
0x1800b0d13  mov     rax, [rax+10h]
0x1800b0d17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0d1c  mov     [rsp+128h+ppmk], 0
0x1800b0d25  test    ebx, ebx
0x1800b0d27  jns     short loc_1800B0D47
0x1800b0d29  mov     edx, [rsp+128h+var_C8]
0x1800b0d2d  mov     rax, [rsp+128h+var_D0]
0x1800b0d32  mov     [rax+4Ch], edx
0x1800b0d35  xor     edx, edx; void *
0x1800b0d37  mov     rcx, r14; struct IUnknown **
0x1800b0d3a  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800b0d3f  mov     ecx, ebx; int
0x1800b0d41  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x1800b0d47  lea     rcx, [rsp+128h+var_D0]; this
0x1800b0d4c  call    ??1Model@@QEAA@XZ; Model::~Model(void)
0x1800b0d51  mov     rcx, [rsp+128h+var_38]
0x1800b0d59  xor     rcx, rsp; StackCookie
0x1800b0d5c  call    __security_check_cookie
0x1800b0d61  mov     rbx, [rsp+128h+arg_10]
0x1800b0d69  add     rsp, 100h
0x1800b0d70  pop     r15
0x1800b0d72  pop     r14
0x1800b0d74  pop     r13
0x1800b0d76  pop     rdi
0x1800b0d77  pop     rsi
0x1800b0d78  retn
0x1800b0d79  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x1800b0d7f  call    cs:__imp_TlsGetValue
0x1800b0d85  mov     rbx, rax
0x1800b0d88  cmp     dword ptr [rax+54h], 0C00000FDh
0x1800b0d8f  jnz     short loc_1800B0E0A
0x1800b0d91  call    cs:__imp__resetstkoflw
0x1800b0d97  test    eax, eax
0x1800b0d99  jnz     short loc_1800B0DEC
0x1800b0d9b  mov     rcx, cs:?g_pMutexGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexGC
0x1800b0da2  test    rcx, rcx
0x1800b0da5  jz      short loc_1800B0DB9
0x1800b0da7  cmp     [rcx+50h], rbx
0x1800b0dab  jnz     short loc_1800B0DB9
0x1800b0dad  mov     rax, [rcx]
0x1800b0db0  mov     rax, [rax+20h]
0x1800b0db4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0db9  mov     rcx, cs:?g_pMutexFullGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexFullGC
0x1800b0dc0  test    rcx, rcx
0x1800b0dc3  jz      short loc_1800B0DD7
0x1800b0dc5  cmp     [rcx+50h], rbx
0x1800b0dc9  jnz     short loc_1800B0DD7
0x1800b0dcb  mov     rax, [rcx]
0x1800b0dce  mov     rax, [rax+20h]
0x1800b0dd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0dd7  xor     r9d, r9d; lpArguments
0x1800b0dda  xor     r8d, r8d; nNumberOfArguments
0x1800b0ddd  xor     edx, edx; dwExceptionFlags
0x1800b0ddf  mov     ecx, 0C00000FDh; dwExceptionCode
0x1800b0de4  call    cs:__imp_RaiseException
0x1800b0dea  jmp     short loc_1800B0E0A
0x1800b0dec  mov     rax, [rbx+60h]
0x1800b0df0  mov     [rbx+68h], rax
0x1800b0df4  lea     rax, ?s_cexpOutOfStack@Exception@@2V_CodebaseException@@B; _CodebaseException const Exception::s_cexpOutOfStack
0x1800b0dfb  mov     [rbx+60h], rax
0x1800b0dff  mov     dword ptr [rbx+54h], 800703E9h
0x1800b0e06  mov     byte ptr [rbx+78h], 0
0x1800b0e0a  mov     ecx, [rsp+128h+var_C8]
0x1800b0e0e  mov     rax, [rsp+128h+var_D0]
0x1800b0e13  mov     [rax+4Ch], ecx
0x1800b0e16  xor     edx, edx; void *
0x1800b0e18  mov     rcx, [rsp+128h+var_C0]; struct IUnknown **
0x1800b0e1d  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800b0e22  mov     rcx, [rsp+128h+ppbc]
0x1800b0e27  test    rcx, rcx
0x1800b0e2a  jz      short loc_1800B0E41
0x1800b0e2c  mov     rax, [rcx]
0x1800b0e2f  mov     rax, [rax+10h]
0x1800b0e33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0e38  mov     [rsp+128h+ppbc], 0
0x1800b0e41  mov     rcx, [rsp+128h+ppBSCBPrev]
0x1800b0e46  test    rcx, rcx
0x1800b0e49  jz      short loc_1800B0E60
0x1800b0e4b  mov     rax, [rcx]
0x1800b0e4e  mov     rax, [rax+10h]
0x1800b0e52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0e57  mov     [rsp+128h+ppBSCBPrev], 0
0x1800b0e60  mov     rcx, [rsp+128h+var_D8]
0x1800b0e65  test    rcx, rcx
0x1800b0e68  jz      short loc_1800B0E7F
0x1800b0e6a  mov     rax, [rcx]
0x1800b0e6d  mov     rax, [rax+10h]
0x1800b0e71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0e76  mov     [rsp+128h+var_D8], 0
0x1800b0e7f  mov     rcx, [rsp+128h+ppmk]
0x1800b0e84  test    rcx, rcx
0x1800b0e87  jz      short loc_1800B0E9E
0x1800b0e89  mov     rax, [rcx]
0x1800b0e8c  mov     rax, [rax+10h]
0x1800b0e90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0e95  mov     [rsp+128h+ppmk], 0
0x1800b0e9e  call    ?throwAgain@Exception@@SAXXZ; Exception::throwAgain(void)
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
