# RepoMan::Legacy::GetAttributeValue(RepoMan::ComPtr<IXMLDOMElement> const &,RepoMan::Legacy::XmlAttributeName)

- ea: `0x180194194`
- end: `0x1801943c7`
- name: `?GetAttributeValue@Legacy@RepoMan@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$ComPtr@UIXMLDOMElement@@@2@W4XmlAttributeName@12@@Z`
- size: `563`
- prototype: `__int64 __fastcall(LPSTR lpMultiByteStr)`
- caller_count: `6`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180194e04`
- `0x180195428`
- `0x18019589c`
- `0x180195d50`
- `0x180196460`
- `0x18019696c`

## callees

- `0x180013b14`
- `0x18002d958`
- `0x18018aed8`
- `0x18018b5f0`
- `0x180194194`
- `0x18019a840`
- `0x18019f7a0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x18019420f`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18019420f`
- `OLEAUT32!__imp_SysFreeString` at `0x180194374`
- `OLEAUT32!__imp_SysFreeString` at `0x180194374`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18019426d`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180194342`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18019426d`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180194342`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180194266`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18019433b`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180194266`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18019433b`

## string_xrefs

- `0x1801942a4`: `src\repoman\src\reposhared\pal\masterdescriptor\win32\masterdescriptor.cpp`
- `0x1801943b5`: `src\repoman\src\reposhared\pal\masterdescriptor\win32\masterdescriptor.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
LPSTR __fastcall RepoMan::Legacy::GetAttributeValue(LPSTR lpMultiByteStr, _QWORD *a2, unsigned __int8 a3)
{
  wchar_t *v5; // rdx
  __int64 v6; // rsi
  __int64 v7; // r8
  const OLECHAR *v8; // rcx
  OLECHAR *v9; // rbx
  OLECHAR *v10; // rcx
  unsigned int v11; // eax
  const char *v12; // r9
  OLECHAR *v13; // rcx
  __int16 v15; // [rsp+40h] [rbp-40h] BYREF
  __int64 v16; // [rsp+48h] [rbp-38h]
  OLECHAR *strIn[2]; // [rsp+58h] [rbp-28h] BYREF
  UINT ui[4]; // [rsp+68h] [rbp-18h]

  v5 = off_1801F29A0[a3];
  *(_OWORD *)strIn = 0;
  *(_OWORD *)ui = 0;
  v6 = -1;
  v7 = -1;
  do
    ++v7;
  while ( v5[v7] );
  std::wstring::_Construct<1,wchar_t const *>(strIn, v5, v7);
  v8 = (const OLECHAR *)strIn;
  if ( *(_QWORD *)&ui[2] > 7u )
    v8 = strIn[0];
  v9 = SysAllocStringLen(v8, ui[0]);
  if ( !v9 )
    RepoMan::RaiseException<RepoMan::Exception,enum RepoMan::Error>(
      39,
      (unsigned int)"src\\repoman\\src\\reposhared\\pal\\masterdescriptor\\win32\\masterdescriptor.cpp",
      (unsigned int)"SysAllocStringLen failed!",
      -2147024882,
      8);
  if ( *(_QWORD *)&ui[2] > 7u )
  {
    v10 = strIn[0];
    if ( (unsigned __int64)(2LL * *(_QWORD *)&ui[2] + 2) >= 0x1000 )
    {
      v10 = (OLECHAR *)*((_QWORD *)strIn[0] - 1);
      if ( (unsigned __int64)((char *)strIn[0] - (char *)v10 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v10);
  }
  strIn[0] = (OLECHAR *)19937;
  *(__m128i *)ui = _mm_load_si128((const __m128i *)&_xmm);
  v11 = (*(__int64 (__fastcall **)(_QWORD, OLECHAR *, __int16 *))(*(_QWORD *)*a2 + 352LL))(*a2, v9, &v15);
  RepoMan::RaiseExceptionIfFailed(
    (RepoMan *)v11,
    160,
    (int)"src\\repoman\\src\\reposhared\\pal\\masterdescriptor\\win32\\masterdescriptor.cpp",
    v12);
  if ( v15 == 8 )
  {
    *(_OWORD *)strIn = 0;
    *(_OWORD *)ui = 0;
    do
      ++v6;
    while ( *(_WORD *)(v16 + 2 * v6) );
    std::wstring::_Construct<1,wchar_t const *>(strIn, v16, v6);
    RepoMan::utf16_to_utf8(lpMultiByteStr, (LPCWCH)strIn);
    if ( *(_QWORD *)&ui[2] > 7u )
    {
      v13 = strIn[0];
      if ( (unsigned __int64)(2LL * *(_QWORD *)&ui[2] + 2) >= 0x1000 )
      {
        v13 = (OLECHAR *)*((_QWORD *)strIn[0] - 1);
        if ( (unsigned __int64)((char *)strIn[0] - (char *)v13 - 8) > 0x1F )
          _invoke_watson(0, 0, 0, 0, 0);
      }
      free(v13);
    }
    strIn[0] = (OLECHAR *)19937;
    *(__m128i *)ui = _mm_load_si128((const __m128i *)&_xmm);
  }
  else
  {
    *(_OWORD *)lpMultiByteStr = 0;
    *((_QWORD *)lpMultiByteStr + 2) = 0;
    *((_QWORD *)lpMultiByteStr + 3) = 15;
    *lpMultiByteStr = 0;
  }
  SysFreeString(v9);
  return lpMultiByteStr;
}

```

## disassembly

```asm
0x180194194  mov     [rsp-28h+arg_18], rbx
0x180194199  push    rbp
0x18019419a  push    rsi
0x18019419b  push    rdi
0x18019419c  push    r14
0x18019419e  push    r15
0x1801941a0  mov     rbp, rsp
0x1801941a3  sub     rsp, 80h
0x1801941aa  mov     rax, cs:__security_cookie
0x1801941b1  xor     rax, rsp
0x1801941b4  mov     [rbp+var_8], rax
0x1801941b8  mov     r14, rdx
0x1801941bb  mov     rdi, rcx
0x1801941be  mov     [rbp+var_48], rcx
0x1801941c2  xor     r15d, r15d
0x1801941c5  movzx   eax, r8b
0x1801941c9  lea     rdx, off_1801F29A0; "name"
0x1801941d0  mov     rdx, [rdx+rax*8]
0x1801941d4  xorps   xmm0, xmm0
0x1801941d7  movups  xmmword ptr [rbp+strIn], xmm0
0x1801941db  xorps   xmm1, xmm1
0x1801941de  movdqu  xmmword ptr [rbp+ui], xmm1
0x1801941e3  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1801941e7  mov     r8, rsi
0x1801941ea  inc     r8
0x1801941ed  cmp     [rdx+r8*2], r15w
0x1801941f2  jnz     short loc_1801941EA
0x1801941f4  lea     rcx, [rbp+strIn]
0x1801941f8  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1801941fd  nop
0x1801941fe  lea     rcx, [rbp+strIn]
0x180194202  cmp     qword ptr [rbp+ui+8], 7
0x180194207  cmova   rcx, [rbp+strIn]; strIn
0x18019420c  mov     edx, [rbp+ui]; ui
0x18019420f  call    cs:__imp_SysAllocStringLen
0x180194215  mov     rbx, rax
0x180194218  mov     [rbp+var_48], rax
0x18019421c  test    rax, rax
0x18019421f  jz      loc_1801943A0
0x180194225  mov     rax, qword ptr [rbp+ui+8]
0x180194229  cmp     rax, 7
0x18019422d  jbe     short loc_180194273
0x18019422f  mov     rcx, [rbp+strIn]; Block
0x180194233  mov     rdx, rcx
0x180194236  lea     rax, ds:2[rax*2]
0x18019423e  cmp     rax, 1000h
0x180194244  jb      short loc_18019426D
0x180194246  mov     rcx, [rcx-8]
0x18019424a  sub     rdx, rcx
0x18019424d  lea     rax, [rdx-8]
0x180194251  cmp     rax, 1Fh
0x180194255  jbe     short loc_18019426D
0x180194257  mov     [rsp+80h+Reserved], r15; Reserved
0x18019425c  xor     r9d, r9d; LineNo
0x18019425f  xor     r8d, r8d; FileName
0x180194262  xor     edx, edx; FunctionName
0x180194264  xor     ecx, ecx; Expression
0x180194266  call    cs:__imp__invoke_watson
0x18019426d  call    cs:__imp_free
0x180194273  mov     [rbp+strIn], 4DE1h
0x18019427b  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x180194283  movdqu  xmmword ptr [rbp+ui], xmm0
0x180194288  mov     rcx, [r14]
0x18019428b  mov     rax, [rcx]
0x18019428e  lea     r8, [rbp+var_40]
0x180194292  mov     rdx, rbx
0x180194295  mov     rax, [rax+160h]
0x18019429c  call    cs:__guard_dispatch_icall_fptr
0x1801942a2  mov     ecx, eax; this
0x1801942a4  lea     r8, aSrcRepomanSrcR_18; "src\\repoman\\src\\reposhared\\pal\\mas"...
0x1801942ab  mov     edx, 0A0h; int
0x1801942b0  call    ?RaiseExceptionIfFailed@RepoMan@@YAXJHQEBD@Z; RepoMan::RaiseExceptionIfFailed(long,int,char const * const)
0x1801942b5  mov     eax, 8
0x1801942ba  xorps   xmm0, xmm0
0x1801942bd  cmp     [rbp+var_40], ax
0x1801942c1  jnz     loc_18019435F
0x1801942c7  movups  xmmword ptr [rbp+strIn], xmm0
0x1801942cb  xorps   xmm1, xmm1
0x1801942ce  movdqu  xmmword ptr [rbp+ui], xmm1
0x1801942d3  mov     rdx, [rbp+var_38]
0x1801942d7  inc     rsi
0x1801942da  cmp     [rdx+rsi*2], r15w
0x1801942df  jnz     short loc_1801942D7
0x1801942e1  mov     r8, rsi
0x1801942e4  lea     rcx, [rbp+strIn]
0x1801942e8  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1801942ed  nop
0x1801942ee  lea     rdx, [rbp+strIn]; lpWideCharStr
0x1801942f2  mov     rcx, rdi; lpMultiByteStr
0x1801942f5  call    ?utf16_to_utf8@RepoMan@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@@Z; RepoMan::utf16_to_utf8(std::wstring const &)
0x1801942fa  mov     rax, qword ptr [rbp+ui+8]
0x1801942fe  cmp     rax, 7
0x180194302  jbe     short loc_180194348
0x180194304  mov     rcx, [rbp+strIn]; Block
0x180194308  mov     rdx, rcx
0x18019430b  lea     rax, ds:2[rax*2]
0x180194313  cmp     rax, 1000h
0x180194319  jb      short loc_180194342
0x18019431b  mov     rcx, [rcx-8]
0x18019431f  sub     rdx, rcx
0x180194322  lea     rax, [rdx-8]
0x180194326  cmp     rax, 1Fh
0x18019432a  jbe     short loc_180194342
0x18019432c  mov     [rsp+80h+Reserved], r15; Reserved
0x180194331  xor     r9d, r9d; LineNo
0x180194334  xor     r8d, r8d; FileName
0x180194337  xor     edx, edx; FunctionName
0x180194339  xor     ecx, ecx; Expression
0x18019433b  call    cs:__imp__invoke_watson
0x180194342  call    cs:__imp_free
0x180194348  mov     [rbp+strIn], 4DE1h
0x180194350  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x180194358  movdqu  xmmword ptr [rbp+ui], xmm0
0x18019435d  jmp     short loc_180194371
0x18019435f  movups  xmmword ptr [rdi], xmm0
0x180194362  mov     [rdi+10h], r15
0x180194366  mov     qword ptr [rdi+18h], 0Fh
0x18019436e  mov     [rdi], r15b
0x180194371  mov     rcx, rbx; bstrString
0x180194374  call    cs:__imp_SysFreeString
0x18019437a  mov     rax, rdi
0x18019437d  mov     rcx, [rbp+var_8]
0x180194381  xor     rcx, rsp; StackCookie
0x180194384  call    __security_check_cookie
0x180194389  mov     rbx, [rsp+80h+arg_18]
0x180194391  add     rsp, 80h
0x180194398  pop     r15
0x18019439a  pop     r14
0x18019439c  pop     rdi
0x18019439d  pop     rsi
0x18019439e  pop     rbp
0x18019439f  retn
0x1801943a0  mov     dword ptr [rsp+80h+Reserved], 8
0x1801943a8  mov     r9d, 8007000Eh
0x1801943ae  lea     r8, aSysallocstring; "SysAllocStringLen failed!"
0x1801943b5  lea     rdx, aSrcRepomanSrcR_18; "src\\repoman\\src\\reposhared\\pal\\mas"...
0x1801943bc  mov     ecx, 27h ; '''
0x1801943c1  call    ??$RaiseException@VException@RepoMan@@W4Error@2@@RepoMan@@YAXHQEBDPEBDW4Error@0@W4Verbosity@ILogger@0@@Z; RepoMan::RaiseException<RepoMan::Exception,RepoMan::Error>(int,char const * const,char const *,RepoMan::Error,RepoMan::ILogger::Verbosity)
```
