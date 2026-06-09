# NgscbpCheckDmaSecurityForHardware

- ea: `0x180008320`
- end: `0x180008b8e`
- name: `NgscbpCheckDmaSecurityForHardware`
- size: `2158`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18002c9c4`

## callees

- `0x180006a08`
- `0x180008320`
- `0x180008d70`
- `0x1800090c0`
- `0x180009130`
- `0x180036fbc`
- `0x180037db0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800089e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008a40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008aa0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800089e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008a40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008aa0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b00`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800084af`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800085f6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800087f4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000882c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800084af`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800085f6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800087f4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000882c`

## pseudocode

```c
__int64 __fastcall NgscbpCheckDmaSecurityForHardware(
        _WORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _BYTE *a5,
        __int64 **a6,
        __int64 a7)
{
  PVOID *v10; // rcx
  _WORD *i; // rbx
  __int64 v12; // rax
  bool v13; // zf
  char v14; // bp
  char v15; // r15
  __int64 *v16; // r12
  __int64 *v17; // r13
  const WCHAR *v18; // rsi
  int v19; // eax
  __int64 v20; // rax
  __int64 *v22; // rdi
  const WCHAR *k; // rbx
  int v24; // eax
  __int64 v25; // rax
  unsigned int v26; // eax
  int v27; // ebx
  unsigned int v28; // eax
  __int64 *j; // rbx
  int v30; // eax
  int v31; // eax
  signed int v32; // eax
  signed int v33; // eax
  signed int v34; // eax
  signed int LastError; // eax
  _BYTE v36[4]; // [rsp+30h] [rbp-48h] BYREF
  unsigned int v37; // [rsp+34h] [rbp-44h]

  v36[0] = 0;
  if ( a5 )
  {
    v37 = 0;
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 236, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids);
        v10 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 8) != 0 )
      {
        WPP_SF_(v10[2], 237, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids);
        v10 = (PVOID *)WPP_GLOBAL_Control;
      }
    }
    for ( i = a1; *i; i += v12 + 1 )
    {
      if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 8) != 0 )
      {
        WPP_SF_S(v10[2], 238, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, i);
        v10 = (PVOID *)WPP_GLOBAL_Control;
      }
      v12 = -1;
      do
        v13 = i[++v12] == 0;
      while ( !v13 );
    }
    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 8) != 0 )
    {
      WPP_SF_(v10[2], 239, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids);
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( a2 )
    {
      v14 = 0;
      v15 = 0;
      if ( !a4 && v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 8) != 0 )
      {
        WPP_SF_(v10[2], 241, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids);
        v10 = (PVOID *)WPP_GLOBAL_Control;
      }
      v16 = *(__int64 **)(a2 + 8);
      v17 = (__int64 *)(a2 + 8);
      while ( v16 != v17 && !v14 )
      {
        if ( v15 )
          goto LABEL_38;
        if ( !*((_DWORD *)v16 + 9) )
        {
          v18 = a1;
          v10 = (PVOID *)WPP_GLOBAL_Control;
          while ( 2 )
          {
            if ( !*v18 || v14 || v15 )
              goto LABEL_34;
            v19 = CompareStringOrdinal(v18, -1, (LPCWCH)v16[3], -1, 1);
            if ( !v19 )
            {
              LastError = GetLastError();
              v37 = LastError;
              if ( LastError > 0 )
                v37 = (unsigned __int16)LastError | 0x80070000;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  243,
                  &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids,
                  v37);
              return v37;
            }
            if ( v19 == 2 )
            {
              v10 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              {
                WPP_SF_SSS(*((_QWORD *)WPP_GLOBAL_Control + 2), v16[2], v16[3]);
                v10 = (PVOID *)WPP_GLOBAL_Control;
              }
              if ( a4 )
              {
                v22 = *(__int64 **)(a4 + 8);
LABEL_46:
                if ( v22 == (__int64 *)(a4 + 8) )
                {
                  if ( !v14 )
                  {
                    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 8) != 0 )
                    {
                      WPP_SF_S(v10[2], 247, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, v18);
                      v10 = (PVOID *)WPP_GLOBAL_Control;
                    }
                    if ( a7 )
                    {
                      LOBYTE(v10) = 1;
                      v26 = NgscbpCheckDmaSecurityHSTIException(v10, v16[2], a7, v36);
                      v37 = v26;
                      v27 = v26;
                      if ( v26 )
                      {
                        v10 = (PVOID *)WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
                        {
                          WPP_SF_d(
                            *((_QWORD *)WPP_GLOBAL_Control + 2),
                            248,
                            &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids,
                            v26);
                          v10 = (PVOID *)WPP_GLOBAL_Control;
                        }
                        if ( v27 < 0 )
                          return v37;
                      }
                      else
                      {
                        v10 = (PVOID *)WPP_GLOBAL_Control;
                      }
                      if ( v36[0] )
                        goto LABEL_72;
                      v28 = NgscbpCheckDmaSecurityHSTIException(0, v16[2], a7, v36);
                      v37 = v28;
                      if ( v28 )
                      {
                        v10 = (PVOID *)WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
                        {
                          WPP_SF_d(
                            *((_QWORD *)WPP_GLOBAL_Control + 2),
                            249,
                            &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids,
                            v28);
                          v10 = (PVOID *)WPP_GLOBAL_Control;
                        }
                        if ( (v37 & 0x80000000) != 0 )
                          return v37;
                      }
                      else
                      {
                        v10 = (PVOID *)WPP_GLOBAL_Control;
                      }
                      if ( v36[0] )
                      {
LABEL_72:
                        if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 8) != 0 )
                          WPP_SF_SSS((TRACEHANDLE)v10[2], v16[2], v16[3]);
                        *((_DWORD *)v16 + 9) = 1;
                        goto LABEL_106;
                      }
                    }
                    else
                    {
                      v36[0] = 0;
                    }
                    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 8) != 0 )
                      WPP_SF_S(v10[2], 251, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, v18);
                    v13 = (*((_DWORD *)v16 + 8))++ == -1;
                    v15 = 1;
                    if ( v13 )
                      *((_DWORD *)v16 + 8) = 1;
                    if ( a3 && a6 )
                    {
                      for ( j = *(__int64 **)(a3 + 8); j != (__int64 *)(a3 + 8); j = (__int64 *)*j )
                      {
                        v30 = CompareStringOrdinal((LPCWCH)v16[3], -1, (LPCWCH)j[3], -1, 0);
                        if ( !v30 )
                        {
                          v34 = GetLastError();
                          v37 = v34;
                          if ( v34 > 0 )
                            v37 = (unsigned __int16)v34 | 0x80070000;
                          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
                          {
                            WPP_SF_d(
                              *((_QWORD *)WPP_GLOBAL_Control + 2),
                              252,
                              &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids,
                              v37);
                          }
                          return v37;
                        }
                        if ( v30 == 2 )
                        {
                          v31 = CompareStringOrdinal((LPCWCH)v16[2], -1, (LPCWCH)j[2], -1, 0);
                          if ( !v31 )
                          {
                            v33 = GetLastError();
                            v37 = v33;
                            if ( v33 > 0 )
                              v37 = (unsigned __int16)v33 | 0x80070000;
                            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
                            {
                              WPP_SF_d(
                                *((_QWORD *)WPP_GLOBAL_Control + 2),
                                253,
                                &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids,
                                v37);
                            }
                            return v37;
                          }
                          if ( v31 == 2 )
                          {
                            v13 = (*((_DWORD *)j + 8))++ == -1;
                            if ( v13 )
                              *((_DWORD *)j + 8) = 1;
                            *a6 = j;
                            goto LABEL_29;
                          }
                        }
                      }
                    }
                    goto LABEL_29;
                  }
                }
                else if ( !v14 )
                {
                  for ( k = a1; ; k += v25 + 1 )
                  {
                    if ( !*k )
                    {
                      v10 = (PVOID *)WPP_GLOBAL_Control;
                      v22 = (__int64 *)*v22;
                      goto LABEL_46;
                    }
                    v24 = CompareStringOrdinal(k, -1, (LPCWCH)v22[3], -1, 1);
                    if ( !v24 )
                      break;
                    if ( v24 == 2 )
                    {
                      v10 = (PVOID *)WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                      {
                        WPP_SF_SSS(*((_QWORD *)WPP_GLOBAL_Control + 2), v22[2], v22[3]);
                        v10 = (PVOID *)WPP_GLOBAL_Control;
                      }
                      v22 = (__int64 *)*v22;
                      v14 = 1;
                      goto LABEL_46;
                    }
                    v25 = -1;
                    do
                      v13 = k[++v25] == 0;
                    while ( !v13 );
                  }
                  v32 = GetLastError();
                  v37 = v32;
                  if ( v32 > 0 )
                    v37 = (unsigned __int16)v32 | 0x80070000;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      245,
                      &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids,
                      v37);
                  return v37;
                }
              }
            }
            else
            {
LABEL_29:
              v10 = (PVOID *)WPP_GLOBAL_Control;
            }
            v20 = -1;
            do
              v13 = v18[++v20] == 0;
            while ( !v13 );
            v18 += v20 + 1;
            continue;
          }
        }
        if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 8) != 0 )
        {
          WPP_SF_SS(
            (unsigned int)v10[2],
            242,
            (unsigned int)&WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids,
            v16[2],
            v16[3]);
LABEL_106:
          v10 = (PVOID *)WPP_GLOBAL_Control;
        }
LABEL_34:
        v16 = (__int64 *)*v16;
      }
      if ( v15 )
LABEL_38:
        *a5 = 0;
    }
    else if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 8) != 0 )
    {
      WPP_SF_(v10[2], 240, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids);
    }
    return v37;
  }
  v37 = -2147467261;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
    return v37;
  WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 235, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, 2147500035LL);
  return v37;
}

```

## disassembly

```asm
0x180008320  mov     rax, rsp
0x180008323  mov     [rax+20h], r9
0x180008327  mov     [rax+18h], r8
0x18000832b  mov     [rax+8], rcx
0x18000832f  push    rsi
0x180008330  push    rdi
0x180008331  push    r13
0x180008333  sub     rsp, 60h
0x180008337  cmp     [rsp+78h+arg_20], 0
0x180008340  mov     r13, r9
0x180008343  mov     rdi, rdx
0x180008346  mov     byte ptr [rax-48h], 0
0x18000834a  mov     rsi, rcx
0x18000834d  jz      loc_18000891F
0x180008353  mov     [rax+10h], rbx
0x180008357  mov     [rax-30h], r14
0x18000835b  mov     [rsp+78h+var_44], 0
0x180008363  mov     rcx, cs:WPP_GLOBAL_Control
0x18000836a  lea     r14, WPP_GLOBAL_Control
0x180008371  cmp     rcx, r14
0x180008374  jz      short loc_1800083BF
0x180008376  test    byte ptr [rcx+1Ch], 8
0x18000837a  jz      short loc_180008398
0x18000837c  mov     rcx, [rcx+10h]
0x180008380  lea     r8, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids
0x180008387  mov     edx, 0ECh
0x18000838c  call    WPP_SF_
0x180008391  mov     rcx, cs:WPP_GLOBAL_Control
0x180008398  cmp     rcx, r14
0x18000839b  jz      short loc_1800083BF
0x18000839d  test    byte ptr [rcx+1Ch], 8
0x1800083a1  jz      short loc_1800083BF
0x1800083a3  mov     rcx, [rcx+10h]
0x1800083a7  lea     r8, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids
0x1800083ae  mov     edx, 0EDh
0x1800083b3  call    WPP_SF_
0x1800083b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800083bf  cmp     word ptr [rsi], 0
0x1800083c3  mov     rbx, rsi
0x1800083c6  jz      short loc_1800083FA
0x1800083c8  nop     dword ptr [rax+rax+00000000h]
0x1800083d0  cmp     rcx, r14
0x1800083d3  jnz     loc_18000850F
0x1800083d9  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800083e0  cmp     word ptr [rbx+rax*2+2], 0
0x1800083e6  lea     rax, [rax+1]
0x1800083ea  jnz     short loc_1800083E0
0x1800083ec  lea     rbx, [rbx+rax*2]
0x1800083f0  add     rbx, 2
0x1800083f4  cmp     word ptr [rbx], 0
0x1800083f8  jnz     short loc_1800083D0
0x1800083fa  cmp     rcx, r14
0x1800083fd  jz      short loc_180008421
0x1800083ff  test    byte ptr [rcx+1Ch], 8
0x180008403  jz      short loc_180008421
0x180008405  mov     rcx, [rcx+10h]
0x180008409  lea     r8, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids
0x180008410  mov     edx, 0EFh
0x180008415  call    WPP_SF_
0x18000841a  mov     rcx, cs:WPP_GLOBAL_Control
0x180008421  test    rdi, rdi
0x180008424  jz      loc_180008577
0x18000842a  mov     [rsp+78h+var_20], rbp
0x18000842f  xor     bpl, bpl
0x180008432  mov     [rsp+78h+var_28], r12
0x180008437  mov     [rsp+78h+var_38], r15
0x18000843c  xor     r15b, r15b
0x18000843f  test    r13, r13
0x180008442  jz      loc_180008B5A
0x180008448  mov     r12, [rdi+8]
0x18000844c  lea     r13, [rdi+8]
0x180008450  cmp     r12, r13
0x180008453  jz      loc_18000853D
0x180008459  test    bpl, bpl
0x18000845c  jnz     loc_18000853D
0x180008462  test    r15b, r15b
0x180008465  jnz     loc_180008542
0x18000846b  cmp     dword ptr [r12+24h], 0
0x180008471  jnz     loc_1800084FD
0x180008477  mov     rsi, [rsp+78h+lpString1]
0x18000847f  mov     rcx, cs:WPP_GLOBAL_Control
0x180008486  cmp     word ptr [rsi], 0
0x18000848a  jz      short loc_180008506
0x18000848c  test    bpl, bpl
0x18000848f  jnz     short loc_180008506
0x180008491  test    r15b, r15b
0x180008494  jnz     short loc_180008506
0x180008496  mov     r8, [r12+18h]; lpString2
0x18000849b  mov     r9d, 0FFFFFFFFh; cchCount2
0x1800084a1  mov     edx, r9d; cchCount1
0x1800084a4  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x1800084ac  mov     rcx, rsi; lpString1
0x1800084af  call    cs:__imp_CompareStringOrdinal
0x1800084b6  nop     dword ptr [rax+rax+00h]
0x1800084bb  test    eax, eax
0x1800084bd  jz      loc_180008B00
0x1800084c3  cmp     eax, 2
0x1800084c6  jz      loc_180008599
0x1800084cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800084d3  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800084da  nop     word ptr [rax+rax+00h]
0x1800084e0  cmp     word ptr [rsi+rax*2+2], 0
0x1800084e6  lea     rax, [rax+1]
0x1800084ea  jnz     short loc_1800084E0
0x1800084ec  lea     rsi, [rsi+rax*2]
0x1800084f0  add     rsi, 2
0x1800084f4  lea     r14, WPP_GLOBAL_Control
0x1800084fb  jmp     short loc_180008486
0x1800084fd  cmp     rcx, r14
0x180008500  jnz     loc_18000898E
0x180008506  mov     r12, [r12]
0x18000850a  jmp     loc_180008450
0x18000850f  test    byte ptr [rcx+1Ch], 8
0x180008513  jz      loc_1800083D9
0x180008519  mov     rcx, [rcx+10h]
0x18000851d  lea     r8, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids
0x180008524  mov     edx, 0EEh
0x180008529  mov     r9, rbx
0x18000852c  call    WPP_SF_S
0x180008531  mov     rcx, cs:WPP_GLOBAL_Control
0x180008538  jmp     loc_1800083D9
0x18000853d  test    r15b, r15b
0x180008540  jz      short loc_18000854D
0x180008542  mov     rax, [rsp+78h+arg_20]
0x18000854a  mov     byte ptr [rax], 0
0x18000854d  mov     rbp, [rsp+78h+var_20]
0x180008552  mov     r12, [rsp+78h+var_28]
0x180008557  mov     r15, [rsp+78h+var_38]
0x18000855c  mov     rbx, [rsp+78h+arg_8]
0x180008564  mov     r14, [rsp+78h+var_30]
0x180008569  mov     eax, [rsp+78h+var_44]
0x18000856d  add     rsp, 60h
0x180008571  pop     r13
0x180008573  pop     rdi
0x180008574  pop     rsi
0x180008575  retn
0x180008577  cmp     rcx, r14
0x18000857a  jz      short loc_18000855C
0x18000857c  test    byte ptr [rcx+1Ch], 8
0x180008580  jz      short loc_18000855C
0x180008582  mov     rcx, [rcx+10h]
0x180008586  lea     r8, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids
0x18000858d  mov     edx, 0F0h
0x180008592  call    WPP_SF_
0x180008597  jmp     short loc_18000855C
0x180008599  mov     rcx, cs:WPP_GLOBAL_Control
0x1800085a0  cmp     rcx, r14
0x1800085a3  jnz     loc_180008888
0x1800085a9  mov     rax, [rsp+78h+arg_18]
0x1800085b1  test    rax, rax
0x1800085b4  jz      loc_1800084D3
0x1800085ba  mov     rdi, [rax+8]
0x1800085be  lea     r14, [rax+8]
0x1800085c2  cmp     rdi, r14
0x1800085c5  jz      short loc_180008642
0x1800085c7  test    bpl, bpl
0x1800085ca  jnz     loc_1800084D3
0x1800085d0  mov     rbx, [rsp+78h+lpString1]
0x1800085d8  cmp     word ptr [rbx], 0
0x1800085dc  jz      short loc_180008636
0x1800085de  mov     r8, [rdi+18h]; lpString2
0x1800085e2  mov     r9d, 0FFFFFFFFh; cchCount2
0x1800085e8  mov     edx, r9d; cchCount1
0x1800085eb  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x1800085f3  mov     rcx, rbx; lpString1
0x1800085f6  call    cs:__imp_CompareStringOrdinal
0x1800085fd  nop     dword ptr [rax+rax+00h]
0x180008602  test    eax, eax
0x180008604  jz      loc_1800089E0
0x18000860a  cmp     eax, 2
0x18000860d  jz      loc_1800088CA
0x180008613  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000861a  nop     word ptr [rax+rax+00h]
0x180008620  cmp     word ptr [rbx+rax*2+2], 0
0x180008626  lea     rax, [rax+1]
0x18000862a  jnz     short loc_180008620
0x18000862c  lea     rbx, [rbx+rax*2]
0x180008630  add     rbx, 2
0x180008634  jmp     short loc_1800085D8
0x180008636  mov     rcx, cs:WPP_GLOBAL_Control
0x18000863d  mov     rdi, [rdi]
0x180008640  jmp     short loc_1800085C2
0x180008642  test    bpl, bpl
0x180008645  jnz     loc_1800084D3
0x18000864b  lea     r14, WPP_GLOBAL_Control
0x180008652  cmp     rcx, r14
0x180008655  jnz     loc_18000885A
0x18000865b  cmp     [rsp+78h+arg_30], 0
0x180008664  jz      loc_18000877F
0x18000866a  mov     r8, [rsp+78h+arg_30]
0x180008672  lea     r9, [rsp+78h+var_48]
0x180008677  mov     rdx, [r12+10h]
0x18000867c  mov     cl, 1
0x18000867e  call    NgscbpCheckDmaSecurityHSTIException
0x180008683  mov     [rsp+78h+var_44], eax
0x180008687  mov     ebx, eax
0x180008689  test    eax, eax
0x18000868b  jz      loc_1800089C8
0x180008691  mov     rcx, cs:WPP_GLOBAL_Control
0x180008698  cmp     rcx, r14
0x18000869b  jz      short loc_1800086C2
0x18000869d  test    byte ptr [rcx+1Ch], 40h
0x1800086a1  jz      short loc_1800086C2
0x1800086a3  mov     rcx, [rcx+10h]
0x1800086a7  lea     r8, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids
0x1800086ae  mov     edx, 0F8h
0x1800086b3  mov     r9d, eax
0x1800086b6  call    WPP_SF_d
0x1800086bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800086c2  test    ebx, ebx
0x1800086c4  js      loc_18000854D
0x1800086ca  cmp     [rsp+78h+var_48], 0
0x1800086cf  jnz     short loc_18000873A
0x1800086d1  mov     r8, [rsp+78h+arg_30]
0x1800086d9  lea     r9, [rsp+78h+var_48]
0x1800086de  mov     rdx, [r12+10h]
0x1800086e3  xor     ecx, ecx
0x1800086e5  call    NgscbpCheckDmaSecurityHSTIException
0x1800086ea  mov     [rsp+78h+var_44], eax
0x1800086ee  test    eax, eax
0x1800086f0  jz      loc_1800089D4
0x1800086f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800086fd  cmp     rcx, r14
0x180008700  jz      short loc_180008727
0x180008702  test    byte ptr [rcx+1Ch], 40h
0x180008706  jz      short loc_180008727
0x180008708  mov     rcx, [rcx+10h]
0x18000870c  lea     r8, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids
0x180008713  mov     edx, 0F9h
0x180008718  mov     r9d, eax
0x18000871b  call    WPP_SF_d
0x180008720  mov     rcx, cs:WPP_GLOBAL_Control
0x180008727  mov     ebx, [rsp+78h+var_44]
0x18000872b  test    ebx, ebx
0x18000872d  js      loc_18000854D
0x180008733  cmp     [rsp+78h+var_48], 0
0x180008738  jz      short loc_180008784
0x18000873a  cmp     rcx, r14
0x18000873d  jz      short loc_180008771
0x18000873f  test    byte ptr [rcx+1Ch], 8
0x180008743  jz      short loc_180008771
0x180008745  mov     rax, [r12+18h]
0x18000874a  lea     r8, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids
0x180008751  mov     rcx, [rcx+10h]; LoggerHandle
0x180008755  mov     edx, 0FAh
0x18000875a  mov     [rsp+78h+var_50], rax; __int64
0x18000875f  mov     r9, rsi
0x180008762  mov     rax, [r12+10h]
0x180008767  mov     qword ptr [rsp+78h+bIgnoreCase], rax; __int64
0x18000876c  call    WPP_SF_SSS
0x180008771  mov     dword ptr [r12+24h], 1
0x18000877a  jmp     loc_1800089BC
0x18000877f  mov     [rsp+78h+var_48], 0
0x180008784  cmp     rcx, r14
0x180008787  jz      short loc_180008793
0x180008789  test    byte ptr [rcx+1Ch], 8
0x18000878d  jnz     loc_180008971
0x180008793  add     dword ptr [r12+20h], 1
0x180008799  mov     r15b, 1
0x18000879c  jnz     short loc_1800087A7
0x18000879e  mov     dword ptr [r12+20h], 1
0x1800087a7  mov     rax, [rsp+78h+arg_10]
0x1800087af  test    rax, rax
0x1800087b2  jz      loc_1800084CC
0x1800087b8  mov     r14, [rsp+78h+arg_28]
0x1800087c0  test    r14, r14
0x1800087c3  jz      loc_1800084CC
0x1800087c9  mov     rbx, [rax+8]
0x1800087cd  lea     rdi, [rax+8]
0x1800087d1  cmp     rbx, rdi
0x1800087d4  jz      loc_1800084CC
0x1800087da  mov     r8, [rbx+18h]; lpString2
0x1800087de  mov     r9d, 0FFFFFFFFh; cchCount2
0x1800087e4  mov     rcx, [r12+18h]; lpString1
0x1800087e9  mov     edx, r9d; cchCount1
0x1800087ec  mov     [rsp+78h+bIgnoreCase], 0; bIgnoreCase
0x1800087f4  call    cs:__imp_CompareStringOrdinal
0x1800087fb  nop     dword ptr [rax+rax+00h]
0x180008800  test    eax, eax
0x180008802  jz      loc_180008AA0
0x180008808  cmp     eax, 2
0x18000880b  jz      short loc_180008812
0x18000880d  mov     rbx, [rbx]
0x180008810  jmp     short loc_1800087D1
0x180008812  mov     r8, [rbx+10h]; lpString2
0x180008816  mov     r9d, 0FFFFFFFFh; cchCount2
0x18000881c  mov     rcx, [r12+10h]; lpString1
0x180008821  mov     edx, r9d; cchCount1
0x180008824  mov     [rsp+78h+bIgnoreCase], 0; bIgnoreCase
0x18000882c  call    cs:__imp_CompareStringOrdinal
0x180008833  nop     dword ptr [rax+rax+00h]
0x180008838  test    eax, eax
0x18000883a  jz      loc_180008A40
0x180008840  cmp     eax, 2
0x180008843  jnz     short loc_18000880D
0x180008845  add     dword ptr [rbx+20h], 1
0x180008849  jnz     short loc_180008852
0x18000884b  mov     dword ptr [rbx+20h], 1
0x180008852  mov     [r14], rbx
0x180008855  jmp     loc_1800084CC
  ... truncated ...
```
