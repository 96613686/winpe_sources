# NatDeleteInterface

- ea: `0x18002bda8`
- end: `0x18002c1be`
- name: `NatDeleteInterface`
- size: `1046`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `5`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180047e80`
- `0x18004b754`
- `0x180072f10`
- `0x180078b80`
- `0x1800791e8`

## callees

- `0x18000c110`
- `0x18000c750`
- `0x18001ec08`
- `0x18002bda8`
- `0x18002c1c4`
- `0x18002c3ec`
- `0x180055728`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002c011`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002c025`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002c011`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002c025`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002c01f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002c033`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002c01f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002c033`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002be9f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002be9f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c0c0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c13b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c0c0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c13b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002be18`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002be18`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002bf8f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002bf8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002be3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002be3d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002bfe1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c144`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002bfe1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c144`
- `ntdll!NtDeviceIoControlFile` at `0x18002bf7a`
- `ntdll!NtDeviceIoControlFile` at `0x18002bf7a`
- `ntdll!RtlNtStatusToDosError` at `0x18002bf9f`
- `ntdll!RtlNtStatusToDosError` at `0x18002bf9f`

## pseudocode

```c
__int64 __fastcall NatDeleteInterface(unsigned int a1, int a2)
{
  HANDLE EventW; // r14
  PVOID *v5; // rcx
  DWORD LastError; // eax
  PVOID *v8; // rcx
  LPVOID *i; // rbx
  ULONG v10; // edi
  int Status; // esi
  ULONG v12; // eax
  _QWORD *v13; // rcx
  LPVOID *v14; // rax
  void *v15; // rsi
  HANDLE ProcessHeap; // rax
  HANDLE v17; // rax
  PVOID *v18; // rcx
  PVOID *v19; // rcx
  int IoStatusBlock; // [rsp+20h] [rbp-78h]
  struct _IO_STATUS_BLOCK v21; // [rsp+50h] [rbp-48h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_Dc(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids, a1, a2 != 0);
  }
  v21 = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  if ( EventW )
  {
    if ( !a2 )
      EnterCriticalSection(&NatInterfaceLock);
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 111, &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids, a1);
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
    for ( i = (LPVOID *)NatInterfaceList; ; i = (LPVOID *)*i )
    {
      if ( i == &NatInterfaceList )
        goto LABEL_59;
      if ( a1 <= *((_DWORD *)i + 4) )
        break;
    }
    if ( a1 < *((_DWORD *)i + 4) )
    {
LABEL_59:
      if ( v8 != &WPP_GLOBAL_Control && (*((_DWORD *)v8 + 7) & 0x200) != 0 && *((_BYTE *)v8 + 25) >= 6u )
        WPP_SF_d(v8[2], 113, &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids, a1);
      goto LABEL_63;
    }
    if ( v8 != &WPP_GLOBAL_Control && (*((_DWORD *)v8 + 7) & 0x200) != 0 && *((_BYTE *)v8 + 25) >= 6u )
      WPP_SF_d(v8[2], 112, &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids, a1);
    if ( i )
    {
      v10 = 0;
      if ( (*((_DWORD *)i + 7) & 0x40000000) != 0 )
      {
        Status = NtDeviceIoControlFile(NatFileHandle, EventW, 0, 0, &v21, 0x12800Cu, (char *)i + 20, 4u, 0, 0);
        if ( Status == 259 )
        {
          WaitForSingleObject(EventW, 0xFFFFFFFF);
          Status = v21.Status;
        }
        if ( Status < 0 )
        {
          v12 = RtlNtStatusToDosError(Status);
          v10 = v12;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              90,
              &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids,
              (unsigned int)Status,
              v12);
          }
        }
      }
      CloseHandle(EventW);
      v13 = *i;
      if ( *((LPVOID **)*i + 1) != i || (v14 = (LPVOID *)i[1], *v14 != i) )
        __fastfail(3u);
      *v14 = v13;
      v13[1] = v14;
      v15 = i[4];
      if ( v15 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v15);
      }
      v17 = GetProcessHeap();
      HeapFree(v17, 0, i);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        LOBYTE(IoStatusBlock) = 0;
        WPP_SF_Dc(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          116,
          &WPP_1aaa4111f34f303c0aa2c26dd507e416_Traceguids,
          a1,
          IoStatusBlock);
      }
      DhcpSignalNatInterface(a1, 0);
      DnsSignalNatInterface(a1, 0);
      v18 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 117, &WPP_1aaa4111f34f303c0aa2c26dd507e416_Traceguids);
        v18 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( !a2 )
      {
        LeaveCriticalSection(&NatInterfaceLock);
        v18 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v18 != &WPP_GLOBAL_Control && (*((_DWORD *)v18 + 7) & 0x200) != 0 && *((_BYTE *)v18 + 25) >= 6u )
        WPP_SF_d(v18[2], 91, &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids, v10);
      return v10;
    }
LABEL_63:
    if ( !a2 )
      LeaveCriticalSection(&NatInterfaceLock);
    CloseHandle(EventW);
    v19 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids, a1);
        v19 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v19 != &WPP_GLOBAL_Control && (*((_DWORD *)v19 + 7) & 0x200) != 0 && *((_BYTE *)v19 + 25) >= 6u )
        WPP_SF_d(v19[2], 89, &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids, 905);
    }
    return 905;
  }
  else
  {
    v5 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids, LastError);
        v5 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v5 != &WPP_GLOBAL_Control && (*((_DWORD *)v5 + 7) & 0x200) != 0 && *((_BYTE *)v5 + 25) >= 6u )
        WPP_SF_d(v5[2], 87, &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids, 8);
    }
    return 8;
  }
}

```

## disassembly

```asm
0x18002bda8  push    rbx
0x18002bdaa  push    rbp
0x18002bdab  push    rsi
0x18002bdac  push    rdi
0x18002bdad  push    r13
0x18002bdaf  push    r14
0x18002bdb1  push    r15
0x18002bdb3  sub     rsp, 60h
0x18002bdb7  mov     r15d, edx
0x18002bdba  mov     ebp, ecx
0x18002bdbc  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bdc3  lea     r13, WPP_GLOBAL_Control
0x18002bdca  lea     rbx, WPP_1a1a310d9f3938633825d91885f62d23_Traceguids
0x18002bdd1  mov     sil, 6
0x18002bdd4  mov     edi, 200h
0x18002bdd9  cmp     rcx, r13
0x18002bddc  jz      short loc_18002BE06
0x18002bdde  test    [rcx+1Ch], edi
0x18002bde1  jz      short loc_18002BE06
0x18002bde3  cmp     [rcx+19h], sil
0x18002bde7  jb      short loc_18002BE06
0x18002bde9  mov     rcx, [rcx+10h]
0x18002bded  test    edx, edx
0x18002bdef  mov     edx, 55h ; 'U'
0x18002bdf4  mov     r9d, ebp
0x18002bdf7  setnz   al
0x18002bdfa  mov     r8, rbx
0x18002bdfd  mov     byte ptr [rsp+98h+IoStatusBlock], al
0x18002be01  call    WPP_SF_Dc
0x18002be06  xorps   xmm0, xmm0
0x18002be09  xor     r9d, r9d; lpName
0x18002be0c  xor     r8d, r8d; bInitialState
0x18002be0f  xor     edx, edx; bManualReset
0x18002be11  xor     ecx, ecx; lpEventAttributes
0x18002be13  movups  xmmword ptr [rsp+98h+var_48], xmm0
0x18002be18  call    cs:__imp_CreateEventW
0x18002be1e  mov     r14, rax
0x18002be21  test    rax, rax
0x18002be24  jnz     short loc_18002BE93
0x18002be26  mov     rcx, cs:WPP_GLOBAL_Control
0x18002be2d  cmp     rcx, r13
0x18002be30  jz      short loc_18002BE89
0x18002be32  test    [rcx+1Ch], edi
0x18002be35  jz      short loc_18002BE64
0x18002be37  cmp     byte ptr [rcx+19h], 2
0x18002be3b  jb      short loc_18002BE64
0x18002be3d  call    cs:__imp_GetLastError
0x18002be43  mov     rcx, cs:WPP_GLOBAL_Control
0x18002be4a  lea     edx, [r14+56h]
0x18002be4e  mov     r9d, eax
0x18002be51  mov     r8, rbx
0x18002be54  mov     rcx, [rcx+10h]
0x18002be58  call    WPP_SF_d
0x18002be5d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002be64  cmp     rcx, r13
0x18002be67  jz      short loc_18002BE89
0x18002be69  test    [rcx+1Ch], edi
0x18002be6c  jz      short loc_18002BE89
0x18002be6e  cmp     [rcx+19h], sil
0x18002be72  jb      short loc_18002BE89
0x18002be74  mov     rcx, [rcx+10h]
0x18002be78  mov     edx, 57h ; 'W'
0x18002be7d  mov     r8, rbx
0x18002be80  lea     r9d, [rdx-4Fh]
0x18002be84  call    WPP_SF_d
0x18002be89  mov     eax, 8
0x18002be8e  jmp     loc_18002C1AF
0x18002be93  test    r15d, r15d
0x18002be96  jnz     short loc_18002BEA5
0x18002be98  lea     rcx, NatInterfaceLock; lpCriticalSection
0x18002be9f  call    cs:__imp_EnterCriticalSection
0x18002bea5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002beac  cmp     rcx, r13
0x18002beaf  jz      short loc_18002BED7
0x18002beb1  test    [rcx+1Ch], edi
0x18002beb4  jz      short loc_18002BED7
0x18002beb6  cmp     [rcx+19h], sil
0x18002beba  jb      short loc_18002BED7
0x18002bebc  mov     rcx, [rcx+10h]
0x18002bec0  mov     edx, 6Fh ; 'o'
0x18002bec5  mov     r9d, ebp
0x18002bec8  mov     r8, rbx
0x18002becb  call    WPP_SF_d
0x18002bed0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bed7  mov     rbx, cs:NatInterfaceList
0x18002bede  lea     rax, NatInterfaceList
0x18002bee5  cmp     rbx, rax
0x18002bee8  jz      loc_18002C107
0x18002beee  cmp     ebp, [rbx+10h]
0x18002bef1  jbe     short loc_18002BEF8
0x18002bef3  mov     rbx, [rbx]
0x18002bef6  jmp     short loc_18002BEDE
0x18002bef8  jb      loc_18002C107
0x18002befe  cmp     rcx, r13
0x18002bf01  jz      short loc_18002BF26
0x18002bf03  test    [rcx+1Ch], edi
0x18002bf06  jz      short loc_18002BF26
0x18002bf08  cmp     [rcx+19h], sil
0x18002bf0c  jb      short loc_18002BF26
0x18002bf0e  mov     rcx, [rcx+10h]
0x18002bf12  lea     r8, WPP_1a1a310d9f3938633825d91885f62d23_Traceguids
0x18002bf19  mov     edx, 70h ; 'p'
0x18002bf1e  mov     r9d, ebp
0x18002bf21  call    WPP_SF_d
0x18002bf26  test    rbx, rbx
0x18002bf29  jz      loc_18002C12F
0x18002bf2f  xor     edi, edi
0x18002bf31  test    dword ptr [rbx+1Ch], 40000000h
0x18002bf38  jz      loc_18002BFDE
0x18002bf3e  mov     rcx, cs:NatFileHandle; FileHandle
0x18002bf45  lea     rax, [rbx+14h]
0x18002bf49  mov     [rsp+98h+OutputBufferLength], edi; OutputBufferLength
0x18002bf4d  xor     r9d, r9d; ApcContext
0x18002bf50  mov     [rsp+98h+OutputBuffer], rdi; OutputBuffer
0x18002bf55  xor     r8d, r8d; ApcRoutine
0x18002bf58  mov     [rsp+98h+InputBufferLength], 4; InputBufferLength
0x18002bf60  mov     rdx, r14; Event
0x18002bf63  mov     [rsp+98h+InputBuffer], rax; InputBuffer
0x18002bf68  lea     rax, [rsp+98h+var_48]
0x18002bf6d  mov     [rsp+98h+IoControlCode], 12800Ch; IoControlCode
0x18002bf75  mov     [rsp+98h+IoStatusBlock], rax; IoStatusBlock
0x18002bf7a  call    cs:__imp_NtDeviceIoControlFile
0x18002bf80  mov     esi, eax
0x18002bf82  cmp     eax, 103h
0x18002bf87  jnz     short loc_18002BF99
0x18002bf89  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002bf8c  mov     rcx, r14; hHandle
0x18002bf8f  call    cs:__imp_WaitForSingleObject
0x18002bf95  mov     esi, dword ptr [rsp+98h+var_48]
0x18002bf99  test    esi, esi
0x18002bf9b  jns     short loc_18002BFDE
0x18002bf9d  mov     ecx, esi; Status
0x18002bf9f  call    cs:__imp_RtlNtStatusToDosError
0x18002bfa5  mov     edi, eax
0x18002bfa7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bfae  cmp     rcx, r13
0x18002bfb1  jz      short loc_18002BFDE
0x18002bfb3  test    dword ptr [rcx+1Ch], 200h
0x18002bfba  jz      short loc_18002BFDE
0x18002bfbc  cmp     byte ptr [rcx+19h], 2
0x18002bfc0  jb      short loc_18002BFDE
0x18002bfc2  mov     rcx, [rcx+10h]
0x18002bfc6  lea     r8, WPP_1a1a310d9f3938633825d91885f62d23_Traceguids
0x18002bfcd  mov     edx, 5Ah ; 'Z'
0x18002bfd2  mov     dword ptr [rsp+98h+IoStatusBlock], eax
0x18002bfd6  mov     r9d, esi
0x18002bfd9  call    WPP_SF_Dd
0x18002bfde  mov     rcx, r14; hObject
0x18002bfe1  call    cs:__imp_CloseHandle
0x18002bfe7  mov     rcx, [rbx]
0x18002bfea  cmp     [rcx+8], rbx
0x18002bfee  jnz     loc_18002C100
0x18002bff4  mov     rax, [rbx+8]
0x18002bff8  cmp     [rax], rbx
0x18002bffb  jnz     loc_18002C100
0x18002c001  mov     [rax], rcx
0x18002c004  mov     [rcx+8], rax
0x18002c008  mov     rsi, [rbx+20h]
0x18002c00c  test    rsi, rsi
0x18002c00f  jz      short loc_18002C025
0x18002c011  call    cs:__imp_GetProcessHeap
0x18002c017  mov     r8, rsi; lpMem
0x18002c01a  xor     edx, edx; dwFlags
0x18002c01c  mov     rcx, rax; hHeap
0x18002c01f  call    cs:__imp_HeapFree
0x18002c025  call    cs:__imp_GetProcessHeap
0x18002c02b  mov     r8, rbx; lpMem
0x18002c02e  xor     edx, edx; dwFlags
0x18002c030  mov     rcx, rax; hHeap
0x18002c033  call    cs:__imp_HeapFree
0x18002c039  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c040  cmp     rcx, r13
0x18002c043  jz      short loc_18002C06E
0x18002c045  test    byte ptr [rcx+1Ch], 8
0x18002c049  jz      short loc_18002C06E
0x18002c04b  cmp     byte ptr [rcx+19h], 6
0x18002c04f  jb      short loc_18002C06E
0x18002c051  mov     rcx, [rcx+10h]
0x18002c055  lea     r8, WPP_1aaa4111f34f303c0aa2c26dd507e416_Traceguids
0x18002c05c  mov     edx, 74h ; 't'
0x18002c061  mov     byte ptr [rsp+98h+IoStatusBlock], 0
0x18002c066  mov     r9d, ebp
0x18002c069  call    WPP_SF_Dc
0x18002c06e  xor     edx, edx; unsigned __int8
0x18002c070  mov     ecx, ebp; unsigned int
0x18002c072  call    ?DhcpSignalNatInterface@@YAXKE@Z; DhcpSignalNatInterface(ulong,uchar)
0x18002c077  xor     edx, edx; unsigned __int8
0x18002c079  mov     ecx, ebp; unsigned int
0x18002c07b  call    ?DnsSignalNatInterface@@YAXKE@Z; DnsSignalNatInterface(ulong,uchar)
0x18002c080  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c087  cmp     rcx, r13
0x18002c08a  jz      short loc_18002C0B4
0x18002c08c  test    byte ptr [rcx+1Ch], 8
0x18002c090  jz      short loc_18002C0B4
0x18002c092  cmp     byte ptr [rcx+19h], 6
0x18002c096  jb      short loc_18002C0B4
0x18002c098  mov     rcx, [rcx+10h]
0x18002c09c  lea     r8, WPP_1aaa4111f34f303c0aa2c26dd507e416_Traceguids
0x18002c0a3  mov     edx, 75h ; 'u'
0x18002c0a8  call    WPP_SF_
0x18002c0ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c0b4  test    r15d, r15d
0x18002c0b7  jnz     short loc_18002C0CD
0x18002c0b9  lea     rcx, NatInterfaceLock; lpCriticalSection
0x18002c0c0  call    cs:__imp_LeaveCriticalSection
0x18002c0c6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c0cd  cmp     rcx, r13
0x18002c0d0  jz      short loc_18002C0F9
0x18002c0d2  test    dword ptr [rcx+1Ch], 200h
0x18002c0d9  jz      short loc_18002C0F9
0x18002c0db  cmp     byte ptr [rcx+19h], 6
0x18002c0df  jb      short loc_18002C0F9
0x18002c0e1  mov     rcx, [rcx+10h]
0x18002c0e5  lea     r8, WPP_1a1a310d9f3938633825d91885f62d23_Traceguids
0x18002c0ec  mov     edx, 5Bh ; '['
0x18002c0f1  mov     r9d, edi
0x18002c0f4  call    WPP_SF_d
0x18002c0f9  mov     eax, edi
0x18002c0fb  jmp     loc_18002C1AF
0x18002c100  mov     ecx, 3
0x18002c105  int     29h; Win8: RtlFailFast(ecx)
0x18002c107  cmp     rcx, r13
0x18002c10a  jz      short loc_18002C12F
0x18002c10c  test    [rcx+1Ch], edi
0x18002c10f  jz      short loc_18002C12F
0x18002c111  cmp     [rcx+19h], sil
0x18002c115  jb      short loc_18002C12F
0x18002c117  mov     rcx, [rcx+10h]
0x18002c11b  lea     r8, WPP_1a1a310d9f3938633825d91885f62d23_Traceguids
0x18002c122  mov     edx, 71h ; 'q'
0x18002c127  mov     r9d, ebp
0x18002c12a  call    WPP_SF_d
0x18002c12f  test    r15d, r15d
0x18002c132  jnz     short loc_18002C141
0x18002c134  lea     rcx, NatInterfaceLock; lpCriticalSection
0x18002c13b  call    cs:__imp_LeaveCriticalSection
0x18002c141  mov     rcx, r14; hObject
0x18002c144  call    cs:__imp_CloseHandle
0x18002c14a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c151  mov     ebx, 389h
0x18002c156  cmp     rcx, r13
0x18002c159  jz      short loc_18002C1AD
0x18002c15b  test    [rcx+1Ch], edi
0x18002c15e  jz      short loc_18002C185
0x18002c160  cmp     byte ptr [rcx+19h], 2
0x18002c164  jb      short loc_18002C185
0x18002c166  mov     rcx, [rcx+10h]
0x18002c16a  lea     r8, WPP_1a1a310d9f3938633825d91885f62d23_Traceguids
0x18002c171  mov     edx, 58h ; 'X'
0x18002c176  mov     r9d, ebp
0x18002c179  call    WPP_SF_d
0x18002c17e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c185  cmp     rcx, r13
0x18002c188  jz      short loc_18002C1AD
0x18002c18a  test    [rcx+1Ch], edi
0x18002c18d  jz      short loc_18002C1AD
0x18002c18f  cmp     [rcx+19h], sil
0x18002c193  jb      short loc_18002C1AD
0x18002c195  mov     rcx, [rcx+10h]
0x18002c199  lea     r8, WPP_1a1a310d9f3938633825d91885f62d23_Traceguids
0x18002c1a0  mov     edx, 59h ; 'Y'
0x18002c1a5  mov     r9d, ebx
0x18002c1a8  call    WPP_SF_d
0x18002c1ad  mov     eax, ebx
0x18002c1af  add     rsp, 60h
0x18002c1b3  pop     r15
0x18002c1b5  pop     r14
0x18002c1b7  pop     r13
0x18002c1b9  pop     rdi
0x18002c1ba  pop     rsi
0x18002c1bb  pop     rbp
0x18002c1bc  pop     rbx
0x18002c1bd  retn
```
