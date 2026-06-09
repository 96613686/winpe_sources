# GetURLContents

- ea: `0x100475548`
- end: `0x100475968`
- name: `GetURLContents`
- size: `1056`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x100474a74`
- `0x1004750f0`

## callees

- `0x10040128c`
- `0x10042a7b4`
- `0x100431464`
- `0x10047291c`
- `0x100473820`
- `0x100475548`
- `0x100548210`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x100475733`
- `KERNEL32!GetLastError` at `0x1004757ae`
- `KERNEL32!GetLastError` at `0x1004758c0`
- `KERNEL32!GetLastError` at `0x1004758d7`
- `KERNEL32!GetLastError` at `0x100475733`
- `KERNEL32!GetLastError` at `0x1004757ae`
- `KERNEL32!GetLastError` at `0x1004758c0`
- `KERNEL32!GetLastError` at `0x1004758d7`
- `KERNEL32!SetLastError` at `0x1004758ba`
- `KERNEL32!SetLastError` at `0x1004758ba`
- `WININET!HttpSendRequestW` at `0x1004757a4`
- `WININET!HttpSendRequestW` at `0x1004757ce`
- `WININET!HttpSendRequestW` at `0x1004757a4`
- `WININET!HttpSendRequestW` at `0x1004757ce`
- `WININET!InternetReadFile` at `0x100475823`
- `WININET!InternetReadFile` at `0x100475823`
- `WININET!InternetConnectW` at `0x1004756d1`
- `WININET!InternetConnectW` at `0x1004756d1`
- `WININET!InternetCloseHandle` at `0x100475830`
- `WININET!InternetCloseHandle` at `0x100475849`
- `WININET!InternetCloseHandle` at `0x100475853`
- `WININET!InternetCloseHandle` at `0x1004758cc`
- `WININET!InternetCloseHandle` at `0x100475830`
- `WININET!InternetCloseHandle` at `0x100475849`
- `WININET!InternetCloseHandle` at `0x100475853`
- `WININET!InternetCloseHandle` at `0x1004758cc`
- `WININET!InternetOpenA` at `0x1004755d8`
- `WININET!InternetOpenA` at `0x1004755d8`
- `WININET!HttpOpenRequestW` at `0x100475781`
- `WININET!HttpOpenRequestW` at `0x100475781`
- `VCRUNTIME140!wcschr` at `0x100475659`
- `VCRUNTIME140!wcschr` at `0x100475659`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x100475612`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10047563f`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x100475612`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10047563f`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1004758ae`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x100475961`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1004758ae`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x100475961`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetURLContents(void (__fastcall **a1)(_QWORD, __int64, _QWORD), const wchar_t *a2, void **a3)
{
  void (__fastcall **v5)(_QWORD, __int64, _QWORD); // rsi
  const wchar_t *v6; // rax
  __int64 v7; // r8
  unsigned int i; // r12d
  INTERNET_PORT v9; // r13
  const wchar_t *v10; // rbx
  wchar_t *v11; // rax
  __int64 v12; // r9
  wchar_t *v13; // rsi
  wchar_t *v14; // r8
  __int64 v15; // rax
  const WCHAR *v16; // rdx
  void *v17; // r13
  WCHAR *v18; // rdx
  DWORD v19; // eax
  const WCHAR *v20; // r8
  void *v21; // rax
  void *v22; // rbx
  unsigned int v23; // esi
  char *j; // rdx
  WCHAR *v25; // rdx
  DWORD LastError; // ebx
  void *v27; // rcx
  char v29[4]; // [rsp+48h] [rbp-59h] BYREF
  DWORD dwNumberOfBytesRead; // [rsp+4Ch] [rbp-55h] BYREF
  void (__fastcall **v31)(_QWORD, __int64, _QWORD); // [rsp+50h] [rbp-51h]
  HINTERNET hInternet; // [rsp+58h] [rbp-49h]
  LPCWSTR lpszAcceptTypes[3]; // [rsp+60h] [rbp-41h] BYREF
  LPCWSTR lpszServerName[3]; // [rsp+78h] [rbp-29h] BYREF
  unsigned __int64 v35; // [rsp+90h] [rbp-11h]
  unsigned __int64 v36; // [rsp+98h] [rbp-9h] BYREF
  __m128i si128; // [rsp+A8h] [rbp+7h]

  lpszAcceptTypes[2] = (LPCWSTR)-2LL;
  v5 = a1;
  v31 = a1;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v36) = 0;
  v6 = a2;
  v7 = 0;
  for ( i = 1; *v6; ++v6 )
    ++v7;
  std::basic_string<char16_t>::assign(&v36, a2, v7);
  hInternet = InternetOpenA("MSODBCEP", 0, 0, 0, 0);
  if ( !hInternet )
  {
    LastError = GetLastError();
    goto LABEL_45;
  }
  v9 = 80;
  dwNumberOfBytesRead = 0;
  if ( !wcsncmp(a2, L"https://", 8u) )
  {
    v9 = 443;
    dwNumberOfBytesRead = 0x800000;
    v10 = a2 + 8;
  }
  else
  {
    if ( wcsncmp(a2, L"http://", 7u) )
    {
      SetLastError(0x2EE5u);
      v19 = GetLastError();
LABEL_43:
      LastError = v19;
      InternetCloseHandle(hInternet);
LABEL_45:
      (*v5)(v5, 100, LastError);
      i = 0;
      goto LABEL_46;
    }
    v10 = a2 + 7;
  }
  v11 = wcschr(v10, 0x2Fu);
  v13 = v11;
  if ( v11 )
  {
    v14 = v11;
  }
  else
  {
    v15 = -1;
    do
      ++v15;
    while ( v10[v15] );
    v14 = (wchar_t *)&v10[v15];
  }
  lpszServerName[2] = 0;
  v35 = 7;
  LOWORD(lpszServerName[0]) = 0;
  LOBYTE(v12) = v29[0];
  std::basic_string<char16_t>::_Construct<unsigned short *>(lpszServerName, v10, v14, v12);
  v16 = (const WCHAR *)lpszServerName;
  if ( v35 >= 8 )
    v16 = lpszServerName[0];
  v17 = InternetConnectW(hInternet, v16, v9, 0, 0, 3u, 0, 0);
  if ( !v17 )
    goto LABEL_16;
  lpszAcceptTypes[0] = L"*/*";
  lpszAcceptTypes[1] = 0;
  v20 = L"/";
  if ( v13 )
    v20 = v13;
  v21 = HttpOpenRequestW(v17, 0, v20, 0, 0, lpszAcceptTypes, dwNumberOfBytesRead, 0);
  v22 = v21;
  v23 = 0;
  if ( !v21 || !HttpSendRequestW(v21, 0, 0, 0, 0) && (GetLastError() != 12044 || !HttpSendRequestW(v22, 0, 0, 0, 0)) )
  {
LABEL_16:
    if ( v35 >= 8 )
    {
      v18 = (WCHAR *)lpszServerName[0];
      if ( v35 + 1 > 0x7FFFFFFFFFFFFFFFLL )
        goto LABEL_41;
      if ( 2 * (v35 + 1) >= 0x1000 )
      {
        if ( ((__int64)lpszServerName[0] & 0x1F) != 0 )
          goto LABEL_41;
        v18 = (WCHAR *)*((_QWORD *)lpszServerName[0] - 1);
        if ( v18 >= lpszServerName[0] || (unsigned __int64)((char *)lpszServerName[0] - (char *)v18 - 8) > 0x1F )
          goto LABEL_41;
      }
      operator delete(v18);
    }
    v19 = GetLastError();
    v5 = v31;
    goto LABEL_43;
  }
  dwNumberOfBytesRead = 0;
  std::vector<unsigned char>::_Resize<_lambda_2b51424039c320f102fd798e073c89b2_>(a3, 4096, a3);
  for ( j = (char *)*a3;
        InternetReadFile(v22, j, 0x1000u, &dwNumberOfBytesRead) && dwNumberOfBytesRead;
        j = (char *)*a3 + v23 )
  {
    v23 += dwNumberOfBytesRead;
    std::vector<unsigned char>::_Resize<_lambda_2b51424039c320f102fd798e073c89b2_>(a3, v23 + 4096, a3);
  }
  InternetCloseHandle(v22);
  v29[0] = 0;
  std::vector<unsigned char>::emplace_back<unsigned char const &>(a3, v29);
  InternetCloseHandle(v17);
  InternetCloseHandle(hInternet);
  if ( v35 >= 8 )
  {
    v25 = (WCHAR *)lpszServerName[0];
    if ( v35 + 1 <= 0x7FFFFFFFFFFFFFFFLL )
    {
      if ( 2 * (v35 + 1) < 0x1000
        || ((__int64)lpszServerName[0] & 0x1F) == 0
        && (v25 = (WCHAR *)*((_QWORD *)lpszServerName[0] - 1), v25 < lpszServerName[0])
        && (unsigned __int64)((char *)lpszServerName[0] - (char *)v25 - 8) <= 0x1F )
      {
        operator delete(v25);
        goto LABEL_46;
      }
    }
LABEL_41:
    _invalid_parameter_noinfo_noreturn();
  }
LABEL_46:
  if ( si128.m128i_i64[1] >= 8uLL )
  {
    v27 = (void *)v36;
    if ( (unsigned __int64)(si128.m128i_i64[1] + 1) > 0x7FFFFFFFFFFFFFFFLL
      || (unsigned __int64)(2 * (si128.m128i_i64[1] + 1)) >= 0x1000
      && ((v36 & 0x1F) != 0
       || (v27 = *(void **)(v36 - 8), (unsigned __int64)v27 >= v36)
       || v36 - (unsigned __int64)v27 - 8 > 0x1F) )
    {
      _invalid_parameter_noinfo_noreturn();
    }
    operator delete(v27);
  }
  return i;
}

```

## disassembly

```asm
0x100475548  mov     rax, rsp
0x10047554b  push    rbp
0x10047554c  push    rsi
0x10047554d  push    rdi
0x10047554e  push    r12
0x100475550  push    r13
0x100475552  push    r14
0x100475554  push    r15
0x100475556  lea     rbp, [rax-5Fh]
0x10047555a  sub     rsp, 0C0h
0x100475561  mov     [rbp+57h+var_88], 0FFFFFFFFFFFFFFFEh
0x100475569  mov     [rax+20h], rbx
0x10047556d  mov     rax, cs:__security_cookie
0x100475574  xor     rax, rsp
0x100475577  mov     [rbp+57h+var_40], rax
0x10047557b  mov     r14, r8
0x10047557e  mov     rbx, rdx
0x100475581  mov     rsi, rcx
0x100475584  mov     [rbp+57h+var_A8], rcx
0x100475588  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x100475590  movdqu  [rbp+57h+var_50], xmm0
0x100475595  xor     r13d, r13d
0x100475598  mov     word ptr [rbp+57h+var_60], r13w
0x10047559d  mov     rax, rdx
0x1004755a0  mov     r8d, r13d
0x1004755a3  lea     r12d, [r13+1]
0x1004755a7  cmp     [rdx], r13w
0x1004755ab  jz      short loc_1004755BA
0x1004755ad  add     r8, r12
0x1004755b0  lea     rax, [rax+2]
0x1004755b4  cmp     [rax], r13w
0x1004755b8  jnz     short loc_1004755AD
0x1004755ba  lea     rcx, [rbp+57h+var_60]
0x1004755be  call    ?assign@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@QEAAAEAV12@QEB_S_K@Z; std::basic_string<char16_t>::assign(char16_t const * const,unsigned __int64)
0x1004755c3  nop
0x1004755c4  mov     [rsp+0F0h+dwFlags], r13d; dwFlags
0x1004755c9  xor     r9d, r9d; lpszProxyBypass
0x1004755cc  xor     r8d, r8d; lpszProxy
0x1004755cf  xor     edx, edx; dwAccessType
0x1004755d1  lea     rcx, szAgent; "MSODBCEP"
0x1004755d8  call    cs:__imp_InternetOpenA
0x1004755de  mov     [rbp+57h+hInternet], rax
0x1004755e2  mov     edi, 1000h
0x1004755e7  mov     r15, 7FFFFFFFFFFFFFFFh
0x1004755f1  test    rax, rax
0x1004755f4  jz      loc_1004758D7
0x1004755fa  mov     r13d, 50h ; 'P'
0x100475600  and     [rbp+57h+dwNumberOfBytesRead], 0
0x100475604  lea     r8d, [r13-48h]; MaxCount
0x100475608  lea     rdx, aHttps; "https://"
0x10047560f  mov     rcx, rbx; String1
0x100475612  call    cs:__imp_wcsncmp
0x100475618  test    eax, eax
0x10047561a  jnz     short loc_10047562F
0x10047561c  mov     r13d, 1BBh
0x100475622  mov     [rbp+57h+dwNumberOfBytesRead], 800000h
0x100475629  add     rbx, 10h
0x10047562d  jmp     short loc_100475651
0x10047562f  mov     r8d, 7; MaxCount
0x100475635  lea     rdx, aHttp; "http://"
0x10047563c  mov     rcx, rbx; String1
0x10047563f  call    cs:__imp_wcsncmp
0x100475645  test    eax, eax
0x100475647  jnz     loc_1004758B5
0x10047564d  add     rbx, 0Eh
0x100475651  mov     edx, 2Fh ; '/'; Ch
0x100475656  mov     rcx, rbx; Str
0x100475659  call    cs:__imp_wcschr
0x10047565f  mov     rsi, rax
0x100475662  xor     ecx, ecx
0x100475664  test    rax, rax
0x100475667  jz      short loc_10047566E
0x100475669  mov     r8, rax
0x10047566c  jmp     short loc_10047567F
0x10047566e  or      rax, 0FFFFFFFFFFFFFFFFh
0x100475672  inc     rax
0x100475675  cmp     [rbx+rax*2], cx
0x100475679  jnz     short loc_100475672
0x10047567b  lea     r8, [rbx+rax*2]
0x10047567f  mov     [rbp+57h+var_70], rcx
0x100475683  mov     [rbp+57h+var_68], 7
0x10047568b  mov     word ptr [rbp+57h+lpszServerName], cx
0x10047568f  mov     r9b, [rbp+57h+var_B0]
0x100475693  mov     rdx, rbx
0x100475696  lea     rcx, [rbp+57h+lpszServerName]
0x10047569a  call    ??$_Construct@PEAG@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@QEAAXQEAG0Uforward_iterator_tag@1@@Z; std::basic_string<char16_t>::_Construct<ushort *>(ushort * const,ushort * const,std::forward_iterator_tag)
0x10047569f  nop
0x1004756a0  lea     rdx, [rbp+57h+lpszServerName]
0x1004756a4  cmp     [rbp+57h+var_68], 8
0x1004756a9  cmovnb  rdx, [rbp+57h+lpszServerName]; lpszServerName
0x1004756ae  xor     ebx, ebx
0x1004756b0  mov     [rsp+38h], rbx; dwContext
0x1004756b5  mov     [rsp+0F0h+var_C0], ebx; dwFlags
0x1004756b9  mov     [rsp+0F0h+dwService], 3; dwService
0x1004756c1  mov     qword ptr [rsp+0F0h+dwFlags], rbx; lpszPassword
0x1004756c6  xor     r9d, r9d; lpszUserName
0x1004756c9  movzx   r8d, r13w; nServerPort
0x1004756cd  mov     rcx, [rbp+57h+hInternet]; hInternet
0x1004756d1  call    cs:__imp_InternetConnectW
0x1004756d7  mov     r13, rax
0x1004756da  test    rax, rax
0x1004756dd  jnz     short loc_100475742
0x1004756df  mov     rax, [rbp+57h+var_68]
0x1004756e3  cmp     rax, 8
0x1004756e7  jb      short loc_100475733
0x1004756e9  inc     rax
0x1004756ec  mov     rdx, [rbp+57h+lpszServerName]
0x1004756f0  cmp     rax, r15
0x1004756f3  mov     rcx, rdx
0x1004756f6  ja      loc_1004758AE
0x1004756fc  add     rax, rax
0x1004756ff  cmp     rax, rdi
0x100475702  jb      short loc_10047572B
0x100475704  test    cl, 1Fh
0x100475707  jnz     loc_1004758AE
0x10047570d  mov     rdx, [rdx-8]
0x100475711  cmp     rdx, rcx
0x100475714  jnb     loc_1004758AE
0x10047571a  sub     rcx, rdx
0x10047571d  sub     rcx, 8
0x100475721  cmp     rcx, 1Fh
0x100475725  ja      loc_1004758AE
0x10047572b  mov     rcx, rdx; void *
0x10047572e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x100475733  call    cs:__imp_GetLastError
0x100475739  mov     rsi, [rbp+57h+var_A8]
0x10047573d  jmp     loc_1004758C6
0x100475742  lea     rax, asc_100594E70; "*/*"
0x100475749  mov     [rbp+57h+lpszAcceptTypes], rax
0x10047574d  mov     [rbp+57h+var_90], rbx
0x100475751  lea     r8, asc_100594E78; "/"
0x100475758  test    rsi, rsi
0x10047575b  cmovnz  r8, rsi; lpszObjectName
0x10047575f  mov     [rsp+38h], rbx; dwContext
0x100475764  mov     eax, [rbp+57h+dwNumberOfBytesRead]
0x100475767  mov     [rsp+0F0h+var_C0], eax; dwFlags
0x10047576b  lea     rax, [rbp+57h+lpszAcceptTypes]
0x10047576f  mov     qword ptr [rsp+0F0h+dwService], rax; lplpszAcceptTypes
0x100475774  mov     qword ptr [rsp+0F0h+dwFlags], rbx; lpszReferrer
0x100475779  xor     r9d, r9d; lpszVersion
0x10047577c  xor     edx, edx; lpszVerb
0x10047577e  mov     rcx, r13; hConnect
0x100475781  call    cs:__imp_HttpOpenRequestW
0x100475787  mov     rbx, rax
0x10047578a  xor     esi, esi
0x10047578c  test    rax, rax
0x10047578f  jz      loc_1004756DF
0x100475795  mov     [rsp+0F0h+dwFlags], esi; dwOptionalLength
0x100475799  xor     r9d, r9d; lpOptional
0x10047579c  xor     r8d, r8d; dwHeadersLength
0x10047579f  xor     edx, edx; lpszHeaders
0x1004757a1  mov     rcx, rax; hRequest
0x1004757a4  call    cs:__imp_HttpSendRequestW
0x1004757aa  test    eax, eax
0x1004757ac  jnz     short loc_1004757DC
0x1004757ae  call    cs:__imp_GetLastError
0x1004757b4  cmp     eax, 2F0Ch
0x1004757b9  jnz     loc_1004756DF
0x1004757bf  mov     [rsp+0F0h+dwFlags], esi; dwOptionalLength
0x1004757c3  xor     r9d, r9d; lpOptional
0x1004757c6  xor     r8d, r8d; dwHeadersLength
0x1004757c9  xor     edx, edx; lpszHeaders
0x1004757cb  mov     rcx, rbx; hRequest
0x1004757ce  call    cs:__imp_HttpSendRequestW
0x1004757d4  test    eax, eax
0x1004757d6  jz      loc_1004756DF
0x1004757dc  xor     r15d, r15d
0x1004757df  mov     [rbp+57h+dwNumberOfBytesRead], r15d
0x1004757e3  mov     r8, r14
0x1004757e6  mov     edi, 1000h
0x1004757eb  mov     edx, edi
0x1004757ed  mov     rcx, r14
0x1004757f0  call    ??$_Resize@V_lambda_2b51424039c320f102fd798e073c89b2_@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KV_lambda_2b51424039c320f102fd798e073c89b2_@@@Z; std::vector<uchar>::_Resize<_lambda_2b51424039c320f102fd798e073c89b2_>(unsigned __int64,_lambda_2b51424039c320f102fd798e073c89b2_)
0x1004757f5  mov     rdx, [r14]
0x1004757f8  jmp     short loc_100475819
0x1004757fa  mov     eax, [rbp+57h+dwNumberOfBytesRead]
0x1004757fd  test    eax, eax
0x1004757ff  jz      short loc_10047582D
0x100475801  add     esi, eax
0x100475803  lea     edx, [rsi+1000h]
0x100475809  mov     r8, r14
0x10047580c  mov     rcx, r14
0x10047580f  call    ??$_Resize@V_lambda_2b51424039c320f102fd798e073c89b2_@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KV_lambda_2b51424039c320f102fd798e073c89b2_@@@Z; std::vector<uchar>::_Resize<_lambda_2b51424039c320f102fd798e073c89b2_>(unsigned __int64,_lambda_2b51424039c320f102fd798e073c89b2_)
0x100475814  mov     edx, esi
0x100475816  add     rdx, [r14]; lpBuffer
0x100475819  lea     r9, [rbp+57h+dwNumberOfBytesRead]; lpdwNumberOfBytesRead
0x10047581d  mov     r8d, edi; dwNumberOfBytesToRead
0x100475820  mov     rcx, rbx; hFile
0x100475823  call    cs:__imp_InternetReadFile
0x100475829  test    eax, eax
0x10047582b  jnz     short loc_1004757FA
0x10047582d  mov     rcx, rbx; hInternet
0x100475830  call    cs:__imp_InternetCloseHandle
0x100475836  mov     [rbp+57h+var_B0], r15b
0x10047583a  lea     rdx, [rbp+57h+var_B0]
0x10047583e  mov     rcx, r14
0x100475841  call    ??$emplace_back@AEBE@?$vector@EV?$allocator@E@std@@@std@@QEAA?A_TAEBE@Z
0x100475846  mov     rcx, r13; hInternet
0x100475849  call    cs:__imp_InternetCloseHandle
0x10047584f  mov     rcx, [rbp+57h+hInternet]; hInternet
0x100475853  call    cs:__imp_InternetCloseHandle
0x100475859  nop
0x10047585a  mov     r15, 7FFFFFFFFFFFFFFFh
0x100475864  mov     rax, [rbp+57h+var_68]
0x100475868  cmp     rax, 8
0x10047586c  jb      loc_1004758F6
0x100475872  inc     rax
0x100475875  mov     rdx, [rbp+57h+lpszServerName]
0x100475879  mov     rcx, rdx
0x10047587c  cmp     rax, r15
0x10047587f  ja      short loc_1004758AE
0x100475881  add     rax, rax
0x100475884  cmp     rax, rdi
0x100475887  jb      short loc_1004758A4
0x100475889  test    cl, 1Fh
0x10047588c  jnz     short loc_1004758AE
0x10047588e  mov     rdx, [rdx-8]
0x100475892  cmp     rdx, rcx
0x100475895  jnb     short loc_1004758AE
0x100475897  sub     rcx, rdx
0x10047589a  sub     rcx, 8
0x10047589e  cmp     rcx, 1Fh
0x1004758a2  ja      short loc_1004758AE
0x1004758a4  mov     rcx, rdx; void *
0x1004758a7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1004758ac  jmp     short loc_1004758F6
0x1004758ae  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x1004758b5  mov     ecx, 2EE5h; dwErrCode
0x1004758ba  call    cs:__imp_SetLastError
0x1004758c0  call    cs:__imp_GetLastError
0x1004758c6  mov     ebx, eax
0x1004758c8  mov     rcx, [rbp+57h+hInternet]; hInternet
0x1004758cc  call    cs:__imp_InternetCloseHandle
0x1004758d2  xor     r13d, r13d
0x1004758d5  jmp     short loc_1004758DF
0x1004758d7  call    cs:__imp_GetLastError
0x1004758dd  mov     ebx, eax
0x1004758df  mov     r8d, ebx
0x1004758e2  mov     edx, 64h ; 'd'
0x1004758e7  mov     rcx, rsi
0x1004758ea  mov     rax, [rsi]
0x1004758ed  call    cs:__guard_dispatch_icall_fptr
0x1004758f3  mov     r12d, r13d
0x1004758f6  mov     rax, qword ptr [rbp+57h+var_50+8]
0x1004758fa  cmp     rax, 8
0x1004758fe  jb      short loc_100475937
0x100475900  inc     rax
0x100475903  mov     rcx, [rbp+57h+var_60]
0x100475907  mov     rdx, rcx
0x10047590a  cmp     rax, r15
0x10047590d  ja      short loc_100475961
0x10047590f  add     rax, rax
0x100475912  cmp     rax, rdi
0x100475915  jb      short loc_100475932
0x100475917  test    dl, 1Fh
0x10047591a  jnz     short loc_100475961
0x10047591c  mov     rcx, [rcx-8]; void *
0x100475920  cmp     rcx, rdx
0x100475923  jnb     short loc_100475961
0x100475925  sub     rdx, rcx
0x100475928  sub     rdx, 8
0x10047592c  cmp     rdx, 1Fh
0x100475930  ja      short loc_100475961
0x100475932  call    ??3@YAXPEAX@Z; operator delete(void *)
0x100475937  mov     eax, r12d
0x10047593a  mov     rcx, [rbp+57h+var_40]
0x10047593e  xor     rcx, rsp; StackCookie
0x100475941  call    __security_check_cookie
0x100475946  mov     rbx, [rsp+0F0h+arg_18]
0x10047594e  add     rsp, 0C0h
0x100475955  pop     r15
0x100475957  pop     r14
0x100475959  pop     r13
0x10047595b  pop     r12
0x10047595d  pop     rdi
0x10047595e  pop     rsi
0x10047595f  pop     rbp
0x100475960  retn
0x100475961  call    cs:__imp__invalid_parameter_noinfo_noreturn
```
