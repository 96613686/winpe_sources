# ReadRegistryValueA(char const *,uchar *,ulong *,char const *)

- ea: `0x1800c0000`
- end: `0x1800c00aa`
- name: `?ReadRegistryValueA@@YA_NPEBDPEAEPEAK0@Z`
- size: `170`
- prototype: `bool __fastcall(const char *, unsigned __int8 *, unsigned int *, const char *)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800c00ac`
- `0x1800cab00`
- `0x1800cf814`
- `0x1800fa23c`

## callees

- `0x1800c0000`
- `0x18032f050`
- `0x18032f0b0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1800c0089`
- `ADVAPI32!RegCloseKey` at `0x1800c0089`
- `ADVAPI32!RegOpenKeyExA` at `0x1800c0053`
- `ADVAPI32!RegOpenKeyExA` at `0x1800c0053`
- `ADVAPI32!RegQueryValueExA` at `0x1800c0077`
- `ADVAPI32!RegQueryValueExA` at `0x1800c0077`

## pseudocode

```c
bool __fastcall ReadRegistryValueA(const char *a1, unsigned __int8 *a2, unsigned int *a3, const char *a4)
{
  LSTATUS Value; // ebx
  HKEY hKey; // [rsp+30h] [rbp-38h] BYREF

  hKey = 0;
  Value = RegOpenKeyExA(HKEY_LOCAL_MACHINE, a4, 0, 0x20019u, &hKey);
  if ( !Value )
    Value = RegQueryValueExA(hKey, a1, 0, 0, a2, a3);
  if ( hKey )
    RegCloseKey(hKey);
  return Value == 0;
}

```

## disassembly

```asm
0x1800c0000  push    rbx
0x1800c0002  push    rbp
0x1800c0003  push    rsi
0x1800c0004  push    rdi
0x1800c0005  mov     eax, 48h
0x1800c000a  call    _alloca_probe
0x1800c000f  sub     rsp, rax
0x1800c0012  mov     rax, cs:__security_cookie
0x1800c0019  xor     rax, rsp
0x1800c001c  mov     [rsp+68h+var_30], rax
0x1800c0021  mov     rdi, rcx
0x1800c0024  mov     [rsp+68h+hKey], 0
0x1800c002d  mov     rax, r9
0x1800c0030  lea     rcx, [rsp+68h+hKey]
0x1800c0035  mov     [rsp+68h+phkResult], rcx; phkResult
0x1800c003a  mov     rbp, r8
0x1800c003d  mov     rsi, rdx
0x1800c0040  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800c0047  mov     r9d, 20019h; samDesired
0x1800c004d  xor     r8d, r8d; ulOptions
0x1800c0050  mov     rdx, rax; lpSubKey
0x1800c0053  call    cs:__imp_RegOpenKeyExA
0x1800c0059  mov     ebx, eax
0x1800c005b  test    eax, eax
0x1800c005d  jnz     short loc_1800C007F
0x1800c005f  mov     rcx, [rsp+68h+hKey]; hKey
0x1800c0064  xor     r9d, r9d; lpType
0x1800c0067  mov     [rsp+68h+lpcbData], rbp; lpcbData
0x1800c006c  xor     r8d, r8d; lpReserved
0x1800c006f  mov     rdx, rdi; lpValueName
0x1800c0072  mov     [rsp+68h+phkResult], rsi; lpData
0x1800c0077  call    cs:__imp_RegQueryValueExA
0x1800c007d  mov     ebx, eax
0x1800c007f  mov     rcx, [rsp+68h+hKey]; hKey
0x1800c0084  test    rcx, rcx
0x1800c0087  jz      short loc_1800C008F
0x1800c0089  call    cs:__imp_RegCloseKey
0x1800c008f  test    ebx, ebx
0x1800c0091  setz    al
0x1800c0094  mov     rcx, [rsp+68h+var_30]
0x1800c0099  xor     rcx, rsp; StackCookie
0x1800c009c  call    __security_check_cookie
0x1800c00a1  add     rsp, 48h
0x1800c00a5  pop     rdi
0x1800c00a6  pop     rsi
0x1800c00a7  pop     rbp
0x1800c00a8  pop     rbx
0x1800c00a9  retn
```
