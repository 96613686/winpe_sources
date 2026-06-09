# IsPrivateQPath(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>)

- ea: `0x14000fabc`
- end: `0x14000fbc6`
- name: `?IsPrivateQPath@@YA_NV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@@Z`
- size: `266`
- prototype: `bool __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x14000fe40`

## callees

- `0x140004648`
- `0x140004f9c`
- `0x140007554`
- `0x14000ed18`
- `0x14000f6a0`
- `0x14000fabc`
- `0x140010190`
- `0x14001cf00`

## import_xrefs

- `msvcrt!free` at `0x14000fb98`
- `msvcrt!free` at `0x14000fb98`
- `USER32!CharLowerW` at `0x14000fb5a`
- `USER32!CharLowerW` at `0x14000fb5a`

## pseudocode

```c
bool __fastcall IsPrivateQPath(_QWORD *a1)
{
  unsigned __int64 v2; // rdi
  wchar_t *v3; // rax
  WCHAR *v4; // rbx
  const wchar_t *v5; // r8
  __int64 v6; // rdx
  __int64 v7; // r8
  bool v8; // di
  wchar_t *v10; // [rsp+20h] [rbp-68h]
  _BYTE v12[40]; // [rsp+30h] [rbp-58h] BYREF

  v2 = a1[3] + 1LL;
  v3 = (wchar_t *)MmAllocate(saturated_mul(v2, 2u));
  v4 = v3;
  v10 = v3;
  if ( a1[4] < 8u )
    v5 = (const wchar_t *)(a1 + 1);
  else
    v5 = (const wchar_t *)a1[1];
  if ( (int)StringCchCopyW(v3, v2, v5) < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_f17d2b29d4b8365f8ea91b4848b968c5_Traceguids);
  }
  CharLowerW(v4);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>(
    v12,
    v4);
  v8 = std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::find(
         v12,
         v6,
         v7,
         8,
         v10,
         a1) != -1;
  std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy((__int64)v12, 1, 0);
  free(v4);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy((__int64)a1, 1, 0);
  return v8;
}

```

## disassembly

```asm
0x14000fabc  push    rbx
0x14000fabe  push    rbp
0x14000fabf  push    rsi
0x14000fac0  push    rdi
0x14000fac1  sub     rsp, 68h
0x14000fac5  mov     rax, cs:__security_cookie
0x14000facc  xor     rax, rsp
0x14000facf  mov     [rsp+88h+var_30], rax
0x14000fad4  mov     rsi, rcx
0x14000fad7  mov     [rsp+88h+var_60], rcx
0x14000fadc  mov     rdi, [rcx+18h]
0x14000fae0  inc     rdi
0x14000fae3  mov     eax, 2
0x14000fae8  mul     rdi
0x14000faeb  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x14000faf2  cmovb   rax, rbp
0x14000faf6  mov     rcx, rax; unsigned __int64
0x14000faf9  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x14000fafe  mov     rbx, rax
0x14000fb01  mov     [rsp+88h+var_68], rax
0x14000fb06  cmp     qword ptr [rsi+20h], 8
0x14000fb0b  jb      short loc_14000FB13
0x14000fb0d  mov     r8, [rsi+8]
0x14000fb11  jmp     short loc_14000FB17
0x14000fb13  lea     r8, [rsi+8]; wchar_t *
0x14000fb17  mov     rdx, rdi; unsigned __int64
0x14000fb1a  mov     rcx, rbx; wchar_t *
0x14000fb1d  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x14000fb22  test    eax, eax
0x14000fb24  jns     short loc_14000FB57
0x14000fb26  lea     rdx, WPP_GLOBAL_Control
0x14000fb2d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fb34  cmp     rcx, rdx
0x14000fb37  jz      short loc_14000FB57
0x14000fb39  test    byte ptr [rcx+1Ch], 1
0x14000fb3d  jz      short loc_14000FB57
0x14000fb3f  mov     edx, 0Fh
0x14000fb44  mov     r9d, eax
0x14000fb47  lea     r8, WPP_f17d2b29d4b8365f8ea91b4848b968c5_Traceguids
0x14000fb4e  mov     rcx, [rcx+10h]
0x14000fb52  call    WPP_SF_d
0x14000fb57  mov     rcx, rbx; lpsz
0x14000fb5a  call    cs:__imp_CharLowerW
0x14000fb60  mov     rdx, rbx
0x14000fb63  lea     rcx, [rsp+88h+var_58]
0x14000fb68  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>(wchar_t const *)
0x14000fb6d  mov     r9d, 8
0x14000fb73  lea     rcx, [rsp+88h+var_58]
0x14000fb78  call    ?find@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@QEBA_KPEB_W_K1@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::find(wchar_t const *,unsigned __int64,unsigned __int64)
0x14000fb7d  nop
0x14000fb7e  cmp     rax, rbp
0x14000fb81  setnz   dil
0x14000fb85  xor     r8d, r8d
0x14000fb88  mov     dl, 1
0x14000fb8a  lea     rcx, [rsp+88h+var_58]
0x14000fb8f  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy(bool,unsigned __int64)
0x14000fb94  nop
0x14000fb95  mov     rcx, rbx; Block
0x14000fb98  call    cs:__imp_free
0x14000fb9e  nop
0x14000fb9f  xor     r8d, r8d
0x14000fba2  mov     dl, 1
0x14000fba4  mov     rcx, rsi
0x14000fba7  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy(bool,unsigned __int64)
0x14000fbac  nop
0x14000fbad  mov     al, dil
0x14000fbb0  mov     rcx, [rsp+88h+var_30]
0x14000fbb5  xor     rcx, rsp; StackCookie
0x14000fbb8  call    __security_check_cookie
0x14000fbbd  add     rsp, 68h
0x14000fbc1  pop     rdi
0x14000fbc2  pop     rsi
0x14000fbc3  pop     rbp
0x14000fbc4  pop     rbx
0x14000fbc5  retn
```
