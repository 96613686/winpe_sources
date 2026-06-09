# JetDupSession(x,x)

- ea: `0x10019770`
- end: `0x10019a49`
- name: `_JetDupSession@8`
- size: `729`
- prototype: `JET_ERR __stdcall(JET_SESID sesid, JET_SESID *psesid)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation`

## callees

- `0x10019770`
- `0x100290e0`
- `0x10029140`
- `0x10029190`
- `0x1002c5f0`
- `0x1003e370`
- `0x1003e420`
- `0x1003e530`
- `0x1003e6d0`
- `0x1003eef0`
- `0x100429d0`
- `0x10048dcc`
- `0x10048e6f`
- `0x10122f60`
- `0x10123ec8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1001995f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1001995f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100197c0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001985a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100199f9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10019a2e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100197c0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001985a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100199f9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10019a2e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10019790`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10019790`

## pseudocode

```c
JET_ERR __stdcall JetDupSession(JET_SESID sesid, JET_SESID *psesid)
{
  int v2; // esi
  int v4; // edi
  int IsibOfSesidIscb; // eax
  int v6; // edx
  unsigned __int16 *v7; // eax
  unsigned __int16 *v8; // ecx
  unsigned __int16 *v9; // eax
  int v10; // edi
  int v11; // ebx
  JET_ERR inited; // edi
  int v13; // eax
  void *v14; // ebx
  void *v15; // ecx
  int v16; // edx
  int v17; // eax
  void *v18; // ecx
  size_t *v19; // edi
  void *v20; // edx
  void *v21; // eax
  int v22; // edi
  int v23; // [esp-14h] [ebp-6Ch]
  int v24; // [esp-10h] [ebp-68h]
  int v25; // [esp+Ch] [ebp-4Ch]
  int v26; // [esp+10h] [ebp-48h]
  int v27; // [esp+14h] [ebp-44h]
  void *v28; // [esp+14h] [ebp-44h]
  int v29; // [esp+18h] [ebp-40h]
  void *Block; // [esp+1Ch] [ebp-3Ch] BYREF
  int ItibOfSesid; // [esp+20h] [ebp-38h]
  void *v32; // [esp+24h] [ebp-34h] BYREF
  unsigned __int16 v33[22]; // [esp+28h] [ebp-30h] BYREF

  EnterCriticalSection(critJet);
  v2 = isibHead;
  if ( isibHead == -1 )
  {
LABEL_4:
    LeaveCriticalSection(critJet);
    return -1104;
  }
  while ( rgsib[26 * v2] != sesid )
  {
    v2 = dword_1016EAE8[26 * v2];
    if ( v2 == -1 )
      goto LABEL_4;
  }
  ItibOfSesid = UtilGetItibOfSesid(sesid);
  v4 = 2147483646;
  IsibOfSesidIscb = UtilGetIsibOfSesidIscb((void *)sesid);
  v6 = 21;
  v7 = (unsigned __int16 *)dword_1016EAD4[26 * IsibOfSesidIscb];
  v8 = v33;
  do
  {
    if ( !v4 )
      break;
    if ( !*v7 )
      break;
    *v8++ = *v7++;
    --v4;
    --v6;
  }
  while ( v6 );
  v9 = v8 - 1;
  if ( v6 )
    v9 = v8;
  *v9 = 0;
  v10 = IsibAllocate(ItibOfSesid);
  v26 = v10;
  if ( v10 == -1 )
    goto LABEL_14;
  v11 = IiscbAllocate();
  v29 = v11;
  if ( v11 == -1 )
  {
    ReleaseIsib(v10);
LABEL_14:
    LeaveCriticalSection(critJet);
    return -1101;
  }
  Block = (void *)-1;
  v27 = 2316 * ItibOfSesid;
  inited = ErrIsamBeginSession3(*((struct Connection **)rgtib + 579 * ItibOfSesid + 570), v33, (int)&Block);
  if ( inited < 0 )
    goto LABEL_32;
  v13 = 5 * v11;
  v14 = Block;
  v25 = 4 * v13;
  *(&rgiscb + v13) = Block;
  Block = (void *)(104 * v2);
  inited = ErrInitSib(
             *(void **)((char *)dword_1016EAD4 + (_DWORD)Block),
             *(void **)((char *)&dword_1016EAD8 + (_DWORD)Block));
  if ( inited < 0 )
  {
    v11 = v29;
    goto LABEL_32;
  }
  v15 = Block;
  v16 = 26 * v26;
  v17 = *(int *)((char *)dword_1016EAD0 + (_DWORD)Block);
  ItibOfSesid = v16 * 4;
  dword_1016EAD0[v16] = v17;
  dword_1016EAF8[v16] = v29;
  v18 = *(&rgiscb + 5 * *(int *)((char *)dword_1016EAD0 + (_DWORD)v15) + 3);
  v32 = v18;
  if ( v18 != (void *)-1 )
  {
    inited = ErrTryOpenDatabase((int)v14, (wchar_t *)((char *)rgtib + v27), 0, (int)&v32, 0, 0);
    if ( inited < 0 )
    {
LABEL_26:
      ErrIsamEndSession(v14);
      v11 = v29;
LABEL_32:
      ReleaseIsib(v26);
      ReleaseIscb(v11, v11);
      LeaveCriticalSection(critJet);
      return inited;
    }
    v18 = v32;
  }
  v19 = (size_t *)*(&Src + 5 * *(int *)((char *)dword_1016EAD0 + (_DWORD)Block));
  if ( v19 )
  {
    v21 = _malloc(v19[1]);
    v28 = v21;
    if ( v21 )
    {
      memcpy(v21, v19, v19[1]);
      v18 = v32;
      v20 = v28;
      goto LABEL_28;
    }
    inited = -1011;
    if ( v32 != (void *)-1 && (int)ErrDispCloseDatabase(v14, v32, 0) < 0 )
      ErrDispCloseDatabase(v14, v32, 1);
    goto LABEL_26;
  }
  v20 = 0;
LABEL_28:
  v22 = ItibOfSesid;
  if ( v18 != (void *)-1 )
    *(int *)((char *)dword_1016EAD0 + ItibOfSesid) = mpdbidiiscb[(_DWORD)v18];
  *(void **)((char *)&rgiscb + v25 + 12) = v18;
  *(&rgiscb + 5 * *(int *)((char *)dword_1016EAD0 + v22) + 3) = v18;
  InitIscb(v23, v24, v18, v20);
  *psesid = (JET_SESID)v14;
  LeaveCriticalSection(critJet);
  return 0;
}

```

## disassembly

```asm
0x10019770  mov     edi, edi
0x10019772  push    ebp
0x10019773  mov     ebp, esp
0x10019775  sub     esp, 50h
0x10019778  mov     eax, ___security_cookie
0x1001977d  xor     eax, ebp
0x1001977f  mov     [ebp+var_4], eax
0x10019782  mov     eax, [ebp+psesid]
0x10019785  push    ebx
0x10019786  push    esi
0x10019787  push    _critJet; lpCriticalSection
0x1001978d  mov     [ebp+var_50], eax
0x10019790  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10019796  mov     esi, _isibHead
0x1001979c  cmp     esi, 0FFFFFFFFh
0x1001979f  jz      short loc_100197BA
0x100197a1  mov     ebx, [ebp+sesid]
0x100197a4  imul    eax, esi, 68h ; 'h'
0x100197a7  cmp     _rgsib[eax], ebx
0x100197ad  jz      short loc_100197DD
0x100197af  mov     esi, dword_1016EAE8[eax]
0x100197b5  cmp     esi, 0FFFFFFFFh
0x100197b8  jnz     short loc_100197A4
0x100197ba  push    _critJet; lpCriticalSection
0x100197c0  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100197c6  pop     esi
0x100197c7  mov     eax, 0FFFFFBB0h
0x100197cc  pop     ebx
0x100197cd  mov     ecx, [ebp+var_4]
0x100197d0  xor     ecx, ebp; StackCookie
0x100197d2  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100197d7  mov     esp, ebp
0x100197d9  pop     ebp
0x100197da  retn    8
0x100197dd  push    edi
0x100197de  push    ebx
0x100197df  call    _UtilGetItibOfSesid@4; UtilGetItibOfSesid(x)
0x100197e4  mov     ecx, ebx
0x100197e6  mov     [ebp+var_38], eax
0x100197e9  mov     edi, 7FFFFFFEh
0x100197ee  call    _UtilGetIsibOfSesidIscb@4; UtilGetIsibOfSesidIscb(x)
0x100197f3  imul    ecx, eax, 68h ; 'h'
0x100197f6  mov     edx, 15h
0x100197fb  mov     eax, dword_1016EAD4[ecx]
0x10019801  lea     ecx, [ebp+var_30]
0x10019804  test    edi, edi
0x10019806  jz      short loc_1001981F
0x10019808  movzx   ebx, word ptr [eax]
0x1001980b  test    bx, bx
0x1001980e  jz      short loc_1001981F
0x10019810  mov     [ecx], bx
0x10019813  add     eax, 2
0x10019816  add     ecx, 2
0x10019819  dec     edi
0x1001981a  sub     edx, 1
0x1001981d  jnz     short loc_10019804
0x1001981f  lea     eax, [ecx-2]
0x10019822  test    edx, edx
0x10019824  cmovnz  eax, ecx
0x10019827  xor     ecx, ecx
0x10019829  mov     [eax], cx
0x1001982c  mov     ecx, [ebp+var_38]
0x1001982f  call    _IsibAllocate@4; IsibAllocate(x)
0x10019834  mov     edi, eax
0x10019836  mov     [ebp+var_48], edi
0x10019839  cmp     edi, 0FFFFFFFFh
0x1001983c  jz      short loc_10019854
0x1001983e  call    _IiscbAllocate@0; IiscbAllocate()
0x10019843  mov     ebx, eax
0x10019845  mov     [ebp+var_40], ebx
0x10019848  cmp     ebx, 0FFFFFFFFh
0x1001984b  jnz     short loc_10019878
0x1001984d  mov     ecx, edi
0x1001984f  call    _ReleaseIsib@4; ReleaseIsib(x)
0x10019854  push    _critJet; lpCriticalSection
0x1001985a  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10019860  pop     edi
0x10019861  pop     esi
0x10019862  mov     eax, 0FFFFFBB3h
0x10019867  pop     ebx
0x10019868  mov     ecx, [ebp+var_4]
0x1001986b  xor     ecx, ebp; StackCookie
0x1001986d  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10019872  mov     esp, ebp
0x10019874  pop     ebp
0x10019875  retn    8
0x10019878  imul    eax, [ebp+var_38], 90Ch
0x1001987f  lea     ecx, [ebp+Block]
0x10019882  push    ecx; int
0x10019883  mov     ecx, _rgtib
0x10019889  lea     edx, [ebp+var_30]; unsigned __int16 *
0x1001988c  mov     [ebp+Block], 0FFFFFFFFh
0x10019893  mov     [ebp+var_44], eax
0x10019896  mov     ecx, [eax+ecx+8E8h]; struct Connection *
0x1001989d  call    _ErrIsamBeginSession3@12; ErrIsamBeginSession3(x,x,x)
0x100198a2  mov     edi, eax
0x100198a4  test    edi, edi
0x100198a6  js      loc_10019A17
0x100198ac  lea     eax, [ebx+ebx*4]
0x100198af  mov     ebx, [ebp+Block]
0x100198b2  shl     eax, 2
0x100198b5  mov     ecx, ebx
0x100198b7  mov     [ebp+var_4C], eax
0x100198ba  mov     dword ptr _rgiscb[eax], ebx
0x100198c0  imul    eax, esi, 68h ; 'h'
0x100198c3  mov     esi, [ebp+var_48]
0x100198c6  mov     edx, esi
0x100198c8  mov     [ebp+Block], eax
0x100198cb  push    dword_1016EAD8[eax]; void *
0x100198d1  push    dword_1016EAD4[eax]; Src
0x100198d7  call    _ErrInitSib@16; ErrInitSib(x,x,x,x)
0x100198dc  mov     edi, eax
0x100198de  test    edi, edi
0x100198e0  js      loc_10019A14
0x100198e6  mov     ecx, [ebp+Block]
0x100198e9  imul    edx, esi, 68h ; 'h'
0x100198ec  mov     esi, [ebp+var_40]
0x100198ef  mov     eax, dword_1016EAD0[ecx]
0x100198f5  mov     [ebp+var_38], edx
0x100198f8  mov     dword_1016EAD0[edx], eax
0x100198fe  mov     dword_1016EAF8[edx], esi
0x10019904  mov     eax, dword_1016EAD0[ecx]
0x1001990a  lea     eax, [eax+eax*4]
0x1001990d  mov     ecx, dword ptr (_rgiscb+0Ch)[eax*4]
0x10019914  mov     [ebp+var_34], ecx
0x10019917  cmp     ecx, 0FFFFFFFFh
0x1001991a  jz      short loc_10019941
0x1001991c  mov     edx, [ebp+var_44]
0x1001991f  lea     eax, [ebp+var_34]
0x10019922  push    0
0x10019924  push    0
0x10019926  push    eax
0x10019927  mov     eax, _rgtib
0x1001992c  mov     ecx, ebx
0x1001992e  push    0
0x10019930  lea     edx, [edx+eax]
0x10019933  call    _ErrTryOpenDatabase@24; ErrTryOpenDatabase(x,x,x,x,x,x)
0x10019938  mov     edi, eax
0x1001993a  test    edi, edi
0x1001993c  js      short loc_10019994
0x1001993e  mov     ecx, [ebp+var_34]
0x10019941  mov     eax, [ebp+Block]
0x10019944  mov     eax, dword_1016EAD0[eax]
0x1001994a  lea     eax, [eax+eax*4]
0x1001994d  mov     edi, Src[eax*4]
0x10019954  test    edi, edi
0x10019956  jnz     short loc_1001995C
0x10019958  xor     edx, edx
0x1001995a  jmp     short loc_100199B2
0x1001995c  push    dword ptr [edi+4]; Size
0x1001995f  call    ds:__imp__malloc
0x10019965  add     esp, 4
0x10019968  mov     [ebp+var_44], eax
0x1001996b  test    eax, eax
0x1001996d  jnz     short loc_1001999F
0x1001996f  mov     eax, [ebp+var_34]
0x10019972  mov     edi, 0FFFFFC0Dh
0x10019977  cmp     eax, 0FFFFFFFFh
0x1001997a  jz      short loc_10019994
0x1001997c  push    0
0x1001997e  push    eax
0x1001997f  push    ebx
0x10019980  call    _ErrDispCloseDatabase@12; ErrDispCloseDatabase(x,x,x)
0x10019985  test    eax, eax
0x10019987  jns     short loc_10019994
0x10019989  push    1
0x1001998b  push    [ebp+var_34]
0x1001998e  push    ebx
0x1001998f  call    _ErrDispCloseDatabase@12; ErrDispCloseDatabase(x,x,x)
0x10019994  mov     ecx, ebx; Block
0x10019996  call    _ErrIsamEndSession@8; ErrIsamEndSession(x,x)
0x1001999b  mov     ebx, esi
0x1001999d  jmp     short loc_10019A17
0x1001999f  push    dword ptr [edi+4]; Size
0x100199a2  push    edi; Src
0x100199a3  push    eax; void *
0x100199a4  call    _memcpy
0x100199a9  mov     ecx, [ebp+var_34]
0x100199ac  add     esp, 0Ch
0x100199af  mov     edx, [ebp+var_44]
0x100199b2  mov     edi, [ebp+var_38]
0x100199b5  cmp     ecx, 0FFFFFFFFh
0x100199b8  jz      short loc_100199C7
0x100199ba  mov     eax, _mpdbidiiscb[ecx*4]
0x100199c1  mov     dword_1016EAD0[edi], eax
0x100199c7  mov     eax, [ebp+var_4C]
0x100199ca  push    edx
0x100199cb  push    ecx
0x100199cc  sub     esp, 8
0x100199cf  mov     edx, ebx
0x100199d1  mov     dword ptr (_rgiscb+0Ch)[eax], ecx
0x100199d7  mov     eax, dword_1016EAD0[edi]
0x100199dd  lea     eax, [eax+eax*4]
0x100199e0  mov     dword ptr (_rgiscb+0Ch)[eax*4], ecx
0x100199e7  mov     ecx, esi
0x100199e9  call    _InitIscb@24; InitIscb(x,x,x,x,x,x)
0x100199ee  mov     eax, [ebp+var_50]
0x100199f1  mov     [eax], ebx
0x100199f3  push    _critJet; lpCriticalSection
0x100199f9  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100199ff  pop     edi
0x10019a00  pop     esi
0x10019a01  xor     eax, eax
0x10019a03  pop     ebx
0x10019a04  mov     ecx, [ebp+var_4]
0x10019a07  xor     ecx, ebp; StackCookie
0x10019a09  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10019a0e  mov     esp, ebp
0x10019a10  pop     ebp
0x10019a11  retn    8
0x10019a14  mov     ebx, [ebp+var_40]
0x10019a17  mov     ecx, [ebp+var_48]
0x10019a1a  call    _ReleaseIsib@4; ReleaseIsib(x)
0x10019a1f  mov     edx, ebx
0x10019a21  mov     ecx, ebx
0x10019a23  call    _ReleaseIscb@8; ReleaseIscb(x,x)
0x10019a28  push    _critJet; lpCriticalSection
0x10019a2e  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10019a34  mov     ecx, [ebp+var_4]
0x10019a37  mov     eax, edi
0x10019a39  pop     edi
0x10019a3a  pop     esi
0x10019a3b  xor     ecx, ebp; StackCookie
0x10019a3d  pop     ebx
0x10019a3e  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10019a43  mov     esp, ebp
0x10019a45  pop     ebp
0x10019a46  retn    8
```
