# udk::CopilotPlusDetection::_GetPhysicalDiskSize(ushort const *,_ULARGE_INTEGER *)

- ea: `0x1400ff5b4`
- end: `0x1400ff8d6`
- name: `?_GetPhysicalDiskSize@CopilotPlusDetection@udk@@YAJPEBGPEAT_ULARGE_INTEGER@@@Z`
- size: `802`
- prototype: `__int64 __fastcall(LPCWSTR lpszFileName, const unsigned __int16 *, union _ULARGE_INTEGER *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path, registry_config`

## callers

- `0x14009945c`

## callees

- `0x1400847f8`
- `0x1400954e0`
- `0x1400987b8`
- `0x1400ff5b4`
- `0x1400ff8dc`
- `0x1401040e0`
- `0x140104490`
- `0x140104ce0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400ff7b4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400ff847`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400ff88f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400ff7b4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400ff847`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400ff88f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400ff7c8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400ff7c8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400ff855`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400ff89d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400ff855`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400ff89d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400ff67f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400ff788`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400ff67f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400ff788`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400ff76f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400ff76f`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1400ff62c`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1400ff6ab`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1400ff62c`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1400ff6ab`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1400ff675`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1400ff675`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1400ff6cb`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1400ff6cb`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1400ff823`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1400ff823`

## pseudocode

```c
signed int __fastcall udk::CopilotPlusDetection::_GetPhysicalDiskSize(
        LPCWSTR lpszFileName,
        unsigned __int16 *a2,
        union _ULARGE_INTEGER *a3)
{
  const char *v5; // r9
  __int64 v6; // rdx
  signed int result; // eax
  int v8; // eax
  unsigned int v9; // ebx
  unsigned __int64 v10; // rcx
  HANDLE FileW; // rbx
  signed int LastError; // eax
  HANDLE ProcessHeap; // rax
  unsigned int *v14; // rdi
  const char *v15; // r9
  HANDLE v16; // rax
  unsigned __int64 v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rax
  HANDLE v20; // rax
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v23; // [rsp+40h] [rbp-C0h] BYREF
  DWORD BytesReturned[6]; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR szVolumeName[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR szVolumePathName[264]; // [rsp+270h] [rbp+170h] BYREF
  WCHAR Buffer[264]; // [rsp+480h] [rbp+380h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+6B8h] [rbp+5B8h]

  *(_QWORD *)a2 = 0;
  memset_0(szVolumeName, 0, 0x208u);
  memset_0(szVolumePathName, 0, 0x208u);
  if ( lpszFileName )
  {
    if ( !GetVolumePathNameW(lpszFileName, szVolumePathName, 0x104u) )
    {
      v6 = 413;
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)v6,
               (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
               v5);
    }
  }
  else
  {
    memset_0(Buffer, 0, 0x208u);
    if ( !GetSystemDirectoryW(Buffer, 0x104u) )
    {
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
      return result;
    }
    if ( !GetVolumePathNameW(Buffer, szVolumePathName, 0x104u) )
    {
      v6 = 423;
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)v6,
               (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
               v5);
    }
  }
  if ( !GetVolumeNameForVolumeMountPointW(szVolumePathName, szVolumeName, 0x104u) )
  {
    v6 = 426;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v6,
             (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
             v5);
  }
  v23 = 0;
  v8 = StringCchLengthW(szVolumeName, 0x104u, &v23);
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1AE,
      (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
      (const char *)(unsigned int)v8,
      dwCreationDisposition);
    return v9;
  }
  if ( v23 && *((_WORD *)&BytesReturned[5] + v23 + 1) == 92 )
  {
    v10 = 2 * v23 - 2;
    if ( v10 >= 0x208 )
      _report_rangecheckfailure();
    *(WCHAR *)((char *)szVolumeName + v10) = 0;
  }
  FileW = CreateFileW(szVolumeName, 0, 1u, 0, 3u, 0x2000000u, 0);
  v23 = (unsigned __int64)FileW;
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_27;
  }
  BytesReturned[0] = 0;
  ProcessHeap = GetProcessHeap();
  v14 = (unsigned int *)HeapAlloc(ProcessHeap, 0, 0x48C0u);
  if ( !v14 )
  {
    v9 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1BE,
      (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
      (const char *)0x8007000ELL,
      dwCreationDispositiona);
LABEL_27:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v23);
    return v9;
  }
  if ( !DeviceIoControl(FileW, 0x70050u, 0, 0, v14, 0x48C0u, BytesReturned, 0) )
  {
    v9 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x1C4,
           (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
           v15);
    v16 = GetProcessHeap();
    HeapFree(v16, 0, v14);
    goto LABEL_27;
  }
  v17 = 0;
  if ( v14[1] )
  {
    v18 = *(_QWORD *)a2;
    do
    {
      v19 = 9 * v17++;
      v18 += *(_QWORD *)&v14[4 * v19 + 16];
      *(_QWORD *)a2 = v18;
    }
    while ( v17 < v14[1] );
  }
  v20 = GetProcessHeap();
  HeapFree(v20, 0, v14);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v23);
  return 0;
}

```

## disassembly

```asm
0x1400ff5b4  mov     [rsp-8+arg_10], rbx
0x1400ff5b9  mov     [rsp-8+arg_18], rsi
0x1400ff5be  push    rbp
0x1400ff5bf  push    rdi
0x1400ff5c0  push    r15
0x1400ff5c2  lea     rbp, [rsp-5A0h]
0x1400ff5ca  sub     rsp, 6A0h
0x1400ff5d1  mov     rax, cs:__security_cookie
0x1400ff5d8  xor     rax, rsp
0x1400ff5db  mov     [rbp+5B0h+var_20], rax
0x1400ff5e2  mov     rsi, rdx
0x1400ff5e5  mov     qword ptr [rdx], 0
0x1400ff5ec  mov     rdi, rcx
0x1400ff5ef  mov     r15d, 208h
0x1400ff5f5  mov     r8d, r15d; Size
0x1400ff5f8  lea     rcx, [rsp+6B0h+szVolumeName]; void *
0x1400ff5fd  xor     edx, edx; Val
0x1400ff5ff  call    memset_0
0x1400ff604  mov     r8d, r15d; Size
0x1400ff607  lea     rcx, [rbp+5B0h+szVolumePathName]; void *
0x1400ff60e  xor     edx, edx; Val
0x1400ff610  call    memset_0
0x1400ff615  test    rdi, rdi
0x1400ff618  jz      short loc_1400FF656
0x1400ff61a  mov     ebx, 104h
0x1400ff61f  lea     rdx, [rbp+5B0h+szVolumePathName]; lpszVolumePathName
0x1400ff626  mov     r8d, ebx; cchBufferLength
0x1400ff629  mov     rcx, rdi; lpszFileName
0x1400ff62c  call    cs:__imp_GetVolumePathNameW
0x1400ff632  test    eax, eax
0x1400ff634  jnz     loc_1400FF6BC
0x1400ff63a  lea     edx, [r15-6Bh]; void *
0x1400ff63e  mov     rcx, [rbp+5B8h]; this
0x1400ff645  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x1400ff64c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400ff651  jmp     loc_1400FF8AF
0x1400ff656  mov     r8, r15; Size
0x1400ff659  lea     rcx, [rbp+5B0h+Buffer]; void *
0x1400ff660  xor     edx, edx; Val
0x1400ff662  call    memset_0
0x1400ff667  mov     ebx, 104h
0x1400ff66c  lea     rcx, [rbp+5B0h+Buffer]; lpBuffer
0x1400ff673  mov     edx, ebx; uSize
0x1400ff675  call    cs:__imp_GetSystemDirectoryW
0x1400ff67b  test    eax, eax
0x1400ff67d  jnz     short loc_1400FF69A
0x1400ff67f  call    cs:__imp_GetLastError
0x1400ff685  test    eax, eax
0x1400ff687  jle     loc_1400FF8AF
0x1400ff68d  movzx   eax, ax
0x1400ff690  or      eax, 80070000h
0x1400ff695  jmp     loc_1400FF8AF
0x1400ff69a  mov     r8d, ebx; cchBufferLength
0x1400ff69d  lea     rdx, [rbp+5B0h+szVolumePathName]; lpszVolumePathName
0x1400ff6a4  lea     rcx, [rbp+5B0h+Buffer]; lpszFileName
0x1400ff6ab  call    cs:__imp_GetVolumePathNameW
0x1400ff6b1  test    eax, eax
0x1400ff6b3  jnz     short loc_1400FF6BC
0x1400ff6b5  mov     edx, 1A7h
0x1400ff6ba  jmp     short loc_1400FF63E
0x1400ff6bc  mov     r8d, ebx; cchBufferLength
0x1400ff6bf  lea     rdx, [rsp+6B0h+szVolumeName]; lpszVolumeName
0x1400ff6c4  lea     rcx, [rbp+5B0h+szVolumePathName]; lpszVolumeMountPoint
0x1400ff6cb  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x1400ff6d1  test    eax, eax
0x1400ff6d3  jnz     short loc_1400FF6DF
0x1400ff6d5  mov     edx, 1AAh
0x1400ff6da  jmp     loc_1400FF63E
0x1400ff6df  lea     r8, [rsp+6B0h+var_670]; unsigned __int64 *
0x1400ff6e4  mov     [rsp+6B0h+var_670], 0
0x1400ff6ed  mov     rdx, rbx; unsigned __int64
0x1400ff6f0  lea     rcx, [rsp+6B0h+szVolumeName]; unsigned __int16 *
0x1400ff6f5  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1400ff6fa  mov     ebx, eax
0x1400ff6fc  test    eax, eax
0x1400ff6fe  jns     short loc_1400FF722
0x1400ff700  mov     rcx, [rbp+5B8h]; this
0x1400ff707  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x1400ff70e  mov     r9d, eax; char *
0x1400ff711  mov     edx, 1AEh; void *
0x1400ff716  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400ff71b  mov     eax, ebx
0x1400ff71d  jmp     loc_1400FF8AF
0x1400ff722  mov     rax, [rsp+6B0h+var_670]
0x1400ff727  test    rax, rax
0x1400ff72a  jz      short loc_1400FF748
0x1400ff72c  cmp     [rsp+rax*2+6B0h+var_652], 5Ch ; '\'
0x1400ff732  jnz     short loc_1400FF748
0x1400ff734  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x1400ff73c  cmp     rcx, r15
0x1400ff73f  jnb     short loc_1400FF7A6
0x1400ff741  xor     eax, eax
0x1400ff743  mov     [rsp+rcx+6B0h+szVolumeName], ax
0x1400ff748  xor     r9d, r9d; lpSecurityAttributes
0x1400ff74b  mov     [rsp+6B0h+hTemplateFile], 0; hTemplateFile
0x1400ff754  mov     [rsp+6B0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x1400ff75c  lea     rcx, [rsp+6B0h+szVolumeName]; lpFileName
0x1400ff761  xor     edx, edx; dwDesiredAccess
0x1400ff763  mov     [rsp+6B0h+dwCreationDisposition], 3; int
0x1400ff76b  lea     r8d, [r9+1]; dwShareMode
0x1400ff76f  call    cs:__imp_CreateFileW
0x1400ff775  mov     rbx, rax
0x1400ff778  mov     [rsp+6B0h+var_670], rax
0x1400ff77d  inc     rax
0x1400ff780  test    rax, 0FFFFFFFFFFFFFFFEh
0x1400ff786  jnz     short loc_1400FF7AC
0x1400ff788  call    cs:__imp_GetLastError
0x1400ff78e  mov     ebx, eax
0x1400ff790  test    eax, eax
0x1400ff792  jle     loc_1400FF85B
0x1400ff798  movzx   ebx, ax
0x1400ff79b  or      ebx, 80070000h
0x1400ff7a1  jmp     loc_1400FF85B
0x1400ff7a6  call    __report_rangecheckfailure
0x1400ff7ac  mov     [rsp+6B0h+BytesReturned], 0
0x1400ff7b4  call    cs:__imp_GetProcessHeap
0x1400ff7ba  mov     r15d, 48C0h
0x1400ff7c0  xor     edx, edx; dwFlags
0x1400ff7c2  mov     rcx, rax; hHeap
0x1400ff7c5  mov     r8d, r15d; dwBytes
0x1400ff7c8  call    cs:__imp_HeapAlloc
0x1400ff7ce  mov     rdi, rax
0x1400ff7d1  test    rax, rax
0x1400ff7d4  jnz     short loc_1400FF7F8
0x1400ff7d6  mov     rcx, [rbp+5B8h]; this
0x1400ff7dd  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x1400ff7e4  mov     ebx, 8007000Eh
0x1400ff7e9  mov     edx, 1BEh; void *
0x1400ff7ee  mov     r9d, ebx; char *
0x1400ff7f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400ff7f6  jmp     short loc_1400FF85B
0x1400ff7f8  mov     [rsp+6B0h+lpOverlapped], 0; lpOverlapped
0x1400ff801  lea     rax, [rsp+6B0h+BytesReturned]
0x1400ff806  mov     [rsp+6B0h+hTemplateFile], rax; lpBytesReturned
0x1400ff80b  xor     r9d, r9d; nInBufferSize
0x1400ff80e  mov     [rsp+6B0h+dwFlagsAndAttributes], r15d; nOutBufferSize
0x1400ff813  xor     r8d, r8d; lpInBuffer
0x1400ff816  mov     edx, 70050h; dwIoControlCode
0x1400ff81b  mov     qword ptr [rsp+6B0h+dwCreationDisposition], rdi; lpOutBuffer
0x1400ff820  mov     rcx, rbx; hDevice
0x1400ff823  call    cs:__imp_DeviceIoControl
0x1400ff829  test    eax, eax
0x1400ff82b  jnz     short loc_1400FF86A
0x1400ff82d  mov     rcx, [rbp+5B8h]; this
0x1400ff834  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x1400ff83b  mov     edx, 1C4h; void *
0x1400ff840  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400ff845  mov     ebx, eax
0x1400ff847  call    cs:__imp_GetProcessHeap
0x1400ff84d  mov     r8, rdi; lpMem
0x1400ff850  xor     edx, edx; dwFlags
0x1400ff852  mov     rcx, rax; hHeap
0x1400ff855  call    cs:__imp_HeapFree
0x1400ff85b  lea     rcx, [rsp+6B0h+var_670]
0x1400ff860  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1400ff865  jmp     loc_1400FF71B
0x1400ff86a  xor     ecx, ecx
0x1400ff86c  cmp     [rdi+4], ecx
0x1400ff86f  jbe     short loc_1400FF88F
0x1400ff871  mov     rdx, [rsi]
0x1400ff874  lea     rax, [rcx+rcx*8]
0x1400ff878  inc     rcx
0x1400ff87b  shl     rax, 4
0x1400ff87f  add     rdx, [rax+rdi+40h]
0x1400ff884  mov     [rsi], rdx
0x1400ff887  mov     eax, [rdi+4]
0x1400ff88a  cmp     rcx, rax
0x1400ff88d  jb      short loc_1400FF874
0x1400ff88f  call    cs:__imp_GetProcessHeap
0x1400ff895  mov     r8, rdi; lpMem
0x1400ff898  xor     edx, edx; dwFlags
0x1400ff89a  mov     rcx, rax; hHeap
0x1400ff89d  call    cs:__imp_HeapFree
0x1400ff8a3  lea     rcx, [rsp+6B0h+var_670]
0x1400ff8a8  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1400ff8ad  xor     eax, eax
0x1400ff8af  mov     rcx, [rbp+5B0h+var_20]
0x1400ff8b6  xor     rcx, rsp; StackCookie
0x1400ff8b9  call    __security_check_cookie
0x1400ff8be  lea     r11, [rsp+6B0h+var_10]
0x1400ff8c6  mov     rbx, [r11+30h]
0x1400ff8ca  mov     rsi, [r11+38h]
0x1400ff8ce  mov     rsp, r11
0x1400ff8d1  pop     r15
0x1400ff8d3  pop     rdi
0x1400ff8d4  pop     rbp
0x1400ff8d5  retn
```
