# RealtimeProtection::DlpProcessCache::DlpProcessStateCache::DereferenceFile(PPID const &,wchar_t const *,bool)

- ea: `0x18004f430`
- end: `0x18004fa25`
- name: `?DereferenceFile@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@QEAAJAEBUPPID@@PEB_W_N@Z`
- size: `1525`
- prototype: `__int64 __fastcall(RealtimeProtection::DlpProcessCache::DlpProcessStateCache *__hidden this, const struct PPID *, const wchar_t *, bool)`
- caller_count: `2`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x18004f370`
- `0x18004fa30`

## callees

- `0x18001bad0`
- `0x180020180`
- `0x18002bda4`
- `0x18004e2d0`
- `0x18004f430`
- `0x18006ad2c`
- `0x18006b2fc`
- `0x18006b350`
- `0x18006b4c8`
- `0x18006b500`
- `0x18006bb8c`
- `0x18006c3c0`
- `0x18006c458`
- `0x1800809d0`
- `0x180096a40`
- `0x180107874`
- `0x180109324`
- `0x18010cb40`
- `0x18010ce44`
- `0x18023a310`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x18004f46f`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18004f46f`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18004f519`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18004f757`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18004f8ff`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18004f9da`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18004f519`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18004f757`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18004f8ff`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18004f9da`
- `KERNEL32!CompareFileTime` at `0x18004f4d8`
- `KERNEL32!CompareFileTime` at `0x18004f662`
- `KERNEL32!CompareFileTime` at `0x18004f4d8`
- `KERNEL32!CompareFileTime` at `0x18004f662`

## string_xrefs

- `0x18004f785`: `RealtimeProtection::DlpProcessCache::DlpProcessStateCache::DereferenceFile`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall RealtimeProtection::DlpProcessCache::DlpProcessStateCache::DereferenceFile(
        RTL_SRWLOCK *this,
        const FILETIME *a2,
        wchar_t *a3)
{
  wchar_t *v3; // r15
  RTL_SRWLOCK *v6; // r14
  __int64 v7; // r9
  _QWORD *Ptr; // rax
  __int64 v9; // rbx
  __int64 v10; // r15
  int v12; // eax
  unsigned int v13; // r12d
  _QWORD *v14; // rax
  __int64 v15; // r15
  __int64 v16; // rax
  _QWORD *v17; // rcx
  FILETIME *v18; // r15
  FILETIME *v19; // rbx
  __int64 v20; // rdx
  float v21; // xmm0_4
  __int64 v22; // rcx
  float v23; // xmm1_4
  const FILETIME *v24; // rcx
  __int64 v25; // rbx
  FILETIME **v26; // r8
  __int64 v27; // rax
  _QWORD *v28; // rdx
  void *v29; // r9
  __int64 v30; // rdx
  __int64 v31; // rcx
  __int64 v32; // rax
  __int64 v33; // r9
  int v34; // eax
  __int64 v35; // rax
  __int64 v36; // rdx
  const FILETIME *v37; // [rsp+30h] [rbp-88h] BYREF
  wchar_t *v38; // [rsp+38h] [rbp-80h]
  RTL_SRWLOCK *v39; // [rsp+40h] [rbp-78h] BYREF
  FILETIME *v40; // [rsp+48h] [rbp-70h]
  RTL_SRWLOCK *v41; // [rsp+50h] [rbp-68h] BYREF
  char v42; // [rsp+58h] [rbp-60h]
  unsigned int v43; // [rsp+68h] [rbp-50h] BYREF
  int v44; // [rsp+6Ch] [rbp-4Ch] BYREF

  v3 = a3;
  v38 = a3;
  v6 = this + 58;
  v41 = this + 58;
  AcquireSRWLockExclusive(this + 58);
  v42 = 1;
  v43 = 0;
  MpHashCrc32(&v43, 12);
  Ptr = this[28].Ptr;
  v9 = Ptr[2 * (v43 & (__int64)this[31].Ptr) + 1];
  if ( (PVOID)v9 != this[26].Ptr )
  {
    v10 = Ptr[2 * (v43 & (__int64)this[31].Ptr)];
    while ( 1 )
    {
      if ( a2[1].dwLowDateTime == *(_DWORD *)(v9 + 24) && !CompareFileTime(a2, (const FILETIME *)(v9 + 16)) )
      {
        v3 = v38;
        goto LABEL_10;
      }
      if ( v9 == v10 )
        break;
      v9 = *(_QWORD *)(v9 + 8);
    }
    v3 = v38;
  }
  v9 = 0;
LABEL_10:
  if ( !v9 || (PVOID)v9 == this[26].Ptr )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        83,
        (unsigned int)&WPP_37379ce3a908304aafca380d907f5915_Traceguids,
        (unsigned int)"RealtimeProtection::DlpProcessCache::DlpProcessStateCache::DereferenceFile",
        a2[1].dwLowDateTime);
    ReleaseSRWLockExclusive(v6);
    return 1;
  }
  v44 = 0;
  v12 = RealtimeProtection::DlpProcessCache::DlpProcessStateCache::DereferenceFileInternal(
          (RealtimeProtection::DlpProcessCache::DlpProcessStateCache *)this,
          a2,
          v3,
          v7,
          (enum _MP_KNOWN_PROCESS_TYPE *)&v44);
  v13 = v12;
  if ( v12 >= 0 )
  {
    _mm_lfence();
    v14 = this[36].Ptr;
    v15 = v14[2
            * ((unsigned __int64)this[39].Ptr
             & (0x100000001B3LL
              * (HIBYTE(a2[1].dwLowDateTime)
               ^ (0x100000001B3LL
                * (BYTE2(a2[1].dwLowDateTime)
                 ^ (0x100000001B3LL
                  * (BYTE1(a2[1].dwLowDateTime)
                   ^ (0x100000001B3LL * (LOBYTE(a2[1].dwLowDateTime) ^ 0xCBF29CE484222325uLL)))))))))
            + 1];
    if ( (PVOID)v15 == this[34].Ptr )
    {
LABEL_16:
      v15 = 0;
    }
    else
    {
      while ( a2[1].dwLowDateTime != *(_DWORD *)(v15 + 16) )
      {
        if ( v15 == v14[2
                      * ((unsigned __int64)this[39].Ptr
                       & (0x100000001B3LL
                        * (HIBYTE(a2[1].dwLowDateTime)
                         ^ (0x100000001B3LL
                          * (BYTE2(a2[1].dwLowDateTime)
                           ^ (0x100000001B3LL
                            * (BYTE1(a2[1].dwLowDateTime)
                             ^ (0x100000001B3LL * (LOBYTE(a2[1].dwLowDateTime) ^ 0xCBF29CE484222325uLL)))))))))] )
          goto LABEL_16;
        v15 = *(_QWORD *)(v15 + 8);
      }
    }
    if ( v15
      && (PVOID)v15 != this[34].Ptr
      && (*(_DWORD *)(v15 + 32) != a2->dwHighDateTime || *(_DWORD *)(v15 + 28) != a2->dwLowDateTime) )
    {
      v37 = (const FILETIME *)std::_Uhash_compare<EndpointDlp::PPID,EndpointDlp::PPIDHasher,EndpointDlp::PPIDComparer>::operator()<EndpointDlp::PPID>(
                                2
                              * ((unsigned __int64)this[39].Ptr
                               & (0x100000001B3LL
                                * (HIBYTE(a2[1].dwLowDateTime)
                                 ^ (0x100000001B3LL
                                  * (BYTE2(a2[1].dwLowDateTime)
                                   ^ (0x100000001B3LL
                                    * (BYTE1(a2[1].dwLowDateTime)
                                     ^ (0x100000001B3LL * (LOBYTE(a2[1].dwLowDateTime) ^ 0xCBF29CE484222325uLL))))))))),
                                v15 + 28);
      v30 = *(_QWORD *)(std::_Hash<std::_Umap_traits<PPID,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor,std::_Uhash_compare<PPID,RealtimeProtection::DlpUtils::PPIDHasher,RealtimeProtection::DlpUtils::PPIDComparer>,std::allocator<std::pair<PPID const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor>>,0>>::_Find_last<PPID>(
                          &this[25],
                          &v39,
                          v15 + 28,
                          v37)
                      + 8);
      if ( v30 )
      {
        std::_Hash<std::_Umap_traits<unsigned long,std::pair<Dlp::DlpSaveAsCache::SaveAsCandidate,std::_List_iterator<std::_List_val<std::_List_simple_types<unsigned long>>>>,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,std::pair<Dlp::DlpSaveAsCache::SaveAsCandidate,std::_List_iterator<std::_List_val<std::_List_simple_types<unsigned long>>>>>>,0>>::_Erase_bucket(
          &this[25],
          v30,
          (unsigned __int64)v37 & (unsigned __int64)this[31].Ptr);
        std::list<std::pair<PPID const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor>>::_Unchecked_erase(&this[26]);
      }
      v32 = std::_Uhash_compare<enum DlpActionType,std::hash<enum DlpActionType>,std::equal_to<enum DlpActionType>>::operator()<enum DlpActionType>(
              v31,
              v15 + 16);
      std::_Hash<std::_Umap_traits<unsigned long,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::TerminatedProcessDescriptor,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::TerminatedProcessDescriptor>>,0>>::_Erase_bucket(
        &this[33],
        v15,
        v32 & (__int64)this[39].Ptr);
      std::list<std::pair<unsigned long const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::TerminatedProcessDescriptor>>::_Unchecked_erase(&this[34]);
    }
    v43 = 0;
    MpHashCrc32(&v43, 12);
    v16 = 2 * (v43 & (__int64)this[31].Ptr);
    v17 = this[28].Ptr;
    v18 = (FILETIME *)v17[2 * (v43 & (__int64)this[31].Ptr) + 1];
    v37 = (const FILETIME *)this[26].Ptr;
    if ( v18 != v37 )
    {
      v19 = (FILETIME *)v17[v16];
      while ( a2[1].dwLowDateTime != v18[3].dwLowDateTime || CompareFileTime(a2, v18 + 2) )
      {
        if ( v18 == v19 )
        {
          v37 = v18;
          goto LABEL_43;
        }
        v18 = (FILETIME *)v18[1];
      }
      goto LABEL_37;
    }
LABEL_43:
    if ( this[27].Ptr == (PVOID)0x41041041041041LL )
      std::_Xlength_error("unordered_map/set too long");
    v39 = this + 26;
    v40 = 0;
    v18 = (FILETIME *)operator new(0x3F0u);
    v40 = v18;
    v18[2] = *a2;
    v18[3].dwLowDateTime = a2[1].dwLowDateTime;
    memset(&v18[4], 0, 0x3D0u);
    RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor::ProcessEnforcementDescriptor((RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor *)&v18[4]);
    v20 = (__int64)this[27].Ptr + 1;
    if ( v20 < 0 )
      v21 = (float)(v20 & 1 | (unsigned int)((unsigned __int64)v20 >> 1))
          + (float)(v20 & 1 | (unsigned int)((unsigned __int64)v20 >> 1));
    else
      v21 = (float)(int)v20;
    v22 = (__int64)this[32].Ptr;
    if ( v22 < 0 )
    {
      v35 = (__int64)this[32].Ptr & 1 | ((unsigned __int64)v22 >> 1);
      v23 = (float)(int)v35 + (float)(int)v35;
    }
    else
    {
      v23 = (float)(int)v22;
    }
    if ( (float)(v21 / v23) > *(float *)&this[25].Ptr )
    {
      v36 = std::_Hash<std::_Umap_traits<RealtimeProtection::FileUniqueId,RealtimeProtection::_DlpQuarantineItem,std::_Uhash_compare<RealtimeProtection::FileUniqueId,RealtimeProtection::FileUniqueIdHasher,RealtimeProtection::FileUniqueIdComparer>,std::allocator<std::pair<RealtimeProtection::FileUniqueId const,RealtimeProtection::_DlpQuarantineItem>>,0>>::_Desired_grow_bucket_count(&this[25]);
      std::_Hash<std::_Umap_traits<PPID,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::PauseResumeProcessInfo,std::_Uhash_compare<PPID,RealtimeProtection::DlpUtils::PPIDHasher,RealtimeProtection::DlpUtils::PPIDComparer>,std::allocator<std::pair<PPID const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::PauseResumeProcessInfo>>,0>>::_Forced_rehash(
        &this[25],
        v36);
      v25 = v43;
      v24 = *(const FILETIME **)std::_Hash<std::_Umap_traits<PPID,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor,std::_Uhash_compare<PPID,RealtimeProtection::DlpUtils::PPIDHasher,RealtimeProtection::DlpUtils::PPIDComparer>,std::allocator<std::pair<PPID const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor>>,0>>::_Find_last<PPID>(
                                  &this[25],
                                  &v41,
                                  &v18[2],
                                  v43);
    }
    else
    {
      v24 = v37;
      v25 = v43;
    }
    v26 = (FILETIME **)v24[1];
    ++this[27].Ptr;
    *v18 = (FILETIME)v24;
    v18[1] = (FILETIME)v26;
    *v26 = v18;
    v24[1] = (const FILETIME)v18;
    v27 = 2 * (v25 & (__int64)this[31].Ptr);
    v28 = this[28].Ptr;
    v29 = (void *)v28[2 * (v25 & (__int64)this[31].Ptr)];
    if ( v29 == this[26].Ptr )
    {
      v28[2 * (v25 & (__int64)this[31].Ptr)] = v18;
    }
    else
    {
      if ( v29 == v24 )
      {
        v28[2 * (v25 & (__int64)this[31].Ptr)] = v18;
        goto LABEL_37;
      }
      if ( (FILETIME **)v28[2 * (v25 & (__int64)this[31].Ptr) + 1] != v26 )
        goto LABEL_37;
    }
    v28[v27 + 1] = v18;
LABEL_37:
    if ( v18[55].dwLowDateTime != 1
      || (v37 = 0,
          std::_Hash<std::_Umap_traits<PPID,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor,std::_Uhash_compare<PPID,RealtimeProtection::DlpUtils::PPIDHasher,RealtimeProtection::DlpUtils::PPIDComparer>,std::allocator<std::pair<PPID const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor>>,0>>::find(
            &this[25],
            &v37,
            &v18[56]),
          v37 == this[26].Ptr)
      || (v34 = RealtimeProtection::DlpProcessCache::DlpProcessStateCache::DereferenceFileInternal(
                  (RealtimeProtection::DlpProcessCache::DlpProcessStateCache *)this,
                  v37 + 2,
                  v38,
                  v33,
                  (enum _MP_KNOWN_PROCESS_TYPE *)&v44),
          v13 = v34,
          v34 >= 0) )
    {
      ReleaseSRWLockExclusive(v6);
      if ( (v13 & 0x80000000) != 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, &WPP_37379ce3a908304aafca380d907f5915_Traceguids, v13);
      }
      return v13;
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          85,
          &WPP_37379ce3a908304aafca380d907f5915_Traceguids,
          (unsigned int)v34);
      ReleaseSRWLockExclusive(v6);
      return v13;
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      84,
      &WPP_37379ce3a908304aafca380d907f5915_Traceguids,
      (unsigned int)v12);
  ReleaseSRWLockExclusive(v6);
  return v13;
}

```

## disassembly

```asm
0x18004f430  push    rbx
0x18004f432  push    rsi
0x18004f433  push    rdi
0x18004f434  push    r12
0x18004f436  push    r13
0x18004f438  push    r14
0x18004f43a  push    r15
0x18004f43c  sub     rsp, 80h
0x18004f443  mov     rax, cs:__security_cookie
0x18004f44a  xor     rax, rsp
0x18004f44d  mov     [rsp+0B8h+var_48], rax
0x18004f452  mov     r15, r8
0x18004f455  mov     [rsp+0B8h+var_80], r8
0x18004f45a  mov     rdi, rdx
0x18004f45d  mov     rsi, rcx
0x18004f460  lea     r14, [rcx+1D0h]
0x18004f467  mov     [rsp+0B8h+var_68], r14
0x18004f46c  mov     rcx, r14; SRWLock
0x18004f46f  call    cs:__imp_AcquireSRWLockExclusive
0x18004f475  mov     [rsp+0B8h+var_60], 1
0x18004f47a  xor     r13d, r13d
0x18004f47d  mov     [rsp+0B8h+var_50], r13d
0x18004f482  mov     r8, rdi
0x18004f485  mov     edx, 0Ch
0x18004f48a  lea     rcx, [rsp+0B8h+var_50]
0x18004f48f  call    MpHashCrc32
0x18004f494  mov     eax, [rsp+0B8h+var_50]
0x18004f498  mov     rcx, [rsi+0F8h]
0x18004f49f  and     rcx, rax
0x18004f4a2  add     rcx, rcx
0x18004f4a5  mov     rax, [rsi+0E0h]
0x18004f4ac  mov     rbx, [rax+rcx*8+8]
0x18004f4b1  cmp     rbx, [rsi+0D0h]
0x18004f4b8  jz      short loc_18004F4EE
0x18004f4ba  mov     r15, [rax+rcx*8]
0x18004f4be  lea     rdx, [rbx+10h]; lpFileTime2
0x18004f4c2  mov     eax, [rdx+8]
0x18004f4c5  cmp     [rdi+8], eax
0x18004f4c8  jz      short loc_18004F4D5
0x18004f4ca  cmp     rbx, r15
0x18004f4cd  jz      short loc_18004F4E9
0x18004f4cf  mov     rbx, [rbx+8]
0x18004f4d3  jmp     short loc_18004F4BE
0x18004f4d5  mov     rcx, rdi; lpFileTime1
0x18004f4d8  call    cs:__imp_CompareFileTime
0x18004f4de  test    eax, eax
0x18004f4e0  jnz     short loc_18004F4CA
0x18004f4e2  mov     r15, [rsp+0B8h+var_80]
0x18004f4e7  jmp     short loc_18004F4F1
0x18004f4e9  mov     r15, [rsp+0B8h+var_80]
0x18004f4ee  mov     rbx, r13
0x18004f4f1  test    rbx, rbx
0x18004f4f4  jz      short loc_18004F4FF
0x18004f4f6  cmp     rbx, [rsi+0D0h]
0x18004f4fd  jnz     short loc_18004F544
0x18004f4ff  lea     rdx, WPP_GLOBAL_Control
0x18004f506  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f50d  cmp     rcx, rdx
0x18004f510  jnz     loc_18004F76F
0x18004f516  mov     rcx, r14; SRWLock
0x18004f519  call    cs:__imp_ReleaseSRWLockExclusive
0x18004f51f  mov     eax, 1
0x18004f524  mov     rcx, [rsp+0B8h+var_48]
0x18004f529  xor     rcx, rsp; StackCookie
0x18004f52c  call    __security_check_cookie
0x18004f531  add     rsp, 80h
0x18004f538  pop     r15
0x18004f53a  pop     r14
0x18004f53c  pop     r13
0x18004f53e  pop     r12
0x18004f540  pop     rdi
0x18004f541  pop     rsi
0x18004f542  pop     rbx
0x18004f543  retn
0x18004f544  mov     [rsp+0B8h+var_4C], r13d
0x18004f549  lea     rax, [rsp+0B8h+var_4C]
0x18004f54e  mov     [rsp+0B8h+var_98], rax; enum _MP_KNOWN_PROCESS_TYPE *
0x18004f553  mov     r8, r15; wchar_t *
0x18004f556  mov     rdx, rdi; struct PPID *
0x18004f559  mov     rcx, rsi; this
0x18004f55c  call    ?DereferenceFileInternal@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@AEAAJAEBUPPID@@PEB_W_NAEAW4_MP_KNOWN_PROCESS_TYPE@@@Z; RealtimeProtection::DlpProcessCache::DlpProcessStateCache::DereferenceFileInternal(PPID const &,wchar_t const *,bool,_MP_KNOWN_PROCESS_TYPE &)
0x18004f561  mov     r12d, eax
0x18004f564  test    eax, eax
0x18004f566  js      loc_18004F9A5
0x18004f56c  lfence
0x18004f56f  movzx   ecx, byte ptr [rdi+8]
0x18004f573  mov     rax, 0CBF29CE484222325h
0x18004f57d  xor     rcx, rax
0x18004f580  mov     rdx, 100000001B3h
0x18004f58a  imul    rcx, rdx
0x18004f58e  movzx   eax, byte ptr [rdi+9]
0x18004f592  xor     rcx, rax
0x18004f595  imul    rcx, rdx
0x18004f599  movzx   eax, byte ptr [rdi+0Ah]
0x18004f59d  xor     rcx, rax
0x18004f5a0  imul    rcx, rdx
0x18004f5a4  movzx   eax, byte ptr [rdi+0Bh]
0x18004f5a8  xor     rcx, rax
0x18004f5ab  imul    rcx, rdx
0x18004f5af  and     rcx, [rsi+138h]
0x18004f5b6  add     rcx, rcx
0x18004f5b9  mov     rax, [rsi+120h]
0x18004f5c0  mov     r15, [rax+rcx*8+8]
0x18004f5c5  cmp     r15, [rsi+110h]
0x18004f5cc  jnz     short loc_18004F643
0x18004f5ce  mov     r15, r13
0x18004f5d1  test    r15, r15
0x18004f5d4  jnz     loc_18004F7C9
0x18004f5da  lea     r13, [rsi+0C8h]
0x18004f5e1  mov     [rsp+0B8h+var_50], 0
0x18004f5e9  mov     r8, rdi
0x18004f5ec  mov     edx, 0Ch
0x18004f5f1  lea     rcx, [rsp+0B8h+var_50]
0x18004f5f6  call    MpHashCrc32
0x18004f5fb  mov     ecx, [rsp+0B8h+var_50]
0x18004f5ff  mov     rax, [r13+30h]
0x18004f603  and     rax, rcx
0x18004f606  add     rax, rax
0x18004f609  mov     rcx, [r13+18h]
0x18004f60d  mov     r15, [rcx+rax*8+8]
0x18004f612  mov     rdx, [r13+8]
0x18004f616  mov     [rsp+0B8h+var_88], rdx
0x18004f61b  cmp     r15, rdx
0x18004f61e  jz      loc_18004F7A6
0x18004f624  mov     rbx, [rcx+rax*8]
0x18004f628  lea     rdx, [r15+10h]; lpFileTime2
0x18004f62c  mov     eax, [rdx+8]
0x18004f62f  cmp     [rdi+8], eax
0x18004f632  jz      short loc_18004F65F
0x18004f634  cmp     r15, rbx
0x18004f637  jz      loc_18004F7A1
0x18004f63d  mov     r15, [r15+8]
0x18004f641  jmp     short loc_18004F628
0x18004f643  mov     rdx, [rax+rcx*8]
0x18004f647  mov     eax, [r15+10h]
0x18004f64b  cmp     [rdi+8], eax
0x18004f64e  jz      short loc_18004F5D1
0x18004f650  cmp     r15, rdx
0x18004f653  jz      loc_18004F5CE
0x18004f659  mov     r15, [r15+8]
0x18004f65d  jmp     short loc_18004F647
0x18004f65f  mov     rcx, rdi; lpFileTime1
0x18004f662  call    cs:__imp_CompareFileTime
0x18004f668  test    eax, eax
0x18004f66a  jz      loc_18004F746
0x18004f670  jmp     short loc_18004F634
0x18004f672  lea     rax, [r13+8]
0x18004f676  mov     [rsp+0B8h+var_78], rax
0x18004f67b  mov     [rsp+0B8h+var_70], 0
0x18004f684  mov     ecx, 3F0h; Size
0x18004f689  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004f68e  mov     r15, rax
0x18004f691  mov     [rsp+0B8h+var_70], rax
0x18004f696  movsd   xmm0, qword ptr [rdi]
0x18004f69a  movsd   qword ptr [rax+10h], xmm0
0x18004f69f  mov     ecx, [rdi+8]
0x18004f6a2  mov     [rax+18h], ecx
0x18004f6a5  lea     rbx, [rax+20h]
0x18004f6a9  xor     edx, edx; Val
0x18004f6ab  mov     r8d, 3D0h; Size
0x18004f6b1  mov     rcx, rbx; void *
0x18004f6b4  call    memset
0x18004f6b9  mov     rcx, rbx; this
0x18004f6bc  call    ??0ProcessEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@QEAA@XZ; RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor::ProcessEnforcementDescriptor(void)
0x18004f6c1  nop
0x18004f6c2  mov     rdx, [rsi+0D8h]
0x18004f6c9  add     rdx, 1
0x18004f6cd  xorps   xmm0, xmm0
0x18004f6d0  js      loc_18004F96E
0x18004f6d6  cvtsi2ss xmm0, rdx
0x18004f6db  mov     rcx, [r13+38h]
0x18004f6df  xorps   xmm1, xmm1
0x18004f6e2  test    rcx, rcx
0x18004f6e5  js      loc_18004F98B
0x18004f6eb  cvtsi2ss xmm1, rcx
0x18004f6f0  divss   xmm0, xmm1
0x18004f6f4  comiss  xmm0, dword ptr [r13+0]
0x18004f6f9  ja      loc_18004F9E8
0x18004f6ff  mov     rcx, [rsp+0B8h+var_88]
0x18004f704  mov     ebx, [rsp+0B8h+var_50]
0x18004f708  mov     r8, [rcx+8]
0x18004f70c  inc     qword ptr [rsi+0D8h]
0x18004f713  mov     [r15], rcx
0x18004f716  mov     [r15+8], r8
0x18004f71a  mov     [r8], r15
0x18004f71d  mov     [rcx+8], r15
0x18004f721  mov     rax, [r13+30h]
0x18004f725  and     rax, rbx
0x18004f728  add     rax, rax
0x18004f72b  mov     rdx, [r13+18h]
0x18004f72f  mov     r9, [rdx+rax*8]
0x18004f733  cmp     r9, [r13+8]
0x18004f737  jnz     loc_18004F950
0x18004f73d  mov     [rdx+rax*8], r15
0x18004f741  mov     [rdx+rax*8+8], r15
0x18004f746  cmp     dword ptr [r15+1B8h], 1
0x18004f74e  jz      loc_18004F871
0x18004f754  mov     rcx, r14; SRWLock
0x18004f757  call    cs:__imp_ReleaseSRWLockExclusive
0x18004f75d  nop
0x18004f75e  test    r12d, r12d
0x18004f761  js      loc_18004F912
0x18004f767  mov     eax, r12d
0x18004f76a  jmp     loc_18004F524
0x18004f76f  test    byte ptr [rcx+1Ch], 10h
0x18004f773  jz      loc_18004F516
0x18004f779  mov     edx, 53h ; 'S'
0x18004f77e  mov     eax, [rdi+8]
0x18004f781  mov     dword ptr [rsp+0B8h+var_98], eax
0x18004f785  lea     r9, aRealtimeprotec_4; "RealtimeProtection::DlpProcessCache::Dl"...
0x18004f78c  lea     r8, WPP_37379ce3a908304aafca380d907f5915_Traceguids
0x18004f793  mov     rcx, [rcx+10h]
0x18004f797  call    WPP_SF_sd
0x18004f79c  jmp     loc_18004F516
0x18004f7a1  mov     [rsp+0B8h+var_88], r15
0x18004f7a6  mov     rax, 41041041041041h
0x18004f7b0  cmp     [rsi+0D8h], rax
0x18004f7b7  jnz     loc_18004F672
0x18004f7bd  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x18004f7c4  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18004f7c9  cmp     r15, [rsi+110h]
0x18004f7d0  jz      loc_18004F5DA
0x18004f7d6  mov     eax, [rdi+4]
0x18004f7d9  cmp     [r15+20h], eax
0x18004f7dd  jnz     short loc_18004F7EB
0x18004f7df  mov     eax, [rdi]
0x18004f7e1  cmp     [r15+1Ch], eax
0x18004f7e5  jz      loc_18004F5DA
0x18004f7eb  lea     rdx, [r15+1Ch]
0x18004f7ef  call    ??$?RUPPID@EndpointDlp@@@?$_Uhash_compare@UPPID@EndpointDlp@@UPPIDHasher@2@UPPIDComparer@2@@std@@QEBA_KAEBUPPID@EndpointDlp@@@Z; std::_Uhash_compare<EndpointDlp::PPID,EndpointDlp::PPIDHasher,EndpointDlp::PPIDComparer>::operator()<EndpointDlp::PPID>(EndpointDlp::PPID const &)
0x18004f7f4  mov     [rsp+0B8h+var_88], rax
0x18004f7f9  mov     r9, rax
0x18004f7fc  lea     r8, [r15+1Ch]
0x18004f800  lea     rdx, [rsp+0B8h+var_78]
0x18004f805  lea     rcx, [rsi+0C8h]
0x18004f80c  call    ??$_Find_last@UPPID@@@?$_Hash@V?$_Umap_traits@UPPID@@UProcessEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@V?$_Uhash_compare@UPPID@@UPPIDHasher@DlpUtils@RealtimeProtection@@UPPIDComparer@34@@std@@V?$allocator@U?$pair@$$CBUPPID@@UProcessEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@@7@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBUPPID@@UProcessEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@PEAX@std@@@1@AEBUPPID@@_K@Z; std::_Hash<std::_Umap_traits<PPID,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor,std::_Uhash_compare<PPID,RealtimeProtection::DlpUtils::PPIDHasher,RealtimeProtection::DlpUtils::PPIDComparer>,std::allocator<std::pair<PPID const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor>>,0>>::_Find_last<PPID>(PPID const &,unsigned __int64)
0x18004f811  mov     rdx, [rax+8]
0x18004f815  test    rdx, rdx
0x18004f818  jz      short loc_18004F83E
0x18004f81a  mov     r8, [rsi+0F8h]
0x18004f821  and     r8, [rsp+0B8h+var_88]
0x18004f826  lea     rcx, [rsi+0C8h]
0x18004f82d  call    ?_Erase_bucket@?$_Hash@V?$_Umap_traits@KU?$pair@USaveAsCandidate@DlpSaveAsCache@Dlp@@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@K@std@@@std@@@std@@@std@@V?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@2@V?$allocator@U?$pair@$$CBKU?$pair@USaveAsCandidate@DlpSaveAsCache@Dlp@@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@K@std@@@std@@@std@@@std@@@std@@@2@$0A@@std@@@std@@IEAAXPEAU?$_List_node@U?$pair@$$CBKU?$pair@USaveAsCandidate@DlpSaveAsCache@Dlp@@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@K@std@@@std@@@std@@@std@@@std@@PEAX@2@_K@Z; std::_Hash<std::_Umap_traits<ulong,std::pair<Dlp::DlpSaveAsCache::SaveAsCandidate,std::_List_iterator<std::_List_val<std::_List_simple_types<ulong>>>>,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,std::pair<Dlp::DlpSaveAsCache::SaveAsCandidate,std::_List_iterator<std::_List_val<std::_List_simple_types<ulong>>>>>>,0>>::_Erase_bucket(std::_List_node<std::pair<ulong const,std::pair<Dlp::DlpSaveAsCache::SaveAsCandidate,std::_List_iterator<std::_List_val<std::_List_simple_types<ulong>>>>>,void *> *,unsigned __int64)
0x18004f832  lea     rcx, [rsi+0D0h]
0x18004f839  call    ?_Unchecked_erase@?$list@U?$pair@$$CBUPPID@@UProcessEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@V?$allocator@U?$pair@$$CBUPPID@@UProcessEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@@2@@std@@AEAAPEAU?$_List_node@U?$pair@$$CBUPPID@@UProcessEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@PEAX@2@QEAU32@@Z; std::list<std::pair<PPID const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor>>::_Unchecked_erase(std::_List_node<std::pair<PPID const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor>,void *> * const)
0x18004f83e  lea     rdx, [r15+10h]
0x18004f842  call    ??$?RW4DlpActionType@@@?$_Uhash_compare@W4DlpActionType@@U?$hash@W4DlpActionType@@@std@@U?$equal_to@W4DlpActionType@@@3@@std@@QEBA_KAEBW4DlpActionType@@@Z; std::_Uhash_compare<DlpActionType,std::hash<DlpActionType>,std::equal_to<DlpActionType>>::operator()<DlpActionType>(DlpActionType const &)
0x18004f847  mov     r8, [rsi+138h]
0x18004f84e  and     r8, rax
0x18004f851  mov     rdx, r15
0x18004f854  lea     rcx, [rsi+108h]
0x18004f85b  call    ?_Erase_bucket@?$_Hash@V?$_Umap_traits@KUTerminatedProcessDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@V?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@std@@V?$allocator@U?$pair@$$CBKUTerminatedProcessDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@@6@$0A@@std@@@std@@IEAAXPEAU?$_List_node@U?$pair@$$CBKUTerminatedProcessDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@PEAX@2@_K@Z; std::_Hash<std::_Umap_traits<ulong,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::TerminatedProcessDescriptor,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::TerminatedProcessDescriptor>>,0>>::_Erase_bucket(std::_List_node<std::pair<ulong const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::TerminatedProcessDescriptor>,void *> *,unsigned __int64)
0x18004f860  lea     rcx, [rsi+110h]
0x18004f867  call    ?_Unchecked_erase@?$list@U?$pair@$$CBKUTerminatedProcessDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@V?$allocator@U?$pair@$$CBKUTerminatedProcessDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@@2@@std@@AEAAPEAU?$_List_node@U?$pair@$$CBKUTerminatedProcessDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@PEAX@2@QEAU32@@Z; std::list<std::pair<ulong const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::TerminatedProcessDescriptor>>::_Unchecked_erase(std::_List_node<std::pair<ulong const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::TerminatedProcessDescriptor>,void *> * const)
0x18004f86c  jmp     loc_18004F5DA
0x18004f871  mov     [rsp+0B8h+var_88], 0
0x18004f87a  lea     rcx, [rsi+0C8h]
0x18004f881  lea     r8, [r15+1C0h]
0x18004f888  lea     rdx, [rsp+0B8h+var_88]
0x18004f88d  call    ?find@?$_Hash@V?$_Umap_traits@UPPID@@UProcessEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@V?$_Uhash_compare@UPPID@@UPPIDHasher@DlpUtils@RealtimeProtection@@UPPIDComparer@34@@std@@V?$allocator@U?$pair@$$CBUPPID@@UProcessEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@@7@$0A@@std@@@std@@QEBA?AV?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUPPID@@UProcessEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@@std@@@std@@@2@AEBUPPID@@@Z; std::_Hash<std::_Umap_traits<PPID,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor,std::_Uhash_compare<PPID,RealtimeProtection::DlpUtils::PPIDHasher,RealtimeProtection::DlpUtils::PPIDComparer>,std::allocator<std::pair<PPID const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor>>,0>>::find(PPID const &)
0x18004f892  mov     rdx, [rsp+0B8h+var_88]
0x18004f897  cmp     rdx, [rsi+0D0h]
0x18004f89e  jz      loc_18004F754
0x18004f8a4  add     rdx, 10h; struct PPID *
0x18004f8a8  lea     rax, [rsp+0B8h+var_4C]
0x18004f8ad  mov     [rsp+0B8h+var_98], rax; enum _MP_KNOWN_PROCESS_TYPE *
0x18004f8b2  mov     r8, [rsp+0B8h+var_80]; wchar_t *
0x18004f8b7  mov     rcx, rsi; this
0x18004f8ba  call    ?DereferenceFileInternal@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@AEAAJAEBUPPID@@PEB_W_NAEAW4_MP_KNOWN_PROCESS_TYPE@@@Z; RealtimeProtection::DlpProcessCache::DlpProcessStateCache::DereferenceFileInternal(PPID const &,wchar_t const *,bool,_MP_KNOWN_PROCESS_TYPE &)
0x18004f8bf  mov     r12d, eax
0x18004f8c2  test    eax, eax
0x18004f8c4  jns     loc_18004F754
0x18004f8ca  lea     rdx, WPP_GLOBAL_Control
0x18004f8d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f8d8  cmp     rcx, rdx
0x18004f8db  jz      short loc_18004F8FC
0x18004f8dd  test    byte ptr [rcx+1Ch], 1
0x18004f8e1  jz      short loc_18004F8FC
0x18004f8e3  mov     edx, 55h ; 'U'
0x18004f8e8  mov     r9d, eax
0x18004f8eb  lea     r8, WPP_37379ce3a908304aafca380d907f5915_Traceguids
0x18004f8f2  mov     rcx, [rcx+10h]
0x18004f8f6  call    WPP_SF_d
0x18004f8fb  nop
0x18004f8fc  mov     rcx, r14; SRWLock
0x18004f8ff  call    cs:__imp_ReleaseSRWLockExclusive
0x18004f905  mov     eax, r12d
0x18004f908  jmp     loc_18004F524
0x18004f90d  mov     r12d, [rsp+0B8h+var_50]
0x18004f912  lea     rdx, WPP_GLOBAL_Control
0x18004f919  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f920  cmp     rcx, rdx
0x18004f923  jz      loc_18004F767
0x18004f929  test    byte ptr [rcx+1Ch], 1
0x18004f92d  jz      loc_18004F767
0x18004f933  mov     edx, 56h ; 'V'
0x18004f938  mov     r9d, r12d
0x18004f93b  lea     r8, WPP_37379ce3a908304aafca380d907f5915_Traceguids
0x18004f942  mov     rcx, [rcx+10h]
0x18004f946  call    WPP_SF_d
  ... truncated ...
```
