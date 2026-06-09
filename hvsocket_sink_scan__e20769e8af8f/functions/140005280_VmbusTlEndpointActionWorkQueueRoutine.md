# VmbusTlEndpointActionWorkQueueRoutine

- ea: `0x140005280`
- end: `0x1400056d2`
- name: `VmbusTlEndpointActionWorkQueueRoutine`
- size: `1106`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140001008`
- `0x14000309c`
- `0x140003cec`
- `0x14000440c`
- `0x1400045c0`
- `0x140004690`
- `0x140004750`
- `0x140005280`
- `0x140009834`
- `0x140009b84`
- `0x14000a048`
- `0x14000bfa0`
- `0x14000bfe0`
- `0x140019110`
- `0x14001f1ec`
- `0x14001f464`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140005516`
- `ntoskrnl!KeWaitForSingleObject` at `0x140005516`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400054cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000567a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000569c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400054cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000567a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000569c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400054b2`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140005664`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400054b2`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140005664`
- `ntoskrnl!PsGetProcessId` at `0x140005548`
- `ntoskrnl!PsGetProcessId` at `0x140005548`

## string_xrefs

- `0x1400053e5`: `VmbusTlCommonEndpointCleanup: Cleaning up endpoint.`
- `0x140005435`: `VmbusTlCommonEndpointCleanup: connection aborted.`
- `0x140005464`: `VmbusTlCommonEndpointCleanup`

## pseudocode

```c
void __fastcall VmbusTlEndpointActionWorkQueueRoutine(PVOID *P)
{
  PVOID *v2; // r14
  PVOID *v3; // r13
  PVOID *v4; // rbx
  __int64 v5; // rsi
  char v6; // r12
  int *v7; // rbx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  void (__fastcall *v13)(PVOID, _QWORD); // rdi
  PVOID v14; // rbx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  void (__fastcall *v18)(_QWORD, _QWORD); // rax
  signed __int64 v19; // rax
  bool v20; // cc
  signed __int64 v21; // rax
  void (__fastcall *v22)(__int64); // rax
  int v23; // r8d
  int v24; // r9d
  struct _KPROCESS *v25; // rcx
  unsigned int ProcessId; // eax
  bool v27; // al
  signed __int64 v28; // rax
  signed __int64 v29; // rax
  void (__fastcall *v30)(__int64); // rax
  bool v31; // [rsp+30h] [rbp-79h] BYREF
  __int64 v32; // [rsp+38h] [rbp-71h] BYREF
  __int64 v33[14]; // [rsp+40h] [rbp-69h] BYREF

  do
  {
    v2 = P;
    v3 = P;
    v4 = P;
    P = (PVOID *)*P;
    v5 = (__int64)v2[2];
    v6 = *((_BYTE *)v2 + 48);
    if ( (unsigned int)dword_140013058 <= 4 )
    {
      v7 = (int *)(v4 + 1);
    }
    else
    {
      v7 = (int *)(v2 + 1);
      HvsocketTraceEndpointEvent("VmbusTlEndpointActionWorkQueueRoutine", v2[2], *((unsigned int *)v2 + 2));
    }
    v8 = *v7;
    if ( *v7 > 6 )
    {
      v15 = v8 - 7;
      if ( v15 )
      {
        v16 = v15 - 1;
        if ( v16 )
        {
          v17 = v16 - 1;
          if ( v17 )
          {
            if ( v17 == 1 && *(_QWORD *)(v5 + 696) )
              (*(void (**)(void))(*(_QWORD *)(*(_QWORD *)(v5 + 736) + 504LL) + 80LL))();
          }
          else
          {
            if ( (unsigned int)dword_140013058 > 4 )
              HvsocketTraceEndpointMessage("VmbusTlCommonEndpointCleanup: Cleaning up endpoint.", v5);
            if ( *(_DWORD *)(v5 + 104) == 2 )
              VmbusTlShutdownTransport(v5);
            if ( *(_DWORD *)(v5 + 104) == 3 )
              VmbusTlDissociateListenerFromPartition(v5);
            v18 = *(void (__fastcall **)(_QWORD, _QWORD))(v5 + 256);
            if ( v18 )
              v18(*(_QWORD *)(v5 + 264), 0);
            if ( (unsigned int)dword_140013058 > 4 )
              HvsocketTraceEndpointMessage("VmbusTlCommonEndpointCleanup: connection aborted.", v5);
            if ( (unsigned int)dword_140013058 > 5 )
              HvsocketTraceReferenceCount(
                (unsigned int)"VmbusTlCommonEndpointCleanup",
                553,
                v5,
                *(_QWORD *)(v5 + 8),
                (__int64)"Dereference object");
            v19 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v5 + 8), 0xFFFFFFFFFFFFFFFFuLL);
            v20 = v19 <= 1;
            v21 = v19 - 1;
            if ( v20 )
            {
              if ( v21 )
                __fastfail(0xEu);
              v22 = *(void (__fastcall **)(__int64))(v5 + 80);
              if ( v22 )
                v22(v5);
              if ( *(_DWORD *)(v5 + 88) == 1 )
              {
                ExFreePoolWithTag((PVOID)v5, 0x69706E56u);
              }
              else if ( *(_DWORD *)(v5 + 88) == 2 )
              {
                ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v5 + 96), (PVOID)v5);
              }
            }
          }
        }
        else
        {
          HvSocketConnectionTimeOut((PVOID)v5);
        }
      }
      else if ( *(_QWORD *)(v5 + 736) )
      {
        KeWaitForSingleObject((PVOID)(v5 + 712), Executive, 0, 0, 0);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)(v5 + 736) + 160LL))(v5);
        v25 = *(struct _KPROCESS **)(v5 + 272);
        if ( v25 )
          ProcessId = (unsigned int)PsGetProcessId(v25);
        else
          ProcessId = 0;
        if ( (unsigned int)dword_140013058 > 4 )
        {
          v32 = ProcessId;
          v33[4] = (__int64)"A Hyper-V socket connection has disconnected.";
          v33[6] = (__int64)&v32;
          v33[5] = 46;
          v33[8] = v5 + 140;
          v33[10] = v5 + 156;
          v27 = (*(_DWORD *)(v5 + 516) & 2) != 0;
          v33[7] = 8;
          v31 = v27;
          v33[12] = (__int64)&v31;
          v33[9] = 16;
          v33[11] = 16;
          v33[13] = 1;
          tlgWriteTransfer_EtwWriteTransfer((int)&dword_140013058, (int)&byte_140011389, v23, v24, 7u, (__int64)v33);
        }
        VmbusTlDissociateConnectionFromPartition(v5);
      }
    }
    else if ( v8 == 6 )
    {
      VmbusTlShutdownTransport(v5);
    }
    else
    {
      v9 = v8 - 1;
      if ( v9 )
      {
        v10 = v9 - 1;
        if ( v10 )
        {
          v11 = v10 - 1;
          if ( v11 )
          {
            v12 = v11 - 1;
            if ( v12 )
            {
              if ( v12 == 1 )
                VmbusTlSendConsumptionNoticeImpl(v5);
            }
            else
            {
              VmbusTlSendDisconnectRequestImpl(v5);
            }
          }
          else
          {
            VmbusTlProcessClientDisconnectRequest(v5, *((_BYTE *)v3 + 24));
          }
        }
        else
        {
          v13 = (void (__fastcall *)(PVOID, _QWORD))v3[3];
          v14 = v3[4];
          VmbusTlpReleaseIndicationList((KSPIN_LOCK *)v5, v2[5], 1);
          v13(v14, 0);
        }
      }
      else
      {
        VmbusTlDeliverDataIndications(v5, 1);
      }
    }
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (unsigned int)"VmbusTlEndpointActionWorkQueueRoutine",
        653,
        v5,
        *(_QWORD *)(v5 + 8),
        (__int64)"Dereference object");
    v28 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v5 + 8), 0xFFFFFFFFFFFFFFFFuLL);
    v20 = v28 <= 1;
    v29 = v28 - 1;
    if ( v20 )
    {
      if ( v29 )
        __fastfail(0xEu);
      v30 = *(void (__fastcall **)(__int64))(v5 + 80);
      if ( v30 )
        v30(v5);
      if ( *(_DWORD *)(v5 + 88) == 1 )
      {
        ExFreePoolWithTag((PVOID)v5, 0x69706E56u);
      }
      else if ( *(_DWORD *)(v5 + 88) == 2 )
      {
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v5 + 96), (PVOID)v5);
      }
    }
    if ( v6 )
      ExFreePoolWithTag(v3, 0x69706E56u);
  }
  while ( P );
}

```

## disassembly

```asm
0x140005280  push    rbp
0x140005282  push    rbx
0x140005283  push    rsi
0x140005284  push    rdi
0x140005285  push    r12
0x140005287  push    r13
0x140005289  push    r14
0x14000528b  push    r15
0x14000528d  lea     rbp, [rsp-1Fh]
0x140005292  sub     rsp, 0C8h
0x140005299  mov     rax, cs:__security_cookie
0x1400052a0  xor     rax, rsp
0x1400052a3  mov     [rbp+57h+var_50], rax
0x1400052a7  mov     r15, rcx
0x1400052aa  xor     edi, edi
0x1400052ac  mov     eax, cs:dword_140013058
0x1400052b2  mov     r14, r15
0x1400052b5  mov     r13, r15
0x1400052b8  mov     rbx, r15
0x1400052bb  mov     r15, [r15]
0x1400052be  mov     rsi, [r14+10h]
0x1400052c2  mov     r12b, [r14+30h]
0x1400052c6  cmp     eax, 4
0x1400052c9  jbe     short loc_1400052E3
0x1400052cb  lea     rbx, [r14+8]
0x1400052cf  mov     rdx, rsi
0x1400052d2  mov     r8d, [rbx]
0x1400052d5  lea     rcx, aVmbustlendpoin_3; "VmbusTlEndpointActionWorkQueueRoutine"
0x1400052dc  call    HvsocketTraceEndpointEvent
0x1400052e1  jmp     short loc_1400052E7
0x1400052e3  add     rbx, 8
0x1400052e7  mov     ecx, [rbx]
0x1400052e9  cmp     ecx, 6
0x1400052ec  jg      loc_140005387
0x1400052f2  jz      loc_14000537A
0x1400052f8  sub     ecx, 1
0x1400052fb  jz      short loc_14000536B
0x1400052fd  sub     ecx, 1
0x140005300  jz      short loc_140005340
0x140005302  sub     ecx, 1
0x140005305  jz      short loc_14000532F
0x140005307  sub     ecx, 1
0x14000530a  jz      short loc_140005322
0x14000530c  cmp     ecx, 1
0x14000530f  jnz     loc_1400055FB
0x140005315  mov     rcx, rsi
0x140005318  call    VmbusTlSendConsumptionNoticeImpl
0x14000531d  jmp     loc_1400055FB
0x140005322  mov     rcx, rsi
0x140005325  call    VmbusTlSendDisconnectRequestImpl
0x14000532a  jmp     loc_1400055FB
0x14000532f  mov     dl, [r13+18h]
0x140005333  mov     rcx, rsi
0x140005336  call    VmbusTlProcessClientDisconnectRequest
0x14000533b  jmp     loc_1400055FB
0x140005340  mov     rdx, [r14+28h]
0x140005344  mov     r8b, 1
0x140005347  mov     rdi, [r13+18h]
0x14000534b  mov     rcx, rsi
0x14000534e  mov     rbx, [r13+20h]
0x140005352  call    VmbusTlpReleaseIndicationList
0x140005357  xor     edx, edx
0x140005359  mov     rcx, rbx
0x14000535c  mov     rax, rdi
0x14000535f  call    _guard_dispatch_icall
0x140005364  xor     edi, edi
0x140005366  jmp     loc_1400055FB
0x14000536b  mov     dl, 1
0x14000536d  mov     rcx, rsi
0x140005370  call    VmbusTlDeliverDataIndications
0x140005375  jmp     loc_1400055FB
0x14000537a  mov     rcx, rsi
0x14000537d  call    VmbusTlShutdownTransport
0x140005382  jmp     loc_1400055FB
0x140005387  sub     ecx, 7
0x14000538a  jz      loc_1400054F5
0x140005390  sub     ecx, 1
0x140005393  jz      loc_1400054E8
0x140005399  sub     ecx, 1
0x14000539c  jz      short loc_1400053D7
0x14000539e  cmp     ecx, 1
0x1400053a1  jnz     loc_1400055FB
0x1400053a7  mov     rcx, [rsi+2B8h]
0x1400053ae  mov     rax, [rsi+70h]
0x1400053b2  test    rcx, rcx
0x1400053b5  jz      loc_1400055FB
0x1400053bb  mov     rax, [rsi+2E0h]
0x1400053c2  mov     rdx, [rax+1F8h]
0x1400053c9  mov     rax, [rdx+50h]
0x1400053cd  call    _guard_dispatch_icall
0x1400053d2  jmp     loc_1400055FB
0x1400053d7  mov     eax, cs:dword_140013058
0x1400053dd  cmp     eax, 4
0x1400053e0  jbe     short loc_1400053F1
0x1400053e2  mov     rdx, rsi
0x1400053e5  lea     rcx, aVmbustlcommone; "VmbusTlCommonEndpointCleanup: Cleaning "...
0x1400053ec  call    HvsocketTraceEndpointMessage
0x1400053f1  cmp     dword ptr [rsi+68h], 2
0x1400053f5  jnz     short loc_1400053FF
0x1400053f7  mov     rcx, rsi
0x1400053fa  call    VmbusTlShutdownTransport
0x1400053ff  cmp     dword ptr [rsi+68h], 3
0x140005403  jnz     short loc_14000540D
0x140005405  mov     rcx, rsi
0x140005408  call    VmbusTlDissociateListenerFromPartition
0x14000540d  mov     rax, [rsi+100h]
0x140005414  test    rax, rax
0x140005417  jz      short loc_140005427
0x140005419  mov     rcx, [rsi+108h]
0x140005420  xor     edx, edx
0x140005422  call    _guard_dispatch_icall
0x140005427  mov     eax, cs:dword_140013058
0x14000542d  cmp     eax, 4
0x140005430  jbe     short loc_140005441
0x140005432  mov     rdx, rsi
0x140005435  lea     rcx, aVmbustlcommone_0; "VmbusTlCommonEndpointCleanup: connectio"...
0x14000543c  call    HvsocketTraceEndpointMessage
0x140005441  mov     eax, cs:dword_140013058
0x140005447  cmp     eax, 5
0x14000544a  jbe     short loc_140005470
0x14000544c  mov     r9, [rsi+8]
0x140005450  lea     rax, aDereferenceObj; "Dereference object"
0x140005457  mov     r8, rsi
0x14000545a  mov     [rsp+100h+Timeout], rax
0x14000545f  mov     edx, 229h
0x140005464  lea     rcx, aVmbustlcommone_1; "VmbusTlCommonEndpointCleanup"
0x14000546b  call    HvsocketTraceReferenceCount
0x140005470  or      rax, 0FFFFFFFFFFFFFFFFh
0x140005474  lock xadd [rsi+8], rax
0x14000547a  sub     rax, 1
0x14000547e  jg      loc_1400055FB
0x140005484  test    rax, rax
0x140005487  jnz     short loc_1400054DC
0x140005489  mov     rax, [rsi+50h]
0x14000548d  test    rax, rax
0x140005490  jz      short loc_14000549A
0x140005492  mov     rcx, rsi
0x140005495  call    _guard_dispatch_icall
0x14000549a  mov     ecx, [rsi+58h]
0x14000549d  sub     ecx, 1
0x1400054a0  jz      short loc_1400054C3
0x1400054a2  cmp     ecx, 1
0x1400054a5  jnz     loc_1400055FB
0x1400054ab  mov     rcx, [rsi+60h]; Lookaside
0x1400054af  mov     rdx, rsi; Entry
0x1400054b2  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400054b9  nop     dword ptr [rax+rax+00h]
0x1400054be  jmp     loc_1400055FB
0x1400054c3  mov     edx, 69706E56h; Tag
0x1400054c8  mov     rcx, rsi; P
0x1400054cb  call    cs:__imp_ExFreePoolWithTag
0x1400054d2  nop     dword ptr [rax+rax+00h]
0x1400054d7  jmp     loc_1400055FB
0x1400054dc  mov     ecx, 0Eh
0x1400054e1  int     29h; Win8: RtlFailFast(ecx)
0x1400054e3  jmp     loc_1400055FB
0x1400054e8  mov     rcx, rsi; P
0x1400054eb  call    HvSocketConnectionTimeOut
0x1400054f0  jmp     loc_1400055FB
0x1400054f5  cmp     [rsi+2E0h], rdi
0x1400054fc  jz      loc_1400055FB
0x140005502  lea     rcx, [rsi+2C8h]; Object
0x140005509  mov     [rsp+100h+Timeout], rdi; Timeout
0x14000550e  xor     r9d, r9d; Alertable
0x140005511  xor     r8d, r8d; WaitMode
0x140005514  xor     edx, edx; WaitReason
0x140005516  call    cs:__imp_KeWaitForSingleObject
0x14000551d  nop     dword ptr [rax+rax+00h]
0x140005522  mov     rax, [rsi+2E0h]
0x140005529  mov     rcx, rsi
0x14000552c  mov     rax, [rax+0A0h]
0x140005533  call    _guard_dispatch_icall
0x140005538  mov     rcx, [rsi+110h]; Process
0x14000553f  test    rcx, rcx
0x140005542  jnz     short loc_140005548
0x140005544  mov     eax, edi
0x140005546  jmp     short loc_140005554
0x140005548  call    cs:__imp_PsGetProcessId
0x14000554f  nop     dword ptr [rax+rax+00h]
0x140005554  mov     ecx, cs:dword_140013058
0x14000555a  cmp     ecx, 4
0x14000555d  jbe     loc_1400055F3
0x140005563  mov     eax, eax
0x140005565  lea     rcx, aAHyperVSocketC; "A Hyper-V socket connection has disconn"...
0x14000556c  mov     [rbp+57h+var_C8], rax
0x140005570  lea     rdx, byte_140011389; int
0x140005577  lea     rax, [rbp+57h+var_C8]
0x14000557b  mov     [rbp+57h+var_A0], rcx
0x14000557f  mov     [rbp+57h+var_90], rax
0x140005583  lea     rcx, dword_140013058; int
0x14000558a  lea     rax, [rsi+8Ch]
0x140005591  mov     [rbp+57h+var_98], 2Eh ; '.'
0x140005599  mov     [rbp+57h+var_80], rax
0x14000559d  lea     rax, [rsi+9Ch]
0x1400055a4  mov     [rbp+57h+var_70], rax
0x1400055a8  mov     eax, [rsi+204h]
0x1400055ae  shr     eax, 1
0x1400055b0  and     al, 1
0x1400055b2  mov     [rbp+57h+var_88], 8
0x1400055ba  mov     [rbp+57h+var_D0], al
0x1400055bd  lea     rax, [rbp+57h+var_D0]
0x1400055c1  mov     [rbp+57h+var_60], rax
0x1400055c5  lea     rax, [rbp+57h+var_C0]
0x1400055c9  mov     [rsp+100h+var_D8], rax; __int64
0x1400055ce  mov     dword ptr [rsp+100h+Timeout], 7; ULONG
0x1400055d6  mov     [rbp+57h+var_78], 10h
0x1400055de  mov     [rbp+57h+var_68], 10h
0x1400055e6  mov     [rbp+57h+var_58], 1
0x1400055ee  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400055f3  mov     rcx, rsi
0x1400055f6  call    VmbusTlDissociateConnectionFromPartition
0x1400055fb  mov     eax, cs:dword_140013058
0x140005601  cmp     eax, 5
0x140005604  jbe     short loc_14000562A
0x140005606  mov     r9, [rsi+8]
0x14000560a  lea     rax, aDereferenceObj; "Dereference object"
0x140005611  mov     r8, rsi
0x140005614  mov     [rsp+100h+Timeout], rax
0x140005619  mov     edx, 28Dh
0x14000561e  lea     rcx, aVmbustlendpoin_3; "VmbusTlEndpointActionWorkQueueRoutine"
0x140005625  call    HvsocketTraceReferenceCount
0x14000562a  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000562e  lock xadd [rsi+8], rax
0x140005634  sub     rax, 1
0x140005638  jg      short loc_14000568F
0x14000563a  test    rax, rax
0x14000563d  jnz     short loc_140005688
0x14000563f  mov     rax, [rsi+50h]
0x140005643  test    rax, rax
0x140005646  jz      short loc_140005650
0x140005648  mov     rcx, rsi
0x14000564b  call    _guard_dispatch_icall
0x140005650  mov     ecx, [rsi+58h]
0x140005653  sub     ecx, 1
0x140005656  jz      short loc_140005672
0x140005658  cmp     ecx, 1
0x14000565b  jnz     short loc_14000568F
0x14000565d  mov     rcx, [rsi+60h]; Lookaside
0x140005661  mov     rdx, rsi; Entry
0x140005664  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000566b  nop     dword ptr [rax+rax+00h]
0x140005670  jmp     short loc_14000568F
0x140005672  mov     edx, 69706E56h; Tag
0x140005677  mov     rcx, rsi; P
0x14000567a  call    cs:__imp_ExFreePoolWithTag
0x140005681  nop     dword ptr [rax+rax+00h]
0x140005686  jmp     short loc_14000568F
0x140005688  mov     ecx, 0Eh
0x14000568d  int     29h; Win8: RtlFailFast(ecx)
0x14000568f  test    r12b, r12b
0x140005692  jz      short loc_1400056A8
0x140005694  mov     edx, 69706E56h; Tag
0x140005699  mov     rcx, r13; P
0x14000569c  call    cs:__imp_ExFreePoolWithTag
0x1400056a3  nop     dword ptr [rax+rax+00h]
0x1400056a8  test    r15, r15
0x1400056ab  jnz     loc_1400052AC
0x1400056b1  mov     rcx, [rbp+57h+var_50]
0x1400056b5  xor     rcx, rsp; StackCookie
0x1400056b8  call    __security_check_cookie
0x1400056bd  add     rsp, 0C8h
0x1400056c4  pop     r15
0x1400056c6  pop     r14
0x1400056c8  pop     r13
0x1400056ca  pop     r12
0x1400056cc  pop     rdi
0x1400056cd  pop     rsi
0x1400056ce  pop     rbx
0x1400056cf  pop     rbp
0x1400056d0  retn
```
