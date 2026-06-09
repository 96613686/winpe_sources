# WSearchRegOpenKey(HKEY__ *,wchar_t const *,ulong,ulong,HKEY__ * *)

- ea: `0x180014394`
- end: `0x180014418`
- name: `?WSearchRegOpenKey@@YAJPEAUHKEY__@@PEB_WKKPEAPEAU1@@Z`
- size: `132`
- prototype: `LSTATUS __fastcall(wchar_t *, wchar_t *, __int64, REGSAM, HKEY *phkResult)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000c690`
- `0x180011470`
- `0x180011500`

## callees

- `0x1800024a0`
- `0x180014008`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800143ef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800143ef`

## pseudocode

```c
LSTATUS __fastcall WSearchRegOpenKey(wchar_t *a1, wchar_t *a2, __int64 a3, REGSAM a4, HKEY *phkResult)
{
  bool v8; // al
  wchar_t *v9; // rdx
  wchar_t v11[264]; // [rsp+30h] [rbp-238h] BYREF

  v8 = MapRegistryKeyPath(a1, (HKEY)a1, a2, v11);
  v9 = v11;
  if ( !v8 )
    v9 = a2;
  return RegOpenKeyExW((HKEY)a1, v9, 0, a4, phkResult);
}

```

## disassembly

```asm
0x180014394  mov     [rsp+arg_10], rbx
0x180014399  push    rbp
0x18001439a  push    rsi
0x18001439b  push    rdi
0x18001439c  sub     rsp, 250h
0x1800143a3  mov     rax, cs:__security_cookie
0x1800143aa  xor     rax, rsp
0x1800143ad  mov     [rsp+268h+var_28], rax
0x1800143b5  mov     rbx, [rsp+268h+arg_20]
0x1800143bd  mov     ebp, r9d
0x1800143c0  mov     rdi, rdx
0x1800143c3  lea     r9, [rsp+268h+var_238]; wchar_t *
0x1800143c8  mov     r8, rdx; wchar_t *
0x1800143cb  mov     rsi, rcx
0x1800143ce  mov     rdx, rcx; HKEY
0x1800143d1  call    ?MapRegistryKeyPath@@YA_NPEB_WPEAUHKEY__@@0PEA_WK@Z; MapRegistryKeyPath(wchar_t const *,HKEY__ *,wchar_t const *,wchar_t *,ulong)
0x1800143d6  test    al, al
0x1800143d8  mov     [rsp+268h+phkResult], rbx; phkResult
0x1800143dd  lea     rdx, [rsp+268h+var_238]
0x1800143e2  mov     r9d, ebp; samDesired
0x1800143e5  cmovz   rdx, rdi; lpSubKey
0x1800143e9  mov     rcx, rsi; hKey
0x1800143ec  xor     r8d, r8d; ulOptions
0x1800143ef  call    cs:__imp_RegOpenKeyExW
0x1800143f5  mov     rcx, [rsp+268h+var_28]
0x1800143fd  xor     rcx, rsp; StackCookie
0x180014400  call    __security_check_cookie
0x180014405  mov     rbx, [rsp+268h+arg_10]
0x18001440d  add     rsp, 250h
0x180014414  pop     rdi
0x180014415  pop     rsi
0x180014416  pop     rbp
0x180014417  retn
```
