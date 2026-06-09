# JetICopyQuerySesid(x,x,x,x,x,x,x,x)

- ea: `0x1008be3f`
- end: `0x1008c56b`
- name: `_JetICopyQuerySesid@32`
- size: `1836`
- prototype: `int __stdcall(int, JET_SESID, int, int, int, int)`
- caller_count: `2`
- callee_count: `27`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1008c580`
- `0x100cfb84`

## callees

- `0x10016970`
- `0x100325e0`
- `0x1003e7e0`
- `0x1003e930`
- `0x10043060`
- `0x100435d0`
- `0x100439d0`
- `0x10045400`
- `0x10045450`
- `0x10089260`
- `0x1008a320`
- `0x1008a3c0`
- `0x1008a460`
- `0x1008a4c0`
- `0x1008a610`
- `0x1008acb8`
- `0x1008baf0`
- `0x1008bd67`
- `0x1008be3f`
- `0x1008e960`
- `0x10094710`
- `0x100a8b10`
- `0x100c99c2`
- `0x100c9a29`
- `0x100c9a9a`
- `0x10123110`
- `0x10123b3c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1008c0db`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1008c162`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1008c53f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1008c0db`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1008c162`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1008c53f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1008c0af`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1008c0f1`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1008c0af`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1008c0f1`

## pseudocode

```c
int __fastcall JetICopyQuerySesid(JET_SESID a1, int a2, int a3, Session *a4, int a5, int a6, _DWORD *a7, int a8)
{
  char *v8; // ebx
  int result; // eax
  int VtidTableid; // esi
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // eax
  _DWORD *v16; // ebx
  _DWORD *v17; // edx
  int ObjectProperties; // eax
  size_t v19; // edi
  char *v20; // eax
  char *v21; // eax
  int v22; // eax
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  int v27; // eax
  int v28; // eax
  JET_ERR v29; // eax
  int v30; // eax
  int v31[14]; // [esp-38h] [ebp-2E0h] BYREF
  int v32; // [esp+10h] [ebp-298h] BYREF
  int v33; // [esp+14h] [ebp-294h] BYREF
  JET_SESID sesid; // [esp+18h] [ebp-290h]
  int v35; // [esp+1Ch] [ebp-28Ch] BYREF
  int v36; // [esp+20h] [ebp-288h] BYREF
  int v37; // [esp+24h] [ebp-284h] BYREF
  int v38; // [esp+28h] [ebp-280h] BYREF
  int v39; // [esp+2Ch] [ebp-27Ch] BYREF
  int v40; // [esp+30h] [ebp-278h] BYREF
  int v41; // [esp+34h] [ebp-274h]
  int v42; // [esp+38h] [ebp-270h]
  int v43; // [esp+3Ch] [ebp-26Ch]
  int v44; // [esp+40h] [ebp-268h]
  int v45; // [esp+44h] [ebp-264h]
  int v46; // [esp+48h] [ebp-260h]
  int v47; // [esp+4Ch] [ebp-25Ch]
  int v48; // [esp+50h] [ebp-258h]
  int v49; // [esp+54h] [ebp-254h]
  int v50; // [esp+58h] [ebp-250h]
  int v51; // [esp+5Ch] [ebp-24Ch]
  int v52; // [esp+60h] [ebp-248h]
  int v53; // [esp+64h] [ebp-244h] BYREF
  JET_TABLEID v54[14]; // [esp+68h] [ebp-240h] BYREF
  _BYTE v55[516]; // [esp+A0h] [ebp-208h] BYREF

  v8 = 0;
  v37 = a6;
  v36 = a2;
  sesid = a1;
  v41 = (int)a7;
  memset(v54, 0, sizeof(v54));
  *a7 = -1;
  v54[1] = -1;
  if ( !FValidSesid(a1) || !FValidSesid(a4) )
    return -1104;
  if ( !FValidDbid(a1, a5) && a5 != -1 )
    return -1010;
  result = ErrGetPvtfndefTableid(a1, a3, &v40);
  if ( result >= 0 )
  {
    if ( (char *)v40 != &vtfndefQodef )
      return -1312;
    result = ErrQjetBeginTransaction(a4, 0);
    if ( result >= 0 )
    {
      VtidTableid = ErrGetVtidTableid(a1, a3, &v35);
      if ( VtidTableid < 0 )
        goto LABEL_19;
      v31[13] = 0;
      v31[12] = *(_DWORD *)(v35 + 92);
      v12 = *(_DWORD *)(v35 + 32);
      v31[11] = v41;
      v44 = v12;
      v13 = *(_DWORD *)(v35 + 36);
      v31[10] = v37;
      v45 = v13;
      v14 = *(_DWORD *)(v35 + 40);
      v31[9] = a5;
      v47 = v14;
      v42 = *(_DWORD *)(v35 + 44);
      v50 = *(_DWORD *)(v35 + 48);
      v52 = *(_DWORD *)(v35 + 52);
      VtidTableid = ErrQodefSecCreateVtQoDef(a4, a5, v37, v41, v31[12], 0);
      if ( VtidTableid < 0 )
        goto LABEL_19;
      VtidTableid = ErrGetVtidTableid(a4, *(_DWORD *)v41, &v33);
      if ( VtidTableid < 0 )
        goto LABEL_19;
      v40 = *(_DWORD *)(v33 + 32);
      v46 = *(_DWORD *)(v33 + 36);
      v48 = *(_DWORD *)(v33 + 40);
      v39 = *(_DWORD *)(v33 + 44);
      v15 = *(_DWORD *)(v33 + 52);
      v51 = *(_DWORD *)(v33 + 48);
      v43 = v15;
      if ( a5 == -1 )
      {
        if ( v37 && *(_WORD *)v37 )
          return -1003;
      }
      else
      {
        if ( !FValidDbid(a4, a5) )
        {
          VtidTableid = -1010;
          goto LABEL_19;
        }
        if ( !IsJetIsam(sesid, a5) )
        {
          VtidTableid = -1001;
          goto LABEL_19;
        }
        VtidTableid = ErrDispGetDatabaseInfo(a4, a5, &v37, 4, 8);
        if ( VtidTableid < 0 )
        {
LABEL_19:
          v16 = (_DWORD *)v41;
          if ( *(_DWORD *)v41 != -1 )
          {
            ErrDispCloseTable(a4, *(_DWORD *)v41);
            *v16 = -1;
          }
          if ( v54[1] != -1 )
          {
            ErrDispCloseTable(sesid, v54[1]);
            v54[1] = -1;
          }
          ErrQjetRollback(a4, 0);
          return VtidTableid;
        }
        if ( v37 == 0x10000 || v37 == 65537 )
        {
          v17 = (_DWORD *)v33;
          *(_DWORD *)(v33 + 100) = 1;
          goto LABEL_31;
        }
      }
      v17 = (_DWORD *)v33;
LABEL_31:
      ObjectProperties = ErrCopyQueryObjectProperties(v35, v17);
      VtidTableid = ObjectProperties;
      if ( ObjectProperties != -1507 )
      {
        if ( ObjectProperties < 0 )
          goto LABEL_19;
        if ( *(_DWORD *)(v35 + 112) )
        {
          v19 = 2048;
          v20 = (char *)_malloc(0x800u);
          v8 = v20;
          if ( !v20 )
          {
LABEL_35:
            VtidTableid = -1011;
            goto LABEL_19;
          }
          memset(&v31[10], 0, 16);
          *v20 = 0;
          v31[9] = (int)&v39;
          for ( v31[8] = 1024; ; v31[8] = v19 >> 1 )
          {
            v22 = ErrSQLRetrieveQoSql(
                    sesid,
                    a3,
                    v8,
                    v31[8],
                    (int *)v31[9],
                    (_WORD *)v31[10],
                    v31[11],
                    (_DWORD *)v31[12],
                    (_DWORD *)v31[13]);
            VtidTableid = v22;
            if ( v22 != -3515 )
              break;
            _free(v8);
            v19 *= 2;
            if ( v19 >= 0x10000 )
            {
              VtidTableid = -3071;
              goto LABEL_19;
            }
            v21 = (char *)_malloc(v19);
            v8 = v21;
            if ( !v21 )
              goto LABEL_35;
            memset(&v31[10], 0, 16);
            *v21 = 0;
            v31[9] = (int)&v39;
          }
          v40 = (int)v8;
          if ( v22 < 0 )
            goto LABEL_92;
          VtidTableid = ErrSQLSetQoSql(a4, -1, *(_DWORD *)v41, v8, v39, 0, 0);
          if ( VtidTableid >= 0 )
          {
            if ( v8 )
            {
              _free(v8);
              v8 = 0;
            }
            goto LABEL_90;
          }
          goto LABEL_91;
        }
      }
      if ( a8 )
      {
        VtidTableid = JetGetTempQueryColumnInfo(sesid, v36, a3, 0, v54, 56, 2);
        if ( VtidTableid < 0 )
          goto LABEL_19;
      }
      v31[13] = 0;
      for ( v31[12] = 0x80000000; ; v31[12] = 1 )
      {
        v30 = ErrQodefMove(sesid, v35, v31[12], v31[13]);
        VtidTableid = v30;
        if ( v30 < 0 )
        {
          if ( v30 != -1603 )
            goto LABEL_19;
          if ( a8 && v54[2] )
          {
            qmemcpy(v31, v54, sizeof(v31));
            VtidTableid = ErrAddMoreOutputs(
                            (JET_SESID)a4,
                            v39,
                            v40,
                            v31[0],
                            v31[1],
                            v31[2],
                            v31[3],
                            v31[4],
                            v31[5],
                            v31[6],
                            v31[7],
                            v31[8],
                            v31[9],
                            v31[10],
                            v31[11],
                            v31[12],
                            v31[13]);
            if ( VtidTableid >= 0 )
            {
              ErrDispCloseTable(sesid, v54[1]);
              v54[1] = -1;
              goto LABEL_90;
            }
            goto LABEL_19;
          }
LABEL_90:
          VtidTableid = ErrQjetCommitTransaction(0);
          if ( VtidTableid < 0 )
          {
LABEL_91:
            if ( v8 )
LABEL_92:
              _free(v8);
            goto LABEL_19;
          }
          return 0;
        }
        VtidTableid = ErrQodefPrepareUpdate(a4, v33, 0);
        if ( VtidTableid < 0 )
          goto LABEL_19;
        VtidTableid = ErrQodefRetrieveColumn(sesid, v35, v44, (char *)&v32 + 3, 1, 0, 0, 0);
        if ( VtidTableid < 0 )
          goto LABEL_19;
        v37 = HIBYTE(v32) == 6;
        VtidTableid = ErrQodefSetColumn(a4, v33, v40, (char *)&v32 + 3, 1, 0, 0);
        if ( VtidTableid < 0 )
          goto LABEL_19;
        v23 = ErrQodefRetrieveColumn(sesid, v35, v45, v55, 510, &v36, 0, 0);
        VtidTableid = v23;
        if ( v23 < 0 )
          goto LABEL_19;
        if ( v23 != 1004 )
        {
          VtidTableid = ErrQodefSetColumn(a4, v33, v46, v55, v36, 0, 0);
          if ( VtidTableid < 0 )
            goto LABEL_19;
        }
        v24 = ErrQodefRetrieveColumn(sesid, v35, v47, v55, 510, &v36, 0, 0);
        VtidTableid = v24;
        if ( v24 < 0 )
          goto LABEL_19;
        if ( v24 != 1004 )
        {
          VtidTableid = ErrQodefSetColumn(a4, v33, v48, v55, v36, 0, 0);
          if ( VtidTableid < 0 )
            goto LABEL_19;
        }
        v25 = ErrQodefRetrieveColumn(sesid, v35, v42, v55, 510, &v36, 0, 0);
        VtidTableid = v25;
        if ( v25 < 0 )
          goto LABEL_19;
        if ( v25 == 1006 )
        {
          VtidTableid = ErrQodefGetLVBuf(v36 + 2);
          if ( VtidTableid < 0 )
            goto LABEL_19;
          v26 = ErrAssignLVCol(a4, v49, v36, a3, v42, a4, *(_DWORD *)v41, v39, 0);
        }
        else
        {
          if ( v25 == 1004 )
            goto LABEL_65;
          v26 = ErrQodefSetColumn(a4, v33, v39, v55, v36, 0, 0);
        }
        VtidTableid = v26;
        if ( v26 < 0 )
          goto LABEL_19;
LABEL_65:
        v27 = ErrQodefRetrieveColumn(sesid, v35, v50, &v38, 2, 0, 0, 0);
        VtidTableid = v27;
        if ( v27 < 0 )
          goto LABEL_19;
        if ( v27 != 1004 )
        {
          if ( HIBYTE(v32) == 3 && (v38 & 1) != 0 && a8 )
            LOWORD(v38) = v38 & 0xFFFE;
          VtidTableid = ErrQodefSetColumn(a4, v33, v51, &v38, 2, 0, 0);
          if ( VtidTableid < 0 )
            goto LABEL_19;
        }
        if ( v52 != -1 && v43 != -1 )
        {
          v28 = ErrQodefRetrieveColumn(sesid, v35, v52, &v53, 4, &v36, 0, 0);
          VtidTableid = v28;
          if ( v28 < 0 )
            goto LABEL_19;
          if ( v28 != 1004 )
          {
            VtidTableid = ErrQodefSetColumn(a4, v33, v43, &v53, v36, 0, 0);
            if ( VtidTableid < 0 )
              goto LABEL_19;
          }
        }
        if ( v37 && a8 )
        {
          v29 = JetMove(sesid, v54[1], 1, 0);
          VtidTableid = v29;
          if ( v29 != -1603 && v29 < 0 )
            goto LABEL_19;
          --v54[2];
        }
        VtidTableid = ErrQodefUpdate(a4, v33, 0, 0, 0);
        if ( VtidTableid < 0 )
          goto LABEL_19;
        v31[13] = 0;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1008be3f  mov     edi, edi
0x1008be41  push    ebp
0x1008be42  mov     ebp, esp
0x1008be44  and     esp, 0FFFFFFF8h
0x1008be47  sub     esp, 29Ch
0x1008be4d  mov     eax, ___security_cookie
0x1008be52  xor     eax, esp
0x1008be54  mov     [esp+29Ch+var_4], eax
0x1008be5b  mov     eax, [ebp+arg_C]
0x1008be5e  push    ebx
0x1008be5f  push    esi
0x1008be60  push    edi
0x1008be61  mov     edi, [ebp+arg_10]
0x1008be64  xor     ebx, ebx
0x1008be66  push    38h ; '8'; Size
0x1008be68  mov     [esp+2ACh+var_284], eax
0x1008be6c  mov     esi, ecx
0x1008be6e  lea     eax, [esp+2ACh+var_240]
0x1008be72  mov     [esp+2ACh+var_288], edx
0x1008be76  push    ebx; Val
0x1008be77  push    eax; void *
0x1008be78  mov     [esp+2B4h+sesid], esi
0x1008be7c  mov     [esp+2B4h+var_274], edi
0x1008be80  call    _memset
0x1008be85  add     esp, 0Ch
0x1008be88  mov     dword ptr [edi], 0FFFFFFFFh
0x1008be8e  mov     [esp+2A8h+tableid], 0FFFFFFFFh
0x1008be96  push    esi
0x1008be97  call    _FValidSesid@4; FValidSesid(x)
0x1008be9c  test    eax, eax
0x1008be9e  jz      loc_1008C54F
0x1008bea4  mov     edi, [ebp+arg_4]
0x1008bea7  push    edi
0x1008bea8  call    _FValidSesid@4; FValidSesid(x)
0x1008bead  test    eax, eax
0x1008beaf  jz      loc_1008C54F
0x1008beb5  push    [ebp+arg_8]
0x1008beb8  push    esi
0x1008beb9  call    _FValidDbid@8; FValidDbid(x,x)
0x1008bebe  test    eax, eax
0x1008bec0  jnz     short loc_1008BED2
0x1008bec2  cmp     [ebp+arg_8], 0FFFFFFFFh
0x1008bec6  jz      short loc_1008BED2
0x1008bec8  mov     eax, 0FFFFFC0Eh
0x1008becd  jmp     loc_1008C554
0x1008bed2  lea     eax, [esp+2A8h+var_278]
0x1008bed6  push    eax
0x1008bed7  push    [ebp+arg_0]
0x1008beda  push    esi
0x1008bedb  call    _ErrGetPvtfndefTableid@12; ErrGetPvtfndefTableid(x,x,x)
0x1008bee0  test    eax, eax
0x1008bee2  js      loc_1008C554
0x1008bee8  cmp     [esp+2A8h+var_278], offset _vtfndefQodef
0x1008bef0  jz      short loc_1008BEFC
0x1008bef2  mov     eax, 0FFFFFAE0h
0x1008bef7  jmp     loc_1008C554
0x1008befc  xor     edx, edx
0x1008befe  mov     ecx, edi
0x1008bf00  call    _ErrQjetBeginTransaction@8; ErrQjetBeginTransaction(x,x)
0x1008bf05  test    eax, eax
0x1008bf07  js      loc_1008C554
0x1008bf0d  lea     eax, [esp+2A8h+var_28C]
0x1008bf11  push    eax
0x1008bf12  push    [ebp+arg_0]
0x1008bf15  push    esi
0x1008bf16  call    _ErrGetVtidTableid@12; ErrGetVtidTableid(x,x,x)
0x1008bf1b  mov     esi, eax
0x1008bf1d  test    esi, esi
0x1008bf1f  js      loc_1008BFED
0x1008bf25  mov     eax, [esp+2A8h+var_28C]
0x1008bf29  push    0; int
0x1008bf2b  push    dword ptr [eax+5Ch]; int
0x1008bf2e  mov     ecx, [eax+20h]
0x1008bf31  push    [esp+2B0h+var_274]; int
0x1008bf35  mov     [esp+2B4h+var_268], ecx
0x1008bf39  mov     ecx, [eax+24h]
0x1008bf3c  push    [esp+2B4h+var_284]; int
0x1008bf40  mov     [esp+2B8h+var_264], ecx
0x1008bf44  mov     ecx, [eax+28h]
0x1008bf47  push    [ebp+arg_8]; int
0x1008bf4a  mov     [esp+2BCh+var_25C], ecx
0x1008bf4e  mov     ecx, [eax+2Ch]
0x1008bf51  mov     [esp+2BCh+var_270], ecx
0x1008bf55  mov     ecx, [eax+30h]
0x1008bf58  mov     [esp+2BCh+var_250], ecx
0x1008bf5c  mov     ecx, [eax+34h]
0x1008bf5f  push    edi; Session *
0x1008bf60  mov     [esp+2C0h+var_248], ecx
0x1008bf64  call    _ErrQodefSecCreateVtQoDef@24; ErrQodefSecCreateVtQoDef(x,x,x,x,x,x)
0x1008bf69  mov     esi, eax
0x1008bf6b  test    esi, esi
0x1008bf6d  js      short loc_1008BFED
0x1008bf6f  lea     eax, [esp+2A8h+var_294]
0x1008bf73  push    eax
0x1008bf74  mov     eax, [esp+2ACh+var_274]
0x1008bf78  push    dword ptr [eax]
0x1008bf7a  push    edi
0x1008bf7b  call    _ErrGetVtidTableid@12; ErrGetVtidTableid(x,x,x)
0x1008bf80  mov     esi, eax
0x1008bf82  test    esi, esi
0x1008bf84  js      short loc_1008BFED
0x1008bf86  mov     eax, [esp+2A8h+var_294]
0x1008bf8a  mov     esi, [ebp+arg_8]
0x1008bf8d  mov     ecx, [eax+20h]
0x1008bf90  mov     [esp+2A8h+var_278], ecx
0x1008bf94  mov     ecx, [eax+24h]
0x1008bf97  mov     [esp+2A8h+var_260], ecx
0x1008bf9b  mov     ecx, [eax+28h]
0x1008bf9e  mov     [esp+2A8h+var_258], ecx
0x1008bfa2  mov     ecx, [eax+2Ch]
0x1008bfa5  mov     [esp+2A8h+var_27C], ecx
0x1008bfa9  mov     ecx, [eax+30h]
0x1008bfac  mov     eax, [eax+34h]
0x1008bfaf  mov     [esp+2A8h+var_24C], ecx
0x1008bfb3  mov     [esp+2A8h+var_26C], eax
0x1008bfb7  cmp     esi, 0FFFFFFFFh
0x1008bfba  jnz     short loc_1008BFDD
0x1008bfbc  mov     eax, [esp+2A8h+var_284]
0x1008bfc0  test    eax, eax
0x1008bfc2  jz      loc_1008C079
0x1008bfc8  xor     ecx, ecx
0x1008bfca  cmp     [eax], cx
0x1008bfcd  jz      loc_1008C079
0x1008bfd3  mov     eax, 0FFFFFC15h
0x1008bfd8  jmp     loc_1008C554
0x1008bfdd  push    esi
0x1008bfde  push    edi
0x1008bfdf  call    _FValidDbid@8; FValidDbid(x,x)
0x1008bfe4  test    eax, eax
0x1008bfe6  jnz     short loc_1008C02C
0x1008bfe8  mov     esi, 0FFFFFC0Eh
0x1008bfed  mov     ebx, [esp+2A8h+var_274]
0x1008bff1  or      edi, 0FFFFFFFFh
0x1008bff4  cmp     [ebx], edi
0x1008bff6  jz      short loc_1008C004
0x1008bff8  push    dword ptr [ebx]
0x1008bffa  push    [ebp+arg_4]
0x1008bffd  call    _ErrDispCloseTable@8; ErrDispCloseTable(x,x)
0x1008c002  mov     [ebx], edi
0x1008c004  cmp     [esp+2A8h+tableid], edi
0x1008c008  jz      short loc_1008C01B
0x1008c00a  push    [esp+2A8h+tableid]
0x1008c00e  push    [esp+2ACh+sesid]
0x1008c012  call    _ErrDispCloseTable@8; ErrDispCloseTable(x,x)
0x1008c017  mov     [esp+2A8h+tableid], edi
0x1008c01b  mov     ecx, [ebp+arg_4]; Session *
0x1008c01e  push    0; int
0x1008c020  call    _ErrQjetRollback@12; ErrQjetRollback(x,x,x)
0x1008c025  mov     eax, esi
0x1008c027  jmp     loc_1008C554
0x1008c02c  mov     ecx, [esp+2A8h+sesid]
0x1008c030  mov     edx, esi
0x1008c032  call    _IsJetIsam@8; IsJetIsam(x,x)
0x1008c037  test    eax, eax
0x1008c039  jnz     short loc_1008C042
0x1008c03b  mov     esi, 0FFFFFC17h
0x1008c040  jmp     short loc_1008BFED
0x1008c042  push    8
0x1008c044  push    4
0x1008c046  lea     eax, [esp+2B0h+var_284]
0x1008c04a  push    eax
0x1008c04b  push    esi
0x1008c04c  push    edi
0x1008c04d  call    _ErrDispGetDatabaseInfo@20; ErrDispGetDatabaseInfo(x,x,x,x,x)
0x1008c052  mov     esi, eax
0x1008c054  test    esi, esi
0x1008c056  js      short loc_1008BFED
0x1008c058  cmp     [esp+2A8h+var_284], 10000h
0x1008c060  jz      short loc_1008C06C
0x1008c062  cmp     [esp+2A8h+var_284], 10001h
0x1008c06a  jnz     short loc_1008C079
0x1008c06c  mov     edx, [esp+2A8h+var_294]
0x1008c070  mov     dword ptr [edx+64h], 1
0x1008c077  jmp     short loc_1008C07D
0x1008c079  mov     edx, [esp+2A8h+var_294]
0x1008c07d  mov     ecx, [esp+2A8h+var_28C]
0x1008c081  call    _ErrCopyQueryObjectProperties@8; ErrCopyQueryObjectProperties(x,x)
0x1008c086  mov     esi, eax
0x1008c088  cmp     esi, 0FFFFFA1Dh
0x1008c08e  jz      loc_1008C17A
0x1008c094  test    esi, esi
0x1008c096  js      loc_1008BFED
0x1008c09c  mov     eax, [esp+2A8h+var_28C]
0x1008c0a0  cmp     [eax+70h], ebx
0x1008c0a3  jz      loc_1008C17A
0x1008c0a9  mov     edi, 800h
0x1008c0ae  push    edi; Size
0x1008c0af  call    ds:__imp__malloc
0x1008c0b5  mov     ebx, eax
0x1008c0b7  pop     ecx
0x1008c0b8  test    ebx, ebx
0x1008c0ba  jnz     short loc_1008C0C6
0x1008c0bc  mov     esi, 0FFFFFC0Dh
0x1008c0c1  jmp     loc_1008BFED
0x1008c0c6  xor     eax, eax
0x1008c0c8  push    eax
0x1008c0c9  push    eax
0x1008c0ca  push    eax
0x1008c0cb  push    eax
0x1008c0cc  mov     [ebx], al
0x1008c0ce  lea     eax, [esp+2B8h+var_27C]
0x1008c0d2  push    eax
0x1008c0d3  push    400h
0x1008c0d8  jmp     short loc_1008C110
0x1008c0da  push    ebx; Block
0x1008c0db  call    ds:__imp__free
0x1008c0e1  add     edi, edi
0x1008c0e3  pop     ecx
0x1008c0e4  cmp     edi, 10000h
0x1008c0ea  jnb     loc_1008C170
0x1008c0f0  push    edi; Size
0x1008c0f1  call    ds:__imp__malloc
0x1008c0f7  mov     ebx, eax
0x1008c0f9  pop     ecx
0x1008c0fa  test    ebx, ebx
0x1008c0fc  jz      short loc_1008C0BC
0x1008c0fe  xor     eax, eax
0x1008c100  push    eax; int
0x1008c101  push    eax; int
0x1008c102  push    eax; int
0x1008c103  push    eax; int
0x1008c104  mov     [ebx], al
0x1008c106  lea     eax, [esp+2B8h+var_27C]
0x1008c10a  push    eax; int
0x1008c10b  mov     eax, edi
0x1008c10d  shr     eax, 1
0x1008c10f  push    eax; int
0x1008c110  push    ebx; Src
0x1008c111  push    [ebp+arg_0]; int
0x1008c114  push    [esp+2C8h+sesid]; int
0x1008c118  call    _ErrSQLRetrieveQoSql@36; ErrSQLRetrieveQoSql(x,x,x,x,x,x,x,x,x)
0x1008c11d  mov     esi, eax
0x1008c11f  cmp     esi, 0FFFFF245h
0x1008c125  jz      short loc_1008C0DA
0x1008c127  mov     [esp+2A8h+var_278], ebx
0x1008c12b  test    esi, esi
0x1008c12d  js      loc_1008C53E
0x1008c133  mov     edi, [ebp+arg_4]
0x1008c136  xor     eax, eax
0x1008c138  push    eax
0x1008c139  push    eax
0x1008c13a  push    [esp+2B0h+var_27C]
0x1008c13e  mov     eax, [esp+2B4h+var_274]
0x1008c142  push    ebx
0x1008c143  push    dword ptr [eax]
0x1008c145  push    0FFFFFFFFh
0x1008c147  push    edi
0x1008c148  call    _ErrSQLSetQoSql@28; ErrSQLSetQoSql(x,x,x,x,x,x,x)
0x1008c14d  mov     esi, eax
0x1008c14f  test    esi, esi
0x1008c151  js      loc_1008C536
0x1008c157  mov     eax, ebx
0x1008c159  test    eax, eax
0x1008c15b  jz      loc_1008C524
0x1008c161  push    eax; Block
0x1008c162  call    ds:__imp__free
0x1008c168  pop     ecx
0x1008c169  xor     ebx, ebx
0x1008c16b  jmp     loc_1008C524
0x1008c170  mov     esi, 0FFFFF401h
0x1008c175  jmp     loc_1008BFED
0x1008c17a  cmp     [ebp+arg_14], ebx
0x1008c17d  jz      short loc_1008C1A4
0x1008c17f  push    2
0x1008c181  push    38h ; '8'
0x1008c183  lea     eax, [esp+2B0h+var_240]
0x1008c187  push    eax
0x1008c188  push    0
0x1008c18a  push    [ebp+arg_0]
0x1008c18d  push    [esp+2BCh+var_288]
0x1008c191  push    [esp+2C0h+sesid]
0x1008c195  call    _JetGetTempQueryColumnInfo@28; JetGetTempQueryColumnInfo(x,x,x,x,x,x,x)
0x1008c19a  mov     esi, eax
0x1008c19c  test    esi, esi
0x1008c19e  js      loc_1008BFED
0x1008c1a4  push    0
0x1008c1a6  push    80000000h
0x1008c1ab  jmp     loc_1008C4B3
0x1008c1b0  xor     ecx, ecx
0x1008c1b2  push    ecx
0x1008c1b3  push    [esp+2ACh+var_294]
0x1008c1b7  push    edi
0x1008c1b8  call    _ErrQodefPrepareUpdate@12; ErrQodefPrepareUpdate(x,x,x)
0x1008c1bd  mov     esi, eax
0x1008c1bf  test    esi, esi
0x1008c1c1  js      loc_1008BFED
0x1008c1c7  xor     eax, eax
0x1008c1c9  push    eax
0x1008c1ca  push    eax
0x1008c1cb  push    eax
0x1008c1cc  push    1
0x1008c1ce  lea     eax, [esp+2B8h+var_298+3]
0x1008c1d2  push    eax
0x1008c1d3  push    [esp+2BCh+var_268]
0x1008c1d7  push    [esp+2C0h+var_28C]
0x1008c1db  push    [esp+2C4h+sesid]
0x1008c1df  call    _ErrQodefRetrieveColumn@32; ErrQodefRetrieveColumn(x,x,x,x,x,x,x,x)
0x1008c1e4  mov     esi, eax
0x1008c1e6  test    esi, esi
0x1008c1e8  js      loc_1008BFED
  ... truncated ...
```
