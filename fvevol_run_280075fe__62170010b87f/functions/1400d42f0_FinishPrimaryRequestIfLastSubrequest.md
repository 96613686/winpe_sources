# FinishPrimaryRequestIfLastSubrequest

- ea: `0x1400d42f0`
- end: `0x1400d4504`
- name: `FinishPrimaryRequestIfLastSubrequest`
- size: `532`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter2)`
- caller_count: `5`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1400d23d0`
- `0x1400d330c`
- `0x1400d3820`
- `0x1400d3a70`
- `0x1400d6d48`

## callees

- `0x140008cd4`
- `0x14002c140`
- `0x140030690`
- `0x1400d42f0`
- `0x1400d45c8`
- `0x1400d4980`
- `0x1400dd594`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x1400d43ed`
- `ntoskrnl!KfRaiseIrql` at `0x1400d43ed`
- `ntoskrnl!KeLowerIrql` at `0x1400d4410`
- `ntoskrnl!KeLowerIrql` at `0x1400d4410`
- `ntoskrnl!IofCompleteRequest` at `0x1400d4401`
- `ntoskrnl!IofCompleteRequest` at `0x1400d4401`
- `ntoskrnl!KeBugCheckEx` at `0x1400d4453`
- `ntoskrnl!KeBugCheckEx` at `0x1400d4453`

## pseudocode

```c
void __fastcall FinishPrimaryRequestIfLastSubrequest(unsigned int *BugCheckParameter2, __int64 a2, __int64 a3)
{
  int v4; // eax
  ULONGLONG v5; // r14
  NTSTATUS v6; // ebp
  IRP *v7; // rsi
  ULONG_PTR v8; // r12
  char v9; // r15
  __int64 v10; // rdi
  const EVENT_DESCRIPTOR *v11; // rdx
  __int64 v12; // r8
  KIRQL v13; // bl

  v4 = _InterlockedDecrement((volatile signed __int32 *)BugCheckParameter2 + 35);
  if ( v4 < 0 )
    KeBugCheckEx(0x120u, 0xBu, (ULONG_PTR)BugCheckParameter2, 0, v4);
  if ( !v4 )
  {
    v5 = *((_QWORD *)BugCheckParameter2 + 6);
    if ( !*(_DWORD *)(v5 + 840) )
    {
      v6 = BugCheckParameter2[32];
      v7 = *(IRP **)BugCheckParameter2;
      v8 = BugCheckParameter2[31];
      v9 = **(_BYTE **)(*(_QWORD *)BugCheckParameter2 + 184LL);
      if ( v6 == -1073741805 || v6 == -2147483626 )
      {
        LOBYTE(a3) = 1;
        *(_DWORD *)(v5 + 836) = 1;
        FveTestDevStateChange(v5, 26, a3);
      }
      if ( BugCheckParameter2[22] )
        ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))FveEowUnconvertedIoComplete)(
          *((_QWORD *)BugCheckParameter2 + 7),
          (LARGE_INTEGER)v7->Tail.Overlay.CurrentStackLocation->Parameters.Read.ByteOffset.QuadPart,
          v7->Tail.Overlay.CurrentStackLocation->Parameters.Read.Length);
      v10 = *((_QWORD *)BugCheckParameter2 + 6);
      ReleaseControl(v10, BugCheckParameter2);
      SignalResourceRelease(v10);
      if ( v7 )
      {
        v11 = (const EVENT_DESCRIPTOR *)FVE_PERF_WRITE_REQUEST_STOP;
        if ( v9 != 4 )
          v11 = &FVE_PERF_READ_REQUEST_STOP;
        FvePerfTraceDevPtr(v5, v11, (__int64)v7);
        if ( v6 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_qqd(WPP_GLOBAL_Control->AttachedDevice, 73, v12, v5, v7, v6);
          }
        }
        else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_qqd(WPP_GLOBAL_Control->AttachedDevice, 74, v12, v5, v7, 0);
        }
        v7->IoStatus.Status = v6;
        v7->IoStatus.Information = v8;
        v13 = KfRaiseIrql(2u);
        IofCompleteRequest(v7, 1);
        KeLowerIrql(v13);
      }
    }
  }
}

```

## disassembly

```asm
0x1400d42f0  push    rbx
0x1400d42f2  sub     rsp, 40h
0x1400d42f6  mov     rbx, rcx
0x1400d42f9  mov     eax, 0FFFFFFFFh
0x1400d42fe  lock xadd [rcx+8Ch], eax
0x1400d4306  sub     eax, 1
0x1400d4309  js      loc_1400D443C
0x1400d430f  test    eax, eax
0x1400d4311  jnz     loc_1400D4435
0x1400d4317  mov     [rsp+48h+var_10], r14
0x1400d431c  mov     r14, [rcx+30h]
0x1400d4320  cmp     [r14+348h], eax
0x1400d4327  jnz     loc_1400D4430
0x1400d432d  mov     [rsp+48h+arg_0], rbp
0x1400d4332  mov     ebp, [rcx+80h]
0x1400d4338  mov     [rsp+48h+arg_8], rsi
0x1400d433d  mov     rsi, [rcx]
0x1400d4340  mov     [rsp+48h+arg_10], rdi
0x1400d4345  mov     [rsp+48h+arg_18], r12
0x1400d434a  mov     r12d, [rcx+7Ch]
0x1400d434e  mov     rax, [rsi+0B8h]
0x1400d4355  mov     [rsp+48h+var_18], r15
0x1400d435a  movzx   r15d, byte ptr [rax]
0x1400d435e  cmp     ebp, 0C0000013h
0x1400d4364  jz      loc_1400D44AA
0x1400d436a  cmp     ebp, 80000016h
0x1400d4370  jz      loc_1400D44AA
0x1400d4376  cmp     dword ptr [rbx+58h], 0
0x1400d437a  ja      loc_1400D448D
0x1400d4380  mov     rdi, [rbx+30h]
0x1400d4384  mov     rdx, rbx
0x1400d4387  mov     rcx, rdi
0x1400d438a  call    ReleaseControl
0x1400d438f  mov     rcx, rdi
0x1400d4392  call    SignalResourceRelease
0x1400d4397  mov     rdi, [rsp+48h+arg_10]
0x1400d439c  test    rsi, rsi
0x1400d439f  jz      short loc_1400D441C
0x1400d43a1  lea     rax, FVE_PERF_READ_REQUEST_STOP
0x1400d43a8  cmp     r15b, 4
0x1400d43ac  lea     rdx, FVE_PERF_WRITE_REQUEST_STOP
0x1400d43b3  mov     r8, rsi
0x1400d43b6  cmovnz  rdx, rax
0x1400d43ba  mov     rcx, r14
0x1400d43bd  call    FvePerfTraceDevPtr
0x1400d43c2  test    ebp, ebp
0x1400d43c4  jnz     loc_1400D44CA
0x1400d43ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d43d1  lea     rax, WPP_GLOBAL_Control
0x1400d43d8  cmp     rcx, rax
0x1400d43db  jz      short loc_1400D43E4
0x1400d43dd  mov     eax, [rcx+2Ch]
0x1400d43e0  test    al, al
0x1400d43e2  js      short loc_1400D4460
0x1400d43e4  mov     cl, 2; NewIrql
0x1400d43e6  mov     [rsi+30h], ebp
0x1400d43e9  mov     [rsi+38h], r12
0x1400d43ed  call    cs:__imp_KfRaiseIrql
0x1400d43f4  nop     dword ptr [rax+rax+00h]
0x1400d43f9  mov     dl, 1; PriorityBoost
0x1400d43fb  mov     rcx, rsi; Irp
0x1400d43fe  movzx   ebx, al
0x1400d4401  call    cs:__imp_IofCompleteRequest
0x1400d4408  nop     dword ptr [rax+rax+00h]
0x1400d440d  movzx   ecx, bl; NewIrql
0x1400d4410  call    cs:__imp_KeLowerIrql
0x1400d4417  nop     dword ptr [rax+rax+00h]
0x1400d441c  mov     rbp, [rsp+48h+arg_0]
0x1400d4421  mov     r12, [rsp+48h+arg_18]
0x1400d4426  mov     rsi, [rsp+48h+arg_8]
0x1400d442b  mov     r15, [rsp+48h+var_18]
0x1400d4430  mov     r14, [rsp+48h+var_10]
0x1400d4435  add     rsp, 40h
0x1400d4439  pop     rbx
0x1400d443a  retn
0x1400d443c  cdqe
0x1400d443e  xor     r9d, r9d; BugCheckParameter3
0x1400d4441  mov     r8, rbx; BugCheckParameter2
0x1400d4444  mov     [rsp+48h+BugCheckParameter4], rax; BugCheckParameter4
0x1400d4449  mov     edx, 0Bh; BugCheckParameter1
0x1400d444e  mov     ecx, 120h; BugCheckCode
0x1400d4453  call    cs:__imp_KeBugCheckEx
0x1400d4460  cmp     byte ptr [rcx+29h], 4
0x1400d4464  jb      loc_1400D43E4
0x1400d446a  mov     edx, 4Ah ; 'J'
0x1400d446f  mov     [rsp+48h+var_20], 0
0x1400d4477  mov     rcx, [rcx+18h]
0x1400d447b  mov     r9, r14
0x1400d447e  mov     [rsp+48h+BugCheckParameter4], rsi
0x1400d4483  call    WPP_SF_qqd
0x1400d4488  jmp     loc_1400D43E4
0x1400d448d  mov     rdx, [rsi+0B8h]
0x1400d4494  mov     rcx, [rbx+38h]
0x1400d4498  mov     r8d, [rdx+8]
0x1400d449c  mov     rdx, [rdx+18h]
0x1400d44a0  call    FveEowUnconvertedIoComplete
0x1400d44a5  jmp     loc_1400D4380
0x1400d44aa  mov     r8b, 1
0x1400d44ad  mov     dword ptr [r14+344h], 1
0x1400d44b8  mov     edx, 1Ah
0x1400d44bd  mov     rcx, r14
0x1400d44c0  call    FveTestDevStateChange
0x1400d44c5  jmp     loc_1400D4376
0x1400d44ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d44d1  lea     rax, WPP_GLOBAL_Control
0x1400d44d8  cmp     rcx, rax
0x1400d44db  jz      loc_1400D43E4
0x1400d44e1  mov     eax, [rcx+2Ch]
0x1400d44e4  test    al, al
0x1400d44e6  jns     loc_1400D43E4
0x1400d44ec  cmp     byte ptr [rcx+29h], 2
0x1400d44f0  jb      loc_1400D43E4
0x1400d44f6  mov     edx, 49h ; 'I'
0x1400d44fb  mov     [rsp+48h+var_20], ebp
0x1400d44ff  jmp     loc_1400D4477
```
