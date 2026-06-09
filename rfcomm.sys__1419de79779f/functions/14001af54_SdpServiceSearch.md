# SdpServiceSearch

- ea: `0x14001af54`
- end: `0x14001b108`
- name: `SdpServiceSearch`
- size: `436`
- prototype: `__int64 __usercall@<rax>(PDEVICE_OBJECT DeviceObject@<rcx>, int, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14001b7a0`

## callees

- `0x140003bf4`
- `0x14001a3a8`
- `0x14001af54`
- `0x14001b420`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x14001b0af`
- `ntoskrnl!IofCallDriver` at `0x14001b0af`
- `ntoskrnl!ExAllocatePool2` at `0x14001afce`
- `ntoskrnl!ExAllocatePool2` at `0x14001afce`
- `ntoskrnl!ExFreePool` at `0x14001b09b`
- `ntoskrnl!ExFreePool` at `0x14001b09b`

## pseudocode

```c
__int64 __fastcall SdpServiceSearch(
        PDEVICE_OBJECT DeviceObject,
        struct _DEVICE_OBJECT *a2,
        __int64 a3,
        _OWORD *a4,
        unsigned int a5,
        __int64 a6,
        int a7,
        __int64 a8)
{
  unsigned __int64 v12; // rdx
  char *Pool2; // rax
  __int64 v14; // r9
  void *v15; // rbx
  int v16; // edx
  IRP *v17; // rax

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      3,
      66,
      (__int64)&WPP_3313475e708830025d331cff5c1f0c33_Traceguids);
  v12 = 4LL * a5 + 32;
  if ( v12 < 0x118 )
    v12 = 280;
  Pool2 = (char *)ExAllocatePool2(64, v12, 1146311746);
  v15 = Pool2;
  if ( Pool2 )
  {
    *((_QWORD *)Pool2 + 2) = a8;
    *(_QWORD *)Pool2 = a6;
    *((_DWORD *)Pool2 + 2) = a5;
    *((_QWORD *)Pool2 + 3) = SdppIdToPortAttribute;
    *((_QWORD *)Pool2 + 4) = a3;
    *((_WORD *)Pool2 + 28) = 1072;
    *(_OWORD *)(Pool2 + 40) = *a4;
    v17 = IrpBuildIoctlEx(
            (__int64)DeviceObject,
            a2,
            0,
            v14,
            0x410208u,
            (_IRP *)(Pool2 + 32),
            0xF8u,
            4 * a5,
            (IO_COMPLETION_ROUTINE *)SdppServiceSearchCompletionRoutine,
            Pool2);
    if ( v17 )
    {
      IofCallDriver(DeviceObject, v17);
    }
    else
    {
      SdppIdToPortAttribute(a8);
      ExFreePool(v15);
    }
  }
  else
  {
    SdppIdToPortAttribute(a8);
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v16,
      3,
      67,
      (__int64)&WPP_3313475e708830025d331cff5c1f0c33_Traceguids);
  return 259;
}

```

## disassembly

```asm
0x14001af54  push    rbx
0x14001af56  push    rbp
0x14001af57  push    rsi
0x14001af58  push    rdi
0x14001af59  push    r12
0x14001af5b  push    r13
0x14001af5d  push    r14
0x14001af5f  push    r15
0x14001af61  sub     rsp, 58h
0x14001af65  mov     r15, r9
0x14001af68  mov     r12, r8
0x14001af6b  mov     r13, rdx
0x14001af6e  mov     rdi, rcx
0x14001af71  lea     rax, WPP_RECORDER_INITIALIZED
0x14001af78  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001af7f  lea     rsi, WPP_3313475e708830025d331cff5c1f0c33_Traceguids
0x14001af86  jz      short loc_14001AFA7
0x14001af88  mov     rcx, cs:WPP_GLOBAL_Control
0x14001af8f  mov     r9d, 42h ; 'B'
0x14001af95  mov     [rsp+98h+var_78], rsi
0x14001af9a  mov     rcx, [rcx+40h]
0x14001af9e  lea     r8d, [r9-3Fh]
0x14001afa2  call    WPP_RECORDER_SF_
0x14001afa7  mov     r14d, [rsp+98h+arg_20]
0x14001afaf  mov     eax, 118h
0x14001afb4  mov     ecx, 40h ; '@'
0x14001afb9  mov     r8d, 44535442h
0x14001afbf  lea     rdx, ds:20h[r14*4]
0x14001afc7  cmp     rdx, rax
0x14001afca  cmovb   rdx, rax
0x14001afce  call    cs:__imp_ExAllocatePool2
0x14001afd5  nop     dword ptr [rax+rax+00h]
0x14001afda  mov     rbx, rax
0x14001afdd  test    rax, rax
0x14001afe0  jnz     short loc_14001B004
0x14001afe2  mov     r8, [rsp+98h+arg_28]
0x14001afea  mov     r9d, 0C000009Ah
0x14001aff0  mov     rcx, [rsp+98h+arg_38]; __int64
0x14001aff8  xor     edx, edx
0x14001affa  call    SdppIdToPortAttribute
0x14001afff  jmp     loc_14001B0C2
0x14001b004  mov     rsi, [rsp+98h+arg_38]
0x14001b00c  lea     rdx, [rbx+20h]
0x14001b010  mov     rbp, [rsp+98h+arg_28]
0x14001b018  lea     rcx, SdppServiceSearchCompletionRoutine
0x14001b01f  mov     [rax+10h], rsi
0x14001b023  xor     r8d, r8d
0x14001b026  mov     [rax], rbp
0x14001b029  mov     [rax+8], r14d
0x14001b02d  lea     rax, SdppIdToPortAttribute
0x14001b034  mov     [rsp+98h+var_50], rbx
0x14001b039  mov     [rsp+98h+var_58], rcx
0x14001b03e  mov     rcx, rdi
0x14001b041  mov     [rbx+18h], rax
0x14001b045  lea     eax, ds:0[r14*4]
0x14001b04d  mov     [rdx], r12
0x14001b050  mov     [rsp+98h+var_60], eax
0x14001b054  mov     word ptr [rbx+38h], 430h
0x14001b05a  movups  xmm0, xmmword ptr [r15]
0x14001b05e  mov     [rsp+98h+var_68], 0F8h
0x14001b066  mov     [rsp+98h+var_70], rdx
0x14001b06b  mov     rdx, r13
0x14001b06e  movdqu  xmmword ptr [rbx+28h], xmm0
0x14001b073  mov     dword ptr [rsp+98h+var_78], 410208h
0x14001b07b  call    IrpBuildIoctlEx
0x14001b080  test    rax, rax
0x14001b083  jnz     short loc_14001B0A9
0x14001b085  mov     r9d, 0C000009Ah
0x14001b08b  mov     r8, rbp
0x14001b08e  xor     edx, edx
0x14001b090  mov     rcx, rsi; __int64
0x14001b093  call    SdppIdToPortAttribute
0x14001b098  mov     rcx, rbx; P
0x14001b09b  call    cs:__imp_ExFreePool
0x14001b0a2  nop     dword ptr [rax+rax+00h]
0x14001b0a7  jmp     short loc_14001B0BB
0x14001b0a9  mov     rdx, rax; Irp
0x14001b0ac  mov     rcx, rdi; DeviceObject
0x14001b0af  call    cs:__imp_IofCallDriver
0x14001b0b6  nop     dword ptr [rax+rax+00h]
0x14001b0bb  lea     rsi, WPP_3313475e708830025d331cff5c1f0c33_Traceguids
0x14001b0c2  lea     rax, WPP_RECORDER_INITIALIZED
0x14001b0c9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001b0d0  jz      short loc_14001B0F1
0x14001b0d2  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b0d9  mov     r9d, 43h ; 'C'
0x14001b0df  mov     [rsp+98h+var_78], rsi
0x14001b0e4  mov     rcx, [rcx+40h]
0x14001b0e8  lea     r8d, [r9-40h]
0x14001b0ec  call    WPP_RECORDER_SF_
0x14001b0f1  mov     eax, 103h
0x14001b0f6  add     rsp, 58h
0x14001b0fa  pop     r15
0x14001b0fc  pop     r14
0x14001b0fe  pop     r13
0x14001b100  pop     r12
0x14001b102  pop     rdi
0x14001b103  pop     rsi
0x14001b104  pop     rbp
0x14001b105  pop     rbx
0x14001b106  retn
```
