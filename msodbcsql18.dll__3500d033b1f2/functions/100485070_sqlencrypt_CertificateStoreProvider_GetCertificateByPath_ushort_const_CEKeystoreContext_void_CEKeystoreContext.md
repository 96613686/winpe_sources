# sqlencrypt::CertificateStoreProvider::GetCertificateByPath(ushort const *,CEKeystoreContext *,void (*)(CEKeystoreContext *,ushort const *,...))

- ea: `0x100485070`
- end: `0x100485777`
- name: `?GetCertificateByPath@CertificateStoreProvider@sqlencrypt@@CAPEBU_CERT_CONTEXT@@PEBGPEAUCEKeystoreContext@@P6AX10ZZ@Z`
- size: `1799`
- prototype: `const struct _CERT_CONTEXT *__fastcall(const unsigned __int16 *, struct CEKeystoreContext *, void (*)(struct CEKeystoreContext *, const unsigned __int16 *, ...))`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x100484830`
- `0x100484ea0`

## callees

- `0x10040128c`
- `0x1004306f0`
- `0x100430824`
- `0x100483738`
- `0x100483890`
- `0x100485070`
- `0x100546aa8`
- `0x100548210`
- `0x1005495d0`

## import_xrefs

- `CRYPT32!CertOpenStore` at `0x100485625`
- `CRYPT32!CertOpenStore` at `0x100485625`
- `CRYPT32!CertCloseStore` at `0x1004856f7`
- `CRYPT32!CertCloseStore` at `0x1004856f7`
- `CRYPT32!CertFindCertificateInStore` at `0x100485655`
- `CRYPT32!CertFindCertificateInStore` at `0x100485655`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x100485212`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x100485245`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004852f5`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x100485212`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x100485245`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004852f5`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x10048573b`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x10048575b`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x100485762`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x100485769`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x100485770`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x10048573b`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x10048575b`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x100485762`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x100485769`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x100485770`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
PCCERT_CONTEXT __fastcall sqlencrypt::CertificateStoreProvider::GetCertificateByPath(
        const unsigned __int16 *a1,
        struct CEKeystoreContext *a2,
        const CERT_CONTEXT *a3)
{
  __int64 v6; // r8
  const wchar_t *v7; // rax
  unsigned __int64 v8; // rbx
  __int64 v9; // rdx
  int v10; // edi
  const wchar_t *v11; // rcx
  wchar_t *v12; // rcx
  const wchar_t *v13; // rbx
  PCCERT_CONTEXT CertificateInStore; // rsi
  wchar_t *v15; // rbx
  wchar_t *v16; // rdi
  unsigned __int64 v17; // rcx
  wchar_t *v18; // rax
  void *v19; // rcx
  void *v20; // rcx
  void *v21; // rcx
  HCERTSTORE v23; // rdi
  _QWORD *v24; // r9
  _QWORD *v25; // r8
  void *v26; // rdx
  PCCERT_CONTEXT pPrevCertContext; // [rsp+30h] [rbp-A1h]
  int String1; // [rsp+38h] [rbp-99h] BYREF
  wchar_t *String1_8[2]; // [rsp+40h] [rbp-91h] BYREF
  __int64 v30; // [rsp+50h] [rbp-81h]
  void *v31[2]; // [rsp+58h] [rbp-79h] BYREF
  __int64 v32; // [rsp+68h] [rbp-69h]
  int pvFindPara; // [rsp+78h] [rbp-59h] BYREF
  void *v34; // [rsp+80h] [rbp-51h]
  __int64 v35; // [rsp+88h] [rbp-49h]
  _QWORD v36[2]; // [rsp+90h] [rbp-41h] BYREF
  __int64 v37; // [rsp+A0h] [rbp-31h]
  unsigned __int64 v38; // [rsp+A8h] [rbp-29h]
  _QWORD v39[3]; // [rsp+B0h] [rbp-21h] BYREF
  unsigned __int64 v40; // [rsp+C8h] [rbp-9h]
  _QWORD v41[2]; // [rsp+D0h] [rbp-1h] BYREF
  __m128i si128; // [rsp+E0h] [rbp+Fh]

  v35 = -2;
  if ( (bidGblFlags & 2) != 0 && off_1005E6FF8[0] )
  {
    pPrevCertContext = a3;
    bidTraceW(0, 59392, off_1005E6FF8[0], a1);
  }
  v39[2] = 0;
  v40 = 7;
  LOWORD(v39[0]) = 0;
  std::wstring::assign(v39);
  v37 = 0;
  v38 = 7;
  LOWORD(v36[0]) = 0;
  std::wstring::assign(v36);
  LOWORD(String1) = 47;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v41[0]) = 0;
  v6 = -1;
  do
    ++v6;
  while ( a1[v6] );
  std::wstring::assign(v41);
  *(_OWORD *)String1_8 = 0;
  v30 = 0;
  sqlencrypt::utils::Split(v41, &String1, String1_8);
  v7 = String1_8[0];
  v8 = ((char *)String1_8[1] - (char *)String1_8[0]) >> 5;
  if ( v8 > 3 )
  {
    if ( (bidGblFlags & 2) != 0 && off_1005E7000[0] && bidID != -1 )
      ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD, PCCERT_CONTEXT, int))off_1005D39E0[0])(
        bidID,
        0,
        75776,
        off_1005E7000[0],
        0,
        pPrevCertContext,
        String1);
    v9 = 41323;
LABEL_37:
    ((void (__fastcall *)(struct CEKeystoreContext *, __int64))a3)(a2, v9);
    CertificateInStore = 0;
    goto LABEL_38;
  }
  if ( v8 <= 2 )
  {
    v10 = 0x20000;
    if ( v8 <= 1 )
      goto LABEL_31;
  }
  else
  {
    if ( *((_QWORD *)String1_8[0] + 3) >= 8u )
      v7 = *(const wchar_t **)String1_8[0];
    if ( _wcsicmp(v7, L"LocalMachine") )
    {
      v11 = String1_8[0];
      if ( *((_QWORD *)String1_8[0] + 3) >= 8u )
        v11 = *(const wchar_t **)String1_8[0];
      if ( _wcsicmp(v11, L"CurrentUser") )
      {
        if ( (bidGblFlags & 2) != 0 && off_1005E7008[0] && bidID != -1 )
          ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD, PCCERT_CONTEXT, int))off_1005D39E0[0])(
            bidID,
            0,
            96256,
            off_1005E7008[0],
            0,
            pPrevCertContext,
            String1);
        v9 = 41324;
        goto LABEL_37;
      }
      std::wstring::assign(v39);
      v10 = 0x10000;
    }
    else
    {
      std::wstring::assign(v39);
      v10 = 0x20000;
    }
  }
  _mm_lfence();
  v12 = &String1_8[0][16 * v8 - 32];
  if ( *((_QWORD *)v12 + 3) >= 8u )
    v12 = *(wchar_t **)v12;
  if ( _wcsicmp(v12, L"My") )
  {
    _mm_lfence();
    if ( (bidGblFlags & 2) != 0 && off_1005E7010[0] && bidID != -1 )
      ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD, PCCERT_CONTEXT, int))off_1005D39E0[0])(
        bidID,
        0,
        112640,
        off_1005E7010[0],
        0,
        pPrevCertContext,
        String1);
    v9 = 41325;
    goto LABEL_37;
  }
  std::wstring::assign(v36);
  v7 = String1_8[0];
LABEL_31:
  v13 = &v7[16 * v8 - 16];
  if ( !*((_QWORD *)v13 + 2) )
  {
    if ( (bidGblFlags & 2) != 0 && off_1005E7018[0] && bidID != -1 )
      ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD, PCCERT_CONTEXT, int))off_1005D39E0[0])(
        bidID,
        0,
        124928,
        off_1005E7018[0],
        0,
        pPrevCertContext,
        String1);
    v9 = 41326;
    goto LABEL_37;
  }
  _mm_lfence();
  CertificateInStore = 0;
  v31[0] = 0;
  v31[1] = 0;
  v32 = 0;
  sqlencrypt::utils::DecodeHexString(v13, v31);
  pvFindPara = LODWORD(v31[1]) - LODWORD(v31[0]);
  v34 = v31[0];
  v23 = CertOpenStore((LPCSTR)0xA, 0, 0, v10 | 0x4000u, L"My");
  if ( v23 )
  {
    CertificateInStore = CertFindCertificateInStore(v23, 0x10001u, 0, 0x10000u, &pvFindPara, 0);
    if ( CertificateInStore )
    {
      CertCloseStore(v23, 0);
    }
    else
    {
      _mm_lfence();
      if ( (bidGblFlags & 2) != 0 && off_1005E7020[0] && bidID != -1 )
        ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD))off_1005D39E0[0])(
          bidID,
          0,
          163840,
          off_1005E7020[0],
          0);
      if ( *((_QWORD *)v13 + 3) >= 8u )
        v13 = *(const wchar_t **)v13;
      v24 = v36;
      if ( v38 >= 8 )
        v24 = (_QWORD *)v36[0];
      v25 = v39;
      if ( v40 >= 8 )
        v25 = (_QWORD *)v39[0];
      ((void (__fastcall *)(struct CEKeystoreContext *, __int64, _QWORD *, _QWORD *, const wchar_t *))a3)(
        a2,
        41327,
        v25,
        v24,
        v13);
      CertificateInStore = 0;
    }
  }
  v26 = v31[0];
  if ( v31[0] )
  {
    if ( v32 - (unsigned __int64)v31[0] >= 0x1000 )
    {
      if ( ((__int64)v31[0] & 0x1F) != 0
        || (v26 = (void *)*((_QWORD *)v31[0] - 1), v26 >= v31[0])
        || (unsigned __int64)((char *)v31[0] - (char *)v26 - 8) > 0x1F )
      {
        _invalid_parameter_noinfo_noreturn();
      }
    }
    operator delete(v26);
    *(_OWORD *)v31 = 0;
    v32 = 0;
  }
LABEL_38:
  v15 = String1_8[0];
  if ( String1_8[0] )
  {
    v16 = String1_8[1];
    if ( String1_8[0] != String1_8[1] )
    {
      do
      {
        std::basic_string<char16_t>::_Tidy_deallocate(v15);
        v15 += 16;
      }
      while ( v15 != v16 );
      v15 = String1_8[0];
    }
    v17 = (v30 - (__int64)v15) >> 5;
    v18 = v15;
    if ( v17 > 0x7FFFFFFFFFFFFFFLL
      || 32 * v17 >= 0x1000
      && (((unsigned __int8)v15 & 0x1F) != 0
       || (v15 = (wchar_t *)*((_QWORD *)v15 - 1), v15 >= v18)
       || (unsigned __int64)((char *)v18 - (char *)v15 - 8) > 0x1F) )
    {
      _invalid_parameter_noinfo_noreturn();
    }
    operator delete(v15);
    *(_OWORD *)String1_8 = 0;
    v30 = 0;
  }
  if ( si128.m128i_i64[1] >= 8uLL )
  {
    v19 = (void *)v41[0];
    if ( (unsigned __int64)(si128.m128i_i64[1] + 1) > 0x7FFFFFFFFFFFFFFFLL
      || (unsigned __int64)(2 * (si128.m128i_i64[1] + 1)) >= 0x1000
      && ((v41[0] & 0x1F) != 0
       || (v19 = *(void **)(v41[0] - 8LL), (unsigned __int64)v19 >= v41[0])
       || (unsigned __int64)(v41[0] - (_QWORD)v19 - 8LL) > 0x1F) )
    {
      _invalid_parameter_noinfo_noreturn();
    }
    operator delete(v19);
  }
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v41[0]) = 0;
  if ( v38 >= 8 )
  {
    v20 = (void *)v36[0];
    if ( v38 + 1 > 0x7FFFFFFFFFFFFFFFLL
      || 2 * (v38 + 1) >= 0x1000
      && ((v36[0] & 0x1F) != 0
       || (v20 = *(void **)(v36[0] - 8LL), (unsigned __int64)v20 >= v36[0])
       || (unsigned __int64)(v36[0] - (_QWORD)v20 - 8LL) > 0x1F) )
    {
      _invalid_parameter_noinfo_noreturn();
    }
    operator delete(v20);
  }
  v37 = 0;
  v38 = 7;
  LOWORD(v36[0]) = 0;
  if ( v40 >= 8 )
  {
    v21 = (void *)v39[0];
    if ( v40 + 1 > 0x7FFFFFFFFFFFFFFFLL
      || 2 * (v40 + 1) >= 0x1000
      && ((v39[0] & 0x1F) != 0
       || (v21 = *(void **)(v39[0] - 8LL), (unsigned __int64)v21 >= v39[0])
       || (unsigned __int64)(v39[0] - (_QWORD)v21 - 8LL) > 0x1F) )
    {
      _invalid_parameter_noinfo_noreturn();
    }
    operator delete(v21);
  }
  return CertificateInStore;
}

```

## disassembly

```asm
0x100485070  mov     rax, rsp
0x100485073  push    rbp
0x100485074  push    rsi
0x100485075  push    rdi
0x100485076  push    r12
0x100485078  push    r13
0x10048507a  push    r14
0x10048507c  push    r15
0x10048507e  lea     rbp, [rax-5Fh]
0x100485082  sub     rsp, 0F0h
0x100485089  mov     [rbp+57h+var_A0], 0FFFFFFFFFFFFFFFEh
0x100485091  mov     [rax+20h], rbx
0x100485095  mov     rax, cs:__security_cookie
0x10048509c  xor     rax, rsp
0x10048509f  mov     [rbp+57h+var_38], rax
0x1004850a3  mov     r12, r8
0x1004850a6  mov     r15, rdx
0x1004850a9  mov     r14, rcx
0x1004850ac  xor     r13d, r13d
0x1004850af  test    byte ptr cs:_bidGblFlags, 2
0x1004850b6  jz      short loc_1004850E4
0x1004850b8  mov     rax, cs:off_1005E6FF8; "<sqlencrypt::CertificateStoreProvider::"...
0x1004850bf  test    rax, rax
0x1004850c2  jz      short loc_1004850E4
0x1004850c4  mov     [rsp+120h+pPrevCertContext], r8
0x1004850c9  mov     [rsp+120h+pvPara], rdx
0x1004850ce  mov     r9, rcx
0x1004850d1  mov     r8, cs:off_1005E6FF8; "<sqlencrypt::CertificateStoreProvider::"...
0x1004850d8  mov     edx, 0E800h
0x1004850dd  xor     ecx, ecx
0x1004850df  call    _bidTraceW
0x1004850e4  mov     [rbp+57h+var_68], r13
0x1004850e8  mov     ebx, 7
0x1004850ed  mov     [rbp+57h+var_60], rbx
0x1004850f1  mov     word ptr [rbp+57h+var_78], r13w
0x1004850f6  lea     r8d, [rbx+5]
0x1004850fa  lea     rdi, aLocalmachine; "LocalMachine"
0x100485101  mov     rdx, rdi
0x100485104  lea     rcx, [rbp+57h+var_78]; void *
0x100485108  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG_K@Z; std::wstring::assign(ushort const * const,unsigned __int64)
0x10048510d  nop
0x10048510e  mov     [rbp+57h+var_88], r13
0x100485112  mov     [rbp+57h+var_80], rbx
0x100485116  mov     word ptr [rbp+57h+var_98], r13w
0x10048511b  lea     r8d, [rbx+4]
0x10048511f  lea     rsi, aCurrentuser; "CurrentUser"
0x100485126  mov     rdx, rsi
0x100485129  lea     rcx, [rbp+57h+var_98]; void *
0x10048512d  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG_K@Z; std::wstring::assign(ushort const * const,unsigned __int64)
0x100485132  nop
0x100485133  lea     eax, [rbx+28h]
0x100485136  mov     word ptr [rsp+120h+String1], ax
0x10048513b  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x100485143  movdqu  [rbp+57h+var_48], xmm0
0x100485148  mov     word ptr [rbp+57h+var_58], r13w
0x10048514d  or      r8, 0FFFFFFFFFFFFFFFFh
0x100485151  inc     r8
0x100485154  cmp     [r14+r8*2], r13w
0x100485159  jnz     short loc_100485151
0x10048515b  mov     rdx, r14
0x10048515e  lea     rcx, [rbp+57h+var_58]; void *
0x100485162  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG_K@Z; std::wstring::assign(ushort const * const,unsigned __int64)
0x100485167  nop
0x100485168  xorps   xmm0, xmm0
0x10048516b  movdqu  xmmword ptr [rsp+120h+String1+8], xmm0
0x100485171  mov     [rsp+120h+var_D8], r13
0x100485176  lea     r8, [rsp+120h+String1+8]
0x10048517b  lea     rdx, [rsp+120h+String1]
0x100485180  lea     rcx, [rbp+57h+var_58]
0x100485184  call    ?Split@utils@sqlencrypt@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBGAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@4@@Z; sqlencrypt::utils::Split(std::wstring const &,ushort const &,std::vector<std::wstring> &)
0x100485189  mov     rbx, [rsp+120h+var_E0]
0x10048518e  mov     rax, [rsp+120h+String1+8]
0x100485193  sub     rbx, rax
0x100485196  sar     rbx, 5
0x10048519a  cmp     rbx, 3
0x10048519e  jbe     short loc_1004851F1
0x1004851a0  test    byte ptr cs:_bidGblFlags, 2
0x1004851a7  jz      short loc_1004851E7
0x1004851a9  mov     rax, cs:off_1005E7000; "<sqlencrypt::CertificateStoreProvider::"...
0x1004851b0  test    rax, rax
0x1004851b3  jz      short loc_1004851E7
0x1004851b5  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x1004851bd  jz      short loc_1004851E7
0x1004851bf  mov     rax, cs:off_1005D39E0
0x1004851c6  mov     [rsp+120h+pvPara], r13
0x1004851cb  mov     r9, cs:off_1005E7000; "<sqlencrypt::CertificateStoreProvider::"...
0x1004851d2  xor     edx, edx
0x1004851d4  mov     r8d, 12800h
0x1004851da  mov     rcx, cs:_bidID
0x1004851e1  call    cs:__guard_dispatch_icall_fptr
0x1004851e7  mov     edx, 0A16Bh
0x1004851ec  jmp     loc_10048537D
0x1004851f1  lea     rdx, aMy; "My"
0x1004851f8  cmp     rbx, 2
0x1004851fc  jbe     loc_1004852CD
0x100485202  cmp     qword ptr [rax+18h], 8
0x100485207  jb      short loc_10048520C
0x100485209  mov     rax, [rax]
0x10048520c  mov     rdx, rdi; String2
0x10048520f  mov     rcx, rax; String1
0x100485212  call    cs:__imp__wcsicmp
0x100485218  test    eax, eax
0x10048521a  jnz     short loc_100485233
0x10048521c  lea     r8d, [rax+0Ch]
0x100485220  mov     rdx, rdi
0x100485223  lea     rcx, [rbp+57h+var_78]; void *
0x100485227  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG_K@Z; std::wstring::assign(ushort const * const,unsigned __int64)
0x10048522c  mov     edi, 20000h
0x100485231  jmp     short loc_100485264
0x100485233  mov     rcx, [rsp+120h+String1+8]
0x100485238  cmp     qword ptr [rcx+18h], 8
0x10048523d  jb      short loc_100485242
0x10048523f  mov     rcx, [rcx]; String1
0x100485242  mov     rdx, rsi; String2
0x100485245  call    cs:__imp__wcsicmp
0x10048524b  test    eax, eax
0x10048524d  jnz     short loc_10048526D
0x10048524f  lea     r8d, [rax+0Bh]
0x100485253  mov     rdx, rsi
0x100485256  lea     rcx, [rbp+57h+var_78]; void *
0x10048525a  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG_K@Z; std::wstring::assign(ushort const * const,unsigned __int64)
0x10048525f  mov     edi, 10000h
0x100485264  lea     rdx, aMy; "My"
0x10048526b  jmp     short loc_1004852D8
0x10048526d  test    byte ptr cs:_bidGblFlags, 2
0x100485274  jz      short loc_1004852B4
0x100485276  mov     rax, cs:off_1005E7008; "<sqlencrypt::CertificateStoreProvider::"...
0x10048527d  test    rax, rax
0x100485280  jz      short loc_1004852B4
0x100485282  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x10048528a  jz      short loc_1004852B4
0x10048528c  mov     rax, cs:off_1005D39E0
0x100485293  mov     [rsp+120h+pvPara], r13
0x100485298  mov     r9, cs:off_1005E7008; "<sqlencrypt::CertificateStoreProvider::"...
0x10048529f  xor     edx, edx
0x1004852a1  mov     r8d, 17800h
0x1004852a7  mov     rcx, cs:_bidID
0x1004852ae  call    cs:__guard_dispatch_icall_fptr
0x1004852b4  mov     r8, [rsp+120h+String1+8]
0x1004852b9  cmp     qword ptr [r8+18h], 8
0x1004852be  jb      short loc_1004852C3
0x1004852c0  mov     r8, [r8]
0x1004852c3  mov     edx, 0A16Ch
0x1004852c8  jmp     loc_100485380
0x1004852cd  mov     edi, 20000h
0x1004852d2  cmp     rbx, 1
0x1004852d6  jbe     short loc_10048531C
0x1004852d8  lfence
0x1004852db  lea     rsi, [rbx-2]
0x1004852df  shl     rsi, 5
0x1004852e3  mov     rcx, [rsp+120h+String1+8]
0x1004852e8  add     rcx, rsi
0x1004852eb  cmp     qword ptr [rcx+18h], 8
0x1004852f0  jb      short loc_1004852F5
0x1004852f2  mov     rcx, [rcx]; String1
0x1004852f5  call    cs:__imp__wcsicmp
0x1004852fb  test    eax, eax
0x1004852fd  jnz     loc_100485574
0x100485303  lea     r8d, [rax+2]
0x100485307  lea     rdx, aMy; "My"
0x10048530e  lea     rcx, [rbp+57h+var_98]; void *
0x100485312  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG_K@Z; std::wstring::assign(ushort const * const,unsigned __int64)
0x100485317  mov     rax, [rsp+120h+String1+8]
0x10048531c  shl     rbx, 5
0x100485320  add     rbx, 0FFFFFFFFFFFFFFE0h
0x100485324  add     rbx, rax
0x100485327  cmp     [rbx+10h], r13
0x10048532b  jnz     loc_1004855DA
0x100485331  test    byte ptr cs:_bidGblFlags, 2
0x100485338  jz      short loc_100485378
0x10048533a  mov     rax, cs:off_1005E7018; "<sqlencrypt::CertificateStoreProvider::"...
0x100485341  test    rax, rax
0x100485344  jz      short loc_100485378
0x100485346  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x10048534e  jz      short loc_100485378
0x100485350  mov     rax, cs:off_1005D39E0
0x100485357  mov     [rsp+120h+pvPara], r13
0x10048535c  mov     r9, cs:off_1005E7018; "<sqlencrypt::CertificateStoreProvider::"...
0x100485363  xor     edx, edx
0x100485365  mov     r8d, 1E800h
0x10048536b  mov     rcx, cs:_bidID
0x100485372  call    cs:__guard_dispatch_icall_fptr
0x100485378  mov     edx, 0A16Eh
0x10048537d  mov     r8, r14
0x100485380  mov     rcx, r15
0x100485383  mov     rax, r12
0x100485386  call    cs:__guard_dispatch_icall_fptr
0x10048538c  mov     rsi, r13
0x10048538f  mov     r14d, 1000h
0x100485395  mov     rbx, [rsp+120h+String1+8]
0x10048539a  test    rbx, rbx
0x10048539d  jz      loc_10048542A
0x1004853a3  mov     rdi, [rsp+120h+var_E0]
0x1004853a8  cmp     rbx, rdi
0x1004853ab  jz      short loc_1004853C3
0x1004853ad  mov     rcx, rbx
0x1004853b0  call    ?_Tidy_deallocate@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@QEAAXXZ; std::basic_string<char16_t>::_Tidy_deallocate(void)
0x1004853b5  add     rbx, 20h ; ' '
0x1004853b9  cmp     rbx, rdi
0x1004853bc  jnz     short loc_1004853AD
0x1004853be  mov     rbx, [rsp+120h+String1+8]
0x1004853c3  mov     rcx, [rsp+120h+var_D8]
0x1004853c8  sub     rcx, rbx
0x1004853cb  sar     rcx, 5
0x1004853cf  mov     rax, rbx
0x1004853d2  mov     rdx, 7FFFFFFFFFFFFFFh
0x1004853dc  cmp     rcx, rdx
0x1004853df  ja      loc_10048575B
0x1004853e5  shl     rcx, 5
0x1004853e9  cmp     rcx, r14
0x1004853ec  jb      short loc_100485414
0x1004853ee  test    al, 1Fh
0x1004853f0  jnz     loc_10048575B
0x1004853f6  mov     rbx, [rbx-8]
0x1004853fa  cmp     rbx, rax
0x1004853fd  jnb     loc_10048575B
0x100485403  sub     rax, rbx
0x100485406  sub     rax, 8
0x10048540a  cmp     rax, 1Fh
0x10048540e  ja      loc_10048575B
0x100485414  mov     rcx, rbx; void *
0x100485417  call    ??3@YAXPEAX@Z; operator delete(void *)
0x10048541c  xorps   xmm0, xmm0
0x10048541f  movdqu  xmmword ptr [rsp+120h+String1+8], xmm0
0x100485425  mov     [rsp+120h+var_D8], r13
0x10048542a  mov     rbx, 7FFFFFFFFFFFFFFFh
0x100485434  mov     rax, qword ptr [rbp+57h+var_48+8]
0x100485438  cmp     rax, 8
0x10048543c  jb      short loc_100485485
0x10048543e  inc     rax
0x100485441  mov     rcx, [rbp+57h+var_58]
0x100485445  mov     rdx, rcx
0x100485448  cmp     rax, rbx
0x10048544b  ja      loc_100485762
0x100485451  add     rax, rax
0x100485454  cmp     rax, r14
0x100485457  jb      short loc_100485480
0x100485459  test    dl, 1Fh
0x10048545c  jnz     loc_100485762
0x100485462  mov     rcx, [rcx-8]; void *
0x100485466  cmp     rcx, rdx
0x100485469  jnb     loc_100485762
0x10048546f  sub     rdx, rcx
0x100485472  sub     rdx, 8
0x100485476  cmp     rdx, 1Fh
0x10048547a  ja      loc_100485762
0x100485480  call    ??3@YAXPEAX@Z; operator delete(void *)
0x100485485  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x10048548d  movdqu  [rbp+57h+var_48], xmm0
0x100485492  mov     word ptr [rbp+57h+var_58], r13w
0x100485497  mov     rax, [rbp+57h+var_80]
0x10048549b  cmp     rax, 8
0x10048549f  jb      short loc_1004854E8
0x1004854a1  inc     rax
0x1004854a4  mov     rcx, [rbp+57h+var_98]
0x1004854a8  mov     rdx, rcx
0x1004854ab  cmp     rax, rbx
0x1004854ae  ja      loc_100485769
0x1004854b4  add     rax, rax
0x1004854b7  cmp     rax, r14
0x1004854ba  jb      short loc_1004854E3
0x1004854bc  test    dl, 1Fh
0x1004854bf  jnz     loc_100485769
0x1004854c5  mov     rcx, [rcx-8]; void *
0x1004854c9  cmp     rcx, rdx
0x1004854cc  jnb     loc_100485769
0x1004854d2  sub     rdx, rcx
0x1004854d5  sub     rdx, 8
0x1004854d9  cmp     rdx, 1Fh
0x1004854dd  ja      loc_100485769
0x1004854e3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1004854e8  mov     [rbp+57h+var_88], r13
0x1004854ec  mov     [rbp+57h+var_80], 7
0x1004854f4  mov     word ptr [rbp+57h+var_98], r13w
0x1004854f9  mov     rax, [rbp+57h+var_60]
0x1004854fd  cmp     rax, 8
0x100485501  jb      short loc_10048554A
0x100485503  inc     rax
0x100485506  mov     rcx, [rbp+57h+var_78]
0x10048550a  mov     rdx, rcx
0x10048550d  cmp     rax, rbx
0x100485510  ja      loc_100485770
0x100485516  add     rax, rax
0x100485519  cmp     rax, r14
0x10048551c  jb      short loc_100485545
0x10048551e  test    dl, 1Fh
0x100485521  jnz     loc_100485770
0x100485527  mov     rcx, [rcx-8]; void *
0x10048552b  cmp     rcx, rdx
0x10048552e  jnb     loc_100485770
0x100485534  sub     rdx, rcx
0x100485537  sub     rdx, 8
0x10048553b  cmp     rdx, 1Fh
0x10048553f  ja      loc_100485770
0x100485545  call    ??3@YAXPEAX@Z; operator delete(void *)
0x10048554a  mov     rax, rsi
0x10048554d  mov     rcx, [rbp+57h+var_38]
0x100485551  xor     rcx, rsp; StackCookie
0x100485554  call    __security_check_cookie
0x100485559  mov     rbx, [rsp+120h+arg_18]
  ... truncated ...
```
