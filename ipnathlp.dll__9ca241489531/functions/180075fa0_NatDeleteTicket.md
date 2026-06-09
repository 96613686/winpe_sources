# NatDeleteTicket

- ea: `0x180075fa0`
- end: `0x180076213`
- name: `NatDeleteTicket`
- size: `627`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180074350`
- `0x1800749f8`

## callees

- `0x18000c750`
- `0x18001ec08`
- `0x18004b654`
- `0x18004e0c0`
- `0x180075fa0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800760f2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800760f2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180076142`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180076142`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007604c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007604c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180076156`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180076156`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076080`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076080`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800761b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800761b4`
- `ntdll!NtDeviceIoControlFile` at `0x180076133`
- `ntdll!NtDeviceIoControlFile` at `0x180076133`
- `ntdll!RtlNtStatusToDosError` at `0x18007616e`
- `ntdll!RtlNtStatusToDosError` at `0x18007616e`

## pseudocode

```c
__int64 __fastcall NatDeleteTicket(
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
      95,
      &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids,
      a1,
      a2,
      0,
      a3,
      a6,
      a5);
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
    Status = NtDeviceIoControlFile(NatFileHandle, EventW, 0, 0, &IoStatusBlock, 0x12806Cu, &InputBuffer, 0x14u, 0, 0);
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
          98,
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
      v13 = 99;
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
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 96, &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids, LastError);
        v10 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v10 != &WPP_GLOBAL_Control && (*((_DWORD *)v10 + 7) & 0x200) != 0 && *((_BYTE *)v10 + 25) >= 6u )
      {
        v13 = 97;
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
0x180075fa0  mov     [rsp-38h+arg_18], rbx
0x180075fa5  push    rbp
0x180075fa6  push    rsi
0x180075fa7  push    rdi
0x180075fa8  push    r12
0x180075faa  push    r13
0x180075fac  push    r14
0x180075fae  push    r15
0x180075fb0  mov     rbp, rsp
0x180075fb3  sub     rsp, 80h
0x180075fba  mov     rax, cs:__security_cookie
0x180075fc1  xor     rax, rsp
0x180075fc4  mov     [rbp+var_8], rax
0x180075fc8  movzx   r14d, r8w
0x180075fcc  mov     ebx, ecx
0x180075fce  movzx   edi, dl
0x180075fd1  mov     rcx, cs:WPP_GLOBAL_Control
0x180075fd8  lea     rax, WPP_GLOBAL_Control
0x180075fdf  mov     r15d, [rbp+arg_28]
0x180075fe3  mov     r13d, 200h
0x180075fe9  movzx   r12d, [rbp+arg_20]
0x180075fee  cmp     rcx, rax
0x180075ff1  jz      short loc_180076032
0x180075ff3  test    [rcx+1Ch], r13d
0x180075ff7  jz      short loc_180076032
0x180075ff9  cmp     byte ptr [rcx+19h], 6
0x180075ffd  jb      short loc_180076032
0x180075fff  mov     rcx, [rcx+10h]
0x180076003  lea     r8, WPP_1a1a310d9f3938633825d91885f62d23_Traceguids
0x18007600a  mov     dword ptr [rsp+80h+OutputBuffer], r12d
0x18007600f  mov     edx, 5Fh ; '_'
0x180076014  mov     [rsp+80h+InputBufferLength], r15d
0x180076019  mov     r9d, ebx
0x18007601c  mov     dword ptr [rsp+80h+InputBuffer], r14d
0x180076021  mov     [rsp+80h+IoControlCode], 0
0x180076029  mov     dword ptr [rsp+80h+IoStatusBlock], edi
0x18007602d  call    WPP_SF_dddddd
0x180076032  xorps   xmm0, xmm0
0x180076035  xor     eax, eax
0x180076037  xor     r9d, r9d; lpName
0x18007603a  mov     [rbp+var_10], eax
0x18007603d  xor     r8d, r8d; bInitialState
0x180076040  xor     edx, edx; bManualReset
0x180076042  xor     ecx, ecx; lpEventAttributes
0x180076044  movups  [rbp+var_20], xmm0
0x180076048  movups  xmmword ptr [rbp+var_30], xmm0
0x18007604c  call    cs:__imp_CreateEventW
0x180076052  mov     rsi, rax
0x180076055  test    rax, rax
0x180076058  jnz     short loc_1800760D1
0x18007605a  mov     rcx, cs:WPP_GLOBAL_Control
0x180076061  lea     r14, WPP_GLOBAL_Control
0x180076068  lea     ebx, [rax+8]
0x18007606b  cmp     rcx, r14
0x18007606e  jz      loc_1800761EA
0x180076074  test    [rcx+1Ch], r13d
0x180076078  jz      short loc_1800760AA
0x18007607a  cmp     byte ptr [rcx+19h], 2
0x18007607e  jb      short loc_1800760AA
0x180076080  call    cs:__imp_GetLastError
0x180076086  mov     rcx, cs:WPP_GLOBAL_Control
0x18007608d  lea     edx, [rsi+60h]
0x180076090  mov     r9d, eax
0x180076093  lea     r8, WPP_1a1a310d9f3938633825d91885f62d23_Traceguids
0x18007609a  mov     rcx, [rcx+10h]
0x18007609e  call    WPP_SF_d
0x1800760a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800760aa  cmp     rcx, r14
0x1800760ad  jz      loc_1800761EA
0x1800760b3  test    [rcx+1Ch], r13d
0x1800760b7  jz      loc_1800761EA
0x1800760bd  cmp     byte ptr [rcx+19h], 6
0x1800760c1  jb      loc_1800761EA
0x1800760c7  mov     edx, 61h ; 'a'
0x1800760cc  jmp     loc_1800761D7
0x1800760d1  mov     dword ptr [rbp+var_20], ebx
0x1800760d4  lea     rcx, NatInterfaceLock; lpCriticalSection
0x1800760db  xor     ebx, ebx
0x1800760dd  mov     byte ptr [rbp+var_20+4], dil
0x1800760e1  mov     dword ptr [rbp+var_20+8], ebx
0x1800760e4  mov     word ptr [rbp+var_20+6], r14w
0x1800760e9  mov     word ptr [rbp+var_20+0Ch], r12w
0x1800760ee  mov     [rbp+var_10], r15d
0x1800760f2  call    cs:__imp_EnterCriticalSection
0x1800760f8  mov     rcx, cs:NatFileHandle; FileHandle
0x1800760ff  lea     rax, [rbp+var_20]
0x180076103  mov     [rsp+80h+OutputBufferLength], ebx; OutputBufferLength
0x180076107  xor     r9d, r9d; ApcContext
0x18007610a  mov     [rsp+80h+OutputBuffer], rbx; OutputBuffer
0x18007610f  xor     r8d, r8d; ApcRoutine
0x180076112  mov     [rsp+80h+InputBufferLength], 14h; InputBufferLength
0x18007611a  mov     rdx, rsi; Event
0x18007611d  mov     [rsp+80h+InputBuffer], rax; InputBuffer
0x180076122  lea     rax, [rbp+var_30]
0x180076126  mov     [rsp+80h+IoControlCode], 12806Ch; IoControlCode
0x18007612e  mov     [rsp+80h+IoStatusBlock], rax; IoStatusBlock
0x180076133  call    cs:__imp_NtDeviceIoControlFile
0x180076139  lea     rcx, NatInterfaceLock; lpCriticalSection
0x180076140  mov     edi, eax
0x180076142  call    cs:__imp_LeaveCriticalSection
0x180076148  cmp     edi, 103h
0x18007614e  jnz     short loc_18007615F
0x180076150  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180076153  mov     rcx, rsi; hHandle
0x180076156  call    cs:__imp_WaitForSingleObject
0x18007615c  mov     edi, dword ptr [rbp+var_30]
0x18007615f  test    edi, edi
0x180076161  js      short loc_18007616C
0x180076163  lea     r14, WPP_GLOBAL_Control
0x18007616a  jmp     short loc_1800761B1
0x18007616c  mov     ecx, edi; Status
0x18007616e  call    cs:__imp_RtlNtStatusToDosError
0x180076174  mov     ebx, eax
0x180076176  mov     rcx, cs:WPP_GLOBAL_Control
0x18007617d  lea     r14, WPP_GLOBAL_Control
0x180076184  cmp     rcx, r14
0x180076187  jz      short loc_1800761B1
0x180076189  test    [rcx+1Ch], r13d
0x18007618d  jz      short loc_1800761B1
0x18007618f  cmp     byte ptr [rcx+19h], 2
0x180076193  jb      short loc_1800761B1
0x180076195  mov     rcx, [rcx+10h]
0x180076199  lea     r8, WPP_1a1a310d9f3938633825d91885f62d23_Traceguids
0x1800761a0  mov     edx, 62h ; 'b'
0x1800761a5  mov     dword ptr [rsp+80h+IoStatusBlock], eax
0x1800761a9  mov     r9d, edi
0x1800761ac  call    WPP_SF_Dd
0x1800761b1  mov     rcx, rsi; hObject
0x1800761b4  call    cs:__imp_CloseHandle
0x1800761ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800761c1  cmp     rcx, r14
0x1800761c4  jz      short loc_1800761EA
0x1800761c6  test    [rcx+1Ch], r13d
0x1800761ca  jz      short loc_1800761EA
0x1800761cc  cmp     byte ptr [rcx+19h], 6
0x1800761d0  jb      short loc_1800761EA
0x1800761d2  mov     edx, 63h ; 'c'
0x1800761d7  mov     rcx, [rcx+10h]
0x1800761db  lea     r8, WPP_1a1a310d9f3938633825d91885f62d23_Traceguids
0x1800761e2  mov     r9d, ebx
0x1800761e5  call    WPP_SF_d
0x1800761ea  mov     eax, ebx
0x1800761ec  mov     rcx, [rbp+var_8]
0x1800761f0  xor     rcx, rsp; StackCookie
0x1800761f3  call    __security_check_cookie
0x1800761f8  mov     rbx, [rsp+80h+arg_18]
0x180076200  add     rsp, 80h
0x180076207  pop     r15
0x180076209  pop     r14
0x18007620b  pop     r13
0x18007620d  pop     r12
0x18007620f  pop     rdi
0x180076210  pop     rsi
0x180076211  pop     rbp
0x180076212  retn
```
