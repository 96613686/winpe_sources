# JetICopyQuerySesid(x,x,x,x,x,x,x,x)

- ea: `0x1008bcaf`
- end: `0x1008c3db`
- name: `_JetICopyQuerySesid@32`
- size: `1836`
- prototype: `int __stdcall(int, JET_SESID, int, int, int, int)`
- caller_count: `2`
- callee_count: `27`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1008c3f0`
- `0x100cf9f4`

## callees

- `0x10016830`
- `0x10032440`
- `0x1003e650`
- `0x1003e7a0`
- `0x10042ed0`
- `0x10043440`
- `0x10043840`
- `0x10045280`
- `0x100452d0`
- `0x100890d0`
- `0x1008a190`
- `0x1008a230`
- `0x1008a2d0`
- `0x1008a330`
- `0x1008a480`
- `0x1008ab28`
- `0x1008b960`
- `0x1008bbd7`
- `0x1008bcaf`
- `0x1008e7d0`
- `0x10094580`
- `0x100a8980`
- `0x100c9832`
- `0x100c9899`
- `0x100c990a`
- `0x10122f60`
- `0x1012398c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1008bf4b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1008bfd2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1008c3af`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1008bf4b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1008bfd2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1008c3af`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1008bf1f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1008bf61`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1008bf1f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1008bf61`

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
  int ObjectProperties; // eax
  size_t v18; // edi
  char *v19; // eax
  char *v20; // eax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  int v27; // eax
  JET_ERR v28; // eax
  int v29; // eax
  int v30[14]; // [esp-38h] [ebp-2E0h] BYREF
  int v31; // [esp+10h] [ebp-298h] BYREF
  int v32; // [esp+14h] [ebp-294h] BYREF
  JET_SESID sesid; // [esp+18h] [ebp-290h]
  int v34; // [esp+1Ch] [ebp-28Ch] BYREF
  int v35; // [esp+20h] [ebp-288h] BYREF
  int v36; // [esp+24h] [ebp-284h] BYREF
  int v37; // [esp+28h] [ebp-280h] BYREF
  int v38; // [esp+2Ch] [ebp-27Ch] BYREF
  int v39; // [esp+30h] [ebp-278h] BYREF
  int v40; // [esp+34h] [ebp-274h]
  int v41; // [esp+38h] [ebp-270h]
  int v42; // [esp+3Ch] [ebp-26Ch]
  int v43; // [esp+40h] [ebp-268h]
  int v44; // [esp+44h] [ebp-264h]
  int v45; // [esp+48h] [ebp-260h]
  int v46; // [esp+4Ch] [ebp-25Ch]
  int v47; // [esp+50h] [ebp-258h]
  int v48; // [esp+54h] [ebp-254h]
  int v49; // [esp+58h] [ebp-250h]
  int v50; // [esp+5Ch] [ebp-24Ch]
  int v51; // [esp+60h] [ebp-248h]
  int v52; // [esp+64h] [ebp-244h] BYREF
  JET_TABLEID v53[14]; // [esp+68h] [ebp-240h] BYREF
  _BYTE v54[516]; // [esp+A0h] [ebp-208h] BYREF

  v8 = 0;
  v36 = a6;
  v35 = a2;
  sesid = a1;
  v40 = (int)a7;
  memset(v53, 0, sizeof(v53));
  *a7 = -1;
  v53[1] = -1;
  if ( !FValidSesid(a1) || !FValidSesid(a4) )
    return -1104;
  if ( !FValidDbid(a1, a5) && a5 != -1 )
    return -1010;
  result = ErrGetPvtfndefTableid(a1, a3, &v39);
  if ( result >= 0 )
  {
    if ( (char *)v39 != &vtfndefQodef )
      return -1312;
    result = ErrQjetBeginTransaction(a4, 0);
    if ( result >= 0 )
    {
      VtidTableid = ErrGetVtidTableid(a1, a3, &v34);
      if ( VtidTableid < 0 )
        goto LABEL_19;
      v30[13] = 0;
      v30[12] = *(_DWORD *)(v34 + 92);
      v12 = *(_DWORD *)(v34 + 32);
      v30[11] = v40;
      v43 = v12;
      v13 = *(_DWORD *)(v34 + 36);
      v30[10] = v36;
      v44 = v13;
      v14 = *(_DWORD *)(v34 + 40);
      v30[9] = a5;
      v46 = v14;
      v41 = *(_DWORD *)(v34 + 44);
      v49 = *(_DWORD *)(v34 + 48);
      v51 = *(_DWORD *)(v34 + 52);
      VtidTableid = ErrQodefSecCreateVtQoDef(a4, a5, v36, v40, v30[12], 0);
      if ( VtidTableid < 0 )
        goto LABEL_19;
      VtidTableid = ErrGetVtidTableid(a4, *(_DWORD *)v40, &v32);
      if ( VtidTableid < 0 )
        goto LABEL_19;
      v39 = *(_DWORD *)(v32 + 32);
      v45 = *(_DWORD *)(v32 + 36);
      v47 = *(_DWORD *)(v32 + 40);
      v38 = *(_DWORD *)(v32 + 44);
      v15 = *(_DWORD *)(v32 + 52);
      v50 = *(_DWORD *)(v32 + 48);
      v42 = v15;
      if ( a5 == -1 )
      {
        if ( v36 && *(_WORD *)v36 )
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
        VtidTableid = ErrDispGetDatabaseInfo(a4, a5, &v36, 4, 8);
        if ( VtidTableid < 0 )
        {
LABEL_19:
          v16 = (_DWORD *)v40;
          if ( *(_DWORD *)v40 != -1 )
          {
            ErrDispCloseTable(a4, *(_DWORD *)v40);
            *v16 = -1;
          }
          if ( v53[1] != -1 )
          {
            ErrDispCloseTable(sesid, v53[1]);
            v53[1] = -1;
          }
          ErrQjetRollback(a4, 0);
          return VtidTableid;
        }
        if ( v36 == 0x10000 || v36 == 65537 )
          *(_DWORD *)(v32 + 100) = 1;
      }
      ObjectProperties = ErrCopyQueryObjectProperties(v34);
      VtidTableid = ObjectProperties;
      if ( ObjectProperties != -1507 )
      {
        if ( ObjectProperties < 0 )
          goto LABEL_19;
        if ( *(_DWORD *)(v34 + 112) )
        {
          v18 = 2048;
          v19 = (char *)_malloc(0x800u);
          v8 = v19;
          if ( !v19 )
          {
LABEL_34:
            VtidTableid = -1011;
            goto LABEL_19;
          }
          memset(&v30[10], 0, 16);
          *v19 = 0;
          v30[9] = (int)&v38;
          for ( v30[8] = 1024; ; v30[8] = v18 >> 1 )
          {
            v21 = ErrSQLRetrieveQoSql(
                    sesid,
                    a3,
                    v8,
                    v30[8],
                    (int *)v30[9],
                    (_WORD *)v30[10],
                    v30[11],
                    (_DWORD *)v30[12],
                    (_DWORD *)v30[13]);
            VtidTableid = v21;
            if ( v21 != -3515 )
              break;
            _free(v8);
            v18 *= 2;
            if ( v18 >= 0x10000 )
            {
              VtidTableid = -3071;
              goto LABEL_19;
            }
            v20 = (char *)_malloc(v18);
            v8 = v20;
            if ( !v20 )
              goto LABEL_34;
            memset(&v30[10], 0, 16);
            *v20 = 0;
            v30[9] = (int)&v38;
          }
          v39 = (int)v8;
          if ( v21 < 0 )
            goto LABEL_91;
          VtidTableid = ErrSQLSetQoSql(a4, -1, *(_DWORD *)v40, v8, v38, 0, 0);
          if ( VtidTableid >= 0 )
          {
            if ( v8 )
            {
              _free(v8);
              v8 = 0;
            }
            goto LABEL_89;
          }
          goto LABEL_90;
        }
      }
      if ( a8 )
      {
        VtidTableid = JetGetTempQueryColumnInfo(sesid, v35, a3, 0, v53, 56, 2);
        if ( VtidTableid < 0 )
          goto LABEL_19;
      }
      v30[13] = 0;
      for ( v30[12] = 0x80000000; ; v30[12] = 1 )
      {
        v29 = ErrQodefMove(sesid, v34, v30[12], v30[13]);
        VtidTableid = v29;
        if ( v29 < 0 )
        {
          if ( v29 != -1603 )
            goto LABEL_19;
          if ( a8 && v53[2] )
          {
            qmemcpy(v30, v53, sizeof(v30));
            VtidTableid = ErrAddMoreOutputs(
                            (JET_SESID)a4,
                            v38,
                            v39,
                            v30[0],
                            v30[1],
                            v30[2],
                            v30[3],
                            v30[4],
                            v30[5],
                            v30[6],
                            v30[7],
                            v30[8],
                            v30[9],
                            v30[10],
                            v30[11],
                            v30[12],
                            v30[13]);
            if ( VtidTableid >= 0 )
            {
              ErrDispCloseTable(sesid, v53[1]);
              v53[1] = -1;
              goto LABEL_89;
            }
            goto LABEL_19;
          }
LABEL_89:
          VtidTableid = ErrQjetCommitTransaction(0);
          if ( VtidTableid < 0 )
          {
LABEL_90:
            if ( v8 )
LABEL_91:
              _free(v8);
            goto LABEL_19;
          }
          return 0;
        }
        VtidTableid = ErrQodefPrepareUpdate(a4, v32, 0);
        if ( VtidTableid < 0 )
          goto LABEL_19;
        VtidTableid = ErrQodefRetrieveColumn(sesid, v34, v43, (char *)&v31 + 3, 1, 0, 0, 0);
        if ( VtidTableid < 0 )
          goto LABEL_19;
        v36 = HIBYTE(v31) == 6;
        VtidTableid = ErrQodefSetColumn(a4, v32, v39, (char *)&v31 + 3, 1, 0, 0);
        if ( VtidTableid < 0 )
          goto LABEL_19;
        v22 = ErrQodefRetrieveColumn(sesid, v34, v44, v54, 510, &v35, 0, 0);
        VtidTableid = v22;
        if ( v22 < 0 )
          goto LABEL_19;
        if ( v22 != 1004 )
        {
          VtidTableid = ErrQodefSetColumn(a4, v32, v45, v54, v35, 0, 0);
          if ( VtidTableid < 0 )
            goto LABEL_19;
        }
        v23 = ErrQodefRetrieveColumn(sesid, v34, v46, v54, 510, &v35, 0, 0);
        VtidTableid = v23;
        if ( v23 < 0 )
          goto LABEL_19;
        if ( v23 != 1004 )
        {
          VtidTableid = ErrQodefSetColumn(a4, v32, v47, v54, v35, 0, 0);
          if ( VtidTableid < 0 )
            goto LABEL_19;
        }
        v24 = ErrQodefRetrieveColumn(sesid, v34, v41, v54, 510, &v35, 0, 0);
        VtidTableid = v24;
        if ( v24 < 0 )
          goto LABEL_19;
        if ( v24 == 1006 )
        {
          VtidTableid = ErrQodefGetLVBuf(v35 + 2);
          if ( VtidTableid < 0 )
            goto LABEL_19;
          v25 = ErrAssignLVCol(a4, v48, v35, a3, v41, a4, *(_DWORD *)v40, v38, 0);
        }
        else
        {
          if ( v24 == 1004 )
            goto LABEL_64;
          v25 = ErrQodefSetColumn(a4, v32, v38, v54, v35, 0, 0);
        }
        VtidTableid = v25;
        if ( v25 < 0 )
          goto LABEL_19;
LABEL_64:
        v26 = ErrQodefRetrieveColumn(sesid, v34, v49, &v37, 2, 0, 0, 0);
        VtidTableid = v26;
        if ( v26 < 0 )
          goto LABEL_19;
        if ( v26 != 1004 )
        {
          if ( HIBYTE(v31) == 3 && (v37 & 1) != 0 && a8 )
            LOWORD(v37) = v37 & 0xFFFE;
          VtidTableid = ErrQodefSetColumn(a4, v32, v50, &v37, 2, 0, 0);
          if ( VtidTableid < 0 )
            goto LABEL_19;
        }
        if ( v51 != -1 && v42 != -1 )
        {
          v27 = ErrQodefRetrieveColumn(sesid, v34, v51, &v52, 4, &v35, 0, 0);
          VtidTableid = v27;
          if ( v27 < 0 )
            goto LABEL_19;
          if ( v27 != 1004 )
          {
            VtidTableid = ErrQodefSetColumn(a4, v32, v42, &v52, v35, 0, 0);
            if ( VtidTableid < 0 )
              goto LABEL_19;
          }
        }
        if ( v36 && a8 )
        {
          v28 = JetMove(sesid, v53[1], 1, 0);
          VtidTableid = v28;
          if ( v28 != -1603 && v28 < 0 )
            goto LABEL_19;
          --v53[2];
        }
        VtidTableid = ErrQodefUpdate(a4, v32, 0, 0, 0);
        if ( VtidTableid < 0 )
          goto LABEL_19;
        v30[13] = 0;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1008bcaf  mov     edi, edi
0x1008bcb1  push    ebp
0x1008bcb2  mov     ebp, esp
0x1008bcb4  and     esp, 0FFFFFFF8h
0x1008bcb7  sub     esp, 29Ch
0x1008bcbd  mov     eax, ___security_cookie
0x1008bcc2  xor     eax, esp
0x1008bcc4  mov     [esp+29Ch+var_4], eax
0x1008bccb  mov     eax, [ebp+arg_C]
0x1008bcce  push    ebx
0x1008bccf  push    esi
0x1008bcd0  push    edi
0x1008bcd1  mov     edi, [ebp+arg_10]
0x1008bcd4  xor     ebx, ebx
0x1008bcd6  push    38h ; '8'; Size
0x1008bcd8  mov     [esp+2ACh+var_284], eax
0x1008bcdc  mov     esi, ecx
0x1008bcde  lea     eax, [esp+2ACh+var_240]
0x1008bce2  mov     [esp+2ACh+var_288], edx
0x1008bce6  push    ebx; Val
0x1008bce7  push    eax; void *
0x1008bce8  mov     [esp+2B4h+sesid], esi
0x1008bcec  mov     [esp+2B4h+var_274], edi
0x1008bcf0  call    _memset
0x1008bcf5  add     esp, 0Ch
0x1008bcf8  mov     dword ptr [edi], 0FFFFFFFFh
0x1008bcfe  mov     [esp+2A8h+tableid], 0FFFFFFFFh
0x1008bd06  push    esi
0x1008bd07  call    _FValidSesid@4; FValidSesid(x)
0x1008bd0c  test    eax, eax
0x1008bd0e  jz      loc_1008C3BF
0x1008bd14  mov     edi, [ebp+arg_4]
0x1008bd17  push    edi
0x1008bd18  call    _FValidSesid@4; FValidSesid(x)
0x1008bd1d  test    eax, eax
0x1008bd1f  jz      loc_1008C3BF
0x1008bd25  push    [ebp+arg_8]
0x1008bd28  push    esi
0x1008bd29  call    _FValidDbid@8; FValidDbid(x,x)
0x1008bd2e  test    eax, eax
0x1008bd30  jnz     short loc_1008BD42
0x1008bd32  cmp     [ebp+arg_8], 0FFFFFFFFh
0x1008bd36  jz      short loc_1008BD42
0x1008bd38  mov     eax, 0FFFFFC0Eh
0x1008bd3d  jmp     loc_1008C3C4
0x1008bd42  lea     eax, [esp+2A8h+var_278]
0x1008bd46  push    eax
0x1008bd47  push    [ebp+arg_0]
0x1008bd4a  push    esi
0x1008bd4b  call    _ErrGetPvtfndefTableid@12; ErrGetPvtfndefTableid(x,x,x)
0x1008bd50  test    eax, eax
0x1008bd52  js      loc_1008C3C4
0x1008bd58  cmp     [esp+2A8h+var_278], offset _vtfndefQodef
0x1008bd60  jz      short loc_1008BD6C
0x1008bd62  mov     eax, 0FFFFFAE0h
0x1008bd67  jmp     loc_1008C3C4
0x1008bd6c  xor     edx, edx
0x1008bd6e  mov     ecx, edi
0x1008bd70  call    _ErrQjetBeginTransaction@8; ErrQjetBeginTransaction(x,x)
0x1008bd75  test    eax, eax
0x1008bd77  js      loc_1008C3C4
0x1008bd7d  lea     eax, [esp+2A8h+var_28C]
0x1008bd81  push    eax
0x1008bd82  push    [ebp+arg_0]
0x1008bd85  push    esi
0x1008bd86  call    _ErrGetVtidTableid@12; ErrGetVtidTableid(x,x,x)
0x1008bd8b  mov     esi, eax
0x1008bd8d  test    esi, esi
0x1008bd8f  js      loc_1008BE5D
0x1008bd95  mov     eax, [esp+2A8h+var_28C]
0x1008bd99  push    0; int
0x1008bd9b  push    dword ptr [eax+5Ch]; int
0x1008bd9e  mov     ecx, [eax+20h]
0x1008bda1  push    [esp+2B0h+var_274]; int
0x1008bda5  mov     [esp+2B4h+var_268], ecx
0x1008bda9  mov     ecx, [eax+24h]
0x1008bdac  push    [esp+2B4h+var_284]; int
0x1008bdb0  mov     [esp+2B8h+var_264], ecx
0x1008bdb4  mov     ecx, [eax+28h]
0x1008bdb7  push    [ebp+arg_8]; int
0x1008bdba  mov     [esp+2BCh+var_25C], ecx
0x1008bdbe  mov     ecx, [eax+2Ch]
0x1008bdc1  mov     [esp+2BCh+var_270], ecx
0x1008bdc5  mov     ecx, [eax+30h]
0x1008bdc8  mov     [esp+2BCh+var_250], ecx
0x1008bdcc  mov     ecx, [eax+34h]
0x1008bdcf  push    edi; Session *
0x1008bdd0  mov     [esp+2C0h+var_248], ecx
0x1008bdd4  call    _ErrQodefSecCreateVtQoDef@24; ErrQodefSecCreateVtQoDef(x,x,x,x,x,x)
0x1008bdd9  mov     esi, eax
0x1008bddb  test    esi, esi
0x1008bddd  js      short loc_1008BE5D
0x1008bddf  lea     eax, [esp+2A8h+var_294]
0x1008bde3  push    eax
0x1008bde4  mov     eax, [esp+2ACh+var_274]
0x1008bde8  push    dword ptr [eax]
0x1008bdea  push    edi
0x1008bdeb  call    _ErrGetVtidTableid@12; ErrGetVtidTableid(x,x,x)
0x1008bdf0  mov     esi, eax
0x1008bdf2  test    esi, esi
0x1008bdf4  js      short loc_1008BE5D
0x1008bdf6  mov     eax, [esp+2A8h+var_294]
0x1008bdfa  mov     esi, [ebp+arg_8]
0x1008bdfd  mov     ecx, [eax+20h]
0x1008be00  mov     [esp+2A8h+var_278], ecx
0x1008be04  mov     ecx, [eax+24h]
0x1008be07  mov     [esp+2A8h+var_260], ecx
0x1008be0b  mov     ecx, [eax+28h]
0x1008be0e  mov     [esp+2A8h+var_258], ecx
0x1008be12  mov     ecx, [eax+2Ch]
0x1008be15  mov     [esp+2A8h+var_27C], ecx
0x1008be19  mov     ecx, [eax+30h]
0x1008be1c  mov     eax, [eax+34h]
0x1008be1f  mov     [esp+2A8h+var_24C], ecx
0x1008be23  mov     [esp+2A8h+var_26C], eax
0x1008be27  cmp     esi, 0FFFFFFFFh
0x1008be2a  jnz     short loc_1008BE4D
0x1008be2c  mov     eax, [esp+2A8h+var_284]
0x1008be30  test    eax, eax
0x1008be32  jz      loc_1008BEE9
0x1008be38  xor     ecx, ecx
0x1008be3a  cmp     [eax], cx
0x1008be3d  jz      loc_1008BEE9
0x1008be43  mov     eax, 0FFFFFC15h
0x1008be48  jmp     loc_1008C3C4
0x1008be4d  push    esi
0x1008be4e  push    edi
0x1008be4f  call    _FValidDbid@8; FValidDbid(x,x)
0x1008be54  test    eax, eax
0x1008be56  jnz     short loc_1008BE9C
0x1008be58  mov     esi, 0FFFFFC0Eh
0x1008be5d  mov     ebx, [esp+2A8h+var_274]
0x1008be61  or      edi, 0FFFFFFFFh
0x1008be64  cmp     [ebx], edi
0x1008be66  jz      short loc_1008BE74
0x1008be68  push    dword ptr [ebx]
0x1008be6a  push    [ebp+arg_4]
0x1008be6d  call    _ErrDispCloseTable@8; ErrDispCloseTable(x,x)
0x1008be72  mov     [ebx], edi
0x1008be74  cmp     [esp+2A8h+tableid], edi
0x1008be78  jz      short loc_1008BE8B
0x1008be7a  push    [esp+2A8h+tableid]
0x1008be7e  push    [esp+2ACh+sesid]
0x1008be82  call    _ErrDispCloseTable@8; ErrDispCloseTable(x,x)
0x1008be87  mov     [esp+2A8h+tableid], edi
0x1008be8b  mov     ecx, [ebp+arg_4]; Session *
0x1008be8e  push    0; int
0x1008be90  call    _ErrQjetRollback@12; ErrQjetRollback(x,x,x)
0x1008be95  mov     eax, esi
0x1008be97  jmp     loc_1008C3C4
0x1008be9c  mov     ecx, [esp+2A8h+sesid]
0x1008bea0  mov     edx, esi
0x1008bea2  call    _IsJetIsam@8; IsJetIsam(x,x)
0x1008bea7  test    eax, eax
0x1008bea9  jnz     short loc_1008BEB2
0x1008beab  mov     esi, 0FFFFFC17h
0x1008beb0  jmp     short loc_1008BE5D
0x1008beb2  push    8
0x1008beb4  push    4
0x1008beb6  lea     eax, [esp+2B0h+var_284]
0x1008beba  push    eax
0x1008bebb  push    esi
0x1008bebc  push    edi
0x1008bebd  call    _ErrDispGetDatabaseInfo@20; ErrDispGetDatabaseInfo(x,x,x,x,x)
0x1008bec2  mov     esi, eax
0x1008bec4  test    esi, esi
0x1008bec6  js      short loc_1008BE5D
0x1008bec8  cmp     [esp+2A8h+var_284], 10000h
0x1008bed0  jz      short loc_1008BEDC
0x1008bed2  cmp     [esp+2A8h+var_284], 10001h
0x1008beda  jnz     short loc_1008BEE9
0x1008bedc  mov     edx, [esp+2A8h+var_294]
0x1008bee0  mov     dword ptr [edx+64h], 1
0x1008bee7  jmp     short loc_1008BEED
0x1008bee9  mov     edx, [esp+2A8h+var_294]
0x1008beed  mov     ecx, [esp+2A8h+var_28C]
0x1008bef1  call    _ErrCopyQueryObjectProperties@8; ErrCopyQueryObjectProperties(x,x)
0x1008bef6  mov     esi, eax
0x1008bef8  cmp     esi, 0FFFFFA1Dh
0x1008befe  jz      loc_1008BFEA
0x1008bf04  test    esi, esi
0x1008bf06  js      loc_1008BE5D
0x1008bf0c  mov     eax, [esp+2A8h+var_28C]
0x1008bf10  cmp     [eax+70h], ebx
0x1008bf13  jz      loc_1008BFEA
0x1008bf19  mov     edi, 800h
0x1008bf1e  push    edi; Size
0x1008bf1f  call    ds:__imp__malloc
0x1008bf25  mov     ebx, eax
0x1008bf27  pop     ecx
0x1008bf28  test    ebx, ebx
0x1008bf2a  jnz     short loc_1008BF36
0x1008bf2c  mov     esi, 0FFFFFC0Dh
0x1008bf31  jmp     loc_1008BE5D
0x1008bf36  xor     eax, eax
0x1008bf38  push    eax
0x1008bf39  push    eax
0x1008bf3a  push    eax
0x1008bf3b  push    eax
0x1008bf3c  mov     [ebx], al
0x1008bf3e  lea     eax, [esp+2B8h+var_27C]
0x1008bf42  push    eax
0x1008bf43  push    400h
0x1008bf48  jmp     short loc_1008BF80
0x1008bf4a  push    ebx; Block
0x1008bf4b  call    ds:__imp__free
0x1008bf51  add     edi, edi
0x1008bf53  pop     ecx
0x1008bf54  cmp     edi, 10000h
0x1008bf5a  jnb     loc_1008BFE0
0x1008bf60  push    edi; Size
0x1008bf61  call    ds:__imp__malloc
0x1008bf67  mov     ebx, eax
0x1008bf69  pop     ecx
0x1008bf6a  test    ebx, ebx
0x1008bf6c  jz      short loc_1008BF2C
0x1008bf6e  xor     eax, eax
0x1008bf70  push    eax; int
0x1008bf71  push    eax; int
0x1008bf72  push    eax; int
0x1008bf73  push    eax; int
0x1008bf74  mov     [ebx], al
0x1008bf76  lea     eax, [esp+2B8h+var_27C]
0x1008bf7a  push    eax; int
0x1008bf7b  mov     eax, edi
0x1008bf7d  shr     eax, 1
0x1008bf7f  push    eax; int
0x1008bf80  push    ebx; Src
0x1008bf81  push    [ebp+arg_0]; int
0x1008bf84  push    [esp+2C8h+sesid]; int
0x1008bf88  call    _ErrSQLRetrieveQoSql@36; ErrSQLRetrieveQoSql(x,x,x,x,x,x,x,x,x)
0x1008bf8d  mov     esi, eax
0x1008bf8f  cmp     esi, 0FFFFF245h
0x1008bf95  jz      short loc_1008BF4A
0x1008bf97  mov     [esp+2A8h+var_278], ebx
0x1008bf9b  test    esi, esi
0x1008bf9d  js      loc_1008C3AE
0x1008bfa3  mov     edi, [ebp+arg_4]
0x1008bfa6  xor     eax, eax
0x1008bfa8  push    eax
0x1008bfa9  push    eax
0x1008bfaa  push    [esp+2B0h+var_27C]
0x1008bfae  mov     eax, [esp+2B4h+var_274]
0x1008bfb2  push    ebx
0x1008bfb3  push    dword ptr [eax]
0x1008bfb5  push    0FFFFFFFFh
0x1008bfb7  push    edi
0x1008bfb8  call    _ErrSQLSetQoSql@28; ErrSQLSetQoSql(x,x,x,x,x,x,x)
0x1008bfbd  mov     esi, eax
0x1008bfbf  test    esi, esi
0x1008bfc1  js      loc_1008C3A6
0x1008bfc7  mov     eax, ebx
0x1008bfc9  test    eax, eax
0x1008bfcb  jz      loc_1008C394
0x1008bfd1  push    eax; Block
0x1008bfd2  call    ds:__imp__free
0x1008bfd8  pop     ecx
0x1008bfd9  xor     ebx, ebx
0x1008bfdb  jmp     loc_1008C394
0x1008bfe0  mov     esi, 0FFFFF401h
0x1008bfe5  jmp     loc_1008BE5D
0x1008bfea  cmp     [ebp+arg_14], ebx
0x1008bfed  jz      short loc_1008C014
0x1008bfef  push    2
0x1008bff1  push    38h ; '8'
0x1008bff3  lea     eax, [esp+2B0h+var_240]
0x1008bff7  push    eax
0x1008bff8  push    0
0x1008bffa  push    [ebp+arg_0]
0x1008bffd  push    [esp+2BCh+var_288]
0x1008c001  push    [esp+2C0h+sesid]
0x1008c005  call    _JetGetTempQueryColumnInfo@28; JetGetTempQueryColumnInfo(x,x,x,x,x,x,x)
0x1008c00a  mov     esi, eax
0x1008c00c  test    esi, esi
0x1008c00e  js      loc_1008BE5D
0x1008c014  push    0
0x1008c016  push    80000000h
0x1008c01b  jmp     loc_1008C323
0x1008c020  xor     ecx, ecx
0x1008c022  push    ecx
0x1008c023  push    [esp+2ACh+var_294]
0x1008c027  push    edi
0x1008c028  call    _ErrQodefPrepareUpdate@12; ErrQodefPrepareUpdate(x,x,x)
0x1008c02d  mov     esi, eax
0x1008c02f  test    esi, esi
0x1008c031  js      loc_1008BE5D
0x1008c037  xor     eax, eax
0x1008c039  push    eax
0x1008c03a  push    eax
0x1008c03b  push    eax
0x1008c03c  push    1
0x1008c03e  lea     eax, [esp+2B8h+var_298+3]
0x1008c042  push    eax
0x1008c043  push    [esp+2BCh+var_268]
0x1008c047  push    [esp+2C0h+var_28C]
0x1008c04b  push    [esp+2C4h+sesid]
0x1008c04f  call    _ErrQodefRetrieveColumn@32; ErrQodefRetrieveColumn(x,x,x,x,x,x,x,x)
0x1008c054  mov     esi, eax
0x1008c056  test    esi, esi
0x1008c058  js      loc_1008BE5D
  ... truncated ...
```
