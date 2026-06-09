# HbEvtpLocalDiagWriteBuffer

- ea: `0x140001bfc`
- end: `0x140001d4d`
- name: `HbEvtpLocalDiagWriteBuffer`
- size: `337`
- prototype: `__int64 __fastcall(__int64, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140011e18`

## callees

- `0x140001600`
- `0x140001bfc`
- `0x140001f6c`

## import_xrefs

- `ntoskrnl!KeLowerIrql` at `0x140001cdc`
- `ntoskrnl!KeLowerIrql` at `0x140001cdc`
- `ntoskrnl!EtwSendTraceBuffer` at `0x140001ccb`
- `ntoskrnl!EtwSendTraceBuffer` at `0x140001ccb`
- `ntoskrnl!KfRaiseIrql` at `0x140001ca1`
- `ntoskrnl!KfRaiseIrql` at `0x140001ca1`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140001d30`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140001d30`

## string_xrefs

- `0x140001c38`: `HbEvtpLocalDiagWriteBuffer`
- `0x140001c8c`: `HbEvtpLocalDiagWriteBuffer`
- `0x140001d01`: `HbEvtpLocalDiagWriteBuffer`

## pseudocode

```c
__int64 __fastcall HbEvtpLocalDiagWriteBuffer(__int64 a1, __int64 a2, __int64 *a3)
{
  __int64 v3; // rbp
  unsigned int *v4; // rdi
  __int16 v8; // ax
  KIRQL v9; // bl
  int v10; // r14d

  v3 = *a3;
  v4 = (unsigned int *)a3 + 21;
  if ( (int)HbEvtpTransferBufferOwnershipToEtw(a3) < 0 )
    HbpTraceEvent(0, "HbEvtpLocalDiagWriteBuffer", 3876, "Failure to transfer ownership of buffer %d to ETW", *v4);
  *(_DWORD *)v3 += 72;
  v8 = *(_WORD *)(a1 + 328);
  *(_DWORD *)(v3 + 48) += 72;
  *(_WORD *)(v3 + 42) = v8;
  *(_DWORD *)(v3 + 52) = 32;
  HbpTraceEvent(
    3,
    "HbEvtpLocalDiagWriteBuffer",
    3911,
    "Sending buffer %d to ETW logger 0x%x (state %d)",
    *v4,
    *(_QWORD *)(a1 + 328),
    *(_DWORD *)(v3 + 44));
  *(_DWORD *)(v3 + 60) = 0;
  v9 = KfRaiseIrql(2u);
  v10 = EtwSendTraceBuffer(
          *(_QWORD *)(a1 + 328),
          v3,
          *(unsigned int *)(v3 + 8),
          HbEvtpLocalDiagnosticsBufferCompletedCallback,
          *v4);
  KeLowerIrql(v9);
  if ( v10 < 0 )
  {
    *((_DWORD *)a3 + 22) = 0;
    HbpTraceEvent(
      1,
      "HbEvtpLocalDiagWriteBuffer",
      3930,
      "Error 0x%x sending buffer %d to ETW (state %d)",
      v10,
      *v4,
      *(_DWORD *)(v3 + 44));
    ExReleaseRundownProtection((PEX_RUNDOWN_REF)(*(_QWORD *)(a2 + 40) + 8LL * *v4));
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140001bfc  push    rbx
0x140001bfe  push    rbp
0x140001bff  push    rsi
0x140001c00  push    rdi
0x140001c01  push    r14
0x140001c03  push    r15
0x140001c05  sub     rsp, 48h
0x140001c09  mov     rbp, [r8]
0x140001c0c  lea     rdi, [r8+54h]
0x140001c10  mov     r14, rcx
0x140001c13  mov     rsi, r8
0x140001c16  mov     rcx, r8
0x140001c19  mov     r15, rdx
0x140001c1c  call    HbEvtpTransferBufferOwnershipToEtw
0x140001c21  test    eax, eax
0x140001c23  jns     short loc_140001C46
0x140001c25  mov     eax, [rdi]
0x140001c27  lea     r9, aFailureToTrans; "Failure to transfer ownership of buffer"...
0x140001c2e  mov     r8d, 0F24h
0x140001c34  mov     dword ptr [rsp+78h+var_58], eax
0x140001c38  lea     rdx, aHbevtplocaldia_2; "HbEvtpLocalDiagWriteBuffer"
0x140001c3f  xor     ecx, ecx
0x140001c41  call    HbpTraceEvent
0x140001c46  add     dword ptr [rbp+0], 48h ; 'H'
0x140001c4a  movzx   eax, word ptr [r14+148h]
0x140001c52  add     dword ptr [rbp+30h], 48h ; 'H'
0x140001c56  mov     [rbp+2Ah], ax
0x140001c5a  mov     dword ptr [rbp+34h], 20h ; ' '
0x140001c61  mov     rcx, [r14+148h]
0x140001c68  lea     r9, aSendingBufferD; "Sending buffer %d to ETW logger 0x%x (s"...
0x140001c6f  mov     edx, [rdi]
0x140001c71  mov     r8d, 0F47h
0x140001c77  mov     eax, [rbp+2Ch]
0x140001c7a  mov     [rsp+78h+var_48], eax
0x140001c7e  mov     [rsp+78h+var_50], rcx
0x140001c83  mov     ecx, 3
0x140001c88  mov     dword ptr [rsp+78h+var_58], edx
0x140001c8c  lea     rdx, aHbevtplocaldia_2; "HbEvtpLocalDiagWriteBuffer"
0x140001c93  call    HbpTraceEvent
0x140001c98  mov     cl, 2; NewIrql
0x140001c9a  mov     dword ptr [rbp+3Ch], 0
0x140001ca1  call    cs:__imp_KfRaiseIrql
0x140001ca8  nop     dword ptr [rax+rax+00h]
0x140001cad  mov     ecx, [rdi]
0x140001caf  lea     r9, HbEvtpLocalDiagnosticsBufferCompletedCallback
0x140001cb6  mov     r8d, [rbp+8]
0x140001cba  mov     rdx, rbp
0x140001cbd  mov     [rsp+78h+var_58], rcx
0x140001cc2  mov     bl, al
0x140001cc4  mov     rcx, [r14+148h]
0x140001ccb  call    cs:__imp_EtwSendTraceBuffer
0x140001cd2  nop     dword ptr [rax+rax+00h]
0x140001cd7  mov     cl, bl; NewIrql
0x140001cd9  mov     r14d, eax
0x140001cdc  call    cs:__imp_KeLowerIrql
0x140001ce3  nop     dword ptr [rax+rax+00h]
0x140001ce8  test    r14d, r14d
0x140001ceb  jns     short loc_140001D3C
0x140001ced  mov     dword ptr [rsi+58h], 0
0x140001cf4  mov     ecx, [rbp+2Ch]
0x140001cf7  lea     r9, aError0xXSendin; "Error 0x%x sending buffer %d to ETW (st"...
0x140001cfe  mov     r8d, [rdi]
0x140001d01  lea     rdx, aHbevtplocaldia_2; "HbEvtpLocalDiagWriteBuffer"
0x140001d08  mov     [rsp+78h+var_48], ecx
0x140001d0c  mov     ecx, 1
0x140001d11  mov     dword ptr [rsp+78h+var_50], r8d
0x140001d16  mov     r8d, 0F5Ah
0x140001d1c  mov     dword ptr [rsp+78h+var_58], r14d
0x140001d21  call    HbpTraceEvent
0x140001d26  mov     ecx, [rdi]
0x140001d28  mov     rax, [r15+28h]
0x140001d2c  lea     rcx, [rax+rcx*8]; RunRef
0x140001d30  call    cs:__imp_ExReleaseRundownProtection
0x140001d37  nop     dword ptr [rax+rax+00h]
0x140001d3c  mov     eax, r14d
0x140001d3f  add     rsp, 48h
0x140001d43  pop     r15
0x140001d45  pop     r14
0x140001d47  pop     rdi
0x140001d48  pop     rsi
0x140001d49  pop     rbp
0x140001d4a  pop     rbx
0x140001d4b  retn
```
