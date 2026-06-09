# StoreInterfaceGuidAndNameToRegistry

- ea: `0x1800533d8`
- end: `0x18005358f`
- name: `StoreInterfaceGuidAndNameToRegistry`
- size: `439`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180045db8`
- `0x180059338`
- `0x1800598cc`

## callees

- `0x18000d7c0`
- `0x18004b5f0`
- `0x1800528fc`
- `0x1800533d8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180053561`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180053561`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800534b7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180053529`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800534b7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180053529`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180053452`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180053452`
- `IPHLPAPI!ConvertGuidToStringW` at `0x1800534de`
- `IPHLPAPI!ConvertGuidToStringW` at `0x1800534de`

## string_xrefs

- `0x18005346b`: `StoreInterfaceGuidAndNameToRegistry: failed tocreate key %s, status %d`
- `0x18005354b`: `StoreInterfaceGuidAndNameToRegistry: created key %s, name: %s, status: %d`

## pseudocode

```c
__int64 __fastcall StoreInterfaceGuidAndNameToRegistry(__int64 a1, __int64 a2, const BYTE *a3, __int64 a4)
{
  __int64 result; // rax
  unsigned int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rdi
  __int64 v10; // rax
  DWORD dwOptions[2]; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  _WORD Data[40]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR SubKey[264]; // [rsp+B0h] [rbp-50h] BYREF

  hKey = 0;
  result = GenerateInterfaceKeyName(a1, a2, SubKey);
  if ( !(_DWORD)result )
  {
    v7 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x2001Fu, 0, &hKey, 0);
    v8 = v7;
    if ( v7 )
    {
      EventWrite0(0x800000, L"StoreInterfaceGuidAndNameToRegistry: failed tocreate key %s, status %d", SubKey, v7);
    }
    else
    {
      v9 = -1;
      v10 = -1;
      do
        ++v10;
      while ( *(_WORD *)&a3[2 * v10] );
      v8 = RegSetValueExW(hKey, L"InterfaceName", 0, 1u, a3, 2 * v10 + 2);
      if ( !v8 )
      {
        if ( !a4 )
          goto LABEL_11;
        v8 = ConvertGuidToStringW(a4, Data, 39);
        if ( !v8 )
        {
          do
            ++v9;
          while ( Data[v9] );
          v8 = RegSetValueExW(hKey, L"PhysicalInterfaceGuid", 0, 1u, (const BYTE *)Data, 2 * v9 + 2);
          if ( !v8 )
          {
LABEL_11:
            dwOptions[0] = v8;
            EventWrite0(
              0x800000,
              L"StoreInterfaceGuidAndNameToRegistry: created key %s, name: %s, status: %d",
              SubKey,
              a3,
              *(_QWORD *)dwOptions);
          }
        }
      }
    }
    if ( hKey )
      RegCloseKey(hKey);
    return v8;
  }
  return result;
}

```

## disassembly

```asm
0x1800533d8  push    rbp
0x1800533da  push    rbx
0x1800533db  push    rsi
0x1800533dc  push    rdi
0x1800533dd  push    r14
0x1800533df  push    r15
0x1800533e1  lea     rbp, [rsp-1D8h]
0x1800533e9  sub     rsp, 2D8h
0x1800533f0  mov     rax, cs:__security_cookie
0x1800533f7  xor     rax, rsp
0x1800533fa  mov     [rbp+200h+var_40], rax
0x180053401  mov     rsi, r8
0x180053404  xor     r15d, r15d
0x180053407  lea     r8, [rbp+200h+SubKey]
0x18005340b  mov     [rsp+300h+hKey], r15
0x180053410  mov     r14, r9
0x180053413  call    GenerateInterfaceKeyName
0x180053418  test    eax, eax
0x18005341a  jnz     loc_18005356F
0x180053420  mov     [rsp+300h+lpdwDisposition], r15; lpdwDisposition
0x180053425  lea     rax, [rsp+300h+hKey]
0x18005342a  mov     [rsp+300h+phkResult], rax; phkResult
0x18005342f  lea     rdx, [rbp+200h+SubKey]; lpSubKey
0x180053433  mov     [rsp+300h+lpSecurityAttributes], r15; lpSecurityAttributes
0x180053438  xor     r9d, r9d; lpClass
0x18005343b  mov     [rsp+300h+samDesired], 2001Fh; samDesired
0x180053443  xor     r8d, r8d; Reserved
0x180053446  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005344d  mov     [rsp+300h+dwOptions], r15d; dwOptions
0x180053452  call    cs:__imp_RegCreateKeyExW
0x180053459  nop     dword ptr [rax+rax+00h]
0x18005345e  mov     ebx, eax
0x180053460  test    eax, eax
0x180053462  jz      short loc_180053481
0x180053464  mov     r9d, eax
0x180053467  lea     r8, [rbp+200h+SubKey]
0x18005346b  lea     rdx, aStoreinterface; "StoreInterfaceGuidAndNameToRegistry: fa"...
0x180053472  mov     ecx, 800000h
0x180053477  call    EventWrite0
0x18005347c  jmp     loc_180053557
0x180053481  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180053485  mov     rax, rdi
0x180053488  inc     rax
0x18005348b  cmp     [rsi+rax*2], r15w
0x180053490  jnz     short loc_180053488
0x180053492  mov     rcx, [rsp+300h+hKey]; hKey
0x180053497  lea     eax, ds:2[rax*2]
0x18005349e  mov     [rsp+300h+samDesired], eax; cbData
0x1800534a2  lea     rdx, aInterfacename; "InterfaceName"
0x1800534a9  mov     r9d, 1; dwType
0x1800534af  mov     qword ptr [rsp+300h+dwOptions], rsi; lpData
0x1800534b4  xor     r8d, r8d; Reserved
0x1800534b7  call    cs:__imp_RegSetValueExW
0x1800534be  nop     dword ptr [rax+rax+00h]
0x1800534c3  mov     ebx, eax
0x1800534c5  test    eax, eax
0x1800534c7  jnz     loc_180053557
0x1800534cd  test    r14, r14
0x1800534d0  jz      short loc_18005353B
0x1800534d2  lea     r8d, [rax+27h]
0x1800534d6  mov     rcx, r14
0x1800534d9  lea     rdx, [rsp+300h+Data]
0x1800534de  call    cs:__imp_ConvertGuidToStringW
0x1800534e5  nop     dword ptr [rax+rax+00h]
0x1800534ea  mov     ebx, eax
0x1800534ec  test    eax, eax
0x1800534ee  jnz     short loc_180053557
0x1800534f0  lea     rax, [rsp+300h+Data]
0x1800534f5  inc     rdi
0x1800534f8  cmp     [rax+rdi*2], r15w
0x1800534fd  jnz     short loc_1800534F5
0x1800534ff  mov     rcx, [rsp+300h+hKey]; hKey
0x180053504  lea     eax, ds:2[rdi*2]
0x18005350b  mov     [rsp+300h+samDesired], eax; cbData
0x18005350f  lea     rdx, aPhysicalinterf; "PhysicalInterfaceGuid"
0x180053516  lea     rax, [rsp+300h+Data]
0x18005351b  mov     r9d, 1; dwType
0x180053521  xor     r8d, r8d; Reserved
0x180053524  mov     qword ptr [rsp+300h+dwOptions], rax; lpData
0x180053529  call    cs:__imp_RegSetValueExW
0x180053530  nop     dword ptr [rax+rax+00h]
0x180053535  mov     ebx, eax
0x180053537  test    eax, eax
0x180053539  jnz     short loc_180053557
0x18005353b  mov     r9, rsi
0x18005353e  mov     [rsp+300h+dwOptions], ebx
0x180053542  lea     r8, [rbp+200h+SubKey]
0x180053546  mov     ecx, 800000h
0x18005354b  lea     rdx, aStoreinterface_0; "StoreInterfaceGuidAndNameToRegistry: cr"...
0x180053552  call    EventWrite0
0x180053557  mov     rcx, [rsp+300h+hKey]; hKey
0x18005355c  test    rcx, rcx
0x18005355f  jz      short loc_18005356D
0x180053561  call    cs:__imp_RegCloseKey
0x180053568  nop     dword ptr [rax+rax+00h]
0x18005356d  mov     eax, ebx
0x18005356f  mov     rcx, [rbp+200h+var_40]
0x180053576  xor     rcx, rsp; StackCookie
0x180053579  call    __security_check_cookie
0x18005357e  add     rsp, 2D8h
0x180053585  pop     r15
0x180053587  pop     r14
0x180053589  pop     rdi
0x18005358a  pop     rsi
0x18005358b  pop     rbx
0x18005358c  pop     rbp
0x18005358d  retn
```
