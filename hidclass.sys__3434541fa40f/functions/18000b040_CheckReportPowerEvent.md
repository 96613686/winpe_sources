# CheckReportPowerEvent

- ea: `0x18000b040`
- end: `0x18000b139`
- name: `CheckReportPowerEvent`
- size: `249`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x18000ac70`

## callees

- `0x18000b040`

## import_xrefs

- `ntoskrnl!MmBadPointer` at `0x18000b0b5`
- `ntoskrnl!MmBadPointer` at `0x18000b0d3`
- `ntoskrnl!IofCompleteRequest` at `0x18000b123`
- `ntoskrnl!IofCompleteRequest` at `0x18000b123`
- `ntoskrnl!KeReleaseSpinLock` at `0x18000b0ef`
- `ntoskrnl!KeReleaseSpinLock` at `0x18000b0ef`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18000b099`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18000b099`
- `HIDPARSE!HidP_SysPowerEvent` at `0x18000b068`
- `HIDPARSE!HidP_SysPowerEvent` at `0x18000b068`

## pseudocode

```c
void __fastcall CheckReportPowerEvent(__int64 a1, __int64 a2, CHAR *a3, USHORT a4)
{
  __int64 v5; // rdi
  KIRQL v6; // al
  volatile __int64 *v7; // rdx
  ULONG OutputBuffer; // [rsp+30h] [rbp+8h] BYREF
  int v9; // [rsp+34h] [rbp+Ch]

  v9 = HIDWORD(a1);
  OutputBuffer = 0;
  if ( HidP_SysPowerEvent(a3, a4, *(PHIDP_PREPARSED_DATA *)(a2 + 304), &OutputBuffer) >= 0 && OutputBuffer )
  {
    v5 = 0;
    v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 328));
    v7 = *(volatile __int64 **)(a2 + 320);
    if ( v7 && v7 != MmBadPointer )
    {
      v5 = *(_QWORD *)(a2 + 320);
      if ( !_InterlockedExchange64(v7 + 13, 0) )
        v5 = 0;
      *(_QWORD *)(a2 + 320) = MmBadPointer;
    }
    KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 328), v6);
    if ( v5 )
    {
      **(_DWORD **)(v5 + 24) = OutputBuffer;
      *(_QWORD *)(v5 + 56) = 4;
      *(_DWORD *)(v5 + 48) = 0;
      IofCompleteRequest((PIRP)v5, 0);
    }
  }
}

```

## disassembly

```asm
0x18000b040  mov     qword ptr [rsp+OutputBuffer], rcx
0x18000b045  push    rbx
0x18000b046  sub     rsp, 20h
0x18000b04a  mov     rbx, rdx
0x18000b04d  mov     [rsp+28h+OutputBuffer], 0
0x18000b055  mov     rcx, r8; HidPacket
0x18000b058  movzx   edx, r9w; HidPacketLength
0x18000b05c  lea     r9, [rsp+28h+OutputBuffer]; OutputBuffer
0x18000b061  mov     r8, [rbx+130h]; Ppd
0x18000b068  call    cs:__imp_HidP_SysPowerEvent
0x18000b06f  nop     dword ptr [rax+rax+00h]
0x18000b074  test    eax, eax
0x18000b076  jns     short loc_18000B07F
0x18000b078  add     rsp, 20h
0x18000b07c  pop     rbx
0x18000b07d  retn
0x18000b07f  cmp     [rsp+28h+OutputBuffer], 0
0x18000b084  jz      short loc_18000B078
0x18000b086  mov     [rsp+28h+arg_8], rsi
0x18000b08b  lea     rcx, [rbx+148h]; SpinLock
0x18000b092  mov     [rsp+28h+arg_10], rdi
0x18000b097  xor     edi, edi
0x18000b099  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x18000b0a0  nop     dword ptr [rax+rax+00h]
0x18000b0a5  mov     rdx, [rbx+140h]
0x18000b0ac  movzx   r8d, al
0x18000b0b0  test    rdx, rdx
0x18000b0b3  jz      short loc_18000B0E4
0x18000b0b5  mov     rcx, cs:MmBadPointer
0x18000b0bc  cmp     rdx, [rcx]
0x18000b0bf  jz      short loc_18000B0E4
0x18000b0c1  xor     ecx, ecx
0x18000b0c3  xor     eax, eax
0x18000b0c5  xchg    rcx, [rdx+68h]
0x18000b0c9  test    rcx, rcx
0x18000b0cc  mov     rdi, rdx
0x18000b0cf  cmovz   rdi, rax
0x18000b0d3  mov     rax, cs:MmBadPointer
0x18000b0da  mov     rcx, [rax]
0x18000b0dd  mov     [rbx+140h], rcx
0x18000b0e4  movzx   edx, r8b; NewIrql
0x18000b0e8  lea     rcx, [rbx+148h]; SpinLock
0x18000b0ef  call    cs:__imp_KeReleaseSpinLock
0x18000b0f6  nop     dword ptr [rax+rax+00h]
0x18000b0fb  mov     rsi, [rsp+28h+arg_8]
0x18000b100  test    rdi, rdi
0x18000b103  jz      short loc_18000B12F
0x18000b105  mov     eax, [rsp+28h+OutputBuffer]
0x18000b109  mov     rcx, rdi; Irp
0x18000b10c  mov     rdx, [rdi+18h]
0x18000b110  mov     [rdx], eax
0x18000b112  xor     edx, edx; PriorityBoost
0x18000b114  mov     qword ptr [rdi+38h], 4
0x18000b11c  mov     dword ptr [rdi+30h], 0
0x18000b123  call    cs:__imp_IofCompleteRequest
0x18000b12a  nop     dword ptr [rax+rax+00h]
0x18000b12f  mov     rdi, [rsp+28h+arg_10]
0x18000b134  jmp     loc_18000B078
```
