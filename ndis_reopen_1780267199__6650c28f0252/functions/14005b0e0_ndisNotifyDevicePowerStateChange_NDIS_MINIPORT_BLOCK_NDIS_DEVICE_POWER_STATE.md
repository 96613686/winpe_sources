# ndisNotifyDevicePowerStateChange(_NDIS_MINIPORT_BLOCK *,_NDIS_DEVICE_POWER_STATE)

- ea: `0x14005b0e0`
- end: `0x14005b312`
- name: `?ndisNotifyDevicePowerStateChange@@YAXPEAU_NDIS_MINIPORT_BLOCK@@W4_NDIS_DEVICE_POWER_STATE@@@Z`
- size: `562`
- prototype: `void __fastcall(struct _NDIS_MINIPORT_BLOCK *, enum _NDIS_DEVICE_POWER_STATE)`
- caller_count: `4`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x14005ac50`
- `0x1400b2f5c`
- `0x140179ea0`
- `0x140180470`

## callees

- `0x1400114b0`
- `0x14001cf60`
- `0x14005b0e0`
- `0x14005b320`
- `0x140092d80`
- `0x1400eb4c0`

## import_xrefs

- `ntoskrnl!IoWMIWriteEvent` at `0x14005b182`
- `ntoskrnl!IoWMIWriteEvent` at `0x14005b207`
- `ntoskrnl!IoWMIWriteEvent` at `0x14005b182`
- `ntoskrnl!IoWMIWriteEvent` at `0x14005b207`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f1490`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f14d6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f1490`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f14d6`

## pseudocode

```c
void __fastcall ndisNotifyDevicePowerStateChange(struct _NDIS_MINIPORT_BLOCK *a1, int a2)
{
  int v2; // esi
  GUID *v4; // r9
  PVOID v5; // rdi
  NTSTATUS v6; // eax
  int v7; // edx
  int v8; // ecx
  NTSTATUS v9; // ebp
  GUID *v10; // r9
  int v11; // edx
  PVOID v12; // rdi
  unsigned __int16 *v13; // rcx
  NTSTATUS v14; // eax
  int v15; // ecx
  NTSTATUS v16; // ebp
  char v17; // [rsp+30h] [rbp-28h]
  PVOID WnodeEventItem; // [rsp+60h] [rbp+8h] BYREF

  v2 = a2;
  WnodeEventItem = 0;
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v17 = a2;
    LOBYTE(a2) = 4;
    WPP_RECORDER_SF_qL(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      a2,
      14,
      63,
      (struct _GUID *)&WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids,
      (char)a1,
      v17);
  }
  v4 = &GUID_NDIS_NOTIFY_DEVICE_POWER_ON;
  if ( v2 != 1 )
    v4 = &GUID_NDIS_NOTIFY_DEVICE_POWER_OFF;
  ndisSetupWmiNode(
    a1,
    a1->pAdapterInstanceName,
    a1->MiniportName.Length + 2,
    v4,
    (struct tagWNODE_SINGLE_INSTANCE **)&WnodeEventItem);
  v5 = WnodeEventItem;
  if ( WnodeEventItem )
  {
    memmove(
      (char *)WnodeEventItem + *((unsigned int *)WnodeEventItem + 14),
      a1->MiniportName.Buffer,
      a1->MiniportName.Length);
    v6 = IoWMIWriteEvent(v5);
    v9 = v6;
    if ( v6 < 0 )
    {
      if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v7) = 2;
        WPP_RECORDER_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          v7,
          14,
          64,
          (struct _GUID *)&WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids,
          v6);
      }
      if ( (byte_140121001 & 0x10) != 0 )
        McTemplateK0qqq_EtwWriteTransfer(v8, (unsigned int)IoWMIWriteEventFailed, (_DWORD)a1 + 4008, v9, 5, 0);
      ExFreePoolWithTag(v5, 0);
    }
  }
  v10 = &GUID_NDIS_NOTIFY_DEVICE_POWER_ON_EX;
  if ( v2 != 1 )
    v10 = &GUID_NDIS_NOTIFY_DEVICE_POWER_OFF_EX;
  ndisSetupWmiNode(
    a1,
    a1->pAdapterInstanceName,
    a1->MiniportName.Length + 2,
    v10,
    (struct tagWNODE_SINGLE_INSTANCE **)&WnodeEventItem);
  v12 = WnodeEventItem;
  if ( WnodeEventItem )
  {
    v13 = (unsigned __int16 *)((char *)WnodeEventItem + *((unsigned int *)WnodeEventItem + 14));
    *v13 = a1->MiniportName.Length;
    memmove(v13 + 1, a1->MiniportName.Buffer, a1->MiniportName.Length);
    v14 = IoWMIWriteEvent(v12);
    v16 = v14;
    if ( v14 < 0 )
    {
      if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v11) = 2;
        WPP_RECORDER_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          v11,
          14,
          65,
          (struct _GUID *)&WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids,
          v14);
      }
      if ( (byte_140121001 & 0x10) != 0 )
        McTemplateK0qqq_EtwWriteTransfer(v15, (unsigned int)IoWMIWriteEventFailed, (_DWORD)a1 + 4008, v16, 6, 0);
      ExFreePoolWithTag(v12, 0);
    }
  }
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v11) = 4;
    WPP_RECORDER_SF_qL(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v11,
      14,
      66,
      (struct _GUID *)&WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids,
      (char)a1,
      v2);
  }
}

```

## disassembly

```asm
0x14005b0e0  push    rbx
0x14005b0e2  push    rsi
0x14005b0e3  push    r12
0x14005b0e5  sub     rsp, 40h
0x14005b0e9  mov     [rsp+58h+arg_10], rdi
0x14005b0ee  mov     esi, edx
0x14005b0f0  mov     [rsp+58h+arg_18], r14
0x14005b0f5  mov     rbx, rcx
0x14005b0f8  mov     [rsp+58h+WnodeEventItem], 0
0x14005b101  lea     r14, WPP_RECORDER_INITIALIZED
0x14005b108  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14005b10f  lea     r12, WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids
0x14005b116  jnz     loc_14005B26D
0x14005b11c  movzx   r8d, word ptr [rbx+0EE0h]
0x14005b124  lea     rax, GUID_NDIS_NOTIFY_DEVICE_POWER_OFF
0x14005b12b  mov     rdx, [rbx+0F10h]; struct _UNICODE_STRING *
0x14005b132  lea     r9, GUID_NDIS_NOTIFY_DEVICE_POWER_ON
0x14005b139  cmp     esi, 1
0x14005b13c  mov     [rsp+58h+arg_8], rbp
0x14005b141  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14005b144  cmovnz  r9, rax; void *
0x14005b148  lea     rax, [rsp+58h+WnodeEventItem]
0x14005b14d  add     r8d, 2; unsigned int
0x14005b151  mov     [rsp+58h+var_38], rax; struct tagWNODE_SINGLE_INSTANCE **
0x14005b156  call    ?ndisSetupWmiNode@@YAXPEAU_NDIS_MINIPORT_BLOCK@@PEBU_UNICODE_STRING@@KPEAXPEAPEAUtagWNODE_SINGLE_INSTANCE@@@Z; ndisSetupWmiNode(_NDIS_MINIPORT_BLOCK *,_UNICODE_STRING const *,ulong,void *,tagWNODE_SINGLE_INSTANCE * *)
0x14005b15b  mov     rdi, [rsp+58h+WnodeEventItem]
0x14005b160  test    rdi, rdi
0x14005b163  jz      short loc_14005B198
0x14005b165  mov     ecx, [rdi+38h]
0x14005b168  movzx   r8d, word ptr [rbx+0EE0h]; Size
0x14005b170  add     rcx, rdi; void *
0x14005b173  mov     rdx, [rbx+0EE8h]; Src
0x14005b17a  call    memmove
0x14005b17f  mov     rcx, rdi; WnodeEventItem
0x14005b182  call    cs:__imp_IoWMIWriteEvent
0x14005b189  nop     dword ptr [rax+rax+00h]
0x14005b18e  mov     ebp, eax
0x14005b190  test    eax, eax
0x14005b192  js      loc_14005B29E
0x14005b198  movzx   r8d, word ptr [rbx+0EE0h]
0x14005b1a0  lea     rax, GUID_NDIS_NOTIFY_DEVICE_POWER_OFF_EX
0x14005b1a7  mov     rdx, [rbx+0F10h]; struct _UNICODE_STRING *
0x14005b1ae  lea     r9, GUID_NDIS_NOTIFY_DEVICE_POWER_ON_EX
0x14005b1b5  cmp     esi, 1
0x14005b1b8  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14005b1bb  cmovnz  r9, rax; void *
0x14005b1bf  lea     rax, [rsp+58h+WnodeEventItem]
0x14005b1c4  add     r8d, 2; unsigned int
0x14005b1c8  mov     [rsp+58h+var_38], rax; struct tagWNODE_SINGLE_INSTANCE **
0x14005b1cd  call    ?ndisSetupWmiNode@@YAXPEAU_NDIS_MINIPORT_BLOCK@@PEBU_UNICODE_STRING@@KPEAXPEAPEAUtagWNODE_SINGLE_INSTANCE@@@Z; ndisSetupWmiNode(_NDIS_MINIPORT_BLOCK *,_UNICODE_STRING const *,ulong,void *,tagWNODE_SINGLE_INSTANCE * *)
0x14005b1d2  mov     rdi, [rsp+58h+WnodeEventItem]
0x14005b1d7  test    rdi, rdi
0x14005b1da  jz      short loc_14005B21D
0x14005b1dc  mov     ecx, [rdi+38h]
0x14005b1df  movzx   eax, word ptr [rbx+0EE0h]
0x14005b1e6  add     rcx, rdi
0x14005b1e9  mov     [rcx], ax
0x14005b1ec  add     rcx, 2; void *
0x14005b1f0  movzx   r8d, word ptr [rbx+0EE0h]; Size
0x14005b1f8  mov     rdx, [rbx+0EE8h]; Src
0x14005b1ff  call    memmove
0x14005b204  mov     rcx, rdi; WnodeEventItem
0x14005b207  call    cs:__imp_IoWMIWriteEvent
0x14005b20e  nop     dword ptr [rax+rax+00h]
0x14005b213  mov     ebp, eax
0x14005b215  test    eax, eax
0x14005b217  js      loc_14005B2D8
0x14005b21d  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14005b224  mov     r14, [rsp+58h+arg_18]
0x14005b229  mov     rdi, [rsp+58h+arg_10]
0x14005b22e  mov     rbp, [rsp+58h+arg_8]
0x14005b233  jnz     short loc_14005B23F
0x14005b235  add     rsp, 40h
0x14005b239  pop     r12
0x14005b23b  pop     rsi
0x14005b23c  pop     rbx
0x14005b23d  retn
0x14005b23f  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b246  mov     r9d, 42h ; 'B'; int
0x14005b24c  mov     dword ptr [rsp+58h+var_28], esi; char
0x14005b250  mov     r8d, 0Eh; int
0x14005b256  mov     qword ptr [rsp+58h+var_30], rbx; char
0x14005b25b  mov     dl, 4; int
0x14005b25d  mov     [rsp+58h+var_38], r12; struct _GUID *
0x14005b262  mov     rcx, [rcx+40h]; int
0x14005b266  call    WPP_RECORDER_SF_qL
0x14005b26b  jmp     short loc_14005B235
0x14005b26d  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b274  mov     r9d, 3Fh ; '?'; int
0x14005b27a  mov     dword ptr [rsp+58h+var_28], esi; char
0x14005b27e  mov     r8d, 0Eh; int
0x14005b284  mov     qword ptr [rsp+58h+var_30], rbx; char
0x14005b289  mov     dl, 4; int
0x14005b28b  mov     [rsp+58h+var_38], r12; struct _GUID *
0x14005b290  mov     rcx, [rcx+40h]; int
0x14005b294  call    WPP_RECORDER_SF_qL
0x14005b299  jmp     loc_14005B11C
0x14005b29e  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14005b2a5  jz      loc_1400F145C
0x14005b2ab  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b2b2  mov     r9d, 40h ; '@'; int
0x14005b2b8  mov     dword ptr [rsp+58h+var_30], ebp; char
0x14005b2bc  mov     r8d, 0Eh; int
0x14005b2c2  mov     dl, 2; int
0x14005b2c4  mov     [rsp+58h+var_38], r12; struct _GUID *
0x14005b2c9  mov     rcx, [rcx+40h]; int
0x14005b2cd  call    WPP_RECORDER_SF_d
0x14005b2d2  nop
0x14005b2d3  jmp     loc_1400F145C
0x14005b2d8  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14005b2df  jz      loc_1400F14A2
0x14005b2e5  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b2ec  mov     r9d, 41h ; 'A'; int
0x14005b2f2  mov     dword ptr [rsp+58h+var_30], ebp; char
0x14005b2f6  mov     r8d, 0Eh; int
0x14005b2fc  mov     dl, 2; int
0x14005b2fe  mov     [rsp+58h+var_38], r12; struct _GUID *
0x14005b303  mov     rcx, [rcx+40h]; int
0x14005b307  call    WPP_RECORDER_SF_d
0x14005b30c  nop
0x14005b30d  jmp     loc_1400F14A2
0x1400f145c  test    cs:byte_140121001, 10h
0x1400f1463  jz      short loc_1400F148B
0x1400f1465  lea     r8, [rbx+0FA8h]
0x1400f146c  mov     dword ptr [rsp+58h+var_30], 0
0x1400f1474  mov     r9d, ebp
0x1400f1477  mov     dword ptr [rsp+58h+var_38], 10005h
0x1400f147f  lea     rdx, IoWMIWriteEventFailed
0x1400f1486  call    McTemplateK0qqq_EtwWriteTransfer
0x1400f148b  xor     edx, edx; Tag
0x1400f148d  mov     rcx, rdi; P
0x1400f1490  call    cs:__imp_ExFreePoolWithTag
0x1400f1497  nop     dword ptr [rax+rax+00h]
0x1400f149c  nop
0x1400f149d  jmp     loc_14005B198
0x1400f14a2  test    cs:byte_140121001, 10h
0x1400f14a9  jz      short loc_1400F14D1
0x1400f14ab  lea     r8, [rbx+0FA8h]
0x1400f14b2  mov     dword ptr [rsp+58h+var_30], 0
0x1400f14ba  mov     r9d, ebp
0x1400f14bd  mov     dword ptr [rsp+58h+var_38], 10006h
0x1400f14c5  lea     rdx, IoWMIWriteEventFailed
0x1400f14cc  call    McTemplateK0qqq_EtwWriteTransfer
0x1400f14d1  xor     edx, edx; Tag
0x1400f14d3  mov     rcx, rdi; P
0x1400f14d6  call    cs:__imp_ExFreePoolWithTag
0x1400f14dd  nop     dword ptr [rax+rax+00h]
0x1400f14e2  nop
0x1400f14e3  jmp     loc_14005B21D
```
