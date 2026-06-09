# CMSMQTransaction::~CMSMQTransaction(void)

- ea: `0x1800201e0`
- end: `0x180020225`
- name: `??1CMSMQTransaction@@UEAA@XZ`
- size: `69`
- prototype: `void __fastcall(CMSMQTransaction *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000ac98`
- `0x18000b098`
- `0x18000b640`

## callees

- `0x1800033ec`
- `0x180003848`
- `0x1800201e0`
- `0x180029010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180020207`
- `KERNEL32!DeleteCriticalSection` at `0x180020207`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CMSMQTransaction::~CMSMQTransaction(struct _RTL_CRITICAL_SECTION *this)
{
  void (__fastcall ***DebugInfo)(_QWORD, _QWORD); // rcx

  DebugInfo = (void (__fastcall ***)(_QWORD, _QWORD))this[3].DebugInfo;
  if ( DebugInfo )
    (**DebugInfo)(DebugInfo, 1);
  DeleteCriticalSection(this + 2);
  R<IADs>::~R<IADs>(&this[1].SpinCount);
  ATL::CComAutoDeleteCriticalSection::~CComAutoDeleteCriticalSection((ATL::CComAutoDeleteCriticalSection *)&this->LockSemaphore);
}

```

## disassembly

```asm
0x1800201e0  push    rbx
0x1800201e2  sub     rsp, 20h
0x1800201e6  mov     rbx, rcx
0x1800201e9  mov     rcx, [rcx+78h]
0x1800201ed  test    rcx, rcx
0x1800201f0  jz      short loc_180020203
0x1800201f2  mov     rax, [rcx]
0x1800201f5  mov     edx, 1
0x1800201fa  mov     rax, [rax]
0x1800201fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020202  nop
0x180020203  lea     rcx, [rbx+50h]; lpCriticalSection
0x180020207  call    cs:__imp_DeleteCriticalSection
0x18002020d  nop
0x18002020e  lea     rcx, [rbx+48h]
0x180020212  call    ??1?$R@UIADs@@@@QEAA@XZ; R<IADs>::~R<IADs>(void)
0x180020217  lea     rcx, [rbx+18h]; this
0x18002021b  add     rsp, 20h
0x18002021f  pop     rbx
0x180020220  jmp     ??1CComAutoDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComAutoDeleteCriticalSection::~CComAutoDeleteCriticalSection(void)
```
