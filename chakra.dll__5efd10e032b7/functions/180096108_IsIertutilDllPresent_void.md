# IsIertutilDllPresent(void)

- ea: `0x180096108`
- end: `0x1800961b5`
- name: `?IsIertutilDllPresent@@YA_NXZ`
- size: `173`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800960c4`

## callees

- `0x180096108`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180096143`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180096184`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180096143`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180096184`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180096127`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180096127`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18009615d`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18009615d`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180096198`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180096198`

## string_xrefs

- `0x180096154`: `iertutil.dll`

## pseudocode

```c
bool IsIertutilDllPresent(void)
{
  HMODULE Library; // rbx

  if ( IertutilDllPresentStatus )
    return IertutilDllPresentStatus == 1;
  EnterCriticalSection(&cs_IertutilDll);
  if ( IertutilDllPresentStatus )
  {
    LeaveCriticalSection(&cs_IertutilDll);
  }
  else
  {
    Library = LoadLibraryExW(L"iertutil.dll", 0, 0);
    IertutilDllPresentStatus = 2 - (Library != 0);
    LeaveCriticalSection(&cs_IertutilDll);
    if ( Library )
      FreeLibrary(Library);
  }
  return IertutilDllPresentStatus == 1;
}

```

## disassembly

```asm
0x180096108  push    rbx
0x18009610a  sub     rsp, 20h
0x18009610e  mov     eax, cs:?IertutilDllPresentStatus@@3W4IertutilDllStatus@@A; IertutilDllStatus IertutilDllPresentStatus
0x180096114  test    eax, eax
0x180096116  jz      short loc_180096120
0x180096118  cmp     eax, 1
0x18009611b  jmp     loc_1800961AB
0x180096120  lea     rcx, ?cs_IertutilDll@@3VCriticalSection@@A; lpCriticalSection
0x180096127  call    cs:__imp_EnterCriticalSection
0x18009612e  nop     dword ptr [rax+rax+00h]
0x180096133  cmp     cs:?IertutilDllPresentStatus@@3W4IertutilDllStatus@@A, 0; IertutilDllStatus IertutilDllPresentStatus
0x18009613a  jz      short loc_180096151
0x18009613c  lea     rcx, ?cs_IertutilDll@@3VCriticalSection@@A; lpCriticalSection
0x180096143  call    cs:__imp_LeaveCriticalSection
0x18009614a  nop     dword ptr [rax+rax+00h]
0x18009614f  jmp     short loc_1800961A4
0x180096151  xor     r8d, r8d; dwFlags
0x180096154  lea     rcx, LibFileName; "iertutil.dll"
0x18009615b  xor     edx, edx; hFile
0x18009615d  call    cs:__imp_LoadLibraryExW
0x180096164  nop     dword ptr [rax+rax+00h]
0x180096169  mov     rcx, rax
0x18009616c  mov     rbx, rax
0x18009616f  neg     rcx
0x180096172  lea     rcx, ?cs_IertutilDll@@3VCriticalSection@@A; lpCriticalSection
0x180096179  sbb     edx, edx
0x18009617b  add     edx, 2
0x18009617e  mov     cs:?IertutilDllPresentStatus@@3W4IertutilDllStatus@@A, edx; IertutilDllStatus IertutilDllPresentStatus
0x180096184  call    cs:__imp_LeaveCriticalSection
0x18009618b  nop     dword ptr [rax+rax+00h]
0x180096190  test    rbx, rbx
0x180096193  jz      short loc_1800961A4
0x180096195  mov     rcx, rbx; hLibModule
0x180096198  call    cs:__imp_FreeLibrary
0x18009619f  nop     dword ptr [rax+rax+00h]
0x1800961a4  cmp     cs:?IertutilDllPresentStatus@@3W4IertutilDllStatus@@A, 1; IertutilDllStatus IertutilDllPresentStatus
0x1800961ab  setz    al
0x1800961ae  add     rsp, 20h
0x1800961b2  pop     rbx
0x1800961b3  retn
```
