# CMSVidStreamBufferV2Source::View(tagVARIANT *)

- ea: `0x18009df90`
- end: `0x18009e0cf`
- name: `?View@CMSVidStreamBufferV2Source@@UEAAJPEAUtagVARIANT@@@Z`
- size: `319`
- prototype: `__int64 __fastcall(CMSVidStreamBufferV2Source *__hidden this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180004640`
- `0x1800145ac`
- `0x18009c9cc`
- `0x18009df90`
- `0x1800f8010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18009e01b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18009e01b`
- `OLEAUT32!__imp_SysAllocString` at `0x18009e030`
- `OLEAUT32!__imp_SysAllocString` at `0x18009e030`
- `OLEAUT32!__imp_SysFreeString` at `0x18009e0a2`
- `OLEAUT32!__imp_SysFreeString` at `0x18009e0a2`
- `SHLWAPI!PathCreateFromUrlW` at `0x18009e068`
- `SHLWAPI!PathCreateFromUrlW` at `0x18009e068`
- `SHLWAPI!UrlIsW` at `0x18009e046`
- `SHLWAPI!UrlIsW` at `0x18009e046`

## pseudocode

```c
__int64 __fastcall CMSVidStreamBufferV2Source::View(CMSVidStreamBufferV2Source *this, struct tagVARIANT *a2)
{
  OLECHAR *v5; // rbx
  HRESULT v6; // edi
  DWORD pcchPath; // [rsp+20h] [rbp-238h] BYREF
  OLECHAR *v8; // [rsp+28h] [rbp-230h] BYREF
  WCHAR pszPath[264]; // [rsp+30h] [rbp-228h] BYREF

  if ( !*((_BYTE *)this + *(int *)(*((_QWORD *)this - 1) + 4LL)) )
    return ATL::CComCoClass<CMSVidStreamBufferV2Source,&__s_GUID const _GUID_fd351ea1_4173_4af4_821d_80d4ae979048>::Error(
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
    v6 = (*(__int64 (__fastcall **)(CMSVidStreamBufferV2Source *, OLECHAR *))(*(_QWORD *)this + 264LL))(this, v5);
  }
  SysFreeString(v5);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18009df90  mov     [rsp+arg_10], rbx
0x18009df95  mov     [rsp+arg_18], rsi
0x18009df9a  push    rdi
0x18009df9b  sub     rsp, 250h
0x18009dfa2  mov     rax, cs:__security_cookie
0x18009dfa9  xor     rax, rsp
0x18009dfac  mov     [rsp+258h+var_18], rax
0x18009dfb4  mov     rax, [rcx-8]
0x18009dfb8  mov     rsi, rcx
0x18009dfbb  mov     rbx, rdx
0x18009dfbe  movsxd  rcx, dword ptr [rax+4]
0x18009dfc2  cmp     byte ptr [rcx+rsi], 0
0x18009dfc6  jnz     short loc_18009DFEB
0x18009dfc8  mov     r9, cs:hInstance; HINSTANCE
0x18009dfcf  lea     rdx, _GUID_eb0c8cf9_6950_4772_87b1_47d11cf3a02f; struct _GUID *
0x18009dfd6  mov     r8d, 800401F0h; int
0x18009dfdc  mov     ecx, 0C0040502h; dwMessageId
0x18009dfe1  call    ?Error@?$CComCoClass@VCMSVidStreamBufferV2Source@@$1?_GUID_fd351ea1_4173_4af4_821d_80d4ae979048@@3U__s_GUID@@B@ATL@@SAJIAEBU_GUID@@JPEAUHINSTANCE__@@@Z; ATL::CComCoClass<CMSVidStreamBufferV2Source,&__s_GUID const _GUID_fd351ea1_4173_4af4_821d_80d4ae979048>::Error(uint,_GUID const &,long,HINSTANCE__ *)
0x18009dfe6  jmp     loc_18009E0AA
0x18009dfeb  test    rbx, rbx
0x18009dfee  jnz     short loc_18009DFFA
0x18009dff0  mov     eax, 80004003h
0x18009dff5  jmp     loc_18009E0AA
0x18009dffa  cmp     word ptr [rdx], 8
0x18009dffe  jz      short loc_18009E00A
0x18009e000  mov     eax, 80070057h
0x18009e005  jmp     loc_18009E0AA
0x18009e00a  mov     rcx, [rbx+8]
0x18009e00e  lea     rdx, aDvd_1; "DVD:"
0x18009e015  mov     r8d, 4
0x18009e01b  call    cs:__imp__o__wcsnicmp
0x18009e021  test    eax, eax
0x18009e023  jnz     short loc_18009E02C
0x18009e025  mov     eax, 80004005h
0x18009e02a  jmp     short loc_18009E0AA
0x18009e02c  mov     rcx, [rbx+8]; psz
0x18009e030  call    cs:__imp_SysAllocString
0x18009e036  mov     rcx, rax; pszUrl
0x18009e039  mov     [rsp+258h+var_230], rax
0x18009e03e  mov     edx, 3; UrlIs
0x18009e043  mov     rbx, rax
0x18009e046  call    cs:__imp_UrlIsW
0x18009e04c  test    eax, eax
0x18009e04e  jz      short loc_18009E088
0x18009e050  xor     r9d, r9d; dwFlags
0x18009e053  mov     [rsp+258h+pcchPath], 104h
0x18009e05b  lea     r8, [rsp+258h+pcchPath]; pcchPath
0x18009e060  mov     rcx, rbx; pszUrl
0x18009e063  lea     rdx, [rsp+258h+pszPath]; pszPath
0x18009e068  call    cs:__imp_PathCreateFromUrlW
0x18009e06e  mov     edi, eax
0x18009e070  test    eax, eax
0x18009e072  js      short loc_18009E09F
0x18009e074  lea     rdx, [rsp+258h+pszPath]
0x18009e079  lea     rcx, [rsp+258h+var_230]
0x18009e07e  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18009e083  mov     rbx, [rsp+258h+var_230]
0x18009e088  mov     rax, [rsi]
0x18009e08b  mov     rdx, rbx
0x18009e08e  mov     rcx, rsi
0x18009e091  mov     rax, [rax+108h]
0x18009e098  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e09d  mov     edi, eax
0x18009e09f  mov     rcx, rbx; bstrString
0x18009e0a2  call    cs:__imp_SysFreeString
0x18009e0a8  mov     eax, edi
0x18009e0aa  mov     rcx, [rsp+258h+var_18]
0x18009e0b2  xor     rcx, rsp; StackCookie
0x18009e0b5  call    __security_check_cookie
0x18009e0ba  lea     r11, [rsp+258h+var_8]
0x18009e0c2  mov     rbx, [r11+20h]
0x18009e0c6  mov     rsi, [r11+28h]
0x18009e0ca  mov     rsp, r11
0x18009e0cd  pop     rdi
0x18009e0ce  retn
```
