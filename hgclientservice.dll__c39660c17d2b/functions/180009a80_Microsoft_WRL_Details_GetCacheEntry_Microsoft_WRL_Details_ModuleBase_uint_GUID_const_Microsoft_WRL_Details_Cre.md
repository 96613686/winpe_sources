# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x180009a80`
- end: `0x180009c04`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `388`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, const struct Microsoft::WRL::Details::CreatorMap *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008a70`

## callees

- `0x180009a80`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009b70`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009b70`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009bb8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009bb8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180009ad2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180009ad2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180009b14`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180009b29`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180009b14`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180009b29`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180009ae4`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180009b98`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180009ae4`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180009b98`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180009b89`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180009b89`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::GetCacheEntry(
        Microsoft::WRL::Details *this,
        struct Microsoft::WRL::Details::ModuleBase *a2,
        unsigned int *a3,
        const struct _GUID *a4,
        const struct Microsoft::WRL::Details::CreatorMap *a5)
{
  const struct Microsoft::WRL::Details::CreatorMap *v8; // r14
  RTL_SRWLOCK *v9; // rbx
  void *v10; // rcx
  unsigned int v11; // edi
  __int64 result; // rax
  RTL_SRWLOCK *v13; // rsi
  void *v14; // rcx
  PVOID v15; // rbx
  PVOID Ptr; // [rsp+60h] [rbp+18h] BYREF

  v8 = a5;
  *(_QWORD *)a5 = 0;
  Ptr = 0;
  if ( **(_QWORD **)a4[1].Data4 )
  {
    v9 = (RTL_SRWLOCK *)(*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 56LL))(this);
    AcquireSRWLockShared(v9);
    v10 = **(void ***)a4[1].Data4;
    if ( v10 )
    {
      Ptr = DecodePointer(v10);
      v11 = (**(__int64 (__fastcall ***)(PVOID, GUID *, const struct Microsoft::WRL::Details::CreatorMap *))Ptr)(
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
    v13 = (RTL_SRWLOCK *)(*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 56LL))(this);
    AcquireSRWLockExclusive(v13);
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
    if ( v13 )
      ReleaseSRWLockExclusive(v13);
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
    *(_QWORD *)v8 = v15;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180009a80  mov     rax, rsp
0x180009a83  mov     [rax+8], rbx
0x180009a87  mov     [rax+10h], rbp
0x180009a8b  mov     [rax+18h], r8
0x180009a8f  push    rsi
0x180009a90  push    rdi
0x180009a91  push    r14
0x180009a93  sub     rsp, 30h
0x180009a97  mov     rdi, r9
0x180009a9a  mov     rbp, rdx
0x180009a9d  mov     rsi, rcx
0x180009aa0  mov     r14, [rsp+48h+arg_20]
0x180009aa5  mov     qword ptr [r14], 0
0x180009aac  mov     qword ptr [rax+18h], 0
0x180009ab4  mov     rax, [r9+18h]
0x180009ab8  mov     r8, [rax]
0x180009abb  test    r8, r8
0x180009abe  jz      short loc_180009B2F
0x180009ac0  mov     rax, [rcx]
0x180009ac3  mov     rax, [rax+38h]
0x180009ac7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009acc  mov     rbx, rax
0x180009acf  mov     rcx, rax; SRWLock
0x180009ad2  call    cs:__imp_AcquireSRWLockShared
0x180009ad8  mov     rcx, [rdi+18h]
0x180009adc  mov     rcx, [rcx]; Ptr
0x180009adf  test    rcx, rcx
0x180009ae2  jz      short loc_180009B21
0x180009ae4  call    cs:__imp_DecodePointer
0x180009aea  mov     r9, rax
0x180009aed  mov     [rsp+48h+Ptr], rax
0x180009af2  mov     rcx, [rax]
0x180009af5  mov     rax, [rcx]
0x180009af8  mov     r8, r14
0x180009afb  lea     rdx, _GUID_00000035_0000_0000_c000_000000000046
0x180009b02  mov     rcx, r9
0x180009b05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b0a  mov     edi, eax
0x180009b0c  test    rbx, rbx
0x180009b0f  jz      short loc_180009B1A
0x180009b11  mov     rcx, rbx; SRWLock
0x180009b14  call    cs:__imp_ReleaseSRWLockShared
0x180009b1a  mov     eax, edi
0x180009b1c  jmp     loc_180009BF1
0x180009b21  test    rbx, rbx
0x180009b24  jz      short loc_180009B2F
0x180009b26  mov     rcx, rbx; SRWLock
0x180009b29  call    cs:__imp_ReleaseSRWLockShared
0x180009b2f  lea     r9, [rsp+48h+Ptr]
0x180009b34  lea     r8, _GUID_00000035_0000_0000_c000_000000000046
0x180009b3b  mov     rdx, rdi
0x180009b3e  mov     rcx, rbp
0x180009b41  mov     rax, [rdi]
0x180009b44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b49  test    eax, eax
0x180009b4b  js      loc_180009BF1
0x180009b51  test    byte ptr [rbp+0], 4
0x180009b55  jnz     loc_180009BE7
0x180009b5b  mov     rax, [rsi]
0x180009b5e  mov     rcx, rsi
0x180009b61  mov     rax, [rax+38h]
0x180009b65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b6a  mov     rsi, rax
0x180009b6d  mov     rcx, rax; SRWLock
0x180009b70  call    cs:__imp_AcquireSRWLockExclusive
0x180009b76  mov     rcx, [rdi+18h]
0x180009b7a  mov     rcx, [rcx]; Ptr
0x180009b7d  test    rcx, rcx
0x180009b80  jnz     short loc_180009B98
0x180009b82  xor     ebx, ebx
0x180009b84  mov     rcx, [rsp+48h+Ptr]; Ptr
0x180009b89  call    cs:__imp_EncodePointer
0x180009b8f  mov     rcx, [rdi+18h]
0x180009b93  mov     [rcx], rax
0x180009b96  jmp     short loc_180009BB0
0x180009b98  call    cs:__imp_DecodePointer
0x180009b9e  mov     rbx, rax
0x180009ba1  mov     rcx, [rax]
0x180009ba4  mov     rax, [rcx+8]
0x180009ba8  mov     rcx, rbx
0x180009bab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009bb0  test    rsi, rsi
0x180009bb3  jz      short loc_180009BBE
0x180009bb5  mov     rcx, rsi; SRWLock
0x180009bb8  call    cs:__imp_ReleaseSRWLockExclusive
0x180009bbe  test    rbx, rbx
0x180009bc1  jz      short loc_180009BE7
0x180009bc3  mov     rcx, [rsp+48h+Ptr]
0x180009bc8  mov     rax, [rcx]
0x180009bcb  mov     rax, [rax+10h]
0x180009bcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009bd4  mov     rcx, [rsp+48h+Ptr]
0x180009bd9  mov     rax, [rcx]
0x180009bdc  mov     rax, [rax+10h]
0x180009be0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009be5  jmp     short loc_180009BEC
0x180009be7  mov     rbx, [rsp+48h+Ptr]
0x180009bec  mov     [r14], rbx
0x180009bef  xor     eax, eax
0x180009bf1  mov     rbx, [rsp+48h+arg_0]
0x180009bf6  mov     rbp, [rsp+48h+arg_8]
0x180009bfb  add     rsp, 30h
0x180009bff  pop     r14
0x180009c01  pop     rdi
0x180009c02  pop     rsi
0x180009c03  retn
```
