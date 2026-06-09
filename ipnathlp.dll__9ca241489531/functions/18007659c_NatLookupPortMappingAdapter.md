# NatLookupPortMappingAdapter

- ea: `0x18007659c`
- end: `0x1800767e2`
- name: `NatLookupPortMappingAdapter`
- size: `582`
- prototype: `__int64 __fastcall(int, int, int, int, PVOID)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180082f30`

## callees

- `0x18000c110`
- `0x18000c750`
- `0x180012730`
- `0x18001ec08`
- `0x180037690`
- `0x18004e0c0`
- `0x18007659c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007662c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007662c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180076726`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180076726`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076658`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076658`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180076787`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180076787`
- `ntdll!NtDeviceIoControlFile` at `0x180076711`
- `ntdll!NtDeviceIoControlFile` at `0x180076711`
- `ntdll!RtlNtStatusToDosError` at `0x180076735`
- `ntdll!RtlNtStatusToDosError` at `0x180076735`

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
0x18007659c  push    rbp
0x18007659e  push    rbx
0x18007659f  push    rsi
0x1800765a0  push    rdi
0x1800765a1  push    r12
0x1800765a3  push    r13
0x1800765a5  push    r14
0x1800765a7  push    r15
0x1800765a9  lea     rbp, [rsp-17h]
0x1800765ae  sub     rsp, 88h
0x1800765b5  mov     rax, cs:__security_cookie
0x1800765bc  xor     rax, rsp
0x1800765bf  mov     [rbp+4Fh+var_48], rax
0x1800765c3  mov     r13, [rbp+4Fh+arg_20]
0x1800765c7  mov     r15d, r8d
0x1800765ca  movzx   r12d, r9w
0x1800765ce  mov     edi, ecx
0x1800765d0  movzx   r14d, dl
0x1800765d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800765db  lea     rax, WPP_GLOBAL_Control
0x1800765e2  mov     ebx, 200h
0x1800765e7  cmp     rcx, rax
0x1800765ea  jz      short loc_180076612
0x1800765ec  test    [rcx+1Ch], ebx
0x1800765ef  jz      short loc_180076612
0x1800765f1  cmp     byte ptr [rcx+19h], 6
0x1800765f5  jb      short loc_180076612
0x1800765f7  mov     rcx, [rcx+10h]
0x1800765fb  mov     r9d, edi
0x1800765fe  mov     dword ptr [rsp+0C0h+InputBuffer], r12d
0x180076603  mov     [rsp+0C0h+IoControlCode], r8d
0x180076608  mov     dword ptr [rsp+0C0h+IoStatusBlock], r14d
0x18007660d  call    WPP_SF_dddd
0x180076612  xorps   xmm0, xmm0
0x180076615  xor     eax, eax
0x180076617  xor     r9d, r9d; lpName
0x18007661a  mov     [rbp+4Fh+var_50], eax
0x18007661d  xor     r8d, r8d; bInitialState
0x180076620  xor     edx, edx; bManualReset
0x180076622  xor     ecx, ecx; lpEventAttributes
0x180076624  movups  [rbp+4Fh+var_60], xmm0
0x180076628  movups  xmmword ptr [rbp+4Fh+var_70], xmm0
0x18007662c  call    cs:__imp_CreateEventW
0x180076632  mov     rsi, rax
0x180076635  test    rax, rax
0x180076638  jnz     short loc_1800766B7
0x18007663a  mov     rcx, cs:WPP_GLOBAL_Control
0x180076641  lea     r14, WPP_GLOBAL_Control
0x180076648  cmp     rcx, r14
0x18007664b  jz      short loc_1800766AD
0x18007664d  test    [rcx+1Ch], ebx
0x180076650  jz      short loc_180076688
0x180076652  cmp     byte ptr [rcx+19h], 2
0x180076656  jb      short loc_180076688
0x180076658  call    cs:__imp_GetLastError
0x18007665e  mov     rcx, cs:WPP_GLOBAL_Control
0x180076665  lea     r8, WPP_1a1a310d9f3938633825d91885f62d23_Traceguids
0x18007666c  mov     edx, 0A0h
0x180076671  mov     dword ptr [rsp+0C0h+IoStatusBlock], edi
0x180076675  mov     r9d, eax
0x180076678  mov     rcx, [rcx+10h]
0x18007667c  call    WPP_SF_dd
0x180076681  mov     rcx, cs:WPP_GLOBAL_Control
0x180076688  cmp     rcx, r14
0x18007668b  jz      short loc_1800766AD
0x18007668d  test    [rcx+1Ch], ebx
0x180076690  jz      short loc_1800766AD
0x180076692  cmp     byte ptr [rcx+19h], 6
0x180076696  jb      short loc_1800766AD
0x180076698  mov     rcx, [rcx+10h]
0x18007669c  lea     r8, WPP_1a1a310d9f3938633825d91885f62d23_Traceguids
0x1800766a3  mov     edx, 0A1h
0x1800766a8  call    WPP_SF_
0x1800766ad  mov     eax, 8
0x1800766b2  jmp     loc_1800767C2
0x1800766b7  mov     rcx, cs:NatFileHandle; FileHandle
0x1800766be  xor     eax, eax
0x1800766c0  mov     [rsp+0C0h+OutputBufferLength], 10h; OutputBufferLength
0x1800766c8  xor     r9d, r9d; ApcContext
0x1800766cb  mov     [rsp+0C0h+OutputBuffer], r13; OutputBuffer
0x1800766d0  xor     r8d, r8d; ApcRoutine
0x1800766d3  mov     word ptr [rbp+4Fh+var_60+0Ch], ax
0x1800766d7  mov     rdx, rsi; Event
0x1800766da  mov     [rbp+4Fh+var_50], eax
0x1800766dd  xor     ebx, ebx
0x1800766df  mov     [rsp+0C0h+InputBufferLength], 14h; InputBufferLength
0x1800766e7  lea     rax, [rbp+4Fh+var_60]
0x1800766eb  mov     [rsp+0C0h+InputBuffer], rax; InputBuffer
0x1800766f0  lea     rax, [rbp+4Fh+var_70]
0x1800766f4  mov     [rsp+0C0h+IoControlCode], 128070h; IoControlCode
0x1800766fc  mov     [rsp+0C0h+IoStatusBlock], rax; IoStatusBlock
0x180076701  mov     dword ptr [rbp+4Fh+var_60], edi
0x180076704  mov     byte ptr [rbp+4Fh+var_60+4], r14b
0x180076708  mov     word ptr [rbp+4Fh+var_60+6], r12w
0x18007670d  mov     dword ptr [rbp+4Fh+var_60+8], r15d
0x180076711  call    cs:__imp_NtDeviceIoControlFile
0x180076717  mov     edi, eax
0x180076719  cmp     eax, 103h
0x18007671e  jnz     short loc_18007672F
0x180076720  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180076723  mov     rcx, rsi; hHandle
0x180076726  call    cs:__imp_WaitForSingleObject
0x18007672c  mov     edi, dword ptr [rbp+4Fh+var_70]
0x18007672f  test    edi, edi
0x180076731  jns     short loc_18007677D
0x180076733  mov     ecx, edi; Status
0x180076735  call    cs:__imp_RtlNtStatusToDosError
0x18007673b  mov     ebx, eax
0x18007673d  mov     rcx, cs:WPP_GLOBAL_Control
0x180076744  lea     r14, WPP_GLOBAL_Control
0x18007674b  cmp     rcx, r14
0x18007674e  jz      short loc_180076784
0x180076750  test    dword ptr [rcx+1Ch], 200h
0x180076757  jz      short loc_180076784
0x180076759  cmp     byte ptr [rcx+19h], 2
0x18007675d  jb      short loc_180076784
0x18007675f  mov     rcx, [rcx+10h]
0x180076763  lea     r8, WPP_1a1a310d9f3938633825d91885f62d23_Traceguids
0x18007676a  mov     edx, 0A2h
0x18007676f  mov     dword ptr [rsp+0C0h+IoStatusBlock], eax
0x180076773  mov     r9d, edi
0x180076776  call    WPP_SF_Dd
0x18007677b  jmp     short loc_180076784
0x18007677d  lea     r14, WPP_GLOBAL_Control
0x180076784  mov     rcx, rsi; hObject
0x180076787  call    cs:__imp_CloseHandle
0x18007678d  mov     rcx, cs:WPP_GLOBAL_Control
0x180076794  cmp     rcx, r14
0x180076797  jz      short loc_1800767C0
0x180076799  test    dword ptr [rcx+1Ch], 200h
0x1800767a0  jz      short loc_1800767C0
0x1800767a2  cmp     byte ptr [rcx+19h], 6
0x1800767a6  jb      short loc_1800767C0
0x1800767a8  mov     rcx, [rcx+10h]
0x1800767ac  lea     r8, WPP_1a1a310d9f3938633825d91885f62d23_Traceguids
0x1800767b3  mov     edx, 0A3h
0x1800767b8  mov     r9d, ebx
0x1800767bb  call    WPP_SF_d
0x1800767c0  mov     eax, ebx
0x1800767c2  mov     rcx, [rbp+4Fh+var_48]
0x1800767c6  xor     rcx, rsp; StackCookie
0x1800767c9  call    __security_check_cookie
0x1800767ce  add     rsp, 88h
0x1800767d5  pop     r15
0x1800767d7  pop     r14
0x1800767d9  pop     r13
0x1800767db  pop     r12
0x1800767dd  pop     rdi
0x1800767de  pop     rsi
0x1800767df  pop     rbx
0x1800767e0  pop     rbp
0x1800767e1  retn
```
