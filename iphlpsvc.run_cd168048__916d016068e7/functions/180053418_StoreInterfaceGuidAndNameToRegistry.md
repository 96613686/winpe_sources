# StoreInterfaceGuidAndNameToRegistry

- ea: `0x180053418`
- end: `0x1800535cf`
- name: `StoreInterfaceGuidAndNameToRegistry`
- size: `439`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180045df8`
- `0x180059318`
- `0x1800598ac`

## callees

- `0x18000d7b0`
- `0x18004b630`
- `0x18005293c`
- `0x180053418`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800535a1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800535a1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800534f7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180053569`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800534f7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180053569`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180053492`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180053492`
- `IPHLPAPI!ConvertGuidToStringW` at `0x18005351e`
- `IPHLPAPI!ConvertGuidToStringW` at `0x18005351e`

## string_xrefs

- `0x1800534ab`: `StoreInterfaceGuidAndNameToRegistry: failed tocreate key %s, status %d`
- `0x18005358b`: `StoreInterfaceGuidAndNameToRegistry: created key %s, name: %s, status: %d`

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
0x180053418  push    rbp
0x18005341a  push    rbx
0x18005341b  push    rsi
0x18005341c  push    rdi
0x18005341d  push    r14
0x18005341f  push    r15
0x180053421  lea     rbp, [rsp-1D8h]
0x180053429  sub     rsp, 2D8h
0x180053430  mov     rax, cs:__security_cookie
0x180053437  xor     rax, rsp
0x18005343a  mov     [rbp+200h+var_40], rax
0x180053441  mov     rsi, r8
0x180053444  xor     r15d, r15d
0x180053447  lea     r8, [rbp+200h+SubKey]
0x18005344b  mov     [rsp+300h+hKey], r15
0x180053450  mov     r14, r9
0x180053453  call    GenerateInterfaceKeyName
0x180053458  test    eax, eax
0x18005345a  jnz     loc_1800535AF
0x180053460  mov     [rsp+300h+lpdwDisposition], r15; lpdwDisposition
0x180053465  lea     rax, [rsp+300h+hKey]
0x18005346a  mov     [rsp+300h+phkResult], rax; phkResult
0x18005346f  lea     rdx, [rbp+200h+SubKey]; lpSubKey
0x180053473  mov     [rsp+300h+lpSecurityAttributes], r15; lpSecurityAttributes
0x180053478  xor     r9d, r9d; lpClass
0x18005347b  mov     [rsp+300h+samDesired], 2001Fh; samDesired
0x180053483  xor     r8d, r8d; Reserved
0x180053486  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005348d  mov     [rsp+300h+dwOptions], r15d; dwOptions
0x180053492  call    cs:__imp_RegCreateKeyExW
0x180053499  nop     dword ptr [rax+rax+00h]
0x18005349e  mov     ebx, eax
0x1800534a0  test    eax, eax
0x1800534a2  jz      short loc_1800534C1
0x1800534a4  mov     r9d, eax
0x1800534a7  lea     r8, [rbp+200h+SubKey]
0x1800534ab  lea     rdx, aStoreinterface; "StoreInterfaceGuidAndNameToRegistry: fa"...
0x1800534b2  mov     ecx, 800000h
0x1800534b7  call    EventWrite0
0x1800534bc  jmp     loc_180053597
0x1800534c1  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800534c5  mov     rax, rdi
0x1800534c8  inc     rax
0x1800534cb  cmp     [rsi+rax*2], r15w
0x1800534d0  jnz     short loc_1800534C8
0x1800534d2  mov     rcx, [rsp+300h+hKey]; hKey
0x1800534d7  lea     eax, ds:2[rax*2]
0x1800534de  mov     [rsp+300h+samDesired], eax; cbData
0x1800534e2  lea     rdx, aInterfacename; "InterfaceName"
0x1800534e9  mov     r9d, 1; dwType
0x1800534ef  mov     qword ptr [rsp+300h+dwOptions], rsi; lpData
0x1800534f4  xor     r8d, r8d; Reserved
0x1800534f7  call    cs:__imp_RegSetValueExW
0x1800534fe  nop     dword ptr [rax+rax+00h]
0x180053503  mov     ebx, eax
0x180053505  test    eax, eax
0x180053507  jnz     loc_180053597
0x18005350d  test    r14, r14
0x180053510  jz      short loc_18005357B
0x180053512  lea     r8d, [rax+27h]
0x180053516  mov     rcx, r14
0x180053519  lea     rdx, [rsp+300h+Data]
0x18005351e  call    cs:__imp_ConvertGuidToStringW
0x180053525  nop     dword ptr [rax+rax+00h]
0x18005352a  mov     ebx, eax
0x18005352c  test    eax, eax
0x18005352e  jnz     short loc_180053597
0x180053530  lea     rax, [rsp+300h+Data]
0x180053535  inc     rdi
0x180053538  cmp     [rax+rdi*2], r15w
0x18005353d  jnz     short loc_180053535
0x18005353f  mov     rcx, [rsp+300h+hKey]; hKey
0x180053544  lea     eax, ds:2[rdi*2]
0x18005354b  mov     [rsp+300h+samDesired], eax; cbData
0x18005354f  lea     rdx, aPhysicalinterf; "PhysicalInterfaceGuid"
0x180053556  lea     rax, [rsp+300h+Data]
0x18005355b  mov     r9d, 1; dwType
0x180053561  xor     r8d, r8d; Reserved
0x180053564  mov     qword ptr [rsp+300h+dwOptions], rax; lpData
0x180053569  call    cs:__imp_RegSetValueExW
0x180053570  nop     dword ptr [rax+rax+00h]
0x180053575  mov     ebx, eax
0x180053577  test    eax, eax
0x180053579  jnz     short loc_180053597
0x18005357b  mov     r9, rsi
0x18005357e  mov     [rsp+300h+dwOptions], ebx
0x180053582  lea     r8, [rbp+200h+SubKey]
0x180053586  mov     ecx, 800000h
0x18005358b  lea     rdx, aStoreinterface_0; "StoreInterfaceGuidAndNameToRegistry: cr"...
0x180053592  call    EventWrite0
0x180053597  mov     rcx, [rsp+300h+hKey]; hKey
0x18005359c  test    rcx, rcx
0x18005359f  jz      short loc_1800535AD
0x1800535a1  call    cs:__imp_RegCloseKey
0x1800535a8  nop     dword ptr [rax+rax+00h]
0x1800535ad  mov     eax, ebx
0x1800535af  mov     rcx, [rbp+200h+var_40]
0x1800535b6  xor     rcx, rsp; StackCookie
0x1800535b9  call    __security_check_cookie
0x1800535be  add     rsp, 2D8h
0x1800535c5  pop     r15
0x1800535c7  pop     r14
0x1800535c9  pop     rdi
0x1800535ca  pop     rsi
0x1800535cb  pop     rbx
0x1800535cc  pop     rbp
0x1800535cd  retn
```
