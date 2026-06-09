# IsFileOnClusterSharedVolume

- ea: `0x18002e8c0`
- end: `0x18002e9e7`
- name: `IsFileOnClusterSharedVolume`
- size: `295`
- prototype: `DWORD __stdcall(LPCWSTR lpszPathName, PBOOL pbFileIsOnSharedVolume)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x18002e8c0`
- `0x18006f910`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e920`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e98b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e920`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e98b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e9cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e9cf`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002e911`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002e911`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18002e981`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18002e981`

## string_xrefs

- `0x18002e941`: `Cannot open file %ws, error %d.`

## pseudocode

```c
DWORD __stdcall IsFileOnClusterSharedVolume(LPCWSTR lpszPathName, PBOOL pbFileIsOnSharedVolume)
{
  HANDLE FileW; // rsi
  DWORD v5; // ebx
  DWORD v7; // edi
  LPDWORD lpBytesReturned; // [rsp+30h] [rbp-38h]
  LPDWORD lpBytesReturneda; // [rsp+30h] [rbp-38h]
  DWORD BytesReturned; // [rsp+70h] [rbp+8h] BYREF

  BytesReturned = 0;
  if ( !lpszPathName || !*lpszPathName || !pbFileIsOnSharedVolume )
    return 87;
  *pbFileIsOnSharedVolume = 0;
  FileW = CreateFileW(lpszPathName, 0x100000u, 7u, 0, 3u, 0x2000000u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LODWORD(lpBytesReturned) = GetLastError();
    v5 = (unsigned int)lpBytesReturned;
    TraceMsg(
      2u,
      0,
      (__int64)L"IsFileOnClusterSharedVolume",
      6542,
      L"Cannot open file %ws, error %d.",
      lpszPathName,
      lpBytesReturned);
    return v5;
  }
  else
  {
    if ( DeviceIoControl(FileW, 0x90248u, 0, 0, 0, 0, &BytesReturned, 0) )
    {
      v7 = 0;
      *pbFileIsOnSharedVolume = 1;
    }
    else
    {
      LODWORD(lpBytesReturneda) = GetLastError();
      TraceMsg(
        4u,
        0,
        (__int64)L"IsFileOnClusterSharedVolume",
        6555,
        L"Failed DeviceIoControl on file %ws, error %d.",
        lpszPathName,
        lpBytesReturneda);
      v7 = 5945;
    }
    CloseHandle(FileW);
    return v7;
  }
}

```

## disassembly

```asm
0x18002e8c0  mov     rax, rsp
0x18002e8c3  push    rbx
0x18002e8c4  push    rbp
0x18002e8c5  push    rsi
0x18002e8c6  push    rdi
0x18002e8c7  sub     rsp, 48h
0x18002e8cb  xor     ebp, ebp
0x18002e8cd  mov     rbx, rdx
0x18002e8d0  mov     [rax+8], ebp
0x18002e8d3  mov     rdi, rcx
0x18002e8d6  test    rcx, rcx
0x18002e8d9  jz      loc_18002E9D9
0x18002e8df  cmp     [rcx], bp
0x18002e8e2  jz      loc_18002E9D9
0x18002e8e8  test    rdx, rdx
0x18002e8eb  jz      loc_18002E9D9
0x18002e8f1  mov     [rax-38h], rbp
0x18002e8f5  lea     r8d, [rbp+7]; dwShareMode
0x18002e8f9  mov     [rdx], ebp
0x18002e8fb  xor     r9d, r9d; lpSecurityAttributes
0x18002e8fe  mov     dword ptr [rax-40h], 2000000h
0x18002e905  mov     edx, 100000h; dwDesiredAccess
0x18002e90a  mov     dword ptr [rax-48h], 3
0x18002e911  call    cs:__imp_CreateFileW
0x18002e917  mov     rsi, rax
0x18002e91a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002e91e  jnz     short loc_18002E95B
0x18002e920  call    cs:__imp_GetLastError
0x18002e926  mov     dword ptr [rsp+68h+lpBytesReturned], eax
0x18002e92a  mov     r9d, 198Eh
0x18002e930  mov     qword ptr [rsp+68h+nOutBufferSize], rdi
0x18002e935  lea     r8, aIsfileoncluste_0; "IsFileOnClusterSharedVolume"
0x18002e93c  mov     ebx, eax
0x18002e93e  lea     ecx, [rbp+2]
0x18002e941  lea     rax, aCannotOpenFile; "Cannot open file %ws, error %d."
0x18002e948  xor     edx, edx
0x18002e94a  mov     [rsp+68h+lpOutBuffer], rax
0x18002e94f  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18002e954  mov     eax, ebx
0x18002e956  jmp     loc_18002E9DE
0x18002e95b  mov     [rsp+68h+lpOverlapped], rbp; lpOverlapped
0x18002e960  lea     rax, [rsp+68h+BytesReturned]
0x18002e965  mov     [rsp+68h+lpBytesReturned], rax; lpBytesReturned
0x18002e96a  xor     r9d, r9d; nInBufferSize
0x18002e96d  mov     [rsp+68h+nOutBufferSize], ebp; nOutBufferSize
0x18002e971  xor     r8d, r8d; lpInBuffer
0x18002e974  mov     edx, 90248h; dwIoControlCode
0x18002e979  mov     [rsp+68h+lpOutBuffer], rbp; lpOutBuffer
0x18002e97e  mov     rcx, rsi; hDevice
0x18002e981  call    cs:__imp_DeviceIoControl
0x18002e987  test    eax, eax
0x18002e989  jnz     short loc_18002E9C4
0x18002e98b  call    cs:__imp_GetLastError
0x18002e991  mov     dword ptr [rsp+68h+lpBytesReturned], eax
0x18002e995  xor     edx, edx
0x18002e997  mov     qword ptr [rsp+68h+nOutBufferSize], rdi
0x18002e99c  lea     r8, aIsfileoncluste_0; "IsFileOnClusterSharedVolume"
0x18002e9a3  lea     rax, aFailedDeviceio; "Failed DeviceIoControl on file %ws, err"...
0x18002e9aa  mov     r9d, 199Bh
0x18002e9b0  mov     [rsp+68h+lpOutBuffer], rax
0x18002e9b5  lea     ecx, [rdx+4]
0x18002e9b8  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18002e9bd  mov     edi, 1739h
0x18002e9c2  jmp     short loc_18002E9CC
0x18002e9c4  mov     edi, ebp
0x18002e9c6  mov     dword ptr [rbx], 1
0x18002e9cc  mov     rcx, rsi; hObject
0x18002e9cf  call    cs:__imp_CloseHandle
0x18002e9d5  mov     eax, edi
0x18002e9d7  jmp     short loc_18002E9DE
0x18002e9d9  mov     eax, 57h ; 'W'
0x18002e9de  add     rsp, 48h
0x18002e9e2  pop     rdi
0x18002e9e3  pop     rsi
0x18002e9e4  pop     rbp
0x18002e9e5  pop     rbx
0x18002e9e6  retn
```
