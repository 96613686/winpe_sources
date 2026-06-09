# Cabinet::CreateCab(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,CompressionType)

- ea: `0x180008c24`
- end: `0x180008d7a`
- name: `?CreateCab@Cabinet@@SAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@000W4CompressionType@@@Z`
- size: `342`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int64, __int64, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180006b60`

## callees

- `0x180001540`
- `0x180003648`
- `0x1800036b4`
- `0x18000553c`
- `0x180008c24`
- `0x180008d80`
- `0x18000b84c`
- `0x1800104d4`

## pseudocode

```c
__int64 __fastcall Cabinet::CreateCab(__int64 a1, _QWORD *a2, __int64 a3, __int64 a4, int a5)
{
  _QWORD *v5; // rbx
  __int64 v7; // rdx
  int Files; // eax
  unsigned int v10; // edi
  __int64 v11; // rax
  int CabSelected; // eax
  int v13; // [rsp+20h] [rbp-41h]
  int v14; // [rsp+20h] [rbp-41h]
  _QWORD v15[3]; // [rsp+30h] [rbp-31h] BYREF
  __int128 v16; // [rsp+48h] [rbp-19h] BYREF
  __int64 v17; // [rsp+58h] [rbp-9h]
  char *v18[4]; // [rsp+60h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+57h]

  v15[2] = -2;
  v5 = a2;
  if ( !*(_QWORD *)(a1 + 16) )
  {
    v7 = 421;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\cbs\\mobile\\cabapi\\privlib\\cabinetapi.cpp",
      (const char *)0x80070057LL,
      v13);
    return 2147942487LL;
  }
  if ( !a2[2] )
  {
    v7 = 422;
    goto LABEL_3;
  }
  if ( !*(_QWORD *)(a3 + 16) )
  {
    v7 = 423;
    goto LABEL_3;
  }
  v16 = 0;
  v17 = 0;
  Files = Utils::GetFiles((__int64)&v16, a2, a4, 1);
  v10 = Files;
  if ( Files >= 0 )
  {
    v11 = v5[2];
    if ( v5[3] > 7u )
      v5 = (_QWORD *)*v5;
    v15[0] = v5;
    v15[1] = v11;
    GetCanonicalUNCPath(v18, v15);
    CabSelected = Cabinet::CreateCabSelected((wchar_t *)a1, a5);
    v10 = CabSelected;
    if ( CabSelected >= 0 )
    {
      std::wstring::~wstring(v18);
      v10 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1AD,
        (unsigned int)"onecore\\base\\cbs\\mobile\\cabapi\\privlib\\cabinetapi.cpp",
        (const char *)(unsigned int)CabSelected,
        v14);
      std::wstring::~wstring(v18);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1AA,
      (unsigned int)"onecore\\base\\cbs\\mobile\\cabapi\\privlib\\cabinetapi.cpp",
      (const char *)(unsigned int)Files,
      v13);
  }
  std::vector<std::wstring>::~vector<std::wstring>((__int64)&v16);
  return v10;
}

```

## disassembly

```asm
0x180008c24  push    rbp
0x180008c26  push    rbx
0x180008c27  push    rsi
0x180008c28  push    rdi
0x180008c29  push    r14
0x180008c2b  lea     rbp, [rsp-2Fh]
0x180008c30  sub     rsp, 90h
0x180008c37  mov     [rbp+4Fh+var_70], 0FFFFFFFFFFFFFFFEh
0x180008c3f  mov     rax, cs:__security_cookie
0x180008c46  xor     rax, rsp
0x180008c49  mov     [rbp+4Fh+var_30], rax
0x180008c4d  mov     rax, r9
0x180008c50  mov     rsi, r8
0x180008c53  mov     rbx, rdx
0x180008c56  mov     r14, rcx
0x180008c59  cmp     qword ptr [rcx+10h], 0
0x180008c5e  jnz     short loc_180008C84
0x180008c60  mov     edx, 1A5h; void *
0x180008c65  mov     ebx, 80070057h
0x180008c6a  mov     rcx, [rbp+57h]; this
0x180008c6e  mov     r9d, ebx; char *
0x180008c71  lea     r8, aOnecoreBaseCbs; "onecore\\base\\cbs\\mobile\\cabapi\\pri"...
0x180008c78  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008c7d  mov     eax, ebx
0x180008c7f  jmp     loc_180008D60
0x180008c84  cmp     qword ptr [rdx+10h], 0
0x180008c89  jnz     short loc_180008C92
0x180008c8b  mov     edx, 1A6h
0x180008c90  jmp     short loc_180008C65
0x180008c92  cmp     qword ptr [r8+10h], 0
0x180008c97  jnz     short loc_180008CA0
0x180008c99  mov     edx, 1A7h
0x180008c9e  jmp     short loc_180008C65
0x180008ca0  xorps   xmm0, xmm0
0x180008ca3  movdqu  [rbp+4Fh+var_68], xmm0
0x180008ca8  mov     [rbp+4Fh+var_58], 0
0x180008cb0  mov     r9d, 1
0x180008cb6  mov     r8, rax
0x180008cb9  lea     rcx, [rbp+4Fh+var_68]
0x180008cbd  call    ?GetFiles@Utils@@SAJPEAV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@1H@Z; Utils::GetFiles(std::vector<std::wstring> *,std::wstring const &,std::wstring const &,int)
0x180008cc2  mov     edi, eax
0x180008cc4  test    eax, eax
0x180008cc6  jns     short loc_180008CE2
0x180008cc8  mov     rcx, [rbp+57h]; this
0x180008ccc  mov     r9d, eax; char *
0x180008ccf  lea     r8, aOnecoreBaseCbs; "onecore\\base\\cbs\\mobile\\cabapi\\pri"...
0x180008cd6  mov     edx, 1AAh; void *
0x180008cdb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008ce0  jmp     short loc_180008D55
0x180008ce2  mov     rax, [rbx+10h]
0x180008ce6  cmp     qword ptr [rbx+18h], 7
0x180008ceb  jbe     short loc_180008CF0
0x180008ced  mov     rbx, [rbx]
0x180008cf0  mov     [rbp+4Fh+var_80], rbx
0x180008cf4  mov     [rbp+4Fh+var_78], rax
0x180008cf8  lea     rdx, [rbp+4Fh+var_80]
0x180008cfc  lea     rcx, [rbp+4Fh+var_50]
0x180008d00  call    ?GetCanonicalUNCPath@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_zstring_view@_W@wil@@@Z; GetCanonicalUNCPath(wil::basic_zstring_view<wchar_t> const &)
0x180008d05  nop
0x180008d06  mov     eax, [rbp+4Fh+arg_20]
0x180008d09  mov     [rsp+0B0h+var_90], eax; int
0x180008d0d  lea     r9, [rbp+4Fh+var_50]
0x180008d11  mov     r8, rsi
0x180008d14  lea     rdx, [rbp+4Fh+var_68]
0x180008d18  mov     rcx, r14
0x180008d1b  call    ?CreateCabSelected@Cabinet@@SAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@3@00W4CompressionType@@@Z; Cabinet::CreateCabSelected(std::wstring const &,std::vector<std::wstring> const &,std::wstring const &,std::wstring const &,CompressionType)
0x180008d20  mov     edi, eax
0x180008d22  test    eax, eax
0x180008d24  jns     short loc_180008D4A
0x180008d26  mov     rcx, [rbp+57h]; this
0x180008d2a  mov     r9d, eax; char *
0x180008d2d  lea     r8, aOnecoreBaseCbs; "onecore\\base\\cbs\\mobile\\cabapi\\pri"...
0x180008d34  mov     edx, 1ADh; void *
0x180008d39  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008d3e  nop
0x180008d3f  lea     rcx, [rbp+4Fh+var_50]
0x180008d43  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008d48  jmp     short loc_180008D55
0x180008d4a  lea     rcx, [rbp+4Fh+var_50]
0x180008d4e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008d53  xor     edi, edi
0x180008d55  lea     rcx, [rbp+4Fh+var_68]
0x180008d59  call    ??1?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x180008d5e  mov     eax, edi
0x180008d60  mov     rcx, [rbp+4Fh+var_30]
0x180008d64  xor     rcx, rsp; StackCookie
0x180008d67  call    __security_check_cookie
0x180008d6c  add     rsp, 90h
0x180008d73  pop     r14
0x180008d75  pop     rdi
0x180008d76  pop     rsi
0x180008d77  pop     rbx
0x180008d78  pop     rbp
0x180008d79  retn
```
