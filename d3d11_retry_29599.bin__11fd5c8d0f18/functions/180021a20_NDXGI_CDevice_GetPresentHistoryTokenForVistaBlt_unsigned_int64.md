# NDXGI::CDevice::GetPresentHistoryTokenForVistaBlt(unsigned __int64 &)

- ea: `0x180021a20`
- end: `0x180021aee`
- name: `?GetPresentHistoryTokenForVistaBlt@CDevice@NDXGI@@QEAAHAEA_K@Z`
- size: `206`
- prototype: `__int64 __fastcall(NDXGI::CDevice *__hidden this, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180021700`
- `0x180071e70`

## callees

- `0x180021a20`
- `0x1800bc23c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021a4e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021a4e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180021a48`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180021a48`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180021a82`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180021ad3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180021a82`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180021ad3`

## pseudocode

```c
__int64 __fastcall NDXGI::CDevice::GetPresentHistoryTokenForVistaBlt(RTL_SRWLOCK *this, unsigned __int64 *a2)
{
  RTL_SRWLOCK *v4; // rsi
  _QWORD **v5; // rax
  unsigned __int64 *Ptr; // rax
  DWORD CurrentThreadId; // [rsp+30h] [rbp+8h] BYREF
  char v9; // [rsp+40h] [rbp+18h] BYREF

  if ( BYTE2(this[112].Ptr) )
  {
    Ptr = (unsigned __int64 *)this[196].Ptr;
    if ( !Ptr )
      return 0;
    *a2 = *Ptr;
    return 1;
  }
  else
  {
    v4 = this + 187;
    AcquireSRWLockShared(this + 187);
    CurrentThreadId = GetCurrentThreadId();
    v5 = *(_QWORD ***)std::_Hash<std::_Umap_traits<unsigned long,NDXGI::CDevice::SRenderCBThreadLocalData *,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,NDXGI::CDevice::SRenderCBThreadLocalData *>>,0>>::find(
                        &this[188],
                        &v9,
                        &CurrentThreadId);
    if ( v5 == this[189].Ptr )
    {
      if ( v4 )
        ReleaseSRWLockShared(v4);
      return 0;
    }
    *a2 = *v5[3];
    if ( v4 )
      ReleaseSRWLockShared(v4);
    return 1;
  }
}

```

## disassembly

```asm
0x180021a20  mov     [rsp+arg_8], rbx
0x180021a25  mov     [rsp+arg_18], rsi
0x180021a2a  push    rdi
0x180021a2b  sub     rsp, 20h
0x180021a2f  cmp     byte ptr [rcx+382h], 0
0x180021a36  mov     rdi, rdx
0x180021a39  mov     rbx, rcx
0x180021a3c  jnz     short loc_180021A9A
0x180021a3e  lea     rsi, [rcx+5D8h]
0x180021a45  mov     rcx, rsi; SRWLock
0x180021a48  call    cs:__imp_AcquireSRWLockShared
0x180021a4e  call    cs:__imp_GetCurrentThreadId
0x180021a54  lea     r8, [rsp+28h+arg_0]
0x180021a59  mov     [rsp+28h+arg_0], eax
0x180021a5d  lea     rdx, [rsp+28h+arg_10]
0x180021a62  lea     rcx, [rbx+5E0h]
0x180021a69  call    ?find@?$_Hash@V?$_Umap_traits@KPEAUSRenderCBThreadLocalData@CDevice@NDXGI@@V?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@std@@V?$allocator@U?$pair@$$CBKPEAUSRenderCBThreadLocalData@CDevice@NDXGI@@@std@@@5@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKPEAUSRenderCBThreadLocalData@CDevice@NDXGI@@@std@@@std@@@std@@@2@AEBK@Z; std::_Hash<std::_Umap_traits<ulong,NDXGI::CDevice::SRenderCBThreadLocalData *,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,NDXGI::CDevice::SRenderCBThreadLocalData *>>,0>>::find(ulong const &)
0x180021a6e  mov     rax, [rax]
0x180021a71  cmp     rax, [rbx+5E8h]
0x180021a78  jnz     short loc_180021AC1
0x180021a7a  test    rsi, rsi
0x180021a7d  jz      short loc_180021A88
0x180021a7f  mov     rcx, rsi; SRWLock
0x180021a82  call    cs:__imp_ReleaseSRWLockShared
0x180021a88  xor     eax, eax
0x180021a8a  mov     rbx, [rsp+28h+arg_8]
0x180021a8f  mov     rsi, [rsp+28h+arg_18]
0x180021a94  add     rsp, 20h
0x180021a98  pop     rdi
0x180021a99  retn
0x180021a9a  mov     rax, [rcx+620h]
0x180021aa1  test    rax, rax
0x180021aa4  jz      short loc_180021A88
0x180021aa6  mov     rax, [rax]
0x180021aa9  mov     [rdx], rax
0x180021aac  mov     eax, 1
0x180021ab1  mov     rbx, [rsp+28h+arg_8]
0x180021ab6  mov     rsi, [rsp+28h+arg_18]
0x180021abb  add     rsp, 20h
0x180021abf  pop     rdi
0x180021ac0  retn
0x180021ac1  mov     rax, [rax+18h]
0x180021ac5  mov     rdx, [rax]
0x180021ac8  mov     [rdi], rdx
0x180021acb  test    rsi, rsi
0x180021ace  jz      short loc_180021AD9
0x180021ad0  mov     rcx, rsi; SRWLock
0x180021ad3  call    cs:__imp_ReleaseSRWLockShared
0x180021ad9  mov     rbx, [rsp+28h+arg_8]
0x180021ade  mov     eax, 1
0x180021ae3  mov     rsi, [rsp+28h+arg_18]
0x180021ae8  add     rsp, 20h
0x180021aec  pop     rdi
0x180021aed  retn
```
