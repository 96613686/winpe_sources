# RepoMan::Legacy::Descriptor::Index(IRepoWriter *,IRepoBuild *,IRepoCulture *)

- ea: `0x1800c6940`
- end: `0x1800c70b0`
- name: `?Index@Descriptor@Legacy@RepoMan@@QEAAXPEAUIRepoWriter@@PEAUIRepoBuild@@PEAUIRepoCulture@@@Z`
- size: `1904`
- prototype: `void __fastcall(RepoMan::Legacy::Descriptor *__hidden this, struct IRepoWriter *, struct IRepoBuild *, struct IRepoCulture *)`
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1800c70b0`
- `0x1800c7294`

## callees

- `0x180001ffc`
- `0x180008770`
- `0x18002bf64`
- `0x18002f940`
- `0x1800385d8`
- `0x18003a710`
- `0x1800c6940`
- `0x1800dfffc`
- `0x18018aed8`
- `0x18018b53c`
- `0x18019a840`
- `0x18019f7a0`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800c69a3`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800c6c6e`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800c6ec4`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800c69a3`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800c6c6e`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800c6ec4`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800c7060`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800c7060`

## string_xrefs

- `0x1800c6a84`: `src\repoman\src\inc\MasterDescriptor.hpp`
- `0x1800c6b11`: `src\repoman\src\inc\MasterDescriptor.hpp`
- `0x1800c6b4c`: `src\repoman\src\inc\MasterDescriptor.hpp`
- `0x1800c6dd4`: `src\repoman\src\inc\MasterDescriptor.hpp`
- `0x1800c6f6d`: `src\repoman\src\inc\MasterDescriptor.hpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
void __fastcall RepoMan::Legacy::Descriptor::Index(
        RepoMan::Legacy::Descriptor *this,
        struct IRepoWriter *a2,
        struct IRepoBuild *a3,
        struct IRepoCulture *a4)
{
  struct IRepoBuild *v4; // rsi
  struct IRepoWriter *v5; // r12
  RepoMan::Legacy::Descriptor *v6; // r13
  int v7; // r14d
  __int64 **v8; // rax
  __int64 **v9; // rbx
  __int64 *v10; // rdi
  const CHAR *v11; // rdi
  __m128i si128; // xmm6
  struct IRepoBuild *v13; // r13
  __int64 (__fastcall *v14)(struct IRepoWriter *, struct IRepoBuild *, _QWORD *, _QWORD *, struct IRepoCulture *, _BYTE **); // r15
  _QWORD *v15; // rax
  _QWORD *v16; // rbx
  __int64 **v17; // r14
  __int64 (__fastcall *v18)(struct IRepoWriter *, struct IRepoBuild *, _QWORD *, __int64 *); // rbx
  _QWORD *v19; // rax
  unsigned int v20; // eax
  const char *v21; // r9
  unsigned __int64 j; // rcx
  unsigned __int64 v23; // rbx
  struct IRepoBuild *v24; // r13
  struct IRepoCulture *v25; // r14
  BOOL v26; // esi
  __int64 (__fastcall *v27)(struct IRepoWriter *, struct IRepoBuild *, struct IRepoCulture *, _QWORD *, BOOL, _BYTE **); // r15
  _QWORD *v28; // rax
  unsigned int v29; // eax
  const char *v30; // r9
  unsigned int v31; // eax
  const char *v32; // r9
  __int64 v33; // rax
  unsigned __int64 i; // rax
  _BYTE *v35; // r12
  int v36; // edx
  _BYTE *v37; // rsi
  _BYTE *v38; // r15
  unsigned __int8 v39; // al
  char *v40; // rax
  _QWORD *v41; // rax
  __int64 ***v42; // rsi
  _QWORD *v43; // r15
  unsigned __int64 v44; // r8
  __int64 v45; // rcx
  __int64 **v46; // rax
  __int64 *k; // rax
  __int64 *m; // rcx
  _QWORD *v49; // rax
  unsigned int v50; // eax
  const char *v51; // r9
  _BYTE *ii; // rcx
  _BYTE *v53; // rbx
  _OWORD *v54; // r14
  __int64 (__fastcall *v55)(struct IRepoWriter *, struct IRepoBuild *, _BYTE *, _QWORD); // r12
  void *v56; // r13
  _BYTE *v57; // r15
  _BYTE *inserted; // rsi
  char v59; // al
  _QWORD *v60; // rax
  _QWORD *v61; // rsi
  _QWORD *v62; // r15
  unsigned int v63; // eax
  const char *v64; // r9
  __int64 v65; // rax
  __int64 n; // rax
  _BYTE *v67; // rcx
  const CHAR **v68; // rax
  const CHAR *jj; // rax
  const CHAR *kk; // rcx
  int v71; // [rsp+48h] [rbp-C0h]
  _BYTE *v72; // [rsp+50h] [rbp-B8h] BYREF
  void *Block; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v74; // [rsp+60h] [rbp-A8h]
  __int64 v75; // [rsp+68h] [rbp-A0h] BYREF
  struct IRepoBuild *v76; // [rsp+70h] [rbp-98h]
  struct IRepoWriter *v77; // [rsp+78h] [rbp-90h]
  void **p_Block; // [rsp+80h] [rbp-88h]
  _QWORD *v79; // [rsp+88h] [rbp-80h]
  __int128 v80; // [rsp+98h] [rbp-70h] BYREF
  struct IRepoCulture *v81; // [rsp+B8h] [rbp-50h]
  WCHAR v82[8]; // [rsp+C0h] [rbp-48h] BYREF
  __m128i v83; // [rsp+D0h] [rbp-38h]
  WCHAR WideCharStr[16]; // [rsp+E8h] [rbp-20h] BYREF

  v81 = a4;
  v4 = a3;
  v76 = a3;
  v5 = a2;
  v77 = a2;
  v6 = this;
  *(_QWORD *)WideCharStr = this;
  v7 = 0;
  v71 = 0;
  Block = 0;
  v74 = 0;
  v8 = (__int64 **)malloc(0x48u);
  v9 = v8;
  if ( !v8 )
    std::_Xbad_alloc();
  *v8 = (__int64 *)v8;
  v8[1] = (__int64 *)v8;
  v8[2] = (__int64 *)v8;
  *((_WORD *)v8 + 12) = 257;
  Block = v8;
  v10 = (__int64 *)**((_QWORD **)v6 + 6);
  if ( !*((_BYTE *)v10 + 25) )
  {
    while ( 1 )
    {
      v17 = (__int64 **)(v10 + 4);
      *(_QWORD *)&v80 = v10 + 4;
      v75 = 0;
      v18 = *(__int64 (__fastcall **)(struct IRepoWriter *, struct IRepoBuild *, _QWORD *, __int64 *))(*(_QWORD *)v5 + 64LL);
      v19 = (_QWORD *)RepoMan::utf8_to_wstring(v82, (LPCCH)v10 + 32);
      if ( v19[3] > 7u )
        v19 = (_QWORD *)*v19;
      v20 = v18(v5, v4, v19, &v75);
      RepoMan::RaiseExceptionIfFailed((RepoMan *)v20, 86, (int)"src\\repoman\\src\\inc\\MasterDescriptor.hpp", v21);
      std::wstring::_Tidy_deallocate(v82);
      v23 = *(_QWORD *)v10[8];
      if ( !*(_BYTE *)(v23 + 25) )
      {
        v24 = v76;
        v25 = v81;
        do
        {
          v72 = 0;
          v26 = *(_BYTE *)(v23 + 64) != 0;
          v27 = *(__int64 (__fastcall **)(struct IRepoWriter *, struct IRepoBuild *, struct IRepoCulture *, _QWORD *, BOOL, _BYTE **))(*(_QWORD *)v5 + 224LL);
          v28 = (_QWORD *)RepoMan::utf8_to_wstring(v82, (LPCCH)(v23 + 32));
          if ( v28[3] > 7u )
            v28 = (_QWORD *)*v28;
          v29 = v27(v5, v24, v25, v28, v26, &v72);
          RepoMan::RaiseExceptionIfFailed((RepoMan *)v29, 95, (int)"src\\repoman\\src\\inc\\MasterDescriptor.hpp", v30);
          std::wstring::_Tidy_deallocate(v82);
          v31 = (*(__int64 (__fastcall **)(struct IRepoWriter *, struct IRepoBuild *, __int64, _BYTE *))(*(_QWORD *)v5 + 88LL))(
                  v5,
                  v24,
                  v75,
                  v72);
          RepoMan::RaiseExceptionIfFailed((RepoMan *)v31, 96, (int)"src\\repoman\\src\\inc\\MasterDescriptor.hpp", v32);
          j = (unsigned __int64)v72;
          if ( v72 )
          {
            v72 = 0;
            (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)j + 16LL))(j);
          }
          v33 = *(_QWORD *)(v23 + 16);
          if ( *(_BYTE *)(v33 + 25) )
          {
            for ( i = *(_QWORD *)(v23 + 8); !*(_BYTE *)(i + 25) && v23 == *(_QWORD *)(i + 16); i = *(_QWORD *)(i + 8) )
              v23 = i;
            v23 = i;
          }
          else
          {
            v23 = *(_QWORD *)(v23 + 16);
            for ( j = *(_QWORD *)v33; !*(_BYTE *)(j + 25); j = *(_QWORD *)j )
              v23 = j;
          }
        }
        while ( !*(_BYTE *)(v23 + 25) );
        v17 = (__int64 **)v80;
        v6 = *(RepoMan::Legacy::Descriptor **)WideCharStr;
      }
      v9 = (__int64 **)Block;
      v35 = (_BYTE *)*((_QWORD *)Block + 1);
      v36 = 0;
      v37 = Block;
      if ( !v35[25] )
      {
        v38 = (_BYTE *)*((_QWORD *)Block + 1);
        do
        {
          v35 = v38;
          v39 = std::less<void>::operator()<std::string &,std::string &>(j, v38 + 32, v17);
          j = v39;
          v36 = v39 ^ 1;
          if ( !v39 )
            v37 = v38;
          v40 = v38 + 16;
          if ( !(_BYTE)j )
            v40 = v38;
          v38 = *(_BYTE **)v40;
        }
        while ( !*(_BYTE *)(*(_QWORD *)v40 + 25LL) );
      }
      *(_QWORD *)v82 = v35;
      *(_DWORD *)&v82[4] = v36;
      if ( v37[25] || (unsigned __int8)std::less<void>::operator()<std::string &,std::string &>(j, v17, v37 + 32) )
      {
        if ( v74 == 0x38E38E38E38E38ELL )
          std::_Throw_tree_length_error();
        p_Block = &Block;
        v79 = 0;
        v41 = malloc(0x48u);
        v42 = (__int64 ***)v41;
        if ( !v41 )
          std::_Xbad_alloc();
        v79 = v41;
        v43 = v41 + 4;
        *(_QWORD *)&v80 = v41 + 4;
        *((_OWORD *)v41 + 2) = 0;
        v41[6] = 0;
        v41[7] = 0;
        v44 = (unsigned __int64)v17[2];
        if ( (unsigned __int64)v17[3] > 0xF )
          v17 = (__int64 **)*v17;
        std::string::_Construct<2,char const *>(v41 + 4, v17, v44);
        v43[4] = v75;
        if ( v75 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 8LL))(v75);
        *v42 = v9;
        v42[1] = v9;
        v42[2] = v9;
        *((_WORD *)v42 + 12) = 0;
        v79 = 0;
        v80 = *(_OWORD *)v82;
        std::_Tree_val<std::_Tree_simple_types<std::pair<enum _REPOMAN_PROGRESS_SCENARIO const,unsigned __int64>>>::_Insert_node(
          &Block,
          &v80,
          v42);
        v9 = (__int64 **)Block;
      }
      v45 = v75;
      if ( v75 )
      {
        v75 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
        v9 = (__int64 **)Block;
      }
      v46 = (__int64 **)v10[2];
      if ( *((_BYTE *)v46 + 25) )
      {
        for ( k = (__int64 *)v10[1]; !*((_BYTE *)k + 25) && v10 == (__int64 *)k[2]; k = (__int64 *)k[1] )
          v10 = k;
        v10 = k;
      }
      else
      {
        v10 = (__int64 *)v10[2];
        for ( m = *v46; !*((_BYTE *)m + 25); m = (__int64 *)*m )
          v10 = m;
      }
      v5 = v77;
      if ( *((_BYTE *)v10 + 25) )
        break;
      v4 = v76;
    }
    v7 = 0;
  }
  v11 = (const CHAR *)**((_QWORD **)v6 + 4);
  if ( !v11[25] )
  {
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v13 = v76;
    do
    {
      v72 = 0;
      v14 = *(__int64 (__fastcall **)(struct IRepoWriter *, struct IRepoBuild *, _QWORD *, _QWORD *, struct IRepoCulture *, _BYTE **))(*(_QWORD *)v5 + 56LL);
      if ( *((_QWORD *)v11 + 10) )
      {
        v15 = (_QWORD *)RepoMan::utf8_to_wstring(WideCharStr, v11 + 64);
        v16 = v15;
        v7 |= 1u;
        v71 = v7;
        if ( v15[3] > 7u )
          v16 = (_QWORD *)*v15;
      }
      else
      {
        v16 = 0;
      }
      v49 = (_QWORD *)RepoMan::utf8_to_wstring(v82, v11 + 32);
      if ( v49[3] > 7u )
        v49 = (_QWORD *)*v49;
      v50 = v14(v5, v13, v49, v16, v81, &v72);
      RepoMan::RaiseExceptionIfFailed((RepoMan *)v50, 109, (int)"src\\repoman\\src\\inc\\MasterDescriptor.hpp", v51);
      std::wstring::_Tidy_deallocate(v82);
      *(_QWORD *)v82 = 19937;
      v83 = si128;
      if ( (v7 & 1) != 0 )
      {
        v7 &= ~1u;
        v71 = v7;
        std::wstring::_Tidy_deallocate(WideCharStr);
      }
      v53 = (_BYTE *)**((_QWORD **)v11 + 12);
      if ( !v53[25] )
      {
        do
        {
          v54 = v53 + 32;
          v55 = *(__int64 (__fastcall **)(struct IRepoWriter *, struct IRepoBuild *, _BYTE *, _QWORD))(*(_QWORD *)v5 + 72LL);
          v56 = Block;
          v57 = (_BYTE *)*((_QWORD *)Block + 1);
          *(_QWORD *)&v80 = v57;
          DWORD2(v80) = 0;
          inserted = Block;
          while ( !v57[25] )
          {
            *(_QWORD *)&v80 = v57;
            v59 = std::less<void>::operator()<std::string &,std::string &>(ii, v57 + 32, v53 + 32);
            DWORD2(v80) = v59 == 0;
            if ( !v59 )
              inserted = v57;
            ii = v57 + 16;
            if ( !v59 )
              ii = v57;
            v57 = *(_BYTE **)ii;
          }
          if ( inserted[25]
            || (unsigned __int8)std::less<void>::operator()<std::string &,std::string &>(ii, v53 + 32, inserted + 32) )
          {
            if ( v74 == 0x38E38E38E38E38ELL )
              std::_Throw_tree_length_error();
            p_Block = &Block;
            v79 = 0;
            v60 = malloc(0x48u);
            v61 = v60;
            if ( !v60 )
              std::_Xbad_alloc();
            v79 = v60;
            v62 = v60 + 4;
            *(_QWORD *)WideCharStr = v60 + 4;
            *((_OWORD *)v60 + 2) = 0;
            v60[6] = 0;
            v60[7] = 0;
            if ( *((_QWORD *)v53 + 7) > 0xFu )
              v54 = *(_OWORD **)v54;
            std::string::_Construct<2,char const *>(v60 + 4, v54, *((_QWORD *)v53 + 6));
            v62[4] = 0;
            *v61 = v56;
            v61[1] = v56;
            v61[2] = v56;
            *((_WORD *)v61 + 12) = 0;
            v79 = 0;
            *(_OWORD *)WideCharStr = v80;
            inserted = (_BYTE *)std::_Tree_val<std::_Tree_simple_types<std::pair<enum _REPOMAN_PROGRESS_SCENARIO const,unsigned __int64>>>::_Insert_node(
                                  &Block,
                                  WideCharStr,
                                  v61);
          }
          v63 = v55(v77, v76, v72, *((_QWORD *)inserted + 8));
          RepoMan::RaiseExceptionIfFailed((RepoMan *)v63, 113, (int)"src\\repoman\\src\\inc\\MasterDescriptor.hpp", v64);
          v65 = *((_QWORD *)v53 + 2);
          if ( *(_BYTE *)(v65 + 25) )
          {
            for ( n = *((_QWORD *)v53 + 1); !*(_BYTE *)(n + 25) && v53 == *(_BYTE **)(n + 16); n = *(_QWORD *)(n + 8) )
              v53 = (_BYTE *)n;
            v53 = (_BYTE *)n;
          }
          else
          {
            v53 = (_BYTE *)*((_QWORD *)v53 + 2);
            for ( ii = *(_BYTE **)v65; !ii[25]; ii = *(_BYTE **)ii )
              v53 = ii;
          }
          v5 = v77;
        }
        while ( !v53[25] );
        v7 = v71;
        v13 = v76;
      }
      v67 = v72;
      if ( v72 )
      {
        v72 = 0;
        (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v67 + 16LL))(v67);
      }
      v68 = (const CHAR **)*((_QWORD *)v11 + 2);
      if ( *((_BYTE *)v68 + 25) )
      {
        for ( jj = (const CHAR *)*((_QWORD *)v11 + 1);
              !jj[25] && v11 == *((const CHAR **)jj + 2);
              jj = (const CHAR *)*((_QWORD *)jj + 1) )
        {
          v11 = jj;
        }
        v11 = jj;
      }
      else
      {
        v11 = (const CHAR *)*((_QWORD *)v11 + 2);
        for ( kk = *v68; !kk[25]; kk = *(const CHAR **)kk )
          v11 = kk;
      }
    }
    while ( !v11[25] );
    v9 = (__int64 **)Block;
  }
  std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,RepoMan::ComPtr<IRepoOperation>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::string const,RepoMan::ComPtr<IRepoOperation>>,void *>>>(
    (__int64)&Block,
    (__int64)&Block,
    v9[1]);
  free(Block);
}

```

## disassembly

```asm
0x1800c6940  mov     rax, rsp
0x1800c6943  mov     [rax+8], rbx
0x1800c6947  push    rbp
0x1800c6948  push    rsi
0x1800c6949  push    rdi
0x1800c694a  push    r12
0x1800c694c  push    r13
0x1800c694e  push    r14
0x1800c6950  push    r15
0x1800c6952  lea     rbp, [rax-58h]
0x1800c6956  sub     rsp, 120h
0x1800c695d  movaps  xmmword ptr [rax-48h], xmm6
0x1800c6961  mov     rax, cs:__security_cookie
0x1800c6968  xor     rax, rsp
0x1800c696b  mov     [rbp+50h+var_50], rax
0x1800c696f  mov     [rbp+50h+var_A0], r9
0x1800c6973  mov     rsi, r8
0x1800c6976  mov     [rsp+150h+var_E8], r8
0x1800c697b  mov     r12, rdx
0x1800c697e  mov     [rsp+150h+var_E0], rdx
0x1800c6983  mov     r13, rcx
0x1800c6986  mov     qword ptr [rbp+50h+WideCharStr], rcx
0x1800c698a  xor     r15d, r15d
0x1800c698d  mov     r14d, r15d
0x1800c6990  mov     dword ptr [rsp+150h+var_110], r15d
0x1800c6995  mov     [rsp+150h+Block], r15
0x1800c699a  mov     [rsp+150h+var_F8], r15
0x1800c699f  lea     ecx, [r15+48h]; Size
0x1800c69a3  call    cs:__imp_malloc
0x1800c69a9  mov     rbx, rax
0x1800c69ac  test    rax, rax
0x1800c69af  jz      loc_1800C709E
0x1800c69b5  mov     [rax], rax
0x1800c69b8  mov     [rax+8], rax
0x1800c69bc  mov     [rax+10h], rax
0x1800c69c0  mov     word ptr [rax+18h], 101h
0x1800c69c6  mov     [rsp+150h+Block], rax
0x1800c69cb  mov     rdi, [r13+30h]
0x1800c69cf  mov     rdi, [rdi]
0x1800c69d2  cmp     [rdi+19h], r15b
0x1800c69d6  jz      short loc_1800C6A3F
0x1800c69d8  mov     rdi, [r13+20h]
0x1800c69dc  mov     rdi, [rdi]
0x1800c69df  cmp     [rdi+19h], r15b
0x1800c69e3  jnz     loc_1800C7048
0x1800c69e9  movdqa  xmm6, cs:__xmm@000000000000000f0000000000000000
0x1800c69f1  mov     r13, [rsp+150h+var_E8]
0x1800c69f6  mov     [rsp+150h+var_108], r15
0x1800c69fb  mov     rax, [r12]
0x1800c69ff  mov     r15, [rax+38h]
0x1800c6a03  cmp     qword ptr [rdi+50h], 0
0x1800c6a08  jz      loc_1800C6D90
0x1800c6a0e  lea     rdx, [rdi+40h]; lpMultiByteStr
0x1800c6a12  lea     rcx, [rbp+50h+WideCharStr]; lpWideCharStr
0x1800c6a16  call    ?utf8_to_wstring@RepoMan@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@@Z; RepoMan::utf8_to_wstring(std::string const &)
0x1800c6a1b  mov     rbx, rax
0x1800c6a1e  or      r14d, 1
0x1800c6a22  mov     dword ptr [rsp+150h+var_110], r14d
0x1800c6a27  cmp     qword ptr [rax+18h], 7
0x1800c6a2c  jbe     loc_1800C6D92
0x1800c6a32  mov     rbx, [rax]
0x1800c6a35  jmp     loc_1800C6D92
0x1800c6a3a  mov     rsi, [rsp+150h+var_E8]
0x1800c6a3f  lea     r14, [rdi+20h]
0x1800c6a43  mov     qword ptr [rbp+50h+var_C0], r14
0x1800c6a47  mov     [rsp+150h+var_F0], r15
0x1800c6a4c  mov     rax, [r12]
0x1800c6a50  mov     rbx, [rax+40h]
0x1800c6a54  mov     rdx, r14; lpMultiByteStr
0x1800c6a57  lea     rcx, [rbp+50h+var_98]; lpWideCharStr
0x1800c6a5b  call    ?utf8_to_wstring@RepoMan@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@@Z; RepoMan::utf8_to_wstring(std::string const &)
0x1800c6a60  nop
0x1800c6a61  cmp     qword ptr [rax+18h], 7
0x1800c6a66  jbe     short loc_1800C6A6B
0x1800c6a68  mov     rax, [rax]
0x1800c6a6b  lea     r9, [rsp+150h+var_F0]
0x1800c6a70  mov     r8, rax
0x1800c6a73  mov     rdx, rsi
0x1800c6a76  mov     rcx, r12
0x1800c6a79  mov     rax, rbx
0x1800c6a7c  call    cs:__guard_dispatch_icall_fptr
0x1800c6a82  mov     ecx, eax; this
0x1800c6a84  lea     r8, aSrcRepomanSrcI_16; "src\\repoman\\src\\inc\\MasterDescripto"...
0x1800c6a8b  mov     edx, 56h ; 'V'; int
0x1800c6a90  call    ?RaiseExceptionIfFailed@RepoMan@@YAXJHQEBD@Z; RepoMan::RaiseExceptionIfFailed(long,int,char const * const)
0x1800c6a95  nop
0x1800c6a96  lea     rcx, [rbp+50h+var_98]
0x1800c6a9a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c6a9f  mov     rbx, [r14+20h]
0x1800c6aa3  mov     rbx, [rbx]
0x1800c6aa6  cmp     [rbx+19h], r15b
0x1800c6aaa  jnz     loc_1800C6BD2
0x1800c6ab0  mov     r13, [rsp+150h+var_E8]
0x1800c6ab5  mov     r14, [rbp+50h+var_A0]
0x1800c6ab9  lea     rdx, [rbx+20h]; lpMultiByteStr
0x1800c6abd  mov     [rsp+150h+var_108], r15
0x1800c6ac2  mov     esi, r15d
0x1800c6ac5  cmp     [rdx+20h], r15b
0x1800c6ac9  setnz   sil
0x1800c6acd  mov     rax, [r12]
0x1800c6ad1  mov     r15, [rax+0E0h]
0x1800c6ad8  lea     rcx, [rbp+50h+var_98]; lpWideCharStr
0x1800c6adc  call    ?utf8_to_wstring@RepoMan@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@@Z; RepoMan::utf8_to_wstring(std::string const &)
0x1800c6ae1  nop
0x1800c6ae2  cmp     qword ptr [rax+18h], 7
0x1800c6ae7  jbe     short loc_1800C6AEC
0x1800c6ae9  mov     rax, [rax]
0x1800c6aec  lea     rcx, [rsp+150h+var_108]
0x1800c6af1  mov     [rsp+150h+var_128], rcx
0x1800c6af6  mov     dword ptr [rsp+150h+var_130], esi
0x1800c6afa  mov     r9, rax
0x1800c6afd  mov     r8, r14
0x1800c6b00  mov     rdx, r13
0x1800c6b03  mov     rcx, r12
0x1800c6b06  mov     rax, r15
0x1800c6b09  call    cs:__guard_dispatch_icall_fptr
0x1800c6b0f  mov     ecx, eax; this
0x1800c6b11  lea     r8, aSrcRepomanSrcI_16; "src\\repoman\\src\\inc\\MasterDescripto"...
0x1800c6b18  mov     edx, 5Fh ; '_'; int
0x1800c6b1d  call    ?RaiseExceptionIfFailed@RepoMan@@YAXJHQEBD@Z; RepoMan::RaiseExceptionIfFailed(long,int,char const * const)
0x1800c6b22  nop
0x1800c6b23  lea     rcx, [rbp+50h+var_98]
0x1800c6b27  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c6b2c  mov     rax, [r12]
0x1800c6b30  mov     r9, [rsp+150h+var_108]
0x1800c6b35  mov     r8, [rsp+150h+var_F0]
0x1800c6b3a  mov     rdx, r13
0x1800c6b3d  mov     rcx, r12
0x1800c6b40  mov     rax, [rax+58h]
0x1800c6b44  call    cs:__guard_dispatch_icall_fptr
0x1800c6b4a  mov     ecx, eax; this
0x1800c6b4c  lea     r8, aSrcRepomanSrcI_16; "src\\repoman\\src\\inc\\MasterDescripto"...
0x1800c6b53  mov     edx, 60h ; '`'; int
0x1800c6b58  call    ?RaiseExceptionIfFailed@RepoMan@@YAXJHQEBD@Z; RepoMan::RaiseExceptionIfFailed(long,int,char const * const)
0x1800c6b5d  nop
0x1800c6b5e  mov     rcx, [rsp+150h+var_108]
0x1800c6b63  xor     r15d, r15d
0x1800c6b66  test    rcx, rcx
0x1800c6b69  jz      short loc_1800C6B7D
0x1800c6b6b  mov     [rsp+150h+var_108], r15
0x1800c6b70  mov     rax, [rcx]
0x1800c6b73  mov     rax, [rax+10h]
0x1800c6b77  call    cs:__guard_dispatch_icall_fptr
0x1800c6b7d  mov     rax, [rbx+10h]
0x1800c6b81  cmp     [rax+19h], r15b
0x1800c6b85  jz      short loc_1800C6BA5
0x1800c6b87  mov     rax, [rbx+8]
0x1800c6b8b  jmp     short loc_1800C6B9A
0x1800c6b8d  cmp     rbx, [rax+10h]
0x1800c6b91  jnz     short loc_1800C6BA0
0x1800c6b93  mov     rbx, rax
0x1800c6b96  mov     rax, [rax+8]
0x1800c6b9a  cmp     [rax+19h], r15b
0x1800c6b9e  jz      short loc_1800C6B8D
0x1800c6ba0  mov     rbx, rax
0x1800c6ba3  jmp     short loc_1800C6BC0
0x1800c6ba5  mov     rbx, rax
0x1800c6ba8  mov     rcx, [rax]
0x1800c6bab  cmp     [rcx+19h], r15b
0x1800c6baf  jnz     short loc_1800C6BC0
0x1800c6bb1  mov     rbx, rcx
0x1800c6bb4  mov     rax, [rcx]
0x1800c6bb7  mov     rcx, rax
0x1800c6bba  cmp     [rax+19h], r15b
0x1800c6bbe  jz      short loc_1800C6BB1
0x1800c6bc0  cmp     [rbx+19h], r15b
0x1800c6bc4  jz      loc_1800C6AB9
0x1800c6bca  mov     r14, qword ptr [rbp+50h+var_C0]
0x1800c6bce  mov     r13, qword ptr [rbp+50h+WideCharStr]
0x1800c6bd2  mov     rbx, [rsp+150h+Block]
0x1800c6bd7  mov     r12, [rbx+8]
0x1800c6bdb  mov     edx, r15d
0x1800c6bde  mov     rsi, rbx
0x1800c6be1  cmp     [r12+19h], r15b
0x1800c6be6  jnz     short loc_1800C6C1F
0x1800c6be8  mov     r15, r12
0x1800c6beb  mov     r12, r15
0x1800c6bee  lea     rdx, [r15+20h]
0x1800c6bf2  mov     r8, r14
0x1800c6bf5  call    ??$?RAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAV01@@?$less@X@std@@QEBA_NAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@0@Z; std::less<void>::operator()<std::string &,std::string &>(std::string &,std::string &)
0x1800c6bfa  movzx   ecx, al
0x1800c6bfd  mov     edx, ecx
0x1800c6bff  xor     edx, 1
0x1800c6c02  test    al, al
0x1800c6c04  cmovz   rsi, r15
0x1800c6c08  lea     rax, [r15+10h]
0x1800c6c0c  test    cl, cl
0x1800c6c0e  cmovz   rax, r15
0x1800c6c12  mov     r15, [rax]
0x1800c6c15  cmp     byte ptr [r15+19h], 0
0x1800c6c1a  jz      short loc_1800C6BEB
0x1800c6c1c  xor     r15d, r15d
0x1800c6c1f  mov     qword ptr [rbp+50h+var_98], r12
0x1800c6c23  mov     dword ptr [rbp+50h+var_98+8], edx
0x1800c6c26  mov     eax, dword ptr [rbp+50h+var_98+0Ch]
0x1800c6c29  mov     dword ptr [rbp+50h+var_98+0Ch], eax
0x1800c6c2c  cmp     [rsi+19h], r15b
0x1800c6c30  jnz     short loc_1800C6C46
0x1800c6c32  lea     r8, [rsi+20h]
0x1800c6c36  mov     rdx, r14
0x1800c6c39  call    ??$?RAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAV01@@?$less@X@std@@QEBA_NAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@0@Z; std::less<void>::operator()<std::string &,std::string &>(std::string &,std::string &)
0x1800c6c3e  test    al, al
0x1800c6c40  jz      loc_1800C6D13
0x1800c6c46  mov     rax, 38E38E38E38E38Eh
0x1800c6c50  cmp     [rsp+150h+var_F8], rax
0x1800c6c55  jz      loc_1800C70AA
0x1800c6c5b  lea     rax, [rsp+150h+Block]
0x1800c6c60  mov     [rsp+150h+var_D8], rax
0x1800c6c65  mov     [rbp+50h+var_D0], r15
0x1800c6c69  mov     ecx, 48h ; 'H'; Size
0x1800c6c6e  call    cs:__imp_malloc
0x1800c6c74  mov     rsi, rax
0x1800c6c77  test    rax, rax
0x1800c6c7a  jz      loc_1800C70A4
0x1800c6c80  mov     [rbp+50h+var_D0], rax
0x1800c6c84  lea     r15, [rax+20h]
0x1800c6c88  mov     qword ptr [rbp+50h+var_C0], r15
0x1800c6c8c  xorps   xmm0, xmm0
0x1800c6c8f  movups  xmmword ptr [r15], xmm0
0x1800c6c93  mov     qword ptr [r15+10h], 0
0x1800c6c9b  mov     qword ptr [r15+18h], 0
0x1800c6ca3  mov     r8, [r14+10h]
0x1800c6ca7  cmp     qword ptr [r14+18h], 0Fh
0x1800c6cac  jbe     short loc_1800C6CB1
0x1800c6cae  mov     r14, [r14]
0x1800c6cb1  mov     rdx, r14
0x1800c6cb4  mov     rcx, r15
0x1800c6cb7  call    ??$_Construct@$01PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<2,char const *>(char const * const,unsigned __int64)
0x1800c6cbc  nop
0x1800c6cbd  mov     rax, [rsp+150h+var_F0]
0x1800c6cc2  mov     [r15+20h], rax
0x1800c6cc6  mov     rcx, [rsp+150h+var_F0]
0x1800c6ccb  xor     r15d, r15d
0x1800c6cce  test    rcx, rcx
0x1800c6cd1  jz      short loc_1800C6CE0
0x1800c6cd3  mov     rax, [rcx]
0x1800c6cd6  mov     rax, [rax+8]
0x1800c6cda  call    cs:__guard_dispatch_icall_fptr
0x1800c6ce0  mov     [rsi], rbx
0x1800c6ce3  mov     [rsi+8], rbx
0x1800c6ce7  mov     [rsi+10h], rbx
0x1800c6ceb  mov     [rsi+18h], r15w
0x1800c6cf0  mov     [rbp+50h+var_D0], r15
0x1800c6cf4  movups  xmm0, xmmword ptr [rbp+50h+var_98]
0x1800c6cf8  movdqu  [rbp+50h+var_C0], xmm0
0x1800c6cfd  mov     r8, rsi
0x1800c6d00  lea     rdx, [rbp+50h+var_C0]
0x1800c6d04  lea     rcx, [rsp+150h+Block]
0x1800c6d09  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4_REPOMAN_PROGRESS_SCENARIO@@_K@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBW4_REPOMAN_PROGRESS_SCENARIO@@_K@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBW4_REPOMAN_PROGRESS_SCENARIO@@_K@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_REPOMAN_PROGRESS_SCENARIO const,unsigned __int64>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<_REPOMAN_PROGRESS_SCENARIO const,unsigned __int64>,void *> *>,std::_Tree_node<std::pair<_REPOMAN_PROGRESS_SCENARIO const,unsigned __int64>,void *> * const)
0x1800c6d0e  mov     rbx, [rsp+150h+Block]
0x1800c6d13  mov     rcx, [rsp+150h+var_F0]
0x1800c6d18  test    rcx, rcx
0x1800c6d1b  jz      short loc_1800C6D34
0x1800c6d1d  mov     [rsp+150h+var_F0], r15
0x1800c6d22  mov     rax, [rcx]
0x1800c6d25  mov     rax, [rax+10h]
0x1800c6d29  call    cs:__guard_dispatch_icall_fptr
0x1800c6d2f  mov     rbx, [rsp+150h+Block]
0x1800c6d34  mov     rax, [rdi+10h]
0x1800c6d38  cmp     [rax+19h], r15b
0x1800c6d3c  jz      short loc_1800C6D5C
0x1800c6d3e  mov     rax, [rdi+8]
0x1800c6d42  jmp     short loc_1800C6D51
0x1800c6d44  cmp     rdi, [rax+10h]
0x1800c6d48  jnz     short loc_1800C6D57
0x1800c6d4a  mov     rdi, rax
0x1800c6d4d  mov     rax, [rax+8]
0x1800c6d51  cmp     [rax+19h], r15b
0x1800c6d55  jz      short loc_1800C6D44
0x1800c6d57  mov     rdi, rax
0x1800c6d5a  jmp     short loc_1800C6D77
0x1800c6d5c  mov     rdi, rax
0x1800c6d5f  mov     rcx, [rax]
0x1800c6d62  cmp     [rcx+19h], r15b
0x1800c6d66  jnz     short loc_1800C6D77
0x1800c6d68  mov     rdi, rcx
0x1800c6d6b  mov     rax, [rcx]
0x1800c6d6e  mov     rcx, rax
0x1800c6d71  cmp     [rax+19h], r15b
0x1800c6d75  jz      short loc_1800C6D68
0x1800c6d77  cmp     [rdi+19h], r15b
0x1800c6d7b  mov     r12, [rsp+150h+var_E0]
0x1800c6d80  jz      loc_1800C6A3A
0x1800c6d86  mov     r14d, dword ptr [rsp+150h+var_110]
0x1800c6d8b  jmp     loc_1800C69D8
0x1800c6d90  xor     ebx, ebx
0x1800c6d92  lea     rdx, [rdi+20h]; lpMultiByteStr
0x1800c6d96  lea     rcx, [rbp+50h+var_98]; lpWideCharStr
0x1800c6d9a  call    ?utf8_to_wstring@RepoMan@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@@Z; RepoMan::utf8_to_wstring(std::string const &)
0x1800c6d9f  nop
0x1800c6da0  cmp     qword ptr [rax+18h], 7
0x1800c6da5  jbe     short loc_1800C6DAA
0x1800c6da7  mov     rax, [rax]
0x1800c6daa  lea     rcx, [rsp+150h+var_108]
0x1800c6daf  mov     [rsp+150h+var_128], rcx
0x1800c6db4  mov     rcx, [rbp+50h+var_A0]
0x1800c6db8  mov     [rsp+150h+var_130], rcx
0x1800c6dbd  mov     r9, rbx
0x1800c6dc0  mov     r8, rax
0x1800c6dc3  mov     rdx, r13
  ... truncated ...
```
