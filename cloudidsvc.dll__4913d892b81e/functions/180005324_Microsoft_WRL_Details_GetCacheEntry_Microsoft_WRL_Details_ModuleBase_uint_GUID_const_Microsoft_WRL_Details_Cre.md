# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x180005324`
- end: `0x1800054ab`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `391`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, PSRWLOCK SRWLock)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180002708`

## callees

- `0x180005324`
- `0x1800061e8`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000545f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000545f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800053b8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800053cd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800053b8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800053cd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180005376`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180005376`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18000542e`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18000542e`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180005388`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000543d`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180005388`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000543d`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::GetCacheEntry(
        Microsoft::WRL::Details *this,
        struct Microsoft::WRL::Details::ModuleBase *a2,
        unsigned int *a3,
        const struct _GUID *a4,
        PSRWLOCK SRWLock)
{
  PSRWLOCK v8; // r14
  RTL_SRWLOCK *v9; // rbx
  void *v10; // rcx
  unsigned int v11; // edi
  __int64 result; // rax
  __int64 v13; // rax
  void *v14; // rcx
  PVOID v15; // rbx
  PVOID Ptr; // [rsp+60h] [rbp+18h] BYREF

  v8 = SRWLock;
  SRWLock->Ptr = 0;
  Ptr = 0;
  if ( **(_QWORD **)a4[1].Data4 )
  {
    v9 = (RTL_SRWLOCK *)(*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 56LL))(this);
    AcquireSRWLockShared(v9);
    v10 = **(void ***)a4[1].Data4;
    if ( v10 )
    {
      Ptr = DecodePointer(v10);
      v11 = (**(__int64 (__fastcall ***)(PVOID, GUID *, PSRWLOCK))Ptr)(
              Ptr,
              &GUID_00000035_0000_0000_c000_000000000046,
              v8);
      if ( v9 )
        ReleaseSRWLockShared(v9);
      return v11;
    }
    if ( v9 )
      ReleaseSRWLockShared(v9);
  }
  result = (*(__int64 (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *, const struct _GUID *, GUID *, PVOID *))&a4->Data1)(
             a2,
             a4,
             &GUID_00000035_0000_0000_c000_000000000046,
             &Ptr);
  if ( (int)result >= 0 )
  {
    if ( (*(_BYTE *)a2 & 4) != 0 )
      goto LABEL_17;
    v13 = (*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 56LL))(this);
    Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, v13);
    v14 = **(void ***)a4[1].Data4;
    if ( v14 )
    {
      v15 = DecodePointer(v14);
      (*(void (__fastcall **)(PVOID))(*(_QWORD *)v15 + 8LL))(v15);
    }
    else
    {
      v15 = 0;
      **(_QWORD **)a4[1].Data4 = EncodePointer(Ptr);
    }
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    if ( !v15 )
    {
LABEL_17:
      v15 = Ptr;
    }
    else
    {
      (*(void (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 16LL))(Ptr);
      (*(void (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 16LL))(Ptr);
    }
    v8->Ptr = v15;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180005324  mov     rax, rsp
0x180005327  mov     [rax+8], rbx
0x18000532b  mov     [rax+10h], rbp
0x18000532f  mov     [rax+18h], r8
0x180005333  push    rsi
0x180005334  push    rdi
0x180005335  push    r14
0x180005337  sub     rsp, 30h
0x18000533b  mov     rdi, r9
0x18000533e  mov     rbp, rdx
0x180005341  mov     rsi, rcx
0x180005344  mov     r14, [rsp+48h+SRWLock]
0x180005349  mov     qword ptr [r14], 0
0x180005350  mov     qword ptr [rax+18h], 0
0x180005358  mov     rax, [r9+18h]
0x18000535c  mov     r8, [rax]
0x18000535f  test    r8, r8
0x180005362  jz      short loc_1800053D3
0x180005364  mov     rax, [rcx]
0x180005367  mov     rax, [rax+38h]
0x18000536b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005370  mov     rbx, rax
0x180005373  mov     rcx, rax; SRWLock
0x180005376  call    cs:__imp_AcquireSRWLockShared
0x18000537c  mov     rcx, [rdi+18h]
0x180005380  mov     rcx, [rcx]; Ptr
0x180005383  test    rcx, rcx
0x180005386  jz      short loc_1800053C5
0x180005388  call    cs:__imp_DecodePointer
0x18000538e  mov     r9, rax
0x180005391  mov     [rsp+48h+Ptr], rax
0x180005396  mov     rcx, [rax]
0x180005399  mov     rax, [rcx]
0x18000539c  mov     r8, r14
0x18000539f  lea     rdx, _GUID_00000035_0000_0000_c000_000000000046
0x1800053a6  mov     rcx, r9
0x1800053a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053ae  mov     edi, eax
0x1800053b0  test    rbx, rbx
0x1800053b3  jz      short loc_1800053BE
0x1800053b5  mov     rcx, rbx; SRWLock
0x1800053b8  call    cs:__imp_ReleaseSRWLockShared
0x1800053be  mov     eax, edi
0x1800053c0  jmp     loc_180005498
0x1800053c5  test    rbx, rbx
0x1800053c8  jz      short loc_1800053D3
0x1800053ca  mov     rcx, rbx; SRWLock
0x1800053cd  call    cs:__imp_ReleaseSRWLockShared
0x1800053d3  lea     r9, [rsp+48h+Ptr]
0x1800053d8  lea     r8, _GUID_00000035_0000_0000_c000_000000000046
0x1800053df  mov     rdx, rdi
0x1800053e2  mov     rcx, rbp
0x1800053e5  mov     rax, [rdi]
0x1800053e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053ed  test    eax, eax
0x1800053ef  js      loc_180005498
0x1800053f5  test    byte ptr [rbp+0], 4
0x1800053f9  jnz     loc_18000548E
0x1800053ff  mov     rax, [rsi]
0x180005402  mov     rcx, rsi
0x180005405  mov     rax, [rax+38h]
0x180005409  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000540e  mov     rdx, rax
0x180005411  lea     rcx, [rsp+48h+SRWLock]
0x180005416  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18000541b  mov     rax, [rdi+18h]
0x18000541f  mov     rcx, [rax]; Ptr
0x180005422  test    rcx, rcx
0x180005425  jnz     short loc_18000543D
0x180005427  xor     ebx, ebx
0x180005429  mov     rcx, [rsp+48h+Ptr]; Ptr
0x18000542e  call    cs:__imp_EncodePointer
0x180005434  mov     rcx, [rdi+18h]
0x180005438  mov     [rcx], rax
0x18000543b  jmp     short loc_180005455
0x18000543d  call    cs:__imp_DecodePointer
0x180005443  mov     rbx, rax
0x180005446  mov     rcx, [rax]
0x180005449  mov     rax, [rcx+8]
0x18000544d  mov     rcx, rbx
0x180005450  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005455  mov     rcx, [rsp+48h+SRWLock]; SRWLock
0x18000545a  test    rcx, rcx
0x18000545d  jz      short loc_180005465
0x18000545f  call    cs:__imp_ReleaseSRWLockExclusive
0x180005465  test    rbx, rbx
0x180005468  jz      short loc_18000548E
0x18000546a  mov     rcx, [rsp+48h+Ptr]
0x18000546f  mov     rax, [rcx]
0x180005472  mov     rax, [rax+10h]
0x180005476  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000547b  mov     rcx, [rsp+48h+Ptr]
0x180005480  mov     rax, [rcx]
0x180005483  mov     rax, [rax+10h]
0x180005487  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000548c  jmp     short loc_180005493
0x18000548e  mov     rbx, [rsp+48h+Ptr]
0x180005493  mov     [r14], rbx
0x180005496  xor     eax, eax
0x180005498  mov     rbx, [rsp+48h+arg_0]
0x18000549d  mov     rbp, [rsp+48h+arg_8]
0x1800054a2  add     rsp, 30h
0x1800054a6  pop     r14
0x1800054a8  pop     rdi
0x1800054a9  pop     rsi
0x1800054aa  retn
```
