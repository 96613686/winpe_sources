# CKsFilter::DistributeCopyFrames(uchar,uchar)

- ea: `0x1800102d4`
- end: `0x18001047a`
- name: `?DistributeCopyFrames@CKsFilter@@AEAAEEE@Z`
- size: `422`
- prototype: `unsigned __int8 __fastcall(CKsFilter *__hidden this, unsigned __int8, unsigned __int8)`
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000513c`
- `0x180014510`
- `0x1800330cc`

## callees

- `0x18000513c`
- `0x18000b7bc`
- `0x1800102d4`
- `0x180010480`
- `0x180019c60`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18001033c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18001033c`
- `ntoskrnl!KeReleaseSpinLock` at `0x18001039f`
- `ntoskrnl!KeReleaseSpinLock` at `0x180010453`
- `ntoskrnl!KeReleaseSpinLock` at `0x18001039f`
- `ntoskrnl!KeReleaseSpinLock` at `0x180010453`
- `ntoskrnl!KeWaitForSingleObject` at `0x180010380`
- `ntoskrnl!KeWaitForSingleObject` at `0x180010380`

## pseudocode

```c
unsigned __int8 __fastcall CKsFilter::DistributeCopyFrames(CKsFilter *this, char a2, char a3)
{
  KIRQL v6; // bp
  INTERLOCKEDLIST_HEAD *p_m_CopyFrames; // rsi
  struct _LIST_ENTRY *Flink; // rdi
  struct _KSPPROCESSPIPESECTION *QuadPart; // rdx
  INTERLOCKEDLIST_HEAD *v11; // r12
  struct _LIST_ENTRY *Blink; // rax
  LARGE_INTEGER v13; // rcx
  LARGE_INTEGER Timeout; // [rsp+98h] [rbp+20h] BYREF

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      67,
      (__int64)WPP_001f1e784e56319d01cbbdcd1f1acdab_Traceguids);
  if ( a2 )
    v6 = KeAcquireSpinLockRaiseToDpc(&this->m_CopyFrames.SpinLock);
  else
    v6 = 0;
  p_m_CopyFrames = &this->m_CopyFrames;
  if ( a3 && (Timeout.QuadPart = 0, KeWaitForSingleObject(&this->m_Mutex, Executive, 0, 0, &Timeout) == 258) )
  {
    if ( a2 )
      KeReleaseSpinLock(&this->m_CopyFrames.SpinLock, v6);
    return 0;
  }
  else
  {
    Flink = p_m_CopyFrames->ListEntry.Flink;
    if ( (INTERLOCKEDLIST_HEAD *)p_m_CopyFrames->ListEntry.Flink != p_m_CopyFrames )
    {
      do
      {
        Timeout = (LARGE_INTEGER)Flink[-4].Blink[8].Blink[4].Flink;
        QuadPart = (struct _KSPPROCESSPIPESECTION *)Timeout.QuadPart;
        *(_QWORD *)(Timeout.QuadPart + 72) = Flink - 10;
        CKsFilter::CopyToDestinations(this, QuadPart, (int)Flink[-3].Flink[3].Flink);
        v11 = (INTERLOCKEDLIST_HEAD *)Flink->Flink;
        if ( Flink->Flink->Blink != Flink || (Blink = Flink->Blink, Blink->Flink != Flink) )
          __fastfail(3u);
        v13 = Timeout;
        Blink->Flink = &v11->ListEntry;
        v11->ListEntry.Blink = Blink;
        (*(void (__fastcall **)(_QWORD, struct _LIST_ENTRY **))(**(_QWORD **)(v13.QuadPart + 64) + 96LL))(
          *(_QWORD *)(v13.QuadPart + 64),
          &Flink[-10].Flink);
        Flink = &v11->ListEntry;
      }
      while ( v11 != p_m_CopyFrames );
    }
    this->m_FramesWaitingForCopy = 0;
    if ( a3 )
      CKsFilter::ReleaseProcessSync(this);
    if ( a2 )
      KeReleaseSpinLock(&this->m_CopyFrames.SpinLock, v6);
    return 1;
  }
}

```

## disassembly

```asm
0x1800102d4  push    rbx
0x1800102d6  push    rbp
0x1800102d7  push    rsi
0x1800102d8  push    rdi
0x1800102d9  push    r12
0x1800102db  push    r13
0x1800102dd  push    r14
0x1800102df  push    r15
0x1800102e1  sub     rsp, 38h
0x1800102e5  mov     r15b, r8b
0x1800102e8  mov     r14b, dl
0x1800102eb  mov     rbx, rcx
0x1800102ee  lea     rax, WPP_RECORDER_INITIALIZED
0x1800102f5  xor     r12d, r12d
0x1800102f8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800102ff  jz      short loc_180010330
0x180010301  mov     rcx, cs:WPP_GLOBAL_Control
0x180010308  cmp     [rcx+48h], r12w
0x18001030d  jz      short loc_180010330
0x18001030f  mov     rcx, [rcx+40h]
0x180010313  lea     rax, WPP_001f1e784e56319d01cbbdcd1f1acdab_Traceguids
0x18001031a  lea     r9d, [r12+43h]
0x18001031f  mov     [rsp+78h+Timeout], rax
0x180010324  lea     r8d, [r12+1]
0x180010329  mov     dl, 5
0x18001032b  call    WPP_RECORDER_SF_
0x180010330  test    r14b, r14b
0x180010333  jz      short loc_18001034D
0x180010335  lea     rcx, [rbx+2F0h]; SpinLock
0x18001033c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x180010343  nop     dword ptr [rax+rax+00h]
0x180010348  mov     bpl, al
0x18001034b  jmp     short loc_180010350
0x18001034d  mov     bpl, r12b
0x180010350  lea     rsi, [rbx+2E0h]
0x180010357  test    r15b, r15b
0x18001035a  jz      short loc_1800103B2
0x18001035c  lea     rax, [rsp+78h+arg_18]
0x180010364  mov     qword ptr [rsp+78h+arg_18], r12
0x18001036c  lea     rcx, [rbx+290h]; Object
0x180010373  mov     [rsp+78h+Timeout], rax; Timeout
0x180010378  xor     r9d, r9d; Alertable
0x18001037b  xor     r8d, r8d; WaitMode
0x18001037e  xor     edx, edx; WaitReason
0x180010380  call    cs:__imp_KeWaitForSingleObject
0x180010387  nop     dword ptr [rax+rax+00h]
0x18001038c  cmp     eax, 102h
0x180010391  jnz     short loc_1800103B2
0x180010393  test    r14b, r14b
0x180010396  jz      short loc_1800103AB
0x180010398  lea     rcx, [rsi+10h]; SpinLock
0x18001039c  mov     dl, bpl; NewIrql
0x18001039f  call    cs:__imp_KeReleaseSpinLock
0x1800103a6  nop     dword ptr [rax+rax+00h]
0x1800103ab  xor     al, al
0x1800103ad  jmp     loc_180010461
0x1800103b2  mov     rdi, [rsi]
0x1800103b5  cmp     rdi, rsi
0x1800103b8  jz      short loc_180010430
0x1800103ba  lea     r13, [rdi-0A0h]
0x1800103c1  mov     rax, [r13+68h]
0x1800103c5  mov     rcx, [rax+88h]
0x1800103cc  mov     rax, [rcx+40h]
0x1800103d0  mov     rcx, rbx; this
0x1800103d3  mov     rdx, rax; struct _KSPPROCESSPIPESECTION *
0x1800103d6  mov     qword ptr [rsp+78h+arg_18], rax
0x1800103de  mov     [rax+48h], r13
0x1800103e2  mov     r8, [r13+70h]
0x1800103e6  mov     r8d, [r8+30h]; unsigned int
0x1800103ea  call    ?CopyToDestinations@CKsFilter@@QEAAXPEAU_KSPPROCESSPIPESECTION@@KE@Z; CKsFilter::CopyToDestinations(_KSPPROCESSPIPESECTION *,ulong,uchar)
0x1800103ef  mov     r12, [rdi]
0x1800103f2  cmp     [r12+8], rdi
0x1800103f7  jnz     short loc_180010473
0x1800103f9  mov     rax, [rdi+8]
0x1800103fd  cmp     [rax], rdi
0x180010400  jnz     short loc_180010473
0x180010402  mov     rcx, qword ptr [rsp+78h+arg_18]
0x18001040a  mov     rdx, r13
0x18001040d  mov     [rax], r12
0x180010410  mov     [r12+8], rax
0x180010415  mov     rcx, [rcx+40h]
0x180010419  mov     rax, [rcx]
0x18001041c  mov     rax, [rax+60h]
0x180010420  call    _guard_dispatch_icall
0x180010425  mov     rdi, r12
0x180010428  cmp     r12, rsi
0x18001042b  jnz     short loc_1800103BA
0x18001042d  xor     r12d, r12d
0x180010430  mov     [rbx+2DCh], r12d
0x180010437  test    r15b, r15b
0x18001043a  jz      short loc_180010444
0x18001043c  mov     rcx, rbx; this
0x18001043f  call    ?ReleaseProcessSync@CKsFilter@@QEAAXXZ; CKsFilter::ReleaseProcessSync(void)
0x180010444  test    r14b, r14b
0x180010447  jz      short loc_18001045F
0x180010449  lea     rcx, [rbx+2F0h]; SpinLock
0x180010450  mov     dl, bpl; NewIrql
0x180010453  call    cs:__imp_KeReleaseSpinLock
0x18001045a  nop     dword ptr [rax+rax+00h]
0x18001045f  mov     al, 1
0x180010461  add     rsp, 38h
0x180010465  pop     r15
0x180010467  pop     r14
0x180010469  pop     r13
0x18001046b  pop     r12
0x18001046d  pop     rdi
0x18001046e  pop     rsi
0x18001046f  pop     rbp
0x180010470  pop     rbx
0x180010471  retn
0x180010473  mov     ecx, 3
0x180010478  int     29h; Win8: RtlFailFast(ecx)
```
