# NatQueryInterfaceMappingTable

- ea: `0x180076944`
- end: `0x180076e61`
- name: `NatQueryInterfaceMappingTable`
- size: `1309`
- prototype: `__int64 __fastcall(unsigned int, PVOID OutputBuffer)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180073600`

## callees

- `0x18000c110`
- `0x18000c750`
- `0x18001ec08`
- `0x180032e10`
- `0x18004e0c0`
- `0x18004ed64`
- `0x180076944`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800769d4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800769d4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800769f3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180076a72`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180076b1b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180076c25`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180076cce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180076da1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800769f3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180076a72`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180076b1b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180076c25`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180076cce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180076da1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180076b02`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180076b02`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180076c02`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180076d87`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180076c02`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180076d87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076b47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076b47`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180076c18`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180076cc1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180076d94`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180076c18`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180076cc1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180076d94`
- `ntdll!NtDeviceIoControlFile` at `0x180076bec`
- `ntdll!NtDeviceIoControlFile` at `0x180076d71`
- `ntdll!NtDeviceIoControlFile` at `0x180076bec`
- `ntdll!NtDeviceIoControlFile` at `0x180076d71`
- `ntdll!RtlNtStatusToDosError` at `0x180076c34`
- `ntdll!RtlNtStatusToDosError` at `0x180076e00`
- `ntdll!RtlNtStatusToDosError` at `0x180076c34`
- `ntdll!RtlNtStatusToDosError` at `0x180076e00`

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
0x180076944  mov     [rsp-8+arg_18], rbx
0x180076949  push    rbp
0x18007694a  push    rsi
0x18007694b  push    rdi
0x18007694c  push    r12
0x18007694e  push    r13
0x180076950  push    r14
0x180076952  push    r15
0x180076954  lea     rbp, [rsp-27h]
0x180076959  sub     rsp, 0B0h
0x180076960  mov     rax, cs:__security_cookie
0x180076967  xor     rax, rsp
0x18007696a  mov     [rbp+57h+var_40], rax
0x18007696e  mov     rbx, r8
0x180076971  mov     rsi, rdx
0x180076974  mov     r14d, ecx
0x180076977  mov     rcx, cs:WPP_GLOBAL_Control
0x18007697e  lea     rdi, WPP_GLOBAL_Control
0x180076985  lea     r15, WPP_1a1a310d9f3938633825d91885f62d23_Traceguids
0x18007698c  mov     r12d, 200h
0x180076992  cmp     rcx, rdi
0x180076995  jz      short loc_1800769B7
0x180076997  test    [rcx+1Ch], r12d
0x18007699b  jz      short loc_1800769B7
0x18007699d  cmp     byte ptr [rcx+19h], 6
0x1800769a1  jb      short loc_1800769B7
0x1800769a3  mov     rcx, [rcx+10h]
0x1800769a7  mov     edx, 76h ; 'v'
0x1800769ac  mov     r9d, r14d
0x1800769af  mov     r8, r15
0x1800769b2  call    WPP_SF_d
0x1800769b7  xor     edx, edx; Val
0x1800769b9  lea     rcx, [rbp+57h+var_80]; void *
0x1800769bd  lea     r8d, [rdx+40h]; Size
0x1800769c1  call    memset_0
0x1800769c6  xorps   xmm0, xmm0
0x1800769c9  lea     rcx, NatInterfaceLock; lpCriticalSection
0x1800769d0  movups  xmmword ptr [rbp+57h+var_90], xmm0
0x1800769d4  call    cs:__imp_EnterCriticalSection
0x1800769da  xor     edx, edx; struct _LIST_ENTRY **
0x1800769dc  mov     ecx, r14d; unsigned int
0x1800769df  call    ?NatLookupInterface@@YAPEAU_NAT_INTERFACE@@KPEAPEAU_LIST_ENTRY@@@Z; NatLookupInterface(ulong,_LIST_ENTRY * *)
0x1800769e4  mov     r13, rax
0x1800769e7  test    rax, rax
0x1800769ea  jnz     short loc_180076A5E
0x1800769ec  lea     rcx, NatInterfaceLock; lpCriticalSection
0x1800769f3  call    cs:__imp_LeaveCriticalSection
0x1800769f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180076a00  mov     ebx, 389h
0x180076a05  cmp     rcx, rdi
0x180076a08  jz      loc_180076E38
0x180076a0e  test    [rcx+1Ch], r12d
0x180076a12  jz      short loc_180076A34
0x180076a14  cmp     byte ptr [rcx+19h], 2
0x180076a18  jb      short loc_180076A34
0x180076a1a  mov     rcx, [rcx+10h]
0x180076a1e  lea     edx, [r13+77h]
0x180076a22  mov     r9d, r14d
0x180076a25  mov     r8, r15
0x180076a28  call    WPP_SF_d
0x180076a2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180076a34  cmp     rcx, rdi
0x180076a37  jz      loc_180076E38
0x180076a3d  test    [rcx+1Ch], r12d
0x180076a41  jz      loc_180076E38
0x180076a47  cmp     byte ptr [rcx+19h], 6
0x180076a4b  jb      loc_180076E38
0x180076a51  mov     edx, 78h ; 'x'
0x180076a56  mov     r8, r15
0x180076a59  jmp     loc_180076E2C
0x180076a5e  test    dword ptr [rax+1Ch], 40000000h
0x180076a65  jnz     loc_180076AF8
0x180076a6b  lea     rcx, NatInterfaceLock; lpCriticalSection
0x180076a72  call    cs:__imp_LeaveCriticalSection
0x180076a78  mov     eax, 1Ch
0x180076a7d  cmp     [rbx], eax
0x180076a7f  jnb     short loc_180076AB2
0x180076a81  mov     [rbx], eax
0x180076a83  mov     rcx, cs:WPP_GLOBAL_Control
0x180076a8a  cmp     rcx, rdi
0x180076a8d  jz      loc_180076D17
0x180076a93  test    [rcx+1Ch], r12d
0x180076a97  jz      loc_180076D17
0x180076a9d  cmp     byte ptr [rcx+19h], 6
0x180076aa1  jb      loc_180076D17
0x180076aa7  lea     edx, [rax+5Dh]
0x180076aaa  mov     r8, r15
0x180076aad  jmp     loc_180076D08
0x180076ab2  mov     [rsi], r14d
0x180076ab5  mov     dword ptr [rsi+4], 0
0x180076abc  mov     dword ptr [rsi+14h], 0
0x180076ac3  mov     [rbx], eax
0x180076ac5  mov     rcx, cs:WPP_GLOBAL_Control
0x180076acc  cmp     rcx, rdi
0x180076acf  jz      short loc_180076AF1
0x180076ad1  test    [rcx+1Ch], r12d
0x180076ad5  jz      short loc_180076AF1
0x180076ad7  cmp     byte ptr [rcx+19h], 6
0x180076adb  jb      short loc_180076AF1
0x180076add  mov     rcx, [rcx+10h]
0x180076ae1  mov     edx, 7Ah ; 'z'
0x180076ae6  xor     r9d, r9d
0x180076ae9  mov     r8, r15
0x180076aec  call    WPP_SF_d
0x180076af1  xor     eax, eax
0x180076af3  jmp     loc_180076E3A
0x180076af8  xor     r9d, r9d; lpName
0x180076afb  xor     r8d, r8d; bInitialState
0x180076afe  xor     edx, edx; bManualReset
0x180076b00  xor     ecx, ecx; lpEventAttributes
0x180076b02  call    cs:__imp_CreateEventW
0x180076b08  mov     rdi, rax
0x180076b0b  test    rax, rax
0x180076b0e  jnz     loc_180076B94
0x180076b14  lea     rcx, NatInterfaceLock; lpCriticalSection
0x180076b1b  call    cs:__imp_LeaveCriticalSection
0x180076b21  mov     rcx, cs:WPP_GLOBAL_Control
0x180076b28  lea     ebx, [rdi+8]
0x180076b2b  lea     rdi, WPP_GLOBAL_Control
0x180076b32  cmp     rcx, rdi
0x180076b35  jz      loc_180076E38
0x180076b3b  test    [rcx+1Ch], r12d
0x180076b3f  jz      short loc_180076B6D
0x180076b41  cmp     byte ptr [rcx+19h], 2
0x180076b45  jb      short loc_180076B6D
0x180076b47  call    cs:__imp_GetLastError
0x180076b4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180076b54  lea     edx, [rbx+73h]
0x180076b57  mov     r9d, eax
0x180076b5a  mov     r8, r15
0x180076b5d  mov     rcx, [rcx+10h]
0x180076b61  call    WPP_SF_d
0x180076b66  mov     rcx, cs:WPP_GLOBAL_Control
0x180076b6d  cmp     rcx, rdi
0x180076b70  jz      loc_180076E38
0x180076b76  test    [rcx+1Ch], r12d
0x180076b7a  jz      loc_180076E38
0x180076b80  cmp     byte ptr [rcx+19h], 6
0x180076b84  jb      loc_180076E38
0x180076b8a  mov     edx, 7Ch ; '|'
0x180076b8f  jmp     loc_180076A56
0x180076b94  mov     eax, [r13+14h]
0x180076b98  xor     r9d, r9d; ApcContext
0x180076b9b  mov     rcx, cs:NatFileHandle; FileHandle
0x180076ba2  xor     r8d, r8d; ApcRoutine
0x180076ba5  mov     [rsp+0E0h+OutputBufferLength], 40h ; '@'; OutputBufferLength
0x180076bad  mov     rdx, rdi; Event
0x180076bb0  mov     [rbp+57h+var_80], eax
0x180076bb3  lea     rax, [rbp+57h+var_80]
0x180076bb7  mov     [rsp+0E0h+OutputBuffer], rax; OutputBuffer
0x180076bbc  lea     rax, [rbp+57h+var_80]
0x180076bc0  mov     [rsp+0E0h+InputBufferLength], 40h ; '@'; InputBufferLength
0x180076bc8  mov     [rsp+0E0h+InputBuffer], rax; InputBuffer
0x180076bcd  lea     rax, [rbp+57h+var_90]
0x180076bd1  mov     [rsp+0E0h+IoControlCode], 128038h; IoControlCode
0x180076bd9  mov     [rsp+0E0h+IoStatusBlock], rax; IoStatusBlock
0x180076bde  mov     [rbp+57h+var_6C], 0
0x180076be5  mov     [rbp+57h+var_7C], 0
0x180076bec  call    cs:__imp_NtDeviceIoControlFile
0x180076bf2  mov     r15d, eax
0x180076bf5  cmp     eax, 103h
0x180076bfa  jnz     short loc_180076C0C
0x180076bfc  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180076bff  mov     rcx, rdi; hHandle
0x180076c02  call    cs:__imp_WaitForSingleObject
0x180076c08  mov     r15d, dword ptr [rbp+57h+var_90]
0x180076c0c  test    r15d, r15d
0x180076c0f  jns     loc_180076CA9
0x180076c15  mov     rcx, rdi; hObject
0x180076c18  call    cs:__imp_CloseHandle
0x180076c1e  lea     rcx, NatInterfaceLock; lpCriticalSection
0x180076c25  call    cs:__imp_LeaveCriticalSection
0x180076c2b  mov     ecx, r15d; Status
0x180076c2e  mov     dword ptr [rbx], 0
0x180076c34  call    cs:__imp_RtlNtStatusToDosError
0x180076c3a  mov     ebx, eax
0x180076c3c  mov     rcx, cs:WPP_GLOBAL_Control
0x180076c43  lea     rdi, WPP_GLOBAL_Control
0x180076c4a  cmp     rcx, rdi
0x180076c4d  jz      loc_180076E38
0x180076c53  test    [rcx+1Ch], r12d
0x180076c57  jz      short loc_180076C82
0x180076c59  cmp     byte ptr [rcx+19h], 2
0x180076c5d  jb      short loc_180076C82
0x180076c5f  mov     rcx, [rcx+10h]
0x180076c63  lea     r8, WPP_1a1a310d9f3938633825d91885f62d23_Traceguids
0x180076c6a  mov     edx, 7Dh ; '}'
0x180076c6f  mov     dword ptr [rsp+0E0h+IoStatusBlock], eax
0x180076c73  mov     r9d, r15d
0x180076c76  call    WPP_SF_Dd
0x180076c7b  mov     rcx, cs:WPP_GLOBAL_Control
0x180076c82  cmp     rcx, rdi
0x180076c85  jz      loc_180076E38
0x180076c8b  test    [rcx+1Ch], r12d
0x180076c8f  jz      loc_180076E38
0x180076c95  cmp     byte ptr [rcx+19h], 6
0x180076c99  jb      loc_180076E38
0x180076c9f  mov     edx, 7Eh ; '~'
0x180076ca4  jmp     loc_180076E25
0x180076ca9  mov     eax, [rbp+57h+var_68]
0x180076cac  lea     ecx, [rax+rax*8]
0x180076caf  lea     r15d, ds:1Ch[rcx*4]
0x180076cb7  mov     ecx, [rbx]
0x180076cb9  cmp     ecx, r15d
0x180076cbc  jnb     short loc_180076D21
0x180076cbe  mov     rcx, rdi; hObject
0x180076cc1  call    cs:__imp_CloseHandle
0x180076cc7  lea     rcx, NatInterfaceLock; lpCriticalSection
0x180076cce  call    cs:__imp_LeaveCriticalSection
0x180076cd4  lea     eax, [r15+0B4h]
0x180076cdb  mov     [rbx], eax
0x180076cdd  mov     rcx, cs:WPP_GLOBAL_Control
0x180076ce4  lea     rdi, WPP_GLOBAL_Control
0x180076ceb  cmp     rcx, rdi
0x180076cee  jz      short loc_180076D17
0x180076cf0  test    [rcx+1Ch], r12d
0x180076cf4  jz      short loc_180076D17
0x180076cf6  cmp     byte ptr [rcx+19h], 6
0x180076cfa  jb      short loc_180076D17
0x180076cfc  mov     edx, 7Fh
0x180076d01  lea     r8, WPP_1a1a310d9f3938633825d91885f62d23_Traceguids
0x180076d08  mov     rcx, [rcx+10h]
0x180076d0c  mov     r9d, 7Ah ; 'z'
0x180076d12  call    WPP_SF_d
0x180076d17  mov     eax, 7Ah ; 'z'
0x180076d1c  jmp     loc_180076E3A
0x180076d21  mov     eax, [r13+14h]
0x180076d25  xor     r9d, r9d; ApcContext
0x180076d28  mov     [rsp+0E0h+OutputBufferLength], ecx; OutputBufferLength
0x180076d2c  xor     r8d, r8d; ApcRoutine
0x180076d2f  mov     rcx, cs:NatFileHandle; FileHandle
0x180076d36  mov     rdx, rdi; Event
0x180076d39  mov     [rsp+0E0h+OutputBuffer], rsi; OutputBuffer
0x180076d3e  mov     [rbp+57h+var_80], eax
0x180076d41  lea     rax, [rbp+57h+var_80]
0x180076d45  mov     [rsp+0E0h+InputBufferLength], 40h ; '@'; InputBufferLength
0x180076d4d  mov     [rsp+0E0h+InputBuffer], rax; InputBuffer
0x180076d52  lea     rax, [rbp+57h+var_90]
0x180076d56  mov     [rsp+0E0h+IoControlCode], 128038h; IoControlCode
0x180076d5e  mov     [rsp+0E0h+IoStatusBlock], rax; IoStatusBlock
0x180076d63  mov     [rbp+57h+var_6C], 0
0x180076d6a  mov     [rbp+57h+var_7C], 0
0x180076d71  call    cs:__imp_NtDeviceIoControlFile
0x180076d77  mov     r15d, eax
0x180076d7a  cmp     eax, 103h
0x180076d7f  jnz     short loc_180076D91
0x180076d81  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180076d84  mov     rcx, rdi; hHandle
0x180076d87  call    cs:__imp_WaitForSingleObject
0x180076d8d  mov     r15d, dword ptr [rbp+57h+var_90]
0x180076d91  mov     rcx, rdi; hObject
0x180076d94  call    cs:__imp_CloseHandle
0x180076d9a  lea     rcx, NatInterfaceLock; lpCriticalSection
0x180076da1  call    cs:__imp_LeaveCriticalSection
0x180076da7  mov     eax, [rsi+14h]
0x180076daa  mov     [rsi], r14d
0x180076dad  lea     ecx, [rax+rax*8]
0x180076db0  lea     ecx, ds:1Ch[rcx*4]
0x180076db7  mov     [rbx], ecx
0x180076db9  mov     rcx, cs:WPP_GLOBAL_Control
0x180076dc0  lea     rdi, WPP_GLOBAL_Control
0x180076dc7  cmp     rcx, rdi
0x180076dca  jz      short loc_180076DF4
0x180076dcc  test    [rcx+1Ch], r12d
0x180076dd0  jz      short loc_180076DF4
0x180076dd2  cmp     byte ptr [rcx+19h], 6
0x180076dd6  jb      short loc_180076DF4
0x180076dd8  mov     rcx, [rcx+10h]
0x180076ddc  lea     r8, WPP_1a1a310d9f3938633825d91885f62d23_Traceguids
0x180076de3  mov     edx, 80h
0x180076de8  call    WPP_SF_
0x180076ded  mov     rcx, cs:WPP_GLOBAL_Control
0x180076df4  test    r15d, r15d
0x180076df7  js      short loc_180076DFD
0x180076df9  xor     ebx, ebx
0x180076dfb  jmp     short loc_180076E0F
0x180076dfd  mov     ecx, r15d; Status
0x180076e00  call    cs:__imp_RtlNtStatusToDosError
0x180076e06  mov     rcx, cs:WPP_GLOBAL_Control
0x180076e0d  mov     ebx, eax
0x180076e0f  cmp     rcx, rdi
0x180076e12  jz      short loc_180076E38
0x180076e14  test    [rcx+1Ch], r12d
0x180076e18  jz      short loc_180076E38
0x180076e1a  cmp     byte ptr [rcx+19h], 6
0x180076e1e  jb      short loc_180076E38
0x180076e20  mov     edx, 81h
0x180076e25  lea     r8, WPP_1a1a310d9f3938633825d91885f62d23_Traceguids
0x180076e2c  mov     rcx, [rcx+10h]
0x180076e30  mov     r9d, ebx
0x180076e33  call    WPP_SF_d
0x180076e38  mov     eax, ebx
0x180076e3a  mov     rcx, [rbp+57h+var_40]
0x180076e3e  xor     rcx, rsp; StackCookie
0x180076e41  call    __security_check_cookie
0x180076e46  mov     rbx, [rsp+0E0h+arg_18]
0x180076e4e  add     rsp, 0B0h
0x180076e55  pop     r15
0x180076e57  pop     r14
0x180076e59  pop     r13
  ... truncated ...
```
