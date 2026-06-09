# NatConfigureDriver

- ea: `0x18003a3b4`
- end: `0x18003a5e7`
- name: `NatConfigureDriver`
- size: `563`
- prototype: `__int64 __fastcall(PVOID InputBuffer)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800466fc`
- `0x180079490`

## callees

- `0x18000ca20`
- `0x18000d090`
- `0x18003a3b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003a41a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003a41a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003a480`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003a480`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003a3f9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003a3f9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003a566`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003a566`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a503`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a503`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a497`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a497`
- `ntdll!NtDeviceIoControlFile` at `0x18003a460`
- `ntdll!NtDeviceIoControlFile` at `0x18003a460`
- `ntdll!RtlNtStatusToDosError` at `0x18003a5a8`
- `ntdll!RtlNtStatusToDosError` at `0x18003a5a8`

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
0x18003a3b4  push    rbx
0x18003a3b6  push    rbp
0x18003a3b7  push    rsi
0x18003a3b8  push    rdi
0x18003a3b9  push    r14
0x18003a3bb  push    r15
0x18003a3bd  sub     rsp, 68h
0x18003a3c1  mov     rbx, rcx
0x18003a3c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a3cb  lea     r14, WPP_GLOBAL_Control
0x18003a3d2  lea     r15, WPP_1a1a310d9f3938633825d91885f62d23_Traceguids
0x18003a3d9  mov     ebp, 200h
0x18003a3de  cmp     rcx, r14
0x18003a3e1  jnz     loc_18003A4C3
0x18003a3e7  xorps   xmm0, xmm0
0x18003a3ea  xor     r9d, r9d; lpName
0x18003a3ed  xor     r8d, r8d; bInitialState
0x18003a3f0  xor     edx, edx; bManualReset
0x18003a3f2  xor     ecx, ecx; lpEventAttributes
0x18003a3f4  movups  xmmword ptr [rsp+98h+var_48], xmm0
0x18003a3f9  call    cs:__imp_CreateEventW
0x18003a400  nop     dword ptr [rax+rax+00h]
0x18003a405  mov     rsi, rax
0x18003a408  test    rax, rax
0x18003a40b  jz      loc_18003A4EC
0x18003a411  lea     rcx, NatInterfaceLock; lpCriticalSection
0x18003a418  xor     edi, edi
0x18003a41a  call    cs:__imp_EnterCriticalSection
0x18003a421  nop     dword ptr [rax+rax+00h]
0x18003a426  mov     eax, [rbx+0Ch]
0x18003a429  xor     r9d, r9d; ApcContext
0x18003a42c  mov     rcx, cs:NatFileHandle; FileHandle
0x18003a433  add     eax, 8
0x18003a436  mov     [rsp+98h+OutputBufferLength], edi; OutputBufferLength
0x18003a43a  xor     r8d, r8d; ApcRoutine
0x18003a43d  mov     [rsp+98h+OutputBuffer], rdi; OutputBuffer
0x18003a442  mov     rdx, rsi; Event
0x18003a445  mov     [rsp+98h+InputBufferLength], eax; InputBufferLength
0x18003a449  lea     rax, [rsp+98h+var_48]
0x18003a44e  mov     [rsp+98h+InputBuffer], rbx; InputBuffer
0x18003a453  mov     [rsp+98h+IoControlCode], 128000h; IoControlCode
0x18003a45b  mov     [rsp+98h+IoStatusBlock], rax; IoStatusBlock
0x18003a460  call    cs:__imp_NtDeviceIoControlFile
0x18003a467  nop     dword ptr [rax+rax+00h]
0x18003a46c  mov     ebx, eax
0x18003a46e  cmp     eax, 103h
0x18003a473  jz      loc_18003A560
0x18003a479  lea     rcx, NatInterfaceLock; lpCriticalSection
0x18003a480  call    cs:__imp_LeaveCriticalSection
0x18003a487  nop     dword ptr [rax+rax+00h]
0x18003a48c  test    ebx, ebx
0x18003a48e  js      loc_18003A57B
0x18003a494  mov     rcx, rsi; hObject
0x18003a497  call    cs:__imp_CloseHandle
0x18003a49e  nop     dword ptr [rax+rax+00h]
0x18003a4a3  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a4aa  cmp     rcx, r14
0x18003a4ad  jnz     loc_18003A5BB
0x18003a4b3  mov     eax, edi
0x18003a4b5  add     rsp, 68h
0x18003a4b9  pop     r15
0x18003a4bb  pop     r14
0x18003a4bd  pop     rdi
0x18003a4be  pop     rsi
0x18003a4bf  pop     rbp
0x18003a4c0  pop     rbx
0x18003a4c1  retn
0x18003a4c3  test    [rcx+1Ch], ebp
0x18003a4c6  jz      loc_18003A3E7
0x18003a4cc  cmp     byte ptr [rcx+19h], 6
0x18003a4d0  jb      loc_18003A3E7
0x18003a4d6  mov     rcx, [rcx+10h]
0x18003a4da  mov     edx, 28h ; '('
0x18003a4df  mov     r8, r15
0x18003a4e2  call    WPP_SF_
0x18003a4e7  jmp     loc_18003A3E7
0x18003a4ec  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a4f3  cmp     rcx, r14
0x18003a4f6  jz      short loc_18003A556
0x18003a4f8  test    [rcx+1Ch], ebp
0x18003a4fb  jz      short loc_18003A531
0x18003a4fd  cmp     byte ptr [rcx+19h], 2
0x18003a501  jb      short loc_18003A531
0x18003a503  call    cs:__imp_GetLastError
0x18003a50a  nop     dword ptr [rax+rax+00h]
0x18003a50f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a516  mov     edx, 29h ; ')'
0x18003a51b  mov     r9d, eax
0x18003a51e  mov     r8, r15
0x18003a521  mov     rcx, [rcx+10h]
0x18003a525  call    WPP_SF_d
0x18003a52a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a531  cmp     rcx, r14
0x18003a534  jz      short loc_18003A556
0x18003a536  test    [rcx+1Ch], ebp
0x18003a539  jz      short loc_18003A556
0x18003a53b  cmp     byte ptr [rcx+19h], 6
0x18003a53f  jb      short loc_18003A556
0x18003a541  mov     rcx, [rcx+10h]
0x18003a545  mov     edx, 2Ah ; '*'
0x18003a54a  mov     r8, r15
0x18003a54d  lea     r9d, [rdx-22h]
0x18003a551  call    WPP_SF_d
0x18003a556  mov     eax, 8
0x18003a55b  jmp     loc_18003A4B5
0x18003a560  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18003a563  mov     rcx, rsi; hHandle
0x18003a566  call    cs:__imp_WaitForSingleObject
0x18003a56d  nop     dword ptr [rax+rax+00h]
0x18003a572  mov     ebx, dword ptr [rsp+98h+var_48]
0x18003a576  jmp     loc_18003A479
0x18003a57b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a582  cmp     rcx, r14
0x18003a585  jz      short loc_18003A5A6
0x18003a587  test    [rcx+1Ch], ebp
0x18003a58a  jz      short loc_18003A5A6
0x18003a58c  cmp     byte ptr [rcx+19h], 2
0x18003a590  jb      short loc_18003A5A6
0x18003a592  mov     rcx, [rcx+10h]
0x18003a596  mov     edx, 2Bh ; '+'
0x18003a59b  mov     r9d, ebx
0x18003a59e  mov     r8, r15
0x18003a5a1  call    WPP_SF_d
0x18003a5a6  mov     ecx, ebx; Status
0x18003a5a8  call    cs:__imp_RtlNtStatusToDosError
0x18003a5af  nop     dword ptr [rax+rax+00h]
0x18003a5b4  mov     edi, eax
0x18003a5b6  jmp     loc_18003A494
0x18003a5bb  test    [rcx+1Ch], ebp
0x18003a5be  jz      loc_18003A4B3
0x18003a5c4  cmp     byte ptr [rcx+19h], 6
0x18003a5c8  jb      loc_18003A4B3
0x18003a5ce  mov     rcx, [rcx+10h]
0x18003a5d2  mov     edx, 2Ch ; ','
0x18003a5d7  mov     r9d, edi
0x18003a5da  mov     r8, r15
0x18003a5dd  call    WPP_SF_d
0x18003a5e2  jmp     loc_18003A4B3
```
