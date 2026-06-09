# RealtimeProtection::DlpProcessCache::GetDlpDelegationFlag(PPID const &,bool &)

- ea: `0x180092a68`
- end: `0x180092c49`
- name: `?GetDlpDelegationFlag@DlpProcessCache@RealtimeProtection@@YAJAEBUPPID@@AEA_N@Z`
- size: `481`
- prototype: `__int64 __fastcall(FILETIME *lpFileTime1, const struct PPID *, bool *)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800857d0`
- `0x18009d7b0`

## callees

- `0x180028d80`
- `0x180046d10`
- `0x180092a68`
- `0x180107874`
- `0x18010b558`
- `0x18010b568`
- `0x18010cb40`
- `0x18023a290`

## import_xrefs

- `KERNEL32!AcquireSRWLockShared` at `0x180092ad5`
- `KERNEL32!AcquireSRWLockShared` at `0x180092ad5`
- `KERNEL32!ReleaseSRWLockShared` at `0x180092b73`
- `KERNEL32!ReleaseSRWLockShared` at `0x180092c27`
- `KERNEL32!ReleaseSRWLockShared` at `0x180092b73`
- `KERNEL32!ReleaseSRWLockShared` at `0x180092c27`
- `KERNEL32!CompareFileTime` at `0x180092b43`
- `KERNEL32!CompareFileTime` at `0x180092b43`

## pseudocode

```c
__int64 __fastcall RealtimeProtection::DlpProcessCache::GetDlpDelegationFlag(
        FILETIME *lpFileTime1,
        const struct PPID *a2,
        bool *a3)
{
  volatile signed __int32 *v5; // rbx
  unsigned int v6; // esi
  RTL_SRWLOCK *v7; // rbp
  _QWORD *Ptr; // r13
  __int64 v9; // rdi
  __int64 v10; // r13
  unsigned int v12; // [rsp+30h] [rbp-48h] BYREF

  Lock_shared_ptr_spin_lock(lpFileTime1, a2, a3);
  v5 = (volatile signed __int32 *)qword_180314488;
  v6 = 1;
  if ( qword_180314488 )
  {
    _InterlockedAdd((volatile signed __int32 *)qword_180314488 + 2, 1u);
    v5 = (volatile signed __int32 *)qword_180314488;
  }
  v7 = (RTL_SRWLOCK *)qword_180314480;
  Unlock_shared_ptr_spin_lock();
  if ( v7 )
  {
    *(_BYTE *)a2 = 0;
    AcquireSRWLockShared(v7 + 58);
    v12 = 0;
    MpHashCrc32(&v12, 12);
    Ptr = v7[28].Ptr;
    v9 = Ptr[2 * (v12 & (__int64)v7[31].Ptr) + 1];
    if ( (PVOID)v9 == v7[26].Ptr )
    {
LABEL_21:
      v9 = 0;
    }
    else
    {
      v10 = Ptr[2 * (v12 & (__int64)v7[31].Ptr)];
      while ( lpFileTime1[1].dwLowDateTime != *(_DWORD *)(v9 + 24)
           || CompareFileTime(lpFileTime1, (const FILETIME *)(v9 + 16)) )
      {
        if ( v9 == v10 )
          goto LABEL_21;
        v9 = *(_QWORD *)(v9 + 8);
      }
    }
    if ( !v9 || (PVOID)v9 == v7[26].Ptr )
    {
      ReleaseSRWLockShared(v7 + 58);
    }
    else
    {
      *(_BYTE *)a2 = *(_DWORD *)(v9 + 504) != 0;
      ReleaseSRWLockShared(v7 + 58);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          159,
          &WPP_37379ce3a908304aafca380d907f5915_Traceguids,
          lpFileTime1[1].dwLowDateTime,
          *(unsigned __int8 *)a2);
      v6 = 0;
    }
    if ( v5 && _InterlockedExchangeAdd(v5 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v5)(v5);
      if ( _InterlockedExchangeAdd(v5 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 8LL))(v5);
    }
    return v6;
  }
  else
  {
    if ( v5 )
      std::_Ref_count_base::_Decref((std::_Ref_count_base *)v5);
    return 2147483662LL;
  }
}

```

## disassembly

```asm
0x180092a68  mov     [rsp+arg_10], rbx
0x180092a6d  push    rbp
0x180092a6e  push    rsi
0x180092a6f  push    rdi
0x180092a70  push    r12
0x180092a72  push    r13
0x180092a74  push    r14
0x180092a76  push    r15
0x180092a78  sub     rsp, 40h
0x180092a7c  mov     rax, cs:__security_cookie
0x180092a83  xor     rax, rsp
0x180092a86  mov     [rsp+78h+var_40], rax
0x180092a8b  mov     r15, rdx
0x180092a8e  mov     r14, rcx
0x180092a91  call    _Lock_shared_ptr_spin_lock
0x180092a96  mov     rbx, cs:qword_180314488
0x180092a9d  mov     esi, 1
0x180092aa2  test    rbx, rbx
0x180092aa5  jz      short loc_180092AB2
0x180092aa7  lock add [rbx+8], esi
0x180092aab  mov     rbx, cs:qword_180314488
0x180092ab2  mov     rbp, cs:qword_180314480
0x180092ab9  call    _Unlock_shared_ptr_spin_lock
0x180092abe  test    rbp, rbp
0x180092ac1  jz      loc_180092C32
0x180092ac7  lea     r12, [rbp+1D0h]
0x180092ace  mov     byte ptr [r15], 0
0x180092ad2  mov     rcx, r12; SRWLock
0x180092ad5  call    cs:__imp_AcquireSRWLockShared
0x180092adb  mov     r8, r14
0x180092ade  mov     [rsp+78h+var_48], 0
0x180092ae6  mov     edx, 0Ch
0x180092aeb  lea     rcx, [rsp+78h+var_48]
0x180092af0  call    MpHashCrc32
0x180092af5  mov     eax, [rsp+78h+var_48]
0x180092af9  mov     rcx, [rbp+0F8h]
0x180092b00  mov     r13, [rbp+0E0h]
0x180092b07  and     rcx, rax
0x180092b0a  add     rcx, rcx
0x180092b0d  mov     rdi, [r13+rcx*8+8]
0x180092b12  cmp     rdi, [rbp+0D0h]
0x180092b19  jz      loc_180092C1D
0x180092b1f  mov     r13, [r13+rcx*8+0]
0x180092b24  lea     rdx, [rdi+10h]; lpFileTime2
0x180092b28  mov     eax, [rdx+8]
0x180092b2b  cmp     [r14+8], eax
0x180092b2f  jz      short loc_180092B40
0x180092b31  cmp     rdi, r13
0x180092b34  jz      loc_180092C1D
0x180092b3a  mov     rdi, [rdi+8]
0x180092b3e  jmp     short loc_180092B24
0x180092b40  mov     rcx, r14; lpFileTime1
0x180092b43  call    cs:__imp_CompareFileTime
0x180092b49  test    eax, eax
0x180092b4b  jnz     short loc_180092B31
0x180092b4d  test    rdi, rdi
0x180092b50  jz      loc_180092C24
0x180092b56  cmp     rdi, [rbp+0D0h]
0x180092b5d  jz      loc_180092C24
0x180092b63  cmp     dword ptr [rdi+1F8h], 0
0x180092b6a  mov     rcx, r12; SRWLock
0x180092b6d  setnbe  al
0x180092b70  mov     [r15], al
0x180092b73  call    cs:__imp_ReleaseSRWLockShared
0x180092b79  mov     rcx, cs:WPP_GLOBAL_Control
0x180092b80  lea     rax, WPP_GLOBAL_Control
0x180092b87  cmp     rcx, rax
0x180092b8a  jnz     short loc_180092BE2
0x180092b8c  xor     esi, esi
0x180092b8e  test    rbx, rbx
0x180092b91  jz      short loc_180092BBB
0x180092b93  or      edi, 0FFFFFFFFh
0x180092b96  mov     eax, edi
0x180092b98  lock xadd [rbx+8], eax
0x180092b9d  add     eax, edi
0x180092b9f  jnz     short loc_180092BBB
0x180092ba1  mov     rax, [rbx]
0x180092ba4  mov     rcx, rbx
0x180092ba7  mov     rax, [rax]
0x180092baa  call    cs:__guard_dispatch_icall_fptr
0x180092bb0  mov     edx, edi
0x180092bb2  lock xadd [rbx+0Ch], edx
0x180092bb7  add     edx, edi
0x180092bb9  jz      short loc_180092C0B
0x180092bbb  mov     eax, esi
0x180092bbd  mov     rcx, [rsp+78h+var_40]
0x180092bc2  xor     rcx, rsp; StackCookie
0x180092bc5  call    __security_check_cookie
0x180092bca  mov     rbx, [rsp+78h+arg_10]
0x180092bd2  add     rsp, 40h
0x180092bd6  pop     r15
0x180092bd8  pop     r14
0x180092bda  pop     r13
0x180092bdc  pop     r12
0x180092bde  pop     rdi
0x180092bdf  pop     rsi
0x180092be0  pop     rbp
0x180092be1  retn
0x180092be2  test    byte ptr [rcx+1Ch], 10h
0x180092be6  jz      short loc_180092B8C
0x180092be8  movzx   eax, byte ptr [r15]
0x180092bec  lea     r8, WPP_37379ce3a908304aafca380d907f5915_Traceguids
0x180092bf3  mov     r9d, [r14+8]
0x180092bf7  mov     edx, 9Fh
0x180092bfc  mov     rcx, [rcx+10h]
0x180092c00  mov     [rsp+78h+var_58], eax
0x180092c04  call    WPP_SF_Dd
0x180092c09  jmp     short loc_180092B8C
0x180092c0b  mov     rdx, [rbx]
0x180092c0e  mov     rcx, rbx
0x180092c11  mov     rax, [rdx+8]
0x180092c15  call    cs:__guard_dispatch_icall_fptr
0x180092c1b  jmp     short loc_180092BBB
0x180092c1d  xor     edi, edi
0x180092c1f  jmp     loc_180092B4D
0x180092c24  mov     rcx, r12; SRWLock
0x180092c27  call    cs:__imp_ReleaseSRWLockShared
0x180092c2d  jmp     loc_180092B8E
0x180092c32  test    rbx, rbx
0x180092c35  jz      short loc_180092C3F
0x180092c37  mov     rcx, rbx; this
0x180092c3a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180092c3f  mov     eax, 8000000Eh
0x180092c44  jmp     loc_180092BBD
```
