# NtReadLogRecordInternal(void *,_CLS_LSN *,ulong,void *,ulong,ulong *,void *,uchar,_OVERLAPPED *)

- ea: `0x180008ca0`
- end: `0x180008ea7`
- name: `?NtReadLogRecordInternal@@YAKPEAXPEAT_CLS_LSN@@K0KPEAK0EPEAU_OVERLAPPED@@@Z`
- size: `519`
- prototype: `unsigned int(void *, union _CLS_LSN *, unsigned int, void *, unsigned int, unsigned int *, void *, unsigned __int8, struct _OVERLAPPED *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001195c`
- `0x1800124f0`

## callees

- `0x180008ca0`
- `0x180014e00`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180008e0d`
- `ntdll!RtlNtStatusToDosError` at `0x180008e0d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008e71`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008e71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008dcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008dcd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008e2e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008e2e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180008dba`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180008dba`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180008d58`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180008d58`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180008df4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180008df4`

## pseudocode

```c
__int64 __fastcall NtReadLogRecordInternal(
        void *a1,
        union _CLS_LSN *a2,
        int a3,
        char *a4,
        DWORD nOutBufferSize,
        unsigned int *lpBytesReturned,
        unsigned __int64 a7,
        unsigned __int8 a8,
        struct _OVERLAPPED *a9)
{
  DWORD LastError; // ebx
  struct _OVERLAPPED *lpOverlapped; // rdi
  unsigned __int64 EventA; // rax
  union _CLS_LSN *v15; // [rsp+48h] [rbp-49h]
  struct _OVERLAPPED Overlapped; // [rsp+50h] [rbp-41h] BYREF
  HANDLE hDevice; // [rsp+70h] [rbp-21h]
  _BYTE InBuffer[12]; // [rsp+78h] [rbp-19h] BYREF
  int v19; // [rsp+84h] [rbp-Dh]

  LastError = 0;
  v15 = a2;
  hDevice = a1;
  memset(&Overlapped, 0, sizeof(Overlapped));
  memset(InBuffer, 0, sizeof(InBuffer));
  v19 = 0;
  if ( !a2 || !lpBytesReturned )
    return 87;
  if ( nOutBufferSize && (!a4 || nOutBufferSize < 0x28) )
    return 1784;
  if ( a7 )
  {
    lpOverlapped = &Overlapped;
    Overlapped.hEvent = (HANDLE)(a7 | 1);
  }
  else if ( a9 )
  {
    lpOverlapped = a9;
  }
  else
  {
    EventA = (unsigned __int64)CreateEventA(0, 0, 0, 0);
    if ( !EventA )
      return 8;
    a2 = v15;
    lpOverlapped = &Overlapped;
    Overlapped.hEvent = (HANDLE)(EventA | 1);
  }
  *(union _CLS_LSN *)InBuffer = *a2;
  *(_DWORD *)&InBuffer[8] = a3;
  if ( !DeviceIoControl(hDevice, 0x80076832, InBuffer, 0x10u, a4, nOutBufferSize, lpBytesReturned, lpOverlapped) )
    LastError = GetLastError();
  if ( a7 || !a9 )
  {
    if ( LastError == 997 )
    {
      if ( WaitForSingleObject(lpOverlapped->hEvent, 0xFFFFFFFF) )
        LastError = 1117;
      else
        LastError = RtlNtStatusToDosError(lpOverlapped->Internal);
    }
    lpOverlapped->hEvent = (HANDLE)((unsigned __int64)lpOverlapped->hEvent & ~1uLL);
    if ( !a7 && !a9 )
    {
      CloseHandle(lpOverlapped->hEvent);
      lpOverlapped->hEvent = 0;
    }
  }
  if ( !LastError )
  {
    *v15 = *(union _CLS_LSN *)&a4[nOutBufferSize - 32];
    if ( a9 )
    {
      if ( a8 && (!a9->hEvent || ((__int64)a9->hEvent & 1) == 0) )
        return 997;
    }
  }
  SetLastError(LastError);
  return LastError;
}

```

## disassembly

```asm
0x180008ca0  push    rbp
0x180008ca2  push    rbx
0x180008ca3  push    rsi
0x180008ca4  push    rdi
0x180008ca5  push    r12
0x180008ca7  push    r13
0x180008ca9  push    r14
0x180008cab  push    r15
0x180008cad  lea     rbp, [rsp-7]
0x180008cb2  sub     rsp, 98h
0x180008cb9  mov     rax, cs:__security_cookie
0x180008cc0  xor     rax, rsp
0x180008cc3  mov     [rbp+3Fh+var_48], rax
0x180008cc7  mov     r15d, [rbp+3Fh+arg_20]
0x180008ccb  xor     ebx, ebx
0x180008ccd  mov     r12, [rbp+3Fh+arg_28]
0x180008cd1  xor     eax, eax
0x180008cd3  mov     r14, [rbp+3Fh+arg_30]
0x180008cd7  mov     r13, r9
0x180008cda  mov     rsi, [rbp+3Fh+arg_40]
0x180008ce1  mov     [rbp+3Fh+var_90], r8d
0x180008ce5  mov     [rbp+3Fh+var_88], rdx
0x180008ce9  mov     [rbp+3Fh+hDevice], rcx
0x180008ced  mov     [rbp+3Fh+Overlapped.Internal], rbx
0x180008cf1  mov     [rbp+3Fh+Overlapped.InternalHigh], rbx
0x180008cf5  mov     qword ptr [rbp+3Fh+Overlapped.10h], rbx
0x180008cf9  mov     [rbp+3Fh+Overlapped.hEvent], rbx
0x180008cfd  mov     dword ptr [rbp+3Fh+InBuffer], ebx
0x180008d00  mov     [rbp+3Fh+InBuffer+4], rax
0x180008d04  mov     [rbp+3Fh+var_4C], eax
0x180008d07  test    rdx, rdx
0x180008d0a  jz      loc_180008E81
0x180008d10  test    r12, r12
0x180008d13  jz      loc_180008E81
0x180008d19  test    r15d, r15d
0x180008d1c  jz      short loc_180008D33
0x180008d1e  test    r9, r9
0x180008d21  jz      short loc_180008D29
0x180008d23  cmp     r15d, 28h ; '('
0x180008d27  jnb     short loc_180008D33
0x180008d29  mov     eax, 6F8h
0x180008d2e  jmp     loc_180008E86
0x180008d33  test    r14, r14
0x180008d36  jz      short loc_180008D49
0x180008d38  mov     rax, r14
0x180008d3b  lea     rdi, [rbp+3Fh+Overlapped]
0x180008d3f  or      rax, 1
0x180008d43  mov     [rbp+3Fh+Overlapped.hEvent], rax
0x180008d47  jmp     short loc_180008D86
0x180008d49  test    rsi, rsi
0x180008d4c  jnz     short loc_180008D83
0x180008d4e  xor     r9d, r9d; lpName
0x180008d51  xor     r8d, r8d; bInitialState
0x180008d54  xor     edx, edx; bManualReset
0x180008d56  xor     ecx, ecx; lpEventAttributes
0x180008d58  call    cs:__imp_CreateEventA
0x180008d5f  nop     dword ptr [rax+rax+00h]
0x180008d64  test    rax, rax
0x180008d67  jnz     short loc_180008D71
0x180008d69  lea     eax, [rsi+8]
0x180008d6c  jmp     loc_180008E86
0x180008d71  mov     rdx, [rbp+3Fh+var_88]
0x180008d75  lea     rdi, [rbp+3Fh+Overlapped]
0x180008d79  or      rax, 1
0x180008d7d  mov     [rbp+3Fh+Overlapped.hEvent], rax
0x180008d81  jmp     short loc_180008D86
0x180008d83  mov     rdi, rsi
0x180008d86  mov     rax, [rdx]
0x180008d89  lea     r8, [rbp+3Fh+InBuffer]; lpInBuffer
0x180008d8d  mov     rcx, [rbp+3Fh+hDevice]; hDevice
0x180008d91  mov     r9d, 10h; nInBufferSize
0x180008d97  mov     [rsp+0D0h+lpOverlapped], rdi; lpOverlapped
0x180008d9c  mov     edx, 80076832h; dwIoControlCode
0x180008da1  mov     [rbp+3Fh+InBuffer], rax
0x180008da5  mov     eax, [rbp+3Fh+var_90]
0x180008da8  mov     [rsp+0D0h+lpBytesReturned], r12; lpBytesReturned
0x180008dad  mov     [rsp+0D0h+nOutBufferSize], r15d; nOutBufferSize
0x180008db2  mov     [rbp+3Fh+var_50], eax
0x180008db5  mov     [rsp+0D0h+lpOutBuffer], r13; lpOutBuffer
0x180008dba  call    cs:__imp_DeviceIoControl
0x180008dc1  nop     dword ptr [rax+rax+00h]
0x180008dc6  xor     r12d, r12d
0x180008dc9  test    eax, eax
0x180008dcb  jnz     short loc_180008DDB
0x180008dcd  call    cs:__imp_GetLastError
0x180008dd4  nop     dword ptr [rax+rax+00h]
0x180008dd9  mov     ebx, eax
0x180008ddb  test    r14, r14
0x180008dde  jnz     short loc_180008DE5
0x180008de0  test    rsi, rsi
0x180008de3  jnz     short loc_180008E3E
0x180008de5  cmp     ebx, 3E5h
0x180008deb  jnz     short loc_180008E1B
0x180008ded  mov     rcx, [rdi+18h]; hHandle
0x180008df1  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180008df4  call    cs:__imp_WaitForSingleObject
0x180008dfb  nop     dword ptr [rax+rax+00h]
0x180008e00  test    eax, eax
0x180008e02  jz      short loc_180008E0B
0x180008e04  mov     ebx, 45Dh
0x180008e09  jmp     short loc_180008E1B
0x180008e0b  mov     ecx, [rdi]; Status
0x180008e0d  call    cs:__imp_RtlNtStatusToDosError
0x180008e14  nop     dword ptr [rax+rax+00h]
0x180008e19  mov     ebx, eax
0x180008e1b  and     qword ptr [rdi+18h], 0FFFFFFFFFFFFFFFEh
0x180008e20  test    r14, r14
0x180008e23  jnz     short loc_180008E3E
0x180008e25  test    rsi, rsi
0x180008e28  jnz     short loc_180008E3E
0x180008e2a  mov     rcx, [rdi+18h]; hObject
0x180008e2e  call    cs:__imp_CloseHandle
0x180008e35  nop     dword ptr [rax+rax+00h]
0x180008e3a  mov     [rdi+18h], r12
0x180008e3e  test    ebx, ebx
0x180008e40  jnz     short loc_180008E6F
0x180008e42  mov     rax, [rbp+3Fh+var_88]
0x180008e46  mov     rcx, [r15+r13-20h]
0x180008e4b  mov     [rax], rcx
0x180008e4e  test    rsi, rsi
0x180008e51  jz      short loc_180008E6F
0x180008e53  cmp     [rbp+3Fh+arg_38], r12b
0x180008e5a  jz      short loc_180008E6F
0x180008e5c  cmp     [rsi+18h], r12
0x180008e60  jz      short loc_180008E68
0x180008e62  test    byte ptr [rsi+18h], 1
0x180008e66  jnz     short loc_180008E6F
0x180008e68  mov     eax, 3E5h
0x180008e6d  jmp     short loc_180008E86
0x180008e6f  mov     ecx, ebx; dwErrCode
0x180008e71  call    cs:__imp_SetLastError
0x180008e78  nop     dword ptr [rax+rax+00h]
0x180008e7d  mov     eax, ebx
0x180008e7f  jmp     short loc_180008E86
0x180008e81  mov     eax, 57h ; 'W'
0x180008e86  mov     rcx, [rbp+3Fh+var_48]
0x180008e8a  xor     rcx, rsp; StackCookie
0x180008e8d  call    __security_check_cookie
0x180008e92  add     rsp, 98h
0x180008e99  pop     r15
0x180008e9b  pop     r14
0x180008e9d  pop     r13
0x180008e9f  pop     r12
0x180008ea1  pop     rdi
0x180008ea2  pop     rsi
0x180008ea3  pop     rbx
0x180008ea4  pop     rbp
0x180008ea5  retn
```
