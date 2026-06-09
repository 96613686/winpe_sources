# CImpIRowsetIndex::ValidateAccessorForCurrentIndex(ulong,ulong,void *,long &)

- ea: `0x1002fa60`
- end: `0x1002fef2`
- name: `?ValidateAccessorForCurrentIndex@CImpIRowsetIndex@@QAEJKKPAXAAJ@Z`
- size: `1170`
- prototype: `int __thiscall(CImpIRowsetIndex *__hidden this, unsigned int, JET_GRBIT grbit, void *, int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1002f660`
- `0x1002f820`

## callees

- `0x1001c6d0`
- `0x1002fa60`
- `0x1004d420`
- `0x1004d5a1`
- `0x1004dc81`

## import_xrefs

- `msjet40!__imp__JetCloseTable@8` at `0x1002fed2`
- `msjet40!__imp__JetCloseTable@8` at `0x1002fed2`
- `msjet40!__imp__JetGetCurrentIndex@16` at `0x1002fbac`
- `msjet40!__imp__JetGetCurrentIndex@16` at `0x1002fbac`
- `msjet40!__imp__JetGetTableIndexInfo@24` at `0x1002fbe2`
- `msjet40!__imp__JetGetTableIndexInfo@24` at `0x1002fbe2`
- `msjet40!__imp__JetMove@16` at `0x1002fdaf`
- `msjet40!__imp__JetMove@16` at `0x1002fdaf`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1002fc8c`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1002fd6e`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1002fe0e`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1002fc8c`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1002fd6e`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1002fe0e`

## pseudocode

```c
int __thiscall CImpIRowsetIndex::ValidateAccessorForCurrentIndex(
        CImpIRowsetIndex *this,
        unsigned int a2,
        JET_GRBIT grbit,
        char *a4,
        int *a5)
{
  CImpIRowsetIndex *v5; // esi
  int v6; // ebx
  _DWORD *v7; // ecx
  int v8; // edi
  JET_SESID v9; // eax
  int v10; // edx
  size_t *v11; // esi
  size_t v12; // ecx
  int CurrentIndex; // eax
  int *v14; // ebx
  JET_SESID v15; // edi
  int TableIndexInfo; // eax
  JET_GRBIT v17; // ecx
  JET_GRBIT v18; // edi
  JET_GRBIT v19; // edx
  JET_GRBIT v20; // eax
  int *v21; // edi
  JET_GRBIT v22; // esi
  JET_ERR v23; // eax
  int v24; // ecx
  const unsigned __int16 *v25; // eax
  int v26; // eax
  int v27; // eax
  int v28; // eax
  JET_ERR v29; // eax
  CImpIRowsetIndex *v30; // esi
  JET_GRBIT v31; // eax
  JET_ERR v32; // eax
  CImpIRowsetIndex *v33; // edx
  JET_GRBIT v34; // ecx
  int v36; // [esp-14h] [ebp-188h]
  int v37; // [esp+10h] [ebp-164h]
  int v38; // [esp+14h] [ebp-160h] BYREF
  int v39; // [esp+18h] [ebp-15Ch]
  int *v40; // [esp+1Ch] [ebp-158h]
  unsigned int pcbActual; // [esp+20h] [ebp-154h] BYREF
  int v42; // [esp+24h] [ebp-150h] BYREF
  CImpIRowsetIndex *v43; // [esp+28h] [ebp-14Ch]
  JET_SESID sesid; // [esp+2Ch] [ebp-148h]
  char v45[4]; // [esp+30h] [ebp-144h] BYREF
  JET_TABLEID tableid; // [esp+34h] [ebp-140h]
  JET_GRBIT v47; // [esp+38h] [ebp-13Ch]
  JET_COLUMNID v48; // [esp+64h] [ebp-110h]
  JET_COLUMNID columnid; // [esp+68h] [ebp-10Ch]
  unsigned __int16 pvData[130]; // [esp+6Ch] [ebp-108h] BYREF

  v5 = this;
  v6 = 0;
  v40 = a5;
  v7 = (_DWORD *)*((_DWORD *)this + 2);
  v43 = v5;
  v42 = 0;
  v8 = v7[27];
  v9 = *(_DWORD *)(v7[14] + 16);
  tableid = -1;
  v10 = v7[46];
  sesid = v9;
  if ( a2 == v10 && v7[48] == grbit )
    return v6;
  if ( v10 )
  {
    v7[46] = 0;
    *(_DWORD *)(*((_DWORD *)v5 + 2) + 188) = 0;
    *(_DWORD *)(*((_DWORD *)v5 + 2) + 192) = 0;
    *(_DWORD *)(*((_DWORD *)v5 + 2) + 196) = 0;
    *(_DWORD *)(*((_DWORD *)v5 + 2) + 200) = 0;
    v6 = (*(int (__thiscall **)(_DWORD, _DWORD, int, _DWORD))(**(_DWORD **)(*((_DWORD *)v5 + 2) + 12) + 24))(
           *(_DWORD *)(**(_DWORD **)(*((_DWORD *)v5 + 2) + 12) + 24),
           *(_DWORD *)(*((_DWORD *)v5 + 2) + 12),
           v10,
           0);
    if ( v6 < 0 )
      goto LABEL_54;
    v5 = v43;
  }
  v11 = *(size_t **)(*((_DWORD *)v5 + 2) + 100);
  v12 = v11[6];
  if ( a2 > v12 + 8 * v11[5] - 1
    || (*(_BYTE *)(((a2 - v12) >> 3) + v11[4]) & *((_BYTE *)&Bitmap::ThisBit + ((a2 - v12) & 7))) != 0
    || (memcpy(&v42, (const void *)(v11[2] + a2 * *v11), *v11), !v42) )
  {
    v6 = -2147217920;
    goto LABEL_54;
  }
  v6 = 0;
  if ( *(_DWORD *)(v42 + 36) )
  {
    CurrentIndex = JetGetCurrentIndex(sesid, v8, pvData, 129);
    v14 = v40;
    *v40 = CurrentIndex;
    if ( CurrentIndex >= 0 )
    {
      v36 = v8;
      v15 = sesid;
      TableIndexInfo = JetGetTableIndexInfo(sesid, v36, pvData, v45, 60, 1);
      *v14 = TableIndexInfo;
      if ( TableIndexInfo < 0 )
      {
LABEL_13:
        v6 = -2147467259;
        goto LABEL_55;
      }
      v17 = v47;
      v18 = grbit;
      if ( grbit > v47 || grbit > *(_DWORD *)(v42 + 36) )
      {
        v6 = -2147024809;
        goto LABEL_54;
      }
      v19 = 0;
      v20 = grbit;
      v39 = 0;
      v6 = 0;
      if ( v47 < grbit )
        v20 = v47;
      if ( !v20 )
      {
        v30 = v43;
LABEL_42:
        if ( !v18 && v17 )
        {
          v32 = JetRetrieveColumn(sesid, tableid, v48, &v38, 4u, &pcbActual, 0, 0);
          *v40 = v32;
          if ( v32 < 0 )
          {
            v6 = -2147467259;
            goto LABEL_54;
          }
          *(_DWORD *)(*((_DWORD *)v30 + 2) + 200) |= v38 & 1;
        }
        if ( v6 >= 0 )
        {
          v6 = (*(int (__thiscall **)(_DWORD, _DWORD, unsigned int, _DWORD))(**(_DWORD **)(*((_DWORD *)v30 + 2) + 12)
                                                                           + 12))(
                 *(_DWORD *)(**(_DWORD **)(*((_DWORD *)v30 + 2) + 12) + 12),
                 *(_DWORD *)(*((_DWORD *)v30 + 2) + 12),
                 a2,
                 0);
          if ( v6 >= 0 )
          {
            v33 = v43;
            *(_DWORD *)(*((_DWORD *)v43 + 2) + 184) = a2;
            v34 = v18;
            if ( *(_DWORD *)(v42 + 36) < v18 )
              v34 = *(_DWORD *)(v42 + 36);
            *(_DWORD *)(*((_DWORD *)v33 + 2) + 188) = v34 < v47;
            *(_DWORD *)(*((_DWORD *)v33 + 2) + 192) = v18;
            *(_DWORD *)(*((_DWORD *)v33 + 2) + 196) = v47;
          }
        }
        goto LABEL_54;
      }
      while ( 1 )
      {
        pcbActual = 0;
        v21 = 0;
        v37 = 0;
        v22 = v42 + 52 * v19;
        if ( (*(_BYTE *)(v22 + 68) & 4) != 0 )
        {
          v21 = (int *)&a4[*(_DWORD *)(v22 + 52)];
          if ( v21 )
            v37 = *v21;
        }
        v23 = JetRetrieveColumn(sesid, tableid, columnid, pvData, 0x102u, &pcbActual, 0, 0);
        *v40 = v23;
        if ( v23 < 0 )
          break;
        if ( (pcbActual & 0xFFFFFFFE) >= 0x102 )
          __report_rangecheckfailure();
        *(unsigned __int16 *)((char *)pvData + (pcbActual & 0xFFFFFFFE)) = 0;
        v24 = *(_DWORD *)(*(_DWORD *)(*((_DWORD *)v43 + 2) + 148) + 12) + 104 * *(_DWORD *)(v22 + 40);
        v25 = *(const unsigned __int16 **)(v24 - 100);
        if ( !v25 )
        {
          v26 = *(_DWORD *)(v24 - 80);
          if ( v26 && (unsigned int)(v26 - 2) >= 2 )
            v25 = 0;
          else
            v25 = *(const unsigned __int16 **)(v24 - 76);
        }
        v27 = wcscmp(pvData, v25);
        if ( v27 )
          v27 = v27 < 0 ? -1 : 1;
        if ( v27 )
        {
          v28 = 1;
          v6 = -2147217912;
        }
        else
        {
          v28 = v37;
        }
        if ( v21 )
          *v21 = v28;
        v15 = sesid;
        v29 = JetRetrieveColumn(sesid, tableid, v48, &v38, 4u, &pcbActual, 0, 0);
        *v40 = v29;
        if ( v29 < 0 )
          goto LABEL_13;
        v30 = v43;
        *(_DWORD *)(*((_DWORD *)v43 + 2) + 200) |= (v38 & 1) << v39;
        JetMove(v15, tableid, 1, 0);
        v18 = grbit;
        v19 = v39 + 1;
        v17 = v47;
        v31 = grbit;
        ++v39;
        if ( v47 < grbit )
          v31 = v47;
        if ( v19 >= v31 )
          goto LABEL_42;
      }
    }
    v6 = -2147467259;
  }
LABEL_54:
  v15 = sesid;
LABEL_55:
  if ( tableid != -1 )
    JetCloseTable(v15, tableid);
  return v6;
}

```

## disassembly

```asm
0x1002fa60  mov     edi, edi
0x1002fa62  push    ebp
0x1002fa63  mov     ebp, esp
0x1002fa65  sub     esp, 168h
0x1002fa6b  mov     eax, ___security_cookie
0x1002fa70  xor     eax, ebp
0x1002fa72  mov     [ebp+var_4], eax
0x1002fa75  mov     eax, [ebp+arg_8]
0x1002fa78  push    ebx
0x1002fa79  push    esi
0x1002fa7a  mov     esi, ecx
0x1002fa7c  mov     [ebp+var_168], eax
0x1002fa82  mov     eax, [ebp+arg_C]
0x1002fa85  xor     ebx, ebx
0x1002fa87  mov     [ebp+var_158], eax
0x1002fa8d  push    edi
0x1002fa8e  mov     ecx, [esi+8]
0x1002fa91  mov     [ebp+var_14C], esi
0x1002fa97  mov     [ebp+var_150], ebx
0x1002fa9d  mov     eax, [ecx+38h]
0x1002faa0  mov     edi, [ecx+6Ch]
0x1002faa3  mov     eax, [eax+10h]
0x1002faa6  mov     [ebp+tableid], 0FFFFFFFFh
0x1002fab0  mov     edx, [ecx+0B8h]
0x1002fab6  mov     [ebp+sesid], eax
0x1002fabc  cmp     [ebp+arg_0], edx
0x1002fabf  jnz     short loc_1002FAD0
0x1002fac1  mov     eax, [ebp+grbit]
0x1002fac4  cmp     [ecx+0C0h], eax
0x1002faca  jz      loc_1002FED8
0x1002fad0  test    edx, edx
0x1002fad2  jz      short loc_1002FB27
0x1002fad4  mov     [ecx+0B8h], ebx
0x1002fada  mov     eax, [esi+8]
0x1002fadd  push    0
0x1002fadf  push    edx
0x1002fae0  mov     [eax+0BCh], ebx
0x1002fae6  mov     eax, [esi+8]
0x1002fae9  mov     [eax+0C0h], ebx
0x1002faef  mov     eax, [esi+8]
0x1002faf2  mov     [eax+0C4h], ebx
0x1002faf8  mov     eax, [esi+8]
0x1002fafb  mov     [eax+0C8h], ebx
0x1002fb01  mov     eax, [esi+8]
0x1002fb04  mov     ecx, [eax+0Ch]
0x1002fb07  push    ecx
0x1002fb08  mov     eax, [ecx]
0x1002fb0a  mov     esi, [eax+18h]
0x1002fb0d  mov     ecx, esi
0x1002fb0f  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1002fb15  call    esi
0x1002fb17  mov     ebx, eax
0x1002fb19  test    ebx, ebx
0x1002fb1b  js      loc_1002FEBF
0x1002fb21  mov     esi, [ebp+var_14C]
0x1002fb27  mov     eax, [esi+8]
0x1002fb2a  mov     ebx, [ebp+arg_0]
0x1002fb2d  mov     esi, [eax+64h]
0x1002fb30  mov     eax, [esi+14h]
0x1002fb33  mov     ecx, [esi+18h]
0x1002fb36  lea     eax, ds:0FFFFFFFFh[eax*8]
0x1002fb3d  add     eax, ecx
0x1002fb3f  cmp     ebx, eax
0x1002fb41  ja      loc_1002FEBA
0x1002fb47  mov     eax, [esi+10h]
0x1002fb4a  mov     edx, ebx
0x1002fb4c  sub     edx, ecx
0x1002fb4e  mov     ecx, edx
0x1002fb50  and     edx, 7
0x1002fb53  shr     ecx, 3
0x1002fb56  mov     al, [ecx+eax]
0x1002fb59  test    ds:?ThisBit@Bitmap@@1QBEB[edx], al; uchar const * const Bitmap::ThisBit
0x1002fb5f  jnz     loc_1002FEBA
0x1002fb65  mov     eax, [esi]
0x1002fb67  push    eax; Size
0x1002fb68  imul    eax, ebx
0x1002fb6b  add     eax, [esi+8]
0x1002fb6e  push    eax; Src
0x1002fb6f  lea     eax, [ebp+var_150]
0x1002fb75  push    eax; void *
0x1002fb76  call    _memcpy
0x1002fb7b  mov     eax, [ebp+var_150]
0x1002fb81  add     esp, 0Ch
0x1002fb84  xor     esi, esi
0x1002fb86  test    eax, eax
0x1002fb88  jz      loc_1002FEBA
0x1002fb8e  mov     ebx, esi
0x1002fb90  cmp     [eax+24h], ebx
0x1002fb93  jz      loc_1002FEBF
0x1002fb99  push    81h
0x1002fb9e  lea     eax, [ebp+pvData]
0x1002fba4  push    eax
0x1002fba5  push    edi
0x1002fba6  push    [ebp+sesid]
0x1002fbac  call    ds:__imp__JetGetCurrentIndex@16; JetGetCurrentIndex(x,x,x,x)
0x1002fbb2  mov     ebx, [ebp+var_158]
0x1002fbb8  mov     [ebx], eax
0x1002fbba  test    eax, eax
0x1002fbbc  jns     short loc_1002FBC8
0x1002fbbe  mov     ebx, 80004005h
0x1002fbc3  jmp     loc_1002FEBF
0x1002fbc8  push    1
0x1002fbca  push    3Ch ; '<'
0x1002fbcc  lea     eax, [ebp+var_144]
0x1002fbd2  push    eax
0x1002fbd3  lea     eax, [ebp+pvData]
0x1002fbd9  push    eax
0x1002fbda  push    edi
0x1002fbdb  mov     edi, [ebp+sesid]
0x1002fbe1  push    edi
0x1002fbe2  call    ds:__imp__JetGetTableIndexInfo@24; JetGetTableIndexInfo(x,x,x,x,x,x)
0x1002fbe8  mov     [ebx], eax
0x1002fbea  test    eax, eax
0x1002fbec  jns     short loc_1002FBF8
0x1002fbee  mov     ebx, 80004005h
0x1002fbf3  jmp     loc_1002FEC5
0x1002fbf8  mov     ecx, [ebp+var_13C]
0x1002fbfe  mov     edi, [ebp+grbit]
0x1002fc01  cmp     edi, ecx
0x1002fc03  ja      loc_1002FEB3
0x1002fc09  mov     eax, [ebp+var_150]
0x1002fc0f  cmp     edi, [eax+24h]
0x1002fc12  ja      loc_1002FEB3
0x1002fc18  xor     edx, edx
0x1002fc1a  mov     eax, edi
0x1002fc1c  cmp     ecx, edi
0x1002fc1e  mov     [ebp+var_15C], edx
0x1002fc24  mov     ebx, esi
0x1002fc26  cmovb   eax, ecx
0x1002fc29  test    eax, eax
0x1002fc2b  jz      loc_1002FDDC
0x1002fc31  imul    esi, edx, 34h ; '4'
0x1002fc34  xor     eax, eax
0x1002fc36  mov     [ebp+pcbActual], eax
0x1002fc3c  xor     edi, edi
0x1002fc3e  mov     [ebp+var_164], eax
0x1002fc44  add     esi, [ebp+var_150]
0x1002fc4a  test    byte ptr [esi+44h], 4
0x1002fc4e  jz      short loc_1002FC63
0x1002fc50  mov     edi, [esi+34h]
0x1002fc53  add     edi, [ebp+var_168]
0x1002fc59  jz      short loc_1002FC63
0x1002fc5b  mov     eax, [edi]
0x1002fc5d  mov     [ebp+var_164], eax
0x1002fc63  push    0; pretinfo
0x1002fc65  push    0; grbit
0x1002fc67  lea     eax, [ebp+pcbActual]
0x1002fc6d  push    eax; pcbActual
0x1002fc6e  push    102h; cbData
0x1002fc73  lea     eax, [ebp+pvData]
0x1002fc79  push    eax; pvData
0x1002fc7a  push    [ebp+columnid]; columnid
0x1002fc80  push    [ebp+tableid]; tableid
0x1002fc86  push    [ebp+sesid]; sesid
0x1002fc8c  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x1002fc92  mov     ecx, [ebp+var_158]
0x1002fc98  mov     [ecx], eax
0x1002fc9a  test    eax, eax
0x1002fc9c  js      loc_1002FBBE
0x1002fca2  mov     eax, [ebp+pcbActual]
0x1002fca8  and     eax, 0FFFFFFFEh
0x1002fcab  cmp     eax, 102h
0x1002fcb0  jnb     loc_1002FEED
0x1002fcb6  xor     ecx, ecx
0x1002fcb8  mov     [ebp+eax+pvData], cx
0x1002fcc0  mov     eax, [ebp+var_14C]
0x1002fcc6  imul    ecx, [esi+28h], 68h ; 'h'
0x1002fcca  mov     eax, [eax+8]
0x1002fccd  mov     eax, [eax+94h]
0x1002fcd3  add     ecx, [eax+0Ch]
0x1002fcd6  mov     eax, [ecx-64h]
0x1002fcd9  test    eax, eax
0x1002fcdb  jnz     short loc_1002FCF6
0x1002fcdd  mov     eax, [ecx-50h]
0x1002fce0  sub     eax, 0
0x1002fce3  jz      short loc_1002FCF3
0x1002fce5  sub     eax, 2
0x1002fce8  jz      short loc_1002FCF3
0x1002fcea  sub     eax, 1
0x1002fced  jz      short loc_1002FCF3
0x1002fcef  xor     eax, eax
0x1002fcf1  jmp     short loc_1002FCF6
0x1002fcf3  mov     eax, [ecx-4Ch]
0x1002fcf6  lea     ecx, [ebp+pvData]
0x1002fcfc  nop     dword ptr [eax+00h]
0x1002fd00  mov     dx, [ecx]
0x1002fd03  cmp     dx, [eax]
0x1002fd06  jnz     short loc_1002FD26
0x1002fd08  test    dx, dx
0x1002fd0b  jz      short loc_1002FD22
0x1002fd0d  mov     dx, [ecx+2]
0x1002fd11  cmp     dx, [eax+2]
0x1002fd15  jnz     short loc_1002FD26
0x1002fd17  add     ecx, 4
0x1002fd1a  add     eax, 4
0x1002fd1d  test    dx, dx
0x1002fd20  jnz     short loc_1002FD00
0x1002fd22  xor     eax, eax
0x1002fd24  jmp     short loc_1002FD2B
0x1002fd26  sbb     eax, eax
0x1002fd28  or      eax, 1
0x1002fd2b  test    eax, eax
0x1002fd2d  jz      short loc_1002FD3B
0x1002fd2f  mov     eax, 1
0x1002fd34  mov     ebx, 80040E08h
0x1002fd39  jmp     short loc_1002FD41
0x1002fd3b  mov     eax, [ebp+var_164]
0x1002fd41  test    edi, edi
0x1002fd43  jz      short loc_1002FD47
0x1002fd45  mov     [edi], eax
0x1002fd47  mov     edi, [ebp+sesid]
0x1002fd4d  lea     eax, [ebp+pcbActual]
0x1002fd53  push    0; pretinfo
0x1002fd55  push    0; grbit
0x1002fd57  push    eax; pcbActual
0x1002fd58  push    4; cbData
0x1002fd5a  lea     eax, [ebp+var_160]
0x1002fd60  push    eax; pvData
0x1002fd61  push    [ebp+var_110]; columnid
0x1002fd67  push    [ebp+tableid]; tableid
0x1002fd6d  push    edi; sesid
0x1002fd6e  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x1002fd74  mov     ecx, [ebp+var_158]
0x1002fd7a  mov     [ecx], eax
0x1002fd7c  test    eax, eax
0x1002fd7e  js      loc_1002FBEE
0x1002fd84  mov     esi, [ebp+var_14C]
0x1002fd8a  mov     eax, [ebp+var_160]
0x1002fd90  mov     ecx, [ebp+var_15C]
0x1002fd96  and     eax, 1
0x1002fd99  push    0; grbit
0x1002fd9b  mov     edx, [esi+8]
0x1002fd9e  shl     eax, cl
0x1002fda0  push    1; cRow
0x1002fda2  or      [edx+0C8h], eax
0x1002fda8  push    [ebp+tableid]; tableid
0x1002fdae  push    edi; sesid
0x1002fdaf  call    ds:__imp__JetMove@16; JetMove(x,x,x,x)
0x1002fdb5  mov     edx, [ebp+var_15C]
0x1002fdbb  mov     edi, [ebp+grbit]
0x1002fdbe  inc     edx
0x1002fdbf  mov     ecx, [ebp+var_13C]
0x1002fdc5  mov     eax, edi
0x1002fdc7  cmp     ecx, edi
0x1002fdc9  mov     [ebp+var_15C], edx
0x1002fdcf  cmovb   eax, ecx
0x1002fdd2  cmp     edx, eax
0x1002fdd4  jb      loc_1002FC31
0x1002fdda  jmp     short loc_1002FDE2
0x1002fddc  mov     esi, [ebp+var_14C]
0x1002fde2  test    edi, edi
0x1002fde4  jnz     short loc_1002FE3C
0x1002fde6  test    ecx, ecx
0x1002fde8  jz      short loc_1002FE3C
0x1002fdea  push    edi; pretinfo
0x1002fdeb  push    edi; grbit
0x1002fdec  lea     eax, [ebp+pcbActual]
0x1002fdf2  push    eax; pcbActual
0x1002fdf3  push    4; cbData
0x1002fdf5  lea     eax, [ebp+var_160]
0x1002fdfb  push    eax; pvData
0x1002fdfc  push    [ebp+var_110]; columnid
0x1002fe02  push    [ebp+tableid]; tableid
0x1002fe08  push    [ebp+sesid]; sesid
0x1002fe0e  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x1002fe14  mov     ecx, [ebp+var_158]
0x1002fe1a  mov     [ecx], eax
0x1002fe1c  test    eax, eax
0x1002fe1e  jns     short loc_1002FE2A
0x1002fe20  mov     ebx, 80004005h
0x1002fe25  jmp     loc_1002FEBF
0x1002fe2a  mov     ecx, [esi+8]
0x1002fe2d  mov     eax, [ebp+var_160]
0x1002fe33  and     eax, 1
0x1002fe36  or      [ecx+0C8h], eax
0x1002fe3c  test    ebx, ebx
0x1002fe3e  js      loc_1002FEBF
0x1002fe44  mov     eax, [esi+8]
0x1002fe47  push    0
0x1002fe49  push    [ebp+arg_0]
0x1002fe4c  mov     ecx, [eax+0Ch]
0x1002fe4f  push    ecx
0x1002fe50  mov     eax, [ecx]
0x1002fe52  mov     esi, [eax+0Ch]
0x1002fe55  mov     ecx, esi
0x1002fe57  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1002fe5d  call    esi
0x1002fe5f  mov     ebx, eax
0x1002fe61  test    ebx, ebx
0x1002fe63  js      short loc_1002FEBF
0x1002fe65  mov     edx, [ebp+var_14C]
0x1002fe6b  mov     ecx, [ebp+arg_0]
0x1002fe6e  mov     eax, [edx+8]
0x1002fe71  mov     [eax+0B8h], ecx
0x1002fe77  mov     ecx, edi
0x1002fe79  mov     eax, [ebp+var_150]
0x1002fe7f  cmp     [eax+24h], edi
0x1002fe82  cmovb   ecx, [eax+24h]
0x1002fe86  cmp     ecx, [ebp+var_13C]
0x1002fe8c  mov     eax, [edx+8]
  ... truncated ...
```
