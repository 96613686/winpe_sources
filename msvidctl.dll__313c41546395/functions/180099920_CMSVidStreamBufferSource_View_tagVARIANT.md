# CMSVidStreamBufferSource::View(tagVARIANT *)

- ea: `0x180099920`
- end: `0x180099a5f`
- name: `?View@CMSVidStreamBufferSource@@UEAAJPEAUtagVARIANT@@@Z`
- size: `319`
- prototype: `__int64 __fastcall(CMSVidStreamBufferSource *__hidden this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180004640`
- `0x1800145ac`
- `0x180097c8c`
- `0x180099920`
- `0x1800f8010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800999ab`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800999ab`
- `OLEAUT32!__imp_SysAllocString` at `0x1800999c0`
- `OLEAUT32!__imp_SysAllocString` at `0x1800999c0`
- `OLEAUT32!__imp_SysFreeString` at `0x180099a32`
- `OLEAUT32!__imp_SysFreeString` at `0x180099a32`
- `SHLWAPI!PathCreateFromUrlW` at `0x1800999f8`
- `SHLWAPI!PathCreateFromUrlW` at `0x1800999f8`
- `SHLWAPI!UrlIsW` at `0x1800999d6`
- `SHLWAPI!UrlIsW` at `0x1800999d6`

## pseudocode

```c
__int64 __fastcall CMSVidStreamBufferSource::View(CMSVidStreamBufferSource *this, struct tagVARIANT *a2)
{
  OLECHAR *v5; // rbx
  HRESULT v6; // edi
  DWORD pcchPath; // [rsp+20h] [rbp-238h] BYREF
  OLECHAR *v8; // [rsp+28h] [rbp-230h] BYREF
  WCHAR pszPath[264]; // [rsp+30h] [rbp-228h] BYREF

  if ( !*((_BYTE *)this + *(int *)(*((_QWORD *)this - 1) + 4LL)) )
    return ATL::CComCoClass<CMSVidStreamBufferSource,&__s_GUID const _GUID_ad8e510d_217f_409b_8076_29c5e73b98e8>::Error(
             0xC0040502,
             &GUID_eb0c8cf9_6950_4772_87b1_47d11cf3a02f,
             -2147221008,
             hInstance);
  if ( !a2 )
    return 2147500035LL;
  if ( a2->vt != 8 )
    return 2147942487LL;
  if ( !(unsigned int)_o__wcsnicmp(a2->llVal, L"DVD:", 4) )
    return 2147500037LL;
  v8 = SysAllocString(a2->bstrVal);
  v5 = v8;
  if ( !UrlIsW(v8, URLIS_FILEURL) )
    goto LABEL_12;
  pcchPath = 260;
  v6 = PathCreateFromUrlW(v8, pszPath, &pcchPath, 0);
  if ( v6 >= 0 )
  {
    ATL::CComBSTR::operator=(&v8, pszPath);
    v5 = v8;
LABEL_12:
    v6 = (*(__int64 (__fastcall **)(CMSVidStreamBufferSource *, OLECHAR *))(*(_QWORD *)this + 264LL))(this, v5);
  }
  SysFreeString(v5);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180099920  mov     [rsp+arg_10], rbx
0x180099925  mov     [rsp+arg_18], rsi
0x18009992a  push    rdi
0x18009992b  sub     rsp, 250h
0x180099932  mov     rax, cs:__security_cookie
0x180099939  xor     rax, rsp
0x18009993c  mov     [rsp+258h+var_18], rax
0x180099944  mov     rax, [rcx-8]
0x180099948  mov     rsi, rcx
0x18009994b  mov     rbx, rdx
0x18009994e  movsxd  rcx, dword ptr [rax+4]
0x180099952  cmp     byte ptr [rcx+rsi], 0
0x180099956  jnz     short loc_18009997B
0x180099958  mov     r9, cs:hInstance; HINSTANCE
0x18009995f  lea     rdx, _GUID_eb0c8cf9_6950_4772_87b1_47d11cf3a02f; struct _GUID *
0x180099966  mov     r8d, 800401F0h; int
0x18009996c  mov     ecx, 0C0040502h; dwMessageId
0x180099971  call    ?Error@?$CComCoClass@VCMSVidStreamBufferSource@@$1?_GUID_ad8e510d_217f_409b_8076_29c5e73b98e8@@3U__s_GUID@@B@ATL@@SAJIAEBU_GUID@@JPEAUHINSTANCE__@@@Z; ATL::CComCoClass<CMSVidStreamBufferSource,&__s_GUID const _GUID_ad8e510d_217f_409b_8076_29c5e73b98e8>::Error(uint,_GUID const &,long,HINSTANCE__ *)
0x180099976  jmp     loc_180099A3A
0x18009997b  test    rbx, rbx
0x18009997e  jnz     short loc_18009998A
0x180099980  mov     eax, 80004003h
0x180099985  jmp     loc_180099A3A
0x18009998a  cmp     word ptr [rdx], 8
0x18009998e  jz      short loc_18009999A
0x180099990  mov     eax, 80070057h
0x180099995  jmp     loc_180099A3A
0x18009999a  mov     rcx, [rbx+8]
0x18009999e  lea     rdx, aDvd_1; "DVD:"
0x1800999a5  mov     r8d, 4
0x1800999ab  call    cs:__imp__o__wcsnicmp
0x1800999b1  test    eax, eax
0x1800999b3  jnz     short loc_1800999BC
0x1800999b5  mov     eax, 80004005h
0x1800999ba  jmp     short loc_180099A3A
0x1800999bc  mov     rcx, [rbx+8]; psz
0x1800999c0  call    cs:__imp_SysAllocString
0x1800999c6  mov     rcx, rax; pszUrl
0x1800999c9  mov     [rsp+258h+var_230], rax
0x1800999ce  mov     edx, 3; UrlIs
0x1800999d3  mov     rbx, rax
0x1800999d6  call    cs:__imp_UrlIsW
0x1800999dc  test    eax, eax
0x1800999de  jz      short loc_180099A18
0x1800999e0  xor     r9d, r9d; dwFlags
0x1800999e3  mov     [rsp+258h+pcchPath], 104h
0x1800999eb  lea     r8, [rsp+258h+pcchPath]; pcchPath
0x1800999f0  mov     rcx, rbx; pszUrl
0x1800999f3  lea     rdx, [rsp+258h+pszPath]; pszPath
0x1800999f8  call    cs:__imp_PathCreateFromUrlW
0x1800999fe  mov     edi, eax
0x180099a00  test    eax, eax
0x180099a02  js      short loc_180099A2F
0x180099a04  lea     rdx, [rsp+258h+pszPath]
0x180099a09  lea     rcx, [rsp+258h+var_230]
0x180099a0e  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x180099a13  mov     rbx, [rsp+258h+var_230]
0x180099a18  mov     rax, [rsi]
0x180099a1b  mov     rdx, rbx
0x180099a1e  mov     rcx, rsi
0x180099a21  mov     rax, [rax+108h]
0x180099a28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099a2d  mov     edi, eax
0x180099a2f  mov     rcx, rbx; bstrString
0x180099a32  call    cs:__imp_SysFreeString
0x180099a38  mov     eax, edi
0x180099a3a  mov     rcx, [rsp+258h+var_18]
0x180099a42  xor     rcx, rsp; StackCookie
0x180099a45  call    __security_check_cookie
0x180099a4a  lea     r11, [rsp+258h+var_8]
0x180099a52  mov     rbx, [r11+20h]
0x180099a56  mov     rsi, [r11+28h]
0x180099a5a  mov     rsp, r11
0x180099a5d  pop     rdi
0x180099a5e  retn
```
