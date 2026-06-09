# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x18000a4b0`
- end: `0x18000a63f`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `399`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, _QWORD *Ptr)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180008778`

## callees

- `0x18000a4b0`
- `0x18000aa34`
- `0x18001c010`

## import_xrefs

- `KERNEL32!EncodePointer` at `0x18000a5bc`
- `KERNEL32!EncodePointer` at `0x18000a5bc`
- `KERNEL32!DecodePointer` at `0x18000a512`
- `KERNEL32!DecodePointer` at `0x18000a5cb`
- `KERNEL32!DecodePointer` at `0x18000a512`
- `KERNEL32!DecodePointer` at `0x18000a5cb`
- `KERNEL32!AcquireSRWLockShared` at `0x18000a500`
- `KERNEL32!AcquireSRWLockShared` at `0x18000a500`
- `KERNEL32!ReleaseSRWLockShared` at `0x18000a541`
- `KERNEL32!ReleaseSRWLockShared` at `0x18000a556`
- `KERNEL32!ReleaseSRWLockShared` at `0x18000a541`
- `KERNEL32!ReleaseSRWLockShared` at `0x18000a556`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000a5f0`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000a5f0`

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
0x18000a4b0  mov     rax, rsp
0x18000a4b3  push    rbx
0x18000a4b4  push    rbp
0x18000a4b5  push    rsi
0x18000a4b6  push    rdi
0x18000a4b7  push    r14
0x18000a4b9  push    r15
0x18000a4bb  sub     rsp, 38h
0x18000a4bf  mov     rdi, r9
0x18000a4c2  mov     r15, r8
0x18000a4c5  mov     rbp, rdx
0x18000a4c8  mov     rsi, rcx
0x18000a4cb  mov     r14, [rsp+68h+Ptr]
0x18000a4d3  mov     qword ptr [r14], 0
0x18000a4da  mov     qword ptr [rax+28h], 0
0x18000a4e2  mov     rax, [r9+18h]
0x18000a4e6  mov     r10, [rax]
0x18000a4e9  test    r10, r10
0x18000a4ec  jz      short loc_18000A55C
0x18000a4ee  mov     rax, [rcx]
0x18000a4f1  mov     rax, [rax+38h]
0x18000a4f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4fa  mov     rbx, rax
0x18000a4fd  mov     rcx, rax; SRWLock
0x18000a500  call    cs:__imp_AcquireSRWLockShared
0x18000a506  mov     rcx, [rdi+18h]
0x18000a50a  mov     rcx, [rcx]; Ptr
0x18000a50d  test    rcx, rcx
0x18000a510  jz      short loc_18000A54E
0x18000a512  call    cs:__imp_DecodePointer
0x18000a518  mov     r9, rax
0x18000a51b  mov     [rsp+68h+Ptr], rax
0x18000a523  mov     rcx, [rax]
0x18000a526  mov     rax, [rcx]
0x18000a529  mov     r8, r14
0x18000a52c  mov     rdx, r15
0x18000a52f  mov     rcx, r9
0x18000a532  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a537  mov     edi, eax
0x18000a539  test    rbx, rbx
0x18000a53c  jz      short loc_18000A547
0x18000a53e  mov     rcx, rbx; SRWLock
0x18000a541  call    cs:__imp_ReleaseSRWLockShared
0x18000a547  mov     eax, edi
0x18000a549  jmp     loc_18000A632
0x18000a54e  test    rbx, rbx
0x18000a551  jz      short loc_18000A55C
0x18000a553  mov     rcx, rbx; SRWLock
0x18000a556  call    cs:__imp_ReleaseSRWLockShared
0x18000a55c  lea     r9, [rsp+68h+Ptr]
0x18000a564  mov     r8, r15
0x18000a567  mov     rdx, rdi
0x18000a56a  mov     rcx, rbp
0x18000a56d  mov     rax, [rdi]
0x18000a570  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a575  test    eax, eax
0x18000a577  js      loc_18000A632
0x18000a57d  test    byte ptr [rbp+0], 4
0x18000a581  jnz     loc_18000A625
0x18000a587  mov     rax, [rsi]
0x18000a58a  mov     rcx, rsi
0x18000a58d  mov     rax, [rax+38h]
0x18000a591  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a596  mov     rdx, rax
0x18000a599  lea     rcx, [rsp+68h+SRWLock]
0x18000a5a1  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18000a5a6  mov     rax, [rdi+18h]
0x18000a5aa  mov     rcx, [rax]; Ptr
0x18000a5ad  test    rcx, rcx
0x18000a5b0  jnz     short loc_18000A5CB
0x18000a5b2  xor     ebx, ebx
0x18000a5b4  mov     rcx, [rsp+68h+Ptr]; Ptr
0x18000a5bc  call    cs:__imp_EncodePointer
0x18000a5c2  mov     rcx, [rdi+18h]
0x18000a5c6  mov     [rcx], rax
0x18000a5c9  jmp     short loc_18000A5E3
0x18000a5cb  call    cs:__imp_DecodePointer
0x18000a5d1  mov     rbx, rax
0x18000a5d4  mov     rcx, [rax]
0x18000a5d7  mov     rax, [rcx+8]
0x18000a5db  mov     rcx, rbx
0x18000a5de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5e3  mov     rcx, [rsp+68h+SRWLock]; SRWLock
0x18000a5eb  test    rcx, rcx
0x18000a5ee  jz      short loc_18000A5F6
0x18000a5f0  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a5f6  test    rbx, rbx
0x18000a5f9  jz      short loc_18000A625
0x18000a5fb  mov     rcx, [rsp+68h+Ptr]
0x18000a603  mov     rax, [rcx]
0x18000a606  mov     rax, [rax+10h]
0x18000a60a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a60f  mov     rcx, [rsp+68h+Ptr]
0x18000a617  mov     rax, [rcx]
0x18000a61a  mov     rax, [rax+10h]
0x18000a61e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a623  jmp     short loc_18000A62D
0x18000a625  mov     rbx, [rsp+68h+Ptr]
0x18000a62d  mov     [r14], rbx
0x18000a630  xor     eax, eax
0x18000a632  add     rsp, 38h
0x18000a636  pop     r15
0x18000a638  pop     r14
0x18000a63a  pop     rdi
0x18000a63b  pop     rsi
0x18000a63c  pop     rbp
0x18000a63d  pop     rbx
0x18000a63e  retn
```
