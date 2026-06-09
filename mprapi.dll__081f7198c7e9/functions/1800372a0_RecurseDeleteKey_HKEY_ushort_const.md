# RecurseDeleteKey(HKEY__ *,ushort const *)

- ea: `0x1800372a0`
- end: `0x180037399`
- name: `?RecurseDeleteKey@@YAJPEAUHKEY__@@PEBG@Z`
- size: `249`
- prototype: `LSTATUS __fastcall(HKEY, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180035c70`
- `0x1800372a0`

## callees

- `0x1800372a0`
- `0x180051160`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003735d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003735d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18003736f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18003736f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003734e`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003734e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800372ed`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800372ed`

## pseudocode

```c
LSTATUS __fastcall RecurseDeleteKey(HKEY a1, const unsigned __int16 *a2)
{
  LSTATUS result; // eax
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Name[256]; // [rsp+60h] [rbp-A0h] BYREF

  hKey = 0;
  result = RegOpenKeyExW(a1, a2, 0, 0x2000000u, &hKey);
  if ( !result )
  {
    ftLastWriteTime = 0;
    while ( 1 )
    {
      cchName = 256;
      if ( RegEnumKeyExW(hKey, 0, Name, &cchName, 0, 0, 0, &ftLastWriteTime) )
        break;
      result = RecurseDeleteKey(hKey, Name);
      if ( result )
        return result;
    }
    RegCloseKey(hKey);
    return RegDeleteKeyExW(a1, a2, 0, 0);
  }
  return result;
}

```

## disassembly

```asm
0x1800372a0  mov     [rsp-8+arg_10], rbx
0x1800372a5  mov     [rsp-8+arg_18], rdi
0x1800372aa  push    rbp
0x1800372ab  lea     rbp, [rsp-170h]
0x1800372b3  sub     rsp, 270h
0x1800372ba  mov     rax, cs:__security_cookie
0x1800372c1  xor     rax, rsp
0x1800372c4  mov     [rbp+170h+var_10], rax
0x1800372cb  lea     rax, [rsp+270h+hKey]
0x1800372d0  mov     [rsp+270h+hKey], 0
0x1800372d9  mov     r9d, 2000000h; samDesired
0x1800372df  mov     [rsp+270h+phkResult], rax; phkResult
0x1800372e4  xor     r8d, r8d; ulOptions
0x1800372e7  mov     rdi, rdx
0x1800372ea  mov     rbx, rcx
0x1800372ed  call    cs:__imp_RegOpenKeyExW
0x1800372f3  test    eax, eax
0x1800372f5  jnz     short loc_180037375
0x1800372f7  mov     qword ptr [rsp+270h+ftLastWriteTime.dwLowDateTime], 0
0x180037300  jmp     short loc_180037310
0x180037302  lea     rdx, [rsp+270h+Name]; unsigned __int16 *
0x180037307  call    ?RecurseDeleteKey@@YAJPEAUHKEY__@@PEBG@Z; RecurseDeleteKey(HKEY__ *,ushort const *)
0x18003730c  test    eax, eax
0x18003730e  jnz     short loc_180037375
0x180037310  mov     rcx, [rsp+270h+hKey]; hKey
0x180037315  lea     rax, [rsp+270h+ftLastWriteTime]
0x18003731a  mov     [rsp+270h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18003731f  lea     r9, [rsp+270h+cchName]; lpcchName
0x180037324  mov     [rsp+270h+lpcchClass], 0; lpcchClass
0x18003732d  lea     r8, [rsp+270h+Name]; lpName
0x180037332  mov     [rsp+270h+lpClass], 0; lpClass
0x18003733b  xor     edx, edx; dwIndex
0x18003733d  mov     [rsp+270h+phkResult], 0; lpReserved
0x180037346  mov     [rsp+270h+cchName], 100h
0x18003734e  call    cs:__imp_RegEnumKeyExW
0x180037354  mov     rcx, [rsp+270h+hKey]; HKEY
0x180037359  test    eax, eax
0x18003735b  jz      short loc_180037302
0x18003735d  call    cs:__imp_RegCloseKey
0x180037363  xor     r9d, r9d; Reserved
0x180037366  xor     r8d, r8d; samDesired
0x180037369  mov     rdx, rdi; lpSubKey
0x18003736c  mov     rcx, rbx; hKey
0x18003736f  call    cs:__imp_RegDeleteKeyExW
0x180037375  mov     rcx, [rbp+170h+var_10]
0x18003737c  xor     rcx, rsp; StackCookie
0x18003737f  call    __security_check_cookie
0x180037384  lea     r11, [rsp+270h+var_s0]
0x18003738c  mov     rbx, [r11+20h]
0x180037390  mov     rdi, [r11+28h]
0x180037394  mov     rsp, r11
0x180037397  pop     rbp
0x180037398  retn
```
