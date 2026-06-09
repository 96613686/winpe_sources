# SAXReader::parse(tagVARIANT)

- ea: `0x180099350`
- end: `0x18009955b`
- name: `?parse@SAXReader@@UEAAJUtagVARIANT@@@Z`
- size: `523`
- prototype: `HRESULT __fastcall(SAXReader *this, tagVARIANT varInput)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180015a80`
- `0x18003a4a0`
- `0x180078d60`
- `0x180078e98`
- `0x180099350`
- `0x18009fefc`
- `0x1800a3c08`
- `0x180125994`
- `0x18018c010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180099537`
- `OLEAUT32!__imp_VariantClear` at `0x180099537`
- `OLEAUT32!__imp_VariantCopy` at `0x1800993db`
- `OLEAUT32!__imp_VariantCopy` at `0x1800993db`

## pseudocode

```c
__int64 __fastcall SAXReader::parse(SAXReader *this, tagVARIANT *varInput)
{
  Node *v5; // r15
  char v6; // r14
  HRESULT DTSReader; // ebx
  IUnknown *Unknown; // rax
  IUnknown *v9; // rbx
  Object *ObjectFromIUnk; // rax
  tagVARIANT v11; // [rsp+30h] [rbp-48h] BYREF

  if ( !(__int64)g_pfnEntry() )
    return 2147500037LL;
  v5 = 0;
  v6 = 0;
  if ( this->_fBusy )
  {
    DTSReader = -2147467259;
  }
  else
  {
    if ( this->_securitySetting != AllowNone )
    {
      if ( varInput->vt <= 1u || varInput->vt == 10 )
      {
        DTSReader = VariantCopy(varInput, &this->_varInput);
        if ( DTSReader < 0 )
          goto $CleanUp_120;
        v6 = 1;
      }
      Unknown = Variant::getUnknown(varInput, 0);
      v9 = Unknown;
      if ( Unknown )
      {
        ObjectFromIUnk = Object::getObjectFromIUnk(Unknown, &IID_Document, 0);
        if ( ObjectFromIUnk )
          v5 = (Node *)ObjectFromIUnk[25].__vftable;
        else
          v5 = (Node *)Object::getObjectFromIUnk(v9, &IID_Node, 0);
      }
      if ( v5 )
      {
        assign(&this->_pDtsReader._p, 0);
        DTSReader = SAXReader::CreateDTSReader(this, &this->_pDtsReader._p);
        if ( DTSReader < 0 )
          goto $CleanUp_120;
        this->_fBusy = 1;
        DTSReader = this->_pDtsReader._p->traverse(this->_pDtsReader._p, v5);
        assign(&this->_pDtsReader._p, 0);
      }
      else
      {
        this->_fBusy = 1;
        v11 = *varInput;
        DTSReader = Reader::parse(this, &v11);
      }
      this->_fBusy = 0;
      goto $CleanUp_120;
    }
    DTSReader = -2147024891;
  }
$CleanUp_120:
  if ( v6 )
    VariantClear(varInput);
  return (unsigned int)DTSReader;
}

```

## disassembly

```asm
0x180099350  mov     [rsp+arg_10], rbx
0x180099355  mov     [rsp+arg_8], varInput
0x18009935a  mov     [rsp+arg_0], this
0x18009935f  push    rsi
0x180099360  push    rdi
0x180099361  push    r12
0x180099363  push    r14
0x180099365  push    r15
0x180099367  sub     rsp, 50h
0x18009936b  mov     rsi, varInput
0x18009936e  mov     rdi, this
0x180099371  mov     rax, cs:?g_pfnEntry@@3P6APEAUTLSDATA@@XZEA; TLSDATA * (*g_pfnEntry)(void)
0x180099378  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009937d  test    rax, rax
0x180099380  jnz     short loc_18009938C
0x180099382  mov     eax, 80004005h
0x180099387  jmp     loc_180099545
0x18009938c  xor     r15d, r15d
0x18009938f  xor     r14b, r14b
0x180099392  mov     [rsp+78h+fClearVariant], r14b
0x180099397  cmp     [rdi+0A00h], r14b
0x18009939e  jz      short loc_1800993AE
0x1800993a0  mov     ebx, 80004005h
0x1800993a5  mov     [rsp+78h+hr], ebx
0x1800993a9  jmp     $CleanUp_120
0x1800993ae  cmp     dword ptr [rdi+9B0h], 2
0x1800993b5  jnz     short loc_1800993C5
0x1800993b7  mov     ebx, 80070005h
0x1800993bc  mov     [rsp+78h+hr], ebx
0x1800993c0  jmp     $CleanUp_120
0x1800993c5  cmp     word ptr [rsi], 1
0x1800993c9  jbe     short loc_1800993D1
0x1800993cb  cmp     word ptr [rsi], 0Ah
0x1800993cf  jnz     short loc_1800993FD
0x1800993d1  lea     varInput, [rdi+0A18h]; pvargSrc
0x1800993d8  mov     this, rsi; pvargDest
0x1800993db  call    cs:__imp_VariantCopy
0x1800993e2  nop     dword ptr [rax+rax+00h]
0x1800993e7  mov     ebx, eax
0x1800993e9  mov     [rsp+78h+hr], eax
0x1800993ed  test    eax, eax
0x1800993ef  js      $CleanUp_120
0x1800993f5  mov     r14b, 1
0x1800993f8  mov     [rsp+78h+fClearVariant], r14b
0x1800993fd  xor     edx, edx; fRequirePtrType
0x1800993ff  mov     this, rsi; pVar
0x180099402  call    ?getUnknown@Variant@@SAPEAUIUnknown@@PEAUtagVARIANT@@_N@Z; Variant::getUnknown(tagVARIANT *,bool)
0x180099407  mov     rbx, rax
0x18009940a  test    rax, rax
0x18009940d  jz      short loc_180099444
0x18009940f  xor     r8d, r8d; fInsideWinRT
0x180099412  lea     varInput, ?IID_Document@@3U_GUID@@B; iid
0x180099419  mov     this, rax; pUnk
0x18009941c  call    ?getObjectFromIUnk@Object@@SAPEAV1@PEAUIUnknown@@AEBU_GUID@@_N@Z; Object::getObjectFromIUnk(IUnknown *,_GUID const &,bool)
0x180099421  test    rax, rax
0x180099424  jz      short loc_18009942F
0x180099426  mov     r15, [rax+0C8h]
0x18009942d  jmp     short loc_180099444
0x18009942f  xor     r8d, r8d; fInsideWinRT
0x180099432  lea     varInput, ?IID_Node@@3U_GUID@@B; iid
0x180099439  mov     this, rbx; pUnk
0x18009943c  call    ?getObjectFromIUnk@Object@@SAPEAV1@PEAUIUnknown@@AEBU_GUID@@_N@Z; Object::getObjectFromIUnk(IUnknown *,_GUID const &,bool)
0x180099441  mov     r15, rax
0x180099444  test    r15, r15
0x180099447  jz      short loc_18009949F
0x180099449  lea     r12, [rdi+0A08h]
0x180099450  xor     edx, edx; pref
0x180099452  mov     this, r12; ppref
0x180099455  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x18009945a  mov     varInput, r12; ppDtsReader
0x18009945d  mov     this, rdi; this
0x180099460  call    ?CreateDTSReader@SAXReader@@IEAAJPEAPEAVDTSReader@@@Z; SAXReader::CreateDTSReader(DTSReader * *)
0x180099465  mov     ebx, eax
0x180099467  mov     [rsp+78h+hr], eax
0x18009946b  test    eax, eax
0x18009946d  js      $CleanUp_120
0x180099473  mov     byte ptr [rdi+0A00h], 1
0x18009947a  mov     this, [r12]
0x18009947e  mov     rax, [this]
0x180099481  mov     varInput, r15
0x180099484  mov     rax, [rax+20h]
0x180099488  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009948d  mov     ebx, eax
0x18009948f  mov     [rsp+78h+hr], eax
0x180099493  xor     edx, edx; pref
0x180099495  mov     this, r12; ppref
0x180099498  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x18009949d  jmp     short loc_1800994CC
0x18009949f  mov     byte ptr [rdi+0A00h], 1
0x1800994a6  movups  xmm0, xmmword ptr [rsi]
0x1800994a9  movaps  [rsp+78h+var_48], xmm0
0x1800994ae  movsd   xmm1, qword ptr [rsi+10h]
0x1800994b3  movsd   [rsp+78h+var_38], xmm1
0x1800994b9  lea     varInput, [rsp+78h+var_48]
0x1800994be  mov     this, rdi
0x1800994c1  call    ?parse@Reader@@UEAAJUtagVARIANT@@@Z; Reader::parse(tagVARIANT)
0x1800994c6  mov     ebx, eax
0x1800994c8  mov     [rsp+78h+hr], eax
0x1800994cc  jmp     short loc_180099528
0x1800994ce  call    ?exceptionCatch@Exception@@SAXXZ; Exception::exceptionCatch(void)
0x1800994d3  mov     rdi, [rsp+78h+arg_0]
0x1800994db  lea     this, [rdi+0A08h]; ppref
0x1800994e2  xor     edx, edx; pref
0x1800994e4  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800994e9  mov     ecx, cs:_tls_index
0x1800994ef  mov     rax, gs:58h
0x1800994f8  mov     edx, 8
0x1800994fd  mov     rax, [rax+this*8]
0x180099501  mov     this, [rax+varInput]
0x180099505  mov     this, [this+8]
0x180099509  mov     rax, [this]
0x18009950c  mov     rax, [rax+68h]
0x180099510  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099515  mov     ebx, eax
0x180099517  mov     [rsp+78h+hr], eax
0x18009951b  mov     rsi, [rsp+78h+arg_8]
0x180099523  mov     r14b, [rsp+78h+fClearVariant]
0x180099528  mov     byte ptr [rdi+0A00h], 0
0x18009952f  test    r14b, r14b
0x180099532  jz      short loc_180099543
0x180099534  mov     this, rsi; pvarg
0x180099537  call    cs:__imp_VariantClear
0x18009953e  nop     dword ptr [rax+rax+00h]
0x180099543  mov     eax, ebx
0x180099545  mov     rbx, [rsp+78h+arg_10]
0x18009954d  add     rsp, 50h
0x180099551  pop     r15
0x180099553  pop     r14
0x180099555  pop     r12
0x180099557  pop     rdi
0x180099558  pop     rsi
0x180099559  retn
0x1801814e8  push    rbp
0x1801814ea  sub     rsp, 20h
0x1801814ee  mov     rbp, rdx
0x1801814f1  call    ?fillException@Exception@@SAHPEAU_EXCEPTION_POINTERS@@@Z; Exception::fillException(_EXCEPTION_POINTERS *)
0x1801814f6  nop
0x1801814f7  add     rsp, 20h
0x1801814fb  pop     rbp
0x1801814fc  retn
```
