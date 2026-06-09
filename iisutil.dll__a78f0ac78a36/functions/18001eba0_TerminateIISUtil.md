# TerminateIISUtil

- ea: `0x18001eba0`
- end: `0x18001ec9b`
- name: `TerminateIISUtil`
- size: `251`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180007300`
- `0x180018438`
- `0x18001eba0`
- `0x18001fc10`
- `0x1800201b0`
- `0x1800229d8`
- `0x18002a8f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ec94`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ebab`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ebab`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001ec79`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001ec79`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001ec61`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001ec61`

## string_xrefs

- `0x18001ebed`: `servercommon\inetsrv\iis\iisrearc\core\common\util\init_iisutil.cxx`

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
      dword_18004E50C[0]);
  if ( !--*(_DWORD *)dword_18004E50C )
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
0x18001eba0  sub     rsp, 48h
0x18001eba4  lea     rcx, CriticalSection; lpCriticalSection
0x18001ebab  call    cs:__imp_EnterCriticalSection
0x18001ebb1  mov     eax, cs:g_dwDebugFlagsIISUtil
0x18001ebb7  test    al, 3
0x18001ebb9  setnz   cl
0x18001ebbc  test    al, 4
0x18001ebbe  setnz   al
0x18001ebc1  test    al, cl
0x18001ebc3  jz      short loc_18001EC15
0x18001ebc5  mov     eax, cs:dword_18004E50C
0x18001ebcb  lea     rdx, byte_180031FA9
0x18001ebd2  cmp     eax, 1
0x18001ebd5  lea     rcx, aUninitializing; "Uninitializing"
0x18001ebdc  lea     r9, aTerminateiisut_0; "TerminateIISUtil"
0x18001ebe3  mov     r8d, 158h; unsigned int
0x18001ebe9  cmovnz  rcx, rdx
0x18001ebed  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18001ebf4  mov     [rsp+48h+var_18], rcx
0x18001ebf9  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18001ec00  mov     dword ptr [rsp+48h+var_20], eax; char
0x18001ec04  lea     rax, aTerminateiisut_1; "TerminateIISUtil, %d %s\n"
0x18001ec0b  mov     [rsp+48h+var_28], rax; char *
0x18001ec10  call    PuDbgPrint
0x18001ec15  sub     cs:dword_18004E50C, 1
0x18001ec1c  jnz     short loc_18001EC89
0x18001ec1e  call    ?ResetLookasideCleanupInterval@ALLOC_CACHE_HANDLER@@SAHXZ; ALLOC_CACHE_HANDLER::ResetLookasideCleanupInterval(void)
0x18001ec23  call    ?SchedulerTerminate@@YAXXZ; SchedulerTerminate(void)
0x18001ec28  call    ?UninitializeTokenAcl@@YAXXZ; UninitializeTokenAcl(void)
0x18001ec2d  mov     rcx, cs:?g_pLocalizedLangString@@3PEAVLANG_STRING@@EA; this
0x18001ec34  test    rcx, rcx
0x18001ec37  jz      short loc_18001EC55
0x18001ec39  call    ?Terminate@LANG_STRING@@QEAAJXZ; LANG_STRING::Terminate(void)
0x18001ec3e  mov     rcx, cs:?g_pLocalizedLangString@@3PEAVLANG_STRING@@EA; Block
0x18001ec45  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001ec4a  mov     cs:?g_pLocalizedLangString@@3PEAVLANG_STRING@@EA, 0; LANG_STRING * g_pLocalizedLangString
0x18001ec55  mov     rcx, cs:?g_hLocalizedResourceDll@@3PEAUHINSTANCE__@@EA; hLibModule
0x18001ec5c  test    rcx, rcx
0x18001ec5f  jz      short loc_18001EC72
0x18001ec61  call    cs:__imp_FreeLibrary
0x18001ec67  mov     cs:?g_hLocalizedResourceDll@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * g_hLocalizedResourceDll
0x18001ec72  lea     rcx, ?g_csLocalizedResourceDll@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001ec79  call    cs:__imp_DeleteCriticalSection
0x18001ec7f  mov     cs:?g_fInitialized@@3HA, 0; int g_fInitialized
0x18001ec89  lea     rcx, CriticalSection
0x18001ec90  add     rsp, 48h
0x18001ec94  jmp     cs:__imp_LeaveCriticalSection
```
