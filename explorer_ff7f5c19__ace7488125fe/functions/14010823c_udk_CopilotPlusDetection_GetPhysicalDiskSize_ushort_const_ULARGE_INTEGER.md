# udk::CopilotPlusDetection::_GetPhysicalDiskSize(ushort const *,_ULARGE_INTEGER *)

- ea: `0x14010823c`
- end: `0x1401085b6`
- name: `?_GetPhysicalDiskSize@CopilotPlusDetection@udk@@YAJPEBGPEAT_ULARGE_INTEGER@@@Z`
- size: `890`
- prototype: `__int64 __fastcall(LPCWSTR lpszFileName, const unsigned __int16 *, union _ULARGE_INTEGER *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path, registry_config`

## callers

- `0x14009eaa4`

## callees

- `0x14008a0b8`
- `0x14009ac68`
- `0x14009de4c`
- `0x14010823c`
- `0x1401085bc`
- `0x14010e160`
- `0x14010e510`
- `0x14010ed90`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140108483`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140108483`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140108469`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14010850e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140108562`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140108469`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14010850e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140108562`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140108522`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140108576`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140108522`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140108576`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140108313`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140108437`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140108313`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140108437`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140108418`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140108418`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1401082b4`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x140108345`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1401082b4`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x140108345`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x140108303`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x140108303`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x14010836e`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x14010836e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1401084e4`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1401084e4`

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
      v6 = 410;
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
      v6 = 420;
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)v6,
               (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
               v5);
    }
  }
  if ( !GetVolumeNameForVolumeMountPointW(szVolumePathName, szVolumeName, 0x104u) )
  {
    v6 = 423;
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
      (void *)0x1AB,
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
      (void *)0x1BB,
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
           (void *)0x1C1,
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
0x14010823c  mov     [rsp-8+arg_10], rbx
0x140108241  mov     [rsp-8+arg_18], rsi
0x140108246  push    rbp
0x140108247  push    rdi
0x140108248  push    r15
0x14010824a  lea     rbp, [rsp-5A0h]
0x140108252  sub     rsp, 6A0h
0x140108259  mov     rax, cs:__security_cookie
0x140108260  xor     rax, rsp
0x140108263  mov     [rbp+5B0h+var_20], rax
0x14010826a  mov     rsi, rdx
0x14010826d  mov     qword ptr [rdx], 0
0x140108274  mov     rdi, rcx
0x140108277  mov     r15d, 208h
0x14010827d  mov     r8d, r15d; Size
0x140108280  lea     rcx, [rsp+6B0h+szVolumeName]; void *
0x140108285  xor     edx, edx; Val
0x140108287  call    memset_0
0x14010828c  mov     r8d, r15d; Size
0x14010828f  lea     rcx, [rbp+5B0h+szVolumePathName]; void *
0x140108296  xor     edx, edx; Val
0x140108298  call    memset_0
0x14010829d  test    rdi, rdi
0x1401082a0  jz      short loc_1401082E4
0x1401082a2  mov     ebx, 104h
0x1401082a7  lea     rdx, [rbp+5B0h+szVolumePathName]; lpszVolumePathName
0x1401082ae  mov     r8d, ebx; cchBufferLength
0x1401082b1  mov     rcx, rdi; lpszFileName
0x1401082b4  call    cs:__imp_GetVolumePathNameW
0x1401082bb  nop     dword ptr [rax+rax+00h]
0x1401082c0  test    eax, eax
0x1401082c2  jnz     loc_14010835F
0x1401082c8  lea     edx, [r15-6Eh]; void *
0x1401082cc  mov     rcx, [rbp+5B8h]; this
0x1401082d3  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x1401082da  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1401082df  jmp     loc_14010858E
0x1401082e4  mov     r8, r15; Size
0x1401082e7  lea     rcx, [rbp+5B0h+Buffer]; void *
0x1401082ee  xor     edx, edx; Val
0x1401082f0  call    memset_0
0x1401082f5  mov     ebx, 104h
0x1401082fa  lea     rcx, [rbp+5B0h+Buffer]; lpBuffer
0x140108301  mov     edx, ebx; uSize
0x140108303  call    cs:__imp_GetSystemDirectoryW
0x14010830a  nop     dword ptr [rax+rax+00h]
0x14010830f  test    eax, eax
0x140108311  jnz     short loc_140108334
0x140108313  call    cs:__imp_GetLastError
0x14010831a  nop     dword ptr [rax+rax+00h]
0x14010831f  test    eax, eax
0x140108321  jle     loc_14010858E
0x140108327  movzx   eax, ax
0x14010832a  or      eax, 80070000h
0x14010832f  jmp     loc_14010858E
0x140108334  mov     r8d, ebx; cchBufferLength
0x140108337  lea     rdx, [rbp+5B0h+szVolumePathName]; lpszVolumePathName
0x14010833e  lea     rcx, [rbp+5B0h+Buffer]; lpszFileName
0x140108345  call    cs:__imp_GetVolumePathNameW
0x14010834c  nop     dword ptr [rax+rax+00h]
0x140108351  test    eax, eax
0x140108353  jnz     short loc_14010835F
0x140108355  mov     edx, 1A4h
0x14010835a  jmp     loc_1401082CC
0x14010835f  mov     r8d, ebx; cchBufferLength
0x140108362  lea     rdx, [rsp+6B0h+szVolumeName]; lpszVolumeName
0x140108367  lea     rcx, [rbp+5B0h+szVolumePathName]; lpszVolumeMountPoint
0x14010836e  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x140108375  nop     dword ptr [rax+rax+00h]
0x14010837a  test    eax, eax
0x14010837c  jnz     short loc_140108388
0x14010837e  mov     edx, 1A7h
0x140108383  jmp     loc_1401082CC
0x140108388  lea     r8, [rsp+6B0h+var_670]; unsigned __int64 *
0x14010838d  mov     [rsp+6B0h+var_670], 0
0x140108396  mov     rdx, rbx; unsigned __int64
0x140108399  lea     rcx, [rsp+6B0h+szVolumeName]; unsigned __int16 *
0x14010839e  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1401083a3  mov     ebx, eax
0x1401083a5  test    eax, eax
0x1401083a7  jns     short loc_1401083CB
0x1401083a9  mov     rcx, [rbp+5B8h]; this
0x1401083b0  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x1401083b7  mov     r9d, eax; char *
0x1401083ba  mov     edx, 1ABh; void *
0x1401083bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1401083c4  mov     eax, ebx
0x1401083c6  jmp     loc_14010858E
0x1401083cb  mov     rax, [rsp+6B0h+var_670]
0x1401083d0  test    rax, rax
0x1401083d3  jz      short loc_1401083F1
0x1401083d5  cmp     [rsp+rax*2+6B0h+var_652], 5Ch ; '\'
0x1401083db  jnz     short loc_1401083F1
0x1401083dd  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x1401083e5  cmp     rcx, r15
0x1401083e8  jnb     short loc_14010845B
0x1401083ea  xor     eax, eax
0x1401083ec  mov     [rsp+rcx+6B0h+szVolumeName], ax
0x1401083f1  xor     r9d, r9d; lpSecurityAttributes
0x1401083f4  mov     [rsp+6B0h+hTemplateFile], 0; hTemplateFile
0x1401083fd  mov     [rsp+6B0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x140108405  lea     rcx, [rsp+6B0h+szVolumeName]; lpFileName
0x14010840a  xor     edx, edx; dwDesiredAccess
0x14010840c  mov     [rsp+6B0h+dwCreationDisposition], 3; int
0x140108414  lea     r8d, [r9+1]; dwShareMode
0x140108418  call    cs:__imp_CreateFileW
0x14010841f  nop     dword ptr [rax+rax+00h]
0x140108424  mov     rbx, rax
0x140108427  mov     [rsp+6B0h+var_670], rax
0x14010842c  inc     rax
0x14010842f  test    rax, 0FFFFFFFFFFFFFFFEh
0x140108435  jnz     short loc_140108461
0x140108437  call    cs:__imp_GetLastError
0x14010843e  nop     dword ptr [rax+rax+00h]
0x140108443  mov     ebx, eax
0x140108445  test    eax, eax
0x140108447  jle     loc_14010852E
0x14010844d  movzx   ebx, ax
0x140108450  or      ebx, 80070000h
0x140108456  jmp     loc_14010852E
0x14010845b  call    __report_rangecheckfailure
0x140108461  mov     [rsp+6B0h+BytesReturned], 0
0x140108469  call    cs:__imp_GetProcessHeap
0x140108470  nop     dword ptr [rax+rax+00h]
0x140108475  mov     r15d, 48C0h
0x14010847b  xor     edx, edx; dwFlags
0x14010847d  mov     rcx, rax; hHeap
0x140108480  mov     r8d, r15d; dwBytes
0x140108483  call    cs:__imp_HeapAlloc
0x14010848a  nop     dword ptr [rax+rax+00h]
0x14010848f  mov     rdi, rax
0x140108492  test    rax, rax
0x140108495  jnz     short loc_1401084B9
0x140108497  mov     rcx, [rbp+5B8h]; this
0x14010849e  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x1401084a5  mov     ebx, 8007000Eh
0x1401084aa  mov     edx, 1BBh; void *
0x1401084af  mov     r9d, ebx; char *
0x1401084b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1401084b7  jmp     short loc_14010852E
0x1401084b9  mov     [rsp+6B0h+lpOverlapped], 0; lpOverlapped
0x1401084c2  lea     rax, [rsp+6B0h+BytesReturned]
0x1401084c7  mov     [rsp+6B0h+hTemplateFile], rax; lpBytesReturned
0x1401084cc  xor     r9d, r9d; nInBufferSize
0x1401084cf  mov     [rsp+6B0h+dwFlagsAndAttributes], r15d; nOutBufferSize
0x1401084d4  xor     r8d, r8d; lpInBuffer
0x1401084d7  mov     edx, 70050h; dwIoControlCode
0x1401084dc  mov     qword ptr [rsp+6B0h+dwCreationDisposition], rdi; lpOutBuffer
0x1401084e1  mov     rcx, rbx; hDevice
0x1401084e4  call    cs:__imp_DeviceIoControl
0x1401084eb  nop     dword ptr [rax+rax+00h]
0x1401084f0  test    eax, eax
0x1401084f2  jnz     short loc_14010853D
0x1401084f4  mov     rcx, [rbp+5B8h]; this
0x1401084fb  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x140108502  mov     edx, 1C1h; void *
0x140108507  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14010850c  mov     ebx, eax
0x14010850e  call    cs:__imp_GetProcessHeap
0x140108515  nop     dword ptr [rax+rax+00h]
0x14010851a  mov     r8, rdi; lpMem
0x14010851d  xor     edx, edx; dwFlags
0x14010851f  mov     rcx, rax; hHeap
0x140108522  call    cs:__imp_HeapFree
0x140108529  nop     dword ptr [rax+rax+00h]
0x14010852e  lea     rcx, [rsp+6B0h+var_670]
0x140108533  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x140108538  jmp     loc_1401083C4
0x14010853d  xor     ecx, ecx
0x14010853f  cmp     [rdi+4], ecx
0x140108542  jbe     short loc_140108562
0x140108544  mov     rdx, [rsi]
0x140108547  lea     rax, [rcx+rcx*8]
0x14010854b  inc     rcx
0x14010854e  shl     rax, 4
0x140108552  add     rdx, [rax+rdi+40h]
0x140108557  mov     [rsi], rdx
0x14010855a  mov     eax, [rdi+4]
0x14010855d  cmp     rcx, rax
0x140108560  jb      short loc_140108547
0x140108562  call    cs:__imp_GetProcessHeap
0x140108569  nop     dword ptr [rax+rax+00h]
0x14010856e  mov     r8, rdi; lpMem
0x140108571  xor     edx, edx; dwFlags
0x140108573  mov     rcx, rax; hHeap
0x140108576  call    cs:__imp_HeapFree
0x14010857d  nop     dword ptr [rax+rax+00h]
0x140108582  lea     rcx, [rsp+6B0h+var_670]
0x140108587  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14010858c  xor     eax, eax
0x14010858e  mov     rcx, [rbp+5B0h+var_20]
0x140108595  xor     rcx, rsp; StackCookie
0x140108598  call    __security_check_cookie
0x14010859d  lea     r11, [rsp+6B0h+var_10]
0x1401085a5  mov     rbx, [r11+30h]
0x1401085a9  mov     rsi, [r11+38h]
0x1401085ad  mov     rsp, r11
0x1401085b0  pop     r15
0x1401085b2  pop     rdi
0x1401085b3  pop     rbp
0x1401085b4  retn
```
