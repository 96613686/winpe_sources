# FveIceSimProcessIceIrp

- ea: `0x1400ea498`
- end: `0x1400ea76d`
- name: `FveIceSimProcessIceIrp`
- size: `725`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400eac70`

## callees

- `0x1400b9f84`
- `0x1400d23d0`
- `0x1400ea498`
- `0x1400ea774`
- `0x1400ea9d8`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x1400ea6c9`
- `ntoskrnl!IofCallDriver` at `0x1400ea6c9`
- `ntoskrnl!IofCompleteRequest` at `0x1400ea727`
- `ntoskrnl!IofCompleteRequest` at `0x1400ea727`
- `ntoskrnl!IoGetAdapterCryptoEngineExtension` at `0x1400ea58b`
- `ntoskrnl!IoGetAdapterCryptoEngineExtension` at `0x1400ea58b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400ea649`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400ea649`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400ea60a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400ea60a`
- `ntoskrnl!KeBugCheckEx` at `0x1400ea56c`
- `ntoskrnl!KeBugCheckEx` at `0x1400ea5b1`
- `ntoskrnl!KeBugCheckEx` at `0x1400ea760`
- `ntoskrnl!KeBugCheckEx` at `0x1400ea56c`
- `ntoskrnl!KeBugCheckEx` at `0x1400ea5b1`
- `ntoskrnl!KeBugCheckEx` at `0x1400ea760`

## pseudocode

```c
char __fastcall FveIceSimProcessIceIrp(__int64 a1, IRP *a2)
{
  ULONG_PTR BugCheckParameter4; // rdi
  ULONG_PTR Blink; // rbp
  ULONG_PTR v6; // rdx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  PIO_SECURITY_CONTEXT SecurityContext; // rcx
  unsigned __int64 v9; // r12
  unsigned int SecurityQos; // r15d
  char v11; // r13
  int AdapterCryptoEngineExtension; // eax
  char v13; // r14
  __int64 v14; // rax
  KIRQL v15; // al
  __int64 v16; // rcx
  int v17; // edi
  _QWORD *v19; // [rsp+88h] [rbp+10h] BYREF

  BugCheckParameter4 = (int)a2->Tail.Overlay.DeviceQueueEntry.SortKey;
  Blink = (ULONG_PTR)a2->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Blink;
  v19 = 0;
  if ( (unsigned int)(BugCheckParameter4 - 3) <= 1 )
  {
    v6 = Blink;
    if ( Blink )
    {
      SecurityContext = *(PIO_SECURITY_CONTEXT *)(Blink + 16);
      CurrentStackLocation = 0;
      v9 = *(_QWORD *)(Blink + 8);
      SecurityQos = *(_DWORD *)(Blink + 124);
      goto LABEL_11;
    }
  }
  else
  {
    v6 = 0;
  }
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  if ( !CurrentStackLocation )
    goto LABEL_39;
  SecurityContext = CurrentStackLocation->Parameters.Create.SecurityContext;
  if ( !SecurityContext
    || CurrentStackLocation->Parameters.QueryDirectory.FileName
    || CurrentStackLocation->Parameters.Read.ByteOffset.QuadPart
    || CurrentStackLocation->Parameters.CreatePipe.Parameters )
  {
    goto LABEL_39;
  }
  v9 = *(_QWORD *)&SecurityContext[2].DesiredAccess;
  SecurityQos = (unsigned int)SecurityContext[3].SecurityQos;
LABEL_11:
  if ( !*(_QWORD *)(a1 + 4736) || !v6 && (unsigned __int8)(CurrentStackLocation->MajorFunction - 3) > 1u )
    goto LABEL_39;
  if ( (unsigned int)(BugCheckParameter4 - 1) > 3 )
    KeBugCheckEx(0x120u, 0xCu, 0, 0, BugCheckParameter4);
  v11 = BYTE2(SecurityContext[11].AccessState);
  AdapterCryptoEngineExtension = IoGetAdapterCryptoEngineExtension(a2, &v19);
  if ( AdapterCryptoEngineExtension < 0 )
    KeBugCheckEx(0x120u, 0xCu, 0, 0, AdapterCryptoEngineExtension);
  v13 = 1;
  v14 = v19[1];
  if ( v14 )
  {
    if ( *(_QWORD *)(a1 + 4736) != v14 || *v19 != v9 / *(unsigned int *)(a1 + 1308) )
      goto LABEL_39;
    if ( v11 )
    {
      v15 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(*(_QWORD *)(a1 + 4752) + 32LL));
      v16 = *(_QWORD *)(a1 + 4752);
      if ( *(_QWORD *)(v16 + 104) )
      {
        v13 = 0;
      }
      else
      {
        *(_QWORD *)(v16 + 104) = a2;
        *(_QWORD *)(*(_QWORD *)(a1 + 4752) + 112LL) = a2->MdlAddress;
      }
      KeReleaseSpinLock((PKSPIN_LOCK)(*(_QWORD *)(a1 + 4752) + 32LL), v15);
      if ( !v13 )
        return v13;
      FveIceSimProcessIceWriteIrp(a1, a2, v9, SecurityQos);
    }
    else if ( a2->IoStatus.Status >= 0 )
    {
      FveIceSimProcessIceReadIrp(a1, a2, v9, SecurityQos);
    }
  }
  *(_OWORD *)(&a2->Tail.CompletionKey + 1) = 0;
  if ( v11 )
  {
    if ( (unsigned int)(BugCheckParameter4 - 1) <= 2 )
    {
      ++*(_QWORD *)(*(_QWORD *)(a1 + 4752) + 128LL);
      *(_QWORD *)(*(_QWORD *)(a1 + 4752) + 144LL) += SecurityQos;
      IofCallDriver(*(PDEVICE_OBJECT *)(a1 + 112), a2);
      return v13;
    }
LABEL_39:
    KeBugCheckEx(0x120u, 0xCu, 0, 0, 0);
  }
  if ( (_DWORD)BugCheckParameter4 != 1 && (_DWORD)BugCheckParameter4 != 4 )
    goto LABEL_39;
  ++*(_QWORD *)(*(_QWORD *)(a1 + 4752) + 120LL);
  *(_QWORD *)(*(_QWORD *)(a1 + 4752) + 136LL) += SecurityQos;
  v17 = BugCheckParameter4 - 1;
  if ( v17 )
  {
    if ( v17 == 3 )
      FveReadCompletionRoutine(Blink);
  }
  else
  {
    FveIceIrpCompletionRoutine(a1, a2, Blink);
    IofCompleteRequest(a2, 0);
  }
  return v13;
}

```

## disassembly

```asm
0x1400ea498  mov     rax, rsp
0x1400ea49b  push    rbx
0x1400ea49c  push    rbp
0x1400ea49d  push    rsi
0x1400ea49e  push    rdi
0x1400ea49f  push    r12
0x1400ea4a1  push    r13
0x1400ea4a3  push    r14
0x1400ea4a5  push    r15
0x1400ea4a7  sub     rsp, 38h
0x1400ea4ab  movsxd  rdi, dword ptr [rdx+88h]
0x1400ea4b2  mov     rbx, rdx
0x1400ea4b5  mov     rbp, [rdx+80h]
0x1400ea4bc  mov     rsi, rcx
0x1400ea4bf  mov     qword ptr [rax+10h], 0
0x1400ea4c7  lea     eax, [rdi-3]
0x1400ea4ca  cmp     eax, 1
0x1400ea4cd  jbe     short loc_1400EA4D3
0x1400ea4cf  xor     edx, edx
0x1400ea4d1  jmp     short loc_1400EA4DB
0x1400ea4d3  mov     rdx, rbp
0x1400ea4d6  test    rbp, rbp
0x1400ea4d9  jnz     short loc_1400EA523
0x1400ea4db  mov     rax, [rbx+0B8h]
0x1400ea4e2  test    rax, rax
0x1400ea4e5  jz      loc_1400EA748
0x1400ea4eb  mov     rcx, [rax+8]
0x1400ea4ef  test    rcx, rcx
0x1400ea4f2  jz      loc_1400EA748
0x1400ea4f8  cmp     qword ptr [rax+10h], 0
0x1400ea4fd  jnz     loc_1400EA748
0x1400ea503  cmp     qword ptr [rax+18h], 0
0x1400ea508  jnz     loc_1400EA748
0x1400ea50e  cmp     qword ptr [rax+20h], 0
0x1400ea513  jnz     loc_1400EA748
0x1400ea519  mov     r12, [rcx+40h]
0x1400ea51d  mov     r15d, [rcx+48h]
0x1400ea521  jmp     short loc_1400EA531
0x1400ea523  mov     rcx, [rbp+10h]
0x1400ea527  xor     eax, eax
0x1400ea529  mov     r12, [rbp+8]
0x1400ea52d  mov     r15d, [rbp+7Ch]
0x1400ea531  cmp     qword ptr [rsi+1280h], 0
0x1400ea539  jz      loc_1400EA748
0x1400ea53f  test    rdx, rdx
0x1400ea542  jnz     short loc_1400EA550
0x1400ea544  mov     al, [rax]
0x1400ea546  sub     al, 3
0x1400ea548  cmp     al, 1
0x1400ea54a  ja      loc_1400EA748
0x1400ea550  lea     eax, [rdi-1]
0x1400ea553  cmp     eax, 3
0x1400ea556  jbe     short loc_1400EA579
0x1400ea558  xor     r9d, r9d; BugCheckParameter3
0x1400ea55b  mov     [rsp+78h+BugCheckParameter4], rdi; BugCheckParameter4
0x1400ea560  xor     r8d, r8d; BugCheckParameter2
0x1400ea563  mov     ecx, 120h; BugCheckCode
0x1400ea568  lea     edx, [r9+0Ch]; BugCheckParameter1
0x1400ea56c  call    cs:__imp_KeBugCheckEx
0x1400ea579  mov     r13b, [rcx+112h]
0x1400ea580  lea     rdx, [rsp+78h+arg_8]
0x1400ea588  mov     rcx, rbx
0x1400ea58b  call    cs:__imp_IoGetAdapterCryptoEngineExtension
0x1400ea592  nop     dword ptr [rax+rax+00h]
0x1400ea597  test    eax, eax
0x1400ea599  jns     short loc_1400EA5BE
0x1400ea59b  xor     r9d, r9d; BugCheckParameter3
0x1400ea59e  cdqe
0x1400ea5a0  xor     r8d, r8d; BugCheckParameter2
0x1400ea5a3  mov     [rsp+78h+BugCheckParameter4], rax; BugCheckParameter4
0x1400ea5a8  mov     ecx, 120h; BugCheckCode
0x1400ea5ad  lea     edx, [r9+0Ch]; BugCheckParameter1
0x1400ea5b1  call    cs:__imp_KeBugCheckEx
0x1400ea5be  mov     r8, [rsp+78h+arg_8]
0x1400ea5c6  mov     r14b, 1
0x1400ea5c9  mov     rax, [r8+8]
0x1400ea5cd  test    rax, rax
0x1400ea5d0  jz      loc_1400EA688
0x1400ea5d6  cmp     [rsi+1280h], rax
0x1400ea5dd  jnz     loc_1400EA748
0x1400ea5e3  mov     ecx, [rsi+51Ch]
0x1400ea5e9  xor     edx, edx
0x1400ea5eb  mov     rax, r12
0x1400ea5ee  div     rcx
0x1400ea5f1  cmp     [r8], rax
0x1400ea5f4  jnz     loc_1400EA748
0x1400ea5fa  test    r13b, r13b
0x1400ea5fd  jz      short loc_1400EA671
0x1400ea5ff  mov     rcx, [rsi+1290h]
0x1400ea606  add     rcx, 20h ; ' '; SpinLock
0x1400ea60a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400ea611  nop     dword ptr [rax+rax+00h]
0x1400ea616  mov     rcx, [rsi+1290h]
0x1400ea61d  mov     dl, al; NewIrql
0x1400ea61f  cmp     qword ptr [rcx+68h], 0
0x1400ea624  jz      short loc_1400EA62B
0x1400ea626  xor     r14b, r14b
0x1400ea629  jmp     short loc_1400EA63E
0x1400ea62b  mov     [rcx+68h], rbx
0x1400ea62f  mov     rcx, [rsi+1290h]
0x1400ea636  mov     rax, [rbx+8]
0x1400ea63a  mov     [rcx+70h], rax
0x1400ea63e  mov     rcx, [rsi+1290h]
0x1400ea645  add     rcx, 20h ; ' '; SpinLock
0x1400ea649  call    cs:__imp_KeReleaseSpinLock
0x1400ea650  nop     dword ptr [rax+rax+00h]
0x1400ea655  test    r14b, r14b
0x1400ea658  jz      loc_1400EA733
0x1400ea65e  mov     r9d, r15d
0x1400ea661  mov     r8, r12
0x1400ea664  mov     rdx, rbx
0x1400ea667  mov     rcx, rsi
0x1400ea66a  call    FveIceSimProcessIceWriteIrp
0x1400ea66f  jmp     short loc_1400EA688
0x1400ea671  cmp     dword ptr [rbx+30h], 0
0x1400ea675  jl      short loc_1400EA688
0x1400ea677  mov     r9d, r15d
0x1400ea67a  mov     r8, r12
0x1400ea67d  mov     rdx, rbx
0x1400ea680  mov     rcx, rsi
0x1400ea683  call    FveIceSimProcessIceReadIrp
0x1400ea688  xorps   xmm0, xmm0
0x1400ea68b  movups  xmmword ptr [rbx+80h], xmm0
0x1400ea692  test    r13b, r13b
0x1400ea695  jz      short loc_1400EA6D7
0x1400ea697  lea     eax, [rdi-1]
0x1400ea69a  cmp     eax, 2
0x1400ea69d  ja      loc_1400EA748
0x1400ea6a3  mov     rax, [rsi+1290h]
0x1400ea6aa  mov     rdx, rbx; Irp
0x1400ea6ad  inc     qword ptr [rax+80h]
0x1400ea6b4  mov     rcx, [rsi+1290h]
0x1400ea6bb  mov     eax, r15d
0x1400ea6be  add     [rcx+90h], rax
0x1400ea6c5  mov     rcx, [rsi+70h]; DeviceObject
0x1400ea6c9  call    cs:__imp_IofCallDriver
0x1400ea6d0  nop     dword ptr [rax+rax+00h]
0x1400ea6d5  jmp     short loc_1400EA733
0x1400ea6d7  cmp     edi, 1
0x1400ea6da  jz      short loc_1400EA6E1
0x1400ea6dc  cmp     edi, 4
0x1400ea6df  jnz     short loc_1400EA748
0x1400ea6e1  mov     rax, [rsi+1290h]
0x1400ea6e8  inc     qword ptr [rax+78h]
0x1400ea6ec  mov     rdx, [rsi+1290h]
0x1400ea6f3  mov     eax, r15d
0x1400ea6f6  add     [rdx+88h], rax
0x1400ea6fd  sub     edi, 1
0x1400ea700  jz      short loc_1400EA714
0x1400ea702  cmp     edi, 3
0x1400ea705  jnz     short loc_1400EA733
0x1400ea707  mov     rdx, rbx
0x1400ea70a  mov     rcx, rbp; BugCheckParameter4
0x1400ea70d  call    FveReadCompletionRoutine
0x1400ea712  jmp     short loc_1400EA733
0x1400ea714  mov     r8, rbp
0x1400ea717  mov     rdx, rbx
0x1400ea71a  mov     rcx, rsi
0x1400ea71d  call    FveIceIrpCompletionRoutine
0x1400ea722  xor     edx, edx; PriorityBoost
0x1400ea724  mov     rcx, rbx; Irp
0x1400ea727  call    cs:__imp_IofCompleteRequest
0x1400ea72e  nop     dword ptr [rax+rax+00h]
0x1400ea733  mov     al, r14b
0x1400ea736  add     rsp, 38h
0x1400ea73a  pop     r15
0x1400ea73c  pop     r14
0x1400ea73e  pop     r13
0x1400ea740  pop     r12
0x1400ea742  pop     rdi
0x1400ea743  pop     rsi
0x1400ea744  pop     rbp
0x1400ea745  pop     rbx
0x1400ea746  retn
0x1400ea748  xor     r9d, r9d; BugCheckParameter3
0x1400ea74b  mov     [rsp+78h+BugCheckParameter4], 0; BugCheckParameter4
0x1400ea754  xor     r8d, r8d; BugCheckParameter2
0x1400ea757  mov     ecx, 120h; BugCheckCode
0x1400ea75c  lea     edx, [r9+0Ch]; BugCheckParameter1
0x1400ea760  call    cs:__imp_KeBugCheckEx
```
