# Microsoft::HostGuardian::Client::Utilities::AppendBinaryToSystemPath(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>)

- ea: `0x18001486c`
- end: `0x180014c6d`
- name: `?AppendBinaryToSystemPath@Utilities@Client@HostGuardian@Microsoft@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V56@@Z`
- size: `1025`
- prototype: `wchar_t *__fastcall(wchar_t *Src, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x180013d28`

## callees

- `0x180001770`
- `0x180001794`
- `0x1800021f0`
- `0x180002aa0`
- `0x180002e55`
- `0x180003d0c`
- `0x180004274`
- `0x18000a7bc`
- `0x18001446c`
- `0x180014600`
- `0x18001477c`
- `0x1800147f8`
- `0x18001486c`
- `0x180014fdc`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001494d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180014a33`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001494d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180014a33`

## string_xrefs

- `0x180014c46`: `servercommon\base\securehostingservice\common\service\lib\utilities.cpp`
- `0x180014c5b`: `servercommon\base\securehostingservice\common\service\lib\utilities.cpp`

## pseudocode

```c
wchar_t *__fastcall Microsoft::HostGuardian::Client::Utilities::AppendBinaryToSystemPath(wchar_t *Src, __int64 a2)
{
  UINT SystemDirectoryW; // eax
  const char *v5; // r9
  UINT v6; // r14d
  WCHAR *v7; // rcx
  unsigned __int64 v8; // rdi
  size_t v9; // rdi
  const char *v10; // r9
  LPWSTR v11; // rdx
  unsigned __int64 v12; // r8
  __int64 v13; // rdi
  wchar_t *v14; // rsi
  __int64 v15; // rdi
  __int64 last_of_trivial_pos_2; // rdi
  const wchar_t *v17; // rcx
  size_t v18; // r8
  wchar_t *i; // rdi
  __int64 v20; // rdx
  wchar_t *v21; // rcx
  unsigned __int64 v22; // rdx
  char *v23; // r9
  __int64 v24; // rcx
  __int64 v25; // rsi
  wchar_t *v26; // rdi
  __int16 v28[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v29; // [rsp+34h] [rbp-CCh]
  LPWSTR lpBuffer[2]; // [rsp+38h] [rbp-C8h] BYREF
  LPWSTR v31; // [rsp+48h] [rbp-B8h]
  int v32; // [rsp+50h] [rbp-B0h]
  _QWORD v33[3]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v34[256]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v35; // [rsp+170h] [rbp+70h]
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  v33[1] = Src;
  v35 = a2;
  v32 = 0;
  v28[0] = 0;
  lpBuffer[0] = (LPWSTR)operator new(0x208u);
  v31 = lpBuffer[0] + 260;
  v29 = 0;
  memset_0(lpBuffer[0], 0, 0x208u);
  lpBuffer[1] = lpBuffer[0] + 260;
  v33[0] = 0;
  std::_Tidy_guard<std::vector<wchar_t>>::~_Tidy_guard<std::vector<wchar_t>>(v33);
  SystemDirectoryW = GetSystemDirectoryW(lpBuffer[0], 0x104u);
  v6 = SystemDirectoryW;
  if ( !SystemDirectoryW )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x53,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\utilities.cpp",
      v5);
  if ( SystemDirectoryW > 0x104 )
  {
    v28[0] = 0;
    v7 = lpBuffer[0];
    v8 = lpBuffer[1] - lpBuffer[0];
    if ( SystemDirectoryW >= v8 )
    {
      if ( SystemDirectoryW > v8 )
      {
        if ( SystemDirectoryW <= (unsigned __int64)(v31 - lpBuffer[0]) )
        {
          v29 = 0;
          v9 = 2 * (SystemDirectoryW - v8);
          memset_0(lpBuffer[1], 0, v9);
          v7 = lpBuffer[0];
          lpBuffer[1] = (LPWSTR)((char *)lpBuffer[1] + v9);
        }
        else
        {
          std::vector<wchar_t>::_Resize_reallocate<wchar_t>(lpBuffer, SystemDirectoryW, v28);
          v7 = lpBuffer[0];
        }
      }
    }
    else
    {
      lpBuffer[1] = &lpBuffer[0][SystemDirectoryW];
    }
    if ( !GetSystemDirectoryW(v7, v6) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x58,
        (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\utilities.cpp",
        v10);
  }
  v11 = lpBuffer[0];
  *(_OWORD *)Src = 0;
  *((_QWORD *)Src + 2) = 0;
  *((_QWORD *)Src + 3) = 0;
  v12 = -1;
  do
    ++v12;
  while ( v11[v12] );
  std::wstring::_Construct<1,wchar_t const *>(Src, v11, v12);
  v32 = 1;
  v13 = *((_QWORD *)Src + 2);
  if ( *((_QWORD *)Src + 3) <= 7u )
    v14 = Src;
  else
    v14 = *(wchar_t **)Src;
  if ( v13 )
  {
    v15 = v13 - 1;
    if ( v15 == -1 )
      v15 = -1;
    if ( (unsigned __int64)(v15 + 3) < 0x10 )
    {
      memset_0(v34, 0, sizeof(v34));
      v17 = L"\\/";
      v18 = 2;
      while ( *v17 < 0x100u )
      {
        v34[*(unsigned __int8 *)v17++] = 1;
        if ( v17 == L"" )
        {
          for ( i = &v14[v15]; *i >= 0x100u || !v34[*i]; --i )
          {
            if ( i == v14 )
              goto LABEL_40;
          }
          goto LABEL_32;
        }
      }
      for ( i = &v14[v15]; !wmemchr(L"\\/", *i, v18); i = (wchar_t *)((char *)i - v18) )
      {
        if ( i == v14 )
          goto LABEL_40;
      }
LABEL_32:
      last_of_trivial_pos_2 = i - v14;
    }
    else
    {
      last_of_trivial_pos_2 = _std_find_last_of_trivial_pos_2(v14, v15 + 1, L"\\/", 2);
    }
    if ( last_of_trivial_pos_2 != -1 )
    {
      v20 = *((_QWORD *)Src + 2);
      if ( *((_QWORD *)Src + 3) == v20 )
      {
        std::wstring::_Reallocate_grow_by<_lambda_942448a5eca1a40cdf35e7a483deabf2_,wchar_t const *,unsigned __int64>(
          Src,
          1);
      }
      else
      {
        *((_QWORD *)Src + 2) = v20 + 1;
        if ( *((_QWORD *)Src + 3) <= 7u )
          v21 = Src;
        else
          v21 = *(wchar_t **)Src;
        v21[v20] = asc_180019FE0[0];
        v21[v20 + 1] = 0;
      }
    }
  }
LABEL_40:
  v22 = *(_QWORD *)(a2 + 16);
  if ( *(_QWORD *)(a2 + 24) <= 7u )
    v23 = (char *)a2;
  else
    v23 = *(char **)a2;
  v24 = *((_QWORD *)Src + 2);
  if ( v22 > *((_QWORD *)Src + 3) - v24 )
  {
    std::wstring::_Reallocate_grow_by<_lambda_942448a5eca1a40cdf35e7a483deabf2_,wchar_t const *,unsigned __int64>(
      Src,
      *(_QWORD *)(a2 + 16));
  }
  else
  {
    v25 = v22 + v24;
    *((_QWORD *)Src + 2) = v22 + v24;
    if ( *((_QWORD *)Src + 3) <= 7u )
      v26 = Src;
    else
      v26 = *(wchar_t **)Src;
    memmove_0(&v26[v24], v23, 2 * v22);
    v26[v25] = 0;
  }
  std::vector<wchar_t>::~vector<wchar_t>(lpBuffer);
  std::wstring::~wstring((char **)a2);
  return Src;
}

```

## disassembly

```asm
0x18001486c  mov     [rsp-8+arg_10], rbx
0x180014871  push    rbp
0x180014872  push    rsi
0x180014873  push    rdi
0x180014874  push    r12
0x180014876  push    r13
0x180014878  push    r14
0x18001487a  push    r15
0x18001487c  lea     rbp, [rsp-80h]
0x180014881  sub     rsp, 180h
0x180014888  mov     rax, cs:__security_cookie
0x18001488f  xor     rax, rsp
0x180014892  mov     [rbp+0B0h+var_38], rax
0x180014896  mov     r15, rdx
0x180014899  mov     rbx, rcx
0x18001489c  mov     [rsp+1B0h+var_150], rcx
0x1800148a1  mov     [rbp+0B0h+var_40], rdx
0x1800148a5  xor     r12d, r12d
0x1800148a8  mov     [rsp+1B0h+var_160], r12d
0x1800148ad  mov     [rsp+1B0h+var_180], r12w
0x1800148b3  xorps   xmm0, xmm0
0x1800148b6  movdqu  xmmword ptr [rsp+1B0h+lpBuffer], xmm0
0x1800148bc  mov     [rsp+1B0h+var_168], r12
0x1800148c1  mov     r14d, 208h
0x1800148c7  mov     ecx, r14d; Size
0x1800148ca  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800148cf  mov     rcx, rax; void *
0x1800148d2  mov     [rsp+1B0h+lpBuffer], rax
0x1800148d7  lea     rsi, [rax+208h]
0x1800148de  mov     [rsp+1B0h+var_168], rsi
0x1800148e3  mov     [rsp+1B0h+var_17C], r12w
0x1800148e9  mov     al, byte ptr [rsp+1B0h+var_180+1]
0x1800148ed  cmp     al, byte ptr [rsp+1B0h+var_17C+1]
0x1800148f1  jnz     short loc_1800148F8
0x1800148f3  mov     eax, r12d
0x1800148f6  jmp     short loc_1800148FD
0x1800148f8  sbb     eax, eax
0x1800148fa  or      eax, 1
0x1800148fd  mov     r13d, 104h
0x180014903  test    eax, eax
0x180014905  jnz     short loc_180014913
0x180014907  mov     r8, r14; Size
0x18001490a  xor     edx, edx; Val
0x18001490c  call    memset_0
0x180014911  jmp     short loc_180014930
0x180014913  mov     rdx, r13
0x180014916  mov     rsi, rcx
0x180014919  movzx   eax, r12w
0x18001491d  mov     rdi, rcx
0x180014920  mov     rcx, r13
0x180014923  rep stosw
0x180014926  add     rsi, 2
0x18001492a  sub     rdx, 1
0x18001492e  jnz     short loc_180014926
0x180014930  mov     [rsp+1B0h+lpBuffer+8], rsi
0x180014935  mov     [rsp+1B0h+var_158], r12
0x18001493a  lea     rcx, [rsp+1B0h+var_158]
0x18001493f  call    ??1?$_Tidy_guard@V?$vector@_WV?$allocator@_W@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<wchar_t>>::~_Tidy_guard<std::vector<wchar_t>>(void)
0x180014944  nop
0x180014945  mov     edx, r13d; uSize
0x180014948  mov     rcx, [rsp+1B0h+lpBuffer]; lpBuffer
0x18001494d  call    cs:__imp_GetSystemDirectoryW
0x180014953  mov     r14d, eax
0x180014956  mov     rcx, [rbp+0B8h]; this
0x18001495d  test    eax, eax
0x18001495f  jz      loc_180014C5B
0x180014965  cmp     r14d, r13d
0x180014968  jbe     loc_180014A41
0x18001496e  mov     r8d, r12d
0x180014971  mov     [rsp+1B0h+var_180], r8w
0x180014977  mov     edx, r14d
0x18001497a  mov     rsi, [rsp+1B0h+lpBuffer+8]
0x18001497f  mov     rdi, rsi
0x180014982  mov     rcx, [rsp+1B0h+lpBuffer]
0x180014987  sub     rdi, rcx
0x18001498a  sar     rdi, 1
0x18001498d  cmp     r14, rdi
0x180014990  jnb     short loc_1800149A0
0x180014992  lea     rax, [rcx+r14*2]
0x180014996  mov     [rsp+1B0h+lpBuffer+8], rax
0x18001499b  jmp     loc_180014A29
0x1800149a0  jbe     loc_180014A29
0x1800149a6  mov     rax, [rsp+1B0h+var_168]
0x1800149ab  sub     rax, rcx
0x1800149ae  sar     rax, 1
0x1800149b1  cmp     rdx, rax
0x1800149b4  jbe     short loc_1800149CC
0x1800149b6  lea     r8, [rsp+1B0h+var_180]
0x1800149bb  lea     rcx, [rsp+1B0h+lpBuffer]
0x1800149c0  call    ??$_Resize_reallocate@_W@?$vector@_WV?$allocator@_W@std@@@std@@AEAAX_KAEB_W@Z; std::vector<wchar_t>::_Resize_reallocate<wchar_t>(unsigned __int64,wchar_t const &)
0x1800149c5  mov     rcx, [rsp+1B0h+lpBuffer]
0x1800149ca  jmp     short loc_180014A29
0x1800149cc  sub     rdx, rdi
0x1800149cf  mov     [rsp+1B0h+var_17C], r12w
0x1800149d5  mov     al, byte ptr [rsp+1B0h+var_180+1]
0x1800149d9  cmp     al, byte ptr [rsp+1B0h+var_17C+1]
0x1800149dd  jnz     short loc_1800149E4
0x1800149df  mov     eax, r12d
0x1800149e2  jmp     short loc_1800149E9
0x1800149e4  sbb     eax, eax
0x1800149e6  or      eax, 1
0x1800149e9  test    eax, eax
0x1800149eb  jnz     short loc_180014A03
0x1800149ed  lea     rdi, [rdx+rdx]
0x1800149f1  mov     r8, rdi; Size
0x1800149f4  xor     edx, edx; Val
0x1800149f6  mov     rcx, rsi; void *
0x1800149f9  call    memset_0
0x1800149fe  add     rsi, rdi
0x180014a01  jmp     short loc_180014A1F
0x180014a03  test    rdx, rdx
0x180014a06  jz      short loc_180014A24
0x180014a08  movzx   eax, r12w
0x180014a0c  mov     rdi, rsi
0x180014a0f  mov     rcx, rdx
0x180014a12  rep stosw
0x180014a15  add     rsi, 2
0x180014a19  sub     rdx, 1
0x180014a1d  jnz     short loc_180014A15
0x180014a1f  mov     rcx, [rsp+1B0h+lpBuffer]; lpBuffer
0x180014a24  mov     [rsp+1B0h+lpBuffer+8], rsi
0x180014a29  mov     rdi, [rbp+0B8h]
0x180014a30  mov     edx, r14d; uSize
0x180014a33  call    cs:__imp_GetSystemDirectoryW
0x180014a39  test    eax, eax
0x180014a3b  jz      loc_180014C46
0x180014a41  mov     rdx, [rsp+1B0h+lpBuffer]
0x180014a46  xorps   xmm0, xmm0
0x180014a49  movups  xmmword ptr [rbx], xmm0
0x180014a4c  mov     [rbx+10h], r12
0x180014a50  mov     [rbx+18h], r12
0x180014a54  or      r13, 0FFFFFFFFFFFFFFFFh
0x180014a58  mov     r8, r13
0x180014a5b  inc     r8
0x180014a5e  cmp     [rdx+r8*2], r12w
0x180014a63  jnz     short loc_180014A5B
0x180014a65  mov     rcx, rbx
0x180014a68  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180014a6d  mov     r14d, 1
0x180014a73  mov     [rsp+1B0h+var_160], r14d
0x180014a78  mov     rdi, [rbx+10h]
0x180014a7c  cmp     qword ptr [rbx+18h], 7
0x180014a81  jbe     short loc_180014A88
0x180014a83  mov     rsi, [rbx]
0x180014a86  jmp     short loc_180014A8B
0x180014a88  mov     rsi, rbx
0x180014a8b  test    rdi, rdi
0x180014a8e  jz      loc_180014BAA
0x180014a94  dec     rdi
0x180014a97  cmp     rdi, r13
0x180014a9a  cmovnb  rdi, r13
0x180014a9e  lea     rdx, [rdi+1]
0x180014aa2  lea     rax, [rdx+2]
0x180014aa6  cmp     rax, 10h
0x180014aaa  jb      short loc_180014AC9
0x180014aac  mov     r9d, 2
0x180014ab2  lea     r8, S; "\\/"
0x180014ab9  mov     rcx, rsi
0x180014abc  call    __std_find_last_of_trivial_pos_2
0x180014ac1  mov     rdi, rax
0x180014ac4  jmp     loc_180014B56
0x180014ac9  mov     r13d, 100h
0x180014acf  mov     r8d, r13d; Size
0x180014ad2  xor     edx, edx; Val
0x180014ad4  lea     rcx, [rsp+1B0h+var_140]; void *
0x180014ad9  call    memset_0
0x180014ade  lea     rcx, S; "\\/"
0x180014ae5  mov     r8d, 2; N
0x180014aeb  cmp     [rcx], r13w
0x180014aef  jnb     short loc_180014B2A
0x180014af1  movzx   eax, byte ptr [rcx]
0x180014af4  mov     [rsp+rax+1B0h+var_140], r14b
0x180014af9  add     rcx, r8
0x180014afc  lea     rax, S+4; ""
0x180014b03  cmp     rcx, rax
0x180014b06  jnz     short loc_180014AEB
0x180014b08  lea     rdi, [rsi+rdi*2]
0x180014b0c  cmp     [rdi], r13w
0x180014b10  jnb     short loc_180014B1C
0x180014b12  movzx   eax, word ptr [rdi]
0x180014b15  cmp     [rsp+rax+1B0h+var_140], r12b
0x180014b1a  jnz     short loc_180014B4C
0x180014b1c  cmp     rdi, rsi
0x180014b1f  jz      loc_180014BAA
0x180014b25  sub     rdi, r8
0x180014b28  jmp     short loc_180014B0C
0x180014b2a  lea     rdi, [rsi+rdi*2]
0x180014b2e  movzx   edx, word ptr [rdi]; C
0x180014b31  lea     rcx, S; "\\/"
0x180014b38  call    wmemchr
0x180014b3d  test    rax, rax
0x180014b40  jnz     short loc_180014B4C
0x180014b42  cmp     rdi, rsi
0x180014b45  jz      short loc_180014BAA
0x180014b47  sub     rdi, r8
0x180014b4a  jmp     short loc_180014B2E
0x180014b4c  sub     rdi, rsi
0x180014b4f  sar     rdi, 1
0x180014b52  or      r13, 0FFFFFFFFFFFFFFFFh
0x180014b56  cmp     rdi, r13
0x180014b59  jz      short loc_180014BAA
0x180014b5b  mov     rdx, [rbx+10h]
0x180014b5f  mov     rax, [rbx+18h]
0x180014b63  sub     rax, rdx
0x180014b66  cmp     rax, r14
0x180014b69  jb      short loc_180014B93
0x180014b6b  lea     rdi, [rdx+1]
0x180014b6f  mov     [rbx+10h], rdi
0x180014b73  cmp     qword ptr [rbx+18h], 7
0x180014b78  jbe     short loc_180014B7F
0x180014b7a  mov     rcx, [rbx]
0x180014b7d  jmp     short loc_180014B82
0x180014b7f  mov     rcx, rbx
0x180014b82  mov     eax, dword ptr cs:asc_180019FE0; "\\"
0x180014b88  mov     [rcx+rdx*2], ax
0x180014b8c  mov     [rcx+rdi*2], r12w
0x180014b91  jmp     short loc_180014BAA
0x180014b93  mov     [rsp+1B0h+var_190], r14; __int64
0x180014b98  lea     r9, asc_180019FE0; "\\"
0x180014b9f  mov     rdx, r14
0x180014ba2  mov     rcx, rbx; Src
0x180014ba5  call    ??$_Reallocate_grow_by@V_lambda_942448a5eca1a40cdf35e7a483deabf2_@@PEB_W_K@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_942448a5eca1a40cdf35e7a483deabf2_@@PEB_W_K@Z; std::wstring::_Reallocate_grow_by<_lambda_942448a5eca1a40cdf35e7a483deabf2_,wchar_t const *,unsigned __int64>(unsigned __int64,_lambda_942448a5eca1a40cdf35e7a483deabf2_,wchar_t const *,unsigned __int64)
0x180014baa  mov     rdx, [r15+10h]
0x180014bae  cmp     qword ptr [r15+18h], 7
0x180014bb3  jbe     short loc_180014BBA
0x180014bb5  mov     r9, [r15]
0x180014bb8  jmp     short loc_180014BBD
0x180014bba  mov     r9, r15
0x180014bbd  mov     rcx, [rbx+10h]
0x180014bc1  mov     rax, [rbx+18h]
0x180014bc5  sub     rax, rcx
0x180014bc8  cmp     rdx, rax
0x180014bcb  ja      short loc_180014BFB
0x180014bcd  lea     rsi, [rdx+rcx]
0x180014bd1  mov     [rbx+10h], rsi
0x180014bd5  cmp     qword ptr [rbx+18h], 7
0x180014bda  jbe     short loc_180014BE1
0x180014bdc  mov     rdi, [rbx]
0x180014bdf  jmp     short loc_180014BE4
0x180014be1  mov     rdi, rbx
0x180014be4  lea     r8, [rdx+rdx]; Size
0x180014be8  lea     rcx, [rdi+rcx*2]; void *
0x180014bec  mov     rdx, r9; Src
0x180014bef  call    memmove_0
0x180014bf4  mov     [rdi+rsi*2], r12w
0x180014bf9  jmp     short loc_180014C09
0x180014bfb  mov     [rsp+1B0h+var_190], rdx; __int64
0x180014c00  mov     rcx, rbx; Src
0x180014c03  call    ??$_Reallocate_grow_by@V_lambda_942448a5eca1a40cdf35e7a483deabf2_@@PEB_W_K@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_942448a5eca1a40cdf35e7a483deabf2_@@PEB_W_K@Z; std::wstring::_Reallocate_grow_by<_lambda_942448a5eca1a40cdf35e7a483deabf2_,wchar_t const *,unsigned __int64>(unsigned __int64,_lambda_942448a5eca1a40cdf35e7a483deabf2_,wchar_t const *,unsigned __int64)
0x180014c08  nop
0x180014c09  lea     rcx, [rsp+1B0h+lpBuffer]
0x180014c0e  call    ??1?$vector@_WV?$allocator@_W@std@@@std@@QEAA@XZ; std::vector<wchar_t>::~vector<wchar_t>(void)
0x180014c13  nop
0x180014c14  mov     rcx, r15
0x180014c17  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180014c1c  mov     rax, rbx
0x180014c1f  mov     rcx, [rbp+0B0h+var_38]
0x180014c23  xor     rcx, rsp; StackCookie
0x180014c26  call    __security_check_cookie
0x180014c2b  mov     rbx, [rsp+1B0h+arg_10]
0x180014c33  add     rsp, 180h
0x180014c3a  pop     r15
0x180014c3c  pop     r14
0x180014c3e  pop     r13
0x180014c40  pop     r12
0x180014c42  pop     rdi
0x180014c43  pop     rsi
0x180014c44  pop     rbp
0x180014c45  retn
0x180014c46  lea     r8, aServercommonBa_2; "servercommon\\base\\securehostingservic"...
0x180014c4d  mov     edx, 58h ; 'X'; void *
0x180014c52  mov     rcx, rdi; this
0x180014c55  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180014c5b  lea     r8, aServercommonBa_2; "servercommon\\base\\securehostingservic"...
0x180014c62  mov     edx, 53h ; 'S'; void *
0x180014c67  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
