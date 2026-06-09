# HidpFdoUpdateOpenCounts

- ea: `0x18000c5c0`
- end: `0x18000c942`
- name: `HidpFdoUpdateOpenCounts`
- size: `898`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x18000621c`
- `0x18000b140`
- `0x18003b444`

## callees

- `0x18000c5c0`
- `0x18000ce08`
- `0x18000e004`
- `0x180013b5c`
- `0x18001b744`
- `0x180025700`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x18000c64f`
- `ntoskrnl!KeReleaseSpinLock` at `0x18000c64f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18000c5e7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18000c5e7`

## pseudocode

```c
__int64 __fastcall HidpFdoUpdateOpenCounts(__int64 a1, __int64 a2, __int64 a3, __int64 a4, char a5, char a6)
{
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  KIRQL v13; // r12
  char v14; // bl
  unsigned int *v15; // rdi
  bool v16; // r15
  __int64 v17; // rdx
  unsigned int v18; // ebp
  int v20; // r8d
  PDEVICE_OBJECT v21; // rcx
  char v22; // al
  __int64 v23; // rdx
  KIRQL v24; // [rsp+D0h] [rbp+8h] BYREF

  v13 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 1792));
  v24 = v13;
  if ( !a5 )
  {
    if ( a2 )
      --*(_DWORD *)(a2 + 352);
    if ( a3 )
      --*(_DWORD *)(a3 + 136);
    v15 = (unsigned int *)(a1 + 248);
    v14 = 1;
    v16 = --*(_DWORD *)(a1 + 248) == 1;
    if ( a4 )
    {
      LOBYTE(v12) = 1;
      if ( (unsigned __int8)HidpFdoNotifyPdoClientInputSuppressionWithLock(a1, a3, a4, v12) )
      {
        v17 = *v15;
        v18 = *v15;
LABEL_17:
        if ( !a3 )
        {
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
          {
            v14 = 0;
          }
          if ( v14 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v17) = v14;
            LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            WPP_RECORDER_AND_TRACE_SF_qsL(WPP_GLOBAL_Control->AttachedDevice, v17, v11, *(_QWORD *)(a1 + 672));
          }
          goto LABEL_23;
        }
        if ( (unsigned int)Feature_HCTI01__private_IsEnabledDeviceUsageNoInline(v10, v17, v11, v12) )
        {
          v21 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
          {
            v14 = 0;
          }
          LOBYTE(v20) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          if ( !v14 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_23;
          v23 = *(_QWORD *)(a3 + 64);
        }
        else
        {
          v21 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
          {
            v14 = 0;
          }
          LOBYTE(v20) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          if ( !v14 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_23;
          v23 = *(_QWORD *)(a3 + 64);
        }
        LOBYTE(v23) = v14;
        WPP_RECORDER_AND_TRACE_SF_qdqsLLLL(v21->AttachedDevice, v23, v20, *(_QWORD *)(a1 + 672));
LABEL_23:
        HidFdoRunTimePolicyEngine(a1, &v24);
        v13 = v24;
        goto LABEL_9;
      }
    }
    goto LABEL_7;
  }
  v14 = 1;
  if ( a2 )
    ++*(_DWORD *)(a2 + 352);
  if ( a3 )
    ++*(_DWORD *)(a3 + 136);
  v15 = (unsigned int *)(a1 + 248);
  v16 = ++*(_DWORD *)(a1 + 248) == 2;
  if ( !a4 || a6 )
  {
LABEL_7:
    LOBYTE(v10) = v16;
    goto LABEL_8;
  }
  v22 = HidpFdoNotifyPdoClientInputSuppressionWithLock(a1, a3, a4, 0);
  v10 = v16;
  if ( v22 )
    v10 = 1;
LABEL_8:
  v17 = *v15;
  v18 = *v15;
  if ( (_BYTE)v10 )
    goto LABEL_17;
LABEL_9:
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 1792), v13);
  return v18;
}

```

## disassembly

```asm
0x18000c5c0  push    rbx
0x18000c5c2  push    rbp
0x18000c5c3  push    rsi
0x18000c5c4  push    rdi
0x18000c5c5  push    r12
0x18000c5c7  push    r13
0x18000c5c9  push    r14
0x18000c5cb  push    r15
0x18000c5cd  sub     rsp, 88h
0x18000c5d4  mov     r14, rcx
0x18000c5d7  mov     rbp, r9
0x18000c5da  add     rcx, 700h; SpinLock
0x18000c5e1  mov     rsi, r8
0x18000c5e4  mov     rdi, rdx
0x18000c5e7  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x18000c5ee  nop     dword ptr [rax+rax+00h]
0x18000c5f3  mov     r13b, [rsp+0C8h+arg_20]
0x18000c5fb  mov     r12b, al
0x18000c5fe  mov     [rsp+0C8h+arg_0], al
0x18000c605  test    r13b, r13b
0x18000c608  jz      short loc_18000C672
0x18000c60a  mov     ebx, 1
0x18000c60f  test    rdi, rdi
0x18000c612  jnz     loc_18000C728
0x18000c618  test    rsi, rsi
0x18000c61b  jnz     loc_18000C733
0x18000c621  lea     rdi, [r14+0F8h]
0x18000c628  add     [rdi], ebx
0x18000c62a  cmp     dword ptr [rdi], 2
0x18000c62d  setz    r15b
0x18000c631  test    rbp, rbp
0x18000c634  jnz     loc_18000C73E
0x18000c63a  mov     cl, r15b
0x18000c63d  mov     edx, [rdi]
0x18000c63f  mov     ebp, edx
0x18000c641  test    cl, cl
0x18000c643  jnz     short loc_18000C6B9
0x18000c645  mov     dl, r12b; NewIrql
0x18000c648  lea     rcx, [r14+700h]; SpinLock
0x18000c64f  call    cs:__imp_KeReleaseSpinLock
0x18000c656  nop     dword ptr [rax+rax+00h]
0x18000c65b  mov     eax, ebp
0x18000c65d  add     rsp, 88h
0x18000c664  pop     r15
0x18000c666  pop     r14
0x18000c668  pop     r13
0x18000c66a  pop     r12
0x18000c66c  pop     rdi
0x18000c66d  pop     rsi
0x18000c66e  pop     rbp
0x18000c66f  pop     rbx
0x18000c670  retn
0x18000c672  or      eax, 0FFFFFFFFh
0x18000c675  test    rdi, rdi
0x18000c678  jnz     loc_18000C76B
0x18000c67e  test    rsi, rsi
0x18000c681  jnz     loc_18000C776
0x18000c687  lea     rdi, [r14+0F8h]
0x18000c68e  mov     ebx, 1
0x18000c693  add     [rdi], eax
0x18000c695  cmp     [rdi], ebx
0x18000c697  setz    r15b
0x18000c69b  test    rbp, rbp
0x18000c69e  jz      short loc_18000C63A
0x18000c6a0  mov     r9b, bl
0x18000c6a3  mov     r8, rbp
0x18000c6a6  mov     rdx, rsi
0x18000c6a9  mov     rcx, r14
0x18000c6ac  call    HidpFdoNotifyPdoClientInputSuppressionWithLock
0x18000c6b1  test    al, al
0x18000c6b3  jz      short loc_18000C63A
0x18000c6b5  mov     edx, [rdi]
0x18000c6b7  mov     ebp, edx
0x18000c6b9  test    rsi, rsi
0x18000c6bc  jz      loc_18000C781
0x18000c6c2  call    Feature_HCTI01__private_IsEnabledDeviceUsageNoInline
0x18000c6c7  test    eax, eax
0x18000c6c9  jz      loc_18000C885
0x18000c6cf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c6d6  lea     rax, WPP_GLOBAL_Control
0x18000c6dd  cmp     rcx, rax
0x18000c6e0  jnz     loc_18000C801
0x18000c6e6  xor     bl, bl
0x18000c6e8  lea     rax, WPP_RECORDER_INITIALIZED
0x18000c6ef  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18000c6f6  setnz   r8b
0x18000c6fa  test    bl, bl
0x18000c6fc  jnz     loc_18000C81D
0x18000c702  test    r8b, r8b
0x18000c705  jnz     loc_18000C81D
0x18000c70b  lea     rdx, [rsp+0C8h+arg_0]
0x18000c713  mov     rcx, r14
0x18000c716  call    HidFdoRunTimePolicyEngine
0x18000c71b  mov     r12b, [rsp+0C8h+arg_0]
0x18000c723  jmp     loc_18000C645
0x18000c728  add     [rdi+160h], ebx
0x18000c72e  jmp     loc_18000C618
0x18000c733  add     [rsi+88h], ebx
0x18000c739  jmp     loc_18000C621
0x18000c73e  cmp     [rsp+0C8h+arg_28], 0
0x18000c746  jnz     loc_18000C63A
0x18000c74c  xor     r9d, r9d
0x18000c74f  mov     r8, rbp
0x18000c752  mov     rdx, rsi
0x18000c755  mov     rcx, r14
0x18000c758  call    HidpFdoNotifyPdoClientInputSuppressionWithLock
0x18000c75d  test    al, al
0x18000c75f  movzx   ecx, r15b
0x18000c763  cmovnz  ecx, ebx
0x18000c766  jmp     loc_18000C63D
0x18000c76b  add     [rdi+160h], eax
0x18000c771  jmp     loc_18000C67E
0x18000c776  dec     dword ptr [rsi+88h]
0x18000c77c  jmp     loc_18000C687
0x18000c781  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c788  lea     rax, WPP_GLOBAL_Control
0x18000c78f  cmp     rcx, rax
0x18000c792  jz      short loc_18000C7A3
0x18000c794  test    dword ptr [rcx+2Ch], 100h
0x18000c79b  jz      short loc_18000C7A3
0x18000c79d  cmp     byte ptr [rcx+29h], 4
0x18000c7a1  jnb     short loc_18000C7A5
0x18000c7a3  xor     bl, bl
0x18000c7a5  lea     rax, WPP_RECORDER_INITIALIZED
0x18000c7ac  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18000c7b3  setnz   r8b
0x18000c7b7  test    bl, bl
0x18000c7b9  jnz     short loc_18000C7C4
0x18000c7bb  test    r8b, r8b
0x18000c7be  jz      loc_18000C70B
0x18000c7c4  mov     rcx, [rcx+18h]
0x18000c7c8  lea     rax, aDecremented; "decremented"
0x18000c7cf  mov     dword ptr [rsp+0C8h+var_78], edx
0x18000c7d3  lea     r9, aIncremented; "incremented"
0x18000c7da  test    r13b, r13b
0x18000c7dd  mov     dl, bl
0x18000c7df  cmovz   r9, rax
0x18000c7e3  mov     rax, [r14]
0x18000c7e6  mov     [rsp+0C8h+var_80], r9
0x18000c7eb  mov     r9, [r14+2A0h]
0x18000c7f2  mov     [rsp+0C8h+var_88], rax
0x18000c7f7  call    WPP_RECORDER_AND_TRACE_SF_qsL
0x18000c7fc  jmp     loc_18000C70B
0x18000c801  test    dword ptr [rcx+2Ch], 100h
0x18000c808  jz      loc_18000C6E6
0x18000c80e  cmp     byte ptr [rcx+29h], 4
0x18000c812  jnb     loc_18000C6E8
0x18000c818  jmp     loc_18000C6E6
0x18000c81d  mov     rdx, [rsi+40h]
0x18000c821  lea     rax, aDecremented; "decremented"
0x18000c828  test    r13b, r13b
0x18000c82b  lea     r9, aIncremented; "incremented"
0x18000c832  cmovz   r9, rax
0x18000c836  mov     eax, [r14+6ECh]
0x18000c83d  mov     [rsp+0C8h+var_50], eax
0x18000c841  mov     eax, [rsi+10Ch]
0x18000c847  mov     [rsp+0C8h+var_58], eax
0x18000c84b  mov     eax, [rdi]
0x18000c84d  mov     [rsp+0C8h+var_60], eax
0x18000c851  mov     eax, [rsi+88h]
0x18000c857  mov     [rsp+0C8h+var_68], eax
0x18000c85b  mov     rax, [rsi+30h]
0x18000c85f  mov     [rsp+0C8h+var_70], r9
0x18000c864  mov     [rsp+0C8h+var_78], rax
0x18000c869  mov     eax, [rsi+8]
0x18000c86c  mov     dword ptr [rsp+0C8h+var_80], eax
0x18000c870  mov     rax, [rdx+20h]
0x18000c874  mov     [rsp+0C8h+var_88], rax
0x18000c879  mov     [rsp+0C8h+var_98], 29h ; ')'
0x18000c880  jmp     loc_18000C92B
0x18000c885  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c88c  lea     rax, WPP_GLOBAL_Control
0x18000c893  cmp     rcx, rax
0x18000c896  jz      short loc_18000C8A7
0x18000c898  test    dword ptr [rcx+2Ch], 100h
0x18000c89f  jz      short loc_18000C8A7
0x18000c8a1  cmp     byte ptr [rcx+29h], 4
0x18000c8a5  jnb     short loc_18000C8A9
0x18000c8a7  xor     bl, bl
0x18000c8a9  lea     rax, WPP_RECORDER_INITIALIZED
0x18000c8b0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18000c8b7  setnz   r8b
0x18000c8bb  test    bl, bl
0x18000c8bd  jnz     short loc_18000C8C8
0x18000c8bf  test    r8b, r8b
0x18000c8c2  jz      loc_18000C70B
0x18000c8c8  mov     rdx, [rsi+40h]
0x18000c8cc  lea     rax, aDecremented; "decremented"
0x18000c8d3  test    r13b, r13b
0x18000c8d6  lea     r9, aIncremented; "incremented"
0x18000c8dd  cmovz   r9, rax
0x18000c8e1  mov     eax, [rsi+10Ch]
0x18000c8e7  mov     [rsp+0C8h+var_50], eax
0x18000c8eb  mov     eax, [r14+6ECh]
0x18000c8f2  mov     [rsp+0C8h+var_58], eax
0x18000c8f6  mov     eax, [rsi+88h]
0x18000c8fc  mov     [rsp+0C8h+var_60], eax
0x18000c900  mov     eax, [rdi]
0x18000c902  mov     [rsp+0C8h+var_68], eax
0x18000c906  mov     rax, [rsi+30h]
0x18000c90a  mov     [rsp+0C8h+var_70], r9
0x18000c90f  mov     [rsp+0C8h+var_78], rax
0x18000c914  mov     eax, [rsi+8]
0x18000c917  mov     dword ptr [rsp+0C8h+var_80], eax
0x18000c91b  mov     rax, [rdx+20h]
0x18000c91f  mov     [rsp+0C8h+var_88], rax
0x18000c924  mov     [rsp+0C8h+var_98], 2Ah ; '*'
0x18000c92b  mov     r9, [r14+2A0h]
0x18000c932  mov     dl, bl
0x18000c934  mov     rcx, [rcx+18h]
0x18000c938  call    WPP_RECORDER_AND_TRACE_SF_qdqsLLLL
0x18000c93d  jmp     loc_18000C70B
```
