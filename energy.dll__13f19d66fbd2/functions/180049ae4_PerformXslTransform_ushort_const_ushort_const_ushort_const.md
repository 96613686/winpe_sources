# PerformXslTransform(ushort const *,ushort const *,ushort const *)

- ea: `0x180049ae4`
- end: `0x180049f40`
- name: `?PerformXslTransform@@YAJPEBG00@Z`
- size: `1116`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, wchar_t *FileName)`
- caller_count: `4`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800561c0`
- `0x18005e270`
- `0x180077ec0`
- `0x18008a4f0`

## callees

- `0x180008da0`
- `0x1800340f4`
- `0x180049ae4`
- `0x180049f48`
- `0x180049fbc`
- `0x18004d92c`
- `0x180090090`
- `0x180090118`
- `0x18009013c`
- `0x180090160`
- `0x1800901a8`
- `0x180090208`
- `0x1800903f8`
- `0x18009055c`
- `0x180090570`
- `0x180096010`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!__doserrno` at `0x180049ea1`
- `api-ms-win-crt-runtime-l1-1-0!__doserrno` at `0x180049ea1`
- `api-ms-win-crt-private-l1-1-0!_o__wfopen_s` at `0x180049e97`
- `api-ms-win-crt-private-l1-1-0!_o__wfopen_s` at `0x180049e97`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x180049ef7`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x180049ef7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180049b43`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180049c73`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180049b43`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180049c73`
- `OLEAUT32!__imp_SysAllocString` at `0x180049ba0`
- `OLEAUT32!__imp_SysAllocString` at `0x180049ba0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180049dbb`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180049dbb`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall PerformXslTransform(const unsigned __int16 *a1, const unsigned __int16 *a2, wchar_t *FileName)
{
  int v6; // ebx
  struct IUnknown *v7; // rdi
  BSTR *v8; // rax
  BSTR *v9; // rbx
  BSTR v10; // rax
  int v11; // eax
  struct IUnknown *v12; // rbx
  struct IUnknown *v13; // rbx
  int v14; // eax
  struct IUnknown *v15; // rbx
  struct IUnknown *v16; // rax
  __int64 v17; // rax
  struct IUnknown *v18; // rax
  int v19; // ebx
  unsigned int i; // ebx
  struct IUnknown *v21; // rax
  struct IUnknown *v22; // rax
  struct IUnknown *v23; // rax
  __int64 v24; // rax
  struct IUnknown *v25; // rax
  int v26; // ebx
  __int64 v27; // rax
  __int64 v28; // rax
  _QWORD **v29; // rbx
  _QWORD *v30; // rbx
  __int64 v31; // r8
  LPVOID ppv; // [rsp+30h] [rbp-A8h] BYREF
  LPVOID v34; // [rsp+38h] [rbp-A0h] BYREF
  FILE *Stream; // [rsp+40h] [rbp-98h] BYREF
  _QWORD *v36; // [rsp+48h] [rbp-90h] BYREF
  _QWORD *v37; // [rsp+50h] [rbp-88h]
  __int128 v38; // [rsp+60h] [rbp-78h] BYREF
  __int64 v39; // [rsp+70h] [rbp-68h]
  __int128 v40; // [rsp+80h] [rbp-58h] BYREF
  __int64 v41; // [rsp+90h] [rbp-48h]
  BSTR *v42; // [rsp+F8h] [rbp+20h] BYREF

  v36 = 0;
  Stream = 0;
  v34 = 0;
  ppv = 0;
  _com_ptr_t<_com_IIID<MSXML6::IXMLDOMDocument,&__s_GUID const _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60>>::_Release(&ppv);
  ppv = 0;
  v6 = CoCreateInstance(&GUID_88d96a05_f192_11d4_a65f_0040963251e5, 0, 1u, &IID_IXMLDOMDocument2, &ppv);
  if ( v6 >= 0 )
  {
    v7 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML6::IXMLDOMDocument,&__s_GUID const _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60>>::operator->(&ppv);
    LOWORD(v40) = 11;
    WORD4(v40) = -1;
    v8 = (BSTR *)operator new(0x18u);
    v9 = v8;
    v37 = v8;
    if ( v8 )
    {
      v8[1] = 0;
      *((_DWORD *)v8 + 4) = 1;
      v10 = SysAllocString(L"AllowXsltScript");
      *v9 = v10;
      if ( !v10 )
        _com_issue_error(-2147024882);
    }
    else
    {
      v9 = 0;
    }
    v42 = v9;
    if ( !v9 )
      _com_issue_error(-2147024882);
    v37 = &v42;
    v38 = v40;
    v39 = v41;
    v11 = ((__int64 (__fastcall *)(struct IUnknown *, BSTR, __int128 *))v7->lpVtbl[26].Release)(v7, *v9, &v38);
    if ( v11 < 0 )
      _com_issue_errorex(v11, v7, &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60);
    _bstr_t::_Free((_bstr_t *)&v42);
    _variant_t::~_variant_t((_variant_t *)&v40);
    _com_ptr_t<_com_IIID<MSXML6::IXMLDOMDocument,&__s_GUID const _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60>>::_Release(&v34);
    v34 = 0;
    v6 = CoCreateInstance(&GUID_88d96a05_f192_11d4_a65f_0040963251e5, 0, 1u, &IID_IXMLDOMDocument, &v34);
    if ( v6 >= 0 )
    {
      v12 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML6::IXMLDOMDocument,&__s_GUID const _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60>>::operator->(&ppv);
      _variant_t::_variant_t((_variant_t *)&v38, a1);
      LOWORD(v12) = MSXML6::IXMLDOMDocument::load(v12, (const struct _variant_t *)&v38);
      _variant_t::~_variant_t((_variant_t *)&v38);
      if ( (_WORD)v12 )
      {
        v13 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML6::IXMLDOMDocument,&__s_GUID const _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60>>::operator->(&v34);
        v14 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD))v13->lpVtbl[21].QueryInterface)(v13, 0);
        if ( v14 < 0 )
          _com_issue_errorex(v14, v13, &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60);
        v15 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML6::IXMLDOMDocument,&__s_GUID const _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60>>::operator->(&v34);
        _variant_t::_variant_t((_variant_t *)&v38, a2);
        LOWORD(v15) = MSXML6::IXMLDOMDocument::load(v15, (const struct _variant_t *)&v38);
        _variant_t::~_variant_t((_variant_t *)&v38);
        if ( (_WORD)v15 )
        {
          v16 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML6::IXMLDOMDocument,&__s_GUID const _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60>>::operator->(&v34);
          v17 = MSXML6::IXMLDOMDocument::GetparseError(v16);
          v18 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML6::IXMLDOMDocument,&__s_GUID const _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60>>::operator->(v17);
          v19 = MSXML6::IXMLDOMParseError::GeterrorCode(v18);
          if ( v42 )
            (*((void (__fastcall **)(BSTR *))*v42 + 2))(v42);
          if ( v19 )
          {
            v6 = -2147467259;
          }
          else
          {
            for ( i = 0; ; ++i )
            {
              v21 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML6::IXMLDOMDocument,&__s_GUID const _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60>>::operator->(&ppv);
              if ( (unsigned int)MSXML6::IXMLDOMDocument::GetreadyState(v21) == 4 || i > 0xA )
                break;
              Sleep(0x3E8u);
            }
            v22 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML6::IXMLDOMDocument,&__s_GUID const _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60>>::operator->(&ppv);
            if ( (unsigned int)MSXML6::IXMLDOMDocument::GetreadyState(v22) == 4 )
            {
              v23 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML6::IXMLDOMDocument,&__s_GUID const _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60>>::operator->(&ppv);
              v24 = MSXML6::IXMLDOMDocument::GetparseError(v23);
              v25 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML6::IXMLDOMDocument,&__s_GUID const _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60>>::operator->(v24);
              v26 = MSXML6::IXMLDOMParseError::GeterrorCode(v25);
              if ( v42 )
                (*((void (__fastcall **)(BSTR *))*v42 + 2))(v42);
              if ( v26 )
              {
                v6 = -2147467259;
              }
              else
              {
                v27 = _com_ptr_t<_com_IIID<MSXML6::IXMLDOMDocument,&__s_GUID const _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60>>::operator->(&v34);
                v28 = MSXML6::IXMLDOMNode::transformNode(v27, &v42, ppv);
                v29 = (_QWORD **)v28;
                if ( *(_QWORD *)v28 )
                  _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)v28 + 16LL));
                _bstr_t::_Free((_bstr_t *)&v36);
                v30 = *v29;
                v36 = v30;
                _bstr_t::_Free((_bstr_t *)&v42);
                if ( _wfopen_s(&Stream, FileName, L"w, ccs=UTF-8") )
                {
                  v6 = *__doserrno();
                  if ( v6 > 0 )
                    v6 = (unsigned __int16)v6 | 0x80070000;
                }
                else
                {
                  fwprintf_s(Stream, L"<!DOCTYPE html>\n<!-- saved from url=(0016)http://localhost -->\n");
                  if ( v30 )
                    v31 = *v30;
                  else
                    v31 = 0;
                  if ( fwprintf_s(Stream, L"%s", v31) >= 0 )
                  {
                    fclose(Stream);
                    v6 = 0;
                  }
                  else
                  {
                    v6 = -2147467259;
                  }
                }
              }
            }
            else
            {
              v6 = -2147467259;
            }
          }
        }
        else
        {
          v6 = -2147467259;
        }
      }
      else
      {
        v6 = -2147467259;
      }
    }
  }
  _com_ptr_t<_com_IIID<MSXML6::IXMLDOMDocument,&__s_GUID const _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60>>::_Release(&ppv);
  _com_ptr_t<_com_IIID<MSXML6::IXMLDOMDocument,&__s_GUID const _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60>>::_Release(&v34);
  _bstr_t::_Free((_bstr_t *)&v36);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180049ae4  push    rbx
0x180049ae6  push    rsi
0x180049ae7  push    rdi
0x180049ae8  push    r12
0x180049aea  push    r14
0x180049aec  push    r15
0x180049aee  sub     rsp, 0A8h
0x180049af5  mov     r15, r8
0x180049af8  mov     r14, rdx
0x180049afb  mov     rsi, rcx
0x180049afe  xor     r12d, r12d
0x180049b01  mov     [rsp+0D8h+var_90], r12
0x180049b06  mov     [rsp+0D8h+Stream], r12
0x180049b0b  mov     [rsp+0D8h+var_A0], r12
0x180049b10  mov     [rsp+0D8h+var_A8], r12
0x180049b15  lea     rcx, [rsp+0D8h+var_A8]
0x180049b1a  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument@MSXML6@@$1?_GUID_2933bf81_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<MSXML6::IXMLDOMDocument,&__s_GUID const _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60>>::_Release(void)
0x180049b1f  mov     [rsp+0D8h+var_A8], r12
0x180049b24  lea     rax, [rsp+0D8h+var_A8]
0x180049b29  mov     [rsp+0D8h+ppv], rax; ppv
0x180049b2e  lea     r9, IID_IXMLDOMDocument2; riid
0x180049b35  xor     edx, edx; pUnkOuter
0x180049b37  lea     r8d, [r12+1]; dwClsContext
0x180049b3c  lea     rcx, _GUID_88d96a05_f192_11d4_a65f_0040963251e5; rclsid
0x180049b43  call    cs:__imp_CoCreateInstance
0x180049b49  mov     ebx, eax
0x180049b4b  test    eax, eax
0x180049b4d  jns     short loc_180049B54
0x180049b4f  jmp     loc_180049F0D
0x180049b54  lea     rcx, [rsp+0D8h+var_A8]
0x180049b59  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument@MSXML6@@$1?_GUID_2933bf81_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument@MSXML6@@XZ; _com_ptr_t<_com_IIID<MSXML6::IXMLDOMDocument,&__s_GUID const _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x180049b5e  mov     rdi, rax
0x180049b61  mov     eax, 0Bh
0x180049b66  mov     word ptr [rsp+0D8h+var_58], ax
0x180049b6e  or      eax, 0FFFFFFFFh
0x180049b71  mov     word ptr [rsp+0D8h+var_58+8], ax
0x180049b79  lea     ecx, [rax+19h]; dwBytes
0x180049b7c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180049b81  mov     rbx, rax
0x180049b84  mov     [rsp+0D8h+var_88], rax
0x180049b89  test    rax, rax
0x180049b8c  jz      short loc_180049BB8
0x180049b8e  mov     [rax+8], r12
0x180049b92  mov     dword ptr [rax+10h], 1
0x180049b99  lea     rcx, psz; "AllowXsltScript"
0x180049ba0  call    cs:__imp_SysAllocString
0x180049ba6  mov     [rbx], rax
0x180049ba9  test    rax, rax
0x180049bac  jnz     short loc_180049BBB
0x180049bae  mov     ecx, 8007000Eh; int
0x180049bb3  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180049bb8  mov     rbx, r12
0x180049bbb  mov     [rsp+0D8h+arg_18], rbx
0x180049bc3  test    rbx, rbx
0x180049bc6  jnz     short loc_180049BD2
0x180049bc8  mov     ecx, 8007000Eh; int
0x180049bcd  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180049bd2  lea     rax, [rsp+0D8h+arg_18]
0x180049bda  mov     [rsp+0D8h+var_88], rax
0x180049bdf  movups  xmm0, [rsp+0D8h+var_58]
0x180049be7  movaps  [rsp+0D8h+var_78], xmm0
0x180049bec  movsd   xmm1, [rsp+0D8h+var_48]
0x180049bf5  movsd   [rsp+0D8h+var_68], xmm1
0x180049bfb  mov     rax, [rdi]
0x180049bfe  lea     r8, [rsp+0D8h+var_78]
0x180049c03  mov     rdx, [rbx]
0x180049c06  mov     rcx, rdi
0x180049c09  mov     rax, [rax+280h]
0x180049c10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049c15  test    eax, eax
0x180049c17  jns     short loc_180049C2B
0x180049c19  lea     r8, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60; struct _GUID *
0x180049c20  mov     rdx, rdi; struct IUnknown *
0x180049c23  mov     ecx, eax; int
0x180049c25  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
0x180049c2b  lea     rcx, [rsp+0D8h+arg_18]; this
0x180049c33  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180049c38  nop
0x180049c39  lea     rcx, [rsp+0D8h+var_58]; this
0x180049c41  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180049c46  lea     rcx, [rsp+0D8h+var_A0]
0x180049c4b  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument@MSXML6@@$1?_GUID_2933bf81_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<MSXML6::IXMLDOMDocument,&__s_GUID const _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60>>::_Release(void)
0x180049c50  mov     [rsp+0D8h+var_A0], r12
0x180049c55  lea     rax, [rsp+0D8h+var_A0]
0x180049c5a  mov     [rsp+0D8h+ppv], rax; ppv
0x180049c5f  lea     r9, IID_IXMLDOMDocument; riid
0x180049c66  xor     edx, edx; pUnkOuter
0x180049c68  lea     r8d, [rdx+1]; dwClsContext
0x180049c6c  lea     rcx, _GUID_88d96a05_f192_11d4_a65f_0040963251e5; rclsid
0x180049c73  call    cs:__imp_CoCreateInstance
0x180049c79  mov     ebx, eax
0x180049c7b  test    eax, eax
0x180049c7d  jns     short loc_180049C84
0x180049c7f  jmp     loc_180049F0D
0x180049c84  lea     rcx, [rsp+0D8h+var_A8]
0x180049c89  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument@MSXML6@@$1?_GUID_2933bf81_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument@MSXML6@@XZ; _com_ptr_t<_com_IIID<MSXML6::IXMLDOMDocument,&__s_GUID const _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x180049c8e  mov     rbx, rax
0x180049c91  mov     rdx, rsi; unsigned __int16 *
0x180049c94  lea     rcx, [rsp+0D8h+var_78]; this
0x180049c99  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x180049c9e  nop
0x180049c9f  lea     rdx, [rsp+0D8h+var_78]; struct _variant_t *
0x180049ca4  mov     rcx, rbx; this
0x180049ca7  call    ?load@IXMLDOMDocument@MSXML6@@QEAAFAEBV_variant_t@@@Z; MSXML6::IXMLDOMDocument::load(_variant_t const &)
0x180049cac  movzx   ebx, ax
0x180049caf  lea     rcx, [rsp+0D8h+var_78]; this
0x180049cb4  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180049cb9  test    bx, bx
0x180049cbc  jnz     short loc_180049CC8
0x180049cbe  mov     ebx, 80004005h
0x180049cc3  jmp     loc_180049F0D
0x180049cc8  lea     rcx, [rsp+0D8h+var_A0]
0x180049ccd  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument@MSXML6@@$1?_GUID_2933bf81_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument@MSXML6@@XZ; _com_ptr_t<_com_IIID<MSXML6::IXMLDOMDocument,&__s_GUID const _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x180049cd2  mov     rbx, rax
0x180049cd5  mov     rcx, [rax]
0x180049cd8  xor     edx, edx
0x180049cda  mov     rax, [rcx+1F8h]
0x180049ce1  mov     rcx, rbx
0x180049ce4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049ce9  test    eax, eax
0x180049ceb  jns     short loc_180049CFE
0x180049ced  lea     r8, _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60; struct _GUID *
0x180049cf4  mov     rdx, rbx; struct IUnknown *
0x180049cf7  mov     ecx, eax; int
0x180049cf9  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
0x180049cfe  lea     rcx, [rsp+0D8h+var_A0]
0x180049d03  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument@MSXML6@@$1?_GUID_2933bf81_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument@MSXML6@@XZ; _com_ptr_t<_com_IIID<MSXML6::IXMLDOMDocument,&__s_GUID const _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x180049d08  mov     rbx, rax
0x180049d0b  mov     rdx, r14; unsigned __int16 *
0x180049d0e  lea     rcx, [rsp+0D8h+var_78]; this
0x180049d13  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x180049d18  nop
0x180049d19  lea     rdx, [rsp+0D8h+var_78]; struct _variant_t *
0x180049d1e  mov     rcx, rbx; this
0x180049d21  call    ?load@IXMLDOMDocument@MSXML6@@QEAAFAEBV_variant_t@@@Z; MSXML6::IXMLDOMDocument::load(_variant_t const &)
0x180049d26  movzx   ebx, ax
0x180049d29  lea     rcx, [rsp+0D8h+var_78]; this
0x180049d2e  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180049d33  test    bx, bx
0x180049d36  jnz     short loc_180049D42
0x180049d38  mov     ebx, 80004005h
0x180049d3d  jmp     loc_180049F0D
0x180049d42  lea     rcx, [rsp+0D8h+var_A0]
0x180049d47  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument@MSXML6@@$1?_GUID_2933bf81_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument@MSXML6@@XZ; _com_ptr_t<_com_IIID<MSXML6::IXMLDOMDocument,&__s_GUID const _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x180049d4c  lea     rdx, [rsp+0D8h+arg_18]
0x180049d54  mov     rcx, rax; struct IUnknown *
0x180049d57  call    ?GetparseError@IXMLDOMDocument@MSXML6@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMParseError@MSXML6@@$1?_GUID_3efaa426_272f_11d2_836f_0000f87a7782@@3U__s_GUID@@B@@@@XZ; MSXML6::IXMLDOMDocument::GetparseError(void)
0x180049d5c  nop
0x180049d5d  mov     rcx, rax
0x180049d60  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument@MSXML6@@$1?_GUID_2933bf81_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument@MSXML6@@XZ; _com_ptr_t<_com_IIID<MSXML6::IXMLDOMDocument,&__s_GUID const _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x180049d65  mov     rcx, rax; this
0x180049d68  call    ?GeterrorCode@IXMLDOMParseError@MSXML6@@QEAAJXZ; MSXML6::IXMLDOMParseError::GeterrorCode(void)
0x180049d6d  mov     ebx, eax
0x180049d6f  mov     rcx, [rsp+0D8h+arg_18]
0x180049d77  test    rcx, rcx
0x180049d7a  jz      short loc_180049D89
0x180049d7c  mov     rdx, [rcx]
0x180049d7f  mov     rax, [rdx+10h]
0x180049d83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049d88  nop
0x180049d89  test    ebx, ebx
0x180049d8b  jz      short loc_180049D97
0x180049d8d  mov     ebx, 80004005h
0x180049d92  jmp     loc_180049F0D
0x180049d97  mov     ebx, r12d
0x180049d9a  lea     rcx, [rsp+0D8h+var_A8]
0x180049d9f  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument@MSXML6@@$1?_GUID_2933bf81_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument@MSXML6@@XZ; _com_ptr_t<_com_IIID<MSXML6::IXMLDOMDocument,&__s_GUID const _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x180049da4  mov     rcx, rax; this
0x180049da7  call    ?GetreadyState@IXMLDOMDocument@MSXML6@@QEAAJXZ; MSXML6::IXMLDOMDocument::GetreadyState(void)
0x180049dac  cmp     eax, 4
0x180049daf  jz      short loc_180049DC5
0x180049db1  cmp     ebx, 0Ah
0x180049db4  ja      short loc_180049DC5
0x180049db6  mov     ecx, 3E8h; dwMilliseconds
0x180049dbb  call    cs:__imp_Sleep
0x180049dc1  inc     ebx
0x180049dc3  jmp     short loc_180049D9A
0x180049dc5  lea     rcx, [rsp+0D8h+var_A8]
0x180049dca  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument@MSXML6@@$1?_GUID_2933bf81_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument@MSXML6@@XZ; _com_ptr_t<_com_IIID<MSXML6::IXMLDOMDocument,&__s_GUID const _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x180049dcf  mov     rcx, rax; this
0x180049dd2  call    ?GetreadyState@IXMLDOMDocument@MSXML6@@QEAAJXZ; MSXML6::IXMLDOMDocument::GetreadyState(void)
0x180049dd7  cmp     eax, 4
0x180049dda  jz      short loc_180049DE6
0x180049ddc  mov     ebx, 80004005h
0x180049de1  jmp     loc_180049F0D
0x180049de6  lea     rcx, [rsp+0D8h+var_A8]
0x180049deb  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument@MSXML6@@$1?_GUID_2933bf81_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument@MSXML6@@XZ; _com_ptr_t<_com_IIID<MSXML6::IXMLDOMDocument,&__s_GUID const _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x180049df0  lea     rdx, [rsp+0D8h+arg_18]
0x180049df8  mov     rcx, rax; struct IUnknown *
0x180049dfb  call    ?GetparseError@IXMLDOMDocument@MSXML6@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMParseError@MSXML6@@$1?_GUID_3efaa426_272f_11d2_836f_0000f87a7782@@3U__s_GUID@@B@@@@XZ; MSXML6::IXMLDOMDocument::GetparseError(void)
0x180049e00  nop
0x180049e01  mov     rcx, rax
0x180049e04  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument@MSXML6@@$1?_GUID_2933bf81_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument@MSXML6@@XZ; _com_ptr_t<_com_IIID<MSXML6::IXMLDOMDocument,&__s_GUID const _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x180049e09  mov     rcx, rax; this
0x180049e0c  call    ?GeterrorCode@IXMLDOMParseError@MSXML6@@QEAAJXZ; MSXML6::IXMLDOMParseError::GeterrorCode(void)
0x180049e11  mov     ebx, eax
0x180049e13  mov     rcx, [rsp+0D8h+arg_18]
0x180049e1b  test    rcx, rcx
0x180049e1e  jz      short loc_180049E2D
0x180049e20  mov     rdx, [rcx]
0x180049e23  mov     rax, [rdx+10h]
0x180049e27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049e2c  nop
0x180049e2d  test    ebx, ebx
0x180049e2f  jz      short loc_180049E3B
0x180049e31  mov     ebx, 80004005h
0x180049e36  jmp     loc_180049F0D
0x180049e3b  lea     rcx, [rsp+0D8h+var_A0]
0x180049e40  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument@MSXML6@@$1?_GUID_2933bf81_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument@MSXML6@@XZ; _com_ptr_t<_com_IIID<MSXML6::IXMLDOMDocument,&__s_GUID const _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x180049e45  mov     r8, [rsp+0D8h+var_A8]
0x180049e4a  lea     rdx, [rsp+0D8h+arg_18]
0x180049e52  mov     rcx, rax
0x180049e55  call    ?transformNode@IXMLDOMNode@MSXML6@@QEAA?AV_bstr_t@@PEAU12@@Z; MSXML6::IXMLDOMNode::transformNode(MSXML6::IXMLDOMNode *)
0x180049e5a  mov     rbx, rax
0x180049e5d  mov     rcx, [rax]
0x180049e60  test    rcx, rcx
0x180049e63  jz      short loc_180049E69
0x180049e65  lock inc dword ptr [rcx+10h]
0x180049e69  lea     rcx, [rsp+0D8h+var_90]; this
0x180049e6e  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180049e73  mov     rbx, [rbx]
0x180049e76  mov     [rsp+0D8h+var_90], rbx
0x180049e7b  lea     rcx, [rsp+0D8h+arg_18]; this
0x180049e83  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180049e88  lea     r8, aWCcsUtf8; "w, ccs=UTF-8"
0x180049e8f  mov     rdx, r15; FileName
0x180049e92  lea     rcx, [rsp+0D8h+Stream]; Stream
0x180049e97  call    cs:__imp__wfopen_s
0x180049e9d  test    eax, eax
0x180049e9f  jz      short loc_180049EB8
0x180049ea1  call    cs:__imp___doserrno
0x180049ea7  mov     ebx, [rax]
0x180049ea9  test    ebx, ebx
0x180049eab  jle     short loc_180049EB6
0x180049ead  movzx   ebx, bx
0x180049eb0  or      ebx, 80070000h
0x180049eb6  jmp     short loc_180049F0D
0x180049eb8  lea     rdx, aDoctypeHtmlSav; "<!DOCTYPE html>\n<!-- saved from url=(0"...
0x180049ebf  mov     rcx, [rsp+0D8h+Stream]; Stream
0x180049ec4  call    fwprintf_s
0x180049ec9  test    rbx, rbx
0x180049ecc  jz      short loc_180049ED3
0x180049ece  mov     r8, [rbx]
0x180049ed1  jmp     short loc_180049ED6
0x180049ed3  mov     r8, r12
0x180049ed6  lea     rdx, aS; "%s"
0x180049edd  mov     rcx, [rsp+0D8h+Stream]; Stream
0x180049ee2  call    fwprintf_s
0x180049ee7  test    eax, eax
0x180049ee9  jns     short loc_180049EF2
0x180049eeb  mov     ebx, 80004005h
0x180049ef0  jmp     short loc_180049F0D
0x180049ef2  mov     rcx, [rsp+0D8h+Stream]; Stream
0x180049ef7  call    cs:__imp_fclose
0x180049efd  mov     ebx, r12d
0x180049f00  jmp     short loc_180049F0D
0x180049f02  jmp     short loc_180049F06
0x180049f04  jmp     short $+2
0x180049f06  mov     ebx, dword ptr [rsp+0D8h+arg_18]
0x180049f0d  lea     rcx, [rsp+0D8h+var_A8]
0x180049f12  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument@MSXML6@@$1?_GUID_2933bf81_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<MSXML6::IXMLDOMDocument,&__s_GUID const _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60>>::_Release(void)
0x180049f17  nop
0x180049f18  lea     rcx, [rsp+0D8h+var_A0]
0x180049f1d  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument@MSXML6@@$1?_GUID_2933bf81_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<MSXML6::IXMLDOMDocument,&__s_GUID const _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60>>::_Release(void)
0x180049f22  nop
0x180049f23  lea     rcx, [rsp+0D8h+var_90]; this
0x180049f28  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180049f2d  mov     eax, ebx
0x180049f2f  add     rsp, 0A8h
0x180049f36  pop     r15
0x180049f38  pop     r14
0x180049f3a  pop     r12
0x180049f3c  pop     rdi
0x180049f3d  pop     rsi
0x180049f3e  pop     rbx
0x180049f3f  retn
```
