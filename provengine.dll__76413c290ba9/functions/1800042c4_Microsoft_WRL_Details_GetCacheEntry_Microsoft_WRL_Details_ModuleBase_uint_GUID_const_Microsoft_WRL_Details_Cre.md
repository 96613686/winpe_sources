# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x1800042c4`
- end: `0x18000444a`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `390`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, _QWORD *Ptr)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005e20`
- `0x180005fe0`

## callees

- `0x1800042c4`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1800043cc`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1800043cc`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180004326`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800043db`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180004326`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800043db`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800043b0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800043b0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180004355`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000436a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180004355`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000436a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180004314`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180004314`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800043fb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800043fb`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Microsoft::WRL::Details::GetCacheEntry(
        Microsoft::WRL::Details *this,
        struct Microsoft::WRL::Details::ModuleBase *a2,
        unsigned int *a3,
        const struct _GUID *a4,
        _QWORD *Ptr)
{
  _QWORD *v9; // r14
  RTL_SRWLOCK *v10; // rbx
  void *v11; // rcx
  unsigned int v12; // edi
  __int64 result; // rax
  RTL_SRWLOCK *v14; // rsi
  void *v15; // rcx
  PVOID v16; // rbx

  v9 = Ptr;
  *Ptr = 0;
  Ptr = 0;
  if ( **(_QWORD **)a4[1].Data4 )
  {
    v10 = (RTL_SRWLOCK *)(*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 56LL))(this);
    AcquireSRWLockShared(v10);
    v11 = **(void ***)a4[1].Data4;
    if ( v11 )
    {
      Ptr = DecodePointer(v11);
      v12 = (*(__int64 (__fastcall **)(_QWORD *, unsigned int *, _QWORD *))*Ptr)(Ptr, a3, v9);
      if ( v10 )
        ReleaseSRWLockShared(v10);
      return v12;
    }
    if ( v10 )
      ReleaseSRWLockShared(v10);
  }
  result = (*(__int64 (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *, const struct _GUID *, unsigned int *, _QWORD **))&a4->Data1)(
             a2,
             a4,
             a3,
             &Ptr);
  if ( (int)result >= 0 )
  {
    if ( (*(_BYTE *)a2 & 4) != 0 )
      goto LABEL_17;
    v14 = (RTL_SRWLOCK *)(*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 56LL))(this);
    AcquireSRWLockExclusive(v14);
    v15 = **(void ***)a4[1].Data4;
    if ( v15 )
    {
      v16 = DecodePointer(v15);
      (*(void (__fastcall **)(PVOID))(*(_QWORD *)v16 + 8LL))(v16);
    }
    else
    {
      v16 = 0;
      **(_QWORD **)a4[1].Data4 = EncodePointer(Ptr);
    }
    if ( v14 )
      ReleaseSRWLockExclusive(v14);
    if ( !v16 )
    {
LABEL_17:
      v16 = Ptr;
    }
    else
    {
      (*(void (__fastcall **)(_QWORD *))(*Ptr + 16LL))(Ptr);
      (*(void (__fastcall **)(_QWORD *))(*Ptr + 16LL))(Ptr);
    }
    *v9 = v16;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800042c4  mov     rax, rsp
0x1800042c7  push    rbx
0x1800042c8  push    rbp
0x1800042c9  push    rsi
0x1800042ca  push    rdi
0x1800042cb  push    r14
0x1800042cd  push    r15
0x1800042cf  sub     rsp, 38h
0x1800042d3  mov     rdi, r9
0x1800042d6  mov     r15, r8
0x1800042d9  mov     rbp, rdx
0x1800042dc  mov     rsi, rcx
0x1800042df  mov     r14, [rsp+68h+Ptr]
0x1800042e7  mov     qword ptr [r14], 0
0x1800042ee  mov     qword ptr [rax+28h], 0
0x1800042f6  mov     rax, [r9+18h]
0x1800042fa  mov     r10, [rax]
0x1800042fd  test    r10, r10
0x180004300  jz      short loc_180004370
0x180004302  mov     rax, [rcx]
0x180004305  mov     rax, [rax+38h]
0x180004309  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000430e  mov     rbx, rax
0x180004311  mov     rcx, rax; SRWLock
0x180004314  call    cs:__imp_AcquireSRWLockShared
0x18000431a  mov     rcx, [rdi+18h]
0x18000431e  mov     rcx, [rcx]; Ptr
0x180004321  test    rcx, rcx
0x180004324  jz      short loc_180004362
0x180004326  call    cs:__imp_DecodePointer
0x18000432c  mov     r9, rax
0x18000432f  mov     [rsp+68h+Ptr], rax
0x180004337  mov     rcx, [rax]
0x18000433a  mov     rax, [rcx]
0x18000433d  mov     r8, r14
0x180004340  mov     rdx, r15
0x180004343  mov     rcx, r9
0x180004346  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000434b  mov     edi, eax
0x18000434d  test    rbx, rbx
0x180004350  jz      short loc_18000435B
0x180004352  mov     rcx, rbx; SRWLock
0x180004355  call    cs:__imp_ReleaseSRWLockShared
0x18000435b  mov     eax, edi
0x18000435d  jmp     loc_18000443D
0x180004362  test    rbx, rbx
0x180004365  jz      short loc_180004370
0x180004367  mov     rcx, rbx; SRWLock
0x18000436a  call    cs:__imp_ReleaseSRWLockShared
0x180004370  lea     r9, [rsp+68h+Ptr]
0x180004378  mov     r8, r15
0x18000437b  mov     rdx, rdi
0x18000437e  mov     rcx, rbp
0x180004381  mov     rax, [rdi]
0x180004384  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004389  test    eax, eax
0x18000438b  js      loc_18000443D
0x180004391  test    byte ptr [rbp+0], 4
0x180004395  jnz     loc_180004430
0x18000439b  mov     rax, [rsi]
0x18000439e  mov     rcx, rsi
0x1800043a1  mov     rax, [rax+38h]
0x1800043a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043aa  mov     rsi, rax
0x1800043ad  mov     rcx, rax; SRWLock
0x1800043b0  call    cs:__imp_AcquireSRWLockExclusive
0x1800043b6  mov     rcx, [rdi+18h]
0x1800043ba  mov     rcx, [rcx]; Ptr
0x1800043bd  test    rcx, rcx
0x1800043c0  jnz     short loc_1800043DB
0x1800043c2  xor     ebx, ebx
0x1800043c4  mov     rcx, [rsp+68h+Ptr]; Ptr
0x1800043cc  call    cs:__imp_EncodePointer
0x1800043d2  mov     rcx, [rdi+18h]
0x1800043d6  mov     [rcx], rax
0x1800043d9  jmp     short loc_1800043F3
0x1800043db  call    cs:__imp_DecodePointer
0x1800043e1  mov     rbx, rax
0x1800043e4  mov     rcx, [rax]
0x1800043e7  mov     rax, [rcx+8]
0x1800043eb  mov     rcx, rbx
0x1800043ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043f3  test    rsi, rsi
0x1800043f6  jz      short loc_180004401
0x1800043f8  mov     rcx, rsi; SRWLock
0x1800043fb  call    cs:__imp_ReleaseSRWLockExclusive
0x180004401  test    rbx, rbx
0x180004404  jz      short loc_180004430
0x180004406  mov     rcx, [rsp+68h+Ptr]
0x18000440e  mov     rax, [rcx]
0x180004411  mov     rax, [rax+10h]
0x180004415  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000441a  mov     rcx, [rsp+68h+Ptr]
0x180004422  mov     rax, [rcx]
0x180004425  mov     rax, [rax+10h]
0x180004429  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000442e  jmp     short loc_180004438
0x180004430  mov     rbx, [rsp+68h+Ptr]
0x180004438  mov     [r14], rbx
0x18000443b  xor     eax, eax
0x18000443d  add     rsp, 38h
0x180004441  pop     r15
0x180004443  pop     r14
0x180004445  pop     rdi
0x180004446  pop     rsi
0x180004447  pop     rbp
0x180004448  pop     rbx
0x180004449  retn
```
