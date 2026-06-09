# RadiusProxy::getLocalIpAddress(ushort *)

- ea: `0x18001e6c4`
- end: `0x18001e990`
- name: `?getLocalIpAddress@RadiusProxy@@IEAAXPEAG@Z`
- size: `716`
- prototype: `void(RadiusProxy *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x18001dad0`

## callees

- `0x180009540`
- `0x18000dc54`
- `0x1800160b4`
- `0x18001d31c`
- `0x18001e6c4`
- `0x18001ed6c`

## import_xrefs

- `iassvcs!IASReportEvent` at `0x18001e96a`
- `iassvcs!IASReportEvent` at `0x18001e96a`
- `ADVAPI32!RegQueryValueExW` at `0x18001e7c5`
- `ADVAPI32!RegQueryValueExW` at `0x18001e8ef`
- `ADVAPI32!RegQueryValueExW` at `0x18001e7c5`
- `ADVAPI32!RegQueryValueExW` at `0x18001e8ef`
- `ADVAPI32!RegOpenKeyExW` at `0x18001e721`
- `ADVAPI32!RegOpenKeyExW` at `0x18001e721`
- `ADVAPI32!RegCloseKey` at `0x18001e97e`
- `ADVAPI32!RegCloseKey` at `0x18001e97e`

## string_xrefs

- `0x18001e75e`: `RadiusProxy::getLocalIpAddress RegOpenKeyEx(%S) Failed: 0x%x\n`
- `0x18001e6ec`: `System\CurrentControlSet\Services\RemoteAccess\Policy`

## pseudocode

```c
void __fastcall RadiusProxy::getLocalIpAddress(RadiusProxy *this, BYTE *a2)
{
  LSTATUS v3; // eax
  char v4; // di
  LSTATUS v5; // eax
  char v6; // di
  LSTATUS v7; // eax
  RadiusProxy *v8; // rcx
  DWORD cbData; // [rsp+70h] [rbp+30h] BYREF
  int v10; // [rsp+74h] [rbp+34h]
  DWORD Type; // [rsp+78h] [rbp+38h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+40h] BYREF
  BYTE *v13; // [rsp+88h] [rbp+48h] BYREF

  if ( a2 )
  {
    v10 = HIDWORD(this);
    Type = 1;
    *(_WORD *)a2 = 0;
    cbData = 0;
    hKey = 0;
    v3 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"System\\CurrentControlSet\\Services\\RemoteAccess\\Policy",
           0,
           0x20019u,
           &hKey);
    v4 = v3;
    if ( v3 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      {
        WppDbgPrint("RadiusProxy::getLocalIpAddress RegOpenKeyEx(%S) Failed: 0x%x\n");
        WPP_SF_sSD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17,
          (unsigned int)&WPP_71998f247ae0370d2143b01685e48c0c_Traceguids,
          (unsigned int)"NPSRAD",
          (__int64)L"System\\CurrentControlSet\\Services\\RemoteAccess\\Policy",
          v4);
      }
      goto LABEL_27;
    }
    v5 = RegQueryValueExW(hKey, L"LocalIpAddress", 0, &Type, 0, &cbData);
    v6 = v5;
    if ( v5 )
    {
      if ( v5 == 2
        || WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
      {
        goto LABEL_27;
      }
    }
    else
    {
      if ( !cbData )
        goto LABEL_27;
      if ( cbData > 0x82 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
        {
          WppDbgPrint("RadiusProxy::getLocalIpAddress ValueSize is greater than 64 wchars, %d");
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            19,
            (unsigned int)&WPP_71998f247ae0370d2143b01685e48c0c_Traceguids,
            (unsigned int)"NPSRAD",
            cbData);
        }
        goto LABEL_27;
      }
      v7 = RegQueryValueExW(hKey, L"LocalIpAddress", 0, &Type, a2, &cbData);
      v6 = v7;
      if ( !v7 )
      {
        if ( !RadiusProxy::isIPValid(v8, (unsigned __int16 *)a2) )
        {
          v13 = a2;
          IASReportEvent(2147488065LL, 1, 0, &v13, 0);
          *(_WORD *)a2 = 0;
        }
        goto LABEL_27;
      }
      if ( v7 == 2
        || WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
      {
LABEL_27:
        if ( hKey )
          RegCloseKey(hKey);
        return;
      }
    }
    WppDbgPrint("RadiusProxy::getLocalIpAddress RegQueryValueEx(%S\\%S) failed with 0x%x");
    WPP_SF_sSSD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (__int64)L"System\\CurrentControlSet\\Services\\RemoteAccess\\Policy",
      (__int64)L"LocalIpAddress",
      v6);
    goto LABEL_27;
  }
}

```

## disassembly

```asm
0x18001e6c4  test    rdx, rdx
0x18001e6c7  jz      locret_18001E98F
0x18001e6cd  mov     qword ptr [rsp-28h+cbData], rcx
0x18001e6d2  push    rbp
0x18001e6d3  push    rbx
0x18001e6d4  push    rdi
0x18001e6d5  push    r12
0x18001e6d7  push    r15
0x18001e6d9  mov     rbp, rsp
0x18001e6dc  sub     rsp, 40h
0x18001e6e0  xor     eax, eax
0x18001e6e2  mov     [rbp+Type], 1
0x18001e6e9  mov     [rdx], ax
0x18001e6ec  lea     r15, ?pwszRegKeyPath@RadiusProxy@@1QBGB; "System\\CurrentControlSet\\Services\\Re"...
0x18001e6f3  lea     rax, [rbp+hKey]
0x18001e6f7  mov     [rbp+cbData], 0
0x18001e6fe  mov     rbx, rdx
0x18001e701  mov     [rsp+40h+phkResult], rax; phkResult
0x18001e706  mov     r9d, 20019h; samDesired
0x18001e70c  mov     [rbp+hKey], 0
0x18001e714  xor     r8d, r8d; ulOptions
0x18001e717  mov     rdx, r15; lpSubKey
0x18001e71a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001e721  call    cs:__imp_RegOpenKeyExW
0x18001e727  mov     edi, eax
0x18001e729  test    eax, eax
0x18001e72b  jz      short loc_18001E79E
0x18001e72d  mov     rdx, cs:WPP_GLOBAL_Control
0x18001e734  lea     rcx, WPP_GLOBAL_Control
0x18001e73b  cmp     rdx, rcx
0x18001e73e  jz      loc_18001E975
0x18001e744  cmp     byte ptr [rdx+19h], 2
0x18001e748  jb      loc_18001E975
0x18001e74e  test    dword ptr [rdx+1Ch], 100h
0x18001e755  jz      loc_18001E975
0x18001e75b  mov     r8d, eax
0x18001e75e  lea     rcx, aRadiusproxyGet; "RadiusProxy::getLocalIpAddress RegOpenK"...
0x18001e765  mov     rdx, r15
0x18001e768  call    WppDbgPrint
0x18001e76d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e774  lea     r9, aNpsrad; "NPSRAD"
0x18001e77b  mov     edx, 11h
0x18001e780  mov     dword ptr [rsp+40h+lpcbData], edi
0x18001e784  lea     r8, WPP_71998f247ae0370d2143b01685e48c0c_Traceguids
0x18001e78b  mov     [rsp+40h+phkResult], r15
0x18001e790  mov     rcx, [rcx+10h]
0x18001e794  call    WPP_SF_sSD
0x18001e799  jmp     loc_18001E975
0x18001e79e  mov     rcx, [rbp+hKey]; hKey
0x18001e7a2  lea     rax, [rbp+cbData]
0x18001e7a6  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18001e7ab  lea     r12, ?pwszLocalIpAddressValueName@RadiusProxy@@1QBGB; "LocalIpAddress"
0x18001e7b2  mov     rdx, r12; lpValueName
0x18001e7b5  mov     [rsp+40h+phkResult], 0; lpData
0x18001e7be  lea     r9, [rbp+Type]; lpType
0x18001e7c2  xor     r8d, r8d; lpReserved
0x18001e7c5  call    cs:__imp_RegQueryValueExW
0x18001e7cb  mov     edi, eax
0x18001e7cd  test    eax, eax
0x18001e7cf  jz      loc_18001E857
0x18001e7d5  cmp     eax, 2
0x18001e7d8  jz      loc_18001E975
0x18001e7de  mov     rdx, cs:WPP_GLOBAL_Control
0x18001e7e5  lea     rcx, WPP_GLOBAL_Control
0x18001e7ec  cmp     rdx, rcx
0x18001e7ef  jz      loc_18001E975
0x18001e7f5  cmp     byte ptr [rdx+19h], 2
0x18001e7f9  jb      loc_18001E975
0x18001e7ff  test    dword ptr [rdx+1Ch], 100h
0x18001e806  jz      loc_18001E975
0x18001e80c  mov     r9d, eax
0x18001e80f  lea     rcx, aRadiusproxyGet_3; "RadiusProxy::getLocalIpAddress RegQuery"...
0x18001e816  mov     r8, r12
0x18001e819  mov     rdx, r15
0x18001e81c  call    WppDbgPrint
0x18001e821  mov     edx, 12h
0x18001e826  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e82d  lea     r9, aNpsrad; "NPSRAD"
0x18001e834  mov     dword ptr [rsp+40h+var_10], edi; char
0x18001e838  lea     r8, WPP_71998f247ae0370d2143b01685e48c0c_Traceguids
0x18001e83f  mov     [rsp+40h+lpcbData], r12; __int64
0x18001e844  mov     [rsp+40h+phkResult], r15; __int64
0x18001e849  mov     rcx, [rcx+10h]; LoggerHandle
0x18001e84d  call    WPP_SF_sSSD
0x18001e852  jmp     loc_18001E975
0x18001e857  mov     edx, [rbp+cbData]
0x18001e85a  test    edx, edx
0x18001e85c  jz      loc_18001E975
0x18001e862  cmp     edx, 82h
0x18001e868  jbe     short loc_18001E8D3
0x18001e86a  mov     rax, cs:WPP_GLOBAL_Control
0x18001e871  lea     rcx, WPP_GLOBAL_Control
0x18001e878  cmp     rax, rcx
0x18001e87b  jz      loc_18001E975
0x18001e881  cmp     byte ptr [rax+19h], 3
0x18001e885  jb      loc_18001E975
0x18001e88b  test    dword ptr [rax+1Ch], 100h
0x18001e892  jz      loc_18001E975
0x18001e898  lea     rcx, aRadiusproxyGet_2; "RadiusProxy::getLocalIpAddress ValueSiz"...
0x18001e89f  call    WppDbgPrint
0x18001e8a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e8ab  lea     r9, aNpsrad; "NPSRAD"
0x18001e8b2  mov     eax, [rbp+cbData]
0x18001e8b5  lea     r8, WPP_71998f247ae0370d2143b01685e48c0c_Traceguids
0x18001e8bc  mov     edx, 13h
0x18001e8c1  mov     dword ptr [rsp+40h+phkResult], eax
0x18001e8c5  mov     rcx, [rcx+10h]
0x18001e8c9  call    WPP_SF_sd
0x18001e8ce  jmp     loc_18001E975
0x18001e8d3  mov     rcx, [rbp+hKey]; hKey
0x18001e8d7  lea     rax, [rbp+cbData]
0x18001e8db  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18001e8e0  lea     r9, [rbp+Type]; lpType
0x18001e8e4  xor     r8d, r8d; lpReserved
0x18001e8e7  mov     [rsp+40h+phkResult], rbx; lpData
0x18001e8ec  mov     rdx, r12; lpValueName
0x18001e8ef  call    cs:__imp_RegQueryValueExW
0x18001e8f5  mov     edi, eax
0x18001e8f7  test    eax, eax
0x18001e8f9  jz      short loc_18001E941
0x18001e8fb  cmp     eax, 2
0x18001e8fe  jz      short loc_18001E975
0x18001e900  mov     rdx, cs:WPP_GLOBAL_Control
0x18001e907  lea     rcx, WPP_GLOBAL_Control
0x18001e90e  cmp     rdx, rcx
0x18001e911  jz      short loc_18001E975
0x18001e913  cmp     byte ptr [rdx+19h], 2
0x18001e917  jb      short loc_18001E975
0x18001e919  test    dword ptr [rdx+1Ch], 100h
0x18001e920  jz      short loc_18001E975
0x18001e922  mov     r9d, eax
0x18001e925  lea     rcx, aRadiusproxyGet_3; "RadiusProxy::getLocalIpAddress RegQuery"...
0x18001e92c  mov     r8, r12
0x18001e92f  mov     rdx, r15
0x18001e932  call    WppDbgPrint
0x18001e937  mov     edx, 14h
0x18001e93c  jmp     loc_18001E826
0x18001e941  mov     rdx, rbx; unsigned __int16 *
0x18001e944  call    ?isIPValid@RadiusProxy@@IEAA_NPEAG@Z; RadiusProxy::isIPValid(ushort *)
0x18001e949  test    al, al
0x18001e94b  jnz     short loc_18001E975
0x18001e94d  xor     r8d, r8d
0x18001e950  mov     [rbp+arg_18], rbx
0x18001e954  lea     r9, [rbp+arg_18]
0x18001e958  mov     [rsp+40h+phkResult], 0
0x18001e961  mov     ecx, 80001141h
0x18001e966  lea     edx, [r8+1]
0x18001e96a  call    cs:__imp_IASReportEvent
0x18001e970  xor     eax, eax
0x18001e972  mov     [rbx], ax
0x18001e975  mov     rcx, [rbp+hKey]; hKey
0x18001e979  test    rcx, rcx
0x18001e97c  jz      short loc_18001E984
0x18001e97e  call    cs:__imp_RegCloseKey
0x18001e984  add     rsp, 40h
0x18001e988  pop     r15
0x18001e98a  pop     r12
0x18001e98c  pop     rdi
0x18001e98d  pop     rbx
0x18001e98e  pop     rbp
0x18001e98f  retn
```
