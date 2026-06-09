# WSearchRegCreateKey(HKEY__ *,wchar_t const *,ulong,wchar_t *,ulong,ulong,_SECURITY_ATTRIBUTES * const,HKEY__ * *,ulong *)

- ea: `0x1800142d8`
- end: `0x18001438d`
- name: `?WSearchRegCreateKey@@YAJPEAUHKEY__@@PEB_WKPEA_WKKQEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@Z`
- size: `181`
- prototype: `LSTATUS __fastcall(const wchar_t *, wchar_t *, __int64, wchar_t *, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *const, HKEY *phkResult, unsigned int *lpdwDisposition)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800111b0`

## callees

- `0x1800024a0`
- `0x180014008`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180014362`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180014362`

## pseudocode

```c
LSTATUS __fastcall WSearchRegCreateKey(
        const wchar_t *a1,
        wchar_t *a2,
        __int64 a3,
        wchar_t *a4,
        unsigned int a5,
        unsigned int a6,
        struct _SECURITY_ATTRIBUTES *const a7,
        HKEY *phkResult,
        unsigned int *lpdwDisposition)
{
  bool v10; // al
  wchar_t *v11; // rdx
  wchar_t v13[264]; // [rsp+50h] [rbp-228h] BYREF

  v10 = MapRegistryKeyPath(a1, HKEY_LOCAL_MACHINE, a2, v13);
  v11 = v13;
  if ( !v10 )
    v11 = a2;
  return RegCreateKeyExW(HKEY_LOCAL_MACHINE, v11, 0, (LPWSTR)&Class, 0, 0x20006u, 0, phkResult, lpdwDisposition);
}

```

## disassembly

```asm
0x1800142d8  mov     [rsp+arg_0], rbx
0x1800142dd  mov     [rsp+arg_10], rsi
0x1800142e2  push    rdi
0x1800142e3  sub     rsp, 270h
0x1800142ea  mov     rax, cs:__security_cookie
0x1800142f1  xor     rax, rsp
0x1800142f4  mov     [rsp+278h+var_18], rax
0x1800142fc  mov     rdi, [rsp+278h+arg_38]
0x180014304  lea     r9, [rsp+278h+var_228]; wchar_t *
0x180014309  mov     rbx, [rsp+278h+arg_40]
0x180014311  mov     rsi, rdx
0x180014314  mov     r8, rdx; wchar_t *
0x180014317  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x18001431e  call    ?MapRegistryKeyPath@@YA_NPEB_WPEAUHKEY__@@0PEA_WK@Z; MapRegistryKeyPath(wchar_t const *,HKEY__ *,wchar_t const *,wchar_t *,ulong)
0x180014323  mov     [rsp+278h+lpdwDisposition], rbx; lpdwDisposition
0x180014328  lea     rdx, [rsp+278h+var_228]
0x18001432d  mov     [rsp+278h+phkResult], rdi; phkResult
0x180014332  lea     r9, Class; lpClass
0x180014339  test    al, al
0x18001433b  mov     [rsp+278h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180014344  mov     [rsp+278h+samDesired], 20006h; samDesired
0x18001434c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180014353  cmovz   rdx, rsi; lpSubKey
0x180014357  mov     [rsp+278h+dwOptions], 0; dwOptions
0x18001435f  xor     r8d, r8d; Reserved
0x180014362  call    cs:__imp_RegCreateKeyExW
0x180014368  mov     rcx, [rsp+278h+var_18]
0x180014370  xor     rcx, rsp; StackCookie
0x180014373  call    __security_check_cookie
0x180014378  lea     r11, [rsp+278h+var_8]
0x180014380  mov     rbx, [r11+10h]
0x180014384  mov     rsi, [r11+20h]
0x180014388  mov     rsp, r11
0x18001438b  pop     rdi
0x18001438c  retn
```
