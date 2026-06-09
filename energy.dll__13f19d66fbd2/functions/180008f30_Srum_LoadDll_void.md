# Srum::LoadDll(void)

- ea: `0x180008f30`
- end: `0x180008fcb`
- name: `?LoadDll@Srum@@AEAAJXZ`
- size: `155`
- prototype: `__int64 __fastcall(Srum *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007920`
- `0x1800337d8`

## callees

- `0x180008740`
- `0x180008f30`
- `0x180042e08`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008fa9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008fa9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008f62`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008f7b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008f62`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008f7b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180008f49`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180008f49`

## pseudocode

```c
__int64 __fastcall Srum::LoadDll(Srum *this)
{
  HMODULE Library; // rax
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8
  FARPROC ProcAddress; // rax
  FARPROC v7; // rax
  unsigned int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  signed int LastError; // eax

  Library = LoadLibraryExW(L"srumapi", 0, 0);
  *((_QWORD *)this + 2) = Library;
  if ( Library
    && (ProcAddress = GetProcAddress(Library, "SruFreeRecordSet"), (*(_QWORD *)this = ProcAddress) != 0)
    && (v7 = GetProcAddress(*((HMODULE *)this + 2), "SruQueryStats"), (*((_QWORD *)this + 1) = v7) != 0) )
  {
    return 0;
  }
  else
  {
    v8 = -2147467259;
    MicrosoftTelemetryAssertTriggeredNoArgs(v4, v3, v5);
    if ( !(unsigned int)Srum::UnloadDll(this) )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(v10, v9, v11);
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180008f30  mov     [rsp+arg_0], rbx
0x180008f35  push    rdi
0x180008f36  sub     rsp, 20h
0x180008f3a  mov     rdi, rcx
0x180008f3d  xor     r8d, r8d; dwFlags
0x180008f40  lea     rcx, LibFileName; "srumapi"
0x180008f47  xor     edx, edx; hFile
0x180008f49  call    cs:__imp_LoadLibraryExW
0x180008f4f  mov     [rdi+10h], rax
0x180008f53  test    rax, rax
0x180008f56  jz      short loc_180008F8E
0x180008f58  lea     rdx, aSrufreerecords; "SruFreeRecordSet"
0x180008f5f  mov     rcx, rax; hModule
0x180008f62  call    cs:__imp_GetProcAddress
0x180008f68  mov     [rdi], rax
0x180008f6b  test    rax, rax
0x180008f6e  jz      short loc_180008F8E
0x180008f70  mov     rcx, [rdi+10h]; hModule
0x180008f74  lea     rdx, aSruquerystats; "SruQueryStats"
0x180008f7b  call    cs:__imp_GetProcAddress
0x180008f81  mov     [rdi+8], rax
0x180008f85  test    rax, rax
0x180008f88  jz      short loc_180008F8E
0x180008f8a  xor     ebx, ebx
0x180008f8c  jmp     short loc_180008FBE
0x180008f8e  mov     ebx, 80004005h
0x180008f93  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180008f98  mov     rcx, rdi; this
0x180008f9b  call    ?UnloadDll@Srum@@AEAAHXZ; Srum::UnloadDll(void)
0x180008fa0  test    eax, eax
0x180008fa2  jnz     short loc_180008FBE
0x180008fa4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180008fa9  call    cs:__imp_GetLastError
0x180008faf  mov     ebx, eax
0x180008fb1  test    eax, eax
0x180008fb3  jle     short loc_180008FBE
0x180008fb5  movzx   ebx, ax
0x180008fb8  or      ebx, 80070000h
0x180008fbe  mov     eax, ebx
0x180008fc0  mov     rbx, [rsp+28h+arg_0]
0x180008fc5  add     rsp, 20h
0x180008fc9  pop     rdi
0x180008fca  retn
```
