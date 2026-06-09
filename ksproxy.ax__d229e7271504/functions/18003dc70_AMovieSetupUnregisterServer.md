# AMovieSetupUnregisterServer

- ea: `0x18003dc70`
- end: `0x18003dcf9`
- name: `AMovieSetupUnregisterServer`
- size: `137`
- prototype: `__int64 __fastcall(GUID *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18003de64`

## callees

- `0x18000909c`
- `0x18001f620`
- `0x18003dd00`

## import_xrefs

- `ole32!StringFromGUID2` at `0x18003dca2`
- `ole32!StringFromGUID2` at `0x18003dca2`

## string_xrefs

- `0x18003dcb8`: `CLSID\%ls`

## pseudocode

```c
__int64 __fastcall AMovieSetupUnregisterServer(GUID *a1)
{
  GUID rguid; // [rsp+20h] [rbp-288h] BYREF
  OLECHAR sz[40]; // [rsp+30h] [rbp-278h] BYREF
  unsigned __int16 v4[264]; // [rsp+80h] [rbp-228h] BYREF

  rguid = *a1;
  StringFromGUID2(&rguid, sz, 39);
  StringCchPrintfW(v4, 0x104u, L"CLSID\\%ls", sz);
  return EliminateSubKey(0xFFFFFFFF80000000uLL, v4);
}

```

## disassembly

```asm
0x18003dc70  sub     rsp, 2A8h
0x18003dc77  mov     rax, cs:__security_cookie
0x18003dc7e  xor     rax, rsp
0x18003dc81  mov     [rsp+2A8h+var_18], rax
0x18003dc89  movups  xmm0, xmmword ptr [rcx]
0x18003dc8c  mov     r8d, 27h ; '''; cchMax
0x18003dc92  lea     rdx, [rsp+2A8h+sz]; lpsz
0x18003dc97  lea     rcx, [rsp+2A8h+rguid]; rguid
0x18003dc9c  movdqu  xmmword ptr [rsp+2A8h+rguid.Data1], xmm0
0x18003dca2  call    cs:__imp_StringFromGUID2
0x18003dca9  nop     dword ptr [rax+rax+00h]
0x18003dcae  lea     r9, [rsp+2A8h+sz]
0x18003dcb3  mov     edx, 104h; unsigned __int64
0x18003dcb8  lea     r8, aClsidLs; "CLSID\\%ls"
0x18003dcbf  lea     rcx, [rsp+2A8h+var_228]; unsigned __int16 *
0x18003dcc7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003dccc  lea     rdx, [rsp+2A8h+var_228]
0x18003dcd4  mov     rcx, 0FFFFFFFF80000000h
0x18003dcdb  call    EliminateSubKey
0x18003dce0  mov     rcx, [rsp+2A8h+var_18]
0x18003dce8  xor     rcx, rsp; StackCookie
0x18003dceb  call    __security_check_cookie
0x18003dcf0  add     rsp, 2A8h
0x18003dcf7  retn
```
