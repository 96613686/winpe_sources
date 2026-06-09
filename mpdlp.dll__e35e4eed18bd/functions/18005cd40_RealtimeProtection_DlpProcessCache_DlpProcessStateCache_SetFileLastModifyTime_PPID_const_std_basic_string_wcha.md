# RealtimeProtection::DlpProcessCache::DlpProcessStateCache::SetFileLastModifyTime(PPID const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,unsigned __int64)

- ea: `0x18005cd40`
- end: `0x18005d230`
- name: `?SetFileLastModifyTime@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@QEAAXAEBUPPID@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_K@Z`
- size: `1264`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18004fa30`

## callees

- `0x180034420`
- `0x1800344a0`
- `0x1800376e0`
- `0x180037754`
- `0x18004e000`
- `0x18005cd40`
- `0x18005da68`
- `0x1800809d0`
- `0x180107874`
- `0x180109324`
- `0x18010cb40`
- `0x18010ce3c`
- `0x18011db70`
- `0x18023a6d0`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x18005d16c`
- `KERNEL32!CompareStringOrdinal` at `0x18005d16c`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18005cd83`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18005cd83`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18005ce0c`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18005d076`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18005d0bd`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18005d0f0`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18005ce0c`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18005d076`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18005d0bd`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18005d0f0`
- `KERNEL32!CompareFileTime` at `0x18005cdf1`
- `KERNEL32!CompareFileTime` at `0x18005cdf1`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
void __fastcall RealtimeProtection::DlpProcessCache::DlpProcessStateCache::SetFileLastModifyTime(
        RTL_SRWLOCK *a1,
        const FILETIME *a2,
        _QWORD *a3,
        void *a4)
{
  RTL_SRWLOCK *v8; // r15
  _QWORD *Ptr; // rax
  __int64 v10; // rsi
  __int64 v11; // r14
  _QWORD *v12; // rdx
  unsigned __int64 v13; // rdi
  void **v14; // r14
  __int64 v15; // rbx
  __int64 v16; // rcx
  unsigned __int64 v17; // r9
  void **v18; // rdi
  void **v19; // r10
  void **v20; // rcx
  void **v21; // r14
  void **v22; // rbx
  void **v23; // rdx
  __int64 v24; // rbx
  unsigned __int64 i; // rax
  void *v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // rax
  __int64 v29; // rbx
  void *v30; // rdx
  void *v31; // rcx
  _OWORD *v32; // rax
  __int64 v33; // rdi
  const WCHAR *v34; // r8
  void **v35; // rcx
  void *v36[2]; // [rsp+30h] [rbp-B8h] BYREF
  RTL_SRWLOCK *v37; // [rsp+48h] [rbp-A0h]
  char v38; // [rsp+50h] [rbp-98h]
  void *v39; // [rsp+58h] [rbp-90h] BYREF
  void *v40[2]; // [rsp+60h] [rbp-88h] BYREF
  __m128i si128; // [rsp+70h] [rbp-78h]
  void *Src[2]; // [rsp+80h] [rbp-68h] BYREF
  unsigned __int64 v43; // [rsp+90h] [rbp-58h]
  unsigned __int64 v44; // [rsp+98h] [rbp-50h]

  v8 = a1 + 58;
  v37 = a1 + 58;
  AcquireSRWLockExclusive(a1 + 58);
  v38 = 1;
  LODWORD(v39) = 0;
  MpHashCrc32(&v39, 12);
  Ptr = a1[28].Ptr;
  v10 = Ptr[2 * ((unsigned int)v39 & (__int64)a1[31].Ptr) + 1];
  if ( (PVOID)v10 == a1[26].Ptr )
  {
    v10 = 0;
  }
  else
  {
    v11 = Ptr[2 * ((unsigned int)v39 & (__int64)a1[31].Ptr)];
    while ( a2[1].dwLowDateTime != *(_DWORD *)(v10 + 24) || CompareFileTime(a2, (const FILETIME *)(v10 + 16)) )
    {
      if ( v10 == v11 )
      {
        v10 = 0;
        break;
      }
      v10 = *(_QWORD *)(v10 + 8);
    }
  }
  if ( v10 && (PVOID)v10 != a1[26].Ptr )
  {
    v12 = a3;
    if ( a3[3] > 7u )
      v12 = (_QWORD *)*a3;
    RealtimeProtection::DlpUtils::GetFileExtensions(Src, v12);
    *(_OWORD *)v40 = 0;
    si128 = 0;
    v13 = v43;
    v14 = Src;
    if ( v44 > 7 )
      v14 = (void **)Src[0];
    v15 = 0x7FFFFFFFFFFFFFFELL;
    if ( v43 > 0x7FFFFFFFFFFFFFFELL )
      std::_Xlength_error("string too long");
    if ( v43 <= 7 )
    {
      si128.m128i_i64[0] = v43;
      v17 = 7;
      si128.m128i_i64[1] = 7;
      *(_OWORD *)v40 = *(_OWORD *)v14;
    }
    else
    {
      if ( (v43 | 7) > 0x7FFFFFFFFFFFFFFELL )
      {
        v16 = 0x7FFFFFFFFFFFFFFFLL;
      }
      else
      {
        v15 = v43 | 7;
        if ( (v43 | 7) < 0xA )
          v15 = 10;
        v16 = v15 + 1;
        if ( (unsigned __int64)(v15 + 1) > 0x7FFFFFFFFFFFFFFFLL )
          std::_Throw_bad_array_new_length();
      }
      _mm_lfence();
      v40[0] = (void *)std::_Allocate<16,std::_Default_allocate_traits>(2 * v16);
      si128.m128i_i64[0] = v13;
      si128.m128i_i64[1] = v15;
      memmove(v40[0], v14, 2 * v13 + 2);
      v17 = si128.m128i_u64[1];
    }
    v18 = v40;
    v19 = (void **)v40[0];
    if ( v17 > 7 )
      v18 = (void **)v40[0];
    v20 = v40;
    if ( v17 > 7 )
      v20 = (void **)v40[0];
    v21 = (void **)((char *)v20 + 2 * si128.m128i_i64[0]);
    v22 = v40;
    if ( v17 > 7 )
      v22 = (void **)v40[0];
    while ( v22 != v21 )
    {
      *(_WORD *)v18 = towlower(*(_WORD *)v22);
      v22 = (void **)((char *)v22 + 2);
      v18 = (void **)((char *)v18 + 2);
      v17 = si128.m128i_u64[1];
      v19 = (void **)v40[0];
    }
    v23 = v40;
    if ( v17 > 7 )
      v23 = v19;
    v24 = 0xCBF29CE484222325uLL;
    for ( i = 0; i < 2 * si128.m128i_i64[0]; ++i )
      v24 = 0x100000001B3LL * (*((unsigned __int8 *)v23 + i) ^ (unsigned __int64)v24);
    if ( v17 > 7 )
    {
      v26 = (void *)(2 * v17 + 2);
      v39 = v26;
      v36[0] = v19;
      if ( (unsigned __int64)v26 >= 0x1000 )
      {
        std::_Adjust_manually_vector_aligned(v36, (unsigned __int64 *)&v39);
        v26 = v39;
        v19 = (void **)v36[0];
      }
      operator delete(v19, (const struct std::nothrow_t *)v26);
    }
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v40[0]) = 0;
    v27 = 2 * (v24 & *(_QWORD *)(v10 + 224));
    v28 = *(_QWORD *)(v10 + 200);
    v29 = *(_QWORD *)(v28 + 16 * (v24 & *(_QWORD *)(v10 + 224)) + 8);
    if ( v29 == *(_QWORD *)(v10 + 184) )
    {
LABEL_38:
      v29 = 0;
    }
    else
    {
      v33 = *(_QWORD *)(v28 + 8 * v27);
      while ( 1 )
      {
        v34 = (const WCHAR *)(v29 + 16);
        if ( *(_QWORD *)(v29 + 40) > 7u )
          v34 = *(const WCHAR **)v34;
        v35 = Src;
        if ( v44 > 7 )
          v35 = (void **)Src[0];
        if ( CompareStringOrdinal((LPCWCH)v35, -1, v34, -1, 1) == 2 )
          break;
        if ( v29 == v33 )
          goto LABEL_38;
        v29 = *(_QWORD *)(v29 + 8);
      }
    }
    if ( v29 && v29 != *(_QWORD *)(v10 + 184) )
    {
      v36[0] = 0;
      std::_Hash<std::_Umap_traits<std::wstring,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileEnforcementDescriptor,std::_Uhash_compare<std::wstring,RealtimeProtection::DlpUtils::CaseInsensitiveHasher,RealtimeProtection::DlpUtils::CStrOrdinalCompEqual>,std::allocator<std::pair<std::wstring const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileEnforcementDescriptor>>,0>>::find(
        v29 + 48,
        v36,
        a3);
      v32 = v36[0];
      if ( v36[0] != *(void **)(v29 + 56) )
      {
        v36[0] = a4;
        LOBYTE(v36[1]) = 1;
        v32[31] = *(_OWORD *)v36;
      }
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(Src);
      ReleaseSRWLockExclusive(v8);
    }
    else
    {
      if ( v44 > 7 )
      {
        v30 = (void *)(2 * v44 + 2);
        v36[0] = v30;
        v31 = Src[0];
        v39 = Src[0];
        if ( (unsigned __int64)v30 >= 0x1000 )
        {
          std::_Adjust_manually_vector_aligned(&v39, (unsigned __int64 *)v36);
          v30 = v36[0];
          v31 = v39;
        }
        operator delete(v31, (const struct std::nothrow_t *)v30);
      }
      v43 = 0;
      v44 = 7;
      LOWORD(Src[0]) = 0;
      ReleaseSRWLockExclusive(v8);
    }
  }
  else
  {
    ReleaseSRWLockExclusive(v8);
  }
}

```

## disassembly

```asm
0x18005cd40  push    rbx
0x18005cd42  push    rsi
0x18005cd43  push    rdi
0x18005cd44  push    r12
0x18005cd46  push    r13
0x18005cd48  push    r14
0x18005cd4a  push    r15
0x18005cd4c  sub     rsp, 0B0h
0x18005cd53  mov     rax, cs:__security_cookie
0x18005cd5a  xor     rax, rsp
0x18005cd5d  mov     [rsp+0E8h+var_48], rax
0x18005cd65  mov     r13, r9
0x18005cd68  mov     r12, r8
0x18005cd6b  mov     rdi, rdx
0x18005cd6e  mov     rbx, rcx
0x18005cd71  xor     r14d, r14d
0x18005cd74  lea     r15, [rcx+1D0h]
0x18005cd7b  mov     [rsp+0E8h+var_A0], r15
0x18005cd80  mov     rcx, r15; SRWLock
0x18005cd83  call    cs:__imp_AcquireSRWLockExclusive
0x18005cd89  mov     [rsp+0E8h+var_98], 1
0x18005cd8e  mov     dword ptr [rsp+0E8h+var_90], r14d
0x18005cd93  mov     r8, rdi
0x18005cd96  mov     edx, 0Ch
0x18005cd9b  lea     rcx, [rsp+0E8h+var_90]
0x18005cda0  call    MpHashCrc32
0x18005cda5  mov     eax, dword ptr [rsp+0E8h+var_90]
0x18005cda9  mov     rcx, [rbx+0F8h]
0x18005cdb0  and     rcx, rax
0x18005cdb3  add     rcx, rcx
0x18005cdb6  mov     rax, [rbx+0E0h]
0x18005cdbd  mov     rsi, [rax+rcx*8+8]
0x18005cdc2  cmp     rsi, [rbx+0D0h]
0x18005cdc9  jz      loc_18005D18A
0x18005cdcf  mov     r14, [rax+rcx*8]
0x18005cdd3  lea     rdx, [rsi+10h]; lpFileTime2
0x18005cdd7  mov     eax, [rdx+8]
0x18005cdda  cmp     [rdi+8], eax
0x18005cddd  jz      short loc_18005CDEE
0x18005cddf  cmp     rsi, r14
0x18005cde2  jz      loc_18005D0FC
0x18005cde8  mov     rsi, [rsi+8]
0x18005cdec  jmp     short loc_18005CDD3
0x18005cdee  mov     rcx, rdi; lpFileTime1
0x18005cdf1  call    cs:__imp_CompareFileTime
0x18005cdf7  test    eax, eax
0x18005cdf9  jnz     short loc_18005CDDF
0x18005cdfb  test    rsi, rsi
0x18005cdfe  jz      short loc_18005CE09
0x18005ce00  cmp     rsi, [rbx+0D0h]
0x18005ce07  jnz     short loc_18005CE36
0x18005ce09  mov     rcx, r15; SRWLock
0x18005ce0c  call    cs:__imp_ReleaseSRWLockExclusive
0x18005ce12  nop
0x18005ce13  mov     rcx, [rsp+0E8h+var_48]
0x18005ce1b  xor     rcx, rsp; StackCookie
0x18005ce1e  call    __security_check_cookie
0x18005ce23  add     rsp, 0B0h
0x18005ce2a  pop     r15
0x18005ce2c  pop     r14
0x18005ce2e  pop     r13
0x18005ce30  pop     r12
0x18005ce32  pop     rdi
0x18005ce33  pop     rsi
0x18005ce34  pop     rbx
0x18005ce35  retn
0x18005ce36  mov     rdx, r12
0x18005ce39  cmp     qword ptr [r12+18h], 7
0x18005ce3f  ja      loc_18005D082
0x18005ce45  lea     rcx, [rsp+0E8h+Src]
0x18005ce4d  call    ?GetFileExtensions@DlpUtils@RealtimeProtection@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W@Z; RealtimeProtection::DlpUtils::GetFileExtensions(wchar_t const *)
0x18005ce52  nop
0x18005ce53  xorps   xmm0, xmm0
0x18005ce56  movups  xmmword ptr [rsp+0E8h+var_88], xmm0
0x18005ce5b  xorps   xmm1, xmm1
0x18005ce5e  movdqu  [rsp+0E8h+var_78], xmm1
0x18005ce64  mov     rdi, [rsp+0E8h+var_58]
0x18005ce6c  lea     r14, [rsp+0E8h+Src]
0x18005ce74  cmp     [rsp+0E8h+var_50], 7
0x18005ce7d  cmova   r14, [rsp+0E8h+Src]
0x18005ce86  mov     rbx, 7FFFFFFFFFFFFFFEh
0x18005ce90  cmp     rdi, rbx
0x18005ce93  ja      loc_18005D1CE
0x18005ce99  cmp     rdi, 7
0x18005ce9d  jbe     loc_18005D103
0x18005cea3  mov     rax, rdi
0x18005cea6  or      rax, 7
0x18005ceaa  cmp     rax, rbx
0x18005cead  ja      loc_18005D121
0x18005ceb3  mov     rbx, rax
0x18005ceb6  mov     ecx, 0Ah
0x18005cebb  cmp     rax, rcx
0x18005cebe  cmovb   rbx, rcx
0x18005cec2  lea     rcx, [rbx+1]
0x18005cec6  mov     rax, 7FFFFFFFFFFFFFFFh
0x18005ced0  cmp     rcx, rax
0x18005ced3  ja      loc_18005D1DA
0x18005ced9  lfence
0x18005cedc  add     rcx, rcx
0x18005cedf  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18005cee4  mov     [rsp+0E8h+var_88], rax
0x18005cee9  mov     qword ptr [rsp+0E8h+var_78], rdi
0x18005ceee  mov     qword ptr [rsp+0E8h+var_78+8], rbx
0x18005cef3  lea     r8, ds:2[rdi*2]; Size
0x18005cefb  mov     rdx, r14; Src
0x18005cefe  mov     rcx, rax; void *
0x18005cf01  call    memmove
0x18005cf06  mov     r9, qword ptr [rsp+0E8h+var_78+8]
0x18005cf0b  lea     rdi, [rsp+0E8h+var_88]
0x18005cf10  mov     r10, [rsp+0E8h+var_88]
0x18005cf15  cmp     r9, 7
0x18005cf19  cmova   rdi, r10
0x18005cf1d  lea     rcx, [rsp+0E8h+var_88]
0x18005cf22  cmova   rcx, r10
0x18005cf26  mov     rax, qword ptr [rsp+0E8h+var_78]
0x18005cf2b  lea     r14, [rcx+rax*2]
0x18005cf2f  lea     rbx, [rsp+0E8h+var_88]
0x18005cf34  cmova   rbx, r10
0x18005cf38  cmp     rbx, r14
0x18005cf3b  jz      short loc_18005CF5C
0x18005cf3d  movzx   ecx, word ptr [rbx]; C
0x18005cf40  call    towlower
0x18005cf45  mov     [rdi], ax
0x18005cf48  add     rbx, 2
0x18005cf4c  add     rdi, 2
0x18005cf50  mov     r9, qword ptr [rsp+0E8h+var_78+8]
0x18005cf55  mov     r10, [rsp+0E8h+var_88]
0x18005cf5a  jmp     short loc_18005CF38
0x18005cf5c  lea     rdx, [rsp+0E8h+var_88]
0x18005cf61  cmp     r9, 7
0x18005cf65  cmova   rdx, r10
0x18005cf69  mov     rbx, 0CBF29CE484222325h
0x18005cf73  mov     rax, qword ptr [rsp+0E8h+var_78]
0x18005cf78  lea     r8, [rax+rax]
0x18005cf7c  xor     r14d, r14d
0x18005cf7f  mov     eax, r14d
0x18005cf82  test    r8, r8
0x18005cf85  jz      short loc_18005CFA4
0x18005cf87  mov     r11, 100000001B3h
0x18005cf91  movzx   ecx, byte ptr [rax+rdx]
0x18005cf95  xor     rbx, rcx
0x18005cf98  imul    rbx, r11
0x18005cf9c  inc     rax
0x18005cf9f  cmp     rax, r8
0x18005cfa2  jb      short loc_18005CF91
0x18005cfa4  cmp     r9, 7
0x18005cfa8  jbe     short loc_18005CFD1
0x18005cfaa  lea     rdx, ds:2[r9*2]; struct std::nothrow_t *
0x18005cfb2  mov     [rsp+0E8h+var_90], rdx
0x18005cfb7  mov     [rsp+0E8h+var_B8], r10
0x18005cfbc  cmp     rdx, 1000h
0x18005cfc3  jnb     loc_18005D192
0x18005cfc9  mov     rcx, r10; void *
0x18005cfcc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005cfd1  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18005cfd9  movdqu  [rsp+0E8h+var_78], xmm0
0x18005cfdf  mov     word ptr [rsp+0E8h+var_88], r14w
0x18005cfe5  mov     rcx, [rsi+0E0h]
0x18005cfec  and     rcx, rbx
0x18005cfef  add     rcx, rcx
0x18005cff2  mov     rax, [rsi+0C8h]
0x18005cff9  mov     rbx, [rax+rcx*8+8]
0x18005cffe  cmp     rbx, [rsi+0B8h]
0x18005d005  jnz     loc_18005D130
0x18005d00b  mov     rbx, r14
0x18005d00e  test    rbx, rbx
0x18005d011  jz      short loc_18005D01C
0x18005d013  cmp     rbx, [rsi+0B8h]
0x18005d01a  jnz     short loc_18005D08B
0x18005d01c  mov     rdx, [rsp+0E8h+var_50]
0x18005d024  cmp     rdx, 7
0x18005d028  jbe     short loc_18005D056
0x18005d02a  lea     rdx, ds:2[rdx*2]; struct std::nothrow_t *
0x18005d032  mov     [rsp+0E8h+var_B8], rdx
0x18005d037  mov     rcx, [rsp+0E8h+Src]; void *
0x18005d03f  mov     [rsp+0E8h+var_90], rcx
0x18005d044  cmp     rdx, 1000h
0x18005d04b  jnb     loc_18005D1B0
0x18005d051  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005d056  mov     [rsp+0E8h+var_58], r14
0x18005d05e  mov     [rsp+0E8h+var_50], 7
0x18005d06a  mov     word ptr [rsp+0E8h+Src], r14w
0x18005d073  mov     rcx, r15; SRWLock
0x18005d076  call    cs:__imp_ReleaseSRWLockExclusive
0x18005d07c  nop
0x18005d07d  jmp     loc_18005CE13
0x18005d082  mov     rdx, [r12]
0x18005d086  jmp     loc_18005CE45
0x18005d08b  mov     [rsp+0E8h+var_B8], r14
0x18005d090  lea     rcx, [rbx+30h]
0x18005d094  mov     r8, r12
0x18005d097  lea     rdx, [rsp+0E8h+var_B8]
0x18005d09c  call    ?find@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UFileEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UCaseInsensitiveHasher@DlpUtils@RealtimeProtection@@UCStrOrdinalCompEqual@45@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UFileEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UFileEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@@std@@@std@@@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@@Z; std::_Hash<std::_Umap_traits<std::wstring,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileEnforcementDescriptor,std::_Uhash_compare<std::wstring,RealtimeProtection::DlpUtils::CaseInsensitiveHasher,RealtimeProtection::DlpUtils::CStrOrdinalCompEqual>,std::allocator<std::pair<std::wstring const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileEnforcementDescriptor>>,0>>::find(std::wstring const &)
0x18005d0a1  mov     rax, [rsp+0E8h+var_B8]
0x18005d0a6  cmp     rax, [rbx+38h]
0x18005d0aa  jnz     short loc_18005D0C9
0x18005d0ac  lea     rcx, [rsp+0E8h+Src]; void *
0x18005d0b4  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x18005d0b9  nop
0x18005d0ba  mov     rcx, r15; SRWLock
0x18005d0bd  call    cs:__imp_ReleaseSRWLockExclusive
0x18005d0c3  nop
0x18005d0c4  jmp     loc_18005CE13
0x18005d0c9  mov     [rsp+0E8h+var_B8], r13
0x18005d0ce  mov     byte ptr [rsp+0E8h+var_B8+8], 1
0x18005d0d3  movups  xmm0, xmmword ptr [rsp+0E8h+var_B8]
0x18005d0d8  movups  xmmword ptr [rax+1F0h], xmm0
0x18005d0df  lea     rcx, [rsp+0E8h+Src]; void *
0x18005d0e7  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x18005d0ec  nop
0x18005d0ed  mov     rcx, r15; SRWLock
0x18005d0f0  call    cs:__imp_ReleaseSRWLockExclusive
0x18005d0f6  nop
0x18005d0f7  jmp     loc_18005CE13
0x18005d0fc  xor     esi, esi
0x18005d0fe  jmp     loc_18005CDFB
0x18005d103  mov     qword ptr [rsp+0E8h+var_78], rdi
0x18005d108  mov     r9d, 7
0x18005d10e  mov     qword ptr [rsp+0E8h+var_78+8], r9
0x18005d113  movups  xmm0, xmmword ptr [r14]
0x18005d117  movups  xmmword ptr [rsp+0E8h+var_88], xmm0
0x18005d11c  jmp     loc_18005CF0B
0x18005d121  mov     rcx, 7FFFFFFFFFFFFFFFh
0x18005d12b  jmp     loc_18005CED9
0x18005d130  mov     rdi, [rax+rcx*8]
0x18005d134  lea     r8, [rbx+10h]
0x18005d138  cmp     qword ptr [rbx+28h], 7
0x18005d13d  jbe     short loc_18005D142
0x18005d13f  mov     r8, [r8]; lpString2
0x18005d142  lea     rcx, [rsp+0E8h+Src]
0x18005d14a  cmp     [rsp+0E8h+var_50], 7
0x18005d153  cmova   rcx, [rsp+0E8h+Src]; lpString1
0x18005d15c  mov     [rsp+0E8h+bIgnoreCase], 1; bIgnoreCase
0x18005d164  mov     edx, 0FFFFFFFFh; cchCount1
0x18005d169  mov     r9d, edx; cchCount2
0x18005d16c  call    cs:__imp_CompareStringOrdinal
0x18005d172  cmp     eax, 2
0x18005d175  jz      loc_18005D00E
0x18005d17b  cmp     rbx, rdi
0x18005d17e  jz      loc_18005D00B
0x18005d184  mov     rbx, [rbx+8]
0x18005d188  jmp     short loc_18005D134
0x18005d18a  mov     rsi, r14
0x18005d18d  jmp     loc_18005CDFB
0x18005d192  lea     rdx, [rsp+0E8h+var_90]; unsigned __int64 *
0x18005d197  lea     rcx, [rsp+0E8h+var_B8]; void **
0x18005d19c  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x18005d1a1  mov     rdx, [rsp+0E8h+var_90]
0x18005d1a6  mov     r10, [rsp+0E8h+var_B8]
0x18005d1ab  jmp     loc_18005CFC9
0x18005d1b0  lea     rdx, [rsp+0E8h+var_B8]; unsigned __int64 *
0x18005d1b5  lea     rcx, [rsp+0E8h+var_90]; void **
0x18005d1ba  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x18005d1bf  mov     rdx, [rsp+0E8h+var_B8]
0x18005d1c4  mov     rcx, [rsp+0E8h+var_90]
0x18005d1c9  jmp     loc_18005D051
0x18005d1ce  lea     rcx, aStringTooLong; "string too long"
0x18005d1d5  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18005d1da  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
0x18005d1e0  mov     r9d, dword ptr [rsp+0E8h+var_90]
0x18005d1e5  jmp     short loc_18005D1F5
0x18005d1e7  mov     r9d, dword ptr [rsp+0E8h+var_90]
0x18005d1ec  test    r9d, r9d
0x18005d1ef  jns     loc_18005CE13
0x18005d1f5  lea     rax, WPP_GLOBAL_Control
0x18005d1fc  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d203  cmp     rcx, rax
0x18005d206  jz      loc_18005CE13
0x18005d20c  test    byte ptr [rcx+1Ch], 1
0x18005d210  jz      loc_18005CE13
0x18005d216  mov     edx, 0E7h
0x18005d21b  lea     r8, WPP_37379ce3a908304aafca380d907f5915_Traceguids
0x18005d222  mov     rcx, [rcx+10h]
0x18005d226  call    WPP_SF_d
0x18005d22b  jmp     loc_18005CE13
```
