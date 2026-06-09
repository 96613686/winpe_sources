# EliminateSubKey

- ea: `0x18003dd00`
- end: `0x18003de5b`
- name: `EliminateSubKey`
- size: `347`
- prototype: `LSTATUS __fastcall(HKEY, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18003dc70`
- `0x18003dd00`

## callees

- `0x180010ec4`
- `0x18001f620`
- `0x18003dd00`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18003de05`
- `ADVAPI32!RegCloseKey` at `0x18003de05`
- `ADVAPI32!RegOpenKeyExW` at `0x18003dd82`
- `ADVAPI32!RegOpenKeyExW` at `0x18003dd82`
- `ADVAPI32!RegEnumKeyExW` at `0x18003dddd`
- `ADVAPI32!RegEnumKeyExW` at `0x18003dddd`
- `ADVAPI32!RegDeleteKeyW` at `0x18003de17`
- `ADVAPI32!RegDeleteKeyW` at `0x18003de17`

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
  if ( (int)StringCchLengthW(a2, 0x7FFFFFFF, (unsigned __int64 *)cchName) < 0 || !*(_QWORD *)cchName )
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
0x18003dd00  mov     [rsp-8+arg_10], rbx
0x18003dd05  mov     [rsp-8+arg_18], rdi
0x18003dd0a  push    rbp
0x18003dd0b  lea     rbp, [rsp-180h]
0x18003dd13  sub     rsp, 280h
0x18003dd1a  mov     rax, cs:__security_cookie
0x18003dd21  xor     rax, rsp
0x18003dd24  mov     [rbp+180h+var_10], rax
0x18003dd2b  mov     rbx, rdx
0x18003dd2e  mov     [rsp+280h+hKey], 0
0x18003dd37  mov     rdi, rcx
0x18003dd3a  mov     qword ptr [rsp+280h+cchName], 0
0x18003dd43  mov     rcx, rbx; unsigned __int16 *
0x18003dd46  lea     r8, [rsp+280h+cchName]; unsigned __int64 *
0x18003dd4b  mov     edx, 7FFFFFFFh; unsigned __int64
0x18003dd50  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18003dd55  test    eax, eax
0x18003dd57  js      loc_18003DE31
0x18003dd5d  cmp     qword ptr [rsp+280h+cchName], 0
0x18003dd63  jz      loc_18003DE31
0x18003dd69  lea     rax, [rsp+280h+hKey]
0x18003dd6e  mov     r9d, 2000000h; samDesired
0x18003dd74  xor     r8d, r8d; ulOptions
0x18003dd77  mov     [rsp+280h+phkResult], rax; phkResult
0x18003dd7c  mov     rdx, rbx; lpSubKey
0x18003dd7f  mov     rcx, rdi; hKey
0x18003dd82  call    cs:__imp_RegOpenKeyExW
0x18003dd89  nop     dword ptr [rax+rax+00h]
0x18003dd8e  test    eax, eax
0x18003dd90  jnz     loc_18003DE25
0x18003dd96  mov     rcx, [rsp+280h+hKey]; hKey
0x18003dd9b  lea     rax, [rsp+280h+ftLastWriteTime]
0x18003dda0  mov     [rsp+280h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18003dda5  lea     r9, [rsp+280h+cchName]; lpcchName
0x18003ddaa  mov     [rsp+280h+lpcchClass], 0; lpcchClass
0x18003ddb3  lea     r8, [rsp+280h+SubKey]; lpName
0x18003ddb8  mov     [rsp+280h+lpClass], 0; lpClass
0x18003ddc1  xor     edx, edx; dwIndex
0x18003ddc3  mov     [rsp+280h+phkResult], 0; lpReserved
0x18003ddcc  mov     [rsp+280h+cchName], 104h
0x18003ddd4  mov     qword ptr [rsp+280h+ftLastWriteTime.dwLowDateTime], 0
0x18003dddd  call    cs:__imp_RegEnumKeyExW
0x18003dde4  nop     dword ptr [rax+rax+00h]
0x18003dde9  test    eax, eax
0x18003ddeb  jnz     short loc_18003DE00
0x18003dded  mov     rcx, [rsp+280h+hKey]
0x18003ddf2  lea     rdx, [rsp+280h+SubKey]
0x18003ddf7  call    EliminateSubKey
0x18003ddfc  test    eax, eax
0x18003ddfe  jz      short loc_18003DD96
0x18003de00  mov     rcx, [rsp+280h+hKey]; hKey
0x18003de05  call    cs:__imp_RegCloseKey
0x18003de0c  nop     dword ptr [rax+rax+00h]
0x18003de11  mov     rdx, rbx; lpSubKey
0x18003de14  mov     rcx, rdi; hKey
0x18003de17  call    cs:__imp_RegDeleteKeyW
0x18003de1e  nop     dword ptr [rax+rax+00h]
0x18003de23  test    eax, eax
0x18003de25  jle     short loc_18003DE36
0x18003de27  movzx   eax, ax
0x18003de2a  or      eax, 80070000h
0x18003de2f  jmp     short loc_18003DE36
0x18003de31  mov     eax, 80004005h
0x18003de36  mov     rcx, [rbp+180h+var_10]
0x18003de3d  xor     rcx, rsp; StackCookie
0x18003de40  call    __security_check_cookie
0x18003de45  lea     r11, [rsp+280h+var_s0]
0x18003de4d  mov     rbx, [r11+20h]
0x18003de51  mov     rdi, [r11+28h]
0x18003de55  mov     rsp, r11
0x18003de58  pop     rbp
0x18003de59  retn
```
