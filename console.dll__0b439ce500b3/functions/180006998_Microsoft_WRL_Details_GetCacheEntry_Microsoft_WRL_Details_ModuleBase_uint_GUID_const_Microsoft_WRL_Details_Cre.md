# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x180006998`
- end: `0x180006b56`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `446`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *__hidden this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, PVOID Ptr, struct IUnknown **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800067e0`

## callees

- `0x180006998`
- `0x180006bc8`
- `0x18001a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006b00`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006b00`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800069ec`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800069ec`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180006a39`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180006a54`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180006a39`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180006a54`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180006a04`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180006ad5`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180006a04`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180006ad5`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180006ac0`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180006ac0`

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
  __int64 v14; // rax
  void *v15; // rcx
  PVOID v16; // rbx
  PSRWLOCK SRWLock; // [rsp+88h] [rbp+20h] BYREF

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
    v14 = (*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 56LL))(this);
    Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, v14);
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
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
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
0x180006998  mov     rax, rsp
0x18000699b  push    rbx
0x18000699c  push    rbp
0x18000699d  push    rsi
0x18000699e  push    rdi
0x18000699f  push    r14
0x1800069a1  push    r15
0x1800069a3  sub     rsp, 38h
0x1800069a7  mov     rdi, r9
0x1800069aa  mov     r15, r8
0x1800069ad  mov     rbp, rdx
0x1800069b0  mov     rsi, rcx
0x1800069b3  mov     r14, [rsp+68h+Ptr]
0x1800069bb  mov     qword ptr [r14], 0
0x1800069c2  mov     qword ptr [rax+28h], 0
0x1800069ca  mov     rax, [r9+18h]
0x1800069ce  mov     r10, [rax]
0x1800069d1  test    r10, r10
0x1800069d4  jz      loc_180006A60
0x1800069da  mov     rax, [rcx]
0x1800069dd  mov     rax, [rax+38h]
0x1800069e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069e6  mov     rbx, rax
0x1800069e9  mov     rcx, rax; SRWLock
0x1800069ec  call    cs:__imp_AcquireSRWLockShared
0x1800069f3  nop     dword ptr [rax+rax+00h]
0x1800069f8  mov     rcx, [rdi+18h]
0x1800069fc  mov     rcx, [rcx]; Ptr
0x1800069ff  test    rcx, rcx
0x180006a02  jz      short loc_180006A4C
0x180006a04  call    cs:__imp_DecodePointer
0x180006a0b  nop     dword ptr [rax+rax+00h]
0x180006a10  mov     r9, rax
0x180006a13  mov     [rsp+68h+Ptr], rax
0x180006a1b  mov     rcx, [rax]
0x180006a1e  mov     rax, [rcx]
0x180006a21  mov     r8, r14
0x180006a24  mov     rdx, r15
0x180006a27  mov     rcx, r9
0x180006a2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a2f  mov     edi, eax
0x180006a31  test    rbx, rbx
0x180006a34  jz      short loc_180006A45
0x180006a36  mov     rcx, rbx; SRWLock
0x180006a39  call    cs:__imp_ReleaseSRWLockShared
0x180006a40  nop     dword ptr [rax+rax+00h]
0x180006a45  mov     eax, edi
0x180006a47  jmp     loc_180006B48
0x180006a4c  test    rbx, rbx
0x180006a4f  jz      short loc_180006A60
0x180006a51  mov     rcx, rbx; SRWLock
0x180006a54  call    cs:__imp_ReleaseSRWLockShared
0x180006a5b  nop     dword ptr [rax+rax+00h]
0x180006a60  lea     r9, [rsp+68h+Ptr]
0x180006a68  mov     r8, r15
0x180006a6b  mov     rdx, rdi
0x180006a6e  mov     rcx, rbp
0x180006a71  mov     rax, [rdi]
0x180006a74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a79  test    eax, eax
0x180006a7b  js      loc_180006B48
0x180006a81  test    byte ptr [rbp+0], 4
0x180006a85  jnz     loc_180006B3B
0x180006a8b  mov     rax, [rsi]
0x180006a8e  mov     rcx, rsi
0x180006a91  mov     rax, [rax+38h]
0x180006a95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a9a  mov     rdx, rax
0x180006a9d  lea     rcx, [rsp+68h+SRWLock]
0x180006aa5  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x180006aaa  mov     rax, [rdi+18h]
0x180006aae  mov     rcx, [rax]; Ptr
0x180006ab1  test    rcx, rcx
0x180006ab4  jnz     short loc_180006AD5
0x180006ab6  xor     ebx, ebx
0x180006ab8  mov     rcx, [rsp+68h+Ptr]; Ptr
0x180006ac0  call    cs:__imp_EncodePointer
0x180006ac7  nop     dword ptr [rax+rax+00h]
0x180006acc  mov     rcx, [rdi+18h]
0x180006ad0  mov     [rcx], rax
0x180006ad3  jmp     short loc_180006AF3
0x180006ad5  call    cs:__imp_DecodePointer
0x180006adc  nop     dword ptr [rax+rax+00h]
0x180006ae1  mov     rbx, rax
0x180006ae4  mov     rcx, [rax]
0x180006ae7  mov     rax, [rcx+8]
0x180006aeb  mov     rcx, rbx
0x180006aee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006af3  mov     rcx, [rsp+68h+SRWLock]; SRWLock
0x180006afb  test    rcx, rcx
0x180006afe  jz      short loc_180006B0C
0x180006b00  call    cs:__imp_ReleaseSRWLockExclusive
0x180006b07  nop     dword ptr [rax+rax+00h]
0x180006b0c  test    rbx, rbx
0x180006b0f  jz      short loc_180006B3B
0x180006b11  mov     rcx, [rsp+68h+Ptr]
0x180006b19  mov     rax, [rcx]
0x180006b1c  mov     rax, [rax+10h]
0x180006b20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b25  mov     rcx, [rsp+68h+Ptr]
0x180006b2d  mov     rax, [rcx]
0x180006b30  mov     rax, [rax+10h]
0x180006b34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b39  jmp     short loc_180006B43
0x180006b3b  mov     rbx, [rsp+68h+Ptr]
0x180006b43  mov     [r14], rbx
0x180006b46  xor     eax, eax
0x180006b48  add     rsp, 38h
0x180006b4c  pop     r15
0x180006b4e  pop     r14
0x180006b50  pop     rdi
0x180006b51  pop     rsi
0x180006b52  pop     rbp
0x180006b53  pop     rbx
0x180006b54  retn
```
