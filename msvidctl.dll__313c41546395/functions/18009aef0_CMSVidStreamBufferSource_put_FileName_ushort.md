# CMSVidStreamBufferSource::put_FileName(ushort *)

- ea: `0x18009aef0`
- end: `0x18009b072`
- name: `?put_FileName@CMSVidStreamBufferSource@@UEAAJPEAG@Z`
- size: `386`
- prototype: `int(CMSVidStreamBufferSource *__hidden this, unsigned __int16 *)`
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
- `0x18009ac74`
- `0x18009aef0`
- `0x1800f8010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18009af3e`
- `OLEAUT32!__imp_SysAllocString` at `0x18009af3e`
- `OLEAUT32!__imp_SysFreeString` at `0x18009b00e`
- `OLEAUT32!__imp_SysFreeString` at `0x18009b023`
- `OLEAUT32!__imp_SysFreeString` at `0x18009b043`
- `OLEAUT32!__imp_SysFreeString` at `0x18009b00e`
- `OLEAUT32!__imp_SysFreeString` at `0x18009b023`
- `OLEAUT32!__imp_SysFreeString` at `0x18009b043`
- `OLEAUT32!__imp_SysStringLen` at `0x18009af27`
- `OLEAUT32!__imp_SysStringLen` at `0x18009af27`
- `SHLWAPI!PathCreateFromUrlW` at `0x18009af76`
- `SHLWAPI!PathCreateFromUrlW` at `0x18009af76`
- `SHLWAPI!UrlIsW` at `0x18009af54`
- `SHLWAPI!UrlIsW` at `0x18009af54`

## pseudocode

```c
__int64 __fastcall CMSVidStreamBufferSource::put_FileName(CMSVidStreamBufferSource *this, unsigned __int16 *a2)
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
    v7 = (struct IUnknown *)*((_QWORD *)this + 7);
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
    v6 = MSVideoControl::IMSVidFilePlaybackImpl<CMSVidStreamBufferSource,&_GUID const LIBID_MSVidCtlLib,&__s_GUID const _GUID_00000000_0000_0000_0000_000000000000,IMSVidStreamBufferSource2>::put_FileName(
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
0x18009aef0  mov     [rsp-8+arg_10], rbx
0x18009aef5  mov     [rsp-8+arg_18], rsi
0x18009aefa  push    rbp
0x18009aefb  push    rdi
0x18009aefc  push    r14
0x18009aefe  lea     rbp, [rsp-160h]
0x18009af06  sub     rsp, 260h
0x18009af0d  mov     rax, cs:__security_cookie
0x18009af14  xor     rax, rsp
0x18009af17  mov     [rbp+170h+var_20], rax
0x18009af1e  mov     r14, rcx
0x18009af21  mov     rbx, rdx
0x18009af24  mov     rcx, rdx; pbstr
0x18009af27  call    cs:__imp_SysStringLen
0x18009af2d  test    eax, eax
0x18009af2f  jnz     short loc_18009AF3B
0x18009af31  mov     eax, 80070057h
0x18009af36  jmp     loc_18009B04B
0x18009af3b  mov     rcx, rbx; psz
0x18009af3e  call    cs:__imp_SysAllocString
0x18009af44  mov     rcx, rax; pszUrl
0x18009af47  mov     [rsp+270h+var_248], rax
0x18009af4c  mov     edx, 3; UrlIs
0x18009af51  mov     rbx, rax
0x18009af54  call    cs:__imp_UrlIsW
0x18009af5a  test    eax, eax
0x18009af5c  jz      short loc_18009AF9A
0x18009af5e  xor     r9d, r9d; dwFlags
0x18009af61  mov     [rsp+270h+pcchPath], 104h
0x18009af69  lea     r8, [rsp+270h+pcchPath]; pcchPath
0x18009af6e  mov     rcx, rbx; pszUrl
0x18009af71  lea     rdx, [rsp+270h+pszPath]; pszPath
0x18009af76  call    cs:__imp_PathCreateFromUrlW
0x18009af7c  mov     edi, eax
0x18009af7e  test    eax, eax
0x18009af80  js      loc_18009B040
0x18009af86  lea     rdx, [rsp+270h+pszPath]
0x18009af8b  lea     rcx, [rsp+270h+var_248]
0x18009af90  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18009af95  mov     rbx, [rsp+270h+var_248]
0x18009af9a  mov     rdx, [r14+38h]; struct IUnknown *
0x18009af9e  test    rdx, rdx
0x18009afa1  jz      loc_18009B033
0x18009afa7  lea     rcx, [rsp+270h+var_250]; struct IUnknown **
0x18009afac  mov     [rsp+270h+var_250], 0
0x18009afb5  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18009afba  mov     rdi, [rsp+270h+var_250]
0x18009afbf  test    rdi, rdi
0x18009afc2  jnz     short loc_18009AFD5
0x18009afc4  lea     rcx, [rsp+270h+var_250]
0x18009afc9  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x18009afce  mov     edi, 8000FFFFh
0x18009afd3  jmp     short loc_18009B040
0x18009afd5  lea     rcx, [rsp+270h+var_248]; this
0x18009afda  call    ?Copy@CComBSTR@ATL@@QEBAPEAGXZ; ATL::CComBSTR::Copy(void)
0x18009afdf  mov     rsi, rax
0x18009afe2  xor     r8d, r8d
0x18009afe5  mov     rax, [rdi]
0x18009afe8  mov     rdx, rsi
0x18009afeb  mov     rcx, rdi
0x18009afee  mov     rax, [rax+18h]
0x18009aff2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009aff7  mov     edi, eax
0x18009aff9  test    eax, eax
0x18009affb  js      short loc_18009B020
0x18009affd  lea     rcx, [r14+18h]
0x18009b001  lea     rdx, [rsp+270h+var_248]
0x18009b006  call    ??4CComBSTR@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CComBSTR::operator=(ATL::CComBSTR const &)
0x18009b00b  mov     rcx, rsi; bstrString
0x18009b00e  call    cs:__imp_SysFreeString
0x18009b014  lea     rcx, [rsp+270h+var_250]
0x18009b019  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x18009b01e  jmp     short loc_18009B040
0x18009b020  mov     rcx, rsi; bstrString
0x18009b023  call    cs:__imp_SysFreeString
0x18009b029  lea     rcx, [rsp+270h+var_250]
0x18009b02e  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x18009b033  mov     rdx, rbx
0x18009b036  mov     rcx, r14
0x18009b039  call    ?put_FileName@?$IMSVidFilePlaybackImpl@VCMSVidStreamBufferSource@@$1?LIBID_MSVidCtlLib@@3U_GUID@@B$1?_GUID_00000000_0000_0000_0000_000000000000@@3U__s_GUID@@BUIMSVidStreamBufferSource2@@@MSVideoControl@@UEAAJPEAG@Z; MSVideoControl::IMSVidFilePlaybackImpl<CMSVidStreamBufferSource,&_GUID const LIBID_MSVidCtlLib,&__s_GUID const _GUID_00000000_0000_0000_0000_000000000000,IMSVidStreamBufferSource2>::put_FileName(ushort *)
0x18009b03e  mov     edi, eax
0x18009b040  mov     rcx, rbx; bstrString
0x18009b043  call    cs:__imp_SysFreeString
0x18009b049  mov     eax, edi
0x18009b04b  mov     rcx, [rbp+170h+var_20]
0x18009b052  xor     rcx, rsp; StackCookie
0x18009b055  call    __security_check_cookie
0x18009b05a  lea     r11, [rsp+270h+var_10]
0x18009b062  mov     rbx, [r11+30h]
0x18009b066  mov     rsi, [r11+38h]
0x18009b06a  mov     rsp, r11
0x18009b06d  pop     r14
0x18009b06f  pop     rdi
0x18009b070  pop     rbp
0x18009b071  retn
```
