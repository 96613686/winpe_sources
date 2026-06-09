# BthServOverlappedIoctl(void *,ulong,void *,ulong,void *,ulong,ulong *)

- ea: `0x18000dfcc`
- end: `0x18000e202`
- name: `?BthServOverlappedIoctl@@YAKPEAXK0K0KPEAK@Z`
- size: `566`
- prototype: `unsigned int __fastcall(HANDLE hFile, DWORD dwIoControlCode, void *lpInBuffer, DWORD nInBufferSize, void *, DWORD, LPDWORD lpNumberOfBytesTransferred)`
- caller_count: `17`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000c0cc`
- `0x180015010`
- `0x180015b30`
- `0x180015edc`
- `0x1800161a4`
- `0x180016414`
- `0x180016864`
- `0x180016be0`
- `0x180016dd8`
- `0x1800170b4`
- `0x1800173b0`
- `0x180017630`
- `0x18001addc`
- `0x18001afcc`
- `0x18001ca3c`
- `0x18001d754`
- `0x18001ee00`

## callees

- `0x1800058f8`
- `0x180009944`
- `0x180009ce8`
- `0x18000dfcc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000e020`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000e020`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e038`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e0e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e0f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e16e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e038`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e0e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e0f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e16e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e0bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e117`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e156`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e184`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e0bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e117`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e156`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e184`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000e0a3`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000e0a3`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18000e13e`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18000e13e`

## pseudocode

```c
DWORD __fastcall BthServOverlappedIoctl(
        HANDLE hFile,
        DWORD dwIoControlCode,
        void *lpInBuffer,
        DWORD nInBufferSize,
        void *lpOutBuffer,
        DWORD nOutBufferSize,
        LPDWORD lpNumberOfBytesTransferred)
{
  DWORD *lpBytesReturned; // rsi
  LPDWORD v12; // rbx
  wil::details *v13; // rcx
  HANDLE Event; // rdi
  unsigned int v15; // r8d
  const char *v16; // r9
  DWORD LastError; // edi
  unsigned int v19; // r8d
  const char *v20; // r9
  unsigned int v21; // r8d
  const char *v22; // r9
  unsigned int v23; // r8d
  const char *v24; // r9
  int v25; // [rsp+40h] [rbp-48h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+48h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  lpBytesReturned = (DWORD *)&v25;
  v25 = 0;
  if ( lpNumberOfBytesTransferred )
    lpBytesReturned = lpNumberOfBytesTransferred;
  v12 = 0;
  lpNumberOfBytesTransferred = 0;
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  if ( Event )
  {
    GetLastError();
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      &lpNumberOfBytesTransferred,
      Event);
    v12 = lpNumberOfBytesTransferred;
  }
  else if ( (int)wil::details::GetLastErrorFailHr(v13) < 0 )
  {
    return GetLastError();
  }
  memset(&Overlapped, 0, 24);
  Overlapped.hEvent = v12;
  if ( DeviceIoControl(
         hFile,
         dwIoControlCode,
         lpInBuffer,
         nInBufferSize,
         lpOutBuffer,
         nOutBufferSize,
         lpBytesReturned,
         &Overlapped) )
  {
    if ( v12 )
    {
      if ( !CloseHandle(v12) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DD, v15, v16);
    }
    return 0;
  }
  LastError = GetLastError();
  if ( LastError == 997 )
  {
    if ( GetOverlappedResult(hFile, &Overlapped, lpBytesReturned, 1) )
    {
      if ( v12 && !CloseHandle(v12) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DD, v21, v22);
      return 0;
    }
    LastError = GetLastError();
    if ( v12 && !CloseHandle(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DD, v23, v24);
  }
  else if ( v12 && !CloseHandle(v12) )
  {
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DD, v19, v20);
  }
  return LastError;
}

```

## disassembly

```asm
0x18000dfcc  mov     r11, rsp
0x18000dfcf  mov     [r11+8], rbx
0x18000dfd3  mov     [r11+10h], rbp
0x18000dfd7  mov     [r11+18h], rsi
0x18000dfdb  mov     [r11+20h], rdi
0x18000dfdf  push    r12
0x18000dfe1  push    r14
0x18000dfe3  push    r15
0x18000dfe5  sub     rsp, 70h
0x18000dfe9  mov     rax, [rsp+88h+lpNumberOfBytesTransferred]
0x18000dff1  lea     rsi, [r11-48h]
0x18000dff5  and     [rsp+88h+var_48], 0
0x18000dffa  mov     r14d, r9d
0x18000dffd  test    rax, rax
0x18000e000  mov     r15, r8
0x18000e003  mov     r12d, edx
0x18000e006  mov     rbp, rcx
0x18000e009  cmovnz  rsi, rax
0x18000e00d  mov     r9d, 1F0003h; dwDesiredAccess
0x18000e013  xor     ebx, ebx
0x18000e015  xor     r8d, r8d; dwFlags
0x18000e018  xor     edx, edx; lpName
0x18000e01a  mov     [r11+38h], rbx
0x18000e01e  xor     ecx, ecx; lpEventAttributes
0x18000e020  call    cs:__imp_CreateEventExW
0x18000e027  nop     dword ptr [rax+rax+00h]
0x18000e02c  mov     rdi, rax
0x18000e02f  test    rax, rax
0x18000e032  jz      loc_18000E0D8
0x18000e038  call    cs:__imp_GetLastError
0x18000e03f  nop     dword ptr [rax+rax+00h]
0x18000e044  mov     rdx, rdi
0x18000e047  lea     rcx, [rsp+88h+lpNumberOfBytesTransferred]
0x18000e04f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000e054  mov     rbx, [rsp+88h+lpNumberOfBytesTransferred]
0x18000e05c  and     [rsp+88h+Overlapped.Internal], 0
0x18000e062  lea     rax, [rsp+88h+Overlapped]
0x18000e067  mov     [rsp+88h+lpOverlapped], rax; lpOverlapped
0x18000e06c  xorps   xmm0, xmm0
0x18000e06f  mov     eax, [rsp+88h+arg_28]
0x18000e076  mov     r9d, r14d; nInBufferSize
0x18000e079  mov     [rsp+88h+lpBytesReturned], rsi; lpBytesReturned
0x18000e07e  mov     r8, r15; lpInBuffer
0x18000e081  mov     [rsp+88h+nOutBufferSize], eax; nOutBufferSize
0x18000e085  mov     edx, r12d; dwIoControlCode
0x18000e088  mov     rax, [rsp+88h+arg_20]
0x18000e090  mov     rcx, rbp; hDevice
0x18000e093  mov     [rsp+88h+lpOutBuffer], rax; lpOutBuffer
0x18000e098  movdqu  xmmword ptr [rsp+88h+Overlapped.InternalHigh], xmm0
0x18000e09e  mov     [rsp+88h+Overlapped.hEvent], rbx
0x18000e0a3  call    cs:__imp_DeviceIoControl
0x18000e0aa  nop     dword ptr [rax+rax+00h]
0x18000e0af  test    eax, eax
0x18000e0b1  jz      short loc_18000E0F6
0x18000e0b3  test    rbx, rbx
0x18000e0b6  jz      loc_18000E16A
0x18000e0bc  mov     rcx, rbx; hObject
0x18000e0bf  call    cs:__imp_CloseHandle
0x18000e0c6  nop     dword ptr [rax+rax+00h]
0x18000e0cb  test    eax, eax
0x18000e0cd  jz      loc_18000E1C9
0x18000e0d3  jmp     loc_18000E16A
0x18000e0d8  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000e0dd  test    eax, eax
0x18000e0df  jns     loc_18000E05C
0x18000e0e5  call    cs:__imp_GetLastError
0x18000e0ec  nop     dword ptr [rax+rax+00h]
0x18000e0f1  jmp     loc_18000E196
0x18000e0f6  call    cs:__imp_GetLastError
0x18000e0fd  nop     dword ptr [rax+rax+00h]
0x18000e102  mov     edi, eax
0x18000e104  cmp     eax, 3E5h
0x18000e109  jz      short loc_18000E12D
0x18000e10b  test    rbx, rbx
0x18000e10e  jz      loc_18000E194
0x18000e114  mov     rcx, rbx; hObject
0x18000e117  call    cs:__imp_CloseHandle
0x18000e11e  nop     dword ptr [rax+rax+00h]
0x18000e123  test    eax, eax
0x18000e125  jz      loc_18000E1DC
0x18000e12b  jmp     short loc_18000E194
0x18000e12d  mov     r9d, 1; bWait
0x18000e133  lea     rdx, [rsp+88h+Overlapped]; lpOverlapped
0x18000e138  mov     r8, rsi; lpNumberOfBytesTransferred
0x18000e13b  mov     rcx, rbp; hFile
0x18000e13e  call    cs:__imp_GetOverlappedResult
0x18000e145  nop     dword ptr [rax+rax+00h]
0x18000e14a  test    eax, eax
0x18000e14c  jz      short loc_18000E16E
0x18000e14e  test    rbx, rbx
0x18000e151  jz      short loc_18000E16A
0x18000e153  mov     rcx, rbx; hObject
0x18000e156  call    cs:__imp_CloseHandle
0x18000e15d  nop     dword ptr [rax+rax+00h]
0x18000e162  test    eax, eax
0x18000e164  jz      loc_18000E1EF
0x18000e16a  xor     eax, eax
0x18000e16c  jmp     short loc_18000E196
0x18000e16e  call    cs:__imp_GetLastError
0x18000e175  nop     dword ptr [rax+rax+00h]
0x18000e17a  mov     edi, eax
0x18000e17c  test    rbx, rbx
0x18000e17f  jz      short loc_18000E194
0x18000e181  mov     rcx, rbx; hObject
0x18000e184  call    cs:__imp_CloseHandle
0x18000e18b  nop     dword ptr [rax+rax+00h]
0x18000e190  test    eax, eax
0x18000e192  jz      short loc_18000E1B6
0x18000e194  mov     eax, edi
0x18000e196  lea     r11, [rsp+88h+var_18]
0x18000e19b  mov     rbx, [r11+20h]
0x18000e19f  mov     rbp, [r11+28h]
0x18000e1a3  mov     rsi, [r11+30h]
0x18000e1a7  mov     rdi, [r11+38h]
0x18000e1ab  mov     rsp, r11
0x18000e1ae  pop     r15
0x18000e1b0  pop     r14
0x18000e1b2  pop     r12
0x18000e1b4  retn
0x18000e1b6  mov     rcx, [rsp+88h]; this
0x18000e1be  mov     edx, 9DDh; void *
0x18000e1c3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000e1c9  mov     rcx, [rsp+88h]; this
0x18000e1d1  mov     edx, 9DDh; void *
0x18000e1d6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000e1dc  mov     rcx, [rsp+88h]; this
0x18000e1e4  mov     edx, 9DDh; void *
0x18000e1e9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000e1ef  mov     rcx, [rsp+88h]; this
0x18000e1f7  mov     edx, 9DDh; void *
0x18000e1fc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
