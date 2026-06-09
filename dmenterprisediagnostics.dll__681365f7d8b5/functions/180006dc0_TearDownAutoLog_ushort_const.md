# TearDownAutoLog(ushort const *)

- ea: `0x180006dc0`
- end: `0x1800070b8`
- name: `?TearDownAutoLog@@YAJPEBG@Z`
- size: `760`
- prototype: `__int64 __fastcall(OLECHAR *psz)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180003b70`
- `0x1800050e0`
- `0x180005c14`
- `0x180006dc0`
- `0x180007630`
- `0x180027010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180006e57`
- `OLEAUT32!__imp_SysAllocString` at `0x180006ec3`
- `OLEAUT32!__imp_SysAllocString` at `0x180006e57`
- `OLEAUT32!__imp_SysAllocString` at `0x180006ec3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006e01`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006e01`

## string_xrefs

- `0x180006e1b`: `onecoreuap\admin\enterprisemgmt\enterprisediagnosticsetw\dll\dmautologging.cpp`
- `0x180006e87`: `onecoreuap\admin\enterprisemgmt\enterprisediagnosticsetw\dll\dmautologging.cpp`
- `0x180006ef3`: `onecoreuap\admin\enterprisemgmt\enterprisediagnosticsetw\dll\dmautologging.cpp`
- `0x180006f6c`: `onecoreuap\admin\enterprisemgmt\enterprisediagnosticsetw\dll\dmautologging.cpp`
- `0x180006fd2`: `onecoreuap\admin\enterprisemgmt\enterprisediagnosticsetw\dll\dmautologging.cpp`
- `0x180007035`: `onecoreuap\admin\enterprisemgmt\enterprisediagnosticsetw\dll\dmautologging.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall TearDownAutoLog(OLECHAR *psz)
{
  HRESULT v2; // eax
  unsigned int v3; // ebx
  __int64 result; // rax
  BSTR v5; // rax
  BSTR v6; // rax
  __int64 v7; // rbx
  __int64 (*v8)(void); // rsi
  int v9; // eax
  unsigned int v10; // edi
  unsigned int v11; // r8d
  const char *v12; // r9
  int v13; // eax
  unsigned int v14; // ebx
  int v15; // eax
  unsigned int v16; // ebx
  int ppv; // [rsp+20h] [rbp-38h]
  _QWORD v18[5]; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  LPVOID v20; // [rsp+68h] [rbp+10h] BYREF
  __int64 v21; // [rsp+70h] [rbp+18h] BYREF
  __int64 v22; // [rsp+78h] [rbp+20h] BYREF

  v20 = 0;
  Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(&v20);
  v2 = CoCreateInstance(
         &GUID_66d0db14_5638_475f_a386_629522d8c461,
         0,
         1u,
         &GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0,
         &v20);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v22 = 0;
    v21 = 0;
    v5 = SysAllocString(L"./Vendor/MSFT/DiagnosticLog/EtwLog/Collectors");
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v22,
      v5);
    if ( v22 )
    {
      v6 = SysAllocString(psz);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v21,
        v6);
      v7 = v21;
      if ( v21 )
      {
        v18[0] = 0;
        v8 = *(__int64 (**)(void))(*(_QWORD *)v20 + 80LL);
        Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(v18);
        try
        {
          v9 = v8();
          v10 = v9;
          if ( v9 >= 0 )
          {
            v13 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v18[0] + 72LL))(v18[0], v7);
            v14 = v13;
            if ( v13 >= 0 )
            {
              v15 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)v20 + 24LL))(v20);
              v16 = v15;
              if ( v15 >= 0 )
              {
                Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(v18);
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v21);
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v22);
                Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(&v20);
                result = 0;
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x185,
                  (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisediagnosticsetw\\dll\\dmautologging.cpp",
                  (const char *)(unsigned int)v15,
                  ppv);
                Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(v18);
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v21);
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v22);
                Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(&v20);
                result = v16;
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x184,
                (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisediagnosticsetw\\dll\\dmautologging.cpp",
                (const char *)(unsigned int)v13,
                ppv);
              Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(v18);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v21);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v22);
              Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(&v20);
              result = v14;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x183,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisediagnosticsetw\\dll\\dmautologging.cpp",
              (const char *)(unsigned int)v9,
              ppv);
            Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(v18);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v21);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v22);
            Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(&v20);
            result = v10;
          }
        }
        catch ( ... )
        {
          return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x188, v11, v12);
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x180,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisediagnosticsetw\\dll\\dmautologging.cpp",
          (const char *)0x8007000ELL,
          ppv);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v21);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v22);
        Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(&v20);
        return 2147942414LL;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x17D,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisediagnosticsetw\\dll\\dmautologging.cpp",
        (const char *)0x8007000ELL,
        ppv);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v21);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v22);
      Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(&v20);
      return 2147942414LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x177,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisediagnosticsetw\\dll\\dmautologging.cpp",
      (const char *)(unsigned int)v2,
      ppv);
    Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(&v20);
    return v3;
  }
  return result;
}

```

## disassembly

```asm
0x180006dc0  mov     [rsp+arg_0], rbx
0x180006dc5  push    rsi
0x180006dc6  push    rdi
0x180006dc7  push    r14
0x180006dc9  sub     rsp, 40h
0x180006dcd  mov     rsi, rcx
0x180006dd0  mov     [rsp+58h+arg_8], 0
0x180006dd9  lea     rcx, [rsp+58h+arg_8]
0x180006dde  call    ?InternalRelease@?$ComPtr@UIConfigNode@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(void)
0x180006de3  lea     rax, [rsp+58h+arg_8]
0x180006de8  mov     qword ptr [rsp+58h+ppv], rax; int
0x180006ded  lea     r9, _GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0; riid
0x180006df4  xor     edx, edx; pUnkOuter
0x180006df6  lea     r8d, [rdx+1]; dwClsContext
0x180006dfa  lea     rcx, _GUID_66d0db14_5638_475f_a386_629522d8c461; rclsid
0x180006e01  call    cs:__imp_CoCreateInstance
0x180006e08  nop     dword ptr [rax+rax+00h]
0x180006e0d  mov     ebx, eax
0x180006e0f  test    eax, eax
0x180006e11  jns     short loc_180006E3E
0x180006e13  mov     rcx, [rsp+58h]; this
0x180006e18  mov     r9d, eax; char *
0x180006e1b  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180006e22  mov     edx, 177h; void *
0x180006e27  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006e2c  nop
0x180006e2d  lea     rcx, [rsp+58h+arg_8]
0x180006e32  call    ?InternalRelease@?$ComPtr@UIConfigNode@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(void)
0x180006e37  mov     eax, ebx
0x180006e39  jmp     loc_1800070A9
0x180006e3e  mov     [rsp+58h+arg_18], 0
0x180006e47  mov     [rsp+58h+arg_10], 0
0x180006e50  lea     rcx, aVendorMsftDiag; "./Vendor/MSFT/DiagnosticLog/EtwLog/Coll"...
0x180006e57  call    cs:__imp_SysAllocString
0x180006e5e  nop     dword ptr [rax+rax+00h]
0x180006e63  mov     rdx, rax
0x180006e66  lea     rcx, [rsp+58h+arg_18]
0x180006e6b  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180006e70  mov     rdi, [rsp+58h+arg_18]
0x180006e75  test    rdi, rdi
0x180006e78  jnz     short loc_180006EC0
0x180006e7a  mov     rcx, [rsp+58h]; this
0x180006e7f  mov     ebx, 8007000Eh
0x180006e84  mov     r9d, ebx; char *
0x180006e87  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180006e8e  mov     edx, 17Dh; void *
0x180006e93  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006e98  nop
0x180006e99  lea     rcx, [rsp+58h+arg_10]
0x180006e9e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180006ea3  nop
0x180006ea4  lea     rcx, [rsp+58h+arg_18]
0x180006ea9  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180006eae  nop
0x180006eaf  lea     rcx, [rsp+58h+arg_8]
0x180006eb4  call    ?InternalRelease@?$ComPtr@UIConfigNode@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(void)
0x180006eb9  mov     eax, ebx
0x180006ebb  jmp     loc_1800070A9
0x180006ec0  mov     rcx, rsi; psz
0x180006ec3  call    cs:__imp_SysAllocString
0x180006eca  nop     dword ptr [rax+rax+00h]
0x180006ecf  mov     rdx, rax
0x180006ed2  lea     rcx, [rsp+58h+arg_10]
0x180006ed7  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180006edc  mov     rbx, [rsp+58h+arg_10]
0x180006ee1  test    rbx, rbx
0x180006ee4  jnz     short loc_180006F2C
0x180006ee6  mov     rcx, [rsp+58h]; this
0x180006eeb  mov     ebx, 8007000Eh
0x180006ef0  mov     r9d, ebx; char *
0x180006ef3  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180006efa  mov     edx, 180h; void *
0x180006eff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006f04  nop
0x180006f05  lea     rcx, [rsp+58h+arg_10]
0x180006f0a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180006f0f  nop
0x180006f10  lea     rcx, [rsp+58h+arg_18]
0x180006f15  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180006f1a  nop
0x180006f1b  lea     rcx, [rsp+58h+arg_8]
0x180006f20  call    ?InternalRelease@?$ComPtr@UIConfigNode@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(void)
0x180006f25  mov     eax, ebx
0x180006f27  jmp     loc_1800070A9
0x180006f2c  mov     [rsp+58h+var_28], 0
0x180006f35  mov     r14, [rsp+58h+arg_8]
0x180006f3a  mov     rax, [r14]
0x180006f3d  mov     rsi, [rax+50h]
0x180006f41  lea     rcx, [rsp+58h+var_28]
0x180006f46  call    ?InternalRelease@?$ComPtr@UIConfigNode@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(void)
0x180006f4b  lea     r8, [rsp+58h+var_28]
0x180006f50  mov     rdx, rdi
0x180006f53  mov     rcx, r14
0x180006f56  mov     rax, rsi
0x180006f59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f5e  mov     edi, eax
0x180006f60  test    eax, eax
0x180006f62  jns     short loc_180006FB0
0x180006f64  mov     rcx, [rsp+58h]; this
0x180006f69  mov     r9d, eax; char *
0x180006f6c  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180006f73  mov     edx, 183h; void *
0x180006f78  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006f7d  nop
0x180006f7e  lea     rcx, [rsp+58h+var_28]
0x180006f83  call    ?InternalRelease@?$ComPtr@UIConfigNode@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(void)
0x180006f88  nop
0x180006f89  lea     rcx, [rsp+58h+arg_10]
0x180006f8e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180006f93  nop
0x180006f94  lea     rcx, [rsp+58h+arg_18]
0x180006f99  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180006f9e  nop
0x180006f9f  lea     rcx, [rsp+58h+arg_8]
0x180006fa4  call    ?InternalRelease@?$ComPtr@UIConfigNode@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(void)
0x180006fa9  mov     eax, edi
0x180006fab  jmp     loc_1800070A9
0x180006fb0  mov     rcx, [rsp+58h+var_28]
0x180006fb5  mov     rax, [rcx]
0x180006fb8  mov     rdx, rbx
0x180006fbb  mov     rax, [rax+48h]
0x180006fbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fc4  mov     ebx, eax
0x180006fc6  test    eax, eax
0x180006fc8  jns     short loc_180007016
0x180006fca  mov     rcx, [rsp+58h]; this
0x180006fcf  mov     r9d, eax; char *
0x180006fd2  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180006fd9  mov     edx, 184h; void *
0x180006fde  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006fe3  nop
0x180006fe4  lea     rcx, [rsp+58h+var_28]
0x180006fe9  call    ?InternalRelease@?$ComPtr@UIConfigNode@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(void)
0x180006fee  nop
0x180006fef  lea     rcx, [rsp+58h+arg_10]
0x180006ff4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180006ff9  nop
0x180006ffa  lea     rcx, [rsp+58h+arg_18]
0x180006fff  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180007004  nop
0x180007005  lea     rcx, [rsp+58h+arg_8]
0x18000700a  call    ?InternalRelease@?$ComPtr@UIConfigNode@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(void)
0x18000700f  mov     eax, ebx
0x180007011  jmp     loc_1800070A9
0x180007016  mov     rcx, [rsp+58h+arg_8]
0x18000701b  mov     rax, [rcx]
0x18000701e  mov     rax, [rax+18h]
0x180007022  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007027  mov     ebx, eax
0x180007029  test    eax, eax
0x18000702b  jns     short loc_180007076
0x18000702d  mov     rcx, [rsp+58h]; this
0x180007032  mov     r9d, eax; char *
0x180007035  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x18000703c  mov     edx, 185h; void *
0x180007041  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007046  nop
0x180007047  lea     rcx, [rsp+58h+var_28]
0x18000704c  call    ?InternalRelease@?$ComPtr@UIConfigNode@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(void)
0x180007051  nop
0x180007052  lea     rcx, [rsp+58h+arg_10]
0x180007057  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000705c  nop
0x18000705d  lea     rcx, [rsp+58h+arg_18]
0x180007062  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180007067  nop
0x180007068  lea     rcx, [rsp+58h+arg_8]
0x18000706d  call    ?InternalRelease@?$ComPtr@UIConfigNode@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(void)
0x180007072  mov     eax, ebx
0x180007074  jmp     short loc_1800070A9
0x180007076  lea     rcx, [rsp+58h+var_28]
0x18000707b  call    ?InternalRelease@?$ComPtr@UIConfigNode@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(void)
0x180007080  nop
0x180007081  lea     rcx, [rsp+58h+arg_10]
0x180007086  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000708b  nop
0x18000708c  lea     rcx, [rsp+58h+arg_18]
0x180007091  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180007096  nop
0x180007097  lea     rcx, [rsp+58h+arg_8]
0x18000709c  call    ?InternalRelease@?$ComPtr@UIConfigNode@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(void)
0x1800070a1  xor     eax, eax
0x1800070a3  jmp     short loc_1800070A9
0x1800070a5  mov     eax, dword ptr [rsp+58h+arg_8]
0x1800070a9  mov     rbx, [rsp+58h+arg_0]
0x1800070ae  add     rsp, 40h
0x1800070b2  pop     r14
0x1800070b4  pop     rdi
0x1800070b5  pop     rsi
0x1800070b6  retn
```
