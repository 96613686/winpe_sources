# ErrSecBuildUserToken(x,x,x,x,x)

- ea: `0x1003cb10`
- end: `0x1003ce63`
- name: `_ErrSecBuildUserToken@20`
- size: `851`
- prototype: `int __stdcall(int, size_t Size, int)`
- caller_count: `5`
- callee_count: `13`
- tags: `authz_impersonation, installer_update`

## callers

- `0x10018b00`
- `0x10019410`
- `0x10037a30`
- `0x10038030`
- `0x1003a6c0`

## callees

- `0x10029260`
- `0x1003c5f0`
- `0x1003c9b0`
- `0x1003cb10`
- `0x1003e160`
- `0x10043090`
- `0x10043840`
- `0x100440c0`
- `0x10044460`
- `0x10044b20`
- `0x10044b90`
- `0x10050000`
- `0x10122f60`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1003ce41`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1003ce41`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1003cb46`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1003cb46`

## string_xrefs

- `0x1003cca2`: `UserSID`
- `0x1003cccc`: `GroupSID`
- `0x1003cc4d`: `UserSID`

## pseudocode

```c
int __fastcall ErrSecBuildUserToken(int a1, int DbidSysOfSesidIscb, int a3, size_t Size, void **a5)
{
  _DWORD *v7; // eax
  int appended; // esi
  int OldSidFromSid; // eax
  int v11; // eax
  unsigned int v12; // edx
  int v13; // ecx
  int v14; // eax
  unsigned int v15; // [esp+20h] [ebp-13Ch] BYREF
  void *Block; // [esp+24h] [ebp-138h]
  size_t v17; // [esp+28h] [ebp-134h] BYREF
  int v18; // [esp+2Ch] [ebp-130h]
  size_t v19; // [esp+30h] [ebp-12Ch] BYREF
  void **v20; // [esp+34h] [ebp-128h]
  int v21; // [esp+38h] [ebp-124h]
  char v22[4]; // [esp+3Ch] [ebp-120h] BYREF
  int v23; // [esp+40h] [ebp-11Ch]
  _BYTE v24[128]; // [esp+54h] [ebp-108h] BYREF
  _BYTE v25[132]; // [esp+D4h] [ebp-88h] BYREF

  v18 = a3;
  v20 = a5;
  v7 = _malloc(0x100u);
  Block = v7;
  if ( !v7 )
    return -1011;
  *v7 = 0;
  v7[1] = 256;
  v7[2] = 0;
  v7[3] = 16;
  appended = ErrSecAppendSidToToken(Size);
  if ( appended < 0 )
    goto LABEL_37;
  OldSidFromSid = ErrSecGetOldSidFromSid(v18, Size, v24, &v17);
  appended = OldSidFromSid;
  if ( OldSidFromSid < 0 )
    goto LABEL_37;
  if ( OldSidFromSid != 1004 )
  {
    if ( v17 )
    {
      *(_DWORD *)Block = 1;
      appended = ErrSecAppendSidToToken(v17);
      if ( appended < 0 )
        goto LABEL_37;
    }
  }
  if ( DbidSysOfSesidIscb == -2 )
    goto LABEL_33;
  if ( DbidSysOfSesidIscb == -1 )
  {
    DbidSysOfSesidIscb = UtilGetDbidSysOfSesidIscb(a1);
    if ( DbidSysOfSesidIscb == -1 )
      goto LABEL_33;
  }
  v11 = ErrDispOpenTable(a1, DbidSysOfSesidIscb, &v15, L"MSysGroups", 0);
  appended = v11;
  if ( v11 < 0 )
  {
    if ( v11 == -1305 )
      appended = -1909;
    goto LABEL_37;
  }
  appended = ErrDispSetCurrentIndex(a1, v15, L"UserSID");
  if ( appended < 0 )
    goto LABEL_35;
  appended = ErrDispMakeKey(a1, v15, v18, Size, 1);
  if ( appended < 0 )
    goto LABEL_35;
  appended = ErrDispSeek(a1, v15, 1);
  if ( appended < 0 )
  {
LABEL_30:
    if ( appended != -1601 && appended != -1603 )
      goto LABEL_35;
    ErrDispCloseTable(a1, v15);
LABEL_33:
    *v20 = Block;
    return 0;
  }
  appended = ErrDispGetTableColumnInfo(a1, v15, L"UserSID", v22, 24, 0);
  if ( appended >= 0 )
  {
    v21 = v23;
    appended = ErrDispGetTableColumnInfo(a1, v15, L"GroupSID", v22, 24, 0);
    if ( appended >= 0 )
    {
      while ( 1 )
      {
        v12 = v15;
        if ( v15 >= 0x800 || v15 < tableidInit )
          break;
        v13 = a1;
        if ( rgvtdef[4 * v15] != -1 )
          v13 = rgvtdef[4 * v15];
        appended = (*(int (__thiscall **)(_DWORD, int, int, int, _BYTE *, int, size_t *, _DWORD, _DWORD))(dword_1016362C[4 * v15] + 140))(
                     *(_DWORD *)(dword_1016362C[4 * v15] + 140),
                     v13,
                     dword_10163624[4 * v15],
                     v23,
                     v25,
                     128,
                     &v19,
                     0,
                     0);
        if ( appended < 0 )
          goto LABEL_35;
        appended = ErrSecAppendSidToToken(v19);
        if ( appended < 0 )
          goto LABEL_35;
        v14 = ErrSecGetOldSidFromSid(v25, v19, v24, &v17);
        appended = v14;
        if ( v14 < 0 )
          goto LABEL_35;
        if ( v14 != 1004 )
        {
          if ( v17 )
          {
            appended = ErrSecAppendSidToToken(v17);
            if ( appended < 0 )
              goto LABEL_35;
          }
        }
        appended = ErrSecMoveNextKey(v21, v18, Size);
        if ( appended < 0 )
          goto LABEL_30;
      }
      appended = -1310;
      goto LABEL_36;
    }
  }
LABEL_35:
  v12 = v15;
LABEL_36:
  ErrDispCloseTable(a1, v12);
LABEL_37:
  if ( Block )
    _free(Block);
  return appended;
}

```

## disassembly

```asm
0x1003cb10  mov     edi, edi
0x1003cb12  push    ebp
0x1003cb13  mov     ebp, esp
0x1003cb15  and     esp, 0FFFFFFF8h
0x1003cb18  sub     esp, 13Ch
0x1003cb1e  mov     eax, ___security_cookie
0x1003cb23  xor     eax, esp
0x1003cb25  mov     [esp+13Ch+var_4], eax
0x1003cb2c  mov     eax, [ebp+arg_8]
0x1003cb2f  push    ebx
0x1003cb30  push    esi
0x1003cb31  mov     esi, [ebp+arg_0]
0x1003cb34  mov     ebx, edx
0x1003cb36  push    edi
0x1003cb37  push    100h; Size
0x1003cb3c  mov     edi, ecx
0x1003cb3e  mov     [esp+14Ch+var_130], esi
0x1003cb42  mov     [esp+14Ch+var_128], eax
0x1003cb46  call    ds:__imp__malloc
0x1003cb4c  add     esp, 4
0x1003cb4f  mov     [esp+148h+Block], eax
0x1003cb53  test    eax, eax
0x1003cb55  jnz     short loc_1003CB73
0x1003cb57  mov     eax, 0FFFFFC0Dh
0x1003cb5c  pop     edi
0x1003cb5d  pop     esi
0x1003cb5e  pop     ebx
0x1003cb5f  mov     ecx, [esp+13Ch+var_4]
0x1003cb66  xor     ecx, esp; StackCookie
0x1003cb68  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1003cb6d  mov     esp, ebp
0x1003cb6f  pop     ebp
0x1003cb70  retn    0Ch
0x1003cb73  push    [ebp+Size]; Size
0x1003cb76  mov     dword ptr [eax], 0
0x1003cb7c  lea     ecx, [esp+14Ch+Block]
0x1003cb80  mov     dword ptr [eax+4], 100h
0x1003cb87  mov     edx, esi
0x1003cb89  mov     dword ptr [eax+8], 0
0x1003cb90  mov     dword ptr [eax+0Ch], 10h
0x1003cb97  call    _ErrSecAppendSidToToken@12; ErrSecAppendSidToToken(x,x,x)
0x1003cb9c  mov     esi, eax
0x1003cb9e  test    esi, esi
0x1003cba0  js      loc_1003CE38
0x1003cba6  lea     eax, [esp+148h+var_134]
0x1003cbaa  mov     edx, ebx
0x1003cbac  push    eax
0x1003cbad  lea     eax, [esp+14Ch+var_108]
0x1003cbb1  mov     ecx, edi
0x1003cbb3  push    eax
0x1003cbb4  push    [ebp+Size]
0x1003cbb7  push    [esp+154h+var_130]
0x1003cbbb  call    _ErrSecGetOldSidFromSid@24; ErrSecGetOldSidFromSid(x,x,x,x,x,x)
0x1003cbc0  mov     esi, eax
0x1003cbc2  test    esi, esi
0x1003cbc4  js      loc_1003CE38
0x1003cbca  cmp     esi, 3ECh
0x1003cbd0  jz      short loc_1003CBFE
0x1003cbd2  cmp     [esp+148h+var_134], 0
0x1003cbd7  jbe     short loc_1003CBFE
0x1003cbd9  mov     eax, [esp+148h+Block]
0x1003cbdd  lea     edx, [esp+148h+var_108]
0x1003cbe1  lea     ecx, [esp+148h+Block]
0x1003cbe5  mov     dword ptr [eax], 1
0x1003cbeb  push    [esp+148h+var_134]; Size
0x1003cbef  call    _ErrSecAppendSidToToken@12; ErrSecAppendSidToToken(x,x,x)
0x1003cbf4  mov     esi, eax
0x1003cbf6  test    esi, esi
0x1003cbf8  js      loc_1003CE38
0x1003cbfe  cmp     ebx, 0FFFFFFFEh
0x1003cc01  jz      loc_1003CE03
0x1003cc07  cmp     ebx, 0FFFFFFFFh
0x1003cc0a  jnz     short loc_1003CC1E
0x1003cc0c  mov     ecx, edi
0x1003cc0e  call    _UtilGetDbidSysOfSesidIscb@4; UtilGetDbidSysOfSesidIscb(x)
0x1003cc13  mov     ebx, eax
0x1003cc15  cmp     ebx, 0FFFFFFFFh
0x1003cc18  jz      loc_1003CE03
0x1003cc1e  push    0
0x1003cc20  push    offset _wszSgTable; "MSysGroups"
0x1003cc25  lea     eax, [esp+150h+var_13C]
0x1003cc29  push    eax
0x1003cc2a  push    ebx
0x1003cc2b  push    edi
0x1003cc2c  call    _ErrDispOpenTable@20; ErrDispOpenTable(x,x,x,x,x)
0x1003cc31  mov     esi, eax
0x1003cc33  test    esi, esi
0x1003cc35  jns     short loc_1003CC4D
0x1003cc37  cmp     esi, 0FFFFFAE7h
0x1003cc3d  jnz     loc_1003CE38
0x1003cc43  mov     esi, 0FFFFF88Bh
0x1003cc48  jmp     loc_1003CE38
0x1003cc4d  push    offset _wszSgUserIndex; "UserSID"
0x1003cc52  push    [esp+14Ch+var_13C]
0x1003cc56  push    edi
0x1003cc57  call    _ErrDispSetCurrentIndex@12; ErrDispSetCurrentIndex(x,x,x)
0x1003cc5c  mov     esi, eax
0x1003cc5e  test    esi, esi
0x1003cc60  js      loc_1003CE2D
0x1003cc66  push    1
0x1003cc68  push    [ebp+Size]
0x1003cc6b  push    [esp+150h+var_130]
0x1003cc6f  push    [esp+154h+var_13C]
0x1003cc73  push    edi
0x1003cc74  call    _ErrDispMakeKey@20; ErrDispMakeKey(x,x,x,x,x)
0x1003cc79  mov     esi, eax
0x1003cc7b  test    esi, esi
0x1003cc7d  js      loc_1003CE2D
0x1003cc83  push    1
0x1003cc85  push    [esp+14Ch+var_13C]
0x1003cc89  push    edi
0x1003cc8a  call    _ErrDispSeek@12; ErrDispSeek(x,x,x)
0x1003cc8f  mov     esi, eax
0x1003cc91  test    esi, esi
0x1003cc93  js      loc_1003CDE9
0x1003cc99  push    0
0x1003cc9b  push    18h
0x1003cc9d  lea     eax, [esp+150h+var_120]
0x1003cca1  push    eax
0x1003cca2  push    offset _wszSgUserSidColumn; "UserSID"
0x1003cca7  push    [esp+158h+var_13C]
0x1003ccab  push    edi
0x1003ccac  call    _ErrDispGetTableColumnInfo@24; ErrDispGetTableColumnInfo(x,x,x,x,x,x)
0x1003ccb1  mov     esi, eax
0x1003ccb3  test    esi, esi
0x1003ccb5  js      loc_1003CE2D
0x1003ccbb  mov     eax, [esp+148h+var_11C]
0x1003ccbf  push    0
0x1003ccc1  push    18h
0x1003ccc3  mov     [esp+150h+var_124], eax
0x1003ccc7  lea     eax, [esp+150h+var_120]
0x1003cccb  push    eax
0x1003cccc  push    offset _wszSgGroupSidColumn; "GroupSID"
0x1003ccd1  push    [esp+158h+var_13C]
0x1003ccd5  push    edi
0x1003ccd6  call    _ErrDispGetTableColumnInfo@24; ErrDispGetTableColumnInfo(x,x,x,x,x,x)
0x1003ccdb  mov     esi, eax
0x1003ccdd  test    esi, esi
0x1003ccdf  js      loc_1003CE2D
0x1003cce5  nop     word ptr [eax+eax+00000000h]
0x1003ccf0  mov     edx, [esp+148h+var_13C]
0x1003ccf4  cmp     edx, 800h
0x1003ccfa  jnb     loc_1003CE26
0x1003cd00  cmp     edx, _tableidInit
0x1003cd06  jb      loc_1003CE26
0x1003cd0c  shl     edx, 4
0x1003cd0f  mov     ecx, edi
0x1003cd11  push    0
0x1003cd13  push    0
0x1003cd15  mov     eax, _rgvtdef[edx]
0x1003cd1b  cmp     eax, 0FFFFFFFFh
0x1003cd1e  mov     esi, dword_1016362C[edx]
0x1003cd24  cmovnz  ecx, eax
0x1003cd27  lea     eax, [esp+150h+var_12C]
0x1003cd2b  push    eax
0x1003cd2c  push    80h
0x1003cd31  mov     esi, [esi+8Ch]
0x1003cd37  lea     eax, [esp+158h+var_88]
0x1003cd3e  push    eax
0x1003cd3f  push    [esp+15Ch+var_11C]
0x1003cd43  push    dword_10163624[edx]; unsigned int
0x1003cd49  push    ecx; void *
0x1003cd4a  mov     ecx, esi
0x1003cd4c  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1003cd52  call    esi
0x1003cd54  mov     esi, eax
0x1003cd56  test    esi, esi
0x1003cd58  js      loc_1003CE2D
0x1003cd5e  push    [esp+148h+var_12C]; Size
0x1003cd62  lea     edx, [esp+14Ch+var_88]
0x1003cd69  lea     ecx, [esp+14Ch+Block]
0x1003cd6d  call    _ErrSecAppendSidToToken@12; ErrSecAppendSidToToken(x,x,x)
0x1003cd72  mov     esi, eax
0x1003cd74  test    esi, esi
0x1003cd76  js      loc_1003CE2D
0x1003cd7c  lea     eax, [esp+148h+var_134]
0x1003cd80  mov     edx, ebx
0x1003cd82  push    eax
0x1003cd83  lea     eax, [esp+14Ch+var_108]
0x1003cd87  mov     ecx, edi
0x1003cd89  push    eax
0x1003cd8a  push    [esp+150h+var_12C]
0x1003cd8e  lea     eax, [esp+154h+var_88]
0x1003cd95  push    eax
0x1003cd96  call    _ErrSecGetOldSidFromSid@24; ErrSecGetOldSidFromSid(x,x,x,x,x,x)
0x1003cd9b  mov     esi, eax
0x1003cd9d  test    esi, esi
0x1003cd9f  js      loc_1003CE2D
0x1003cda5  cmp     esi, 3ECh
0x1003cdab  jz      short loc_1003CDC9
0x1003cdad  mov     eax, [esp+148h+var_134]
0x1003cdb1  test    eax, eax
0x1003cdb3  jz      short loc_1003CDC9
0x1003cdb5  push    eax; Size
0x1003cdb6  lea     edx, [esp+14Ch+var_108]
0x1003cdba  lea     ecx, [esp+14Ch+Block]
0x1003cdbe  call    _ErrSecAppendSidToToken@12; ErrSecAppendSidToToken(x,x,x)
0x1003cdc3  mov     esi, eax
0x1003cdc5  test    esi, esi
0x1003cdc7  js      short loc_1003CE2D
0x1003cdc9  push    [ebp+Size]
0x1003cdcc  mov     edx, [esp+14Ch+var_13C]
0x1003cdd0  mov     ecx, edi
0x1003cdd2  push    [esp+14Ch+var_130]
0x1003cdd6  push    [esp+150h+var_124]
0x1003cdda  call    _ErrSecMoveNextKey@20; ErrSecMoveNextKey(x,x,x,x,x)
0x1003cddf  mov     esi, eax
0x1003cde1  test    esi, esi
0x1003cde3  jns     loc_1003CCF0
0x1003cde9  cmp     esi, 0FFFFF9BFh
0x1003cdef  jz      short loc_1003CDF9
0x1003cdf1  cmp     esi, 0FFFFF9BDh
0x1003cdf7  jnz     short loc_1003CE2D
0x1003cdf9  push    [esp+148h+var_13C]
0x1003cdfd  push    edi
0x1003cdfe  call    _ErrDispCloseTable@8; ErrDispCloseTable(x,x)
0x1003ce03  mov     ecx, [esp+148h+var_128]
0x1003ce07  mov     eax, [esp+148h+Block]
0x1003ce0b  mov     [ecx], eax
0x1003ce0d  xor     eax, eax
0x1003ce0f  pop     edi
0x1003ce10  pop     esi
0x1003ce11  pop     ebx
0x1003ce12  mov     ecx, [esp+13Ch+var_4]
0x1003ce19  xor     ecx, esp; StackCookie
0x1003ce1b  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1003ce20  mov     esp, ebp
0x1003ce22  pop     ebp
0x1003ce23  retn    0Ch
0x1003ce26  mov     esi, 0FFFFFAE2h
0x1003ce2b  jmp     short loc_1003CE31
0x1003ce2d  mov     edx, [esp+148h+var_13C]
0x1003ce31  push    edx
0x1003ce32  push    edi
0x1003ce33  call    _ErrDispCloseTable@8; ErrDispCloseTable(x,x)
0x1003ce38  mov     eax, [esp+148h+Block]
0x1003ce3c  test    eax, eax
0x1003ce3e  jz      short loc_1003CE4A
0x1003ce40  push    eax; Block
0x1003ce41  call    ds:__imp__free
0x1003ce47  add     esp, 4
0x1003ce4a  mov     ecx, [esp+148h+var_4]
0x1003ce51  mov     eax, esi
0x1003ce53  pop     edi
0x1003ce54  pop     esi
0x1003ce55  pop     ebx
0x1003ce56  xor     ecx, esp; StackCookie
0x1003ce58  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1003ce5d  mov     esp, ebp
0x1003ce5f  pop     ebp
0x1003ce60  retn    0Ch
```
