# ClasspReleaseQueue

- ea: `0x1400176f8`
- end: `0x14001791a`
- name: `ClasspReleaseQueue`
- size: `546`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter2, PIRP Irp)`
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140013530`
- `0x140016350`
- `0x1400176e0`
- `0x14001ccb0`
- `0x140022920`
- `0x140037e10`

## callees

- `0x1400176f8`
- `0x14001fbf4`
- `0x14001ff30`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x140017831`
- `ntoskrnl!IofCallDriver` at `0x140017831`
- `ntoskrnl!KeBugCheckEx` at `0x14001790d`
- `ntoskrnl!KeBugCheckEx` at `0x14001790d`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140017801`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140017801`
- `ntoskrnl!KeLowerIrql` at `0x140017840`
- `ntoskrnl!KeLowerIrql` at `0x140017840`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140017730`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140017730`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400177a6`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140017878`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400177a6`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140017878`
- `ntoskrnl!KfRaiseIrql` at `0x140017717`
- `ntoskrnl!KfRaiseIrql` at `0x140017717`

## pseudocode

```c
void __fastcall ClasspReleaseQueue(ULONG_PTR BugCheckParameter2, PIRP Irp)
{
  __int64 v2; // rbx
  struct _DEVICE_OBJECT *v5; // r12
  KIRQL v6; // r15
  __int64 v7; // rsi
  unsigned __int64 v8; // rsi
  _IO_STACK_LOCATION *CurrentStackLocation; // rax
  int v10; // ecx
  __int64 v11; // rbx
  _IO_STACK_LOCATION *v12; // rax

  v2 = *(_QWORD *)(BugCheckParameter2 + 64);
  v5 = *(struct _DEVICE_OBJECT **)(v2 + 16);
  v6 = KfRaiseIrql(2u);
  KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(v2 + 712));
  if ( !*(_BYTE *)(*(_QWORD *)(v2 + 1144) + 1506LL) )
    ClasspAllocateReleaseQueueIrp(v2);
  v7 = *(_QWORD *)(v2 + 1144);
  if ( !*(_BYTE *)(v7 + 1506) )
    KeBugCheckEx(0x2Du, 0x12u, BugCheckParameter2, 0, 0);
  if ( !*(_BYTE *)(v2 + 817) || Irp )
  {
    *(_BYTE *)(v2 + 817) = 1;
    if ( !Irp )
      Irp = *(PIRP *)(v7 + 1512);
    v8 = v7 + 1128;
    if ( *(_BYTE *)(*(_QWORD *)(v2 + 528) + 30LL) != 1 )
      v8 = v2 + 728;
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v2 + 712));
    CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
    CurrentStackLocation[-1].MajorFunction = 15;
    if ( *(_BYTE *)(v8 + 2) == 40 )
      *(_QWORD *)(v8 + 80) = Irp;
    else
      *(_QWORD *)(v8 + 48) = Irp;
    CurrentStackLocation[-1].Parameters.WMI.ProviderId = v8;
    v10 = (*(_DWORD *)(BugCheckParameter2 + 52) & 1) != 0 ? 21 : 4;
    if ( *(_BYTE *)(*(_QWORD *)(v2 + 528) + 30LL) == 1 )
      *(_DWORD *)(v8 + 20) = v10;
    else
      *(_BYTE *)(v8 + 2) = v10;
    v11 = *(_QWORD *)(BugCheckParameter2 + 64);
    if ( !ExAcquireRundownProtectionCacheAware((PEX_RUNDOWN_REF_CACHE_AWARE)(*(_QWORD *)(v11 + 440) + 8LL)) )
    {
      _InterlockedIncrement(*(volatile signed __int32 **)(v11 + 440));
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          14,
          WPP_a22cc05f221e30b8049471910da99059_Traceguids,
          **(unsigned int **)(v11 + 440));
      }
    }
    v12 = Irp->Tail.Overlay.CurrentStackLocation;
    v12[-1].CompletionRoutine = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *, void *))&ClassReleaseQueueCompletion;
    v12[-1].Context = (void *)BugCheckParameter2;
    v12[-1].Control = -32;
    IofCallDriver(v5, Irp);
  }
  else
  {
    *(_BYTE *)(v2 + 816) = 1;
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v2 + 712));
  }
  KeLowerIrql(v6);
}

```

## disassembly

```asm
0x1400176f8  push    rbx
0x1400176fa  push    rbp
0x1400176fb  push    rsi
0x1400176fc  push    rdi
0x1400176fd  push    r12
0x1400176ff  push    r14
0x140017701  push    r15
0x140017703  sub     rsp, 30h
0x140017707  mov     rbx, [rcx+40h]
0x14001770b  mov     rbp, rcx
0x14001770e  mov     cl, 2; NewIrql
0x140017710  mov     rdi, rdx
0x140017713  mov     r12, [rbx+10h]
0x140017717  call    cs:__imp_KfRaiseIrql
0x14001771e  nop     dword ptr [rax+rax+00h]
0x140017723  lea     r14, [rbx+2C8h]
0x14001772a  mov     r15b, al
0x14001772d  mov     rcx, r14; SpinLock
0x140017730  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140017737  nop     dword ptr [rax+rax+00h]
0x14001773c  mov     rdx, [rbx+478h]
0x140017743  cmp     byte ptr [rdx+5E2h], 0
0x14001774a  jz      loc_1400178EA
0x140017750  mov     rsi, [rbx+478h]
0x140017757  cmp     byte ptr [rsi+5E2h], 0
0x14001775e  jz      loc_1400178F7
0x140017764  cmp     byte ptr [rbx+331h], 0
0x14001776b  jnz     loc_140017865
0x140017771  mov     byte ptr [rbx+331h], 1
0x140017778  test    rdi, rdi
0x14001777b  jnz     short loc_140017784
0x14001777d  mov     rdi, [rsi+5E8h]
0x140017784  mov     rax, [rbx+210h]
0x14001778b  add     rsi, 468h
0x140017792  mov     cl, [rax+1Eh]
0x140017795  lea     rax, [rbx+2D8h]
0x14001779c  cmp     cl, 1
0x14001779f  mov     rcx, r14; SpinLock
0x1400177a2  cmovnz  rsi, rax
0x1400177a6  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x1400177ad  nop     dword ptr [rax+rax+00h]
0x1400177b2  mov     rax, [rdi+0B8h]
0x1400177b9  mov     byte ptr [rax-48h], 0Fh
0x1400177bd  cmp     byte ptr [rsi+2], 28h ; '('
0x1400177c1  jnz     loc_14001785C
0x1400177c7  mov     [rsi+50h], rdi
0x1400177cb  mov     [rax-40h], rsi
0x1400177cf  mov     eax, [rbp+34h]
0x1400177d2  and     al, 1
0x1400177d4  neg     al
0x1400177d6  mov     rax, [rbx+210h]
0x1400177dd  sbb     ecx, ecx
0x1400177df  and     ecx, 11h
0x1400177e2  add     ecx, 4
0x1400177e5  cmp     byte ptr [rax+1Eh], 1
0x1400177e9  jz      loc_140017886
0x1400177ef  mov     [rsi+2], cl
0x1400177f2  mov     rbx, [rbp+40h]
0x1400177f6  mov     rcx, [rbx+1B8h]
0x1400177fd  add     rcx, 8; RunRefCacheAware
0x140017801  call    cs:__imp_ExAcquireRundownProtectionCacheAware
0x140017808  nop     dword ptr [rax+rax+00h]
0x14001780d  test    al, al
0x14001780f  jz      short loc_14001788E
0x140017811  mov     rax, [rdi+0B8h]
0x140017818  lea     rcx, ClassReleaseQueueCompletion
0x14001781f  mov     rdx, rdi; Irp
0x140017822  mov     [rax-10h], rcx
0x140017826  mov     rcx, r12; DeviceObject
0x140017829  mov     [rax-8], rbp
0x14001782d  mov     byte ptr [rax-45h], 0E0h
0x140017831  call    cs:__imp_IofCallDriver
0x140017838  nop     dword ptr [rax+rax+00h]
0x14001783d  mov     cl, r15b; NewIrql
0x140017840  call    cs:__imp_KeLowerIrql
0x140017847  nop     dword ptr [rax+rax+00h]
0x14001784c  add     rsp, 30h
0x140017850  pop     r15
0x140017852  pop     r14
0x140017854  pop     r12
0x140017856  pop     rdi
0x140017857  pop     rsi
0x140017858  pop     rbp
0x140017859  pop     rbx
0x14001785a  retn
0x14001785c  mov     [rsi+30h], rdi
0x140017860  jmp     loc_1400177CB
0x140017865  test    rdi, rdi
0x140017868  jnz     loc_140017771
0x14001786e  mov     rcx, r14; SpinLock
0x140017871  mov     byte ptr [rbx+330h], 1
0x140017878  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14001787f  nop     dword ptr [rax+rax+00h]
0x140017884  jmp     short loc_14001783D
0x140017886  mov     [rsi+14h], ecx
0x140017889  jmp     loc_1400177F2
0x14001788e  mov     rax, [rbx+1B8h]
0x140017895  lock inc dword ptr [rax]
0x140017898  mov     rcx, cs:WPP_GLOBAL_Control
0x14001789f  lea     rax, WPP_GLOBAL_Control
0x1400178a6  cmp     rcx, rax
0x1400178a9  jz      loc_140017811
0x1400178af  test    dword ptr [rcx+2Ch], 200h
0x1400178b6  jz      loc_140017811
0x1400178bc  cmp     byte ptr [rcx+29h], 5
0x1400178c0  jb      loc_140017811
0x1400178c6  mov     r9, [rbx+1B8h]
0x1400178cd  lea     r8, WPP_a22cc05f221e30b8049471910da99059_Traceguids
0x1400178d4  mov     rcx, [rcx+18h]
0x1400178d8  mov     edx, 0Eh
0x1400178dd  mov     r9d, [r9]
0x1400178e0  call    WPP_SF_d
0x1400178e5  jmp     loc_140017811
0x1400178ea  mov     rcx, rbx
0x1400178ed  call    ClasspAllocateReleaseQueueIrp
0x1400178f2  jmp     loc_140017750
0x1400178f7  xor     r9d, r9d; BugCheckParameter3
0x1400178fa  mov     [rsp+68h+BugCheckParameter4], 0; BugCheckParameter4
0x140017903  mov     r8, rbp; BugCheckParameter2
0x140017906  lea     edx, [r9+12h]; BugCheckParameter1
0x14001790a  lea     ecx, [rdx+1Bh]; BugCheckCode
0x14001790d  call    cs:__imp_KeBugCheckEx
```
