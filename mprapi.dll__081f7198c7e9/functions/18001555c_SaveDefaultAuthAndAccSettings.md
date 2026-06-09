# SaveDefaultAuthAndAccSettings

- ea: `0x18001555c`
- end: `0x180015821`
- name: `SaveDefaultAuthAndAccSettings`
- size: `709`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180026b90`

## callees

- `0x18000aeb4`
- `0x1800152a0`
- `0x18001555c`
- `0x18003765c`
- `0x18003771c`
- `0x1800377e8`
- `0x180037908`
- `0x180051160`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800157be`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800157d3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800157e8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800157be`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800157d3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800157e8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001569d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015728`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001577e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001569d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015728`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001577e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015641`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800156f8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001574b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015641`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800156f8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001574b`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800155ff`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180015617`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800155ff`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180015617`
- `OLEAUT32!__imp_SysFreeString` at `0x1800157fb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800157fb`

## string_xrefs

- `0x1800156ee`: `System\CurrentControlSet\Services\RemoteAccess\Authentication\Providers`
- `0x180015637`: `System\CurrentControlSet\Services\RemoteAccess\Parameters`
- `0x180015741`: `System\CurrentControlSet\Services\RemoteAccess\Accounting\Providers`

## pseudocode

```c
__int64 SaveDefaultAuthAndAccSettings()
{
  unsigned int v0; // ebx
  OLECHAR *v1; // rdi
  unsigned int v2; // eax
  LSTATUS v3; // eax
  __int64 v4; // rcx
  __int64 result; // rax
  int SdoNameFromRegistry; // eax
  BYTE Data[8]; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  int v9; // [rsp+40h] [rbp-C0h] BYREF
  int v10; // [rsp+44h] [rbp-BCh] BYREF
  OLECHAR *psz; // [rsp+48h] [rbp-B8h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  HKEY v13; // [rsp+58h] [rbp-A8h] BYREF
  GUID rguid; // [rsp+60h] [rbp-A0h] BYREF
  GUID v15; // [rsp+70h] [rbp-90h] BYREF
  OLECHAR sz[128]; // [rsp+80h] [rbp-80h] BYREF
  OLECHAR v17[128]; // [rsp+180h] [rbp+80h] BYREF

  rguid.Data1 = 447215681;
  v9 = 0;
  *(_DWORD *)Data = 0;
  hKey = 0;
  v0 = 0;
  phkResult = 0;
  v13 = 0;
  v1 = 0;
  v10 = 0;
  psz = 0;
  *(_DWORD *)&rguid.Data2 = 298895349;
  *(_DWORD *)rguid.Data4 = -1073711453;
  *(_DWORD *)&rguid.Data4[4] = 81447247;
  v15.Data1 = 447215686;
  *(_DWORD *)&v15.Data2 = 298895349;
  *(_DWORD *)v15.Data4 = -1073711453;
  *(_DWORD *)&v15.Data4[4] = 81447247;
  StringFromGUID2(&rguid, sz, 128);
  StringFromGUID2(&v15, v17, 128);
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Services\\RemoteAccess\\Parameters",
          0,
          0xF003Fu,
          &hKey) )
  {
    v2 = QueryDwordValue(hKey, L"ServerFlags", &v9);
    if ( v2 )
    {
      v0 = v2;
    }
    else
    {
      *(_DWORD *)Data |= v9 & 0x40602;
      v3 = RegSetValueExW(hKey, L"ServerFlags", 0, 4u, Data, 4u);
      if ( v3 )
        v0 = v3;
    }
  }
  if ( (unsigned int)IsQuarantineInstalled() )
  {
    LODWORD(result) = IsIasInstalled(v4, &v10);
    if ( (int)result < 0 || v10 )
      return (unsigned __int16)result;
  }
  if ( (unsigned int)IsQuarantineInstalled() )
  {
    SdoNameFromRegistry = GetSdoNameFromRegistry(&psz);
    v1 = psz;
    if ( SdoNameFromRegistry < 0
      || (SdoNameFromRegistry = SdoAuthHelper(psz), SdoNameFromRegistry < 0)
      || (SdoNameFromRegistry = SdoAcctHelper(v1), SdoNameFromRegistry < 0) )
    {
      v0 = (unsigned __int16)SdoNameFromRegistry;
    }
  }
  else
  {
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"System\\CurrentControlSet\\Services\\RemoteAccess\\Authentication\\Providers",
            0,
            0xF003Fu,
            &phkResult) )
      RegSetValueExW(hKey, L"ActiveProvider", 0, 1u, (const BYTE *)sz, 0x100u);
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"System\\CurrentControlSet\\Services\\RemoteAccess\\Accounting\\Providers",
            0,
            0xF003Fu,
            &v13) )
      RegSetValueExW(hKey, L"ActiveProvider", 0, 1u, (const BYTE *)v17, 0x100u);
  }
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  if ( v13 )
  {
    RegCloseKey(v13);
    v13 = 0;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v1 )
    SysFreeString(v1);
  return v0;
}

```

## disassembly

```asm
0x18001555c  push    rbp
0x18001555e  push    rbx
0x18001555f  push    rdi
0x180015560  push    r13
0x180015562  push    r14
0x180015564  lea     rbp, [rsp-190h]
0x18001556c  sub     rsp, 290h
0x180015573  mov     rax, cs:__security_cookie
0x18001557a  xor     rax, rsp
0x18001557d  mov     [rbp+1B0h+var_30], rax
0x180015584  xor     r14d, r14d
0x180015587  mov     [rsp+2B0h+rguid.Data1], 1AA7F841h
0x18001558f  mov     r8d, 80h; cchMax
0x180015595  mov     [rsp+2B0h+var_270], r14d
0x18001559a  lea     rdx, [rbp+1B0h+sz]; lpsz
0x18001559e  mov     dword ptr [rsp+2B0h+Data], r14d
0x1800155a3  lea     rcx, [rsp+2B0h+rguid]; rguid
0x1800155a8  mov     [rsp+2B0h+hKey], r14
0x1800155ad  mov     ebx, r14d
0x1800155b0  mov     [rsp+2B0h+var_260], r14
0x1800155b5  mov     [rsp+2B0h+var_258], r14
0x1800155ba  mov     edi, r14d
0x1800155bd  mov     [rsp+2B0h+var_26C], r14d
0x1800155c2  mov     [rsp+2B0h+psz], r14
0x1800155c7  mov     dword ptr [rsp+2B0h+rguid.Data2], 11D0C7F5h
0x1800155cf  mov     dword ptr [rsp+2B0h+rguid.Data4], 0C00076A3h
0x1800155d7  mov     dword ptr [rsp+2B0h+rguid.Data4+4], 4DAC94Fh
0x1800155df  mov     [rsp+2B0h+var_240.Data1], 1AA7F846h
0x1800155e7  mov     dword ptr [rsp+2B0h+var_240.Data2], 11D0C7F5h
0x1800155ef  mov     dword ptr [rsp+2B0h+var_240.Data4], 0C00076A3h
0x1800155f7  mov     dword ptr [rsp+2B0h+var_240.Data4+4], 4DAC94Fh
0x1800155ff  call    cs:__imp_StringFromGUID2
0x180015605  mov     r8d, 80h; cchMax
0x18001560b  lea     rdx, [rbp+1B0h+var_130]; lpsz
0x180015612  lea     rcx, [rsp+2B0h+var_240]; rguid
0x180015617  call    cs:__imp_StringFromGUID2
0x18001561d  lea     rax, [rsp+2B0h+hKey]
0x180015622  mov     r13, 0FFFFFFFF80000002h
0x180015629  mov     rcx, r13; hKey
0x18001562c  mov     [rsp+2B0h+phkResult], rax; phkResult
0x180015631  mov     r9d, 0F003Fh; samDesired
0x180015637  lea     rdx, c_szRegKeyRemoteAccessParameters; "System\\CurrentControlSet\\Services\\Re"...
0x18001563e  xor     r8d, r8d; ulOptions
0x180015641  call    cs:__imp_RegOpenKeyExW
0x180015647  test    eax, eax
0x180015649  jnz     short loc_1800156A8
0x18001564b  mov     rcx, [rsp+2B0h+hKey]
0x180015650  lea     r8, [rsp+2B0h+var_270]
0x180015655  lea     rdx, c_szServerFlags; "ServerFlags"
0x18001565c  call    QueryDwordValue
0x180015661  test    eax, eax
0x180015663  jz      short loc_180015669
0x180015665  mov     ebx, eax
0x180015667  jmp     short loc_1800156A8
0x180015669  mov     eax, [rsp+2B0h+var_270]
0x18001566d  lea     rdx, c_szServerFlags; "ServerFlags"
0x180015674  mov     rcx, [rsp+2B0h+hKey]; hKey
0x180015679  and     eax, 40602h
0x18001567e  or      dword ptr [rsp+2B0h+Data], eax
0x180015682  mov     r9d, 4; dwType
0x180015688  lea     rax, [rsp+2B0h+Data]
0x18001568d  mov     [rsp+2B0h+cbData], 4; cbData
0x180015695  xor     r8d, r8d; Reserved
0x180015698  mov     [rsp+2B0h+phkResult], rax; lpData
0x18001569d  call    cs:__imp_RegSetValueExW
0x1800156a3  test    eax, eax
0x1800156a5  cmovnz  ebx, eax
0x1800156a8  call    IsQuarantineInstalled
0x1800156ad  test    eax, eax
0x1800156af  jz      short loc_1800156CE
0x1800156b1  lea     rdx, [rsp+2B0h+var_26C]
0x1800156b6  call    IsIasInstalled
0x1800156bb  test    eax, eax
0x1800156bd  js      short loc_1800156C6
0x1800156bf  cmp     [rsp+2B0h+var_26C], r14d
0x1800156c4  jz      short loc_1800156CE
0x1800156c6  movzx   eax, ax
0x1800156c9  jmp     loc_180015803
0x1800156ce  call    IsQuarantineInstalled
0x1800156d3  test    eax, eax
0x1800156d5  jnz     loc_180015786
0x1800156db  lea     rax, [rsp+2B0h+var_260]
0x1800156e0  mov     r9d, 0F003Fh; samDesired
0x1800156e6  xor     r8d, r8d; ulOptions
0x1800156e9  mov     [rsp+2B0h+phkResult], rax; phkResult
0x1800156ee  lea     rdx, c_szRegKeyRouterAuthenticationProviders; "System\\CurrentControlSet\\Services\\Re"...
0x1800156f5  mov     rcx, r13; hKey
0x1800156f8  call    cs:__imp_RegOpenKeyExW
0x1800156fe  test    eax, eax
0x180015700  jnz     short loc_18001572E
0x180015702  mov     rcx, [rsp+2B0h+hKey]; hKey
0x180015707  lea     rax, [rbp+1B0h+sz]
0x18001570b  mov     [rsp+2B0h+cbData], 100h; cbData
0x180015713  lea     rdx, c_szActiveProvider; "ActiveProvider"
0x18001571a  mov     r9d, 1; dwType
0x180015720  mov     [rsp+2B0h+phkResult], rax; lpData
0x180015725  xor     r8d, r8d; Reserved
0x180015728  call    cs:__imp_RegSetValueExW
0x18001572e  lea     rax, [rsp+2B0h+var_258]
0x180015733  mov     r9d, 0F003Fh; samDesired
0x180015739  xor     r8d, r8d; ulOptions
0x18001573c  mov     [rsp+2B0h+phkResult], rax; phkResult
0x180015741  lea     rdx, c_szRegKeyRouterAccountingProviders; "System\\CurrentControlSet\\Services\\Re"...
0x180015748  mov     rcx, r13; hKey
0x18001574b  call    cs:__imp_RegOpenKeyExW
0x180015751  test    eax, eax
0x180015753  jnz     short loc_1800157B4
0x180015755  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18001575a  lea     rax, [rbp+1B0h+var_130]
0x180015761  mov     [rsp+2B0h+cbData], 100h; cbData
0x180015769  lea     rdx, c_szActiveProvider; "ActiveProvider"
0x180015770  mov     r9d, 1; dwType
0x180015776  mov     [rsp+2B0h+phkResult], rax; lpData
0x18001577b  xor     r8d, r8d; Reserved
0x18001577e  call    cs:__imp_RegSetValueExW
0x180015784  jmp     short loc_1800157B4
0x180015786  lea     rcx, [rsp+2B0h+psz]
0x18001578b  call    GetSdoNameFromRegistry
0x180015790  mov     rdi, [rsp+2B0h+psz]
0x180015795  test    eax, eax
0x180015797  js      short loc_1800157B1
0x180015799  mov     rcx, rdi; psz
0x18001579c  call    SdoAuthHelper
0x1800157a1  test    eax, eax
0x1800157a3  js      short loc_1800157B1
0x1800157a5  mov     rcx, rdi; psz
0x1800157a8  call    SdoAcctHelper
0x1800157ad  test    eax, eax
0x1800157af  jns     short loc_1800157B4
0x1800157b1  movzx   ebx, ax
0x1800157b4  mov     rcx, [rsp+2B0h+var_260]; hKey
0x1800157b9  test    rcx, rcx
0x1800157bc  jz      short loc_1800157C9
0x1800157be  call    cs:__imp_RegCloseKey
0x1800157c4  mov     [rsp+2B0h+var_260], r14
0x1800157c9  mov     rcx, [rsp+2B0h+var_258]; hKey
0x1800157ce  test    rcx, rcx
0x1800157d1  jz      short loc_1800157DE
0x1800157d3  call    cs:__imp_RegCloseKey
0x1800157d9  mov     [rsp+2B0h+var_258], r14
0x1800157de  mov     rcx, [rsp+2B0h+hKey]; hKey
0x1800157e3  test    rcx, rcx
0x1800157e6  jz      short loc_1800157F3
0x1800157e8  call    cs:__imp_RegCloseKey
0x1800157ee  mov     [rsp+2B0h+hKey], r14
0x1800157f3  test    rdi, rdi
0x1800157f6  jz      short loc_180015801
0x1800157f8  mov     rcx, rdi; bstrString
0x1800157fb  call    cs:__imp_SysFreeString
0x180015801  mov     eax, ebx
0x180015803  mov     rcx, [rbp+1B0h+var_30]
0x18001580a  xor     rcx, rsp; StackCookie
0x18001580d  call    __security_check_cookie
0x180015812  add     rsp, 290h
0x180015819  pop     r14
0x18001581b  pop     r13
0x18001581d  pop     rdi
0x18001581e  pop     rbx
0x18001581f  pop     rbp
0x180015820  retn
```
