# validate(IXMLDOMDocument2 *)

- ea: `0x1800046e0`
- end: `0x180004969`
- name: `?validate@@YAJPEAUIXMLDOMDocument2@@@Z`
- size: `649`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 *)`
- caller_count: `4`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180005170`
- `0x18005ea34`
- `0x18005ee0c`
- `0x18005f628`

## callees

- `0x1800046e0`
- `0x180004bd0`
- `0x18001c680`
- `0x1800200b4`
- `0x180035680`
- `0x180036254`
- `0x18003633c`
- `0x18007c010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800048ca`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800048ca`
- `OLEAUT32!__imp_SysFreeString` at `0x1800048fe`
- `OLEAUT32!__imp_SysFreeString` at `0x18000490a`
- `OLEAUT32!__imp_SysFreeString` at `0x180004916`
- `OLEAUT32!__imp_SysFreeString` at `0x180004922`
- `OLEAUT32!__imp_SysFreeString` at `0x1800048fe`
- `OLEAUT32!__imp_SysFreeString` at `0x18000490a`
- `OLEAUT32!__imp_SysFreeString` at `0x180004916`
- `OLEAUT32!__imp_SysFreeString` at `0x180004922`

## string_xrefs

- `0x180004879`: `XML blob parsing error at line %d: %s. Reason: %s`

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
0x1800046e0  mov     [rsp-8+arg_8], rbx
0x1800046e5  mov     [rsp-8+arg_10], rsi
0x1800046ea  push    rbp
0x1800046eb  push    rdi
0x1800046ec  push    r14
0x1800046ee  lea     rbp, [rsp-790h]
0x1800046f6  sub     rsp, 890h
0x1800046fd  mov     rax, cs:__security_cookie
0x180004704  xor     rax, rsp
0x180004707  mov     [rbp+7A0h+var_20], rax
0x18000470e  mov     rdi, rcx
0x180004711  xor     esi, esi
0x180004713  mov     [rsp+8A0h+var_860], rsi
0x180004718  mov     rax, [rcx]
0x18000471b  lea     rdx, [rsp+8A0h+var_860]
0x180004720  mov     rax, [rax+278h]
0x180004727  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000472c  mov     ebx, eax
0x18000472e  test    eax, eax
0x180004730  jz      loc_180004929
0x180004736  mov     [rsp+8A0h+var_858], 0FFFFFFFFh
0x18000473e  mov     [rsp+8A0h+var_840], rsi
0x180004743  mov     [rsp+8A0h+var_848], rsi
0x180004748  mov     [rsp+8A0h+var_830], rsi
0x18000474d  mov     [rsp+8A0h+bstrString], rsi
0x180004752  xor     edx, edx; Val
0x180004754  mov     r8d, 400h; Size
0x18000475a  lea     rcx, [rbp+7A0h+Buffer]; void *
0x18000475e  call    memset_0
0x180004763  xor     edx, edx; Val
0x180004765  mov     r8d, 400h; Size
0x18000476b  lea     rcx, [rbp+7A0h+MultiByteStr]; void *
0x180004772  call    memset_0
0x180004777  lea     r14, WPP_GLOBAL_Control
0x18000477e  mov     rcx, cs:WPP_GLOBAL_Control
0x180004785  cmp     rcx, r14
0x180004788  jz      short loc_1800047A2
0x18000478a  mov     edx, 0FFh
0x18000478f  mov     r9d, ebx
0x180004792  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180004799  mov     rcx, [rcx+10h]
0x18000479d  call    WPP_SF_d
0x1800047a2  mov     rcx, [rsp+8A0h+var_860]
0x1800047a7  mov     rax, [rcx]
0x1800047aa  lea     rdx, [rsp+8A0h+var_858]
0x1800047af  mov     rax, [rax+58h]
0x1800047b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047b8  mov     rcx, [rsp+8A0h+var_860]
0x1800047bd  mov     rax, [rcx]
0x1800047c0  lea     rdx, [rsp+8A0h+var_840]
0x1800047c5  mov     rax, [rax+48h]
0x1800047c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047ce  mov     rcx, [rsp+8A0h+var_860]
0x1800047d3  mov     rax, [rcx]
0x1800047d6  lea     rdx, [rsp+8A0h+var_848]
0x1800047db  mov     rax, [rax+50h]
0x1800047df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047e4  mov     [rsp+8A0h+var_850], rsi
0x1800047e9  mov     rcx, [rsp+8A0h+var_860]
0x1800047ee  mov     rax, [rcx]
0x1800047f1  lea     r8, [rsp+8A0h+var_850]
0x1800047f6  lea     rdx, IID_IXMLDOMParseError2
0x1800047fd  mov     rax, [rax]
0x180004800  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004805  test    eax, eax
0x180004807  jnz     short loc_18000481F
0x180004809  mov     rcx, [rsp+8A0h+var_850]
0x18000480e  mov     rax, [rcx]
0x180004811  lea     rdx, [rsp+8A0h+var_830]
0x180004816  mov     rax, [rax+70h]
0x18000481a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000481f  mov     rax, [rdi]
0x180004822  lea     rdx, [rsp+8A0h+bstrString]
0x180004827  mov     rcx, rdi
0x18000482a  mov     rax, [rax+110h]
0x180004831  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004836  nop
0x180004837  lea     rcx, [rsp+8A0h+var_850]
0x18000483c  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180004841  lea     rax, aUnknown_0; "Unknown"
0x180004848  mov     rcx, [rsp+8A0h+var_840]
0x18000484d  test    rcx, rcx
0x180004850  cmovz   rcx, rax
0x180004854  lea     rdx, aUnableToGetThe; "unable to get the content of the line"
0x18000485b  mov     rax, [rsp+8A0h+var_848]
0x180004860  test    rax, rax
0x180004863  cmovz   rax, rdx
0x180004867  mov     [rsp+8A0h+lpDefaultChar], rcx
0x18000486c  mov     qword ptr [rsp+8A0h+cbMultiByte], rax
0x180004871  mov     eax, [rsp+8A0h+var_858]
0x180004875  mov     dword ptr [rsp+8A0h+lpMultiByteStr], eax
0x180004879  lea     r9, aXmlBlobParsing; "XML blob parsing error at line %d: %s. "...
0x180004880  mov     edx, 200h; BufferCount
0x180004885  mov     r8d, 1FFh; MaxCount
0x18000488b  lea     rcx, [rbp+7A0h+Buffer]; Buffer
0x18000488f  call    _snwprintf_s
0x180004894  mov     [rbp+7A0h+var_422], si
0x18000489b  mov     [rsp+8A0h+lpUsedDefaultChar], rsi; lpUsedDefaultChar
0x1800048a0  mov     [rsp+8A0h+lpDefaultChar], rsi; lpDefaultChar
0x1800048a5  mov     [rsp+8A0h+cbMultiByte], 400h; cbMultiByte
0x1800048ad  lea     rax, [rbp+7A0h+MultiByteStr]
0x1800048b4  mov     [rsp+8A0h+lpMultiByteStr], rax; lpMultiByteStr
0x1800048b9  mov     r9d, 0FFFFFFFFh; cchWideChar
0x1800048bf  lea     r8, [rbp+7A0h+Buffer]; lpWideCharStr
0x1800048c3  xor     edx, edx; dwFlags
0x1800048c5  mov     ecx, 0FDE9h; CodePage
0x1800048ca  call    cs:__imp_WideCharToMultiByte
0x1800048d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800048d7  cmp     rcx, r14
0x1800048da  jz      short loc_1800048F9
0x1800048dc  mov     edx, 100h
0x1800048e1  lea     r9, [rbp+7A0h+MultiByteStr]
0x1800048e8  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x1800048ef  mov     rcx, [rcx+10h]
0x1800048f3  call    WPP_SF_s
0x1800048f8  nop
0x1800048f9  mov     rcx, [rsp+8A0h+bstrString]; bstrString
0x1800048fe  call    cs:__imp_SysFreeString
0x180004904  nop
0x180004905  mov     rcx, [rsp+8A0h+var_830]; bstrString
0x18000490a  call    cs:__imp_SysFreeString
0x180004910  nop
0x180004911  mov     rcx, [rsp+8A0h+var_848]; bstrString
0x180004916  call    cs:__imp_SysFreeString
0x18000491c  nop
0x18000491d  mov     rcx, [rsp+8A0h+var_840]; bstrString
0x180004922  call    cs:__imp_SysFreeString
0x180004928  nop
0x180004929  mov     rcx, [rsp+8A0h+var_860]
0x18000492e  test    rcx, rcx
0x180004931  jz      short loc_180004940
0x180004933  mov     rax, [rcx]
0x180004936  mov     rax, [rax+10h]
0x18000493a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000493f  nop
0x180004940  mov     eax, ebx
0x180004942  mov     rcx, [rbp+7A0h+var_20]
0x180004949  xor     rcx, rsp; StackCookie
0x18000494c  call    __security_check_cookie
0x180004951  lea     r11, [rsp+8A0h+var_10]
0x180004959  mov     rbx, [r11+28h]
0x18000495d  mov     rsi, [r11+30h]
0x180004961  mov     rsp, r11
0x180004964  pop     r14
0x180004966  pop     rdi
0x180004967  pop     rbp
0x180004968  retn
```
