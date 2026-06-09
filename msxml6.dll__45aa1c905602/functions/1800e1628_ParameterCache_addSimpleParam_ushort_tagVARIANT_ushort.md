# ParameterCache::addSimpleParam(ushort *,tagVARIANT *,ushort *)

- ea: `0x1800e1628`
- end: `0x1800e18c1`
- name: `?addSimpleParam@ParameterCache@@QEAAXPEAGPEAUtagVARIANT@@0@Z`
- size: `665`
- prototype: `void __fastcall(ParameterCache *this, wchar_t *baseName, tagVARIANT *pvar, wchar_t *namespaceURI)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x1800e1560`

## callees

- `0x1800097cc`
- `0x180015a80`
- `0x180015d54`
- `0x180019e20`
- `0x18002ca20`
- `0x180032de8`
- `0x18003a79c`
- `0x180078e98`
- `0x1800aa61c`
- `0x1800bda08`
- `0x1800db84c`
- `0x1800e0854`
- `0x1800e1628`
- `0x180114ae8`

## import_xrefs

- `OLEAUT32!__imp_VariantCopy` at `0x1800e17cc`
- `OLEAUT32!__imp_VariantCopy` at `0x1800e17cc`

## pseudocode

```c
void __fastcall ParameterCache::addSimpleParam(
        ParameterCache *this,
        wchar_t *baseName,
        tagVARIANT *pvar,
        wchar_t *namespaceURI)
{
  unsigned __int16 BaseType; // ax
  char v9; // r13
  int v10; // edx
  Vector *v11; // rbx
  Atom *v12; // rbx
  SimpleParam *v13; // rdi
  SimpleParam *v14; // r14
  Atom *v15; // r15
  Name *v16; // rsi
  Vector *p; // rcx
  int elementCount; // r8d
  Object *v20; // rax
  HRESULT v21; // eax
  _reference<Atom> atomGI; // [rsp+28h] [rbp-60h] BYREF
  _reference<Atom> atomURI; // [rsp+30h] [rbp-58h] BYREF
  _reference<Name> name; // [rsp+38h] [rbp-50h] BYREF
  _reference<SimpleParam> pSPNew; // [rsp+40h] [rbp-48h] BYREF
  _reference<SimpleParam> pProtectSP; // [rsp+48h] [rbp-40h] BYREF
  Object *v27; // [rsp+50h] [rbp-38h]

  BaseType = Variant::getBaseType(pvar);
  if ( ((BaseType - 1) & 0xFFF3) != 0 || BaseType == 5 )
  {
    v9 = 0;
    if ( BaseType )
    {
LABEL_17:
      if ( !XRuntime::canConvert(pvar) )
        Exception::throwHR(-2147352571);
      goto LABEL_6;
    }
  }
  if ( Variant::getUnknown(pvar, 0) )
  {
    v9 = 0;
    goto LABEL_17;
  }
  v9 = 1;
LABEL_6:
  if ( !this->_simpleParams._p )
  {
    v11 = Vector::newVector(6, v10);
    release(&this->_simpleParams._p);
    this->_simpleParams._p = v11;
  }
  atomGI._p = 0;
  v12 = 0;
  atomURI._p = 0;
  name._p = 0;
  v13 = 0;
  pSPNew._p = 0;
  v14 = 0;
  pProtectSP._p = 0;
  v15 = Atom::create(baseName);
  release(&atomGI._p);
  atomGI._p = v15;
  if ( namespaceURI && *namespaceURI )
  {
    v12 = Atom::create(namespaceURI);
    release(&atomURI._p);
    atomURI._p = v12;
  }
  v16 = Name::create(v15, v12);
  release(&name._p);
  name._p = v16;
  p = this->_simpleParams._p;
  elementCount = p->_elementCount;
  while ( elementCount-- )
  {
    v20 = p->_elementData[elementCount];
    v27 = v20;
    if ( (Name *)v20[3].__vftable == v16 )
    {
      if ( v9 )
      {
        Vector::removeElement(p, v20);
      }
      else
      {
        assign(&pProtectSP._p, v20);
        v21 = VariantCopy((VARIANTARG *)&v27[4], pvar);
        checkhr(v21);
        v14 = pProtectSP._p;
      }
      goto $LN62_13;
    }
  }
  if ( !v9 )
  {
    SimpleParam::New(v16, pvar, &pSPNew._p);
    v13 = pSPNew._p;
    Vector::addElement(this->_simpleParams._p, pSPNew._p);
  }
$LN62_13:
  if ( v15 )
    assign(&atomGI._p, 0);
  if ( v12 )
    assign(&atomURI._p, 0);
  if ( v16 )
    assign(&name._p, 0);
  if ( v13 )
    assign(&pSPNew._p, 0);
  if ( v14 )
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
0x1800e1628  mov     rax, rsp
0x1800e162b  mov     [rax+10h], rbx
0x1800e162f  mov     [rax+20h], rsi
0x1800e1633  mov     [rax+18h], pvar
0x1800e1637  mov     [rax+8], this
0x1800e163b  push    rdi
0x1800e163c  push    r12
0x1800e163e  push    r13
0x1800e1640  push    r14
0x1800e1642  push    r15
0x1800e1644  sub     rsp, 60h
0x1800e1648  mov     rsi, namespaceURI
0x1800e164b  mov     rbx, pvar
0x1800e164e  mov     r15, baseName
0x1800e1651  mov     rdi, this
0x1800e1654  mov     this, pvar; varObject
0x1800e1657  call    ?getBaseType@Variant@@SAGPEAUtagVARIANT@@@Z; Variant::getBaseType(tagVARIANT *)
0x1800e165c  movzx   r10d, ax
0x1800e1660  mov     r14d, 1
0x1800e1666  sub     r10w, r14w
0x1800e166a  mov     ecx, 0FFF3h
0x1800e166f  test    cx, r10w
0x1800e1673  jnz     short loc_1800E1680
0x1800e1675  cmp     ax, 5
0x1800e1679  jz      short loc_1800E1680
0x1800e167b  xor     r12d, r12d
0x1800e167e  jmp     short loc_1800E168F
0x1800e1680  xor     r12d, r12d
0x1800e1683  mov     r13b, r12b
0x1800e1686  test    ax, ax
0x1800e1689  jnz     loc_1800E1796
0x1800e168f  xor     edx, edx; fRequirePtrType
0x1800e1691  mov     this, rbx; pVar
0x1800e1694  call    ?getUnknown@Variant@@SAPEAUIUnknown@@PEAUtagVARIANT@@_N@Z; Variant::getUnknown(tagVARIANT *,bool)
0x1800e1699  test    rax, rax
0x1800e169c  jnz     loc_1800E1793
0x1800e16a2  mov     r13b, r14b
0x1800e16a5  cmp     [rdi+18h], r12
0x1800e16a9  jnz     short loc_1800E16C5
0x1800e16ab  mov     ecx, 6; initialCapacity
0x1800e16b0  call    ?newVector@Vector@@SAPEAV1@HH@Z; Vector::newVector(int,int)
0x1800e16b5  mov     rbx, rax
0x1800e16b8  lea     this, [rdi+18h]; ppref
0x1800e16bc  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x1800e16c1  mov     [rdi+18h], rbx
0x1800e16c5  mov     [rsp+88h+atomGI._p], r12
0x1800e16ca  mov     rbx, r12
0x1800e16cd  mov     [rsp+88h+atomURI._p], rbx
0x1800e16d2  mov     [rsp+88h+name._p], r12
0x1800e16d7  mov     rdi, r12
0x1800e16da  mov     [rsp+88h+pSPNew._p], r12
0x1800e16df  mov     r14, r12
0x1800e16e2  mov     [rsp+88h+pProtectSP._p], r12
0x1800e16e7  mov     this, r15; c
0x1800e16ea  call    ?create@Atom@@SAPEAV1@PEBG@Z; Atom::create(ushort const *)
0x1800e16ef  mov     r15, rax
0x1800e16f2  lea     this, [rsp+88h+atomGI]; ppref
0x1800e16f7  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x1800e16fc  mov     [rsp+88h+atomGI._p], r15
0x1800e1701  test    rsi, rsi
0x1800e1704  jz      short loc_1800E1726
0x1800e1706  cmp     [rsi], r12w
0x1800e170a  jz      short loc_1800E1726
0x1800e170c  mov     this, rsi; c
0x1800e170f  call    ?create@Atom@@SAPEAV1@PEBG@Z; Atom::create(ushort const *)
0x1800e1714  mov     rbx, rax
0x1800e1717  lea     this, [rsp+88h+atomURI]; ppref
0x1800e171c  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x1800e1721  mov     [rsp+88h+atomURI._p], rbx
0x1800e1726  mov     baseName, rbx; pAtomURN
0x1800e1729  mov     this, r15; pAtomGI
0x1800e172c  call    ?create@Name@@SAPEAV1@PEAVAtom@@0@Z; Name::create(Atom *,Atom *)
0x1800e1731  mov     rsi, rax
0x1800e1734  lea     this, [rsp+88h+name]; ppref
0x1800e1739  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x1800e173e  mov     [rsp+88h+name._p], rsi
0x1800e1743  mov     this, [rsp+88h+arg_0]
0x1800e174b  mov     this, [this+18h]; this
0x1800e174f  mov     r8d, [this+14h]
0x1800e1753  mov     [rsp+88h+i], r8d
0x1800e1758  mov     eax, r8d
0x1800e175b  dec     r8d
0x1800e175e  mov     [rsp+88h+i], r8d
0x1800e1763  test    eax, eax
0x1800e1765  jz      loc_1800E17EB
0x1800e176b  movsxd  baseName, r8d
0x1800e176e  mov     rax, [this+20h]
0x1800e1772  mov     rax, [rax+baseName*8]
0x1800e1776  mov     [rsp+88h+var_38], rax
0x1800e177b  cmp     [rax+18h], rsi
0x1800e177f  jnz     short loc_1800E17E6
0x1800e1781  mov     baseName, rax; pref
0x1800e1784  test    r13b, r13b
0x1800e1787  jz      short loc_1800E17B1
0x1800e1789  call    ?removeElement@Vector@@QEAA_NPEAVObject@@@Z; Vector::removeElement(Object *)
0x1800e178e  jmp     $LN62_13
0x1800e1793  mov     r13b, r12b
0x1800e1796  mov     this, rbx; var
0x1800e1799  call    ?canConvert@XRuntime@@SA_NPEAUtagVARIANT@@@Z; XRuntime::canConvert(tagVARIANT *)
0x1800e179e  test    al, al
0x1800e17a0  jnz     loc_1800E16A5
0x1800e17a6  mov     ecx, 80020005h; hr
0x1800e17ab  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x1800e17b1  lea     this, [rsp+88h+pProtectSP]; ppref
0x1800e17b6  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800e17bb  mov     this, [rsp+88h+var_38]
0x1800e17c0  add     this, 20h ; ' '; pvargDest
0x1800e17c4  mov     baseName, [rsp+88h+pvargSrc]; pvargSrc
0x1800e17cc  call    cs:__imp_VariantCopy
0x1800e17d3  nop     dword ptr [rax+rax+00h]
0x1800e17d8  mov     ecx, eax; hr
0x1800e17da  call    ?checkhr@@YAXJ@Z; checkhr(long)
0x1800e17df  mov     r14, [rsp+88h+pProtectSP._p]
0x1800e17e4  jmp     short $LN62_13
0x1800e17e6  jmp     loc_1800E1758
0x1800e17eb  test    r13b, r13b
0x1800e17ee  jnz     short $LN62_13
0x1800e17f0  lea     pvar, [rsp+88h+pSPNew]; ppsp
0x1800e17f5  mov     baseName, [rsp+88h+pvargSrc]; pvar
0x1800e17fd  mov     this, rsi; name
0x1800e1800  call    ?New@SimpleParam@@SAXPEAVName@@PEAUtagVARIANT@@PEAPEAV1@@Z; SimpleParam::New(Name *,tagVARIANT *,SimpleParam * *)
0x1800e1805  mov     rdi, [rsp+88h+pSPNew._p]
0x1800e180a  mov     baseName, rdi; obj
0x1800e180d  mov     this, [rsp+88h+arg_0]
0x1800e1815  mov     this, [this+18h]; this
0x1800e1819  call    ?addElement@Vector@@QEAAXPEAVObject@@@Z; Vector::addElement(Object *)
0x1800e181e  nop
0x1800e181f  test    r15, r15
0x1800e1822  jz      short loc_1800E1830
0x1800e1824  xor     edx, edx; pref
0x1800e1826  lea     this, [rsp+88h+atomGI]; ppref
0x1800e182b  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800e1830  test    rbx, rbx
0x1800e1833  jz      short loc_1800E1841
0x1800e1835  xor     edx, edx; pref
0x1800e1837  lea     this, [rsp+88h+atomURI]; ppref
0x1800e183c  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800e1841  test    rsi, rsi
0x1800e1844  jz      short loc_1800E1852
0x1800e1846  xor     edx, edx; pref
0x1800e1848  lea     this, [rsp+88h+name]; ppref
0x1800e184d  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800e1852  test    rdi, rdi
0x1800e1855  jz      short loc_1800E1863
0x1800e1857  xor     edx, edx; pref
0x1800e1859  lea     this, [rsp+88h+pSPNew]; ppref
0x1800e185e  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800e1863  test    r14, r14
0x1800e1866  jz      short loc_1800E1874
0x1800e1868  xor     edx, edx; pref
0x1800e186a  lea     this, [rsp+88h+pProtectSP]; ppref
0x1800e186f  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800e1874  lea     this, [rsp+88h+pProtectSP]; ppref
0x1800e1879  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x1800e187e  lea     this, [rsp+88h+pSPNew]; ppref
0x1800e1883  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x1800e1888  lea     this, [rsp+88h+name]; ppref
0x1800e188d  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x1800e1892  lea     this, [rsp+88h+atomURI]; ppref
0x1800e1897  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x1800e189c  lea     this, [rsp+88h+atomGI]; ppref
0x1800e18a1  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x1800e18a6  lea     r11, [rsp+88h+var_28]
0x1800e18ab  mov     rbx, [r11+38h]
0x1800e18af  mov     rsi, [r11+48h]
0x1800e18b3  mov     rsp, r11
0x1800e18b6  pop     r15
0x1800e18b8  pop     r14
0x1800e18ba  pop     r13
0x1800e18bc  pop     r12
0x1800e18be  pop     rdi
0x1800e18bf  retn
0x180182c12  push    rbp
0x180182c14  sub     rsp, 20h
0x180182c18  mov     rbp, rdx
0x180182c1b  cmp     qword ptr [rbp+28h], 0
0x180182c20  jz      short loc_180182C2E
0x180182c22  xor     edx, edx; pref
0x180182c24  lea     rcx, [rbp+28h]; ppref
0x180182c28  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x180182c2d  nop
0x180182c2e  cmp     qword ptr [rbp+30h], 0
0x180182c33  jz      short loc_180182C41
0x180182c35  xor     edx, edx; pref
0x180182c37  lea     rcx, [rbp+30h]; ppref
0x180182c3b  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x180182c40  nop
0x180182c41  cmp     qword ptr [rbp+38h], 0
0x180182c46  jz      short loc_180182C54
0x180182c48  xor     edx, edx; pref
0x180182c4a  lea     rcx, [rbp+38h]; ppref
0x180182c4e  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x180182c53  nop
0x180182c54  cmp     qword ptr [rbp+40h], 0
0x180182c59  jz      short loc_180182C67
0x180182c5b  xor     edx, edx; pref
0x180182c5d  lea     rcx, [rbp+40h]; ppref
0x180182c61  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x180182c66  nop
0x180182c67  cmp     qword ptr [rbp+48h], 0
0x180182c6c  jz      short loc_180182C7A
0x180182c6e  xor     edx, edx; pref
0x180182c70  lea     rcx, [rbp+48h]; ppref
0x180182c74  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x180182c79  nop
0x180182c7a  add     rsp, 20h
0x180182c7e  pop     rbp
0x180182c7f  retn
```
