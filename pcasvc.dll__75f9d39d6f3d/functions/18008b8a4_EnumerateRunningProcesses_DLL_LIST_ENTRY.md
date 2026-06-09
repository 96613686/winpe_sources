# EnumerateRunningProcesses(_DLL_LIST_ENTRY * *)

- ea: `0x18008b8a4`
- end: `0x18008ba93`
- name: `?EnumerateRunningProcesses@@YAHPEAPEAU_DLL_LIST_ENTRY@@@Z`
- size: `495`
- prototype: `__int64 __fastcall(struct _DLL_LIST_ENTRY **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18008a920`

## callees

- `0x180012920`
- `0x18007a9cf`
- `0x18008b784`
- `0x18008b8a4`
- `0x1800f1f10`
- `0x1800f1fd0`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18008b9d3`
- `msvcrt!wcscpy_s` at `0x18008b9f3`
- `msvcrt!wcscpy_s` at `0x18008b9d3`
- `msvcrt!wcscpy_s` at `0x18008b9f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b90f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b954`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b90f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b954`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008b9dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008ba60`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008b9dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008ba60`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18008b99b`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18008b99b`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18008b9ba`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18008b9ba`
- `api-ms-win-core-toolhelp-l1-1-0!Process32NextW` at `0x18008ba21`
- `api-ms-win-core-toolhelp-l1-1-0!Process32NextW` at `0x18008ba21`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x18008b900`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x18008b900`
- `api-ms-win-core-toolhelp-l1-1-0!Process32FirstW` at `0x18008b948`
- `api-ms-win-core-toolhelp-l1-1-0!Process32FirstW` at `0x18008b948`

## string_xrefs

- `0x18008b915`: `CreateToolhelp32Snapshot failed with error [%d]`
- `0x18008ba33`: `Process enumeration completed: %d total processes, %d with DLL info, %d access denied`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall EnumerateRunningProcesses(struct _DLL_LIST_ENTRY **a1)
{
  HANDLE Toolhelp32Snapshot; // rax
  void *v3; // rbx
  unsigned int v5; // edi
  int v6; // esi
  int v7; // r14d
  HANDLE v8; // rax
  void *v9; // rdi
  int v10; // eax
  int v11; // ecx
  DWORD dwSize[4]; // [rsp+40h] [rbp-C0h] BYREF
  PROCESSENTRY32W pe; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR ExeName[4096]; // [rsp+290h] [rbp+190h] BYREF

  memset_0(&pe, 0, sizeof(pe));
  dwSize[0] = 0;
  Toolhelp32Snapshot = CreateToolhelp32Snapshot(2u, 0);
  v3 = Toolhelp32Snapshot;
  if ( Toolhelp32Snapshot == (HANDLE)-1LL )
  {
    GetLastError();
    AslLogCallPrintf(
      1,
      (unsigned int)"EnumerateRunningProcesses",
      997,
      (unsigned int)"CreateToolhelp32Snapshot failed with error [%d]");
    return 0;
  }
  else
  {
    pe.dwSize = 568;
    if ( Process32FirstW(Toolhelp32Snapshot, &pe) )
    {
      v6 = 0;
      v7 = 0;
      do
      {
        dwSize[0] = 4096;
        ++v6;
        v8 = OpenProcess(0x1000u, 0, pe.th32ProcessID);
        v9 = v8;
        if ( v8 )
        {
          if ( !QueryFullProcessImageNameW(v8, 0, ExeName, dwSize) )
            wcscpy_s(ExeName, 0x1000u, pe.szExeFile);
          CloseHandle(v9);
        }
        else
        {
          wcscpy_s(ExeName, 0x1000u, pe.szExeFile);
        }
        v10 = EnumerateProcessDlls(pe.th32ProcessID, ExeName, a1);
        v11 = v7 + 1;
        if ( !v10 )
          v11 = v7;
        v7 = v11;
      }
      while ( Process32NextW(v3, &pe) );
      AslLogCallPrintf(
        3,
        (unsigned int)"EnumerateRunningProcesses",
        1040,
        (unsigned int)"Process enumeration completed: %d total processes, %d with DLL info, %d access denied");
      v5 = 1;
    }
    else
    {
      v5 = 0;
      GetLastError();
      AslLogCallPrintf(
        1,
        (unsigned int)"EnumerateRunningProcesses",
        1006,
        (unsigned int)"Process32First failed with error [%d]");
    }
    CloseHandle(v3);
    return v5;
  }
}

```

## disassembly

```asm
0x18008b8a4  mov     [rsp-8+arg_8], rbx
0x18008b8a9  mov     [rsp-8+arg_10], rsi
0x18008b8ae  push    rbp
0x18008b8af  push    rdi
0x18008b8b0  push    r12
0x18008b8b2  push    r14
0x18008b8b4  push    r15
0x18008b8b6  lea     rbp, [rsp-21A0h]
0x18008b8be  mov     eax, 22A0h
0x18008b8c3  call    _alloca_probe
0x18008b8c8  sub     rsp, rax
0x18008b8cb  mov     rax, cs:__security_cookie
0x18008b8d2  xor     rax, rsp
0x18008b8d5  mov     [rbp+21C0h+var_30], rax
0x18008b8dc  mov     r15, rcx
0x18008b8df  mov     edi, 238h
0x18008b8e4  mov     r8d, edi; Size
0x18008b8e7  lea     rcx, [rsp+22C0h+pe]; void *
0x18008b8ec  xor     edx, edx; Val
0x18008b8ee  call    memset_0
0x18008b8f3  xor     edx, edx; th32ProcessID
0x18008b8f5  mov     [rsp+22C0h+dwSize], 0
0x18008b8fd  lea     ecx, [rdx+2]; dwFlags
0x18008b900  call    cs:__imp_CreateToolhelp32Snapshot
0x18008b906  mov     rbx, rax
0x18008b909  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18008b90d  jnz     short loc_18008B93C
0x18008b90f  call    cs:__imp_GetLastError
0x18008b915  lea     r9, aCreatetoolhelp; "CreateToolhelp32Snapshot failed with er"...
0x18008b91c  mov     r8d, 3E5h
0x18008b922  lea     rdx, aEnumeraterunni; "EnumerateRunningProcesses"
0x18008b929  mov     [rsp+22C0h+var_22A0], eax
0x18008b92d  lea     ecx, [rbx+2]
0x18008b930  call    AslLogCallPrintf
0x18008b935  xor     eax, eax
0x18008b937  jmp     loc_18008BA68
0x18008b93c  lea     rdx, [rsp+22C0h+pe]; lppe
0x18008b941  mov     [rsp+22C0h+pe.dwSize], edi
0x18008b945  mov     rcx, rbx; hSnapshot
0x18008b948  call    cs:__imp_Process32FirstW
0x18008b94e  test    eax, eax
0x18008b950  jnz     short loc_18008B97F
0x18008b952  xor     edi, edi
0x18008b954  call    cs:__imp_GetLastError
0x18008b95a  lea     r9, aProcess32first; "Process32First failed with error [%d]"
0x18008b961  mov     r8d, 3EEh
0x18008b967  lea     rdx, aEnumeraterunni; "EnumerateRunningProcesses"
0x18008b96e  mov     [rsp+22C0h+var_22A0], eax
0x18008b972  lea     ecx, [rdi+1]
0x18008b975  call    AslLogCallPrintf
0x18008b97a  jmp     loc_18008BA5D
0x18008b97f  xor     esi, esi
0x18008b981  mov     r12d, 1000h
0x18008b987  xor     r14d, r14d
0x18008b98a  mov     r8d, [rsp+22C0h+pe.th32ProcessID]; dwProcessId
0x18008b98f  xor     edx, edx; bInheritHandle
0x18008b991  mov     ecx, r12d; dwDesiredAccess
0x18008b994  mov     [rsp+22C0h+dwSize], r12d
0x18008b999  inc     esi
0x18008b99b  call    cs:__imp_OpenProcess
0x18008b9a1  mov     rdi, rax
0x18008b9a4  test    rax, rax
0x18008b9a7  jz      short loc_18008B9E4
0x18008b9a9  lea     r9, [rsp+22C0h+dwSize]; lpdwSize
0x18008b9ae  xor     edx, edx; dwFlags
0x18008b9b0  lea     r8, [rbp+21C0h+ExeName]; lpExeName
0x18008b9b7  mov     rcx, rax; hProcess
0x18008b9ba  call    cs:__imp_QueryFullProcessImageNameW
0x18008b9c0  test    eax, eax
0x18008b9c2  jnz     short loc_18008B9D9
0x18008b9c4  lea     r8, [rsp+22C0h+pe.szExeFile]; Source
0x18008b9c9  mov     rdx, r12; SizeInWords
0x18008b9cc  lea     rcx, [rbp+21C0h+ExeName]; Destination
0x18008b9d3  call    cs:__imp_wcscpy_s
0x18008b9d9  mov     rcx, rdi; hObject
0x18008b9dc  call    cs:__imp_CloseHandle
0x18008b9e2  jmp     short loc_18008B9F9
0x18008b9e4  lea     r8, [rsp+22C0h+pe.szExeFile]; Source
0x18008b9e9  mov     rdx, r12; SizeInWords
0x18008b9ec  lea     rcx, [rbp+21C0h+ExeName]; Destination
0x18008b9f3  call    cs:__imp_wcscpy_s
0x18008b9f9  mov     ecx, [rsp+22C0h+pe.th32ProcessID]; th32ProcessID
0x18008b9fd  lea     rdx, [rbp+21C0h+ExeName]; unsigned __int16 *
0x18008ba04  mov     r8, r15; struct _DLL_LIST_ENTRY **
0x18008ba07  call    ?EnumerateProcessDlls@@YAHKPEBGPEAPEAU_DLL_LIST_ENTRY@@@Z; EnumerateProcessDlls(ulong,ushort const *,_DLL_LIST_ENTRY * *)
0x18008ba0c  lea     ecx, [r14+1]
0x18008ba10  test    eax, eax
0x18008ba12  lea     rdx, [rsp+22C0h+pe]; lppe
0x18008ba17  cmovz   ecx, r14d
0x18008ba1b  mov     r14d, ecx
0x18008ba1e  mov     rcx, rbx; hSnapshot
0x18008ba21  call    cs:__imp_Process32NextW
0x18008ba27  test    eax, eax
0x18008ba29  jnz     loc_18008B98A
0x18008ba2f  mov     [rsp+22C0h+var_2290], eax
0x18008ba33  lea     r9, aProcessEnumera; "Process enumeration completed: %d total"...
0x18008ba3a  mov     [rsp+22C0h+var_2298], r14d
0x18008ba3f  lea     rdx, aEnumeraterunni; "EnumerateRunningProcesses"
0x18008ba46  mov     r8d, 410h
0x18008ba4c  mov     [rsp+22C0h+var_22A0], esi
0x18008ba50  lea     ecx, [rax+3]
0x18008ba53  call    AslLogCallPrintf
0x18008ba58  mov     edi, 1
0x18008ba5d  mov     rcx, rbx; hObject
0x18008ba60  call    cs:__imp_CloseHandle
0x18008ba66  mov     eax, edi
0x18008ba68  mov     rcx, [rbp+21C0h+var_30]
0x18008ba6f  xor     rcx, rsp; StackCookie
0x18008ba72  call    __security_check_cookie
0x18008ba77  lea     r11, [rsp+22C0h+var_20]
0x18008ba7f  mov     rbx, [r11+38h]
0x18008ba83  mov     rsi, [r11+40h]
0x18008ba87  mov     rsp, r11
0x18008ba8a  pop     r15
0x18008ba8c  pop     r14
0x18008ba8e  pop     r12
0x18008ba90  pop     rdi
0x18008ba91  pop     rbp
0x18008ba92  retn
```
