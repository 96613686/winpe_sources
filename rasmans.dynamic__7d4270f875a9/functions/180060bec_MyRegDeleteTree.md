# MyRegDeleteTree

- ea: `0x180060bec`
- end: `0x180060d13`
- name: `MyRegDeleteTree`
- size: `295`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18005d87c`
- `0x180060bec`

## callees

- `0x180060bec`
- `0x1800e8e96`
- `0x1800e8ef0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180060c39`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180060c39`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180060cca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180060cca`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180060cb2`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180060cb2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180060ce2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180060ce2`

## pseudocode

```c
LSTATUS __fastcall MyRegDeleteTree(HKEY a1, const WCHAR *a2)
{
  LSTATUS result; // eax
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Name[264]; // [rsp+60h] [rbp-A0h] BYREF

  hKey = 0;
  result = RegOpenKeyExW(a1, a2, 0, 0xF003Fu, &hKey);
  if ( !result )
  {
    memset_0(Name, 0, 0x20Au);
    ftLastWriteTime = 0;
    while ( 1 )
    {
      cchName = 260;
      if ( RegEnumKeyExW(hKey, 0, Name, &cchName, 0, 0, 0, &ftLastWriteTime) == 259 )
        break;
      MyRegDeleteTree(hKey, Name);
    }
    RegCloseKey(hKey);
    return RegDeleteKeyExW(a1, a2, 0, 0);
  }
  return result;
}

```

## disassembly

```asm
0x180060bec  mov     [rsp-8+arg_10], rbx
0x180060bf1  mov     [rsp-8+arg_18], rdi
0x180060bf6  push    rbp
0x180060bf7  lea     rbp, [rsp-180h]
0x180060bff  sub     rsp, 280h
0x180060c06  mov     rax, cs:__security_cookie
0x180060c0d  xor     rax, rsp
0x180060c10  mov     [rbp+180h+var_10], rax
0x180060c17  lea     rax, [rsp+280h+hKey]
0x180060c1c  mov     [rsp+280h+hKey], 0
0x180060c25  mov     r9d, 0F003Fh; samDesired
0x180060c2b  mov     [rsp+280h+phkResult], rax; phkResult
0x180060c30  xor     r8d, r8d; ulOptions
0x180060c33  mov     rdi, rdx
0x180060c36  mov     rbx, rcx
0x180060c39  call    cs:__imp_RegOpenKeyExW
0x180060c40  nop     dword ptr [rax+rax+00h]
0x180060c45  test    eax, eax
0x180060c47  jnz     loc_180060CEE
0x180060c4d  xor     edx, edx; Val
0x180060c4f  lea     rcx, [rsp+280h+Name]; void *
0x180060c54  mov     r8d, 20Ah; Size
0x180060c5a  call    memset_0
0x180060c5f  mov     qword ptr [rsp+280h+ftLastWriteTime.dwLowDateTime], 0
0x180060c68  jmp     short loc_180060C74
0x180060c6a  lea     rdx, [rsp+280h+Name]
0x180060c6f  call    MyRegDeleteTree
0x180060c74  mov     rcx, [rsp+280h+hKey]; hKey
0x180060c79  lea     rax, [rsp+280h+ftLastWriteTime]
0x180060c7e  mov     [rsp+280h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180060c83  lea     r9, [rsp+280h+cchName]; lpcchName
0x180060c88  mov     [rsp+280h+lpcchClass], 0; lpcchClass
0x180060c91  lea     r8, [rsp+280h+Name]; lpName
0x180060c96  mov     [rsp+280h+lpClass], 0; lpClass
0x180060c9f  xor     edx, edx; dwIndex
0x180060ca1  mov     [rsp+280h+phkResult], 0; lpReserved
0x180060caa  mov     [rsp+280h+cchName], 104h
0x180060cb2  call    cs:__imp_RegEnumKeyExW
0x180060cb9  nop     dword ptr [rax+rax+00h]
0x180060cbe  mov     rcx, [rsp+280h+hKey]; hKey
0x180060cc3  cmp     eax, 103h
0x180060cc8  jnz     short loc_180060C6A
0x180060cca  call    cs:__imp_RegCloseKey
0x180060cd1  nop     dword ptr [rax+rax+00h]
0x180060cd6  xor     r9d, r9d; Reserved
0x180060cd9  xor     r8d, r8d; samDesired
0x180060cdc  mov     rdx, rdi; lpSubKey
0x180060cdf  mov     rcx, rbx; hKey
0x180060ce2  call    cs:__imp_RegDeleteKeyExW
0x180060ce9  nop     dword ptr [rax+rax+00h]
0x180060cee  mov     rcx, [rbp+180h+var_10]
0x180060cf5  xor     rcx, rsp; StackCookie
0x180060cf8  call    __security_check_cookie
0x180060cfd  lea     r11, [rsp+280h+var_s0]
0x180060d05  mov     rbx, [r11+20h]
0x180060d09  mov     rdi, [r11+28h]
0x180060d0d  mov     rsp, r11
0x180060d10  pop     rbp
0x180060d11  retn
```
