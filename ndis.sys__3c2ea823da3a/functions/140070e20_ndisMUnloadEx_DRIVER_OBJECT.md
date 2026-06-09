# ndisMUnloadEx(_DRIVER_OBJECT *)

- ea: `0x140070e20`
- end: `0x140070f70`
- name: `?ndisMUnloadEx@@YAXPEAU_DRIVER_OBJECT@@@Z`
- size: `336`
- prototype: `void __fastcall(struct _DRIVER_OBJECT *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x14001cf50`
- `0x14002b980`
- `0x140070e20`
- `0x14013d298`
- `0x1401564e0`

## import_xrefs

- `ntoskrnl!IoGetDriverObjectExtension` at `0x140070e7c`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x140070e93`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x140070e7c`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x140070e93`
- `ntoskrnl!KeClearEvent` at `0x140070f0a`
- `ntoskrnl!KeClearEvent` at `0x140070f2b`
- `ntoskrnl!KeClearEvent` at `0x140070f0a`
- `ntoskrnl!KeClearEvent` at `0x140070f2b`

## pseudocode

```c
void __fastcall ndisMUnloadEx(struct _DRIVER_OBJECT *a1)
{
  struct _NDIS_M_DRIVER_BLOCK *DriverObjectExtension; // rbp
  int v3; // edx
  struct _NDIS_M_DRIVER_BLOCK *v4; // rbx

  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      4,
      1,
      109,
      (struct _GUID *)&WPP_b0ad62796b5830cbf8ad07ce2f1bab24_Traceguids,
      (char)a1);
  DriverObjectExtension = (struct _NDIS_M_DRIVER_BLOCK *)IoGetDriverObjectExtension(a1, (PVOID)0x4E4D4944);
  v4 = (struct _NDIS_M_DRIVER_BLOCK *)IoGetDriverObjectExtension(a1, (PVOID)0x4E494944);
  if ( DriverObjectExtension )
    ndisMInvokeDriverUnload(DriverObjectExtension, a1);
  if ( v4 )
    ndisMInvokeDriverUnload(v4, a1);
  if ( DriverObjectExtension )
  {
    ndisWaitForKernelObject(&DriverObjectExtension->MiniportsRemovedEvent);
    KeClearEvent(&DriverObjectExtension->MiniportsRemovedEvent);
  }
  if ( v4 )
  {
    ndisWaitForKernelObject(&v4->MiniportsRemovedEvent);
    KeClearEvent(&v4->MiniportsRemovedEvent);
  }
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v3) = 4;
    WPP_RECORDER_SF_qqq(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v3,
      1,
      110,
      (struct _GUID *)&WPP_b0ad62796b5830cbf8ad07ce2f1bab24_Traceguids,
      (char)a1,
      (char)DriverObjectExtension,
      (char)v4);
  }
}

```

## disassembly

```asm
0x140070e20  mov     [rsp+arg_10], rbx
0x140070e25  push    rbp
0x140070e26  push    rsi
0x140070e27  push    r15
0x140070e29  sub     rsp, 40h
0x140070e2d  mov     [rsp+58h+arg_8], r14
0x140070e32  mov     rsi, rcx
0x140070e35  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140070e3c  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140070e43  lea     r15, WPP_b0ad62796b5830cbf8ad07ce2f1bab24_Traceguids
0x140070e4a  jz      short loc_140070E74
0x140070e4c  mov     qword ptr [rsp+58h+var_30], rcx; char
0x140070e51  mov     r9d, 6Dh ; 'm'; int
0x140070e57  mov     rcx, cs:WPP_GLOBAL_Control
0x140070e5e  mov     r8d, 1; int
0x140070e64  mov     dl, 4; int
0x140070e66  mov     [rsp+58h+var_38], r15; struct _GUID *
0x140070e6b  mov     rcx, [rcx+40h]; int
0x140070e6f  call    WPP_RECORDER_SF_q
0x140070e74  mov     edx, 4E4D4944h; ClientIdentificationAddress
0x140070e79  mov     rcx, rsi; DriverObject
0x140070e7c  call    cs:__imp_IoGetDriverObjectExtension
0x140070e83  nop     dword ptr [rax+rax+00h]
0x140070e88  mov     edx, 4E494944h; ClientIdentificationAddress
0x140070e8d  mov     rcx, rsi; DriverObject
0x140070e90  mov     rbp, rax
0x140070e93  call    cs:__imp_IoGetDriverObjectExtension
0x140070e9a  nop     dword ptr [rax+rax+00h]
0x140070e9f  mov     rbx, rax
0x140070ea2  test    rbp, rbp
0x140070ea5  jnz     short loc_140070EDD
0x140070ea7  test    rbx, rbx
0x140070eaa  jnz     short loc_140070EEA
0x140070eac  mov     [rsp+58h+arg_0], rdi
0x140070eb1  test    rbp, rbp
0x140070eb4  jnz     short loc_140070EF7
0x140070eb6  test    rbx, rbx
0x140070eb9  jnz     short loc_140070F18
0x140070ebb  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x140070ec2  mov     r14, [rsp+58h+arg_8]
0x140070ec7  mov     rdi, [rsp+58h+arg_0]
0x140070ecc  jnz     short loc_140070F39
0x140070ece  mov     rbx, [rsp+58h+arg_10]
0x140070ed3  add     rsp, 40h
0x140070ed7  pop     r15
0x140070ed9  pop     rsi
0x140070eda  pop     rbp
0x140070edb  retn
0x140070edd  mov     rdx, rsi; struct _DRIVER_OBJECT *
0x140070ee0  mov     rcx, rbp; struct _NDIS_M_DRIVER_BLOCK *
0x140070ee3  call    ?ndisMInvokeDriverUnload@@YAXPEAU_NDIS_M_DRIVER_BLOCK@@PEAU_DRIVER_OBJECT@@@Z; ndisMInvokeDriverUnload(_NDIS_M_DRIVER_BLOCK *,_DRIVER_OBJECT *)
0x140070ee8  jmp     short loc_140070EA7
0x140070eea  mov     rdx, rsi; struct _DRIVER_OBJECT *
0x140070eed  mov     rcx, rbx; struct _NDIS_M_DRIVER_BLOCK *
0x140070ef0  call    ?ndisMInvokeDriverUnload@@YAXPEAU_NDIS_M_DRIVER_BLOCK@@PEAU_DRIVER_OBJECT@@@Z; ndisMInvokeDriverUnload(_NDIS_M_DRIVER_BLOCK *,_DRIVER_OBJECT *)
0x140070ef5  jmp     short loc_140070EAC
0x140070ef7  lea     rcx, [rbp+170h]; void *
0x140070efe  call    ?ndisWaitForKernelObject@@YAXPEAX@Z; ndisWaitForKernelObject(void *)
0x140070f03  lea     rcx, [rbp+170h]; Event
0x140070f0a  call    cs:__imp_KeClearEvent
0x140070f11  nop     dword ptr [rax+rax+00h]
0x140070f16  jmp     short loc_140070EB6
0x140070f18  lea     rcx, [rbx+170h]; void *
0x140070f1f  call    ?ndisWaitForKernelObject@@YAXPEAX@Z; ndisWaitForKernelObject(void *)
0x140070f24  lea     rcx, [rbx+170h]; Event
0x140070f2b  call    cs:__imp_KeClearEvent
0x140070f32  nop     dword ptr [rax+rax+00h]
0x140070f37  jmp     short loc_140070EBB
0x140070f39  mov     rcx, cs:WPP_GLOBAL_Control
0x140070f40  mov     r9d, 6Eh ; 'n'; int
0x140070f46  mov     qword ptr [rsp+58h+var_20], rbx; char
0x140070f4b  mov     r8d, 1; int
0x140070f51  mov     qword ptr [rsp+58h+var_28], rbp; char
0x140070f56  mov     dl, 4; int
0x140070f58  mov     qword ptr [rsp+58h+var_30], rsi; char
0x140070f5d  mov     rcx, [rcx+40h]; int
0x140070f61  mov     [rsp+58h+var_38], r15; struct _GUID *
0x140070f66  call    WPP_RECORDER_SF_qqq
0x140070f6b  jmp     loc_140070ECE
```
