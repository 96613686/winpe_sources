# ClasspDeviceLockFailurePowerIrpCompletion

- ea: `0x140029040`
- end: `0x1400291ca`
- name: `ClasspDeviceLockFailurePowerIrpCompletion`
- size: `394`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1400134a0`
- `0x1400181ec`
- `0x140018424`
- `0x140029040`
- `0x14003e430`

## import_xrefs

- `ntoskrnl!IoGetActivityIdIrp` at `0x14002915e`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14002915e`
- `ntoskrnl!PoStartNextPowerIrp` at `0x14002919a`
- `ntoskrnl!PoStartNextPowerIrp` at `0x14002919a`
- `ntoskrnl!PoSetPowerState` at `0x140029137`
- `ntoskrnl!PoSetPowerState` at `0x140029137`

## pseudocode

```c
__int64 __fastcall ClasspDeviceLockFailurePowerIrpCompletion(__int64 a1, IRP *a2, __int64 a3)
{
  __int64 v3; // rax
  _IO_STACK_LOCATION *CurrentStackLocation; // rbp
  __int64 v7; // rdi
  _DWORD *v9; // rax
  bool v10; // cl
  __int64 v11; // rax
  __int64 v12; // r8
  __int128 v14; // [rsp+20h] [rbp-48h] BYREF

  v3 = *(_QWORD *)(a3 + 32);
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v14 = 0;
  v7 = *(_QWORD *)(v3 + 64);
  LODWORD(v3) = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  *(_DWORD *)(v7 + 536) = v3;
  if ( (_DWORD)v3 == 1 )
  {
    v9 = *(_DWORD **)(v7 + 824);
    v10 = 0;
    if ( v9 )
      v10 = *v9 != 0;
    if ( *(_QWORD *)(*(_QWORD *)(v7 + 32) + 400LL)
      || *(_QWORD *)(v7 + 648) && (v11 = *(_QWORD *)(v7 + 1152)) != 0 && !*(_BYTE *)(v11 + 37)
      || v10 )
    {
      if ( v10 )
      {
        v12 = *(_QWORD *)(v7 + 824);
        if ( (MEMORY[0xFFFFF78000000014] - *(_QWORD *)(v12 + 48)) / 10000000LL >= *(unsigned int *)(v12 + 8) )
          *(_DWORD *)(v12 + 4) = 1;
      }
      ClasspEnableTimer(v7);
    }
  }
  PoSetPowerState(
    *(PDEVICE_OBJECT *)(a3 + 32),
    CurrentStackLocation->Parameters.Power.Type,
    CurrentStackLocation->Parameters.Power.State);
  *(_BYTE *)(a3 + 8) = 0;
  if ( a2->IoStatus.Status < 0 && ClassPnPETWEnabled )
  {
    IoGetActivityIdIrp(a2, &v14);
    ClasspWritePowerFailureEvent((int)&v14, a1, (__int64)a2);
  }
  ClassReleaseRemoveLock(*(PDEVICE_OBJECT *)(v7 + 8), a2);
  if ( a2->PendingReturned )
    a2->Tail.Overlay.CurrentStackLocation->Control |= 1u;
  PoStartNextPowerIrp(a2);
  return 0;
}

```

## disassembly

```asm
0x140029040  mov     [rsp+arg_18], rbx
0x140029045  push    rbp
0x140029046  push    rsi
0x140029047  push    rdi
0x140029048  push    r12
0x14002904a  push    r14
0x14002904c  sub     rsp, 40h
0x140029050  mov     rax, cs:__security_cookie
0x140029057  xor     rax, rsp
0x14002905a  mov     [rsp+68h+var_38], rax
0x14002905f  mov     rax, [r8+20h]
0x140029063  xorps   xmm0, xmm0
0x140029066  mov     rbp, [rdx+0B8h]
0x14002906d  mov     r12d, 1
0x140029073  movups  [rsp+68h+var_48], xmm0
0x140029078  mov     rsi, r8
0x14002907b  mov     rbx, rdx
0x14002907e  mov     rdi, [rax+40h]
0x140029082  mov     r14, rcx
0x140029085  mov     eax, [rbp+18h]
0x140029088  mov     [rdi+218h], eax
0x14002908e  cmp     eax, r12d
0x140029091  jnz     loc_14002912C
0x140029097  mov     rax, [rdi+338h]
0x14002909e  xor     cl, cl
0x1400290a0  test    rax, rax
0x1400290a3  jz      short loc_1400290AF
0x1400290a5  cmp     dword ptr [rax], 0
0x1400290a8  movzx   ecx, cl
0x1400290ab  cmovnz  ecx, r12d
0x1400290af  mov     rax, [rdi+20h]
0x1400290b3  cmp     qword ptr [rax+190h], 0
0x1400290bb  jnz     short loc_1400290DD
0x1400290bd  cmp     qword ptr [rdi+288h], 0
0x1400290c5  jz      short loc_1400290D9
0x1400290c7  mov     rax, [rdi+480h]
0x1400290ce  test    rax, rax
0x1400290d1  jz      short loc_1400290D9
0x1400290d3  cmp     byte ptr [rax+25h], 0
0x1400290d7  jz      short loc_1400290DD
0x1400290d9  test    cl, cl
0x1400290db  jz      short loc_14002912C
0x1400290dd  test    cl, cl
0x1400290df  jz      short loc_140029124
0x1400290e1  mov     rcx, 0FFFFF78000000014h
0x1400290eb  mov     rax, 0D6BF94D5E57A42BDh
0x1400290f5  mov     rcx, [rcx]
0x1400290f8  mov     r8, [rdi+338h]
0x1400290ff  sub     rcx, [r8+30h]
0x140029103  imul    rcx
0x140029106  add     rdx, rcx
0x140029109  sar     rdx, 17h
0x14002910d  mov     rax, rdx
0x140029110  shr     rax, 3Fh
0x140029114  add     rdx, rax
0x140029117  mov     eax, [r8+8]
0x14002911b  cmp     rdx, rax
0x14002911e  jl      short loc_140029124
0x140029120  mov     [r8+4], r12d
0x140029124  mov     rcx, rdi
0x140029127  call    ClasspEnableTimer
0x14002912c  mov     r8d, [rbp+18h]; State
0x140029130  mov     edx, [rbp+10h]; Type
0x140029133  mov     rcx, [rsi+20h]; DeviceObject
0x140029137  call    cs:__imp_PoSetPowerState
0x14002913e  nop     dword ptr [rax+rax+00h]
0x140029143  mov     byte ptr [rsi+8], 0
0x140029147  cmp     dword ptr [rbx+30h], 0
0x14002914b  jge     short loc_14002917A
0x14002914d  cmp     cs:ClassPnPETWEnabled, 0
0x140029154  jz      short loc_14002917A
0x140029156  lea     rdx, [rsp+68h+var_48]
0x14002915b  mov     rcx, rbx
0x14002915e  call    cs:__imp_IoGetActivityIdIrp
0x140029165  nop     dword ptr [rax+rax+00h]
0x14002916a  mov     r8, rbx
0x14002916d  lea     rcx, [rsp+68h+var_48]
0x140029172  mov     rdx, r14
0x140029175  call    ClasspWritePowerFailureEvent
0x14002917a  mov     rcx, [rdi+8]; DeviceObject
0x14002917e  mov     rdx, rbx; Tag
0x140029181  call    ClassReleaseRemoveLock
0x140029186  cmp     byte ptr [rbx+41h], 0
0x14002918a  jz      short loc_140029197
0x14002918c  mov     rax, [rbx+0B8h]
0x140029193  or      [rax+3], r12b
0x140029197  mov     rcx, rbx; Irp
0x14002919a  call    cs:__imp_PoStartNextPowerIrp
0x1400291a1  nop     dword ptr [rax+rax+00h]
0x1400291a6  xor     eax, eax
0x1400291a8  mov     rcx, [rsp+68h+var_38]
0x1400291ad  xor     rcx, rsp; StackCookie
0x1400291b0  call    __security_check_cookie
0x1400291b5  mov     rbx, [rsp+68h+arg_18]
0x1400291bd  add     rsp, 40h
0x1400291c1  pop     r14
0x1400291c3  pop     r12
0x1400291c5  pop     rdi
0x1400291c6  pop     rsi
0x1400291c7  pop     rbp
0x1400291c8  retn
```
