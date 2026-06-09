# InstalledPackageNode::Remove(IConfigManager2URI *)

- ea: `0x180008ab0`
- end: `0x180008d27`
- name: `?Remove@InstalledPackageNode@@SAJPEAUIConfigManager2URI@@@Z`
- size: `631`
- prototype: `__int64 __fastcall(struct IConfigManager2URI *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000db50`

## callees

- `0x18000526c`
- `0x180006974`
- `0x180007834`
- `0x1800083e8`
- `0x1800088a4`
- `0x180008ab0`
- `0x180032c84`
- `0x180032e84`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180008ae0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180008ae0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008b22`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008b22`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180008b97`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180008b97`

## string_xrefs

- `0x180008b4a`: `onecoreuap\admin\prov\provcsp\installedpackagenode.cpp`
- `0x180008bb1`: `onecoreuap\admin\prov\provcsp\installedpackagenode.cpp`
- `0x180008c1a`: `onecoreuap\admin\prov\provcsp\installedpackagenode.cpp`
- `0x180008c7f`: `onecoreuap\admin\prov\provcsp\installedpackagenode.cpp`
- `0x180008d09`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall InstalledPackageNode::Remove(struct IConfigManager2URI *a1)
{
  __int64 v1; // r14
  HANDLE v2; // rsi
  DWORD v3; // eax
  const char *v4; // r9
  DWORD v5; // edi
  unsigned int v6; // r8d
  const char *v7; // r9
  const char *v8; // r9
  __int64 result; // rax
  HRESULT v10; // eax
  unsigned int v11; // edi
  LPVOID v12; // rcx
  int v13; // eax
  LPVOID v14; // rcx
  int v15; // eax
  LPVOID v16; // rcx
  LPVOID v17; // rcx
  int ppv; // [rsp+20h] [rbp-38h]
  int ppva; // [rsp+20h] [rbp-38h]
  HANDLE hHandle[2]; // [rsp+30h] [rbp-28h] BYREF
  _BYTE v21[24]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  LPVOID v23; // [rsp+68h] [rbp+10h] BYREF
  HANDLE hMutex; // [rsp+70h] [rbp+18h] BYREF

  try
  {
    v1 = PackageIdFromUri();
    ProvAgent::ProvAgent((ProvAgent *)hHandle);
    v2 = hHandle[0];
    v3 = WaitForSingleObjectEx(hHandle[0], 0, 0);
    v5 = v3;
    if ( v3 == 258 )
    {
      v2 = 0;
    }
    else if ( (v3 & 0xFFFFFF7F) != 0 )
    {
      wil::details::in1diag3::FailFast_Unexpected(
        retaddr,
        (void *)0xE01,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
        v4);
    }
    hMutex = v2;
    __4__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___wil__QEAAAEAV01___QEAV01__Z(
      v21,
      &hMutex);
    if ( hMutex && !ReleaseMutex(hMutex) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v6, v7);
    if ( v5 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4B,
        (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\installedpackagenode.cpp",
        (const char *)0x86000019LL,
        ppv);
      ProvAgent::~ProvAgent((ProvAgent *)hHandle);
      return 2248146969LL;
    }
    v23 = 0;
    v10 = CoCreateInstance(
            &GUID_5b89deeb_4df1_4cf6_9979_c79185cb95a0,
            0,
            1u,
            &GUID_9051683d_92ab_4ffd_bb73_1f80a11ae5c2,
            &v23);
    v11 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4E,
        (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\installedpackagenode.cpp",
        (const char *)(unsigned int)v10,
        ppva);
      v12 = v23;
      if ( v23 )
      {
        v23 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v12 + 16LL))(v12);
      }
LABEL_21:
      ProvAgent::~ProvAgent((ProvAgent *)hHandle);
      return v11;
    }
    v13 = (*(__int64 (__fastcall **)(LPVOID, const WCHAR *))(*(_QWORD *)v23 + 72LL))(v23, L"ProvisioningCSP");
    v11 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4F,
        (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\installedpackagenode.cpp",
        (const char *)(unsigned int)v13,
        ppva);
      v14 = v23;
      if ( v23 )
      {
        v23 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v14 + 16LL))(v14);
      }
      goto LABEL_21;
    }
    v15 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v23 + 32LL))(v23, v1);
    v11 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x50,
        (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\installedpackagenode.cpp",
        (const char *)(unsigned int)v15,
        ppva);
      v16 = v23;
      if ( v23 )
      {
        v23 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v16 + 16LL))(v16);
      }
      goto LABEL_21;
    }
    v17 = v23;
    if ( v23 )
    {
      v23 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v17 + 16LL))(v17);
    }
    ProvAgent::~ProvAgent((ProvAgent *)hHandle);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x52,
                           (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\installedpackagenode.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x180008ab0  mov     [rsp+arg_0], rsi
0x180008ab5  mov     [rsp+arg_18], rdi
0x180008aba  push    r14
0x180008abc  sub     rsp, 50h
0x180008ac0  call    PackageIdFromUri
0x180008ac5  mov     r14, rax
0x180008ac8  lea     rcx, [rsp+58h+hHandle]; this
0x180008acd  call    ??0ProvAgent@@QEAA@XZ; ProvAgent::ProvAgent(void)
0x180008ad2  nop
0x180008ad3  mov     rsi, [rsp+58h+hHandle]
0x180008ad8  xor     r8d, r8d; bAlertable
0x180008adb  xor     edx, edx; dwMilliseconds
0x180008add  mov     rcx, rsi; hHandle
0x180008ae0  call    cs:__imp_WaitForSingleObjectEx
0x180008ae7  nop     dword ptr [rax+rax+00h]
0x180008aec  mov     edi, eax
0x180008aee  cmp     eax, 102h
0x180008af3  jz      short loc_180008B02
0x180008af5  test    eax, 0FFFFFF7Fh
0x180008afa  jnz     loc_180008D04
0x180008b00  jmp     short loc_180008B04
0x180008b02  xor     esi, esi
0x180008b04  mov     [rsp+58h+hMutex], rsi
0x180008b09  lea     rdx, [rsp+58h+hMutex]
0x180008b0e  lea     rcx, [rsp+58h+var_18]
0x180008b13  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z
0x180008b18  mov     rcx, [rsp+58h+hMutex]; hMutex
0x180008b1d  test    rcx, rcx
0x180008b20  jz      short loc_180008B3B
0x180008b22  call    cs:__imp_ReleaseMutex
0x180008b29  nop     dword ptr [rax+rax+00h]
0x180008b2e  mov     rcx, [rsp+58h]; this
0x180008b33  test    eax, eax
0x180008b35  jz      loc_180008D1B
0x180008b3b  test    edi, edi
0x180008b3d  jz      short loc_180008B70
0x180008b3f  mov     rcx, [rsp+58h]; this
0x180008b44  mov     r9d, 86000019h; char *
0x180008b4a  lea     r8, aOnecoreuapAdmi_26; "onecoreuap\\admin\\prov\\provcsp\\insta"...
0x180008b51  mov     edx, 4Bh ; 'K'; void *
0x180008b56  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008b5b  nop
0x180008b5c  lea     rcx, [rsp+58h+hHandle]; this
0x180008b61  call    ??1ProvAgent@@QEAA@XZ; ProvAgent::~ProvAgent(void)
0x180008b66  mov     eax, 86000019h
0x180008b6b  jmp     loc_180008CF2
0x180008b70  mov     [rsp+58h+arg_8], 0
0x180008b79  lea     rax, [rsp+58h+arg_8]
0x180008b7e  mov     qword ptr [rsp+58h+ppv], rax; int
0x180008b83  lea     r9, _GUID_9051683d_92ab_4ffd_bb73_1f80a11ae5c2; riid
0x180008b8a  xor     edx, edx; pUnkOuter
0x180008b8c  lea     r8d, [rdx+1]; dwClsContext
0x180008b90  lea     rcx, _GUID_5b89deeb_4df1_4cf6_9979_c79185cb95a0; rclsid
0x180008b97  call    cs:__imp_CoCreateInstance
0x180008b9e  nop     dword ptr [rax+rax+00h]
0x180008ba3  mov     edi, eax
0x180008ba5  test    eax, eax
0x180008ba7  jns     short loc_180008BF4
0x180008ba9  mov     rcx, [rsp+58h]; this
0x180008bae  mov     r9d, eax; char *
0x180008bb1  lea     r8, aOnecoreuapAdmi_26; "onecoreuap\\admin\\prov\\provcsp\\insta"...
0x180008bb8  mov     edx, 4Eh ; 'N'; void *
0x180008bbd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008bc2  nop
0x180008bc3  mov     rcx, [rsp+58h+arg_8]
0x180008bc8  test    rcx, rcx
0x180008bcb  jz      short loc_180008BE3
0x180008bcd  mov     [rsp+58h+arg_8], 0
0x180008bd6  mov     rax, [rcx]
0x180008bd9  mov     rax, [rax+10h]
0x180008bdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008be2  nop
0x180008be3  lea     rcx, [rsp+58h+hHandle]; this
0x180008be8  call    ??1ProvAgent@@QEAA@XZ; ProvAgent::~ProvAgent(void)
0x180008bed  mov     eax, edi
0x180008bef  jmp     loc_180008CF2
0x180008bf4  mov     rcx, [rsp+58h+arg_8]
0x180008bf9  mov     rax, [rcx]
0x180008bfc  lea     rdx, sourceString; "ProvisioningCSP"
0x180008c03  mov     rax, [rax+48h]
0x180008c07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c0c  mov     edi, eax
0x180008c0e  test    eax, eax
0x180008c10  jns     short loc_180008C5D
0x180008c12  mov     rcx, [rsp+58h]; this
0x180008c17  mov     r9d, eax; char *
0x180008c1a  lea     r8, aOnecoreuapAdmi_26; "onecoreuap\\admin\\prov\\provcsp\\insta"...
0x180008c21  mov     edx, 4Fh ; 'O'; void *
0x180008c26  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008c2b  nop
0x180008c2c  mov     rcx, [rsp+58h+arg_8]
0x180008c31  test    rcx, rcx
0x180008c34  jz      short loc_180008C4C
0x180008c36  mov     [rsp+58h+arg_8], 0
0x180008c3f  mov     rax, [rcx]
0x180008c42  mov     rax, [rax+10h]
0x180008c46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c4b  nop
0x180008c4c  lea     rcx, [rsp+58h+hHandle]; this
0x180008c51  call    ??1ProvAgent@@QEAA@XZ; ProvAgent::~ProvAgent(void)
0x180008c56  mov     eax, edi
0x180008c58  jmp     loc_180008CF2
0x180008c5d  mov     rcx, [rsp+58h+arg_8]
0x180008c62  mov     rax, [rcx]
0x180008c65  mov     rdx, r14
0x180008c68  mov     rax, [rax+20h]
0x180008c6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c71  mov     edi, eax
0x180008c73  test    eax, eax
0x180008c75  jns     short loc_180008CBF
0x180008c77  mov     rcx, [rsp+58h]; this
0x180008c7c  mov     r9d, eax; char *
0x180008c7f  lea     r8, aOnecoreuapAdmi_26; "onecoreuap\\admin\\prov\\provcsp\\insta"...
0x180008c86  mov     edx, 50h ; 'P'; void *
0x180008c8b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008c90  nop
0x180008c91  mov     rcx, [rsp+58h+arg_8]
0x180008c96  test    rcx, rcx
0x180008c99  jz      short loc_180008CB1
0x180008c9b  mov     [rsp+58h+arg_8], 0
0x180008ca4  mov     rax, [rcx]
0x180008ca7  mov     rax, [rax+10h]
0x180008cab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cb0  nop
0x180008cb1  lea     rcx, [rsp+58h+hHandle]; this
0x180008cb6  call    ??1ProvAgent@@QEAA@XZ; ProvAgent::~ProvAgent(void)
0x180008cbb  mov     eax, edi
0x180008cbd  jmp     short loc_180008CF2
0x180008cbf  mov     rcx, [rsp+58h+arg_8]
0x180008cc4  test    rcx, rcx
0x180008cc7  jz      short loc_180008CDF
0x180008cc9  mov     [rsp+58h+arg_8], 0
0x180008cd2  mov     rax, [rcx]
0x180008cd5  mov     rax, [rax+10h]
0x180008cd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cde  nop
0x180008cdf  lea     rcx, [rsp+58h+hHandle]; this
0x180008ce4  call    ??1ProvAgent@@QEAA@XZ; ProvAgent::~ProvAgent(void)
0x180008ce9  nop
0x180008cea  xor     eax, eax
0x180008cec  jmp     short loc_180008CF2
0x180008cee  mov     eax, dword ptr [rsp+58h+arg_8]
0x180008cf2  mov     rsi, [rsp+58h+arg_0]
0x180008cf7  mov     rdi, [rsp+58h+arg_18]
0x180008cfc  add     rsp, 50h
0x180008d00  pop     r14
0x180008d02  retn
0x180008d04  mov     rcx, [rsp+58h]; this
0x180008d09  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008d10  mov     edx, 0E01h; void *
0x180008d15  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180008d1b  mov     edx, 0A15h; void *
0x180008d20  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
