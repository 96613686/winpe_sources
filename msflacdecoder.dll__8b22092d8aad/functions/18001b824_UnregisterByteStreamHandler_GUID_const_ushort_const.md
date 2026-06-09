# UnregisterByteStreamHandler(_GUID const &,ushort const *)

- ea: `0x18001b824`
- end: `0x18001b8d7`
- name: `?UnregisterByteStreamHandler@@YAJAEBU_GUID@@PEBG@Z`
- size: `179`
- prototype: `__int64 __fastcall(const struct _GUID *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001c300`

## callees

- `0x180001e80`
- `0x18001b6c0`
- `0x18001b824`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001b883`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001b883`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18001b8a3`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18001b8a3`

## pseudocode

```c
__int64 __fastcall UnregisterByteStreamHandler(const struct _GUID *a1, const unsigned __int16 *a2)
{
  int v2; // ebx
  LSTATUS v3; // eax
  OLECHAR sz[40]; // [rsp+30h] [rbp-278h] BYREF
  WCHAR SubKey[264]; // [rsp+80h] [rbp-228h] BYREF

  v2 = StringCchPrintfW(
         SubKey,
         0x104u,
         L"%s\\%s",
         L"Software\\Microsoft\\Windows Media Foundation\\ByteStreamHandlers",
         L".flac");
  if ( v2 >= 0 )
  {
    v2 = StringFromGUID2(&CLSID_MFFLACBytestreamHandler, sz, 39);
    if ( v2 >= 0 )
    {
      v3 = RegDeleteKeyValueW(HKEY_LOCAL_MACHINE, SubKey, sz);
      if ( v3 )
      {
        if ( v3 > 0 )
          return (unsigned __int16)v3 | 0x80070000;
        else
          return (unsigned int)v3;
      }
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18001b824  push    rbx
0x18001b826  sub     rsp, 2A0h
0x18001b82d  mov     rax, cs:__security_cookie
0x18001b834  xor     rax, rsp
0x18001b837  mov     [rsp+2A8h+var_18], rax
0x18001b83f  lea     rax, aFlac; ".flac"
0x18001b846  mov     edx, 104h; unsigned __int64
0x18001b84b  lea     r9, aSoftwareMicros; "Software\\Microsoft\\Windows Media Foun"...
0x18001b852  mov     [rsp+2A8h+var_288], rax
0x18001b857  lea     r8, aSS; "%s\\%s"
0x18001b85e  lea     rcx, [rsp+2A8h+SubKey]; unsigned __int16 *
0x18001b866  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001b86b  mov     ebx, eax
0x18001b86d  test    eax, eax
0x18001b86f  js      short loc_18001B8BC
0x18001b871  mov     r8d, 27h ; '''; cchMax
0x18001b877  lea     rdx, [rsp+2A8h+sz]; lpsz
0x18001b87c  lea     rcx, CLSID_MFFLACBytestreamHandler; rguid
0x18001b883  call    cs:__imp_StringFromGUID2
0x18001b889  mov     ebx, eax
0x18001b88b  test    eax, eax
0x18001b88d  js      short loc_18001B8BC
0x18001b88f  lea     r8, [rsp+2A8h+sz]; lpValueName
0x18001b894  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001b89b  lea     rdx, [rsp+2A8h+SubKey]; lpSubKey
0x18001b8a3  call    cs:__imp_RegDeleteKeyValueW
0x18001b8a9  test    eax, eax
0x18001b8ab  jz      short loc_18001B8BC
0x18001b8ad  jg      short loc_18001B8B3
0x18001b8af  mov     ebx, eax
0x18001b8b1  jmp     short loc_18001B8BC
0x18001b8b3  movzx   ebx, ax
0x18001b8b6  or      ebx, 80070000h
0x18001b8bc  mov     eax, ebx
0x18001b8be  mov     rcx, [rsp+2A8h+var_18]
0x18001b8c6  xor     rcx, rsp; StackCookie
0x18001b8c9  call    __security_check_cookie
0x18001b8ce  add     rsp, 2A0h
0x18001b8d5  pop     rbx
0x18001b8d6  retn
```
