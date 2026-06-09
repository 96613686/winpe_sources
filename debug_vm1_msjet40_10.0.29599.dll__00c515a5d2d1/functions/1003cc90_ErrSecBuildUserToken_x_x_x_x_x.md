# ErrSecBuildUserToken(x,x,x,x,x)

- ea: `0x1003cc90`
- end: `0x1003cfe3`
- name: `_ErrSecBuildUserToken@20`
- size: `851`
- prototype: `int __stdcall(int, size_t Size, int)`
- caller_count: `5`
- callee_count: `13`
- tags: `authz_impersonation, installer_update`

## callers

- `0x10018c40`
- `0x10019550`
- `0x10037bb0`
- `0x100381b0`
- `0x1003a840`

## callees

- `0x10029430`
- `0x1003c770`
- `0x1003cb30`
- `0x1003cc90`
- `0x1003e2f0`
- `0x10043220`
- `0x100439d0`
- `0x10044240`
- `0x100445e0`
- `0x10044ca0`
- `0x10044d10`
- `0x10050190`
- `0x10123110`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1003cfc1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1003cfc1`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1003ccc6`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1003ccc6`

## string_xrefs

- `0x1003ce22`: `UserSID`
- `0x1003ce4c`: `GroupSID`
- `0x1003cdcd`: `UserSID`

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
        appended = (*(int (__thiscall **)(_DWORD, int, int, int, _BYTE *, int, size_t *, _DWORD, _DWORD))(dword_101636CC[4 * v15] + 140))(
                     *(_DWORD *)(dword_101636CC[4 * v15] + 140),
                     v13,
                     dword_101636C4[4 * v15],
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
0x1003cc90  mov     edi, edi
0x1003cc92  push    ebp
0x1003cc93  mov     ebp, esp
0x1003cc95  and     esp, 0FFFFFFF8h
0x1003cc98  sub     esp, 13Ch
0x1003cc9e  mov     eax, ___security_cookie
0x1003cca3  xor     eax, esp
0x1003cca5  mov     [esp+13Ch+var_4], eax
0x1003ccac  mov     eax, [ebp+arg_8]
0x1003ccaf  push    ebx
0x1003ccb0  push    esi
0x1003ccb1  mov     esi, [ebp+arg_0]
0x1003ccb4  mov     ebx, edx
0x1003ccb6  push    edi
0x1003ccb7  push    100h; Size
0x1003ccbc  mov     edi, ecx
0x1003ccbe  mov     [esp+14Ch+var_130], esi
0x1003ccc2  mov     [esp+14Ch+var_128], eax
0x1003ccc6  call    ds:__imp__malloc
0x1003cccc  add     esp, 4
0x1003cccf  mov     [esp+148h+Block], eax
0x1003ccd3  test    eax, eax
0x1003ccd5  jnz     short loc_1003CCF3
0x1003ccd7  mov     eax, 0FFFFFC0Dh
0x1003ccdc  pop     edi
0x1003ccdd  pop     esi
0x1003ccde  pop     ebx
0x1003ccdf  mov     ecx, [esp+13Ch+var_4]
0x1003cce6  xor     ecx, esp; StackCookie
0x1003cce8  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1003cced  mov     esp, ebp
0x1003ccef  pop     ebp
0x1003ccf0  retn    0Ch
0x1003ccf3  push    [ebp+Size]; Size
0x1003ccf6  mov     dword ptr [eax], 0
0x1003ccfc  lea     ecx, [esp+14Ch+Block]
0x1003cd00  mov     dword ptr [eax+4], 100h
0x1003cd07  mov     edx, esi
0x1003cd09  mov     dword ptr [eax+8], 0
0x1003cd10  mov     dword ptr [eax+0Ch], 10h
0x1003cd17  call    _ErrSecAppendSidToToken@12; ErrSecAppendSidToToken(x,x,x)
0x1003cd1c  mov     esi, eax
0x1003cd1e  test    esi, esi
0x1003cd20  js      loc_1003CFB8
0x1003cd26  lea     eax, [esp+148h+var_134]
0x1003cd2a  mov     edx, ebx
0x1003cd2c  push    eax
0x1003cd2d  lea     eax, [esp+14Ch+var_108]
0x1003cd31  mov     ecx, edi
0x1003cd33  push    eax
0x1003cd34  push    [ebp+Size]
0x1003cd37  push    [esp+154h+var_130]
0x1003cd3b  call    _ErrSecGetOldSidFromSid@24; ErrSecGetOldSidFromSid(x,x,x,x,x,x)
0x1003cd40  mov     esi, eax
0x1003cd42  test    esi, esi
0x1003cd44  js      loc_1003CFB8
0x1003cd4a  cmp     esi, 3ECh
0x1003cd50  jz      short loc_1003CD7E
0x1003cd52  cmp     [esp+148h+var_134], 0
0x1003cd57  jbe     short loc_1003CD7E
0x1003cd59  mov     eax, [esp+148h+Block]
0x1003cd5d  lea     edx, [esp+148h+var_108]
0x1003cd61  lea     ecx, [esp+148h+Block]
0x1003cd65  mov     dword ptr [eax], 1
0x1003cd6b  push    [esp+148h+var_134]; Size
0x1003cd6f  call    _ErrSecAppendSidToToken@12; ErrSecAppendSidToToken(x,x,x)
0x1003cd74  mov     esi, eax
0x1003cd76  test    esi, esi
0x1003cd78  js      loc_1003CFB8
0x1003cd7e  cmp     ebx, 0FFFFFFFEh
0x1003cd81  jz      loc_1003CF83
0x1003cd87  cmp     ebx, 0FFFFFFFFh
0x1003cd8a  jnz     short loc_1003CD9E
0x1003cd8c  mov     ecx, edi
0x1003cd8e  call    _UtilGetDbidSysOfSesidIscb@4; UtilGetDbidSysOfSesidIscb(x)
0x1003cd93  mov     ebx, eax
0x1003cd95  cmp     ebx, 0FFFFFFFFh
0x1003cd98  jz      loc_1003CF83
0x1003cd9e  push    0
0x1003cda0  push    offset _wszSgTable; "MSysGroups"
0x1003cda5  lea     eax, [esp+150h+var_13C]
0x1003cda9  push    eax
0x1003cdaa  push    ebx
0x1003cdab  push    edi
0x1003cdac  call    _ErrDispOpenTable@20; ErrDispOpenTable(x,x,x,x,x)
0x1003cdb1  mov     esi, eax
0x1003cdb3  test    esi, esi
0x1003cdb5  jns     short loc_1003CDCD
0x1003cdb7  cmp     esi, 0FFFFFAE7h
0x1003cdbd  jnz     loc_1003CFB8
0x1003cdc3  mov     esi, 0FFFFF88Bh
0x1003cdc8  jmp     loc_1003CFB8
0x1003cdcd  push    offset _wszSgUserIndex; "UserSID"
0x1003cdd2  push    [esp+14Ch+var_13C]
0x1003cdd6  push    edi
0x1003cdd7  call    _ErrDispSetCurrentIndex@12; ErrDispSetCurrentIndex(x,x,x)
0x1003cddc  mov     esi, eax
0x1003cdde  test    esi, esi
0x1003cde0  js      loc_1003CFAD
0x1003cde6  push    1
0x1003cde8  push    [ebp+Size]
0x1003cdeb  push    [esp+150h+var_130]
0x1003cdef  push    [esp+154h+var_13C]
0x1003cdf3  push    edi
0x1003cdf4  call    _ErrDispMakeKey@20; ErrDispMakeKey(x,x,x,x,x)
0x1003cdf9  mov     esi, eax
0x1003cdfb  test    esi, esi
0x1003cdfd  js      loc_1003CFAD
0x1003ce03  push    1
0x1003ce05  push    [esp+14Ch+var_13C]
0x1003ce09  push    edi
0x1003ce0a  call    _ErrDispSeek@12; ErrDispSeek(x,x,x)
0x1003ce0f  mov     esi, eax
0x1003ce11  test    esi, esi
0x1003ce13  js      loc_1003CF69
0x1003ce19  push    0
0x1003ce1b  push    18h
0x1003ce1d  lea     eax, [esp+150h+var_120]
0x1003ce21  push    eax
0x1003ce22  push    offset _wszSgUserSidColumn; "UserSID"
0x1003ce27  push    [esp+158h+var_13C]
0x1003ce2b  push    edi
0x1003ce2c  call    _ErrDispGetTableColumnInfo@24; ErrDispGetTableColumnInfo(x,x,x,x,x,x)
0x1003ce31  mov     esi, eax
0x1003ce33  test    esi, esi
0x1003ce35  js      loc_1003CFAD
0x1003ce3b  mov     eax, [esp+148h+var_11C]
0x1003ce3f  push    0
0x1003ce41  push    18h
0x1003ce43  mov     [esp+150h+var_124], eax
0x1003ce47  lea     eax, [esp+150h+var_120]
0x1003ce4b  push    eax
0x1003ce4c  push    offset _wszSgGroupSidColumn; "GroupSID"
0x1003ce51  push    [esp+158h+var_13C]
0x1003ce55  push    edi
0x1003ce56  call    _ErrDispGetTableColumnInfo@24; ErrDispGetTableColumnInfo(x,x,x,x,x,x)
0x1003ce5b  mov     esi, eax
0x1003ce5d  test    esi, esi
0x1003ce5f  js      loc_1003CFAD
0x1003ce65  nop     word ptr [eax+eax+00000000h]
0x1003ce70  mov     edx, [esp+148h+var_13C]
0x1003ce74  cmp     edx, 800h
0x1003ce7a  jnb     loc_1003CFA6
0x1003ce80  cmp     edx, _tableidInit
0x1003ce86  jb      loc_1003CFA6
0x1003ce8c  shl     edx, 4
0x1003ce8f  mov     ecx, edi
0x1003ce91  push    0
0x1003ce93  push    0
0x1003ce95  mov     eax, _rgvtdef[edx]
0x1003ce9b  cmp     eax, 0FFFFFFFFh
0x1003ce9e  mov     esi, dword_101636CC[edx]
0x1003cea4  cmovnz  ecx, eax
0x1003cea7  lea     eax, [esp+150h+var_12C]
0x1003ceab  push    eax
0x1003ceac  push    80h
0x1003ceb1  mov     esi, [esi+8Ch]
0x1003ceb7  lea     eax, [esp+158h+var_88]
0x1003cebe  push    eax
0x1003cebf  push    [esp+15Ch+var_11C]
0x1003cec3  push    dword_101636C4[edx]; unsigned int
0x1003cec9  push    ecx; void *
0x1003ceca  mov     ecx, esi
0x1003cecc  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1003ced2  call    esi
0x1003ced4  mov     esi, eax
0x1003ced6  test    esi, esi
0x1003ced8  js      loc_1003CFAD
0x1003cede  push    [esp+148h+var_12C]; Size
0x1003cee2  lea     edx, [esp+14Ch+var_88]
0x1003cee9  lea     ecx, [esp+14Ch+Block]
0x1003ceed  call    _ErrSecAppendSidToToken@12; ErrSecAppendSidToToken(x,x,x)
0x1003cef2  mov     esi, eax
0x1003cef4  test    esi, esi
0x1003cef6  js      loc_1003CFAD
0x1003cefc  lea     eax, [esp+148h+var_134]
0x1003cf00  mov     edx, ebx
0x1003cf02  push    eax
0x1003cf03  lea     eax, [esp+14Ch+var_108]
0x1003cf07  mov     ecx, edi
0x1003cf09  push    eax
0x1003cf0a  push    [esp+150h+var_12C]
0x1003cf0e  lea     eax, [esp+154h+var_88]
0x1003cf15  push    eax
0x1003cf16  call    _ErrSecGetOldSidFromSid@24; ErrSecGetOldSidFromSid(x,x,x,x,x,x)
0x1003cf1b  mov     esi, eax
0x1003cf1d  test    esi, esi
0x1003cf1f  js      loc_1003CFAD
0x1003cf25  cmp     esi, 3ECh
0x1003cf2b  jz      short loc_1003CF49
0x1003cf2d  mov     eax, [esp+148h+var_134]
0x1003cf31  test    eax, eax
0x1003cf33  jz      short loc_1003CF49
0x1003cf35  push    eax; Size
0x1003cf36  lea     edx, [esp+14Ch+var_108]
0x1003cf3a  lea     ecx, [esp+14Ch+Block]
0x1003cf3e  call    _ErrSecAppendSidToToken@12; ErrSecAppendSidToToken(x,x,x)
0x1003cf43  mov     esi, eax
0x1003cf45  test    esi, esi
0x1003cf47  js      short loc_1003CFAD
0x1003cf49  push    [ebp+Size]
0x1003cf4c  mov     edx, [esp+14Ch+var_13C]
0x1003cf50  mov     ecx, edi
0x1003cf52  push    [esp+14Ch+var_130]
0x1003cf56  push    [esp+150h+var_124]
0x1003cf5a  call    _ErrSecMoveNextKey@20; ErrSecMoveNextKey(x,x,x,x,x)
0x1003cf5f  mov     esi, eax
0x1003cf61  test    esi, esi
0x1003cf63  jns     loc_1003CE70
0x1003cf69  cmp     esi, 0FFFFF9BFh
0x1003cf6f  jz      short loc_1003CF79
0x1003cf71  cmp     esi, 0FFFFF9BDh
0x1003cf77  jnz     short loc_1003CFAD
0x1003cf79  push    [esp+148h+var_13C]
0x1003cf7d  push    edi
0x1003cf7e  call    _ErrDispCloseTable@8; ErrDispCloseTable(x,x)
0x1003cf83  mov     ecx, [esp+148h+var_128]
0x1003cf87  mov     eax, [esp+148h+Block]
0x1003cf8b  mov     [ecx], eax
0x1003cf8d  xor     eax, eax
0x1003cf8f  pop     edi
0x1003cf90  pop     esi
0x1003cf91  pop     ebx
0x1003cf92  mov     ecx, [esp+13Ch+var_4]
0x1003cf99  xor     ecx, esp; StackCookie
0x1003cf9b  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1003cfa0  mov     esp, ebp
0x1003cfa2  pop     ebp
0x1003cfa3  retn    0Ch
0x1003cfa6  mov     esi, 0FFFFFAE2h
0x1003cfab  jmp     short loc_1003CFB1
0x1003cfad  mov     edx, [esp+148h+var_13C]
0x1003cfb1  push    edx
0x1003cfb2  push    edi
0x1003cfb3  call    _ErrDispCloseTable@8; ErrDispCloseTable(x,x)
0x1003cfb8  mov     eax, [esp+148h+Block]
0x1003cfbc  test    eax, eax
0x1003cfbe  jz      short loc_1003CFCA
0x1003cfc0  push    eax; Block
0x1003cfc1  call    ds:__imp__free
0x1003cfc7  add     esp, 4
0x1003cfca  mov     ecx, [esp+148h+var_4]
0x1003cfd1  mov     eax, esi
0x1003cfd3  pop     edi
0x1003cfd4  pop     esi
0x1003cfd5  pop     ebx
0x1003cfd6  xor     ecx, esp; StackCookie
0x1003cfd8  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1003cfdd  mov     esp, ebp
0x1003cfdf  pop     ebp
0x1003cfe0  retn    0Ch
```
