# KeyValueComparison::NumericCompareWithRange(ushort const *)

- ea: `0x180025660`
- end: `0x180025998`
- name: `?NumericCompareWithRange@KeyValueComparison@@AEBA_NPEBG@Z`
- size: `824`
- prototype: `bool __fastcall(KeyValueComparison *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180021cf4`
- `0x180023900`
- `0x180024348`
- `0x180024a20`
- `0x180024f58`
- `0x180025660`
- `0x18002cdf4`
- `0x180043500`
- `0x180043750`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800257ad`
- `msvcrt!??3@YAXPEAX@Z` at `0x180025815`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800258ea`
- `msvcrt!??3@YAXPEAX@Z` at `0x180025924`
- `msvcrt!??3@YAXPEAX@Z` at `0x180025955`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800257ad`
- `msvcrt!??3@YAXPEAX@Z` at `0x180025815`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800258ea`
- `msvcrt!??3@YAXPEAX@Z` at `0x180025924`
- `msvcrt!??3@YAXPEAX@Z` at `0x180025955`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
bool __fastcall KeyValueComparison::NumericCompareWithRange(KeyValueComparison *this, const unsigned __int16 *a2)
{
  _QWORD *v4; // rcx
  __int64 v5; // rsi
  __int64 v6; // rax
  __int64 v7; // r15
  unsigned __int64 v8; // rbx
  bool v9; // r14
  _QWORD *v10; // rcx
  __int64 v11; // r12
  _QWORD *v12; // rcx
  __int64 v13; // r15
  void *v14; // rbx
  void *v15; // rcx
  __int64 v16; // rbx
  bool result; // al
  int v18; // [rsp+20h] [rbp-128h]
  _BYTE v19[16]; // [rsp+30h] [rbp-118h] BYREF
  __int128 v20; // [rsp+40h] [rbp-108h]
  __int128 v21; // [rsp+50h] [rbp-F8h]
  __int64 v22; // [rsp+60h] [rbp-E8h]
  char v23; // [rsp+68h] [rbp-E0h]
  __int128 v24; // [rsp+70h] [rbp-D8h]
  char v25; // [rsp+80h] [rbp-C8h]
  _QWORD v26[2]; // [rsp+88h] [rbp-C0h] BYREF
  char v27; // [rsp+98h] [rbp-B0h]
  _BYTE v28[32]; // [rsp+A0h] [rbp-A8h] BYREF
  _BYTE v29[32]; // [rsp+C0h] [rbp-88h] BYREF
  wchar_t String[4]; // [rsp+E0h] [rbp-68h] BYREF
  unsigned __int64 v31; // [rsp+F8h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+0h]

  v19[8] = 0;
  v20 = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v26[0] = 0;
  v26[1] = 0;
  v27 = 0;
  std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::basic_regex<unsigned short,std::regex_traits<unsigned short>>(
    v29,
    L"^(-?\\d{1,19})(\\d|F)?,\\s?(-?\\d{1,19})(\\d|F)?$");
  v4 = (_QWORD *)((char *)this + 48);
  if ( *((_QWORD *)this + 9) >= 8u )
    v4 = (_QWORD *)*v4;
  v5 = -1;
  if ( *(_WORD *)v4 )
  {
    v6 = -1;
    do
      ++v6;
    while ( *((_WORD *)v4 + v6) );
  }
  else
  {
    LODWORD(v6) = 0;
  }
  if ( !(unsigned __int8)std::_Regex_match<unsigned short const *,std::allocator<std::sub_match<unsigned short const *>>,unsigned short,std::regex_traits<unsigned short>,unsigned short const *>(
                           (_DWORD)v4,
                           (int)v4 + 2 * (int)v6,
                           (unsigned int)v19,
                           (unsigned int)v29,
                           0) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x29,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\keys.cpp",
      (const char *)0x80070057LL,
      v18);
  v7 = v20;
  v8 = 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)&v20 + 1) - v20) >> 3);
  if ( v8 != 5 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v9 = 1;
  v10 = v26;
  if ( v8 > 1 )
    v10 = (_QWORD *)(v7 + 24);
  std::sub_match<unsigned short const *>::operator std::wstring(v10, String);
  v11 = std::stoll(String);
  if ( v31 >= 8 )
    operator delete(*(void **)String);
  v12 = v26;
  if ( 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)&v20 + 1) - v20) >> 3) > 3 )
    v12 = (_QWORD *)(v20 + 72);
  std::sub_match<unsigned short const *>::operator std::wstring(v12, String);
  v13 = std::stoll(String);
  if ( v31 >= 8 )
    operator delete(*(void **)String);
  if ( v13 <= v11 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::basic_regex<unsigned short,std::regex_traits<unsigned short>>(
    v28,
    L"^(-?\\d{1,19})(\\d|F)?$");
  if ( *a2 )
  {
    do
      ++v5;
    while ( a2[v5] );
  }
  else
  {
    LODWORD(v5) = 0;
  }
  std::_Regex_match<unsigned short const *,std::allocator<std::sub_match<unsigned short const *>>,unsigned short,std::regex_traits<unsigned short>,unsigned short const *>(
    (_DWORD)a2,
    (_DWORD)a2 + 2 * v5,
    (unsigned int)v19,
    (unsigned int)v28,
    0);
  v14 = (void *)v20;
  if ( *((_QWORD *)&v20 + 1) - (_QWORD)v20 != 72 )
  {
    std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::~basic_regex<unsigned short,std::regex_traits<unsigned short>>(v28);
    std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::~basic_regex<unsigned short,std::regex_traits<unsigned short>>(v29);
    if ( !v14 )
      return 0;
    v15 = v14;
LABEL_35:
    operator delete(v15);
    return 0;
  }
  try
  {
    std::sub_match<unsigned short const *>::operator std::wstring(v20 + 24, String);
    v16 = std::stoll(String);
    if ( v31 >= 8 )
      operator delete(*(void **)String);
    if ( v16 < v11 || v16 > v13 )
      v9 = 0;
    std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::~basic_regex<unsigned short,std::regex_traits<unsigned short>>(v28);
    std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::~basic_regex<unsigned short,std::regex_traits<unsigned short>>(v29);
    if ( (_QWORD)v20 )
      operator delete((void *)v20);
    result = v9;
  }
  catch ( std::invalid_argument )
  {
    goto LABEL_34;
  }
  catch ( std::out_of_range )
  {
LABEL_34:
    std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::~basic_regex<unsigned short,std::regex_traits<unsigned short>>(v28);
    std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::~basic_regex<unsigned short,std::regex_traits<unsigned short>>(v29);
    v15 = (void *)v20;
    if ( !(_QWORD)v20 )
      return 0;
    goto LABEL_35;
  }
  return result;
}

```

## disassembly

```asm
0x180025660  push    rbx
0x180025662  push    rsi
0x180025663  push    rdi
0x180025664  push    r12
0x180025666  push    r13
0x180025668  push    r14
0x18002566a  push    r15
0x18002566c  sub     rsp, 110h
0x180025673  mov     rax, cs:__security_cookie
0x18002567a  xor     rax, rsp
0x18002567d  mov     [rsp+148h+var_48], rax
0x180025685  mov     r13, rdx
0x180025688  mov     rbx, rcx
0x18002568b  xor     edi, edi
0x18002568d  mov     [rsp+148h+var_110], dil
0x180025692  xorps   xmm0, xmm0
0x180025695  movdqa  [rsp+148h+var_108], xmm0
0x18002569b  xorps   xmm1, xmm1
0x18002569e  movdqa  [rsp+148h+var_F8], xmm1
0x1800256a4  mov     [rsp+148h+var_E8], rdi
0x1800256a9  mov     [rsp+148h+var_E0], dil
0x1800256ae  movdqa  [rsp+148h+var_D8], xmm0
0x1800256b4  mov     [rsp+148h+var_C8], dil
0x1800256bc  mov     [rsp+148h+var_C0], rdi
0x1800256c4  mov     [rsp+148h+var_B8], rdi
0x1800256cc  mov     [rsp+148h+var_B0], dil
0x1800256d4  lea     rdx, aD119DFSD119DF; "^(-?\\d{1,19})(\\d|F)?,\\s?(-?\\d{1,19}"...
0x1800256db  lea     rcx, [rsp+148h+var_88]
0x1800256e3  call    ??0?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@PEBGW4syntax_option_type@regex_constants@1@@Z; std::basic_regex<ushort,std::regex_traits<ushort>>::basic_regex<ushort,std::regex_traits<ushort>>(ushort const *,std::regex_constants::syntax_option_type)
0x1800256e8  nop
0x1800256e9  lea     rcx, [rbx+30h]
0x1800256ed  cmp     qword ptr [rcx+18h], 8
0x1800256f2  jb      short loc_1800256F7
0x1800256f4  mov     rcx, [rcx]
0x1800256f7  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800256fb  cmp     [rcx], di
0x1800256fe  jnz     short loc_180025705
0x180025700  mov     rax, rdi
0x180025703  jmp     short loc_180025711
0x180025705  mov     rax, rsi
0x180025708  inc     rax
0x18002570b  cmp     [rcx+rax*2], di
0x18002570f  jnz     short loc_180025708
0x180025711  lea     rdx, [rcx+rax*2]
0x180025715  mov     [rsp+148h+var_128], edi; int
0x180025719  lea     r9, [rsp+148h+var_88]
0x180025721  lea     r8, [rsp+148h+var_118]
0x180025726  call    ??$_Regex_match@PEBGV?$allocator@V?$sub_match@PEBG@std@@@std@@GV?$regex_traits@G@2@PEBG@std@@YA_NPEBG0PEAV?$match_results@PEBGV?$allocator@V?$sub_match@PEBG@std@@@std@@@0@AEBV?$basic_regex@GV?$regex_traits@G@std@@@0@W4match_flag_type@regex_constants@0@_N@Z; std::_Regex_match<ushort const *,std::allocator<std::sub_match<ushort const *>>,ushort,std::regex_traits<ushort>,ushort const *>(ushort const *,ushort const *,std::match_results<ushort const *> *,std::basic_regex<ushort,std::regex_traits<ushort>> const &,std::regex_constants::match_flag_type,bool)
0x18002572b  mov     rcx, [rsp+148h]; this
0x180025733  test    al, al
0x180025735  jz      loc_180025980
0x18002573b  mov     r15, qword ptr [rsp+148h+var_108]
0x180025740  mov     rbx, qword ptr [rsp+148h+var_108+8]
0x180025745  sub     rbx, r15
0x180025748  sar     rbx, 3
0x18002574c  mov     rax, 0AAAAAAAAAAAAAAABh
0x180025756  imul    rbx, rax
0x18002575a  cmp     rbx, 5
0x18002575e  jz      short loc_180025765
0x180025760  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180025765  mov     r14d, 1
0x18002576b  cmp     rbx, r14
0x18002576e  lea     rcx, [rsp+148h+var_C0]
0x180025776  jbe     short loc_18002577C
0x180025778  lea     rcx, [r15+18h]
0x18002577c  lea     rdx, [rsp+148h+String]
0x180025784  call    ??B?$sub_match@PEBG@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@XZ; std::sub_match<ushort const *>::operator std::wstring(void)
0x180025789  nop
0x18002578a  lea     rcx, [rsp+148h+String]; String
0x180025792  call    ?stoll@std@@YA_JAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@PEA_KH@Z; std::stoll(std::wstring const &,unsigned __int64 *,int)
0x180025797  mov     r12, rax
0x18002579a  cmp     [rsp+148h+var_50], 8
0x1800257a3  jb      short loc_1800257B3
0x1800257a5  mov     rcx, qword ptr [rsp+148h+String]
0x1800257ad  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800257b3  mov     rdx, qword ptr [rsp+148h+var_108]
0x1800257b8  mov     rcx, qword ptr [rsp+148h+var_108+8]
0x1800257bd  sub     rcx, rdx
0x1800257c0  sar     rcx, 3
0x1800257c4  mov     rax, 0AAAAAAAAAAAAAAABh
0x1800257ce  imul    rcx, rax
0x1800257d2  cmp     rcx, 3
0x1800257d6  lea     rcx, [rsp+148h+var_C0]
0x1800257de  jbe     short loc_1800257E4
0x1800257e0  lea     rcx, [rdx+48h]
0x1800257e4  lea     rdx, [rsp+148h+String]
0x1800257ec  call    ??B?$sub_match@PEBG@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@XZ; std::sub_match<ushort const *>::operator std::wstring(void)
0x1800257f1  nop
0x1800257f2  lea     rcx, [rsp+148h+String]; String
0x1800257fa  call    ?stoll@std@@YA_JAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@PEA_KH@Z; std::stoll(std::wstring const &,unsigned __int64 *,int)
0x1800257ff  mov     r15, rax
0x180025802  cmp     [rsp+148h+var_50], 8
0x18002580b  jb      short loc_18002581B
0x18002580d  mov     rcx, qword ptr [rsp+148h+String]
0x180025815  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002581b  cmp     r15, r12
0x18002581e  jg      short loc_180025825
0x180025820  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180025825  lea     rdx, aD119DF; "^(-?\\d{1,19})(\\d|F)?$"
0x18002582c  lea     rcx, [rsp+148h+var_A8]
0x180025834  call    ??0?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@PEBGW4syntax_option_type@regex_constants@1@@Z; std::basic_regex<ushort,std::regex_traits<ushort>>::basic_regex<ushort,std::regex_traits<ushort>>(ushort const *,std::regex_constants::syntax_option_type)
0x180025839  nop
0x18002583a  cmp     [r13+0], di
0x18002583f  jnz     short loc_180025846
0x180025841  mov     rsi, rdi
0x180025844  jmp     short loc_180025851
0x180025846  inc     rsi
0x180025849  cmp     [r13+rsi*2+0], di
0x18002584f  jnz     short loc_180025846
0x180025851  lea     rdx, ds:0[rsi*2]
0x180025859  add     rdx, r13
0x18002585c  mov     [rsp+148h+var_128], edi
0x180025860  lea     r9, [rsp+148h+var_A8]
0x180025868  lea     r8, [rsp+148h+var_118]
0x18002586d  mov     rcx, r13
0x180025870  call    ??$_Regex_match@PEBGV?$allocator@V?$sub_match@PEBG@std@@@std@@GV?$regex_traits@G@2@PEBG@std@@YA_NPEBG0PEAV?$match_results@PEBGV?$allocator@V?$sub_match@PEBG@std@@@std@@@0@AEBV?$basic_regex@GV?$regex_traits@G@std@@@0@W4match_flag_type@regex_constants@0@_N@Z; std::_Regex_match<ushort const *,std::allocator<std::sub_match<ushort const *>>,ushort,std::regex_traits<ushort>,ushort const *>(ushort const *,ushort const *,std::match_results<ushort const *> *,std::basic_regex<ushort,std::regex_traits<ushort>> const &,std::regex_constants::match_flag_type,bool)
0x180025875  mov     rbx, qword ptr [rsp+148h+var_108]
0x18002587a  mov     rax, qword ptr [rsp+148h+var_108+8]
0x18002587f  sub     rax, rbx
0x180025882  cmp     rax, 48h ; 'H'
0x180025886  jz      short loc_1800258B5
0x180025888  lea     rcx, [rsp+148h+var_A8]
0x180025890  call    ??1?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@XZ; std::basic_regex<ushort,std::regex_traits<ushort>>::~basic_regex<ushort,std::regex_traits<ushort>>(void)
0x180025895  nop
0x180025896  lea     rcx, [rsp+148h+var_88]
0x18002589e  call    ??1?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@XZ; std::basic_regex<ushort,std::regex_traits<ushort>>::~basic_regex<ushort,std::regex_traits<ushort>>(void)
0x1800258a3  nop
0x1800258a4  test    rbx, rbx
0x1800258a7  jz      loc_18002595B
0x1800258ad  mov     rcx, rbx
0x1800258b0  jmp     loc_180025955
0x1800258b5  lea     rcx, [rbx+18h]
0x1800258b9  lea     rdx, [rsp+148h+String]
0x1800258c1  call    ??B?$sub_match@PEBG@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@XZ; std::sub_match<ushort const *>::operator std::wstring(void)
0x1800258c6  nop
0x1800258c7  lea     rcx, [rsp+148h+String]; String
0x1800258cf  call    ?stoll@std@@YA_JAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@PEA_KH@Z; std::stoll(std::wstring const &,unsigned __int64 *,int)
0x1800258d4  mov     rbx, rax
0x1800258d7  cmp     [rsp+148h+var_50], 8
0x1800258e0  jb      short loc_1800258F1
0x1800258e2  mov     rcx, qword ptr [rsp+148h+String]
0x1800258ea  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800258f0  nop
0x1800258f1  cmp     rbx, r12
0x1800258f4  jl      short loc_1800258FB
0x1800258f6  cmp     rbx, r15
0x1800258f9  jle     short loc_1800258FE
0x1800258fb  mov     r14b, dil
0x1800258fe  lea     rcx, [rsp+148h+var_A8]
0x180025906  call    ??1?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@XZ; std::basic_regex<ushort,std::regex_traits<ushort>>::~basic_regex<ushort,std::regex_traits<ushort>>(void)
0x18002590b  nop
0x18002590c  lea     rcx, [rsp+148h+var_88]
0x180025914  call    ??1?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@XZ; std::basic_regex<ushort,std::regex_traits<ushort>>::~basic_regex<ushort,std::regex_traits<ushort>>(void)
0x180025919  nop
0x18002591a  mov     rcx, qword ptr [rsp+148h+var_108]
0x18002591f  test    rcx, rcx
0x180025922  jz      short loc_18002592A
0x180025924  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002592a  mov     al, r14b
0x18002592d  jmp     short loc_18002595D
0x18002592f  lea     rcx, [rsp+148h+var_A8]
0x180025937  call    ??1?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@XZ; std::basic_regex<ushort,std::regex_traits<ushort>>::~basic_regex<ushort,std::regex_traits<ushort>>(void)
0x18002593c  nop
0x18002593d  lea     rcx, [rsp+148h+var_88]
0x180025945  call    ??1?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@XZ; std::basic_regex<ushort,std::regex_traits<ushort>>::~basic_regex<ushort,std::regex_traits<ushort>>(void)
0x18002594a  nop
0x18002594b  mov     rcx, qword ptr [rsp+148h+var_108]
0x180025950  test    rcx, rcx
0x180025953  jz      short loc_18002595B
0x180025955  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002595b  xor     al, al
0x18002595d  mov     rcx, [rsp+148h+var_48]
0x180025965  xor     rcx, rsp; StackCookie
0x180025968  call    __security_check_cookie
0x18002596d  add     rsp, 110h
0x180025974  pop     r15
0x180025976  pop     r14
0x180025978  pop     r13
0x18002597a  pop     r12
0x18002597c  pop     rdi
0x18002597d  pop     rsi
0x18002597e  pop     rbx
0x18002597f  retn
0x180025980  mov     r9d, 80070057h; char *
0x180025986  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18002598d  mov     edx, 29h ; ')'; void *
0x180025992  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
