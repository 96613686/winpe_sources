# win_musl::CreateComObject<IOpcFactory>(_GUID const &,ulong)

- ea: `0x140027f20`
- end: `0x140028023`
- name: `??$CreateComObject@UIOpcFactory@@@win_musl@@YA?AV?$scope@PEAUIOpcFactory@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@AEBU_GUID@@K@Z`
- size: `259`
- prototype: `LPVOID *__fastcall(LPVOID *ppv)`
- caller_count: `8`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14002f5ac`
- `0x1400306dc`
- `0x140035f18`
- `0x140038508`
- `0x14003ae70`
- `0x14003e5b0`
- `0x14003e950`
- `0x14005a304`

## callees

- `0x140002070`
- `0x140002c68`
- `0x140002c74`
- `0x140007654`
- `0x14001b26c`
- `0x140027f20`
- `0x140041030`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140027f85`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140027f85`

## string_xrefs

- `0x140027fa9`: `Call to CoCreateInstance failed with HResult 0x%X.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
LPVOID *__fastcall win_musl::CreateComObject<IOpcFactory>(LPVOID *ppv)
{
  HRESULT Instance; // edi
  _BYTE pExceptionObject[160]; // [rsp+50h] [rbp-4B8h] BYREF
  wchar_t v5[512]; // [rsp+F0h] [rbp-418h] BYREF

  *ppv = 0;
  win_scope::detail::scope_helper<IOpcFactory *,win_scope::const_policies<win_scope::com_policies>>::reset(ppv, 0);
  *ppv = 0;
  Instance = CoCreateInstance(
               &GUID_6b2d6ba0_9f3e_4f27_920b_313cc426a39e,
               0,
               1u,
               &GUID_6d0b4446_cd73_4ab3_94f4_8ccdf6116154,
               ppv);
  if ( Instance < 0 )
  {
    memset_0(v5, 0, sizeof(v5));
    StringCchPrintfW(v5, 0x200u, L"Call to CoCreateInstance failed with HResult 0x%X.", (unsigned int)Instance);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x169u,
      Instance,
      (struct win_musl::TStringEllipseBase *)v5);
    throw (SplException::THResultException *)pExceptionObject;
  }
  return ppv;
}

```

## disassembly

```asm
0x140027f20  mov     [rsp+arg_8], rbx
0x140027f25  push    rdi
0x140027f26  sub     rsp, 500h
0x140027f2d  mov     rax, cs:__security_cookie
0x140027f34  xor     rax, rsp
0x140027f37  mov     [rsp+508h+var_18], rax
0x140027f3f  mov     rbx, rcx
0x140027f42  mov     [rsp+508h+var_4C0], rcx
0x140027f47  mov     [rsp+508h+var_4C8], 0
0x140027f4f  mov     qword ptr [rcx], 0
0x140027f56  mov     edi, 1
0x140027f5b  mov     [rsp+508h+var_4C8], edi
0x140027f5f  xor     edx, edx
0x140027f61  call    ?reset@?$scope_helper@PEAUIOpcFactory@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@detail@win_scope@@SAXAEAV?$scope@PEAUIOpcFactory@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@3@PEAUIOpcFactory@@@Z; win_scope::detail::scope_helper<IOpcFactory *,win_scope::const_policies<win_scope::com_policies>>::reset(win_scope::scope<IOpcFactory *,win_scope::const_policies<win_scope::com_policies>> &,IOpcFactory *)
0x140027f66  mov     qword ptr [rbx], 0
0x140027f6d  mov     [rsp+508h+ppv], rbx; ppv
0x140027f72  lea     r9, _GUID_6d0b4446_cd73_4ab3_94f4_8ccdf6116154; riid
0x140027f79  mov     r8d, edi; dwClsContext
0x140027f7c  xor     edx, edx; pUnkOuter
0x140027f7e  lea     rcx, _GUID_6b2d6ba0_9f3e_4f27_920b_313cc426a39e; rclsid
0x140027f85  call    cs:__imp_CoCreateInstance
0x140027f8b  mov     edi, eax
0x140027f8d  test    eax, eax
0x140027f8f  jns     short loc_140027FFE
0x140027f91  xor     edx, edx; Val
0x140027f93  mov     r8d, 400h; Size
0x140027f99  lea     rcx, [rsp+508h+var_418]; void *
0x140027fa1  call    memset_0
0x140027fa6  mov     r9d, edi
0x140027fa9  lea     r8, aCallToCocreate; "Call to CoCreateInstance failed with HR"...
0x140027fb0  mov     edx, 200h; unsigned __int64
0x140027fb5  lea     rcx, [rsp+508h+var_418]; wchar_t *
0x140027fbd  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x140027fc2  lea     rax, [rsp+508h+var_418]
0x140027fca  mov     [rsp+508h+var_4D8], rax; struct win_musl::TStringEllipseBase *
0x140027fcf  mov     [rsp+508h+var_4E0], edi; unsigned int
0x140027fd3  mov     dword ptr [rsp+508h+ppv], 169h; unsigned int
0x140027fdb  lea     r8, aNoFilename; "(no filename)"
0x140027fe2  lea     rcx, [rsp+508h+pExceptionObject]; this
0x140027fe7  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x140027fec  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x140027ff3  lea     rcx, [rsp+508h+pExceptionObject]; pExceptionObject
0x140027ff8  call    _CxxThrowException_0
0x140027ffe  mov     rax, rbx
0x140028001  mov     rcx, [rsp+508h+var_18]
0x140028009  xor     rcx, rsp; StackCookie
0x14002800c  call    __security_check_cookie
0x140028011  mov     rbx, [rsp+508h+arg_8]
0x140028019  add     rsp, 500h
0x140028020  pop     rdi
0x140028021  retn
```
