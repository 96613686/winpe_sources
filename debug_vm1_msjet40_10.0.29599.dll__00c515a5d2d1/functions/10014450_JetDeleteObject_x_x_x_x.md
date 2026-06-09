# JetDeleteObject(x,x,x,x)

- ea: `0x10014450`
- end: `0x10014883`
- name: `_JetDeleteObject@16`
- size: `1075`
- prototype: `int __stdcall(Session *, int, int, int)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x10033ef0`

## callees

- `0x10012a80`
- `0x10014380`
- `0x10014450`
- `0x1003a840`
- `0x1003a970`
- `0x1003e7e0`
- `0x1003e930`
- `0x1003ea00`
- `0x10043140`
- `0x100433f0`
- `0x1004d920`
- `0x1004d9c0`
- `0x1004da20`
- `0x101170a0`
- `0x1011b3e8`
- `0x1011d1f2`
- `0x10123110`
- `0x10123b3c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001449b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10014521`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10014573`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100145ff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10014657`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100146a8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10014810`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10014861`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001449b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10014521`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10014573`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100145ff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10014657`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100146a8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10014810`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10014861`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10014482`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10014482`

## pseudocode

```c
int __stdcall JetDeleteObject(Session *a1, unsigned int a2, _WORD *a3, char *Src)
{
  _WORD *v4; // esi
  char *v5; // edi
  int v7; // eax
  unsigned int v8; // eax
  int v9; // ecx
  int v10; // eax
  int Schema; // esi
  int v12; // eax
  __int16 v14; // ax
  int v15; // edi
  int v16; // eax
  int ObjectInfo; // [esp+14h] [ebp-ACh] BYREF
  int ObjidFromName; // [esp+18h] [ebp-A8h] BYREF
  int v19; // [esp+1Ch] [ebp-A4h] BYREF
  int v20; // [esp+20h] [ebp-A0h]
  int v21; // [esp+24h] [ebp-9Ch] BYREF
  _DWORD v22[4]; // [esp+28h] [ebp-98h] BYREF
  _DWORD v23[2]; // [esp+38h] [ebp-88h] BYREF
  int v24; // [esp+40h] [ebp-80h]
  char *v25; // [esp+44h] [ebp-7Ch]
  int v26; // [esp+48h] [ebp-78h]
  _BYTE v27[64]; // [esp+4Ch] [ebp-74h] BYREF
  char v28; // [esp+94h] [ebp-2Ch] BYREF
  int v29; // [esp+98h] [ebp-28h]

  v4 = a3;
  v5 = Src;
  EnterCriticalSection(critJet);
  if ( !FValidSesid(a1) )
  {
    LeaveCriticalSection(critJet);
    return -1104;
  }
  if ( a2 >= dbidInit && a2 < 0x100 && (int *)mpdbidpvdbfndef[a2] != vdbfndefInvalidDbid )
  {
    if ( !IsJetIsam(a1, a2) && (!*(&::Src + 5 * mpdbidiiscb[a2]) || (int *)mpdbidpvdbfndef[a2] == vdbfndefRdb) )
    {
      LeaveCriticalSection(critJet);
      return -1001;
    }
    v7 = ErrSecValidateAccess(a3, Src, 0, 0, 0x10000, a2);
    ObjidFromName = v7;
    if ( v7 )
    {
      if ( v7 < 0 && v7 != -1907
        || (ObjidFromName = ErrDispGetObjidFromName(a1, a2, L"Tables", L"MSysObjects", &v19), ObjidFromName < 0)
        || (ObjidFromName = ErrSecGetAccess((int)a1, a2, v19, 0, 0, 0, &ObjectInfo, 0), ObjidFromName < 0) )
      {
        LeaveCriticalSection(critJet);
        return ObjidFromName;
      }
      if ( (ObjectInfo & 0x80u) == 0 )
      {
        UtilSetErrorInfoReal((int)a1, L"MSysObjects", 0, 0, -8114, 0, 0, 0);
        LeaveCriticalSection(critJet);
        return -1907;
      }
    }
    v22[0] = 40;
    v22[3] = &v28;
    ObjectInfo = ErrDispGetObjectInfo(a1, a2, 0, a3, Src, v22, 5);
    if ( ObjectInfo < 0 )
      goto LABEL_19;
    if ( v29 == 1 && !WCSICMP(Src, wszMSysAccounts) || !WCSICMP(Src, wszMSysGroups) )
    {
      LeaveCriticalSection(critJet);
      return -1304;
    }
    ObjectInfo = ErrDispGetObjidFromName(a1, a2, a3, Src, &v21);
    if ( ObjectInfo < 0 || (ObjectInfo = ErrIsamBeginTransaction(a1), ObjectInfo < 0) )
    {
LABEL_19:
      LeaveCriticalSection(critJet);
      return ObjectInfo;
    }
    v8 = a2;
    v20 = (int)*(&rgrepdbinfo + a2);
    v9 = *(_DWORD *)(v20 + 228);
    if ( (v9 & 0x10) == 0 && (v9 & 1) != 0 )
    {
      v10 = ErrFObjectReplicable2((int)a3, Src, (int)&ObjidFromName, (int)&ObjectInfo);
      ObjectInfo = v10;
      if ( v10 < 0 )
      {
        Schema = v10;
        goto LABEL_43;
      }
      if ( ObjidFromName )
      {
        v12 = *(_DWORD *)(v20 + 228);
        if ( (v12 & 2) == 0 )
        {
          Schema = -20003;
          goto LABEL_43;
        }
        if ( (v12 & 0x80000) != 0 )
        {
          Schema = -20309;
          goto LABEL_43;
        }
        memset(v27, 0, sizeof(v27));
        v23[0] = 15;
        v23[1] = a3;
        if ( a3 )
        {
          while ( *v4++ )
            ;
          v24 = 2 * (v4 - (a3 + 1));
        }
        else
        {
          v24 = 0;
        }
        v25 = Src;
        do
        {
          v14 = *(_WORD *)v5;
          v5 += 2;
        }
        while ( v14 );
        v26 = 2 * ((v5 - (Src + 2)) >> 1);
        Schema = ErrReplSchChangeInsert(a1, a2, v23);
        if ( Schema < 0 )
          goto LABEL_43;
        Schema = ErrRepSetLastSchema(a1, a2);
        if ( Schema < 0 )
          goto LABEL_43;
      }
      v8 = a2;
    }
    Schema = ErrDeleteObject(a1, v8, v21);
    v15 = Schema;
    if ( Schema >= 0 )
    {
      v16 = ErrIsamCommitTransaction(a1, 0);
      Schema = v16;
      if ( v16 >= 0 )
      {
        if ( !v16 )
          Schema = v15;
        goto LABEL_44;
      }
    }
LABEL_43:
    ErrIsamRollback(a1, 0);
LABEL_44:
    LeaveCriticalSection(critJet);
    return Schema;
  }
  LeaveCriticalSection(critJet);
  return -1010;
}

```

## disassembly

```asm
0x10014450  mov     edi, edi
0x10014452  push    ebp
0x10014453  mov     ebp, esp
0x10014455  and     esp, 0FFFFFFF8h
0x10014458  sub     esp, 0B4h
0x1001445e  mov     eax, ___security_cookie
0x10014463  xor     eax, esp
0x10014465  mov     [esp+0B4h+var_4], eax
0x1001446c  mov     eax, [ebp+arg_4]
0x1001446f  push    ebx
0x10014470  push    esi
0x10014471  mov     esi, [ebp+arg_8]
0x10014474  push    edi
0x10014475  push    _critJet; lpCriticalSection
0x1001447b  mov     edi, [ebp+Src]
0x1001447e  mov     [esp+0C4h+var_B0], eax
0x10014482  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10014488  mov     ebx, [ebp+arg_0]
0x1001448b  push    ebx
0x1001448c  call    _FValidSesid@4; FValidSesid(x)
0x10014491  test    eax, eax
0x10014493  jnz     short loc_100144BD
0x10014495  push    _critJet; lpCriticalSection
0x1001449b  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100144a1  mov     eax, 0FFFFFBB0h
0x100144a6  pop     edi
0x100144a7  pop     esi
0x100144a8  pop     ebx
0x100144a9  mov     ecx, [esp+0B4h+var_4]
0x100144b0  xor     ecx, esp; StackCookie
0x100144b2  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100144b7  mov     esp, ebp
0x100144b9  pop     ebp
0x100144ba  retn    10h
0x100144bd  mov     eax, [esp+0C0h+var_B0]
0x100144c1  cmp     eax, _dbidInit
0x100144c7  jb      loc_1001485B
0x100144cd  cmp     eax, 100h
0x100144d2  jnb     loc_1001485B
0x100144d8  cmp     _mpdbidpvdbfndef[eax*4], offset _vdbfndefInvalidDbid
0x100144e3  jz      loc_1001485B
0x100144e9  mov     edx, eax
0x100144eb  mov     ecx, ebx
0x100144ed  call    _IsJetIsam@8; IsJetIsam(x,x)
0x100144f2  mov     ecx, [esp+0C0h+var_B0]
0x100144f6  test    eax, eax
0x100144f8  jnz     short loc_10014543
0x100144fa  mov     eax, _mpdbidiiscb[ecx*4]
0x10014501  lea     eax, [eax+eax*4]
0x10014504  cmp     Src[eax*4], 0
0x1001450c  jz      short loc_1001451B
0x1001450e  cmp     _mpdbidpvdbfndef[ecx*4], offset _vdbfndefRdb
0x10014519  jnz     short loc_10014543
0x1001451b  push    _critJet; lpCriticalSection
0x10014521  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10014527  mov     eax, 0FFFFFC17h
0x1001452c  pop     edi
0x1001452d  pop     esi
0x1001452e  pop     ebx
0x1001452f  mov     ecx, [esp+0B4h+var_4]
0x10014536  xor     ecx, esp; StackCookie
0x10014538  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001453d  mov     esp, ebp
0x1001453f  pop     ebp
0x10014540  retn    10h
0x10014543  push    ecx
0x10014544  push    10000h
0x10014549  push    0
0x1001454b  push    0
0x1001454d  push    edi
0x1001454e  mov     edx, ecx
0x10014550  mov     ecx, ebx
0x10014552  push    esi
0x10014553  call    _ErrSecValidateAccess@32; ErrSecValidateAccess(x,x,x,x,x,x,x,x)
0x10014558  mov     [esp+0C0h+var_A8], eax
0x1001455c  test    eax, eax
0x1001455e  jz      loc_10014621
0x10014564  jns     short loc_10014594
0x10014566  cmp     eax, 0FFFFF88Dh
0x1001456b  jz      short loc_10014594
0x1001456d  push    _critJet; lpCriticalSection
0x10014573  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10014579  mov     eax, [esp+0C0h+var_A8]
0x1001457d  pop     edi
0x1001457e  pop     esi
0x1001457f  pop     ebx
0x10014580  mov     ecx, [esp+0B4h+var_4]
0x10014587  xor     ecx, esp; StackCookie
0x10014589  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001458e  mov     esp, ebp
0x10014590  pop     ebp
0x10014591  retn    10h
0x10014594  lea     eax, [esp+0C0h+var_A4]
0x10014598  push    eax
0x10014599  push    offset _wszSoTable; "MSysObjects"
0x1001459e  push    offset _wszTcObject; "Tables"
0x100145a3  push    [esp+0CCh+var_B0]
0x100145a7  push    ebx
0x100145a8  call    _ErrDispGetObjidFromName@20; ErrDispGetObjidFromName(x,x,x,x,x)
0x100145ad  mov     [esp+0C0h+var_A8], eax
0x100145b1  test    eax, eax
0x100145b3  js      short loc_1001456D
0x100145b5  push    0
0x100145b7  lea     eax, [esp+0C4h+var_AC]
0x100145bb  push    eax
0x100145bc  push    0
0x100145be  push    0
0x100145c0  push    0
0x100145c2  push    [esp+0D4h+var_A4]
0x100145c6  push    [esp+0D8h+var_B0]
0x100145ca  push    ebx
0x100145cb  call    _ErrSecGetAccess@32; ErrSecGetAccess(x,x,x,x,x,x,x,x)
0x100145d0  mov     [esp+0C0h+var_A8], eax
0x100145d4  test    eax, eax
0x100145d6  js      short loc_1001456D
0x100145d8  test    byte ptr [esp+0C0h+var_AC], 80h
0x100145dd  jnz     short loc_10014621
0x100145df  push    0; int
0x100145e1  push    0; int
0x100145e3  push    0; int
0x100145e5  push    0FFFFE04Eh; int
0x100145ea  push    0; void *
0x100145ec  push    0; void *
0x100145ee  push    offset _wszSoTable; "MSysObjects"
0x100145f3  push    ebx; int
0x100145f4  call    _UtilSetErrorInfoReal@32; UtilSetErrorInfoReal(x,x,x,x,x,x,x,x)
0x100145f9  push    _critJet; lpCriticalSection
0x100145ff  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10014605  mov     eax, 0FFFFF88Dh
0x1001460a  pop     edi
0x1001460b  pop     esi
0x1001460c  pop     ebx
0x1001460d  mov     ecx, [esp+0B4h+var_4]
0x10014614  xor     ecx, esp; StackCookie
0x10014616  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001461b  mov     esp, ebp
0x1001461d  pop     ebp
0x1001461e  retn    10h
0x10014621  push    5
0x10014623  lea     eax, [esp+0C4h+var_2C]
0x1001462a  mov     [esp+0C4h+var_98], 28h ; '('
0x10014632  mov     [esp+0C4h+var_8C], eax
0x10014636  lea     eax, [esp+0C4h+var_98]
0x1001463a  push    eax
0x1001463b  push    edi
0x1001463c  push    esi
0x1001463d  push    0
0x1001463f  push    [esp+0D4h+var_B0]
0x10014643  push    ebx
0x10014644  call    _ErrDispGetObjectInfo@28; ErrDispGetObjectInfo(x,x,x,x,x,x,x)
0x10014649  mov     [esp+0C0h+var_AC], eax
0x1001464d  test    eax, eax
0x1001464f  jns     short loc_10014678
0x10014651  push    _critJet; lpCriticalSection
0x10014657  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001465d  mov     eax, [esp+0C0h+var_AC]
0x10014661  pop     edi
0x10014662  pop     esi
0x10014663  pop     ebx
0x10014664  mov     ecx, [esp+0B4h+var_4]
0x1001466b  xor     ecx, esp; StackCookie
0x1001466d  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10014672  mov     esp, ebp
0x10014674  pop     ebp
0x10014675  retn    10h
0x10014678  cmp     [esp+0C0h+var_28], 1
0x10014680  jnz     short loc_10014692
0x10014682  mov     edx, offset _wszMSysAccounts; "MSysAccounts"
0x10014687  mov     ecx, edi
0x10014689  call    _WCSICMP@8; WCSICMP(x,x)
0x1001468e  test    eax, eax
0x10014690  jz      short loc_100146A2
0x10014692  mov     edx, offset _wszMSysGroups; "MSysGroups"
0x10014697  mov     ecx, edi
0x10014699  call    _WCSICMP@8; WCSICMP(x,x)
0x1001469e  test    eax, eax
0x100146a0  jnz     short loc_100146CA
0x100146a2  push    _critJet; lpCriticalSection
0x100146a8  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100146ae  mov     eax, 0FFFFFAE8h
0x100146b3  pop     edi
0x100146b4  pop     esi
0x100146b5  pop     ebx
0x100146b6  mov     ecx, [esp+0B4h+var_4]
0x100146bd  xor     ecx, esp; StackCookie
0x100146bf  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100146c4  mov     esp, ebp
0x100146c6  pop     ebp
0x100146c7  retn    10h
0x100146ca  lea     eax, [esp+0C0h+var_9C]
0x100146ce  push    eax
0x100146cf  push    edi
0x100146d0  push    esi
0x100146d1  push    [esp+0CCh+var_B0]
0x100146d5  push    ebx
0x100146d6  call    _ErrDispGetObjidFromName@20; ErrDispGetObjidFromName(x,x,x,x,x)
0x100146db  mov     [esp+0C0h+var_AC], eax
0x100146df  test    eax, eax
0x100146e1  js      loc_10014651
0x100146e7  push    ebx
0x100146e8  call    _ErrIsamBeginTransaction@4; ErrIsamBeginTransaction(x)
0x100146ed  mov     [esp+0C0h+var_AC], eax
0x100146f1  test    eax, eax
0x100146f3  js      loc_10014651
0x100146f9  mov     eax, [esp+0C0h+var_B0]
0x100146fd  mov     ecx, _rgrepdbinfo[eax*4]
0x10014704  mov     [esp+0C0h+var_A0], ecx
0x10014708  mov     ecx, [ecx+0E4h]
0x1001470e  test    cl, 10h
0x10014711  jnz     loc_10014833
0x10014717  test    cl, 1
0x1001471a  jz      loc_10014833
0x10014720  lea     ecx, [esp+0C0h+var_AC]
0x10014724  mov     edx, eax
0x10014726  push    ecx; int
0x10014727  lea     ecx, [esp+0C4h+var_A8]
0x1001472b  push    ecx; int
0x1001472c  push    edi; Src
0x1001472d  push    esi; int
0x1001472e  mov     ecx, ebx
0x10014730  call    _ErrFObjectReplicable2@24; ErrFObjectReplicable2(x,x,x,x,x,x)
0x10014735  mov     [esp+0C0h+var_AC], eax
0x10014739  test    eax, eax
0x1001473b  jns     short loc_10014744
0x1001473d  mov     esi, eax
0x1001473f  jmp     loc_10014802
0x10014744  cmp     [esp+0C0h+var_A8], 0
0x10014749  jz      loc_1001482F
0x1001474f  mov     eax, [esp+0C0h+var_A0]
0x10014753  mov     eax, [eax+0E4h]
0x10014759  test    al, 2
0x1001475b  jnz     short loc_10014767
0x1001475d  mov     esi, 0FFFFB1DDh
0x10014762  jmp     loc_10014802
0x10014767  test    eax, 80000h
0x1001476c  jz      short loc_10014778
0x1001476e  mov     esi, 0FFFFB0ABh
0x10014773  jmp     loc_10014802
0x10014778  push    40h ; '@'; Size
0x1001477a  lea     eax, [esp+0C4h+var_74]
0x1001477e  push    0; Val
0x10014780  push    eax; void *
0x10014781  call    _memset
0x10014786  add     esp, 0Ch
0x10014789  mov     [esp+0C0h+var_88], 0Fh
0x10014791  mov     [esp+0C0h+var_84], esi
0x10014795  test    esi, esi
0x10014797  jz      short loc_100147B8
0x10014799  lea     ecx, [esi+2]
0x1001479c  nop     dword ptr [eax+00h]
0x100147a0  mov     ax, [esi]
0x100147a3  add     esi, 2
0x100147a6  test    ax, ax
0x100147a9  jnz     short loc_100147A0
0x100147ab  sub     esi, ecx
0x100147ad  sar     esi, 1
0x100147af  lea     eax, [esi+esi]
0x100147b2  mov     [esp+0C0h+var_80], eax
0x100147b6  jmp     short loc_100147C0
0x100147b8  mov     [esp+0C0h+var_80], 0
0x100147c0  mov     [esp+0C0h+var_7C], edi
0x100147c4  lea     ecx, [edi+2]
0x100147c7  mov     ax, [edi]
0x100147ca  add     edi, 2
0x100147cd  test    ax, ax
0x100147d0  jnz     short loc_100147C7
0x100147d2  sub     edi, ecx
0x100147d4  sar     edi, 1
0x100147d6  lea     eax, [edi+edi]
0x100147d9  mov     [esp+0C0h+var_78], eax
0x100147dd  lea     eax, [esp+0C0h+var_88]
0x100147e1  push    eax
0x100147e2  push    [esp+0C4h+var_B0]
0x100147e6  push    ebx
0x100147e7  call    _ErrReplSchChangeInsert@12; ErrReplSchChangeInsert(x,x,x)
0x100147ec  mov     esi, eax
0x100147ee  test    esi, esi
0x100147f0  js      short loc_10014802
0x100147f2  push    [esp+0C0h+var_B0]
0x100147f6  push    ebx
0x100147f7  call    _ErrRepSetLastSchema@8; ErrRepSetLastSchema(x,x)
0x100147fc  mov     esi, eax
0x100147fe  test    esi, esi
0x10014800  jns     short loc_1001482F
0x10014802  push    0; char
0x10014804  push    ebx; Session *
0x10014805  call    _ErrIsamRollback@8; ErrIsamRollback(x,x)
0x1001480a  push    _critJet; lpCriticalSection
0x10014810  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10014816  mov     eax, esi
0x10014818  pop     edi
0x10014819  pop     esi
0x1001481a  pop     ebx
0x1001481b  mov     ecx, [esp+0B4h+var_4]
0x10014822  xor     ecx, esp; StackCookie
0x10014824  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10014829  mov     esp, ebp
0x1001482b  pop     ebp
0x1001482c  retn    10h
0x1001482f  mov     eax, [esp+0C0h+var_B0]
  ... truncated ...
```
