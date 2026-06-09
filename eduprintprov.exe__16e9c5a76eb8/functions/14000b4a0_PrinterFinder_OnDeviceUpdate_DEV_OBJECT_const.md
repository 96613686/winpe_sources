# PrinterFinder::_OnDeviceUpdate(_DEV_OBJECT const &)

- ea: `0x14000b4a0`
- end: `0x14000b851`
- name: `?_OnDeviceUpdate@PrinterFinder@@AEAA_NAEBU_DEV_OBJECT@@@Z`
- size: `945`
- prototype: `bool __fastcall(PrinterFinder *__hidden this, const struct _DEV_OBJECT *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x14000b860`

## callees

- `0x140003144`
- `0x14000315c`
- `0x1400034f8`
- `0x14000452c`
- `0x14000b4a0`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x14000b54f`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x14000b54f`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@_N@Z` at `0x14000b719`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@_N@Z` at `0x14000b7d1`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@_N@Z` at `0x14000b719`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@_N@Z` at `0x14000b7d1`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x14000b4f6`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x14000b64a`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x14000b729`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x14000b7e1`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x14000b4f6`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x14000b64a`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x14000b729`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x14000b7e1`
- `msvcp_win!?wcout@std@@3V?$basic_ostream@GU?$char_traits@G@std@@@1@A` at `0x14000b4d4`
- `msvcp_win!?wcout@std@@3V?$basic_ostream@GU?$char_traits@G@std@@@1@A` at `0x14000b53d`
- `msvcp_win!?wcout@std@@3V?$basic_ostream@GU?$char_traits@G@std@@@1@A` at `0x14000b609`
- `msvcp_win!?wcout@std@@3V?$basic_ostream@GU?$char_traits@G@std@@@1@A` at `0x14000b712`
- `msvcp_win!?wcout@std@@3V?$basic_ostream@GU?$char_traits@G@std@@@1@A` at `0x14000b7ca`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x14000b757`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x14000b757`

## pseudocode

```c
char __fastcall PrinterFinder::_OnDeviceUpdate(PrinterFinder *this, const struct _DEV_OBJECT *a2)
{
  __int64 v4; // rax
  __int64 v5; // rax
  unsigned int v6; // r12d
  __int64 v7; // rax
  __int128 v8; // xmm6
  __m128i v9; // xmm7
  __m128i v10; // xmm8
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rdi
  int v14; // r14d
  __int64 *v15; // rbx
  __int64 v16; // xmm6_8
  __int64 v17; // rax
  int v18; // eax
  __int64 v19; // rax
  _WORD *v20; // xmm8_8
  __int64 v21; // rax
  __int64 v22; // r8
  char **v23; // rcx
  unsigned __int64 v24; // rdx
  char *v25; // r14
  __int64 v26; // rbx
  _BYTE *v27; // xmm8_8
  __int64 v28; // rax
  const wchar_t *v29; // rdi
  const wchar_t *v30; // rdx
  __int64 v31; // r8
  char *v32; // rcx
  unsigned __int64 v33; // rdx
  char *v34; // rsi
  __int64 v36; // rbx
  __int128 Buf2_8; // [rsp+28h] [rbp-99h] BYREF
  int v38; // [rsp+38h] [rbp-89h]
  __int64 v39; // [rsp+3Ch] [rbp-85h]
  int v40; // [rsp+44h] [rbp-7Dh]
  __int128 Buf1; // [rsp+48h] [rbp-79h] BYREF
  __m128i v42; // [rsp+58h] [rbp-69h]
  __int64 v43; // [rsp+68h] [rbp-59h]
  __int128 v44; // [rsp+70h] [rbp-51h] BYREF
  __m128i v45; // [rsp+80h] [rbp-41h]
  __m128i v46; // [rsp+90h] [rbp-31h]

  v4 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(std::wcout, L"  Found device: ");
  v5 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v4, *((_QWORD *)a2 + 1));
  std::basic_ostream<unsigned short>::operator<<(v5, std::endl<unsigned short,std::char_traits<unsigned short>>);
  v6 = 0;
  if ( !*((_DWORD *)a2 + 4) )
    return *((_QWORD *)this + 23) != 0;
  while ( 1 )
  {
    v7 = *((_QWORD *)a2 + 3);
    v44 = *(_OWORD *)(v7 + 48LL * v6);
    v8 = v44;
    v45 = *(__m128i *)(v7 + 48LL * v6 + 16);
    v9 = v45;
    v10 = *(__m128i *)(v7 + 48LL * v6 + 32);
    v46 = v10;
    v11 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(std::wcout, L"    ");
    v12 = std::basic_ostream<unsigned short>::operator<<(v11, v6);
    v13 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v12, L") ");
    Buf2_8 = v8;
    v14 = _mm_cvtsi128_si32(v9);
    v38 = v14;
    v39 = *(__int64 *)((char *)v45.m128i_i64 + 4);
    v40 = _mm_cvtsi128_si32(_mm_srli_si128(v9, 12));
    v15 = qword_14001D150;
    while ( 1 )
    {
      Buf1 = *(_OWORD *)v15;
      v42 = *((__m128i *)v15 + 1);
      v16 = v15[4];
      v43 = v16;
      if ( _mm_cvtsi128_si32(v42) == v14 && !memcmp_0(&Buf1, &Buf2_8, 0x10u) )
        break;
      v15 += 5;
      if ( v15 == (__int64 *)&std::bad_alloc `RTTI Type Descriptor' )
      {
        v17 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v13, &dword_140015CE4);
        goto LABEL_7;
      }
    }
    v17 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v13, v16);
LABEL_7:
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v17, L" = ");
    v18 = _mm_cvtsi128_si32(v10) - 17;
    if ( v18 )
    {
      if ( v18 == 1 )
      {
        v20 = (_WORD *)_mm_srli_si128(v10, 8).m128i_u64[0];
        v21 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(std::wcout, v20);
        std::basic_ostream<unsigned short>::operator<<(v21, std::endl<unsigned short,std::char_traits<unsigned short>>);
        if ( v14 == 4096 && !memcmp_0(DEVPKEY_PNPX_GlobalIdentity, &v44, 0x10u) )
        {
          v23 = (char **)((char *)this + 168);
          v24 = -1;
          do
            ++v24;
          while ( v20[v24] );
          if ( v24 > *((_QWORD *)this + 24) )
          {
            std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
              v23,
              v24,
              v22,
              v20);
          }
          else
          {
            if ( *((_QWORD *)this + 24) <= 7u )
              v25 = (char *)this + 168;
            else
              v25 = *v23;
            *((_QWORD *)this + 23) = v24;
            v26 = 2 * v24;
            memmove_0(v25, v20, 2 * v24);
            *(_WORD *)&v25[v26] = 0;
          }
        }
        goto LABEL_37;
      }
      v19 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(std::wcout, L"(unknown)");
      goto LABEL_36;
    }
    v27 = (_BYTE *)_mm_srli_si128(v10, 8).m128i_u64[0];
    if ( v14 == 16 )
      break;
    if ( v14 != 3 || memcmp_0(DEVPKEY_Aep_IsAssociatable, &v44, 0x10u) )
      goto LABEL_37;
    *((_BYTE *)this + 200) = *v27 != 0;
    v19 = std::basic_ostream<unsigned short>::operator<<(std::wcout);
LABEL_36:
    std::basic_ostream<unsigned short>::operator<<(v19, std::endl<unsigned short,std::char_traits<unsigned short>>);
LABEL_37:
    if ( ++v6 >= *((_DWORD *)a2 + 4) )
      return *((_QWORD *)this + 23) != 0;
  }
  if ( memcmp_0(DEVPKEY_Aep_IsAssociated, &v44, 0x10u) )
    goto LABEL_37;
  *((_BYTE *)this + 201) = *v27 != 0;
  v28 = std::basic_ostream<unsigned short>::operator<<(std::wcout);
  std::basic_ostream<unsigned short>::operator<<(v28, std::endl<unsigned short,std::char_traits<unsigned short>>);
  if ( !*((_QWORD *)this + 28) )
    goto LABEL_37;
  v29 = (const wchar_t *)((char *)this + 208);
  v30 = (const wchar_t *)((char *)this + 208);
  if ( *((_QWORD *)this + 29) > 7u )
    v30 = *(const wchar_t **)v29;
  if ( !wcsstr(*((const wchar_t **)a2 + 1), v30) )
    goto LABEL_37;
  v32 = (char *)this + 168;
  if ( (const wchar_t *)((char *)this + 168) != v29 )
  {
    v33 = *((_QWORD *)this + 28);
    if ( *((_QWORD *)this + 29) > 7u )
      v29 = *(const wchar_t **)v29;
    if ( v33 > *((_QWORD *)this + 24) )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        v32,
        v33,
        v31,
        v29);
    }
    else
    {
      if ( *((_QWORD *)this + 24) <= 7u )
        v34 = (char *)this + 168;
      else
        v34 = *(char **)v32;
      *((_QWORD *)v32 + 2) = v33;
      v36 = 2 * v33;
      memmove_0(v34, v29, 2 * v33);
      *(_WORD *)&v34[v36] = 0;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x14000b4a0  mov     rax, rsp
0x14000b4a3  push    rbp
0x14000b4a4  push    rbx
0x14000b4a5  push    rsi
0x14000b4a6  push    rdi
0x14000b4a7  push    r12
0x14000b4a9  push    r13
0x14000b4ab  push    r14
0x14000b4ad  push    r15
0x14000b4af  lea     rbp, [rax-5Fh]
0x14000b4b3  sub     rsp, 0D8h
0x14000b4ba  movaps  xmmword ptr [rax-58h], xmm6
0x14000b4be  movaps  xmmword ptr [rax-68h], xmm7
0x14000b4c2  movaps  xmmword ptr [rax-78h], xmm8
0x14000b4c7  mov     r15, rdx
0x14000b4ca  mov     rsi, rcx
0x14000b4cd  lea     rdx, aFoundDevice; "  Found device: "
0x14000b4d4  mov     rcx, cs:__imp_?wcout@std@@3V?$basic_ostream@GU?$char_traits@G@std@@@1@A; std::basic_ostream<ushort> std::wcout
0x14000b4db  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14000b4e0  mov     rdx, [r15+8]
0x14000b4e4  mov     rcx, rax
0x14000b4e7  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14000b4ec  lea     rdx, ??$endl@GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@@Z; std::endl<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &)
0x14000b4f3  mov     rcx, rax
0x14000b4f6  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z; std::basic_ostream<ushort>::operator<<(std::basic_ostream<ushort> & (*)(std::basic_ostream<ushort> &))
0x14000b4fc  xor     r13d, r13d
0x14000b4ff  mov     r12d, r13d
0x14000b502  cmp     [r15+10h], r13d
0x14000b506  jbe     loc_14000B7F4
0x14000b50c  mov     eax, r12d
0x14000b50f  lea     rcx, [rax+rax*2]
0x14000b513  add     rcx, rcx
0x14000b516  mov     rax, [r15+18h]
0x14000b51a  movups  xmm6, xmmword ptr [rax+rcx*8]
0x14000b51e  movups  [rbp+57h+var_A8], xmm6
0x14000b522  movups  xmm7, xmmword ptr [rax+rcx*8+10h]
0x14000b527  movups  [rbp+57h+var_98], xmm7
0x14000b52b  movups  xmm8, xmmword ptr [rax+rcx*8+20h]
0x14000b531  movups  [rbp+57h+var_88], xmm8
0x14000b536  lea     rdx, asc_140015E00; "    "
0x14000b53d  mov     rcx, cs:__imp_?wcout@std@@3V?$basic_ostream@GU?$char_traits@G@std@@@1@A; std::basic_ostream<ushort> std::wcout
0x14000b544  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14000b549  mov     edx, r12d
0x14000b54c  mov     rcx, rax
0x14000b54f  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z; std::basic_ostream<ushort>::operator<<(ulong)
0x14000b555  mov     rcx, rax
0x14000b558  lea     rdx, asc_140016480; ") "
0x14000b55f  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14000b564  mov     rdi, rax
0x14000b567  movdqu  [rsp+110h+Buf2+8], xmm6
0x14000b56d  movd    r14d, xmm7
0x14000b572  mov     dword ptr [rsp+110h+var_E4+4], r14d
0x14000b577  movsd   xmm0, qword ptr [rbp+57h+var_98+4]
0x14000b57c  movsd   [rsp+110h+var_DC], xmm0
0x14000b582  psrldq  xmm7, 0Ch
0x14000b587  movd    [rbp+57h+var_D4], xmm7
0x14000b58c  lea     rbx, qword_14001D150
0x14000b593  movups  xmm0, xmmword ptr [rbx]
0x14000b596  movups  [rbp+57h+Buf1], xmm0
0x14000b59a  movups  xmm1, xmmword ptr [rbx+10h]
0x14000b59e  movups  [rbp+57h+var_C0], xmm1
0x14000b5a2  movsd   xmm6, qword ptr [rbx+20h]
0x14000b5a7  movsd   [rbp+57h+var_B0], xmm6
0x14000b5ac  movd    eax, xmm1
0x14000b5b0  cmp     eax, r14d
0x14000b5b3  jnz     short loc_14000B5CD
0x14000b5b5  mov     r8d, 10h; Size
0x14000b5bb  lea     rdx, [rsp+110h+Buf2+8]; Buf2
0x14000b5c0  lea     rcx, [rbp+57h+Buf1]; Buf1
0x14000b5c4  call    memcmp_0
0x14000b5c9  test    eax, eax
0x14000b5cb  jz      short loc_14000B626
0x14000b5cd  add     rbx, 28h ; '('
0x14000b5d1  lea     rax, ??_R0?AVbad_alloc@std@@@8; std::bad_alloc `RTTI Type Descriptor'
0x14000b5d8  cmp     rbx, rax
0x14000b5db  jnz     short loc_14000B593
0x14000b5dd  lea     rdx, dword_140015CE4
0x14000b5e4  mov     rcx, rdi
0x14000b5e7  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14000b5ec  mov     rcx, rax
0x14000b5ef  lea     rdx, asc_140016478; " = "
0x14000b5f6  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14000b5fb  movd    eax, xmm8
0x14000b600  sub     eax, 11h
0x14000b603  jz      loc_14000B6D2
0x14000b609  mov     rcx, cs:__imp_?wcout@std@@3V?$basic_ostream@GU?$char_traits@G@std@@@1@A; std::basic_ostream<ushort> std::wcout
0x14000b610  cmp     eax, 1
0x14000b613  jz      short loc_14000B62D
0x14000b615  lea     rdx, aUnknown; "(unknown)"
0x14000b61c  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14000b621  jmp     loc_14000B7D7
0x14000b626  movq    rdx, xmm6
0x14000b62b  jmp     short loc_14000B5E4
0x14000b62d  psrldq  xmm8, 8
0x14000b633  movq    rdi, xmm8
0x14000b638  mov     rdx, rdi
0x14000b63b  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14000b640  lea     rdx, ??$endl@GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@@Z; std::endl<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &)
0x14000b647  mov     rcx, rax
0x14000b64a  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z; std::basic_ostream<ushort>::operator<<(std::basic_ostream<ushort> & (*)(std::basic_ostream<ushort> &))
0x14000b650  cmp     r14d, 1000h
0x14000b657  jnz     loc_14000B7E7
0x14000b65d  mov     r8d, 10h; Size
0x14000b663  lea     rdx, [rbp+57h+var_A8]; Buf2
0x14000b667  lea     rcx, DEVPKEY_PNPX_GlobalIdentity; Buf1
0x14000b66e  call    memcmp_0
0x14000b673  test    eax, eax
0x14000b675  jnz     loc_14000B7E7
0x14000b67b  lea     rcx, [rsi+0A8h]
0x14000b682  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14000b686  inc     rdx
0x14000b689  cmp     [rdi+rdx*2], r13w
0x14000b68e  jnz     short loc_14000B686
0x14000b690  cmp     rdx, [rcx+18h]
0x14000b694  ja      short loc_14000B6C5
0x14000b696  cmp     qword ptr [rcx+18h], 7
0x14000b69b  jbe     short loc_14000B6A2
0x14000b69d  mov     r14, [rcx]
0x14000b6a0  jmp     short loc_14000B6A5
0x14000b6a2  mov     r14, rcx
0x14000b6a5  mov     [rcx+10h], rdx
0x14000b6a9  lea     rbx, [rdx+rdx]
0x14000b6ad  mov     r8, rbx; Size
0x14000b6b0  mov     rdx, rdi; Src
0x14000b6b3  mov     rcx, r14; void *
0x14000b6b6  call    memmove_0
0x14000b6bb  mov     [rbx+r14], r13w
0x14000b6c0  jmp     loc_14000B7E7
0x14000b6c5  mov     r9, rdi
0x14000b6c8  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x14000b6cd  jmp     loc_14000B7E7
0x14000b6d2  psrldq  xmm8, 8
0x14000b6d8  movq    rbx, xmm8
0x14000b6dd  mov     eax, 10h
0x14000b6e2  cmp     r14d, eax
0x14000b6e5  jnz     loc_14000B7A1
0x14000b6eb  mov     r8d, eax; Size
0x14000b6ee  lea     rdx, [rbp+57h+var_A8]; Buf2
0x14000b6f2  lea     rcx, DEVPKEY_Aep_IsAssociated; Buf1
0x14000b6f9  call    memcmp_0
0x14000b6fe  test    eax, eax
0x14000b700  jnz     loc_14000B7E7
0x14000b706  cmp     [rbx], r13b
0x14000b709  setnz   dl
0x14000b70c  mov     [rsi+0C9h], dl
0x14000b712  mov     rcx, cs:__imp_?wcout@std@@3V?$basic_ostream@GU?$char_traits@G@std@@@1@A; std::basic_ostream<ushort> std::wcout
0x14000b719  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@_N@Z; std::basic_ostream<ushort>::operator<<(bool)
0x14000b71f  lea     rdx, ??$endl@GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@@Z; std::endl<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &)
0x14000b726  mov     rcx, rax
0x14000b729  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z; std::basic_ostream<ushort>::operator<<(std::basic_ostream<ushort> & (*)(std::basic_ostream<ushort> &))
0x14000b72f  cmp     [rsi+0E0h], r13
0x14000b736  jz      loc_14000B7E7
0x14000b73c  lea     rdi, [rsi+0D0h]
0x14000b743  mov     rdx, rdi
0x14000b746  cmp     qword ptr [rsi+0E8h], 7
0x14000b74e  jbe     short loc_14000B753
0x14000b750  mov     rdx, [rdi]; SubStr
0x14000b753  mov     rcx, [r15+8]; Str
0x14000b757  call    cs:__imp_wcsstr
0x14000b75d  test    rax, rax
0x14000b760  jz      loc_14000B7E7
0x14000b766  lea     rcx, [rsi+0A8h]
0x14000b76d  cmp     rcx, rdi
0x14000b770  jz      loc_14000B84D
0x14000b776  mov     rdx, [rdi+10h]
0x14000b77a  cmp     qword ptr [rdi+18h], 7
0x14000b77f  jbe     short loc_14000B784
0x14000b781  mov     rdi, [rdi]
0x14000b784  cmp     rdx, [rcx+18h]
0x14000b788  ja      loc_14000B845
0x14000b78e  cmp     qword ptr [rcx+18h], 7
0x14000b793  jbe     loc_14000B825
0x14000b799  mov     rsi, [rcx]
0x14000b79c  jmp     loc_14000B828
0x14000b7a1  cmp     r14d, 3
0x14000b7a5  jnz     short loc_14000B7E7
0x14000b7a7  mov     r8, rax; Size
0x14000b7aa  lea     rdx, [rbp+57h+var_A8]; Buf2
0x14000b7ae  lea     rcx, DEVPKEY_Aep_IsAssociatable; Buf1
0x14000b7b5  call    memcmp_0
0x14000b7ba  test    eax, eax
0x14000b7bc  jnz     short loc_14000B7E7
0x14000b7be  cmp     [rbx], r13b
0x14000b7c1  setnz   dl
0x14000b7c4  mov     [rsi+0C8h], dl
0x14000b7ca  mov     rcx, cs:__imp_?wcout@std@@3V?$basic_ostream@GU?$char_traits@G@std@@@1@A; std::basic_ostream<ushort> std::wcout
0x14000b7d1  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@_N@Z; std::basic_ostream<ushort>::operator<<(bool)
0x14000b7d7  lea     rdx, ??$endl@GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@@Z; std::endl<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &)
0x14000b7de  mov     rcx, rax
0x14000b7e1  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z; std::basic_ostream<ushort>::operator<<(std::basic_ostream<ushort> & (*)(std::basic_ostream<ushort> &))
0x14000b7e7  inc     r12d
0x14000b7ea  cmp     r12d, [r15+10h]
0x14000b7ee  jb      loc_14000B50C
0x14000b7f4  cmp     [rsi+0B8h], r13
0x14000b7fb  setnz   al
0x14000b7fe  lea     r11, [rsp+110h+var_38]
0x14000b806  movaps  xmm6, xmmword ptr [r11-18h]
0x14000b80b  movaps  xmm7, xmmword ptr [r11-28h]
0x14000b810  movaps  xmm8, xmmword ptr [r11-38h]
0x14000b815  mov     rsp, r11
0x14000b818  pop     r15
0x14000b81a  pop     r14
0x14000b81c  pop     r13
0x14000b81e  pop     r12
0x14000b820  pop     rdi
0x14000b821  pop     rsi
0x14000b822  pop     rbx
0x14000b823  pop     rbp
0x14000b824  retn
0x14000b825  mov     rsi, rcx
0x14000b828  mov     [rcx+10h], rdx
0x14000b82c  lea     rbx, [rdx+rdx]
0x14000b830  mov     r8, rbx; Size
0x14000b833  mov     rdx, rdi; Src
0x14000b836  mov     rcx, rsi; void *
0x14000b839  call    memmove_0
0x14000b83e  mov     [rbx+rsi], r13w
0x14000b843  jmp     short loc_14000B84D
0x14000b845  mov     r9, rdi
0x14000b848  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x14000b84d  mov     al, 1
0x14000b84f  jmp     short loc_14000B7FE
```
