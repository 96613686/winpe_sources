# Windows::Internal::Feedback::SiufPayloadImpl::GetVersion(uint *)

- ea: `0x140016818`
- end: `0x140016916`
- name: `?GetVersion@SiufPayloadImpl@Feedback@Internal@Windows@@QEAAJPEAI@Z`
- size: `254`
- prototype: `__int64 __fastcall(Windows::Internal::Feedback::SiufPayloadImpl *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14000e290`

## callees

- `0x14000ac50`
- `0x140016818`
- `0x140018850`
- `0x140019610`
- `0x14001a010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14001689b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14001689b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::Feedback::SiufPayloadImpl::GetVersion(__int64 **this, unsigned int *a2)
{
  __int64 *v4; // rdi
  __int64 v5; // rsi
  HRESULT v6; // eax
  int v7; // edx
  unsigned int v8; // r8d
  int v9; // eax
  unsigned int v10; // edi
  double v11; // [rsp+20h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+28h] [rbp-30h] BYREF
  HSTRING string; // [rsp+40h] [rbp-18h] BYREF

  if ( a2 )
  {
    *a2 = 1;
    v11 = DOUBLE_1_0;
    v4 = *this;
    v5 = **this;
    string = 0;
    v6 = WindowsCreateStringReference(L"Version", 7u, &hstringHeader, &string);
    if ( v6 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v6, v7, v8);
      JUMPOUT(0x140016915LL);
    }
    v9 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, double *))(v5 + 88))(v4, string, &v11);
    v10 = v9;
    if ( v9 >= 0 )
    {
      *a2 = (int)v11;
      return 0;
    }
    else
    {
      SuifTraceLogging::WriteErrorTraceFormat(
        v9,
        63,
        "Windows::Internal::Feedback::SiufPayloadImpl::GetVersion",
        (wchar_t *)L"GetNamedNumber failed to get SIUF payload Version");
      return v10;
    }
  }
  else
  {
    SuifTraceLogging::WriteErrorTraceFormat(
      -2147467261,
      52,
      "Windows::Internal::Feedback::SiufPayloadImpl::GetVersion",
      (wchar_t *)L"Version pointer is null.");
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x140016818  mov     [rsp+arg_10], rbx
0x14001681d  mov     [rsp+arg_18], rsi
0x140016822  push    rdi
0x140016823  sub     rsp, 50h
0x140016827  mov     rax, cs:__security_cookie
0x14001682e  xor     rax, rsp
0x140016831  mov     [rsp+58h+var_10], rax
0x140016836  mov     rbx, rdx
0x140016839  test    rdx, rdx
0x14001683c  jnz     short loc_140016862
0x14001683e  lea     r9, aVersionPointer; "Version pointer is null."
0x140016845  lea     r8, aWindowsInterna_0; "Windows::Internal::Feedback::SiufPayloa"...
0x14001684c  lea     edx, [rbx+34h]; int
0x14001684f  mov     ebx, 80004003h
0x140016854  mov     ecx, ebx; int
0x140016856  call    ?WriteErrorTraceFormat@SuifTraceLogging@@SAXJHPEBDPEBGZZ; SuifTraceLogging::WriteErrorTraceFormat(long,int,char const *,ushort const *,...)
0x14001685b  mov     eax, ebx
0x14001685d  jmp     loc_1400168F0
0x140016862  mov     dword ptr [rdx], 1
0x140016868  movsd   xmm0, cs:__real@3ff0000000000000
0x140016870  movsd   [rsp+58h+var_38], xmm0
0x140016876  mov     rdi, [rcx]
0x140016879  mov     rsi, [rdi]
0x14001687c  mov     [rsp+58h+string], 0
0x140016885  lea     r9, [rsp+58h+string]; string
0x14001688a  lea     r8, [rsp+58h+hstringHeader]; hstringHeader
0x14001688f  mov     edx, 7; length
0x140016894  lea     rcx, aVersion; "Version"
0x14001689b  call    cs:__imp_WindowsCreateStringReference
0x1400168a2  nop     dword ptr [rax+rax+00h]
0x1400168a7  test    eax, eax
0x1400168a9  js      short loc_14001690E
0x1400168ab  lea     r8, [rsp+58h+var_38]
0x1400168b0  mov     rdx, [rsp+58h+string]
0x1400168b5  mov     rcx, rdi
0x1400168b8  mov     rax, [rsi+58h]
0x1400168bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400168c1  mov     edi, eax
0x1400168c3  test    eax, eax
0x1400168c5  jns     short loc_1400168E5
0x1400168c7  lea     r9, aGetnamednumber; "GetNamedNumber failed to get SIUF paylo"...
0x1400168ce  lea     r8, aWindowsInterna_0; "Windows::Internal::Feedback::SiufPayloa"...
0x1400168d5  mov     edx, 3Fh ; '?'; int
0x1400168da  mov     ecx, eax; int
0x1400168dc  call    ?WriteErrorTraceFormat@SuifTraceLogging@@SAXJHPEBDPEBGZZ; SuifTraceLogging::WriteErrorTraceFormat(long,int,char const *,ushort const *,...)
0x1400168e1  mov     eax, edi
0x1400168e3  jmp     short loc_1400168F0
0x1400168e5  cvttsd2si rax, [rsp+58h+var_38]
0x1400168ec  mov     [rbx], eax
0x1400168ee  xor     eax, eax
0x1400168f0  mov     rcx, [rsp+58h+var_10]
0x1400168f5  xor     rcx, rsp; StackCookie
0x1400168f8  call    __security_check_cookie
0x1400168fd  mov     rbx, [rsp+58h+arg_10]
0x140016902  mov     rsi, [rsp+58h+arg_18]
0x140016907  add     rsp, 50h
0x14001690b  pop     rdi
0x14001690c  retn
0x14001690e  mov     ecx, eax; this
0x140016910  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
