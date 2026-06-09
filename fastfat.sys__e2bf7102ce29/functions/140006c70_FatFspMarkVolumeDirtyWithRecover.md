# FatFspMarkVolumeDirtyWithRecover

- ea: `0x140006c70`
- end: `0x140006d49`
- name: `FatFspMarkVolumeDirtyWithRecover`
- size: `217`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140005288`
- `0x140006c70`
- `0x140006dbc`
- `0x14000c680`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140006d27`
- `ntoskrnl!IofCompleteRequest` at `0x140006d27`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140006cbe`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140006cfa`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140006cbe`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140006cfa`
- `ntoskrnl!KeSetEvent` at `0x140006d14`
- `ntoskrnl!KeSetEvent` at `0x140006d14`

## pseudocode

```c
void __fastcall FatFspMarkVolumeDirtyWithRecover(_QWORD *a1)
{
  __int64 v2; // rsi
  IRP *v3; // rdi
  struct _KEVENT *v4; // rcx
  _QWORD v5[18]; // [rsp+20h] [rbp-98h] BYREF

  v2 = a1[5];
  v3 = (IRP *)a1[4];
  memset(v5, 0, sizeof(v5));
  HIDWORD(v5[8]) = 2;
  v5[5] = v3;
  IoSetTopLevelIrp((PIRP)1);
  _InterlockedOr((volatile signed __int32 *)(v2 + 200), 0x10u);
  FatMarkVolume((__int64)v5, v2, 2);
  IoSetTopLevelIrp(0);
  v4 = (struct _KEVENT *)a1[6];
  if ( v4 )
    KeSetEvent(v4, 0, 0);
  else
    IofCompleteRequest(v3, 1);
}

```

## disassembly

```asm
0x140006c70  mov     [rsp+arg_10], rbx
0x140006c75  mov     [rsp+arg_18], rsi
0x140006c7a  mov     [rsp+arg_0], rcx
0x140006c7f  push    rdi
0x140006c80  sub     rsp, 0B0h
0x140006c87  mov     rbx, rcx
0x140006c8a  mov     rsi, [rcx+28h]
0x140006c8e  mov     rdi, [rcx+20h]
0x140006c92  mov     [rsp+0B8h+arg_8], rdi
0x140006c9a  xor     edx, edx; Val
0x140006c9c  mov     r8d, 90h; Size
0x140006ca2  lea     rcx, [rsp+0B8h+var_98]; void *
0x140006ca7  call    memset
0x140006cac  mov     [rsp+0B8h+var_54], 2
0x140006cb4  mov     [rsp+0B8h+var_70], rdi
0x140006cb9  mov     ecx, 1; Irp
0x140006cbe  call    cs:__imp_IoSetTopLevelIrp
0x140006cc5  nop     dword ptr [rax+rax+00h]
0x140006cca  nop
0x140006ccb  lock or dword ptr [rsi+0C8h], 10h
0x140006cd3  mov     r8d, 2
0x140006cd9  mov     rdx, rsi
0x140006cdc  lea     rcx, [rsp+0B8h+var_98]
0x140006ce1  call    FatMarkVolume
0x140006ce6  jmp     short loc_140006CF8
0x140006ce8  mov     rbx, [rsp+0B8h+arg_0]
0x140006cf0  mov     rdi, [rsp+0B8h+arg_8]
0x140006cf8  xor     ecx, ecx; Irp
0x140006cfa  call    cs:__imp_IoSetTopLevelIrp
0x140006d01  nop     dword ptr [rax+rax+00h]
0x140006d06  mov     rcx, [rbx+30h]; Event
0x140006d0a  test    rcx, rcx
0x140006d0d  jz      short loc_140006D22
0x140006d0f  xor     r8d, r8d; Wait
0x140006d12  xor     edx, edx; Increment
0x140006d14  call    cs:__imp_KeSetEvent
0x140006d1b  nop     dword ptr [rax+rax+00h]
0x140006d20  jmp     short loc_140006D33
0x140006d22  mov     dl, 1; PriorityBoost
0x140006d24  mov     rcx, rdi; Irp
0x140006d27  call    cs:__imp_IofCompleteRequest
0x140006d2e  nop     dword ptr [rax+rax+00h]
0x140006d33  lea     r11, [rsp+0B8h+var_8]
0x140006d3b  mov     rbx, [r11+20h]
0x140006d3f  mov     rsi, [r11+28h]
0x140006d43  mov     rsp, r11
0x140006d46  pop     rdi
0x140006d47  retn
0x14000d336  push    rbp
0x14000d338  sub     rsp, 20h
0x14000d33c  mov     rbp, rdx
0x14000d33f  mov     rdx, rcx
0x14000d342  lea     rcx, [rbp+20h]
0x14000d346  call    FatExceptionFilter
0x14000d34b  nop
0x14000d34c  add     rsp, 20h
0x14000d350  pop     rbp
0x14000d351  retn
```
