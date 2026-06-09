# _LoadInterface

- ea: `0x180004e34`
- end: `0x18000542d`
- name: `_LoadInterface`
- size: `1529`
- prototype: `__int64 __fastcall(HMODULE, int *, int, _WORD **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180004b70`

## callees

- `0x180003cf0`
- `0x180004470`
- `0x180004e34`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004e68`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004e68`

## string_xrefs

- `0x180004ea3`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x180004f4a`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x180004f80`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x180004fcc`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`

## pseudocode

```c
__int64 __fastcall LoadInterface(HMODULE a1, int *a2, int a3, _WORD **a4)
{
  int v4; // eax
  int v7; // eax
  const CHAR *v8; // rdx
  int v9; // edx
  int v10; // r8d
  FARPROC ProcAddress; // r10
  int v12; // ebx
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  int v24; // eax
  int v25; // ebp
  int v26; // eax
  int v27; // eax
  int v28; // eax
  int v29; // eax
  __int64 v30; // r9
  int v31; // eax
  int v32; // eax
  int v33; // eax
  int v34; // eax
  _QWORD *v35; // rcx
  int v36; // eax
  int v37; // eax
  int v38; // eax
  int v39; // eax
  __int64 v40; // r9
  int v41; // eax
  int v42; // eax
  __int64 v43; // r9

  v4 = *a2;
  if ( (unsigned int)*a2 > 6 )
  {
    v14 = v4 - 7;
    if ( v14 )
    {
      v15 = v14 - 1;
      if ( v15 )
      {
        v16 = v15 - 65529;
        if ( v16 )
        {
          v20 = v16 - 1;
          if ( v20 )
          {
            if ( v20 != 2 )
              goto LABEL_18;
            v8 = "GetKeyProtectionInterface";
          }
          else
          {
            v8 = "GetSChannelInterface";
          }
        }
        else
        {
          v8 = "GetKeyStorageInterface";
        }
      }
      else
      {
        v8 = "GetKeyEncapsulationInterface";
      }
    }
    else
    {
      v8 = "GetKeyDerivationInterface";
    }
LABEL_5:
    ProcAddress = GetProcAddress(a1, v8);
    if ( !ProcAddress )
    {
      v12 = -1073741511;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v9,
          v10,
          (unsigned int)"sResult",
          57,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c",
          115);
      return (unsigned int)v12;
    }
    v21 = *a2;
    if ( (unsigned int)*a2 <= 6 )
    {
      if ( v21 == 6 )
      {
        v12 = ((__int64 (__fastcall *)(_QWORD, _WORD **, __int64))ProcAddress)(*((_QWORD *)a2 + 2), a4, 1);
        if ( v12 < 0 )
        {
          v30 = 1546;
          goto LABEL_79;
        }
        goto LABEL_28;
      }
      v31 = v21 - 1;
      if ( !v31 )
      {
        v12 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _WORD **, __int64))ProcAddress)(
                *((_QWORD *)a2 + 2),
                *((_QWORD *)a2 + 1),
                a4,
                1);
        if ( v12 < 0 )
        {
          v30 = 1482;
          goto LABEL_79;
        }
        goto LABEL_28;
      }
      v32 = v31 - 1;
      if ( !v32 )
      {
        v12 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _WORD **, __int64))ProcAddress)(
                *((_QWORD *)a2 + 2),
                *((_QWORD *)a2 + 1),
                a4,
                1);
        if ( v12 < 0 )
        {
          v30 = 1495;
          goto LABEL_79;
        }
        goto LABEL_28;
      }
      v33 = v32 - 1;
      if ( !v33 )
      {
        v12 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _WORD **, __int64))ProcAddress)(
                *((_QWORD *)a2 + 2),
                *((_QWORD *)a2 + 1),
                a4,
                1);
        if ( v12 < 0 )
        {
          v30 = 1508;
          goto LABEL_79;
        }
        goto LABEL_28;
      }
      v34 = v33 - 1;
      if ( !v34 )
      {
        v12 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _WORD **, __int64))ProcAddress)(
                *((_QWORD *)a2 + 2),
                *((_QWORD *)a2 + 1),
                a4,
                1);
        if ( v12 < 0 )
        {
          v30 = 1521;
          goto LABEL_79;
        }
        goto LABEL_28;
      }
      if ( v34 == 1 )
      {
        v12 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _WORD **, __int64))ProcAddress)(
                *((_QWORD *)a2 + 2),
                *((_QWORD *)a2 + 1),
                a4,
                1);
        if ( v12 < 0 )
        {
          v30 = 1534;
          goto LABEL_79;
        }
LABEL_28:
        v24 = *a2;
        v25 = 0;
        if ( (unsigned int)*a2 <= 6 )
        {
          if ( v24 == 6 )
          {
            if ( !**a4 )
            {
              v40 = 1394;
LABEL_97:
              v25 = -1073741637;
              DebugTraceError(
                3221225659LL,
                "ntStatus",
                "onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c",
                v40);
            }
LABEL_32:
            v12 = v25;
            if ( v25 >= 0 )
              return (unsigned int)v12;
LABEL_33:
            DebugTraceError(
              (unsigned int)v25,
              "sResult",
              "onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c",
              1922);
            return (unsigned int)v12;
          }
          v36 = v24 - 1;
          if ( !v36 )
          {
            if ( **a4 )
              goto LABEL_32;
            v40 = 1344;
            goto LABEL_97;
          }
          v37 = v36 - 1;
          if ( !v37 )
          {
            if ( **a4 )
              goto LABEL_32;
            v40 = 1354;
            goto LABEL_97;
          }
          v38 = v37 - 1;
          if ( !v38 )
          {
            if ( **a4 )
              goto LABEL_32;
            v40 = 1364;
            goto LABEL_97;
          }
          v39 = v38 - 1;
          if ( !v39 )
          {
            if ( **a4 )
              goto LABEL_32;
            v40 = 1374;
            goto LABEL_97;
          }
          if ( v39 == 1 )
          {
            if ( **a4 )
              goto LABEL_32;
            v40 = 1384;
            goto LABEL_97;
          }
        }
        else
        {
          v26 = v24 - 7;
          if ( !v26 )
          {
            if ( **a4 )
              goto LABEL_32;
            v43 = 1404;
LABEL_106:
            v12 = -1073741637;
            v25 = -1073741637;
            DebugTraceError(3221225659LL, "ntStatus", "onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c", v43);
            goto LABEL_33;
          }
          v27 = v26 - 1;
          if ( !v27 )
          {
            if ( **a4 )
              goto LABEL_32;
            v40 = 1414;
            goto LABEL_97;
          }
          v41 = v27 - 65529;
          if ( !v41 )
          {
            if ( !**a4 )
            {
              v40 = 1424;
              goto LABEL_97;
            }
            goto LABEL_32;
          }
          v42 = v41 - 1;
          if ( !v42 )
          {
            if ( !**a4 )
            {
              v40 = 1444;
              goto LABEL_97;
            }
            goto LABEL_32;
          }
          if ( v42 == 2 )
          {
            if ( !**a4 )
            {
              v40 = 1434;
              goto LABEL_97;
            }
            goto LABEL_32;
          }
        }
        v43 = 1450;
        goto LABEL_106;
      }
    }
    else
    {
      v22 = v21 - 7;
      if ( !v22 )
      {
        v12 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _WORD **, __int64))ProcAddress)(
                *((_QWORD *)a2 + 2),
                *((_QWORD *)a2 + 1),
                a4,
                1);
        if ( v12 < 0 )
        {
          v30 = 1559;
          goto LABEL_79;
        }
        goto LABEL_28;
      }
      v23 = v22 - 1;
      if ( !v23 )
      {
        v12 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _WORD **, __int64))ProcAddress)(
                *((_QWORD *)a2 + 2),
                *((_QWORD *)a2 + 1),
                a4,
                1);
        if ( v12 >= 0 )
          goto LABEL_28;
        v30 = 1572;
        goto LABEL_79;
      }
      v28 = v23 - 65529;
      if ( !v28 )
      {
        v12 = ((__int64 (__fastcall *)(_QWORD, _WORD **, __int64))ProcAddress)(*((_QWORD *)a2 + 2), a4, 1);
        if ( v12 < 0 )
        {
          v30 = 1584;
          goto LABEL_79;
        }
        goto LABEL_28;
      }
      v29 = v28 - 1;
      if ( !v29 )
      {
        v12 = ((__int64 (__fastcall *)(_QWORD, _WORD **, __int64))ProcAddress)(*((_QWORD *)a2 + 2), a4, 1);
        if ( v12 < 0 )
        {
          v30 = 1608;
          goto LABEL_79;
        }
        goto LABEL_28;
      }
      if ( v29 == 2 )
      {
        v12 = ((__int64 (__fastcall *)(_QWORD, _WORD **, __int64))ProcAddress)(*((_QWORD *)a2 + 2), a4, 1);
        if ( v12 < 0 )
        {
          v30 = 1596;
LABEL_79:
          DebugTraceError(
            (unsigned int)v12,
            "ntStatus",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c",
            v30);
          goto LABEL_48;
        }
        goto LABEL_28;
      }
    }
    v12 = -1073741637;
    v35 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return (unsigned int)v12;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_49;
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v9,
      v10,
      (unsigned int)"ntStatus",
      187,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c",
      78);
LABEL_48:
    v35 = WPP_GLOBAL_Control;
LABEL_49:
    if ( v35 != &WPP_GLOBAL_Control && (*((_BYTE *)v35 + 28) & 1) != 0 )
      WPP_SF_sDsd(
        v35[2],
        v9,
        v10,
        (unsigned int)"sResult",
        v12,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c",
        135);
    return (unsigned int)v12;
  }
  if ( v4 == 6 )
  {
    v8 = "GetRngInterface";
    goto LABEL_5;
  }
  v7 = v4 - 1;
  if ( !v7 )
  {
    v8 = "GetCipherInterface";
    goto LABEL_5;
  }
  v17 = v7 - 1;
  if ( !v17 )
  {
    v8 = "GetHashInterface";
    goto LABEL_5;
  }
  v18 = v17 - 1;
  if ( !v18 )
  {
    v8 = "GetAsymmetricEncryptionInterface";
    goto LABEL_5;
  }
  v19 = v18 - 1;
  if ( !v19 )
  {
    v8 = "GetSecretAgreementInterface";
    goto LABEL_5;
  }
  if ( v19 == 1 )
  {
    v8 = "GetSignatureInterface";
    goto LABEL_5;
  }
LABEL_18:
  v12 = -1073741637;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)a2,
      a3,
      (unsigned int)"sResult",
      187,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c",
      104);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180004e34  push    rbx
0x180004e36  push    rbp
0x180004e37  push    rsi
0x180004e38  push    rdi
0x180004e39  push    r14
0x180004e3b  push    r15
0x180004e3d  sub     rsp, 48h
0x180004e41  mov     eax, [rdx]
0x180004e43  mov     r14, r9
0x180004e46  mov     r15, rdx
0x180004e49  cmp     eax, 6
0x180004e4c  ja      loc_180004ED6
0x180004e52  jz      loc_18000512E
0x180004e58  sub     eax, 1
0x180004e5b  jnz     loc_180004EFB
0x180004e61  lea     rdx, ProcName; "GetCipherInterface"
0x180004e68  call    cs:__imp_GetProcAddress
0x180004e6e  mov     r10, rax
0x180004e71  test    rax, rax
0x180004e74  jnz     loc_180004F7D
0x180004e7a  mov     ebx, 0C0000139h
0x180004e7f  mov     rcx, cs:WPP_GLOBAL_Control
0x180004e86  lea     rbp, WPP_GLOBAL_Control
0x180004e8d  cmp     rcx, rbp
0x180004e90  jz      short loc_180004EC7
0x180004e92  lea     esi, [rax+1]
0x180004e95  test    [rcx+1Ch], sil
0x180004e99  jz      short loc_180004EC7
0x180004e9b  mov     [rsp+78h+var_48], 773h
0x180004ea3  lea     rdi, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180004eaa  mov     [rsp+78h+var_50], rdi
0x180004eaf  mov     [rsp+78h+var_58], 0C0000139h
0x180004eb7  mov     rcx, [rcx+10h]
0x180004ebb  lea     r9, aSresult; "sResult"
0x180004ec2  call    WPP_SF_sDsd
0x180004ec7  mov     eax, ebx
0x180004ec9  add     rsp, 48h
0x180004ecd  pop     r15
0x180004ecf  pop     r14
0x180004ed1  pop     rdi
0x180004ed2  pop     rsi
0x180004ed3  pop     rbp
0x180004ed4  pop     rbx
0x180004ed5  retn
0x180004ed6  sub     eax, 7
0x180004ed9  jz      loc_180005152
0x180004edf  sub     eax, 1
0x180004ee2  jz      loc_180005146
0x180004ee8  sub     eax, 0FFF9h
0x180004eed  jnz     short loc_180004F63
0x180004eef  lea     rdx, aGetkeystoragei; "GetKeyStorageInterface"
0x180004ef6  jmp     loc_180004E68
0x180004efb  sub     eax, 1
0x180004efe  jz      loc_180005122
0x180004f04  sub     eax, 1
0x180004f07  jz      loc_180005116
0x180004f0d  sub     eax, 1
0x180004f10  jz      loc_18000510A
0x180004f16  cmp     eax, 1
0x180004f19  jz      loc_1800050FE
0x180004f1f  mov     ebx, 0C00000BBh
0x180004f24  mov     rcx, cs:WPP_GLOBAL_Control
0x180004f2b  lea     rbp, WPP_GLOBAL_Control
0x180004f32  cmp     rcx, rbp
0x180004f35  jz      short loc_180004EC7
0x180004f37  mov     esi, 1
0x180004f3c  test    [rcx+1Ch], sil
0x180004f40  jz      short loc_180004EC7
0x180004f42  mov     [rsp+78h+var_48], 768h
0x180004f4a  lea     rdi, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180004f51  mov     [rsp+78h+var_50], rdi
0x180004f56  mov     [rsp+78h+var_58], 0C00000BBh
0x180004f5e  jmp     loc_180004EB7
0x180004f63  sub     eax, 1
0x180004f66  jz      loc_18000513A
0x180004f6c  cmp     eax, 2
0x180004f6f  jnz     short loc_180004F1F
0x180004f71  lea     rdx, aGetkeyprotecti; "GetKeyProtectionInterface"
0x180004f78  jmp     loc_180004E68
0x180004f7d  mov     eax, [r15]
0x180004f80  lea     rdi, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180004f87  lea     rbp, WPP_GLOBAL_Control
0x180004f8e  mov     esi, 1
0x180004f93  cmp     eax, 6
0x180004f96  jbe     loc_180005060
0x180004f9c  sub     eax, 7
0x180004f9f  jz      loc_1800052A9
0x180004fa5  sub     eax, esi
0x180004fa7  jnz     short loc_180005021
0x180004fa9  mov     rdx, [r15+8]
0x180004fad  mov     r9d, esi
0x180004fb0  mov     rcx, [r15+10h]
0x180004fb4  mov     r8, r14
0x180004fb7  mov     rax, r10
0x180004fba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fbf  mov     ebx, eax
0x180004fc1  test    eax, eax
0x180004fc3  js      loc_1800052A1
0x180004fc9  mov     eax, [r15]
0x180004fcc  lea     rdi, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180004fd3  xor     ebp, ebp
0x180004fd5  cmp     eax, 6
0x180004fd8  jbe     loc_1800052E5
0x180004fde  sub     eax, 7
0x180004fe1  jz      loc_18000541F
0x180004fe7  sub     eax, esi
0x180004fe9  jnz     loc_18000539F
0x180004fef  mov     rax, [r14]
0x180004ff2  cmp     si, [rax]
0x180004ff5  ja      loc_180005367
0x180004ffb  mov     ebx, ebp
0x180004ffd  test    ebp, ebp
0x180004fff  jns     loc_180004EC7
0x180005005  mov     r9d, 782h
0x18000500b  lea     rdx, aSresult; "sResult"
0x180005012  mov     r8, rdi
0x180005015  mov     ecx, ebp
0x180005017  call    DebugTraceError
0x18000501c  jmp     loc_180004EC7
0x180005021  sub     eax, 0FFF9h
0x180005026  jz      loc_18000527D
0x18000502c  sub     eax, esi
0x18000502e  jz      loc_180005259
0x180005034  cmp     eax, 2
0x180005037  jnz     short loc_18000508E
0x180005039  mov     rcx, [r15+10h]
0x18000503d  mov     r8d, esi
0x180005040  mov     rdx, r14
0x180005043  mov     rax, r10
0x180005046  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000504b  mov     ebx, eax
0x18000504d  test    eax, eax
0x18000504f  jns     loc_180004FC9
0x180005055  mov     r9d, 63Ch
0x18000505b  jmp     loc_1800052CF
0x180005060  jz      loc_180005235
0x180005066  sub     eax, esi
0x180005068  jz      loc_18000520A
0x18000506e  sub     eax, esi
0x180005070  jz      loc_1800051DF
0x180005076  sub     eax, esi
0x180005078  jz      loc_1800051B4
0x18000507e  sub     eax, esi
0x180005080  jz      loc_180005189
0x180005086  cmp     eax, esi
0x180005088  jz      loc_18000515E
0x18000508e  mov     ebx, 0C00000BBh
0x180005093  mov     rcx, cs:WPP_GLOBAL_Control
0x18000509a  cmp     rcx, rbp
0x18000509d  jz      loc_180004EC7
0x1800050a3  test    [rcx+1Ch], sil
0x1800050a7  jz      short loc_1800050D5
0x1800050a9  mov     rcx, [rcx+10h]
0x1800050ad  lea     r9, aNtstatus; "ntStatus"
0x1800050b4  mov     [rsp+78h+var_48], 64Eh
0x1800050bc  mov     [rsp+78h+var_50], rdi
0x1800050c1  mov     [rsp+78h+var_58], 0C00000BBh
0x1800050c9  call    WPP_SF_sDsd
0x1800050ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800050d5  cmp     rcx, rbp
0x1800050d8  jz      loc_180004EC7
0x1800050de  test    [rcx+1Ch], sil
0x1800050e2  jz      loc_180004EC7
0x1800050e8  mov     [rsp+78h+var_48], 787h
0x1800050f0  mov     [rsp+78h+var_50], rdi
0x1800050f5  mov     [rsp+78h+var_58], ebx
0x1800050f9  jmp     loc_180004EB7
0x1800050fe  lea     rdx, aGetsignaturein; "GetSignatureInterface"
0x180005105  jmp     loc_180004E68
0x18000510a  lea     rdx, aGetsecretagree; "GetSecretAgreementInterface"
0x180005111  jmp     loc_180004E68
0x180005116  lea     rdx, aGetasymmetrice; "GetAsymmetricEncryptionInterface"
0x18000511d  jmp     loc_180004E68
0x180005122  lea     rdx, aGethashinterfa; "GetHashInterface"
0x180005129  jmp     loc_180004E68
0x18000512e  lea     rdx, aGetrnginterfac; "GetRngInterface"
0x180005135  jmp     loc_180004E68
0x18000513a  lea     rdx, aGetschannelint; "GetSChannelInterface"
0x180005141  jmp     loc_180004E68
0x180005146  lea     rdx, aGetkeyencapsul; "GetKeyEncapsulationInterface"
0x18000514d  jmp     loc_180004E68
0x180005152  lea     rdx, aGetkeyderivati; "GetKeyDerivationInterface"
0x180005159  jmp     loc_180004E68
0x18000515e  mov     rdx, [r15+8]
0x180005162  mov     r9d, esi
0x180005165  mov     rcx, [r15+10h]
0x180005169  mov     r8, r14
0x18000516c  mov     rax, r10
0x18000516f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005174  mov     ebx, eax
0x180005176  test    eax, eax
0x180005178  jns     loc_180004FC9
0x18000517e  mov     r9d, 5FEh
0x180005184  jmp     loc_1800052CF
0x180005189  mov     rdx, [r15+8]
0x18000518d  mov     r9d, esi
0x180005190  mov     rcx, [r15+10h]
0x180005194  mov     r8, r14
0x180005197  mov     rax, r10
0x18000519a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000519f  mov     ebx, eax
0x1800051a1  test    eax, eax
0x1800051a3  jns     loc_180004FC9
0x1800051a9  mov     r9d, 5F1h
0x1800051af  jmp     loc_1800052CF
0x1800051b4  mov     rdx, [r15+8]
0x1800051b8  mov     r9d, esi
0x1800051bb  mov     rcx, [r15+10h]
0x1800051bf  mov     r8, r14
0x1800051c2  mov     rax, r10
0x1800051c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051ca  mov     ebx, eax
0x1800051cc  test    eax, eax
0x1800051ce  jns     loc_180004FC9
0x1800051d4  mov     r9d, 5E4h
0x1800051da  jmp     loc_1800052CF
0x1800051df  mov     rdx, [r15+8]
0x1800051e3  mov     r9d, esi
0x1800051e6  mov     rcx, [r15+10h]
0x1800051ea  mov     r8, r14
0x1800051ed  mov     rax, r10
0x1800051f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051f5  mov     ebx, eax
0x1800051f7  test    eax, eax
0x1800051f9  jns     loc_180004FC9
0x1800051ff  mov     r9d, 5D7h
0x180005205  jmp     loc_1800052CF
0x18000520a  mov     rdx, [r15+8]
0x18000520e  mov     r9d, esi
0x180005211  mov     rcx, [r15+10h]
0x180005215  mov     r8, r14
0x180005218  mov     rax, r10
0x18000521b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005220  mov     ebx, eax
0x180005222  test    eax, eax
0x180005224  jns     loc_180004FC9
0x18000522a  mov     r9d, 5CAh
0x180005230  jmp     loc_1800052CF
0x180005235  mov     rcx, [r15+10h]
0x180005239  mov     r8d, esi
0x18000523c  mov     rdx, r14
0x18000523f  mov     rax, r10
0x180005242  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005247  mov     ebx, eax
0x180005249  test    eax, eax
0x18000524b  jns     loc_180004FC9
0x180005251  mov     r9d, 60Ah
0x180005257  jmp     short loc_1800052CF
0x180005259  mov     rcx, [r15+10h]
0x18000525d  mov     r8d, esi
0x180005260  mov     rdx, r14
0x180005263  mov     rax, r10
0x180005266  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000526b  mov     ebx, eax
0x18000526d  test    eax, eax
0x18000526f  jns     loc_180004FC9
0x180005275  mov     r9d, 648h
0x18000527b  jmp     short loc_1800052CF
0x18000527d  mov     rcx, [r15+10h]
0x180005281  mov     r8d, esi
0x180005284  mov     rdx, r14
0x180005287  mov     rax, r10
0x18000528a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000528f  mov     ebx, eax
0x180005291  test    eax, eax
0x180005293  jns     loc_180004FC9
0x180005299  mov     r9d, 630h
0x18000529f  jmp     short loc_1800052CF
0x1800052a1  mov     r9d, 624h
0x1800052a7  jmp     short loc_1800052CF
0x1800052a9  mov     rdx, [r15+8]
0x1800052ad  mov     r9d, esi
0x1800052b0  mov     rcx, [r15+10h]
0x1800052b4  mov     r8, r14
0x1800052b7  mov     rax, r10
0x1800052ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052bf  mov     ebx, eax
0x1800052c1  test    eax, eax
0x1800052c3  jns     loc_180004FC9
0x1800052c9  mov     r9d, 617h
0x1800052cf  lea     rdx, aNtstatus; "ntStatus"
0x1800052d6  mov     r8, rdi
0x1800052d9  mov     ecx, ebx
0x1800052db  call    DebugTraceError
0x1800052e0  jmp     loc_1800050CE
0x1800052e5  jz      loc_18000538B
0x1800052eb  sub     eax, esi
0x1800052ed  jz      short loc_180005353
0x1800052ef  sub     eax, esi
0x1800052f1  jz      short loc_18000533F
0x1800052f3  sub     eax, esi
0x1800052f5  jz      short loc_18000532B
0x1800052f7  sub     eax, esi
0x1800052f9  jz      short loc_180005317
0x1800052fb  cmp     eax, esi
0x1800052fd  jnz     loc_1800053C3
0x180005303  mov     rax, [r14]
0x180005306  cmp     si, [rax]
0x180005309  jbe     loc_180004FFB
0x18000530f  mov     r9d, 568h
  ... truncated ...
```
