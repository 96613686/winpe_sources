# NetworkInterface::Read(wchar_t const *,tagVARIANT *,IErrorLog *)

- ea: `0x1800d9c40`
- end: `0x1800d9e77`
- name: `?Read@NetworkInterface@@UEAAJPEB_WPEAUtagVARIANT@@PEAUIErrorLog@@@Z`
- size: `567`
- prototype: `int(NetworkInterface *__hidden this, const wchar_t *, struct tagVARIANT *, struct IErrorLog *)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task`

## callees

- `0x1800120a0`
- `0x180012210`
- `0x180015608`
- `0x180015710`
- `0x18004208c`
- `0x1800a88a0`
- `0x1800d9c40`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800d9d31`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800d9d67`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800d9d94`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800d9d31`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800d9d67`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800d9d94`
- `OLEAUT32!__imp_VariantInit` at `0x1800d9d20`
- `OLEAUT32!__imp_VariantInit` at `0x1800d9d20`
- `OLEAUT32!__imp_VariantClear` at `0x1800d9e20`
- `OLEAUT32!__imp_VariantClear` at `0x1800d9e20`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800d9df4`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800d9df4`

## string_xrefs

- `0x1800d9c8f`: `onecore\net\netprofiles\service\src\host\lib\interfacei.cpp`
- `0x1800d9cb3`: `onecore\net\netprofiles\service\src\host\lib\interfacei.cpp`
- `0x1800d9d0a`: `onecore\net\netprofiles\service\src\host\lib\interfacei.cpp`
- `0x1800d9e09`: `onecore\net\netprofiles\service\src\host\lib\interfacei.cpp`
- `0x1800d9e43`: `onecore\net\netprofiles\service\src\host\lib\interfacei.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall NetworkInterface::Read(
        NetworkInterface *this,
        const wchar_t *a2,
        struct tagVARIANT *a3,
        struct IErrorLog *a4)
{
  char *v7; // rdi
  LONG v8; // eax
  VARTYPE v9; // ax
  int v10; // ecx
  VARTYPE vt; // r9
  HRESULT v12; // eax
  int v14; // [rsp+20h] [rbp-C8h]
  VARIANTARG pvarg; // [rsp+38h] [rbp-B0h] BYREF
  __int128 v16; // [rsp+50h] [rbp-98h] BYREF
  __int64 v17; // [rsp+60h] [rbp-88h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  StandbyMonitor::ProcessClientActivity(60);
  if ( !a2 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1F3,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\host\\lib\\interfacei.cpp",
      (const char *)0x80070057LL,
      v14);
  if ( !a3 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1F4,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\host\\lib\\interfacei.cpp",
      (const char *)0x80070057LL,
      v14);
  v16 = 0;
  v17 = 0;
  v7 = (char *)this + 92;
  NetworkPropertyMaps::FindConnectedNetworksByInterface(&v16, v7, 0, 0);
  if ( (_QWORD)v16 == *((_QWORD *)&v16 + 1) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1F8,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\host\\lib\\interfacei.cpp",
      (const char *)0x80070490LL,
      v14);
  VariantInit(&pvarg);
  if ( !(unsigned int)_o__wcsicmp(a2, L"NA_InternetConnectivityV4") )
  {
    v8 = *(_DWORD *)(std::map<_GUID,INTERFACE_DATA>::at(v16 + 112, v7) + 520);
LABEL_9:
    pvarg.lVal = v8;
    v9 = 19;
    goto LABEL_17;
  }
  if ( !(unsigned int)_o__wcsicmp(a2, L"NA_InternetConnectivityV6") )
  {
    v8 = *(_DWORD *)(std::map<_GUID,INTERFACE_DATA>::at(v16 + 112, v7) + 532);
    goto LABEL_9;
  }
  if ( (unsigned int)_o__wcsicmp(a2, L"NA_NetworkClass") )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x217,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\host\\lib\\interfacei.cpp",
      (const char *)0x80070057LL,
      v14);
  v10 = *(_DWORD *)(v16 + 156);
  if ( (v10 & 1) != 0 )
    pvarg.lVal = 3;
  else
    pvarg.lVal = 2 - ((v10 & 2) != 0);
  v9 = 23;
LABEL_17:
  pvarg.vt = v9;
  vt = a3->vt;
  if ( !a3->vt || vt == 13 )
    vt = v9;
  v12 = VariantChangeType(a3, &pvarg, 0, vt);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x21D,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\host\\lib\\interfacei.cpp",
      (const char *)(unsigned int)v12,
      v14);
  VariantClear(&pvarg);
  std::vector<ACTIVE_NETWORK>::_Tidy(&v16);
  return 0;
}

```

## disassembly

```asm
0x1800d9c40  push    rbx
0x1800d9c42  push    rsi
0x1800d9c43  push    rdi
0x1800d9c44  push    r14
0x1800d9c46  sub     rsp, 0C8h
0x1800d9c4d  mov     rax, cs:__security_cookie
0x1800d9c54  xor     rax, rsp
0x1800d9c57  mov     [rsp+0E8h+var_38], rax
0x1800d9c5f  mov     rsi, r8
0x1800d9c62  mov     rbx, rdx
0x1800d9c65  mov     rdi, rcx
0x1800d9c68  mov     [rsp+0E8h+var_B8], rdx
0x1800d9c6d  mov     [rsp+0E8h+var_C0], r9
0x1800d9c72  mov     ecx, 3Ch ; '<'
0x1800d9c77  call    ?ProcessClientActivity@StandbyMonitor@@YAXW4ClientActivity@1@@Z; StandbyMonitor::ProcessClientActivity(StandbyMonitor::ClientActivity)
0x1800d9c7c  mov     rcx, [rsp+0E8h]; this
0x1800d9c84  test    rbx, rbx
0x1800d9c87  jnz     short loc_1800D9CA0
0x1800d9c89  mov     r9d, 80070057h; char *
0x1800d9c8f  lea     r8, aOnecoreNetNetp_13; "onecore\\net\\netprofiles\\service\\src"...
0x1800d9c96  mov     edx, 1F3h; void *
0x1800d9c9b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800d9ca0  mov     rcx, [rsp+0E8h]; this
0x1800d9ca8  test    rsi, rsi
0x1800d9cab  jnz     short loc_1800D9CC4
0x1800d9cad  mov     r9d, 80070057h; char *
0x1800d9cb3  lea     r8, aOnecoreNetNetp_13; "onecore\\net\\netprofiles\\service\\src"...
0x1800d9cba  mov     edx, 1F4h; void *
0x1800d9cbf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800d9cc4  xorps   xmm0, xmm0
0x1800d9cc7  xor     eax, eax
0x1800d9cc9  movups  [rsp+0E8h+var_98], xmm0
0x1800d9cce  mov     [rsp+0E8h+var_88], rax
0x1800d9cd3  add     rdi, 5Ch ; '\'
0x1800d9cd7  xor     r9d, r9d
0x1800d9cda  xor     r8d, r8d
0x1800d9cdd  mov     rdx, rdi
0x1800d9ce0  lea     rcx, [rsp+0E8h+var_98]
0x1800d9ce5  call    ?FindConnectedNetworksByInterface@NetworkPropertyMaps@@SA?AV?$vector@UACTIVE_NETWORK@@V?$allocator@UACTIVE_NETWORK@@@std@@@std@@PEBU_GUID@@_NI@Z; NetworkPropertyMaps::FindConnectedNetworksByInterface(_GUID const *,bool,uint)
0x1800d9cea  nop
0x1800d9ceb  mov     rax, qword ptr [rsp+0E8h+var_98+8]
0x1800d9cf0  cmp     qword ptr [rsp+0E8h+var_98], rax
0x1800d9cf5  setz    al
0x1800d9cf8  mov     rcx, [rsp+0E8h]; this
0x1800d9d00  test    al, al
0x1800d9d02  jz      short loc_1800D9D1B
0x1800d9d04  mov     r9d, 80070490h; char *
0x1800d9d0a  lea     r8, aOnecoreNetNetp_13; "onecore\\net\\netprofiles\\service\\src"...
0x1800d9d11  mov     edx, 1F8h; void *
0x1800d9d16  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800d9d1b  lea     rcx, [rsp+0E8h+pvarg]; pvarg
0x1800d9d20  call    cs:__imp_VariantInit
0x1800d9d26  nop
0x1800d9d27  lea     rdx, aNaInternetconn_0; "NA_InternetConnectivityV4"
0x1800d9d2e  mov     rcx, rbx
0x1800d9d31  call    cs:__imp__o__wcsicmp
0x1800d9d37  test    eax, eax
0x1800d9d39  jnz     short loc_1800D9D5D
0x1800d9d3b  mov     rcx, qword ptr [rsp+0E8h+var_98]
0x1800d9d40  add     rcx, 70h ; 'p'
0x1800d9d44  mov     rdx, rdi
0x1800d9d47  call    ?at@?$map@U_GUID@@UINTERFACE_DATA@@U?$less@U_GUID@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@UINTERFACE_DATA@@@std@@@4@@std@@QEBAAEBUINTERFACE_DATA@@AEBU_GUID@@@Z; std::map<_GUID,INTERFACE_DATA>::at(_GUID const &)
0x1800d9d4c  mov     eax, [rax+208h]
0x1800d9d52  mov     dword ptr [rsp+0E8h+pvarg+8], eax
0x1800d9d56  mov     eax, 13h
0x1800d9d5b  jmp     short loc_1800D9DCF
0x1800d9d5d  lea     rdx, aNaInternetconn; "NA_InternetConnectivityV6"
0x1800d9d64  mov     rcx, rbx
0x1800d9d67  call    cs:__imp__o__wcsicmp
0x1800d9d6d  test    eax, eax
0x1800d9d6f  jnz     short loc_1800D9D8A
0x1800d9d71  mov     rcx, qword ptr [rsp+0E8h+var_98]
0x1800d9d76  add     rcx, 70h ; 'p'
0x1800d9d7a  mov     rdx, rdi
0x1800d9d7d  call    ?at@?$map@U_GUID@@UINTERFACE_DATA@@U?$less@U_GUID@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@UINTERFACE_DATA@@@std@@@4@@std@@QEBAAEBUINTERFACE_DATA@@AEBU_GUID@@@Z; std::map<_GUID,INTERFACE_DATA>::at(_GUID const &)
0x1800d9d82  mov     eax, [rax+214h]
0x1800d9d88  jmp     short loc_1800D9D52
0x1800d9d8a  lea     rdx, aNaNetworkclass; "NA_NetworkClass"
0x1800d9d91  mov     rcx, rbx
0x1800d9d94  call    cs:__imp__o__wcsicmp
0x1800d9d9a  test    eax, eax
0x1800d9d9c  jnz     loc_1800D9E35
0x1800d9da2  mov     rax, qword ptr [rsp+0E8h+var_98]
0x1800d9da7  mov     ecx, [rax+9Ch]
0x1800d9dad  test    cl, 1
0x1800d9db0  jz      short loc_1800D9DBC
0x1800d9db2  mov     dword ptr [rsp+0E8h+pvarg+8], 3
0x1800d9dba  jmp     short loc_1800D9DCA
0x1800d9dbc  and     cl, 2
0x1800d9dbf  neg     cl
0x1800d9dc1  sbb     eax, eax
0x1800d9dc3  add     eax, 2
0x1800d9dc6  mov     dword ptr [rsp+0E8h+pvarg+8], eax
0x1800d9dca  mov     eax, 17h
0x1800d9dcf  mov     word ptr [rsp+0E8h+pvarg], ax
0x1800d9dd4  movzx   r9d, word ptr [rsi]
0x1800d9dd8  test    r9w, r9w
0x1800d9ddc  jz      short loc_1800D9DE5
0x1800d9dde  cmp     r9w, 0Dh
0x1800d9de3  jnz     short loc_1800D9DE9
0x1800d9de5  movzx   r9d, ax; vt
0x1800d9de9  xor     r8d, r8d; wFlags
0x1800d9dec  lea     rdx, [rsp+0E8h+pvarg]; pvarSrc
0x1800d9df1  mov     rcx, rsi; pvargDest
0x1800d9df4  call    cs:__imp_VariantChangeType
0x1800d9dfa  mov     rcx, [rsp+0E8h]; this
0x1800d9e02  test    eax, eax
0x1800d9e04  jns     short loc_1800D9E1B
0x1800d9e06  mov     r9d, eax; char *
0x1800d9e09  lea     r8, aOnecoreNetNetp_13; "onecore\\net\\netprofiles\\service\\src"...
0x1800d9e10  mov     edx, 21Dh; void *
0x1800d9e15  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800d9e1b  lea     rcx, [rsp+0E8h+pvarg]; pvarg
0x1800d9e20  call    cs:__imp_VariantClear
0x1800d9e26  nop
0x1800d9e27  lea     rcx, [rsp+0E8h+var_98]
0x1800d9e2c  call    ?_Tidy@?$vector@UACTIVE_NETWORK@@V?$allocator@UACTIVE_NETWORK@@@std@@@std@@AEAAXXZ; std::vector<ACTIVE_NETWORK>::_Tidy(void)
0x1800d9e31  xor     eax, eax
0x1800d9e33  jmp     short loc_1800D9E59
0x1800d9e35  mov     rcx, [rsp+0E8h]; this
0x1800d9e3d  mov     r9d, 80070057h; char *
0x1800d9e43  lea     r8, aOnecoreNetNetp_13; "onecore\\net\\netprofiles\\service\\src"...
0x1800d9e4a  mov     edx, 217h; void *
0x1800d9e4f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800d9e55  mov     eax, [rsp+0E8h+var_C8]
0x1800d9e59  mov     rcx, [rsp+0E8h+var_38]
0x1800d9e61  xor     rcx, rsp; StackCookie
0x1800d9e64  call    __security_check_cookie
0x1800d9e69  add     rsp, 0C8h
0x1800d9e70  pop     r14
0x1800d9e72  pop     rdi
0x1800d9e73  pop     rsi
0x1800d9e74  pop     rbx
0x1800d9e75  retn
```
