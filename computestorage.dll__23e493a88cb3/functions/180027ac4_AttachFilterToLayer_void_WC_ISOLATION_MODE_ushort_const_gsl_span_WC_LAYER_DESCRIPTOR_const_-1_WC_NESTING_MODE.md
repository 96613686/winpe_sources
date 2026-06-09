# AttachFilterToLayer(void *,_WC_ISOLATION_MODE,ushort const *,gsl::span<_WC_LAYER_DESCRIPTOR const,-1>,_WC_NESTING_MODE)

- ea: `0x180027ac4`
- end: `0x180027c5d`
- name: `?AttachFilterToLayer@@YAXPEAXW4_WC_ISOLATION_MODE@@PEBGV?$span@$$CBU_WC_LAYER_DESCRIPTOR@@$0?0@gsl@@W4_WC_NESTING_MODE@@@Z`
- size: `409`
- prototype: `__int64 __fastcall(__int64, __int64, const WCHAR *, _QWORD *)`
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180009ad8`
- `0x18000e530`

## callees

- `0x180002690`
- `0x1800026b4`
- `0x180003bc1`
- `0x180008fac`
- `0x1800092d8`
- `0x18000a578`
- `0x1800127bc`
- `0x180013714`
- `0x180013990`
- `0x180013d30`
- `0x180027a50`
- `0x180027ac4`

## import_xrefs

- `wc_storage!WcAttachFilterEx` at `0x180027bf6`
- `wc_storage!WcAttachFilterEx` at `0x180027bf6`

## string_xrefs

- `0x180027c39`: `onecore\vm\compute\shared\storage\layerutilities.cpp`

## pseudocode

```c
__int64 __fastcall AttachFilterToLayer(__int64 a1, __int64 a2, const WCHAR *a3, _QWORD *a4)
{
  gsl::details *v5; // rcx
  char *v6; // rsi
  signed __int64 v7; // rdi
  unsigned __int64 v8; // rbx
  size_t v9; // rbx
  _QWORD *v10; // rax
  void *v11; // rax
  void *v12; // rcx
  char **v13; // r8
  int v14; // eax
  __int128 v16; // [rsp+30h] [rbp-21h] BYREF
  char *v17; // [rsp+40h] [rbp-11h]
  char **v18; // [rsp+48h] [rbp-9h] BYREF
  char *Src[4]; // [rsp+50h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+57h]

  Vml::CombineFilePath(Src, a3, L".\\");
  v6 = (char *)a4[1];
  v7 = 32LL * *a4;
  v16 = 0;
  v17 = 0;
  if ( v6 > &v6[v7] )
  {
    gsl::details::terminate(v5);
    __debugbreak();
  }
  v8 = v7 >> 5;
  if ( v7 >> 5 )
  {
    if ( v8 > 0x7FFFFFFFFFFFFFFLL )
      std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Xlength();
    v9 = 32 * v8;
    if ( v9 )
    {
      if ( v9 < 0x1000 )
      {
        v10 = operator new(v9);
      }
      else
      {
        if ( v9 + 39 < v9 )
          __scrt_throw_std_bad_array_new_length();
        v11 = operator new(v9 + 39);
        v12 = v11;
        if ( !v11 )
          __fastfail(5u);
        v10 = (_QWORD *)(((unsigned __int64)v11 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *(v10 - 1) = v12;
      }
    }
    else
    {
      v10 = 0;
    }
    *(_QWORD *)&v16 = v10;
    v17 = (char *)&v10[v9 / 8];
    memmove_0(v10, v6, v7);
    *((_QWORD *)&v16 + 1) = v17;
    v18 = 0;
    std::_Tidy_guard<std::vector<_WC_LAYER_DESCRIPTOR>>::~_Tidy_guard<std::vector<_WC_LAYER_DESCRIPTOR>>(&v18);
  }
  *(_DWORD *)(*((_QWORD *)&v16 + 1) - 16LL) |= 2u;
  v13 = Src;
  if ( Src[3] > (char *)7 )
    v13 = (char **)Src[0];
  v14 = WcAttachFilterEx(0, 0, v13);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6B,
      (unsigned int)"onecore\\vm\\compute\\shared\\storage\\layerutilities.cpp",
      (const char *)(unsigned int)v14,
      (__int64)(*((_QWORD *)&v16 + 1) - v16) >> 5);
  std::vector<_WC_LAYER_DESCRIPTOR>::~vector<_WC_LAYER_DESCRIPTOR>((char **)&v16);
  return std::wstring::~wstring(Src);
}

```

## disassembly

```asm
0x180027ac4  push    rbp
0x180027ac6  push    rbx
0x180027ac7  push    rsi
0x180027ac8  push    rdi
0x180027ac9  lea     rbp, [rsp-37h]
0x180027ace  sub     rsp, 88h
0x180027ad5  mov     rax, cs:__security_cookie
0x180027adc  xor     rax, rsp
0x180027adf  mov     [rbp+4Fh+var_30], rax
0x180027ae3  mov     rbx, r9
0x180027ae6  mov     rdx, r8; pszPathIn
0x180027ae9  lea     r8, pszMore; ".\\"
0x180027af0  lea     rcx, [rbp+4Fh+Src]; Src
0x180027af4  call    ?CombineFilePath@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; Vml::CombineFilePath(ushort const *,ushort const *)
0x180027af9  nop
0x180027afa  xorps   xmm0, xmm0
0x180027afd  xor     eax, eax
0x180027aff  mov     rsi, [rbx+8]
0x180027b03  mov     rdi, [rbx]
0x180027b06  shl     rdi, 5
0x180027b0a  movdqu  [rbp+4Fh+var_70], xmm0
0x180027b0f  mov     [rbp+4Fh+var_60], rax
0x180027b13  lea     rax, [rdi+rsi]
0x180027b17  cmp     rsi, rax
0x180027b1a  ja      loc_180027C4B
0x180027b20  mov     rbx, rdi
0x180027b23  sar     rbx, 5
0x180027b27  test    rbx, rbx
0x180027b2a  jz      loc_180027BC1
0x180027b30  mov     rax, 7FFFFFFFFFFFFFFh
0x180027b3a  cmp     rbx, rax
0x180027b3d  ja      loc_180027C51
0x180027b43  shl     rbx, 5
0x180027b47  test    rbx, rbx
0x180027b4a  jnz     short loc_180027B50
0x180027b4c  xor     eax, eax
0x180027b4e  jmp     short loc_180027B8E
0x180027b50  cmp     rbx, 1000h
0x180027b57  jb      short loc_180027B86
0x180027b59  lea     rcx, [rbx+27h]; Size
0x180027b5d  cmp     rcx, rbx
0x180027b60  jbe     loc_180027C57
0x180027b66  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180027b6b  mov     rcx, rax
0x180027b6e  test    rax, rax
0x180027b71  jnz     short loc_180027B78
0x180027b73  lea     ecx, [rax+5]
0x180027b76  int     29h; Win8: RtlFailFast(ecx)
0x180027b78  add     rax, 27h ; '''
0x180027b7c  and     rax, 0FFFFFFFFFFFFFFE0h
0x180027b80  mov     [rax-8], rcx
0x180027b84  jmp     short loc_180027B8E
0x180027b86  mov     rcx, rbx; Size
0x180027b89  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180027b8e  mov     qword ptr [rbp+4Fh+var_70], rax
0x180027b92  mov     qword ptr [rbp+4Fh+var_70+8], rax
0x180027b96  add     rbx, rax
0x180027b99  mov     [rbp+4Fh+var_60], rbx
0x180027b9d  mov     r8, rdi; Size
0x180027ba0  mov     rdx, rsi; Src
0x180027ba3  mov     rcx, rax; void *
0x180027ba6  call    memmove_0
0x180027bab  mov     qword ptr [rbp+4Fh+var_70+8], rbx
0x180027baf  mov     [rbp+4Fh+var_58], 0
0x180027bb7  lea     rcx, [rbp+4Fh+var_58]
0x180027bbb  call    ??1?$_Tidy_guard@V?$vector@U_WC_LAYER_DESCRIPTOR@@V?$allocator@U_WC_LAYER_DESCRIPTOR@@@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<_WC_LAYER_DESCRIPTOR>>::~_Tidy_guard<std::vector<_WC_LAYER_DESCRIPTOR>>(void)
0x180027bc0  nop
0x180027bc1  mov     rax, qword ptr [rbp+4Fh+var_70+8]
0x180027bc5  or      dword ptr [rax-10h], 2
0x180027bc9  mov     r9, qword ptr [rbp+4Fh+var_70]
0x180027bcd  mov     rax, qword ptr [rbp+4Fh+var_70+8]
0x180027bd1  sub     rax, r9
0x180027bd4  sar     rax, 5
0x180027bd8  lea     r8, [rbp+4Fh+Src]
0x180027bdc  cmp     [rbp+4Fh+var_38], 7
0x180027be1  cmova   r8, [rbp+4Fh+Src]
0x180027be6  mov     [rsp+0A0h+var_78], 0
0x180027bee  mov     [rsp+0A0h+var_80], eax; int
0x180027bf2  xor     edx, edx
0x180027bf4  xor     ecx, ecx
0x180027bf6  call    cs:__imp_WcAttachFilterEx
0x180027bfd  nop     dword ptr [rax+rax+00h]
0x180027c02  mov     rcx, [rbp+57h]; this
0x180027c06  test    eax, eax
0x180027c08  js      short loc_180027C36
0x180027c0a  lea     rcx, [rbp+4Fh+var_70]
0x180027c0e  call    ??1?$vector@U_WC_LAYER_DESCRIPTOR@@V?$allocator@U_WC_LAYER_DESCRIPTOR@@@std@@@std@@QEAA@XZ; std::vector<_WC_LAYER_DESCRIPTOR>::~vector<_WC_LAYER_DESCRIPTOR>(void)
0x180027c13  nop
0x180027c14  lea     rcx, [rbp+4Fh+Src]
0x180027c18  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180027c1d  mov     rcx, [rbp+4Fh+var_30]
0x180027c21  xor     rcx, rsp; StackCookie
0x180027c24  call    __security_check_cookie
0x180027c29  add     rsp, 88h
0x180027c30  pop     rdi
0x180027c31  pop     rsi
0x180027c32  pop     rbx
0x180027c33  pop     rbp
0x180027c34  retn
0x180027c36  mov     r9d, eax; char *
0x180027c39  lea     r8, aOnecoreVmCompu_2; "onecore\\vm\\compute\\shared\\storage\\"...
0x180027c40  mov     edx, 6Bh ; 'k'; void *
0x180027c45  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180027c4b  call    ?terminate@details@gsl@@YAXXZ; gsl::details::terminate(void)
0x180027c50  int     3; Trap to Debugger
0x180027c51  call    ?_Xlength@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@CAXXZ; std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>::_Xlength(void)
0x180027c57  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
