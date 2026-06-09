# RealtimeProtection::DlpProcessCache::GetSessionId(PPID const &,ulong &)

- ea: `0x180074f60`
- end: `0x180075174`
- name: `?GetSessionId@DlpProcessCache@RealtimeProtection@@YAJAEBUPPID@@AEAK@Z`
- size: `532`
- prototype: `__int64 __fastcall(RealtimeProtection::DlpProcessCache *__hidden this, const struct PPID *, unsigned int *)`
- caller_count: `15`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180069838`
- `0x180069cb8`
- `0x180074248`
- `0x180074e20`
- `0x18009d7b0`
- `0x18018babc`
- `0x18018cc50`
- `0x1801920b4`
- `0x180199a18`
- `0x18019a344`
- `0x18019d0f0`
- `0x1801a17cc`
- `0x1801d7d6c`
- `0x1801d7e30`
- `0x1801d85a8`

## callees

- `0x180028d80`
- `0x180074f60`
- `0x1800a4248`
- `0x180105f50`
- `0x180107874`
- `0x18010b558`
- `0x18010b568`
- `0x18010cb40`
- `0x18023a290`

## import_xrefs

- `KERNEL32!ProcessIdToSessionId` at `0x180075052`
- `KERNEL32!ProcessIdToSessionId` at `0x180075052`
- `KERNEL32!AcquireSRWLockShared` at `0x180074fc6`
- `KERNEL32!AcquireSRWLockShared` at `0x180074fc6`
- `KERNEL32!ReleaseSRWLockShared` at `0x18007503a`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800750be`
- `KERNEL32!ReleaseSRWLockShared` at `0x18007503a`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800750be`
- `KERNEL32!CompareFileTime` at `0x18007510a`
- `KERNEL32!CompareFileTime` at `0x18007510a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RealtimeProtection::DlpProcessCache::GetSessionId(
        const FILETIME *this,
        const struct PPID *a2,
        unsigned int *a3)
{
  char v5; // bl
  volatile signed __int32 *v6; // rdi
  RTL_SRWLOCK *v7; // rbp
  _QWORD *Ptr; // rax
  __int64 v9; // rbx
  __int64 v10; // r15
  __int64 v11; // rbx
  unsigned int LastFailure; // ebx
  DWORD pSessionId; // [rsp+20h] [rbp-48h] BYREF
  unsigned int v15[5]; // [rsp+24h] [rbp-44h] BYREF

  v5 = 0;
  Lock_shared_ptr_spin_lock(this, a2, a3);
  v6 = (volatile signed __int32 *)qword_180314488;
  if ( qword_180314488 )
  {
    _InterlockedIncrement((volatile signed __int32 *)qword_180314488 + 2);
    v6 = (volatile signed __int32 *)qword_180314488;
  }
  v7 = (RTL_SRWLOCK *)qword_180314480;
  Unlock_shared_ptr_spin_lock();
  if ( v7 )
  {
    AcquireSRWLockShared(v7 + 58);
    v15[0] = 0;
    MpHashCrc32(v15, 12);
    Ptr = v7[28].Ptr;
    v9 = Ptr[2 * (v15[0] & (__int64)v7[31].Ptr) + 1];
    if ( (PVOID)v9 == v7[26].Ptr )
    {
LABEL_25:
      v9 = 0;
    }
    else
    {
      v10 = Ptr[2 * (v15[0] & (__int64)v7[31].Ptr)];
      while ( this[1].dwLowDateTime != *(_DWORD *)(v9 + 24) || CompareFileTime(this, (const FILETIME *)(v9 + 16)) )
      {
        if ( v9 == v10 )
          goto LABEL_25;
        v9 = *(_QWORD *)(v9 + 8);
      }
    }
    if ( !v9 || (PVOID)v9 == v7[26].Ptr )
    {
      ReleaseSRWLockShared(v7 + 58);
      v5 = 0;
    }
    else
    {
      v11 = *(_QWORD *)(v9 + 164);
      ReleaseSRWLockShared(v7 + 58);
      if ( BYTE4(v11) )
      {
        *(_DWORD *)a2 = v11;
        if ( v6 )
          std::_Ref_count_base::_Decref((std::_Ref_count_base *)v6);
        return 0;
      }
      v5 = 1;
    }
  }
  pSessionId = 0;
  if ( ProcessIdToSessionId(this[1].dwLowDateTime, &pSessionId) )
  {
    if ( v5 && v7 )
      RealtimeProtection::DlpProcessCache::DlpProcessStateCache::TrySetSessionId(
        (RealtimeProtection::DlpProcessCache::DlpProcessStateCache *)v7,
        (const struct PPID *)this,
        pSessionId);
    *(_DWORD *)a2 = pSessionId;
    if ( v6 )
    {
      if ( _InterlockedExchangeAdd(v6 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
        if ( _InterlockedExchangeAdd(v6 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
      }
    }
    return 0;
  }
  LastFailure = HrGetLastFailure();
  if ( v6 )
    std::_Ref_count_base::_Decref((std::_Ref_count_base *)v6);
  return LastFailure;
}

```

## disassembly

```asm
0x180074f60  mov     [rsp+arg_10], rbx
0x180074f65  mov     [rsp+arg_18], rbp
0x180074f6a  push    rsi
0x180074f6b  push    rdi
0x180074f6c  push    r12
0x180074f6e  push    r14
0x180074f70  push    r15
0x180074f72  sub     rsp, 40h
0x180074f76  mov     rax, cs:__security_cookie
0x180074f7d  xor     rax, rsp
0x180074f80  mov     [rsp+68h+var_30], rax
0x180074f85  mov     r14, rdx
0x180074f88  mov     rsi, rcx
0x180074f8b  xor     bl, bl
0x180074f8d  call    _Lock_shared_ptr_spin_lock
0x180074f92  mov     rdi, cs:qword_180314488
0x180074f99  test    rdi, rdi
0x180074f9c  jz      short loc_180074FA9
0x180074f9e  lock inc dword ptr [rdi+8]
0x180074fa2  mov     rdi, cs:qword_180314488
0x180074fa9  mov     rbp, cs:qword_180314480
0x180074fb0  call    _Unlock_shared_ptr_spin_lock
0x180074fb5  nop
0x180074fb6  test    rbp, rbp
0x180074fb9  jz      loc_180075042
0x180074fbf  lea     rcx, [rbp+1D0h]; SRWLock
0x180074fc6  call    cs:__imp_AcquireSRWLockShared
0x180074fcc  mov     [rsp+68h+var_44], 0
0x180074fd4  mov     r8, rsi
0x180074fd7  mov     edx, 0Ch
0x180074fdc  lea     rcx, [rsp+68h+var_44]
0x180074fe1  call    MpHashCrc32
0x180074fe6  mov     eax, [rsp+68h+var_44]
0x180074fea  mov     rcx, [rbp+0F8h]
0x180074ff1  and     rcx, rax
0x180074ff4  add     rcx, rcx
0x180074ff7  mov     rax, [rbp+0E0h]
0x180074ffe  mov     rbx, [rax+rcx*8+8]
0x180075003  cmp     rbx, [rbp+0D0h]
0x18007500a  jz      loc_180075137
0x180075010  mov     r15, [rax+rcx*8]
0x180075014  lea     rdx, [rbx+10h]; lpFileTime2
0x180075018  mov     eax, [rdx+8]
0x18007501b  cmp     [rsi+8], eax
0x18007501e  jz      loc_180075107
0x180075024  cmp     rbx, r15
0x180075027  jz      loc_180075137
0x18007502d  mov     rbx, [rbx+8]
0x180075031  jmp     short loc_180075014
0x180075033  lea     rcx, [rbp+1D0h]; SRWLock
0x18007503a  call    cs:__imp_ReleaseSRWLockShared
0x180075040  xor     bl, bl
0x180075042  mov     [rsp+68h+pSessionId], 0
0x18007504a  lea     rdx, [rsp+68h+pSessionId]; pSessionId
0x18007504f  mov     ecx, [rsi+8]; dwProcessId
0x180075052  call    cs:__imp_ProcessIdToSessionId
0x180075058  test    eax, eax
0x18007505a  jz      loc_180075159
0x180075060  test    bl, bl
0x180075062  jnz     loc_18007513B
0x180075068  mov     eax, [rsp+68h+pSessionId]
0x18007506c  mov     [r14], eax
0x18007506f  test    rdi, rdi
0x180075072  jz      short loc_1800750DF
0x180075074  mov     ebx, 0FFFFFFFFh
0x180075079  mov     eax, ebx
0x18007507b  lock xadd [rdi+8], eax
0x180075080  cmp     eax, 1
0x180075083  jnz     short loc_1800750DF
0x180075085  mov     rax, [rdi]
0x180075088  mov     rcx, rdi
0x18007508b  mov     rax, [rax]
0x18007508e  call    cs:__guard_dispatch_icall_fptr
0x180075094  lock xadd [rdi+0Ch], ebx
0x180075099  cmp     ebx, 1
0x18007509c  jnz     short loc_1800750DF
0x18007509e  mov     rax, [rdi]
0x1800750a1  mov     rcx, rdi
0x1800750a4  mov     rax, [rax+8]
0x1800750a8  call    cs:__guard_dispatch_icall_fptr
0x1800750ae  jmp     short loc_1800750DF
0x1800750b0  mov     rbx, [rbx+0A4h]
0x1800750b7  lea     rcx, [rbp+1D0h]; SRWLock
0x1800750be  call    cs:__imp_ReleaseSRWLockShared
0x1800750c4  mov     rax, rbx
0x1800750c7  shr     rax, 20h
0x1800750cb  test    al, al
0x1800750cd  jz      short loc_180075130
0x1800750cf  mov     [r14], ebx
0x1800750d2  test    rdi, rdi
0x1800750d5  jz      short loc_1800750DF
0x1800750d7  mov     rcx, rdi; this
0x1800750da  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800750df  xor     eax, eax
0x1800750e1  mov     rcx, [rsp+68h+var_30]
0x1800750e6  xor     rcx, rsp; StackCookie
0x1800750e9  call    __security_check_cookie
0x1800750ee  lea     r11, [rsp+68h+var_28]
0x1800750f3  mov     rbx, [r11+40h]
0x1800750f7  mov     rbp, [r11+48h]
0x1800750fb  mov     rsp, r11
0x1800750fe  pop     r15
0x180075100  pop     r14
0x180075102  pop     r12
0x180075104  pop     rdi
0x180075105  pop     rsi
0x180075106  retn
0x180075107  mov     rcx, rsi; lpFileTime1
0x18007510a  call    cs:__imp_CompareFileTime
0x180075110  test    eax, eax
0x180075112  jnz     loc_180075024
0x180075118  test    rbx, rbx
0x18007511b  jz      loc_180075033
0x180075121  cmp     rbx, [rbp+0D0h]
0x180075128  jz      loc_180075033
0x18007512e  jmp     short loc_1800750B0
0x180075130  mov     bl, 1
0x180075132  jmp     loc_180075042
0x180075137  xor     ebx, ebx
0x180075139  jmp     short loc_180075118
0x18007513b  test    rbp, rbp
0x18007513e  jz      loc_180075068
0x180075144  mov     r8d, [rsp+68h+pSessionId]; unsigned int
0x180075149  mov     rdx, rsi; struct PPID *
0x18007514c  mov     rcx, rbp; this
0x18007514f  call    ?TrySetSessionId@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@QEAAXAEBUPPID@@K@Z; RealtimeProtection::DlpProcessCache::DlpProcessStateCache::TrySetSessionId(PPID const &,ulong)
0x180075154  jmp     loc_180075068
0x180075159  call    HrGetLastFailure
0x18007515e  mov     ebx, eax
0x180075160  test    rdi, rdi
0x180075163  jz      short loc_18007516D
0x180075165  mov     rcx, rdi; this
0x180075168  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18007516d  mov     eax, ebx
0x18007516f  jmp     loc_1800750E1
```
