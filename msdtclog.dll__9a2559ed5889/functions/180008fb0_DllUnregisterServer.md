# DllUnregisterServer

- ea: `0x180008fb0`
- end: `0x180009048`
- name: `DllUnregisterServer`
- size: `152`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## import_xrefs

- `ADVAPI32!RegDeleteKeyA` at `0x180008fd0`
- `ADVAPI32!RegDeleteKeyA` at `0x180008fe0`
- `ADVAPI32!RegDeleteKeyA` at `0x180008ff0`
- `ADVAPI32!RegDeleteKeyA` at `0x180009000`
- `ADVAPI32!RegDeleteKeyA` at `0x18000901b`
- `ADVAPI32!RegDeleteKeyA` at `0x18000902b`
- `ADVAPI32!RegDeleteKeyA` at `0x180008fd0`
- `ADVAPI32!RegDeleteKeyA` at `0x180008fe0`
- `ADVAPI32!RegDeleteKeyA` at `0x180008ff0`
- `ADVAPI32!RegDeleteKeyA` at `0x180009000`
- `ADVAPI32!RegDeleteKeyA` at `0x18000901b`
- `ADVAPI32!RegDeleteKeyA` at `0x18000902b`

## string_xrefs

- `0x180008ff6`: `CLSID\{d959f1b0-9e42-11ce-8b97-0080c7a01d7f}`
- `0x180008fc6`: `CLSID\{d959f1b0-9e42-11ce-8b97-0080c7a01d7f}\InprocServer32`
- `0x180008fd6`: `CLSID\{d959f1b0-9e42-11ce-8b97-0080c7a01d7f}\VersionIndependentProgID`
- `0x180008fe6`: `CLSID\{d959f1b0-9e42-11ce-8b97-0080c7a01d7f}\ProgID`
- `0x18000900b`: `MSDTC.CLogMgr\CLSID`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  HRESULT v0; // ebx

  RegDeleteKeyA(HKEY_CLASSES_ROOT, "CLSID\\{d959f1b0-9e42-11ce-8b97-0080c7a01d7f}\\InprocServer32");
  RegDeleteKeyA(HKEY_CLASSES_ROOT, "CLSID\\{d959f1b0-9e42-11ce-8b97-0080c7a01d7f}\\VersionIndependentProgID");
  RegDeleteKeyA(HKEY_CLASSES_ROOT, "CLSID\\{d959f1b0-9e42-11ce-8b97-0080c7a01d7f}\\ProgID");
  v0 = RegDeleteKeyA(HKEY_CLASSES_ROOT, "CLSID\\{d959f1b0-9e42-11ce-8b97-0080c7a01d7f}") != 0 ? 0x8000FFFF : 0;
  RegDeleteKeyA(HKEY_CLASSES_ROOT, "MSDTC.CLogMgr\\CLSID");
  if ( RegDeleteKeyA(HKEY_CLASSES_ROOT, (LPCSTR)"MSDTC.CLogMgr") )
    return -2147418113;
  return v0;
}

```

## disassembly

```asm
0x180008fb0  mov     [rsp+arg_0], rbx
0x180008fb5  mov     [rsp+arg_8], rsi
0x180008fba  push    rdi
0x180008fbb  sub     rsp, 20h
0x180008fbf  mov     rsi, 0FFFFFFFF80000000h
0x180008fc6  lea     rdx, aClsidD959f1b09_1; "CLSID\\{d959f1b0-9e42-11ce-8b97-0080c7a"...
0x180008fcd  mov     rcx, rsi; hKey
0x180008fd0  call    cs:__imp_RegDeleteKeyA
0x180008fd6  lea     rdx, aClsidD959f1b09_0; "CLSID\\{d959f1b0-9e42-11ce-8b97-0080c7a"...
0x180008fdd  mov     rcx, rsi; hKey
0x180008fe0  call    cs:__imp_RegDeleteKeyA
0x180008fe6  lea     rdx, aClsidD959f1b09_2; "CLSID\\{d959f1b0-9e42-11ce-8b97-0080c7a"...
0x180008fed  mov     rcx, rsi; hKey
0x180008ff0  call    cs:__imp_RegDeleteKeyA
0x180008ff6  lea     rdx, aClsidD959f1b09; "CLSID\\{d959f1b0-9e42-11ce-8b97-0080c7a"...
0x180008ffd  mov     rcx, rsi; hKey
0x180009000  call    cs:__imp_RegDeleteKeyA
0x180009006  mov     edi, 8000FFFFh
0x18000900b  lea     rdx, aMsdtcClogmgrCl; "MSDTC.CLogMgr\\CLSID"
0x180009012  neg     eax
0x180009014  mov     rcx, rsi; hKey
0x180009017  sbb     ebx, ebx
0x180009019  and     ebx, edi
0x18000901b  call    cs:__imp_RegDeleteKeyA
0x180009021  lea     rdx, SubKey; "MSDTC.CLogMgr"
0x180009028  mov     rcx, rsi; hKey
0x18000902b  call    cs:__imp_RegDeleteKeyA
0x180009031  mov     rsi, [rsp+28h+arg_8]
0x180009036  test    eax, eax
0x180009038  cmovnz  ebx, edi
0x18000903b  mov     eax, ebx
0x18000903d  mov     rbx, [rsp+28h+arg_0]
0x180009042  add     rsp, 20h
0x180009046  pop     rdi
0x180009047  retn
```
