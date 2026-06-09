# CIISApp::InitWamAdm(ushort *)

- ea: `0x180005e50`
- end: `0x180005f98`
- name: `?InitWamAdm@CIISApp@@QEAAJPEAG@Z`
- size: `328`
- prototype: `int __fastcall(CIISApp *this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180005a58`

## callees

- `0x180003efc`
- `0x180005e50`
- `0x1800111e0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180005e95`
- `msvcrt!_wcsicmp` at `0x180005e95`
- `ole32!CoCreateInstanceEx` at `0x180005f23`
- `ole32!CoCreateInstanceEx` at `0x180005f23`

## pseudocode

```c
int __fastcall CIISApp::InitWamAdm(CIISApp *this, unsigned __int16 *a2)
{
  int result; // eax
  IUnknown *pItf; // rcx
  IUnknown *v5; // rcx
  IUnknown *v6; // rcx
  COSERVERINFO pServerInfo; // [rsp+30h] [rbp-29h] BYREF
  MULTI_QI pResults; // [rsp+50h] [rbp-9h] BYREF
  GUID *v9; // [rsp+68h] [rbp+Fh]
  IUnknown *pProxy; // [rsp+70h] [rbp+17h]
  int v11; // [rsp+78h] [rbp+1Fh]
  GUID *v12; // [rsp+80h] [rbp+27h]
  IUnknown *v13; // [rsp+88h] [rbp+2Fh]
  int v14; // [rsp+90h] [rbp+37h]

  memset(&pServerInfo, 0, sizeof(pServerInfo));
  if ( !a2 || (pServerInfo.pwszName = a2, !_wcsicmp(a2, L"localhost")) )
    pServerInfo.pwszName = 0;
  pServerInfo.pAuthInfo = 0;
  pResults.pIID = &IID_IWamAdmin;
  pResults.hr = 0;
  v9 = &IID_IWamAdmin2;
  pResults.pItf = 0;
  v12 = &IID_IIISApplicationAdmin;
  v11 = 0;
  pProxy = 0;
  v14 = 0;
  v13 = 0;
  result = CoCreateInstanceEx(&CLSID_WamAdmin, 0, 0x15u, &pServerInfo, 3u, &pResults);
  if ( result >= 0 )
  {
    if ( pResults.hr < 0
      || (pItf = pResults.pItf,
          *((_QWORD *)this + 16) = pResults.pItf,
          result = SetProxyImpersonationLevel(pItf),
          result >= 0) )
    {
      if ( v11 < 0
        || (v5 = pProxy, *((_QWORD *)this + 17) = pProxy, result = SetProxyImpersonationLevel(v5), result >= 0) )
      {
        if ( v14 >= 0 )
        {
          v6 = v13;
          *((_QWORD *)this + 18) = v13;
          return SetProxyImpersonationLevel(v6);
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180005e50  mov     [rsp-8+arg_10], rbx
0x180005e55  mov     [rsp-8+arg_18], rdi
0x180005e5a  push    rbp
0x180005e5b  lea     rbp, [rsp-57h]
0x180005e60  sub     rsp, 0B0h
0x180005e67  mov     rax, cs:__security_cookie
0x180005e6e  xor     rax, rsp
0x180005e71  mov     [rbp+57h+var_10], rax
0x180005e75  xorps   xmm0, xmm0
0x180005e78  mov     rbx, rdx
0x180005e7b  mov     rdi, rcx
0x180005e7e  movups  xmmword ptr [rbp+57h+pServerInfo.dwReserved1], xmm0
0x180005e82  movups  xmmword ptr [rbp+57h+pServerInfo.pAuthInfo], xmm0
0x180005e86  test    rdx, rdx
0x180005e89  jz      short loc_180005EA3
0x180005e8b  lea     rdx, aLocalhost; "localhost"
0x180005e92  mov     rcx, rbx; String1
0x180005e95  call    cs:__imp__wcsicmp
0x180005e9b  mov     [rbp+57h+pServerInfo.pwszName], rbx
0x180005e9f  test    eax, eax
0x180005ea1  jnz     short loc_180005EAB
0x180005ea3  mov     [rbp+57h+pServerInfo.pwszName], 0
0x180005eab  lea     rax, IID_IWamAdmin
0x180005eb2  mov     [rbp+57h+pServerInfo.pAuthInfo], 0
0x180005eba  mov     [rbp+57h+var_60.pIID], rax
0x180005ebe  lea     r9, [rbp+57h+pServerInfo]; pServerInfo
0x180005ec2  lea     rax, IID_IWamAdmin2
0x180005ec9  mov     [rbp+57h+var_60.hr], 0
0x180005ed0  mov     [rbp+57h+var_48], rax
0x180005ed4  lea     rcx, CLSID_WamAdmin; Clsid
0x180005edb  lea     rax, IID_IIISApplicationAdmin
0x180005ee2  mov     [rbp+57h+var_60.pItf], 0
0x180005eea  xor     edx, edx; punkOuter
0x180005eec  mov     [rbp+57h+var_30], rax
0x180005ef0  lea     rax, [rbp+57h+var_60]
0x180005ef4  mov     [rbp+57h+var_38], 0
0x180005efb  mov     [rsp+0B0h+pResults], rax; pResults
0x180005f00  mov     [rsp+0B0h+dwCount], 3; dwCount
0x180005f08  lea     r8d, [rdx+15h]; dwClsCtx
0x180005f0c  mov     [rbp+57h+pProxy], 0
0x180005f14  mov     [rbp+57h+var_20], 0
0x180005f1b  mov     [rbp+57h+var_28], 0
0x180005f23  call    cs:__imp_CoCreateInstanceEx
0x180005f29  test    eax, eax
0x180005f2b  js      short loc_180005F77
0x180005f2d  cmp     [rbp+57h+var_60.hr], 0
0x180005f31  jl      short loc_180005F47
0x180005f33  mov     rcx, [rbp+57h+var_60.pItf]; pProxy
0x180005f37  mov     [rdi+80h], rcx
0x180005f3e  call    ?SetProxyImpersonationLevel@@YAJPEAUIUnknown@@K@Z; SetProxyImpersonationLevel(IUnknown *,ulong)
0x180005f43  test    eax, eax
0x180005f45  js      short loc_180005F77
0x180005f47  cmp     [rbp+57h+var_38], 0
0x180005f4b  jl      short loc_180005F61
0x180005f4d  mov     rcx, [rbp+57h+pProxy]; pProxy
0x180005f51  mov     [rdi+88h], rcx
0x180005f58  call    ?SetProxyImpersonationLevel@@YAJPEAUIUnknown@@K@Z; SetProxyImpersonationLevel(IUnknown *,ulong)
0x180005f5d  test    eax, eax
0x180005f5f  js      short loc_180005F77
0x180005f61  cmp     [rbp+57h+var_20], 0
0x180005f65  jl      short loc_180005F77
0x180005f67  mov     rcx, [rbp+57h+var_28]; pProxy
0x180005f6b  mov     [rdi+90h], rcx
0x180005f72  call    ?SetProxyImpersonationLevel@@YAJPEAUIUnknown@@K@Z; SetProxyImpersonationLevel(IUnknown *,ulong)
0x180005f77  mov     rcx, [rbp+57h+var_10]
0x180005f7b  xor     rcx, rsp; StackCookie
0x180005f7e  call    __security_check_cookie
0x180005f83  lea     r11, [rsp+0B0h+var_s0]
0x180005f8b  mov     rbx, [r11+20h]
0x180005f8f  mov     rdi, [r11+28h]
0x180005f93  mov     rsp, r11
0x180005f96  pop     rbp
0x180005f97  retn
```
