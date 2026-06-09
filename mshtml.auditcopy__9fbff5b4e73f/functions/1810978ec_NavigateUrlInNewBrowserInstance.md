# NavigateUrlInNewBrowserInstance

- ea: `0x1810978ec`
- end: `0x181097c3a`
- name: `NavigateUrlInNewBrowserInstance`
- size: `846`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18084789c`

## callees

- `0x180842d84`
- `0x181097620`
- `0x1810978ec`
- `0x181104010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18109796c`
- `KERNEL32!GetCurrentThreadId` at `0x18109796c`
- `USER32!AllowSetForegroundWindow` at `0x1810979bf`
- `USER32!AllowSetForegroundWindow` at `0x181097af5`
- `USER32!AllowSetForegroundWindow` at `0x1810979bf`
- `USER32!AllowSetForegroundWindow` at `0x181097af5`
- `iertutil!__imp_?CoCreateUserBrokerForThread@@YAJKPEAPEAUIEUserBroker@@@Z` at `0x18109797e`
- `iertutil!__imp_?CoCreateUserBrokerForThread@@YAJKPEAPEAUIEUserBroker@@@Z` at `0x18109797e`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x181097918`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x181097a77`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x181097918`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x181097a77`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x181097944`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x181097944`
- `urlmon!__imp_IsProtectedModeURL` at `0x181097a91`
- `urlmon!__imp_IsProtectedModeURL` at `0x181097a91`
- `urlmon!__imp_?LCIEGetRedirectionPolicyForURL2@@YAJPEBGHHKPEAKPEAHPEAPEAG@Z` at `0x181097ade`
- `urlmon!__imp_?LCIEGetRedirectionPolicyForURL2@@YAJPEBGHHKPEAKPEAHPEAPEAG@Z` at `0x181097ade`
- `OLEAUT32!__imp_SysAllocString` at `0x181097b6d`
- `OLEAUT32!__imp_SysAllocString` at `0x181097b6d`
- `OLEAUT32!__imp_SysFreeString` at `0x181097bdc`
- `OLEAUT32!__imp_SysFreeString` at `0x181097bec`
- `OLEAUT32!__imp_SysFreeString` at `0x181097bfc`
- `OLEAUT32!__imp_SysFreeString` at `0x181097c1e`
- `OLEAUT32!__imp_SysFreeString` at `0x181097bdc`
- `OLEAUT32!__imp_SysFreeString` at `0x181097bec`
- `OLEAUT32!__imp_SysFreeString` at `0x181097bfc`
- `OLEAUT32!__imp_SysFreeString` at `0x181097c1e`

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
      254,
      (__int64)"onecoreuap\\inetcore\\lib\\nav\\iehelper.cpp",
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
0x1810978ec  mov     rax, rsp
0x1810978ef  mov     [rax+20h], r9
0x1810978f3  mov     [rax+18h], r8
0x1810978f7  mov     [rax+10h], rdx
0x1810978fb  mov     [rax+8], rcx
0x1810978ff  push    rbp
0x181097900  push    rbx
0x181097901  push    rdi
0x181097902  push    r14
0x181097904  lea     rbp, [rax-5Fh]
0x181097908  sub     rsp, 0E8h
0x18109790f  mov     r14d, 1000002Dh
0x181097915  mov     ecx, r14d
0x181097918  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x18109791f  nop     dword ptr [rax+rax+00h]
0x181097924  cmp     eax, 2
0x181097927  jnz     short loc_18109793F
0x181097929  mov     rcx, [rbp+5Fh]; this
0x18109792d  lea     r8, aOnecoreuapInet_46; "onecoreuap\\inetcore\\lib\\nav\\iehelpe"...
0x181097934  mov     edx, 0FEh; void *
0x181097939  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18109793f  mov     ebx, 80004005h
0x181097944  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x18109794b  nop     dword ptr [rax+rax+00h]
0x181097950  mov     rdi, [rbp+57h+arg_10]
0x181097954  test    al, al
0x181097956  jz      loc_181097A74
0x18109795c  mov     [rbp+57h+var_B0], 0
0x181097964  mov     [rbp+57h+var_B8], 0
0x18109796c  call    cs:__imp_GetCurrentThreadId
0x181097973  nop     dword ptr [rax+rax+00h]
0x181097978  mov     ecx, eax
0x18109797a  lea     rdx, [rbp+57h+var_B8]
0x18109797e  call    cs:__imp_?CoCreateUserBrokerForThread@@YAJKPEAPEAUIEUserBroker@@@Z; CoCreateUserBrokerForThread(ulong,IEUserBroker * *)
0x181097985  nop     dword ptr [rax+rax+00h]
0x18109798a  mov     ebx, eax
0x18109798c  test    eax, eax
0x18109798e  js      loc_181097A74
0x181097994  mov     rcx, [rbp+57h+var_B8]
0x181097998  lea     r9, [rbp+57h+dwProcessId]
0x18109799c  mov     [rbp+57h+dwProcessId], 0
0x1810979a3  xor     r8d, r8d
0x1810979a6  xor     edx, edx
0x1810979a8  mov     rax, [rcx]
0x1810979ab  mov     rax, [rax+18h]
0x1810979af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1810979b4  mov     eax, [rbp+57h+dwProcessId]
0x1810979b7  or      ecx, 0FFFFFFFFh
0x1810979ba  test    eax, eax
0x1810979bc  cmovnz  ecx, eax; dwProcessId
0x1810979bf  call    cs:__imp_AllowSetForegroundWindow
0x1810979c6  nop     dword ptr [rax+rax+00h]
0x1810979cb  mov     rcx, [rbp+57h+var_B8]
0x1810979cf  lea     r9, [rbp+57h+var_A8]
0x1810979d3  mov     [rbp+57h+var_A8], 0
0x1810979db  lea     r8, IID_IUnknown
0x1810979e2  lea     rdx, CLSID_CShdocvwBroker
0x1810979e9  mov     rax, [rcx]
0x1810979ec  mov     rax, [rax+30h]
0x1810979f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1810979f5  mov     ebx, eax
0x1810979f7  test    eax, eax
0x1810979f9  js      short loc_181097A27
0x1810979fb  mov     rcx, [rbp+57h+var_A8]
0x1810979ff  lea     r8, [rbp+57h+var_B0]
0x181097a03  lea     rdx, IID_IDualEngineBroker
0x181097a0a  mov     rax, [rcx]
0x181097a0d  mov     rax, [rax]
0x181097a10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181097a15  mov     rcx, [rbp+57h+var_A8]
0x181097a19  mov     ebx, eax
0x181097a1b  mov     rax, [rcx]
0x181097a1e  mov     rax, [rax+10h]
0x181097a22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181097a27  mov     rcx, [rbp+57h+var_B8]
0x181097a2b  mov     rax, [rcx]
0x181097a2e  mov     rax, [rax+10h]
0x181097a32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181097a37  test    ebx, ebx
0x181097a39  js      short loc_181097A74
0x181097a3b  mov     rcx, [rbp+57h+var_B0]
0x181097a3f  xor     r9d, r9d
0x181097a42  mov     rdx, [rbp+57h+psz]
0x181097a46  xor     r8d, r8d
0x181097a49  mov     [rsp+100h+var_E0], rdi
0x181097a4e  mov     rax, [rcx]
0x181097a51  mov     rax, [rax+40h]
0x181097a55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181097a5a  mov     rcx, [rbp+57h+var_B0]
0x181097a5e  mov     ebx, eax
0x181097a60  mov     rax, [rcx]
0x181097a63  mov     rax, [rax+10h]
0x181097a67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181097a6c  test    ebx, ebx
0x181097a6e  jns     loc_181097C2A
0x181097a74  mov     ecx, r14d
0x181097a77  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x181097a7e  nop     dword ptr [rax+rax+00h]
0x181097a83  cmp     eax, 2
0x181097a86  jz      short loc_181097AA1
0x181097a88  mov     rcx, [rbp+57h+psz]
0x181097a8c  xor     edx, edx
0x181097a8e  xor     r14b, r14b
0x181097a91  call    cs:__imp_IsProtectedModeURL
0x181097a98  nop     dword ptr [rax+rax+00h]
0x181097a9d  test    eax, eax
0x181097a9f  jnz     short loc_181097AA4
0x181097aa1  mov     r14b, 1
0x181097aa4  mov     rcx, [rbp+57h+psz]
0x181097aa8  lea     rax, [rbp+57h+var_B0]
0x181097aac  mov     [rsp+30h], rax
0x181097ab1  xor     edx, edx
0x181097ab3  lea     rax, [rbp+57h+dwProcessId]
0x181097ab7  mov     [rsp+100h+var_D8], 0
0x181097ac0  mov     r9d, 8000h
0x181097ac6  mov     [rbp+57h+dwProcessId], 0
0x181097acd  mov     [rbp+57h+var_B0], 0
0x181097ad5  lea     r8d, [rdx+1]
0x181097ad9  mov     [rsp+100h+var_E0], rax
0x181097ade  call    cs:__imp_?LCIEGetRedirectionPolicyForURL2@@YAJPEBGHHKPEAKPEAHPEAPEAG@Z; LCIEGetRedirectionPolicyForURL2(ushort const *,int,int,ulong,ulong *,int *,ushort * *)
0x181097ae5  nop     dword ptr [rax+rax+00h]
0x181097aea  or      ecx, 0FFFFFFFFh; dwProcessId
0x181097aed  mov     [rbp+57h+var_B8], 0
0x181097af5  call    cs:__imp_AllowSetForegroundWindow
0x181097afc  nop     dword ptr [rax+rax+00h]
0x181097b01  mov     r9, [rbp+57h+var_B0]
0x181097b05  lea     rdx, [rbp+57h+var_B8]
0x181097b09  mov     r8b, r14b
0x181097b0c  lea     rcx, _GUID_d30c1661_cdaf_11d0_8a3e_00c04fc9e26e
0x181097b13  call    CoCreateLocalServerIE
0x181097b18  test    eax, eax
0x181097b1a  js      loc_181097C1A
0x181097b20  mov     rcx, [rbp+57h+psz]; psz
0x181097b24  xor     eax, eax
0x181097b26  xorps   xmm0, xmm0
0x181097b29  mov     [rbp+57h+var_90], rax
0x181097b2d  mov     [rbp+57h+var_48], rax
0x181097b31  xorps   xmm1, xmm1
0x181097b34  mov     [rbp+57h+var_60], rax
0x181097b38  mov     [rbp+57h+var_78], rax
0x181097b3c  mov     [rbp+57h+var_30], rax
0x181097b40  mov     eax, 3
0x181097b45  movups  [rbp+57h+var_88], xmm1
0x181097b49  mov     word ptr [rbp+57h+var_88], ax
0x181097b4d  mov     eax, 8
0x181097b52  movups  xmmword ptr [rbp+57h+bstrString], xmm0
0x181097b56  mov     word ptr [rbp+57h+bstrString], ax
0x181097b5a  movups  xmmword ptr [rbp+57h+var_58], xmm1
0x181097b5e  mov     dword ptr [rbp+57h+var_88+8], 0
0x181097b65  movups  xmmword ptr [rbp+57h+var_70], xmm0
0x181097b69  movups  [rbp+57h+var_40], xmm0
0x181097b6d  call    cs:__imp_SysAllocString
0x181097b74  nop     dword ptr [rax+rax+00h]
0x181097b79  mov     [rbp+57h+bstrString+8], rax
0x181097b7d  test    rdi, rdi
0x181097b80  jz      short loc_181097B8C
0x181097b82  mov     ecx, 2011h
0x181097b87  test    [rdi], cx
0x181097b8a  jnz     short loc_181097B90
0x181097b8c  lea     rdi, [rbp+57h+var_40]
0x181097b90  test    rax, rax
0x181097b93  jz      short loc_181097BE8
0x181097b95  mov     rcx, [rbp+57h+var_B8]
0x181097b99  or      edx, 0FFFFFFFFh
0x181097b9c  mov     rax, [rcx]
0x181097b9f  mov     rax, [rax+148h]
0x181097ba6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181097bab  mov     rcx, [rbp+57h+var_B8]
0x181097baf  lea     rdx, [rbp+57h+var_58]
0x181097bb3  mov     [rsp+100h+var_D8], rdx
0x181097bb8  lea     r9, [rbp+57h+var_70]
0x181097bbc  lea     r8, [rbp+57h+var_88]
0x181097bc0  mov     [rsp+100h+var_E0], rdi
0x181097bc5  lea     rdx, [rbp+57h+bstrString]
0x181097bc9  mov     rax, [rcx]
0x181097bcc  mov     rax, [rax+1A0h]
0x181097bd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181097bd8  mov     rcx, [rbp+57h+bstrString+8]; bstrString
0x181097bdc  call    cs:__imp_SysFreeString
0x181097be3  nop     dword ptr [rax+rax+00h]
0x181097be8  mov     rcx, [rbp+57h+var_70+8]; bstrString
0x181097bec  call    cs:__imp_SysFreeString
0x181097bf3  nop     dword ptr [rax+rax+00h]
0x181097bf8  mov     rcx, [rbp+57h+var_58+8]; bstrString
0x181097bfc  call    cs:__imp_SysFreeString
0x181097c03  nop     dword ptr [rax+rax+00h]
0x181097c08  mov     rcx, [rbp+57h+var_B8]
0x181097c0c  mov     rax, [rcx]
0x181097c0f  mov     rax, [rax+10h]
0x181097c13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181097c18  xor     ebx, ebx
0x181097c1a  mov     rcx, [rbp+57h+var_B0]; bstrString
0x181097c1e  call    cs:__imp_SysFreeString
0x181097c25  nop     dword ptr [rax+rax+00h]
0x181097c2a  mov     eax, ebx
0x181097c2c  add     rsp, 0E8h
0x181097c33  pop     r14
0x181097c35  pop     rdi
0x181097c36  pop     rbx
0x181097c37  pop     rbp
0x181097c38  retn
```
