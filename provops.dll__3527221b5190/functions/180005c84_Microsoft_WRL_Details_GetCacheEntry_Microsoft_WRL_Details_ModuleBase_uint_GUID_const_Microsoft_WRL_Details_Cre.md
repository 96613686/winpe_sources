# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x180005c84`
- end: `0x180005e0a`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `390`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, _QWORD *Ptr)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008af0`
- `0x180008cb0`

## callees

- `0x180005c84`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005d70`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005d70`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005dbb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005dbb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180005d15`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180005d2a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180005d15`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180005d2a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180005cd4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180005cd4`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180005ce6`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180005d9b`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180005ce6`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180005d9b`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180005d8c`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180005d8c`

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
0x180005c84  mov     rax, rsp
0x180005c87  push    rbx
0x180005c88  push    rbp
0x180005c89  push    rsi
0x180005c8a  push    rdi
0x180005c8b  push    r14
0x180005c8d  push    r15
0x180005c8f  sub     rsp, 38h
0x180005c93  mov     rdi, r9
0x180005c96  mov     r15, r8
0x180005c99  mov     rbp, rdx
0x180005c9c  mov     rsi, rcx
0x180005c9f  mov     r14, [rsp+68h+Ptr]
0x180005ca7  mov     qword ptr [r14], 0
0x180005cae  mov     qword ptr [rax+28h], 0
0x180005cb6  mov     rax, [r9+18h]
0x180005cba  mov     r10, [rax]
0x180005cbd  test    r10, r10
0x180005cc0  jz      short loc_180005D30
0x180005cc2  mov     rax, [rcx]
0x180005cc5  mov     rax, [rax+38h]
0x180005cc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cce  mov     rbx, rax
0x180005cd1  mov     rcx, rax; SRWLock
0x180005cd4  call    cs:__imp_AcquireSRWLockShared
0x180005cda  mov     rcx, [rdi+18h]
0x180005cde  mov     rcx, [rcx]; Ptr
0x180005ce1  test    rcx, rcx
0x180005ce4  jz      short loc_180005D22
0x180005ce6  call    cs:__imp_DecodePointer
0x180005cec  mov     r9, rax
0x180005cef  mov     [rsp+68h+Ptr], rax
0x180005cf7  mov     rcx, [rax]
0x180005cfa  mov     rax, [rcx]
0x180005cfd  mov     r8, r14
0x180005d00  mov     rdx, r15
0x180005d03  mov     rcx, r9
0x180005d06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d0b  mov     edi, eax
0x180005d0d  test    rbx, rbx
0x180005d10  jz      short loc_180005D1B
0x180005d12  mov     rcx, rbx; SRWLock
0x180005d15  call    cs:__imp_ReleaseSRWLockShared
0x180005d1b  mov     eax, edi
0x180005d1d  jmp     loc_180005DFD
0x180005d22  test    rbx, rbx
0x180005d25  jz      short loc_180005D30
0x180005d27  mov     rcx, rbx; SRWLock
0x180005d2a  call    cs:__imp_ReleaseSRWLockShared
0x180005d30  lea     r9, [rsp+68h+Ptr]
0x180005d38  mov     r8, r15
0x180005d3b  mov     rdx, rdi
0x180005d3e  mov     rcx, rbp
0x180005d41  mov     rax, [rdi]
0x180005d44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d49  test    eax, eax
0x180005d4b  js      loc_180005DFD
0x180005d51  test    byte ptr [rbp+0], 4
0x180005d55  jnz     loc_180005DF0
0x180005d5b  mov     rax, [rsi]
0x180005d5e  mov     rcx, rsi
0x180005d61  mov     rax, [rax+38h]
0x180005d65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d6a  mov     rsi, rax
0x180005d6d  mov     rcx, rax; SRWLock
0x180005d70  call    cs:__imp_AcquireSRWLockExclusive
0x180005d76  mov     rcx, [rdi+18h]
0x180005d7a  mov     rcx, [rcx]; Ptr
0x180005d7d  test    rcx, rcx
0x180005d80  jnz     short loc_180005D9B
0x180005d82  xor     ebx, ebx
0x180005d84  mov     rcx, [rsp+68h+Ptr]; Ptr
0x180005d8c  call    cs:__imp_EncodePointer
0x180005d92  mov     rcx, [rdi+18h]
0x180005d96  mov     [rcx], rax
0x180005d99  jmp     short loc_180005DB3
0x180005d9b  call    cs:__imp_DecodePointer
0x180005da1  mov     rbx, rax
0x180005da4  mov     rcx, [rax]
0x180005da7  mov     rax, [rcx+8]
0x180005dab  mov     rcx, rbx
0x180005dae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005db3  test    rsi, rsi
0x180005db6  jz      short loc_180005DC1
0x180005db8  mov     rcx, rsi; SRWLock
0x180005dbb  call    cs:__imp_ReleaseSRWLockExclusive
0x180005dc1  test    rbx, rbx
0x180005dc4  jz      short loc_180005DF0
0x180005dc6  mov     rcx, [rsp+68h+Ptr]
0x180005dce  mov     rax, [rcx]
0x180005dd1  mov     rax, [rax+10h]
0x180005dd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005dda  mov     rcx, [rsp+68h+Ptr]
0x180005de2  mov     rax, [rcx]
0x180005de5  mov     rax, [rax+10h]
0x180005de9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005dee  jmp     short loc_180005DF8
0x180005df0  mov     rbx, [rsp+68h+Ptr]
0x180005df8  mov     [r14], rbx
0x180005dfb  xor     eax, eax
0x180005dfd  add     rsp, 38h
0x180005e01  pop     r15
0x180005e03  pop     r14
0x180005e05  pop     rdi
0x180005e06  pop     rsi
0x180005e07  pop     rbp
0x180005e08  pop     rbx
0x180005e09  retn
```
