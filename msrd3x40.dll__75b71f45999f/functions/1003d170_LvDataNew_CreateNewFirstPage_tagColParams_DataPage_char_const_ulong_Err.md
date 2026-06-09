# LvDataNew::CreateNewFirstPage(tagColParams *,DataPage &,char const *,ulong,Err &)

- ea: `0x1003d170`
- end: `0x1003d2f4`
- name: `?CreateNewFirstPage@LvDataNew@@AAEKPAUtagColParams@@AAVDataPage@@PBDKAAVErr@@@Z`
- size: `388`
- prototype: `unsigned int __thiscall(LvDataNew *__hidden this, struct tagColParams *, struct DataPage *, const char *Src, unsigned int, struct Err *)`
- caller_count: `4`
- callee_count: `14`
- tags: `file_ops, installer_update`

## callers

- `0x1003c070`
- `0x1003cc10`
- `0x1003d300`
- `0x1003ee10`

## callees

- `0x1000da40`
- `0x1000f750`
- `0x10024ee0`
- `0x10024f60`
- `0x10025290`
- `0x10025ee0`
- `0x1003c9a0`
- `0x1003d170`
- `0x1003ff40`
- `0x1005d1d0`
- `0x1005e3b0`
- `0x1005e7e8`
- `0x1005f064`
- `0x1005f07c`

## pseudocode

```c
unsigned int __thiscall LvDataNew::CreateNewFirstPage(
        LvDataNew *this,
        struct tagColParams *a2,
        struct DataPage *a3,
        const char *Src,
        size_t a5,
        struct Err *a6)
{
  unsigned int v7; // edi
  bool v8; // zf
  size_t v9; // eax
  int v10; // ecx
  int v11; // ecx
  Array *v12; // ecx
  int v13; // eax
  int v15; // [esp+10h] [ebp-2Ch] BYREF
  int v16; // [esp+14h] [ebp-28h] BYREF
  void *Block; // [esp+1Ch] [ebp-20h]
  void *v18; // [esp+20h] [ebp-1Ch]
  char v19[4]; // [esp+24h] [ebp-18h] BYREF
  size_t Size; // [esp+28h] [ebp-14h]
  int v21; // [esp+38h] [ebp-4h]

  v7 = 0;
  LvDataNew::AllocatePage(this, this, a3, a6);
  v8 = (*(_BYTE *)a6 & 8) == 0;
  if ( (*(_BYTE *)a6 & 8) == 0 )
  {
    *(_DWORD *)v19 = 0;
    if ( Src )
    {
      v9 = a5;
    }
    else
    {
      Src = (char *)this + 4;
      v9 = *((_DWORD *)this + 516);
    }
    Size = v9;
    v7 = DataPage::Insert(a3, (const unsigned __int8 *)v19, 4u);
    if ( v7 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_jet_3xlv>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_jet_3xlv>::GetImpl'::`2'::impl) )
        DataPage::Resize(a3, v7, 1, Size + 4);
      if ( (*(_BYTE *)a6 & 8) != 0 )
        goto LABEL_15;
      DataPage::RecordAddress(a3, v7, &v16);
      memcpy((void *)(v16 + 4), Src, Size);
    }
    else
    {
      Err::SetError(a6, -1012, v10);
    }
    if ( (*(_BYTE *)a6 & 8) == 0 )
    {
      v11 = *(_DWORD *)a3;
      *(_DWORD *)(v11 + 4 * *(_DWORD *)(*(_DWORD *)a3 + 24) + 28) |= 8u;
      ++*(_DWORD *)(v11 + 64);
      if ( (*(_BYTE *)a6 & 8) == 0 )
      {
        v12 = (Array *)*((_DWORD *)this + 518);
        *(_DWORD *)v19 = v7;
        Array::Set(v12, 0, v19, a6);
        if ( (*(_BYTE *)a6 & 8) == 0 )
        {
          *((_DWORD *)this + 514) = 0;
LABEL_23:
          v8 = (*(_BYTE *)a6 & 8) == 0;
          goto LABEL_24;
        }
      }
    }
LABEL_15:
    v15 = 1;
    v21 = 0;
    if ( *(_DWORD *)a3 )
      v13 = *(_DWORD *)(*(_DWORD *)a3 + 12);
    else
      v13 = 0;
    Transaction::FreePage(*((_DWORD *)this + 523), v13, 1, &v15);
    if ( (v15 & 0xFFFFFFFE) != 0 )
    {
      if ( Block )
        operator delete[](Block);
      if ( v18 )
        operator delete[](v18);
    }
    goto LABEL_23;
  }
LABEL_24:
  if ( !v8 )
    return 0;
  return v7;
}

```

## disassembly

```asm
0x1003d170  mov     edi, edi
0x1003d172  push    ebp
0x1003d173  mov     ebp, esp
0x1003d175  push    0FFFFFFFFh
0x1003d177  push    offset ?RecordAddress@TableMover@@UAEPAVRecord@@AAVErr@@@Z_SEH
0x1003d17c  mov     eax, large fs:0
0x1003d182  push    eax
0x1003d183  sub     esp, 20h
0x1003d186  push    ebx
0x1003d187  push    esi
0x1003d188  push    edi
0x1003d189  mov     eax, ___security_cookie
0x1003d18e  xor     eax, ebp
0x1003d190  push    eax
0x1003d191  lea     eax, [ebp+var_C]
0x1003d194  mov     large fs:0, eax
0x1003d19a  mov     ebx, ecx
0x1003d19c  mov     esi, [ebp+arg_10]
0x1003d19f  xor     edi, edi
0x1003d1a1  push    esi; struct Err *
0x1003d1a2  push    [ebp+arg_4]; struct DataPage *
0x1003d1a5  push    ecx; struct tagColParams *
0x1003d1a6  call    ?AllocatePage@LvDataNew@@QAEKPAUtagColParams@@AAVDataPage@@AAVErr@@@Z; LvDataNew::AllocatePage(tagColParams *,DataPage &,Err &)
0x1003d1ab  test    byte ptr [esi], 8
0x1003d1ae  jnz     loc_1003D2D6
0x1003d1b4  mov     dword ptr [ebp+var_18], edi
0x1003d1b7  cmp     [ebp+Src], edi
0x1003d1ba  jnz     short loc_1003D1CA
0x1003d1bc  lea     eax, [ebx+4]
0x1003d1bf  mov     [ebp+Src], eax
0x1003d1c2  mov     eax, [ebx+810h]
0x1003d1c8  jmp     short loc_1003D1CD
0x1003d1ca  mov     eax, [ebp+arg_C]
0x1003d1cd  mov     ecx, [ebp+arg_4]; this
0x1003d1d0  mov     [ebp+Size], eax
0x1003d1d3  lea     eax, [ebp+var_18]
0x1003d1d6  push    4; unsigned int
0x1003d1d8  push    eax; Src
0x1003d1d9  call    ?Insert@DataPage@@QAEKPBEI@Z; DataPage::Insert(uchar const *,uint)
0x1003d1de  mov     edi, eax
0x1003d1e0  test    edi, edi
0x1003d1e2  jnz     short loc_1003D1F3
0x1003d1e4  push    ecx
0x1003d1e5  push    0FFFFFC0Ch
0x1003d1ea  mov     ecx, esi
0x1003d1ec  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1003d1f1  jmp     short loc_1003D23A
0x1003d1f3  mov     ecx, offset ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_jet_3xlv@@@wil@@CGAAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_jet_3xlv@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_jet_3xlv> `wil::Feature<__WilFeatureTraits_Feature_Servicing_jet_3xlv>::GetImpl(void)'::`2'::impl
0x1003d1f8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_jet_3xlv@@@details@wil@@QAE_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_jet_3xlv>::__private_IsEnabled(void)
0x1003d1fd  test    al, al
0x1003d1ff  jz      short loc_1003D213
0x1003d201  mov     eax, [ebp+Size]
0x1003d204  mov     ecx, [ebp+arg_4]
0x1003d207  add     eax, 4
0x1003d20a  push    eax
0x1003d20b  push    1
0x1003d20d  push    edi
0x1003d20e  call    ?Resize@DataPage@@QAE?AW4DPBool@@KW42@I@Z; DataPage::Resize(ulong,DPBool,uint)
0x1003d213  test    byte ptr [esi], 8
0x1003d216  jnz     short loc_1003D27A
0x1003d218  mov     ecx, [ebp+arg_4]
0x1003d21b  lea     eax, [ebp+var_28]
0x1003d21e  push    eax
0x1003d21f  push    edi
0x1003d220  call    ?RecordAddress@DataPage@@QBE?AW4RowType@@KPAVRecord@@@Z; DataPage::RecordAddress(ulong,Record *)
0x1003d225  push    [ebp+Size]; Size
0x1003d228  mov     eax, [ebp+var_28]
0x1003d22b  push    [ebp+Src]; Src
0x1003d22e  add     eax, 4
0x1003d231  push    eax; void *
0x1003d232  call    _memcpy
0x1003d237  add     esp, 0Ch
0x1003d23a  test    byte ptr [esi], 8
0x1003d23d  jnz     short loc_1003D27A
0x1003d23f  mov     eax, [ebp+arg_4]
0x1003d242  mov     ecx, [eax]
0x1003d244  mov     eax, [ecx+18h]
0x1003d247  or      dword ptr [ecx+eax*4+1Ch], 8
0x1003d24c  inc     dword ptr [ecx+40h]
0x1003d24f  test    byte ptr [esi], 8
0x1003d252  jnz     short loc_1003D27A
0x1003d254  mov     ecx, [ebx+818h]; this
0x1003d25a  lea     eax, [ebp+var_18]
0x1003d25d  push    esi; struct Err *
0x1003d25e  push    eax; Src
0x1003d25f  push    0; int
0x1003d261  mov     dword ptr [ebp+var_18], edi
0x1003d264  call    ?Set@Array@@QAEXHPADAAVErr@@@Z; Array::Set(int,char *,Err &)
0x1003d269  test    byte ptr [esi], 8
0x1003d26c  jnz     short loc_1003D27A
0x1003d26e  mov     dword ptr [ebx+808h], 0
0x1003d278  jmp     short loc_1003D2D3
0x1003d27a  mov     [ebp+var_2C], 1
0x1003d281  mov     eax, [ebp+arg_4]
0x1003d284  mov     [ebp+var_4], 0
0x1003d28b  mov     eax, [eax]
0x1003d28d  test    eax, eax
0x1003d28f  jz      short loc_1003D296
0x1003d291  mov     eax, [eax+0Ch]
0x1003d294  jmp     short loc_1003D298
0x1003d296  xor     eax, eax
0x1003d298  lea     ecx, [ebp+var_2C]
0x1003d29b  push    ecx
0x1003d29c  mov     ecx, [ebx+82Ch]
0x1003d2a2  push    1
0x1003d2a4  push    eax
0x1003d2a5  call    ?FreePage@Transaction@@QAEXKW4FreeDisposition@@AAVErr@@@Z; Transaction::FreePage(ulong,FreeDisposition,Err &)
0x1003d2aa  test    [ebp+var_2C], 0FFFFFFFEh
0x1003d2b1  jz      short loc_1003D2D3
0x1003d2b3  mov     eax, [ebp+Block]
0x1003d2b6  test    eax, eax
0x1003d2b8  jz      short loc_1003D2C3
0x1003d2ba  push    eax; Block
0x1003d2bb  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1003d2c0  add     esp, 4
0x1003d2c3  mov     eax, [ebp+var_1C]
0x1003d2c6  test    eax, eax
0x1003d2c8  jz      short loc_1003D2D3
0x1003d2ca  push    eax; Block
0x1003d2cb  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1003d2d0  add     esp, 4
0x1003d2d3  test    byte ptr [esi], 8
0x1003d2d6  mov     eax, 0
0x1003d2db  cmovnz  edi, eax
0x1003d2de  mov     eax, edi
0x1003d2e0  mov     ecx, [ebp+var_C]
0x1003d2e3  mov     large fs:0, ecx
0x1003d2ea  pop     ecx
0x1003d2eb  pop     edi
0x1003d2ec  pop     esi
0x1003d2ed  pop     ebx
0x1003d2ee  mov     esp, ebp
0x1003d2f0  pop     ebp
0x1003d2f1  retn    14h
0x10061090  lea     ecx, [ebp+var_2C]; this
0x10061093  jmp     ??1Err@@QAE@XZ; Err::~Err(void)
0x1006109d  nop
0x1006109e  nop
0x1006109f  mov     edx, [esp-4+arg_4]
0x100610a3  lea     eax, [edx+0Ch]
0x100610a6  mov     ecx, [edx-30h]
0x100610a9  xor     ecx, eax; StackCookie
0x100610ab  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100610b0  mov     eax, offset stru_10063C28
0x100610b5  jmp     ___CxxFrameHandler3
```
