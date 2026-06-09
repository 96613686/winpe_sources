# NatQueryMappingTable

- ea: `0x18007cdb4`
- end: `0x18007d17b`
- name: `NatQueryMappingTable`
- size: `967`
- prototype: `__int64 __fastcall(PVOID OutputBuffer)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180079170`

## callees

- `0x18000ca20`
- `0x18000d090`
- `0x1800202e0`
- `0x180051f30`
- `0x180052bf4`
- `0x18007cdb4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007ced2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007ced2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007cf60`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007d00d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007d0ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007cf60`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007d00d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007d0ea`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007ce45`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007ce45`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007cf42`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007d0c5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007cf42`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007d0c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ce78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ce78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007cf6f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007d01c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007d0d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007cf6f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007d01c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007d0d7`
- `ntdll!NtDeviceIoControlFile` at `0x18007cf27`
- `ntdll!NtDeviceIoControlFile` at `0x18007d0aa`
- `ntdll!NtDeviceIoControlFile` at `0x18007cf27`
- `ntdll!NtDeviceIoControlFile` at `0x18007d0aa`
- `ntdll!RtlNtStatusToDosError` at `0x18007cf83`
- `ntdll!RtlNtStatusToDosError` at `0x18007d117`
- `ntdll!RtlNtStatusToDosError` at `0x18007cf83`
- `ntdll!RtlNtStatusToDosError` at `0x18007d117`

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
0x18007cdb4  mov     [rsp-8+arg_10], rbx
0x18007cdb9  push    rbp
0x18007cdba  push    rsi
0x18007cdbb  push    rdi
0x18007cdbc  push    r12
0x18007cdbe  push    r13
0x18007cdc0  push    r14
0x18007cdc2  push    r15
0x18007cdc4  lea     rbp, [rsp-27h]
0x18007cdc9  sub     rsp, 0B0h
0x18007cdd0  mov     rax, cs:__security_cookie
0x18007cdd7  xor     rax, rsp
0x18007cdda  mov     [rbp+57h+var_40], rax
0x18007cdde  mov     rsi, rdx
0x18007cde1  mov     r14, rcx
0x18007cde4  mov     rcx, cs:WPP_GLOBAL_Control
0x18007cdeb  lea     r12, WPP_GLOBAL_Control
0x18007cdf2  lea     r13, WPP_1a1a310d9f3938633825d91885f62d23_Traceguids
0x18007cdf9  mov     r15d, 200h
0x18007cdff  cmp     rcx, r12
0x18007ce02  jz      short loc_18007CE21
0x18007ce04  test    [rcx+1Ch], r15d
0x18007ce08  jz      short loc_18007CE21
0x18007ce0a  cmp     byte ptr [rcx+19h], 6
0x18007ce0e  jb      short loc_18007CE21
0x18007ce10  mov     rcx, [rcx+10h]
0x18007ce14  mov     edx, 82h
0x18007ce19  mov     r8, r13
0x18007ce1c  call    WPP_SF_
0x18007ce21  mov     edi, 40h ; '@'
0x18007ce26  lea     rcx, [rbp+57h+var_80]; void *
0x18007ce2a  mov     r8d, edi; Size
0x18007ce2d  xor     edx, edx; Val
0x18007ce2f  call    memset_0
0x18007ce34  xorps   xmm0, xmm0
0x18007ce37  xor     r9d, r9d; lpName
0x18007ce3a  xor     r8d, r8d; bInitialState
0x18007ce3d  xor     edx, edx; bManualReset
0x18007ce3f  xor     ecx, ecx; lpEventAttributes
0x18007ce41  movups  xmmword ptr [rbp+57h+var_90], xmm0
0x18007ce45  call    cs:__imp_CreateEventW
0x18007ce4c  nop     dword ptr [rax+rax+00h]
0x18007ce51  mov     rbx, rax
0x18007ce54  test    rax, rax
0x18007ce57  jnz     short loc_18007CECB
0x18007ce59  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ce60  lea     ebx, [rdi-38h]
0x18007ce63  cmp     rcx, r12
0x18007ce66  jz      loc_18007D151
0x18007ce6c  test    [rcx+1Ch], r15d
0x18007ce70  jz      short loc_18007CEA4
0x18007ce72  cmp     byte ptr [rcx+19h], 2
0x18007ce76  jb      short loc_18007CEA4
0x18007ce78  call    cs:__imp_GetLastError
0x18007ce7f  nop     dword ptr [rax+rax+00h]
0x18007ce84  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ce8b  lea     edx, [rdi+43h]
0x18007ce8e  mov     r9d, eax
0x18007ce91  mov     r8, r13
0x18007ce94  mov     rcx, [rcx+10h]
0x18007ce98  call    WPP_SF_d
0x18007ce9d  mov     rcx, cs:WPP_GLOBAL_Control
0x18007cea4  cmp     rcx, r12
0x18007cea7  jz      loc_18007D151
0x18007cead  test    [rcx+1Ch], r15d
0x18007ceb1  jz      loc_18007D151
0x18007ceb7  cmp     byte ptr [rcx+19h], 6
0x18007cebb  jb      loc_18007D151
0x18007cec1  mov     edx, 84h
0x18007cec6  jmp     loc_18007D142
0x18007cecb  lea     rcx, NatInterfaceLock; lpCriticalSection
0x18007ced2  call    cs:__imp_EnterCriticalSection
0x18007ced9  nop     dword ptr [rax+rax+00h]
0x18007cede  mov     rcx, cs:NatFileHandle; FileHandle
0x18007cee5  lea     rax, [rbp+57h+var_80]
0x18007cee9  mov     [rsp+0E0h+OutputBufferLength], edi; OutputBufferLength
0x18007ceed  xor     r9d, r9d; ApcContext
0x18007cef0  mov     [rsp+0E0h+OutputBuffer], rax; OutputBuffer
0x18007cef5  xor     r8d, r8d; ApcRoutine
0x18007cef8  mov     [rsp+0E0h+InputBufferLength], edi; InputBufferLength
0x18007cefc  lea     rax, [rbp+57h+var_80]
0x18007cf00  mov     [rsp+0E0h+InputBuffer], rax; InputBuffer
0x18007cf05  mov     rdx, rbx; Event
0x18007cf08  lea     rax, [rbp+57h+var_90]
0x18007cf0c  mov     [rsp+0E0h+IoControlCode], 128028h; IoControlCode
0x18007cf14  mov     [rsp+0E0h+IoStatusBlock], rax; IoStatusBlock
0x18007cf19  mov     [rbp+57h+var_6C], 0
0x18007cf20  mov     [rbp+57h+var_7C], 0
0x18007cf27  call    cs:__imp_NtDeviceIoControlFile
0x18007cf2e  nop     dword ptr [rax+rax+00h]
0x18007cf33  mov     edi, eax
0x18007cf35  cmp     eax, 103h
0x18007cf3a  jnz     short loc_18007CF51
0x18007cf3c  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18007cf3f  mov     rcx, rbx; hHandle
0x18007cf42  call    cs:__imp_WaitForSingleObject
0x18007cf49  nop     dword ptr [rax+rax+00h]
0x18007cf4e  mov     edi, dword ptr [rbp+57h+var_90]
0x18007cf51  test    edi, edi
0x18007cf53  jns     loc_18007CFF3
0x18007cf59  lea     rcx, NatInterfaceLock; lpCriticalSection
0x18007cf60  call    cs:__imp_LeaveCriticalSection
0x18007cf67  nop     dword ptr [rax+rax+00h]
0x18007cf6c  mov     rcx, rbx; hObject
0x18007cf6f  call    cs:__imp_CloseHandle
0x18007cf76  nop     dword ptr [rax+rax+00h]
0x18007cf7b  mov     ecx, edi; Status
0x18007cf7d  mov     dword ptr [rsi], 0
0x18007cf83  call    cs:__imp_RtlNtStatusToDosError
0x18007cf8a  nop     dword ptr [rax+rax+00h]
0x18007cf8f  mov     ebx, eax
0x18007cf91  mov     rcx, cs:WPP_GLOBAL_Control
0x18007cf98  cmp     rcx, r12
0x18007cf9b  jz      loc_18007D151
0x18007cfa1  test    [rcx+1Ch], r15d
0x18007cfa5  jz      short loc_18007CFCC
0x18007cfa7  cmp     byte ptr [rcx+19h], 2
0x18007cfab  jb      short loc_18007CFCC
0x18007cfad  mov     rcx, [rcx+10h]
0x18007cfb1  mov     edx, 85h
0x18007cfb6  mov     r9d, edi
0x18007cfb9  mov     dword ptr [rsp+0E0h+IoStatusBlock], eax
0x18007cfbd  mov     r8, r13
0x18007cfc0  call    WPP_SF_Dd
0x18007cfc5  mov     rcx, cs:WPP_GLOBAL_Control
0x18007cfcc  cmp     rcx, r12
0x18007cfcf  jz      loc_18007D151
0x18007cfd5  test    [rcx+1Ch], r15d
0x18007cfd9  jz      loc_18007D151
0x18007cfdf  cmp     byte ptr [rcx+19h], 6
0x18007cfe3  jb      loc_18007D151
0x18007cfe9  mov     edx, 86h
0x18007cfee  jmp     loc_18007D142
0x18007cff3  mov     eax, [rbp+57h+var_68]
0x18007cff6  lea     ecx, [rax+rax*8]
0x18007cff9  mov     eax, [rsi]
0x18007cffb  lea     edi, ds:1Ch[rcx*4]
0x18007d002  cmp     eax, edi
0x18007d004  jnb     short loc_18007D061
0x18007d006  lea     rcx, NatInterfaceLock; lpCriticalSection
0x18007d00d  call    cs:__imp_LeaveCriticalSection
0x18007d014  nop     dword ptr [rax+rax+00h]
0x18007d019  mov     rcx, rbx; hObject
0x18007d01c  call    cs:__imp_CloseHandle
0x18007d023  nop     dword ptr [rax+rax+00h]
0x18007d028  lea     eax, [rdi+0B4h]
0x18007d02e  mov     [rsi], eax
0x18007d030  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d037  mov     ebx, 7Ah ; 'z'
0x18007d03c  cmp     rcx, r12
0x18007d03f  jz      loc_18007D151
0x18007d045  test    [rcx+1Ch], r15d
0x18007d049  jz      loc_18007D151
0x18007d04f  cmp     byte ptr [rcx+19h], 6
0x18007d053  jb      loc_18007D151
0x18007d059  lea     edx, [rbx+0Dh]
0x18007d05c  jmp     loc_18007D142
0x18007d061  mov     rcx, cs:NatFileHandle; FileHandle
0x18007d068  xor     r9d, r9d; ApcContext
0x18007d06b  mov     [rsp+0E0h+OutputBufferLength], eax; OutputBufferLength
0x18007d06f  xor     r8d, r8d; ApcRoutine
0x18007d072  mov     [rsp+0E0h+OutputBuffer], r14; OutputBuffer
0x18007d077  lea     rax, [rbp+57h+var_80]
0x18007d07b  mov     [rsp+0E0h+InputBufferLength], 40h ; '@'; InputBufferLength
0x18007d083  mov     rdx, rbx; Event
0x18007d086  mov     [rsp+0E0h+InputBuffer], rax; InputBuffer
0x18007d08b  lea     rax, [rbp+57h+var_90]
0x18007d08f  mov     [rsp+0E0h+IoControlCode], 128028h; IoControlCode
0x18007d097  mov     [rsp+0E0h+IoStatusBlock], rax; IoStatusBlock
0x18007d09c  mov     [rbp+57h+var_6C], 0
0x18007d0a3  mov     [rbp+57h+var_7C], 0
0x18007d0aa  call    cs:__imp_NtDeviceIoControlFile
0x18007d0b1  nop     dword ptr [rax+rax+00h]
0x18007d0b6  mov     edi, eax
0x18007d0b8  cmp     eax, 103h
0x18007d0bd  jnz     short loc_18007D0D4
0x18007d0bf  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18007d0c2  mov     rcx, rbx; hHandle
0x18007d0c5  call    cs:__imp_WaitForSingleObject
0x18007d0cc  nop     dword ptr [rax+rax+00h]
0x18007d0d1  mov     edi, dword ptr [rbp+57h+var_90]
0x18007d0d4  mov     rcx, rbx; hObject
0x18007d0d7  call    cs:__imp_CloseHandle
0x18007d0de  nop     dword ptr [rax+rax+00h]
0x18007d0e3  lea     rcx, NatInterfaceLock; lpCriticalSection
0x18007d0ea  call    cs:__imp_LeaveCriticalSection
0x18007d0f1  nop     dword ptr [rax+rax+00h]
0x18007d0f6  mov     eax, [r14+14h]
0x18007d0fa  mov     dword ptr [r14], 0FFFFFFFFh
0x18007d101  lea     ecx, [rax+rax*8]
0x18007d104  lea     ecx, ds:1Ch[rcx*4]
0x18007d10b  mov     [rsi], ecx
0x18007d10d  test    edi, edi
0x18007d10f  js      short loc_18007D115
0x18007d111  xor     ebx, ebx
0x18007d113  jmp     short loc_18007D125
0x18007d115  mov     ecx, edi; Status
0x18007d117  call    cs:__imp_RtlNtStatusToDosError
0x18007d11e  nop     dword ptr [rax+rax+00h]
0x18007d123  mov     ebx, eax
0x18007d125  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d12c  cmp     rcx, r12
0x18007d12f  jz      short loc_18007D151
0x18007d131  test    [rcx+1Ch], r15d
0x18007d135  jz      short loc_18007D151
0x18007d137  cmp     byte ptr [rcx+19h], 6
0x18007d13b  jb      short loc_18007D151
0x18007d13d  mov     edx, 88h
0x18007d142  mov     rcx, [rcx+10h]
0x18007d146  mov     r9d, ebx
0x18007d149  mov     r8, r13
0x18007d14c  call    WPP_SF_d
0x18007d151  mov     eax, ebx
0x18007d153  mov     rcx, [rbp+57h+var_40]
0x18007d157  xor     rcx, rsp; StackCookie
0x18007d15a  call    __security_check_cookie
0x18007d15f  mov     rbx, [rsp+0E0h+arg_10]
0x18007d167  add     rsp, 0B0h
0x18007d16e  pop     r15
0x18007d170  pop     r14
0x18007d172  pop     r13
0x18007d174  pop     r12
0x18007d176  pop     rdi
0x18007d177  pop     rsi
0x18007d178  pop     rbp
0x18007d179  retn
```
