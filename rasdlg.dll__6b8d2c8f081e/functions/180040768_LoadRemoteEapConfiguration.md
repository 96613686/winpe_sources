# LoadRemoteEapConfiguration

- ea: `0x180040768`
- end: `0x180040aeb`
- name: `LoadRemoteEapConfiguration`
- size: `899`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180040af4`

## callees

- `0x18003b57c`
- `0x18003ca0c`
- `0x180040530`
- `0x180040580`
- `0x180040768`
- `0x1800412e4`
- `0x1800413ac`
- `0x18004146c`
- `0x1800414d0`
- `0x1800416b0`
- `0x18004d110`

## import_xrefs

- `msvcrt!atol` at `0x180040891`
- `msvcrt!atol` at `0x180040891`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800408de`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18004092f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180040965`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180040a37`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800408de`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18004092f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180040965`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180040a37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040803`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040803`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180040a2d`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180040a2d`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExA` at `0x180040a97`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExA` at `0x180040a97`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800407ed`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800407ed`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18004086a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18004086a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800407f9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040a66`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040ab4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800407f9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040a66`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040ab4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180040844`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180040844`
- `api-ms-win-core-registry-l2-1-0!RegConnectRegistryW` at `0x1800407b9`
- `api-ms-win-core-registry-l2-1-0!RegConnectRegistryW` at `0x1800407b9`

## string_xrefs

- `0x1800407e6`: `System\CurrentControlSet\Services\Rasman\PPP\EAP`
- `0x180040907`: `ConfigUIPath`
- `0x18004093d`: `IdentityPath`
- `0x1800409dc`: `RequireConfigUI`
- `0x180040a15`: `ConfigCLSID`

## pseudocode

```c
DWORD __fastcall LoadRemoteEapConfiguration(const WCHAR *a1, __int64 a2)
{
  LSTATUS v3; // ebx
  int v5; // r14d
  DWORD v6; // esi
  DWORD i; // edx
  __int64 EapcfgNode; // rax
  _QWORD *v9; // rdi
  __int64 v10; // rbx
  int v11; // eax
  HGLOBAL v12; // rax
  bool v13; // zf
  __int64 v14; // rdx
  LSTATUS v15; // eax
  LSTATUS v16; // ebx
  DWORD cbData; // [rsp+40h] [rbp-29h] BYREF
  HKEY v18; // [rsp+48h] [rbp-21h] BYREF
  DWORD Type[2]; // [rsp+50h] [rbp-19h] BYREF
  DWORD cchName; // [rsp+58h] [rbp-11h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-9h] BYREF
  BYTE Data[8]; // [rsp+68h] [rbp-1h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp+7h] BYREF
  LPCOLESTR lpsz; // [rsp+78h] [rbp+Fh]
  CHAR SubKey[16]; // [rsp+80h] [rbp+17h] BYREF

  phkResult = 0;
  hKey = 0;
  v18 = 0;
  cchName = 0;
  lpsz = 0;
  if ( RegConnectRegistryW(a1, HKEY_LOCAL_MACHINE, &phkResult) || !phkResult )
    return 87;
  v3 = RegOpenKeyExW(phkResult, L"System\\CurrentControlSet\\Services\\Rasman\\PPP\\EAP", 0, 0x20019u, &hKey);
  RegCloseKey(phkResult);
  if ( v3 )
    return GetLastError();
  *(_DWORD *)Data = 0;
  Type[0] = 0;
  v5 = 0;
  cbData = 4;
  RegQueryValueExW(hKey, L"HidePEAPMSChapv2", 0, Type, Data, &cbData);
  v6 = 0;
  for ( i = 0; ; i = v6 )
  {
    cchName = 12;
    v15 = RegEnumKeyExA(hKey, i, SubKey, &cchName, 0, 0, 0, 0);
    if ( v15 )
      break;
    if ( !RegOpenKeyExA(hKey, SubKey, 0, 0x20019u, &v18) )
    {
      EapcfgNode = CreateEapcfgNode();
      v9 = (_QWORD *)EapcfgNode;
      if ( !EapcfgNode )
        goto LABEL_27;
      v10 = *(_QWORD *)(EapcfgNode + 16);
      v11 = atol(SubKey);
      *(_DWORD *)(v10 + 4) = 1;
      *(_DWORD *)v10 = v11;
      *(_QWORD *)Type = 0;
      if ( (unsigned int)GetMuiString(v18) )
      {
        if ( (unsigned int)GetRegSz(v18, L"FriendlyName") )
          goto LABEL_27;
      }
      v12 = *(HGLOBAL *)Type;
      if ( !**(_WORD **)Type )
      {
        GlobalFree(*(HGLOBAL *)Type);
        v12 = (HGLOBAL)StrDupWFromAInternal(SubKey, 0xFDE9u);
        if ( !v12 )
          goto LABEL_27;
      }
      *(_QWORD *)(v10 + 24) = v12;
      *(_QWORD *)Type = 0;
      if ( (unsigned int)GetRegExpandSz(v18, L"ConfigUIPath", Type) )
        goto LABEL_27;
      if ( **(_WORD **)Type )
        *(_QWORD *)(v10 + 32) = *(_QWORD *)Type;
      else
        GlobalFree(*(HGLOBAL *)Type);
      *(_QWORD *)Type = 0;
      if ( (unsigned int)GetRegExpandSz(v18, L"IdentityPath", Type) )
        goto LABEL_27;
      if ( **(_WORD **)Type )
        *(_QWORD *)(v10 + 40) = *(_QWORD *)Type;
      else
        GlobalFree(*(HGLOBAL *)Type);
      cbData = 1;
      GetRegDword(v18, L"InvokeUsernameDialog", &cbData);
      if ( cbData )
        *(_DWORD *)(v10 + 48) |= 1u;
      cbData = 0;
      GetRegDword(v18, L"InvokePasswordDialog", &cbData);
      if ( cbData )
        *(_DWORD *)(v10 + 48) |= 2u;
      cbData = 0;
      GetRegDword(v18, L"MPPEEncryptionSupported", &cbData);
      v13 = cbData == 0;
      cbData = 0;
      *(_DWORD *)(v10 + 56) = !v13;
      GetRegDword(v18, L"RequireConfigUI", &cbData);
      *(_DWORD *)(v10 + 52) = cbData != 0;
      GetRegBinary(v18, v14, (BYTE **)(v10 + 64), (_DWORD *)(v10 + 72));
      if ( (unsigned int)GetRegSz(v18, L"ConfigCLSID") )
      {
LABEL_27:
        if ( !v5 && v9 )
          DestroyEapcfgNode(v9);
      }
      else
      {
        CLSIDFromString(lpsz, (LPCLSID)(v10 + 92));
        GlobalFree((HGLOBAL)lpsz);
        DtlAddNodeLast(a2, v9);
        v5 = 1;
      }
      RegCloseKey(v18);
    }
    ++v6;
  }
  v16 = 0;
  if ( v15 != 259 )
    v16 = v15;
  RegCloseKey(hKey);
  return v16;
}

```

## disassembly

```asm
0x180040768  mov     [rsp-8+arg_10], rbx
0x18004076d  mov     [rsp-8+arg_18], rsi
0x180040772  push    rbp
0x180040773  push    rdi
0x180040774  push    r12
0x180040776  push    r14
0x180040778  push    r15
0x18004077a  lea     rbp, [rsp-37h]
0x18004077f  sub     rsp, 0A0h
0x180040786  mov     rax, cs:__security_cookie
0x18004078d  xor     rax, rsp
0x180040790  mov     [rbp+57h+var_30], rax
0x180040794  xor     r12d, r12d
0x180040797  lea     r8, [rbp+57h+phkResult]; phkResult
0x18004079b  mov     r15, rdx
0x18004079e  mov     [rbp+57h+phkResult], r12
0x1800407a2  mov     rdx, 0FFFFFFFF80000002h; hKey
0x1800407a9  mov     [rbp+57h+hKey], r12
0x1800407ad  mov     [rbp+57h+var_78], r12
0x1800407b1  mov     [rbp+57h+cchName], r12d
0x1800407b5  mov     [rbp+57h+lpsz], r12
0x1800407b9  call    cs:__imp_RegConnectRegistryW
0x1800407bf  test    eax, eax
0x1800407c1  jnz     loc_180040ABE
0x1800407c7  mov     rcx, [rbp+57h+phkResult]; hKey
0x1800407cb  test    rcx, rcx
0x1800407ce  jz      loc_180040ABE
0x1800407d4  lea     rax, [rbp+57h+hKey]
0x1800407d8  mov     r9d, 20019h; samDesired
0x1800407de  xor     r8d, r8d; ulOptions
0x1800407e1  mov     [rsp+0C0h+var_A0], rax; phkResult
0x1800407e6  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\Ra"...
0x1800407ed  call    cs:__imp_RegOpenKeyExW
0x1800407f3  mov     rcx, [rbp+57h+phkResult]; hKey
0x1800407f7  mov     ebx, eax
0x1800407f9  call    cs:__imp_RegCloseKey
0x1800407ff  test    ebx, ebx
0x180040801  jz      short loc_18004080E
0x180040803  call    cs:__imp_GetLastError
0x180040809  jmp     loc_180040AC3
0x18004080e  mov     rcx, [rbp+57h+hKey]; hKey
0x180040812  lea     rax, [rbp+57h+cbData]
0x180040816  mov     [rsp+0C0h+lpcbData], rax; lpcbData
0x18004081b  lea     r9, [rbp+57h+Type]; lpType
0x18004081f  lea     rax, [rbp+57h+Data]
0x180040823  mov     dword ptr [rbp+57h+Data], r12d
0x180040827  xor     r8d, r8d; lpReserved
0x18004082a  mov     [rsp+0C0h+var_A0], rax; lpData
0x18004082f  lea     rdx, aHidepeapmschap; "HidePEAPMSChapv2"
0x180040836  mov     [rbp+57h+Type], r12d
0x18004083a  mov     r14d, r12d
0x18004083d  mov     [rbp+57h+cbData], 4
0x180040844  call    cs:__imp_RegQueryValueExW
0x18004084a  mov     esi, r12d
0x18004084d  xor     edx, edx
0x18004084f  jmp     loc_180040A70
0x180040854  lea     rax, [rbp+57h+var_78]
0x180040858  mov     r9d, 20019h; samDesired
0x18004085e  xor     r8d, r8d; ulOptions
0x180040861  mov     [rsp+0C0h+var_A0], rax; phkResult
0x180040866  lea     rdx, [rbp+57h+SubKey]; lpSubKey
0x18004086a  call    cs:__imp_RegOpenKeyExA
0x180040870  test    eax, eax
0x180040872  jnz     loc_180040A6C
0x180040878  call    CreateEapcfgNode
0x18004087d  mov     rdi, rax
0x180040880  test    rax, rax
0x180040883  jz      loc_180040A50
0x180040889  mov     rbx, [rax+10h]
0x18004088d  lea     rcx, [rbp+57h+SubKey]; String
0x180040891  call    cs:__imp_atol
0x180040897  mov     dword ptr [rbx+4], 1
0x18004089e  lea     r8, [rbp+57h+Type]
0x1800408a2  mov     [rbx], eax
0x1800408a4  mov     rcx, [rbp+57h+var_78]; hKey
0x1800408a8  mov     qword ptr [rbp+57h+Type], r12
0x1800408ac  call    GetMuiString
0x1800408b1  test    eax, eax
0x1800408b3  jz      short loc_1800408D1
0x1800408b5  mov     rcx, [rbp+57h+var_78]; hKey
0x1800408b9  lea     r8, [rbp+57h+Type]
0x1800408bd  lea     rdx, pszValue; "FriendlyName"
0x1800408c4  call    GetRegSz
0x1800408c9  test    eax, eax
0x1800408cb  jnz     loc_180040A50
0x1800408d1  mov     rax, qword ptr [rbp+57h+Type]
0x1800408d5  cmp     [rax], r12w
0x1800408d9  jnz     short loc_1800408FB
0x1800408db  mov     rcx, rax; hMem
0x1800408de  call    cs:__imp_GlobalFree
0x1800408e4  mov     edx, 0FDE9h; CodePage
0x1800408e9  lea     rcx, [rbp+57h+SubKey]; lpMultiByteStr
0x1800408ed  call    StrDupWFromAInternal
0x1800408f2  test    rax, rax
0x1800408f5  jz      loc_180040A50
0x1800408fb  mov     [rbx+18h], rax
0x1800408ff  lea     r8, [rbp+57h+Type]
0x180040903  mov     rcx, [rbp+57h+var_78]
0x180040907  lea     rdx, aConfiguipath; "ConfigUIPath"
0x18004090e  mov     qword ptr [rbp+57h+Type], r12
0x180040912  call    GetRegExpandSz
0x180040917  test    eax, eax
0x180040919  jnz     loc_180040A50
0x18004091f  mov     rcx, qword ptr [rbp+57h+Type]; hMem
0x180040923  cmp     [rcx], r12w
0x180040927  jz      short loc_18004092F
0x180040929  mov     [rbx+20h], rcx
0x18004092d  jmp     short loc_180040935
0x18004092f  call    cs:__imp_GlobalFree
0x180040935  mov     rcx, [rbp+57h+var_78]
0x180040939  lea     r8, [rbp+57h+Type]
0x18004093d  lea     rdx, aIdentitypath; "IdentityPath"
0x180040944  mov     qword ptr [rbp+57h+Type], r12
0x180040948  call    GetRegExpandSz
0x18004094d  test    eax, eax
0x18004094f  jnz     loc_180040A50
0x180040955  mov     rcx, qword ptr [rbp+57h+Type]; hMem
0x180040959  cmp     [rcx], r12w
0x18004095d  jz      short loc_180040965
0x18004095f  mov     [rbx+28h], rcx
0x180040963  jmp     short loc_18004096B
0x180040965  call    cs:__imp_GlobalFree
0x18004096b  mov     rcx, [rbp+57h+var_78]
0x18004096f  lea     r8, [rbp+57h+cbData]
0x180040973  lea     rdx, aInvokeusername; "InvokeUsernameDialog"
0x18004097a  mov     [rbp+57h+cbData], 1
0x180040981  call    GetRegDword
0x180040986  cmp     [rbp+57h+cbData], r12d
0x18004098a  jz      short loc_180040990
0x18004098c  or      dword ptr [rbx+30h], 1
0x180040990  mov     rcx, [rbp+57h+var_78]
0x180040994  lea     r8, [rbp+57h+cbData]
0x180040998  lea     rdx, aInvokepassword; "InvokePasswordDialog"
0x18004099f  mov     [rbp+57h+cbData], r12d
0x1800409a3  call    GetRegDword
0x1800409a8  cmp     [rbp+57h+cbData], r12d
0x1800409ac  jz      short loc_1800409B2
0x1800409ae  or      dword ptr [rbx+30h], 2
0x1800409b2  mov     rcx, [rbp+57h+var_78]
0x1800409b6  lea     r8, [rbp+57h+cbData]
0x1800409ba  lea     rdx, aMppeencryption; "MPPEEncryptionSupported"
0x1800409c1  mov     [rbp+57h+cbData], r12d
0x1800409c5  call    GetRegDword
0x1800409ca  cmp     [rbp+57h+cbData], r12d
0x1800409ce  lea     r8, [rbp+57h+cbData]
0x1800409d2  mov     eax, r12d
0x1800409d5  mov     [rbp+57h+cbData], r12d
0x1800409d9  setnz   al
0x1800409dc  lea     rdx, aRequireconfigu; "RequireConfigUI"
0x1800409e3  mov     [rbx+38h], eax
0x1800409e6  mov     rcx, [rbp+57h+var_78]
0x1800409ea  call    GetRegDword
0x1800409ef  cmp     [rbp+57h+cbData], r12d
0x1800409f3  lea     r9, [rbx+48h]
0x1800409f7  mov     eax, r12d
0x1800409fa  lea     r8, [rbx+40h]
0x1800409fe  setnz   al
0x180040a01  mov     [rbx+34h], eax
0x180040a04  mov     rcx, [rbp+57h+var_78]; hKey
0x180040a08  call    GetRegBinary
0x180040a0d  mov     rcx, [rbp+57h+var_78]; hKey
0x180040a11  lea     r8, [rbp+57h+lpsz]
0x180040a15  lea     rdx, aConfigclsid; "ConfigCLSID"
0x180040a1c  call    GetRegSz
0x180040a21  test    eax, eax
0x180040a23  jnz     short loc_180040A50
0x180040a25  mov     rcx, [rbp+57h+lpsz]; lpsz
0x180040a29  lea     rdx, [rbx+5Ch]; pclsid
0x180040a2d  call    cs:__imp_CLSIDFromString
0x180040a33  mov     rcx, [rbp+57h+lpsz]; hMem
0x180040a37  call    cs:__imp_GlobalFree
0x180040a3d  mov     rdx, rdi
0x180040a40  mov     rcx, r15
0x180040a43  call    DtlAddNodeLast
0x180040a48  mov     r14d, 1
0x180040a4e  jmp     short loc_180040A62
0x180040a50  test    r14d, r14d
0x180040a53  jnz     short loc_180040A62
0x180040a55  test    rdi, rdi
0x180040a58  jz      short loc_180040A62
0x180040a5a  mov     rcx, rdi
0x180040a5d  call    DestroyEapcfgNode
0x180040a62  mov     rcx, [rbp+57h+var_78]; hKey
0x180040a66  call    cs:__imp_RegCloseKey
0x180040a6c  inc     esi
0x180040a6e  mov     edx, esi; dwIndex
0x180040a70  mov     rcx, [rbp+57h+hKey]; hKey
0x180040a74  lea     r9, [rbp+57h+cchName]; lpcchName
0x180040a78  mov     [rsp+0C0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180040a7d  lea     r8, [rbp+57h+SubKey]; lpName
0x180040a81  mov     [rsp+0C0h+lpcchClass], r12; lpcchClass
0x180040a86  mov     [rsp+0C0h+lpcbData], r12; lpClass
0x180040a8b  mov     [rsp+0C0h+var_A0], r12; lpReserved
0x180040a90  mov     [rbp+57h+cchName], 0Ch
0x180040a97  call    cs:__imp_RegEnumKeyExA
0x180040a9d  mov     rcx, [rbp+57h+hKey]; hKey
0x180040aa1  test    eax, eax
0x180040aa3  jz      loc_180040854
0x180040aa9  cmp     eax, 103h
0x180040aae  mov     ebx, r12d
0x180040ab1  cmovnz  ebx, eax
0x180040ab4  call    cs:__imp_RegCloseKey
0x180040aba  mov     eax, ebx
0x180040abc  jmp     short loc_180040AC3
0x180040abe  mov     eax, 57h ; 'W'
0x180040ac3  mov     rcx, [rbp+57h+var_30]
0x180040ac7  xor     rcx, rsp; StackCookie
0x180040aca  call    __security_check_cookie
0x180040acf  lea     r11, [rsp+0C0h+var_20]
0x180040ad7  mov     rbx, [r11+40h]
0x180040adb  mov     rsi, [r11+48h]
0x180040adf  mov     rsp, r11
0x180040ae2  pop     r15
0x180040ae4  pop     r14
0x180040ae6  pop     r12
0x180040ae8  pop     rdi
0x180040ae9  pop     rbp
0x180040aea  retn
```
