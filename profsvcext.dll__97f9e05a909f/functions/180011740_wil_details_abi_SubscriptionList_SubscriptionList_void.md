# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x180011740`
- end: `0x18001176e`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180011644`
- `0x180011674`

## callees

- `0x18000ccfc`
- `0x180011740`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180011767`

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
0x180011740  push    rbx
0x180011742  sub     rsp, 20h
0x180011746  mov     rbx, rcx
0x180011749  mov     rcx, [rcx+40h]
0x18001174d  mov     qword ptr [rbx+40h], 0
0x180011755  test    rcx, rcx
0x180011758  jz      short loc_18001175F
0x18001175a  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x18001175f  mov     rcx, rbx
0x180011762  add     rsp, 20h
0x180011766  pop     rbx
0x180011767  jmp     cs:__imp_DeleteCriticalSection
```
