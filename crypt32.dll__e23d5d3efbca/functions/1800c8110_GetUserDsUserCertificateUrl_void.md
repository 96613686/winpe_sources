# GetUserDsUserCertificateUrl(void)

- ea: `0x1800c8110`
- end: `0x1800c81a5`
- name: `?GetUserDsUserCertificateUrl@@YAPEAGXZ`
- size: `149`
- prototype: `unsigned __int16 *(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18005be80`

## callees

- `0x1800c8110`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c8162`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c817c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c8162`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c817c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c816a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c818f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c816a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c818f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800c8187`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800c8187`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c8142`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c8142`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x1800c812a`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x1800c812a`

## string_xrefs

- `0x1800c811a`: `cryptnet.dll`

## pseudocode

```c
unsigned __int16 *GetUserDsUserCertificateUrl(void)
{
  HMODULE LibraryA; // rax
  HMODULE v1; // rdi
  FARPROC ProcAddress; // rax
  DWORD LastError; // eax
  unsigned __int16 *result; // rax
  DWORD v5; // ebx
  __int64 v6; // [rsp+30h] [rbp+8h] BYREF

  v6 = 0;
  LibraryA = LoadLibraryA("cryptnet.dll");
  v1 = LibraryA;
  if ( !LibraryA || (ProcAddress = GetProcAddress(LibraryA, "I_CryptNetGetUserDsStoreUrl")) == 0 )
  {
LABEL_5:
    result = 0;
    v6 = 0;
    if ( !v1 )
      return result;
    goto LABEL_6;
  }
  if ( !((unsigned int (__fastcall *)(const wchar_t *, __int64 *))ProcAddress)(L"userCertificate", &v6) )
  {
    LastError = GetLastError();
    SetLastError(LastError);
    goto LABEL_5;
  }
LABEL_6:
  v5 = GetLastError();
  FreeLibrary(v1);
  SetLastError(v5);
  return (unsigned __int16 *)v6;
}

```

## disassembly

```asm
0x1800c8110  mov     [rsp+arg_8], rbx
0x1800c8115  push    rdi
0x1800c8116  sub     rsp, 20h
0x1800c811a  lea     rcx, LibFileName; "cryptnet.dll"
0x1800c8121  mov     [rsp+28h+arg_0], 0
0x1800c812a  call    cs:__imp_LoadLibraryA
0x1800c8130  mov     rdi, rax
0x1800c8133  test    rax, rax
0x1800c8136  jz      short loc_1800C8170
0x1800c8138  lea     rdx, aICryptnetgetus; "I_CryptNetGetUserDsStoreUrl"
0x1800c813f  mov     rcx, rax; hModule
0x1800c8142  call    cs:__imp_GetProcAddress
0x1800c8148  test    rax, rax
0x1800c814b  jz      short loc_1800C8170
0x1800c814d  lea     rdx, [rsp+28h+arg_0]
0x1800c8152  lea     rcx, aUsercertificat; "userCertificate"
0x1800c8159  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c815e  test    eax, eax
0x1800c8160  jnz     short loc_1800C817C
0x1800c8162  call    cs:__imp_GetLastError
0x1800c8168  mov     ecx, eax; dwErrCode
0x1800c816a  call    cs:__imp_SetLastError
0x1800c8170  xor     eax, eax
0x1800c8172  mov     [rsp+28h+arg_0], rax
0x1800c8177  test    rdi, rdi
0x1800c817a  jz      short loc_1800C819A
0x1800c817c  call    cs:__imp_GetLastError
0x1800c8182  mov     rcx, rdi; hLibModule
0x1800c8185  mov     ebx, eax
0x1800c8187  call    cs:__imp_FreeLibrary
0x1800c818d  mov     ecx, ebx; dwErrCode
0x1800c818f  call    cs:__imp_SetLastError
0x1800c8195  mov     rax, [rsp+28h+arg_0]
0x1800c819a  mov     rbx, [rsp+28h+arg_8]
0x1800c819f  add     rsp, 20h
0x1800c81a3  pop     rdi
0x1800c81a4  retn
```
