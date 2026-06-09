# FveIceSimProcessIceIrp

- ea: `0x1400ef498`
- end: `0x1400ef76d`
- name: `FveIceSimProcessIceIrp`
- size: `725`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400efc70`

## callees

- `0x1400bd6a4`
- `0x1400dda80`
- `0x1400ef498`
- `0x1400ef774`
- `0x1400ef9d8`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x1400ef6c9`
- `ntoskrnl!IofCallDriver` at `0x1400ef6c9`
- `ntoskrnl!IofCompleteRequest` at `0x1400ef727`
- `ntoskrnl!IofCompleteRequest` at `0x1400ef727`
- `ntoskrnl!IoGetAdapterCryptoEngineExtension` at `0x1400ef58b`
- `ntoskrnl!IoGetAdapterCryptoEngineExtension` at `0x1400ef58b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400ef649`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400ef649`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400ef60a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400ef60a`
- `ntoskrnl!KeBugCheckEx` at `0x1400ef56c`
- `ntoskrnl!KeBugCheckEx` at `0x1400ef5b1`
- `ntoskrnl!KeBugCheckEx` at `0x1400ef760`
- `ntoskrnl!KeBugCheckEx` at `0x1400ef56c`
- `ntoskrnl!KeBugCheckEx` at `0x1400ef5b1`
- `ntoskrnl!KeBugCheckEx` at `0x1400ef760`

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
  if ( !*(_QWORD *)(a1 + 4752) || !v6 && (unsigned __int8)(CurrentStackLocation->MajorFunction - 3) > 1u )
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
    if ( *(_QWORD *)(a1 + 4752) != v14 || *v19 != v9 / *(unsigned int *)(a1 + 1308) )
      goto LABEL_39;
    if ( v11 )
    {
      v15 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(*(_QWORD *)(a1 + 4768) + 32LL));
      v16 = *(_QWORD *)(a1 + 4768);
      if ( *(_QWORD *)(v16 + 104) )
      {
        v13 = 0;
      }
      else
      {
        *(_QWORD *)(v16 + 104) = a2;
        *(_QWORD *)(*(_QWORD *)(a1 + 4768) + 112LL) = a2->MdlAddress;
      }
      KeReleaseSpinLock((PKSPIN_LOCK)(*(_QWORD *)(a1 + 4768) + 32LL), v15);
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
      ++*(_QWORD *)(*(_QWORD *)(a1 + 4768) + 128LL);
      *(_QWORD *)(*(_QWORD *)(a1 + 4768) + 144LL) += SecurityQos;
      IofCallDriver(*(PDEVICE_OBJECT *)(a1 + 112), a2);
      return v13;
    }
LABEL_39:
    KeBugCheckEx(0x120u, 0xCu, 0, 0, 0);
  }
  if ( (_DWORD)BugCheckParameter4 != 1 && (_DWORD)BugCheckParameter4 != 4 )
    goto LABEL_39;
  ++*(_QWORD *)(*(_QWORD *)(a1 + 4768) + 120LL);
  *(_QWORD *)(*(_QWORD *)(a1 + 4768) + 136LL) += SecurityQos;
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
0x1400ef498  mov     rax, rsp
0x1400ef49b  push    rbx
0x1400ef49c  push    rbp
0x1400ef49d  push    rsi
0x1400ef49e  push    rdi
0x1400ef49f  push    r12
0x1400ef4a1  push    r13
0x1400ef4a3  push    r14
0x1400ef4a5  push    r15
0x1400ef4a7  sub     rsp, 38h
0x1400ef4ab  movsxd  rdi, dword ptr [rdx+88h]
0x1400ef4b2  mov     rbx, rdx
0x1400ef4b5  mov     rbp, [rdx+80h]
0x1400ef4bc  mov     rsi, rcx
0x1400ef4bf  mov     qword ptr [rax+10h], 0
0x1400ef4c7  lea     eax, [rdi-3]
0x1400ef4ca  cmp     eax, 1
0x1400ef4cd  jbe     short loc_1400EF4D3
0x1400ef4cf  xor     edx, edx
0x1400ef4d1  jmp     short loc_1400EF4DB
0x1400ef4d3  mov     rdx, rbp
0x1400ef4d6  test    rbp, rbp
0x1400ef4d9  jnz     short loc_1400EF523
0x1400ef4db  mov     rax, [rbx+0B8h]
0x1400ef4e2  test    rax, rax
0x1400ef4e5  jz      loc_1400EF748
0x1400ef4eb  mov     rcx, [rax+8]
0x1400ef4ef  test    rcx, rcx
0x1400ef4f2  jz      loc_1400EF748
0x1400ef4f8  cmp     qword ptr [rax+10h], 0
0x1400ef4fd  jnz     loc_1400EF748
0x1400ef503  cmp     qword ptr [rax+18h], 0
0x1400ef508  jnz     loc_1400EF748
0x1400ef50e  cmp     qword ptr [rax+20h], 0
0x1400ef513  jnz     loc_1400EF748
0x1400ef519  mov     r12, [rcx+40h]
0x1400ef51d  mov     r15d, [rcx+48h]
0x1400ef521  jmp     short loc_1400EF531
0x1400ef523  mov     rcx, [rbp+10h]
0x1400ef527  xor     eax, eax
0x1400ef529  mov     r12, [rbp+8]
0x1400ef52d  mov     r15d, [rbp+7Ch]
0x1400ef531  cmp     qword ptr [rsi+1290h], 0
0x1400ef539  jz      loc_1400EF748
0x1400ef53f  test    rdx, rdx
0x1400ef542  jnz     short loc_1400EF550
0x1400ef544  mov     al, [rax]
0x1400ef546  sub     al, 3
0x1400ef548  cmp     al, 1
0x1400ef54a  ja      loc_1400EF748
0x1400ef550  lea     eax, [rdi-1]
0x1400ef553  cmp     eax, 3
0x1400ef556  jbe     short loc_1400EF579
0x1400ef558  xor     r9d, r9d; BugCheckParameter3
0x1400ef55b  mov     [rsp+78h+BugCheckParameter4], rdi; BugCheckParameter4
0x1400ef560  xor     r8d, r8d; BugCheckParameter2
0x1400ef563  mov     ecx, 120h; BugCheckCode
0x1400ef568  lea     edx, [r9+0Ch]; BugCheckParameter1
0x1400ef56c  call    cs:__imp_KeBugCheckEx
0x1400ef579  mov     r13b, [rcx+112h]
0x1400ef580  lea     rdx, [rsp+78h+arg_8]
0x1400ef588  mov     rcx, rbx
0x1400ef58b  call    cs:__imp_IoGetAdapterCryptoEngineExtension
0x1400ef592  nop     dword ptr [rax+rax+00h]
0x1400ef597  test    eax, eax
0x1400ef599  jns     short loc_1400EF5BE
0x1400ef59b  xor     r9d, r9d; BugCheckParameter3
0x1400ef59e  cdqe
0x1400ef5a0  xor     r8d, r8d; BugCheckParameter2
0x1400ef5a3  mov     [rsp+78h+BugCheckParameter4], rax; BugCheckParameter4
0x1400ef5a8  mov     ecx, 120h; BugCheckCode
0x1400ef5ad  lea     edx, [r9+0Ch]; BugCheckParameter1
0x1400ef5b1  call    cs:__imp_KeBugCheckEx
0x1400ef5be  mov     r8, [rsp+78h+arg_8]
0x1400ef5c6  mov     r14b, 1
0x1400ef5c9  mov     rax, [r8+8]
0x1400ef5cd  test    rax, rax
0x1400ef5d0  jz      loc_1400EF688
0x1400ef5d6  cmp     [rsi+1290h], rax
0x1400ef5dd  jnz     loc_1400EF748
0x1400ef5e3  mov     ecx, [rsi+51Ch]
0x1400ef5e9  xor     edx, edx
0x1400ef5eb  mov     rax, r12
0x1400ef5ee  div     rcx
0x1400ef5f1  cmp     [r8], rax
0x1400ef5f4  jnz     loc_1400EF748
0x1400ef5fa  test    r13b, r13b
0x1400ef5fd  jz      short loc_1400EF671
0x1400ef5ff  mov     rcx, [rsi+12A0h]
0x1400ef606  add     rcx, 20h ; ' '; SpinLock
0x1400ef60a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400ef611  nop     dword ptr [rax+rax+00h]
0x1400ef616  mov     rcx, [rsi+12A0h]
0x1400ef61d  mov     dl, al; NewIrql
0x1400ef61f  cmp     qword ptr [rcx+68h], 0
0x1400ef624  jz      short loc_1400EF62B
0x1400ef626  xor     r14b, r14b
0x1400ef629  jmp     short loc_1400EF63E
0x1400ef62b  mov     [rcx+68h], rbx
0x1400ef62f  mov     rcx, [rsi+12A0h]
0x1400ef636  mov     rax, [rbx+8]
0x1400ef63a  mov     [rcx+70h], rax
0x1400ef63e  mov     rcx, [rsi+12A0h]
0x1400ef645  add     rcx, 20h ; ' '; SpinLock
0x1400ef649  call    cs:__imp_KeReleaseSpinLock
0x1400ef650  nop     dword ptr [rax+rax+00h]
0x1400ef655  test    r14b, r14b
0x1400ef658  jz      loc_1400EF733
0x1400ef65e  mov     r9d, r15d
0x1400ef661  mov     r8, r12
0x1400ef664  mov     rdx, rbx
0x1400ef667  mov     rcx, rsi
0x1400ef66a  call    FveIceSimProcessIceWriteIrp
0x1400ef66f  jmp     short loc_1400EF688
0x1400ef671  cmp     dword ptr [rbx+30h], 0
0x1400ef675  jl      short loc_1400EF688
0x1400ef677  mov     r9d, r15d
0x1400ef67a  mov     r8, r12
0x1400ef67d  mov     rdx, rbx
0x1400ef680  mov     rcx, rsi
0x1400ef683  call    FveIceSimProcessIceReadIrp
0x1400ef688  xorps   xmm0, xmm0
0x1400ef68b  movups  xmmword ptr [rbx+80h], xmm0
0x1400ef692  test    r13b, r13b
0x1400ef695  jz      short loc_1400EF6D7
0x1400ef697  lea     eax, [rdi-1]
0x1400ef69a  cmp     eax, 2
0x1400ef69d  ja      loc_1400EF748
0x1400ef6a3  mov     rax, [rsi+12A0h]
0x1400ef6aa  mov     rdx, rbx; Irp
0x1400ef6ad  inc     qword ptr [rax+80h]
0x1400ef6b4  mov     rcx, [rsi+12A0h]
0x1400ef6bb  mov     eax, r15d
0x1400ef6be  add     [rcx+90h], rax
0x1400ef6c5  mov     rcx, [rsi+70h]; DeviceObject
0x1400ef6c9  call    cs:__imp_IofCallDriver
0x1400ef6d0  nop     dword ptr [rax+rax+00h]
0x1400ef6d5  jmp     short loc_1400EF733
0x1400ef6d7  cmp     edi, 1
0x1400ef6da  jz      short loc_1400EF6E1
0x1400ef6dc  cmp     edi, 4
0x1400ef6df  jnz     short loc_1400EF748
0x1400ef6e1  mov     rax, [rsi+12A0h]
0x1400ef6e8  inc     qword ptr [rax+78h]
0x1400ef6ec  mov     rdx, [rsi+12A0h]
0x1400ef6f3  mov     eax, r15d
0x1400ef6f6  add     [rdx+88h], rax
0x1400ef6fd  sub     edi, 1
0x1400ef700  jz      short loc_1400EF714
0x1400ef702  cmp     edi, 3
0x1400ef705  jnz     short loc_1400EF733
0x1400ef707  mov     rdx, rbx
0x1400ef70a  mov     rcx, rbp; BugCheckParameter2
0x1400ef70d  call    FveReadCompletionRoutine
0x1400ef712  jmp     short loc_1400EF733
0x1400ef714  mov     r8, rbp
0x1400ef717  mov     rdx, rbx
0x1400ef71a  mov     rcx, rsi
0x1400ef71d  call    FveIceIrpCompletionRoutine
0x1400ef722  xor     edx, edx; PriorityBoost
0x1400ef724  mov     rcx, rbx; Irp
0x1400ef727  call    cs:__imp_IofCompleteRequest
0x1400ef72e  nop     dword ptr [rax+rax+00h]
0x1400ef733  mov     al, r14b
0x1400ef736  add     rsp, 38h
0x1400ef73a  pop     r15
0x1400ef73c  pop     r14
0x1400ef73e  pop     r13
0x1400ef740  pop     r12
0x1400ef742  pop     rdi
0x1400ef743  pop     rsi
0x1400ef744  pop     rbp
0x1400ef745  pop     rbx
0x1400ef746  retn
0x1400ef748  xor     r9d, r9d; BugCheckParameter3
0x1400ef74b  mov     [rsp+78h+BugCheckParameter4], 0; BugCheckParameter4
0x1400ef754  xor     r8d, r8d; BugCheckParameter2
0x1400ef757  mov     ecx, 120h; BugCheckCode
0x1400ef75c  lea     edx, [r9+0Ch]; BugCheckParameter1
0x1400ef760  call    cs:__imp_KeBugCheckEx
```
