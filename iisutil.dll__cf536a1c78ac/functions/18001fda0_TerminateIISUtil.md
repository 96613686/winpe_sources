# TerminateIISUtil

- ea: `0x18001fda0`
- end: `0x18001feb2`
- name: `TerminateIISUtil`
- size: `274`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180008000`
- `0x180019270`
- `0x18001fda0`
- `0x180020f40`
- `0x180021550`
- `0x1800241e8`
- `0x18002c800`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fea6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001fdab`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001fdab`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001fe85`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001fe85`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001fe67`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001fe67`

## string_xrefs

- `0x18001fdf3`: `servercommon\inetsrv\iis\iisrearc\core\common\util\init_iisutil.cxx`

## pseudocode

```c
void TerminateIISUtil()
{
  EnterCriticalSection(&CriticalSection);
  if ( (g_dwDebugFlagsIISUtil & 3) != 0 && (g_dwDebugFlagsIISUtil & 4) != 0 )
    PuDbgPrint(
      (struct _DEBUG_PRINTS *)g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\init_iisutil.cxx",
      0x158u,
      "TerminateIISUtil",
      "TerminateIISUtil, %d %s\n",
      dword_180050504[0]);
  if ( !--*(_DWORD *)dword_180050504 )
  {
    ALLOC_CACHE_HANDLER::ResetLookasideCleanupInterval();
    SchedulerTerminate();
    UninitializeTokenAcl();
    if ( g_pLocalizedLangString )
    {
      LANG_STRING::Terminate(g_pLocalizedLangString);
      operator delete(g_pLocalizedLangString);
      g_pLocalizedLangString = 0;
    }
    if ( g_hLocalizedResourceDll )
    {
      FreeLibrary(g_hLocalizedResourceDll);
      g_hLocalizedResourceDll = 0;
    }
    DeleteCriticalSection(&g_csLocalizedResourceDll);
    g_fInitialized = 0;
  }
  LeaveCriticalSection(&CriticalSection);
}

```

## disassembly

```asm
0x18001fda0  sub     rsp, 48h
0x18001fda4  lea     rcx, CriticalSection; lpCriticalSection
0x18001fdab  call    cs:__imp_EnterCriticalSection
0x18001fdb2  nop     dword ptr [rax+rax+00h]
0x18001fdb7  mov     eax, cs:g_dwDebugFlagsIISUtil
0x18001fdbd  test    al, 3
0x18001fdbf  setnz   cl
0x18001fdc2  test    al, 4
0x18001fdc4  setnz   al
0x18001fdc7  test    al, cl
0x18001fdc9  jz      short loc_18001FE1B
0x18001fdcb  mov     eax, cs:dword_180050504
0x18001fdd1  lea     rdx, byte_180033FA9
0x18001fdd8  cmp     eax, 1
0x18001fddb  lea     rcx, aUninitializing; "Uninitializing"
0x18001fde2  lea     r9, aTerminateiisut_0; "TerminateIISUtil"
0x18001fde9  mov     r8d, 158h; unsigned int
0x18001fdef  cmovnz  rcx, rdx
0x18001fdf3  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18001fdfa  mov     [rsp+48h+var_18], rcx
0x18001fdff  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18001fe06  mov     dword ptr [rsp+48h+var_20], eax; char
0x18001fe0a  lea     rax, aTerminateiisut_1; "TerminateIISUtil, %d %s\n"
0x18001fe11  mov     [rsp+48h+var_28], rax; char *
0x18001fe16  call    PuDbgPrint
0x18001fe1b  sub     cs:dword_180050504, 1
0x18001fe22  jnz     short loc_18001FE9B
0x18001fe24  call    ?ResetLookasideCleanupInterval@ALLOC_CACHE_HANDLER@@SAHXZ; ALLOC_CACHE_HANDLER::ResetLookasideCleanupInterval(void)
0x18001fe29  call    ?SchedulerTerminate@@YAXXZ; SchedulerTerminate(void)
0x18001fe2e  call    ?UninitializeTokenAcl@@YAXXZ; UninitializeTokenAcl(void)
0x18001fe33  mov     rcx, cs:?g_pLocalizedLangString@@3PEAVLANG_STRING@@EA; this
0x18001fe3a  test    rcx, rcx
0x18001fe3d  jz      short loc_18001FE5B
0x18001fe3f  call    ?Terminate@LANG_STRING@@QEAAJXZ; LANG_STRING::Terminate(void)
0x18001fe44  mov     rcx, cs:?g_pLocalizedLangString@@3PEAVLANG_STRING@@EA; Block
0x18001fe4b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001fe50  mov     cs:?g_pLocalizedLangString@@3PEAVLANG_STRING@@EA, 0; LANG_STRING * g_pLocalizedLangString
0x18001fe5b  mov     rcx, cs:?g_hLocalizedResourceDll@@3PEAUHINSTANCE__@@EA; hLibModule
0x18001fe62  test    rcx, rcx
0x18001fe65  jz      short loc_18001FE7E
0x18001fe67  call    cs:__imp_FreeLibrary
0x18001fe6e  nop     dword ptr [rax+rax+00h]
0x18001fe73  mov     cs:?g_hLocalizedResourceDll@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * g_hLocalizedResourceDll
0x18001fe7e  lea     rcx, ?g_csLocalizedResourceDll@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001fe85  call    cs:__imp_DeleteCriticalSection
0x18001fe8c  nop     dword ptr [rax+rax+00h]
0x18001fe91  mov     cs:?g_fInitialized@@3HA, 0; int g_fInitialized
0x18001fe9b  lea     rcx, CriticalSection
0x18001fea2  add     rsp, 48h
0x18001fea6  jmp     cs:__imp_LeaveCriticalSection
```
