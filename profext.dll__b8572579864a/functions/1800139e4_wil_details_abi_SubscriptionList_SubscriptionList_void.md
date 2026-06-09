# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x1800139e4`
- end: `0x180013a17`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `51`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180013880`
- `0x1800138b0`

## callees

- `0x18000f8b0`
- `0x1800139e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180013a0b`

## pseudocode

```c
void __fastcall wil::details_abi::SubscriptionList::~SubscriptionList(struct _RTL_CRITICAL_SECTION *this)
{
  HANDLE LockSemaphore; // rcx

  LockSemaphore = this[1].LockSemaphore;
  this[1].LockSemaphore = 0;
  if ( LockSemaphore )
    Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Free(LockSemaphore);
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x1800139e4  push    rbx
0x1800139e6  sub     rsp, 20h
0x1800139ea  mov     rbx, rcx
0x1800139ed  mov     rcx, [rcx+40h]
0x1800139f1  mov     qword ptr [rbx+40h], 0
0x1800139f9  test    rcx, rcx
0x1800139fc  jz      short loc_180013A03
0x1800139fe  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x180013a03  mov     rcx, rbx
0x180013a06  add     rsp, 20h
0x180013a0a  pop     rbx
0x180013a0b  jmp     cs:__imp_DeleteCriticalSection
```
