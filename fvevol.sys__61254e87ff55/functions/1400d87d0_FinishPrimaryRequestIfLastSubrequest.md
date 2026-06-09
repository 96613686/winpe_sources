# FinishPrimaryRequestIfLastSubrequest

- ea: `0x1400d87d0`
- end: `0x1400d89e4`
- name: `FinishPrimaryRequestIfLastSubrequest`
- size: `532`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter2)`
- caller_count: `6`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1400bc610`
- `0x1400d6968`
- `0x1400d8588`
- `0x1400dda80`
- `0x1400ed8f8`
- `0x1400edab0`

## callees

- `0x140008d94`
- `0x14002d140`
- `0x140031690`
- `0x1400d87d0`
- `0x1400d8aa8`
- `0x1400d8e60`
- `0x1400da368`

## import_xrefs

- `ntoskrnl!KeLowerIrql` at `0x1400d88f0`
- `ntoskrnl!KeLowerIrql` at `0x1400d88f0`
- `ntoskrnl!IofCompleteRequest` at `0x1400d88e1`
- `ntoskrnl!IofCompleteRequest` at `0x1400d88e1`
- `ntoskrnl!KfRaiseIrql` at `0x1400d88cd`
- `ntoskrnl!KfRaiseIrql` at `0x1400d88cd`
- `ntoskrnl!KeBugCheckEx` at `0x1400d8933`
- `ntoskrnl!KeBugCheckEx` at `0x1400d8933`

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
            WPP_SF_qqd(WPP_GLOBAL_Control->AttachedDevice, 80, v12, v5, v7, v6);
          }
        }
        else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_qqd(WPP_GLOBAL_Control->AttachedDevice, 81, v12, v5, v7, 0);
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
0x1400d87d0  push    rbx
0x1400d87d2  sub     rsp, 40h
0x1400d87d6  mov     rbx, rcx
0x1400d87d9  mov     eax, 0FFFFFFFFh
0x1400d87de  lock xadd [rcx+8Ch], eax
0x1400d87e6  sub     eax, 1
0x1400d87e9  js      loc_1400D891C
0x1400d87ef  test    eax, eax
0x1400d87f1  jnz     loc_1400D8915
0x1400d87f7  mov     [rsp+48h+var_10], r14
0x1400d87fc  mov     r14, [rcx+30h]
0x1400d8800  cmp     [r14+348h], eax
0x1400d8807  jnz     loc_1400D8910
0x1400d880d  mov     [rsp+48h+arg_0], rbp
0x1400d8812  mov     ebp, [rcx+80h]
0x1400d8818  mov     [rsp+48h+arg_8], rsi
0x1400d881d  mov     rsi, [rcx]
0x1400d8820  mov     [rsp+48h+arg_10], rdi
0x1400d8825  mov     [rsp+48h+arg_18], r12
0x1400d882a  mov     r12d, [rcx+7Ch]
0x1400d882e  mov     rax, [rsi+0B8h]
0x1400d8835  mov     [rsp+48h+var_18], r15
0x1400d883a  movzx   r15d, byte ptr [rax]
0x1400d883e  cmp     ebp, 0C0000013h
0x1400d8844  jz      loc_1400D898A
0x1400d884a  cmp     ebp, 80000016h
0x1400d8850  jz      loc_1400D898A
0x1400d8856  cmp     dword ptr [rbx+58h], 0
0x1400d885a  ja      loc_1400D896D
0x1400d8860  mov     rdi, [rbx+30h]
0x1400d8864  mov     rdx, rbx
0x1400d8867  mov     rcx, rdi
0x1400d886a  call    ReleaseControl
0x1400d886f  mov     rcx, rdi
0x1400d8872  call    SignalResourceRelease
0x1400d8877  mov     rdi, [rsp+48h+arg_10]
0x1400d887c  test    rsi, rsi
0x1400d887f  jz      short loc_1400D88FC
0x1400d8881  lea     rax, FVE_PERF_READ_REQUEST_STOP
0x1400d8888  cmp     r15b, 4
0x1400d888c  lea     rdx, FVE_PERF_WRITE_REQUEST_STOP
0x1400d8893  mov     r8, rsi
0x1400d8896  cmovnz  rdx, rax
0x1400d889a  mov     rcx, r14
0x1400d889d  call    FvePerfTraceDevPtr
0x1400d88a2  test    ebp, ebp
0x1400d88a4  jnz     loc_1400D89AA
0x1400d88aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d88b1  lea     rax, WPP_GLOBAL_Control
0x1400d88b8  cmp     rcx, rax
0x1400d88bb  jz      short loc_1400D88C4
0x1400d88bd  mov     eax, [rcx+2Ch]
0x1400d88c0  test    al, al
0x1400d88c2  js      short loc_1400D8940
0x1400d88c4  mov     cl, 2; NewIrql
0x1400d88c6  mov     [rsi+30h], ebp
0x1400d88c9  mov     [rsi+38h], r12
0x1400d88cd  call    cs:__imp_KfRaiseIrql
0x1400d88d4  nop     dword ptr [rax+rax+00h]
0x1400d88d9  mov     dl, 1; PriorityBoost
0x1400d88db  mov     rcx, rsi; Irp
0x1400d88de  movzx   ebx, al
0x1400d88e1  call    cs:__imp_IofCompleteRequest
0x1400d88e8  nop     dword ptr [rax+rax+00h]
0x1400d88ed  movzx   ecx, bl; NewIrql
0x1400d88f0  call    cs:__imp_KeLowerIrql
0x1400d88f7  nop     dword ptr [rax+rax+00h]
0x1400d88fc  mov     rbp, [rsp+48h+arg_0]
0x1400d8901  mov     r12, [rsp+48h+arg_18]
0x1400d8906  mov     rsi, [rsp+48h+arg_8]
0x1400d890b  mov     r15, [rsp+48h+var_18]
0x1400d8910  mov     r14, [rsp+48h+var_10]
0x1400d8915  add     rsp, 40h
0x1400d8919  pop     rbx
0x1400d891a  retn
0x1400d891c  cdqe
0x1400d891e  xor     r9d, r9d; BugCheckParameter3
0x1400d8921  mov     r8, rbx; BugCheckParameter2
0x1400d8924  mov     [rsp+48h+BugCheckParameter4], rax; BugCheckParameter4
0x1400d8929  mov     edx, 0Bh; BugCheckParameter1
0x1400d892e  mov     ecx, 120h; BugCheckCode
0x1400d8933  call    cs:__imp_KeBugCheckEx
0x1400d8940  cmp     byte ptr [rcx+29h], 4
0x1400d8944  jb      loc_1400D88C4
0x1400d894a  mov     edx, 51h ; 'Q'
0x1400d894f  mov     [rsp+48h+var_20], 0
0x1400d8957  mov     rcx, [rcx+18h]
0x1400d895b  mov     r9, r14
0x1400d895e  mov     [rsp+48h+BugCheckParameter4], rsi
0x1400d8963  call    WPP_SF_qqd
0x1400d8968  jmp     loc_1400D88C4
0x1400d896d  mov     rdx, [rsi+0B8h]
0x1400d8974  mov     rcx, [rbx+38h]
0x1400d8978  mov     r8d, [rdx+8]
0x1400d897c  mov     rdx, [rdx+18h]
0x1400d8980  call    FveEowUnconvertedIoComplete
0x1400d8985  jmp     loc_1400D8860
0x1400d898a  mov     r8b, 1
0x1400d898d  mov     dword ptr [r14+344h], 1
0x1400d8998  mov     edx, 1Ah
0x1400d899d  mov     rcx, r14
0x1400d89a0  call    FveTestDevStateChange
0x1400d89a5  jmp     loc_1400D8856
0x1400d89aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d89b1  lea     rax, WPP_GLOBAL_Control
0x1400d89b8  cmp     rcx, rax
0x1400d89bb  jz      loc_1400D88C4
0x1400d89c1  mov     eax, [rcx+2Ch]
0x1400d89c4  test    al, al
0x1400d89c6  jns     loc_1400D88C4
0x1400d89cc  cmp     byte ptr [rcx+29h], 2
0x1400d89d0  jb      loc_1400D88C4
0x1400d89d6  mov     edx, 50h ; 'P'
0x1400d89db  mov     [rsp+48h+var_20], ebp
0x1400d89df  jmp     loc_1400D8957
```
