# AMovieSetupUnregisterServer

- ea: `0x180002eb4`
- end: `0x180002f36`
- name: `AMovieSetupUnregisterServer`
- size: `130`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800028b0`

## callees

- `0x180001460`
- `0x1800026d4`
- `0x180002f3c`

## import_xrefs

- `ole32!StringFromGUID2` at `0x180002ee6`
- `ole32!StringFromGUID2` at `0x180002ee6`

## string_xrefs

- `0x180002ef6`: `CLSID\%ls`

## pseudocode

```c
LSTATUS __fastcall AMovieSetupUnregisterServer(GUID *a1)
{
  GUID rguid; // [rsp+20h] [rbp-288h] BYREF
  OLECHAR sz[40]; // [rsp+30h] [rbp-278h] BYREF
  WCHAR SubKey[264]; // [rsp+80h] [rbp-228h] BYREF

  rguid = *a1;
  StringFromGUID2(&rguid, sz, 39);
  StringCchPrintfW(SubKey, 0x104u, L"CLSID\\%ls", sz);
  return EliminateSubKey(HKEY_CLASSES_ROOT, SubKey);
}

```

## disassembly

```asm
0x180002eb4  sub     rsp, 2A8h
0x180002ebb  mov     rax, cs:__security_cookie
0x180002ec2  xor     rax, rsp
0x180002ec5  mov     [rsp+2A8h+var_18], rax
0x180002ecd  movups  xmm0, xmmword ptr [rcx]
0x180002ed0  mov     r8d, 27h ; '''; cchMax
0x180002ed6  lea     rdx, [rsp+2A8h+sz]; lpsz
0x180002edb  lea     rcx, [rsp+2A8h+rguid]; rguid
0x180002ee0  movdqu  xmmword ptr [rsp+2A8h+rguid.Data1], xmm0
0x180002ee6  call    cs:__imp_StringFromGUID2
0x180002eec  lea     r9, [rsp+2A8h+sz]
0x180002ef1  mov     edx, 104h; unsigned __int64
0x180002ef6  lea     r8, aClsidLs; "CLSID\\%ls"
0x180002efd  lea     rcx, [rsp+2A8h+SubKey]; unsigned __int16 *
0x180002f05  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180002f0a  lea     rdx, [rsp+2A8h+SubKey]; lpSubKey
0x180002f12  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180002f19  call    EliminateSubKey
0x180002f1e  mov     rcx, [rsp+2A8h+var_18]
0x180002f26  xor     rcx, rsp; StackCookie
0x180002f29  call    __security_check_cookie
0x180002f2e  add     rsp, 2A8h
0x180002f35  retn
```
