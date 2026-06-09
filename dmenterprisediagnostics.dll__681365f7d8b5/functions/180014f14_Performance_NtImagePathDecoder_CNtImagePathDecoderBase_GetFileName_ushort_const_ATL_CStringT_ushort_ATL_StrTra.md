# Performance::NtImagePathDecoder::CNtImagePathDecoderBase::GetFileName(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x180014f14`
- end: `0x180015107`
- name: `?GetFileName@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEBA_NPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `499`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x1800129cc`
- `0x180014ecc`

## callees

- `0x180008044`
- `0x18000ab4c`
- `0x18000c980`
- `0x180014f14`
- `0x180025284`
- `0x180025290`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180014f4a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180014f4a`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180014fc7`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18001501c`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180014fc7`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18001501c`

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
        ATL::CSimpleStringT<unsigned short,0>::SetString(a3, &qword_18002AA30);
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
0x180014f14  push    rbx
0x180014f16  push    rbp
0x180014f17  push    rsi
0x180014f18  push    rdi
0x180014f19  push    r14
0x180014f1b  sub     rsp, 20h
0x180014f1f  mov     rbx, [rcx]
0x180014f22  mov     rbp, r8
0x180014f25  mov     rdi, rdx
0x180014f28  mov     rsi, rcx
0x180014f2b  xor     r14d, r14d
0x180014f2e  cmp     rbx, [rsi+8]
0x180014f32  jz      short loc_180014F8A
0x180014f34  cmp     qword ptr [rbx+18h], 7
0x180014f39  jbe     short loc_180014F40
0x180014f3b  mov     rcx, [rbx]
0x180014f3e  jmp     short loc_180014F43
0x180014f40  mov     rcx, rbx
0x180014f43  mov     r8, [rbx+10h]
0x180014f47  mov     rdx, rdi
0x180014f4a  call    cs:__imp__o__wcsnicmp
0x180014f51  nop     dword ptr [rax+rax+00h]
0x180014f56  test    eax, eax
0x180014f58  jz      short loc_180014F60
0x180014f5a  add     rbx, 40h ; '@'
0x180014f5e  jmp     short loc_180014F2E
0x180014f60  mov     rax, [rbx+10h]
0x180014f64  lea     r8, [rbx+20h]
0x180014f68  cmp     qword ptr [r8+18h], 7
0x180014f6d  lea     r9, [rdi+rax*2]
0x180014f71  jbe     short loc_180014F76
0x180014f73  mov     r8, [r8]
0x180014f76  lea     rdx, aWsWs; "%ws%ws"
0x180014f7d  mov     rcx, rbp
0x180014f80  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180014f85  jmp     loc_1800150EE
0x180014f8a  mov     rbx, [rsi+18h]
0x180014f8e  cmp     rbx, [rsi+20h]
0x180014f92  jz      short loc_180014FBD
0x180014f94  cmp     qword ptr [rbx+18h], 7
0x180014f99  jbe     short loc_180014FA0
0x180014f9b  mov     rcx, [rbx]
0x180014f9e  jmp     short loc_180014FA3
0x180014fa0  mov     rcx, rbx; String1
0x180014fa3  mov     r8d, [rbx+10h]; MaxCount
0x180014fa7  mov     rdx, rdi; String2
0x180014faa  call    wcsncmp_0
0x180014faf  test    eax, eax
0x180014fb1  jz      loc_180015081
0x180014fb7  add     rbx, 20h ; ' '
0x180014fbb  jmp     short loc_180014F8E
0x180014fbd  mov     ebx, 5Ch ; '\'
0x180014fc2  mov     rcx, rdi; Str
0x180014fc5  mov     edx, ebx; Ch
0x180014fc7  call    cs:__imp_wcschr
0x180014fce  nop     dword ptr [rax+rax+00h]
0x180014fd3  test    rax, rax
0x180014fd6  jnz     short loc_180014FFC
0x180014fd8  cmp     [rsi+40h], r14
0x180014fdc  jz      loc_1800150FC
0x180014fe2  lea     r8, [rsi+30h]
0x180014fe6  cmp     qword ptr [r8+18h], 7
0x180014feb  jbe     short loc_180014FF0
0x180014fed  mov     r8, [r8]
0x180014ff0  mov     r9, rdi
0x180014ff3  lea     rdx, aWsDriversWs; "%ws\\drivers\\%ws"
0x180014ffa  jmp     short loc_180014F7D
0x180014ffc  cmp     [rdi], bx
0x180014fff  jnz     short loc_180015044
0x180015001  cmp     word ptr [rdi+2], 3Bh ; ';'
0x180015006  jnz     short loc_180015044
0x180015008  cmp     [rdi+4], r14w
0x18001500d  jz      short loc_180015044
0x18001500f  cmp     word ptr [rdi+6], 3Ah ; ':'
0x180015014  jnz     short loc_180015044
0x180015016  mov     edx, ebx; Ch
0x180015018  lea     rcx, [rdi+8]; Str
0x18001501c  call    cs:__imp_wcschr
0x180015023  nop     dword ptr [rax+rax+00h]
0x180015028  test    rax, rax
0x18001502b  jz      short loc_180015044
0x18001502d  mov     r8, rax
0x180015030  lea     rdx, aWs; "\\%ws"
0x180015037  mov     rcx, rbp
0x18001503a  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18001503f  jmp     loc_1800150EE
0x180015044  cmp     [rdi], r14w
0x180015048  jz      loc_1800150E3
0x18001504e  cmp     word ptr [rdi+2], 3Ah ; ':'
0x180015053  jz      loc_1800150E3
0x180015059  cmp     [rsi+60h], r14
0x18001505d  jz      loc_1800150FC
0x180015063  cmp     [rdi], bx
0x180015066  jnz     short loc_1800150CD
0x180015068  mov     r8d, 8; MaxCount
0x18001506e  lea     rdx, ?wchDevicePrefix@?CD@??GetFileName@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEBA_NPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z@4PAGA; "\\Device\\"
0x180015075  mov     rcx, rdi; String1
0x180015078  call    wcsncmp_0
0x18001507d  test    eax, eax
0x18001507f  jnz     short loc_180015094
0x180015081  lea     rdx, qword_18002AA30
0x180015088  mov     rcx, rbp
0x18001508b  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x180015090  xor     al, al
0x180015092  jmp     short loc_1800150F0
0x180015094  lea     rdx, aFiUnknown; "\\FI_UNKNOWN"
0x18001509b  mov     rcx, rdi; String1
0x18001509e  call    wcscmp_0
0x1800150a3  test    eax, eax
0x1800150a5  jz      short loc_1800150E3
0x1800150a7  add     rsi, 50h ; 'P'
0x1800150ab  cmp     qword ptr [rsi+18h], 7
0x1800150b0  jbe     short loc_1800150B5
0x1800150b2  mov     rsi, [rsi]
0x1800150b5  movzx   r8d, word ptr [rsi]
0x1800150b9  lea     rdx, aWcWs; "%wc:%ws"
0x1800150c0  mov     r9, rdi
0x1800150c3  mov     rcx, rbp
0x1800150c6  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x1800150cb  jmp     short loc_1800150EE
0x1800150cd  lea     r8, [rsi+50h]
0x1800150d1  cmp     qword ptr [r8+18h], 7
0x1800150d6  jbe     short loc_1800150DB
0x1800150d8  mov     r8, [r8]
0x1800150db  mov     r9, rdi
0x1800150de  jmp     loc_180014F76
0x1800150e3  mov     rdx, rdi
0x1800150e6  mov     rcx, rbp
0x1800150e9  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x1800150ee  mov     al, 1
0x1800150f0  add     rsp, 20h
0x1800150f4  pop     r14
0x1800150f6  pop     rdi
0x1800150f7  pop     rsi
0x1800150f8  pop     rbp
0x1800150f9  pop     rbx
0x1800150fa  retn
0x1800150fc  mov     ecx, 8000FFFFh; int
0x180015101  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
