# ChangeTracingStatus(ushort const *,bool)

- ea: `0x180003eec`
- end: `0x1800041b8`
- name: `?ChangeTracingStatus@@YAJPEBG_N@Z`
- size: `716`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180006bb0`
- `0x180006bd0`

## callees

- `0x180001800`
- `0x1800034e4`
- `0x180003768`
- `0x180003b14`
- `0x180003b70`
- `0x180003eec`
- `0x1800050e0`
- `0x180005c14`
- `0x180007618`
- `0x180007630`
- `0x180027010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180003faa`
- `OLEAUT32!__imp_SysAllocString` at `0x180004051`
- `OLEAUT32!__imp_SysAllocString` at `0x180003faa`
- `OLEAUT32!__imp_SysAllocString` at `0x180004051`
- `OLEAUT32!__imp_VariantInit` at `0x180003f7f`
- `OLEAUT32!__imp_VariantInit` at `0x180003f7f`
- `OLEAUT32!__imp_VariantClear` at `0x1800040a8`
- `OLEAUT32!__imp_VariantClear` at `0x180004186`
- `OLEAUT32!__imp_VariantClear` at `0x1800040a8`
- `OLEAUT32!__imp_VariantClear` at `0x180004186`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003f3f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003f3f`

## string_xrefs

- `0x180003f58`: `onecoreuap\admin\enterprisemgmt\enterprisediagnosticsetw\dll\dmautologging.cpp`
- `0x18000407e`: `onecoreuap\admin\enterprisemgmt\enterprisediagnosticsetw\dll\dmautologging.cpp`
- `0x1800040f9`: `onecoreuap\admin\enterprisemgmt\enterprisediagnosticsetw\dll\dmautologging.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
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
0x180003eec  push    rbp
0x180003eee  push    rbx
0x180003eef  push    rsi
0x180003ef0  push    rdi
0x180003ef1  lea     rbp, [rsp-3Fh]
0x180003ef6  sub     rsp, 0C8h
0x180003efd  mov     rax, cs:__security_cookie
0x180003f04  xor     rax, rsp
0x180003f07  mov     [rbp+57h+var_30], rax
0x180003f0b  mov     dil, dl
0x180003f0e  mov     rsi, rcx
0x180003f11  mov     [rbp+57h+var_A0], 0
0x180003f19  lea     rcx, [rbp+57h+var_A0]
0x180003f1d  call    ?InternalRelease@?$ComPtr@UIConfigNode@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(void)
0x180003f22  lea     rax, [rbp+57h+var_A0]
0x180003f26  mov     qword ptr [rsp+0E0h+ppv], rax; int
0x180003f2b  lea     r9, _GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0; riid
0x180003f32  xor     edx, edx; pUnkOuter
0x180003f34  lea     r8d, [rdx+1]; dwClsContext
0x180003f38  lea     rcx, _GUID_66d0db14_5638_475f_a386_629522d8c461; rclsid
0x180003f3f  call    cs:__imp_CoCreateInstance
0x180003f46  nop     dword ptr [rax+rax+00h]
0x180003f4b  mov     ebx, eax
0x180003f4d  test    eax, eax
0x180003f4f  jns     short loc_180003F6E
0x180003f51  mov     rcx, [rbp+5Fh]; this
0x180003f55  mov     r9d, eax; char *
0x180003f58  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180003f5f  mov     edx, 4Bh ; 'K'; void *
0x180003f64  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003f69  jmp     loc_180004194
0x180003f6e  xorps   xmm0, xmm0
0x180003f71  xor     eax, eax
0x180003f73  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180003f77  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180003f7b  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180003f7f  call    cs:__imp_VariantInit
0x180003f86  nop     dword ptr [rax+rax+00h]
0x180003f8b  lea     rax, [rbp+57h+pvarg]
0x180003f8f  mov     [rbp+57h+var_80], rax
0x180003f93  mov     [rbp+57h+var_78], 1
0x180003f97  test    dil, dil
0x180003f9a  lea     rcx, aStart; "START"
0x180003fa1  jnz     short loc_180003FAA
0x180003fa3  lea     rcx, psz; "STOP"
0x180003faa  call    cs:__imp_SysAllocString
0x180003fb1  nop     dword ptr [rax+rax+00h]
0x180003fb6  mov     qword ptr [rbp+57h+pvarg+8], rax
0x180003fba  mov     eax, 8
0x180003fbf  mov     word ptr [rbp+57h+pvarg], ax
0x180003fc3  lea     rdx, aVendorMsftDiag; "./Vendor/MSFT/DiagnosticLog/EtwLog/Coll"...
0x180003fca  lea     rcx, [rbp+57h+psz]
0x180003fce  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180003fd3  nop
0x180003fd4  lea     rbx, asc_18002A92C; "/"
0x180003fdb  mov     rcx, rbx
0x180003fde  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180003fe3  mov     r8, rax
0x180003fe6  mov     rdx, rbx
0x180003fe9  lea     rcx, [rbp+57h+psz]; Src
0x180003fed  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180003ff2  mov     rcx, rsi
0x180003ff5  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180003ffa  mov     r8, rax
0x180003ffd  mov     rdx, rsi
0x180004000  lea     rcx, [rbp+57h+psz]; Src
0x180004004  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180004009  mov     rcx, rbx
0x18000400c  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180004011  mov     r8, rax
0x180004014  mov     rdx, rbx
0x180004017  lea     rcx, [rbp+57h+psz]; Src
0x18000401b  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180004020  lea     rcx, aTracecontrol; "TraceControl"
0x180004027  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18000402c  mov     r8, rax
0x18000402f  mov     rdx, rcx
0x180004032  lea     rcx, [rbp+57h+psz]; Src
0x180004036  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18000403b  mov     [rbp+57h+var_A8], 0
0x180004043  lea     rcx, [rbp+57h+psz]
0x180004047  cmp     [rbp+57h+var_38], 7
0x18000404c  cmova   rcx, [rbp+57h+psz]; psz
0x180004051  call    cs:__imp_SysAllocString
0x180004058  nop     dword ptr [rax+rax+00h]
0x18000405d  mov     rdx, rax
0x180004060  lea     rcx, [rbp+57h+var_A8]
0x180004064  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180004069  mov     rbx, [rbp+57h+var_A8]
0x18000406d  test    rbx, rbx
0x180004070  jnz     short loc_1800040B9
0x180004072  mov     rcx, [rbp+5Fh]; this
0x180004076  mov     ebx, 8007000Eh
0x18000407b  mov     r9d, ebx; char *
0x18000407e  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180004085  mov     edx, 60h ; '`'; void *
0x18000408a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000408f  nop
0x180004090  lea     rcx, [rbp+57h+var_A8]
0x180004094  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180004099  nop
0x18000409a  lea     rcx, [rbp+57h+psz]
0x18000409e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800040a3  nop
0x1800040a4  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800040a8  call    cs:__imp_VariantClear
0x1800040af  nop     dword ptr [rax+rax+00h]
0x1800040b4  jmp     loc_180004194
0x1800040b9  mov     [rbp+57h+var_B0], 0
0x1800040c1  mov     rsi, [rbp+57h+var_A0]
0x1800040c5  mov     rax, [rsi]
0x1800040c8  mov     rdi, [rax+50h]
0x1800040cc  lea     rcx, [rbp+57h+var_B0]
0x1800040d0  call    ?InternalRelease@?$ComPtr@UIConfigNode@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(void)
0x1800040d5  lea     r8, [rbp+57h+var_B0]
0x1800040d9  mov     rdx, rbx
0x1800040dc  mov     rcx, rsi
0x1800040df  mov     rax, rdi
0x1800040e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040e7  mov     ebx, eax
0x1800040e9  test    eax, eax
0x1800040eb  jns     short loc_180004114
0x1800040ed  mov     edx, 63h ; 'c'; void *
0x1800040f2  mov     rcx, [rbp+5Fh]; this
0x1800040f6  mov     r9d, eax; char *
0x1800040f9  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180004100  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004105  nop
0x180004106  lea     rcx, [rbp+57h+var_B0]
0x18000410a  call    ?InternalRelease@?$ComPtr@UIConfigNode@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(void)
0x18000410f  jmp     loc_180004090
0x180004114  mov     rcx, [rbp+57h+var_B0]
0x180004118  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x18000411c  movaps  [rbp+57h+var_70], xmm0
0x180004120  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x180004125  movsd   [rbp+57h+var_60], xmm1
0x18000412a  mov     rax, [rcx]
0x18000412d  lea     rdx, [rbp+57h+var_70]
0x180004131  mov     rax, [rax+58h]
0x180004135  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000413a  mov     ebx, eax
0x18000413c  test    eax, eax
0x18000413e  jns     short loc_180004147
0x180004140  mov     edx, 64h ; 'd'
0x180004145  jmp     short loc_1800040F2
0x180004147  mov     rcx, [rbp+57h+var_A0]
0x18000414b  mov     rax, [rcx]
0x18000414e  mov     rax, [rax+18h]
0x180004152  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004157  mov     ebx, eax
0x180004159  test    eax, eax
0x18000415b  jns     short loc_180004164
0x18000415d  mov     edx, 65h ; 'e'
0x180004162  jmp     short loc_1800040F2
0x180004164  lea     rcx, [rbp+57h+var_B0]
0x180004168  call    ?InternalRelease@?$ComPtr@UIConfigNode@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(void)
0x18000416d  nop
0x18000416e  lea     rcx, [rbp+57h+var_A8]
0x180004172  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180004177  nop
0x180004178  lea     rcx, [rbp+57h+psz]
0x18000417c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180004181  nop
0x180004182  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180004186  call    cs:__imp_VariantClear
0x18000418d  nop     dword ptr [rax+rax+00h]
0x180004192  xor     ebx, ebx
0x180004194  lea     rcx, [rbp+57h+var_A0]
0x180004198  call    ?InternalRelease@?$ComPtr@UIConfigNode@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(void)
0x18000419d  mov     eax, ebx
0x18000419f  mov     rcx, [rbp+57h+var_30]
0x1800041a3  xor     rcx, rsp; StackCookie
0x1800041a6  call    __security_check_cookie
0x1800041ab  add     rsp, 0C8h
0x1800041b2  pop     rdi
0x1800041b3  pop     rsi
0x1800041b4  pop     rbx
0x1800041b5  pop     rbp
0x1800041b6  retn
```
