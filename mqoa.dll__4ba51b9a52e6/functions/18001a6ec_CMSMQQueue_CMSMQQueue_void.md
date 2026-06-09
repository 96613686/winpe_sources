# CMSMQQueue::~CMSMQQueue(void)

- ea: `0x18001a6ec`
- end: `0x18001a744`
- name: `??1CMSMQQueue@@UEAA@XZ`
- size: `88`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000abd8`
- `0x18000afc0`
- `0x18000b580`

## callees

- `0x1800033ec`
- `0x180003848`
- `0x1800135d0`
- `0x18001a6ec`
- `0x18001a830`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18001a71b`
- `KERNEL32!DeleteCriticalSection` at `0x18001a726`
- `KERNEL32!DeleteCriticalSection` at `0x18001a71b`
- `KERNEL32!DeleteCriticalSection` at `0x18001a726`

## pseudocode

```c
void __fastcall CMSMQQueue::~CMSMQQueue(struct _RTL_CRITICAL_SECTION *this)
{
  CMSMQQueue::Close((CMSMQQueue *)&this->LockCount);
  CFakeGITInterface::~CFakeGITInterface((CFakeGITInterface *)&this[4].SpinCount);
  DeleteCriticalSection(this + 3);
  DeleteCriticalSection(this + 2);
  R<IADs>::~R<IADs>(&this[1].SpinCount);
  ATL::CComAutoDeleteCriticalSection::~CComAutoDeleteCriticalSection((ATL::CComAutoDeleteCriticalSection *)&this->LockSemaphore);
}

```

## disassembly

```asm
0x18001a6ec  mov     [rsp+arg_0], rcx
0x18001a6f1  push    rbx
0x18001a6f2  sub     rsp, 20h
0x18001a6f6  mov     rbx, rcx
0x18001a6f9  add     rcx, 8; this
0x18001a6fd  call    ?Close@CMSMQQueue@@UEAAJXZ; CMSMQQueue::Close(void)
0x18001a702  nop
0x18001a703  jmp     short loc_18001A70A
0x18001a705  mov     rbx, [rsp+28h+arg_0]
0x18001a70a  lea     rcx, [rbx+0C0h]; this
0x18001a711  call    ??1CFakeGITInterface@@UEAA@XZ; CFakeGITInterface::~CFakeGITInterface(void)
0x18001a716  nop
0x18001a717  lea     rcx, [rbx+78h]; lpCriticalSection
0x18001a71b  call    cs:__imp_DeleteCriticalSection
0x18001a721  nop
0x18001a722  lea     rcx, [rbx+50h]; lpCriticalSection
0x18001a726  call    cs:__imp_DeleteCriticalSection
0x18001a72c  nop
0x18001a72d  lea     rcx, [rbx+48h]
0x18001a731  call    ??1?$R@UIADs@@@@QEAA@XZ; R<IADs>::~R<IADs>(void)
0x18001a736  lea     rcx, [rbx+18h]; this
0x18001a73a  add     rsp, 20h
0x18001a73e  pop     rbx
0x18001a73f  jmp     ??1CComAutoDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComAutoDeleteCriticalSection::~CComAutoDeleteCriticalSection(void)
```
