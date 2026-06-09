# CreateAccountingAttributes

- ea: `0x18001016c`
- end: `0x180010847`
- name: `CreateAccountingAttributes`
- size: `1755`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x180003770`
- `0x1800126b8`

## callees

- `0x180001460`
- `0x18001016c`
- `0x1800196c0`
- `0x18001a2ac`
- `0x18001a330`
- `0x18001a9e4`
- `0x18001aa08`
- `0x18001aa34`
- `0x18001aac0`
- `0x18001acac`
- `0x18001acf0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__itoa_s` at `0x180010269`
- `api-ms-win-crt-private-l1-1-0!_o__itoa_s` at `0x18001028c`
- `api-ms-win-crt-private-l1-1-0!_o__itoa_s` at `0x180010269`
- `api-ms-win-crt-private-l1-1-0!_o__itoa_s` at `0x18001028c`
- `DSROLE!DsRoleFreeMemory` at `0x180010751`
- `DSROLE!DsRoleFreeMemory` at `0x180010751`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x180010732`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x180010732`
- `WS2_32!__imp_ntohl` at `0x180010485`
- `WS2_32!__imp_ntohl` at `0x180010485`

## pseudocode

```c
__int64 __fastcall CreateAccountingAttributes(__int64 a1)
{
  __int64 v1; // r15
  void *v3; // rcx
  __int64 result; // rax
  bool v5; // zf
  __int64 v6; // rsi
  int v7; // ebx
  __int64 i; // rax
  __int64 j; // rax
  __int64 v10; // rcx
  __int64 VendorSpecific; // rax
  __int64 v12; // rcx
  __int64 v13; // r14
  __int64 v14; // rcx
  int v15; // r9d
  _DWORD *v16; // rcx
  unsigned int v17; // ebx
  int inserted; // eax
  __int64 k; // rax
  int v20; // r9d
  __int64 m; // rax
  int v22; // r9d
  __int64 v23; // rsi
  __int64 v24; // rax
  int v25; // r9d
  _BYTE *v26; // rcx
  __int64 v27; // rax
  u_long v28; // ecx
  signed int v29; // eax
  int v30; // r9d
  int v31; // r9d
  __int64 v32; // rax
  int v33; // r9d
  __int64 v34; // rax
  __int64 v35; // rax
  int v36; // r9d
  unsigned int SecondsSince1970; // eax
  int v38; // r9d
  int v39; // r9d
  __int64 v40; // rsi
  int v41; // r8d
  int v42; // r9d
  __int64 v43; // rax
  int v44; // ecx
  __int64 v45; // rdx
  __int64 v46; // rcx
  size_t Size; // [rsp+20h] [rbp-49h]
  size_t Sizea; // [rsp+20h] [rbp-49h]
  size_t Sizeb; // [rsp+20h] [rbp-49h]
  size_t Sizec; // [rsp+20h] [rbp-49h]
  size_t Sized; // [rsp+20h] [rbp-49h]
  size_t Sizee; // [rsp+20h] [rbp-49h]
  size_t Sizef; // [rsp+20h] [rbp-49h]
  __int64 v54; // [rsp+30h] [rbp-39h] BYREF
  PBYTE Buffer; // [rsp+38h] [rbp-31h] BYREF
  __int128 Src; // [rsp+40h] [rbp-29h] BYREF
  int v57; // [rsp+50h] [rbp-19h]
  __int128 v58; // [rsp+58h] [rbp-11h] BYREF
  int v59; // [rsp+68h] [rbp-1h]

  v1 = *(_QWORD *)(a1 + 1472);
  v3 = *(void **)(a1 + 176);
  v54 = 0;
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
    for ( i = RasAuthAttributeGetFirst(25, v6, &v54); i; i = RasAuthAttributeGetNext(&v54, 25) )
      ++v7;
    for ( j = RasAuthAttributeGetFirst(22, *(_QWORD *)(a1 + 160), &v54); j; j = RasAuthAttributeGetNext(&v54, 22) )
      ++v7;
    VendorSpecific = RasAuthAttributeGetVendorSpecific(v10, 10, v6);
    v12 = *(unsigned int *)(a1 + 1688);
    v13 = VendorSpecific;
    v57 = 0;
    Src = 0;
    _o__itoa_s(v12, &Src, 20);
    v14 = *(_QWORD *)(a1 + 8);
    v58 = 0;
    v59 = 0;
    _o__itoa_s(*(unsigned int *)(v14 + 28), &v58, 20);
    result = RasAuthAttributeCreate((unsigned int)(v7 + 44));
    *(_QWORD *)(a1 + 176) = result;
    if ( result )
    {
      v16 = *(_DWORD **)(a1 + 152);
      v17 = 0;
      if ( *v16 )
      {
        while ( 1 )
        {
          LODWORD(Size) = v16[4 * v17 + 1];
          inserted = RasAuthAttributeInsert(
                       v17,
                       *(_QWORD *)(a1 + 176),
                       v16[4 * v17],
                       v15,
                       Size,
                       *(void **)&v16[4 * v17 + 2]);
          if ( inserted )
            goto LABEL_70;
          v16 = *(_DWORD **)(a1 + 152);
          if ( !v16[4 * ++v17] )
          {
            result = *(_QWORD *)(a1 + 176);
            break;
          }
        }
      }
      inserted = RasAuthAttributeInsertNAS(v17++, result);
      if ( !inserted )
      {
        for ( k = RasAuthAttributeGetFirst(25, v6, &v54); k; k = RasAuthAttributeGetNext(&v54, 25) )
        {
          LODWORD(Size) = *(_DWORD *)(k + 4);
          inserted = RasAuthAttributeInsert(v17++, *(_QWORD *)(a1 + 176), *(_DWORD *)k, v20, Size, *(void **)(k + 8));
          if ( inserted )
            goto LABEL_70;
        }
        for ( m = RasAuthAttributeGetFirst(22, *(_QWORD *)(a1 + 160), &v54); m; m = RasAuthAttributeGetNext(&v54, 22) )
        {
          LODWORD(Size) = *(_DWORD *)(m + 4);
          inserted = RasAuthAttributeInsert(v17++, *(_QWORD *)(a1 + 176), *(_DWORD *)m, v22, Size, *(void **)(m + 8));
          if ( inserted )
            goto LABEL_70;
        }
        if ( !v13
          || (LODWORD(Size) = *(_DWORD *)(v13 + 4),
              inserted = RasAuthAttributeInsert(
                           v17,
                           *(_QWORD *)(a1 + 176),
                           *(_DWORD *)v13,
                           v22,
                           Size,
                           *(void **)(v13 + 8)),
              ++v17,
              !inserted) )
        {
          v23 = -1;
          v24 = -1;
          do
            ++v24;
          while ( *((_BYTE *)&Src + v24) );
          LODWORD(Size) = v24;
          inserted = RasAuthAttributeInsert(v17++, *(_QWORD *)(a1 + 176), 44, v22, Size, &Src);
          if ( !inserted )
          {
            v26 = *(_BYTE **)(*(_QWORD *)(a1 + 8) + 176LL);
            if ( !v26 )
              goto LABEL_34;
            v27 = -1;
            do
              ++v27;
            while ( v26[v27] );
            LODWORD(Sizea) = v27;
            inserted = RasAuthAttributeInsert(v17++, *(_QWORD *)(a1 + 176), 1, v25, Sizea, v26);
            if ( !inserted )
            {
LABEL_34:
              v28 = *(_DWORD *)(*(_QWORD *)(a1 + 8) + 120LL);
              if ( !v28
                || (v29 = ntohl(v28),
                    LODWORD(Sizea) = 4,
                    inserted = RasAuthAttributeInsert(v17, *(_QWORD *)(a1 + 176), 8, v30, Sizea, (void *)v29),
                    ++v17,
                    !inserted) )
              {
                if ( !*(_QWORD *)(*(_QWORD *)(a1 + 8) + 136LL)
                  || (LODWORD(Sizea) = 8,
                      inserted = RasAuthAttributeInsert(
                                   v17,
                                   *(_QWORD *)(a1 + 176),
                                   96,
                                   v25,
                                   Sizea,
                                   (void *)(*(_QWORD *)(a1 + 8) + 136LL)),
                      ++v17,
                      !inserted)
                  && (LODWORD(Sizeb) = 8,
                      inserted = RasAuthAttributeInsert(
                                   v17,
                                   *(_QWORD *)(a1 + 176),
                                   97,
                                   v31,
                                   Sizeb,
                                   (void *)(*(_QWORD *)(a1 + 8) + 144LL)),
                      ++v17,
                      !inserted) )
                {
                  v32 = *(unsigned int *)(v1 + 1412);
                  if ( (unsigned int)v32 > 0x5DC )
                    v32 = 1500;
                  LODWORD(Sizea) = 4;
                  inserted = RasAuthAttributeInsert(v17++, *(_QWORD *)(a1 + 176), 12, v25, Sizea, (void *)v32);
                  if ( !inserted )
                  {
                    if ( (*(_DWORD *)(*(_QWORD *)(a1 + 8) + 52LL) & 0x400) == 0
                      || (LODWORD(Sizec) = 4,
                          inserted = RasAuthAttributeInsert(v17, *(_QWORD *)(a1 + 176), 13, v33, Sizec, (void *)1),
                          ++v17,
                          !inserted) )
                    {
                      if ( !*(_BYTE *)(a1 + 1536) )
                        goto LABEL_75;
                      v34 = -1;
                      do
                        ++v34;
                      while ( *(_BYTE *)(a1 + 1536 + v34) );
                      LODWORD(Sizec) = v34;
                      inserted = RasAuthAttributeInsert(
                                   v17++,
                                   *(_QWORD *)(a1 + 176),
                                   19,
                                   v33,
                                   Sizec,
                                   (void *)(a1 + 1536));
                      if ( !inserted )
                      {
LABEL_75:
                        if ( !*(_DWORD *)(a1 + 80)
                          || (LODWORD(Sizec) = 4,
                              inserted = RasAuthAttributeInsert(
                                           v17,
                                           *(_QWORD *)(a1 + 176),
                                           27,
                                           v33,
                                           Sizec,
                                           (void *)*(unsigned int *)(a1 + 80)),
                              ++v17,
                              !inserted) )
                        {
                          if ( !*(_DWORD *)(a1 + 88)
                            || (LODWORD(Sizec) = 4,
                                inserted = RasAuthAttributeInsert(
                                             v17,
                                             *(_QWORD *)(a1 + 176),
                                             28,
                                             v33,
                                             Sizec,
                                             (void *)*(unsigned int *)(a1 + 88)),
                                ++v17,
                                !inserted) )
                          {
                            v35 = *(_QWORD *)(a1 + 8);
                            if ( *(_DWORD *)(v35 + 24) == -1
                              || (LODWORD(Sizec) = 4,
                                  inserted = RasAuthAttributeInsert(
                                               v17,
                                               *(_QWORD *)(a1 + 176),
                                               62,
                                               v33,
                                               Sizec,
                                               (void *)*(unsigned int *)(v35 + 24)),
                                  ++v17,
                                  !inserted) )
                            {
                              do
                                ++v23;
                              while ( *((_BYTE *)&v58 + v23) );
                              LODWORD(Sizec) = v23;
                              inserted = RasAuthAttributeInsert(v17++, *(_QWORD *)(a1 + 176), 50, v33, Sizec, &v58);
                              if ( !inserted )
                              {
                                LODWORD(Sized) = 4;
                                inserted = RasAuthAttributeInsert(
                                             v17++,
                                             *(_QWORD *)(a1 + 176),
                                             51,
                                             v36,
                                             Sized,
                                             (void *)*(unsigned int *)(*(_QWORD *)(a1 + 8) + 20LL));
                                if ( !inserted )
                                {
                                  SecondsSince1970 = GetSecondsSince1970();
                                  LODWORD(Sizee) = 4;
                                  inserted = RasAuthAttributeInsert(
                                               v17++,
                                               *(_QWORD *)(a1 + 176),
                                               55,
                                               v38,
                                               Sizee,
                                               (void *)SecondsSince1970);
                                  if ( !inserted )
                                  {
                                    if ( dword_18004C9F0 )
                                    {
                                      v40 = 1;
                                    }
                                    else
                                    {
                                      Buffer = 0;
                                      if ( DsRoleGetPrimaryDomainInformation(0, DsRolePrimaryDomainInfoBasic, &Buffer) )
                                      {
LABEL_63:
                                        v43 = *(_QWORD *)(a1 + 8);
                                        if ( (*(_DWORD *)(v43 + 52) & 0x48800) != 0 )
                                        {
                                          v44 = 2;
                                        }
                                        else if ( (*(_DWORD *)(v43 + 52) & 0xA1000) != 0 )
                                        {
                                          v44 = 8;
                                        }
                                        else
                                        {
                                          v44 = 0;
                                          if ( (*(_DWORD *)(v43 + 52) & 0x112000) != 0 )
                                            v44 = 4;
                                        }
                                        v45 = *(_QWORD *)(a1 + 176);
                                        BYTE2(v54) = HIBYTE(v44);
                                        BYTE3(v54) = BYTE2(v44);
                                        BYTE4(v54) = BYTE1(v44);
                                        BYTE5(v54) = v44;
                                        LOWORD(v54) = 1544;
                                        inserted = RasAuthAttributeInsertVSA(v17++, v45, v41, v42, (__int64)&v54);
                                        goto LABEL_70;
                                      }
                                      v40 = 3LL - (((*(_DWORD *)Buffer - 1) & 0xFFFFFFFD) != 0);
                                      DsRoleFreeMemory(Buffer);
                                    }
                                    LODWORD(Sizef) = 4;
                                    inserted = RasAuthAttributeInsert(
                                                 v17++,
                                                 *(_QWORD *)(a1 + 176),
                                                 45,
                                                 v39,
                                                 Sizef,
                                                 (void *)v40);
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
        result = RasAuthAttributeDestroy(*(HLOCAL *)(a1 + 176));
        *(_QWORD *)(a1 + 176) = 0;
      }
      else
      {
        v46 = 2LL * v17;
        *(_DWORD *)(*(_QWORD *)(a1 + 176) + 8 * v46) = 0;
        *(_DWORD *)(*(_QWORD *)(a1 + 176) + 8 * v46 + 4) = 0;
        result = *(_QWORD *)(a1 + 176);
        *(_QWORD *)(result + 8 * v46 + 8) = 0;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001016c  push    rbp
0x18001016e  push    rbx
0x18001016f  push    rsi
0x180010170  push    rdi
0x180010171  push    r12
0x180010173  push    r13
0x180010175  push    r14
0x180010177  push    r15
0x180010179  lea     rbp, [rsp-1Fh]
0x18001017e  sub     rsp, 88h
0x180010185  mov     rax, cs:__security_cookie
0x18001018c  xor     rax, rsp
0x18001018f  mov     [rbp+57h+var_50], rax
0x180010193  mov     r15, [rcx+5C0h]
0x18001019a  mov     rdi, rcx
0x18001019d  mov     rcx, [rcx+0B0h]; hMem
0x1800101a4  xor     r14d, r14d
0x1800101a7  mov     [rbp+57h+var_90], r14
0x1800101ab  mov     [rbp+57h+Buffer], r14
0x1800101af  call    RasAuthAttributeDestroy
0x1800101b4  test    byte ptr [rdi+38h], 4
0x1800101b8  mov     [rdi+0B0h], r14
0x1800101bf  jz      loc_180010827
0x1800101c5  mov     rsi, [rdi+0A8h]
0x1800101cc  mov     ebx, r14d
0x1800101cf  test    rsi, rsi
0x1800101d2  jnz     short loc_1800101E5
0x1800101d4  mov     rax, [rdi+0A0h]
0x1800101db  mov     esi, r14d
0x1800101de  test    rax, rax
0x1800101e1  cmovnz  rsi, rax
0x1800101e5  lea     r8, [rbp+57h+var_90]
0x1800101e9  mov     rdx, rsi
0x1800101ec  mov     ecx, 19h
0x1800101f1  call    RasAuthAttributeGetFirst
0x1800101f6  jmp     short loc_180010208
0x1800101f8  inc     ebx
0x1800101fa  lea     rcx, [rbp+57h+var_90]
0x1800101fe  mov     edx, 19h
0x180010203  call    RasAuthAttributeGetNext
0x180010208  test    rax, rax
0x18001020b  jnz     short loc_1800101F8
0x18001020d  mov     rdx, [rdi+0A0h]
0x180010214  lea     r8, [rbp+57h+var_90]
0x180010218  lea     ecx, [rax+16h]
0x18001021b  call    RasAuthAttributeGetFirst
0x180010220  jmp     short loc_180010232
0x180010222  inc     ebx
0x180010224  lea     rcx, [rbp+57h+var_90]
0x180010228  mov     edx, 16h
0x18001022d  call    RasAuthAttributeGetNext
0x180010232  test    rax, rax
0x180010235  jnz     short loc_180010222
0x180010237  lea     r13d, [rax+0Ah]
0x18001023b  mov     r8, rsi
0x18001023e  mov     edx, r13d
0x180010241  call    RasAuthAttributeGetVendorSpecific
0x180010246  mov     ecx, [rdi+698h]
0x18001024c  lea     r12d, [r13+0Ah]
0x180010250  mov     r14, rax
0x180010253  lea     rdx, [rbp+57h+var_80]
0x180010257  xor     eax, eax
0x180010259  xorps   xmm0, xmm0
0x18001025c  mov     r9d, r13d
0x18001025f  mov     [rbp+57h+var_70], eax
0x180010262  mov     r8d, r12d
0x180010265  movups  [rbp+57h+var_80], xmm0
0x180010269  call    cs:__imp__o__itoa_s
0x18001026f  mov     rcx, [rdi+8]
0x180010273  lea     rdx, [rbp+57h+var_68]
0x180010277  xorps   xmm0, xmm0
0x18001027a  xor     eax, eax
0x18001027c  movups  [rbp+57h+var_68], xmm0
0x180010280  mov     [rbp+57h+var_58], eax
0x180010283  mov     r9d, r13d
0x180010286  mov     ecx, [rcx+1Ch]
0x180010289  mov     r8d, r12d
0x18001028c  call    cs:__imp__o__itoa_s
0x180010292  lea     ecx, [rbx+2Ch]
0x180010295  call    RasAuthAttributeCreate
0x18001029a  xor     r12d, r12d
0x18001029d  mov     [rdi+0B0h], rax
0x1800102a4  test    rax, rax
0x1800102a7  jz      loc_180010827
0x1800102ad  mov     rcx, [rdi+98h]
0x1800102b4  lea     r13d, [r12+1]
0x1800102b9  mov     ebx, r12d
0x1800102bc  cmp     [rcx], r12d
0x1800102bf  jz      short loc_180010310
0x1800102c1  mov     rdx, [rdi+0B0h]; int
0x1800102c8  mov     r8d, ebx
0x1800102cb  add     r8, r8
0x1800102ce  mov     rax, [rcx+r8*8+8]
0x1800102d3  mov     [rsp+0C0h+Src], rax; Src
0x1800102d8  mov     eax, [rcx+r8*8+4]
0x1800102dd  mov     r8d, [rcx+r8*8]; int
0x1800102e1  mov     ecx, ebx; int
0x1800102e3  mov     dword ptr [rsp+0C0h+Size], eax; Size
0x1800102e7  call    RasAuthAttributeInsert
0x1800102ec  test    eax, eax
0x1800102ee  jnz     loc_1800107EA
0x1800102f4  mov     rcx, [rdi+98h]
0x1800102fb  add     ebx, r13d
0x1800102fe  mov     eax, ebx
0x180010300  add     rax, rax
0x180010303  cmp     [rcx+rax*8], r12d
0x180010307  jnz     short loc_1800102C1
0x180010309  mov     rax, [rdi+0B0h]
0x180010310  mov     rdx, rax
0x180010313  mov     ecx, ebx
0x180010315  call    RasAuthAttributeInsertNAS
0x18001031a  add     ebx, r13d
0x18001031d  test    eax, eax
0x18001031f  jnz     loc_1800107EA
0x180010325  mov     rdx, rsi
0x180010328  lea     r8, [rbp+57h+var_90]
0x18001032c  lea     esi, [rax+19h]
0x18001032f  mov     ecx, esi
0x180010331  call    RasAuthAttributeGetFirst
0x180010336  jmp     short loc_18001036F
0x180010338  mov     rcx, [rax+8]
0x18001033c  mov     r8d, [rax]; int
0x18001033f  mov     rdx, [rdi+0B0h]; int
0x180010346  mov     [rsp+0C0h+Src], rcx; Src
0x18001034b  mov     ecx, [rax+4]
0x18001034e  mov     dword ptr [rsp+0C0h+Size], ecx; Size
0x180010352  mov     ecx, ebx; int
0x180010354  call    RasAuthAttributeInsert
0x180010359  add     ebx, r13d
0x18001035c  test    eax, eax
0x18001035e  jnz     loc_1800107EA
0x180010364  mov     edx, esi
0x180010366  lea     rcx, [rbp+57h+var_90]
0x18001036a  call    RasAuthAttributeGetNext
0x18001036f  test    rax, rax
0x180010372  jnz     short loc_180010338
0x180010374  mov     rdx, [rdi+0A0h]
0x18001037b  lea     esi, [rax+16h]
0x18001037e  mov     ecx, esi
0x180010380  lea     r8, [rbp+57h+var_90]
0x180010384  call    RasAuthAttributeGetFirst
0x180010389  jmp     short loc_1800103C2
0x18001038b  mov     rcx, [rax+8]
0x18001038f  mov     r8d, [rax]; int
0x180010392  mov     rdx, [rdi+0B0h]; int
0x180010399  mov     [rsp+0C0h+Src], rcx; Src
0x18001039e  mov     ecx, [rax+4]
0x1800103a1  mov     dword ptr [rsp+0C0h+Size], ecx; Size
0x1800103a5  mov     ecx, ebx; int
0x1800103a7  call    RasAuthAttributeInsert
0x1800103ac  add     ebx, r13d
0x1800103af  test    eax, eax
0x1800103b1  jnz     loc_1800107EA
0x1800103b7  mov     edx, esi
0x1800103b9  lea     rcx, [rbp+57h+var_90]
0x1800103bd  call    RasAuthAttributeGetNext
0x1800103c2  test    rax, rax
0x1800103c5  jnz     short loc_18001038B
0x1800103c7  test    r14, r14
0x1800103ca  jz      short loc_1800103F9
0x1800103cc  mov     rax, [r14+8]
0x1800103d0  mov     ecx, ebx; int
0x1800103d2  mov     r8d, [r14]; int
0x1800103d5  mov     rdx, [rdi+0B0h]; int
0x1800103dc  mov     [rsp+0C0h+Src], rax; Src
0x1800103e1  mov     eax, [r14+4]
0x1800103e5  mov     dword ptr [rsp+0C0h+Size], eax; Size
0x1800103e9  call    RasAuthAttributeInsert
0x1800103ee  add     ebx, r13d
0x1800103f1  test    eax, eax
0x1800103f3  jnz     loc_1800107EA
0x1800103f9  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800103fd  lea     rcx, [rbp+57h+var_80]
0x180010401  mov     rax, rsi
0x180010404  inc     rax
0x180010407  cmp     [rcx+rax], r12b
0x18001040b  jnz     short loc_180010404
0x18001040d  mov     rdx, [rdi+0B0h]; int
0x180010414  lea     rcx, [rbp+57h+var_80]
0x180010418  mov     [rsp+0C0h+Src], rcx; Src
0x18001041d  mov     r8d, 2Ch ; ','; int
0x180010423  mov     ecx, ebx; int
0x180010425  mov     dword ptr [rsp+0C0h+Size], eax; Size
0x180010429  call    RasAuthAttributeInsert
0x18001042e  add     ebx, r13d
0x180010431  test    eax, eax
0x180010433  jnz     loc_1800107EA
0x180010439  mov     rax, [rdi+8]
0x18001043d  mov     rcx, [rax+0B0h]
0x180010444  test    rcx, rcx
0x180010447  jz      short loc_18001047A
0x180010449  mov     rax, rsi
0x18001044c  inc     rax
0x18001044f  cmp     [rcx+rax], r12b
0x180010453  jnz     short loc_18001044C
0x180010455  mov     rdx, [rdi+0B0h]; int
0x18001045c  mov     r8d, r13d; int
0x18001045f  mov     [rsp+0C0h+Src], rcx; Src
0x180010464  mov     ecx, ebx; int
0x180010466  mov     dword ptr [rsp+0C0h+Size], eax; Size
0x18001046a  call    RasAuthAttributeInsert
0x18001046f  add     ebx, r13d
0x180010472  test    eax, eax
0x180010474  jnz     loc_1800107EA
0x18001047a  mov     rax, [rdi+8]
0x18001047e  mov     ecx, [rax+78h]; netlong
0x180010481  test    ecx, ecx
0x180010483  jz      short loc_1800104BD
0x180010485  call    cs:__imp_ntohl
0x18001048b  mov     rdx, [rdi+0B0h]; int
0x180010492  mov     r14d, 4
0x180010498  movsxd  rcx, eax
0x18001049b  mov     [rsp+0C0h+Src], rcx; Src
0x1800104a0  mov     ecx, ebx; int
0x1800104a2  mov     dword ptr [rsp+0C0h+Size], r14d; Size
0x1800104a7  lea     r8d, [r14+4]; int
0x1800104ab  call    RasAuthAttributeInsert
0x1800104b0  add     ebx, r13d
0x1800104b3  test    eax, eax
0x1800104b5  jnz     loc_1800107EA
0x1800104bb  jmp     short loc_1800104C3
0x1800104bd  mov     r14d, 4
0x1800104c3  mov     rax, [rdi+8]
0x1800104c7  add     rax, 88h
0x1800104cd  cmp     [rax], r12
0x1800104d0  jz      short loc_180010534
0x1800104d2  mov     rdx, [rdi+0B0h]; int
0x1800104d9  mov     r8d, 60h ; '`'; int
0x1800104df  mov     [rsp+0C0h+Src], rax; Src
0x1800104e4  mov     ecx, ebx; int
0x1800104e6  mov     dword ptr [rsp+0C0h+Size], 8; Size
0x1800104ee  call    RasAuthAttributeInsert
0x1800104f3  add     ebx, r13d
0x1800104f6  test    eax, eax
0x1800104f8  jnz     loc_1800107EA
0x1800104fe  mov     rax, [rdi+8]
0x180010502  mov     r8d, 61h ; 'a'; int
0x180010508  mov     rdx, [rdi+0B0h]; int
0x18001050f  add     rax, 90h
0x180010515  mov     [rsp+0C0h+Src], rax; Src
0x18001051a  mov     ecx, ebx; int
0x18001051c  mov     dword ptr [rsp+0C0h+Size], 8; Size
0x180010524  call    RasAuthAttributeInsert
0x180010529  add     ebx, r13d
0x18001052c  test    eax, eax
0x18001052e  jnz     loc_1800107EA
0x180010534  mov     eax, [r15+584h]
0x18001053b  mov     ecx, 5DCh
0x180010540  mov     rdx, [rdi+0B0h]; int
0x180010547  cmp     eax, ecx
0x180010549  mov     r8d, 0Ch; int
0x18001054f  cmova   eax, ecx
0x180010552  mov     ecx, ebx; int
0x180010554  mov     [rsp+0C0h+Src], rax; Src
0x180010559  mov     dword ptr [rsp+0C0h+Size], r14d; Size
0x18001055e  call    RasAuthAttributeInsert
0x180010563  add     ebx, r13d
0x180010566  test    eax, eax
0x180010568  jnz     loc_1800107EA
0x18001056e  mov     rax, [rdi+8]
0x180010572  test    dword ptr [rax+34h], 400h
0x180010579  jz      short loc_1800105A4
0x18001057b  mov     rdx, [rdi+0B0h]; int
0x180010582  mov     r8d, 0Dh; int
0x180010588  mov     [rsp+0C0h+Src], r13; Src
0x18001058d  mov     ecx, ebx; int
0x18001058f  mov     dword ptr [rsp+0C0h+Size], r14d; Size
0x180010594  call    RasAuthAttributeInsert
0x180010599  add     ebx, r13d
0x18001059c  test    eax, eax
0x18001059e  jnz     loc_1800107EA
0x1800105a4  lea     rcx, [rdi+600h]
0x1800105ab  cmp     [rcx], r12b
0x1800105ae  jz      short loc_1800105E4
0x1800105b0  mov     rax, rsi
0x1800105b3  inc     rax
0x1800105b6  cmp     [rcx+rax], r12b
0x1800105ba  jnz     short loc_1800105B3
0x1800105bc  mov     rdx, [rdi+0B0h]; int
0x1800105c3  mov     r8d, 13h; int
0x1800105c9  mov     [rsp+0C0h+Src], rcx; Src
0x1800105ce  mov     ecx, ebx; int
0x1800105d0  mov     dword ptr [rsp+0C0h+Size], eax; Size
0x1800105d4  call    RasAuthAttributeInsert
0x1800105d9  add     ebx, r13d
0x1800105dc  test    eax, eax
0x1800105de  jnz     loc_1800107EA
0x1800105e4  cmp     [rdi+50h], r12d
0x1800105e8  jbe     short loc_180010616
0x1800105ea  mov     eax, [rdi+50h]
0x1800105ed  mov     r8d, 1Bh; int
0x1800105f3  mov     rdx, [rdi+0B0h]; int
0x1800105fa  mov     ecx, ebx; int
0x1800105fc  mov     [rsp+0C0h+Src], rax; Src
0x180010601  mov     dword ptr [rsp+0C0h+Size], r14d; Size
0x180010606  call    RasAuthAttributeInsert
0x18001060b  add     ebx, r13d
0x18001060e  test    eax, eax
0x180010610  jnz     loc_1800107EA
0x180010616  cmp     [rdi+58h], r12d
  ... truncated ...
```
