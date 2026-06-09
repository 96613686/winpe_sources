# Ssl::CreateCertificateContext(std::vector<char,std::allocator<char>> const &,_CERT_CONTEXT const * &)

- ea: `0x1801796c0`
- end: `0x180179a98`
- name: `?CreateCertificateContext@Ssl@@CAKAEBV?$vector@DV?$allocator@D@std@@@std@@AEAPEBU_CERT_CONTEXT@@@Z`
- size: `984`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, loader_planting`

## callers

- `0x18017c160`

## callees

- `0x180001f70`
- `0x1800030c0`
- `0x180003824`
- `0x180003d80`
- `0x180005180`
- `0x180179450`
- `0x1801796c0`
- `0x1801a65f0`
- `0x1801a6640`
- `0x1801ad6a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1801799b2`
- `KERNEL32!GetLastError` at `0x1801799b2`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1801798e4`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180179a55`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1801798e4`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180179a55`
- `CRYPT32!CertCreateCertificateContext` at `0x1801799a0`
- `CRYPT32!CertCreateCertificateContext` at `0x1801799a0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Ssl::CreateCertificateContext(__int64 a1, PCCERT_CONTEXT *a2)
{
  DWORD LastError; // esi
  const void *v4; // rdi
  __int64 v5; // r13
  size_t v6; // rbx
  wchar_t *v7; // r8
  __int64 v8; // rdx
  char *v9; // rcx
  __int64 v10; // r13
  unsigned __int64 v11; // r14
  void *v12; // r15
  void **v13; // r12
  char *v14; // r13
  size_t v15; // r8
  void **i; // rcx
  _BYTE *v17; // rbx
  void **v18; // rbx
  __int64 v19; // rbx
  unsigned __int64 v20; // rdx
  _BYTE *v21; // rax
  DWORD v22; // eax
  __int64 v23; // r9
  PCCERT_CONTEXT CertificateContext; // rax
  void *v25; // rdi
  unsigned __int64 v26; // rdx
  DWORD cbCertEncoded[2]; // [rsp+40h] [rbp-39h]
  void *Buf[2]; // [rsp+48h] [rbp-31h] BYREF
  size_t v30; // [rsp+58h] [rbp-21h]
  __int64 v31; // [rsp+60h] [rbp-19h]
  __int64 v32; // [rsp+68h] [rbp-11h]
  PCCERT_CONTEXT *v33; // [rsp+70h] [rbp-9h]
  void *v34[2]; // [rsp+78h] [rbp-1h] BYREF
  __int64 v35; // [rsp+88h] [rbp+Fh]
  __int64 v36; // [rsp+90h] [rbp+17h] BYREF

  v33 = a2;
  v32 = a1;
  v36 = -1;
  LastError = 0;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_180266D88[0] && bidID != -1 )
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *, wchar_t *, _QWORD))off_180248060[0])(
      bidID,
      0,
      0,
      &v36,
      off_180266D88[0],
      0);
  *(_OWORD *)v34 = 0;
  v35 = 0;
  v4 = *(const void **)a1;
  v5 = *(_QWORD *)(a1 + 8);
  v6 = v5 - *(_QWORD *)a1;
  if ( v6 > 0xFFFFFFFF )
  {
    LastError = 87;
    if ( (bidGblFlags & 2) != 0 && off_1802652C8[0] )
    {
      v7 = off_1802652C8[0];
      v8 = 1050624;
      v9 = off_180261F80[0];
LABEL_46:
      v23 = LastError;
      goto LABEL_47;
    }
    goto LABEL_48;
  }
  v10 = (unsigned int)(v5 - (_DWORD)v4);
  *(_QWORD *)cbCertEncoded = v10;
  *(_OWORD *)Buf = 0;
  if ( v6 > 0xF )
  {
    v11 = 0x7FFFFFFFFFFFFFFFLL;
    if ( (v6 | 0xF) <= 0x7FFFFFFFFFFFFFFFLL )
    {
      v11 = v6 | 0xF;
      if ( (v6 | 0xF) < 0x16 )
        v11 = 22;
    }
    v12 = (void *)std::_Allocate<16,std::_Default_allocate_traits>(v11 + 1);
    Buf[0] = v12;
    v30 = v6;
    v31 = v11;
    memcpy_0(v12, v4, v6);
    *((_BYTE *)v12 + v6) = 0;
  }
  else
  {
    v30 = v6;
    v31 = 15;
    memcpy_0(Buf, v4, v6);
    *((_BYTE *)Buf + v6) = 0;
    v11 = v31;
    v6 = v30;
    v12 = Buf[0];
  }
  v13 = Buf;
  if ( v11 > 0xF )
    v13 = (void **)v12;
  if ( v6 >= 0xB )
  {
    v14 = (char *)v13 + v6;
    v15 = v6 - 10;
    for ( i = v13; ; i = v18 )
    {
      v17 = memchr_0(i, 45, v15);
      if ( !v17 )
        break;
      if ( *(_QWORD *)v17 == 0x4745422D2D2D2D2DLL && *((_WORD *)v17 + 4) == 20041 && v17[10] == 32 )
      {
        v19 = v17 - (_BYTE *)v13;
        LODWORD(v10) = cbCertEncoded[0];
        goto LABEL_27;
      }
      v18 = (void **)(v17 + 1);
      v15 = v14 - 10 - (char *)v18;
    }
    LODWORD(v10) = cbCertEncoded[0];
  }
  v19 = -1;
LABEL_27:
  if ( v11 > 0xF )
  {
    v20 = v11 + 1;
    v21 = v12;
    if ( v11 + 1 >= 0x1000 )
    {
      v20 = v11 + 40;
      v12 = (void *)*((_QWORD *)v12 - 1);
      if ( (unsigned __int64)(v21 - (_BYTE *)v12 - 8) > 0x1F )
        _invalid_parameter_noinfo_noreturn();
    }
    operator delete(v12, v20);
  }
  if ( v19 == -1 )
  {
LABEL_42:
    CertificateContext = CertCreateCertificateContext(0x10001u, (const BYTE *)v4, v10);
    *v33 = CertificateContext;
    if ( !CertificateContext )
    {
      LastError = GetLastError();
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( off_1802652E0[0] )
        {
          v7 = off_1802652E0[0];
          v8 = 1082368;
          v9 = off_180261F98[0];
          goto LABEL_46;
        }
      }
    }
    goto LABEL_48;
  }
  v22 = Ssl::ConvertBase64StringToBinaryBlob(v32, v34);
  LastError = v22;
  if ( v22 )
  {
    if ( (bidGblFlags & 2) != 0 && off_1802652D0[0] )
    {
      v23 = v22;
      v7 = off_1802652D0[0];
      v8 = 1061888;
      v9 = off_180261F88[0];
LABEL_47:
      bidTraceW(v9, v8, v7, v23);
      goto LABEL_48;
    }
    goto LABEL_48;
  }
  if ( (void *)((char *)v34[1] - (char *)v34[0]) <= (void *)0xFFFFFFFFLL )
  {
    v4 = v34[0];
    LODWORD(v10) = LODWORD(v34[1]) - LODWORD(v34[0]);
    goto LABEL_42;
  }
  LastError = 87;
  if ( (bidGblFlags & 2) != 0 && off_1802652D8[0] )
  {
    v7 = off_1802652D8[0];
    v8 = 1069056;
    v9 = off_180261F90[0];
    goto LABEL_46;
  }
LABEL_48:
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_1802652E8[0] )
    bidTraceW(off_180261FA0[0], 1088512, off_1802652E8[0], LastError);
  v25 = v34[0];
  if ( v34[0] )
  {
    v26 = v35 - (unsigned __int64)v34[0];
    if ( v35 - (unsigned __int64)v34[0] >= 0x1000 )
    {
      v26 += 39LL;
      v25 = (void *)*((_QWORD *)v34[0] - 1);
      if ( (unsigned __int64)((char *)v34[0] - (char *)v25 - 8) > 0x1F )
        _invalid_parameter_noinfo_noreturn();
    }
    operator delete(v25, v26);
  }
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v36);
  return LastError;
}

```

## disassembly

```asm
0x1801796c0  mov     [rsp-8+arg_10], rbx
0x1801796c5  push    rbp
0x1801796c6  push    rsi
0x1801796c7  push    rdi
0x1801796c8  push    r12
0x1801796ca  push    r13
0x1801796cc  push    r14
0x1801796ce  push    r15
0x1801796d0  lea     rbp, [rsp-27h]
0x1801796d5  sub     rsp, 0A0h
0x1801796dc  mov     rax, cs:__security_cookie
0x1801796e3  xor     rax, rsp
0x1801796e6  mov     [rbp+57h+var_38], rax
0x1801796ea  mov     [rbp+57h+var_60], rdx
0x1801796ee  mov     rbx, rcx
0x1801796f1  mov     [rbp+57h+var_68], rcx
0x1801796f5  mov     [rbp+57h+var_40], 0FFFFFFFFFFFFFFFFh
0x1801796fd  mov     eax, cs:_bidGblFlags
0x180179703  and     eax, 20004h
0x180179708  xor     esi, esi
0x18017970a  cmp     eax, 20004h
0x18017970f  jnz     short loc_180179758
0x180179711  mov     rax, cs:off_180266D88; "<Ssl::CreateCertificateContext|API|SNI>"...
0x180179718  test    rax, rax
0x18017971b  jz      short loc_180179758
0x18017971d  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x180179725  jz      short loc_180179758
0x180179727  mov     r10, cs:off_180248060
0x18017972e  mov     [rsp+0D0h+var_A8], rsi
0x180179733  mov     rax, cs:off_180266D88; "<Ssl::CreateCertificateContext|API|SNI>"...
0x18017973a  mov     [rsp+0D0h+var_B0], rax
0x18017973f  lea     r9, [rbp+57h+var_40]
0x180179743  xor     r8d, r8d
0x180179746  xor     edx, edx
0x180179748  mov     rcx, cs:_bidID
0x18017974f  mov     rax, r10
0x180179752  call    cs:__guard_dispatch_icall_fptr
0x180179758  xorps   xmm0, xmm0
0x18017975b  xorps   xmm1, xmm1
0x18017975e  movdqu  xmmword ptr [rbp+57h+var_58], xmm1
0x180179763  mov     [rbp+57h+var_48], rsi
0x180179767  mov     rdi, [rbx]
0x18017976a  mov     r13, [rbx+8]
0x18017976e  mov     rbx, r13
0x180179771  sub     rbx, rdi
0x180179774  mov     eax, 0FFFFFFFFh
0x180179779  cmp     rbx, rax
0x18017977c  jbe     short loc_1801797B8
0x18017977e  mov     esi, 57h ; 'W'
0x180179783  test    byte ptr cs:_bidGblFlags, 2
0x18017978a  jz      loc_1801799EA
0x180179790  mov     rax, cs:off_1802652C8; "<Ssl::CreateCertificateContext|ERR|SNI>"...
0x180179797  test    rax, rax
0x18017979a  jz      loc_1801799EA
0x1801797a0  mov     r8, cs:off_1802652C8; "<Ssl::CreateCertificateContext|ERR|SNI>"...
0x1801797a7  mov     edx, 100800h
0x1801797ac  mov     rcx, cs:off_180261F80; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x1801797b3  jmp     loc_1801799E2
0x1801797b8  sub     r13d, edi
0x1801797bb  mov     qword ptr [rbp+57h+cbCertEncoded], r13
0x1801797bf  movups  xmmword ptr [rbp+57h+Buf], xmm0
0x1801797c3  cmp     rbx, 0Fh
0x1801797c7  ja      short loc_1801797F7
0x1801797c9  mov     [rbp+57h+var_78], rbx
0x1801797cd  mov     [rbp+57h+var_70], 0Fh
0x1801797d5  mov     r8, rbx; Size
0x1801797d8  mov     rdx, rdi; Src
0x1801797db  lea     rcx, [rbp+57h+Buf]; void *
0x1801797df  call    memcpy_0
0x1801797e4  mov     byte ptr [rbp+rbx+57h+Buf], 0
0x1801797e9  mov     r14, [rbp+57h+var_70]
0x1801797ed  mov     rbx, [rbp+57h+var_78]
0x1801797f1  mov     r15, [rbp+57h+Buf]
0x1801797f5  jmp     short loc_180179847
0x1801797f7  mov     rax, rbx
0x1801797fa  or      rax, 0Fh
0x1801797fe  mov     r14, 7FFFFFFFFFFFFFFFh
0x180179808  cmp     rax, r14
0x18017980b  ja      short loc_18017981C
0x18017980d  mov     r14, rax
0x180179810  mov     ecx, 16h
0x180179815  cmp     rax, rcx
0x180179818  cmovb   r14, rcx
0x18017981c  lea     rcx, [r14+1]
0x180179820  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180179825  mov     r15, rax
0x180179828  mov     [rbp+57h+Buf], rax
0x18017982c  mov     [rbp+57h+var_78], rbx
0x180179830  mov     [rbp+57h+var_70], r14
0x180179834  mov     r8, rbx; Size
0x180179837  mov     rdx, rdi; Src
0x18017983a  mov     rcx, rax; void *
0x18017983d  call    memcpy_0
0x180179842  mov     byte ptr [r15+rbx], 0
0x180179847  lea     r12, [rbp+57h+Buf]
0x18017984b  cmp     r14, 0Fh
0x18017984f  cmova   r12, r15
0x180179853  cmp     rbx, 0Bh
0x180179857  jb      short loc_1801798B2
0x180179859  lea     r13, [rbx+r12]
0x18017985d  lea     r8, [r13-0Ah]
0x180179861  sub     r8, r12; MaxCount
0x180179864  mov     rcx, r12; Buf
0x180179867  mov     edx, 2Dh ; '-'; Val
0x18017986c  call    memchr_0
0x180179871  test    rax, rax
0x180179874  mov     rbx, rax
0x180179877  jz      short loc_1801798AE
0x180179879  mov     rax, 4745422D2D2D2D2Dh
0x180179883  cmp     [rbx], rax
0x180179886  jnz     short loc_180179896
0x180179888  cmp     word ptr [rbx+8], 4E49h
0x18017988e  jnz     short loc_180179896
0x180179890  cmp     byte ptr [rbx+0Ah], 20h ; ' '
0x180179894  jz      short loc_1801798A5
0x180179896  inc     rbx
0x180179899  lea     r8, [r13-0Ah]
0x18017989d  sub     r8, rbx
0x1801798a0  mov     rcx, rbx
0x1801798a3  jmp     short loc_180179867
0x1801798a5  sub     rbx, r12
0x1801798a8  mov     r13, qword ptr [rbp+57h+cbCertEncoded]
0x1801798ac  jmp     short loc_1801798B9
0x1801798ae  mov     r13, qword ptr [rbp+57h+cbCertEncoded]
0x1801798b2  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1801798b9  cmp     r14, 0Fh
0x1801798bd  jbe     short loc_1801798F3
0x1801798bf  lea     rdx, [r14+1]; unsigned __int64
0x1801798c3  mov     rax, r15
0x1801798c6  cmp     rdx, 1000h
0x1801798cd  jb      short loc_1801798EB
0x1801798cf  add     rdx, 27h ; '''
0x1801798d3  mov     r15, [r15-8]
0x1801798d7  sub     rax, r15
0x1801798da  add     rax, 0FFFFFFFFFFFFFFF8h
0x1801798de  cmp     rax, 1Fh
0x1801798e2  jbe     short loc_1801798EB
0x1801798e4  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x1801798eb  mov     rcx, r15; void *
0x1801798ee  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1801798f3  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1801798f7  jz      loc_180179995
0x1801798fd  lea     rdx, [rbp+57h+var_58]
0x180179901  mov     rcx, [rbp+57h+var_68]
0x180179905  call    ?ConvertBase64StringToBinaryBlob@Ssl@@CAKAEBV?$vector@DV?$allocator@D@std@@@std@@AEAV?$vector@EV?$allocator@E@std@@@3@@Z; Ssl::ConvertBase64StringToBinaryBlob(std::vector<char> const &,std::vector<uchar> &)
0x18017990a  mov     esi, eax
0x18017990c  test    eax, eax
0x18017990e  jz      short loc_180179948
0x180179910  test    byte ptr cs:_bidGblFlags, 2
0x180179917  jz      loc_1801799EA
0x18017991d  mov     rcx, cs:off_1802652D0; "<Ssl::CreateCertificateContext|ERR|SNI>"...
0x180179924  test    rcx, rcx
0x180179927  jz      loc_1801799EA
0x18017992d  mov     r9d, eax
0x180179930  mov     r8, cs:off_1802652D0; "<Ssl::CreateCertificateContext|ERR|SNI>"...
0x180179937  mov     edx, 103400h
0x18017993c  mov     rcx, cs:off_180261F88; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x180179943  jmp     loc_1801799E5
0x180179948  mov     rcx, [rbp+57h+var_58+8]
0x18017994c  mov     rax, rcx
0x18017994f  sub     rax, [rbp+57h+var_58]
0x180179953  mov     edx, 0FFFFFFFFh
0x180179958  cmp     rax, rdx
0x18017995b  jbe     short loc_18017998C
0x18017995d  mov     esi, 57h ; 'W'
0x180179962  test    byte ptr cs:_bidGblFlags, 2
0x180179969  jz      short loc_1801799EA
0x18017996b  mov     rax, cs:off_1802652D8; "<Ssl::CreateCertificateContext|ERR|SNI>"...
0x180179972  test    rax, rax
0x180179975  jz      short loc_1801799EA
0x180179977  mov     r8, cs:off_1802652D8; "<Ssl::CreateCertificateContext|ERR|SNI>"...
0x18017997e  mov     edx, 105000h
0x180179983  mov     rcx, cs:off_180261F90; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18017998a  jmp     short loc_1801799E2
0x18017998c  mov     rdi, [rbp+57h+var_58]
0x180179990  sub     ecx, edi
0x180179992  mov     r13d, ecx
0x180179995  mov     r8d, r13d; cbCertEncoded
0x180179998  mov     rdx, rdi; pbCertEncoded
0x18017999b  mov     ecx, 10001h; dwCertEncodingType
0x1801799a0  call    cs:__imp_CertCreateCertificateContext
0x1801799a6  mov     rcx, [rbp+57h+var_60]
0x1801799aa  mov     [rcx], rax
0x1801799ad  test    rax, rax
0x1801799b0  jnz     short loc_1801799EA
0x1801799b2  call    cs:__imp_GetLastError
0x1801799b8  mov     esi, eax
0x1801799ba  test    byte ptr cs:_bidGblFlags, 2
0x1801799c1  jz      short loc_1801799EA
0x1801799c3  mov     rax, cs:off_1802652E0; "<Ssl::CreateCertificateContext|ERR|SNI>"...
0x1801799ca  test    rax, rax
0x1801799cd  jz      short loc_1801799EA
0x1801799cf  mov     r8, cs:off_1802652E0; "<Ssl::CreateCertificateContext|ERR|SNI>"...
0x1801799d6  mov     edx, 108400h
0x1801799db  mov     rcx, cs:off_180261F98; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x1801799e2  mov     r9d, esi
0x1801799e5  call    _bidTraceW
0x1801799ea  mov     eax, cs:_bidGblFlags
0x1801799f0  and     eax, 20002h
0x1801799f5  cmp     eax, 20002h
0x1801799fa  jnz     short loc_180179A24
0x1801799fc  mov     rax, cs:off_1802652E8; "<Ssl::CreateCertificateContext|RET|SNI>"...
0x180179a03  test    rax, rax
0x180179a06  jz      short loc_180179A24
0x180179a08  mov     r9d, esi
0x180179a0b  mov     r8, cs:off_1802652E8; "<Ssl::CreateCertificateContext|RET|SNI>"...
0x180179a12  mov     edx, 109C00h
0x180179a17  mov     rcx, cs:off_180261FA0; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x180179a1e  call    _bidTraceW
0x180179a23  nop
0x180179a24  mov     rdi, [rbp+57h+var_58]
0x180179a28  test    rdi, rdi
0x180179a2b  jz      short loc_180179A65
0x180179a2d  mov     rdx, [rbp+57h+var_48]
0x180179a31  sub     rdx, rdi; unsigned __int64
0x180179a34  mov     rax, rdi
0x180179a37  cmp     rdx, 1000h
0x180179a3e  jb      short loc_180179A5C
0x180179a40  add     rdx, 27h ; '''
0x180179a44  mov     rdi, [rdi-8]
0x180179a48  sub     rax, rdi
0x180179a4b  add     rax, 0FFFFFFFFFFFFFFF8h
0x180179a4f  cmp     rax, 1Fh
0x180179a53  jbe     short loc_180179A5C
0x180179a55  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x180179a5c  mov     rcx, rdi; void *
0x180179a5f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180179a64  nop
0x180179a65  lea     rcx, [rbp+57h+var_40]; this
0x180179a69  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x180179a6e  nop
0x180179a6f  mov     eax, esi
0x180179a71  mov     rcx, [rbp+57h+var_38]
0x180179a75  xor     rcx, rsp; StackCookie
0x180179a78  call    __security_check_cookie
0x180179a7d  mov     rbx, [rsp+0D0h+arg_10]
0x180179a85  add     rsp, 0A0h
0x180179a8c  pop     r15
0x180179a8e  pop     r14
0x180179a90  pop     r13
0x180179a92  pop     r12
0x180179a94  pop     rdi
0x180179a95  pop     rsi
0x180179a96  pop     rbp
0x180179a97  retn
```
