# PrjfRemoveSparse

- ea: `0x14002b3c0`
- end: `0x14002b4e5`
- name: `PrjfRemoveSparse`
- size: `293`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14002a260`

## callees

- `0x14000b1d0`
- `0x14000d754`
- `0x14002b3c0`

## import_xrefs

- `FLTMGR!FltFsControlFile` at `0x14002b43b`
- `FLTMGR!FltFsControlFile` at `0x14002b43b`

## pseudocode

```c
__int64 __fastcall PrjfRemoveSparse(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject, __int64 a3, __int64 a4)
{
  bool v4; // zf
  int v9; // edx
  NTSTATUS v10; // edi
  int v11; // r8d
  char InputBuffer; // [rsp+80h] [rbp+18h] BYREF

  v4 = *(_DWORD *)a3 == 1;
  InputBuffer = 0;
  if ( v4 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(Instance, FileObject, a3, a4);
  if ( (**(_DWORD **)(*(_QWORD *)(a3 + 8) + 88LL) & 1) != 0 )
    return 0;
  InputBuffer = 0;
  v10 = FltFsControlFile(Instance, FileObject, 0x900C4u, &InputBuffer, 1u, 0, 0, 0);
  if ( v10 >= 0 )
  {
    **(_DWORD **)(*(_QWORD *)(a3 + 8) + 88LL) |= 1u;
  }
  else if ( (BYTE1(xmmword_14001A3E0) & 4) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v9) = BYTE1(xmmword_14001A3E0) & 4;
    LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sDdZ(
      1034,
      v9,
      v11,
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      4,
      10,
      12,
      (__int64)&WPP_f6f932a41f663696b98ce9faa74178e4_Traceguids,
      (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\expansion.c",
      191,
      v10,
      (__int64)&FileObject->FileName);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14002b3c0  mov     rax, rsp
0x14002b3c3  mov     [rax+8], rbx
0x14002b3c7  mov     [rax+10h], rsi
0x14002b3cb  push    rdi
0x14002b3cc  sub     rsp, 60h
0x14002b3d0  cmp     dword ptr [r8], 1
0x14002b3d4  mov     rbx, r8
0x14002b3d7  mov     rsi, rdx
0x14002b3da  mov     byte ptr [rax+18h], 0
0x14002b3de  mov     rdi, rcx
0x14002b3e1  jnz     short loc_14002B3E8
0x14002b3e3  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14002b3e8  mov     rax, [rbx+8]
0x14002b3ec  mov     rdx, [rax+58h]
0x14002b3f0  mov     eax, [rdx]
0x14002b3f2  test    al, 1
0x14002b3f4  jz      short loc_14002B3FD
0x14002b3f6  xor     eax, eax
0x14002b3f8  jmp     loc_14002B4D4
0x14002b3fd  mov     [rsp+68h+LengthReturned], 0; LengthReturned
0x14002b406  lea     r9, [rsp+68h+InputBuffer]; InputBuffer
0x14002b40e  mov     [rsp+68h+OutputBufferLength], 0; OutputBufferLength
0x14002b416  mov     r8d, 900C4h; FsControlCode
0x14002b41c  mov     [rsp+68h+OutputBuffer], 0; OutputBuffer
0x14002b425  mov     rdx, rsi; FileObject
0x14002b428  mov     rcx, rdi; Instance
0x14002b42b  mov     [rsp+68h+InputBufferLength], 1; InputBufferLength
0x14002b433  mov     [rsp+68h+InputBuffer], 0
0x14002b43b  call    cs:__imp_FltFsControlFile
0x14002b442  nop     dword ptr [rax+rax+00h]
0x14002b447  mov     edi, eax
0x14002b449  test    eax, eax
0x14002b44b  jns     short loc_14002B4C7
0x14002b44d  mov     dl, byte ptr cs:xmmword_14001A3E0+1
0x14002b453  lea     rax, WPP_RECORDER_INITIALIZED
0x14002b45a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002b461  setnz   r8b
0x14002b465  and     dl, 4
0x14002b468  jnz     short loc_14002B46F
0x14002b46a  test    r8b, r8b
0x14002b46d  jz      short loc_14002B4D2
0x14002b46f  mov     r9, cs:WPP_GLOBAL_Control
0x14002b476  lea     rax, [rsi+58h]
0x14002b47a  mov     [rsp+68h+var_10], rax
0x14002b47f  mov     ecx, 40Ah
0x14002b484  mov     [rsp+68h+var_18], edi
0x14002b488  lea     rax, aOnecoreBaseFsG_10; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002b48f  mov     [rsp+68h+var_20], 2BFh
0x14002b497  mov     r9, [r9+40h]
0x14002b49b  mov     [rsp+68h+var_28], rax
0x14002b4a0  lea     rax, WPP_f6f932a41f663696b98ce9faa74178e4_Traceguids
0x14002b4a7  mov     [rsp+68h+LengthReturned], rax
0x14002b4ac  mov     word ptr [rsp+68h+OutputBufferLength], 0Ch
0x14002b4b3  mov     dword ptr [rsp+68h+OutputBuffer], 0Ah
0x14002b4bb  mov     byte ptr [rsp+68h+InputBufferLength], 4
0x14002b4c0  call    WPP_RECORDER_AND_TRACE_SF_sDdZ
0x14002b4c5  jmp     short loc_14002B4D2
0x14002b4c7  mov     rax, [rbx+8]
0x14002b4cb  mov     rcx, [rax+58h]
0x14002b4cf  or      dword ptr [rcx], 1
0x14002b4d2  mov     eax, edi
0x14002b4d4  mov     rbx, [rsp+68h+arg_0]
0x14002b4d9  mov     rsi, [rsp+68h+arg_8]
0x14002b4de  add     rsp, 60h
0x14002b4e2  pop     rdi
0x14002b4e3  retn
```
