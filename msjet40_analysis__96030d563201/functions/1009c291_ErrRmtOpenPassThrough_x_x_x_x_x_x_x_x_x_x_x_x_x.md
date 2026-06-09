# ErrRmtOpenPassThrough(x,x,x,x,x,x,x,x,x,x,x,x,x)

- ea: `0x1009c291`
- end: `0x1009c620`
- name: `_ErrRmtOpenPassThrough@52`
- size: `911`
- prototype: ``
- caller_count: `2`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x10015460`
- `0x100b220a`

## callees

- `0x1003e6a0`
- `0x10045100`
- `0x10045320`
- `0x10050000`
- `0x100969cf`
- `0x10096d1d`
- `0x10097e3a`
- `0x1009c291`
- `0x1009c626`
- `0x1009c678`
- `0x1009c6ca`
- `0x1009c81c`
- `0x1009c8f6`
- `0x1009cc3b`
- `0x1009cda8`
- `0x1009daea`
- `0x1009e173`
- `0x100a4504`
- `0x100a63df`
- `0x100a645c`
- `0x100a64ed`
- `0x100a687c`
- `0x10122f60`
- `0x1012398c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1009c501`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1009c501`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1009c303`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1009c354`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1009c38a`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1009c3d9`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1009c59a`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1009c5ca`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1009c303`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1009c354`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1009c38a`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1009c3d9`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1009c59a`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1009c5ca`

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
      v29 = (void (__thiscall *)(_DWORD, int, int, int, _DWORD *))dword_1016EAA8[26 * (__int16)UtilGetIsibOfSesid(v13)];
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
0x1009c291  mov     edi, edi
0x1009c293  push    ebp
0x1009c294  mov     ebp, esp
0x1009c296  sub     esp, 40h
0x1009c299  mov     eax, ___security_cookie
0x1009c29e  xor     eax, ebp
0x1009c2a0  mov     [ebp+var_8], eax
0x1009c2a3  mov     eax, [ebp+arg_C]
0x1009c2a6  push    ebx
0x1009c2a7  mov     ebx, [ebp+arg_20]
0x1009c2aa  push    esi
0x1009c2ab  mov     esi, [ebp+arg_4]
0x1009c2ae  push    edi
0x1009c2af  mov     [ebp+var_28], edx
0x1009c2b2  mov     edi, ecx
0x1009c2b4  mov     edx, [ebp+arg_8]
0x1009c2b7  mov     ecx, [ebp+arg_1C]
0x1009c2ba  mov     [ebp+var_38], ebx
0x1009c2bd  mov     ebx, [ebp+arg_24]
0x1009c2c0  mov     [ebp+var_2C], edi
0x1009c2c3  mov     [ebp+var_40], esi
0x1009c2c6  mov     [ebp+var_3C], edx
0x1009c2c9  mov     [ebp+var_34], eax
0x1009c2cc  mov     [ebp+var_30], ecx
0x1009c2cf  mov     [ebp+var_24], ebx
0x1009c2d2  test    edx, edx
0x1009c2d4  jz      loc_1009C60A
0x1009c2da  test    eax, eax
0x1009c2dc  jz      loc_1009C60A
0x1009c2e2  cmp     [ebp+arg_0], 0FFFFFFFFh
0x1009c2e6  jz      short loc_1009C2F8
0x1009c2e8  test    esi, esi
0x1009c2ea  jnz     loc_1009C60A
0x1009c2f0  test    ecx, ecx
0x1009c2f2  jnz     loc_1009C60A
0x1009c2f8  push    98h; Size
0x1009c2fd  mov     dword ptr [eax], 0FFFFFFFFh
0x1009c303  call    ds:__imp__malloc
0x1009c309  mov     ebx, eax
0x1009c30b  pop     ecx
0x1009c30c  test    ebx, ebx
0x1009c30e  jnz     short loc_1009C31A
0x1009c310  mov     eax, 0FFFFFC0Dh
0x1009c315  jmp     loc_1009C60F
0x1009c31a  push    98h; Size
0x1009c31f  push    0; Val
0x1009c321  push    ebx; void *
0x1009c322  call    _memset
0x1009c327  xor     eax, eax
0x1009c329  or      ecx, 0FFFFFFFFh
0x1009c32c  add     esp, 0Ch
0x1009c32f  mov     [ebx], eax
0x1009c331  mov     [ebx+4], eax
0x1009c334  mov     eax, [ebp+var_28]
0x1009c337  mov     [ebx+64h], eax
0x1009c33a  mov     eax, [ebp+arg_10]
0x1009c33d  push    120h; Size
0x1009c342  mov     [ebx+0Ch], ecx
0x1009c345  mov     [ebx+68h], ecx
0x1009c348  mov     [ebx+60h], ecx
0x1009c34b  mov     [ebx+24h], ecx
0x1009c34e  mov     [ebx+78h], ecx
0x1009c351  mov     [ebx+70h], eax
0x1009c354  call    ds:__imp__malloc
0x1009c35a  mov     [ebx+5Ch], eax
0x1009c35d  pop     ecx
0x1009c35e  test    eax, eax
0x1009c360  jnz     short loc_1009C375
0x1009c362  mov     esi, 0FFFFFC0Dh
0x1009c367  mov     edx, ebx
0x1009c369  mov     ecx, edi
0x1009c36b  call    SPTCloseDown
0x1009c370  jmp     loc_1009C500
0x1009c375  and     dword ptr [eax+4], 0FFFFEFFFh
0x1009c37c  mov     eax, [ebx+5Ch]
0x1009c37f  mov     ecx, [ebp+arg_14]
0x1009c382  push    4; Size
0x1009c384  mov     [eax+10Ch], ecx
0x1009c38a  call    ds:__imp__malloc
0x1009c390  mov     [ebx+8], eax
0x1009c393  pop     ecx
0x1009c394  test    eax, eax
0x1009c396  jz      short loc_1009C362
0x1009c398  mov     edx, [ebp+arg_0]
0x1009c39b  mov     ecx, edi; int
0x1009c39d  push    ebx; int
0x1009c39e  push    esi; int
0x1009c39f  call    ErrSPTGetHdbc
0x1009c3a4  mov     esi, eax
0x1009c3a6  test    esi, esi
0x1009c3a8  js      short loc_1009C367
0x1009c3aa  mov     eax, [ebp+var_30]
0x1009c3ad  test    eax, eax
0x1009c3af  jz      short loc_1009C3C2
0x1009c3b1  push    dword ptr [eax]
0x1009c3b3  mov     edx, ebx
0x1009c3b5  mov     ecx, edi
0x1009c3b7  call    ErrSPTGetDest
0x1009c3bc  mov     esi, eax
0x1009c3be  test    esi, esi
0x1009c3c0  js      short loc_1009C367
0x1009c3c2  mov     ecx, [ebx]
0x1009c3c4  test    ecx, ecx
0x1009c3c6  jz      short loc_1009C362
0x1009c3c8  push    [ebp+var_24]
0x1009c3cb  mov     ecx, [ecx]
0x1009c3cd  xor     edx, edx
0x1009c3cf  push    [ebp+var_38]
0x1009c3d2  call    _GetHdbcConfigOptions@16; GetHdbcConfigOptions(x,x,x,x)
0x1009c3d7  push    4; Size
0x1009c3d9  call    ds:__imp__malloc
0x1009c3df  mov     [ebx+4], eax
0x1009c3e2  pop     ecx
0x1009c3e3  test    eax, eax
0x1009c3e5  jz      loc_1009C362
0x1009c3eb  push    [ebp+arg_14]
0x1009c3ee  mov     dword ptr [eax], 0
0x1009c3f4  mov     ecx, edi
0x1009c3f6  mov     edx, [ebx]
0x1009c3f8  push    1
0x1009c3fa  push    dword ptr [ebx+4]
0x1009c3fd  mov     edx, [edx]
0x1009c3ff  call    _ErrSQLAllocStmt@20; ErrSQLAllocStmt(x,x,x,x,x)
0x1009c404  mov     esi, eax
0x1009c406  test    esi, esi
0x1009c408  js      loc_1009C367
0x1009c40e  cmp     [ebp+arg_18], 0
0x1009c412  jz      short loc_1009C429
0x1009c414  push    [ebp+arg_18]; int
0x1009c417  mov     eax, [ebx+4]
0x1009c41a  mov     ecx, edi
0x1009c41c  mov     edx, [ebx]
0x1009c41e  push    1; unsigned int
0x1009c420  push    dword ptr [eax]; void *
0x1009c422  mov     edx, [edx]
0x1009c424  call    _RmtSetStmtOption@20; RmtSetStmtOption(x,x,x,x,x)
0x1009c429  mov     eax, [ebx+4]
0x1009c42c  mov     edx, edi
0x1009c42e  push    [ebp+var_3C]
0x1009c431  mov     ecx, [ebx+5Ch]
0x1009c434  push    dword ptr [eax]
0x1009c436  mov     eax, [ebx]
0x1009c438  push    dword ptr [eax]
0x1009c43a  call    _ErrSQLExecDirect@20; ErrSQLExecDirect(x,x,x,x,x)
0x1009c43f  mov     esi, eax
0x1009c441  test    esi, esi
0x1009c443  jns     short loc_1009C458
0x1009c445  mov     edx, esi
0x1009c447  mov     ecx, edi
0x1009c449  call    ErrRestoreGenericError
0x1009c44e  mov     esi, eax
0x1009c450  test    esi, esi
0x1009c452  js      loc_1009C367
0x1009c458  mov     edx, ebx
0x1009c45a  mov     ecx, edi; int
0x1009c45c  call    SPTLog
0x1009c461  cmp     [ebp+var_40], 0
0x1009c465  jnz     loc_1009C4EF
0x1009c46b  mov     ecx, edi
0x1009c46d  call    _UtilGetIsibOfSesid@4; UtilGetIsibOfSesid(x)
0x1009c472  cwde
0x1009c473  imul    eax, 68h ; 'h'
0x1009c476  mov     eax, dword_1016EAA8[eax]
0x1009c47c  mov     [ebp+var_28], eax
0x1009c47f  test    eax, eax
0x1009c481  jz      short loc_1009C4EF
0x1009c483  mov     eax, [ebx+4]
0x1009c486  xor     edx, edx
0x1009c488  push    [ebp+var_2C]
0x1009c48b  mov     esi, _pfnSQLRowCount
0x1009c491  mov     [ebp+var_24], edx
0x1009c494  mov     ecx, [eax]
0x1009c496  mov     eax, [ebx]
0x1009c498  push    edx
0x1009c499  mov     edi, [eax]
0x1009c49b  lea     eax, [ebp+var_24]
0x1009c49e  push    eax; unsigned int
0x1009c49f  push    ecx; void *
0x1009c4a0  mov     ecx, esi
0x1009c4a2  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1009c4a8  call    esi ; _pfnSQLRowCount
0x1009c4aa  mov     edx, edi
0x1009c4ac  mov     ecx, eax
0x1009c4ae  call    _ErrSQLCheckError@16; ErrSQLCheckError(x,x,x,x)
0x1009c4b3  mov     esi, eax
0x1009c4b5  test    esi, esi
0x1009c4b7  jns     short loc_1009C4C0
0x1009c4b9  xor     edx, edx
0x1009c4bb  mov     [ebp+var_24], edx
0x1009c4be  jmp     short loc_1009C4C3
0x1009c4c0  mov     edx, [ebp+var_24]
0x1009c4c3  push    6
0x1009c4c5  pop     ecx
0x1009c4c6  xor     eax, eax
0x1009c4c8  lea     edi, [ebp+var_20]
0x1009c4cb  rep stosd
0x1009c4cd  mov     edi, [ebp+var_2C]
0x1009c4d0  lea     eax, [ebp+var_20]
0x1009c4d3  mov     ecx, [ebp+var_28]
0x1009c4d6  push    eax
0x1009c4d7  push    8
0x1009c4d9  push    8; unsigned int
0x1009c4db  push    edi; void *
0x1009c4dc  mov     [ebp+var_20], 18h
0x1009c4e3  mov     [ebp+var_10], edx
0x1009c4e6  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1009c4ec  call    [ebp+var_28]
0x1009c4ef  cmp     [ebp+var_30], 0
0x1009c4f3  jz      short loc_1009C50F
0x1009c4f5  mov     edx, ebx
0x1009c4f7  mov     ecx, edi; int
0x1009c4f9  call    ErrSPTDoMultiResult
0x1009c4fe  mov     esi, eax
0x1009c500  push    ebx; Block
0x1009c501  call    ds:__imp__free
0x1009c507  pop     ecx
0x1009c508  mov     eax, esi
0x1009c50a  jmp     loc_1009C60F
0x1009c50f  mov     ecx, [ebx]
0x1009c511  mov     edx, [ebx+4]
0x1009c514  push    1
0x1009c516  mov     ecx, [ecx]
0x1009c518  call    _RegisterHdbcHstmt@12; RegisterHdbcHstmt(x,x,x)
0x1009c51d  cmp     [ebp+arg_28], 0
0x1009c521  jz      short loc_1009C538
0x1009c523  mov     edx, ebx
0x1009c525  mov     ecx, edi
0x1009c527  call    ErrSPTBuildColInfo
0x1009c52c  mov     esi, eax
0x1009c52e  test    esi, esi
0x1009c530  js      loc_1009C367
0x1009c536  jmp     short loc_1009C53E
0x1009c538  xor     eax, eax
0x1009c53a  mov     [ebx+14h], ax
0x1009c53e  mov     ecx, [ebx]
0x1009c540  mov     ecx, [ecx]
0x1009c542  call    _RmtStartIdle@4; RmtStartIdle(x)
0x1009c547  xor     eax, eax
0x1009c549  cmp     [ebx+14h], ax
0x1009c54d  jnz     short loc_1009C598
0x1009c54f  mov     edx, [ebx]
0x1009c551  mov     ecx, edi
0x1009c553  mov     edx, [edx]
0x1009c555  call    FMoreResSupp
0x1009c55a  test    eax, eax
0x1009c55c  jz      loc_1009C367
0x1009c562  jmp     short loc_1009C582
0x1009c564  mov     eax, [ebx+4]
0x1009c567  mov     edx, edi
0x1009c569  mov     ecx, [ebx+5Ch]
0x1009c56c  push    dword ptr [eax]; void *
0x1009c56e  mov     eax, [ebx]
0x1009c570  push    dword ptr [eax]; int
0x1009c572  call    _ErrSQLMoreResults@16; ErrSQLMoreResults(x,x,x,x)
0x1009c577  mov     edx, ebx
0x1009c579  mov     ecx, edi; int
0x1009c57b  mov     esi, eax
0x1009c57d  call    SPTLog
0x1009c582  test    esi, esi
0x1009c584  jns     short loc_1009C564
0x1009c586  xor     eax, eax
0x1009c588  cmp     esi, 0FFFFF9BDh
0x1009c58e  cmovnz  eax, esi
0x1009c591  mov     esi, eax
0x1009c593  jmp     loc_1009C367
0x1009c598  push    4; Size
0x1009c59a  call    ds:__imp__malloc
0x1009c5a0  mov     [ebx+94h], eax
0x1009c5a6  pop     ecx
0x1009c5a7  test    eax, eax
0x1009c5a9  jz      loc_1009C362
0x1009c5af  mov     edx, ebx
0x1009c5b1  mov     dword ptr [eax], 0
0x1009c5b7  mov     ecx, edi; int
0x1009c5b9  call    ErrSPTOpenResultTT
0x1009c5be  mov     esi, eax
0x1009c5c0  test    esi, esi
0x1009c5c2  js      loc_1009C367
0x1009c5c8  push    2; Size
0x1009c5ca  call    ds:__imp__malloc
0x1009c5d0  mov     [ebx+58h], eax
0x1009c5d3  pop     ecx
0x1009c5d4  test    eax, eax
0x1009c5d6  jz      loc_1009C362
0x1009c5dc  xor     ecx, ecx
0x1009c5de  xor     edx, edx
0x1009c5e0  mov     [eax], cx
0x1009c5e3  push    ecx
0x1009c5e4  mov     ecx, [ebp+var_34]
0x1009c5e7  call    _ErrAllocateTableid@12; ErrAllocateTableid(x,x,x)
0x1009c5ec  mov     esi, eax
0x1009c5ee  test    esi, esi
0x1009c5f0  js      loc_1009C367
0x1009c5f6  mov     eax, [ebp+var_34]
0x1009c5f9  push    offset _vtfndefRmtPass
0x1009c5fe  push    ebx
0x1009c5ff  push    dword ptr [eax]
0x1009c601  call    _ErrUpdateTableid@12; ErrUpdateTableid(x,x,x)
0x1009c606  xor     eax, eax
0x1009c608  jmp     short loc_1009C60F
  ... truncated ...
```
