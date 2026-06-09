# NatConfigureDriver

- ea: `0x1800376fc`
- end: `0x1800378fe`
- name: `NatConfigureDriver`
- size: `514`
- prototype: `__int64 __fastcall(PVOID InputBuffer)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180042df4`
- `0x180073920`

## callees

- `0x18000c110`
- `0x18000c750`
- `0x1800376fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003775c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003775c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800377b6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800377b6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180037741`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180037741`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180037889`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180037889`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003782c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003782c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800377c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800377c7`
- `ntdll!NtDeviceIoControlFile` at `0x18003779c`
- `ntdll!NtDeviceIoControlFile` at `0x18003779c`
- `ntdll!RtlNtStatusToDosError` at `0x1800378c5`
- `ntdll!RtlNtStatusToDosError` at `0x1800378c5`

## pseudocode

```c
__int64 __fastcall NatConfigureDriver(PVOID InputBuffer)
{
  HANDLE EventW; // rsi
  ULONG v3; // edi
  int Status; // ebx
  PVOID *v6; // rcx
  DWORD LastError; // eax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-48h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids);
  }
  IoStatusBlock = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  if ( EventW )
  {
    v3 = 0;
    EnterCriticalSection(&NatInterfaceLock);
    Status = NtDeviceIoControlFile(
               NatFileHandle,
               EventW,
               0,
               0,
               &IoStatusBlock,
               0x128000u,
               InputBuffer,
               *((_DWORD *)InputBuffer + 3) + 8,
               0,
               0);
    if ( Status == 259 )
    {
      WaitForSingleObject(EventW, 0xFFFFFFFF);
      Status = IoStatusBlock.Status;
    }
    LeaveCriticalSection(&NatInterfaceLock);
    if ( Status < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          43,
          &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids,
          (unsigned int)Status);
      }
      v3 = RtlNtStatusToDosError(Status);
    }
    CloseHandle(EventW);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids, v3);
    }
    return v3;
  }
  else
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids, LastError);
        v6 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v6 != &WPP_GLOBAL_Control && (*((_DWORD *)v6 + 7) & 0x200) != 0 && *((_BYTE *)v6 + 25) >= 6u )
        WPP_SF_d(v6[2], 42, &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids, 8);
    }
    return 8;
  }
}

```

## disassembly

```asm
0x1800376fc  push    rbx
0x1800376fe  push    rbp
0x1800376ff  push    rsi
0x180037700  push    rdi
0x180037701  push    r14
0x180037703  push    r15
0x180037705  sub     rsp, 68h
0x180037709  mov     rbx, rcx
0x18003770c  mov     rcx, cs:WPP_GLOBAL_Control
0x180037713  lea     r14, WPP_GLOBAL_Control
0x18003771a  lea     r15, WPP_1a1a310d9f3938633825d91885f62d23_Traceguids
0x180037721  mov     ebp, 200h
0x180037726  cmp     rcx, r14
0x180037729  jnz     loc_1800377EC
0x18003772f  xorps   xmm0, xmm0
0x180037732  xor     r9d, r9d; lpName
0x180037735  xor     r8d, r8d; bInitialState
0x180037738  xor     edx, edx; bManualReset
0x18003773a  xor     ecx, ecx; lpEventAttributes
0x18003773c  movups  xmmword ptr [rsp+98h+var_48], xmm0
0x180037741  call    cs:__imp_CreateEventW
0x180037747  mov     rsi, rax
0x18003774a  test    rax, rax
0x18003774d  jz      loc_180037815
0x180037753  lea     rcx, NatInterfaceLock; lpCriticalSection
0x18003775a  xor     edi, edi
0x18003775c  call    cs:__imp_EnterCriticalSection
0x180037762  mov     eax, [rbx+0Ch]
0x180037765  xor     r9d, r9d; ApcContext
0x180037768  mov     rcx, cs:NatFileHandle; FileHandle
0x18003776f  add     eax, 8
0x180037772  mov     [rsp+98h+OutputBufferLength], edi; OutputBufferLength
0x180037776  xor     r8d, r8d; ApcRoutine
0x180037779  mov     [rsp+98h+OutputBuffer], rdi; OutputBuffer
0x18003777e  mov     rdx, rsi; Event
0x180037781  mov     [rsp+98h+InputBufferLength], eax; InputBufferLength
0x180037785  lea     rax, [rsp+98h+var_48]
0x18003778a  mov     [rsp+98h+InputBuffer], rbx; InputBuffer
0x18003778f  mov     [rsp+98h+IoControlCode], 128000h; IoControlCode
0x180037797  mov     [rsp+98h+IoStatusBlock], rax; IoStatusBlock
0x18003779c  call    cs:__imp_NtDeviceIoControlFile
0x1800377a2  mov     ebx, eax
0x1800377a4  cmp     eax, 103h
0x1800377a9  jz      loc_180037883
0x1800377af  lea     rcx, NatInterfaceLock; lpCriticalSection
0x1800377b6  call    cs:__imp_LeaveCriticalSection
0x1800377bc  test    ebx, ebx
0x1800377be  js      loc_180037898
0x1800377c4  mov     rcx, rsi; hObject
0x1800377c7  call    cs:__imp_CloseHandle
0x1800377cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800377d4  cmp     rcx, r14
0x1800377d7  jnz     loc_1800378D2
0x1800377dd  mov     eax, edi
0x1800377df  add     rsp, 68h
0x1800377e3  pop     r15
0x1800377e5  pop     r14
0x1800377e7  pop     rdi
0x1800377e8  pop     rsi
0x1800377e9  pop     rbp
0x1800377ea  pop     rbx
0x1800377eb  retn
0x1800377ec  test    [rcx+1Ch], ebp
0x1800377ef  jz      loc_18003772F
0x1800377f5  cmp     byte ptr [rcx+19h], 6
0x1800377f9  jb      loc_18003772F
0x1800377ff  mov     rcx, [rcx+10h]
0x180037803  mov     edx, 28h ; '('
0x180037808  mov     r8, r15
0x18003780b  call    WPP_SF_
0x180037810  jmp     loc_18003772F
0x180037815  mov     rcx, cs:WPP_GLOBAL_Control
0x18003781c  cmp     rcx, r14
0x18003781f  jz      short loc_180037879
0x180037821  test    [rcx+1Ch], ebp
0x180037824  jz      short loc_180037854
0x180037826  cmp     byte ptr [rcx+19h], 2
0x18003782a  jb      short loc_180037854
0x18003782c  call    cs:__imp_GetLastError
0x180037832  mov     rcx, cs:WPP_GLOBAL_Control
0x180037839  mov     edx, 29h ; ')'
0x18003783e  mov     r9d, eax
0x180037841  mov     r8, r15
0x180037844  mov     rcx, [rcx+10h]
0x180037848  call    WPP_SF_d
0x18003784d  mov     rcx, cs:WPP_GLOBAL_Control
0x180037854  cmp     rcx, r14
0x180037857  jz      short loc_180037879
0x180037859  test    [rcx+1Ch], ebp
0x18003785c  jz      short loc_180037879
0x18003785e  cmp     byte ptr [rcx+19h], 6
0x180037862  jb      short loc_180037879
0x180037864  mov     rcx, [rcx+10h]
0x180037868  mov     edx, 2Ah ; '*'
0x18003786d  mov     r8, r15
0x180037870  lea     r9d, [rdx-22h]
0x180037874  call    WPP_SF_d
0x180037879  mov     eax, 8
0x18003787e  jmp     loc_1800377DF
0x180037883  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180037886  mov     rcx, rsi; hHandle
0x180037889  call    cs:__imp_WaitForSingleObject
0x18003788f  mov     ebx, dword ptr [rsp+98h+var_48]
0x180037893  jmp     loc_1800377AF
0x180037898  mov     rcx, cs:WPP_GLOBAL_Control
0x18003789f  cmp     rcx, r14
0x1800378a2  jz      short loc_1800378C3
0x1800378a4  test    [rcx+1Ch], ebp
0x1800378a7  jz      short loc_1800378C3
0x1800378a9  cmp     byte ptr [rcx+19h], 2
0x1800378ad  jb      short loc_1800378C3
0x1800378af  mov     rcx, [rcx+10h]
0x1800378b3  mov     edx, 2Bh ; '+'
0x1800378b8  mov     r9d, ebx
0x1800378bb  mov     r8, r15
0x1800378be  call    WPP_SF_d
0x1800378c3  mov     ecx, ebx; Status
0x1800378c5  call    cs:__imp_RtlNtStatusToDosError
0x1800378cb  mov     edi, eax
0x1800378cd  jmp     loc_1800377C4
0x1800378d2  test    [rcx+1Ch], ebp
0x1800378d5  jz      loc_1800377DD
0x1800378db  cmp     byte ptr [rcx+19h], 6
0x1800378df  jb      loc_1800377DD
0x1800378e5  mov     rcx, [rcx+10h]
0x1800378e9  mov     edx, 2Ch ; ','
0x1800378ee  mov     r9d, edi
0x1800378f1  mov     r8, r15
0x1800378f4  call    WPP_SF_d
0x1800378f9  jmp     loc_1800377DD
```
