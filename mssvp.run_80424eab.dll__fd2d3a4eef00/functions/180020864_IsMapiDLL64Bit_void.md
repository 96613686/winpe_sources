# IsMapiDLL64Bit(void)

- ea: `0x180020864`
- end: `0x180020a3f`
- name: `?IsMapiDLL64Bit@@YA_NXZ`
- size: `475`
- prototype: `bool(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180019a20`
- `0x180020b00`

## callees

- `0x180006270`
- `0x180006dcc`
- `0x180020864`
- `0x180028bdc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800208bb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180020948`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800208bb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180020948`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020a08`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020a13`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020a08`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020a13`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800209cb`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800209cb`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x1800209e2`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x1800209e2`
- `api-ms-win-shcore-registry-l1-1-0!SHRegGetValueW` at `0x180020912`
- `api-ms-win-shcore-registry-l1-1-0!SHRegGetValueW` at `0x18002099e`
- `api-ms-win-shcore-registry-l1-1-0!SHRegGetValueW` at `0x180020912`
- `api-ms-win-shcore-registry-l1-1-0!SHRegGetValueW` at `0x18002099e`

## string_xrefs

- `0x180020976`: `DLLPathEx`

## pseudocode

```c
bool IsMapiDLL64Bit(void)
{
  bool v0; // bl
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Dst[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR SubKey[264]; // [rsp+270h] [rbp+170h] BYREF
  WCHAR Src[264]; // [rsp+480h] [rbp+380h] BYREF

  hkey = 0;
  v0 = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Clients\\Mail", 0, 0x20019u, &hkey) )
  {
    memset_0(SubKey, 0, 0x208u);
    pcbData = 520;
    if ( !SHRegGetValueW(hkey, 0, 0, 2, 0, SubKey, &pcbData) )
    {
      hKey = 0;
      if ( !RegOpenKeyExW(hkey, SubKey, 0, 0x20019u, &hKey) )
      {
        memset_0(Src, 0, 0x208u);
        pcbData = 520;
        if ( !SHRegGetValueW(hKey, 0, L"DLLPathEx", 2, 0, Src, &pcbData) )
        {
          memset_0(Dst, 0, 0x208u);
          if ( ExpandEnvironmentStringsW(Src, Dst, 0x104u) )
          {
            if ( GetLongPathNameW(Dst, Dst, 0x104u) )
              v0 = (unsigned int)Is64bitDll(Dst) != 0;
          }
        }
        RegCloseKey(hKey);
      }
    }
    RegCloseKey(hkey);
  }
  return v0;
}

```

## disassembly

```asm
0x180020864  mov     [rsp-8+arg_0], rbx
0x180020869  mov     [rsp-8+arg_8], rsi
0x18002086e  push    rbp
0x18002086f  lea     rbp, [rsp-5A0h]
0x180020877  sub     rsp, 6A0h
0x18002087e  mov     rax, cs:__security_cookie
0x180020885  xor     rax, rsp
0x180020888  mov     [rbp+5A0h+var_10], rax
0x18002088f  lea     rax, [rsp+6A0h+hkey]
0x180020894  mov     [rsp+6A0h+hkey], 0
0x18002089d  mov     r9d, 20019h; samDesired
0x1800208a3  mov     [rsp+6A0h+phkResult], rax; phkResult
0x1800208a8  xor     r8d, r8d; ulOptions
0x1800208ab  lea     rdx, SubKey; "Software\\Clients\\Mail"
0x1800208b2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800208b9  xor     bl, bl
0x1800208bb  call    cs:__imp_RegOpenKeyExW
0x1800208c1  test    eax, eax
0x1800208c3  jnz     loc_180020A19
0x1800208c9  mov     esi, 208h
0x1800208ce  lea     rcx, [rbp+5A0h+SubKey]; void *
0x1800208d5  mov     r8d, esi; Size
0x1800208d8  xor     edx, edx; Val
0x1800208da  call    memset_0
0x1800208df  mov     rcx, [rsp+6A0h+hkey]; hkey
0x1800208e4  lea     rax, [rsp+6A0h+var_660]
0x1800208e9  mov     [rsp+6A0h+pcbData], rax; pcbData
0x1800208ee  mov     r9d, 2; srrfFlags
0x1800208f4  lea     rax, [rbp+5A0h+SubKey]
0x1800208fb  mov     [rsp+6A0h+var_660], esi
0x1800208ff  mov     [rsp+6A0h+pvData], rax; pvData
0x180020904  xor     r8d, r8d; pszValue
0x180020907  xor     edx, edx; pszSubKey
0x180020909  mov     [rsp+6A0h+phkResult], 0; pdwType
0x180020912  call    cs:__imp_SHRegGetValueW
0x180020918  test    eax, eax
0x18002091a  jnz     loc_180020A0E
0x180020920  mov     rcx, [rsp+6A0h+hkey]; hKey
0x180020925  lea     rax, [rsp+6A0h+hKey]
0x18002092a  mov     r9d, 20019h; samDesired
0x180020930  mov     [rsp+6A0h+phkResult], rax; phkResult
0x180020935  xor     r8d, r8d; ulOptions
0x180020938  mov     [rsp+6A0h+hKey], 0
0x180020941  lea     rdx, [rbp+5A0h+SubKey]; lpSubKey
0x180020948  call    cs:__imp_RegOpenKeyExW
0x18002094e  test    eax, eax
0x180020950  jnz     loc_180020A0E
0x180020956  mov     r8d, esi; Size
0x180020959  lea     rcx, [rbp+5A0h+Src]; void *
0x180020960  xor     edx, edx; Val
0x180020962  call    memset_0
0x180020967  mov     rcx, [rsp+6A0h+hKey]; hkey
0x18002096c  lea     rax, [rsp+6A0h+var_660]
0x180020971  mov     [rsp+6A0h+pcbData], rax; pcbData
0x180020976  lea     r8, aDllpathex; "DLLPathEx"
0x18002097d  lea     rax, [rbp+5A0h+Src]
0x180020984  mov     [rsp+6A0h+var_660], esi
0x180020988  mov     [rsp+6A0h+pvData], rax; pvData
0x18002098d  mov     r9d, 2; srrfFlags
0x180020993  xor     edx, edx; pszSubKey
0x180020995  mov     [rsp+6A0h+phkResult], 0; pdwType
0x18002099e  call    cs:__imp_SHRegGetValueW
0x1800209a4  test    eax, eax
0x1800209a6  jnz     short loc_180020A03
0x1800209a8  mov     r8d, esi; Size
0x1800209ab  lea     rcx, [rsp+6A0h+Dst]; void *
0x1800209b0  xor     edx, edx; Val
0x1800209b2  call    memset_0
0x1800209b7  mov     esi, 104h
0x1800209bc  lea     rdx, [rsp+6A0h+Dst]; lpDst
0x1800209c1  mov     r8d, esi; nSize
0x1800209c4  lea     rcx, [rbp+5A0h+Src]; lpSrc
0x1800209cb  call    cs:__imp_ExpandEnvironmentStringsW
0x1800209d1  test    eax, eax
0x1800209d3  jz      short loc_180020A03
0x1800209d5  mov     r8d, esi; cchBuffer
0x1800209d8  lea     rdx, [rsp+6A0h+Dst]; lpszLongPath
0x1800209dd  lea     rcx, [rsp+6A0h+Dst]; lpszShortPath
0x1800209e2  call    cs:__imp_GetLongPathNameW
0x1800209e8  test    eax, eax
0x1800209ea  jz      short loc_180020A03
0x1800209ec  lea     rcx, [rsp+6A0h+Dst]; wchar_t *
0x1800209f1  call    ?Is64bitDll@@YAHPEB_W@Z; Is64bitDll(wchar_t const *)
0x1800209f6  test    eax, eax
0x1800209f8  movzx   ebx, bl
0x1800209fb  mov     ecx, 1
0x180020a00  cmovnz  ebx, ecx
0x180020a03  mov     rcx, [rsp+6A0h+hKey]; hKey
0x180020a08  call    cs:__imp_RegCloseKey
0x180020a0e  mov     rcx, [rsp+6A0h+hkey]; hKey
0x180020a13  call    cs:__imp_RegCloseKey
0x180020a19  mov     al, bl
0x180020a1b  mov     rcx, [rbp+5A0h+var_10]
0x180020a22  xor     rcx, rsp; StackCookie
0x180020a25  call    __security_check_cookie
0x180020a2a  lea     r11, [rsp+6A0h+var_s0]
0x180020a32  mov     rbx, [r11+10h]
0x180020a36  mov     rsi, [r11+18h]
0x180020a3a  mov     rsp, r11
0x180020a3d  pop     rbp
0x180020a3e  retn
```
