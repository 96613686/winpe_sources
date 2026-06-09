# ReadWaveHeader

- ea: `0x180003208`
- end: `0x1800033cd`
- name: `ReadWaveHeader`
- size: `453`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180004318`

## callees

- `0x180003208`
- `0x180003514`
- `0x180005c60`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800032a4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800032a4`
- `WINMM!mmioDescend` at `0x180003252`
- `WINMM!mmioDescend` at `0x180003284`
- `WINMM!mmioDescend` at `0x180003366`
- `WINMM!mmioDescend` at `0x180003252`
- `WINMM!mmioDescend` at `0x180003284`
- `WINMM!mmioDescend` at `0x180003366`
- `WINMM!mmioAscend` at `0x180003341`
- `WINMM!mmioAscend` at `0x180003341`
- `WINMM!mmioRead` at `0x1800032d0`
- `WINMM!mmioRead` at `0x1800032d0`

## pseudocode

```c
__int64 __fastcall ReadWaveHeader(__int64 a1)
{
  HMMIO v2; // rcx
  MMRESULT v3; // eax
  HMMIO v4; // rcx
  SIZE_T cksize; // rdx
  char *v6; // rax
  LONG v7; // eax
  __int64 v8; // rdx
  HMMIO v9; // rcx
  __int64 v10; // rcx
  __int64 result; // rax
  struct _MMCKINFO v12; // [rsp+20h] [rbp-48h] BYREF
  struct _MMCKINFO pmmcki; // [rsp+38h] [rbp-30h] BYREF

  pmmcki.fccType = 1163280727;
  *(_QWORD *)&pmmcki.ckid = 0;
  v2 = *(HMMIO *)(a1 + 80);
  *(_QWORD *)&pmmcki.dwDataOffset = 0;
  memset(&v12, 0, sizeof(v12));
  v3 = mmioDescend(v2, &pmmcki, 0, 0x20u);
  if ( !v3 )
  {
    v4 = *(HMMIO *)(a1 + 80);
    v12.ckid = 544501094;
    v3 = mmioDescend(v4, &v12, &pmmcki, 0x10u);
    if ( !v3 )
    {
      if ( v12.cksize < 0x10 )
        goto LABEL_18;
      cksize = v12.cksize;
      *(_DWORD *)(a1 + 160) = v12.cksize;
      v6 = (char *)LocalAlloc(0x40u, cksize);
      *(_QWORD *)(a1 + 168) = v6;
      if ( !v6 )
      {
        *(_DWORD *)(a1 + 140) = 264;
        return 0;
      }
      v7 = mmioRead(*(HMMIO *)(a1 + 80), v6, v12.cksize);
      if ( v7 != v12.cksize )
      {
        *(_DWORD *)(a1 + 140) = 348;
        return 0;
      }
      v8 = *(_QWORD *)(a1 + 168);
      if ( *(_WORD *)v8 != 1
        && (v12.cksize < 0x12 || v12.cksize < (unsigned __int64)*(unsigned __int16 *)(v8 + 16) + 18) )
      {
LABEL_18:
        *(_DWORD *)(a1 + 140) = 296;
        return 0;
      }
      if ( *(_DWORD *)(v8 + 8) > 0x5F5E100u )
        *(_DWORD *)(v8 + 8) = 100000000;
      if ( !*(_WORD *)(*(_QWORD *)(a1 + 168) + 12LL) )
        return 0;
      v3 = mmioAscend(*(HMMIO *)(a1 + 80), &v12, 0);
      if ( !v3 )
      {
        v9 = *(HMMIO *)(a1 + 80);
        v12.ckid = 1635017060;
        v3 = mmioDescend(v9, &v12, &pmmcki, 0x10u);
        if ( !v3 )
        {
          *(_DWORD *)(a1 + 76) = v12.cksize;
          *(_DWORD *)(a1 + 112) = v12.dwDataOffset;
          v10 = *(_QWORD *)(a1 + 168);
          result = 1;
          *(_DWORD *)(a1 + 148) = *(_DWORD *)(v10 + 8)
                                + *(unsigned __int16 *)(v10 + 12)
                                - 1
                                - (*(_DWORD *)(v10 + 8) + (unsigned int)*(unsigned __int16 *)(v10 + 12) - 1)
                                % *(unsigned __int16 *)(v10 + 12);
          return result;
        }
      }
    }
  }
  SetMMIOError(a1, v3);
  return 0;
}

```

## disassembly

```asm
0x180003208  push    rbp
0x18000320a  push    rbx
0x18000320b  push    rdi
0x18000320c  push    r14
0x18000320e  mov     rbp, rsp
0x180003211  sub     rsp, 68h
0x180003215  mov     rax, cs:__security_cookie
0x18000321c  xor     rax, rsp
0x18000321f  mov     [rbp+var_18], rax
0x180003223  xor     edi, edi
0x180003225  mov     [rbp+pmmcki.fccType], 45564157h
0x18000322c  mov     rbx, rcx
0x18000322f  mov     qword ptr [rbp+pmmcki.ckid], rdi
0x180003233  mov     rcx, [rcx+50h]; hmmio
0x180003237  lea     rdx, [rbp+pmmcki]; pmmcki
0x18000323b  xorps   xmm0, xmm0
0x18000323e  mov     qword ptr [rbp+pmmcki.dwDataOffset], rdi
0x180003242  xor     eax, eax
0x180003244  lea     r9d, [rdi+20h]; fuDescend
0x180003248  xor     r8d, r8d; pmmckiParent
0x18000324b  mov     [rbp+var_48.dwFlags], eax
0x18000324e  movups  xmmword ptr [rbp+var_48.ckid], xmm0
0x180003252  call    cs:__imp_mmioDescend
0x180003258  test    eax, eax
0x18000325a  jz      short loc_18000326B
0x18000325c  mov     edx, eax
0x18000325e  mov     rcx, rbx
0x180003261  call    SetMMIOError
0x180003266  jmp     loc_1800033B5
0x18000326b  mov     rcx, [rbx+50h]; hmmio
0x18000326f  lea     r8, [rbp+pmmcki]; pmmckiParent
0x180003273  mov     r9d, 10h; fuDescend
0x180003279  mov     [rbp+var_48.ckid], 20746D66h
0x180003280  lea     rdx, [rbp+var_48]; pmmcki
0x180003284  call    cs:__imp_mmioDescend
0x18000328a  test    eax, eax
0x18000328c  jnz     short loc_18000325C
0x18000328e  cmp     [rbp+var_48.cksize], 10h
0x180003292  jb      loc_1800033AB
0x180003298  mov     edx, [rbp+var_48.cksize]; uBytes
0x18000329b  lea     ecx, [rax+40h]; uFlags
0x18000329e  mov     [rbx+0A0h], edx
0x1800032a4  call    cs:__imp_LocalAlloc
0x1800032aa  mov     [rbx+0A8h], rax
0x1800032b1  test    rax, rax
0x1800032b4  jnz     short loc_1800032C5
0x1800032b6  mov     dword ptr [rbx+8Ch], 108h
0x1800032c0  jmp     loc_1800033B5
0x1800032c5  mov     r8d, [rbp+var_48.cksize]; cch
0x1800032c9  mov     rdx, rax; pch
0x1800032cc  mov     rcx, [rbx+50h]; hmmio
0x1800032d0  call    cs:__imp_mmioRead
0x1800032d6  mov     r8d, [rbp+var_48.cksize]
0x1800032da  cmp     eax, r8d
0x1800032dd  jz      short loc_1800032EE
0x1800032df  mov     dword ptr [rbx+8Ch], 15Ch
0x1800032e9  jmp     loc_1800033B5
0x1800032ee  mov     rdx, [rbx+0A8h]
0x1800032f5  mov     r14d, 1
0x1800032fb  cmp     [rdx], r14w
0x1800032ff  jz      short loc_18000331C
0x180003301  cmp     r8d, 12h
0x180003305  jb      loc_1800033AB
0x18000330b  movzx   ecx, word ptr [rdx+10h]
0x18000330f  add     rcx, 12h
0x180003313  cmp     r8, rcx
0x180003316  jb      loc_1800033AB
0x18000331c  mov     eax, 5F5E100h
0x180003321  cmp     [rdx+8], eax
0x180003324  jbe     short loc_180003329
0x180003326  mov     [rdx+8], eax
0x180003329  mov     rax, [rbx+0A8h]
0x180003330  cmp     [rax+0Ch], di
0x180003334  jz      short loc_1800033B5
0x180003336  mov     rcx, [rbx+50h]; hmmio
0x18000333a  lea     rdx, [rbp+var_48]; pmmcki
0x18000333e  xor     r8d, r8d; fuAscend
0x180003341  call    cs:__imp_mmioAscend
0x180003347  test    eax, eax
0x180003349  jnz     loc_18000325C
0x18000334f  mov     rcx, [rbx+50h]; hmmio
0x180003353  lea     r9d, [rax+10h]; fuDescend
0x180003357  lea     r8, [rbp+pmmcki]; pmmckiParent
0x18000335b  mov     [rbp+var_48.ckid], 61746164h
0x180003362  lea     rdx, [rbp+var_48]; pmmcki
0x180003366  call    cs:__imp_mmioDescend
0x18000336c  test    eax, eax
0x18000336e  jnz     loc_18000325C
0x180003374  mov     ecx, [rbp+var_48.cksize]
0x180003377  xor     edx, edx
0x180003379  mov     [rbx+4Ch], ecx
0x18000337c  mov     ecx, [rbp+var_48.dwDataOffset]
0x18000337f  mov     [rbx+70h], ecx
0x180003382  mov     rcx, [rbx+0A8h]
0x180003389  movzx   r8d, word ptr [rcx+0Ch]
0x18000338e  lea     r9d, [r8-1]
0x180003392  add     r9d, [rcx+8]
0x180003396  mov     eax, r9d
0x180003399  div     r8d
0x18000339c  mov     eax, r14d
0x18000339f  sub     r9d, edx
0x1800033a2  mov     [rbx+94h], r9d
0x1800033a9  jmp     short loc_1800033B7
0x1800033ab  mov     dword ptr [rbx+8Ch], 128h
0x1800033b5  xor     eax, eax
0x1800033b7  mov     rcx, [rbp+var_18]
0x1800033bb  xor     rcx, rsp; StackCookie
0x1800033be  call    __security_check_cookie
0x1800033c3  add     rsp, 68h
0x1800033c7  pop     r14
0x1800033c9  pop     rdi
0x1800033ca  pop     rbx
0x1800033cb  pop     rbp
0x1800033cc  retn
```
