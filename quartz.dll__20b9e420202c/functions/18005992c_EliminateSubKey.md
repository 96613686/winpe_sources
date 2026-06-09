# EliminateSubKey

- ea: `0x18005992c`
- end: `0x180059a87`
- name: `EliminateSubKey`
- size: `347`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18005989c`
- `0x18005992c`
- `0x180068510`
- `0x1800686b0`

## callees

- `0x180026490`
- `0x1800388a0`
- `0x18005992c`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x1800599ae`
- `ADVAPI32!RegOpenKeyExW` at `0x1800599ae`
- `ADVAPI32!RegEnumKeyExW` at `0x180059a09`
- `ADVAPI32!RegEnumKeyExW` at `0x180059a09`
- `ADVAPI32!RegDeleteKeyW` at `0x180059a43`
- `ADVAPI32!RegDeleteKeyW` at `0x180059a43`
- `ADVAPI32!RegCloseKey` at `0x180059a31`
- `ADVAPI32!RegCloseKey` at `0x180059a31`

## pseudocode

```c
LSTATUS __fastcall EliminateSubKey(HKEY a1, const unsigned __int16 *a2)
{
  LSTATUS result; // eax
  bool v5; // cc
  DWORD cchName[2]; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-A0h] BYREF

  hKey = 0;
  *(_QWORD *)cchName = 0;
  if ( (int)StringCchLengthW(a2, 0x7FFFFFFFu, (unsigned __int64 *)cchName) < 0 || !*(_QWORD *)cchName )
    return -2147467259;
  result = RegOpenKeyExW(a1, a2, 0, 0x2000000u, &hKey);
  v5 = result <= 0;
  if ( !result )
  {
    do
    {
      cchName[0] = 260;
      ftLastWriteTime = 0;
    }
    while ( !RegEnumKeyExW(hKey, 0, SubKey, cchName, 0, 0, 0, &ftLastWriteTime)
         && !(unsigned int)EliminateSubKey(hKey, SubKey) );
    RegCloseKey(hKey);
    result = RegDeleteKeyW(a1, a2);
    v5 = result <= 0;
  }
  if ( !v5 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18005992c  mov     [rsp-8+arg_10], rbx
0x180059931  mov     [rsp-8+arg_18], rdi
0x180059936  push    rbp
0x180059937  lea     rbp, [rsp-180h]
0x18005993f  sub     rsp, 280h
0x180059946  mov     rax, cs:__security_cookie
0x18005994d  xor     rax, rsp
0x180059950  mov     [rbp+180h+var_10], rax
0x180059957  mov     rbx, rdx
0x18005995a  mov     [rsp+280h+hKey], 0
0x180059963  mov     rdi, rcx
0x180059966  mov     qword ptr [rsp+280h+cchName], 0
0x18005996f  mov     rcx, rbx; unsigned __int16 *
0x180059972  lea     r8, [rsp+280h+cchName]; unsigned __int64 *
0x180059977  mov     edx, 7FFFFFFFh; unsigned __int64
0x18005997c  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180059981  test    eax, eax
0x180059983  js      loc_180059A5D
0x180059989  cmp     qword ptr [rsp+280h+cchName], 0
0x18005998f  jz      loc_180059A5D
0x180059995  lea     rax, [rsp+280h+hKey]
0x18005999a  mov     r9d, 2000000h; samDesired
0x1800599a0  xor     r8d, r8d; ulOptions
0x1800599a3  mov     [rsp+280h+phkResult], rax; phkResult
0x1800599a8  mov     rdx, rbx; lpSubKey
0x1800599ab  mov     rcx, rdi; hKey
0x1800599ae  call    cs:__imp_RegOpenKeyExW
0x1800599b5  nop     dword ptr [rax+rax+00h]
0x1800599ba  test    eax, eax
0x1800599bc  jnz     loc_180059A51
0x1800599c2  mov     rcx, [rsp+280h+hKey]; hKey
0x1800599c7  lea     rax, [rsp+280h+ftLastWriteTime]
0x1800599cc  mov     [rsp+280h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1800599d1  lea     r9, [rsp+280h+cchName]; lpcchName
0x1800599d6  mov     [rsp+280h+lpcchClass], 0; lpcchClass
0x1800599df  lea     r8, [rsp+280h+SubKey]; lpName
0x1800599e4  mov     [rsp+280h+lpClass], 0; lpClass
0x1800599ed  xor     edx, edx; dwIndex
0x1800599ef  mov     [rsp+280h+phkResult], 0; lpReserved
0x1800599f8  mov     [rsp+280h+cchName], 104h
0x180059a00  mov     qword ptr [rsp+280h+ftLastWriteTime.dwLowDateTime], 0
0x180059a09  call    cs:__imp_RegEnumKeyExW
0x180059a10  nop     dword ptr [rax+rax+00h]
0x180059a15  test    eax, eax
0x180059a17  jnz     short loc_180059A2C
0x180059a19  mov     rcx, [rsp+280h+hKey]
0x180059a1e  lea     rdx, [rsp+280h+SubKey]
0x180059a23  call    EliminateSubKey
0x180059a28  test    eax, eax
0x180059a2a  jz      short loc_1800599C2
0x180059a2c  mov     rcx, [rsp+280h+hKey]; hKey
0x180059a31  call    cs:__imp_RegCloseKey
0x180059a38  nop     dword ptr [rax+rax+00h]
0x180059a3d  mov     rdx, rbx; lpSubKey
0x180059a40  mov     rcx, rdi; hKey
0x180059a43  call    cs:__imp_RegDeleteKeyW
0x180059a4a  nop     dword ptr [rax+rax+00h]
0x180059a4f  test    eax, eax
0x180059a51  jle     short loc_180059A62
0x180059a53  movzx   eax, ax
0x180059a56  or      eax, 80070000h
0x180059a5b  jmp     short loc_180059A62
0x180059a5d  mov     eax, 80004005h
0x180059a62  mov     rcx, [rbp+180h+var_10]
0x180059a69  xor     rcx, rsp; StackCookie
0x180059a6c  call    __security_check_cookie
0x180059a71  lea     r11, [rsp+280h+var_s0]
0x180059a79  mov     rbx, [r11+20h]
0x180059a7d  mov     rdi, [r11+28h]
0x180059a81  mov     rsp, r11
0x180059a84  pop     rbp
0x180059a85  retn
```
