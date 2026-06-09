# Cabinet::CreateCabSelected(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,CompressionType)

- ea: `0x180008d80`
- end: `0x180008fd0`
- name: `?CreateCabSelected@Cabinet@@SAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@3@00W4CompressionType@@@Z`
- size: `592`
- prototype: `__int64 __fastcall(wchar_t *String1, __int64 *, __int64 **, __int64, int)`
- caller_count: `2`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180006d20`
- `0x180008c24`

## callees

- `0x180001540`
- `0x180001f82`
- `0x180002e54`
- `0x180002f70`
- `0x180003648`
- `0x1800036b4`
- `0x18000553c`
- `0x180007b64`
- `0x180007fd0`
- `0x180008414`
- `0x180008d80`
- `0x180008fd8`
- `0x18000a74c`

## pseudocode

```c
__int64 __fastcall Cabinet::CreateCabSelected(wchar_t *String1, __int64 *a2, __int64 **a3, __int64 a4, int a5)
{
  __int64 v8; // rbx
  __int64 v9; // rsi
  unsigned __int64 v10; // r8
  wchar_t *v11; // rdx
  size_t v12; // r8
  const wchar_t *v13; // rdx
  const wchar_t *v14; // rcx
  unsigned __int64 v15; // rcx
  unsigned __int64 v16; // r8
  wchar_t **v17; // rax
  int CabSelected; // eax
  unsigned int v19; // ebx
  __int64 v20; // r9
  __int64 v21; // rdx
  int v23; // [rsp+20h] [rbp-81h]
  _OWORD v24[2]; // [rsp+38h] [rbp-69h] BYREF
  __int64 v25; // [rsp+58h] [rbp-49h]
  wchar_t *String1a[2]; // [rsp+60h] [rbp-41h] BYREF
  unsigned __int64 v27; // [rsp+70h] [rbp-31h]
  unsigned __int64 v28; // [rsp+78h] [rbp-29h]
  __int128 v29; // [rsp+80h] [rbp-21h] BYREF
  __int64 v30; // [rsp+90h] [rbp-11h]
  __int128 v31; // [rsp+98h] [rbp-9h] BYREF
  __int64 v32; // [rsp+A8h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+57h]

  v25 = -2;
  *(_OWORD *)String1a = 0;
  v27 = 0;
  v28 = 7;
  LOWORD(String1a[0]) = 0;
  v31 = 0;
  v32 = 0;
  v29 = 0;
  v30 = 0;
  v8 = *a2;
  v9 = a2[1];
  while ( v8 != v9 )
  {
    v10 = *(_QWORD *)(v8 + 16);
    if ( !v10 )
    {
      v21 = 480;
LABEL_34:
      v19 = -2147024809;
      v20 = 2147942487LL;
LABEL_35:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v21,
        (unsigned int)"onecore\\base\\cbs\\mobile\\cabapi\\privlib\\cabinetapi.cpp",
        (const char *)v20,
        v23);
      std::vector<std::wstring>::~vector<std::wstring>((__int64)&v29);
      std::vector<std::wstring>::~vector<std::wstring>((__int64)&v31);
      std::wstring::~wstring((char **)String1a);
      return v19;
    }
    if ( String1a != (wchar_t **)v8 )
    {
      if ( *(_QWORD *)(v8 + 24) <= 7u )
        v11 = (wchar_t *)v8;
      else
        v11 = *(wchar_t **)v8;
      std::wstring::_Assign<wchar_t>((void **)String1a, v11, v10);
    }
    v12 = *(_QWORD *)(a4 + 16);
    if ( v12 )
    {
      if ( *(_QWORD *)(a4 + 24) <= 7u )
        v13 = (const wchar_t *)a4;
      else
        v13 = *(const wchar_t **)a4;
      v14 = (const wchar_t *)String1a;
      if ( v28 > 7 )
        v14 = String1a[0];
      if ( !wcsnicmp(v14, v13, v12) )
      {
        v15 = *(_QWORD *)(a4 + 16);
        memset(v24, 0, sizeof(v24));
        if ( v27 < v15 )
          std::_String_val<std::_Simple_types<wchar_t>>::_Xran();
        v16 = -1;
        if ( v27 - v15 != -1 )
          v16 = v27 - v15;
        v17 = String1a;
        if ( v28 > 7 )
          v17 = (wchar_t **)String1a[0];
        std::wstring::_Construct<1,wchar_t const *>((__int64)v24, (char *)v17 + 2 * v15, v16);
        std::wstring::operator=((char **)String1a, (__int64)v24);
        std::wstring::~wstring((char **)v24);
      }
    }
    if ( !v27 )
    {
      v21 = 490;
      goto LABEL_34;
    }
    if ( *((_QWORD *)&v31 + 1) == v32 )
    {
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>((__int64 *)&v31, *((__int64 *)&v31 + 1), v8);
    }
    else
    {
      std::wstring::wstring(*((__int64 *)&v31 + 1), v8);
      *((_QWORD *)&v31 + 1) += 32LL;
    }
    if ( *((_QWORD *)&v29 + 1) == v30 )
    {
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(
        (__int64 *)&v29,
        *((__int64 *)&v29 + 1),
        (__int64)String1a);
    }
    else
    {
      std::wstring::wstring(*((__int64 *)&v29 + 1), (__int64)String1a);
      *((_QWORD *)&v29 + 1) += 32LL;
    }
    v8 += 32;
  }
  CabSelected = Cabinet::CreateCabSelected(String1, (__int64 *)&v31, (__int64 *)&v29, a3, a5);
  v19 = CabSelected;
  if ( CabSelected < 0 )
  {
    v20 = (unsigned int)CabSelected;
    v21 = 502;
    goto LABEL_35;
  }
  std::vector<std::wstring>::~vector<std::wstring>((__int64)&v29);
  std::vector<std::wstring>::~vector<std::wstring>((__int64)&v31);
  std::wstring::~wstring((char **)String1a);
  return 0;
}

```

## disassembly

```asm
0x180008d80  push    rbp
0x180008d82  push    rbx
0x180008d83  push    rsi
0x180008d84  push    rdi
0x180008d85  push    r14
0x180008d87  push    r15
0x180008d89  lea     rbp, [rsp-27h]
0x180008d8e  sub     rsp, 0C8h
0x180008d95  mov     [rbp+4Fh+var_98], 0FFFFFFFFFFFFFFFEh
0x180008d9d  mov     rax, cs:__security_cookie
0x180008da4  xor     rax, rsp
0x180008da7  mov     [rbp+4Fh+var_40], rax
0x180008dab  mov     rdi, r9
0x180008dae  mov     r15, r8
0x180008db1  mov     r14, rcx
0x180008db4  xorps   xmm0, xmm0
0x180008db7  movups  xmmword ptr [rbp+4Fh+String1], xmm0
0x180008dbb  mov     [rbp+4Fh+var_80], 0
0x180008dc3  mov     [rbp+4Fh+var_78], 7
0x180008dcb  xor     eax, eax
0x180008dcd  mov     word ptr [rbp+4Fh+String1], ax
0x180008dd1  movdqu  [rbp+4Fh+var_58], xmm0
0x180008dd6  mov     [rbp+4Fh+var_48], rax
0x180008dda  movdqu  [rbp+4Fh+var_70], xmm0
0x180008ddf  mov     [rbp+4Fh+var_60], rax
0x180008de3  mov     rbx, [rdx]
0x180008de6  mov     rsi, [rdx+8]
0x180008dea  jmp     loc_180008F16
0x180008def  mov     r8, [rbx+10h]
0x180008df3  test    r8, r8
0x180008df6  jz      loc_180008F50
0x180008dfc  lea     rax, [rbp+4Fh+String1]
0x180008e00  cmp     rax, rbx
0x180008e03  jz      short loc_180008E1D
0x180008e05  cmp     qword ptr [rbx+18h], 7
0x180008e0a  jbe     short loc_180008E11
0x180008e0c  mov     rdx, [rbx]
0x180008e0f  jmp     short loc_180008E14
0x180008e11  mov     rdx, rbx
0x180008e14  lea     rcx, [rbp+4Fh+String1]
0x180008e18  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x180008e1d  mov     r8, [rdi+10h]; MaxCount
0x180008e21  test    r8, r8
0x180008e24  jz      loc_180008EAF
0x180008e2a  cmp     qword ptr [rdi+18h], 7
0x180008e2f  jbe     short loc_180008E36
0x180008e31  mov     rdx, [rdi]
0x180008e34  jmp     short loc_180008E39
0x180008e36  mov     rdx, rdi; String2
0x180008e39  lea     rcx, [rbp+4Fh+String1]
0x180008e3d  cmp     [rbp+4Fh+var_78], 7
0x180008e42  cmova   rcx, [rbp+4Fh+String1]; String1
0x180008e47  call    _wcsnicmp
0x180008e4c  test    eax, eax
0x180008e4e  jnz     short loc_180008EAF
0x180008e50  mov     rcx, [rdi+10h]
0x180008e54  xorps   xmm0, xmm0
0x180008e57  movups  [rbp+4Fh+var_B8], xmm0
0x180008e5b  xorps   xmm1, xmm1
0x180008e5e  movdqu  [rbp+4Fh+var_A8], xmm1
0x180008e63  mov     rax, [rbp+4Fh+var_80]
0x180008e67  cmp     rax, rcx
0x180008e6a  jb      loc_180008FCA
0x180008e70  sub     rax, rcx
0x180008e73  or      r8, 0FFFFFFFFFFFFFFFFh
0x180008e77  cmp     rax, r8
0x180008e7a  cmovb   r8, rax
0x180008e7e  lea     rax, [rbp+4Fh+String1]
0x180008e82  cmp     [rbp+4Fh+var_78], 7
0x180008e87  cmova   rax, [rbp+4Fh+String1]
0x180008e8c  lea     rdx, [rax+rcx*2]
0x180008e90  lea     rcx, [rbp+4Fh+var_B8]
0x180008e94  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180008e99  lea     rdx, [rbp+4Fh+var_B8]
0x180008e9d  lea     rcx, [rbp+4Fh+String1]
0x180008ea1  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180008ea6  lea     rcx, [rbp+4Fh+var_B8]
0x180008eaa  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008eaf  cmp     [rbp+4Fh+var_80], 0
0x180008eb4  jz      loc_180008F49
0x180008eba  mov     rax, qword ptr [rbp+4Fh+var_58+8]
0x180008ebe  cmp     rax, [rbp+4Fh+var_48]
0x180008ec2  jz      short loc_180008ED6
0x180008ec4  mov     rdx, rbx
0x180008ec7  mov     rcx, rax
0x180008eca  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180008ecf  add     qword ptr [rbp+4Fh+var_58+8], 20h ; ' '
0x180008ed4  jmp     short loc_180008EE5
0x180008ed6  mov     r8, rbx
0x180008ed9  mov     rdx, rax
0x180008edc  lea     rcx, [rbp+4Fh+var_58]
0x180008ee0  call    ??$_Emplace_reallocate@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x180008ee5  mov     rax, qword ptr [rbp+4Fh+var_70+8]
0x180008ee9  cmp     rax, [rbp+4Fh+var_60]
0x180008eed  jz      short loc_180008F02
0x180008eef  lea     rdx, [rbp+4Fh+String1]
0x180008ef3  mov     rcx, rax
0x180008ef6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180008efb  add     qword ptr [rbp+4Fh+var_70+8], 20h ; ' '
0x180008f00  jmp     short loc_180008F12
0x180008f02  lea     r8, [rbp+4Fh+String1]
0x180008f06  mov     rdx, rax
0x180008f09  lea     rcx, [rbp+4Fh+var_70]
0x180008f0d  call    ??$_Emplace_reallocate@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x180008f12  add     rbx, 20h ; ' '
0x180008f16  cmp     rbx, rsi
0x180008f19  jnz     loc_180008DEF
0x180008f1f  mov     eax, [rbp+4Fh+arg_20]
0x180008f22  mov     [rsp+0F0h+var_D0], eax; int
0x180008f26  mov     r9, r15
0x180008f29  lea     r8, [rbp+4Fh+var_70]
0x180008f2d  lea     rdx, [rbp+4Fh+var_58]
0x180008f31  mov     rcx, r14; String1
0x180008f34  call    ?CreateCabSelected@Cabinet@@SAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@3@10W4CompressionType@@@Z; Cabinet::CreateCabSelected(std::wstring const &,std::vector<std::wstring> const &,std::vector<std::wstring> const &,std::wstring const &,CompressionType)
0x180008f39  mov     ebx, eax
0x180008f3b  test    eax, eax
0x180008f3d  jns     short loc_180008F8F
0x180008f3f  mov     r9d, eax
0x180008f42  mov     edx, 1F6h
0x180008f47  jmp     short loc_180008F5D
0x180008f49  mov     edx, 1EAh
0x180008f4e  jmp     short loc_180008F55
0x180008f50  mov     edx, 1E0h; void *
0x180008f55  mov     ebx, 80070057h
0x180008f5a  mov     r9d, ebx; char *
0x180008f5d  lea     r8, aOnecoreBaseCbs; "onecore\\base\\cbs\\mobile\\cabapi\\pri"...
0x180008f64  mov     rcx, [rbp+57h]; this
0x180008f68  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008f6d  nop
0x180008f6e  lea     rcx, [rbp+4Fh+var_70]
0x180008f72  call    ??1?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x180008f77  nop
0x180008f78  lea     rcx, [rbp+4Fh+var_58]
0x180008f7c  call    ??1?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x180008f81  nop
0x180008f82  lea     rcx, [rbp+4Fh+String1]
0x180008f86  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008f8b  mov     eax, ebx
0x180008f8d  jmp     short loc_180008FAE
0x180008f8f  lea     rcx, [rbp+4Fh+var_70]
0x180008f93  call    ??1?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x180008f98  nop
0x180008f99  lea     rcx, [rbp+4Fh+var_58]
0x180008f9d  call    ??1?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x180008fa2  nop
0x180008fa3  lea     rcx, [rbp+4Fh+String1]
0x180008fa7  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008fac  xor     eax, eax
0x180008fae  mov     rcx, [rbp+4Fh+var_40]
0x180008fb2  xor     rcx, rsp; StackCookie
0x180008fb5  call    __security_check_cookie
0x180008fba  add     rsp, 0C8h
0x180008fc1  pop     r15
0x180008fc3  pop     r14
0x180008fc5  pop     rdi
0x180008fc6  pop     rsi
0x180008fc7  pop     rbx
0x180008fc8  pop     rbp
0x180008fc9  retn
0x180008fca  call    ?_Xran@?$_String_val@U?$_Simple_types@_W@std@@@std@@SAXXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Xran(void)
```
