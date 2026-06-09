# DnsConnectionManager::DeleteConnectionIfIndexTable(void)

- ea: `0x180041e00`
- end: `0x18004207c`
- name: `?DeleteConnectionIfIndexTable@DnsConnectionManager@@AEAAJXZ`
- size: `636`
- prototype: `__int64 __fastcall(DnsConnectionManager *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x180041cd8`
- `0x1800437d0`

## callees

- `0x1800097e0`
- `0x180041e00`
- `0x18008b5f0`
- `0x18008bf98`
- `0x1800dbfe0`
- `0x1800dc9e0`
- `0x1800ddfa8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180041f08`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180041fb9`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180041f08`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180041fb9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042051`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042051`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180041f4c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180041f4c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180041fd8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180041fd8`

## string_xrefs

- `0x180041e99`: `Dnscache`
- `0x180041e92`: `SYSTEM\CurrentControlSet\Services\Dnscache`

## pseudocode

```c
__int64 __fastcall DnsConnectionManager::DeleteConnectionIfIndexTable(DnsConnectionManager *this)
{
  int v2; // r9d
  int PersistedRegistryKeyHelper; // eax
  unsigned int v4; // ebx
  DWORD v5; // edi
  unsigned int v6; // eax
  unsigned int v7; // eax
  int v8; // edi
  DWORD cchName; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h]
  WCHAR Name[264]; // [rsp+60h] [rbp-A0h] BYREF

  hKey = 0;
  memset_0(Name, 0, 0x20Au);
  cchName = 261;
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_q(1035, 69, WPP_8d63ef3cf88f3278fb85f81933f2f00e_Traceguids, this);
  PersistedRegistryKeyHelper = CreatePersistedRegistryKeyHelper(
                                 (unsigned int)L"Dnscache",
                                 (unsigned int)L"SYSTEM\\CurrentControlSet\\Services\\Dnscache",
                                 (unsigned int)L"Parameters\\DnsActiveIfs",
                                 v2,
                                 131103);
  v4 = PersistedRegistryKeyHelper;
  if ( PersistedRegistryKeyHelper == 1168 || PersistedRegistryKeyHelper == 2 )
  {
    v4 = 0;
  }
  else
  {
    if ( PersistedRegistryKeyHelper > 0 )
      v4 = (unsigned __int16)PersistedRegistryKeyHelper | 0x80070000;
    if ( (v4 & 0x80000000) == 0 )
    {
      v5 = 0;
      if ( !RegEnumKeyExW(hKey, 0, Name, &cchName, 0, 0, 0, 0) )
      {
        do
        {
          if ( (BYTE3(xmmword_1801119E0) & 0x40) != 0 )
            WPP_SF_S(1054, 70, WPP_8d63ef3cf88f3278fb85f81933f2f00e_Traceguids, Name);
          v6 = RegDeleteKeyExW(hKey, Name, 0, 0);
          if ( v6 )
          {
            ++v5;
            if ( (byte_1801119D3 & 0x40) != 0 )
              WPP_SF_d(542, 71, WPP_8d63ef3cf88f3278fb85f81933f2f00e_Traceguids, v6);
          }
          cchName = 261;
        }
        while ( !RegEnumKeyExW(hKey, v5, Name, &cchName, 0, 0, 0, 0) );
        if ( v5 )
        {
          v7 = RegDeleteTreeW(hKey, 0);
          v8 = v7;
          if ( v7 )
          {
            if ( (byte_1801119D3 & 0x40) != 0 )
              WPP_SF_d(542, 72, WPP_8d63ef3cf88f3278fb85f81933f2f00e_Traceguids, v7);
            if ( v8 > 0 )
              v4 = (unsigned __int16)v8 | 0x80070000;
            else
              v4 = v8;
          }
        }
      }
    }
  }
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_d(1035, 73, WPP_8d63ef3cf88f3278fb85f81933f2f00e_Traceguids, v4);
  if ( hKey )
    RegCloseKey(hKey);
  return v4;
}

```

## disassembly

```asm
0x180041e00  push    rbp
0x180041e02  push    rbx
0x180041e03  push    rdi
0x180041e04  push    r15
0x180041e06  lea     rbp, [rsp-188h]
0x180041e0e  sub     rsp, 288h
0x180041e15  mov     rax, cs:__security_cookie
0x180041e1c  xor     rax, rsp
0x180041e1f  mov     [rbp+1A0h+var_30], rax
0x180041e26  mov     rbx, rcx
0x180041e29  mov     [rsp+2A0h+var_25C], 0
0x180041e31  lea     rcx, [rsp+2A0h+Name]; void *
0x180041e36  mov     [rsp+2A0h+hKey], 0
0x180041e3f  xor     edx, edx; Val
0x180041e41  mov     r8d, 20Ah; Size
0x180041e47  call    memset_0
0x180041e4c  mov     [rsp+2A0h+cchName], 105h
0x180041e54  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180041e5b  lea     r15, WPP_8d63ef3cf88f3278fb85f81933f2f00e_Traceguids
0x180041e62  jz      short loc_180041E79
0x180041e64  mov     edx, 45h ; 'E'
0x180041e69  mov     ecx, 40Bh
0x180041e6e  mov     r9, rbx
0x180041e71  mov     r8, r15
0x180041e74  call    WPP_SF_q
0x180041e79  lea     rax, [rsp+2A0h+hKey]
0x180041e7e  mov     [rsp+2A0h+lpftLastWriteTime], rax
0x180041e83  lea     r8, aParametersDnsa; "Parameters\\DnsActiveIfs"
0x180041e8a  mov     dword ptr [rsp+2A0h+lpcchClass], 0
0x180041e92  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Dn"...
0x180041e99  lea     rcx, aDnscache_1; "Dnscache"
0x180041ea0  mov     dword ptr [rsp+2A0h+lpReserved], 2001Fh
0x180041ea8  call    CreatePersistedRegistryKeyHelper
0x180041ead  mov     ebx, eax
0x180041eaf  cmp     eax, 490h
0x180041eb4  jz      loc_180042027
0x180041eba  cmp     eax, 2
0x180041ebd  jz      loc_180042027
0x180041ec3  test    eax, eax
0x180041ec5  jle     short loc_180041ED0
0x180041ec7  movzx   ebx, ax
0x180041eca  or      ebx, 80070000h
0x180041ed0  test    ebx, ebx
0x180041ed2  jns     short loc_180041EE1
0x180041ed4  mov     [rsp+2A0h+var_25C], 65Ch
0x180041edc  jmp     loc_180042029
0x180041ee1  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180041ee6  lea     r9, [rsp+2A0h+cchName]; lpcchName
0x180041eeb  xor     edi, edi
0x180041eed  lea     r8, [rsp+2A0h+Name]; lpName
0x180041ef2  mov     [rsp+2A0h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x180041ef7  xor     edx, edx; dwIndex
0x180041ef9  mov     [rsp+2A0h+lpcchClass], rdi; lpcchClass
0x180041efe  mov     [rsp+2A0h+lpClass], rdi; lpClass
0x180041f03  mov     [rsp+2A0h+lpReserved], rdi; lpReserved
0x180041f08  call    cs:__imp_RegEnumKeyExW
0x180041f0f  nop     dword ptr [rax+rax+00h]
0x180041f14  test    eax, eax
0x180041f16  jnz     loc_180042029
0x180041f1c  test    byte ptr cs:xmmword_1801119E0+3, 40h
0x180041f23  jz      short loc_180041F3C
0x180041f25  mov     edx, 46h ; 'F'
0x180041f2a  lea     r9, [rsp+2A0h+Name]
0x180041f2f  mov     ecx, 41Eh
0x180041f34  mov     r8, r15
0x180041f37  call    WPP_SF_S
0x180041f3c  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180041f41  lea     rdx, [rsp+2A0h+Name]; lpSubKey
0x180041f46  xor     r9d, r9d; Reserved
0x180041f49  xor     r8d, r8d; samDesired
0x180041f4c  call    cs:__imp_RegDeleteKeyExW
0x180041f53  nop     dword ptr [rax+rax+00h]
0x180041f58  test    eax, eax
0x180041f5a  jz      short loc_180041F7C
0x180041f5c  inc     edi
0x180041f5e  test    cs:byte_1801119D3, 40h
0x180041f65  jz      short loc_180041F7C
0x180041f67  mov     edx, 47h ; 'G'
0x180041f6c  mov     ecx, 21Eh
0x180041f71  mov     r9d, eax
0x180041f74  mov     r8, r15
0x180041f77  call    WPP_SF_d
0x180041f7c  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180041f81  lea     r9, [rsp+2A0h+cchName]; lpcchName
0x180041f86  mov     [rsp+2A0h+lpftLastWriteTime], 0; lpftLastWriteTime
0x180041f8f  lea     r8, [rsp+2A0h+Name]; lpName
0x180041f94  mov     [rsp+2A0h+lpcchClass], 0; lpcchClass
0x180041f9d  mov     edx, edi; dwIndex
0x180041f9f  mov     [rsp+2A0h+lpClass], 0; lpClass
0x180041fa8  mov     [rsp+2A0h+lpReserved], 0; lpReserved
0x180041fb1  mov     [rsp+2A0h+cchName], 105h
0x180041fb9  call    cs:__imp_RegEnumKeyExW
0x180041fc0  nop     dword ptr [rax+rax+00h]
0x180041fc5  test    eax, eax
0x180041fc7  jz      loc_180041F1C
0x180041fcd  test    edi, edi
0x180041fcf  jz      short loc_180042029
0x180041fd1  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180041fd6  xor     edx, edx; lpSubKey
0x180041fd8  call    cs:__imp_RegDeleteTreeW
0x180041fdf  nop     dword ptr [rax+rax+00h]
0x180041fe4  mov     edi, eax
0x180041fe6  test    eax, eax
0x180041fe8  jz      short loc_180042029
0x180041fea  test    cs:byte_1801119D3, 40h
0x180041ff1  jz      short loc_180042008
0x180041ff3  mov     edx, 48h ; 'H'
0x180041ff8  mov     ecx, 21Eh
0x180041ffd  mov     r9d, eax
0x180042000  mov     r8, r15
0x180042003  call    WPP_SF_d
0x180042008  test    edi, edi
0x18004200a  jg      short loc_180042010
0x18004200c  mov     ebx, edi
0x18004200e  jmp     short loc_180042019
0x180042010  movzx   ebx, di
0x180042013  or      ebx, 80070000h
0x180042019  test    ebx, ebx
0x18004201b  jns     short loc_180042029
0x18004201d  mov     [rsp+2A0h+var_25C], 68Ah
0x180042025  jmp     short loc_180042029
0x180042027  xor     ebx, ebx
0x180042029  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180042030  jz      short loc_180042047
0x180042032  mov     edx, 49h ; 'I'
0x180042037  mov     ecx, 40Bh
0x18004203c  mov     r9d, ebx
0x18004203f  mov     r8, r15
0x180042042  call    WPP_SF_d
0x180042047  mov     rcx, [rsp+2A0h+hKey]; hKey
0x18004204c  test    rcx, rcx
0x18004204f  jz      short loc_18004205D
0x180042051  call    cs:__imp_RegCloseKey
0x180042058  nop     dword ptr [rax+rax+00h]
0x18004205d  mov     eax, ebx
0x18004205f  mov     rcx, [rbp+1A0h+var_30]
0x180042066  xor     rcx, rsp; StackCookie
0x180042069  call    __security_check_cookie
0x18004206e  add     rsp, 288h
0x180042075  pop     r15
0x180042077  pop     rdi
0x180042078  pop     rbx
0x180042079  pop     rbp
0x18004207a  retn
```
