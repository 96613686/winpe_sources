# RealtimeProtection::DlpUserSidCache::GetUserSidFromSessionId(ulong,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x180049280`
- end: `0x1800499ed`
- name: `?GetUserSidFromSessionId@DlpUserSidCache@RealtimeProtection@@YAJKAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `1901`
- prototype: ``
- caller_count: `4`
- callee_count: `21`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180048e20`
- `0x180049090`
- `0x180069838`
- `0x1801a6948`

## callees

- `0x180024ac0`
- `0x180028d80`
- `0x180029590`
- `0x18002c150`
- `0x180037754`
- `0x180037a14`
- `0x180049280`
- `0x18004b3bc`
- `0x18004b514`
- `0x1800809d0`
- `0x180105f50`
- `0x180106d38`
- `0x180109324`
- `0x18010b558`
- `0x18010b568`
- `0x18010cb40`
- `0x18010ce3c`
- `0x18010ce44`
- `0x180119428`
- `0x18023a290`
- `0x18023a6d0`

## import_xrefs

- `KERNEL32!AcquireSRWLockShared` at `0x18004930f`
- `KERNEL32!AcquireSRWLockShared` at `0x18004930f`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800493b1`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800493b1`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180049794`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180049794`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800497c4`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800497c4`
- `KERNEL32!CloseHandle` at `0x1800497e8`
- `KERNEL32!CloseHandle` at `0x18004987b`
- `KERNEL32!CloseHandle` at `0x180049963`
- `KERNEL32!CloseHandle` at `0x1800497e8`
- `KERNEL32!CloseHandle` at `0x18004987b`
- `KERNEL32!CloseHandle` at `0x180049963`
- `WTSAPI32!WTSQueryUserToken` at `0x180049748`
- `WTSAPI32!WTSQueryUserToken` at `0x180049748`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall RealtimeProtection::DlpUserSidCache::GetUserSidFromSessionId(__int64 a1, void **a2, __int64 a3)
{
  volatile signed __int32 *v4; // rdi
  RTL_SRWLOCK *v5; // rbx
  RTL_SRWLOCK *v6; // r12
  unsigned __int64 v7; // rdx
  _QWORD *v8; // rax
  _QWORD *Ptr; // r9
  __int64 v10; // r13
  unsigned __int64 v11; // rdx
  unsigned __int64 v12; // rbx
  void **v13; // r15
  unsigned __int64 v14; // r12
  void *v15; // r13
  const struct std::nothrow_t *v16; // rdx
  void *v17; // rcx
  _QWORD *v19; // r8
  unsigned __int64 v20; // rax
  unsigned __int64 v21; // r12
  size_t v22; // rcx
  void *v23; // rax
  void *v24; // rcx
  size_t v25; // rcx
  void *v26; // rax
  size_t v27; // rbx
  void **v28; // rdx
  void *v29; // r15
  void *v30; // r8
  const struct std::nothrow_t *v31; // rdx
  int StringSidFromToken; // r14d
  __int64 v33; // rax
  int LastFailure; // r15d
  const struct std::nothrow_t *v35; // rdx
  _BYTE v36[32]; // [rsp+0h] [rbp-E8h] BYREF
  void *v37; // [rsp+30h] [rbp-B8h]
  __int128 v38; // [rsp+38h] [rbp-B0h]
  void *v39; // [rsp+48h] [rbp-A0h] BYREF
  RTL_SRWLOCK *v40; // [rsp+58h] [rbp-90h]
  char v41; // [rsp+60h] [rbp-88h]
  const std::exception *v42; // [rsp+68h] [rbp-80h] BYREF
  ULONG SessionId; // [rsp+70h] [rbp-78h] BYREF
  void *phToken; // [rsp+78h] [rbp-70h] BYREF
  void *Src[2]; // [rsp+80h] [rbp-68h] BYREF
  unsigned __int64 v46; // [rsp+90h] [rbp-58h]
  unsigned __int64 v47; // [rsp+98h] [rbp-50h]
  char v48; // [rsp+A0h] [rbp-48h]
  void *v49; // [rsp+A8h] [rbp-40h] BYREF

  SessionId = a1;
  Lock_shared_ptr_spin_lock(a1, a2, a3);
  v38 = 0;
  v4 = (volatile signed __int32 *)qword_180314498;
  if ( qword_180314498 )
  {
    _InterlockedIncrement((volatile signed __int32 *)qword_180314498 + 2);
    v4 = (volatile signed __int32 *)qword_180314498;
  }
  v5 = (RTL_SRWLOCK *)qword_180314490;
  *(_QWORD *)&v38 = qword_180314490;
  *((_QWORD *)&v38 + 1) = v4;
  Unlock_shared_ptr_spin_lock();
  if ( !v5 )
  {
    if ( v4 )
      std::_Ref_count_base::_Decref((std::_Ref_count_base *)v4);
    return 2147483662LL;
  }
  v48 = 0;
  v6 = v5 + 8;
  v40 = v5 + 8;
  AcquireSRWLockShared(v5 + 8);
  v41 = 1;
  _mm_lfence();
  v7 = (unsigned __int64)v5[3].Ptr
     + 16
     * ((unsigned __int64)v5[6].Ptr
      & (0x100000001B3LL
       * (HIBYTE(SessionId)
        ^ (0x100000001B3LL
         * (BYTE2(SessionId)
          ^ (0x100000001B3LL
           * (BYTE1(SessionId) ^ (0x100000001B3LL * ((unsigned __int8)SessionId ^ 0xCBF29CE484222325uLL)))))))));
  v8 = *(_QWORD **)(v7 + 8);
  Ptr = v5[1].Ptr;
  if ( v8 == Ptr )
  {
LABEL_83:
    v8 = 0;
  }
  else
  {
    while ( SessionId != *((_DWORD *)v8 + 4) )
    {
      if ( v8 == *(_QWORD **)v7 )
        goto LABEL_83;
      v8 = (_QWORD *)v8[1];
    }
  }
  if ( !v8 )
    v8 = v5[1].Ptr;
  if ( v8 != Ptr && v8[5] )
  {
    v19 = v8 + 3;
    v39 = v8 + 3;
    *(_OWORD *)Src = 0;
    v46 = 0;
    v47 = 0;
    v20 = v8[5];
    v37 = (void *)v19[2];
    if ( v19[3] > 7u )
    {
      v19 = (_QWORD *)*v19;
      v39 = v19;
    }
    v10 = 0x7FFFFFFFFFFFFFFELL;
    if ( v20 > 0x7FFFFFFFFFFFFFFELL )
      std::_Xlength_error("string too long");
    if ( v20 <= 7 )
    {
      v46 = v20;
      v47 = 7;
      *(_OWORD *)Src = *(_OWORD *)v19;
      v48 = 1;
      goto LABEL_10;
    }
    v21 = v20 | 7;
    if ( (v20 | 7) > 0x7FFFFFFFFFFFFFFELL )
    {
      v21 = 0x7FFFFFFFFFFFFFFELL;
      v22 = -2;
    }
    else
    {
      if ( v21 < 0xA )
        v21 = 10;
      v7 = v21 + 1;
      if ( v21 + 1 > 0x7FFFFFFFFFFFFFFFLL )
        std::_Throw_bad_array_new_length();
      v22 = 2 * v7;
      if ( !(2 * v7) )
      {
        v24 = 0;
LABEL_43:
        Src[0] = v24;
        v46 = v20;
        v47 = v21;
        memmove(v24, v39, 2 * v20 + 2);
        v6 = v5 + 8;
        v48 = 1;
        goto LABEL_10;
      }
    }
    _mm_lfence();
    if ( v22 >= 0x1000 )
      v23 = (void *)std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>(v22, v7);
    else
      v23 = operator new(v22);
    v24 = v23;
    v20 = (unsigned __int64)v37;
    goto LABEL_43;
  }
  v10 = 0x7FFFFFFFFFFFFFFELL;
LABEL_10:
  ReleaseSRWLockShared(v5 + 8);
  if ( v48 )
  {
    if ( a2 == Src )
    {
LABEL_18:
      if ( v48 )
      {
        if ( v47 > 7 )
        {
          v16 = (const struct std::nothrow_t *)(2 * v47 + 2);
          v17 = Src[0];
          if ( (unsigned __int64)v16 >= 0x1000 )
          {
            v16 = (const struct std::nothrow_t *)(2 * v47 + 41);
            v17 = (void *)*((_QWORD *)Src[0] - 1);
            if ( (unsigned __int64)((char *)Src[0] - (char *)v17 - 8) > 0x1F )
              invoke_watson(0, 0, 0, 0, 0);
          }
          operator delete(v17, v16);
        }
        v46 = 0;
        v47 = 7;
        LOWORD(Src[0]) = 0;
      }
      if ( v4 && _InterlockedExchangeAdd(v4 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v4)(v4);
        if ( _InterlockedExchangeAdd(v4 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 8LL))(v4);
      }
      return 0;
    }
    v12 = v46;
    v13 = Src;
    if ( v47 > 7 )
      v13 = (void **)Src[0];
    v14 = (unsigned __int64)a2[3];
    if ( v46 <= v14 )
    {
      v15 = a2;
      if ( v14 > 7 )
        v15 = *a2;
      a2[2] = (void *)v46;
      memmove(v15, v13, 2 * v12);
      *((_WORD *)v15 + v12) = 0;
      goto LABEL_18;
    }
    if ( v46 > 0x7FFFFFFFFFFFFFFELL )
      std::_Xlength_error("string too long");
    if ( (v46 | 7) > 0x7FFFFFFFFFFFFFFELL || (v11 = v14 >> 1, v14 > 0x7FFFFFFFFFFFFFFELL - (v14 >> 1)) )
    {
      v25 = -2;
    }
    else
    {
      v10 = v14 + v11;
      if ( (v46 | 7) >= v14 + v11 )
        v10 = v46 | 7;
      if ( (unsigned __int64)(v10 + 1) > 0x7FFFFFFFFFFFFFFFLL )
        std::_Throw_bad_array_new_length();
      v25 = 2 * (v10 + 1);
      if ( !v25 )
      {
        v37 = 0;
LABEL_54:
        a2[2] = (void *)v12;
        a2[3] = (void *)v10;
        v27 = 2 * v12;
        v28 = v13;
        v29 = v37;
        memmove(v37, v28, v27);
        *(_WORD *)((char *)v37 + v27) = 0;
        if ( v14 > 7 )
        {
          _mm_lfence();
          std::_Deallocate<16>(*a2, 2 * v14 + 2);
        }
        *a2 = v29;
        goto LABEL_18;
      }
    }
    _mm_lfence();
    if ( v25 >= 0x1000 )
      v26 = (void *)std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>(v25, v11);
    else
      v26 = operator new(v25);
    v37 = v26;
    goto LABEL_54;
  }
  phToken = 0;
  if ( WTSQueryUserToken(SessionId, &phToken) || (LastFailure = HrGetLastFailure(), LastFailure >= 0) )
  {
    v49 = 0;
    StringSidFromToken = CommonUtil::UtilGetStringSidFromToken((CommonUtil *)&v49, (wchar_t **)phToken, v30);
    if ( StringSidFromToken >= 0 )
    {
      std::wstring::assign(a2, v49);
      v40 = v6;
      AcquireSRWLockExclusive(v6);
      try
      {
        v41 = 1;
        v33 = std::_Hash<std::_Umap_traits<unsigned long,std::wstring,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,std::wstring>>,0>>::_Try_emplace<unsigned long const &,>(
                v5,
                &v39,
                &SessionId);
        std::wstring::operator=((void *)(*(_QWORD *)v33 + 24LL), a2);
        ReleaseSRWLockExclusive(v6);
      }
      catch ( const std::exception *v42 )
      {
        CommonUtil::HrFromStdException(v42, (const struct std::exception *)v36);
      }
      catch ( ... )
      {
        v35 = (const struct std::nothrow_t *)v36;
        LODWORD(v37) = -2147467259;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            15,
            WPP_3aa1f00f36e330821d5f037f1b346392_Traceguids,
            (unsigned int)v37);
        v4 = (volatile signed __int32 *)*((_QWORD *)&v38 + 1);
      }
      if ( v49 )
        operator delete(v49, v35);
      if ( phToken )
        CloseHandle(phToken);
      std::optional<std::wstring>::~optional<std::wstring>(Src);
      if ( v4 )
        std::_Ref_count_base::_Decref((std::_Ref_count_base *)v4);
      return 0;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        WPP_3aa1f00f36e330821d5f037f1b346392_Traceguids,
        (unsigned int)StringSidFromToken);
    if ( v49 )
      operator delete(v49, v31);
    if ( phToken )
      CloseHandle(phToken);
    std::optional<std::wstring>::~optional<std::wstring>(Src);
    if ( v4 )
      std::_Ref_count_base::_Decref((std::_Ref_count_base *)v4);
    return (unsigned int)StringSidFromToken;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        WPP_3aa1f00f36e330821d5f037f1b346392_Traceguids,
        (unsigned int)LastFailure);
    if ( phToken )
      CloseHandle(phToken);
    std::optional<std::wstring>::~optional<std::wstring>(Src);
    if ( v4 )
      std::_Ref_count_base::_Decref((std::_Ref_count_base *)v4);
    return (unsigned int)LastFailure;
  }
}

```

## disassembly

```asm
0x180049280  mov     [rsp+arg_10], rbx
0x180049285  mov     [rsp+arg_18], rsi
0x18004928a  push    rdi
0x18004928b  push    r12
0x18004928d  push    r13
0x18004928f  push    r14
0x180049291  push    r15
0x180049293  sub     rsp, 0C0h
0x18004929a  mov     rax, cs:__security_cookie
0x1800492a1  xor     rax, rsp
0x1800492a4  mov     [rsp+0E8h+var_38], rax
0x1800492ac  mov     rsi, rdx
0x1800492af  mov     [rsp+0E8h+SessionId], ecx
0x1800492b3  call    _Lock_shared_ptr_spin_lock
0x1800492b8  xorps   xmm0, xmm0
0x1800492bb  movups  [rsp+0E8h+var_B0], xmm0
0x1800492c0  mov     rdi, cs:qword_180314498
0x1800492c7  test    rdi, rdi
0x1800492ca  jz      short loc_1800492D7
0x1800492cc  lock inc dword ptr [rdi+8]
0x1800492d0  mov     rdi, cs:qword_180314498
0x1800492d7  mov     rbx, cs:qword_180314490
0x1800492de  mov     qword ptr [rsp+0E8h+var_B0], rbx
0x1800492e3  mov     qword ptr [rsp+0E8h+var_B0+8], rdi
0x1800492e8  call    _Unlock_shared_ptr_spin_lock
0x1800492ed  nop
0x1800492ee  test    rbx, rbx
0x1800492f1  jz      loc_1800499D6
0x1800492f7  mov     [rsp+0E8h+var_48], 0
0x1800492ff  lea     r12, [rbx+40h]
0x180049303  lea     r15, [rbx+40h]
0x180049307  mov     [rsp+0E8h+var_90], r15
0x18004930c  mov     rcx, r15; SRWLock
0x18004930f  call    cs:__imp_AcquireSRWLockShared
0x180049315  mov     [rsp+0E8h+var_88], 1
0x18004931a  lfence
0x18004931d  mov     r8d, [rsp+0E8h+SessionId]
0x180049322  movzx   ecx, r8b
0x180049326  mov     rax, 0CBF29CE484222325h
0x180049330  xor     rcx, rax
0x180049333  mov     rdx, 100000001B3h
0x18004933d  imul    rcx, rdx
0x180049341  movzx   eax, byte ptr [rsp+0E8h+SessionId+1]
0x180049346  xor     rcx, rax
0x180049349  imul    rcx, rdx
0x18004934d  movzx   eax, byte ptr [rsp+0E8h+SessionId+2]
0x180049352  xor     rcx, rax
0x180049355  imul    rcx, rdx
0x180049359  movzx   eax, byte ptr [rsp+0E8h+SessionId+3]
0x18004935e  xor     rcx, rax
0x180049361  imul    rdx, rcx
0x180049365  and     rdx, [rbx+30h]
0x180049369  shl     rdx, 4
0x18004936d  add     rdx, [rbx+18h]
0x180049371  mov     rax, [rdx+8]
0x180049375  mov     r9, [rbx+8]
0x180049379  cmp     rax, r9
0x18004937c  jz      loc_1800498A5
0x180049382  mov     rcx, [rdx]
0x180049385  cmp     r8d, [rax+10h]
0x180049389  jnz     loc_1800494E2
0x18004938f  xor     r14d, r14d
0x180049392  test    rax, rax
0x180049395  jz      loc_1800498DE
0x18004939b  cmp     rax, r9
0x18004939e  jnz     loc_1800494F4
0x1800493a4  mov     r13, 7FFFFFFFFFFFFFFEh
0x1800493ae  mov     rcx, r15; SRWLock
0x1800493b1  call    cs:__imp_ReleaseSRWLockShared
0x1800493b7  cmp     [rsp+0E8h+var_48], 0
0x1800493bf  jz      loc_18004973A
0x1800493c5  lea     rax, [rsp+0E8h+Src]
0x1800493cd  cmp     rsi, rax
0x1800493d0  jz      short loc_180049426
0x1800493d2  mov     rbx, [rsp+0E8h+var_58]
0x1800493da  lea     r15, [rsp+0E8h+Src]
0x1800493e2  cmp     [rsp+0E8h+var_50], 7
0x1800493eb  cmova   r15, [rsp+0E8h+Src]
0x1800493f4  mov     r12, [rsi+18h]
0x1800493f8  cmp     rbx, r12
0x1800493fb  ja      loc_1800495FF
0x180049401  mov     r13, rsi
0x180049404  cmp     r12, 7
0x180049408  jbe     short loc_18004940D
0x18004940a  mov     r13, [rsi]
0x18004940d  mov     [rsi+10h], rbx
0x180049411  lea     r8, [rbx+rbx]; Size
0x180049415  mov     rdx, r15; Src
0x180049418  mov     rcx, r13; void *
0x18004941b  call    memmove
0x180049420  mov     [r13+rbx*2+0], r14w
0x180049426  cmp     [rsp+0E8h+var_48], 0
0x18004942e  jz      short loc_180049480
0x180049430  mov     rax, [rsp+0E8h+var_50]
0x180049438  cmp     rax, 7
0x18004943c  jbe     short loc_180049463
0x18004943e  lea     rdx, ds:2[rax*2]; struct std::nothrow_t *
0x180049446  mov     rcx, [rsp+0E8h+Src]; void *
0x18004944e  mov     rax, rcx
0x180049451  cmp     rdx, 1000h
0x180049458  jnb     loc_1800498B0
0x18004945e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180049463  mov     [rsp+0E8h+var_58], r14
0x18004946b  mov     [rsp+0E8h+var_50], 7
0x180049477  mov     word ptr [rsp+0E8h+Src], r14w
0x180049480  test    rdi, rdi
0x180049483  jz      short loc_1800494B3
0x180049485  mov     ebx, 0FFFFFFFFh
0x18004948a  mov     eax, ebx
0x18004948c  lock xadd [rdi+8], eax
0x180049491  cmp     eax, 1
0x180049494  jnz     short loc_1800494B3
0x180049496  mov     rax, [rdi]
0x180049499  mov     rcx, rdi
0x18004949c  mov     rax, [rax]
0x18004949f  call    cs:__guard_dispatch_icall_fptr
0x1800494a5  lock xadd [rdi+0Ch], ebx
0x1800494aa  cmp     ebx, 1
0x1800494ad  jz      loc_1800496A3
0x1800494b3  xor     eax, eax
0x1800494b5  mov     rcx, [rsp+0E8h+var_38]
0x1800494bd  xor     rcx, rsp; StackCookie
0x1800494c0  call    __security_check_cookie
0x1800494c5  lea     r11, [rsp+0E8h+var_28]
0x1800494cd  mov     rbx, [r11+40h]
0x1800494d1  mov     rsi, [r11+48h]
0x1800494d5  mov     rsp, r11
0x1800494d8  pop     r15
0x1800494da  pop     r14
0x1800494dc  pop     r13
0x1800494de  pop     r12
0x1800494e0  pop     rdi
0x1800494e1  retn
0x1800494e2  cmp     rax, rcx
0x1800494e5  jz      loc_1800498A5
0x1800494eb  mov     rax, [rax+8]
0x1800494ef  jmp     loc_180049385
0x1800494f4  cmp     qword ptr [rax+28h], 0
0x1800494f9  jz      loc_1800493A4
0x1800494ff  lea     r8, [rax+18h]
0x180049503  mov     [rsp+0E8h+var_A0], r8
0x180049508  cmp     [rsp+0E8h+var_48], 0
0x180049510  jnz     loc_1800498E6
0x180049516  xorps   xmm0, xmm0
0x180049519  movups  xmmword ptr [rsp+0E8h+Src], xmm0
0x180049521  mov     [rsp+0E8h+var_58], r14
0x180049529  mov     [rsp+0E8h+var_50], r14
0x180049531  mov     rax, [r8+10h]
0x180049535  mov     [rsp+0E8h+var_B8], rax
0x18004953a  cmp     qword ptr [r8+18h], 7
0x18004953f  jbe     short loc_180049549
0x180049541  mov     r8, [r8]
0x180049544  mov     [rsp+0E8h+var_A0], r8
0x180049549  mov     r13, 7FFFFFFFFFFFFFFEh
0x180049553  cmp     rax, r13
0x180049556  ja      loc_1800498FB
0x18004955c  cmp     rax, 7
0x180049560  jbe     loc_1800496D5
0x180049566  mov     r12, rax
0x180049569  or      r12, 7
0x18004956d  cmp     r12, r13
0x180049570  ja      loc_180049702
0x180049576  mov     ecx, 0Ah
0x18004957b  cmp     r12, rcx
0x18004957e  cmovb   r12, rcx
0x180049582  lea     rdx, [r12+1]
0x180049587  mov     rcx, 7FFFFFFFFFFFFFFFh
0x180049591  cmp     rdx, rcx
0x180049594  ja      loc_180049908
0x18004959a  lea     rcx, [rdx+rdx]; Size
0x18004959e  test    rcx, rcx
0x1800495a1  jz      loc_180049827
0x1800495a7  lfence
0x1800495aa  cmp     rcx, 1000h
0x1800495b1  jnb     loc_180049813
0x1800495b7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800495bc  mov     rcx, rax; void *
0x1800495bf  mov     rax, [rsp+0E8h+var_B8]
0x1800495c4  mov     [rsp+0E8h+Src], rcx
0x1800495cc  mov     [rsp+0E8h+var_58], rax
0x1800495d4  mov     [rsp+0E8h+var_50], r12
0x1800495dc  lea     r8, ds:2[rax*2]; Size
0x1800495e4  mov     rdx, [rsp+0E8h+var_A0]; Src
0x1800495e9  call    memmove
0x1800495ee  lea     r12, [rbx+40h]
0x1800495f2  mov     [rsp+0E8h+var_48], 1
0x1800495fa  jmp     loc_1800493AE
0x1800495ff  cmp     rbx, r13
0x180049602  ja      loc_1800496B8
0x180049608  mov     rcx, rbx
0x18004960b  or      rcx, 7
0x18004960f  cmp     rcx, r13
0x180049612  ja      loc_1800496C5
0x180049618  mov     rdx, r12
0x18004961b  shr     rdx, 1
0x18004961e  mov     rax, r13
0x180049621  sub     rax, rdx
0x180049624  cmp     r12, rax
0x180049627  mov     rax, 7FFFFFFFFFFFFFFFh
0x180049631  ja      loc_1800496CF
0x180049637  lea     r13, [r12+rdx]
0x18004963b  cmp     rcx, r13
0x18004963e  cmovnb  r13, rcx
0x180049642  lea     rcx, [r13+1]
0x180049646  cmp     rcx, rax
0x180049649  ja      loc_18004990E
0x18004964f  add     rcx, rcx; Size
0x180049652  jz      loc_18004981D
0x180049658  lfence
0x18004965b  cmp     rcx, 1000h
0x180049662  jnb     loc_180049730
0x180049668  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004966d  mov     [rsp+0E8h+var_B8], rax
0x180049672  mov     [rsi+10h], rbx
0x180049676  mov     [rsi+18h], r13
0x18004967a  add     rbx, rbx
0x18004967d  mov     r8, rbx; Size
0x180049680  mov     rdx, r15; Src
0x180049683  mov     r15, [rsp+0E8h+var_B8]
0x180049688  mov     rcx, r15; void *
0x18004968b  call    memmove
0x180049690  mov     [rbx+r15], r14w
0x180049695  cmp     r12, 7
0x180049699  ja      short loc_180049718
0x18004969b  mov     [rsi], r15
0x18004969e  jmp     loc_180049426
0x1800496a3  mov     rax, [rdi]
0x1800496a6  mov     rcx, rdi
0x1800496a9  mov     rax, [rax+8]
0x1800496ad  call    cs:__guard_dispatch_icall_fptr
0x1800496b3  jmp     loc_1800494B3
0x1800496b8  lea     rcx, aStringTooLong; "string too long"
0x1800496bf  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1800496c5  mov     rax, 7FFFFFFFFFFFFFFFh
0x1800496cf  lea     rcx, [rax+rax]
0x1800496d3  jmp     short loc_180049658
0x1800496d5  mov     [rsp+0E8h+var_58], rax
0x1800496dd  mov     [rsp+0E8h+var_50], 7
0x1800496e9  movups  xmm0, xmmword ptr [r8]
0x1800496ed  movups  xmmword ptr [rsp+0E8h+Src], xmm0
0x1800496f5  mov     [rsp+0E8h+var_48], 1
0x1800496fd  jmp     loc_1800493AE
0x180049702  mov     r12, r13
0x180049705  mov     rax, 7FFFFFFFFFFFFFFFh
0x18004970f  lea     rcx, [rax+rax]
0x180049713  jmp     loc_1800495A7
0x180049718  lfence
0x18004971b  lea     rdx, ds:2[r12*2]
0x180049723  mov     rcx, [rsi]
0x180049726  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18004972b  jmp     loc_18004969B
0x180049730  call    ??$_Allocate_manually_vector_aligned@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>(unsigned __int64)
0x180049735  jmp     loc_18004966D
0x18004973a  mov     [rsp+0E8h+phToken], r14
0x18004973f  lea     rdx, [rsp+0E8h+phToken]; phToken
0x180049744  mov     ecx, [rsp+0E8h+SessionId]; SessionId
0x180049748  call    cs:__imp_WTSQueryUserToken
0x18004974e  test    eax, eax
0x180049750  jz      loc_18004982F
0x180049756  mov     [rsp+0E8h+var_40], r14
0x18004975e  mov     rdx, [rsp+0E8h+phToken]; wchar_t **
0x180049763  lea     rcx, [rsp+0E8h+var_40]; this
0x18004976b  call    ?UtilGetStringSidFromToken@CommonUtil@@YAJPEAPEA_WPEAX@Z; CommonUtil::UtilGetStringSidFromToken(wchar_t * *,void *)
0x180049770  mov     r14d, eax
0x180049773  test    eax, eax
0x180049775  js      loc_180049914
0x18004977b  mov     rdx, [rsp+0E8h+var_40]; Src
0x180049783  mov     rcx, rsi; void *
0x180049786  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18004978b  nop
0x18004978c  mov     [rsp+0E8h+var_90], r12
0x180049791  mov     rcx, r12; SRWLock
0x180049794  call    cs:__imp_AcquireSRWLockExclusive
0x18004979a  mov     [rsp+0E8h+var_88], 1
0x18004979f  lea     r8, [rsp+0E8h+SessionId]
0x1800497a4  lea     rdx, [rsp+0E8h+var_A0]
0x1800497a9  mov     rcx, rbx
0x1800497ac  call    ??$_Try_emplace@AEBK$$V@?$_Hash@V?$_Umap_traits@KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@2@V?$allocator@U?$pair@$$CBKV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBKV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@PEAX@std@@_N@1@AEBK@Z; std::_Hash<std::_Umap_traits<ulong,std::wstring,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,std::wstring>>,0>>::_Try_emplace<ulong const &,>(ulong const &)
0x1800497b1  mov     rcx, [rax]
0x1800497b4  add     rcx, 18h; void *
0x1800497b8  mov     rdx, rsi; Src
0x1800497bb  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800497c0  nop
0x1800497c1  mov     rcx, r12; SRWLock
0x1800497c4  call    cs:__imp_ReleaseSRWLockExclusive
0x1800497ca  nop
0x1800497cb  mov     rcx, [rsp+0E8h+var_40]; void *
0x1800497d3  test    rcx, rcx
0x1800497d6  jz      short loc_1800497DE
0x1800497d8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800497dd  nop
0x1800497de  mov     rcx, [rsp+0E8h+phToken]; hObject
0x1800497e3  test    rcx, rcx
0x1800497e6  jz      short loc_1800497EF
0x1800497e8  call    cs:__imp_CloseHandle
0x1800497ee  nop
0x1800497ef  lea     rcx, [rsp+0E8h+Src]
0x1800497f7  call    ??1?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEAA@XZ; std::optional<std::wstring>::~optional<std::wstring>(void)
0x1800497fc  nop
0x1800497fd  test    rdi, rdi
  ... truncated ...
```
