# JetRemoveMember(x,x,x)

- ea: `0x10038620`
- end: `0x10038ba8`
- name: `_JetRemoveMember@12`
- size: `1416`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, installer_update`

## callers

- `0x100cfb84`

## callees

- `0x10029480`
- `0x10038620`
- `0x10039d80`
- `0x1003c8e0`
- `0x1003c9a0`
- `0x1003cb30`
- `0x1003d260`
- `0x1003da50`
- `0x1003db70`
- `0x1003e9b0`
- `0x1003ea00`
- `0x10043220`
- `0x100433f0`
- `0x100439d0`
- `0x10043d40`
- `0x10044240`
- `0x100445e0`
- `0x10044ca0`
- `0x10044d10`
- `0x10044f10`
- `0x10050190`
- `0x10123110`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1003868c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100386d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10038738`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1003879e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100387f7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1003888c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100388de`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10038add`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10038b89`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1003868c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100386d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10038738`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1003879e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100387f7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1003888c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100388de`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10038add`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10038b89`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1003865e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1003865e`

## string_xrefs

- `0x1003891f`: `UserSID`
- `0x100388fd`: `GroupSID`

## pseudocode

```c
int __stdcall JetRemoveMember(int a1, void *a2, void *a3)
{
  int v3; // esi
  int v5; // ebx
  int ObjidFromName; // esi
  int v7; // eax
  int TableColumnInfo; // esi
  void *v9; // ebx
  int v10; // eax
  int v11; // ebx
  int v12; // ecx
  int v13; // edx
  int v14; // ecx
  void *v15; // esi
  int OldSidFromSid; // eax
  unsigned int v17; // [esp+20h] [ebp-244h] BYREF
  int v18; // [esp+24h] [ebp-240h] BYREF
  void *Src; // [esp+28h] [ebp-23Ch]
  int v20; // [esp+2Ch] [ebp-238h] BYREF
  void *v21; // [esp+30h] [ebp-234h] BYREF
  int v22; // [esp+34h] [ebp-230h]
  _DWORD v23[2]; // [esp+38h] [ebp-22Ch] BYREF
  int v24; // [esp+40h] [ebp-224h] BYREF
  _BYTE v25[4]; // [esp+44h] [ebp-220h] BYREF
  int v26; // [esp+48h] [ebp-21Ch]
  _BYTE v27[128]; // [esp+5Ch] [ebp-208h] BYREF
  int v28[32]; // [esp+DCh] [ebp-188h] BYREF
  _BYTE v29[128]; // [esp+15Ch] [ebp-108h] BYREF
  _BYTE v30[132]; // [esp+1DCh] [ebp-88h] BYREF

  Src = a2;
  v21 = a3;
  v22 = 0;
  EnterCriticalSection(critJet);
  v3 = isibHead;
  if ( isibHead == -1 )
  {
LABEL_4:
    LeaveCriticalSection(critJet);
    return -1104;
  }
  while ( rgsib[26 * v3] != a1 )
  {
    v3 = dword_1016EB88[26 * v3];
    if ( v3 == -1 )
      goto LABEL_4;
  }
  ClearErrorInfo(a1);
  v5 = (int)*(&rgiscb + 5 * dword_1016EB70[26 * v3] + 3);
  v23[1] = v5;
  if ( v5 == -1 )
  {
    LeaveCriticalSection(critJet);
    return -1802;
  }
  ObjidFromName = ErrDispGetObjidFromName(a1, v5, L"Tables", L"MSysGroups", v23);
  if ( ObjidFromName < 0 )
    goto LABEL_25;
  v7 = (int)*(&::Src + 5 * mpdbidiiscb[v5]);
  if ( !v7 )
  {
    LeaveCriticalSection(critJet);
    return -1001;
  }
  ObjidFromName = ErrSecCollectAccess(v23[0], v7, 0, &v18, 0);
  if ( ObjidFromName < 0 )
    goto LABEL_25;
  if ( (v18 & 0x80u) == 0 )
  {
    UtilSetErrorInfoReal(a1, Src, 0, 0, -8114, 0, 0, 0);
    LeaveCriticalSection(critJet);
    return -1907;
  }
  ObjidFromName = ErrSecGetSidFromName(a1, -1, Src, (int)v27, 0x80u, (int)&v20, (int)&v18);
  if ( ObjidFromName < 0 )
    goto LABEL_25;
  if ( !v18 )
  {
LABEL_15:
    LeaveCriticalSection(critJet);
    return -1904;
  }
  Src = (void *)v20;
  ObjidFromName = ErrSecGetSidFromName(a1, -1, v21, (int)v28, 0x80u, (int)&v20, (int)&v18);
  if ( ObjidFromName < 0 )
    goto LABEL_25;
  if ( v18 )
    goto LABEL_15;
  v18 = v20;
  if ( v27[0] == 1 )
  {
    ObjidFromName = ErrSecGetNumMembers(Src, &v21);
    if ( ObjidFromName < 0 )
    {
LABEL_25:
      LeaveCriticalSection(critJet);
      return ObjidFromName;
    }
    if ( v21 == (void *)1 )
    {
      LeaveCriticalSection(critJet);
      return -1906;
    }
  }
  ObjidFromName = ErrDispOpenTable(a1, v5, &v17, L"MSysGroups", 0x80000000);
  if ( ObjidFromName < 0 )
  {
    if ( ObjidFromName == -1305 )
      ObjidFromName = -1909;
    goto LABEL_25;
  }
  TableColumnInfo = ErrDispSetCurrentIndex(a1, v17, L"GroupSID");
  if ( TableColumnInfo < 0 )
    goto LABEL_53;
  TableColumnInfo = ErrDispGetTableColumnInfo(a1, v17, L"UserSID", v25, 24, 0);
  if ( TableColumnInfo < 0 )
    goto LABEL_53;
  v9 = Src;
  TableColumnInfo = ErrDispMakeKey(a1, v17, v27, Src, 1);
  if ( TableColumnInfo < 0 )
    goto LABEL_53;
  v10 = ErrDispSeek(a1, v17, 1);
  TableColumnInfo = v10;
  if ( v10 != -1601 )
  {
    if ( v10 < 0 )
      goto LABEL_53;
    TableColumnInfo = ErrDispMakeKey(a1, v17, v27, v9, 1);
    if ( TableColumnInfo < 0 )
      goto LABEL_53;
    TableColumnInfo = ErrDispSetIndexRange(a1, v17, 3);
  }
  if ( TableColumnInfo < 0 )
  {
LABEL_49:
    if ( TableColumnInfo != -1601 && TableColumnInfo != -1603 )
      goto LABEL_53;
  }
  else
  {
    v11 = v18;
    while ( 1 )
    {
      if ( v17 >= 0x800 || v17 < tableidInit )
      {
LABEL_54:
        TableColumnInfo = -1310;
        goto LABEL_53;
      }
      v12 = a1;
      if ( rgvtdef[4 * v17] != -1 )
        v12 = rgvtdef[4 * v17];
      TableColumnInfo = (*(int (__thiscall **)(_DWORD, int, int, int, _BYTE *, int, int *, _DWORD, _DWORD))(dword_101636CC[4 * v17] + 140))(
                          *(_DWORD *)(dword_101636CC[4 * v17] + 140),
                          v12,
                          dword_101636C4[4 * v17],
                          v26,
                          v29,
                          128,
                          &v20,
                          0,
                          0);
      if ( TableColumnInfo < 0 )
        goto LABEL_53;
      if ( SecFSameSid(v28, v11) )
        break;
      if ( v17 >= 0x800 || v17 < tableidInit )
        goto LABEL_54;
      v13 = 4 * v17;
      v14 = a1;
      _mm_lfence();
      if ( rgvtdef[v13] != -1 )
        v14 = rgvtdef[4 * v17];
      TableColumnInfo = (*(int (__thiscall **)(_DWORD, int, int, int, _DWORD))(dword_101636CC[4 * v17] + 104))(
                          *(_DWORD *)(dword_101636CC[4 * v17] + 104),
                          v14,
                          dword_101636C4[4 * v17],
                          1,
                          0);
      if ( TableColumnInfo < 0 )
        goto LABEL_49;
    }
    v22 = 1;
    TableColumnInfo = ErrDispDelete(a1, v17);
    if ( TableColumnInfo < 0 )
      goto LABEL_53;
  }
  if ( !v22 )
  {
    TableColumnInfo = -1906;
LABEL_53:
    ErrDispCloseTable(a1, v17);
    LeaveCriticalSection(critJet);
    return TableColumnInfo;
  }
  ErrDispCloseTable(a1, v17);
  UtilGetpUserTokenOfSesidIscb(a1);
  if ( !SecIndexOfTokenSid(v18) )
  {
    v15 = Src;
    SecDeleteSidFromToken(Src);
    OldSidFromSid = ErrSecGetOldSidFromSid(v27, v15, v30, &v24);
    TableColumnInfo = OldSidFromSid;
    if ( OldSidFromSid < 0 )
      goto LABEL_53;
    if ( OldSidFromSid != 1004 && v24 )
      SecDeleteSidFromToken(v24);
  }
  LeaveCriticalSection(critJet);
  return 0;
}

```

## disassembly

```asm
0x10038620  mov     edi, edi
0x10038622  push    ebp
0x10038623  mov     ebp, esp
0x10038625  and     esp, 0FFFFFFF8h
0x10038628  sub     esp, 244h
0x1003862e  mov     eax, ___security_cookie
0x10038633  xor     eax, esp
0x10038635  mov     [esp+244h+var_4], eax
0x1003863c  mov     eax, [ebp+arg_4]
0x1003863f  push    ebx
0x10038640  push    esi
0x10038641  push    edi
0x10038642  push    _critJet; lpCriticalSection
0x10038648  mov     edi, [ebp+arg_0]
0x1003864b  mov     [esp+254h+Src], eax
0x1003864f  mov     eax, [ebp+arg_8]
0x10038652  mov     [esp+254h+var_234], eax
0x10038656  mov     [esp+254h+var_230], 0
0x1003865e  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10038664  mov     esi, _isibHead
0x1003866a  cmp     esi, 0FFFFFFFFh
0x1003866d  jz      short loc_10038686
0x1003866f  nop
0x10038670  imul    eax, esi, 68h ; 'h'
0x10038673  cmp     _rgsib[eax], edi
0x10038679  jz      short loc_100386AE
0x1003867b  mov     esi, dword_1016EB88[eax]
0x10038681  cmp     esi, 0FFFFFFFFh
0x10038684  jnz     short loc_10038670
0x10038686  push    _critJet; lpCriticalSection
0x1003868c  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10038692  mov     eax, 0FFFFFBB0h
0x10038697  pop     edi
0x10038698  pop     esi
0x10038699  pop     ebx
0x1003869a  mov     ecx, [esp+244h+var_4]
0x100386a1  xor     ecx, esp; StackCookie
0x100386a3  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100386a8  mov     esp, ebp
0x100386aa  pop     ebp
0x100386ab  retn    0Ch
0x100386ae  push    edi
0x100386af  call    _ClearErrorInfo@4; ClearErrorInfo(x)
0x100386b4  imul    eax, esi, 68h ; 'h'
0x100386b7  mov     eax, dword_1016EB70[eax]
0x100386bd  lea     eax, [eax+eax*4]
0x100386c0  mov     ebx, dword ptr (_rgiscb+0Ch)[eax*4]
0x100386c7  mov     [esp+250h+var_228], ebx
0x100386cb  cmp     ebx, 0FFFFFFFFh
0x100386ce  jnz     short loc_100386F8
0x100386d0  push    _critJet; lpCriticalSection
0x100386d6  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100386dc  mov     eax, 0FFFFF8F6h
0x100386e1  pop     edi
0x100386e2  pop     esi
0x100386e3  pop     ebx
0x100386e4  mov     ecx, [esp+244h+var_4]
0x100386eb  xor     ecx, esp; StackCookie
0x100386ed  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100386f2  mov     esp, ebp
0x100386f4  pop     ebp
0x100386f5  retn    0Ch
0x100386f8  lea     eax, [esp+250h+var_22C]
0x100386fc  push    eax
0x100386fd  push    offset _wszSgTable; "MSysGroups"
0x10038702  push    offset _wszTcObject; "Tables"
0x10038707  push    ebx
0x10038708  push    edi
0x10038709  call    _ErrDispGetObjidFromName@20; ErrDispGetObjidFromName(x,x,x,x,x)
0x1003870e  mov     esi, eax
0x10038710  test    esi, esi
0x10038712  js      loc_100388D8
0x10038718  mov     eax, _mpdbidiiscb[ebx*4]
0x1003871f  lea     eax, [eax+eax*4]
0x10038722  mov     eax, Src[eax*4]
0x10038729  test    eax, eax
0x1003872b  jnz     short loc_10038757
0x1003872d  push    _critJet; lpCriticalSection
0x10038733  mov     esi, 0FFFFFC17h
0x10038738  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1003873e  mov     eax, esi
0x10038740  pop     edi
0x10038741  pop     esi
0x10038742  pop     ebx
0x10038743  mov     ecx, [esp+244h+var_4]
0x1003874a  xor     ecx, esp; StackCookie
0x1003874c  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10038751  mov     esp, ebp
0x10038753  pop     ebp
0x10038754  retn    0Ch
0x10038757  push    0
0x10038759  lea     ecx, [esp+254h+var_240]
0x1003875d  mov     edx, ebx
0x1003875f  push    ecx
0x10038760  push    0
0x10038762  push    eax
0x10038763  push    [esp+260h+var_22C]
0x10038767  mov     ecx, edi
0x10038769  call    _ErrSecCollectAccess@28; ErrSecCollectAccess(x,x,x,x,x,x,x)
0x1003876e  mov     esi, eax
0x10038770  test    esi, esi
0x10038772  js      loc_100388D8
0x10038778  test    byte ptr [esp+250h+var_240], 80h
0x1003877d  jnz     short loc_100387C0
0x1003877f  push    0; int
0x10038781  push    0; int
0x10038783  push    0; int
0x10038785  push    0FFFFE04Eh; int
0x1003878a  push    0; void *
0x1003878c  push    0; void *
0x1003878e  push    [esp+268h+Src]; Src
0x10038792  push    edi; int
0x10038793  call    _UtilSetErrorInfoReal@32; UtilSetErrorInfoReal(x,x,x,x,x,x,x,x)
0x10038798  push    _critJet; lpCriticalSection
0x1003879e  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100387a4  mov     eax, 0FFFFF88Dh
0x100387a9  pop     edi
0x100387aa  pop     esi
0x100387ab  pop     ebx
0x100387ac  mov     ecx, [esp+244h+var_4]
0x100387b3  xor     ecx, esp; StackCookie
0x100387b5  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100387ba  mov     esp, ebp
0x100387bc  pop     ebp
0x100387bd  retn    0Ch
0x100387c0  lea     eax, [esp+250h+var_240]
0x100387c4  push    eax; int
0x100387c5  lea     eax, [esp+254h+var_238]
0x100387c9  push    eax; int
0x100387ca  push    80h; Size
0x100387cf  lea     eax, [esp+25Ch+var_208]
0x100387d3  push    eax; int
0x100387d4  push    [esp+260h+Src]; Src
0x100387d8  push    0FFFFFFFFh; int
0x100387da  push    edi; int
0x100387db  call    _ErrSecGetSidFromName@28; ErrSecGetSidFromName(x,x,x,x,x,x,x)
0x100387e0  mov     esi, eax
0x100387e2  test    esi, esi
0x100387e4  js      loc_100388D8
0x100387ea  cmp     [esp+250h+var_240], 0
0x100387ef  jnz     short loc_10038819
0x100387f1  push    _critJet; lpCriticalSection
0x100387f7  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100387fd  mov     eax, 0FFFFF890h
0x10038802  pop     edi
0x10038803  pop     esi
0x10038804  pop     ebx
0x10038805  mov     ecx, [esp+244h+var_4]
0x1003880c  xor     ecx, esp; StackCookie
0x1003880e  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10038813  mov     esp, ebp
0x10038815  pop     ebp
0x10038816  retn    0Ch
0x10038819  mov     eax, [esp+250h+var_238]
0x1003881d  mov     [esp+250h+Src], eax
0x10038821  lea     eax, [esp+250h+var_240]
0x10038825  push    eax; int
0x10038826  lea     eax, [esp+254h+var_238]
0x1003882a  push    eax; int
0x1003882b  push    80h; Size
0x10038830  lea     eax, [esp+25Ch+var_188]
0x10038837  push    eax; int
0x10038838  push    [esp+260h+var_234]; Src
0x1003883c  push    0FFFFFFFFh; int
0x1003883e  push    edi; int
0x1003883f  call    _ErrSecGetSidFromName@28; ErrSecGetSidFromName(x,x,x,x,x,x,x)
0x10038844  mov     esi, eax
0x10038846  test    esi, esi
0x10038848  js      loc_100388D8
0x1003884e  cmp     [esp+250h+var_240], 0
0x10038853  jnz     short loc_100387F1
0x10038855  cmp     [esp+250h+var_208], 1
0x1003885a  mov     eax, [esp+250h+var_238]
0x1003885e  mov     [esp+250h+var_240], eax
0x10038862  jnz     short loc_100388AE
0x10038864  mov     esi, [esp+250h+Src]
0x10038868  lea     eax, [esp+250h+var_234]
0x1003886c  push    eax
0x1003886d  push    esi
0x1003886e  lea     edx, [esp+258h+var_208]
0x10038872  mov     ecx, edi
0x10038874  call    _ErrSecGetNumMembers@16; ErrSecGetNumMembers(x,x,x,x)
0x10038879  mov     esi, eax
0x1003887b  test    esi, esi
0x1003887d  js      short loc_100388D8
0x1003887f  cmp     [esp+250h+var_234], 1
0x10038884  jnz     short loc_100388AE
0x10038886  push    _critJet; lpCriticalSection
0x1003888c  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10038892  mov     eax, 0FFFFF88Eh
0x10038897  pop     edi
0x10038898  pop     esi
0x10038899  pop     ebx
0x1003889a  mov     ecx, [esp+244h+var_4]
0x100388a1  xor     ecx, esp; StackCookie
0x100388a3  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100388a8  mov     esp, ebp
0x100388aa  pop     ebp
0x100388ab  retn    0Ch
0x100388ae  push    80000000h
0x100388b3  push    offset _wszSgTable; "MSysGroups"
0x100388b8  lea     eax, [esp+258h+var_244]
0x100388bc  push    eax
0x100388bd  push    ebx
0x100388be  push    edi
0x100388bf  call    _ErrDispOpenTable@20; ErrDispOpenTable(x,x,x,x,x)
0x100388c4  mov     esi, eax
0x100388c6  test    esi, esi
0x100388c8  jns     short loc_100388FD
0x100388ca  cmp     esi, 0FFFFFAE7h
0x100388d0  mov     eax, 0FFFFF88Bh
0x100388d5  cmovz   esi, eax
0x100388d8  push    _critJet; lpCriticalSection
0x100388de  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100388e4  mov     eax, esi
0x100388e6  pop     edi
0x100388e7  pop     esi
0x100388e8  pop     ebx
0x100388e9  mov     ecx, [esp+244h+var_4]
0x100388f0  xor     ecx, esp; StackCookie
0x100388f2  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100388f7  mov     esp, ebp
0x100388f9  pop     ebp
0x100388fa  retn    0Ch
0x100388fd  push    offset _wszSgGroupIndex; "GroupSID"
0x10038902  push    [esp+254h+var_244]
0x10038906  push    edi
0x10038907  call    _ErrDispSetCurrentIndex@12; ErrDispSetCurrentIndex(x,x,x)
0x1003890c  mov     esi, eax
0x1003890e  test    esi, esi
0x10038910  js      loc_10038ACD
0x10038916  push    0
0x10038918  push    18h
0x1003891a  lea     eax, [esp+258h+var_220]
0x1003891e  push    eax
0x1003891f  push    offset _wszSgUserSidColumn; "UserSID"
0x10038924  push    [esp+260h+var_244]
0x10038928  push    edi
0x10038929  call    _ErrDispGetTableColumnInfo@24; ErrDispGetTableColumnInfo(x,x,x,x,x,x)
0x1003892e  mov     esi, eax
0x10038930  test    esi, esi
0x10038932  js      loc_10038ACD
0x10038938  mov     ebx, [esp+250h+Src]
0x1003893c  lea     eax, [esp+250h+var_208]
0x10038940  push    1
0x10038942  push    ebx
0x10038943  push    eax
0x10038944  push    [esp+25Ch+var_244]
0x10038948  push    edi
0x10038949  call    _ErrDispMakeKey@20; ErrDispMakeKey(x,x,x,x,x)
0x1003894e  mov     esi, eax
0x10038950  test    esi, esi
0x10038952  js      loc_10038ACD
0x10038958  push    1
0x1003895a  push    [esp+254h+var_244]
0x1003895e  push    edi
0x1003895f  call    _ErrDispSeek@12; ErrDispSeek(x,x,x)
0x10038964  mov     esi, eax
0x10038966  cmp     esi, 0FFFFF9BFh
0x1003896c  jz      short loc_100389A0
0x1003896e  test    esi, esi
0x10038970  js      loc_10038ACD
0x10038976  push    1
0x10038978  push    ebx
0x10038979  lea     eax, [esp+258h+var_208]
0x1003897d  push    eax
0x1003897e  push    [esp+25Ch+var_244]
0x10038982  push    edi
0x10038983  call    _ErrDispMakeKey@20; ErrDispMakeKey(x,x,x,x,x)
0x10038988  mov     esi, eax
0x1003898a  test    esi, esi
0x1003898c  js      loc_10038ACD
0x10038992  push    3
0x10038994  push    [esp+254h+var_244]
0x10038998  push    edi
0x10038999  call    _ErrDispSetIndexRange@12; ErrDispSetIndexRange(x,x,x)
0x1003899e  mov     esi, eax
0x100389a0  test    esi, esi
0x100389a2  js      loc_10038AB1
0x100389a8  mov     ebx, [esp+250h+var_240]
0x100389ac  nop     dword ptr [eax+00h]
0x100389b0  mov     edx, [esp+250h+var_244]
0x100389b4  cmp     edx, 800h
0x100389ba  jnb     loc_10038AFC
0x100389c0  cmp     edx, _tableidInit
0x100389c6  jb      loc_10038AFC
0x100389cc  shl     edx, 4
0x100389cf  mov     ecx, edi
0x100389d1  push    0
0x100389d3  push    0
0x100389d5  mov     eax, _rgvtdef[edx]
0x100389db  cmp     eax, 0FFFFFFFFh
0x100389de  mov     esi, dword_101636CC[edx]
0x100389e4  cmovnz  ecx, eax
0x100389e7  lea     eax, [esp+258h+var_238]
0x100389eb  push    eax
0x100389ec  push    80h
0x100389f1  mov     esi, [esi+8Ch]
0x100389f7  lea     eax, [esp+260h+var_108]
0x100389fe  push    eax
  ... truncated ...
```
