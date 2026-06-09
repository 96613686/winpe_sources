# CdCreateKernelConnection

- ea: `0x1400083b0`
- end: `0x140008789`
- name: `CdCreateKernelConnection`
- size: `985`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x1400083b0`
- `0x140008790`
- `0x140008984`
- `0x140008a54`
- `0x14000b020`
- `0x14000b820`
- `0x14000bc10`
- `0x14000c690`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400085a0`
- `ntoskrnl!ExAllocatePool2` at `0x1400085a0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008706`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008706`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000844b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400085f3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140008690`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000844b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400085f3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140008690`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000856e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140008646`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400086f0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000856e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140008646`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400086f0`
- `ntoskrnl!IofCompleteRequest` at `0x1400084a9`
- `ntoskrnl!IofCompleteRequest` at `0x140008753`
- `ntoskrnl!IofCompleteRequest` at `0x1400084a9`
- `ntoskrnl!IofCompleteRequest` at `0x140008753`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000846b`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000860b`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400086a5`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000846b`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000860b`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400086a5`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140008562`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000863a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400086e4`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140008562`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000863a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400086e4`

## pseudocode

```c
__int64 __fastcall CdCreateKernelConnection(PIRP Irp)
{
  __int64 v1; // r15
  struct _LIST_ENTRY *v2; // rbx
  unsigned int v4; // r14d
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r13
  struct _LIST_ENTRY **v6; // r12
  __int64 EaBufferItem; // rax
  int ProcessServerFromConnection; // esi
  char *v9; // rsi
  struct _IO_STACK_LOCATION *v10; // rax
  struct _LIST_ENTRY *v11; // r13
  struct _LIST_ENTRY *Blink; // rcx
  struct _LIST_ENTRY **Pool2; // rax
  int v14; // eax
  char v15; // r13
  struct _IO_STACK_LOCATION *v17; // [rsp+20h] [rbp-48h]
  char v18; // [rsp+70h] [rbp+8h]
  PVOID P; // [rsp+80h] [rbp+18h] BYREF
  __int64 v20; // [rsp+88h] [rbp+20h] BYREF

  v1 = 0;
  v2 = 0;
  v20 = 0;
  P = 0;
  if ( Irp->RequestorMode )
  {
    v4 = -1073741790;
LABEL_39:
    Irp->IoStatus.Status = v4;
    Irp->IoStatus.Information = 0;
    IofCompleteRequest(Irp, 0);
    return v4;
  }
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  LOBYTE(v6) = 0;
  v18 = 0;
  v17 = CurrentStackLocation;
  EaBufferItem = CdpFindEaBufferItem(Irp->AssociatedIrp.MasterIrp, "attach");
  v4 = 259;
  if ( EaBufferItem && *(_WORD *)(EaBufferItem + 6) == 8 )
  {
    ProcessServerFromConnection = CdpGetProcessServerFromConnection(
                                    &P,
                                    (__int64)Irp,
                                    *(void **)(*(unsigned __int8 *)(EaBufferItem + 5) + EaBufferItem + 9));
    if ( ProcessServerFromConnection < 0 )
    {
      v2 = (struct _LIST_ENTRY *)P;
      goto LABEL_35;
    }
    v6 = 0;
    KeEnterCriticalRegion();
    v2 = (struct _LIST_ENTRY *)P;
    v9 = (char *)P + 216;
    ExAcquirePushLockExclusiveEx((char *)P + 216, 0);
    if ( v2[14].Flink )
    {
      ProcessServerFromConnection = 0;
      ++v2[16].Flink;
      CurrentStackLocation->FileObject->FsContext = v2[14].Flink;
      Irp->IoStatus.Status = 0;
      Irp->IoStatus.Information = 0;
      IofCompleteRequest(Irp, 0);
      goto LABEL_30;
    }
    v10 = --Irp->Tail.Overlay.CurrentStackLocation;
    --Irp->CurrentLocation;
    v10->Parameters.WMI.ProviderId = (ULONG_PTR)v2;
    _InterlockedExchange64((volatile __int64 *)&Irp->CancelRoutine, (__int64)CdpCancelKernelConnectionQueuedIrp);
    if ( Irp->Cancel && _InterlockedExchange64((volatile __int64 *)&Irp->CancelRoutine, 0) )
    {
      ProcessServerFromConnection = -1073741536;
      ++Irp->CurrentLocation;
      ++Irp->Tail.Overlay.CurrentStackLocation;
      goto LABEL_30;
    }
    if ( ++v2[16].Flink == (struct _LIST_ENTRY *)1 )
    {
      v2[16].Flink = (struct _LIST_ENTRY *)2;
      LOBYTE(v6) = 1;
      v18 = 1;
    }
    v11 = v2 + 15;
    Blink = v2[15].Blink;
    if ( Blink->Flink != &v2[15] )
      __fastfail(3u);
    Irp->Tail.Overlay.ListEntry.Blink = Blink;
    Irp->Tail.Overlay.ListEntry.Flink = v11;
    Blink->Flink = &Irp->Tail.Overlay.ListEntry;
    v2[15].Blink = &Irp->Tail.Overlay.ListEntry;
    ExReleasePushLockExclusiveEx(v9, 0);
    KeLeaveCriticalRegion();
    Irp->Tail.Overlay.CurrentStackLocation->Control |= 1u;
    if ( !(_BYTE)v6 )
    {
      ProcessServerFromConnection = 259;
      goto LABEL_35;
    }
    Pool2 = (struct _LIST_ENTRY **)ExAllocatePool2(64, 16, 1665360963);
    v6 = Pool2;
    if ( !Pool2 )
    {
      ProcessServerFromConnection = -1073741670;
LABEL_27:
      KeEnterCriticalRegion();
      ExAcquirePushLockExclusiveEx(&v2[13].Blink, 0);
LABEL_28:
      --v2[16].Flink;
      if ( ProcessServerFromConnection < 0 )
      {
        v2[14].Blink = 0;
        CdpCompleteServerKernelConnectionQueue(v2, (unsigned int)ProcessServerFromConnection);
      }
LABEL_30:
      ExReleasePushLockExclusiveEx(&v2[13].Blink, 0);
      KeLeaveCriticalRegion();
      if ( !v6 )
      {
LABEL_32:
        LOBYTE(v6) = v18;
        goto LABEL_33;
      }
LABEL_31:
      ExFreePoolWithTag(v6, 0);
      goto LABEL_32;
    }
    LOBYTE(P) = 0;
    *Pool2 = v2;
    v14 = CdpAllocateKernelConnectionIrp(Irp, v17, Pool2, &v20);
    v1 = v20;
    ProcessServerFromConnection = v14;
    if ( v14 < 0 )
    {
      v15 = (char)P;
    }
    else
    {
      KeEnterCriticalRegion();
      ExAcquirePushLockExclusiveEx(&v2[13].Blink, 0);
      if ( v11->Flink == v11 )
      {
        --v2[16].Flink;
        ProcessServerFromConnection = -1073741536;
        goto LABEL_30;
      }
      v2[14].Blink = (struct _LIST_ENTRY *)v1;
      ExReleasePushLockExclusiveEx(&v2[13].Blink, 0);
      KeLeaveCriticalRegion();
      v15 = 0;
      ProcessServerFromConnection = CdpCreateServerConnectionIo(v1, (__int64)v2, v6 + 1);
      if ( ProcessServerFromConnection >= 0 )
      {
        v1 = 0;
        v20 = 0;
        v6 = 0;
        goto LABEL_27;
      }
    }
    if ( ProcessServerFromConnection == -1073741536 )
      goto LABEL_31;
    if ( v15 )
      goto LABEL_28;
    goto LABEL_27;
  }
  ProcessServerFromConnection = -1073741811;
LABEL_33:
  if ( v1 )
    CdpFreeKernelConnectionIrp(&v20);
LABEL_35:
  if ( v2 )
    CdDereferenceServer(v2);
  if ( !(_BYTE)v6 )
  {
    v4 = ProcessServerFromConnection;
    if ( ProcessServerFromConnection < 0 )
      goto LABEL_39;
  }
  return v4;
}

```

## disassembly

```asm
0x1400083b0  mov     rax, rsp
0x1400083b3  mov     [rax+10h], rbx
0x1400083b7  push    rbp
0x1400083b8  push    rsi
0x1400083b9  push    rdi
0x1400083ba  push    r12
0x1400083bc  push    r13
0x1400083be  push    r14
0x1400083c0  push    r15
0x1400083c2  sub     rsp, 30h
0x1400083c6  xor     r15d, r15d
0x1400083c9  xor     ebx, ebx
0x1400083cb  mov     rdi, rcx
0x1400083ce  mov     [rax+20h], r15
0x1400083d2  mov     [rax+18h], rbx
0x1400083d6  cmp     [rcx+40h], bl
0x1400083d9  jz      short loc_1400083E6
0x1400083db  mov     r14d, 0C0000022h
0x1400083e1  jmp     loc_140008742
0x1400083e6  mov     r13, [rcx+0B8h]
0x1400083ed  lea     rdx, aAttach; "attach"
0x1400083f4  mov     rcx, [rcx+18h]
0x1400083f8  xor     r12b, r12b
0x1400083fb  mov     [rsp+68h+arg_0], r12b
0x140008400  mov     [rsp+68h+var_48], r13
0x140008405  call    CdpFindEaBufferItem
0x14000840a  mov     r14d, 103h
0x140008410  test    rax, rax
0x140008413  jz      loc_140008782
0x140008419  cmp     word ptr [rax+6], 8
0x14000841e  jnz     loc_140008782
0x140008424  movzx   r8d, byte ptr [rax+5]
0x140008429  lea     rcx, [rsp+68h+P]
0x140008431  mov     rdx, rdi
0x140008434  mov     r8, [r8+rax+9]
0x140008439  call    CdpGetProcessServerFromConnection
0x14000843e  mov     esi, eax
0x140008440  test    eax, eax
0x140008442  js      loc_140008778
0x140008448  xor     r12d, r12d
0x14000844b  call    cs:__imp_KeEnterCriticalRegion
0x140008452  nop     dword ptr [rax+rax+00h]
0x140008457  mov     rbx, [rsp+68h+P]
0x14000845f  xor     edx, edx
0x140008461  lea     rsi, [rbx+0D8h]
0x140008468  mov     rcx, rsi
0x14000846b  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140008472  nop     dword ptr [rax+rax+00h]
0x140008477  cmp     [rbx+0E0h], r12
0x14000847e  jz      short loc_1400084BA
0x140008480  xor     esi, esi
0x140008482  lea     ebp, [r12+1]
0x140008487  add     [rbx+100h], rbp
0x14000848e  xor     edx, edx; PriorityBoost
0x140008490  mov     rcx, [r13+30h]
0x140008494  mov     rax, [rbx+0E0h]
0x14000849b  mov     [rcx+18h], rax
0x14000849f  mov     rcx, rdi; Irp
0x1400084a2  mov     [rdi+30h], esi
0x1400084a5  mov     [rdi+38h], rsi
0x1400084a9  call    cs:__imp_IofCompleteRequest
0x1400084b0  nop     dword ptr [rax+rax+00h]
0x1400084b5  jmp     loc_1400086DB
0x1400084ba  add     qword ptr [rdi+0B8h], 0FFFFFFFFFFFFFFB8h
0x1400084c2  mov     rax, [rdi+0B8h]
0x1400084c9  dec     byte ptr [rdi+43h]
0x1400084cc  mov     [rax+8], rbx
0x1400084d0  lea     rax, CdpCancelKernelConnectionQueuedIrp
0x1400084d7  xchg    rax, [rdi+68h]
0x1400084db  cmp     [rdi+44h], r12b
0x1400084df  jz      short loc_140008507
0x1400084e1  xor     eax, eax
0x1400084e3  xchg    rax, [rdi+68h]
0x1400084e7  test    rax, rax
0x1400084ea  jz      short loc_140008507
0x1400084ec  mov     ebp, 1
0x1400084f1  mov     esi, 0C0000120h
0x1400084f6  add     [rdi+43h], bpl
0x1400084fa  add     qword ptr [rdi+0B8h], 48h ; 'H'
0x140008502  jmp     loc_1400086DB
0x140008507  mov     ebp, 1
0x14000850c  add     [rbx+100h], rbp
0x140008513  cmp     [rbx+100h], rbp
0x14000851a  jnz     short loc_140008531
0x14000851c  mov     qword ptr [rbx+100h], 2
0x140008527  mov     r12b, bpl
0x14000852a  mov     [rsp+68h+arg_0], bpl
0x14000852f  jmp     short $+2
0x140008531  lea     r13, [rbx+0F0h]
0x140008538  mov     rcx, [r13+8]
0x14000853c  cmp     [rcx], r13
0x14000853f  jz      short loc_140008548
0x140008541  mov     ecx, 3
0x140008546  int     29h; Win8: RtlFailFast(ecx)
0x140008548  lea     rax, [rdi+0A8h]
0x14000854f  xor     edx, edx
0x140008551  mov     [rax+8], rcx
0x140008555  mov     [rax], r13
0x140008558  mov     [rcx], rax
0x14000855b  mov     rcx, rsi
0x14000855e  mov     [r13+8], rax
0x140008562  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140008569  nop     dword ptr [rax+rax+00h]
0x14000856e  call    cs:__imp_KeLeaveCriticalRegion
0x140008575  nop     dword ptr [rax+rax+00h]
0x14000857a  mov     rax, [rdi+0B8h]
0x140008581  or      [rax+3], bpl
0x140008585  test    r12b, r12b
0x140008588  jnz     short loc_140008592
0x14000858a  mov     esi, r14d
0x14000858d  jmp     loc_140008729
0x140008592  mov     edx, 10h
0x140008597  mov     r8d, 63436443h
0x14000859d  lea     ecx, [rdx+30h]
0x1400085a0  call    cs:__imp_ExAllocatePool2
0x1400085a7  nop     dword ptr [rax+rax+00h]
0x1400085ac  mov     r12, rax
0x1400085af  test    rax, rax
0x1400085b2  jnz     short loc_1400085BE
0x1400085b4  mov     esi, 0C000009Ah
0x1400085b9  jmp     loc_140008690
0x1400085be  mov     rdx, [rsp+68h+var_48]
0x1400085c3  lea     r9, [rsp+68h+arg_18]
0x1400085cb  mov     r8, r12
0x1400085ce  mov     byte ptr [rsp+68h+P], r15b
0x1400085d6  mov     rcx, rdi
0x1400085d9  mov     [rax], rbx
0x1400085dc  call    CdpAllocateKernelConnectionIrp
0x1400085e1  mov     r15, [rsp+68h+arg_18]
0x1400085e9  mov     esi, eax
0x1400085eb  test    eax, eax
0x1400085ed  js      loc_14000867B
0x1400085f3  call    cs:__imp_KeEnterCriticalRegion
0x1400085fa  nop     dword ptr [rax+rax+00h]
0x1400085ff  lea     rsi, [rbx+0D8h]
0x140008606  xor     edx, edx
0x140008608  mov     rcx, rsi
0x14000860b  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140008612  nop     dword ptr [rax+rax+00h]
0x140008617  cmp     [r13+0], r13
0x14000861b  jnz     short loc_14000862E
0x14000861d  dec     qword ptr [rbx+100h]
0x140008624  mov     esi, 0C0000120h
0x140008629  jmp     loc_1400086DB
0x14000862e  xor     edx, edx
0x140008630  mov     [rbx+0E8h], r15
0x140008637  mov     rcx, rsi
0x14000863a  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140008641  nop     dword ptr [rax+rax+00h]
0x140008646  call    cs:__imp_KeLeaveCriticalRegion
0x14000864d  nop     dword ptr [rax+rax+00h]
0x140008652  lea     r8, [r12+8]
0x140008657  mov     rdx, rbx
0x14000865a  mov     rcx, r15
0x14000865d  xor     r13b, r13b
0x140008660  call    CdpCreateServerConnectionIo
0x140008665  mov     esi, eax
0x140008667  test    eax, eax
0x140008669  js      short loc_140008683
0x14000866b  xor     r15d, r15d
0x14000866e  mov     [rsp+68h+arg_18], r15
0x140008676  xor     r12d, r12d
0x140008679  jmp     short loc_140008690
0x14000867b  mov     r13b, byte ptr [rsp+68h+P]
0x140008683  cmp     esi, 0C0000120h
0x140008689  jz      short loc_140008701
0x14000868b  test    r13b, r13b
0x14000868e  jnz     short loc_1400086B3
0x140008690  call    cs:__imp_KeEnterCriticalRegion
0x140008697  nop     dword ptr [rax+rax+00h]
0x14000869c  lea     rcx, [rbx+0D8h]
0x1400086a3  xor     edx, edx
0x1400086a5  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400086ac  nop     dword ptr [rax+rax+00h]
0x1400086b1  jmp     short loc_1400086B6
0x1400086b3  mov     bpl, r13b
0x1400086b6  dec     qword ptr [rbx+100h]
0x1400086bd  test    esi, esi
0x1400086bf  jns     short loc_1400086D6
0x1400086c1  mov     edx, esi
0x1400086c3  mov     qword ptr [rbx+0E8h], 0
0x1400086ce  mov     rcx, rbx
0x1400086d1  call    CdpCompleteServerKernelConnectionQueue
0x1400086d6  test    bpl, bpl
0x1400086d9  jz      short loc_1400086FC
0x1400086db  lea     rcx, [rbx+0D8h]
0x1400086e2  xor     edx, edx
0x1400086e4  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400086eb  nop     dword ptr [rax+rax+00h]
0x1400086f0  call    cs:__imp_KeLeaveCriticalRegion
0x1400086f7  nop     dword ptr [rax+rax+00h]
0x1400086fc  test    r12, r12
0x1400086ff  jz      short loc_140008712
0x140008701  xor     edx, edx; Tag
0x140008703  mov     rcx, r12; P
0x140008706  call    cs:__imp_ExFreePoolWithTag
0x14000870d  nop     dword ptr [rax+rax+00h]
0x140008712  mov     r12b, [rsp+68h+arg_0]
0x140008717  test    r15, r15
0x14000871a  jz      short loc_140008729
0x14000871c  lea     rcx, [rsp+68h+arg_18]
0x140008724  call    CdpFreeKernelConnectionIrp
0x140008729  test    rbx, rbx
0x14000872c  jz      short loc_140008736
0x14000872e  mov     rcx, rbx; P
0x140008731  call    CdDereferenceServer
0x140008736  test    r12b, r12b
0x140008739  jnz     short loc_14000875F
0x14000873b  mov     r14d, esi
0x14000873e  test    esi, esi
0x140008740  jns     short loc_14000875F
0x140008742  xor     edx, edx; PriorityBoost
0x140008744  mov     [rdi+30h], r14d
0x140008748  mov     rcx, rdi; Irp
0x14000874b  mov     qword ptr [rdi+38h], 0
0x140008753  call    cs:__imp_IofCompleteRequest
0x14000875a  nop     dword ptr [rax+rax+00h]
0x14000875f  mov     rbx, [rsp+68h+arg_8]
0x140008764  mov     eax, r14d
0x140008767  add     rsp, 30h
0x14000876b  pop     r15
0x14000876d  pop     r14
0x14000876f  pop     r13
0x140008771  pop     r12
0x140008773  pop     rdi
0x140008774  pop     rsi
0x140008775  pop     rbp
0x140008776  retn
0x140008778  mov     rbx, [rsp+68h+P]
0x140008780  jmp     short loc_140008729
0x140008782  mov     esi, 0C000000Dh
0x140008787  jmp     short loc_140008717
```
