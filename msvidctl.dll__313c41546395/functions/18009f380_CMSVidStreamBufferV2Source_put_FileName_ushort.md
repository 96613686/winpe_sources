# CMSVidStreamBufferV2Source::put_FileName(ushort *)

- ea: `0x18009f380`
- end: `0x18009f502`
- name: `?put_FileName@CMSVidStreamBufferV2Source@@UEAAJPEAG@Z`
- size: `386`
- prototype: `int(CMSVidStreamBufferV2Source *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180004640`
- `0x180006b38`
- `0x18000e518`
- `0x180014568`
- `0x1800145ac`
- `0x180015f90`
- `0x18009f104`
- `0x18009f380`
- `0x1800f8010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18009f3ce`
- `OLEAUT32!__imp_SysAllocString` at `0x18009f3ce`
- `OLEAUT32!__imp_SysFreeString` at `0x18009f49e`
- `OLEAUT32!__imp_SysFreeString` at `0x18009f4b3`
- `OLEAUT32!__imp_SysFreeString` at `0x18009f4d3`
- `OLEAUT32!__imp_SysFreeString` at `0x18009f49e`
- `OLEAUT32!__imp_SysFreeString` at `0x18009f4b3`
- `OLEAUT32!__imp_SysFreeString` at `0x18009f4d3`
- `OLEAUT32!__imp_SysStringLen` at `0x18009f3b7`
- `OLEAUT32!__imp_SysStringLen` at `0x18009f3b7`
- `SHLWAPI!PathCreateFromUrlW` at `0x18009f406`
- `SHLWAPI!PathCreateFromUrlW` at `0x18009f406`
- `SHLWAPI!UrlIsW` at `0x18009f3e4`
- `SHLWAPI!UrlIsW` at `0x18009f3e4`

## pseudocode

```c
__int64 __fastcall CMSVidStreamBufferV2Source::put_FileName(CMSVidStreamBufferV2Source *this, unsigned __int16 *a2)
{
  OLECHAR *v5; // rbx
  HRESULT v6; // edi
  struct IUnknown *v7; // rdx
  struct IUnknown *v8; // rdi
  OLECHAR *v9; // rsi
  struct IUnknown *v10; // [rsp+20h] [rbp-E0h] BYREF
  OLECHAR *v11; // [rsp+28h] [rbp-D8h] BYREF
  DWORD pcchPath[4]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR pszPath[264]; // [rsp+40h] [rbp-C0h] BYREF

  if ( !SysStringLen(a2) )
    return 2147942487LL;
  v11 = SysAllocString(a2);
  v5 = v11;
  if ( !UrlIsW(v11, URLIS_FILEURL) )
  {
LABEL_6:
    v7 = (struct IUnknown *)*((_QWORD *)this + 8);
    if ( v7 )
    {
      v10 = 0;
      ATL::AtlComPtrAssign(&v10, v7);
      v8 = v10;
      if ( !v10 )
      {
        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v10);
        v6 = -2147418113;
        goto LABEL_13;
      }
      v9 = ATL::CComBSTR::Copy((ATL::CComBSTR *)&v11);
      v6 = ((__int64 (__fastcall *)(struct IUnknown *, OLECHAR *, _QWORD))v8->lpVtbl[1].QueryInterface)(v8, v9, 0);
      if ( v6 >= 0 )
      {
        ATL::CComBSTR::operator=((char *)this + 24, &v11);
        SysFreeString(v9);
        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v10);
        goto LABEL_13;
      }
      SysFreeString(v9);
      ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v10);
    }
    v6 = MSVideoControl::IMSVidFilePlaybackImpl<CMSVidStreamBufferV2Source,&_GUID const LIBID_MSVidCtlLib,&__s_GUID const _GUID_00000000_0000_0000_0000_000000000000,IMSVidStreamBufferSource2>::put_FileName(
           this,
           v5);
    goto LABEL_13;
  }
  pcchPath[0] = 260;
  v6 = PathCreateFromUrlW(v11, pszPath, pcchPath, 0);
  if ( v6 >= 0 )
  {
    ATL::CComBSTR::operator=(&v11, pszPath);
    v5 = v11;
    goto LABEL_6;
  }
LABEL_13:
  SysFreeString(v5);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18009f380  mov     [rsp-8+arg_10], rbx
0x18009f385  mov     [rsp-8+arg_18], rsi
0x18009f38a  push    rbp
0x18009f38b  push    rdi
0x18009f38c  push    r14
0x18009f38e  lea     rbp, [rsp-160h]
0x18009f396  sub     rsp, 260h
0x18009f39d  mov     rax, cs:__security_cookie
0x18009f3a4  xor     rax, rsp
0x18009f3a7  mov     [rbp+170h+var_20], rax
0x18009f3ae  mov     r14, rcx
0x18009f3b1  mov     rbx, rdx
0x18009f3b4  mov     rcx, rdx; pbstr
0x18009f3b7  call    cs:__imp_SysStringLen
0x18009f3bd  test    eax, eax
0x18009f3bf  jnz     short loc_18009F3CB
0x18009f3c1  mov     eax, 80070057h
0x18009f3c6  jmp     loc_18009F4DB
0x18009f3cb  mov     rcx, rbx; psz
0x18009f3ce  call    cs:__imp_SysAllocString
0x18009f3d4  mov     rcx, rax; pszUrl
0x18009f3d7  mov     [rsp+270h+var_248], rax
0x18009f3dc  mov     edx, 3; UrlIs
0x18009f3e1  mov     rbx, rax
0x18009f3e4  call    cs:__imp_UrlIsW
0x18009f3ea  test    eax, eax
0x18009f3ec  jz      short loc_18009F42A
0x18009f3ee  xor     r9d, r9d; dwFlags
0x18009f3f1  mov     [rsp+270h+pcchPath], 104h
0x18009f3f9  lea     r8, [rsp+270h+pcchPath]; pcchPath
0x18009f3fe  mov     rcx, rbx; pszUrl
0x18009f401  lea     rdx, [rsp+270h+pszPath]; pszPath
0x18009f406  call    cs:__imp_PathCreateFromUrlW
0x18009f40c  mov     edi, eax
0x18009f40e  test    eax, eax
0x18009f410  js      loc_18009F4D0
0x18009f416  lea     rdx, [rsp+270h+pszPath]
0x18009f41b  lea     rcx, [rsp+270h+var_248]
0x18009f420  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18009f425  mov     rbx, [rsp+270h+var_248]
0x18009f42a  mov     rdx, [r14+40h]; struct IUnknown *
0x18009f42e  test    rdx, rdx
0x18009f431  jz      loc_18009F4C3
0x18009f437  lea     rcx, [rsp+270h+var_250]; struct IUnknown **
0x18009f43c  mov     [rsp+270h+var_250], 0
0x18009f445  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18009f44a  mov     rdi, [rsp+270h+var_250]
0x18009f44f  test    rdi, rdi
0x18009f452  jnz     short loc_18009F465
0x18009f454  lea     rcx, [rsp+270h+var_250]
0x18009f459  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x18009f45e  mov     edi, 8000FFFFh
0x18009f463  jmp     short loc_18009F4D0
0x18009f465  lea     rcx, [rsp+270h+var_248]; this
0x18009f46a  call    ?Copy@CComBSTR@ATL@@QEBAPEAGXZ; ATL::CComBSTR::Copy(void)
0x18009f46f  mov     rsi, rax
0x18009f472  xor     r8d, r8d
0x18009f475  mov     rax, [rdi]
0x18009f478  mov     rdx, rsi
0x18009f47b  mov     rcx, rdi
0x18009f47e  mov     rax, [rax+18h]
0x18009f482  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f487  mov     edi, eax
0x18009f489  test    eax, eax
0x18009f48b  js      short loc_18009F4B0
0x18009f48d  lea     rcx, [r14+18h]
0x18009f491  lea     rdx, [rsp+270h+var_248]
0x18009f496  call    ??4CComBSTR@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CComBSTR::operator=(ATL::CComBSTR const &)
0x18009f49b  mov     rcx, rsi; bstrString
0x18009f49e  call    cs:__imp_SysFreeString
0x18009f4a4  lea     rcx, [rsp+270h+var_250]
0x18009f4a9  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x18009f4ae  jmp     short loc_18009F4D0
0x18009f4b0  mov     rcx, rsi; bstrString
0x18009f4b3  call    cs:__imp_SysFreeString
0x18009f4b9  lea     rcx, [rsp+270h+var_250]
0x18009f4be  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x18009f4c3  mov     rdx, rbx
0x18009f4c6  mov     rcx, r14
0x18009f4c9  call    ?put_FileName@?$IMSVidFilePlaybackImpl@VCMSVidStreamBufferV2Source@@$1?LIBID_MSVidCtlLib@@3U_GUID@@B$1?_GUID_00000000_0000_0000_0000_000000000000@@3U__s_GUID@@BUIMSVidStreamBufferSource2@@@MSVideoControl@@UEAAJPEAG@Z; MSVideoControl::IMSVidFilePlaybackImpl<CMSVidStreamBufferV2Source,&_GUID const LIBID_MSVidCtlLib,&__s_GUID const _GUID_00000000_0000_0000_0000_000000000000,IMSVidStreamBufferSource2>::put_FileName(ushort *)
0x18009f4ce  mov     edi, eax
0x18009f4d0  mov     rcx, rbx; bstrString
0x18009f4d3  call    cs:__imp_SysFreeString
0x18009f4d9  mov     eax, edi
0x18009f4db  mov     rcx, [rbp+170h+var_20]
0x18009f4e2  xor     rcx, rsp; StackCookie
0x18009f4e5  call    __security_check_cookie
0x18009f4ea  lea     r11, [rsp+270h+var_10]
0x18009f4f2  mov     rbx, [r11+30h]
0x18009f4f6  mov     rsi, [r11+38h]
0x18009f4fa  mov     rsp, r11
0x18009f4fd  pop     r14
0x18009f4ff  pop     rdi
0x18009f500  pop     rbp
0x18009f501  retn
```
