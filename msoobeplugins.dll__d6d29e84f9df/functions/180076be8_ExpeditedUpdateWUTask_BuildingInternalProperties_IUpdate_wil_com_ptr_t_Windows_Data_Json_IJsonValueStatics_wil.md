# ExpeditedUpdateWUTask::_BuildingInternalProperties(IUpdate *,wil::com_ptr_t<Windows::Data::Json::IJsonValueStatics,wil::err_exception_policy>,wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy> &)

- ea: `0x180076be8`
- end: `0x180076f9b`
- name: `?_BuildingInternalProperties@ExpeditedUpdateWUTask@@AEAAJPEAUIUpdate@@V?$com_ptr_t@UIJsonValueStatics@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@AEAV?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@4@@Z`
- size: `947`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800765c8`

## callees

- `0x180003470`
- `0x180008544`
- `0x18001ad08`
- `0x1800230b0`
- `0x180040898`
- `0x1800418d8`
- `0x180043c58`
- `0x180076be8`
- `0x1800b8834`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180076e37`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180076e37`
- `OLEAUT32!__imp_SysStringLen` at `0x180076e27`
- `OLEAUT32!__imp_SysStringLen` at `0x180076e27`
- `OLEAUT32!__imp_VariantInit` at `0x180076c6e`
- `OLEAUT32!__imp_VariantInit` at `0x180076c79`
- `OLEAUT32!__imp_VariantInit` at `0x180076c6e`
- `OLEAUT32!__imp_VariantInit` at `0x180076c79`
- `OLEAUT32!__imp_VariantClear` at `0x180076efc`
- `OLEAUT32!__imp_VariantClear` at `0x180076f59`
- `OLEAUT32!__imp_VariantClear` at `0x180076efc`
- `OLEAUT32!__imp_VariantClear` at `0x180076f59`

## string_xrefs

- `0x180076c46`: `shell\oobe\machine\plugins\adapters\com\expeditedupdatewutasks.cpp`
- `0x180076c63`: `shell\oobe\machine\plugins\adapters\com\expeditedupdatewutasks.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall ExpeditedUpdateWUTask::_BuildingInternalProperties(
        __int64 a1,
        __int64 (__fastcall ***a2)(_QWORD, GUID *, __int64 *),
        __int64 *a3,
        __int64 *a4)
{
  __int64 (__fastcall **v6)(_QWORD, GUID *, __int64 *); // rax
  int v7; // eax
  unsigned int v8; // ebx
  wchar_t **v9; // r13
  int v10; // eax
  unsigned __int64 v11; // rdx
  char v12; // r8
  __int64 v13; // rbx
  __int64 (__fastcall *v14)(__int64, unsigned __int64, __int64 *); // rdi
  __int64 v15; // rcx
  int v16; // eax
  wil::details::in1diag3 *v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rbx
  __int64 (__fastcall *v20)(__int64, _QWORD, __int64 *); // rdi
  __int64 v21; // rcx
  __int64 v22; // rbx
  __int64 (__fastcall *v23)(__int64, unsigned __int64, __int64 *); // rdi
  __int64 v24; // rcx
  UINT v25; // eax
  HRESULT v26; // eax
  __int64 v27; // rbx
  __int64 (__fastcall *v28)(__int64, HSTRING, __int64 *); // rdi
  __int64 v29; // rcx
  int v30; // eax
  __int64 v31; // rbx
  __int64 v32; // rsi
  __int64 (__fastcall *v33)(__int64, PVOID, __int64); // rdi
  HSTRING_HEADER *v34; // rax
  int v35; // eax
  __int64 v37; // [rsp+20h] [rbp-60h] BYREF
  HSTRING string; // [rsp+28h] [rbp-58h] BYREF
  __int64 v39; // [rsp+30h] [rbp-50h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-48h] BYREF
  __int64 *v41; // [rsp+50h] [rbp-30h]
  HSTRING_HEADER v42; // [rsp+58h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  v41 = a3;
  v6 = *a2;
  v39 = 0;
  v7 = (*v6)(a2, &GUID_f7a9d4c1_ea19_4c5a_bf5d_c4173d2734c2, &v39);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v9 = &off_1800D1890;
    while ( 1 )
    {
      VariantInit(&pvarg);
      VariantInit(&pvarg);
      v37 = 0;
      v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, VARIANTARG *))(*(_QWORD *)v39 + 24LL))(
              v39,
              *((unsigned int *)v9 + 2),
              &pvarg);
      if ( v10 >= 0 )
        break;
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x473,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdatewutasks.cpp",
        (const char *)(unsigned int)v10,
        v37);
LABEL_35:
      wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v37);
      VariantClear(&pvarg);
      v9 += 2;
      if ( v9 == `ExpeditedUpdateTelemetryHelper::ExpeditedUpdateReasons'::`2'::reasons )
      {
        wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v39);
        wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(a3);
        return 0;
      }
    }
    switch ( pvarg.vt )
    {
      case 8u:
        string = 0;
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
          &string,
          0);
        v25 = SysStringLen(pvarg.bstrVal);
        v26 = WindowsCreateString(pvarg.bstrVal, v25, &string);
        v8 = v26;
        if ( v26 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x47F,
            (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdatewutasks.cpp",
            (const char *)(unsigned int)v26,
            v37);
          Windows::Internal::String::~String((Windows::Internal::String *)&string);
          wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v37);
          VariantClear(&pvarg);
          goto LABEL_38;
        }
        v27 = *a3;
        v28 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)*a3 + 80LL);
        v29 = v37;
        v37 = 0;
        if ( v29 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
        v30 = v28(v27, string, &v37);
        if ( v30 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x480,
            (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdatewutasks.cpp",
            (const char *)(unsigned int)v30,
            v37);
        Windows::Internal::String::~String((Windows::Internal::String *)&string);
        goto LABEL_32;
      case 0xBu:
        v22 = *a3;
        v23 = *(__int64 (__fastcall **)(__int64, unsigned __int64, __int64 *))(*(_QWORD *)*a3 + 64LL);
        v24 = v37;
        v37 = 0;
        if ( v24 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
        LOBYTE(v11) = pvarg.bVal;
        v16 = v23(v22, v11, &v37);
        v17 = retaddr;
        if ( v16 >= 0 )
          goto LABEL_32;
        v18 = 1145;
        break;
      case 0x13u:
        v19 = *a3;
        v20 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)*a3 + 72LL);
        v21 = v37;
        v37 = 0;
        if ( v21 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
        v16 = v20(v19, pvarg.cyVal.Lo, &v37);
        v17 = retaddr;
        if ( v16 >= 0 )
          goto LABEL_32;
        v18 = 1162;
        break;
      case 0x15u:
        v13 = *a3;
        v14 = *(__int64 (__fastcall **)(__int64, unsigned __int64, __int64 *))(*(_QWORD *)*a3 + 72LL);
        v15 = v37;
        v37 = 0;
        if ( v15 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
        if ( pvarg.llVal < 0 )
          v11 = pvarg.bVal & 1 | ((unsigned __int64)pvarg.llVal >> 1);
        v16 = v14(v13, v11, &v37);
        v17 = retaddr;
        if ( v16 >= 0 )
          goto LABEL_32;
        v18 = 1157;
        break;
      default:
        UnattendLogW(1, L"Unexpected internal property type! [%d - %d]", *((unsigned int *)v9 + 2));
        goto LABEL_32;
    }
    wil::details::in1diag3::_Log_Hr(
      v17,
      (void *)v18,
      (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdatewutasks.cpp",
      (const char *)(unsigned int)v16,
      v37);
LABEL_32:
    v31 = v37;
    if ( v37 )
    {
      v32 = *a4;
      v33 = *(__int64 (__fastcall **)(__int64, PVOID, __int64))(*(_QWORD *)*a4 + 56LL);
      v34 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v42, (const WCHAR **)v9, v12);
      v35 = v33(v32, v34[1].Reserved.Reserved1, v31);
      if ( v35 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x496,
          (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdatewutasks.cpp",
          (const char *)(unsigned int)v35,
          v37);
    }
    goto LABEL_35;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x45F,
    (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdatewutasks.cpp",
    (const char *)(unsigned int)v7,
    v37);
LABEL_38:
  wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v39);
  wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(a3);
  return v8;
}

```

## disassembly

```asm
0x180076be8  mov     [rsp-38h+arg_0], rbx
0x180076bed  push    rbp
0x180076bee  push    rsi
0x180076bef  push    rdi
0x180076bf0  push    r12
0x180076bf2  push    r13
0x180076bf4  push    r14
0x180076bf6  push    r15
0x180076bf8  mov     rbp, rsp
0x180076bfb  sub     rsp, 80h
0x180076c02  mov     rax, cs:__security_cookie
0x180076c09  xor     rax, rsp
0x180076c0c  mov     [rbp+var_8], rax
0x180076c10  mov     r12, r9
0x180076c13  mov     r15, r8
0x180076c16  mov     rcx, rdx
0x180076c19  mov     [rbp+var_30], r8
0x180076c1d  mov     rax, [rdx]
0x180076c20  xor     esi, esi
0x180076c22  mov     [rbp+var_50], rsi
0x180076c26  lea     r8, [rbp+var_50]
0x180076c2a  lea     rdx, _GUID_f7a9d4c1_ea19_4c5a_bf5d_c4173d2734c2
0x180076c31  mov     rax, [rax]
0x180076c34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076c39  mov     ebx, eax
0x180076c3b  test    eax, eax
0x180076c3d  jns     short loc_180076C5C
0x180076c3f  mov     rcx, [rbp+38h]; this
0x180076c43  mov     r9d, eax; char *
0x180076c46  lea     r8, aShellOobeMachi_0; "shell\\oobe\\machine\\plugins\\adapters"...
0x180076c4d  mov     edx, 45Fh; void *
0x180076c52  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076c57  jmp     loc_180076F60
0x180076c5c  lea     r13, off_1800D1890; "FlightID"
0x180076c63  lea     r14, aShellOobeMachi_0; "shell\\oobe\\machine\\plugins\\adapters"...
0x180076c6a  lea     rcx, [rbp+pvarg]; pvarg
0x180076c6e  call    cs:__imp_VariantInit
0x180076c74  nop
0x180076c75  lea     rcx, [rbp+pvarg]; pvarg
0x180076c79  call    cs:__imp_VariantInit
0x180076c7f  mov     [rbp+var_60], rsi
0x180076c83  mov     rcx, [rbp+var_50]
0x180076c87  mov     rax, [rcx]
0x180076c8a  lea     r8, [rbp+pvarg]
0x180076c8e  mov     edx, [r13+8]
0x180076c92  mov     rax, [rax+18h]
0x180076c96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076c9b  mov     rcx, [rbp+38h]; this
0x180076c9f  test    eax, eax
0x180076ca1  jns     short loc_180076CB8
0x180076ca3  mov     r9d, eax; char *
0x180076ca6  mov     r8, r14; unsigned int
0x180076ca9  mov     edx, 473h; void *
0x180076cae  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180076cb3  jmp     loc_180076EEE
0x180076cb8  movzx   r9d, word ptr [rbp+pvarg]
0x180076cbd  cmp     r9d, 8
0x180076cc1  jz      loc_180076E14
0x180076cc7  cmp     r9d, 0Bh
0x180076ccb  jz      loc_180076DBD
0x180076cd1  cmp     r9d, 13h
0x180076cd5  jz      loc_180076D6C
0x180076cdb  cmp     r9d, 15h
0x180076cdf  jz      short loc_180076CFB
0x180076ce1  mov     r8d, [r13+8]
0x180076ce5  lea     rdx, aUnexpectedInte; "Unexpected internal property type! [%d "...
0x180076cec  mov     ecx, 1
0x180076cf1  call    UnattendLogW
0x180076cf6  jmp     loc_180076EA0
0x180076cfb  mov     rbx, [r15]
0x180076cfe  mov     rax, [rbx]
0x180076d01  mov     rdi, [rax+48h]
0x180076d05  mov     rcx, [rbp+var_60]
0x180076d09  mov     [rbp+var_60], rsi
0x180076d0d  test    rcx, rcx
0x180076d10  jz      short loc_180076D1F
0x180076d12  mov     rax, [rcx]
0x180076d15  mov     rax, [rax+10h]
0x180076d19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076d1e  nop
0x180076d1f  mov     rax, qword ptr [rbp+pvarg+8]
0x180076d23  xorps   xmm1, xmm1
0x180076d26  test    rax, rax
0x180076d29  js      short loc_180076D32
0x180076d2b  cvtsi2sd xmm1, rax
0x180076d30  jmp     short loc_180076D47
0x180076d32  mov     rdx, rax
0x180076d35  shr     rdx, 1
0x180076d38  and     eax, 1
0x180076d3b  or      rdx, rax
0x180076d3e  cvtsi2sd xmm1, rdx
0x180076d43  addsd   xmm1, xmm1
0x180076d47  lea     r8, [rbp+var_60]
0x180076d4b  mov     rcx, rbx
0x180076d4e  mov     rax, rdi
0x180076d51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076d56  mov     rcx, [rbp+38h]
0x180076d5a  test    eax, eax
0x180076d5c  jns     loc_180076EA0
0x180076d62  mov     edx, 485h
0x180076d67  jmp     loc_180076E04
0x180076d6c  mov     rbx, [r15]
0x180076d6f  mov     rax, [rbx]
0x180076d72  mov     rdi, [rax+48h]
0x180076d76  mov     rcx, [rbp+var_60]
0x180076d7a  mov     [rbp+var_60], rsi
0x180076d7e  test    rcx, rcx
0x180076d81  jz      short loc_180076D90
0x180076d83  mov     rdx, [rcx]
0x180076d86  mov     rax, [rdx+10h]
0x180076d8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076d8f  nop
0x180076d90  mov     edx, dword ptr [rbp+pvarg+8]
0x180076d93  xorps   xmm1, xmm1
0x180076d96  cvtsi2sd xmm1, rdx
0x180076d9b  lea     r8, [rbp+var_60]
0x180076d9f  mov     rcx, rbx
0x180076da2  mov     rax, rdi
0x180076da5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076daa  mov     rcx, [rbp+38h]
0x180076dae  test    eax, eax
0x180076db0  jns     loc_180076EA0
0x180076db6  mov     edx, 48Ah
0x180076dbb  jmp     short loc_180076E04
0x180076dbd  mov     rbx, [r15]
0x180076dc0  mov     rax, [rbx]
0x180076dc3  mov     rdi, [rax+40h]
0x180076dc7  mov     rcx, [rbp+var_60]
0x180076dcb  mov     [rbp+var_60], rsi
0x180076dcf  test    rcx, rcx
0x180076dd2  jz      short loc_180076DE1
0x180076dd4  mov     rdx, [rcx]
0x180076dd7  mov     rax, [rdx+10h]
0x180076ddb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076de0  nop
0x180076de1  lea     r8, [rbp+var_60]
0x180076de5  mov     dl, byte ptr [rbp+pvarg+8]
0x180076de8  mov     rcx, rbx
0x180076deb  mov     rax, rdi
0x180076dee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076df3  mov     rcx, [rbp+38h]; this
0x180076df7  test    eax, eax
0x180076df9  jns     loc_180076EA0
0x180076dff  mov     edx, 479h; void *
0x180076e04  mov     r9d, eax; char *
0x180076e07  mov     r8, r14; unsigned int
0x180076e0a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180076e0f  jmp     loc_180076EA0
0x180076e14  mov     [rbp+string], rsi
0x180076e18  xor     edx, edx
0x180076e1a  lea     rcx, [rbp+string]
0x180076e1e  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x180076e23  mov     rcx, qword ptr [rbp+pvarg+8]; pbstr
0x180076e27  call    cs:__imp_SysStringLen
0x180076e2d  lea     r8, [rbp+string]; string
0x180076e31  mov     edx, eax; length
0x180076e33  mov     rcx, qword ptr [rbp+pvarg+8]; sourceString
0x180076e37  call    cs:__imp_WindowsCreateString
0x180076e3d  mov     ebx, eax
0x180076e3f  test    eax, eax
0x180076e41  js      loc_180076F2C
0x180076e47  mov     rbx, [r15]
0x180076e4a  mov     rax, [rbx]
0x180076e4d  mov     rdi, [rax+50h]
0x180076e51  mov     rcx, [rbp+var_60]
0x180076e55  mov     [rbp+var_60], rsi
0x180076e59  test    rcx, rcx
0x180076e5c  jz      short loc_180076E6B
0x180076e5e  mov     rdx, [rcx]
0x180076e61  mov     rax, [rdx+10h]
0x180076e65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076e6a  nop
0x180076e6b  lea     r8, [rbp+var_60]
0x180076e6f  mov     rdx, [rbp+string]
0x180076e73  mov     rcx, rbx
0x180076e76  mov     rax, rdi
0x180076e79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076e7e  mov     rcx, [rbp+38h]; this
0x180076e82  test    eax, eax
0x180076e84  jns     short loc_180076E97
0x180076e86  mov     r9d, eax; char *
0x180076e89  mov     r8, r14; unsigned int
0x180076e8c  mov     edx, 480h; void *
0x180076e91  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180076e96  nop
0x180076e97  lea     rcx, [rbp+string]; this
0x180076e9b  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180076ea0  mov     rbx, [rbp+var_60]
0x180076ea4  test    rbx, rbx
0x180076ea7  jz      short loc_180076EEE
0x180076ea9  mov     rsi, [r12]
0x180076ead  mov     rax, [rsi]
0x180076eb0  mov     rdi, [rax+38h]
0x180076eb4  mov     rdx, r13
0x180076eb7  lea     rcx, [rbp+var_28]
0x180076ebb  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180076ec0  nop
0x180076ec1  mov     r8, rbx
0x180076ec4  mov     rdx, [rax+18h]
0x180076ec8  mov     rcx, rsi
0x180076ecb  mov     rax, rdi
0x180076ece  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076ed3  mov     rcx, [rbp+38h]; this
0x180076ed7  xor     esi, esi
0x180076ed9  test    eax, eax
0x180076edb  jns     short loc_180076EEE
0x180076edd  mov     r9d, eax; char *
0x180076ee0  mov     r8, r14; unsigned int
0x180076ee3  mov     edx, 496h; void *
0x180076ee8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180076eed  nop
0x180076eee  lea     rcx, [rbp+var_60]
0x180076ef2  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x180076ef7  nop
0x180076ef8  lea     rcx, [rbp+pvarg]; pvarg
0x180076efc  call    cs:__imp_VariantClear
0x180076f02  add     r13, 10h
0x180076f06  lea     rax, ?reasons@?1??ExpeditedUpdateReasons@ExpeditedUpdateTelemetryHelper@@YAQEAGW4OobeExpeditedUpdateStatus@CloudExperienceHostAPI@@@Z@4QBQEAGB; ushort * const near * const `ExpeditedUpdateTelemetryHelper::ExpeditedUpdateReasons(CloudExperienceHostAPI::OobeExpeditedUpdateStatus)'::`2'::reasons
0x180076f0d  cmp     r13, rax
0x180076f10  jnz     loc_180076C6A
0x180076f16  lea     rcx, [rbp+var_50]
0x180076f1a  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x180076f1f  nop
0x180076f20  mov     rcx, r15
0x180076f23  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x180076f28  xor     eax, eax
0x180076f2a  jmp     short loc_180076F74
0x180076f2c  mov     rcx, [rbp+38h]; this
0x180076f30  mov     r9d, ebx; char *
0x180076f33  mov     r8, r14; unsigned int
0x180076f36  mov     edx, 47Fh; void *
0x180076f3b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076f40  nop
0x180076f41  lea     rcx, [rbp+string]; this
0x180076f45  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180076f4a  nop
0x180076f4b  lea     rcx, [rbp+var_60]
0x180076f4f  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x180076f54  nop
0x180076f55  lea     rcx, [rbp+pvarg]; pvarg
0x180076f59  call    cs:__imp_VariantClear
0x180076f5f  nop
0x180076f60  lea     rcx, [rbp+var_50]
0x180076f64  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x180076f69  nop
0x180076f6a  mov     rcx, r15
0x180076f6d  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x180076f72  mov     eax, ebx
0x180076f74  mov     rcx, [rbp+var_8]
0x180076f78  xor     rcx, rsp; StackCookie
0x180076f7b  call    __security_check_cookie
0x180076f80  mov     rbx, [rsp+80h+arg_0]
0x180076f88  add     rsp, 80h
0x180076f8f  pop     r15
0x180076f91  pop     r14
0x180076f93  pop     r13
0x180076f95  pop     r12
0x180076f97  pop     rdi
0x180076f98  pop     rsi
0x180076f99  pop     rbp
0x180076f9a  retn
```
