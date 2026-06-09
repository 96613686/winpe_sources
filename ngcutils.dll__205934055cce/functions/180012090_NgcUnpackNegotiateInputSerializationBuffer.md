# NgcUnpackNegotiateInputSerializationBuffer

- ea: `0x180012090`
- end: `0x180012398`
- name: `NgcUnpackNegotiateInputSerializationBuffer`
- size: `776`
- prototype: `__int64 __fastcall(__int64, unsigned int, int, const unsigned __int16 *, unsigned __int16 *, _DWORD *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003080`
- `0x18000a5b4`
- `0x18000ce74`
- `0x180012090`
- `0x180013b3c`
- `0x1800567f8`

## string_xrefs

- `0x1800120d7`: `onecore\ds\security\ngc\utils\common\dll\entrypoints.cpp`
- `0x180012104`: `onecore\ds\security\ngc\utils\common\dll\entrypoints.cpp`
- `0x180012131`: `onecore\ds\security\ngc\utils\common\dll\entrypoints.cpp`
- `0x18001215e`: `onecore\ds\security\ngc\utils\common\dll\entrypoints.cpp`
- `0x180012249`: `onecore\ds\security\ngc\utils\common\dll\entrypoints.cpp`
- `0x1800122b6`: `onecore\ds\security\ngc\utils\common\dll\entrypoints.cpp`
- `0x180012322`: `onecore\ds\security\ngc\utils\common\dll\entrypoints.cpp`

## pseudocode

```c
__int64 __fastcall NgcUnpackNegotiateInputSerializationBuffer(
        __int64 a1,
        unsigned int a2,
        int a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        _DWORD *a6)
{
  const char *v7; // r9
  __int64 result; // rax
  int v9; // eax
  unsigned __int16 **v10; // r8
  unsigned int v11; // r14d
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 v15; // r8
  NgcUtils *v16; // rcx
  int v17; // eax
  unsigned __int16 **v18; // r8
  unsigned int v19; // ebx
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // rdx
  __int64 v23; // r8
  NgcUtils *v24; // rcx
  int v25; // eax
  __int64 v26; // rdx
  __int64 v27; // r8
  unsigned int v28; // ebx
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // rdx
  __int64 v34; // r8
  int v35; // [rsp+20h] [rbp-D8h] BYREF
  bool v36; // [rsp+28h] [rbp-D0h] BYREF
  unsigned int v37; // [rsp+30h] [rbp-C8h] BYREF
  __int64 v38; // [rsp+38h] [rbp-C0h] BYREF
  NgcUtils **v39; // [rsp+40h] [rbp-B8h] BYREF
  NgcUtils **v40; // [rsp+48h] [rbp-B0h] BYREF
  int *v41; // [rsp+50h] [rbp-A8h] BYREF
  _QWORD v42[6]; // [rsp+58h] [rbp-A0h] BYREF
  NgcUtils *v43[2]; // [rsp+88h] [rbp-70h] BYREF
  __m128i v44; // [rsp+98h] [rbp-60h]
  NgcUtils *v45[2]; // [rsp+A8h] [rbp-50h] BYREF
  __m128i si128; // [rsp+B8h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  if ( a1 )
  {
    if ( a4 )
    {
      if ( a5 )
      {
        if ( a6 )
        {
          *(_OWORD *)v45 = 0;
          si128 = _mm_load_si128((const __m128i *)&_xmm);
          LOWORD(v45[0]) = 0;
          *(_OWORD *)v43 = 0;
          v44 = si128;
          LOWORD(v43[0]) = 0;
          LOBYTE(v35) = 0;
          v36 = a3 != 0;
          v41 = &v35;
          v40 = v43;
          v39 = v45;
          v37 = a2;
          v38 = a1;
          v42[0] = &v38;
          v42[1] = &v37;
          v42[2] = &v36;
          v42[3] = &v39;
          v42[4] = &v40;
          v42[5] = &v41;
          v9 = HResultErrorContract__lambda_512e99141b121238e125c8e957ea4058_(v42);
          v11 = v9;
          if ( v9 >= 0 )
          {
            *(_QWORD *)a4 = 0;
            v16 = (NgcUtils *)v45;
            if ( si128.m128i_i64[1] > 7uLL )
              v16 = v45[0];
            v17 = NgcUtils::DuplicateString(v16, a4, v10);
            v19 = v17;
            if ( v17 >= 0 )
            {
              *(_QWORD *)a5 = 0;
              v24 = (NgcUtils *)v43;
              if ( v44.m128i_i64[1] > 7uLL )
                v24 = v43[0];
              v25 = NgcUtils::DuplicateString(v24, a5, v18);
              v28 = v25;
              if ( v25 >= 0 )
              {
                *a6 = (unsigned __int8)v35;
                std::wstring::~wstring(v43, v26, v27);
                std::wstring::~wstring(v45, v33, v34);
                result = 0;
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x9C,
                  (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\dll\\entrypoints.cpp",
                  (const char *)(unsigned int)v25,
                  v35);
                std::wstring::~wstring(v43, v29, v30);
                std::wstring::~wstring(v45, v31, v32);
                result = v28;
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x99,
                (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\dll\\entrypoints.cpp",
                (const char *)(unsigned int)v17,
                v35);
              std::wstring::~wstring(v43, v20, v21);
              std::wstring::~wstring(v45, v22, v23);
              result = v19;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x96,
              (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\dll\\entrypoints.cpp",
              (const char *)(unsigned int)v9,
              v35);
            std::wstring::~wstring(v43, v12, v13);
            std::wstring::~wstring(v45, v14, v15);
            result = v11;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x90,
            (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\dll\\entrypoints.cpp",
            (const char *)0x80004003LL,
            v35);
          result = 2147500035LL;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x8F,
          (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\dll\\entrypoints.cpp",
          (const char *)0x80004003LL,
          v35);
        result = 2147500035LL;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8E,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\dll\\entrypoints.cpp",
        (const char *)0x80004003LL,
        v35);
      result = 2147500035LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8D,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\dll\\entrypoints.cpp",
      (const char *)0x80004003LL,
      v35);
    result = 2147500035LL;
  }
  while ( 2 )
  {
    try
    {
    }
    catch ( ... )
    {
      v37 = wil::details::in1diag3::Return_CaughtException(
              retaddr,
              (void *)0xA1,
              (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\dll\\entrypoints.cpp",
              v7);
      result = v37;
      continue;
    }
    break;
  }
  return result;
}

```

## disassembly

```asm
0x180012090  push    rbx
0x180012092  push    rsi
0x180012093  push    rdi
0x180012094  push    r14
0x180012096  sub     rsp, 0D8h
0x18001209d  mov     rax, cs:__security_cookie
0x1800120a4  xor     rax, rsp
0x1800120a7  mov     [rsp+0F8h+var_30], rax
0x1800120af  mov     rbx, r9
0x1800120b2  mov     rdi, [rsp+0F8h+arg_20]
0x1800120ba  mov     rsi, [rsp+0F8h+arg_28]
0x1800120c2  test    rcx, rcx
0x1800120c5  jnz     short loc_1800120EF
0x1800120c7  mov     rcx, [rsp+0F8h]; this
0x1800120cf  mov     ebx, 80004003h
0x1800120d4  mov     r9d, ebx; char *
0x1800120d7  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800120de  mov     edx, 8Dh; void *
0x1800120e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800120e8  mov     eax, ebx
0x1800120ea  jmp     loc_18001237A
0x1800120ef  test    rbx, rbx
0x1800120f2  jnz     short loc_18001211C
0x1800120f4  mov     rcx, [rsp+0F8h]; this
0x1800120fc  mov     ebx, 80004003h
0x180012101  mov     r9d, ebx; char *
0x180012104  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001210b  mov     edx, 8Eh; void *
0x180012110  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012115  mov     eax, ebx
0x180012117  jmp     loc_18001237A
0x18001211c  test    rdi, rdi
0x18001211f  jnz     short loc_180012149
0x180012121  mov     rcx, [rsp+0F8h]; this
0x180012129  mov     ebx, 80004003h
0x18001212e  mov     r9d, ebx; char *
0x180012131  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180012138  mov     edx, 8Fh; void *
0x18001213d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012142  mov     eax, ebx
0x180012144  jmp     loc_18001237A
0x180012149  test    rsi, rsi
0x18001214c  jnz     short loc_180012176
0x18001214e  mov     rcx, [rsp+0F8h]; this
0x180012156  mov     ebx, 80004003h
0x18001215b  mov     r9d, ebx; char *
0x18001215e  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180012165  mov     edx, 90h; void *
0x18001216a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001216f  mov     eax, ebx
0x180012171  jmp     loc_18001237A
0x180012176  xorps   xmm0, xmm0
0x180012179  movups  xmmword ptr [rsp+0F8h+var_50], xmm0
0x180012181  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180012189  movdqu  [rsp+0F8h+var_40], xmm1
0x180012192  xor     eax, eax
0x180012194  mov     word ptr [rsp+0F8h+var_50], ax
0x18001219c  movups  xmmword ptr [rsp+0F8h+var_70], xmm0
0x1800121a4  movdqu  [rsp+0F8h+var_60], xmm1
0x1800121ad  mov     word ptr [rsp+0F8h+var_70], ax
0x1800121b5  mov     byte ptr [rsp+0F8h+var_D8], al; int
0x1800121b9  test    r8d, r8d
0x1800121bc  setnz   [rsp+0F8h+var_D0]
0x1800121c1  lea     rax, [rsp+0F8h+var_D8]
0x1800121c6  mov     [rsp+0F8h+var_A8], rax
0x1800121cb  lea     rax, [rsp+0F8h+var_70]
0x1800121d3  mov     [rsp+0F8h+var_B0], rax
0x1800121d8  lea     rax, [rsp+0F8h+var_50]
0x1800121e0  mov     [rsp+0F8h+var_B8], rax
0x1800121e5  mov     [rsp+0F8h+var_C8], edx
0x1800121e9  mov     [rsp+0F8h+var_C0], rcx
0x1800121ee  lea     rax, [rsp+0F8h+var_C0]
0x1800121f3  mov     [rsp+0F8h+var_A0], rax
0x1800121f8  lea     rax, [rsp+0F8h+var_C8]
0x1800121fd  mov     [rsp+0F8h+var_98], rax
0x180012202  lea     rax, [rsp+0F8h+var_D0]
0x180012207  mov     [rsp+0F8h+var_90], rax
0x18001220c  lea     rax, [rsp+0F8h+var_B8]
0x180012211  mov     [rsp+0F8h+var_88], rax
0x180012216  lea     rax, [rsp+0F8h+var_B0]
0x18001221b  mov     [rsp+0F8h+var_80], rax
0x180012220  lea     rax, [rsp+0F8h+var_A8]
0x180012225  mov     [rsp+0F8h+var_78], rax
0x18001222d  lea     rcx, [rsp+0F8h+var_A0]
0x180012232  call    HResultErrorContract__lambda_512e99141b121238e125c8e957ea4058___; HResultErrorContract__lambda_512e99141b121238e125c8e957ea4058_
0x180012237  mov     r14d, eax
0x18001223a  test    eax, eax
0x18001223c  jns     short loc_18001227C
0x18001223e  mov     rcx, [rsp+0F8h]; this
0x180012246  mov     r9d, eax; char *
0x180012249  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180012250  mov     edx, 96h; void *
0x180012255  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001225a  lea     rcx, [rsp+0F8h+var_70]
0x180012262  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180012267  lea     rcx, [rsp+0F8h+var_50]
0x18001226f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180012274  mov     eax, r14d
0x180012277  jmp     loc_18001237A
0x18001227c  mov     qword ptr [rbx], 0
0x180012283  lea     rcx, [rsp+0F8h+var_50]
0x18001228b  cmp     qword ptr [rsp+0F8h+var_40+8], 7
0x180012294  cmova   rcx, [rsp+0F8h+var_50]; this
0x18001229d  mov     rdx, rbx; unsigned __int16 *
0x1800122a0  call    ?DuplicateString@NgcUtils@@YAJPEBGPEAPEAG@Z; NgcUtils::DuplicateString(ushort const *,ushort * *)
0x1800122a5  mov     ebx, eax
0x1800122a7  test    eax, eax
0x1800122a9  jns     short loc_1800122E8
0x1800122ab  mov     rcx, [rsp+0F8h]; this
0x1800122b3  mov     r9d, eax; char *
0x1800122b6  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800122bd  mov     edx, 99h; void *
0x1800122c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800122c7  lea     rcx, [rsp+0F8h+var_70]
0x1800122cf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800122d4  lea     rcx, [rsp+0F8h+var_50]
0x1800122dc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800122e1  mov     eax, ebx
0x1800122e3  jmp     loc_18001237A
0x1800122e8  mov     qword ptr [rdi], 0
0x1800122ef  lea     rcx, [rsp+0F8h+var_70]
0x1800122f7  cmp     qword ptr [rsp+0F8h+var_60+8], 7
0x180012300  cmova   rcx, [rsp+0F8h+var_70]; this
0x180012309  mov     rdx, rdi; unsigned __int16 *
0x18001230c  call    ?DuplicateString@NgcUtils@@YAJPEBGPEAPEAG@Z; NgcUtils::DuplicateString(ushort const *,ushort * *)
0x180012311  mov     ebx, eax
0x180012313  test    eax, eax
0x180012315  jns     short loc_180012351
0x180012317  mov     rcx, [rsp+0F8h]; this
0x18001231f  mov     r9d, eax; char *
0x180012322  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180012329  mov     edx, 9Ch; void *
0x18001232e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012333  lea     rcx, [rsp+0F8h+var_70]
0x18001233b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180012340  lea     rcx, [rsp+0F8h+var_50]
0x180012348  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001234d  mov     eax, ebx
0x18001234f  jmp     short loc_18001237A
0x180012351  movzx   eax, byte ptr [rsp+0F8h+var_D8]
0x180012356  mov     [rsi], eax
0x180012358  lea     rcx, [rsp+0F8h+var_70]
0x180012360  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180012365  lea     rcx, [rsp+0F8h+var_50]
0x18001236d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180012372  xor     eax, eax
0x180012374  jmp     short loc_18001237A
0x180012376  mov     eax, [rsp+0F8h+var_C8]
0x18001237a  mov     rcx, [rsp+0F8h+var_30]
0x180012382  xor     rcx, rsp; StackCookie
0x180012385  call    __security_check_cookie
0x18001238a  add     rsp, 0D8h
0x180012391  pop     r14
0x180012393  pop     rdi
0x180012394  pop     rsi
0x180012395  pop     rbx
0x180012396  retn
```
