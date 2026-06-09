# LoadInfoFromRegistry(ushort const *,ushort const *,ushort *,ushort *)

- ea: `0x18003aecc`
- end: `0x18003aff5`
- name: `?LoadInfoFromRegistry@@YAXPEBG0PEAG1@Z`
- size: `297`
- prototype: `void(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003adf8`

## callees

- `0x18003aecc`
- `0x18006ed20`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003af1c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003af91`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003af1c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003af91`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003af56`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003afcf`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003af56`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003afcf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003af6e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003afda`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003af6e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003afda`
- `api-ms-win-core-string-l2-1-0!CharLowerW` at `0x18003af63`
- `api-ms-win-core-string-l2-1-0!CharLowerW` at `0x18003af63`

## pseudocode

```c
void __fastcall LoadInfoFromRegistry(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  HKEY hkey; // [rsp+40h] [rbp-38h] BYREF
  DWORD pcbData; // [rsp+48h] [rbp-30h] BYREF

  *a3 = 0;
  *a4 = 0;
  hkey = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\KindMap",
          0,
          0x20019u,
          &hkey) )
  {
    pcbData = 520;
    if ( !RegGetValueW(hkey, 0, a2, 2u, 0, a3, &pcbData) )
      CharLowerW(a3);
    RegCloseKey(hkey);
  }
  if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, a2, 0, 0x20019u, &hkey) )
  {
    pcbData = 520;
    RegGetValueW(hkey, 0, L"Content Type", 2u, 0, a4, &pcbData);
    RegCloseKey(hkey);
  }
}

```

## disassembly

```asm
0x18003aecc  push    rbx
0x18003aece  push    rsi
0x18003aecf  push    rdi
0x18003aed0  sub     rsp, 60h
0x18003aed4  mov     rax, cs:__security_cookie
0x18003aedb  xor     rax, rsp
0x18003aede  mov     [rsp+78h+var_28], rax
0x18003aee3  xor     eax, eax
0x18003aee5  mov     rsi, r9
0x18003aee8  mov     [r8], ax
0x18003aeec  mov     rbx, r8
0x18003aeef  mov     [r9], ax
0x18003aef3  mov     rdi, rdx
0x18003aef6  mov     [rsp+78h+hkey], rax
0x18003aefb  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18003af02  lea     rax, [rsp+78h+hkey]
0x18003af07  mov     r9d, 20019h; samDesired
0x18003af0d  xor     r8d, r8d; ulOptions
0x18003af10  mov     [rsp+78h+phkResult], rax; phkResult
0x18003af15  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003af1c  call    cs:__imp_RegOpenKeyExW
0x18003af22  test    eax, eax
0x18003af24  jnz     short loc_18003AF74
0x18003af26  mov     rcx, [rsp+78h+hkey]; hkey
0x18003af2b  lea     rax, [rsp+78h+var_30]
0x18003af30  mov     [rsp+78h+pcbData], rax; pcbData
0x18003af35  mov     r9d, 2; dwFlags
0x18003af3b  mov     [rsp+78h+pvData], rbx; pvData
0x18003af40  mov     r8, rdi; lpValue
0x18003af43  xor     edx, edx; lpSubKey
0x18003af45  mov     [rsp+78h+phkResult], 0; pdwType
0x18003af4e  mov     [rsp+78h+var_30], 208h
0x18003af56  call    cs:__imp_RegGetValueW
0x18003af5c  test    eax, eax
0x18003af5e  jnz     short loc_18003AF69
0x18003af60  mov     rcx, rbx; lpsz
0x18003af63  call    cs:__imp_CharLowerW
0x18003af69  mov     rcx, [rsp+78h+hkey]; hKey
0x18003af6e  call    cs:__imp_RegCloseKey
0x18003af74  lea     rax, [rsp+78h+hkey]
0x18003af79  mov     r9d, 20019h; samDesired
0x18003af7f  xor     r8d, r8d; ulOptions
0x18003af82  mov     [rsp+78h+phkResult], rax; phkResult
0x18003af87  mov     rdx, rdi; lpSubKey
0x18003af8a  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18003af91  call    cs:__imp_RegOpenKeyExW
0x18003af97  test    eax, eax
0x18003af99  jnz     short loc_18003AFE0
0x18003af9b  mov     rcx, [rsp+78h+hkey]; hkey
0x18003afa0  lea     rax, [rsp+78h+var_30]
0x18003afa5  mov     [rsp+78h+pcbData], rax; pcbData
0x18003afaa  lea     r8, Value; "Content Type"
0x18003afb1  mov     [rsp+78h+pvData], rsi; pvData
0x18003afb6  mov     r9d, 2; dwFlags
0x18003afbc  xor     edx, edx; lpSubKey
0x18003afbe  mov     [rsp+78h+phkResult], 0; pdwType
0x18003afc7  mov     [rsp+78h+var_30], 208h
0x18003afcf  call    cs:__imp_RegGetValueW
0x18003afd5  mov     rcx, [rsp+78h+hkey]; hKey
0x18003afda  call    cs:__imp_RegCloseKey
0x18003afe0  mov     rcx, [rsp+78h+var_28]
0x18003afe5  xor     rcx, rsp; StackCookie
0x18003afe8  call    __security_check_cookie
0x18003afed  add     rsp, 60h
0x18003aff1  pop     rdi
0x18003aff2  pop     rsi
0x18003aff3  pop     rbx
0x18003aff4  retn
```
