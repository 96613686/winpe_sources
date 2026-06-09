# DsRolepSetExtensionPointKeys

- ea: `0x18000fea8`
- end: `0x18000fedb`
- name: `DsRolepSetExtensionPointKeys`
- size: `51`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x1800100c0`
- `0x180011240`
- `0x180012460`

## callees

- `0x18000fdd4`
- `0x18000fea8`

## string_xrefs

- `0x18000feac`: `%systemroot%\system32\ntdsa.dll`
- `0x18000feb3`: `DirectoryServiceExtPt`
- `0x18000fec3`: `%systemroot%\system32\lsadb.dll`

## pseudocode

```c
__int64 __fastcall DsRolepSetExtensionPointKeys(HKEY a1)
{
  __int64 result; // rax
  HKEY v2; // rcx

  result = DsRolepSetExtensionKey(a1, L"DirectoryServiceExtPt", (const BYTE *)L"%systemroot%\\system32\\ntdsa.dll");
  if ( !(_DWORD)result )
    return DsRolepSetExtensionKey(v2, L"LsaDbExtPt", (const BYTE *)L"%systemroot%\\system32\\lsadb.dll");
  return result;
}

```

## disassembly

```asm
0x18000fea8  sub     rsp, 28h
0x18000feac  lea     r8, aSystemrootSyst_2; "%systemroot%\\system32\\ntdsa.dll"
0x18000feb3  lea     rdx, aDirectoryservi; "DirectoryServiceExtPt"
0x18000feba  call    DsRolepSetExtensionKey
0x18000febf  test    eax, eax
0x18000fec1  jnz     short loc_18000FED6
0x18000fec3  lea     r8, aSystemrootSyst_0; "%systemroot%\\system32\\lsadb.dll"
0x18000feca  lea     rdx, aLsadbextpt; "LsaDbExtPt"
0x18000fed1  call    DsRolepSetExtensionKey
0x18000fed6  add     rsp, 28h
0x18000feda  retn
```
