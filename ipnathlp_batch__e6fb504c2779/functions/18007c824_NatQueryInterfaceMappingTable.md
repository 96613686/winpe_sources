# NatQueryInterfaceMappingTable

- ea: `0x18007c824`
- end: `0x18007cdae`
- name: `NatQueryInterfaceMappingTable`
- size: `1418`
- prototype: `__int64 __fastcall(unsigned int, unsigned int *OutputBuffer, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180079170`

## callees

- `0x18000ca20`
- `0x18000d090`
- `0x1800202e0`
- `0x180035678`
- `0x180051f30`
- `0x180052bf4`
- `0x18007c824`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007c8b4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007c8b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007c8d9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007c95e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007ca13`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007cb3b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007cbf6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007cce1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007c8d9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007c95e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007ca13`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007cb3b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007cbf6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007cce1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007c9f4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007c9f4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007cb0c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007ccbb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007cb0c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007ccbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ca45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ca45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007cb28`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007cbe3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007ccce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007cb28`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007cbe3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007ccce`
- `ntdll!NtDeviceIoControlFile` at `0x18007caf0`
- `ntdll!NtDeviceIoControlFile` at `0x18007cc9f`
- `ntdll!NtDeviceIoControlFile` at `0x18007caf0`
- `ntdll!NtDeviceIoControlFile` at `0x18007cc9f`
- `ntdll!RtlNtStatusToDosError` at `0x18007cb50`
- `ntdll!RtlNtStatusToDosError` at `0x18007cd46`
- `ntdll!RtlNtStatusToDosError` at `0x18007cb50`
- `ntdll!RtlNtStatusToDosError` at `0x18007cd46`

## pseudocode

```c
__int64 __fastcall NatQueryInterfaceMappingTable(unsigned int a1, unsigned int *OutputBuffer, unsigned int *a3)
{
  struct _NAT_INTERFACE *v6; // rax
  struct _NAT_INTERFACE *v7; // r13
  PVOID *v8; // rcx
  unsigned int v9; // ebx
  __int64 v10; // rdx
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  HANDLE EventW; // rdi
  DWORD LastError; // eax
  int Status; // r15d
  ULONG v17; // eax
  unsigned int v18; // r15d
  ULONG OutputBufferLength; // ecx
  int v20; // r15d
  unsigned int v21; // eax
  ULONG v22; // eax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-39h] BYREF
  int InputBuffer; // [rsp+60h] [rbp-29h] BYREF
  int v25; // [rsp+64h] [rbp-25h]
  int v26; // [rsp+74h] [rbp-15h]
  int v27; // [rsp+78h] [rbp-11h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 118, &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids, a1);
  }
  memset_0(&InputBuffer, 0, 0x40u);
  IoStatusBlock = 0;
  EnterCriticalSection(&NatInterfaceLock);
  v6 = NatLookupInterface(a1, 0);
  v7 = v6;
  if ( !v6 )
  {
    LeaveCriticalSection(&NatInterfaceLock);
    v8 = (PVOID *)WPP_GLOBAL_Control;
    v9 = 905;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v9;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 119, &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids, a1);
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v8 == &WPP_GLOBAL_Control || (*((_DWORD *)v8 + 7) & 0x200) == 0 || *((_BYTE *)v8 + 25) < 6u )
      return v9;
    v10 = 120;
LABEL_65:
    WPP_SF_d(v8[2], v10, &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids, v9);
    return v9;
  }
  if ( (*((_DWORD *)v6 + 7) & 0x40000000) != 0 )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    if ( !EventW )
    {
      LeaveCriticalSection(&NatInterfaceLock);
      v8 = (PVOID *)WPP_GLOBAL_Control;
      v9 = 8;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v9;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 123, &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids, LastError);
        v8 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v8 == &WPP_GLOBAL_Control || (*((_DWORD *)v8 + 7) & 0x200) == 0 || *((_BYTE *)v8 + 25) < 6u )
        return v9;
      v10 = 124;
      goto LABEL_65;
    }
    InputBuffer = *((_DWORD *)v7 + 5);
    v26 = 0;
    v25 = 0;
    Status = NtDeviceIoControlFile(
               NatFileHandle,
               EventW,
               0,
               0,
               &IoStatusBlock,
               0x128038u,
               &InputBuffer,
               0x40u,
               &InputBuffer,
               0x40u);
    if ( Status == 259 )
    {
      WaitForSingleObject(EventW, 0xFFFFFFFF);
      Status = IoStatusBlock.Status;
    }
    if ( Status < 0 )
    {
      CloseHandle(EventW);
      LeaveCriticalSection(&NatInterfaceLock);
      *a3 = 0;
      v17 = RtlNtStatusToDosError(Status);
      v9 = v17;
      v8 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v9;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          125,
          &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids,
          (unsigned int)Status,
          v17);
        v8 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v8 == &WPP_GLOBAL_Control || (*((_DWORD *)v8 + 7) & 0x200) == 0 || *((_BYTE *)v8 + 25) < 6u )
        return v9;
      v10 = 126;
      goto LABEL_65;
    }
    v18 = 36 * v27 + 28;
    OutputBufferLength = *a3;
    if ( *a3 >= v18 )
    {
      InputBuffer = *((_DWORD *)v7 + 5);
      v26 = 0;
      v25 = 0;
      v20 = NtDeviceIoControlFile(
              NatFileHandle,
              EventW,
              0,
              0,
              &IoStatusBlock,
              0x128038u,
              &InputBuffer,
              0x40u,
              OutputBuffer,
              OutputBufferLength);
      if ( v20 == 259 )
      {
        WaitForSingleObject(EventW, 0xFFFFFFFF);
        v20 = IoStatusBlock.Status;
      }
      CloseHandle(EventW);
      LeaveCriticalSection(&NatInterfaceLock);
      v21 = OutputBuffer[5];
      *OutputBuffer = a1;
      *a3 = 36 * v21 + 28;
      v8 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 128, &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids);
        v8 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v20 < 0 )
      {
        v22 = RtlNtStatusToDosError(v20);
        v8 = (PVOID *)WPP_GLOBAL_Control;
        v9 = v22;
      }
      else
      {
        v9 = 0;
      }
      if ( v8 == &WPP_GLOBAL_Control || (*((_DWORD *)v8 + 7) & 0x200) == 0 || *((_BYTE *)v8 + 25) < 6u )
        return v9;
      v10 = 129;
      goto LABEL_65;
    }
    CloseHandle(EventW);
    LeaveCriticalSection(&NatInterfaceLock);
    *a3 = v18 + 180;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 6u )
    {
      return 122;
    }
    v12 = 127;
LABEL_50:
    WPP_SF_d(v11[2], v12, &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids, 122);
    return 122;
  }
  LeaveCriticalSection(&NatInterfaceLock);
  if ( *a3 < 0x1C )
  {
    *a3 = 28;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 6u )
    {
      return 122;
    }
    v12 = 121;
    goto LABEL_50;
  }
  *OutputBuffer = a1;
  OutputBuffer[1] = 0;
  OutputBuffer[5] = 0;
  *a3 = 28;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 122, &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x18007c824  mov     [rsp-8+arg_18], rbx
0x18007c829  push    rbp
0x18007c82a  push    rsi
0x18007c82b  push    rdi
0x18007c82c  push    r12
0x18007c82e  push    r13
0x18007c830  push    r14
0x18007c832  push    r15
0x18007c834  lea     rbp, [rsp-27h]
0x18007c839  sub     rsp, 0B0h
0x18007c840  mov     rax, cs:__security_cookie
0x18007c847  xor     rax, rsp
0x18007c84a  mov     [rbp+57h+var_40], rax
0x18007c84e  mov     rbx, r8
0x18007c851  mov     rsi, rdx
0x18007c854  mov     r14d, ecx
0x18007c857  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c85e  lea     rdi, WPP_GLOBAL_Control
0x18007c865  lea     r15, WPP_1a1a310d9f3938633825d91885f62d23_Traceguids
0x18007c86c  mov     r12d, 200h
0x18007c872  cmp     rcx, rdi
0x18007c875  jz      short loc_18007C897
0x18007c877  test    [rcx+1Ch], r12d
0x18007c87b  jz      short loc_18007C897
0x18007c87d  cmp     byte ptr [rcx+19h], 6
0x18007c881  jb      short loc_18007C897
0x18007c883  mov     rcx, [rcx+10h]
0x18007c887  mov     edx, 76h ; 'v'
0x18007c88c  mov     r9d, r14d
0x18007c88f  mov     r8, r15
0x18007c892  call    WPP_SF_d
0x18007c897  xor     edx, edx; Val
0x18007c899  lea     rcx, [rbp+57h+var_80]; void *
0x18007c89d  lea     r8d, [rdx+40h]; Size
0x18007c8a1  call    memset_0
0x18007c8a6  xorps   xmm0, xmm0
0x18007c8a9  lea     rcx, NatInterfaceLock; lpCriticalSection
0x18007c8b0  movups  xmmword ptr [rbp+57h+var_90], xmm0
0x18007c8b4  call    cs:__imp_EnterCriticalSection
0x18007c8bb  nop     dword ptr [rax+rax+00h]
0x18007c8c0  xor     edx, edx; struct _LIST_ENTRY **
0x18007c8c2  mov     ecx, r14d; unsigned int
0x18007c8c5  call    ?NatLookupInterface@@YAPEAU_NAT_INTERFACE@@KPEAPEAU_LIST_ENTRY@@@Z; NatLookupInterface(ulong,_LIST_ENTRY * *)
0x18007c8ca  mov     r13, rax
0x18007c8cd  test    rax, rax
0x18007c8d0  jnz     short loc_18007C94A
0x18007c8d2  lea     rcx, NatInterfaceLock; lpCriticalSection
0x18007c8d9  call    cs:__imp_LeaveCriticalSection
0x18007c8e0  nop     dword ptr [rax+rax+00h]
0x18007c8e5  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c8ec  mov     ebx, 389h
0x18007c8f1  cmp     rcx, rdi
0x18007c8f4  jz      loc_18007CD84
0x18007c8fa  test    [rcx+1Ch], r12d
0x18007c8fe  jz      short loc_18007C920
0x18007c900  cmp     byte ptr [rcx+19h], 2
0x18007c904  jb      short loc_18007C920
0x18007c906  mov     rcx, [rcx+10h]
0x18007c90a  lea     edx, [r13+77h]
0x18007c90e  mov     r9d, r14d
0x18007c911  mov     r8, r15
0x18007c914  call    WPP_SF_d
0x18007c919  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c920  cmp     rcx, rdi
0x18007c923  jz      loc_18007CD84
0x18007c929  test    [rcx+1Ch], r12d
0x18007c92d  jz      loc_18007CD84
0x18007c933  cmp     byte ptr [rcx+19h], 6
0x18007c937  jb      loc_18007CD84
0x18007c93d  mov     edx, 78h ; 'x'
0x18007c942  mov     r8, r15
0x18007c945  jmp     loc_18007CD78
0x18007c94a  test    dword ptr [rax+1Ch], 40000000h
0x18007c951  jnz     loc_18007C9EA
0x18007c957  lea     rcx, NatInterfaceLock; lpCriticalSection
0x18007c95e  call    cs:__imp_LeaveCriticalSection
0x18007c965  nop     dword ptr [rax+rax+00h]
0x18007c96a  mov     eax, 1Ch
0x18007c96f  cmp     [rbx], eax
0x18007c971  jnb     short loc_18007C9A4
0x18007c973  mov     [rbx], eax
0x18007c975  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c97c  cmp     rcx, rdi
0x18007c97f  jz      loc_18007CC45
0x18007c985  test    [rcx+1Ch], r12d
0x18007c989  jz      loc_18007CC45
0x18007c98f  cmp     byte ptr [rcx+19h], 6
0x18007c993  jb      loc_18007CC45
0x18007c999  lea     edx, [rax+5Dh]
0x18007c99c  mov     r8, r15
0x18007c99f  jmp     loc_18007CC36
0x18007c9a4  mov     [rsi], r14d
0x18007c9a7  mov     dword ptr [rsi+4], 0
0x18007c9ae  mov     dword ptr [rsi+14h], 0
0x18007c9b5  mov     [rbx], eax
0x18007c9b7  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c9be  cmp     rcx, rdi
0x18007c9c1  jz      short loc_18007C9E3
0x18007c9c3  test    [rcx+1Ch], r12d
0x18007c9c7  jz      short loc_18007C9E3
0x18007c9c9  cmp     byte ptr [rcx+19h], 6
0x18007c9cd  jb      short loc_18007C9E3
0x18007c9cf  mov     rcx, [rcx+10h]
0x18007c9d3  mov     edx, 7Ah ; 'z'
0x18007c9d8  xor     r9d, r9d
0x18007c9db  mov     r8, r15
0x18007c9de  call    WPP_SF_d
0x18007c9e3  xor     eax, eax
0x18007c9e5  jmp     loc_18007CD86
0x18007c9ea  xor     r9d, r9d; lpName
0x18007c9ed  xor     r8d, r8d; bInitialState
0x18007c9f0  xor     edx, edx; bManualReset
0x18007c9f2  xor     ecx, ecx; lpEventAttributes
0x18007c9f4  call    cs:__imp_CreateEventW
0x18007c9fb  nop     dword ptr [rax+rax+00h]
0x18007ca00  mov     rdi, rax
0x18007ca03  test    rax, rax
0x18007ca06  jnz     loc_18007CA98
0x18007ca0c  lea     rcx, NatInterfaceLock; lpCriticalSection
0x18007ca13  call    cs:__imp_LeaveCriticalSection
0x18007ca1a  nop     dword ptr [rax+rax+00h]
0x18007ca1f  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ca26  lea     ebx, [rdi+8]
0x18007ca29  lea     rdi, WPP_GLOBAL_Control
0x18007ca30  cmp     rcx, rdi
0x18007ca33  jz      loc_18007CD84
0x18007ca39  test    [rcx+1Ch], r12d
0x18007ca3d  jz      short loc_18007CA71
0x18007ca3f  cmp     byte ptr [rcx+19h], 2
0x18007ca43  jb      short loc_18007CA71
0x18007ca45  call    cs:__imp_GetLastError
0x18007ca4c  nop     dword ptr [rax+rax+00h]
0x18007ca51  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ca58  lea     edx, [rbx+73h]
0x18007ca5b  mov     r9d, eax
0x18007ca5e  mov     r8, r15
0x18007ca61  mov     rcx, [rcx+10h]
0x18007ca65  call    WPP_SF_d
0x18007ca6a  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ca71  cmp     rcx, rdi
0x18007ca74  jz      loc_18007CD84
0x18007ca7a  test    [rcx+1Ch], r12d
0x18007ca7e  jz      loc_18007CD84
0x18007ca84  cmp     byte ptr [rcx+19h], 6
0x18007ca88  jb      loc_18007CD84
0x18007ca8e  mov     edx, 7Ch ; '|'
0x18007ca93  jmp     loc_18007C942
0x18007ca98  mov     eax, [r13+14h]
0x18007ca9c  xor     r9d, r9d; ApcContext
0x18007ca9f  mov     rcx, cs:NatFileHandle; FileHandle
0x18007caa6  xor     r8d, r8d; ApcRoutine
0x18007caa9  mov     [rsp+0E0h+OutputBufferLength], 40h ; '@'; OutputBufferLength
0x18007cab1  mov     rdx, rdi; Event
0x18007cab4  mov     [rbp+57h+var_80], eax
0x18007cab7  lea     rax, [rbp+57h+var_80]
0x18007cabb  mov     [rsp+0E0h+OutputBuffer], rax; OutputBuffer
0x18007cac0  lea     rax, [rbp+57h+var_80]
0x18007cac4  mov     [rsp+0E0h+InputBufferLength], 40h ; '@'; InputBufferLength
0x18007cacc  mov     [rsp+0E0h+InputBuffer], rax; InputBuffer
0x18007cad1  lea     rax, [rbp+57h+var_90]
0x18007cad5  mov     [rsp+0E0h+IoControlCode], 128038h; IoControlCode
0x18007cadd  mov     [rsp+0E0h+IoStatusBlock], rax; IoStatusBlock
0x18007cae2  mov     [rbp+57h+var_6C], 0
0x18007cae9  mov     [rbp+57h+var_7C], 0
0x18007caf0  call    cs:__imp_NtDeviceIoControlFile
0x18007caf7  nop     dword ptr [rax+rax+00h]
0x18007cafc  mov     r15d, eax
0x18007caff  cmp     eax, 103h
0x18007cb04  jnz     short loc_18007CB1C
0x18007cb06  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18007cb09  mov     rcx, rdi; hHandle
0x18007cb0c  call    cs:__imp_WaitForSingleObject
0x18007cb13  nop     dword ptr [rax+rax+00h]
0x18007cb18  mov     r15d, dword ptr [rbp+57h+var_90]
0x18007cb1c  test    r15d, r15d
0x18007cb1f  jns     loc_18007CBCB
0x18007cb25  mov     rcx, rdi; hObject
0x18007cb28  call    cs:__imp_CloseHandle
0x18007cb2f  nop     dword ptr [rax+rax+00h]
0x18007cb34  lea     rcx, NatInterfaceLock; lpCriticalSection
0x18007cb3b  call    cs:__imp_LeaveCriticalSection
0x18007cb42  nop     dword ptr [rax+rax+00h]
0x18007cb47  mov     ecx, r15d; Status
0x18007cb4a  mov     dword ptr [rbx], 0
0x18007cb50  call    cs:__imp_RtlNtStatusToDosError
0x18007cb57  nop     dword ptr [rax+rax+00h]
0x18007cb5c  mov     ebx, eax
0x18007cb5e  mov     rcx, cs:WPP_GLOBAL_Control
0x18007cb65  lea     rdi, WPP_GLOBAL_Control
0x18007cb6c  cmp     rcx, rdi
0x18007cb6f  jz      loc_18007CD84
0x18007cb75  test    [rcx+1Ch], r12d
0x18007cb79  jz      short loc_18007CBA4
0x18007cb7b  cmp     byte ptr [rcx+19h], 2
0x18007cb7f  jb      short loc_18007CBA4
0x18007cb81  mov     rcx, [rcx+10h]
0x18007cb85  lea     r8, WPP_1a1a310d9f3938633825d91885f62d23_Traceguids
0x18007cb8c  mov     edx, 7Dh ; '}'
0x18007cb91  mov     dword ptr [rsp+0E0h+IoStatusBlock], eax
0x18007cb95  mov     r9d, r15d
0x18007cb98  call    WPP_SF_Dd
0x18007cb9d  mov     rcx, cs:WPP_GLOBAL_Control
0x18007cba4  cmp     rcx, rdi
0x18007cba7  jz      loc_18007CD84
0x18007cbad  test    [rcx+1Ch], r12d
0x18007cbb1  jz      loc_18007CD84
0x18007cbb7  cmp     byte ptr [rcx+19h], 6
0x18007cbbb  jb      loc_18007CD84
0x18007cbc1  mov     edx, 7Eh ; '~'
0x18007cbc6  jmp     loc_18007CD71
0x18007cbcb  mov     eax, [rbp+57h+var_68]
0x18007cbce  lea     ecx, [rax+rax*8]
0x18007cbd1  lea     r15d, ds:1Ch[rcx*4]
0x18007cbd9  mov     ecx, [rbx]
0x18007cbdb  cmp     ecx, r15d
0x18007cbde  jnb     short loc_18007CC4F
0x18007cbe0  mov     rcx, rdi; hObject
0x18007cbe3  call    cs:__imp_CloseHandle
0x18007cbea  nop     dword ptr [rax+rax+00h]
0x18007cbef  lea     rcx, NatInterfaceLock; lpCriticalSection
0x18007cbf6  call    cs:__imp_LeaveCriticalSection
0x18007cbfd  nop     dword ptr [rax+rax+00h]
0x18007cc02  lea     eax, [r15+0B4h]
0x18007cc09  mov     [rbx], eax
0x18007cc0b  mov     rcx, cs:WPP_GLOBAL_Control
0x18007cc12  lea     rdi, WPP_GLOBAL_Control
0x18007cc19  cmp     rcx, rdi
0x18007cc1c  jz      short loc_18007CC45
0x18007cc1e  test    [rcx+1Ch], r12d
0x18007cc22  jz      short loc_18007CC45
0x18007cc24  cmp     byte ptr [rcx+19h], 6
0x18007cc28  jb      short loc_18007CC45
0x18007cc2a  mov     edx, 7Fh
0x18007cc2f  lea     r8, WPP_1a1a310d9f3938633825d91885f62d23_Traceguids
0x18007cc36  mov     rcx, [rcx+10h]
0x18007cc3a  mov     r9d, 7Ah ; 'z'
0x18007cc40  call    WPP_SF_d
0x18007cc45  mov     eax, 7Ah ; 'z'
0x18007cc4a  jmp     loc_18007CD86
0x18007cc4f  mov     eax, [r13+14h]
0x18007cc53  xor     r9d, r9d; ApcContext
0x18007cc56  mov     [rsp+0E0h+OutputBufferLength], ecx; OutputBufferLength
0x18007cc5a  xor     r8d, r8d; ApcRoutine
0x18007cc5d  mov     rcx, cs:NatFileHandle; FileHandle
0x18007cc64  mov     rdx, rdi; Event
0x18007cc67  mov     [rsp+0E0h+OutputBuffer], rsi; OutputBuffer
0x18007cc6c  mov     [rbp+57h+var_80], eax
0x18007cc6f  lea     rax, [rbp+57h+var_80]
0x18007cc73  mov     [rsp+0E0h+InputBufferLength], 40h ; '@'; InputBufferLength
0x18007cc7b  mov     [rsp+0E0h+InputBuffer], rax; InputBuffer
0x18007cc80  lea     rax, [rbp+57h+var_90]
0x18007cc84  mov     [rsp+0E0h+IoControlCode], 128038h; IoControlCode
0x18007cc8c  mov     [rsp+0E0h+IoStatusBlock], rax; IoStatusBlock
0x18007cc91  mov     [rbp+57h+var_6C], 0
0x18007cc98  mov     [rbp+57h+var_7C], 0
0x18007cc9f  call    cs:__imp_NtDeviceIoControlFile
0x18007cca6  nop     dword ptr [rax+rax+00h]
0x18007ccab  mov     r15d, eax
0x18007ccae  cmp     eax, 103h
0x18007ccb3  jnz     short loc_18007CCCB
0x18007ccb5  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18007ccb8  mov     rcx, rdi; hHandle
0x18007ccbb  call    cs:__imp_WaitForSingleObject
0x18007ccc2  nop     dword ptr [rax+rax+00h]
0x18007ccc7  mov     r15d, dword ptr [rbp+57h+var_90]
0x18007cccb  mov     rcx, rdi; hObject
0x18007ccce  call    cs:__imp_CloseHandle
0x18007ccd5  nop     dword ptr [rax+rax+00h]
0x18007ccda  lea     rcx, NatInterfaceLock; lpCriticalSection
0x18007cce1  call    cs:__imp_LeaveCriticalSection
0x18007cce8  nop     dword ptr [rax+rax+00h]
0x18007cced  mov     eax, [rsi+14h]
0x18007ccf0  mov     [rsi], r14d
0x18007ccf3  lea     ecx, [rax+rax*8]
0x18007ccf6  lea     ecx, ds:1Ch[rcx*4]
0x18007ccfd  mov     [rbx], ecx
0x18007ccff  mov     rcx, cs:WPP_GLOBAL_Control
0x18007cd06  lea     rdi, WPP_GLOBAL_Control
0x18007cd0d  cmp     rcx, rdi
0x18007cd10  jz      short loc_18007CD3A
0x18007cd12  test    [rcx+1Ch], r12d
0x18007cd16  jz      short loc_18007CD3A
0x18007cd18  cmp     byte ptr [rcx+19h], 6
0x18007cd1c  jb      short loc_18007CD3A
0x18007cd1e  mov     rcx, [rcx+10h]
0x18007cd22  lea     r8, WPP_1a1a310d9f3938633825d91885f62d23_Traceguids
0x18007cd29  mov     edx, 80h
0x18007cd2e  call    WPP_SF_
0x18007cd33  mov     rcx, cs:WPP_GLOBAL_Control
0x18007cd3a  test    r15d, r15d
0x18007cd3d  js      short loc_18007CD43
0x18007cd3f  xor     ebx, ebx
0x18007cd41  jmp     short loc_18007CD5B
0x18007cd43  mov     ecx, r15d; Status
0x18007cd46  call    cs:__imp_RtlNtStatusToDosError
0x18007cd4d  nop     dword ptr [rax+rax+00h]
0x18007cd52  mov     rcx, cs:WPP_GLOBAL_Control
0x18007cd59  mov     ebx, eax
0x18007cd5b  cmp     rcx, rdi
0x18007cd5e  jz      short loc_18007CD84
  ... truncated ...
```
