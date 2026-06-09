# RealtimeProtection::DlpProcessCache::DlpProcessStateCache::GetExtensionEnforcementProperty(PPID const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,ulong &,DlpAction *,DlpAppGroupInfo &,DlpUnallowedAppType &,uchar &)

- ea: `0x18002c504`
- end: `0x18002c98f`
- name: `?GetExtensionEnforcementProperty@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@QEAAJAEBUPPID@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV56@2AEAKPEAUDlpAction@@AEAUDlpAppGroupInfo@@AEAW4DlpUnallowedAppType@@AEAE@Z`
- size: `1163`
- prototype: `__int64 __usercall@<rax>(RealtimeProtection::DlpProcessCache::DlpProcessStateCache *this@<rcx>, struct PPID *@<rdx>, LPCWCH lpString1@<r8>, void *, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180084f38`

## callees

- `0x180024ac0`
- `0x18002ba50`
- `0x18002c504`
- `0x18002c990`
- `0x18002dcc0`
- `0x1800376e0`
- `0x180109324`
- `0x18023a6d0`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x18002c5ff`
- `KERNEL32!CompareStringOrdinal` at `0x18002c5ff`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18002c580`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18002c580`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18002c7bd`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18002c932`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18002c974`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18002c7bd`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18002c932`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18002c974`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall RealtimeProtection::DlpProcessCache::DlpProcessStateCache::GetExtensionEnforcementProperty(
        RTL_SRWLOCK *this,
        const FILETIME *a2,
        const WCHAR *lpString1,
        char *a4,
        _QWORD *a5,
        _DWORD *a6,
        unsigned int *a7,
        _WORD *a8,
        _DWORD *a9,
        _BYTE *a10)
{
  FILETIME *ProcessFromCacheUnsafe; // rdi
  __int64 v15; // rcx
  __int64 v16; // rax
  FILETIME v17; // rcx
  __int64 v18; // rsi
  __int64 v19; // r13
  const WCHAR *v20; // r8
  const WCHAR *v21; // rcx
  unsigned int v22; // ecx
  unsigned int *v23; // rdx
  _QWORD *v24; // r15
  unsigned __int64 v25; // r13
  unsigned __int64 v26; // r12
  void *v27; // rdi
  __int64 v28; // rdi
  _QWORD *v29; // r15
  unsigned __int64 v30; // rbx
  unsigned __int64 v31; // r12
  char *v32; // rdi
  size_t v33; // rbx
  unsigned __int64 v34; // r8
  _QWORD *v35; // rdx
  unsigned __int64 v36; // r8
  _QWORD *v37; // rdx
  unsigned __int64 v38; // r8
  _QWORD *v39; // rdx
  unsigned __int64 v41; // rdx
  __int64 v42; // rbx
  __int64 size_of; // rax
  unsigned __int64 v44; // rdx
  __int64 v45; // rax
  char *v46; // r13
  size_t v47; // rbx
  void *v49; // [rsp+48h] [rbp-70h]
  RTL_SRWLOCK *SRWLock; // [rsp+50h] [rbp-68h]

  SRWLock = this + 58;
  AcquireSRWLockExclusive(this + 58);
  ProcessFromCacheUnsafe = RealtimeProtection::DlpProcessCache::DlpProcessStateCache::GetProcessFromCacheUnsafe(
                             (RealtimeProtection::DlpProcessCache::DlpProcessStateCache *)this,
                             a2);
  *a10 = ProcessFromCacheUnsafe[17].dwHighDateTime;
  v16 = 2
      * (std::_Uhash_compare<std::wstring,RealtimeProtection::DlpUtils::CaseInsensitiveHasher,RealtimeProtection::DlpUtils::CStrOrdinalCompEqual>::operator()<std::wstring>(
           v15,
           lpString1)
       & *(_QWORD *)&ProcessFromCacheUnsafe[32]);
  v17 = ProcessFromCacheUnsafe[29];
  v18 = *(_QWORD *)(*(_QWORD *)&v17 + 8 * v16 + 8);
  if ( v18 == *(_QWORD *)&ProcessFromCacheUnsafe[27] )
  {
LABEL_9:
    v18 = 0;
  }
  else
  {
    v19 = *(_QWORD *)(*(_QWORD *)&v17 + 8 * v16);
    while ( 1 )
    {
      v20 = (const WCHAR *)(v18 + 16);
      if ( *(_QWORD *)(v18 + 40) > 7u )
        v20 = *(const WCHAR **)v20;
      v21 = lpString1;
      if ( *((_QWORD *)lpString1 + 3) > 7u )
        v21 = *(const WCHAR **)lpString1;
      if ( CompareStringOrdinal(v21, -1, v20, -1, 1) == 2 )
        break;
      if ( v18 == v19 )
        goto LABEL_9;
      v18 = *(_QWORD *)(v18 + 8);
    }
  }
  if ( !v18 || v18 == *(_QWORD *)&ProcessFromCacheUnsafe[27] )
  {
    ReleaseSRWLockExclusive(SRWLock);
    return 2147943568LL;
  }
  if ( *a6 != 10 )
  {
    ReleaseSRWLockExclusive(SRWLock);
    return 2147500037LL;
  }
  *a6 = 10;
  v22 = 0;
  v23 = (unsigned int *)(v18 + 152);
  do
  {
    *a7 = v22;
    a7[1] = *v23;
    ++v22;
    ++v23;
    a7 += 2;
  }
  while ( v22 < 0xA );
  v24 = (_QWORD *)(v18 + 88);
  if ( a5 != (_QWORD *)(v18 + 88) )
  {
    v25 = *(_QWORD *)(v18 + 104);
    if ( *(_QWORD *)(v18 + 112) > 7u )
      v24 = (_QWORD *)*v24;
    v26 = a5[3];
    if ( v25 > v26 )
    {
      v28 = 0x7FFFFFFFFFFFFFFELL;
      if ( v25 > 0x7FFFFFFFFFFFFFFELL )
        std::_Xlength_error("string too long");
      _mm_lfence();
      if ( (v25 | 7) > 0x7FFFFFFFFFFFFFFELL || (v41 = v26 >> 1, v26 > 0x7FFFFFFFFFFFFFFELL - (v26 >> 1)) )
      {
        v42 = 0x7FFFFFFFFFFFFFFELL;
      }
      else
      {
        v42 = v26 + v41;
        if ( (v25 | 7) >= v26 + v41 )
          v42 = v25 | 7;
      }
      size_of = std::_Get_size_of_n<2>(v42 + 1);
      _mm_lfence();
      v49 = (void *)std::_Allocate<16,std::_Default_allocate_traits>(size_of);
      a5[2] = v25;
      a5[3] = v42;
      memmove(v49, v24, 2 * v25);
      *((_WORD *)v49 + v25) = 0;
      if ( v26 > 7 )
      {
        _mm_lfence();
        std::_Deallocate<16>(*a5, 2 * v26 + 2);
      }
      *a5 = v49;
      goto LABEL_23;
    }
    v27 = a5;
    if ( v26 > 7 )
      v27 = (void *)*a5;
    a5[2] = v25;
    memmove(v27, v24, 2 * v25);
    *((_WORD *)v27 + v25) = 0;
  }
  v28 = 0x7FFFFFFFFFFFFFFELL;
LABEL_23:
  v29 = (_QWORD *)(v18 + 120);
  if ( a4 != (char *)(v18 + 120) )
  {
    v30 = *(_QWORD *)(v18 + 136);
    if ( *(_QWORD *)(v18 + 144) > 7u )
      v29 = (_QWORD *)*v29;
    v31 = *((_QWORD *)a4 + 3);
    if ( v30 > v31 )
    {
      if ( v30 > 0x7FFFFFFFFFFFFFFELL )
        std::_Xlength_error("string too long");
      _mm_lfence();
      if ( (v30 | 7) <= 0x7FFFFFFFFFFFFFFELL )
      {
        v44 = v31 >> 1;
        if ( v31 <= 0x7FFFFFFFFFFFFFFELL - (v31 >> 1) )
        {
          v28 = v44 + v31;
          if ( (v30 | 7) >= v44 + v31 )
            v28 = v30 | 7;
        }
      }
      v45 = std::_Get_size_of_n<2>(v28 + 1);
      _mm_lfence();
      v46 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(v45);
      *((_QWORD *)a4 + 2) = v30;
      *((_QWORD *)a4 + 3) = v28;
      v47 = 2 * v30;
      memmove(v46, v29, v47);
      *(_WORD *)&v46[v47] = 0;
      if ( v31 > 7 )
      {
        _mm_lfence();
        std::_Deallocate<16>(*(_QWORD *)a4, 2 * v31 + 2);
      }
      *(_QWORD *)a4 = v46;
    }
    else
    {
      v32 = a4;
      if ( v31 > 7 )
        v32 = *(char **)a4;
      *((_QWORD *)a4 + 2) = v30;
      v33 = 2 * v30;
      memmove(v32, v29, v33);
      *(_WORD *)&v32[v33] = 0;
    }
  }
  *a8 = 0;
  v34 = *(_QWORD *)(v18 + 208);
  if ( v34 <= 0x48 )
  {
    v35 = (_QWORD *)(v18 + 192);
    if ( *(_QWORD *)(v18 + 216) > 7u )
      v35 = (_QWORD *)*v35;
    memmove(a8, v35, 2 * v34);
  }
  a8[73] = 0;
  v36 = *(_QWORD *)(v18 + 240);
  if ( v36 <= 0x80 )
  {
    v37 = (_QWORD *)(v18 + 224);
    if ( *(_QWORD *)(v18 + 248) > 7u )
      v37 = (_QWORD *)*v37;
    memmove(a8 + 73, v37, 2 * v36);
  }
  a8[202] = 0;
  v38 = *(_QWORD *)(v18 + 272);
  if ( v38 <= 0x100 )
  {
    v39 = (_QWORD *)(v18 + 256);
    if ( *(_QWORD *)(v18 + 280) > 7u )
      v39 = (_QWORD *)*v39;
    memmove(a8 + 202, v39, 2 * v38);
  }
  *a9 = *(_DWORD *)(v18 + 292);
  ReleaseSRWLockExclusive(SRWLock);
  return 0;
}

```

## disassembly

```asm
0x18002c504  push    rbx
0x18002c506  push    rsi
0x18002c507  push    rdi
0x18002c508  push    r12
0x18002c50a  push    r13
0x18002c50c  push    r14
0x18002c50e  push    r15
0x18002c510  sub     rsp, 80h
0x18002c517  mov     [rsp+0B8h+var_80], r9
0x18002c51c  mov     r15, r8
0x18002c51f  mov     rsi, rdx
0x18002c522  mov     rdi, rcx
0x18002c525  mov     rbx, [rsp+0B8h+arg_20]
0x18002c52d  mov     [rsp+0B8h+var_78], rbx
0x18002c532  mov     rax, [rsp+0B8h+arg_28]
0x18002c53a  mov     [rsp+0B8h+var_70], rax
0x18002c53f  mov     r12, [rsp+0B8h+arg_30]
0x18002c547  mov     rax, [rsp+0B8h+arg_38]
0x18002c54f  mov     [rsp+0B8h+var_58], rax
0x18002c554  mov     rax, [rsp+0B8h+arg_40]
0x18002c55c  mov     [rsp+0B8h+var_50], rax
0x18002c561  mov     r13, [rsp+0B8h+arg_48]
0x18002c569  xor     r14d, r14d
0x18002c56c  mov     [rsp+0B8h+var_88], r14d
0x18002c571  lea     rax, [rcx+1D0h]
0x18002c578  mov     [rsp+0B8h+SRWLock], rax
0x18002c57d  mov     rcx, rax; SRWLock
0x18002c580  call    cs:__imp_AcquireSRWLockExclusive
0x18002c586  mov     [rsp+0B8h+var_60], 1
0x18002c58b  mov     rdx, rsi; struct PPID *
0x18002c58e  mov     rcx, rdi; this
0x18002c591  call    ?GetProcessFromCacheUnsafe@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@AEAAAEAUProcessEnforcementDescriptor@123@AEBUPPID@@@Z; RealtimeProtection::DlpProcessCache::DlpProcessStateCache::GetProcessFromCacheUnsafe(PPID const &)
0x18002c596  mov     rdi, rax
0x18002c599  mov     al, [rax+8Ch]
0x18002c59f  mov     [r13+0], al
0x18002c5a3  mov     rdx, r15
0x18002c5a6  call    ??$?RV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UCaseInsensitiveHasher@DlpUtils@RealtimeProtection@@UCStrOrdinalCompEqual@45@@std@@QEBA_KAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Uhash_compare<std::wstring,RealtimeProtection::DlpUtils::CaseInsensitiveHasher,RealtimeProtection::DlpUtils::CStrOrdinalCompEqual>::operator()<std::wstring>(std::wstring const &)
0x18002c5ab  mov     rcx, rax
0x18002c5ae  mov     rax, [rdi+100h]
0x18002c5b5  and     rax, rcx
0x18002c5b8  add     rax, rax
0x18002c5bb  mov     rcx, [rdi+0E8h]
0x18002c5c2  mov     rsi, [rcx+rax*8+8]
0x18002c5c7  cmp     rsi, [rdi+0D8h]
0x18002c5ce  jz      short loc_18002C613
0x18002c5d0  mov     r13, [rcx+rax*8]
0x18002c5d4  lea     r8, [rsi+10h]
0x18002c5d8  cmp     qword ptr [rsi+28h], 7
0x18002c5dd  jbe     short loc_18002C5E2
0x18002c5df  mov     r8, [r8]; lpString2
0x18002c5e2  mov     rcx, r15; lpString1
0x18002c5e5  cmp     qword ptr [r15+18h], 7
0x18002c5ea  ja      loc_18002C7D8
0x18002c5f0  mov     [rsp+0B8h+bIgnoreCase], 1; bIgnoreCase
0x18002c5f8  or      r9d, 0FFFFFFFFh; cchCount2
0x18002c5fc  or      edx, r9d; cchCount1
0x18002c5ff  call    cs:__imp_CompareStringOrdinal
0x18002c605  cmp     eax, 2
0x18002c608  jz      short loc_18002C616
0x18002c60a  cmp     rsi, r13
0x18002c60d  jnz     loc_18002C904
0x18002c613  mov     rsi, r14
0x18002c616  test    rsi, rsi
0x18002c619  jz      loc_18002C92D
0x18002c61f  cmp     rsi, [rdi+0D8h]
0x18002c626  jz      loc_18002C92D
0x18002c62c  mov     rax, [rsp+0B8h+var_70]
0x18002c631  cmp     dword ptr [rax], 0Ah
0x18002c634  jnz     loc_18002C96F
0x18002c63a  mov     dword ptr [rax], 0Ah
0x18002c640  mov     ecx, r14d
0x18002c643  lea     rdx, [rsi+98h]
0x18002c64a  mov     [r12], ecx
0x18002c64e  mov     eax, [rdx]
0x18002c650  mov     [r12+4], eax
0x18002c655  inc     ecx
0x18002c657  lea     rdx, [rdx+4]
0x18002c65b  lea     r12, [r12+8]
0x18002c660  cmp     ecx, 0Ah
0x18002c663  jb      short loc_18002C64A
0x18002c665  lea     r15, [rsi+58h]
0x18002c669  cmp     rbx, r15
0x18002c66c  jz      short loc_18002C6B4
0x18002c66e  mov     r13, [r15+10h]
0x18002c672  cmp     qword ptr [r15+18h], 7
0x18002c677  jbe     short loc_18002C67C
0x18002c679  mov     r15, [r15]
0x18002c67c  mov     r12, [rbx+18h]
0x18002c680  cmp     r13, r12
0x18002c683  ja      loc_18002C7E0
0x18002c689  mov     rdi, rbx
0x18002c68c  cmp     r12, 7
0x18002c690  jbe     short loc_18002C695
0x18002c692  mov     rdi, [rbx]
0x18002c695  mov     [rbx+10h], r13
0x18002c699  lea     rbx, ds:0[r13*2]
0x18002c6a1  mov     r8, rbx; Size
0x18002c6a4  mov     rdx, r15; Src
0x18002c6a7  mov     rcx, rdi; void *
0x18002c6aa  call    memmove
0x18002c6af  mov     [rdi+rbx], r14w
0x18002c6b4  mov     rdi, 7FFFFFFFFFFFFFFEh
0x18002c6be  lea     r15, [rsi+78h]
0x18002c6c2  mov     rax, [rsp+0B8h+var_80]
0x18002c6c7  cmp     rax, r15
0x18002c6ca  jz      short loc_18002C70D
0x18002c6cc  mov     rbx, [r15+10h]
0x18002c6d0  cmp     qword ptr [r15+18h], 7
0x18002c6d5  jbe     short loc_18002C6DA
0x18002c6d7  mov     r15, [r15]
0x18002c6da  mov     r12, [rax+18h]
0x18002c6de  cmp     rbx, r12
0x18002c6e1  ja      loc_18002C883
0x18002c6e7  mov     rdi, rax
0x18002c6ea  cmp     r12, 7
0x18002c6ee  jbe     short loc_18002C6F3
0x18002c6f0  mov     rdi, [rax]
0x18002c6f3  mov     [rax+10h], rbx
0x18002c6f7  add     rbx, rbx
0x18002c6fa  mov     r8, rbx; Size
0x18002c6fd  mov     rdx, r15; Src
0x18002c700  mov     rcx, rdi; void *
0x18002c703  call    memmove
0x18002c708  mov     [rdi+rbx], r14w
0x18002c70d  mov     rbx, [rsp+0B8h+var_58]
0x18002c712  mov     [rbx], r14w
0x18002c716  mov     r8, [rsi+0D0h]
0x18002c71d  cmp     r8, 48h ; 'H'
0x18002c721  ja      short loc_18002C73F
0x18002c723  lea     rdx, [rsi+0C0h]
0x18002c72a  cmp     qword ptr [rdx+18h], 7
0x18002c72f  jbe     short loc_18002C734
0x18002c731  mov     rdx, [rdx]; Src
0x18002c734  add     r8, r8; Size
0x18002c737  mov     rcx, rbx; void *
0x18002c73a  call    memmove
0x18002c73f  lea     rcx, [rbx+92h]; void *
0x18002c746  mov     [rcx], r14w
0x18002c74a  mov     r8, [rsi+0F0h]
0x18002c751  cmp     r8, 80h
0x18002c758  ja      short loc_18002C773
0x18002c75a  lea     rdx, [rsi+0E0h]
0x18002c761  cmp     qword ptr [rdx+18h], 7
0x18002c766  jbe     short loc_18002C76B
0x18002c768  mov     rdx, [rdx]; Src
0x18002c76b  add     r8, r8; Size
0x18002c76e  call    memmove
0x18002c773  lea     rcx, [rbx+194h]; void *
0x18002c77a  mov     [rcx], r14w
0x18002c77e  mov     r8, [rsi+110h]
0x18002c785  cmp     r8, 100h
0x18002c78c  ja      short loc_18002C7A7
0x18002c78e  lea     rdx, [rsi+100h]
0x18002c795  cmp     qword ptr [rdx+18h], 7
0x18002c79a  jbe     short loc_18002C79F
0x18002c79c  mov     rdx, [rdx]; Src
0x18002c79f  add     r8, r8; Size
0x18002c7a2  call    memmove
0x18002c7a7  mov     eax, [rsi+124h]
0x18002c7ad  mov     rcx, [rsp+0B8h+var_50]
0x18002c7b2  mov     [rcx], eax
0x18002c7b4  mov     ebx, [rsp+0B8h+var_88]
0x18002c7b8  mov     rcx, [rsp+0B8h+SRWLock]; SRWLock
0x18002c7bd  call    cs:__imp_ReleaseSRWLockExclusive
0x18002c7c3  mov     eax, ebx
0x18002c7c5  add     rsp, 80h
0x18002c7cc  pop     r15
0x18002c7ce  pop     r14
0x18002c7d0  pop     r13
0x18002c7d2  pop     r12
0x18002c7d4  pop     rdi
0x18002c7d5  pop     rsi
0x18002c7d6  pop     rbx
0x18002c7d7  retn
0x18002c7d8  mov     rcx, [r15]
0x18002c7db  jmp     loc_18002C5F0
0x18002c7e0  mov     rdi, 7FFFFFFFFFFFFFFEh
0x18002c7ea  cmp     r13, rdi
0x18002c7ed  ja      loc_18002C90D
0x18002c7f3  lfence
0x18002c7f6  mov     rcx, r13
0x18002c7f9  or      rcx, 7
0x18002c7fd  cmp     rcx, rdi
0x18002c800  ja      loc_18002C925
0x18002c806  mov     rdx, r12
0x18002c809  shr     rdx, 1
0x18002c80c  mov     rax, rdi
0x18002c80f  sub     rax, rdx
0x18002c812  cmp     r12, rax
0x18002c815  ja      loc_18002C925
0x18002c81b  lea     rbx, [r12+rdx]
0x18002c81f  cmp     rcx, rbx
0x18002c822  cmovnb  rbx, rcx
0x18002c826  lea     rcx, [rbx+1]
0x18002c82a  call    ??$_Get_size_of_n@$01@std@@YA_K_K@Z; std::_Get_size_of_n<2>(unsigned __int64)
0x18002c82f  lfence
0x18002c832  mov     rcx, rax
0x18002c835  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18002c83a  mov     [rsp+0B8h+var_70], rax
0x18002c83f  mov     rax, [rsp+0B8h+var_78]
0x18002c844  mov     [rax+10h], r13
0x18002c848  mov     [rax+18h], rbx
0x18002c84c  lea     rbx, ds:0[r13*2]
0x18002c854  mov     r8, rbx; Size
0x18002c857  mov     rdx, r15; Src
0x18002c85a  mov     r15, [rsp+0B8h+var_70]
0x18002c85f  mov     rcx, r15; void *
0x18002c862  call    memmove
0x18002c867  mov     [rbx+r15], r14w
0x18002c86c  mov     rbx, [rsp+0B8h+var_78]
0x18002c871  cmp     r12, 7
0x18002c875  ja      loc_18002C942
0x18002c87b  mov     [rbx], r15
0x18002c87e  jmp     loc_18002C6BE
0x18002c883  cmp     rbx, rdi
0x18002c886  ja      loc_18002C919
0x18002c88c  lfence
0x18002c88f  mov     rcx, rbx
0x18002c892  or      rcx, 7
0x18002c896  cmp     rcx, rdi
0x18002c899  ja      short loc_18002C8B7
0x18002c89b  mov     rdx, r12
0x18002c89e  shr     rdx, 1
0x18002c8a1  mov     rax, rdi
0x18002c8a4  sub     rax, rdx
0x18002c8a7  cmp     r12, rax
0x18002c8aa  ja      short loc_18002C8B7
0x18002c8ac  lea     rdi, [rdx+r12]
0x18002c8b0  cmp     rcx, rdi
0x18002c8b3  cmovnb  rdi, rcx
0x18002c8b7  lea     rcx, [rdi+1]
0x18002c8bb  call    ??$_Get_size_of_n@$01@std@@YA_K_K@Z; std::_Get_size_of_n<2>(unsigned __int64)
0x18002c8c0  lfence
0x18002c8c3  mov     rcx, rax
0x18002c8c6  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18002c8cb  mov     r13, rax
0x18002c8ce  mov     rax, [rsp+0B8h+var_80]
0x18002c8d3  mov     [rax+10h], rbx
0x18002c8d7  mov     [rax+18h], rdi
0x18002c8db  add     rbx, rbx
0x18002c8de  mov     r8, rbx; Size
0x18002c8e1  mov     rdx, r15; Src
0x18002c8e4  mov     rcx, r13; void *
0x18002c8e7  call    memmove
0x18002c8ec  mov     [rbx+r13], r14w
0x18002c8f1  mov     rbx, [rsp+0B8h+var_80]
0x18002c8f6  cmp     r12, 7
0x18002c8fa  ja      short loc_18002C95A
0x18002c8fc  mov     [rbx], r13
0x18002c8ff  jmp     loc_18002C70D
0x18002c904  mov     rsi, [rsi+8]
0x18002c908  jmp     loc_18002C5D4
0x18002c90d  lea     rcx, aStringTooLong; "string too long"
0x18002c914  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18002c919  lea     rcx, aStringTooLong; "string too long"
0x18002c920  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18002c925  mov     rbx, rdi
0x18002c928  jmp     loc_18002C826
0x18002c92d  mov     rcx, [rsp+0B8h+SRWLock]; SRWLock
0x18002c932  call    cs:__imp_ReleaseSRWLockExclusive
0x18002c938  mov     eax, 80070490h
0x18002c93d  jmp     loc_18002C7C5
0x18002c942  lfence
0x18002c945  lea     rdx, ds:2[r12*2]
0x18002c94d  mov     rcx, [rbx]
0x18002c950  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002c955  jmp     loc_18002C87B
0x18002c95a  lfence
0x18002c95d  lea     rdx, ds:2[r12*2]
0x18002c965  mov     rcx, [rbx]
0x18002c968  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002c96d  jmp     short loc_18002C8FC
0x18002c96f  mov     rcx, [rsp+0B8h+SRWLock]; SRWLock
0x18002c974  call    cs:__imp_ReleaseSRWLockExclusive
0x18002c97a  mov     eax, 80004005h
0x18002c97f  jmp     loc_18002C7C5
0x18002c984  jmp     loc_18002C7B4
0x18002c989  jmp     loc_18002C7B4
```
