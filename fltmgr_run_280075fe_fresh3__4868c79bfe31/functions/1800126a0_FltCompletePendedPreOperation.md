# FltCompletePendedPreOperation

- ea: `0x1800126a0`
- end: `0x1800128e1`
- name: `FltCompletePendedPreOperation`
- size: `577`
- prototype: `void __stdcall(PFLT_CALLBACK_DATA CallbackData, FLT_PREOP_CALLBACK_STATUS CallbackStatus, PVOID Context)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180002100`
- `0x18007dd60`

## callees

- `0x180007500`
- `0x180009f20`
- `0x1800126a0`
- `0x1800128f0`
- `0x180019800`
- `0x18001b2a0`
- `0x18001f4c0`
- `0x1800247a0`
- `0x18006c0c0`

## import_xrefs

- `ntoskrnl!IoPropagateActivityIdToThread` at `0x180012766`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x180012766`
- `ntoskrnl!KeSetEvent` at `0x18001281f`
- `ntoskrnl!KeSetEvent` at `0x18001281f`
- `ntoskrnl!IoClearActivityIdThread` at `0x1800127c0`
- `ntoskrnl!IoClearActivityIdThread` at `0x1800127c0`

## string_xrefs

- `0x18001283a`: `FltCompletePendedPreOperation`

## pseudocode

```c
void __stdcall FltCompletePendedPreOperation(
        PFLT_CALLBACK_DATA CallbackData,
        FLT_PREOP_CALLBACK_STATUS CallbackStatus,
        PVOID Context)
{
  ULONG_PTR *p_Information; // r10
  struct _LIST_ENTRY *Flink; // rax
  PVOID v7; // rdi
  unsigned int v8; // esi
  unsigned int v9; // eax
  __int64 v10; // r8
  unsigned int v11; // ebx
  const char *v12; // rcx
  int v13; // edx
  _OWORD v14[3]; // [rsp+40h] [rbp-9h] BYREF
  __int64 v15; // [rsp+70h] [rbp+27h] BYREF
  __int128 v16; // [rsp+78h] [rbp+2Fh] BYREF

  p_Information = &CallbackData[-3].IoStatus.Information;
  Flink = CallbackData[-2].QueueLinks.Flink;
  memset(v14, 0, sizeof(v14));
  v7 = Context;
  *(_QWORD *)&v14[0] = Flink[4].Flink[5].Flink;
  *((_QWORD *)&v14[0] + 1) = *(_QWORD *)&CallbackData[-3].RequestorMode;
  *(_QWORD *)&v14[1] = (char *)CallbackData - 232;
  *(__m128i *)((char *)&v14[1] + 8) = _mm_load_si128((const __m128i *)&_xmm);
  DWORD2(v14[2]) = 0;
  if ( (byte_1800404C1 & 0x10) != 0 )
  {
    v12 = "SYNC";
    if ( (*((_DWORD *)p_Information + 1) & 8) == 0 )
      v12 = "NotSYNC";
    McTemplateU0sdpps_EtwWriteTransfer(
      (_DWORD)v12,
      (unsigned int)PendingSup_c626,
      (unsigned int)"FltCompletePendedPreOperation",
      CallbackData->Iopb->MajorFunction,
      (char)p_Information,
      p_Information[10],
      (__int64)v12);
    p_Information = *(ULONG_PTR **)&v14[1];
  }
  if ( *(_QWORD *)(qword_18003FD98 + 24) || *(_QWORD *)(qword_18003FD98 + 32) )
  {
    LOBYTE(Context) = 1;
    FltpPerfTraceOperationCallback(p_Information, p_Information[10], Context);
    p_Information = *(ULONG_PTR **)&v14[1];
  }
  if ( p_Information[16] )
  {
    p_Information[16] = 0;
    --*(_BYTE *)(*(_QWORD *)&v14[1] + 15LL);
    p_Information = *(ULONG_PTR **)&v14[1];
  }
  if ( (*((_DWORD *)p_Information + 1) & 8) != 0 )
  {
    *((_DWORD *)p_Information + 34) = CallbackStatus;
    *(_QWORD *)(*(_QWORD *)&v14[1] + 120LL) = v7;
    KeSetEvent((PRKEVENT)(*(_QWORD *)&v14[1] + 24LL), 0, 0);
  }
  else
  {
    v15 = 0;
    v16 = 0;
    v8 = IoPropagateActivityIdToThread(p_Information[6], &v16, &v15);
    v9 = FltpInternalCompletePendedPreOperation((__int64)v14, CallbackStatus, (__int64)v7);
    v11 = v9;
    if ( v9 == 259 )
    {
      if ( *(_QWORD *)&v14[2] )
        FltpProcessOperationStatusCallbacks(v14, 259);
    }
    else
    {
      if ( !v9 && *(_BYTE *)(*(_QWORD *)&v14[1] + 12LL) == 13 )
      {
        v13 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)&v14[1] + 248LL) + 40LL);
        if ( v13 == 606820 || v13 == 623208 )
        {
          v11 = FltpCopyOffloadCapable(*(struct _DEVICE_OBJECT **)(*(_QWORD *)&v14[0] + 64LL), v13);
          if ( (int)FltpDbgStatus(v11, "minkernel\\fs\\filtermgr\\filter\\pendingsup.c", 718, 0) < 0 )
            *(_DWORD *)(*(_QWORD *)&v14[1] + 256LL) = v11;
        }
      }
      LOBYTE(v10) = 1;
      FltpLegacyProcessingAfterPreCallbacksCompleted(v14, v11, v10);
    }
    if ( (int)FltpDbgStatus(v8, "minkernel\\fs\\filtermgr\\filter\\pendingsup.c", 749, 0) >= 0 )
      IoClearActivityIdThread(v15);
  }
}

```

## disassembly

```asm
0x1800126a0  mov     [rsp-8+arg_18], rbx
0x1800126a5  push    rbp
0x1800126a6  push    rsi
0x1800126a7  push    rdi
0x1800126a8  lea     rbp, [rsp-47h]
0x1800126ad  sub     rsp, 90h
0x1800126b4  mov     rax, cs:__security_cookie
0x1800126bb  xor     rax, rsp
0x1800126be  mov     [rbp+57h+var_18], rax
0x1800126c2  lea     r10, [rcx-0E8h]
0x1800126c9  xorps   xmm0, xmm0
0x1800126cc  mov     rax, [r10+68h]
0x1800126d0  xor     esi, esi
0x1800126d2  test    cs:byte_1800404C1, 10h
0x1800126d9  mov     ebx, edx
0x1800126db  movups  [rbp+57h+var_60], xmm0
0x1800126df  mov     rdx, rcx
0x1800126e2  mov     rdi, r8
0x1800126e5  movups  [rbp+57h+var_50], xmm0
0x1800126e9  movups  [rbp+57h+var_40], xmm0
0x1800126ed  mov     rcx, [rax+40h]
0x1800126f1  movdqa  xmm0, cs:__xmm@0000000000000000ffffffffffffffff
0x1800126f9  mov     rax, [rcx+50h]
0x1800126fd  mov     qword ptr [rbp+57h+var_60], rax
0x180012701  mov     rax, [r10+30h]
0x180012705  mov     qword ptr [rbp+57h+var_60+8], rax
0x180012709  mov     qword ptr [rbp+57h+var_50], r10
0x18001270d  movdqu  [rbp+57h+var_50+8], xmm0
0x180012712  mov     dword ptr [rbp+57h+var_40+8], esi
0x180012715  jnz     loc_18001282D
0x18001271b  mov     rax, cs:qword_18003FD98
0x180012722  cmp     [rax+18h], rsi
0x180012726  jnz     loc_18001287D
0x18001272c  cmp     [rax+20h], rsi
0x180012730  jnz     loc_18001287D
0x180012736  cmp     [r10+80h], rsi
0x18001273d  jnz     loc_180012895
0x180012743  mov     eax, [r10+4]
0x180012747  test    al, 8
0x180012749  jnz     loc_180012803
0x18001274f  xorps   xmm0, xmm0
0x180012752  mov     [rbp+57h+var_30], rsi
0x180012756  movups  [rbp+57h+var_28], xmm0
0x18001275a  mov     rcx, [r10+30h]
0x18001275e  lea     r8, [rbp+57h+var_30]
0x180012762  lea     rdx, [rbp+57h+var_28]
0x180012766  call    cs:__imp_IoPropagateActivityIdToThread
0x18001276d  nop     dword ptr [rax+rax+00h]
0x180012772  mov     r8, rdi
0x180012775  lea     rcx, [rbp+57h+var_60]
0x180012779  mov     edx, ebx
0x18001277b  mov     esi, eax
0x18001277d  call    FltpInternalCompletePendedPreOperation
0x180012782  mov     ebx, eax
0x180012784  cmp     eax, 103h
0x180012789  jz      short loc_1800127EC
0x18001278b  test    eax, eax
0x18001278d  jz      loc_1800128AC
0x180012793  mov     r8b, 1
0x180012796  lea     rcx, [rbp+57h+var_60]
0x18001279a  mov     edx, ebx
0x18001279c  call    FltpLegacyProcessingAfterPreCallbacksCompleted
0x1800127a1  mov     r8d, 2EDh
0x1800127a7  lea     rdx, aMinkernelFsFil_2; "minkernel\\fs\\filtermgr\\filter\\pendi"...
0x1800127ae  xor     r9d, r9d
0x1800127b1  mov     ecx, esi
0x1800127b3  call    FltpDbgStatus
0x1800127b8  test    eax, eax
0x1800127ba  js      short loc_1800127CC
0x1800127bc  mov     rcx, [rbp+57h+var_30]
0x1800127c0  call    cs:__imp_IoClearActivityIdThread
0x1800127c7  nop     dword ptr [rax+rax+00h]
0x1800127cc  mov     rcx, [rbp+57h+var_18]
0x1800127d0  xor     rcx, rsp; StackCookie
0x1800127d3  call    __security_check_cookie
0x1800127d8  mov     rbx, [rsp+0A0h+arg_18]
0x1800127e0  add     rsp, 90h
0x1800127e7  pop     rdi
0x1800127e8  pop     rsi
0x1800127e9  pop     rbp
0x1800127ea  retn
0x1800127ec  cmp     qword ptr [rbp+57h+var_40], 0
0x1800127f1  jz      short loc_1800127A1
0x1800127f3  mov     edx, 103h
0x1800127f8  lea     rcx, [rbp+57h+var_60]
0x1800127fc  call    FltpProcessOperationStatusCallbacks
0x180012801  jmp     short loc_1800127A1
0x180012803  mov     [r10+88h], ebx
0x18001280a  xor     r8d, r8d; Wait
0x18001280d  mov     rax, qword ptr [rbp+57h+var_50]
0x180012811  xor     edx, edx; Increment
0x180012813  mov     [rax+78h], rdi
0x180012817  mov     rcx, qword ptr [rbp+57h+var_50]
0x18001281b  add     rcx, 18h; Event
0x18001281f  call    cs:__imp_KeSetEvent
0x180012826  nop     dword ptr [rax+rax+00h]
0x18001282b  jmp     short loc_1800127CC
0x18001282d  mov     eax, [r10+4]
0x180012831  lea     rcx, aSync; "SYNC"
0x180012838  test    al, 8
0x18001283a  lea     r8, aFltcompletepen; "FltCompletePendedPreOperation"
0x180012841  lea     rax, aNotsync; "NotSYNC"
0x180012848  cmovz   rcx, rax
0x18001284c  mov     rax, [rdx+10h]
0x180012850  mov     [rsp+0A0h+var_70], rcx
0x180012855  lea     rdx, PendingSup_c626
0x18001285c  movzx   r9d, byte ptr [rax+4]
0x180012861  mov     rax, [r10+50h]
0x180012865  mov     [rsp+0A0h+var_78], rax
0x18001286a  mov     [rsp+0A0h+var_80], r10
0x18001286f  call    McTemplateU0sdpps_EtwWriteTransfer
0x180012874  mov     r10, qword ptr [rbp+57h+var_50]
0x180012878  jmp     loc_18001271B
0x18001287d  mov     rdx, [r10+50h]
0x180012881  mov     r8b, 1
0x180012884  mov     rcx, r10
0x180012887  call    FltpPerfTraceOperationCallback
0x18001288c  mov     r10, qword ptr [rbp+57h+var_50]
0x180012890  jmp     loc_180012736
0x180012895  mov     [r10+80h], rsi
0x18001289c  mov     rax, qword ptr [rbp+57h+var_50]
0x1800128a0  dec     byte ptr [rax+0Fh]
0x1800128a3  mov     r10, qword ptr [rbp+57h+var_50]
0x1800128a7  jmp     loc_180012743
0x1800128ac  mov     rcx, qword ptr [rbp+57h+var_50]
0x1800128b0  cmp     byte ptr [rcx+0Ch], 0Dh
0x1800128b4  jnz     loc_180012793
0x1800128ba  mov     rcx, [rcx+0F8h]
0x1800128c1  mov     edx, [rcx+28h]
0x1800128c4  cmp     edx, 94264h
0x1800128ca  jz      loc_180025DDE
0x1800128d0  cmp     edx, 98268h
0x1800128d6  jnz     loc_180012793
0x1800128dc  jmp     loc_180025DDE
0x180025dde  mov     rcx, qword ptr [rbp+57h+var_60]
0x180025de2  mov     rcx, [rcx+40h]
0x180025de6  call    FltpCopyOffloadCapable
0x180025deb  mov     r8d, 2CEh
0x180025df1  lea     rdx, aMinkernelFsFil_2; "minkernel\\fs\\filtermgr\\filter\\pendi"...
0x180025df8  xor     r9d, r9d
0x180025dfb  mov     ecx, eax
0x180025dfd  mov     ebx, eax
0x180025dff  call    FltpDbgStatus
0x180025e04  test    eax, eax
0x180025e06  jns     loc_180012793
0x180025e0c  mov     rax, qword ptr [rbp+57h+var_50]
0x180025e10  mov     [rax+100h], ebx
0x180025e16  jmp     loc_180012793
```
