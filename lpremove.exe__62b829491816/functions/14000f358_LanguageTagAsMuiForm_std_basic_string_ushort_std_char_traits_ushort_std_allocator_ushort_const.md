# LanguageTagAsMuiForm(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x14000f358`
- end: `0x14000f463`
- name: `?LanguageTagAsMuiForm@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@@Z`
- size: `267`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000eeb8`

## callees

- `0x140002190`
- `0x1400042a4`
- `0x14000f358`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14000f3c8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14000f3c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14000f3e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14000f3e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000f3af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000f3af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000f38a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000f43b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000f38a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000f43b`
- `Bcp47Langs!Bcp47GetMuiForm` at `0x14000f3d8`
- `Bcp47Langs!Bcp47GetMuiForm` at `0x14000f3d8`

## pseudocode

```c
_QWORD *__fastcall LanguageTagAsMuiForm(_QWORD *a1, __int64 *a2)
{
  UINT32 v4; // edx
  PCWSTR StringRawBuffer; // rax
  unsigned __int64 v6; // r8
  int *v7; // rdx
  HSTRING v9[2]; // [rsp+20h] [rbp-48h] BYREF
  HSTRING string; // [rsp+30h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-30h] BYREF

  WindowsDeleteString(0);
  v9[0] = 0;
  v4 = *((_DWORD *)a2 + 4);
  if ( (unsigned __int64)a2[3] > 7 )
    a2 = (__int64 *)*a2;
  if ( WindowsCreateStringReference((PCWSTR)a2, v4, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  if ( (int)Bcp47GetMuiForm(string, v9) < 0 )
  {
    *(_OWORD *)a1 = 0;
    a1[2] = 0;
    a1[3] = 0;
    v6 = 0;
    v7 = &dword_140013804;
  }
  else
  {
    StringRawBuffer = WindowsGetStringRawBuffer(v9[0], 0);
    *(_OWORD *)a1 = 0;
    a1[2] = 0;
    a1[3] = 0;
    v6 = -1;
    do
      ++v6;
    while ( StringRawBuffer[v6] );
    v7 = (int *)StringRawBuffer;
  }
  std::wstring::_Construct<1,unsigned short const *>(a1, v7, v6);
  if ( v9[0] )
    WindowsDeleteString(v9[0]);
  return a1;
}

```

## disassembly

```asm
0x14000f358  mov     [rsp+arg_10], rbx
0x14000f35d  mov     [rsp+arg_18], rsi
0x14000f362  push    rdi
0x14000f363  sub     rsp, 60h
0x14000f367  mov     rax, cs:__security_cookie
0x14000f36e  xor     rax, rsp
0x14000f371  mov     [rsp+68h+var_18], rax
0x14000f376  mov     rdi, rdx
0x14000f379  mov     rbx, rcx
0x14000f37c  mov     [rsp+68h+var_48], rcx
0x14000f381  xor     esi, esi
0x14000f383  mov     [rsp+68h+var_48], rsi
0x14000f388  xor     ecx, ecx; string
0x14000f38a  call    cs:__imp_WindowsDeleteString
0x14000f390  mov     [rsp+68h+var_48], rsi
0x14000f395  mov     edx, [rdi+10h]; length
0x14000f398  cmp     qword ptr [rdi+18h], 7
0x14000f39d  jbe     short loc_14000F3A2
0x14000f39f  mov     rdi, [rdi]
0x14000f3a2  lea     r9, [rsp+68h+string]; string
0x14000f3a7  lea     r8, [rsp+68h+hstringHeader]; hstringHeader
0x14000f3ac  mov     rcx, rdi; sourceString
0x14000f3af  call    cs:__imp_WindowsCreateStringReference
0x14000f3b5  test    eax, eax
0x14000f3b7  jns     short loc_14000F3CE
0x14000f3b9  xor     r9d, r9d; lpArguments
0x14000f3bc  xor     r8d, r8d; nNumberOfArguments
0x14000f3bf  lea     edx, [r9+1]; dwExceptionFlags
0x14000f3c3  mov     ecx, 0C000000Dh; dwExceptionCode
0x14000f3c8  call    cs:__imp_RaiseException
0x14000f3ce  lea     rdx, [rsp+68h+var_48]
0x14000f3d3  mov     rcx, [rsp+68h+string]
0x14000f3d8  call    cs:__imp_Bcp47GetMuiForm
0x14000f3de  test    eax, eax
0x14000f3e0  js      short loc_14000F410
0x14000f3e2  xor     edx, edx; length
0x14000f3e4  mov     rcx, [rsp+68h+var_48]; string
0x14000f3e9  call    cs:__imp_WindowsGetStringRawBuffer
0x14000f3ef  xorps   xmm0, xmm0
0x14000f3f2  movups  xmmword ptr [rbx], xmm0
0x14000f3f5  mov     [rbx+10h], rsi
0x14000f3f9  mov     [rbx+18h], rsi
0x14000f3fd  or      r8, 0FFFFFFFFFFFFFFFFh
0x14000f401  inc     r8
0x14000f404  cmp     [rax+r8*2], si
0x14000f409  jnz     short loc_14000F401
0x14000f40b  mov     rdx, rax
0x14000f40e  jmp     short loc_14000F428
0x14000f410  xorps   xmm0, xmm0
0x14000f413  movups  xmmword ptr [rbx], xmm0
0x14000f416  mov     [rbx+10h], rsi
0x14000f41a  mov     [rbx+18h], rsi
0x14000f41e  xor     r8d, r8d
0x14000f421  lea     rdx, dword_140013804
0x14000f428  mov     rcx, rbx
0x14000f42b  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14000f430  nop
0x14000f431  mov     rcx, [rsp+68h+var_48]; string
0x14000f436  test    rcx, rcx
0x14000f439  jz      short loc_14000F441
0x14000f43b  call    cs:__imp_WindowsDeleteString
0x14000f441  mov     rax, rbx
0x14000f444  mov     rcx, [rsp+68h+var_18]
0x14000f449  xor     rcx, rsp; StackCookie
0x14000f44c  call    __security_check_cookie
0x14000f451  lea     r11, [rsp+68h+var_8]
0x14000f456  mov     rbx, [r11+20h]
0x14000f45a  mov     rsi, [r11+28h]
0x14000f45e  mov     rsp, r11
0x14000f461  pop     rdi
0x14000f462  retn
```
