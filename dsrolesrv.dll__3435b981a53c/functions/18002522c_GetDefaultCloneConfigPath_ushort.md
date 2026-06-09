# GetDefaultCloneConfigPath(ushort *)

- ea: `0x18002522c`
- end: `0x180025276`
- name: `?GetDefaultCloneConfigPath@@YAKPEAG@Z`
- size: `74`
- prototype: `DWORD __fastcall(unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800249ec`
- `0x180026428`

## callees

- `0x18001cd60`
- `0x18002522c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002523a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002523a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025249`

## string_xrefs

- `0x18002525f`: `DefaultDCCloneAllowList.xml`

## pseudocode

```c
DWORD __fastcall GetDefaultCloneConfigPath(unsigned __int16 *a1)
{
  unsigned __int64 v2; // rdx
  unsigned __int64 v4; // rdx

  if ( !GetSystemDirectoryW(a1, 0x104u) )
    return GetLastError();
  StringCchCatW(a1, v2, L"\\");
  StringCchCatW(a1, v4, L"DefaultDCCloneAllowList.xml");
  return 0;
}

```

## disassembly

```asm
0x18002522c  push    rbx
0x18002522e  sub     rsp, 20h
0x180025232  mov     edx, 104h; uSize
0x180025237  mov     rbx, rcx
0x18002523a  call    cs:__imp_GetSystemDirectoryW
0x180025240  test    eax, eax
0x180025242  jnz     short loc_180025250
0x180025244  add     rsp, 20h
0x180025248  pop     rbx
0x180025249  jmp     cs:__imp_GetLastError
0x180025250  lea     r8, pszSrc; "\\"
0x180025257  mov     rcx, rbx; unsigned __int16 *
0x18002525a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002525f  lea     r8, aDefaultdcclone; "DefaultDCCloneAllowList.xml"
0x180025266  mov     rcx, rbx; unsigned __int16 *
0x180025269  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002526e  xor     eax, eax
0x180025270  add     rsp, 20h
0x180025274  pop     rbx
0x180025275  retn
```
