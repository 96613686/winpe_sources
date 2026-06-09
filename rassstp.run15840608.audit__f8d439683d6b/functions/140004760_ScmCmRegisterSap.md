# ScmCmRegisterSap

- ea: `0x140004760`
- end: `0x140004a16`
- name: `ScmCmRegisterSap`
- size: `694`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140002bd8`
- `0x140004760`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400047ba`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400047ba`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400048f8`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004966`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400049cd`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400048f8`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004966`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400049cd`
- `ntoskrnl!IoCsqRemoveNextIrp` at `0x1400048a6`
- `ntoskrnl!IoCsqRemoveNextIrp` at `0x1400048a6`
- `NDIS!NdisQueueIoWorkItem` at `0x14000497f`
- `NDIS!NdisQueueIoWorkItem` at `0x14000497f`
- `NDIS!NdisAllocateIoWorkItem` at `0x140004853`
- `NDIS!NdisAllocateIoWorkItem` at `0x140004853`
- `NDIS!NdisFreeIoWorkItem` at `0x140004907`
- `NDIS!NdisFreeIoWorkItem` at `0x140004907`

## pseudocode

```c
__int64 __fastcall ScmCmRegisterSap(__int64 a1, _DWORD *a2, __int64 a3)
{
  KIRQL v5; // di
  unsigned int v6; // ebx
  int v7; // ecx
  NDIS_HANDLE IoWorkItem; // rbp
  PIRP v9; // rax
  PIRP v10; // rsi

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->Timer) & 0x82) == 0x82 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_f061e284a7f133f0e4904ed0310bea13_Traceguids);
  v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)SstpGlobals + 55);
  if ( *((_DWORD *)SstpGlobals + 112) == 3 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_f061e284a7f133f0e4904ed0310bea13_Traceguids);
    }
    v6 = -1073676255;
LABEL_32:
    KeReleaseSpinLock((PKSPIN_LOCK)SstpGlobals + 55, v5);
    goto LABEL_33;
  }
  if ( *a2 != 0x8000 || a2[1] < 0xCu )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_f061e284a7f133f0e4904ed0310bea13_Traceguids);
    }
    v6 = -1073676267;
    goto LABEL_32;
  }
  *((_DWORD *)SstpGlobals + 116) = a2[2];
  v7 = a2[3];
  if ( v7 == -1 )
    v7 = 0;
  *((_DWORD *)SstpGlobals + 117) = v7;
  IoWorkItem = NdisAllocateIoWorkItem(*((NDIS_HANDLE *)SstpGlobals + 21));
  if ( !IoWorkItem )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_f061e284a7f133f0e4904ed0310bea13_Traceguids);
    }
    v6 = -1073741670;
    goto LABEL_32;
  }
  v9 = IoCsqRemoveNextIrp((PIO_CSQ)SstpGlobals + 1, 0);
  v10 = v9;
  if ( v9 )
  {
    v6 = 259;
    *((_DWORD *)SstpGlobals + 112) = 1;
    *(_DWORD *)v9->AssociatedIrp.MasterIrp = 0;
    v9->IoStatus.Status = 0;
    v9->IoStatus.Information = 8208;
    *((_QWORD *)SstpGlobals + 57) = a3;
    KeReleaseSpinLock((PKSPIN_LOCK)SstpGlobals + 55, v5);
    NdisQueueIoWorkItem(IoWorkItem, (NDIS_IO_WORKITEM_ROUTINE)ScmCmCompleteIrpPassive, v10);
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_f061e284a7f133f0e4904ed0310bea13_Traceguids);
    }
    v6 = -1073741670;
    KeReleaseSpinLock((PKSPIN_LOCK)SstpGlobals + 55, v5);
    NdisFreeIoWorkItem(IoWorkItem);
  }
LABEL_33:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->Timer) & 0x82) == 0x82 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_f061e284a7f133f0e4904ed0310bea13_Traceguids);
  return v6;
}

```

## disassembly

```asm
0x140004760  push    rbx
0x140004762  push    rbp
0x140004763  push    rsi
0x140004764  push    rdi
0x140004765  push    r12
0x140004767  push    r14
0x140004769  push    r15
0x14000476b  sub     rsp, 20h
0x14000476f  mov     r14, r8
0x140004772  mov     rbx, rdx
0x140004775  mov     rcx, cs:WPP_GLOBAL_Control
0x14000477c  lea     r15, WPP_GLOBAL_Control
0x140004783  lea     r12, WPP_f061e284a7f133f0e4904ed0310bea13_Traceguids
0x14000478a  cmp     rcx, r15
0x14000478d  jz      short loc_1400047AC
0x14000478f  mov     eax, [rcx+2Ch]
0x140004792  and     eax, 82h
0x140004797  cmp     al, 82h
0x140004799  jnz     short loc_1400047AC
0x14000479b  mov     rcx, [rcx+18h]
0x14000479f  mov     edx, 17h
0x1400047a4  mov     r8, r12
0x1400047a7  call    WPP_SF_
0x1400047ac  mov     rcx, cs:SstpGlobals
0x1400047b3  add     rcx, 1B8h; SpinLock
0x1400047ba  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400047c1  nop     dword ptr [rax+rax+00h]
0x1400047c6  mov     rcx, cs:SstpGlobals
0x1400047cd  mov     dil, al
0x1400047d0  cmp     dword ptr [rcx+1C0h], 3
0x1400047d7  jnz     short loc_14000480E
0x1400047d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400047e0  cmp     rcx, r15
0x1400047e3  jz      short loc_140004804
0x1400047e5  mov     edx, [rcx+2Ch]
0x1400047e8  test    dl, 1
0x1400047eb  jz      short loc_140004804
0x1400047ed  cmp     byte ptr [rcx+29h], 1
0x1400047f1  jb      short loc_140004804
0x1400047f3  mov     rcx, [rcx+18h]
0x1400047f7  mov     edx, 18h
0x1400047fc  mov     r8, r12
0x1400047ff  call    WPP_SF_
0x140004804  mov     ebx, 0C0010021h
0x140004809  jmp     loc_1400049BC
0x14000480e  cmp     dword ptr [rbx], 8000h
0x140004814  jnz     loc_14000498D
0x14000481a  cmp     dword ptr [rbx+4], 0Ch
0x14000481e  jb      loc_14000498D
0x140004824  mov     eax, [rbx+8]
0x140004827  mov     [rcx+1D0h], eax
0x14000482d  xor     eax, eax
0x14000482f  mov     ecx, [rbx+0Ch]
0x140004832  cmp     ecx, 0FFFFFFFFh
0x140004835  cmovz   ecx, eax
0x140004838  mov     rax, cs:SstpGlobals
0x14000483f  mov     [rax+1D4h], ecx
0x140004845  mov     rcx, cs:SstpGlobals
0x14000484c  mov     rcx, [rcx+0A8h]; NdisObjectHandle
0x140004853  call    cs:__imp_NdisAllocateIoWorkItem
0x14000485a  nop     dword ptr [rax+rax+00h]
0x14000485f  mov     rbp, rax
0x140004862  test    rax, rax
0x140004865  jnz     short loc_140004899
0x140004867  mov     rcx, cs:WPP_GLOBAL_Control
0x14000486e  cmp     rcx, r15
0x140004871  jz      short loc_14000488F
0x140004873  mov     eax, [rcx+2Ch]
0x140004876  test    al, 1
0x140004878  jz      short loc_14000488F
0x14000487a  cmp     byte ptr [rcx+29h], 1
0x14000487e  jb      short loc_14000488F
0x140004880  mov     rcx, [rcx+18h]
0x140004884  lea     edx, [rbp+1Ah]
0x140004887  mov     r8, r12
0x14000488a  call    WPP_SF_
0x14000488f  mov     ebx, 0C000009Ah
0x140004894  jmp     loc_1400049BC
0x140004899  mov     rcx, cs:SstpGlobals
0x1400048a0  xor     edx, edx; PeekContext
0x1400048a2  add     rcx, 40h ; '@'; Csq
0x1400048a6  call    cs:__imp_IoCsqRemoveNextIrp
0x1400048ad  nop     dword ptr [rax+rax+00h]
0x1400048b2  mov     rsi, rax
0x1400048b5  test    rax, rax
0x1400048b8  jnz     short loc_140004918
0x1400048ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1400048c1  cmp     rcx, r15
0x1400048c4  jz      short loc_1400048E2
0x1400048c6  mov     eax, [rcx+2Ch]
0x1400048c9  test    al, 2
0x1400048cb  jz      short loc_1400048E2
0x1400048cd  cmp     byte ptr [rcx+29h], 1
0x1400048d1  jb      short loc_1400048E2
0x1400048d3  mov     rcx, [rcx+18h]
0x1400048d7  lea     edx, [rsi+1Bh]
0x1400048da  mov     r8, r12
0x1400048dd  call    WPP_SF_
0x1400048e2  mov     rcx, cs:SstpGlobals
0x1400048e9  mov     dl, dil; NewIrql
0x1400048ec  add     rcx, 1B8h; SpinLock
0x1400048f3  mov     ebx, 0C000009Ah
0x1400048f8  call    cs:__imp_KeReleaseSpinLock
0x1400048ff  nop     dword ptr [rax+rax+00h]
0x140004904  mov     rcx, rbp; NdisIoWorkItemHandle
0x140004907  call    cs:__imp_NdisFreeIoWorkItem
0x14000490e  nop     dword ptr [rax+rax+00h]
0x140004913  jmp     loc_1400049D9
0x140004918  mov     rax, cs:SstpGlobals
0x14000491f  mov     dl, dil; NewIrql
0x140004922  mov     ebx, 103h
0x140004927  mov     dword ptr [rax+1C0h], 1
0x140004931  mov     rax, [rsi+18h]
0x140004935  mov     dword ptr [rax], 0
0x14000493b  mov     dword ptr [rsi+30h], 0
0x140004942  mov     qword ptr [rsi+38h], 2010h
0x14000494a  mov     rax, cs:SstpGlobals
0x140004951  mov     [rax+1C8h], r14
0x140004958  mov     rcx, cs:SstpGlobals
0x14000495f  add     rcx, 1B8h; SpinLock
0x140004966  call    cs:__imp_KeReleaseSpinLock
0x14000496d  nop     dword ptr [rax+rax+00h]
0x140004972  mov     r8, rsi; WorkItemContext
0x140004975  lea     rdx, ScmCmCompleteIrpPassive; Routine
0x14000497c  mov     rcx, rbp; NdisIoWorkItemHandle
0x14000497f  call    cs:__imp_NdisQueueIoWorkItem
0x140004986  nop     dword ptr [rax+rax+00h]
0x14000498b  jmp     short loc_1400049D9
0x14000498d  mov     rcx, cs:WPP_GLOBAL_Control
0x140004994  cmp     rcx, r15
0x140004997  jz      short loc_1400049B7
0x140004999  mov     eax, [rcx+2Ch]
0x14000499c  test    al, 1
0x14000499e  jz      short loc_1400049B7
0x1400049a0  cmp     byte ptr [rcx+29h], 1
0x1400049a4  jb      short loc_1400049B7
0x1400049a6  mov     rcx, [rcx+18h]
0x1400049aa  mov     edx, 19h
0x1400049af  mov     r8, r12
0x1400049b2  call    WPP_SF_
0x1400049b7  mov     ebx, 0C0010015h
0x1400049bc  mov     rcx, cs:SstpGlobals
0x1400049c3  mov     dl, dil; NewIrql
0x1400049c6  add     rcx, 1B8h; SpinLock
0x1400049cd  call    cs:__imp_KeReleaseSpinLock
0x1400049d4  nop     dword ptr [rax+rax+00h]
0x1400049d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400049e0  cmp     rcx, r15
0x1400049e3  jz      short loc_140004A04
0x1400049e5  mov     edx, [rcx+2Ch]
0x1400049e8  and     edx, 82h
0x1400049ee  cmp     dl, 82h
0x1400049f1  jnz     short loc_140004A04
0x1400049f3  mov     rcx, [rcx+18h]
0x1400049f7  mov     edx, 1Ch
0x1400049fc  mov     r8, r12
0x1400049ff  call    WPP_SF_
0x140004a04  mov     eax, ebx
0x140004a06  add     rsp, 20h
0x140004a0a  pop     r15
0x140004a0c  pop     r14
0x140004a0e  pop     r12
0x140004a10  pop     rdi
0x140004a11  pop     rsi
0x140004a12  pop     rbp
0x140004a13  pop     rbx
0x140004a14  retn
```
