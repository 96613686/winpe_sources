# CDataSource::JETBeginSession(ulong &,long &)

- ea: `0x100196e0`
- end: `0x100198b3`
- name: `?JETBeginSession@CDataSource@@QAEJAAKAAJ@Z`
- size: `467`
- prototype: `int __thiscall(CDataSource *__hidden this, unsigned int *, int *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x10019070`
- `0x1001a970`
- `0x100407e0`
- `0x10040c30`
- `0x10043840`

## callees

- `0x100196e0`
- `0x1001f2d0`

## import_xrefs

- `msjet40!__imp__JetBeginSession@16` at `0x100197ee`
- `msjet40!__imp__JetBeginSession@16` at `0x100197ee`
- `msjet40!__imp__JetEndSession@8` at `0x10019891`
- `msjet40!__imp__JetEndSession@8` at `0x10019891`
- `msjet40!__imp__JetSetSystemParameter@20` at `0x10019845`
- `msjet40!__imp__JetSetSystemParameter@20` at `0x1001985a`
- `msjet40!__imp__JetSetSystemParameter@20` at `0x10019876`
- `msjet40!__imp__JetSetSystemParameter@20` at `0x10019845`
- `msjet40!__imp__JetSetSystemParameter@20` at `0x1001985a`
- `msjet40!__imp__JetSetSystemParameter@20` at `0x10019876`

## pseudocode

```c
int __thiscall CDataSource::JETBeginSession(JoltProperties **this, unsigned int *a2, int *a3)
{
  CDataSource *v3; // ebx
  JoltProperties *v4; // esi
  int v5; // eax
  int v6; // eax
  int v7; // eax
  int v8; // eax
  _DWORD *v9; // esi
  const OLECHAR *v10; // eax
  int v11; // eax
  int v12; // esi
  int v13; // eax
  int v14; // eax
  int v15; // eax
  unsigned int v17; // [esp+Ch] [ebp-14h] BYREF
  unsigned int v18; // [esp+10h] [ebp-10h] BYREF
  int v19; // [esp+14h] [ebp-Ch]
  int v20; // [esp+18h] [ebp-8h]
  const OLECHAR *v21; // [esp+1Ch] [ebp-4h]

  v3 = (CDataSource *)this;
  v20 = 0;
  v17 = (unsigned int)this;
  v4 = this[40];
  v21 = 0;
  if ( JoltProperties::BinarySearch(v4, 0xCu, &v18) >= 0 )
  {
    v5 = *((_DWORD *)v4 + 4);
    if ( *(_WORD *)(v5 + 48 * v18 + 16) == 8 )
      v20 = *(_DWORD *)(v5 + 48 * v18 + 24);
  }
  if ( JoltProperties::BinarySearch(v4, 9u, &v18) >= 0 )
  {
    v6 = *((_DWORD *)v4 + 4);
    if ( *(_WORD *)(v6 + 48 * v18 + 16) == 8 )
      v21 = *(const OLECHAR **)(v6 + 48 * v18 + 24);
  }
  if ( JoltProperties::BinarySearch(v4, 0x40u, &v18) >= 0
    && (v7 = *((_DWORD *)v4 + 4), *(_WORD *)(v7 + 48 * v18 + 16) == 3) )
  {
    v19 = *(_DWORD *)(v7 + 48 * v18 + 24);
    v3 = (CDataSource *)v17;
  }
  else
  {
    v19 = 0;
  }
  if ( JoltProperties::BinarySearch(v4, 0x3Cu, &v17) >= 0
    && (v8 = *((_DWORD *)v4 + 4), *(_WORD *)(v8 + 48 * v17 + 16) == 3) )
  {
    v18 = *(_DWORD *)(v8 + 48 * v17 + 24);
  }
  else
  {
    v18 = 0;
  }
  if ( *a2 != -1 )
    return 0;
  v9 = (_DWORD *)((char *)v3 + 96);
  v10 = &word_100046A0;
  if ( v21 )
    v10 = v21;
  v11 = JetBeginSession(*v9, a2, v20, v10);
  *a3 = v11;
  if ( v11 <= -1101 )
  {
    if ( v11 == -1101 )
    {
      v12 = -2147217815;
      *a2 = -1;
    }
    else
    {
      switch ( v11 )
      {
        case -1907:
        case -1905:
        case -1903:
        case -1902:
        case -1901:
          v12 = -2147217843;
          break;
        default:
          goto LABEL_24;
      }
    }
    goto LABEL_30;
  }
  if ( v11 >= 0 )
  {
    v13 = JetSetSystemParameter(v9, *a2, 38, 1, 0);
    *a3 = v13;
    if ( v13 < 0 )
      goto LABEL_29;
    v14 = JetSetSystemParameter(v9, *a2, 69, 92, 0);
    *a3 = v14;
    if ( v14 < 0 )
      goto LABEL_29;
    if ( v19 != 4 )
    {
      v15 = JetSetSystemParameter(v9, *a2, 4, v18, 0);
      *a3 = v15;
      if ( v15 < 0 )
        goto LABEL_29;
    }
    return 0;
  }
LABEL_24:
  *a2 = -1;
LABEL_29:
  v12 = -2147467259;
LABEL_30:
  if ( *a2 != -1 )
  {
    JetEndSession(*a2, 0);
    *a2 = -1;
  }
  return v12;
}

```

## disassembly

```asm
0x100196e0  mov     edi, edi
0x100196e2  push    ebp
0x100196e3  mov     ebp, esp
0x100196e5  sub     esp, 14h
0x100196e8  push    ebx
0x100196e9  push    esi
0x100196ea  mov     ebx, ecx
0x100196ec  mov     [ebp+var_8], 0
0x100196f3  push    edi
0x100196f4  lea     eax, [ebp+var_10]
0x100196f7  mov     [ebp+var_14], ebx
0x100196fa  push    eax; unsigned int *
0x100196fb  mov     esi, [ebx+0A0h]
0x10019701  mov     ecx, esi; this
0x10019703  push    0Ch; unsigned int
0x10019705  mov     [ebp+var_4], 0
0x1001970c  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x10019711  mov     edi, 8
0x10019716  test    eax, eax
0x10019718  js      short loc_10019733
0x1001971a  mov     eax, [ebp+var_10]
0x1001971d  lea     ecx, [eax+eax*2]
0x10019720  mov     eax, [esi+10h]
0x10019723  add     ecx, ecx
0x10019725  cmp     di, [eax+ecx*8+10h]
0x1001972a  jnz     short loc_10019733
0x1001972c  mov     eax, [eax+ecx*8+18h]
0x10019730  mov     [ebp+var_8], eax
0x10019733  lea     eax, [ebp+var_10]
0x10019736  mov     ecx, esi; this
0x10019738  push    eax; unsigned int *
0x10019739  push    9; unsigned int
0x1001973b  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x10019740  test    eax, eax
0x10019742  js      short loc_1001975D
0x10019744  mov     eax, [ebp+var_10]
0x10019747  lea     ecx, [eax+eax*2]
0x1001974a  mov     eax, [esi+10h]
0x1001974d  add     ecx, ecx
0x1001974f  cmp     di, [eax+ecx*8+10h]
0x10019754  jnz     short loc_1001975D
0x10019756  mov     eax, [eax+ecx*8+18h]
0x1001975a  mov     [ebp+var_4], eax
0x1001975d  lea     eax, [ebp+var_10]
0x10019760  mov     ecx, esi; this
0x10019762  push    eax; unsigned int *
0x10019763  push    40h ; '@'; unsigned int
0x10019765  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x1001976a  mov     edi, 3
0x1001976f  test    eax, eax
0x10019771  js      short loc_10019791
0x10019773  mov     eax, [ebp+var_10]
0x10019776  lea     ecx, [eax+eax*2]
0x10019779  mov     eax, [esi+10h]
0x1001977c  add     ecx, ecx
0x1001977e  cmp     di, [eax+ecx*8+10h]
0x10019783  jnz     short loc_10019791
0x10019785  mov     ebx, [eax+ecx*8+18h]
0x10019789  mov     [ebp+var_C], ebx
0x1001978c  mov     ebx, [ebp+var_14]
0x1001978f  jmp     short loc_10019798
0x10019791  mov     [ebp+var_C], 0
0x10019798  lea     eax, [ebp+var_14]
0x1001979b  mov     ecx, esi; this
0x1001979d  push    eax; unsigned int *
0x1001979e  push    3Ch ; '<'; unsigned int
0x100197a0  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x100197a5  test    eax, eax
0x100197a7  js      short loc_100197C4
0x100197a9  mov     eax, [ebp+var_14]
0x100197ac  lea     ecx, [eax+eax*2]
0x100197af  mov     eax, [esi+10h]
0x100197b2  add     ecx, ecx
0x100197b4  cmp     di, [eax+ecx*8+10h]
0x100197b9  jnz     short loc_100197C4
0x100197bb  mov     eax, [eax+ecx*8+18h]
0x100197bf  mov     [ebp+var_10], eax
0x100197c2  jmp     short loc_100197CB
0x100197c4  mov     [ebp+var_10], 0
0x100197cb  mov     edi, [ebp+arg_0]
0x100197ce  cmp     dword ptr [edi], 0FFFFFFFFh
0x100197d1  jnz     loc_100198A8
0x100197d7  mov     ecx, [ebp+var_4]
0x100197da  lea     esi, [ebx+60h]
0x100197dd  test    ecx, ecx
0x100197df  mov     eax, offset word_100046A0
0x100197e4  cmovnz  eax, ecx
0x100197e7  push    eax
0x100197e8  push    [ebp+var_8]
0x100197eb  push    edi
0x100197ec  push    dword ptr [esi]
0x100197ee  call    ds:__imp__JetBeginSession@16; JetBeginSession(x,x,x,x)
0x100197f4  mov     ebx, [ebp+arg_4]
0x100197f7  mov     [ebx], eax
0x100197f9  cmp     eax, 0FFFFFBB3h
0x100197fe  jg      short loc_1001982E
0x10019800  jz      short loc_10019821
0x10019802  add     eax, 773h; switch 7 cases
0x10019807  cmp     eax, 6
0x1001980a  ja      short def_10019813; jumptable 10019813 default case, cases -1906,-1904
0x1001980c  movzx   eax, ds:byte_100198BC[eax]
0x10019813  jmp     ds:jpt_10019813[eax*4]; switch jump
0x1001981a  mov     esi, 80040E4Dh; jumptable 10019813 cases -1907,-1905,-1903--1901
0x1001981f  jmp     short loc_10019887
0x10019821  mov     esi, 80040E69h
0x10019826  mov     dword ptr [edi], 0FFFFFFFFh
0x1001982c  jmp     short loc_10019887
0x1001982e  test    eax, eax
0x10019830  jz      short loc_1001983C
0x10019832  jns     short loc_1001983C
0x10019834  mov     dword ptr [edi], 0FFFFFFFFh; jumptable 10019813 default case, cases -1906,-1904
0x1001983a  jmp     short loc_10019882
0x1001983c  push    0
0x1001983e  push    1
0x10019840  push    26h ; '&'
0x10019842  push    dword ptr [edi]
0x10019844  push    esi
0x10019845  call    ds:__imp__JetSetSystemParameter@20; JetSetSystemParameter(x,x,x,x,x)
0x1001984b  mov     [ebx], eax
0x1001984d  test    eax, eax
0x1001984f  js      short loc_10019882
0x10019851  push    0
0x10019853  push    5Ch ; '\'
0x10019855  push    45h ; 'E'
0x10019857  push    dword ptr [edi]
0x10019859  push    esi
0x1001985a  call    ds:__imp__JetSetSystemParameter@20; JetSetSystemParameter(x,x,x,x,x)
0x10019860  mov     [ebx], eax
0x10019862  test    eax, eax
0x10019864  js      short loc_10019882
0x10019866  cmp     [ebp+var_C], 4
0x1001986a  jz      short loc_100198A8
0x1001986c  push    0
0x1001986e  push    [ebp+var_10]
0x10019871  push    4
0x10019873  push    dword ptr [edi]
0x10019875  push    esi
0x10019876  call    ds:__imp__JetSetSystemParameter@20; JetSetSystemParameter(x,x,x,x,x)
0x1001987c  mov     [ebx], eax
0x1001987e  test    eax, eax
0x10019880  jns     short loc_100198A8
0x10019882  mov     esi, 80004005h
0x10019887  mov     eax, [edi]
0x10019889  cmp     eax, 0FFFFFFFFh
0x1001988c  jz      short loc_1001989D
0x1001988e  push    0; grbit
0x10019890  push    eax; sesid
0x10019891  call    ds:__imp__JetEndSession@8; JetEndSession(x,x)
0x10019897  mov     dword ptr [edi], 0FFFFFFFFh
0x1001989d  pop     edi
0x1001989e  mov     eax, esi
0x100198a0  pop     esi
0x100198a1  pop     ebx
0x100198a2  mov     esp, ebp
0x100198a4  pop     ebp
0x100198a5  retn    8
0x100198a8  pop     edi
0x100198a9  pop     esi
0x100198aa  xor     eax, eax
0x100198ac  pop     ebx
0x100198ad  mov     esp, ebp
0x100198af  pop     ebp
0x100198b0  retn    8
```
