# FltpAllocateCallbackDataMustSucceed

- ea: `0x180019520`
- end: `0x180019689`
- name: `FltpAllocateCallbackDataMustSucceed`
- size: `361`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180060330`
- `0x18006f920`

## callees

- `0x180009f20`
- `0x18000a360`
- `0x180019520`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x180019612`
- `ntoskrnl!KeDelayExecutionThread` at `0x180019644`
- `ntoskrnl!KeDelayExecutionThread` at `0x180019612`
- `ntoskrnl!KeDelayExecutionThread` at `0x180019644`
- `ntoskrnl!IoAllocateIrpEx` at `0x1800195b2`
- `ntoskrnl!IoAllocateIrpEx` at `0x180019628`
- `ntoskrnl!IoAllocateIrpEx` at `0x1800195b2`
- `ntoskrnl!IoAllocateIrpEx` at `0x180019628`

## pseudocode

```c
__int64 __fastcall FltpAllocateCallbackDataMustSucceed(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4)
{
  __int64 v4; // rbx
  __int64 v8; // rbx
  unsigned int IrpCtrlInternal; // eax
  unsigned __int8 v10; // bp
  char *v11; // rdi
  char *v12; // rsi
  __int64 result; // rax
  unsigned int v14; // eax
  __int64 v15; // [rsp+20h] [rbp-48h]
  __int64 v16; // [rsp+20h] [rbp-48h]
  LARGE_INTEGER Interval; // [rsp+70h] [rbp+8h] BYREF
  char *v18; // [rsp+78h] [rbp+10h] BYREF

  v4 = *(_QWORD *)(a1 + 64);
  Interval.QuadPart = -100000;
  v8 = *(_QWORD *)(v4 + 64);
  v18 = 0;
  IrpCtrlInternal = FltpAllocateIrpCtrlInternal(v8, 0, 0, (PSLIST_ENTRY *)&v18, v15, (__int64)&Interval);
  if ( (int)FltpDbgStatus(IrpCtrlInternal, "minkernel\\fs\\filtermgr\\filter\\allocateirpctrlsup.c", 951, 0) < 0 )
  {
    do
    {
      KeDelayExecutionThread(0, 0, &Interval);
      v14 = FltpAllocateIrpCtrlInternal(v8, 0, 0, (PSLIST_ENTRY *)&v18, v16, (__int64)&Interval);
    }
    while ( (int)FltpDbgStatus(v14, "minkernel\\fs\\filtermgr\\filter\\allocateirpctrlsup.c", 951, 0) < 0 );
  }
  v10 = *(_BYTE *)(v8 + 76);
  v11 = v18;
  Interval.QuadPart = 0;
  v12 = v18 + 232;
  for ( result = IoAllocateIrpEx(v8, v10, 0); !result; result = IoAllocateIrpEx(v8, v10, 0) )
  {
    Interval.QuadPart = -100000;
    KeDelayExecutionThread(0, 0, &Interval);
  }
  *((_QWORD *)v11 + 6) = result;
  *((_DWORD *)v11 + 1) |= 0x1000000u;
  *((_QWORD *)v11 + 13) = v8;
  *((_QWORD *)v11 + 14) = a2;
  *((_QWORD *)v11 + 9) = a1;
  *a4 = v12;
  return result;
}

```

## disassembly

```asm
0x180019520  mov     [rsp+arg_10], rbx
0x180019525  push    rbp
0x180019526  push    rsi
0x180019527  push    rdi
0x180019528  push    r12
0x18001952a  push    r13
0x18001952c  push    r14
0x18001952e  push    r15
0x180019530  sub     rsp, 30h
0x180019534  mov     rbx, [rcx+40h]
0x180019538  lea     rax, [rsp+68h+Interval]
0x18001953d  mov     r15, r9
0x180019540  mov     qword ptr [rsp+68h+Interval], 0FFFFFFFFFFFE7960h
0x180019549  mov     r12, rdx
0x18001954c  mov     [rsp+68h+var_40], rax
0x180019551  mov     r14, rcx
0x180019554  lea     r9, [rsp+68h+arg_8]
0x180019559  mov     rbx, [rbx+40h]
0x18001955d  xor     r13d, r13d
0x180019560  mov     rcx, rbx
0x180019563  mov     [rsp+68h+arg_8], r13
0x180019568  xor     r8d, r8d
0x18001956b  xor     edx, edx
0x18001956d  call    FltpAllocateIrpCtrlInternal
0x180019572  mov     edi, 3B7h
0x180019577  lea     rdx, aMinkernelFsFil_1; "minkernel\\fs\\filtermgr\\filter\\alloc"...
0x18001957e  mov     r8d, edi
0x180019581  xor     r9d, r9d
0x180019584  mov     ecx, eax
0x180019586  call    FltpDbgStatus
0x18001958b  test    eax, eax
0x18001958d  js      loc_18001963B
0x180019593  movzx   ebp, byte ptr [rbx+4Ch]
0x180019597  xor     r8d, r8d
0x18001959a  mov     rdi, [rsp+68h+arg_8]
0x18001959f  movzx   edx, bpl
0x1800195a3  mov     rcx, rbx
0x1800195a6  mov     qword ptr [rsp+68h+Interval], r13
0x1800195ab  lea     rsi, [rdi+0E8h]
0x1800195b2  call    cs:__imp_IoAllocateIrpEx
0x1800195b9  nop     dword ptr [rax+rax+00h]
0x1800195be  test    rax, rax
0x1800195c1  jz      short loc_180019600
0x1800195c3  mov     [rdi+30h], rax
0x1800195c7  or      dword ptr [rdi+4], 1000000h
0x1800195ce  mov     [rdi+68h], rbx
0x1800195d2  mov     rbx, [rsp+68h+arg_10]
0x1800195da  mov     [rdi+70h], r12
0x1800195de  mov     [rdi+48h], r14
0x1800195e2  mov     [r15], rsi
0x1800195e5  add     rsp, 30h
0x1800195e9  pop     r15
0x1800195eb  pop     r14
0x1800195ed  pop     r13
0x1800195ef  pop     r12
0x1800195f1  pop     rdi
0x1800195f2  pop     rsi
0x1800195f3  pop     rbp
0x1800195f4  retn
0x180019600  lea     r8, [rsp+68h+Interval]; Interval
0x180019605  mov     qword ptr [rsp+68h+Interval], 0FFFFFFFFFFFE7960h
0x18001960e  xor     edx, edx; Alertable
0x180019610  xor     ecx, ecx; WaitMode
0x180019612  call    cs:__imp_KeDelayExecutionThread
0x180019619  nop     dword ptr [rax+rax+00h]
0x18001961e  xor     r8d, r8d
0x180019621  movzx   edx, bpl
0x180019625  mov     rcx, rbx
0x180019628  call    cs:__imp_IoAllocateIrpEx
0x18001962f  nop     dword ptr [rax+rax+00h]
0x180019634  test    rax, rax
0x180019637  jnz     short loc_1800195C3
0x180019639  jmp     short loc_180019600
0x18001963b  lea     r8, [rsp+68h+Interval]; Interval
0x180019640  xor     edx, edx; Alertable
0x180019642  xor     ecx, ecx; WaitMode
0x180019644  call    cs:__imp_KeDelayExecutionThread
0x18001964b  nop     dword ptr [rax+rax+00h]
0x180019650  lea     rax, [rsp+68h+Interval]
0x180019655  xor     r8d, r8d
0x180019658  lea     r9, [rsp+68h+arg_8]
0x18001965d  mov     [rsp+68h+var_40], rax
0x180019662  xor     edx, edx
0x180019664  mov     rcx, rbx
0x180019667  call    FltpAllocateIrpCtrlInternal
0x18001966c  xor     r9d, r9d
0x18001966f  lea     rdx, aMinkernelFsFil_1; "minkernel\\fs\\filtermgr\\filter\\alloc"...
0x180019676  mov     r8d, edi
0x180019679  mov     ecx, eax
0x18001967b  call    FltpDbgStatus
0x180019680  test    eax, eax
0x180019682  js      short loc_18001963B
0x180019684  jmp     loc_180019593
```
