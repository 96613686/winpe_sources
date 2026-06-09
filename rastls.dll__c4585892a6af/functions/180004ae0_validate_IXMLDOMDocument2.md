# validate(IXMLDOMDocument2 *)

- ea: `0x180004ae0`
- end: `0x180004d88`
- name: `?validate@@YAJPEAUIXMLDOMDocument2@@@Z`
- size: `680`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 *)`
- caller_count: `4`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800055e0`
- `0x180062228`
- `0x180062614`
- `0x180062e58`

## callees

- `0x180004ae0`
- `0x180005010`
- `0x18001e0c0`
- `0x180021e74`
- `0x180038270`
- `0x180038e64`
- `0x180038f4c`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180004cca`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180004cca`
- `OLEAUT32!__imp_SysFreeString` at `0x180004d04`
- `OLEAUT32!__imp_SysFreeString` at `0x180004d16`
- `OLEAUT32!__imp_SysFreeString` at `0x180004d28`
- `OLEAUT32!__imp_SysFreeString` at `0x180004d3a`
- `OLEAUT32!__imp_SysFreeString` at `0x180004d04`
- `OLEAUT32!__imp_SysFreeString` at `0x180004d16`
- `OLEAUT32!__imp_SysFreeString` at `0x180004d28`
- `OLEAUT32!__imp_SysFreeString` at `0x180004d3a`

## string_xrefs

- `0x180004c79`: `XML blob parsing error at line %d: %s. Reason: %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall validate(struct IXMLDOMDocument2 *a1)
{
  unsigned int v2; // ebx
  BSTR v3; // rcx
  BSTR v4; // rax
  __int64 v6; // [rsp+40h] [rbp-C0h] BYREF
  int v7; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v8; // [rsp+50h] [rbp-B0h] BYREF
  BSTR v9; // [rsp+58h] [rbp-A8h] BYREF
  BSTR v10; // [rsp+60h] [rbp-A0h] BYREF
  BSTR bstrString; // [rsp+68h] [rbp-98h] BYREF
  BSTR v12[2]; // [rsp+70h] [rbp-90h] BYREF
  wchar_t Buffer[512]; // [rsp+80h] [rbp-80h] BYREF
  CHAR MultiByteStr[1024]; // [rsp+480h] [rbp+380h] BYREF

  v6 = 0;
  v2 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, __int64 *))a1->lpVtbl->validate)(a1, &v6);
  if ( v2 )
  {
    v7 = -1;
    v10 = 0;
    v9 = 0;
    v12[0] = 0;
    bstrString = 0;
    memset_0(Buffer, 0, sizeof(Buffer));
    memset_0(MultiByteStr, 0, sizeof(MultiByteStr));
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 255, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, v2);
    (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v6 + 88LL))(v6, &v7);
    (*(void (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v6 + 72LL))(v6, &v10);
    (*(void (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v6 + 80LL))(v6, &v9);
    v8 = 0;
    if ( !(**(unsigned int (__fastcall ***)(__int64, GUID *, __int64 *))v6)(v6, &IID_IXMLDOMParseError2, &v8) )
      (*(void (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v8 + 112LL))(v8, v12);
    ((void (__fastcall *)(struct IXMLDOMDocument2 *, BSTR *))a1->lpVtbl->get_xml)(a1, &bstrString);
    ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v8);
    v3 = v10;
    if ( !v10 )
      v3 = L"Unknown";
    v4 = v9;
    if ( !v9 )
      v4 = L"unable to get the content of the line";
    snwprintf_s(Buffer, 0x200u, 0x1FFu, L"XML blob parsing error at line %d: %s. Reason: %s", v7, v4, v3);
    Buffer[511] = 0;
    WideCharToMultiByte(0xFDE9u, 0, Buffer, -1, MultiByteStr, 1024, 0, 0);
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 256, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, MultiByteStr);
    SysFreeString(bstrString);
    SysFreeString(v12[0]);
    SysFreeString(v9);
    SysFreeString(v10);
  }
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  return v2;
}

```

## disassembly

```asm
0x180004ae0  mov     [rsp-8+arg_8], rbx
0x180004ae5  mov     [rsp-8+arg_10], rsi
0x180004aea  push    rbp
0x180004aeb  push    rdi
0x180004aec  push    r14
0x180004aee  lea     rbp, [rsp-790h]
0x180004af6  sub     rsp, 890h
0x180004afd  mov     rax, cs:__security_cookie
0x180004b04  xor     rax, rsp
0x180004b07  mov     [rbp+7A0h+var_20], rax
0x180004b0e  mov     rdi, rcx
0x180004b11  xor     esi, esi
0x180004b13  mov     [rsp+8A0h+var_860], rsi
0x180004b18  mov     rax, [rcx]
0x180004b1b  lea     rdx, [rsp+8A0h+var_860]
0x180004b20  mov     rax, [rax+278h]
0x180004b27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b2c  mov     ebx, eax
0x180004b2e  test    eax, eax
0x180004b30  jz      loc_180004D47
0x180004b36  mov     [rsp+8A0h+var_858], 0FFFFFFFFh
0x180004b3e  mov     [rsp+8A0h+var_840], rsi
0x180004b43  mov     [rsp+8A0h+var_848], rsi
0x180004b48  mov     [rsp+8A0h+var_830], rsi
0x180004b4d  mov     [rsp+8A0h+bstrString], rsi
0x180004b52  xor     edx, edx; Val
0x180004b54  mov     r8d, 400h; Size
0x180004b5a  lea     rcx, [rbp+7A0h+Buffer]; void *
0x180004b5e  call    memset_0
0x180004b63  xor     edx, edx; Val
0x180004b65  mov     r8d, 400h; Size
0x180004b6b  lea     rcx, [rbp+7A0h+MultiByteStr]; void *
0x180004b72  call    memset_0
0x180004b77  lea     r14, WPP_GLOBAL_Control
0x180004b7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180004b85  cmp     rcx, r14
0x180004b88  jz      short loc_180004BA2
0x180004b8a  mov     edx, 0FFh
0x180004b8f  mov     r9d, ebx
0x180004b92  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180004b99  mov     rcx, [rcx+10h]
0x180004b9d  call    WPP_SF_d
0x180004ba2  mov     rcx, [rsp+8A0h+var_860]
0x180004ba7  mov     rax, [rcx]
0x180004baa  lea     rdx, [rsp+8A0h+var_858]
0x180004baf  mov     rax, [rax+58h]
0x180004bb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bb8  mov     rcx, [rsp+8A0h+var_860]
0x180004bbd  mov     rax, [rcx]
0x180004bc0  lea     rdx, [rsp+8A0h+var_840]
0x180004bc5  mov     rax, [rax+48h]
0x180004bc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bce  mov     rcx, [rsp+8A0h+var_860]
0x180004bd3  mov     rax, [rcx]
0x180004bd6  lea     rdx, [rsp+8A0h+var_848]
0x180004bdb  mov     rax, [rax+50h]
0x180004bdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004be4  mov     [rsp+8A0h+var_850], rsi
0x180004be9  mov     rcx, [rsp+8A0h+var_860]
0x180004bee  mov     rax, [rcx]
0x180004bf1  lea     r8, [rsp+8A0h+var_850]
0x180004bf6  lea     rdx, IID_IXMLDOMParseError2
0x180004bfd  mov     rax, [rax]
0x180004c00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c05  test    eax, eax
0x180004c07  jnz     short loc_180004C1F
0x180004c09  mov     rcx, [rsp+8A0h+var_850]
0x180004c0e  mov     rax, [rcx]
0x180004c11  lea     rdx, [rsp+8A0h+var_830]
0x180004c16  mov     rax, [rax+70h]
0x180004c1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c1f  mov     rax, [rdi]
0x180004c22  lea     rdx, [rsp+8A0h+bstrString]
0x180004c27  mov     rcx, rdi
0x180004c2a  mov     rax, [rax+110h]
0x180004c31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c36  nop
0x180004c37  lea     rcx, [rsp+8A0h+var_850]
0x180004c3c  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180004c41  lea     rax, aUnknown_0; "Unknown"
0x180004c48  mov     rcx, [rsp+8A0h+var_840]
0x180004c4d  test    rcx, rcx
0x180004c50  cmovz   rcx, rax
0x180004c54  lea     rdx, aUnableToGetThe; "unable to get the content of the line"
0x180004c5b  mov     rax, [rsp+8A0h+var_848]
0x180004c60  test    rax, rax
0x180004c63  cmovz   rax, rdx
0x180004c67  mov     [rsp+8A0h+lpDefaultChar], rcx
0x180004c6c  mov     qword ptr [rsp+8A0h+cbMultiByte], rax
0x180004c71  mov     eax, [rsp+8A0h+var_858]
0x180004c75  mov     dword ptr [rsp+8A0h+lpMultiByteStr], eax
0x180004c79  lea     r9, aXmlBlobParsing; "XML blob parsing error at line %d: %s. "...
0x180004c80  mov     edx, 200h; BufferCount
0x180004c85  mov     r8d, 1FFh; MaxCount
0x180004c8b  lea     rcx, [rbp+7A0h+Buffer]; Buffer
0x180004c8f  call    _snwprintf_s
0x180004c94  mov     [rbp+7A0h+var_422], si
0x180004c9b  mov     [rsp+8A0h+lpUsedDefaultChar], rsi; lpUsedDefaultChar
0x180004ca0  mov     [rsp+8A0h+lpDefaultChar], rsi; lpDefaultChar
0x180004ca5  mov     [rsp+8A0h+cbMultiByte], 400h; cbMultiByte
0x180004cad  lea     rax, [rbp+7A0h+MultiByteStr]
0x180004cb4  mov     [rsp+8A0h+lpMultiByteStr], rax; lpMultiByteStr
0x180004cb9  mov     r9d, 0FFFFFFFFh; cchWideChar
0x180004cbf  lea     r8, [rbp+7A0h+Buffer]; lpWideCharStr
0x180004cc3  xor     edx, edx; dwFlags
0x180004cc5  mov     ecx, 0FDE9h; CodePage
0x180004cca  call    cs:__imp_WideCharToMultiByte
0x180004cd1  nop     dword ptr [rax+rax+00h]
0x180004cd6  mov     rcx, cs:WPP_GLOBAL_Control
0x180004cdd  cmp     rcx, r14
0x180004ce0  jz      short loc_180004CFF
0x180004ce2  mov     edx, 100h
0x180004ce7  lea     r9, [rbp+7A0h+MultiByteStr]
0x180004cee  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180004cf5  mov     rcx, [rcx+10h]
0x180004cf9  call    WPP_SF_s
0x180004cfe  nop
0x180004cff  mov     rcx, [rsp+8A0h+bstrString]; bstrString
0x180004d04  call    cs:__imp_SysFreeString
0x180004d0b  nop     dword ptr [rax+rax+00h]
0x180004d10  nop
0x180004d11  mov     rcx, [rsp+8A0h+var_830]; bstrString
0x180004d16  call    cs:__imp_SysFreeString
0x180004d1d  nop     dword ptr [rax+rax+00h]
0x180004d22  nop
0x180004d23  mov     rcx, [rsp+8A0h+var_848]; bstrString
0x180004d28  call    cs:__imp_SysFreeString
0x180004d2f  nop     dword ptr [rax+rax+00h]
0x180004d34  nop
0x180004d35  mov     rcx, [rsp+8A0h+var_840]; bstrString
0x180004d3a  call    cs:__imp_SysFreeString
0x180004d41  nop     dword ptr [rax+rax+00h]
0x180004d46  nop
0x180004d47  mov     rcx, [rsp+8A0h+var_860]
0x180004d4c  test    rcx, rcx
0x180004d4f  jz      short loc_180004D5E
0x180004d51  mov     rax, [rcx]
0x180004d54  mov     rax, [rax+10h]
0x180004d58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d5d  nop
0x180004d5e  mov     eax, ebx
0x180004d60  mov     rcx, [rbp+7A0h+var_20]
0x180004d67  xor     rcx, rsp; StackCookie
0x180004d6a  call    __security_check_cookie
0x180004d6f  lea     r11, [rsp+8A0h+var_10]
0x180004d77  mov     rbx, [r11+28h]
0x180004d7b  mov     rsi, [r11+30h]
0x180004d7f  mov     rsp, r11
0x180004d82  pop     r14
0x180004d84  pop     rdi
0x180004d85  pop     rbp
0x180004d86  retn
```
