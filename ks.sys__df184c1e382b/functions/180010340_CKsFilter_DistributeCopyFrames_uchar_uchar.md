# CKsFilter::DistributeCopyFrames(uchar,uchar)

- ea: `0x180010340`
- end: `0x1800104e6`
- name: `?DistributeCopyFrames@CKsFilter@@AEAAEEE@Z`
- size: `422`
- prototype: `unsigned __int8 __fastcall(CKsFilter *this, char, char, unsigned __int8)`
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
- `0x180010340`
- `0x1800104ec`
- `0x180019cb0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1800103a8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1800103a8`
- `ntoskrnl!KeReleaseSpinLock` at `0x18001040b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1800104bf`
- `ntoskrnl!KeReleaseSpinLock` at `0x18001040b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1800104bf`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800103ec`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800103ec`

## pseudocode

```c
unsigned __int8 __fastcall CKsFilter::DistributeCopyFrames(CKsFilter *this, char a2, char a3, unsigned __int8 a4)
{
  KIRQL v7; // bp
  INTERLOCKEDLIST_HEAD *p_m_CopyFrames; // rsi
  struct _LIST_ENTRY *Flink; // rdi
  struct _KSPPROCESSPIPESECTION *QuadPart; // rdx
  INTERLOCKEDLIST_HEAD *v12; // r12
  struct _LIST_ENTRY *Blink; // rax
  LARGE_INTEGER v14; // rcx
  LARGE_INTEGER Timeout; // [rsp+98h] [rbp+20h] BYREF

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      67,
      (__int64)WPP_001f1e784e56319d01cbbdcd1f1acdab_Traceguids);
  if ( a2 )
    v7 = KeAcquireSpinLockRaiseToDpc(&this->m_CopyFrames.SpinLock);
  else
    v7 = 0;
  p_m_CopyFrames = &this->m_CopyFrames;
  if ( a3 && (Timeout.QuadPart = 0, KeWaitForSingleObject(&this->m_Mutex, Executive, 0, 0, &Timeout) == 258) )
  {
    if ( a2 )
      KeReleaseSpinLock(&this->m_CopyFrames.SpinLock, v7);
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
        CKsFilter::CopyToDestinations(this, QuadPart, (unsigned int)Flink[-3].Flink[3].Flink, a4);
        v12 = (INTERLOCKEDLIST_HEAD *)Flink->Flink;
        if ( Flink->Flink->Blink != Flink || (Blink = Flink->Blink, Blink->Flink != Flink) )
          __fastfail(3u);
        v14 = Timeout;
        Blink->Flink = &v12->ListEntry;
        v12->ListEntry.Blink = Blink;
        (*(void (__fastcall **)(_QWORD, struct _LIST_ENTRY **))(**(_QWORD **)(v14.QuadPart + 64) + 96LL))(
          *(_QWORD *)(v14.QuadPart + 64),
          &Flink[-10].Flink);
        Flink = &v12->ListEntry;
      }
      while ( v12 != p_m_CopyFrames );
    }
    this->m_FramesWaitingForCopy = 0;
    if ( a3 )
      CKsFilter::ReleaseProcessSync(this);
    if ( a2 )
      KeReleaseSpinLock(&this->m_CopyFrames.SpinLock, v7);
    return 1;
  }
}

```

## disassembly

```asm
0x180010340  push    rbx
0x180010342  push    rbp
0x180010343  push    rsi
0x180010344  push    rdi
0x180010345  push    r12
0x180010347  push    r13
0x180010349  push    r14
0x18001034b  push    r15
0x18001034d  sub     rsp, 38h
0x180010351  mov     r15b, r8b
0x180010354  mov     r14b, dl
0x180010357  mov     rbx, rcx
0x18001035a  lea     rax, WPP_RECORDER_INITIALIZED
0x180010361  xor     r12d, r12d
0x180010364  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18001036b  jz      short loc_18001039C
0x18001036d  mov     rcx, cs:WPP_GLOBAL_Control
0x180010374  cmp     [rcx+48h], r12w
0x180010379  jz      short loc_18001039C
0x18001037b  mov     rcx, [rcx+40h]
0x18001037f  lea     rax, WPP_001f1e784e56319d01cbbdcd1f1acdab_Traceguids
0x180010386  lea     r9d, [r12+43h]
0x18001038b  mov     [rsp+78h+Timeout], rax
0x180010390  lea     r8d, [r12+1]
0x180010395  mov     dl, 5
0x180010397  call    WPP_RECORDER_SF_
0x18001039c  test    r14b, r14b
0x18001039f  jz      short loc_1800103B9
0x1800103a1  lea     rcx, [rbx+2F0h]; SpinLock
0x1800103a8  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1800103af  nop     dword ptr [rax+rax+00h]
0x1800103b4  mov     bpl, al
0x1800103b7  jmp     short loc_1800103BC
0x1800103b9  mov     bpl, r12b
0x1800103bc  lea     rsi, [rbx+2E0h]
0x1800103c3  test    r15b, r15b
0x1800103c6  jz      short loc_18001041E
0x1800103c8  lea     rax, [rsp+78h+arg_18]
0x1800103d0  mov     qword ptr [rsp+78h+arg_18], r12
0x1800103d8  lea     rcx, [rbx+290h]; Object
0x1800103df  mov     [rsp+78h+Timeout], rax; Timeout
0x1800103e4  xor     r9d, r9d; Alertable
0x1800103e7  xor     r8d, r8d; WaitMode
0x1800103ea  xor     edx, edx; WaitReason
0x1800103ec  call    cs:__imp_KeWaitForSingleObject
0x1800103f3  nop     dword ptr [rax+rax+00h]
0x1800103f8  cmp     eax, 102h
0x1800103fd  jnz     short loc_18001041E
0x1800103ff  test    r14b, r14b
0x180010402  jz      short loc_180010417
0x180010404  lea     rcx, [rsi+10h]; SpinLock
0x180010408  mov     dl, bpl; NewIrql
0x18001040b  call    cs:__imp_KeReleaseSpinLock
0x180010412  nop     dword ptr [rax+rax+00h]
0x180010417  xor     al, al
0x180010419  jmp     loc_1800104CD
0x18001041e  mov     rdi, [rsi]
0x180010421  cmp     rdi, rsi
0x180010424  jz      short loc_18001049C
0x180010426  lea     r13, [rdi-0A0h]
0x18001042d  mov     rax, [r13+68h]
0x180010431  mov     rcx, [rax+88h]
0x180010438  mov     rax, [rcx+40h]
0x18001043c  mov     rcx, rbx; this
0x18001043f  mov     rdx, rax; struct _KSPPROCESSPIPESECTION *
0x180010442  mov     qword ptr [rsp+78h+arg_18], rax
0x18001044a  mov     [rax+48h], r13
0x18001044e  mov     r8, [r13+70h]
0x180010452  mov     r8d, [r8+30h]; unsigned int
0x180010456  call    ?CopyToDestinations@CKsFilter@@QEAAXPEAU_KSPPROCESSPIPESECTION@@KE@Z; CKsFilter::CopyToDestinations(_KSPPROCESSPIPESECTION *,ulong,uchar)
0x18001045b  mov     r12, [rdi]
0x18001045e  cmp     [r12+8], rdi
0x180010463  jnz     short loc_1800104DF
0x180010465  mov     rax, [rdi+8]
0x180010469  cmp     [rax], rdi
0x18001046c  jnz     short loc_1800104DF
0x18001046e  mov     rcx, qword ptr [rsp+78h+arg_18]
0x180010476  mov     rdx, r13
0x180010479  mov     [rax], r12
0x18001047c  mov     [r12+8], rax
0x180010481  mov     rcx, [rcx+40h]
0x180010485  mov     rax, [rcx]
0x180010488  mov     rax, [rax+60h]
0x18001048c  call    _guard_dispatch_icall
0x180010491  mov     rdi, r12
0x180010494  cmp     r12, rsi
0x180010497  jnz     short loc_180010426
0x180010499  xor     r12d, r12d
0x18001049c  mov     [rbx+2DCh], r12d
0x1800104a3  test    r15b, r15b
0x1800104a6  jz      short loc_1800104B0
0x1800104a8  mov     rcx, rbx; this
0x1800104ab  call    ?ReleaseProcessSync@CKsFilter@@QEAAXXZ; CKsFilter::ReleaseProcessSync(void)
0x1800104b0  test    r14b, r14b
0x1800104b3  jz      short loc_1800104CB
0x1800104b5  lea     rcx, [rbx+2F0h]; SpinLock
0x1800104bc  mov     dl, bpl; NewIrql
0x1800104bf  call    cs:__imp_KeReleaseSpinLock
0x1800104c6  nop     dword ptr [rax+rax+00h]
0x1800104cb  mov     al, 1
0x1800104cd  add     rsp, 38h
0x1800104d1  pop     r15
0x1800104d3  pop     r14
0x1800104d5  pop     r13
0x1800104d7  pop     r12
0x1800104d9  pop     rdi
0x1800104da  pop     rsi
0x1800104db  pop     rbp
0x1800104dc  pop     rbx
0x1800104dd  retn
0x1800104df  mov     ecx, 3
0x1800104e4  int     29h; Win8: RtlFailFast(ecx)
```
