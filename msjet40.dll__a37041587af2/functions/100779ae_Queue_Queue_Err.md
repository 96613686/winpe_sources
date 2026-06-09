# Queue::Queue(Err &)

- ea: `0x100779ae`
- end: `0x10077a00`
- name: `??0Queue@@QAE@AAVErr@@@Z`
- size: `82`
- prototype: `Queue *__thiscall(Queue *__hidden this, struct Err *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x10060b19`

## callees

- `0x10050e15`
- `0x10061284`
- `0x100618a3`
- `0x1007796a`
- `0x100779ae`
- `0x10123110`
- `0x10124048`
- `0x1012410f`
- `0x1012413e`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x100779cf`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x100779cf`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x100779c0`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x100779c0`

## pseudocode

```c
Queue *__thiscall Queue::Queue(Queue *this, struct Err *a2)
{
  HANDLE EventA; // eax
  struct Err *v4; // ecx

  InitializeCriticalSection((LPCRITICAL_SECTION)this);
  EventA = CreateEventA(0, 0, 0, 0);
  *((_DWORD *)this + 6) = EventA;
  if ( !EventA )
    System::ErrGetLastError(v4);
  Collection::Collection((Queue *)((char *)this + 28), 0xAu, (struct Err *)&Sys);
  return this;
}

```

## disassembly

```asm
0x100779ae  push    4
0x100779b0  mov     eax, offset loc_10126F78
0x100779b5  call    __EH_prolog3
0x100779ba  mov     esi, ecx
0x100779bc  mov     [ebp+lpCriticalSection], esi
0x100779bf  push    esi; lpCriticalSection
0x100779c0  call    ds:__imp__InitializeCriticalSection@4; InitializeCriticalSection(x)
0x100779c6  xor     eax, eax
0x100779c8  push    eax; lpName
0x100779c9  push    eax; bInitialState
0x100779ca  push    eax; bManualReset
0x100779cb  push    eax; lpEventAttributes
0x100779cc  mov     [ebp+var_4], eax
0x100779cf  call    ds:__imp__CreateEventA@16; CreateEventA(x,x,x,x)
0x100779d5  mov     [esi+18h], eax
0x100779d8  mov     edi, offset ?Sys@@3VSystem@@A; System Sys
0x100779dd  test    eax, eax
0x100779df  jnz     short loc_100779E7
0x100779e1  push    edi
0x100779e2  call    ?ErrGetLastError@System@@QAEJAAVErr@@@Z; System::ErrGetLastError(Err &)
0x100779e7  push    edi; struct Err *
0x100779e8  push    0Ah; unsigned int
0x100779ea  lea     ecx, [esi+1Ch]; this
0x100779ed  mov     byte ptr [ebp+var_4], 1
0x100779f1  call    ??0Collection@@QAE@KAAVErr@@@Z; Collection::Collection(ulong,Err &)
0x100779f6  mov     eax, esi
0x100779f8  call    __EH_epilog3
0x100779fd  retn    4
0x10126f60  mov     ecx, [ebp+lpCriticalSection]; lpCriticalSection
0x10126f63  jmp     ??1CriticalSection@@QAE@XZ; CriticalSection::~CriticalSection(void)
0x10126f68  mov     ecx, [ebp+lpCriticalSection]
0x10126f6b  add     ecx, 18h; this
0x10126f6e  jmp     ??1Semaphore@@QAE@XZ; Semaphore::~Semaphore(void)
0x10126f78  nop
0x10126f79  nop
0x10126f7a  mov     edx, [esp-4+arg_4]
0x10126f7e  lea     eax, [edx+0Ch]
0x10126f81  mov     ecx, [edx-14h]
0x10126f84  xor     ecx, eax; StackCookie
0x10126f86  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10126f8b  mov     eax, offset stru_10129408
0x10126f90  jmp     ___CxxFrameHandler3
```
