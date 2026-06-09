# MyRegDeleteTree

- ea: `0x18004176c`
- end: `0x18004187a`
- name: `MyRegDeleteTree`
- size: `270`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18003f2a4`
- `0x18004176c`

## callees

- `0x18004176c`
- `0x18004d0d2`
- `0x18004d110`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180041850`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180041850`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800417b9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800417b9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004183e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004183e`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18004182c`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18004182c`

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
0x18004176c  mov     [rsp-8+arg_10], rbx
0x180041771  mov     [rsp-8+arg_18], rdi
0x180041776  push    rbp
0x180041777  lea     rbp, [rsp-180h]
0x18004177f  sub     rsp, 280h
0x180041786  mov     rax, cs:__security_cookie
0x18004178d  xor     rax, rsp
0x180041790  mov     [rbp+180h+var_10], rax
0x180041797  lea     rax, [rsp+280h+hKey]
0x18004179c  mov     [rsp+280h+hKey], 0
0x1800417a5  mov     r9d, 0F003Fh; samDesired
0x1800417ab  mov     [rsp+280h+phkResult], rax; phkResult
0x1800417b0  xor     r8d, r8d; ulOptions
0x1800417b3  mov     rdi, rdx
0x1800417b6  mov     rbx, rcx
0x1800417b9  call    cs:__imp_RegOpenKeyExW
0x1800417bf  test    eax, eax
0x1800417c1  jnz     loc_180041856
0x1800417c7  xor     edx, edx; Val
0x1800417c9  lea     rcx, [rsp+280h+Name]; void *
0x1800417ce  mov     r8d, 20Ah; Size
0x1800417d4  call    memset_0
0x1800417d9  mov     qword ptr [rsp+280h+ftLastWriteTime.dwLowDateTime], 0
0x1800417e2  jmp     short loc_1800417EE
0x1800417e4  lea     rdx, [rsp+280h+Name]
0x1800417e9  call    MyRegDeleteTree
0x1800417ee  mov     rcx, [rsp+280h+hKey]; hKey
0x1800417f3  lea     rax, [rsp+280h+ftLastWriteTime]
0x1800417f8  mov     [rsp+280h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1800417fd  lea     r9, [rsp+280h+cchName]; lpcchName
0x180041802  mov     [rsp+280h+lpcchClass], 0; lpcchClass
0x18004180b  lea     r8, [rsp+280h+Name]; lpName
0x180041810  mov     [rsp+280h+lpClass], 0; lpClass
0x180041819  xor     edx, edx; dwIndex
0x18004181b  mov     [rsp+280h+phkResult], 0; lpReserved
0x180041824  mov     [rsp+280h+cchName], 104h
0x18004182c  call    cs:__imp_RegEnumKeyExW
0x180041832  mov     rcx, [rsp+280h+hKey]; hKey
0x180041837  cmp     eax, 103h
0x18004183c  jnz     short loc_1800417E4
0x18004183e  call    cs:__imp_RegCloseKey
0x180041844  xor     r9d, r9d; Reserved
0x180041847  xor     r8d, r8d; samDesired
0x18004184a  mov     rdx, rdi; lpSubKey
0x18004184d  mov     rcx, rbx; hKey
0x180041850  call    cs:__imp_RegDeleteKeyExW
0x180041856  mov     rcx, [rbp+180h+var_10]
0x18004185d  xor     rcx, rsp; StackCookie
0x180041860  call    __security_check_cookie
0x180041865  lea     r11, [rsp+280h+var_s0]
0x18004186d  mov     rbx, [r11+20h]
0x180041871  mov     rdi, [r11+28h]
0x180041875  mov     rsp, r11
0x180041878  pop     rbp
0x180041879  retn
```
