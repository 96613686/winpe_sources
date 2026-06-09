# CUSTOM_ERROR_HANDLER::LocalizedGetFileInfo(STRU *,char const *,STRU *,void *,void *,IHttpFileInfo * *,IHttpTraceContext *)

- ea: `0x1800038d0`
- end: `0x180003ac3`
- name: `?LocalizedGetFileInfo@CUSTOM_ERROR_HANDLER@@AEAAJPEAVSTRU@@PEBD0PEAX2PEAPEAVIHttpFileInfo@@PEAVIHttpTraceContext@@@Z`
- size: `499`
- prototype: `__int64 __fastcall(CUSTOM_ERROR_HANDLER *__hidden this, struct STRU *, const char *, struct STRU *, void *, void *, struct IHttpFileInfo **, struct IHttpTraceContext *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x180004968`

## callees

- `0x1800038d0`
- `0x180007836`
- `0x180007870`
- `0x180008010`

## import_xrefs

- `iisutil!?AppendA@STRU@@QEAAJPEBD@Z` at `0x1800039d0`
- `iisutil!?AppendA@STRU@@QEAAJPEBD@Z` at `0x1800039d0`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x1800039b8`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x1800039f8`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x1800039b8`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x1800039f8`
- `iisutil!?Copy@STRU@@QEAAJPEBV1@@Z` at `0x18000397a`
- `iisutil!?Copy@STRU@@QEAAJPEBV1@@Z` at `0x18000397a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003a91`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003a91`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000398f`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800039e3`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180003a0b`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180003a36`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180003a44`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000398f`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800039e3`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180003a0b`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180003a36`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180003a44`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x180003953`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x180003964`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x180003953`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x180003964`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18000399d`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18000399d`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180003a19`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180003a19`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000394a`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000394a`

## pseudocode

```c
__int64 __fastcall CUSTOM_ERROR_HANDLER::LocalizedGetFileInfo(
        CUSTOM_ERROR_HANDLER *this,
        struct STRU *a2,
        const char *a3,
        struct STRU *a4,
        void *a5,
        void *a6,
        struct IHttpFileInfo **a7,
        struct IHttpTraceContext *a8)
{
  int v11; // ebx
  unsigned __int16 *Str; // rbx
  const unsigned __int16 *v13; // rax
  __int64 (__fastcall *v14)(struct IHttpServer *, unsigned __int16 *, void *, _QWORD, unsigned __int16 *, void *, int, struct IHttpFileInfo **, struct IHttpTraceContext *); // rdi
  unsigned __int16 *v15; // rbx
  unsigned __int16 *v16; // rax
  _BYTE v18[56]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 v19[256]; // [rsp+90h] [rbp-70h] BYREF

  memset_0(v19, 0, sizeof(v19));
  STRU::STRU((STRU *)v18, v19, 0x100u);
  if ( STRU::IsEmpty(a2) || STRU::IsEmpty(a4) )
  {
    v11 = -2147024809;
  }
  else
  {
    v11 = STRU::Copy((STRU *)v18, a2);
    if ( v11 >= 0 )
    {
      Str = STRU::QueryStr((STRU *)v18);
      if ( Str[STRU::QueryCCH((STRU *)v18) - 1] == 92 || (v11 = STRU::Append((STRU *)v18, 0x5Cu), v11 >= 0) )
      {
        v11 = STRU::AppendA((STRU *)v18, a3);
        if ( v11 >= 0 )
        {
          if ( *STRU::QueryStr(a4) == 92 || (v11 = STRU::Append((STRU *)v18, 0x5Cu), v11 >= 0) )
          {
            v13 = STRU::QueryStr(a4);
            v11 = STRU::Append((STRU *)v18, v13);
            if ( v11 >= 0 )
            {
              v14 = *(__int64 (__fastcall **)(struct IHttpServer *, unsigned __int16 *, void *, _QWORD, unsigned __int16 *, void *, int, struct IHttpFileInfo **, struct IHttpTraceContext *))(*(_QWORD *)s_pGlobalInfo + 64LL);
              v15 = STRU::QueryStr(a2);
              v16 = STRU::QueryStr((STRU *)v18);
              v11 = v14(s_pGlobalInfo, v16, a5, 0, v15, a6, 1, a7, a8);
            }
          }
        }
      }
    }
  }
  STRU::~STRU((STRU *)v18);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800038d0  mov     [rsp-8+arg_0], rbx
0x1800038d5  push    rbp
0x1800038d6  push    rsi
0x1800038d7  push    rdi
0x1800038d8  push    r12
0x1800038da  push    r13
0x1800038dc  push    r14
0x1800038de  push    r15
0x1800038e0  lea     rbp, [rsp-1A0h]
0x1800038e8  sub     rsp, 2A0h
0x1800038ef  mov     rax, cs:__security_cookie
0x1800038f6  xor     rax, rsp
0x1800038f9  mov     [rbp+1D0h+var_40], rax
0x180003900  mov     rax, [rbp+1D0h+arg_38]
0x180003907  lea     rcx, [rbp+1D0h+var_240]; void *
0x18000390b  mov     r15, [rbp+1D0h+arg_20]
0x180003912  mov     r14, r8
0x180003915  mov     r12, [rbp+1D0h+arg_28]
0x18000391c  mov     rsi, rdx
0x18000391f  mov     r13, [rbp+1D0h+arg_30]
0x180003926  xor     edx, edx; Val
0x180003928  mov     r8d, 200h; Size
0x18000392e  mov     [rsp+2D0h+var_280], rax
0x180003933  mov     rdi, r9
0x180003936  call    memset_0
0x18000393b  mov     r8d, 100h
0x180003941  lea     rdx, [rbp+1D0h+var_240]
0x180003945  lea     rcx, [rsp+2D0h+var_278]
0x18000394a  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180003950  mov     rcx, rsi
0x180003953  call    cs:__imp_?IsEmpty@STRU@@QEBA_NXZ; STRU::IsEmpty(void)
0x180003959  test    al, al
0x18000395b  jnz     loc_180003A87
0x180003961  mov     rcx, rdi
0x180003964  call    cs:__imp_?IsEmpty@STRU@@QEBA_NXZ; STRU::IsEmpty(void)
0x18000396a  test    al, al
0x18000396c  jnz     loc_180003A87
0x180003972  mov     rdx, rsi
0x180003975  lea     rcx, [rsp+2D0h+var_278]
0x18000397a  call    cs:__imp_?Copy@STRU@@QEAAJPEBV1@@Z; STRU::Copy(STRU const *)
0x180003980  mov     ebx, eax
0x180003982  test    eax, eax
0x180003984  js      loc_180003A8C
0x18000398a  lea     rcx, [rsp+2D0h+var_278]
0x18000398f  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180003995  lea     rcx, [rsp+2D0h+var_278]
0x18000399a  mov     rbx, rax
0x18000399d  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x1800039a3  lea     ecx, [rax-1]
0x1800039a6  mov     eax, 5Ch ; '\'
0x1800039ab  cmp     ax, [rbx+rcx*2]
0x1800039af  jz      short loc_1800039C8
0x1800039b1  mov     edx, eax
0x1800039b3  lea     rcx, [rsp+2D0h+var_278]
0x1800039b8  call    cs:__imp_?Append@STRU@@QEAAJG@Z; STRU::Append(ushort)
0x1800039be  mov     ebx, eax
0x1800039c0  test    eax, eax
0x1800039c2  js      loc_180003A8C
0x1800039c8  mov     rdx, r14
0x1800039cb  lea     rcx, [rsp+2D0h+var_278]
0x1800039d0  call    cs:__imp_?AppendA@STRU@@QEAAJPEBD@Z; STRU::AppendA(char const *)
0x1800039d6  mov     ebx, eax
0x1800039d8  test    eax, eax
0x1800039da  js      loc_180003A8C
0x1800039e0  mov     rcx, rdi
0x1800039e3  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800039e9  mov     edx, 5Ch ; '\'
0x1800039ee  cmp     dx, [rax]
0x1800039f1  jz      short loc_180003A08
0x1800039f3  lea     rcx, [rsp+2D0h+var_278]
0x1800039f8  call    cs:__imp_?Append@STRU@@QEAAJG@Z; STRU::Append(ushort)
0x1800039fe  mov     ebx, eax
0x180003a00  test    eax, eax
0x180003a02  js      loc_180003A8C
0x180003a08  mov     rcx, rdi
0x180003a0b  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180003a11  mov     rdx, rax
0x180003a14  lea     rcx, [rsp+2D0h+var_278]
0x180003a19  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180003a1f  mov     ebx, eax
0x180003a21  test    eax, eax
0x180003a23  js      short loc_180003A8C
0x180003a25  mov     rax, cs:?s_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * s_pGlobalInfo
0x180003a2c  mov     rcx, rsi
0x180003a2f  mov     rdx, [rax]
0x180003a32  mov     rdi, [rdx+40h]
0x180003a36  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180003a3c  lea     rcx, [rsp+2D0h+var_278]
0x180003a41  mov     rbx, rax
0x180003a44  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180003a4a  mov     rcx, [rsp+2D0h+var_280]
0x180003a4f  xor     r9d, r9d
0x180003a52  mov     [rsp+2D0h+var_290], rcx
0x180003a57  mov     rdx, rax
0x180003a5a  mov     rcx, cs:?s_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * s_pGlobalInfo
0x180003a61  mov     r8, r15
0x180003a64  mov     [rsp+2D0h+var_298], r13
0x180003a69  mov     rax, rdi
0x180003a6c  mov     [rsp+2D0h+var_2A0], 1
0x180003a74  mov     [rsp+2D0h+var_2A8], r12
0x180003a79  mov     [rsp+2D0h+var_2B0], rbx
0x180003a7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a83  mov     ebx, eax
0x180003a85  jmp     short loc_180003A8C
0x180003a87  mov     ebx, 80070057h
0x180003a8c  lea     rcx, [rsp+2D0h+var_278]
0x180003a91  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180003a97  mov     eax, ebx
0x180003a99  mov     rcx, [rbp+1D0h+var_40]
0x180003aa0  xor     rcx, rsp; StackCookie
0x180003aa3  call    __security_check_cookie
0x180003aa8  mov     rbx, [rsp+2D0h+arg_0]
0x180003ab0  add     rsp, 2A0h
0x180003ab7  pop     r15
0x180003ab9  pop     r14
0x180003abb  pop     r13
0x180003abd  pop     r12
0x180003abf  pop     rdi
0x180003ac0  pop     rsi
0x180003ac1  pop     rbp
0x180003ac2  retn
```
