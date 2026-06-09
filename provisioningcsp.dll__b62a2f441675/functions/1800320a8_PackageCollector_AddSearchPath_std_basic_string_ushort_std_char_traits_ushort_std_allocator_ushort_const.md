# PackageCollector::AddSearchPath(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800320a8`
- end: `0x1800322b7`
- name: `?AddSearchPath@PackageCollector@@QEAA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `527`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x180031afc`

## callees

- `0x180001b14`
- `0x180001cf0`
- `0x180009fac`
- `0x18000f054`
- `0x18000fc30`
- `0x180028ee8`
- `0x1800320a8`
- `0x1800358a0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18003220c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180032280`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003220c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180032280`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x180032143`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x180032143`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool __fastcall PackageCollector::AddSearchPath(_QWORD *a1, _QWORD *a2, int a3, int a4)
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
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  bool v20; // r14
  WCHAR *v22; // [rsp+30h] [rbp-50h] BYREF
  WCHAR *v23; // [rsp+38h] [rbp-48h] BYREF
  PWSTR pszPathOut[2]; // [rsp+40h] [rbp-40h] BYREF
  __int64 v25; // [rsp+50h] [rbp-30h]
  void *v26[3]; // [rsp+58h] [rbp-28h] BYREF
  unsigned __int64 v27; // [rsp+70h] [rbp-10h]

  *(_OWORD *)pszPathOut = 0;
  v6 = 0;
  v25 = 0;
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
      v6 = v25;
      v9 = pszPathOut[0];
    }
    v10 = a2[3] < 8u ? (const WCHAR *)a2 : (const WCHAR *)*a2;
    v8 = PathCchCanonicalizeEx(v9, (v6 - (__int64)v9) >> 1, v10, 1u);
    v7 *= 2LL;
  }
  while ( v8 == -2147024774 );
  if ( v8 < 0 )
  {
    if ( (unsigned int)dword_1800495B0 > 3 )
    {
      LODWORD(v22) = v8;
      v23 = v9;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (_DWORD)a1,
        (unsigned int)&dword_180041A44,
        a3,
        a4,
        (__int64)&v23,
        (__int64)&v22);
    }
  }
  else
  {
    v11 = a1 + 1;
    v27 = 7;
    v26[2] = 0;
    LOWORD(v26[0]) = 0;
    if ( *v9 )
    {
      v12 = -1;
      do
        ++v12;
      while ( v9[v12] );
    }
    std::wstring::assign(v26, v9);
    if ( (unsigned __int64)v26 >= a1[2] || (v13 = 1, *v11 > (unsigned __int64)v26) )
      v13 = 0;
    v14 = a1[3];
    if ( v13 )
    {
      v15 = (unsigned __int64)v26 - *v11;
      if ( a1[2] == v14 )
        std::vector<std::wstring>::_Reserve(a1 + 1);
      v16 = (void **)(*v11 + (v15 & 0xFFFFFFFFFFFFFFE0uLL));
    }
    else
    {
      if ( a1[2] == v14 )
        std::vector<std::wstring>::_Reserve(a1 + 1);
      v16 = v26;
    }
    std::wstring::wstring(a1[2], v16);
    a1[2] += 32LL;
    if ( v27 >= 8 )
      operator delete(v26[0]);
    if ( (unsigned int)dword_1800495B0 > 5 )
    {
      v22 = v9;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        v17,
        (unsigned int)&byte_180041A17,
        v18,
        v19,
        (__int64)&v22);
    }
  }
  v20 = v8 >= 0;
  if ( v9 )
    operator delete(v9);
  return v20;
}

```

## disassembly

```asm
0x1800320a8  mov     [rsp-38h+arg_10], rbx
0x1800320ad  push    rbp
0x1800320ae  push    rsi
0x1800320af  push    rdi
0x1800320b0  push    r12
0x1800320b2  push    r13
0x1800320b4  push    r14
0x1800320b6  push    r15
0x1800320b8  mov     rbp, rsp
0x1800320bb  sub     rsp, 80h
0x1800320c2  mov     rax, cs:__security_cookie
0x1800320c9  xor     rax, rsp
0x1800320cc  mov     [rbp+var_8], rax
0x1800320d0  mov     rsi, rdx
0x1800320d3  mov     r13, rcx
0x1800320d6  xorps   xmm0, xmm0
0x1800320d9  movdqu  xmmword ptr [rbp+pszPathOut], xmm0
0x1800320de  xor     r12d, r12d
0x1800320e1  mov     r15d, r12d
0x1800320e4  mov     [rbp+var_30], r12
0x1800320e8  mov     ebx, 208h
0x1800320ed  mov     r14d, 8007007Ah
0x1800320f3  mov     rdi, [rbp+pszPathOut]
0x1800320f7  cmp     rbx, 0FFFFFFFh
0x1800320fe  jnb     short loc_18003215C
0x180032100  mov     rax, r15
0x180032103  sub     rax, rdi
0x180032106  sar     rax, 1
0x180032109  cmp     rax, rbx
0x18003210c  jnb     short loc_180032122
0x18003210e  mov     rdx, rbx
0x180032111  lea     rcx, [rbp+pszPathOut]
0x180032115  call    ?_Reallocate@?$vector@GV?$allocator@G@std@@@std@@IEAAX_K@Z; std::vector<ushort>::_Reallocate(unsigned __int64)
0x18003211a  mov     r15, [rbp+var_30]
0x18003211e  mov     rdi, [rbp+pszPathOut]
0x180032122  cmp     qword ptr [rsi+18h], 8
0x180032127  jb      short loc_18003212E
0x180032129  mov     r8, [rsi]
0x18003212c  jmp     short loc_180032131
0x18003212e  mov     r8, rsi; pszPathIn
0x180032131  mov     rdx, r15
0x180032134  sub     rdx, rdi
0x180032137  sar     rdx, 1; cchPathOut
0x18003213a  mov     r9d, 1; dwFlags
0x180032140  mov     rcx, rdi; pszPathOut
0x180032143  call    cs:__imp_PathCchCanonicalizeEx
0x18003214a  nop     dword ptr [rax+rax+00h]
0x18003214f  mov     r14d, eax
0x180032152  add     rbx, rbx
0x180032155  cmp     eax, 8007007Ah
0x18003215a  jz      short loc_1800320F7
0x18003215c  test    r14d, r14d
0x18003215f  js      loc_18003223E
0x180032165  lea     rbx, [r13+8]
0x180032169  mov     [rbp+var_10], 7
0x180032171  mov     [rbp+var_18], r12
0x180032175  mov     word ptr [rbp+var_28], r12w
0x18003217a  cmp     [rdi], r12w
0x18003217e  jnz     short loc_180032185
0x180032180  mov     r8, r12
0x180032183  jmp     short loc_180032193
0x180032185  or      r8, 0FFFFFFFFFFFFFFFFh
0x180032189  inc     r8
0x18003218c  cmp     [rdi+r8*2], r12w
0x180032191  jnz     short loc_180032189
0x180032193  mov     rdx, rdi; Src
0x180032196  lea     rcx, [rbp+var_28]; void *
0x18003219a  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18003219f  nop
0x1800321a0  lea     rax, [rbp+var_28]
0x1800321a4  cmp     rax, [rbx+8]
0x1800321a8  jnb     short loc_1800321B5
0x1800321aa  lea     rax, [rbp+var_28]
0x1800321ae  cmp     [rbx], rax
0x1800321b1  mov     al, 1
0x1800321b3  jbe     short loc_1800321B8
0x1800321b5  mov     al, r12b
0x1800321b8  mov     rcx, [rbx+10h]
0x1800321bc  test    al, al
0x1800321be  jz      short loc_1800321E1
0x1800321c0  lea     rsi, [rbp+var_28]
0x1800321c4  sub     rsi, [rbx]
0x1800321c7  cmp     [rbx+8], rcx
0x1800321cb  jnz     short loc_1800321D5
0x1800321cd  mov     rcx, rbx
0x1800321d0  call    ?_Reserve@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::wstring>::_Reserve(unsigned __int64)
0x1800321d5  and     rsi, 0FFFFFFFFFFFFFFE0h
0x1800321d9  add     rsi, [rbx]
0x1800321dc  mov     rdx, rsi
0x1800321df  jmp     short loc_1800321F3
0x1800321e1  cmp     [rbx+8], rcx
0x1800321e5  jnz     short loc_1800321EF
0x1800321e7  mov     rcx, rbx
0x1800321ea  call    ?_Reserve@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::wstring>::_Reserve(unsigned __int64)
0x1800321ef  lea     rdx, [rbp+var_28]
0x1800321f3  mov     rcx, [rbx+8]
0x1800321f7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x1800321fc  add     qword ptr [rbx+8], 20h ; ' '
0x180032201  cmp     [rbp+var_10], 8
0x180032206  jb      short loc_180032218
0x180032208  mov     rcx, [rbp+var_28]
0x18003220c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180032213  nop     dword ptr [rax+rax+00h]
0x180032218  mov     eax, cs:dword_1800495B0
0x18003221e  cmp     eax, 5
0x180032221  jbe     short loc_180032270
0x180032223  mov     [rbp+var_50], rdi
0x180032227  lea     rax, [rbp+var_50]
0x18003222b  mov     [rsp+80h+var_60], rax
0x180032230  lea     rdx, byte_180041A17
0x180032237  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18003223c  jmp     short loc_180032270
0x18003223e  mov     eax, cs:dword_1800495B0
0x180032244  cmp     eax, 3
0x180032247  jbe     short loc_180032270
0x180032249  mov     dword ptr [rbp+var_50], r14d
0x18003224d  mov     [rbp+var_48], rdi
0x180032251  lea     rax, [rbp+var_50]
0x180032255  mov     [rsp+80h+var_58], rax
0x18003225a  lea     rax, [rbp+var_48]
0x18003225e  mov     [rsp+80h+var_60], rax
0x180032263  lea     rdx, dword_180041A44
0x18003226a  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18003226f  nop
0x180032270  shr     r14d, 1Fh
0x180032274  xor     r14b, 1
0x180032278  test    rdi, rdi
0x18003227b  jz      short loc_18003228C
0x18003227d  mov     rcx, rdi
0x180032280  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180032287  nop     dword ptr [rax+rax+00h]
0x18003228c  mov     al, r14b
0x18003228f  mov     rcx, [rbp+var_8]
0x180032293  xor     rcx, rsp; StackCookie
0x180032296  call    __security_check_cookie
0x18003229b  mov     rbx, [rsp+80h+arg_10]
0x1800322a3  add     rsp, 80h
0x1800322aa  pop     r15
0x1800322ac  pop     r14
0x1800322ae  pop     r13
0x1800322b0  pop     r12
0x1800322b2  pop     rdi
0x1800322b3  pop     rsi
0x1800322b4  pop     rbp
0x1800322b5  retn
```
