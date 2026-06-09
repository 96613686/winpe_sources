# win_dox::Uri::GetAbsoluteUri(void)

- ea: `0x140055e58`
- end: `0x140055f4b`
- name: `?GetAbsoluteUri@Uri@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ`
- size: `243`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `48`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140028e54`
- `0x140028f98`
- `0x1400290d8`
- `0x1400292a4`
- `0x140029488`
- `0x1400295a8`
- `0x140029768`
- `0x140029c54`
- `0x140029e58`
- `0x14002a054`
- `0x14002a1c8`
- `0x14002c080`
- `0x14002c23c`
- `0x14002c3e0`
- `0x14002c6c0`
- `0x14002ca60`
- `0x14002ce00`
- `0x14002d190`
- `0x14002d530`
- `0x14002d8d0`
- `0x14002dd30`
- `0x14002e220`
- `0x14002e5f0`
- `0x14002e980`
- `0x14002ea50`
- `0x14002ede8`
- `0x140030210`
- `0x140030480`
- `0x1400307e4`
- `0x1400309fc`
- `0x1400318f0`
- `0x140031d80`
- `0x1400353d0`
- `0x1400355e0`
- `0x140035d68`
- `0x14003ccc0`
- `0x14003cef0`
- `0x14003d130`
- `0x14003d6f0`
- `0x14003d840`
- `0x14003dee0`
- `0x14003e270`
- `0x14003efa0`
- `0x14003f350`
- `0x14003f740`
- `0x14003fbd0`
- `0x1400400a0`
- `0x1400404e0`

## callees

- `0x140002070`
- `0x140002c68`
- `0x140002c74`
- `0x140007654`
- `0x14001b26c`
- `0x14001bd50`
- `0x140055e58`
- `0x140063010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x140055f21`
- `OLEAUT32!__imp_SysFreeString` at `0x140055f21`

## string_xrefs

- `0x140055eba`: `Call to GetAbsoluteUri failed with HResult 0x%X.`

## pseudocode

```c
OLECHAR *__fastcall win_dox::Uri::GetAbsoluteUri(__int64 *a1, OLECHAR *a2)
{
  __int64 v3; // rcx
  signed int v4; // edi
  __int64 v5; // rdx
  __int64 v6; // r9
  BSTR bstrString[2]; // [rsp+40h] [rbp-4C8h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+50h] [rbp-4B8h] BYREF
  wchar_t v10[512]; // [rsp+F0h] [rbp-418h] BYREF

  bstrString[0] = a2;
  v3 = *a1;
  bstrString[0] = 0;
  v4 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v3 + 56LL))(v3, bstrString);
  if ( v4 < 0 )
  {
    memset_0(v10, 0, sizeof(v10));
    StringCchPrintfW(v10, 0x200u, L"Call to GetAbsoluteUri failed with HResult 0x%X.", (unsigned int)v4);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      v5,
      "(no filename)",
      v6,
      0x8Du,
      v4,
      (struct win_musl::TStringEllipseBase *)v10);
    throw (SplException::THResultException *)pExceptionObject;
  }
  std::wstring::wstring((__int64)a2, (__int64)bstrString[0]);
  SysFreeString(bstrString[0]);
  return a2;
}

```

## disassembly

```asm
0x140055e58  mov     [rsp+arg_10], rbx
0x140055e5d  push    rdi
0x140055e5e  sub     rsp, 500h
0x140055e65  mov     rax, cs:__security_cookie
0x140055e6c  xor     rax, rsp
0x140055e6f  mov     [rsp+508h+var_18], rax
0x140055e77  mov     [rsp+508h+bstrString], rdx
0x140055e7c  mov     rbx, rdx
0x140055e7f  mov     rcx, [rcx]
0x140055e82  lea     rdx, [rsp+508h+bstrString]
0x140055e87  mov     [rsp+508h+bstrString], 0
0x140055e90  mov     rax, [rcx]
0x140055e93  mov     rax, [rax+38h]
0x140055e97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140055e9c  mov     edi, eax
0x140055e9e  test    eax, eax
0x140055ea0  jns     short loc_140055F0F
0x140055ea2  xor     edx, edx; Val
0x140055ea4  lea     rcx, [rsp+508h+var_418]; void *
0x140055eac  mov     r8d, 400h; Size
0x140055eb2  call    memset_0
0x140055eb7  mov     r9d, edi
0x140055eba  lea     r8, aCallToGetabsol; "Call to GetAbsoluteUri failed with HRes"...
0x140055ec1  mov     edx, 200h; unsigned __int64
0x140055ec6  lea     rcx, [rsp+508h+var_418]; wchar_t *
0x140055ece  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x140055ed3  lea     rax, [rsp+508h+var_418]
0x140055edb  mov     [rsp+508h+var_4D8], rax; struct win_musl::TStringEllipseBase *
0x140055ee0  lea     r8, aNoFilename; "(no filename)"
0x140055ee7  mov     [rsp+508h+var_4E0], edi; unsigned int
0x140055eeb  lea     rcx, [rsp+508h+pExceptionObject]; this
0x140055ef0  mov     [rsp+508h+var_4E8], 8Dh; unsigned int
0x140055ef8  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x140055efd  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x140055f04  lea     rcx, [rsp+508h+pExceptionObject]; pExceptionObject
0x140055f09  call    _CxxThrowException_0
0x140055f0f  mov     rdx, [rsp+508h+bstrString]
0x140055f14  mov     rcx, rbx
0x140055f17  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x140055f1c  mov     rcx, [rsp+508h+bstrString]; bstrString
0x140055f21  call    cs:__imp_SysFreeString
0x140055f27  mov     rax, rbx
0x140055f2a  mov     rcx, [rsp+508h+var_18]
0x140055f32  xor     rcx, rsp; StackCookie
0x140055f35  call    __security_check_cookie
0x140055f3a  mov     rbx, [rsp+508h+arg_10]
0x140055f42  add     rsp, 500h
0x140055f49  pop     rdi
0x140055f4a  retn
```
