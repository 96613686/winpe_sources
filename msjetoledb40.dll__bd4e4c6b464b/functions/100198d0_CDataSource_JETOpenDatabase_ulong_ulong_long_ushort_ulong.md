# CDataSource::JETOpenDatabase(ulong &,ulong &,long &,ushort *,ulong *)

- ea: `0x100198d0`
- end: `0x10019cbd`
- name: `?JETOpenDatabase@CDataSource@@QAEJAAK0AAJPAGPAK@Z`
- size: `1005`
- prototype: `int __thiscall(CDataSource *this, unsigned int *, unsigned int *, unsigned int *, unsigned __int16 *, unsigned int *)`
- caller_count: `5`
- callee_count: `8`
- tags: `file_ops, authz_impersonation`

## callers

- `0x10019070`
- `0x1001af60`
- `0x10042ed0`
- `0x100438b0`
- `0x100438f0`

## callees

- `0x100198d0`
- `0x10019cd0`
- `0x1001a140`
- `0x1001bdc0`
- `0x1001f2d0`
- `0x1001fd10`
- `0x1004cea1`
- `0x1004d420`

## import_xrefs

- `msjet40!__imp__JetCloseDatabase@12` at `0x10019c9c`
- `msjet40!__imp__JetCloseDatabase@12` at `0x10019c9c`
- `msjet40!__imp__JetOpenDatabase@20` at `0x10019a18`
- `msjet40!__imp__JetOpenDatabase@20` at `0x10019a18`

## pseudocode

```c
int __thiscall CDataSource::JETOpenDatabase(
        CDataSource *this,
        unsigned int *a2,
        unsigned int *a3,
        unsigned int *a4,
        unsigned __int16 *a5,
        unsigned int *a6)
{
  int v6; // esi
  JET_DBID *v7; // edi
  _WORD *v8; // edi
  _WORD *v9; // edx
  int v10; // ecx
  int v11; // esi
  JoltProperties **v12; // edi
  _WORD *v13; // eax
  unsigned int v14; // ebx
  unsigned __int16 *v15; // eax
  unsigned int *v16; // esi
  int v17; // eax
  bool v18; // zf
  unsigned int v19; // eax
  JoltProperties *v20; // edi
  unsigned int v21; // eax
  JoltProperties *v22; // edi
  int v23; // eax
  JoltProperties *v24; // edi
  unsigned int v25; // eax
  unsigned int v26; // eax
  JoltProperties *v27; // edi
  unsigned int v28; // ecx
  int v29; // edx
  int v31; // [esp+0h] [ebp-44Ch]
  const struct _GUID *v32; // [esp+4h] [ebp-448h]
  unsigned int v33; // [esp+14h] [ebp-438h] BYREF
  unsigned int v34; // [esp+18h] [ebp-434h] BYREF
  JET_SESID *v35; // [esp+1Ch] [ebp-430h]
  void *Block; // [esp+20h] [ebp-42Ch] BYREF
  unsigned __int16 *v37; // [esp+24h] [ebp-428h] BYREF
  unsigned int v38; // [esp+28h] [ebp-424h] BYREF
  unsigned int *v39; // [esp+2Ch] [ebp-420h]
  int v40; // [esp+30h] [ebp-41Ch]
  unsigned __int16 *v41; // [esp+34h] [ebp-418h]
  CDataSource *v42; // [esp+38h] [ebp-414h]
  _BYTE v43[1036]; // [esp+3Ch] [ebp-410h] BYREF

  v35 = a2;
  v6 = 0;
  v7 = a3;
  v41 = a5;
  v34 = (unsigned int)a6;
  v18 = *a3 == -1;
  v42 = this;
  v39 = a3;
  v37 = 0;
  Block = 0;
  v38 = 0;
  v40 = 0;
  if ( !v18 )
    goto LABEL_63;
  v6 = CDataSource::BuildConnectString(this, (unsigned __int16 **)&Block, (CDataSource *)((char *)this + 152));
  if ( v6 < 0 )
    goto LABEL_63;
  v8 = Block;
  v9 = v43;
  v10 = 512;
  v11 = 513;
  do
  {
    if ( !v10 )
      break;
    if ( !*v8 )
      break;
    *v9++ = *v8++;
    --v10;
    --v11;
  }
  while ( v11 );
  v12 = (JoltProperties **)v42;
  v13 = v9 - 1;
  if ( v11 )
    v13 = v9;
  *v13 = 0;
  if ( v34 )
  {
    v14 = *(_DWORD *)v34;
  }
  else
  {
    v6 = CDataSource::ValidateStateForJetOpenDatabase((CDataSource *)v12, &v38);
    if ( v6 < 0 )
      goto LABEL_62;
    v14 = v38;
  }
  v15 = v41;
  if ( !v41 )
  {
    JoltProperties::GetStrValue(v12[40], 0x3Bu, &v37);
    v15 = v37;
    v41 = v37;
  }
  while ( 1 )
  {
    v16 = v39;
    v17 = JetOpenDatabase(*v35, v15, v43, v39, v14);
    *a4 = v17;
    if ( v17 > 1208 )
    {
      v18 = v17 == 5011;
      goto LABEL_21;
    }
    if ( v17 == 1208 )
      break;
    if ( v17 == -1905 )
    {
      v6 = -2147217843;
      goto LABEL_24;
    }
    v18 = v17 == 0;
LABEL_21:
    if ( v18 || v17 > 0 )
      goto LABEL_50;
    *v16 = -1;
    v6 = -2147467259;
LABEL_24:
    v19 = *a4;
    if ( *a4 == -1032 )
    {
      if ( (v14 & 1) != 0 )
        goto LABEL_51;
      v20 = v12[40];
      v21 = JoltProperties::BinarySearch(v20, 0x3Fu, &v34) < 0 ? 0 : *((_DWORD *)v20 + 4) + 48 * v34;
      if ( (*(_BYTE *)(v21 + 40) & 2) != 0 )
        goto LABEL_51;
      v12 = (JoltProperties **)v42;
      v14 |= 1u;
      v15 = v41;
      v40 = 1;
    }
    else if ( v19 == -1031 )
    {
      if ( (v14 & 2) != 0 )
        goto LABEL_51;
      v22 = v12[40];
      v23 = JoltProperties::BinarySearch(v22, 0x3Fu, (unsigned int *)&v37) < 0
          ? 0
          : *((_DWORD *)v22 + 4) + 48 * (_DWORD)v37;
      if ( (*(_BYTE *)(v23 + 40) & 2) != 0 )
        goto LABEL_51;
      v12 = (JoltProperties **)v42;
      v14 |= 2u;
      v15 = v41;
      v40 = 1;
    }
    else
    {
      if ( v19 != -1024 || (v14 & 3) == 3 )
        goto LABEL_51;
      v24 = v12[40];
      v25 = JoltProperties::BinarySearch(v24, 0x3Fu, &v38) < 0 ? 0 : *((_DWORD *)v24 + 4) + 48 * v38;
      if ( (*(_BYTE *)(v25 + 40) & 2) != 0 )
        goto LABEL_51;
      v26 = JoltProperties::BinarySearch(v24, 0x3Fu, &v33) < 0 ? 0 : *((_DWORD *)v24 + 4) + 48 * v33;
      if ( (*(_BYTE *)(v26 + 40) & 2) != 0 )
        goto LABEL_51;
      v12 = (JoltProperties **)v42;
      v14 |= 3u;
      v15 = v41;
      v40 = 1;
    }
  }
  *a4 = 0;
LABEL_50:
  v6 = 0;
LABEL_51:
  if ( v40 == 1 )
  {
    v27 = (JoltProperties *)*((_DWORD *)v42 + 40);
    if ( JoltProperties::BinarySearch(v27, 0x3Fu, &v33) < 0 )
      v28 = 0;
    else
      v28 = *((_DWORD *)v27 + 4) + 48 * v33;
    v29 = *(_DWORD *)(v28 + 32) | 0x400;
    if ( (v14 & 3) == 3 )
    {
      *(_DWORD *)(v28 + 24) = 13;
    }
    else if ( (v14 & 1) != 0 )
    {
      *(_DWORD *)(v28 + 24) = 1;
    }
    else if ( (v14 & 2) != 0 )
    {
      *(_DWORD *)(v28 + 24) = 12;
    }
    *(_DWORD *)(v28 + 32) = v29 & 0xFFFFFBFF;
  }
LABEL_62:
  v7 = v39;
LABEL_63:
  if ( *a4 )
    CExtError::SendJetErrortoOLEAuto(*a4, (int)&IID_IDBInitialize, v31, v32);
  if ( Block )
    operator delete(Block);
  if ( v6 < 0 && *v7 != -1 && (*a4 & 0x80000000) == 0 )
  {
    JetCloseDatabase(*v35, *v7, 0);
    *v7 = -1;
  }
  return v6;
}

```

## disassembly

```asm
0x100198d0  mov     edi, edi
0x100198d2  push    ebp
0x100198d3  mov     ebp, esp
0x100198d5  sub     esp, 440h
0x100198db  mov     eax, ___security_cookie
0x100198e0  xor     eax, ebp
0x100198e2  mov     [ebp+var_4], eax
0x100198e5  mov     eax, [ebp+arg_0]
0x100198e8  push    ebx
0x100198e9  mov     [ebp+var_430], eax
0x100198ef  mov     eax, [ebp+arg_8]
0x100198f2  push    esi; struct _GUID *
0x100198f3  mov     [ebp+var_43C], eax
0x100198f9  xor     esi, esi
0x100198fb  mov     eax, [ebp+arg_C]
0x100198fe  push    edi; int
0x100198ff  mov     edi, [ebp+arg_4]
0x10019902  mov     [ebp+var_418], eax
0x10019908  mov     eax, [ebp+arg_10]
0x1001990b  mov     [ebp+var_434], eax
0x10019911  xor     eax, eax
0x10019913  cmp     dword ptr [edi], 0FFFFFFFFh
0x10019916  mov     [ebp+var_414], ecx
0x1001991c  mov     [ebp+var_420], edi
0x10019922  mov     [ebp+var_428], esi
0x10019928  mov     [ebp+Block], esi
0x1001992e  mov     [ebp+var_424], esi
0x10019934  mov     [ebp+var_41C], eax
0x1001993a  jnz     loc_10019C4D
0x10019940  lea     eax, [ecx+98h]
0x10019946  push    eax; struct CDBInitProperties *
0x10019947  lea     eax, [ebp+Block]
0x1001994d  push    eax; unsigned __int16 **
0x1001994e  call    ?BuildConnectString@CDataSource@@QAEJAAPAGAAVCDBInitProperties@@@Z; CDataSource::BuildConnectString(ushort * &,CDBInitProperties &)
0x10019953  mov     esi, eax
0x10019955  test    esi, esi
0x10019957  js      loc_10019C4D
0x1001995d  mov     edi, [ebp+Block]
0x10019963  lea     edx, [ebp+var_410]
0x10019969  mov     ecx, 200h
0x1001996e  lea     esi, [ecx+1]
0x10019971  test    ecx, ecx
0x10019973  jz      short loc_1001998E
0x10019975  movzx   eax, word ptr [edi]
0x10019978  mov     ebx, eax
0x1001997a  test    ax, ax
0x1001997d  jz      short loc_1001998E
0x1001997f  mov     [edx], bx
0x10019982  add     edi, 2
0x10019985  add     edx, 2
0x10019988  dec     ecx
0x10019989  sub     esi, 1
0x1001998c  jnz     short loc_10019971
0x1001998e  mov     edi, [ebp+var_414]
0x10019994  lea     eax, [edx-2]
0x10019997  test    esi, esi
0x10019999  cmovnz  eax, edx
0x1001999c  xor     ecx, ecx
0x1001999e  mov     [eax], cx
0x100199a1  mov     eax, [ebp+var_434]
0x100199a7  test    eax, eax
0x100199a9  jnz     short loc_100199CB
0x100199ab  lea     eax, [ebp+var_424]
0x100199b1  mov     ecx, edi; this
0x100199b3  push    eax; unsigned int *
0x100199b4  call    ?ValidateStateForJetOpenDatabase@CDataSource@@QAEJAAK@Z; CDataSource::ValidateStateForJetOpenDatabase(ulong &)
0x100199b9  mov     esi, eax
0x100199bb  test    esi, esi
0x100199bd  js      loc_10019C47
0x100199c3  mov     ebx, [ebp+var_424]
0x100199c9  jmp     short loc_100199CD
0x100199cb  mov     ebx, [eax]
0x100199cd  mov     eax, [ebp+var_418]
0x100199d3  test    eax, eax
0x100199d5  jnz     short loc_10019A00
0x100199d7  mov     ecx, [edi+0A0h]; this
0x100199dd  lea     eax, [ebp+var_428]
0x100199e3  push    eax; unsigned __int16 **
0x100199e4  push    3Bh ; ';'; unsigned int
0x100199e6  call    ?GetStrValue@JoltProperties@@QBEJKAAPAG@Z; JoltProperties::GetStrValue(ulong,ushort * &)
0x100199eb  mov     eax, [ebp+var_428]
0x100199f1  mov     [ebp+var_418], eax
0x100199f7  nop     word ptr [eax+eax+00000000h]
0x10019a00  mov     esi, [ebp+var_420]
0x10019a06  lea     ecx, [ebp+var_410]
0x10019a0c  push    ebx
0x10019a0d  push    esi
0x10019a0e  push    ecx
0x10019a0f  push    eax
0x10019a10  mov     eax, [ebp+var_430]
0x10019a16  push    dword ptr [eax]
0x10019a18  call    ds:__imp__JetOpenDatabase@20; JetOpenDatabase(x,x,x,x,x)
0x10019a1e  mov     ecx, [ebp+var_43C]
0x10019a24  mov     [ecx], eax
0x10019a26  cmp     eax, 4B8h
0x10019a2b  jg      short loc_10019A45
0x10019a2d  jz      loc_10019BC5
0x10019a33  cmp     eax, 0FFFFF88Fh
0x10019a38  jz      short loc_10019A3E
0x10019a3a  test    eax, eax
0x10019a3c  jmp     short loc_10019A4A
0x10019a3e  mov     esi, 80040E4Dh
0x10019a43  jmp     short loc_10019A63
0x10019a45  cmp     eax, 1393h
0x10019a4a  jz      loc_10019BCB
0x10019a50  test    eax, eax
0x10019a52  jg      loc_10019BCB
0x10019a58  mov     dword ptr [esi], 0FFFFFFFFh
0x10019a5e  mov     esi, 80004005h
0x10019a63  mov     eax, [ecx]
0x10019a65  cmp     eax, 0FFFFFBF8h
0x10019a6a  jnz     short loc_10019ACA
0x10019a6c  test    bl, 1
0x10019a6f  jnz     loc_10019BCD
0x10019a75  mov     edi, [edi+0A0h]
0x10019a7b  lea     eax, [ebp+var_434]
0x10019a81  push    eax; unsigned int *
0x10019a82  push    3Fh ; '?'; unsigned int
0x10019a84  mov     ecx, edi; this
0x10019a86  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x10019a8b  test    eax, eax
0x10019a8d  js      short loc_10019AA0
0x10019a8f  mov     eax, [ebp+var_434]
0x10019a95  lea     eax, [eax+eax*2]
0x10019a98  shl     eax, 4
0x10019a9b  add     eax, [edi+10h]
0x10019a9e  jmp     short loc_10019AA2
0x10019aa0  xor     eax, eax
0x10019aa2  test    byte ptr [eax+28h], 2
0x10019aa6  jnz     loc_10019BCD
0x10019aac  mov     edi, [ebp+var_414]
0x10019ab2  or      ebx, 1
0x10019ab5  mov     eax, [ebp+var_418]
0x10019abb  mov     [ebp+var_41C], 1
0x10019ac5  jmp     loc_10019A00
0x10019aca  cmp     eax, 0FFFFFBF9h
0x10019acf  jnz     short loc_10019B2F
0x10019ad1  test    bl, 2
0x10019ad4  jnz     loc_10019BCD
0x10019ada  mov     edi, [edi+0A0h]
0x10019ae0  lea     eax, [ebp+var_428]
0x10019ae6  push    eax; unsigned int *
0x10019ae7  push    3Fh ; '?'; unsigned int
0x10019ae9  mov     ecx, edi; this
0x10019aeb  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x10019af0  test    eax, eax
0x10019af2  js      short loc_10019B05
0x10019af4  mov     eax, [ebp+var_428]
0x10019afa  lea     eax, [eax+eax*2]
0x10019afd  shl     eax, 4
0x10019b00  add     eax, [edi+10h]
0x10019b03  jmp     short loc_10019B07
0x10019b05  xor     eax, eax
0x10019b07  test    byte ptr [eax+28h], 2
0x10019b0b  jnz     loc_10019BCD
0x10019b11  mov     edi, [ebp+var_414]
0x10019b17  or      ebx, 2
0x10019b1a  mov     eax, [ebp+var_418]
0x10019b20  mov     [ebp+var_41C], 1
0x10019b2a  jmp     loc_10019A00
0x10019b2f  cmp     eax, 0FFFFFC00h
0x10019b34  jnz     loc_10019BCD
0x10019b3a  mov     eax, ebx
0x10019b3c  and     eax, 3
0x10019b3f  cmp     al, 3
0x10019b41  jz      loc_10019BCD
0x10019b47  mov     edi, [edi+0A0h]
0x10019b4d  lea     eax, [ebp+var_424]
0x10019b53  push    eax; unsigned int *
0x10019b54  push    3Fh ; '?'; unsigned int
0x10019b56  mov     ecx, edi; this
0x10019b58  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x10019b5d  test    eax, eax
0x10019b5f  js      short loc_10019B72
0x10019b61  mov     eax, [ebp+var_424]
0x10019b67  lea     eax, [eax+eax*2]
0x10019b6a  shl     eax, 4
0x10019b6d  add     eax, [edi+10h]
0x10019b70  jmp     short loc_10019B74
0x10019b72  xor     eax, eax
0x10019b74  test    byte ptr [eax+28h], 2
0x10019b78  jnz     short loc_10019BCD
0x10019b7a  lea     eax, [ebp+var_438]
0x10019b80  mov     ecx, edi; this
0x10019b82  push    eax; unsigned int *
0x10019b83  push    3Fh ; '?'; unsigned int
0x10019b85  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x10019b8a  test    eax, eax
0x10019b8c  js      short loc_10019B9F
0x10019b8e  mov     eax, [ebp+var_438]
0x10019b94  lea     eax, [eax+eax*2]
0x10019b97  shl     eax, 4
0x10019b9a  add     eax, [edi+10h]
0x10019b9d  jmp     short loc_10019BA1
0x10019b9f  xor     eax, eax
0x10019ba1  test    byte ptr [eax+28h], 2
0x10019ba5  jnz     short loc_10019BCD
0x10019ba7  mov     edi, [ebp+var_414]
0x10019bad  or      ebx, 3
0x10019bb0  mov     eax, [ebp+var_418]
0x10019bb6  mov     [ebp+var_41C], 1
0x10019bc0  jmp     loc_10019A00
0x10019bc5  mov     dword ptr [ecx], 0
0x10019bcb  xor     esi, esi
0x10019bcd  cmp     [ebp+var_41C], 1
0x10019bd4  jnz     short loc_10019C47
0x10019bd6  mov     ecx, [ebp+var_414]
0x10019bdc  lea     eax, [ebp+var_438]
0x10019be2  push    eax; unsigned int *
0x10019be3  push    3Fh ; '?'; unsigned int
0x10019be5  mov     edi, [ecx+0A0h]
0x10019beb  mov     ecx, edi; this
0x10019bed  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x10019bf2  test    eax, eax
0x10019bf4  js      short loc_10019C07
0x10019bf6  mov     eax, [ebp+var_438]
0x10019bfc  lea     ecx, [eax+eax*2]
0x10019bff  shl     ecx, 4
0x10019c02  add     ecx, [edi+10h]
0x10019c05  jmp     short loc_10019C09
0x10019c07  xor     ecx, ecx
0x10019c09  mov     edx, [ecx+20h]
0x10019c0c  mov     eax, ebx
0x10019c0e  and     eax, 3
0x10019c11  or      edx, 400h
0x10019c17  cmp     al, 3
0x10019c19  jnz     short loc_10019C24
0x10019c1b  mov     dword ptr [ecx+18h], 0Dh
0x10019c22  jmp     short loc_10019C3E
0x10019c24  test    bl, 1
0x10019c27  jz      short loc_10019C32
0x10019c29  mov     dword ptr [ecx+18h], 1
0x10019c30  jmp     short loc_10019C3E
0x10019c32  test    bl, 2
0x10019c35  jz      short loc_10019C3E
0x10019c37  mov     dword ptr [ecx+18h], 0Ch
0x10019c3e  and     edx, 0FFFFFBFFh
0x10019c44  mov     [ecx+20h], edx
0x10019c47  mov     edi, [ebp+var_420]
0x10019c4d  mov     ebx, [ebp+var_43C]
0x10019c53  mov     eax, [ebx]
0x10019c55  test    eax, eax
0x10019c57  jz      short loc_10019C6E
0x10019c59  push    offset _IID_IDBInitialize; int
0x10019c5e  push    eax; unsigned int
0x10019c5f  mov     eax, [ebp+var_430]
0x10019c65  mov     edx, esi
0x10019c67  mov     ecx, [eax]
0x10019c69  call    ?SendJetErrortoOLEAuto@CExtError@@SGJKJJABU_GUID@@@Z; CExtError::SendJetErrortoOLEAuto(ulong,long,long,_GUID const &)
0x10019c6e  mov     eax, [ebp+Block]
0x10019c74  test    eax, eax
0x10019c76  jz      short loc_10019C81
0x10019c78  push    eax; Block
0x10019c79  call    ??3@YAXPAX@Z; operator delete(void *)
0x10019c7e  add     esp, 4
0x10019c81  test    esi, esi
0x10019c83  jns     short loc_10019CA8
0x10019c85  mov     eax, [edi]
0x10019c87  cmp     eax, 0FFFFFFFFh
0x10019c8a  jz      short loc_10019CA8
0x10019c8c  cmp     dword ptr [ebx], 0
0x10019c8f  jl      short loc_10019CA8
0x10019c91  push    0; grbit
0x10019c93  push    eax; dbid
0x10019c94  mov     eax, [ebp+var_430]
0x10019c9a  push    dword ptr [eax]; sesid
0x10019c9c  call    ds:__imp__JetCloseDatabase@12; JetCloseDatabase(x,x,x)
0x10019ca2  mov     dword ptr [edi], 0FFFFFFFFh
0x10019ca8  mov     ecx, [ebp+var_4]
0x10019cab  mov     eax, esi
0x10019cad  pop     edi
0x10019cae  pop     esi
0x10019caf  xor     ecx, ebp; StackCookie
0x10019cb1  pop     ebx
0x10019cb2  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10019cb7  mov     esp, ebp
0x10019cb9  pop     ebp
0x10019cba  retn    14h
```
