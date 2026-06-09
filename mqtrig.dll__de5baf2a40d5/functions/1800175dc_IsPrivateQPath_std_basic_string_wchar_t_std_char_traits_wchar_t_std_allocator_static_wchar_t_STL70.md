# IsPrivateQPath(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>)

- ea: `0x1800175dc`
- end: `0x1800176e6`
- name: `?IsPrivateQPath@@YA_NV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@@Z`
- size: `266`
- prototype: `bool __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18001792c`

## callees

- `0x180002ec8`
- `0x1800041ec`
- `0x18000c654`
- `0x18000d87c`
- `0x180014ae8`
- `0x1800175dc`
- `0x180017c44`
- `0x18001e380`

## import_xrefs

- `msvcrt!free` at `0x1800176b8`
- `msvcrt!free` at `0x1800176b8`
- `USER32!CharLowerW` at `0x18001767a`
- `USER32!CharLowerW` at `0x18001767a`

## pseudocode

```c
bool __fastcall IsPrivateQPath(_QWORD *a1)
{
  unsigned __int64 v2; // rdi
  wchar_t *v3; // rax
  WCHAR *v4; // rbx
  const wchar_t *v5; // r8
  int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  bool v9; // di
  wchar_t *v11; // [rsp+20h] [rbp-68h]
  _BYTE v13[40]; // [rsp+30h] [rbp-58h] BYREF

  v2 = a1[3] + 1LL;
  v3 = (wchar_t *)MmAllocate(saturated_mul(v2, 2u));
  v4 = v3;
  v11 = v3;
  if ( a1[4] < 8u )
    v5 = (const wchar_t *)(a1 + 1);
  else
    v5 = (const wchar_t *)a1[1];
  v6 = StringCchCopyW(v3, v2, v5);
  if ( v6 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_f17d2b29d4b8365f8ea91b4848b968c5_Traceguids, (unsigned int)v6);
  CharLowerW(v4);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>(
    (__int64)v13,
    (__int64)v4);
  v9 = std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::find(
         v13,
         v7,
         v8,
         8,
         v11,
         a1) != -1;
  std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy((__int64)v13, 1, 0);
  free(v4);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy((__int64)a1, 1, 0);
  return v9;
}

```

## disassembly

```asm
0x1800175dc  push    rbx
0x1800175de  push    rbp
0x1800175df  push    rsi
0x1800175e0  push    rdi
0x1800175e1  sub     rsp, 68h
0x1800175e5  mov     rax, cs:__security_cookie
0x1800175ec  xor     rax, rsp
0x1800175ef  mov     [rsp+88h+var_30], rax
0x1800175f4  mov     rsi, rcx
0x1800175f7  mov     [rsp+88h+var_60], rcx
0x1800175fc  mov     rdi, [rcx+18h]
0x180017600  inc     rdi
0x180017603  mov     eax, 2
0x180017608  mul     rdi
0x18001760b  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x180017612  cmovb   rax, rbp
0x180017616  mov     rcx, rax; unsigned __int64
0x180017619  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18001761e  mov     rbx, rax
0x180017621  mov     [rsp+88h+var_68], rax
0x180017626  cmp     qword ptr [rsi+20h], 8
0x18001762b  jb      short loc_180017633
0x18001762d  mov     r8, [rsi+8]
0x180017631  jmp     short loc_180017637
0x180017633  lea     r8, [rsi+8]; wchar_t *
0x180017637  mov     rdx, rdi; unsigned __int64
0x18001763a  mov     rcx, rbx; wchar_t *
0x18001763d  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180017642  test    eax, eax
0x180017644  jns     short loc_180017677
0x180017646  lea     rdx, WPP_GLOBAL_Control
0x18001764d  mov     rcx, cs:WPP_GLOBAL_Control
0x180017654  cmp     rcx, rdx
0x180017657  jz      short loc_180017677
0x180017659  test    byte ptr [rcx+1Ch], 1
0x18001765d  jz      short loc_180017677
0x18001765f  mov     edx, 0Fh
0x180017664  mov     r9d, eax
0x180017667  lea     r8, WPP_f17d2b29d4b8365f8ea91b4848b968c5_Traceguids
0x18001766e  mov     rcx, [rcx+10h]
0x180017672  call    WPP_SF_d
0x180017677  mov     rcx, rbx; lpsz
0x18001767a  call    cs:__imp_CharLowerW
0x180017680  mov     rdx, rbx
0x180017683  lea     rcx, [rsp+88h+var_58]
0x180017688  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>(wchar_t const *)
0x18001768d  mov     r9d, 8
0x180017693  lea     rcx, [rsp+88h+var_58]
0x180017698  call    ?find@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@QEBA_KPEB_W_K1@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::find(wchar_t const *,unsigned __int64,unsigned __int64)
0x18001769d  nop
0x18001769e  cmp     rax, rbp
0x1800176a1  setnz   dil
0x1800176a5  xor     r8d, r8d
0x1800176a8  mov     dl, 1
0x1800176aa  lea     rcx, [rsp+88h+var_58]
0x1800176af  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy(bool,unsigned __int64)
0x1800176b4  nop
0x1800176b5  mov     rcx, rbx; Block
0x1800176b8  call    cs:__imp_free
0x1800176be  nop
0x1800176bf  xor     r8d, r8d
0x1800176c2  mov     dl, 1
0x1800176c4  mov     rcx, rsi
0x1800176c7  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy(bool,unsigned __int64)
0x1800176cc  nop
0x1800176cd  mov     al, dil
0x1800176d0  mov     rcx, [rsp+88h+var_30]
0x1800176d5  xor     rcx, rsp; StackCookie
0x1800176d8  call    __security_check_cookie
0x1800176dd  add     rsp, 68h
0x1800176e1  pop     rdi
0x1800176e2  pop     rsi
0x1800176e3  pop     rbp
0x1800176e4  pop     rbx
0x1800176e5  retn
```
