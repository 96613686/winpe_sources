# MyRegDeleteTree

- ea: `0x1800c51dc`
- end: `0x1800c52ea`
- name: `MyRegDeleteTree`
- size: `270`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800c3d0c`
- `0x1800c51dc`

## callees

- `0x1800c51dc`
- `0x1800ded06`
- `0x1800ded50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800c529c`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800c529c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c5229`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c5229`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800c52c0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800c52c0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c52ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c52ae`

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
0x1800c51dc  mov     [rsp-8+arg_10], rbx
0x1800c51e1  mov     [rsp-8+arg_18], rdi
0x1800c51e6  push    rbp
0x1800c51e7  lea     rbp, [rsp-180h]
0x1800c51ef  sub     rsp, 280h
0x1800c51f6  mov     rax, cs:__security_cookie
0x1800c51fd  xor     rax, rsp
0x1800c5200  mov     [rbp+180h+var_10], rax
0x1800c5207  lea     rax, [rsp+280h+hKey]
0x1800c520c  mov     [rsp+280h+hKey], 0
0x1800c5215  mov     r9d, 0F003Fh; samDesired
0x1800c521b  mov     [rsp+280h+phkResult], rax; phkResult
0x1800c5220  xor     r8d, r8d; ulOptions
0x1800c5223  mov     rdi, rdx
0x1800c5226  mov     rbx, rcx
0x1800c5229  call    cs:__imp_RegOpenKeyExW
0x1800c522f  test    eax, eax
0x1800c5231  jnz     loc_1800C52C6
0x1800c5237  xor     edx, edx; Val
0x1800c5239  lea     rcx, [rsp+280h+Name]; void *
0x1800c523e  mov     r8d, 20Ah; Size
0x1800c5244  call    memset_0
0x1800c5249  mov     qword ptr [rsp+280h+ftLastWriteTime.dwLowDateTime], 0
0x1800c5252  jmp     short loc_1800C525E
0x1800c5254  lea     rdx, [rsp+280h+Name]
0x1800c5259  call    MyRegDeleteTree
0x1800c525e  mov     rcx, [rsp+280h+hKey]; hKey
0x1800c5263  lea     rax, [rsp+280h+ftLastWriteTime]
0x1800c5268  mov     [rsp+280h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1800c526d  lea     r9, [rsp+280h+cchName]; lpcchName
0x1800c5272  mov     [rsp+280h+lpcchClass], 0; lpcchClass
0x1800c527b  lea     r8, [rsp+280h+Name]; lpName
0x1800c5280  mov     [rsp+280h+lpClass], 0; lpClass
0x1800c5289  xor     edx, edx; dwIndex
0x1800c528b  mov     [rsp+280h+phkResult], 0; lpReserved
0x1800c5294  mov     [rsp+280h+cchName], 104h
0x1800c529c  call    cs:__imp_RegEnumKeyExW
0x1800c52a2  mov     rcx, [rsp+280h+hKey]; hKey
0x1800c52a7  cmp     eax, 103h
0x1800c52ac  jnz     short loc_1800C5254
0x1800c52ae  call    cs:__imp_RegCloseKey
0x1800c52b4  xor     r9d, r9d; Reserved
0x1800c52b7  xor     r8d, r8d; samDesired
0x1800c52ba  mov     rdx, rdi; lpSubKey
0x1800c52bd  mov     rcx, rbx; hKey
0x1800c52c0  call    cs:__imp_RegDeleteKeyExW
0x1800c52c6  mov     rcx, [rbp+180h+var_10]
0x1800c52cd  xor     rcx, rsp; StackCookie
0x1800c52d0  call    __security_check_cookie
0x1800c52d5  lea     r11, [rsp+280h+var_s0]
0x1800c52dd  mov     rbx, [r11+20h]
0x1800c52e1  mov     rdi, [r11+28h]
0x1800c52e5  mov     rsp, r11
0x1800c52e8  pop     rbp
0x1800c52e9  retn
```
