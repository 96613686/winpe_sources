# ChangeTracingStatus(ushort const *,bool)

- ea: `0x180003ec8`
- end: `0x18000416c`
- name: `?ChangeTracingStatus@@YAJPEBG_N@Z`
- size: `676`
- prototype: `__int64 __fastcall(const unsigned __int16 *, char)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180006930`
- `0x180006950`

## callees

- `0x1800017e0`
- `0x180003490`
- `0x180003714`
- `0x180003b10`
- `0x180003b68`
- `0x180003ec8`
- `0x180004f58`
- `0x180005a14`
- `0x180007350`
- `0x180007368`
- `0x180026010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180003f7a`
- `OLEAUT32!__imp_SysAllocString` at `0x18000401b`
- `OLEAUT32!__imp_SysAllocString` at `0x180003f7a`
- `OLEAUT32!__imp_SysAllocString` at `0x18000401b`
- `OLEAUT32!__imp_VariantInit` at `0x180003f55`
- `OLEAUT32!__imp_VariantInit` at `0x180003f55`
- `OLEAUT32!__imp_VariantClear` at `0x18000406c`
- `OLEAUT32!__imp_VariantClear` at `0x180004141`
- `OLEAUT32!__imp_VariantClear` at `0x18000406c`
- `OLEAUT32!__imp_VariantClear` at `0x180004141`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003f1b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003f1b`

## string_xrefs

- `0x180003f2e`: `onecoreuap\admin\enterprisemgmt\enterprisediagnosticsetw\dll\dmautologging.cpp`
- `0x180004042`: `onecoreuap\admin\enterprisemgmt\enterprisediagnosticsetw\dll\dmautologging.cpp`
- `0x1800040b7`: `onecoreuap\admin\enterprisemgmt\enterprisediagnosticsetw\dll\dmautologging.cpp`

## pseudocode

```c
__int64 __fastcall ChangeTracingStatus(const unsigned __int16 *a1, char a2)
{
  HRESULT v4; // eax
  unsigned int v5; // ebx
  const OLECHAR *v6; // rcx
  const OLECHAR *v7; // rcx
  BSTR v8; // rax
  __int64 v9; // rbx
  LPVOID v10; // rsi
  __int64 (__fastcall *v11)(LPVOID, __int64, __int64 *); // rdi
  int v12; // eax
  __int64 v13; // rdx
  int ppv; // [rsp+20h] [rbp-69h]
  __int64 v16; // [rsp+30h] [rbp-59h] BYREF
  __int64 v17; // [rsp+38h] [rbp-51h] BYREF
  LPVOID v18; // [rsp+40h] [rbp-49h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-41h] BYREF
  VARIANTARG *p_pvarg; // [rsp+60h] [rbp-29h]
  char v21; // [rsp+68h] [rbp-21h]
  VARIANTARG v22; // [rsp+70h] [rbp-19h] BYREF
  OLECHAR *psz[4]; // [rsp+90h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v18 = 0;
  Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(&v18);
  v4 = CoCreateInstance(
         &GUID_66d0db14_5638_475f_a386_629522d8c461,
         0,
         1u,
         &GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0,
         &v18);
  v5 = v4;
  if ( v4 >= 0 )
  {
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    p_pvarg = &pvarg;
    v21 = 1;
    v6 = L"START";
    if ( !a2 )
      v6 = L"STOP";
    pvarg.llVal = (LONGLONG)SysAllocString(v6);
    pvarg.vt = 8;
    std::wstring::wstring(psz, L"./Vendor/MSFT/DiagnosticLog/EtwLog/Collectors");
    std::_WChar_traits<unsigned short>::length(L"/");
    std::wstring::_Append<unsigned short>(psz);
    std::_WChar_traits<unsigned short>::length(a1);
    std::wstring::_Append<unsigned short>(psz);
    std::_WChar_traits<unsigned short>::length(L"/");
    std::wstring::_Append<unsigned short>(psz);
    std::_WChar_traits<unsigned short>::length(L"TraceControl");
    std::wstring::_Append<unsigned short>(psz);
    v17 = 0;
    v7 = (const OLECHAR *)psz;
    if ( psz[3] > (OLECHAR *)7 )
      v7 = psz[0];
    v8 = SysAllocString(v7);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v17,
      v8);
    v9 = v17;
    if ( v17 )
    {
      v16 = 0;
      v10 = v18;
      v11 = *(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)v18 + 80LL);
      Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(&v16);
      v12 = v11(v10, v9, &v16);
      v5 = v12;
      if ( v12 >= 0 )
      {
        v22 = pvarg;
        v12 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v16 + 88LL))(v16, &v22);
        v5 = v12;
        if ( v12 >= 0 )
        {
          v12 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)v18 + 24LL))(v18);
          v5 = v12;
          if ( v12 >= 0 )
          {
            Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(&v16);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v17);
            std::wstring::~wstring(psz);
            VariantClear(&pvarg);
            v5 = 0;
            goto LABEL_18;
          }
          v13 = 101;
        }
        else
        {
          v13 = 100;
        }
      }
      else
      {
        v13 = 99;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisediagnosticsetw\\dll\\dmautologging.cpp",
        (const char *)(unsigned int)v12,
        ppv);
      Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(&v16);
    }
    else
    {
      v5 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x60,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisediagnosticsetw\\dll\\dmautologging.cpp",
        (const char *)0x8007000ELL,
        ppv);
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v17);
    std::wstring::~wstring(psz);
    VariantClear(&pvarg);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4B,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisediagnosticsetw\\dll\\dmautologging.cpp",
      (const char *)(unsigned int)v4,
      ppv);
  }
LABEL_18:
  Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(&v18);
  return v5;
}

```

## disassembly

```asm
0x180003ec8  push    rbp
0x180003eca  push    rbx
0x180003ecb  push    rsi
0x180003ecc  push    rdi
0x180003ecd  lea     rbp, [rsp-3Fh]
0x180003ed2  sub     rsp, 0C8h
0x180003ed9  mov     rax, cs:__security_cookie
0x180003ee0  xor     rax, rsp
0x180003ee3  mov     [rbp+57h+var_30], rax
0x180003ee7  mov     dil, dl
0x180003eea  mov     rsi, rcx
0x180003eed  mov     [rbp+57h+var_A0], 0
0x180003ef5  lea     rcx, [rbp+57h+var_A0]
0x180003ef9  call    ?InternalRelease@?$ComPtr@UIConfigNode@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(void)
0x180003efe  lea     rax, [rbp+57h+var_A0]
0x180003f02  mov     qword ptr [rsp+0E0h+ppv], rax; int
0x180003f07  lea     r9, _GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0; riid
0x180003f0e  xor     edx, edx; pUnkOuter
0x180003f10  lea     r8d, [rdx+1]; dwClsContext
0x180003f14  lea     rcx, _GUID_66d0db14_5638_475f_a386_629522d8c461; rclsid
0x180003f1b  call    cs:__imp_CoCreateInstance
0x180003f21  mov     ebx, eax
0x180003f23  test    eax, eax
0x180003f25  jns     short loc_180003F44
0x180003f27  mov     rcx, [rbp+5Fh]; this
0x180003f2b  mov     r9d, eax; char *
0x180003f2e  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180003f35  mov     edx, 4Bh ; 'K'; void *
0x180003f3a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003f3f  jmp     loc_180004149
0x180003f44  xorps   xmm0, xmm0
0x180003f47  xor     eax, eax
0x180003f49  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180003f4d  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180003f51  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180003f55  call    cs:__imp_VariantInit
0x180003f5b  lea     rax, [rbp+57h+pvarg]
0x180003f5f  mov     [rbp+57h+var_80], rax
0x180003f63  mov     [rbp+57h+var_78], 1
0x180003f67  test    dil, dil
0x180003f6a  lea     rcx, aStart; "START"
0x180003f71  jnz     short loc_180003F7A
0x180003f73  lea     rcx, psz; "STOP"
0x180003f7a  call    cs:__imp_SysAllocString
0x180003f80  mov     qword ptr [rbp+57h+pvarg+8], rax
0x180003f84  mov     eax, 8
0x180003f89  mov     word ptr [rbp+57h+pvarg], ax
0x180003f8d  lea     rdx, aVendorMsftDiag; "./Vendor/MSFT/DiagnosticLog/EtwLog/Coll"...
0x180003f94  lea     rcx, [rbp+57h+psz]
0x180003f98  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180003f9d  nop
0x180003f9e  lea     rbx, asc_18002992C; "/"
0x180003fa5  mov     rcx, rbx
0x180003fa8  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180003fad  mov     r8, rax
0x180003fb0  mov     rdx, rbx
0x180003fb3  lea     rcx, [rbp+57h+psz]; Src
0x180003fb7  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180003fbc  mov     rcx, rsi
0x180003fbf  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180003fc4  mov     r8, rax
0x180003fc7  mov     rdx, rsi
0x180003fca  lea     rcx, [rbp+57h+psz]; Src
0x180003fce  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180003fd3  mov     rcx, rbx
0x180003fd6  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180003fdb  mov     r8, rax
0x180003fde  mov     rdx, rbx
0x180003fe1  lea     rcx, [rbp+57h+psz]; Src
0x180003fe5  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180003fea  lea     rcx, aTracecontrol; "TraceControl"
0x180003ff1  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180003ff6  mov     r8, rax
0x180003ff9  mov     rdx, rcx
0x180003ffc  lea     rcx, [rbp+57h+psz]; Src
0x180004000  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180004005  mov     [rbp+57h+var_A8], 0
0x18000400d  lea     rcx, [rbp+57h+psz]
0x180004011  cmp     [rbp+57h+var_38], 7
0x180004016  cmova   rcx, [rbp+57h+psz]; psz
0x18000401b  call    cs:__imp_SysAllocString
0x180004021  mov     rdx, rax
0x180004024  lea     rcx, [rbp+57h+var_A8]
0x180004028  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18000402d  mov     rbx, [rbp+57h+var_A8]
0x180004031  test    rbx, rbx
0x180004034  jnz     short loc_180004077
0x180004036  mov     rcx, [rbp+5Fh]; this
0x18000403a  mov     ebx, 8007000Eh
0x18000403f  mov     r9d, ebx; char *
0x180004042  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180004049  mov     edx, 60h ; '`'; void *
0x18000404e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004053  nop
0x180004054  lea     rcx, [rbp+57h+var_A8]
0x180004058  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000405d  nop
0x18000405e  lea     rcx, [rbp+57h+psz]
0x180004062  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180004067  nop
0x180004068  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18000406c  call    cs:__imp_VariantClear
0x180004072  jmp     loc_180004149
0x180004077  mov     [rbp+57h+var_B0], 0
0x18000407f  mov     rsi, [rbp+57h+var_A0]
0x180004083  mov     rax, [rsi]
0x180004086  mov     rdi, [rax+50h]
0x18000408a  lea     rcx, [rbp+57h+var_B0]
0x18000408e  call    ?InternalRelease@?$ComPtr@UIConfigNode@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(void)
0x180004093  lea     r8, [rbp+57h+var_B0]
0x180004097  mov     rdx, rbx
0x18000409a  mov     rcx, rsi
0x18000409d  mov     rax, rdi
0x1800040a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040a5  mov     ebx, eax
0x1800040a7  test    eax, eax
0x1800040a9  jns     short loc_1800040CF
0x1800040ab  mov     edx, 63h ; 'c'; void *
0x1800040b0  mov     rcx, [rbp+5Fh]; this
0x1800040b4  mov     r9d, eax; char *
0x1800040b7  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1800040be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800040c3  nop
0x1800040c4  lea     rcx, [rbp+57h+var_B0]
0x1800040c8  call    ?InternalRelease@?$ComPtr@UIConfigNode@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(void)
0x1800040cd  jmp     short loc_180004054
0x1800040cf  mov     rcx, [rbp+57h+var_B0]
0x1800040d3  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x1800040d7  movaps  [rbp+57h+var_70], xmm0
0x1800040db  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x1800040e0  movsd   [rbp+57h+var_60], xmm1
0x1800040e5  mov     rax, [rcx]
0x1800040e8  lea     rdx, [rbp+57h+var_70]
0x1800040ec  mov     rax, [rax+58h]
0x1800040f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040f5  mov     ebx, eax
0x1800040f7  test    eax, eax
0x1800040f9  jns     short loc_180004102
0x1800040fb  mov     edx, 64h ; 'd'
0x180004100  jmp     short loc_1800040B0
0x180004102  mov     rcx, [rbp+57h+var_A0]
0x180004106  mov     rax, [rcx]
0x180004109  mov     rax, [rax+18h]
0x18000410d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004112  mov     ebx, eax
0x180004114  test    eax, eax
0x180004116  jns     short loc_18000411F
0x180004118  mov     edx, 65h ; 'e'
0x18000411d  jmp     short loc_1800040B0
0x18000411f  lea     rcx, [rbp+57h+var_B0]
0x180004123  call    ?InternalRelease@?$ComPtr@UIConfigNode@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(void)
0x180004128  nop
0x180004129  lea     rcx, [rbp+57h+var_A8]
0x18000412d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180004132  nop
0x180004133  lea     rcx, [rbp+57h+psz]
0x180004137  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000413c  nop
0x18000413d  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180004141  call    cs:__imp_VariantClear
0x180004147  xor     ebx, ebx
0x180004149  lea     rcx, [rbp+57h+var_A0]
0x18000414d  call    ?InternalRelease@?$ComPtr@UIConfigNode@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(void)
0x180004152  mov     eax, ebx
0x180004154  mov     rcx, [rbp+57h+var_30]
0x180004158  xor     rcx, rsp; StackCookie
0x18000415b  call    __security_check_cookie
0x180004160  add     rsp, 0C8h
0x180004167  pop     rdi
0x180004168  pop     rsi
0x180004169  pop     rbx
0x18000416a  pop     rbp
0x18000416b  retn
```
