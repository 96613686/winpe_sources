# TcpListener::CancelPendingIO(void)

- ea: `0x180026c20`
- end: `0x180026cf3`
- name: `?CancelPendingIO@TcpListener@@AEAAKXZ`
- size: `211`
- prototype: `unsigned int __fastcall(TcpListener *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180026d00`
- `0x18002758c`

## callees

- `0x180026c20`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180026cb4`
- `ntdll!RtlNtStatusToDosError` at `0x180026cb4`
- `ntdll!NtSetInformationFile` at `0x180026cac`
- `ntdll!NtSetInformationFile` at `0x180026cac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026cc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026cc0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026c45`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026c8c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026c45`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026c8c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026c78`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026ce2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026c78`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026ce2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x180026c83`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x180026c83`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x180026cd2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x180026cd2`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x180026c6f`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x180026c6f`

## pseudocode

```c
__int64 __fastcall TcpListener::CancelPendingIO(TcpListener *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbp
  DWORD LastError; // esi
  PTP_IO *v4; // rbx
  NTSTATUS v5; // eax
  __int128 FileInformation; // [rsp+30h] [rbp-48h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-38h] BYREF

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 40);
  LastError = 0;
  IoStatusBlock = 0;
  FileInformation = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)this + 1);
  v4 = (PTP_IO *)((char *)this + 832);
  *((_DWORD *)this + 218) = 1;
  if ( *((_DWORD *)this + 219)
    && (CancelIoEx(*((HANDLE *)this + 4), (LPOVERLAPPED)((char *)this + 840)),
        LeaveCriticalSection(v1),
        WaitForThreadpoolIoCallbacks(*v4, 0),
        EnterCriticalSection(v1),
        v5 = NtSetInformationFile(
               *((HANDLE *)this + 4),
               &IoStatusBlock,
               &FileInformation,
               0x10u,
               FileMaximumInformation|FileStandardInformation),
        (LastError = RtlNtStatusToDosError(v5)) != 0) )
  {
    LastError = GetLastError();
  }
  else if ( *v4 )
  {
    CloseThreadpoolIo(*v4);
    *v4 = 0;
  }
  LeaveCriticalSection(v1);
  return LastError;
}

```

## disassembly

```asm
0x180026c20  push    rbx
0x180026c22  push    rbp
0x180026c23  push    rsi
0x180026c24  push    rdi
0x180026c25  sub     rsp, 58h
0x180026c29  lea     rbp, [rcx+28h]
0x180026c2d  mov     rdi, rcx
0x180026c30  xorps   xmm0, xmm0
0x180026c33  xorps   xmm1, xmm1
0x180026c36  mov     rcx, rbp; lpCriticalSection
0x180026c39  xor     esi, esi
0x180026c3b  movups  xmmword ptr [rsp+78h+IoStatusBlock], xmm0
0x180026c40  movups  [rsp+78h+FileInformation], xmm1
0x180026c45  call    cs:__imp_EnterCriticalSection
0x180026c4b  lea     rbx, [rdi+340h]
0x180026c52  mov     dword ptr [rdi+368h], 1
0x180026c5c  cmp     [rdi+36Ch], esi
0x180026c62  jz      short loc_180026CCA
0x180026c64  mov     rcx, [rdi+20h]; hFile
0x180026c68  lea     rdx, [rdi+348h]; lpOverlapped
0x180026c6f  call    cs:__imp_CancelIoEx
0x180026c75  mov     rcx, rbp; lpCriticalSection
0x180026c78  call    cs:__imp_LeaveCriticalSection
0x180026c7e  mov     rcx, [rbx]; pio
0x180026c81  xor     edx, edx; fCancelPendingCallbacks
0x180026c83  call    cs:__imp_WaitForThreadpoolIoCallbacks
0x180026c89  mov     rcx, rbp; lpCriticalSection
0x180026c8c  call    cs:__imp_EnterCriticalSection
0x180026c92  mov     rcx, [rdi+20h]; FileHandle
0x180026c96  lea     r9d, [rsi+10h]; Length
0x180026c9a  lea     r8, [rsp+78h+FileInformation]; FileInformation
0x180026c9f  mov     [rsp+78h+FileInformationClass], 3Dh ; '='; FileInformationClass
0x180026ca7  lea     rdx, [rsp+78h+IoStatusBlock]; IoStatusBlock
0x180026cac  call    cs:__imp_NtSetInformationFile
0x180026cb2  mov     ecx, eax; Status
0x180026cb4  call    cs:__imp_RtlNtStatusToDosError
0x180026cba  mov     esi, eax
0x180026cbc  test    eax, eax
0x180026cbe  jz      short loc_180026CCA
0x180026cc0  call    cs:__imp_GetLastError
0x180026cc6  mov     esi, eax
0x180026cc8  jmp     short loc_180026CDF
0x180026cca  mov     rcx, [rbx]; pio
0x180026ccd  test    rcx, rcx
0x180026cd0  jz      short loc_180026CDF
0x180026cd2  call    cs:__imp_CloseThreadpoolIo
0x180026cd8  mov     qword ptr [rbx], 0
0x180026cdf  mov     rcx, rbp; lpCriticalSection
0x180026ce2  call    cs:__imp_LeaveCriticalSection
0x180026ce8  mov     eax, esi
0x180026cea  add     rsp, 58h
0x180026cee  pop     rdi
0x180026cef  pop     rsi
0x180026cf0  pop     rbp
0x180026cf1  pop     rbx
0x180026cf2  retn
```
