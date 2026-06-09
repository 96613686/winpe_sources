# MiniDumpOsImports::Initialize(void)

- ea: `0x18041053c`
- end: `0x180410704`
- name: `?Initialize@MiniDumpOsImports@@QEAAJXZ`
- size: `456`
- prototype: `__int64 __fastcall(MiniDumpOsImports *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1803ffef0`

## callees

- `0x18008fa64`
- `0x180090e00`
- `0x180093698`
- `0x18041053c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1804105c2`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180410602`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180410641`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18041067e`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18041069b`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1804106d9`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1804105c2`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180410602`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180410641`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18041067e`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18041069b`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1804106d9`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x1804105a3`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x1804105e3`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x180410621`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x180410660`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x1804106ba`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x1804105a3`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x1804105e3`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x180410621`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x180410660`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x1804106ba`
- `ntdll!RtlRunOnceExecuteOnce` at `0x180410576`
- `ntdll!RtlRunOnceExecuteOnce` at `0x180410576`

## string_xrefs

- `0x180410657`: `ntdll.dll`
- `0x18041059a`: `kernel32.dll`
- `0x1804105da`: `api-ms-win-core-processthreads-l1-1-2.dll`
- `0x180410618`: `api-ms-win-downlevel-kernel32-l2-1-0.dll`
- `0x18041063a`: `CreateFileMappingA`
- `0x1804105b8`: `GetThreadContext`
- `0x1804105f8`: `GetThreadContext`
- `0x1804106b1`: `api-ms-win-core-wow64-l1-1-2.dll`
- `0x180410691`: `RtlWow64GetThreadContext`
- `0x180410674`: `NtQueryInformationThread`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
__int64 __fastcall MiniDumpOsImports::Initialize(MiniDumpOsImports *this)
{
  HMODULE Library; // rax
  HMODULE v4; // rax
  HMODULE v5; // rax
  HMODULE v6; // rax
  HMODULE v7; // rax
  __int64 v8; // [rsp+38h] [rbp+10h] BYREF

  if ( !(unsigned __int8)RtlMrdataAcquireSectionWriteAccess(&g_RunOnceMrdataCommitObtained) )
    return 2147500034LL;
  RtlRunOnceExecuteOnce(&g_RunOnceMrdataCommitObtained, RunOnceObtainMrdataCommit, &g_RunOnceMrdataCommitObtained, 0);
  RtlMrdataObtainSectionWriteAccess::RtlMrdataObtainSectionWriteAccess(
    (RtlMrdataObtainSectionWriteAccess *)&v8,
    (const void *)&g_RunOnceMrdataCommitObtained);
  RtlMrdataReleaseSectionWriteAccess(&g_RunOnceMrdataCommitObtained);
  Library = LoadLibraryExA("kernel32.dll", 0, 0);
  *((_QWORD *)this + 1) = Library;
  if ( Library )
  {
    *(&g_Kernel32CallsMdwd + 1) = GetProcAddress(Library, "GetThreadContext");
  }
  else
  {
    v4 = LoadLibraryExA("api-ms-win-core-processthreads-l1-1-2.dll", 0, 0);
    *((_QWORD *)this + 2) = v4;
    if ( v4 )
      *(&g_Kernel32CallsMdwd + 1) = GetProcAddress(v4, "GetThreadContext");
    v5 = LoadLibraryExA("api-ms-win-downlevel-kernel32-l2-1-0.dll", 0, 0);
    *((_QWORD *)this + 3) = v5;
    if ( !v5 )
      goto LABEL_9;
  }
  g_Kernel32CallsMdwd = GetProcAddress(*((HMODULE *)this + 1), "CreateFileMappingA");
LABEL_9:
  v6 = LoadLibraryExA("ntdll.dll", 0, 0);
  *(_QWORD *)this = v6;
  if ( v6 )
  {
    g_NtDllCallsMdwd = GetProcAddress(v6, "NtQueryInformationThread");
    *(&g_NtDllCallsMdwd + 1) = GetProcAddress(*(HMODULE *)this, "RtlWow64GetThreadContext");
  }
  v7 = LoadLibraryExA("api-ms-win-core-wow64-l1-1-2.dll", 0, 0);
  *((_QWORD *)this + 4) = v7;
  if ( v7 )
    g_CoreWow64CallsMdwd = GetProcAddress(v7, "IsWow64Process2");
  RtlMrdataReleaseSectionWriteAccess(v8);
  return 0;
}

```

## disassembly

```asm
0x18041053c  mov     [rsp+arg_0], rbx
0x180410541  push    rdi
0x180410542  sub     rsp, 20h
0x180410546  mov     rbx, rcx
0x180410549  lea     rdi, ?g_RunOnceMrdataCommitObtained@@3T_RTL_RUN_ONCE@@C; _RTL_RUN_ONCE volatile g_RunOnceMrdataCommitObtained
0x180410550  mov     rcx, rdi
0x180410553  call    RtlMrdataAcquireSectionWriteAccess
0x180410558  test    al, al
0x18041055a  jnz     short loc_180410566
0x18041055c  mov     eax, 80004002h
0x180410561  jmp     loc_1804106F8
0x180410566  xor     r9d, r9d
0x180410569  lea     rdx, ?RunOnceObtainMrdataCommit@@YAKPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; RunOnceObtainMrdataCommit(_RTL_RUN_ONCE *,void *,void * *)
0x180410570  mov     r8, rdi
0x180410573  mov     rcx, rdi
0x180410576  call    cs:__imp_RtlRunOnceExecuteOnce
0x18041057d  nop     dword ptr [rax+rax+00h]
0x180410582  mov     rdx, rdi; void *
0x180410585  lea     rcx, [rsp+28h+arg_8]; this
0x18041058a  call    ??0RtlMrdataObtainSectionWriteAccess@@QEAA@PEBX@Z; RtlMrdataObtainSectionWriteAccess::RtlMrdataObtainSectionWriteAccess(void const *)
0x18041058f  mov     rcx, rdi
0x180410592  call    RtlMrdataReleaseSectionWriteAccess
0x180410597  xor     r8d, r8d; dwFlags
0x18041059a  lea     rcx, aKernel32Dll; "kernel32.dll"
0x1804105a1  xor     edx, edx; hFile
0x1804105a3  call    cs:__imp_LoadLibraryExA
0x1804105aa  nop     dword ptr [rax+rax+00h]
0x1804105af  mov     [rbx+8], rax
0x1804105b3  test    rax, rax
0x1804105b6  jz      short loc_1804105D7
0x1804105b8  lea     rdx, aGetthreadconte; "GetThreadContext"
0x1804105bf  mov     rcx, rax; hModule
0x1804105c2  call    cs:__imp_GetProcAddress
0x1804105c9  nop     dword ptr [rax+rax+00h]
0x1804105ce  mov     qword ptr cs:?g_Kernel32CallsMdwd@@3UKERNEL32_CALLS_MDWD@@C+8, rax; KERNEL32_CALLS_MDWD volatile g_Kernel32CallsMdwd
0x1804105d5  jmp     short loc_180410636
0x1804105d7  xor     r8d, r8d; dwFlags
0x1804105da  lea     rcx, aApiMsWinCorePr_4; "api-ms-win-core-processthreads-l1-1-2.d"...
0x1804105e1  xor     edx, edx; hFile
0x1804105e3  call    cs:__imp_LoadLibraryExA
0x1804105ea  nop     dword ptr [rax+rax+00h]
0x1804105ef  mov     [rbx+10h], rax
0x1804105f3  test    rax, rax
0x1804105f6  jz      short loc_180410615
0x1804105f8  lea     rdx, aGetthreadconte; "GetThreadContext"
0x1804105ff  mov     rcx, rax; hModule
0x180410602  call    cs:__imp_GetProcAddress
0x180410609  nop     dword ptr [rax+rax+00h]
0x18041060e  mov     qword ptr cs:?g_Kernel32CallsMdwd@@3UKERNEL32_CALLS_MDWD@@C+8, rax; KERNEL32_CALLS_MDWD volatile g_Kernel32CallsMdwd
0x180410615  xor     r8d, r8d; dwFlags
0x180410618  lea     rcx, aApiMsWinDownle_0; "api-ms-win-downlevel-kernel32-l2-1-0.dl"...
0x18041061f  xor     edx, edx; hFile
0x180410621  call    cs:__imp_LoadLibraryExA
0x180410628  nop     dword ptr [rax+rax+00h]
0x18041062d  mov     [rbx+18h], rax
0x180410631  test    rax, rax
0x180410634  jz      short loc_180410654
0x180410636  mov     rcx, [rbx+8]; hModule
0x18041063a  lea     rdx, aCreatefilemapp; "CreateFileMappingA"
0x180410641  call    cs:__imp_GetProcAddress
0x180410648  nop     dword ptr [rax+rax+00h]
0x18041064d  mov     qword ptr cs:?g_Kernel32CallsMdwd@@3UKERNEL32_CALLS_MDWD@@C, rax; KERNEL32_CALLS_MDWD volatile g_Kernel32CallsMdwd
0x180410654  xor     r8d, r8d; dwFlags
0x180410657  lea     rcx, ModuleName; "ntdll.dll"
0x18041065e  xor     edx, edx; hFile
0x180410660  call    cs:__imp_LoadLibraryExA
0x180410667  nop     dword ptr [rax+rax+00h]
0x18041066c  mov     [rbx], rax
0x18041066f  test    rax, rax
0x180410672  jz      short loc_1804106AE
0x180410674  lea     rdx, aNtqueryinforma_1; "NtQueryInformationThread"
0x18041067b  mov     rcx, rax; hModule
0x18041067e  call    cs:__imp_GetProcAddress
0x180410685  nop     dword ptr [rax+rax+00h]
0x18041068a  mov     qword ptr cs:?g_NtDllCallsMdwd@@3UNTDLL_CALLS_MDWD@@C, rax; NTDLL_CALLS_MDWD volatile g_NtDllCallsMdwd
0x180410691  lea     rdx, aRtlwow64getthr; "RtlWow64GetThreadContext"
0x180410698  mov     rcx, [rbx]; hModule
0x18041069b  call    cs:__imp_GetProcAddress
0x1804106a2  nop     dword ptr [rax+rax+00h]
0x1804106a7  mov     qword ptr cs:?g_NtDllCallsMdwd@@3UNTDLL_CALLS_MDWD@@C+8, rax; NTDLL_CALLS_MDWD volatile g_NtDllCallsMdwd
0x1804106ae  xor     r8d, r8d; dwFlags
0x1804106b1  lea     rcx, aApiMsWinCoreWo_0; "api-ms-win-core-wow64-l1-1-2.dll"
0x1804106b8  xor     edx, edx; hFile
0x1804106ba  call    cs:__imp_LoadLibraryExA
0x1804106c1  nop     dword ptr [rax+rax+00h]
0x1804106c6  mov     [rbx+20h], rax
0x1804106ca  test    rax, rax
0x1804106cd  jz      short loc_1804106EC
0x1804106cf  lea     rdx, aIswow64process_0; "IsWow64Process2"
0x1804106d6  mov     rcx, rax; hModule
0x1804106d9  call    cs:__imp_GetProcAddress
0x1804106e0  nop     dword ptr [rax+rax+00h]
0x1804106e5  mov     cs:?g_CoreWow64CallsMdwd@@3UCOREWOW64_CALLS_MDWD@@C, rax; COREWOW64_CALLS_MDWD volatile g_CoreWow64CallsMdwd
0x1804106ec  mov     rcx, [rsp+28h+arg_8]
0x1804106f1  call    RtlMrdataReleaseSectionWriteAccess
0x1804106f6  xor     eax, eax
0x1804106f8  mov     rbx, [rsp+28h+arg_0]
0x1804106fd  add     rsp, 20h
0x180410701  pop     rdi
0x180410702  retn
```
