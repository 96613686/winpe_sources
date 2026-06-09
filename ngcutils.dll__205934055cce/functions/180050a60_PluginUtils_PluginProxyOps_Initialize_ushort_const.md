# PluginUtils::PluginProxyOps::Initialize(ushort const *)

- ea: `0x180050a60`
- end: `0x180050cc5`
- name: `?Initialize@PluginProxyOps@PluginUtils@@UEAAJPEBG@Z`
- size: `613`
- prototype: `int(PluginUtils::PluginProxyOps *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180003080`
- `0x18000a5b4`
- `0x18000ef08`
- `0x18000f7d0`
- `0x180050a60`
- `0x180061010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180050ac9`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180050ac9`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x180050b17`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x180050b17`

## string_xrefs

- `0x180050aa3`: `onecore\ds\security\ngc\utils\plugin\lib\pluginproxyopsimpl.cpp`
- `0x180050add`: `onecore\ds\security\ngc\utils\plugin\lib\pluginproxyopsimpl.cpp`
- `0x180050b2b`: `onecore\ds\security\ngc\utils\plugin\lib\pluginproxyopsimpl.cpp`
- `0x180050b87`: `onecore\ds\security\ngc\utils\plugin\lib\pluginproxyopsimpl.cpp`
- `0x180050bf2`: `onecore\ds\security\ngc\utils\plugin\lib\pluginproxyopsimpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall PluginUtils::PluginProxyOps::Initialize(
        PluginUtils::PluginProxyOps *this,
        const unsigned __int16 *a2)
{
  HRESULT v5; // eax
  unsigned int v6; // ebx
  HRESULT ClassObject; // eax
  unsigned int v8; // ebx
  int v9; // eax
  unsigned int v10; // ebx
  int v11; // eax
  unsigned int v12; // ebx
  _QWORD *v13; // rbx
  __int64 v14; // rdi
  int ppv; // [rsp+20h] [rbp-48h]
  int ppva; // [rsp+20h] [rbp-48h]
  LPVOID v17; // [rsp+30h] [rbp-38h] BYREF
  __int64 (__fastcall ***v18)(_QWORD, GUID *, __int64 *); // [rsp+38h] [rbp-30h] BYREF
  __int64 v19; // [rsp+40h] [rbp-28h] BYREF
  GUID pclsid; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
  {
    pclsid = 0;
    v5 = CLSIDFromString(a2, &pclsid);
    v6 = v5;
    if ( v5 >= 0 )
    {
      v17 = 0;
      ClassObject = CoGetClassObject(&pclsid, 4u, 0, &GUID_00000001_0000_0000_c000_000000000046, &v17);
      v8 = ClassObject;
      if ( ClassObject >= 0 )
      {
        v18 = 0;
        v9 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, GUID *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v17 + 24LL))(
               v17,
               0,
               &GUID_00000000_0000_0000_c000_000000000046,
               &v18);
        v10 = v9;
        if ( v9 >= 0 )
        {
          v19 = 0;
          v11 = (**v18)(v18, &GUID_d26bcf6f_b54c_43ff_9f06_d5bf148625f7, &v19);
          v12 = v11;
          if ( v11 >= 0 )
          {
            v13 = (_QWORD *)((char *)this + 32);
            v14 = v19;
            v19 = 0;
            if ( *v13 )
            {
              winrt::com_ptr<Windows::Storage::Streams::IBufferByteAccess>::unconditional_release_ref(v13);
              if ( *v13 )
                winrt::com_ptr<Windows::Storage::Streams::IBufferByteAccess>::unconditional_release_ref(v13);
            }
            *v13 = v14;
            if ( v19 )
              winrt::com_ptr<Windows::Storage::Streams::IBufferByteAccess>::unconditional_release_ref(&v19);
            if ( v18 )
              winrt::com_ptr<Windows::Storage::Streams::IBufferByteAccess>::unconditional_release_ref(&v18);
            if ( v17 )
              winrt::com_ptr<Windows::Storage::Streams::IBufferByteAccess>::unconditional_release_ref(&v17);
            return 0;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x20,
              (unsigned int)"onecore\\ds\\security\\ngc\\utils\\plugin\\lib\\pluginproxyopsimpl.cpp",
              (const char *)(unsigned int)v11,
              ppva);
            if ( v19 )
              winrt::com_ptr<Windows::Storage::Streams::IBufferByteAccess>::unconditional_release_ref(&v19);
            if ( v18 )
              winrt::com_ptr<Windows::Storage::Streams::IBufferByteAccess>::unconditional_release_ref(&v18);
            if ( v17 )
              winrt::com_ptr<Windows::Storage::Streams::IBufferByteAccess>::unconditional_release_ref(&v17);
            return v12;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1D,
            (unsigned int)"onecore\\ds\\security\\ngc\\utils\\plugin\\lib\\pluginproxyopsimpl.cpp",
            (const char *)(unsigned int)v9,
            ppva);
          if ( v18 )
            winrt::com_ptr<Windows::Storage::Streams::IBufferByteAccess>::unconditional_release_ref(&v18);
          if ( v17 )
            winrt::com_ptr<Windows::Storage::Streams::IBufferByteAccess>::unconditional_release_ref(&v17);
          return v10;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1A,
          (unsigned int)"onecore\\ds\\security\\ngc\\utils\\plugin\\lib\\pluginproxyopsimpl.cpp",
          (const char *)(unsigned int)ClassObject,
          ppva);
        if ( v17 )
          winrt::com_ptr<Windows::Storage::Streams::IBufferByteAccess>::unconditional_release_ref(&v17);
        return v8;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x12,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\plugin\\lib\\pluginproxyopsimpl.cpp",
        (const char *)(unsigned int)v5,
        ppv);
      return v6;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\plugin\\lib\\pluginproxyopsimpl.cpp",
      (const char *)0x80004001LL,
      ppv);
    return 2147500033LL;
  }
}

```

## disassembly

```asm
0x180050a60  mov     [rsp+arg_10], rbx
0x180050a65  mov     [rsp+arg_18], rsi
0x180050a6a  push    rdi
0x180050a6b  sub     rsp, 60h
0x180050a6f  mov     rax, cs:__security_cookie
0x180050a76  xor     rax, rsp
0x180050a79  mov     [rsp+68h+var_10], rax
0x180050a7e  mov     rbx, rdx
0x180050a81  mov     rdi, rcx
0x180050a84  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements> `wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl(void)'::`2'::impl
0x180050a8b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x180050a90  xor     esi, esi
0x180050a92  test    al, al
0x180050a94  jnz     short loc_180050AB9
0x180050a96  mov     rcx, [rsp+68h]; this
0x180050a9b  mov     ebx, 80004001h
0x180050aa0  mov     r9d, ebx; char *
0x180050aa3  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\utils\\plug"...
0x180050aaa  lea     edx, [rsi+0Fh]; void *
0x180050aad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050ab2  mov     eax, ebx
0x180050ab4  jmp     loc_180050CA5
0x180050ab9  xorps   xmm0, xmm0
0x180050abc  movups  xmmword ptr [rsp+68h+pclsid.Data1], xmm0
0x180050ac1  lea     rdx, [rsp+68h+pclsid]; pclsid
0x180050ac6  mov     rcx, rbx; lpsz
0x180050ac9  call    cs:__imp_CLSIDFromString
0x180050acf  mov     ebx, eax
0x180050ad1  test    eax, eax
0x180050ad3  jns     short loc_180050AF5
0x180050ad5  mov     rcx, [rsp+68h]; this
0x180050ada  mov     r9d, eax; char *
0x180050add  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\utils\\plug"...
0x180050ae4  mov     edx, 12h; void *
0x180050ae9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050aee  mov     eax, ebx
0x180050af0  jmp     loc_180050CA5
0x180050af5  mov     [rsp+68h+var_38], rsi
0x180050afa  lea     rax, [rsp+68h+var_38]
0x180050aff  mov     qword ptr [rsp+68h+ppv], rax; int
0x180050b04  lea     r9, _GUID_00000001_0000_0000_c000_000000000046; riid
0x180050b0b  xor     r8d, r8d; pvReserved
0x180050b0e  lea     edx, [r8+4]; dwClsContext
0x180050b12  lea     rcx, [rsp+68h+pclsid]; rclsid
0x180050b17  call    cs:__imp_CoGetClassObject
0x180050b1d  mov     ebx, eax
0x180050b1f  test    eax, eax
0x180050b21  jns     short loc_180050B55
0x180050b23  mov     rcx, [rsp+68h]; this
0x180050b28  mov     r9d, eax; char *
0x180050b2b  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\utils\\plug"...
0x180050b32  mov     edx, 1Ah; void *
0x180050b37  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050b3c  nop
0x180050b3d  cmp     [rsp+68h+var_38], rsi
0x180050b42  jz      short loc_180050B4E
0x180050b44  lea     rcx, [rsp+68h+var_38]
0x180050b49  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@Streams@Storage@Windows@@@winrt@@AEAAXXZ; winrt::com_ptr<Windows::Storage::Streams::IBufferByteAccess>::unconditional_release_ref(void)
0x180050b4e  mov     eax, ebx
0x180050b50  jmp     loc_180050CA5
0x180050b55  mov     [rsp+68h+var_30], rsi
0x180050b5a  mov     rcx, [rsp+68h+var_38]
0x180050b5f  mov     rax, [rcx]
0x180050b62  lea     r9, [rsp+68h+var_30]
0x180050b67  lea     r8, _GUID_00000000_0000_0000_c000_000000000046
0x180050b6e  xor     edx, edx
0x180050b70  mov     rax, [rax+18h]
0x180050b74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050b79  mov     ebx, eax
0x180050b7b  test    eax, eax
0x180050b7d  jns     short loc_180050BC3
0x180050b7f  mov     rcx, [rsp+68h]; this
0x180050b84  mov     r9d, eax; char *
0x180050b87  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\utils\\plug"...
0x180050b8e  mov     edx, 1Dh; void *
0x180050b93  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050b98  nop
0x180050b99  cmp     [rsp+68h+var_30], rsi
0x180050b9e  jz      short loc_180050BAB
0x180050ba0  lea     rcx, [rsp+68h+var_30]
0x180050ba5  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@Streams@Storage@Windows@@@winrt@@AEAAXXZ; winrt::com_ptr<Windows::Storage::Streams::IBufferByteAccess>::unconditional_release_ref(void)
0x180050baa  nop
0x180050bab  cmp     [rsp+68h+var_38], rsi
0x180050bb0  jz      short loc_180050BBC
0x180050bb2  lea     rcx, [rsp+68h+var_38]
0x180050bb7  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@Streams@Storage@Windows@@@winrt@@AEAAXXZ; winrt::com_ptr<Windows::Storage::Streams::IBufferByteAccess>::unconditional_release_ref(void)
0x180050bbc  mov     eax, ebx
0x180050bbe  jmp     loc_180050CA5
0x180050bc3  mov     [rsp+68h+var_28], rsi
0x180050bc8  mov     rcx, [rsp+68h+var_30]
0x180050bcd  mov     rax, [rcx]
0x180050bd0  lea     r8, [rsp+68h+var_28]
0x180050bd5  lea     rdx, _GUID_d26bcf6f_b54c_43ff_9f06_d5bf148625f7
0x180050bdc  mov     rax, [rax]
0x180050bdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050be4  mov     ebx, eax
0x180050be6  test    eax, eax
0x180050be8  jns     short loc_180050C3D
0x180050bea  mov     rcx, [rsp+68h]; this
0x180050bef  mov     r9d, eax; char *
0x180050bf2  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\utils\\plug"...
0x180050bf9  mov     edx, 20h ; ' '; void *
0x180050bfe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050c03  nop
0x180050c04  cmp     [rsp+68h+var_28], rsi
0x180050c09  jz      short loc_180050C16
0x180050c0b  lea     rcx, [rsp+68h+var_28]
0x180050c10  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@Streams@Storage@Windows@@@winrt@@AEAAXXZ; winrt::com_ptr<Windows::Storage::Streams::IBufferByteAccess>::unconditional_release_ref(void)
0x180050c15  nop
0x180050c16  cmp     [rsp+68h+var_30], rsi
0x180050c1b  jz      short loc_180050C28
0x180050c1d  lea     rcx, [rsp+68h+var_30]
0x180050c22  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@Streams@Storage@Windows@@@winrt@@AEAAXXZ; winrt::com_ptr<Windows::Storage::Streams::IBufferByteAccess>::unconditional_release_ref(void)
0x180050c27  nop
0x180050c28  cmp     [rsp+68h+var_38], rsi
0x180050c2d  jz      short loc_180050C39
0x180050c2f  lea     rcx, [rsp+68h+var_38]
0x180050c34  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@Streams@Storage@Windows@@@winrt@@AEAAXXZ; winrt::com_ptr<Windows::Storage::Streams::IBufferByteAccess>::unconditional_release_ref(void)
0x180050c39  mov     eax, ebx
0x180050c3b  jmp     short loc_180050CA5
0x180050c3d  lea     rbx, [rdi+20h]
0x180050c41  mov     rdi, [rsp+68h+var_28]
0x180050c46  mov     [rsp+68h+var_28], rsi
0x180050c4b  cmp     [rbx], rsi
0x180050c4e  jz      short loc_180050C65
0x180050c50  mov     rcx, rbx
0x180050c53  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@Streams@Storage@Windows@@@winrt@@AEAAXXZ; winrt::com_ptr<Windows::Storage::Streams::IBufferByteAccess>::unconditional_release_ref(void)
0x180050c58  cmp     [rbx], rsi
0x180050c5b  jz      short loc_180050C65
0x180050c5d  mov     rcx, rbx
0x180050c60  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@Streams@Storage@Windows@@@winrt@@AEAAXXZ; winrt::com_ptr<Windows::Storage::Streams::IBufferByteAccess>::unconditional_release_ref(void)
0x180050c65  mov     [rbx], rdi
0x180050c68  cmp     [rsp+68h+var_28], rsi
0x180050c6d  jz      short loc_180050C7A
0x180050c6f  lea     rcx, [rsp+68h+var_28]
0x180050c74  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@Streams@Storage@Windows@@@winrt@@AEAAXXZ; winrt::com_ptr<Windows::Storage::Streams::IBufferByteAccess>::unconditional_release_ref(void)
0x180050c79  nop
0x180050c7a  cmp     [rsp+68h+var_30], rsi
0x180050c7f  jz      short loc_180050C8C
0x180050c81  lea     rcx, [rsp+68h+var_30]
0x180050c86  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@Streams@Storage@Windows@@@winrt@@AEAAXXZ; winrt::com_ptr<Windows::Storage::Streams::IBufferByteAccess>::unconditional_release_ref(void)
0x180050c8b  nop
0x180050c8c  cmp     [rsp+68h+var_38], rsi
0x180050c91  jz      short loc_180050C9D
0x180050c93  lea     rcx, [rsp+68h+var_38]
0x180050c98  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@Streams@Storage@Windows@@@winrt@@AEAAXXZ; winrt::com_ptr<Windows::Storage::Streams::IBufferByteAccess>::unconditional_release_ref(void)
0x180050c9d  xor     eax, eax
0x180050c9f  jmp     short loc_180050CA5
0x180050ca1  mov     eax, dword ptr [rsp+68h+var_38]
0x180050ca5  mov     rcx, [rsp+68h+var_10]
0x180050caa  xor     rcx, rsp; StackCookie
0x180050cad  call    __security_check_cookie
0x180050cb2  lea     r11, [rsp+68h+var_8]
0x180050cb7  mov     rbx, [r11+20h]
0x180050cbb  mov     rsi, [r11+28h]
0x180050cbf  mov     rsp, r11
0x180050cc2  pop     rdi
0x180050cc3  retn
```
