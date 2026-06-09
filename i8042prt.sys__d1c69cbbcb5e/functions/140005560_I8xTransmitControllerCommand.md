# I8xTransmitControllerCommand

- ea: `0x140005560`
- end: `0x14000581e`
- name: `I8xTransmitControllerCommand`
- size: `702`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001d8b0`
- `0x14001eda0`

## callees

- `0x140004530`
- `0x140005560`
- `0x140005830`
- `0x140005de0`
- `0x140006950`
- `0x140007b10`
- `0x14000a018`

## import_xrefs

- `ntoskrnl!IoAllocateErrorLogEntry` at `0x14000570c`
- `ntoskrnl!IoAllocateErrorLogEntry` at `0x14000570c`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400056e2`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400056e2`
- `ntoskrnl!KeQueryTimeIncrement` at `0x1400055f1`
- `ntoskrnl!KeQueryTimeIncrement` at `0x1400055f1`
- `ntoskrnl!IoWriteErrorLogEntry` at `0x14000575b`
- `ntoskrnl!IoWriteErrorLogEntry` at `0x14000575b`
- `HAL!KeStallExecutionProcessor` at `0x14000577d`
- `HAL!KeStallExecutionProcessor` at `0x14000577d`

## pseudocode

```c
__int64 __fastcall I8xTransmitControllerCommand(unsigned int *a1, int a2)
{
  __int64 result; // rax
  int v4; // edx
  char v5; // bp
  unsigned __int8 v6; // bp
  __int64 v7; // rbx
  __int64 v8; // rdi
  int v9; // edx
  int v10; // edx
  unsigned __int8 v11; // bl
  PVOID *DeviceRoutine; // rcx
  _DWORD *ErrorLogEntry; // rax
  unsigned int v14; // r8d
  char v15; // [rsp+70h] [rbp+8h] BYREF
  unsigned __int8 v16; // [rsp+78h] [rbp+10h] BYREF

  v15 = 0;
  v16 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      19,
      89,
      (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids);
  result = I8xGetControllerCommand(*a1, &v15);
  a1[2] = result;
  if ( (int)result >= 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_D(
        WPP_GLOBAL_Control->DeviceExtension,
        v4,
        20,
        90,
        (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids,
        v15);
    v5 = *((_BYTE *)a1 + 5);
    if ( *((_BYTE *)a1 + 4) )
      v6 = v15 & v5;
    else
      v6 = v15 | v5;
    v7 = MEMORY[0xFFFFF78000000320];
    v8 = v7 + 20000000 * KeQueryTimeIncrement();
    do
    {
      a1[2] = I8xPutControllerCommand(v6);
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_D(
          WPP_GLOBAL_Control->DeviceExtension,
          v9,
          20,
          91,
          (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids,
          v6);
      result = I8xGetControllerCommand(*a1, &v16);
      v11 = v16;
      a1[2] = result;
      if ( v11 != 0xFF )
        break;
      KeStallExecutionProcessor(0x32u);
      result = MEMORY[0xFFFFF78000000320];
    }
    while ( v8 > MEMORY[0xFFFFF78000000320] );
    if ( (a1[2] & 0x80000000) == 0 && v11 != v6 && v11 != 0xFA )
    {
      a1[2] = -1073741668;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_dD(
          WPP_GLOBAL_Control->DeviceExtension,
          v10,
          21,
          92,
          (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids,
          v6,
          v11);
      if ( KeGetCurrentIrql() <= 2u )
      {
        DeviceRoutine = (PVOID *)WPP_MAIN_CB.Queue.Wcb.DeviceRoutine;
        if ( WPP_MAIN_CB.Queue.Wcb.DeviceContext )
          DeviceRoutine = (PVOID *)WPP_MAIN_CB.Queue.Wcb.DeviceContext;
        ErrorLogEntry = IoAllocateErrorLogEntry(*DeviceRoutine, 0x40u);
        if ( ErrorLogEntry )
        {
          v14 = a1[2];
          ErrorLogEntry[3] = 1074069532;
          *((_WORD *)ErrorLogEntry + 1) = 16;
          *((_QWORD *)ErrorLogEntry + 3) = 0;
          *(_WORD *)ErrorLogEntry = 0;
          ErrorLogEntry[13] = v6;
          ErrorLogEntry[4] = 80;
          ErrorLogEntry[5] = v14;
          *((_QWORD *)ErrorLogEntry + 5) = 1;
          ErrorLogEntry[12] = 96;
          IoWriteErrorLogEntry(ErrorLogEntry);
        }
      }
      result = TraceLoggingTransmitControllerCommandFailed(v6, v11);
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return WPP_RECORDER_SF_(
               WPP_GLOBAL_Control->DeviceExtension,
               v10,
               19,
               93,
               (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x140005560  push    rsi
0x140005562  push    r14
0x140005564  push    r15
0x140005566  sub     rsp, 50h
0x14000556a  mov     rsi, rcx
0x14000556d  mov     [rsp+68h+arg_0], 0
0x140005572  mov     [rsp+68h+arg_8], 0
0x140005577  lea     r14, WPP_RECORDER_INITIALIZED
0x14000557e  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140005585  lea     r15, WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids
0x14000558c  jnz     loc_1400057C9
0x140005592  mov     ecx, [rsi]
0x140005594  lea     rdx, [rsp+68h+arg_0]
0x140005599  call    I8xGetControllerCommand
0x14000559e  mov     [rsi+8], eax
0x1400055a1  test    eax, eax
0x1400055a3  js      loc_140005686
0x1400055a9  mov     [rsp+68h+arg_10], rbx
0x1400055b1  mov     [rsp+68h+arg_18], rbp
0x1400055b9  mov     [rsp+68h+var_20], rdi
0x1400055be  mov     [rsp+68h+var_28], r12
0x1400055c3  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400055ca  jnz     loc_1400057EF
0x1400055d0  cmp     byte ptr [rsi+4], 0
0x1400055d4  movzx   ebp, byte ptr [rsi+5]
0x1400055d8  jz      loc_140005691
0x1400055de  and     bpl, [rsp+68h+arg_0]
0x1400055e3  mov     r12, 0FFFFF78000000320h
0x1400055ed  mov     rbx, [r12]
0x1400055f1  call    cs:__imp_KeQueryTimeIncrement
0x1400055f8  nop     dword ptr [rax+rax+00h]
0x1400055fd  imul    edi, eax, 1312D00h
0x140005603  add     rdi, rbx
0x140005606  movzx   ecx, bpl
0x14000560a  call    I8xPutControllerCommand
0x14000560f  mov     [rsi+8], eax
0x140005612  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140005619  jnz     loc_14000579B
0x14000561f  mov     ecx, [rsi]
0x140005621  lea     rdx, [rsp+68h+arg_8]
0x140005626  call    I8xGetControllerCommand
0x14000562b  movzx   ebx, [rsp+68h+arg_8]
0x140005630  mov     [rsi+8], eax
0x140005633  cmp     bl, 0FFh
0x140005636  jz      loc_140005778
0x14000563c  cmp     dword ptr [rsi+8], 0
0x140005640  mov     r12, [rsp+68h+var_28]
0x140005645  mov     rdi, [rsp+68h+var_20]
0x14000564a  jge     short loc_14000569B
0x14000564c  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140005653  mov     rbp, [rsp+68h+arg_18]
0x14000565b  mov     rbx, [rsp+68h+arg_10]
0x140005663  jz      short loc_140005686
0x140005665  mov     rcx, cs:WPP_GLOBAL_Control
0x14000566c  mov     r9d, 5Dh ; ']'
0x140005672  mov     r8d, 13h
0x140005678  mov     [rsp+68h+var_48], r15
0x14000567d  mov     rcx, [rcx+40h]
0x140005681  call    WPP_RECORDER_SF_
0x140005686  add     rsp, 50h
0x14000568a  pop     r15
0x14000568c  pop     r14
0x14000568e  pop     rsi
0x14000568f  retn
0x140005691  or      bpl, [rsp+68h+arg_0]
0x140005696  jmp     loc_1400055E3
0x14000569b  cmp     bl, bpl
0x14000569e  jz      short loc_14000564C
0x1400056a0  cmp     bl, 0FAh
0x1400056a3  jz      short loc_14000564C
0x1400056a5  mov     dword ptr [rsi+8], 0C000009Ch
0x1400056ac  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400056b3  jz      short loc_1400056E2
0x1400056b5  movzx   ecx, bpl
0x1400056b9  mov     r9d, 5Ch ; '\'
0x1400056bf  mov     [rsp+68h+var_38], ebx
0x1400056c3  mov     r8d, 15h
0x1400056c9  mov     [rsp+68h+var_40], ecx
0x1400056cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400056d4  mov     [rsp+68h+var_48], r15
0x1400056d9  mov     rcx, [rcx+40h]
0x1400056dd  call    WPP_RECORDER_SF_dD
0x1400056e2  call    cs:__imp_KeGetCurrentIrql
0x1400056e9  nop     dword ptr [rax+rax+00h]
0x1400056ee  cmp     al, 2
0x1400056f0  ja      short loc_140005767
0x1400056f2  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+20h
0x1400056f9  mov     dl, 40h ; '@'; EntrySize
0x1400056fb  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+18h
0x140005702  test    rax, rax
0x140005705  cmovnz  rcx, rax
0x140005709  mov     rcx, [rcx]; IoObject
0x14000570c  call    cs:__imp_IoAllocateErrorLogEntry
0x140005713  nop     dword ptr [rax+rax+00h]
0x140005718  mov     rcx, rax; ElEntry
0x14000571b  test    rax, rax
0x14000571e  jz      short loc_140005767
0x140005720  mov     r8d, [rsi+8]
0x140005724  mov     dword ptr [rax+0Ch], 4005001Ch
0x14000572b  mov     word ptr [rax+2], 10h
0x140005731  xor     eax, eax
0x140005733  mov     [rcx+18h], rax
0x140005737  mov     [rcx], ax
0x14000573a  movzx   eax, bpl
0x14000573e  mov     [rcx+34h], eax
0x140005741  mov     dword ptr [rcx+10h], 50h ; 'P'
0x140005748  mov     [rcx+14h], r8d
0x14000574c  mov     qword ptr [rcx+28h], 1
0x140005754  mov     dword ptr [rcx+30h], 60h ; '`'
0x14000575b  call    cs:__imp_IoWriteErrorLogEntry
0x140005762  nop     dword ptr [rax+rax+00h]
0x140005767  movzx   edx, bl
0x14000576a  movzx   ecx, bpl
0x14000576e  call    TraceLoggingTransmitControllerCommandFailed
0x140005773  jmp     loc_14000564C
0x140005778  mov     ecx, 32h ; '2'; MicroSeconds
0x14000577d  call    cs:__imp_KeStallExecutionProcessor
0x140005784  nop     dword ptr [rax+rax+00h]
0x140005789  mov     rax, [r12]
0x14000578d  cmp     rdi, rax
0x140005790  jle     loc_14000563C
0x140005796  jmp     loc_140005606
0x14000579b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400057a2  mov     r9d, 5Bh ; '['
0x1400057a8  movzx   eax, bpl
0x1400057ac  mov     r8d, 14h
0x1400057b2  mov     [rsp+68h+var_40], eax
0x1400057b6  mov     [rsp+68h+var_48], r15
0x1400057bb  mov     rcx, [rcx+40h]
0x1400057bf  call    WPP_RECORDER_SF_D
0x1400057c4  jmp     loc_14000561F
0x1400057c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400057d0  mov     r9d, 59h ; 'Y'
0x1400057d6  mov     r8d, 13h
0x1400057dc  mov     [rsp+68h+var_48], r15
0x1400057e1  mov     rcx, [rcx+40h]
0x1400057e5  call    WPP_RECORDER_SF_
0x1400057ea  jmp     loc_140005592
0x1400057ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1400057f6  mov     r9d, 5Ah ; 'Z'
0x1400057fc  movzx   eax, [rsp+68h+arg_0]
0x140005801  mov     r8d, 14h
0x140005807  mov     [rsp+68h+var_40], eax
0x14000580b  mov     [rsp+68h+var_48], r15
0x140005810  mov     rcx, [rcx+40h]
0x140005814  call    WPP_RECORDER_SF_D
0x140005819  jmp     loc_1400055D0
```
