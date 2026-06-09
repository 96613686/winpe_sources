# `ListenerRegistration::RegistrationLock(void)'::`2'::`dynamic atexit destructor for 'registrationLock''(void)

- ea: `0x18001e470`
- end: `0x18001e47e`
- name: `??__FregistrationLock@?1??RegistrationLock@ListenerRegistration@@CAAEAVCritSec@@XZ@YAXXZ`
- size: `14`
- prototype: `void __fastcall()`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001e477`

## pseudocode

```c
void __fastcall `ListenerRegistration::RegistrationLock'::`2'::`dynamic atexit destructor for 'registrationLock''()
{
  DeleteCriticalSection(&`ListenerRegistration::RegistrationLock'::`2'::registrationLock);
}

```

## disassembly

```asm
0x18001e470  lea     rcx, ?registrationLock@?1??RegistrationLock@ListenerRegistration@@CAAEAVCritSec@@XZ@4V3@A; CritSec `ListenerRegistration::RegistrationLock(void)'::`2'::registrationLock
0x18001e477  jmp     cs:__imp_DeleteCriticalSection
```
