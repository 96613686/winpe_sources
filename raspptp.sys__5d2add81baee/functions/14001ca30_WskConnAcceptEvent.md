# WskConnAcceptEvent

- ea: `0x14001ca30`
- end: `0x14001ccef`
- name: `WskConnAcceptEvent`
- size: `703`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x140007710`
- `0x14001ca30`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001ca5d`
- `ntoskrnl!ExAllocatePool2` at `0x14001ca5d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ccc3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ccc3`
- `ntoskrnl!ExInterlockedInsertTailList` at `0x14001caf8`
- `ntoskrnl!ExInterlockedInsertTailList` at `0x14001caf8`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14001cb79`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14001cbb7`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14001cb79`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14001cbb7`
- `ntoskrnl!IoAllocateIrp` at `0x14001cc14`
- `ntoskrnl!IoAllocateIrp` at `0x14001cc14`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001cbca`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001cbca`
- `NDIS!NdisGetVersion` at `0x14001cb3c`
- `NDIS!NdisGetVersion` at `0x14001cb85`
- `NDIS!NdisGetVersion` at `0x14001cb3c`
- `NDIS!NdisGetVersion` at `0x14001cb85`

## pseudocode

```c
__int64 __fastcall WskConnAcceptEvent(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int128 *a4,
        __int64 (__fastcall ***a5)(_QWORD, _QWORD, __int64, __int64, __int64, __int128 *, _QWORD, _QWORD, _QWORD, PIRP),
        volatile signed __int32 **a6,
        _QWORD *a7)
{
  volatile signed __int32 *Pool2; // rbx
  int v10; // edi
  __int128 v11; // xmm0
  PIRP Irp; // rax
  PIRP v13; // rcx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  __int64 (__fastcall **v15)(_QWORD, _QWORD, __int64, __int64, __int64, __int128 *, _QWORD, _QWORD, _QWORD, PIRP); // rax
  __int128 v17; // [rsp+60h] [rbp-48h] BYREF

  v17 = 0;
  Pool2 = (volatile signed __int32 *)ExAllocatePool2(64, 576, 1634623863);
  if ( !Pool2 )
  {
    v10 = -1073741616;
LABEL_11:
    *a7 = 0;
    *a6 = 0;
    return (unsigned int)v10;
  }
  if ( (*(_DWORD *)(a1 + 392) & 0x20) == 0 )
    goto LABEL_4;
  *Pool2 = 1129010007;
  *((_QWORD *)Pool2 + 2) = *(_QWORD *)(a1 + 16);
  *((_QWORD *)Pool2 + 8) = *(_QWORD *)(a1 + 64);
  *((_QWORD *)Pool2 + 3) = *(_QWORD *)(a1 + 24);
  *((_QWORD *)Pool2 + 4) = *(_QWORD *)(a1 + 32);
  *((_QWORD *)Pool2 + 9) = *(_QWORD *)(a1 + 72);
  *((_QWORD *)Pool2 + 6) = *(_QWORD *)(a1 + 48);
  *((_QWORD *)Pool2 + 54) = Pool2 + 106;
  *((_QWORD *)Pool2 + 53) = Pool2 + 106;
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 512));
  ExInterlockedInsertTailList((PLIST_ENTRY)(a1 + 424), (PLIST_ENTRY)(Pool2 + 106), (PKSPIN_LOCK)(a1 + 456));
  *((_QWORD *)Pool2 + 65) = FreeSockHandle;
  *((_QWORD *)Pool2 + 48) = a5;
  *((_DWORD *)Pool2 + 98) = 20;
  *((_QWORD *)Pool2 + 63) = a1;
  *((_DWORD *)Pool2 + 128) = 1;
  NdisGetVersion();
  ExInitializeNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)Pool2 + 1, 0, 0, 0x200u, 0x30u, 0x72774152u, 0xAu);
  NdisGetVersion();
  ExInitializeNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)Pool2 + 2, 0, 0, 0x200u, 0x40u, 0x73774152u, 0xAu);
  KeInitializeSpinLock((PKSPIN_LOCK)Pool2 + 57);
  *((_DWORD *)Pool2 + 98) |= 0x800u;
  v11 = *a4;
  if ( (unsigned __int16)*a4 == 2 )
  {
    *(_OWORD *)(Pool2 + 118) = v11;
  }
  else
  {
    *(_OWORD *)(Pool2 + 118) = v11;
    *(_OWORD *)(Pool2 + 121) = *(__int128 *)((char *)a4 + 12);
  }
  *a6 = Pool2;
  *a7 = &g_WskClientConnDispatch;
  Irp = IoAllocateIrp(1, 0);
  v13 = Irp;
  if ( !Irp )
  {
LABEL_4:
    v10 = -1073741616;
LABEL_10:
    ExFreePoolWithTag((PVOID)Pool2, 0);
    goto LABEL_11;
  }
  _InterlockedIncrement(Pool2 + 128);
  _InterlockedIncrement(Pool2 + 128);
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  CurrentStackLocation[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&WskAcceptCompletion;
  CurrentStackLocation[-1].Context = (PVOID)Pool2;
  CurrentStackLocation[-1].Control = -32;
  *(_QWORD *)&v17 = &NPI_WSK_INTERFACE_ID;
  v15 = *a5;
  DWORD2(v17) = 192;
  v10 = (*v15)(a5, 0, 16386, 0xFFFF, 16, &v17, 0, 0, 0, v13);
  if ( v10 < 0 )
    goto LABEL_10;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14001ca30  push    rbx
0x14001ca32  push    rbp
0x14001ca33  push    rsi
0x14001ca34  push    rdi
0x14001ca35  push    r12
0x14001ca37  push    r14
0x14001ca39  push    r15
0x14001ca3b  sub     rsp, 70h
0x14001ca3f  mov     rsi, rcx
0x14001ca42  xorps   xmm0, xmm0
0x14001ca45  mov     ecx, 40h ; '@'
0x14001ca4a  mov     edx, 240h
0x14001ca4f  mov     r8d, 616E6177h
0x14001ca55  mov     rdi, r9
0x14001ca58  movups  [rsp+0A8h+var_48], xmm0
0x14001ca5d  call    cs:__imp_ExAllocatePool2
0x14001ca64  nop     dword ptr [rax+rax+00h]
0x14001ca69  mov     r14, [rsp+0A8h+arg_30]
0x14001ca71  mov     rbx, rax
0x14001ca74  mov     r15, [rsp+0A8h+arg_28]
0x14001ca7c  test    rax, rax
0x14001ca7f  jnz     short loc_14001CA8B
0x14001ca81  mov     edi, 0C00000D0h
0x14001ca86  jmp     loc_14001CCCF
0x14001ca8b  mov     eax, [rsi+188h]
0x14001ca91  test    al, 20h
0x14001ca93  jnz     short loc_14001CA9F
0x14001ca95  mov     edi, 0C00000D0h
0x14001ca9a  jmp     loc_14001CCBE
0x14001ca9f  mov     dword ptr [rbx], 434B5357h
0x14001caa5  lea     rdx, [rbx+1A8h]; ListEntry
0x14001caac  mov     rax, [rsi+10h]
0x14001cab0  mov     [rbx+10h], rax
0x14001cab4  mov     rax, [rsi+40h]
0x14001cab8  mov     [rbx+40h], rax
0x14001cabc  mov     rax, [rsi+18h]
0x14001cac0  mov     [rbx+18h], rax
0x14001cac4  mov     rax, [rsi+20h]
0x14001cac8  mov     [rbx+20h], rax
0x14001cacc  mov     rax, [rsi+48h]
0x14001cad0  mov     [rbx+48h], rax
0x14001cad4  mov     rax, [rsi+30h]
0x14001cad8  mov     [rbx+30h], rax
0x14001cadc  mov     [rdx+8], rdx
0x14001cae0  mov     [rdx], rdx
0x14001cae3  lock inc dword ptr [rsi+200h]
0x14001caea  lea     r8, [rsi+1C8h]; Lock
0x14001caf1  lea     rcx, [rsi+1A8h]; ListHead
0x14001caf8  call    cs:__imp_ExInterlockedInsertTailList
0x14001caff  nop     dword ptr [rax+rax+00h]
0x14001cb04  mov     rbp, [rsp+0A8h+arg_20]
0x14001cb0c  lea     rax, FreeSockHandle
0x14001cb13  mov     [rbx+208h], rax
0x14001cb1a  mov     [rbx+180h], rbp
0x14001cb21  mov     dword ptr [rbx+188h], 14h
0x14001cb2b  mov     [rbx+1F8h], rsi
0x14001cb32  mov     dword ptr [rbx+200h], 1
0x14001cb3c  call    cs:__imp_NdisGetVersion
0x14001cb43  nop     dword ptr [rax+rax+00h]
0x14001cb48  mov     r12d, 0Ah
0x14001cb4e  lea     rcx, [rbx+80h]; Lookaside
0x14001cb55  mov     [rsp+0A8h+Depth], r12w; Depth
0x14001cb5b  mov     esi, 200h
0x14001cb60  mov     [rsp+0A8h+Tag], 72774152h; Tag
0x14001cb68  mov     r9d, esi; Flags
0x14001cb6b  xor     r8d, r8d; Free
0x14001cb6e  mov     [rsp+0A8h+Size], 30h ; '0'; Size
0x14001cb77  xor     edx, edx; Allocate
0x14001cb79  call    cs:__imp_ExInitializeNPagedLookasideList
0x14001cb80  nop     dword ptr [rax+rax+00h]
0x14001cb85  call    cs:__imp_NdisGetVersion
0x14001cb8c  nop     dword ptr [rax+rax+00h]
0x14001cb91  mov     [rsp+0A8h+Depth], r12w; Depth
0x14001cb97  lea     rcx, [rbx+100h]; Lookaside
0x14001cb9e  mov     [rsp+0A8h+Tag], 73774152h; Tag
0x14001cba6  mov     r9d, esi; Flags
0x14001cba9  xor     r8d, r8d; Free
0x14001cbac  mov     [rsp+0A8h+Size], 40h ; '@'; Size
0x14001cbb5  xor     edx, edx; Allocate
0x14001cbb7  call    cs:__imp_ExInitializeNPagedLookasideList
0x14001cbbe  nop     dword ptr [rax+rax+00h]
0x14001cbc3  lea     rcx, [rbx+1C8h]; SpinLock
0x14001cbca  call    cs:__imp_KeInitializeSpinLock
0x14001cbd1  nop     dword ptr [rax+rax+00h]
0x14001cbd6  bts     dword ptr [rbx+188h], 0Bh
0x14001cbde  cmp     word ptr [rdi], 2
0x14001cbe2  movups  xmm0, xmmword ptr [rdi]
0x14001cbe5  jnz     short loc_14001CBF1
0x14001cbe7  movdqu  xmmword ptr [rbx+1D8h], xmm0
0x14001cbef  jmp     short loc_14001CC03
0x14001cbf1  movups  xmmword ptr [rbx+1D8h], xmm0
0x14001cbf8  movups  xmm1, xmmword ptr [rdi+0Ch]
0x14001cbfc  movups  xmmword ptr [rbx+1E4h], xmm1
0x14001cc03  lea     rax, g_WskClientConnDispatch
0x14001cc0a  mov     [r15], rbx
0x14001cc0d  xor     edx, edx; ChargeQuota
0x14001cc0f  mov     [r14], rax
0x14001cc12  mov     cl, 1; StackSize
0x14001cc14  call    cs:__imp_IoAllocateIrp
0x14001cc1b  nop     dword ptr [rax+rax+00h]
0x14001cc20  mov     rcx, rax
0x14001cc23  test    rax, rax
0x14001cc26  jz      loc_14001CA95
0x14001cc2c  lock inc dword ptr [rbx+200h]
0x14001cc33  lock inc dword ptr [rbx+200h]
0x14001cc3a  mov     rax, [rax+0B8h]
0x14001cc41  lea     rdx, WskAcceptCompletion
0x14001cc48  mov     [rsp+0A8h+var_60], rcx
0x14001cc4d  mov     r9d, 0FFFFh
0x14001cc53  mov     [rsp+0A8h+var_68], 0
0x14001cc5c  lea     rcx, [rsp+0A8h+var_48]
0x14001cc61  mov     [rsp+0A8h+var_70], 0
0x14001cc6a  mov     r8d, 4002h
0x14001cc70  mov     [rax-10h], rdx
0x14001cc74  xor     edx, edx
0x14001cc76  mov     [rax-8], rbx
0x14001cc7a  mov     byte ptr [rax-45h], 0E0h
0x14001cc7e  lea     rax, NPI_WSK_INTERFACE_ID
0x14001cc85  mov     qword ptr [rsp+0A8h+var_48], rax
0x14001cc8a  mov     rax, [rbp+0]
0x14001cc8e  mov     qword ptr [rsp+0A8h+Depth], 0
0x14001cc97  mov     qword ptr [rsp+0A8h+Tag], rcx
0x14001cc9c  mov     rcx, rbp
0x14001cc9f  mov     dword ptr [rsp+0A8h+var_48+8], 0C0h
0x14001cca7  mov     rax, [rax]
0x14001ccaa  mov     [rsp+0A8h+Size], 10h
0x14001ccb3  call    _guard_dispatch_icall
0x14001ccb8  mov     edi, eax
0x14001ccba  test    eax, eax
0x14001ccbc  jns     short loc_14001CCDD
0x14001ccbe  xor     edx, edx; Tag
0x14001ccc0  mov     rcx, rbx; P
0x14001ccc3  call    cs:__imp_ExFreePoolWithTag
0x14001ccca  nop     dword ptr [rax+rax+00h]
0x14001cccf  mov     qword ptr [r14], 0
0x14001ccd6  mov     qword ptr [r15], 0
0x14001ccdd  mov     eax, edi
0x14001ccdf  add     rsp, 70h
0x14001cce3  pop     r15
0x14001cce5  pop     r14
0x14001cce7  pop     r12
0x14001cce9  pop     rdi
0x14001ccea  pop     rsi
0x14001cceb  pop     rbp
0x14001ccec  pop     rbx
0x14001cced  retn
```
