# ndisMUnloadEx(_DRIVER_OBJECT *)

- ea: `0x140076870`
- end: `0x1400769c0`
- name: `?ndisMUnloadEx@@YAXPEAU_DRIVER_OBJECT@@@Z`
- size: `336`
- prototype: `void __fastcall(struct _DRIVER_OBJECT *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x1400110b0`
- `0x14001fa30`
- `0x140076870`
- `0x140144238`
- `0x14015d480`

## import_xrefs

- `ntoskrnl!IoGetDriverObjectExtension` at `0x1400768cc`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x1400768e3`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x1400768cc`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x1400768e3`
- `ntoskrnl!KeClearEvent` at `0x14007695a`
- `ntoskrnl!KeClearEvent` at `0x14007697b`
- `ntoskrnl!KeClearEvent` at `0x14007695a`
- `ntoskrnl!KeClearEvent` at `0x14007697b`

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
0x140076870  mov     [rsp+arg_10], rbx
0x140076875  push    rbp
0x140076876  push    rsi
0x140076877  push    r15
0x140076879  sub     rsp, 40h
0x14007687d  mov     [rsp+58h+arg_8], r14
0x140076882  mov     rsi, rcx
0x140076885  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14007688c  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140076893  lea     r15, WPP_b0ad62796b5830cbf8ad07ce2f1bab24_Traceguids
0x14007689a  jz      short loc_1400768C4
0x14007689c  mov     qword ptr [rsp+58h+var_30], rcx; char
0x1400768a1  mov     r9d, 6Dh ; 'm'; int
0x1400768a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400768ae  mov     r8d, 1; int
0x1400768b4  mov     dl, 4; int
0x1400768b6  mov     [rsp+58h+var_38], r15; struct _GUID *
0x1400768bb  mov     rcx, [rcx+40h]; int
0x1400768bf  call    WPP_RECORDER_SF_q
0x1400768c4  mov     edx, 4E4D4944h; ClientIdentificationAddress
0x1400768c9  mov     rcx, rsi; DriverObject
0x1400768cc  call    cs:__imp_IoGetDriverObjectExtension
0x1400768d3  nop     dword ptr [rax+rax+00h]
0x1400768d8  mov     edx, 4E494944h; ClientIdentificationAddress
0x1400768dd  mov     rcx, rsi; DriverObject
0x1400768e0  mov     rbp, rax
0x1400768e3  call    cs:__imp_IoGetDriverObjectExtension
0x1400768ea  nop     dword ptr [rax+rax+00h]
0x1400768ef  mov     rbx, rax
0x1400768f2  test    rbp, rbp
0x1400768f5  jnz     short loc_14007692D
0x1400768f7  test    rbx, rbx
0x1400768fa  jnz     short loc_14007693A
0x1400768fc  mov     [rsp+58h+arg_0], rdi
0x140076901  test    rbp, rbp
0x140076904  jnz     short loc_140076947
0x140076906  test    rbx, rbx
0x140076909  jnz     short loc_140076968
0x14007690b  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x140076912  mov     r14, [rsp+58h+arg_8]
0x140076917  mov     rdi, [rsp+58h+arg_0]
0x14007691c  jnz     short loc_140076989
0x14007691e  mov     rbx, [rsp+58h+arg_10]
0x140076923  add     rsp, 40h
0x140076927  pop     r15
0x140076929  pop     rsi
0x14007692a  pop     rbp
0x14007692b  retn
0x14007692d  mov     rdx, rsi; struct _DRIVER_OBJECT *
0x140076930  mov     rcx, rbp; struct _NDIS_M_DRIVER_BLOCK *
0x140076933  call    ?ndisMInvokeDriverUnload@@YAXPEAU_NDIS_M_DRIVER_BLOCK@@PEAU_DRIVER_OBJECT@@@Z; ndisMInvokeDriverUnload(_NDIS_M_DRIVER_BLOCK *,_DRIVER_OBJECT *)
0x140076938  jmp     short loc_1400768F7
0x14007693a  mov     rdx, rsi; struct _DRIVER_OBJECT *
0x14007693d  mov     rcx, rbx; struct _NDIS_M_DRIVER_BLOCK *
0x140076940  call    ?ndisMInvokeDriverUnload@@YAXPEAU_NDIS_M_DRIVER_BLOCK@@PEAU_DRIVER_OBJECT@@@Z; ndisMInvokeDriverUnload(_NDIS_M_DRIVER_BLOCK *,_DRIVER_OBJECT *)
0x140076945  jmp     short loc_1400768FC
0x140076947  lea     rcx, [rbp+170h]; void *
0x14007694e  call    ?ndisWaitForKernelObject@@YAXPEAX@Z; ndisWaitForKernelObject(void *)
0x140076953  lea     rcx, [rbp+170h]; Event
0x14007695a  call    cs:__imp_KeClearEvent
0x140076961  nop     dword ptr [rax+rax+00h]
0x140076966  jmp     short loc_140076906
0x140076968  lea     rcx, [rbx+170h]; void *
0x14007696f  call    ?ndisWaitForKernelObject@@YAXPEAX@Z; ndisWaitForKernelObject(void *)
0x140076974  lea     rcx, [rbx+170h]; Event
0x14007697b  call    cs:__imp_KeClearEvent
0x140076982  nop     dword ptr [rax+rax+00h]
0x140076987  jmp     short loc_14007690B
0x140076989  mov     rcx, cs:WPP_GLOBAL_Control
0x140076990  mov     r9d, 6Eh ; 'n'; int
0x140076996  mov     qword ptr [rsp+58h+var_20], rbx; char
0x14007699b  mov     r8d, 1; int
0x1400769a1  mov     qword ptr [rsp+58h+var_28], rbp; char
0x1400769a6  mov     dl, 4; int
0x1400769a8  mov     qword ptr [rsp+58h+var_30], rsi; char
0x1400769ad  mov     rcx, [rcx+40h]; int
0x1400769b1  mov     [rsp+58h+var_38], r15; struct _GUID *
0x1400769b6  call    WPP_RECORDER_SF_qqq
0x1400769bb  jmp     loc_14007691E
```
