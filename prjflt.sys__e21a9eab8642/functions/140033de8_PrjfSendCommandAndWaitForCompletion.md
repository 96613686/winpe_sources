# PrjfSendCommandAndWaitForCompletion

- ea: `0x140033de8`
- end: `0x140034421`
- name: `PrjfSendCommandAndWaitForCompletion`
- size: `1593`
- prototype: `__int64 __fastcall(struct _FLT_CALLBACK_DATA *, void *, _DWORD *, __int64, __int64, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140033bd0`

## callees

- `0x14000b1a0`
- `0x14000b1d0`
- `0x14000ba20`
- `0x1400106ec`
- `0x14002fda4`
- `0x1400339a8`
- `0x140033de8`

## import_xrefs

- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140033ecb`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140033ecb`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1400343e2`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1400343e2`
- `ntoskrnl!KeInitializeEvent` at `0x140033e5a`
- `ntoskrnl!KeInitializeEvent` at `0x140033e5a`
- `FLTMGR!FltCancellableWaitForMultipleObjects` at `0x14003407a`
- `FLTMGR!FltCancellableWaitForMultipleObjects` at `0x14003407a`
- `FLTMGR!FltSendMessage` at `0x140033f8e`
- `FLTMGR!FltSendMessage` at `0x140033f8e`
- `FLTMGR!FltAcquireResourceExclusive` at `0x140033ea5`
- `FLTMGR!FltAcquireResourceExclusive` at `0x1400343ce`
- `FLTMGR!FltAcquireResourceExclusive` at `0x140033ea5`
- `FLTMGR!FltAcquireResourceExclusive` at `0x1400343ce`
- `FLTMGR!FltReleaseResource` at `0x140033ee1`
- `FLTMGR!FltReleaseResource` at `0x1400343f2`
- `FLTMGR!FltReleaseResource` at `0x140033ee1`
- `FLTMGR!FltReleaseResource` at `0x1400343f2`

## string_xrefs

- `0x140034034`: `CallbackData is expected to be NULL for GetFileStream Command`
- `0x14003413e`: `Command type is expected to be GetFileStream`
- `0x140034127`: `Unexpected command type`

## pseudocode

```c
__int64 __fastcall PrjfSendCommandAndWaitForCompletion(
        struct _FLT_CALLBACK_DATA *a1,
        void *a2,
        _DWORD *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        _DWORD *a7)
{
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  char v13; // si
  PVOID inserted; // rbx
  int v15; // edx
  int v16; // r8d
  int v17; // ebx
  NTSTATUS v18; // eax
  __int64 v19; // rdx
  __int64 v20; // r8
  struct _FLT_CALLBACK_DATA *v21; // rbx
  ULONG v22; // ecx
  NTSTATUS v23; // eax
  __int64 v24; // r9
  int v25; // edx
  int v26; // r8d
  unsigned __int8 NewElement[8]; // [rsp+80h] [rbp-80h] BYREF
  PFLT_CALLBACK_DATA CallbackData; // [rsp+88h] [rbp-78h]
  __int128 Buffer; // [rsp+90h] [rbp-70h] BYREF
  PERESOURCE Resource; // [rsp+A0h] [rbp-60h]
  PRTL_AVL_TABLE Table; // [rsp+A8h] [rbp-58h]
  _BYTE Event[32]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v34; // [rsp+D0h] [rbp-30h]
  PVOID ObjectArray[2]; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v36; // [rsp+E8h] [rbp-18h]

  CallbackData = a1;
  v34 = 0;
  v36 = 0;
  NewElement[0] = 0;
  Buffer = 0;
  memset(Event, 0, sizeof(Event));
  *(_OWORD *)ObjectArray = 0;
  KeInitializeEvent((PRKEVENT)Event, NotificationEvent, 0);
  if ( !a6 || !*a7 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v11, v10, v12);
  v13 = 1;
  *(_DWORD *)&Event[28] = *a7;
  LODWORD(Buffer) = a3[6];
  *((_QWORD *)&Buffer + 1) = Event;
  v34 = a6;
  DWORD1(Buffer) = 1;
  Resource = (PERESOURCE)(a5 + 312);
  FltAcquireResourceExclusive((PERESOURCE)(a5 + 312));
  Table = (PRTL_AVL_TABLE)(a5 + 416);
  inserted = RtlInsertElementGenericTableAvl((PRTL_AVL_TABLE)(a5 + 416), &Buffer, 0x10u, NewElement);
  FltReleaseResource((PERESOURCE)(a5 + 312));
  if ( inserted )
  {
    v18 = FltSendMessage(Globals, (PFLT_PORT *)(a5 + 80), a3, *a3, 0, 0, 0);
    v17 = v18;
    if ( v18 == -1073741769 )
    {
      v17 = -1073689087;
LABEL_11:
      LOBYTE(v20) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      LOBYTE(v19) = BYTE1(xmmword_14001A3D0) & 0x40;
      if ( (BYTE1(xmmword_14001A3D0) & 0x40) == 0 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_55;
      goto LABEL_13;
    }
    if ( v18 < 0 )
      goto LABEL_11;
    v21 = CallbackData;
    if ( a4 )
    {
      if ( CallbackData )
        MicrosoftTelemetryAssertTriggeredMsgKM(
          "CallbackData is expected to be NULL for GetFileStream Command",
          v19,
          v20,
          0);
      v22 = 3;
    }
    else
    {
      v22 = 2;
    }
    ObjectArray[0] = (PVOID)(a5 + 520);
    ObjectArray[1] = Event;
    v36 = a4;
    v23 = FltCancellableWaitForMultipleObjects(v22, ObjectArray, WaitAny, 0, 0, v21);
    v17 = v23;
    switch ( v23 )
    {
      case -1073741749:
      case -1073741536:
        if ( (BYTE9(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v19) = BYTE9(xmmword_14001A3D0) & 0x40;
          LOBYTE(v20) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_sDdLlqqq(782, v19, v20, *((_QWORD *)WPP_GLOBAL_Control + 8), 3);
        }
        break;
      case 0:
        v17 = -1073689087;
        LOBYTE(v20) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        LOBYTE(v19) = BYTE1(xmmword_14001A3D0) & 0x40;
        if ( (BYTE1(xmmword_14001A3D0) & 0x40) == 0 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_55;
LABEL_13:
        WPP_RECORDER_AND_TRACE_SF_sDdLlqqq(526, v19, v20, *((_QWORD *)WPP_GLOBAL_Control + 8), 2);
LABEL_55:
        FltAcquireResourceExclusive(Resource);
        RtlDeleteElementGenericTableAvl(Table, &Buffer);
        FltReleaseResource(Resource);
        return (unsigned int)v17;
      case 1:
        v17 = PrjfFilterCommandReplyStatus(a3, *(unsigned int *)&Event[24]);
        *a7 = *(_DWORD *)&Event[28];
        if ( v17 < 0 )
        {
          if ( a3[1] == 3 && v17 == -2147483642 )
          {
            LOBYTE(v25) = BYTE9(xmmword_14001A3E0) & 0x40;
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
              || !*((_WORD *)WPP_GLOBAL_Control + 36) )
            {
              v13 = 0;
            }
            if ( (_BYTE)v25 || v13 )
            {
              LOBYTE(v26) = v13;
              WPP_RECORDER_AND_TRACE_SF_sDdLlqqq(1294, v25, v26, PrjfTraceRecorder, 5);
            }
            goto LABEL_55;
          }
          if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0
            || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v25) = BYTE1(xmmword_14001A3D0) & 0x40;
            LOBYTE(v26) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            WPP_RECORDER_AND_TRACE_SF_sDdLlqqq(526, v25, v26, *((_QWORD *)WPP_GLOBAL_Control + 8), 2);
          }
        }
        break;
      case 2:
        if ( a3[1] != 6 )
          MicrosoftTelemetryAssertTriggeredMsgKM("Command type is expected to be GetFileStream", v19, v20, v24);
        v17 = -1073741536;
        if ( (BYTE9(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v19) = BYTE9(xmmword_14001A3D0) & 0x40;
          LOBYTE(v20) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_sDdLlqqq(782, v19, v20, *((_QWORD *)WPP_GLOBAL_Control + 8), 3);
        }
LABEL_54:
        PrjfSendCancelCommandInNewThread(a2);
        goto LABEL_55;
      default:
        if ( v23 < 0 )
        {
          LOBYTE(v20) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          LOBYTE(v19) = BYTE1(xmmword_14001A3D0) & 0x40;
          if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0
            || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            WPP_RECORDER_AND_TRACE_SF_sDdLlqqq(526, v19, v20, *((_QWORD *)WPP_GLOBAL_Control + 8), 2);
          }
        }
        MicrosoftTelemetryAssertTriggeredMsgKM("Unexpected command type", v19, v20, v24);
        goto LABEL_55;
    }
    if ( v17 != -1073741536 && v17 != -1073741749 )
      goto LABEL_55;
    goto LABEL_54;
  }
  v17 = -1073741670;
  if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v15) = BYTE1(xmmword_14001A3D0) & 0x40;
    LOBYTE(v16) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sDdLlqqq(526, v15, v16, *((_QWORD *)WPP_GLOBAL_Control + 8), 2);
  }
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x140033de8  push    rbp
0x140033dea  push    rbx
0x140033deb  push    rsi
0x140033dec  push    rdi
0x140033ded  push    r12
0x140033def  push    r13
0x140033df1  push    r14
0x140033df3  push    r15
0x140033df5  lea     rbp, [rsp-8]
0x140033dfa  sub     rsp, 108h
0x140033e01  mov     rax, cs:__security_cookie
0x140033e08  xor     rax, rsp
0x140033e0b  mov     [rbp+40h+var_50], rax
0x140033e0f  mov     r14, [rbp+40h+arg_20]
0x140033e13  xorps   xmm0, xmm0
0x140033e16  mov     rbx, [rbp+40h+arg_28]
0x140033e1a  xorps   xmm1, xmm1
0x140033e1d  mov     r13, [rbp+40h+arg_30]
0x140033e24  xor     eax, eax
0x140033e26  mov     rdi, r8
0x140033e29  mov     [rbp+40h+CallbackData], rcx
0x140033e2d  mov     r12, rdx
0x140033e30  mov     [rbp+40h+var_70], rax
0x140033e34  xor     esi, esi
0x140033e36  mov     [rbp+40h+var_58], rax
0x140033e3a  xor     r8d, r8d; State
0x140033e3d  mov     [rbp+40h+NewElement], sil
0x140033e41  xor     edx, edx; Type
0x140033e43  lea     rcx, [rbp+40h+Event]; Event
0x140033e47  movups  [rbp+40h+Buffer], xmm0
0x140033e4b  mov     r15, r9
0x140033e4e  movups  xmmword ptr [rbp+40h+Event], xmm1
0x140033e52  movups  xmmword ptr [rbp+40h+Event+10h], xmm1
0x140033e56  movups  xmmword ptr [rbp+40h+ObjectArray], xmm0
0x140033e5a  call    cs:__imp_KeInitializeEvent
0x140033e61  nop     dword ptr [rax+rax+00h]
0x140033e66  test    rbx, rbx
0x140033e69  jz      short loc_140033E71
0x140033e6b  cmp     [r13+0], esi
0x140033e6f  jnz     short loc_140033E76
0x140033e71  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140033e76  mov     eax, [r13+0]
0x140033e7a  mov     esi, 1
0x140033e7f  mov     dword ptr [rbp+40h+Event+1Ch], eax
0x140033e82  mov     eax, [rdi+18h]
0x140033e85  mov     dword ptr [rbp+40h+Buffer], eax
0x140033e88  lea     rax, [rbp+40h+Event]
0x140033e8c  mov     qword ptr [rbp+40h+Buffer+8], rax
0x140033e90  lea     rax, [r14+138h]
0x140033e97  mov     rcx, rax; Resource
0x140033e9a  mov     [rbp+40h+var_70], rbx
0x140033e9e  mov     dword ptr [rbp+40h+Buffer+4], esi
0x140033ea1  mov     [rbp+40h+Resource], rax
0x140033ea5  call    cs:__imp_FltAcquireResourceExclusive
0x140033eac  nop     dword ptr [rax+rax+00h]
0x140033eb1  lea     rax, [r14+1A0h]
0x140033eb8  mov     rcx, rax; Table
0x140033ebb  mov     [rbp+40h+Table], rax
0x140033ebf  lea     r9, [rbp+40h+NewElement]; NewElement
0x140033ec3  lea     r8d, [rsi+0Fh]; BufferSize
0x140033ec7  lea     rdx, [rbp+40h+Buffer]; Buffer
0x140033ecb  call    cs:__imp_RtlInsertElementGenericTableAvl
0x140033ed2  nop     dword ptr [rax+rax+00h]
0x140033ed7  lea     rcx, [r14+138h]; Resource
0x140033ede  mov     rbx, rax
0x140033ee1  call    cs:__imp_FltReleaseResource
0x140033ee8  nop     dword ptr [rax+rax+00h]
0x140033eed  xor     ecx, ecx
0x140033eef  test    rbx, rbx
0x140033ef2  jnz     short loc_140033F6E
0x140033ef4  mov     ebx, 0C000009Ah
0x140033ef9  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140033eff  lea     rax, WPP_RECORDER_INITIALIZED
0x140033f06  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140033f0d  setnz   r8b
0x140033f11  and     dl, 40h
0x140033f14  jnz     short loc_140033F1F
0x140033f16  test    r8b, r8b
0x140033f19  jz      loc_1400343FE
0x140033f1f  mov     eax, [rdi+18h]
0x140033f22  mov     ecx, 20Eh
0x140033f27  mov     r9, cs:WPP_GLOBAL_Control
0x140033f2e  mov     [rsp+140h+var_C8], r15
0x140033f33  mov     [rsp+140h+var_D0], r12
0x140033f38  mov     [rsp+140h+var_D8], r14
0x140033f3d  mov     r9, [r9+40h]
0x140033f41  mov     [rsp+140h+var_E0], eax
0x140033f45  mov     eax, [rdi+4]
0x140033f48  mov     [rsp+140h+var_E8], eax
0x140033f4c  mov     [rsp+140h+var_F0], ebx
0x140033f50  mov     [rsp+140h+var_F8], 0EE4h
0x140033f58  mov     word ptr [rsp+140h+Timeout], 87h
0x140033f5f  mov     byte ptr [rsp+140h+ReplyBuffer], 2
0x140033f64  call    WPP_RECORDER_AND_TRACE_SF_sDdLlqqq
0x140033f69  jmp     loc_1400343FE
0x140033f6e  mov     r9d, [rdi]; SenderBufferLength
0x140033f71  lea     rdx, [r14+50h]; ClientPort
0x140033f75  mov     [rsp+140h+Timeout], rcx; Timeout
0x140033f7a  mov     r8, rdi; SenderBuffer
0x140033f7d  mov     [rsp+140h+ReplyLength], rcx; ReplyLength
0x140033f82  mov     [rsp+140h+ReplyBuffer], rcx; ReplyBuffer
0x140033f87  mov     rcx, cs:Globals; Filter
0x140033f8e  call    cs:__imp_FltSendMessage
0x140033f95  nop     dword ptr [rax+rax+00h]
0x140033f9a  mov     ebx, eax
0x140033f9c  cmp     eax, 0C0000037h
0x140033fa1  jnz     short loc_140033FAA
0x140033fa3  mov     ebx, 0C000CE01h
0x140033fa8  jmp     short loc_140033FB1
0x140033faa  xor     r9d, r9d
0x140033fad  test    eax, eax
0x140033faf  jns     short loc_140034026
0x140033fb1  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140033fb7  lea     rax, WPP_RECORDER_INITIALIZED
0x140033fbe  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140033fc5  setnz   r8b
0x140033fc9  and     dl, 40h
0x140033fcc  jnz     short loc_140033FD7
0x140033fce  test    r8b, r8b
0x140033fd1  jz      loc_1400343CA
0x140033fd7  mov     eax, [rdi+18h]
0x140033fda  mov     [rsp+140h+var_C8], r15
0x140033fdf  mov     [rsp+140h+var_D0], r12
0x140033fe4  mov     [rsp+140h+var_D8], r14
0x140033fe9  mov     [rsp+140h+var_E0], eax
0x140033fed  mov     eax, [rdi+4]
0x140033ff0  mov     [rsp+140h+var_E8], eax
0x140033ff4  mov     [rsp+140h+var_F0], ebx
0x140033ff8  mov     [rsp+140h+var_F8], 0F0Ah
0x140034000  mov     word ptr [rsp+140h+Timeout], 88h
0x140034007  mov     r9, cs:WPP_GLOBAL_Control
0x14003400e  mov     ecx, 20Eh
0x140034013  mov     byte ptr [rsp+140h+ReplyBuffer], 2
0x140034018  mov     r9, [r9+40h]
0x14003401c  call    WPP_RECORDER_AND_TRACE_SF_sDdLlqqq
0x140034021  jmp     loc_1400343CA
0x140034026  mov     rbx, [rbp+40h+CallbackData]
0x14003402a  test    r15, r15
0x14003402d  jz      short loc_14003404A
0x14003402f  test    rbx, rbx
0x140034032  jz      short loc_140034043
0x140034034  lea     rcx, aCallbackdataIs; "CallbackData is expected to be NULL for"...
0x14003403b  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140034040  xor     r9d, r9d
0x140034043  mov     ecx, 3
0x140034048  jmp     short loc_14003404F
0x14003404a  mov     ecx, 2; Count
0x14003404f  lea     rax, [r14+208h]
0x140034056  mov     [rsp+140h+ReplyLength], rbx; CallbackData
0x14003405b  mov     [rbp+40h+ObjectArray], rax
0x14003405f  lea     rdx, [rbp+40h+ObjectArray]; ObjectArray
0x140034063  lea     rax, [rbp+40h+Event]
0x140034067  mov     [rsp+140h+ReplyBuffer], r9; WaitBlockArray
0x14003406c  xor     r9d, r9d; Timeout
0x14003406f  mov     [rbp+40h+ObjectArray+8], rax
0x140034073  mov     r8d, esi; WaitType
0x140034076  mov     [rbp+40h+var_58], r15
0x14003407a  call    cs:__imp_FltCancellableWaitForMultipleObjects
0x140034081  nop     dword ptr [rax+rax+00h]
0x140034086  mov     ebx, eax
0x140034088  cmp     eax, 0C000004Bh
0x14003408d  jz      loc_140034343
0x140034093  cmp     eax, 0C0000120h
0x140034098  jz      loc_140034343
0x14003409e  test    eax, eax
0x1400340a0  jz      loc_1400342E3
0x1400340a6  cmp     eax, esi
0x1400340a8  jz      loc_1400341C4
0x1400340ae  cmp     eax, 2
0x1400340b1  jz      loc_140034138
0x1400340b7  test    eax, eax
0x1400340b9  jns     short loc_140034127
0x1400340bb  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x1400340c1  lea     rax, WPP_RECORDER_INITIALIZED
0x1400340c8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400340cf  setnz   r8b
0x1400340d3  and     dl, 40h
0x1400340d6  jnz     short loc_1400340DD
0x1400340d8  test    r8b, r8b
0x1400340db  jz      short loc_140034127
0x1400340dd  mov     eax, [rdi+18h]
0x1400340e0  mov     ecx, 20Eh
0x1400340e5  mov     r9, cs:WPP_GLOBAL_Control
0x1400340ec  mov     [rsp+140h+var_C8], r15
0x1400340f1  mov     [rsp+140h+var_D0], r12
0x1400340f6  mov     [rsp+140h+var_D8], r14
0x1400340fb  mov     r9, [r9+40h]
0x1400340ff  mov     [rsp+140h+var_E0], eax
0x140034103  mov     eax, [rdi+4]
0x140034106  mov     [rsp+140h+var_E8], eax
0x14003410a  mov     [rsp+140h+var_F0], ebx
0x14003410e  mov     [rsp+140h+var_F8], 0F99h
0x140034116  mov     word ptr [rsp+140h+Timeout], 8Eh
0x14003411d  mov     byte ptr [rsp+140h+ReplyBuffer], 2
0x140034122  call    WPP_RECORDER_AND_TRACE_SF_sDdLlqqq
0x140034127  lea     rcx, aUnexpectedComm; "Unexpected command type"
0x14003412e  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140034133  jmp     loc_1400343CA
0x140034138  cmp     dword ptr [rdi+4], 6
0x14003413c  jz      short loc_14003414A
0x14003413e  lea     rcx, aCommandTypeIsE; "Command type is expected to be GetFileS"...
0x140034145  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14003414a  mov     ebx, 0C0000120h
0x14003414f  mov     dl, byte ptr cs:xmmword_14001A3D0+9
0x140034155  lea     rax, WPP_RECORDER_INITIALIZED
0x14003415c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140034163  setnz   r8b
0x140034167  and     dl, 40h
0x14003416a  jnz     short loc_140034175
0x14003416c  test    r8b, r8b
0x14003416f  jz      loc_1400343BF
0x140034175  mov     eax, [rdi+18h]
0x140034178  mov     ecx, 30Eh
0x14003417d  mov     r9, cs:WPP_GLOBAL_Control
0x140034184  mov     [rsp+140h+var_C8], r15
0x140034189  mov     [rsp+140h+var_D0], r12
0x14003418e  mov     [rsp+140h+var_D8], r14
0x140034193  mov     r9, [r9+40h]
0x140034197  mov     [rsp+140h+var_E0], eax
0x14003419b  mov     eax, [rdi+4]
0x14003419e  mov     [rsp+140h+var_E8], eax
0x1400341a2  mov     [rsp+140h+var_F0], ebx
0x1400341a6  mov     [rsp+140h+var_F8], 0F87h
0x1400341ae  mov     word ptr [rsp+140h+Timeout], 8Dh
0x1400341b5  mov     byte ptr [rsp+140h+ReplyBuffer], 3
0x1400341ba  call    WPP_RECORDER_AND_TRACE_SF_sDdLlqqq
0x1400341bf  jmp     loc_1400343BF
0x1400341c4  mov     edx, dword ptr [rbp+40h+Event+18h]
0x1400341c7  mov     rcx, rdi
0x1400341ca  call    PrjfFilterCommandReplyStatus
0x1400341cf  mov     ebx, eax
0x1400341d1  xor     ecx, ecx
0x1400341d3  mov     eax, dword ptr [rbp+40h+Event+1Ch]
0x1400341d6  mov     [r13+0], eax
0x1400341da  test    ebx, ebx
0x1400341dc  jns     loc_1400343AF
0x1400341e2  mov     r9d, [rdi+4]
0x1400341e6  cmp     r9d, 3
0x1400341ea  jnz     loc_140034280
0x1400341f0  mov     r10d, 80000006h
0x1400341f6  cmp     ebx, r10d
0x1400341f9  jnz     loc_140034280
0x1400341ff  mov     dl, byte ptr cs:xmmword_14001A3E0+9
0x140034205  lea     rax, WPP_RECORDER_INITIALIZED
0x14003420c  and     dl, 40h
0x14003420f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140034216  jz      short loc_140034225
0x140034218  mov     rax, cs:WPP_GLOBAL_Control
0x14003421f  cmp     [rax+48h], cx
0x140034223  jnz     short loc_140034228
0x140034225  mov     sil, cl
0x140034228  test    dl, dl
0x14003422a  jnz     short loc_140034235
0x14003422c  test    sil, sil
0x14003422f  jz      loc_1400343CA
0x140034235  mov     eax, [rdi+18h]
0x140034238  mov     ecx, 50Eh
0x14003423d  mov     r9, cs:_PrjfTraceRecorder
0x140034244  mov     r8b, sil
0x140034247  mov     [rsp+140h+var_C8], r15
0x14003424c  mov     [rsp+140h+var_D0], r12
0x140034251  mov     [rsp+140h+var_D8], r14
0x140034256  mov     [rsp+140h+var_E0], eax
0x14003425a  mov     [rsp+140h+var_E8], 3
0x140034262  mov     [rsp+140h+var_F0], r10d
0x140034267  mov     [rsp+140h+var_F8], 0F61h
0x14003426f  mov     word ptr [rsp+140h+Timeout], 8Bh
0x140034276  mov     byte ptr [rsp+140h+ReplyBuffer], 5
0x14003427b  jmp     loc_14003401C
0x140034280  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140034286  lea     rax, WPP_RECORDER_INITIALIZED
0x14003428d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140034294  setnz   r8b
0x140034298  and     dl, 40h
0x14003429b  jnz     short loc_1400342A6
0x14003429d  test    r8b, r8b
0x1400342a0  jz      loc_1400343AF
0x1400342a6  mov     eax, [rdi+18h]
0x1400342a9  mov     ecx, 20Eh
0x1400342ae  mov     [rsp+140h+var_C8], r15
0x1400342b3  mov     [rsp+140h+var_D0], r12
0x1400342b8  mov     [rsp+140h+var_D8], r14
0x1400342bd  mov     [rsp+140h+var_E0], eax
0x1400342c1  mov     [rsp+140h+var_E8], r9d
0x1400342c6  mov     [rsp+140h+var_F0], ebx
0x1400342ca  mov     [rsp+140h+var_F8], 0F6Fh
0x1400342d2  mov     word ptr [rsp+140h+Timeout], 8Ch
0x1400342d9  mov     byte ptr [rsp+140h+ReplyBuffer], 2
0x1400342de  jmp     loc_14003439F
0x1400342e3  mov     ebx, 0C000CE01h
0x1400342e8  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x1400342ee  lea     rax, WPP_RECORDER_INITIALIZED
0x1400342f5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400342fc  setnz   r8b
0x140034300  and     dl, 40h
0x140034303  jnz     short loc_14003430E
0x140034305  test    r8b, r8b
0x140034308  jz      loc_1400343CA
0x14003430e  mov     eax, [rdi+18h]
0x140034311  mov     [rsp+140h+var_C8], r15
  ... truncated ...
```
