# EliminateSubKey

- ea: `0x180002f3c`
- end: `0x180003079`
- name: `EliminateSubKey`
- size: `317`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180002eb4`
- `0x180002f3c`

## callees

- `0x180001460`
- `0x180002f3c`

## import_xrefs

- `ADVAPI32!RegDeleteKeyW` at `0x18000303e`
- `ADVAPI32!RegDeleteKeyW` at `0x18000303e`
- `ADVAPI32!RegCloseKey` at `0x180003032`
- `ADVAPI32!RegCloseKey` at `0x180003032`
- `ADVAPI32!RegEnumKeyExW` at `0x180003023`
- `ADVAPI32!RegEnumKeyExW` at `0x180003023`
- `ADVAPI32!RegOpenKeyExW` at `0x180002fcd`
- `ADVAPI32!RegOpenKeyExW` at `0x180002fcd`

## pseudocode

```c
LSTATUS __fastcall EliminateSubKey(HKEY hKey, LPCWSTR lpSubKey)
{
  LPCWSTR v4; // rax
  __int64 v5; // rcx
  LSTATUS result; // eax
  bool v7; // cc
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKeya; // [rsp+48h] [rbp-B8h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-A0h] BYREF

  hKeya = 0;
  if ( !lpSubKey )
    return -2147467259;
  v4 = lpSubKey;
  v5 = 0x7FFFFFFF;
  do
  {
    if ( !*v4 )
      break;
    ++v4;
    --v5;
  }
  while ( v5 );
  if ( !v5 || ((0x7FFFFFFF - v5) & -(__int64)(v5 != 0)) == 0 )
    return -2147467259;
  result = RegOpenKeyExW(hKey, lpSubKey, 0, 0x2000000u, &hKeya);
  v7 = result <= 0;
  if ( !result )
  {
    do
    {
      cchName = 260;
      ftLastWriteTime = 0;
    }
    while ( !RegEnumKeyExW(hKeya, 0, SubKey, &cchName, 0, 0, 0, &ftLastWriteTime)
         && !(unsigned int)EliminateSubKey(hKeya, SubKey) );
    RegCloseKey(hKeya);
    result = RegDeleteKeyW(hKey, lpSubKey);
    v7 = result <= 0;
  }
  if ( !v7 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180002f3c  mov     [rsp-8+arg_10], rbx
0x180002f41  push    rbp
0x180002f42  push    rsi
0x180002f43  push    rdi
0x180002f44  lea     rbp, [rsp-180h]
0x180002f4c  sub     rsp, 280h
0x180002f53  mov     rax, cs:__security_cookie
0x180002f5a  xor     rax, rsp
0x180002f5d  mov     [rbp+190h+var_20], rax
0x180002f64  xor     esi, esi
0x180002f66  mov     rbx, rdx
0x180002f69  mov     [rsp+290h+hKey], rsi
0x180002f6e  mov     rdi, rcx
0x180002f71  test    rdx, rdx
0x180002f74  jz      loc_180003052
0x180002f7a  mov     edx, 7FFFFFFFh
0x180002f7f  mov     rax, rbx
0x180002f82  mov     ecx, edx
0x180002f84  cmp     [rax], si
0x180002f87  jz      short loc_180002F93
0x180002f89  add     rax, 2
0x180002f8d  sub     rcx, 1
0x180002f91  jnz     short loc_180002F84
0x180002f93  sub     rdx, rcx
0x180002f96  mov     rax, rcx
0x180002f99  neg     rax
0x180002f9c  sbb     r8, r8
0x180002f9f  and     r8, rdx
0x180002fa2  test    rcx, rcx
0x180002fa5  jz      loc_180003052
0x180002fab  test    r8, r8
0x180002fae  jz      loc_180003052
0x180002fb4  lea     rax, [rsp+290h+hKey]
0x180002fb9  mov     r9d, 2000000h; samDesired
0x180002fbf  xor     r8d, r8d; ulOptions
0x180002fc2  mov     [rsp+290h+phkResult], rax; phkResult
0x180002fc7  mov     rdx, rbx; lpSubKey
0x180002fca  mov     rcx, rdi; hKey
0x180002fcd  call    cs:__imp_RegOpenKeyExW
0x180002fd3  test    eax, eax
0x180002fd5  jnz     short loc_180003046
0x180002fd7  jmp     short loc_180002FEC
0x180002fd9  mov     rcx, [rsp+290h+hKey]; hKey
0x180002fde  lea     rdx, [rsp+290h+SubKey]; lpSubKey
0x180002fe3  call    EliminateSubKey
0x180002fe8  test    eax, eax
0x180002fea  jnz     short loc_18000302D
0x180002fec  mov     rcx, [rsp+290h+hKey]; hKey
0x180002ff1  lea     rax, [rsp+290h+ftLastWriteTime]
0x180002ff6  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180002ffb  lea     r9, [rsp+290h+cchName]; lpcchName
0x180003000  mov     [rsp+290h+lpcchClass], rsi; lpcchClass
0x180003005  lea     r8, [rsp+290h+SubKey]; lpName
0x18000300a  mov     [rsp+290h+lpClass], rsi; lpClass
0x18000300f  xor     edx, edx; dwIndex
0x180003011  mov     [rsp+290h+phkResult], rsi; lpReserved
0x180003016  mov     [rsp+290h+cchName], 104h
0x18000301e  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], rsi
0x180003023  call    cs:__imp_RegEnumKeyExW
0x180003029  test    eax, eax
0x18000302b  jz      short loc_180002FD9
0x18000302d  mov     rcx, [rsp+290h+hKey]; hKey
0x180003032  call    cs:__imp_RegCloseKey
0x180003038  mov     rdx, rbx; lpSubKey
0x18000303b  mov     rcx, rdi; hKey
0x18000303e  call    cs:__imp_RegDeleteKeyW
0x180003044  test    eax, eax
0x180003046  jle     short loc_180003057
0x180003048  movzx   eax, ax
0x18000304b  or      eax, 80070000h
0x180003050  jmp     short loc_180003057
0x180003052  mov     eax, 80004005h
0x180003057  mov     rcx, [rbp+190h+var_20]
0x18000305e  xor     rcx, rsp; StackCookie
0x180003061  call    __security_check_cookie
0x180003066  mov     rbx, [rsp+290h+arg_10]
0x18000306e  add     rsp, 280h
0x180003075  pop     rdi
0x180003076  pop     rsi
0x180003077  pop     rbp
0x180003078  retn
```
