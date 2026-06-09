# SdpServiceAttributeSearchInternal

- ea: `0x14001ade8`
- end: `0x14001af4d`
- name: `SdpServiceAttributeSearchInternal`
- size: `357`
- prototype: `__int64 __usercall@<rax>(PDEVICE_OBJECT DeviceObject@<rcx>, __int64, __int16, __int16, __int64, __int64, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x14001ba60`
- `0x14001bb50`

## callees

- `0x14001a3a8`
- `0x14001ade8`
- `0x14001fc70`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x14001aefe`
- `ntoskrnl!IofCallDriver` at `0x14001aefe`
- `ntoskrnl!ExAllocatePool2` at `0x14001ae28`
- `ntoskrnl!ExAllocatePool2` at `0x14001ae28`
- `ntoskrnl!ExFreePool` at `0x14001af2a`
- `ntoskrnl!ExFreePool` at `0x14001af2a`

## pseudocode

```c
__int64 __fastcall SdpServiceAttributeSearchInternal(
        PDEVICE_OBJECT DeviceObject,
        struct _DEVICE_OBJECT *a2,
        __int64 a3,
        int a4,
        __int128 *a5,
        __int16 a6,
        __int16 a7,
        void (__fastcall *a8)(__int64, _QWORD, _QWORD, __int64),
        __int64 a9,
        unsigned int a10)
{
  unsigned __int64 v14; // rdx
  char *Pool2; // rax
  __int64 v16; // r9
  void *v17; // rbx
  __int128 v18; // xmm0
  IRP *v19; // rax

  v14 = a10 + 81LL;
  if ( v14 < 0x148 )
    v14 = 328;
  Pool2 = (char *)ExAllocatePool2(64, v14, 1146311746);
  v17 = Pool2;
  if ( !Pool2 )
    goto LABEL_6;
  *(_QWORD *)Pool2 = DeviceObject;
  *((_QWORD *)Pool2 + 1) = a2;
  *((_DWORD *)Pool2 + 4) = a10;
  *((_DWORD *)Pool2 + 8) = a4;
  v18 = *a5;
  *((_WORD *)Pool2 + 26) = a6;
  *(_OWORD *)(Pool2 + 36) = v18;
  *((_QWORD *)Pool2 + 7) = a8;
  *((_QWORD *)Pool2 + 8) = a9;
  *((_WORD *)Pool2 + 27) = a7;
  *((_WORD *)Pool2 + 162) = a6;
  *((_QWORD *)Pool2 + 3) = a3;
  *((_WORD *)Pool2 + 50) = 1072;
  *(_OWORD *)(Pool2 + 84) = v18;
  *((_WORD *)Pool2 + 163) = a7;
  *((_QWORD *)Pool2 + 9) = a3;
  *((_DWORD *)Pool2 + 20) = a4;
  v19 = IrpBuildIoctlEx(
          (__int64)DeviceObject,
          a2,
          0,
          v16,
          0x410210u,
          (_IRP *)(Pool2 + 72),
          0x100u,
          a10 + 9,
          (IO_COMPLETION_ROUTINE *)SdppServiceAttributeSearchCompletionRoutine,
          Pool2);
  if ( v19 )
  {
    IofCallDriver(DeviceObject, v19);
  }
  else
  {
LABEL_6:
    a8(a9, 0, 0, 3221225626LL);
    if ( v17 )
      ExFreePool(v17);
  }
  return 259;
}

```

## disassembly

```asm
0x14001ade8  push    rbx
0x14001adea  push    rbp
0x14001adeb  push    rsi
0x14001adec  push    rdi
0x14001aded  push    r12
0x14001adef  push    r13
0x14001adf1  push    r14
0x14001adf3  push    r15
0x14001adf5  sub     rsp, 58h
0x14001adf9  mov     r14d, [rsp+98h+arg_48]
0x14001ae01  mov     r13, rdx
0x14001ae04  mov     eax, 148h
0x14001ae09  mov     r12, r8
0x14001ae0c  mov     rdi, rcx
0x14001ae0f  mov     r8d, 44535442h
0x14001ae15  mov     ecx, 40h ; '@'
0x14001ae1a  mov     r15d, r9d
0x14001ae1d  lea     rdx, [r14+51h]
0x14001ae21  cmp     rdx, rax
0x14001ae24  cmovb   rdx, rax
0x14001ae28  call    cs:__imp_ExAllocatePool2
0x14001ae2f  nop     dword ptr [rax+rax+00h]
0x14001ae34  mov     rsi, [rsp+98h+arg_40]
0x14001ae3c  mov     rbx, rax
0x14001ae3f  mov     rbp, [rsp+98h+arg_38]
0x14001ae47  test    rax, rax
0x14001ae4a  jz      loc_14001AF0C
0x14001ae50  mov     rcx, [rsp+98h+arg_20]
0x14001ae58  lea     rdx, SdppServiceAttributeSearchCompletionRoutine
0x14001ae5f  mov     [rax], rdi
0x14001ae62  xor     r8d, r8d
0x14001ae65  mov     [rax+8], r13
0x14001ae69  mov     [rax+10h], r14d
0x14001ae6d  mov     [rax+20h], r15d
0x14001ae71  movups  xmm0, xmmword ptr [rcx]
0x14001ae74  movzx   ecx, [rsp+98h+arg_28]
0x14001ae7c  mov     [rax+34h], cx
0x14001ae80  movdqu  xmmword ptr [rax+24h], xmm0
0x14001ae85  movzx   eax, [rsp+98h+arg_30]
0x14001ae8d  mov     [rsp+98h+var_50], rbx
0x14001ae92  mov     [rsp+98h+var_58], rdx
0x14001ae97  mov     rdx, r13
0x14001ae9a  mov     [rbx+38h], rbp
0x14001ae9e  mov     [rbx+40h], rsi
0x14001aea2  mov     [rbx+36h], ax
0x14001aea6  mov     [rbx+144h], cx
0x14001aead  lea     rcx, [rbx+48h]
0x14001aeb1  mov     [rbx+18h], r12
0x14001aeb5  mov     word ptr [rbx+64h], 430h
0x14001aebb  movdqu  xmmword ptr [rbx+54h], xmm0
0x14001aec0  mov     [rbx+146h], ax
0x14001aec7  lea     eax, [r14+9]
0x14001aecb  mov     [rsp+98h+var_60], eax
0x14001aecf  mov     [rsp+98h+var_68], 100h
0x14001aed7  mov     [rsp+98h+var_70], rcx
0x14001aedc  mov     [rcx], r12
0x14001aedf  mov     rcx, rdi
0x14001aee2  mov     [rbx+50h], r15d
0x14001aee6  mov     [rsp+98h+var_78], 410210h
0x14001aeee  call    IrpBuildIoctlEx
0x14001aef3  test    rax, rax
0x14001aef6  jz      short loc_14001AF0C
0x14001aef8  mov     rdx, rax; Irp
0x14001aefb  mov     rcx, rdi; DeviceObject
0x14001aefe  call    cs:__imp_IofCallDriver
0x14001af05  nop     dword ptr [rax+rax+00h]
0x14001af0a  jmp     short loc_14001AF36
0x14001af0c  mov     r9d, 0C000009Ah
0x14001af12  xor     r8d, r8d
0x14001af15  xor     edx, edx
0x14001af17  mov     rcx, rsi
0x14001af1a  mov     rax, rbp
0x14001af1d  call    _guard_dispatch_icall
0x14001af22  test    rbx, rbx
0x14001af25  jz      short loc_14001AF36
0x14001af27  mov     rcx, rbx; P
0x14001af2a  call    cs:__imp_ExFreePool
0x14001af31  nop     dword ptr [rax+rax+00h]
0x14001af36  mov     eax, 103h
0x14001af3b  add     rsp, 58h
0x14001af3f  pop     r15
0x14001af41  pop     r14
0x14001af43  pop     r13
0x14001af45  pop     r12
0x14001af47  pop     rdi
0x14001af48  pop     rsi
0x14001af49  pop     rbp
0x14001af4a  pop     rbx
0x14001af4b  retn
```
