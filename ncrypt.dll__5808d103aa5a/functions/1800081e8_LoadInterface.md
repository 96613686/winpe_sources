# _LoadInterface

- ea: `0x1800081e8`
- end: `0x18000873c`
- name: `_LoadInterface`
- size: `1364`
- prototype: `__int64 __fastcall(HMODULE, unsigned int *, int, _WORD **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180007df4`

## callees

- `0x1800081e8`
- `0x18000d02c`
- `0x18000e120`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000830b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000830b`

## string_xrefs

- `0x1800082b3`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x18000831e`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x180008554`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x18000857b`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`

## pseudocode

```c
__int64 __fastcall LoadInterface(HMODULE a1, unsigned int *a2, int a3, _WORD **a4)
{
  unsigned int v4; // eax
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // eax
  const CHAR *v11; // rdx
  unsigned int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  int v16; // edi
  FARPROC ProcAddress; // r10
  __int64 v18; // r9
  __int64 v19; // rcx
  unsigned int v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  __int64 v25; // r9
  unsigned int v26; // eax
  unsigned int v27; // eax
  unsigned int v28; // eax
  unsigned int v29; // eax
  __int64 v30; // rcx
  unsigned int v31; // eax
  int v32; // esi
  unsigned int v33; // eax
  unsigned int v34; // eax
  unsigned int v35; // eax
  unsigned int v36; // eax
  __int64 v37; // r9
  unsigned int v39; // eax
  unsigned int v40; // eax
  unsigned int v41; // eax
  unsigned int v42; // eax
  __int64 v43; // r9

  v4 = *a2;
  if ( *a2 > 6 )
  {
    v12 = v4 - 7;
    if ( v12 )
    {
      v13 = v12 - 1;
      if ( v13 )
      {
        v14 = v13 - 65529;
        if ( v14 )
        {
          v15 = v14 - 1;
          if ( v15 )
          {
            if ( v15 != 2 )
              goto LABEL_19;
            v11 = "GetKeyProtectionInterface";
          }
          else
          {
            v11 = "GetSChannelInterface";
          }
        }
        else
        {
          v11 = "GetKeyStorageInterface";
        }
      }
      else
      {
        v11 = "GetKeyEncapsulationInterface";
      }
    }
    else
    {
      v11 = "GetKeyDerivationInterface";
    }
  }
  else if ( v4 == 6 )
  {
    v11 = "GetRngInterface";
  }
  else
  {
    v7 = v4 - 1;
    if ( v7 )
    {
      v8 = v7 - 1;
      if ( v8 )
      {
        v9 = v8 - 1;
        if ( v9 )
        {
          v10 = v9 - 1;
          if ( v10 )
          {
            if ( v10 == 1 )
            {
              v11 = "GetSignatureInterface";
              goto LABEL_27;
            }
LABEL_19:
            v16 = -1073741637;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_sDsd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                1,
                a3,
                (unsigned int)"sResult",
                187,
                (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c",
                104);
            return (unsigned int)v16;
          }
          v11 = "GetSecretAgreementInterface";
        }
        else
        {
          v11 = "GetAsymmetricEncryptionInterface";
        }
      }
      else
      {
        v11 = "GetHashInterface";
      }
    }
    else
    {
      v11 = "GetCipherInterface";
    }
  }
LABEL_27:
  ProcAddress = GetProcAddress(a1, v11);
  if ( !ProcAddress )
  {
    v16 = -1073741511;
    v18 = 1907;
    v19 = 3221225785LL;
LABEL_86:
    DebugTraceError(v19, "sResult", "onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c", v18);
    return (unsigned int)v16;
  }
  v20 = *a2;
  if ( *a2 > 6 )
  {
    v26 = v20 - 7;
    if ( !v26 )
    {
      v16 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _WORD **, _QWORD))ProcAddress)(
              *((_QWORD *)a2 + 2),
              *((_QWORD *)a2 + 1),
              a4,
              0);
      if ( v16 < 0 )
      {
        v25 = 1559;
        goto LABEL_64;
      }
      goto LABEL_66;
    }
    v27 = v26 - 1;
    if ( !v27 )
    {
      v16 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _WORD **, _QWORD))ProcAddress)(
              *((_QWORD *)a2 + 2),
              *((_QWORD *)a2 + 1),
              a4,
              0);
      if ( v16 < 0 )
      {
        v25 = 1572;
        goto LABEL_64;
      }
      goto LABEL_66;
    }
    v28 = v27 - 65529;
    if ( !v28 )
    {
      v16 = ((__int64 (__fastcall *)(_QWORD, _WORD **, _QWORD))ProcAddress)(*((_QWORD *)a2 + 2), a4, 0);
      if ( v16 < 0 )
      {
        v25 = 1584;
        goto LABEL_64;
      }
      goto LABEL_66;
    }
    v29 = v28 - 1;
    if ( !v29 )
    {
      v16 = ((__int64 (__fastcall *)(_QWORD, _WORD **, _QWORD))ProcAddress)(*((_QWORD *)a2 + 2), a4, 0);
      if ( v16 < 0 )
      {
        v25 = 1608;
        goto LABEL_64;
      }
      goto LABEL_66;
    }
    if ( v29 == 2 )
    {
      v16 = ((__int64 (__fastcall *)(_QWORD, _WORD **, _QWORD))ProcAddress)(*((_QWORD *)a2 + 2), a4, 0);
      if ( v16 < 0 )
      {
        v25 = 1596;
        goto LABEL_64;
      }
      goto LABEL_66;
    }
    goto LABEL_53;
  }
  if ( v20 == 6 )
  {
    v16 = ((__int64 (__fastcall *)(_QWORD, _WORD **, _QWORD))ProcAddress)(*((_QWORD *)a2 + 2), a4, 0);
    if ( v16 < 0 )
    {
      v25 = 1546;
      goto LABEL_64;
    }
    goto LABEL_66;
  }
  v21 = v20 - 1;
  if ( !v21 )
  {
    v16 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _WORD **, _QWORD))ProcAddress)(
            *((_QWORD *)a2 + 2),
            *((_QWORD *)a2 + 1),
            a4,
            0);
    if ( v16 < 0 )
    {
      v25 = 1482;
      goto LABEL_64;
    }
    goto LABEL_66;
  }
  v22 = v21 - 1;
  if ( !v22 )
  {
    v16 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _WORD **, _QWORD))ProcAddress)(
            *((_QWORD *)a2 + 2),
            *((_QWORD *)a2 + 1),
            a4,
            0);
    if ( v16 < 0 )
    {
      v25 = 1495;
      goto LABEL_64;
    }
    goto LABEL_66;
  }
  v23 = v22 - 1;
  if ( !v23 )
  {
    v16 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _WORD **, _QWORD))ProcAddress)(
            *((_QWORD *)a2 + 2),
            *((_QWORD *)a2 + 1),
            a4,
            0);
    if ( v16 < 0 )
    {
      v25 = 1508;
      goto LABEL_64;
    }
    goto LABEL_66;
  }
  v24 = v23 - 1;
  if ( v24 )
  {
    if ( v24 == 1 )
    {
      v16 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _WORD **, _QWORD))ProcAddress)(
              *((_QWORD *)a2 + 2),
              *((_QWORD *)a2 + 1),
              a4,
              0);
      if ( v16 < 0 )
      {
        v25 = 1534;
LABEL_64:
        v30 = (unsigned int)v16;
        goto LABEL_65;
      }
      goto LABEL_66;
    }
LABEL_53:
    v16 = -1073741637;
    v30 = 3221225659LL;
    v25 = 1614;
LABEL_65:
    DebugTraceError(v30, "ntStatus", "onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c", v25);
    v18 = 1927;
    v19 = (unsigned int)v16;
    goto LABEL_86;
  }
  v16 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _WORD **, _QWORD))ProcAddress)(
          *((_QWORD *)a2 + 2),
          *((_QWORD *)a2 + 1),
          a4,
          0);
  if ( v16 < 0 )
  {
    v25 = 1521;
    goto LABEL_64;
  }
LABEL_66:
  v31 = *a2;
  v32 = 0;
  if ( *a2 > 6 )
  {
    v39 = v31 - 7;
    if ( v39 )
    {
      v40 = v39 - 1;
      if ( v40 )
      {
        v41 = v40 - 65529;
        if ( v41 )
        {
          v42 = v41 - 1;
          if ( v42 )
          {
            if ( v42 != 2 )
            {
LABEL_95:
              v43 = 1450;
LABEL_96:
              v16 = -1073741637;
              v32 = -1073741637;
              DebugTraceError(
                3221225659LL,
                "ntStatus",
                "onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c",
                v43);
              goto LABEL_85;
            }
            if ( !**a4 )
            {
              v37 = 1434;
              goto LABEL_83;
            }
          }
          else if ( !**a4 )
          {
            v37 = 1444;
            goto LABEL_83;
          }
        }
        else if ( !**a4 )
        {
          v37 = 1424;
          goto LABEL_83;
        }
      }
      else if ( !**a4 )
      {
        v37 = 1414;
        goto LABEL_83;
      }
    }
    else if ( !**a4 )
    {
      v43 = 1404;
      goto LABEL_96;
    }
  }
  else
  {
    if ( v31 != 6 )
    {
      v33 = v31 - 1;
      if ( !v33 )
      {
        if ( **a4 )
          goto LABEL_84;
        v37 = 1344;
        goto LABEL_83;
      }
      v34 = v33 - 1;
      if ( !v34 )
      {
        if ( **a4 )
          goto LABEL_84;
        v37 = 1354;
        goto LABEL_83;
      }
      v35 = v34 - 1;
      if ( !v35 )
      {
        if ( **a4 )
          goto LABEL_84;
        v37 = 1364;
        goto LABEL_83;
      }
      v36 = v35 - 1;
      if ( !v36 )
      {
        if ( **a4 )
          goto LABEL_84;
        v37 = 1374;
        goto LABEL_83;
      }
      if ( v36 == 1 )
      {
        if ( **a4 )
          goto LABEL_84;
        v37 = 1384;
        goto LABEL_83;
      }
      goto LABEL_95;
    }
    if ( !**a4 )
    {
      v37 = 1394;
LABEL_83:
      v32 = -1073741637;
      DebugTraceError(3221225659LL, "ntStatus", "onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c", v37);
    }
  }
LABEL_84:
  v16 = v32;
  if ( v32 < 0 )
  {
LABEL_85:
    v18 = 1922;
    v19 = (unsigned int)v32;
    goto LABEL_86;
  }
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x1800081e8  push    rbx
0x1800081ea  push    rsi
0x1800081eb  push    rdi
0x1800081ec  push    r14
0x1800081ee  sub     rsp, 48h
0x1800081f2  mov     eax, [rdx]
0x1800081f4  mov     r14, r9
0x1800081f7  mov     rbx, rdx
0x1800081fa  cmp     eax, 6
0x1800081fd  ja      short loc_180008262
0x1800081ff  jz      short loc_180008256
0x180008201  sub     eax, 1
0x180008204  jz      short loc_18000824A
0x180008206  sub     eax, 1
0x180008209  jz      short loc_18000823E
0x18000820b  sub     eax, 1
0x18000820e  jz      short loc_180008232
0x180008210  sub     eax, 1
0x180008213  jz      short loc_180008226
0x180008215  cmp     eax, 1
0x180008218  jnz     short loc_180008285
0x18000821a  lea     rdx, aGetsignaturein; "GetSignatureInterface"
0x180008221  jmp     loc_18000830B
0x180008226  lea     rdx, aGetsecretagree; "GetSecretAgreementInterface"
0x18000822d  jmp     loc_18000830B
0x180008232  lea     rdx, aGetasymmetrice; "GetAsymmetricEncryptionInterface"
0x180008239  jmp     loc_18000830B
0x18000823e  lea     rdx, aGethashinterfa; "GetHashInterface"
0x180008245  jmp     loc_18000830B
0x18000824a  lea     rdx, aGetcipherinter; "GetCipherInterface"
0x180008251  jmp     loc_18000830B
0x180008256  lea     rdx, aGetrnginterfac; "GetRngInterface"
0x18000825d  jmp     loc_18000830B
0x180008262  sub     eax, 7
0x180008265  jz      loc_180008304
0x18000826b  sub     eax, 1
0x18000826e  jz      loc_1800082FB
0x180008274  sub     eax, 0FFF9h
0x180008279  jz      short loc_1800082F2
0x18000827b  sub     eax, 1
0x18000827e  jz      short loc_1800082E9
0x180008280  cmp     eax, 2
0x180008283  jz      short loc_1800082E0
0x180008285  mov     edi, 0C00000BBh
0x18000828a  mov     rax, cs:WPP_GLOBAL_Control
0x180008291  lea     rcx, WPP_GLOBAL_Control
0x180008298  cmp     rax, rcx
0x18000829b  jz      loc_180008649
0x1800082a1  mov     edx, 1
0x1800082a6  test    [rax+1Ch], dl
0x1800082a9  jz      loc_180008649
0x1800082af  mov     rcx, [rax+10h]
0x1800082b3  lea     rbx, aOnecoreDsSecur_12; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800082ba  mov     [rsp+68h+var_38], 768h
0x1800082c2  lea     r9, aSresult; "sResult"
0x1800082c9  mov     [rsp+68h+var_40], rbx
0x1800082ce  mov     [rsp+68h+var_48], 0C00000BBh
0x1800082d6  call    WPP_SF_sDsd
0x1800082db  jmp     loc_180008649
0x1800082e0  lea     rdx, aGetkeyprotecti; "GetKeyProtectionInterface"
0x1800082e7  jmp     short loc_18000830B
0x1800082e9  lea     rdx, aGetschannelint_0; "GetSChannelInterface"
0x1800082f0  jmp     short loc_18000830B
0x1800082f2  lea     rdx, aGetkeystoragei_0; "GetKeyStorageInterface"
0x1800082f9  jmp     short loc_18000830B
0x1800082fb  lea     rdx, aGetkeyencapsul; "GetKeyEncapsulationInterface"
0x180008302  jmp     short loc_18000830B
0x180008304  lea     rdx, ProcName; "GetKeyDerivationInterface"
0x18000830b  call    cs:__imp_GetProcAddress
0x180008311  mov     r10, rax
0x180008314  test    rax, rax
0x180008317  jnz     short loc_180008335
0x180008319  mov     edi, 0C0000139h
0x18000831e  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180008325  mov     r9d, 773h
0x18000832b  mov     ecx, 0C0000139h
0x180008330  jmp     loc_18000863D
0x180008335  mov     eax, [rbx]
0x180008337  cmp     eax, 6
0x18000833a  ja      loc_180008469
0x180008340  jz      loc_180008442
0x180008346  sub     eax, 1
0x180008349  jz      loc_180008417
0x18000834f  sub     eax, 1
0x180008352  jz      loc_1800083EC
0x180008358  sub     eax, 1
0x18000835b  jz      short loc_1800083C1
0x18000835d  sub     eax, 1
0x180008360  jz      short loc_180008396
0x180008362  cmp     eax, 1
0x180008365  jnz     loc_18000848C
0x18000836b  mov     rdx, [rbx+8]
0x18000836f  xor     r9d, r9d
0x180008372  mov     rcx, [rbx+10h]
0x180008376  mov     r8, r14
0x180008379  mov     rax, r10
0x18000837c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008381  mov     edi, eax
0x180008383  test    eax, eax
0x180008385  jns     loc_180008577
0x18000838b  mov     r9d, 5FEh
0x180008391  jmp     loc_180008552
0x180008396  mov     rdx, [rbx+8]
0x18000839a  xor     r9d, r9d
0x18000839d  mov     rcx, [rbx+10h]
0x1800083a1  mov     r8, r14
0x1800083a4  mov     rax, r10
0x1800083a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083ac  mov     edi, eax
0x1800083ae  test    eax, eax
0x1800083b0  jns     loc_180008577
0x1800083b6  mov     r9d, 5F1h
0x1800083bc  jmp     loc_180008552
0x1800083c1  mov     rdx, [rbx+8]
0x1800083c5  xor     r9d, r9d
0x1800083c8  mov     rcx, [rbx+10h]
0x1800083cc  mov     r8, r14
0x1800083cf  mov     rax, r10
0x1800083d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083d7  mov     edi, eax
0x1800083d9  test    eax, eax
0x1800083db  jns     loc_180008577
0x1800083e1  mov     r9d, 5E4h
0x1800083e7  jmp     loc_180008552
0x1800083ec  mov     rdx, [rbx+8]
0x1800083f0  xor     r9d, r9d
0x1800083f3  mov     rcx, [rbx+10h]
0x1800083f7  mov     r8, r14
0x1800083fa  mov     rax, r10
0x1800083fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008402  mov     edi, eax
0x180008404  test    eax, eax
0x180008406  jns     loc_180008577
0x18000840c  mov     r9d, 5D7h
0x180008412  jmp     loc_180008552
0x180008417  mov     rdx, [rbx+8]
0x18000841b  xor     r9d, r9d
0x18000841e  mov     rcx, [rbx+10h]
0x180008422  mov     r8, r14
0x180008425  mov     rax, r10
0x180008428  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000842d  mov     edi, eax
0x18000842f  test    eax, eax
0x180008431  jns     loc_180008577
0x180008437  mov     r9d, 5CAh
0x18000843d  jmp     loc_180008552
0x180008442  mov     rcx, [rbx+10h]
0x180008446  xor     r8d, r8d
0x180008449  mov     rdx, r14
0x18000844c  mov     rax, r10
0x18000844f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008454  mov     edi, eax
0x180008456  test    eax, eax
0x180008458  jns     loc_180008577
0x18000845e  mov     r9d, 60Ah
0x180008464  jmp     loc_180008552
0x180008469  sub     eax, 7
0x18000846c  jz      loc_180008530
0x180008472  sub     eax, 1
0x180008475  jz      loc_18000850C
0x18000847b  sub     eax, 0FFF9h
0x180008480  jz      short loc_1800084EC
0x180008482  sub     eax, 1
0x180008485  jz      short loc_1800084C8
0x180008487  cmp     eax, 2
0x18000848a  jz      short loc_1800084A1
0x18000848c  mov     edi, 0C00000BBh
0x180008491  mov     ecx, 0C00000BBh
0x180008496  mov     r9d, 64Eh
0x18000849c  jmp     loc_180008554
0x1800084a1  mov     rcx, [rbx+10h]
0x1800084a5  xor     r8d, r8d
0x1800084a8  mov     rdx, r14
0x1800084ab  mov     rax, r10
0x1800084ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084b3  mov     edi, eax
0x1800084b5  test    eax, eax
0x1800084b7  jns     loc_180008577
0x1800084bd  mov     r9d, 63Ch
0x1800084c3  jmp     loc_180008552
0x1800084c8  mov     rcx, [rbx+10h]
0x1800084cc  xor     r8d, r8d
0x1800084cf  mov     rdx, r14
0x1800084d2  mov     rax, r10
0x1800084d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084da  mov     edi, eax
0x1800084dc  test    eax, eax
0x1800084de  jns     loc_180008577
0x1800084e4  mov     r9d, 648h
0x1800084ea  jmp     short loc_180008552
0x1800084ec  mov     rcx, [rbx+10h]
0x1800084f0  xor     r8d, r8d
0x1800084f3  mov     rdx, r14
0x1800084f6  mov     rax, r10
0x1800084f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084fe  mov     edi, eax
0x180008500  test    eax, eax
0x180008502  jns     short loc_180008577
0x180008504  mov     r9d, 630h
0x18000850a  jmp     short loc_180008552
0x18000850c  mov     rdx, [rbx+8]
0x180008510  xor     r9d, r9d
0x180008513  mov     rcx, [rbx+10h]
0x180008517  mov     r8, r14
0x18000851a  mov     rax, r10
0x18000851d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008522  mov     edi, eax
0x180008524  test    eax, eax
0x180008526  jns     short loc_180008577
0x180008528  mov     r9d, 624h
0x18000852e  jmp     short loc_180008552
0x180008530  mov     rdx, [rbx+8]
0x180008534  xor     r9d, r9d
0x180008537  mov     rcx, [rbx+10h]
0x18000853b  mov     r8, r14
0x18000853e  mov     rax, r10
0x180008541  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008546  mov     edi, eax
0x180008548  test    eax, eax
0x18000854a  jns     short loc_180008577
0x18000854c  mov     r9d, 617h
0x180008552  mov     ecx, edi
0x180008554  lea     rbx, aOnecoreDsSecur_12; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000855b  mov     r8, rbx
0x18000855e  lea     rdx, aNtstatus; "ntStatus"
0x180008565  call    DebugTraceError
0x18000856a  mov     r9d, 787h
0x180008570  mov     ecx, edi
0x180008572  jmp     loc_18000863A
0x180008577  mov     eax, [rbx]
0x180008579  xor     esi, esi
0x18000857b  lea     rbx, aOnecoreDsSecur_12; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180008582  cmp     eax, 6
0x180008585  ja      loc_18000866A
0x18000858b  jz      loc_180008655
0x180008591  sub     eax, 1
0x180008594  jz      short loc_180008600
0x180008596  sub     eax, 1
0x180008599  jz      short loc_1800085EB
0x18000859b  sub     eax, 1
0x18000859e  jz      short loc_1800085D6
0x1800085a0  sub     eax, 1
0x1800085a3  jz      short loc_1800085C1
0x1800085a5  cmp     eax, 1
0x1800085a8  jnz     loc_18000868D
0x1800085ae  mov     rax, [r14]
0x1800085b1  lea     edx, [rsi+1]
0x1800085b4  cmp     dx, [rax]
0x1800085b7  jbe     short loc_18000862C
0x1800085b9  mov     r9d, 568h
0x1800085bf  jmp     short loc_180008613
0x1800085c1  mov     rax, [r14]
0x1800085c4  mov     edx, 1
0x1800085c9  cmp     dx, [rax]
0x1800085cc  jbe     short loc_18000862C
0x1800085ce  mov     r9d, 55Eh
0x1800085d4  jmp     short loc_180008613
0x1800085d6  mov     rax, [r14]
0x1800085d9  mov     edx, 1
0x1800085de  cmp     dx, [rax]
0x1800085e1  jbe     short loc_18000862C
0x1800085e3  mov     r9d, 554h
0x1800085e9  jmp     short loc_180008613
0x1800085eb  mov     rax, [r14]
0x1800085ee  mov     edx, 1
0x1800085f3  cmp     dx, [rax]
0x1800085f6  jbe     short loc_18000862C
0x1800085f8  mov     r9d, 54Ah
0x1800085fe  jmp     short loc_180008613
0x180008600  mov     rax, [r14]
0x180008603  mov     edx, 1
0x180008608  cmp     dx, [rax]
0x18000860b  jbe     short loc_18000862C
0x18000860d  mov     r9d, 540h
0x180008613  mov     r8, rbx
0x180008616  lea     rdx, aNtstatus; "ntStatus"
0x18000861d  mov     ecx, 0C00000BBh
0x180008622  mov     esi, 0C00000BBh
0x180008627  call    DebugTraceError
0x18000862c  mov     edi, esi
0x18000862e  test    esi, esi
0x180008630  jns     short loc_180008649
0x180008632  mov     r9d, 782h
0x180008638  mov     ecx, esi
0x18000863a  mov     r8, rbx
0x18000863d  lea     rdx, aSresult; "sResult"
0x180008644  call    DebugTraceError
0x180008649  mov     eax, edi
0x18000864b  add     rsp, 48h
0x18000864f  pop     r14
0x180008651  pop     rdi
0x180008652  pop     rsi
0x180008653  pop     rbx
0x180008654  retn
0x180008655  mov     rax, [r14]
0x180008658  mov     edx, 1
0x18000865d  cmp     dx, [rax]
0x180008660  jbe     short loc_18000862C
0x180008662  mov     r9d, 572h
0x180008668  jmp     short loc_180008613
  ... truncated ...
```
