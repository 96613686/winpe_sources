# SAXReader::parse(tagVARIANT)

- ea: `0x1800986a0`
- end: `0x18009889e`
- name: `?parse@SAXReader@@UEAAJUtagVARIANT@@@Z`
- size: `510`
- prototype: `HRESULT __fastcall(SAXReader *this, tagVARIANT varInput)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180009490`
- `0x180025730`
- `0x1800799dc`
- `0x180079b10`
- `0x1800986a0`
- `0x18009f718`
- `0x1800a3e04`
- `0x180122de4`
- `0x180188010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180098881`
- `OLEAUT32!__imp_VariantClear` at `0x180098881`
- `OLEAUT32!__imp_VariantCopy` at `0x18009872b`
- `OLEAUT32!__imp_VariantCopy` at `0x18009872b`

## pseudocode

```c
__int64 __fastcall SAXReader::parse(SAXReader *this, tagVARIANT *varInput)
{
  Node *v5; // r15
  char v6; // r14
  int DTSReader; // ebx
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
          goto $CleanUp_122;
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
          goto $CleanUp_122;
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
      goto $CleanUp_122;
    }
    DTSReader = -2147024891;
  }
$CleanUp_122:
  if ( v6 )
    VariantClear(varInput);
  return (unsigned int)DTSReader;
}

```

## disassembly

```asm
0x1800986a0  mov     [rsp+arg_10], rbx
0x1800986a5  mov     [rsp+arg_8], varInput
0x1800986aa  mov     [rsp+arg_0], this
0x1800986af  push    rsi
0x1800986b0  push    rdi
0x1800986b1  push    r12
0x1800986b3  push    r14
0x1800986b5  push    r15
0x1800986b7  sub     rsp, 50h
0x1800986bb  mov     rsi, varInput
0x1800986be  mov     rdi, this
0x1800986c1  mov     rax, cs:?g_pfnEntry@@3P6APEAUTLSDATA@@XZEA; TLSDATA * (*g_pfnEntry)(void)
0x1800986c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800986cd  test    rax, rax
0x1800986d0  jnz     short loc_1800986DC
0x1800986d2  mov     eax, 80004005h
0x1800986d7  jmp     loc_180098889
0x1800986dc  xor     r15d, r15d
0x1800986df  xor     r14b, r14b
0x1800986e2  mov     [rsp+78h+fClearVariant], r14b
0x1800986e7  cmp     [rdi+0A00h], r14b
0x1800986ee  jz      short loc_1800986FE
0x1800986f0  mov     ebx, 80004005h
0x1800986f5  mov     [rsp+78h+hr], ebx
0x1800986f9  jmp     $CleanUp_122
0x1800986fe  cmp     dword ptr [rdi+9B0h], 2
0x180098705  jnz     short loc_180098715
0x180098707  mov     ebx, 80070005h
0x18009870c  mov     [rsp+78h+hr], ebx
0x180098710  jmp     $CleanUp_122
0x180098715  cmp     word ptr [rsi], 1
0x180098719  jbe     short loc_180098721
0x18009871b  cmp     word ptr [rsi], 0Ah
0x18009871f  jnz     short loc_180098747
0x180098721  lea     varInput, [rdi+0A18h]; pvargSrc
0x180098728  mov     this, rsi; pvargDest
0x18009872b  call    cs:__imp_VariantCopy
0x180098731  mov     ebx, eax
0x180098733  mov     [rsp+78h+hr], eax
0x180098737  test    eax, eax
0x180098739  js      $CleanUp_122
0x18009873f  mov     r14b, 1
0x180098742  mov     [rsp+78h+fClearVariant], r14b
0x180098747  xor     edx, edx; fRequirePtrType
0x180098749  mov     this, rsi; pVar
0x18009874c  call    ?getUnknown@Variant@@SAPEAUIUnknown@@PEAUtagVARIANT@@_N@Z; Variant::getUnknown(tagVARIANT *,bool)
0x180098751  mov     rbx, rax
0x180098754  test    rax, rax
0x180098757  jz      short loc_18009878E
0x180098759  xor     r8d, r8d; fInsideWinRT
0x18009875c  lea     varInput, ?IID_Document@@3U_GUID@@B; iid
0x180098763  mov     this, rax; pUnk
0x180098766  call    ?getObjectFromIUnk@Object@@SAPEAV1@PEAUIUnknown@@AEBU_GUID@@_N@Z; Object::getObjectFromIUnk(IUnknown *,_GUID const &,bool)
0x18009876b  test    rax, rax
0x18009876e  jz      short loc_180098779
0x180098770  mov     r15, [rax+0C8h]
0x180098777  jmp     short loc_18009878E
0x180098779  xor     r8d, r8d; fInsideWinRT
0x18009877c  lea     varInput, ?IID_Node@@3U_GUID@@B; iid
0x180098783  mov     this, rbx; pUnk
0x180098786  call    ?getObjectFromIUnk@Object@@SAPEAV1@PEAUIUnknown@@AEBU_GUID@@_N@Z; Object::getObjectFromIUnk(IUnknown *,_GUID const &,bool)
0x18009878b  mov     r15, rax
0x18009878e  test    r15, r15
0x180098791  jz      short loc_1800987E9
0x180098793  lea     r12, [rdi+0A08h]
0x18009879a  xor     edx, edx; pref
0x18009879c  mov     this, r12; ppref
0x18009879f  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800987a4  mov     varInput, r12; ppDtsReader
0x1800987a7  mov     this, rdi; this
0x1800987aa  call    ?CreateDTSReader@SAXReader@@IEAAJPEAPEAVDTSReader@@@Z; SAXReader::CreateDTSReader(DTSReader * *)
0x1800987af  mov     ebx, eax
0x1800987b1  mov     [rsp+78h+hr], eax
0x1800987b5  test    eax, eax
0x1800987b7  js      $CleanUp_122
0x1800987bd  mov     byte ptr [rdi+0A00h], 1
0x1800987c4  mov     this, [r12]
0x1800987c8  mov     rax, [this]
0x1800987cb  mov     varInput, r15
0x1800987ce  mov     rax, [rax+20h]
0x1800987d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800987d7  mov     ebx, eax
0x1800987d9  mov     [rsp+78h+hr], eax
0x1800987dd  xor     edx, edx; pref
0x1800987df  mov     this, r12; ppref
0x1800987e2  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800987e7  jmp     short loc_180098816
0x1800987e9  mov     byte ptr [rdi+0A00h], 1
0x1800987f0  movups  xmm0, xmmword ptr [rsi]
0x1800987f3  movaps  [rsp+78h+var_48], xmm0
0x1800987f8  movsd   xmm1, qword ptr [rsi+10h]
0x1800987fd  movsd   [rsp+78h+var_38], xmm1
0x180098803  lea     varInput, [rsp+78h+var_48]
0x180098808  mov     this, rdi
0x18009880b  call    ?parse@Reader@@UEAAJUtagVARIANT@@@Z; Reader::parse(tagVARIANT)
0x180098810  mov     ebx, eax
0x180098812  mov     [rsp+78h+hr], eax
0x180098816  jmp     short loc_180098872
0x180098818  call    ?exceptionCatch@Exception@@SAXXZ; Exception::exceptionCatch(void)
0x18009881d  mov     rdi, [rsp+78h+arg_0]
0x180098825  lea     this, [rdi+0A08h]; ppref
0x18009882c  xor     edx, edx; pref
0x18009882e  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x180098833  mov     ecx, cs:_tls_index
0x180098839  mov     rax, gs:58h
0x180098842  mov     edx, 8
0x180098847  mov     rax, [rax+this*8]
0x18009884b  mov     this, [rax+varInput]
0x18009884f  mov     this, [this+8]
0x180098853  mov     rax, [this]
0x180098856  mov     rax, [rax+68h]
0x18009885a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009885f  mov     ebx, eax
0x180098861  mov     [rsp+78h+hr], eax
0x180098865  mov     rsi, [rsp+78h+arg_8]
0x18009886d  mov     r14b, [rsp+78h+fClearVariant]
0x180098872  mov     byte ptr [rdi+0A00h], 0
0x180098879  test    r14b, r14b
0x18009887c  jz      short loc_180098887
0x18009887e  mov     this, rsi; pvarg
0x180098881  call    cs:__imp_VariantClear
0x180098887  mov     eax, ebx
0x180098889  mov     rbx, [rsp+78h+arg_10]
0x180098891  add     rsp, 50h
0x180098895  pop     r15
0x180098897  pop     r14
0x180098899  pop     r12
0x18009889b  pop     rdi
0x18009889c  pop     rsi
0x18009889d  retn
0x18017d95a  push    rbp
0x18017d95c  sub     rsp, 20h
0x18017d960  mov     rbp, rdx
0x18017d963  call    ?fillException@Exception@@SAHPEAU_EXCEPTION_POINTERS@@@Z; Exception::fillException(_EXCEPTION_POINTERS *)
0x18017d968  nop
0x18017d969  add     rsp, 20h
0x18017d96d  pop     rbp
0x18017d96e  retn
```
