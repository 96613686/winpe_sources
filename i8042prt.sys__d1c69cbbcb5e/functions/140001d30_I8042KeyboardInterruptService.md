# I8042KeyboardInterruptService

- ea: `0x140001d30`
- end: `0x1400025ff`
- name: `I8042KeyboardInterruptService`
- size: `2255`
- prototype: `KSERVICE_ROUTINE`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, service_task`

## callees

- `0x140001360`
- `0x1400014e0`
- `0x1400015c0`
- `0x1400019e0`
- `0x140001d30`
- `0x140004180`
- `0x140004530`
- `0x140007b10`
- `0x14000daa0`

## import_xrefs

- `ntoskrnl!KdDebuggerEnabled` at `0x140001e73`
- `ntoskrnl!DbgBreakPointWithStatus` at `0x140002559`
- `ntoskrnl!DbgBreakPointWithStatus` at `0x1400025ac`
- `ntoskrnl!DbgBreakPointWithStatus` at `0x140002559`
- `ntoskrnl!DbgBreakPointWithStatus` at `0x1400025ac`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x14000253c`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x14000258f`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x14000253c`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x14000258f`
- `ntoskrnl!KeInsertQueueDpc` at `0x14000204c`
- `ntoskrnl!KeInsertQueueDpc` at `0x14000219a`
- `ntoskrnl!KeInsertQueueDpc` at `0x140002411`
- `ntoskrnl!KeInsertQueueDpc` at `0x14000204c`
- `ntoskrnl!KeInsertQueueDpc` at `0x14000219a`
- `ntoskrnl!KeInsertQueueDpc` at `0x140002411`
- `HAL!KeStallExecutionProcessor` at `0x140001ed3`
- `HAL!KeStallExecutionProcessor` at `0x140001ed3`

## pseudocode

```c
BOOLEAN __fastcall I8042KeyboardInterruptService(struct _KINTERRUPT *Interrupt, char *ServiceContext)
{
  __int64 v3; // rdi
  unsigned __int8 v4; // r12
  __int64 v5; // rcx
  __int64 v6; // r15
  __int64 (__fastcall *v7)(_QWORD, __int64, __int64, _QWORD, unsigned __int8 *, char *, __int64); // rax
  int v8; // edx
  int *v9; // rbx
  int v10; // r8d
  int v11; // ecx
  BOOLEAN result; // al
  unsigned int i; // ebx
  int v14; // edx
  int v15; // r9d
  int v16; // ecx
  int v17; // eax
  struct _KDPC *v18; // rcx
  __int64 v19; // r8
  int v20; // edx
  int v21; // r9d
  int v22; // r9d
  unsigned int v23; // eax
  int v24; // r8d
  unsigned __int8 v25; // [rsp+A0h] [rbp+18h] BYREF
  char v26; // [rsp+A8h] [rbp+20h] BYREF

  v25 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)ServiceContext,
      26,
      10,
      (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids);
  v3 = *((_QWORD *)ServiceContext + 8);
  if ( *(_DWORD *)(v3 + 80) != 1 )
    return 0;
  v4 = (*(__int64 (__fastcall **)(_QWORD))&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters)(*(_QWORD *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels
                                                                                                 + 216LL));
  v5 = v4;
  v6 = 1;
  if ( (v4 & 0x21) == 1 )
    goto LABEL_5;
  for ( i = 0; i < *(unsigned __int16 *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 76LL); ++i )
  {
    KeStallExecutionProcessor(1u);
    if ( ((*(__int64 (__fastcall **)(_QWORD))&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters)(*(_QWORD *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 216LL))
        & 0x21) == 1 )
      break;
  }
  v4 = (*(__int64 (__fastcall **)(_QWORD))&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters)(*(_QWORD *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels
                                                                                                 + 216LL));
  if ( (v4 & 0x21) != 1 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v14,
        28,
        11,
        (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids);
    if ( !*(_DWORD *)(v3 + 96) )
      (*(void (__fastcall **)(_QWORD))&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters)(*(_QWORD *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels
                                                                                             + 208LL));
    return 0;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v14,
      27,
      12,
      (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids,
      i + 1);
LABEL_5:
  LOBYTE(v5) = 1;
  I8xGetByteAsynchronous(v5, &v25);
  *(_BYTE *)(v3 + 587) = *(_BYTE *)(v3 + 586);
  *(_BYTE *)(v3 + 586) = v25;
  v7 = *(__int64 (__fastcall **)(_QWORD, __int64, __int64, _QWORD, unsigned __int8 *, char *, __int64))(v3 + 928);
  if ( v7 )
  {
    v26 = 0;
    result = v7(*(_QWORD *)(v3 + 936), v3 + 904, v3 + 512, v4, &v25, &v26, v3 + 916);
    if ( !v26 )
      return result;
  }
  v8 = v25;
  if ( v25 == 250 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v25,
        27,
        14,
        (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids);
    if ( !*(_DWORD *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 204LL) )
      goto LABEL_21;
    *(_DWORD *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 204LL) = -1;
    *(_WORD *)(v3 + 560) = 0;
    if ( *(_DWORD *)(v3 + 528) != 1 )
      goto LABEL_21;
    if ( *(_DWORD *)(v3 + 520) < *(_DWORD *)(v3 + 524) )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          v8,
          27,
          16,
          (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids,
          *(_DWORD *)(v3 + 520));
      I8xInitiateIo(ServiceContext);
      goto LABEL_21;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v8,
        27,
        17,
        (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids);
    v18 = (struct _KDPC *)(ServiceContext + 200);
    v19 = 1;
  }
  else
  {
    if ( v25 != 254 )
      goto LABEL_8;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v25,
        27,
        13,
        (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids,
        *(_WORD *)(v3 + 560) + 1);
    if ( !*(_DWORD *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 204LL) )
      goto LABEL_21;
    *(_DWORD *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 204LL) = -1;
    if ( !*(_DWORD *)(v3 + 528) || !*((_QWORD *)ServiceContext + 4) )
    {
      v8 = v25;
LABEL_8:
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v8,
          27,
          18,
          (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids);
        v8 = v25;
      }
      v9 = (int *)(v3 + 916);
      if ( (_BYTE)v8 == 0xFF )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            v8,
            28,
            19,
            (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids);
        *(_DWORD *)(v3 + 906) = 255;
        goto LABEL_18;
      }
      v10 = *v9;
      if ( *v9 == 2 )
      {
LABEL_12:
        if ( *(_DWORD *)(v3 + 944) || *(_DWORD *)(v3 + 956) )
        {
          I8xProcessCrashDump(v3);
          v8 = v25;
        }
        if ( (unsigned __int8)v8 <= 0x7Fu )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            WPP_RECORDER_SF_(
              WPP_GLOBAL_Control->DeviceExtension,
              v8,
              27,
              29,
              (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids);
            v8 = v25;
          }
          v11 = (unsigned __int8)v8;
          *(_WORD *)(v3 + 906) = (unsigned __int8)v8;
          if ( (_BYTE)KdDebuggerEnabled )
          {
            v8 = *(unsigned __int16 *)(v3 + 908);
            if ( (v8 & 1) == 0 )
            {
              v23 = *(unsigned __int8 *)(v3 + 688);
              if ( (unsigned __int8)v23 <= 8u && (v24 = 404, _bittest(&v24, v23)) )
              {
                if ( v11 == 55
                  && (v8 & 2) != 0
                  && !KdRefreshDebuggerNotPresent()
                  && BYTE5(WPP_MAIN_CB.Dpc.DeferredRoutine) )
                {
                  DbgBreakPointWithStatus(2u);
                }
              }
              else if ( v11 == 84 && !KdRefreshDebuggerNotPresent() && BYTE5(WPP_MAIN_CB.Dpc.DeferredRoutine) )
              {
                DbgBreakPointWithStatus(2u);
              }
            }
          }
LABEL_18:
          *v9 = 0;
          goto LABEL_19;
        }
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            v8,
            27,
            22,
            (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids);
          v8 = v25;
        }
        LOBYTE(v8) = v8 & 0x7F;
        v16 = (unsigned __int8)v8;
        *(_WORD *)(v3 + 906) = (unsigned __int8)v8;
        *(_WORD *)(v3 + 908) |= 1u;
        if ( (*(_WORD *)(v3 + 908) & 2) == 0 )
          goto LABEL_18;
        v8 = (unsigned __int8)v8 - 94;
        if ( v16 == 94 )
        {
          if ( (*(_BYTE *)(v3 + 584) & 1) != 0 )
          {
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_101;
            v21 = 23;
            goto LABEL_86;
          }
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v22 = 24;
            goto LABEL_99;
          }
        }
        else if ( --v8 )
        {
          if ( v8 != 4 )
          {
            v17 = 0;
            v6 = 0;
            goto LABEL_44;
          }
          if ( (*(_BYTE *)(v3 + 584) & 4) != 0 )
          {
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
LABEL_101:
              v17 = v6;
LABEL_44:
              if ( v17 )
                KeInsertQueueDpc((PRKDPC)(v3 + 600), (PVOID)v6, (PVOID)*(unsigned __int16 *)(v3 + 906));
              goto LABEL_18;
            }
            v21 = 27;
LABEL_86:
            WPP_RECORDER_SF_(
              WPP_GLOBAL_Control->DeviceExtension,
              v8,
              26,
              v21,
              (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids);
            goto LABEL_101;
          }
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v22 = 28;
LABEL_99:
            WPP_RECORDER_SF_(
              WPP_GLOBAL_Control->DeviceExtension,
              v8,
              26,
              v22,
              (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids);
          }
        }
        else
        {
          if ( (*(_BYTE *)(v3 + 584) & 2) != 0 )
          {
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_101;
            v21 = 25;
            goto LABEL_86;
          }
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v22 = 26;
            goto LABEL_99;
          }
        }
        v6 = 2;
        goto LABEL_101;
      }
      if ( v10 )
      {
        if ( v10 == 1 )
          goto LABEL_12;
        KeInsertQueueDpc((PRKDPC)(v3 + 232), 0, (PVOID)0xFFFFFFFFC005000ALL);
      }
      else
      {
        if ( (_BYTE)v8 == 0xE0 )
        {
          *(_WORD *)(v3 + 908) |= 2u;
          *v9 = 1;
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_19;
          v15 = 20;
          goto LABEL_49;
        }
        if ( (_BYTE)v8 != 0xE1 )
          goto LABEL_12;
        *(_WORD *)(v3 + 908) |= 4u;
        *v9 = 2;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v15 = 21;
LABEL_49:
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            v8,
            27,
            v15,
            (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids);
        }
      }
LABEL_19:
      if ( !*v9 )
        I8xQueueCurrentKeyboardInput(ServiceContext);
      goto LABEL_21;
    }
    v20 = *(__int16 *)(v3 + 560);
    if ( v20 < *(unsigned __int16 *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 70LL) )
    {
      --*(_DWORD *)(v3 + 520);
      *(_WORD *)(v3 + 560) = v20 + 1;
      I8xInitiateIo(ServiceContext);
      goto LABEL_21;
    }
    v18 = (struct _KDPC *)(v3 + 168);
    v19 = 0;
  }
  *(_DWORD *)(v3 + 528) = 0;
  KeInsertQueueDpc(v18, *((PVOID *)ServiceContext + 4), (PVOID)v19);
LABEL_21:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v8,
      26,
      30,
      (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids);
  return 1;
}

```

## disassembly

```asm
0x140001d30  mov     [rsp+arg_8], rdx
0x140001d35  push    rbx
0x140001d36  push    rsi
0x140001d37  push    rdi
0x140001d38  push    r12
0x140001d3a  push    r13
0x140001d3c  push    r14
0x140001d3e  push    r15
0x140001d40  sub     rsp, 50h
0x140001d44  mov     r14, rdx
0x140001d47  mov     [rsp+88h+arg_10], 0
0x140001d4f  lea     rsi, WPP_RECORDER_INITIALIZED
0x140001d56  lea     rbx, WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids
0x140001d5d  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140001d64  jnz     loc_140001F57
0x140001d6a  mov     rdi, [r14+40h]
0x140001d6e  cmp     dword ptr [rdi+50h], 1
0x140001d72  jnz     loc_140001F50
0x140001d78  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+28h
0x140001d7f  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x140001d86  mov     rcx, [rcx+0D8h]
0x140001d8d  call    _guard_dispatch_icall
0x140001d92  movzx   r12d, al
0x140001d96  movzx   ecx, al
0x140001d99  and     cl, 21h
0x140001d9c  xor     r13d, r13d
0x140001d9f  mov     r15d, 1
0x140001da5  cmp     cl, r15b
0x140001da8  jnz     loc_140001EBA
0x140001dae  lea     rdx, [rsp+88h+arg_10]
0x140001db6  mov     cl, 1
0x140001db8  call    I8xGetByteAsynchronous
0x140001dbd  movzx   eax, byte ptr [rdi+24Ah]
0x140001dc4  mov     [rdi+24Bh], al
0x140001dca  movzx   eax, [rsp+88h+arg_10]
0x140001dd2  mov     [rdi+24Ah], al
0x140001dd8  mov     rax, [rdi+3A0h]
0x140001ddf  test    rax, rax
0x140001de2  jnz     loc_1400020AE
0x140001de8  movzx   edx, [rsp+88h+arg_10]
0x140001df0  mov     ecx, edx
0x140001df2  sub     ecx, 0FAh
0x140001df8  jz      loc_14000210D
0x140001dfe  cmp     ecx, 4
0x140001e01  jz      loc_1400022D5
0x140001e07  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140001e0e  jnz     loc_140002389
0x140001e14  lea     rbx, [rdi+394h]
0x140001e1b  mov     [rsp+88h+var_48], rbx
0x140001e20  cmp     dl, 0FFh
0x140001e23  jz      loc_1400023B7
0x140001e29  mov     r8d, [rbx]
0x140001e2c  cmp     r8d, 2
0x140001e30  jnz     loc_140001F7D
0x140001e36  cmp     dword ptr [rdi+3B0h], 0
0x140001e3d  jz      loc_140002422
0x140001e43  mov     rcx, rdi
0x140001e46  call    I8xProcessCrashDump
0x140001e4b  movzx   edx, [rsp+88h+arg_10]
0x140001e53  cmp     dl, 7Fh
0x140001e56  ja      loc_140001FB2
0x140001e5c  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140001e63  jnz     loc_14000220C
0x140001e69  movzx   ecx, dl
0x140001e6c  mov     [rdi+38Ah], cx
0x140001e73  mov     rax, cs:KdDebuggerEnabled
0x140001e7a  cmp     byte ptr [rax], 0
0x140001e7d  jnz     loc_140002503
0x140001e83  mov     [rbx], r13d
0x140001e86  cmp     dword ptr [rbx], 0
0x140001e89  jnz     short loc_140001E93
0x140001e8b  mov     rcx, r14
0x140001e8e  call    I8xQueueCurrentKeyboardInput
0x140001e93  lea     rbx, WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids
0x140001e9a  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140001ea1  jnz     loc_1400021AB
0x140001ea7  mov     al, 1
0x140001ea9  add     rsp, 50h
0x140001ead  pop     r15
0x140001eaf  pop     r14
0x140001eb1  pop     r13
0x140001eb3  pop     r12
0x140001eb5  pop     rdi
0x140001eb6  pop     rsi
0x140001eb7  pop     rbx
0x140001eb8  retn
0x140001eba  mov     ebx, r13d
0x140001ebd  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x140001ec4  cmp     r13w, [rax+4Ch]
0x140001ec9  jnb     short loc_140001F11
0x140001ecb  nop     dword ptr [rax+rax+00h]
0x140001ed0  mov     ecx, r15d; MicroSeconds
0x140001ed3  call    cs:__imp_KeStallExecutionProcessor
0x140001eda  nop     dword ptr [rax+rax+00h]
0x140001edf  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+28h
0x140001ee6  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x140001eed  mov     rcx, [rcx+0D8h]
0x140001ef4  call    _guard_dispatch_icall
0x140001ef9  and     al, 21h
0x140001efb  cmp     al, r15b
0x140001efe  jz      short loc_140001F11
0x140001f00  inc     ebx
0x140001f02  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x140001f09  movzx   ecx, word ptr [rax+4Ch]
0x140001f0d  cmp     ebx, ecx
0x140001f0f  jb      short loc_140001ED0
0x140001f11  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+28h
0x140001f18  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x140001f1f  mov     rcx, [rcx+0D8h]
0x140001f26  call    _guard_dispatch_icall
0x140001f2b  movzx   r12d, al
0x140001f2f  and     al, 21h
0x140001f31  cmp     al, 1
0x140001f33  jz      loc_14000228D
0x140001f39  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140001f40  jnz     loc_140002241
0x140001f46  cmp     [rdi+60h], r13d
0x140001f4a  jz      loc_14000226E
0x140001f50  xor     al, al
0x140001f52  jmp     loc_140001EA9
0x140001f57  mov     r9d, 0Ah
0x140001f5d  mov     [rsp+88h+var_68], rbx
0x140001f62  mov     r8d, 1Ah
0x140001f68  mov     rcx, cs:WPP_GLOBAL_Control
0x140001f6f  mov     rcx, [rcx+40h]
0x140001f73  call    WPP_RECORDER_SF_
0x140001f78  jmp     loc_140001D6A
0x140001f7d  test    r8d, r8d
0x140001f80  jnz     loc_1400023F7
0x140001f86  cmp     dl, 0E0h
0x140001f89  jnz     loc_14000205D
0x140001f8f  or      word ptr [rdi+38Ch], 2
0x140001f97  mov     [rbx], r15d
0x140001f9a  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140001fa1  jz      loc_140001E86
0x140001fa7  mov     r9d, 14h
0x140001fad  jmp     loc_140002087
0x140001fb2  lea     r12, WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids
0x140001fb9  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140001fc0  jz      short loc_140001FEB
0x140001fc2  mov     r9d, 16h
0x140001fc8  mov     [rsp+88h+var_68], r12
0x140001fcd  mov     r8d, 1Bh
0x140001fd3  mov     rcx, cs:WPP_GLOBAL_Control
0x140001fda  mov     rcx, [rcx+40h]
0x140001fde  call    WPP_RECORDER_SF_
0x140001fe3  movzx   edx, [rsp+88h+arg_10]
0x140001feb  and     dl, 7Fh
0x140001fee  movzx   ecx, dl
0x140001ff1  mov     [rdi+38Ah], cx
0x140001ff8  or      word ptr [rdi+38Ch], 1
0x140002000  movzx   eax, word ptr [rdi+38Ch]
0x140002007  test    al, 2
0x140002009  jz      loc_140001E83
0x14000200f  mov     edx, ecx
0x140002011  sub     edx, 5Eh ; '^'
0x140002014  jz      loc_1400024B7
0x14000201a  sub     edx, 1
0x14000201d  jz      loc_140002489
0x140002023  cmp     edx, 4
0x140002026  jz      loc_140002434
0x14000202c  mov     eax, r13d
0x14000202f  mov     r15, r13
0x140002032  test    eax, eax
0x140002034  jz      loc_140001E83
0x14000203a  movzx   r8d, word ptr [rdi+38Ah]; SystemArgument2
0x140002042  lea     rcx, [rdi+258h]; Dpc
0x140002049  mov     rdx, r15; SystemArgument1
0x14000204c  call    cs:__imp_KeInsertQueueDpc
0x140002053  nop     dword ptr [rax+rax+00h]
0x140002058  jmp     loc_140001E83
0x14000205d  cmp     dl, 0E1h
0x140002060  jnz     loc_140001E36
0x140002066  or      word ptr [rdi+38Ch], 4
0x14000206e  mov     dword ptr [rbx], 2
0x140002074  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14000207b  jz      loc_140001E86
0x140002081  mov     r9d, 15h
0x140002087  lea     r12, WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids
0x14000208e  mov     [rsp+88h+var_68], r12
0x140002093  mov     r8d, 1Bh
0x140002099  mov     rcx, cs:WPP_GLOBAL_Control
0x1400020a0  mov     rcx, [rcx+40h]
0x1400020a4  call    WPP_RECORDER_SF_
0x1400020a9  jmp     loc_140001E86
0x1400020ae  mov     [rsp+88h+arg_18], 0
0x1400020b6  lea     rcx, [rdi+394h]
0x1400020bd  lea     r8, [rdi+200h]
0x1400020c4  lea     rdx, [rdi+388h]
0x1400020cb  mov     [rsp+88h+var_58], rcx
0x1400020d0  lea     rcx, [rsp+88h+arg_18]
0x1400020d8  mov     [rsp+88h+var_60], rcx
0x1400020dd  lea     rcx, [rsp+88h+arg_10]
0x1400020e5  mov     [rsp+88h+var_68], rcx
0x1400020ea  movzx   r9d, r12b
0x1400020ee  mov     rcx, [rdi+3A8h]
0x1400020f5  call    _guard_dispatch_icall
0x1400020fa  cmp     [rsp+88h+arg_18], 0
0x140002102  jnz     loc_140001DE8
0x140002108  jmp     loc_140001EA9
0x14000210d  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140002114  jnz     loc_1400025D9
0x14000211a  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x140002121  cmp     dword ptr [rax+0CCh], 0
0x140002128  jz      loc_140001E9A
0x14000212e  mov     dword ptr [rax+0CCh], 0FFFFFFFFh
0x140002138  mov     [rdi+230h], r13w
0x140002140  cmp     dword ptr [rdi+210h], 1
0x140002147  jnz     loc_140001E9A
0x14000214d  mov     eax, [rdi+208h]
0x140002153  cmp     eax, [rdi+20Ch]
0x140002159  jb      short loc_1400021D1
0x14000215b  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140002162  jz      short loc_140002185
0x140002164  mov     r9d, 11h
0x14000216a  mov     [rsp+88h+var_68], rbx
0x14000216f  mov     r8d, 1Bh
0x140002175  mov     rcx, cs:WPP_GLOBAL_Control
0x14000217c  mov     rcx, [rcx+40h]
0x140002180  call    WPP_RECORDER_SF_
0x140002185  lea     rcx, [r14+0C8h]; Dpc
0x14000218c  mov     r8, r15; SystemArgument2
0x14000218f  mov     [rdi+210h], r13d
0x140002196  mov     rdx, [r14+20h]; SystemArgument1
0x14000219a  call    cs:__imp_KeInsertQueueDpc
0x1400021a1  nop     dword ptr [rax+rax+00h]
0x1400021a6  jmp     loc_140001E9A
0x1400021ab  mov     r9d, 1Eh
0x1400021b1  mov     [rsp+88h+var_68], rbx
0x1400021b6  mov     r8d, 1Ah
0x1400021bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400021c3  mov     rcx, [rcx+40h]
0x1400021c7  call    WPP_RECORDER_SF_
0x1400021cc  jmp     loc_140001EA7
0x1400021d1  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400021d8  jz      short loc_1400021FF
0x1400021da  mov     r9d, 10h
0x1400021e0  mov     dword ptr [rsp+88h+var_60], eax
0x1400021e4  mov     [rsp+88h+var_68], rbx
0x1400021e9  mov     r8d, 1Bh
0x1400021ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1400021f6  mov     rcx, [rcx+40h]
0x1400021fa  call    WPP_RECORDER_SF_d
0x1400021ff  mov     rcx, r14
0x140002202  call    I8xInitiateIo
0x140002207  jmp     loc_140001E9A
0x14000220c  mov     r9d, 1Dh
0x140002212  lea     r12, WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids
0x140002219  mov     [rsp+88h+var_68], r12
0x14000221e  mov     r8d, 1Bh
0x140002224  mov     rcx, cs:WPP_GLOBAL_Control
0x14000222b  mov     rcx, [rcx+40h]
0x14000222f  call    WPP_RECORDER_SF_
0x140002234  movzx   edx, [rsp+88h+arg_10]
0x14000223c  jmp     loc_140001E69
0x140002241  mov     r9d, 0Bh
0x140002247  lea     r12, WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids
0x14000224e  mov     [rsp+88h+var_68], r12
0x140002253  mov     r8d, 1Ch
0x140002259  mov     rcx, cs:WPP_GLOBAL_Control
0x140002260  mov     rcx, [rcx+40h]
0x140002264  call    WPP_RECORDER_SF_
0x140002269  jmp     loc_140001F46
0x14000226e  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+28h
0x140002275  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x14000227c  mov     rcx, [rcx+0D0h]
0x140002283  call    _guard_dispatch_icall
0x140002288  jmp     loc_140001F50
0x14000228d  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140002294  jz      short loc_1400022C9
0x140002296  inc     ebx
0x140002298  mov     r9d, 0Ch
0x14000229e  mov     dword ptr [rsp+88h+var_60], ebx
0x1400022a2  lea     rbx, WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids
0x1400022a9  mov     [rsp+88h+var_68], rbx
0x1400022ae  mov     r8d, 1Bh
0x1400022b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400022bb  mov     rcx, [rcx+40h]
0x1400022bf  call    WPP_RECORDER_SF_D
0x1400022c4  jmp     loc_140001DAE
0x1400022c9  lea     rbx, WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids
0x1400022d0  jmp     loc_140001DAE
0x1400022d5  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400022dc  jz      short loc_14000230C
0x1400022de  movsx   eax, word ptr [rdi+230h]
0x1400022e5  inc     eax
0x1400022e7  mov     r9d, 0Dh
0x1400022ed  mov     dword ptr [rsp+88h+var_60], eax
0x1400022f1  mov     [rsp+88h+var_68], rbx
0x1400022f6  mov     r8d, 1Bh
0x1400022fc  mov     rcx, cs:WPP_GLOBAL_Control
0x140002303  mov     rcx, [rcx+40h]
0x140002307  call    WPP_RECORDER_SF_d
0x14000230c  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x140002313  cmp     dword ptr [rax+0CCh], 0
0x14000231a  jz      loc_140001E9A
0x140002320  mov     dword ptr [rax+0CCh], 0FFFFFFFFh
0x14000232a  cmp     dword ptr [rdi+210h], 0
0x140002331  jz      short loc_14000237C
0x140002333  cmp     qword ptr [r14+20h], 0
  ... truncated ...
```
