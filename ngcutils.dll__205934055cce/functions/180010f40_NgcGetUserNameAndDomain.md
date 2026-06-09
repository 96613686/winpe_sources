# NgcGetUserNameAndDomain

- ea: `0x180010f40`
- end: `0x180011189`
- name: `NgcGetUserNameAndDomain`
- size: `585`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003080`
- `0x18000a5b4`
- `0x18000ce74`
- `0x180010f40`
- `0x180013b3c`
- `0x180019374`

## string_xrefs

- `0x180010f82`: `onecore\ds\security\ngc\utils\common\dll\entrypoints.cpp`
- `0x180010faf`: `onecore\ds\security\ngc\utils\common\dll\entrypoints.cpp`
- `0x180010fdc`: `onecore\ds\security\ngc\utils\common\dll\entrypoints.cpp`
- `0x180011054`: `onecore\ds\security\ngc\utils\common\dll\entrypoints.cpp`
- `0x1800110b3`: `onecore\ds\security\ngc\utils\common\dll\entrypoints.cpp`
- `0x180011112`: `onecore\ds\security\ngc\utils\common\dll\entrypoints.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall NgcGetUserNameAndDomain(
        NgcUtils *a1,
        int a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        _DWORD *a5)
{
  int UserNameAndDomain; // eax
  unsigned __int16 **v9; // r8
  unsigned int v10; // ebx
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // r8
  NgcUtils *v15; // rcx
  int v16; // eax
  unsigned __int16 **v17; // r8
  unsigned int v18; // ebx
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // rdx
  __int64 v22; // r8
  NgcUtils *v23; // rcx
  int v24; // eax
  __int64 v25; // rdx
  __int64 v26; // r8
  unsigned int v27; // ebx
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // rdx
  __int64 v33; // r8
  int v34; // [rsp+20h] [rbp-78h]
  int v35; // [rsp+20h] [rbp-78h]
  __int64 v36; // [rsp+30h] [rbp-68h] BYREF
  NgcUtils *v37[2]; // [rsp+38h] [rbp-60h] BYREF
  __m128i v38; // [rsp+48h] [rbp-50h]
  NgcUtils *v39[2]; // [rsp+58h] [rbp-40h] BYREF
  __m128i si128; // [rsp+68h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  if ( a1 )
  {
    if ( a3 )
    {
      if ( a4 )
      {
        *(_OWORD *)v39 = 0;
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        LOWORD(v39[0]) = 0;
        *(_OWORD *)v37 = 0;
        v38 = si128;
        LOWORD(v37[0]) = 0;
        LOBYTE(v36) = 0;
        UserNameAndDomain = NgcUtils::GetUserNameAndDomain(a1, a2 != 0, (__int64)v39, (char *)v37, &v36);
        v10 = UserNameAndDomain;
        if ( UserNameAndDomain >= 0 )
        {
          *(_QWORD *)a3 = 0;
          v15 = (NgcUtils *)v39;
          if ( si128.m128i_i64[1] > 7uLL )
            v15 = v39[0];
          v16 = NgcUtils::DuplicateString(v15, a3, v9);
          v18 = v16;
          if ( v16 >= 0 )
          {
            *(_QWORD *)a4 = 0;
            v23 = (NgcUtils *)v37;
            if ( v38.m128i_i64[1] > 7uLL )
              v23 = v37[0];
            v24 = NgcUtils::DuplicateString(v23, a4, v17);
            v27 = v24;
            if ( v24 >= 0 )
            {
              if ( a5 )
                *a5 = (unsigned __int8)v36;
              std::wstring::~wstring(v37, v25, v26);
              std::wstring::~wstring(v39, v32, v33);
              return 0;
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1ED,
                (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\dll\\entrypoints.cpp",
                (const char *)(unsigned int)v24,
                v35);
              std::wstring::~wstring(v37, v28, v29);
              std::wstring::~wstring(v39, v30, v31);
              return v27;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1EA,
              (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\dll\\entrypoints.cpp",
              (const char *)(unsigned int)v16,
              v35);
            std::wstring::~wstring(v37, v19, v20);
            std::wstring::~wstring(v39, v21, v22);
            return v18;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1E7,
            (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\dll\\entrypoints.cpp",
            (const char *)(unsigned int)UserNameAndDomain,
            v35);
          std::wstring::~wstring(v37, v11, v12);
          std::wstring::~wstring(v39, v13, v14);
          return v10;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1E1,
          (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\dll\\entrypoints.cpp",
          (const char *)0x80004003LL,
          v34);
        return 2147500035LL;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1E0,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\dll\\entrypoints.cpp",
        (const char *)0x80004003LL,
        v34);
      return 2147500035LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1DF,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\dll\\entrypoints.cpp",
      (const char *)0x80004003LL,
      v34);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x180010f40  mov     [rsp+arg_8], rbx
0x180010f45  push    rsi
0x180010f46  push    rdi
0x180010f47  push    r14
0x180010f49  sub     rsp, 80h
0x180010f50  mov     rax, cs:__security_cookie
0x180010f57  xor     rax, rsp
0x180010f5a  mov     [rsp+98h+var_20], rax
0x180010f5f  mov     rdi, r9
0x180010f62  mov     rsi, r8
0x180010f65  mov     r14, [rsp+98h+arg_20]
0x180010f6d  test    rcx, rcx
0x180010f70  jnz     short loc_180010F9A
0x180010f72  mov     rcx, [rsp+98h]; this
0x180010f7a  mov     ebx, 80004003h
0x180010f7f  mov     r9d, ebx; char *
0x180010f82  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180010f89  mov     edx, 1DFh; void *
0x180010f8e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010f93  mov     eax, ebx
0x180010f95  jmp     loc_180011167
0x180010f9a  test    rsi, rsi
0x180010f9d  jnz     short loc_180010FC7
0x180010f9f  mov     rcx, [rsp+98h]; this
0x180010fa7  mov     ebx, 80004003h
0x180010fac  mov     r9d, ebx; char *
0x180010faf  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180010fb6  mov     edx, 1E0h; void *
0x180010fbb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010fc0  mov     eax, ebx
0x180010fc2  jmp     loc_180011167
0x180010fc7  test    rdi, rdi
0x180010fca  jnz     short loc_180010FF4
0x180010fcc  mov     rcx, [rsp+98h]; this
0x180010fd4  mov     ebx, 80004003h
0x180010fd9  mov     r9d, ebx; char *
0x180010fdc  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180010fe3  mov     edx, 1E1h; void *
0x180010fe8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010fed  mov     eax, ebx
0x180010fef  jmp     loc_180011167
0x180010ff4  xorps   xmm0, xmm0
0x180010ff7  movups  xmmword ptr [rsp+98h+var_40], xmm0
0x180010ffc  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180011004  movdqu  [rsp+98h+var_30], xmm1
0x18001100a  xor     eax, eax
0x18001100c  mov     word ptr [rsp+98h+var_40], ax
0x180011011  movups  xmmword ptr [rsp+98h+var_60], xmm0
0x180011016  movdqu  [rsp+98h+var_50], xmm1
0x18001101c  mov     word ptr [rsp+98h+var_60], ax
0x180011021  mov     byte ptr [rsp+98h+var_68], al
0x180011025  test    edx, edx
0x180011027  setnz   dl
0x18001102a  lea     rax, [rsp+98h+var_68]
0x18001102f  mov     qword ptr [rsp+98h+var_78], rax; int
0x180011034  lea     r9, [rsp+98h+var_60]
0x180011039  lea     r8, [rsp+98h+var_40]
0x18001103e  call    ?GetUserNameAndDomain@NgcUtils@@YAJQEAX_NPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@2PEA_N@Z; NgcUtils::GetUserNameAndDomain(void * const,bool,std::wstring *,std::wstring *,bool *)
0x180011043  mov     ebx, eax
0x180011045  test    eax, eax
0x180011047  jns     short loc_180011082
0x180011049  mov     rcx, [rsp+98h]; this
0x180011051  mov     r9d, eax; char *
0x180011054  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001105b  mov     edx, 1E7h; void *
0x180011060  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011065  nop
0x180011066  lea     rcx, [rsp+98h+var_60]
0x18001106b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011070  nop
0x180011071  lea     rcx, [rsp+98h+var_40]
0x180011076  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001107b  mov     eax, ebx
0x18001107d  jmp     loc_180011167
0x180011082  mov     qword ptr [rsi], 0
0x180011089  lea     rcx, [rsp+98h+var_40]
0x18001108e  cmp     qword ptr [rsp+98h+var_30+8], 7
0x180011094  cmova   rcx, [rsp+98h+var_40]; this
0x18001109a  mov     rdx, rsi; unsigned __int16 *
0x18001109d  call    ?DuplicateString@NgcUtils@@YAJPEBGPEAPEAG@Z; NgcUtils::DuplicateString(ushort const *,ushort * *)
0x1800110a2  mov     ebx, eax
0x1800110a4  test    eax, eax
0x1800110a6  jns     short loc_1800110E1
0x1800110a8  mov     rcx, [rsp+98h]; this
0x1800110b0  mov     r9d, eax; char *
0x1800110b3  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800110ba  mov     edx, 1EAh; void *
0x1800110bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800110c4  nop
0x1800110c5  lea     rcx, [rsp+98h+var_60]
0x1800110ca  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800110cf  nop
0x1800110d0  lea     rcx, [rsp+98h+var_40]
0x1800110d5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800110da  mov     eax, ebx
0x1800110dc  jmp     loc_180011167
0x1800110e1  mov     qword ptr [rdi], 0
0x1800110e8  lea     rcx, [rsp+98h+var_60]
0x1800110ed  cmp     qword ptr [rsp+98h+var_50+8], 7
0x1800110f3  cmova   rcx, [rsp+98h+var_60]; this
0x1800110f9  mov     rdx, rdi; unsigned __int16 *
0x1800110fc  call    ?DuplicateString@NgcUtils@@YAJPEBGPEAPEAG@Z; NgcUtils::DuplicateString(ushort const *,ushort * *)
0x180011101  mov     ebx, eax
0x180011103  test    eax, eax
0x180011105  jns     short loc_18001113D
0x180011107  mov     rcx, [rsp+98h]; this
0x18001110f  mov     r9d, eax; char *
0x180011112  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180011119  mov     edx, 1EDh; void *
0x18001111e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011123  nop
0x180011124  lea     rcx, [rsp+98h+var_60]
0x180011129  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001112e  nop
0x18001112f  lea     rcx, [rsp+98h+var_40]
0x180011134  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011139  mov     eax, ebx
0x18001113b  jmp     short loc_180011167
0x18001113d  test    r14, r14
0x180011140  jz      short loc_18001114A
0x180011142  movzx   eax, byte ptr [rsp+98h+var_68]
0x180011147  mov     [r14], eax
0x18001114a  lea     rcx, [rsp+98h+var_60]
0x18001114f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011154  nop
0x180011155  lea     rcx, [rsp+98h+var_40]
0x18001115a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001115f  xor     eax, eax
0x180011161  jmp     short loc_180011167
0x180011163  mov     eax, dword ptr [rsp+98h+var_68+4]
0x180011167  mov     rcx, [rsp+98h+var_20]
0x18001116c  xor     rcx, rsp; StackCookie
0x18001116f  call    __security_check_cookie
0x180011174  mov     rbx, [rsp+98h+arg_8]
0x18001117c  add     rsp, 80h
0x180011183  pop     r14
0x180011185  pop     rdi
0x180011186  pop     rsi
0x180011187  retn
```
