# NdisCoDeleteVc

- ea: `0x140088ab0`
- end: `0x140088e19`
- name: `NdisCoDeleteVc`
- size: `873`
- prototype: `NDIS_STATUS __stdcall(NDIS_HANDLE NdisVcHandle)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x1400d26e0`

## callees

- `0x140028e00`
- `0x140056ae0`
- `0x140088ab0`
- `0x14008e340`
- `0x1400d10c0`
- `0x1400d2a24`
- `0x1400e6240`

## import_xrefs

- `ntoskrnl!IoWMIWriteEvent` at `0x140088bb6`
- `ntoskrnl!IoWMIWriteEvent` at `0x140088bb6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088c4e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088cc4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088c4e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088cc4`
- `ntoskrnl!KeReleaseSpinLock` at `0x140088dbc`
- `ntoskrnl!KeReleaseSpinLock` at `0x140088dbc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140088b09`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140088b09`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140088ce9`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140088d52`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140088da7`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140088ce9`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140088d52`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140088da7`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140088c78`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140088d1a`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140088d6d`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140088c78`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140088d1a`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140088d6d`

## pseudocode

```c
NDIS_STATUS __stdcall NdisCoDeleteVc(NDIS_HANDLE NdisVcHandle)
{
  KIRQL v2; // al
  _DWORD *v3; // rcx
  KIRQL v4; // r12
  NDIS_STATUS v5; // edi
  int v6; // edx
  int v7; // ecx
  NTSTATUS v8; // ebp
  char *v9; // rsi
  NDIS_HANDLE *v10; // rdx
  NDIS_HANDLE *v11; // rcx
  KSPIN_LOCK *v12; // rcx
  void (__fastcall *v13)(_QWORD); // rax
  NDIS_HANDLE *v14; // rdx
  NDIS_HANDLE *v15; // rcx
  __int64 v16; // rcx
  _QWORD *v17; // r8
  NDIS_HANDLE *v18; // rdx
  int v19; // edx
  PVOID WnodeEventItem; // [rsp+90h] [rbp+8h] BYREF

  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qLLqL(*((_QWORD *)WPP_GLOBAL_Control + 8), **((_DWORD **)NdisVcHandle + 1));
  v2 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)NdisVcHandle + 2);
  v3 = (_DWORD *)*((_QWORD *)NdisVcHandle + 1);
  v4 = v2;
  if ( (*v3 & 3) != 0 )
  {
    v5 = 65539;
    goto LABEL_32;
  }
  if ( (*v3 & 4) != 0 )
  {
    v5 = -1073676286;
    goto LABEL_32;
  }
  *((_DWORD *)NdisVcHandle + 1) |= 0x80000000;
  if ( *((_DWORD *)NdisVcHandle + 22) && *((_QWORD *)NdisVcHandle + 27) )
    *v3 |= 8u;
  if ( *((_QWORD *)NdisVcHandle + 38) )
  {
    WnodeEventItem = 0;
    ndisSetupWmiNode(
      *((struct _NDIS_MINIPORT_BLOCK **)NdisVcHandle + 24),
      (const struct _UNICODE_STRING *)((char *)NdisVcHandle + 296),
      0,
      (__int128 *)&GUID_NDIS_NOTIFY_VC_REMOVAL,
      (struct tagWNODE_SINGLE_INSTANCE **)&WnodeEventItem);
    if ( WnodeEventItem && (v8 = IoWMIWriteEvent(WnodeEventItem), v8 < 0) )
    {
      if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v6) = 2;
        WPP_RECORDER_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          v6,
          18,
          20,
          (struct _GUID *)&WPP_de7b4475eb543019aeb186df8ee4bca2_Traceguids,
          v8);
      }
      v9 = (char *)NdisVcHandle + 192;
      if ( (byte_14011B001 & 0x10) != 0 )
        McTemplateK0qqq_EtwWriteTransfer(
          v7,
          (unsigned int)IoWMIWriteEventFailed,
          *((_DWORD *)NdisVcHandle + 48) + 4008,
          v8,
          1,
          0);
      else
        v9 = (char *)NdisVcHandle + 192;
      ExFreePoolWithTag(WnodeEventItem, 0);
    }
    else
    {
      v9 = (char *)NdisVcHandle + 192;
    }
    KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(*(_QWORD *)v9 + 1344LL));
    v10 = (NDIS_HANDLE *)*((_QWORD *)NdisVcHandle + 40);
    if ( v10[1] != (char *)NdisVcHandle + 320 )
      goto LABEL_37;
    v11 = (NDIS_HANDLE *)*((_QWORD *)NdisVcHandle + 41);
    if ( *v11 != (char *)NdisVcHandle + 320 )
      goto LABEL_37;
    *v11 = v10;
    v10[1] = v11;
    --*(_WORD *)(*(_QWORD *)v9 + 1384LL);
    ExFreePoolWithTag(*((PVOID *)NdisVcHandle + 38), 0);
    v12 = (KSPIN_LOCK *)(*(_QWORD *)v9 + 1344LL);
    *((_QWORD *)NdisVcHandle + 38) = 0;
    *((_DWORD *)NdisVcHandle + 74) = 0;
    KeReleaseSpinLockFromDpcLevel(v12);
  }
  v13 = (void (__fastcall *)(_QWORD))*((_QWORD *)NdisVcHandle + 12);
  if ( v13 )
    v13(*((_QWORD *)NdisVcHandle + 13));
  KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(*((_QWORD *)NdisVcHandle + 10) + 232LL));
  v14 = (NDIS_HANDLE *)*((_QWORD *)NdisVcHandle + 4);
  if ( v14[1] != (char *)NdisVcHandle + 32 )
    goto LABEL_37;
  v15 = (NDIS_HANDLE *)*((_QWORD *)NdisVcHandle + 5);
  if ( *v15 != (char *)NdisVcHandle + 32 )
    goto LABEL_37;
  *v15 = v14;
  v14[1] = v15;
  KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(*((_QWORD *)NdisVcHandle + 10) + 232LL));
  v16 = *((_QWORD *)NdisVcHandle + 17);
  if ( v16 )
  {
    KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(v16 + 232));
    v17 = (_QWORD *)*((_QWORD *)NdisVcHandle + 19);
    if ( (NDIS_HANDLE)v17[1] == (char *)NdisVcHandle + 152 )
    {
      v18 = (NDIS_HANDLE *)*((_QWORD *)NdisVcHandle + 20);
      if ( *v18 == (char *)NdisVcHandle + 152 )
      {
        *v18 = v17;
        v17[1] = v18;
        KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(*((_QWORD *)NdisVcHandle + 17) + 232LL));
        goto LABEL_31;
      }
    }
LABEL_37:
    __fastfail(3u);
  }
LABEL_31:
  v5 = 0;
LABEL_32:
  KeReleaseSpinLock((PKSPIN_LOCK)NdisVcHandle + 2, v4);
  if ( !v5 )
    ndisDereferenceVcPtr((struct _NDIS_CO_VC_PTR_BLOCK *)NdisVcHandle);
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v19) = 4;
    WPP_RECORDER_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v19,
      19,
      21,
      (struct _GUID *)&WPP_de7b4475eb543019aeb186df8ee4bca2_Traceguids,
      v5);
  }
  return v5;
}

```

## disassembly

```asm
0x140088ab0  push    rbx
0x140088ab2  push    rbp
0x140088ab3  push    rsi
0x140088ab4  push    rdi
0x140088ab5  push    r12
0x140088ab7  push    r15
0x140088ab9  sub     rsp, 58h
0x140088abd  mov     rbx, rcx
0x140088ac0  lea     rbp, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140088ac7  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140088ace  jz      short loc_140088B05
0x140088ad0  mov     rax, [rcx+8]
0x140088ad4  mov     edx, [rax]
0x140088ad6  mov     rax, [rcx+48h]
0x140088ada  mov     [rsp+88h+var_40], edx
0x140088ade  mov     [rsp+88h+var_48], rax
0x140088ae3  mov     eax, [rcx]
0x140088ae5  mov     [rsp+88h+var_50], eax
0x140088ae9  mov     eax, [rcx+4]
0x140088aec  mov     [rsp+88h+var_58], eax
0x140088af0  mov     qword ptr [rsp+88h+var_60], rcx
0x140088af5  mov     rcx, cs:WPP_GLOBAL_Control
0x140088afc  mov     rcx, [rcx+40h]
0x140088b00  call    WPP_RECORDER_SF_qLLqL
0x140088b05  lea     rcx, [rbx+10h]; SpinLock
0x140088b09  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140088b10  nop     dword ptr [rax+rax+00h]
0x140088b15  mov     rcx, [rbx+8]
0x140088b19  lea     rsi, WPP_de7b4475eb543019aeb186df8ee4bca2_Traceguids
0x140088b20  mov     r12b, al
0x140088b23  mov     edx, [rcx]
0x140088b25  test    dl, 3
0x140088b28  jz      short loc_140088B34
0x140088b2a  mov     edi, 10003h
0x140088b2f  jmp     loc_140088DB5
0x140088b34  test    dl, 4
0x140088b37  jz      short loc_140088B43
0x140088b39  mov     edi, 0C0010002h
0x140088b3e  jmp     loc_140088DB5
0x140088b43  bts     dword ptr [rbx+4], 1Fh
0x140088b48  cmp     dword ptr [rbx+58h], 0
0x140088b4c  jz      short loc_140088B5B
0x140088b4e  cmp     qword ptr [rbx+0D8h], 0
0x140088b56  jz      short loc_140088B5B
0x140088b58  or      dword ptr [rcx], 8
0x140088b5b  lea     rdx, [rbx+128h]; struct _UNICODE_STRING *
0x140088b62  cmp     qword ptr [rdx+8], 0
0x140088b67  jz      loc_140088CFC
0x140088b6d  lea     rax, [rsp+88h+WnodeEventItem]
0x140088b75  mov     [rsp+88h+WnodeEventItem], 0
0x140088b81  lea     rdi, [rbx+0C0h]
0x140088b88  mov     [rsp+88h+var_68], rax; struct tagWNODE_SINGLE_INSTANCE **
0x140088b8d  mov     rcx, [rdi]; struct _NDIS_MINIPORT_BLOCK *
0x140088b90  lea     r9, GUID_NDIS_NOTIFY_VC_REMOVAL; void *
0x140088b97  xor     r8d, r8d; unsigned int
0x140088b9a  call    ?ndisSetupWmiNode@@YAXPEAU_NDIS_MINIPORT_BLOCK@@PEBU_UNICODE_STRING@@KPEAXPEAPEAUtagWNODE_SINGLE_INSTANCE@@@Z; ndisSetupWmiNode(_NDIS_MINIPORT_BLOCK *,_UNICODE_STRING const *,ulong,void *,tagWNODE_SINGLE_INSTANCE * *)
0x140088b9f  cmp     [rsp+88h+WnodeEventItem], 0
0x140088ba8  jz      loc_140088C6A
0x140088bae  mov     rcx, [rsp+88h+WnodeEventItem]; WnodeEventItem
0x140088bb6  call    cs:__imp_IoWMIWriteEvent
0x140088bbd  nop     dword ptr [rax+rax+00h]
0x140088bc2  mov     ebp, eax
0x140088bc4  test    eax, eax
0x140088bc6  jns     loc_140088C63
0x140088bcc  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140088bd3  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140088bda  jz      short loc_140088C0A
0x140088bdc  mov     rcx, cs:WPP_GLOBAL_Control
0x140088be3  mov     r9d, 14h; int
0x140088be9  mov     dword ptr [rsp+88h+var_60], ebp; char
0x140088bed  mov     dl, 2; int
0x140088bef  mov     [rsp+88h+var_68], rsi; struct _GUID *
0x140088bf4  mov     rcx, [rcx+40h]; int
0x140088bf8  lea     r8d, [r9-2]; int
0x140088bfc  call    WPP_RECORDER_SF_d
0x140088c01  lea     rsi, [rbx+0C0h]
0x140088c08  jmp     short loc_140088C0D
0x140088c0a  mov     rsi, rdi
0x140088c0d  test    cs:byte_14011B001, 10h
0x140088c14  jz      short loc_140088C41
0x140088c16  mov     r8, [rdi]
0x140088c19  lea     rdx, IoWMIWriteEventFailed
0x140088c20  add     r8, 0FA8h
0x140088c27  mov     dword ptr [rsp+88h+var_60], 0
0x140088c2f  mov     r9d, ebp
0x140088c32  mov     dword ptr [rsp+88h+var_68], 10001h
0x140088c3a  call    McTemplateK0qqq_EtwWriteTransfer
0x140088c3f  jmp     short loc_140088C44
0x140088c41  mov     rsi, rdi
0x140088c44  mov     rcx, [rsp+88h+WnodeEventItem]; P
0x140088c4c  xor     edx, edx; Tag
0x140088c4e  call    cs:__imp_ExFreePoolWithTag
0x140088c55  nop     dword ptr [rax+rax+00h]
0x140088c5a  lea     rbp, WPP_RECORDER_INITIALIZED
0x140088c61  jmp     short loc_140088C6D
0x140088c63  lea     rbp, WPP_RECORDER_INITIALIZED
0x140088c6a  mov     rsi, rdi
0x140088c6d  mov     rcx, [rsi]
0x140088c70  mov     edi, 540h
0x140088c75  add     rcx, rdi; SpinLock
0x140088c78  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140088c7f  nop     dword ptr [rax+rax+00h]
0x140088c84  lea     rax, [rbx+140h]
0x140088c8b  mov     rdx, [rax]
0x140088c8e  cmp     [rdx+8], rax
0x140088c92  jnz     loc_140088E12
0x140088c98  mov     rcx, [rax+8]
0x140088c9c  cmp     [rcx], rax
0x140088c9f  jnz     loc_140088E12
0x140088ca5  mov     [rcx], rdx
0x140088ca8  mov     [rdx+8], rcx
0x140088cac  mov     ecx, 0FFFFh
0x140088cb1  mov     rax, [rsi]
0x140088cb4  xor     edx, edx; Tag
0x140088cb6  add     [rax+568h], cx
0x140088cbd  mov     rcx, [rbx+130h]; P
0x140088cc4  call    cs:__imp_ExFreePoolWithTag
0x140088ccb  nop     dword ptr [rax+rax+00h]
0x140088cd0  mov     rcx, [rsi]
0x140088cd3  xor     eax, eax
0x140088cd5  add     rcx, rdi; SpinLock
0x140088cd8  mov     qword ptr [rbx+130h], 0
0x140088ce3  mov     [rbx+128h], eax
0x140088ce9  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140088cf0  nop     dword ptr [rax+rax+00h]
0x140088cf5  lea     rsi, WPP_de7b4475eb543019aeb186df8ee4bca2_Traceguids
0x140088cfc  mov     rax, [rbx+60h]
0x140088d00  test    rax, rax
0x140088d03  jz      short loc_140088D0E
0x140088d05  mov     rcx, [rbx+68h]
0x140088d09  call    _guard_dispatch_icall
0x140088d0e  mov     rcx, [rbx+50h]
0x140088d12  mov     edi, 0E8h
0x140088d17  add     rcx, rdi; SpinLock
0x140088d1a  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140088d21  nop     dword ptr [rax+rax+00h]
0x140088d26  lea     rax, [rbx+20h]
0x140088d2a  mov     rdx, [rax]
0x140088d2d  cmp     [rdx+8], rax
0x140088d31  jnz     loc_140088E12
0x140088d37  mov     rcx, [rax+8]
0x140088d3b  cmp     [rcx], rax
0x140088d3e  jnz     loc_140088E12
0x140088d44  mov     [rcx], rdx
0x140088d47  mov     [rdx+8], rcx
0x140088d4b  mov     rcx, [rbx+50h]
0x140088d4f  add     rcx, rdi; SpinLock
0x140088d52  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140088d59  nop     dword ptr [rax+rax+00h]
0x140088d5e  mov     rcx, [rbx+88h]
0x140088d65  test    rcx, rcx
0x140088d68  jz      short loc_140088DB3
0x140088d6a  add     rcx, rdi; SpinLock
0x140088d6d  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140088d74  nop     dword ptr [rax+rax+00h]
0x140088d79  lea     rax, [rbx+98h]
0x140088d80  mov     r8, [rax]
0x140088d83  cmp     [r8+8], rax
0x140088d87  jnz     loc_140088E12
0x140088d8d  mov     rdx, [rax+8]
0x140088d91  cmp     [rdx], rax
0x140088d94  jnz     short loc_140088E12
0x140088d96  mov     [rdx], r8
0x140088d99  mov     [r8+8], rdx
0x140088d9d  mov     rcx, [rbx+88h]
0x140088da4  add     rcx, rdi; SpinLock
0x140088da7  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140088dae  nop     dword ptr [rax+rax+00h]
0x140088db3  xor     edi, edi
0x140088db5  mov     dl, r12b; NewIrql
0x140088db8  lea     rcx, [rbx+10h]; SpinLock
0x140088dbc  call    cs:__imp_KeReleaseSpinLock
0x140088dc3  nop     dword ptr [rax+rax+00h]
0x140088dc8  test    edi, edi
0x140088dca  jnz     short loc_140088DD4
0x140088dcc  mov     rcx, rbx; struct _NDIS_CO_VC_PTR_BLOCK *
0x140088dcf  call    ?ndisDereferenceVcPtr@@YAXPEAU_NDIS_CO_VC_PTR_BLOCK@@@Z; ndisDereferenceVcPtr(_NDIS_CO_VC_PTR_BLOCK *)
0x140088dd4  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x140088ddb  jz      short loc_140088E02
0x140088ddd  mov     rcx, cs:WPP_GLOBAL_Control
0x140088de4  mov     r9d, 15h; int
0x140088dea  mov     dword ptr [rsp+88h+var_60], edi; char
0x140088dee  mov     dl, 4; int
0x140088df0  mov     [rsp+88h+var_68], rsi; struct _GUID *
0x140088df5  mov     rcx, [rcx+40h]; int
0x140088df9  lea     r8d, [r9-2]; int
0x140088dfd  call    WPP_RECORDER_SF_d
0x140088e02  mov     eax, edi
0x140088e04  add     rsp, 58h
0x140088e08  pop     r15
0x140088e0a  pop     r12
0x140088e0c  pop     rdi
0x140088e0d  pop     rsi
0x140088e0e  pop     rbp
0x140088e0f  pop     rbx
0x140088e10  retn
0x140088e12  mov     ecx, 3
0x140088e17  int     29h; Win8: RtlFailFast(ecx)
```
