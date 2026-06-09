# DllHandle::GetProcAddress(char const *)

- ea: `0x18000d5cc`
- end: `0x18000d609`
- name: `?GetProcAddress@DllHandle@@AEBAP6A_JXZPEBD@Z`
- size: `61`
- prototype: `FARPROC __fastcall(HMODULE *, const CHAR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000a5cc`

## callees

- `0x18000a5ac`
- `0x18000d4a8`
- `0x18000d5cc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d5d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d5d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d5de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d5de`

## pseudocode

```c
FARPROC __fastcall DllHandle::GetProcAddress(HMODULE *a1, const CHAR *a2)
{
  FARPROC result; // rax
  DWORD LastError; // eax
  __int64 v4; // rcx

  result = GetProcAddress(*a1, a2);
  if ( !result )
  {
    LastError = GetLastError();
    if ( LastError != 127 )
      SystemError::Throw<unsigned int>(v4, LastError);
    SystemError::Throw<long>((__int64)L"GetProcAddress", 127);
  }
  return result;
}

```

## disassembly

```asm
0x18000d5cc  sub     rsp, 28h
0x18000d5d0  mov     rcx, [rcx]; hModule
0x18000d5d3  call    cs:__imp_GetProcAddress
0x18000d5d9  test    rax, rax
0x18000d5dc  jnz     short loc_18000D5EF
0x18000d5de  call    cs:__imp_GetLastError
0x18000d5e4  mov     edx, 7Fh
0x18000d5e9  cmp     eax, edx
0x18000d5eb  jz      short loc_18000D5FC
0x18000d5ed  jmp     short loc_18000D5F4
0x18000d5ef  add     rsp, 28h
0x18000d5f3  retn
0x18000d5f4  mov     edx, eax
0x18000d5f6  call    ??$Throw@I@SystemError@@SAXPEB_WI@Z; SystemError::Throw<uint>(wchar_t const *,uint)
0x18000d5fc  lea     rcx, aGetprocaddress; "GetProcAddress"
0x18000d603  call    ??$Throw@J@SystemError@@SAXPEB_WJ@Z; SystemError::Throw<long>(wchar_t const *,long)
```
