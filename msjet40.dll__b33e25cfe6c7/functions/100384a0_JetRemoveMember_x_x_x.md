# JetRemoveMember(x,x,x)

- ea: `0x100384a0`
- end: `0x10038a28`
- name: `_JetRemoveMember@12`
- size: `1416`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, installer_update`

## callers

- `0x100cf9f4`

## callees

- `0x100292b0`
- `0x100384a0`
- `0x10039c00`
- `0x1003c760`
- `0x1003c820`
- `0x1003c9b0`
- `0x1003d0e0`
- `0x1003d8d0`
- `0x1003d9f0`
- `0x1003e820`
- `0x1003e870`
- `0x10043090`
- `0x10043260`
- `0x10043840`
- `0x10043bb0`
- `0x100440c0`
- `0x10044460`
- `0x10044b20`
- `0x10044b90`
- `0x10044d90`
- `0x10050000`
- `0x10122f60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1003850c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10038556`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100385b8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1003861e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10038677`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1003870c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1003875e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1003895d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10038a09`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1003850c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10038556`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100385b8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1003861e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10038677`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1003870c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1003875e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1003895d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10038a09`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x100384de`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x100384de`

## string_xrefs

- `0x1003879f`: `UserSID`
- `0x1003877d`: `GroupSID`

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
    v3 = dword_1016EAE8[26 * v3];
    if ( v3 == -1 )
      goto LABEL_4;
  }
  ClearErrorInfo(a1);
  v5 = (int)*(&rgiscb + 5 * dword_1016EAD0[26 * v3] + 3);
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
    UtilSetErrorInfoReal(a1, (const unsigned __int16 *)Src, 0, 0, -8114, 0, 0, 0);
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
      TableColumnInfo = (*(int (__thiscall **)(_DWORD, int, int, int, _BYTE *, int, int *, _DWORD, _DWORD))(dword_1016362C[4 * v17] + 140))(
                          *(_DWORD *)(dword_1016362C[4 * v17] + 140),
                          v12,
                          dword_10163624[4 * v17],
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
      TableColumnInfo = (*(int (__thiscall **)(_DWORD, int, int, int, _DWORD))(dword_1016362C[4 * v17] + 104))(
                          *(_DWORD *)(dword_1016362C[4 * v17] + 104),
                          v14,
                          dword_10163624[4 * v17],
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
0x100384a0  mov     edi, edi
0x100384a2  push    ebp
0x100384a3  mov     ebp, esp
0x100384a5  and     esp, 0FFFFFFF8h
0x100384a8  sub     esp, 244h
0x100384ae  mov     eax, ___security_cookie
0x100384b3  xor     eax, esp
0x100384b5  mov     [esp+244h+var_4], eax
0x100384bc  mov     eax, [ebp+arg_4]
0x100384bf  push    ebx
0x100384c0  push    esi
0x100384c1  push    edi
0x100384c2  push    _critJet; lpCriticalSection
0x100384c8  mov     edi, [ebp+arg_0]
0x100384cb  mov     [esp+254h+Src], eax
0x100384cf  mov     eax, [ebp+arg_8]
0x100384d2  mov     [esp+254h+var_234], eax
0x100384d6  mov     [esp+254h+var_230], 0
0x100384de  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x100384e4  mov     esi, _isibHead
0x100384ea  cmp     esi, 0FFFFFFFFh
0x100384ed  jz      short loc_10038506
0x100384ef  nop
0x100384f0  imul    eax, esi, 68h ; 'h'
0x100384f3  cmp     _rgsib[eax], edi
0x100384f9  jz      short loc_1003852E
0x100384fb  mov     esi, dword_1016EAE8[eax]
0x10038501  cmp     esi, 0FFFFFFFFh
0x10038504  jnz     short loc_100384F0
0x10038506  push    _critJet; lpCriticalSection
0x1003850c  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10038512  mov     eax, 0FFFFFBB0h
0x10038517  pop     edi
0x10038518  pop     esi
0x10038519  pop     ebx
0x1003851a  mov     ecx, [esp+244h+var_4]
0x10038521  xor     ecx, esp; StackCookie
0x10038523  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10038528  mov     esp, ebp
0x1003852a  pop     ebp
0x1003852b  retn    0Ch
0x1003852e  push    edi
0x1003852f  call    _ClearErrorInfo@4; ClearErrorInfo(x)
0x10038534  imul    eax, esi, 68h ; 'h'
0x10038537  mov     eax, dword_1016EAD0[eax]
0x1003853d  lea     eax, [eax+eax*4]
0x10038540  mov     ebx, dword ptr (_rgiscb+0Ch)[eax*4]
0x10038547  mov     [esp+250h+var_228], ebx
0x1003854b  cmp     ebx, 0FFFFFFFFh
0x1003854e  jnz     short loc_10038578
0x10038550  push    _critJet; lpCriticalSection
0x10038556  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1003855c  mov     eax, 0FFFFF8F6h
0x10038561  pop     edi
0x10038562  pop     esi
0x10038563  pop     ebx
0x10038564  mov     ecx, [esp+244h+var_4]
0x1003856b  xor     ecx, esp; StackCookie
0x1003856d  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10038572  mov     esp, ebp
0x10038574  pop     ebp
0x10038575  retn    0Ch
0x10038578  lea     eax, [esp+250h+var_22C]
0x1003857c  push    eax
0x1003857d  push    offset _wszSgTable; "MSysGroups"
0x10038582  push    offset _wszTcObject; "Tables"
0x10038587  push    ebx
0x10038588  push    edi
0x10038589  call    _ErrDispGetObjidFromName@20; ErrDispGetObjidFromName(x,x,x,x,x)
0x1003858e  mov     esi, eax
0x10038590  test    esi, esi
0x10038592  js      loc_10038758
0x10038598  mov     eax, _mpdbidiiscb[ebx*4]
0x1003859f  lea     eax, [eax+eax*4]
0x100385a2  mov     eax, Src[eax*4]
0x100385a9  test    eax, eax
0x100385ab  jnz     short loc_100385D7
0x100385ad  push    _critJet; lpCriticalSection
0x100385b3  mov     esi, 0FFFFFC17h
0x100385b8  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100385be  mov     eax, esi
0x100385c0  pop     edi
0x100385c1  pop     esi
0x100385c2  pop     ebx
0x100385c3  mov     ecx, [esp+244h+var_4]
0x100385ca  xor     ecx, esp; StackCookie
0x100385cc  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100385d1  mov     esp, ebp
0x100385d3  pop     ebp
0x100385d4  retn    0Ch
0x100385d7  push    0
0x100385d9  lea     ecx, [esp+254h+var_240]
0x100385dd  mov     edx, ebx
0x100385df  push    ecx
0x100385e0  push    0
0x100385e2  push    eax
0x100385e3  push    [esp+260h+var_22C]
0x100385e7  mov     ecx, edi
0x100385e9  call    _ErrSecCollectAccess@28; ErrSecCollectAccess(x,x,x,x,x,x,x)
0x100385ee  mov     esi, eax
0x100385f0  test    esi, esi
0x100385f2  js      loc_10038758
0x100385f8  test    byte ptr [esp+250h+var_240], 80h
0x100385fd  jnz     short loc_10038640
0x100385ff  push    0; int
0x10038601  push    0; int
0x10038603  push    0; int
0x10038605  push    0FFFFE04Eh; int
0x1003860a  push    0; void *
0x1003860c  push    0; void *
0x1003860e  push    [esp+268h+Src]; Src
0x10038612  push    edi; int
0x10038613  call    _UtilSetErrorInfoReal@32; UtilSetErrorInfoReal(x,x,x,x,x,x,x,x)
0x10038618  push    _critJet; lpCriticalSection
0x1003861e  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10038624  mov     eax, 0FFFFF88Dh
0x10038629  pop     edi
0x1003862a  pop     esi
0x1003862b  pop     ebx
0x1003862c  mov     ecx, [esp+244h+var_4]
0x10038633  xor     ecx, esp; StackCookie
0x10038635  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1003863a  mov     esp, ebp
0x1003863c  pop     ebp
0x1003863d  retn    0Ch
0x10038640  lea     eax, [esp+250h+var_240]
0x10038644  push    eax; int
0x10038645  lea     eax, [esp+254h+var_238]
0x10038649  push    eax; int
0x1003864a  push    80h; Size
0x1003864f  lea     eax, [esp+25Ch+var_208]
0x10038653  push    eax; int
0x10038654  push    [esp+260h+Src]; Src
0x10038658  push    0FFFFFFFFh; int
0x1003865a  push    edi; int
0x1003865b  call    _ErrSecGetSidFromName@28; ErrSecGetSidFromName(x,x,x,x,x,x,x)
0x10038660  mov     esi, eax
0x10038662  test    esi, esi
0x10038664  js      loc_10038758
0x1003866a  cmp     [esp+250h+var_240], 0
0x1003866f  jnz     short loc_10038699
0x10038671  push    _critJet; lpCriticalSection
0x10038677  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1003867d  mov     eax, 0FFFFF890h
0x10038682  pop     edi
0x10038683  pop     esi
0x10038684  pop     ebx
0x10038685  mov     ecx, [esp+244h+var_4]
0x1003868c  xor     ecx, esp; StackCookie
0x1003868e  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10038693  mov     esp, ebp
0x10038695  pop     ebp
0x10038696  retn    0Ch
0x10038699  mov     eax, [esp+250h+var_238]
0x1003869d  mov     [esp+250h+Src], eax
0x100386a1  lea     eax, [esp+250h+var_240]
0x100386a5  push    eax; int
0x100386a6  lea     eax, [esp+254h+var_238]
0x100386aa  push    eax; int
0x100386ab  push    80h; Size
0x100386b0  lea     eax, [esp+25Ch+var_188]
0x100386b7  push    eax; int
0x100386b8  push    [esp+260h+var_234]; Src
0x100386bc  push    0FFFFFFFFh; int
0x100386be  push    edi; int
0x100386bf  call    _ErrSecGetSidFromName@28; ErrSecGetSidFromName(x,x,x,x,x,x,x)
0x100386c4  mov     esi, eax
0x100386c6  test    esi, esi
0x100386c8  js      loc_10038758
0x100386ce  cmp     [esp+250h+var_240], 0
0x100386d3  jnz     short loc_10038671
0x100386d5  cmp     [esp+250h+var_208], 1
0x100386da  mov     eax, [esp+250h+var_238]
0x100386de  mov     [esp+250h+var_240], eax
0x100386e2  jnz     short loc_1003872E
0x100386e4  mov     esi, [esp+250h+Src]
0x100386e8  lea     eax, [esp+250h+var_234]
0x100386ec  push    eax
0x100386ed  push    esi
0x100386ee  lea     edx, [esp+258h+var_208]
0x100386f2  mov     ecx, edi
0x100386f4  call    _ErrSecGetNumMembers@16; ErrSecGetNumMembers(x,x,x,x)
0x100386f9  mov     esi, eax
0x100386fb  test    esi, esi
0x100386fd  js      short loc_10038758
0x100386ff  cmp     [esp+250h+var_234], 1
0x10038704  jnz     short loc_1003872E
0x10038706  push    _critJet; lpCriticalSection
0x1003870c  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10038712  mov     eax, 0FFFFF88Eh
0x10038717  pop     edi
0x10038718  pop     esi
0x10038719  pop     ebx
0x1003871a  mov     ecx, [esp+244h+var_4]
0x10038721  xor     ecx, esp; StackCookie
0x10038723  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10038728  mov     esp, ebp
0x1003872a  pop     ebp
0x1003872b  retn    0Ch
0x1003872e  push    80000000h
0x10038733  push    offset _wszSgTable; "MSysGroups"
0x10038738  lea     eax, [esp+258h+var_244]
0x1003873c  push    eax
0x1003873d  push    ebx
0x1003873e  push    edi
0x1003873f  call    _ErrDispOpenTable@20; ErrDispOpenTable(x,x,x,x,x)
0x10038744  mov     esi, eax
0x10038746  test    esi, esi
0x10038748  jns     short loc_1003877D
0x1003874a  cmp     esi, 0FFFFFAE7h
0x10038750  mov     eax, 0FFFFF88Bh
0x10038755  cmovz   esi, eax
0x10038758  push    _critJet; lpCriticalSection
0x1003875e  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10038764  mov     eax, esi
0x10038766  pop     edi
0x10038767  pop     esi
0x10038768  pop     ebx
0x10038769  mov     ecx, [esp+244h+var_4]
0x10038770  xor     ecx, esp; StackCookie
0x10038772  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10038777  mov     esp, ebp
0x10038779  pop     ebp
0x1003877a  retn    0Ch
0x1003877d  push    offset _wszSgGroupIndex; "GroupSID"
0x10038782  push    [esp+254h+var_244]
0x10038786  push    edi
0x10038787  call    _ErrDispSetCurrentIndex@12; ErrDispSetCurrentIndex(x,x,x)
0x1003878c  mov     esi, eax
0x1003878e  test    esi, esi
0x10038790  js      loc_1003894D
0x10038796  push    0
0x10038798  push    18h
0x1003879a  lea     eax, [esp+258h+var_220]
0x1003879e  push    eax
0x1003879f  push    offset _wszSgUserSidColumn; "UserSID"
0x100387a4  push    [esp+260h+var_244]
0x100387a8  push    edi
0x100387a9  call    _ErrDispGetTableColumnInfo@24; ErrDispGetTableColumnInfo(x,x,x,x,x,x)
0x100387ae  mov     esi, eax
0x100387b0  test    esi, esi
0x100387b2  js      loc_1003894D
0x100387b8  mov     ebx, [esp+250h+Src]
0x100387bc  lea     eax, [esp+250h+var_208]
0x100387c0  push    1
0x100387c2  push    ebx
0x100387c3  push    eax
0x100387c4  push    [esp+25Ch+var_244]
0x100387c8  push    edi
0x100387c9  call    _ErrDispMakeKey@20; ErrDispMakeKey(x,x,x,x,x)
0x100387ce  mov     esi, eax
0x100387d0  test    esi, esi
0x100387d2  js      loc_1003894D
0x100387d8  push    1
0x100387da  push    [esp+254h+var_244]
0x100387de  push    edi
0x100387df  call    _ErrDispSeek@12; ErrDispSeek(x,x,x)
0x100387e4  mov     esi, eax
0x100387e6  cmp     esi, 0FFFFF9BFh
0x100387ec  jz      short loc_10038820
0x100387ee  test    esi, esi
0x100387f0  js      loc_1003894D
0x100387f6  push    1
0x100387f8  push    ebx
0x100387f9  lea     eax, [esp+258h+var_208]
0x100387fd  push    eax
0x100387fe  push    [esp+25Ch+var_244]
0x10038802  push    edi
0x10038803  call    _ErrDispMakeKey@20; ErrDispMakeKey(x,x,x,x,x)
0x10038808  mov     esi, eax
0x1003880a  test    esi, esi
0x1003880c  js      loc_1003894D
0x10038812  push    3
0x10038814  push    [esp+254h+var_244]
0x10038818  push    edi
0x10038819  call    _ErrDispSetIndexRange@12; ErrDispSetIndexRange(x,x,x)
0x1003881e  mov     esi, eax
0x10038820  test    esi, esi
0x10038822  js      loc_10038931
0x10038828  mov     ebx, [esp+250h+var_240]
0x1003882c  nop     dword ptr [eax+00h]
0x10038830  mov     edx, [esp+250h+var_244]
0x10038834  cmp     edx, 800h
0x1003883a  jnb     loc_1003897C
0x10038840  cmp     edx, _tableidInit
0x10038846  jb      loc_1003897C
0x1003884c  shl     edx, 4
0x1003884f  mov     ecx, edi
0x10038851  push    0
0x10038853  push    0
0x10038855  mov     eax, _rgvtdef[edx]
0x1003885b  cmp     eax, 0FFFFFFFFh
0x1003885e  mov     esi, dword_1016362C[edx]
0x10038864  cmovnz  ecx, eax
0x10038867  lea     eax, [esp+258h+var_238]
0x1003886b  push    eax
0x1003886c  push    80h
0x10038871  mov     esi, [esi+8Ch]
0x10038877  lea     eax, [esp+260h+var_108]
0x1003887e  push    eax
  ... truncated ...
```
