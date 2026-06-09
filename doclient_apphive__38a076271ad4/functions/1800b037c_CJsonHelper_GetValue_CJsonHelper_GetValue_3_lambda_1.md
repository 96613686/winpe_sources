# CJsonHelper::_GetValue__CJsonHelper::GetValue_::_3_::_lambda_1___

- ea: `0x1800b037c`
- end: `0x1800b05b2`
- name: `CJsonHelper::_GetValue__CJsonHelper::GetValue_::_3_::_lambda_1___`
- size: `566`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800af3e8`

## callees

- `0x180007c24`
- `0x18000933c`
- `0x18000ef98`
- `0x18009c2f0`
- `0x1800a979c`
- `0x1800b037c`
- `0x1800f82f0`
- `0x180108e50`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b0555`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b0555`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b0507`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b0547`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b056b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b0507`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b0547`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b056b`

## string_xrefs

- `0x1800b03b3`: `C:\__w\1\s\src\DeliveryOptimization\Util\win10\JsonHelper.cpp`
- `0x1800b0465`: `C:\__w\1\s\src\DeliveryOptimization\Util\win10\JsonHelper.cpp`
- `0x1800b0531`: `C:\__w\1\s\src\DeliveryOptimization\Util\win10\JsonHelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall CJsonHelper::_GetValue__CJsonHelper::GetValue_::_3_::_lambda_1___(
        __int64 *a1,
        __int64 a2,
        void **a3)
{
  __int64 v4; // rdi
  int v5; // ebx
  __int64 (__fastcall *v6)(__int64, _QWORD, __int64 *); // rbx
  HSTRING v7; // rdx
  __int64 v8; // rax
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // r9
  __int64 (__fastcall ***v12)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, HSTRING *); // rbx
  int v15; // eax
  WCHAR *StringRawBuffer; // rax
  __int64 v17; // rcx
  _QWORD v19[4]; // [rsp+20h] [rbp-60h] BYREF
  _BYTE v20[24]; // [rsp+40h] [rbp-40h] BYREF
  __int64 v21; // [rsp+58h] [rbp-28h]
  int v22; // [rsp+60h] [rbp-20h] BYREF
  __int64 v23; // [rsp+68h] [rbp-18h] BYREF
  HSTRING string; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  v4 = *a1;
  if ( !*a1 )
  {
    v5 = -2147467259;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF3,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\JsonHelper.cpp",
      (const char *)0x80004005LL,
      v19[0]);
    return (unsigned int)v5;
  }
  v23 = 0;
  if ( a2 )
  {
    v6 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v4 + 48LL);
    UTF8toWstr(v19, a2, 0);
    v7 = (HSTRING)v19;
    if ( v19[3] > 7u )
      v7 = (HSTRING)v19[0];
    string = v7;
    v8 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v20, &string);
    v5 = v6(v4, *(_QWORD *)(v8 + 24), &v23);
    v21 = 0;
    std::wstring::~wstring(v19);
    if ( v5 < 0 )
      goto LABEL_23;
  }
  else
  {
    v12 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))a1[1];
    if ( v12 )
    {
      v9 = (**v12)(v12, &GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e, &v23);
      v5 = v9;
      if ( v9 < 0 )
      {
        v10 = 252;
        goto LABEL_9;
      }
    }
    else
    {
      v9 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v4)(
             v4,
             &GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e,
             &v23);
      v5 = v9;
      if ( v9 < 0 )
      {
        v10 = 256;
        goto LABEL_9;
      }
    }
  }
  v22 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v23 + 48LL))(v23, &v22);
  v5 = v9;
  if ( v9 < 0 )
  {
    v10 = 260;
LABEL_9:
    v11 = (unsigned int)v9;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\JsonHelper.cpp",
      (const char *)v11,
      v19[0]);
    goto LABEL_23;
  }
  if ( v22 )
  {
    v13 = v23;
    if ( v22 != 3 )
    {
      v5 = -2147024809;
      v11 = 2147942487LL;
      v10 = 119;
      goto LABEL_10;
    }
    string = 0;
    v14 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v23 + 64LL);
    WindowsDeleteString(0);
    string = 0;
    v15 = v14(v13, &string);
    v5 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x79,
        (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\JsonHelper.cpp",
        (const char *)(unsigned int)v15,
        v19[0]);
      WindowsDeleteString(string);
      goto LABEL_23;
    }
    StringRawBuffer = (WCHAR *)WindowsGetStringRawBuffer(string, 0);
    std::wstring::operator=(*a3, StringRawBuffer);
    WindowsDeleteString(string);
  }
  v5 = 0;
LABEL_23:
  v17 = v23;
  if ( v23 )
  {
    v23 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800b037c  mov     [rsp-18h+arg_18], rbx
0x1800b0381  push    rbp
0x1800b0382  push    rsi
0x1800b0383  push    rdi
0x1800b0384  mov     rbp, rsp
0x1800b0387  sub     rsp, 80h
0x1800b038e  mov     rax, cs:__security_cookie
0x1800b0395  xor     rax, rsp
0x1800b0398  mov     [rbp+var_8], rax
0x1800b039c  mov     rsi, r8
0x1800b039f  mov     rdi, [rcx]
0x1800b03a2  test    rdi, rdi
0x1800b03a5  jnz     short loc_1800B03C9
0x1800b03a7  mov     rcx, [rbp+18h]; this
0x1800b03ab  mov     ebx, 80004005h
0x1800b03b0  mov     r9d, ebx; char *
0x1800b03b3  lea     r8, aCW1SSrcDeliver_40; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800b03ba  mov     edx, 0F3h; void *
0x1800b03bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b03c4  jmp     loc_1800B0591
0x1800b03c9  mov     [rbp+var_18], 0
0x1800b03d1  test    rdx, rdx
0x1800b03d4  jz      loc_1800B047A
0x1800b03da  mov     rax, [rdi]
0x1800b03dd  mov     rbx, [rax+30h]
0x1800b03e1  xor     r8d, r8d
0x1800b03e4  lea     rcx, [rbp+var_60]
0x1800b03e8  call    ?UTF8toWstr@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBD_K@Z; UTF8toWstr(char const *,unsigned __int64)
0x1800b03ed  nop
0x1800b03ee  lea     rdx, [rbp+var_60]
0x1800b03f2  cmp     [rbp+var_48], 7
0x1800b03f7  cmova   rdx, [rbp+var_60]
0x1800b03fc  mov     [rbp+string], rdx
0x1800b0400  lea     rdx, [rbp+string]
0x1800b0404  lea     rcx, [rbp+var_40]
0x1800b0408  call    ??$?0PEB_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x1800b040d  nop
0x1800b040e  lea     r8, [rbp+var_18]
0x1800b0412  mov     rdx, [rax+18h]
0x1800b0416  mov     rcx, rdi
0x1800b0419  mov     rax, rbx
0x1800b041c  call    _guard_dispatch_icall
0x1800b0421  mov     ebx, eax
0x1800b0423  mov     [rbp+var_28], 0
0x1800b042b  lea     rcx, [rbp+var_60]
0x1800b042f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800b0434  test    ebx, ebx
0x1800b0436  js      loc_1800B0573
0x1800b043c  mov     [rbp+var_20], 0
0x1800b0443  mov     rcx, [rbp+var_18]
0x1800b0447  mov     rax, [rcx]
0x1800b044a  lea     rdx, [rbp+var_20]
0x1800b044e  mov     rax, [rax+30h]
0x1800b0452  call    _guard_dispatch_icall
0x1800b0457  mov     ebx, eax
0x1800b0459  test    eax, eax
0x1800b045b  jns     short loc_1800B04D0
0x1800b045d  mov     edx, 104h; void *
0x1800b0462  mov     r9d, eax; char *
0x1800b0465  lea     r8, aCW1SSrcDeliver_40; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800b046c  mov     rcx, [rbp+18h]; this
0x1800b0470  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b0475  jmp     loc_1800B0573
0x1800b047a  mov     rcx, [rcx+8]
0x1800b047e  test    rcx, rcx
0x1800b0481  jz      short loc_1800B04A6
0x1800b0483  mov     rax, [rcx]
0x1800b0486  lea     r8, [rbp+var_18]
0x1800b048a  lea     rdx, _GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e
0x1800b0491  mov     rax, [rax]
0x1800b0494  call    _guard_dispatch_icall
0x1800b0499  mov     ebx, eax
0x1800b049b  test    eax, eax
0x1800b049d  jns     short loc_1800B043C
0x1800b049f  mov     edx, 0FCh
0x1800b04a4  jmp     short loc_1800B0462
0x1800b04a6  mov     rax, [rdi]
0x1800b04a9  lea     r8, [rbp+var_18]
0x1800b04ad  lea     rdx, _GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e
0x1800b04b4  mov     rcx, rdi
0x1800b04b7  mov     rax, [rax]
0x1800b04ba  call    _guard_dispatch_icall
0x1800b04bf  mov     ebx, eax
0x1800b04c1  test    eax, eax
0x1800b04c3  jns     loc_1800B043C
0x1800b04c9  mov     edx, 100h
0x1800b04ce  jmp     short loc_1800B0462
0x1800b04d0  mov     eax, [rbp+var_20]
0x1800b04d3  test    eax, eax
0x1800b04d5  jz      loc_1800B0571
0x1800b04db  mov     rdi, [rbp+var_18]
0x1800b04df  cmp     eax, 3
0x1800b04e2  jz      short loc_1800B04F6
0x1800b04e4  mov     ebx, 80070057h
0x1800b04e9  mov     r9d, ebx
0x1800b04ec  mov     edx, 77h ; 'w'
0x1800b04f1  jmp     loc_1800B0465
0x1800b04f6  mov     [rbp+string], 0
0x1800b04fe  mov     rax, [rdi]
0x1800b0501  mov     rbx, [rax+40h]
0x1800b0505  xor     ecx, ecx; string
0x1800b0507  call    cs:__imp_WindowsDeleteString
0x1800b050d  mov     [rbp+string], 0
0x1800b0515  lea     rdx, [rbp+string]
0x1800b0519  mov     rcx, rdi
0x1800b051c  mov     rax, rbx
0x1800b051f  call    _guard_dispatch_icall
0x1800b0524  mov     ebx, eax
0x1800b0526  test    eax, eax
0x1800b0528  jns     short loc_1800B054F
0x1800b052a  mov     rcx, [rbp+18h]; this
0x1800b052e  mov     r9d, eax; char *
0x1800b0531  lea     r8, aCW1SSrcDeliver_40; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800b0538  mov     edx, 79h ; 'y'; void *
0x1800b053d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b0542  nop
0x1800b0543  mov     rcx, [rbp+string]; string
0x1800b0547  call    cs:__imp_WindowsDeleteString
0x1800b054d  jmp     short loc_1800B0573
0x1800b054f  xor     edx, edx; length
0x1800b0551  mov     rcx, [rbp+string]; string
0x1800b0555  call    cs:__imp_WindowsGetStringRawBuffer
0x1800b055b  mov     rdx, rax; Src
0x1800b055e  mov     rcx, [rsi]; void *
0x1800b0561  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@QEB_W@Z; std::wstring::operator=(wchar_t const * const)
0x1800b0566  nop
0x1800b0567  mov     rcx, [rbp+string]; string
0x1800b056b  call    cs:__imp_WindowsDeleteString
0x1800b0571  xor     ebx, ebx
0x1800b0573  mov     rcx, [rbp+var_18]
0x1800b0577  test    rcx, rcx
0x1800b057a  jz      short loc_1800B0591
0x1800b057c  mov     [rbp+var_18], 0
0x1800b0584  mov     rdx, [rcx]
0x1800b0587  mov     rax, [rdx+10h]
0x1800b058b  call    _guard_dispatch_icall
0x1800b0590  nop
0x1800b0591  mov     eax, ebx
0x1800b0593  mov     rcx, [rbp+var_8]
0x1800b0597  xor     rcx, rsp; StackCookie
0x1800b059a  call    __security_check_cookie
0x1800b059f  mov     rbx, [rsp+80h+arg_18]
0x1800b05a7  add     rsp, 80h
0x1800b05ae  pop     rdi
0x1800b05af  pop     rsi
0x1800b05b0  pop     rbp
0x1800b05b1  retn
```
