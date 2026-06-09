# Performance::NtImagePathDecoder::CNtImagePathDecoderBase::GetFileName(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x18001468c`
- end: `0x18001486c`
- name: `?GetFileName@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEBA_NPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `480`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x1800121e8`
- `0x180014644`

## callees

- `0x180007cc4`
- `0x18000a5d4`
- `0x18000c3b0`
- `0x18001468c`
- `0x1800243c4`
- `0x1800243d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800146c2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800146c2`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180014739`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180014788`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180014739`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180014788`

## pseudocode

```c
char __fastcall Performance::NtImagePathDecoder::CNtImagePathDecoderBase::GetFileName(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  _QWORD *i; // rbx
  _QWORD *v7; // rcx
  _QWORD *v8; // r8
  __int64 v9; // r9
  __int64 j; // rbx
  const wchar_t *v11; // rcx
  _QWORD *v12; // r8
  wchar_t *v13; // rax
  unsigned __int16 *v15; // rsi

  for ( i = *(_QWORD **)a1; i != *(_QWORD **)(a1 + 8); i += 8 )
  {
    if ( i[3] <= 7u )
      v7 = i;
    else
      v7 = (_QWORD *)*i;
    if ( !(unsigned int)_o__wcsnicmp(v7, a2, i[2]) )
    {
      v8 = i + 4;
      v9 = a2 + 2LL * i[2];
      if ( i[7] > 7u )
        v8 = (_QWORD *)*v8;
      goto LABEL_10;
    }
  }
  for ( j = *(_QWORD *)(a1 + 24); j != *(_QWORD *)(a1 + 32); j += 32 )
  {
    if ( *(_QWORD *)(j + 24) <= 7u )
      v11 = (const wchar_t *)j;
    else
      v11 = *(const wchar_t **)j;
    if ( !wcsncmp_0(v11, (const wchar_t *)a2, *(unsigned int *)(j + 16)) )
      goto LABEL_35;
  }
  if ( !wcschr((const wchar_t *)a2, 0x5Cu) )
  {
    if ( *(_QWORD *)(a1 + 64) )
    {
      v12 = (_QWORD *)(a1 + 48);
      if ( *(_QWORD *)(a1 + 72) > 7u )
        v12 = (_QWORD *)*v12;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        a3,
        L"%ws\\drivers\\%ws",
        v12,
        a2);
      return 1;
    }
LABEL_45:
    ATL::AtlThrowImpl(-2147418113);
  }
  if ( *(_WORD *)a2 == 92
    && *(_WORD *)(a2 + 2) == 59
    && *(_WORD *)(a2 + 4)
    && *(_WORD *)(a2 + 6) == 58
    && (v13 = wcschr((const wchar_t *)(a2 + 8), 0x5Cu)) != 0 )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
      a3,
      L"\\%ws",
      v13);
  }
  else
  {
    if ( *(_WORD *)a2 && *(_WORD *)(a2 + 2) != 58 )
    {
      if ( !*(_QWORD *)(a1 + 96) )
        goto LABEL_45;
      if ( *(_WORD *)a2 != 92 )
      {
        v8 = (_QWORD *)(a1 + 80);
        if ( *(_QWORD *)(a1 + 104) > 7u )
          v8 = (_QWORD *)*v8;
        v9 = a2;
LABEL_10:
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
          a3,
          L"%ws%ws",
          v8,
          v9);
        return 1;
      }
      if ( !wcsncmp_0(
              (const wchar_t *)a2,
              `Performance::NtImagePathDecoder::CNtImagePathDecoderBase::GetFileName'::`35'::wchDevicePrefix,
              8u) )
      {
LABEL_35:
        ATL::CSimpleStringT<unsigned short,0>::SetString(a3, &qword_180029A30);
        return 0;
      }
      if ( wcscmp_0((const wchar_t *)a2, L"\\FI_UNKNOWN") )
      {
        v15 = (unsigned __int16 *)(a1 + 80);
        if ( *((_QWORD *)v15 + 3) > 7u )
          v15 = *(unsigned __int16 **)v15;
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
          a3,
          L"%wc:%ws",
          *v15,
          a2);
        return 1;
      }
    }
    ATL::CSimpleStringT<unsigned short,0>::SetString(a3, a2);
  }
  return 1;
}

```

## disassembly

```asm
0x18001468c  push    rbx
0x18001468e  push    rbp
0x18001468f  push    rsi
0x180014690  push    rdi
0x180014691  push    r14
0x180014693  sub     rsp, 20h
0x180014697  mov     rbx, [rcx]
0x18001469a  mov     rbp, r8
0x18001469d  mov     rdi, rdx
0x1800146a0  mov     rsi, rcx
0x1800146a3  xor     r14d, r14d
0x1800146a6  cmp     rbx, [rsi+8]
0x1800146aa  jz      short loc_1800146FC
0x1800146ac  cmp     qword ptr [rbx+18h], 7
0x1800146b1  jbe     short loc_1800146B8
0x1800146b3  mov     rcx, [rbx]
0x1800146b6  jmp     short loc_1800146BB
0x1800146b8  mov     rcx, rbx
0x1800146bb  mov     r8, [rbx+10h]
0x1800146bf  mov     rdx, rdi
0x1800146c2  call    cs:__imp__o__wcsnicmp
0x1800146c8  test    eax, eax
0x1800146ca  jz      short loc_1800146D2
0x1800146cc  add     rbx, 40h ; '@'
0x1800146d0  jmp     short loc_1800146A6
0x1800146d2  mov     rax, [rbx+10h]
0x1800146d6  lea     r8, [rbx+20h]
0x1800146da  cmp     qword ptr [r8+18h], 7
0x1800146df  lea     r9, [rdi+rax*2]
0x1800146e3  jbe     short loc_1800146E8
0x1800146e5  mov     r8, [r8]
0x1800146e8  lea     rdx, aWsWs; "%ws%ws"
0x1800146ef  mov     rcx, rbp
0x1800146f2  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x1800146f7  jmp     loc_180014854
0x1800146fc  mov     rbx, [rsi+18h]
0x180014700  cmp     rbx, [rsi+20h]
0x180014704  jz      short loc_18001472F
0x180014706  cmp     qword ptr [rbx+18h], 7
0x18001470b  jbe     short loc_180014712
0x18001470d  mov     rcx, [rbx]
0x180014710  jmp     short loc_180014715
0x180014712  mov     rcx, rbx; String1
0x180014715  mov     r8d, [rbx+10h]; MaxCount
0x180014719  mov     rdx, rdi; String2
0x18001471c  call    wcsncmp_0
0x180014721  test    eax, eax
0x180014723  jz      loc_1800147E7
0x180014729  add     rbx, 20h ; ' '
0x18001472d  jmp     short loc_180014700
0x18001472f  mov     ebx, 5Ch ; '\'
0x180014734  mov     rcx, rdi; Str
0x180014737  mov     edx, ebx; Ch
0x180014739  call    cs:__imp_wcschr
0x18001473f  test    rax, rax
0x180014742  jnz     short loc_180014768
0x180014744  cmp     [rsi+40h], r14
0x180014748  jz      loc_180014861
0x18001474e  lea     r8, [rsi+30h]
0x180014752  cmp     qword ptr [r8+18h], 7
0x180014757  jbe     short loc_18001475C
0x180014759  mov     r8, [r8]
0x18001475c  mov     r9, rdi
0x18001475f  lea     rdx, aWsDriversWs; "%ws\\drivers\\%ws"
0x180014766  jmp     short loc_1800146EF
0x180014768  cmp     [rdi], bx
0x18001476b  jnz     short loc_1800147AA
0x18001476d  cmp     word ptr [rdi+2], 3Bh ; ';'
0x180014772  jnz     short loc_1800147AA
0x180014774  cmp     [rdi+4], r14w
0x180014779  jz      short loc_1800147AA
0x18001477b  cmp     word ptr [rdi+6], 3Ah ; ':'
0x180014780  jnz     short loc_1800147AA
0x180014782  mov     edx, ebx; Ch
0x180014784  lea     rcx, [rdi+8]; Str
0x180014788  call    cs:__imp_wcschr
0x18001478e  test    rax, rax
0x180014791  jz      short loc_1800147AA
0x180014793  mov     r8, rax
0x180014796  lea     rdx, aWs; "\\%ws"
0x18001479d  mov     rcx, rbp
0x1800147a0  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x1800147a5  jmp     loc_180014854
0x1800147aa  cmp     [rdi], r14w
0x1800147ae  jz      loc_180014849
0x1800147b4  cmp     word ptr [rdi+2], 3Ah ; ':'
0x1800147b9  jz      loc_180014849
0x1800147bf  cmp     [rsi+60h], r14
0x1800147c3  jz      loc_180014861
0x1800147c9  cmp     [rdi], bx
0x1800147cc  jnz     short loc_180014833
0x1800147ce  mov     r8d, 8; MaxCount
0x1800147d4  lea     rdx, ?wchDevicePrefix@?CD@??GetFileName@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEBA_NPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z@4PAGA; "\\Device\\"
0x1800147db  mov     rcx, rdi; String1
0x1800147de  call    wcsncmp_0
0x1800147e3  test    eax, eax
0x1800147e5  jnz     short loc_1800147FA
0x1800147e7  lea     rdx, qword_180029A30
0x1800147ee  mov     rcx, rbp
0x1800147f1  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x1800147f6  xor     al, al
0x1800147f8  jmp     short loc_180014856
0x1800147fa  lea     rdx, aFiUnknown; "\\FI_UNKNOWN"
0x180014801  mov     rcx, rdi; String1
0x180014804  call    wcscmp_0
0x180014809  test    eax, eax
0x18001480b  jz      short loc_180014849
0x18001480d  add     rsi, 50h ; 'P'
0x180014811  cmp     qword ptr [rsi+18h], 7
0x180014816  jbe     short loc_18001481B
0x180014818  mov     rsi, [rsi]
0x18001481b  movzx   r8d, word ptr [rsi]
0x18001481f  lea     rdx, aWcWs; "%wc:%ws"
0x180014826  mov     r9, rdi
0x180014829  mov     rcx, rbp
0x18001482c  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180014831  jmp     short loc_180014854
0x180014833  lea     r8, [rsi+50h]
0x180014837  cmp     qword ptr [r8+18h], 7
0x18001483c  jbe     short loc_180014841
0x18001483e  mov     r8, [r8]
0x180014841  mov     r9, rdi
0x180014844  jmp     loc_1800146E8
0x180014849  mov     rdx, rdi
0x18001484c  mov     rcx, rbp
0x18001484f  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x180014854  mov     al, 1
0x180014856  add     rsp, 20h
0x18001485a  pop     r14
0x18001485c  pop     rdi
0x18001485d  pop     rsi
0x18001485e  pop     rbp
0x18001485f  pop     rbx
0x180014860  retn
0x180014861  mov     ecx, 8000FFFFh; int
0x180014866  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
