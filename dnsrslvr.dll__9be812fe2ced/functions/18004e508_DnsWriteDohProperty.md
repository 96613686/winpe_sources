# DnsWriteDohProperty

- ea: `0x18004e508`
- end: `0x18004e66c`
- name: `DnsWriteDohProperty`
- size: `356`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180032978`

## callees

- `0x18003431c`
- `0x180046ec0`
- `0x18004e508`
- `0x1800868b8`
- `0x180086b1c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004e62e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004e62e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18004e647`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18004e647`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004e5e1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004e5e1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004e564`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004e564`

## string_xrefs

- `0x18004e581`: `DohTemplate`

## pseudocode

```c
__int64 __fastcall DnsWriteDohProperty(HKEY hKey, LPCWSTR lpSubKey, __int64 a3)
{
  LSTATUS v6; // eax
  unsigned int v7; // ebx
  unsigned int v8; // eax
  __int64 v9; // rdx
  HKEY hKeya; // [rsp+50h] [rbp-28h] BYREF

  hKeya = 0;
  v6 = RegCreateKeyExW(hKey, lpSubKey, 0, 0, 0, 0x20006u, 0, &hKeya, 0);
  v7 = v6;
  if ( v6 )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_DS(1035, 161, (unsigned int)WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, v6, (__int64)lpSubKey);
  }
  else
  {
    if ( *(_QWORD *)a3 )
    {
      v8 = SetRegistryString(hKeya, L"DohTemplate", *(BYTE **)a3);
      v7 = v8;
      if ( v8 )
      {
        if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
          goto LABEL_12;
        v9 = 162;
        goto LABEL_6;
      }
    }
    v8 = RegSetValueExW(hKeya, L"DohFlags", 0, 0xBu, (const BYTE *)(a3 + 8), 8u);
    v7 = v8;
    if ( v8 && (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    {
      v9 = 163;
LABEL_6:
      WPP_SF_d(1035, v9, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, v8);
    }
  }
LABEL_12:
  if ( hKeya )
  {
    RegCloseKey(hKeya);
    hKeya = 0;
  }
  if ( v7 )
    RegDeleteTreeW(hKey, lpSubKey);
  return v7;
}

```

## disassembly

```asm
0x18004e508  mov     r11, rsp
0x18004e50b  mov     [r11+20h], rbx
0x18004e50f  push    rbp
0x18004e510  push    rsi
0x18004e511  push    rdi
0x18004e512  sub     rsp, 60h
0x18004e516  mov     rax, cs:__security_cookie
0x18004e51d  xor     rax, rsp
0x18004e520  mov     [rsp+78h+var_20], rax
0x18004e525  mov     qword ptr [r11-38h], 0
0x18004e52d  lea     rax, [r11-28h]
0x18004e531  mov     [r11-40h], rax
0x18004e535  mov     rdi, r8
0x18004e538  mov     qword ptr [r11-48h], 0
0x18004e540  xor     r9d, r9d; lpClass
0x18004e543  mov     [rsp+78h+samDesired], 20006h; samDesired
0x18004e54b  xor     r8d, r8d; Reserved
0x18004e54e  mov     [rsp+78h+dwOptions], 0; dwOptions
0x18004e556  mov     rsi, rdx
0x18004e559  mov     rbp, rcx
0x18004e55c  mov     qword ptr [r11-28h], 0
0x18004e564  call    cs:__imp_RegCreateKeyExW
0x18004e56a  mov     ebx, eax
0x18004e56c  test    eax, eax
0x18004e56e  jnz     loc_18004E5FD
0x18004e574  mov     r8, [rdi]; lpData
0x18004e577  test    r8, r8
0x18004e57a  jz      short loc_18004E5BB
0x18004e57c  mov     rcx, [rsp+78h+hKey]; hKey
0x18004e581  lea     rdx, aDohtemplate; "DohTemplate"
0x18004e588  call    SetRegistryString
0x18004e58d  mov     ebx, eax
0x18004e58f  test    eax, eax
0x18004e591  jz      short loc_18004E5BB
0x18004e593  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18004e59a  jz      loc_18004E624
0x18004e5a0  mov     edx, 0A2h
0x18004e5a5  mov     ecx, 40Bh
0x18004e5aa  lea     r8, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids
0x18004e5b1  mov     r9d, eax
0x18004e5b4  call    WPP_SF_d
0x18004e5b9  jmp     short loc_18004E624
0x18004e5bb  mov     rcx, [rsp+78h+hKey]; hKey
0x18004e5c0  lea     rax, [rdi+8]
0x18004e5c4  mov     [rsp+78h+samDesired], 8; cbData
0x18004e5cc  lea     rdx, aDohflags; "DohFlags"
0x18004e5d3  mov     r9d, 0Bh; dwType
0x18004e5d9  mov     qword ptr [rsp+78h+dwOptions], rax; lpData
0x18004e5de  xor     r8d, r8d; Reserved
0x18004e5e1  call    cs:__imp_RegSetValueExW
0x18004e5e7  mov     ebx, eax
0x18004e5e9  test    eax, eax
0x18004e5eb  jz      short loc_18004E624
0x18004e5ed  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18004e5f4  jz      short loc_18004E624
0x18004e5f6  mov     edx, 0A3h
0x18004e5fb  jmp     short loc_18004E5A5
0x18004e5fd  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18004e604  jz      short loc_18004E624
0x18004e606  mov     edx, 0A1h
0x18004e60b  mov     qword ptr [rsp+78h+dwOptions], rsi
0x18004e610  mov     ecx, 40Bh
0x18004e615  lea     r8, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids
0x18004e61c  mov     r9d, eax
0x18004e61f  call    WPP_SF_DS
0x18004e624  mov     rcx, [rsp+78h+hKey]; hKey
0x18004e629  test    rcx, rcx
0x18004e62c  jz      short loc_18004E63D
0x18004e62e  call    cs:__imp_RegCloseKey
0x18004e634  mov     [rsp+78h+hKey], 0
0x18004e63d  test    ebx, ebx
0x18004e63f  jz      short loc_18004E64D
0x18004e641  mov     rdx, rsi; lpSubKey
0x18004e644  mov     rcx, rbp; hKey
0x18004e647  call    cs:__imp_RegDeleteTreeW
0x18004e64d  mov     eax, ebx
0x18004e64f  mov     rcx, [rsp+78h+var_20]
0x18004e654  xor     rcx, rsp; StackCookie
0x18004e657  call    __security_check_cookie
0x18004e65c  mov     rbx, [rsp+78h+arg_18]
0x18004e664  add     rsp, 60h
0x18004e668  pop     rdi
0x18004e669  pop     rsi
0x18004e66a  pop     rbp
0x18004e66b  retn
```
