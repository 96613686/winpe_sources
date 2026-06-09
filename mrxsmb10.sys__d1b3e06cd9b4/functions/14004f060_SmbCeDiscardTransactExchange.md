# SmbCeDiscardTransactExchange

- ea: `0x14004f060`
- end: `0x14004f389`
- name: `SmbCeDiscardTransactExchange`
- size: `809`
- prototype: `void __stdcall(PVOID Context)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1400144a0`

## callees

- `0x14000e01c`
- `0x140016640`
- `0x14004f060`
- `0x140052944`

## import_xrefs

- `ntoskrnl!MmUnlockPages` at `0x14004f1ae`
- `ntoskrnl!MmUnlockPages` at `0x14004f1d2`
- `ntoskrnl!MmUnlockPages` at `0x14004f214`
- `ntoskrnl!MmUnlockPages` at `0x14004f238`
- `ntoskrnl!MmUnlockPages` at `0x14004f26b`
- `ntoskrnl!MmUnlockPages` at `0x14004f28f`
- `ntoskrnl!MmUnlockPages` at `0x14004f1ae`
- `ntoskrnl!MmUnlockPages` at `0x14004f1d2`
- `ntoskrnl!MmUnlockPages` at `0x14004f214`
- `ntoskrnl!MmUnlockPages` at `0x14004f238`
- `ntoskrnl!MmUnlockPages` at `0x14004f26b`
- `ntoskrnl!MmUnlockPages` at `0x14004f28f`
- `ntoskrnl!KeSetEvent` at `0x14004f198`
- `ntoskrnl!KeSetEvent` at `0x14004f198`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004f2ff`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004f2ff`
- `ntoskrnl!DbgPrint` at `0x14004f378`
- `ntoskrnl!DbgPrint` at `0x14004f378`
- `ntoskrnl!IoFreeMdl` at `0x14004f1c1`
- `ntoskrnl!IoFreeMdl` at `0x14004f1e5`
- `ntoskrnl!IoFreeMdl` at `0x14004f227`
- `ntoskrnl!IoFreeMdl` at `0x14004f24b`
- `ntoskrnl!IoFreeMdl` at `0x14004f27e`
- `ntoskrnl!IoFreeMdl` at `0x14004f2a2`
- `ntoskrnl!IoFreeMdl` at `0x14004f1c1`
- `ntoskrnl!IoFreeMdl` at `0x14004f1e5`
- `ntoskrnl!IoFreeMdl` at `0x14004f227`
- `ntoskrnl!IoFreeMdl` at `0x14004f24b`
- `ntoskrnl!IoFreeMdl` at `0x14004f27e`
- `ntoskrnl!IoFreeMdl` at `0x14004f2a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004f1f8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004f1f8`
- `rdbss!RxDispatchToWorkerThread` at `0x14004f329`
- `rdbss!RxDispatchToWorkerThread` at `0x14004f329`
- `mrxsmb!MRxSmbDeviceObject` at `0x14004f31d`

## pseudocode

```c
void __fastcall SmbCeDiscardTransactExchange(unsigned __int8 *Context)
{
  void *v2; // rcx
  struct _MDL *v3; // rcx
  struct _MDL *v4; // rcx
  struct _MDL *v5; // rcx
  struct _MDL *v6; // rcx
  struct _MDL *v7; // rcx
  struct _MDL *v8; // rcx
  __int64 v9; // rdi
  __int64 v10; // rsi
  int v11; // ecx
  int v12; // edx

  v2 = (void *)*((_QWORD *)Context + 60);
  if ( v2 )
  {
    ExFreePoolWithTag(v2, 0);
    *((_QWORD *)Context + 60) = 0;
  }
  v3 = (struct _MDL *)*((_QWORD *)Context + 57);
  if ( v3 )
  {
    MmUnlockPages(v3);
    IoFreeMdl(*((PMDL *)Context + 57));
  }
  v4 = (struct _MDL *)*((_QWORD *)Context + 53);
  if ( v4 )
  {
    MmUnlockPages(v4);
    IoFreeMdl(*((PMDL *)Context + 53));
  }
  v5 = (struct _MDL *)*((_QWORD *)Context + 48);
  if ( v5 )
  {
    MmUnlockPages(v5);
    IoFreeMdl(*((PMDL *)Context + 48));
  }
  v6 = (struct _MDL *)*((_QWORD *)Context + 55);
  if ( v6 )
  {
    MmUnlockPages(v6);
    IoFreeMdl(*((PMDL *)Context + 55));
  }
  v7 = (struct _MDL *)*((_QWORD *)Context + 46);
  if ( v7 && !_bittest16((const signed __int16 *)Context + 255, 0xDu) )
  {
    MmUnlockPages(v7);
    IoFreeMdl(*((PMDL *)Context + 46));
  }
  v8 = (struct _MDL *)*((_QWORD *)Context + 50);
  if ( v8 )
  {
    MmUnlockPages(v8);
    IoFreeMdl(*((PMDL *)Context + 50));
  }
  v9 = *((_QWORD *)Context + 66);
  if ( v9 )
  {
    v10 = *((_QWORD *)Context + 10);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_Dd(
        WPP_GLOBAL_Control->AttachedDevice,
        10,
        WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids,
        *((unsigned int *)Context + 109),
        *((_DWORD *)Context + 99));
    v11 = *(_DWORD *)(v10 + 328);
    v12 = *((_DWORD *)Context + 12);
    if ( !v11 || (*((_DWORD *)Context + 18) & 0x40) != 0 )
      v11 = *((_DWORD *)Context + 10);
    *(_DWORD *)(v9 + 68) = v11;
    if ( !v12 || v12 == -1073741802 )
      v12 = v11;
    *(_DWORD *)(v9 + 12) = v12;
    *(_DWORD *)(v9 + 56) = *((_DWORD *)Context + 117);
    *(_DWORD *)(v9 + 60) = *((_DWORD *)Context + 99);
    *(_DWORD *)(v9 + 64) = *((_DWORD *)Context + 109);
    *(_DWORD *)(v9 + 72) = *((_DWORD *)Context + 13);
    if ( (*(_DWORD *)(v9 + 8) & 1) != 0 )
    {
      if ( KeGetCurrentIrql() < 2u )
        (*(void (__fastcall **)(_QWORD))(v9 + 24))(*(_QWORD *)(v9 + 16));
      else
        RxDispatchToWorkerThread(
          MRxSmbDeviceObject,
          CriticalWorkQueue,
          *(PRX_WORKERTHREAD_ROUTINE *)(v9 + 24),
          *(PVOID *)(v9 + 16));
    }
    else
    {
      KeSetEvent((PRKEVENT)(v9 + 24), 0, 0);
    }
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)Context + 1, 0xFFFFFFFF) == 1 )
    SmbCeDiscardExchange(Context);
  if ( SmbCeTraceExchangeReferenceCount )
    DbgPrint(
      "Dereference Exchange %p Type(%ld) %s %ld %ld\n",
      Context,
      *Context,
      "SmbCeDiscardTransactExchange",
      394,
      *((_DWORD *)Context + 1));
}

```

## disassembly

```asm
0x14004f060  push    rbx
0x14004f062  sub     rsp, 30h
0x14004f066  mov     rbx, rcx
0x14004f069  mov     [rsp+38h+arg_8], rdi
0x14004f06e  mov     rcx, [rcx+1E0h]; P
0x14004f075  test    rcx, rcx
0x14004f078  jnz     loc_14004F1F6
0x14004f07e  mov     rcx, [rbx+1C8h]; MemoryDescriptorList
0x14004f085  test    rcx, rcx
0x14004f088  jnz     loc_14004F214
0x14004f08e  mov     rcx, [rbx+1A8h]; MemoryDescriptorList
0x14004f095  test    rcx, rcx
0x14004f098  jnz     loc_14004F1AE
0x14004f09e  mov     rcx, [rbx+180h]; MemoryDescriptorList
0x14004f0a5  test    rcx, rcx
0x14004f0a8  jnz     loc_14004F1D2
0x14004f0ae  mov     rcx, [rbx+1B8h]; MemoryDescriptorList
0x14004f0b5  test    rcx, rcx
0x14004f0b8  jnz     loc_14004F238
0x14004f0be  mov     rcx, [rbx+170h]; MemoryDescriptorList
0x14004f0c5  test    rcx, rcx
0x14004f0c8  jnz     loc_14004F25C
0x14004f0ce  mov     rcx, [rbx+190h]; MemoryDescriptorList
0x14004f0d5  test    rcx, rcx
0x14004f0d8  jnz     loc_14004F28F
0x14004f0de  mov     rdi, [rbx+210h]
0x14004f0e5  test    rdi, rdi
0x14004f0e8  jnz     short loc_14004F116
0x14004f0ea  mov     eax, 0FFFFFFFFh
0x14004f0ef  lock xadd [rbx+4], eax
0x14004f0f4  mov     rdi, [rsp+38h+arg_8]
0x14004f0f9  cmp     eax, 1
0x14004f0fc  jz      loc_14004F347
0x14004f102  cmp     cs:SmbCeTraceExchangeReferenceCount, 0
0x14004f109  jnz     loc_14004F354
0x14004f10f  add     rsp, 30h
0x14004f113  pop     rbx
0x14004f114  retn
0x14004f116  mov     [rsp+38h+arg_0], rsi
0x14004f11b  mov     rsi, [rbx+50h]
0x14004f11f  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004f126  lea     rax, WPP_GLOBAL_Control
0x14004f12d  cmp     rcx, rax
0x14004f130  jz      short loc_14004F13F
0x14004f132  test    dword ptr [rcx+2Ch], 400h
0x14004f139  jnz     loc_14004F2B3
0x14004f13f  mov     ecx, [rsi+148h]
0x14004f145  mov     edx, [rbx+30h]
0x14004f148  test    ecx, ecx
0x14004f14a  jnz     loc_14004F2DE
0x14004f150  mov     ecx, [rbx+28h]
0x14004f153  mov     [rdi+44h], ecx
0x14004f156  test    edx, edx
0x14004f158  jnz     loc_14004F2EE
0x14004f15e  mov     edx, ecx
0x14004f160  mov     [rdi+0Ch], edx
0x14004f163  mov     eax, [rbx+1D4h]
0x14004f169  mov     [rdi+38h], eax
0x14004f16c  mov     eax, [rbx+18Ch]
0x14004f172  mov     [rdi+3Ch], eax
0x14004f175  mov     eax, [rbx+1B4h]
0x14004f17b  mov     [rdi+40h], eax
0x14004f17e  mov     eax, [rbx+34h]
0x14004f181  mov     [rdi+48h], eax
0x14004f184  mov     eax, [rdi+8]
0x14004f187  test    al, 1
0x14004f189  jnz     loc_14004F2FF
0x14004f18f  xor     r8d, r8d; Wait
0x14004f192  lea     rcx, [rdi+18h]; Event
0x14004f196  xor     edx, edx; Increment
0x14004f198  call    cs:__imp_KeSetEvent
0x14004f19f  nop     dword ptr [rax+rax+00h]
0x14004f1a4  mov     rsi, [rsp+38h+arg_0]
0x14004f1a9  jmp     loc_14004F0EA
0x14004f1ae  call    cs:__imp_MmUnlockPages
0x14004f1b5  nop     dword ptr [rax+rax+00h]
0x14004f1ba  mov     rcx, [rbx+1A8h]; Mdl
0x14004f1c1  call    cs:__imp_IoFreeMdl
0x14004f1c8  nop     dword ptr [rax+rax+00h]
0x14004f1cd  jmp     loc_14004F09E
0x14004f1d2  call    cs:__imp_MmUnlockPages
0x14004f1d9  nop     dword ptr [rax+rax+00h]
0x14004f1de  mov     rcx, [rbx+180h]; Mdl
0x14004f1e5  call    cs:__imp_IoFreeMdl
0x14004f1ec  nop     dword ptr [rax+rax+00h]
0x14004f1f1  jmp     loc_14004F0AE
0x14004f1f6  xor     edx, edx; Tag
0x14004f1f8  call    cs:__imp_ExFreePoolWithTag
0x14004f1ff  nop     dword ptr [rax+rax+00h]
0x14004f204  mov     qword ptr [rbx+1E0h], 0
0x14004f20f  jmp     loc_14004F07E
0x14004f214  call    cs:__imp_MmUnlockPages
0x14004f21b  nop     dword ptr [rax+rax+00h]
0x14004f220  mov     rcx, [rbx+1C8h]; Mdl
0x14004f227  call    cs:__imp_IoFreeMdl
0x14004f22e  nop     dword ptr [rax+rax+00h]
0x14004f233  jmp     loc_14004F08E
0x14004f238  call    cs:__imp_MmUnlockPages
0x14004f23f  nop     dword ptr [rax+rax+00h]
0x14004f244  mov     rcx, [rbx+1B8h]; Mdl
0x14004f24b  call    cs:__imp_IoFreeMdl
0x14004f252  nop     dword ptr [rax+rax+00h]
0x14004f257  jmp     loc_14004F0BE
0x14004f25c  bt      word ptr [rbx+1FEh], 0Dh
0x14004f265  jb      loc_14004F0CE
0x14004f26b  call    cs:__imp_MmUnlockPages
0x14004f272  nop     dword ptr [rax+rax+00h]
0x14004f277  mov     rcx, [rbx+170h]; Mdl
0x14004f27e  call    cs:__imp_IoFreeMdl
0x14004f285  nop     dword ptr [rax+rax+00h]
0x14004f28a  jmp     loc_14004F0CE
0x14004f28f  call    cs:__imp_MmUnlockPages
0x14004f296  nop     dword ptr [rax+rax+00h]
0x14004f29b  mov     rcx, [rbx+190h]; Mdl
0x14004f2a2  call    cs:__imp_IoFreeMdl
0x14004f2a9  nop     dword ptr [rax+rax+00h]
0x14004f2ae  jmp     loc_14004F0DE
0x14004f2b3  mov     eax, [rbx+18Ch]
0x14004f2b9  lea     r8, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids
0x14004f2c0  mov     r9d, [rbx+1B4h]
0x14004f2c7  mov     edx, 0Ah
0x14004f2cc  mov     rcx, [rcx+18h]
0x14004f2d0  mov     [rsp+38h+var_18], eax
0x14004f2d4  call    WPP_SF_Dd
0x14004f2d9  jmp     loc_14004F13F
0x14004f2de  mov     eax, [rbx+48h]
0x14004f2e1  test    al, 40h
0x14004f2e3  jz      loc_14004F153
0x14004f2e9  jmp     loc_14004F150
0x14004f2ee  cmp     edx, 0C0000016h
0x14004f2f4  jnz     loc_14004F160
0x14004f2fa  jmp     loc_14004F15E
0x14004f2ff  call    cs:__imp_KeGetCurrentIrql
0x14004f306  nop     dword ptr [rax+rax+00h]
0x14004f30b  mov     rcx, [rdi+10h]
0x14004f30f  mov     rdx, [rdi+18h]
0x14004f313  cmp     al, 2
0x14004f315  jb      short loc_14004F33A
0x14004f317  mov     r9, rcx; pContext
0x14004f31a  mov     r8, rdx; Routine
0x14004f31d  mov     rcx, cs:__imp_MRxSmbDeviceObject
0x14004f324  xor     edx, edx; WorkQueueType
0x14004f326  mov     rcx, [rcx]; pMRxDeviceObject
0x14004f329  call    cs:__imp_RxDispatchToWorkerThread
0x14004f330  nop     dword ptr [rax+rax+00h]
0x14004f335  jmp     loc_14004F1A4
0x14004f33a  mov     rax, rdx
0x14004f33d  call    _guard_dispatch_icall
0x14004f342  jmp     loc_14004F1A4
0x14004f347  mov     rcx, rbx; pContext
0x14004f34a  call    SmbCeDiscardExchange
0x14004f34f  jmp     loc_14004F102
0x14004f354  mov     eax, [rbx+4]
0x14004f357  lea     r9, aSmbcediscardtr; "SmbCeDiscardTransactExchange"
0x14004f35e  movzx   r8d, byte ptr [rbx]
0x14004f362  lea     rcx, aDereferenceExc; "Dereference Exchange %p Type(%ld) %s %l"...
0x14004f369  mov     [rsp+38h+var_10], eax
0x14004f36d  mov     rdx, rbx
0x14004f370  mov     [rsp+38h+var_18], 18Ah
0x14004f378  call    cs:__imp_DbgPrint
0x14004f37f  nop     dword ptr [rax+rax+00h]
0x14004f384  jmp     loc_14004F10F
```
