# CWMWriter::EndOfStreamFromPin(int)

- ea: `0x18000f738`
- end: `0x18000f86d`
- name: `?EndOfStreamFromPin@CWMWriter@@QEAAJH@Z`
- size: `309`
- prototype: `__int64 __fastcall(CWMWriter *__hidden this, int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180013fc0`

## callees

- `0x18000f738`
- `0x18001f010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000f756`
- `KERNEL32!EnterCriticalSection` at `0x18000f7ca`
- `KERNEL32!EnterCriticalSection` at `0x18000f756`
- `KERNEL32!EnterCriticalSection` at `0x18000f7ca`
- `KERNEL32!LeaveCriticalSection` at `0x18000f838`
- `KERNEL32!LeaveCriticalSection` at `0x18000f855`
- `KERNEL32!LeaveCriticalSection` at `0x18000f838`
- `KERNEL32!LeaveCriticalSection` at `0x18000f855`
- `KERNEL32!SetEvent` at `0x18000f84c`
- `KERNEL32!SetEvent` at `0x18000f84c`

## pseudocode

```c
__int64 __fastcall CWMWriter::EndOfStreamFromPin(struct _RTL_CRITICAL_SECTION *this, int a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  __int64 v5; // rax
  int v6; // r8d
  __int64 v7; // rcx
  __int64 v8; // r10
  __int64 v9; // r9
  __int64 v10; // rax
  HANDLE LockSemaphore; // r10

  v2 = this + 6;
  EnterCriticalSection(this + 6);
  v5 = *(_QWORD *)&this[10].LockCount;
  v6 = 0;
  v7 = 0;
  v8 = 0x7FFFFFFFFFFFFFFFLL;
  if ( v5 )
  {
    do
    {
      v9 = *(_QWORD *)(v5 + 8);
      v10 = *(_QWORD *)(v5 + 16);
      if ( *(_DWORD *)(v10 + 428) )
      {
        ++v6;
      }
      else if ( *(_QWORD *)(v10 + 480) < v8 )
      {
        v7 = v10;
        v8 = *(_QWORD *)(v10 + 480);
      }
      if ( *(_DWORD *)(v10 + 396) == a2 && *(_DWORD *)(v10 + 424) == 1 )
        --HIDWORD(this[13].DebugInfo);
      v5 = v9;
    }
    while ( v9 );
  }
  if ( v6 == HIDWORD(this[12].SpinCount) )
  {
    EnterCriticalSection(v2);
    if ( !HIDWORD(this[7].OwningThread) && LODWORD(this[1].DebugInfo) == 2 )
    {
      LockSemaphore = this[2].LockSemaphore;
      if ( LODWORD(this[5].LockSemaphore) )
      {
        if ( LockSemaphore )
          (*(void (__fastcall **)(HANDLE, __int64, _QWORD, unsigned __int64))(*(_QWORD *)LockSemaphore + 24LL))(
            LockSemaphore,
            86,
            0,
            (unsigned __int64)&this->LockSemaphore & -(__int64)(this != 0));
      }
      else if ( LockSemaphore )
      {
        (*(void (__fastcall **)(HANDLE, __int64, _QWORD, unsigned __int64))(*(_QWORD *)LockSemaphore + 24LL))(
          LockSemaphore,
          1,
          0,
          (unsigned __int64)&this->LockSemaphore & -(__int64)(this != 0));
      }
    }
    LeaveCriticalSection(v2);
  }
  else if ( v7 )
  {
    SetEvent(*(HANDLE *)(v7 + 336));
  }
  LeaveCriticalSection(v2);
  return 0;
}

```

## disassembly

```asm
0x18000f738  mov     [rsp+arg_0], rbx
0x18000f73d  mov     [rsp+arg_8], rsi
0x18000f742  push    rdi
0x18000f743  sub     rsp, 30h
0x18000f747  lea     rbx, [rcx+0F0h]
0x18000f74e  mov     rdi, rcx
0x18000f751  mov     rcx, rbx; lpCriticalSection
0x18000f754  mov     esi, edx
0x18000f756  call    cs:__imp_EnterCriticalSection
0x18000f75c  mov     rax, [rdi+198h]
0x18000f763  xor     r8d, r8d
0x18000f766  xor     ecx, ecx
0x18000f768  mov     r10, 7FFFFFFFFFFFFFFFh
0x18000f772  test    rax, rax
0x18000f775  jz      short loc_18000F7BE
0x18000f777  mov     r9, [rax+8]
0x18000f77b  mov     rax, [rax+10h]
0x18000f77f  cmp     dword ptr [rax+1ACh], 0
0x18000f786  jz      short loc_18000F78D
0x18000f788  inc     r8d
0x18000f78b  jmp     short loc_18000F79F
0x18000f78d  mov     rdx, [rax+1E0h]
0x18000f794  cmp     rdx, r10
0x18000f797  jge     short loc_18000F79F
0x18000f799  mov     rcx, rax
0x18000f79c  mov     r10, rdx
0x18000f79f  cmp     [rax+18Ch], esi
0x18000f7a5  jnz     short loc_18000F7B6
0x18000f7a7  cmp     dword ptr [rax+1A8h], 1
0x18000f7ae  jnz     short loc_18000F7B6
0x18000f7b0  dec     dword ptr [rdi+20Ch]
0x18000f7b6  mov     rax, r9
0x18000f7b9  test    r9, r9
0x18000f7bc  jnz     short loc_18000F777
0x18000f7be  cmp     r8d, [rdi+204h]
0x18000f7c5  jnz     short loc_18000F840
0x18000f7c7  mov     rcx, rbx; lpCriticalSection
0x18000f7ca  call    cs:__imp_EnterCriticalSection
0x18000f7d0  cmp     dword ptr [rdi+12Ch], 0
0x18000f7d7  jnz     short loc_18000F835
0x18000f7d9  cmp     dword ptr [rdi+28h], 2
0x18000f7dd  jnz     short loc_18000F835
0x18000f7df  cmp     dword ptr [rdi+0E0h], 0
0x18000f7e6  mov     r10, [rdi+68h]
0x18000f7ea  jz      short loc_18000F80C
0x18000f7ec  lea     rax, [rdi+18h]
0x18000f7f0  neg     rdi
0x18000f7f3  sbb     r9, r9
0x18000f7f6  and     r9, rax
0x18000f7f9  test    r10, r10
0x18000f7fc  jz      short loc_18000F835
0x18000f7fe  mov     rax, [r10]
0x18000f801  mov     edx, 56h ; 'V'
0x18000f806  mov     rax, [rax+18h]
0x18000f80a  jmp     short loc_18000F82A
0x18000f80c  test    r10, r10
0x18000f80f  jz      short loc_18000F835
0x18000f811  mov     rcx, [r10]
0x18000f814  lea     rax, [rdi+18h]
0x18000f818  neg     rdi
0x18000f81b  mov     edx, 1
0x18000f820  sbb     r9, r9
0x18000f823  and     r9, rax
0x18000f826  mov     rax, [rcx+18h]
0x18000f82a  xor     r8d, r8d
0x18000f82d  mov     rcx, r10
0x18000f830  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f835  mov     rcx, rbx; lpCriticalSection
0x18000f838  call    cs:__imp_LeaveCriticalSection
0x18000f83e  jmp     short loc_18000F852
0x18000f840  test    rcx, rcx
0x18000f843  jz      short loc_18000F852
0x18000f845  mov     rcx, [rcx+150h]; hEvent
0x18000f84c  call    cs:__imp_SetEvent
0x18000f852  mov     rcx, rbx; lpCriticalSection
0x18000f855  call    cs:__imp_LeaveCriticalSection
0x18000f85b  mov     rbx, [rsp+38h+arg_0]
0x18000f860  xor     eax, eax
0x18000f862  mov     rsi, [rsp+38h+arg_8]
0x18000f867  add     rsp, 30h
0x18000f86b  pop     rdi
0x18000f86c  retn
```
