# CRowsetProperties::ValidateStateForJetOpenTable(ulong &,_GUID const &,eJetCursorType &,int)

- ea: `0x10021070`
- end: `0x100215a6`
- name: `?ValidateStateForJetOpenTable@CRowsetProperties@@QAEJAAKABU_GUID@@AAW4eJetCursorType@@H@Z`
- size: `1334`
- prototype: `int __thiscall(CRowsetProperties *__hidden this, unsigned int *, const struct _GUID *, enum eJetCursorType *, int)`
- caller_count: `4`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x1000fcf0`
- `0x10025180`
- `0x10028340`
- `0x10044ee0`

## callees

- `0x1001f2d0`
- `0x1001fc50`
- `0x10020dd0`
- `0x10020e30`
- `0x10021070`

## pseudocode

```c
int __thiscall CRowsetProperties::ValidateStateForJetOpenTable(
        CRowsetProperties *this,
        unsigned int *a2,
        const struct _GUID *a3,
        enum eJetCursorType *a4,
        int a5)
{
  const struct _GUID *v5; // ebx
  CRowsetProperties *v6; // esi
  int result; // eax
  int v8; // eax
  int v9; // eax
  JoltProperties *v10; // esi
  int v11; // eax
  int v12; // eax
  GUID *v13; // ecx
  const struct _GUID *v14; // edx
  unsigned int v15; // esi
  bool v16; // cf
  GUID *v17; // ecx
  const struct _GUID *v18; // edx
  unsigned int v19; // esi
  GUID *v20; // ecx
  const struct _GUID *v21; // edx
  unsigned int v22; // esi
  GUID *v23; // ecx
  unsigned int v24; // edx
  enum eJetCursorType *v25; // ebx
  JoltProperties *v26; // esi
  CRowsetProperties *v27; // ebx
  JoltProperties *v28; // esi
  int v29; // eax
  JoltProperties *v30; // esi
  unsigned int v31; // [esp+Ch] [ebp-40h] BYREF
  unsigned int v32; // [esp+10h] [ebp-3Ch] BYREF
  BOOL v33; // [esp+14h] [ebp-38h]
  BOOL v34; // [esp+18h] [ebp-34h]
  BOOL v35; // [esp+1Ch] [ebp-30h]
  BOOL v36; // [esp+20h] [ebp-2Ch]
  BOOL v37; // [esp+24h] [ebp-28h]
  int v38; // [esp+28h] [ebp-24h]
  int v39; // [esp+2Ch] [ebp-20h]
  JoltProperties *v40; // [esp+30h] [ebp-1Ch] BYREF
  int v41; // [esp+34h] [ebp-18h]
  CRowsetProperties *v42; // [esp+38h] [ebp-14h]
  BOOL v43; // [esp+3Ch] [ebp-10h]
  BOOL v44; // [esp+40h] [ebp-Ch]
  int v45; // [esp+44h] [ebp-8h]
  BOOL v46; // [esp+48h] [ebp-4h]

  v5 = a3;
  v6 = this;
  v42 = this;
  v45 = 0;
  *a2 = 0;
  *(_DWORD *)a4 = 0xFFFF;
  if ( a5 == 1 )
  {
    result = CRowsetProperties::SetInterfacesFromREFIID(this, a3);
    v45 = result;
    if ( result < 0 )
      return result;
    v6 = v42;
  }
  v40 = (JoltProperties *)*((_DWORD *)v6 + 3);
  if ( JoltProperties::BinarySearch(v40, 0xFFu, &v31) >= 0
    && (v8 = *(_DWORD *)(*((_DWORD *)v6 + 3) + 16), *(_WORD *)(v8 + 48 * v31 + 16) == 3) )
  {
    v9 = *(_DWORD *)(v8 + 48 * v31 + 24);
  }
  else
  {
    v9 = 0;
  }
  v10 = (JoltProperties *)*((_DWORD *)v6 + 2);
  v41 = v9;
  if ( JoltProperties::BinarySearch(v10, 0x75u, &v31) >= 0
    && (v11 = *((_DWORD *)v10 + 4), *(_WORD *)(v11 + 48 * v31 + 16) == 3) )
  {
    v39 = *(_DWORD *)(v11 + 48 * v31 + 24);
  }
  else
  {
    v39 = 0;
  }
  if ( JoltProperties::BinarySearch(v10, 0x47u, &v31) >= 0
    && (v12 = *((_DWORD *)v10 + 4), *(_WORD *)(v12 + 48 * v31 + 16) == 3) )
  {
    v38 = *(_DWORD *)(v12 + 48 * v31 + 24);
  }
  else
  {
    v38 = 0;
  }
  v37 = JoltProperties::BinarySearch(v10, 0x58u, &v31) >= 0
     && *(_WORD *)(*((_DWORD *)v10 + 4) + 48 * v31 + 24) == 0xFFFF;
  v36 = JoltProperties::BinarySearch(v10, 0x5Au, &v31) >= 0
     && *(_WORD *)(*((_DWORD *)v10 + 4) + 48 * v31 + 24) == 0xFFFF;
  v35 = JoltProperties::BinarySearch(v10, 0x59u, &v31) >= 0
     && *(_WORD *)(*((_DWORD *)v10 + 4) + 48 * v31 + 24) == 0xFFFF;
  v46 = JoltProperties::BinarySearch(v10, 0x7Fu, &v31) >= 0
     && *(_WORD *)(*((_DWORD *)v10 + 4) + 48 * v31 + 24) == 0xFFFF;
  v34 = JoltProperties::BinarySearch(v10, 0x15u, &v31) >= 0
     && *(_WORD *)(*((_DWORD *)v10 + 4) + 48 * v31 + 24) == 0xFFFF;
  v33 = JoltProperties::BinarySearch(v10, 0x12u, &v31) >= 0
     && *(_WORD *)(*((_DWORD *)v10 + 4) + 48 * v31 + 24) == 0xFFFF;
  v44 = JoltProperties::BinarySearch(v10, 0x82u, &v31) >= 0
     && *(_WORD *)(*((_DWORD *)v10 + 4) + 48 * v31 + 24) == 0xFFFF;
  v43 = JoltProperties::BinarySearch(v10, 0x85u, &v31) >= 0
     && *(_WORD *)(*((_DWORD *)v10 + 4) + 48 * v31 + 24) == 0xFFFF;
  v31 = JoltProperties::BinarySearch(v10, 0x13u, &v31) >= 0
     && *(_WORD *)(*((_DWORD *)v10 + 4) + 48 * v31 + 24) == 0xFFFF;
  v32 = JoltProperties::BinarySearch(v10, 0xEu, &v32) >= 0 && *(_WORD *)(*((_DWORD *)v10 + 4) + 48 * v32 + 24) == 0xFFFF;
  if ( !a5 )
  {
    v13 = &IID_IRowsetLocate;
    v14 = a3;
    v15 = 12;
    while ( v13->Data1 == v14->Data1 )
    {
      v13 = (GUID *)((char *)v13 + 4);
      v14 = (const struct _GUID *)((char *)v14 + 4);
      v16 = v15 < 4;
      v15 -= 4;
      if ( v16 )
      {
        v44 = 1;
        goto LABEL_63;
      }
    }
    v17 = &IID_IRowsetScroll;
    v18 = a3;
    v19 = 12;
    while ( v17->Data1 == v18->Data1 )
    {
      v17 = (GUID *)((char *)v17 + 4);
      v18 = (const struct _GUID *)((char *)v18 + 4);
      v16 = v19 < 4;
      v19 -= 4;
      if ( v16 )
      {
        v43 = 1;
        goto LABEL_63;
      }
    }
    v20 = &IID_IRowsetChange;
    v21 = a3;
    v22 = 12;
    while ( v20->Data1 == v21->Data1 )
    {
      v20 = (GUID *)((char *)v20 + 4);
      v21 = (const struct _GUID *)((char *)v21 + 4);
      v16 = v22 < 4;
      v22 -= 4;
      if ( v16 )
      {
        v46 = 1;
        goto LABEL_63;
      }
    }
    v23 = &IID_IRowsetUpdate;
    v24 = 12;
    while ( v23->Data1 == v5->Data1 )
    {
      v23 = (GUID *)((char *)v23 + 4);
      v5 = (const struct _GUID *)((char *)v5 + 4);
      v16 = v24 < 4;
      v24 -= 4;
      if ( v16 )
      {
        v46 = 1;
        break;
      }
    }
  }
LABEL_63:
  if ( v41 )
  {
    if ( v41 != 1 )
    {
      if ( v41 == 2 )
      {
        JoltProperties::GetIntValue(v40, 0xFEu, a2);
        *(_DWORD *)a4 = CRowsetProperties::InterrogategrbitForCursorType(*a2);
      }
      goto LABEL_88;
    }
    JoltProperties::GetIntValue(v40, 0xFEu, a2);
    v25 = a4;
    *(_DWORD *)a4 = CRowsetProperties::InterrogategrbitForCursorType(*a2);
  }
  else
  {
    v25 = a4;
  }
  v26 = (JoltProperties *)*((_DWORD *)v42 + 2);
  if ( JoltProperties::BinarySearch(v26, 0xBBu, (unsigned int *)&v40) >= 0
    && *(_WORD *)(*((_DWORD *)v26 + 4) + 48 * (_DWORD)v40 + 24) == 0xFFFF )
  {
    *(_DWORD *)v25 = 4;
    *a2 = 56;
  }
  else if ( v39 || v38 != 1 || v46 )
  {
    *(_DWORD *)v25 = 3;
    *a2 |= 0x30u;
  }
  else if ( v37 )
  {
    *(_DWORD *)v25 = 2;
    *a2 |= 0x34u;
  }
  else if ( v36 || v35 || v34 || v33 || v44 || v43 || v32 == 1 || v31 == 1 )
  {
    *(_DWORD *)v25 = 1;
    *a2 |= 0x20u;
  }
  else
  {
    *(_DWORD *)v25 = 0;
  }
LABEL_88:
  v27 = v42;
  v28 = (JoltProperties *)*((_DWORD *)v42 + 3);
  if ( JoltProperties::BinarySearch(v28, 0x107u, &v31) >= 0 )
  {
    v29 = *((_DWORD *)v28 + 4);
    if ( *(_WORD *)(v29 + 48 * v31 + 16) == 3 && *(_DWORD *)(v29 + 48 * v31 + 24) == 1 )
      *a2 |= 0x400000u;
  }
  v30 = (JoltProperties *)*((_DWORD *)v27 + 3);
  if ( JoltProperties::BinarySearch(v30, 0x117u, &v31) < 0 )
    return v45;
  result = v45;
  if ( *(_WORD *)(*((_DWORD *)v30 + 4) + 48 * v31 + 24) == 0xFFFF )
    *a2 |= 0x80u;
  return result;
}

```

## disassembly

```asm
0x10021070  mov     edi, edi
0x10021072  push    ebp
0x10021073  mov     ebp, esp
0x10021075  sub     esp, 40h
0x10021078  cmp     [ebp+arg_C], 1
0x1002107c  mov     eax, [ebp+arg_8]
0x1002107f  push    ebx
0x10021080  mov     ebx, [ebp+arg_4]
0x10021083  push    esi
0x10021084  push    edi
0x10021085  mov     edi, [ebp+arg_0]
0x10021088  mov     esi, ecx
0x1002108a  mov     [ebp+var_14], esi
0x1002108d  mov     [ebp+var_8], 0
0x10021094  mov     dword ptr [edi], 0
0x1002109a  mov     dword ptr [eax], 0FFFFh
0x100210a0  jnz     short loc_100210B8
0x100210a2  push    ebx; struct _GUID *
0x100210a3  call    ?SetInterfacesFromREFIID@CRowsetProperties@@QAEJABU_GUID@@@Z; CRowsetProperties::SetInterfacesFromREFIID(_GUID const &)
0x100210a8  mov     esi, eax
0x100210aa  mov     [ebp+var_8], esi
0x100210ad  test    esi, esi
0x100210af  js      loc_1002159D
0x100210b5  mov     esi, [ebp+var_14]
0x100210b8  mov     eax, [esi+0Ch]
0x100210bb  lea     ecx, [ebp+var_40]
0x100210be  push    ecx; unsigned int *
0x100210bf  push    0FFh; unsigned int
0x100210c4  mov     ecx, eax; this
0x100210c6  mov     [ebp+var_1C], eax
0x100210c9  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x100210ce  mov     edx, 3
0x100210d3  test    eax, eax
0x100210d5  js      short loc_100210F2
0x100210d7  mov     eax, [ebp+var_40]
0x100210da  lea     ecx, [eax+eax*2]
0x100210dd  mov     eax, [esi+0Ch]
0x100210e0  add     ecx, ecx
0x100210e2  mov     eax, [eax+10h]
0x100210e5  cmp     dx, [eax+ecx*8+10h]
0x100210ea  jnz     short loc_100210F2
0x100210ec  mov     eax, [eax+ecx*8+18h]
0x100210f0  jmp     short loc_100210F4
0x100210f2  xor     eax, eax
0x100210f4  mov     esi, [esi+8]
0x100210f7  mov     ecx, esi; this
0x100210f9  mov     [ebp+var_18], eax
0x100210fc  lea     eax, [ebp+var_40]
0x100210ff  push    eax; unsigned int *
0x10021100  push    75h ; 'u'; unsigned int
0x10021102  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x10021107  test    eax, eax
0x10021109  js      short loc_1002112B
0x1002110b  mov     eax, [ebp+var_40]
0x1002110e  mov     edx, 3
0x10021113  lea     ecx, [eax+eax*2]
0x10021116  mov     eax, [esi+10h]
0x10021119  add     ecx, ecx
0x1002111b  cmp     dx, [eax+ecx*8+10h]
0x10021120  jnz     short loc_1002112B
0x10021122  mov     eax, [eax+ecx*8+18h]
0x10021126  mov     [ebp+var_20], eax
0x10021129  jmp     short loc_10021132
0x1002112b  mov     [ebp+var_20], 0
0x10021132  lea     eax, [ebp+var_40]
0x10021135  mov     ecx, esi; this
0x10021137  push    eax; unsigned int *
0x10021138  push    47h ; 'G'; unsigned int
0x1002113a  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x1002113f  test    eax, eax
0x10021141  js      short loc_10021163
0x10021143  mov     eax, [ebp+var_40]
0x10021146  mov     edx, 3
0x1002114b  lea     ecx, [eax+eax*2]
0x1002114e  mov     eax, [esi+10h]
0x10021151  add     ecx, ecx
0x10021153  cmp     dx, [eax+ecx*8+10h]
0x10021158  jnz     short loc_10021163
0x1002115a  mov     eax, [eax+ecx*8+18h]
0x1002115e  mov     [ebp+var_24], eax
0x10021161  jmp     short loc_1002116A
0x10021163  mov     [ebp+var_24], 0
0x1002116a  lea     eax, [ebp+var_40]
0x1002116d  mov     ecx, esi; this
0x1002116f  push    eax; unsigned int *
0x10021170  push    58h ; 'X'; unsigned int
0x10021172  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x10021177  test    eax, eax
0x10021179  js      short loc_10021196
0x1002117b  mov     eax, [ebp+var_40]
0x1002117e  xor     edx, edx
0x10021180  lea     ecx, [eax+eax*2]
0x10021183  mov     eax, [esi+10h]
0x10021186  add     ecx, ecx
0x10021188  cmp     word ptr [eax+ecx*8+18h], 0FFFFh
0x1002118e  setz    dl
0x10021191  mov     [ebp+var_28], edx
0x10021194  jmp     short loc_1002119D
0x10021196  mov     [ebp+var_28], 0
0x1002119d  lea     eax, [ebp+var_40]
0x100211a0  mov     ecx, esi; this
0x100211a2  push    eax; unsigned int *
0x100211a3  push    5Ah ; 'Z'; unsigned int
0x100211a5  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x100211aa  test    eax, eax
0x100211ac  js      short loc_100211C9
0x100211ae  mov     eax, [ebp+var_40]
0x100211b1  xor     edx, edx
0x100211b3  lea     ecx, [eax+eax*2]
0x100211b6  mov     eax, [esi+10h]
0x100211b9  add     ecx, ecx
0x100211bb  cmp     word ptr [eax+ecx*8+18h], 0FFFFh
0x100211c1  setz    dl
0x100211c4  mov     [ebp+var_2C], edx
0x100211c7  jmp     short loc_100211D0
0x100211c9  mov     [ebp+var_2C], 0
0x100211d0  lea     eax, [ebp+var_40]
0x100211d3  mov     ecx, esi; this
0x100211d5  push    eax; unsigned int *
0x100211d6  push    59h ; 'Y'; unsigned int
0x100211d8  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x100211dd  test    eax, eax
0x100211df  js      short loc_100211FC
0x100211e1  mov     eax, [ebp+var_40]
0x100211e4  xor     edx, edx
0x100211e6  lea     ecx, [eax+eax*2]
0x100211e9  mov     eax, [esi+10h]
0x100211ec  add     ecx, ecx
0x100211ee  cmp     word ptr [eax+ecx*8+18h], 0FFFFh
0x100211f4  setz    dl
0x100211f7  mov     [ebp+var_30], edx
0x100211fa  jmp     short loc_10021203
0x100211fc  mov     [ebp+var_30], 0
0x10021203  lea     eax, [ebp+var_40]
0x10021206  mov     ecx, esi; this
0x10021208  push    eax; unsigned int *
0x10021209  push    7Fh; unsigned int
0x1002120b  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x10021210  test    eax, eax
0x10021212  js      short loc_1002122F
0x10021214  mov     eax, [ebp+var_40]
0x10021217  xor     edx, edx
0x10021219  lea     ecx, [eax+eax*2]
0x1002121c  mov     eax, [esi+10h]
0x1002121f  add     ecx, ecx
0x10021221  cmp     word ptr [eax+ecx*8+18h], 0FFFFh
0x10021227  setz    dl
0x1002122a  mov     [ebp+var_4], edx
0x1002122d  jmp     short loc_10021236
0x1002122f  mov     [ebp+var_4], 0
0x10021236  lea     eax, [ebp+var_40]
0x10021239  mov     ecx, esi; this
0x1002123b  push    eax; unsigned int *
0x1002123c  push    15h; unsigned int
0x1002123e  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x10021243  test    eax, eax
0x10021245  js      short loc_10021262
0x10021247  mov     eax, [ebp+var_40]
0x1002124a  xor     edx, edx
0x1002124c  lea     ecx, [eax+eax*2]
0x1002124f  mov     eax, [esi+10h]
0x10021252  add     ecx, ecx
0x10021254  cmp     word ptr [eax+ecx*8+18h], 0FFFFh
0x1002125a  setz    dl
0x1002125d  mov     [ebp+var_34], edx
0x10021260  jmp     short loc_10021269
0x10021262  mov     [ebp+var_34], 0
0x10021269  lea     eax, [ebp+var_40]
0x1002126c  mov     ecx, esi; this
0x1002126e  push    eax; unsigned int *
0x1002126f  push    12h; unsigned int
0x10021271  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x10021276  test    eax, eax
0x10021278  js      short loc_10021295
0x1002127a  mov     eax, [ebp+var_40]
0x1002127d  xor     edx, edx
0x1002127f  lea     ecx, [eax+eax*2]
0x10021282  mov     eax, [esi+10h]
0x10021285  add     ecx, ecx
0x10021287  cmp     word ptr [eax+ecx*8+18h], 0FFFFh
0x1002128d  setz    dl
0x10021290  mov     [ebp+var_38], edx
0x10021293  jmp     short loc_1002129C
0x10021295  mov     [ebp+var_38], 0
0x1002129c  lea     eax, [ebp+var_40]
0x1002129f  mov     ecx, esi; this
0x100212a1  push    eax; unsigned int *
0x100212a2  push    82h; unsigned int
0x100212a7  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x100212ac  test    eax, eax
0x100212ae  js      short loc_100212CB
0x100212b0  mov     eax, [ebp+var_40]
0x100212b3  xor     edx, edx
0x100212b5  lea     ecx, [eax+eax*2]
0x100212b8  mov     eax, [esi+10h]
0x100212bb  add     ecx, ecx
0x100212bd  cmp     word ptr [eax+ecx*8+18h], 0FFFFh
0x100212c3  setz    dl
0x100212c6  mov     [ebp+var_C], edx
0x100212c9  jmp     short loc_100212D2
0x100212cb  mov     [ebp+var_C], 0
0x100212d2  lea     eax, [ebp+var_40]
0x100212d5  mov     ecx, esi; this
0x100212d7  push    eax; unsigned int *
0x100212d8  push    85h; unsigned int
0x100212dd  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x100212e2  test    eax, eax
0x100212e4  js      short loc_10021301
0x100212e6  mov     eax, [ebp+var_40]
0x100212e9  xor     edx, edx
0x100212eb  lea     ecx, [eax+eax*2]
0x100212ee  mov     eax, [esi+10h]
0x100212f1  add     ecx, ecx
0x100212f3  cmp     word ptr [eax+ecx*8+18h], 0FFFFh
0x100212f9  setz    dl
0x100212fc  mov     [ebp+var_10], edx
0x100212ff  jmp     short loc_10021308
0x10021301  mov     [ebp+var_10], 0
0x10021308  lea     eax, [ebp+var_40]
0x1002130b  mov     ecx, esi; this
0x1002130d  push    eax; unsigned int *
0x1002130e  push    13h; unsigned int
0x10021310  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x10021315  test    eax, eax
0x10021317  js      short loc_10021334
0x10021319  mov     eax, [ebp+var_40]
0x1002131c  xor     edx, edx
0x1002131e  lea     ecx, [eax+eax*2]
0x10021321  mov     eax, [esi+10h]
0x10021324  add     ecx, ecx
0x10021326  cmp     word ptr [eax+ecx*8+18h], 0FFFFh
0x1002132c  setz    dl
0x1002132f  mov     [ebp+var_40], edx
0x10021332  jmp     short loc_1002133B
0x10021334  mov     [ebp+var_40], 0
0x1002133b  lea     eax, [ebp+var_3C]
0x1002133e  mov     ecx, esi; this
0x10021340  push    eax; unsigned int *
0x10021341  push    0Eh; unsigned int
0x10021343  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x10021348  test    eax, eax
0x1002134a  js      short loc_10021367
0x1002134c  mov     eax, [ebp+var_3C]
0x1002134f  xor     edx, edx
0x10021351  lea     ecx, [eax+eax*2]
0x10021354  mov     eax, [esi+10h]
0x10021357  add     ecx, ecx
0x10021359  cmp     word ptr [eax+ecx*8+18h], 0FFFFh
0x1002135f  setz    dl
0x10021362  mov     [ebp+var_3C], edx
0x10021365  jmp     short loc_1002136E
0x10021367  mov     [ebp+var_3C], 0
0x1002136e  cmp     [ebp+arg_C], 0
0x10021372  jnz     loc_10021420
0x10021378  mov     ecx, offset _IID_IRowsetLocate
0x1002137d  mov     edx, ebx
0x1002137f  mov     esi, 0Ch
0x10021384  mov     eax, [ecx]
0x10021386  cmp     eax, [edx]
0x10021388  jnz     short loc_100213A1
0x1002138a  add     ecx, 4
0x1002138d  add     edx, 4
0x10021390  sub     esi, 4
0x10021393  jnb     short loc_10021384
0x10021395  mov     [ebp+var_C], 1
0x1002139c  jmp     loc_10021420
0x100213a1  mov     ecx, offset _IID_IRowsetScroll
0x100213a6  mov     edx, ebx
0x100213a8  mov     esi, 0Ch
0x100213ad  nop     dword ptr [eax]
0x100213b0  mov     eax, [ecx]
0x100213b2  cmp     eax, [edx]
0x100213b4  jnz     short loc_100213CA
0x100213b6  add     ecx, 4
0x100213b9  add     edx, 4
0x100213bc  sub     esi, 4
0x100213bf  jnb     short loc_100213B0
0x100213c1  mov     [ebp+var_10], 1
0x100213c8  jmp     short loc_10021420
0x100213ca  mov     ecx, offset _IID_IRowsetChange
0x100213cf  mov     edx, ebx
0x100213d1  mov     esi, 0Ch
0x100213d6  mov     eax, [ecx]
0x100213d8  cmp     eax, [edx]
0x100213da  jnz     short loc_100213F0
0x100213dc  add     ecx, 4
0x100213df  add     edx, 4
0x100213e2  sub     esi, 4
0x100213e5  jnb     short loc_100213D6
0x100213e7  mov     [ebp+var_4], 1
0x100213ee  jmp     short loc_10021420
0x100213f0  mov     ecx, offset _IID_IRowsetUpdate
0x100213f5  mov     edx, 0Ch
0x100213fa  nop     word ptr [eax+eax+00h]
0x10021400  mov     eax, [ecx]
0x10021402  cmp     eax, [ebx]
0x10021404  jnz     short loc_1002141A
0x10021406  add     ecx, 4
0x10021409  add     ebx, 4
0x1002140c  sub     edx, 4
  ... truncated ...
```
