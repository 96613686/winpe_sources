# FIPfBlockedOpBlock

- ea: `0x14000ed40`
- end: `0x14000ef6a`
- name: `FIPfBlockedOpBlock`
- size: `554`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140010350`
- `0x140015a48`
- `0x140015d3c`
- `0x14001606c`

## callees

- `0x1400034a8`
- `0x1400035bc`
- `0x14000ed40`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14000ee59`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000ee59`
- `ntoskrnl!PsIsThreadTerminating` at `0x14000ee1e`
- `ntoskrnl!PsIsThreadTerminating` at `0x14000ee95`
- `ntoskrnl!PsIsThreadTerminating` at `0x14000ee1e`
- `ntoskrnl!PsIsThreadTerminating` at `0x14000ee95`
- `ntoskrnl!PsIsSystemThread` at `0x14000ede2`
- `ntoskrnl!PsIsSystemThread` at `0x14000ede2`
- `ntoskrnl!IoGetCurrentProcess` at `0x14000ed6e`
- `ntoskrnl!IoGetCurrentProcess` at `0x14000ed6e`
- `ntoskrnl!KeSetKernelStackSwapEnable` at `0x14000edf7`
- `ntoskrnl!KeSetKernelStackSwapEnable` at `0x14000ef2c`
- `ntoskrnl!KeSetKernelStackSwapEnable` at `0x14000edf7`
- `ntoskrnl!KeSetKernelStackSwapEnable` at `0x14000ef2c`

## pseudocode

```c
__int64 __fastcall FIPfBlockedOpBlock(__int64 a1, int a2)
{
  struct _KTHREAD *CurrentThread; // rsi
  PEPROCESS CurrentProcess; // rax
  int v6; // ecx
  __int64 v7; // rax
  volatile signed __int32 *v8; // rax
  KPROCESSOR_MODE v9; // r14
  BOOLEAN v10; // bp
  __int64 v11; // rdi
  union _LARGE_INTEGER *Timeout; // rax
  NTSTATUS v13; // eax
  unsigned int v14; // edi
  union _LARGE_INTEGER v16; // [rsp+60h] [rbp+8h] BYREF
  __int64 v17; // [rsp+70h] [rbp+18h]

  v16.QuadPart = 0;
  CurrentThread = KeGetCurrentThread();
  CurrentProcess = IoGetCurrentProcess();
  v6 = *(_DWORD *)(a1 + 112);
  *(_QWORD *)(a1 + 72) = CurrentProcess;
  *(_QWORD *)(a1 + 80) = CurrentThread;
  if ( (v6 & 8) != 0 )
  {
    _InterlockedIncrement(&dword_140009808);
    v7 = *(_QWORD *)(a1 + 96);
    if ( v7 )
      _InterlockedIncrement((volatile signed __int32 *)(v7 + 372));
  }
  else
  {
    v8 = *(volatile signed __int32 **)(a1 + 96);
    if ( (v6 & 2) != 0 )
    {
      _InterlockedIncrement(v8 + 94);
      _InterlockedIncrement(&dword_14000980C);
    }
    else if ( (v6 & 4) != 0 )
    {
      _InterlockedIncrement(v8 + 95);
      _InterlockedIncrement(&dword_140009810);
    }
    else
    {
      _InterlockedIncrement(v8 + 96);
      _InterlockedIncrement(&dword_140009814);
    }
  }
  if ( PsIsSystemThread(CurrentThread) )
  {
    _InterlockedIncrement(&dword_140009804);
    v10 = 0;
    v9 = 0;
  }
  else
  {
    v9 = 1;
    v10 = KeSetKernelStackSwapEnable(0);
  }
  v11 = (unsigned int)dword_1400093D8;
  if ( PsIsThreadTerminating(CurrentThread) )
  {
LABEL_20:
    _InterlockedIncrement((volatile signed __int32 *)&FIGlobals + *(int *)(a1 + 88) + 361);
LABEL_21:
    v14 = -1073741749;
  }
  else
  {
    if ( (_DWORD)v11 == -1 )
      goto LABEL_15;
    Timeout = &v16;
    v16.QuadPart = -10000 * v11;
    while ( 1 )
    {
      v13 = KeWaitForSingleObject((PVOID)(a1 + 48), Executive, v9, 0, Timeout);
      v14 = v13;
      if ( !v13 )
        break;
      if ( v13 == 192 )
      {
        _InterlockedIncrement((volatile signed __int32 *)&FIGlobals + *(int *)(a1 + 88) + 357);
        goto LABEL_21;
      }
      _InterlockedIncrement(&dword_140009818);
      FIPfBlockTimeoutDbgBreak(a1);
      FIPfBlockedOpTimeoutLiveKd(a1);
      if ( a2 )
        break;
      if ( PsIsThreadTerminating(CurrentThread) )
        goto LABEL_20;
LABEL_15:
      Timeout = 0;
    }
  }
  if ( (*(_DWORD *)(a1 + 112) & 0x20) != 0 )
    _InterlockedIncrement(&dword_1400097FC);
  _InterlockedIncrement(&dword_140009800);
  HIDWORD(v17) = _InterlockedIncrement(&dword_140009640);
  LODWORD(v17) = ((MEMORY[0xFFFFF78000000004] * MEMORY[0xFFFFF78000000324]) << 8)
               + ((MEMORY[0xFFFFF78000000320] * (unsigned __int64)MEMORY[0xFFFFF78000000004]) >> 24);
  *(_QWORD *)(a1 + 40) = v17;
  if ( v9 == 1 )
    KeSetKernelStackSwapEnable(v10);
  return v14;
}

```

## disassembly

```asm
0x14000ed40  mov     [rsp+arg_8], rbx
0x14000ed45  mov     [rsp+arg_18], rbp
0x14000ed4a  push    rsi
0x14000ed4b  push    rdi
0x14000ed4c  push    r12
0x14000ed4e  push    r14
0x14000ed50  push    r15
0x14000ed52  sub     rsp, 30h
0x14000ed56  mov     qword ptr [rsp+58h+arg_0], 0
0x14000ed5f  mov     r12d, edx
0x14000ed62  mov     rsi, gs:188h
0x14000ed6b  mov     rbx, rcx
0x14000ed6e  call    cs:__imp_IoGetCurrentProcess
0x14000ed75  nop     dword ptr [rax+rax+00h]
0x14000ed7a  mov     ecx, [rbx+70h]
0x14000ed7d  mov     [rbx+48h], rax
0x14000ed81  mov     [rbx+50h], rsi
0x14000ed85  test    cl, 8
0x14000ed88  jz      short loc_14000EDA3
0x14000ed8a  lock inc cs:dword_140009808
0x14000ed91  mov     rax, [rbx+60h]
0x14000ed95  test    rax, rax
0x14000ed98  jz      short loc_14000EDDF
0x14000ed9a  lock inc dword ptr [rax+174h]
0x14000eda1  jmp     short loc_14000EDDF
0x14000eda3  mov     rax, [rbx+60h]
0x14000eda7  test    cl, 2
0x14000edaa  jz      short loc_14000EDBC
0x14000edac  lock inc dword ptr [rax+178h]
0x14000edb3  lock inc cs:dword_14000980C
0x14000edba  jmp     short loc_14000EDDF
0x14000edbc  test    cl, 4
0x14000edbf  jz      short loc_14000EDD1
0x14000edc1  lock inc dword ptr [rax+17Ch]
0x14000edc8  lock inc cs:dword_140009810
0x14000edcf  jmp     short loc_14000EDDF
0x14000edd1  lock inc dword ptr [rax+180h]
0x14000edd8  lock inc cs:dword_140009814
0x14000eddf  mov     rcx, rsi; Thread
0x14000ede2  call    cs:__imp_PsIsSystemThread
0x14000ede9  nop     dword ptr [rax+rax+00h]
0x14000edee  test    al, al
0x14000edf0  jnz     short loc_14000EE08
0x14000edf2  xor     ecx, ecx; Enable
0x14000edf4  mov     r14b, 1
0x14000edf7  call    cs:__imp_KeSetKernelStackSwapEnable
0x14000edfe  nop     dword ptr [rax+rax+00h]
0x14000ee03  mov     bpl, al
0x14000ee06  jmp     short loc_14000EE15
0x14000ee08  lock inc cs:dword_140009804
0x14000ee0f  xor     bpl, bpl
0x14000ee12  xor     r14b, r14b
0x14000ee15  mov     edi, cs:dword_1400093D8
0x14000ee1b  mov     rcx, rsi; Thread
0x14000ee1e  call    cs:__imp_PsIsThreadTerminating
0x14000ee25  nop     dword ptr [rax+rax+00h]
0x14000ee2a  test    al, al
0x14000ee2c  jnz     short loc_14000EEA5
0x14000ee2e  cmp     edi, 0FFFFFFFFh
0x14000ee31  jz      short loc_14000EE46
0x14000ee33  imul    rcx, rdi, 0FFFFFFFFFFFFD8F0h
0x14000ee3a  lea     rax, [rsp+58h+arg_0]
0x14000ee3f  mov     qword ptr [rsp+58h+arg_0], rcx
0x14000ee44  jmp     short loc_14000EE48
0x14000ee46  xor     eax, eax
0x14000ee48  xor     r9d, r9d; Alertable
0x14000ee4b  mov     [rsp+58h+Timeout], rax; Timeout
0x14000ee50  mov     r8b, r14b; WaitMode
0x14000ee53  lea     rcx, [rbx+30h]; Object
0x14000ee57  xor     edx, edx; WaitReason
0x14000ee59  call    cs:__imp_KeWaitForSingleObject
0x14000ee60  nop     dword ptr [rax+rax+00h]
0x14000ee65  mov     edi, eax
0x14000ee67  test    eax, eax
0x14000ee69  jz      short loc_14000EEBD
0x14000ee6b  cmp     eax, 0C0h
0x14000ee70  jz      loc_14000EF52
0x14000ee76  lock inc cs:dword_140009818
0x14000ee7d  mov     rcx, rbx
0x14000ee80  call    FIPfBlockTimeoutDbgBreak
0x14000ee85  mov     rcx, rbx
0x14000ee88  call    FIPfBlockedOpTimeoutLiveKd
0x14000ee8d  test    r12d, r12d
0x14000ee90  jnz     short loc_14000EEBD
0x14000ee92  mov     rcx, rsi; Thread
0x14000ee95  call    cs:__imp_PsIsThreadTerminating
0x14000ee9c  nop     dword ptr [rax+rax+00h]
0x14000eea1  test    al, al
0x14000eea3  jz      short loc_14000EE46
0x14000eea5  movsxd  rax, dword ptr [rbx+58h]
0x14000eea9  lea     rcx, FIGlobals
0x14000eeb0  lock inc dword ptr [rcx+rax*4+5A4h]
0x14000eeb8  mov     edi, 0C000004Bh
0x14000eebd  mov     eax, [rbx+70h]
0x14000eec0  test    al, 20h
0x14000eec2  jz      short loc_14000EECB
0x14000eec4  lock inc cs:dword_1400097FC
0x14000eecb  lock inc cs:dword_140009800
0x14000eed2  mov     eax, 1
0x14000eed7  lock xadd cs:dword_140009640, eax
0x14000eedf  inc     eax
0x14000eee1  mov     rcx, 0FFFFF78000000320h
0x14000eeeb  mov     dword ptr [rsp+58h+arg_10+4], eax
0x14000eeef  mov     rcx, [rcx]
0x14000eef2  mov     eax, ds:0FFFFF78000000004h
0x14000eefb  mov     edx, ecx
0x14000eefd  mov     r8d, eax
0x14000ef00  imul    r8, rdx
0x14000ef04  shr     rcx, 20h
0x14000ef08  imul    ecx, eax
0x14000ef0b  shr     r8, 18h
0x14000ef0f  shl     ecx, 8
0x14000ef12  add     r8d, ecx
0x14000ef15  mov     dword ptr [rsp+58h+arg_10], r8d
0x14000ef1a  mov     rax, [rsp+58h+arg_10]
0x14000ef1f  mov     [rbx+28h], rax
0x14000ef23  cmp     r14b, 1
0x14000ef27  jnz     short loc_14000EF38
0x14000ef29  mov     cl, bpl; Enable
0x14000ef2c  call    cs:__imp_KeSetKernelStackSwapEnable
0x14000ef33  nop     dword ptr [rax+rax+00h]
0x14000ef38  mov     rbx, [rsp+58h+arg_8]
0x14000ef3d  mov     eax, edi
0x14000ef3f  mov     rbp, [rsp+58h+arg_18]
0x14000ef44  add     rsp, 30h
0x14000ef48  pop     r15
0x14000ef4a  pop     r14
0x14000ef4c  pop     r12
0x14000ef4e  pop     rdi
0x14000ef4f  pop     rsi
0x14000ef50  retn
0x14000ef52  movsxd  rax, dword ptr [rbx+58h]
0x14000ef56  lea     rcx, FIGlobals
0x14000ef5d  lock inc dword ptr [rcx+rax*4+594h]
0x14000ef65  jmp     loc_14000EEB8
```
