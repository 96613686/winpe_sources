# JetAddMember(x,x,x)

- ea: `0x100381b0`
- end: `0x1003860f`
- name: `_JetAddMember@12`
- size: `1119`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, installer_update`

## callers

- `0x100cfb84`

## callees

- `0x10029480`
- `0x100294c0`
- `0x100381b0`
- `0x10039d80`
- `0x1003c770`
- `0x1003c8e0`
- `0x1003cc90`
- `0x1003db70`
- `0x1003e9b0`
- `0x1003ea00`
- `0x10043220`
- `0x100433f0`
- `0x100437f0`
- `0x100439d0`
- `0x10044240`
- `0x10044d80`
- `0x10044f80`
- `0x10123110`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1003844f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1003844f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1003821c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10038262`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100382a6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10038324`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10038380`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100383e1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10038490`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100385c1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100385f0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1003821c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10038262`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100382a6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10038324`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10038380`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100383e1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10038490`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100385c1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100385f0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x100381e6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x100381e6`

## string_xrefs

- `0x100384ce`: `UserSID`
- `0x10038515`: `GroupSID`

## pseudocode

```c
int __stdcall JetAddMember(int a1, void *a2, void *a3)
{
  int v3; // edi
  int v5; // edi
  int ObjidFromName; // ebx
  int v7; // eax
  BOOL v8; // ebx
  int appended; // edi
  int TableColumnInfo; // edi
  size_t v11; // ebx
  int v12; // [esp+Ch] [ebp-13Ch] BYREF
  size_t Size; // [esp+10h] [ebp-138h] BYREF
  int v14; // [esp+14h] [ebp-134h] BYREF
  void *Block; // [esp+18h] [ebp-130h] BYREF
  size_t v16; // [esp+1Ch] [ebp-12Ch] BYREF
  int v17; // [esp+20h] [ebp-128h] BYREF
  void *Src; // [esp+24h] [ebp-124h]
  _BYTE v19[4]; // [esp+28h] [ebp-120h] BYREF
  int v20; // [esp+2Ch] [ebp-11Ch]
  int v21[32]; // [esp+40h] [ebp-108h] BYREF
  int v22[33]; // [esp+C0h] [ebp-88h] BYREF

  Block = a2;
  Src = a3;
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
  if ( v5 == -1 )
  {
    LeaveCriticalSection(critJet);
    return -1802;
  }
  ObjidFromName = ErrDispGetObjidFromName(a1, v5, L"Tables", L"MSysGroups", &v17);
  if ( ObjidFromName < 0 )
    goto LABEL_8;
  v7 = (int)*(&::Src + 5 * mpdbidiiscb[v5]);
  if ( !v7 )
  {
    ObjidFromName = -1001;
LABEL_8:
    LeaveCriticalSection(critJet);
    return ObjidFromName;
  }
  ObjidFromName = ErrSecCollectAccess(v17, v7, 0, &Size, 0);
  if ( ObjidFromName < 0 )
    goto LABEL_8;
  if ( (Size & 0x20) == 0 )
  {
    UtilSetErrorInfoReal(a1, Block, 0, 0, -8170, 0, 0, 0);
    LeaveCriticalSection(critJet);
    return -1907;
  }
  ObjidFromName = ErrSecGetSidFromName(a1, -1, Block, (int)v22, 0x80u, (int)&v16, (int)&v14);
  if ( ObjidFromName < 0 )
    goto LABEL_8;
  if ( !v14 )
  {
    LeaveCriticalSection(critJet);
    return -1904;
  }
  Size = v16;
  ObjidFromName = ErrSecGetSidFromName(a1, -1, Src, (int)v21, 0x80u, (int)&v16, (int)&v14);
  if ( ObjidFromName < 0 )
    goto LABEL_8;
  if ( v14 )
    goto LABEL_19;
  v14 = v16;
  ObjidFromName = ErrSecBuildUserToken(a1, -1, (int)v21, v16, &Block);
  if ( ObjidFromName < 0 )
    goto LABEL_8;
  v8 = SecIndexOfTokenSid(Size) != -1;
  if ( Block )
    _free(Block);
  if ( v8 )
  {
LABEL_19:
    LeaveCriticalSection(critJet);
    return -1906;
  }
  appended = ErrDispOpenTable(a1, v5, &v12, L"MSysGroups", 0x80000000);
  if ( appended < 0 )
  {
    if ( appended == -1305 )
      appended = -1909;
    goto LABEL_27;
  }
  TableColumnInfo = ErrDispPrepareUpdate2(a1, v12, 0);
  if ( TableColumnInfo < 0
    || (TableColumnInfo = ErrDispGetTableColumnInfo(a1, v12, L"UserSID", v19, 24, 0), TableColumnInfo < 0)
    || (TableColumnInfo = ErrDispSetColumn(a1, v12, v20, v21, v14, 0, 0), TableColumnInfo < 0)
    || (TableColumnInfo = ErrDispGetTableColumnInfo(a1, v12, L"GroupSID", v19, 24, 0), TableColumnInfo < 0)
    || (v11 = Size, TableColumnInfo = ErrDispSetColumn(a1, v12, v20, v22, Size, 0, 0), TableColumnInfo < 0)
    || (TableColumnInfo = ErrDispUpdate(a1, v12, 0, 0, 0), TableColumnInfo < 0) )
  {
    ErrDispCloseTable(a1, v12);
    LeaveCriticalSection(critJet);
    return TableColumnInfo;
  }
  else
  {
    ErrDispCloseTable(a1, v12);
    Size = UtilGetpUserTokenOfSesidIscb(a1);
    if ( !SecIndexOfTokenSid(v14) )
    {
      appended = ErrSecAppendSidToToken(v11);
      if ( appended < 0 )
      {
LABEL_27:
        LeaveCriticalSection(critJet);
        return appended;
      }
      UtilSetpUserTokenOfSesidIscb(a1, Size);
    }
    LeaveCriticalSection(critJet);
    return 0;
  }
}

```

## disassembly

```asm
0x100381b0  mov     edi, edi
0x100381b2  push    ebp
0x100381b3  mov     ebp, esp
0x100381b5  and     esp, 0FFFFFFF8h
0x100381b8  sub     esp, 13Ch
0x100381be  mov     eax, ___security_cookie
0x100381c3  xor     eax, esp
0x100381c5  mov     [esp+13Ch+var_4], eax
0x100381cc  mov     eax, [ebp+arg_4]
0x100381cf  push    ebx
0x100381d0  push    esi
0x100381d1  mov     esi, [ebp+arg_0]
0x100381d4  push    edi
0x100381d5  push    _critJet; lpCriticalSection
0x100381db  mov     [esp+14Ch+Block], eax
0x100381df  mov     eax, [ebp+arg_8]
0x100381e2  mov     [esp+14Ch+Src], eax
0x100381e6  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x100381ec  mov     edi, _isibHead
0x100381f2  cmp     edi, 0FFFFFFFFh
0x100381f5  jz      short loc_10038216
0x100381f7  nop     word ptr [eax+eax+00000000h]
0x10038200  imul    eax, edi, 68h ; 'h'
0x10038203  cmp     _rgsib[eax], esi
0x10038209  jz      short loc_1003823E
0x1003820b  mov     edi, dword_1016EB88[eax]
0x10038211  cmp     edi, 0FFFFFFFFh
0x10038214  jnz     short loc_10038200
0x10038216  push    _critJet; lpCriticalSection
0x1003821c  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10038222  mov     eax, 0FFFFFBB0h
0x10038227  pop     edi
0x10038228  pop     esi
0x10038229  pop     ebx
0x1003822a  mov     ecx, [esp+13Ch+var_4]
0x10038231  xor     ecx, esp; StackCookie
0x10038233  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10038238  mov     esp, ebp
0x1003823a  pop     ebp
0x1003823b  retn    0Ch
0x1003823e  push    esi
0x1003823f  call    _ClearErrorInfo@4; ClearErrorInfo(x)
0x10038244  imul    eax, edi, 68h ; 'h'
0x10038247  mov     eax, dword_1016EB70[eax]
0x1003824d  lea     eax, [eax+eax*4]
0x10038250  mov     edi, dword ptr (_rgiscb+0Ch)[eax*4]
0x10038257  cmp     edi, 0FFFFFFFFh
0x1003825a  jnz     short loc_10038284
0x1003825c  push    _critJet; lpCriticalSection
0x10038262  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10038268  mov     eax, 0FFFFF8F6h
0x1003826d  pop     edi
0x1003826e  pop     esi
0x1003826f  pop     ebx
0x10038270  mov     ecx, [esp+13Ch+var_4]
0x10038277  xor     ecx, esp; StackCookie
0x10038279  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1003827e  mov     esp, ebp
0x10038280  pop     ebp
0x10038281  retn    0Ch
0x10038284  lea     eax, [esp+148h+var_128]
0x10038288  push    eax
0x10038289  push    offset _wszSgTable; "MSysGroups"
0x1003828e  push    offset _wszTcObject; "Tables"
0x10038293  push    edi
0x10038294  push    esi
0x10038295  call    _ErrDispGetObjidFromName@20; ErrDispGetObjidFromName(x,x,x,x,x)
0x1003829a  mov     ebx, eax
0x1003829c  test    ebx, ebx
0x1003829e  jns     short loc_100382C5
0x100382a0  push    _critJet; lpCriticalSection
0x100382a6  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100382ac  mov     eax, ebx
0x100382ae  pop     edi
0x100382af  pop     esi
0x100382b0  pop     ebx
0x100382b1  mov     ecx, [esp+13Ch+var_4]
0x100382b8  xor     ecx, esp; StackCookie
0x100382ba  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100382bf  mov     esp, ebp
0x100382c1  pop     ebp
0x100382c2  retn    0Ch
0x100382c5  mov     eax, _mpdbidiiscb[edi*4]
0x100382cc  lea     eax, [eax+eax*4]
0x100382cf  mov     eax, Src[eax*4]
0x100382d6  test    eax, eax
0x100382d8  jnz     short loc_100382E1
0x100382da  mov     ebx, 0FFFFFC17h
0x100382df  jmp     short loc_100382A0
0x100382e1  push    0
0x100382e3  lea     ecx, [esp+14Ch+Size]
0x100382e7  mov     edx, edi
0x100382e9  push    ecx
0x100382ea  push    0
0x100382ec  push    eax
0x100382ed  push    [esp+158h+var_128]
0x100382f1  mov     ecx, esi
0x100382f3  call    _ErrSecCollectAccess@28; ErrSecCollectAccess(x,x,x,x,x,x,x)
0x100382f8  mov     ebx, eax
0x100382fa  test    ebx, ebx
0x100382fc  js      short loc_100382A0
0x100382fe  test    byte ptr [esp+148h+Size], 20h
0x10038303  jnz     short loc_10038346
0x10038305  push    0; int
0x10038307  push    0; int
0x10038309  push    0; int
0x1003830b  push    0FFFFE016h; int
0x10038310  push    0; void *
0x10038312  push    0; void *
0x10038314  push    [esp+160h+Block]; Src
0x10038318  push    esi; int
0x10038319  call    _UtilSetErrorInfoReal@32; UtilSetErrorInfoReal(x,x,x,x,x,x,x,x)
0x1003831e  push    _critJet; lpCriticalSection
0x10038324  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1003832a  mov     eax, 0FFFFF88Dh
0x1003832f  pop     edi
0x10038330  pop     esi
0x10038331  pop     ebx
0x10038332  mov     ecx, [esp+13Ch+var_4]
0x10038339  xor     ecx, esp; StackCookie
0x1003833b  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10038340  mov     esp, ebp
0x10038342  pop     ebp
0x10038343  retn    0Ch
0x10038346  lea     eax, [esp+148h+var_134]
0x1003834a  push    eax; int
0x1003834b  lea     eax, [esp+14Ch+var_12C]
0x1003834f  push    eax; int
0x10038350  push    80h; Size
0x10038355  lea     eax, [esp+154h+var_88]
0x1003835c  push    eax; int
0x1003835d  push    [esp+158h+Block]; Src
0x10038361  push    0FFFFFFFFh; int
0x10038363  push    esi; int
0x10038364  call    _ErrSecGetSidFromName@28; ErrSecGetSidFromName(x,x,x,x,x,x,x)
0x10038369  mov     ebx, eax
0x1003836b  test    ebx, ebx
0x1003836d  js      loc_100382A0
0x10038373  cmp     [esp+148h+var_134], 0
0x10038378  jnz     short loc_100383A2
0x1003837a  push    _critJet; lpCriticalSection
0x10038380  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10038386  mov     eax, 0FFFFF890h
0x1003838b  pop     edi
0x1003838c  pop     esi
0x1003838d  pop     ebx
0x1003838e  mov     ecx, [esp+13Ch+var_4]
0x10038395  xor     ecx, esp; StackCookie
0x10038397  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1003839c  mov     esp, ebp
0x1003839e  pop     ebp
0x1003839f  retn    0Ch
0x100383a2  mov     eax, [esp+148h+var_12C]
0x100383a6  mov     [esp+148h+Size], eax
0x100383aa  lea     eax, [esp+148h+var_134]
0x100383ae  push    eax; int
0x100383af  lea     eax, [esp+14Ch+var_12C]
0x100383b3  push    eax; int
0x100383b4  push    80h; Size
0x100383b9  lea     eax, [esp+154h+var_108]
0x100383bd  push    eax; int
0x100383be  push    [esp+158h+Src]; Src
0x100383c2  push    0FFFFFFFFh; int
0x100383c4  push    esi; int
0x100383c5  call    _ErrSecGetSidFromName@28; ErrSecGetSidFromName(x,x,x,x,x,x,x)
0x100383ca  mov     ebx, eax
0x100383cc  test    ebx, ebx
0x100383ce  js      loc_100382A0
0x100383d4  cmp     [esp+148h+var_134], 0
0x100383d9  jz      short loc_10038403
0x100383db  push    _critJet; lpCriticalSection
0x100383e1  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100383e7  mov     eax, 0FFFFF88Eh
0x100383ec  pop     edi
0x100383ed  pop     esi
0x100383ee  pop     ebx
0x100383ef  mov     ecx, [esp+13Ch+var_4]
0x100383f6  xor     ecx, esp; StackCookie
0x100383f8  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100383fd  mov     esp, ebp
0x100383ff  pop     ebp
0x10038400  retn    0Ch
0x10038403  mov     eax, [esp+148h+var_12C]
0x10038407  lea     ecx, [esp+148h+Block]
0x1003840b  push    ecx; int
0x1003840c  push    eax; Size
0x1003840d  mov     [esp+150h+var_134], eax
0x10038411  or      edx, 0FFFFFFFFh
0x10038414  lea     eax, [esp+150h+var_108]
0x10038418  mov     ecx, esi
0x1003841a  push    eax; int
0x1003841b  call    _ErrSecBuildUserToken@20; ErrSecBuildUserToken(x,x,x,x,x)
0x10038420  mov     ebx, eax
0x10038422  test    ebx, ebx
0x10038424  js      loc_100382A0
0x1003842a  push    [esp+148h+Size]
0x1003842e  mov     ecx, [esp+14Ch+Block]
0x10038432  lea     edx, [esp+14Ch+var_88]
0x10038439  call    _SecIndexOfTokenSid@12; SecIndexOfTokenSid(x,x,x)
0x1003843e  xor     ebx, ebx
0x10038440  cmp     eax, 0FFFFFFFFh
0x10038443  mov     eax, [esp+148h+Block]
0x10038447  setnz   bl
0x1003844a  test    eax, eax
0x1003844c  jz      short loc_10038458
0x1003844e  push    eax; Block
0x1003844f  call    ds:__imp__free
0x10038455  add     esp, 4
0x10038458  test    ebx, ebx
0x1003845a  jnz     loc_100383DB
0x10038460  push    80000000h
0x10038465  push    offset _wszSgTable; "MSysGroups"
0x1003846a  lea     eax, [esp+150h+var_13C]
0x1003846e  push    eax
0x1003846f  push    edi
0x10038470  push    esi
0x10038471  call    _ErrDispOpenTable@20; ErrDispOpenTable(x,x,x,x,x)
0x10038476  mov     edi, eax
0x10038478  test    edi, edi
0x1003847a  jns     short loc_100384AF
0x1003847c  cmp     edi, 0FFFFFAE7h
0x10038482  mov     eax, 0FFFFF88Bh
0x10038487  cmovz   edi, eax
0x1003848a  push    _critJet; lpCriticalSection
0x10038490  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10038496  mov     eax, edi
0x10038498  pop     edi
0x10038499  pop     esi
0x1003849a  pop     ebx
0x1003849b  mov     ecx, [esp+13Ch+var_4]
0x100384a2  xor     ecx, esp; StackCookie
0x100384a4  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100384a9  mov     esp, ebp
0x100384ab  pop     ebp
0x100384ac  retn    0Ch
0x100384af  push    0
0x100384b1  push    [esp+14Ch+var_13C]
0x100384b5  push    esi
0x100384b6  call    _ErrDispPrepareUpdate2@12; ErrDispPrepareUpdate2(x,x,x)
0x100384bb  mov     edi, eax
0x100384bd  test    edi, edi
0x100384bf  js      loc_100385E0
0x100384c5  push    0
0x100384c7  push    18h
0x100384c9  lea     eax, [esp+150h+var_120]
0x100384cd  push    eax
0x100384ce  push    offset _wszSgUserSidColumn; "UserSID"
0x100384d3  push    [esp+158h+var_13C]
0x100384d7  push    esi
0x100384d8  call    _ErrDispGetTableColumnInfo@24; ErrDispGetTableColumnInfo(x,x,x,x,x,x)
0x100384dd  mov     edi, eax
0x100384df  test    edi, edi
0x100384e1  js      loc_100385E0
0x100384e7  push    0
0x100384e9  push    0
0x100384eb  push    [esp+150h+var_134]
0x100384ef  lea     eax, [esp+154h+var_108]
0x100384f3  push    eax
0x100384f4  push    [esp+158h+var_11C]
0x100384f8  push    [esp+15Ch+var_13C]
0x100384fc  push    esi
0x100384fd  call    _ErrDispSetColumn@28; ErrDispSetColumn(x,x,x,x,x,x,x)
0x10038502  mov     edi, eax
0x10038504  test    edi, edi
0x10038506  js      loc_100385E0
0x1003850c  push    0
0x1003850e  push    18h
0x10038510  lea     eax, [esp+150h+var_120]
0x10038514  push    eax
0x10038515  push    offset _wszSgGroupSidColumn; "GroupSID"
0x1003851a  push    [esp+158h+var_13C]
0x1003851e  push    esi
0x1003851f  call    _ErrDispGetTableColumnInfo@24; ErrDispGetTableColumnInfo(x,x,x,x,x,x)
0x10038524  mov     edi, eax
0x10038526  test    edi, edi
0x10038528  js      loc_100385E0
0x1003852e  mov     ebx, [esp+148h+Size]
0x10038532  lea     eax, [esp+148h+var_88]
0x10038539  push    0
0x1003853b  push    0
0x1003853d  push    ebx
0x1003853e  push    eax
0x1003853f  push    [esp+158h+var_11C]
0x10038543  push    [esp+15Ch+var_13C]
0x10038547  push    esi
0x10038548  call    _ErrDispSetColumn@28; ErrDispSetColumn(x,x,x,x,x,x,x)
0x1003854d  mov     edi, eax
0x1003854f  test    edi, edi
0x10038551  js      loc_100385E0
0x10038557  push    0
0x10038559  push    0
0x1003855b  push    0
0x1003855d  push    [esp+154h+var_13C]
0x10038561  push    esi
0x10038562  call    _ErrDispUpdate@20; ErrDispUpdate(x,x,x,x,x)
0x10038567  mov     edi, eax
0x10038569  test    edi, edi
0x1003856b  js      short loc_100385E0
0x1003856d  push    [esp+148h+var_13C]
0x10038571  push    esi
  ... truncated ...
```
