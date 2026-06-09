# SetDhcpEnabledForDisconnectedAdapter

- ea: `0x18002e5f4`
- end: `0x18002e8c8`
- name: `SetDhcpEnabledForDisconnectedAdapter`
- size: `724`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1800022fc`

## callees

- `0x1800069d0`
- `0x180019248`
- `0x180019ba8`
- `0x18001cef0`
- `0x18001d826`
- `0x18002e5f4`
- `0x180049ae8`
- `0x18004d4c0`
- `0x18004d958`
- `0x18004e400`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18002e86d`
- `ntdll!RtlFreeUnicodeString` at `0x18002e86d`
- `ntdll!RtlStringFromGUID` at `0x18002e6fd`
- `ntdll!RtlStringFromGUID` at `0x18002e6fd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e83c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e854`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e83c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e854`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e746`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e76f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e746`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e76f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e803`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e82a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e803`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e82a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002e81b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002e81b`

## string_xrefs

- `0x18002e71b`: `System\CurrentControlSet\Services\Tcpip\Parameters\Interfaces`

## pseudocode

```c
__int64 __fastcall SetDhcpEnabledForDisconnectedAdapter(__int64 a1, int a2)
{
  char v3; // bl
  int v4; // ecx
  int v5; // r8d
  const char *v6; // r9
  unsigned int AllParameters; // ebx
  unsigned int v8; // eax
  BOOL IsWCOSSystem; // eax
  const WCHAR *v10; // rdx
  HKEY phkResult; // [rsp+70h] [rbp-90h] BYREF
  BYTE Data[8]; // [rsp+78h] [rbp-88h] BYREF
  HKEY hKey; // [rsp+80h] [rbp-80h] BYREF
  __int64 v15; // [rsp+88h] [rbp-78h] BYREF
  struct _UNICODE_STRING GuidString; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v17[536]; // [rsp+A0h] [rbp-60h] BYREF
  GUID Guid; // [rsp+2B8h] [rbp+1B8h] BYREF

  v15 = a1;
  v3 = a1;
  *(_DWORD *)Data = 1;
  memset_0(v17, 0, 0x238u);
  phkResult = 0;
  GuidString = 0;
  hKey = 0;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
  {
    v6 = "Enable";
    if ( !a2 )
      v6 = "Disable";
    WPP_SF_sJ(v4, 13, v5, (_DWORD)v6, v3);
  }
  AllParameters = GetAllParameters(
                    0,
                    (unsigned int)&NPI_MS_NDIS_MODULEID,
                    1,
                    (unsigned int)&v15,
                    8,
                    0,
                    0,
                    0,
                    0,
                    (__int64)v17,
                    568,
                    1,
                    0);
  if ( !AllParameters )
  {
    v8 = RtlStringFromGUID(&Guid, &GuidString);
    AllParameters = Win32FromNTSTATUS(v8);
    if ( !AllParameters )
    {
      IsWCOSSystem = DhcpIsWCOSSystem();
      v10 = L"OSDATA\\Networking\\Dhcp\\Client4";
      if ( !IsWCOSSystem )
        v10 = L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters\\Interfaces";
      AllParameters = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v10, 0, 0x2001Bu, &hKey);
      if ( !AllParameters )
      {
        AllParameters = RegOpenKeyExW(hKey, GuidString.Buffer, 0, 2u, &phkResult);
        if ( AllParameters )
        {
          if ( (xmmword_1800616A0 & 2) != 0 )
            WPP_SF_DJ_guid_(
              1025,
              14,
              (unsigned int)WPP_8f191193bd893a0df37ce357b02d0085_Traceguids,
              AllParameters,
              v15,
              (__int64)&Guid);
        }
        else
        {
          if ( (xmmword_1800616A0 & 0x10) != 0 )
            WPP_SF_q(1028, 15, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids, v15);
          if ( a2 )
          {
            AllParameters = RegSetValueExW(phkResult, L"EnableDhcp", 0, 4u, Data, 4u);
            if ( !AllParameters )
              RegDeleteValueW(phkResult, L"DisableDhcpOnConnect");
          }
          else
          {
            AllParameters = RegSetValueExW(phkResult, L"DisableDhcpOnConnect", 0, 4u, Data, 4u);
          }
        }
      }
    }
  }
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( GuidString.Buffer )
  {
    RtlFreeUnicodeString(&GuidString);
    GuidString.Buffer = 0;
  }
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_qD(1028, 16, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids, v15, AllParameters);
  return AllParameters;
}

```

## disassembly

```asm
0x18002e5f4  mov     [rsp-8+arg_8], rbx
0x18002e5f9  mov     [rsp-8+arg_10], rdi
0x18002e5fe  push    rbp
0x18002e5ff  lea     rbp, [rsp-1F0h]
0x18002e607  sub     rsp, 2F0h
0x18002e60e  mov     rax, cs:__security_cookie
0x18002e615  xor     rax, rsp
0x18002e618  mov     [rbp+1F0h+var_10], rax
0x18002e61f  mov     edi, edx
0x18002e621  mov     [rbp+1F0h+var_268], rcx
0x18002e625  mov     rbx, rcx
0x18002e628  mov     dword ptr [rsp+2F0h+Data], 1
0x18002e630  xor     edx, edx; Val
0x18002e632  lea     rcx, [rbp+1F0h+var_250]; void *
0x18002e636  mov     r8d, 238h; Size
0x18002e63c  call    memset_0
0x18002e641  xorps   xmm0, xmm0
0x18002e644  mov     [rsp+2F0h+var_280], 0
0x18002e64d  movups  xmmword ptr [rbp+1F0h+GuidString.Length], xmm0
0x18002e651  mov     [rbp+1F0h+hKey], 0
0x18002e659  test    byte ptr cs:xmmword_1800616A0, 10h
0x18002e660  jz      short loc_18002E685
0x18002e662  test    edi, edi
0x18002e664  mov     [rsp+2F0h+phkResult], rbx
0x18002e669  lea     rax, aDisable; "Disable"
0x18002e670  mov     edx, 0Dh
0x18002e675  lea     r9, aEnable; "Enable"
0x18002e67c  cmovz   r9, rax
0x18002e680  call    WPP_SF_sJ
0x18002e685  mov     [rsp+2F0h+var_290], 0
0x18002e68d  lea     rax, [rbp+1F0h+var_250]
0x18002e691  mov     [rsp+2F0h+var_298], 1
0x18002e699  lea     r9, [rbp+1F0h+var_268]
0x18002e69d  mov     [rsp+2F0h+var_2A0], 238h
0x18002e6a5  lea     rdx, NPI_MS_NDIS_MODULEID
0x18002e6ac  mov     [rsp+2F0h+var_2A8], rax
0x18002e6b1  mov     r8d, 1
0x18002e6b7  mov     [rsp+2F0h+var_2B0], 0
0x18002e6bf  xor     ecx, ecx
0x18002e6c1  mov     [rsp+2F0h+var_2B8], 0
0x18002e6ca  mov     [rsp+2F0h+var_2C0], 0
0x18002e6d2  mov     qword ptr [rsp+2F0h+cbData], 0
0x18002e6db  mov     dword ptr [rsp+2F0h+phkResult], 8
0x18002e6e3  call    GetAllParameters
0x18002e6e8  mov     ebx, eax
0x18002e6ea  test    eax, eax
0x18002e6ec  jnz     loc_18002E832
0x18002e6f2  lea     rdx, [rbp+1F0h+GuidString]; GuidString
0x18002e6f6  lea     rcx, [rbp+1F0h+Guid]; Guid
0x18002e6fd  call    cs:__imp_RtlStringFromGUID
0x18002e703  mov     ecx, eax
0x18002e705  call    Win32FromNTSTATUS
0x18002e70a  mov     ebx, eax
0x18002e70c  test    eax, eax
0x18002e70e  jnz     loc_18002E832
0x18002e714  call    DhcpIsWCOSSystem
0x18002e719  test    eax, eax
0x18002e71b  lea     rcx, aSystemCurrentc_15; "System\\CurrentControlSet\\Services\\Tc"...
0x18002e722  lea     rax, [rbp+1F0h+hKey]
0x18002e726  mov     r9d, 2001Bh; samDesired
0x18002e72c  lea     rdx, aOsdataNetworki; "OSDATA\\Networking\\Dhcp\\Client4"
0x18002e733  mov     [rsp+2F0h+phkResult], rax; phkResult
0x18002e738  cmovz   rdx, rcx; lpSubKey
0x18002e73c  xor     r8d, r8d; ulOptions
0x18002e73f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002e746  call    cs:__imp_RegOpenKeyExW
0x18002e74c  mov     ebx, eax
0x18002e74e  test    eax, eax
0x18002e750  jnz     loc_18002E832
0x18002e756  mov     rdx, [rbp+1F0h+GuidString.Buffer]; lpSubKey
0x18002e75a  lea     rax, [rsp+2F0h+var_280]
0x18002e75f  mov     rcx, [rbp+1F0h+hKey]; hKey
0x18002e763  lea     r9d, [rbx+2]; samDesired
0x18002e767  xor     r8d, r8d; ulOptions
0x18002e76a  mov     [rsp+2F0h+phkResult], rax; phkResult
0x18002e76f  call    cs:__imp_RegOpenKeyExW
0x18002e775  mov     ebx, eax
0x18002e777  test    eax, eax
0x18002e779  jz      short loc_18002E7B8
0x18002e77b  test    byte ptr cs:xmmword_1800616A0, 2
0x18002e782  jz      loc_18002E832
0x18002e788  lea     rax, [rbp+1F0h+Guid]
0x18002e78f  mov     edx, 0Eh
0x18002e794  mov     qword ptr [rsp+2F0h+cbData], rax
0x18002e799  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x18002e7a0  mov     rax, [rbp+1F0h+var_268]
0x18002e7a4  mov     ecx, 401h
0x18002e7a9  mov     r9d, ebx
0x18002e7ac  mov     [rsp+2F0h+phkResult], rax
0x18002e7b1  call    WPP_SF_DJ_guid_
0x18002e7b6  jmp     short loc_18002E832
0x18002e7b8  test    byte ptr cs:xmmword_1800616A0, 10h
0x18002e7bf  jz      short loc_18002E7DB
0x18002e7c1  mov     r9, [rbp+1F0h+var_268]
0x18002e7c5  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x18002e7cc  mov     edx, 0Fh
0x18002e7d1  mov     ecx, 404h
0x18002e7d6  call    WPP_SF_q
0x18002e7db  mov     rcx, [rsp+2F0h+var_280]; hKey
0x18002e7e0  lea     rax, [rsp+2F0h+Data]
0x18002e7e5  mov     r9d, 4; dwType
0x18002e7eb  xor     r8d, r8d; Reserved
0x18002e7ee  mov     [rsp+2F0h+cbData], r9d; cbData
0x18002e7f3  mov     [rsp+2F0h+phkResult], rax; lpData
0x18002e7f8  test    edi, edi
0x18002e7fa  jz      short loc_18002E823
0x18002e7fc  lea     rdx, aEnabledhcp; "EnableDhcp"
0x18002e803  call    cs:__imp_RegSetValueExW
0x18002e809  mov     ebx, eax
0x18002e80b  test    eax, eax
0x18002e80d  jnz     short loc_18002E832
0x18002e80f  mov     rcx, [rsp+2F0h+var_280]; hKey
0x18002e814  lea     rdx, aDisabledhcponc; "DisableDhcpOnConnect"
0x18002e81b  call    cs:__imp_RegDeleteValueW
0x18002e821  jmp     short loc_18002E832
0x18002e823  lea     rdx, aDisabledhcponc; "DisableDhcpOnConnect"
0x18002e82a  call    cs:__imp_RegSetValueExW
0x18002e830  mov     ebx, eax
0x18002e832  mov     rcx, [rsp+2F0h+var_280]; hKey
0x18002e837  test    rcx, rcx
0x18002e83a  jz      short loc_18002E84B
0x18002e83c  call    cs:__imp_RegCloseKey
0x18002e842  mov     [rsp+2F0h+var_280], 0
0x18002e84b  mov     rcx, [rbp+1F0h+hKey]; hKey
0x18002e84f  test    rcx, rcx
0x18002e852  jz      short loc_18002E862
0x18002e854  call    cs:__imp_RegCloseKey
0x18002e85a  mov     [rbp+1F0h+hKey], 0
0x18002e862  cmp     [rbp+1F0h+GuidString.Buffer], 0
0x18002e867  jz      short loc_18002E87B
0x18002e869  lea     rcx, [rbp+1F0h+GuidString]; UnicodeString
0x18002e86d  call    cs:__imp_RtlFreeUnicodeString
0x18002e873  mov     [rbp+1F0h+GuidString.Buffer], 0
0x18002e87b  test    byte ptr cs:xmmword_1800616A0, 10h
0x18002e882  jz      short loc_18002E8A2
0x18002e884  mov     r9, [rbp+1F0h+var_268]
0x18002e888  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x18002e88f  mov     edx, 10h
0x18002e894  mov     dword ptr [rsp+2F0h+phkResult], ebx
0x18002e898  mov     ecx, 404h
0x18002e89d  call    WPP_SF_qD
0x18002e8a2  mov     eax, ebx
0x18002e8a4  mov     rcx, [rbp+1F0h+var_10]
0x18002e8ab  xor     rcx, rsp; StackCookie
0x18002e8ae  call    __security_check_cookie
0x18002e8b3  lea     r11, [rsp+2F0h+var_s0]
0x18002e8bb  mov     rbx, [r11+18h]
0x18002e8bf  mov     rdi, [r11+20h]
0x18002e8c3  mov     rsp, r11
0x18002e8c6  pop     rbp
0x18002e8c7  retn
```
