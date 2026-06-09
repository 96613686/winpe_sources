# FwpFlushCurrentBuffer(ulong)

- ea: `0x180058ba0`
- end: `0x180058dfc`
- name: `?FwpFlushCurrentBuffer@@YAKK@Z`
- size: `604`
- prototype: `unsigned int __fastcall(unsigned int)`
- caller_count: `4`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180051770`
- `0x180056b40`
- `0x18005ecb0`
- `0x180098d20`

## callees

- `0x1800089bc`
- `0x18000a710`
- `0x180058ba0`
- `0x1800729c0`
- `0x18007d3c8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058d03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058d03`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180058dd2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180058dd2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180058bcc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180058bcc`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180058cc6`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180058cc6`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180058d4a`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180058d4a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180058cf3`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180058cf3`

## pseudocode

```c
__int64 __fastcall FwpFlushCurrentBuffer(unsigned int a1)
{
  __int64 v1; // rbx
  DWORD v2; // esi
  int v3; // r8d
  __int64 v4; // rcx
  __int64 v5; // rdi
  struct _TP_IO *v6; // rcx
  DWORD v7; // ebx
  int v8; // r8d
  DWORD LastError; // eax
  struct _FW_LOG_BUFFER * near *v10; // rax
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-48h] BYREF

  v1 = a1;
  v2 = 0;
  NumberOfBytesWritten = 0;
  EnterCriticalSection(&g_FwFileLock);
  v4 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_ss(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 18, v3, (unsigned int)"FwpFlushCurrentBuffer", (__int64)"g_File");
  v5 = v1;
  if ( *((_BYTE *)&g_fIOPending + v1) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v4);
  if ( *(&g_pCurrentBuffer)[v1] )
    MicrosoftTelemetryAssertTriggeredNoArgs(v4);
  if ( (&g_pCurrentBuffer)[v1][1] )
    MicrosoftTelemetryAssertTriggeredNoArgs(v4);
  if ( *((_DWORD *)(&g_pCurrentBuffer)[v1] + 4) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v4);
  if ( *((_DWORD *)(&g_pCurrentBuffer)[v1] + 5) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v4);
  if ( (&g_pCurrentBuffer)[v1][3] )
    MicrosoftTelemetryAssertTriggeredNoArgs(v4);
  if ( (&g_hFile)[v1] == (void * near *)-1LL )
    MicrosoftTelemetryAssertTriggeredNoArgs(v4);
  *((_DWORD *)(&g_pCurrentBuffer)[v1] + 4) = *((_DWORD *)&g_dwFileOffset + v1);
  v6 = (struct _TP_IO *)(&g_TPFileIO)[v1];
  v7 = *((_DWORD *)(&g_pCurrentBuffer)[v1] + 8) - LODWORD((&g_pCurrentBuffer)[v1]) - 40;
  StartThreadpoolIo(v6);
  if ( WriteFile(
         (&g_hFile)[v5],
         (&g_pCurrentBuffer)[v5] + 5,
         v7,
         &NumberOfBytesWritten,
         (LPOVERLAPPED)(&g_pCurrentBuffer)[v5])
    || (LastError = GetLastError(), v2 = LastError, LastError == 997) )
  {
    (&g_pCurrentBuffer)[v5] = (&g_pReserveBuffer)[v5];
    *((_BYTE *)&g_fIOPending + v5) = 1;
    (&g_pReserveBuffer)[v5] = 0;
  }
  else
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 24, WPP_3d59fee1d00932d8b651bda1e8e67a3f_Traceguids, LastError);
    CancelThreadpoolIo((PTP_IO)(&g_TPFileIO)[v5]);
    v10 = (&g_pCurrentBuffer)[v5];
    *(_OWORD *)v10 = 0;
    *((_OWORD *)v10 + 1) = 0;
    (&g_pCurrentBuffer)[v5][4] = (struct _FW_LOG_BUFFER *)((&g_pCurrentBuffer)[v5] + 5);
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_ss(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 19, v8, (unsigned int)"FwpFlushCurrentBuffer", (__int64)"g_File");
  LeaveCriticalSection(&g_FwFileLock);
  return v2;
}

```

## disassembly

```asm
0x180058ba0  push    rbx
0x180058ba2  push    rsi
0x180058ba3  push    rdi
0x180058ba4  push    r12
0x180058ba6  push    r14
0x180058ba8  push    r15
0x180058baa  sub     rsp, 48h
0x180058bae  mov     rax, cs:__security_cookie
0x180058bb5  xor     rax, rsp
0x180058bb8  mov     [rsp+78h+var_40], rax
0x180058bbd  mov     ebx, ecx
0x180058bbf  xor     esi, esi
0x180058bc1  lea     rcx, ?g_FwFileLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180058bc8  mov     [rsp+78h+NumberOfBytesWritten], esi
0x180058bcc  call    cs:__imp_EnterCriticalSection
0x180058bd3  nop     dword ptr [rax+rax+00h]
0x180058bd8  mov     rcx, cs:WPP_GLOBAL_Control
0x180058bdf  lea     r15, WPP_GLOBAL_Control
0x180058be6  lea     r12, aGFile; "g_File"
0x180058bed  cmp     rcx, r15
0x180058bf0  jz      short loc_180058C10
0x180058bf2  test    byte ptr [rcx+1Ch], 4
0x180058bf6  jz      short loc_180058C10
0x180058bf8  mov     rcx, [rcx+10h]
0x180058bfc  lea     edx, [rsi+12h]
0x180058bff  lea     r9, aFwpflushcurren; "FwpFlushCurrentBuffer"
0x180058c06  mov     [rsp+78h+lpOverlapped], r12
0x180058c0b  call    WPP_SF_ss
0x180058c10  lea     r14, __ImageBase
0x180058c17  mov     rdi, rbx
0x180058c1a  cmp     [rbx+r14+132550h], sil
0x180058c22  jz      short loc_180058C29
0x180058c24  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "FALSE == g_fIOPending[FileIndex]")
0x180058c29  mov     rax, rva ?g_pCurrentBuffer@@3PAPEAU_FW_LOG_BUFFER@@A[r14+rbx*8]; _FW_LOG_BUFFER * near * g_pCurrentBuffer ...
0x180058c31  cmp     [rax], rsi
0x180058c34  jz      short loc_180058C3B
0x180058c36  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "0 == g_pCurrentBuffer[FileIndex]->Overlapped.Internal")
0x180058c3b  mov     rax, rva ?g_pCurrentBuffer@@3PAPEAU_FW_LOG_BUFFER@@A[r14+rbx*8]; _FW_LOG_BUFFER * near * g_pCurrentBuffer ...
0x180058c43  cmp     [rax+8], rsi
0x180058c47  jz      short loc_180058C4E
0x180058c49  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "0 == g_pCurrentBuffer[FileIndex]->Overlapped.InternalHigh")
0x180058c4e  mov     rax, rva ?g_pCurrentBuffer@@3PAPEAU_FW_LOG_BUFFER@@A[r14+rbx*8]; _FW_LOG_BUFFER * near * g_pCurrentBuffer ...
0x180058c56  cmp     [rax+10h], esi
0x180058c59  jz      short loc_180058C60
0x180058c5b  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "0 == g_pCurrentBuffer[FileIndex]->Overlapped.Offset")
0x180058c60  mov     rax, rva ?g_pCurrentBuffer@@3PAPEAU_FW_LOG_BUFFER@@A[r14+rbx*8]; _FW_LOG_BUFFER * near * g_pCurrentBuffer ...
0x180058c68  cmp     [rax+14h], esi
0x180058c6b  jz      short loc_180058C72
0x180058c6d  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "0 == g_pCurrentBuffer[FileIndex]->Overlapped.OffsetHigh")
0x180058c72  mov     rax, rva ?g_pCurrentBuffer@@3PAPEAU_FW_LOG_BUFFER@@A[r14+rbx*8]; _FW_LOG_BUFFER * near * g_pCurrentBuffer ...
0x180058c7a  cmp     [rax+18h], rsi
0x180058c7e  jz      short loc_180058C85
0x180058c80  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "0 == g_pCurrentBuffer[FileIndex]->Overlapped.hEvent")
0x180058c85  cmp     rva ?g_hFile@@3PAPEAXA[r14+rbx*8], 0FFFFFFFFFFFFFFFFh; void * near * g_hFile ...
0x180058c8e  jnz     short loc_180058C95
0x180058c90  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "INVALID_HANDLE_VALUE != g_hFile[FileIndex]")
0x180058c95  mov     rcx, rva ?g_pCurrentBuffer@@3PAPEAU_FW_LOG_BUFFER@@A[r14+rbx*8]; _FW_LOG_BUFFER * near * g_pCurrentBuffer ...
0x180058c9d  mov     eax, rva ?g_dwFileOffset@@3PAKA[r14+rbx*4]; ulong near * g_dwFileOffset ...
0x180058ca5  mov     [rcx+10h], eax
0x180058ca8  mov     rax, rva ?g_pCurrentBuffer@@3PAPEAU_FW_LOG_BUFFER@@A[r14+rbx*8]; _FW_LOG_BUFFER * near * g_pCurrentBuffer ...
0x180058cb0  mov     rcx, rva ?g_TPFileIO@@3PAPEAU_TP_IO@@A[r14+rdi*8]; pio
0x180058cb8  mov     ebx, [rax+20h]
0x180058cbb  sub     ebx, dword ptr rva ?g_pCurrentBuffer@@3PAPEAU_FW_LOG_BUFFER@@A[r14+rdi*8]; _FW_LOG_BUFFER * near * g_pCurrentBuffer ...
0x180058cc3  add     ebx, 0FFFFFFD8h
0x180058cc6  call    cs:__imp_StartThreadpoolIo
0x180058ccd  nop     dword ptr [rax+rax+00h]
0x180058cd2  mov     rax, rva ?g_pCurrentBuffer@@3PAPEAU_FW_LOG_BUFFER@@A[r14+rdi*8]; _FW_LOG_BUFFER * near * g_pCurrentBuffer ...
0x180058cda  lea     r9, [rsp+78h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180058cdf  mov     rcx, rva ?g_hFile@@3PAPEAXA[r14+rdi*8]; hFile
0x180058ce7  mov     r8d, ebx; nNumberOfBytesToWrite
0x180058cea  mov     [rsp+78h+lpOverlapped], rax; lpOverlapped
0x180058cef  lea     rdx, [rax+28h]; lpBuffer
0x180058cf3  call    cs:__imp_WriteFile
0x180058cfa  nop     dword ptr [rax+rax+00h]
0x180058cff  test    eax, eax
0x180058d01  jnz     short loc_180058D7A
0x180058d03  call    cs:__imp_GetLastError
0x180058d0a  nop     dword ptr [rax+rax+00h]
0x180058d0f  mov     esi, eax
0x180058d11  cmp     eax, 3E5h
0x180058d16  jz      short loc_180058D7A
0x180058d18  mov     rcx, cs:WPP_GLOBAL_Control
0x180058d1f  cmp     rcx, r15
0x180058d22  jz      short loc_180058D42
0x180058d24  test    byte ptr [rcx+1Ch], 1
0x180058d28  jz      short loc_180058D42
0x180058d2a  mov     rcx, [rcx+10h]
0x180058d2e  lea     r8, WPP_3d59fee1d00932d8b651bda1e8e67a3f_Traceguids
0x180058d35  mov     edx, 18h
0x180058d3a  mov     r9d, eax
0x180058d3d  call    WPP_SF_d
0x180058d42  mov     rcx, rva ?g_TPFileIO@@3PAPEAU_TP_IO@@A[r14+rdi*8]; pio
0x180058d4a  call    cs:__imp_CancelThreadpoolIo
0x180058d51  nop     dword ptr [rax+rax+00h]
0x180058d56  mov     rax, rva ?g_pCurrentBuffer@@3PAPEAU_FW_LOG_BUFFER@@A[r14+rdi*8]; _FW_LOG_BUFFER * near * g_pCurrentBuffer ...
0x180058d5e  xorps   xmm0, xmm0
0x180058d61  movups  xmmword ptr [rax], xmm0
0x180058d64  movups  xmmword ptr [rax+10h], xmm0
0x180058d68  mov     rcx, rva ?g_pCurrentBuffer@@3PAPEAU_FW_LOG_BUFFER@@A[r14+rdi*8]; _FW_LOG_BUFFER * near * g_pCurrentBuffer ...
0x180058d70  lea     rax, [rcx+28h]
0x180058d74  mov     [rcx+20h], rax
0x180058d78  jmp     short loc_180058D9F
0x180058d7a  mov     rax, rva ?g_pReserveBuffer@@3PAPEAU_FW_LOG_BUFFER@@A[r14+rdi*8]; _FW_LOG_BUFFER * near * g_pReserveBuffer ...
0x180058d82  mov     rva ?g_pCurrentBuffer@@3PAPEAU_FW_LOG_BUFFER@@A[r14+rdi*8], rax; _FW_LOG_BUFFER * near * g_pCurrentBuffer ...
0x180058d8a  mov     byte ptr [rdi+r14+132550h], 1
0x180058d93  mov     rva ?g_pReserveBuffer@@3PAPEAU_FW_LOG_BUFFER@@A[r14+rdi*8], 0; _FW_LOG_BUFFER * near * g_pReserveBuffer ...
0x180058d9f  mov     rcx, cs:WPP_GLOBAL_Control
0x180058da6  cmp     rcx, r15
0x180058da9  jz      short loc_180058DCB
0x180058dab  test    byte ptr [rcx+1Ch], 4
0x180058daf  jz      short loc_180058DCB
0x180058db1  mov     rcx, [rcx+10h]
0x180058db5  lea     r9, aFwpflushcurren; "FwpFlushCurrentBuffer"
0x180058dbc  mov     edx, 13h
0x180058dc1  mov     [rsp+78h+lpOverlapped], r12
0x180058dc6  call    WPP_SF_ss
0x180058dcb  lea     rcx, ?g_FwFileLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180058dd2  call    cs:__imp_LeaveCriticalSection
0x180058dd9  nop     dword ptr [rax+rax+00h]
0x180058dde  mov     eax, esi
0x180058de0  mov     rcx, [rsp+78h+var_40]
0x180058de5  xor     rcx, rsp; StackCookie
0x180058de8  call    __security_check_cookie
0x180058ded  add     rsp, 48h
0x180058df1  pop     r15
0x180058df3  pop     r14
0x180058df5  pop     r12
0x180058df7  pop     rdi
0x180058df8  pop     rsi
0x180058df9  pop     rbx
0x180058dfa  retn
```
