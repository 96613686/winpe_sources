# HrRegDeleteKeyTree(HKEY__ *,ushort const *)

- ea: `0x180030324`
- end: `0x18003042c`
- name: `?HrRegDeleteKeyTree@@YAJPEAUHKEY__@@PEBG@Z`
- size: `264`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180024760`
- `0x180030324`
- `0x180031b1c`

## callees

- `0x180001710`
- `0x180030324`
- `0x180030434`

## import_xrefs

- `ADVAPI32!RegEnumKeyExW` at `0x1800303c8`
- `ADVAPI32!RegEnumKeyExW` at `0x1800303c8`
- `ADVAPI32!RegCloseKey` at `0x1800303d9`
- `ADVAPI32!RegCloseKey` at `0x1800303d9`
- `ADVAPI32!RegDeleteKeyExW` at `0x1800303f3`
- `ADVAPI32!RegDeleteKeyExW` at `0x1800303f3`

## pseudocode

```c
__int64 __fastcall HrRegDeleteKeyTree(HKEY a1, const unsigned __int16 *a2)
{
  int v4; // ebx
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Name[264]; // [rsp+60h] [rbp-A0h] BYREF

  hKey = 0;
  v4 = HrRegOpenKeyEx(a1, a2, 0x3001Fu, &hKey);
  if ( !v4 )
  {
    ftLastWriteTime = 0;
    while ( 1 )
    {
      cchName = 260;
      v4 = RegEnumKeyExW(hKey, 0, Name, &cchName, 0, 0, 0, &ftLastWriteTime);
      if ( v4 )
        break;
      HrRegDeleteKeyTree(hKey, Name);
    }
    RegCloseKey(hKey);
    if ( v4 == 259 )
      v4 = RegDeleteKeyExW(a1, a2, 0, 0);
    if ( v4 > 0 )
      return (unsigned __int16)v4 | 0x80070000;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180030324  mov     [rsp-8+arg_10], rbx
0x180030329  push    rbp
0x18003032a  push    rsi
0x18003032b  push    rdi
0x18003032c  lea     rbp, [rsp-180h]
0x180030334  sub     rsp, 280h
0x18003033b  mov     rax, cs:__security_cookie
0x180030342  xor     rax, rsp
0x180030345  mov     [rbp+190h+var_20], rax
0x18003034c  lea     r9, [rsp+290h+hKey]; HKEY *
0x180030351  mov     [rsp+290h+hKey], 0
0x18003035a  mov     r8d, 3001Fh; unsigned int
0x180030360  mov     rsi, rdx
0x180030363  mov     rdi, rcx
0x180030366  call    ?HrRegOpenKeyEx@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z; HrRegOpenKeyEx(HKEY__ *,ushort const *,ulong,HKEY__ * *)
0x18003036b  mov     ebx, eax
0x18003036d  test    eax, eax
0x18003036f  jnz     loc_180030408
0x180030375  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], 0
0x18003037e  jmp     short loc_18003038A
0x180030380  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x180030385  call    ?HrRegDeleteKeyTree@@YAJPEAUHKEY__@@PEBG@Z; HrRegDeleteKeyTree(HKEY__ *,ushort const *)
0x18003038a  mov     rcx, [rsp+290h+hKey]; hKey
0x18003038f  lea     rax, [rsp+290h+ftLastWriteTime]
0x180030394  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180030399  lea     r9, [rsp+290h+cchName]; lpcchName
0x18003039e  mov     [rsp+290h+lpcchClass], 0; lpcchClass
0x1800303a7  lea     r8, [rsp+290h+Name]; lpName
0x1800303ac  mov     [rsp+290h+lpClass], 0; lpClass
0x1800303b5  xor     edx, edx; dwIndex
0x1800303b7  mov     [rsp+290h+lpReserved], 0; lpReserved
0x1800303c0  mov     [rsp+290h+cchName], 104h
0x1800303c8  call    cs:__imp_RegEnumKeyExW
0x1800303ce  mov     rcx, [rsp+290h+hKey]; HKEY
0x1800303d3  mov     ebx, eax
0x1800303d5  test    eax, eax
0x1800303d7  jz      short loc_180030380
0x1800303d9  call    cs:__imp_RegCloseKey
0x1800303df  cmp     ebx, 103h
0x1800303e5  jnz     short loc_1800303FB
0x1800303e7  xor     r9d, r9d; Reserved
0x1800303ea  xor     r8d, r8d; samDesired
0x1800303ed  mov     rdx, rsi; lpSubKey
0x1800303f0  mov     rcx, rdi; hKey
0x1800303f3  call    cs:__imp_RegDeleteKeyExW
0x1800303f9  mov     ebx, eax
0x1800303fb  test    ebx, ebx
0x1800303fd  jle     short loc_180030408
0x1800303ff  movzx   ebx, bx
0x180030402  or      ebx, 80070000h
0x180030408  mov     eax, ebx
0x18003040a  mov     rcx, [rbp+190h+var_20]
0x180030411  xor     rcx, rsp; StackCookie
0x180030414  call    __security_check_cookie
0x180030419  mov     rbx, [rsp+290h+arg_10]
0x180030421  add     rsp, 280h
0x180030428  pop     rdi
0x180030429  pop     rsi
0x18003042a  pop     rbp
0x18003042b  retn
```
