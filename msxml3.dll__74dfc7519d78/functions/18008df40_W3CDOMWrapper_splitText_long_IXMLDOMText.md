# W3CDOMWrapper::splitText(long,IXMLDOMText * *)

- ea: `0x18008df40`
- end: `0x18008e28b`
- name: `?splitText@W3CDOMWrapper@@UEAAJJPEAPEAUIXMLDOMText@@@Z`
- size: `843`
- prototype: `int(W3CDOMWrapper *__hidden this, int, struct IXMLDOMText **)`
- caller_count: `0`
- callee_count: `19`
- tags: `reparse_path, registry_config, installer_update`

## callees

- `0x1800105fc`
- `0x18001b690`
- `0x180022aec`
- `0x1800249f8`
- `0x1800251c4`
- `0x1800265f4`
- `0x180026ad0`
- `0x180026d84`
- `0x180026e00`
- `0x180036da8`
- `0x180043e60`
- `0x18004d4dc`
- `0x18004ebf0`
- `0x18005f9b8`
- `0x180064034`
- `0x18008a770`
- `0x18008a99c`
- `0x18008df40`
- `0x180107010`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x18008e185`
- `msvcrt!_resetstkoflw` at `0x18008e185`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008e1d8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008e1d8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18008e173`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18008e204`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18008e173`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18008e204`

## pseudocode

```c
__int64 __fastcall W3CDOMWrapper::splitText(struct DOMNode **this, int a2, struct IXMLDOMText **a3)
{
  struct TLSDATA *v6; // rcx
  unsigned int v8; // esi
  __int64 v9; // r14
  struct String *InnerTextPreserve; // rax
  const unsigned __int16 *v11; // r13
  int v12; // r12d
  W3CDOMWrapper *v13; // rcx
  int NormalizedLength; // eax
  W3CDOMWrapper *v15; // rcx
  int v16; // r9d
  int ActualLength; // eax
  __int64 v18; // rdi
  __int64 v19; // rax
  struct DOMNode *DOMNodeWrapper; // rbx
  struct String *v21; // rax
  Node *v22; // rdi
  struct Node *NextSibling; // rax
  Node *v24; // [rsp+28h] [rbp-60h]
  struct ArrayString *v25; // [rsp+30h] [rbp-58h]
  _BYTE v26[40]; // [rsp+38h] [rbp-50h] BYREF
  struct TLSDATA *v27; // [rsp+A8h] [rbp+20h] BYREF

  EnsureTls::EnsureTls((EnsureTls *)&v27);
  if ( !v27 )
  {
    v6 = 0;
LABEL_3:
    ((void (__fastcall *)(struct TLSDATA *))g_pfnExit)(v6);
    return 2147500037LL;
  }
  OMWriteLock::OMWriteLock((OMWriteLock *)v26, v27, this[7]);
  if ( DocumentLock::lockFailedErrorInfo((DocumentLock *)v26) )
  {
    OMWriteLock::~OMWriteLock((OMWriteLock *)v26);
    v6 = v27;
    goto LABEL_3;
  }
  if ( a2 < 0 )
    goto LABEL_7;
  if ( !a3 )
  {
    OMWriteLock::~OMWriteLock((OMWriteLock *)v26);
    ((void (__fastcall *)(struct TLSDATA *))g_pfnExit)(v27);
    return 2147942487LL;
  }
  v8 = 1;
  *a3 = 0;
  v9 = *((_QWORD *)this[7] + 7);
  Node::checkReadOnly((Node *)v9);
  InnerTextPreserve = Node::getInnerTextPreserve((Node *)v9, 0);
  v11 = (const unsigned __int16 *)*((_QWORD *)InnerTextPreserve + 3);
  v12 = *((_DWORD *)InnerTextPreserve + 4);
  NormalizedLength = W3CDOMWrapper::_getNormalizedLength(v13, v11, v12, v12);
  if ( a2 > NormalizedLength )
  {
LABEL_7:
    _dispatchImpl::setErrorInfo(-1072897512);
    v8 = -2147024809;
  }
  else if ( NormalizedLength && a2 != NormalizedLength )
  {
    ActualLength = W3CDOMWrapper::_getActualLength(v15, v11, a2, v16);
    v18 = ActualLength;
    v25 = ArrayString::newString(v11, ActualLength);
    v19 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 400LL))(v9);
    v24 = (Node *)Node::newNode(*(_BYTE *)(v9 + 19) & 0x1F, 0, v19, *(_QWORD *)(v19 + 256));
    DOMNodeWrapper = Node::getDOMNodeWrapper(v24);
    v8 = (**(__int64 (__fastcall ***)(struct DOMNode *, GUID *, struct IXMLDOMText **))DOMNodeWrapper)(
           DOMNodeWrapper,
           &IID_IXMLDOMText,
           a3);
    (*(void (__fastcall **)(struct DOMNode *))(*(_QWORD *)DOMNodeWrapper + 16LL))(DOMNodeWrapper);
    v21 = ArrayString::newString(&v11[v18], v12 - (int)v18);
    Node::setInnerText(v24, v21, 0);
    v22 = (Node *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 568LL))(v9);
    if ( v22 )
    {
      NextSibling = Node::getNextSibling((Node *)v9);
      Node::_insert(v22, v24, NextSibling);
    }
    Node::setInnerText((Node *)v9, v25, 0);
  }
  OMWriteLock::~OMWriteLock((OMWriteLock *)v26);
  ((void (__fastcall *)(struct TLSDATA *))g_pfnExit)(v27);
  return v8;
}

```

## disassembly

```asm
0x18008df40  mov     rax, rsp
0x18008df43  mov     [rax+8], rbx
0x18008df47  mov     [rax+10h], rsi
0x18008df4b  mov     [rax+18h], r8
0x18008df4f  push    rdi
0x18008df50  push    r12
0x18008df52  push    r13
0x18008df54  push    r14
0x18008df56  push    r15
0x18008df58  sub     rsp, 60h
0x18008df5c  mov     r15, r8
0x18008df5f  mov     ebx, edx
0x18008df61  mov     rdi, rcx
0x18008df64  lea     rcx, [rax+20h]; this
0x18008df68  call    ??0EnsureTls@@QEAA@XZ; EnsureTls::EnsureTls(void)
0x18008df6d  cmp     [rsp+88h+arg_18], 0
0x18008df76  jnz     short loc_18008DF90
0x18008df78  xor     ecx, ecx
0x18008df7a  mov     rax, cs:?g_pfnExit@@3P6AXPEAUTLSDATA@@@ZEA; void (*g_pfnExit)(TLSDATA *)
0x18008df81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008df86  mov     eax, 80004005h
0x18008df8b  jmp     loc_18008E271
0x18008df90  mov     r8, [rdi+38h]; struct DOMNode *
0x18008df94  mov     rdx, [rsp+88h+arg_18]; struct TLSDATA *
0x18008df9c  lea     rcx, [rsp+88h+var_50]; this
0x18008dfa1  call    ??0OMWriteLock@@QEAA@PEAUTLSDATA@@PEAVDOMNode@@@Z; OMWriteLock::OMWriteLock(TLSDATA *,DOMNode *)
0x18008dfa6  lea     rcx, [rsp+88h+var_50]; this
0x18008dfab  call    ?lockFailedErrorInfo@DocumentLock@@QEAA_NXZ; DocumentLock::lockFailedErrorInfo(void)
0x18008dfb0  test    al, al
0x18008dfb2  jz      short loc_18008DFC8
0x18008dfb4  lea     rcx, [rsp+88h+var_50]; this
0x18008dfb9  call    ??1OMWriteLock@@QEAA@XZ; OMWriteLock::~OMWriteLock(void)
0x18008dfbe  mov     rcx, [rsp+88h+arg_18]
0x18008dfc6  jmp     short loc_18008DF7A
0x18008dfc8  test    ebx, ebx
0x18008dfca  jns     short loc_18008DFE0
0x18008dfcc  mov     ecx, 0C00CE218h; int
0x18008dfd1  call    ?setErrorInfo@_dispatchImpl@@SAXJ@Z; _dispatchImpl::setErrorInfo(long)
0x18008dfd6  mov     esi, 80070057h
0x18008dfdb  jmp     loc_18008E251
0x18008dfe0  test    r15, r15
0x18008dfe3  jnz     short loc_18008E00D
0x18008dfe5  lea     rcx, [rsp+88h+var_50]; this
0x18008dfea  call    ??1OMWriteLock@@QEAA@XZ; OMWriteLock::~OMWriteLock(void)
0x18008dfef  mov     rcx, [rsp+88h+arg_18]
0x18008dff7  mov     rax, cs:?g_pfnExit@@3P6AXPEAUTLSDATA@@@ZEA; void (*g_pfnExit)(TLSDATA *)
0x18008dffe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e003  mov     eax, 80070057h
0x18008e008  jmp     loc_18008E271
0x18008e00d  mov     esi, 1
0x18008e012  mov     qword ptr [r15], 0
0x18008e019  mov     rax, [rdi+38h]
0x18008e01d  mov     r14, [rax+38h]
0x18008e021  mov     rcx, r14; this
0x18008e024  call    ?checkReadOnly@Node@@QEAA_NXZ; Node::checkReadOnly(void)
0x18008e029  xor     edx, edx; bool
0x18008e02b  mov     rcx, r14; this
0x18008e02e  call    ?getInnerTextPreserve@Node@@QEAAPEAVString@@_N@Z; Node::getInnerTextPreserve(bool)
0x18008e033  mov     r13, [rax+18h]
0x18008e037  mov     r12d, [rax+10h]
0x18008e03b  mov     r9d, r12d; int
0x18008e03e  mov     r8d, r12d; int
0x18008e041  mov     rdx, r13; unsigned __int16 *
0x18008e044  call    ?_getNormalizedLength@W3CDOMWrapper@@AEAAHPEBGHH@Z; W3CDOMWrapper::_getNormalizedLength(ushort const *,int,int)
0x18008e049  cmp     ebx, eax
0x18008e04b  jle     short loc_18008E065
0x18008e04d  mov     ecx, 0C00CE218h; int
0x18008e052  call    ?setErrorInfo@_dispatchImpl@@SAXJ@Z; _dispatchImpl::setErrorInfo(long)
0x18008e057  mov     esi, 80070057h
0x18008e05c  mov     [rsp+88h+var_68], esi
0x18008e060  jmp     loc_18008E251
0x18008e065  test    eax, eax
0x18008e067  jz      loc_18008E168
0x18008e06d  cmp     ebx, eax
0x18008e06f  jz      loc_18008E168
0x18008e075  mov     r8d, ebx; int
0x18008e078  mov     rdx, r13; unsigned __int16 *
0x18008e07b  call    ?_getActualLength@W3CDOMWrapper@@AEAAHPEBGHH@Z; W3CDOMWrapper::_getActualLength(ushort const *,int,int)
0x18008e080  movsxd  rdi, eax
0x18008e083  mov     edx, edi; int
0x18008e085  mov     rcx, r13; Src
0x18008e088  call    ?newString@ArrayString@@SAPEAV1@PEBGH@Z; ArrayString::newString(ushort const *,int)
0x18008e08d  mov     [rsp+88h+var_58], rax
0x18008e092  mov     rcx, [r14]
0x18008e095  mov     rax, [rcx+190h]
0x18008e09c  mov     rcx, r14
0x18008e09f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e0a4  movzx   ecx, byte ptr [r14+13h]
0x18008e0a9  and     ecx, 1Fh
0x18008e0ac  mov     r9, [rax+100h]
0x18008e0b3  mov     r8, rax
0x18008e0b6  xor     edx, edx
0x18008e0b8  call    ?newNode@Node@@SAPEAV1@W4NodeType@Element@@PEAVNameDef@@PEAVDocument@@PEAVNodeManager@@@Z; Node::newNode(Element::NodeType,NameDef *,Document *,NodeManager *)
0x18008e0bd  mov     [rsp+88h+var_60], rax
0x18008e0c2  mov     rcx, rax; this
0x18008e0c5  call    ?getDOMNodeWrapper@Node@@QEAAPEAVDOMNode@@XZ; Node::getDOMNodeWrapper(void)
0x18008e0ca  mov     rbx, rax
0x18008e0cd  mov     rcx, [rax]
0x18008e0d0  mov     rax, [rcx]
0x18008e0d3  mov     r8, r15
0x18008e0d6  lea     rdx, IID_IXMLDOMText
0x18008e0dd  mov     rcx, rbx
0x18008e0e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e0e5  mov     esi, eax
0x18008e0e7  mov     [rsp+88h+var_68], eax
0x18008e0eb  mov     rcx, [rbx]
0x18008e0ee  mov     rax, [rcx+10h]
0x18008e0f2  mov     rcx, rbx
0x18008e0f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e0fa  sub     r12d, edi
0x18008e0fd  lea     rcx, ds:0[rdi*2]
0x18008e105  add     rcx, r13; Src
0x18008e108  mov     edx, r12d; int
0x18008e10b  call    ?newString@ArrayString@@SAPEAV1@PEBGH@Z; ArrayString::newString(ushort const *,int)
0x18008e110  xor     r8d, r8d; bool
0x18008e113  mov     rdx, rax; struct String *
0x18008e116  mov     rbx, [rsp+88h+var_60]
0x18008e11b  mov     rcx, rbx; this
0x18008e11e  call    ?setInnerText@Node@@QEAAXPEAVString@@_N@Z; Node::setInnerText(String *,bool)
0x18008e123  mov     rax, [r14]
0x18008e126  mov     rcx, r14
0x18008e129  mov     rax, [rax+238h]
0x18008e130  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e135  mov     rdi, rax
0x18008e138  test    rax, rax
0x18008e13b  jz      short loc_18008E153
0x18008e13d  mov     rcx, r14; this
0x18008e140  call    ?getNextSibling@Node@@QEAAPEAV1@XZ; Node::getNextSibling(void)
0x18008e145  mov     r8, rax; struct Node *
0x18008e148  mov     rdx, rbx; struct Node *
0x18008e14b  mov     rcx, rdi; this
0x18008e14e  call    ?_insert@Node@@QEAAXPEAV1@0@Z; Node::_insert(Node *,Node *)
0x18008e153  xor     r8d, r8d; bool
0x18008e156  mov     rdx, [rsp+88h+var_58]; struct String *
0x18008e15b  mov     rcx, r14; this
0x18008e15e  call    ?setInnerText@Node@@QEAAXPEAVString@@_N@Z; Node::setInnerText(String *,bool)
0x18008e163  jmp     loc_18008E251
0x18008e168  jmp     loc_18008E251
0x18008e16d  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x18008e173  call    cs:__imp_TlsGetValue
0x18008e179  mov     rbx, rax
0x18008e17c  cmp     dword ptr [rax+54h], 0C00000FDh
0x18008e183  jnz     short loc_18008E1FE
0x18008e185  call    cs:__imp__resetstkoflw
0x18008e18b  test    eax, eax
0x18008e18d  jnz     short loc_18008E1E0
0x18008e18f  mov     rcx, cs:?g_pMutexGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexGC
0x18008e196  test    rcx, rcx
0x18008e199  jz      short loc_18008E1AD
0x18008e19b  cmp     [rcx+50h], rbx
0x18008e19f  jnz     short loc_18008E1AD
0x18008e1a1  mov     rax, [rcx]
0x18008e1a4  mov     rax, [rax+20h]
0x18008e1a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e1ad  mov     rcx, cs:?g_pMutexFullGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexFullGC
0x18008e1b4  test    rcx, rcx
0x18008e1b7  jz      short loc_18008E1CB
0x18008e1b9  cmp     [rcx+50h], rbx
0x18008e1bd  jnz     short loc_18008E1CB
0x18008e1bf  mov     rax, [rcx]
0x18008e1c2  mov     rax, [rax+20h]
0x18008e1c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e1cb  xor     r9d, r9d; lpArguments
0x18008e1ce  xor     r8d, r8d; nNumberOfArguments
0x18008e1d1  xor     edx, edx; dwExceptionFlags
0x18008e1d3  mov     ecx, 0C00000FDh; dwExceptionCode
0x18008e1d8  call    cs:__imp_RaiseException
0x18008e1de  jmp     short loc_18008E1FE
0x18008e1e0  mov     rax, [rbx+60h]
0x18008e1e4  mov     [rbx+68h], rax
0x18008e1e8  lea     rax, ?s_cexpOutOfStack@Exception@@2V_CodebaseException@@B; _CodebaseException const Exception::s_cexpOutOfStack
0x18008e1ef  mov     [rbx+60h], rax
0x18008e1f3  mov     dword ptr [rbx+54h], 800703E9h
0x18008e1fa  mov     byte ptr [rbx+78h], 0
0x18008e1fe  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x18008e204  call    cs:__imp_TlsGetValue
0x18008e20a  mov     rcx, [rax+60h]; struct Exception *
0x18008e20e  call    ?setErrorInfo@_dispatchImpl@@SAPEAVException@@PEAV2@@Z; _dispatchImpl::setErrorInfo(Exception *)
0x18008e213  mov     rdx, rax
0x18008e216  mov     rcx, [rax]
0x18008e219  mov     rax, [rcx+80h]
0x18008e220  mov     rcx, rdx
0x18008e223  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e228  mov     esi, eax
0x18008e22a  mov     [rsp+88h+var_68], eax
0x18008e22e  mov     rbx, [rsp+88h+arg_10]
0x18008e236  mov     rcx, [rbx]
0x18008e239  test    rcx, rcx
0x18008e23c  jz      short loc_18008E251
0x18008e23e  mov     rax, [rcx]
0x18008e241  mov     rax, [rax+10h]
0x18008e245  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e24a  mov     qword ptr [rbx], 0
0x18008e251  lea     rcx, [rsp+88h+var_50]; this
0x18008e256  call    ??1OMWriteLock@@QEAA@XZ; OMWriteLock::~OMWriteLock(void)
0x18008e25b  mov     rcx, [rsp+88h+arg_18]
0x18008e263  mov     rax, cs:?g_pfnExit@@3P6AXPEAUTLSDATA@@@ZEA; void (*g_pfnExit)(TLSDATA *)
0x18008e26a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e26f  mov     eax, esi
0x18008e271  lea     r11, [rsp+88h+var_28]
0x18008e276  mov     rbx, [r11+30h]
0x18008e27a  mov     rsi, [r11+38h]
0x18008e27e  mov     rsp, r11
0x18008e281  pop     r15
0x18008e283  pop     r14
0x18008e285  pop     r13
0x18008e287  pop     r12
0x18008e289  pop     rdi
0x18008e28a  retn
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
