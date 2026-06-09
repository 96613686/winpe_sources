# _anonymous_namespace_::Utf16ToUtf8

- ea: `0x180021000`
- end: `0x18002117e`
- name: `_anonymous_namespace_::Utf16ToUtf8`
- size: `382`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012910`
- `0x18001cb44`
- `0x18001fb28`

## callees

- `0x180002490`
- `0x180008a68`
- `0x180021000`
- `0x180022280`
- `0x180025c30`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180021099`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800210fd`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180021099`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800210fd`

## string_xrefs

- `0x180021157`: `onecore\ds\security\cfl\api\lib\CflApiJson.h`
- `0x18002116c`: `onecore\ds\security\cfl\api\lib\CflApiJson.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall anonymous_namespace_::Utf16ToUtf8(__int64 a1, __int64 *a2)
{
  __int64 *v2; // rdi
  const WCHAR *v4; // r8
  int v5; // eax
  const char *v6; // r9
  CHAR *lpMultiByteStr; // rax
  int v8; // r9d
  const char *v9; // r9
  LPSTR v11[2]; // [rsp+50h] [rbp-30h] BYREF
  int cbMultiByte[4]; // [rsp+60h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  v2 = a2;
  if ( a2[2] )
  {
    *(_OWORD *)v11 = 0;
    *(_QWORD *)cbMultiByte = 0;
    *(_QWORD *)&cbMultiByte[2] = 15;
    LOBYTE(v11[0]) = 0;
    if ( (unsigned __int64)a2[3] <= 7 )
      v4 = (const WCHAR *)a2;
    else
      v4 = (const WCHAR *)*a2;
    v5 = WideCharToMultiByte(0xFDE9u, 0x80u, v4, *((_DWORD *)a2 + 4), 0, 0, 0, 0);
    if ( !v5 )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x2F,
        (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\CflApiJson.h",
        v6);
    std::string::resize(v11, v5, 0);
    lpMultiByteStr = (CHAR *)v11;
    if ( *(_QWORD *)&cbMultiByte[2] > 0xFu )
      lpMultiByteStr = v11[0];
    v8 = *((_DWORD *)v2 + 4);
    if ( (unsigned __int64)v2[3] > 7 )
      v2 = (__int64 *)*v2;
    if ( !WideCharToMultiByte(0xFDE9u, 0x80u, (LPCWCH)v2, v8, lpMultiByteStr, cbMultiByte[0], 0, 0) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x34,
        (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\CflApiJson.h",
        v9);
    *(_OWORD *)a1 = *(_OWORD *)v11;
    *(_OWORD *)(a1 + 16) = *(_OWORD *)cbMultiByte;
    *(_QWORD *)cbMultiByte = 0;
    *(_QWORD *)&cbMultiByte[2] = 15;
    LOBYTE(v11[0]) = 0;
    std::string::~string(v11);
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
0x180021000  mov     [rsp-18h+arg_10], rbx
0x180021005  mov     [rsp-18h+arg_18], rdi
0x18002100a  push    rbp
0x18002100b  push    r14
0x18002100d  push    r15
0x18002100f  mov     rbp, rsp
0x180021012  sub     rsp, 80h
0x180021019  mov     rax, cs:__security_cookie
0x180021020  xor     rax, rsp
0x180021023  mov     [rbp+var_10], rax
0x180021027  mov     rdi, rdx
0x18002102a  mov     rbx, rcx
0x18002102d  mov     [rbp+var_38], rcx
0x180021031  xor     r15d, r15d
0x180021034  xorps   xmm0, xmm0
0x180021037  cmp     [rdx+10h], r15
0x18002103b  jnz     short loc_180021054
0x18002103d  movups  xmmword ptr [rcx], xmm0
0x180021040  mov     [rcx+10h], r15
0x180021044  mov     qword ptr [rcx+18h], 0Fh
0x18002104c  mov     [rcx], r15b
0x18002104f  jmp     loc_18002112F
0x180021054  movups  xmmword ptr [rbp+var_30], xmm0
0x180021058  mov     qword ptr [rbp+var_20], r15
0x18002105c  mov     qword ptr [rbp+var_20+8], 0Fh
0x180021064  mov     byte ptr [rbp+var_30], r15b
0x180021068  cmp     qword ptr [rdx+18h], 7
0x18002106d  jbe     short loc_180021074
0x18002106f  mov     r8, [rdx]
0x180021072  jmp     short loc_180021077
0x180021074  mov     r8, rdi; lpWideCharStr
0x180021077  mov     [rsp+80h+lpUsedDefaultChar], r15; lpUsedDefaultChar
0x18002107c  mov     [rsp+80h+lpDefaultChar], r15; lpDefaultChar
0x180021081  mov     [rsp+80h+cbMultiByte], r15d; cbMultiByte
0x180021086  mov     [rsp+80h+lpMultiByteStr], r15; lpMultiByteStr
0x18002108b  mov     r9d, [rdx+10h]; cchWideChar
0x18002108f  mov     edx, 80h; dwFlags
0x180021094  mov     ecx, 0FDE9h; CodePage
0x180021099  call    cs:__imp_WideCharToMultiByte
0x18002109f  mov     rcx, [rbp+18h]; this
0x1800210a3  test    eax, eax
0x1800210a5  jz      loc_18002116C
0x1800210ab  movsxd  rdx, eax
0x1800210ae  xor     r8d, r8d
0x1800210b1  lea     rcx, [rbp+var_30]
0x1800210b5  call    ?resize@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_KD@Z; std::string::resize(unsigned __int64,char)
0x1800210ba  mov     ecx, [rbp+var_20]
0x1800210bd  lea     rax, [rbp+var_30]
0x1800210c1  cmp     qword ptr [rbp+var_20+8], 0Fh
0x1800210c6  cmova   rax, [rbp+var_30]
0x1800210cb  mov     r9d, [rdi+10h]; cchWideChar
0x1800210cf  cmp     qword ptr [rdi+18h], 7
0x1800210d4  jbe     short loc_1800210D9
0x1800210d6  mov     rdi, [rdi]
0x1800210d9  mov     r14, [rbp+18h]
0x1800210dd  mov     [rsp+80h+lpUsedDefaultChar], r15; lpUsedDefaultChar
0x1800210e2  mov     [rsp+80h+lpDefaultChar], r15; lpDefaultChar
0x1800210e7  mov     [rsp+80h+cbMultiByte], ecx; cbMultiByte
0x1800210eb  mov     [rsp+80h+lpMultiByteStr], rax; lpMultiByteStr
0x1800210f0  mov     r8, rdi; lpWideCharStr
0x1800210f3  mov     edx, 80h; dwFlags
0x1800210f8  mov     ecx, 0FDE9h; CodePage
0x1800210fd  call    cs:__imp_WideCharToMultiByte
0x180021103  test    eax, eax
0x180021105  jz      short loc_180021157
0x180021107  movups  xmm0, xmmword ptr [rbp+var_30]
0x18002110b  movups  xmmword ptr [rbx], xmm0
0x18002110e  movups  xmm1, xmmword ptr [rbp+var_20]
0x180021112  movups  xmmword ptr [rbx+10h], xmm1
0x180021116  mov     qword ptr [rbp+var_20], r15
0x18002111a  mov     qword ptr [rbp+var_20+8], 0Fh
0x180021122  mov     byte ptr [rbp+var_30], r15b
0x180021126  lea     rcx, [rbp+var_30]
0x18002112a  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18002112f  mov     rax, rbx
0x180021132  mov     rcx, [rbp+var_10]
0x180021136  xor     rcx, rsp; StackCookie
0x180021139  call    __security_check_cookie
0x18002113e  lea     r11, [rsp+80h+var_s0]
0x180021146  mov     rbx, [r11+30h]
0x18002114a  mov     rdi, [r11+38h]
0x18002114e  mov     rsp, r11
0x180021151  pop     r15
0x180021153  pop     r14
0x180021155  pop     rbp
0x180021156  retn
0x180021157  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cfl\\api\\lib\\C"...
0x18002115e  mov     edx, 34h ; '4'; void *
0x180021163  mov     rcx, r14; this
0x180021166  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18002116c  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cfl\\api\\lib\\C"...
0x180021173  mov     edx, 2Fh ; '/'; void *
0x180021178  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
