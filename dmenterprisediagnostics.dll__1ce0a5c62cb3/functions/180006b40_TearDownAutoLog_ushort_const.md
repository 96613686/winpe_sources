# TearDownAutoLog(ushort const *)

- ea: `0x180006b40`
- end: `0x180006e26`
- name: `?TearDownAutoLog@@YAJPEBG@Z`
- size: `742`
- prototype: `__int64 __fastcall(OLECHAR *psz)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180003b68`
- `0x180004f58`
- `0x180005a14`
- `0x180006b40`
- `0x180007368`
- `0x180026010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180006bd1`
- `OLEAUT32!__imp_SysAllocString` at `0x180006c37`
- `OLEAUT32!__imp_SysAllocString` at `0x180006bd1`
- `OLEAUT32!__imp_SysAllocString` at `0x180006c37`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006b81`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006b81`

## string_xrefs

- `0x180006b95`: `onecoreuap\admin\enterprisemgmt\enterprisediagnosticsetw\dll\dmautologging.cpp`
- `0x180006bfb`: `onecoreuap\admin\enterprisemgmt\enterprisediagnosticsetw\dll\dmautologging.cpp`
- `0x180006c61`: `onecoreuap\admin\enterprisemgmt\enterprisediagnosticsetw\dll\dmautologging.cpp`
- `0x180006cda`: `onecoreuap\admin\enterprisemgmt\enterprisediagnosticsetw\dll\dmautologging.cpp`
- `0x180006d40`: `onecoreuap\admin\enterprisemgmt\enterprisediagnosticsetw\dll\dmautologging.cpp`
- `0x180006da3`: `onecoreuap\admin\enterprisemgmt\enterprisediagnosticsetw\dll\dmautologging.cpp`

## pseudocode

```c
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
0x180006b40  mov     [rsp+arg_0], rbx
0x180006b45  push    rsi
0x180006b46  push    rdi
0x180006b47  push    r14
0x180006b49  sub     rsp, 40h
0x180006b4d  mov     rsi, rcx
0x180006b50  mov     [rsp+58h+arg_8], 0
0x180006b59  lea     rcx, [rsp+58h+arg_8]
0x180006b5e  call    ?InternalRelease@?$ComPtr@UIConfigNode@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(void)
0x180006b63  lea     rax, [rsp+58h+arg_8]
0x180006b68  mov     qword ptr [rsp+58h+ppv], rax; int
0x180006b6d  lea     r9, _GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0; riid
0x180006b74  xor     edx, edx; pUnkOuter
0x180006b76  lea     r8d, [rdx+1]; dwClsContext
0x180006b7a  lea     rcx, _GUID_66d0db14_5638_475f_a386_629522d8c461; rclsid
0x180006b81  call    cs:__imp_CoCreateInstance
0x180006b87  mov     ebx, eax
0x180006b89  test    eax, eax
0x180006b8b  jns     short loc_180006BB8
0x180006b8d  mov     rcx, [rsp+58h]; this
0x180006b92  mov     r9d, eax; char *
0x180006b95  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180006b9c  mov     edx, 177h; void *
0x180006ba1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006ba6  nop
0x180006ba7  lea     rcx, [rsp+58h+arg_8]
0x180006bac  call    ?InternalRelease@?$ComPtr@UIConfigNode@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(void)
0x180006bb1  mov     eax, ebx
0x180006bb3  jmp     loc_180006E17
0x180006bb8  mov     [rsp+58h+arg_18], 0
0x180006bc1  mov     [rsp+58h+arg_10], 0
0x180006bca  lea     rcx, aVendorMsftDiag; "./Vendor/MSFT/DiagnosticLog/EtwLog/Coll"...
0x180006bd1  call    cs:__imp_SysAllocString
0x180006bd7  mov     rdx, rax
0x180006bda  lea     rcx, [rsp+58h+arg_18]
0x180006bdf  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180006be4  mov     rdi, [rsp+58h+arg_18]
0x180006be9  test    rdi, rdi
0x180006bec  jnz     short loc_180006C34
0x180006bee  mov     rcx, [rsp+58h]; this
0x180006bf3  mov     ebx, 8007000Eh
0x180006bf8  mov     r9d, ebx; char *
0x180006bfb  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180006c02  mov     edx, 17Dh; void *
0x180006c07  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006c0c  nop
0x180006c0d  lea     rcx, [rsp+58h+arg_10]
0x180006c12  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180006c17  nop
0x180006c18  lea     rcx, [rsp+58h+arg_18]
0x180006c1d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180006c22  nop
0x180006c23  lea     rcx, [rsp+58h+arg_8]
0x180006c28  call    ?InternalRelease@?$ComPtr@UIConfigNode@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(void)
0x180006c2d  mov     eax, ebx
0x180006c2f  jmp     loc_180006E17
0x180006c34  mov     rcx, rsi; psz
0x180006c37  call    cs:__imp_SysAllocString
0x180006c3d  mov     rdx, rax
0x180006c40  lea     rcx, [rsp+58h+arg_10]
0x180006c45  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180006c4a  mov     rbx, [rsp+58h+arg_10]
0x180006c4f  test    rbx, rbx
0x180006c52  jnz     short loc_180006C9A
0x180006c54  mov     rcx, [rsp+58h]; this
0x180006c59  mov     ebx, 8007000Eh
0x180006c5e  mov     r9d, ebx; char *
0x180006c61  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180006c68  mov     edx, 180h; void *
0x180006c6d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006c72  nop
0x180006c73  lea     rcx, [rsp+58h+arg_10]
0x180006c78  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180006c7d  nop
0x180006c7e  lea     rcx, [rsp+58h+arg_18]
0x180006c83  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180006c88  nop
0x180006c89  lea     rcx, [rsp+58h+arg_8]
0x180006c8e  call    ?InternalRelease@?$ComPtr@UIConfigNode@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(void)
0x180006c93  mov     eax, ebx
0x180006c95  jmp     loc_180006E17
0x180006c9a  mov     [rsp+58h+var_28], 0
0x180006ca3  mov     r14, [rsp+58h+arg_8]
0x180006ca8  mov     rax, [r14]
0x180006cab  mov     rsi, [rax+50h]
0x180006caf  lea     rcx, [rsp+58h+var_28]
0x180006cb4  call    ?InternalRelease@?$ComPtr@UIConfigNode@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(void)
0x180006cb9  lea     r8, [rsp+58h+var_28]
0x180006cbe  mov     rdx, rdi
0x180006cc1  mov     rcx, r14
0x180006cc4  mov     rax, rsi
0x180006cc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ccc  mov     edi, eax
0x180006cce  test    eax, eax
0x180006cd0  jns     short loc_180006D1E
0x180006cd2  mov     rcx, [rsp+58h]; this
0x180006cd7  mov     r9d, eax; char *
0x180006cda  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180006ce1  mov     edx, 183h; void *
0x180006ce6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006ceb  nop
0x180006cec  lea     rcx, [rsp+58h+var_28]
0x180006cf1  call    ?InternalRelease@?$ComPtr@UIConfigNode@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(void)
0x180006cf6  nop
0x180006cf7  lea     rcx, [rsp+58h+arg_10]
0x180006cfc  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180006d01  nop
0x180006d02  lea     rcx, [rsp+58h+arg_18]
0x180006d07  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180006d0c  nop
0x180006d0d  lea     rcx, [rsp+58h+arg_8]
0x180006d12  call    ?InternalRelease@?$ComPtr@UIConfigNode@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(void)
0x180006d17  mov     eax, edi
0x180006d19  jmp     loc_180006E17
0x180006d1e  mov     rcx, [rsp+58h+var_28]
0x180006d23  mov     rax, [rcx]
0x180006d26  mov     rdx, rbx
0x180006d29  mov     rax, [rax+48h]
0x180006d2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d32  mov     ebx, eax
0x180006d34  test    eax, eax
0x180006d36  jns     short loc_180006D84
0x180006d38  mov     rcx, [rsp+58h]; this
0x180006d3d  mov     r9d, eax; char *
0x180006d40  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180006d47  mov     edx, 184h; void *
0x180006d4c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006d51  nop
0x180006d52  lea     rcx, [rsp+58h+var_28]
0x180006d57  call    ?InternalRelease@?$ComPtr@UIConfigNode@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(void)
0x180006d5c  nop
0x180006d5d  lea     rcx, [rsp+58h+arg_10]
0x180006d62  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180006d67  nop
0x180006d68  lea     rcx, [rsp+58h+arg_18]
0x180006d6d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180006d72  nop
0x180006d73  lea     rcx, [rsp+58h+arg_8]
0x180006d78  call    ?InternalRelease@?$ComPtr@UIConfigNode@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(void)
0x180006d7d  mov     eax, ebx
0x180006d7f  jmp     loc_180006E17
0x180006d84  mov     rcx, [rsp+58h+arg_8]
0x180006d89  mov     rax, [rcx]
0x180006d8c  mov     rax, [rax+18h]
0x180006d90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d95  mov     ebx, eax
0x180006d97  test    eax, eax
0x180006d99  jns     short loc_180006DE4
0x180006d9b  mov     rcx, [rsp+58h]; this
0x180006da0  mov     r9d, eax; char *
0x180006da3  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180006daa  mov     edx, 185h; void *
0x180006daf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006db4  nop
0x180006db5  lea     rcx, [rsp+58h+var_28]
0x180006dba  call    ?InternalRelease@?$ComPtr@UIConfigNode@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(void)
0x180006dbf  nop
0x180006dc0  lea     rcx, [rsp+58h+arg_10]
0x180006dc5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180006dca  nop
0x180006dcb  lea     rcx, [rsp+58h+arg_18]
0x180006dd0  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180006dd5  nop
0x180006dd6  lea     rcx, [rsp+58h+arg_8]
0x180006ddb  call    ?InternalRelease@?$ComPtr@UIConfigNode@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(void)
0x180006de0  mov     eax, ebx
0x180006de2  jmp     short loc_180006E17
0x180006de4  lea     rcx, [rsp+58h+var_28]
0x180006de9  call    ?InternalRelease@?$ComPtr@UIConfigNode@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(void)
0x180006dee  nop
0x180006def  lea     rcx, [rsp+58h+arg_10]
0x180006df4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180006df9  nop
0x180006dfa  lea     rcx, [rsp+58h+arg_18]
0x180006dff  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180006e04  nop
0x180006e05  lea     rcx, [rsp+58h+arg_8]
0x180006e0a  call    ?InternalRelease@?$ComPtr@UIConfigNode@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(void)
0x180006e0f  xor     eax, eax
0x180006e11  jmp     short loc_180006E17
0x180006e13  mov     eax, dword ptr [rsp+58h+arg_8]
0x180006e17  mov     rbx, [rsp+58h+arg_0]
0x180006e1c  add     rsp, 40h
0x180006e20  pop     r14
0x180006e22  pop     rdi
0x180006e23  pop     rsi
0x180006e24  retn
```
