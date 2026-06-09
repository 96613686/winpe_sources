# FwpFlushCurrentBuffer(ulong)

- ea: `0x18005398c`
- end: `0x180053bc3`
- name: `?FwpFlushCurrentBuffer@@YAKK@Z`
- size: `567`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `4`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18004df10`
- `0x1800526d0`
- `0x180059c50`
- `0x180093f30`

## callees

- `0x1800093b0`
- `0x18000af3c`
- `0x18005398c`
- `0x18006f520`
- `0x180079750`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053add`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053add`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180053ba0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180053ba0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800539b8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800539b8`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180053aac`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180053aac`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180053b1e`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180053b1e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180053ad3`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180053ad3`

## pseudocode

```c
__int64 __fastcall FwpFlushCurrentBuffer(unsigned int a1)
{
  __int64 v1; // rbx
  DWORD v2; // esi
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // r9
  __int64 v6; // rcx
  __int64 v7; // rdi
  struct _TP_IO *v8; // rcx
  DWORD v9; // ebx
  int v10; // r8d
  DWORD LastError; // eax
  struct _FW_LOG_BUFFER * near *v12; // rax
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-48h] BYREF

  v1 = a1;
  v2 = 0;
  NumberOfBytesWritten = 0;
  EnterCriticalSection(&g_FwFileLock);
  v6 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_ss(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 18, v4, (unsigned int)"FwpFlushCurrentBuffer", (__int64)"g_File");
  v7 = v1;
  if ( *((_BYTE *)&g_fIOPending + v1) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v6, v3, v4, v5);
  if ( *(&g_pCurrentBuffer)[v1] )
    MicrosoftTelemetryAssertTriggeredNoArgs(v6, v3, v4, v5);
  if ( (&g_pCurrentBuffer)[v1][1] )
    MicrosoftTelemetryAssertTriggeredNoArgs(v6, v3, v4, v5);
  if ( *((_DWORD *)(&g_pCurrentBuffer)[v1] + 4) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v6, v3, v4, v5);
  if ( *((_DWORD *)(&g_pCurrentBuffer)[v1] + 5) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v6, v3, v4, v5);
  if ( (&g_pCurrentBuffer)[v1][3] )
    MicrosoftTelemetryAssertTriggeredNoArgs(v6, v3, v4, v5);
  if ( (&g_hFile)[v1] == (void * near *)-1LL )
    MicrosoftTelemetryAssertTriggeredNoArgs(v6, v3, v4, v5);
  *((_DWORD *)(&g_pCurrentBuffer)[v1] + 4) = *((_DWORD *)&g_dwFileOffset + v1);
  v8 = (struct _TP_IO *)(&g_TPFileIO)[v1];
  v9 = *((_DWORD *)(&g_pCurrentBuffer)[v1] + 8) - LODWORD((&g_pCurrentBuffer)[v1]) - 40;
  StartThreadpoolIo(v8);
  if ( WriteFile(
         (&g_hFile)[v7],
         (&g_pCurrentBuffer)[v7] + 5,
         v9,
         &NumberOfBytesWritten,
         (LPOVERLAPPED)(&g_pCurrentBuffer)[v7])
    || (LastError = GetLastError(), v2 = LastError, LastError == 997) )
  {
    (&g_pCurrentBuffer)[v7] = (&g_pReserveBuffer)[v7];
    *((_BYTE *)&g_fIOPending + v7) = 1;
    (&g_pReserveBuffer)[v7] = 0;
  }
  else
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 24, WPP_3d59fee1d00932d8b651bda1e8e67a3f_Traceguids, LastError);
    CancelThreadpoolIo((PTP_IO)(&g_TPFileIO)[v7]);
    v12 = (&g_pCurrentBuffer)[v7];
    *(_OWORD *)v12 = 0;
    *((_OWORD *)v12 + 1) = 0;
    (&g_pCurrentBuffer)[v7][4] = (struct _FW_LOG_BUFFER *)((&g_pCurrentBuffer)[v7] + 5);
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_ss(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 19, v10, (unsigned int)"FwpFlushCurrentBuffer", (__int64)"g_File");
  LeaveCriticalSection(&g_FwFileLock);
  return v2;
}

```

## disassembly

```asm
0x18005398c  push    rbx
0x18005398e  push    rsi
0x18005398f  push    rdi
0x180053990  push    r12
0x180053992  push    r14
0x180053994  push    r15
0x180053996  sub     rsp, 48h
0x18005399a  mov     rax, cs:__security_cookie
0x1800539a1  xor     rax, rsp
0x1800539a4  mov     [rsp+78h+var_40], rax
0x1800539a9  mov     ebx, ecx
0x1800539ab  xor     esi, esi
0x1800539ad  lea     rcx, ?g_FwFileLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800539b4  mov     [rsp+78h+NumberOfBytesWritten], esi
0x1800539b8  call    cs:__imp_EnterCriticalSection
0x1800539be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800539c5  lea     r15, WPP_GLOBAL_Control
0x1800539cc  lea     r12, aGFile; "g_File"
0x1800539d3  cmp     rcx, r15
0x1800539d6  jz      short loc_1800539F6
0x1800539d8  test    byte ptr [rcx+1Ch], 4
0x1800539dc  jz      short loc_1800539F6
0x1800539de  mov     rcx, [rcx+10h]
0x1800539e2  lea     edx, [rsi+12h]
0x1800539e5  lea     r9, aFwpflushcurren; "FwpFlushCurrentBuffer"
0x1800539ec  mov     [rsp+78h+lpOverlapped], r12
0x1800539f1  call    WPP_SF_ss
0x1800539f6  lea     r14, __ImageBase
0x1800539fd  mov     rdi, rbx
0x180053a00  cmp     [rbx+r14+12C318h], sil
0x180053a08  jz      short loc_180053A0F
0x180053a0a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180053a0f  mov     rax, rva ?g_pCurrentBuffer@@3PAPEAU_FW_LOG_BUFFER@@A[r14+rbx*8]; _FW_LOG_BUFFER * near * g_pCurrentBuffer ...
0x180053a17  cmp     [rax], rsi
0x180053a1a  jz      short loc_180053A21
0x180053a1c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180053a21  mov     rax, rva ?g_pCurrentBuffer@@3PAPEAU_FW_LOG_BUFFER@@A[r14+rbx*8]; _FW_LOG_BUFFER * near * g_pCurrentBuffer ...
0x180053a29  cmp     [rax+8], rsi
0x180053a2d  jz      short loc_180053A34
0x180053a2f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180053a34  mov     rax, rva ?g_pCurrentBuffer@@3PAPEAU_FW_LOG_BUFFER@@A[r14+rbx*8]; _FW_LOG_BUFFER * near * g_pCurrentBuffer ...
0x180053a3c  cmp     [rax+10h], esi
0x180053a3f  jz      short loc_180053A46
0x180053a41  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180053a46  mov     rax, rva ?g_pCurrentBuffer@@3PAPEAU_FW_LOG_BUFFER@@A[r14+rbx*8]; _FW_LOG_BUFFER * near * g_pCurrentBuffer ...
0x180053a4e  cmp     [rax+14h], esi
0x180053a51  jz      short loc_180053A58
0x180053a53  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180053a58  mov     rax, rva ?g_pCurrentBuffer@@3PAPEAU_FW_LOG_BUFFER@@A[r14+rbx*8]; _FW_LOG_BUFFER * near * g_pCurrentBuffer ...
0x180053a60  cmp     [rax+18h], rsi
0x180053a64  jz      short loc_180053A6B
0x180053a66  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180053a6b  cmp     rva ?g_hFile@@3PAPEAXA[r14+rbx*8], 0FFFFFFFFFFFFFFFFh; void * near * g_hFile ...
0x180053a74  jnz     short loc_180053A7B
0x180053a76  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180053a7b  mov     rcx, rva ?g_pCurrentBuffer@@3PAPEAU_FW_LOG_BUFFER@@A[r14+rbx*8]; _FW_LOG_BUFFER * near * g_pCurrentBuffer ...
0x180053a83  mov     eax, rva ?g_dwFileOffset@@3PAKA[r14+rbx*4]; ulong near * g_dwFileOffset ...
0x180053a8b  mov     [rcx+10h], eax
0x180053a8e  mov     rax, rva ?g_pCurrentBuffer@@3PAPEAU_FW_LOG_BUFFER@@A[r14+rbx*8]; _FW_LOG_BUFFER * near * g_pCurrentBuffer ...
0x180053a96  mov     rcx, rva ?g_TPFileIO@@3PAPEAU_TP_IO@@A[r14+rdi*8]; pio
0x180053a9e  mov     ebx, [rax+20h]
0x180053aa1  sub     ebx, dword ptr rva ?g_pCurrentBuffer@@3PAPEAU_FW_LOG_BUFFER@@A[r14+rdi*8]; _FW_LOG_BUFFER * near * g_pCurrentBuffer ...
0x180053aa9  add     ebx, 0FFFFFFD8h
0x180053aac  call    cs:__imp_StartThreadpoolIo
0x180053ab2  mov     rax, rva ?g_pCurrentBuffer@@3PAPEAU_FW_LOG_BUFFER@@A[r14+rdi*8]; _FW_LOG_BUFFER * near * g_pCurrentBuffer ...
0x180053aba  lea     r9, [rsp+78h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180053abf  mov     rcx, rva ?g_hFile@@3PAPEAXA[r14+rdi*8]; hFile
0x180053ac7  mov     r8d, ebx; nNumberOfBytesToWrite
0x180053aca  mov     [rsp+78h+lpOverlapped], rax; lpOverlapped
0x180053acf  lea     rdx, [rax+28h]; lpBuffer
0x180053ad3  call    cs:__imp_WriteFile
0x180053ad9  test    eax, eax
0x180053adb  jnz     short loc_180053B48
0x180053add  call    cs:__imp_GetLastError
0x180053ae3  mov     esi, eax
0x180053ae5  cmp     eax, 3E5h
0x180053aea  jz      short loc_180053B48
0x180053aec  mov     rcx, cs:WPP_GLOBAL_Control
0x180053af3  cmp     rcx, r15
0x180053af6  jz      short loc_180053B16
0x180053af8  test    byte ptr [rcx+1Ch], 1
0x180053afc  jz      short loc_180053B16
0x180053afe  mov     rcx, [rcx+10h]
0x180053b02  lea     r8, WPP_3d59fee1d00932d8b651bda1e8e67a3f_Traceguids
0x180053b09  mov     edx, 18h
0x180053b0e  mov     r9d, eax
0x180053b11  call    WPP_SF_d
0x180053b16  mov     rcx, rva ?g_TPFileIO@@3PAPEAU_TP_IO@@A[r14+rdi*8]; pio
0x180053b1e  call    cs:__imp_CancelThreadpoolIo
0x180053b24  mov     rax, rva ?g_pCurrentBuffer@@3PAPEAU_FW_LOG_BUFFER@@A[r14+rdi*8]; _FW_LOG_BUFFER * near * g_pCurrentBuffer ...
0x180053b2c  xorps   xmm0, xmm0
0x180053b2f  movups  xmmword ptr [rax], xmm0
0x180053b32  movups  xmmword ptr [rax+10h], xmm0
0x180053b36  mov     rcx, rva ?g_pCurrentBuffer@@3PAPEAU_FW_LOG_BUFFER@@A[r14+rdi*8]; _FW_LOG_BUFFER * near * g_pCurrentBuffer ...
0x180053b3e  lea     rax, [rcx+28h]
0x180053b42  mov     [rcx+20h], rax
0x180053b46  jmp     short loc_180053B6D
0x180053b48  mov     rax, rva ?g_pReserveBuffer@@3PAPEAU_FW_LOG_BUFFER@@A[r14+rdi*8]; _FW_LOG_BUFFER * near * g_pReserveBuffer ...
0x180053b50  mov     rva ?g_pCurrentBuffer@@3PAPEAU_FW_LOG_BUFFER@@A[r14+rdi*8], rax; _FW_LOG_BUFFER * near * g_pCurrentBuffer ...
0x180053b58  mov     byte ptr [rdi+r14+12C318h], 1
0x180053b61  mov     rva ?g_pReserveBuffer@@3PAPEAU_FW_LOG_BUFFER@@A[r14+rdi*8], 0; _FW_LOG_BUFFER * near * g_pReserveBuffer ...
0x180053b6d  mov     rcx, cs:WPP_GLOBAL_Control
0x180053b74  cmp     rcx, r15
0x180053b77  jz      short loc_180053B99
0x180053b79  test    byte ptr [rcx+1Ch], 4
0x180053b7d  jz      short loc_180053B99
0x180053b7f  mov     rcx, [rcx+10h]
0x180053b83  lea     r9, aFwpflushcurren; "FwpFlushCurrentBuffer"
0x180053b8a  mov     edx, 13h
0x180053b8f  mov     [rsp+78h+lpOverlapped], r12
0x180053b94  call    WPP_SF_ss
0x180053b99  lea     rcx, ?g_FwFileLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180053ba0  call    cs:__imp_LeaveCriticalSection
0x180053ba6  mov     eax, esi
0x180053ba8  mov     rcx, [rsp+78h+var_40]
0x180053bad  xor     rcx, rsp; StackCookie
0x180053bb0  call    __security_check_cookie
0x180053bb5  add     rsp, 48h
0x180053bb9  pop     r15
0x180053bbb  pop     r14
0x180053bbd  pop     r12
0x180053bbf  pop     rdi
0x180053bc0  pop     rsi
0x180053bc1  pop     rbx
0x180053bc2  retn
```
