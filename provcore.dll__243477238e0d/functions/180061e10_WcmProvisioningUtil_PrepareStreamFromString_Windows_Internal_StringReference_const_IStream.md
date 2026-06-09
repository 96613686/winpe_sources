# WcmProvisioningUtil::PrepareStreamFromString(Windows::Internal::StringReference const &,IStream * *)

- ea: `0x180061e10`
- end: `0x180061fd8`
- name: `?PrepareStreamFromString@WcmProvisioningUtil@@YAJAEBVStringReference@Internal@Windows@@PEAPEAUIStream@@@Z`
- size: `456`
- prototype: `HRESULT __fastcall(const Windows::Internal::StringReference *StringRef, IStream **ppStream)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006230c`

## callees

- `0x180002790`
- `0x1800071d4`
- `0x1800071f4`
- `0x18001a0d4`
- `0x180060d40`
- `0x180060de8`
- `0x180061344`
- `0x1800618e8`
- `0x180061e10`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180061e93`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180061f0a`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180061e93`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180061f0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180061e41`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180061e41`

## string_xrefs

- `0x180061ea5`: `onecoreuap\private\net\inc\common\utils\WcmProvisioningUtil.h`
- `0x180061f19`: `onecoreuap\private\net\inc\common\utils\WcmProvisioningUtil.h`
- `0x180061f55`: `onecoreuap\private\net\inc\common\utils\WcmProvisioningUtil.h`
- `0x180061fc3`: `onecoreuap\private\net\inc\common\utils\WcmProvisioningUtil.h`

## pseudocode

```c
HRESULT __fastcall WcmProvisioningUtil::PrepareStreamFromString(
        const Windows::Internal::StringReference *StringRef,
        IStream **ppStream)
{
  const wchar_t *StringRawBuffer; // rbx
  int v4; // eax
  int cbMultiByte; // edi
  unsigned int v7; // eax
  const char *v8; // r8
  HRESULT LastError; // ebx
  HRESULT StreamFrom; // eax
  HRESULT v11; // ebx
  HRESULT v12; // eax
  HRESULT v13; // ebx
  __int64 v14; // [rsp+0h] [rbp-78h] BYREF
  unsigned int stringLength; // [rsp+40h] [rbp-38h] BYREF
  std::vector<char> utf8buffer; // [rsp+48h] [rbp-30h] BYREF
  void *retaddr; // [rsp+78h] [rbp+0h]

  stringLength = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(StringRef->_hstring, &stringLength);
  if ( WcmProvisioningUtil::IsStringConvertedUtf8Xml(StringRawBuffer, stringLength) )
  {
    v4 = WideCharToMultiByte(0xFDE9u, 0x80u, StringRawBuffer, stringLength, 0, 0, 0, 0);
    cbMultiByte = v4;
    if ( !v4 )
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               0x54u,
               "onecoreuap\\private\\net\\inc\\common\\utils\\WcmProvisioningUtil.h");
    try
    {
      memset(&utf8buffer, 0, sizeof(utf8buffer));
      std::vector<char>::_Construct_n<>(&utf8buffer, v4);
      v7 = WideCharToMultiByte(
             0xFDE9u,
             0x80u,
             StringRawBuffer,
             stringLength,
             utf8buffer._Mypair._Myval2._Myfirst,
             cbMultiByte,
             0,
             0);
    }
    catch ( ... )
    {
      return wil::details::in1diag3::Return_CaughtException(retaddr, (unsigned int)&v14, v8);
    }
    if ( !v7 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    0x5Fu,
                    "onecoreuap\\private\\net\\inc\\common\\utils\\WcmProvisioningUtil.h");
      std::vector<unsigned char>::_Tidy(&utf8buffer);
      return LastError;
    }
    StreamFrom = WcmProvisioningUtil::CreateStreamFromArray<char>(utf8buffer._Mypair._Myval2._Myfirst, v7, ppStream);
    v11 = StreamFrom;
    if ( StreamFrom < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        0x61u,
        "onecoreuap\\private\\net\\inc\\common\\utils\\WcmProvisioningUtil.h",
        StreamFrom);
      std::vector<unsigned char>::_Tidy(&utf8buffer);
      return v11;
    }
    std::vector<unsigned char>::_Tidy(&utf8buffer);
    return 0;
  }
  v12 = WcmProvisioningUtil::CreateStreamFromArray<unsigned short>(StringRawBuffer, stringLength, ppStream);
  v13 = v12;
  if ( v12 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    0x67u,
    "onecoreuap\\private\\net\\inc\\common\\utils\\WcmProvisioningUtil.h",
    v12);
  return v13;
}

```

## disassembly

```asm
0x180061e10  mov     [rsp+arg_10], rbx
0x180061e15  mov     [rsp+arg_18], rsi
0x180061e1a  push    rdi
0x180061e1b  sub     rsp, 70h
0x180061e1f  mov     rax, cs:__security_cookie
0x180061e26  xor     rax, rsp
0x180061e29  mov     [rsp+78h+var_18], rax
0x180061e2e  mov     rsi, ppStream
0x180061e31  mov     [rsp+78h+stringLength], 0
0x180061e39  lea     ppStream, [rsp+78h+stringLength]; length
0x180061e3e  mov     StringRef, [StringRef]; string
0x180061e41  call    cs:__imp_WindowsGetStringRawBuffer
0x180061e47  mov     rbx, rax
0x180061e4a  mov     edx, [rsp+78h+stringLength]; StringLength
0x180061e4e  mov     StringRef, rax; String
0x180061e51  call    ?IsStringConvertedUtf8Xml@WcmProvisioningUtil@@YA_NPEBGI@Z; WcmProvisioningUtil::IsStringConvertedUtf8Xml(ushort const *,uint)
0x180061e56  test    al, al
0x180061e58  jz      loc_180061FA6
0x180061e5e  mov     [rsp+78h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180061e67  mov     [rsp+78h+lpDefaultChar], 0; lpDefaultChar
0x180061e70  mov     [rsp+78h+cbMultiByte], 0; cbMultiByte
0x180061e78  mov     [rsp+78h+lpMultiByteStr], 0; lpMultiByteStr
0x180061e81  mov     r9d, [rsp+78h+stringLength]; cchWideChar
0x180061e86  mov     r8, rbx; lpWideCharStr
0x180061e89  mov     edx, 80h; dwFlags
0x180061e8e  mov     ecx, 0FDE9h; CodePage
0x180061e93  call    cs:__imp_WideCharToMultiByte
0x180061e99  movsxd  rdi, eax
0x180061e9c  test    eax, eax
0x180061e9e  jnz     short loc_180061EB9
0x180061ea0  mov     StringRef, [rsp+78h]; callerReturnAddress
0x180061ea5  lea     r8, aOnecoreuapPriv; "onecoreuap\\private\\net\\inc\\common\\"...
0x180061eac  lea     edx, [rax+54h]; lineNumber
0x180061eaf  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180061eb4  jmp     loc_180061F81
0x180061eb9  xorps   xmm0, xmm0
0x180061ebc  movdqu  xmmword ptr [rsp+78h+utf8buffer._Mypair._Myval2._Myfirst], xmm0
0x180061ec2  mov     [rsp+78h+utf8buffer._Mypair._Myval2._Myend], 0
0x180061ecb  mov     ppStream, rdi; _Count
0x180061ece  lea     StringRef, [rsp+78h+utf8buffer]; this
0x180061ed3  call    ??$_Construct_n@$$V@?$vector@DV?$allocator@D@std@@@std@@AEAAX_K@Z; std::vector<char>::_Construct_n<>(unsigned __int64)
0x180061ed8  mov     rax, [rsp+78h+utf8buffer._Mypair._Myval2._Myfirst]
0x180061edd  mov     [rsp+78h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180061ee6  mov     [rsp+78h+lpDefaultChar], 0; lpDefaultChar
0x180061eef  mov     [rsp+78h+cbMultiByte], edi; cbMultiByte
0x180061ef3  mov     [rsp+78h+lpMultiByteStr], rax; lpMultiByteStr
0x180061ef8  mov     r9d, [rsp+78h+stringLength]; cchWideChar
0x180061efd  mov     r8, rbx; lpWideCharStr
0x180061f00  mov     edx, 80h; dwFlags
0x180061f05  mov     ecx, 0FDE9h; CodePage
0x180061f0a  call    cs:__imp_WideCharToMultiByte
0x180061f10  test    eax, eax
0x180061f12  jnz     short loc_180061F38
0x180061f14  mov     StringRef, [rsp+78h]; callerReturnAddress
0x180061f19  lea     r8, aOnecoreuapPriv; "onecoreuap\\private\\net\\inc\\common\\"...
0x180061f20  lea     edx, [rax+5Fh]; lineNumber
0x180061f23  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180061f28  mov     ebx, eax
0x180061f2a  lea     StringRef, [rsp+78h+utf8buffer]; this
0x180061f2f  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180061f34  mov     eax, ebx
0x180061f36  jmp     short loc_180061F81
0x180061f38  mov     r8, rsi; ppStream
0x180061f3b  mov     edx, eax; NumElements
0x180061f3d  mov     StringRef, [rsp+78h+utf8buffer._Mypair._Myval2._Myfirst]; Array
0x180061f42  call    ??$CreateStreamFromArray@D@WcmProvisioningUtil@@YAJPEBDIPEAPEAUIStream@@@Z; WcmProvisioningUtil::CreateStreamFromArray<char>(char const *,uint,IStream * *)
0x180061f47  mov     ebx, eax
0x180061f49  test    eax, eax
0x180061f4b  jns     short loc_180061F74
0x180061f4d  mov     StringRef, [rsp+78h]; callerReturnAddress
0x180061f52  mov     r9d, eax; hr
0x180061f55  lea     r8, aOnecoreuapPriv; "onecoreuap\\private\\net\\inc\\common\\"...
0x180061f5c  mov     edx, 61h ; 'a'; lineNumber
0x180061f61  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180061f66  lea     StringRef, [rsp+78h+utf8buffer]; this
0x180061f6b  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180061f70  mov     eax, ebx
0x180061f72  jmp     short loc_180061F81
0x180061f74  lea     StringRef, [rsp+78h+utf8buffer]; this
0x180061f79  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180061f7e  nop
0x180061f7f  xor     eax, eax
0x180061f81  mov     StringRef, [rsp+78h+var_18]
0x180061f86  xor     StringRef, rsp; StackCookie
0x180061f89  call    __security_check_cookie
0x180061f8e  lea     r11, [rsp+78h+var_8]
0x180061f93  mov     rbx, [r11+20h]
0x180061f97  mov     rsi, [r11+28h]
0x180061f9b  mov     rsp, r11
0x180061f9e  pop     rdi
0x180061f9f  retn
0x180061fa0  mov     eax, [rsp+78h+stringLength]
0x180061fa4  jmp     short loc_180061F81
0x180061fa6  mov     r8, rsi; ppStream
0x180061fa9  mov     edx, [rsp+78h+stringLength]; NumElements
0x180061fad  mov     StringRef, rbx; Array
0x180061fb0  call    ??$CreateStreamFromArray@G@WcmProvisioningUtil@@YAJPEBGIPEAPEAUIStream@@@Z; WcmProvisioningUtil::CreateStreamFromArray<ushort>(ushort const *,uint,IStream * *)
0x180061fb5  mov     ebx, eax
0x180061fb7  test    eax, eax
0x180061fb9  jns     short loc_180061F7F
0x180061fbb  mov     StringRef, [rsp+78h]; callerReturnAddress
0x180061fc0  mov     r9d, eax; hr
0x180061fc3  lea     r8, aOnecoreuapPriv; "onecoreuap\\private\\net\\inc\\common\\"...
0x180061fca  mov     edx, 67h ; 'g'; lineNumber
0x180061fcf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180061fd4  mov     eax, ebx
0x180061fd6  jmp     short loc_180061F81
```
