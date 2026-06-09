# CellState::PnnFromBytes(uchar const *,unsigned __int64)

- ea: `0x1800397ac`
- end: `0x180039ade`
- name: `?PnnFromBytes@CellState@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBE_K@Z`
- size: `818`
- prototype: `_QWORD *__fastcall(_QWORD *, _BYTE *, unsigned __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180038b00`

## callees

- `0x180004244`
- `0x18000e308`
- `0x180012d80`
- `0x180024e34`
- `0x1800397ac`
- `0x18003aaf8`
- `0x18003ac98`
- `0x18003b1e0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800399b1`
- `msvcrt!??3@YAXPEAX@Z` at `0x180039a59`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800399b1`
- `msvcrt!??3@YAXPEAX@Z` at `0x180039a59`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800398e4`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180039960`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800398e4`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180039960`

## string_xrefs

- `0x180039a81`: `onecoreuap\admin\prov\multivariant\handlers\common\cellstate.cpp`
- `0x180039aa4`: `onecoreuap\admin\prov\multivariant\handlers\common\cellstate.cpp`
- `0x180039ac1`: `onecoreuap\admin\prov\multivariant\handlers\common\cellstate.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall CellState::PnnFromBytes(_QWORD *a1, _BYTE *a2, unsigned __int64 a3)
{
  __int64 v5; // rdi
  char v6; // al
  unsigned int v7; // r12d
  CHAR v8; // r9
  unsigned int v9; // r10d
  __int64 v10; // rsi
  unsigned int v11; // r8d
  const CHAR *i; // r15
  int v13; // eax
  __int64 v14; // r8
  const char *v15; // r9
  int v16; // r14d
  unsigned __int64 v17; // rax
  unsigned __int64 v18; // rdi
  const char *v19; // r9
  char *v20; // r14
  int v21; // eax
  unsigned int v22; // r8d
  const char *v23; // r9
  CHAR *v24; // rcx
  int v25; // r8d
  char *v26; // rsi
  unsigned int v28; // eax
  int lpWideCharStr; // [rsp+20h] [rbp-50h]
  int lpWideCharStra; // [rsp+20h] [rbp-50h]
  int cchWideChar; // [rsp+28h] [rbp-48h]
  LPCCH lpMultiByteStr[2]; // [rsp+38h] [rbp-38h] BYREF
  __int64 v33; // [rsp+48h] [rbp-28h]
  LPWSTR v34[2]; // [rsp+50h] [rbp-20h] BYREF
  __int64 v35; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  char v37; // [rsp+B0h] [rbp+40h] BYREF

  if ( a3 < 3 )
    goto LABEL_30;
  if ( *a2 != 67 )
    goto LABEL_30;
  v5 = (unsigned int)(unsigned __int8)a2[1] - 1;
  if ( a3 < v5 + 3 )
    goto LABEL_30;
  v6 = a2[2];
  if ( (v6 & 0x70) == 0 )
  {
    v7 = 8 * (int)v5 / 7u - ((v6 & 7) == 7);
    v37 = 0;
    *(_OWORD *)lpMultiByteStr = 0;
    v33 = 0;
    std::vector<char>::_Construct_n(lpMultiByteStr, v7, &v37);
    v8 = 0;
    v9 = 0;
    LODWORD(v10) = 0;
    v11 = 0;
    for ( i = lpMultiByteStr[0]; v11 < (unsigned int)v5; ++v11 )
    {
      if ( (unsigned int)v10 >= v7 )
        break;
      i[(unsigned int)v10] = v8 | (a2[v11 + 3] << v9) & 0x7F;
      v10 = (unsigned int)(v10 + 1);
      if ( (_DWORD)v10 == v7 )
        break;
      v8 = (a2[v11 + 3] >> (7 - v9)) & 0x7F;
      v9 = (v9 + 1) % 7;
      if ( !v9 )
      {
        i[v10] = v8;
        LODWORD(v10) = v10 + 1;
        v8 = 0;
      }
    }
    v13 = MultiByteToWideChar(0xD6D8u, 0, i, v10, 0, 0);
    if ( !v13 )
      wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x1AE, v14, v15);
    v16 = v13 + 1;
    v17 = v13 + 2147483649LL;
    v18 = -1;
    if ( v17 > 0xFFFFFFFF )
      v16 = -1;
    v19 = v17 > 0xFFFFFFFF ? (const char *)0x80070216LL : 0LL;
    if ( v17 > 0xFFFFFFFF )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1AF,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\cellstate.cpp",
        v19,
        lpWideCharStra);
    *(_OWORD *)v34 = 0;
    v35 = 0;
    std::vector<unsigned short>::resize(v34, v16, v14, v19);
    cchWideChar = v16;
    v20 = (char *)v34[0];
    v21 = MultiByteToWideChar(0xD6D8u, 0, i, v10, v34[0], cchWideChar);
    if ( !v21 )
      wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x1B5, v22, v23);
    *(_WORD *)&v20[2 * v21] = 0;
    a1[3] = 7;
    a1[2] = 0;
    *(_WORD *)a1 = 0;
    if ( *(_WORD *)v20 )
    {
      do
        ++v18;
      while ( *(_WORD *)&v20[2 * v18] );
    }
    else
    {
      v18 = 0;
    }
    std::wstring::assign(a1, v20, v18);
    operator delete(v20);
    if ( i )
    {
      v24 = (CHAR *)i;
LABEL_27:
      operator delete(v24);
      return a1;
    }
    return a1;
  }
  if ( (v6 & 0x70) != 0x10 )
  {
LABEL_30:
    v28 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C9,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\cellstate.cpp",
      (const char *)v28,
      lpWideCharStr);
  }
  if ( (v5 & 1) != 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1BC,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\cellstate.cpp",
      (const char *)0x80070057LL,
      lpWideCharStr);
  *(_OWORD *)lpMultiByteStr = 0;
  v33 = 0;
  std::vector<unsigned char>::resize(lpMultiByteStr, v5);
  v25 = 0;
  v26 = (char *)lpMultiByteStr[0];
  if ( (unsigned int)v5 > 1 )
  {
    do
    {
      v26[v25] = a2[v25 + 1 + 3];
      v26[v25 + 1] = a2[v25 + 3];
      v25 += 2;
    }
    while ( v25 + 1 < (unsigned int)v5 );
  }
  a1[3] = 7;
  a1[2] = 0;
  *(_WORD *)a1 = 0;
  std::wstring::assign(a1, v26, (unsigned __int64)(lpMultiByteStr[1] - (LPCCH)v26) >> 1);
  if ( v26 )
  {
    v24 = v26;
    goto LABEL_27;
  }
  return a1;
}

```

## disassembly

```asm
0x1800397ac  mov     [rsp-28h+arg_0], rbx
0x1800397b1  mov     [rsp-28h+arg_8], rsi
0x1800397b6  push    rbp
0x1800397b7  push    rdi
0x1800397b8  push    r12
0x1800397ba  push    r14
0x1800397bc  push    r15
0x1800397be  mov     rbp, rsp
0x1800397c1  sub     rsp, 70h
0x1800397c5  mov     r14, rdx
0x1800397c8  mov     rbx, rcx
0x1800397cb  xor     r15d, r15d
0x1800397ce  cmp     r8, 3
0x1800397d2  jb      loc_180039A93
0x1800397d8  cmp     byte ptr [rdx], 43h ; 'C'
0x1800397db  jnz     loc_180039A93
0x1800397e1  movzx   edi, byte ptr [rdx+1]
0x1800397e5  dec     edi
0x1800397e7  mov     edx, edi
0x1800397e9  lea     rax, [rdi+3]
0x1800397ed  cmp     r8, rax
0x1800397f0  jb      loc_180039A93
0x1800397f6  movzx   eax, byte ptr [r14+2]
0x1800397fb  test    al, 70h
0x1800397fd  jnz     loc_1800399C9
0x180039803  and     al, 7
0x180039805  mov     ecx, r15d
0x180039808  cmp     al, 7
0x18003980a  setz    cl
0x18003980d  lea     r12d, ds:0[rdi*8]
0x180039815  mov     eax, 24924925h
0x18003981a  mul     r12d
0x18003981d  sub     r12d, edx
0x180039820  shr     r12d, 1
0x180039823  add     r12d, edx
0x180039826  shr     r12d, 2
0x18003982a  sub     r12d, ecx
0x18003982d  mov     [rbp+arg_10], r15b
0x180039831  xorps   xmm0, xmm0
0x180039834  movdqu  xmmword ptr [rbp+lpMultiByteStr], xmm0
0x180039839  mov     [rbp+var_28], r15
0x18003983d  mov     edx, r12d
0x180039840  lea     r8, [rbp+arg_10]
0x180039844  lea     rcx, [rbp+lpMultiByteStr]
0x180039848  call    ?_Construct_n@?$vector@DV?$allocator@D@std@@@std@@QEAAX_KPEBD@Z; std::vector<char>::_Construct_n(unsigned __int64,char const *)
0x18003984d  nop
0x18003984e  mov     r9b, r15b
0x180039851  mov     r10d, r15d
0x180039854  mov     esi, r15d
0x180039857  mov     r8d, r15d
0x18003985a  mov     r15, [rbp+lpMultiByteStr]
0x18003985e  test    edi, edi
0x180039860  jz      short loc_1800398CA
0x180039862  cmp     esi, r12d
0x180039865  jnb     short loc_1800398CA
0x180039867  mov     r11d, r8d
0x18003986a  mov     edx, esi
0x18003986c  mov     ecx, r10d
0x18003986f  mov     al, [r11+r14+3]
0x180039874  shl     al, cl
0x180039876  and     al, 7Fh
0x180039878  or      al, r9b
0x18003987b  mov     [r15+rdx], al
0x18003987f  inc     esi
0x180039881  cmp     esi, r12d
0x180039884  jz      short loc_1800398CA
0x180039886  mov     ecx, 7
0x18003988b  sub     cl, r10b
0x18003988e  mov     r9b, [r11+r14+3]
0x180039893  shr     r9b, cl
0x180039896  and     r9b, 7Fh
0x18003989a  inc     r10d
0x18003989d  mov     eax, 24924925h
0x1800398a2  mul     r10d
0x1800398a5  mov     eax, r10d
0x1800398a8  sub     eax, edx
0x1800398aa  shr     eax, 1
0x1800398ac  add     eax, edx
0x1800398ae  shr     eax, 2
0x1800398b1  imul    eax, 7
0x1800398b4  sub     r10d, eax
0x1800398b7  jnz     short loc_1800398C2
0x1800398b9  mov     [r15+rsi], r9b
0x1800398bd  inc     esi
0x1800398bf  xor     r9b, r9b
0x1800398c2  inc     r8d
0x1800398c5  cmp     r8d, edi
0x1800398c8  jb      short loc_180039862
0x1800398ca  xor     r12d, r12d
0x1800398cd  mov     [rsp+70h+cchWideChar], r12d; cchWideChar
0x1800398d2  mov     [rsp+70h+lpWideCharStr], r12; int
0x1800398d7  mov     r9d, esi; cbMultiByte
0x1800398da  mov     r8, r15; lpMultiByteStr
0x1800398dd  xor     edx, edx; dwFlags
0x1800398df  mov     ecx, 0D6D8h; CodePage
0x1800398e4  call    cs:__imp_MultiByteToWideChar
0x1800398ea  mov     rcx, [rbp+28h]; this
0x1800398ee  test    eax, eax
0x1800398f0  jz      loc_180039AB6
0x1800398f6  movsxd  r14, eax
0x1800398f9  inc     r14
0x1800398fc  mov     eax, 80000000h
0x180039901  add     rax, r14
0x180039904  mov     edx, 0FFFFFFFFh
0x180039909  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18003990d  cmp     rdx, rax
0x180039910  jnb     short loc_180039915
0x180039912  mov     r14d, edi
0x180039915  sbb     r9d, r9d
0x180039918  and     r9d, 80070216h; char *
0x18003991f  mov     rcx, [rbp+28h]; this
0x180039923  cmp     rax, rdx
0x180039926  ja      loc_180039AC1
0x18003992c  xorps   xmm0, xmm0
0x18003992f  movdqu  xmmword ptr [rbp+var_20], xmm0
0x180039934  mov     [rbp+var_10], r12
0x180039938  movsxd  rdx, r14d
0x18003993b  lea     rcx, [rbp+var_20]
0x18003993f  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180039944  nop
0x180039945  mov     [rsp+70h+cchWideChar], r14d; cchWideChar
0x18003994a  mov     r14, [rbp+var_20]
0x18003994e  mov     [rsp+70h+lpWideCharStr], r14; lpWideCharStr
0x180039953  mov     r9d, esi; cbMultiByte
0x180039956  mov     r8, r15; lpMultiByteStr
0x180039959  xor     edx, edx; dwFlags
0x18003995b  mov     ecx, 0D6D8h; CodePage
0x180039960  call    cs:__imp_MultiByteToWideChar
0x180039966  mov     rcx, [rbp+28h]; this
0x18003996a  test    eax, eax
0x18003996c  jz      loc_180039AD3
0x180039972  movsxd  rcx, eax
0x180039975  mov     [r14+rcx*2], r12w
0x18003997a  mov     qword ptr [rbx+18h], 7
0x180039982  mov     [rbx+10h], r12
0x180039986  mov     [rbx], r12w
0x18003998a  cmp     [r14], r12w
0x18003998e  jnz     short loc_180039995
0x180039990  mov     rdi, r12
0x180039993  jmp     short loc_18003999F
0x180039995  inc     rdi
0x180039998  cmp     [r14+rdi*2], r12w
0x18003999d  jnz     short loc_180039995
0x18003999f  mov     r8, rdi
0x1800399a2  mov     rdx, r14; Src
0x1800399a5  mov     rcx, rbx; void *
0x1800399a8  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800399ad  nop
0x1800399ae  mov     rcx, r14
0x1800399b1  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800399b7  nop
0x1800399b8  test    r15, r15
0x1800399bb  jz      loc_180039A5F
0x1800399c1  mov     rcx, r15
0x1800399c4  jmp     loc_180039A59
0x1800399c9  and     al, 70h
0x1800399cb  cmp     al, 10h
0x1800399cd  jnz     loc_180039A93
0x1800399d3  mov     rcx, [rbp+28h]; this
0x1800399d7  mov     al, dil
0x1800399da  not     al
0x1800399dc  test    al, 1
0x1800399de  jz      loc_180039A7B
0x1800399e4  xorps   xmm0, xmm0
0x1800399e7  movdqu  xmmword ptr [rbp+lpMultiByteStr], xmm0
0x1800399ec  mov     [rbp+var_28], r15
0x1800399f0  lea     rcx, [rbp+lpMultiByteStr]
0x1800399f4  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x1800399f9  nop
0x1800399fa  mov     r8d, r15d
0x1800399fd  mov     rsi, [rbp+lpMultiByteStr]
0x180039a01  cmp     edi, 1
0x180039a04  jbe     short loc_180039A2B
0x180039a06  lea     eax, [r8+1]
0x180039a0a  mov     edx, eax
0x180039a0c  mov     ecx, r8d
0x180039a0f  mov     al, [r14+rax+3]
0x180039a14  mov     [rsi+rcx], al
0x180039a17  mov     al, [r14+rcx+3]
0x180039a1c  mov     [rsi+rdx], al
0x180039a1f  add     r8d, 2
0x180039a23  lea     eax, [r8+1]
0x180039a27  cmp     eax, edi
0x180039a29  jb      short loc_180039A06
0x180039a2b  mov     qword ptr [rbx+18h], 7
0x180039a33  mov     [rbx+10h], r15
0x180039a37  mov     [rbx], r15w
0x180039a3b  mov     r8, [rbp+lpMultiByteStr+8]
0x180039a3f  sub     r8, rsi
0x180039a42  shr     r8, 1
0x180039a45  mov     rdx, rsi; Src
0x180039a48  mov     rcx, rbx; void *
0x180039a4b  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180039a50  nop
0x180039a51  test    rsi, rsi
0x180039a54  jz      short loc_180039A5F
0x180039a56  mov     rcx, rsi
0x180039a59  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180039a5f  mov     rax, rbx
0x180039a62  lea     r11, [rsp+70h+var_s0]
0x180039a67  mov     rbx, [r11+30h]
0x180039a6b  mov     rsi, [r11+38h]
0x180039a6f  mov     rsp, r11
0x180039a72  pop     r15
0x180039a74  pop     r14
0x180039a76  pop     r12
0x180039a78  pop     rdi
0x180039a79  pop     rbp
0x180039a7a  retn
0x180039a7b  mov     r9d, 80070057h; char *
0x180039a81  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180039a88  mov     edx, 1BCh; void *
0x180039a8d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180039a93  mov     ecx, 80070057h
0x180039a98  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180039a9d  mov     r9d, eax; char *
0x180039aa0  mov     rcx, [rbp+28h]; this
0x180039aa4  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180039aab  mov     edx, 1C9h; void *
0x180039ab0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180039ab6  mov     edx, 1AEh; void *
0x180039abb  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180039ac1  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180039ac8  mov     edx, 1AFh; void *
0x180039acd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180039ad3  mov     edx, 1B5h; void *
0x180039ad8  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
