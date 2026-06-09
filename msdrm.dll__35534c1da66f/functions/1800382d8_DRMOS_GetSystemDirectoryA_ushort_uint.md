# DRMOS::GetSystemDirectoryA(ushort *,uint)

- ea: `0x1800382d8`
- end: `0x180038385`
- name: `?GetSystemDirectoryA@DRMOS@@YAIPEAGI@Z`
- size: `173`
- prototype: `unsigned int __fastcall(LPWSTR lpBuffer, UINT uSize, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180037e58`

## callees

- `0x1800382d8`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003831b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003831b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180038364`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180038364`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18003830d`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180038346`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18003830d`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180038346`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180038374`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180038374`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x1800382f5`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x1800382f5`

## string_xrefs

- `0x1800382ec`: `kernel32.dll`
- `0x18003833c`: `GetSystemWow64DirectoryW`

## pseudocode

```c
__int64 __fastcall DRMOS::GetSystemDirectoryA(LPWSTR lpBuffer, UINT uSize)
{
  HMODULE LibraryW; // rax
  HMODULE v5; // rbx
  FARPROC ProcAddress; // rdi
  HANDLE CurrentProcess; // rax
  FARPROC v8; // rax
  UINT SystemDirectoryW; // edi
  int v11; // [rsp+60h] [rbp+18h] BYREF

  v11 = 0;
  LibraryW = LoadLibraryW(L"kernel32.dll");
  v5 = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, "IsWow64Process");
    if ( ProcAddress )
    {
      CurrentProcess = GetCurrentProcess();
      if ( ((unsigned int (__fastcall *)(HANDLE, int *))ProcAddress)(CurrentProcess, &v11) )
      {
        if ( v11 )
        {
          v8 = GetProcAddress(v5, "GetSystemWow64DirectoryW");
          if ( v8 )
          {
            SystemDirectoryW = ((__int64 (__fastcall *)(LPWSTR, _QWORD))v8)(lpBuffer, uSize);
LABEL_8:
            FreeLibrary(v5);
            return SystemDirectoryW;
          }
        }
      }
    }
  }
  SystemDirectoryW = GetSystemDirectoryW(lpBuffer, uSize);
  if ( v5 )
    goto LABEL_8;
  return SystemDirectoryW;
}

```

## disassembly

```asm
0x1800382d8  push    rbx
0x1800382da  push    rbp
0x1800382db  push    rsi
0x1800382dc  push    rdi
0x1800382dd  sub     rsp, 28h
0x1800382e1  mov     rbp, rcx
0x1800382e4  mov     [rsp+48h+arg_10], 0
0x1800382ec  lea     rcx, aKernel32Dll; "kernel32.dll"
0x1800382f3  mov     esi, edx
0x1800382f5  call    cs:__imp_LoadLibraryW
0x1800382fb  mov     rbx, rax
0x1800382fe  test    rax, rax
0x180038301  jz      short loc_18003835F
0x180038303  lea     rdx, aIswow64process; "IsWow64Process"
0x18003830a  mov     rcx, rax; hModule
0x18003830d  call    cs:__imp_GetProcAddress
0x180038313  mov     rdi, rax
0x180038316  test    rax, rax
0x180038319  jz      short loc_18003835F
0x18003831b  call    cs:__imp_GetCurrentProcess
0x180038321  mov     rcx, rax
0x180038324  lea     rdx, [rsp+48h+arg_10]
0x180038329  mov     rax, rdi
0x18003832c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038331  test    eax, eax
0x180038333  jz      short loc_18003835F
0x180038335  cmp     [rsp+48h+arg_10], 0
0x18003833a  jz      short loc_18003835F
0x18003833c  lea     rdx, aGetsystemwow64; "GetSystemWow64DirectoryW"
0x180038343  mov     rcx, rbx; hModule
0x180038346  call    cs:__imp_GetProcAddress
0x18003834c  test    rax, rax
0x18003834f  jz      short loc_18003835F
0x180038351  mov     edx, esi
0x180038353  mov     rcx, rbp
0x180038356  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003835b  mov     edi, eax
0x18003835d  jmp     short loc_180038371
0x18003835f  mov     edx, esi; uSize
0x180038361  mov     rcx, rbp; lpBuffer
0x180038364  call    cs:__imp_GetSystemDirectoryW
0x18003836a  mov     edi, eax
0x18003836c  test    rbx, rbx
0x18003836f  jz      short loc_18003837A
0x180038371  mov     rcx, rbx; hLibModule
0x180038374  call    cs:__imp_FreeLibrary
0x18003837a  mov     eax, edi
0x18003837c  add     rsp, 28h
0x180038380  pop     rdi
0x180038381  pop     rsi
0x180038382  pop     rbp
0x180038383  pop     rbx
0x180038384  retn
```
