# ndisNotifyDevicePowerStateChange(_NDIS_MINIPORT_BLOCK *,_NDIS_DEVICE_POWER_STATE)

- ea: `0x1400568a0`
- end: `0x140056ad2`
- name: `?ndisNotifyDevicePowerStateChange@@YAXPEAU_NDIS_MINIPORT_BLOCK@@W4_NDIS_DEVICE_POWER_STATE@@@Z`
- size: `562`
- prototype: `void __fastcall(struct _NDIS_MINIPORT_BLOCK *, enum _NDIS_DEVICE_POWER_STATE)`
- caller_count: `4`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x140056410`
- `0x1400adb1c`
- `0x140173ea0`
- `0x14017a4a0`

## callees

- `0x14001d350`
- `0x140028e00`
- `0x1400568a0`
- `0x140056ae0`
- `0x14008e340`
- `0x1400e62c0`

## import_xrefs

- `ntoskrnl!IoWMIWriteEvent` at `0x140056942`
- `ntoskrnl!IoWMIWriteEvent` at `0x1400569c7`
- `ntoskrnl!IoWMIWriteEvent` at `0x140056942`
- `ntoskrnl!IoWMIWriteEvent` at `0x1400569c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ec4f6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ec53c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ec4f6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ec53c`

## pseudocode

```c
void __fastcall ndisNotifyDevicePowerStateChange(struct _NDIS_MINIPORT_BLOCK *a1, int a2)
{
  int v2; // esi
  __int128 *v4; // r9
  PVOID v5; // rdi
  NTSTATUS v6; // eax
  int v7; // edx
  int v8; // ecx
  NTSTATUS v9; // ebp
  __int128 *v10; // r9
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
  v4 = (__int128 *)&GUID_NDIS_NOTIFY_DEVICE_POWER_ON;
  if ( v2 != 1 )
    v4 = (__int128 *)&GUID_NDIS_NOTIFY_DEVICE_POWER_OFF;
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
      if ( (byte_14011B001 & 0x10) != 0 )
        McTemplateK0qqq_EtwWriteTransfer(v8, (unsigned int)IoWMIWriteEventFailed, (_DWORD)a1 + 4008, v9, 5, 0);
      ExFreePoolWithTag(v5, 0);
    }
  }
  v10 = (__int128 *)&GUID_NDIS_NOTIFY_DEVICE_POWER_ON_EX;
  if ( v2 != 1 )
    v10 = (__int128 *)&GUID_NDIS_NOTIFY_DEVICE_POWER_OFF_EX;
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
      if ( (byte_14011B001 & 0x10) != 0 )
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
0x1400568a0  push    rbx
0x1400568a2  push    rsi
0x1400568a3  push    r12
0x1400568a5  sub     rsp, 40h
0x1400568a9  mov     [rsp+58h+arg_10], rdi
0x1400568ae  mov     esi, edx
0x1400568b0  mov     [rsp+58h+arg_18], r14
0x1400568b5  mov     rbx, rcx
0x1400568b8  mov     [rsp+58h+WnodeEventItem], 0
0x1400568c1  lea     r14, WPP_RECORDER_INITIALIZED
0x1400568c8  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400568cf  lea     r12, WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids
0x1400568d6  jnz     loc_140056A2D
0x1400568dc  movzx   r8d, word ptr [rbx+0EE0h]
0x1400568e4  lea     rax, GUID_NDIS_NOTIFY_DEVICE_POWER_OFF
0x1400568eb  mov     rdx, [rbx+0F10h]; struct _UNICODE_STRING *
0x1400568f2  lea     r9, GUID_NDIS_NOTIFY_DEVICE_POWER_ON
0x1400568f9  cmp     esi, 1
0x1400568fc  mov     [rsp+58h+arg_8], rbp
0x140056901  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x140056904  cmovnz  r9, rax; void *
0x140056908  lea     rax, [rsp+58h+WnodeEventItem]
0x14005690d  add     r8d, 2; unsigned int
0x140056911  mov     [rsp+58h+var_38], rax; struct tagWNODE_SINGLE_INSTANCE **
0x140056916  call    ?ndisSetupWmiNode@@YAXPEAU_NDIS_MINIPORT_BLOCK@@PEBU_UNICODE_STRING@@KPEAXPEAPEAUtagWNODE_SINGLE_INSTANCE@@@Z; ndisSetupWmiNode(_NDIS_MINIPORT_BLOCK *,_UNICODE_STRING const *,ulong,void *,tagWNODE_SINGLE_INSTANCE * *)
0x14005691b  mov     rdi, [rsp+58h+WnodeEventItem]
0x140056920  test    rdi, rdi
0x140056923  jz      short loc_140056958
0x140056925  mov     ecx, [rdi+38h]
0x140056928  movzx   r8d, word ptr [rbx+0EE0h]; Size
0x140056930  add     rcx, rdi; void *
0x140056933  mov     rdx, [rbx+0EE8h]; Src
0x14005693a  call    memmove
0x14005693f  mov     rcx, rdi; WnodeEventItem
0x140056942  call    cs:__imp_IoWMIWriteEvent
0x140056949  nop     dword ptr [rax+rax+00h]
0x14005694e  mov     ebp, eax
0x140056950  test    eax, eax
0x140056952  js      loc_140056A5E
0x140056958  movzx   r8d, word ptr [rbx+0EE0h]
0x140056960  lea     rax, GUID_NDIS_NOTIFY_DEVICE_POWER_OFF_EX
0x140056967  mov     rdx, [rbx+0F10h]; struct _UNICODE_STRING *
0x14005696e  lea     r9, GUID_NDIS_NOTIFY_DEVICE_POWER_ON_EX
0x140056975  cmp     esi, 1
0x140056978  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14005697b  cmovnz  r9, rax; void *
0x14005697f  lea     rax, [rsp+58h+WnodeEventItem]
0x140056984  add     r8d, 2; unsigned int
0x140056988  mov     [rsp+58h+var_38], rax; struct tagWNODE_SINGLE_INSTANCE **
0x14005698d  call    ?ndisSetupWmiNode@@YAXPEAU_NDIS_MINIPORT_BLOCK@@PEBU_UNICODE_STRING@@KPEAXPEAPEAUtagWNODE_SINGLE_INSTANCE@@@Z; ndisSetupWmiNode(_NDIS_MINIPORT_BLOCK *,_UNICODE_STRING const *,ulong,void *,tagWNODE_SINGLE_INSTANCE * *)
0x140056992  mov     rdi, [rsp+58h+WnodeEventItem]
0x140056997  test    rdi, rdi
0x14005699a  jz      short loc_1400569DD
0x14005699c  mov     ecx, [rdi+38h]
0x14005699f  movzx   eax, word ptr [rbx+0EE0h]
0x1400569a6  add     rcx, rdi
0x1400569a9  mov     [rcx], ax
0x1400569ac  add     rcx, 2; void *
0x1400569b0  movzx   r8d, word ptr [rbx+0EE0h]; Size
0x1400569b8  mov     rdx, [rbx+0EE8h]; Src
0x1400569bf  call    memmove
0x1400569c4  mov     rcx, rdi; WnodeEventItem
0x1400569c7  call    cs:__imp_IoWMIWriteEvent
0x1400569ce  nop     dword ptr [rax+rax+00h]
0x1400569d3  mov     ebp, eax
0x1400569d5  test    eax, eax
0x1400569d7  js      loc_140056A98
0x1400569dd  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400569e4  mov     r14, [rsp+58h+arg_18]
0x1400569e9  mov     rdi, [rsp+58h+arg_10]
0x1400569ee  mov     rbp, [rsp+58h+arg_8]
0x1400569f3  jnz     short loc_1400569FF
0x1400569f5  add     rsp, 40h
0x1400569f9  pop     r12
0x1400569fb  pop     rsi
0x1400569fc  pop     rbx
0x1400569fd  retn
0x1400569ff  mov     rcx, cs:WPP_GLOBAL_Control
0x140056a06  mov     r9d, 42h ; 'B'; int
0x140056a0c  mov     dword ptr [rsp+58h+var_28], esi; char
0x140056a10  mov     r8d, 0Eh; int
0x140056a16  mov     qword ptr [rsp+58h+var_30], rbx; char
0x140056a1b  mov     dl, 4; int
0x140056a1d  mov     [rsp+58h+var_38], r12; struct _GUID *
0x140056a22  mov     rcx, [rcx+40h]; int
0x140056a26  call    WPP_RECORDER_SF_qL
0x140056a2b  jmp     short loc_1400569F5
0x140056a2d  mov     rcx, cs:WPP_GLOBAL_Control
0x140056a34  mov     r9d, 3Fh ; '?'; int
0x140056a3a  mov     dword ptr [rsp+58h+var_28], esi; char
0x140056a3e  mov     r8d, 0Eh; int
0x140056a44  mov     qword ptr [rsp+58h+var_30], rbx; char
0x140056a49  mov     dl, 4; int
0x140056a4b  mov     [rsp+58h+var_38], r12; struct _GUID *
0x140056a50  mov     rcx, [rcx+40h]; int
0x140056a54  call    WPP_RECORDER_SF_qL
0x140056a59  jmp     loc_1400568DC
0x140056a5e  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140056a65  jz      loc_1400EC4C2
0x140056a6b  mov     rcx, cs:WPP_GLOBAL_Control
0x140056a72  mov     r9d, 40h ; '@'; int
0x140056a78  mov     dword ptr [rsp+58h+var_30], ebp; char
0x140056a7c  mov     r8d, 0Eh; int
0x140056a82  mov     dl, 2; int
0x140056a84  mov     [rsp+58h+var_38], r12; struct _GUID *
0x140056a89  mov     rcx, [rcx+40h]; int
0x140056a8d  call    WPP_RECORDER_SF_d
0x140056a92  nop
0x140056a93  jmp     loc_1400EC4C2
0x140056a98  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140056a9f  jz      loc_1400EC508
0x140056aa5  mov     rcx, cs:WPP_GLOBAL_Control
0x140056aac  mov     r9d, 41h ; 'A'; int
0x140056ab2  mov     dword ptr [rsp+58h+var_30], ebp; char
0x140056ab6  mov     r8d, 0Eh; int
0x140056abc  mov     dl, 2; int
0x140056abe  mov     [rsp+58h+var_38], r12; struct _GUID *
0x140056ac3  mov     rcx, [rcx+40h]; int
0x140056ac7  call    WPP_RECORDER_SF_d
0x140056acc  nop
0x140056acd  jmp     loc_1400EC508
0x1400ec4c2  test    cs:byte_14011B001, 10h
0x1400ec4c9  jz      short loc_1400EC4F1
0x1400ec4cb  lea     r8, [rbx+0FA8h]
0x1400ec4d2  mov     dword ptr [rsp+58h+var_30], 0
0x1400ec4da  mov     r9d, ebp
0x1400ec4dd  mov     dword ptr [rsp+58h+var_38], 10005h
0x1400ec4e5  lea     rdx, IoWMIWriteEventFailed
0x1400ec4ec  call    McTemplateK0qqq_EtwWriteTransfer
0x1400ec4f1  xor     edx, edx; Tag
0x1400ec4f3  mov     rcx, rdi; P
0x1400ec4f6  call    cs:__imp_ExFreePoolWithTag
0x1400ec4fd  nop     dword ptr [rax+rax+00h]
0x1400ec502  nop
0x1400ec503  jmp     loc_140056958
0x1400ec508  test    cs:byte_14011B001, 10h
0x1400ec50f  jz      short loc_1400EC537
0x1400ec511  lea     r8, [rbx+0FA8h]
0x1400ec518  mov     dword ptr [rsp+58h+var_30], 0
0x1400ec520  mov     r9d, ebp
0x1400ec523  mov     dword ptr [rsp+58h+var_38], 10006h
0x1400ec52b  lea     rdx, IoWMIWriteEventFailed
0x1400ec532  call    McTemplateK0qqq_EtwWriteTransfer
0x1400ec537  xor     edx, edx; Tag
0x1400ec539  mov     rcx, rdi; P
0x1400ec53c  call    cs:__imp_ExFreePoolWithTag
0x1400ec543  nop     dword ptr [rax+rax+00h]
0x1400ec548  nop
0x1400ec549  jmp     loc_1400569DD
```
