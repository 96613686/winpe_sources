# DfdATA::ReadSMARTLog(_SENDCMDOUTPARAMS *,ulong,uchar)

- ea: `0x180007f08`
- end: `0x1800080c0`
- name: `?ReadSMARTLog@DfdATA@@AEAAKPEAU_SENDCMDOUTPARAMS@@KE@Z`
- size: `440`
- prototype: `__int64 __fastcall(void **this, struct _SENDCMDOUTPARAMS *, DWORD, char)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180007c6c`

## callees

- `0x180002c90`
- `0x180002d64`
- `0x180005178`
- `0x180007f08`
- `0x180008178`

## import_xrefs

- `KERNEL32!DeviceIoControl` at `0x180008010`
- `KERNEL32!DeviceIoControl` at `0x180008010`
- `KERNEL32!HeapAlloc` at `0x180007f3a`
- `KERNEL32!HeapAlloc` at `0x180007f3a`
- `KERNEL32!GetProcessHeap` at `0x180007f28`
- `KERNEL32!GetProcessHeap` at `0x180008097`
- `KERNEL32!GetProcessHeap` at `0x180007f28`
- `KERNEL32!GetProcessHeap` at `0x180008097`
- `KERNEL32!HeapFree` at `0x1800080a5`
- `KERNEL32!HeapFree` at `0x1800080a5`
- `KERNEL32!GetLastError` at `0x18000801a`
- `KERNEL32!GetLastError` at `0x18000801a`

## pseudocode

```c
__int64 __fastcall DfdATA::ReadSMARTLog(void **this, struct _SENDCMDOUTPARAMS *a2, DWORD a3, char a4)
{
  HANDLE ProcessHeap; // rax
  _WORD *v8; // rax
  _WORD *v9; // rsi
  unsigned int v10; // ebx
  void *v11; // rcx
  __int64 v12; // r8
  DWORD LastError; // eax
  HANDLE v14; // rax
  DWORD BytesReturned; // [rsp+70h] [rbp+18h] BYREF

  BytesReturned = a3;
  ProcessHeap = GetProcessHeap();
  v8 = HeapAlloc(ProcessHeap, 8u, 0x21u);
  v9 = v8;
  if ( v8 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_47546f163ca83b4871ae2173b5583170_Traceguids, v8, 33);
    *(_DWORD *)v9 = 32;
    v9[2] = 469;
    *((_BYTE *)v9 + 6) = a4;
    *(_WORD *)((char *)v9 + 7) = -15793;
    *((_BYTE *)v9 + 10) = -80;
    v11 = *this;
    BytesReturned = 0;
    if ( DeviceIoControl(v11, 0x7C088u, v9, 0x20u, a2, 0x221u, &BytesReturned, 0) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_LLL(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          a2->DriverStatus.bDriverError,
          v12,
          a2->cBufferSize,
          a2->DriverStatus.bDriverError,
          a2->DriverStatus.bIDEError);
      v10 = a2->DriverStatus.bDriverError || a2->DriverStatus.bIDEError;
    }
    else
    {
      LastError = GetLastError();
      v10 = LastError;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_DD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          21,
          &WPP_47546f163ca83b4871ae2173b5583170_Traceguids,
          BytesReturned,
          LastError);
    }
    v14 = GetProcessHeap();
    HeapFree(v14, 0, v9);
  }
  else
  {
    v10 = 14;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_47546f163ca83b4871ae2173b5583170_Traceguids, 14);
  }
  return v10;
}

```

## disassembly

```asm
0x180007f08  mov     [rsp+arg_0], rbx
0x180007f0d  mov     [rsp+arg_8], rbp
0x180007f12  mov     [rsp+BytesReturned], r8d
0x180007f17  push    rsi
0x180007f18  push    rdi
0x180007f19  push    r14
0x180007f1b  sub     rsp, 40h
0x180007f1f  mov     bpl, r9b
0x180007f22  mov     rbx, rdx
0x180007f25  mov     r14, rcx
0x180007f28  call    cs:__imp_GetProcessHeap
0x180007f2e  mov     edx, 8; dwFlags
0x180007f33  mov     rcx, rax; hHeap
0x180007f36  lea     r8d, [rdx+19h]; dwBytes
0x180007f3a  call    cs:__imp_HeapAlloc
0x180007f40  mov     rsi, rax
0x180007f43  test    rax, rax
0x180007f46  jnz     short loc_180007F87
0x180007f48  lea     ebx, [rax+0Eh]
0x180007f4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180007f52  lea     rdi, WPP_GLOBAL_Control
0x180007f59  cmp     rcx, rdi
0x180007f5c  jz      loc_1800080AB
0x180007f62  test    byte ptr [rcx+1Ch], 1
0x180007f66  jz      loc_1800080AB
0x180007f6c  mov     rcx, [rcx+10h]
0x180007f70  lea     edx, [rax+13h]
0x180007f73  mov     r9d, ebx
0x180007f76  lea     r8, WPP_47546f163ca83b4871ae2173b5583170_Traceguids
0x180007f7d  call    WPP_SF_d
0x180007f82  jmp     loc_1800080AB
0x180007f87  mov     rcx, cs:WPP_GLOBAL_Control
0x180007f8e  lea     rdi, WPP_GLOBAL_Control
0x180007f95  cmp     rcx, rdi
0x180007f98  jz      short loc_180007FC0
0x180007f9a  test    byte ptr [rcx+1Ch], 4
0x180007f9e  jz      short loc_180007FC0
0x180007fa0  mov     rcx, [rcx+10h]
0x180007fa4  lea     r8, WPP_47546f163ca83b4871ae2173b5583170_Traceguids
0x180007fab  mov     edx, 14h
0x180007fb0  mov     dword ptr [rsp+58h+lpOutBuffer], 21h ; '!'
0x180007fb8  mov     r9, rsi
0x180007fbb  call    WPP_SF_qD
0x180007fc0  mov     [rsp+58h+lpOverlapped], 0; lpOverlapped
0x180007fc9  lea     rax, [rsp+58h+BytesReturned]
0x180007fce  mov     [rsp+58h+lpBytesReturned], rax; lpBytesReturned
0x180007fd3  mov     r9d, 20h ; ' '; nInBufferSize
0x180007fd9  mov     [rsi], r9d
0x180007fdc  mov     r8, rsi; lpInBuffer
0x180007fdf  mov     word ptr [rsi+4], 1D5h
0x180007fe5  mov     edx, 7C088h; dwIoControlCode
0x180007fea  mov     [rsi+6], bpl
0x180007fee  mov     word ptr [rsi+7], 0C24Fh
0x180007ff4  mov     byte ptr [rsi+0Ah], 0B0h
0x180007ff8  mov     rcx, [r14]; hDevice
0x180007ffb  mov     [rsp+58h+nOutBufferSize], 221h; nOutBufferSize
0x180008003  mov     [rsp+58h+lpOutBuffer], rbx; lpOutBuffer
0x180008008  mov     [rsp+58h+BytesReturned], 0
0x180008010  call    cs:__imp_DeviceIoControl
0x180008016  test    eax, eax
0x180008018  jnz     short loc_180008054
0x18000801a  call    cs:__imp_GetLastError
0x180008020  mov     ebx, eax
0x180008022  mov     rcx, cs:WPP_GLOBAL_Control
0x180008029  cmp     rcx, rdi
0x18000802c  jz      short loc_180008097
0x18000802e  test    byte ptr [rcx+1Ch], 1
0x180008032  jz      short loc_180008097
0x180008034  mov     r9d, [rsp+58h+BytesReturned]
0x180008039  lea     r8, WPP_47546f163ca83b4871ae2173b5583170_Traceguids
0x180008040  mov     rcx, [rcx+10h]
0x180008044  mov     edx, 15h
0x180008049  mov     dword ptr [rsp+58h+lpOutBuffer], eax
0x18000804d  call    WPP_SF_DD
0x180008052  jmp     short loc_180008097
0x180008054  mov     rcx, cs:WPP_GLOBAL_Control
0x18000805b  cmp     rcx, rdi
0x18000805e  jz      short loc_180008082
0x180008060  test    byte ptr [rcx+1Ch], 4
0x180008064  jz      short loc_180008082
0x180008066  movzx   eax, byte ptr [rbx+5]
0x18000806a  movzx   edx, byte ptr [rbx+4]
0x18000806e  mov     r9d, [rbx]
0x180008071  mov     rcx, [rcx+10h]
0x180008075  mov     [rsp+58h+nOutBufferSize], eax
0x180008079  mov     dword ptr [rsp+58h+lpOutBuffer], edx
0x18000807d  call    WPP_SF_LLL
0x180008082  cmp     byte ptr [rbx+4], 0
0x180008086  jnz     short loc_180008092
0x180008088  cmp     byte ptr [rbx+5], 0
0x18000808c  jnz     short loc_180008092
0x18000808e  xor     ebx, ebx
0x180008090  jmp     short loc_180008097
0x180008092  mov     ebx, 1
0x180008097  call    cs:__imp_GetProcessHeap
0x18000809d  mov     r8, rsi; lpMem
0x1800080a0  xor     edx, edx; dwFlags
0x1800080a2  mov     rcx, rax; hHeap
0x1800080a5  call    cs:__imp_HeapFree
0x1800080ab  mov     rbp, [rsp+58h+arg_8]
0x1800080b0  mov     eax, ebx
0x1800080b2  mov     rbx, [rsp+58h+arg_0]
0x1800080b7  add     rsp, 40h
0x1800080bb  pop     r14
0x1800080bd  pop     rdi
0x1800080be  pop     rsi
0x1800080bf  retn
```
