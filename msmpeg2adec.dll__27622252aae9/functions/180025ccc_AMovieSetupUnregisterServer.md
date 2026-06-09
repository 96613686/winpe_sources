# AMovieSetupUnregisterServer

- ea: `0x180025ccc`
- end: `0x180025d55`
- name: `AMovieSetupUnregisterServer`
- size: `137`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180025658`

## callees

- `0x1800017b0`
- `0x180017ba0`
- `0x180025d5c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180025cfe`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180025cfe`

## string_xrefs

- `0x180025d14`: `CLSID\%ls`

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
0x180025ccc  sub     rsp, 2A8h
0x180025cd3  mov     rax, cs:__security_cookie
0x180025cda  xor     rax, rsp
0x180025cdd  mov     [rsp+2A8h+var_18], rax
0x180025ce5  movups  xmm0, xmmword ptr [rcx]
0x180025ce8  mov     r8d, 27h ; '''; cchMax
0x180025cee  lea     rdx, [rsp+2A8h+sz]; lpsz
0x180025cf3  lea     rcx, [rsp+2A8h+rguid]; rguid
0x180025cf8  movdqu  xmmword ptr [rsp+2A8h+rguid.Data1], xmm0
0x180025cfe  call    cs:__imp_StringFromGUID2
0x180025d05  nop     dword ptr [rax+rax+00h]
0x180025d0a  lea     r9, [rsp+2A8h+sz]
0x180025d0f  mov     edx, 104h; unsigned __int64
0x180025d14  lea     r8, aClsidLs; "CLSID\\%ls"
0x180025d1b  lea     rcx, [rsp+2A8h+SubKey]; unsigned __int16 *
0x180025d23  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180025d28  lea     rdx, [rsp+2A8h+SubKey]; lpSubKey
0x180025d30  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180025d37  call    EliminateSubKey
0x180025d3c  mov     rcx, [rsp+2A8h+var_18]
0x180025d44  xor     rcx, rsp; StackCookie
0x180025d47  call    __security_check_cookie
0x180025d4c  add     rsp, 2A8h
0x180025d53  retn
```
