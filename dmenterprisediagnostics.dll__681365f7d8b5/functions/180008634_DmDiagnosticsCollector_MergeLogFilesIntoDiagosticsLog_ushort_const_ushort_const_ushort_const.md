# DmDiagnosticsCollector::MergeLogFilesIntoDiagosticsLog(ushort const *,ushort const *,ushort const *)

- ea: `0x180008634`
- end: `0x1800087c4`
- name: `?MergeLogFilesIntoDiagosticsLog@DmDiagnosticsCollector@@SAJPEBG00@Z`
- size: `400`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800084a0`

## callees

- `0x180001800`
- `0x180005bf4`
- `0x180005c14`
- `0x180006cb0`
- `0x180008634`
- `0x18000d67c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800086df`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008794`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800086df`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008794`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008668`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008668`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008653`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800086cb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008780`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008653`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800086cb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008780`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180008750`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180008750`

## pseudocode

```c
__int64 __fastcall DmDiagnosticsCollector::MergeLogFilesIntoDiagosticsLog(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  HANDLE ProcessHeap; // rax
  _QWORD *v4; // rdi
  int LastError; // ebx
  __int64 v6; // rdx
  HANDLE v7; // rax
  const char *v9; // r9
  HANDLE v10; // rax
  int v11; // [rsp+20h] [rbp-858h]
  __int64 v12; // [rsp+40h] [rbp-838h] BYREF
  WCHAR ExistingFileName[1032]; // [rsp+50h] [rbp-828h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+878h] [rbp+0h]

  ProcessHeap = GetProcessHeap();
  v4 = HeapAlloc(ProcessHeap, 0, 0x10u);
  *v4 = L"\\data\\SystemData\\Etw\\DiagnosticsCircularFiltered.etl";
  v4[1] = L"\\data\\SystemData\\Etw\\DiagnosticsCriticalFiltered.etl";
  LastError = StringCchPrintfW(
                ExistingFileName,
                0x401u,
                L"%s.merged",
                L"\\data\\SystemData\\Etw\\EnterpriseDiagnostics.etl");
  if ( LastError < 0 )
  {
    v6 = 219;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisediagnosticsetw\\lib\\dmdiagnosticscollector.cpp",
      (const char *)(unsigned int)LastError,
      v11);
LABEL_4:
    v7 = GetProcessHeap();
    HeapFree(v7, 0, v4);
    return (unsigned int)LastError;
  }
  LODWORD(v12) = 0;
  LastError = MergeEtlExWithErrorContext(2, (int)v4, (int)ExistingFileName, 0xFFFFF, 0, (__int64)&v12, 0);
  if ( LastError < 0 )
  {
    v6 = 222;
    goto LABEL_3;
  }
  if ( !MoveFileExW(ExistingFileName, L"\\data\\SystemData\\Etw\\EnterpriseDiagnostics.etl", 1u) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xE1,
                  (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisediagnosticsetw\\lib\\dmdiagnosticscollector.cpp",
                  v9);
    goto LABEL_4;
  }
  v10 = GetProcessHeap();
  HeapFree(v10, 0, v4);
  return 0;
}

```

## disassembly

```asm
0x180008634  mov     [rsp+arg_0], rbx
0x180008639  push    rdi
0x18000863a  sub     rsp, 870h
0x180008641  mov     rax, cs:__security_cookie
0x180008648  xor     rax, rsp
0x18000864b  mov     [rsp+878h+var_18], rax
0x180008653  call    cs:__imp_GetProcessHeap
0x18000865a  nop     dword ptr [rax+rax+00h]
0x18000865f  xor     edx, edx; dwFlags
0x180008661  mov     rcx, rax; hHeap
0x180008664  lea     r8d, [rdx+10h]; dwBytes
0x180008668  call    cs:__imp_HeapAlloc
0x18000866f  nop     dword ptr [rax+rax+00h]
0x180008674  lea     r9, NewFileName; "\\data\\SystemData\\Etw\\EnterpriseDiag"...
0x18000867b  mov     edx, 401h; unsigned __int64
0x180008680  mov     rdi, rax
0x180008683  lea     r8, aSMerged; "%s.merged"
0x18000868a  lea     rax, aDataSystemdata_0; "\\data\\SystemData\\Etw\\DiagnosticsCir"...
0x180008691  lea     rcx, [rsp+878h+ExistingFileName]; unsigned __int16 *
0x180008696  mov     [rdi], rax
0x180008699  lea     rax, aDataSystemdata; "\\data\\SystemData\\Etw\\DiagnosticsCri"...
0x1800086a0  mov     [rdi+8], rax
0x1800086a4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800086a9  mov     ebx, eax
0x1800086ab  test    eax, eax
0x1800086ad  jns     short loc_1800086F2
0x1800086af  mov     edx, 0DBh; void *
0x1800086b4  mov     rcx, [rsp+878h]; this
0x1800086bc  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1800086c3  mov     r9d, ebx; char *
0x1800086c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800086cb  call    cs:__imp_GetProcessHeap
0x1800086d2  nop     dword ptr [rax+rax+00h]
0x1800086d7  mov     r8, rdi; lpMem
0x1800086da  xor     edx, edx; dwFlags
0x1800086dc  mov     rcx, rax; hHeap
0x1800086df  call    cs:__imp_HeapFree
0x1800086e6  nop     dword ptr [rax+rax+00h]
0x1800086eb  mov     eax, ebx
0x1800086ed  jmp     loc_1800087A2
0x1800086f2  lea     rax, [rsp+878h+var_838]
0x1800086f7  mov     [rsp+878h+var_848], 0; struct IUnknown *
0x180008700  mov     [rsp+878h+var_850], rax; __int64
0x180008705  lea     r8, [rsp+878h+ExistingFileName]; int
0x18000870a  mov     r9d, 0FFFFFh; int
0x180008710  mov     [rsp+878h+var_858], 0; struct IUnknown *
0x180008719  mov     rdx, rdi; int
0x18000871c  mov     dword ptr [rsp+878h+var_838], 0
0x180008724  mov     ecx, 2; int
0x180008729  call    MergeEtlExWithErrorContext
0x18000872e  mov     ebx, eax
0x180008730  test    eax, eax
0x180008732  jns     short loc_18000873E
0x180008734  mov     edx, 0DEh
0x180008739  jmp     loc_1800086B4
0x18000873e  mov     r8d, 1; dwFlags
0x180008744  lea     rdx, NewFileName; "\\data\\SystemData\\Etw\\EnterpriseDiag"...
0x18000874b  lea     rcx, [rsp+878h+ExistingFileName]; lpExistingFileName
0x180008750  call    cs:__imp_MoveFileExW
0x180008757  nop     dword ptr [rax+rax+00h]
0x18000875c  test    eax, eax
0x18000875e  jnz     short loc_180008780
0x180008760  mov     rcx, [rsp+878h]; this
0x180008768  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x18000876f  mov     edx, 0E1h; void *
0x180008774  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180008779  mov     ebx, eax
0x18000877b  jmp     loc_1800086CB
0x180008780  call    cs:__imp_GetProcessHeap
0x180008787  nop     dword ptr [rax+rax+00h]
0x18000878c  mov     r8, rdi; lpMem
0x18000878f  xor     edx, edx; dwFlags
0x180008791  mov     rcx, rax; hHeap
0x180008794  call    cs:__imp_HeapFree
0x18000879b  nop     dword ptr [rax+rax+00h]
0x1800087a0  xor     eax, eax
0x1800087a2  mov     rcx, [rsp+878h+var_18]
0x1800087aa  xor     rcx, rsp; StackCookie
0x1800087ad  call    __security_check_cookie
0x1800087b2  mov     rbx, [rsp+878h+arg_0]
0x1800087ba  add     rsp, 870h
0x1800087c1  pop     rdi
0x1800087c2  retn
```
