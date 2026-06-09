# WebCoreShutdown(ulong)

- ea: `0x180002170`
- end: `0x18000221e`
- name: `?WebCoreShutdown@@YAJK@Z`
- size: `174`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x180001048`
- `0x180002170`
- `0x18000290c`
- `0x180004010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002209`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002209`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000217f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000217f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800021bd`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800021bd`

## pseudocode

```c
__int64 __fastcall WebCoreShutdown(int a1)
{
  unsigned int v2; // ebx

  EnterCriticalSection(&g_csHWebMethods);
  if ( g_hIisW3AdmModule && g_pfnWebCoreShutdown )
  {
    v2 = g_pfnWebCoreShutdown(a1);
    g_pDebug = PuDeleteDebugPrintsObject();
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
0x180002170  push    rbx
0x180002172  sub     rsp, 20h
0x180002176  mov     ebx, ecx
0x180002178  lea     rcx, ?g_csHWebMethods@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000217f  call    cs:__imp_EnterCriticalSection
0x180002186  nop     dword ptr [rax+rax+00h]
0x18000218b  cmp     cs:?g_hIisW3AdmModule@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * g_hIisW3AdmModule
0x180002193  jz      short loc_1800021FD
0x180002195  mov     rax, cs:?g_pfnWebCoreShutdown@@3P6AJH@ZEA; long (*g_pfnWebCoreShutdown)(int)
0x18000219c  test    rax, rax
0x18000219f  jz      short loc_1800021FD
0x1800021a1  mov     ecx, ebx
0x1800021a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800021a8  mov     ebx, eax
0x1800021aa  call    PuDeleteDebugPrintsObject
0x1800021af  mov     rcx, cs:?g_hIisW3AdmModule@@3PEAUHINSTANCE__@@EA; hLibModule
0x1800021b6  mov     cs:g_pDebug, rax
0x1800021bd  call    cs:__imp_FreeLibrary
0x1800021c4  nop     dword ptr [rax+rax+00h]
0x1800021c9  mov     rcx, cs:?g_szAppPool@@3PEAGEA; Block
0x1800021d0  mov     cs:?g_hIisW3AdmModule@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * g_hIisW3AdmModule
0x1800021db  mov     cs:?g_pfnWebCoreShutdown@@3P6AJH@ZEA, 0; long (*g_pfnWebCoreShutdown)(int)
0x1800021e6  test    rcx, rcx
0x1800021e9  jz      short loc_180002202
0x1800021eb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800021f0  mov     cs:?g_szAppPool@@3PEAGEA, 0; ushort * g_szAppPool
0x1800021fb  jmp     short loc_180002202
0x1800021fd  mov     ebx, 80070426h
0x180002202  lea     rcx, ?g_csHWebMethods@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180002209  call    cs:__imp_LeaveCriticalSection
0x180002210  nop     dword ptr [rax+rax+00h]
0x180002215  mov     eax, ebx
0x180002217  add     rsp, 20h
0x18000221b  pop     rbx
0x18000221c  retn
```
