# NatCreateTicket

- ea: `0x18007bb0c`
- end: `0x18007bdb0`
- name: `NatCreateTicket`
- size: `676`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180079f30`
- `0x18007a534`

## callees

- `0x18000d090`
- `0x1800202e0`
- `0x18004f290`
- `0x180051f30`
- `0x18007bb0c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007bc6a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007bc6a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007bcc6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007bcc6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007bbb8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007bbb8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007bce0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007bce0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007bbf2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007bbf2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007bd4a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007bd4a`
- `ntdll!NtDeviceIoControlFile` at `0x18007bcb1`
- `ntdll!NtDeviceIoControlFile` at `0x18007bcb1`
- `ntdll!RtlNtStatusToDosError` at `0x18007bcfe`
- `ntdll!RtlNtStatusToDosError` at `0x18007bcfe`

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
0x18007bb0c  mov     [rsp-38h+arg_18], rbx
0x18007bb11  push    rbp
0x18007bb12  push    rsi
0x18007bb13  push    rdi
0x18007bb14  push    r12
0x18007bb16  push    r13
0x18007bb18  push    r14
0x18007bb1a  push    r15
0x18007bb1c  mov     rbp, rsp
0x18007bb1f  sub     rsp, 80h
0x18007bb26  mov     rax, cs:__security_cookie
0x18007bb2d  xor     rax, rsp
0x18007bb30  mov     [rbp+var_8], rax
0x18007bb34  movzx   r14d, r8w
0x18007bb38  mov     ebx, ecx
0x18007bb3a  movzx   edi, dl
0x18007bb3d  mov     rcx, cs:WPP_GLOBAL_Control
0x18007bb44  lea     rax, WPP_GLOBAL_Control
0x18007bb4b  mov     r15d, [rbp+arg_28]
0x18007bb4f  mov     r13d, 200h
0x18007bb55  movzx   r12d, [rbp+arg_20]
0x18007bb5a  cmp     rcx, rax
0x18007bb5d  jz      short loc_18007BB9E
0x18007bb5f  test    [rcx+1Ch], r13d
0x18007bb63  jz      short loc_18007BB9E
0x18007bb65  cmp     byte ptr [rcx+19h], 6
0x18007bb69  jb      short loc_18007BB9E
0x18007bb6b  mov     rcx, [rcx+10h]
0x18007bb6f  lea     r8, WPP_1a1a310d9f3938633825d91885f62d23_Traceguids
0x18007bb76  mov     dword ptr [rsp+80h+OutputBuffer], r15d
0x18007bb7b  mov     edx, 50h ; 'P'
0x18007bb80  mov     [rsp+80h+InputBufferLength], r12d
0x18007bb85  mov     r9d, ebx
0x18007bb88  mov     dword ptr [rsp+80h+InputBuffer], 0
0x18007bb90  mov     [rsp+80h+IoControlCode], r14d
0x18007bb95  mov     dword ptr [rsp+80h+IoStatusBlock], edi
0x18007bb99  call    WPP_SF_dddddd
0x18007bb9e  xorps   xmm0, xmm0
0x18007bba1  xor     eax, eax
0x18007bba3  xor     r9d, r9d; lpName
0x18007bba6  mov     [rbp+var_10], eax
0x18007bba9  xor     r8d, r8d; bInitialState
0x18007bbac  xor     edx, edx; bManualReset
0x18007bbae  xor     ecx, ecx; lpEventAttributes
0x18007bbb0  movups  [rbp+var_20], xmm0
0x18007bbb4  movups  xmmword ptr [rbp+var_30], xmm0
0x18007bbb8  call    cs:__imp_CreateEventW
0x18007bbbf  nop     dword ptr [rax+rax+00h]
0x18007bbc4  mov     rsi, rax
0x18007bbc7  test    rax, rax
0x18007bbca  jnz     short loc_18007BC49
0x18007bbcc  mov     rcx, cs:WPP_GLOBAL_Control
0x18007bbd3  lea     r14, WPP_GLOBAL_Control
0x18007bbda  lea     ebx, [rax+8]
0x18007bbdd  cmp     rcx, r14
0x18007bbe0  jz      loc_18007BD86
0x18007bbe6  test    [rcx+1Ch], r13d
0x18007bbea  jz      short loc_18007BC22
0x18007bbec  cmp     byte ptr [rcx+19h], 2
0x18007bbf0  jb      short loc_18007BC22
0x18007bbf2  call    cs:__imp_GetLastError
0x18007bbf9  nop     dword ptr [rax+rax+00h]
0x18007bbfe  mov     rcx, cs:WPP_GLOBAL_Control
0x18007bc05  lea     edx, [rsi+51h]
0x18007bc08  mov     r9d, eax
0x18007bc0b  lea     r8, WPP_1a1a310d9f3938633825d91885f62d23_Traceguids
0x18007bc12  mov     rcx, [rcx+10h]
0x18007bc16  call    WPP_SF_d
0x18007bc1b  mov     rcx, cs:WPP_GLOBAL_Control
0x18007bc22  cmp     rcx, r14
0x18007bc25  jz      loc_18007BD86
0x18007bc2b  test    [rcx+1Ch], r13d
0x18007bc2f  jz      loc_18007BD86
0x18007bc35  cmp     byte ptr [rcx+19h], 6
0x18007bc39  jb      loc_18007BD86
0x18007bc3f  mov     edx, 52h ; 'R'
0x18007bc44  jmp     loc_18007BD73
0x18007bc49  mov     dword ptr [rbp+var_20], ebx
0x18007bc4c  lea     rcx, NatInterfaceLock; lpCriticalSection
0x18007bc53  xor     ebx, ebx
0x18007bc55  mov     byte ptr [rbp+var_20+4], dil
0x18007bc59  mov     dword ptr [rbp+var_20+8], ebx
0x18007bc5c  mov     word ptr [rbp+var_20+6], r14w
0x18007bc61  mov     word ptr [rbp+var_20+0Ch], r12w
0x18007bc66  mov     [rbp+var_10], r15d
0x18007bc6a  call    cs:__imp_EnterCriticalSection
0x18007bc71  nop     dword ptr [rax+rax+00h]
0x18007bc76  mov     rcx, cs:NatFileHandle; FileHandle
0x18007bc7d  lea     rax, [rbp+var_20]
0x18007bc81  mov     [rsp+80h+OutputBufferLength], ebx; OutputBufferLength
0x18007bc85  xor     r9d, r9d; ApcContext
0x18007bc88  mov     [rsp+80h+OutputBuffer], rbx; OutputBuffer
0x18007bc8d  xor     r8d, r8d; ApcRoutine
0x18007bc90  mov     [rsp+80h+InputBufferLength], 14h; InputBufferLength
0x18007bc98  mov     rdx, rsi; Event
0x18007bc9b  mov     [rsp+80h+InputBuffer], rax; InputBuffer
0x18007bca0  lea     rax, [rbp+var_30]
0x18007bca4  mov     [rsp+80h+IoControlCode], 128068h; IoControlCode
0x18007bcac  mov     [rsp+80h+IoStatusBlock], rax; IoStatusBlock
0x18007bcb1  call    cs:__imp_NtDeviceIoControlFile
0x18007bcb8  nop     dword ptr [rax+rax+00h]
0x18007bcbd  lea     rcx, NatInterfaceLock; lpCriticalSection
0x18007bcc4  mov     edi, eax
0x18007bcc6  call    cs:__imp_LeaveCriticalSection
0x18007bccd  nop     dword ptr [rax+rax+00h]
0x18007bcd2  cmp     edi, 103h
0x18007bcd8  jnz     short loc_18007BCEF
0x18007bcda  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18007bcdd  mov     rcx, rsi; hHandle
0x18007bce0  call    cs:__imp_WaitForSingleObject
0x18007bce7  nop     dword ptr [rax+rax+00h]
0x18007bcec  mov     edi, dword ptr [rbp+var_30]
0x18007bcef  test    edi, edi
0x18007bcf1  js      short loc_18007BCFC
0x18007bcf3  lea     r14, WPP_GLOBAL_Control
0x18007bcfa  jmp     short loc_18007BD47
0x18007bcfc  mov     ecx, edi; Status
0x18007bcfe  call    cs:__imp_RtlNtStatusToDosError
0x18007bd05  nop     dword ptr [rax+rax+00h]
0x18007bd0a  mov     ebx, eax
0x18007bd0c  mov     rcx, cs:WPP_GLOBAL_Control
0x18007bd13  lea     r14, WPP_GLOBAL_Control
0x18007bd1a  cmp     rcx, r14
0x18007bd1d  jz      short loc_18007BD47
0x18007bd1f  test    [rcx+1Ch], r13d
0x18007bd23  jz      short loc_18007BD47
0x18007bd25  cmp     byte ptr [rcx+19h], 2
0x18007bd29  jb      short loc_18007BD47
0x18007bd2b  mov     rcx, [rcx+10h]
0x18007bd2f  lea     r8, WPP_1a1a310d9f3938633825d91885f62d23_Traceguids
0x18007bd36  mov     edx, 53h ; 'S'
0x18007bd3b  mov     dword ptr [rsp+80h+IoStatusBlock], eax
0x18007bd3f  mov     r9d, edi
0x18007bd42  call    WPP_SF_Dd
0x18007bd47  mov     rcx, rsi; hObject
0x18007bd4a  call    cs:__imp_CloseHandle
0x18007bd51  nop     dword ptr [rax+rax+00h]
0x18007bd56  mov     rcx, cs:WPP_GLOBAL_Control
0x18007bd5d  cmp     rcx, r14
0x18007bd60  jz      short loc_18007BD86
0x18007bd62  test    [rcx+1Ch], r13d
0x18007bd66  jz      short loc_18007BD86
0x18007bd68  cmp     byte ptr [rcx+19h], 6
0x18007bd6c  jb      short loc_18007BD86
0x18007bd6e  mov     edx, 54h ; 'T'
0x18007bd73  mov     rcx, [rcx+10h]
0x18007bd77  lea     r8, WPP_1a1a310d9f3938633825d91885f62d23_Traceguids
0x18007bd7e  mov     r9d, ebx
0x18007bd81  call    WPP_SF_d
0x18007bd86  mov     eax, ebx
0x18007bd88  mov     rcx, [rbp+var_8]
0x18007bd8c  xor     rcx, rsp; StackCookie
0x18007bd8f  call    __security_check_cookie
0x18007bd94  mov     rbx, [rsp+80h+arg_18]
0x18007bd9c  add     rsp, 80h
0x18007bda3  pop     r15
0x18007bda5  pop     r14
0x18007bda7  pop     r13
0x18007bda9  pop     r12
0x18007bdab  pop     rdi
0x18007bdac  pop     rsi
0x18007bdad  pop     rbp
0x18007bdae  retn
```
