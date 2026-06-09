# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x180009b84`
- end: `0x180009d0a`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `390`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, _QWORD *Ptr)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000ae80`

## callees

- `0x180009b84`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180009bd4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180009bd4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180009c15`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180009c2a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180009c15`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180009c2a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009c70`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009c70`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009cbb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009cbb`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180009c8c`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180009c8c`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180009be6`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180009c9b`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180009be6`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180009c9b`

## pseudocode

```c
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
0x180009b84  mov     rax, rsp
0x180009b87  push    rbx
0x180009b88  push    rbp
0x180009b89  push    rsi
0x180009b8a  push    rdi
0x180009b8b  push    r14
0x180009b8d  push    r15
0x180009b8f  sub     rsp, 38h
0x180009b93  mov     rdi, r9
0x180009b96  mov     r15, r8
0x180009b99  mov     rbp, rdx
0x180009b9c  mov     rsi, rcx
0x180009b9f  mov     r14, [rsp+68h+Ptr]
0x180009ba7  mov     qword ptr [r14], 0
0x180009bae  mov     qword ptr [rax+28h], 0
0x180009bb6  mov     rax, [r9+18h]
0x180009bba  mov     r10, [rax]
0x180009bbd  test    r10, r10
0x180009bc0  jz      short loc_180009C30
0x180009bc2  mov     rax, [rcx]
0x180009bc5  mov     rax, [rax+38h]
0x180009bc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009bce  mov     rbx, rax
0x180009bd1  mov     rcx, rax; SRWLock
0x180009bd4  call    cs:__imp_AcquireSRWLockShared
0x180009bda  mov     rcx, [rdi+18h]
0x180009bde  mov     rcx, [rcx]; Ptr
0x180009be1  test    rcx, rcx
0x180009be4  jz      short loc_180009C22
0x180009be6  call    cs:__imp_DecodePointer
0x180009bec  mov     r9, rax
0x180009bef  mov     [rsp+68h+Ptr], rax
0x180009bf7  mov     rcx, [rax]
0x180009bfa  mov     rax, [rcx]
0x180009bfd  mov     r8, r14
0x180009c00  mov     rdx, r15
0x180009c03  mov     rcx, r9
0x180009c06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c0b  mov     edi, eax
0x180009c0d  test    rbx, rbx
0x180009c10  jz      short loc_180009C1B
0x180009c12  mov     rcx, rbx; SRWLock
0x180009c15  call    cs:__imp_ReleaseSRWLockShared
0x180009c1b  mov     eax, edi
0x180009c1d  jmp     loc_180009CFD
0x180009c22  test    rbx, rbx
0x180009c25  jz      short loc_180009C30
0x180009c27  mov     rcx, rbx; SRWLock
0x180009c2a  call    cs:__imp_ReleaseSRWLockShared
0x180009c30  lea     r9, [rsp+68h+Ptr]
0x180009c38  mov     r8, r15
0x180009c3b  mov     rdx, rdi
0x180009c3e  mov     rcx, rbp
0x180009c41  mov     rax, [rdi]
0x180009c44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c49  test    eax, eax
0x180009c4b  js      loc_180009CFD
0x180009c51  test    byte ptr [rbp+0], 4
0x180009c55  jnz     loc_180009CF0
0x180009c5b  mov     rax, [rsi]
0x180009c5e  mov     rcx, rsi
0x180009c61  mov     rax, [rax+38h]
0x180009c65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c6a  mov     rsi, rax
0x180009c6d  mov     rcx, rax; SRWLock
0x180009c70  call    cs:__imp_AcquireSRWLockExclusive
0x180009c76  mov     rcx, [rdi+18h]
0x180009c7a  mov     rcx, [rcx]; Ptr
0x180009c7d  test    rcx, rcx
0x180009c80  jnz     short loc_180009C9B
0x180009c82  xor     ebx, ebx
0x180009c84  mov     rcx, [rsp+68h+Ptr]; Ptr
0x180009c8c  call    cs:__imp_EncodePointer
0x180009c92  mov     rcx, [rdi+18h]
0x180009c96  mov     [rcx], rax
0x180009c99  jmp     short loc_180009CB3
0x180009c9b  call    cs:__imp_DecodePointer
0x180009ca1  mov     rbx, rax
0x180009ca4  mov     rcx, [rax]
0x180009ca7  mov     rax, [rcx+8]
0x180009cab  mov     rcx, rbx
0x180009cae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009cb3  test    rsi, rsi
0x180009cb6  jz      short loc_180009CC1
0x180009cb8  mov     rcx, rsi; SRWLock
0x180009cbb  call    cs:__imp_ReleaseSRWLockExclusive
0x180009cc1  test    rbx, rbx
0x180009cc4  jz      short loc_180009CF0
0x180009cc6  mov     rcx, [rsp+68h+Ptr]
0x180009cce  mov     rax, [rcx]
0x180009cd1  mov     rax, [rax+10h]
0x180009cd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009cda  mov     rcx, [rsp+68h+Ptr]
0x180009ce2  mov     rax, [rcx]
0x180009ce5  mov     rax, [rax+10h]
0x180009ce9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009cee  jmp     short loc_180009CF8
0x180009cf0  mov     rbx, [rsp+68h+Ptr]
0x180009cf8  mov     [r14], rbx
0x180009cfb  xor     eax, eax
0x180009cfd  add     rsp, 38h
0x180009d01  pop     r15
0x180009d03  pop     r14
0x180009d05  pop     rdi
0x180009d06  pop     rsi
0x180009d07  pop     rbp
0x180009d08  pop     rbx
0x180009d09  retn
```
