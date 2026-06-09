# CFileVC::DuplicateHandleInPid(_IRP *,_IO_STACK_LOCATION *)

- ea: `0x14002a2ec`
- end: `0x14002a4f0`
- name: `?DuplicateHandleInPid@CFileVC@@QEAAJPEAU_IRP@@PEAU_IO_STACK_LOCATION@@@Z`
- size: `516`
- prototype: `__int64 __fastcall(CFileVC *__hidden this, struct _IRP *, struct _IO_STACK_LOCATION *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x14002a1e0`

## callees

- `0x140003064`
- `0x14000324c`
- `0x14000327c`
- `0x140011c9c`
- `0x14002a2ec`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14002a4a4`
- `ntoskrnl!ObfDereferenceObject` at `0x14002a4a4`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x14002a349`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x14002a349`
- `ntoskrnl!IoGetCurrentProcess` at `0x14002a399`
- `ntoskrnl!IoGetCurrentProcess` at `0x14002a399`
- `ntoskrnl!ObDuplicateObject` at `0x14002a415`
- `ntoskrnl!ObDuplicateObject` at `0x14002a415`

## pseudocode

```c
__int64 __fastcall CFileVC::DuplicateHandleInPid(CFileVC *this, struct _IRP *a2, struct _IO_STACK_LOCATION *a3)
{
  PNAMED_PIPE_CREATE_PARAMETERS Parameters; // rax
  PVOID UserBuffer; // rsi
  __int64 v5; // rdi
  NTSTATUS v6; // ebx
  PDEVICE_OBJECT v7; // rcx
  __int64 v8; // rdx
  PEPROCESS CurrentProcess; // rax
  char v11; // [rsp+38h] [rbp-40h]
  int v12; // [rsp+40h] [rbp-38h]
  __int64 v13; // [rsp+48h] [rbp-30h]
  __int64 v14; // [rsp+50h] [rbp-28h] BYREF
  HANDLE ProcessId; // [rsp+58h] [rbp-20h]
  PEPROCESS Process; // [rsp+80h] [rbp+8h] BYREF
  __int64 v17; // [rsp+88h] [rbp+10h] BYREF
  __int64 v18; // [rsp+90h] [rbp+18h]

  v17 = 0;
  Process = 0;
  Parameters = a3->Parameters.CreatePipe.Parameters;
  UserBuffer = a2->UserBuffer;
  v14 = 0;
  LODWORD(ProcessId) = 0;
  RtlCopyFromUser(&v14, Parameters, 0xCu);
  v5 = v14;
  v13 = v14;
  v12 = (int)ProcessId;
  v6 = PsLookupProcessByProcessId((HANDLE)(unsigned int)ProcessId, &Process);
  if ( v6 >= 0 )
  {
    CurrentProcess = IoGetCurrentProcess();
    if ( CurrentProcess )
    {
      v11 = 1;
      v6 = ObDuplicateObject(CurrentProcess, v5, Process, &v17, 0, 0, 6, v11, v12, v13);
      if ( v6 >= 0 )
      {
        v18 = v17;
        RtlWriteULong64ToUser(UserBuffer, v17);
      }
      else
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v8 = 16;
          goto LABEL_5;
        }
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_d4f12fa315663c1b230acb9b01de5cc1_Traceguids);
      v6 = -1073741811;
    }
  }
  else
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v8 = 14;
LABEL_5:
      WPP_SF_d(v7->AttachedDevice, v8, WPP_d4f12fa315663c1b230acb9b01de5cc1_Traceguids, (unsigned int)v6);
    }
  }
  if ( Process )
    ObfDereferenceObject(Process);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14002a2ec  mov     r11, rsp
0x14002a2ef  mov     [r11+8], rcx
0x14002a2f3  push    rbx
0x14002a2f4  push    rsi
0x14002a2f5  push    rdi
0x14002a2f6  sub     rsp, 60h
0x14002a2fa  mov     qword ptr [r11+10h], 0
0x14002a302  mov     qword ptr [r11+8], 0
0x14002a30a  mov     rax, [r8+20h]
0x14002a30e  mov     rsi, [rdx+70h]
0x14002a312  xor     ecx, ecx
0x14002a314  mov     [r11-28h], rcx
0x14002a318  mov     dword ptr [rsp+78h+ProcessId], ecx
0x14002a31c  lea     r8d, [rcx+0Ch]; Size
0x14002a320  mov     rdx, rax; Src
0x14002a323  lea     rcx, [r11-28h]; void *
0x14002a327  call    RtlCopyFromUser
0x14002a32c  mov     rdi, [rsp+78h+var_28]
0x14002a331  mov     [rsp+78h+var_30], rdi
0x14002a336  mov     eax, dword ptr [rsp+78h+ProcessId]
0x14002a33a  mov     [rsp+78h+var_38], eax
0x14002a33e  mov     rcx, rax; ProcessId
0x14002a341  lea     rdx, [rsp+78h+Process]; Process
0x14002a349  call    cs:__imp_PsLookupProcessByProcessId
0x14002a350  nop     dword ptr [rax+rax+00h]
0x14002a355  mov     ebx, eax
0x14002a357  test    eax, eax
0x14002a359  jns     short loc_14002A399
0x14002a35b  lea     rax, WPP_GLOBAL_Control
0x14002a362  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a369  cmp     rcx, rax
0x14002a36c  jz      loc_14002A497
0x14002a372  cmp     byte ptr [rcx+29h], 2
0x14002a376  jb      loc_14002A497
0x14002a37c  mov     edx, 0Eh
0x14002a381  mov     r9d, ebx
0x14002a384  lea     r8, WPP_d4f12fa315663c1b230acb9b01de5cc1_Traceguids
0x14002a38b  mov     rcx, [rcx+18h]
0x14002a38f  call    WPP_SF_d
0x14002a394  jmp     loc_14002A497
0x14002a399  call    cs:__imp_IoGetCurrentProcess
0x14002a3a0  nop     dword ptr [rax+rax+00h]
0x14002a3a5  test    rax, rax
0x14002a3a8  jnz     short loc_14002A3E2
0x14002a3aa  lea     rax, WPP_GLOBAL_Control
0x14002a3b1  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a3b8  cmp     rcx, rax
0x14002a3bb  jz      short loc_14002A3D8
0x14002a3bd  cmp     byte ptr [rcx+29h], 2
0x14002a3c1  jb      short loc_14002A3D8
0x14002a3c3  mov     edx, 0Fh
0x14002a3c8  lea     r8, WPP_d4f12fa315663c1b230acb9b01de5cc1_Traceguids
0x14002a3cf  mov     rcx, [rcx+18h]
0x14002a3d3  call    WPP_SF_
0x14002a3d8  mov     ebx, 0C000000Dh
0x14002a3dd  jmp     loc_14002A497
0x14002a3e2  mov     [rsp+78h+var_40], 1
0x14002a3e7  mov     [rsp+78h+var_48], 6
0x14002a3ef  mov     [rsp+78h+var_50], 0
0x14002a3f7  mov     [rsp+78h+var_58], 0
0x14002a3ff  lea     r9, [rsp+78h+arg_8]
0x14002a407  mov     r8, [rsp+78h+Process]
0x14002a40f  mov     rdx, rdi
0x14002a412  mov     rcx, rax
0x14002a415  call    cs:__imp_ObDuplicateObject
0x14002a41c  nop     dword ptr [rax+rax+00h]
0x14002a421  mov     ebx, eax
0x14002a423  test    eax, eax
0x14002a425  jns     short loc_14002A44A
0x14002a427  lea     rax, WPP_GLOBAL_Control
0x14002a42e  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a435  cmp     rcx, rax
0x14002a438  jz      short loc_14002A497
0x14002a43a  cmp     byte ptr [rcx+29h], 2
0x14002a43e  jb      short loc_14002A497
0x14002a440  mov     edx, 10h
0x14002a445  jmp     loc_14002A381
0x14002a44a  mov     rdx, [rsp+78h+arg_8]
0x14002a452  mov     [rsp+78h+arg_10], rdx
0x14002a45a  mov     rcx, rsi
0x14002a45d  call    RtlWriteULong64ToUser
0x14002a462  jmp     short loc_14002A497
0x14002a464  lea     rax, WPP_GLOBAL_Control
0x14002a46b  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a472  cmp     rcx, rax
0x14002a475  jz      short loc_14002A492
0x14002a477  cmp     byte ptr [rcx+29h], 2
0x14002a47b  jb      short loc_14002A492
0x14002a47d  mov     edx, 11h
0x14002a482  lea     r8, WPP_d4f12fa315663c1b230acb9b01de5cc1_Traceguids
0x14002a489  mov     rcx, [rcx+18h]
0x14002a48d  call    WPP_SF_
0x14002a492  mov     ebx, 0C000000Dh
0x14002a497  mov     rcx, [rsp+78h+Process]; Object
0x14002a49f  test    rcx, rcx
0x14002a4a2  jz      short loc_14002A4B0
0x14002a4a4  call    cs:__imp_ObfDereferenceObject
0x14002a4ab  nop     dword ptr [rax+rax+00h]
0x14002a4b0  mov     eax, ebx
0x14002a4b2  jmp     short loc_14002A4E7
0x14002a4b4  lea     rax, WPP_GLOBAL_Control
0x14002a4bb  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a4c2  cmp     rcx, rax
0x14002a4c5  jz      short loc_14002A4E2
0x14002a4c7  cmp     byte ptr [rcx+29h], 2
0x14002a4cb  jb      short loc_14002A4E2
0x14002a4cd  mov     edx, 0Dh
0x14002a4d2  lea     r8, WPP_d4f12fa315663c1b230acb9b01de5cc1_Traceguids
0x14002a4d9  mov     rcx, [rcx+18h]
0x14002a4dd  call    WPP_SF_
0x14002a4e2  mov     eax, 0C000000Dh
0x14002a4e7  add     rsp, 60h
0x14002a4eb  pop     rdi
0x14002a4ec  pop     rsi
0x14002a4ed  pop     rbx
0x14002a4ee  retn
```
