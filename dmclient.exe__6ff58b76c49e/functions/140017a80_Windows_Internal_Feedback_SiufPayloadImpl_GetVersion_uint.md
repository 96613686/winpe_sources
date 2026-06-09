# Windows::Internal::Feedback::SiufPayloadImpl::GetVersion(uint *)

- ea: `0x140017a80`
- end: `0x140017b77`
- name: `?GetVersion@SiufPayloadImpl@Feedback@Internal@Windows@@QEAAJPEAI@Z`
- size: `247`
- prototype: `__int64 __fastcall(__int64 **this, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14000dd30`

## callees

- `0x14000a9f0`
- `0x140017a80`
- `0x140017fbc`
- `0x1400187e0`
- `0x140019010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140017b03`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140017b03`

## pseudocode

```c
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
      JUMPOUT(0x140017B76LL);
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
0x140017a80  mov     [rsp+arg_10], rbx
0x140017a85  mov     [rsp+arg_18], rsi
0x140017a8a  push    rdi
0x140017a8b  sub     rsp, 50h
0x140017a8f  mov     rax, cs:__security_cookie
0x140017a96  xor     rax, rsp
0x140017a99  mov     [rsp+58h+var_10], rax
0x140017a9e  mov     rbx, rdx
0x140017aa1  test    rdx, rdx
0x140017aa4  jnz     short loc_140017ACA
0x140017aa6  lea     r9, aVersionPointer; "Version pointer is null."
0x140017aad  lea     r8, aWindowsInterna_0; "Windows::Internal::Feedback::SiufPayloa"...
0x140017ab4  lea     edx, [rbx+34h]; int
0x140017ab7  mov     ebx, 80004003h
0x140017abc  mov     ecx, ebx; int
0x140017abe  call    ?WriteErrorTraceFormat@SuifTraceLogging@@SAXJHPEBDPEBGZZ; SuifTraceLogging::WriteErrorTraceFormat(long,int,char const *,ushort const *,...)
0x140017ac3  mov     eax, ebx
0x140017ac5  jmp     loc_140017B52
0x140017aca  mov     dword ptr [rdx], 1
0x140017ad0  movsd   xmm0, cs:__real@3ff0000000000000
0x140017ad8  movsd   [rsp+58h+var_38], xmm0
0x140017ade  mov     rdi, [rcx]
0x140017ae1  mov     rsi, [rdi]
0x140017ae4  mov     [rsp+58h+string], 0
0x140017aed  lea     r9, [rsp+58h+string]; string
0x140017af2  lea     r8, [rsp+58h+hstringHeader]; hstringHeader
0x140017af7  mov     edx, 7; length
0x140017afc  lea     rcx, aVersion; "Version"
0x140017b03  call    cs:__imp_WindowsCreateStringReference
0x140017b09  test    eax, eax
0x140017b0b  js      short loc_140017B6F
0x140017b0d  lea     r8, [rsp+58h+var_38]
0x140017b12  mov     rdx, [rsp+58h+string]
0x140017b17  mov     rcx, rdi
0x140017b1a  mov     rax, [rsi+58h]
0x140017b1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017b23  mov     edi, eax
0x140017b25  test    eax, eax
0x140017b27  jns     short loc_140017B47
0x140017b29  lea     r9, aGetnamednumber; "GetNamedNumber failed to get SIUF paylo"...
0x140017b30  lea     r8, aWindowsInterna_0; "Windows::Internal::Feedback::SiufPayloa"...
0x140017b37  mov     edx, 3Fh ; '?'; int
0x140017b3c  mov     ecx, eax; int
0x140017b3e  call    ?WriteErrorTraceFormat@SuifTraceLogging@@SAXJHPEBDPEBGZZ; SuifTraceLogging::WriteErrorTraceFormat(long,int,char const *,ushort const *,...)
0x140017b43  mov     eax, edi
0x140017b45  jmp     short loc_140017B52
0x140017b47  cvttsd2si rax, [rsp+58h+var_38]
0x140017b4e  mov     [rbx], eax
0x140017b50  xor     eax, eax
0x140017b52  mov     rcx, [rsp+58h+var_10]
0x140017b57  xor     rcx, rsp; StackCookie
0x140017b5a  call    __security_check_cookie
0x140017b5f  mov     rbx, [rsp+58h+arg_10]
0x140017b64  mov     rsi, [rsp+58h+arg_18]
0x140017b69  add     rsp, 50h
0x140017b6d  pop     rdi
0x140017b6e  retn
0x140017b6f  mov     ecx, eax; this
0x140017b71  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
