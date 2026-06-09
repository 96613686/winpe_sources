# JetRenameTable(x,x,x,x)

- ea: `0x1001c020`
- end: `0x1001c542`
- name: `_JetRenameTable@16`
- size: `1314`
- prototype: `int __stdcall(Session *, int, void *Src, int)`
- caller_count: `0`
- callee_count: `23`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x1001c020`
- `0x10035450`
- `0x1003db70`
- `0x1003e7e0`
- `0x1003e930`
- `0x1003ea00`
- `0x10043140`
- `0x10043380`
- `0x100433f0`
- `0x100437f0`
- `0x10044ca0`
- `0x10044d80`
- `0x10044f80`
- `0x1004d920`
- `0x1004d9c0`
- `0x1004da20`
- `0x10050190`
- `0x10113e3c`
- `0x101170a0`
- `0x1011b3e8`
- `0x1011d1f2`
- `0x10123110`
- `0x10123b3c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001c077`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001c132`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001c197`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001c1dd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001c223`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001c4f4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001c520`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001c077`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001c132`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001c197`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001c1dd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001c223`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001c4f4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001c520`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1001c05e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1001c05e`

## pseudocode

```c
JET_ERR __stdcall JetRenameTable(Session *sesid, unsigned int a2, void *Src, void *a4)
{
  _DWORD *v5; // eax
  int v6; // eax
  int v7; // esi
  JET_ERR updated; // esi
  Session *v9; // edx
  int v10; // ecx
  int v11; // [esp+14h] [ebp-B4h] BYREF
  int ObjidFromName; // [esp+18h] [ebp-B0h] BYREF
  void *v13; // [esp+1Ch] [ebp-ACh]
  int v14; // [esp+20h] [ebp-A8h]
  int v15; // [esp+24h] [ebp-A4h]
  int v16; // [esp+28h] [ebp-A0h] BYREF
  int v17; // [esp+2Ch] [ebp-9Ch] BYREF
  _DWORD v18[4]; // [esp+30h] [ebp-98h] BYREF
  _DWORD v19[23]; // [esp+40h] [ebp-88h] BYREF
  char v20; // [esp+9Ch] [ebp-2Ch] BYREF
  int v21; // [esp+A0h] [ebp-28h] BYREF

  v14 = (int)Src;
  v13 = a4;
  v15 = 0;
  EnterCriticalSection(critJet);
  if ( !FValidSesid(sesid) )
  {
    LeaveCriticalSection(critJet);
    return -1104;
  }
  if ( a2 >= dbidInit && a2 < 0x100 && (int *)mpdbidpvdbfndef[a2] != vdbfndefInvalidDbid )
  {
    v11 = (int)&mpdbidiiscb[a2];
    if ( IsJetIsam(sesid, a2) )
    {
      v11 = (int)&mpdbidiiscb[a2];
    }
    else if ( !*(&::Src + 5 * mpdbidiiscb[a2]) || (int *)mpdbidpvdbfndef[a2] == vdbfndefRdb )
    {
      goto LABEL_9;
    }
    ObjidFromName = ErrDispGetObjidFromName(sesid, a2, L"Tables", Src, &v17);
    if ( ObjidFromName < 0 )
      goto LABEL_12;
    v5 = *(&::Src + 5 * *(_DWORD *)v11);
    if ( !v5 )
    {
      LeaveCriticalSection(critJet);
      return -1001;
    }
    v6 = ErrSecCollectAccess((int)sesid, a2, v17, v5, 0, &v11, 0);
    ObjidFromName = v6;
    if ( v6 < 0 )
    {
      v7 = v6;
      LeaveCriticalSection(critJet);
      return v7;
    }
    if ( (v11 & 8) == 0 )
    {
      UtilSetErrorInfoReal((int)sesid, Src, 0, 0, -8170, 0, 0, 0);
      LeaveCriticalSection(critJet);
      return -1907;
    }
LABEL_9:
    ObjidFromName = ErrIsamBeginTransaction(sesid);
    if ( ObjidFromName < 0 )
    {
LABEL_12:
      LeaveCriticalSection(critJet);
      return ObjidFromName;
    }
    ObjidFromName = ErrREPRenameTableCheck((int)sesid, a2, Src, &v11);
    if ( ObjidFromName < 0 )
    {
      ErrIsamRollback(sesid, 0);
      goto LABEL_12;
    }
    updated = ErrDispRenameTable(sesid, a2, Src, v13);
    if ( updated < 0 )
      goto LABEL_44;
    v15 = 1;
    updated = ErrRelationshipUpdateNames(sesid, a2, v14, (const unsigned __int16 *)v13, 0, 0);
    if ( updated < 0 )
      goto LABEL_44;
    if ( !v11 )
    {
LABEL_43:
      updated = ErrIsamCommitTransaction(sesid, 0);
      if ( updated >= 0 )
      {
LABEL_46:
        LeaveCriticalSection(critJet);
        return updated;
      }
LABEL_44:
      ErrIsamRollback(sesid, 0);
      if ( v15 )
        ErrDispRenameTable(sesid, a2, v13, v14);
      goto LABEL_46;
    }
    updated = ErrFObjectReplicable2((int)L"Tables", v13, (int)&ObjidFromName, (int)&v16);
    if ( updated < 0 )
      goto LABEL_44;
    if ( !ObjidFromName )
    {
      updated = -20311;
      goto LABEL_42;
    }
    memset(&v19[5], 0, 0x40u);
    v19[0] = 3;
    v19[1] = v14;
    v19[3] = v13;
    v19[2] = 2 * wcslen((const unsigned __int16 *)v14);
    v18[0] = 40;
    v19[4] = 2 * wcslen((const unsigned __int16 *)v13);
    v18[3] = &v20;
    updated = ErrDispGetObjectInfo(sesid, a2, 0, L"Tables", v13, v18, 5);
    if ( updated < 0 )
      goto LABEL_44;
    v19[12] = 4;
    v19[11] = &v21;
    updated = ErrReplSchChangeInsert(sesid, a2, v19);
    if ( updated < 0 )
      goto LABEL_44;
    updated = ErrRepSetLastSchema(sesid, a2);
    if ( updated < 0 )
      goto LABEL_44;
    if ( v21 == 1 )
    {
      v16 = (int)*(&rgrepdbinfo + a2);
      v11 = *(_DWORD *)(v16 + 8);
      ObjidFromName = 2 * wcslen((const unsigned __int16 *)v14);
      if ( (unsigned int)v11 >= 0x800 || v11 < (unsigned int)tableidInit )
      {
        updated = -1310;
LABEL_42:
        if ( updated < 0 )
          goto LABEL_44;
        goto LABEL_43;
      }
      v9 = sesid;
      v10 = 4 * v11;
      _mm_lfence();
      if ( rgvtdef[v10] != -1 )
        v9 = (Session *)rgvtdef[4 * v11];
      updated = (*(int (__thiscall **)(_DWORD, Session *, int, int, int, int))(dword_101636CC[4 * v11] + 100))(
                  *(_DWORD *)(dword_101636CC[4 * v11] + 100),
                  v9,
                  dword_101636C4[4 * v11],
                  v14,
                  ObjidFromName,
                  1);
      if ( updated < 0 )
        goto LABEL_44;
      updated = ErrDispSeek(sesid, v11, 1);
      if ( updated < 0 )
        goto LABEL_44;
      updated = ErrDispPrepareUpdate2(sesid, v11, 2);
      if ( updated < 0
        || (updated = ErrDispSetColumn(
                        sesid,
                        v11,
                        *(_DWORD *)(v16 + 120),
                        v13,
                        2 * wcslen((const unsigned __int16 *)v13),
                        0,
                        0),
            updated < 0)
        || (updated = ErrDispUpdate(sesid, v11, 0, 0, 0), updated < 0) )
      {
        ErrDispPrepareUpdate2(sesid, v11, 3);
        goto LABEL_42;
      }
    }
    updated = 0;
    goto LABEL_42;
  }
  LeaveCriticalSection(critJet);
  return -1010;
}

```

## disassembly

```asm
0x1001c020  mov     edi, edi
0x1001c022  push    ebp
0x1001c023  mov     ebp, esp
0x1001c025  and     esp, 0FFFFFFF8h
0x1001c028  sub     esp, 0B4h
0x1001c02e  mov     eax, ___security_cookie
0x1001c033  xor     eax, esp
0x1001c035  mov     [esp+0B4h+var_4], eax
0x1001c03c  mov     eax, [ebp+arg_C]
0x1001c03f  push    ebx
0x1001c040  mov     ebx, [ebp+arg_4]
0x1001c043  push    esi
0x1001c044  mov     esi, [ebp+Src]
0x1001c047  push    edi
0x1001c048  push    _critJet; lpCriticalSection
0x1001c04e  mov     [esp+0C4h+var_A8], esi
0x1001c052  mov     [esp+0C4h+var_AC], eax
0x1001c056  mov     [esp+0C4h+var_A4], 0
0x1001c05e  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1001c064  mov     edi, [ebp+sesid]
0x1001c067  push    edi
0x1001c068  call    _FValidSesid@4; FValidSesid(x)
0x1001c06d  test    eax, eax
0x1001c06f  jnz     short loc_1001C099
0x1001c071  push    _critJet; lpCriticalSection
0x1001c077  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001c07d  mov     eax, 0FFFFFBB0h
0x1001c082  pop     edi
0x1001c083  pop     esi
0x1001c084  pop     ebx
0x1001c085  mov     ecx, [esp+0B4h+var_4]
0x1001c08c  xor     ecx, esp; StackCookie
0x1001c08e  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001c093  mov     esp, ebp
0x1001c095  pop     ebp
0x1001c096  retn    10h
0x1001c099  cmp     ebx, _dbidInit
0x1001c09f  jb      loc_1001C51A
0x1001c0a5  cmp     ebx, 100h
0x1001c0ab  jnb     loc_1001C51A
0x1001c0b1  cmp     _mpdbidpvdbfndef[ebx*4], offset _vdbfndefInvalidDbid
0x1001c0bc  jz      loc_1001C51A
0x1001c0c2  lea     eax, _mpdbidiiscb[ebx*4]
0x1001c0c9  mov     edx, ebx
0x1001c0cb  mov     ecx, edi
0x1001c0cd  mov     [esp+0C0h+var_B4], eax
0x1001c0d1  call    _IsJetIsam@8; IsJetIsam(x,x)
0x1001c0d6  test    eax, eax
0x1001c0d8  jnz     short loc_1001C153
0x1001c0da  mov     eax, _mpdbidiiscb[ebx*4]
0x1001c0e1  lea     eax, [eax+eax*4]
0x1001c0e4  cmp     Src[eax*4], 0
0x1001c0ec  jz      short loc_1001C0FB
0x1001c0ee  cmp     _mpdbidpvdbfndef[ebx*4], offset _vdbfndefRdb
0x1001c0f9  jnz     short loc_1001C15E
0x1001c0fb  push    edi
0x1001c0fc  call    _ErrIsamBeginTransaction@4; ErrIsamBeginTransaction(x)
0x1001c101  mov     [esp+0C0h+var_B0], eax
0x1001c105  test    eax, eax
0x1001c107  js      short loc_1001C12C
0x1001c109  lea     eax, [esp+0C0h+var_B4]
0x1001c10d  mov     edx, ebx
0x1001c10f  push    eax; int
0x1001c110  push    esi; Src
0x1001c111  mov     ecx, edi; int
0x1001c113  call    _ErrREPRenameTableCheck@16; ErrREPRenameTableCheck(x,x,x,x)
0x1001c118  mov     [esp+0C0h+var_B0], eax
0x1001c11c  test    eax, eax
0x1001c11e  jns     loc_1001C245
0x1001c124  push    0; char
0x1001c126  push    edi; Session *
0x1001c127  call    _ErrIsamRollback@8; ErrIsamRollback(x,x)
0x1001c12c  push    _critJet; lpCriticalSection
0x1001c132  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001c138  mov     eax, [esp+0C0h+var_B0]
0x1001c13c  pop     edi
0x1001c13d  pop     esi
0x1001c13e  pop     ebx
0x1001c13f  mov     ecx, [esp+0B4h+var_4]
0x1001c146  xor     ecx, esp; StackCookie
0x1001c148  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001c14d  mov     esp, ebp
0x1001c14f  pop     ebp
0x1001c150  retn    10h
0x1001c153  lea     eax, _mpdbidiiscb[ebx*4]
0x1001c15a  mov     [esp+0C0h+var_B4], eax
0x1001c15e  lea     eax, [esp+0C0h+var_9C]
0x1001c162  push    eax
0x1001c163  push    esi
0x1001c164  push    offset _wszTcObject; "Tables"
0x1001c169  push    ebx
0x1001c16a  push    edi
0x1001c16b  call    _ErrDispGetObjidFromName@20; ErrDispGetObjidFromName(x,x,x,x,x)
0x1001c170  mov     [esp+0C0h+var_B0], eax
0x1001c174  test    eax, eax
0x1001c176  js      short loc_1001C12C
0x1001c178  mov     eax, [esp+0C0h+var_B4]
0x1001c17c  mov     eax, [eax]
0x1001c17e  lea     eax, [eax+eax*4]
0x1001c181  mov     eax, Src[eax*4]
0x1001c188  test    eax, eax
0x1001c18a  jnz     short loc_1001C1B6
0x1001c18c  push    _critJet; lpCriticalSection
0x1001c192  mov     esi, 0FFFFFC17h
0x1001c197  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001c19d  mov     eax, esi
0x1001c19f  pop     edi
0x1001c1a0  pop     esi
0x1001c1a1  pop     ebx
0x1001c1a2  mov     ecx, [esp+0B4h+var_4]
0x1001c1a9  xor     ecx, esp; StackCookie
0x1001c1ab  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001c1b0  mov     esp, ebp
0x1001c1b2  pop     ebp
0x1001c1b3  retn    10h
0x1001c1b6  push    0
0x1001c1b8  lea     ecx, [esp+0C4h+var_B4]
0x1001c1bc  mov     edx, ebx
0x1001c1be  push    ecx
0x1001c1bf  push    0
0x1001c1c1  push    eax
0x1001c1c2  push    [esp+0D0h+var_9C]
0x1001c1c6  mov     ecx, edi
0x1001c1c8  call    _ErrSecCollectAccess@28; ErrSecCollectAccess(x,x,x,x,x,x,x)
0x1001c1cd  mov     [esp+0C0h+var_B0], eax
0x1001c1d1  test    eax, eax
0x1001c1d3  jns     short loc_1001C1FC
0x1001c1d5  push    _critJet; lpCriticalSection
0x1001c1db  mov     esi, eax
0x1001c1dd  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001c1e3  mov     eax, esi
0x1001c1e5  pop     edi
0x1001c1e6  pop     esi
0x1001c1e7  pop     ebx
0x1001c1e8  mov     ecx, [esp+0B4h+var_4]
0x1001c1ef  xor     ecx, esp; StackCookie
0x1001c1f1  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001c1f6  mov     esp, ebp
0x1001c1f8  pop     ebp
0x1001c1f9  retn    10h
0x1001c1fc  test    byte ptr [esp+0C0h+var_B4], 8
0x1001c201  jnz     loc_1001C0FB
0x1001c207  push    0; int
0x1001c209  push    0; int
0x1001c20b  push    0; int
0x1001c20d  push    0FFFFE016h; int
0x1001c212  push    0; void *
0x1001c214  push    0; void *
0x1001c216  push    esi; Src
0x1001c217  push    edi; int
0x1001c218  call    _UtilSetErrorInfoReal@32; UtilSetErrorInfoReal(x,x,x,x,x,x,x,x)
0x1001c21d  push    _critJet; lpCriticalSection
0x1001c223  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001c229  mov     eax, 0FFFFF88Dh
0x1001c22e  pop     edi
0x1001c22f  pop     esi
0x1001c230  pop     ebx
0x1001c231  mov     ecx, [esp+0B4h+var_4]
0x1001c238  xor     ecx, esp; StackCookie
0x1001c23a  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001c23f  mov     esp, ebp
0x1001c241  pop     ebp
0x1001c242  retn    10h
0x1001c245  push    [esp+0C0h+var_AC]
0x1001c249  push    esi
0x1001c24a  push    ebx
0x1001c24b  push    edi
0x1001c24c  call    _ErrDispRenameTable@16; ErrDispRenameTable(x,x,x,x)
0x1001c251  mov     esi, eax
0x1001c253  test    esi, esi
0x1001c255  js      loc_1001C4CC
0x1001c25b  push    0; int
0x1001c25d  push    0; int
0x1001c25f  push    [esp+0C8h+var_AC]; int
0x1001c263  mov     [esp+0CCh+var_A4], 1
0x1001c26b  push    [esp+0CCh+var_A8]; int
0x1001c26f  push    ebx; int
0x1001c270  push    edi; sesid
0x1001c271  call    _ErrRelationshipUpdateNames@24; ErrRelationshipUpdateNames(x,x,x,x,x,x)
0x1001c276  mov     esi, eax
0x1001c278  test    esi, esi
0x1001c27a  js      loc_1001C4CC
0x1001c280  cmp     [esp+0C0h+var_B4], 0
0x1001c285  jz      loc_1001C4BE
0x1001c28b  lea     eax, [esp+0C0h+var_A0]
0x1001c28f  mov     edx, ebx
0x1001c291  push    eax; int
0x1001c292  lea     eax, [esp+0C4h+var_B0]
0x1001c296  mov     ecx, edi
0x1001c298  push    eax; int
0x1001c299  push    [esp+0C8h+var_AC]; Src
0x1001c29d  push    offset _wszTcObject; "Tables"
0x1001c2a2  call    _ErrFObjectReplicable2@24; ErrFObjectReplicable2(x,x,x,x,x,x)
0x1001c2a7  mov     esi, eax
0x1001c2a9  test    esi, esi
0x1001c2ab  js      loc_1001C4CC
0x1001c2b1  cmp     [esp+0C0h+var_B0], 0
0x1001c2b6  jnz     short loc_1001C2C2
0x1001c2b8  mov     esi, 0FFFFB0A9h
0x1001c2bd  jmp     loc_1001C4BA
0x1001c2c2  push    40h ; '@'; Size
0x1001c2c4  lea     eax, [esp+0C4h+var_74]
0x1001c2c8  push    0; Val
0x1001c2ca  push    eax; void *
0x1001c2cb  call    _memset
0x1001c2d0  mov     eax, [esp+0CCh+var_A8]
0x1001c2d4  add     esp, 0Ch
0x1001c2d7  mov     ecx, eax
0x1001c2d9  mov     [esp+0C0h+var_88], 3
0x1001c2e1  mov     [esp+0C0h+var_84], eax
0x1001c2e5  lea     edx, [ecx+2]
0x1001c2e8  nop     dword ptr [eax+eax+00000000h]
0x1001c2f0  mov     ax, [ecx]
0x1001c2f3  add     ecx, 2
0x1001c2f6  test    ax, ax
0x1001c2f9  jnz     short loc_1001C2F0
0x1001c2fb  sub     ecx, edx
0x1001c2fd  mov     edx, [esp+0C0h+var_AC]
0x1001c301  sar     ecx, 1
0x1001c303  mov     [esp+0C0h+var_7C], edx
0x1001c307  lea     eax, [ecx+ecx]
0x1001c30a  mov     ecx, edx
0x1001c30c  mov     [esp+0C0h+var_80], eax
0x1001c310  lea     esi, [ecx+2]
0x1001c313  mov     ax, [ecx]
0x1001c316  add     ecx, 2
0x1001c319  test    ax, ax
0x1001c31c  jnz     short loc_1001C313
0x1001c31e  sub     ecx, esi
0x1001c320  mov     [esp+0C0h+var_98], 28h ; '('
0x1001c328  sar     ecx, 1
0x1001c32a  push    5
0x1001c32c  lea     eax, [ecx+ecx]
0x1001c32f  mov     [esp+0C4h+var_78], eax
0x1001c333  lea     eax, [esp+0C4h+var_2C]
0x1001c33a  mov     [esp+0C4h+var_8C], eax
0x1001c33e  lea     eax, [esp+0C4h+var_98]
0x1001c342  push    eax
0x1001c343  push    edx
0x1001c344  push    offset _wszTcObject; "Tables"
0x1001c349  push    0
0x1001c34b  push    ebx
0x1001c34c  push    edi
0x1001c34d  call    _ErrDispGetObjectInfo@28; ErrDispGetObjectInfo(x,x,x,x,x,x,x)
0x1001c352  mov     esi, eax
0x1001c354  test    esi, esi
0x1001c356  js      loc_1001C4CC
0x1001c35c  lea     eax, [esp+0C0h+var_28]
0x1001c363  mov     [esp+0C0h+var_58], 4
0x1001c36b  mov     [esp+0C0h+var_5C], eax
0x1001c36f  lea     eax, [esp+0C0h+var_88]
0x1001c373  push    eax
0x1001c374  push    ebx
0x1001c375  push    edi
0x1001c376  call    _ErrReplSchChangeInsert@12; ErrReplSchChangeInsert(x,x,x)
0x1001c37b  mov     esi, eax
0x1001c37d  test    esi, esi
0x1001c37f  js      loc_1001C4CC
0x1001c385  push    ebx
0x1001c386  push    edi
0x1001c387  call    _ErrRepSetLastSchema@8; ErrRepSetLastSchema(x,x)
0x1001c38c  mov     esi, eax
0x1001c38e  test    esi, esi
0x1001c390  js      loc_1001C4CC
0x1001c396  cmp     [esp+0C0h+var_28], 1
0x1001c39e  jnz     loc_1001C4B8
0x1001c3a4  mov     eax, _rgrepdbinfo[ebx*4]
0x1001c3ab  mov     ecx, [esp+0C0h+var_A8]
0x1001c3af  mov     [esp+0C0h+var_A0], eax
0x1001c3b3  mov     edx, [eax+8]
0x1001c3b6  mov     [esp+0C0h+var_B4], edx
0x1001c3ba  lea     esi, [ecx+2]
0x1001c3bd  nop     dword ptr [eax]
0x1001c3c0  mov     ax, [ecx]
0x1001c3c3  add     ecx, 2
0x1001c3c6  test    ax, ax
0x1001c3c9  jnz     short loc_1001C3C0
0x1001c3cb  sub     ecx, esi
0x1001c3cd  sar     ecx, 1
0x1001c3cf  lea     eax, [ecx+ecx]
0x1001c3d2  mov     [esp+0C0h+var_B0], eax
0x1001c3d6  cmp     edx, 800h
0x1001c3dc  jnb     loc_1001C513
0x1001c3e2  cmp     edx, _tableidInit
0x1001c3e8  jb      loc_1001C513
0x1001c3ee  mov     ecx, edx
0x1001c3f0  mov     edx, edi
0x1001c3f2  shl     ecx, 4
0x1001c3f5  lfence
0x1001c3f8  push    1
0x1001c3fa  push    [esp+0C4h+var_B0]
0x1001c3fe  mov     eax, _rgvtdef[ecx]
0x1001c404  cmp     eax, 0FFFFFFFFh
0x1001c407  mov     esi, dword_101636CC[ecx]
0x1001c40d  push    [esp+0C8h+var_A8]
0x1001c411  cmovnz  edx, eax
0x1001c414  push    dword_101636C4[ecx]; unsigned int
0x1001c41a  mov     esi, [esi+64h]
0x1001c41d  mov     ecx, esi
0x1001c41f  push    edx; void *
  ... truncated ...
```
