# RegisterByteStreamHandler(_GUID const &,ushort const *,ushort const *)

- ea: `0x18001a540`
- end: `0x18001a660`
- name: `?RegisterByteStreamHandler@@YAJAEBU_GUID@@PEBG1@Z`
- size: `288`
- prototype: `__int64 __fastcall(const struct _GUID *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001c1d0`

## callees

- `0x180001e80`
- `0x180018cec`
- `0x18001a540`
- `0x18001b654`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001a5b0`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001a5b0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001a617`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001a617`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a628`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a637`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a628`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a637`

## pseudocode

```c
__int64 __fastcall RegisterByteStreamHandler(
        const struct _GUID *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  int v3; // ebx
  HKEY hKey; // [rsp+30h] [rbp-29h] BYREF
  HKEY v6; // [rsp+38h] [rbp-21h] BYREF
  unsigned __int64 v7; // [rsp+40h] [rbp-19h] BYREF
  OLECHAR sz[40]; // [rsp+50h] [rbp-9h] BYREF

  v6 = 0;
  hKey = 0;
  v7 = 0;
  v3 = StringCchLengthW(L"MF FLAC Media Source ByteStreamHandler", 0x7FFFFFFFu, &v7);
  if ( v3 >= 0 )
  {
    v3 = StringFromGUID2(&CLSID_MFFLACBytestreamHandler, sz, 39);
    if ( v3 >= 0 )
    {
      v3 = CreateRegistryKey(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows Media Foundation\\ByteStreamHandlers",
             &v6);
      if ( v3 >= 0 )
      {
        v3 = CreateRegistryKey(v6, L".flac", &hKey);
        if ( v3 >= 0 )
          v3 = RegSetValueExW(hKey, sz, 0, 1u, L"MF FLAC Media Source ByteStreamHandler", 2 * v7 + 2);
      }
    }
    if ( hKey )
      RegCloseKey(hKey);
    if ( v6 )
      RegCloseKey(v6);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18001a540  mov     [rsp-8+arg_0], rbx
0x18001a545  mov     [rsp-8+arg_8], rsi
0x18001a54a  push    rbp
0x18001a54b  lea     rbp, [rsp-57h]
0x18001a550  sub     rsp, 0B0h
0x18001a557  mov     rax, cs:__security_cookie
0x18001a55e  xor     rax, rsp
0x18001a561  mov     [rbp+57h+var_10], rax
0x18001a565  lea     rsi, Data; "MF FLAC Media Source ByteStreamHandler"
0x18001a56c  mov     [rbp+57h+var_78], 0
0x18001a574  mov     rcx, rsi; unsigned __int16 *
0x18001a577  mov     [rbp+57h+hKey], 0
0x18001a57f  lea     r8, [rbp+57h+var_70]; unsigned __int64 *
0x18001a583  mov     [rbp+57h+var_70], 0
0x18001a58b  mov     edx, 7FFFFFFFh; unsigned __int64
0x18001a590  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18001a595  mov     ebx, eax
0x18001a597  test    eax, eax
0x18001a599  js      loc_18001A63D
0x18001a59f  mov     r8d, 27h ; '''; cchMax
0x18001a5a5  lea     rdx, [rbp+57h+sz]; lpsz
0x18001a5a9  lea     rcx, CLSID_MFFLACBytestreamHandler; rguid
0x18001a5b0  call    cs:__imp_StringFromGUID2
0x18001a5b6  mov     ebx, eax
0x18001a5b8  test    eax, eax
0x18001a5ba  js      short loc_18001A61F
0x18001a5bc  lea     r8, [rbp+57h+var_78]; HKEY *
0x18001a5c0  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x18001a5c7  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows Media Foun"...
0x18001a5ce  call    ?CreateRegistryKey@@YAJPEAUHKEY__@@PEBGPEAPEAU1@@Z; CreateRegistryKey(HKEY__ *,ushort const *,HKEY__ * *)
0x18001a5d3  mov     ebx, eax
0x18001a5d5  test    eax, eax
0x18001a5d7  js      short loc_18001A61F
0x18001a5d9  mov     rcx, [rbp+57h+var_78]; HKEY
0x18001a5dd  lea     r8, [rbp+57h+hKey]; HKEY *
0x18001a5e1  lea     rdx, aFlac; ".flac"
0x18001a5e8  call    ?CreateRegistryKey@@YAJPEAUHKEY__@@PEBGPEAPEAU1@@Z; CreateRegistryKey(HKEY__ *,ushort const *,HKEY__ * *)
0x18001a5ed  mov     ebx, eax
0x18001a5ef  test    eax, eax
0x18001a5f1  js      short loc_18001A61F
0x18001a5f3  mov     eax, dword ptr [rbp+57h+var_70]
0x18001a5f6  lea     rdx, [rbp+57h+sz]; lpValueName
0x18001a5fa  mov     rcx, [rbp+57h+hKey]; hKey
0x18001a5fe  mov     r9d, 1; dwType
0x18001a604  xor     r8d, r8d; Reserved
0x18001a607  lea     eax, ds:2[rax*2]
0x18001a60e  mov     [rsp+0B0h+cbData], eax; cbData
0x18001a612  mov     [rsp+0B0h+lpData], rsi; lpData
0x18001a617  call    cs:__imp_RegSetValueExW
0x18001a61d  mov     ebx, eax
0x18001a61f  mov     rcx, [rbp+57h+hKey]; hKey
0x18001a623  test    rcx, rcx
0x18001a626  jz      short loc_18001A62E
0x18001a628  call    cs:__imp_RegCloseKey
0x18001a62e  mov     rcx, [rbp+57h+var_78]; hKey
0x18001a632  test    rcx, rcx
0x18001a635  jz      short loc_18001A63D
0x18001a637  call    cs:__imp_RegCloseKey
0x18001a63d  mov     eax, ebx
0x18001a63f  mov     rcx, [rbp+57h+var_10]
0x18001a643  xor     rcx, rsp; StackCookie
0x18001a646  call    __security_check_cookie
0x18001a64b  lea     r11, [rsp+0B0h+var_s0]
0x18001a653  mov     rbx, [r11+10h]
0x18001a657  mov     rsi, [r11+18h]
0x18001a65b  mov     rsp, r11
0x18001a65e  pop     rbp
0x18001a65f  retn
```
