# helium::CreateLookasideRegistryValue(HKEY__ *,DESKTOP_APPX_REGKEYANDVALUE const &,TokenMap &)

- ea: `0x180013bec`
- end: `0x180013e5d`
- name: `?CreateLookasideRegistryValue@helium@@YAXPEAUHKEY__@@AEBUDESKTOP_APPX_REGKEYANDVALUE@@AEAVTokenMap@@@Z`
- size: `625`
- prototype: `void __fastcall(helium *__hidden this, HKEY, const struct DESKTOP_APPX_REGKEYANDVALUE *, struct TokenMap *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800137e8`

## callees

- `0x180004f70`
- `0x18000b132`
- `0x180012fb8`
- `0x1800130e4`
- `0x180013510`
- `0x180013bec`
- `0x180014dbc`
- `0x180050fc0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180013d8c`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180013d8c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180013d0f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180013d41`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180013d73`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180013d0f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180013d41`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180013d73`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall helium::CreateLookasideRegistryValue(
        helium *this,
        _QWORD *a2,
        const struct DESKTOP_APPX_REGKEYANDVALUE *a3,
        struct TokenMap *a4)
{
  _WORD *v7; // r9
  __int64 v8; // rdi
  unsigned __int64 v9; // rdx
  __int64 v10; // rbx
  const WCHAR *v11; // rsi
  __int64 v12; // r9
  DWORD v13; // ebx
  __int64 v14; // r9
  __int64 v15; // rdx
  WCHAR *v16; // r9
  BYTE v17[8]; // [rsp+30h] [rbp-59h] BYREF
  WCHAR v18[16]; // [rsp+38h] [rbp-51h] BYREF
  __int128 v19; // [rsp+58h] [rbp-31h] BYREF
  unsigned __int64 v20; // [rsp+68h] [rbp-21h]
  __int64 v21; // [rsp+70h] [rbp-19h]
  WCHAR String1[8]; // [rsp+78h] [rbp-11h] BYREF
  WCHAR v23[12]; // [rsp+88h] [rbp-1h] BYREF

  v19 = 0;
  v20 = 0;
  v21 = 7;
  LOWORD(v19) = 0;
  v7 = (_WORD *)a2[1];
  v8 = -1;
  if ( v7 )
  {
    v9 = -1;
    do
      ++v9;
    while ( v7[v9] );
    if ( v9 > 7 )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(&v19, v9, a3, v7);
    }
    else
    {
      v20 = v9;
      v10 = 2 * v9;
      memmove_0(&v19, v7, 2 * v9);
      *(_WORD *)((char *)&v19 + v10) = 0;
    }
    TokenMap::DetokenizeString(a3, &v19, 0);
  }
  v11 = (const WCHAR *)a2[3];
  wcscpy(String1, L"REG_SZ");
  wcscpy(v18, L"REG_PAND_SZ");
  wcscpy(v23, L"REG_DWORD");
  if ( !v11 || !*v11 )
  {
    v13 = 1;
LABEL_21:
    v15 = a2[2];
    memset(v18, 0, sizeof(v18));
    do
      ++v8;
    while ( *(_WORD *)(v15 + 2 * v8) );
    std::wstring::_Construct<1,unsigned short const *>(v18, v15, v8);
    TokenMap::DetokenizeString(a3, v18, 0);
    v16 = v18;
    if ( *(_QWORD *)&v18[12] > 7u )
      v16 = *(WCHAR **)v18;
    helium::SetLookasideRegistryValue(
      (HKEY)this,
      (const WCHAR *)&v19,
      v13,
      (const BYTE *)v16,
      2 * *(_DWORD *)&v18[8] + 2);
    std::wstring::~wstring(v18);
    goto LABEL_26;
  }
  v12 = -1;
  do
    ++v12;
  while ( v11[v12] );
  v13 = 1;
  if ( CompareStringOrdinal(String1, 6, v11, v12, 1) == 2 )
    goto LABEL_21;
  v14 = -1;
  do
    ++v14;
  while ( v11[v14] );
  if ( CompareStringOrdinal(v18, 13, v11, v14, 1) == 2 )
  {
    v13 = 2;
    goto LABEL_21;
  }
  do
    ++v8;
  while ( v11[v8] );
  if ( CompareStringOrdinal(v23, 9, v11, v8, 1) == 2 )
  {
    *(_DWORD *)v17 = _o__wtoi(a2[2]);
    helium::SetLookasideRegistryValue((HKEY)this, (const WCHAR *)&v19, 4u, v17, 4u);
  }
LABEL_26:
  std::wstring::~wstring(&v19);
}

```

## disassembly

```asm
0x180013bec  mov     [rsp-8+arg_18], rbx
0x180013bf1  push    rbp
0x180013bf2  push    rsi
0x180013bf3  push    rdi
0x180013bf4  push    r12
0x180013bf6  push    r13
0x180013bf8  push    r14
0x180013bfa  push    r15
0x180013bfc  lea     rbp, [rsp-27h]
0x180013c01  sub     rsp, 0B0h
0x180013c08  mov     rax, cs:__security_cookie
0x180013c0f  xor     rax, rsp
0x180013c12  mov     [rbp+57h+var_40], rax
0x180013c16  mov     r15, r8
0x180013c19  mov     r14, rdx
0x180013c1c  mov     r12, rcx
0x180013c1f  xorps   xmm0, xmm0
0x180013c22  movups  [rbp+57h+var_88], xmm0
0x180013c26  xor     r13d, r13d
0x180013c29  mov     [rbp+57h+var_78], r13
0x180013c2d  mov     [rbp+57h+var_70], 7
0x180013c35  mov     word ptr [rbp+57h+var_88], r13w
0x180013c3a  mov     r9, [rdx+8]
0x180013c3e  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180013c42  test    r9, r9
0x180013c45  jz      short loc_180013C8D
0x180013c47  mov     rdx, rdi
0x180013c4a  inc     rdx
0x180013c4d  cmp     [r9+rdx*2], r13w
0x180013c52  jnz     short loc_180013C4A
0x180013c54  lea     rcx, [rbp+57h+var_88]; void *
0x180013c58  cmp     rdx, 7
0x180013c5c  ja      short loc_180013C79
0x180013c5e  mov     [rbp+57h+var_78], rdx
0x180013c62  lea     rbx, [rdx+rdx]
0x180013c66  mov     r8, rbx; Size
0x180013c69  mov     rdx, r9; Src
0x180013c6c  call    memmove_0
0x180013c71  mov     word ptr [rbp+rbx+57h+var_88], r13w
0x180013c77  jmp     short loc_180013C7E
0x180013c79  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180013c7e  xor     r8d, r8d
0x180013c81  lea     rdx, [rbp+57h+var_88]
0x180013c85  mov     rcx, r15
0x180013c88  call    ?DetokenizeString@TokenMap@@QEBAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; TokenMap::DetokenizeString(std::wstring &,bool)
0x180013c8d  mov     rsi, [r14+18h]
0x180013c91  movsd   xmm0, qword ptr cs:aRegSz; "REG_SZ"
0x180013c99  movsd   qword ptr [rbp+57h+String1], xmm0
0x180013c9e  mov     eax, dword ptr cs:aRegSz+8; "SZ"
0x180013ca4  mov     [rbp+57h+var_60], eax
0x180013ca7  movzx   eax, word ptr cs:aRegSz+0Ch; ""
0x180013cae  mov     [rbp+57h+var_5C], ax
0x180013cb2  movups  xmm0, xmmword ptr cs:aRegExpandSz; "REG_EXPAND_SZ"
0x180013cb9  movups  xmmword ptr [rbp+57h+var_A8], xmm0
0x180013cbd  movups  xmm1, xmmword ptr cs:aRegExpandSz+0Ch; "PAND_SZ"
0x180013cc4  movups  xmmword ptr [rbp+57h+var_A8+0Ch], xmm1
0x180013cc8  movups  xmm0, xmmword ptr cs:aRegDword; "REG_DWORD"
0x180013ccf  movups  xmmword ptr [rbp+57h+var_58], xmm0
0x180013cd3  mov     eax, dword ptr cs:aRegDword+10h; "D"
0x180013cd9  mov     [rbp+57h+var_48], eax
0x180013cdc  test    rsi, rsi
0x180013cdf  jz      loc_180013DB8
0x180013ce5  cmp     [rsi], r13w
0x180013ce9  jz      loc_180013DB8
0x180013cef  mov     r9, rdi
0x180013cf2  inc     r9; cchCount2
0x180013cf5  cmp     [rsi+r9*2], r13w
0x180013cfa  jnz     short loc_180013CF2
0x180013cfc  mov     ebx, 1
0x180013d01  mov     [rsp+0E0h+bIgnoreCase], ebx; bIgnoreCase
0x180013d05  mov     r8, rsi; lpString2
0x180013d08  lea     edx, [rbx+5]; cchCount1
0x180013d0b  lea     rcx, [rbp+57h+String1]; lpString1
0x180013d0f  call    cs:__imp_CompareStringOrdinal
0x180013d16  nop     dword ptr [rax+rax+00h]
0x180013d1b  cmp     eax, 2
0x180013d1e  jz      loc_180013DBD
0x180013d24  mov     r9, rdi
0x180013d27  inc     r9; cchCount2
0x180013d2a  cmp     [rsi+r9*2], r13w
0x180013d2f  jnz     short loc_180013D27
0x180013d31  mov     [rsp+0E0h+bIgnoreCase], ebx; bIgnoreCase
0x180013d35  mov     r8, rsi; lpString2
0x180013d38  mov     edx, 0Dh; cchCount1
0x180013d3d  lea     rcx, [rbp+57h+var_A8]; lpString1
0x180013d41  call    cs:__imp_CompareStringOrdinal
0x180013d48  nop     dword ptr [rax+rax+00h]
0x180013d4d  cmp     eax, 2
0x180013d50  jnz     short loc_180013D56
0x180013d52  mov     ebx, eax
0x180013d54  jmp     short loc_180013DBD
0x180013d56  inc     rdi
0x180013d59  cmp     [rsi+rdi*2], r13w
0x180013d5e  jnz     short loc_180013D56
0x180013d60  mov     [rsp+0E0h+bIgnoreCase], ebx; bIgnoreCase
0x180013d64  mov     r9d, edi; cchCount2
0x180013d67  mov     r8, rsi; lpString2
0x180013d6a  mov     edx, 9; cchCount1
0x180013d6f  lea     rcx, [rbp+57h+var_58]; lpString1
0x180013d73  call    cs:__imp_CompareStringOrdinal
0x180013d7a  nop     dword ptr [rax+rax+00h]
0x180013d7f  cmp     eax, 2
0x180013d82  jnz     loc_180013E2C
0x180013d88  mov     rcx, [r14+10h]
0x180013d8c  call    cs:__imp__o__wtoi
0x180013d93  nop     dword ptr [rax+rax+00h]
0x180013d98  mov     dword ptr [rbp+57h+var_B0], eax
0x180013d9b  mov     r8d, 4
0x180013da1  mov     [rsp+0E0h+bIgnoreCase], r8d
0x180013da6  lea     r9, [rbp+57h+var_B0]
0x180013daa  lea     rdx, [rbp+57h+var_88]
0x180013dae  mov     rcx, r12
0x180013db1  call    ?SetLookasideRegistryValue@helium@@YAXPEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KPEBEK@Z; helium::SetLookasideRegistryValue(HKEY__ *,std::wstring const &,ulong,uchar const *,ulong)
0x180013db6  jmp     short loc_180013E2C
0x180013db8  mov     ebx, 1
0x180013dbd  mov     rdx, [r14+10h]
0x180013dc1  xorps   xmm0, xmm0
0x180013dc4  movups  xmmword ptr [rbp+57h+var_A8], xmm0
0x180013dc8  xorps   xmm1, xmm1
0x180013dcb  movdqu  [rbp+57h+var_98], xmm1
0x180013dd0  inc     rdi
0x180013dd3  cmp     [rdx+rdi*2], r13w
0x180013dd8  jnz     short loc_180013DD0
0x180013dda  mov     r8, rdi
0x180013ddd  lea     rcx, [rbp+57h+var_A8]
0x180013de1  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180013de6  nop
0x180013de7  xor     r8d, r8d
0x180013dea  lea     rdx, [rbp+57h+var_A8]
0x180013dee  mov     rcx, r15
0x180013df1  call    ?DetokenizeString@TokenMap@@QEBAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; TokenMap::DetokenizeString(std::wstring &,bool)
0x180013df6  lea     r9, [rbp+57h+var_A8]
0x180013dfa  cmp     qword ptr [rbp+57h+var_98+8], 7
0x180013dff  cmova   r9, qword ptr [rbp+57h+var_A8]
0x180013e04  mov     eax, dword ptr [rbp+57h+var_98]
0x180013e07  lea     eax, ds:2[rax*2]
0x180013e0e  mov     [rsp+0E0h+bIgnoreCase], eax
0x180013e12  mov     r8d, ebx
0x180013e15  lea     rdx, [rbp+57h+var_88]
0x180013e19  mov     rcx, r12
0x180013e1c  call    ?SetLookasideRegistryValue@helium@@YAXPEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KPEBEK@Z; helium::SetLookasideRegistryValue(HKEY__ *,std::wstring const &,ulong,uchar const *,ulong)
0x180013e21  nop
0x180013e22  lea     rcx, [rbp+57h+var_A8]; void *
0x180013e26  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180013e2b  nop
0x180013e2c  lea     rcx, [rbp+57h+var_88]; void *
0x180013e30  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180013e35  mov     rcx, [rbp+57h+var_40]
0x180013e39  xor     rcx, rsp; StackCookie
0x180013e3c  call    __security_check_cookie
0x180013e41  mov     rbx, [rsp+0E0h+arg_18]
0x180013e49  add     rsp, 0B0h
0x180013e50  pop     r15
0x180013e52  pop     r14
0x180013e54  pop     r13
0x180013e56  pop     r12
0x180013e58  pop     rdi
0x180013e59  pop     rsi
0x180013e5a  pop     rbp
0x180013e5b  retn
```
