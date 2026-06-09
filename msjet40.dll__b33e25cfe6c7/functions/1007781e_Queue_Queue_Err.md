# Queue::Queue(Err &)

- ea: `0x1007781e`
- end: `0x10077870`
- name: `??0Queue@@QAE@AAVErr@@@Z`
- size: `82`
- prototype: `Queue *__thiscall(Queue *__hidden this, struct Err *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x10060989`

## callees

- `0x10050c85`
- `0x100610f0`
- `0x10061713`
- `0x100777da`
- `0x1007781e`
- `0x10122f60`
- `0x10123e98`
- `0x10123f5f`
- `0x10123f8e`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1007783f`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1007783f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x10077830`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x10077830`

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
0x1007781e  push    4
0x10077820  mov     eax, offset loc_10126DC8
0x10077825  call    __EH_prolog3
0x1007782a  mov     esi, ecx
0x1007782c  mov     [ebp+lpCriticalSection], esi
0x1007782f  push    esi; lpCriticalSection
0x10077830  call    ds:__imp__InitializeCriticalSection@4; InitializeCriticalSection(x)
0x10077836  xor     eax, eax
0x10077838  push    eax; lpName
0x10077839  push    eax; bInitialState
0x1007783a  push    eax; bManualReset
0x1007783b  push    eax; lpEventAttributes
0x1007783c  mov     [ebp+var_4], eax
0x1007783f  call    ds:__imp__CreateEventA@16; CreateEventA(x,x,x,x)
0x10077845  mov     [esi+18h], eax
0x10077848  mov     edi, offset ?Sys@@3VSystem@@A; System Sys
0x1007784d  test    eax, eax
0x1007784f  jnz     short loc_10077857
0x10077851  push    edi
0x10077852  call    ?ErrGetLastError@System@@QAEJAAVErr@@@Z; System::ErrGetLastError(Err &)
0x10077857  push    edi; struct Err *
0x10077858  push    0Ah; unsigned int
0x1007785a  lea     ecx, [esi+1Ch]; this
0x1007785d  mov     byte ptr [ebp+var_4], 1
0x10077861  call    ??0Collection@@QAE@KAAVErr@@@Z; Collection::Collection(ulong,Err &)
0x10077866  mov     eax, esi
0x10077868  call    __EH_epilog3
0x1007786d  retn    4
0x10126db0  mov     ecx, [ebp+lpCriticalSection]; lpCriticalSection
0x10126db3  jmp     ??1CriticalSection@@QAE@XZ; CriticalSection::~CriticalSection(void)
0x10126db8  mov     ecx, [ebp+lpCriticalSection]
0x10126dbb  add     ecx, 18h; this
0x10126dbe  jmp     ??1Semaphore@@QAE@XZ; Semaphore::~Semaphore(void)
0x10126dc8  nop
0x10126dc9  nop
0x10126dca  mov     edx, [esp-4+arg_4]
0x10126dce  lea     eax, [edx+0Ch]
0x10126dd1  mov     ecx, [edx-14h]
0x10126dd4  xor     ecx, eax; StackCookie
0x10126dd6  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10126ddb  mov     eax, offset stru_10129258
0x10126de0  jmp     ___CxxFrameHandler3
```
