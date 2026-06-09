# JetEndSession(x,x)

- ea: `0x10019b90`
- end: `0x1001a2a7`
- name: `_JetEndSession@8`
- size: `1815`
- prototype: `JET_ERR __stdcall(JET_SESID sesid, JET_GRBIT grbit)`
- caller_count: `0`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x10019b90`
- `0x10029360`
- `0x1002a600`
- `0x1003e6c0`
- `0x1003e9b0`
- `0x10042b60`
- `0x10045570`
- `0x1004da20`
- `0x1004f89d`
- `0x10050190`
- `0x1005814f`
- `0x1005e748`
- `0x100964cf`
- `0x100a44bf`
- `0x10123110`
- `0x10123c92`
- `0x10123ca8`
- `0x10124048`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1001a0b1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1001a0b1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10019c04`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10019ddc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001a28b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10019c04`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10019ddc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001a28b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10019bc0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10019bc0`

## pseudocode

```c
JET_ERR __stdcall JetEndSession(JET_SESID sesid, JET_GRBIT grbit)
{
  int v2; // esi
  JET_SESID v3; // ebx
  int v5; // edi
  int v6; // esi
  int v7; // eax
  int v8; // edi
  unsigned int v9; // esi
  _DWORD *v10; // eax
  unsigned int v11; // ebx
  bool v12; // cf
  int v13; // edx
  char v14; // al
  int v15; // esi
  _DWORD *i; // edx
  _DWORD *v17; // eax
  unsigned int v18; // ecx
  bool v19; // cf
  _DWORD *v20; // ecx
  int v21; // esi
  int v22; // eax
  int j; // ecx
  int v24; // edx
  int v25; // ecx
  unsigned int v26; // edx
  unsigned int v27; // eax
  _DWORD *v28; // edi
  int v29; // esi
  int v30; // ecx
  int v31; // eax
  int v32; // ecx
  struct Instance *v33; // edi
  _DWORD *v34; // ecx
  Table *v35; // ecx
  Table *v36; // ecx
  void (__thiscall ***v37)(int, int); // eax
  unsigned int v38; // esi
  _DWORD *v39; // esi
  int v40; // ecx
  unsigned int v41; // ecx
  struct Instance **v42; // edx
  unsigned int v43; // eax
  unsigned int v44; // eax
  IAccMeth *v45; // ecx
  void **v46; // edi
  int v47; // eax
  int v48; // edx
  int v49; // eax
  unsigned int v50; // ecx
  unsigned int v51; // ecx
  _DWORD *v52; // esi
  unsigned int v53; // eax
  unsigned int v54; // eax
  int v55; // ecx
  unsigned int v56; // ecx
  _DWORD *v57; // esi
  unsigned int v58; // eax
  unsigned int v59; // eax
  _DWORD *v60; // esi
  int v61; // ecx
  unsigned int v62; // ecx
  _DWORD *v63; // edx
  unsigned int v64; // eax
  unsigned int v65; // eax
  int v66[3]; // [esp+10h] [ebp-38h] BYREF
  void *Block; // [esp+1Ch] [ebp-2Ch]
  void *v68; // [esp+20h] [ebp-28h]
  int v69; // [esp+24h] [ebp-24h]
  int k; // [esp+28h] [ebp-20h]
  int v71; // [esp+2Ch] [ebp-1Ch]
  JET_ERR v72; // [esp+30h] [ebp-18h]
  int v73; // [esp+34h] [ebp-14h]
  int v74; // [esp+38h] [ebp-10h]
  int v75; // [esp+44h] [ebp-4h]

  EnterCriticalSection(critJet);
  v2 = isibHead;
  v3 = sesid;
  k = isibHead;
  if ( isibHead == -1 )
    goto LABEL_5;
  do
  {
    if ( rgsib[26 * v2] == sesid )
      break;
    v2 = dword_1016EB88[26 * v2];
  }
  while ( v2 != -1 );
  k = v2;
  if ( v2 == -1 )
  {
LABEL_5:
    LeaveCriticalSection(critJet);
    return -1104;
  }
  NotifyRollbackTransaction(sesid, 1);
  v5 = 104 * v2;
  v72 = ErrIsamRollback((Session *)sesid, 1);
  v73 = 104 * v2;
  if ( v72 < 0 )
  {
    v73 = 104 * v2;
  }
  else
  {
    dword_1016EB8C[26 * v2] = 0;
    RollbackIsamTransactions(sesid, 1);
    v6 = dword_1016EB90[26 * v2];
    v71 = v6;
    if ( v6 > 0 )
    {
      *(int *)((char *)dword_1016EB90 + v5) = 0;
      v73 = v5;
      do
      {
        if ( dword_1013112C )
        {
          v7 = HenvOfSesid(v3);
          v74 = v7;
          v8 = *((_DWORD *)dword_1013112C + 7);
          if ( v8 )
          {
            do
            {
              if ( *(_DWORD *)(v8 + 24) && *(_DWORD *)(v8 + 28) == v7 )
              {
                v9 = v8 + 32;
                v10 = (_DWORD *)(v8 + 32);
                v11 = v8 + 192;
                v12 = v8 + 32 < (unsigned int)(v8 + 192);
                if ( v8 + 32 < (unsigned int)(v8 + 192) )
                {
                  do
                  {
                    if ( *v10 == sesid )
                      break;
                    v10 += 2;
                  }
                  while ( (unsigned int)v10 < v11 );
                  v12 = (unsigned int)v10 < v11;
                }
                v13 = v12 ? (unsigned int)v10 : 0;
                if ( v13 && (*(_BYTE *)(v8 + 4) & 4) == 0 )
                {
                  v14 = *(v12 ? (_BYTE *)(v10 + 1) : (_BYTE *)4);
                  if ( v14 > 0 )
                  {
                    *(_BYTE *)(v13 + 4) = v14 - 1;
                    --*(_WORD *)(v8 + 192);
                  }
                  if ( !*(_WORD *)(v8 + 192) )
                  {
                    ErrRmtSimComRbk(1);
                    if ( !*(_WORD *)v8 )
                    {
                      for ( ; v9 < v11; v9 += 8 )
                      {
                        *(_DWORD *)v9 = -1;
                        *(_BYTE *)(v9 + 4) = 0;
                      }
                    }
                  }
                }
                v7 = v74;
              }
              v8 = *(_DWORD *)(v8 + 212);
            }
            while ( v8 );
            v3 = sesid;
            v6 = v71;
          }
        }
        v71 = --v6;
      }
      while ( v6 );
      v5 = v73;
    }
  }
  if ( dword_1013112C )
  {
    v15 = HenvOfSesid(v3);
    for ( i = (_DWORD *)*((_DWORD *)dword_1013112C + 7); i; i = (_DWORD *)i[53] )
    {
      if ( i[7] == v15 )
      {
        v17 = i + 8;
        v18 = (unsigned int)(i + 48);
        v19 = i + 8 < i + 48;
        if ( i + 8 < i + 48 )
        {
          do
          {
            if ( *v17 == v3 )
              break;
            v17 += 2;
          }
          while ( (unsigned int)v17 < v18 );
          v19 = (unsigned int)v17 < v18;
        }
        v20 = v19 ? v17 : 0;
        if ( v20 )
          *v20 = -1;
      }
    }
  }
  ClearErrorInfo(v3);
  v21 = (int)*(&rgiscb + 5 * *(int *)((char *)dword_1016EB70 + v5) + 3);
  if ( v21 != -1 )
  {
    v72 = ErrDispCloseDatabase(v3, v21, 0);
    if ( v72 < 0 )
    {
      if ( (grbit & 1) == 0 )
      {
LABEL_44:
        LeaveCriticalSection(critJet);
        return v72;
      }
      ErrDispCloseDatabase(v3, v21, 1);
    }
  }
  v22 = isibHead;
  for ( j = isibHead; j != -1; j = dword_1016EB88[26 * j] )
  {
    if ( rgsib[26 * j] == v3 )
      break;
  }
  v69 = 104 * j;
  v24 = dword_1016EB94[26 * j];
  v71 = v24;
  if ( v24 != -1 )
  {
    while ( 1 )
    {
      v25 = 20 * v24;
      v74 = 20 * v24;
      v26 = (unsigned int)*(&rgiscb + 5 * v24 + 1);
      if ( v22 != -1 )
      {
        do
        {
          if ( rgsib[26 * v22] == v3 )
            break;
          v22 = dword_1016EB88[26 * v22];
        }
        while ( v22 != -1 );
        v25 = v74;
      }
      if ( v22 >= 0 )
      {
        _mm_lfence();
        v27 = dword_1016EB44[26 * v22];
      }
      else
      {
        v27 = -1;
      }
      if ( rgtib && v26 <= 0x27 && v27 <= 0x3F )
      {
        _mm_lfence();
        v28 = (_DWORD *)*((_DWORD *)rgtib + 579 * v27 + v26 + 264);
      }
      else
      {
        v28 = 0;
      }
      v29 = *(int *)((char *)&rgiscb + v25 + 12);
      if ( v29 != -1 && *(&rgiscb + 5 * mpdbidiiscb[v29]) == *(void **)((char *)&rgiscb + v25) )
      {
        if ( (int)ErrDispCloseDatabase(v3, v29, 0) < 0 )
          ErrDispCloseDatabase(v3, v29, 1);
        v25 = v74;
      }
      (*(void (__thiscall **)(_DWORD, _DWORD, _DWORD))(*v28 + 32))(
        *(_DWORD *)(*v28 + 32),
        *(void **)((char *)&rgiscb + v25),
        0);
      v30 = v74;
      --v28[3];
      v31 = v71;
      v24 = *(int *)((char *)&rgiscb + v30 + 8);
      v71 = v24;
      if ( v24 == -1 )
        break;
      v22 = isibHead;
    }
    v5 = v73;
    if ( v31 != -1 )
    {
      *(void **)((char *)&rgiscb + v30 + 8) = (void *)dword_10130574;
      dword_10130574 = *(int *)((char *)dword_1016EB94 + v69);
      *(int *)((char *)dword_1016EB94 + v69) = -1;
    }
  }
  if ( !rgtib )
    goto LABEL_44;
  ReleaseIscb(*(int *)((char *)dword_1016EB98 + v5), *(int *)((char *)dword_1016EB98 + v5));
  ReleaseIsib(k);
  if ( dword_10130568 && v3 )
  {
    v75 = 0;
    while ( *(int *)(v3 + 8) > 0 )
    {
      v66[0] = 1;
      Session::AbortTransaction((Session *)v3, (struct Err *)v66);
      if ( (v66[0] & 0xFFFFFFFE) != 0 )
      {
        if ( Block )
          operator delete[](Block);
        if ( v68 )
          operator delete[](v68);
      }
    }
    v32 = *(_DWORD *)(v3 + 164) - 1;
    for ( k = v32; k >= 0; --k )
    {
      v33 = *(struct Instance **)(*(_DWORD *)(v3 + 156) + 4 * v32);
      v34 = (_DWORD *)*((_DWORD *)v33 + 16);
      *((_DWORD *)v33 + 16) = (char *)v34 - 1;
      if ( v34 == (_DWORD *)1 )
      {
        LOBYTE(v75) = 1;
        *((_DWORD *)v33 + 16) = 1;
        v35 = (Table *)*((_DWORD *)v33 + 17);
        if ( v35 )
        {
          Table::Release(v35, v33);
          *((_DWORD *)v33 + 17) = 0;
        }
        v36 = (Table *)*((_DWORD *)v33 + 18);
        if ( v36 )
        {
          Table::Release(v36, v33);
          *((_DWORD *)v33 + 18) = 0;
        }
        while ( *((_DWORD *)v33 + 2) )
        {
          v37 = **(void (__thiscall *****)(int, int))v33;
          v69 = (int)v37;
          if ( v37 )
            (**v37)(v69, 1);
        }
        v38 = 256;
        if ( dbidInit != 256 )
        {
          while ( 1 )
          {
            --v38;
            if ( (struct Instance *)*(&mpdbiddbid + v38) == v33 && (int *)mpdbidpvdbfndef[v38] == vdbfndefIsam )
              break;
            if ( v38 == dbidInit )
              goto LABEL_102;
          }
          if ( v38 != -1 )
          {
            *(&mpdbiddbid + v38) = dbidFree;
            mpdbidpvdbfndef[v38] = (int)vdbfndefInvalidDbid;
            if ( v38 < 0x100 )
            {
              if ( *(&rgrepdbinfo + v38) )
                _free(*(&rgrepdbinfo + v38));
              *(&rgrepdbinfo + v38) = 0;
            }
            dbidFree = v38;
          }
        }
LABEL_102:
        v39 = (_DWORD *)*((_DWORD *)v33 + 3);
        v40 = v39[41];
        if ( v40 )
        {
          *(_DWORD *)(v39[39] + 4 * v40) = v33;
          v41 = 0;
          v42 = (struct Instance **)v39[39];
          if ( *v42 != v33 )
          {
            do
              ++v41;
            while ( v42[v41] != v33 );
          }
          v43 = v39[41];
          if ( v41 < v43 )
          {
            v44 = v43 - 1;
            v39[41] = v44;
            v42[v41] = v42[v44];
          }
        }
        v45 = (IAccMeth *)*((_DWORD *)v33 + 15);
        if ( v45 )
          IAccMeth::Release(v45);
        if ( *(_DWORD *)v33 )
          operator delete[](*(void **)v33);
        operator delete(v33, 0x4Cu);
      }
      v32 = k - 1;
    }
    v46 = (void **)(v3 + 192);
    v47 = *(_DWORD *)(v3 + 200) - 1;
    if ( v47 >= 0 )
    {
      while ( 1 )
      {
        v69 = v47 - 1;
        v48 = *((_DWORD *)*v46 + v47);
        v49 = 0;
        v50 = *(_DWORD *)(v48 + 120);
        if ( v50 )
          break;
LABEL_117:
        if ( v49 != v50 )
        {
          if ( v50 )
            goto LABEL_119;
          goto LABEL_123;
        }
LABEL_128:
        v47 = v69;
        if ( v69 < 0 )
          goto LABEL_129;
      }
      while ( *(_DWORD *)(*(_DWORD *)(v48 + 112) + 4 * v49) != v3 )
      {
        if ( ++v49 >= v50 )
          goto LABEL_117;
      }
LABEL_119:
      *(_DWORD *)(*(_DWORD *)(v48 + 112) + 4 * v50) = v3;
      v51 = 0;
      v52 = *(_DWORD **)(v48 + 112);
      if ( *v52 != v3 )
      {
        do
          ++v51;
        while ( v52[v51] != v3 );
      }
      v53 = *(_DWORD *)(v48 + 120);
      if ( v51 < v53 )
      {
        v54 = v53 - 1;
        *(_DWORD *)(v48 + 120) = v54;
        v52[v51] = v52[v54];
      }
LABEL_123:
      v55 = *(_DWORD *)(v3 + 200);
      if ( v55 )
      {
        *((_DWORD *)*v46 + v55) = v48;
        v56 = 0;
        v57 = *v46;
        if ( *(_DWORD *)*v46 != v48 )
        {
          do
            ++v56;
          while ( v57[v56] != v48 );
        }
        v58 = *(_DWORD *)(v3 + 200);
        if ( v56 < v58 )
        {
          v59 = v58 - 1;
          *(_DWORD *)(v3 + 200) = v59;
          v57[v56] = v57[v59];
        }
      }
      goto LABEL_128;
    }
LABEL_129:
    v60 = *(_DWORD **)v3;
    v61 = *(_DWORD *)(*(_DWORD *)v3 + 8);
    if ( v61 )
    {
      *(_DWORD *)(*v60 + 4 * v61) = v3;
      v62 = 0;
      v63 = (_DWORD *)*v60;
      if ( *(_DWORD *)*v60 != v3 )
      {
        do
          ++v62;
        while ( v63[v62] != v3 );
        v46 = (void **)(v3 + 192);
      }
      v64 = v60[2];
      if ( v62 < v64 )
      {
        v65 = v64 - 1;
        v60[2] = v65;
        v63[v62] = v63[v65];
      }
    }
    if ( *(_DWORD *)(v3 + 204) )
      operator delete[](*(void **)(v3 + 204));
    if ( *v46 )
      operator delete[](*v46);
    if ( *(_DWORD *)(v3 + 180) )
      operator delete[](*(void **)(v3 + 180));
    if ( *(_DWORD *)(v3 + 168) )
      operator delete[](*(void **)(v3 + 168));
    if ( *(_DWORD *)(v3 + 156) )
      operator delete[](*(void **)(v3 + 156));
    v75 = -1;
    operator delete((void *)v3, 0xDCu);
  }
  LeaveCriticalSection(critJet);
  return 0;
}

```

## disassembly

```asm
0x10019b90  mov     edi, edi
0x10019b92  push    ebp
0x10019b93  mov     ebp, esp
0x10019b95  push    0FFFFFFFFh
0x10019b97  push    offset _JetEndSession@8_SEH
0x10019b9c  mov     eax, large fs:0
0x10019ba2  push    eax
0x10019ba3  sub     esp, 2Ch
0x10019ba6  push    ebx
0x10019ba7  push    esi
0x10019ba8  push    edi
0x10019ba9  mov     eax, ___security_cookie
0x10019bae  xor     eax, ebp
0x10019bb0  push    eax; unsigned int
0x10019bb1  lea     eax, [ebp+var_C]
0x10019bb4  mov     large fs:0, eax
0x10019bba  push    _critJet; lpCriticalSection
0x10019bc0  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10019bc6  mov     esi, _isibHead
0x10019bcc  mov     ebx, [ebp+sesid]
0x10019bcf  mov     [ebp+var_20], esi
0x10019bd2  cmp     esi, 0FFFFFFFFh
0x10019bd5  jz      short loc_10019BFE
0x10019bd7  nop     word ptr [eax+eax+00000000h]
0x10019be0  imul    eax, esi, 68h ; 'h'
0x10019be3  cmp     _rgsib[eax], ebx
0x10019be9  jz      short loc_10019BF6
0x10019beb  mov     esi, dword_1016EB88[eax]
0x10019bf1  cmp     esi, 0FFFFFFFFh
0x10019bf4  jnz     short loc_10019BE0
0x10019bf6  mov     [ebp+var_20], esi
0x10019bf9  cmp     esi, 0FFFFFFFFh
0x10019bfc  jnz     short loc_10019C23
0x10019bfe  push    _critJet; lpCriticalSection
0x10019c04  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10019c0a  mov     eax, 0FFFFFBB0h
0x10019c0f  mov     ecx, [ebp+var_C]
0x10019c12  mov     large fs:0, ecx
0x10019c19  pop     ecx
0x10019c1a  pop     edi
0x10019c1b  pop     esi
0x10019c1c  pop     ebx
0x10019c1d  mov     esp, ebp
0x10019c1f  pop     ebp
0x10019c20  retn    8
0x10019c23  mov     edx, 1
0x10019c28  mov     ecx, ebx
0x10019c2a  call    _NotifyRollbackTransaction@8; NotifyRollbackTransaction(x,x)
0x10019c2f  push    1; char
0x10019c31  push    ebx; Session *
0x10019c32  call    _ErrIsamRollback@8; ErrIsamRollback(x,x)
0x10019c37  imul    edi, esi, 68h ; 'h'
0x10019c3a  mov     [ebp+var_18], eax
0x10019c3d  mov     [ebp+var_14], edi
0x10019c40  test    eax, eax
0x10019c42  js      loc_10019D4C
0x10019c48  mov     edx, 1
0x10019c4d  mov     dword_1016EB8C[edi], 0
0x10019c57  mov     ecx, ebx
0x10019c59  call    _RollbackIsamTransactions@8; RollbackIsamTransactions(x,x)
0x10019c5e  mov     esi, dword_1016EB90[edi]
0x10019c64  mov     [ebp+var_1C], esi
0x10019c67  test    esi, esi
0x10019c69  jle     loc_10019D4F
0x10019c6f  mov     dword_1016EB90[edi], 0
0x10019c79  mov     [ebp+var_14], edi
0x10019c7c  nop     dword ptr [eax+00h]
0x10019c80  cmp     dword_1013112C, 0
0x10019c87  jz      loc_10019D3B
0x10019c8d  mov     ecx, ebx
0x10019c8f  call    _HenvOfSesid@4; HenvOfSesid(x)
0x10019c94  mov     ecx, dword_1013112C
0x10019c9a  mov     [ebp+var_10], eax
0x10019c9d  mov     edi, [ecx+1Ch]
0x10019ca0  test    edi, edi
0x10019ca2  jz      loc_10019D3B
0x10019ca8  cmp     dword ptr [edi+18h], 0
0x10019cac  jz      short loc_10019D27
0x10019cae  cmp     [edi+1Ch], eax
0x10019cb1  jnz     short loc_10019D27
0x10019cb3  mov     ecx, [ebp+sesid]
0x10019cb6  lea     esi, [edi+20h]
0x10019cb9  mov     eax, esi
0x10019cbb  lea     ebx, [eax+0A0h]
0x10019cc1  cmp     eax, ebx
0x10019cc3  jnb     short loc_10019CD2
0x10019cc5  cmp     [eax], ecx
0x10019cc7  jz      short loc_10019CD0
0x10019cc9  add     eax, 8
0x10019ccc  cmp     eax, ebx
0x10019cce  jb      short loc_10019CC5
0x10019cd0  cmp     eax, ebx
0x10019cd2  sbb     edx, edx
0x10019cd4  and     edx, eax
0x10019cd6  jz      short loc_10019D24
0x10019cd8  test    byte ptr [edi+4], 4
0x10019cdc  jnz     short loc_10019D24
0x10019cde  mov     al, [edx+4]
0x10019ce1  test    al, al
0x10019ce3  jle     short loc_10019CF6
0x10019ce5  dec     al
0x10019ce7  mov     [edx+4], al
0x10019cea  mov     eax, 0FFFFh
0x10019cef  add     [edi+0C0h], ax
0x10019cf6  cmp     word ptr [edi+0C0h], 0
0x10019cfe  jnz     short loc_10019D24
0x10019d00  push    1
0x10019d02  mov     edx, edi
0x10019d04  call    ErrRmtSimComRbk
0x10019d09  cmp     word ptr [edi], 0
0x10019d0d  jnz     short loc_10019D24
0x10019d0f  cmp     esi, ebx
0x10019d11  jnb     short loc_10019D24
0x10019d13  mov     dword ptr [esi], 0FFFFFFFFh
0x10019d19  mov     byte ptr [esi+4], 0
0x10019d1d  add     esi, 8
0x10019d20  cmp     esi, ebx
0x10019d22  jb      short loc_10019D13
0x10019d24  mov     eax, [ebp+var_10]
0x10019d27  mov     edi, [edi+0D4h]
0x10019d2d  test    edi, edi
0x10019d2f  jnz     loc_10019CA8
0x10019d35  mov     ebx, [ebp+sesid]
0x10019d38  mov     esi, [ebp+var_1C]
0x10019d3b  sub     esi, 1
0x10019d3e  mov     [ebp+var_1C], esi
0x10019d41  jnz     loc_10019C80
0x10019d47  mov     edi, [ebp+var_14]
0x10019d4a  jmp     short loc_10019D4F
0x10019d4c  mov     [ebp+var_14], edi
0x10019d4f  cmp     dword_1013112C, 0
0x10019d56  jz      short loc_10019DA5
0x10019d58  mov     ecx, ebx
0x10019d5a  call    _HenvOfSesid@4; HenvOfSesid(x)
0x10019d5f  mov     ecx, dword_1013112C
0x10019d65  mov     esi, eax
0x10019d67  mov     edx, [ecx+1Ch]
0x10019d6a  test    edx, edx
0x10019d6c  jz      short loc_10019DA5
0x10019d6e  mov     edi, edi
0x10019d70  cmp     [edx+1Ch], esi
0x10019d73  jnz     short loc_10019D9B
0x10019d75  lea     eax, [edx+20h]
0x10019d78  lea     ecx, [eax+0A0h]
0x10019d7e  cmp     eax, ecx
0x10019d80  jnb     short loc_10019D8F
0x10019d82  cmp     [eax], ebx
0x10019d84  jz      short loc_10019D8D
0x10019d86  add     eax, 8
0x10019d89  cmp     eax, ecx
0x10019d8b  jb      short loc_10019D82
0x10019d8d  cmp     eax, ecx
0x10019d8f  sbb     ecx, ecx
0x10019d91  and     ecx, eax
0x10019d93  jz      short loc_10019D9B
0x10019d95  mov     dword ptr [ecx], 0FFFFFFFFh
0x10019d9b  mov     edx, [edx+0D4h]
0x10019da1  test    edx, edx
0x10019da3  jnz     short loc_10019D70
0x10019da5  push    ebx
0x10019da6  call    _ClearErrorInfo@4; ClearErrorInfo(x)
0x10019dab  mov     eax, dword_1016EB70[edi]
0x10019db1  lea     eax, [eax+eax*4]
0x10019db4  mov     esi, dword ptr (_rgiscb+0Ch)[eax*4]
0x10019dbb  cmp     esi, 0FFFFFFFFh
0x10019dbe  jz      short loc_10019E02
0x10019dc0  push    0
0x10019dc2  push    esi
0x10019dc3  push    ebx
0x10019dc4  call    _ErrDispCloseDatabase@12; ErrDispCloseDatabase(x,x,x)
0x10019dc9  mov     [ebp+var_18], eax
0x10019dcc  test    eax, eax
0x10019dce  jns     short loc_10019E02
0x10019dd0  test    byte ptr [ebp+grbit], 1
0x10019dd4  jnz     short loc_10019DF9
0x10019dd6  push    _critJet; lpCriticalSection
0x10019ddc  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10019de2  mov     eax, [ebp+var_18]
0x10019de5  mov     ecx, [ebp+var_C]
0x10019de8  mov     large fs:0, ecx
0x10019def  pop     ecx
0x10019df0  pop     edi
0x10019df1  pop     esi
0x10019df2  pop     ebx
0x10019df3  mov     esp, ebp
0x10019df5  pop     ebp
0x10019df6  retn    8
0x10019df9  push    1
0x10019dfb  push    esi
0x10019dfc  push    ebx
0x10019dfd  call    _ErrDispCloseDatabase@12; ErrDispCloseDatabase(x,x,x)
0x10019e02  mov     eax, _isibHead
0x10019e07  mov     ecx, eax
0x10019e09  cmp     ecx, 0FFFFFFFFh
0x10019e0c  jz      short loc_10019E26
0x10019e0e  mov     edi, edi
0x10019e10  imul    edx, ecx, 68h ; 'h'
0x10019e13  cmp     _rgsib[edx], ebx
0x10019e19  jz      short loc_10019E26
0x10019e1b  mov     ecx, dword_1016EB88[edx]
0x10019e21  cmp     ecx, 0FFFFFFFFh
0x10019e24  jnz     short loc_10019E10
0x10019e26  imul    ecx, 68h ; 'h'
0x10019e29  mov     [ebp+var_24], ecx
0x10019e2c  mov     edx, dword_1016EB94[ecx]
0x10019e32  mov     [ebp+var_1C], edx
0x10019e35  cmp     edx, 0FFFFFFFFh
0x10019e38  jz      loc_10019F4C
0x10019e3e  mov     edi, edi
0x10019e40  lea     ecx, [edx+edx*4]
0x10019e43  shl     ecx, 2
0x10019e46  mov     [ebp+var_10], ecx
0x10019e49  mov     edx, dword ptr (_rgiscb+4)[ecx]
0x10019e4f  cmp     eax, 0FFFFFFFFh
0x10019e52  jz      short loc_10019E6D
0x10019e54  imul    ecx, eax, 68h ; 'h'
0x10019e57  cmp     _rgsib[ecx], ebx
0x10019e5d  jz      short loc_10019E6A
0x10019e5f  mov     eax, dword_1016EB88[ecx]
0x10019e65  cmp     eax, 0FFFFFFFFh
0x10019e68  jnz     short loc_10019E54
0x10019e6a  mov     ecx, [ebp+var_10]
0x10019e6d  test    eax, eax
0x10019e6f  jns     short loc_10019E76
0x10019e71  or      eax, 0FFFFFFFFh
0x10019e74  jmp     short loc_10019E82
0x10019e76  imul    eax, 68h ; 'h'
0x10019e79  lfence
0x10019e7c  mov     eax, dword_1016EB44[eax]
0x10019e82  mov     edi, _rgtib
0x10019e88  test    edi, edi
0x10019e8a  jz      short loc_10019EAA
0x10019e8c  cmp     edx, 27h ; '''
0x10019e8f  ja      short loc_10019EAA
0x10019e91  cmp     eax, 3Fh ; '?'
0x10019e94  ja      short loc_10019EAA
0x10019e96  imul    eax, 243h
0x10019e9c  lfence
0x10019e9f  add     eax, edx
0x10019ea1  mov     edi, [edi+eax*4+420h]
0x10019ea8  jmp     short loc_10019EAC
0x10019eaa  xor     edi, edi
0x10019eac  mov     esi, dword ptr (_rgiscb+0Ch)[ecx]
0x10019eb2  cmp     esi, 0FFFFFFFFh
0x10019eb5  jz      short loc_10019EE9
0x10019eb7  mov     eax, _mpdbidiiscb[esi*4]
0x10019ebe  lea     eax, [eax+eax*4]
0x10019ec1  mov     eax, dword ptr _rgiscb[eax*4]
0x10019ec8  cmp     eax, dword ptr _rgiscb[ecx]
0x10019ece  jnz     short loc_10019EE9
0x10019ed0  push    0
0x10019ed2  push    esi
0x10019ed3  push    ebx
0x10019ed4  call    _ErrDispCloseDatabase@12; ErrDispCloseDatabase(x,x,x)
0x10019ed9  test    eax, eax
0x10019edb  jns     short loc_10019EE6
0x10019edd  push    1
0x10019edf  push    esi
0x10019ee0  push    ebx
0x10019ee1  call    _ErrDispCloseDatabase@12; ErrDispCloseDatabase(x,x,x)
0x10019ee6  mov     ecx, [ebp+var_10]
0x10019ee9  mov     eax, [edi]
0x10019eeb  push    0; unsigned int
0x10019eed  push    dword ptr _rgiscb[ecx]; void *
0x10019ef3  mov     esi, [eax+20h]
0x10019ef6  mov     ecx, esi
0x10019ef8  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10019efe  call    esi
0x10019f00  mov     ecx, [ebp+var_10]
0x10019f03  dec     dword ptr [edi+0Ch]
0x10019f06  mov     eax, [ebp+var_1C]
0x10019f09  mov     edx, dword ptr (_rgiscb+8)[ecx]
0x10019f0f  mov     [ebp+var_1C], edx
0x10019f12  cmp     edx, 0FFFFFFFFh
0x10019f15  jz      short loc_10019F21
0x10019f17  mov     eax, _isibHead
0x10019f1c  jmp     loc_10019E40
0x10019f21  mov     edi, [ebp+var_14]
0x10019f24  cmp     eax, 0FFFFFFFFh
0x10019f27  jz      short loc_10019F4C
0x10019f29  mov     eax, dword_10130574
0x10019f2e  mov     dword ptr (_rgiscb+8)[ecx], eax
0x10019f34  mov     ecx, [ebp+var_24]
0x10019f37  mov     eax, dword_1016EB94[ecx]
0x10019f3d  mov     dword_10130574, eax
0x10019f42  mov     dword_1016EB94[ecx], 0FFFFFFFFh
0x10019f4c  cmp     _rgtib, 0
0x10019f53  jz      loc_10019DD6
0x10019f59  mov     ecx, dword_1016EB98[edi]
0x10019f5f  mov     edx, ecx
0x10019f61  call    _ReleaseIscb@8; ReleaseIscb(x,x)
0x10019f66  mov     ecx, [ebp+var_20]
0x10019f69  call    _ReleaseIsib@4; ReleaseIsib(x)
0x10019f6e  cmp     dword_10130568, 0
0x10019f75  jz      loc_1001A285
0x10019f7b  test    ebx, ebx
0x10019f7d  jz      loc_1001A285
0x10019f83  mov     [ebp+var_4], 0
0x10019f8a  cmp     dword ptr [ebx+8], 0
0x10019f8e  jle     short loc_10019FD1
  ... truncated ...
```
