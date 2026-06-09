# sqlencrypt::AzureKeyVault::AKVRequest(aadauth::AzureADAuth const &,CEKeystoreContext *,void (*)(CEKeystoreContext *,ushort const *,...),char const *,std::basic_string<char,std::char_traits<char>,std::allocator<char>> &,std::basic_string<char,std::char_traits<char>,std::allocator<char>> *,bool)

- ea: `0x100470b78`
- end: `0x10047117e`
- name: `?AKVRequest@AzureKeyVault@sqlencrypt@@CAJAEBVAzureADAuth@aadauth@@PEAUCEKeystoreContext@@P6AX1PEBGZZPEBDAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAV67@_N@Z`
- size: `1542`
- prototype: `__int64 __fastcall(int, int, int, int, void *, __int64, char)`
- caller_count: `3`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x10046dab0`
- `0x10046edf0`
- `0x100470b78`

## callees

- `0x10040128c`
- `0x1004245f0`
- `0x100470b78`
- `0x100471184`
- `0x1004717c4`
- `0x1004837f0`
- `0x100486398`
- `0x1004886ac`
- `0x100546aa8`
- `0x10054814c`
- `0x100548210`
- `0x1005495d0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_strnicmp` at `0x100470eaf`
- `api-ms-win-crt-string-l1-1-0!_strnicmp` at `0x100470eaf`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1004710af`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x10047114d`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1004710af`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x10047114d`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100470d7e`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100470d7e`

## string_xrefs

- `0x100470e11`: `authorization_uri="`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall sqlencrypt::AzureKeyVault::AKVRequest(
        unsigned int *a1,
        struct CEKeystoreContext *a2,
        void (__fastcall *a3)(struct CEKeystoreContext *, __int64),
        __int64 a4,
        _QWORD *a5,
        __int64 a6,
        char a7)
{
  struct sqlencrypt::AzureKeyVault::ConfigData *Config; // rax
  struct sqlencrypt::AzureKeyVault::ConfigData *v12; // rdi
  char *v13; // rax
  unsigned int v14; // eax
  char **v15; // r9
  char *v16; // r12
  int v17; // ecx
  int v18; // ecx
  int v19; // ecx
  unsigned int v20; // ebx
  __int64 v21; // rdx
  int *v22; // rax
  sqlencrypt::utils **v23; // rax
  sqlencrypt::utils *v24; // rcx
  char **v25; // r9
  char *Value; // r15
  sqlencrypt::utils *v27; // rcx
  __int64 v28; // rax
  _QWORD *v29; // rcx
  struct sqlencrypt::AzureKeyVault::ConfigData *v30; // rdx
  unsigned int AccessToken; // r15d
  _BYTE *v32; // rbx
  _BYTE *v33; // rdx
  sqlencrypt::utils *v34; // rdx
  sqlencrypt::utils *v37[2]; // [rsp+80h] [rbp-51h] BYREF
  unsigned __int64 v38; // [rsp+90h] [rbp-41h]
  unsigned __int64 v39; // [rsp+98h] [rbp-39h]
  void *v40; // [rsp+A0h] [rbp-31h] BYREF
  __m128i si128; // [rsp+B0h] [rbp-21h]

  if ( (bidGblFlags & 2) != 0 && off_1005E6C50[0] )
    bidTraceW(0, 133120, off_1005E6C50[0], a1);
  Config = sqlencrypt::AzureKeyVault::GetConfig(a2);
  v12 = Config;
  v38 = 0;
  v39 = 15;
  LOBYTE(v37[0]) = 0;
  if ( *((_QWORD *)Config + 10) )
  {
    v13 = (char *)Config + 64;
    if ( *((_QWORD *)v13 + 3) >= 0x10u )
      v13 = *(char **)v13;
  }
  else
  {
    v13 = 0;
  }
  v14 = aadauth::AzureADAuth::Request(
          a1,
          (void (__fastcall *)(__int64, __int64, __int64, _QWORD *))a3,
          (__int64)a2,
          a4,
          v13,
          a5,
          a6,
          0,
          0,
          v37);
  if ( v14 != 401 || (v16 = 0, a7) || (*((_DWORD *)v12 + 37) & 0x10) != 0 || (v17 = *((_DWORD *)v12 + 37) & 0xF) == 0 )
  {
    v20 = v14;
  }
  else
  {
    v18 = v17 - 1;
    if ( v18 && (v19 = v18 - 1) != 0 )
    {
      if ( (unsigned int)(v19 - 3) >= 2 )
      {
LABEL_15:
        v20 = -1;
        if ( (bidGblFlags & 2) != 0 && off_1005E6C58[0] && bidID != -1 )
          ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD))off_1005D39E0)(
            bidID,
            0,
            166912,
            off_1005E6C58[0],
            0);
        v21 = 41355;
LABEL_20:
        a3(a2, v21);
        goto LABEL_82;
      }
    }
    else if ( !*((_QWORD *)v12 + 2) || !*((_QWORD *)v12 + 6) )
    {
      goto LABEL_15;
    }
    if ( v38 )
    {
      if ( v38 < 0x18 )
        goto LABEL_76;
      v23 = v37;
      if ( v39 >= 0x10 )
        v23 = (sqlencrypt::utils **)v37[0];
      if ( *(_DWORD *)v23 != 1918985538 || *((_WORD *)v23 + 2) != 29285 || *((_BYTE *)v23 + 6) != 32 )
      {
LABEL_76:
        v20 = -1;
        if ( (bidGblFlags & 2) != 0 && off_1005E6C68[0] && bidID != -1 )
          ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD))off_1005D39E0)(
            bidID,
            0,
            182272,
            off_1005E6C68[0],
            0);
        v21 = 41357;
        goto LABEL_20;
      }
      v24 = (sqlencrypt::utils *)v37;
      if ( v39 >= 0x10 )
        v24 = v37[0];
      Value = sqlencrypt::utils::ExtractValue(v24, "authorization=\"", 0, v15);
      v20 = -1;
      if ( !Value )
      {
        v27 = (sqlencrypt::utils *)v37;
        if ( v39 >= 0x10 )
          v27 = v37[0];
        Value = sqlencrypt::utils::ExtractValue(v27, "authorization_uri=\"", 0, v25);
        if ( !Value )
          goto LABEL_46;
      }
      v28 = -1;
      do
        ++v28;
      while ( Value[v28] );
      v16 = sqlencrypt::utils::ExtractValue((sqlencrypt::utils *)&Value[v28 + 1], "resource=\"", 0, v25);
      if ( !v16 )
      {
LABEL_46:
        if ( (bidGblFlags & 2) != 0 && off_1005E6C70[0] && bidID != -1 )
          ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, char *))off_1005D39E0)(
            bidID,
            0,
            194560,
            off_1005E6C70[0],
            v16);
        v21 = 41358;
        goto LABEL_20;
      }
      if ( _strnicmp(Value, "https://", 8u) )
      {
        if ( (bidGblFlags & 2) != 0 && off_1005E6C78[0] && bidID != -1 )
          ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD))off_1005D39E0)(
            bidID,
            0,
            201728,
            off_1005E6C78[0],
            0);
        v21 = 41359;
        goto LABEL_20;
      }
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOBYTE(v40) = 0;
      v29 = (_QWORD *)((char *)v12 + 32);
      if ( *((_QWORD *)v12 + 7) >= 0x10u )
        v29 = (_QWORD *)*v29;
      v30 = v12;
      if ( *((_QWORD *)v12 + 3) >= 0x10u )
        v30 = *(struct sqlencrypt::AzureKeyVault::ConfigData **)v12;
      AccessToken = aadauth::AzureADAuth::GetAccessToken(
                      (__int64)a1,
                      (void (__fastcall *)(__int64, __int64, __int64, _QWORD *))a3,
                      (__int64)a2,
                      *((_DWORD *)v12 + 37) & 0xF,
                      v30,
                      (__int64)v29,
                      Value,
                      (__int64)v16,
                      *((_DWORD *)v12 + 37) & 0x20,
                      a4,
                      (__int64)&v40,
                      0);
      if ( AccessToken )
      {
        if ( (bidGblFlags & 2) != 0 && off_1005E6C80[0] && bidID != -1 )
          ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD))off_1005D39E0)(
            bidID,
            0,
            215040,
            off_1005E6C80[0],
            0);
        ((void (__fastcall *)(struct CEKeystoreContext *, __int64, _QWORD))a3)(a2, 41360, AccessToken);
      }
      else
      {
        if ( *((_QWORD *)v12 + 11) < 0x16u )
        {
          _mm_lfence();
          std::string::_Reallocate_for<_lambda_66f57f934f28d61049862f64df852ff0_,char const *>(
            (char *)v12 + 64,
            22,
            0,
            "Authorization: Bearer ");
        }
        else
        {
          v32 = (_BYTE *)*((_QWORD *)v12 + 8);
          *((_QWORD *)v12 + 10) = 22;
          memmove_0(v32, "Authorization: Bearer ", 0x16u);
          v32[22] = 0;
        }
        std::string::append((char *)v12 + 64);
        v20 = sqlencrypt::AzureKeyVault::AKVRequest((int)a1, (int)a2, (int)a3, a4, a5, a6, 1);
      }
      if ( si128.m128i_i64[1] >= 0x10uLL )
      {
        v33 = v40;
        if ( (unsigned __int64)(si128.m128i_i64[1] + 1) >= 0x1000 )
        {
          if ( ((unsigned __int8)v40 & 0x1F) != 0
            || (v33 = (_BYTE *)*((_QWORD *)v40 - 1), v33 >= v40)
            || (unsigned __int64)((_BYTE *)v40 - v33 - 8) > 0x1F )
          {
            _invalid_parameter_noinfo_noreturn();
          }
        }
        operator delete(v33);
      }
    }
    else
    {
      v20 = -1;
      if ( (bidGblFlags & 2) != 0 && off_1005E6C60[0] && bidID != -1 )
        ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD))off_1005D39E0)(
          bidID,
          0,
          174080,
          off_1005E6C60[0],
          0);
      v22 = _errno();
      ((void (__fastcall *)(struct CEKeystoreContext *, __int64, _QWORD))a3)(a2, 41356, (unsigned int)*v22);
    }
  }
LABEL_82:
  if ( v39 >= 0x10 )
  {
    v34 = v37[0];
    if ( v39 + 1 >= 0x1000 )
    {
      if ( ((__int64)v37[0] & 0x1F) != 0
        || (v34 = (sqlencrypt::utils *)*((_QWORD *)v37[0] - 1), v34 >= v37[0])
        || (unsigned __int64)(v37[0] - v34 - 8) > 0x1F )
      {
        _invalid_parameter_noinfo_noreturn();
      }
    }
    operator delete(v34);
  }
  return v20;
}

```

## disassembly

```asm
0x100470b78  push    rbp
0x100470b7a  push    rbx
0x100470b7b  push    rsi
0x100470b7c  push    rdi
0x100470b7d  push    r12
0x100470b7f  push    r13
0x100470b81  push    r14
0x100470b83  push    r15
0x100470b85  lea     rbp, [rsp-7]
0x100470b8a  sub     rsp, 0D8h
0x100470b91  mov     [rbp+3Fh+var_98], 0FFFFFFFFFFFFFFFEh
0x100470b99  mov     rax, cs:__security_cookie
0x100470ba0  xor     rax, rsp
0x100470ba3  mov     [rbp+3Fh+var_50], rax
0x100470ba7  mov     r15, r9
0x100470baa  mov     qword ptr [rbp+3Fh+var_A8], r9
0x100470bae  mov     r14, r8
0x100470bb1  mov     rsi, rdx
0x100470bb4  mov     r13, rcx
0x100470bb7  mov     r12, [rbp+3Fh+arg_20]
0x100470bbb  mov     [rbp+3Fh+var_A0], r12
0x100470bbf  mov     rcx, [rbp+3Fh+arg_28]
0x100470bc3  mov     [rbp+3Fh+var_B0], rcx
0x100470bc7  movzx   ebx, [rbp+3Fh+arg_30]
0x100470bcb  test    byte ptr cs:_bidGblFlags, 2
0x100470bd2  jz      short loc_100470C13
0x100470bd4  mov     rax, cs:off_1005E6C50; "<sqlencrypt::AzureKeyVault::AKVRequest|"...
0x100470bdb  test    rax, rax
0x100470bde  jz      short loc_100470C13
0x100470be0  mov     dword ptr [rsp+110h+var_C8], ebx
0x100470be4  mov     qword ptr [rsp+110h+var_D0], rcx
0x100470be9  mov     [rsp+110h+var_D8], r12
0x100470bee  mov     qword ptr [rsp+110h+var_E0], r9
0x100470bf3  mov     [rsp+110h+var_E8], r8
0x100470bf8  mov     [rsp+110h+var_F0], rdx
0x100470bfd  mov     r9, r13
0x100470c00  mov     r8, cs:off_1005E6C50; "<sqlencrypt::AzureKeyVault::AKVRequest|"...
0x100470c07  mov     edx, 20800h
0x100470c0c  xor     ecx, ecx
0x100470c0e  call    _bidTraceW
0x100470c13  mov     rcx, rsi; struct CEKeystoreContext *
0x100470c16  call    ?GetConfig@AzureKeyVault@sqlencrypt@@CAAEAUConfigData@12@PEAUCEKeystoreContext@@@Z; sqlencrypt::AzureKeyVault::GetConfig(CEKeystoreContext *)
0x100470c1b  mov     rdi, rax
0x100470c1e  xor     edx, edx
0x100470c20  mov     [rbp+3Fh+var_80], rdx
0x100470c24  mov     [rbp+3Fh+var_78], 0Fh
0x100470c2c  mov     byte ptr [rbp+3Fh+var_90], dl
0x100470c2f  cmp     [rax+50h], rdx
0x100470c33  jnz     short loc_100470C39
0x100470c35  mov     eax, edx
0x100470c37  jmp     short loc_100470C47
0x100470c39  add     rax, 40h ; '@'
0x100470c3d  cmp     qword ptr [rax+18h], 10h
0x100470c42  jb      short loc_100470C47
0x100470c44  mov     rax, [rax]
0x100470c47  lea     rcx, [rbp+3Fh+var_90]
0x100470c4b  mov     [rsp+110h+var_C8], rcx; void *
0x100470c50  mov     [rsp+110h+var_D0], dl; char
0x100470c54  mov     [rsp+110h+var_D8], rdx; __int64
0x100470c59  mov     rcx, [rbp+3Fh+var_B0]
0x100470c5d  mov     qword ptr [rsp+110h+var_E0], rcx; __int64
0x100470c62  mov     [rsp+110h+var_E8], r12; void *
0x100470c67  mov     [rsp+110h+var_F0], rax; __int64
0x100470c6c  mov     r9, r15; int
0x100470c6f  mov     r8, rsi; int
0x100470c72  mov     rdx, r14; int
0x100470c75  mov     rcx, r13; int
0x100470c78  call    ?Request@AzureADAuth@aadauth@@QEBAJP6AXPEAUCEKeystoreContext@@PEBGZZPEAXPEBD4AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAV45@4D6@Z; aadauth::AzureADAuth::Request(void (*)(CEKeystoreContext *,ushort const *,...),void *,char const *,char const *,std::string &,std::string *,char const *,char,std::string *)
0x100470c7d  cmp     eax, 191h
0x100470c82  jnz     loc_100471114
0x100470c88  xor     r12d, r12d
0x100470c8b  test    bl, bl
0x100470c8d  jnz     loc_100471114
0x100470c93  mov     ecx, [rdi+94h]
0x100470c99  test    cl, 10h
0x100470c9c  jnz     loc_100471114
0x100470ca2  and     ecx, 0Fh
0x100470ca5  jz      loc_100471114
0x100470cab  sub     ecx, 1
0x100470cae  jz      short loc_100470D1F
0x100470cb0  sub     ecx, 1
0x100470cb3  jz      short loc_100470D1F
0x100470cb5  sub     ecx, 3
0x100470cb8  jz      short loc_100470D2B
0x100470cba  cmp     ecx, 1
0x100470cbd  jz      short loc_100470D2B
0x100470cbf  or      rbx, 0FFFFFFFFFFFFFFFFh
0x100470cc3  test    byte ptr cs:_bidGblFlags, 2
0x100470cca  jz      short loc_100470D09
0x100470ccc  mov     rax, cs:off_1005E6C58; "<sqlencrypt::AzureKeyVault::AKVRequest|"...
0x100470cd3  test    rax, rax
0x100470cd6  jz      short loc_100470D09
0x100470cd8  cmp     cs:_bidID, rbx
0x100470cdf  jz      short loc_100470D09
0x100470ce1  mov     rax, cs:off_1005D39E0
0x100470ce8  mov     [rsp+110h+var_F0], r12
0x100470ced  mov     r9, cs:off_1005E6C58; "<sqlencrypt::AzureKeyVault::AKVRequest|"...
0x100470cf4  xor     edx, edx
0x100470cf6  mov     r8d, 28C00h
0x100470cfc  mov     rcx, cs:_bidID
0x100470d03  call    cs:__guard_dispatch_icall_fptr
0x100470d09  mov     edx, 0A18Bh
0x100470d0e  mov     rcx, rsi
0x100470d11  mov     rax, r14
0x100470d14  call    cs:__guard_dispatch_icall_fptr
0x100470d1a  jmp     loc_100471116
0x100470d1f  cmp     [rdi+10h], r12
0x100470d23  jz      short loc_100470CBF
0x100470d25  cmp     [rdi+30h], r12
0x100470d29  jz      short loc_100470CBF
0x100470d2b  mov     rax, [rbp+3Fh+var_80]
0x100470d2f  test    rax, rax
0x100470d32  jnz     short loc_100470D9D
0x100470d34  or      rbx, 0FFFFFFFFFFFFFFFFh
0x100470d38  test    byte ptr cs:_bidGblFlags, 2
0x100470d3f  jz      short loc_100470D7E
0x100470d41  mov     rax, cs:off_1005E6C60; "<sqlencrypt::AzureKeyVault::AKVRequest|"...
0x100470d48  test    rax, rax
0x100470d4b  jz      short loc_100470D7E
0x100470d4d  cmp     cs:_bidID, rbx
0x100470d54  jz      short loc_100470D7E
0x100470d56  mov     rax, cs:off_1005D39E0
0x100470d5d  mov     [rsp+110h+var_F0], r12
0x100470d62  mov     r9, cs:off_1005E6C60; "<sqlencrypt::AzureKeyVault::AKVRequest|"...
0x100470d69  xor     edx, edx
0x100470d6b  mov     r8d, 2A800h
0x100470d71  mov     rcx, cs:_bidID
0x100470d78  call    cs:__guard_dispatch_icall_fptr
0x100470d7e  call    cs:__imp__errno
0x100470d84  mov     r8d, [rax]
0x100470d87  mov     edx, 0A18Ch
0x100470d8c  mov     rcx, rsi
0x100470d8f  mov     rax, r14
0x100470d92  call    cs:__guard_dispatch_icall_fptr
0x100470d98  jmp     loc_100471116
0x100470d9d  cmp     rax, 18h
0x100470da1  jb      loc_1004710C0
0x100470da7  lea     rax, [rbp+3Fh+var_90]
0x100470dab  cmp     [rbp+3Fh+var_78], 10h
0x100470db0  cmovnb  rax, [rbp+3Fh+var_90]
0x100470db5  cmp     dword ptr [rax], 72616542h
0x100470dbb  jnz     loc_1004710C0
0x100470dc1  cmp     word ptr [rax+4], 7265h
0x100470dc7  jnz     loc_1004710C0
0x100470dcd  cmp     byte ptr [rax+6], 20h ; ' '
0x100470dd1  jnz     loc_1004710C0
0x100470dd7  lea     rcx, [rbp+3Fh+var_90]
0x100470ddb  cmp     [rbp+3Fh+var_78], 10h
0x100470de0  cmovnb  rcx, [rbp+3Fh+var_90]; this
0x100470de5  xor     r8d, r8d; char *
0x100470de8  lea     rdx, aAuthorization; "authorization=\""
0x100470def  call    ?ExtractValue@utils@sqlencrypt@@YAPEADPEAD0PEAPEAD@Z; sqlencrypt::utils::ExtractValue(char *,char *,char * *)
0x100470df4  mov     r15, rax
0x100470df7  or      rbx, 0FFFFFFFFFFFFFFFFh
0x100470dfb  test    rax, rax
0x100470dfe  jnz     short loc_100470E25
0x100470e00  lea     rcx, [rbp+3Fh+var_90]
0x100470e04  cmp     [rbp+3Fh+var_78], 10h
0x100470e09  cmovnb  rcx, [rbp+3Fh+var_90]; this
0x100470e0e  xor     r8d, r8d; char *
0x100470e11  lea     rdx, aAuthorizationU; "authorization_uri=\""
0x100470e18  call    ?ExtractValue@utils@sqlencrypt@@YAPEADPEAD0PEAPEAD@Z; sqlencrypt::utils::ExtractValue(char *,char *,char * *)
0x100470e1d  mov     r15, rax
0x100470e20  test    rax, rax
0x100470e23  jz      short loc_100470E4F
0x100470e25  mov     rax, rbx
0x100470e28  inc     rax
0x100470e2b  cmp     [r15+rax], r12b
0x100470e2f  jnz     short loc_100470E28
0x100470e31  lea     rcx, [rax+1]
0x100470e35  add     rcx, r15; this
0x100470e38  xor     r8d, r8d; char *
0x100470e3b  lea     rdx, aResource_0; "resource=\""
0x100470e42  call    ?ExtractValue@utils@sqlencrypt@@YAPEADPEAD0PEAPEAD@Z; sqlencrypt::utils::ExtractValue(char *,char *,char * *)
0x100470e47  mov     r12, rax
0x100470e4a  test    rax, rax
0x100470e4d  jnz     short loc_100470E9F
0x100470e4f  test    byte ptr cs:_bidGblFlags, 2
0x100470e56  jz      short loc_100470E95
0x100470e58  mov     rax, cs:off_1005E6C70; "<sqlencrypt::AzureKeyVault::AKVRequest|"...
0x100470e5f  test    rax, rax
0x100470e62  jz      short loc_100470E95
0x100470e64  cmp     cs:_bidID, rbx
0x100470e6b  jz      short loc_100470E95
0x100470e6d  mov     rax, cs:off_1005D39E0
0x100470e74  mov     [rsp+110h+var_F0], r12
0x100470e79  mov     r9, cs:off_1005E6C70; "<sqlencrypt::AzureKeyVault::AKVRequest|"...
0x100470e80  xor     edx, edx
0x100470e82  mov     r8d, 2F800h
0x100470e88  mov     rcx, cs:_bidID
0x100470e8f  call    cs:__guard_dispatch_icall_fptr
0x100470e95  mov     edx, 0A18Eh
0x100470e9a  jmp     loc_100470D0E
0x100470e9f  mov     r8d, 8; MaxCount
0x100470ea5  lea     rdx, aHttps_0; "https://"
0x100470eac  mov     rcx, r15; String1
0x100470eaf  call    cs:__imp__strnicmp
0x100470eb5  xor     r8d, r8d
0x100470eb8  test    eax, eax
0x100470eba  jz      short loc_100470F0C
0x100470ebc  test    byte ptr cs:_bidGblFlags, 2
0x100470ec3  jz      short loc_100470F02
0x100470ec5  mov     rax, cs:off_1005E6C78; "<sqlencrypt::AzureKeyVault::AKVRequest|"...
0x100470ecc  test    rax, rax
0x100470ecf  jz      short loc_100470F02
0x100470ed1  cmp     cs:_bidID, rbx
0x100470ed8  jz      short loc_100470F02
0x100470eda  mov     rax, cs:off_1005D39E0
0x100470ee1  mov     [rsp+110h+var_F0], r8
0x100470ee6  mov     r9, cs:off_1005E6C78; "<sqlencrypt::AzureKeyVault::AKVRequest|"...
0x100470eed  xor     edx, edx
0x100470eef  mov     r8d, 31400h
0x100470ef5  mov     rcx, cs:_bidID
0x100470efc  call    cs:__guard_dispatch_icall_fptr
0x100470f02  mov     edx, 0A18Fh
0x100470f07  jmp     loc_100470D0E
0x100470f0c  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x100470f14  movdqu  [rbp+3Fh+var_60], xmm0
0x100470f19  mov     byte ptr [rbp+3Fh+var_70], r8b
0x100470f1d  lea     rcx, [rdi+20h]
0x100470f21  cmp     qword ptr [rcx+18h], 10h
0x100470f26  jb      short loc_100470F2B
0x100470f28  mov     rcx, [rcx]
0x100470f2b  mov     rdx, rdi
0x100470f2e  cmp     qword ptr [rdi+18h], 10h
0x100470f33  jb      short loc_100470F38
0x100470f35  mov     rdx, [rdi]
0x100470f38  mov     r9d, [rdi+94h]
0x100470f3f  mov     eax, r9d
0x100470f42  and     eax, 20h
0x100470f45  and     r9d, 0Fh
0x100470f49  mov     [rsp+110h+var_B8], r8
0x100470f4e  lea     r8, [rbp+3Fh+var_70]
0x100470f52  mov     [rsp+110h+var_C0], r8
0x100470f57  mov     r8, qword ptr [rbp+3Fh+var_A8]
0x100470f5b  mov     [rsp+110h+var_C8], r8
0x100470f60  mov     dword ptr [rsp+110h+var_D0], eax
0x100470f64  mov     [rsp+110h+var_D8], r12
0x100470f69  mov     qword ptr [rsp+110h+var_E0], r15
0x100470f6e  mov     [rsp+110h+var_E8], rcx
0x100470f73  mov     [rsp+110h+var_F0], rdx
0x100470f78  mov     r8, rsi
0x100470f7b  mov     rdx, r14
0x100470f7e  mov     rcx, r13
0x100470f81  call    ?GetAccessToken@AzureADAuth@aadauth@@QEBAJP6AXPEAUCEKeystoreContext@@PEBGZZPEAXHPEBD444K4AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEA_J@Z; aadauth::AzureADAuth::GetAccessToken(void (*)(CEKeystoreContext *,ushort const *,...),void *,int,char const *,char const *,char const *,char const *,ulong,char const *,std::string &,__int64 *)
0x100470f86  mov     r15d, eax
0x100470f89  test    eax, eax
0x100470f8b  jz      short loc_100470FED
0x100470f8d  test    byte ptr cs:_bidGblFlags, 2
0x100470f94  jz      short loc_100470FD4
0x100470f96  mov     rcx, cs:off_1005E6C80; "<sqlencrypt::AzureKeyVault::AKVRequest|"...
0x100470f9d  test    rcx, rcx
0x100470fa0  jz      short loc_100470FD4
0x100470fa2  cmp     cs:_bidID, rbx
0x100470fa9  jz      short loc_100470FD4
0x100470fab  mov     rax, cs:off_1005D39E0
0x100470fb2  and     [rsp+110h+var_F0], 0
0x100470fb8  mov     r9, cs:off_1005E6C80; "<sqlencrypt::AzureKeyVault::AKVRequest|"...
0x100470fbf  xor     edx, edx
0x100470fc1  mov     r8d, 34800h
0x100470fc7  mov     rcx, cs:_bidID
0x100470fce  call    cs:__guard_dispatch_icall_fptr
0x100470fd4  mov     r8d, r15d
0x100470fd7  mov     edx, 0A190h
0x100470fdc  mov     rcx, rsi
0x100470fdf  mov     rax, r14
0x100470fe2  call    cs:__guard_dispatch_icall_fptr
0x100470fe8  jmp     loc_100471074
0x100470fed  mov     edx, 16h
0x100470ff2  cmp     [rdi+58h], rdx
0x100470ff6  jb      short loc_100471018
0x100470ff8  mov     rbx, [rdi+40h]
0x100470ffc  mov     [rdi+50h], rdx
0x100471000  mov     r8d, edx; Size
0x100471003  lea     rdx, aAuthorizationB_0; "Authorization: Bearer "
0x10047100a  mov     rcx, rbx; void *
0x10047100d  call    memmove_0
0x100471012  mov     byte ptr [rbx+16h], 0
0x100471016  jmp     short loc_10047102E
0x100471018  lfence
0x10047101b  lea     r9, aAuthorizationB_0; "Authorization: Bearer "
0x100471022  xor     r8d, r8d
0x100471025  lea     rcx, [rdi+40h]
0x100471029  call    ??$_Reallocate_for@V_lambda_66f57f934f28d61049862f64df852ff0_@@PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@_KV_lambda_66f57f934f28d61049862f64df852ff0_@@PEBD@Z; std::string::_Reallocate_for<_lambda_66f57f934f28d61049862f64df852ff0_,char const *>(unsigned __int64,_lambda_66f57f934f28d61049862f64df852ff0_,char const *)
0x10047102e  lea     rdx, [rbp+3Fh+var_70]
0x100471032  cmp     qword ptr [rbp+3Fh+var_60+8], 10h
0x100471037  cmovnb  rdx, [rbp+3Fh+var_70]
0x10047103c  mov     r8, qword ptr [rbp+3Fh+var_60]
0x100471040  lea     rcx, [rdi+40h]; Src
0x100471044  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::append(char const * const,unsigned __int64)
0x100471049  mov     [rsp+110h+var_E0], 1; char
0x10047104e  mov     rax, [rbp+3Fh+var_B0]
0x100471052  mov     [rsp+110h+var_E8], rax; __int64
0x100471057  mov     rax, [rbp+3Fh+var_A0]
0x10047105b  mov     [rsp+110h+var_F0], rax; void *
0x100471060  mov     r9, qword ptr [rbp+3Fh+var_A8]; int
0x100471064  mov     r8, r14; int
0x100471067  mov     rdx, rsi; int
0x10047106a  mov     rcx, r13; int
0x10047106d  call    ?AKVRequest@AzureKeyVault@sqlencrypt@@CAJAEBVAzureADAuth@aadauth@@PEAUCEKeystoreContext@@P6AX1PEBGZZPEBDAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAV67@_N@Z; sqlencrypt::AzureKeyVault::AKVRequest(aadauth::AzureADAuth const &,CEKeystoreContext *,void (*)(CEKeystoreContext *,ushort const *,...),char const *,std::string &,std::string *,bool)
  ... truncated ...
```
