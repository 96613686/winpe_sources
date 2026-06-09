# udk::CopilotPlusDetection::_GetPhysicalDiskSize(ushort const *,_ULARGE_INTEGER *)

- ea: `0x18002435c`
- end: `0x18002467e`
- name: `?_GetPhysicalDiskSize@CopilotPlusDetection@udk@@YAJPEBGPEAT_ULARGE_INTEGER@@@Z`
- size: `802`
- prototype: `__int64 __fastcall(LPCWSTR lpszFileName, const unsigned __int16 *, union _ULARGE_INTEGER *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path, registry_config`

## callers

- `0x180075bc4`

## callees

- `0x180017988`
- `0x1800179ac`
- `0x18001a100`
- `0x18002435c`
- `0x18002a3d0`
- `0x18002a910`
- `0x18002af50`
- `0x180077f40`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180024570`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180024570`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800245fd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024645`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800245fd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024645`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002455c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800245ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024637`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002455c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800245ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024637`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024427`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024530`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024427`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024530`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002441d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002441d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180024517`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180024517`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1800243d4`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x180024453`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1800243d4`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x180024453`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180024473`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180024473`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800245cb`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800245cb`

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
               (unsigned int)"OneCore\\Internal\\Shell\\inc\\CopilotPlusPCDetection.h",
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
               (unsigned int)"OneCore\\Internal\\Shell\\inc\\CopilotPlusPCDetection.h",
               v5);
    }
  }
  if ( !GetVolumeNameForVolumeMountPointW(szVolumePathName, szVolumeName, 0x104u) )
  {
    v6 = 426;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v6,
             (unsigned int)"OneCore\\Internal\\Shell\\inc\\CopilotPlusPCDetection.h",
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
      (unsigned int)"OneCore\\Internal\\Shell\\inc\\CopilotPlusPCDetection.h",
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
      (unsigned int)"OneCore\\Internal\\Shell\\inc\\CopilotPlusPCDetection.h",
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
           (unsigned int)"OneCore\\Internal\\Shell\\inc\\CopilotPlusPCDetection.h",
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
0x18002435c  mov     [rsp-8+arg_10], rbx
0x180024361  mov     [rsp-8+arg_18], rsi
0x180024366  push    rbp
0x180024367  push    rdi
0x180024368  push    r15
0x18002436a  lea     rbp, [rsp-5A0h]
0x180024372  sub     rsp, 6A0h
0x180024379  mov     rax, cs:__security_cookie
0x180024380  xor     rax, rsp
0x180024383  mov     [rbp+5B0h+var_20], rax
0x18002438a  mov     rsi, rdx
0x18002438d  mov     qword ptr [rdx], 0
0x180024394  mov     rdi, rcx
0x180024397  mov     r15d, 208h
0x18002439d  mov     r8d, r15d; Size
0x1800243a0  lea     rcx, [rsp+6B0h+szVolumeName]; void *
0x1800243a5  xor     edx, edx; Val
0x1800243a7  call    memset_0
0x1800243ac  mov     r8d, r15d; Size
0x1800243af  lea     rcx, [rbp+5B0h+szVolumePathName]; void *
0x1800243b6  xor     edx, edx; Val
0x1800243b8  call    memset_0
0x1800243bd  test    rdi, rdi
0x1800243c0  jz      short loc_1800243FE
0x1800243c2  mov     ebx, 104h
0x1800243c7  lea     rdx, [rbp+5B0h+szVolumePathName]; lpszVolumePathName
0x1800243ce  mov     r8d, ebx; cchBufferLength
0x1800243d1  mov     rcx, rdi; lpszFileName
0x1800243d4  call    cs:__imp_GetVolumePathNameW
0x1800243da  test    eax, eax
0x1800243dc  jnz     loc_180024464
0x1800243e2  lea     edx, [r15-6Bh]; void *
0x1800243e6  mov     rcx, [rbp+5B8h]; this
0x1800243ed  lea     r8, aOnecoreInterna_4; "OneCore\\Internal\\Shell\\inc\\CopilotP"...
0x1800243f4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800243f9  jmp     loc_180024657
0x1800243fe  mov     r8, r15; Size
0x180024401  lea     rcx, [rbp+5B0h+Buffer]; void *
0x180024408  xor     edx, edx; Val
0x18002440a  call    memset_0
0x18002440f  mov     ebx, 104h
0x180024414  lea     rcx, [rbp+5B0h+Buffer]; lpBuffer
0x18002441b  mov     edx, ebx; uSize
0x18002441d  call    cs:__imp_GetSystemDirectoryW
0x180024423  test    eax, eax
0x180024425  jnz     short loc_180024442
0x180024427  call    cs:__imp_GetLastError
0x18002442d  test    eax, eax
0x18002442f  jle     loc_180024657
0x180024435  movzx   eax, ax
0x180024438  or      eax, 80070000h
0x18002443d  jmp     loc_180024657
0x180024442  mov     r8d, ebx; cchBufferLength
0x180024445  lea     rdx, [rbp+5B0h+szVolumePathName]; lpszVolumePathName
0x18002444c  lea     rcx, [rbp+5B0h+Buffer]; lpszFileName
0x180024453  call    cs:__imp_GetVolumePathNameW
0x180024459  test    eax, eax
0x18002445b  jnz     short loc_180024464
0x18002445d  mov     edx, 1A7h
0x180024462  jmp     short loc_1800243E6
0x180024464  mov     r8d, ebx; cchBufferLength
0x180024467  lea     rdx, [rsp+6B0h+szVolumeName]; lpszVolumeName
0x18002446c  lea     rcx, [rbp+5B0h+szVolumePathName]; lpszVolumeMountPoint
0x180024473  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180024479  test    eax, eax
0x18002447b  jnz     short loc_180024487
0x18002447d  mov     edx, 1AAh
0x180024482  jmp     loc_1800243E6
0x180024487  lea     r8, [rsp+6B0h+var_670]; unsigned __int64 *
0x18002448c  mov     [rsp+6B0h+var_670], 0
0x180024495  mov     rdx, rbx; unsigned __int64
0x180024498  lea     rcx, [rsp+6B0h+szVolumeName]; unsigned __int16 *
0x18002449d  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800244a2  mov     ebx, eax
0x1800244a4  test    eax, eax
0x1800244a6  jns     short loc_1800244CA
0x1800244a8  mov     rcx, [rbp+5B8h]; this
0x1800244af  lea     r8, aOnecoreInterna_4; "OneCore\\Internal\\Shell\\inc\\CopilotP"...
0x1800244b6  mov     r9d, eax; char *
0x1800244b9  mov     edx, 1AEh; void *
0x1800244be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800244c3  mov     eax, ebx
0x1800244c5  jmp     loc_180024657
0x1800244ca  mov     rax, [rsp+6B0h+var_670]
0x1800244cf  test    rax, rax
0x1800244d2  jz      short loc_1800244F0
0x1800244d4  cmp     [rsp+rax*2+6B0h+var_652], 5Ch ; '\'
0x1800244da  jnz     short loc_1800244F0
0x1800244dc  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x1800244e4  cmp     rcx, r15
0x1800244e7  jnb     short loc_18002454E
0x1800244e9  xor     eax, eax
0x1800244eb  mov     [rsp+rcx+6B0h+szVolumeName], ax
0x1800244f0  xor     r9d, r9d; lpSecurityAttributes
0x1800244f3  mov     [rsp+6B0h+hTemplateFile], 0; hTemplateFile
0x1800244fc  mov     [rsp+6B0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x180024504  lea     rcx, [rsp+6B0h+szVolumeName]; lpFileName
0x180024509  xor     edx, edx; dwDesiredAccess
0x18002450b  mov     [rsp+6B0h+dwCreationDisposition], 3; int
0x180024513  lea     r8d, [r9+1]; dwShareMode
0x180024517  call    cs:__imp_CreateFileW
0x18002451d  mov     rbx, rax
0x180024520  mov     [rsp+6B0h+var_670], rax
0x180024525  inc     rax
0x180024528  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002452e  jnz     short loc_180024554
0x180024530  call    cs:__imp_GetLastError
0x180024536  mov     ebx, eax
0x180024538  test    eax, eax
0x18002453a  jle     loc_180024603
0x180024540  movzx   ebx, ax
0x180024543  or      ebx, 80070000h
0x180024549  jmp     loc_180024603
0x18002454e  call    __report_rangecheckfailure
0x180024554  mov     [rsp+6B0h+BytesReturned], 0
0x18002455c  call    cs:__imp_GetProcessHeap
0x180024562  mov     r15d, 48C0h
0x180024568  xor     edx, edx; dwFlags
0x18002456a  mov     rcx, rax; hHeap
0x18002456d  mov     r8d, r15d; dwBytes
0x180024570  call    cs:__imp_HeapAlloc
0x180024576  mov     rdi, rax
0x180024579  test    rax, rax
0x18002457c  jnz     short loc_1800245A0
0x18002457e  mov     rcx, [rbp+5B8h]; this
0x180024585  lea     r8, aOnecoreInterna_4; "OneCore\\Internal\\Shell\\inc\\CopilotP"...
0x18002458c  mov     ebx, 8007000Eh
0x180024591  mov     edx, 1BEh; void *
0x180024596  mov     r9d, ebx; char *
0x180024599  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002459e  jmp     short loc_180024603
0x1800245a0  mov     [rsp+6B0h+lpOverlapped], 0; lpOverlapped
0x1800245a9  lea     rax, [rsp+6B0h+BytesReturned]
0x1800245ae  mov     [rsp+6B0h+hTemplateFile], rax; lpBytesReturned
0x1800245b3  xor     r9d, r9d; nInBufferSize
0x1800245b6  mov     [rsp+6B0h+dwFlagsAndAttributes], r15d; nOutBufferSize
0x1800245bb  xor     r8d, r8d; lpInBuffer
0x1800245be  mov     edx, 70050h; dwIoControlCode
0x1800245c3  mov     qword ptr [rsp+6B0h+dwCreationDisposition], rdi; lpOutBuffer
0x1800245c8  mov     rcx, rbx; hDevice
0x1800245cb  call    cs:__imp_DeviceIoControl
0x1800245d1  test    eax, eax
0x1800245d3  jnz     short loc_180024612
0x1800245d5  mov     rcx, [rbp+5B8h]; this
0x1800245dc  lea     r8, aOnecoreInterna_4; "OneCore\\Internal\\Shell\\inc\\CopilotP"...
0x1800245e3  mov     edx, 1C4h; void *
0x1800245e8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800245ed  mov     ebx, eax
0x1800245ef  call    cs:__imp_GetProcessHeap
0x1800245f5  mov     r8, rdi; lpMem
0x1800245f8  xor     edx, edx; dwFlags
0x1800245fa  mov     rcx, rax; hHeap
0x1800245fd  call    cs:__imp_HeapFree
0x180024603  lea     rcx, [rsp+6B0h+var_670]
0x180024608  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002460d  jmp     loc_1800244C3
0x180024612  xor     ecx, ecx
0x180024614  cmp     [rdi+4], ecx
0x180024617  jbe     short loc_180024637
0x180024619  mov     rdx, [rsi]
0x18002461c  lea     rax, [rcx+rcx*8]
0x180024620  inc     rcx
0x180024623  shl     rax, 4
0x180024627  add     rdx, [rax+rdi+40h]
0x18002462c  mov     [rsi], rdx
0x18002462f  mov     eax, [rdi+4]
0x180024632  cmp     rcx, rax
0x180024635  jb      short loc_18002461C
0x180024637  call    cs:__imp_GetProcessHeap
0x18002463d  mov     r8, rdi; lpMem
0x180024640  xor     edx, edx; dwFlags
0x180024642  mov     rcx, rax; hHeap
0x180024645  call    cs:__imp_HeapFree
0x18002464b  lea     rcx, [rsp+6B0h+var_670]
0x180024650  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180024655  xor     eax, eax
0x180024657  mov     rcx, [rbp+5B0h+var_20]
0x18002465e  xor     rcx, rsp; StackCookie
0x180024661  call    __security_check_cookie
0x180024666  lea     r11, [rsp+6B0h+var_10]
0x18002466e  mov     rbx, [r11+30h]
0x180024672  mov     rsi, [r11+38h]
0x180024676  mov     rsp, r11
0x180024679  pop     r15
0x18002467b  pop     rdi
0x18002467c  pop     rbp
0x18002467d  retn
```
