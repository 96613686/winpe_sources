# TSPI_providerInit

- ea: `0x1800077c0`
- end: `0x180007c1a`
- name: `TSPI_providerInit`
- size: `1114`
- prototype: `LONG __stdcall(DWORD dwTSPIVersion, DWORD dwPermanentProviderID, DWORD dwLineDeviceIDBase, DWORD dwPhoneDeviceIDBase, DWORD_PTR dwNumLines, DWORD_PTR dwNumPhones, ASYNC_COMPLETION lpfnCompletionProc, LPDWORD lpdwTSPIOptions)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001400`
- `0x180002080`
- `0x180002600`
- `0x1800029dc`
- `0x1800077c0`
- `0x180007df8`

## import_xrefs

- `KERNEL32!CreateIoCompletionPort` at `0x18000794f`
- `KERNEL32!CreateIoCompletionPort` at `0x18000794f`
- `KERNEL32!CreateThread` at `0x180007ae2`
- `KERNEL32!CreateThread` at `0x180007ae2`
- `KERNEL32!DefineDosDeviceA` at `0x180007870`
- `KERNEL32!DefineDosDeviceA` at `0x180007bd4`
- `KERNEL32!DefineDosDeviceA` at `0x180007870`
- `KERNEL32!DefineDosDeviceA` at `0x180007bd4`
- `KERNEL32!CreateFileA` at `0x1800078a1`
- `KERNEL32!CreateFileA` at `0x180007905`
- `KERNEL32!CreateFileA` at `0x1800078a1`
- `KERNEL32!CreateFileA` at `0x180007905`
- `KERNEL32!GetLastError` at `0x1800078ba`
- `KERNEL32!GetLastError` at `0x18000791e`
- `KERNEL32!GetLastError` at `0x180007968`
- `KERNEL32!GetLastError` at `0x180007afd`
- `KERNEL32!GetLastError` at `0x180007b6e`
- `KERNEL32!GetLastError` at `0x1800078ba`
- `KERNEL32!GetLastError` at `0x18000791e`
- `KERNEL32!GetLastError` at `0x180007968`
- `KERNEL32!GetLastError` at `0x180007afd`
- `KERNEL32!GetLastError` at `0x180007b6e`
- `KERNEL32!DeviceIoControl` at `0x1800079c5`
- `KERNEL32!DeviceIoControl` at `0x1800079c5`
- `KERNEL32!LocalFree` at `0x180007b25`
- `KERNEL32!LocalFree` at `0x180007b38`
- `KERNEL32!LocalFree` at `0x180007b25`
- `KERNEL32!LocalFree` at `0x180007b38`
- `KERNEL32!CloseHandle` at `0x180007b92`
- `KERNEL32!CloseHandle` at `0x180007ba5`
- `KERNEL32!CloseHandle` at `0x180007bb8`
- `KERNEL32!CloseHandle` at `0x180007b92`
- `KERNEL32!CloseHandle` at `0x180007ba5`
- `KERNEL32!CloseHandle` at `0x180007bb8`
- `KERNEL32!LocalAlloc` at `0x180007a65`
- `KERNEL32!LocalAlloc` at `0x180007a9a`
- `KERNEL32!LocalAlloc` at `0x180007a65`
- `KERNEL32!LocalAlloc` at `0x180007a9a`
- `KERNEL32!InitializeCriticalSection` at `0x180007a06`
- `KERNEL32!InitializeCriticalSection` at `0x180007a20`
- `KERNEL32!InitializeCriticalSection` at `0x180007a41`
- `KERNEL32!InitializeCriticalSection` at `0x180007a06`
- `KERNEL32!InitializeCriticalSection` at `0x180007a20`
- `KERNEL32!InitializeCriticalSection` at `0x180007a41`

## string_xrefs

- `0x1800078cf`: `providerInit: CreateFile(%s, sync) failed(%ld)`
- `0x180007933`: `providerInit: CreateFile(%s, async) failed(%ld)`
- `0x180007974`: `providerInit: CreateIoCompletionPort failed(%ld)`
- `0x180007a7d`: `providerInit: failed to alloc thread info`
- `0x180007b09`: `providerInit: CreateThread failed(%ld)`

## pseudocode

```c
LONG __stdcall TSPI_providerInit(
        DWORD dwTSPIVersion,
        DWORD dwPermanentProviderID,
        DWORD dwLineDeviceIDBase,
        DWORD dwPhoneDeviceIDBase,
        DWORD_PTR dwNumLines,
        DWORD_PTR dwNumPhones,
        ASYNC_COMPLETION lpfnCompletionProc,
        LPDWORD lpdwTSPIOptions)
{
  DWORD LastError; // eax
  HANDLE FileA; // rax
  DWORD v11; // eax
  DWORD v12; // eax
  _DWORD *v13; // rax
  HLOCAL v14; // rax
  HANDLE v15; // rax
  DWORD v16; // eax
  LONG v17; // ebx
  DWORD v18; // eax
  DWORD BytesReturned; // [rsp+40h] [rbp-49h] BYREF
  _DWORD OutBuffer[2]; // [rsp+48h] [rbp-41h] BYREF
  DWORD ThreadId; // [rsp+50h] [rbp-39h] BYREF
  CHAR FileName[16]; // [rsp+58h] [rbp-31h] BYREF
  CHAR DeviceName[16]; // [rsp+68h] [rbp-21h] BYREF
  CHAR TargetPath[24]; // [rsp+78h] [rbp-11h] BYREF

  strcpy(DeviceName, "NDISTAPI");
  strcpy(TargetPath, "\\Device\\NdisTapi");
  strcpy(FileName, "\\\\.\\NDISTAPI");
  BytesReturned = 0;
  ThreadId = 0;
  TspLog(8, "providerInit: perfProvID(%x), lineDevIDBase(%x)", dwPermanentProviderID, dwLineDeviceIDBase);
  *lpdwTSPIOptions = 0;
  DefineDosDeviceA(1u, DeviceName, TargetPath);
  ghDriverSync = CreateFileA(FileName, 0xC0000000, 3u, 0, 3u, 0x80u, 0);
  if ( ghDriverSync == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    TspLog(1, "providerInit: CreateFile(%s, sync) failed(%ld)", FileName, LastError);
LABEL_23:
    v17 = -2147483576;
    DefineDosDeviceA(2u, DeviceName, 0);
    goto LABEL_24;
  }
  FileA = CreateFileA(FileName, 0xC0000000, 3u, 0, 3u, 0x40000080u, 0);
  ghDriverAsync = FileA;
  if ( FileA == (HANDLE)-1LL )
  {
    v11 = GetLastError();
    TspLog(1, "providerInit: CreateFile(%s, async) failed(%ld)", FileName, v11);
LABEL_22:
    CloseHandle(ghDriverSync);
    goto LABEL_23;
  }
  ghCompletionPort = CreateIoCompletionPort(FileA, 0, 0, 0);
  if ( ghCompletionPort == (HANDLE)-1LL )
  {
    v12 = GetLastError();
    TspLog(1, "providerInit: CreateIoCompletionPort failed(%ld)", v12);
LABEL_21:
    CloseHandle(ghDriverAsync);
    goto LABEL_22;
  }
  OutBuffer[0] = dwLineDeviceIDBase;
  OutBuffer[1] = 1;
  if ( !DeviceIoControl(ghDriverSync, 0x8FFF23C0, OutBuffer, 8u, OutBuffer, 8u, &BytesReturned, 0) || BytesReturned < 4 )
  {
    v18 = GetLastError();
    TspLog(1, "providerInit: CONNECT failed(%ld)", v18);
    goto LABEL_20;
  }
  if ( (unsigned int)InitializeMapper() )
  {
LABEL_20:
    CloseHandle(ghCompletionPort);
    goto LABEL_21;
  }
  TspLog(8, "InitAllocator: entering...");
  InitializeCriticalSection(&stru_18000E350);
  qword_18000E348 = 0;
  InitializeCriticalSection(&stru_18000E388);
  LODWORD(Size) = 0;
  qword_18000E380 = 0;
  InitializeCriticalSection(&stru_18000E320);
  LODWORD(dword_18000E310) = 0;
  qword_18000E318 = 0;
  v13 = LocalAlloc(0x40u, 0x18u);
  gpAsyncEventsThreadInfo = v13;
  if ( !v13 )
  {
    TspLog(1, "providerInit: failed to alloc thread info");
LABEL_17:
    UninitAllocator();
    UninitializeMapper();
    goto LABEL_20;
  }
  v13[4] = 1024;
  v14 = LocalAlloc(0x40u, 0x400u);
  *((_QWORD *)gpAsyncEventsThreadInfo + 1) = v14;
  if ( !v14 )
  {
    TspLog(1, "providerInit: failed to alloc event buf");
LABEL_16:
    LocalFree(gpAsyncEventsThreadInfo);
    goto LABEL_17;
  }
  v15 = CreateThread(0, 0, AsyncEventsThread, 0, 0, &ThreadId);
  *(_QWORD *)gpAsyncEventsThreadInfo = v15;
  if ( !v15 )
  {
    v16 = GetLastError();
    TspLog(1, "providerInit: CreateThread failed(%ld)", v16);
    LocalFree(*((HLOCAL *)gpAsyncEventsThreadInfo + 1));
    goto LABEL_16;
  }
  *(_DWORD *)dwNumLines = OutBuffer[0];
  gdwRequestID = 1;
  v17 = 0;
  gpfnCompletionProc = (__int64)lpfnCompletionProc;
  *(_DWORD *)dwNumPhones = 0;
LABEL_24:
  TspLog(4, "providerInit: lRes(%x)", v17);
  return v17;
}

```

## disassembly

```asm
0x1800077c0  mov     [rsp-8+arg_0], rbx
0x1800077c5  push    rbp
0x1800077c6  push    rsi
0x1800077c7  push    rdi
0x1800077c8  push    r14
0x1800077ca  push    r15
0x1800077cc  lea     rbp, [rsp-17h]
0x1800077d1  sub     rsp, 0A0h
0x1800077d8  mov     rax, cs:__security_cookie
0x1800077df  xor     rax, rsp
0x1800077e2  mov     [rbp+37h+var_30], rax
0x1800077e6  mov     al, byte ptr cs:aNdistapi_0+8; ""
0x1800077ec  xor     r15d, r15d
0x1800077ef  movsd   xmm0, qword ptr cs:aNdistapi_0; "NDISTAPI"
0x1800077f7  mov     edi, r8d
0x1800077fa  mov     rsi, [rbp+37h+dwNumLines]
0x1800077fe  mov     r9d, r8d
0x180007801  mov     r14, [rbp+37h+dwNumPhones]
0x180007805  mov     r8d, edx
0x180007808  mov     rbx, [rbp+37h+lpdwTSPIOptions]
0x18000780c  lea     rdx, aProviderinitPe; "providerInit: perfProvID(%x), lineDevID"...
0x180007813  mov     [rbp+37h+var_50], al
0x180007816  lea     ecx, [r15+8]
0x18000781a  mov     al, byte ptr cs:aDeviceNdistapi+10h; ""
0x180007820  movsd   qword ptr [rbp+37h+DeviceName], xmm0
0x180007825  movups  xmm0, xmmword ptr cs:aDeviceNdistapi; "\\Device\\NdisTapi"
0x18000782c  mov     [rbp+37h+var_38], al
0x18000782f  mov     eax, dword ptr cs:aNdistapi+8; "TAPI"
0x180007835  movups  xmmword ptr [rbp+37h+TargetPath], xmm0
0x180007839  mov     dword ptr [rbp+37h+var_60], eax
0x18000783c  movsd   xmm0, qword ptr cs:aNdistapi; "\\\\.\\NDISTAPI"
0x180007844  mov     al, byte ptr cs:aNdistapi+0Ch; ""
0x18000784a  movsd   qword ptr [rbp+37h+FileName], xmm0
0x18000784f  mov     [rbp+37h+var_60+4], al
0x180007852  mov     [rbp+37h+BytesReturned], r15d
0x180007856  mov     [rbp+37h+ThreadId], r15d
0x18000785a  call    TspLog
0x18000785f  mov     [rbx], r15d
0x180007862  lea     r8, [rbp+37h+TargetPath]; lpTargetPath
0x180007866  lea     ebx, [r15+1]
0x18000786a  mov     ecx, ebx; dwFlags
0x18000786c  lea     rdx, [rbp+37h+DeviceName]; lpDeviceName
0x180007870  call    cs:__imp_DefineDosDeviceA
0x180007877  nop     dword ptr [rax+rax+00h]
0x18000787c  mov     [rsp+0C0h+hTemplateFile], r15; hTemplateFile
0x180007881  lea     r8d, [r15+3]; dwShareMode
0x180007885  mov     [rsp+0C0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18000788d  lea     rcx, [rbp+37h+FileName]; lpFileName
0x180007891  xor     r9d, r9d; lpSecurityAttributes
0x180007894  mov     [rsp+0C0h+dwCreationDisposition], 3; dwCreationDisposition
0x18000789c  mov     edx, 0C0000000h; dwDesiredAccess
0x1800078a1  call    cs:__imp_CreateFileA
0x1800078a8  nop     dword ptr [rax+rax+00h]
0x1800078ad  mov     cs:ghDriverSync, rax
0x1800078b4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800078b8  jnz     short loc_1800078E0
0x1800078ba  call    cs:__imp_GetLastError
0x1800078c1  nop     dword ptr [rax+rax+00h]
0x1800078c6  lea     r8, [rbp+37h+FileName]
0x1800078ca  mov     ecx, ebx
0x1800078cc  mov     r9d, eax
0x1800078cf  lea     rdx, aProviderinitCr_1; "providerInit: CreateFile(%s, sync) fail"...
0x1800078d6  call    TspLog
0x1800078db  jmp     loc_180007BC4
0x1800078e0  xor     r9d, r9d; lpSecurityAttributes
0x1800078e3  mov     [rsp+0C0h+hTemplateFile], r15; hTemplateFile
0x1800078e8  mov     [rsp+0C0h+dwFlagsAndAttributes], 40000080h; dwFlagsAndAttributes
0x1800078f0  lea     rcx, [rbp+37h+FileName]; lpFileName
0x1800078f4  mov     edx, 0C0000000h; dwDesiredAccess
0x1800078f9  mov     [rsp+0C0h+dwCreationDisposition], 3; dwCreationDisposition
0x180007901  lea     r8d, [r9+3]; dwShareMode
0x180007905  call    cs:__imp_CreateFileA
0x18000790c  nop     dword ptr [rax+rax+00h]
0x180007911  mov     cs:ghDriverAsync, rax
0x180007918  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000791c  jnz     short loc_180007944
0x18000791e  call    cs:__imp_GetLastError
0x180007925  nop     dword ptr [rax+rax+00h]
0x18000792a  lea     r8, [rbp+37h+FileName]
0x18000792e  mov     ecx, ebx
0x180007930  mov     r9d, eax
0x180007933  lea     rdx, aProviderinitCr; "providerInit: CreateFile(%s, async) fai"...
0x18000793a  call    TspLog
0x18000793f  jmp     loc_180007BB1
0x180007944  xor     r9d, r9d; NumberOfConcurrentThreads
0x180007947  xor     r8d, r8d; CompletionKey
0x18000794a  xor     edx, edx; ExistingCompletionPort
0x18000794c  mov     rcx, rax; FileHandle
0x18000794f  call    cs:__imp_CreateIoCompletionPort
0x180007956  nop     dword ptr [rax+rax+00h]
0x18000795b  mov     cs:ghCompletionPort, rax
0x180007962  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180007966  jnz     short loc_18000798A
0x180007968  call    cs:__imp_GetLastError
0x18000796f  nop     dword ptr [rax+rax+00h]
0x180007974  lea     rdx, aProviderinitCr_0; "providerInit: CreateIoCompletionPort fa"...
0x18000797b  mov     ecx, ebx
0x18000797d  mov     r8d, eax
0x180007980  call    TspLog
0x180007985  jmp     loc_180007B9E
0x18000798a  mov     rcx, cs:ghDriverSync; hDevice
0x180007991  lea     rax, [rbp+37h+BytesReturned]
0x180007995  mov     [rsp+0C0h+lpOverlapped], r15; lpOverlapped
0x18000799a  lea     r8, [rbp+37h+OutBuffer]; lpInBuffer
0x18000799e  mov     [rsp+0C0h+hTemplateFile], rax; lpBytesReturned
0x1800079a3  mov     r9d, 8; nInBufferSize
0x1800079a9  lea     rax, [rbp+37h+OutBuffer]
0x1800079ad  mov     [rsp+0C0h+dwFlagsAndAttributes], 8; nOutBufferSize
0x1800079b5  mov     edx, 8FFF23C0h; dwIoControlCode
0x1800079ba  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rax; lpOutBuffer
0x1800079bf  mov     [rbp+37h+OutBuffer], edi
0x1800079c2  mov     [rbp+37h+var_74], ebx
0x1800079c5  call    cs:__imp_DeviceIoControl
0x1800079cc  nop     dword ptr [rax+rax+00h]
0x1800079d1  test    eax, eax
0x1800079d3  jz      loc_180007B6E
0x1800079d9  cmp     [rbp+37h+BytesReturned], 4
0x1800079dd  jb      loc_180007B6E
0x1800079e3  call    InitializeMapper
0x1800079e8  test    eax, eax
0x1800079ea  jnz     loc_180007B8B
0x1800079f0  lea     rdx, aInitallocatorE; "InitAllocator: entering..."
0x1800079f7  lea     ecx, [rax+8]
0x1800079fa  call    TspLog
0x1800079ff  lea     rcx, stru_18000E350; lpCriticalSection
0x180007a06  call    cs:__imp_InitializeCriticalSection
0x180007a0d  nop     dword ptr [rax+rax+00h]
0x180007a12  lea     rcx, stru_18000E388; lpCriticalSection
0x180007a19  mov     cs:qword_18000E348, r15
0x180007a20  call    cs:__imp_InitializeCriticalSection
0x180007a27  nop     dword ptr [rax+rax+00h]
0x180007a2c  lea     rcx, stru_18000E320; lpCriticalSection
0x180007a33  mov     cs:Size, r15d
0x180007a3a  mov     cs:qword_18000E380, r15
0x180007a41  call    cs:__imp_InitializeCriticalSection
0x180007a48  nop     dword ptr [rax+rax+00h]
0x180007a4d  mov     edx, 18h; uBytes
0x180007a52  mov     cs:dword_18000E310, r15d
0x180007a59  mov     cs:qword_18000E318, r15
0x180007a60  lea     edi, [rdx+28h]
0x180007a63  mov     ecx, edi; uFlags
0x180007a65  call    cs:__imp_LocalAlloc
0x180007a6c  nop     dword ptr [rax+rax+00h]
0x180007a71  mov     cs:gpAsyncEventsThreadInfo, rax
0x180007a78  test    rax, rax
0x180007a7b  jnz     short loc_180007A90
0x180007a7d  lea     rdx, aProviderinitFa_0; "providerInit: failed to alloc thread in"...
0x180007a84  mov     ecx, ebx
0x180007a86  call    TspLog
0x180007a8b  jmp     loc_180007B44
0x180007a90  mov     edx, 400h; uBytes
0x180007a95  mov     ecx, edi; uFlags
0x180007a97  mov     [rax+10h], edx
0x180007a9a  call    cs:__imp_LocalAlloc
0x180007aa1  nop     dword ptr [rax+rax+00h]
0x180007aa6  mov     rcx, cs:gpAsyncEventsThreadInfo
0x180007aad  mov     [rcx+8], rax
0x180007ab1  test    rax, rax
0x180007ab4  jnz     short loc_180007AC6
0x180007ab6  lea     rdx, aProviderinitFa; "providerInit: failed to alloc event buf"
0x180007abd  mov     ecx, ebx
0x180007abf  call    TspLog
0x180007ac4  jmp     short loc_180007B31
0x180007ac6  lea     rax, [rbp+37h+ThreadId]
0x180007aca  xor     r9d, r9d; lpParameter
0x180007acd  mov     qword ptr [rsp+0C0h+dwFlagsAndAttributes], rax; lpThreadId
0x180007ad2  lea     r8, AsyncEventsThread; lpStartAddress
0x180007ad9  xor     edx, edx; dwStackSize
0x180007adb  mov     [rsp+0C0h+dwCreationDisposition], r15d; dwCreationFlags
0x180007ae0  xor     ecx, ecx; lpThreadAttributes
0x180007ae2  call    cs:__imp_CreateThread
0x180007ae9  nop     dword ptr [rax+rax+00h]
0x180007aee  mov     rcx, cs:gpAsyncEventsThreadInfo
0x180007af5  mov     [rcx], rax
0x180007af8  test    rax, rax
0x180007afb  jnz     short loc_180007B50
0x180007afd  call    cs:__imp_GetLastError
0x180007b04  nop     dword ptr [rax+rax+00h]
0x180007b09  lea     rdx, aProviderinitCr_2; "providerInit: CreateThread failed(%ld)"
0x180007b10  mov     ecx, ebx
0x180007b12  mov     r8d, eax
0x180007b15  call    TspLog
0x180007b1a  mov     rcx, cs:gpAsyncEventsThreadInfo
0x180007b21  mov     rcx, [rcx+8]; hMem
0x180007b25  call    cs:__imp_LocalFree
0x180007b2c  nop     dword ptr [rax+rax+00h]
0x180007b31  mov     rcx, cs:gpAsyncEventsThreadInfo; hMem
0x180007b38  call    cs:__imp_LocalFree
0x180007b3f  nop     dword ptr [rax+rax+00h]
0x180007b44  call    UninitAllocator
0x180007b49  call    UninitializeMapper
0x180007b4e  jmp     short loc_180007B8B
0x180007b50  mov     eax, [rbp+37h+OutBuffer]
0x180007b53  mov     [rsi], eax
0x180007b55  mov     rax, [rbp+37h+lpfnCompletionProc]
0x180007b59  mov     cs:gdwRequestID, ebx
0x180007b5f  mov     ebx, r15d
0x180007b62  mov     cs:gpfnCompletionProc, rax
0x180007b69  mov     [r14], r15d
0x180007b6c  jmp     short loc_180007BE0
0x180007b6e  call    cs:__imp_GetLastError
0x180007b75  nop     dword ptr [rax+rax+00h]
0x180007b7a  lea     rdx, aProviderinitCo; "providerInit: CONNECT failed(%ld)"
0x180007b81  mov     ecx, ebx
0x180007b83  mov     r8d, eax
0x180007b86  call    TspLog
0x180007b8b  mov     rcx, cs:ghCompletionPort; hObject
0x180007b92  call    cs:__imp_CloseHandle
0x180007b99  nop     dword ptr [rax+rax+00h]
0x180007b9e  mov     rcx, cs:ghDriverAsync; hObject
0x180007ba5  call    cs:__imp_CloseHandle
0x180007bac  nop     dword ptr [rax+rax+00h]
0x180007bb1  mov     rcx, cs:ghDriverSync; hObject
0x180007bb8  call    cs:__imp_CloseHandle
0x180007bbf  nop     dword ptr [rax+rax+00h]
0x180007bc4  xor     r8d, r8d; lpTargetPath
0x180007bc7  lea     rdx, [rbp+37h+DeviceName]; lpDeviceName
0x180007bcb  mov     ebx, 80000048h
0x180007bd0  lea     ecx, [r8+2]; dwFlags
0x180007bd4  call    cs:__imp_DefineDosDeviceA
0x180007bdb  nop     dword ptr [rax+rax+00h]
0x180007be0  mov     r8d, ebx
0x180007be3  lea     rdx, aProviderinitLr; "providerInit: lRes(%x)"
0x180007bea  mov     ecx, 4
0x180007bef  call    TspLog
0x180007bf4  mov     eax, ebx
0x180007bf6  mov     rcx, [rbp+37h+var_30]
0x180007bfa  xor     rcx, rsp; StackCookie
0x180007bfd  call    __security_check_cookie
0x180007c02  mov     rbx, [rsp+0C0h+arg_0]
0x180007c0a  add     rsp, 0A0h
0x180007c11  pop     r15
0x180007c13  pop     r14
0x180007c15  pop     rdi
0x180007c16  pop     rsi
0x180007c17  pop     rbp
0x180007c18  retn
```
