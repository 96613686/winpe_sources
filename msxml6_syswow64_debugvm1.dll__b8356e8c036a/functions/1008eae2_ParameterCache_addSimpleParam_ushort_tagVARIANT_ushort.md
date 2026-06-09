# ParameterCache::addSimpleParam(ushort *,tagVARIANT *,ushort *)

- ea: `0x1008eae2`
- end: `0x1008ecf2`
- name: `?addSimpleParam@ParameterCache@@QAEXPAGPAUtagVARIANT@@0@Z`
- size: `528`
- prototype: `void __thiscall(ParameterCache *this, wchar_t *baseName, tagVARIANT *pvar, wchar_t *namespaceURI)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x1008ea20`

## callees

- `0x1003fba3`
- `0x10040c44`
- `0x10052c41`
- `0x10053212`
- `0x1005719a`
- `0x10064cd1`
- `0x10064cf1`
- `0x100676f8`
- `0x10067804`
- `0x1006c080`
- `0x1007ca22`
- `0x1007dbb3`
- `0x1008de1e`
- `0x1008eae2`
- `0x100d593a`

## import_xrefs

- `OLEAUT32!__imp__VariantCopy@8` at `0x1008ec18`
- `OLEAUT32!__imp__VariantCopy@8` at `0x1008ec18`

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
0x1008eae2  push    30h
0x1008eae4  push    offset stru_101751A8
0x1008eae9  call    __SEH_prolog4
0x1008eaee  mov     esi, this
0x1008eaf0  mov     [ebp+var_2C], esi
0x1008eaf3  mov     this, [ebp+pvar]; varObject
0x1008eaf6  call    ?getBaseType@Variant@@SGGPAUtagVARIANT@@@Z; Variant::getBaseType(tagVARIANT *)
0x1008eafb  movzx   eax, ax
0x1008eafe  cmp     eax, 0Dh
0x1008eb01  jz      short loc_1008EB17
0x1008eb03  cmp     eax, 9
0x1008eb06  jz      short loc_1008EB17
0x1008eb08  xor     ebx, ebx
0x1008eb0a  inc     ebx
0x1008eb0b  cmp     ax, bx
0x1008eb0e  jz      short loc_1008EB1A
0x1008eb10  test    ax, ax
0x1008eb13  jnz     short loc_1008EB28
0x1008eb15  jmp     short loc_1008EB1A
0x1008eb17  xor     ebx, ebx
0x1008eb19  inc     ebx
0x1008eb1a  xor     dl, dl; fRequirePtrType
0x1008eb1c  mov     this, [ebp+pvar]; pVar
0x1008eb1f  call    ?getUnknown@Variant@@SGPAUIUnknown@@PAUtagVARIANT@@_N@Z; Variant::getUnknown(tagVARIANT *,bool)
0x1008eb24  test    eax, eax
0x1008eb26  jz      short loc_1008EB40
0x1008eb28  xor     bl, bl
0x1008eb2a  mov     this, [ebp+pvar]; var
0x1008eb2d  call    ?canConvert@XRuntime@@SG_NPAUtagVARIANT@@@Z; XRuntime::canConvert(tagVARIANT *)
0x1008eb32  test    al, al
0x1008eb34  jnz     short loc_1008EB40
0x1008eb36  mov     this, 80020005h; hr
0x1008eb3b  call    ?throwHR@Exception@@SGXJ@Z; Exception::throwHR(long)
0x1008eb40  xor     eax, eax
0x1008eb42  lea     edi, [esi+0Ch]
0x1008eb45  cmp     [edi], eax
0x1008eb47  jnz     short loc_1008EB5E
0x1008eb49  push    6
0x1008eb4b  pop     this; initialCapacity
0x1008eb4c  call    ?newVector@Vector@@SGPAV1@HH@Z; Vector::newVector(int,int)
0x1008eb51  mov     esi, eax
0x1008eb53  mov     this, edi; ppref
0x1008eb55  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x1008eb5a  mov     [edi], esi
0x1008eb5c  xor     eax, eax
0x1008eb5e  mov     [ebp+atomGI._p], eax
0x1008eb61  mov     [ebp+atomURI._p], eax
0x1008eb64  mov     [ebp+name._p], eax
0x1008eb67  mov     edi, eax
0x1008eb69  mov     [ebp+pSPNew._p], edi
0x1008eb6c  mov     [ebp+pProtectSP._p], eax
0x1008eb6f  mov     [ebp+ms_exc.registration.TryLevel], eax
0x1008eb72  mov     this, [ebp+baseName]; c
0x1008eb75  call    ?create@Atom@@SGPAV1@PBG@Z; Atom::create(ushort const *)
0x1008eb7a  mov     esi, eax
0x1008eb7c  mov     [ebp+pAtomGI], esi
0x1008eb7f  lea     this, [ebp+atomGI]; ppref
0x1008eb82  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x1008eb87  mov     [ebp+atomGI._p], esi
0x1008eb8a  mov     this, [ebp+namespaceURI]; c
0x1008eb8d  xor     esi, esi
0x1008eb8f  test    this, this
0x1008eb91  jz      short loc_1008EBAA
0x1008eb93  cmp     [this], si
0x1008eb96  jz      short loc_1008EBAA
0x1008eb98  call    ?create@Atom@@SGPAV1@PBG@Z; Atom::create(ushort const *)
0x1008eb9d  mov     esi, eax
0x1008eb9f  lea     this, [ebp+atomURI]; ppref
0x1008eba2  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x1008eba7  mov     [ebp+atomURI._p], esi
0x1008ebaa  mov     edx, esi; pAtomURN
0x1008ebac  mov     this, [ebp+pAtomGI]; pAtomGI
0x1008ebaf  call    ?create@Name@@SGPAV1@PAVAtom@@0@Z; Name::create(Atom *,Atom *)
0x1008ebb4  mov     [ebp+var_3C], eax
0x1008ebb7  lea     this, [ebp+name]; ppref
0x1008ebba  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x1008ebbf  mov     eax, [ebp+var_3C]
0x1008ebc2  mov     [ebp+name._p], eax
0x1008ebc5  mov     this, [ebp+var_2C]
0x1008ebc8  mov     this, [this+0Ch]
0x1008ebcb  mov     edx, [this+0Ch]
0x1008ebce  mov     [ebp+i], edx
0x1008ebd1  mov     this, edx
0x1008ebd3  dec     edx
0x1008ebd4  mov     [ebp+i], edx
0x1008ebd7  test    this, this
0x1008ebd9  jz      short loc_1008EC2C
0x1008ebdb  mov     edx, [ebp+var_2C]
0x1008ebde  mov     this, [edx+0Ch]
0x1008ebe1  mov     edx, [this+14h]
0x1008ebe4  mov     this, [ebp+i]
0x1008ebe7  mov     this, [edx+this*4]
0x1008ebea  mov     [ebp+var_40], this
0x1008ebed  cmp     [this+0Ch], eax
0x1008ebf0  jnz     short loc_1008EC27
0x1008ebf2  test    bl, bl
0x1008ebf4  jz      short loc_1008EC04
0x1008ebf6  push    this; obj
0x1008ebf7  mov     eax, [ebp+var_2C]
0x1008ebfa  mov     this, [eax+0Ch]; this
0x1008ebfd  call    ?removeElement@Vector@@QAE_NPAVObject@@@Z; Vector::removeElement(Object *)
0x1008ec02  jmp     short loc_1008EC4D
0x1008ec04  mov     edx, this; pref
0x1008ec06  lea     this, [ebp+pProtectSP]; ppref
0x1008ec09  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x1008ec0e  push    [ebp+pvar]; pvargSrc
0x1008ec11  mov     eax, [ebp+var_40]
0x1008ec14  add     eax, 10h
0x1008ec17  push    eax; pvargDest
0x1008ec18  call    ds:__imp__VariantCopy@8; VariantCopy(x,x)
0x1008ec1e  mov     this, eax; hr
0x1008ec20  call    ?checkhr@@YGXJ@Z; checkhr(long)
0x1008ec25  jmp     short loc_1008EC4D
0x1008ec27  mov     edx, [ebp+i]
0x1008ec2a  jmp     short loc_1008EBD1
0x1008ec2c  test    bl, bl
0x1008ec2e  jnz     short loc_1008EC4D
0x1008ec30  lea     this, [ebp+pSPNew]
0x1008ec33  push    this; ppsp
0x1008ec34  mov     edx, [ebp+pvar]; pvar
0x1008ec37  mov     this, eax; name
0x1008ec39  call    ?New@SimpleParam@@SGXPAVName@@PAUtagVARIANT@@PAPAV1@@Z; SimpleParam::New(Name *,tagVARIANT *,SimpleParam * *)
0x1008ec3e  mov     edi, [ebp+pSPNew._p]
0x1008ec41  push    edi; obj
0x1008ec42  mov     eax, [ebp+var_2C]
0x1008ec45  mov     this, [eax+0Ch]; this
0x1008ec48  call    ?addElement@Vector@@QAEXPAVObject@@@Z; Vector::addElement(Object *)
0x1008ec4d  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x1008ec54  call    $LN41_10
0x1008ec59  lea     this, [ebp+pProtectSP]; ppref
0x1008ec5c  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x1008ec61  lea     this, [ebp+pSPNew]; ppref
0x1008ec64  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x1008ec69  lea     this, [ebp+name]; ppref
0x1008ec6c  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x1008ec71  lea     this, [ebp+atomURI]; ppref
0x1008ec74  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x1008ec79  lea     this, [ebp+atomGI]; ppref
0x1008ec7c  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x1008ec81  mov     this, [ebp+ms_exc.registration.Next]
0x1008ec84  mov     large fs:0, this
0x1008ec8b  pop     this
0x1008ec8c  pop     edi
0x1008ec8d  pop     esi
0x1008ec8e  pop     ebx
0x1008ec8f  leave
0x1008ec90  retn    0Ch
0x1008ec93  mov     eax, [ebp+atomGI._p]
0x1008ec96  mov     [ebp+pAtomGI], eax
0x1008ec99  mov     esi, [ebp+atomURI._p]
0x1008ec9c  mov     eax, [ebp+name._p]
0x1008ec9f  mov     [ebp+var_3C], eax
0x1008eca2  mov     edi, [ebp+pSPNew._p]
0x1008eca5  cmp     [ebp+pAtomGI], 0
0x1008eca9  jz      short loc_1008ECB5
0x1008ecab  xor     edx, edx; pref
0x1008ecad  lea     this, [ebp+atomGI]; ppref
0x1008ecb0  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x1008ecb5  test    esi, esi
0x1008ecb7  jz      short loc_1008ECC3
0x1008ecb9  xor     edx, edx; pref
0x1008ecbb  lea     this, [ebp+atomURI]; ppref
0x1008ecbe  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x1008ecc3  cmp     [ebp+var_3C], 0
0x1008ecc7  jz      short loc_1008ECD3
0x1008ecc9  xor     edx, edx; pref
0x1008eccb  lea     this, [ebp+name]; ppref
0x1008ecce  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x1008ecd3  test    edi, edi
0x1008ecd5  jz      short loc_1008ECE1
0x1008ecd7  xor     edx, edx; pref
0x1008ecd9  lea     this, [ebp+pSPNew]; ppref
0x1008ecdc  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x1008ece1  cmp     [ebp+pProtectSP._p], 0
0x1008ece5  jz      short $LN40_9
0x1008ece7  xor     edx, edx; pref
0x1008ece9  lea     this, [ebp+pProtectSP]; ppref
0x1008ecec  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x1008ecf1  retn
```
