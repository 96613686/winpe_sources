# PackageCollector::AddSearchPath(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180039d80`
- end: `0x180039f90`
- name: `?AddSearchPath@PackageCollector@@QEAA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `528`
- prototype: `bool __fastcall(_QWORD *, _QWORD *, __int64, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x180014810`
- `0x180039828`

## callees

- `0x1800011ac`
- `0x1800018ec`
- `0x18000adec`
- `0x18000b030`
- `0x18000f56c`
- `0x180021c5c`
- `0x180039d80`
- `0x180043750`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180039ede`
- `msvcrt!??3@YAXPEAX@Z` at `0x180039f60`
- `msvcrt!??3@YAXPEAX@Z` at `0x180039ede`
- `msvcrt!??3@YAXPEAX@Z` at `0x180039f60`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x180039e1b`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x180039e1b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool __fastcall PackageCollector::AddSearchPath(_QWORD *a1, _QWORD *a2, __int64 a3, int a4)
{
  __int64 v6; // r15
  unsigned __int64 v7; // rbx
  HRESULT v8; // r14d
  WCHAR *v9; // rdi
  const WCHAR *v10; // r8
  _QWORD *v11; // rbx
  __int64 v12; // r8
  char v13; // al
  __int64 v14; // rcx
  unsigned __int64 v15; // rsi
  void **v16; // rdx
  int v17; // r9d
  bool v18; // r14
  WCHAR *v20; // [rsp+30h] [rbp-50h] BYREF
  WCHAR *v21; // [rsp+38h] [rbp-48h] BYREF
  PWSTR pszPathOut[2]; // [rsp+40h] [rbp-40h] BYREF
  __int64 v23; // [rsp+50h] [rbp-30h]
  void *v24[3]; // [rsp+58h] [rbp-28h] BYREF
  unsigned __int64 v25; // [rsp+70h] [rbp-10h]

  *(_OWORD *)pszPathOut = 0;
  v6 = 0;
  v23 = 0;
  v7 = 520;
  v8 = -2147024774;
  v9 = 0;
  do
  {
    if ( v7 >= 0xFFFFFFF )
      break;
    if ( (v6 - (__int64)v9) >> 1 < v7 )
    {
      std::vector<unsigned short>::_Reallocate(pszPathOut, v7);
      v6 = v23;
      v9 = pszPathOut[0];
    }
    v10 = a2[3] < 8u ? (const WCHAR *)a2 : (const WCHAR *)*a2;
    v8 = PathCchCanonicalizeEx(v9, (v6 - (__int64)v9) >> 1, v10, 1u);
    v7 *= 2LL;
  }
  while ( v8 == -2147024774 );
  if ( v8 < 0 )
  {
    if ( (unsigned int)dword_18005A000 > 3 )
    {
      LODWORD(v20) = v8;
      v21 = v9;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_18005A000,
        (unsigned int)byte_18005033D,
        0,
        a4,
        (__int64)&v21,
        (__int64)&v20);
    }
  }
  else
  {
    v11 = a1 + 1;
    v25 = 7;
    v24[2] = 0;
    LOWORD(v24[0]) = 0;
    if ( *v9 )
    {
      v12 = -1;
      do
        ++v12;
      while ( v9[v12] );
    }
    std::wstring::assign(v24, v9);
    if ( (unsigned __int64)v24 >= a1[2] || (v13 = 1, *v11 > (unsigned __int64)v24) )
      v13 = 0;
    v14 = a1[3];
    if ( v13 )
    {
      v15 = (unsigned __int64)v24 - *v11;
      if ( a1[2] == v14 )
        std::vector<std::wstring>::_Reserve(a1 + 1);
      v16 = (void **)(*v11 + (v15 & 0xFFFFFFFFFFFFFFE0uLL));
    }
    else
    {
      if ( a1[2] == v14 )
        std::vector<std::wstring>::_Reserve(a1 + 1);
      v16 = v24;
    }
    std::wstring::wstring(a1[2], v16);
    a1[2] += 32LL;
    if ( v25 >= 8 )
      operator delete(v24[0]);
    if ( (unsigned int)dword_18005A000 > 5 )
    {
      v20 = v9;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (unsigned int)&dword_18005A000,
        (unsigned int)&unk_180050310,
        0,
        v17,
        (__int64)&v20);
    }
  }
  v18 = v8 >= 0;
  if ( v9 )
    operator delete(v9);
  return v18;
}

```

## disassembly

```asm
0x180039d80  mov     [rsp-38h+arg_10], rbx
0x180039d85  push    rbp
0x180039d86  push    rsi
0x180039d87  push    rdi
0x180039d88  push    r12
0x180039d8a  push    r13
0x180039d8c  push    r14
0x180039d8e  push    r15
0x180039d90  mov     rbp, rsp
0x180039d93  sub     rsp, 80h
0x180039d9a  mov     rax, cs:__security_cookie
0x180039da1  xor     rax, rsp
0x180039da4  mov     [rbp+var_8], rax
0x180039da8  mov     rsi, rdx
0x180039dab  mov     r13, rcx
0x180039dae  xorps   xmm0, xmm0
0x180039db1  movdqu  xmmword ptr [rbp+pszPathOut], xmm0
0x180039db6  xor     r12d, r12d
0x180039db9  mov     r15d, r12d
0x180039dbc  mov     [rbp+var_30], r12
0x180039dc0  mov     ebx, 208h
0x180039dc5  mov     r14d, 8007007Ah
0x180039dcb  mov     rdi, [rbp+pszPathOut]
0x180039dcf  cmp     rbx, 0FFFFFFFh
0x180039dd6  jnb     short loc_180039E2E
0x180039dd8  mov     rax, r15
0x180039ddb  sub     rax, rdi
0x180039dde  sar     rax, 1
0x180039de1  cmp     rax, rbx
0x180039de4  jnb     short loc_180039DFA
0x180039de6  mov     rdx, rbx
0x180039de9  lea     rcx, [rbp+pszPathOut]
0x180039ded  call    ?_Reallocate@?$vector@GV?$allocator@G@std@@@std@@IEAAX_K@Z; std::vector<ushort>::_Reallocate(unsigned __int64)
0x180039df2  mov     r15, [rbp+var_30]
0x180039df6  mov     rdi, [rbp+pszPathOut]
0x180039dfa  cmp     qword ptr [rsi+18h], 8
0x180039dff  jb      short loc_180039E06
0x180039e01  mov     r8, [rsi]
0x180039e04  jmp     short loc_180039E09
0x180039e06  mov     r8, rsi; pszPathIn
0x180039e09  mov     rdx, r15
0x180039e0c  sub     rdx, rdi
0x180039e0f  sar     rdx, 1; cchPathOut
0x180039e12  mov     r9d, 1; dwFlags
0x180039e18  mov     rcx, rdi; pszPathOut
0x180039e1b  call    cs:__imp_PathCchCanonicalizeEx
0x180039e21  mov     r14d, eax
0x180039e24  add     rbx, rbx
0x180039e27  cmp     eax, 8007007Ah
0x180039e2c  jz      short loc_180039DCF
0x180039e2e  test    r14d, r14d
0x180039e31  js      loc_180039F14
0x180039e37  lea     rbx, [r13+8]
0x180039e3b  mov     [rbp+var_10], 7
0x180039e43  mov     [rbp+var_18], r12
0x180039e47  mov     word ptr [rbp+var_28], r12w
0x180039e4c  cmp     [rdi], r12w
0x180039e50  jnz     short loc_180039E57
0x180039e52  mov     r8, r12
0x180039e55  jmp     short loc_180039E65
0x180039e57  or      r8, 0FFFFFFFFFFFFFFFFh
0x180039e5b  inc     r8
0x180039e5e  cmp     [rdi+r8*2], r12w
0x180039e63  jnz     short loc_180039E5B
0x180039e65  mov     rdx, rdi; Src
0x180039e68  lea     rcx, [rbp+var_28]; void *
0x180039e6c  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180039e71  nop
0x180039e72  lea     rax, [rbp+var_28]
0x180039e76  cmp     rax, [rbx+8]
0x180039e7a  jnb     short loc_180039E87
0x180039e7c  lea     rax, [rbp+var_28]
0x180039e80  cmp     [rbx], rax
0x180039e83  mov     al, 1
0x180039e85  jbe     short loc_180039E8A
0x180039e87  mov     al, r12b
0x180039e8a  mov     rcx, [rbx+10h]
0x180039e8e  test    al, al
0x180039e90  jz      short loc_180039EB3
0x180039e92  lea     rsi, [rbp+var_28]
0x180039e96  sub     rsi, [rbx]
0x180039e99  cmp     [rbx+8], rcx
0x180039e9d  jnz     short loc_180039EA7
0x180039e9f  mov     rcx, rbx
0x180039ea2  call    ?_Reserve@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::wstring>::_Reserve(unsigned __int64)
0x180039ea7  and     rsi, 0FFFFFFFFFFFFFFE0h
0x180039eab  add     rsi, [rbx]
0x180039eae  mov     rdx, rsi
0x180039eb1  jmp     short loc_180039EC5
0x180039eb3  cmp     [rbx+8], rcx
0x180039eb7  jnz     short loc_180039EC1
0x180039eb9  mov     rcx, rbx
0x180039ebc  call    ?_Reserve@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::wstring>::_Reserve(unsigned __int64)
0x180039ec1  lea     rdx, [rbp+var_28]
0x180039ec5  mov     rcx, [rbx+8]
0x180039ec9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x180039ece  add     qword ptr [rbx+8], 20h ; ' '
0x180039ed3  cmp     [rbp+var_10], 8
0x180039ed8  jb      short loc_180039EE4
0x180039eda  mov     rcx, [rbp+var_28]
0x180039ede  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180039ee4  mov     eax, cs:dword_18005A000
0x180039eea  cmp     eax, 5
0x180039eed  jbe     short loc_180039F50
0x180039eef  mov     [rbp+var_50], rdi
0x180039ef3  lea     rax, [rbp+var_50]
0x180039ef7  mov     [rsp+80h+var_60], rax
0x180039efc  xor     r8d, r8d
0x180039eff  lea     rdx, unk_180050310
0x180039f06  lea     rcx, dword_18005A000
0x180039f0d  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180039f12  jmp     short loc_180039F50
0x180039f14  mov     eax, cs:dword_18005A000
0x180039f1a  cmp     eax, 3
0x180039f1d  jbe     short loc_180039F50
0x180039f1f  mov     dword ptr [rbp+var_50], r14d
0x180039f23  mov     [rbp+var_48], rdi
0x180039f27  lea     rax, [rbp+var_50]
0x180039f2b  mov     [rsp+80h+var_58], rax
0x180039f30  lea     rax, [rbp+var_48]
0x180039f34  mov     [rsp+80h+var_60], rax
0x180039f39  xor     r8d, r8d
0x180039f3c  lea     rdx, byte_18005033D
0x180039f43  lea     rcx, dword_18005A000
0x180039f4a  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180039f4f  nop
0x180039f50  shr     r14d, 1Fh
0x180039f54  xor     r14b, 1
0x180039f58  test    rdi, rdi
0x180039f5b  jz      short loc_180039F66
0x180039f5d  mov     rcx, rdi
0x180039f60  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180039f66  mov     al, r14b
0x180039f69  mov     rcx, [rbp+var_8]
0x180039f6d  xor     rcx, rsp; StackCookie
0x180039f70  call    __security_check_cookie
0x180039f75  mov     rbx, [rsp+80h+arg_10]
0x180039f7d  add     rsp, 80h
0x180039f84  pop     r15
0x180039f86  pop     r14
0x180039f88  pop     r13
0x180039f8a  pop     r12
0x180039f8c  pop     rdi
0x180039f8d  pop     rsi
0x180039f8e  pop     rbp
0x180039f8f  retn
```
