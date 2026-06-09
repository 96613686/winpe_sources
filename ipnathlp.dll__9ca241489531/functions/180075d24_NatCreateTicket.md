# NatCreateTicket

- ea: `0x180075d24`
- end: `0x180075f97`
- name: `NatCreateTicket`
- size: `627`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180074350`
- `0x180074928`

## callees

- `0x18000c750`
- `0x18001ec08`
- `0x18004b654`
- `0x18004e0c0`
- `0x180075d24`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180075e76`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180075e76`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180075ec6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180075ec6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180075dd0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180075dd0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180075eda`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180075eda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075e04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075e04`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180075f38`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180075f38`
- `ntdll!NtDeviceIoControlFile` at `0x180075eb7`
- `ntdll!NtDeviceIoControlFile` at `0x180075eb7`
- `ntdll!RtlNtStatusToDosError` at `0x180075ef2`
- `ntdll!RtlNtStatusToDosError` at `0x180075ef2`

## pseudocode

```c
__int64 __fastcall NatCreateTicket(
        unsigned int a1,
        unsigned __int8 a2,
        unsigned __int16 a3,
        __int64 a4,
        unsigned __int16 a5,
        int a6)
{
  HANDLE EventW; // rsi
  PVOID *v10; // rcx
  unsigned int v11; // ebx
  DWORD LastError; // eax
  __int64 v13; // rdx
  int Status; // edi
  ULONG v15; // eax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-30h] BYREF
  __int128 InputBuffer; // [rsp+60h] [rbp-20h] BYREF
  int v19; // [rsp+70h] [rbp-10h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_dddddd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      80,
      &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids,
      a1,
      a2,
      a3,
      0,
      a5,
      a6);
  }
  v19 = 0;
  InputBuffer = 0;
  IoStatusBlock = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  if ( EventW )
  {
    LODWORD(InputBuffer) = a1;
    v11 = 0;
    BYTE4(InputBuffer) = a2;
    DWORD2(InputBuffer) = 0;
    WORD3(InputBuffer) = a3;
    WORD6(InputBuffer) = a5;
    v19 = a6;
    EnterCriticalSection(&NatInterfaceLock);
    Status = NtDeviceIoControlFile(NatFileHandle, EventW, 0, 0, &IoStatusBlock, 0x128068u, &InputBuffer, 0x14u, 0, 0);
    LeaveCriticalSection(&NatInterfaceLock);
    if ( Status == 259 )
    {
      WaitForSingleObject(EventW, 0xFFFFFFFF);
      Status = IoStatusBlock.Status;
    }
    if ( Status < 0 )
    {
      v15 = RtlNtStatusToDosError(Status);
      v11 = v15;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          83,
          &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids,
          (unsigned int)Status,
          v15);
      }
    }
    CloseHandle(EventW);
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      v13 = 84;
      goto LABEL_25;
    }
  }
  else
  {
    v10 = (PVOID *)WPP_GLOBAL_Control;
    v11 = 8;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids, LastError);
        v10 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v10 != &WPP_GLOBAL_Control && (*((_DWORD *)v10 + 7) & 0x200) != 0 && *((_BYTE *)v10 + 25) >= 6u )
      {
        v13 = 82;
LABEL_25:
        WPP_SF_d(v10[2], v13, &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids, v11);
      }
    }
  }
  return v11;
}

```

## disassembly

```asm
0x180075d24  mov     [rsp-38h+arg_18], rbx
0x180075d29  push    rbp
0x180075d2a  push    rsi
0x180075d2b  push    rdi
0x180075d2c  push    r12
0x180075d2e  push    r13
0x180075d30  push    r14
0x180075d32  push    r15
0x180075d34  mov     rbp, rsp
0x180075d37  sub     rsp, 80h
0x180075d3e  mov     rax, cs:__security_cookie
0x180075d45  xor     rax, rsp
0x180075d48  mov     [rbp+var_8], rax
0x180075d4c  movzx   r14d, r8w
0x180075d50  mov     ebx, ecx
0x180075d52  movzx   edi, dl
0x180075d55  mov     rcx, cs:WPP_GLOBAL_Control
0x180075d5c  lea     rax, WPP_GLOBAL_Control
0x180075d63  mov     r15d, [rbp+arg_28]
0x180075d67  mov     r13d, 200h
0x180075d6d  movzx   r12d, [rbp+arg_20]
0x180075d72  cmp     rcx, rax
0x180075d75  jz      short loc_180075DB6
0x180075d77  test    [rcx+1Ch], r13d
0x180075d7b  jz      short loc_180075DB6
0x180075d7d  cmp     byte ptr [rcx+19h], 6
0x180075d81  jb      short loc_180075DB6
0x180075d83  mov     rcx, [rcx+10h]
0x180075d87  lea     r8, WPP_1a1a310d9f3938633825d91885f62d23_Traceguids
0x180075d8e  mov     dword ptr [rsp+80h+OutputBuffer], r15d
0x180075d93  mov     edx, 50h ; 'P'
0x180075d98  mov     [rsp+80h+InputBufferLength], r12d
0x180075d9d  mov     r9d, ebx
0x180075da0  mov     dword ptr [rsp+80h+InputBuffer], 0
0x180075da8  mov     [rsp+80h+IoControlCode], r14d
0x180075dad  mov     dword ptr [rsp+80h+IoStatusBlock], edi
0x180075db1  call    WPP_SF_dddddd
0x180075db6  xorps   xmm0, xmm0
0x180075db9  xor     eax, eax
0x180075dbb  xor     r9d, r9d; lpName
0x180075dbe  mov     [rbp+var_10], eax
0x180075dc1  xor     r8d, r8d; bInitialState
0x180075dc4  xor     edx, edx; bManualReset
0x180075dc6  xor     ecx, ecx; lpEventAttributes
0x180075dc8  movups  [rbp+var_20], xmm0
0x180075dcc  movups  xmmword ptr [rbp+var_30], xmm0
0x180075dd0  call    cs:__imp_CreateEventW
0x180075dd6  mov     rsi, rax
0x180075dd9  test    rax, rax
0x180075ddc  jnz     short loc_180075E55
0x180075dde  mov     rcx, cs:WPP_GLOBAL_Control
0x180075de5  lea     r14, WPP_GLOBAL_Control
0x180075dec  lea     ebx, [rax+8]
0x180075def  cmp     rcx, r14
0x180075df2  jz      loc_180075F6E
0x180075df8  test    [rcx+1Ch], r13d
0x180075dfc  jz      short loc_180075E2E
0x180075dfe  cmp     byte ptr [rcx+19h], 2
0x180075e02  jb      short loc_180075E2E
0x180075e04  call    cs:__imp_GetLastError
0x180075e0a  mov     rcx, cs:WPP_GLOBAL_Control
0x180075e11  lea     edx, [rsi+51h]
0x180075e14  mov     r9d, eax
0x180075e17  lea     r8, WPP_1a1a310d9f3938633825d91885f62d23_Traceguids
0x180075e1e  mov     rcx, [rcx+10h]
0x180075e22  call    WPP_SF_d
0x180075e27  mov     rcx, cs:WPP_GLOBAL_Control
0x180075e2e  cmp     rcx, r14
0x180075e31  jz      loc_180075F6E
0x180075e37  test    [rcx+1Ch], r13d
0x180075e3b  jz      loc_180075F6E
0x180075e41  cmp     byte ptr [rcx+19h], 6
0x180075e45  jb      loc_180075F6E
0x180075e4b  mov     edx, 52h ; 'R'
0x180075e50  jmp     loc_180075F5B
0x180075e55  mov     dword ptr [rbp+var_20], ebx
0x180075e58  lea     rcx, NatInterfaceLock; lpCriticalSection
0x180075e5f  xor     ebx, ebx
0x180075e61  mov     byte ptr [rbp+var_20+4], dil
0x180075e65  mov     dword ptr [rbp+var_20+8], ebx
0x180075e68  mov     word ptr [rbp+var_20+6], r14w
0x180075e6d  mov     word ptr [rbp+var_20+0Ch], r12w
0x180075e72  mov     [rbp+var_10], r15d
0x180075e76  call    cs:__imp_EnterCriticalSection
0x180075e7c  mov     rcx, cs:NatFileHandle; FileHandle
0x180075e83  lea     rax, [rbp+var_20]
0x180075e87  mov     [rsp+80h+OutputBufferLength], ebx; OutputBufferLength
0x180075e8b  xor     r9d, r9d; ApcContext
0x180075e8e  mov     [rsp+80h+OutputBuffer], rbx; OutputBuffer
0x180075e93  xor     r8d, r8d; ApcRoutine
0x180075e96  mov     [rsp+80h+InputBufferLength], 14h; InputBufferLength
0x180075e9e  mov     rdx, rsi; Event
0x180075ea1  mov     [rsp+80h+InputBuffer], rax; InputBuffer
0x180075ea6  lea     rax, [rbp+var_30]
0x180075eaa  mov     [rsp+80h+IoControlCode], 128068h; IoControlCode
0x180075eb2  mov     [rsp+80h+IoStatusBlock], rax; IoStatusBlock
0x180075eb7  call    cs:__imp_NtDeviceIoControlFile
0x180075ebd  lea     rcx, NatInterfaceLock; lpCriticalSection
0x180075ec4  mov     edi, eax
0x180075ec6  call    cs:__imp_LeaveCriticalSection
0x180075ecc  cmp     edi, 103h
0x180075ed2  jnz     short loc_180075EE3
0x180075ed4  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180075ed7  mov     rcx, rsi; hHandle
0x180075eda  call    cs:__imp_WaitForSingleObject
0x180075ee0  mov     edi, dword ptr [rbp+var_30]
0x180075ee3  test    edi, edi
0x180075ee5  js      short loc_180075EF0
0x180075ee7  lea     r14, WPP_GLOBAL_Control
0x180075eee  jmp     short loc_180075F35
0x180075ef0  mov     ecx, edi; Status
0x180075ef2  call    cs:__imp_RtlNtStatusToDosError
0x180075ef8  mov     ebx, eax
0x180075efa  mov     rcx, cs:WPP_GLOBAL_Control
0x180075f01  lea     r14, WPP_GLOBAL_Control
0x180075f08  cmp     rcx, r14
0x180075f0b  jz      short loc_180075F35
0x180075f0d  test    [rcx+1Ch], r13d
0x180075f11  jz      short loc_180075F35
0x180075f13  cmp     byte ptr [rcx+19h], 2
0x180075f17  jb      short loc_180075F35
0x180075f19  mov     rcx, [rcx+10h]
0x180075f1d  lea     r8, WPP_1a1a310d9f3938633825d91885f62d23_Traceguids
0x180075f24  mov     edx, 53h ; 'S'
0x180075f29  mov     dword ptr [rsp+80h+IoStatusBlock], eax
0x180075f2d  mov     r9d, edi
0x180075f30  call    WPP_SF_Dd
0x180075f35  mov     rcx, rsi; hObject
0x180075f38  call    cs:__imp_CloseHandle
0x180075f3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180075f45  cmp     rcx, r14
0x180075f48  jz      short loc_180075F6E
0x180075f4a  test    [rcx+1Ch], r13d
0x180075f4e  jz      short loc_180075F6E
0x180075f50  cmp     byte ptr [rcx+19h], 6
0x180075f54  jb      short loc_180075F6E
0x180075f56  mov     edx, 54h ; 'T'
0x180075f5b  mov     rcx, [rcx+10h]
0x180075f5f  lea     r8, WPP_1a1a310d9f3938633825d91885f62d23_Traceguids
0x180075f66  mov     r9d, ebx
0x180075f69  call    WPP_SF_d
0x180075f6e  mov     eax, ebx
0x180075f70  mov     rcx, [rbp+var_8]
0x180075f74  xor     rcx, rsp; StackCookie
0x180075f77  call    __security_check_cookie
0x180075f7c  mov     rbx, [rsp+80h+arg_18]
0x180075f84  add     rsp, 80h
0x180075f8b  pop     r15
0x180075f8d  pop     r14
0x180075f8f  pop     r13
0x180075f91  pop     r12
0x180075f93  pop     rdi
0x180075f94  pop     rsi
0x180075f95  pop     rbp
0x180075f96  retn
```
