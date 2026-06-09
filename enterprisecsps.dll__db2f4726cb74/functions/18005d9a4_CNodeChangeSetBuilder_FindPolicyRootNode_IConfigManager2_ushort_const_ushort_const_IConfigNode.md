# CNodeChangeSetBuilder::FindPolicyRootNode(IConfigManager2 *,ushort const *,ushort const *,IConfigNode * *)

- ea: `0x18005d9a4`
- end: `0x18005dba7`
- name: `?FindPolicyRootNode@CNodeChangeSetBuilder@@QEAAJPEAUIConfigManager2@@PEBG1PEAPEAUIConfigNode@@@Z`
- size: `515`
- prototype: `int(CNodeChangeSetBuilder *__hidden this, struct IConfigManager2 *, const unsigned __int16 *, const unsigned __int16 *, struct IConfigNode **)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005c628`
- `0x18005ce1c`

## callees

- `0x18000caf4`
- `0x18000d4d4`
- `0x180025a78`
- `0x180025a9c`
- `0x18002dc38`
- `0x180041f2c`
- `0x18005a654`
- `0x18005d9a4`
- `0x180107010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005da19`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005da19`
- `omadmapi!__imp_URIEncodeSegment` at `0x18005da86`
- `omadmapi!__imp_URIEncodeSegment` at `0x18005da86`

## string_xrefs

- `0x18005d9d6`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\nodecache\nodechangesetbuilder.cpp`
- `0x18005da56`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\nodecache\nodechangesetbuilder.cpp`
- `0x18005da9f`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\nodecache\nodechangesetbuilder.cpp`
- `0x18005dae2`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\nodecache\nodechangesetbuilder.cpp`
- `0x18005db3d`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\nodecache\nodechangesetbuilder.cpp`
- `0x18005da25`: `./User/Vendor/MSFT/NodeCache`
- `0x18005da2c`: `./Device/Vendor/MSFT/NodeCache`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CNodeChangeSetBuilder::FindPolicyRootNode(
        CNodeChangeSetBuilder *this,
        struct IConfigManager2 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        struct IConfigNode **a5)
{
  __int64 v8; // rdx
  unsigned int v9; // ebx
  struct IConfigNode **v10; // r14
  int v11; // eax
  const unsigned __int16 *v12; // r8
  int CspNodeFromUri; // eax
  int v14; // eax
  __int64 v15; // rbx
  struct IConfigNode *v16; // rsi
  __int64 (__fastcall *v17)(struct IConfigNode *, __int64, struct IConfigNode **); // rdi
  int v18; // eax
  struct IConfigNode *v19; // rax
  struct IConfigNode *v21; // [rsp+20h] [rbp-10h] BYREF
  __int64 v22; // [rsp+28h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  CNodeChangeSetBuilder *v24; // [rsp+50h] [rbp+20h] BYREF
  struct IConfigNode *v25; // [rsp+58h] [rbp+28h] BYREF

  v24 = this;
  if ( a2 )
  {
    v10 = a5;
    if ( !a5 )
    {
      v8 = 383;
      goto LABEL_3;
    }
    v21 = 0;
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v21);
    v11 = _o__wcsicmp(a3, L"Device");
    v12 = L"./Device/Vendor/MSFT/NodeCache";
    if ( v11 )
      v12 = L"./User/Vendor/MSFT/NodeCache";
    CspNodeFromUri = GetCspNodeFromUri(a2, v21, v12, &v21);
    v9 = CspNodeFromUri;
    if ( CspNodeFromUri >= 0 )
    {
      v24 = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v24,
        0);
      v14 = URIEncodeSegment(a4, &v24);
      v9 = v14;
      if ( v14 >= 0 )
      {
        wil::make_bstr_nothrow(&v22, v24);
        v15 = v22;
        if ( v22 )
        {
          v25 = 0;
          v16 = v21;
          v17 = *(__int64 (__fastcall **)(struct IConfigNode *, __int64, struct IConfigNode **))(*(_QWORD *)v21 + 208LL);
          Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v25);
          v18 = v17(v16, v15, &v25);
          v9 = v18;
          if ( v18 >= 0 )
          {
            v19 = v25;
            v25 = 0;
            *v10 = v19;
            Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v25);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v22);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v24);
            v9 = 0;
            goto LABEL_19;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x190,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\nodecache\\nodechangesetbuilder.cpp",
            (const char *)(unsigned int)v18,
            (int)v21);
          Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v25);
        }
        else
        {
          v9 = -2147024882;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x18D,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\nodecache\\nodechangesetbuilder.cpp",
            (const char *)0x8007000ELL,
            (int)v21);
        }
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v22);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x18A,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\nodecache\\nodechangesetbuilder.cpp",
          (const char *)(unsigned int)v14,
          (int)v21);
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v24);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x186,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\nodecache\\nodechangesetbuilder.cpp",
        (const char *)(unsigned int)CspNodeFromUri,
        (int)v21);
    }
LABEL_19:
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v21);
    return v9;
  }
  v8 = 382;
LABEL_3:
  v9 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\nodecache\\nodechangesetbuilder.cpp",
    (const char *)0x80070057LL,
    (int)v21);
  return v9;
}

```

## disassembly

```asm
0x18005d9a4  mov     [rsp-18h+arg_10], rbx
0x18005d9a9  mov     [rsp-18h+arg_18], rsi
0x18005d9ae  mov     [rsp-18h+arg_0], rcx
0x18005d9b3  push    rbp
0x18005d9b4  push    rdi
0x18005d9b5  push    r14
0x18005d9b7  mov     rbp, rsp
0x18005d9ba  sub     rsp, 30h
0x18005d9be  mov     rdi, r9
0x18005d9c1  mov     rsi, r8
0x18005d9c4  mov     rbx, rdx
0x18005d9c7  test    rdx, rdx
0x18005d9ca  jnz     short loc_18005D9EE
0x18005d9cc  mov     edx, 17Eh; void *
0x18005d9d1  mov     ebx, 80070057h
0x18005d9d6  lea     r8, aOnecoreuapAdmi_46; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x18005d9dd  mov     r9d, ebx; char *
0x18005d9e0  mov     rcx, [rbp+18h]; this
0x18005d9e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005d9e9  jmp     loc_18005DB91
0x18005d9ee  mov     r14, [rbp+arg_20]
0x18005d9f2  test    r14, r14
0x18005d9f5  jnz     short loc_18005D9FE
0x18005d9f7  mov     edx, 17Fh
0x18005d9fc  jmp     short loc_18005D9D1
0x18005d9fe  mov     [rbp+var_10], 0
0x18005da06  lea     rcx, [rbp+var_10]
0x18005da0a  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18005da0f  lea     rdx, aDevice; "Device"
0x18005da16  mov     rcx, rsi
0x18005da19  call    cs:__imp__o__wcsicmp
0x18005da20  nop     dword ptr [rax+rax+00h]
0x18005da25  lea     rcx, ?c_szUserCacheCspRoot@CNodeChangeSetBuilder@@2QBGB; "./User/Vendor/MSFT/NodeCache"
0x18005da2c  lea     r8, ?c_szDeviceCacheCspRoot@CNodeChangeSetBuilder@@2QBGB; "./Device/Vendor/MSFT/NodeCache"
0x18005da33  test    eax, eax
0x18005da35  cmovnz  r8, rcx; unsigned __int16 *
0x18005da39  lea     r9, [rbp+var_10]; struct IConfigNode **
0x18005da3d  mov     rdx, [rbp+var_10]; struct IConfigNode *
0x18005da41  mov     rcx, rbx; struct IConfigManager2 *
0x18005da44  call    ?GetCspNodeFromUri@@YAJPEAUIConfigManager2@@PEAUIConfigNode@@PEBGPEAPEAU2@@Z; GetCspNodeFromUri(IConfigManager2 *,IConfigNode *,ushort const *,IConfigNode * *)
0x18005da49  mov     ebx, eax
0x18005da4b  test    eax, eax
0x18005da4d  jns     short loc_18005DA6C
0x18005da4f  mov     rcx, [rbp+18h]; this
0x18005da53  mov     r9d, eax; char *
0x18005da56  lea     r8, aOnecoreuapAdmi_46; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x18005da5d  mov     edx, 186h; void *
0x18005da62  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005da67  jmp     loc_18005DB88
0x18005da6c  mov     [rbp+arg_0], 0
0x18005da74  xor     edx, edx
0x18005da76  lea     rcx, [rbp+arg_0]
0x18005da7a  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18005da7f  lea     rdx, [rbp+arg_0]
0x18005da83  mov     rcx, rdi
0x18005da86  call    cs:__imp_URIEncodeSegment
0x18005da8d  nop     dword ptr [rax+rax+00h]
0x18005da92  mov     ebx, eax
0x18005da94  test    eax, eax
0x18005da96  jns     short loc_18005DABF
0x18005da98  mov     rcx, [rbp+18h]; this
0x18005da9c  mov     r9d, eax; char *
0x18005da9f  lea     r8, aOnecoreuapAdmi_46; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x18005daa6  mov     edx, 18Ah; void *
0x18005daab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005dab0  nop
0x18005dab1  lea     rcx, [rbp+arg_0]
0x18005dab5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18005daba  jmp     loc_18005DB88
0x18005dabf  mov     rdx, [rbp+arg_0]
0x18005dac3  lea     rcx, [rbp+var_8]
0x18005dac7  call    ?make_bstr_nothrow@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr_nothrow(ushort const *)
0x18005dacc  nop
0x18005dacd  mov     rbx, [rbp+var_8]
0x18005dad1  test    rbx, rbx
0x18005dad4  jnz     short loc_18005DAFF
0x18005dad6  mov     rcx, [rbp+18h]; this
0x18005dada  mov     ebx, 8007000Eh
0x18005dadf  mov     r9d, ebx; char *
0x18005dae2  lea     r8, aOnecoreuapAdmi_46; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x18005dae9  mov     edx, 18Dh; void *
0x18005daee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005daf3  nop
0x18005daf4  lea     rcx, [rbp+var_8]
0x18005daf8  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18005dafd  jmp     short loc_18005DAB1
0x18005daff  mov     [rbp+arg_8], 0
0x18005db07  mov     rsi, [rbp+var_10]
0x18005db0b  mov     rax, [rsi]
0x18005db0e  mov     rdi, [rax+0D0h]
0x18005db15  lea     rcx, [rbp+arg_8]
0x18005db19  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18005db1e  lea     r8, [rbp+arg_8]
0x18005db22  mov     rdx, rbx
0x18005db25  mov     rcx, rsi
0x18005db28  mov     rax, rdi
0x18005db2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005db30  mov     ebx, eax
0x18005db32  test    eax, eax
0x18005db34  jns     short loc_18005DB5A
0x18005db36  mov     rcx, [rbp+18h]; this
0x18005db3a  mov     r9d, eax; char *
0x18005db3d  lea     r8, aOnecoreuapAdmi_46; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x18005db44  mov     edx, 190h; void *
0x18005db49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005db4e  nop
0x18005db4f  lea     rcx, [rbp+arg_8]
0x18005db53  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18005db58  jmp     short loc_18005DAF4
0x18005db5a  mov     rax, [rbp+arg_8]
0x18005db5e  mov     [rbp+arg_8], 0
0x18005db66  mov     [r14], rax
0x18005db69  lea     rcx, [rbp+arg_8]
0x18005db6d  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18005db72  nop
0x18005db73  lea     rcx, [rbp+var_8]
0x18005db77  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18005db7c  nop
0x18005db7d  lea     rcx, [rbp+arg_0]
0x18005db81  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18005db86  xor     ebx, ebx
0x18005db88  lea     rcx, [rbp+var_10]
0x18005db8c  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18005db91  mov     eax, ebx
0x18005db93  mov     rbx, [rsp+30h+arg_10]
0x18005db98  mov     rsi, [rsp+30h+arg_18]
0x18005db9d  add     rsp, 30h
0x18005dba1  pop     r14
0x18005dba3  pop     rdi
0x18005dba4  pop     rbp
0x18005dba5  retn
```
