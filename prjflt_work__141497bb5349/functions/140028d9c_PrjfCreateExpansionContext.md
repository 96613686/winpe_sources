# PrjfCreateExpansionContext

- ea: `0x140028d9c`
- end: `0x140029082`
- name: `PrjfCreateExpansionContext`
- size: `742`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, __int64, __int64, int, char, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002aa24`

## callees

- `0x14000af84`
- `0x14000ba20`
- `0x14000d26c`
- `0x140028d9c`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002904c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002904c`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140028ddd`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140028ddd`
- `ntoskrnl!KeInitializeEvent` at `0x140028e70`
- `ntoskrnl!KeInitializeEvent` at `0x140028e87`
- `ntoskrnl!KeInitializeEvent` at `0x140028eb9`
- `ntoskrnl!KeInitializeEvent` at `0x140028e70`
- `ntoskrnl!KeInitializeEvent` at `0x140028e87`
- `ntoskrnl!KeInitializeEvent` at `0x140028eb9`
- `FLTMGR!FltCbdqInitialize` at `0x140028e43`
- `FLTMGR!FltCbdqInitialize` at `0x140028e43`

## pseudocode

```c
__int64 __fastcall PrjfCreateExpansionContext(
        PFLT_INSTANCE Instance,
        __int64 a2,
        __int64 a3,
        int a4,
        char a5,
        _QWORD *a6)
{
  char *v10; // rax
  _DWORD *v11; // rbx
  NTSTATUS v12; // edi
  int v13; // edx
  int v14; // r8d
  __int64 v16; // [rsp+60h] [rbp-69h] BYREF
  __int64 v17; // [rsp+68h] [rbp-61h] BYREF
  _BYTE v18[32]; // [rsp+70h] [rbp-59h] BYREF
  __int64 *v19; // [rsp+90h] [rbp-39h]
  __int64 v20; // [rsp+98h] [rbp-31h]
  _DWORD *v21; // [rsp+A0h] [rbp-29h]
  __int64 v22; // [rsp+A8h] [rbp-21h]
  __int64 v23; // [rsp+B0h] [rbp-19h]
  _DWORD v24[2]; // [rsp+B8h] [rbp-11h] BYREF
  __int64 *v25; // [rsp+C0h] [rbp-9h]
  __int64 v26; // [rsp+C8h] [rbp-1h]

  v10 = (char *)ExAllocateFromNPagedLookasideList(&stru_14001AB40);
  v11 = v10;
  if ( v10 )
  {
    v12 = FltCbdqInitialize(
            Instance,
            (PFLT_CALLBACK_DATA_QUEUE)(v10 + 72),
            PrjfExpansionCsqInsertIo,
            PrjfExpansionCsqRemoveIo,
            PrjfExpansionCsqPeekNextIo,
            PrjfExpansionCsqAcquireLock,
            PrjfExpansionCsqReleaseLock,
            PrjfExpansionCsqCompleteCanceledIo);
    if ( v12 < 0 )
    {
      ExFreeToNPagedLookasideList(&stru_14001AB40, v11);
    }
    else
    {
      *((_QWORD *)v11 + 26) = v11 + 50;
      *((_QWORD *)v11 + 25) = v11 + 50;
      KeInitializeEvent((PRKEVENT)(v11 + 4), NotificationEvent, 1u);
      KeInitializeEvent((PRKEVENT)(v11 + 10), SynchronizationEvent, 0);
      v11[54] = 1;
      *((_QWORD *)v11 + 28) = 0;
      v11[58] = 0;
      KeInitializeEvent((PRKEVENT)v11 + 10, SynchronizationEvent, 0);
      *v11 = 0;
      v11[2] = 0;
      v11[16] = 0;
      v11[17] = 0;
      *((_QWORD *)v11 + 34) = a3;
      v11[74] = *(_DWORD *)(a2 + 72);
      *((_QWORD *)v11 + 36) = _InterlockedIncrement64((volatile signed __int64 *)(a2 + 64));
      v11[70] = 0;
      if ( *(_DWORD *)(a3 + 64) != 1 || a5 )
      {
        v11[1] = a4;
      }
      else
      {
        v11[1] = 3;
        *v11 |= 8u;
        LOBYTE(v14) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        if ( (BYTE9(xmmword_14001A3D0) & 4) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v13) = BYTE9(xmmword_14001A3D0) & 4;
          WPP_RECORDER_AND_TRACE_SF_sDZ(
            778,
            v13,
            v14,
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            3,
            10,
            11,
            (__int64)WPP_f6f932a41f663696b98ce9faa74178e4_Traceguids,
            (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\expansion.c",
            84,
            a3 + 120);
        }
        if ( (unsigned int)dword_14001A068 > 5
          && (qword_14001A078 & 0x400000000000LL) != 0
          && (qword_14001A080 & 0x400000000000LL) == qword_14001A080 )
        {
          v16 = 1;
          v19 = &v16;
          v20 = 8;
          v21 = v24;
          v23 = *(_QWORD *)(a2 + 48);
          v24[0] = *(unsigned __int16 *)(a2 + 40);
          v25 = &v17;
          v22 = 2;
          v24[1] = 0;
          v17 = 0x1000000;
          v26 = 8;
          tlgWriteAgg(qword_14001A080, (unsigned int)&byte_1400164F7, v14, 6, (__int64)v18);
        }
      }
      *a6 = v11;
    }
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140028d9c  mov     [rsp-8+arg_18], rbx
0x140028da1  push    rbp
0x140028da2  push    rsi
0x140028da3  push    rdi
0x140028da4  push    r12
0x140028da6  push    r13
0x140028da8  push    r14
0x140028daa  push    r15
0x140028dac  lea     rbp, [rsp-17h]
0x140028db1  sub     rsp, 0E0h
0x140028db8  mov     rax, cs:__security_cookie
0x140028dbf  xor     rax, rsp
0x140028dc2  mov     [rbp+47h+var_40], rax
0x140028dc6  mov     r12, [rbp+47h+arg_28]
0x140028dca  mov     rdi, rcx
0x140028dcd  lea     rcx, stru_14001AB40; Lookaside
0x140028dd4  mov     r14d, r9d
0x140028dd7  mov     r15, r8
0x140028dda  mov     rsi, rdx
0x140028ddd  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140028de4  nop     dword ptr [rax+rax+00h]
0x140028de9  xor     r13d, r13d
0x140028dec  mov     rbx, rax
0x140028def  test    rax, rax
0x140028df2  jnz     short loc_140028DFE
0x140028df4  mov     edi, 0C000009Ah
0x140028df9  jmp     loc_140029058
0x140028dfe  lea     rdx, [rax+48h]; Cbdq
0x140028e02  mov     rcx, rdi; Instance
0x140028e05  lea     rax, PrjfExpansionCsqCompleteCanceledIo
0x140028e0c  mov     [rsp+110h+CbdqCompleteCanceledIo], rax; CbdqCompleteCanceledIo
0x140028e11  lea     r9, PrjfExpansionCsqRemoveIo; CbdqRemoveIo
0x140028e18  lea     rax, PrjfExpansionCsqReleaseLock
0x140028e1f  mov     [rsp+110h+CbdqRelease], rax; CbdqRelease
0x140028e24  lea     r8, PrjfExpansionCsqInsertIo; CbdqInsertIo
0x140028e2b  lea     rax, PrjfExpansionCsqAcquireLock
0x140028e32  mov     [rsp+110h+CbdqAcquire], rax; CbdqAcquire
0x140028e37  lea     rax, PrjfExpansionCsqPeekNextIo
0x140028e3e  mov     [rsp+110h+CbdqPeekNextIo], rax; CbdqPeekNextIo
0x140028e43  call    cs:__imp_FltCbdqInitialize
0x140028e4a  nop     dword ptr [rax+rax+00h]
0x140028e4f  mov     edi, eax
0x140028e51  test    eax, eax
0x140028e53  js      loc_140029042
0x140028e59  lea     rcx, [rbx+0C8h]
0x140028e60  mov     r8b, 1; State
0x140028e63  mov     [rcx+8], rcx
0x140028e67  xor     edx, edx; Type
0x140028e69  mov     [rcx], rcx
0x140028e6c  lea     rcx, [rbx+10h]; Event
0x140028e70  call    cs:__imp_KeInitializeEvent
0x140028e77  nop     dword ptr [rax+rax+00h]
0x140028e7c  xor     r8d, r8d; State
0x140028e7f  lea     rcx, [rbx+28h]; Event
0x140028e83  lea     edx, [r8+1]; Type
0x140028e87  call    cs:__imp_KeInitializeEvent
0x140028e8e  nop     dword ptr [rax+rax+00h]
0x140028e93  xor     r8d, r8d; State
0x140028e96  mov     dword ptr [rbx+0D8h], 1
0x140028ea0  lea     rcx, [rbx+0F0h]; Event
0x140028ea7  mov     [rbx+0E0h], r13
0x140028eae  mov     [rbx+0E8h], r13d
0x140028eb5  lea     edx, [r8+1]; Type
0x140028eb9  call    cs:__imp_KeInitializeEvent
0x140028ec0  nop     dword ptr [rax+rax+00h]
0x140028ec5  mov     [rbx], r13d
0x140028ec8  mov     [rbx+8], r13d
0x140028ecc  mov     [rbx+40h], r13d
0x140028ed0  mov     [rbx+44h], r13d
0x140028ed4  mov     [rbx+110h], r15
0x140028edb  mov     eax, [rsi+48h]
0x140028ede  mov     [rbx+128h], eax
0x140028ee4  mov     eax, 1
0x140028ee9  lock xadd [rsi+40h], rax
0x140028eef  inc     rax
0x140028ef2  mov     [rbx+120h], rax
0x140028ef9  mov     [rbx+118h], r13d
0x140028f00  cmp     dword ptr [r15+40h], 1
0x140028f05  jnz     loc_140029038
0x140028f0b  cmp     [rbp+47h+arg_20], r13b
0x140028f0f  jnz     loc_140029038
0x140028f15  mov     r14d, 8
0x140028f1b  mov     dword ptr [rbx+4], 3
0x140028f22  or      [rbx], r14d
0x140028f25  mov     dl, byte ptr cs:xmmword_14001A3D0+9
0x140028f2b  lea     rax, WPP_RECORDER_INITIALIZED
0x140028f32  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140028f39  setnz   r8b
0x140028f3d  and     dl, 4
0x140028f40  jnz     short loc_140028F47
0x140028f42  test    r8b, r8b
0x140028f45  jz      short loc_140028F99
0x140028f47  mov     r9, cs:WPP_GLOBAL_Control
0x140028f4e  lea     rax, [r15+78h]
0x140028f52  mov     [rsp+110h+var_C0], rax
0x140028f57  mov     ecx, 30Ah
0x140028f5c  mov     [rsp+110h+var_C8], 254h
0x140028f64  lea     rax, aOnecoreBaseFsG_10; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140028f6b  mov     [rsp+110h+var_D0], rax
0x140028f70  lea     rax, WPP_f6f932a41f663696b98ce9faa74178e4_Traceguids
0x140028f77  mov     r9, [r9+40h]
0x140028f7b  mov     [rsp+110h+CbdqCompleteCanceledIo], rax
0x140028f80  mov     word ptr [rsp+110h+CbdqRelease], 0Bh
0x140028f87  mov     dword ptr [rsp+110h+CbdqAcquire], 0Ah
0x140028f8f  mov     byte ptr [rsp+110h+CbdqPeekNextIo], 3
0x140028f94  call    WPP_RECORDER_AND_TRACE_SF_sDZ
0x140028f99  mov     eax, cs:dword_14001A068
0x140028f9f  cmp     eax, 5
0x140028fa2  jbe     loc_14002903C
0x140028fa8  mov     rcx, cs:qword_14001A080
0x140028faf  mov     rdx, 400000000000h
0x140028fb9  mov     rax, cs:qword_14001A078
0x140028fc0  test    rdx, rax
0x140028fc3  jz      short loc_14002903C
0x140028fc5  mov     rax, rcx
0x140028fc8  and     rax, rdx
0x140028fcb  cmp     rax, rcx
0x140028fce  jnz     short loc_14002903C
0x140028fd0  lea     rax, [rbp+47h+var_B0]
0x140028fd4  mov     [rbp+47h+var_B0], 1
0x140028fdc  mov     [rbp+47h+var_80], rax
0x140028fe0  lea     rdx, byte_1400164F7
0x140028fe7  lea     rax, [rbp+47h+var_58]
0x140028feb  mov     [rbp+47h+var_78], r14
0x140028fef  mov     [rbp+47h+var_70], rax
0x140028ff3  mov     r9d, 6
0x140028ff9  mov     rax, [rsi+30h]
0x140028ffd  mov     [rbp+47h+var_60], rax
0x140029001  movzx   eax, word ptr [rsi+28h]
0x140029005  mov     [rbp+47h+var_58], eax
0x140029008  lea     rax, [rbp+47h+var_A8]
0x14002900c  mov     [rbp+47h+var_50], rax
0x140029010  lea     rax, [rbp+47h+var_A0]
0x140029014  mov     [rsp+110h+CbdqPeekNextIo], rax
0x140029019  mov     [rbp+47h+var_68], 2
0x140029021  mov     [rbp+47h+var_54], r13d
0x140029025  mov     [rbp+47h+var_A8], 1000000h
0x14002902d  mov     [rbp+47h+var_48], r14
0x140029031  call    _tlgWriteAgg
0x140029036  jmp     short loc_14002903C
0x140029038  mov     [rbx+4], r14d
0x14002903c  mov     [r12], rbx
0x140029040  jmp     short loc_140029058
0x140029042  mov     rdx, rbx; Entry
0x140029045  lea     rcx, stru_14001AB40; Lookaside
0x14002904c  call    cs:__imp_ExFreeToNPagedLookasideList
0x140029053  nop     dword ptr [rax+rax+00h]
0x140029058  mov     eax, edi
0x14002905a  mov     rcx, [rbp+47h+var_40]
0x14002905e  xor     rcx, rsp; StackCookie
0x140029061  call    __security_check_cookie
0x140029066  mov     rbx, [rsp+110h+arg_18]
0x14002906e  add     rsp, 0E0h
0x140029075  pop     r15
0x140029077  pop     r14
0x140029079  pop     r13
0x14002907b  pop     r12
0x14002907d  pop     rdi
0x14002907e  pop     rsi
0x14002907f  pop     rbp
0x140029080  retn
```
