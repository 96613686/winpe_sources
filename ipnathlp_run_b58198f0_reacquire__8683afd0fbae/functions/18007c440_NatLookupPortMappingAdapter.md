# NatLookupPortMappingAdapter

- ea: `0x18007c440`
- end: `0x18007c6af`
- name: `NatLookupPortMappingAdapter`
- size: `623`
- prototype: `__int64 __fastcall(int, int, int, int, PVOID)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1800896d0`

## callees

- `0x18000ca20`
- `0x18000d090`
- `0x180013650`
- `0x1800202e0`
- `0x18003931c`
- `0x180051f30`
- `0x18007c440`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007c4d0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007c4d0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007c5e0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007c5e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c506`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c506`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007c64d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007c64d`
- `ntdll!NtDeviceIoControlFile` at `0x18007c5c5`
- `ntdll!NtDeviceIoControlFile` at `0x18007c5c5`
- `ntdll!RtlNtStatusToDosError` at `0x18007c5f5`
- `ntdll!RtlNtStatusToDosError` at `0x18007c5f5`

## pseudocode

```c
__int64 __fastcall NatLookupPortMappingAdapter(
        unsigned int a1,
        __int64 a2,
        __int64 a3,
        unsigned __int16 a4,
        PVOID OutputBuffer)
{
  int v5; // r15d
  char v8; // r14
  HANDLE EventW; // rax
  void *v10; // rsi
  PVOID *v11; // rcx
  DWORD LastError; // eax
  ULONG v14; // ebx
  int Status; // edi
  ULONG v16; // eax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-21h] BYREF
  __int128 InputBuffer; // [rsp+60h] [rbp-11h] BYREF
  int v19; // [rsp+70h] [rbp-1h]

  v5 = a3;
  v8 = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_dddd(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, a1, (unsigned __int8)a2, a3, a4);
  }
  v19 = 0;
  InputBuffer = 0;
  IoStatusBlock = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  v10 = EventW;
  if ( EventW )
  {
    WORD6(InputBuffer) = 0;
    v19 = 0;
    v14 = 0;
    LODWORD(InputBuffer) = a1;
    BYTE4(InputBuffer) = v8;
    WORD3(InputBuffer) = a4;
    DWORD2(InputBuffer) = v5;
    Status = NtDeviceIoControlFile(
               NatFileHandle,
               EventW,
               0,
               0,
               &IoStatusBlock,
               0x128070u,
               &InputBuffer,
               0x14u,
               OutputBuffer,
               0x10u);
    if ( Status == 259 )
    {
      WaitForSingleObject(v10, 0xFFFFFFFF);
      Status = IoStatusBlock.Status;
    }
    if ( Status < 0 )
    {
      v16 = RtlNtStatusToDosError(Status);
      v14 = v16;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          162,
          &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids,
          (unsigned int)Status,
          v16);
      }
    }
    CloseHandle(v10);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 163, &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids, v14);
    }
    return v14;
  }
  else
  {
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        WPP_SF_dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          160,
          &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids,
          LastError,
          a1);
        v11 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v11 != &WPP_GLOBAL_Control && (*((_DWORD *)v11 + 7) & 0x200) != 0 && *((_BYTE *)v11 + 25) >= 6u )
        WPP_SF_(v11[2], 161, &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids);
    }
    return 8;
  }
}

```

## disassembly

```asm
0x18007c440  push    rbp
0x18007c442  push    rbx
0x18007c443  push    rsi
0x18007c444  push    rdi
0x18007c445  push    r12
0x18007c447  push    r13
0x18007c449  push    r14
0x18007c44b  push    r15
0x18007c44d  lea     rbp, [rsp-17h]
0x18007c452  sub     rsp, 88h
0x18007c459  mov     rax, cs:__security_cookie
0x18007c460  xor     rax, rsp
0x18007c463  mov     [rbp+4Fh+var_48], rax
0x18007c467  mov     r13, [rbp+4Fh+arg_20]
0x18007c46b  mov     r15d, r8d
0x18007c46e  movzx   r12d, r9w
0x18007c472  mov     edi, ecx
0x18007c474  movzx   r14d, dl
0x18007c478  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c47f  lea     rax, WPP_GLOBAL_Control
0x18007c486  mov     ebx, 200h
0x18007c48b  cmp     rcx, rax
0x18007c48e  jz      short loc_18007C4B6
0x18007c490  test    [rcx+1Ch], ebx
0x18007c493  jz      short loc_18007C4B6
0x18007c495  cmp     byte ptr [rcx+19h], 6
0x18007c499  jb      short loc_18007C4B6
0x18007c49b  mov     rcx, [rcx+10h]
0x18007c49f  mov     r9d, edi
0x18007c4a2  mov     dword ptr [rsp+0C0h+InputBuffer], r12d
0x18007c4a7  mov     [rsp+0C0h+IoControlCode], r8d
0x18007c4ac  mov     dword ptr [rsp+0C0h+IoStatusBlock], r14d
0x18007c4b1  call    WPP_SF_dddd
0x18007c4b6  xorps   xmm0, xmm0
0x18007c4b9  xor     eax, eax
0x18007c4bb  xor     r9d, r9d; lpName
0x18007c4be  mov     [rbp+4Fh+var_50], eax
0x18007c4c1  xor     r8d, r8d; bInitialState
0x18007c4c4  xor     edx, edx; bManualReset
0x18007c4c6  xor     ecx, ecx; lpEventAttributes
0x18007c4c8  movups  [rbp+4Fh+var_60], xmm0
0x18007c4cc  movups  xmmword ptr [rbp+4Fh+var_70], xmm0
0x18007c4d0  call    cs:__imp_CreateEventW
0x18007c4d7  nop     dword ptr [rax+rax+00h]
0x18007c4dc  mov     rsi, rax
0x18007c4df  test    rax, rax
0x18007c4e2  jnz     loc_18007C56B
0x18007c4e8  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c4ef  lea     r14, WPP_GLOBAL_Control
0x18007c4f6  cmp     rcx, r14
0x18007c4f9  jz      short loc_18007C561
0x18007c4fb  test    [rcx+1Ch], ebx
0x18007c4fe  jz      short loc_18007C53C
0x18007c500  cmp     byte ptr [rcx+19h], 2
0x18007c504  jb      short loc_18007C53C
0x18007c506  call    cs:__imp_GetLastError
0x18007c50d  nop     dword ptr [rax+rax+00h]
0x18007c512  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c519  lea     r8, WPP_1a1a310d9f3938633825d91885f62d23_Traceguids
0x18007c520  mov     edx, 0A0h
0x18007c525  mov     dword ptr [rsp+0C0h+IoStatusBlock], edi
0x18007c529  mov     r9d, eax
0x18007c52c  mov     rcx, [rcx+10h]
0x18007c530  call    WPP_SF_dd
0x18007c535  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c53c  cmp     rcx, r14
0x18007c53f  jz      short loc_18007C561
0x18007c541  test    [rcx+1Ch], ebx
0x18007c544  jz      short loc_18007C561
0x18007c546  cmp     byte ptr [rcx+19h], 6
0x18007c54a  jb      short loc_18007C561
0x18007c54c  mov     rcx, [rcx+10h]
0x18007c550  lea     r8, WPP_1a1a310d9f3938633825d91885f62d23_Traceguids
0x18007c557  mov     edx, 0A1h
0x18007c55c  call    WPP_SF_
0x18007c561  mov     eax, 8
0x18007c566  jmp     loc_18007C68E
0x18007c56b  mov     rcx, cs:NatFileHandle; FileHandle
0x18007c572  xor     eax, eax
0x18007c574  mov     [rsp+0C0h+OutputBufferLength], 10h; OutputBufferLength
0x18007c57c  xor     r9d, r9d; ApcContext
0x18007c57f  mov     [rsp+0C0h+OutputBuffer], r13; OutputBuffer
0x18007c584  xor     r8d, r8d; ApcRoutine
0x18007c587  mov     word ptr [rbp+4Fh+var_60+0Ch], ax
0x18007c58b  mov     rdx, rsi; Event
0x18007c58e  mov     [rbp+4Fh+var_50], eax
0x18007c591  xor     ebx, ebx
0x18007c593  mov     [rsp+0C0h+InputBufferLength], 14h; InputBufferLength
0x18007c59b  lea     rax, [rbp+4Fh+var_60]
0x18007c59f  mov     [rsp+0C0h+InputBuffer], rax; InputBuffer
0x18007c5a4  lea     rax, [rbp+4Fh+var_70]
0x18007c5a8  mov     [rsp+0C0h+IoControlCode], 128070h; IoControlCode
0x18007c5b0  mov     [rsp+0C0h+IoStatusBlock], rax; IoStatusBlock
0x18007c5b5  mov     dword ptr [rbp+4Fh+var_60], edi
0x18007c5b8  mov     byte ptr [rbp+4Fh+var_60+4], r14b
0x18007c5bc  mov     word ptr [rbp+4Fh+var_60+6], r12w
0x18007c5c1  mov     dword ptr [rbp+4Fh+var_60+8], r15d
0x18007c5c5  call    cs:__imp_NtDeviceIoControlFile
0x18007c5cc  nop     dword ptr [rax+rax+00h]
0x18007c5d1  mov     edi, eax
0x18007c5d3  cmp     eax, 103h
0x18007c5d8  jnz     short loc_18007C5EF
0x18007c5da  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18007c5dd  mov     rcx, rsi; hHandle
0x18007c5e0  call    cs:__imp_WaitForSingleObject
0x18007c5e7  nop     dword ptr [rax+rax+00h]
0x18007c5ec  mov     edi, dword ptr [rbp+4Fh+var_70]
0x18007c5ef  test    edi, edi
0x18007c5f1  jns     short loc_18007C643
0x18007c5f3  mov     ecx, edi; Status
0x18007c5f5  call    cs:__imp_RtlNtStatusToDosError
0x18007c5fc  nop     dword ptr [rax+rax+00h]
0x18007c601  mov     ebx, eax
0x18007c603  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c60a  lea     r14, WPP_GLOBAL_Control
0x18007c611  cmp     rcx, r14
0x18007c614  jz      short loc_18007C64A
0x18007c616  test    dword ptr [rcx+1Ch], 200h
0x18007c61d  jz      short loc_18007C64A
0x18007c61f  cmp     byte ptr [rcx+19h], 2
0x18007c623  jb      short loc_18007C64A
0x18007c625  mov     rcx, [rcx+10h]
0x18007c629  lea     r8, WPP_1a1a310d9f3938633825d91885f62d23_Traceguids
0x18007c630  mov     edx, 0A2h
0x18007c635  mov     dword ptr [rsp+0C0h+IoStatusBlock], eax
0x18007c639  mov     r9d, edi
0x18007c63c  call    WPP_SF_Dd
0x18007c641  jmp     short loc_18007C64A
0x18007c643  lea     r14, WPP_GLOBAL_Control
0x18007c64a  mov     rcx, rsi; hObject
0x18007c64d  call    cs:__imp_CloseHandle
0x18007c654  nop     dword ptr [rax+rax+00h]
0x18007c659  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c660  cmp     rcx, r14
0x18007c663  jz      short loc_18007C68C
0x18007c665  test    dword ptr [rcx+1Ch], 200h
0x18007c66c  jz      short loc_18007C68C
0x18007c66e  cmp     byte ptr [rcx+19h], 6
0x18007c672  jb      short loc_18007C68C
0x18007c674  mov     rcx, [rcx+10h]
0x18007c678  lea     r8, WPP_1a1a310d9f3938633825d91885f62d23_Traceguids
0x18007c67f  mov     edx, 0A3h
0x18007c684  mov     r9d, ebx
0x18007c687  call    WPP_SF_d
0x18007c68c  mov     eax, ebx
0x18007c68e  mov     rcx, [rbp+4Fh+var_48]
0x18007c692  xor     rcx, rsp; StackCookie
0x18007c695  call    __security_check_cookie
0x18007c69a  add     rsp, 88h
0x18007c6a1  pop     r15
0x18007c6a3  pop     r14
0x18007c6a5  pop     r13
0x18007c6a7  pop     r12
0x18007c6a9  pop     rdi
0x18007c6aa  pop     rsi
0x18007c6ab  pop     rbx
0x18007c6ac  pop     rbp
0x18007c6ad  retn
```
