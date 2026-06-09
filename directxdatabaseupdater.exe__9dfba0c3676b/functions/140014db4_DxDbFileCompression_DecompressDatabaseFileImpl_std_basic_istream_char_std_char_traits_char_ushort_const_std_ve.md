# DxDbFileCompression::DecompressDatabaseFileImpl(std::basic_istream<char,std::char_traits<char>> &,ushort const *,std::vector<uchar,std::allocator<uchar>> *)

- ea: `0x140014db4`
- end: `0x1400151f1`
- name: `?DecompressDatabaseFileImpl@DxDbFileCompression@@YAJAEAV?$basic_istream@DU?$char_traits@D@std@@@std@@PEBGPEAV?$vector@EV?$allocator@E@std@@@3@@Z`
- size: `1085`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140014be4`

## callees

- `0x140002f40`
- `0x1400039fe`
- `0x140003aa0`
- `0x140003ab8`
- `0x14000a4bc`
- `0x14000df28`
- `0x1400115ec`
- `0x140011a4c`
- `0x140014564`
- `0x140014900`
- `0x140014db4`
- `0x140017c64`
- `0x140017d4c`

## import_xrefs

- `msvcp_win!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x140014e06`
- `msvcp_win!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x140014ee0`
- `msvcp_win!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x140014e06`
- `msvcp_win!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x140014ee0`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140014fdb`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140014fe9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140014fdb`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140014fe9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400150e2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400150e2`

## string_xrefs

- `0x140014f50`: `onecore\windows\directx\database\updater\filecompression\filecompression.cpp`
- `0x1400151b2`: `onecore\windows\directx\database\updater\filecompression\filecompression.cpp`

## pseudocode

```c
__int64 __fastcall DxDbFileCompression::DecompressDatabaseFileImpl(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rdi
  unsigned int v5; // ebx
  __int64 v6; // rdx
  size_t v7; // r15
  int i; // r8d
  size_t v9; // rbx
  __int64 v10; // r13
  __int64 v11; // rdx
  void *v12; // rcx
  __int64 v13; // r12
  __int64 v14; // rax
  int v15; // eax
  size_t v16; // rsi
  UCHAR *v17; // rcx
  int v18; // esi
  const char *v19; // rax
  __int64 v20; // r9
  __int64 v21; // rdx
  int v22; // eax
  __int64 v23; // r9
  __int64 v24; // rdx
  __int128 *v25; // rcx
  int v27; // [rsp+20h] [rbp-E0h]
  int *v28; // [rsp+20h] [rbp-E0h]
  char *v29; // [rsp+28h] [rbp-D8h]
  void *Src; // [rsp+48h] [rbp-B8h]
  size_t Size; // [rsp+50h] [rbp-B0h] BYREF
  PUCHAR pbInput[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v33; // [rsp+68h] [rbp-98h]
  int v34[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v35; // [rsp+78h] [rbp-88h]
  __int64 v36; // [rsp+80h] [rbp-80h]
  __int64 v37; // [rsp+88h] [rbp-78h]
  __int64 v38; // [rsp+90h] [rbp-70h]
  _QWORD v39[3]; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v40[4]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v41[40]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v42; // [rsp+F8h] [rbp-8h]
  __int64 v43; // [rsp+110h] [rbp+10h]
  int v44; // [rsp+12Ch] [rbp+2Ch]
  int v45; // [rsp+134h] [rbp+34h]
  __int128 v46; // [rsp+150h] [rbp+50h] BYREF
  __m128i si128; // [rsp+160h] [rbp+60h]
  __int64 v48; // [rsp+170h] [rbp+70h] BYREF
  int v49; // [rsp+178h] [rbp+78h]
  char v50; // [rsp+17Ch] [rbp+7Ch]
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  v38 = a2;
  v4 = a1;
  v37 = a1;
  v48 = 0;
  v49 = 0;
  v50 = 0;
  std::istream::read(a1, &v48, 13);
  memset_0(v41, 0, 0x80u);
  if ( (unsigned int)LzmaDec_Allocate(v41, &v48) )
  {
    v5 = -2147286789;
    v6 = 92;
  }
  else
  {
    v42 = 0;
    v45 = 0;
    v43 = 0;
    v44 = 276;
    v7 = 0;
    for ( i = 0; i < 8; ++i )
      v7 += (unsigned __int64)*((unsigned __int8 *)&v48 + (unsigned int)i + 5) << (8 * (unsigned __int8)i);
    if ( v7 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      v9 = v7;
      v10 = 0;
      std::vector<unsigned char>::vector<unsigned char>(pbInput, v7);
      std::vector<unsigned char>::vector<unsigned char>(v40, 0x10000);
      std::vector<unsigned char>::vector<unsigned char>(v39, 0x10000);
      v11 = v40[0];
      v36 = v40[0];
      v12 = (void *)v39[0];
      Src = (void *)v39[0];
      v13 = 0;
      v14 = 0;
      v35 = 0;
      while ( 1 )
      {
        if ( v13 == v14 )
        {
          std::istream::read(v4, v11, 0x10000);
          v14 = *(_QWORD *)(v4 + 8);
          v35 = v14;
          v13 = 0;
          v12 = Src;
          v11 = v36;
        }
        *(_QWORD *)v34 = v14 - v13;
        Size = 0x10000;
        if ( v9 < 0x10000 )
          Size = v9;
        v28 = v34;
        v15 = LzmaDec_DecodeToBuf(v41, v12, &Size, v13 + v11);
        if ( v15 )
          break;
        v16 = Size;
        if ( Size )
        {
          v17 = &pbInput[0][v10];
          if ( !&pbInput[0][v10] )
            goto LABEL_24;
          if ( !Src || v9 < Size )
          {
            memset_0(v17, 0, v9);
            if ( Src )
            {
              if ( v9 < v16 )
              {
                *(_DWORD *)_o__errno(v17) = 34;
                goto LABEL_25;
              }
            }
            else
            {
LABEL_24:
              *(_DWORD *)_o__errno(v17) = 22;
LABEL_25:
              invalid_parameter_noinfo();
            }
            v5 = -2147467259;
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x99,
              (unsigned int)"onecore\\windows\\directx\\database\\updater\\filecompression\\filecompression.cpp",
              (const char *)0x80004005LL,
              (int)v34);
LABEL_42:
            std::vector<unsigned char>::_Tidy(v39);
            std::vector<unsigned char>::_Tidy(v40);
            std::vector<unsigned char>::_Tidy(pbInput);
            return v5;
          }
          memcpy_0(v17, Src, Size);
        }
        v10 += v16;
        v9 -= v16;
        if ( !v9 )
        {
          v18 = 0;
          goto LABEL_31;
        }
        if ( !*(_QWORD *)v34 && !v16 )
        {
          v18 = -2147467260;
          LODWORD(v29) = 0;
          v19 = "status: %d";
          v20 = 2147500036LL;
          v21 = 167;
          goto LABEL_30;
        }
        v13 += *(_QWORD *)v34;
        v12 = Src;
        v14 = v35;
        v4 = v37;
        v11 = v36;
      }
      v18 = -2147467259;
      LODWORD(v29) = v15;
      v19 = "res: %d";
      v20 = 2147500037LL;
      v21 = 145;
LABEL_30:
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)v21,
        (unsigned int)"onecore\\windows\\directx\\database\\updater\\filecompression\\filecompression.cpp",
        (const char *)v20,
        (int)v19,
        v29);
LABEL_31:
      if ( v10 != v7 )
      {
        if ( v18 < 0 )
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xAC,
            (unsigned int)"onecore\\windows\\directx\\database\\updater\\filecompression\\filecompression.cpp",
            (const char *)(unsigned int)v18,
            (int)v28);
        v5 = v18;
        goto LABEL_42;
      }
      v46 = 0;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v46) = 0;
      v22 = CalculateSHA512Hash(pbInput[0], LODWORD(pbInput[1]) - LODWORD(pbInput[0]));
      v5 = v22;
      if ( v22 >= 0 )
      {
        v25 = &v46;
        if ( si128.m128i_i64[1] > 7uLL )
          v25 = (__int128 *)v46;
        if ( !(unsigned int)_o__wcsicmp(v25, v38) )
        {
          if ( a3 && (PUCHAR *)a3 != pbInput )
          {
            std::vector<unsigned char>::_Tidy(a3);
            *(PUCHAR *)a3 = pbInput[0];
            *(PUCHAR *)(a3 + 8) = pbInput[1];
            *(_QWORD *)(a3 + 16) = v33;
            *(_OWORD *)pbInput = 0;
            v33 = 0;
          }
          std::wstring::_Tidy_deallocate(&v46);
          std::vector<unsigned char>::_Tidy(v39);
          std::vector<unsigned char>::_Tidy(v40);
          std::vector<unsigned char>::_Tidy(pbInput);
          return (unsigned int)v18;
        }
        v5 = -2146889721;
        v23 = 2148077575LL;
        v24 = 180;
      }
      else
      {
        v23 = (unsigned int)v22;
        v24 = 177;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v24,
        (unsigned int)"onecore\\windows\\directx\\database\\updater\\filecompression\\filecompression.cpp",
        (const char *)v23,
        (int)v28);
      std::wstring::_Tidy_deallocate(&v46);
      goto LABEL_42;
    }
    v5 = -2147467259;
    v6 = 103;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"onecore\\windows\\directx\\database\\updater\\filecompression\\filecompression.cpp",
    (const char *)v5,
    v27);
  return v5;
}

```

## disassembly

```asm
0x140014db4  mov     [rsp-8+arg_18], rbx
0x140014db9  push    rbp
0x140014dba  push    rsi
0x140014dbb  push    rdi
0x140014dbc  push    r12
0x140014dbe  push    r13
0x140014dc0  push    r14
0x140014dc2  push    r15
0x140014dc4  lea     rbp, [rsp-90h]
0x140014dcc  sub     rsp, 190h
0x140014dd3  mov     rax, cs:__security_cookie
0x140014dda  xor     rax, rsp
0x140014ddd  mov     [rbp+0C0h+var_40], rax
0x140014de4  mov     r14, r8
0x140014de7  mov     [rbp+0C0h+var_130], rdx
0x140014deb  mov     rdi, rcx
0x140014dee  mov     [rbp+0C0h+var_138], rcx
0x140014df2  xor     eax, eax
0x140014df4  mov     [rbp+0C0h+var_50], rax
0x140014df8  mov     [rbp+0C0h+var_48], eax
0x140014dfb  mov     [rbp+0C0h+var_44], al
0x140014dfe  lea     r8d, [rax+0Dh]
0x140014e02  lea     rdx, [rbp+0C0h+var_50]
0x140014e06  call    cs:__imp_?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z; std::istream::read(char *,__int64)
0x140014e0c  xor     edx, edx; Val
0x140014e0e  mov     r8d, 80h; Size
0x140014e14  lea     rcx, [rbp+0C0h+var_F0]; void *
0x140014e18  call    memset_0
0x140014e1d  lea     rdx, [rbp+0C0h+var_50]
0x140014e21  lea     rcx, [rbp+0C0h+var_F0]
0x140014e25  call    LzmaDec_Allocate
0x140014e2a  xor     esi, esi
0x140014e2c  test    eax, eax
0x140014e2e  jz      short loc_140014E3D
0x140014e30  mov     ebx, 800300FBh
0x140014e35  lea     edx, [rsi+5Ch]
0x140014e38  jmp     loc_1400151AF
0x140014e3d  mov     [rbp+0C0h+var_C8], rsi
0x140014e41  mov     [rbp+0C0h+var_8C], esi
0x140014e44  mov     [rbp+0C0h+var_B0], rsi
0x140014e48  mov     [rbp+0C0h+var_94], 114h
0x140014e4f  mov     r15, rsi
0x140014e52  mov     r8d, esi
0x140014e55  mov     eax, r8d
0x140014e58  movzx   edx, byte ptr [rbp+rax+0C0h+var_50+5]
0x140014e5d  lea     ecx, ds:0[r8*8]
0x140014e65  shl     rdx, cl
0x140014e68  add     r15, rdx
0x140014e6b  inc     r8d
0x140014e6e  cmp     r8d, 8
0x140014e72  jl      short loc_140014E55
0x140014e74  lea     rax, [r15-1]
0x140014e78  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140014e7c  ja      loc_1400151A5
0x140014e82  mov     rbx, r15
0x140014e85  mov     r13, rsi
0x140014e88  mov     rdx, r15
0x140014e8b  lea     rcx, [rsp+1C0h+pbInput]
0x140014e90  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x140014e95  nop
0x140014e96  mov     r12d, 10000h
0x140014e9c  mov     edx, r12d
0x140014e9f  lea     rcx, [rbp+0C0h+var_110]
0x140014ea3  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x140014ea8  nop
0x140014ea9  mov     edx, r12d
0x140014eac  lea     rcx, [rbp+0C0h+var_128]
0x140014eb0  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x140014eb5  nop
0x140014eb6  mov     rdx, [rbp+0C0h+var_110]
0x140014eba  mov     [rbp+0C0h+var_140], rdx
0x140014ebe  mov     rcx, [rbp+0C0h+var_128]
0x140014ec2  mov     [rsp+1C0h+Src], rcx
0x140014ec7  mov     r12, rsi
0x140014eca  mov     rax, rsi
0x140014ecd  mov     [rsp+1C0h+var_148], rax
0x140014ed2  cmp     r12, rax
0x140014ed5  jnz     short loc_140014EFB
0x140014ed7  mov     r8d, 10000h
0x140014edd  mov     rcx, rdi
0x140014ee0  call    cs:__imp_?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z; std::istream::read(char *,__int64)
0x140014ee6  mov     rax, [rdi+8]
0x140014eea  mov     [rsp+1C0h+var_148], rax
0x140014eef  mov     r12, rsi
0x140014ef2  mov     rcx, [rsp+1C0h+Src]
0x140014ef7  mov     rdx, [rbp+0C0h+var_140]
0x140014efb  sub     rax, r12
0x140014efe  mov     qword ptr [rsp+1C0h+var_150], rax
0x140014f03  mov     r8d, 10000h
0x140014f09  mov     [rsp+1C0h+Size], r8
0x140014f0e  mov     eax, esi
0x140014f10  mov     [rsp+1C0h+var_180], esi
0x140014f14  cmp     rbx, r8
0x140014f17  jnb     short loc_140014F23
0x140014f19  mov     [rsp+1C0h+Size], rbx
0x140014f1e  mov     eax, 1
0x140014f23  lea     r9, [r12+rdx]
0x140014f27  lea     rdx, [rsp+1C0h+var_180]
0x140014f2c  mov     [rsp+1C0h+var_190], rdx
0x140014f31  mov     dword ptr [rsp+1C0h+var_198], eax
0x140014f35  lea     rax, [rsp+1C0h+var_150]
0x140014f3a  mov     qword ptr [rsp+1C0h+var_1A0], rax; int
0x140014f3f  lea     r8, [rsp+1C0h+Size]
0x140014f44  mov     rdx, rcx
0x140014f47  lea     rcx, [rbp+0C0h+var_F0]
0x140014f4b  call    LzmaDec_DecodeToBuf
0x140014f50  lea     rdi, aOnecoreWindows_1; "onecore\\windows\\directx\\database\\up"...
0x140014f57  test    eax, eax
0x140014f59  jnz     loc_14001503D
0x140014f5f  mov     rsi, [rsp+1C0h+Size]
0x140014f64  test    rsi, rsi
0x140014f67  jz      short loc_140014F8D
0x140014f69  mov     rcx, [rsp+1C0h+pbInput]
0x140014f6e  add     rcx, r13; void *
0x140014f71  jz      short loc_140014FE9
0x140014f73  mov     rax, [rsp+1C0h+Src]
0x140014f78  test    rax, rax
0x140014f7b  jz      short loc_140014FC4
0x140014f7d  cmp     rbx, rsi
0x140014f80  jb      short loc_140014FC4
0x140014f82  mov     r8, rsi; Size
0x140014f85  mov     rdx, rax; Src
0x140014f88  call    memcpy_0
0x140014f8d  add     r13, rsi
0x140014f90  sub     rbx, rsi
0x140014f93  jz      loc_140015039
0x140014f99  mov     rax, qword ptr [rsp+1C0h+var_150]
0x140014f9e  test    rax, rax
0x140014fa1  jnz     short loc_140014FA8
0x140014fa3  test    rsi, rsi
0x140014fa6  jz      short loc_14001501B
0x140014fa8  add     r12, rax
0x140014fab  mov     rcx, [rsp+1C0h+Src]
0x140014fb0  mov     rax, [rsp+1C0h+var_148]
0x140014fb5  mov     rdi, [rbp+0C0h+var_138]
0x140014fb9  mov     rdx, [rbp+0C0h+var_140]
0x140014fbd  xor     esi, esi
0x140014fbf  jmp     loc_140014ED2
0x140014fc4  mov     r8, rbx; Size
0x140014fc7  xor     edx, edx; Val
0x140014fc9  call    memset_0
0x140014fce  cmp     [rsp+1C0h+Src], 0
0x140014fd4  jz      short loc_140014FE9
0x140014fd6  cmp     rbx, rsi
0x140014fd9  jnb     short loc_140014FFA
0x140014fdb  call    cs:__imp__o__errno
0x140014fe1  mov     dword ptr [rax], 22h ; '"'
0x140014fe7  jmp     short loc_140014FF5
0x140014fe9  call    cs:__imp__o__errno
0x140014fef  mov     dword ptr [rax], 16h
0x140014ff5  call    _invalid_parameter_noinfo
0x140014ffa  mov     rcx, [rbp+0C8h]; this
0x140015001  mov     ebx, 80004005h
0x140015006  mov     r9d, ebx; char *
0x140015009  mov     r8, rdi; unsigned int
0x14001500c  mov     edx, 99h; void *
0x140015011  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140015016  jmp     loc_140015113
0x14001501b  mov     esi, 80004004h
0x140015020  mov     eax, [rsp+1C0h+var_180]
0x140015024  mov     dword ptr [rsp+1C0h+var_198], eax
0x140015028  lea     rax, aStatusD; "status: %d"
0x14001502f  mov     r9d, esi
0x140015032  mov     edx, 0A7h
0x140015037  jmp     short loc_140015057
0x140015039  xor     esi, esi
0x14001503b  jmp     short loc_14001506B
0x14001503d  mov     ebx, 80004005h
0x140015042  mov     esi, ebx
0x140015044  mov     dword ptr [rsp+1C0h+var_198], eax; char *
0x140015048  lea     rax, aResD; "res: %d"
0x14001504f  mov     r9d, ebx; char *
0x140015052  mov     edx, 91h; void *
0x140015057  mov     qword ptr [rsp+1C0h+var_1A0], rax; int
0x14001505c  mov     r8, rdi; unsigned int
0x14001505f  mov     rcx, [rbp+0C8h]; this
0x140015066  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x14001506b  cmp     r13, r15
0x14001506e  jz      short loc_140015092
0x140015070  test    esi, esi
0x140015072  jns     short loc_14001508B
0x140015074  mov     rcx, [rbp+0C8h]; this
0x14001507b  mov     r9d, esi; char *
0x14001507e  mov     r8, rdi; unsigned int
0x140015081  mov     edx, 0ACh; void *
0x140015086  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001508b  mov     ebx, esi
0x14001508d  jmp     loc_140015113
0x140015092  xorps   xmm0, xmm0
0x140015095  movups  [rbp+0C0h+var_70], xmm0
0x140015099  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1400150a1  movdqu  [rbp+0C0h+var_60], xmm1
0x1400150a6  xor     eax, eax
0x1400150a8  mov     word ptr [rbp+0C0h+var_70], ax
0x1400150ac  mov     rcx, [rsp+1C0h+pbInput]; pbInput
0x1400150b1  mov     edx, dword ptr [rsp+1C0h+pbInput+8]
0x1400150b5  sub     edx, ecx; cbInput
0x1400150b7  lea     r8, [rbp+0C0h+var_70]
0x1400150bb  call    ?CalculateSHA512Hash@@YAJPEAEIAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CalculateSHA512Hash(uchar *,uint,std::wstring &)
0x1400150c0  mov     ebx, eax
0x1400150c2  test    eax, eax
0x1400150c4  jns     short loc_1400150D0
0x1400150c6  mov     r9d, eax
0x1400150c9  mov     edx, 0B1h
0x1400150ce  jmp     short loc_1400150F9
0x1400150d0  lea     rcx, [rbp+0C0h+var_70]
0x1400150d4  cmp     qword ptr [rbp+0C0h+var_60+8], 7
0x1400150d9  cmova   rcx, qword ptr [rbp+0C0h+var_70]
0x1400150de  mov     rdx, [rbp+0C0h+var_130]
0x1400150e2  call    cs:__imp__o__wcsicmp
0x1400150e8  test    eax, eax
0x1400150ea  jz      short loc_140015136
0x1400150ec  mov     ebx, 80091007h
0x1400150f1  mov     r9d, ebx; char *
0x1400150f4  mov     edx, 0B4h; void *
0x1400150f9  mov     r8, rdi; unsigned int
0x1400150fc  mov     rcx, [rbp+0C8h]; this
0x140015103  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140015108  nop
0x140015109  lea     rcx, [rbp+0C0h+var_70]
0x14001510d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140015112  nop
0x140015113  lea     rcx, [rbp+0C0h+var_128]
0x140015117  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x14001511c  nop
0x14001511d  lea     rcx, [rbp+0C0h+var_110]
0x140015121  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140015126  nop
0x140015127  lea     rcx, [rsp+1C0h+pbInput]
0x14001512c  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140015131  jmp     loc_1400151C5
0x140015136  test    r14, r14
0x140015139  jz      short loc_140015179
0x14001513b  lea     rax, [rsp+1C0h+pbInput]
0x140015140  cmp     r14, rax
0x140015143  jz      short loc_140015179
0x140015145  mov     rcx, r14
0x140015148  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x14001514d  mov     rax, [rsp+1C0h+pbInput]
0x140015152  mov     [r14], rax
0x140015155  mov     rax, [rsp+1C0h+pbInput+8]
0x14001515a  mov     [r14+8], rax
0x14001515e  mov     rax, [rsp+1C0h+var_158]
0x140015163  mov     [r14+10h], rax
0x140015167  xorps   xmm0, xmm0
0x14001516a  movdqu  xmmword ptr [rsp+1C0h+pbInput], xmm0
0x140015170  mov     [rsp+1C0h+var_158], 0
0x140015179  lea     rcx, [rbp+0C0h+var_70]
0x14001517d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140015182  nop
0x140015183  lea     rcx, [rbp+0C0h+var_128]
0x140015187  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x14001518c  nop
0x14001518d  lea     rcx, [rbp+0C0h+var_110]
0x140015191  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140015196  nop
0x140015197  lea     rcx, [rsp+1C0h+pbInput]
0x14001519c  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1400151a1  mov     eax, esi
0x1400151a3  jmp     short loc_1400151C7
0x1400151a5  mov     ebx, 80004005h
0x1400151aa  mov     edx, 67h ; 'g'; void *
0x1400151af  mov     r9d, ebx; char *
0x1400151b2  lea     r8, aOnecoreWindows_1; "onecore\\windows\\directx\\database\\up"...
0x1400151b9  mov     rcx, [rbp+0C8h]; this
0x1400151c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400151c5  mov     eax, ebx
0x1400151c7  mov     rcx, [rbp+0C0h+var_40]
0x1400151ce  xor     rcx, rsp; StackCookie
0x1400151d1  call    __security_check_cookie
0x1400151d6  mov     rbx, [rsp+1C0h+arg_18]
0x1400151de  add     rsp, 190h
0x1400151e5  pop     r15
0x1400151e7  pop     r14
0x1400151e9  pop     r13
0x1400151eb  pop     r12
0x1400151ed  pop     rdi
0x1400151ee  pop     rsi
0x1400151ef  pop     rbp
0x1400151f0  retn
```
