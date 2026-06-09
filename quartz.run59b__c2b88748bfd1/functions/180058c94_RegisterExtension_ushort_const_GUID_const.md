# RegisterExtension(ushort const *,_GUID const *)

- ea: `0x180058c94`
- end: `0x180058dca`
- name: `?RegisterExtension@@YAJPEBGPEBU_GUID@@@Z`
- size: `310`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800580c0`

## callees

- `0x1800078b0`
- `0x1800388a0`
- `0x180058c94`
- `0x180058e08`
- `0x180058f3c`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x180058cd5`
- `KERNEL32!lstrlenW` at `0x180058ce8`
- `KERNEL32!lstrlenW` at `0x180058cd5`
- `KERNEL32!lstrlenW` at `0x180058ce8`
- `ADVAPI32!RegCreateKeyW` at `0x180058d32`
- `ADVAPI32!RegCreateKeyW` at `0x180058d32`
- `ADVAPI32!RegCloseKey` at `0x180058d95`
- `ADVAPI32!RegCloseKey` at `0x180058d95`

## string_xrefs

- `0x180058caf`: `Media Type\Extensions\`

## pseudocode

```c
__int64 __fastcall RegisterExtension(const unsigned __int16 *a1, const struct _GUID *a2)
{
  int v2; // ebx
  LSTATUS v4; // eax
  unsigned int v5; // ebx
  HKEY phkResult; // [rsp+20h] [rbp-1B8h] BYREF
  WCHAR String[200]; // [rsp+30h] [rbp-1A8h] BYREF

  phkResult = 0;
  StringCchCopyW(String, 0xC8u, L"Media Type\\Extensions\\");
  v2 = lstrlenW(L".mp3");
  if ( v2 + lstrlenW(String) + 1 > 200 )
    return 2147942511LL;
  StringCchCatW(String, 0xC8u, L".mp3");
  v4 = RegCreateKeyW(HKEY_CLASSES_ROOT, String, &phkResult);
  v5 = v4;
  if ( v4 )
  {
    if ( v4 > 0 )
      return (unsigned __int16)v4 | 0x80070000;
  }
  else
  {
    if ( (unsigned int)WriteGUID(phkResult, L"Source Filter", &CLSID_AsyncReader) )
    {
      WriteGUID(phkResult, L"Media Type", (GUID *)&MEDIATYPE_Stream);
      WriteGUID(phkResult, L"Subtype", (GUID *)&MEDIASUBTYPE_MPEG1Audio);
    }
    RegCloseKey(phkResult);
  }
  return v5;
}

```

## disassembly

```asm
0x180058c94  push    rbx
0x180058c96  sub     rsp, 1D0h
0x180058c9d  mov     rax, cs:__security_cookie
0x180058ca4  xor     rax, rsp
0x180058ca7  mov     [rsp+1D8h+var_18], rax
0x180058caf  lea     r8, aMediaTypeExten; "Media Type\\Extensions\\"
0x180058cb6  mov     [rsp+1D8h+phkResult], 0
0x180058cbf  mov     edx, 0C8h; unsigned __int64
0x180058cc4  lea     rcx, [rsp+1D8h+String]; unsigned __int16 *
0x180058cc9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180058cce  lea     rcx, aMp3; ".mp3"
0x180058cd5  call    cs:__imp_lstrlenW
0x180058cdc  nop     dword ptr [rax+rax+00h]
0x180058ce1  lea     rcx, [rsp+1D8h+String]; lpString
0x180058ce6  mov     ebx, eax
0x180058ce8  call    cs:__imp_lstrlenW
0x180058cef  nop     dword ptr [rax+rax+00h]
0x180058cf4  lea     ecx, [rax+1]
0x180058cf7  add     ecx, ebx
0x180058cf9  cmp     ecx, 0C8h
0x180058cff  jle     short loc_180058D0B
0x180058d01  mov     eax, 8007006Fh
0x180058d06  jmp     loc_180058DB0
0x180058d0b  lea     r8, aMp3; ".mp3"
0x180058d12  mov     edx, 0C8h; unsigned __int64
0x180058d17  lea     rcx, [rsp+1D8h+String]; unsigned __int16 *
0x180058d1c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180058d21  lea     r8, [rsp+1D8h+phkResult]; phkResult
0x180058d26  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180058d2d  lea     rdx, [rsp+1D8h+String]; lpSubKey
0x180058d32  call    cs:__imp_RegCreateKeyW
0x180058d39  nop     dword ptr [rax+rax+00h]
0x180058d3e  mov     ebx, eax
0x180058d40  test    eax, eax
0x180058d42  jnz     short loc_180058DA3
0x180058d44  mov     rcx, [rsp+1D8h+phkResult]; hKey
0x180058d49  lea     r8, CLSID_AsyncReader; rguid
0x180058d50  lea     rdx, aSourceFilter; "Source Filter"
0x180058d57  call    ?WriteGUID@@YAHPEAUHKEY__@@PEBGPEBU_GUID@@@Z; WriteGUID(HKEY__ *,ushort const *,_GUID const *)
0x180058d5c  test    eax, eax
0x180058d5e  jz      short loc_180058D90
0x180058d60  mov     rcx, [rsp+1D8h+phkResult]; hKey
0x180058d65  lea     r8, MEDIATYPE_Stream; rguid
0x180058d6c  lea     rdx, aMediaType; "Media Type"
0x180058d73  call    ?WriteGUID@@YAHPEAUHKEY__@@PEBGPEBU_GUID@@@Z; WriteGUID(HKEY__ *,ushort const *,_GUID const *)
0x180058d78  mov     rcx, [rsp+1D8h+phkResult]; hKey
0x180058d7d  lea     r8, MEDIASUBTYPE_MPEG1Audio; rguid
0x180058d84  lea     rdx, aSubtype; "Subtype"
0x180058d8b  call    ?WriteGUID@@YAHPEAUHKEY__@@PEBGPEBU_GUID@@@Z; WriteGUID(HKEY__ *,ushort const *,_GUID const *)
0x180058d90  mov     rcx, [rsp+1D8h+phkResult]; hKey
0x180058d95  call    cs:__imp_RegCloseKey
0x180058d9c  nop     dword ptr [rax+rax+00h]
0x180058da1  jmp     short loc_180058DAE
0x180058da3  jle     short loc_180058DAE
0x180058da5  movzx   ebx, ax
0x180058da8  or      ebx, 80070000h
0x180058dae  mov     eax, ebx
0x180058db0  mov     rcx, [rsp+1D8h+var_18]
0x180058db8  xor     rcx, rsp; StackCookie
0x180058dbb  call    __security_check_cookie
0x180058dc0  add     rsp, 1D0h
0x180058dc7  pop     rbx
0x180058dc8  retn
```
