# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x180015664`
- end: `0x1800157f3`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `399`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *__hidden this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, PVOID Ptr, struct IUnknown **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180015558`

## callees

- `0x180015664`
- `0x180015838`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800156b4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800156b4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800156f5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001570a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800156f5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001570a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800157a4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800157a4`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800156c6`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18001577f`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800156c6`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18001577f`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180015770`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180015770`

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
  __int64 v14; // rax
  void *v15; // rcx
  PVOID v16; // rbx
  PSRWLOCK SRWLock; // [rsp+88h] [rbp+20h] BYREF

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
    *v5 = v16;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180015664  mov     rax, rsp
0x180015667  push    rbx
0x180015668  push    rbp
0x180015669  push    rsi
0x18001566a  push    rdi
0x18001566b  push    r14
0x18001566d  push    r15
0x18001566f  sub     rsp, 38h
0x180015673  mov     r14, [rsp+68h+Ptr]
0x18001567b  mov     rdi, r9
0x18001567e  mov     qword ptr [rax+28h], 0
0x180015686  mov     r15, r8
0x180015689  mov     rbp, rdx
0x18001568c  mov     rsi, rcx
0x18001568f  mov     qword ptr [r14], 0
0x180015696  mov     rax, [r9+18h]
0x18001569a  mov     r10, [rax]
0x18001569d  test    r10, r10
0x1800156a0  jz      short loc_180015710
0x1800156a2  mov     rax, [rcx]
0x1800156a5  mov     rax, [rax+38h]
0x1800156a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800156ae  mov     rcx, rax; SRWLock
0x1800156b1  mov     rbx, rax
0x1800156b4  call    cs:__imp_AcquireSRWLockShared
0x1800156ba  mov     rcx, [rdi+18h]
0x1800156be  mov     rcx, [rcx]; Ptr
0x1800156c1  test    rcx, rcx
0x1800156c4  jz      short loc_180015702
0x1800156c6  call    cs:__imp_DecodePointer
0x1800156cc  mov     [rsp+68h+Ptr], rax
0x1800156d4  mov     r8, r14
0x1800156d7  mov     r9, rax
0x1800156da  mov     rdx, r15
0x1800156dd  mov     rcx, [rax]
0x1800156e0  mov     rax, [rcx]
0x1800156e3  mov     rcx, r9
0x1800156e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800156eb  mov     edi, eax
0x1800156ed  test    rbx, rbx
0x1800156f0  jz      short loc_1800156FB
0x1800156f2  mov     rcx, rbx; SRWLock
0x1800156f5  call    cs:__imp_ReleaseSRWLockShared
0x1800156fb  mov     eax, edi
0x1800156fd  jmp     loc_1800157E6
0x180015702  test    rbx, rbx
0x180015705  jz      short loc_180015710
0x180015707  mov     rcx, rbx; SRWLock
0x18001570a  call    cs:__imp_ReleaseSRWLockShared
0x180015710  mov     rax, [rdi]
0x180015713  lea     r9, [rsp+68h+Ptr]
0x18001571b  mov     r8, r15
0x18001571e  mov     rdx, rdi
0x180015721  mov     rcx, rbp
0x180015724  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015729  test    eax, eax
0x18001572b  js      loc_1800157E6
0x180015731  test    byte ptr [rbp+0], 4
0x180015735  jnz     loc_1800157D9
0x18001573b  mov     rax, [rsi]
0x18001573e  mov     rcx, rsi
0x180015741  mov     rax, [rax+38h]
0x180015745  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001574a  mov     rdx, rax
0x18001574d  lea     rcx, [rsp+68h+SRWLock]
0x180015755  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18001575a  mov     rax, [rdi+18h]
0x18001575e  mov     rcx, [rax]; Ptr
0x180015761  test    rcx, rcx
0x180015764  jnz     short loc_18001577F
0x180015766  mov     rcx, [rsp+68h+Ptr]; Ptr
0x18001576e  xor     ebx, ebx
0x180015770  call    cs:__imp_EncodePointer
0x180015776  mov     rcx, [rdi+18h]
0x18001577a  mov     [rcx], rax
0x18001577d  jmp     short loc_180015797
0x18001577f  call    cs:__imp_DecodePointer
0x180015785  mov     rbx, rax
0x180015788  mov     rcx, [rax]
0x18001578b  mov     rax, [rcx+8]
0x18001578f  mov     rcx, rbx
0x180015792  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015797  mov     rcx, [rsp+68h+SRWLock]; SRWLock
0x18001579f  test    rcx, rcx
0x1800157a2  jz      short loc_1800157AA
0x1800157a4  call    cs:__imp_ReleaseSRWLockExclusive
0x1800157aa  test    rbx, rbx
0x1800157ad  jz      short loc_1800157D9
0x1800157af  mov     rcx, [rsp+68h+Ptr]
0x1800157b7  mov     rax, [rcx]
0x1800157ba  mov     rax, [rax+10h]
0x1800157be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800157c3  mov     rcx, [rsp+68h+Ptr]
0x1800157cb  mov     rax, [rcx]
0x1800157ce  mov     rax, [rax+10h]
0x1800157d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800157d7  jmp     short loc_1800157E1
0x1800157d9  mov     rbx, [rsp+68h+Ptr]
0x1800157e1  mov     [r14], rbx
0x1800157e4  xor     eax, eax
0x1800157e6  add     rsp, 38h
0x1800157ea  pop     r15
0x1800157ec  pop     r14
0x1800157ee  pop     rdi
0x1800157ef  pop     rsi
0x1800157f0  pop     rbp
0x1800157f1  pop     rbx
0x1800157f2  retn
```
