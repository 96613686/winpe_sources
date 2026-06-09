# RxCeCompleteConnectRequest

- ea: `0x14001cf70`
- end: `0x14001d56a`
- name: `RxCeCompleteConnectRequest`
- size: `1530`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14001cda0`

## callees

- `0x140005bd0`
- `0x14001cf70`
- `0x14001e390`
- `0x14001e440`
- `0x1400215b0`
- `0x140024790`
- `0x140025008`
- `0x140025738`
- `0x140026950`
- `0x140039fa8`
- `0x14003e14c`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001cfa8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001d478`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001cfa8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001d478`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001d4f7`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001d4f7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001d434`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001d4de`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001d434`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001d4de`
- `ntoskrnl!ExInitializeRundownProtection` at `0x14001d1fe`
- `ntoskrnl!ExInitializeRundownProtection` at `0x14001d1fe`
- `rdbss!RxPostToWorkerThread` at `0x14001d53d`
- `rdbss!RxPostToWorkerThread` at `0x14001d53d`
- `rdbss!RxDispatchToWorkerThread` at `0x14001d3c9`
- `rdbss!RxDispatchToWorkerThread` at `0x14001d3c9`

## pseudocode

```c
__int64 __fastcall RxCeCompleteConnectRequest(__int64 *a1)
{
  __int64 pContext; // r13
  __int64 *v2; // rbx
  unsigned int v3; // esi
  char v4; // r15
  __int64 *v5; // rbp
  __int64 v6; // r12
  KSPIN_LOCK *v7; // r14
  __int64 v8; // r8
  int v9; // ecx
  __int64 v10; // r11
  _DWORD *v11; // rdi
  int v12; // r8d
  unsigned int v13; // edx
  __int64 *i; // rcx
  __int64 *v15; // rax
  int v16; // ecx
  __int64 v17; // r12
  int v18; // r15d
  __int64 v19; // rbx
  UCHAR v20; // al
  int v21; // edx
  int v22; // ecx
  int v23; // r10d
  __int16 v24; // r11
  unsigned int v25; // edi
  _DWORD *v26; // rsi
  __int64 *v27; // rcx
  __int64 *v28; // rdi
  KIRQL v29; // al
  int v31; // [rsp+30h] [rbp-B8h]
  __int64 *v32; // [rsp+90h] [rbp-58h]
  KIRQL NewIrql; // [rsp+100h] [rbp+18h]
  NTSTATUS v35; // [rsp+108h] [rbp+20h]

  pContext = a1[1];
  v2 = a1;
  v3 = 0;
  v4 = 0;
  v35 = 0;
  v5 = 0;
  v6 = *(_QWORD *)(pContext + 40);
  v7 = (KSPIN_LOCK *)(pContext + 8);
  NewIrql = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(pContext + 8));
  if ( !*(_BYTE *)(pContext + 188) )
  {
    if ( *((int *)v2 + 4) < 0 )
    {
      if ( (byte_1400712C3 & 4) != 0 )
      {
        v10 = v2[27];
        v31 = *(_BYTE *)(v10 + 325) != 0 ? 28 : 16;
        McTemplateK0hzr0qqbr3hzr5qd_EtwWriteTransfer(
          v31,
          *(_QWORD *)(v10 + 24),
          v10 + 428,
          *(_WORD *)(pContext + 48) >> 1,
          *(_QWORD *)(pContext + 56),
          *(_DWORD *)(v10 + 320),
          v31,
          v10 + 428,
          *(_WORD *)(*(_QWORD *)(v10 + 24) + 360LL) >> 1,
          *(_QWORD *)(*(_QWORD *)(v10 + 24) + 368LL),
          *(_DWORD *)(v10 + 628),
          *((_DWORD *)v2 + 4));
      }
      v11 = v2 + 2;
      LOBYTE(v8) = 1;
      v12 = VctSetEndpointState(v2[27], 1, v8);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        {
          if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            WPP_SF_qD(
              WPP_GLOBAL_Control->AttachedDevice,
              23,
              &WPP_2f623439b0cb30f148aad6ad1abf961a_Traceguids,
              v2[27],
              v12);
        }
        else
        {
          v11 = v2 + 2;
        }
      }
      if ( *v11 == -1073741715 )
        *(_QWORD *)(pContext + 24) = v2[2];
      if ( *(_DWORD *)(pContext + 160) == 1 )
      {
        v13 = *(_DWORD *)(pContext + 176);
        if ( *((_DWORD *)v2 + 52) == v13 )
        {
          for ( i = *(__int64 **)(pContext + 40); i; i = v15 )
          {
            v15 = (__int64 *)*i;
            if ( *((_DWORD *)i + 52) >= v13 && v15 )
            {
              v16 = *((_DWORD *)v15 + 4);
              if ( v16 == 259 )
              {
                *(_DWORD *)(pContext + 176) = *((_DWORD *)v15 + 52);
                goto LABEL_34;
              }
              if ( !v16 )
              {
                v5 = v15;
                v32 = v15;
                goto LABEL_27;
              }
            }
          }
        }
      }
      goto LABEL_34;
    }
    v9 = *(_DWORD *)(pContext + 160);
    if ( v9 && (v9 != 1 || *((_DWORD *)v2 + 52) != *(_DWORD *)(pContext + 176)) || (v32 = v2, (v5 = v2) == 0) )
    {
LABEL_34:
      v25 = *(_DWORD *)(pContext + 168);
      if ( v25 < *(_DWORD *)(pContext + 164) )
      {
        do
        {
          ++*(_DWORD *)(pContext + 168);
          RxCeReferenceConnectionCallOutContext(pContext);
          v26 = (_DWORD *)(v6 + 264LL * v25);
          v35 = RxDispatchToWorkerThread(
                  *(PRDBSS_DEVICE_OBJECT *)(pContext + 32),
                  NormalWorkQueue,
                  *(PRX_WORKERTHREAD_ROUTINE *)(pContext + 128),
                  v26);
          if ( !v35 )
            break;
          ++*(_DWORD *)(pContext + 172);
          RxCeDereferenceConnectionCallOutContext((PVOID)pContext);
          ++v25;
          v26[4] = v35;
          v26[5] = 0;
        }
        while ( v25 < *(_DWORD *)(pContext + 164) );
        v2 = a1;
      }
      goto LABEL_39;
    }
LABEL_27:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 24, &WPP_2f623439b0cb30f148aad6ad1abf961a_Traceguids);
    }
    *(_BYTE *)(pContext + 188) = 1;
    *(_DWORD *)(pContext + 180) = *((_DWORD *)v5 + 52);
    *(_QWORD *)(pContext + 24) = 0;
    v17 = v5[27];
    *(_DWORD *)(v17 + 12) = 0;
    *(_DWORD *)(v17 + 472) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(pContext + 32) + 2408LL) + 120LL);
    ExInitializeRundownProtection((PEX_RUNDOWN_REF)(v17 + 496));
    *(_DWORD *)(v17 + 568) = 0;
    *(_QWORD *)(v17 + 584) = 0;
    *(_DWORD *)(v17 + 592) = 0;
    *(_BYTE *)(v17 + 596) = 0;
    *(_BYTE *)(v17 + 605) = 0;
    *(_DWORD *)(v17 + 328) = 73728;
    *(_QWORD *)(*(_QWORD *)(pContext + 152) + 80LL) = v17;
    **(_QWORD **)(*(_QWORD *)(pContext + 152) + 88LL) = v17;
    if ( (byte_1400712C2 & 0x10) == 0 )
    {
      v5 = v32;
LABEL_39:
      v3 = v35;
      goto LABEL_40;
    }
    v18 = *(_DWORD *)(v17 + 320);
    v19 = *(_QWORD *)(v17 + 24);
    SOCKADDR_SIZE(*(_WORD *)(v17 + 400));
    v20 = SOCKADDR_SIZE(*(_WORD *)(v17 + 428));
    McTemplateK0hzr0qqbr3qbr5hzr7qdqbr11qbr13_EtwWriteTransfer(
      v22,
      v21,
      v20,
      *(_WORD *)(pContext + 48) >> 1,
      *(_QWORD *)(pContext + 56),
      v18,
      v20,
      v17 + 428,
      v23,
      v17 + 400,
      v24,
      *(_QWORD *)(v19 + 368),
      *(_DWORD *)(v17 + 628));
    v3 = 0;
    v7 = (KSPIN_LOCK *)(pContext + 8);
    v2 = a1;
    v4 = 0;
    v5 = v32;
  }
LABEL_40:
  v2[31] = 0;
  KeReleaseSpinLock(v7, NewIrql);
  if ( v5 )
  {
    v27 = *(__int64 **)(pContext + 40);
    if ( v27 )
    {
      do
      {
        v28 = (__int64 *)*v27;
        if ( *((_DWORD *)v27 + 4) == 259 )
        {
          *((_DWORD *)v27 + 4) = -1073741536;
          *((_DWORD *)v27 + 5) = 0;
          RxCeCancelAsynchronousConnect();
        }
        v27 = v28;
      }
      while ( v28 );
    }
  }
  v29 = KeAcquireSpinLockRaiseToDpc(v7);
  if ( ++*(_DWORD *)(pContext + 172) == *(_DWORD *)(pContext + 168) )
  {
    if ( !*(_BYTE *)(pContext + 188) && *(_DWORD *)(pContext + 24) != -1073741715 )
      *(_QWORD *)(pContext + 24) = v2[2];
  }
  else if ( !*(_BYTE *)(pContext + 188) )
  {
    goto LABEL_52;
  }
  if ( !*(_BYTE *)(pContext + 189) )
  {
    v4 = 1;
    *(_BYTE *)(pContext + 189) = 1;
  }
LABEL_52:
  KeReleaseSpinLock(v7, v29);
  if ( v4 )
  {
    *(_DWORD *)(pContext + 16) = 2;
    if ( KeGetCurrentIrql() >= 2u || *(_DWORD *)(v2[27] + 320) == 4 )
      v3 = RxPostToWorkerThread(
             *(PRDBSS_DEVICE_OBJECT *)(pContext + 32),
             DelayedWorkQueue,
             (PRX_WORK_QUEUE_ITEM)(pContext + 208),
             RxCeInitiateConnection,
             (PVOID)pContext);
    else
      RxCeInitiateConnection((PVOID)pContext);
  }
  RxCeDereferenceConnectionCallOutContext((PVOID)pContext);
  return v3;
}

```

## disassembly

```asm
0x14001cf70  mov     [rsp+arg_0], rcx
0x14001cf75  push    rbx
0x14001cf76  push    rbp
0x14001cf77  push    rsi
0x14001cf78  push    rdi
0x14001cf79  push    r12
0x14001cf7b  push    r13
0x14001cf7d  push    r14
0x14001cf7f  push    r15
0x14001cf81  sub     rsp, 0A8h
0x14001cf88  mov     r13, [rcx+8]
0x14001cf8c  mov     rbx, rcx
0x14001cf8f  xor     esi, esi
0x14001cf91  xor     r15b, r15b
0x14001cf94  mov     [rsp+0E8h+arg_18], esi
0x14001cf9b  xor     ebp, ebp
0x14001cf9d  mov     r12, [r13+28h]
0x14001cfa1  lea     r14, [r13+8]
0x14001cfa5  mov     rcx, r14; SpinLock
0x14001cfa8  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001cfaf  nop     dword ptr [rax+rax+00h]
0x14001cfb4  mov     [rsp+0E8h+NewIrql], al
0x14001cfbb  mov     al, [r13+0BCh]
0x14001cfc2  test    al, al
0x14001cfc4  jnz     loc_14001D41F
0x14001cfca  lea     rsi, [rbx+10h]
0x14001cfce  mov     edi, [rsi]
0x14001cfd0  test    edi, edi
0x14001cfd2  js      short loc_14001D014
0x14001cfd4  mov     ecx, [r13+0A0h]
0x14001cfdb  test    ecx, ecx
0x14001cfdd  jz      short loc_14001CFFB
0x14001cfdf  cmp     ecx, 1
0x14001cfe2  jnz     loc_14001D38B
0x14001cfe8  mov     eax, [r13+0B0h]
0x14001cfef  cmp     [rbx+0D0h], eax
0x14001cff5  jnz     loc_14001D38B
0x14001cffb  mov     [rsp+0E8h+var_58], rbx
0x14001d003  mov     rbp, rbx
0x14001d006  test    rbx, rbx
0x14001d009  jnz     loc_14001D172
0x14001d00f  jmp     loc_14001D38B
0x14001d014  test    cs:byte_1400712C3, 4
0x14001d01b  jz      loc_14001D0A2
0x14001d021  mov     r11, [rbx+0D8h]
0x14001d028  movzx   r9d, word ptr [r13+30h]
0x14001d02d  mov     dword ptr [rsp+0E8h+var_90], edi
0x14001d031  mov     al, [r11+145h]
0x14001d038  lea     r8, [r11+1ACh]
0x14001d03f  mov     rdx, [r11+18h]
0x14001d043  movzx   r10d, word ptr [rdx+168h]
0x14001d04b  shr     r10w, 1
0x14001d04f  neg     al
0x14001d051  mov     eax, [r11+274h]
0x14001d058  mov     [rsp+0E8h+var_98], eax
0x14001d05c  sbb     ecx, ecx
0x14001d05e  mov     rax, [rdx+170h]
0x14001d065  and     ecx, 0Ch
0x14001d068  mov     [rsp+0E8h+var_A0], rax
0x14001d06d  add     ecx, 10h
0x14001d070  mov     eax, [r11+140h]
0x14001d077  mov     word ptr [rsp+0E8h+var_A8], r10w
0x14001d07d  mov     [rsp+0E8h+var_B0], r8
0x14001d082  mov     [rsp+0E8h+var_B8], ecx
0x14001d086  mov     [rsp+0E8h+var_C0], eax
0x14001d08a  mov     rax, [r13+38h]
0x14001d08e  shr     r9w, 1
0x14001d092  mov     [rsp+0E8h+pContext], rax
0x14001d097  call    McTemplateK0hzr0qqbr3hzr5qd_EtwWriteTransfer
0x14001d09c  lea     rdi, [rbx+10h]
0x14001d0a0  jmp     short loc_14001D0A5
0x14001d0a2  mov     rdi, rsi
0x14001d0a5  mov     rcx, [rbx+0D8h]
0x14001d0ac  mov     r8b, 1
0x14001d0af  mov     edx, 1
0x14001d0b4  call    VctSetEndpointState
0x14001d0b9  mov     r8d, eax
0x14001d0bc  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001d0c3  lea     rax, WPP_GLOBAL_Control
0x14001d0ca  cmp     rcx, rax
0x14001d0cd  jz      short loc_14001D102
0x14001d0cf  mov     eax, [rcx+2Ch]
0x14001d0d2  test    al, 4
0x14001d0d4  jz      short loc_14001D0FF
0x14001d0d6  cmp     byte ptr [rcx+29h], 4
0x14001d0da  jb      short loc_14001D102
0x14001d0dc  mov     r9, [rbx+0D8h]
0x14001d0e3  mov     edx, 17h
0x14001d0e8  mov     rcx, [rcx+18h]
0x14001d0ec  mov     dword ptr [rsp+0E8h+pContext], r8d
0x14001d0f1  lea     r8, WPP_2f623439b0cb30f148aad6ad1abf961a_Traceguids
0x14001d0f8  call    WPP_SF_qD
0x14001d0fd  jmp     short loc_14001D102
0x14001d0ff  mov     rdi, rsi
0x14001d102  cmp     dword ptr [rdi], 0C000006Dh
0x14001d108  jnz     short loc_14001D111
0x14001d10a  mov     rax, [rsi]
0x14001d10d  mov     [r13+18h], rax
0x14001d111  cmp     dword ptr [r13+0A0h], 1
0x14001d119  jnz     loc_14001D38B
0x14001d11f  mov     edx, [r13+0B0h]
0x14001d126  cmp     [rbx+0D0h], edx
0x14001d12c  jnz     loc_14001D38B
0x14001d132  mov     rcx, [r13+28h]
0x14001d136  test    rcx, rcx
0x14001d139  jz      loc_14001D38B
0x14001d13f  mov     rax, [rcx]
0x14001d142  cmp     [rcx+0D0h], edx
0x14001d148  jb      short loc_14001D162
0x14001d14a  test    rax, rax
0x14001d14d  jz      short loc_14001D162
0x14001d14f  mov     ecx, [rax+10h]
0x14001d152  cmp     ecx, 103h
0x14001d158  jz      loc_14001D37E
0x14001d15e  test    ecx, ecx
0x14001d160  jz      short loc_14001D167
0x14001d162  mov     rcx, rax
0x14001d165  jmp     short loc_14001D136
0x14001d167  mov     rbp, rax
0x14001d16a  mov     [rsp+0E8h+var_58], rax
0x14001d172  mov     [rsp+0E8h+var_50], 0
0x14001d17e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001d185  lea     rax, WPP_GLOBAL_Control
0x14001d18c  cmp     rcx, rax
0x14001d18f  jz      short loc_14001D1B3
0x14001d191  mov     eax, [rcx+2Ch]
0x14001d194  test    al, 4
0x14001d196  jz      short loc_14001D1B3
0x14001d198  cmp     byte ptr [rcx+29h], 4
0x14001d19c  jb      short loc_14001D1B3
0x14001d19e  mov     rcx, [rcx+18h]
0x14001d1a2  lea     r8, WPP_2f623439b0cb30f148aad6ad1abf961a_Traceguids
0x14001d1a9  mov     edx, 18h
0x14001d1ae  call    WPP_SF_
0x14001d1b3  mov     byte ptr [r13+0BCh], 1
0x14001d1bb  mov     eax, [rbp+0D0h]
0x14001d1c1  mov     [r13+0B4h], eax
0x14001d1c8  mov     qword ptr [r13+18h], 0
0x14001d1d0  mov     r12, [rbp+0D8h]
0x14001d1d7  mov     dword ptr [r12+0Ch], 0
0x14001d1e0  mov     rax, [r13+20h]
0x14001d1e4  mov     rcx, [rax+968h]
0x14001d1eb  mov     eax, [rcx+78h]
0x14001d1ee  lea     rcx, [r12+1F0h]; RunRef
0x14001d1f6  mov     [r12+1D8h], eax
0x14001d1fe  call    cs:__imp_ExInitializeRundownProtection
0x14001d205  nop     dword ptr [rax+rax+00h]
0x14001d20a  mov     dword ptr [r12+238h], 0
0x14001d216  mov     qword ptr [r12+248h], 0
0x14001d222  mov     dword ptr [r12+250h], 0
0x14001d22e  mov     [r12+254h], r15b
0x14001d236  mov     [r12+25Dh], r15b
0x14001d23e  mov     dword ptr [r12+148h], 12000h
0x14001d24a  mov     rax, [r13+98h]
0x14001d251  mov     [rax+50h], r12
0x14001d255  mov     rax, [r13+98h]
0x14001d25c  mov     rcx, [rax+58h]
0x14001d260  mov     [rcx], r12
0x14001d263  mov     ecx, [r12+0E8h]
0x14001d26b  test    ecx, ecx
0x14001d26d  jz      short loc_14001D27F
0x14001d26f  mov     rax, [r12+0E0h]
0x14001d277  mov     [rsp+0E8h+var_50], rax
0x14001d27f  test    cs:byte_1400712C2, 10h
0x14001d286  jz      loc_14001D410
0x14001d28c  mov     r15d, [r12+140h]
0x14001d294  lea     rsi, [r12+190h]
0x14001d29c  mov     rbx, [r12+18h]
0x14001d2a1  lea     r14, [r12+1ACh]
0x14001d2a9  xor     eax, eax
0x14001d2ab  lea     rdx, [r12+0ECh]
0x14001d2b3  cmp     r15d, 4
0x14001d2b7  mov     ebp, 14h
0x14001d2bc  movzx   r11d, word ptr [rbx+168h]
0x14001d2c4  cmovnz  ebp, eax
0x14001d2c7  xor     edi, edi
0x14001d2c9  cmp     r15d, 4
0x14001d2cd  cmovz   edi, ecx
0x14001d2d0  movzx   ecx, word ptr [rsi]; af
0x14001d2d3  shr     r11w, 1
0x14001d2d7  call    SOCKADDR_SIZE
0x14001d2dc  movzx   ecx, word ptr [r14]; af
0x14001d2e0  movzx   r10d, al
0x14001d2e4  call    SOCKADDR_SIZE
0x14001d2e9  movzx   r9d, word ptr [r13+30h]
0x14001d2ee  mov     [rsp+0E8h+var_60], rdx
0x14001d2f6  mov     [rsp+0E8h+var_68], ebp
0x14001d2fd  movzx   r8d, al
0x14001d301  mov     rax, [rsp+0E8h+var_50]
0x14001d309  mov     [rsp+0E8h+var_70], rax
0x14001d30e  mov     eax, [r12+274h]
0x14001d316  mov     [rsp+0E8h+var_78], edi
0x14001d31a  mov     [rsp+0E8h+var_88], eax
0x14001d31e  mov     rax, [rbx+170h]
0x14001d325  mov     [rsp+0E8h+var_90], rax
0x14001d32a  mov     rax, [r13+38h]
0x14001d32e  mov     word ptr [rsp+0E8h+var_98], r11w
0x14001d334  mov     [rsp+0E8h+var_A0], rsi
0x14001d339  mov     [rsp+0E8h+var_A8], r10d
0x14001d33e  mov     [rsp+0E8h+var_B0], r14
0x14001d343  mov     [rsp+0E8h+var_B8], r8d
0x14001d348  mov     [rsp+0E8h+var_C0], r15d
0x14001d34d  shr     r9w, 1
0x14001d351  mov     [rsp+0E8h+pContext], rax
0x14001d356  call    McTemplateK0hzr0qqbr3qbr5hzr7qdqbr11qbr13_EtwWriteTransfer
0x14001d35b  mov     esi, [rsp+0E8h+arg_18]
0x14001d362  lea     r14, [r13+8]
0x14001d366  mov     rbx, [rsp+0E8h+arg_0]
0x14001d36e  mov     r15b, sil
0x14001d371  mov     rbp, [rsp+0E8h+var_58]
0x14001d379  jmp     loc_14001D41F
0x14001d37e  mov     eax, [rax+0D0h]
0x14001d384  mov     [r13+0B0h], eax
0x14001d38b  mov     edi, [r13+0A8h]
0x14001d392  cmp     edi, [r13+0A4h]
0x14001d399  jnb     short loc_14001D418
0x14001d39b  inc     dword ptr [r13+0A8h]
0x14001d3a2  mov     rcx, r13
0x14001d3a5  call    RxCeReferenceConnectionCallOutContext
0x14001d3aa  mov     r8, [r13+80h]; Routine
0x14001d3b1  mov     edx, 3; WorkQueueType
0x14001d3b6  mov     rcx, [r13+20h]; pMRxDeviceObject
0x14001d3ba  mov     eax, edi
0x14001d3bc  imul    rsi, rax, 108h
0x14001d3c3  add     rsi, r12
0x14001d3c6  mov     r9, rsi; pContext
0x14001d3c9  call    cs:__imp_RxDispatchToWorkerThread
0x14001d3d0  nop     dword ptr [rax+rax+00h]
0x14001d3d5  mov     [rsp+0E8h+arg_18], eax
0x14001d3dc  mov     ebx, eax
0x14001d3de  test    eax, eax
0x14001d3e0  jz      short loc_14001D406
0x14001d3e2  inc     dword ptr [r13+0ACh]
0x14001d3e9  mov     rcx, r13; pContext
0x14001d3ec  call    RxCeDereferenceConnectionCallOutContext
0x14001d3f1  inc     edi
0x14001d3f3  mov     [rsi+10h], ebx
0x14001d3f6  mov     dword ptr [rsi+14h], 0
0x14001d3fd  cmp     edi, [r13+0A4h]
0x14001d404  jb      short loc_14001D39B
0x14001d406  mov     rbx, [rsp+0E8h+arg_0]
0x14001d40e  jmp     short loc_14001D418
0x14001d410  mov     rbp, [rsp+0E8h+var_58]
0x14001d418  mov     esi, [rsp+0E8h+arg_18]
0x14001d41f  mov     dl, [rsp+0E8h+NewIrql]; NewIrql
0x14001d426  mov     rcx, r14; SpinLock
0x14001d429  mov     qword ptr [rbx+0F8h], 0
0x14001d434  call    cs:__imp_KeReleaseSpinLock
0x14001d43b  nop     dword ptr [rax+rax+00h]
0x14001d440  test    rbp, rbp
0x14001d443  jz      short loc_14001D475
0x14001d445  mov     rcx, [r13+28h]
0x14001d449  test    rcx, rcx
0x14001d44c  jz      short loc_14001D475
0x14001d44e  cmp     dword ptr [rcx+10h], 103h
0x14001d455  mov     rdi, [rcx]
0x14001d458  jnz     short loc_14001D46D
0x14001d45a  mov     dword ptr [rcx+10h], 0C0000120h
0x14001d461  mov     dword ptr [rcx+14h], 0
0x14001d468  call    RxCeCancelAsynchronousConnect
0x14001d46d  mov     rcx, rdi
0x14001d470  test    rdi, rdi
0x14001d473  jnz     short loc_14001D44E
0x14001d475  mov     rcx, r14; SpinLock
0x14001d478  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001d47f  nop     dword ptr [rax+rax+00h]
0x14001d484  inc     dword ptr [r13+0ACh]
0x14001d48b  mov     dl, al; NewIrql
0x14001d48d  mov     ecx, [r13+0ACh]
0x14001d494  cmp     ecx, [r13+0A8h]
0x14001d49b  jnz     short loc_14001D4BC
0x14001d49d  mov     cl, [r13+0BCh]
0x14001d4a4  test    cl, cl
0x14001d4a6  jnz     short loc_14001D4C7
0x14001d4a8  cmp     dword ptr [r13+18h], 0C000006Dh
0x14001d4b0  jz      short loc_14001D4C7
0x14001d4b2  mov     rax, [rbx+10h]
0x14001d4b6  mov     [r13+18h], rax
0x14001d4ba  jmp     short loc_14001D4C7
0x14001d4bc  mov     al, [r13+0BCh]
0x14001d4c3  test    al, al
0x14001d4c5  jz      short loc_14001D4DB
0x14001d4c7  cmp     byte ptr [r13+0BDh], 0
0x14001d4cf  jnz     short loc_14001D4DB
0x14001d4d1  mov     r15b, 1
0x14001d4d4  mov     [r13+0BDh], r15b
0x14001d4db  mov     rcx, r14; SpinLock
0x14001d4de  call    cs:__imp_KeReleaseSpinLock
0x14001d4e5  nop     dword ptr [rax+rax+00h]
0x14001d4ea  test    r15b, r15b
0x14001d4ed  jz      short loc_14001D54B
0x14001d4ef  mov     dword ptr [r13+10h], 2
0x14001d4f7  call    cs:__imp_KeGetCurrentIrql
0x14001d4fe  nop     dword ptr [rax+rax+00h]
0x14001d503  cmp     al, 2
0x14001d505  jnb     short loc_14001D521
0x14001d507  mov     rax, [rbx+0D8h]
0x14001d50e  cmp     dword ptr [rax+140h], 4
0x14001d515  jz      short loc_14001D521
0x14001d517  mov     rcx, r13; Context
  ... truncated ...
```
