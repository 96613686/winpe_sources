# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x180005bac`
- end: `0x180005d32`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `390`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, _QWORD *Ptr)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008c40`
- `0x180008e00`

## callees

- `0x180005bac`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180005bfc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180005bfc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180005c3d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180005c52`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180005c3d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180005c52`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005c98`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005c98`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005ce3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005ce3`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180005c0e`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180005cc3`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180005c0e`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180005cc3`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180005cb4`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180005cb4`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
0x180005bac  mov     rax, rsp
0x180005baf  push    rbx
0x180005bb0  push    rbp
0x180005bb1  push    rsi
0x180005bb2  push    rdi
0x180005bb3  push    r14
0x180005bb5  push    r15
0x180005bb7  sub     rsp, 38h
0x180005bbb  mov     rdi, r9
0x180005bbe  mov     r15, r8
0x180005bc1  mov     rbp, rdx
0x180005bc4  mov     rsi, rcx
0x180005bc7  mov     r14, [rsp+68h+Ptr]
0x180005bcf  mov     qword ptr [r14], 0
0x180005bd6  mov     qword ptr [rax+28h], 0
0x180005bde  mov     rax, [r9+18h]
0x180005be2  mov     r10, [rax]
0x180005be5  test    r10, r10
0x180005be8  jz      short loc_180005C58
0x180005bea  mov     rax, [rcx]
0x180005bed  mov     rax, [rax+38h]
0x180005bf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bf6  mov     rbx, rax
0x180005bf9  mov     rcx, rax; SRWLock
0x180005bfc  call    cs:__imp_AcquireSRWLockShared
0x180005c02  mov     rcx, [rdi+18h]
0x180005c06  mov     rcx, [rcx]; Ptr
0x180005c09  test    rcx, rcx
0x180005c0c  jz      short loc_180005C4A
0x180005c0e  call    cs:__imp_DecodePointer
0x180005c14  mov     r9, rax
0x180005c17  mov     [rsp+68h+Ptr], rax
0x180005c1f  mov     rcx, [rax]
0x180005c22  mov     rax, [rcx]
0x180005c25  mov     r8, r14
0x180005c28  mov     rdx, r15
0x180005c2b  mov     rcx, r9
0x180005c2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c33  mov     edi, eax
0x180005c35  test    rbx, rbx
0x180005c38  jz      short loc_180005C43
0x180005c3a  mov     rcx, rbx; SRWLock
0x180005c3d  call    cs:__imp_ReleaseSRWLockShared
0x180005c43  mov     eax, edi
0x180005c45  jmp     loc_180005D25
0x180005c4a  test    rbx, rbx
0x180005c4d  jz      short loc_180005C58
0x180005c4f  mov     rcx, rbx; SRWLock
0x180005c52  call    cs:__imp_ReleaseSRWLockShared
0x180005c58  lea     r9, [rsp+68h+Ptr]
0x180005c60  mov     r8, r15
0x180005c63  mov     rdx, rdi
0x180005c66  mov     rcx, rbp
0x180005c69  mov     rax, [rdi]
0x180005c6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c71  test    eax, eax
0x180005c73  js      loc_180005D25
0x180005c79  test    byte ptr [rbp+0], 4
0x180005c7d  jnz     loc_180005D18
0x180005c83  mov     rax, [rsi]
0x180005c86  mov     rcx, rsi
0x180005c89  mov     rax, [rax+38h]
0x180005c8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c92  mov     rsi, rax
0x180005c95  mov     rcx, rax; SRWLock
0x180005c98  call    cs:__imp_AcquireSRWLockExclusive
0x180005c9e  mov     rcx, [rdi+18h]
0x180005ca2  mov     rcx, [rcx]; Ptr
0x180005ca5  test    rcx, rcx
0x180005ca8  jnz     short loc_180005CC3
0x180005caa  xor     ebx, ebx
0x180005cac  mov     rcx, [rsp+68h+Ptr]; Ptr
0x180005cb4  call    cs:__imp_EncodePointer
0x180005cba  mov     rcx, [rdi+18h]
0x180005cbe  mov     [rcx], rax
0x180005cc1  jmp     short loc_180005CDB
0x180005cc3  call    cs:__imp_DecodePointer
0x180005cc9  mov     rbx, rax
0x180005ccc  mov     rcx, [rax]
0x180005ccf  mov     rax, [rcx+8]
0x180005cd3  mov     rcx, rbx
0x180005cd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cdb  test    rsi, rsi
0x180005cde  jz      short loc_180005CE9
0x180005ce0  mov     rcx, rsi; SRWLock
0x180005ce3  call    cs:__imp_ReleaseSRWLockExclusive
0x180005ce9  test    rbx, rbx
0x180005cec  jz      short loc_180005D18
0x180005cee  mov     rcx, [rsp+68h+Ptr]
0x180005cf6  mov     rax, [rcx]
0x180005cf9  mov     rax, [rax+10h]
0x180005cfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d02  mov     rcx, [rsp+68h+Ptr]
0x180005d0a  mov     rax, [rcx]
0x180005d0d  mov     rax, [rax+10h]
0x180005d11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d16  jmp     short loc_180005D20
0x180005d18  mov     rbx, [rsp+68h+Ptr]
0x180005d20  mov     [r14], rbx
0x180005d23  xor     eax, eax
0x180005d25  add     rsp, 38h
0x180005d29  pop     r15
0x180005d2b  pop     r14
0x180005d2d  pop     rdi
0x180005d2e  pop     rsi
0x180005d2f  pop     rbp
0x180005d30  pop     rbx
0x180005d31  retn
```
