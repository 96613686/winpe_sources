# NavigateUrlInNewBrowserInstance

- ea: `0x181066d58`
- end: `0x181067051`
- name: `NavigateUrlInNewBrowserInstance`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180844a80`

## callees

- `0x180840178`
- `0x181066ac4`
- `0x181066d58`
- `0x1810d1010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x181066dcc`
- `KERNEL32!GetCurrentThreadId` at `0x181066dcc`
- `USER32!AllowSetForegroundWindow` at `0x181066e13`
- `USER32!AllowSetForegroundWindow` at `0x181066f31`
- `USER32!AllowSetForegroundWindow` at `0x181066e13`
- `USER32!AllowSetForegroundWindow` at `0x181066f31`
- `iertutil!__imp_?CoCreateUserBrokerForThread@@YAJKPEAPEAUIEUserBroker@@@Z` at `0x181066dd8`
- `iertutil!__imp_?CoCreateUserBrokerForThread@@YAJKPEAPEAUIEUserBroker@@@Z` at `0x181066dd8`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x181066d84`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x181066ec5`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x181066d84`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x181066ec5`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x181066daa`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x181066daa`
- `urlmon!__imp_IsProtectedModeURL` at `0x181066ed9`
- `urlmon!__imp_IsProtectedModeURL` at `0x181066ed9`
- `urlmon!__imp_?LCIEGetRedirectionPolicyForURL2@@YAJPEBGHHKPEAKPEAHPEAPEAG@Z` at `0x181066f20`
- `urlmon!__imp_?LCIEGetRedirectionPolicyForURL2@@YAJPEBGHHKPEAKPEAHPEAPEAG@Z` at `0x181066f20`
- `OLEAUT32!__imp_SysAllocString` at `0x181066fa3`
- `OLEAUT32!__imp_SysAllocString` at `0x181066fa3`
- `OLEAUT32!__imp_SysFreeString` at `0x18106700c`
- `OLEAUT32!__imp_SysFreeString` at `0x181067016`
- `OLEAUT32!__imp_SysFreeString` at `0x181067020`
- `OLEAUT32!__imp_SysFreeString` at `0x18106703c`
- `OLEAUT32!__imp_SysFreeString` at `0x18106700c`
- `OLEAUT32!__imp_SysFreeString` at `0x181067016`
- `OLEAUT32!__imp_SysFreeString` at `0x181067020`
- `OLEAUT32!__imp_SysFreeString` at `0x18106703c`

## pseudocode

```c
__int64 __fastcall NavigateUrlInNewBrowserInstance(const unsigned __int16 *a1, __int64 a2, __int128 *a3)
{
  const char *v3; // r9
  int v4; // ebx
  __int128 *v5; // rdi
  DWORD CurrentThreadId; // eax
  DWORD v7; // ecx
  unsigned __int8 v8; // r14
  OLECHAR *v9; // rax
  DWORD dwProcessId; // [rsp+48h] [rbp-69h] BYREF
  struct IEUserBroker *v12; // [rsp+50h] [rbp-61h] BYREF
  BSTR v13; // [rsp+58h] [rbp-59h] BYREF
  __int64 v14; // [rsp+60h] [rbp-51h] BYREF
  BSTR bstrString[2]; // [rsp+68h] [rbp-49h] BYREF
  __int64 v16; // [rsp+78h] [rbp-39h]
  __int128 v17; // [rsp+80h] [rbp-31h] BYREF
  __int64 v18; // [rsp+90h] [rbp-21h]
  BSTR v19[2]; // [rsp+98h] [rbp-19h] BYREF
  __int64 v20; // [rsp+A8h] [rbp-9h]
  BSTR v21[2]; // [rsp+B0h] [rbp-1h] BYREF
  __int64 v22; // [rsp+C0h] [rbp+Fh]
  __int128 v23; // [rsp+C8h] [rbp+17h] BYREF
  __int64 v24; // [rsp+D8h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+110h] [rbp+5Fh]

  if ( (unsigned int)IEConfiguration_GetDWORD(268435501) == 2 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xFE,
      (unsigned int)"onecoreuap\\inetcore\\lib\\nav\\iehelper.cpp",
      v3);
  v4 = -2147467259;
  v5 = a3;
  if ( !IsDualEngineProcess() )
    goto LABEL_25;
  v13 = 0;
  v12 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v4 = CoCreateUserBrokerForThread(CurrentThreadId, &v12);
  if ( v4 < 0 )
    goto LABEL_25;
  dwProcessId = 0;
  (*(void (__fastcall **)(struct IEUserBroker *, _QWORD, _QWORD, DWORD *))(*(_QWORD *)v12 + 24LL))(
    v12,
    0,
    0,
    &dwProcessId);
  v7 = -1;
  if ( dwProcessId )
    v7 = dwProcessId;
  AllowSetForegroundWindow(v7);
  v14 = 0;
  v4 = (*(__int64 (__fastcall **)(struct IEUserBroker *, GUID *, GUID *, __int64 *))(*(_QWORD *)v12 + 48LL))(
         v12,
         &CLSID_CShdocvwBroker,
         &IID_IUnknown,
         &v14);
  if ( v4 >= 0 )
  {
    v4 = (**(__int64 (__fastcall ***)(__int64, GUID *, BSTR *))v14)(v14, &IID_IDualEngineBroker, &v13);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  }
  (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v12 + 16LL))(v12);
  if ( v4 < 0
    || (v4 = (*(__int64 (__fastcall **)(BSTR, const unsigned __int16 *, _QWORD, _QWORD, __int128 *))(*(_QWORD *)v13 + 64LL))(
               v13,
               a1,
               0,
               0,
               a3),
        (*(void (__fastcall **)(BSTR))(*(_QWORD *)v13 + 16LL))(v13),
        v4 < 0) )
  {
LABEL_25:
    if ( (unsigned int)IEConfiguration_GetDWORD(268435501) == 2 || (v8 = 0, !(unsigned int)IsProtectedModeURL(a1, 0)) )
      v8 = 1;
    dwProcessId = 0;
    v13 = 0;
    LCIEGetRedirectionPolicyForURL2(a1, 0, 1, 0x8000u, &dwProcessId, 0, &v13);
    v12 = 0;
    AllowSetForegroundWindow(0xFFFFFFFF);
    if ( (int)CoCreateLocalServerIE(
                (__int64)&GUID_d30c1661_cdaf_11d0_8a3e_00c04fc9e26e,
                (__int64)&v12,
                v8,
                (__int64)v13) >= 0 )
    {
      v16 = 0;
      v22 = 0;
      v20 = 0;
      v18 = 0;
      v24 = 0;
      v17 = 0;
      LOWORD(v17) = 3;
      *(_OWORD *)bstrString = 0;
      LOWORD(bstrString[0]) = 8;
      *(_OWORD *)v21 = 0;
      DWORD2(v17) = 0;
      *(_OWORD *)v19 = 0;
      v23 = 0;
      v9 = SysAllocString(a1);
      bstrString[1] = v9;
      if ( !a3 || (*(_WORD *)a3 & 0x2011) == 0 )
        v5 = &v23;
      if ( v9 )
      {
        (*(void (__fastcall **)(struct IEUserBroker *, __int64))(*(_QWORD *)v12 + 328LL))(v12, 0xFFFFFFFFLL);
        (*(void (__fastcall **)(struct IEUserBroker *, BSTR *, __int128 *, BSTR *, __int128 *, BSTR *))(*(_QWORD *)v12 + 416LL))(
          v12,
          bstrString,
          &v17,
          v19,
          v5,
          v21);
        SysFreeString(bstrString[1]);
      }
      SysFreeString(v19[1]);
      SysFreeString(v21[1]);
      (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v12 + 16LL))(v12);
      v4 = 0;
    }
    SysFreeString(v13);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x181066d58  mov     rax, rsp
0x181066d5b  mov     [rax+20h], r9
0x181066d5f  mov     [rax+18h], r8
0x181066d63  mov     [rax+10h], rdx
0x181066d67  mov     [rax+8], rcx
0x181066d6b  push    rbp
0x181066d6c  push    rbx
0x181066d6d  push    rdi
0x181066d6e  push    r14
0x181066d70  lea     rbp, [rax-5Fh]
0x181066d74  sub     rsp, 0E8h
0x181066d7b  mov     r14d, 1000002Dh
0x181066d81  mov     ecx, r14d
0x181066d84  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x181066d8a  cmp     eax, 2
0x181066d8d  jnz     short loc_181066DA5
0x181066d8f  mov     rcx, [rbp+5Fh]; this
0x181066d93  lea     r8, aOnecoreuapInet_46; "onecoreuap\\inetcore\\lib\\nav\\iehelpe"...
0x181066d9a  mov     edx, 0FEh; void *
0x181066d9f  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x181066da5  mov     ebx, 80004005h
0x181066daa  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x181066db0  mov     rdi, [rbp+57h+arg_10]
0x181066db4  test    al, al
0x181066db6  jz      loc_181066EC2
0x181066dbc  mov     [rbp+57h+var_B0], 0
0x181066dc4  mov     [rbp+57h+var_B8], 0
0x181066dcc  call    cs:__imp_GetCurrentThreadId
0x181066dd2  mov     ecx, eax
0x181066dd4  lea     rdx, [rbp+57h+var_B8]
0x181066dd8  call    cs:__imp_?CoCreateUserBrokerForThread@@YAJKPEAPEAUIEUserBroker@@@Z; CoCreateUserBrokerForThread(ulong,IEUserBroker * *)
0x181066dde  mov     ebx, eax
0x181066de0  test    eax, eax
0x181066de2  js      loc_181066EC2
0x181066de8  mov     rcx, [rbp+57h+var_B8]
0x181066dec  lea     r9, [rbp+57h+dwProcessId]
0x181066df0  mov     [rbp+57h+dwProcessId], 0
0x181066df7  xor     r8d, r8d
0x181066dfa  xor     edx, edx
0x181066dfc  mov     rax, [rcx]
0x181066dff  mov     rax, [rax+18h]
0x181066e03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181066e08  mov     eax, [rbp+57h+dwProcessId]
0x181066e0b  or      ecx, 0FFFFFFFFh
0x181066e0e  test    eax, eax
0x181066e10  cmovnz  ecx, eax; dwProcessId
0x181066e13  call    cs:__imp_AllowSetForegroundWindow
0x181066e19  mov     rcx, [rbp+57h+var_B8]
0x181066e1d  lea     r9, [rbp+57h+var_A8]
0x181066e21  mov     [rbp+57h+var_A8], 0
0x181066e29  lea     r8, IID_IUnknown
0x181066e30  lea     rdx, CLSID_CShdocvwBroker
0x181066e37  mov     rax, [rcx]
0x181066e3a  mov     rax, [rax+30h]
0x181066e3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181066e43  mov     ebx, eax
0x181066e45  test    eax, eax
0x181066e47  js      short loc_181066E75
0x181066e49  mov     rcx, [rbp+57h+var_A8]
0x181066e4d  lea     r8, [rbp+57h+var_B0]
0x181066e51  lea     rdx, IID_IDualEngineBroker
0x181066e58  mov     rax, [rcx]
0x181066e5b  mov     rax, [rax]
0x181066e5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181066e63  mov     rcx, [rbp+57h+var_A8]
0x181066e67  mov     ebx, eax
0x181066e69  mov     rax, [rcx]
0x181066e6c  mov     rax, [rax+10h]
0x181066e70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181066e75  mov     rcx, [rbp+57h+var_B8]
0x181066e79  mov     rax, [rcx]
0x181066e7c  mov     rax, [rax+10h]
0x181066e80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181066e85  test    ebx, ebx
0x181066e87  js      short loc_181066EC2
0x181066e89  mov     rcx, [rbp+57h+var_B0]
0x181066e8d  xor     r9d, r9d
0x181066e90  mov     rdx, [rbp+57h+psz]
0x181066e94  xor     r8d, r8d
0x181066e97  mov     [rsp+100h+var_E0], rdi
0x181066e9c  mov     rax, [rcx]
0x181066e9f  mov     rax, [rax+40h]
0x181066ea3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181066ea8  mov     rcx, [rbp+57h+var_B0]
0x181066eac  mov     ebx, eax
0x181066eae  mov     rax, [rcx]
0x181066eb1  mov     rax, [rax+10h]
0x181066eb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181066eba  test    ebx, ebx
0x181066ebc  jns     loc_181067042
0x181066ec2  mov     ecx, r14d
0x181066ec5  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x181066ecb  cmp     eax, 2
0x181066ece  jz      short loc_181066EE3
0x181066ed0  mov     rcx, [rbp+57h+psz]
0x181066ed4  xor     edx, edx
0x181066ed6  xor     r14b, r14b
0x181066ed9  call    cs:__imp_IsProtectedModeURL
0x181066edf  test    eax, eax
0x181066ee1  jnz     short loc_181066EE6
0x181066ee3  mov     r14b, 1
0x181066ee6  mov     rcx, [rbp+57h+psz]
0x181066eea  lea     rax, [rbp+57h+var_B0]
0x181066eee  mov     [rsp+30h], rax
0x181066ef3  xor     edx, edx
0x181066ef5  lea     rax, [rbp+57h+dwProcessId]
0x181066ef9  mov     [rsp+100h+var_D8], 0
0x181066f02  mov     r9d, 8000h
0x181066f08  mov     [rbp+57h+dwProcessId], 0
0x181066f0f  mov     [rbp+57h+var_B0], 0
0x181066f17  lea     r8d, [rdx+1]
0x181066f1b  mov     [rsp+100h+var_E0], rax
0x181066f20  call    cs:__imp_?LCIEGetRedirectionPolicyForURL2@@YAJPEBGHHKPEAKPEAHPEAPEAG@Z; LCIEGetRedirectionPolicyForURL2(ushort const *,int,int,ulong,ulong *,int *,ushort * *)
0x181066f26  or      ecx, 0FFFFFFFFh; dwProcessId
0x181066f29  mov     [rbp+57h+var_B8], 0
0x181066f31  call    cs:__imp_AllowSetForegroundWindow
0x181066f37  mov     r9, [rbp+57h+var_B0]
0x181066f3b  lea     rdx, [rbp+57h+var_B8]
0x181066f3f  mov     r8b, r14b
0x181066f42  lea     rcx, _GUID_d30c1661_cdaf_11d0_8a3e_00c04fc9e26e
0x181066f49  call    CoCreateLocalServerIE
0x181066f4e  test    eax, eax
0x181066f50  js      loc_181067038
0x181066f56  mov     rcx, [rbp+57h+psz]; psz
0x181066f5a  xor     eax, eax
0x181066f5c  xorps   xmm0, xmm0
0x181066f5f  mov     [rbp+57h+var_90], rax
0x181066f63  mov     [rbp+57h+var_48], rax
0x181066f67  xorps   xmm1, xmm1
0x181066f6a  mov     [rbp+57h+var_60], rax
0x181066f6e  mov     [rbp+57h+var_78], rax
0x181066f72  mov     [rbp+57h+var_30], rax
0x181066f76  mov     eax, 3
0x181066f7b  movups  [rbp+57h+var_88], xmm1
0x181066f7f  mov     word ptr [rbp+57h+var_88], ax
0x181066f83  mov     eax, 8
0x181066f88  movups  xmmword ptr [rbp+57h+bstrString], xmm0
0x181066f8c  mov     word ptr [rbp+57h+bstrString], ax
0x181066f90  movups  xmmword ptr [rbp+57h+var_58], xmm1
0x181066f94  mov     dword ptr [rbp+57h+var_88+8], 0
0x181066f9b  movups  xmmword ptr [rbp+57h+var_70], xmm0
0x181066f9f  movups  [rbp+57h+var_40], xmm0
0x181066fa3  call    cs:__imp_SysAllocString
0x181066fa9  mov     [rbp+57h+bstrString+8], rax
0x181066fad  test    rdi, rdi
0x181066fb0  jz      short loc_181066FBC
0x181066fb2  mov     ecx, 2011h
0x181066fb7  test    [rdi], cx
0x181066fba  jnz     short loc_181066FC0
0x181066fbc  lea     rdi, [rbp+57h+var_40]
0x181066fc0  test    rax, rax
0x181066fc3  jz      short loc_181067012
0x181066fc5  mov     rcx, [rbp+57h+var_B8]
0x181066fc9  or      edx, 0FFFFFFFFh
0x181066fcc  mov     rax, [rcx]
0x181066fcf  mov     rax, [rax+148h]
0x181066fd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181066fdb  mov     rcx, [rbp+57h+var_B8]
0x181066fdf  lea     rdx, [rbp+57h+var_58]
0x181066fe3  mov     [rsp+100h+var_D8], rdx
0x181066fe8  lea     r9, [rbp+57h+var_70]
0x181066fec  lea     r8, [rbp+57h+var_88]
0x181066ff0  mov     [rsp+100h+var_E0], rdi
0x181066ff5  lea     rdx, [rbp+57h+bstrString]
0x181066ff9  mov     rax, [rcx]
0x181066ffc  mov     rax, [rax+1A0h]
0x181067003  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181067008  mov     rcx, [rbp+57h+bstrString+8]; bstrString
0x18106700c  call    cs:__imp_SysFreeString
0x181067012  mov     rcx, [rbp+57h+var_70+8]; bstrString
0x181067016  call    cs:__imp_SysFreeString
0x18106701c  mov     rcx, [rbp+57h+var_58+8]; bstrString
0x181067020  call    cs:__imp_SysFreeString
0x181067026  mov     rcx, [rbp+57h+var_B8]
0x18106702a  mov     rax, [rcx]
0x18106702d  mov     rax, [rax+10h]
0x181067031  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181067036  xor     ebx, ebx
0x181067038  mov     rcx, [rbp+57h+var_B0]; bstrString
0x18106703c  call    cs:__imp_SysFreeString
0x181067042  mov     eax, ebx
0x181067044  add     rsp, 0E8h
0x18106704b  pop     r14
0x18106704d  pop     rdi
0x18106704e  pop     rbx
0x18106704f  pop     rbp
0x181067050  retn
```
