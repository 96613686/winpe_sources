# GetEdpProcs(void)

- ea: `0x1801477bc`
- end: `0x18014788f`
- name: `?GetEdpProcs@@YA_NXZ`
- size: `211`
- prototype: `bool(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1801281e0`
- `0x1801f9e6c`

## callees

- `0x18000f358`
- `0x18005921c`
- `0x1801477bc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180147857`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180147857`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180147824`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180147824`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180147802`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180147802`

## string_xrefs

- `0x1801477f5`: `edputil.dll`

## pseudocode

```c
char GetEdpProcs(void)
{
  char v0; // bl
  HMODULE Library; // rax
  int (*ProcAddress)(void); // rcx
  unsigned int v4; // [rsp+30h] [rbp+8h] BYREF

  CWriteLock::CWriteLock(&v4, 0);
  v0 = 0;
  if ( g_pfnEdpGetIsManaged )
    goto LABEL_11;
  Library = hLibModule;
  if ( hLibModule != (HMODULE)-1LL )
  {
    if ( hLibModule )
      goto LABEL_9;
    Library = LoadLibraryExW(L"edputil.dll", 0, 0x800u);
    hLibModule = Library;
    if ( Library )
    {
      ProcAddress = (int (*)(void))GetProcAddress(Library, "EdpGetIsManaged");
      g_pfnEdpGetIsManaged = ProcAddress;
      Library = hLibModule;
    }
    else
    {
      ProcAddress = g_pfnEdpGetIsManaged;
    }
    if ( ProcAddress )
      goto LABEL_11;
    if ( Library )
    {
LABEL_9:
      FreeLibrary(Library);
      ProcAddress = g_pfnEdpGetIsManaged;
    }
    hLibModule = (HMODULE)-1LL;
    if ( ProcAddress )
LABEL_11:
      v0 = 1;
  }
  CWriteLock::~CWriteLock((CWriteLock *)&v4);
  return v0;
}

```

## disassembly

```asm
0x1801477bc  push    rbx
0x1801477be  sub     rsp, 20h
0x1801477c2  xor     edx, edx
0x1801477c4  lea     rcx, [rsp+28h+arg_0]
0x1801477c9  call    ??0CWriteLock@@QEAA@W4LOCK_TYPE@@@Z; CWriteLock::CWriteLock(LOCK_TYPE)
0x1801477ce  xor     ebx, ebx
0x1801477d0  cmp     cs:?g_pfnEdpGetIsManaged@@3P6AHXZEA, rbx; int (*g_pfnEdpGetIsManaged)(void)
0x1801477d7  jnz     loc_18014787A
0x1801477dd  mov     rax, cs:hLibModule
0x1801477e4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801477e8  jz      loc_18014787C
0x1801477ee  test    rax, rax
0x1801477f1  jnz     short loc_180147854
0x1801477f3  xor     edx, edx; hFile
0x1801477f5  lea     rcx, aEdputilDll; "edputil.dll"
0x1801477fc  mov     r8d, 800h; dwFlags
0x180147802  call    cs:__imp_LoadLibraryExW
0x180147809  nop     dword ptr [rax+rax+00h]
0x18014780e  mov     cs:hLibModule, rax
0x180147815  test    rax, rax
0x180147818  jz      short loc_180147843
0x18014781a  lea     rdx, aEdpgetismanage; "EdpGetIsManaged"
0x180147821  mov     rcx, rax; hModule
0x180147824  call    cs:__imp_GetProcAddress
0x18014782b  nop     dword ptr [rax+rax+00h]
0x180147830  mov     rcx, rax
0x180147833  mov     cs:?g_pfnEdpGetIsManaged@@3P6AHXZEA, rax; int (*g_pfnEdpGetIsManaged)(void)
0x18014783a  mov     rax, cs:hLibModule
0x180147841  jmp     short loc_18014784A
0x180147843  mov     rcx, cs:?g_pfnEdpGetIsManaged@@3P6AHXZEA; int (*g_pfnEdpGetIsManaged)(void)
0x18014784a  test    rcx, rcx
0x18014784d  jnz     short loc_18014787A
0x18014784f  test    rax, rax
0x180147852  jz      short loc_18014786A
0x180147854  mov     rcx, rax; hLibModule
0x180147857  call    cs:__imp_FreeLibrary
0x18014785e  nop     dword ptr [rax+rax+00h]
0x180147863  mov     rcx, cs:?g_pfnEdpGetIsManaged@@3P6AHXZEA; int (*g_pfnEdpGetIsManaged)(void)
0x18014786a  mov     cs:hLibModule, 0FFFFFFFFFFFFFFFFh
0x180147875  test    rcx, rcx
0x180147878  jz      short loc_18014787C
0x18014787a  mov     bl, 1
0x18014787c  lea     rcx, [rsp+28h+arg_0]; this
0x180147881  call    ??1CWriteLock@@QEAA@XZ; CWriteLock::~CWriteLock(void)
0x180147886  mov     al, bl
0x180147888  add     rsp, 20h
0x18014788c  pop     rbx
0x18014788d  retn
```
