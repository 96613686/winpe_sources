# FciCallbacks::CallbackFciGetTempFile(char *,int,void *)

- ea: `0x18000d7f0`
- end: `0x18000d95b`
- name: `?CallbackFciGetTempFile@FciCallbacks@@SAHPEADHPEAX@Z`
- size: `363`
- prototype: `__int64 __fastcall(char *pszTempName, int cbTempName, _QWORD *pv)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180001540`
- `0x180001fb2`
- `0x180002e54`
- `0x180003648`
- `0x1800082b8`
- `0x18000b658`
- `0x18000d7f0`
- `0x18000d964`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000d8da`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000d8da`

## string_xrefs

- `0x18000d8fa`: `%hs\CABTEMP_%lld_%d`

## pseudocode

```c
__int64 __fastcall FciCallbacks::CallbackFciGetTempFile(char *pszTempName, int cbTempName, _QWORD *pv)
{
  unsigned __int64 v3; // rsi
  _QWORD *v5; // rdx
  unsigned __int64 v6; // r8
  WCHAR *v7; // rax
  __int64 v8; // rdx
  WCHAR *v9; // rcx
  int v10; // ebx
  ULONGLONG TickCount64; // rax
  const char *v12; // r9
  __int64 v14; // [rsp+30h] [rbp-50h]
  WCHAR WideCharStr[8]; // [rsp+38h] [rbp-48h] BYREF
  __int64 v16; // [rsp+48h] [rbp-38h]
  unsigned __int64 v17; // [rsp+50h] [rbp-30h]
  __int128 v18; // [rsp+58h] [rbp-28h] BYREF
  __m128i si128; // [rsp+68h] [rbp-18h]

  HIWORD(v14) = -1;
  v3 = cbTempName;
  if ( pv )
  {
    *(_OWORD *)WideCharStr = 0;
    v16 = 0;
    v17 = 7;
    WideCharStr[0] = 0;
    v5 = pv + 12;
    if ( WideCharStr != (WCHAR *)(pv + 12) )
    {
      v6 = pv[14];
      if ( v5[3] > 7u )
        v5 = (_QWORD *)*v5;
      std::wstring::_Assign<wchar_t>((void **)WideCharStr, v5, v6);
      if ( v16 )
      {
        v7 = WideCharStr;
        if ( v17 > 7 )
          v7 = *(WCHAR **)WideCharStr;
        if ( v7[v16 - 1] == 92 )
        {
          v8 = --v16;
          v9 = WideCharStr;
          if ( v17 > 7 )
            v9 = *(WCHAR **)WideCharStr;
          v9[v8] = 0;
        }
        v18 = 0;
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        LOBYTE(v18) = 0;
        if ( (int)Utils::ConvertUnicodeToMultiByte(WideCharStr, &v18) >= 0 )
        {
          v10 = o_rand_0();
          TickCount64 = GetTickCount64();
          v12 = (const char *)&v18;
          if ( si128.m128i_i64[1] > 0xFuLL )
            v12 = (const char *)v18;
          if ( !(unsigned int)StringCchPrintfA(pszTempName, v3, "%hs\\CABTEMP_%lld_%d", v12, TickCount64, v10) )
          {
            std::string::~string((char **)&v18);
            std::wstring::~wstring((char **)WideCharStr);
            return 1;
          }
        }
        std::string::~string((char **)&v18);
      }
    }
    std::wstring::~wstring((char **)WideCharStr);
  }
  return 0;
}

```

## disassembly

```asm
0x18000d7f0  mov     rax, rsp
0x18000d7f3  push    rbp
0x18000d7f4  push    rsi
0x18000d7f5  push    rdi
0x18000d7f6  mov     rbp, rsp
0x18000d7f9  sub     rsp, 80h
0x18000d800  mov     [rbp+var_50], 0FFFFFFFFFFFFFFFEh
0x18000d808  mov     [rax+20h], rbx
0x18000d80c  mov     rax, cs:__security_cookie
0x18000d813  xor     rax, rsp
0x18000d816  mov     [rbp+var_8], rax
0x18000d81a  movsxd  rsi, edx
0x18000d81d  mov     rdi, rcx
0x18000d820  test    r8, r8
0x18000d823  jz      loc_18000D93A
0x18000d829  xorps   xmm0, xmm0
0x18000d82c  movups  xmmword ptr [rbp+WideCharStr], xmm0
0x18000d830  mov     [rbp+var_38], 0
0x18000d838  mov     ebx, 7
0x18000d83d  mov     [rbp+var_30], rbx
0x18000d841  xor     eax, eax
0x18000d843  mov     [rbp+WideCharStr], ax
0x18000d847  lea     rdx, [r8+60h]
0x18000d84b  lea     rax, [rbp+WideCharStr]
0x18000d84f  cmp     rax, rdx
0x18000d852  jz      loc_18000D931
0x18000d858  mov     r8, [rdx+10h]
0x18000d85c  cmp     [rdx+18h], rbx
0x18000d860  jbe     short loc_18000D865
0x18000d862  mov     rdx, [rdx]
0x18000d865  lea     rcx, [rbp+WideCharStr]
0x18000d869  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18000d86e  mov     rdx, [rbp+var_38]
0x18000d872  test    rdx, rdx
0x18000d875  jz      loc_18000D931
0x18000d87b  lea     rax, [rbp+WideCharStr]
0x18000d87f  cmp     [rbp+var_30], rbx
0x18000d883  cmova   rax, qword ptr [rbp+WideCharStr]
0x18000d888  cmp     word ptr [rax+rdx*2-2], 5Ch ; '\'
0x18000d88e  jnz     short loc_18000D8AA
0x18000d890  dec     rdx
0x18000d893  mov     [rbp+var_38], rdx
0x18000d897  lea     rcx, [rbp+WideCharStr]
0x18000d89b  cmp     [rbp+var_30], rbx
0x18000d89f  cmova   rcx, qword ptr [rbp+WideCharStr]
0x18000d8a4  xor     eax, eax
0x18000d8a6  mov     [rcx+rdx*2], ax
0x18000d8aa  xorps   xmm0, xmm0
0x18000d8ad  movups  [rbp+var_28], xmm0
0x18000d8b1  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x18000d8b9  movdqu  [rbp+var_18], xmm1
0x18000d8be  mov     byte ptr [rbp+var_28], 0
0x18000d8c2  lea     rdx, [rbp+var_28]; void *
0x18000d8c6  lea     rcx, [rbp+WideCharStr]; lpWideCharStr
0x18000d8ca  call    ?ConvertUnicodeToMultiByte@Utils@@SAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@@Z; Utils::ConvertUnicodeToMultiByte(std::wstring const &,std::string *)
0x18000d8cf  test    eax, eax
0x18000d8d1  js      short loc_18000D927
0x18000d8d3  call    _o_rand_0
0x18000d8d8  mov     ebx, eax
0x18000d8da  call    cs:__imp_GetTickCount64
0x18000d8e0  lea     r9, [rbp+var_28]
0x18000d8e4  cmp     qword ptr [rbp+var_18+8], 0Fh
0x18000d8e9  cmova   r9, qword ptr [rbp+var_28]
0x18000d8ee  mov     rdx, rsi; unsigned __int64
0x18000d8f1  mov     [rsp+80h+var_58], ebx
0x18000d8f5  mov     [rsp+80h+var_60], rax
0x18000d8fa  lea     r8, aHsCabtempLldD; "%hs\\CABTEMP_%lld_%d"
0x18000d901  mov     rcx, rdi; char *
0x18000d904  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18000d909  test    eax, eax
0x18000d90b  jnz     short loc_18000D927
0x18000d90d  lea     rcx, [rbp+var_28]
0x18000d911  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18000d916  nop
0x18000d917  lea     rcx, [rbp+WideCharStr]
0x18000d91b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000d920  mov     eax, 1
0x18000d925  jmp     short loc_18000D93C
0x18000d927  lea     rcx, [rbp+var_28]
0x18000d92b  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18000d930  nop
0x18000d931  lea     rcx, [rbp+WideCharStr]
0x18000d935  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000d93a  xor     eax, eax
0x18000d93c  mov     rcx, [rbp+var_8]
0x18000d940  xor     rcx, rsp; StackCookie
0x18000d943  call    __security_check_cookie
0x18000d948  mov     rbx, [rsp+80h+arg_18]
0x18000d950  add     rsp, 80h
0x18000d957  pop     rdi
0x18000d958  pop     rsi
0x18000d959  pop     rbp
0x18000d95a  retn
```
