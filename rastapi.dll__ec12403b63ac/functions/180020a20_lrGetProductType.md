# lrGetProductType

- ea: `0x180020a20`
- end: `0x180020b4f`
- name: `lrGetProductType`
- size: `303`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000de88`
- `0x180016d40`
- `0x180020b58`

## callees

- `0x180020a20`
- `0x18002927e`
- `0x1800292b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180020ad6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180020ad6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180020a9a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180020a9a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020b26`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020b26`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180020aee`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180020b0c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180020aee`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180020b0c`

## pseudocode

```c
__int64 __fastcall lrGetProductType(_DWORD *a1)
{
  unsigned int v2; // ebx
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Data[128]; // [rsp+40h] [rbp-C0h] BYREF

  memset_0(Data, 0, sizeof(Data));
  hKey = 0;
  cbData = 0;
  Type = 0;
  *a1 = 1;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\ProductOptions", 0, 0x20019u, &hKey);
  if ( !v2 )
  {
    cbData = 256;
    v2 = RegQueryValueExW(hKey, L"ProductType", 0, &Type, (LPBYTE)Data, &cbData);
    if ( !v2 )
    {
      if ( lstrcmpiW(Data, L"ServerNT") )
      {
        if ( !lstrcmpiW(Data, L"WinNT") )
          *a1 = 1;
      }
      else
      {
        *a1 = 2;
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v2;
}

```

## disassembly

```asm
0x180020a20  mov     [rsp-8+arg_8], rbx
0x180020a25  mov     [rsp-8+arg_10], rdi
0x180020a2a  push    rbp
0x180020a2b  lea     rbp, [rsp-50h]
0x180020a30  sub     rsp, 150h
0x180020a37  mov     rax, cs:__security_cookie
0x180020a3e  xor     rax, rsp
0x180020a41  mov     [rbp+50h+var_10], rax
0x180020a45  mov     rdi, rcx
0x180020a48  xor     edx, edx; Val
0x180020a4a  lea     rcx, [rsp+150h+Data]; void *
0x180020a4f  mov     r8d, 100h; Size
0x180020a55  call    memset_0
0x180020a5a  lea     rax, [rsp+150h+hKey]
0x180020a5f  mov     [rsp+150h+hKey], 0
0x180020a68  mov     r9d, 20019h; samDesired
0x180020a6e  mov     [rsp+150h+phkResult], rax; phkResult
0x180020a73  xor     r8d, r8d; ulOptions
0x180020a76  mov     [rsp+150h+cbData], 0
0x180020a7e  lea     rdx, aSystemCurrentc_2; "System\\CurrentControlSet\\Control\\Pro"...
0x180020a85  mov     [rsp+150h+Type], 0
0x180020a8d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180020a94  mov     dword ptr [rdi], 1
0x180020a9a  call    cs:__imp_RegOpenKeyExW
0x180020aa0  mov     ebx, eax
0x180020aa2  test    eax, eax
0x180020aa4  jnz     short loc_180020B1C
0x180020aa6  mov     rcx, [rsp+150h+hKey]; hKey
0x180020aab  lea     rax, [rsp+150h+cbData]
0x180020ab0  mov     [rsp+150h+lpcbData], rax; lpcbData
0x180020ab5  lea     r9, [rsp+150h+Type]; lpType
0x180020aba  lea     rax, [rsp+150h+Data]
0x180020abf  mov     [rsp+150h+cbData], 100h
0x180020ac7  xor     r8d, r8d; lpReserved
0x180020aca  mov     [rsp+150h+phkResult], rax; lpData
0x180020acf  lea     rdx, aProducttype; "ProductType"
0x180020ad6  call    cs:__imp_RegQueryValueExW
0x180020adc  mov     ebx, eax
0x180020ade  test    eax, eax
0x180020ae0  jnz     short loc_180020B1C
0x180020ae2  lea     rdx, aServernt; "ServerNT"
0x180020ae9  lea     rcx, [rsp+150h+Data]; lpString1
0x180020aee  call    cs:__imp_lstrcmpiW
0x180020af4  test    eax, eax
0x180020af6  jnz     short loc_180020B00
0x180020af8  mov     dword ptr [rdi], 2
0x180020afe  jmp     short loc_180020B1C
0x180020b00  lea     rdx, aWinnt; "WinNT"
0x180020b07  lea     rcx, [rsp+150h+Data]; lpString1
0x180020b0c  call    cs:__imp_lstrcmpiW
0x180020b12  test    eax, eax
0x180020b14  jnz     short loc_180020B1C
0x180020b16  mov     dword ptr [rdi], 1
0x180020b1c  mov     rcx, [rsp+150h+hKey]; hKey
0x180020b21  test    rcx, rcx
0x180020b24  jz      short loc_180020B2C
0x180020b26  call    cs:__imp_RegCloseKey
0x180020b2c  mov     eax, ebx
0x180020b2e  mov     rcx, [rbp+50h+var_10]
0x180020b32  xor     rcx, rsp; StackCookie
0x180020b35  call    __security_check_cookie
0x180020b3a  lea     r11, [rsp+150h+var_s0]
0x180020b42  mov     rbx, [r11+18h]
0x180020b46  mov     rdi, [r11+20h]
0x180020b4a  mov     rsp, r11
0x180020b4d  pop     rbp
0x180020b4e  retn
```
