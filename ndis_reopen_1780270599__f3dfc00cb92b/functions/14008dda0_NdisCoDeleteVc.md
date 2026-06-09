# NdisCoDeleteVc

- ea: `0x14008dda0`
- end: `0x14008e109`
- name: `NdisCoDeleteVc`
- size: `873`
- prototype: `NDIS_STATUS __stdcall(NDIS_HANDLE NdisVcHandle)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x1400d7890`

## callees

- `0x14001cf60`
- `0x14005b320`
- `0x14008dda0`
- `0x140092d80`
- `0x1400d6270`
- `0x1400d7bd4`
- `0x1400eb460`

## import_xrefs

- `ntoskrnl!IoWMIWriteEvent` at `0x14008dea6`
- `ntoskrnl!IoWMIWriteEvent` at `0x14008dea6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008df3e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008dfb4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008df3e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008dfb4`
- `ntoskrnl!KeReleaseSpinLock` at `0x14008e0ac`
- `ntoskrnl!KeReleaseSpinLock` at `0x14008e0ac`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14008ddf9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14008ddf9`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14008df68`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14008e00a`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14008e05d`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14008df68`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14008e00a`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14008e05d`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14008dfd9`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14008e042`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14008e097`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14008dfd9`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14008e042`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14008e097`

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
      &GUID_NDIS_NOTIFY_VC_REMOVAL,
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
      if ( (byte_140121001 & 0x10) != 0 )
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
0x14008dda0  push    rbx
0x14008dda2  push    rbp
0x14008dda3  push    rsi
0x14008dda4  push    rdi
0x14008dda5  push    r12
0x14008dda7  push    r15
0x14008dda9  sub     rsp, 58h
0x14008ddad  mov     rbx, rcx
0x14008ddb0  lea     rbp, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14008ddb7  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14008ddbe  jz      short loc_14008DDF5
0x14008ddc0  mov     rax, [rcx+8]
0x14008ddc4  mov     edx, [rax]
0x14008ddc6  mov     rax, [rcx+48h]
0x14008ddca  mov     [rsp+88h+var_40], edx
0x14008ddce  mov     [rsp+88h+var_48], rax
0x14008ddd3  mov     eax, [rcx]
0x14008ddd5  mov     [rsp+88h+var_50], eax
0x14008ddd9  mov     eax, [rcx+4]
0x14008dddc  mov     [rsp+88h+var_58], eax
0x14008dde0  mov     qword ptr [rsp+88h+var_60], rcx
0x14008dde5  mov     rcx, cs:WPP_GLOBAL_Control
0x14008ddec  mov     rcx, [rcx+40h]
0x14008ddf0  call    WPP_RECORDER_SF_qLLqL
0x14008ddf5  lea     rcx, [rbx+10h]; SpinLock
0x14008ddf9  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14008de00  nop     dword ptr [rax+rax+00h]
0x14008de05  mov     rcx, [rbx+8]
0x14008de09  lea     rsi, WPP_de7b4475eb543019aeb186df8ee4bca2_Traceguids
0x14008de10  mov     r12b, al
0x14008de13  mov     edx, [rcx]
0x14008de15  test    dl, 3
0x14008de18  jz      short loc_14008DE24
0x14008de1a  mov     edi, 10003h
0x14008de1f  jmp     loc_14008E0A5
0x14008de24  test    dl, 4
0x14008de27  jz      short loc_14008DE33
0x14008de29  mov     edi, 0C0010002h
0x14008de2e  jmp     loc_14008E0A5
0x14008de33  bts     dword ptr [rbx+4], 1Fh
0x14008de38  cmp     dword ptr [rbx+58h], 0
0x14008de3c  jz      short loc_14008DE4B
0x14008de3e  cmp     qword ptr [rbx+0D8h], 0
0x14008de46  jz      short loc_14008DE4B
0x14008de48  or      dword ptr [rcx], 8
0x14008de4b  lea     rdx, [rbx+128h]; struct _UNICODE_STRING *
0x14008de52  cmp     qword ptr [rdx+8], 0
0x14008de57  jz      loc_14008DFEC
0x14008de5d  lea     rax, [rsp+88h+WnodeEventItem]
0x14008de65  mov     [rsp+88h+WnodeEventItem], 0
0x14008de71  lea     rdi, [rbx+0C0h]
0x14008de78  mov     [rsp+88h+var_68], rax; struct tagWNODE_SINGLE_INSTANCE **
0x14008de7d  mov     rcx, [rdi]; struct _NDIS_MINIPORT_BLOCK *
0x14008de80  lea     r9, GUID_NDIS_NOTIFY_VC_REMOVAL; void *
0x14008de87  xor     r8d, r8d; unsigned int
0x14008de8a  call    ?ndisSetupWmiNode@@YAXPEAU_NDIS_MINIPORT_BLOCK@@PEBU_UNICODE_STRING@@KPEAXPEAPEAUtagWNODE_SINGLE_INSTANCE@@@Z; ndisSetupWmiNode(_NDIS_MINIPORT_BLOCK *,_UNICODE_STRING const *,ulong,void *,tagWNODE_SINGLE_INSTANCE * *)
0x14008de8f  cmp     [rsp+88h+WnodeEventItem], 0
0x14008de98  jz      loc_14008DF5A
0x14008de9e  mov     rcx, [rsp+88h+WnodeEventItem]; WnodeEventItem
0x14008dea6  call    cs:__imp_IoWMIWriteEvent
0x14008dead  nop     dword ptr [rax+rax+00h]
0x14008deb2  mov     ebp, eax
0x14008deb4  test    eax, eax
0x14008deb6  jns     loc_14008DF53
0x14008debc  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14008dec3  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14008deca  jz      short loc_14008DEFA
0x14008decc  mov     rcx, cs:WPP_GLOBAL_Control
0x14008ded3  mov     r9d, 14h; int
0x14008ded9  mov     dword ptr [rsp+88h+var_60], ebp; char
0x14008dedd  mov     dl, 2; int
0x14008dedf  mov     [rsp+88h+var_68], rsi; struct _GUID *
0x14008dee4  mov     rcx, [rcx+40h]; int
0x14008dee8  lea     r8d, [r9-2]; int
0x14008deec  call    WPP_RECORDER_SF_d
0x14008def1  lea     rsi, [rbx+0C0h]
0x14008def8  jmp     short loc_14008DEFD
0x14008defa  mov     rsi, rdi
0x14008defd  test    cs:byte_140121001, 10h
0x14008df04  jz      short loc_14008DF31
0x14008df06  mov     r8, [rdi]
0x14008df09  lea     rdx, IoWMIWriteEventFailed
0x14008df10  add     r8, 0FA8h
0x14008df17  mov     dword ptr [rsp+88h+var_60], 0
0x14008df1f  mov     r9d, ebp
0x14008df22  mov     dword ptr [rsp+88h+var_68], 10001h
0x14008df2a  call    McTemplateK0qqq_EtwWriteTransfer
0x14008df2f  jmp     short loc_14008DF34
0x14008df31  mov     rsi, rdi
0x14008df34  mov     rcx, [rsp+88h+WnodeEventItem]; P
0x14008df3c  xor     edx, edx; Tag
0x14008df3e  call    cs:__imp_ExFreePoolWithTag
0x14008df45  nop     dword ptr [rax+rax+00h]
0x14008df4a  lea     rbp, WPP_RECORDER_INITIALIZED
0x14008df51  jmp     short loc_14008DF5D
0x14008df53  lea     rbp, WPP_RECORDER_INITIALIZED
0x14008df5a  mov     rsi, rdi
0x14008df5d  mov     rcx, [rsi]
0x14008df60  mov     edi, 540h
0x14008df65  add     rcx, rdi; SpinLock
0x14008df68  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14008df6f  nop     dword ptr [rax+rax+00h]
0x14008df74  lea     rax, [rbx+140h]
0x14008df7b  mov     rdx, [rax]
0x14008df7e  cmp     [rdx+8], rax
0x14008df82  jnz     loc_14008E102
0x14008df88  mov     rcx, [rax+8]
0x14008df8c  cmp     [rcx], rax
0x14008df8f  jnz     loc_14008E102
0x14008df95  mov     [rcx], rdx
0x14008df98  mov     [rdx+8], rcx
0x14008df9c  mov     ecx, 0FFFFh
0x14008dfa1  mov     rax, [rsi]
0x14008dfa4  xor     edx, edx; Tag
0x14008dfa6  add     [rax+568h], cx
0x14008dfad  mov     rcx, [rbx+130h]; P
0x14008dfb4  call    cs:__imp_ExFreePoolWithTag
0x14008dfbb  nop     dword ptr [rax+rax+00h]
0x14008dfc0  mov     rcx, [rsi]
0x14008dfc3  xor     eax, eax
0x14008dfc5  add     rcx, rdi; SpinLock
0x14008dfc8  mov     qword ptr [rbx+130h], 0
0x14008dfd3  mov     [rbx+128h], eax
0x14008dfd9  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14008dfe0  nop     dword ptr [rax+rax+00h]
0x14008dfe5  lea     rsi, WPP_de7b4475eb543019aeb186df8ee4bca2_Traceguids
0x14008dfec  mov     rax, [rbx+60h]
0x14008dff0  test    rax, rax
0x14008dff3  jz      short loc_14008DFFE
0x14008dff5  mov     rcx, [rbx+68h]
0x14008dff9  call    _guard_dispatch_icall
0x14008dffe  mov     rcx, [rbx+50h]
0x14008e002  mov     edi, 0E8h
0x14008e007  add     rcx, rdi; SpinLock
0x14008e00a  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14008e011  nop     dword ptr [rax+rax+00h]
0x14008e016  lea     rax, [rbx+20h]
0x14008e01a  mov     rdx, [rax]
0x14008e01d  cmp     [rdx+8], rax
0x14008e021  jnz     loc_14008E102
0x14008e027  mov     rcx, [rax+8]
0x14008e02b  cmp     [rcx], rax
0x14008e02e  jnz     loc_14008E102
0x14008e034  mov     [rcx], rdx
0x14008e037  mov     [rdx+8], rcx
0x14008e03b  mov     rcx, [rbx+50h]
0x14008e03f  add     rcx, rdi; SpinLock
0x14008e042  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14008e049  nop     dword ptr [rax+rax+00h]
0x14008e04e  mov     rcx, [rbx+88h]
0x14008e055  test    rcx, rcx
0x14008e058  jz      short loc_14008E0A3
0x14008e05a  add     rcx, rdi; SpinLock
0x14008e05d  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14008e064  nop     dword ptr [rax+rax+00h]
0x14008e069  lea     rax, [rbx+98h]
0x14008e070  mov     r8, [rax]
0x14008e073  cmp     [r8+8], rax
0x14008e077  jnz     loc_14008E102
0x14008e07d  mov     rdx, [rax+8]
0x14008e081  cmp     [rdx], rax
0x14008e084  jnz     short loc_14008E102
0x14008e086  mov     [rdx], r8
0x14008e089  mov     [r8+8], rdx
0x14008e08d  mov     rcx, [rbx+88h]
0x14008e094  add     rcx, rdi; SpinLock
0x14008e097  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14008e09e  nop     dword ptr [rax+rax+00h]
0x14008e0a3  xor     edi, edi
0x14008e0a5  mov     dl, r12b; NewIrql
0x14008e0a8  lea     rcx, [rbx+10h]; SpinLock
0x14008e0ac  call    cs:__imp_KeReleaseSpinLock
0x14008e0b3  nop     dword ptr [rax+rax+00h]
0x14008e0b8  test    edi, edi
0x14008e0ba  jnz     short loc_14008E0C4
0x14008e0bc  mov     rcx, rbx; struct _NDIS_CO_VC_PTR_BLOCK *
0x14008e0bf  call    ?ndisDereferenceVcPtr@@YAXPEAU_NDIS_CO_VC_PTR_BLOCK@@@Z; ndisDereferenceVcPtr(_NDIS_CO_VC_PTR_BLOCK *)
0x14008e0c4  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14008e0cb  jz      short loc_14008E0F2
0x14008e0cd  mov     rcx, cs:WPP_GLOBAL_Control
0x14008e0d4  mov     r9d, 15h; int
0x14008e0da  mov     dword ptr [rsp+88h+var_60], edi; char
0x14008e0de  mov     dl, 4; int
0x14008e0e0  mov     [rsp+88h+var_68], rsi; struct _GUID *
0x14008e0e5  mov     rcx, [rcx+40h]; int
0x14008e0e9  lea     r8d, [r9-2]; int
0x14008e0ed  call    WPP_RECORDER_SF_d
0x14008e0f2  mov     eax, edi
0x14008e0f4  add     rsp, 58h
0x14008e0f8  pop     r15
0x14008e0fa  pop     r12
0x14008e0fc  pop     rdi
0x14008e0fd  pop     rsi
0x14008e0fe  pop     rbp
0x14008e0ff  pop     rbx
0x14008e100  retn
0x14008e102  mov     ecx, 3
0x14008e107  int     29h; Win8: RtlFailFast(ecx)
```
