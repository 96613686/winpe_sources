# NatUnbindInterface

- ea: `0x1800402a0`
- end: `0x180040589`
- name: `NatUnbindInterface`
- size: `745`
- prototype: `__int64 __fastcall(unsigned int, struct _NAT_INTERFACE *)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x18004c718`
- `0x180073df8`

## callees

- `0x18000c110`
- `0x18000c750`
- `0x18001ec08`
- `0x180032e10`
- `0x1800402a0`
- `0x18007e4a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180040381`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180040381`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800403a4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040417`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800404fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800403a4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040417`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800404fb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180040302`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180040302`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800404ea`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800404ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040327`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040327`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180040504`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180040504`
- `ntdll!NtDeviceIoControlFile` at `0x1800404d5`
- `ntdll!NtDeviceIoControlFile` at `0x1800404d5`
- `ntdll!RtlNtStatusToDosError` at `0x180040514`
- `ntdll!RtlNtStatusToDosError` at `0x180040514`

## pseudocode

```c
__int64 __fastcall NatUnbindInterface(unsigned int a1, struct _NAT_INTERFACE *a2)
{
  HANDLE EventW; // rsi
  PVOID *v5; // rcx
  DWORD LastError; // eax
  PVOID *v8; // rcx
  int v9; // eax
  PVOID *v10; // rcx
  bool v11; // zf
  int Status; // edi
  ULONG v13; // ebx
  ULONG v14; // eax
  PVOID *v15; // rcx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-48h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 150, &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids, a1);
  }
  IoStatusBlock = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  if ( !EventW )
  {
    v5 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 151, &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids, LastError);
        v5 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v5 != &WPP_GLOBAL_Control && (*((_DWORD *)v5 + 7) & 0x200) != 0 && *((_BYTE *)v5 + 25) >= 6u )
        WPP_SF_(v5[2], 152, &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids);
    }
    return 8;
  }
  EnterCriticalSection(&NatInterfaceLock);
  if ( !a2 )
  {
    a2 = NatLookupInterface(a1, 0);
    if ( !a2 )
    {
      LeaveCriticalSection(&NatInterfaceLock);
      v8 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 153, &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids, a1);
          v8 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v8 != &WPP_GLOBAL_Control && (*((_DWORD *)v8 + 7) & 0x200) != 0 && *((_BYTE *)v8 + 25) >= 6u )
          WPP_SF_(v8[2], 154, &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids);
      }
      return 905;
    }
  }
  v9 = *((_DWORD *)a2 + 7);
  if ( (v9 & 0x40000000) != 0 )
  {
    v11 = *((_DWORD *)a2 + 6) == 3;
    *((_DWORD *)a2 + 7) = v9 & 0xBFFFFFFF;
    if ( v11 )
      NatUpdateProxyArp(a2, 0);
    Status = NtDeviceIoControlFile(NatFileHandle, EventW, 0, 0, &IoStatusBlock, 0x12800Cu, (char *)a2 + 20, 4u, 0, 0);
    if ( Status == 259 )
    {
      WaitForSingleObject(EventW, 0xFFFFFFFF);
      Status = IoStatusBlock.Status;
    }
    LeaveCriticalSection(&NatInterfaceLock);
    CloseHandle(EventW);
    if ( Status < 0 )
    {
      v14 = RtlNtStatusToDosError(Status);
      v13 = v14;
      if ( v14 )
      {
        v15 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          return v13;
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
LABEL_48:
          if ( v15 != &WPP_GLOBAL_Control && (*((_DWORD *)v15 + 7) & 0x200) != 0 && *((_BYTE *)v15 + 25) >= 6u )
            WPP_SF_d(v15[2], 158, &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids, v13);
          return v13;
        }
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          157,
          &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids,
          (unsigned int)Status,
          v14);
      }
    }
    else
    {
      v13 = 0;
    }
    v15 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_48;
  }
  LeaveCriticalSection(&NatInterfaceLock);
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 155, &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids, a1);
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v10 != &WPP_GLOBAL_Control && (*((_DWORD *)v10 + 7) & 0x200) != 0 && *((_BYTE *)v10 + 25) >= 6u )
      WPP_SF_(v10[2], 156, &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids);
  }
  return 1228;
}

```

## disassembly

```asm
0x1800402a0  push    rbx
0x1800402a2  push    rbp
0x1800402a3  push    rsi
0x1800402a4  push    rdi
0x1800402a5  push    r14
0x1800402a7  push    r15
0x1800402a9  sub     rsp, 68h
0x1800402ad  mov     rbx, rdx
0x1800402b0  mov     edi, ecx
0x1800402b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800402b9  lea     r14, WPP_GLOBAL_Control
0x1800402c0  lea     r15, WPP_1a1a310d9f3938633825d91885f62d23_Traceguids
0x1800402c7  mov     ebp, 200h
0x1800402cc  cmp     rcx, r14
0x1800402cf  jz      short loc_1800402F0
0x1800402d1  test    [rcx+1Ch], ebp
0x1800402d4  jz      short loc_1800402F0
0x1800402d6  cmp     byte ptr [rcx+19h], 6
0x1800402da  jb      short loc_1800402F0
0x1800402dc  mov     rcx, [rcx+10h]
0x1800402e0  mov     edx, 96h
0x1800402e5  mov     r9d, edi
0x1800402e8  mov     r8, r15
0x1800402eb  call    WPP_SF_d
0x1800402f0  xorps   xmm0, xmm0
0x1800402f3  xor     r9d, r9d; lpName
0x1800402f6  xor     r8d, r8d; bInitialState
0x1800402f9  xor     edx, edx; bManualReset
0x1800402fb  xor     ecx, ecx; lpEventAttributes
0x1800402fd  movups  xmmword ptr [rsp+98h+var_48], xmm0
0x180040302  call    cs:__imp_CreateEventW
0x180040308  mov     rsi, rax
0x18004030b  test    rax, rax
0x18004030e  jnz     short loc_18004037A
0x180040310  mov     rcx, cs:WPP_GLOBAL_Control
0x180040317  cmp     rcx, r14
0x18004031a  jz      short loc_180040370
0x18004031c  test    [rcx+1Ch], ebp
0x18004031f  jz      short loc_18004034F
0x180040321  cmp     byte ptr [rcx+19h], 2
0x180040325  jb      short loc_18004034F
0x180040327  call    cs:__imp_GetLastError
0x18004032d  mov     rcx, cs:WPP_GLOBAL_Control
0x180040334  mov     edx, 97h
0x180040339  mov     r9d, eax
0x18004033c  mov     r8, r15
0x18004033f  mov     rcx, [rcx+10h]
0x180040343  call    WPP_SF_d
0x180040348  mov     rcx, cs:WPP_GLOBAL_Control
0x18004034f  cmp     rcx, r14
0x180040352  jz      short loc_180040370
0x180040354  test    [rcx+1Ch], ebp
0x180040357  jz      short loc_180040370
0x180040359  cmp     byte ptr [rcx+19h], 6
0x18004035d  jb      short loc_180040370
0x18004035f  mov     rcx, [rcx+10h]
0x180040363  mov     edx, 98h
0x180040368  mov     r8, r15
0x18004036b  call    WPP_SF_
0x180040370  mov     eax, 8
0x180040375  jmp     loc_18004057C
0x18004037a  lea     rcx, NatInterfaceLock; lpCriticalSection
0x180040381  call    cs:__imp_EnterCriticalSection
0x180040387  test    rbx, rbx
0x18004038a  jnz     short loc_180040407
0x18004038c  xor     edx, edx; struct _LIST_ENTRY **
0x18004038e  mov     ecx, edi; unsigned int
0x180040390  call    ?NatLookupInterface@@YAPEAU_NAT_INTERFACE@@KPEAPEAU_LIST_ENTRY@@@Z; NatLookupInterface(ulong,_LIST_ENTRY * *)
0x180040395  mov     rbx, rax
0x180040398  test    rax, rax
0x18004039b  jnz     short loc_180040407
0x18004039d  lea     rcx, NatInterfaceLock; lpCriticalSection
0x1800403a4  call    cs:__imp_LeaveCriticalSection
0x1800403aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800403b1  cmp     rcx, r14
0x1800403b4  jz      short loc_1800403FD
0x1800403b6  test    [rcx+1Ch], ebp
0x1800403b9  jz      short loc_1800403DC
0x1800403bb  cmp     byte ptr [rcx+19h], 2
0x1800403bf  jb      short loc_1800403DC
0x1800403c1  mov     rcx, [rcx+10h]
0x1800403c5  mov     edx, 99h
0x1800403ca  mov     r9d, edi
0x1800403cd  mov     r8, r15
0x1800403d0  call    WPP_SF_d
0x1800403d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800403dc  cmp     rcx, r14
0x1800403df  jz      short loc_1800403FD
0x1800403e1  test    [rcx+1Ch], ebp
0x1800403e4  jz      short loc_1800403FD
0x1800403e6  cmp     byte ptr [rcx+19h], 6
0x1800403ea  jb      short loc_1800403FD
0x1800403ec  mov     rcx, [rcx+10h]
0x1800403f0  mov     edx, 9Ah
0x1800403f5  mov     r8, r15
0x1800403f8  call    WPP_SF_
0x1800403fd  mov     eax, 389h
0x180040402  jmp     loc_18004057C
0x180040407  mov     eax, [rbx+1Ch]
0x18004040a  bt      eax, 1Eh
0x18004040e  jb      short loc_18004047A
0x180040410  lea     rcx, NatInterfaceLock; lpCriticalSection
0x180040417  call    cs:__imp_LeaveCriticalSection
0x18004041d  mov     rcx, cs:WPP_GLOBAL_Control
0x180040424  cmp     rcx, r14
0x180040427  jz      short loc_180040470
0x180040429  test    [rcx+1Ch], ebp
0x18004042c  jz      short loc_18004044F
0x18004042e  cmp     byte ptr [rcx+19h], 2
0x180040432  jb      short loc_18004044F
0x180040434  mov     rcx, [rcx+10h]
0x180040438  mov     edx, 9Bh
0x18004043d  mov     r9d, edi
0x180040440  mov     r8, r15
0x180040443  call    WPP_SF_d
0x180040448  mov     rcx, cs:WPP_GLOBAL_Control
0x18004044f  cmp     rcx, r14
0x180040452  jz      short loc_180040470
0x180040454  test    [rcx+1Ch], ebp
0x180040457  jz      short loc_180040470
0x180040459  cmp     byte ptr [rcx+19h], 6
0x18004045d  jb      short loc_180040470
0x18004045f  mov     rcx, [rcx+10h]
0x180040463  mov     edx, 9Ch
0x180040468  mov     r8, r15
0x18004046b  call    WPP_SF_
0x180040470  mov     eax, 4CCh
0x180040475  jmp     loc_18004057C
0x18004047a  btr     eax, 1Eh
0x18004047e  cmp     dword ptr [rbx+18h], 3
0x180040482  mov     [rbx+1Ch], eax
0x180040485  jnz     short loc_180040491
0x180040487  xor     edx, edx; unsigned __int8
0x180040489  mov     rcx, rbx; struct _NAT_INTERFACE *
0x18004048c  call    ?NatUpdateProxyArp@@YAXPEAU_NAT_INTERFACE@@E@Z; NatUpdateProxyArp(_NAT_INTERFACE *,uchar)
0x180040491  mov     rcx, cs:NatFileHandle; FileHandle
0x180040498  lea     rax, [rbx+14h]
0x18004049c  mov     [rsp+98h+OutputBufferLength], 0; OutputBufferLength
0x1800404a4  xor     r9d, r9d; ApcContext
0x1800404a7  mov     [rsp+98h+OutputBuffer], 0; OutputBuffer
0x1800404b0  xor     r8d, r8d; ApcRoutine
0x1800404b3  mov     [rsp+98h+InputBufferLength], 4; InputBufferLength
0x1800404bb  mov     rdx, rsi; Event
0x1800404be  mov     [rsp+98h+InputBuffer], rax; InputBuffer
0x1800404c3  lea     rax, [rsp+98h+var_48]
0x1800404c8  mov     [rsp+98h+IoControlCode], 12800Ch; IoControlCode
0x1800404d0  mov     [rsp+98h+IoStatusBlock], rax; IoStatusBlock
0x1800404d5  call    cs:__imp_NtDeviceIoControlFile
0x1800404db  mov     edi, eax
0x1800404dd  cmp     eax, 103h
0x1800404e2  jnz     short loc_1800404F4
0x1800404e4  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800404e7  mov     rcx, rsi; hHandle
0x1800404ea  call    cs:__imp_WaitForSingleObject
0x1800404f0  mov     edi, dword ptr [rsp+98h+var_48]
0x1800404f4  lea     rcx, NatInterfaceLock; lpCriticalSection
0x1800404fb  call    cs:__imp_LeaveCriticalSection
0x180040501  mov     rcx, rsi; hObject
0x180040504  call    cs:__imp_CloseHandle
0x18004050a  test    edi, edi
0x18004050c  js      short loc_180040512
0x18004050e  xor     ebx, ebx
0x180040510  jmp     short loc_18004054F
0x180040512  mov     ecx, edi; Status
0x180040514  call    cs:__imp_RtlNtStatusToDosError
0x18004051a  mov     ebx, eax
0x18004051c  test    eax, eax
0x18004051e  jz      short loc_18004054F
0x180040520  mov     rcx, cs:WPP_GLOBAL_Control
0x180040527  cmp     rcx, r14
0x18004052a  jz      short loc_18004057A
0x18004052c  test    [rcx+1Ch], ebp
0x18004052f  jz      short loc_180040556
0x180040531  cmp     byte ptr [rcx+19h], 2
0x180040535  jb      short loc_180040556
0x180040537  mov     rcx, [rcx+10h]
0x18004053b  mov     edx, 9Dh
0x180040540  mov     r9d, edi
0x180040543  mov     dword ptr [rsp+98h+IoStatusBlock], eax
0x180040547  mov     r8, r15
0x18004054a  call    WPP_SF_Dd
0x18004054f  mov     rcx, cs:WPP_GLOBAL_Control
0x180040556  cmp     rcx, r14
0x180040559  jz      short loc_18004057A
0x18004055b  test    [rcx+1Ch], ebp
0x18004055e  jz      short loc_18004057A
0x180040560  cmp     byte ptr [rcx+19h], 6
0x180040564  jb      short loc_18004057A
0x180040566  mov     rcx, [rcx+10h]
0x18004056a  mov     edx, 9Eh
0x18004056f  mov     r9d, ebx
0x180040572  mov     r8, r15
0x180040575  call    WPP_SF_d
0x18004057a  mov     eax, ebx
0x18004057c  add     rsp, 68h
0x180040580  pop     r15
0x180040582  pop     r14
0x180040584  pop     rdi
0x180040585  pop     rsi
0x180040586  pop     rbp
0x180040587  pop     rbx
0x180040588  retn
```
