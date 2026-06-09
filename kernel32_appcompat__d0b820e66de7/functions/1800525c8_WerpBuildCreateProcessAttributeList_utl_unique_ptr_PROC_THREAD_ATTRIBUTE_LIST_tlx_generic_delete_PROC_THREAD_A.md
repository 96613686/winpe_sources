# WerpBuildCreateProcessAttributeList(utl::unique_ptr<_PROC_THREAD_ATTRIBUTE_LIST,tlx::generic_delete<_PROC_THREAD_ATTRIBUTE_LIST,virtualfree_release>> *,void * *,ulong *,void * *,ulong,ulong *,ushort *)

- ea: `0x1800525c8`
- end: `0x1800529c7`
- name: `?WerpBuildCreateProcessAttributeList@@YAJPEAV?$unique_ptr@U_PROC_THREAD_ATTRIBUTE_LIST@@U?$generic_delete@U_PROC_THREAD_ATTRIBUTE_LIST@@Uvirtualfree_release@@@tlx@@@utl@@PEAPEAXPEAK1K2PEAG@Z`
- size: `1023`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18005216c`

## callees

- `0x1800525c8`
- `0x180052b0c`
- `0x180052b38`

## import_xrefs

- `ntdll!DbgPrintEx` at `0x18005274e`
- `ntdll!DbgPrintEx` at `0x180052794`
- `ntdll!DbgPrintEx` at `0x180052958`
- `ntdll!DbgPrintEx` at `0x18005274e`
- `ntdll!DbgPrintEx` at `0x180052794`
- `ntdll!DbgPrintEx` at `0x180052958`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x180052691`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x180052708`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x180052691`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x180052708`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1800527d4`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x180052844`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1800528a8`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x180052912`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1800527d4`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x180052844`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1800528a8`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x180052912`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x180052971`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x180052971`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18005260e`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18005299f`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18005260e`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18005299f`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1800526e6`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1800526e6`

## string_xrefs

- `0x1800527f9`: `WER/ReportFault/%u:%u: ERROR UpdateProcThreadAttribute/EXTENDED_FLAGS failed: %u.\n`
- `0x1800526bd`: `WER/ReportFault/%u:%u: ERROR InitializeProcThreadAttributeList failed: %u.\n`
- `0x180052732`: `WER/ReportFault/%u:%u: ERROR InitializeProcThreadAttributeList failed: %u.\n`
- `0x180052869`: `WER/ReportFault/%u:%u: ERROR UpdateProcThreadAttribute/HANDLE_LIST failed: %u.\n`
- `0x180052937`: `WER/ReportFault/%u:%u: ERROR UpdateProcThreadAttribute/MACHINE_TYPE failed: %u.\n`
- `0x1800528cd`: `WER/ReportFault/%u:%u: ERROR UpdateProcThreadAttribute/CHILD_PROCESS failed: %u.\n`

## pseudocode

```c
__int64 __fastcall WerpBuildCreateProcessAttributeList(
        void **a1,
        __int64 a2,
        _DWORD *a3,
        void *a4,
        unsigned int a5,
        PVOID lpValue,
        PVOID a7)
{
  void *v9; // rcx
  struct _PROC_THREAD_ATTRIBUTE_LIST *v11; // rbx
  int v12; // eax
  int v13; // r8d
  int v14; // edx
  _DWORD *v15; // rsi
  int v16; // ecx
  _WORD *v17; // rdi
  DWORD v18; // r14d
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // r8
  __int64 v22; // r9
  unsigned int v23; // eax
  unsigned int v24; // eax
  int v25; // edx
  const CHAR *v26; // r8
  unsigned int v27; // edi
  struct _PROC_THREAD_ATTRIBUTE_LIST *v28; // rax
  __int64 v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // r8
  unsigned int LastError; // eax
  int v33; // edx
  int v34; // r14d
  __int64 v35; // rdx
  __int64 v36; // rcx
  __int64 v37; // r8
  unsigned int v38; // eax
  unsigned int v39; // eax
  int v40; // edx
  const CHAR *v41; // r8
  __int64 v42; // rdx
  __int64 v43; // rcx
  __int64 v44; // r8
  unsigned int v45; // eax
  int v46; // edx
  __int64 v47; // rdx
  __int64 v48; // rcx
  __int64 v49; // r8
  unsigned int v50; // eax
  int v51; // edx
  __int64 v52; // rdx
  __int64 v53; // rcx
  __int64 v54; // r8
  unsigned int v55; // eax
  int v56; // edx
  void *v57; // rcx
  int cbSize; // [rsp+20h] [rbp-48h]
  SIZE_T cbSizea; // [rsp+20h] [rbp-48h]
  int lpPreviousValue; // [rsp+28h] [rbp-40h]
  PVOID lpPreviousValuea; // [rsp+28h] [rbp-40h]
  ULONG_PTR Size; // [rsp+70h] [rbp+8h] BYREF
  __int64 v64; // [rsp+78h] [rbp+10h]

  v64 = a2;
  v9 = *a1;
  Size = 0;
  LODWORD(v64) = 0;
  v11 = 0;
  *a1 = 0;
  if ( v9 )
    VirtualFree(v9, 0, 0x8000u);
  v12 = 1;
  if ( !a3 || (v13 = 1, !*a3) )
    v13 = 0;
  if ( !a4 || (v14 = 1, !a5) )
    v14 = 0;
  v15 = lpValue;
  if ( !lpValue || (v16 = 1, !*(_DWORD *)lpValue) )
    v16 = 0;
  v17 = a7;
  if ( !a7 || !*(_WORD *)a7 )
    v12 = 0;
  v18 = v13 + v14 + v16 + v12;
  if ( !v18 )
  {
    v34 = 0;
    goto LABEL_26;
  }
  if ( InitializeProcThreadAttributeList(0, v18, 0, &Size)
    || (unsigned int)((__int64 (*)(void))WerpGetLastError)() == 122 )
  {
    v28 = (struct _PROC_THREAD_ATTRIBUTE_LIST *)VirtualAlloc(0, Size, 0x1000u, 4u);
    v11 = v28;
    if ( !v28 )
    {
      v27 = -2147024882;
      v26 = "WER/ReportFault/%u:%u: ERROR Failed to allocate attribute list: HRESULT %08X.\n";
      lpPreviousValue = -2147024882;
      cbSize = 421;
      goto LABEL_24;
    }
    if ( !InitializeProcThreadAttributeList(v28, v18, 0, &Size) )
    {
      LastError = WerpGetLastError(v30, v29, v31, 0);
      v27 = ERROR_HR_FROM_WIN32(LastError);
      DbgPrintEx(
        0x96u,
        0,
        "WER/ReportFault/%u:%u: ERROR InitializeProcThreadAttributeList failed: %u.\n",
        NtCurrentTeb()->ClientId.UniqueProcess,
        434,
        v33);
      v34 = v64;
      goto LABEL_43;
    }
    v34 = 1;
LABEL_26:
    if ( a3 && *a3 && !UpdateProcThreadAttribute(v11, 0, 0x60001u, a3, 4u, 0, 0) )
    {
      v38 = WerpGetLastError(v36, v35, v37, 0);
      v39 = ERROR_HR_FROM_WIN32(v38);
      LODWORD(lpPreviousValuea) = v40;
      v41 = "WER/ReportFault/%u:%u: ERROR UpdateProcThreadAttribute/EXTENDED_FLAGS failed: %u.\n";
      LODWORD(cbSizea) = 474;
    }
    else if ( a4 && a5 && !UpdateProcThreadAttribute(v11, 0, 0x20002u, a4, 8LL * a5, 0, 0) )
    {
      v45 = WerpGetLastError(v43, v42, v44, 0);
      v39 = ERROR_HR_FROM_WIN32(v45);
      LODWORD(lpPreviousValuea) = v46;
      v41 = "WER/ReportFault/%u:%u: ERROR UpdateProcThreadAttribute/HANDLE_LIST failed: %u.\n";
      LODWORD(cbSizea) = 493;
    }
    else if ( v15 && *v15 && !UpdateProcThreadAttribute(v11, 0, 0x2000Eu, v15, 4u, 0, 0) )
    {
      v50 = WerpGetLastError(v48, v47, v49, 0);
      v39 = ERROR_HR_FROM_WIN32(v50);
      LODWORD(lpPreviousValuea) = v51;
      v41 = "WER/ReportFault/%u:%u: ERROR UpdateProcThreadAttribute/CHILD_PROCESS failed: %u.\n";
      LODWORD(cbSizea) = 512;
    }
    else
    {
      if ( !v17 || !*v17 || UpdateProcThreadAttribute(v11, 0, 0x20019u, v17, 2u, 0, 0) )
      {
        v57 = *a1;
        *a1 = v11;
        v27 = v11 == 0;
        if ( !v57 )
          return v27;
LABEL_47:
        VirtualFree(v57, 0, 0x8000u);
        return v27;
      }
      v55 = WerpGetLastError(v53, v52, v54, 0);
      v39 = ERROR_HR_FROM_WIN32(v55);
      LODWORD(lpPreviousValuea) = v56;
      v41 = "WER/ReportFault/%u:%u: ERROR UpdateProcThreadAttribute/MACHINE_TYPE failed: %u.\n";
      LODWORD(cbSizea) = 532;
    }
    v27 = v39;
    DbgPrintEx(0x96u, 0, v41, NtCurrentTeb()->ClientId.UniqueProcess, cbSizea, lpPreviousValuea);
    if ( !v11 )
      return v27;
LABEL_43:
    if ( v34 )
      DeleteProcThreadAttributeList(v11);
    v57 = v11;
    goto LABEL_47;
  }
  v23 = WerpGetLastError(v20, v19, v21, v22);
  v24 = ERROR_HR_FROM_WIN32(v23);
  lpPreviousValue = v25;
  v26 = "WER/ReportFault/%u:%u: ERROR InitializeProcThreadAttributeList failed: %u.\n";
  v27 = v24;
  cbSize = 408;
LABEL_24:
  DbgPrintEx(0x96u, 0, v26, NtCurrentTeb()->ClientId.UniqueProcess, cbSize, lpPreviousValue);
  return v27;
}

```

## disassembly

```asm
0x1800525c8  mov     rax, rsp
0x1800525cb  mov     [rax+18h], rbx
0x1800525cf  mov     [rax+20h], rbp
0x1800525d3  mov     [rax+10h], rdx
0x1800525d7  push    rsi
0x1800525d8  push    rdi
0x1800525d9  push    r13
0x1800525db  push    r14
0x1800525dd  push    r15
0x1800525df  sub     rsp, 40h
0x1800525e3  mov     r15, rcx
0x1800525e6  mov     r13, r9
0x1800525e9  mov     rcx, [rcx]; lpAddress
0x1800525ec  xor     r9d, r9d
0x1800525ef  mov     [rax+8], r9
0x1800525f3  mov     rbp, r8
0x1800525f6  mov     dword ptr [rsp+68h+arg_8], r9d
0x1800525fb  mov     ebx, r9d
0x1800525fe  mov     [r15], r9
0x180052601  test    rcx, rcx
0x180052604  jz      short loc_18005261D
0x180052606  xor     edx, edx; dwSize
0x180052608  mov     r8d, 8000h; dwFreeType
0x18005260e  call    cs:__imp_VirtualFree
0x180052615  nop     dword ptr [rax+rax+00h]
0x18005261a  xor     r9d, r9d
0x18005261d  mov     eax, 1
0x180052622  test    rbp, rbp
0x180052625  jz      short loc_180052630
0x180052627  mov     r8d, eax
0x18005262a  cmp     [rbp+0], r9d
0x18005262e  jnz     short loc_180052633
0x180052630  mov     r8d, r9d
0x180052633  test    r13, r13
0x180052636  jz      short loc_180052644
0x180052638  mov     edx, eax
0x18005263a  cmp     [rsp+68h+arg_20], r9d
0x180052642  jnz     short loc_180052647
0x180052644  mov     edx, r9d
0x180052647  mov     rsi, [rsp+68h+lpValue]
0x18005264f  test    rsi, rsi
0x180052652  jz      short loc_18005265B
0x180052654  mov     ecx, eax
0x180052656  cmp     [rsi], r9d
0x180052659  jnz     short loc_18005265E
0x18005265b  mov     ecx, r9d
0x18005265e  mov     rdi, [rsp+68h+arg_30]
0x180052666  test    rdi, rdi
0x180052669  jz      short loc_180052671
0x18005266b  cmp     [rdi], r9w
0x18005266f  jnz     short loc_180052674
0x180052671  mov     eax, r9d
0x180052674  lea     r14d, [rcx+rax]
0x180052678  add     r14d, edx
0x18005267b  add     r14d, r8d
0x18005267e  jz      loc_1800527A5
0x180052684  lea     r9, [rsp+68h+Size]; lpSize
0x180052689  xor     r8d, r8d; dwFlags
0x18005268c  mov     edx, r14d; dwAttributeCount
0x18005268f  xor     ecx, ecx; lpAttributeList
0x180052691  call    cs:__imp_InitializeProcThreadAttributeList
0x180052698  nop     dword ptr [rax+rax+00h]
0x18005269d  test    eax, eax
0x18005269f  jnz     short loc_1800526D3
0x1800526a1  call    WerpGetLastError
0x1800526a6  cmp     eax, 7Ah ; 'z'
0x1800526a9  jz      short loc_1800526D3
0x1800526ab  call    WerpGetLastError
0x1800526b0  mov     ecx, eax; unsigned int
0x1800526b2  mov     edx, eax
0x1800526b4  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800526b9  mov     dword ptr [rsp+68h+lpPreviousValue], edx
0x1800526bd  lea     r8, aWerReportfault_0; "WER/ReportFault/%u:%u: ERROR Initialize"...
0x1800526c4  mov     edi, eax
0x1800526c6  mov     dword ptr [rsp+68h+cbSize], 198h
0x1800526ce  jmp     loc_180052784
0x1800526d3  mov     rdx, [rsp+68h+Size]; dwSize
0x1800526d8  mov     r9d, 4; flProtect
0x1800526de  mov     r8d, 1000h; flAllocationType
0x1800526e4  xor     ecx, ecx; lpAddress
0x1800526e6  call    cs:__imp_VirtualAlloc
0x1800526ed  nop     dword ptr [rax+rax+00h]
0x1800526f2  mov     rbx, rax
0x1800526f5  test    rax, rax
0x1800526f8  jz      short loc_18005276C
0x1800526fa  lea     r9, [rsp+68h+Size]; lpSize
0x1800526ff  xor     r8d, r8d; dwFlags
0x180052702  mov     edx, r14d; dwAttributeCount
0x180052705  mov     rcx, rax; lpAttributeList
0x180052708  call    cs:__imp_InitializeProcThreadAttributeList
0x18005270f  nop     dword ptr [rax+rax+00h]
0x180052714  xor     r9d, r9d
0x180052717  test    eax, eax
0x180052719  jnz     short loc_180052764
0x18005271b  call    WerpGetLastError
0x180052720  mov     ecx, eax; unsigned int
0x180052722  mov     edx, eax
0x180052724  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180052729  mov     r9, gs:40h
0x180052732  lea     r8, aWerReportfault_0; "WER/ReportFault/%u:%u: ERROR Initialize"...
0x180052739  mov     dword ptr [rsp+68h+lpPreviousValue], edx
0x18005273d  mov     ecx, 96h; ComponentId
0x180052742  xor     edx, edx; Level
0x180052744  mov     dword ptr [rsp+68h+cbSize], 1B2h
0x18005274c  mov     edi, eax
0x18005274e  call    cs:__imp_DbgPrintEx
0x180052755  nop     dword ptr [rax+rax+00h]
0x18005275a  mov     r14d, dword ptr [rsp+68h+arg_8]
0x18005275f  jmp     loc_180052969
0x180052764  mov     r14d, 1
0x18005276a  jmp     short loc_1800527A8
0x18005276c  mov     edi, 8007000Eh
0x180052771  lea     r8, aWerReportfault_7; "WER/ReportFault/%u:%u: ERROR Failed to "...
0x180052778  mov     dword ptr [rsp+68h+lpPreviousValue], edi
0x18005277c  mov     dword ptr [rsp+68h+cbSize], 1A5h
0x180052784  mov     r9, gs:40h
0x18005278d  xor     edx, edx; Level
0x18005278f  mov     ecx, 96h; ComponentId
0x180052794  call    cs:__imp_DbgPrintEx
0x18005279b  nop     dword ptr [rax+rax+00h]
0x1800527a0  jmp     loc_1800529AB
0x1800527a5  mov     r14d, ebx
0x1800527a8  test    rbp, rbp
0x1800527ab  jz      short loc_18005280D
0x1800527ad  cmp     [rbp+0], r9d
0x1800527b1  jz      short loc_18005280D
0x1800527b3  mov     [rsp+68h+lpReturnSize], r9; lpReturnSize
0x1800527b8  xor     edx, edx; dwFlags
0x1800527ba  mov     [rsp+68h+lpPreviousValue], r9; lpPreviousValue
0x1800527bf  mov     r8d, 60001h; Attribute
0x1800527c5  mov     r9, rbp; lpValue
0x1800527c8  mov     [rsp+68h+cbSize], 4; cbSize
0x1800527d1  mov     rcx, rbx; lpAttributeList
0x1800527d4  call    cs:__imp_UpdateProcThreadAttribute
0x1800527db  nop     dword ptr [rax+rax+00h]
0x1800527e0  xor     r9d, r9d
0x1800527e3  test    eax, eax
0x1800527e5  jnz     short loc_18005280D
0x1800527e7  call    WerpGetLastError
0x1800527ec  mov     ecx, eax; unsigned int
0x1800527ee  mov     edx, eax
0x1800527f0  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800527f5  mov     dword ptr [rsp+68h+lpPreviousValue], edx
0x1800527f9  lea     r8, aWerReportfault_18; "WER/ReportFault/%u:%u: ERROR UpdateProc"...
0x180052800  mov     dword ptr [rsp+68h+cbSize], 1DAh
0x180052808  jmp     loc_180052946
0x18005280d  test    r13, r13
0x180052810  jz      short loc_18005287D
0x180052812  cmp     [rsp+68h+arg_20], r9d
0x18005281a  jz      short loc_18005287D
0x18005281c  mov     eax, [rsp+68h+arg_20]
0x180052823  xor     edx, edx; dwFlags
0x180052825  mov     [rsp+68h+lpReturnSize], r9; lpReturnSize
0x18005282a  mov     r8d, 20002h; Attribute
0x180052830  mov     [rsp+68h+lpPreviousValue], r9; lpPreviousValue
0x180052835  mov     rcx, rbx; lpAttributeList
0x180052838  shl     rax, 3
0x18005283c  mov     r9, r13; lpValue
0x18005283f  mov     [rsp+68h+cbSize], rax; cbSize
0x180052844  call    cs:__imp_UpdateProcThreadAttribute
0x18005284b  nop     dword ptr [rax+rax+00h]
0x180052850  xor     r9d, r9d
0x180052853  test    eax, eax
0x180052855  jnz     short loc_18005287D
0x180052857  call    WerpGetLastError
0x18005285c  mov     ecx, eax; unsigned int
0x18005285e  mov     edx, eax
0x180052860  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180052865  mov     dword ptr [rsp+68h+lpPreviousValue], edx
0x180052869  lea     r8, aWerReportfault_1; "WER/ReportFault/%u:%u: ERROR UpdateProc"...
0x180052870  mov     dword ptr [rsp+68h+cbSize], 1EDh
0x180052878  jmp     loc_180052946
0x18005287d  test    rsi, rsi
0x180052880  jz      short loc_1800528DE
0x180052882  cmp     [rsi], r9d
0x180052885  jz      short loc_1800528DE
0x180052887  mov     [rsp+68h+lpReturnSize], r9; lpReturnSize
0x18005288c  xor     edx, edx; dwFlags
0x18005288e  mov     [rsp+68h+lpPreviousValue], r9; lpPreviousValue
0x180052893  mov     r8d, 2000Eh; Attribute
0x180052899  mov     r9, rsi; lpValue
0x18005289c  mov     [rsp+68h+cbSize], 4; cbSize
0x1800528a5  mov     rcx, rbx; lpAttributeList
0x1800528a8  call    cs:__imp_UpdateProcThreadAttribute
0x1800528af  nop     dword ptr [rax+rax+00h]
0x1800528b4  xor     r9d, r9d
0x1800528b7  test    eax, eax
0x1800528b9  jnz     short loc_1800528DE
0x1800528bb  call    WerpGetLastError
0x1800528c0  mov     ecx, eax; unsigned int
0x1800528c2  mov     edx, eax
0x1800528c4  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800528c9  mov     dword ptr [rsp+68h+lpPreviousValue], edx
0x1800528cd  lea     r8, aWerReportfault_3; "WER/ReportFault/%u:%u: ERROR UpdateProc"...
0x1800528d4  mov     dword ptr [rsp+68h+cbSize], 200h
0x1800528dc  jmp     short loc_180052946
0x1800528de  test    rdi, rdi
0x1800528e1  jz      loc_180052982
0x1800528e7  cmp     [rdi], r9w
0x1800528eb  jz      loc_180052982
0x1800528f1  mov     [rsp+68h+lpReturnSize], r9; lpReturnSize
0x1800528f6  xor     edx, edx; dwFlags
0x1800528f8  mov     [rsp+68h+lpPreviousValue], r9; lpPreviousValue
0x1800528fd  mov     r8d, 20019h; Attribute
0x180052903  mov     r9, rdi; lpValue
0x180052906  mov     [rsp+68h+cbSize], 2; cbSize
0x18005290f  mov     rcx, rbx; lpAttributeList
0x180052912  call    cs:__imp_UpdateProcThreadAttribute
0x180052919  nop     dword ptr [rax+rax+00h]
0x18005291e  xor     r9d, r9d
0x180052921  test    eax, eax
0x180052923  jnz     short loc_180052982
0x180052925  call    WerpGetLastError
0x18005292a  mov     ecx, eax; unsigned int
0x18005292c  mov     edx, eax
0x18005292e  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180052933  mov     dword ptr [rsp+68h+lpPreviousValue], edx
0x180052937  lea     r8, aWerReportfault_4; "WER/ReportFault/%u:%u: ERROR UpdateProc"...
0x18005293e  mov     dword ptr [rsp+68h+cbSize], 214h
0x180052946  mov     r9, gs:40h
0x18005294f  xor     edx, edx; Level
0x180052951  mov     ecx, 96h; ComponentId
0x180052956  mov     edi, eax
0x180052958  call    cs:__imp_DbgPrintEx
0x18005295f  nop     dword ptr [rax+rax+00h]
0x180052964  test    rbx, rbx
0x180052967  jz      short loc_1800529AB
0x180052969  test    r14d, r14d
0x18005296c  jz      short loc_18005297D
0x18005296e  mov     rcx, rbx; lpAttributeList
0x180052971  call    cs:__imp_DeleteProcThreadAttributeList
0x180052978  nop     dword ptr [rax+rax+00h]
0x18005297d  mov     rcx, rbx
0x180052980  jmp     short loc_180052997
0x180052982  mov     rcx, [r15]; lpAddress
0x180052985  test    rbx, rbx
0x180052988  mov     edi, r9d
0x18005298b  mov     [r15], rbx
0x18005298e  setz    dil
0x180052992  test    rcx, rcx
0x180052995  jz      short loc_1800529AB
0x180052997  mov     r8d, 8000h; dwFreeType
0x18005299d  xor     edx, edx; dwSize
0x18005299f  call    cs:__imp_VirtualFree
0x1800529a6  nop     dword ptr [rax+rax+00h]
0x1800529ab  lea     r11, [rsp+68h+var_28]
0x1800529b0  mov     eax, edi
0x1800529b2  mov     rbx, [r11+40h]
0x1800529b6  mov     rbp, [r11+48h]
0x1800529ba  mov     rsp, r11
0x1800529bd  pop     r15
0x1800529bf  pop     r14
0x1800529c1  pop     r13
0x1800529c3  pop     rdi
0x1800529c4  pop     rsi
0x1800529c5  retn
```
