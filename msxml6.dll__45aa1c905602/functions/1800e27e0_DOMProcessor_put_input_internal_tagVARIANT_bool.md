# DOMProcessor::put_input_internal(tagVARIANT,bool)

- ea: `0x1800e27e0`
- end: `0x1800e2a64`
- name: `?put_input_internal@DOMProcessor@@QEAAJUtagVARIANT@@_N@Z`
- size: `644`
- prototype: `HRESULT __fastcall(DOMProcessor *this, tagVARIANT var, bool fInsideWinRT)`
- caller_count: `3`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800d5ad0`
- `0x1800d5c70`
- `0x1800e27b0`

## callees

- `0x180015a80`
- `0x180032de8`
- `0x180037830`
- `0x18003a79c`
- `0x180058ef4`
- `0x180078e98`
- `0x18007a804`
- `0x18009402c`
- `0x18009545c`
- `0x18009fefc`
- `0x1800a3c08`
- `0x1800bda08`
- `0x1800d82c0`
- `0x1800e1960`
- `0x1800e27e0`
- `0x1800e2bc0`
- `0x1800e2c70`
- `0x18018c010`

## import_xrefs

- `OLEAUT32!__imp_VariantCopy` at `0x1800e29af`
- `OLEAUT32!__imp_VariantCopy` at `0x1800e29af`

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
  $BE4DFD8530E26B14EE6F3813E010A638 v23; // [rsp+40h] [rbp-48h] BYREF
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
      v16 = ((__int64 (__fastcall *)(IXMLDOMDocument *, $BE4DFD8530E26B14EE6F3813E010A638 *, __int16 *))v15->load)(
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
0x1800e27e0  mov     [rsp+arg_0], rbx
0x1800e27e5  mov     [rsp+arg_8], rsi
0x1800e27ea  push    rdi
0x1800e27eb  push    r12
0x1800e27ed  push    r13
0x1800e27ef  push    r14
0x1800e27f1  push    r15
0x1800e27f3  sub     rsp, 60h
0x1800e27f7  mov     r13b, fInsideWinRT
0x1800e27fa  mov     r12, var
0x1800e27fd  mov     rdi, this
0x1800e2800  lea     this, [rsp+88h+eData]; this
0x1800e2805  call    ??0EnsureTls@@QEAA@XZ; EnsureTls::EnsureTls(void)
0x1800e280a  xor     ebx, ebx
0x1800e280c  cmp     [rsp+88h+eData], rbx
0x1800e2811  jnz     short loc_1800E281D
0x1800e2813  mov     eax, 80004005h
0x1800e2818  jmp     loc_1800E2A38
0x1800e281d  mov     r14, rbx
0x1800e2820  mov     [rsp+88h+eData], rbx
0x1800e2825  mov     [rsp+88h+ppDOMDocument], rbx
0x1800e282a  mov     [rsp+88h+isSuccessful], bx
0x1800e2832  mov     rsi, rbx
0x1800e2835  mov     [rsp+88h+pDocTemp], rbx
0x1800e283a  mov     r15b, 1
0x1800e283d  mov     this, r12; varObject
0x1800e2840  call    ?getBaseType@Variant@@SAGPEAUtagVARIANT@@@Z; Variant::getBaseType(tagVARIANT *)
0x1800e2845  cmp     ax, 0Dh
0x1800e2849  ja      short loc_1800E2887
0x1800e284b  mov     ecx, 2203h
0x1800e2850  bt      ecx, eax
0x1800e2853  jnb     short loc_1800E2887
0x1800e2855  xor     edx, edx; fRequirePtrType
0x1800e2857  mov     this, r12; pVar
0x1800e285a  call    ?getUnknown@Variant@@SAPEAUIUnknown@@PEAUtagVARIANT@@_N@Z; Variant::getUnknown(tagVARIANT *,bool)
0x1800e285f  test    rax, rax
0x1800e2862  jz      loc_1800E2962
0x1800e2868  lea     r8, [rsp+88h+eData]; e
0x1800e286d  mov     dl, r13b; fInsideWinRT
0x1800e2870  mov     this, rax; p
0x1800e2873  call    ?GetElement@@YAJPEAUIUnknown@@_NPEAPEAVNode@@@Z; GetElement(IUnknown *,bool,Node * *)
0x1800e2878  movzx   r15d, r15b
0x1800e287c  test    eax, eax
0x1800e287e  cmovns  r15d, ebx
0x1800e2882  mov     r14, [rsp+88h+eData]
0x1800e2887  test    r15b, r15b
0x1800e288a  jz      loc_1800E2962
0x1800e2890  call    ?newDocument@Document@@SAPEAV1@XZ; Document::newDocument(void)
0x1800e2895  mov     rsi, rax
0x1800e2898  mov     [rsp+88h+pDocTemp], rax
0x1800e289d  mov     var, [rdi+48h]
0x1800e28a1  add     var, 38h ; '8'; saferoot
0x1800e28a5  lea     this, [rax+18h]; this
0x1800e28a9  xor     r8d, r8d; fNewStrings
0x1800e28ac  call    ?copySafeControlRoot@COMSafeControlRoot@@QEAAXAEBV1@_N@Z; COMSafeControlRoot::copySafeControlRoot(COMSafeControlRoot const &,bool)
0x1800e28b1  and     dword ptr [rsi+94h], 0FFFFFFFDh
0x1800e28b8  mov     ecx, [rsi+94h]
0x1800e28be  and     ecx, 0FFFFFFBFh
0x1800e28c1  mov     [rsi+94h], ecx
0x1800e28c7  and     ecx, 0FFFFFFFBh
0x1800e28ca  mov     [rsi+94h], ecx
0x1800e28d0  mov     rax, [rsi]
0x1800e28d3  lea     r8, [rsp+88h+ppDOMDocument]
0x1800e28d8  lea     var, IID_IXMLDOMDocument
0x1800e28df  mov     this, rsi
0x1800e28e2  mov     rax, [rax]
0x1800e28e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e28ea  mov     ecx, eax; hr
0x1800e28ec  call    ?checkhr@@YAXJ@Z; checkhr(long)
0x1800e28f1  mov     this, [rsp+88h+ppDOMDocument]
0x1800e28f6  mov     rax, [this]
0x1800e28f9  movaps  xmm0, xmmword ptr [r12]
0x1800e28fe  movaps  [rsp+88h+var_48], xmm0
0x1800e2903  movsd   xmm1, qword ptr [r12+10h]
0x1800e290a  movsd   [rsp+88h+var_38], xmm1
0x1800e2910  lea     r8, [rsp+88h+isSuccessful]
0x1800e2918  lea     var, [rsp+88h+var_48]
0x1800e291d  mov     rax, [rax+1D0h]
0x1800e2924  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2929  mov     r14d, eax
0x1800e292c  mov     [rsp+88h+hr], eax
0x1800e2930  mov     this, [rsp+88h+ppDOMDocument]
0x1800e2935  mov     var, [this]
0x1800e2938  mov     rax, [var+10h]
0x1800e293c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2941  cmp     [rsi+0E8h], rbx
0x1800e2948  jnz     loc_1800E2A53
0x1800e294e  mov     ecx, r14d; hr
0x1800e2951  call    ?checkhr@@YAXJ@Z; checkhr(long)
0x1800e2956  mov     r14, [rsi+0C8h]
0x1800e295d  mov     [rsp+88h+eData], r14
0x1800e2962  test    r14, r14
0x1800e2965  jz      short loc_1800E2995
0x1800e2967  mov     ecx, [rdi+0D0h]
0x1800e296d  test    ecx, ecx
0x1800e296f  jz      short loc_1800E2989
0x1800e2971  sub     ecx, 1
0x1800e2974  jz      short loc_1800E2989
0x1800e2976  cmp     ecx, 4
0x1800e2979  jnz     loc_1800E2A58
0x1800e297f  mov     this, rdi; this
0x1800e2982  call    ?resetEvent@DOMProcessor@@IEAAXXZ; DOMProcessor::resetEvent(void)
0x1800e2987  jmp     short loc_1800E299D
0x1800e2989  mov     dword ptr [rdi+0D0h], 1
0x1800e2993  jmp     short loc_1800E299D
0x1800e2995  mov     this, rdi; this
0x1800e2998  call    ?clearRequiredEvent@DOMProcessor@@IEAAXXZ; DOMProcessor::clearRequiredEvent(void)
0x1800e299d  mov     this, rdi; this
0x1800e29a0  call    ?releaseInput@DOMProcessor@@IEAAXXZ; DOMProcessor::releaseInput(void)
0x1800e29a5  lea     this, [rdi+0A8h]; pvargDest
0x1800e29ac  mov     var, r12; pvargSrc
0x1800e29af  call    cs:__imp_VariantCopy
0x1800e29b6  nop     dword ptr [rax+rax+00h]
0x1800e29bb  mov     r15d, eax
0x1800e29be  mov     [rsp+88h+hr], eax
0x1800e29c2  test    eax, eax
0x1800e29c4  jns     short loc_1800E29D6
0x1800e29c6  mov     this, rdi; this
0x1800e29c9  call    ?clearRequiredEvent@DOMProcessor@@IEAAXXZ; DOMProcessor::clearRequiredEvent(void)
0x1800e29ce  mov     ecx, r15d; hr
0x1800e29d1  call    ?checkhr@@YAXJ@Z; checkhr(long)
0x1800e29d6  lea     this, [rdi+0A0h]; ppref
0x1800e29dd  mov     var, r14; pref
0x1800e29e0  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800e29e5  mov     edi, ebx
0x1800e29e7  mov     [rsp+88h+hr], ebx
0x1800e29eb  jmp     short loc_1800E2A22
0x1800e29ed  call    ?exceptionCatch@Exception@@SAXXZ; Exception::exceptionCatch(void)
0x1800e29f2  mov     ecx, cs:_tls_index
0x1800e29f8  mov     rax, gs:58h
0x1800e2a01  mov     edx, 8
0x1800e2a06  mov     rax, [rax+this*8]
0x1800e2a0a  mov     this, [rax+var]
0x1800e2a0e  mov     this, [this+8]; e
0x1800e2a12  call    ?setErrorInfoAndGetHR@_dispatchImpl@@SAJPEAVException@@@Z; _dispatchImpl::setErrorInfoAndGetHR(Exception *)
0x1800e2a17  mov     edi, eax
0x1800e2a19  mov     [rsp+88h+hr], eax
0x1800e2a1d  mov     rsi, [rsp+88h+pDocTemp]
0x1800e2a22  test    rsi, rsi
0x1800e2a25  jz      short loc_1800E2A36
0x1800e2a27  mov     this, [rsi]
0x1800e2a2a  mov     rax, [this+10h]
0x1800e2a2e  mov     this, rsi
0x1800e2a31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2a36  mov     eax, edi
0x1800e2a38  lea     r11, [rsp+88h+var_28]
0x1800e2a3d  mov     rbx, [r11+30h]
0x1800e2a41  mov     rsi, [r11+38h]
0x1800e2a45  mov     rsp, r11
0x1800e2a48  pop     r15
0x1800e2a4a  pop     r14
0x1800e2a4c  pop     r13
0x1800e2a4e  pop     r12
0x1800e2a50  pop     rdi
0x1800e2a51  retn
0x1800e2a53  call    ?throwAgain@Exception@@SAXXZ; Exception::throwAgain(void)
0x1800e2a58  mov     ecx, 0C00CE229h; hr
0x1800e2a5d  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x18018197e  push    rbp
0x180181980  sub     rsp, 20h
0x180181984  mov     rbp, rdx
0x180181987  call    ?fillException@Exception@@SAHPEAU_EXCEPTION_POINTERS@@@Z
0x18018198c  nop
0x18018198d  add     rsp, 20h
0x180181991  pop     rbp
0x180181992  retn
```
