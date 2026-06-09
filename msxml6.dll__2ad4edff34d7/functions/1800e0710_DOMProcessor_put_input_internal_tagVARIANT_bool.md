# DOMProcessor::put_input_internal(tagVARIANT,bool)

- ea: `0x1800e0710`
- end: `0x1800e098d`
- name: `?put_input_internal@DOMProcessor@@QEAAJUtagVARIANT@@_N@Z`
- size: `637`
- prototype: `__int64 __fastcall(DOMProcessor *this, tagVARIANT *var, bool fInsideWinRT)`
- caller_count: `3`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800d3ec0`
- `0x1800d4060`
- `0x1800e06e0`

## callees

- `0x180009490`
- `0x180025a08`
- `0x18002b064`
- `0x18003f690`
- `0x1800563a0`
- `0x180056464`
- `0x180056bdc`
- `0x180079b10`
- `0x180095704`
- `0x18009f718`
- `0x1800a3e04`
- `0x1800bc3b0`
- `0x1800d65dc`
- `0x1800df8e4`
- `0x1800e0710`
- `0x1800e0af0`
- `0x1800e0b9c`
- `0x180188010`

## import_xrefs

- `OLEAUT32!__imp_VariantCopy` at `0x1800e08df`
- `OLEAUT32!__imp_VariantCopy` at `0x1800e08df`

## pseudocode

```c
__int64 __fastcall DOMProcessor::put_input_internal(DOMProcessor *this, tagVARIANT *var, bool fInsideWinRT)
{
  Node *p; // r14
  Document *v8; // rsi
  bool v9; // r15
  unsigned int v10; // eax
  int v11; // ecx
  IUnknown *Unknown; // rax
  unsigned int v13; // ecx
  HRESULT v14; // eax
  IXMLDOMDocument_vtbl *v15; // rax
  HRESULT v16; // r14d
  DOMProcessor::ProcessState state; // ecx
  __int32 v18; // ecx
  int v19; // r15d
  IXMLDOMDocument *ppDOMDocument; // [rsp+28h] [rbp-60h] BYREF
  Node *eData; // [rsp+30h] [rbp-58h] BYREF
  Document *pDocTemp; // [rsp+38h] [rbp-50h]
  $D748BF15C0FD78A1D5EA62F74D6448CD v23; // [rsp+40h] [rbp-48h] BYREF
  IRecordInfo *pRecInfo; // [rsp+50h] [rbp-38h]
  __int16 isSuccessful; // [rsp+A8h] [rbp+20h] BYREF

  EnsureTls::EnsureTls((EnsureTls *)&eData);
  if ( !eData )
    return 2147500037LL;
  p = 0;
  eData = 0;
  ppDOMDocument = 0;
  isSuccessful = 0;
  v8 = 0;
  pDocTemp = 0;
  v9 = 1;
  LOWORD(v10) = Variant::getBaseType(var);
  if ( (unsigned __int16)v10 > 0xDu )
    goto LABEL_7;
  v11 = 8707;
  if ( !_bittest(&v11, v10) )
    goto LABEL_7;
  Unknown = Variant::getUnknown(var, 0);
  if ( Unknown )
  {
    v9 = GetElement(Unknown, fInsideWinRT, &eData) < 0;
    p = eData;
LABEL_7:
    if ( v9 )
    {
      v8 = Document::newDocument();
      pDocTemp = v8;
      COMSafeControlRoot::copySafeControlRoot(&v8->COMSafeControlRoot, &this->_pTemplate._p->COMSafeControlRoot, 0);
      v8->_dwFlags &= ~2u;
      v13 = v8->_dwFlags & 0xFFFFFFBF;
      v8->_dwFlags = v13;
      v8->_dwFlags = v13 & 0xFFFFFFFB;
      v14 = v8->QueryInterface(v8, &IID_IXMLDOMDocument, (void **)&ppDOMDocument);
      checkhr(v14);
      v15 = ppDOMDocument->__vftable;
      v23 = var->0;
      pRecInfo = var->pRecInfo;
      v16 = ((__int64 (__fastcall *)(IXMLDOMDocument *, $D748BF15C0FD78A1D5EA62F74D6448CD *, __int16 *))v15->load)(
              ppDOMDocument,
              &v23,
              &isSuccessful);
      ppDOMDocument->Release(ppDOMDocument);
      if ( v8->_pParseError._p )
        Exception::throwAgain();
      checkhr(v16);
      p = v8->_pDocNode._p;
      eData = p;
    }
  }
  if ( p )
  {
    state = this->_state;
    if ( state && (v18 = state - 1) != 0 )
    {
      if ( v18 != 4 )
        Exception::throwHR(-1072897495);
      DOMProcessor::resetEvent(this);
    }
    else
    {
      this->_state = Loaded;
    }
  }
  else
  {
    DOMProcessor::clearRequiredEvent(this);
  }
  DOMProcessor::releaseInput(this);
  v19 = VariantCopy(&this->_varInput, var);
  if ( v19 < 0 )
  {
    DOMProcessor::clearRequiredEvent(this);
    checkhr(v19);
  }
  assign(&this->_eInput._p, p);
  if ( v8 )
    v8->Release(v8);
  return 0;
}

```

## disassembly

```asm
0x1800e0710  mov     [rsp+arg_0], rbx
0x1800e0715  mov     [rsp+arg_8], rsi
0x1800e071a  push    rdi
0x1800e071b  push    r12
0x1800e071d  push    r13
0x1800e071f  push    r14
0x1800e0721  push    r15
0x1800e0723  sub     rsp, 60h
0x1800e0727  mov     r13b, fInsideWinRT
0x1800e072a  mov     r12, var
0x1800e072d  mov     rdi, this
0x1800e0730  lea     this, [rsp+88h+eData]; this
0x1800e0735  call    ??0EnsureTls@@QEAA@XZ; EnsureTls::EnsureTls(void)
0x1800e073a  xor     ebx, ebx
0x1800e073c  cmp     [rsp+88h+eData], rbx
0x1800e0741  jnz     short loc_1800E074D
0x1800e0743  mov     eax, 80004005h
0x1800e0748  jmp     loc_1800E0962
0x1800e074d  mov     r14, rbx
0x1800e0750  mov     [rsp+88h+eData], rbx
0x1800e0755  mov     [rsp+88h+ppDOMDocument], rbx
0x1800e075a  mov     [rsp+88h+isSuccessful], bx
0x1800e0762  mov     rsi, rbx
0x1800e0765  mov     [rsp+88h+pDocTemp], rbx
0x1800e076a  mov     r15b, 1
0x1800e076d  mov     this, r12; varObject
0x1800e0770  call    ?getBaseType@Variant@@SAGPEAUtagVARIANT@@@Z; Variant::getBaseType(tagVARIANT *)
0x1800e0775  cmp     ax, 0Dh
0x1800e0779  ja      short loc_1800E07B7
0x1800e077b  mov     ecx, 2203h
0x1800e0780  bt      ecx, eax
0x1800e0783  jnb     short loc_1800E07B7
0x1800e0785  xor     edx, edx; fRequirePtrType
0x1800e0787  mov     this, r12; pVar
0x1800e078a  call    ?getUnknown@Variant@@SAPEAUIUnknown@@PEAUtagVARIANT@@_N@Z; Variant::getUnknown(tagVARIANT *,bool)
0x1800e078f  test    rax, rax
0x1800e0792  jz      loc_1800E0892
0x1800e0798  lea     r8, [rsp+88h+eData]; e
0x1800e079d  mov     dl, r13b; fInsideWinRT
0x1800e07a0  mov     this, rax; p
0x1800e07a3  call    ?GetElement@@YAJPEAUIUnknown@@_NPEAPEAVNode@@@Z; GetElement(IUnknown *,bool,Node * *)
0x1800e07a8  movzx   r15d, r15b
0x1800e07ac  test    eax, eax
0x1800e07ae  cmovns  r15d, ebx
0x1800e07b2  mov     r14, [rsp+88h+eData]
0x1800e07b7  test    r15b, r15b
0x1800e07ba  jz      loc_1800E0892
0x1800e07c0  call    ?newDocument@Document@@SAPEAV1@XZ; Document::newDocument(void)
0x1800e07c5  mov     rsi, rax
0x1800e07c8  mov     [rsp+88h+pDocTemp], rax
0x1800e07cd  mov     var, [rdi+48h]
0x1800e07d1  add     var, 38h ; '8'; saferoot
0x1800e07d5  lea     this, [rax+18h]; this
0x1800e07d9  xor     r8d, r8d; fNewStrings
0x1800e07dc  call    ?copySafeControlRoot@COMSafeControlRoot@@QEAAXAEBV1@_N@Z; COMSafeControlRoot::copySafeControlRoot(COMSafeControlRoot const &,bool)
0x1800e07e1  and     dword ptr [rsi+94h], 0FFFFFFFDh
0x1800e07e8  mov     ecx, [rsi+94h]
0x1800e07ee  and     ecx, 0FFFFFFBFh
0x1800e07f1  mov     [rsi+94h], ecx
0x1800e07f7  and     ecx, 0FFFFFFFBh
0x1800e07fa  mov     [rsi+94h], ecx
0x1800e0800  mov     rax, [rsi]
0x1800e0803  lea     r8, [rsp+88h+ppDOMDocument]
0x1800e0808  lea     var, IID_IXMLDOMDocument
0x1800e080f  mov     this, rsi
0x1800e0812  mov     rax, [rax]
0x1800e0815  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e081a  mov     ecx, eax; hr
0x1800e081c  call    ?checkhr@@YAXJ@Z; checkhr(long)
0x1800e0821  mov     this, [rsp+88h+ppDOMDocument]
0x1800e0826  mov     rax, [this]
0x1800e0829  movaps  xmm0, xmmword ptr [r12]
0x1800e082e  movaps  [rsp+88h+var_48], xmm0
0x1800e0833  movsd   xmm1, qword ptr [r12+10h]
0x1800e083a  movsd   [rsp+88h+var_38], xmm1
0x1800e0840  lea     r8, [rsp+88h+isSuccessful]
0x1800e0848  lea     var, [rsp+88h+var_48]
0x1800e084d  mov     rax, [rax+1D0h]
0x1800e0854  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0859  mov     r14d, eax
0x1800e085c  mov     [rsp+88h+hr], eax
0x1800e0860  mov     this, [rsp+88h+ppDOMDocument]
0x1800e0865  mov     var, [this]
0x1800e0868  mov     rax, [var+10h]
0x1800e086c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0871  cmp     [rsi+0E8h], rbx
0x1800e0878  jnz     loc_1800E097C
0x1800e087e  mov     ecx, r14d; hr
0x1800e0881  call    ?checkhr@@YAXJ@Z; checkhr(long)
0x1800e0886  mov     r14, [rsi+0C8h]
0x1800e088d  mov     [rsp+88h+eData], r14
0x1800e0892  test    r14, r14
0x1800e0895  jz      short loc_1800E08C5
0x1800e0897  mov     ecx, [rdi+0D0h]
0x1800e089d  test    ecx, ecx
0x1800e089f  jz      short loc_1800E08B9
0x1800e08a1  sub     ecx, 1
0x1800e08a4  jz      short loc_1800E08B9
0x1800e08a6  cmp     ecx, 4
0x1800e08a9  jnz     loc_1800E0981
0x1800e08af  mov     this, rdi; this
0x1800e08b2  call    ?resetEvent@DOMProcessor@@IEAAXXZ; DOMProcessor::resetEvent(void)
0x1800e08b7  jmp     short loc_1800E08CD
0x1800e08b9  mov     dword ptr [rdi+0D0h], 1
0x1800e08c3  jmp     short loc_1800E08CD
0x1800e08c5  mov     this, rdi; this
0x1800e08c8  call    ?clearRequiredEvent@DOMProcessor@@IEAAXXZ; DOMProcessor::clearRequiredEvent(void)
0x1800e08cd  mov     this, rdi; this
0x1800e08d0  call    ?releaseInput@DOMProcessor@@IEAAXXZ; DOMProcessor::releaseInput(void)
0x1800e08d5  lea     this, [rdi+0A8h]; pvargDest
0x1800e08dc  mov     var, r12; pvargSrc
0x1800e08df  call    cs:__imp_VariantCopy
0x1800e08e5  mov     r15d, eax
0x1800e08e8  mov     [rsp+88h+hr], eax
0x1800e08ec  test    eax, eax
0x1800e08ee  jns     short loc_1800E0900
0x1800e08f0  mov     this, rdi; this
0x1800e08f3  call    ?clearRequiredEvent@DOMProcessor@@IEAAXXZ; DOMProcessor::clearRequiredEvent(void)
0x1800e08f8  mov     ecx, r15d; hr
0x1800e08fb  call    ?checkhr@@YAXJ@Z; checkhr(long)
0x1800e0900  lea     this, [rdi+0A0h]; ppref
0x1800e0907  mov     var, r14; pref
0x1800e090a  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800e090f  mov     edi, ebx
0x1800e0911  mov     [rsp+88h+hr], ebx
0x1800e0915  jmp     short loc_1800E094C
0x1800e0917  call    ?exceptionCatch@Exception@@SAXXZ; Exception::exceptionCatch(void)
0x1800e091c  mov     ecx, cs:_tls_index
0x1800e0922  mov     rax, gs:58h
0x1800e092b  mov     edx, 8
0x1800e0930  mov     rax, [rax+this*8]
0x1800e0934  mov     this, [rax+var]
0x1800e0938  mov     this, [this+8]; e
0x1800e093c  call    ?setErrorInfoAndGetHR@_dispatchImpl@@SAJPEAVException@@@Z; _dispatchImpl::setErrorInfoAndGetHR(Exception *)
0x1800e0941  mov     edi, eax
0x1800e0943  mov     [rsp+88h+hr], eax
0x1800e0947  mov     rsi, [rsp+88h+pDocTemp]
0x1800e094c  test    rsi, rsi
0x1800e094f  jz      short loc_1800E0960
0x1800e0951  mov     this, [rsi]
0x1800e0954  mov     rax, [this+10h]
0x1800e0958  mov     this, rsi
0x1800e095b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0960  mov     eax, edi
0x1800e0962  lea     r11, [rsp+88h+var_28]
0x1800e0967  mov     rbx, [r11+30h]
0x1800e096b  mov     rsi, [r11+38h]
0x1800e096f  mov     rsp, r11
0x1800e0972  pop     r15
0x1800e0974  pop     r14
0x1800e0976  pop     r13
0x1800e0978  pop     r12
0x1800e097a  pop     rdi
0x1800e097b  retn
0x1800e097c  call    ?throwAgain@Exception@@SAXXZ; Exception::throwAgain(void)
0x1800e0981  mov     ecx, 0C00CE229h; hr
0x1800e0986  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x18017de3a  push    rbp
0x18017de3c  sub     rsp, 20h
0x18017de40  mov     rbp, rdx
0x18017de43  call    ?fillException@Exception@@SAHPEAU_EXCEPTION_POINTERS@@@Z
0x18017de48  nop
0x18017de49  add     rsp, 20h
0x18017de4d  pop     rbp
0x18017de4e  retn
```
