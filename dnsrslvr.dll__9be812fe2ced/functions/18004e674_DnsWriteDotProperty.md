# DnsWriteDotProperty

- ea: `0x18004e674`
- end: `0x18004e85a`
- name: `DnsWriteDotProperty`
- size: `486`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180032978`

## callees

- `0x18003431c`
- `0x180046ec0`
- `0x18004e674`
- `0x18005ef14`
- `0x1800868b8`
- `0x180086b1c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004e81c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004e81c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18004e732`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18004e732`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18004e835`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18004e835`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004e77b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004e7b9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004e77b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004e7b9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004e6d8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004e6d8`

## pseudocode

```c
__int64 __fastcall DnsWriteDotProperty(HKEY hKey, LPCWSTR lpSubKey, __int64 a3)
{
  LSTATUS v6; // eax
  unsigned int v7; // ebx
  unsigned int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // rdx
  HKEY hKeya; // [rsp+50h] [rbp-38h] BYREF
  BYTE Data[8]; // [rsp+58h] [rbp-30h] BYREF

  hKeya = 0;
  *(_DWORD *)Data = 0;
  v6 = RegCreateKeyExW(hKey, lpSubKey, 0, 0, 0, 0x20006u, 0, &hKeya, 0);
  v7 = v6;
  if ( v6 )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_DS(1035, 164, (unsigned int)WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, v6, (__int64)lpSubKey);
    goto LABEL_18;
  }
  if ( *(_QWORD *)a3 )
  {
    v8 = SetRegistryString(hKeya, L"DotHost", *(BYTE **)a3);
    v7 = v8;
    if ( v8 )
    {
      if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
        goto LABEL_18;
      v9 = 165;
      goto LABEL_6;
    }
LABEL_10:
    v8 = RegSetValueExW(hKeya, L"DotFlags", 0, 0xBu, (const BYTE *)(a3 + 8), 8u);
    v7 = v8;
    if ( v8 )
    {
      if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      {
        v9 = 167;
        goto LABEL_6;
      }
    }
    else
    {
      *(_DWORD *)Data = (unsigned __int16)DnsConvertDotPort(*(unsigned __int16 *)(a3 + 16), v10);
      v8 = RegSetValueExW(hKeya, L"DotPort", 0, 4u, Data, 4u);
      v7 = v8;
      if ( v8 && (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      {
        v9 = 168;
        goto LABEL_6;
      }
    }
    goto LABEL_18;
  }
  v8 = RegDeleteValueW(hKeya, L"DotHost");
  v7 = v8;
  if ( (v8 & 0xFFFFFFFD) == 0 )
    goto LABEL_10;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
  {
    v9 = 166;
LABEL_6:
    WPP_SF_d(1035, v9, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, v8);
  }
LABEL_18:
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
0x18004e674  mov     r11, rsp
0x18004e677  mov     [r11+20h], rbx
0x18004e67b  push    rbp
0x18004e67c  push    rsi
0x18004e67d  push    rdi
0x18004e67e  sub     rsp, 70h
0x18004e682  mov     rax, cs:__security_cookie
0x18004e689  xor     rax, rsp
0x18004e68c  mov     [rsp+88h+var_28], rax
0x18004e691  mov     qword ptr [r11-48h], 0
0x18004e699  lea     rax, [r11-38h]
0x18004e69d  mov     [r11-50h], rax
0x18004e6a1  mov     rdi, r8
0x18004e6a4  mov     qword ptr [r11-58h], 0
0x18004e6ac  xor     r9d, r9d; lpClass
0x18004e6af  mov     [rsp+88h+samDesired], 20006h; samDesired
0x18004e6b7  xor     r8d, r8d; Reserved
0x18004e6ba  mov     [rsp+88h+dwOptions], 0; dwOptions
0x18004e6c2  mov     rsi, rdx
0x18004e6c5  mov     rbp, rcx
0x18004e6c8  mov     qword ptr [r11-38h], 0
0x18004e6d0  mov     dword ptr [rsp+88h+Data], 0
0x18004e6d8  call    cs:__imp_RegCreateKeyExW
0x18004e6de  mov     ebx, eax
0x18004e6e0  test    eax, eax
0x18004e6e2  jnz     loc_18004E7EB
0x18004e6e8  mov     r8, [rdi]; lpData
0x18004e6eb  lea     rdx, aDothost; "DotHost"
0x18004e6f2  mov     rcx, [rsp+88h+hKey]; hKey
0x18004e6f7  test    r8, r8
0x18004e6fa  jz      short loc_18004E732
0x18004e6fc  call    SetRegistryString
0x18004e701  mov     ebx, eax
0x18004e703  test    eax, eax
0x18004e705  jz      short loc_18004E755
0x18004e707  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18004e70e  jz      loc_18004E812
0x18004e714  mov     edx, 0A5h
0x18004e719  mov     ecx, 40Bh
0x18004e71e  lea     r8, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids
0x18004e725  mov     r9d, eax
0x18004e728  call    WPP_SF_d
0x18004e72d  jmp     loc_18004E812
0x18004e732  call    cs:__imp_RegDeleteValueW
0x18004e738  mov     ebx, eax
0x18004e73a  test    eax, 0FFFFFFFDh
0x18004e73f  jz      short loc_18004E755
0x18004e741  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18004e748  jz      loc_18004E812
0x18004e74e  mov     edx, 0A6h
0x18004e753  jmp     short loc_18004E719
0x18004e755  mov     rcx, [rsp+88h+hKey]; hKey
0x18004e75a  lea     rax, [rdi+8]
0x18004e75e  mov     [rsp+88h+samDesired], 8; cbData
0x18004e766  lea     rdx, aDotflags; "DotFlags"
0x18004e76d  mov     r9d, 0Bh; dwType
0x18004e773  mov     qword ptr [rsp+88h+dwOptions], rax; lpData
0x18004e778  xor     r8d, r8d; Reserved
0x18004e77b  call    cs:__imp_RegSetValueExW
0x18004e781  mov     ebx, eax
0x18004e783  test    eax, eax
0x18004e785  jnz     short loc_18004E7D8
0x18004e787  movzx   ecx, word ptr [rdi+10h]
0x18004e78b  call    DnsConvertDotPort
0x18004e790  mov     rcx, [rsp+88h+hKey]; hKey
0x18004e795  lea     r9d, [rbx+4]; dwType
0x18004e799  movzx   eax, ax
0x18004e79c  lea     rdx, aDotport; "DotPort"
0x18004e7a3  mov     dword ptr [rsp+88h+Data], eax
0x18004e7a7  xor     r8d, r8d; Reserved
0x18004e7aa  lea     rax, [rsp+88h+Data]
0x18004e7af  mov     [rsp+88h+samDesired], r9d; cbData
0x18004e7b4  mov     qword ptr [rsp+88h+dwOptions], rax; lpData
0x18004e7b9  call    cs:__imp_RegSetValueExW
0x18004e7bf  mov     ebx, eax
0x18004e7c1  test    eax, eax
0x18004e7c3  jz      short loc_18004E812
0x18004e7c5  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18004e7cc  jz      short loc_18004E812
0x18004e7ce  mov     edx, 0A8h
0x18004e7d3  jmp     loc_18004E719
0x18004e7d8  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18004e7df  jz      short loc_18004E812
0x18004e7e1  mov     edx, 0A7h
0x18004e7e6  jmp     loc_18004E719
0x18004e7eb  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18004e7f2  jz      short loc_18004E812
0x18004e7f4  mov     edx, 0A4h
0x18004e7f9  mov     qword ptr [rsp+88h+dwOptions], rsi
0x18004e7fe  mov     ecx, 40Bh
0x18004e803  lea     r8, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids
0x18004e80a  mov     r9d, eax
0x18004e80d  call    WPP_SF_DS
0x18004e812  mov     rcx, [rsp+88h+hKey]; hKey
0x18004e817  test    rcx, rcx
0x18004e81a  jz      short loc_18004E82B
0x18004e81c  call    cs:__imp_RegCloseKey
0x18004e822  mov     [rsp+88h+hKey], 0
0x18004e82b  test    ebx, ebx
0x18004e82d  jz      short loc_18004E83B
0x18004e82f  mov     rdx, rsi; lpSubKey
0x18004e832  mov     rcx, rbp; hKey
0x18004e835  call    cs:__imp_RegDeleteTreeW
0x18004e83b  mov     eax, ebx
0x18004e83d  mov     rcx, [rsp+88h+var_28]
0x18004e842  xor     rcx, rsp; StackCookie
0x18004e845  call    __security_check_cookie
0x18004e84a  mov     rbx, [rsp+88h+arg_18]
0x18004e852  add     rsp, 70h
0x18004e856  pop     rdi
0x18004e857  pop     rsi
0x18004e858  pop     rbp
0x18004e859  retn
```
