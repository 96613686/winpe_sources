# Cab_CreateCabSelected

- ea: `0x180006d20`
- end: `0x180006fa3`
- name: `Cab_CreateCabSelected`
- size: `643`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, int)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x180001540`
- `0x180002e54`
- `0x180002f70`
- `0x180003648`
- `0x1800036b4`
- `0x18000553c`
- `0x180005ea0`
- `0x180006d20`
- `0x180008d80`
- `0x180008fd8`

## pseudocode

```c
__int64 __fastcall Cab_CreateCabSelected(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        int a8)
{
  __int64 v11; // rdx
  unsigned int v12; // ebx
  __int64 v13; // rdi
  __int64 v14; // r8
  __int64 v15; // r8
  int v16; // eax
  int CabSelected; // eax
  __int64 v18; // rdx
  int v19; // eax
  int v21; // [rsp+20h] [rbp-B1h]
  int v22; // [rsp+20h] [rbp-B1h]
  __int128 v23; // [rsp+30h] [rbp-A1h] BYREF
  __int64 v24; // [rsp+40h] [rbp-91h]
  __int128 v25; // [rsp+48h] [rbp-89h] BYREF
  __int64 v26; // [rsp+58h] [rbp-79h]
  _OWORD v27[2]; // [rsp+60h] [rbp-71h] BYREF
  _OWORD v28[2]; // [rsp+80h] [rbp-51h] BYREF
  wchar_t String1[8]; // [rsp+A0h] [rbp-31h] BYREF
  __int128 v30; // [rsp+B0h] [rbp-21h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+47h]

  if ( a1 )
  {
    if ( !a6 )
    {
      v11 = 395;
      goto LABEL_3;
    }
    if ( a4 )
    {
      if ( a7 )
      {
        v12 = -2147024809;
        v11 = 397;
        goto LABEL_4;
      }
      if ( a5 != a3 )
      {
        v12 = -2147024809;
        v11 = 398;
        goto LABEL_4;
      }
    }
    v13 = -1;
    *(_OWORD *)String1 = 0;
    v14 = -1;
    v30 = 0;
    do
      ++v14;
    while ( *(_WORD *)(a1 + 2 * v14) );
    std::wstring::_Construct<1,wchar_t const *>(String1, a1, v14);
    memset(v28, 0, sizeof(v28));
    v15 = -1;
    do
      ++v15;
    while ( *(_WORD *)(a6 + 2 * v15) );
    std::wstring::_Construct<1,wchar_t const *>(v28, a6, v15);
    v26 = 0;
    v25 = 0;
    v16 = StrArrayToVector(a2, a3, &v25);
    v12 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x194,
        (unsigned int)"onecore\\base\\cbs\\mobile\\cabapi\\cabapi.cpp",
        (const char *)(unsigned int)v16,
        v21);
LABEL_32:
      std::vector<std::wstring>::~vector<std::wstring>(&v25);
      std::wstring::~wstring(v28);
      std::wstring::~wstring(String1);
      return v12;
    }
    if ( a4 )
    {
      v24 = 0;
      v23 = 0;
      CabSelected = StrArrayToVector(a4, a5, &v23);
      v12 = CabSelected;
      if ( CabSelected < 0 )
      {
        v18 = 409;
LABEL_21:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v18,
          (unsigned int)"onecore\\base\\cbs\\mobile\\cabapi\\cabapi.cpp",
          (const char *)(unsigned int)CabSelected,
          v21);
        std::vector<std::wstring>::~vector<std::wstring>(&v23);
        goto LABEL_32;
      }
      CabSelected = Cabinet::CreateCabSelected(String1, (__int64 *)&v25, (__int64 *)&v23, (__int64 **)v28, a8);
      v12 = CabSelected;
      if ( CabSelected < 0 )
      {
        v18 = 417;
        goto LABEL_21;
      }
      std::vector<std::wstring>::~vector<std::wstring>(&v23);
    }
    else
    {
      v27[0] = 0;
      LOWORD(v27[0]) = 0;
      v27[1] = _mm_load_si128((const __m128i *)&_xmm);
      if ( a7 )
      {
        do
          ++v13;
        while ( *(_WORD *)(a7 + 2 * v13) );
        std::wstring::_Assign<wchar_t>(v27, a7, v13);
      }
      v19 = Cabinet::CreateCabSelected(String1, a8);
      v12 = v19;
      if ( v19 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1AC,
          (unsigned int)"onecore\\base\\cbs\\mobile\\cabapi\\cabapi.cpp",
          (const char *)(unsigned int)v19,
          v22);
        std::wstring::~wstring(v27);
        goto LABEL_32;
      }
      std::wstring::~wstring(v27);
    }
    v12 = 0;
    goto LABEL_32;
  }
  v11 = 394;
LABEL_3:
  v12 = -2147467261;
LABEL_4:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v11,
    (unsigned int)"onecore\\base\\cbs\\mobile\\cabapi\\cabapi.cpp",
    (const char *)v12,
    v21);
  return v12;
}

```

## disassembly

```asm
0x180006d20  push    rbp
0x180006d22  push    rbx
0x180006d23  push    rsi
0x180006d24  push    rdi
0x180006d25  push    r12
0x180006d27  push    r13
0x180006d29  push    r14
0x180006d2b  push    r15
0x180006d2d  lea     rbp, [rsp-7]
0x180006d32  sub     rsp, 0D8h
0x180006d39  mov     rax, cs:__security_cookie
0x180006d40  xor     rax, rsp
0x180006d43  mov     [rbp+3Fh+var_50], rax
0x180006d47  mov     rsi, [rbp+3Fh+arg_30]
0x180006d4b  xor     r13d, r13d
0x180006d4e  mov     rbx, [rbp+3Fh+arg_28]
0x180006d52  mov     r14, r9
0x180006d55  mov     r15, r8
0x180006d58  mov     r12, rdx
0x180006d5b  test    rcx, rcx
0x180006d5e  jnz     short loc_180006D82
0x180006d60  mov     edx, 18Ah; void *
0x180006d65  mov     ebx, 80004003h
0x180006d6a  mov     rcx, [rbp+47h]; this
0x180006d6e  lea     r8, aOnecoreBaseCbs_3; "onecore\\base\\cbs\\mobile\\cabapi\\cab"...
0x180006d75  mov     r9d, ebx; char *
0x180006d78  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006d7d  jmp     loc_180006F81
0x180006d82  test    rbx, rbx
0x180006d85  jnz     short loc_180006D8E
0x180006d87  mov     edx, 18Bh
0x180006d8c  jmp     short loc_180006D65
0x180006d8e  test    r14, r14
0x180006d91  jz      short loc_180006DB6
0x180006d93  test    rsi, rsi
0x180006d96  jz      short loc_180006DA4
0x180006d98  mov     ebx, 80070057h
0x180006d9d  mov     edx, 18Dh
0x180006da2  jmp     short loc_180006D6A
0x180006da4  cmp     [rbp+3Fh+arg_20], r15
0x180006da8  jz      short loc_180006DB6
0x180006daa  mov     ebx, 80070057h
0x180006daf  mov     edx, 18Eh
0x180006db4  jmp     short loc_180006D6A
0x180006db6  xorps   xmm0, xmm0
0x180006db9  xorps   xmm1, xmm1
0x180006dbc  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180006dc0  movups  xmmword ptr [rbp+3Fh+String1], xmm0
0x180006dc4  mov     r8, rdi
0x180006dc7  movdqu  [rbp+3Fh+var_60], xmm1
0x180006dcc  inc     r8
0x180006dcf  cmp     [rcx+r8*2], r13w
0x180006dd4  jnz     short loc_180006DCC
0x180006dd6  mov     rdx, rcx
0x180006dd9  lea     rcx, [rbp+3Fh+String1]
0x180006ddd  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180006de2  xorps   xmm0, xmm0
0x180006de5  xorps   xmm1, xmm1
0x180006de8  movups  [rbp+3Fh+var_90], xmm0
0x180006dec  mov     r8, rdi
0x180006def  movdqu  [rbp+3Fh+var_80], xmm1
0x180006df4  inc     r8
0x180006df7  cmp     [rbx+r8*2], r13w
0x180006dfc  jnz     short loc_180006DF4
0x180006dfe  mov     rdx, rbx
0x180006e01  lea     rcx, [rbp+3Fh+var_90]
0x180006e05  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180006e0a  xorps   xmm0, xmm0
0x180006e0d  mov     [rbp+3Fh+var_B8], r13
0x180006e11  lea     r8, [rsp+110h+var_C8]
0x180006e16  mov     rdx, r15
0x180006e19  mov     rcx, r12
0x180006e1c  movdqu  [rsp+110h+var_C8], xmm0
0x180006e22  call    StrArrayToVector
0x180006e27  mov     ebx, eax
0x180006e29  test    eax, eax
0x180006e2b  jns     short loc_180006E4A
0x180006e2d  mov     rcx, [rbp+47h]; this
0x180006e31  lea     r8, aOnecoreBaseCbs_3; "onecore\\base\\cbs\\mobile\\cabapi\\cab"...
0x180006e38  mov     r9d, eax; char *
0x180006e3b  mov     edx, 194h; void *
0x180006e40  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006e45  jmp     loc_180006F65
0x180006e4a  xorps   xmm0, xmm0
0x180006e4d  test    r14, r14
0x180006e50  jz      loc_180006EDC
0x180006e56  mov     rdx, [rbp+3Fh+arg_20]
0x180006e5a  lea     r8, [rsp+110h+var_E0]
0x180006e5f  mov     rcx, r14
0x180006e62  mov     [rsp+110h+var_D0], r13
0x180006e67  movdqu  [rsp+110h+var_E0], xmm0
0x180006e6d  call    StrArrayToVector
0x180006e72  mov     ebx, eax
0x180006e74  test    eax, eax
0x180006e76  jns     short loc_180006E9F
0x180006e78  mov     edx, 199h; void *
0x180006e7d  mov     rcx, [rbp+47h]; this
0x180006e81  lea     r8, aOnecoreBaseCbs_3; "onecore\\base\\cbs\\mobile\\cabapi\\cab"...
0x180006e88  mov     r9d, eax; char *
0x180006e8b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006e90  lea     rcx, [rsp+110h+var_E0]
0x180006e95  call    ??1?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x180006e9a  jmp     loc_180006F65
0x180006e9f  mov     eax, [rbp+3Fh+arg_38]
0x180006ea5  lea     r9, [rbp+3Fh+var_90]
0x180006ea9  lea     r8, [rsp+110h+var_E0]
0x180006eae  mov     [rsp+110h+var_F0], eax; int
0x180006eb2  lea     rdx, [rsp+110h+var_C8]
0x180006eb7  lea     rcx, [rbp+3Fh+String1]; String1
0x180006ebb  call    ?CreateCabSelected@Cabinet@@SAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@3@10W4CompressionType@@@Z; Cabinet::CreateCabSelected(std::wstring const &,std::vector<std::wstring> const &,std::vector<std::wstring> const &,std::wstring const &,CompressionType)
0x180006ec0  mov     ebx, eax
0x180006ec2  test    eax, eax
0x180006ec4  jns     short loc_180006ECD
0x180006ec6  mov     edx, 1A1h
0x180006ecb  jmp     short loc_180006E7D
0x180006ecd  lea     rcx, [rsp+110h+var_E0]
0x180006ed2  call    ??1?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x180006ed7  jmp     loc_180006F62
0x180006edc  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180006ee4  movups  [rbp+3Fh+var_B0], xmm0
0x180006ee8  mov     word ptr [rbp+3Fh+var_B0], r13w
0x180006eed  movdqu  [rbp+3Fh+var_A0], xmm1
0x180006ef2  test    rsi, rsi
0x180006ef5  jz      short loc_180006F10
0x180006ef7  inc     rdi
0x180006efa  cmp     [rsi+rdi*2], r13w
0x180006eff  jnz     short loc_180006EF7
0x180006f01  mov     r8, rdi
0x180006f04  lea     rcx, [rbp+3Fh+var_B0]
0x180006f08  mov     rdx, rsi
0x180006f0b  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x180006f10  mov     eax, [rbp+3Fh+arg_38]
0x180006f16  lea     r9, [rbp+3Fh+var_B0]
0x180006f1a  lea     r8, [rbp+3Fh+var_90]
0x180006f1e  mov     [rsp+110h+var_F0], eax; int
0x180006f22  lea     rdx, [rsp+110h+var_C8]
0x180006f27  lea     rcx, [rbp+3Fh+String1]
0x180006f2b  call    ?CreateCabSelected@Cabinet@@SAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@3@00W4CompressionType@@@Z; Cabinet::CreateCabSelected(std::wstring const &,std::vector<std::wstring> const &,std::wstring const &,std::wstring const &,CompressionType)
0x180006f30  mov     ebx, eax
0x180006f32  test    eax, eax
0x180006f34  jns     short loc_180006F59
0x180006f36  mov     rcx, [rbp+47h]; this
0x180006f3a  lea     r8, aOnecoreBaseCbs_3; "onecore\\base\\cbs\\mobile\\cabapi\\cab"...
0x180006f41  mov     r9d, eax; char *
0x180006f44  mov     edx, 1ACh; void *
0x180006f49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006f4e  lea     rcx, [rbp+3Fh+var_B0]
0x180006f52  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180006f57  jmp     short loc_180006F65
0x180006f59  lea     rcx, [rbp+3Fh+var_B0]
0x180006f5d  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180006f62  mov     ebx, r13d
0x180006f65  lea     rcx, [rsp+110h+var_C8]
0x180006f6a  call    ??1?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x180006f6f  lea     rcx, [rbp+3Fh+var_90]
0x180006f73  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180006f78  lea     rcx, [rbp+3Fh+String1]
0x180006f7c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180006f81  mov     eax, ebx
0x180006f83  mov     rcx, [rbp+3Fh+var_50]
0x180006f87  xor     rcx, rsp; StackCookie
0x180006f8a  call    __security_check_cookie
0x180006f8f  add     rsp, 0D8h
0x180006f96  pop     r15
0x180006f98  pop     r14
0x180006f9a  pop     r13
0x180006f9c  pop     r12
0x180006f9e  pop     rdi
0x180006f9f  pop     rsi
0x180006fa0  pop     rbx
0x180006fa1  pop     rbp
0x180006fa2  retn
```
