# AMovieSetupUnregisterServer(x,x,x,x)

- ea: `0x1002f44b`
- end: `0x1002f4bf`
- name: `_AMovieSetupUnregisterServer@16`
- size: `116`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1002f547`

## callees

- `0x10006937`
- `0x1002f0fc`
- `0x1003aba0`

## import_xrefs

- `ole32!StringFromGUID2` at `0x1002f47c`
- `ole32!StringFromGUID2` at `0x1002f47c`

## string_xrefs

- `0x1002f486`: `CLSID\%ls`

## pseudocode

```c
unsigned int __stdcall AMovieSetupUnregisterServer(unsigned int a1, int a2, int a3, int a4)
{
  GUID rguid; // [esp+8h] [ebp-26Ch] BYREF
  WCHAR SubKey[260]; // [esp+18h] [ebp-25Ch] BYREF
  OLECHAR sz[40]; // [esp+220h] [ebp-54h] BYREF

  rguid.Data1 = a1;
  *(_DWORD *)&rguid.Data2 = a2;
  *(_DWORD *)rguid.Data4 = a3;
  *(_DWORD *)&rguid.Data4[4] = a4;
  StringFromGUID2(&rguid, sz, 39);
  StringCchPrintfW(SubKey, 0x104u, L"CLSID\\%ls", sz);
  return EliminateSubKey(HKEY_CLASSES_ROOT, SubKey);
}

```

## disassembly

```asm
0x1002f44b  mov     edi, edi
0x1002f44d  push    ebp
0x1002f44e  mov     ebp, esp
0x1002f450  sub     esp, 26Ch
0x1002f456  mov     eax, ___security_cookie
0x1002f45b  xor     eax, ebp
0x1002f45d  mov     [ebp+var_4], eax
0x1002f460  push    esi
0x1002f461  push    edi
0x1002f462  lea     esi, [ebp+arg_0]
0x1002f465  lea     edi, [ebp+rguid]
0x1002f46b  movsd
0x1002f46c  lea     eax, [ebp+sz]
0x1002f46f  push    27h ; '''; cchMax
0x1002f471  push    eax; lpsz
0x1002f472  lea     eax, [ebp+rguid]
0x1002f478  movsd
0x1002f479  push    eax; rguid
0x1002f47a  movsd
0x1002f47b  movsd
0x1002f47c  call    ds:__imp__StringFromGUID2@12; StringFromGUID2(x,x,x)
0x1002f482  lea     eax, [ebp+sz]
0x1002f485  push    eax
0x1002f486  push    offset aClsidLs; "CLSID\\%ls"
0x1002f48b  lea     eax, [ebp+SubKey]
0x1002f491  push    104h; unsigned int
0x1002f496  push    eax; unsigned __int16 *
0x1002f497  call    ?StringCchPrintfW@@YAJPAGIPBGZZ; StringCchPrintfW(ushort *,uint,ushort const *,...)
0x1002f49c  add     esp, 10h
0x1002f49f  lea     edx, [ebp+SubKey]; lpSubKey
0x1002f4a5  mov     ecx, 80000000h; hKey
0x1002f4aa  call    _EliminateSubKey@8; EliminateSubKey(x,x)
0x1002f4af  mov     ecx, [ebp+var_4]
0x1002f4b2  pop     edi
0x1002f4b3  xor     ecx, ebp; StackCookie
0x1002f4b5  pop     esi
0x1002f4b6  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1002f4bb  leave
0x1002f4bc  retn    10h
```
