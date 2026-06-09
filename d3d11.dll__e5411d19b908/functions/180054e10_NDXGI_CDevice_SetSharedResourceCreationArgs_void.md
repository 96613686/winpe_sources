# NDXGI::CDevice::SetSharedResourceCreationArgs(void *)

- ea: `0x180054e10`
- end: `0x180054f6c`
- name: `?SetSharedResourceCreationArgs@CDevice@NDXGI@@UEAAJPEAX@Z`
- size: `348`
- prototype: `__int64 __fastcall(NDXGI::CDevice *__hidden this, void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180054e10`
- `0x180054f74`
- `0x18009d94c`
- `0x18009da0c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180054e56`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180054f21`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180054e56`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180054f21`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180054ef1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180054f49`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180054ef1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180054f49`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180054e46`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180054e46`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall NDXGI::CDevice::SetSharedResourceCreationArgs(RTL_SRWLOCK *this, void *a2)
{
  RTL_SRWLOCK *v4; // rbx
  __int64 v5; // rax
  int v6; // r11d
  __int64 v7; // r10
  _QWORD *Ptr; // rdx
  _QWORD *v9; // rcx
  _QWORD *v10; // r8
  __int64 v11; // rdx
  DWORD CurrentThreadId; // [rsp+20h] [rbp-28h] BYREF
  void *v14; // [rsp+28h] [rbp-20h]
  char v15[24]; // [rsp+30h] [rbp-18h] BYREF
  PSRWLOCK SRWLock; // [rsp+50h] [rbp+8h] BYREF
  RTL_SRWLOCK *v17; // [rsp+60h] [rbp+18h]

  if ( BYTE2(this[112].Ptr) )
  {
    this[215].Ptr = a2;
  }
  else
  {
    v4 = this + 206;
    SRWLock = this + 206;
    v17 = this + 206;
    AcquireSRWLockExclusive(this + 206);
    if ( a2 )
    {
      CurrentThreadId = GetCurrentThreadId();
      v14 = a2;
      std::_Hash<std::_Umap_traits<unsigned long,SD3D11SharedResourceCreationArgs *,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,SD3D11SharedResourceCreationArgs *>>,0>>::emplace<std::pair<unsigned long,SD3D11SharedResourceCreationArgs *>>(
        &this[207],
        v15,
        &CurrentThreadId);
    }
    else
    {
      LODWORD(SRWLock) = GetCurrentThreadId();
      v5 = std::_Conditionally_enabled_hash<unsigned long,1>::operator()(&SRWLock);
      v7 = 2 * ((__int64)this[213].Ptr & v5);
      Ptr = this[210].Ptr;
      v9 = (_QWORD *)Ptr[2 * ((__int64)this[213].Ptr & v5) + 1];
      v10 = this[208].Ptr;
      if ( v9 == v10 )
      {
LABEL_7:
        v9 = 0;
      }
      else
      {
        while ( v6 != *((_DWORD *)v9 + 4) )
        {
          if ( v9 == (_QWORD *)Ptr[2 * ((__int64)this[213].Ptr & v5)] )
            goto LABEL_7;
          v9 = (_QWORD *)v9[1];
        }
      }
      if ( v9 )
      {
        if ( (_QWORD *)Ptr[2 * ((__int64)this[213].Ptr & v5) + 1] == v9 )
        {
          if ( (_QWORD *)Ptr[2 * ((__int64)this[213].Ptr & v5)] == v9 )
            Ptr[2 * ((__int64)this[213].Ptr & v5)] = v10;
          else
            v10 = (_QWORD *)v9[1];
          Ptr[v7 + 1] = v10;
        }
        else if ( (_QWORD *)Ptr[2 * ((__int64)this[213].Ptr & v5)] == v9 )
        {
          Ptr[2 * ((__int64)this[213].Ptr & v5)] = *v9;
        }
        v11 = *v9;
        --this[209].Ptr;
        *(_QWORD *)v9[1] = v11;
        *(_QWORD *)(v11 + 8) = v9[1];
        std::_Deallocate<16>(v9, 32);
      }
    }
    if ( v4 )
      ReleaseSRWLockExclusive(v4);
  }
  return 0;
}

```

## disassembly

```asm
0x180054e10  mov     [rsp+arg_8], rbx
0x180054e15  mov     [rsp+arg_18], rsi
0x180054e1a  push    rdi
0x180054e1b  sub     rsp, 40h
0x180054e1f  mov     rsi, rdx
0x180054e22  mov     rdi, rcx
0x180054e25  cmp     byte ptr [rcx+382h], 0
0x180054e2c  jnz     loc_180054F09
0x180054e32  lea     rbx, [rcx+670h]
0x180054e39  mov     [rsp+48h+SRWLock], rbx
0x180054e3e  mov     [rsp+48h+arg_10], rbx
0x180054e43  mov     rcx, rbx; SRWLock
0x180054e46  call    cs:__imp_AcquireSRWLockExclusive
0x180054e4c  nop
0x180054e4d  test    rsi, rsi
0x180054e50  jnz     loc_180054F21
0x180054e56  call    cs:__imp_GetCurrentThreadId
0x180054e5c  mov     r11d, eax
0x180054e5f  mov     dword ptr [rsp+48h+SRWLock], eax
0x180054e63  lea     rcx, [rsp+48h+SRWLock]
0x180054e68  call    ??R?$_Conditionally_enabled_hash@K$00@std@@SA_KAEBK@Z; std::_Conditionally_enabled_hash<ulong,1>::operator()(ulong const &)
0x180054e6d  mov     r10, rax
0x180054e70  and     r10, [rdi+6A8h]
0x180054e77  add     r10, r10
0x180054e7a  mov     rdx, [rdi+690h]
0x180054e81  mov     rcx, [rdx+r10*8+8]
0x180054e86  mov     r8, [rdi+680h]
0x180054e8d  cmp     rcx, r8
0x180054e90  jz      short loc_180054EA4
0x180054e92  cmp     r11d, [rcx+10h]
0x180054e96  jz      short loc_180054EA6
0x180054e98  cmp     rcx, [rdx+r10*8]
0x180054e9c  jz      short loc_180054EA4
0x180054e9e  mov     rcx, [rcx+8]
0x180054ea2  jmp     short loc_180054E92
0x180054ea4  xor     ecx, ecx
0x180054ea6  test    rcx, rcx
0x180054ea9  jz      short loc_180054EE9
0x180054eab  cmp     [rdx+r10*8+8], rcx
0x180054eb0  jnz     short loc_180054F12
0x180054eb2  cmp     [rdx+r10*8], rcx
0x180054eb6  jnz     loc_180054F62
0x180054ebc  mov     [rdx+r10*8], r8
0x180054ec0  mov     [rdx+r10*8+8], r8
0x180054ec5  mov     rdx, [rcx]
0x180054ec8  dec     qword ptr [rdi+688h]
0x180054ecf  mov     rax, [rcx+8]
0x180054ed3  mov     [rax], rdx
0x180054ed6  mov     rax, [rcx+8]
0x180054eda  mov     [rdx+8], rax
0x180054ede  mov     edx, 20h ; ' '
0x180054ee3  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180054ee8  nop
0x180054ee9  test    rbx, rbx
0x180054eec  jz      short loc_180054EF7
0x180054eee  mov     rcx, rbx; SRWLock
0x180054ef1  call    cs:__imp_ReleaseSRWLockExclusive
0x180054ef7  xor     eax, eax
0x180054ef9  mov     rbx, [rsp+48h+arg_8]
0x180054efe  mov     rsi, [rsp+48h+arg_18]
0x180054f03  add     rsp, 40h
0x180054f07  pop     rdi
0x180054f08  retn
0x180054f09  mov     [rcx+6B8h], rsi
0x180054f10  jmp     short loc_180054EF7
0x180054f12  cmp     [rdx+r10*8], rcx
0x180054f16  jnz     short loc_180054EC5
0x180054f18  mov     rax, [rcx]
0x180054f1b  mov     [rdx+r10*8], rax
0x180054f1f  jmp     short loc_180054EC5
0x180054f21  call    cs:__imp_GetCurrentThreadId
0x180054f27  mov     [rsp+48h+var_28], eax
0x180054f2b  mov     [rsp+48h+var_20], rsi
0x180054f30  lea     rcx, [rdi+678h]
0x180054f37  lea     r8, [rsp+48h+var_28]
0x180054f3c  lea     rdx, [rsp+48h+var_18]
0x180054f41  call    ??$emplace@U?$pair@KPEAUSD3D11SharedResourceCreationArgs@@@std@@@?$_Hash@V?$_Umap_traits@KPEAUSD3D11SharedResourceCreationArgs@@V?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@std@@V?$allocator@U?$pair@$$CBKPEAUSD3D11SharedResourceCreationArgs@@@std@@@3@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKPEAUSD3D11SharedResourceCreationArgs@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@KPEAUSD3D11SharedResourceCreationArgs@@@1@@Z; std::_Hash<std::_Umap_traits<ulong,SD3D11SharedResourceCreationArgs *,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,SD3D11SharedResourceCreationArgs *>>,0>>::emplace<std::pair<ulong,SD3D11SharedResourceCreationArgs *>>(std::pair<ulong,SD3D11SharedResourceCreationArgs *> &&)
0x180054f46  nop
0x180054f47  jmp     short loc_180054EE9
0x180054f49  call    cs:__imp_ReleaseSRWLockExclusive
0x180054f4f  mov     eax, 8007000Eh
0x180054f54  jmp     short loc_180054EF9
0x180054f56  mov     rcx, [rsp+48h+SRWLock]; SRWLock
0x180054f5b  test    rcx, rcx
0x180054f5e  jz      short loc_180054F4F
0x180054f60  jmp     short loc_180054F49
0x180054f62  mov     r8, [rcx+8]
0x180054f66  jmp     loc_180054EC0
```
