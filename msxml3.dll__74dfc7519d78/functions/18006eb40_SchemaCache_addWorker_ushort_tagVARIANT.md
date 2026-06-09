# SchemaCache::_addWorker(ushort *,tagVARIANT *)

- ea: `0x18006eb40`
- end: `0x18006eff6`
- name: `?_addWorker@SchemaCache@@QEAAJPEAGPEAUtagVARIANT@@@Z`
- size: `1206`
- prototype: `int(SchemaCache *__hidden this, unsigned __int16 *, struct tagVARIANT *)`
- caller_count: `2`
- callee_count: `23`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18006f020`
- `0x18006f0a0`

## callees

- `0x180012000`
- `0x18001ecd0`
- `0x1800222c0`
- `0x180026a30`
- `0x1800277e8`
- `0x18003889c`
- `0x18003d3f8`
- `0x180042b24`
- `0x18004852c`
- `0x18004a8fc`
- `0x18004a990`
- `0x18004f10c`
- `0x1800542ac`
- `0x18005f9b8`
- `0x180064034`
- `0x180067080`
- `0x18006cd30`
- `0x18006e800`
- `0x18006eb40`
- `0x180070120`
- `0x18008f790`
- `0x1800fc66c`
- `0x180107010`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x18006ec96`
- `msvcrt!_resetstkoflw` at `0x18006ef00`
- `msvcrt!_resetstkoflw` at `0x18006ec96`
- `msvcrt!_resetstkoflw` at `0x18006ef00`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006ece9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006ef53`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006ece9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006ef53`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18006ec84`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18006ed15`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18006eeee`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18006ef7f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18006ec84`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18006ed15`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18006eeee`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18006ef7f`
- `OLEAUT32!__imp_VariantClear` at `0x18006efca`
- `OLEAUT32!__imp_VariantClear` at `0x18006efca`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x18006ebc9`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x18006ebc9`

## pseudocode

```c
__int64 __fastcall SchemaCache::_addWorker(SchemaCache *this, unsigned __int16 *a2, struct tagVARIANT *a3)
{
  struct Document *v5; // rsi
  struct IUnknown *v6; // r15
  unsigned int v7; // ecx
  struct String *v8; // rax
  Exception *lpVtbl; // rcx
  struct Node *Root; // r12
  struct Node *v11; // rax
  struct Node *v12; // rcx
  struct NodeVtbl *v13; // rbx
  struct DTD *v14; // rdi
  struct IUnknown **v15; // rbx
  struct Node *v17; // [rsp+38h] [rbp-60h] BYREF
  struct IUnknown *v18[2]; // [rsp+40h] [rbp-58h] BYREF
  VARIANTARG pvargDest; // [rsp+50h] [rbp-48h] BYREF
  struct Document *v20; // [rsp+B8h] [rbp+20h] BYREF

  memset(&pvargDest, 0, sizeof(pvargDest));
  pvargDest.vt = 1;
  v5 = 0;
  v20 = 0;
  v18[0] = 0;
  v17 = 0;
  if ( a2 && *a2 )
    v6 = (struct IUnknown *)LookupURIAtom(a2, (int)a2);
  else
    v6 = (struct IUnknown *)Atom::s_emptyAtom;
  v18[1] = v6;
  if ( !VariantChangeTypeEx(&pvargDest, a3, 0x409u, 0, 8u) )
  {
    v5 = Document::newDocument();
    v20 = v5;
    COMSafeControlRoot::CloneBase(
      (SchemaCache *)((char *)this + 56),
      (void *)((unsigned __int64)&v5[3] & ((unsigned __int128)-(__int128)(unsigned __int64)v5 >> 64)));
    Document::setDOM(v5, 1);
    LODWORD(v5[25].lpVtbl) &= ~0x10000u;
    v7 = (__int64)v5[25].lpVtbl & 0xFFFFF7FF;
    LODWORD(v5[25].lpVtbl) = v7;
    v7 &= ~0x400u;
    LODWORD(v5[25].lpVtbl) = v7;
    LODWORD(v5[25].lpVtbl) = v7
                           ^ ((unsigned __int16)v7
                            ^ (unsigned __int16)(*((unsigned __int8 *)this + 200) << 8))
                           & 0x100;
    Document::prepareDOMLoad(v5);
    v8 = String::newString(pvargDest.bstrVal);
    ((void (__fastcall *)(struct Document *, struct String *, _QWORD))v5->lpVtbl->get_Application)(v5, v8, 0);
    Document::finishDOMLoad(v5, 0);
    HIDWORD(v5[25].lpVtbl) |= 0x100u;
    lpVtbl = (Exception *)v5[38].lpVtbl;
    if ( lpVtbl )
      Exception::throwThis(lpVtbl);
    Root = Document::getRoot(v5);
    v17 = Root;
LABEL_18:
    _InterlockedAdd((volatile signed __int32 *)&v5[54], 1u);
    DTD::New(0, (struct DTD **)v18);
    v14 = (struct DTD *)v18[0];
    DTD::addSchemaURN((DTD *)v18[0], (struct Atom *)v6, (struct Object *)v6);
    SchemaProcess(v5, v14, Root, (struct Atom *)v6, 0);
    SchemaCacheInfo::remove((SchemaCache *)((char *)this + 120), (struct Atom *)v6);
    v15 = (struct IUnknown **)_SetArray::_newslot((SchemaCache *)((char *)this + 120), 32, (unsigned __int64)v6);
    ((void (__fastcall *)(struct IUnknown *))v6->lpVtbl->AddRef)(v6);
    assign(v15 + 1, v5);
    v15[2] = (struct IUnknown *)Root;
    assign(v15 + 3, v14);
    goto LABEL_23;
  }
  v11 = Node::Variant2Node(a3);
  v12 = v11;
  if ( v11 )
  {
    v13 = v11[3].lpVtbl;
    if ( LODWORD(v13[4].GetTypeInfo) != 4 )
      Exception::throwHR(-1072897493);
    if ( ((__int64)v11[2].lpVtbl & 0x1F000000) == 0x3000000 )
      v12 = Document::getRoot((Document *)v13);
    if ( !v12 )
      Exception::throwHR(-2147024809);
    v17 = v12;
    Document::_clone((Document *)v13, 1, &v17, &v20);
    v5 = v20;
    assign((struct IUnknown **)&v20[50], 0);
    Root = v17;
    goto LABEL_18;
  }
  if ( a3->vt > 1u && a3->vt != 10 )
    Exception::throwHR(-2147024809);
  SchemaCacheInfo::remove((SchemaCache *)((char *)this + 120), (struct Atom *)v6);
LABEL_23:
  if ( v5 )
    ((void (__fastcall *)(struct Document *))v5->lpVtbl->Release)(v5);
  VariantClear(&pvargDest);
  release(v18);
  return 0;
}

```

## disassembly

```asm
0x18006eb40  mov     r11, rsp
0x18006eb43  mov     [r11+10h], rbx
0x18006eb47  mov     [r11+18h], rsi
0x18006eb4b  mov     [r11+8], rcx
0x18006eb4f  push    rdi
0x18006eb50  push    r12
0x18006eb52  push    r13
0x18006eb54  push    r14
0x18006eb56  push    r15
0x18006eb58  sub     rsp, 70h
0x18006eb5c  mov     rbx, r8
0x18006eb5f  mov     r13, rcx
0x18006eb62  xorps   xmm0, xmm0
0x18006eb65  xor     eax, eax
0x18006eb67  movups  xmmword ptr [rsp+98h+pvargDest], xmm0
0x18006eb6c  mov     [r11-38h], rax
0x18006eb70  lea     edi, [rax+1]
0x18006eb73  mov     word ptr [rsp+98h+pvargDest], di
0x18006eb78  xor     r14d, r14d
0x18006eb7b  mov     esi, r14d
0x18006eb7e  mov     [r11+20h], r14
0x18006eb82  mov     [r11-58h], r14
0x18006eb86  mov     [r11-60h], r14
0x18006eb8a  test    rdx, rdx
0x18006eb8d  jz      short loc_18006EBA2
0x18006eb8f  cmp     [rdx], r14w
0x18006eb93  jz      short loc_18006EBA2
0x18006eb95  mov     rcx, rdx; unsigned __int16 *
0x18006eb98  call    ?LookupURIAtom@@YAPEAVAtom@@PEBGH@Z; LookupURIAtom(ushort const *,int)
0x18006eb9d  mov     r15, rax
0x18006eba0  jmp     short loc_18006EBA9
0x18006eba2  mov     r15, cs:?s_emptyAtom@Atom@@0V?$_staticreference@VAtom@@@@A; _staticreference<Atom> Atom::s_emptyAtom
0x18006eba9  mov     [rsp+98h+var_50], r15
0x18006ebae  mov     eax, 8
0x18006ebb3  xor     r9d, r9d; wFlags
0x18006ebb6  mov     [rsp+98h+vt], ax; vt
0x18006ebbb  mov     r8d, 409h; lcid
0x18006ebc1  mov     rdx, rbx; pvarSrc
0x18006ebc4  lea     rcx, [rsp+98h+pvargDest]; pvargDest
0x18006ebc9  call    cs:__imp_VariantChangeTypeEx
0x18006ebcf  test    eax, eax
0x18006ebd1  jnz     loc_18006ED9C
0x18006ebd7  call    ?newDocument@Document@@SAPEAV1@XZ; Document::newDocument(void)
0x18006ebdc  mov     rsi, rax
0x18006ebdf  mov     [rsp+98h+arg_18], rax
0x18006ebe7  lea     rcx, [rax+18h]
0x18006ebeb  neg     rax
0x18006ebee  sbb     rdx, rdx
0x18006ebf1  and     rdx, rcx; void *
0x18006ebf4  lea     rcx, [r13+38h]; this
0x18006ebf8  call    ?CloneBase@COMSafeControlRoot@@IEAAXPEAX@Z; COMSafeControlRoot::CloneBase(void *)
0x18006ebfd  mov     dl, dil; bool
0x18006ec00  mov     rcx, rsi; this
0x18006ec03  call    ?setDOM@Document@@QEAAX_N@Z; Document::setDOM(bool)
0x18006ec08  btr     dword ptr [rsi+0C8h], 10h
0x18006ec10  mov     ecx, [rsi+0C8h]
0x18006ec16  btr     ecx, 0Bh
0x18006ec1a  mov     [rsi+0C8h], ecx
0x18006ec20  btr     ecx, 0Ah
0x18006ec24  mov     [rsi+0C8h], ecx
0x18006ec2a  movzx   eax, byte ptr [r13+0C8h]
0x18006ec32  shl     eax, 8
0x18006ec35  xor     eax, ecx
0x18006ec37  and     eax, 100h
0x18006ec3c  xor     eax, ecx
0x18006ec3e  mov     [rsi+0C8h], eax
0x18006ec44  mov     rcx, rsi; this
0x18006ec47  call    ?prepareDOMLoad@Document@@QEAAXXZ; Document::prepareDOMLoad(void)
0x18006ec4c  nop
0x18006ec4d  mov     rcx, qword ptr [rsp+98h+pvargDest+8]; unsigned __int16 *
0x18006ec52  call    ?newString@String@@SAPEAV1@PEBG@Z; String::newString(ushort const *)
0x18006ec57  mov     rcx, [rsi]
0x18006ec5a  mov     r9, [rcx+0B0h]
0x18006ec61  xor     r8d, r8d
0x18006ec64  mov     rdx, rax
0x18006ec67  mov     rcx, rsi
0x18006ec6a  mov     rax, r9
0x18006ec6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ec72  mov     ebx, r14d
0x18006ec75  mov     [rsp+98h+var_68], ebx
0x18006ec79  jmp     loc_18006ED5C
0x18006ec7e  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x18006ec84  call    cs:__imp_TlsGetValue
0x18006ec8a  mov     rbx, rax
0x18006ec8d  cmp     dword ptr [rax+54h], 0C00000FDh
0x18006ec94  jnz     short loc_18006ED0F
0x18006ec96  call    cs:__imp__resetstkoflw
0x18006ec9c  test    eax, eax
0x18006ec9e  jnz     short loc_18006ECF1
0x18006eca0  mov     rcx, cs:?g_pMutexGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexGC
0x18006eca7  test    rcx, rcx
0x18006ecaa  jz      short loc_18006ECBE
0x18006ecac  cmp     [rcx+50h], rbx
0x18006ecb0  jnz     short loc_18006ECBE
0x18006ecb2  mov     rax, [rcx]
0x18006ecb5  mov     rax, [rax+20h]
0x18006ecb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ecbe  mov     rcx, cs:?g_pMutexFullGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexFullGC
0x18006ecc5  test    rcx, rcx
0x18006ecc8  jz      short loc_18006ECDC
0x18006ecca  cmp     [rcx+50h], rbx
0x18006ecce  jnz     short loc_18006ECDC
0x18006ecd0  mov     rax, [rcx]
0x18006ecd3  mov     rax, [rax+20h]
0x18006ecd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ecdc  xor     r9d, r9d; lpArguments
0x18006ecdf  xor     r8d, r8d; nNumberOfArguments
0x18006ece2  xor     edx, edx; dwExceptionFlags
0x18006ece4  mov     ecx, 0C00000FDh; dwExceptionCode
0x18006ece9  call    cs:__imp_RaiseException
0x18006ecef  jmp     short loc_18006ED0F
0x18006ecf1  mov     rax, [rbx+60h]
0x18006ecf5  mov     [rbx+68h], rax
0x18006ecf9  lea     rax, ?s_cexpOutOfStack@Exception@@2V_CodebaseException@@B; _CodebaseException const Exception::s_cexpOutOfStack
0x18006ed00  mov     [rbx+60h], rax
0x18006ed04  mov     dword ptr [rbx+54h], 800703E9h
0x18006ed0b  mov     byte ptr [rbx+78h], 0
0x18006ed0f  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x18006ed15  call    cs:__imp_TlsGetValue
0x18006ed1b  mov     rcx, [rax+60h]; struct Exception *
0x18006ed1f  call    ?setErrorInfo@_dispatchImpl@@SAPEAVException@@PEAV2@@Z; _dispatchImpl::setErrorInfo(Exception *)
0x18006ed24  mov     rdx, rax
0x18006ed27  mov     rcx, [rax]
0x18006ed2a  mov     rax, [rcx+80h]
0x18006ed31  mov     rcx, rdx
0x18006ed34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ed39  mov     ebx, eax
0x18006ed3b  mov     [rsp+98h+var_68], eax
0x18006ed3f  mov     edi, 1
0x18006ed44  xor     r14d, r14d
0x18006ed47  mov     r13, [rsp+98h+arg_0]
0x18006ed4f  mov     rsi, [rsp+98h+arg_18]
0x18006ed57  mov     r15, [rsp+98h+var_50]
0x18006ed5c  mov     edx, ebx; int
0x18006ed5e  mov     rcx, rsi; this
0x18006ed61  call    ?finishDOMLoad@Document@@QEAAXJ@Z; Document::finishDOMLoad(long)
0x18006ed66  bts     dword ptr [rsi+0CCh], 8
0x18006ed6e  test    ebx, ebx
0x18006ed70  js      loc_18006EFB1
0x18006ed76  mov     rcx, [rsi+130h]; this
0x18006ed7d  test    rcx, rcx
0x18006ed80  jz      short loc_18006ED87
0x18006ed82  call    ?throwThis@Exception@@QEAAXXZ; Exception::throwThis(void)
0x18006ed87  mov     rcx, rsi; this
0x18006ed8a  call    ?getRoot@Document@@QEAAPEAVNode@@XZ; Document::getRoot(void)
0x18006ed8f  mov     r12, rax
0x18006ed92  mov     [rsp+98h+var_60], rax
0x18006ed97  jmp     loc_18006EE28
0x18006ed9c  mov     rcx, rbx; struct tagVARIANT *
0x18006ed9f  call    ?Variant2Node@Node@@SAPEAV1@PEAUtagVARIANT@@@Z; Node::Variant2Node(tagVARIANT *)
0x18006eda4  mov     rcx, rax
0x18006eda7  test    rax, rax
0x18006edaa  jz      loc_18006EEBB
0x18006edb0  mov     rbx, [rax+18h]
0x18006edb4  cmp     dword ptr [rbx+1A0h], 4
0x18006edbb  jz      short loc_18006EDC7
0x18006edbd  mov     ecx, 0C00CE22Bh; int
0x18006edc2  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x18006edc7  mov     eax, [rax+10h]
0x18006edca  and     eax, 1F000000h
0x18006edcf  cmp     eax, 3000000h
0x18006edd4  jnz     short loc_18006EDE1
0x18006edd6  mov     rcx, rbx; this
0x18006edd9  call    ?getRoot@Document@@QEAAPEAVNode@@XZ; Document::getRoot(void)
0x18006edde  mov     rcx, rax
0x18006ede1  test    rcx, rcx
0x18006ede4  jnz     short loc_18006EDF0
0x18006ede6  mov     ecx, 80070057h; int
0x18006edeb  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x18006edf0  mov     [rsp+98h+var_60], rcx
0x18006edf5  lea     r9, [rsp+98h+arg_18]; struct Document **
0x18006edfd  lea     r8, [rsp+98h+var_60]; struct Node **
0x18006ee02  mov     dl, dil; bool
0x18006ee05  mov     rcx, rbx; this
0x18006ee08  call    ?_clone@Document@@QEAAX_NPEAPEAVNode@@PEAPEAV1@@Z; Document::_clone(bool,Node * *,Document * *)
0x18006ee0d  mov     rsi, [rsp+98h+arg_18]
0x18006ee15  lea     rcx, [rsi+190h]; struct IUnknown **
0x18006ee1c  xor     edx, edx; void *
0x18006ee1e  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x18006ee23  mov     r12, [rsp+98h+var_60]
0x18006ee28  lock add [rsi+1B0h], edi
0x18006ee2f  lea     rdx, [rsp+98h+var_58]; struct DTD **
0x18006ee34  xor     ecx, ecx; struct Document *
0x18006ee36  call    ?New@DTD@@SAXPEAVDocument@@PEAPEAV1@@Z; DTD::New(Document *,DTD * *)
0x18006ee3b  mov     r8, r15; struct Object *
0x18006ee3e  mov     rdx, r15; struct Atom *
0x18006ee41  mov     rdi, [rsp+98h+var_58]
0x18006ee46  mov     rcx, rdi; this
0x18006ee49  call    ?addSchemaURN@DTD@@QEAAXPEAVAtom@@PEAVObject@@@Z; DTD::addSchemaURN(Atom *,Object *)
0x18006ee4e  mov     byte ptr [rsp+98h+vt], r14b; bool
0x18006ee53  mov     r9, r15; struct Atom *
0x18006ee56  mov     r8, r12; struct Node *
0x18006ee59  mov     rdx, rdi; struct DTD *
0x18006ee5c  mov     rcx, rsi; struct Document *
0x18006ee5f  call    ?SchemaProcess@@YAXPEAVDocument@@PEAVDTD@@PEAVNode@@PEAVAtom@@_N@Z; SchemaProcess(Document *,DTD *,Node *,Atom *,bool)
0x18006ee64  mov     rdx, r15; struct Atom *
0x18006ee67  lea     rcx, [r13+78h]; this
0x18006ee6b  call    ?remove@SchemaCacheInfo@@QEAAXPEAVAtom@@@Z; SchemaCacheInfo::remove(Atom *)
0x18006ee70  mov     r8, r15; unsigned __int64
0x18006ee73  mov     edx, 20h ; ' '; int
0x18006ee78  lea     rcx, [r13+78h]; this
0x18006ee7c  call    ?_newslot@_SetArray@@IEAAPEAXH_K@Z; _SetArray::_newslot(int,unsigned __int64)
0x18006ee81  mov     rbx, rax
0x18006ee84  mov     rcx, [r15]
0x18006ee87  mov     rax, [rcx+8]
0x18006ee8b  mov     rcx, r15
0x18006ee8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ee93  lea     rcx, [rbx+8]; struct IUnknown **
0x18006ee97  mov     rdx, rsi; void *
0x18006ee9a  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x18006ee9f  mov     [rbx+10h], r12
0x18006eea3  lea     rcx, [rbx+18h]; struct IUnknown **
0x18006eea7  mov     rdx, rdi; void *
0x18006eeaa  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x18006eeaf  mov     ebx, r14d
0x18006eeb2  mov     [rsp+98h+var_68], ebx
0x18006eeb6  jmp     loc_18006EFB1
0x18006eebb  cmp     [rbx], di
0x18006eebe  jbe     short loc_18006EED0
0x18006eec0  cmp     word ptr [rbx], 0Ah
0x18006eec4  jz      short loc_18006EED0
0x18006eec6  mov     ecx, 80070057h; int
0x18006eecb  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x18006eed0  lea     rcx, [r13+78h]; this
0x18006eed4  mov     rdx, r15; struct Atom *
0x18006eed7  call    ?remove@SchemaCacheInfo@@QEAAXPEAVAtom@@@Z; SchemaCacheInfo::remove(Atom *)
0x18006eedc  mov     ebx, r14d
0x18006eedf  mov     [rsp+98h+var_68], ebx
0x18006eee3  jmp     loc_18006EFB1
0x18006eee8  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x18006eeee  call    cs:__imp_TlsGetValue
0x18006eef4  mov     rbx, rax
0x18006eef7  cmp     dword ptr [rax+54h], 0C00000FDh
0x18006eefe  jnz     short loc_18006EF79
0x18006ef00  call    cs:__imp__resetstkoflw
0x18006ef06  test    eax, eax
0x18006ef08  jnz     short loc_18006EF5B
0x18006ef0a  mov     rcx, cs:?g_pMutexGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexGC
0x18006ef11  test    rcx, rcx
0x18006ef14  jz      short loc_18006EF28
0x18006ef16  cmp     [rcx+50h], rbx
0x18006ef1a  jnz     short loc_18006EF28
0x18006ef1c  mov     rax, [rcx]
0x18006ef1f  mov     rax, [rax+20h]
0x18006ef23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ef28  mov     rcx, cs:?g_pMutexFullGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexFullGC
0x18006ef2f  test    rcx, rcx
0x18006ef32  jz      short loc_18006EF46
0x18006ef34  cmp     [rcx+50h], rbx
0x18006ef38  jnz     short loc_18006EF46
0x18006ef3a  mov     rax, [rcx]
0x18006ef3d  mov     rax, [rax+20h]
0x18006ef41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ef46  xor     r9d, r9d; lpArguments
0x18006ef49  xor     r8d, r8d; nNumberOfArguments
0x18006ef4c  xor     edx, edx; dwExceptionFlags
0x18006ef4e  mov     ecx, 0C00000FDh; dwExceptionCode
0x18006ef53  call    cs:__imp_RaiseException
0x18006ef59  jmp     short loc_18006EF79
0x18006ef5b  mov     rax, [rbx+60h]
0x18006ef5f  mov     [rbx+68h], rax
0x18006ef63  lea     rax, ?s_cexpOutOfStack@Exception@@2V_CodebaseException@@B; _CodebaseException const Exception::s_cexpOutOfStack
0x18006ef6a  mov     [rbx+60h], rax
0x18006ef6e  mov     dword ptr [rbx+54h], 800703E9h
0x18006ef75  mov     byte ptr [rbx+78h], 0
0x18006ef79  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x18006ef7f  call    cs:__imp_TlsGetValue
0x18006ef85  mov     rcx, [rax+60h]; struct Exception *
0x18006ef89  call    ?setErrorInfo@_dispatchImpl@@SAPEAVException@@PEAV2@@Z; _dispatchImpl::setErrorInfo(Exception *)
0x18006ef8e  mov     rdx, rax
0x18006ef91  mov     rcx, [rax]
0x18006ef94  mov     rax, [rcx+80h]
0x18006ef9b  mov     rcx, rdx
0x18006ef9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006efa3  mov     ebx, eax
0x18006efa5  mov     [rsp+98h+var_68], eax
0x18006efa9  mov     rsi, [rsp+98h+arg_18]
0x18006efb1  test    rsi, rsi
0x18006efb4  jz      short loc_18006EFC5
0x18006efb6  mov     rax, [rsi]
0x18006efb9  mov     rcx, rsi
0x18006efbc  mov     rax, [rax+10h]
0x18006efc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006efc5  lea     rcx, [rsp+98h+pvargDest]; pvarg
0x18006efca  call    cs:__imp_VariantClear
0x18006efd0  lea     rcx, [rsp+98h+var_58]; struct IUnknown **
0x18006efd5  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x18006efda  mov     eax, ebx
0x18006efdc  lea     r11, [rsp+98h+var_28]
0x18006efe1  mov     rbx, [r11+38h]
0x18006efe5  mov     rsi, [r11+40h]
0x18006efe9  mov     rsp, r11
0x18006efec  pop     r15
0x18006efee  pop     r14
0x18006eff0  pop     r13
0x18006eff2  pop     r12
0x18006eff4  pop     rdi
0x18006eff5  retn
0x18010409a  push    rbp
0x18010409c  sub     rsp, 30h
  ... truncated ...
```
