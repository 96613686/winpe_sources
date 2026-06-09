# _anonymous_namespace_::getBackendServerTimeout

- ea: `0x18001d684`
- end: `0x18001d8c7`
- name: `_anonymous_namespace_::getBackendServerTimeout`
- size: `579`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x18001d914`

## callees

- `0x18001426c`
- `0x18001d684`
- `0x18001daa8`
- `0x1800254a0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18001d8b6`
- `ADVAPI32!RegCloseKey` at `0x18001d8b6`
- `ADVAPI32!RegOpenKeyExW` at `0x18001d6ba`
- `ADVAPI32!RegOpenKeyExW` at `0x18001d6ba`
- `ADVAPI32!RegQueryValueExW` at `0x18001d762`
- `ADVAPI32!RegQueryValueExW` at `0x18001d762`

## string_xrefs

- `0x18001d6eb`: `Cannot open the reg key %S, error %ld`
- `0x18001d7a8`: `Cannot read value %S. Error %ld`
- `0x18001d7f3`: `The registry value %S does not exist. Using default %ld`
- `0x18001d869`: `Cannot read value %S.  Wrong type %ld. Size = %ld. Value = %ld`
- `0x18001d6a9`: `SYSTEM\CurrentControlSet\Services\RemoteAccess\Policy`

## pseudocode

```c
__int64 anonymous_namespace_::getBackendServerTimeout()
{
  LSTATUS v0; // eax
  char v1; // di
  int v2; // r9d
  LSTATUS v4; // eax
  char v5; // di
  int v6; // r9d
  int v7; // r9d
  int v8; // r9d
  unsigned int Data; // [rsp+60h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+28h] BYREF
  DWORD Type; // [rsp+70h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+38h] BYREF

  hKey = 0;
  v0 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\RemoteAccess\\Policy",
         0,
         0x20019u,
         &hKey);
  v1 = v0;
  if ( v0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WppDbgPrint("Cannot open the reg key %S, error %ld");
      WPP_SF_sSl(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        (unsigned int)WPP_4c4937dd1ef3394d6e9963f59526f193_Traceguids,
        v2,
        (__int64)L"SYSTEM\\CurrentControlSet\\Services\\RemoteAccess\\Policy",
        v1);
    }
    return 2;
  }
  else
  {
    Type = 0;
    cbData = 4;
    Data = 2;
    v4 = RegQueryValueExW(hKey, L"BackendServerTimeout", 0, &Type, (LPBYTE)&Data, &cbData);
    v5 = v4;
    if ( v4 )
    {
      if ( v4 == 2 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WppDbgPrint("The registry value %S does not exist. Using default %ld");
          WPP_SF_sSl(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            12,
            (unsigned int)WPP_4c4937dd1ef3394d6e9963f59526f193_Traceguids,
            v7,
            (__int64)L"BackendServerTimeout",
            2);
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WppDbgPrint("Cannot read value %S. Error %ld");
        WPP_SF_sSl(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          (unsigned int)WPP_4c4937dd1ef3394d6e9963f59526f193_Traceguids,
          v6,
          (__int64)L"BackendServerTimeout",
          v5);
      }
    }
    else if ( Type != 4 || cbData != 4 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WppDbgPrint("Cannot read value %S.  Wrong type %ld. Size = %ld. Value = %ld");
        WPP_SF_sSlll(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          (unsigned int)WPP_4c4937dd1ef3394d6e9963f59526f193_Traceguids,
          v8,
          (__int64)L"BackendServerTimeout",
          Type,
          cbData,
          Data);
      }
      Data = 2;
    }
    RegCloseKey(hKey);
    return Data;
  }
}

```

## disassembly

```asm
0x18001d684  push    rbp
0x18001d686  push    rsi
0x18001d687  push    rdi
0x18001d688  mov     rbp, rsp
0x18001d68b  sub     rsp, 40h
0x18001d68f  mov     [rbp+hKey], 0
0x18001d697  lea     rax, [rbp+hKey]
0x18001d69b  mov     [rsp+40h+phkResult], rax; phkResult
0x18001d6a0  mov     r9d, 20019h; samDesired
0x18001d6a6  xor     r8d, r8d; ulOptions
0x18001d6a9  lea     rsi, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Services\\Re"...
0x18001d6b0  mov     rdx, rsi; lpSubKey
0x18001d6b3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001d6ba  call    cs:__imp_RegOpenKeyExW
0x18001d6c0  mov     edi, eax
0x18001d6c2  test    eax, eax
0x18001d6c4  jz      short loc_18001D726
0x18001d6c6  lea     rcx, WPP_GLOBAL_Control
0x18001d6cd  mov     rdx, cs:WPP_GLOBAL_Control
0x18001d6d4  cmp     rdx, rcx
0x18001d6d7  jz      short loc_18001D71C
0x18001d6d9  cmp     byte ptr [rdx+19h], 2
0x18001d6dd  jb      short loc_18001D71C
0x18001d6df  test    byte ptr [rdx+1Ch], 4
0x18001d6e3  jz      short loc_18001D71C
0x18001d6e5  mov     r8d, eax
0x18001d6e8  mov     rdx, rsi
0x18001d6eb  lea     rcx, aCannotOpenTheR; "Cannot open the reg key %S, error %ld"
0x18001d6f2  call    WppDbgPrint
0x18001d6f7  mov     edx, 0Ah
0x18001d6fc  mov     dword ptr [rsp+40h+lpcbData], edi
0x18001d700  mov     [rsp+40h+phkResult], rsi
0x18001d705  lea     r8, WPP_4c4937dd1ef3394d6e9963f59526f193_Traceguids
0x18001d70c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d713  mov     rcx, [rcx+10h]
0x18001d717  call    WPP_SF_sSl
0x18001d71c  mov     eax, 2
0x18001d721  jmp     loc_18001D8BF
0x18001d726  mov     [rbp+Type], 0
0x18001d72d  mov     [rbp+cbData], 4
0x18001d734  mov     [rbp+Data], 2
0x18001d73b  lea     rax, [rbp+cbData]
0x18001d73f  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18001d744  lea     rax, [rbp+Data]
0x18001d748  mov     [rsp+40h+phkResult], rax; lpData
0x18001d74d  lea     r9, [rbp+Type]; lpType
0x18001d751  xor     r8d, r8d; lpReserved
0x18001d754  lea     rsi, aBackendservert; "BackendServerTimeout"
0x18001d75b  mov     rdx, rsi; lpValueName
0x18001d75e  mov     rcx, [rbp+hKey]; hKey
0x18001d762  call    cs:__imp_RegQueryValueExW
0x18001d768  mov     edi, eax
0x18001d76a  test    eax, eax
0x18001d76c  jz      loc_18001D82D
0x18001d772  cmp     eax, 2
0x18001d775  jz      short loc_18001D7BF
0x18001d777  lea     rcx, WPP_GLOBAL_Control
0x18001d77e  mov     rdx, cs:WPP_GLOBAL_Control
0x18001d785  cmp     rdx, rcx
0x18001d788  jz      loc_18001D8B2
0x18001d78e  cmp     byte ptr [rdx+19h], 2
0x18001d792  jb      loc_18001D8B2
0x18001d798  test    byte ptr [rdx+1Ch], 4
0x18001d79c  jz      loc_18001D8B2
0x18001d7a2  mov     r8d, eax
0x18001d7a5  mov     rdx, rsi
0x18001d7a8  lea     rcx, aCannotReadValu_3; "Cannot read value %S. Error %ld"
0x18001d7af  call    WppDbgPrint
0x18001d7b4  mov     edx, 0Bh
0x18001d7b9  mov     dword ptr [rsp+40h+lpcbData], edi
0x18001d7bd  jmp     short loc_18001D80C
0x18001d7bf  lea     rcx, WPP_GLOBAL_Control
0x18001d7c6  mov     rax, cs:WPP_GLOBAL_Control
0x18001d7cd  cmp     rax, rcx
0x18001d7d0  jz      loc_18001D8B2
0x18001d7d6  cmp     byte ptr [rax+19h], 4
0x18001d7da  jb      loc_18001D8B2
0x18001d7e0  test    byte ptr [rax+1Ch], 4
0x18001d7e4  jz      loc_18001D8B2
0x18001d7ea  mov     r8d, 2
0x18001d7f0  mov     rdx, rsi
0x18001d7f3  lea     rcx, aTheRegistryVal; "The registry value %S does not exist. U"...
0x18001d7fa  call    WppDbgPrint
0x18001d7ff  mov     edx, 0Ch
0x18001d804  mov     dword ptr [rsp+40h+lpcbData], 2
0x18001d80c  mov     [rsp+40h+phkResult], rsi
0x18001d811  lea     r8, WPP_4c4937dd1ef3394d6e9963f59526f193_Traceguids
0x18001d818  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d81f  mov     rcx, [rcx+10h]
0x18001d823  call    WPP_SF_sSl
0x18001d828  jmp     loc_18001D8B2
0x18001d82d  mov     r9d, [rbp+cbData]
0x18001d831  mov     r8d, [rbp+Type]
0x18001d835  cmp     r8d, 4
0x18001d839  jnz     short loc_18001D840
0x18001d83b  cmp     r9d, r8d
0x18001d83e  jz      short loc_18001D8B2
0x18001d840  lea     rcx, WPP_GLOBAL_Control
0x18001d847  mov     rax, cs:WPP_GLOBAL_Control
0x18001d84e  cmp     rax, rcx
0x18001d851  jz      short loc_18001D8AB
0x18001d853  cmp     byte ptr [rax+19h], 2
0x18001d857  jb      short loc_18001D8AB
0x18001d859  test    byte ptr [rax+1Ch], 4
0x18001d85d  jz      short loc_18001D8AB
0x18001d85f  mov     eax, [rbp+Data]
0x18001d862  mov     dword ptr [rsp+40h+phkResult], eax
0x18001d866  mov     rdx, rsi
0x18001d869  lea     rcx, aCannotReadValu; "Cannot read value %S.  Wrong type %ld. "...
0x18001d870  call    WppDbgPrint
0x18001d875  mov     edx, 0Dh
0x18001d87a  mov     eax, [rbp+Data]
0x18001d87d  mov     [rsp+40h+var_8], eax
0x18001d881  mov     eax, [rbp+cbData]
0x18001d884  mov     [rsp+40h+var_10], eax
0x18001d888  mov     eax, [rbp+Type]
0x18001d88b  mov     dword ptr [rsp+40h+lpcbData], eax
0x18001d88f  mov     [rsp+40h+phkResult], rsi
0x18001d894  lea     r8, WPP_4c4937dd1ef3394d6e9963f59526f193_Traceguids
0x18001d89b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d8a2  mov     rcx, [rcx+10h]
0x18001d8a6  call    WPP_SF_sSlll
0x18001d8ab  mov     [rbp+Data], 2
0x18001d8b2  mov     rcx, [rbp+hKey]; hKey
0x18001d8b6  call    cs:__imp_RegCloseKey
0x18001d8bc  mov     eax, [rbp+Data]
0x18001d8bf  add     rsp, 40h
0x18001d8c3  pop     rdi
0x18001d8c4  pop     rsi
0x18001d8c5  pop     rbp
0x18001d8c6  retn
```
