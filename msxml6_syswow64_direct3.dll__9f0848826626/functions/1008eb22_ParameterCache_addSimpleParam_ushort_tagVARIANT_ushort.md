# ParameterCache::addSimpleParam(ushort *,tagVARIANT *,ushort *)

- ea: `0x1008eb22`
- end: `0x1008ed32`
- name: `?addSimpleParam@ParameterCache@@QAEXPAGPAUtagVARIANT@@0@Z`
- size: `528`
- prototype: `void __thiscall(ParameterCache *this, wchar_t *baseName, tagVARIANT *pvar, wchar_t *namespaceURI)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x1008ea60`

## callees

- `0x1003fb13`
- `0x10040bb4`
- `0x10052bb1`
- `0x10053182`
- `0x1005710a`
- `0x10064c31`
- `0x10064c51`
- `0x10067658`
- `0x10067764`
- `0x1006bff0`
- `0x1007ca62`
- `0x1007dbf3`
- `0x1008de5e`
- `0x1008eb22`
- `0x100d5a5a`

## import_xrefs

- `OLEAUT32!__imp__VariantCopy@8` at `0x1008ec58`
- `OLEAUT32!__imp__VariantCopy@8` at `0x1008ec58`

## pseudocode

```c
// bad sp value at call has been detected, the output may be wrong!
void __thiscall ParameterCache::addSimpleParam(
        ParameterCache *this,
        wchar_t *baseName,
        tagVARIANT *pvar,
        wchar_t *namespaceURI)
{
  unsigned __int16 BaseType; // ax
  char v6; // bl
  _reference<Vector> *p_simpleParams; // edi
  struct Vector *v8; // esi
  SimpleParam *p; // edi
  Atom *v10; // esi
  int i; // edx
  Object *v12; // ecx
  HRESULT v13; // eax
  VARIANTARG *v14; // [esp+10h] [ebp-40h]
  Name *v15; // [esp+14h] [ebp-3Ch]
  Atom *pAtomGI; // [esp+18h] [ebp-38h]
  _reference<SimpleParam> pProtectSP; // [esp+20h] [ebp-30h] BYREF
  ParameterCache *v18; // [esp+24h] [ebp-2Ch]
  _reference<Atom> atomGI; // [esp+28h] [ebp-28h] BYREF
  _reference<Atom> atomURI; // [esp+2Ch] [ebp-24h] BYREF
  _reference<Name> name; // [esp+30h] [ebp-20h] BYREF
  _reference<SimpleParam> pSPNew; // [esp+34h] [ebp-1Ch] BYREF
  CPPEH_RECORD ms_exc; // [esp+38h] [ebp-18h]

  v18 = this;
  BaseType = Variant::getBaseType(pvar);
  if ( BaseType == 13 || BaseType == 9 )
  {
    v6 = 1;
  }
  else
  {
    v6 = 1;
    if ( BaseType > 1u )
      goto LABEL_7;
  }
  if ( Variant::getUnknown(pvar, 0) )
  {
LABEL_7:
    v6 = 0;
    if ( !XRuntime::canConvert(pvar) )
      Exception::throwHR(-2147352571);
  }
  p_simpleParams = &this->_simpleParams;
  if ( !this->_simpleParams._p )
  {
    v8 = Vector::newVector();
    release(&p_simpleParams->_p);
    p_simpleParams->_p = v8;
  }
  atomGI._p = 0;
  atomURI._p = 0;
  name._p = 0;
  p = 0;
  pSPNew._p = 0;
  pProtectSP._p = 0;
  ms_exc.registration.TryLevel = 0;
  pAtomGI = Atom::create(baseName);
  release(&atomGI._p);
  atomGI._p = pAtomGI;
  v10 = 0;
  if ( namespaceURI && *namespaceURI )
  {
    v10 = Atom::create(namespaceURI);
    release(&atomURI._p);
    atomURI._p = v10;
  }
  v15 = Name::create(pAtomGI, v10);
  release(&name._p);
  name._p = v15;
  for ( i = v18->_simpleParams._p->_elementCount; i; --i )
  {
    v12 = v18->_simpleParams._p->_elementData[i - 1];
    v14 = (VARIANTARG *)v12;
    if ( (Name *)v12[3].__vftable == v15 )
    {
      if ( v6 )
      {
        Vector::removeElement(v18->_simpleParams._p, v12);
      }
      else
      {
        assign(&pProtectSP._p, v12);
        v13 = VariantCopy(v14 + 1, pvar);
        checkhr(v13);
      }
      goto LABEL_23;
    }
  }
  if ( !v6 )
  {
    SimpleParam::New(v15, pvar, &pSPNew._p);
    p = pSPNew._p;
    Vector::addElement(v18->_simpleParams._p, pSPNew._p);
  }
LABEL_23:
  ms_exc.registration.TryLevel = -2;
  if ( pAtomGI )
    assign(&atomGI._p, 0);
  if ( v10 )
    assign(&atomURI._p, 0);
  if ( v15 )
    assign(&name._p, 0);
  if ( p )
    assign(&pSPNew._p, 0);
  if ( pProtectSP._p )
    assign(&pProtectSP._p, 0);
  release(&pProtectSP._p);
  release(&pSPNew._p);
  release(&name._p);
  release(&atomURI._p);
  release(&atomGI._p);
}

```

## disassembly

```asm
0x1008eb22  push    30h
0x1008eb24  push    offset stru_10175298
0x1008eb29  call    __SEH_prolog4
0x1008eb2e  mov     esi, this
0x1008eb30  mov     [ebp+var_2C], esi
0x1008eb33  mov     this, [ebp+pvar]; varObject
0x1008eb36  call    ?getBaseType@Variant@@SGGPAUtagVARIANT@@@Z; Variant::getBaseType(tagVARIANT *)
0x1008eb3b  movzx   eax, ax
0x1008eb3e  cmp     eax, 0Dh
0x1008eb41  jz      short loc_1008EB57
0x1008eb43  cmp     eax, 9
0x1008eb46  jz      short loc_1008EB57
0x1008eb48  xor     ebx, ebx
0x1008eb4a  inc     ebx
0x1008eb4b  cmp     ax, bx
0x1008eb4e  jz      short loc_1008EB5A
0x1008eb50  test    ax, ax
0x1008eb53  jnz     short loc_1008EB68
0x1008eb55  jmp     short loc_1008EB5A
0x1008eb57  xor     ebx, ebx
0x1008eb59  inc     ebx
0x1008eb5a  xor     dl, dl; fRequirePtrType
0x1008eb5c  mov     this, [ebp+pvar]; pVar
0x1008eb5f  call    ?getUnknown@Variant@@SGPAUIUnknown@@PAUtagVARIANT@@_N@Z; Variant::getUnknown(tagVARIANT *,bool)
0x1008eb64  test    eax, eax
0x1008eb66  jz      short loc_1008EB80
0x1008eb68  xor     bl, bl
0x1008eb6a  mov     this, [ebp+pvar]; var
0x1008eb6d  call    ?canConvert@XRuntime@@SG_NPAUtagVARIANT@@@Z; XRuntime::canConvert(tagVARIANT *)
0x1008eb72  test    al, al
0x1008eb74  jnz     short loc_1008EB80
0x1008eb76  mov     this, 80020005h; hr
0x1008eb7b  call    ?throwHR@Exception@@SGXJ@Z; Exception::throwHR(long)
0x1008eb80  xor     eax, eax
0x1008eb82  lea     edi, [esi+0Ch]
0x1008eb85  cmp     [edi], eax
0x1008eb87  jnz     short loc_1008EB9E
0x1008eb89  push    6
0x1008eb8b  pop     this; initialCapacity
0x1008eb8c  call    ?newVector@Vector@@SGPAV1@HH@Z; Vector::newVector(int,int)
0x1008eb91  mov     esi, eax
0x1008eb93  mov     this, edi; ppref
0x1008eb95  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x1008eb9a  mov     [edi], esi
0x1008eb9c  xor     eax, eax
0x1008eb9e  mov     [ebp+atomGI._p], eax
0x1008eba1  mov     [ebp+atomURI._p], eax
0x1008eba4  mov     [ebp+name._p], eax
0x1008eba7  mov     edi, eax
0x1008eba9  mov     [ebp+pSPNew._p], edi
0x1008ebac  mov     [ebp+pProtectSP._p], eax
0x1008ebaf  mov     [ebp+ms_exc.registration.TryLevel], eax
0x1008ebb2  mov     this, [ebp+baseName]; c
0x1008ebb5  call    ?create@Atom@@SGPAV1@PBG@Z; Atom::create(ushort const *)
0x1008ebba  mov     esi, eax
0x1008ebbc  mov     [ebp+pAtomGI], esi
0x1008ebbf  lea     this, [ebp+atomGI]; ppref
0x1008ebc2  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x1008ebc7  mov     [ebp+atomGI._p], esi
0x1008ebca  mov     this, [ebp+namespaceURI]; c
0x1008ebcd  xor     esi, esi
0x1008ebcf  test    this, this
0x1008ebd1  jz      short loc_1008EBEA
0x1008ebd3  cmp     [this], si
0x1008ebd6  jz      short loc_1008EBEA
0x1008ebd8  call    ?create@Atom@@SGPAV1@PBG@Z; Atom::create(ushort const *)
0x1008ebdd  mov     esi, eax
0x1008ebdf  lea     this, [ebp+atomURI]; ppref
0x1008ebe2  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x1008ebe7  mov     [ebp+atomURI._p], esi
0x1008ebea  mov     edx, esi; pAtomURN
0x1008ebec  mov     this, [ebp+pAtomGI]; pAtomGI
0x1008ebef  call    ?create@Name@@SGPAV1@PAVAtom@@0@Z; Name::create(Atom *,Atom *)
0x1008ebf4  mov     [ebp+var_3C], eax
0x1008ebf7  lea     this, [ebp+name]; ppref
0x1008ebfa  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x1008ebff  mov     eax, [ebp+var_3C]
0x1008ec02  mov     [ebp+name._p], eax
0x1008ec05  mov     this, [ebp+var_2C]
0x1008ec08  mov     this, [this+0Ch]
0x1008ec0b  mov     edx, [this+0Ch]
0x1008ec0e  mov     [ebp+i], edx
0x1008ec11  mov     this, edx
0x1008ec13  dec     edx
0x1008ec14  mov     [ebp+i], edx
0x1008ec17  test    this, this
0x1008ec19  jz      short loc_1008EC6C
0x1008ec1b  mov     edx, [ebp+var_2C]
0x1008ec1e  mov     this, [edx+0Ch]
0x1008ec21  mov     edx, [this+14h]
0x1008ec24  mov     this, [ebp+i]
0x1008ec27  mov     this, [edx+this*4]
0x1008ec2a  mov     [ebp+var_40], this
0x1008ec2d  cmp     [this+0Ch], eax
0x1008ec30  jnz     short loc_1008EC67
0x1008ec32  test    bl, bl
0x1008ec34  jz      short loc_1008EC44
0x1008ec36  push    this; obj
0x1008ec37  mov     eax, [ebp+var_2C]
0x1008ec3a  mov     this, [eax+0Ch]; this
0x1008ec3d  call    ?removeElement@Vector@@QAE_NPAVObject@@@Z; Vector::removeElement(Object *)
0x1008ec42  jmp     short loc_1008EC8D
0x1008ec44  mov     edx, this; pref
0x1008ec46  lea     this, [ebp+pProtectSP]; ppref
0x1008ec49  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x1008ec4e  push    [ebp+pvar]; pvargSrc
0x1008ec51  mov     eax, [ebp+var_40]
0x1008ec54  add     eax, 10h
0x1008ec57  push    eax; pvargDest
0x1008ec58  call    ds:__imp__VariantCopy@8; VariantCopy(x,x)
0x1008ec5e  mov     this, eax; hr
0x1008ec60  call    ?checkhr@@YGXJ@Z; checkhr(long)
0x1008ec65  jmp     short loc_1008EC8D
0x1008ec67  mov     edx, [ebp+i]
0x1008ec6a  jmp     short loc_1008EC11
0x1008ec6c  test    bl, bl
0x1008ec6e  jnz     short loc_1008EC8D
0x1008ec70  lea     this, [ebp+pSPNew]
0x1008ec73  push    this; ppsp
0x1008ec74  mov     edx, [ebp+pvar]; pvar
0x1008ec77  mov     this, eax; name
0x1008ec79  call    ?New@SimpleParam@@SGXPAVName@@PAUtagVARIANT@@PAPAV1@@Z; SimpleParam::New(Name *,tagVARIANT *,SimpleParam * *)
0x1008ec7e  mov     edi, [ebp+pSPNew._p]
0x1008ec81  push    edi; obj
0x1008ec82  mov     eax, [ebp+var_2C]
0x1008ec85  mov     this, [eax+0Ch]; this
0x1008ec88  call    ?addElement@Vector@@QAEXPAVObject@@@Z; Vector::addElement(Object *)
0x1008ec8d  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x1008ec94  call    $LN41_10
0x1008ec99  lea     this, [ebp+pProtectSP]; ppref
0x1008ec9c  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x1008eca1  lea     this, [ebp+pSPNew]; ppref
0x1008eca4  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x1008eca9  lea     this, [ebp+name]; ppref
0x1008ecac  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x1008ecb1  lea     this, [ebp+atomURI]; ppref
0x1008ecb4  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x1008ecb9  lea     this, [ebp+atomGI]; ppref
0x1008ecbc  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x1008ecc1  mov     this, [ebp+ms_exc.registration.Next]
0x1008ecc4  mov     large fs:0, this
0x1008eccb  pop     this
0x1008eccc  pop     edi
0x1008eccd  pop     esi
0x1008ecce  pop     ebx
0x1008eccf  leave
0x1008ecd0  retn    0Ch
0x1008ecd3  mov     eax, [ebp+atomGI._p]
0x1008ecd6  mov     [ebp+pAtomGI], eax
0x1008ecd9  mov     esi, [ebp+atomURI._p]
0x1008ecdc  mov     eax, [ebp+name._p]
0x1008ecdf  mov     [ebp+var_3C], eax
0x1008ece2  mov     edi, [ebp+pSPNew._p]
0x1008ece5  cmp     [ebp+pAtomGI], 0
0x1008ece9  jz      short loc_1008ECF5
0x1008eceb  xor     edx, edx; pref
0x1008eced  lea     this, [ebp+atomGI]; ppref
0x1008ecf0  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x1008ecf5  test    esi, esi
0x1008ecf7  jz      short loc_1008ED03
0x1008ecf9  xor     edx, edx; pref
0x1008ecfb  lea     this, [ebp+atomURI]; ppref
0x1008ecfe  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x1008ed03  cmp     [ebp+var_3C], 0
0x1008ed07  jz      short loc_1008ED13
0x1008ed09  xor     edx, edx; pref
0x1008ed0b  lea     this, [ebp+name]; ppref
0x1008ed0e  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x1008ed13  test    edi, edi
0x1008ed15  jz      short loc_1008ED21
0x1008ed17  xor     edx, edx; pref
0x1008ed19  lea     this, [ebp+pSPNew]; ppref
0x1008ed1c  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x1008ed21  cmp     [ebp+pProtectSP._p], 0
0x1008ed25  jz      short $LN40_9
0x1008ed27  xor     edx, edx; pref
0x1008ed29  lea     this, [ebp+pProtectSP]; ppref
0x1008ed2c  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x1008ed31  retn
```
