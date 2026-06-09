# CHidPairing::FinalConstruct(void)

- ea: `0x1800af57c`
- end: `0x1800af746`
- name: `?FinalConstruct@CHidPairing@@QEAAJXZ`
- size: `458`
- prototype: `__int64 __fastcall(CHidPairing *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800af2f8`

## callees

- `0x18000ac48`
- `0x1800af57c`
- `0x1800b0c14`
- `0x1800b8834`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800af5a3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800af5b0`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800af5a3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800af5b0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800af5ea`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800af615`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800af640`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800af66b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800af696`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800af6bd`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800af6e4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800af70b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800af5ea`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800af615`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800af640`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800af66b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800af696`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800af6bd`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800af6e4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800af70b`
- `USER32!RegisterWindowMessageW` at `0x1800af5bd`
- `USER32!RegisterWindowMessageW` at `0x1800af5bd`

## pseudocode

```c
__int64 __fastcall CHidPairing::FinalConstruct(struct _RTL_CRITICAL_SECTION *this)
{
  UINT v2; // eax
  int Error; // ebx
  HANDLE EventW; // rax
  HANDLE v5; // rax
  HANDLE v6; // rax
  HANDLE v7; // rax
  struct _RTL_CRITICAL_SECTION_DEBUG *v8; // rax
  HANDLE v9; // rax
  HANDLE v10; // rax
  HANDLE v11; // rax

  UnattendLogW(0, L"CHidPairing::FinalConstruct - Creating HID Pairing instance");
  InitializeCriticalSection(this + 5);
  InitializeCriticalSection(this + 6);
  v2 = RegisterWindowMessageW(L"HidPairing");
  LODWORD(this[7].DebugInfo) = v2;
  if ( !v2 )
  {
    Error = ResultFromKnownLastError();
    if ( Error < 0 )
      goto LABEL_20;
  }
  EventW = CreateEventW(0, 1, 0, 0);
  this[7].OwningThread = EventW;
  if ( !EventW )
  {
    Error = ResultFromKnownLastError();
    if ( Error < 0 )
      goto LABEL_20;
  }
  v5 = CreateEventW(0, 0, 0, 0);
  this[7].LockSemaphore = v5;
  if ( !v5 )
  {
    Error = ResultFromKnownLastError();
    if ( Error < 0 )
      goto LABEL_20;
  }
  v6 = CreateEventW(0, 1, 0, 0);
  this[7].SpinCount = (ULONG_PTR)v6;
  if ( !v6 )
  {
    Error = ResultFromKnownLastError();
    if ( Error < 0 )
      goto LABEL_20;
  }
  v7 = CreateEventW(0, 1, 0, 0);
  this[8].OwningThread = v7;
  if ( !v7 )
  {
    Error = ResultFromKnownLastError();
    if ( Error < 0 )
      goto LABEL_20;
  }
  v8 = (struct _RTL_CRITICAL_SECTION_DEBUG *)CreateEventW(0, 1, 0, 0);
  this[8].DebugInfo = v8;
  if ( !v8 )
  {
    Error = ResultFromKnownLastError();
    if ( Error < 0 )
      goto LABEL_20;
  }
  v9 = CreateEventW(0, 1, 0, 0);
  *(_QWORD *)&this[8].LockCount = v9;
  if ( !v9 )
  {
    Error = ResultFromKnownLastError();
    if ( Error < 0 )
      goto LABEL_20;
  }
  v10 = CreateEventW(0, 1, 0, 0);
  this[8].SpinCount = (ULONG_PTR)v10;
  if ( !v10 )
  {
    Error = ResultFromKnownLastError();
    if ( Error < 0 )
      goto LABEL_20;
  }
  v11 = CreateEventW(0, 1, 0, 0);
  this[8].LockSemaphore = v11;
  if ( !v11 )
  {
    Error = ResultFromKnownLastError();
    if ( Error >= 0 )
      return (unsigned int)Error;
LABEL_20:
    CHidPairing::_Deinitialize((CHidPairing *)this);
    return (unsigned int)Error;
  }
  return 0;
}

```

## disassembly

```asm
0x1800af57c  mov     [rsp+arg_0], rbx
0x1800af581  mov     [rsp+arg_8], rsi
0x1800af586  push    rdi
0x1800af587  sub     rsp, 20h
0x1800af58b  mov     rdi, rcx
0x1800af58e  lea     rdx, aChidpairingFin; "CHidPairing::FinalConstruct - Creating "...
0x1800af595  xor     ecx, ecx
0x1800af597  call    UnattendLogW
0x1800af59c  lea     rcx, [rdi+0C8h]; lpCriticalSection
0x1800af5a3  call    cs:__imp_InitializeCriticalSection
0x1800af5a9  lea     rcx, [rdi+0F0h]; lpCriticalSection
0x1800af5b0  call    cs:__imp_InitializeCriticalSection
0x1800af5b6  lea     rcx, String; "HidPairing"
0x1800af5bd  call    cs:__imp_RegisterWindowMessageW
0x1800af5c3  mov     [rdi+118h], eax
0x1800af5c9  test    eax, eax
0x1800af5cb  jnz     short loc_1800AF5DC
0x1800af5cd  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800af5d2  mov     ebx, eax
0x1800af5d4  test    eax, eax
0x1800af5d6  js      loc_1800AF72C
0x1800af5dc  xor     r9d, r9d; lpName
0x1800af5df  xor     r8d, r8d; bInitialState
0x1800af5e2  xor     ecx, ecx; lpEventAttributes
0x1800af5e4  lea     esi, [r9+1]
0x1800af5e8  mov     edx, esi; bManualReset
0x1800af5ea  call    cs:__imp_CreateEventW
0x1800af5f0  mov     [rdi+128h], rax
0x1800af5f7  test    rax, rax
0x1800af5fa  jnz     short loc_1800AF60B
0x1800af5fc  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800af601  mov     ebx, eax
0x1800af603  test    eax, eax
0x1800af605  js      loc_1800AF72C
0x1800af60b  xor     r9d, r9d; lpName
0x1800af60e  xor     r8d, r8d; bInitialState
0x1800af611  xor     edx, edx; bManualReset
0x1800af613  xor     ecx, ecx; lpEventAttributes
0x1800af615  call    cs:__imp_CreateEventW
0x1800af61b  mov     [rdi+130h], rax
0x1800af622  test    rax, rax
0x1800af625  jnz     short loc_1800AF636
0x1800af627  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800af62c  mov     ebx, eax
0x1800af62e  test    eax, eax
0x1800af630  js      loc_1800AF72C
0x1800af636  xor     r9d, r9d; lpName
0x1800af639  xor     r8d, r8d; bInitialState
0x1800af63c  mov     edx, esi; bManualReset
0x1800af63e  xor     ecx, ecx; lpEventAttributes
0x1800af640  call    cs:__imp_CreateEventW
0x1800af646  mov     [rdi+138h], rax
0x1800af64d  test    rax, rax
0x1800af650  jnz     short loc_1800AF661
0x1800af652  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800af657  mov     ebx, eax
0x1800af659  test    eax, eax
0x1800af65b  js      loc_1800AF72C
0x1800af661  xor     r9d, r9d; lpName
0x1800af664  xor     r8d, r8d; bInitialState
0x1800af667  mov     edx, esi; bManualReset
0x1800af669  xor     ecx, ecx; lpEventAttributes
0x1800af66b  call    cs:__imp_CreateEventW
0x1800af671  mov     [rdi+150h], rax
0x1800af678  test    rax, rax
0x1800af67b  jnz     short loc_1800AF68C
0x1800af67d  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800af682  mov     ebx, eax
0x1800af684  test    eax, eax
0x1800af686  js      loc_1800AF72C
0x1800af68c  xor     r9d, r9d; lpName
0x1800af68f  xor     r8d, r8d; bInitialState
0x1800af692  mov     edx, esi; bManualReset
0x1800af694  xor     ecx, ecx; lpEventAttributes
0x1800af696  call    cs:__imp_CreateEventW
0x1800af69c  mov     [rdi+140h], rax
0x1800af6a3  test    rax, rax
0x1800af6a6  jnz     short loc_1800AF6B3
0x1800af6a8  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800af6ad  mov     ebx, eax
0x1800af6af  test    eax, eax
0x1800af6b1  js      short loc_1800AF72C
0x1800af6b3  xor     r9d, r9d; lpName
0x1800af6b6  xor     r8d, r8d; bInitialState
0x1800af6b9  mov     edx, esi; bManualReset
0x1800af6bb  xor     ecx, ecx; lpEventAttributes
0x1800af6bd  call    cs:__imp_CreateEventW
0x1800af6c3  mov     [rdi+148h], rax
0x1800af6ca  test    rax, rax
0x1800af6cd  jnz     short loc_1800AF6DA
0x1800af6cf  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800af6d4  mov     ebx, eax
0x1800af6d6  test    eax, eax
0x1800af6d8  js      short loc_1800AF72C
0x1800af6da  xor     r9d, r9d; lpName
0x1800af6dd  xor     r8d, r8d; bInitialState
0x1800af6e0  mov     edx, esi; bManualReset
0x1800af6e2  xor     ecx, ecx; lpEventAttributes
0x1800af6e4  call    cs:__imp_CreateEventW
0x1800af6ea  mov     [rdi+160h], rax
0x1800af6f1  test    rax, rax
0x1800af6f4  jnz     short loc_1800AF701
0x1800af6f6  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800af6fb  mov     ebx, eax
0x1800af6fd  test    eax, eax
0x1800af6ff  js      short loc_1800AF72C
0x1800af701  xor     r9d, r9d; lpName
0x1800af704  xor     r8d, r8d; bInitialState
0x1800af707  mov     edx, esi; bManualReset
0x1800af709  xor     ecx, ecx; lpEventAttributes
0x1800af70b  call    cs:__imp_CreateEventW
0x1800af711  mov     [rdi+158h], rax
0x1800af718  test    rax, rax
0x1800af71b  jz      short loc_1800AF721
0x1800af71d  xor     ebx, ebx
0x1800af71f  jmp     short loc_1800AF734
0x1800af721  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800af726  mov     ebx, eax
0x1800af728  test    eax, eax
0x1800af72a  jns     short loc_1800AF734
0x1800af72c  mov     rcx, rdi; this
0x1800af72f  call    ?_Deinitialize@CHidPairing@@AEAAXXZ; CHidPairing::_Deinitialize(void)
0x1800af734  mov     rsi, [rsp+28h+arg_8]
0x1800af739  mov     eax, ebx
0x1800af73b  mov     rbx, [rsp+28h+arg_0]
0x1800af740  add     rsp, 20h
0x1800af744  pop     rdi
0x1800af745  retn
```
