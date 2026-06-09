# _anonymous_namespace_::LoadMSENV

- ea: `0x140027cbc`
- end: `0x140027dbe`
- name: `_anonymous_namespace_::LoadMSENV`
- size: `258`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `reparse_path, loader_planting`

## callers

- `0x14000ccfc`
- `0x14000f0c0`
- `0x140037900`

## callees

- `0x140001020`
- `0x140004a0c`
- `0x1400084f4`
- `0x140027cbc`
- `0x140027dc0`
- `0x14002fe10`
- `0x140033ab0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140027d92`
- `ADVAPI32!RegCloseKey` at `0x140027d92`
- `KERNEL32!LoadLibraryW` at `0x140027d6a`
- `KERNEL32!LoadLibraryW` at `0x140027d6a`
- `OLEAUT32!__imp_SysAllocString` at `0x140027cf1`
- `OLEAUT32!__imp_SysAllocString` at `0x140027cf1`
- `OLEAUT32!__imp_SysFreeString` at `0x140027d78`
- `OLEAUT32!__imp_SysFreeString` at `0x140027d82`
- `OLEAUT32!__imp_SysFreeString` at `0x140027d78`
- `OLEAUT32!__imp_SysFreeString` at `0x140027d82`
- `OLEAUT32!__imp_SysStringLen` at `0x140027d51`
- `OLEAUT32!__imp_SysStringLen` at `0x140027d51`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
HMODULE __fastcall anonymous_namespace_::LoadMSENV(__int64 a1)
{
  const OLECHAR *v1; // rdx
  HMODULE LibraryW; // rsi
  HKEY v3; // rcx
  OLECHAR *v4; // rdi
  BSTR pbstr[2]; // [rsp+20h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF

  v1 = *(const OLECHAR **)(a1 + 184);
  LibraryW = 0;
  v3 = 0;
  hKey = 0;
  if ( v1 )
  {
    v4 = SysAllocString(v1);
    pbstr[1] = v4;
    if ( !v4 )
      ATL::AtlThrowImpl(-2147024882);
    CodeMarker(9244);
    if ( (int)CVsRegKeyW::Open(&hKey, HKEY_LOCAL_MACHINE, v4, 0x20019u) >= 0 )
    {
      pbstr[0] = 0;
      CVsRegKeyW::QueryValue((CVsRegKeyW *)&hKey, L"MsEnvLocation", pbstr);
      if ( SysStringLen(pbstr[0]) )
      {
        NormalizeFileSlashes(pbstr[0]);
        LibraryW = LoadLibraryW(pbstr[0]);
      }
      SysFreeString(pbstr[0]);
    }
    SysFreeString(v4);
    v3 = hKey;
  }
  if ( v3 )
    RegCloseKey(v3);
  return LibraryW;
}

```

## disassembly

```asm
0x140027cbc  mov     [rsp+arg_8], rsi
0x140027cc1  push    rdi
0x140027cc2  sub     rsp, 40h
0x140027cc6  mov     rax, cs:__security_cookie
0x140027ccd  xor     rax, rsp
0x140027cd0  mov     [rsp+48h+var_10], rax
0x140027cd5  mov     rdx, [rcx+0B8h]
0x140027cdc  xor     esi, esi
0x140027cde  xor     ecx, ecx
0x140027ce0  mov     [rsp+48h+hKey], rcx
0x140027ce5  test    rdx, rdx
0x140027ce8  jz      loc_140027D8D
0x140027cee  mov     rcx, rdx; psz
0x140027cf1  call    cs:__imp_SysAllocString
0x140027cf7  mov     rdi, rax
0x140027cfa  mov     [rsp+48h+var_20], rax
0x140027cff  test    rax, rax
0x140027d02  jz      loc_140027DB3
0x140027d08  mov     ecx, 241Ch
0x140027d0d  call    ?CodeMarker@@YAXW4CodeMarkerEvent@Performance@Internal@Microsoft@@@Z; CodeMarker(Microsoft::Internal::Performance::CodeMarkerEvent)
0x140027d12  mov     r9d, 20019h; unsigned int
0x140027d18  mov     r8, rdi; unsigned __int16 *
0x140027d1b  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x140027d22  lea     rcx, [rsp+48h+hKey]; this
0x140027d27  call    ?Open@CVsRegKeyW@@QEAAJPEAUHKEY__@@PEBGK@Z; CVsRegKeyW::Open(HKEY__ *,ushort const *,ulong)
0x140027d2c  test    eax, eax
0x140027d2e  js      short loc_140027D7F
0x140027d30  and     [rsp+48h+pbstr], 0
0x140027d36  lea     r8, [rsp+48h+pbstr]; unsigned __int16 **
0x140027d3b  lea     rdx, aMsenvlocation; "MsEnvLocation"
0x140027d42  lea     rcx, [rsp+48h+hKey]; this
0x140027d47  call    ?QueryValue@CVsRegKeyW@@QEBAJPEBGPEAPEAG@Z; CVsRegKeyW::QueryValue(ushort const *,ushort * *)
0x140027d4c  mov     rcx, [rsp+48h+pbstr]; pbstr
0x140027d51  call    cs:__imp_SysStringLen
0x140027d57  test    eax, eax
0x140027d59  jz      short loc_140027D73
0x140027d5b  mov     rcx, [rsp+48h+pbstr]; unsigned __int16 *
0x140027d60  call    ?NormalizeFileSlashes@@YAPEAGPEAG@Z; NormalizeFileSlashes(ushort *)
0x140027d65  mov     rcx, [rsp+48h+pbstr]; lpLibFileName
0x140027d6a  call    cs:__imp_LoadLibraryW
0x140027d70  mov     rsi, rax
0x140027d73  mov     rcx, [rsp+48h+pbstr]; bstrString
0x140027d78  call    cs:__imp_SysFreeString
0x140027d7e  nop
0x140027d7f  mov     rcx, rdi; bstrString
0x140027d82  call    cs:__imp_SysFreeString
0x140027d88  mov     rcx, [rsp+48h+hKey]; hKey
0x140027d8d  test    rcx, rcx
0x140027d90  jz      short loc_140027D98
0x140027d92  call    cs:__imp_RegCloseKey
0x140027d98  mov     rax, rsi
0x140027d9b  mov     rcx, [rsp+48h+var_10]
0x140027da0  xor     rcx, rsp; StackCookie
0x140027da3  call    __security_check_cookie
0x140027da8  mov     rsi, [rsp+48h+arg_8]
0x140027dad  add     rsp, 40h
0x140027db1  pop     rdi
0x140027db2  retn
0x140027db3  mov     ecx, 8007000Eh; int
0x140027db8  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
