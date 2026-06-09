# CDirectMusicUMAPort::InitializeOverlappedStructs(void)

- ea: `0x18001f9ac`
- end: `0x18001fb66`
- name: `?InitializeOverlappedStructs@CDirectMusicUMAPort@@AEAAJXZ`
- size: `442`
- prototype: `__int64 __fastcall(CDirectMusicUMAPort *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001f51c`

## callees

- `0x1800012d0`
- `0x18001f9ac`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18001f9fc`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18001fa3c`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18001fa7e`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18001f9fc`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18001fa3c`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18001fa7e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fb0d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fb0d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001fab1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001fab1`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001fb3b`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001fb3b`

## pseudocode

```c
__int64 __fastcall CDirectMusicUMAPort::InitializeOverlappedStructs(struct _RTL_CRITICAL_SECTION *this)
{
  struct _RTL_CRITICAL_SECTION_DEBUG *v2; // rax
  __int64 i; // r8
  __int64 v5; // r10
  __int64 j; // r9
  __int64 v7; // rdx
  HANDLE v8; // rax
  DWORD ThreadId; // [rsp+40h] [rbp+8h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION_DEBUG *)operator new[](saturated_mul(HIDWORD(this[35].OwningThread), 8u));
  this[35].DebugInfo = v2;
  if ( !v2 )
    return 2147942414LL;
  *(_QWORD *)this[35].DebugInfo = CreateEventA(0, 1, 0, 0);
  if ( !*(_QWORD *)this[35].DebugInfo )
    return 2147500037LL;
  ++LODWORD(this[35].OwningThread);
  if ( HIDWORD(this[35].OwningThread) < 2 )
    return 2147500037LL;
  this[35].DebugInfo->CriticalSection = (struct _RTL_CRITICAL_SECTION *)CreateEventA(0, 1, 0, 0);
  if ( !this[35].DebugInfo->CriticalSection )
    return 2147500037LL;
  ++LODWORD(this[35].OwningThread);
  if ( HIDWORD(this[35].OwningThread) < 3 )
    return 2147500037LL;
  this[35].DebugInfo->ProcessLocksList.Flink = (struct _LIST_ENTRY *)CreateEventA(0, 1, 0, 0);
  if ( !this[35].DebugInfo->ProcessLocksList.Flink )
    return 2147500037LL;
  ++LODWORD(this[35].OwningThread);
  EnterCriticalSection(this + 34);
  for ( i = (*(__int64 (__fastcall **)(LONG *))(*(_QWORD *)&this[33].LockCount + 40LL))(&this[33].LockCount);
        i;
        i = *(_QWORD *)(i + 8) )
  {
    v5 = *(_QWORD *)(i + 16);
    if ( v5 )
    {
      for ( j = 0; j != 200; ++j )
      {
        v7 = 32 * j;
        *(_QWORD *)(v7 + v5 + 24) = this[35].DebugInfo->ProcessLocksList.Flink;
      }
    }
  }
  LeaveCriticalSection(this + 34);
  ThreadId = 0;
  v8 = CreateThread(0, 0, FreeWDMHandle, this, 0, &ThreadId);
  *(_QWORD *)&this[35].LockCount = v8;
  return v8 == 0 ? 0x80004005 : 0;
}

```

## disassembly

```asm
0x18001f9ac  mov     [rsp+arg_8], rbx
0x18001f9b1  push    rdi
0x18001f9b2  sub     rsp, 30h
0x18001f9b6  mov     edx, [rcx+58Ch]
0x18001f9bc  mov     rbx, rcx
0x18001f9bf  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001f9c6  mov     eax, 8
0x18001f9cb  mul     rdx
0x18001f9ce  cmovb   rax, rcx
0x18001f9d2  mov     rcx, rax; unsigned __int64
0x18001f9d5  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001f9da  mov     [rbx+578h], rax
0x18001f9e1  test    rax, rax
0x18001f9e4  jnz     short loc_18001F9F0
0x18001f9e6  mov     eax, 8007000Eh
0x18001f9eb  jmp     loc_18001FB5B
0x18001f9f0  xor     r9d, r9d; lpName
0x18001f9f3  xor     r8d, r8d; bInitialState
0x18001f9f6  xor     ecx, ecx; lpEventAttributes
0x18001f9f8  lea     edx, [r9+1]; bManualReset
0x18001f9fc  call    cs:__imp_CreateEventA
0x18001fa02  mov     rcx, [rbx+578h]
0x18001fa09  mov     [rcx], rax
0x18001fa0c  mov     rax, [rbx+578h]
0x18001fa13  cmp     qword ptr [rax], 0
0x18001fa17  jz      loc_18001FB56
0x18001fa1d  inc     dword ptr [rbx+588h]
0x18001fa23  cmp     dword ptr [rbx+58Ch], 2
0x18001fa2a  jb      loc_18001FB56
0x18001fa30  xor     r9d, r9d; lpName
0x18001fa33  xor     r8d, r8d; bInitialState
0x18001fa36  xor     ecx, ecx; lpEventAttributes
0x18001fa38  lea     edx, [r9+1]; bManualReset
0x18001fa3c  call    cs:__imp_CreateEventA
0x18001fa42  mov     rcx, [rbx+578h]
0x18001fa49  mov     [rcx+8], rax
0x18001fa4d  mov     rax, [rbx+578h]
0x18001fa54  cmp     qword ptr [rax+8], 0
0x18001fa59  jz      loc_18001FB56
0x18001fa5f  inc     dword ptr [rbx+588h]
0x18001fa65  cmp     dword ptr [rbx+58Ch], 3
0x18001fa6c  jb      loc_18001FB56
0x18001fa72  xor     r9d, r9d; lpName
0x18001fa75  xor     r8d, r8d; bInitialState
0x18001fa78  xor     ecx, ecx; lpEventAttributes
0x18001fa7a  lea     edx, [r9+1]; bManualReset
0x18001fa7e  call    cs:__imp_CreateEventA
0x18001fa84  mov     rcx, [rbx+578h]
0x18001fa8b  mov     [rcx+10h], rax
0x18001fa8f  mov     rax, [rbx+578h]
0x18001fa96  cmp     qword ptr [rax+10h], 0
0x18001fa9b  jz      loc_18001FB56
0x18001faa1  inc     dword ptr [rbx+588h]
0x18001faa7  lea     rdi, [rbx+550h]
0x18001faae  mov     rcx, rdi; lpCriticalSection
0x18001fab1  call    cs:__imp_EnterCriticalSection
0x18001fab7  lea     rcx, [rbx+530h]
0x18001fabe  mov     rax, [rcx]
0x18001fac1  mov     rax, [rax+28h]
0x18001fac5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001faca  mov     r8, rax
0x18001facd  test    rax, rax
0x18001fad0  jz      short loc_18001FB0A
0x18001fad2  mov     r10, [r8+10h]
0x18001fad6  test    r10, r10
0x18001fad9  jz      short loc_18001FB01
0x18001fadb  xor     r9d, r9d
0x18001fade  mov     rax, [rbx+578h]
0x18001fae5  mov     rdx, r9
0x18001fae8  shl     rdx, 5
0x18001faec  inc     r9
0x18001faef  mov     rax, [rax+10h]
0x18001faf3  mov     [rdx+r10+18h], rax
0x18001faf8  cmp     r9, 0C8h
0x18001faff  jnz     short loc_18001FADE
0x18001fb01  mov     r8, [r8+8]
0x18001fb05  test    r8, r8
0x18001fb08  jnz     short loc_18001FAD2
0x18001fb0a  mov     rcx, rdi; lpCriticalSection
0x18001fb0d  call    cs:__imp_LeaveCriticalSection
0x18001fb13  lea     rax, [rsp+38h+ThreadId]
0x18001fb18  mov     [rsp+38h+ThreadId], 0
0x18001fb20  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x18001fb25  lea     r8, ?FreeWDMHandle@@YAKPEAX@Z; lpStartAddress
0x18001fb2c  mov     r9, rbx; lpParameter
0x18001fb2f  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x18001fb37  xor     edx, edx; dwStackSize
0x18001fb39  xor     ecx, ecx; lpThreadAttributes
0x18001fb3b  call    cs:__imp_CreateThread
0x18001fb41  mov     [rbx+580h], rax
0x18001fb48  neg     rax
0x18001fb4b  sbb     eax, eax
0x18001fb4d  not     eax
0x18001fb4f  and     eax, 80004005h
0x18001fb54  jmp     short loc_18001FB5B
0x18001fb56  mov     eax, 80004005h
0x18001fb5b  mov     rbx, [rsp+38h+arg_8]
0x18001fb60  add     rsp, 30h
0x18001fb64  pop     rdi
0x18001fb65  retn
```
