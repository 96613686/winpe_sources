# DllUnregisterServer

- ea: `0x180011470`
- end: `0x1800114eb`
- name: `DllUnregisterServer`
- size: `123`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000c690`
- `0x18000dd2c`
- `0x180011470`
- `0x180014394`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800114de`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800114de`

## string_xrefs

- `0x180011489`: `"onecoreuap\\base\\appmodel\\search\\common\\pkmcntrs\\pkmcntrs.cxx"`
- `0x180011474`: `[UtilCommon] MSSCNTRS: DllUnregisterServer().`
- `0x1800114a0`: `SYSTEM\CurrentControlSet\Services`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  const wchar_t *v0; // r9
  __int64 v1; // r8
  HRESULT result; // eax
  unsigned int v3; // r8d
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  hKey = 0;
  SearchIndexerTrace::Information(
    (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\common\\\\pkmcntrs\\\\pkmcntrs.cxx\"",
    (const wchar_t *)0x2CE,
    (unsigned int)L"[UtilCommon] MSSCNTRS: DllUnregisterServer().",
    v0);
  result = WSearchRegOpenKey(
             (wchar_t *)0xFFFFFFFF80000002LL,
             (wchar_t *)L"SYSTEM\\CurrentControlSet\\Services",
             v1,
             0xF003Fu,
             &hKey);
  if ( result )
  {
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  else
  {
    DeleteRegSubtree(hKey, L"MSSCNTRS", v3);
    RegCloseKey(hKey);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180011470  sub     rsp, 38h
0x180011474  lea     r8, aUtilcommonMssc_6; "[UtilCommon] MSSCNTRS: DllUnregisterSer"...
0x18001147b  mov     [rsp+38h+hKey], 0
0x180011484  mov     edx, 2CEh; wchar_t *
0x180011489  lea     rcx, aOnecoreuapBase_1; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x180011490  call    ?Information@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Information(wchar_t const *,uint,wchar_t const *,...)
0x180011495  lea     rax, [rsp+38h+hKey]
0x18001149a  mov     r9d, 0F003Fh; unsigned int
0x1800114a0  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services"
0x1800114a7  mov     [rsp+38h+var_18], rax; HKEY *
0x1800114ac  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x1800114b3  call    ?WSearchRegOpenKey@@YAJPEAUHKEY__@@PEB_WKKPEAPEAU1@@Z; WSearchRegOpenKey(HKEY__ *,wchar_t const *,ulong,ulong,HKEY__ * *)
0x1800114b8  test    eax, eax
0x1800114ba  jz      short loc_1800114C8
0x1800114bc  jle     short loc_1800114E6
0x1800114be  movzx   eax, ax
0x1800114c1  or      eax, 80070000h
0x1800114c6  jmp     short loc_1800114E6
0x1800114c8  mov     rcx, [rsp+38h+hKey]; HKEY
0x1800114cd  lea     rdx, aMsscntrs; "MSSCNTRS"
0x1800114d4  call    ?DeleteRegSubtree@@YAXPEAUHKEY__@@PEB_W@Z; DeleteRegSubtree(HKEY__ *,wchar_t const *)
0x1800114d9  mov     rcx, [rsp+38h+hKey]; hKey
0x1800114de  call    cs:__imp_RegCloseKey
0x1800114e4  xor     eax, eax
0x1800114e6  add     rsp, 38h
0x1800114ea  retn
```
