# NatDeleteTicket

- ea: `0x18007bdb8`
- end: `0x18007c05c`
- name: `NatDeleteTicket`
- size: `676`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180079f30`
- `0x18007a608`

## callees

- `0x18000d090`
- `0x1800202e0`
- `0x18004f290`
- `0x180051f30`
- `0x18007bdb8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007bf16`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007bf16`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007bf72`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007bf72`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007be64`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007be64`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007bf8c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007bf8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007be9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007be9e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007bff6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007bff6`
- `ntdll!NtDeviceIoControlFile` at `0x18007bf5d`
- `ntdll!NtDeviceIoControlFile` at `0x18007bf5d`
- `ntdll!RtlNtStatusToDosError` at `0x18007bfaa`
- `ntdll!RtlNtStatusToDosError` at `0x18007bfaa`

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
0x18007bdb8  mov     [rsp-38h+arg_18], rbx
0x18007bdbd  push    rbp
0x18007bdbe  push    rsi
0x18007bdbf  push    rdi
0x18007bdc0  push    r12
0x18007bdc2  push    r13
0x18007bdc4  push    r14
0x18007bdc6  push    r15
0x18007bdc8  mov     rbp, rsp
0x18007bdcb  sub     rsp, 80h
0x18007bdd2  mov     rax, cs:__security_cookie
0x18007bdd9  xor     rax, rsp
0x18007bddc  mov     [rbp+var_8], rax
0x18007bde0  movzx   r14d, r8w
0x18007bde4  mov     ebx, ecx
0x18007bde6  movzx   edi, dl
0x18007bde9  mov     rcx, cs:WPP_GLOBAL_Control
0x18007bdf0  lea     rax, WPP_GLOBAL_Control
0x18007bdf7  mov     r15d, [rbp+arg_28]
0x18007bdfb  mov     r13d, 200h
0x18007be01  movzx   r12d, [rbp+arg_20]
0x18007be06  cmp     rcx, rax
0x18007be09  jz      short loc_18007BE4A
0x18007be0b  test    [rcx+1Ch], r13d
0x18007be0f  jz      short loc_18007BE4A
0x18007be11  cmp     byte ptr [rcx+19h], 6
0x18007be15  jb      short loc_18007BE4A
0x18007be17  mov     rcx, [rcx+10h]
0x18007be1b  lea     r8, WPP_1a1a310d9f3938633825d91885f62d23_Traceguids
0x18007be22  mov     dword ptr [rsp+80h+OutputBuffer], r12d
0x18007be27  mov     edx, 5Fh ; '_'
0x18007be2c  mov     [rsp+80h+InputBufferLength], r15d
0x18007be31  mov     r9d, ebx
0x18007be34  mov     dword ptr [rsp+80h+InputBuffer], r14d
0x18007be39  mov     [rsp+80h+IoControlCode], 0
0x18007be41  mov     dword ptr [rsp+80h+IoStatusBlock], edi
0x18007be45  call    WPP_SF_dddddd
0x18007be4a  xorps   xmm0, xmm0
0x18007be4d  xor     eax, eax
0x18007be4f  xor     r9d, r9d; lpName
0x18007be52  mov     [rbp+var_10], eax
0x18007be55  xor     r8d, r8d; bInitialState
0x18007be58  xor     edx, edx; bManualReset
0x18007be5a  xor     ecx, ecx; lpEventAttributes
0x18007be5c  movups  [rbp+var_20], xmm0
0x18007be60  movups  xmmword ptr [rbp+var_30], xmm0
0x18007be64  call    cs:__imp_CreateEventW
0x18007be6b  nop     dword ptr [rax+rax+00h]
0x18007be70  mov     rsi, rax
0x18007be73  test    rax, rax
0x18007be76  jnz     short loc_18007BEF5
0x18007be78  mov     rcx, cs:WPP_GLOBAL_Control
0x18007be7f  lea     r14, WPP_GLOBAL_Control
0x18007be86  lea     ebx, [rax+8]
0x18007be89  cmp     rcx, r14
0x18007be8c  jz      loc_18007C032
0x18007be92  test    [rcx+1Ch], r13d
0x18007be96  jz      short loc_18007BECE
0x18007be98  cmp     byte ptr [rcx+19h], 2
0x18007be9c  jb      short loc_18007BECE
0x18007be9e  call    cs:__imp_GetLastError
0x18007bea5  nop     dword ptr [rax+rax+00h]
0x18007beaa  mov     rcx, cs:WPP_GLOBAL_Control
0x18007beb1  lea     edx, [rsi+60h]
0x18007beb4  mov     r9d, eax
0x18007beb7  lea     r8, WPP_1a1a310d9f3938633825d91885f62d23_Traceguids
0x18007bebe  mov     rcx, [rcx+10h]
0x18007bec2  call    WPP_SF_d
0x18007bec7  mov     rcx, cs:WPP_GLOBAL_Control
0x18007bece  cmp     rcx, r14
0x18007bed1  jz      loc_18007C032
0x18007bed7  test    [rcx+1Ch], r13d
0x18007bedb  jz      loc_18007C032
0x18007bee1  cmp     byte ptr [rcx+19h], 6
0x18007bee5  jb      loc_18007C032
0x18007beeb  mov     edx, 61h ; 'a'
0x18007bef0  jmp     loc_18007C01F
0x18007bef5  mov     dword ptr [rbp+var_20], ebx
0x18007bef8  lea     rcx, NatInterfaceLock; lpCriticalSection
0x18007beff  xor     ebx, ebx
0x18007bf01  mov     byte ptr [rbp+var_20+4], dil
0x18007bf05  mov     dword ptr [rbp+var_20+8], ebx
0x18007bf08  mov     word ptr [rbp+var_20+6], r14w
0x18007bf0d  mov     word ptr [rbp+var_20+0Ch], r12w
0x18007bf12  mov     [rbp+var_10], r15d
0x18007bf16  call    cs:__imp_EnterCriticalSection
0x18007bf1d  nop     dword ptr [rax+rax+00h]
0x18007bf22  mov     rcx, cs:NatFileHandle; FileHandle
0x18007bf29  lea     rax, [rbp+var_20]
0x18007bf2d  mov     [rsp+80h+OutputBufferLength], ebx; OutputBufferLength
0x18007bf31  xor     r9d, r9d; ApcContext
0x18007bf34  mov     [rsp+80h+OutputBuffer], rbx; OutputBuffer
0x18007bf39  xor     r8d, r8d; ApcRoutine
0x18007bf3c  mov     [rsp+80h+InputBufferLength], 14h; InputBufferLength
0x18007bf44  mov     rdx, rsi; Event
0x18007bf47  mov     [rsp+80h+InputBuffer], rax; InputBuffer
0x18007bf4c  lea     rax, [rbp+var_30]
0x18007bf50  mov     [rsp+80h+IoControlCode], 12806Ch; IoControlCode
0x18007bf58  mov     [rsp+80h+IoStatusBlock], rax; IoStatusBlock
0x18007bf5d  call    cs:__imp_NtDeviceIoControlFile
0x18007bf64  nop     dword ptr [rax+rax+00h]
0x18007bf69  lea     rcx, NatInterfaceLock; lpCriticalSection
0x18007bf70  mov     edi, eax
0x18007bf72  call    cs:__imp_LeaveCriticalSection
0x18007bf79  nop     dword ptr [rax+rax+00h]
0x18007bf7e  cmp     edi, 103h
0x18007bf84  jnz     short loc_18007BF9B
0x18007bf86  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18007bf89  mov     rcx, rsi; hHandle
0x18007bf8c  call    cs:__imp_WaitForSingleObject
0x18007bf93  nop     dword ptr [rax+rax+00h]
0x18007bf98  mov     edi, dword ptr [rbp+var_30]
0x18007bf9b  test    edi, edi
0x18007bf9d  js      short loc_18007BFA8
0x18007bf9f  lea     r14, WPP_GLOBAL_Control
0x18007bfa6  jmp     short loc_18007BFF3
0x18007bfa8  mov     ecx, edi; Status
0x18007bfaa  call    cs:__imp_RtlNtStatusToDosError
0x18007bfb1  nop     dword ptr [rax+rax+00h]
0x18007bfb6  mov     ebx, eax
0x18007bfb8  mov     rcx, cs:WPP_GLOBAL_Control
0x18007bfbf  lea     r14, WPP_GLOBAL_Control
0x18007bfc6  cmp     rcx, r14
0x18007bfc9  jz      short loc_18007BFF3
0x18007bfcb  test    [rcx+1Ch], r13d
0x18007bfcf  jz      short loc_18007BFF3
0x18007bfd1  cmp     byte ptr [rcx+19h], 2
0x18007bfd5  jb      short loc_18007BFF3
0x18007bfd7  mov     rcx, [rcx+10h]
0x18007bfdb  lea     r8, WPP_1a1a310d9f3938633825d91885f62d23_Traceguids
0x18007bfe2  mov     edx, 62h ; 'b'
0x18007bfe7  mov     dword ptr [rsp+80h+IoStatusBlock], eax
0x18007bfeb  mov     r9d, edi
0x18007bfee  call    WPP_SF_Dd
0x18007bff3  mov     rcx, rsi; hObject
0x18007bff6  call    cs:__imp_CloseHandle
0x18007bffd  nop     dword ptr [rax+rax+00h]
0x18007c002  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c009  cmp     rcx, r14
0x18007c00c  jz      short loc_18007C032
0x18007c00e  test    [rcx+1Ch], r13d
0x18007c012  jz      short loc_18007C032
0x18007c014  cmp     byte ptr [rcx+19h], 6
0x18007c018  jb      short loc_18007C032
0x18007c01a  mov     edx, 63h ; 'c'
0x18007c01f  mov     rcx, [rcx+10h]
0x18007c023  lea     r8, WPP_1a1a310d9f3938633825d91885f62d23_Traceguids
0x18007c02a  mov     r9d, ebx
0x18007c02d  call    WPP_SF_d
0x18007c032  mov     eax, ebx
0x18007c034  mov     rcx, [rbp+var_8]
0x18007c038  xor     rcx, rsp; StackCookie
0x18007c03b  call    __security_check_cookie
0x18007c040  mov     rbx, [rsp+80h+arg_18]
0x18007c048  add     rsp, 80h
0x18007c04f  pop     r15
0x18007c051  pop     r14
0x18007c053  pop     r13
0x18007c055  pop     r12
0x18007c057  pop     rdi
0x18007c058  pop     rsi
0x18007c059  pop     rbp
0x18007c05a  retn
```
