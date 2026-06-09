# StartCrashVertical

- ea: `0x18004e470`
- end: `0x18004e8b0`
- name: `StartCrashVertical`
- size: `1088`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180046438`

## callees

- `0x18003b7e0`
- `0x18004e470`
- `0x18004e8b8`
- `0x18004e8e0`
- `0x18004ec94`
- `0x18004ed20`
- `0x18007a7dd`
- `0x18007a840`

## import_xrefs

- `ntdll!DbgPrintEx` at `0x18004e561`
- `ntdll!DbgPrintEx` at `0x18004e761`
- `ntdll!DbgPrintEx` at `0x18004e7b1`
- `ntdll!DbgPrintEx` at `0x18004e7f7`
- `ntdll!DbgPrintEx` at `0x18004e89e`
- `ntdll!DbgPrintEx` at `0x18004e561`
- `ntdll!DbgPrintEx` at `0x18004e761`
- `ntdll!DbgPrintEx` at `0x18004e7b1`
- `ntdll!DbgPrintEx` at `0x18004e7f7`
- `ntdll!DbgPrintEx` at `0x18004e89e`
- `ntdll!NtClose` at `0x18004e82c`
- `ntdll!NtClose` at `0x18004e82c`
- `ntdll!RtlGetCurrentTransaction` at `0x18004e599`
- `ntdll!RtlGetCurrentTransaction` at `0x18004e599`
- `ntdll!RtlSetCurrentTransaction` at `0x18004e5a4`
- `ntdll!RtlSetCurrentTransaction` at `0x18004e853`
- `ntdll!RtlSetCurrentTransaction` at `0x18004e5a4`
- `ntdll!RtlSetCurrentTransaction` at `0x18004e853`
- `api-ms-win-core-processthreads-l1-1-3!GetProcessInformation` at `0x18004e62f`
- `api-ms-win-core-processthreads-l1-1-3!GetProcessInformation` at `0x18004e62f`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18004e715`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18004e715`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18004e777`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18004e777`
- `api-ms-win-core-errorhandling-l1-1-3!SetThreadErrorMode` at `0x18004e593`
- `api-ms-win-core-errorhandling-l1-1-3!SetThreadErrorMode` at `0x18004e845`
- `api-ms-win-core-errorhandling-l1-1-3!SetThreadErrorMode` at `0x18004e593`
- `api-ms-win-core-errorhandling-l1-1-3!SetThreadErrorMode` at `0x18004e845`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18004e582`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18004e839`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18004e582`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18004e839`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x18004e60d`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x18004e60d`

## string_xrefs

- `0x18004e7dc`: `WER/ReportFault/%u:%u: ERROR CreateProcess/mode%u failed with Win32 error %u.\n`
- `0x18004e744`: `WER/ReportFault/%u:%u: WARNING CreateProcess/mode%u failed with Win32 error %u.\n`
- `0x18004e796`: `WER/ReportFault/%u:%u: WARNING CreateProcess/mode%u failed with Win32 error %u.\n`
- `0x18004e547`: `WER/ReportFault/%u:%u: ERROR Failed to get the paths for the crash vertical: HRESULT %08X.\n`
- `0x18004e887`: `WER/ReportFault/%u:%u: ERROR WerpBuildCreateProcessAttributeList failed, HRESULT %08X.\n`

## pseudocode

```c
__int64 __fastcall StartCrashVertical(void *a1, void *a2, unsigned int a3, HANDLE *a4)
{
  void *v4; // r15
  void *v7; // rdx
  int CrashVerticalPaths; // eax
  unsigned int LastError; // ebx
  int v10; // r12d
  __int64 CurrentTransaction; // r13
  unsigned int i; // edi
  int v13; // r14d
  __int16 v14; // cx
  __int16 v15; // ax
  int v16; // eax
  void *v17; // r15
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // r8
  __int64 v21; // r9
  BOOL bInheritHandles; // [rsp+20h] [rbp-E0h]
  unsigned int lpEnvironment; // [rsp+30h] [rbp-D0h]
  unsigned int lpStartupInfo; // [rsp+40h] [rbp-C0h]
  _WORD v26[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v27; // [rsp+54h] [rbp-ACh] BYREF
  int v28; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID lpAddress; // [rsp+60h] [rbp-A0h] BYREF
  DWORD OldMode; // [rsp+68h] [rbp-98h] BYREF
  int v31; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned int v32; // [rsp+70h] [rbp-90h]
  UINT uMode; // [rsp+74h] [rbp-8Ch]
  __int64 v34; // [rsp+78h] [rbp-88h] BYREF
  void *v35; // [rsp+80h] [rbp-80h]
  HANDLE *v36; // [rsp+88h] [rbp-78h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+90h] [rbp-70h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+B0h] [rbp-50h] BYREF
  LPVOID v39; // [rsp+118h] [rbp+18h]
  WCHAR CurrentDirectory[32]; // [rsp+120h] [rbp+20h] BYREF
  WCHAR ApplicationName[64]; // [rsp+160h] [rbp+60h] BYREF
  WCHAR CommandLine[128]; // [rsp+1E0h] [rbp+E0h] BYREF

  v32 = a3;
  v4 = a2;
  v35 = a2;
  v36 = a4;
  *(&StartupInfo.cb + 1) = 0;
  memset_0(&StartupInfo.lpReserved, 0, sizeof(struct _STARTUPINFOW));
  v31 = 2;
  *a4 = 0;
  OldMode = 0;
  v28 = 0;
  CurrentDirectory[0] = 0;
  ApplicationName[0] = 0;
  CommandLine[0] = 0;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  StartupInfo.cb = 112;
  StartupInfo.dwFlags = 1;
  StartupInfo.wShowWindow = 0;
  CrashVerticalPaths = GetCrashVerticalPaths(
                         (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                         v7,
                         a1,
                         ApplicationName,
                         bInheritHandles,
                         CommandLine,
                         lpEnvironment,
                         CurrentDirectory,
                         lpStartupInfo);
  LastError = CrashVerticalPaths;
  if ( CrashVerticalPaths < 0 )
  {
    DbgPrintEx(
      0x96u,
      0,
      "WER/ReportFault/%u:%u: ERROR Failed to get the paths for the crash vertical: HRESULT %08X.\n",
      NtCurrentTeb()->ClientId.UniqueProcess,
      621,
      CrashVerticalPaths);
    return LastError;
  }
  v10 = (unsigned int)WerpIsProtectedProcess((HANDLE)0xFFFFFFFFFFFFFFFFLL) != 0 ? 0x40000 : 0;
  uMode = SetErrorMode(1u);
  SetThreadErrorMode(1u, &OldMode);
  CurrentTransaction = RtlGetCurrentTransaction();
  RtlSetCurrentTransaction(0);
  for ( i = 0; ; ++i )
  {
    if ( i >= 3 )
      goto LABEL_34;
    if ( !i )
    {
      v28 = 4;
      goto LABEL_10;
    }
    if ( i != 1 )
    {
      v28 = 0;
LABEL_10:
      v13 = v10;
      goto LABEL_11;
    }
    v28 = 0;
    v13 = v10 | 0x1000000;
LABEL_11:
    v26[0] = 0;
    v27 = 0;
    if ( (unsigned int)IsWow64Process2(-1, v26, &v27) && (v34 = 0, (unsigned int)GetProcessInformation(-1, 9, &v34, 8)) )
    {
      v14 = v27;
      if ( (_WORD)v34 == v27 )
        v15 = 0;
      else
        v15 = v34;
      v26[0] = v15;
    }
    else
    {
      v15 = v26[0];
      v14 = v27;
    }
    if ( v14 != -21916 || v15 != -31132 )
      v26[0] = 0;
    lpAddress = 0;
    v16 = WerpBuildCreateProcessAttributeList(&lpAddress, 43620, &v28, v4, v32, &v31, v26);
    LastError = v16;
    if ( v16 < 0 )
    {
      DbgPrintEx(
        0x96u,
        0,
        "WER/ReportFault/%u:%u: ERROR WerpBuildCreateProcessAttributeList failed, HRESULT %08X.\n",
        NtCurrentTeb()->ClientId.UniqueProcess,
        703,
        v16);
      goto LABEL_39;
    }
    v17 = lpAddress;
    v39 = lpAddress;
    if ( CreateProcessW(
           ApplicationName,
           CommandLine,
           0,
           0,
           1,
           v13 | (lpAddress != 0 ? 0x80000 : 0),
           0,
           CurrentDirectory,
           &StartupInfo,
           &ProcessInformation) )
    {
      utl::unique_ptr<_PROC_THREAD_ATTRIBUTE_LIST,tlx::generic_delete<_PROC_THREAD_ATTRIBUTE_LIST,virtualfree_release>>::~unique_ptr<_PROC_THREAD_ATTRIBUTE_LIST,tlx::generic_delete<_PROC_THREAD_ATTRIBUTE_LIST,virtualfree_release>>(&lpAddress);
LABEL_34:
      *v36 = ProcessInformation.hProcess;
      NtClose(ProcessInformation.hThread);
      LastError = 0;
      goto LABEL_35;
    }
    LastError = WerpGetLastError(v19, v18, v20, v21);
    if ( i )
      break;
    if ( LastError != 1314 )
      goto LABEL_31;
    DbgPrintEx(
      0x96u,
      1u,
      "WER/ReportFault/%u:%u: WARNING CreateProcess/mode%u failed with Win32 error %u.\n",
      NtCurrentTeb()->ClientId.UniqueProcess,
      732,
      0,
      1314);
    if ( v17 )
      VirtualFree(v17, 0, 0x8000u);
LABEL_30:
    v4 = v35;
  }
  if ( i == 1 && LastError == 5 )
  {
    DbgPrintEx(
      0x96u,
      1u,
      "WER/ReportFault/%u:%u: WARNING CreateProcess/mode%u failed with Win32 error %u.\n",
      NtCurrentTeb()->ClientId.UniqueProcess,
      738,
      1,
      5);
    utl::unique_ptr<_PROC_THREAD_ATTRIBUTE_LIST,tlx::generic_delete<_PROC_THREAD_ATTRIBUTE_LIST,virtualfree_release>>::~unique_ptr<_PROC_THREAD_ATTRIBUTE_LIST,tlx::generic_delete<_PROC_THREAD_ATTRIBUTE_LIST,virtualfree_release>>(&lpAddress);
    goto LABEL_30;
  }
LABEL_31:
  DbgPrintEx(
    0x96u,
    0,
    "WER/ReportFault/%u:%u: ERROR CreateProcess/mode%u failed with Win32 error %u.\n",
    NtCurrentTeb()->ClientId.UniqueProcess,
    743,
    i,
    LastError);
  if ( (int)LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
LABEL_39:
  utl::unique_ptr<_PROC_THREAD_ATTRIBUTE_LIST,tlx::generic_delete<_PROC_THREAD_ATTRIBUTE_LIST,virtualfree_release>>::~unique_ptr<_PROC_THREAD_ATTRIBUTE_LIST,tlx::generic_delete<_PROC_THREAD_ATTRIBUTE_LIST,virtualfree_release>>(&lpAddress);
LABEL_35:
  SetErrorMode(uMode);
  SetThreadErrorMode(OldMode, 0);
  if ( CurrentTransaction )
    RtlSetCurrentTransaction(CurrentTransaction);
  return LastError;
}

```

## disassembly

```asm
0x18004e470  push    rbp
0x18004e472  push    rbx
0x18004e473  push    rsi
0x18004e474  push    rdi
0x18004e475  push    r12
0x18004e477  push    r13
0x18004e479  push    r14
0x18004e47b  push    r15
0x18004e47d  lea     rbp, [rsp-1F8h]
0x18004e485  sub     rsp, 2F8h
0x18004e48c  mov     rax, cs:__security_cookie
0x18004e493  xor     rax, rsp
0x18004e496  mov     [rbp+230h+var_50], rax
0x18004e49d  xor     eax, eax
0x18004e49f  mov     [rsp+330h+var_2C0], r8d
0x18004e4a4  mov     r15, rdx
0x18004e4a7  mov     [rbp+230h+var_2B0], rdx
0x18004e4ab  mov     rbx, rcx
0x18004e4ae  mov     [rbp+230h+var_2A8], r9
0x18004e4b2  xor     edx, edx; Val
0x18004e4b4  mov     dword ptr [rbp+230h+StartupInfo+4], eax
0x18004e4b7  lea     r8d, [rax+68h]; Size
0x18004e4bb  mov     rdi, r9
0x18004e4be  lea     rcx, [rbp+230h+StartupInfo.lpReserved]; void *
0x18004e4c2  call    memset_0
0x18004e4c7  xor     r14d, r14d
0x18004e4ca  mov     [rsp+330h+var_2C4], 2
0x18004e4d2  xor     eax, eax
0x18004e4d4  mov     [rdi], r14
0x18004e4d7  mov     qword ptr [rbp+230h+ProcessInformation.dwProcessId], rax
0x18004e4db  lea     r9, [rbp+230h+ApplicationName]; wchar_t *
0x18004e4df  xorps   xmm0, xmm0
0x18004e4e2  mov     [rsp+330h+OldMode], r14d
0x18004e4e7  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18004e4eb  mov     [rsp+330h+var_2D8], r14d
0x18004e4f0  lea     edi, [rax+1]
0x18004e4f3  mov     [rbp+230h+CurrentDirectory], r14w
0x18004e4f8  lea     rax, [rbp+230h+CurrentDirectory]
0x18004e4fc  mov     [rbp+230h+ApplicationName], r14w
0x18004e501  mov     [rsp+330h+lpCurrentDirectory], rax; wchar_t *
0x18004e506  mov     r8, rbx; void *
0x18004e509  lea     rax, [rbp+230h+CommandLine]
0x18004e510  mov     [rbp+230h+CommandLine], r14w
0x18004e518  mov     rcx, rsi; Process
0x18004e51b  mov     qword ptr [rsp+330h+dwCreationFlags], rax; wchar_t *
0x18004e520  movups  xmmword ptr [rbp+230h+ProcessInformation.hProcess], xmm0
0x18004e524  mov     [rbp+230h+StartupInfo.cb], 70h ; 'p'
0x18004e52b  mov     [rbp+230h+StartupInfo.dwFlags], edi
0x18004e52e  mov     [rbp+230h+StartupInfo.wShowWindow], r14w
0x18004e533  call    ?GetCrashVerticalPaths@@YAJPEAX00PEA_WK1K1K@Z; GetCrashVerticalPaths(void *,void *,void *,wchar_t *,ulong,wchar_t *,ulong,wchar_t *,ulong)
0x18004e538  mov     ebx, eax
0x18004e53a  test    eax, eax
0x18004e53c  jns     short loc_18004E56C
0x18004e53e  mov     r9, gs:40h
0x18004e547  lea     r8, aWerReportfault_20; "WER/ReportFault/%u:%u: ERROR Failed to "...
0x18004e54e  mov     [rsp+330h+dwCreationFlags], eax
0x18004e552  xor     edx, edx; Level
0x18004e554  mov     ecx, 96h; ComponentId
0x18004e559  mov     [rsp+330h+bInheritHandles], 26Dh
0x18004e561  call    cs:__imp_DbgPrintEx
0x18004e567  jmp     loc_18004E859
0x18004e56c  mov     rcx, rsi; ProcessHandle
0x18004e56f  call    ?WerpIsProtectedProcess@@YAHPEAX@Z; WerpIsProtectedProcess(void *)
0x18004e574  neg     eax
0x18004e576  mov     ecx, edi; uMode
0x18004e578  sbb     r12d, r12d
0x18004e57b  and     r12d, 40000h
0x18004e582  call    cs:__imp_SetErrorMode
0x18004e588  lea     rdx, [rsp+330h+OldMode]; lpOldMode
0x18004e58d  mov     ecx, edi; dwNewMode
0x18004e58f  mov     [rsp+330h+uMode], eax
0x18004e593  call    cs:__imp_SetThreadErrorMode
0x18004e599  call    cs:__imp_RtlGetCurrentTransaction
0x18004e59f  xor     ecx, ecx
0x18004e5a1  mov     r13, rax
0x18004e5a4  call    cs:__imp_RtlSetCurrentTransaction
0x18004e5aa  mov     edi, r14d
0x18004e5ad  mov     esi, 96h
0x18004e5b2  cmp     edi, 3
0x18004e5b5  jnb     loc_18004E81D
0x18004e5bb  mov     ecx, edi
0x18004e5bd  test    edi, edi
0x18004e5bf  jz      short loc_18004E5E5
0x18004e5c1  sub     ecx, 1
0x18004e5c4  jz      short loc_18004E5D6
0x18004e5c6  cmp     ecx, 1
0x18004e5c9  jnz     loc_18004E7CC
0x18004e5cf  mov     [rsp+330h+var_2D8], r14d
0x18004e5d4  jmp     short loc_18004E5ED
0x18004e5d6  mov     [rsp+330h+var_2D8], r14d
0x18004e5db  mov     r14d, r12d
0x18004e5de  bts     r14d, 18h
0x18004e5e3  jmp     short loc_18004E5F0
0x18004e5e5  mov     [rsp+330h+var_2D8], 4
0x18004e5ed  mov     r14d, r12d
0x18004e5f0  xor     eax, eax
0x18004e5f2  lea     r8, [rsp+330h+var_2DC]
0x18004e5f7  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18004e5fb  mov     [rsp+330h+var_2E0], ax
0x18004e600  mov     rcx, rbx
0x18004e603  mov     [rsp+330h+var_2DC], ax
0x18004e608  lea     rdx, [rsp+330h+var_2E0]
0x18004e60d  call    cs:__imp_IsWow64Process2
0x18004e613  test    eax, eax
0x18004e615  jz      short loc_18004E655
0x18004e617  lea     r9d, [rbx+9]
0x18004e61b  mov     [rsp+330h+var_2B8], 0
0x18004e624  lea     r8, [rsp+330h+var_2B8]
0x18004e629  mov     rcx, rbx
0x18004e62c  lea     edx, [rbx+0Ah]
0x18004e62f  call    cs:__imp_GetProcessInformation
0x18004e635  test    eax, eax
0x18004e637  jz      short loc_18004E655
0x18004e639  movzx   ecx, [rsp+330h+var_2DC]
0x18004e63e  cmp     word ptr [rsp+330h+var_2B8], cx
0x18004e643  jnz     short loc_18004E64E
0x18004e645  xor     eax, eax
0x18004e647  mov     [rsp+330h+var_2E0], ax
0x18004e64c  jmp     short loc_18004E65F
0x18004e64e  movzx   eax, word ptr [rsp+330h+var_2B8]
0x18004e653  jmp     short loc_18004E647
0x18004e655  movzx   eax, [rsp+330h+var_2E0]
0x18004e65a  movzx   ecx, [rsp+330h+var_2DC]
0x18004e65f  mov     edx, 0AA64h
0x18004e664  cmp     cx, dx
0x18004e667  jnz     short loc_18004E673
0x18004e669  mov     ecx, 8664h
0x18004e66e  cmp     ax, cx
0x18004e671  jz      short loc_18004E67A
0x18004e673  xor     eax, eax
0x18004e675  mov     [rsp+330h+var_2E0], ax
0x18004e67a  lea     rax, [rsp+330h+var_2E0]
0x18004e67f  mov     [rsp+330h+lpAddress], 0
0x18004e688  mov     [rsp+330h+lpEnvironment], rax
0x18004e68d  lea     r8, [rsp+330h+var_2D8]
0x18004e692  lea     rax, [rsp+330h+var_2C4]
0x18004e697  mov     r9, r15
0x18004e69a  mov     qword ptr [rsp+330h+dwCreationFlags], rax
0x18004e69f  lea     rcx, [rsp+330h+lpAddress]
0x18004e6a4  mov     eax, [rsp+330h+var_2C0]
0x18004e6a8  mov     [rsp+330h+bInheritHandles], eax
0x18004e6ac  call    ?WerpBuildCreateProcessAttributeList@@YAJPEAV?$unique_ptr@U_PROC_THREAD_ATTRIBUTE_LIST@@U?$generic_delete@U_PROC_THREAD_ATTRIBUTE_LIST@@Uvirtualfree_release@@@tlx@@@utl@@PEAPEAXPEAK1K2PEAG@Z; WerpBuildCreateProcessAttributeList(utl::unique_ptr<_PROC_THREAD_ATTRIBUTE_LIST,tlx::generic_delete<_PROC_THREAD_ATTRIBUTE_LIST,virtualfree_release>> *,void * *,ulong *,void * *,ulong,ulong *,ushort *)
0x18004e6b1  mov     ebx, eax
0x18004e6b3  test    eax, eax
0x18004e6b5  js      loc_18004E87E
0x18004e6bb  mov     r15, [rsp+330h+lpAddress]
0x18004e6c0  lea     rdx, [rbp+230h+CommandLine]; lpCommandLine
0x18004e6c7  mov     rax, r15
0x18004e6ca  mov     [rbp+230h+var_218], r15
0x18004e6ce  neg     rax
0x18004e6d1  lea     rax, [rbp+230h+ProcessInformation]
0x18004e6d5  mov     [rsp+330h+lpProcessInformation], rax; lpProcessInformation
0x18004e6da  sbb     ecx, ecx
0x18004e6dc  and     ecx, 80000h
0x18004e6e2  lea     rax, [rbp+230h+StartupInfo]
0x18004e6e6  mov     [rsp+330h+lpStartupInfo], rax; lpStartupInfo
0x18004e6eb  or      ecx, r14d
0x18004e6ee  lea     rax, [rbp+230h+CurrentDirectory]
0x18004e6f2  xor     r14d, r14d
0x18004e6f5  mov     [rsp+330h+lpCurrentDirectory], rax; lpCurrentDirectory
0x18004e6fa  xor     r9d, r9d; lpThreadAttributes
0x18004e6fd  mov     [rsp+330h+lpEnvironment], r14; lpEnvironment
0x18004e702  xor     r8d, r8d; lpProcessAttributes
0x18004e705  mov     [rsp+330h+dwCreationFlags], ecx; dwCreationFlags
0x18004e709  lea     rcx, [rbp+230h+ApplicationName]; lpApplicationName
0x18004e70d  mov     [rsp+330h+bInheritHandles], 1; bInheritHandles
0x18004e715  call    cs:__imp_CreateProcessW
0x18004e71b  test    eax, eax
0x18004e71d  jnz     loc_18004E813
0x18004e723  call    WerpGetLastError
0x18004e728  mov     ebx, eax
0x18004e72a  test    edi, edi
0x18004e72c  jnz     short loc_18004E77F
0x18004e72e  mov     eax, 522h
0x18004e733  cmp     ebx, eax
0x18004e735  jnz     loc_18004E7D3
0x18004e73b  mov     r9, gs:40h
0x18004e744  lea     r8, aWerReportfault_21; "WER/ReportFault/%u:%u: WARNING CreatePr"...
0x18004e74b  mov     dword ptr [rsp+330h+lpEnvironment], eax
0x18004e74f  lea     edx, [rdi+1]; Level
0x18004e752  mov     [rsp+330h+dwCreationFlags], r14d
0x18004e757  mov     ecx, esi; ComponentId
0x18004e759  mov     [rsp+330h+bInheritHandles], 2DCh
0x18004e761  call    cs:__imp_DbgPrintEx
0x18004e767  test    r15, r15
0x18004e76a  jz      short loc_18004E7C1
0x18004e76c  xor     edx, edx; dwSize
0x18004e76e  mov     r8d, 8000h; dwFreeType
0x18004e774  mov     rcx, r15; lpAddress
0x18004e777  call    cs:__imp_VirtualFree
0x18004e77d  jmp     short loc_18004E7C1
0x18004e77f  mov     eax, 1
0x18004e784  cmp     edi, eax
0x18004e786  jnz     short loc_18004E7D3
0x18004e788  cmp     ebx, 5
0x18004e78b  jnz     short loc_18004E7D3
0x18004e78d  mov     r9, gs:40h
0x18004e796  lea     r8, aWerReportfault_21; "WER/ReportFault/%u:%u: WARNING CreatePr"...
0x18004e79d  mov     dword ptr [rsp+330h+lpEnvironment], ebx
0x18004e7a1  mov     edx, eax; Level
0x18004e7a3  mov     [rsp+330h+dwCreationFlags], eax
0x18004e7a7  mov     ecx, esi; ComponentId
0x18004e7a9  mov     [rsp+330h+bInheritHandles], 2E2h
0x18004e7b1  call    cs:__imp_DbgPrintEx
0x18004e7b7  lea     rcx, [rsp+330h+lpAddress]
0x18004e7bc  call    ??1?$unique_ptr@U_PROC_THREAD_ATTRIBUTE_LIST@@U?$generic_delete@U_PROC_THREAD_ATTRIBUTE_LIST@@Uvirtualfree_release@@@tlx@@@utl@@QEAA@XZ; utl::unique_ptr<_PROC_THREAD_ATTRIBUTE_LIST,tlx::generic_delete<_PROC_THREAD_ATTRIBUTE_LIST,virtualfree_release>>::~unique_ptr<_PROC_THREAD_ATTRIBUTE_LIST,tlx::generic_delete<_PROC_THREAD_ATTRIBUTE_LIST,virtualfree_release>>(void)
0x18004e7c1  mov     r15, [rbp+230h+var_2B0]
0x18004e7c5  inc     edi
0x18004e7c7  jmp     loc_18004E5B2
0x18004e7cc  mov     ebx, 80004005h
0x18004e7d1  jmp     short loc_18004E835
0x18004e7d3  mov     r9, gs:40h
0x18004e7dc  lea     r8, aWerReportfault_5; "WER/ReportFault/%u:%u: ERROR CreateProc"...
0x18004e7e3  mov     dword ptr [rsp+330h+lpEnvironment], ebx
0x18004e7e7  xor     edx, edx; Level
0x18004e7e9  mov     [rsp+330h+dwCreationFlags], edi
0x18004e7ed  mov     ecx, esi; ComponentId
0x18004e7ef  mov     [rsp+330h+bInheritHandles], 2E7h
0x18004e7f7  call    cs:__imp_DbgPrintEx
0x18004e7fd  test    ebx, ebx
0x18004e7ff  jle     loc_18004E8A4
0x18004e805  movzx   ebx, bx
0x18004e808  or      ebx, 80070000h
0x18004e80e  jmp     loc_18004E8A4
0x18004e813  lea     rcx, [rsp+330h+lpAddress]
0x18004e818  call    ??1?$unique_ptr@U_PROC_THREAD_ATTRIBUTE_LIST@@U?$generic_delete@U_PROC_THREAD_ATTRIBUTE_LIST@@Uvirtualfree_release@@@tlx@@@utl@@QEAA@XZ; utl::unique_ptr<_PROC_THREAD_ATTRIBUTE_LIST,tlx::generic_delete<_PROC_THREAD_ATTRIBUTE_LIST,virtualfree_release>>::~unique_ptr<_PROC_THREAD_ATTRIBUTE_LIST,tlx::generic_delete<_PROC_THREAD_ATTRIBUTE_LIST,virtualfree_release>>(void)
0x18004e81d  mov     rcx, [rbp+230h+var_2A8]
0x18004e821  mov     rax, [rbp+230h+ProcessInformation.hProcess]
0x18004e825  mov     [rcx], rax
0x18004e828  mov     rcx, [rbp+230h+ProcessInformation.hThread]; Handle
0x18004e82c  call    cs:__imp_NtClose
0x18004e832  mov     ebx, r14d
0x18004e835  mov     ecx, [rsp+330h+uMode]; uMode
0x18004e839  call    cs:__imp_SetErrorMode
0x18004e83f  mov     ecx, [rsp+330h+OldMode]; dwNewMode
0x18004e843  xor     edx, edx; lpOldMode
0x18004e845  call    cs:__imp_SetThreadErrorMode
0x18004e84b  test    r13, r13
0x18004e84e  jz      short loc_18004E859
0x18004e850  mov     rcx, r13
0x18004e853  call    cs:__imp_RtlSetCurrentTransaction
0x18004e859  mov     eax, ebx
0x18004e85b  mov     rcx, [rbp+230h+var_50]
0x18004e862  xor     rcx, rsp; StackCookie
0x18004e865  call    __security_check_cookie
0x18004e86a  add     rsp, 2F8h
0x18004e871  pop     r15
0x18004e873  pop     r14
0x18004e875  pop     r13
0x18004e877  pop     r12
0x18004e879  pop     rdi
0x18004e87a  pop     rsi
0x18004e87b  pop     rbx
0x18004e87c  pop     rbp
0x18004e87d  retn
0x18004e87e  mov     r9, gs:40h
0x18004e887  lea     r8, aWerReportfault_10; "WER/ReportFault/%u:%u: ERROR WerpBuildC"...
0x18004e88e  mov     [rsp+330h+dwCreationFlags], eax
0x18004e892  xor     edx, edx; Level
0x18004e894  mov     ecx, esi; ComponentId
0x18004e896  mov     [rsp+330h+bInheritHandles], 2BFh
0x18004e89e  call    cs:__imp_DbgPrintEx
0x18004e8a4  lea     rcx, [rsp+330h+lpAddress]
0x18004e8a9  call    ??1?$unique_ptr@U_PROC_THREAD_ATTRIBUTE_LIST@@U?$generic_delete@U_PROC_THREAD_ATTRIBUTE_LIST@@Uvirtualfree_release@@@tlx@@@utl@@QEAA@XZ; utl::unique_ptr<_PROC_THREAD_ATTRIBUTE_LIST,tlx::generic_delete<_PROC_THREAD_ATTRIBUTE_LIST,virtualfree_release>>::~unique_ptr<_PROC_THREAD_ATTRIBUTE_LIST,tlx::generic_delete<_PROC_THREAD_ATTRIBUTE_LIST,virtualfree_release>>(void)
0x18004e8ae  jmp     short loc_18004E835
```
