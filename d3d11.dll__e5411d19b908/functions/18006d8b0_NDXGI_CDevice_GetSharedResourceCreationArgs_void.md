# NDXGI::CDevice::GetSharedResourceCreationArgs(void)

- ea: `0x18006d8b0`
- end: `0x18006d93f`
- name: `?GetSharedResourceCreationArgs@CDevice@NDXGI@@QEAAPEAUSD3D11SharedResourceCreationArgs@@XZ`
- size: `143`
- prototype: `struct SD3D11SharedResourceCreationArgs *__fastcall(NDXGI::CDevice *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18006d0f0`
- `0x18006d130`
- `0x18006d1e0`

## callees

- `0x18006d8b0`
- `0x1800a7328`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006d8d6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006d8d6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18006d8d0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18006d8d0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18006d90c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18006d92b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18006d90c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18006d92b`

## pseudocode

```c
struct SD3D11SharedResourceCreationArgs *__fastcall NDXGI::CDevice::GetSharedResourceCreationArgs(RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v2; // rbx
  __int64 v4; // rdi
  DWORD CurrentThreadId; // [rsp+30h] [rbp+8h] BYREF
  _QWORD *v6; // [rsp+38h] [rbp+10h] BYREF

  if ( BYTE2(this[112].Ptr) )
    return (struct SD3D11SharedResourceCreationArgs *)this[215].Ptr;
  v2 = this + 206;
  AcquireSRWLockShared(this + 206);
  CurrentThreadId = GetCurrentThreadId();
  std::_Hash<std::_Umap_traits<unsigned long,SD3D11SharedResourceCreationArgs *,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,SD3D11SharedResourceCreationArgs *>>,0>>::find(
    &this[207],
    &v6,
    &CurrentThreadId);
  if ( v6 == this[208].Ptr )
  {
    if ( v2 )
      ReleaseSRWLockShared(v2);
    return 0;
  }
  else
  {
    v4 = v6[3];
    if ( v2 )
      ReleaseSRWLockShared(v2);
    return (struct SD3D11SharedResourceCreationArgs *)v4;
  }
}

```

## disassembly

```asm
0x18006d8b0  mov     [rsp+arg_10], rbx
0x18006d8b5  push    rdi
0x18006d8b6  sub     rsp, 20h
0x18006d8ba  cmp     byte ptr [rcx+382h], 0
0x18006d8c1  mov     rdi, rcx
0x18006d8c4  jnz     short loc_18006D916
0x18006d8c6  lea     rbx, [rcx+670h]
0x18006d8cd  mov     rcx, rbx; SRWLock
0x18006d8d0  call    cs:__imp_AcquireSRWLockShared
0x18006d8d6  call    cs:__imp_GetCurrentThreadId
0x18006d8dc  lea     rcx, [rdi+678h]
0x18006d8e3  mov     [rsp+28h+arg_0], eax
0x18006d8e7  lea     r8, [rsp+28h+arg_0]
0x18006d8ec  lea     rdx, [rsp+28h+arg_8]
0x18006d8f1  call    ?find@?$_Hash@V?$_Umap_traits@KPEAUSD3D11SharedResourceCreationArgs@@V?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@std@@V?$allocator@U?$pair@$$CBKPEAUSD3D11SharedResourceCreationArgs@@@std@@@3@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKPEAUSD3D11SharedResourceCreationArgs@@@std@@@std@@@std@@@2@AEBK@Z; std::_Hash<std::_Umap_traits<ulong,SD3D11SharedResourceCreationArgs *,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,SD3D11SharedResourceCreationArgs *>>,0>>::find(ulong const &)
0x18006d8f6  mov     rax, [rsp+28h+arg_8]
0x18006d8fb  cmp     rax, [rdi+680h]
0x18006d902  jnz     short loc_18006D91F
0x18006d904  test    rbx, rbx
0x18006d907  jz      short loc_18006D912
0x18006d909  mov     rcx, rbx; SRWLock
0x18006d90c  call    cs:__imp_ReleaseSRWLockShared
0x18006d912  xor     eax, eax
0x18006d914  jmp     short loc_18006D934
0x18006d916  mov     rax, [rcx+6B8h]
0x18006d91d  jmp     short loc_18006D934
0x18006d91f  mov     rdi, [rax+18h]
0x18006d923  test    rbx, rbx
0x18006d926  jz      short loc_18006D931
0x18006d928  mov     rcx, rbx; SRWLock
0x18006d92b  call    cs:__imp_ReleaseSRWLockShared
0x18006d931  mov     rax, rdi
0x18006d934  mov     rbx, [rsp+28h+arg_10]
0x18006d939  add     rsp, 20h
0x18006d93d  pop     rdi
0x18006d93e  retn
```
