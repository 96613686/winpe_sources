# CRpcIOManagerClient::Bind(_SessionRank,uchar *,uchar *)

- ea: `0x18006cdd0`
- end: `0x18006d2c2`
- name: `?Bind@CRpcIOManagerClient@@UEAAJW4_SessionRank@@PEAE1@Z`
- size: `1266`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180003cf0`
- `0x1800064d0`
- `0x180006cf8`
- `0x18000f674`
- `0x180054968`
- `0x18006cdd0`
- `0x18006d2c8`
- `0x18006d6e0`
- `0x18006e0cc`
- `0x180081dd0`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x18006d275`
- `RPCRT4!RpcBindingFree` at `0x18006d287`
- `RPCRT4!RpcBindingFree` at `0x18006d275`
- `RPCRT4!RpcBindingFree` at `0x18006d287`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18006ceb7`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18006d091`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18006ceb7`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18006d091`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18006d171`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18006d171`
- `RPCRT4!RpcSsDestroyClientContext` at `0x18006cf72`
- `RPCRT4!RpcSsDestroyClientContext` at `0x18006cf72`
- `RPCRT4!RpcStringFreeW` at `0x18006d299`
- `RPCRT4!RpcStringFreeW` at `0x18006d299`

## string_xrefs

- `0x18006ce48`: `com\complus\dtc\dtc\cm\src\iomgrclt.cpp`
- `0x18006cf05`: `com\complus\dtc\dtc\cm\src\iomgrclt.cpp`
- `0x18006cfb2`: `com\complus\dtc\dtc\cm\src\iomgrclt.cpp`
- `0x18006d069`: `com\complus\dtc\dtc\cm\src\iomgrclt.cpp`
- `0x18006d119`: `com\complus\dtc\dtc\cm\src\iomgrclt.cpp`
- `0x18006d1aa`: `com\complus\dtc\dtc\cm\src\iomgrclt.cpp`
- `0x18006d24b`: `com\complus\dtc\dtc\cm\src\iomgrclt.cpp`
- `0x18006d04e`: `[Remote:%s %.8s] SecureBuildContextWrapper call failed. This is usually due to security/network configuration issues.`
- `0x18006d0fd`: `Secure Bind failed for LRPC and falling back to unsecure mode... Setting RPC security again!`
- `0x18006d21d`: `[Remote:%s %.8s] BuildContextWrapper call failed. This is usually due to network configuration issues.`

## pseudocode

```c
__int64 __fastcall CRpcIOManagerClient::Bind(__int64 a1, unsigned int a2, __int64 a3, __int64 a4)
{
  unsigned int v5; // edi
  const wchar_t *v6; // rax
  __int64 v7; // r9
  RPC_STATUS v8; // eax
  CSessionObject **v9; // r13
  RPC_STATUS v10; // eax
  unsigned int v11; // eax
  RPC_STATUS v12; // edi
  unsigned int AuthzSvc[2]; // [rsp+28h] [rbp-D0h]
  unsigned int AuthzSvca[2]; // [rsp+28h] [rbp-D0h]
  int SecurityQOS; // [rsp+30h] [rbp-C8h]
  int SecurityQOSa; // [rsp+30h] [rbp-C8h]
  __int64 v18; // [rsp+38h] [rbp-C0h]
  __int64 v19; // [rsp+40h] [rbp-B8h]
  RPC_WSTR StringBinding; // [rsp+58h] [rbp-A0h] BYREF
  RPC_BINDING_HANDLE v22; // [rsp+60h] [rbp-98h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+68h] [rbp-90h] BYREF
  unsigned int v24; // [rsp+70h] [rbp-88h]
  __int64 v25; // [rsp+78h] [rbp-80h]
  __int64 v26; // [rsp+80h] [rbp-78h]
  __int64 v27; // [rsp+88h] [rbp-70h]
  __int64 v28; // [rsp+90h] [rbp-68h]
  __int64 v29; // [rsp+98h] [rbp-60h]
  __int64 v30; // [rsp+A0h] [rbp-58h]
  RPC_SECURITY_QOS v31; // [rsp+A8h] [rbp-50h] BYREF

  v25 = a4;
  v26 = a3;
  v27 = a1;
  v24 = a2;
  v28 = a3;
  v29 = a4;
  StringBinding = 0;
  Binding = 0;
  v22 = 0;
  v5 = CRpcIOManagerClient::EstablishStringBindingForPartner((CRpcIOManagerClient *)a1, &StringBinding);
  if ( v5 )
  {
    v19 = *(_QWORD *)(a1 + 24);
    v18 = *(_QWORD *)(a1 + 16);
    v6 = L"[Remote:%s %.8s] EstablishStringBindingForPartner call failed";
    v7 = 239;
LABEL_23:
    AuthzSvc[0] = v5;
    TraceStringInline(
      1,
      1,
      L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrclt.cpp",
      v7,
      L"CRpcIOManagerClient::Bind",
      *(_QWORD *)AuthzSvc,
      v6,
      v18,
      v19);
    goto LABEL_24;
  }
  TraceStringInline(
    1,
    5,
    L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrclt.cpp",
    242,
    L"CRpcIOManagerClient::Bind",
    0,
    L"EstablishStringBindingForPartner returned %s",
    StringBinding);
  v8 = RpcBindingFromStringBindingW(StringBinding, &Binding);
  *(_QWORD *)&v31.Version = a1 + 56;
  *(_DWORD *)(a1 + 56) = v8;
  v5 = RpcStatusToHresult(v8);
  if ( !v5 )
  {
    v9 = (CSessionObject **)(a1 + 8);
    v30 = a1 + 8;
    CSessionObject::SetRpcTimer(*(CSessionObject **)(a1 + 8));
    if ( *(_QWORD *)(a1 + 32) )
      RpcSsDestroyClientContext((void **)(a1 + 32));
    v5 = CRpcIOManagerClient::SecureBuildContextWrapper(a1, Binding, a2, v26, v25);
    *(_DWORD *)(a1 + 60) = v5;
    CSessionObject::ResetRpcTimer(*v9);
    if ( !v5 )
      goto LABEL_10;
    AuthzSvca[0] = v5;
    TraceStringInline(
      1,
      1,
      L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrclt.cpp",
      321,
      L"CRpcIOManagerClient::Bind",
      *(_QWORD *)AuthzSvca,
      L"[Remote:%s %.8s] SecureBuildContextWrapper call failed. This is usually due to security/network configuration issues.");
    if ( !*(_DWORD *)(*(_QWORD *)(a1 + 72) + 40LL) )
      goto LABEL_24;
    v10 = RpcBindingFromStringBindingW(StringBinding, &v22);
    **(_DWORD **)&v31.Version = v10;
    v11 = RpcStatusToHresult(v10);
    v5 = v11;
    if ( v11 == -2147024882 || v11 == -2147483277 )
    {
      v7 = 348;
    }
    else
    {
      if ( !v11 )
      {
        if ( *(_DWORD *)(a1 + 48) == 1 )
        {
          TraceStringInline(
            1,
            3,
            L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrclt.cpp",
            368,
            L"CRpcIOManagerClient::Bind",
            0,
            L"Secure Bind failed for LRPC and falling back to unsecure mode... Setting RPC security again!");
          *(_QWORD *)&v31.Version = 1;
          v31.IdentityTracking = 0;
          v31.ImpersonationType = 2;
          v12 = RpcBindingSetAuthInfoExW(v22, 0, 6u, 0xAu, 0, 0, &v31);
          if ( v12 )
          {
            AuthzSvc[0] = v12;
            TraceStringInline(
              1,
              1,
              L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrclt.cpp",
              390,
              L"CRpcIOManagerClient::Bind",
              *(_QWORD *)AuthzSvc,
              L"[Remote:%s %.8s] Call to RpcBindingSetAuthInfoEx failed",
              *(_QWORD *)(a1 + 16),
              *(_QWORD *)(a1 + 24));
            v5 = RpcStatusToHresult(v12);
            goto LABEL_24;
          }
        }
        CSessionObject::SetRpcTimer(*v9);
        v5 = CRpcIOManagerClient::BuildContextWrapper(a1, v22, a2, v26, v25);
        *(_DWORD *)(a1 + 60) = v5;
        CSessionObject::ResetRpcTimer(*v9);
        if ( v5 )
        {
          v19 = *(_QWORD *)(a1 + 24);
          v18 = *(_QWORD *)(a1 + 16);
          v6 = L"[Remote:%s %.8s] BuildContextWrapper call failed. This is usually due to network configuration issues.";
          v7 = 412;
          goto LABEL_23;
        }
LABEL_10:
        *(_DWORD *)(a1 + 40) = 1;
        goto LABEL_24;
      }
      DtcWriteToEventLoggerA(
        1u,
        3u,
        0x4000103Cu,
        0,
        0,
        "Unexpected error received from RpcBindingFromStr...",
        SecurityQOSa);
      v7 = 357;
    }
    v19 = *(_QWORD *)(a1 + 24);
    v18 = *(_QWORD *)(a1 + 16);
    v6 = (const wchar_t *)L"[Remote:%s %.8s] RpcBindingFromStringBindingW call failed";
    goto LABEL_23;
  }
  AuthzSvca[0] = v5;
  TraceStringInline(
    1,
    1,
    L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrclt.cpp",
    264,
    L"CRpcIOManagerClient::Bind",
    *(_QWORD *)AuthzSvca,
    L"[Remote:%s %.8s] RpcBindingFromStringBindingW call failed");
  if ( v5 == -2147024882 || v5 == -2147483277 )
    DtcWriteToEventLoggerA(
      1u,
      3u,
      0x4000103Cu,
      0,
      0,
      "Unexpected error received from RpcBindingFromStr...",
      SecurityQOS);
LABEL_24:
  if ( Binding )
    RpcBindingFree(&Binding);
  if ( v22 )
    RpcBindingFree(&v22);
  if ( StringBinding )
    RpcStringFreeW(&StringBinding);
  return v5;
}

```

## disassembly

```asm
0x18006cdd0  push    rbx
0x18006cdd2  push    rsi
0x18006cdd3  push    rdi
0x18006cdd4  push    r12
0x18006cdd6  push    r13
0x18006cdd8  push    r14
0x18006cdda  sub     rsp, 0C8h
0x18006cde1  mov     rax, cs:__security_cookie
0x18006cde8  xor     rax, rsp
0x18006cdeb  mov     [rsp+0F8h+var_40], rax
0x18006cdf3  mov     [rsp+0F8h+var_80], r9
0x18006cdf8  mov     [rsp+0F8h+var_78], r8
0x18006ce00  mov     [rsp+0F8h+var_A8], edx
0x18006ce04  mov     rbx, rcx
0x18006ce07  mov     [rsp+0F8h+var_70], rcx
0x18006ce0f  mov     [rsp+0F8h+var_88], edx
0x18006ce13  mov     [rsp+0F8h+var_68], r8
0x18006ce1b  mov     [rsp+0F8h+var_60], r9
0x18006ce23  xor     r14d, r14d
0x18006ce26  mov     [rsp+0F8h+StringBinding], r14
0x18006ce2b  mov     [rsp+0F8h+Binding], r14
0x18006ce30  mov     [rsp+0F8h+var_98], r14
0x18006ce35  lea     rdx, [rsp+0F8h+StringBinding]; unsigned __int16 **
0x18006ce3a  call    ?EstablishStringBindingForPartner@CRpcIOManagerClient@@AEAAJPEAPEAG@Z; CRpcIOManagerClient::EstablishStringBindingForPartner(ushort * *)
0x18006ce3f  mov     edi, eax
0x18006ce41  lea     r12, aCrpciomanagerc_11; "CRpcIOManagerClient::Bind"
0x18006ce48  lea     r8, aComComplusDtcD_29; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrc"...
0x18006ce4f  lea     esi, [r14+1]
0x18006ce53  test    eax, eax
0x18006ce55  jz      short loc_18006CE7B
0x18006ce57  mov     rcx, [rbx+18h]
0x18006ce5b  mov     [rsp+0F8h+var_B8], rcx
0x18006ce60  mov     rcx, [rbx+10h]
0x18006ce64  mov     [rsp+0F8h+var_C0], rcx
0x18006ce69  lea     rax, aRemoteS8sEstab; "[Remote:%s %.8s] EstablishStringBinding"...
0x18006ce70  mov     r9d, 0EFh
0x18006ce76  jmp     loc_18006D252
0x18006ce7b  mov     rax, [rsp+0F8h+StringBinding]
0x18006ce80  mov     [rsp+0F8h+var_C0], rax
0x18006ce85  lea     rax, aEstablishstrin; "EstablishStringBindingForPartner return"...
0x18006ce8c  mov     [rsp+0F8h+SecurityQOS], rax
0x18006ce91  mov     qword ptr [rsp+0F8h+AuthzSvc], r14
0x18006ce96  mov     [rsp+0F8h+AuthIdentity], r12
0x18006ce9b  mov     r9d, 0F2h
0x18006cea1  mov     edx, 5
0x18006cea6  mov     ecx, esi
0x18006cea8  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18006cead  lea     rdx, [rsp+0F8h+Binding]; Binding
0x18006ceb2  mov     rcx, [rsp+0F8h+StringBinding]; StringBinding
0x18006ceb7  call    cs:__imp_RpcBindingFromStringBindingW
0x18006cebd  lea     rcx, [rbx+38h]
0x18006cec1  mov     qword ptr [rsp+0F8h+var_50.Version], rcx
0x18006cec9  mov     [rcx], eax
0x18006cecb  mov     ecx, eax; int
0x18006cecd  call    ?RpcStatusToHresult@@YAJJ@Z; RpcStatusToHresult(long)
0x18006ced2  mov     edi, eax
0x18006ced4  test    eax, eax
0x18006ced6  jz      short loc_18006CF53
0x18006ced8  mov     rax, [rbx+18h]
0x18006cedc  mov     [rsp+0F8h+var_B8], rax
0x18006cee1  mov     rax, [rbx+10h]
0x18006cee5  mov     [rsp+0F8h+var_C0], rax
0x18006ceea  lea     rax, aRemoteS8sRpcbi; "[Remote:%s %.8s] RpcBindingFromStringBi"...
0x18006cef1  mov     [rsp+0F8h+SecurityQOS], rax; int
0x18006cef6  mov     [rsp+0F8h+AuthzSvc], edi
0x18006cefa  mov     [rsp+0F8h+AuthIdentity], r12
0x18006ceff  mov     r9d, 108h
0x18006cf05  lea     r8, aComComplusDtcD_29; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrc"...
0x18006cf0c  mov     edx, esi
0x18006cf0e  mov     ecx, esi
0x18006cf10  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18006cf15  cmp     edi, 8007000Eh
0x18006cf1b  jz      short loc_18006CF29
0x18006cf1d  cmp     edi, 80000173h
0x18006cf23  jnz     loc_18006D269
0x18006cf29  lea     rax, aUnexpectedErro_0; "Unexpected error received from RpcBindi"...
0x18006cf30  mov     qword ptr [rsp+0F8h+AuthzSvc], rax; char *
0x18006cf35  mov     [rsp+0F8h+AuthIdentity], r14; void *
0x18006cf3a  xor     r9d, r9d; unsigned int
0x18006cf3d  lea     edx, [r9+3]; unsigned int
0x18006cf41  mov     r8d, 4000103Ch; unsigned int
0x18006cf47  mov     ecx, esi; unsigned int
0x18006cf49  call    ?DtcWriteToEventLoggerA@@YAJKKKKPEAXPEADH@Z; DtcWriteToEventLoggerA(ulong,ulong,ulong,ulong,void *,char *,int)
0x18006cf4e  jmp     loc_18006D269
0x18006cf53  lea     r13, [rbx+8]
0x18006cf57  mov     [rsp+0F8h+var_58], r13
0x18006cf5f  mov     rcx, [r13+0]; this
0x18006cf63  call    ?SetRpcTimer@CSessionObject@@AEAAXXZ; CSessionObject::SetRpcTimer(void)
0x18006cf68  nop
0x18006cf69  lea     rcx, [rbx+20h]; ContextHandle
0x18006cf6d  cmp     [rcx], r14
0x18006cf70  jz      short loc_18006CF78
0x18006cf72  call    cs:__imp_RpcSsDestroyClientContext
0x18006cf78  mov     eax, [rsp+0F8h+var_A8]
0x18006cf7c  mov     rcx, [rsp+0F8h+var_78]
0x18006cf84  mov     rdx, [rsp+0F8h+var_80]
0x18006cf89  jmp     short loc_18006D00A
0x18006cf8b  lea     rax, aExceptionWhile; "EXCEPTION : While destroying the Contex"...
0x18006cf92  mov     [rsp+0F8h+SecurityQOS], rax
0x18006cf97  mov     qword ptr [rsp+0F8h+AuthzSvc], 0
0x18006cfa0  lea     rax, aCrpciomanagerc_11; "CRpcIOManagerClient::Bind"
0x18006cfa7  mov     [rsp+0F8h+AuthIdentity], rax
0x18006cfac  mov     r9d, 12Ah
0x18006cfb2  lea     r8, aComComplusDtcD_29; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrc"...
0x18006cfb9  lea     edx, [r9-3Ah]
0x18006cfbd  mov     ecx, 1
0x18006cfc2  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18006cfc7  xor     r14d, r14d
0x18006cfca  lea     r12, aCrpciomanagerc_11; "CRpcIOManagerClient::Bind"
0x18006cfd1  lea     esi, [r14+1]
0x18006cfd5  mov     rbx, [rsp+0F8h+var_70]
0x18006cfdd  mov     eax, [rsp+0F8h+var_88]
0x18006cfe1  mov     [rsp+0F8h+var_A8], eax
0x18006cfe5  mov     rcx, [rsp+0F8h+var_68]
0x18006cfed  mov     [rsp+0F8h+var_78], rcx
0x18006cff5  mov     rdx, [rsp+0F8h+var_60]
0x18006cffd  mov     [rsp+0F8h+var_80], rdx
0x18006d002  mov     r13, [rsp+0F8h+var_58]
0x18006d00a  mov     [rsp+0F8h+AuthIdentity], rdx
0x18006d00f  mov     r9, rcx
0x18006d012  mov     r8d, eax
0x18006d015  mov     rdx, [rsp+0F8h+Binding]
0x18006d01a  mov     rcx, rbx
0x18006d01d  call    ?SecureBuildContextWrapper@CRpcIOManagerClient@@AEAAJPEAXW4_SessionRank@@PEAE2@Z; CRpcIOManagerClient::SecureBuildContextWrapper(void *,_SessionRank,uchar *,uchar *)
0x18006d022  mov     edi, eax
0x18006d024  mov     [rbx+3Ch], eax
0x18006d027  mov     rcx, [r13+0]; this
0x18006d02b  call    ?ResetRpcTimer@CSessionObject@@AEAAXXZ; CSessionObject::ResetRpcTimer(void)
0x18006d030  test    edi, edi
0x18006d032  jnz     short loc_18006D03C
0x18006d034  mov     [rbx+28h], esi
0x18006d037  jmp     loc_18006D269
0x18006d03c  mov     rax, [rbx+18h]
0x18006d040  mov     [rsp+0F8h+var_B8], rax
0x18006d045  mov     rax, [rbx+10h]
0x18006d049  mov     [rsp+0F8h+var_C0], rax
0x18006d04e  lea     rax, aRemoteS8sSecur; "[Remote:%s %.8s] SecureBuildContextWrap"...
0x18006d055  mov     [rsp+0F8h+SecurityQOS], rax; int
0x18006d05a  mov     [rsp+0F8h+AuthzSvc], edi
0x18006d05e  mov     [rsp+0F8h+AuthIdentity], r12
0x18006d063  mov     r9d, 141h
0x18006d069  lea     r8, aComComplusDtcD_29; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrc"...
0x18006d070  mov     edx, esi
0x18006d072  mov     ecx, esi
0x18006d074  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18006d079  mov     rax, [rbx+48h]
0x18006d07d  cmp     [rax+28h], r14d
0x18006d081  jz      loc_18006D269
0x18006d087  lea     rdx, [rsp+0F8h+var_98]; Binding
0x18006d08c  mov     rcx, [rsp+0F8h+StringBinding]; StringBinding
0x18006d091  call    cs:__imp_RpcBindingFromStringBindingW
0x18006d097  mov     rcx, qword ptr [rsp+0F8h+var_50.Version]
0x18006d09f  mov     [rcx], eax
0x18006d0a1  mov     ecx, eax; int
0x18006d0a3  call    ?RpcStatusToHresult@@YAJJ@Z; RpcStatusToHresult(long)
0x18006d0a8  mov     edi, eax
0x18006d0aa  cmp     eax, 8007000Eh
0x18006d0af  jz      loc_18006D22C
0x18006d0b5  cmp     eax, 80000173h
0x18006d0ba  jz      loc_18006D22C
0x18006d0c0  test    eax, eax
0x18006d0c2  jz      short loc_18006D0F4
0x18006d0c4  lea     rax, aUnexpectedErro_0; "Unexpected error received from RpcBindi"...
0x18006d0cb  mov     qword ptr [rsp+0F8h+AuthzSvc], rax; char *
0x18006d0d0  mov     [rsp+0F8h+AuthIdentity], r14; void *
0x18006d0d5  xor     r9d, r9d; unsigned int
0x18006d0d8  lea     edx, [r9+3]; unsigned int
0x18006d0dc  mov     r8d, 4000103Ch; unsigned int
0x18006d0e2  mov     ecx, esi; unsigned int
0x18006d0e4  call    ?DtcWriteToEventLoggerA@@YAJKKKKPEAXPEADH@Z; DtcWriteToEventLoggerA(ulong,ulong,ulong,ulong,void *,char *,int)
0x18006d0e9  mov     r9d, 165h
0x18006d0ef  jmp     loc_18006D232
0x18006d0f4  cmp     [rbx+30h], esi
0x18006d0f7  jnz     loc_18006D1C8
0x18006d0fd  lea     rax, aSecureBindFail; "Secure Bind failed for LRPC and falling"...
0x18006d104  mov     [rsp+0F8h+SecurityQOS], rax
0x18006d109  mov     qword ptr [rsp+0F8h+AuthzSvc], r14
0x18006d10e  mov     [rsp+0F8h+AuthIdentity], r12
0x18006d113  mov     r9d, 170h
0x18006d119  lea     r8, aComComplusDtcD_29; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrc"...
0x18006d120  mov     edx, 3
0x18006d125  mov     ecx, esi
0x18006d127  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18006d12c  mov     qword ptr [rsp+0F8h+var_50.Version], 1
0x18006d138  mov     [rsp+0F8h+var_50.IdentityTracking], r14d
0x18006d140  mov     [rsp+0F8h+var_50.ImpersonationType], 2
0x18006d14b  lea     rax, [rsp+0F8h+var_50]
0x18006d153  mov     [rsp+0F8h+SecurityQOS], rax; SecurityQOS
0x18006d158  mov     [rsp+0F8h+AuthzSvc], r14d; AuthzSvc
0x18006d15d  mov     [rsp+0F8h+AuthIdentity], r14; AuthIdentity
0x18006d162  xor     edx, edx; ServerPrincName
0x18006d164  lea     r9d, [rdx+0Ah]; AuthnSvc
0x18006d168  lea     r8d, [rdx+6]; AuthnLevel
0x18006d16c  mov     rcx, [rsp+0F8h+var_98]; Binding
0x18006d171  call    cs:__imp_RpcBindingSetAuthInfoExW
0x18006d177  mov     edi, eax
0x18006d179  test    eax, eax
0x18006d17b  jz      short loc_18006D1C8
0x18006d17d  mov     rcx, [rbx+18h]
0x18006d181  mov     [rsp+0F8h+var_B8], rcx
0x18006d186  mov     rcx, [rbx+10h]
0x18006d18a  mov     [rsp+0F8h+var_C0], rcx
0x18006d18f  lea     rax, aRemoteS8sCallT_0; "[Remote:%s %.8s] Call to RpcBindingSetA"...
0x18006d196  mov     [rsp+0F8h+SecurityQOS], rax
0x18006d19b  mov     [rsp+0F8h+AuthzSvc], edi
0x18006d19f  mov     [rsp+0F8h+AuthIdentity], r12
0x18006d1a4  mov     r9d, 186h
0x18006d1aa  lea     r8, aComComplusDtcD_29; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrc"...
0x18006d1b1  mov     edx, esi
0x18006d1b3  mov     ecx, esi
0x18006d1b5  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18006d1ba  mov     ecx, edi; int
0x18006d1bc  call    ?RpcStatusToHresult@@YAJJ@Z; RpcStatusToHresult(long)
0x18006d1c1  mov     edi, eax
0x18006d1c3  jmp     loc_18006D269
0x18006d1c8  mov     rcx, [r13+0]; this
0x18006d1cc  call    ?SetRpcTimer@CSessionObject@@AEAAXXZ; CSessionObject::SetRpcTimer(void)
0x18006d1d1  mov     rax, [rsp+0F8h+var_80]
0x18006d1d6  mov     [rsp+0F8h+AuthIdentity], rax
0x18006d1db  mov     r9, [rsp+0F8h+var_78]
0x18006d1e3  mov     r8d, [rsp+0F8h+var_A8]
0x18006d1e8  mov     rdx, [rsp+0F8h+var_98]
0x18006d1ed  mov     rcx, rbx
0x18006d1f0  call    ?BuildContextWrapper@CRpcIOManagerClient@@AEAAJPEAXW4_SessionRank@@PEAE2@Z; CRpcIOManagerClient::BuildContextWrapper(void *,_SessionRank,uchar *,uchar *)
0x18006d1f5  mov     edi, eax
0x18006d1f7  mov     [rbx+3Ch], eax
0x18006d1fa  mov     rcx, [r13+0]; this
0x18006d1fe  call    ?ResetRpcTimer@CSessionObject@@AEAAXXZ; CSessionObject::ResetRpcTimer(void)
0x18006d203  test    edi, edi
0x18006d205  jz      loc_18006D034
0x18006d20b  mov     rax, [rbx+18h]
0x18006d20f  mov     [rsp+0F8h+var_B8], rax
0x18006d214  mov     rax, [rbx+10h]
0x18006d218  mov     [rsp+0F8h+var_C0], rax
0x18006d21d  lea     rax, aRemoteS8sBuild; "[Remote:%s %.8s] BuildContextWrapper ca"...
0x18006d224  mov     r9d, 19Ch
0x18006d22a  jmp     short loc_18006D24B
0x18006d22c  mov     r9d, 15Ch
0x18006d232  mov     rax, [rbx+18h]
0x18006d236  mov     [rsp+0F8h+var_B8], rax
0x18006d23b  mov     rax, [rbx+10h]
0x18006d23f  mov     [rsp+0F8h+var_C0], rax
0x18006d244  lea     rax, aRemoteS8sRpcbi; "[Remote:%s %.8s] RpcBindingFromStringBi"...
0x18006d24b  lea     r8, aComComplusDtcD_29; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrc"...
0x18006d252  mov     [rsp+0F8h+SecurityQOS], rax
0x18006d257  mov     [rsp+0F8h+AuthzSvc], edi
0x18006d25b  mov     [rsp+0F8h+AuthIdentity], r12
0x18006d260  mov     edx, esi
0x18006d262  mov     ecx, esi
0x18006d264  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18006d269  cmp     [rsp+0F8h+Binding], r14
0x18006d26e  jz      short loc_18006D27B
0x18006d270  lea     rcx, [rsp+0F8h+Binding]; Binding
0x18006d275  call    cs:__imp_RpcBindingFree
0x18006d27b  cmp     [rsp+0F8h+var_98], r14
0x18006d280  jz      short loc_18006D28D
0x18006d282  lea     rcx, [rsp+0F8h+var_98]; Binding
0x18006d287  call    cs:__imp_RpcBindingFree
0x18006d28d  cmp     [rsp+0F8h+StringBinding], r14
0x18006d292  jz      short loc_18006D29F
0x18006d294  lea     rcx, [rsp+0F8h+StringBinding]; String
0x18006d299  call    cs:__imp_RpcStringFreeW
0x18006d29f  mov     eax, edi
0x18006d2a1  mov     rcx, [rsp+0F8h+var_40]
0x18006d2a9  xor     rcx, rsp; StackCookie
0x18006d2ac  call    __security_check_cookie
0x18006d2b1  add     rsp, 0C8h
0x18006d2b8  pop     r14
0x18006d2ba  pop     r13
0x18006d2bc  pop     r12
0x18006d2be  pop     rdi
0x18006d2bf  pop     rsi
0x18006d2c0  pop     rbx
0x18006d2c1  retn
0x18008369c  push    rbp
0x18008369e  sub     rsp, 50h
0x1800836a2  mov     rbp, rdx
0x1800836a5  mov     rcx, [rcx]
0x1800836a8  mov     ecx, [rcx]; ExceptionCode
0x1800836aa  call    cs:__imp_RpcExceptionFilter
0x1800836b0  nop
0x1800836b1  add     rsp, 50h
0x1800836b5  pop     rbp
0x1800836b6  retn
```
