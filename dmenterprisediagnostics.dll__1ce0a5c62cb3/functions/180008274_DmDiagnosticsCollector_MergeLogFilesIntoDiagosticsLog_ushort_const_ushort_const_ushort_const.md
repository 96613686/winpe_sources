# DmDiagnosticsCollector::MergeLogFilesIntoDiagosticsLog(ushort const *,ushort const *,ushort const *)

- ea: `0x180008274`
- end: `0x1800083d6`
- name: `?MergeLogFilesIntoDiagosticsLog@DmDiagnosticsCollector@@SAJPEBG00@Z`
- size: `354`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800080f8`

## callees

- `0x1800017e0`
- `0x1800059f4`
- `0x180005a14`
- `0x180006a30`
- `0x180008274`
- `0x18000d024`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000830d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800083ad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000830d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800083ad`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800082a2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800082a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008293`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800082ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000839f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008293`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800082ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000839f`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180008375`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180008375`

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
0x180008274  mov     [rsp+arg_0], rbx
0x180008279  push    rdi
0x18000827a  sub     rsp, 870h
0x180008281  mov     rax, cs:__security_cookie
0x180008288  xor     rax, rsp
0x18000828b  mov     [rsp+878h+var_18], rax
0x180008293  call    cs:__imp_GetProcessHeap
0x180008299  xor     edx, edx; dwFlags
0x18000829b  mov     rcx, rax; hHeap
0x18000829e  lea     r8d, [rdx+10h]; dwBytes
0x1800082a2  call    cs:__imp_HeapAlloc
0x1800082a8  lea     r9, NewFileName; "\\data\\SystemData\\Etw\\EnterpriseDiag"...
0x1800082af  mov     edx, 401h; unsigned __int64
0x1800082b4  mov     rdi, rax
0x1800082b7  lea     r8, aSMerged; "%s.merged"
0x1800082be  lea     rax, aDataSystemdata_0; "\\data\\SystemData\\Etw\\DiagnosticsCir"...
0x1800082c5  lea     rcx, [rsp+878h+ExistingFileName]; unsigned __int16 *
0x1800082ca  mov     [rdi], rax
0x1800082cd  lea     rax, aDataSystemdata; "\\data\\SystemData\\Etw\\DiagnosticsCri"...
0x1800082d4  mov     [rdi+8], rax
0x1800082d8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800082dd  mov     ebx, eax
0x1800082df  test    eax, eax
0x1800082e1  jns     short loc_18000831A
0x1800082e3  mov     edx, 0DBh; void *
0x1800082e8  mov     rcx, [rsp+878h]; this
0x1800082f0  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1800082f7  mov     r9d, ebx; char *
0x1800082fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800082ff  call    cs:__imp_GetProcessHeap
0x180008305  mov     r8, rdi; lpMem
0x180008308  xor     edx, edx; dwFlags
0x18000830a  mov     rcx, rax; hHeap
0x18000830d  call    cs:__imp_HeapFree
0x180008313  mov     eax, ebx
0x180008315  jmp     loc_1800083B5
0x18000831a  lea     rax, [rsp+878h+var_838]
0x18000831f  mov     [rsp+878h+var_848], 0; struct IUnknown *
0x180008328  mov     [rsp+878h+var_850], rax; __int64
0x18000832d  lea     r8, [rsp+878h+ExistingFileName]; int
0x180008332  mov     r9d, 0FFFFFh; int
0x180008338  mov     [rsp+878h+var_858], 0; struct IUnknown *
0x180008341  mov     rdx, rdi; int
0x180008344  mov     dword ptr [rsp+878h+var_838], 0
0x18000834c  mov     ecx, 2; int
0x180008351  call    MergeEtlExWithErrorContext
0x180008356  mov     ebx, eax
0x180008358  test    eax, eax
0x18000835a  jns     short loc_180008363
0x18000835c  mov     edx, 0DEh
0x180008361  jmp     short loc_1800082E8
0x180008363  mov     r8d, 1; dwFlags
0x180008369  lea     rdx, NewFileName; "\\data\\SystemData\\Etw\\EnterpriseDiag"...
0x180008370  lea     rcx, [rsp+878h+ExistingFileName]; lpExistingFileName
0x180008375  call    cs:__imp_MoveFileExW
0x18000837b  test    eax, eax
0x18000837d  jnz     short loc_18000839F
0x18000837f  mov     rcx, [rsp+878h]; this
0x180008387  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x18000838e  mov     edx, 0E1h; void *
0x180008393  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180008398  mov     ebx, eax
0x18000839a  jmp     loc_1800082FF
0x18000839f  call    cs:__imp_GetProcessHeap
0x1800083a5  mov     r8, rdi; lpMem
0x1800083a8  xor     edx, edx; dwFlags
0x1800083aa  mov     rcx, rax; hHeap
0x1800083ad  call    cs:__imp_HeapFree
0x1800083b3  xor     eax, eax
0x1800083b5  mov     rcx, [rsp+878h+var_18]
0x1800083bd  xor     rcx, rsp; StackCookie
0x1800083c0  call    __security_check_cookie
0x1800083c5  mov     rbx, [rsp+878h+arg_0]
0x1800083cd  add     rsp, 870h
0x1800083d4  pop     rdi
0x1800083d5  retn
```
