# ErrRmtOpenPassThrough(x,x,x,x,x,x,x,x,x,x,x,x,x)

- ea: `0x1009c421`
- end: `0x1009c7b0`
- name: `_ErrRmtOpenPassThrough@52`
- size: `911`
- prototype: ``
- caller_count: `2`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x100155a0`
- `0x100b2399`

## callees

- `0x1003e830`
- `0x10045280`
- `0x100454a0`
- `0x10050190`
- `0x10096b5f`
- `0x10096ead`
- `0x10097fca`
- `0x1009c421`
- `0x1009c7b6`
- `0x1009c808`
- `0x1009c85a`
- `0x1009c9ac`
- `0x1009ca86`
- `0x1009cdcb`
- `0x1009cf38`
- `0x1009dc7a`
- `0x1009e303`
- `0x100a4694`
- `0x100a656f`
- `0x100a65ec`
- `0x100a667d`
- `0x100a6a0c`
- `0x10123110`
- `0x10123b3c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1009c691`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1009c691`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1009c493`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1009c4e4`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1009c51a`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1009c569`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1009c72a`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1009c75a`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1009c493`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1009c4e4`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1009c51a`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1009c569`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1009c72a`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1009c75a`

## pseudocode

```c
int __fastcall ErrRmtOpenPassThrough(
        int a1,
        _DWORD *a2,
        int a3,
        int a4,
        int a5,
        _DWORD *a6,
        _DWORD *a7,
        int a8,
        int a9,
        _DWORD *a10,
        int a11,
        unsigned int a12,
        int a13)
{
  int v13; // edi
  _DWORD **v14; // eax
  _DWORD **v15; // ebx
  _DWORD *v17; // eax
  int Tableid; // esi
  _DWORD *v19; // eax
  _DWORD *v20; // eax
  int v21; // eax
  _DWORD *v22; // eax
  unsigned int v23; // edx
  int v24; // eax
  _DWORD *v25; // eax
  _WORD *v26; // eax
  void (__thiscall *v29)(_DWORD, int, int, int, _DWORD *); // [esp+24h] [ebp-28h]
  unsigned int v30; // [esp+28h] [ebp-24h] BYREF
  _DWORD v31[6]; // [esp+2Ch] [ebp-20h] BYREF

  v13 = a1;
  v30 = a12;
  if ( a5 && a6 && (a3 == -1 || !a4 && !a10) )
  {
    *a6 = -1;
    v14 = (_DWORD **)_malloc(0x98u);
    v15 = v14;
    if ( !v14 )
      return -1011;
    memset(v14, 0, 0x98u);
    *v15 = 0;
    v15[1] = 0;
    v15[25] = a2;
    v15[3] = (_DWORD *)-1;
    v15[26] = (_DWORD *)-1;
    v15[24] = (_DWORD *)-1;
    v15[9] = (_DWORD *)-1;
    v15[30] = (_DWORD *)-1;
    v15[28] = a7;
    v17 = _malloc(0x120u);
    v15[23] = v17;
    if ( !v17 )
      goto LABEL_9;
    v17[1] &= ~0x1000u;
    v15[23][67] = a8;
    v19 = _malloc(4u);
    v15[2] = v19;
    if ( !v19 )
      goto LABEL_9;
    Tableid = ErrSPTGetHdbc(v13, a4, (int)v15);
    if ( Tableid < 0 )
      goto LABEL_10;
    if ( a10 )
    {
      Tableid = ErrSPTGetDest(*a10);
      if ( Tableid < 0 )
        goto LABEL_10;
    }
    if ( !*v15 )
      goto LABEL_9;
    GetHdbcConfigOptions(a11, v30);
    v20 = _malloc(4u);
    v15[1] = v20;
    if ( !v20 )
      goto LABEL_9;
    *v20 = 0;
    Tableid = ErrSQLAllocStmt(v13, **v15, v15[1], 1, a8);
    if ( Tableid < 0 )
      goto LABEL_10;
    if ( a9 )
      RmtSetStmtOption((void *)*v15[1], 1u, a9);
    v21 = ErrSQLExecDirect(v15[23], v13, **v15, *v15[1], a5);
    Tableid = v21;
    if ( v21 < 0 )
    {
      Tableid = ErrRestoreGenericError(v13, v21);
      if ( Tableid < 0 )
        goto LABEL_10;
    }
    SPTLog(v13);
    if ( !a4 )
    {
      v29 = (void (__thiscall *)(_DWORD, int, int, int, _DWORD *))dword_1016EB48[26 * (__int16)UtilGetIsibOfSesid(v13)];
      if ( v29 )
      {
        v22 = v15[1];
        v30 = 0;
        pfnSQLRowCount(pfnSQLRowCount, *v22, &v30);
        Tableid = ErrSQLCheckError(0, a1);
        if ( Tableid >= 0 )
        {
          v23 = v30;
        }
        else
        {
          v23 = 0;
          v30 = 0;
        }
        memset(v31, 0, sizeof(v31));
        v13 = a1;
        v31[0] = 24;
        v31[4] = v23;
        v29(v29, a1, 8, 8, v31);
      }
    }
    if ( a10 )
    {
      Tableid = ErrSPTDoMultiResult(v13);
      goto LABEL_30;
    }
    RegisterHdbcHstmt(1);
    if ( a13 )
    {
      Tableid = ErrSPTBuildColInfo(v13);
      if ( Tableid < 0 )
        goto LABEL_10;
    }
    else
    {
      *((_WORD *)v15 + 10) = 0;
    }
    RmtStartIdle(**v15);
    if ( !*((_WORD *)v15 + 10) )
    {
      if ( FMoreResSupp(v13, **v15) )
      {
        while ( Tableid >= 0 )
        {
          Tableid = ErrSQLMoreResults(**v15, (void *)*v15[1]);
          SPTLog(v13);
        }
        v24 = 0;
        if ( Tableid != -1603 )
          v24 = Tableid;
        Tableid = v24;
      }
      goto LABEL_10;
    }
    v25 = _malloc(4u);
    v15[37] = v25;
    if ( !v25 )
      goto LABEL_9;
    *v25 = 0;
    Tableid = ErrSPTOpenResultTT(v13);
    if ( Tableid < 0 )
      goto LABEL_10;
    v26 = _malloc(2u);
    v15[22] = v26;
    if ( v26 )
    {
      *v26 = 0;
      Tableid = ErrAllocateTableid(0);
      if ( Tableid >= 0 )
      {
        ErrUpdateTableid(*a6, v15, &vtfndefRmtPass);
        return 0;
      }
    }
    else
    {
LABEL_9:
      Tableid = -1011;
    }
LABEL_10:
    SPTCloseDown(v13, v15);
LABEL_30:
    _free(v15);
    return Tableid;
  }
  return -1003;
}

```

## disassembly

```asm
0x1009c421  mov     edi, edi
0x1009c423  push    ebp
0x1009c424  mov     ebp, esp
0x1009c426  sub     esp, 40h
0x1009c429  mov     eax, ___security_cookie
0x1009c42e  xor     eax, ebp
0x1009c430  mov     [ebp+var_8], eax
0x1009c433  mov     eax, [ebp+arg_C]
0x1009c436  push    ebx
0x1009c437  mov     ebx, [ebp+arg_20]
0x1009c43a  push    esi
0x1009c43b  mov     esi, [ebp+arg_4]
0x1009c43e  push    edi
0x1009c43f  mov     [ebp+var_28], edx
0x1009c442  mov     edi, ecx
0x1009c444  mov     edx, [ebp+arg_8]
0x1009c447  mov     ecx, [ebp+arg_1C]
0x1009c44a  mov     [ebp+var_38], ebx
0x1009c44d  mov     ebx, [ebp+arg_24]
0x1009c450  mov     [ebp+var_2C], edi
0x1009c453  mov     [ebp+var_40], esi
0x1009c456  mov     [ebp+var_3C], edx
0x1009c459  mov     [ebp+var_34], eax
0x1009c45c  mov     [ebp+var_30], ecx
0x1009c45f  mov     [ebp+var_24], ebx
0x1009c462  test    edx, edx
0x1009c464  jz      loc_1009C79A
0x1009c46a  test    eax, eax
0x1009c46c  jz      loc_1009C79A
0x1009c472  cmp     [ebp+arg_0], 0FFFFFFFFh
0x1009c476  jz      short loc_1009C488
0x1009c478  test    esi, esi
0x1009c47a  jnz     loc_1009C79A
0x1009c480  test    ecx, ecx
0x1009c482  jnz     loc_1009C79A
0x1009c488  push    98h; Size
0x1009c48d  mov     dword ptr [eax], 0FFFFFFFFh
0x1009c493  call    ds:__imp__malloc
0x1009c499  mov     ebx, eax
0x1009c49b  pop     ecx
0x1009c49c  test    ebx, ebx
0x1009c49e  jnz     short loc_1009C4AA
0x1009c4a0  mov     eax, 0FFFFFC0Dh
0x1009c4a5  jmp     loc_1009C79F
0x1009c4aa  push    98h; Size
0x1009c4af  push    0; Val
0x1009c4b1  push    ebx; void *
0x1009c4b2  call    _memset
0x1009c4b7  xor     eax, eax
0x1009c4b9  or      ecx, 0FFFFFFFFh
0x1009c4bc  add     esp, 0Ch
0x1009c4bf  mov     [ebx], eax
0x1009c4c1  mov     [ebx+4], eax
0x1009c4c4  mov     eax, [ebp+var_28]
0x1009c4c7  mov     [ebx+64h], eax
0x1009c4ca  mov     eax, [ebp+arg_10]
0x1009c4cd  push    120h; Size
0x1009c4d2  mov     [ebx+0Ch], ecx
0x1009c4d5  mov     [ebx+68h], ecx
0x1009c4d8  mov     [ebx+60h], ecx
0x1009c4db  mov     [ebx+24h], ecx
0x1009c4de  mov     [ebx+78h], ecx
0x1009c4e1  mov     [ebx+70h], eax
0x1009c4e4  call    ds:__imp__malloc
0x1009c4ea  mov     [ebx+5Ch], eax
0x1009c4ed  pop     ecx
0x1009c4ee  test    eax, eax
0x1009c4f0  jnz     short loc_1009C505
0x1009c4f2  mov     esi, 0FFFFFC0Dh
0x1009c4f7  mov     edx, ebx
0x1009c4f9  mov     ecx, edi
0x1009c4fb  call    SPTCloseDown
0x1009c500  jmp     loc_1009C690
0x1009c505  and     dword ptr [eax+4], 0FFFFEFFFh
0x1009c50c  mov     eax, [ebx+5Ch]
0x1009c50f  mov     ecx, [ebp+arg_14]
0x1009c512  push    4; Size
0x1009c514  mov     [eax+10Ch], ecx
0x1009c51a  call    ds:__imp__malloc
0x1009c520  mov     [ebx+8], eax
0x1009c523  pop     ecx
0x1009c524  test    eax, eax
0x1009c526  jz      short loc_1009C4F2
0x1009c528  mov     edx, [ebp+arg_0]
0x1009c52b  mov     ecx, edi; int
0x1009c52d  push    ebx; int
0x1009c52e  push    esi; int
0x1009c52f  call    ErrSPTGetHdbc
0x1009c534  mov     esi, eax
0x1009c536  test    esi, esi
0x1009c538  js      short loc_1009C4F7
0x1009c53a  mov     eax, [ebp+var_30]
0x1009c53d  test    eax, eax
0x1009c53f  jz      short loc_1009C552
0x1009c541  push    dword ptr [eax]
0x1009c543  mov     edx, ebx
0x1009c545  mov     ecx, edi
0x1009c547  call    ErrSPTGetDest
0x1009c54c  mov     esi, eax
0x1009c54e  test    esi, esi
0x1009c550  js      short loc_1009C4F7
0x1009c552  mov     ecx, [ebx]
0x1009c554  test    ecx, ecx
0x1009c556  jz      short loc_1009C4F2
0x1009c558  push    [ebp+var_24]
0x1009c55b  mov     ecx, [ecx]
0x1009c55d  xor     edx, edx
0x1009c55f  push    [ebp+var_38]
0x1009c562  call    _GetHdbcConfigOptions@16; GetHdbcConfigOptions(x,x,x,x)
0x1009c567  push    4; Size
0x1009c569  call    ds:__imp__malloc
0x1009c56f  mov     [ebx+4], eax
0x1009c572  pop     ecx
0x1009c573  test    eax, eax
0x1009c575  jz      loc_1009C4F2
0x1009c57b  push    [ebp+arg_14]
0x1009c57e  mov     dword ptr [eax], 0
0x1009c584  mov     ecx, edi
0x1009c586  mov     edx, [ebx]
0x1009c588  push    1
0x1009c58a  push    dword ptr [ebx+4]
0x1009c58d  mov     edx, [edx]
0x1009c58f  call    _ErrSQLAllocStmt@20; ErrSQLAllocStmt(x,x,x,x,x)
0x1009c594  mov     esi, eax
0x1009c596  test    esi, esi
0x1009c598  js      loc_1009C4F7
0x1009c59e  cmp     [ebp+arg_18], 0
0x1009c5a2  jz      short loc_1009C5B9
0x1009c5a4  push    [ebp+arg_18]; int
0x1009c5a7  mov     eax, [ebx+4]
0x1009c5aa  mov     ecx, edi
0x1009c5ac  mov     edx, [ebx]
0x1009c5ae  push    1; unsigned int
0x1009c5b0  push    dword ptr [eax]; void *
0x1009c5b2  mov     edx, [edx]
0x1009c5b4  call    _RmtSetStmtOption@20; RmtSetStmtOption(x,x,x,x,x)
0x1009c5b9  mov     eax, [ebx+4]
0x1009c5bc  mov     edx, edi
0x1009c5be  push    [ebp+var_3C]
0x1009c5c1  mov     ecx, [ebx+5Ch]
0x1009c5c4  push    dword ptr [eax]
0x1009c5c6  mov     eax, [ebx]
0x1009c5c8  push    dword ptr [eax]
0x1009c5ca  call    _ErrSQLExecDirect@20; ErrSQLExecDirect(x,x,x,x,x)
0x1009c5cf  mov     esi, eax
0x1009c5d1  test    esi, esi
0x1009c5d3  jns     short loc_1009C5E8
0x1009c5d5  mov     edx, esi
0x1009c5d7  mov     ecx, edi
0x1009c5d9  call    ErrRestoreGenericError
0x1009c5de  mov     esi, eax
0x1009c5e0  test    esi, esi
0x1009c5e2  js      loc_1009C4F7
0x1009c5e8  mov     edx, ebx
0x1009c5ea  mov     ecx, edi; int
0x1009c5ec  call    SPTLog
0x1009c5f1  cmp     [ebp+var_40], 0
0x1009c5f5  jnz     loc_1009C67F
0x1009c5fb  mov     ecx, edi
0x1009c5fd  call    _UtilGetIsibOfSesid@4; UtilGetIsibOfSesid(x)
0x1009c602  cwde
0x1009c603  imul    eax, 68h ; 'h'
0x1009c606  mov     eax, dword_1016EB48[eax]
0x1009c60c  mov     [ebp+var_28], eax
0x1009c60f  test    eax, eax
0x1009c611  jz      short loc_1009C67F
0x1009c613  mov     eax, [ebx+4]
0x1009c616  xor     edx, edx
0x1009c618  push    [ebp+var_2C]
0x1009c61b  mov     esi, _pfnSQLRowCount
0x1009c621  mov     [ebp+var_24], edx
0x1009c624  mov     ecx, [eax]
0x1009c626  mov     eax, [ebx]
0x1009c628  push    edx
0x1009c629  mov     edi, [eax]
0x1009c62b  lea     eax, [ebp+var_24]
0x1009c62e  push    eax; unsigned int
0x1009c62f  push    ecx; void *
0x1009c630  mov     ecx, esi
0x1009c632  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1009c638  call    esi ; _pfnSQLRowCount
0x1009c63a  mov     edx, edi
0x1009c63c  mov     ecx, eax
0x1009c63e  call    _ErrSQLCheckError@16; ErrSQLCheckError(x,x,x,x)
0x1009c643  mov     esi, eax
0x1009c645  test    esi, esi
0x1009c647  jns     short loc_1009C650
0x1009c649  xor     edx, edx
0x1009c64b  mov     [ebp+var_24], edx
0x1009c64e  jmp     short loc_1009C653
0x1009c650  mov     edx, [ebp+var_24]
0x1009c653  push    6
0x1009c655  pop     ecx
0x1009c656  xor     eax, eax
0x1009c658  lea     edi, [ebp+var_20]
0x1009c65b  rep stosd
0x1009c65d  mov     edi, [ebp+var_2C]
0x1009c660  lea     eax, [ebp+var_20]
0x1009c663  mov     ecx, [ebp+var_28]
0x1009c666  push    eax
0x1009c667  push    8
0x1009c669  push    8; unsigned int
0x1009c66b  push    edi; void *
0x1009c66c  mov     [ebp+var_20], 18h
0x1009c673  mov     [ebp+var_10], edx
0x1009c676  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1009c67c  call    [ebp+var_28]
0x1009c67f  cmp     [ebp+var_30], 0
0x1009c683  jz      short loc_1009C69F
0x1009c685  mov     edx, ebx
0x1009c687  mov     ecx, edi; int
0x1009c689  call    ErrSPTDoMultiResult
0x1009c68e  mov     esi, eax
0x1009c690  push    ebx; Block
0x1009c691  call    ds:__imp__free
0x1009c697  pop     ecx
0x1009c698  mov     eax, esi
0x1009c69a  jmp     loc_1009C79F
0x1009c69f  mov     ecx, [ebx]
0x1009c6a1  mov     edx, [ebx+4]
0x1009c6a4  push    1
0x1009c6a6  mov     ecx, [ecx]
0x1009c6a8  call    _RegisterHdbcHstmt@12; RegisterHdbcHstmt(x,x,x)
0x1009c6ad  cmp     [ebp+arg_28], 0
0x1009c6b1  jz      short loc_1009C6C8
0x1009c6b3  mov     edx, ebx
0x1009c6b5  mov     ecx, edi
0x1009c6b7  call    ErrSPTBuildColInfo
0x1009c6bc  mov     esi, eax
0x1009c6be  test    esi, esi
0x1009c6c0  js      loc_1009C4F7
0x1009c6c6  jmp     short loc_1009C6CE
0x1009c6c8  xor     eax, eax
0x1009c6ca  mov     [ebx+14h], ax
0x1009c6ce  mov     ecx, [ebx]
0x1009c6d0  mov     ecx, [ecx]
0x1009c6d2  call    _RmtStartIdle@4; RmtStartIdle(x)
0x1009c6d7  xor     eax, eax
0x1009c6d9  cmp     [ebx+14h], ax
0x1009c6dd  jnz     short loc_1009C728
0x1009c6df  mov     edx, [ebx]
0x1009c6e1  mov     ecx, edi
0x1009c6e3  mov     edx, [edx]
0x1009c6e5  call    FMoreResSupp
0x1009c6ea  test    eax, eax
0x1009c6ec  jz      loc_1009C4F7
0x1009c6f2  jmp     short loc_1009C712
0x1009c6f4  mov     eax, [ebx+4]
0x1009c6f7  mov     edx, edi
0x1009c6f9  mov     ecx, [ebx+5Ch]
0x1009c6fc  push    dword ptr [eax]; void *
0x1009c6fe  mov     eax, [ebx]
0x1009c700  push    dword ptr [eax]; int
0x1009c702  call    _ErrSQLMoreResults@16; ErrSQLMoreResults(x,x,x,x)
0x1009c707  mov     edx, ebx
0x1009c709  mov     ecx, edi; int
0x1009c70b  mov     esi, eax
0x1009c70d  call    SPTLog
0x1009c712  test    esi, esi
0x1009c714  jns     short loc_1009C6F4
0x1009c716  xor     eax, eax
0x1009c718  cmp     esi, 0FFFFF9BDh
0x1009c71e  cmovnz  eax, esi
0x1009c721  mov     esi, eax
0x1009c723  jmp     loc_1009C4F7
0x1009c728  push    4; Size
0x1009c72a  call    ds:__imp__malloc
0x1009c730  mov     [ebx+94h], eax
0x1009c736  pop     ecx
0x1009c737  test    eax, eax
0x1009c739  jz      loc_1009C4F2
0x1009c73f  mov     edx, ebx
0x1009c741  mov     dword ptr [eax], 0
0x1009c747  mov     ecx, edi; int
0x1009c749  call    ErrSPTOpenResultTT
0x1009c74e  mov     esi, eax
0x1009c750  test    esi, esi
0x1009c752  js      loc_1009C4F7
0x1009c758  push    2; Size
0x1009c75a  call    ds:__imp__malloc
0x1009c760  mov     [ebx+58h], eax
0x1009c763  pop     ecx
0x1009c764  test    eax, eax
0x1009c766  jz      loc_1009C4F2
0x1009c76c  xor     ecx, ecx
0x1009c76e  xor     edx, edx
0x1009c770  mov     [eax], cx
0x1009c773  push    ecx
0x1009c774  mov     ecx, [ebp+var_34]
0x1009c777  call    _ErrAllocateTableid@12; ErrAllocateTableid(x,x,x)
0x1009c77c  mov     esi, eax
0x1009c77e  test    esi, esi
0x1009c780  js      loc_1009C4F7
0x1009c786  mov     eax, [ebp+var_34]
0x1009c789  push    offset _vtfndefRmtPass
0x1009c78e  push    ebx
0x1009c78f  push    dword ptr [eax]
0x1009c791  call    _ErrUpdateTableid@12; ErrUpdateTableid(x,x,x)
0x1009c796  xor     eax, eax
0x1009c798  jmp     short loc_1009C79F
  ... truncated ...
```
