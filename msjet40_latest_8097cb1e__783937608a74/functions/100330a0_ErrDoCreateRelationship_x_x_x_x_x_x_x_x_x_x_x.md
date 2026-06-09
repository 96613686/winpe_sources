# ErrDoCreateRelationship(x,x,x,x,x,x,x,x,x,x,x)

- ea: `0x100330a0`
- end: `0x10033b9f`
- name: `_ErrDoCreateRelationship@44`
- size: `2815`
- prototype: `int __stdcall(JET_SESID sesid, int, int, int, int, int, int, int, int, int, int)`
- caller_count: `3`
- callee_count: `22`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x10023540`
- `0x10032920`
- `0x100cfb84`

## callees

- `0x10014b30`
- `0x10014d20`
- `0x10014ea0`
- `0x10032d50`
- `0x100330a0`
- `0x10036310`
- `0x10036630`
- `0x1003a420`
- `0x1003a840`
- `0x1003ab40`
- `0x1003ea00`
- `0x10042d20`
- `0x10043060`
- `0x10043220`
- `0x100433f0`
- `0x100439d0`
- `0x10043cd0`
- `0x10050190`
- `0x100b16d5`
- `0x1011b700`
- `0x1011b740`
- `0x10123110`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x10033b18`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x10033b51`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x10033b18`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x10033b51`

## pseudocode

```c
JET_ERR __stdcall ErrDoCreateRelationship(
        Session *sesid,
        int a2,
        int a3,
        const unsigned __int16 *a4,
        void *a5,
        const unsigned __int16 *a6,
        void *a7,
        _WORD *a8,
        int a9,
        int a10,
        int a11)
{
  _WORD *v11; // ecx
  int v12; // edi
  void *v13; // eax
  JET_ERR result; // eax
  _WORD *v15; // edx
  const unsigned __int16 *v16; // esi
  const unsigned __int16 *v17; // ecx
  const unsigned __int16 *v19; // esi
  _WORD *v20; // ecx
  JET_ERR DatabaseInfo; // esi
  unsigned int v23; // eax
  int v24; // edi
  Session *v25; // ecx
  unsigned int v26; // kr00_4
  unsigned int v27; // eax
  Session *v28; // ecx
  Session *v29; // ecx
  Session *v30; // ecx
  Session *v31; // ecx
  unsigned int v32; // kr04_4
  Session *v33; // ecx
  unsigned int v34; // kr08_4
  Session *v35; // ecx
  unsigned int v36; // kr0C_4
  Session *v37; // ecx
  unsigned int v38; // kr10_4
  Session *v39; // ecx
  Session *v40; // ecx
  int v41; // esi
  int v42; // eax
  unsigned int v43; // edi
  int v44; // [esp+Ch] [ebp-F8h] BYREF
  int v45; // [esp+10h] [ebp-F4h] BYREF
  int v46; // [esp+14h] [ebp-F0h] BYREF
  int v47; // [esp+18h] [ebp-ECh]
  const unsigned __int16 *v48; // [esp+1Ch] [ebp-E8h]
  unsigned int v49; // [esp+20h] [ebp-E4h] BYREF
  char *v50; // [esp+24h] [ebp-E0h] BYREF
  void *Block; // [esp+28h] [ebp-DCh]
  unsigned __int16 *v52; // [esp+2Ch] [ebp-D8h]
  void *Src; // [esp+30h] [ebp-D4h]
  void *v54; // [esp+34h] [ebp-D0h]
  int v55; // [esp+38h] [ebp-CCh] BYREF
  const unsigned __int16 *v56; // [esp+3Ch] [ebp-C8h] BYREF
  unsigned int v57; // [esp+40h] [ebp-C4h] BYREF
  unsigned int v58; // [esp+44h] [ebp-C0h]
  char v59[4]; // [esp+48h] [ebp-BCh] BYREF
  unsigned int v60; // [esp+4Ch] [ebp-B8h]
  int v61; // [esp+54h] [ebp-B0h]
  int v62; // [esp+58h] [ebp-ACh]
  int v63; // [esp+5Ch] [ebp-A8h]
  int v64; // [esp+60h] [ebp-A4h]
  int v65; // [esp+64h] [ebp-A0h]
  int v66; // [esp+68h] [ebp-9Ch]
  int v67; // [esp+6Ch] [ebp-98h]
  int v68; // [esp+70h] [ebp-94h]
  unsigned __int16 v69[70]; // [esp+74h] [ebp-90h] BYREF

  v11 = a8;
  Src = a5;
  v12 = -1;
  v13 = a7;
  v52 = (unsigned __int16 *)a4;
  v48 = a6;
  v54 = a7;
  Block = a8;
  v55 = -1;
  v57 = (unsigned int)a8;
  v47 = 0;
  if ( !a6 || !*a6 )
    return -1003;
  if ( !a4 )
  {
    v52 = v69;
    if ( ErrUniqueName((int)a8, (int)L"Rel", v69, (int)a8, 1) < 0 )
      return -1002;
    v13 = v54;
    v11 = Block;
  }
  if ( !v11 || !*v11 )
  {
    result = ErrGetPrimaryKeyCols(v13, &v57);
    if ( result < 0 )
      return result;
    v11 = (_WORD *)v57;
    Block = (void *)v57;
    if ( !v57 || !*(_WORD *)v57 )
      return -1404;
    v47 = 1;
  }
  v15 = v11;
  v50 = 0;
  v16 = v48;
  if ( *v48 )
  {
    v57 = 0;
    while ( *v15 )
    {
      v17 = v16;
      v56 = v16 + 1;
      while ( *v17++ )
        ;
      v19 = &v16[v17 - v56];
      v20 = v15;
      v16 = v19 + 1;
      v56 = v15 + 1;
      while ( *v20++ )
        ;
      v50 = (char *)++v57;
      v15 += v20 - v56 + 1;
      if ( !*v16 )
        goto LABEL_23;
    }
  }
  if ( *v16 )
    goto LABEL_122;
LABEL_23:
  if ( *v15 )
  {
LABEL_122:
    DatabaseInfo = -1406;
    goto LABEL_123;
  }
  DatabaseInfo = ErrDispGetDatabaseInfo(sesid, a2, &v44, 4, 8);
  if ( DatabaseInfo < 0 )
    goto LABEL_123;
  if ( v44 == 0x10000 || v44 == 65537 )
  {
    DatabaseInfo = -1067;
    goto LABEL_123;
  }
  DatabaseInfo = ErrDispGetObjidFromName(sesid, a2, 0, L"Relationships", &v45);
  if ( DatabaseInfo < 0 || (DatabaseInfo = JetBeginTransaction((JET_SESID)sesid), DatabaseInfo < 0) )
  {
LABEL_123:
    if ( v47 )
      _free(Block);
    return DatabaseInfo;
  }
  DatabaseInfo = ErrOpenMSysRelationships(v59, 1);
  if ( DatabaseInfo < 0 )
    goto LABEL_88;
  v12 = v60;
  v58 = v60;
  DatabaseInfo = ErrDispCreateObject(sesid, a2, v45, v52, 8);
  if ( DatabaseInfo < 0 )
    goto LABEL_88;
  DatabaseInfo = ErrDispGetObjidFromName(sesid, a2, L"Relationships", v52, &v46);
  if ( DatabaseInfo < 0 )
    goto LABEL_88;
  if ( a11 )
  {
    DatabaseInfo = ErrSecSetOwner(sesid, a2, v46, 0, 0);
    if ( DatabaseInfo < 0 )
      goto LABEL_88;
    DatabaseInfo = ErrSecBestowAccess(sesid, a2, v45, a2, v46, 0, 0, 1, 1, 0, 0, 1);
    if ( DatabaseInfo < 0 )
      goto LABEL_88;
  }
  v56 = v48;
  v57 = (unsigned int)Block;
  v49 = 0;
  if ( v50 )
  {
    v23 = v12;
    v24 = 4 * v12;
    while ( v23 < 0x800 && v23 >= tableidInit )
    {
      _mm_lfence();
      v25 = sesid;
      if ( rgvtdef[v24] != -1 )
        v25 = (Session *)rgvtdef[v24];
      DatabaseInfo = (*(int (__thiscall **)(_DWORD, Session *, int, _DWORD))(dword_101636CC[v24] + 124))(
                       *(_DWORD *)(dword_101636CC[v24] + 124),
                       v25,
                       dword_101636C4[v24],
                       0);
      if ( DatabaseInfo < 0 )
        goto LABEL_87;
      v26 = wcslen(v52);
      v27 = v58;
      if ( v58 < tableidInit )
        goto LABEL_85;
      v28 = sesid;
      if ( rgvtdef[v24] != -1 )
        v28 = (Session *)rgvtdef[v24];
      DatabaseInfo = (*(int (__thiscall **)(_DWORD, Session *, int, int, unsigned __int16 *, unsigned int, _DWORD, _DWORD))(dword_101636CC[v24] + 156))(
                       *(_DWORD *)(dword_101636CC[v24] + 156),
                       v28,
                       dword_101636C4[v24],
                       v61,
                       v52,
                       2 * v26,
                       0,
                       0);
      if ( DatabaseInfo < 0 )
        goto LABEL_87;
      v27 = v58;
      if ( v58 < tableidInit )
        goto LABEL_85;
      v29 = sesid;
      if ( rgvtdef[v24] != -1 )
        v29 = (Session *)rgvtdef[v24];
      DatabaseInfo = (*(int (__thiscall **)(_DWORD, Session *, int, int, int *, int, _DWORD, _DWORD))(dword_101636CC[v24] + 156))(
                       *(_DWORD *)(dword_101636CC[v24] + 156),
                       v29,
                       dword_101636C4[v24],
                       v62,
                       &a9,
                       4,
                       0,
                       0);
      if ( DatabaseInfo < 0 )
        goto LABEL_87;
      v27 = v58;
      if ( v58 < tableidInit )
        goto LABEL_85;
      v30 = sesid;
      if ( rgvtdef[v24] != -1 )
        v30 = (Session *)rgvtdef[v24];
      DatabaseInfo = (*(int (__thiscall **)(_DWORD, Session *, int, int, char **, int, _DWORD, _DWORD))(dword_101636CC[v24] + 156))(
                       *(_DWORD *)(dword_101636CC[v24] + 156),
                       v30,
                       dword_101636C4[v24],
                       v63,
                       &v50,
                       4,
                       0,
                       0);
      if ( DatabaseInfo < 0 )
        goto LABEL_87;
      v27 = v58;
      if ( v58 < tableidInit )
        goto LABEL_85;
      v31 = sesid;
      if ( rgvtdef[v24] != -1 )
        v31 = (Session *)rgvtdef[v24];
      DatabaseInfo = (*(int (__thiscall **)(_DWORD, Session *, int, int, unsigned int *, int, _DWORD, _DWORD))(dword_101636CC[v24] + 156))(
                       *(_DWORD *)(dword_101636CC[v24] + 156),
                       v31,
                       dword_101636C4[v24],
                       v64,
                       &v49,
                       4,
                       0,
                       0);
      if ( DatabaseInfo < 0 )
        goto LABEL_87;
      v32 = wcslen((const unsigned __int16 *)Src);
      v27 = v58;
      if ( v58 < tableidInit )
        goto LABEL_85;
      v33 = sesid;
      if ( rgvtdef[v24] != -1 )
        v33 = (Session *)rgvtdef[v24];
      DatabaseInfo = (*(int (__thiscall **)(_DWORD, Session *, int, int, void *, unsigned int, _DWORD, _DWORD))(dword_101636CC[v24] + 156))(
                       *(_DWORD *)(dword_101636CC[v24] + 156),
                       v33,
                       dword_101636C4[v24],
                       v65,
                       Src,
                       2 * v32,
                       0,
                       0);
      if ( DatabaseInfo < 0 )
        goto LABEL_87;
      v34 = wcslen(v56);
      v27 = v58;
      if ( v58 < tableidInit )
        goto LABEL_85;
      v35 = sesid;
      if ( rgvtdef[v24] != -1 )
        v35 = (Session *)rgvtdef[v24];
      DatabaseInfo = (*(int (__thiscall **)(_DWORD, Session *, int, int, const unsigned __int16 *, unsigned int, _DWORD, _DWORD))(dword_101636CC[v24] + 156))(
                       *(_DWORD *)(dword_101636CC[v24] + 156),
                       v35,
                       dword_101636C4[v24],
                       v66,
                       v56,
                       2 * v34,
                       0,
                       0);
      if ( DatabaseInfo < 0 )
        goto LABEL_87;
      v36 = wcslen((const unsigned __int16 *)v54);
      v27 = v58;
      if ( v58 < tableidInit )
        goto LABEL_85;
      v37 = sesid;
      if ( rgvtdef[v24] != -1 )
        v37 = (Session *)rgvtdef[v24];
      DatabaseInfo = (*(int (__thiscall **)(_DWORD, Session *, int, int, void *, unsigned int, _DWORD, _DWORD))(dword_101636CC[v24] + 156))(
                       *(_DWORD *)(dword_101636CC[v24] + 156),
                       v37,
                       dword_101636C4[v24],
                       v67,
                       v54,
                       2 * v36,
                       0,
                       0);
      if ( DatabaseInfo < 0 )
        goto LABEL_87;
      v38 = wcslen((const unsigned __int16 *)v57);
      v27 = v58;
      if ( v58 < tableidInit )
        goto LABEL_85;
      v39 = sesid;
      if ( rgvtdef[v24] != -1 )
        v39 = (Session *)rgvtdef[v24];
      DatabaseInfo = (*(int (__thiscall **)(_DWORD, Session *, int, int, unsigned int, unsigned int, _DWORD, _DWORD))(dword_101636CC[v24] + 156))(
                       *(_DWORD *)(dword_101636CC[v24] + 156),
                       v39,
                       dword_101636C4[v24],
                       v68,
                       v57,
                       2 * v38,
                       0,
                       0);
      if ( DatabaseInfo < 0 )
        goto LABEL_87;
      v27 = v58;
      if ( v58 < tableidInit )
      {
LABEL_85:
        DatabaseInfo = -1310;
        v12 = v27;
        goto LABEL_88;
      }
      _mm_lfence();
      v40 = sesid;
      if ( rgvtdef[v24] != -1 )
        v40 = (Session *)rgvtdef[v24];
      DatabaseInfo = (*(int (__thiscall **)(_DWORD, Session *, int, _DWORD, _DWORD, _DWORD))(dword_101636CC[v24] + 164))(
                       *(_DWORD *)(dword_101636CC[v24] + 164),
                       v40,
                       dword_101636C4[v24],
                       0,
                       0,
                       0);
      if ( DatabaseInfo < 0 )
        goto LABEL_87;
      v56 += wcslen(v56) + 1;
      ++v49;
      v57 += 2 * wcslen((const unsigned __int16 *)v57) + 2;
      if ( v49 >= (unsigned int)v50 )
      {
        v12 = v58;
        goto LABEL_81;
      }
      v23 = v58;
    }
    DatabaseInfo = -1310;
    goto LABEL_87;
  }
LABEL_81:
  DatabaseInfo = ErrDispCloseTable(sesid, v12);
  if ( DatabaseInfo < 0 )
    goto LABEL_88;
  v12 = -1;
  v58 = -1;
  if ( (a9 & 2) != 0 )
    goto LABEL_117;
  if ( a3 == -1 )
  {
    v42 = ErrDispOpenTable(sesid, a2, &v55, Src, 2);
    DatabaseInfo = v42;
    if ( v42 >= 0 )
    {
      v41 = v55;
      goto LABEL_100;
    }
    if ( v42 == -1305 )
      UtilSetErrorInfoReal((int)sesid, Src, 0, 0, -8300, 0, 0, 0);
    else
      SetLockErrorInfo(Src);
    v55 = -1;
    ErrRollback(sesid, 0);
    goto LABEL_123;
  }
  v41 = a3;
  v55 = a3;
LABEL_100:
  if ( a10 )
  {
    DatabaseInfo = ErrDispGetObjidFromName(sesid, a2, L"Tables", Src, &v57);
    if ( DatabaseInfo < 0 )
      goto LABEL_88;
    DatabaseInfo = ErrSecGetAccess(sesid, a2, v57, 0, 0, 0, &v56, 0);
    if ( DatabaseInfo < 0 )
      goto LABEL_88;
    if ( ((unsigned __int8)v56 & 0xD0) == 0 || ((unsigned __int8)v56 & 8) == 0 )
    {
      DatabaseInfo = -1907;
      UtilSetErrorInfoReal((int)sesid, Src, 0, 0, -8170, 0, 0, 0);
      goto LABEL_88;
    }
    DatabaseInfo = ErrDispGetObjidFromName(sesid, a2, L"Tables", v54, &v57);
    if ( DatabaseInfo < 0 )
      goto LABEL_88;
    DatabaseInfo = ErrSecGetAccess(sesid, a2, v57, 0, 0, 0, &v56, 0);
    if ( DatabaseInfo < 0 )
      goto LABEL_88;
    if ( ((unsigned __int8)v56 & 0xD0) == 0 || ((unsigned __int8)v56 & 8) == 0 )
    {
      DatabaseInfo = -1907;
      UtilSetErrorInfoReal((int)sesid, v54, 0, 0, -8170, 0, 0, 0);
      goto LABEL_88;
    }
    v41 = v55;
  }
  a9 &= 0xFFFFF3u;
  ErrREPGetTabStatus(v41, &v57);
  v43 = v57;
  ErrREPSetTabStatus(v41, v57 | 0x10);
  DatabaseInfo = ErrDispCreateReference(sesid, v55, v52, v48, v54, Block, a9);
  ErrREPSetTabStatus(v55, v43);
  if ( DatabaseInfo < 0 )
  {
    if ( DatabaseInfo == -1305 )
      UtilSetErrorInfoReal((int)sesid, v54, 0, 0, -8300, 0, 0, 0);
    else
      SetLockErrorInfo(v54);
LABEL_87:
    v12 = v58;
    goto LABEL_88;
  }
  if ( v55 != a3 )
    ErrDispCloseTable(sesid, v55);
  v12 = v58;
  v55 = -1;
LABEL_117:
  DatabaseInfo = JetCommitTransaction((JET_SESID)sesid, 0);
  if ( DatabaseInfo < 0 )
  {
LABEL_88:
    if ( v55 != -1 && v55 != a3 )
      ErrDispCloseTable(sesid, v55);
    if ( v12 != -1 )
      ErrDispCloseTable(sesid, v12);
    ErrRollback(sesid, 0);
    goto LABEL_123;
  }
  if ( v47 )
    _free(Block);
  return 0;
}

```

## disassembly

```asm
0x100330a0  mov     edi, edi
0x100330a2  push    ebp
0x100330a3  mov     ebp, esp
0x100330a5  sub     esp, 0F8h
0x100330ab  mov     eax, ___security_cookie
0x100330b0  xor     eax, ebp
0x100330b2  mov     [ebp+var_4], eax
0x100330b5  mov     eax, [ebp+arg_10]
0x100330b8  mov     edx, [ebp+arg_14]
0x100330bb  mov     ecx, [ebp+arg_1C]
0x100330be  push    ebx
0x100330bf  push    esi
0x100330c0  mov     esi, [ebp+arg_C]
0x100330c3  push    edi
0x100330c4  mov     [ebp+Src], eax
0x100330ca  or      edi, 0FFFFFFFFh
0x100330cd  mov     eax, [ebp+arg_18]
0x100330d0  mov     [ebp+var_D8], esi
0x100330d6  mov     [ebp+var_E8], edx
0x100330dc  mov     [ebp+var_D0], eax
0x100330e2  mov     [ebp+Block], ecx
0x100330e8  mov     [ebp+var_CC], 0FFFFFFFFh
0x100330f2  mov     [ebp+var_C4], ecx
0x100330f8  mov     [ebp+var_EC], 0
0x10033102  test    edx, edx
0x10033104  jz      loc_10033B87
0x1003310a  cmp     word ptr [edx], 0
0x1003310e  jz      loc_10033B87
0x10033114  test    esi, esi
0x10033116  jnz     short loc_1003315A
0x10033118  push    1
0x1003311a  lea     eax, [ebp+var_90]
0x10033120  mov     edx, offset aRel; "Rel"
0x10033125  push    ecx
0x10033126  push    eax
0x10033127  mov     [ebp+var_D8], eax
0x1003312d  call    _ErrUniqueName@20; ErrUniqueName(x,x,x,x,x)
0x10033132  test    eax, eax
0x10033134  jns     short loc_1003314E
0x10033136  mov     eax, 0FFFFFC16h
0x1003313b  pop     edi
0x1003313c  pop     esi
0x1003313d  pop     ebx
0x1003313e  mov     ecx, [ebp+var_4]
0x10033141  xor     ecx, ebp; StackCookie
0x10033143  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10033148  mov     esp, ebp
0x1003314a  pop     ebp
0x1003314b  retn    2Ch ; ','
0x1003314e  mov     eax, [ebp+var_D0]
0x10033154  mov     ecx, [ebp+Block]
0x1003315a  mov     ebx, [ebp+sesid]
0x1003315d  test    ecx, ecx
0x1003315f  jz      short loc_10033167
0x10033161  cmp     word ptr [ecx], 0
0x10033165  jnz     short loc_100331A9
0x10033167  mov     edx, [ebp+arg_4]
0x1003316a  lea     ecx, [ebp+var_C4]
0x10033170  push    ecx
0x10033171  push    eax
0x10033172  mov     ecx, ebx
0x10033174  call    ErrGetPrimaryKeyCols
0x10033179  test    eax, eax
0x1003317b  js      loc_10033B8C
0x10033181  mov     ecx, [ebp+var_C4]
0x10033187  mov     [ebp+Block], ecx
0x1003318d  test    ecx, ecx
0x1003318f  jz      loc_10033B6F
0x10033195  cmp     word ptr [ecx], 0
0x10033199  jz      loc_10033B6F
0x1003319f  mov     [ebp+var_EC], 1
0x100331a9  mov     eax, [ebp+var_E8]
0x100331af  mov     edx, ecx
0x100331b1  mov     [ebp+var_E0], 0
0x100331bb  mov     esi, eax
0x100331bd  cmp     word ptr [eax], 0
0x100331c1  jz      short loc_10033239
0x100331c3  mov     [ebp+var_C4], 0
0x100331cd  nop     dword ptr [eax]
0x100331d0  cmp     word ptr [edx], 0
0x100331d4  jz      short loc_10033239
0x100331d6  mov     ecx, esi
0x100331d8  lea     eax, [ecx+2]
0x100331db  mov     [ebp+var_C8], eax
0x100331e1  mov     ax, [ecx]
0x100331e4  add     ecx, 2
0x100331e7  test    ax, ax
0x100331ea  jnz     short loc_100331E1
0x100331ec  sub     ecx, [ebp+var_C8]
0x100331f2  sar     ecx, 1
0x100331f4  lea     esi, [esi+ecx*2]
0x100331f7  mov     ecx, edx
0x100331f9  add     esi, 2
0x100331fc  lea     eax, [ecx+2]
0x100331ff  mov     [ebp+var_C8], eax
0x10033205  mov     ax, [ecx]
0x10033208  add     ecx, 2
0x1003320b  test    ax, ax
0x1003320e  jnz     short loc_10033205
0x10033210  sub     ecx, [ebp+var_C8]
0x10033216  mov     eax, [ebp+var_C4]
0x1003321c  sar     ecx, 1
0x1003321e  inc     eax
0x1003321f  mov     [ebp+var_E0], eax
0x10033225  mov     [ebp+var_C4], eax
0x1003322b  lea     edx, [edx+ecx*2]
0x1003322e  add     edx, 2
0x10033231  cmp     word ptr [esi], 0
0x10033235  jnz     short loc_100331D0
0x10033237  jmp     short loc_10033243
0x10033239  cmp     word ptr [esi], 0
0x1003323d  jnz     loc_10033B3D
0x10033243  cmp     word ptr [edx], 0
0x10033247  jnz     loc_10033B3D
0x1003324d  push    8
0x1003324f  push    4
0x10033251  lea     eax, [ebp+var_F8]
0x10033257  push    eax
0x10033258  push    [ebp+arg_4]
0x1003325b  push    ebx
0x1003325c  call    _ErrDispGetDatabaseInfo@20; ErrDispGetDatabaseInfo(x,x,x,x,x)
0x10033261  mov     esi, eax
0x10033263  test    esi, esi
0x10033265  js      loc_10033B42
0x1003326b  mov     eax, [ebp+var_F8]
0x10033271  cmp     eax, 10000h
0x10033276  jz      loc_10033B36
0x1003327c  cmp     eax, 10001h
0x10033281  jz      loc_10033B36
0x10033287  lea     eax, [ebp+var_F4]
0x1003328d  push    eax
0x1003328e  push    offset _wszRcObject; "Relationships"
0x10033293  push    0
0x10033295  push    [ebp+arg_4]
0x10033298  push    ebx
0x10033299  call    _ErrDispGetObjidFromName@20; ErrDispGetObjidFromName(x,x,x,x,x)
0x1003329e  mov     esi, eax
0x100332a0  test    esi, esi
0x100332a2  js      loc_10033B42
0x100332a8  push    ebx; sesid
0x100332a9  call    _JetBeginTransaction@4; JetBeginTransaction(x)
0x100332ae  mov     esi, eax
0x100332b0  test    esi, esi
0x100332b2  js      loc_10033B42
0x100332b8  mov     edx, [ebp+arg_4]
0x100332bb  lea     eax, [ebp+var_BC]
0x100332c1  push    1
0x100332c3  push    eax
0x100332c4  mov     ecx, ebx
0x100332c6  call    ErrOpenMSysRelationships
0x100332cb  mov     esi, eax
0x100332cd  test    esi, esi
0x100332cf  js      loc_10033863
0x100332d5  mov     edi, [ebp+var_B8]
0x100332db  push    8
0x100332dd  push    [ebp+var_D8]
0x100332e3  mov     [ebp+var_C0], edi
0x100332e9  push    [ebp+var_F4]
0x100332ef  push    [ebp+arg_4]
0x100332f2  push    ebx
0x100332f3  call    _ErrDispCreateObject@20; ErrDispCreateObject(x,x,x,x,x)
0x100332f8  mov     esi, eax
0x100332fa  test    esi, esi
0x100332fc  js      loc_10033863
0x10033302  lea     eax, [ebp+var_F0]
0x10033308  push    eax
0x10033309  push    [ebp+var_D8]
0x1003330f  push    offset _wszRcObject; "Relationships"
0x10033314  push    [ebp+arg_4]
0x10033317  push    ebx
0x10033318  call    _ErrDispGetObjidFromName@20; ErrDispGetObjidFromName(x,x,x,x,x)
0x1003331d  mov     esi, eax
0x1003331f  test    esi, esi
0x10033321  js      loc_10033863
0x10033327  cmp     [ebp+arg_28], 0
0x1003332b  jz      short loc_10033379
0x1003332d  push    0
0x1003332f  push    0
0x10033331  push    [ebp+var_F0]
0x10033337  push    [ebp+arg_4]
0x1003333a  push    ebx
0x1003333b  call    _ErrSecSetOwner@20; ErrSecSetOwner(x,x,x,x,x)
0x10033340  mov     esi, eax
0x10033342  test    esi, esi
0x10033344  js      loc_10033863
0x1003334a  mov     eax, [ebp+arg_4]
0x1003334d  push    1
0x1003334f  push    0
0x10033351  push    0
0x10033353  push    1
0x10033355  push    1
0x10033357  push    0
0x10033359  push    0
0x1003335b  push    [ebp+var_F0]
0x10033361  push    eax
0x10033362  push    [ebp+var_F4]
0x10033368  push    eax
0x10033369  push    ebx
0x1003336a  call    _ErrSecBestowAccess@48; ErrSecBestowAccess(x,x,x,x,x,x,x,x,x,x,x,x)
0x1003336f  mov     esi, eax
0x10033371  test    esi, esi
0x10033373  js      loc_10033863
0x10033379  cmp     [ebp+var_E0], 0
0x10033380  mov     eax, [ebp+var_E8]
0x10033386  mov     [ebp+var_C8], eax
0x1003338c  mov     eax, [ebp+Block]
0x10033392  mov     [ebp+var_C4], eax
0x10033398  mov     [ebp+var_E4], 0
0x100333a2  jbe     loc_1003381A
0x100333a8  mov     eax, edi
0x100333aa  shl     edi, 4
0x100333ad  jmp     short loc_100333B6
0x100333b0  mov     eax, [ebp+var_C0]
0x100333b6  cmp     eax, 800h
0x100333bb  jnb     loc_10033858
0x100333c1  cmp     eax, _tableidInit
0x100333c7  jb      loc_10033858
0x100333cd  lfence
0x100333d0  mov     eax, _rgvtdef[edi]
0x100333d6  mov     ecx, ebx
0x100333d8  cmp     eax, 0FFFFFFFFh
0x100333db  push    0
0x100333dd  push    dword_101636C4[edi]; unsigned int
0x100333e3  cmovnz  ecx, eax
0x100333e6  mov     eax, dword_101636CC[edi]
0x100333ec  push    ecx; void *
0x100333ed  mov     esi, [eax+7Ch]
0x100333f0  mov     ecx, esi
0x100333f2  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100333f8  call    esi
0x100333fa  mov     esi, eax
0x100333fc  test    esi, esi
0x100333fe  js      loc_1003385D
0x10033404  mov     ecx, [ebp+var_D8]
0x1003340a  lea     edx, [ecx+2]
0x1003340d  nop     dword ptr [eax]
0x10033410  mov     ax, [ecx]
0x10033413  add     ecx, 2
0x10033416  test    ax, ax
0x10033419  jnz     short loc_10033410
0x1003341b  mov     eax, [ebp+var_C0]
0x10033421  sub     ecx, edx
0x10033423  sar     ecx, 1
0x10033425  lea     edx, [ecx+ecx]
0x10033428  cmp     eax, _tableidInit
0x1003342e  jb      loc_1003384F
0x10033434  mov     eax, _rgvtdef[edi]
0x1003343a  mov     ecx, ebx
0x1003343c  mov     esi, dword_101636CC[edi]
0x10033442  cmp     eax, 0FFFFFFFFh
0x10033445  push    0
0x10033447  push    0
0x10033449  push    edx
0x1003344a  push    [ebp+var_D8]
0x10033450  mov     esi, [esi+9Ch]
0x10033456  cmovnz  ecx, eax
0x10033459  push    [ebp+var_B0]
0x1003345f  push    dword_101636C4[edi]; unsigned int
0x10033465  push    ecx; void *
0x10033466  mov     ecx, esi
0x10033468  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1003346e  call    esi
0x10033470  mov     esi, eax
0x10033472  test    esi, esi
0x10033474  js      loc_1003385D
0x1003347a  mov     eax, [ebp+var_C0]
0x10033480  cmp     eax, _tableidInit
0x10033486  jb      loc_1003384F
0x1003348c  mov     eax, _rgvtdef[edi]
0x10033492  mov     ecx, ebx
0x10033494  mov     esi, dword_101636CC[edi]
0x1003349a  cmp     eax, 0FFFFFFFFh
0x1003349d  push    0
0x1003349f  push    0
0x100334a1  cmovnz  ecx, eax
0x100334a4  lea     eax, [ebp+arg_20]
0x100334a7  mov     esi, [esi+9Ch]
0x100334ad  push    4
0x100334af  push    eax
0x100334b0  push    [ebp+var_AC]
0x100334b6  push    dword_101636C4[edi]; unsigned int
0x100334bc  push    ecx; void *
0x100334bd  mov     ecx, esi
0x100334bf  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100334c5  call    esi
0x100334c7  mov     esi, eax
0x100334c9  test    esi, esi
0x100334cb  js      loc_1003385D
0x100334d1  mov     eax, [ebp+var_C0]
0x100334d7  cmp     eax, _tableidInit
0x100334dd  jb      loc_1003384F
0x100334e3  mov     eax, _rgvtdef[edi]
0x100334e9  mov     ecx, ebx
0x100334eb  mov     esi, dword_101636CC[edi]
0x100334f1  cmp     eax, 0FFFFFFFFh
0x100334f4  push    0
0x100334f6  push    0
0x100334f8  cmovnz  ecx, eax
0x100334fb  lea     eax, [ebp+var_E0]
0x10033501  mov     esi, [esi+9Ch]
  ... truncated ...
```
