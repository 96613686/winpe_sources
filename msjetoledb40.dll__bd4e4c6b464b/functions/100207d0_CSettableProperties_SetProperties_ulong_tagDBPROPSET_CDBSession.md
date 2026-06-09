# CSettableProperties::SetProperties(ulong,tagDBPROPSET *,CDBSession *)

- ea: `0x100207d0`
- end: `0x10020a3e`
- name: `?SetProperties@CSettableProperties@@QAEJKPAUtagDBPROPSET@@PAVCDBSession@@@Z`
- size: `622`
- prototype: `int __thiscall(CSettableProperties *__hidden this, unsigned int, struct tagDBPROPSET *, struct CDBSession *)`
- caller_count: `19`
- callee_count: `2`
- tags: ``

## callers

- `0x1000e140`
- `0x10014d90`
- `0x100153e0`
- `0x10017580`
- `0x1001a970`
- `0x1001af60`
- `0x1001b4a0`
- `0x1001d7f0`
- `0x1001e350`
- `0x1001ebc0`
- `0x10025180`
- `0x1002e3e0`
- `0x10034e00`
- `0x100407e0`
- `0x10040c30`
- `0x10044ee0`
- `0x10045d20`
- `0x100467c0`
- `0x10046bb0`

## callees

- `0x1001fe00`
- `0x100207d0`

## pseudocode

```c
int __thiscall CSettableProperties::SetProperties(
        CSettableProperties *this,
        unsigned int a2,
        struct tagDBPROPSET *a3,
        struct CDBSession *a4)
{
  CSettableProperties *v4; // esi
  int v5; // eax
  int v6; // edx
  int v7; // ecx
  int v8; // edi
  struct tagDBPROPSET *v9; // ecx
  int v10; // edi
  int v11; // eax
  __int128 v12; // xmm0
  GUID *p_guidPropertySet; // edx
  unsigned int v14; // esi
  __int128 *v15; // eax
  bool v16; // cf
  int v17; // eax
  ULONG v18; // edi
  int v19; // esi
  struct tagDBPROPSET *v20; // eax
  DBPROP *rgProperties; // eax
  int v22; // ecx
  bool v23; // zf
  int v24; // eax
  int v26; // [esp+14h] [ebp-3Ch]
  int v27; // [esp+18h] [ebp-38h]
  struct tagDBPROPSET *v28; // [esp+1Ch] [ebp-34h]
  int v29; // [esp+20h] [ebp-30h]
  int v30; // [esp+24h] [ebp-2Ch]
  int v31; // [esp+28h] [ebp-28h]
  int v32; // [esp+2Ch] [ebp-24h]
  unsigned int v34; // [esp+34h] [ebp-1Ch]
  JoltProperties *v35; // [esp+38h] [ebp-18h]
  __int128 v36; // [esp+40h] [ebp-10h] BYREF

  v4 = this;
  v5 = 0;
  v34 = 0;
  v6 = 0;
  v7 = 0;
  v29 = 0;
  v8 = -2147217887;
  v26 = 0;
  v27 = 0;
  if ( a2 )
  {
    do
    {
      v31 = v5;
      v32 = v7;
      v30 = v6;
      v9 = &a3[v34];
      v28 = v9;
      if ( v9->cProperties || v9->rgProperties )
      {
        v10 = 0;
        while ( 1 )
        {
          v11 = *((_DWORD *)v4 + v10 + 2);
          v35 = (JoltProperties *)v11;
          if ( v11 )
            break;
LABEL_14:
          if ( (unsigned int)++v10 >= 2 )
          {
            v18 = 0;
            v6 = v30;
            v19 = 265946;
            v5 = v31;
            v27 = v32;
            if ( v28->cProperties )
            {
              v20 = &a3[v34];
              do
              {
                rgProperties = v20->rgProperties;
                v27 = v32;
                v22 = v18;
                v6 = v30;
                v23 = rgProperties[v18].dwOptions == 0;
                rgProperties[v18].dwStatus = 1;
                if ( v23 )
                  v19 = -2147217887;
                ++v18;
                v28->rgProperties[v22].colid = DB_NULLID;
                v7 = v32;
                v20 = &a3[v34];
              }
              while ( v18 < v28->cProperties );
              v5 = v31;
            }
            else
            {
              v7 = v32;
            }
            v29 = 1;
            if ( v19 == -2147217887 )
              v5 = 1;
            v4 = this;
            v26 = v5;
            goto LABEL_34;
          }
        }
        v12 = *(_OWORD *)(v11 + 20);
        p_guidPropertySet = &v9->guidPropertySet;
        v14 = 12;
        v15 = &v36;
        v36 = v12;
        do
        {
          if ( p_guidPropertySet->Data1 != *(_DWORD *)v15 )
          {
            v9 = &a3[v34];
            v4 = this;
            goto LABEL_14;
          }
          p_guidPropertySet = (GUID *)((char *)p_guidPropertySet + 4);
          v15 = (__int128 *)((char *)v15 + 4);
          v16 = v14 < 4;
          v14 -= 4;
        }
        while ( !v16 );
        v4 = this;
        v17 = JoltProperties::SetProperties(v35, v28, this, a4);
        v6 = v17;
        if ( v17 >= 0 && v17 != 265946 )
        {
          v5 = v26;
          if ( *((_DWORD *)this + 1) == 1 )
          {
            v7 = 1;
            v27 = 1;
            goto LABEL_34;
          }
LABEL_31:
          v7 = v27;
          goto LABEL_34;
        }
        v24 = *((_DWORD *)this + 1);
        v29 = 1;
        if ( v24 )
        {
          if ( v24 != 1 )
            goto LABEL_32;
          v5 = v26;
          if ( v6 == 265946 )
          {
            v7 = 1;
            v27 = 1;
            goto LABEL_34;
          }
          goto LABEL_31;
        }
        v7 = v27;
        if ( v6 != -2147217887 )
          goto LABEL_33;
        v5 = 1;
        v26 = 1;
      }
      else
      {
LABEL_32:
        v7 = v27;
LABEL_33:
        v5 = v26;
      }
LABEL_34:
      ++v34;
    }
    while ( v34 < a2 );
    v8 = -2147217887;
  }
  if ( !*((_DWORD *)v4 + 1) )
  {
    if ( v5 == 1 )
      return -2147217887;
    if ( v29 == 1 )
      return 265946;
    return v6;
  }
  if ( v29 != 1 )
    return v6;
  if ( v7 == 1 )
    return 265946;
  return v8;
}

```

## disassembly

```asm
0x100207d0  mov     edi, edi
0x100207d2  push    ebp
0x100207d3  mov     ebp, esp
0x100207d5  and     esp, 0FFFFFFF0h
0x100207d8  sub     esp, 48h
0x100207db  push    esi
0x100207dc  push    edi
0x100207dd  xor     edi, edi
0x100207df  mov     esi, ecx
0x100207e1  xor     eax, eax
0x100207e3  mov     [esp+50h+var_1C], edi
0x100207e7  xor     edx, edx
0x100207e9  mov     [esp+50h+var_20], esi
0x100207ed  xor     ecx, ecx
0x100207ef  mov     [esp+50h+var_30], edx
0x100207f3  mov     edi, 80040E21h
0x100207f8  mov     [esp+50h+var_3C], eax
0x100207fc  mov     [esp+50h+var_38], ecx
0x10020800  mov     [esp+50h+var_14], edi
0x10020804  cmp     [ebp+arg_0], eax
0x10020807  jbe     loc_100209EC
0x1002080d  nop     dword ptr [eax]
0x10020810  mov     [esp+50h+var_28], eax
0x10020814  mov     eax, [esp+50h+var_1C]
0x10020818  mov     [esp+50h+var_24], ecx
0x1002081c  mov     ecx, [ebp+arg_4]
0x1002081f  mov     [esp+50h+var_2C], edx
0x10020823  lea     eax, [eax+eax*2]
0x10020826  cmp     dword ptr [ecx+eax*8+4], 0
0x1002082b  lea     ecx, [ecx+eax*8]
0x1002082e  mov     [esp+50h+var_34], ecx
0x10020832  jnz     short loc_1002083D
0x10020834  cmp     dword ptr [ecx], 0
0x10020837  jz      loc_100209CD
0x1002083d  xor     edi, edi
0x1002083f  nop
0x10020840  mov     eax, [esi+edi*4+8]
0x10020844  mov     [esp+50h+var_18], eax
0x10020848  test    eax, eax
0x1002084a  jz      short loc_100208C2
0x1002084c  movups  xmm0, xmmword ptr [eax+14h]
0x10020850  lea     edx, [ecx+8]
0x10020853  mov     esi, 0Ch
0x10020858  lea     eax, [esp+50h+var_10]
0x1002085c  movups  [esp+50h+var_10], xmm0
0x10020861  mov     ecx, [edx]
0x10020863  cmp     ecx, [eax]
0x10020865  jnz     short loc_100208BA
0x10020867  add     edx, 4
0x1002086a  add     eax, 4
0x1002086d  sub     esi, 4
0x10020870  jnb     short loc_10020861
0x10020872  push    [ebp+arg_8]; struct CDBSession *
0x10020875  mov     esi, [esp+54h+var_20]
0x10020879  mov     eax, [esp+54h+var_34]
0x1002087d  mov     ecx, [esp+54h+var_18]; this
0x10020881  push    esi; struct CSettableProperties *
0x10020882  push    eax; struct tagDBPROPSET *
0x10020883  call    ?SetProperties@JoltProperties@@QAEJPAUtagDBPROPSET@@PAVCSettableProperties@@PAVCDBSession@@@Z; JoltProperties::SetProperties(tagDBPROPSET *,CSettableProperties *,CDBSession *)
0x10020888  mov     edx, eax
0x1002088a  test    edx, edx
0x1002088c  js      loc_10020961
0x10020892  cmp     edx, 40EDAh
0x10020898  jz      loc_10020961
0x1002089e  cmp     dword ptr [esi+4], 1
0x100208a2  mov     eax, [esp+50h+var_3C]
0x100208a6  jnz     loc_100209C7
0x100208ac  mov     ecx, 1
0x100208b1  mov     [esp+50h+var_38], ecx
0x100208b5  jmp     loc_100209D5
0x100208ba  mov     ecx, [esp+50h+var_34]
0x100208be  mov     esi, [esp+50h+var_20]
0x100208c2  inc     edi
0x100208c3  cmp     edi, 2
0x100208c6  jb      loc_10020840
0x100208cc  mov     ecx, [esp+50h+var_24]
0x100208d0  xor     edi, edi
0x100208d2  mov     edx, [esp+50h+var_2C]
0x100208d6  mov     esi, 40EDAh
0x100208db  mov     eax, [esp+50h+var_28]
0x100208df  mov     [esp+50h+var_38], ecx
0x100208e3  mov     ecx, [esp+50h+var_34]
0x100208e7  cmp     [ecx+4], edi
0x100208ea  jbe     loc_100209A3
0x100208f0  mov     eax, ecx
0x100208f2  mov     ecx, [esp+50h+var_24]
0x100208f6  mov     eax, [eax]
0x100208f8  mov     [esp+50h+var_38], ecx
0x100208fc  mov     ecx, [esp+50h+var_28]
0x10020900  mov     [esp+50h+var_3C], ecx
0x10020904  imul    ecx, edi, 34h ; '4'
0x10020907  mov     edx, [esp+50h+var_2C]
0x1002090b  mov     [esp+50h+var_2C], edx
0x1002090f  cmp     dword ptr [ecx+eax+4], 0
0x10020914  mov     dword ptr [ecx+eax+8], 1
0x1002091c  mov     eax, [esp+50h+var_34]
0x10020920  movups  xmm0, xmmword ptr ds:_DB_NULLID.uGuid
0x10020927  cmovz   esi, [esp+50h+var_14]
0x1002092c  inc     edi
0x1002092d  mov     eax, [eax]
0x1002092f  movups  xmmword ptr [ecx+eax+0Ch], xmm0
0x10020934  movq    xmm0, qword ptr ds:_DB_NULLID.eKind
0x1002093c  movq    qword ptr [ecx+eax+1Ch], xmm0
0x10020942  mov     eax, [esp+50h+var_3C]
0x10020946  mov     ecx, [esp+50h+var_38]
0x1002094a  mov     [esp+50h+var_28], eax
0x1002094e  mov     eax, [esp+50h+var_34]
0x10020952  mov     [esp+50h+var_24], ecx
0x10020956  cmp     edi, [eax+4]
0x10020959  jb      short loc_100208F2
0x1002095b  mov     eax, [esp+50h+var_3C]
0x1002095f  jmp     short loc_100209A7
0x10020961  mov     eax, [esi+4]
0x10020964  mov     [esp+50h+var_30], 1
0x1002096c  test    eax, eax
0x1002096e  jnz     short loc_10020987
0x10020970  mov     ecx, [esp+50h+var_38]
0x10020974  cmp     edx, 80040E21h
0x1002097a  jnz     short loc_100209D1
0x1002097c  mov     eax, 1
0x10020981  mov     [esp+50h+var_3C], eax
0x10020985  jmp     short loc_100209D5
0x10020987  cmp     eax, 1
0x1002098a  jnz     short loc_100209CD
0x1002098c  mov     eax, [esp+50h+var_3C]
0x10020990  cmp     edx, 40EDAh
0x10020996  jnz     short loc_100209C7
0x10020998  mov     ecx, 1
0x1002099d  mov     [esp+50h+var_38], ecx
0x100209a1  jmp     short loc_100209D5
0x100209a3  mov     ecx, [esp+50h+var_38]
0x100209a7  cmp     esi, 80040E21h
0x100209ad  mov     [esp+50h+var_30], 1
0x100209b5  mov     esi, 1
0x100209ba  cmovz   eax, esi
0x100209bd  mov     esi, [esp+50h+var_20]
0x100209c1  mov     [esp+50h+var_3C], eax
0x100209c5  jmp     short loc_100209D5
0x100209c7  mov     ecx, [esp+50h+var_38]
0x100209cb  jmp     short loc_100209D5
0x100209cd  mov     ecx, [esp+50h+var_38]
0x100209d1  mov     eax, [esp+50h+var_3C]
0x100209d5  mov     edi, [esp+50h+var_1C]
0x100209d9  inc     edi
0x100209da  mov     [esp+50h+var_1C], edi
0x100209de  cmp     edi, [ebp+arg_0]
0x100209e1  jb      loc_10020810
0x100209e7  mov     edi, 80040E21h
0x100209ec  cmp     dword ptr [esi+4], 0
0x100209f0  jnz     short loc_10020A18
0x100209f2  cmp     eax, 1
0x100209f5  jnz     short loc_10020A04
0x100209f7  mov     eax, 80040E21h
0x100209fc  pop     edi
0x100209fd  pop     esi
0x100209fe  mov     esp, ebp
0x10020a00  pop     ebp
0x10020a01  retn    0Ch
0x10020a04  cmp     [esp+50h+var_30], 1
0x10020a09  jnz     short loc_10020A34
0x10020a0b  mov     eax, 40EDAh
0x10020a10  pop     edi
0x10020a11  pop     esi
0x10020a12  mov     esp, ebp
0x10020a14  pop     ebp
0x10020a15  retn    0Ch
0x10020a18  cmp     [esp+50h+var_30], 1
0x10020a1d  jnz     short loc_10020A34
0x10020a1f  mov     eax, 40EDAh
0x10020a24  cmp     ecx, 1
0x10020a27  cmovz   edi, eax
0x10020a2a  mov     eax, edi
0x10020a2c  pop     edi
0x10020a2d  pop     esi
0x10020a2e  mov     esp, ebp
0x10020a30  pop     ebp
0x10020a31  retn    0Ch
0x10020a34  pop     edi
0x10020a35  mov     eax, edx
0x10020a37  pop     esi
0x10020a38  mov     esp, ebp
0x10020a3a  pop     ebp
0x10020a3b  retn    0Ch
```
