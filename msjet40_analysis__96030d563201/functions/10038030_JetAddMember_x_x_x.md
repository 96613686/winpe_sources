# JetAddMember(x,x,x)

- ea: `0x10038030`
- end: `0x1003848f`
- name: `_JetAddMember@12`
- size: `1119`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, installer_update`

## callers

- `0x100cf9f4`

## callees

- `0x100292b0`
- `0x100292f0`
- `0x10038030`
- `0x10039c00`
- `0x1003c5f0`
- `0x1003c760`
- `0x1003cb10`
- `0x1003d9f0`
- `0x1003e820`
- `0x1003e870`
- `0x10043090`
- `0x10043260`
- `0x10043660`
- `0x10043840`
- `0x100440c0`
- `0x10044c00`
- `0x10044e00`
- `0x10122f60`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x100382cf`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x100382cf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1003809c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100380e2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10038126`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100381a4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10038200`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10038261`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10038310`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10038441`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10038470`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1003809c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100380e2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10038126`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100381a4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10038200`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10038261`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10038310`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10038441`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10038470`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10038066`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10038066`

## string_xrefs

- `0x1003834e`: `UserSID`
- `0x10038395`: `GroupSID`

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
    v3 = dword_1016EAE8[26 * v3];
    if ( v3 == -1 )
      goto LABEL_4;
  }
  ClearErrorInfo(a1);
  v5 = (int)*(&rgiscb + 5 * dword_1016EAD0[26 * v3] + 3);
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
0x10038030  mov     edi, edi
0x10038032  push    ebp
0x10038033  mov     ebp, esp
0x10038035  and     esp, 0FFFFFFF8h
0x10038038  sub     esp, 13Ch
0x1003803e  mov     eax, ___security_cookie
0x10038043  xor     eax, esp
0x10038045  mov     [esp+13Ch+var_4], eax
0x1003804c  mov     eax, [ebp+arg_4]
0x1003804f  push    ebx
0x10038050  push    esi
0x10038051  mov     esi, [ebp+arg_0]
0x10038054  push    edi
0x10038055  push    _critJet; lpCriticalSection
0x1003805b  mov     [esp+14Ch+Block], eax
0x1003805f  mov     eax, [ebp+arg_8]
0x10038062  mov     [esp+14Ch+Src], eax
0x10038066  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1003806c  mov     edi, _isibHead
0x10038072  cmp     edi, 0FFFFFFFFh
0x10038075  jz      short loc_10038096
0x10038077  nop     word ptr [eax+eax+00000000h]
0x10038080  imul    eax, edi, 68h ; 'h'
0x10038083  cmp     _rgsib[eax], esi
0x10038089  jz      short loc_100380BE
0x1003808b  mov     edi, dword_1016EAE8[eax]
0x10038091  cmp     edi, 0FFFFFFFFh
0x10038094  jnz     short loc_10038080
0x10038096  push    _critJet; lpCriticalSection
0x1003809c  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100380a2  mov     eax, 0FFFFFBB0h
0x100380a7  pop     edi
0x100380a8  pop     esi
0x100380a9  pop     ebx
0x100380aa  mov     ecx, [esp+13Ch+var_4]
0x100380b1  xor     ecx, esp; StackCookie
0x100380b3  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100380b8  mov     esp, ebp
0x100380ba  pop     ebp
0x100380bb  retn    0Ch
0x100380be  push    esi
0x100380bf  call    _ClearErrorInfo@4; ClearErrorInfo(x)
0x100380c4  imul    eax, edi, 68h ; 'h'
0x100380c7  mov     eax, dword_1016EAD0[eax]
0x100380cd  lea     eax, [eax+eax*4]
0x100380d0  mov     edi, dword ptr (_rgiscb+0Ch)[eax*4]
0x100380d7  cmp     edi, 0FFFFFFFFh
0x100380da  jnz     short loc_10038104
0x100380dc  push    _critJet; lpCriticalSection
0x100380e2  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100380e8  mov     eax, 0FFFFF8F6h
0x100380ed  pop     edi
0x100380ee  pop     esi
0x100380ef  pop     ebx
0x100380f0  mov     ecx, [esp+13Ch+var_4]
0x100380f7  xor     ecx, esp; StackCookie
0x100380f9  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100380fe  mov     esp, ebp
0x10038100  pop     ebp
0x10038101  retn    0Ch
0x10038104  lea     eax, [esp+148h+var_128]
0x10038108  push    eax
0x10038109  push    offset _wszSgTable; "MSysGroups"
0x1003810e  push    offset _wszTcObject; "Tables"
0x10038113  push    edi
0x10038114  push    esi
0x10038115  call    _ErrDispGetObjidFromName@20; ErrDispGetObjidFromName(x,x,x,x,x)
0x1003811a  mov     ebx, eax
0x1003811c  test    ebx, ebx
0x1003811e  jns     short loc_10038145
0x10038120  push    _critJet; lpCriticalSection
0x10038126  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1003812c  mov     eax, ebx
0x1003812e  pop     edi
0x1003812f  pop     esi
0x10038130  pop     ebx
0x10038131  mov     ecx, [esp+13Ch+var_4]
0x10038138  xor     ecx, esp; StackCookie
0x1003813a  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1003813f  mov     esp, ebp
0x10038141  pop     ebp
0x10038142  retn    0Ch
0x10038145  mov     eax, _mpdbidiiscb[edi*4]
0x1003814c  lea     eax, [eax+eax*4]
0x1003814f  mov     eax, Src[eax*4]
0x10038156  test    eax, eax
0x10038158  jnz     short loc_10038161
0x1003815a  mov     ebx, 0FFFFFC17h
0x1003815f  jmp     short loc_10038120
0x10038161  push    0
0x10038163  lea     ecx, [esp+14Ch+Size]
0x10038167  mov     edx, edi
0x10038169  push    ecx
0x1003816a  push    0
0x1003816c  push    eax
0x1003816d  push    [esp+158h+var_128]
0x10038171  mov     ecx, esi
0x10038173  call    _ErrSecCollectAccess@28; ErrSecCollectAccess(x,x,x,x,x,x,x)
0x10038178  mov     ebx, eax
0x1003817a  test    ebx, ebx
0x1003817c  js      short loc_10038120
0x1003817e  test    byte ptr [esp+148h+Size], 20h
0x10038183  jnz     short loc_100381C6
0x10038185  push    0; int
0x10038187  push    0; int
0x10038189  push    0; int
0x1003818b  push    0FFFFE016h; int
0x10038190  push    0; void *
0x10038192  push    0; void *
0x10038194  push    [esp+160h+Block]; Src
0x10038198  push    esi; int
0x10038199  call    _UtilSetErrorInfoReal@32; UtilSetErrorInfoReal(x,x,x,x,x,x,x,x)
0x1003819e  push    _critJet; lpCriticalSection
0x100381a4  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100381aa  mov     eax, 0FFFFF88Dh
0x100381af  pop     edi
0x100381b0  pop     esi
0x100381b1  pop     ebx
0x100381b2  mov     ecx, [esp+13Ch+var_4]
0x100381b9  xor     ecx, esp; StackCookie
0x100381bb  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100381c0  mov     esp, ebp
0x100381c2  pop     ebp
0x100381c3  retn    0Ch
0x100381c6  lea     eax, [esp+148h+var_134]
0x100381ca  push    eax; int
0x100381cb  lea     eax, [esp+14Ch+var_12C]
0x100381cf  push    eax; int
0x100381d0  push    80h; Size
0x100381d5  lea     eax, [esp+154h+var_88]
0x100381dc  push    eax; int
0x100381dd  push    [esp+158h+Block]; Src
0x100381e1  push    0FFFFFFFFh; int
0x100381e3  push    esi; int
0x100381e4  call    _ErrSecGetSidFromName@28; ErrSecGetSidFromName(x,x,x,x,x,x,x)
0x100381e9  mov     ebx, eax
0x100381eb  test    ebx, ebx
0x100381ed  js      loc_10038120
0x100381f3  cmp     [esp+148h+var_134], 0
0x100381f8  jnz     short loc_10038222
0x100381fa  push    _critJet; lpCriticalSection
0x10038200  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10038206  mov     eax, 0FFFFF890h
0x1003820b  pop     edi
0x1003820c  pop     esi
0x1003820d  pop     ebx
0x1003820e  mov     ecx, [esp+13Ch+var_4]
0x10038215  xor     ecx, esp; StackCookie
0x10038217  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1003821c  mov     esp, ebp
0x1003821e  pop     ebp
0x1003821f  retn    0Ch
0x10038222  mov     eax, [esp+148h+var_12C]
0x10038226  mov     [esp+148h+Size], eax
0x1003822a  lea     eax, [esp+148h+var_134]
0x1003822e  push    eax; int
0x1003822f  lea     eax, [esp+14Ch+var_12C]
0x10038233  push    eax; int
0x10038234  push    80h; Size
0x10038239  lea     eax, [esp+154h+var_108]
0x1003823d  push    eax; int
0x1003823e  push    [esp+158h+Src]; Src
0x10038242  push    0FFFFFFFFh; int
0x10038244  push    esi; int
0x10038245  call    _ErrSecGetSidFromName@28; ErrSecGetSidFromName(x,x,x,x,x,x,x)
0x1003824a  mov     ebx, eax
0x1003824c  test    ebx, ebx
0x1003824e  js      loc_10038120
0x10038254  cmp     [esp+148h+var_134], 0
0x10038259  jz      short loc_10038283
0x1003825b  push    _critJet; lpCriticalSection
0x10038261  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10038267  mov     eax, 0FFFFF88Eh
0x1003826c  pop     edi
0x1003826d  pop     esi
0x1003826e  pop     ebx
0x1003826f  mov     ecx, [esp+13Ch+var_4]
0x10038276  xor     ecx, esp; StackCookie
0x10038278  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1003827d  mov     esp, ebp
0x1003827f  pop     ebp
0x10038280  retn    0Ch
0x10038283  mov     eax, [esp+148h+var_12C]
0x10038287  lea     ecx, [esp+148h+Block]
0x1003828b  push    ecx; int
0x1003828c  push    eax; Size
0x1003828d  mov     [esp+150h+var_134], eax
0x10038291  or      edx, 0FFFFFFFFh
0x10038294  lea     eax, [esp+150h+var_108]
0x10038298  mov     ecx, esi
0x1003829a  push    eax; int
0x1003829b  call    _ErrSecBuildUserToken@20; ErrSecBuildUserToken(x,x,x,x,x)
0x100382a0  mov     ebx, eax
0x100382a2  test    ebx, ebx
0x100382a4  js      loc_10038120
0x100382aa  push    [esp+148h+Size]
0x100382ae  mov     ecx, [esp+14Ch+Block]
0x100382b2  lea     edx, [esp+14Ch+var_88]
0x100382b9  call    _SecIndexOfTokenSid@12; SecIndexOfTokenSid(x,x,x)
0x100382be  xor     ebx, ebx
0x100382c0  cmp     eax, 0FFFFFFFFh
0x100382c3  mov     eax, [esp+148h+Block]
0x100382c7  setnz   bl
0x100382ca  test    eax, eax
0x100382cc  jz      short loc_100382D8
0x100382ce  push    eax; Block
0x100382cf  call    ds:__imp__free
0x100382d5  add     esp, 4
0x100382d8  test    ebx, ebx
0x100382da  jnz     loc_1003825B
0x100382e0  push    80000000h
0x100382e5  push    offset _wszSgTable; "MSysGroups"
0x100382ea  lea     eax, [esp+150h+var_13C]
0x100382ee  push    eax
0x100382ef  push    edi
0x100382f0  push    esi
0x100382f1  call    _ErrDispOpenTable@20; ErrDispOpenTable(x,x,x,x,x)
0x100382f6  mov     edi, eax
0x100382f8  test    edi, edi
0x100382fa  jns     short loc_1003832F
0x100382fc  cmp     edi, 0FFFFFAE7h
0x10038302  mov     eax, 0FFFFF88Bh
0x10038307  cmovz   edi, eax
0x1003830a  push    _critJet; lpCriticalSection
0x10038310  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10038316  mov     eax, edi
0x10038318  pop     edi
0x10038319  pop     esi
0x1003831a  pop     ebx
0x1003831b  mov     ecx, [esp+13Ch+var_4]
0x10038322  xor     ecx, esp; StackCookie
0x10038324  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10038329  mov     esp, ebp
0x1003832b  pop     ebp
0x1003832c  retn    0Ch
0x1003832f  push    0
0x10038331  push    [esp+14Ch+var_13C]
0x10038335  push    esi
0x10038336  call    _ErrDispPrepareUpdate2@12; ErrDispPrepareUpdate2(x,x,x)
0x1003833b  mov     edi, eax
0x1003833d  test    edi, edi
0x1003833f  js      loc_10038460
0x10038345  push    0
0x10038347  push    18h
0x10038349  lea     eax, [esp+150h+var_120]
0x1003834d  push    eax
0x1003834e  push    offset _wszSgUserSidColumn; "UserSID"
0x10038353  push    [esp+158h+var_13C]
0x10038357  push    esi
0x10038358  call    _ErrDispGetTableColumnInfo@24; ErrDispGetTableColumnInfo(x,x,x,x,x,x)
0x1003835d  mov     edi, eax
0x1003835f  test    edi, edi
0x10038361  js      loc_10038460
0x10038367  push    0
0x10038369  push    0
0x1003836b  push    [esp+150h+var_134]
0x1003836f  lea     eax, [esp+154h+var_108]
0x10038373  push    eax
0x10038374  push    [esp+158h+var_11C]
0x10038378  push    [esp+15Ch+var_13C]
0x1003837c  push    esi
0x1003837d  call    _ErrDispSetColumn@28; ErrDispSetColumn(x,x,x,x,x,x,x)
0x10038382  mov     edi, eax
0x10038384  test    edi, edi
0x10038386  js      loc_10038460
0x1003838c  push    0
0x1003838e  push    18h
0x10038390  lea     eax, [esp+150h+var_120]
0x10038394  push    eax
0x10038395  push    offset _wszSgGroupSidColumn; "GroupSID"
0x1003839a  push    [esp+158h+var_13C]
0x1003839e  push    esi
0x1003839f  call    _ErrDispGetTableColumnInfo@24; ErrDispGetTableColumnInfo(x,x,x,x,x,x)
0x100383a4  mov     edi, eax
0x100383a6  test    edi, edi
0x100383a8  js      loc_10038460
0x100383ae  mov     ebx, [esp+148h+Size]
0x100383b2  lea     eax, [esp+148h+var_88]
0x100383b9  push    0
0x100383bb  push    0
0x100383bd  push    ebx
0x100383be  push    eax
0x100383bf  push    [esp+158h+var_11C]
0x100383c3  push    [esp+15Ch+var_13C]
0x100383c7  push    esi
0x100383c8  call    _ErrDispSetColumn@28; ErrDispSetColumn(x,x,x,x,x,x,x)
0x100383cd  mov     edi, eax
0x100383cf  test    edi, edi
0x100383d1  js      loc_10038460
0x100383d7  push    0
0x100383d9  push    0
0x100383db  push    0
0x100383dd  push    [esp+154h+var_13C]
0x100383e1  push    esi
0x100383e2  call    _ErrDispUpdate@20; ErrDispUpdate(x,x,x,x,x)
0x100383e7  mov     edi, eax
0x100383e9  test    edi, edi
0x100383eb  js      short loc_10038460
0x100383ed  push    [esp+148h+var_13C]
0x100383f1  push    esi
  ... truncated ...
```
