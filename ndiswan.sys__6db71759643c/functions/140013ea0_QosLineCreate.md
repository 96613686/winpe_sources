# QosLineCreate

- ea: `0x140013ea0`
- end: `0x140013f42`
- name: `QosLineCreate`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x140011fdc`

## callees

- `0x140009368`
- `0x1400141c0`
- `0x140016700`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140013edf`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140013edf`

## pseudocode

```c
unsigned __int64 __fastcall QosLineCreate(__int64 a1, __int64 a2, __int64 a3)
{
  ULONG CurrentProcessorNumber; // eax
  __int64 v6; // rdx
  __int64 CurrentTime; // rax
  __int64 v8; // r8
  unsigned __int64 v9; // rbx
  unsigned __int64 result; // rax
  unsigned __int64 v11; // rbx
  __int64 v12; // [rsp+38h] [rbp+10h] BYREF

  v12 = a2;
  memset((void *)a1, 0, 0xD8u);
  *(_QWORD *)(a1 + 32) = BwcGenericObjectHandle;
  *(_QWORD *)(a1 + 40) = BwcSendNblPoolHandle;
  CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
  LOBYTE(v6) = 1;
  CurrentTime = QosTimerGetCurrentTime(CurrentProcessorNumber, v6, 0);
  v8 = -1;
  v9 = CurrentTime;
  if ( a3 )
    v8 = a3;
  QosLineUpdate(a1, &v12, v8, 0);
  result = v9 / *(unsigned int *)(a1 + 116);
  v11 = v9 - v9 % *(unsigned int *)(a1 + 116);
  *(_QWORD *)(a1 + 160) = v11;
  *(_QWORD *)(a1 + 168) = v11;
  return result;
}

```

## disassembly

```asm
0x140013ea0  mov     [rsp+arg_0], rbx
0x140013ea5  mov     [rsp+arg_10], rsi
0x140013eaa  mov     [rsp+arg_8], rdx
0x140013eaf  push    rdi
0x140013eb0  sub     rsp, 20h
0x140013eb4  mov     rdi, r8
0x140013eb7  xor     edx, edx; Val
0x140013eb9  mov     r8d, 0D8h; Size
0x140013ebf  mov     rsi, rcx
0x140013ec2  call    memset
0x140013ec7  mov     rax, cs:BwcGenericObjectHandle
0x140013ece  xor     ecx, ecx; ProcNumber
0x140013ed0  mov     [rsi+20h], rax
0x140013ed4  mov     rax, cs:BwcSendNblPoolHandle
0x140013edb  mov     [rsi+28h], rax
0x140013edf  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140013ee6  nop     dword ptr [rax+rax+00h]
0x140013eeb  xor     r8d, r8d
0x140013eee  mov     dl, 1
0x140013ef0  mov     ecx, eax
0x140013ef2  call    QosTimerGetCurrentTime
0x140013ef7  or      r8, 0FFFFFFFFFFFFFFFFh
0x140013efb  lea     rdx, [rsp+28h+arg_8]
0x140013f00  test    rdi, rdi
0x140013f03  mov     rcx, rsi
0x140013f06  mov     rbx, rax
0x140013f09  cmovnz  r8, rdi
0x140013f0d  xor     r9d, r9d
0x140013f10  call    QosLineUpdate
0x140013f15  mov     ecx, [rsi+74h]
0x140013f18  mov     rax, rbx
0x140013f1b  xor     edx, edx
0x140013f1d  div     rcx
0x140013f20  sub     rbx, rdx
0x140013f23  mov     [rsi+0A0h], rbx
0x140013f2a  mov     [rsi+0A8h], rbx
0x140013f31  mov     rbx, [rsp+28h+arg_0]
0x140013f36  mov     rsi, [rsp+28h+arg_10]
0x140013f3b  add     rsp, 20h
0x140013f3f  pop     rdi
0x140013f40  retn
```
