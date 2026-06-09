# FidoUtils::Utf16ToUtf8(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180055aac`
- end: `0x180055c53`
- name: `?Utf16ToUtf8@FidoUtils@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z`
- size: `423`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180047290`
- `0x18004c0a0`

## callees

- `0x180003080`
- `0x180003bc8`
- `0x1800131dc`
- `0x18001361c`
- `0x180014d74`
- `0x180055aac`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180055b30`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180055bd3`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180055b30`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180055bd3`

## string_xrefs

- `0x180055c2c`: `onecore\ds\security\ngc\lockbox\common\lib\utilscommon.cpp`
- `0x180055c41`: `onecore\ds\security\ngc\lockbox\common\lib\utilscommon.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FidoUtils::Utf16ToUtf8(__int64 a1, __int64 *a2)
{
  __int64 *v2; // rdi
  const WCHAR *v4; // r8
  int v5; // eax
  const char *v6; // r9
  __int64 v7; // rsi
  CHAR *lpMultiByteStr; // rax
  int v9; // r9d
  const char *v10; // r9
  LPSTR Src[2]; // [rsp+50h] [rbp-30h] BYREF
  int cbMultiByte[4]; // [rsp+60h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  v2 = a2;
  if ( a2[2] )
  {
    if ( (unsigned __int64)a2[3] <= 7 )
      v4 = (const WCHAR *)a2;
    else
      v4 = (const WCHAR *)*a2;
    v5 = WideCharToMultiByte(0xFDE9u, 0x80u, v4, *((_DWORD *)a2 + 4), 0, 0, 0, 0);
    if ( !v5 )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x23,
        (unsigned int)"onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\utilscommon.cpp",
        v6);
    *(_OWORD *)Src = 0;
    *(_QWORD *)cbMultiByte = 0;
    *(_QWORD *)&cbMultiByte[2] = 15;
    LOBYTE(Src[0]) = 0;
    v7 = v5;
    if ( (unsigned __int64)v5 > 0xF )
    {
      std::string::_Reallocate_grow_by<_lambda_e1befb086ad3257e3f042a63030725f7_,unsigned __int64,char>(Src);
    }
    else
    {
      *(_QWORD *)cbMultiByte = v5;
      memset_0(Src, 0, v5);
      *((_BYTE *)Src + v7) = 0;
    }
    lpMultiByteStr = (CHAR *)Src;
    if ( *(_QWORD *)&cbMultiByte[2] > 0xFu )
      lpMultiByteStr = Src[0];
    v9 = *((_DWORD *)v2 + 4);
    if ( (unsigned __int64)v2[3] > 7 )
      v2 = (__int64 *)*v2;
    if ( !WideCharToMultiByte(0xFDE9u, 0x80u, (LPCWCH)v2, v9, lpMultiByteStr, cbMultiByte[0], 0, 0) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x30,
        (unsigned int)"onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\utilscommon.cpp",
        v10);
    *(_OWORD *)a1 = *(_OWORD *)Src;
    *(_OWORD *)(a1 + 16) = *(_OWORD *)cbMultiByte;
    *(_QWORD *)cbMultiByte = 0;
    *(_QWORD *)&cbMultiByte[2] = 15;
    LOBYTE(Src[0]) = 0;
    std::string::~string(Src);
  }
  else
  {
    *(_OWORD *)a1 = 0;
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 15;
    *(_BYTE *)a1 = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x180055aac  mov     [rsp-18h+arg_10], rbx
0x180055ab1  mov     [rsp-18h+arg_18], rsi
0x180055ab6  push    rbp
0x180055ab7  push    rdi
0x180055ab8  push    r15
0x180055aba  mov     rbp, rsp
0x180055abd  sub     rsp, 80h
0x180055ac4  mov     rax, cs:__security_cookie
0x180055acb  xor     rax, rsp
0x180055ace  mov     [rbp+var_10], rax
0x180055ad2  mov     rdi, rdx
0x180055ad5  mov     rbx, rcx
0x180055ad8  mov     [rbp+var_38], rcx
0x180055adc  xor     r15d, r15d
0x180055adf  cmp     [rdx+10h], r15
0x180055ae3  jnz     short loc_180055AFF
0x180055ae5  xorps   xmm0, xmm0
0x180055ae8  movups  xmmword ptr [rcx], xmm0
0x180055aeb  mov     [rcx+10h], r15
0x180055aef  mov     qword ptr [rcx+18h], 0Fh
0x180055af7  mov     [rcx], r15b
0x180055afa  jmp     loc_180055C05
0x180055aff  cmp     qword ptr [rdx+18h], 7
0x180055b04  jbe     short loc_180055B0B
0x180055b06  mov     r8, [rdx]
0x180055b09  jmp     short loc_180055B0E
0x180055b0b  mov     r8, rdi; lpWideCharStr
0x180055b0e  mov     [rsp+80h+lpUsedDefaultChar], r15; lpUsedDefaultChar
0x180055b13  mov     [rsp+80h+lpDefaultChar], r15; lpDefaultChar
0x180055b18  mov     [rsp+80h+cbMultiByte], r15d; cbMultiByte
0x180055b1d  mov     [rsp+80h+lpMultiByteStr], r15; lpMultiByteStr
0x180055b22  mov     r9d, [rdx+10h]; cchWideChar
0x180055b26  mov     edx, 80h; dwFlags
0x180055b2b  mov     ecx, 0FDE9h; CodePage
0x180055b30  call    cs:__imp_WideCharToMultiByte
0x180055b36  mov     rcx, [rbp+18h]; this
0x180055b3a  test    eax, eax
0x180055b3c  jz      loc_180055C41
0x180055b42  xorps   xmm0, xmm0
0x180055b45  movups  xmmword ptr [rbp+Src], xmm0
0x180055b49  mov     qword ptr [rbp+var_20], r15
0x180055b4d  mov     qword ptr [rbp+var_20+8], 0Fh
0x180055b55  mov     byte ptr [rbp+Src], r15b
0x180055b59  movsxd  rsi, eax
0x180055b5c  test    eax, eax
0x180055b5e  jnz     short loc_180055B66
0x180055b60  mov     qword ptr [rbp+var_20], rsi
0x180055b64  jmp     short loc_180055B7E
0x180055b66  lea     rcx, [rbp+Src]; Src
0x180055b6a  cmp     rsi, 0Fh
0x180055b6e  ja      short loc_180055B85
0x180055b70  mov     qword ptr [rbp+var_20], rsi
0x180055b74  mov     r8, rsi; Size
0x180055b77  xor     edx, edx; Val
0x180055b79  call    memset_0
0x180055b7e  mov     byte ptr [rbp+rsi+Src], r15b
0x180055b83  jmp     short loc_180055B90
0x180055b85  mov     r9, rsi
0x180055b88  mov     rdx, rsi
0x180055b8b  call    ??$_Reallocate_grow_by@V_lambda_e1befb086ad3257e3f042a63030725f7_@@_KD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_e1befb086ad3257e3f042a63030725f7_@@_KD@Z; std::string::_Reallocate_grow_by<_lambda_e1befb086ad3257e3f042a63030725f7_,unsigned __int64,char>(unsigned __int64,_lambda_e1befb086ad3257e3f042a63030725f7_,unsigned __int64,char)
0x180055b90  mov     ecx, [rbp+var_20]
0x180055b93  lea     rax, [rbp+Src]
0x180055b97  cmp     qword ptr [rbp+var_20+8], 0Fh
0x180055b9c  cmova   rax, [rbp+Src]
0x180055ba1  mov     r9d, [rdi+10h]; cchWideChar
0x180055ba5  cmp     qword ptr [rdi+18h], 7
0x180055baa  jbe     short loc_180055BAF
0x180055bac  mov     rdi, [rdi]
0x180055baf  mov     rsi, [rbp+18h]
0x180055bb3  mov     [rsp+80h+lpUsedDefaultChar], r15; lpUsedDefaultChar
0x180055bb8  mov     [rsp+80h+lpDefaultChar], r15; lpDefaultChar
0x180055bbd  mov     [rsp+80h+cbMultiByte], ecx; cbMultiByte
0x180055bc1  mov     [rsp+80h+lpMultiByteStr], rax; lpMultiByteStr
0x180055bc6  mov     r8, rdi; lpWideCharStr
0x180055bc9  mov     edx, 80h; dwFlags
0x180055bce  mov     ecx, 0FDE9h; CodePage
0x180055bd3  call    cs:__imp_WideCharToMultiByte
0x180055bd9  test    eax, eax
0x180055bdb  jz      short loc_180055C2C
0x180055bdd  movups  xmm0, xmmword ptr [rbp+Src]
0x180055be1  movups  xmmword ptr [rbx], xmm0
0x180055be4  movups  xmm1, xmmword ptr [rbp+var_20]
0x180055be8  movups  xmmword ptr [rbx+10h], xmm1
0x180055bec  mov     qword ptr [rbp+var_20], r15
0x180055bf0  mov     qword ptr [rbp+var_20+8], 0Fh
0x180055bf8  mov     byte ptr [rbp+Src], r15b
0x180055bfc  lea     rcx, [rbp+Src]
0x180055c00  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180055c05  mov     rax, rbx
0x180055c08  mov     rcx, [rbp+var_10]
0x180055c0c  xor     rcx, rsp; StackCookie
0x180055c0f  call    __security_check_cookie
0x180055c14  lea     r11, [rsp+80h+var_s0]
0x180055c1c  mov     rbx, [r11+30h]
0x180055c20  mov     rsi, [r11+38h]
0x180055c24  mov     rsp, r11
0x180055c27  pop     r15
0x180055c29  pop     rdi
0x180055c2a  pop     rbp
0x180055c2b  retn
0x180055c2c  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x180055c33  mov     edx, 30h ; '0'; void *
0x180055c38  mov     rcx, rsi; this
0x180055c3b  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180055c41  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x180055c48  mov     edx, 23h ; '#'; void *
0x180055c4d  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
