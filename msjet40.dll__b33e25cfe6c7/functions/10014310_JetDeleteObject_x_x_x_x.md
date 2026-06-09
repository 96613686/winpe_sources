# JetDeleteObject(x,x,x,x)

- ea: `0x10014310`
- end: `0x10014743`
- name: `_JetDeleteObject@16`
- size: `1075`
- prototype: `int __stdcall(Session *, int, int, int)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x10033d50`

## callees

- `0x10012940`
- `0x10014240`
- `0x10014310`
- `0x1003a6c0`
- `0x1003a7f0`
- `0x1003e650`
- `0x1003e7a0`
- `0x1003e870`
- `0x10042fb0`
- `0x10043260`
- `0x1004d790`
- `0x1004d830`
- `0x1004d890`
- `0x10116ef0`
- `0x1011b238`
- `0x1011d044`
- `0x10122f60`
- `0x1012398c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001435b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100143e1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10014433`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100144bf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10014517`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10014568`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100146d0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10014721`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001435b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100143e1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10014433`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100144bf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10014517`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10014568`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100146d0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10014721`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10014342`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10014342`

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
0x10014310  mov     edi, edi
0x10014312  push    ebp
0x10014313  mov     ebp, esp
0x10014315  and     esp, 0FFFFFFF8h
0x10014318  sub     esp, 0B4h
0x1001431e  mov     eax, ___security_cookie
0x10014323  xor     eax, esp
0x10014325  mov     [esp+0B4h+var_4], eax
0x1001432c  mov     eax, [ebp+arg_4]
0x1001432f  push    ebx
0x10014330  push    esi
0x10014331  mov     esi, [ebp+arg_8]
0x10014334  push    edi
0x10014335  push    _critJet; lpCriticalSection
0x1001433b  mov     edi, [ebp+Src]
0x1001433e  mov     [esp+0C4h+var_B0], eax
0x10014342  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10014348  mov     ebx, [ebp+arg_0]
0x1001434b  push    ebx
0x1001434c  call    _FValidSesid@4; FValidSesid(x)
0x10014351  test    eax, eax
0x10014353  jnz     short loc_1001437D
0x10014355  push    _critJet; lpCriticalSection
0x1001435b  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10014361  mov     eax, 0FFFFFBB0h
0x10014366  pop     edi
0x10014367  pop     esi
0x10014368  pop     ebx
0x10014369  mov     ecx, [esp+0B4h+var_4]
0x10014370  xor     ecx, esp; StackCookie
0x10014372  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10014377  mov     esp, ebp
0x10014379  pop     ebp
0x1001437a  retn    10h
0x1001437d  mov     eax, [esp+0C0h+var_B0]
0x10014381  cmp     eax, _dbidInit
0x10014387  jb      loc_1001471B
0x1001438d  cmp     eax, 100h
0x10014392  jnb     loc_1001471B
0x10014398  cmp     _mpdbidpvdbfndef[eax*4], offset _vdbfndefInvalidDbid
0x100143a3  jz      loc_1001471B
0x100143a9  mov     edx, eax
0x100143ab  mov     ecx, ebx
0x100143ad  call    _IsJetIsam@8; IsJetIsam(x,x)
0x100143b2  mov     ecx, [esp+0C0h+var_B0]
0x100143b6  test    eax, eax
0x100143b8  jnz     short loc_10014403
0x100143ba  mov     eax, _mpdbidiiscb[ecx*4]
0x100143c1  lea     eax, [eax+eax*4]
0x100143c4  cmp     Src[eax*4], 0
0x100143cc  jz      short loc_100143DB
0x100143ce  cmp     _mpdbidpvdbfndef[ecx*4], offset _vdbfndefRdb
0x100143d9  jnz     short loc_10014403
0x100143db  push    _critJet; lpCriticalSection
0x100143e1  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100143e7  mov     eax, 0FFFFFC17h
0x100143ec  pop     edi
0x100143ed  pop     esi
0x100143ee  pop     ebx
0x100143ef  mov     ecx, [esp+0B4h+var_4]
0x100143f6  xor     ecx, esp; StackCookie
0x100143f8  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100143fd  mov     esp, ebp
0x100143ff  pop     ebp
0x10014400  retn    10h
0x10014403  push    ecx
0x10014404  push    10000h
0x10014409  push    0
0x1001440b  push    0
0x1001440d  push    edi
0x1001440e  mov     edx, ecx
0x10014410  mov     ecx, ebx
0x10014412  push    esi
0x10014413  call    _ErrSecValidateAccess@32; ErrSecValidateAccess(x,x,x,x,x,x,x,x)
0x10014418  mov     [esp+0C0h+var_A8], eax
0x1001441c  test    eax, eax
0x1001441e  jz      loc_100144E1
0x10014424  jns     short loc_10014454
0x10014426  cmp     eax, 0FFFFF88Dh
0x1001442b  jz      short loc_10014454
0x1001442d  push    _critJet; lpCriticalSection
0x10014433  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10014439  mov     eax, [esp+0C0h+var_A8]
0x1001443d  pop     edi
0x1001443e  pop     esi
0x1001443f  pop     ebx
0x10014440  mov     ecx, [esp+0B4h+var_4]
0x10014447  xor     ecx, esp; StackCookie
0x10014449  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001444e  mov     esp, ebp
0x10014450  pop     ebp
0x10014451  retn    10h
0x10014454  lea     eax, [esp+0C0h+var_A4]
0x10014458  push    eax
0x10014459  push    offset _wszSoTable; "MSysObjects"
0x1001445e  push    offset _wszTcObject; "Tables"
0x10014463  push    [esp+0CCh+var_B0]
0x10014467  push    ebx
0x10014468  call    _ErrDispGetObjidFromName@20; ErrDispGetObjidFromName(x,x,x,x,x)
0x1001446d  mov     [esp+0C0h+var_A8], eax
0x10014471  test    eax, eax
0x10014473  js      short loc_1001442D
0x10014475  push    0
0x10014477  lea     eax, [esp+0C4h+var_AC]
0x1001447b  push    eax
0x1001447c  push    0
0x1001447e  push    0
0x10014480  push    0
0x10014482  push    [esp+0D4h+var_A4]
0x10014486  push    [esp+0D8h+var_B0]
0x1001448a  push    ebx
0x1001448b  call    _ErrSecGetAccess@32; ErrSecGetAccess(x,x,x,x,x,x,x,x)
0x10014490  mov     [esp+0C0h+var_A8], eax
0x10014494  test    eax, eax
0x10014496  js      short loc_1001442D
0x10014498  test    byte ptr [esp+0C0h+var_AC], 80h
0x1001449d  jnz     short loc_100144E1
0x1001449f  push    0; int
0x100144a1  push    0; int
0x100144a3  push    0; int
0x100144a5  push    0FFFFE04Eh; int
0x100144aa  push    0; void *
0x100144ac  push    0; void *
0x100144ae  push    offset _wszSoTable; "MSysObjects"
0x100144b3  push    ebx; int
0x100144b4  call    _UtilSetErrorInfoReal@32; UtilSetErrorInfoReal(x,x,x,x,x,x,x,x)
0x100144b9  push    _critJet; lpCriticalSection
0x100144bf  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100144c5  mov     eax, 0FFFFF88Dh
0x100144ca  pop     edi
0x100144cb  pop     esi
0x100144cc  pop     ebx
0x100144cd  mov     ecx, [esp+0B4h+var_4]
0x100144d4  xor     ecx, esp; StackCookie
0x100144d6  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100144db  mov     esp, ebp
0x100144dd  pop     ebp
0x100144de  retn    10h
0x100144e1  push    5
0x100144e3  lea     eax, [esp+0C4h+var_2C]
0x100144ea  mov     [esp+0C4h+var_98], 28h ; '('
0x100144f2  mov     [esp+0C4h+var_8C], eax
0x100144f6  lea     eax, [esp+0C4h+var_98]
0x100144fa  push    eax
0x100144fb  push    edi
0x100144fc  push    esi
0x100144fd  push    0
0x100144ff  push    [esp+0D4h+var_B0]
0x10014503  push    ebx
0x10014504  call    _ErrDispGetObjectInfo@28; ErrDispGetObjectInfo(x,x,x,x,x,x,x)
0x10014509  mov     [esp+0C0h+var_AC], eax
0x1001450d  test    eax, eax
0x1001450f  jns     short loc_10014538
0x10014511  push    _critJet; lpCriticalSection
0x10014517  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001451d  mov     eax, [esp+0C0h+var_AC]
0x10014521  pop     edi
0x10014522  pop     esi
0x10014523  pop     ebx
0x10014524  mov     ecx, [esp+0B4h+var_4]
0x1001452b  xor     ecx, esp; StackCookie
0x1001452d  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10014532  mov     esp, ebp
0x10014534  pop     ebp
0x10014535  retn    10h
0x10014538  cmp     [esp+0C0h+var_28], 1
0x10014540  jnz     short loc_10014552
0x10014542  mov     edx, offset _wszMSysAccounts; "MSysAccounts"
0x10014547  mov     ecx, edi
0x10014549  call    _WCSICMP@8; WCSICMP(x,x)
0x1001454e  test    eax, eax
0x10014550  jz      short loc_10014562
0x10014552  mov     edx, offset _wszMSysGroups; "MSysGroups"
0x10014557  mov     ecx, edi
0x10014559  call    _WCSICMP@8; WCSICMP(x,x)
0x1001455e  test    eax, eax
0x10014560  jnz     short loc_1001458A
0x10014562  push    _critJet; lpCriticalSection
0x10014568  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001456e  mov     eax, 0FFFFFAE8h
0x10014573  pop     edi
0x10014574  pop     esi
0x10014575  pop     ebx
0x10014576  mov     ecx, [esp+0B4h+var_4]
0x1001457d  xor     ecx, esp; StackCookie
0x1001457f  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10014584  mov     esp, ebp
0x10014586  pop     ebp
0x10014587  retn    10h
0x1001458a  lea     eax, [esp+0C0h+var_9C]
0x1001458e  push    eax
0x1001458f  push    edi
0x10014590  push    esi
0x10014591  push    [esp+0CCh+var_B0]
0x10014595  push    ebx
0x10014596  call    _ErrDispGetObjidFromName@20; ErrDispGetObjidFromName(x,x,x,x,x)
0x1001459b  mov     [esp+0C0h+var_AC], eax
0x1001459f  test    eax, eax
0x100145a1  js      loc_10014511
0x100145a7  push    ebx
0x100145a8  call    _ErrIsamBeginTransaction@4; ErrIsamBeginTransaction(x)
0x100145ad  mov     [esp+0C0h+var_AC], eax
0x100145b1  test    eax, eax
0x100145b3  js      loc_10014511
0x100145b9  mov     eax, [esp+0C0h+var_B0]
0x100145bd  mov     ecx, _rgrepdbinfo[eax*4]
0x100145c4  mov     [esp+0C0h+var_A0], ecx
0x100145c8  mov     ecx, [ecx+0E4h]
0x100145ce  test    cl, 10h
0x100145d1  jnz     loc_100146F3
0x100145d7  test    cl, 1
0x100145da  jz      loc_100146F3
0x100145e0  lea     ecx, [esp+0C0h+var_AC]
0x100145e4  mov     edx, eax
0x100145e6  push    ecx; int
0x100145e7  lea     ecx, [esp+0C4h+var_A8]
0x100145eb  push    ecx; int
0x100145ec  push    edi; Src
0x100145ed  push    esi; int
0x100145ee  mov     ecx, ebx
0x100145f0  call    _ErrFObjectReplicable2@24; ErrFObjectReplicable2(x,x,x,x,x,x)
0x100145f5  mov     [esp+0C0h+var_AC], eax
0x100145f9  test    eax, eax
0x100145fb  jns     short loc_10014604
0x100145fd  mov     esi, eax
0x100145ff  jmp     loc_100146C2
0x10014604  cmp     [esp+0C0h+var_A8], 0
0x10014609  jz      loc_100146EF
0x1001460f  mov     eax, [esp+0C0h+var_A0]
0x10014613  mov     eax, [eax+0E4h]
0x10014619  test    al, 2
0x1001461b  jnz     short loc_10014627
0x1001461d  mov     esi, 0FFFFB1DDh
0x10014622  jmp     loc_100146C2
0x10014627  test    eax, 80000h
0x1001462c  jz      short loc_10014638
0x1001462e  mov     esi, 0FFFFB0ABh
0x10014633  jmp     loc_100146C2
0x10014638  push    40h ; '@'; Size
0x1001463a  lea     eax, [esp+0C4h+var_74]
0x1001463e  push    0; Val
0x10014640  push    eax; void *
0x10014641  call    _memset
0x10014646  add     esp, 0Ch
0x10014649  mov     [esp+0C0h+var_88], 0Fh
0x10014651  mov     [esp+0C0h+var_84], esi
0x10014655  test    esi, esi
0x10014657  jz      short loc_10014678
0x10014659  lea     ecx, [esi+2]
0x1001465c  nop     dword ptr [eax+00h]
0x10014660  mov     ax, [esi]
0x10014663  add     esi, 2
0x10014666  test    ax, ax
0x10014669  jnz     short loc_10014660
0x1001466b  sub     esi, ecx
0x1001466d  sar     esi, 1
0x1001466f  lea     eax, [esi+esi]
0x10014672  mov     [esp+0C0h+var_80], eax
0x10014676  jmp     short loc_10014680
0x10014678  mov     [esp+0C0h+var_80], 0
0x10014680  mov     [esp+0C0h+var_7C], edi
0x10014684  lea     ecx, [edi+2]
0x10014687  mov     ax, [edi]
0x1001468a  add     edi, 2
0x1001468d  test    ax, ax
0x10014690  jnz     short loc_10014687
0x10014692  sub     edi, ecx
0x10014694  sar     edi, 1
0x10014696  lea     eax, [edi+edi]
0x10014699  mov     [esp+0C0h+var_78], eax
0x1001469d  lea     eax, [esp+0C0h+var_88]
0x100146a1  push    eax
0x100146a2  push    [esp+0C4h+var_B0]
0x100146a6  push    ebx
0x100146a7  call    _ErrReplSchChangeInsert@12; ErrReplSchChangeInsert(x,x,x)
0x100146ac  mov     esi, eax
0x100146ae  test    esi, esi
0x100146b0  js      short loc_100146C2
0x100146b2  push    [esp+0C0h+var_B0]
0x100146b6  push    ebx
0x100146b7  call    _ErrRepSetLastSchema@8; ErrRepSetLastSchema(x,x)
0x100146bc  mov     esi, eax
0x100146be  test    esi, esi
0x100146c0  jns     short loc_100146EF
0x100146c2  push    0; char
0x100146c4  push    ebx; Session *
0x100146c5  call    _ErrIsamRollback@8; ErrIsamRollback(x,x)
0x100146ca  push    _critJet; lpCriticalSection
0x100146d0  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100146d6  mov     eax, esi
0x100146d8  pop     edi
0x100146d9  pop     esi
0x100146da  pop     ebx
0x100146db  mov     ecx, [esp+0B4h+var_4]
0x100146e2  xor     ecx, esp; StackCookie
0x100146e4  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100146e9  mov     esp, ebp
0x100146eb  pop     ebp
0x100146ec  retn    10h
0x100146ef  mov     eax, [esp+0C0h+var_B0]
  ... truncated ...
```
