# ErrDoCreateRelationship(x,x,x,x,x,x,x,x,x,x,x)

- ea: `0x10032f00`
- end: `0x100339ff`
- name: `_ErrDoCreateRelationship@44`
- size: `2815`
- prototype: `int __stdcall(JET_SESID sesid, int, int, int, int, int, int, int, int, int, int)`
- caller_count: `3`
- callee_count: `22`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x100233e0`
- `0x10032780`
- `0x100cf9f4`

## callees

- `0x100149f0`
- `0x10014be0`
- `0x10014d60`
- `0x10032bb0`
- `0x10032f00`
- `0x10036180`
- `0x100364a0`
- `0x1003a2a0`
- `0x1003a6c0`
- `0x1003a9c0`
- `0x1003e870`
- `0x10042b90`
- `0x10042ed0`
- `0x10043090`
- `0x10043260`
- `0x10043840`
- `0x10043b40`
- `0x10050000`
- `0x100b1546`
- `0x1011b550`
- `0x1011b590`
- `0x10122f60`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x10033978`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x100339b1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x10033978`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x100339b1`

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
      DatabaseInfo = (*(int (__thiscall **)(_DWORD, Session *, int, _DWORD))(dword_1016362C[v24] + 124))(
                       *(_DWORD *)(dword_1016362C[v24] + 124),
                       v25,
                       dword_10163624[v24],
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
      DatabaseInfo = (*(int (__thiscall **)(_DWORD, Session *, int, int, unsigned __int16 *, unsigned int, _DWORD, _DWORD))(dword_1016362C[v24] + 156))(
                       *(_DWORD *)(dword_1016362C[v24] + 156),
                       v28,
                       dword_10163624[v24],
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
      DatabaseInfo = (*(int (__thiscall **)(_DWORD, Session *, int, int, int *, int, _DWORD, _DWORD))(dword_1016362C[v24] + 156))(
                       *(_DWORD *)(dword_1016362C[v24] + 156),
                       v29,
                       dword_10163624[v24],
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
      DatabaseInfo = (*(int (__thiscall **)(_DWORD, Session *, int, int, char **, int, _DWORD, _DWORD))(dword_1016362C[v24] + 156))(
                       *(_DWORD *)(dword_1016362C[v24] + 156),
                       v30,
                       dword_10163624[v24],
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
      DatabaseInfo = (*(int (__thiscall **)(_DWORD, Session *, int, int, unsigned int *, int, _DWORD, _DWORD))(dword_1016362C[v24] + 156))(
                       *(_DWORD *)(dword_1016362C[v24] + 156),
                       v31,
                       dword_10163624[v24],
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
      DatabaseInfo = (*(int (__thiscall **)(_DWORD, Session *, int, int, void *, unsigned int, _DWORD, _DWORD))(dword_1016362C[v24] + 156))(
                       *(_DWORD *)(dword_1016362C[v24] + 156),
                       v33,
                       dword_10163624[v24],
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
      DatabaseInfo = (*(int (__thiscall **)(_DWORD, Session *, int, int, const unsigned __int16 *, unsigned int, _DWORD, _DWORD))(dword_1016362C[v24] + 156))(
                       *(_DWORD *)(dword_1016362C[v24] + 156),
                       v35,
                       dword_10163624[v24],
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
      DatabaseInfo = (*(int (__thiscall **)(_DWORD, Session *, int, int, void *, unsigned int, _DWORD, _DWORD))(dword_1016362C[v24] + 156))(
                       *(_DWORD *)(dword_1016362C[v24] + 156),
                       v37,
                       dword_10163624[v24],
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
      DatabaseInfo = (*(int (__thiscall **)(_DWORD, Session *, int, int, unsigned int, unsigned int, _DWORD, _DWORD))(dword_1016362C[v24] + 156))(
                       *(_DWORD *)(dword_1016362C[v24] + 156),
                       v39,
                       dword_10163624[v24],
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
      DatabaseInfo = (*(int (__thiscall **)(_DWORD, Session *, int, _DWORD, _DWORD, _DWORD))(dword_1016362C[v24] + 164))(
                       *(_DWORD *)(dword_1016362C[v24] + 164),
                       v40,
                       dword_10163624[v24],
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
0x10032f00  mov     edi, edi
0x10032f02  push    ebp
0x10032f03  mov     ebp, esp
0x10032f05  sub     esp, 0F8h
0x10032f0b  mov     eax, ___security_cookie
0x10032f10  xor     eax, ebp
0x10032f12  mov     [ebp+var_4], eax
0x10032f15  mov     eax, [ebp+arg_10]
0x10032f18  mov     edx, [ebp+arg_14]
0x10032f1b  mov     ecx, [ebp+arg_1C]
0x10032f1e  push    ebx
0x10032f1f  push    esi
0x10032f20  mov     esi, [ebp+arg_C]
0x10032f23  push    edi
0x10032f24  mov     [ebp+Src], eax
0x10032f2a  or      edi, 0FFFFFFFFh
0x10032f2d  mov     eax, [ebp+arg_18]
0x10032f30  mov     [ebp+var_D8], esi
0x10032f36  mov     [ebp+var_E8], edx
0x10032f3c  mov     [ebp+var_D0], eax
0x10032f42  mov     [ebp+Block], ecx
0x10032f48  mov     [ebp+var_CC], 0FFFFFFFFh
0x10032f52  mov     [ebp+var_C4], ecx
0x10032f58  mov     [ebp+var_EC], 0
0x10032f62  test    edx, edx
0x10032f64  jz      loc_100339E7
0x10032f6a  cmp     word ptr [edx], 0
0x10032f6e  jz      loc_100339E7
0x10032f74  test    esi, esi
0x10032f76  jnz     short loc_10032FBA
0x10032f78  push    1
0x10032f7a  lea     eax, [ebp+var_90]
0x10032f80  mov     edx, offset aRel; "Rel"
0x10032f85  push    ecx
0x10032f86  push    eax
0x10032f87  mov     [ebp+var_D8], eax
0x10032f8d  call    _ErrUniqueName@20; ErrUniqueName(x,x,x,x,x)
0x10032f92  test    eax, eax
0x10032f94  jns     short loc_10032FAE
0x10032f96  mov     eax, 0FFFFFC16h
0x10032f9b  pop     edi
0x10032f9c  pop     esi
0x10032f9d  pop     ebx
0x10032f9e  mov     ecx, [ebp+var_4]
0x10032fa1  xor     ecx, ebp; StackCookie
0x10032fa3  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10032fa8  mov     esp, ebp
0x10032faa  pop     ebp
0x10032fab  retn    2Ch ; ','
0x10032fae  mov     eax, [ebp+var_D0]
0x10032fb4  mov     ecx, [ebp+Block]
0x10032fba  mov     ebx, [ebp+sesid]
0x10032fbd  test    ecx, ecx
0x10032fbf  jz      short loc_10032FC7
0x10032fc1  cmp     word ptr [ecx], 0
0x10032fc5  jnz     short loc_10033009
0x10032fc7  mov     edx, [ebp+arg_4]
0x10032fca  lea     ecx, [ebp+var_C4]
0x10032fd0  push    ecx
0x10032fd1  push    eax
0x10032fd2  mov     ecx, ebx
0x10032fd4  call    ErrGetPrimaryKeyCols
0x10032fd9  test    eax, eax
0x10032fdb  js      loc_100339EC
0x10032fe1  mov     ecx, [ebp+var_C4]
0x10032fe7  mov     [ebp+Block], ecx
0x10032fed  test    ecx, ecx
0x10032fef  jz      loc_100339CF
0x10032ff5  cmp     word ptr [ecx], 0
0x10032ff9  jz      loc_100339CF
0x10032fff  mov     [ebp+var_EC], 1
0x10033009  mov     eax, [ebp+var_E8]
0x1003300f  mov     edx, ecx
0x10033011  mov     [ebp+var_E0], 0
0x1003301b  mov     esi, eax
0x1003301d  cmp     word ptr [eax], 0
0x10033021  jz      short loc_10033099
0x10033023  mov     [ebp+var_C4], 0
0x1003302d  nop     dword ptr [eax]
0x10033030  cmp     word ptr [edx], 0
0x10033034  jz      short loc_10033099
0x10033036  mov     ecx, esi
0x10033038  lea     eax, [ecx+2]
0x1003303b  mov     [ebp+var_C8], eax
0x10033041  mov     ax, [ecx]
0x10033044  add     ecx, 2
0x10033047  test    ax, ax
0x1003304a  jnz     short loc_10033041
0x1003304c  sub     ecx, [ebp+var_C8]
0x10033052  sar     ecx, 1
0x10033054  lea     esi, [esi+ecx*2]
0x10033057  mov     ecx, edx
0x10033059  add     esi, 2
0x1003305c  lea     eax, [ecx+2]
0x1003305f  mov     [ebp+var_C8], eax
0x10033065  mov     ax, [ecx]
0x10033068  add     ecx, 2
0x1003306b  test    ax, ax
0x1003306e  jnz     short loc_10033065
0x10033070  sub     ecx, [ebp+var_C8]
0x10033076  mov     eax, [ebp+var_C4]
0x1003307c  sar     ecx, 1
0x1003307e  inc     eax
0x1003307f  mov     [ebp+var_E0], eax
0x10033085  mov     [ebp+var_C4], eax
0x1003308b  lea     edx, [edx+ecx*2]
0x1003308e  add     edx, 2
0x10033091  cmp     word ptr [esi], 0
0x10033095  jnz     short loc_10033030
0x10033097  jmp     short loc_100330A3
0x10033099  cmp     word ptr [esi], 0
0x1003309d  jnz     loc_1003399D
0x100330a3  cmp     word ptr [edx], 0
0x100330a7  jnz     loc_1003399D
0x100330ad  push    8
0x100330af  push    4
0x100330b1  lea     eax, [ebp+var_F8]
0x100330b7  push    eax
0x100330b8  push    [ebp+arg_4]
0x100330bb  push    ebx
0x100330bc  call    _ErrDispGetDatabaseInfo@20; ErrDispGetDatabaseInfo(x,x,x,x,x)
0x100330c1  mov     esi, eax
0x100330c3  test    esi, esi
0x100330c5  js      loc_100339A2
0x100330cb  mov     eax, [ebp+var_F8]
0x100330d1  cmp     eax, 10000h
0x100330d6  jz      loc_10033996
0x100330dc  cmp     eax, 10001h
0x100330e1  jz      loc_10033996
0x100330e7  lea     eax, [ebp+var_F4]
0x100330ed  push    eax
0x100330ee  push    offset _wszRcObject; "Relationships"
0x100330f3  push    0
0x100330f5  push    [ebp+arg_4]
0x100330f8  push    ebx
0x100330f9  call    _ErrDispGetObjidFromName@20; ErrDispGetObjidFromName(x,x,x,x,x)
0x100330fe  mov     esi, eax
0x10033100  test    esi, esi
0x10033102  js      loc_100339A2
0x10033108  push    ebx; sesid
0x10033109  call    _JetBeginTransaction@4; JetBeginTransaction(x)
0x1003310e  mov     esi, eax
0x10033110  test    esi, esi
0x10033112  js      loc_100339A2
0x10033118  mov     edx, [ebp+arg_4]
0x1003311b  lea     eax, [ebp+var_BC]
0x10033121  push    1
0x10033123  push    eax
0x10033124  mov     ecx, ebx
0x10033126  call    ErrOpenMSysRelationships
0x1003312b  mov     esi, eax
0x1003312d  test    esi, esi
0x1003312f  js      loc_100336C3
0x10033135  mov     edi, [ebp+var_B8]
0x1003313b  push    8
0x1003313d  push    [ebp+var_D8]
0x10033143  mov     [ebp+var_C0], edi
0x10033149  push    [ebp+var_F4]
0x1003314f  push    [ebp+arg_4]
0x10033152  push    ebx
0x10033153  call    _ErrDispCreateObject@20; ErrDispCreateObject(x,x,x,x,x)
0x10033158  mov     esi, eax
0x1003315a  test    esi, esi
0x1003315c  js      loc_100336C3
0x10033162  lea     eax, [ebp+var_F0]
0x10033168  push    eax
0x10033169  push    [ebp+var_D8]
0x1003316f  push    offset _wszRcObject; "Relationships"
0x10033174  push    [ebp+arg_4]
0x10033177  push    ebx
0x10033178  call    _ErrDispGetObjidFromName@20; ErrDispGetObjidFromName(x,x,x,x,x)
0x1003317d  mov     esi, eax
0x1003317f  test    esi, esi
0x10033181  js      loc_100336C3
0x10033187  cmp     [ebp+arg_28], 0
0x1003318b  jz      short loc_100331D9
0x1003318d  push    0
0x1003318f  push    0
0x10033191  push    [ebp+var_F0]
0x10033197  push    [ebp+arg_4]
0x1003319a  push    ebx
0x1003319b  call    _ErrSecSetOwner@20; ErrSecSetOwner(x,x,x,x,x)
0x100331a0  mov     esi, eax
0x100331a2  test    esi, esi
0x100331a4  js      loc_100336C3
0x100331aa  mov     eax, [ebp+arg_4]
0x100331ad  push    1
0x100331af  push    0
0x100331b1  push    0
0x100331b3  push    1
0x100331b5  push    1
0x100331b7  push    0
0x100331b9  push    0
0x100331bb  push    [ebp+var_F0]
0x100331c1  push    eax
0x100331c2  push    [ebp+var_F4]
0x100331c8  push    eax
0x100331c9  push    ebx
0x100331ca  call    _ErrSecBestowAccess@48; ErrSecBestowAccess(x,x,x,x,x,x,x,x,x,x,x,x)
0x100331cf  mov     esi, eax
0x100331d1  test    esi, esi
0x100331d3  js      loc_100336C3
0x100331d9  cmp     [ebp+var_E0], 0
0x100331e0  mov     eax, [ebp+var_E8]
0x100331e6  mov     [ebp+var_C8], eax
0x100331ec  mov     eax, [ebp+Block]
0x100331f2  mov     [ebp+var_C4], eax
0x100331f8  mov     [ebp+var_E4], 0
0x10033202  jbe     loc_1003367A
0x10033208  mov     eax, edi
0x1003320a  shl     edi, 4
0x1003320d  jmp     short loc_10033216
0x10033210  mov     eax, [ebp+var_C0]
0x10033216  cmp     eax, 800h
0x1003321b  jnb     loc_100336B8
0x10033221  cmp     eax, _tableidInit
0x10033227  jb      loc_100336B8
0x1003322d  lfence
0x10033230  mov     eax, _rgvtdef[edi]
0x10033236  mov     ecx, ebx
0x10033238  cmp     eax, 0FFFFFFFFh
0x1003323b  push    0
0x1003323d  push    dword_10163624[edi]; unsigned int
0x10033243  cmovnz  ecx, eax
0x10033246  mov     eax, dword_1016362C[edi]
0x1003324c  push    ecx; void *
0x1003324d  mov     esi, [eax+7Ch]
0x10033250  mov     ecx, esi
0x10033252  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10033258  call    esi
0x1003325a  mov     esi, eax
0x1003325c  test    esi, esi
0x1003325e  js      loc_100336BD
0x10033264  mov     ecx, [ebp+var_D8]
0x1003326a  lea     edx, [ecx+2]
0x1003326d  nop     dword ptr [eax]
0x10033270  mov     ax, [ecx]
0x10033273  add     ecx, 2
0x10033276  test    ax, ax
0x10033279  jnz     short loc_10033270
0x1003327b  mov     eax, [ebp+var_C0]
0x10033281  sub     ecx, edx
0x10033283  sar     ecx, 1
0x10033285  lea     edx, [ecx+ecx]
0x10033288  cmp     eax, _tableidInit
0x1003328e  jb      loc_100336AF
0x10033294  mov     eax, _rgvtdef[edi]
0x1003329a  mov     ecx, ebx
0x1003329c  mov     esi, dword_1016362C[edi]
0x100332a2  cmp     eax, 0FFFFFFFFh
0x100332a5  push    0
0x100332a7  push    0
0x100332a9  push    edx
0x100332aa  push    [ebp+var_D8]
0x100332b0  mov     esi, [esi+9Ch]
0x100332b6  cmovnz  ecx, eax
0x100332b9  push    [ebp+var_B0]
0x100332bf  push    dword_10163624[edi]; unsigned int
0x100332c5  push    ecx; void *
0x100332c6  mov     ecx, esi
0x100332c8  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100332ce  call    esi
0x100332d0  mov     esi, eax
0x100332d2  test    esi, esi
0x100332d4  js      loc_100336BD
0x100332da  mov     eax, [ebp+var_C0]
0x100332e0  cmp     eax, _tableidInit
0x100332e6  jb      loc_100336AF
0x100332ec  mov     eax, _rgvtdef[edi]
0x100332f2  mov     ecx, ebx
0x100332f4  mov     esi, dword_1016362C[edi]
0x100332fa  cmp     eax, 0FFFFFFFFh
0x100332fd  push    0
0x100332ff  push    0
0x10033301  cmovnz  ecx, eax
0x10033304  lea     eax, [ebp+arg_20]
0x10033307  mov     esi, [esi+9Ch]
0x1003330d  push    4
0x1003330f  push    eax
0x10033310  push    [ebp+var_AC]
0x10033316  push    dword_10163624[edi]; unsigned int
0x1003331c  push    ecx; void *
0x1003331d  mov     ecx, esi
0x1003331f  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10033325  call    esi
0x10033327  mov     esi, eax
0x10033329  test    esi, esi
0x1003332b  js      loc_100336BD
0x10033331  mov     eax, [ebp+var_C0]
0x10033337  cmp     eax, _tableidInit
0x1003333d  jb      loc_100336AF
0x10033343  mov     eax, _rgvtdef[edi]
0x10033349  mov     ecx, ebx
0x1003334b  mov     esi, dword_1016362C[edi]
0x10033351  cmp     eax, 0FFFFFFFFh
0x10033354  push    0
0x10033356  push    0
0x10033358  cmovnz  ecx, eax
0x1003335b  lea     eax, [ebp+var_E0]
0x10033361  mov     esi, [esi+9Ch]
  ... truncated ...
```
