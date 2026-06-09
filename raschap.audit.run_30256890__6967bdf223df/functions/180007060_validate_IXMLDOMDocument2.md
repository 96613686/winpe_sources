# validate(IXMLDOMDocument2 *)

- ea: `0x180007060`
- end: `0x1800072e9`
- name: `?validate@@YAJPEAUIXMLDOMDocument2@@@Z`
- size: `649`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180005df0`
- `0x18001cbe4`

## callees

- `0x180003bd0`
- `0x180007060`
- `0x18000e500`
- `0x18000ea70`
- `0x180013b20`
- `0x180014610`
- `0x1800146d4`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000724a`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000724a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000727e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000728a`
- `OLEAUT32!__imp_SysFreeString` at `0x180007296`
- `OLEAUT32!__imp_SysFreeString` at `0x1800072a2`
- `OLEAUT32!__imp_SysFreeString` at `0x18000727e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000728a`
- `OLEAUT32!__imp_SysFreeString` at `0x180007296`
- `OLEAUT32!__imp_SysFreeString` at `0x1800072a2`

## string_xrefs

- `0x1800071f9`: `XML blob parsing error at line %d: %s. Reason: %s`

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
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, WPP_47d2ae5abdbe322473422603828ba620_Traceguids, v2);
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
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, WPP_47d2ae5abdbe322473422603828ba620_Traceguids, MultiByteStr);
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
0x180007060  mov     [rsp-8+arg_8], rbx
0x180007065  mov     [rsp-8+arg_10], rsi
0x18000706a  push    rbp
0x18000706b  push    rdi
0x18000706c  push    r14
0x18000706e  lea     rbp, [rsp-790h]
0x180007076  sub     rsp, 890h
0x18000707d  mov     rax, cs:__security_cookie
0x180007084  xor     rax, rsp
0x180007087  mov     [rbp+7A0h+var_20], rax
0x18000708e  mov     rdi, rcx
0x180007091  xor     esi, esi
0x180007093  mov     [rsp+8A0h+var_860], rsi
0x180007098  mov     rax, [rcx]
0x18000709b  lea     rdx, [rsp+8A0h+var_860]
0x1800070a0  mov     rax, [rax+278h]
0x1800070a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070ac  mov     ebx, eax
0x1800070ae  test    eax, eax
0x1800070b0  jz      loc_1800072A9
0x1800070b6  mov     [rsp+8A0h+var_858], 0FFFFFFFFh
0x1800070be  mov     [rsp+8A0h+var_840], rsi
0x1800070c3  mov     [rsp+8A0h+var_848], rsi
0x1800070c8  mov     [rsp+8A0h+var_830], rsi
0x1800070cd  mov     [rsp+8A0h+bstrString], rsi
0x1800070d2  xor     edx, edx; Val
0x1800070d4  mov     r8d, 400h; Size
0x1800070da  lea     rcx, [rbp+7A0h+Buffer]; void *
0x1800070de  call    memset_0
0x1800070e3  xor     edx, edx; Val
0x1800070e5  mov     r8d, 400h; Size
0x1800070eb  lea     rcx, [rbp+7A0h+MultiByteStr]; void *
0x1800070f2  call    memset_0
0x1800070f7  lea     r14, WPP_GLOBAL_Control
0x1800070fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180007105  cmp     rcx, r14
0x180007108  jz      short loc_180007122
0x18000710a  mov     edx, 3Dh ; '='
0x18000710f  mov     r9d, ebx
0x180007112  lea     r8, WPP_47d2ae5abdbe322473422603828ba620_Traceguids
0x180007119  mov     rcx, [rcx+10h]
0x18000711d  call    WPP_SF_d
0x180007122  mov     rcx, [rsp+8A0h+var_860]
0x180007127  mov     rax, [rcx]
0x18000712a  lea     rdx, [rsp+8A0h+var_858]
0x18000712f  mov     rax, [rax+58h]
0x180007133  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007138  mov     rcx, [rsp+8A0h+var_860]
0x18000713d  mov     rax, [rcx]
0x180007140  lea     rdx, [rsp+8A0h+var_840]
0x180007145  mov     rax, [rax+48h]
0x180007149  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000714e  mov     rcx, [rsp+8A0h+var_860]
0x180007153  mov     rax, [rcx]
0x180007156  lea     rdx, [rsp+8A0h+var_848]
0x18000715b  mov     rax, [rax+50h]
0x18000715f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007164  mov     [rsp+8A0h+var_850], rsi
0x180007169  mov     rcx, [rsp+8A0h+var_860]
0x18000716e  mov     rax, [rcx]
0x180007171  lea     r8, [rsp+8A0h+var_850]
0x180007176  lea     rdx, IID_IXMLDOMParseError2
0x18000717d  mov     rax, [rax]
0x180007180  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007185  test    eax, eax
0x180007187  jnz     short loc_18000719F
0x180007189  mov     rcx, [rsp+8A0h+var_850]
0x18000718e  mov     rax, [rcx]
0x180007191  lea     rdx, [rsp+8A0h+var_830]
0x180007196  mov     rax, [rax+70h]
0x18000719a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000719f  mov     rax, [rdi]
0x1800071a2  lea     rdx, [rsp+8A0h+bstrString]
0x1800071a7  mov     rcx, rdi
0x1800071aa  mov     rax, [rax+110h]
0x1800071b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071b6  nop
0x1800071b7  lea     rcx, [rsp+8A0h+var_850]
0x1800071bc  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x1800071c1  lea     rax, aUnknown; "Unknown"
0x1800071c8  mov     rcx, [rsp+8A0h+var_840]
0x1800071cd  test    rcx, rcx
0x1800071d0  cmovz   rcx, rax
0x1800071d4  lea     rdx, aUnableToGetThe; "unable to get the content of the line"
0x1800071db  mov     rax, [rsp+8A0h+var_848]
0x1800071e0  test    rax, rax
0x1800071e3  cmovz   rax, rdx
0x1800071e7  mov     [rsp+8A0h+lpDefaultChar], rcx
0x1800071ec  mov     qword ptr [rsp+8A0h+cbMultiByte], rax
0x1800071f1  mov     eax, [rsp+8A0h+var_858]
0x1800071f5  mov     dword ptr [rsp+8A0h+lpMultiByteStr], eax
0x1800071f9  lea     r9, aXmlBlobParsing; "XML blob parsing error at line %d: %s. "...
0x180007200  mov     edx, 200h; BufferCount
0x180007205  mov     r8d, 1FFh; MaxCount
0x18000720b  lea     rcx, [rbp+7A0h+Buffer]; Buffer
0x18000720f  call    _snwprintf_s
0x180007214  mov     [rbp+7A0h+var_422], si
0x18000721b  mov     [rsp+8A0h+lpUsedDefaultChar], rsi; lpUsedDefaultChar
0x180007220  mov     [rsp+8A0h+lpDefaultChar], rsi; lpDefaultChar
0x180007225  mov     [rsp+8A0h+cbMultiByte], 400h; cbMultiByte
0x18000722d  lea     rax, [rbp+7A0h+MultiByteStr]
0x180007234  mov     [rsp+8A0h+lpMultiByteStr], rax; lpMultiByteStr
0x180007239  mov     r9d, 0FFFFFFFFh; cchWideChar
0x18000723f  lea     r8, [rbp+7A0h+Buffer]; lpWideCharStr
0x180007243  xor     edx, edx; dwFlags
0x180007245  mov     ecx, 0FDE9h; CodePage
0x18000724a  call    cs:__imp_WideCharToMultiByte
0x180007250  mov     rcx, cs:WPP_GLOBAL_Control
0x180007257  cmp     rcx, r14
0x18000725a  jz      short loc_180007279
0x18000725c  mov     edx, 3Eh ; '>'
0x180007261  lea     r9, [rbp+7A0h+MultiByteStr]
0x180007268  lea     r8, WPP_47d2ae5abdbe322473422603828ba620_Traceguids
0x18000726f  mov     rcx, [rcx+10h]
0x180007273  call    WPP_SF_s
0x180007278  nop
0x180007279  mov     rcx, [rsp+8A0h+bstrString]; bstrString
0x18000727e  call    cs:__imp_SysFreeString
0x180007284  nop
0x180007285  mov     rcx, [rsp+8A0h+var_830]; bstrString
0x18000728a  call    cs:__imp_SysFreeString
0x180007290  nop
0x180007291  mov     rcx, [rsp+8A0h+var_848]; bstrString
0x180007296  call    cs:__imp_SysFreeString
0x18000729c  nop
0x18000729d  mov     rcx, [rsp+8A0h+var_840]; bstrString
0x1800072a2  call    cs:__imp_SysFreeString
0x1800072a8  nop
0x1800072a9  mov     rcx, [rsp+8A0h+var_860]
0x1800072ae  test    rcx, rcx
0x1800072b1  jz      short loc_1800072C0
0x1800072b3  mov     rax, [rcx]
0x1800072b6  mov     rax, [rax+10h]
0x1800072ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072bf  nop
0x1800072c0  mov     eax, ebx
0x1800072c2  mov     rcx, [rbp+7A0h+var_20]
0x1800072c9  xor     rcx, rsp; StackCookie
0x1800072cc  call    __security_check_cookie
0x1800072d1  lea     r11, [rsp+8A0h+var_10]
0x1800072d9  mov     rbx, [r11+28h]
0x1800072dd  mov     rsi, [r11+30h]
0x1800072e1  mov     rsp, r11
0x1800072e4  pop     r14
0x1800072e6  pop     rdi
0x1800072e7  pop     rbp
0x1800072e8  retn
```
