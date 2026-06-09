# WebCoreShutdown(ulong)

- ea: `0x1800020b0`
- end: `0x18000214b`
- name: `?WebCoreShutdown@@YAJK@Z`
- size: `155`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x180001048`
- `0x1800020b0`
- `0x180002788`
- `0x180003010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000213d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000213d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800020bf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800020bf`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800020f7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800020f7`

## pseudocode

```c
__int64 __fastcall WebCoreShutdown(int a1)
{
  unsigned int v2; // ebx

  EnterCriticalSection(&g_csHWebMethods);
  if ( g_hIisW3AdmModule && g_pfnWebCoreShutdown )
  {
    v2 = g_pfnWebCoreShutdown(a1);
    g_pDebug = (HGLOBAL)PuDeleteDebugPrintsObject();
    FreeLibrary(g_hIisW3AdmModule);
    g_hIisW3AdmModule = 0;
    g_pfnWebCoreShutdown = 0;
    if ( g_szAppPool )
    {
      operator delete(g_szAppPool);
      g_szAppPool = 0;
    }
  }
  else
  {
    v2 = -2147023834;
  }
  LeaveCriticalSection(&g_csHWebMethods);
  return v2;
}

```

## disassembly

```asm
0x1800020b0  push    rbx
0x1800020b2  sub     rsp, 20h
0x1800020b6  mov     ebx, ecx
0x1800020b8  lea     rcx, ?g_csHWebMethods@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800020bf  call    cs:__imp_EnterCriticalSection
0x1800020c5  cmp     cs:?g_hIisW3AdmModule@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * g_hIisW3AdmModule
0x1800020cd  jz      short loc_180002131
0x1800020cf  mov     rax, cs:?g_pfnWebCoreShutdown@@3P6AJH@ZEA; long (*g_pfnWebCoreShutdown)(int)
0x1800020d6  test    rax, rax
0x1800020d9  jz      short loc_180002131
0x1800020db  mov     ecx, ebx
0x1800020dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020e2  mov     ebx, eax
0x1800020e4  call    PuDeleteDebugPrintsObject
0x1800020e9  mov     rcx, cs:?g_hIisW3AdmModule@@3PEAUHINSTANCE__@@EA; hLibModule
0x1800020f0  mov     cs:g_pDebug, rax
0x1800020f7  call    cs:__imp_FreeLibrary
0x1800020fd  mov     rcx, cs:?g_szAppPool@@3PEAGEA; Block
0x180002104  mov     cs:?g_hIisW3AdmModule@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * g_hIisW3AdmModule
0x18000210f  mov     cs:?g_pfnWebCoreShutdown@@3P6AJH@ZEA, 0; long (*g_pfnWebCoreShutdown)(int)
0x18000211a  test    rcx, rcx
0x18000211d  jz      short loc_180002136
0x18000211f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002124  mov     cs:?g_szAppPool@@3PEAGEA, 0; ushort * g_szAppPool
0x18000212f  jmp     short loc_180002136
0x180002131  mov     ebx, 80070426h
0x180002136  lea     rcx, ?g_csHWebMethods@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000213d  call    cs:__imp_LeaveCriticalSection
0x180002143  mov     eax, ebx
0x180002145  add     rsp, 20h
0x180002149  pop     rbx
0x18000214a  retn
```
