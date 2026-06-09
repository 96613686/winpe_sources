# JetEndSession(x,x)

- ea: `0x10019a50`
- end: `0x1001a167`
- name: `_JetEndSession@8`
- size: `1815`
- prototype: `JET_ERR __stdcall(JET_SESID sesid, JET_GRBIT grbit)`
- caller_count: `0`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x10019a50`
- `0x10029190`
- `0x1002a430`
- `0x1003e530`
- `0x1003e820`
- `0x100429d0`
- `0x100453f0`
- `0x1004d890`
- `0x1004f70d`
- `0x10050000`
- `0x10057fbf`
- `0x1005e5b8`
- `0x1009633f`
- `0x100a432f`
- `0x10122f60`
- `0x10123ae2`
- `0x10123af8`
- `0x10123e98`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x10019f71`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x10019f71`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10019ac4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10019c9c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001a14b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10019ac4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10019c9c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001a14b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10019a80`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10019a80`

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
    v2 = dword_1016EAE8[26 * v2];
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
    dword_1016EAEC[26 * v2] = 0;
    RollbackIsamTransactions(sesid, 1);
    v6 = dword_1016EAF0[26 * v2];
    v71 = v6;
    if ( v6 > 0 )
    {
      *(int *)((char *)dword_1016EAF0 + v5) = 0;
      v73 = v5;
      do
      {
        if ( dword_1013107C )
        {
          v7 = HenvOfSesid(v3);
          v74 = v7;
          v8 = *((_DWORD *)dword_1013107C + 7);
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
  if ( dword_1013107C )
  {
    v15 = HenvOfSesid(v3);
    for ( i = (_DWORD *)*((_DWORD *)dword_1013107C + 7); i; i = (_DWORD *)i[53] )
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
  v21 = (int)*(&rgiscb + 5 * *(int *)((char *)dword_1016EAD0 + v5) + 3);
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
  for ( j = isibHead; j != -1; j = dword_1016EAE8[26 * j] )
  {
    if ( rgsib[26 * j] == v3 )
      break;
  }
  v69 = 104 * j;
  v24 = dword_1016EAF4[26 * j];
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
          v22 = dword_1016EAE8[26 * v22];
        }
        while ( v22 != -1 );
        v25 = v74;
      }
      if ( v22 >= 0 )
      {
        _mm_lfence();
        v27 = dword_1016EAA4[26 * v22];
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
      *(void **)((char *)&rgiscb + v30 + 8) = (void *)dword_101304DC;
      dword_101304DC = *(int *)((char *)dword_1016EAF4 + v69);
      *(int *)((char *)dword_1016EAF4 + v69) = -1;
    }
  }
  if ( !rgtib )
    goto LABEL_44;
  ReleaseIscb(*(int *)((char *)dword_1016EAF8 + v5), *(int *)((char *)dword_1016EAF8 + v5));
  ReleaseIsib(k);
  if ( dword_101304D0 && v3 )
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
0x10019a50  mov     edi, edi
0x10019a52  push    ebp
0x10019a53  mov     ebp, esp
0x10019a55  push    0FFFFFFFFh
0x10019a57  push    offset _JetEndSession@8_SEH
0x10019a5c  mov     eax, large fs:0
0x10019a62  push    eax
0x10019a63  sub     esp, 2Ch
0x10019a66  push    ebx
0x10019a67  push    esi
0x10019a68  push    edi
0x10019a69  mov     eax, ___security_cookie
0x10019a6e  xor     eax, ebp
0x10019a70  push    eax; unsigned int
0x10019a71  lea     eax, [ebp+var_C]
0x10019a74  mov     large fs:0, eax
0x10019a7a  push    _critJet; lpCriticalSection
0x10019a80  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10019a86  mov     esi, _isibHead
0x10019a8c  mov     ebx, [ebp+sesid]
0x10019a8f  mov     [ebp+var_20], esi
0x10019a92  cmp     esi, 0FFFFFFFFh
0x10019a95  jz      short loc_10019ABE
0x10019a97  nop     word ptr [eax+eax+00000000h]
0x10019aa0  imul    eax, esi, 68h ; 'h'
0x10019aa3  cmp     _rgsib[eax], ebx
0x10019aa9  jz      short loc_10019AB6
0x10019aab  mov     esi, dword_1016EAE8[eax]
0x10019ab1  cmp     esi, 0FFFFFFFFh
0x10019ab4  jnz     short loc_10019AA0
0x10019ab6  mov     [ebp+var_20], esi
0x10019ab9  cmp     esi, 0FFFFFFFFh
0x10019abc  jnz     short loc_10019AE3
0x10019abe  push    _critJet; lpCriticalSection
0x10019ac4  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10019aca  mov     eax, 0FFFFFBB0h
0x10019acf  mov     ecx, [ebp+var_C]
0x10019ad2  mov     large fs:0, ecx
0x10019ad9  pop     ecx
0x10019ada  pop     edi
0x10019adb  pop     esi
0x10019adc  pop     ebx
0x10019add  mov     esp, ebp
0x10019adf  pop     ebp
0x10019ae0  retn    8
0x10019ae3  mov     edx, 1
0x10019ae8  mov     ecx, ebx
0x10019aea  call    _NotifyRollbackTransaction@8; NotifyRollbackTransaction(x,x)
0x10019aef  push    1; char
0x10019af1  push    ebx; Session *
0x10019af2  call    _ErrIsamRollback@8; ErrIsamRollback(x,x)
0x10019af7  imul    edi, esi, 68h ; 'h'
0x10019afa  mov     [ebp+var_18], eax
0x10019afd  mov     [ebp+var_14], edi
0x10019b00  test    eax, eax
0x10019b02  js      loc_10019C0C
0x10019b08  mov     edx, 1
0x10019b0d  mov     dword_1016EAEC[edi], 0
0x10019b17  mov     ecx, ebx
0x10019b19  call    _RollbackIsamTransactions@8; RollbackIsamTransactions(x,x)
0x10019b1e  mov     esi, dword_1016EAF0[edi]
0x10019b24  mov     [ebp+var_1C], esi
0x10019b27  test    esi, esi
0x10019b29  jle     loc_10019C0F
0x10019b2f  mov     dword_1016EAF0[edi], 0
0x10019b39  mov     [ebp+var_14], edi
0x10019b3c  nop     dword ptr [eax+00h]
0x10019b40  cmp     dword_1013107C, 0
0x10019b47  jz      loc_10019BFB
0x10019b4d  mov     ecx, ebx
0x10019b4f  call    _HenvOfSesid@4; HenvOfSesid(x)
0x10019b54  mov     ecx, dword_1013107C
0x10019b5a  mov     [ebp+var_10], eax
0x10019b5d  mov     edi, [ecx+1Ch]
0x10019b60  test    edi, edi
0x10019b62  jz      loc_10019BFB
0x10019b68  cmp     dword ptr [edi+18h], 0
0x10019b6c  jz      short loc_10019BE7
0x10019b6e  cmp     [edi+1Ch], eax
0x10019b71  jnz     short loc_10019BE7
0x10019b73  mov     ecx, [ebp+sesid]
0x10019b76  lea     esi, [edi+20h]
0x10019b79  mov     eax, esi
0x10019b7b  lea     ebx, [eax+0A0h]
0x10019b81  cmp     eax, ebx
0x10019b83  jnb     short loc_10019B92
0x10019b85  cmp     [eax], ecx
0x10019b87  jz      short loc_10019B90
0x10019b89  add     eax, 8
0x10019b8c  cmp     eax, ebx
0x10019b8e  jb      short loc_10019B85
0x10019b90  cmp     eax, ebx
0x10019b92  sbb     edx, edx
0x10019b94  and     edx, eax
0x10019b96  jz      short loc_10019BE4
0x10019b98  test    byte ptr [edi+4], 4
0x10019b9c  jnz     short loc_10019BE4
0x10019b9e  mov     al, [edx+4]
0x10019ba1  test    al, al
0x10019ba3  jle     short loc_10019BB6
0x10019ba5  dec     al
0x10019ba7  mov     [edx+4], al
0x10019baa  mov     eax, 0FFFFh
0x10019baf  add     [edi+0C0h], ax
0x10019bb6  cmp     word ptr [edi+0C0h], 0
0x10019bbe  jnz     short loc_10019BE4
0x10019bc0  push    1
0x10019bc2  mov     edx, edi
0x10019bc4  call    ErrRmtSimComRbk
0x10019bc9  cmp     word ptr [edi], 0
0x10019bcd  jnz     short loc_10019BE4
0x10019bcf  cmp     esi, ebx
0x10019bd1  jnb     short loc_10019BE4
0x10019bd3  mov     dword ptr [esi], 0FFFFFFFFh
0x10019bd9  mov     byte ptr [esi+4], 0
0x10019bdd  add     esi, 8
0x10019be0  cmp     esi, ebx
0x10019be2  jb      short loc_10019BD3
0x10019be4  mov     eax, [ebp+var_10]
0x10019be7  mov     edi, [edi+0D4h]
0x10019bed  test    edi, edi
0x10019bef  jnz     loc_10019B68
0x10019bf5  mov     ebx, [ebp+sesid]
0x10019bf8  mov     esi, [ebp+var_1C]
0x10019bfb  sub     esi, 1
0x10019bfe  mov     [ebp+var_1C], esi
0x10019c01  jnz     loc_10019B40
0x10019c07  mov     edi, [ebp+var_14]
0x10019c0a  jmp     short loc_10019C0F
0x10019c0c  mov     [ebp+var_14], edi
0x10019c0f  cmp     dword_1013107C, 0
0x10019c16  jz      short loc_10019C65
0x10019c18  mov     ecx, ebx
0x10019c1a  call    _HenvOfSesid@4; HenvOfSesid(x)
0x10019c1f  mov     ecx, dword_1013107C
0x10019c25  mov     esi, eax
0x10019c27  mov     edx, [ecx+1Ch]
0x10019c2a  test    edx, edx
0x10019c2c  jz      short loc_10019C65
0x10019c2e  mov     edi, edi
0x10019c30  cmp     [edx+1Ch], esi
0x10019c33  jnz     short loc_10019C5B
0x10019c35  lea     eax, [edx+20h]
0x10019c38  lea     ecx, [eax+0A0h]
0x10019c3e  cmp     eax, ecx
0x10019c40  jnb     short loc_10019C4F
0x10019c42  cmp     [eax], ebx
0x10019c44  jz      short loc_10019C4D
0x10019c46  add     eax, 8
0x10019c49  cmp     eax, ecx
0x10019c4b  jb      short loc_10019C42
0x10019c4d  cmp     eax, ecx
0x10019c4f  sbb     ecx, ecx
0x10019c51  and     ecx, eax
0x10019c53  jz      short loc_10019C5B
0x10019c55  mov     dword ptr [ecx], 0FFFFFFFFh
0x10019c5b  mov     edx, [edx+0D4h]
0x10019c61  test    edx, edx
0x10019c63  jnz     short loc_10019C30
0x10019c65  push    ebx
0x10019c66  call    _ClearErrorInfo@4; ClearErrorInfo(x)
0x10019c6b  mov     eax, dword_1016EAD0[edi]
0x10019c71  lea     eax, [eax+eax*4]
0x10019c74  mov     esi, dword ptr (_rgiscb+0Ch)[eax*4]
0x10019c7b  cmp     esi, 0FFFFFFFFh
0x10019c7e  jz      short loc_10019CC2
0x10019c80  push    0
0x10019c82  push    esi
0x10019c83  push    ebx
0x10019c84  call    _ErrDispCloseDatabase@12; ErrDispCloseDatabase(x,x,x)
0x10019c89  mov     [ebp+var_18], eax
0x10019c8c  test    eax, eax
0x10019c8e  jns     short loc_10019CC2
0x10019c90  test    byte ptr [ebp+grbit], 1
0x10019c94  jnz     short loc_10019CB9
0x10019c96  push    _critJet; lpCriticalSection
0x10019c9c  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10019ca2  mov     eax, [ebp+var_18]
0x10019ca5  mov     ecx, [ebp+var_C]
0x10019ca8  mov     large fs:0, ecx
0x10019caf  pop     ecx
0x10019cb0  pop     edi
0x10019cb1  pop     esi
0x10019cb2  pop     ebx
0x10019cb3  mov     esp, ebp
0x10019cb5  pop     ebp
0x10019cb6  retn    8
0x10019cb9  push    1
0x10019cbb  push    esi
0x10019cbc  push    ebx
0x10019cbd  call    _ErrDispCloseDatabase@12; ErrDispCloseDatabase(x,x,x)
0x10019cc2  mov     eax, _isibHead
0x10019cc7  mov     ecx, eax
0x10019cc9  cmp     ecx, 0FFFFFFFFh
0x10019ccc  jz      short loc_10019CE6
0x10019cce  mov     edi, edi
0x10019cd0  imul    edx, ecx, 68h ; 'h'
0x10019cd3  cmp     _rgsib[edx], ebx
0x10019cd9  jz      short loc_10019CE6
0x10019cdb  mov     ecx, dword_1016EAE8[edx]
0x10019ce1  cmp     ecx, 0FFFFFFFFh
0x10019ce4  jnz     short loc_10019CD0
0x10019ce6  imul    ecx, 68h ; 'h'
0x10019ce9  mov     [ebp+var_24], ecx
0x10019cec  mov     edx, dword_1016EAF4[ecx]
0x10019cf2  mov     [ebp+var_1C], edx
0x10019cf5  cmp     edx, 0FFFFFFFFh
0x10019cf8  jz      loc_10019E0C
0x10019cfe  mov     edi, edi
0x10019d00  lea     ecx, [edx+edx*4]
0x10019d03  shl     ecx, 2
0x10019d06  mov     [ebp+var_10], ecx
0x10019d09  mov     edx, dword ptr (_rgiscb+4)[ecx]
0x10019d0f  cmp     eax, 0FFFFFFFFh
0x10019d12  jz      short loc_10019D2D
0x10019d14  imul    ecx, eax, 68h ; 'h'
0x10019d17  cmp     _rgsib[ecx], ebx
0x10019d1d  jz      short loc_10019D2A
0x10019d1f  mov     eax, dword_1016EAE8[ecx]
0x10019d25  cmp     eax, 0FFFFFFFFh
0x10019d28  jnz     short loc_10019D14
0x10019d2a  mov     ecx, [ebp+var_10]
0x10019d2d  test    eax, eax
0x10019d2f  jns     short loc_10019D36
0x10019d31  or      eax, 0FFFFFFFFh
0x10019d34  jmp     short loc_10019D42
0x10019d36  imul    eax, 68h ; 'h'
0x10019d39  lfence
0x10019d3c  mov     eax, dword_1016EAA4[eax]
0x10019d42  mov     edi, _rgtib
0x10019d48  test    edi, edi
0x10019d4a  jz      short loc_10019D6A
0x10019d4c  cmp     edx, 27h ; '''
0x10019d4f  ja      short loc_10019D6A
0x10019d51  cmp     eax, 3Fh ; '?'
0x10019d54  ja      short loc_10019D6A
0x10019d56  imul    eax, 243h
0x10019d5c  lfence
0x10019d5f  add     eax, edx
0x10019d61  mov     edi, [edi+eax*4+420h]
0x10019d68  jmp     short loc_10019D6C
0x10019d6a  xor     edi, edi
0x10019d6c  mov     esi, dword ptr (_rgiscb+0Ch)[ecx]
0x10019d72  cmp     esi, 0FFFFFFFFh
0x10019d75  jz      short loc_10019DA9
0x10019d77  mov     eax, _mpdbidiiscb[esi*4]
0x10019d7e  lea     eax, [eax+eax*4]
0x10019d81  mov     eax, dword ptr _rgiscb[eax*4]
0x10019d88  cmp     eax, dword ptr _rgiscb[ecx]
0x10019d8e  jnz     short loc_10019DA9
0x10019d90  push    0
0x10019d92  push    esi
0x10019d93  push    ebx
0x10019d94  call    _ErrDispCloseDatabase@12; ErrDispCloseDatabase(x,x,x)
0x10019d99  test    eax, eax
0x10019d9b  jns     short loc_10019DA6
0x10019d9d  push    1
0x10019d9f  push    esi
0x10019da0  push    ebx
0x10019da1  call    _ErrDispCloseDatabase@12; ErrDispCloseDatabase(x,x,x)
0x10019da6  mov     ecx, [ebp+var_10]
0x10019da9  mov     eax, [edi]
0x10019dab  push    0; unsigned int
0x10019dad  push    dword ptr _rgiscb[ecx]; void *
0x10019db3  mov     esi, [eax+20h]
0x10019db6  mov     ecx, esi
0x10019db8  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10019dbe  call    esi
0x10019dc0  mov     ecx, [ebp+var_10]
0x10019dc3  dec     dword ptr [edi+0Ch]
0x10019dc6  mov     eax, [ebp+var_1C]
0x10019dc9  mov     edx, dword ptr (_rgiscb+8)[ecx]
0x10019dcf  mov     [ebp+var_1C], edx
0x10019dd2  cmp     edx, 0FFFFFFFFh
0x10019dd5  jz      short loc_10019DE1
0x10019dd7  mov     eax, _isibHead
0x10019ddc  jmp     loc_10019D00
0x10019de1  mov     edi, [ebp+var_14]
0x10019de4  cmp     eax, 0FFFFFFFFh
0x10019de7  jz      short loc_10019E0C
0x10019de9  mov     eax, dword_101304DC
0x10019dee  mov     dword ptr (_rgiscb+8)[ecx], eax
0x10019df4  mov     ecx, [ebp+var_24]
0x10019df7  mov     eax, dword_1016EAF4[ecx]
0x10019dfd  mov     dword_101304DC, eax
0x10019e02  mov     dword_1016EAF4[ecx], 0FFFFFFFFh
0x10019e0c  cmp     _rgtib, 0
0x10019e13  jz      loc_10019C96
0x10019e19  mov     ecx, dword_1016EAF8[edi]
0x10019e1f  mov     edx, ecx
0x10019e21  call    _ReleaseIscb@8; ReleaseIscb(x,x)
0x10019e26  mov     ecx, [ebp+var_20]
0x10019e29  call    _ReleaseIsib@4; ReleaseIsib(x)
0x10019e2e  cmp     dword_101304D0, 0
0x10019e35  jz      loc_1001A145
0x10019e3b  test    ebx, ebx
0x10019e3d  jz      loc_1001A145
0x10019e43  mov     [ebp+var_4], 0
0x10019e4a  cmp     dword ptr [ebx+8], 0
0x10019e4e  jle     short loc_10019E91
  ... truncated ...
```
