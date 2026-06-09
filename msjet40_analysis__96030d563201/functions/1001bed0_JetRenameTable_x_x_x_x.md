# JetRenameTable(x,x,x,x)

- ea: `0x1001bed0`
- end: `0x1001c3f2`
- name: `_JetRenameTable@16`
- size: `1314`
- prototype: `int __stdcall(Session *, int, void *Src, int)`
- caller_count: `0`
- callee_count: `23`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x1001bed0`
- `0x100352b0`
- `0x1003d9f0`
- `0x1003e650`
- `0x1003e7a0`
- `0x1003e870`
- `0x10042fb0`
- `0x100431f0`
- `0x10043260`
- `0x10043660`
- `0x10044b20`
- `0x10044c00`
- `0x10044e00`
- `0x1004d790`
- `0x1004d830`
- `0x1004d890`
- `0x10050000`
- `0x10113c9c`
- `0x10116ef0`
- `0x1011b238`
- `0x1011d044`
- `0x10122f60`
- `0x1012398c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001bf27`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001bfe2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001c047`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001c08d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001c0d3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001c3a4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001c3d0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001bf27`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001bfe2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001c047`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001c08d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001c0d3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001c3a4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001c3d0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1001bf0e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1001bf0e`

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
      updated = (*(int (__thiscall **)(_DWORD, Session *, int, int, int, int))(dword_1016362C[4 * v11] + 100))(
                  *(_DWORD *)(dword_1016362C[4 * v11] + 100),
                  v9,
                  dword_10163624[4 * v11],
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
0x1001bed0  mov     edi, edi
0x1001bed2  push    ebp
0x1001bed3  mov     ebp, esp
0x1001bed5  and     esp, 0FFFFFFF8h
0x1001bed8  sub     esp, 0B4h
0x1001bede  mov     eax, ___security_cookie
0x1001bee3  xor     eax, esp
0x1001bee5  mov     [esp+0B4h+var_4], eax
0x1001beec  mov     eax, [ebp+arg_C]
0x1001beef  push    ebx
0x1001bef0  mov     ebx, [ebp+arg_4]
0x1001bef3  push    esi
0x1001bef4  mov     esi, [ebp+Src]
0x1001bef7  push    edi
0x1001bef8  push    _critJet; lpCriticalSection
0x1001befe  mov     [esp+0C4h+var_A8], esi
0x1001bf02  mov     [esp+0C4h+var_AC], eax
0x1001bf06  mov     [esp+0C4h+var_A4], 0
0x1001bf0e  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1001bf14  mov     edi, [ebp+sesid]
0x1001bf17  push    edi
0x1001bf18  call    _FValidSesid@4; FValidSesid(x)
0x1001bf1d  test    eax, eax
0x1001bf1f  jnz     short loc_1001BF49
0x1001bf21  push    _critJet; lpCriticalSection
0x1001bf27  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001bf2d  mov     eax, 0FFFFFBB0h
0x1001bf32  pop     edi
0x1001bf33  pop     esi
0x1001bf34  pop     ebx
0x1001bf35  mov     ecx, [esp+0B4h+var_4]
0x1001bf3c  xor     ecx, esp; StackCookie
0x1001bf3e  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001bf43  mov     esp, ebp
0x1001bf45  pop     ebp
0x1001bf46  retn    10h
0x1001bf49  cmp     ebx, _dbidInit
0x1001bf4f  jb      loc_1001C3CA
0x1001bf55  cmp     ebx, 100h
0x1001bf5b  jnb     loc_1001C3CA
0x1001bf61  cmp     _mpdbidpvdbfndef[ebx*4], offset _vdbfndefInvalidDbid
0x1001bf6c  jz      loc_1001C3CA
0x1001bf72  lea     eax, _mpdbidiiscb[ebx*4]
0x1001bf79  mov     edx, ebx
0x1001bf7b  mov     ecx, edi
0x1001bf7d  mov     [esp+0C0h+var_B4], eax
0x1001bf81  call    _IsJetIsam@8; IsJetIsam(x,x)
0x1001bf86  test    eax, eax
0x1001bf88  jnz     short loc_1001C003
0x1001bf8a  mov     eax, _mpdbidiiscb[ebx*4]
0x1001bf91  lea     eax, [eax+eax*4]
0x1001bf94  cmp     Src[eax*4], 0
0x1001bf9c  jz      short loc_1001BFAB
0x1001bf9e  cmp     _mpdbidpvdbfndef[ebx*4], offset _vdbfndefRdb
0x1001bfa9  jnz     short loc_1001C00E
0x1001bfab  push    edi
0x1001bfac  call    _ErrIsamBeginTransaction@4; ErrIsamBeginTransaction(x)
0x1001bfb1  mov     [esp+0C0h+var_B0], eax
0x1001bfb5  test    eax, eax
0x1001bfb7  js      short loc_1001BFDC
0x1001bfb9  lea     eax, [esp+0C0h+var_B4]
0x1001bfbd  mov     edx, ebx
0x1001bfbf  push    eax; int
0x1001bfc0  push    esi; Src
0x1001bfc1  mov     ecx, edi; int
0x1001bfc3  call    _ErrREPRenameTableCheck@16; ErrREPRenameTableCheck(x,x,x,x)
0x1001bfc8  mov     [esp+0C0h+var_B0], eax
0x1001bfcc  test    eax, eax
0x1001bfce  jns     loc_1001C0F5
0x1001bfd4  push    0; char
0x1001bfd6  push    edi; Session *
0x1001bfd7  call    _ErrIsamRollback@8; ErrIsamRollback(x,x)
0x1001bfdc  push    _critJet; lpCriticalSection
0x1001bfe2  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001bfe8  mov     eax, [esp+0C0h+var_B0]
0x1001bfec  pop     edi
0x1001bfed  pop     esi
0x1001bfee  pop     ebx
0x1001bfef  mov     ecx, [esp+0B4h+var_4]
0x1001bff6  xor     ecx, esp; StackCookie
0x1001bff8  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001bffd  mov     esp, ebp
0x1001bfff  pop     ebp
0x1001c000  retn    10h
0x1001c003  lea     eax, _mpdbidiiscb[ebx*4]
0x1001c00a  mov     [esp+0C0h+var_B4], eax
0x1001c00e  lea     eax, [esp+0C0h+var_9C]
0x1001c012  push    eax
0x1001c013  push    esi
0x1001c014  push    offset _wszTcObject; "Tables"
0x1001c019  push    ebx
0x1001c01a  push    edi
0x1001c01b  call    _ErrDispGetObjidFromName@20; ErrDispGetObjidFromName(x,x,x,x,x)
0x1001c020  mov     [esp+0C0h+var_B0], eax
0x1001c024  test    eax, eax
0x1001c026  js      short loc_1001BFDC
0x1001c028  mov     eax, [esp+0C0h+var_B4]
0x1001c02c  mov     eax, [eax]
0x1001c02e  lea     eax, [eax+eax*4]
0x1001c031  mov     eax, Src[eax*4]
0x1001c038  test    eax, eax
0x1001c03a  jnz     short loc_1001C066
0x1001c03c  push    _critJet; lpCriticalSection
0x1001c042  mov     esi, 0FFFFFC17h
0x1001c047  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001c04d  mov     eax, esi
0x1001c04f  pop     edi
0x1001c050  pop     esi
0x1001c051  pop     ebx
0x1001c052  mov     ecx, [esp+0B4h+var_4]
0x1001c059  xor     ecx, esp; StackCookie
0x1001c05b  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001c060  mov     esp, ebp
0x1001c062  pop     ebp
0x1001c063  retn    10h
0x1001c066  push    0
0x1001c068  lea     ecx, [esp+0C4h+var_B4]
0x1001c06c  mov     edx, ebx
0x1001c06e  push    ecx
0x1001c06f  push    0
0x1001c071  push    eax
0x1001c072  push    [esp+0D0h+var_9C]
0x1001c076  mov     ecx, edi
0x1001c078  call    _ErrSecCollectAccess@28; ErrSecCollectAccess(x,x,x,x,x,x,x)
0x1001c07d  mov     [esp+0C0h+var_B0], eax
0x1001c081  test    eax, eax
0x1001c083  jns     short loc_1001C0AC
0x1001c085  push    _critJet; lpCriticalSection
0x1001c08b  mov     esi, eax
0x1001c08d  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001c093  mov     eax, esi
0x1001c095  pop     edi
0x1001c096  pop     esi
0x1001c097  pop     ebx
0x1001c098  mov     ecx, [esp+0B4h+var_4]
0x1001c09f  xor     ecx, esp; StackCookie
0x1001c0a1  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001c0a6  mov     esp, ebp
0x1001c0a8  pop     ebp
0x1001c0a9  retn    10h
0x1001c0ac  test    byte ptr [esp+0C0h+var_B4], 8
0x1001c0b1  jnz     loc_1001BFAB
0x1001c0b7  push    0; int
0x1001c0b9  push    0; int
0x1001c0bb  push    0; int
0x1001c0bd  push    0FFFFE016h; int
0x1001c0c2  push    0; void *
0x1001c0c4  push    0; void *
0x1001c0c6  push    esi; Src
0x1001c0c7  push    edi; int
0x1001c0c8  call    _UtilSetErrorInfoReal@32; UtilSetErrorInfoReal(x,x,x,x,x,x,x,x)
0x1001c0cd  push    _critJet; lpCriticalSection
0x1001c0d3  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001c0d9  mov     eax, 0FFFFF88Dh
0x1001c0de  pop     edi
0x1001c0df  pop     esi
0x1001c0e0  pop     ebx
0x1001c0e1  mov     ecx, [esp+0B4h+var_4]
0x1001c0e8  xor     ecx, esp; StackCookie
0x1001c0ea  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001c0ef  mov     esp, ebp
0x1001c0f1  pop     ebp
0x1001c0f2  retn    10h
0x1001c0f5  push    [esp+0C0h+var_AC]
0x1001c0f9  push    esi
0x1001c0fa  push    ebx
0x1001c0fb  push    edi
0x1001c0fc  call    _ErrDispRenameTable@16; ErrDispRenameTable(x,x,x,x)
0x1001c101  mov     esi, eax
0x1001c103  test    esi, esi
0x1001c105  js      loc_1001C37C
0x1001c10b  push    0; int
0x1001c10d  push    0; int
0x1001c10f  push    [esp+0C8h+var_AC]; int
0x1001c113  mov     [esp+0CCh+var_A4], 1
0x1001c11b  push    [esp+0CCh+var_A8]; int
0x1001c11f  push    ebx; int
0x1001c120  push    edi; sesid
0x1001c121  call    _ErrRelationshipUpdateNames@24; ErrRelationshipUpdateNames(x,x,x,x,x,x)
0x1001c126  mov     esi, eax
0x1001c128  test    esi, esi
0x1001c12a  js      loc_1001C37C
0x1001c130  cmp     [esp+0C0h+var_B4], 0
0x1001c135  jz      loc_1001C36E
0x1001c13b  lea     eax, [esp+0C0h+var_A0]
0x1001c13f  mov     edx, ebx
0x1001c141  push    eax; int
0x1001c142  lea     eax, [esp+0C4h+var_B0]
0x1001c146  mov     ecx, edi
0x1001c148  push    eax; int
0x1001c149  push    [esp+0C8h+var_AC]; Src
0x1001c14d  push    offset _wszTcObject; "Tables"
0x1001c152  call    _ErrFObjectReplicable2@24; ErrFObjectReplicable2(x,x,x,x,x,x)
0x1001c157  mov     esi, eax
0x1001c159  test    esi, esi
0x1001c15b  js      loc_1001C37C
0x1001c161  cmp     [esp+0C0h+var_B0], 0
0x1001c166  jnz     short loc_1001C172
0x1001c168  mov     esi, 0FFFFB0A9h
0x1001c16d  jmp     loc_1001C36A
0x1001c172  push    40h ; '@'; Size
0x1001c174  lea     eax, [esp+0C4h+var_74]
0x1001c178  push    0; Val
0x1001c17a  push    eax; void *
0x1001c17b  call    _memset
0x1001c180  mov     eax, [esp+0CCh+var_A8]
0x1001c184  add     esp, 0Ch
0x1001c187  mov     ecx, eax
0x1001c189  mov     [esp+0C0h+var_88], 3
0x1001c191  mov     [esp+0C0h+var_84], eax
0x1001c195  lea     edx, [ecx+2]
0x1001c198  nop     dword ptr [eax+eax+00000000h]
0x1001c1a0  mov     ax, [ecx]
0x1001c1a3  add     ecx, 2
0x1001c1a6  test    ax, ax
0x1001c1a9  jnz     short loc_1001C1A0
0x1001c1ab  sub     ecx, edx
0x1001c1ad  mov     edx, [esp+0C0h+var_AC]
0x1001c1b1  sar     ecx, 1
0x1001c1b3  mov     [esp+0C0h+var_7C], edx
0x1001c1b7  lea     eax, [ecx+ecx]
0x1001c1ba  mov     ecx, edx
0x1001c1bc  mov     [esp+0C0h+var_80], eax
0x1001c1c0  lea     esi, [ecx+2]
0x1001c1c3  mov     ax, [ecx]
0x1001c1c6  add     ecx, 2
0x1001c1c9  test    ax, ax
0x1001c1cc  jnz     short loc_1001C1C3
0x1001c1ce  sub     ecx, esi
0x1001c1d0  mov     [esp+0C0h+var_98], 28h ; '('
0x1001c1d8  sar     ecx, 1
0x1001c1da  push    5
0x1001c1dc  lea     eax, [ecx+ecx]
0x1001c1df  mov     [esp+0C4h+var_78], eax
0x1001c1e3  lea     eax, [esp+0C4h+var_2C]
0x1001c1ea  mov     [esp+0C4h+var_8C], eax
0x1001c1ee  lea     eax, [esp+0C4h+var_98]
0x1001c1f2  push    eax
0x1001c1f3  push    edx
0x1001c1f4  push    offset _wszTcObject; "Tables"
0x1001c1f9  push    0
0x1001c1fb  push    ebx
0x1001c1fc  push    edi
0x1001c1fd  call    _ErrDispGetObjectInfo@28; ErrDispGetObjectInfo(x,x,x,x,x,x,x)
0x1001c202  mov     esi, eax
0x1001c204  test    esi, esi
0x1001c206  js      loc_1001C37C
0x1001c20c  lea     eax, [esp+0C0h+var_28]
0x1001c213  mov     [esp+0C0h+var_58], 4
0x1001c21b  mov     [esp+0C0h+var_5C], eax
0x1001c21f  lea     eax, [esp+0C0h+var_88]
0x1001c223  push    eax
0x1001c224  push    ebx
0x1001c225  push    edi
0x1001c226  call    _ErrReplSchChangeInsert@12; ErrReplSchChangeInsert(x,x,x)
0x1001c22b  mov     esi, eax
0x1001c22d  test    esi, esi
0x1001c22f  js      loc_1001C37C
0x1001c235  push    ebx
0x1001c236  push    edi
0x1001c237  call    _ErrRepSetLastSchema@8; ErrRepSetLastSchema(x,x)
0x1001c23c  mov     esi, eax
0x1001c23e  test    esi, esi
0x1001c240  js      loc_1001C37C
0x1001c246  cmp     [esp+0C0h+var_28], 1
0x1001c24e  jnz     loc_1001C368
0x1001c254  mov     eax, _rgrepdbinfo[ebx*4]
0x1001c25b  mov     ecx, [esp+0C0h+var_A8]
0x1001c25f  mov     [esp+0C0h+var_A0], eax
0x1001c263  mov     edx, [eax+8]
0x1001c266  mov     [esp+0C0h+var_B4], edx
0x1001c26a  lea     esi, [ecx+2]
0x1001c26d  nop     dword ptr [eax]
0x1001c270  mov     ax, [ecx]
0x1001c273  add     ecx, 2
0x1001c276  test    ax, ax
0x1001c279  jnz     short loc_1001C270
0x1001c27b  sub     ecx, esi
0x1001c27d  sar     ecx, 1
0x1001c27f  lea     eax, [ecx+ecx]
0x1001c282  mov     [esp+0C0h+var_B0], eax
0x1001c286  cmp     edx, 800h
0x1001c28c  jnb     loc_1001C3C3
0x1001c292  cmp     edx, _tableidInit
0x1001c298  jb      loc_1001C3C3
0x1001c29e  mov     ecx, edx
0x1001c2a0  mov     edx, edi
0x1001c2a2  shl     ecx, 4
0x1001c2a5  lfence
0x1001c2a8  push    1
0x1001c2aa  push    [esp+0C4h+var_B0]
0x1001c2ae  mov     eax, _rgvtdef[ecx]
0x1001c2b4  cmp     eax, 0FFFFFFFFh
0x1001c2b7  mov     esi, dword_1016362C[ecx]
0x1001c2bd  push    [esp+0C8h+var_A8]
0x1001c2c1  cmovnz  edx, eax
0x1001c2c4  push    dword_10163624[ecx]; unsigned int
0x1001c2ca  mov     esi, [esi+64h]
0x1001c2cd  mov     ecx, esi
0x1001c2cf  push    edx; void *
  ... truncated ...
```
