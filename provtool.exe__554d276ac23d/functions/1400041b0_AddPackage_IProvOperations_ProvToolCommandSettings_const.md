# AddPackage(IProvOperations *,_ProvToolCommandSettings const &)

- ea: `0x1400041b0`
- end: `0x1400045bf`
- name: `?AddPackage@@YAJPEAUIProvOperations@@AEBU_ProvToolCommandSettings@@@Z`
- size: `1039`
- prototype: `__int64 __fastcall(struct IProvOperations *, const unsigned __int16 **, __int64, const char *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1400059ac`

## callees

- `0x140003598`
- `0x1400041b0`
- `0x140008a90`
- `0x140008b88`
- `0x140010010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1400042d3`
- `msvcrt!??3@YAXPEAX@Z` at `0x1400042fe`
- `msvcrt!??3@YAXPEAX@Z` at `0x1400043c5`
- `msvcrt!??3@YAXPEAX@Z` at `0x1400043d3`
- `msvcrt!??3@YAXPEAX@Z` at `0x1400043e4`
- `msvcrt!??3@YAXPEAX@Z` at `0x140004409`
- `msvcrt!??3@YAXPEAX@Z` at `0x1400044cd`
- `msvcrt!??3@YAXPEAX@Z` at `0x1400042d3`
- `msvcrt!??3@YAXPEAX@Z` at `0x1400042fe`
- `msvcrt!??3@YAXPEAX@Z` at `0x1400043c5`
- `msvcrt!??3@YAXPEAX@Z` at `0x1400043d3`
- `msvcrt!??3@YAXPEAX@Z` at `0x1400043e4`
- `msvcrt!??3@YAXPEAX@Z` at `0x140004409`
- `msvcrt!??3@YAXPEAX@Z` at `0x1400044cd`

## pseudocode

```c
__int64 __fastcall AddPackage(struct IProvOperations *a1, const unsigned __int16 **a2, __int64 a3, const char *a4)
{
  TokenizedString *v6; // rax
  _QWORD *v7; // rdx
  void *v8; // rbx
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // rcx
  unsigned int v11; // edi
  __int64 result; // rax
  const unsigned __int16 *v13; // rdi
  const unsigned __int16 *v14; // rbx
  char *v15; // rdx
  char *v16; // rcx
  const unsigned __int16 **v17; // rsi
  unsigned __int64 v18; // rcx
  unsigned int v19; // ebx
  const unsigned __int16 *v20; // r15
  __int64 v21; // r15
  int v22; // [rsp+20h] [rbp-108h]
  const unsigned __int16 *v23; // [rsp+50h] [rbp-D8h] BYREF
  __int128 v24; // [rsp+58h] [rbp-D0h] BYREF
  char *v25; // [rsp+68h] [rbp-C0h]
  __int128 v26; // [rsp+70h] [rbp-B8h]
  __int64 v27; // [rsp+80h] [rbp-A8h]
  __int128 v28; // [rsp+88h] [rbp-A0h] BYREF
  __int128 v29; // [rsp+98h] [rbp-90h] BYREF
  __int128 v30; // [rsp+A8h] [rbp-80h]
  void *v31; // [rsp+B8h] [rbp-70h] BYREF
  __int128 v32; // [rsp+D0h] [rbp-58h]
  __int64 v33; // [rsp+E0h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]
  int v35; // [rsp+138h] [rbp+10h] BYREF

  try
  {
    if ( *(_DWORD *)a2 )
    {
      v35 = 59;
      TokenizedString::TokenizedString((TokenizedString *)&v24, a2[1], (const unsigned __int16 *)&v35);
      v28 = 0;
      v29 = 0;
      v30 = 0;
      if ( *((_DWORD *)a2 + 4) )
      {
        v6 = TokenizedString::TokenizedString((TokenizedString *)&v31, a2[3], (const unsigned __int16 *)&v35);
        if ( &v28 != (__int128 *)v6 )
        {
          v28 = *(_OWORD *)v6;
          *(_QWORD *)&v29 = *((_QWORD *)v6 + 2);
          *(_QWORD *)v6 = 0;
          *((_QWORD *)v6 + 1) = 0;
          *((_QWORD *)v6 + 2) = 0;
        }
        v7 = (_QWORD *)((char *)v6 + 24);
        if ( (char *)&v29 + 8 != (char *)v6 + 24 )
        {
          *((_QWORD *)&v29 + 1) = *v7;
          v30 = *((_OWORD *)v6 + 2);
          *v7 = 0;
          *((_QWORD *)v6 + 4) = 0;
          *((_QWORD *)v6 + 5) = 0;
        }
        if ( (_QWORD)v32 )
        {
          operator delete((void *)v32);
          v32 = 0;
          v33 = 0;
        }
        if ( v31 )
          operator delete(v31);
      }
      v8 = (void *)v28;
      v9 = (__int64)(*((_QWORD *)&v28 + 1) - v28) >> 3;
      if ( v9 > 0xFFFFFFFF )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x76,
          (unsigned int)"onecoreuap\\admin\\prov\\provtool\\provtool.cpp",
          v9 > 0xFFFFFFFF ? (const char *)0x80070216LL : 0,
          v22);
      v10 = (__int64)(*((_QWORD *)&v24 + 1) - v24) >> 3;
      if ( v10 > 0xFFFFFFFF )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x76,
          (unsigned int)"onecoreuap\\admin\\prov\\provtool\\provtool.cpp",
          v10 > 0xFFFFFFFF ? (const char *)0x80070216LL : 0,
          v22);
      v11 = (*(__int64 (__fastcall **)(struct IProvOperations *, _QWORD, _QWORD, _QWORD, _DWORD, bool, _DWORD, _DWORD))(*(_QWORD *)a1 + 24LL))(
              a1,
              v24,
              (unsigned int)((__int64)(*((_QWORD *)&v24 + 1) - v24) >> 3),
              v28,
              (__int64)(*((_QWORD *)&v28 + 1) - v28) >> 3,
              *((_DWORD *)a2 + 15) != 0,
              *((_DWORD *)a2 + 15),
              *((_DWORD *)a2 + 16));
      if ( *((_QWORD *)&v29 + 1) )
        operator delete(*((void **)&v29 + 1));
      if ( v8 )
        operator delete(v8);
      if ( (_QWORD)v26 )
      {
        operator delete((void *)v26);
        v26 = 0;
        v27 = 0;
      }
      if ( (_QWORD)v24 )
        operator delete((void *)v24);
      result = v11;
    }
    else
    {
      v13 = a2[13];
      v14 = a2[12];
      if ( v14 == v13 )
      {
        result = 2147942487LL;
      }
      else
      {
        v24 = 0;
        v15 = 0;
        v25 = 0;
        v16 = (char *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
        v17 = 0;
        while ( v14 != v13 )
        {
          if ( *((_QWORD *)v14 + 3) < 8u )
            v20 = v14;
          else
            v20 = *(const unsigned __int16 **)v14;
          v23 = v20;
          if ( &v23 >= (const unsigned __int16 **)v16 || v17 > &v23 )
          {
            if ( v16 == v15 )
            {
              std::vector<unsigned short const *>::_Reserve(&v24);
              v15 = v25;
              v16 = (char *)*((_QWORD *)&v24 + 1);
              v17 = (const unsigned __int16 **)v24;
            }
            *(_QWORD *)v16 = v20;
          }
          else
          {
            v21 = (char *)&v23 - (char *)v17;
            if ( v16 == v15 )
            {
              std::vector<unsigned short const *>::_Reserve(&v24);
              v15 = v25;
              v16 = (char *)*((_QWORD *)&v24 + 1);
              v17 = (const unsigned __int16 **)v24;
            }
            *(_QWORD *)v16 = v17[v21 >> 3];
          }
          v16 += 8;
          *((_QWORD *)&v24 + 1) = v16;
          v14 += 16;
        }
        v18 = (v16 - (char *)v17) >> 3;
        if ( v18 > 0xFFFFFFFF )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xA5,
            (unsigned int)"onecoreuap\\admin\\prov\\provtool\\provtool.cpp",
            v18 > 0xFFFFFFFF ? (const char *)0x80070216LL : 0,
            v22);
        v19 = (*(__int64 (__fastcall **)(struct IProvOperations *, const unsigned __int16 **, _QWORD, _QWORD, _DWORD, int, int, _DWORD))(*(_QWORD *)a1 + 24LL))(
                a1,
                v17,
                (unsigned int)v18,
                0,
                0,
                1,
                5,
                *((_DWORD *)a2 + 16));
        if ( v17 )
          operator delete(v17);
        result = v19;
      }
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xAB,
                           (unsigned int)"onecoreuap\\admin\\prov\\provtool\\provtool.cpp",
                           a4);
  }
  return result;
}

```

## disassembly

```asm
0x1400041b0  mov     rax, rsp
0x1400041b3  push    rbx
0x1400041b4  push    rsi
0x1400041b5  push    rdi
0x1400041b6  push    r12
0x1400041b8  push    r14
0x1400041ba  push    r15
0x1400041bc  sub     rsp, 0F8h
0x1400041c3  mov     r14, rdx
0x1400041c6  mov     r12, rcx
0x1400041c9  cmp     dword ptr [rdx], 0
0x1400041cc  jz      loc_140004416
0x1400041d2  mov     dword ptr [rax+10h], 3Bh ; ';'
0x1400041d9  lea     r8, [rax+10h]; unsigned __int16 *
0x1400041dd  mov     rdx, [rdx+8]; unsigned __int16 *
0x1400041e1  lea     rcx, [rsp+128h+var_D0]; this
0x1400041e6  call    ??0TokenizedString@@QEAA@PEBG0@Z; TokenizedString::TokenizedString(ushort const *,ushort const *)
0x1400041eb  nop
0x1400041ec  xorps   xmm0, xmm0
0x1400041ef  movdqu  [rsp+128h+var_A0], xmm0
0x1400041f8  xorps   xmm1, xmm1
0x1400041fb  movdqu  [rsp+128h+var_90], xmm1
0x140004204  movdqu  [rsp+128h+var_80], xmm0
0x14000420d  cmp     dword ptr [r14+10h], 0
0x140004212  jz      loc_140004304
0x140004218  lea     r8, [rsp+128h+arg_8]; unsigned __int16 *
0x140004220  mov     rdx, [r14+18h]; unsigned __int16 *
0x140004224  lea     rcx, [rsp+128h+var_70]; this
0x14000422c  call    ??0TokenizedString@@QEAA@PEBG0@Z; TokenizedString::TokenizedString(ushort const *,ushort const *)
0x140004231  mov     rdx, rax
0x140004234  lea     rax, [rsp+128h+var_A0]
0x14000423c  cmp     rax, rdx
0x14000423f  jz      short loc_14000427B
0x140004241  mov     rcx, [rdx]
0x140004244  mov     qword ptr [rsp+128h+var_A0], rcx
0x14000424c  mov     rcx, [rdx+8]
0x140004250  mov     qword ptr [rsp+128h+var_A0+8], rcx
0x140004258  mov     rax, [rdx+10h]
0x14000425c  mov     qword ptr [rsp+128h+var_90], rax
0x140004264  mov     qword ptr [rdx], 0
0x14000426b  mov     qword ptr [rdx+8], 0
0x140004273  mov     qword ptr [rdx+10h], 0
0x14000427b  add     rdx, 18h
0x14000427f  lea     rax, [rsp+128h+var_90+8]
0x140004287  cmp     rax, rdx
0x14000428a  jz      short loc_1400042C6
0x14000428c  mov     rax, [rdx]
0x14000428f  mov     qword ptr [rsp+128h+var_90+8], rax
0x140004297  mov     rax, [rdx+8]
0x14000429b  mov     qword ptr [rsp+128h+var_80], rax
0x1400042a3  mov     rax, [rdx+10h]
0x1400042a7  mov     qword ptr [rsp+128h+var_80+8], rax
0x1400042af  mov     qword ptr [rdx], 0
0x1400042b6  mov     qword ptr [rdx+8], 0
0x1400042be  mov     qword ptr [rdx+10h], 0
0x1400042c6  mov     rcx, qword ptr [rsp+128h+var_58]
0x1400042ce  test    rcx, rcx
0x1400042d1  jz      short loc_1400042F1
0x1400042d3  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1400042d9  xorps   xmm0, xmm0
0x1400042dc  movdqu  [rsp+128h+var_58], xmm0
0x1400042e5  mov     [rsp+128h+var_48], 0
0x1400042f1  mov     rcx, [rsp+128h+var_70]
0x1400042f9  test    rcx, rcx
0x1400042fc  jz      short loc_140004304
0x1400042fe  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140004304  mov     edi, [r14+3Ch]
0x140004308  xor     esi, esi
0x14000430a  test    edi, edi
0x14000430c  setnz   sil
0x140004310  mov     rbx, qword ptr [rsp+128h+var_A0]
0x140004318  mov     rcx, qword ptr [rsp+128h+var_A0+8]
0x140004320  sub     rcx, rbx
0x140004323  sar     rcx, 3
0x140004327  mov     eax, 0FFFFFFFFh
0x14000432c  cmp     rcx, rax
0x14000432f  mov     r10d, ecx
0x140004332  jbe     short loc_140004337
0x140004334  mov     r10d, eax
0x140004337  cmp     rax, rcx
0x14000433a  sbb     r9d, r9d
0x14000433d  mov     edx, 80070216h
0x140004342  and     r9d, edx; char *
0x140004345  mov     r11, [rsp+128h]
0x14000434d  cmp     rcx, rax
0x140004350  ja      loc_140004580
0x140004356  mov     rcx, qword ptr [rsp+128h+var_D0+8]
0x14000435b  sub     rcx, qword ptr [rsp+128h+var_D0]
0x140004360  sar     rcx, 3
0x140004364  cmp     rcx, rax
0x140004367  mov     r8d, ecx
0x14000436a  jbe     short loc_14000436F
0x14000436c  mov     r8d, eax
0x14000436f  cmp     rax, rcx
0x140004372  sbb     r9d, r9d
0x140004375  and     r9d, edx; char *
0x140004378  mov     r11, [rsp+128h]
0x140004380  cmp     rcx, rax
0x140004383  ja      loc_140004594
0x140004389  mov     rax, [r12]
0x14000438d  mov     ecx, [r14+40h]
0x140004391  mov     [rsp+128h+var_F0], ecx
0x140004395  mov     [rsp+128h+var_F8], edi
0x140004399  mov     [rsp+128h+var_100], esi
0x14000439d  mov     [rsp+128h+var_108], r10d
0x1400043a2  mov     r9, rbx
0x1400043a5  mov     rdx, qword ptr [rsp+128h+var_D0]
0x1400043aa  mov     rcx, r12
0x1400043ad  mov     rax, [rax+18h]
0x1400043b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400043b6  mov     edi, eax
0x1400043b8  mov     rcx, qword ptr [rsp+128h+var_90+8]
0x1400043c0  test    rcx, rcx
0x1400043c3  jz      short loc_1400043CB
0x1400043c5  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1400043cb  test    rbx, rbx
0x1400043ce  jz      short loc_1400043DA
0x1400043d0  mov     rcx, rbx
0x1400043d3  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1400043d9  nop
0x1400043da  mov     rcx, qword ptr [rsp+128h+var_B8]
0x1400043df  test    rcx, rcx
0x1400043e2  jz      short loc_1400043FF
0x1400043e4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1400043ea  xorps   xmm0, xmm0
0x1400043ed  movdqu  [rsp+128h+var_B8], xmm0
0x1400043f3  mov     [rsp+128h+var_A8], 0
0x1400043ff  mov     rcx, qword ptr [rsp+128h+var_D0]
0x140004404  test    rcx, rcx
0x140004407  jz      short loc_14000440F
0x140004409  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000440f  mov     eax, edi
0x140004411  jmp     loc_14000456F
0x140004416  mov     rdi, [rdx+68h]
0x14000441a  mov     rbx, [rdx+60h]
0x14000441e  cmp     rbx, rdi
0x140004421  jnz     short loc_14000442D
0x140004423  mov     eax, 80070057h
0x140004428  jmp     loc_14000456F
0x14000442d  xorps   xmm1, xmm1
0x140004430  movdqu  [rsp+128h+var_D0], xmm1
0x140004436  xor     edx, edx
0x140004438  mov     [rsp+128h+var_C0], rdx
0x14000443d  xorps   xmm0, xmm0
0x140004440  psrldq  xmm0, 8
0x140004445  movq    rcx, xmm0
0x14000444a  movq    rsi, xmm1
0x14000444f  cmp     rbx, rdi
0x140004452  jnz     loc_1400044DA
0x140004458  sub     rcx, rsi
0x14000445b  sar     rcx, 3
0x14000445f  mov     eax, 0FFFFFFFFh
0x140004464  cmp     rcx, rax
0x140004467  mov     r8d, ecx
0x14000446a  jbe     short loc_14000446F
0x14000446c  mov     r8d, eax
0x14000446f  cmp     rax, rcx
0x140004472  sbb     r9d, r9d
0x140004475  and     r9d, 80070216h; char *
0x14000447c  mov     r10, [rsp+128h]
0x140004484  cmp     rcx, rax
0x140004487  ja      loc_1400045A9
0x14000448d  mov     rax, [r12]
0x140004491  mov     ecx, [r14+40h]
0x140004495  mov     [rsp+128h+var_F0], ecx
0x140004499  mov     [rsp+128h+var_F8], 5
0x1400044a1  mov     [rsp+128h+var_100], 1
0x1400044a9  mov     [rsp+128h+var_108], 0
0x1400044b1  xor     r9d, r9d
0x1400044b4  mov     rdx, rsi
0x1400044b7  mov     rcx, r12
0x1400044ba  mov     rax, [rax+18h]
0x1400044be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400044c3  mov     ebx, eax
0x1400044c5  test    rsi, rsi
0x1400044c8  jz      short loc_1400044D3
0x1400044ca  mov     rcx, rsi
0x1400044cd  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1400044d3  mov     eax, ebx
0x1400044d5  jmp     loc_14000456F
0x1400044da  cmp     qword ptr [rbx+18h], 8
0x1400044df  jb      short loc_1400044E6
0x1400044e1  mov     r15, [rbx]
0x1400044e4  jmp     short loc_1400044E9
0x1400044e6  mov     r15, rbx
0x1400044e9  mov     [rsp+128h+var_D8], r15
0x1400044ee  lea     rax, [rsp+128h+var_D8]
0x1400044f3  cmp     rax, rcx
0x1400044f6  jnb     short loc_140004535
0x1400044f8  lea     rax, [rsp+128h+var_D8]
0x1400044fd  cmp     rsi, rax
0x140004500  ja      short loc_140004535
0x140004502  lea     r15, [rsp+128h+var_D8]
0x140004507  sub     r15, rsi
0x14000450a  cmp     rcx, rdx
0x14000450d  jnz     short loc_140004528
0x14000450f  lea     rcx, [rsp+128h+var_D0]
0x140004514  call    ?_Reserve@?$vector@PEBGV?$allocator@PEBG@std@@@std@@IEAAX_K@Z; std::vector<ushort const *>::_Reserve(unsigned __int64)
0x140004519  mov     rdx, [rsp+128h+var_C0]
0x14000451e  mov     rcx, qword ptr [rsp+128h+var_D0+8]
0x140004523  mov     rsi, qword ptr [rsp+128h+var_D0]
0x140004528  sar     r15, 3
0x14000452c  mov     rax, [rsi+r15*8]
0x140004530  mov     [rcx], rax
0x140004533  jmp     short loc_140004556
0x140004535  cmp     rcx, rdx
0x140004538  jnz     short loc_140004553
0x14000453a  lea     rcx, [rsp+128h+var_D0]
0x14000453f  call    ?_Reserve@?$vector@PEBGV?$allocator@PEBG@std@@@std@@IEAAX_K@Z; std::vector<ushort const *>::_Reserve(unsigned __int64)
0x140004544  mov     rdx, [rsp+128h+var_C0]
0x140004549  mov     rcx, qword ptr [rsp+128h+var_D0+8]
0x14000454e  mov     rsi, qword ptr [rsp+128h+var_D0]
0x140004553  mov     [rcx], r15
0x140004556  add     rcx, 8
0x14000455a  mov     qword ptr [rsp+128h+var_D0+8], rcx
0x14000455f  add     rbx, 20h ; ' '
0x140004563  jmp     loc_14000444F
0x140004568  mov     eax, [rsp+128h+arg_8]
0x14000456f  add     rsp, 0F8h
0x140004576  pop     r15
0x140004578  pop     r14
0x14000457a  pop     r12
0x14000457c  pop     rdi
0x14000457d  pop     rsi
0x14000457e  pop     rbx
0x14000457f  retn
0x140004580  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\provtool\\prov"...
0x140004587  mov     edx, 76h ; 'v'; void *
0x14000458c  mov     rcx, r11; this
0x14000458f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140004594  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\provtool\\prov"...
0x14000459b  mov     edx, 76h ; 'v'; void *
0x1400045a0  mov     rcx, r11; this
0x1400045a3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400045a9  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\provtool\\prov"...
0x1400045b0  mov     edx, 0A5h; void *
0x1400045b5  mov     rcx, r10; this
0x1400045b8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
