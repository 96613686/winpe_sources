# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x180007294`
- end: `0x180007423`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `399`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *__hidden this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, PVOID Ptr, struct IUnknown **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180006f8c`

## callees

- `0x180007294`
- `0x1800074ac`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180007325`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000733a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180007325`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000733a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800072e4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800072e4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800073d4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800073d4`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1800073a0`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1800073a0`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800072f6`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800073af`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800072f6`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800073af`

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
0x180007294  mov     rax, rsp
0x180007297  push    rbx
0x180007298  push    rbp
0x180007299  push    rsi
0x18000729a  push    rdi
0x18000729b  push    r14
0x18000729d  push    r15
0x18000729f  sub     rsp, 38h
0x1800072a3  mov     rdi, r9
0x1800072a6  mov     r15, r8
0x1800072a9  mov     rbp, rdx
0x1800072ac  mov     rsi, rcx
0x1800072af  mov     r14, [rsp+68h+Ptr]
0x1800072b7  mov     qword ptr [r14], 0
0x1800072be  mov     qword ptr [rax+28h], 0
0x1800072c6  mov     rax, [r9+18h]
0x1800072ca  mov     r10, [rax]
0x1800072cd  test    r10, r10
0x1800072d0  jz      short loc_180007340
0x1800072d2  mov     rax, [rcx]
0x1800072d5  mov     rax, [rax+38h]
0x1800072d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072de  mov     rbx, rax
0x1800072e1  mov     rcx, rax; SRWLock
0x1800072e4  call    cs:__imp_AcquireSRWLockShared
0x1800072ea  mov     rcx, [rdi+18h]
0x1800072ee  mov     rcx, [rcx]; Ptr
0x1800072f1  test    rcx, rcx
0x1800072f4  jz      short loc_180007332
0x1800072f6  call    cs:__imp_DecodePointer
0x1800072fc  mov     r9, rax
0x1800072ff  mov     [rsp+68h+Ptr], rax
0x180007307  mov     rcx, [rax]
0x18000730a  mov     rax, [rcx]
0x18000730d  mov     r8, r14
0x180007310  mov     rdx, r15
0x180007313  mov     rcx, r9
0x180007316  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000731b  mov     edi, eax
0x18000731d  test    rbx, rbx
0x180007320  jz      short loc_18000732B
0x180007322  mov     rcx, rbx; SRWLock
0x180007325  call    cs:__imp_ReleaseSRWLockShared
0x18000732b  mov     eax, edi
0x18000732d  jmp     loc_180007416
0x180007332  test    rbx, rbx
0x180007335  jz      short loc_180007340
0x180007337  mov     rcx, rbx; SRWLock
0x18000733a  call    cs:__imp_ReleaseSRWLockShared
0x180007340  lea     r9, [rsp+68h+Ptr]
0x180007348  mov     r8, r15
0x18000734b  mov     rdx, rdi
0x18000734e  mov     rcx, rbp
0x180007351  mov     rax, [rdi]
0x180007354  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007359  test    eax, eax
0x18000735b  js      loc_180007416
0x180007361  test    byte ptr [rbp+0], 4
0x180007365  jnz     loc_180007409
0x18000736b  mov     rax, [rsi]
0x18000736e  mov     rcx, rsi
0x180007371  mov     rax, [rax+38h]
0x180007375  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000737a  mov     rdx, rax
0x18000737d  lea     rcx, [rsp+68h+SRWLock]
0x180007385  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18000738a  mov     rax, [rdi+18h]
0x18000738e  mov     rcx, [rax]; Ptr
0x180007391  test    rcx, rcx
0x180007394  jnz     short loc_1800073AF
0x180007396  xor     ebx, ebx
0x180007398  mov     rcx, [rsp+68h+Ptr]; Ptr
0x1800073a0  call    cs:__imp_EncodePointer
0x1800073a6  mov     rcx, [rdi+18h]
0x1800073aa  mov     [rcx], rax
0x1800073ad  jmp     short loc_1800073C7
0x1800073af  call    cs:__imp_DecodePointer
0x1800073b5  mov     rbx, rax
0x1800073b8  mov     rcx, [rax]
0x1800073bb  mov     rax, [rcx+8]
0x1800073bf  mov     rcx, rbx
0x1800073c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073c7  mov     rcx, [rsp+68h+SRWLock]; SRWLock
0x1800073cf  test    rcx, rcx
0x1800073d2  jz      short loc_1800073DA
0x1800073d4  call    cs:__imp_ReleaseSRWLockExclusive
0x1800073da  test    rbx, rbx
0x1800073dd  jz      short loc_180007409
0x1800073df  mov     rcx, [rsp+68h+Ptr]
0x1800073e7  mov     rax, [rcx]
0x1800073ea  mov     rax, [rax+10h]
0x1800073ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073f3  mov     rcx, [rsp+68h+Ptr]
0x1800073fb  mov     rax, [rcx]
0x1800073fe  mov     rax, [rax+10h]
0x180007402  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007407  jmp     short loc_180007411
0x180007409  mov     rbx, [rsp+68h+Ptr]
0x180007411  mov     [r14], rbx
0x180007414  xor     eax, eax
0x180007416  add     rsp, 38h
0x18000741a  pop     r15
0x18000741c  pop     r14
0x18000741e  pop     rdi
0x18000741f  pop     rsi
0x180007420  pop     rbp
0x180007421  pop     rbx
0x180007422  retn
```
