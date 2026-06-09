# CreateAccountingAttributes

- ea: `0x18001063c`
- end: `0x180010d36`
- name: `CreateAccountingAttributes`
- size: `1786`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x18000380c`
- `0x180012d54`

## callees

- `0x180001460`
- `0x18001063c`
- `0x18001a024`
- `0x18001ac50`
- `0x18001acd8`
- `0x18001b3d0`
- `0x18001b3f8`
- `0x18001b424`
- `0x18001b4b0`
- `0x18001b6b4`
- `0x18001b6f8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__itoa_s` at `0x180010739`
- `api-ms-win-crt-private-l1-1-0!_o__itoa_s` at `0x180010762`
- `api-ms-win-crt-private-l1-1-0!_o__itoa_s` at `0x180010739`
- `api-ms-win-crt-private-l1-1-0!_o__itoa_s` at `0x180010762`
- `DSROLE!DsRoleFreeMemory` at `0x180010c39`
- `DSROLE!DsRoleFreeMemory` at `0x180010c39`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x180010c14`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x180010c14`
- `WS2_32!__imp_ntohl` at `0x180010961`
- `WS2_32!__imp_ntohl` at `0x180010961`

## pseudocode

```c
_QWORD *__fastcall CreateAccountingAttributes(__int64 a1)
{
  __int64 v1; // r15
  _DWORD *v3; // rcx
  _QWORD *result; // rax
  bool v5; // zf
  __int64 v6; // rsi
  int v7; // ebx
  _DWORD *i; // rax
  _DWORD *j; // rax
  __int64 v10; // rcx
  _DWORD *VendorSpecific; // rax
  __int64 v12; // rcx
  _DWORD *v13; // r14
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  _DWORD *v17; // rcx
  unsigned int v18; // ebx
  DWORD inserted; // eax
  _DWORD *k; // rax
  __int64 v21; // r9
  _DWORD *m; // rax
  __int64 v23; // r9
  __int64 v24; // rsi
  __int64 v25; // rax
  __int64 v26; // r9
  _BYTE *v27; // rcx
  __int64 v28; // rax
  u_long v29; // ecx
  signed int v30; // eax
  __int64 v31; // r9
  __int64 v32; // r9
  __int64 v33; // rax
  __int64 v34; // r9
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // r9
  unsigned int SecondsSince1970; // eax
  __int64 v39; // r9
  __int64 v40; // r9
  __int64 v41; // rsi
  __int64 v42; // r8
  __int64 v43; // r9
  __int64 v44; // rax
  int v45; // ecx
  __int64 v46; // rdx
  __int64 v47; // rcx
  size_t Size; // [rsp+20h] [rbp-49h]
  size_t Sizea; // [rsp+20h] [rbp-49h]
  size_t Sizeb; // [rsp+20h] [rbp-49h]
  size_t Sizec; // [rsp+20h] [rbp-49h]
  size_t Sized; // [rsp+20h] [rbp-49h]
  size_t Sizee; // [rsp+20h] [rbp-49h]
  size_t Sizef; // [rsp+20h] [rbp-49h]
  _DWORD *v55; // [rsp+30h] [rbp-39h] BYREF
  PBYTE Buffer; // [rsp+38h] [rbp-31h] BYREF
  __int128 Src; // [rsp+40h] [rbp-29h] BYREF
  int v58; // [rsp+50h] [rbp-19h]
  __int128 v59; // [rsp+58h] [rbp-11h] BYREF
  int v60; // [rsp+68h] [rbp-1h]

  v1 = *(_QWORD *)(a1 + 1472);
  v3 = *(_DWORD **)(a1 + 176);
  v55 = 0;
  Buffer = 0;
  result = RasAuthAttributeDestroy(v3);
  v5 = (*(_BYTE *)(a1 + 56) & 4) == 0;
  *(_QWORD *)(a1 + 176) = 0;
  if ( !v5 )
  {
    v6 = *(_QWORD *)(a1 + 168);
    v7 = 0;
    if ( !v6 )
    {
      v6 = 0;
      if ( *(_QWORD *)(a1 + 160) )
        v6 = *(_QWORD *)(a1 + 160);
    }
    for ( i = RasAuthAttributeGetFirst(25, v6); i; i = RasAuthAttributeGetNext(&v55, 25) )
      ++v7;
    for ( j = RasAuthAttributeGetFirst(22, *(_QWORD *)(a1 + 160)); j; j = RasAuthAttributeGetNext(&v55, 22) )
      ++v7;
    VendorSpecific = RasAuthAttributeGetVendorSpecific(v10, 10, v6);
    v12 = *(unsigned int *)(a1 + 1688);
    v13 = VendorSpecific;
    v58 = 0;
    Src = 0;
    _o__itoa_s(v12, &Src, 20);
    v14 = *(_QWORD *)(a1 + 8);
    v59 = 0;
    v60 = 0;
    _o__itoa_s(*(unsigned int *)(v14 + 28), &v59, 20);
    result = RasAuthAttributeCreate(v7 + 44);
    *(_QWORD *)(a1 + 176) = result;
    if ( result )
    {
      v17 = *(_DWORD **)(a1 + 152);
      v18 = 0;
      if ( *v17 )
      {
        while ( 1 )
        {
          LODWORD(Size) = v17[4 * v18 + 1];
          inserted = RasAuthAttributeInsert(
                       v18,
                       *(_QWORD *)(a1 + 176),
                       v17[4 * v18],
                       v16,
                       Size,
                       *(void **)&v17[4 * v18 + 2]);
          if ( inserted )
            goto LABEL_70;
          v17 = *(_DWORD **)(a1 + 152);
          if ( !v17[4 * ++v18] )
          {
            result = *(_QWORD **)(a1 + 176);
            break;
          }
        }
      }
      inserted = RasAuthAttributeInsertNAS(v18++, (__int64)result, v15, v16);
      if ( !inserted )
      {
        for ( k = RasAuthAttributeGetFirst(25, v6); k; k = RasAuthAttributeGetNext(&v55, 25) )
        {
          LODWORD(Size) = k[1];
          inserted = RasAuthAttributeInsert(v18++, *(_QWORD *)(a1 + 176), *k, v21, Size, *((void **)k + 1));
          if ( inserted )
            goto LABEL_70;
        }
        for ( m = RasAuthAttributeGetFirst(22, *(_QWORD *)(a1 + 160)); m; m = RasAuthAttributeGetNext(&v55, 22) )
        {
          LODWORD(Size) = m[1];
          inserted = RasAuthAttributeInsert(v18++, *(_QWORD *)(a1 + 176), *m, v23, Size, *((void **)m + 1));
          if ( inserted )
            goto LABEL_70;
        }
        if ( !v13
          || (LODWORD(Size) = v13[1],
              inserted = RasAuthAttributeInsert(v18, *(_QWORD *)(a1 + 176), *v13, v23, Size, *((void **)v13 + 1)),
              ++v18,
              !inserted) )
        {
          v24 = -1;
          v25 = -1;
          do
            ++v25;
          while ( *((_BYTE *)&Src + v25) );
          LODWORD(Size) = v25;
          inserted = RasAuthAttributeInsert(v18++, *(_QWORD *)(a1 + 176), 44, v23, Size, &Src);
          if ( !inserted )
          {
            v27 = *(_BYTE **)(*(_QWORD *)(a1 + 8) + 176LL);
            if ( !v27 )
              goto LABEL_34;
            v28 = -1;
            do
              ++v28;
            while ( v27[v28] );
            LODWORD(Sizea) = v28;
            inserted = RasAuthAttributeInsert(v18++, *(_QWORD *)(a1 + 176), 1, v26, Sizea, v27);
            if ( !inserted )
            {
LABEL_34:
              v29 = *(_DWORD *)(*(_QWORD *)(a1 + 8) + 120LL);
              if ( !v29
                || (v30 = ntohl(v29),
                    LODWORD(Sizea) = 4,
                    inserted = RasAuthAttributeInsert(v18, *(_QWORD *)(a1 + 176), 8, v31, Sizea, (void *)v30),
                    ++v18,
                    !inserted) )
              {
                if ( !*(_QWORD *)(*(_QWORD *)(a1 + 8) + 136LL)
                  || (LODWORD(Sizea) = 8,
                      inserted = RasAuthAttributeInsert(
                                   v18,
                                   *(_QWORD *)(a1 + 176),
                                   96,
                                   v26,
                                   Sizea,
                                   (void *)(*(_QWORD *)(a1 + 8) + 136LL)),
                      ++v18,
                      !inserted)
                  && (LODWORD(Sizeb) = 8,
                      inserted = RasAuthAttributeInsert(
                                   v18,
                                   *(_QWORD *)(a1 + 176),
                                   97,
                                   v32,
                                   Sizeb,
                                   (void *)(*(_QWORD *)(a1 + 8) + 144LL)),
                      ++v18,
                      !inserted) )
                {
                  v33 = *(unsigned int *)(v1 + 1412);
                  if ( (unsigned int)v33 > 0x5DC )
                    v33 = 1500;
                  LODWORD(Sizea) = 4;
                  inserted = RasAuthAttributeInsert(v18++, *(_QWORD *)(a1 + 176), 12, v26, Sizea, (void *)v33);
                  if ( !inserted )
                  {
                    if ( (*(_DWORD *)(*(_QWORD *)(a1 + 8) + 52LL) & 0x400) == 0
                      || (LODWORD(Sizec) = 4,
                          inserted = RasAuthAttributeInsert(v18, *(_QWORD *)(a1 + 176), 13, v34, Sizec, (void *)1),
                          ++v18,
                          !inserted) )
                    {
                      if ( !*(_BYTE *)(a1 + 1536) )
                        goto LABEL_75;
                      v35 = -1;
                      do
                        ++v35;
                      while ( *(_BYTE *)(a1 + 1536 + v35) );
                      LODWORD(Sizec) = v35;
                      inserted = RasAuthAttributeInsert(
                                   v18++,
                                   *(_QWORD *)(a1 + 176),
                                   19,
                                   v34,
                                   Sizec,
                                   (void *)(a1 + 1536));
                      if ( !inserted )
                      {
LABEL_75:
                        if ( !*(_DWORD *)(a1 + 80)
                          || (LODWORD(Sizec) = 4,
                              inserted = RasAuthAttributeInsert(
                                           v18,
                                           *(_QWORD *)(a1 + 176),
                                           27,
                                           v34,
                                           Sizec,
                                           (void *)*(unsigned int *)(a1 + 80)),
                              ++v18,
                              !inserted) )
                        {
                          if ( !*(_DWORD *)(a1 + 88)
                            || (LODWORD(Sizec) = 4,
                                inserted = RasAuthAttributeInsert(
                                             v18,
                                             *(_QWORD *)(a1 + 176),
                                             28,
                                             v34,
                                             Sizec,
                                             (void *)*(unsigned int *)(a1 + 88)),
                                ++v18,
                                !inserted) )
                          {
                            v36 = *(_QWORD *)(a1 + 8);
                            if ( *(_DWORD *)(v36 + 24) == -1
                              || (LODWORD(Sizec) = 4,
                                  inserted = RasAuthAttributeInsert(
                                               v18,
                                               *(_QWORD *)(a1 + 176),
                                               62,
                                               v34,
                                               Sizec,
                                               (void *)*(unsigned int *)(v36 + 24)),
                                  ++v18,
                                  !inserted) )
                            {
                              do
                                ++v24;
                              while ( *((_BYTE *)&v59 + v24) );
                              LODWORD(Sizec) = v24;
                              inserted = RasAuthAttributeInsert(v18++, *(_QWORD *)(a1 + 176), 50, v34, Sizec, &v59);
                              if ( !inserted )
                              {
                                LODWORD(Sized) = 4;
                                inserted = RasAuthAttributeInsert(
                                             v18++,
                                             *(_QWORD *)(a1 + 176),
                                             51,
                                             v37,
                                             Sized,
                                             (void *)*(unsigned int *)(*(_QWORD *)(a1 + 8) + 20LL));
                                if ( !inserted )
                                {
                                  SecondsSince1970 = GetSecondsSince1970();
                                  LODWORD(Sizee) = 4;
                                  inserted = RasAuthAttributeInsert(
                                               v18++,
                                               *(_QWORD *)(a1 + 176),
                                               55,
                                               v39,
                                               Sizee,
                                               (void *)SecondsSince1970);
                                  if ( !inserted )
                                  {
                                    if ( dword_18004D9F0 )
                                    {
                                      v41 = 1;
                                    }
                                    else
                                    {
                                      Buffer = 0;
                                      if ( DsRoleGetPrimaryDomainInformation(0, DsRolePrimaryDomainInfoBasic, &Buffer) )
                                      {
LABEL_63:
                                        v44 = *(_QWORD *)(a1 + 8);
                                        if ( (*(_DWORD *)(v44 + 52) & 0x48800) != 0 )
                                        {
                                          v45 = 2;
                                        }
                                        else if ( (*(_DWORD *)(v44 + 52) & 0xA1000) != 0 )
                                        {
                                          v45 = 8;
                                        }
                                        else
                                        {
                                          v45 = 0;
                                          if ( (*(_DWORD *)(v44 + 52) & 0x112000) != 0 )
                                            v45 = 4;
                                        }
                                        v46 = *(_QWORD *)(a1 + 176);
                                        BYTE2(v55) = HIBYTE(v45);
                                        BYTE3(v55) = BYTE2(v45);
                                        BYTE4(v55) = BYTE1(v45);
                                        BYTE5(v55) = v45;
                                        LOWORD(v55) = 1544;
                                        inserted = RasAuthAttributeInsertVSA(v18++, v46, v42, v43, (__int64)&v55);
                                        goto LABEL_70;
                                      }
                                      v41 = 3LL - (((*(_DWORD *)Buffer - 1) & 0xFFFFFFFD) != 0);
                                      DsRoleFreeMemory(Buffer);
                                    }
                                    LODWORD(Sizef) = 4;
                                    inserted = RasAuthAttributeInsert(
                                                 v18++,
                                                 *(_QWORD *)(a1 + 176),
                                                 45,
                                                 v40,
                                                 Sizef,
                                                 (void *)v41);
                                    if ( !inserted )
                                      goto LABEL_63;
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
LABEL_70:
      if ( inserted )
      {
        result = RasAuthAttributeDestroy(*(_DWORD **)(a1 + 176));
        *(_QWORD *)(a1 + 176) = 0;
      }
      else
      {
        v47 = 2LL * v18;
        *(_DWORD *)(*(_QWORD *)(a1 + 176) + 8 * v47) = 0;
        *(_DWORD *)(*(_QWORD *)(a1 + 176) + 8 * v47 + 4) = 0;
        result = *(_QWORD **)(a1 + 176);
        result[v47 + 1] = 0;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001063c  push    rbp
0x18001063e  push    rbx
0x18001063f  push    rsi
0x180010640  push    rdi
0x180010641  push    r12
0x180010643  push    r13
0x180010645  push    r14
0x180010647  push    r15
0x180010649  lea     rbp, [rsp-1Fh]
0x18001064e  sub     rsp, 88h
0x180010655  mov     rax, cs:__security_cookie
0x18001065c  xor     rax, rsp
0x18001065f  mov     [rbp+57h+var_50], rax
0x180010663  mov     r15, [rcx+5C0h]
0x18001066a  mov     rdi, rcx
0x18001066d  mov     rcx, [rcx+0B0h]; hMem
0x180010674  xor     r14d, r14d
0x180010677  mov     [rbp+57h+var_90], r14
0x18001067b  mov     [rbp+57h+Buffer], r14
0x18001067f  call    RasAuthAttributeDestroy
0x180010684  test    byte ptr [rdi+38h], 4
0x180010688  mov     [rdi+0B0h], r14
0x18001068f  jz      loc_180010D15
0x180010695  mov     rsi, [rdi+0A8h]
0x18001069c  mov     ebx, r14d
0x18001069f  test    rsi, rsi
0x1800106a2  jnz     short loc_1800106B5
0x1800106a4  mov     rax, [rdi+0A0h]
0x1800106ab  mov     esi, r14d
0x1800106ae  test    rax, rax
0x1800106b1  cmovnz  rsi, rax
0x1800106b5  lea     r8, [rbp+57h+var_90]
0x1800106b9  mov     rdx, rsi
0x1800106bc  mov     ecx, 19h
0x1800106c1  call    RasAuthAttributeGetFirst
0x1800106c6  jmp     short loc_1800106D8
0x1800106c8  inc     ebx
0x1800106ca  lea     rcx, [rbp+57h+var_90]
0x1800106ce  mov     edx, 19h
0x1800106d3  call    RasAuthAttributeGetNext
0x1800106d8  test    rax, rax
0x1800106db  jnz     short loc_1800106C8
0x1800106dd  mov     rdx, [rdi+0A0h]
0x1800106e4  lea     r8, [rbp+57h+var_90]
0x1800106e8  lea     ecx, [rax+16h]
0x1800106eb  call    RasAuthAttributeGetFirst
0x1800106f0  jmp     short loc_180010702
0x1800106f2  inc     ebx
0x1800106f4  lea     rcx, [rbp+57h+var_90]
0x1800106f8  mov     edx, 16h
0x1800106fd  call    RasAuthAttributeGetNext
0x180010702  test    rax, rax
0x180010705  jnz     short loc_1800106F2
0x180010707  lea     r13d, [rax+0Ah]
0x18001070b  mov     r8, rsi
0x18001070e  mov     edx, r13d
0x180010711  call    RasAuthAttributeGetVendorSpecific
0x180010716  mov     ecx, [rdi+698h]
0x18001071c  lea     r12d, [r13+0Ah]
0x180010720  mov     r14, rax
0x180010723  lea     rdx, [rbp+57h+var_80]
0x180010727  xor     eax, eax
0x180010729  xorps   xmm0, xmm0
0x18001072c  mov     r9d, r13d
0x18001072f  mov     [rbp+57h+var_70], eax
0x180010732  mov     r8d, r12d
0x180010735  movups  [rbp+57h+var_80], xmm0
0x180010739  call    cs:__imp__o__itoa_s
0x180010740  nop     dword ptr [rax+rax+00h]
0x180010745  mov     rcx, [rdi+8]
0x180010749  lea     rdx, [rbp+57h+var_68]
0x18001074d  xorps   xmm0, xmm0
0x180010750  xor     eax, eax
0x180010752  movups  [rbp+57h+var_68], xmm0
0x180010756  mov     [rbp+57h+var_58], eax
0x180010759  mov     r9d, r13d
0x18001075c  mov     ecx, [rcx+1Ch]
0x18001075f  mov     r8d, r12d
0x180010762  call    cs:__imp__o__itoa_s
0x180010769  nop     dword ptr [rax+rax+00h]
0x18001076e  lea     ecx, [rbx+2Ch]
0x180010771  call    RasAuthAttributeCreate
0x180010776  xor     r12d, r12d
0x180010779  mov     [rdi+0B0h], rax
0x180010780  test    rax, rax
0x180010783  jz      loc_180010D15
0x180010789  mov     rcx, [rdi+98h]
0x180010790  lea     r13d, [r12+1]
0x180010795  mov     ebx, r12d
0x180010798  cmp     [rcx], r12d
0x18001079b  jz      short loc_1800107EC
0x18001079d  mov     rdx, [rdi+0B0h]; int
0x1800107a4  mov     r8d, ebx
0x1800107a7  add     r8, r8
0x1800107aa  mov     rax, [rcx+r8*8+8]
0x1800107af  mov     [rsp+0C0h+Src], rax; Src
0x1800107b4  mov     eax, [rcx+r8*8+4]
0x1800107b9  mov     r8d, [rcx+r8*8]; int
0x1800107bd  mov     ecx, ebx; int
0x1800107bf  mov     dword ptr [rsp+0C0h+Size], eax; Size
0x1800107c3  call    RasAuthAttributeInsert
0x1800107c8  test    eax, eax
0x1800107ca  jnz     loc_180010CD8
0x1800107d0  mov     rcx, [rdi+98h]
0x1800107d7  add     ebx, r13d
0x1800107da  mov     eax, ebx
0x1800107dc  add     rax, rax
0x1800107df  cmp     [rcx+rax*8], r12d
0x1800107e3  jnz     short loc_18001079D
0x1800107e5  mov     rax, [rdi+0B0h]
0x1800107ec  mov     rdx, rax
0x1800107ef  mov     ecx, ebx
0x1800107f1  call    RasAuthAttributeInsertNAS
0x1800107f6  add     ebx, r13d
0x1800107f9  test    eax, eax
0x1800107fb  jnz     loc_180010CD8
0x180010801  mov     rdx, rsi
0x180010804  lea     r8, [rbp+57h+var_90]
0x180010808  lea     esi, [rax+19h]
0x18001080b  mov     ecx, esi
0x18001080d  call    RasAuthAttributeGetFirst
0x180010812  jmp     short loc_18001084B
0x180010814  mov     rcx, [rax+8]
0x180010818  mov     r8d, [rax]; int
0x18001081b  mov     rdx, [rdi+0B0h]; int
0x180010822  mov     [rsp+0C0h+Src], rcx; Src
0x180010827  mov     ecx, [rax+4]
0x18001082a  mov     dword ptr [rsp+0C0h+Size], ecx; Size
0x18001082e  mov     ecx, ebx; int
0x180010830  call    RasAuthAttributeInsert
0x180010835  add     ebx, r13d
0x180010838  test    eax, eax
0x18001083a  jnz     loc_180010CD8
0x180010840  mov     edx, esi
0x180010842  lea     rcx, [rbp+57h+var_90]
0x180010846  call    RasAuthAttributeGetNext
0x18001084b  test    rax, rax
0x18001084e  jnz     short loc_180010814
0x180010850  mov     rdx, [rdi+0A0h]
0x180010857  lea     esi, [rax+16h]
0x18001085a  mov     ecx, esi
0x18001085c  lea     r8, [rbp+57h+var_90]
0x180010860  call    RasAuthAttributeGetFirst
0x180010865  jmp     short loc_18001089E
0x180010867  mov     rcx, [rax+8]
0x18001086b  mov     r8d, [rax]; int
0x18001086e  mov     rdx, [rdi+0B0h]; int
0x180010875  mov     [rsp+0C0h+Src], rcx; Src
0x18001087a  mov     ecx, [rax+4]
0x18001087d  mov     dword ptr [rsp+0C0h+Size], ecx; Size
0x180010881  mov     ecx, ebx; int
0x180010883  call    RasAuthAttributeInsert
0x180010888  add     ebx, r13d
0x18001088b  test    eax, eax
0x18001088d  jnz     loc_180010CD8
0x180010893  mov     edx, esi
0x180010895  lea     rcx, [rbp+57h+var_90]
0x180010899  call    RasAuthAttributeGetNext
0x18001089e  test    rax, rax
0x1800108a1  jnz     short loc_180010867
0x1800108a3  test    r14, r14
0x1800108a6  jz      short loc_1800108D5
0x1800108a8  mov     rax, [r14+8]
0x1800108ac  mov     ecx, ebx; int
0x1800108ae  mov     r8d, [r14]; int
0x1800108b1  mov     rdx, [rdi+0B0h]; int
0x1800108b8  mov     [rsp+0C0h+Src], rax; Src
0x1800108bd  mov     eax, [r14+4]
0x1800108c1  mov     dword ptr [rsp+0C0h+Size], eax; Size
0x1800108c5  call    RasAuthAttributeInsert
0x1800108ca  add     ebx, r13d
0x1800108cd  test    eax, eax
0x1800108cf  jnz     loc_180010CD8
0x1800108d5  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800108d9  lea     rcx, [rbp+57h+var_80]
0x1800108dd  mov     rax, rsi
0x1800108e0  inc     rax
0x1800108e3  cmp     [rcx+rax], r12b
0x1800108e7  jnz     short loc_1800108E0
0x1800108e9  mov     rdx, [rdi+0B0h]; int
0x1800108f0  lea     rcx, [rbp+57h+var_80]
0x1800108f4  mov     [rsp+0C0h+Src], rcx; Src
0x1800108f9  mov     r8d, 2Ch ; ','; int
0x1800108ff  mov     ecx, ebx; int
0x180010901  mov     dword ptr [rsp+0C0h+Size], eax; Size
0x180010905  call    RasAuthAttributeInsert
0x18001090a  add     ebx, r13d
0x18001090d  test    eax, eax
0x18001090f  jnz     loc_180010CD8
0x180010915  mov     rax, [rdi+8]
0x180010919  mov     rcx, [rax+0B0h]
0x180010920  test    rcx, rcx
0x180010923  jz      short loc_180010956
0x180010925  mov     rax, rsi
0x180010928  inc     rax
0x18001092b  cmp     [rcx+rax], r12b
0x18001092f  jnz     short loc_180010928
0x180010931  mov     rdx, [rdi+0B0h]; int
0x180010938  mov     r8d, r13d; int
0x18001093b  mov     [rsp+0C0h+Src], rcx; Src
0x180010940  mov     ecx, ebx; int
0x180010942  mov     dword ptr [rsp+0C0h+Size], eax; Size
0x180010946  call    RasAuthAttributeInsert
0x18001094b  add     ebx, r13d
0x18001094e  test    eax, eax
0x180010950  jnz     loc_180010CD8
0x180010956  mov     rax, [rdi+8]
0x18001095a  mov     ecx, [rax+78h]; netlong
0x18001095d  test    ecx, ecx
0x18001095f  jz      short loc_18001099F
0x180010961  call    cs:__imp_ntohl
0x180010968  nop     dword ptr [rax+rax+00h]
0x18001096d  mov     rdx, [rdi+0B0h]; int
0x180010974  mov     r14d, 4
0x18001097a  movsxd  rcx, eax
0x18001097d  mov     [rsp+0C0h+Src], rcx; Src
0x180010982  mov     ecx, ebx; int
0x180010984  mov     dword ptr [rsp+0C0h+Size], r14d; Size
0x180010989  lea     r8d, [r14+4]; int
0x18001098d  call    RasAuthAttributeInsert
0x180010992  add     ebx, r13d
0x180010995  test    eax, eax
0x180010997  jnz     loc_180010CD8
0x18001099d  jmp     short loc_1800109A5
0x18001099f  mov     r14d, 4
0x1800109a5  mov     rax, [rdi+8]
0x1800109a9  add     rax, 88h
0x1800109af  cmp     [rax], r12
0x1800109b2  jz      short loc_180010A16
0x1800109b4  mov     rdx, [rdi+0B0h]; int
0x1800109bb  mov     r8d, 60h ; '`'; int
0x1800109c1  mov     [rsp+0C0h+Src], rax; Src
0x1800109c6  mov     ecx, ebx; int
0x1800109c8  mov     dword ptr [rsp+0C0h+Size], 8; Size
0x1800109d0  call    RasAuthAttributeInsert
0x1800109d5  add     ebx, r13d
0x1800109d8  test    eax, eax
0x1800109da  jnz     loc_180010CD8
0x1800109e0  mov     rax, [rdi+8]
0x1800109e4  mov     r8d, 61h ; 'a'; int
0x1800109ea  mov     rdx, [rdi+0B0h]; int
0x1800109f1  add     rax, 90h
0x1800109f7  mov     [rsp+0C0h+Src], rax; Src
0x1800109fc  mov     ecx, ebx; int
0x1800109fe  mov     dword ptr [rsp+0C0h+Size], 8; Size
0x180010a06  call    RasAuthAttributeInsert
0x180010a0b  add     ebx, r13d
0x180010a0e  test    eax, eax
0x180010a10  jnz     loc_180010CD8
0x180010a16  mov     eax, [r15+584h]
0x180010a1d  mov     ecx, 5DCh
0x180010a22  mov     rdx, [rdi+0B0h]; int
0x180010a29  cmp     eax, ecx
0x180010a2b  mov     r8d, 0Ch; int
0x180010a31  cmova   eax, ecx
0x180010a34  mov     ecx, ebx; int
0x180010a36  mov     [rsp+0C0h+Src], rax; Src
0x180010a3b  mov     dword ptr [rsp+0C0h+Size], r14d; Size
0x180010a40  call    RasAuthAttributeInsert
0x180010a45  add     ebx, r13d
0x180010a48  test    eax, eax
0x180010a4a  jnz     loc_180010CD8
0x180010a50  mov     rax, [rdi+8]
0x180010a54  test    dword ptr [rax+34h], 400h
0x180010a5b  jz      short loc_180010A86
0x180010a5d  mov     rdx, [rdi+0B0h]; int
0x180010a64  mov     r8d, 0Dh; int
0x180010a6a  mov     [rsp+0C0h+Src], r13; Src
0x180010a6f  mov     ecx, ebx; int
0x180010a71  mov     dword ptr [rsp+0C0h+Size], r14d; Size
0x180010a76  call    RasAuthAttributeInsert
0x180010a7b  add     ebx, r13d
0x180010a7e  test    eax, eax
0x180010a80  jnz     loc_180010CD8
0x180010a86  lea     rcx, [rdi+600h]
0x180010a8d  cmp     [rcx], r12b
0x180010a90  jz      short loc_180010AC6
0x180010a92  mov     rax, rsi
0x180010a95  inc     rax
0x180010a98  cmp     [rcx+rax], r12b
0x180010a9c  jnz     short loc_180010A95
0x180010a9e  mov     rdx, [rdi+0B0h]; int
0x180010aa5  mov     r8d, 13h; int
0x180010aab  mov     [rsp+0C0h+Src], rcx; Src
0x180010ab0  mov     ecx, ebx; int
0x180010ab2  mov     dword ptr [rsp+0C0h+Size], eax; Size
0x180010ab6  call    RasAuthAttributeInsert
0x180010abb  add     ebx, r13d
0x180010abe  test    eax, eax
0x180010ac0  jnz     loc_180010CD8
0x180010ac6  cmp     [rdi+50h], r12d
0x180010aca  jbe     short loc_180010AF8
0x180010acc  mov     eax, [rdi+50h]
0x180010acf  mov     r8d, 1Bh; int
0x180010ad5  mov     rdx, [rdi+0B0h]; int
0x180010adc  mov     ecx, ebx; int
0x180010ade  mov     [rsp+0C0h+Src], rax; Src
0x180010ae3  mov     dword ptr [rsp+0C0h+Size], r14d; Size
0x180010ae8  call    RasAuthAttributeInsert
0x180010aed  add     ebx, r13d
  ... truncated ...
```
