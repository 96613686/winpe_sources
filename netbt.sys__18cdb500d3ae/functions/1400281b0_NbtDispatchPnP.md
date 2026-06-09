# NbtDispatchPnP

- ea: `0x1400281b0`
- end: `0x140028574`
- name: `NbtDispatchPnP`
- size: `964`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140006900`
- `0x14000da94`
- `0x14000dc40`
- `0x140013184`
- `0x1400148a0`
- `0x1400281b0`
- `0x14004025c`
- `0x1400439bc`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x140028399`
- `ntoskrnl!IofCallDriver` at `0x1400284c7`
- `ntoskrnl!IofCallDriver` at `0x140028399`
- `ntoskrnl!IofCallDriver` at `0x1400284c7`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14002832e`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14002832e`
- `ntoskrnl!IofCompleteRequest` at `0x14002820d`
- `ntoskrnl!IofCompleteRequest` at `0x14002820d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140028273`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400282a0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140028417`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400284d8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140028273`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400282a0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140028417`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400284d8`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400282fd`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002830f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400284b5`
- `ntoskrnl!KeReleaseSpinLock` at `0x140028529`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002853d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400282fd`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002830f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400284b5`
- `ntoskrnl!KeReleaseSpinLock` at `0x140028529`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002853d`

## pseudocode

```c
__int64 __fastcall NbtDispatchPnP(__int64 a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r14
  unsigned int v5; // ebx
  PFILE_OBJECT FileObject; // rdi
  int FsContext2; // eax
  char *FsContext; // rdi
  KSPIN_LOCK *v9; // r15
  KIRQL v10; // al
  __int64 v11; // rdi
  KIRQL v12; // r12
  int v13; // ecx
  KIRQL v14; // r13
  int v15; // edx
  int v16; // r8d
  struct _FILE_OBJECT *v17; // rbx
  struct _DEVICE_OBJECT *RelatedDeviceObject; // rcx
  struct _IO_STACK_LOCATION *v19; // rdx
  struct _IO_STACK_LOCATION *v20; // rax
  int v21; // edx
  int v22; // r8d
  KIRQL v23; // dl
  KSPIN_LOCK *v24; // rcx
  KIRQL v25; // al
  KIRQL v26; // r8
  __int64 v27; // rdi
  struct _FILE_OBJECT *v28; // rcx
  struct _DEVICE_OBJECT *v29; // r15
  struct _IO_STACK_LOCATION *v30; // rdx
  struct _IO_STACK_LOCATION *v31; // rax
  KIRQL v32; // al
  bool v33; // zf
  KIRQL v34; // bp

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  if ( !(unsigned __int8)NBT_REFERENCE_DEVICE(a1, 0, 0) )
  {
    if ( (xmmword_140038420 & 4) != 0 )
      WPP_SF_q(1026, 53, WPP_a41fab0ebd9430672f19da0e3e39181e_Traceguids, a1);
    v5 = -1073741436;
    a2->IoStatus.Status = -1073741436;
    IofCompleteRequest(a2, 2);
    return v5;
  }
  v5 = -1073741808;
  if ( CurrentStackLocation->MinorFunction != 7 || CurrentStackLocation->Parameters.Read.Length != 4 )
    goto LABEL_30;
  FileObject = CurrentStackLocation->FileObject;
  FsContext2 = (int)FileObject->FsContext2;
  if ( FsContext2 == 2 )
  {
    FsContext = (char *)FileObject->FsContext;
    if ( !FsContext || ((*((_DWORD *)FsContext + 4) - 829321027) & 0xFEFFFFFF) != 0 )
    {
      v5 = -1073741816;
      goto LABEL_30;
    }
    v9 = (KSPIN_LOCK *)(FsContext + 248);
    v10 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)FsContext + 31);
    v11 = *((_QWORD *)FsContext + 3);
    v12 = v10;
    if ( v11 && *(_DWORD *)(v11 + 16) == 1131900748 )
    {
      v14 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v11 + 104));
      if ( (BYTE9(xmmword_140038420) & 0x40) != 0 )
        WPP_SF_qddds(
          v13,
          11,
          (unsigned int)WPP_d1b5c980e8823d44a1ca8055a7722167_Traceguids,
          v11,
          *(_DWORD *)(v11 + 20),
          *(_DWORD *)(v11 + 20) + 1,
          116,
          (__int64)"minio\\netbt\\sys\\nt\\driver.c");
      _InterlockedIncrement((volatile signed __int32 *)(v11 + 20));
      KeReleaseSpinLock((PKSPIN_LOCK)(v11 + 104), v14);
      KeReleaseSpinLock(v9, v12);
      v17 = *(struct _FILE_OBJECT **)(v11 + 48);
      if ( v17 )
      {
        RelatedDeviceObject = IoGetRelatedDeviceObject(*(PFILE_OBJECT *)(v11 + 48));
        if ( RelatedDeviceObject )
        {
          v19 = a2->Tail.Overlay.CurrentStackLocation;
          *(_OWORD *)&v19[-1].MajorFunction = *(_OWORD *)&CurrentStackLocation->MajorFunction;
          *(_OWORD *)&v19[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&CurrentStackLocation->Parameters.NotifyDirectoryEx.CompletionFilter;
          *(_OWORD *)(&v19[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&CurrentStackLocation->Parameters.SetQuota + 6);
          *(_OWORD *)&v19[-1].FileObject = *(_OWORD *)&CurrentStackLocation->FileObject;
          v19[-1].Context = CurrentStackLocation->Context;
          v20 = a2->Tail.Overlay.CurrentStackLocation;
          v20[-1].CompletionRoutine = 0;
          v20[-1].Context = 0;
          v20[-1].Control = 0;
          v19[-1].FileObject = v17;
          v19[-1].DeviceObject = RelatedDeviceObject;
          v5 = IofCallDriver(RelatedDeviceObject, a2);
          NbtDereferenceLowerConnection(v11, v21, v22, 1675, (__int64)"minio\\netbt\\sys\\nt\\driver.c");
LABEL_31:
          NBT_DEREFERENCE_DEVICE(a1, 0);
          return v5;
        }
      }
      v5 = -1073741816;
      NbtDereferenceLowerConnection(v11, v15, v16, 1684, (__int64)"minio\\netbt\\sys\\nt\\driver.c");
LABEL_30:
      ReturnIrp(a2);
      goto LABEL_31;
    }
    v5 = -1073741254;
    v23 = v10;
    v24 = v9;
LABEL_29:
    KeReleaseSpinLock(v24, v23);
    goto LABEL_30;
  }
  if ( FsContext2 != 1 )
    goto LABEL_30;
  v25 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
  v26 = v25;
  if ( !*(_DWORD *)(a1 + 488)
    || (v27 = *(_QWORD *)(a1 + 616)) == 0
    || (v28 = *(struct _FILE_OBJECT **)(v27 + 48)) == 0
    || (v29 = *(struct _DEVICE_OBJECT **)(v27 + 40)) == 0 )
  {
    v23 = v25;
    v24 = &SpinLock;
    goto LABEL_29;
  }
  ++*(_DWORD *)v27;
  v30 = a2->Tail.Overlay.CurrentStackLocation;
  *(_OWORD *)&v30[-1].MajorFunction = *(_OWORD *)&CurrentStackLocation->MajorFunction;
  *(_OWORD *)&v30[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&CurrentStackLocation->Parameters.NotifyDirectoryEx.CompletionFilter;
  *(_OWORD *)(&v30[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&CurrentStackLocation->Parameters.SetQuota + 6);
  *(_OWORD *)&v30[-1].FileObject = *(_OWORD *)&CurrentStackLocation->FileObject;
  v30[-1].Context = CurrentStackLocation->Context;
  v31 = a2->Tail.Overlay.CurrentStackLocation;
  v31[-1].CompletionRoutine = 0;
  v31[-1].Context = 0;
  v31[-1].Control = 0;
  v30[-1].FileObject = v28;
  v30[-1].DeviceObject = v29;
  KeReleaseSpinLock(&SpinLock, v26);
  v5 = IofCallDriver(v29, a2);
  v32 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
  v33 = (*(_DWORD *)v27)-- == 1;
  v34 = v32;
  if ( v33 )
    NTQueueToWorkerThread(v27 + 56, (unsigned int)&DelayedNbtCloseFileHandles, 0, v27, 0, 0, 1, 1);
  NBT_DEREFERENCE_DEVICE(a1, 0);
  KeReleaseSpinLock(&SpinLock, v34);
  return v5;
}

```

## disassembly

```asm
0x1400281b0  push    rbx
0x1400281b2  push    rbp
0x1400281b3  push    rsi
0x1400281b4  push    rdi
0x1400281b5  push    r12
0x1400281b7  push    r13
0x1400281b9  push    r14
0x1400281bb  push    r15
0x1400281bd  sub     rsp, 48h
0x1400281c1  mov     r14, [rdx+0B8h]
0x1400281c8  mov     rbp, rdx
0x1400281cb  xor     edx, edx
0x1400281cd  xor     r8d, r8d
0x1400281d0  mov     rsi, rcx
0x1400281d3  call    NBT_REFERENCE_DEVICE
0x1400281d8  xor     r13d, r13d
0x1400281db  test    al, al
0x1400281dd  jnz     short loc_14002821E
0x1400281df  test    byte ptr cs:xmmword_140038420, 4
0x1400281e6  jz      short loc_140028200
0x1400281e8  lea     edx, [r13+35h]
0x1400281ec  mov     ecx, 402h
0x1400281f1  mov     r9, rsi
0x1400281f4  lea     r8, WPP_a41fab0ebd9430672f19da0e3e39181e_Traceguids
0x1400281fb  call    WPP_SF_q
0x140028200  mov     ebx, 0C0000184h
0x140028205  mov     dl, 2; PriorityBoost
0x140028207  mov     rcx, rbp; Irp
0x14002820a  mov     [rbp+30h], ebx
0x14002820d  call    cs:__imp_IofCompleteRequest
0x140028214  nop     dword ptr [rax+rax+00h]
0x140028219  jmp     loc_140028560
0x14002821e  cmp     byte ptr [r14+1], 7
0x140028223  mov     ebx, 0C0000010h
0x140028228  jnz     loc_140028549
0x14002822e  cmp     dword ptr [r14+8], 4
0x140028233  jnz     loc_140028549
0x140028239  mov     rdi, [r14+30h]
0x14002823d  mov     eax, [rdi+20h]
0x140028240  cmp     eax, 2
0x140028243  jnz     loc_140028404
0x140028249  mov     rdi, [rdi+18h]
0x14002824d  test    rdi, rdi
0x140028250  jz      loc_1400283FA
0x140028256  mov     eax, [rdi+10h]
0x140028259  sub     eax, 316E6F43h
0x14002825e  test    eax, 0FEFFFFFFh
0x140028263  jnz     loc_1400283FA
0x140028269  lea     r15, [rdi+0F8h]
0x140028270  mov     rcx, r15; SpinLock
0x140028273  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002827a  nop     dword ptr [rax+rax+00h]
0x14002827f  mov     rdi, [rdi+18h]
0x140028283  mov     r12b, al
0x140028286  test    rdi, rdi
0x140028289  jz      loc_1400283EA
0x14002828f  cmp     dword ptr [rdi+10h], 43776F4Ch
0x140028296  jnz     loc_1400283EA
0x14002829c  lea     rcx, [rdi+68h]; SpinLock
0x1400282a0  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400282a7  nop     dword ptr [rax+rax+00h]
0x1400282ac  mov     r13b, al
0x1400282af  test    byte ptr cs:xmmword_140038420+9, 40h
0x1400282b6  lea     rax, aMinioNetbtSysN_4; "minio\\netbt\\sys\\nt\\driver.c"
0x1400282bd  jz      short loc_1400282F2
0x1400282bf  mov     r9d, [rdi+14h]
0x1400282c3  mov     edx, 0Bh
0x1400282c8  mov     [rsp+88h+var_50], rax
0x1400282cd  mov     [rsp+88h+var_58], 674h
0x1400282d5  lea     r8d, [r9+1]
0x1400282d9  mov     dword ptr [rsp+88h+var_60], r8d
0x1400282de  lea     r8, WPP_d1b5c980e8823d44a1ca8055a7722167_Traceguids
0x1400282e5  mov     dword ptr [rsp+88h+var_68], r9d
0x1400282ea  mov     r9, rdi
0x1400282ed  call    WPP_SF_qddds
0x1400282f2  lock inc dword ptr [rdi+14h]
0x1400282f6  mov     dl, r13b; NewIrql
0x1400282f9  lea     rcx, [rdi+68h]; SpinLock
0x1400282fd  call    cs:__imp_KeReleaseSpinLock
0x140028304  nop     dword ptr [rax+rax+00h]
0x140028309  mov     dl, r12b; NewIrql
0x14002830c  mov     rcx, r15; SpinLock
0x14002830f  call    cs:__imp_KeReleaseSpinLock
0x140028316  nop     dword ptr [rax+rax+00h]
0x14002831b  mov     rbx, [rdi+30h]
0x14002831f  xor     r15d, r15d
0x140028322  test    rbx, rbx
0x140028325  jz      loc_1400283C6
0x14002832b  mov     rcx, rbx; FileObject
0x14002832e  call    cs:__imp_IoGetRelatedDeviceObject
0x140028335  nop     dword ptr [rax+rax+00h]
0x14002833a  mov     rcx, rax; DeviceObject
0x14002833d  test    rax, rax
0x140028340  jz      loc_1400283C6
0x140028346  mov     rdx, [rbp+0B8h]
0x14002834d  movups  xmm0, xmmword ptr [r14]
0x140028351  movups  xmmword ptr [rdx-48h], xmm0
0x140028355  movups  xmm1, xmmword ptr [r14+10h]
0x14002835a  movups  xmmword ptr [rdx-38h], xmm1
0x14002835e  movups  xmm0, xmmword ptr [r14+20h]
0x140028363  movups  xmmword ptr [rdx-28h], xmm0
0x140028367  movups  xmm1, xmmword ptr [r14+30h]
0x14002836c  movups  xmmword ptr [rdx-18h], xmm1
0x140028370  movsd   xmm0, qword ptr [r14+40h]
0x140028376  movsd   qword ptr [rdx-8], xmm0
0x14002837b  mov     rax, [rbp+0B8h]
0x140028382  mov     [rax-10h], r15
0x140028386  mov     [rax-8], r15
0x14002838a  mov     [rax-45h], r15b
0x14002838e  mov     [rdx-18h], rbx
0x140028392  mov     [rdx-20h], rcx
0x140028396  mov     rdx, rbp; Irp
0x140028399  call    cs:__imp_IofCallDriver
0x1400283a0  nop     dword ptr [rax+rax+00h]
0x1400283a5  mov     r9d, 68Bh
0x1400283ab  mov     rcx, rdi
0x1400283ae  mov     ebx, eax
0x1400283b0  lea     rax, aMinioNetbtSysN_4; "minio\\netbt\\sys\\nt\\driver.c"
0x1400283b7  mov     [rsp+88h+var_68], rax
0x1400283bc  call    NbtDereferenceLowerConnection
0x1400283c1  jmp     loc_140028553
0x1400283c6  lea     rax, aMinioNetbtSysN_4; "minio\\netbt\\sys\\nt\\driver.c"
0x1400283cd  mov     r9d, 694h
0x1400283d3  mov     rcx, rdi
0x1400283d6  mov     [rsp+88h+var_68], rax
0x1400283db  mov     ebx, 0C0000008h
0x1400283e0  call    NbtDereferenceLowerConnection
0x1400283e5  jmp     loc_140028549
0x1400283ea  mov     ebx, 0C000023Ah
0x1400283ef  mov     dl, r12b
0x1400283f2  mov     rcx, r15
0x1400283f5  jmp     loc_14002853D
0x1400283fa  mov     ebx, 0C0000008h
0x1400283ff  jmp     loc_140028549
0x140028404  cmp     eax, 1
0x140028407  jnz     loc_140028549
0x14002840d  lea     r12, SpinLock
0x140028414  mov     rcx, r12; SpinLock
0x140028417  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002841e  nop     dword ptr [rax+rax+00h]
0x140028423  mov     r8b, al
0x140028426  cmp     [rsi+1E8h], r13d
0x14002842d  jz      loc_140028537
0x140028433  mov     rdi, [rsi+268h]
0x14002843a  test    rdi, rdi
0x14002843d  jz      loc_140028537
0x140028443  mov     rcx, [rdi+30h]
0x140028447  test    rcx, rcx
0x14002844a  jz      loc_140028537
0x140028450  mov     r15, [rdi+28h]
0x140028454  test    r15, r15
0x140028457  jz      loc_140028537
0x14002845d  inc     dword ptr [rdi]
0x14002845f  mov     rdx, [rbp+0B8h]
0x140028466  movups  xmm0, xmmword ptr [r14]
0x14002846a  movups  xmmword ptr [rdx-48h], xmm0
0x14002846e  movups  xmm1, xmmword ptr [r14+10h]
0x140028473  movups  xmmword ptr [rdx-38h], xmm1
0x140028477  movups  xmm0, xmmword ptr [r14+20h]
0x14002847c  movups  xmmword ptr [rdx-28h], xmm0
0x140028480  movups  xmm1, xmmword ptr [r14+30h]
0x140028485  movups  xmmword ptr [rdx-18h], xmm1
0x140028489  movsd   xmm0, qword ptr [r14+40h]
0x14002848f  movsd   qword ptr [rdx-8], xmm0
0x140028494  mov     rax, [rbp+0B8h]
0x14002849b  mov     [rax-10h], r13
0x14002849f  mov     [rax-8], r13
0x1400284a3  mov     [rax-45h], r13b
0x1400284a7  mov     [rdx-18h], rcx
0x1400284ab  mov     rcx, r12; SpinLock
0x1400284ae  mov     [rdx-20h], r15
0x1400284b2  mov     dl, r8b; NewIrql
0x1400284b5  call    cs:__imp_KeReleaseSpinLock
0x1400284bc  nop     dword ptr [rax+rax+00h]
0x1400284c1  mov     rdx, rbp; Irp
0x1400284c4  mov     rcx, r15; DeviceObject
0x1400284c7  call    cs:__imp_IofCallDriver
0x1400284ce  nop     dword ptr [rax+rax+00h]
0x1400284d3  mov     rcx, r12; SpinLock
0x1400284d6  mov     ebx, eax
0x1400284d8  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400284df  nop     dword ptr [rax+rax+00h]
0x1400284e4  add     dword ptr [rdi], 0FFFFFFFFh
0x1400284e7  mov     bpl, al
0x1400284ea  jnz     short loc_140028516
0x1400284ec  mov     byte ptr [rsp+88h+var_50], 1
0x1400284f1  lea     rcx, [rdi+38h]
0x1400284f5  mov     byte ptr [rsp+88h+var_58], 1
0x1400284fa  lea     rdx, DelayedNbtCloseFileHandles
0x140028501  mov     [rsp+88h+var_60], r13
0x140028506  mov     r9, rdi
0x140028509  xor     r8d, r8d
0x14002850c  mov     [rsp+88h+var_68], r13
0x140028511  call    NTQueueToWorkerThread
0x140028516  mov     r8b, 1
0x140028519  xor     edx, edx
0x14002851b  mov     rcx, rsi
0x14002851e  call    NBT_DEREFERENCE_DEVICE
0x140028523  mov     dl, bpl; NewIrql
0x140028526  mov     rcx, r12; SpinLock
0x140028529  call    cs:__imp_KeReleaseSpinLock
0x140028530  nop     dword ptr [rax+rax+00h]
0x140028535  jmp     short loc_140028560
0x140028537  mov     dl, r8b; NewIrql
0x14002853a  mov     rcx, r12; SpinLock
0x14002853d  call    cs:__imp_KeReleaseSpinLock
0x140028544  nop     dword ptr [rax+rax+00h]
0x140028549  mov     edx, ebx
0x14002854b  mov     rcx, rbp; Irp
0x14002854e  call    ReturnIrp
0x140028553  xor     r8d, r8d
0x140028556  xor     edx, edx
0x140028558  mov     rcx, rsi
0x14002855b  call    NBT_DEREFERENCE_DEVICE
0x140028560  mov     eax, ebx
0x140028562  add     rsp, 48h
0x140028566  pop     r15
0x140028568  pop     r14
0x14002856a  pop     r13
0x14002856c  pop     r12
0x14002856e  pop     rdi
0x14002856f  pop     rsi
0x140028570  pop     rbp
0x140028571  pop     rbx
0x140028572  retn
```
