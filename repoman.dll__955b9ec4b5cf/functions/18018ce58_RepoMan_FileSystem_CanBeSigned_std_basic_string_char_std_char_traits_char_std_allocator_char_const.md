# RepoMan::FileSystem::CanBeSigned(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x18018ce58`
- end: `0x18018d136`
- name: `?CanBeSigned@FileSystem@RepoMan@@YA_NAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `734`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18018d138`
- `0x18018da80`

## callees

- `0x180008574`
- `0x18018ce58`
- `0x18019a840`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x18018d0cd`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18018d0cd`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18018d0fc`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18018d0fc`
- `api-ms-win-crt-string-l1-1-0!tolower` at `0x18018d075`
- `api-ms-win-crt-string-l1-1-0!tolower` at `0x18018d083`
- `api-ms-win-crt-string-l1-1-0!tolower` at `0x18018d075`
- `api-ms-win-crt-string-l1-1-0!tolower` at `0x18018d083`

## string_xrefs

- `0x18018cf05`: `.idx_dll`
- `0x18018cf89`: `.trx_dll`
- `0x18018cfec`: `.msix`

## pseudocode

```c
char __fastcall RepoMan::FileSystem::CanBeSigned(_QWORD *a1)
{
  const char *v2; // rdx
  char *v3; // r12
  char v4; // r14
  size_t v5; // r8
  unsigned __int8 *v6; // rbx
  unsigned __int64 v7; // rax
  unsigned __int64 v8; // rcx
  _QWORD *v9; // r8
  _QWORD *v10; // rdx
  unsigned __int8 *v11; // rsi
  unsigned __int8 *v12; // r13
  int v13; // edi
  int v14; // ecx
  char v15; // bl
  void *v16; // rcx
  _QWORD v18[33]; // [rsp+30h] [rbp-D0h] BYREF
  char v19; // [rsp+138h] [rbp+38h] BYREF
  __int128 v20; // [rsp+148h] [rbp+48h] BYREF
  __int128 v21; // [rsp+158h] [rbp+58h]

  v2 = ".add";
  v18[0] = ".add";
  v18[1] = ".cab";
  v18[2] = ".cgl";
  v18[3] = ".cnv";
  v18[4] = ".cpl";
  v18[5] = ".dic";
  v18[6] = ".dll";
  v18[7] = ".exe";
  v18[8] = ".fae";
  v18[9] = ".flt";
  v18[10] = ".idx_dll";
  v18[11] = ".ime";
  v18[12] = ".mdl";
  v18[13] = ".msi";
  v18[14] = ".mui";
  v18[15] = ".ocx";
  v18[16] = ".odf";
  v18[17] = ".olb";
  v18[18] = ".pdl";
  v18[19] = ".rpl";
  v18[20] = ".sam";
  v18[21] = ".tll";
  v18[22] = ".trx_dll";
  v18[23] = ".upl";
  v18[24] = ".vsl";
  v18[25] = ".wll";
  v18[26] = ".xll";
  v18[27] = ".xsn";
  v18[28] = ".cat";
  v18[29] = ".rll";
  v18[30] = ".appx";
  v18[31] = ".msix";
  v18[32] = ".appxbundle";
  v3 = (char *)v18;
  v4 = 0;
  while ( 1 )
  {
    v20 = 0;
    v21 = 0;
    v5 = -1;
    do
      ++v5;
    while ( v2[v5] );
    std::string::_Construct<1,char const *>(&v20, v2, v5);
    v6 = (unsigned __int8 *)&v20;
    v7 = *((_QWORD *)&v21 + 1);
    if ( *((_QWORD *)&v21 + 1) > 0xFu )
      v6 = (unsigned __int8 *)v20;
    v8 = a1[2];
    if ( v8 >= (unsigned __int64)v21 )
    {
      v9 = a1;
      if ( a1[3] > 0xFu )
        v9 = (_QWORD *)*a1;
      v10 = a1;
      if ( a1[3] > 0xFu )
        v10 = (_QWORD *)*a1;
      v11 = (unsigned __int8 *)v10 + v8 - v21;
      v12 = (unsigned __int8 *)v9 + v8;
      if ( v11 == (unsigned __int8 *)((char *)v9 + v8) )
      {
LABEL_15:
        v15 = 1;
        goto LABEL_18;
      }
      while ( 1 )
      {
        v13 = tolower(*v11);
        v14 = *v6++;
        if ( v13 != tolower(v14) )
          break;
        if ( ++v11 == v12 )
        {
          v7 = *((_QWORD *)&v21 + 1);
          goto LABEL_15;
        }
      }
      v7 = *((_QWORD *)&v21 + 1);
    }
    v15 = 0;
LABEL_18:
    if ( v7 > 0xF )
    {
      v16 = (void *)v20;
      if ( v7 + 1 >= 0x1000 )
      {
        v16 = *(void **)(v20 - 8);
        if ( (unsigned __int64)(v20 - (_QWORD)v16 - 8) > 0x1F )
          _invoke_watson(0, 0, 0, 0, 0);
      }
      free(v16);
    }
    if ( v15 )
      return 1;
    v3 += 8;
    if ( v3 == &v19 )
      return v4;
    v2 = *(const char **)v3;
  }
}

```

## disassembly

```asm
0x18018ce58  mov     [rsp-8+arg_0], rbx
0x18018ce5d  mov     [rsp-8+arg_8], rsi
0x18018ce62  mov     [rsp-8+arg_10], rdi
0x18018ce67  push    rbp
0x18018ce68  push    r12
0x18018ce6a  push    r13
0x18018ce6c  push    r14
0x18018ce6e  push    r15
0x18018ce70  lea     rbp, [rsp-70h]
0x18018ce75  sub     rsp, 170h
0x18018ce7c  mov     rax, cs:__security_cookie
0x18018ce83  xor     rax, rsp
0x18018ce86  mov     [rbp+90h+var_28], rax
0x18018ce8a  mov     r15, rcx
0x18018ce8d  lea     rdx, aAdd; ".add"
0x18018ce94  mov     [rsp+190h+var_160], rdx
0x18018ce99  lea     rax, aCab; ".cab"
0x18018cea0  mov     [rsp+190h+var_158], rax
0x18018cea5  lea     rax, aCgl; ".cgl"
0x18018ceac  mov     [rsp+190h+var_150], rax
0x18018ceb1  lea     rax, aCnv; ".cnv"
0x18018ceb8  mov     [rsp+190h+var_148], rax
0x18018cebd  lea     rax, aCpl; ".cpl"
0x18018cec4  mov     [rsp+190h+var_140], rax
0x18018cec9  lea     rax, aDic; ".dic"
0x18018ced0  mov     [rsp+190h+var_138], rax
0x18018ced5  lea     rax, aDll; ".dll"
0x18018cedc  mov     [rsp+190h+var_130], rax
0x18018cee1  lea     rax, aExe; ".exe"
0x18018cee8  mov     [rsp+190h+var_128], rax
0x18018ceed  lea     rax, aFae; ".fae"
0x18018cef4  mov     [rsp+190h+var_120], rax
0x18018cef9  lea     rax, aFlt; ".flt"
0x18018cf00  mov     [rsp+190h+var_118], rax
0x18018cf05  lea     rax, aIdxDll; ".idx_dll"
0x18018cf0c  mov     [rbp+90h+var_110], rax
0x18018cf10  lea     rax, aIme; ".ime"
0x18018cf17  mov     [rbp+90h+var_108], rax
0x18018cf1b  lea     rax, aMdl; ".mdl"
0x18018cf22  mov     [rbp+90h+var_100], rax
0x18018cf26  lea     rax, aMsi; ".msi"
0x18018cf2d  mov     [rbp+90h+var_F8], rax
0x18018cf31  lea     rax, aMui; ".mui"
0x18018cf38  mov     [rbp+90h+var_F0], rax
0x18018cf3c  lea     rax, aOcx; ".ocx"
0x18018cf43  mov     [rbp+90h+var_E8], rax
0x18018cf47  lea     rax, aOdf; ".odf"
0x18018cf4e  mov     [rbp+90h+var_E0], rax
0x18018cf52  lea     rax, aOlb; ".olb"
0x18018cf59  mov     [rbp+90h+var_D8], rax
0x18018cf5d  lea     rax, aPdl; ".pdl"
0x18018cf64  mov     [rbp+90h+var_D0], rax
0x18018cf68  lea     rax, aRpl; ".rpl"
0x18018cf6f  mov     [rbp+90h+var_C8], rax
0x18018cf73  lea     rax, aSam; ".sam"
0x18018cf7a  mov     [rbp+90h+var_C0], rax
0x18018cf7e  lea     rax, aTll; ".tll"
0x18018cf85  mov     [rbp+90h+var_B8], rax
0x18018cf89  lea     rax, aTrxDll; ".trx_dll"
0x18018cf90  mov     [rbp+90h+var_B0], rax
0x18018cf94  lea     rax, aUpl; ".upl"
0x18018cf9b  mov     [rbp+90h+var_A8], rax
0x18018cf9f  lea     rax, aVsl; ".vsl"
0x18018cfa6  mov     [rbp+90h+var_A0], rax
0x18018cfaa  lea     rax, aWll; ".wll"
0x18018cfb1  mov     [rbp+90h+var_98], rax
0x18018cfb5  lea     rax, aXll; ".xll"
0x18018cfbc  mov     [rbp+90h+var_90], rax
0x18018cfc0  lea     rax, aXsn; ".xsn"
0x18018cfc7  mov     [rbp+90h+var_88], rax
0x18018cfcb  lea     rax, aCat; ".cat"
0x18018cfd2  mov     [rbp+90h+var_80], rax
0x18018cfd6  lea     rax, aRll; ".rll"
0x18018cfdd  mov     [rbp+90h+var_78], rax
0x18018cfe1  lea     rax, aAppx; ".appx"
0x18018cfe8  mov     [rbp+90h+var_70], rax
0x18018cfec  lea     rax, aMsix; ".msix"
0x18018cff3  mov     [rbp+90h+var_68], rax
0x18018cff7  lea     rax, aAppxbundle; ".appxbundle"
0x18018cffe  mov     [rbp+90h+var_60], rax
0x18018d002  lea     r12, [rsp+190h+var_160]
0x18018d007  xor     r14d, r14d
0x18018d00a  xorps   xmm0, xmm0
0x18018d00d  movups  [rbp+90h+var_48], xmm0
0x18018d011  xorps   xmm1, xmm1
0x18018d014  movdqu  [rbp+90h+var_38], xmm1
0x18018d019  or      r8, 0FFFFFFFFFFFFFFFFh
0x18018d01d  inc     r8
0x18018d020  cmp     [rdx+r8], r14b
0x18018d024  jnz     short loc_18018D01D
0x18018d026  lea     rcx, [rbp+90h+var_48]
0x18018d02a  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18018d02f  lea     rbx, [rbp+90h+var_48]
0x18018d033  mov     rax, qword ptr [rbp+90h+var_38+8]
0x18018d037  cmp     rax, 0Fh
0x18018d03b  cmova   rbx, qword ptr [rbp+90h+var_48]
0x18018d040  mov     rcx, [r15+10h]
0x18018d044  cmp     rcx, qword ptr [rbp+90h+var_38]
0x18018d048  jb      short loc_18018D0A1
0x18018d04a  mov     r8, r15
0x18018d04d  cmp     qword ptr [r15+18h], 0Fh
0x18018d052  jbe     short loc_18018D057
0x18018d054  mov     r8, [r15]
0x18018d057  mov     rdx, r15
0x18018d05a  jbe     short loc_18018D05F
0x18018d05c  mov     rdx, [r15]
0x18018d05f  mov     rsi, rcx
0x18018d062  sub     rsi, qword ptr [rbp+90h+var_38]
0x18018d066  add     rsi, rdx
0x18018d069  lea     r13, [rcx+r8]
0x18018d06d  cmp     rsi, r13
0x18018d070  jz      short loc_18018D099
0x18018d072  movzx   ecx, byte ptr [rsi]; C
0x18018d075  call    cs:__imp_tolower
0x18018d07b  mov     edi, eax
0x18018d07d  movzx   ecx, byte ptr [rbx]; C
0x18018d080  inc     rbx
0x18018d083  call    cs:__imp_tolower
0x18018d089  cmp     edi, eax
0x18018d08b  jnz     short loc_18018D09D
0x18018d08d  inc     rsi
0x18018d090  cmp     rsi, r13
0x18018d093  jnz     short loc_18018D072
0x18018d095  mov     rax, qword ptr [rbp+90h+var_38+8]
0x18018d099  mov     bl, 1
0x18018d09b  jmp     short loc_18018D0A4
0x18018d09d  mov     rax, qword ptr [rbp+90h+var_38+8]
0x18018d0a1  mov     bl, r14b
0x18018d0a4  cmp     rax, 0Fh
0x18018d0a8  jbe     short loc_18018D0D3
0x18018d0aa  mov     rcx, qword ptr [rbp+90h+var_48]
0x18018d0ae  mov     rdx, rcx
0x18018d0b1  inc     rax
0x18018d0b4  cmp     rax, 1000h
0x18018d0ba  jb      short loc_18018D0CD
0x18018d0bc  mov     rcx, [rcx-8]; Block
0x18018d0c0  sub     rdx, rcx
0x18018d0c3  lea     rax, [rdx-8]
0x18018d0c7  cmp     rax, 1Fh
0x18018d0cb  ja      short loc_18018D0ED
0x18018d0cd  call    cs:__imp_free
0x18018d0d3  test    bl, bl
0x18018d0d5  jnz     short loc_18018D103
0x18018d0d7  add     r12, 8
0x18018d0db  lea     rax, [rbp+90h+var_58]
0x18018d0df  cmp     r12, rax
0x18018d0e2  jz      short loc_18018D106
0x18018d0e4  mov     rdx, [r12]
0x18018d0e8  jmp     loc_18018D00A
0x18018d0ed  mov     [rsp+190h+Reserved], r14; Reserved
0x18018d0f2  xor     r9d, r9d; LineNo
0x18018d0f5  xor     r8d, r8d; FileName
0x18018d0f8  xor     edx, edx; FunctionName
0x18018d0fa  xor     ecx, ecx; Expression
0x18018d0fc  call    cs:__imp__invoke_watson
0x18018d103  mov     r14b, 1
0x18018d106  mov     al, r14b
0x18018d109  mov     rcx, [rbp+90h+var_28]
0x18018d10d  xor     rcx, rsp; StackCookie
0x18018d110  call    __security_check_cookie
0x18018d115  lea     r11, [rsp+190h+var_20]
0x18018d11d  mov     rbx, [r11+30h]
0x18018d121  mov     rsi, [r11+38h]
0x18018d125  mov     rdi, [r11+40h]
0x18018d129  mov     rsp, r11
0x18018d12c  pop     r15
0x18018d12e  pop     r14
0x18018d130  pop     r13
0x18018d132  pop     r12
0x18018d134  pop     rbp
0x18018d135  retn
```
