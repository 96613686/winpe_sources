# UnattendInitializeLogEx2

- ea: `0x18006920c`
- end: `0x1800692fb`
- name: `UnattendInitializeLogEx2`
- size: `239`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180008e10`

## callees

- `0x180068f64`
- `0x18006920c`
- `0x180069664`
- `0x18006a114`
- `0x18006e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800692c9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800692c9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180069265`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180069265`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800692f4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180069219`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180069219`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800692d4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800692d4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800692e2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800692e2`

## string_xrefs

- `0x18006925c`: `wdscore.dll`

## pseudocode

```c
void UnattendInitializeLogEx2()
{
  const wchar_t *Expand; // rax
  wchar_t *v1; // rbx
  HMODULE Library; // rax
  HANDLE ProcessHeap; // rax

  EnterCriticalSection(&CriticalSection);
  ++dword_1800A76F4;
  if ( dword_1800A76F0 )
    goto LABEL_14;
  hLibModule = 0;
  Expand = (const wchar_t *)AllocateExpand(L"%windir%\\Panther\\UnattendGC");
  v1 = (wchar_t *)Expand;
  if ( Expand )
    CreatePath(Expand);
  Library = LoadLibraryExW(L"wdscore.dll", 0, 0);
  hLibModule = Library;
  if ( !Library )
    goto LABEL_9;
  if ( (int)InitFuncPointerTable() < 0 || !qword_1800A76E0 )
  {
    Library = hLibModule;
LABEL_9:
    if ( !dword_1800A76F0 && Library )
      FreeLibrary(Library);
    goto LABEL_12;
  }
  qword_1800A76E0(0, 50393088, v1);
  dword_1800A76F0 = 1;
  dword_1800A7728 = 1;
LABEL_12:
  if ( v1 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v1);
  }
LABEL_14:
  LeaveCriticalSection(&CriticalSection);
}

```

## disassembly

```asm
0x18006920c  push    rbx
0x18006920e  sub     rsp, 20h
0x180069212  lea     rcx, CriticalSection; lpCriticalSection
0x180069219  call    cs:__imp_EnterCriticalSection
0x18006921f  inc     cs:dword_1800A76F4
0x180069225  cmp     cs:dword_1800A76F0, 0
0x18006922c  jnz     loc_1800692E8
0x180069232  lea     rcx, aWindirPantherU; "%windir%\\Panther\\UnattendGC"
0x180069239  mov     cs:hLibModule, 0
0x180069244  call    AllocateExpand
0x180069249  mov     rbx, rax
0x18006924c  test    rax, rax
0x18006924f  jz      short loc_180069259
0x180069251  mov     rcx, rax
0x180069254  call    CreatePath
0x180069259  xor     r8d, r8d; dwFlags
0x18006925c  lea     rcx, aWdscoreDll; "wdscore.dll"
0x180069263  xor     edx, edx; hFile
0x180069265  call    cs:__imp_LoadLibraryExW
0x18006926b  mov     cs:hLibModule, rax
0x180069272  test    rax, rax
0x180069275  jz      short loc_1800692B8
0x180069277  call    InitFuncPointerTable
0x18006927c  test    eax, eax
0x18006927e  js      short loc_1800692B1
0x180069280  mov     rax, cs:qword_1800A76E0
0x180069287  test    rax, rax
0x18006928a  jz      short loc_1800692B1
0x18006928c  mov     r8, rbx
0x18006928f  mov     edx, 300F000h
0x180069294  xor     ecx, ecx
0x180069296  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006929b  mov     cs:dword_1800A76F0, 1
0x1800692a5  mov     cs:dword_1800A7728, 1
0x1800692af  jmp     short loc_1800692CF
0x1800692b1  mov     rax, cs:hLibModule
0x1800692b8  cmp     cs:dword_1800A76F0, 0
0x1800692bf  jnz     short loc_1800692CF
0x1800692c1  test    rax, rax
0x1800692c4  jz      short loc_1800692CF
0x1800692c6  mov     rcx, rax; hLibModule
0x1800692c9  call    cs:__imp_FreeLibrary
0x1800692cf  test    rbx, rbx
0x1800692d2  jz      short loc_1800692E8
0x1800692d4  call    cs:__imp_GetProcessHeap
0x1800692da  mov     r8, rbx; lpMem
0x1800692dd  xor     edx, edx; dwFlags
0x1800692df  mov     rcx, rax; hHeap
0x1800692e2  call    cs:__imp_HeapFree
0x1800692e8  lea     rcx, CriticalSection
0x1800692ef  add     rsp, 20h
0x1800692f3  pop     rbx
0x1800692f4  jmp     cs:__imp_LeaveCriticalSection
```
