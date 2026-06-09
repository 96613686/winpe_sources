# WerpBuildCreateProcessAttributeList(utl::unique_ptr<_PROC_THREAD_ATTRIBUTE_LIST,tlx::generic_delete<_PROC_THREAD_ATTRIBUTE_LIST,virtualfree_release>> *,void * *,ulong *,void * *,ulong,ulong *,ushort *)

- ea: `0x18004e8e0`
- end: `0x18004ec8c`
- name: `?WerpBuildCreateProcessAttributeList@@YAJPEAV?$unique_ptr@U_PROC_THREAD_ATTRIBUTE_LIST@@U?$generic_delete@U_PROC_THREAD_ATTRIBUTE_LIST@@Uvirtualfree_release@@@tlx@@@utl@@PEAPEAXPEAK1K2PEAG@Z`
- size: `940`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18004e470`

## callees

- `0x18004e8e0`
- `0x18004ed20`
- `0x18004ed48`

## import_xrefs

- `ntdll!DbgPrintEx` at `0x18004ea4e`
- `ntdll!DbgPrintEx` at `0x18004ea8e`
- `ntdll!DbgPrintEx` at `0x18004ec30`
- `ntdll!DbgPrintEx` at `0x18004ea4e`
- `ntdll!DbgPrintEx` at `0x18004ea8e`
- `ntdll!DbgPrintEx` at `0x18004ec30`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x18004e9a3`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x18004ea0e`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x18004e9a3`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x18004ea0e`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18004eac8`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18004eb32`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18004eb90`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18004ebf0`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18004eac8`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18004eb32`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18004eb90`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18004ebf0`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x18004ec43`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x18004ec43`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18004e926`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18004ec6b`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18004e926`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18004ec6b`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18004e9f2`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18004e9f2`

## string_xrefs

- `0x18004eae7`: `WER/ReportFault/%u:%u: ERROR UpdateProcThreadAttribute/EXTENDED_FLAGS failed: %u.\n`
- `0x18004e9c9`: `WER/ReportFault/%u:%u: ERROR InitializeProcThreadAttributeList failed: %u.\n`
- `0x18004ea32`: `WER/ReportFault/%u:%u: ERROR InitializeProcThreadAttributeList failed: %u.\n`
- `0x18004ebaf`: `WER/ReportFault/%u:%u: ERROR UpdateProcThreadAttribute/CHILD_PROCESS failed: %u.\n`
- `0x18004eb51`: `WER/ReportFault/%u:%u: ERROR UpdateProcThreadAttribute/HANDLE_LIST failed: %u.\n`
- `0x18004ec0f`: `WER/ReportFault/%u:%u: ERROR UpdateProcThreadAttribute/MACHINE_TYPE failed: %u.\n`

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
0x18004e8e0  mov     rax, rsp
0x18004e8e3  mov     [rax+18h], rbx
0x18004e8e7  mov     [rax+20h], rbp
0x18004e8eb  mov     [rax+10h], rdx
0x18004e8ef  push    rsi
0x18004e8f0  push    rdi
0x18004e8f1  push    r13
0x18004e8f3  push    r14
0x18004e8f5  push    r15
0x18004e8f7  sub     rsp, 40h
0x18004e8fb  mov     r15, rcx
0x18004e8fe  mov     r13, r9
0x18004e901  mov     rcx, [rcx]; lpAddress
0x18004e904  xor     r9d, r9d
0x18004e907  mov     [rax+8], r9
0x18004e90b  mov     rbp, r8
0x18004e90e  mov     dword ptr [rsp+68h+arg_8], r9d
0x18004e913  mov     ebx, r9d
0x18004e916  mov     [r15], r9
0x18004e919  test    rcx, rcx
0x18004e91c  jz      short loc_18004E92F
0x18004e91e  xor     edx, edx; dwSize
0x18004e920  mov     r8d, 8000h; dwFreeType
0x18004e926  call    cs:__imp_VirtualFree
0x18004e92c  xor     r9d, r9d
0x18004e92f  mov     eax, 1
0x18004e934  test    rbp, rbp
0x18004e937  jz      short loc_18004E942
0x18004e939  mov     r8d, eax
0x18004e93c  cmp     [rbp+0], r9d
0x18004e940  jnz     short loc_18004E945
0x18004e942  mov     r8d, r9d
0x18004e945  test    r13, r13
0x18004e948  jz      short loc_18004E956
0x18004e94a  mov     edx, eax
0x18004e94c  cmp     [rsp+68h+arg_20], r9d
0x18004e954  jnz     short loc_18004E959
0x18004e956  mov     edx, r9d
0x18004e959  mov     rsi, [rsp+68h+lpValue]
0x18004e961  test    rsi, rsi
0x18004e964  jz      short loc_18004E96D
0x18004e966  mov     ecx, eax
0x18004e968  cmp     [rsi], r9d
0x18004e96b  jnz     short loc_18004E970
0x18004e96d  mov     ecx, r9d
0x18004e970  mov     rdi, [rsp+68h+arg_30]
0x18004e978  test    rdi, rdi
0x18004e97b  jz      short loc_18004E983
0x18004e97d  cmp     [rdi], r9w
0x18004e981  jnz     short loc_18004E986
0x18004e983  mov     eax, r9d
0x18004e986  lea     r14d, [rcx+rax]
0x18004e98a  add     r14d, edx
0x18004e98d  add     r14d, r8d
0x18004e990  jz      loc_18004EA99
0x18004e996  lea     r9, [rsp+68h+Size]; lpSize
0x18004e99b  xor     r8d, r8d; dwFlags
0x18004e99e  mov     edx, r14d; dwAttributeCount
0x18004e9a1  xor     ecx, ecx; lpAttributeList
0x18004e9a3  call    cs:__imp_InitializeProcThreadAttributeList
0x18004e9a9  test    eax, eax
0x18004e9ab  jnz     short loc_18004E9DF
0x18004e9ad  call    WerpGetLastError
0x18004e9b2  cmp     eax, 7Ah ; 'z'
0x18004e9b5  jz      short loc_18004E9DF
0x18004e9b7  call    WerpGetLastError
0x18004e9bc  mov     ecx, eax; unsigned int
0x18004e9be  mov     edx, eax
0x18004e9c0  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18004e9c5  mov     dword ptr [rsp+68h+lpPreviousValue], edx
0x18004e9c9  lea     r8, aWerReportfault_0; "WER/ReportFault/%u:%u: ERROR Initialize"...
0x18004e9d0  mov     edi, eax
0x18004e9d2  mov     dword ptr [rsp+68h+cbSize], 198h
0x18004e9da  jmp     loc_18004EA7E
0x18004e9df  mov     rdx, [rsp+68h+Size]; dwSize
0x18004e9e4  mov     r9d, 4; flProtect
0x18004e9ea  mov     r8d, 1000h; flAllocationType
0x18004e9f0  xor     ecx, ecx; lpAddress
0x18004e9f2  call    cs:__imp_VirtualAlloc
0x18004e9f8  mov     rbx, rax
0x18004e9fb  test    rax, rax
0x18004e9fe  jz      short loc_18004EA66
0x18004ea00  lea     r9, [rsp+68h+Size]; lpSize
0x18004ea05  xor     r8d, r8d; dwFlags
0x18004ea08  mov     edx, r14d; dwAttributeCount
0x18004ea0b  mov     rcx, rax; lpAttributeList
0x18004ea0e  call    cs:__imp_InitializeProcThreadAttributeList
0x18004ea14  xor     r9d, r9d
0x18004ea17  test    eax, eax
0x18004ea19  jnz     short loc_18004EA5E
0x18004ea1b  call    WerpGetLastError
0x18004ea20  mov     ecx, eax; unsigned int
0x18004ea22  mov     edx, eax
0x18004ea24  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18004ea29  mov     r9, gs:40h
0x18004ea32  lea     r8, aWerReportfault_0; "WER/ReportFault/%u:%u: ERROR Initialize"...
0x18004ea39  mov     dword ptr [rsp+68h+lpPreviousValue], edx
0x18004ea3d  mov     ecx, 96h; ComponentId
0x18004ea42  xor     edx, edx; Level
0x18004ea44  mov     dword ptr [rsp+68h+cbSize], 1B2h
0x18004ea4c  mov     edi, eax
0x18004ea4e  call    cs:__imp_DbgPrintEx
0x18004ea54  mov     r14d, dword ptr [rsp+68h+arg_8]
0x18004ea59  jmp     loc_18004EC3B
0x18004ea5e  mov     r14d, 1
0x18004ea64  jmp     short loc_18004EA9C
0x18004ea66  mov     edi, 8007000Eh
0x18004ea6b  lea     r8, aWerReportfault_7; "WER/ReportFault/%u:%u: ERROR Failed to "...
0x18004ea72  mov     dword ptr [rsp+68h+lpPreviousValue], edi
0x18004ea76  mov     dword ptr [rsp+68h+cbSize], 1A5h
0x18004ea7e  mov     r9, gs:40h
0x18004ea87  xor     edx, edx; Level
0x18004ea89  mov     ecx, 96h; ComponentId
0x18004ea8e  call    cs:__imp_DbgPrintEx
0x18004ea94  jmp     loc_18004EC71
0x18004ea99  mov     r14d, ebx
0x18004ea9c  test    rbp, rbp
0x18004ea9f  jz      short loc_18004EAFB
0x18004eaa1  cmp     [rbp+0], r9d
0x18004eaa5  jz      short loc_18004EAFB
0x18004eaa7  mov     [rsp+68h+lpReturnSize], r9; lpReturnSize
0x18004eaac  xor     edx, edx; dwFlags
0x18004eaae  mov     [rsp+68h+lpPreviousValue], r9; lpPreviousValue
0x18004eab3  mov     r8d, 60001h; Attribute
0x18004eab9  mov     r9, rbp; lpValue
0x18004eabc  mov     [rsp+68h+cbSize], 4; cbSize
0x18004eac5  mov     rcx, rbx; lpAttributeList
0x18004eac8  call    cs:__imp_UpdateProcThreadAttribute
0x18004eace  xor     r9d, r9d
0x18004ead1  test    eax, eax
0x18004ead3  jnz     short loc_18004EAFB
0x18004ead5  call    WerpGetLastError
0x18004eada  mov     ecx, eax; unsigned int
0x18004eadc  mov     edx, eax
0x18004eade  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18004eae3  mov     dword ptr [rsp+68h+lpPreviousValue], edx
0x18004eae7  lea     r8, aWerReportfault_18; "WER/ReportFault/%u:%u: ERROR UpdateProc"...
0x18004eaee  mov     dword ptr [rsp+68h+cbSize], 1DAh
0x18004eaf6  jmp     loc_18004EC1E
0x18004eafb  test    r13, r13
0x18004eafe  jz      short loc_18004EB65
0x18004eb00  cmp     [rsp+68h+arg_20], r9d
0x18004eb08  jz      short loc_18004EB65
0x18004eb0a  mov     eax, [rsp+68h+arg_20]
0x18004eb11  xor     edx, edx; dwFlags
0x18004eb13  mov     [rsp+68h+lpReturnSize], r9; lpReturnSize
0x18004eb18  mov     r8d, 20002h; Attribute
0x18004eb1e  mov     [rsp+68h+lpPreviousValue], r9; lpPreviousValue
0x18004eb23  mov     rcx, rbx; lpAttributeList
0x18004eb26  shl     rax, 3
0x18004eb2a  mov     r9, r13; lpValue
0x18004eb2d  mov     [rsp+68h+cbSize], rax; cbSize
0x18004eb32  call    cs:__imp_UpdateProcThreadAttribute
0x18004eb38  xor     r9d, r9d
0x18004eb3b  test    eax, eax
0x18004eb3d  jnz     short loc_18004EB65
0x18004eb3f  call    WerpGetLastError
0x18004eb44  mov     ecx, eax; unsigned int
0x18004eb46  mov     edx, eax
0x18004eb48  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18004eb4d  mov     dword ptr [rsp+68h+lpPreviousValue], edx
0x18004eb51  lea     r8, aWerReportfault_1; "WER/ReportFault/%u:%u: ERROR UpdateProc"...
0x18004eb58  mov     dword ptr [rsp+68h+cbSize], 1EDh
0x18004eb60  jmp     loc_18004EC1E
0x18004eb65  test    rsi, rsi
0x18004eb68  jz      short loc_18004EBC0
0x18004eb6a  cmp     [rsi], r9d
0x18004eb6d  jz      short loc_18004EBC0
0x18004eb6f  mov     [rsp+68h+lpReturnSize], r9; lpReturnSize
0x18004eb74  xor     edx, edx; dwFlags
0x18004eb76  mov     [rsp+68h+lpPreviousValue], r9; lpPreviousValue
0x18004eb7b  mov     r8d, 2000Eh; Attribute
0x18004eb81  mov     r9, rsi; lpValue
0x18004eb84  mov     [rsp+68h+cbSize], 4; cbSize
0x18004eb8d  mov     rcx, rbx; lpAttributeList
0x18004eb90  call    cs:__imp_UpdateProcThreadAttribute
0x18004eb96  xor     r9d, r9d
0x18004eb99  test    eax, eax
0x18004eb9b  jnz     short loc_18004EBC0
0x18004eb9d  call    WerpGetLastError
0x18004eba2  mov     ecx, eax; unsigned int
0x18004eba4  mov     edx, eax
0x18004eba6  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18004ebab  mov     dword ptr [rsp+68h+lpPreviousValue], edx
0x18004ebaf  lea     r8, aWerReportfault_3; "WER/ReportFault/%u:%u: ERROR UpdateProc"...
0x18004ebb6  mov     dword ptr [rsp+68h+cbSize], 200h
0x18004ebbe  jmp     short loc_18004EC1E
0x18004ebc0  test    rdi, rdi
0x18004ebc3  jz      loc_18004EC4E
0x18004ebc9  cmp     [rdi], r9w
0x18004ebcd  jz      short loc_18004EC4E
0x18004ebcf  mov     [rsp+68h+lpReturnSize], r9; lpReturnSize
0x18004ebd4  xor     edx, edx; dwFlags
0x18004ebd6  mov     [rsp+68h+lpPreviousValue], r9; lpPreviousValue
0x18004ebdb  mov     r8d, 20019h; Attribute
0x18004ebe1  mov     r9, rdi; lpValue
0x18004ebe4  mov     [rsp+68h+cbSize], 2; cbSize
0x18004ebed  mov     rcx, rbx; lpAttributeList
0x18004ebf0  call    cs:__imp_UpdateProcThreadAttribute
0x18004ebf6  xor     r9d, r9d
0x18004ebf9  test    eax, eax
0x18004ebfb  jnz     short loc_18004EC4E
0x18004ebfd  call    WerpGetLastError
0x18004ec02  mov     ecx, eax; unsigned int
0x18004ec04  mov     edx, eax
0x18004ec06  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18004ec0b  mov     dword ptr [rsp+68h+lpPreviousValue], edx
0x18004ec0f  lea     r8, aWerReportfault_4; "WER/ReportFault/%u:%u: ERROR UpdateProc"...
0x18004ec16  mov     dword ptr [rsp+68h+cbSize], 214h
0x18004ec1e  mov     r9, gs:40h
0x18004ec27  xor     edx, edx; Level
0x18004ec29  mov     ecx, 96h; ComponentId
0x18004ec2e  mov     edi, eax
0x18004ec30  call    cs:__imp_DbgPrintEx
0x18004ec36  test    rbx, rbx
0x18004ec39  jz      short loc_18004EC71
0x18004ec3b  test    r14d, r14d
0x18004ec3e  jz      short loc_18004EC49
0x18004ec40  mov     rcx, rbx; lpAttributeList
0x18004ec43  call    cs:__imp_DeleteProcThreadAttributeList
0x18004ec49  mov     rcx, rbx
0x18004ec4c  jmp     short loc_18004EC63
0x18004ec4e  mov     rcx, [r15]; lpAddress
0x18004ec51  test    rbx, rbx
0x18004ec54  mov     edi, r9d
0x18004ec57  mov     [r15], rbx
0x18004ec5a  setz    dil
0x18004ec5e  test    rcx, rcx
0x18004ec61  jz      short loc_18004EC71
0x18004ec63  mov     r8d, 8000h; dwFreeType
0x18004ec69  xor     edx, edx; dwSize
0x18004ec6b  call    cs:__imp_VirtualFree
0x18004ec71  lea     r11, [rsp+68h+var_28]
0x18004ec76  mov     eax, edi
0x18004ec78  mov     rbx, [r11+40h]
0x18004ec7c  mov     rbp, [r11+48h]
0x18004ec80  mov     rsp, r11
0x18004ec83  pop     r15
0x18004ec85  pop     r14
0x18004ec87  pop     r13
0x18004ec89  pop     rdi
0x18004ec8a  pop     rsi
0x18004ec8b  retn
```
