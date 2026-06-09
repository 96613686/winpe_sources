# CONFIG_FILE::GetRawConfigSection(ushort const *,ushort const *,INativeConfigurationElement * *,INativeSectionException * *)

- ea: `0x1800271d0`
- end: `0x180027386`
- name: `?GetRawConfigSection@CONFIG_FILE@@UEAAJPEBG0PEAPEAVINativeConfigurationElement@@PEAPEAVINativeSectionException@@@Z`
- size: `438`
- prototype: `int(CONFIG_FILE *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct INativeConfigurationElement **, struct INativeSectionException **)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callees

- `0x180016440`
- `0x18001c250`
- `0x18001fda0`
- `0x1800266e4`
- `0x1800271d0`
- `0x180058ba0`
- `0x180059bea`
- `0x180059c30`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x180027353`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180027353`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002729e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800272d5`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002729e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800272d5`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18002726e`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18002726e`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18002728f`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x1800272ab`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x1800272be`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18002728f`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x1800272ab`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x1800272be`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18002727b`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18002727b`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x1800272cb`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x1800272cb`

## pseudocode

```c
__int64 __fastcall CONFIG_FILE::GetRawConfigSection(
        CONFIG_FILE *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct INativeConfigurationElement **a4,
        struct INativeSectionException **a5)
{
  int ConfigElement; // edi
  unsigned __int16 *Str; // rbx
  unsigned int CCH; // eax
  const unsigned __int16 *v12; // rax
  struct CONFIG_ELEMENT *v13; // rax
  CONFIG_EXCEPTION *v14; // rax
  CONFIG_EXCEPTION *v15; // rax
  CONFIG_EXCEPTION *v16; // rbx
  struct CONFIG_ELEMENT *v18; // [rsp+30h] [rbp-D0h] BYREF
  void **v19; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v20; // [rsp+48h] [rbp-B8h]
  int v21; // [rsp+50h] [rbp-B0h]
  __int64 v22; // [rsp+58h] [rbp-A8h]
  __int128 v23; // [rsp+60h] [rbp-A0h]
  __int128 v24; // [rsp+70h] [rbp-90h]
  _BYTE v25[64]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v26[256]; // [rsp+C0h] [rbp-40h] BYREF

  v19 = &PARSE_ERROR_INFO::`vftable';
  v18 = 0;
  v20 = 1;
  v21 = 0;
  v23 = 0;
  v24 = 0;
  v22 = 0;
  memset_0(v26, 0, sizeof(v26));
  STRU::STRU((STRU *)v25, v26, 0x100u);
  ConfigElement = STRU::Copy((STRU *)v25, a3);
  if ( ConfigElement >= 0 )
  {
    if ( STRU::QueryCCH((STRU *)v25) )
    {
      Str = STRU::QueryStr((STRU *)v25);
      if ( Str[STRU::QueryCCH((STRU *)v25) - 1] == 47 )
      {
        CCH = STRU::QueryCCH((STRU *)v25);
        STRU::SetLen((STRU *)v25, CCH - 1);
      }
    }
    v12 = STRU::QueryStr((STRU *)v25);
    ConfigElement = CONFIG_FILE::GetConfigElement(
                      (CONFIG_FILE *)((char *)this - 16),
                      v12,
                      a2,
                      &v18,
                      (struct PARSE_ERROR_INFO *)&v19);
    if ( ConfigElement >= 0 )
    {
      v13 = v18;
      if ( v18 )
        v13 = (struct CONFIG_ELEMENT *)((char *)v18 + 16);
      *a4 = v13;
    }
    if ( (_DWORD)v20 != 1 )
    {
      if ( a5 )
      {
        v14 = (CONFIG_EXCEPTION *)operator new(0x178u);
        if ( v14 )
        {
          v15 = CONFIG_EXCEPTION::CONFIG_EXCEPTION(v14);
          v16 = v15;
          if ( v15 )
          {
            CONFIG_EXCEPTION::Create(v15, (struct PARSE_ERROR_INFO *)&v19);
            *a5 = (CONFIG_EXCEPTION *)((char *)v16 + 24);
          }
        }
      }
    }
  }
  STRU::~STRU((STRU *)v25);
  PARSE_ERROR_INFO::~PARSE_ERROR_INFO((PARSE_ERROR_INFO *)&v19);
  return (unsigned int)ConfigElement;
}

```

## disassembly

```asm
0x1800271d0  push    rbp
0x1800271d2  push    rbx
0x1800271d3  push    rsi
0x1800271d4  push    rdi
0x1800271d5  push    r12
0x1800271d7  push    r14
0x1800271d9  push    r15
0x1800271db  lea     rbp, [rsp-1D0h]
0x1800271e3  sub     rsp, 2D0h
0x1800271ea  mov     rax, cs:__security_cookie
0x1800271f1  xor     rax, rsp
0x1800271f4  mov     [rbp+200h+var_40], rax
0x1800271fb  mov     rsi, [rbp+200h+arg_20]
0x180027202  lea     rax, ??_7PARSE_ERROR_INFO@@6B@; const PARSE_ERROR_INFO::`vftable'
0x180027209  mov     rbx, r8
0x18002720c  mov     [rsp+300h+var_2C0], rax
0x180027211  mov     r12, rdx
0x180027214  mov     [rsp+300h+var_2D0], 0
0x18002721d  mov     r15, rcx
0x180027220  mov     [rsp+300h+var_2B8], 1
0x180027229  xorps   xmm0, xmm0
0x18002722c  mov     [rsp+300h+var_2B0], 0
0x180027234  xorps   xmm1, xmm1
0x180027237  movdqa  [rsp+300h+var_2A0], xmm0
0x18002723d  xor     edx, edx; Val
0x18002723f  movdqa  [rsp+300h+var_290], xmm1
0x180027245  mov     r8d, 200h; Size
0x18002724b  mov     [rsp+300h+var_2A8], 0
0x180027254  lea     rcx, [rbp+200h+var_240]; void *
0x180027258  mov     r14, r9
0x18002725b  call    memset_0
0x180027260  mov     r8d, 100h
0x180027266  lea     rdx, [rbp+200h+var_240]
0x18002726a  lea     rcx, [rbp+200h+var_280]
0x18002726e  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180027274  mov     rdx, rbx
0x180027277  lea     rcx, [rbp+200h+var_280]
0x18002727b  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180027281  mov     edi, eax
0x180027283  test    eax, eax
0x180027285  js      loc_18002734F
0x18002728b  lea     rcx, [rbp+200h+var_280]
0x18002728f  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x180027295  cmp     eax, 1
0x180027298  jb      short loc_1800272D1
0x18002729a  lea     rcx, [rbp+200h+var_280]
0x18002729e  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800272a4  lea     rcx, [rbp+200h+var_280]
0x1800272a8  mov     rbx, rax
0x1800272ab  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x1800272b1  dec     eax
0x1800272b3  cmp     word ptr [rbx+rax*2], 2Fh ; '/'
0x1800272b8  jnz     short loc_1800272D1
0x1800272ba  lea     rcx, [rbp+200h+var_280]
0x1800272be  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x1800272c4  lea     rcx, [rbp+200h+var_280]
0x1800272c8  lea     edx, [rax-1]
0x1800272cb  call    cs:__imp_?SetLen@STRU@@QEAA_NK@Z; STRU::SetLen(ulong)
0x1800272d1  lea     rcx, [rbp+200h+var_280]
0x1800272d5  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800272db  lea     rcx, [r15-10h]; this
0x1800272df  mov     r8, r12; unsigned __int16 *
0x1800272e2  mov     rdx, rax; unsigned __int16 *
0x1800272e5  lea     r9, [rsp+300h+var_2D0]; struct CONFIG_ELEMENT **
0x1800272ea  lea     rax, [rsp+300h+var_2C0]
0x1800272ef  mov     [rsp+300h+var_2E0], rax; struct PARSE_ERROR_INFO *
0x1800272f4  call    ?GetConfigElement@CONFIG_FILE@@QEAAJPEBG0PEAPEAVCONFIG_ELEMENT@@PEAVPARSE_ERROR_INFO@@@Z; CONFIG_FILE::GetConfigElement(ushort const *,ushort const *,CONFIG_ELEMENT * *,PARSE_ERROR_INFO *)
0x1800272f9  mov     edi, eax
0x1800272fb  test    eax, eax
0x1800272fd  js      short loc_180027310
0x1800272ff  mov     rax, [rsp+300h+var_2D0]
0x180027304  test    rax, rax
0x180027307  jz      short loc_18002730D
0x180027309  add     rax, 10h
0x18002730d  mov     [r14], rax
0x180027310  cmp     dword ptr [rsp+300h+var_2B8], 1
0x180027315  jz      short loc_18002734F
0x180027317  test    rsi, rsi
0x18002731a  jz      short loc_18002734F
0x18002731c  mov     ecx, 178h; Size
0x180027321  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180027326  test    rax, rax
0x180027329  jz      short loc_18002734F
0x18002732b  mov     rcx, rax; this
0x18002732e  call    ??0CONFIG_EXCEPTION@@QEAA@XZ; CONFIG_EXCEPTION::CONFIG_EXCEPTION(void)
0x180027333  mov     rbx, rax
0x180027336  test    rax, rax
0x180027339  jz      short loc_18002734F
0x18002733b  lea     rdx, [rsp+300h+var_2C0]; struct PARSE_ERROR_INFO *
0x180027340  mov     rcx, rax; this
0x180027343  call    ?Create@CONFIG_EXCEPTION@@QEAAJPEAVPARSE_ERROR_INFO@@@Z; CONFIG_EXCEPTION::Create(PARSE_ERROR_INFO *)
0x180027348  lea     rax, [rbx+18h]
0x18002734c  mov     [rsi], rax
0x18002734f  lea     rcx, [rbp+200h+var_280]
0x180027353  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180027359  lea     rcx, [rsp+300h+var_2C0]; this
0x18002735e  call    ??1PARSE_ERROR_INFO@@UEAA@XZ; PARSE_ERROR_INFO::~PARSE_ERROR_INFO(void)
0x180027363  mov     eax, edi
0x180027365  mov     rcx, [rbp+200h+var_40]
0x18002736c  xor     rcx, rsp; StackCookie
0x18002736f  call    __security_check_cookie
0x180027374  add     rsp, 2D0h
0x18002737b  pop     r15
0x18002737d  pop     r14
0x18002737f  pop     r12
0x180027381  pop     rdi
0x180027382  pop     rsi
0x180027383  pop     rbx
0x180027384  pop     rbp
0x180027385  retn
```
