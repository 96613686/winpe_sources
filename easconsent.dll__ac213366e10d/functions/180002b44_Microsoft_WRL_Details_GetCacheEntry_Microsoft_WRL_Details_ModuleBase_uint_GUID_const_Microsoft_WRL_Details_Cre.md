# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x180002b44`
- end: `0x180002cca`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `390`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, _QWORD *Ptr)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002f20`

## callees

- `0x180002b44`
- `0x180004010`

## import_xrefs

- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180002ba6`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180002c5b`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180002ba6`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180002c5b`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180002c4c`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180002c4c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180002b94`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180002b94`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180002bd5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180002bea`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180002bd5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180002bea`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002c30`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002c30`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180002c7b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180002c7b`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::GetCacheEntry(
        Microsoft::WRL::Details *this,
        struct Microsoft::WRL::Details::ModuleBase *a2,
        unsigned int *a3,
        const struct _GUID *a4,
        _QWORD *Ptr)
{
  _QWORD *v5; // r14
  RTL_SRWLOCK *v10; // rbx
  void *v11; // rcx
  unsigned int v12; // edi
  __int64 result; // rax
  RTL_SRWLOCK *v14; // rsi
  void *v15; // rcx
  PVOID v16; // rbx

  v5 = Ptr;
  Ptr = 0;
  *v5 = 0;
  if ( **(_QWORD **)a4[1].Data4 )
  {
    v10 = (RTL_SRWLOCK *)(*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 56LL))(this);
    AcquireSRWLockShared(v10);
    v11 = **(void ***)a4[1].Data4;
    if ( v11 )
    {
      Ptr = DecodePointer(v11);
      v12 = (*(__int64 (__fastcall **)(_QWORD *, unsigned int *, _QWORD *))*Ptr)(Ptr, a3, v5);
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
    *v5 = v16;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180002b44  mov     rax, rsp
0x180002b47  push    rbx
0x180002b48  push    rbp
0x180002b49  push    rsi
0x180002b4a  push    rdi
0x180002b4b  push    r14
0x180002b4d  push    r15
0x180002b4f  sub     rsp, 38h
0x180002b53  mov     r14, [rsp+68h+Ptr]
0x180002b5b  mov     rdi, r9
0x180002b5e  mov     qword ptr [rax+28h], 0
0x180002b66  mov     r15, r8
0x180002b69  mov     rbp, rdx
0x180002b6c  mov     rsi, rcx
0x180002b6f  mov     qword ptr [r14], 0
0x180002b76  mov     rax, [r9+18h]
0x180002b7a  mov     r10, [rax]
0x180002b7d  test    r10, r10
0x180002b80  jz      short loc_180002BF0
0x180002b82  mov     rax, [rcx]
0x180002b85  mov     rax, [rax+38h]
0x180002b89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b8e  mov     rcx, rax; SRWLock
0x180002b91  mov     rbx, rax
0x180002b94  call    cs:__imp_AcquireSRWLockShared
0x180002b9a  mov     rcx, [rdi+18h]
0x180002b9e  mov     rcx, [rcx]; Ptr
0x180002ba1  test    rcx, rcx
0x180002ba4  jz      short loc_180002BE2
0x180002ba6  call    cs:__imp_DecodePointer
0x180002bac  mov     [rsp+68h+Ptr], rax
0x180002bb4  mov     r8, r14
0x180002bb7  mov     r9, rax
0x180002bba  mov     rdx, r15
0x180002bbd  mov     rcx, [rax]
0x180002bc0  mov     rax, [rcx]
0x180002bc3  mov     rcx, r9
0x180002bc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bcb  mov     edi, eax
0x180002bcd  test    rbx, rbx
0x180002bd0  jz      short loc_180002BDB
0x180002bd2  mov     rcx, rbx; SRWLock
0x180002bd5  call    cs:__imp_ReleaseSRWLockShared
0x180002bdb  mov     eax, edi
0x180002bdd  jmp     loc_180002CBD
0x180002be2  test    rbx, rbx
0x180002be5  jz      short loc_180002BF0
0x180002be7  mov     rcx, rbx; SRWLock
0x180002bea  call    cs:__imp_ReleaseSRWLockShared
0x180002bf0  mov     rax, [rdi]
0x180002bf3  lea     r9, [rsp+68h+Ptr]
0x180002bfb  mov     r8, r15
0x180002bfe  mov     rdx, rdi
0x180002c01  mov     rcx, rbp
0x180002c04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c09  test    eax, eax
0x180002c0b  js      loc_180002CBD
0x180002c11  test    byte ptr [rbp+0], 4
0x180002c15  jnz     loc_180002CB0
0x180002c1b  mov     rax, [rsi]
0x180002c1e  mov     rcx, rsi
0x180002c21  mov     rax, [rax+38h]
0x180002c25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c2a  mov     rcx, rax; SRWLock
0x180002c2d  mov     rsi, rax
0x180002c30  call    cs:__imp_AcquireSRWLockExclusive
0x180002c36  mov     rcx, [rdi+18h]
0x180002c3a  mov     rcx, [rcx]; Ptr
0x180002c3d  test    rcx, rcx
0x180002c40  jnz     short loc_180002C5B
0x180002c42  mov     rcx, [rsp+68h+Ptr]; Ptr
0x180002c4a  xor     ebx, ebx
0x180002c4c  call    cs:__imp_EncodePointer
0x180002c52  mov     rcx, [rdi+18h]
0x180002c56  mov     [rcx], rax
0x180002c59  jmp     short loc_180002C73
0x180002c5b  call    cs:__imp_DecodePointer
0x180002c61  mov     rbx, rax
0x180002c64  mov     rcx, [rax]
0x180002c67  mov     rax, [rcx+8]
0x180002c6b  mov     rcx, rbx
0x180002c6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c73  test    rsi, rsi
0x180002c76  jz      short loc_180002C81
0x180002c78  mov     rcx, rsi; SRWLock
0x180002c7b  call    cs:__imp_ReleaseSRWLockExclusive
0x180002c81  test    rbx, rbx
0x180002c84  jz      short loc_180002CB0
0x180002c86  mov     rcx, [rsp+68h+Ptr]
0x180002c8e  mov     rax, [rcx]
0x180002c91  mov     rax, [rax+10h]
0x180002c95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c9a  mov     rcx, [rsp+68h+Ptr]
0x180002ca2  mov     rax, [rcx]
0x180002ca5  mov     rax, [rax+10h]
0x180002ca9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cae  jmp     short loc_180002CB8
0x180002cb0  mov     rbx, [rsp+68h+Ptr]
0x180002cb8  mov     [r14], rbx
0x180002cbb  xor     eax, eax
0x180002cbd  add     rsp, 38h
0x180002cc1  pop     r15
0x180002cc3  pop     r14
0x180002cc5  pop     rdi
0x180002cc6  pop     rsi
0x180002cc7  pop     rbp
0x180002cc8  pop     rbx
0x180002cc9  retn
```
