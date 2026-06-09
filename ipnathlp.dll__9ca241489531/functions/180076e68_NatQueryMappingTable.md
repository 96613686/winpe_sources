# NatQueryMappingTable

- ea: `0x180076e68`
- end: `0x1800771d4`
- name: `NatQueryMappingTable`
- size: `876`
- prototype: `__int64 __fastcall(PVOID OutputBuffer)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180073600`

## callees

- `0x18000c110`
- `0x18000c750`
- `0x18001ec08`
- `0x18004e0c0`
- `0x18004ed64`
- `0x180076e68`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180076f7a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180076f7a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180076ff6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180077091`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180077150`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180076ff6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180077091`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180077150`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180076ef9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180076ef9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180076fde`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180077137`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180076fde`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180077137`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076f26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076f26`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180076fff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007709a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180077143`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180076fff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007709a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180077143`
- `ntdll!NtDeviceIoControlFile` at `0x180076fc9`
- `ntdll!NtDeviceIoControlFile` at `0x180077122`
- `ntdll!NtDeviceIoControlFile` at `0x180076fc9`
- `ntdll!NtDeviceIoControlFile` at `0x180077122`
- `ntdll!RtlNtStatusToDosError` at `0x18007700d`
- `ntdll!RtlNtStatusToDosError` at `0x180077177`
- `ntdll!RtlNtStatusToDosError` at `0x18007700d`
- `ntdll!RtlNtStatusToDosError` at `0x180077177`

## pseudocode

```c
__int64 __fastcall NatQueryMappingTable(_DWORD *OutputBuffer, ULONG *a2)
{
  HANDLE EventW; // rbx
  PVOID *v5; // rcx
  ULONG v6; // ebx
  DWORD LastError; // eax
  __int64 v8; // rdx
  int Status; // edi
  ULONG v10; // eax
  ULONG OutputBufferLength; // eax
  unsigned int v12; // edi
  int v13; // edi
  int v14; // eax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-39h] BYREF
  _BYTE InputBuffer[4]; // [rsp+60h] [rbp-29h] BYREF
  int v18; // [rsp+64h] [rbp-25h]
  int v19; // [rsp+74h] [rbp-15h]
  int v20; // [rsp+78h] [rbp-11h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 130, &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids);
  }
  memset_0(InputBuffer, 0, 0x40u);
  IoStatusBlock = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  if ( EventW )
  {
    EnterCriticalSection(&NatInterfaceLock);
    v19 = 0;
    v18 = 0;
    Status = NtDeviceIoControlFile(
               NatFileHandle,
               EventW,
               0,
               0,
               &IoStatusBlock,
               0x128028u,
               InputBuffer,
               0x40u,
               InputBuffer,
               0x40u);
    if ( Status == 259 )
    {
      WaitForSingleObject(EventW, 0xFFFFFFFF);
      Status = IoStatusBlock.Status;
    }
    if ( Status >= 0 )
    {
      OutputBufferLength = *a2;
      v12 = 36 * v20 + 28;
      if ( *a2 >= v12 )
      {
        v19 = 0;
        v18 = 0;
        v13 = NtDeviceIoControlFile(
                NatFileHandle,
                EventW,
                0,
                0,
                &IoStatusBlock,
                0x128028u,
                InputBuffer,
                0x40u,
                OutputBuffer,
                OutputBufferLength);
        if ( v13 == 259 )
        {
          WaitForSingleObject(EventW, 0xFFFFFFFF);
          v13 = IoStatusBlock.Status;
        }
        CloseHandle(EventW);
        LeaveCriticalSection(&NatInterfaceLock);
        v14 = OutputBuffer[5];
        *OutputBuffer = -1;
        *a2 = 36 * v14 + 28;
        if ( v13 < 0 )
          v6 = RtlNtStatusToDosError(v13);
        else
          v6 = 0;
        v5 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
        {
          v8 = 136;
          goto LABEL_39;
        }
      }
      else
      {
        LeaveCriticalSection(&NatInterfaceLock);
        CloseHandle(EventW);
        *a2 = v12 + 180;
        v5 = (PVOID *)WPP_GLOBAL_Control;
        v6 = 122;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
        {
          v8 = 135;
          goto LABEL_39;
        }
      }
    }
    else
    {
      LeaveCriticalSection(&NatInterfaceLock);
      CloseHandle(EventW);
      *a2 = 0;
      v10 = RtlNtStatusToDosError(Status);
      v6 = v10;
      v5 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            133,
            &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids,
            (unsigned int)Status,
            v10);
          v5 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v5 != &WPP_GLOBAL_Control && (*((_DWORD *)v5 + 7) & 0x200) != 0 && *((_BYTE *)v5 + 25) >= 6u )
        {
          v8 = 134;
          goto LABEL_39;
        }
      }
    }
  }
  else
  {
    v5 = (PVOID *)WPP_GLOBAL_Control;
    v6 = 8;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 131, &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids, LastError);
        v5 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v5 != &WPP_GLOBAL_Control && (*((_DWORD *)v5 + 7) & 0x200) != 0 && *((_BYTE *)v5 + 25) >= 6u )
      {
        v8 = 132;
LABEL_39:
        WPP_SF_d(v5[2], v8, &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids, v6);
      }
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180076e68  mov     [rsp-8+arg_10], rbx
0x180076e6d  push    rbp
0x180076e6e  push    rsi
0x180076e6f  push    rdi
0x180076e70  push    r12
0x180076e72  push    r13
0x180076e74  push    r14
0x180076e76  push    r15
0x180076e78  lea     rbp, [rsp-27h]
0x180076e7d  sub     rsp, 0B0h
0x180076e84  mov     rax, cs:__security_cookie
0x180076e8b  xor     rax, rsp
0x180076e8e  mov     [rbp+57h+var_40], rax
0x180076e92  mov     rsi, rdx
0x180076e95  mov     r14, rcx
0x180076e98  mov     rcx, cs:WPP_GLOBAL_Control
0x180076e9f  lea     r12, WPP_GLOBAL_Control
0x180076ea6  lea     r13, WPP_1a1a310d9f3938633825d91885f62d23_Traceguids
0x180076ead  mov     r15d, 200h
0x180076eb3  cmp     rcx, r12
0x180076eb6  jz      short loc_180076ED5
0x180076eb8  test    [rcx+1Ch], r15d
0x180076ebc  jz      short loc_180076ED5
0x180076ebe  cmp     byte ptr [rcx+19h], 6
0x180076ec2  jb      short loc_180076ED5
0x180076ec4  mov     rcx, [rcx+10h]
0x180076ec8  mov     edx, 82h
0x180076ecd  mov     r8, r13
0x180076ed0  call    WPP_SF_
0x180076ed5  mov     edi, 40h ; '@'
0x180076eda  lea     rcx, [rbp+57h+var_80]; void *
0x180076ede  mov     r8d, edi; Size
0x180076ee1  xor     edx, edx; Val
0x180076ee3  call    memset_0
0x180076ee8  xorps   xmm0, xmm0
0x180076eeb  xor     r9d, r9d; lpName
0x180076eee  xor     r8d, r8d; bInitialState
0x180076ef1  xor     edx, edx; bManualReset
0x180076ef3  xor     ecx, ecx; lpEventAttributes
0x180076ef5  movups  xmmword ptr [rbp+57h+var_90], xmm0
0x180076ef9  call    cs:__imp_CreateEventW
0x180076eff  mov     rbx, rax
0x180076f02  test    rax, rax
0x180076f05  jnz     short loc_180076F73
0x180076f07  mov     rcx, cs:WPP_GLOBAL_Control
0x180076f0e  lea     ebx, [rdi-38h]
0x180076f11  cmp     rcx, r12
0x180076f14  jz      loc_1800771AB
0x180076f1a  test    [rcx+1Ch], r15d
0x180076f1e  jz      short loc_180076F4C
0x180076f20  cmp     byte ptr [rcx+19h], 2
0x180076f24  jb      short loc_180076F4C
0x180076f26  call    cs:__imp_GetLastError
0x180076f2c  mov     rcx, cs:WPP_GLOBAL_Control
0x180076f33  lea     edx, [rdi+43h]
0x180076f36  mov     r9d, eax
0x180076f39  mov     r8, r13
0x180076f3c  mov     rcx, [rcx+10h]
0x180076f40  call    WPP_SF_d
0x180076f45  mov     rcx, cs:WPP_GLOBAL_Control
0x180076f4c  cmp     rcx, r12
0x180076f4f  jz      loc_1800771AB
0x180076f55  test    [rcx+1Ch], r15d
0x180076f59  jz      loc_1800771AB
0x180076f5f  cmp     byte ptr [rcx+19h], 6
0x180076f63  jb      loc_1800771AB
0x180076f69  mov     edx, 84h
0x180076f6e  jmp     loc_18007719C
0x180076f73  lea     rcx, NatInterfaceLock; lpCriticalSection
0x180076f7a  call    cs:__imp_EnterCriticalSection
0x180076f80  mov     rcx, cs:NatFileHandle; FileHandle
0x180076f87  lea     rax, [rbp+57h+var_80]
0x180076f8b  mov     [rsp+0E0h+OutputBufferLength], edi; OutputBufferLength
0x180076f8f  xor     r9d, r9d; ApcContext
0x180076f92  mov     [rsp+0E0h+OutputBuffer], rax; OutputBuffer
0x180076f97  xor     r8d, r8d; ApcRoutine
0x180076f9a  mov     [rsp+0E0h+InputBufferLength], edi; InputBufferLength
0x180076f9e  lea     rax, [rbp+57h+var_80]
0x180076fa2  mov     [rsp+0E0h+InputBuffer], rax; InputBuffer
0x180076fa7  mov     rdx, rbx; Event
0x180076faa  lea     rax, [rbp+57h+var_90]
0x180076fae  mov     [rsp+0E0h+IoControlCode], 128028h; IoControlCode
0x180076fb6  mov     [rsp+0E0h+IoStatusBlock], rax; IoStatusBlock
0x180076fbb  mov     [rbp+57h+var_6C], 0
0x180076fc2  mov     [rbp+57h+var_7C], 0
0x180076fc9  call    cs:__imp_NtDeviceIoControlFile
0x180076fcf  mov     edi, eax
0x180076fd1  cmp     eax, 103h
0x180076fd6  jnz     short loc_180076FE7
0x180076fd8  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180076fdb  mov     rcx, rbx; hHandle
0x180076fde  call    cs:__imp_WaitForSingleObject
0x180076fe4  mov     edi, dword ptr [rbp+57h+var_90]
0x180076fe7  test    edi, edi
0x180076fe9  jns     loc_180077077
0x180076fef  lea     rcx, NatInterfaceLock; lpCriticalSection
0x180076ff6  call    cs:__imp_LeaveCriticalSection
0x180076ffc  mov     rcx, rbx; hObject
0x180076fff  call    cs:__imp_CloseHandle
0x180077005  mov     ecx, edi; Status
0x180077007  mov     dword ptr [rsi], 0
0x18007700d  call    cs:__imp_RtlNtStatusToDosError
0x180077013  mov     ebx, eax
0x180077015  mov     rcx, cs:WPP_GLOBAL_Control
0x18007701c  cmp     rcx, r12
0x18007701f  jz      loc_1800771AB
0x180077025  test    [rcx+1Ch], r15d
0x180077029  jz      short loc_180077050
0x18007702b  cmp     byte ptr [rcx+19h], 2
0x18007702f  jb      short loc_180077050
0x180077031  mov     rcx, [rcx+10h]
0x180077035  mov     edx, 85h
0x18007703a  mov     r9d, edi
0x18007703d  mov     dword ptr [rsp+0E0h+IoStatusBlock], eax
0x180077041  mov     r8, r13
0x180077044  call    WPP_SF_Dd
0x180077049  mov     rcx, cs:WPP_GLOBAL_Control
0x180077050  cmp     rcx, r12
0x180077053  jz      loc_1800771AB
0x180077059  test    [rcx+1Ch], r15d
0x18007705d  jz      loc_1800771AB
0x180077063  cmp     byte ptr [rcx+19h], 6
0x180077067  jb      loc_1800771AB
0x18007706d  mov     edx, 86h
0x180077072  jmp     loc_18007719C
0x180077077  mov     eax, [rbp+57h+var_68]
0x18007707a  lea     ecx, [rax+rax*8]
0x18007707d  mov     eax, [rsi]
0x18007707f  lea     edi, ds:1Ch[rcx*4]
0x180077086  cmp     eax, edi
0x180077088  jnb     short loc_1800770D9
0x18007708a  lea     rcx, NatInterfaceLock; lpCriticalSection
0x180077091  call    cs:__imp_LeaveCriticalSection
0x180077097  mov     rcx, rbx; hObject
0x18007709a  call    cs:__imp_CloseHandle
0x1800770a0  lea     eax, [rdi+0B4h]
0x1800770a6  mov     [rsi], eax
0x1800770a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800770af  mov     ebx, 7Ah ; 'z'
0x1800770b4  cmp     rcx, r12
0x1800770b7  jz      loc_1800771AB
0x1800770bd  test    [rcx+1Ch], r15d
0x1800770c1  jz      loc_1800771AB
0x1800770c7  cmp     byte ptr [rcx+19h], 6
0x1800770cb  jb      loc_1800771AB
0x1800770d1  lea     edx, [rbx+0Dh]
0x1800770d4  jmp     loc_18007719C
0x1800770d9  mov     rcx, cs:NatFileHandle; FileHandle
0x1800770e0  xor     r9d, r9d; ApcContext
0x1800770e3  mov     [rsp+0E0h+OutputBufferLength], eax; OutputBufferLength
0x1800770e7  xor     r8d, r8d; ApcRoutine
0x1800770ea  mov     [rsp+0E0h+OutputBuffer], r14; OutputBuffer
0x1800770ef  lea     rax, [rbp+57h+var_80]
0x1800770f3  mov     [rsp+0E0h+InputBufferLength], 40h ; '@'; InputBufferLength
0x1800770fb  mov     rdx, rbx; Event
0x1800770fe  mov     [rsp+0E0h+InputBuffer], rax; InputBuffer
0x180077103  lea     rax, [rbp+57h+var_90]
0x180077107  mov     [rsp+0E0h+IoControlCode], 128028h; IoControlCode
0x18007710f  mov     [rsp+0E0h+IoStatusBlock], rax; IoStatusBlock
0x180077114  mov     [rbp+57h+var_6C], 0
0x18007711b  mov     [rbp+57h+var_7C], 0
0x180077122  call    cs:__imp_NtDeviceIoControlFile
0x180077128  mov     edi, eax
0x18007712a  cmp     eax, 103h
0x18007712f  jnz     short loc_180077140
0x180077131  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180077134  mov     rcx, rbx; hHandle
0x180077137  call    cs:__imp_WaitForSingleObject
0x18007713d  mov     edi, dword ptr [rbp+57h+var_90]
0x180077140  mov     rcx, rbx; hObject
0x180077143  call    cs:__imp_CloseHandle
0x180077149  lea     rcx, NatInterfaceLock; lpCriticalSection
0x180077150  call    cs:__imp_LeaveCriticalSection
0x180077156  mov     eax, [r14+14h]
0x18007715a  mov     dword ptr [r14], 0FFFFFFFFh
0x180077161  lea     ecx, [rax+rax*8]
0x180077164  lea     ecx, ds:1Ch[rcx*4]
0x18007716b  mov     [rsi], ecx
0x18007716d  test    edi, edi
0x18007716f  js      short loc_180077175
0x180077171  xor     ebx, ebx
0x180077173  jmp     short loc_18007717F
0x180077175  mov     ecx, edi; Status
0x180077177  call    cs:__imp_RtlNtStatusToDosError
0x18007717d  mov     ebx, eax
0x18007717f  mov     rcx, cs:WPP_GLOBAL_Control
0x180077186  cmp     rcx, r12
0x180077189  jz      short loc_1800771AB
0x18007718b  test    [rcx+1Ch], r15d
0x18007718f  jz      short loc_1800771AB
0x180077191  cmp     byte ptr [rcx+19h], 6
0x180077195  jb      short loc_1800771AB
0x180077197  mov     edx, 88h
0x18007719c  mov     rcx, [rcx+10h]
0x1800771a0  mov     r9d, ebx
0x1800771a3  mov     r8, r13
0x1800771a6  call    WPP_SF_d
0x1800771ab  mov     eax, ebx
0x1800771ad  mov     rcx, [rbp+57h+var_40]
0x1800771b1  xor     rcx, rsp; StackCookie
0x1800771b4  call    __security_check_cookie
0x1800771b9  mov     rbx, [rsp+0E0h+arg_10]
0x1800771c1  add     rsp, 0B0h
0x1800771c8  pop     r15
0x1800771ca  pop     r14
0x1800771cc  pop     r13
0x1800771ce  pop     r12
0x1800771d0  pop     rdi
0x1800771d1  pop     rsi
0x1800771d2  pop     rbp
0x1800771d3  retn
```
