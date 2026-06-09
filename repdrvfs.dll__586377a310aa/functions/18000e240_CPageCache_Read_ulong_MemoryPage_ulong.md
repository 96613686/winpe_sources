# CPageCache::Read(ulong,MemoryPage * *,ulong)

- ea: `0x18000e240`
- end: `0x18000e914`
- name: `?Read@CPageCache@@QEAAKKPEAPEAVMemoryPage@@K@Z`
- size: `1748`
- prototype: `unsigned int __fastcall(CPageCache *__hidden this, unsigned int, struct MemoryPage **, unsigned int)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000e000`

## callees

- `0x1800012b8`
- `0x18000e240`
- `0x18000f3b4`
- `0x18000f460`
- `0x18000f8a0`
- `0x18000f8f0`
- `0x18000f950`
- `0x18001060c`
- `0x180011490`
- `0x180012cd4`
- `0x18001a6b0`
- `0x180021f30`
- `0x180030798`
- `0x18003d184`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000e689`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000e689`
- `wbemcomn!GetMemLogObject` at `0x18000e648`
- `wbemcomn!GetMemLogObject` at `0x18000e6cd`
- `wbemcomn!GetMemLogObject` at `0x18000e72b`
- `wbemcomn!GetMemLogObject` at `0x18000e80e`
- `wbemcomn!GetMemLogObject` at `0x18000e875`
- `wbemcomn!GetMemLogObject` at `0x18000e8c2`
- `wbemcomn!GetMemLogObject` at `0x18000e648`
- `wbemcomn!GetMemLogObject` at `0x18000e6cd`
- `wbemcomn!GetMemLogObject` at `0x18000e72b`
- `wbemcomn!GetMemLogObject` at `0x18000e80e`
- `wbemcomn!GetMemLogObject` at `0x18000e875`
- `wbemcomn!GetMemLogObject` at `0x18000e8c2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000e656`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000e6dd`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000e73b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000e819`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000e885`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000e8cd`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000e656`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000e6dd`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000e73b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000e819`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000e885`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000e8cd`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000e2bc`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000e2de`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000e2f4`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000e2bc`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000e2de`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000e2f4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000e268`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000e268`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000e437`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000e437`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18000e408`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18000e408`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e6b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e867`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e6b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e867`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CPageCache::Read(CPageCache *this, unsigned int a2, struct MemoryPage **a3, unsigned int a4)
{
  __int64 v4; // r13
  __int64 v6; // rdi
  __int64 v8; // rdx
  unsigned int i; // esi
  __int64 v10; // rbx
  MemoryPage *v11; // rdi
  __int64 v13; // r9
  __int64 v14; // rdx
  __int64 v15; // rcx
  unsigned int j; // ebx
  __int64 v17; // rsi
  void *v18; // rbx
  LPVOID *Page; // rsi
  LPVOID *v20; // rbx
  _QWORD *v21; // rdx
  int *v22; // r9
  __int64 v23; // r8
  __int64 v24; // r8
  int v25; // ecx
  int *v26; // rsi
  unsigned int v27; // eax
  __int64 v28; // r9
  __int64 *v29; // rsi
  unsigned __int64 v30; // rax
  const struct SCachePage *v31; // rdx
  MemoryPage *v32; // rdi
  MemoryPage *v33; // rcx
  unsigned int v34; // edi
  __int64 v35; // r9
  CMemoryLog *v36; // rax
  DWORD LastError; // esi
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v39; // rax
  CVarObjHeap *v40; // rcx
  __int64 v41; // rdx
  unsigned __int64 v42; // rdi
  char *v43; // rcx
  CMemoryLog *v44; // rax
  CMemoryLog *v45; // rax
  CMemoryLog *v46; // rax
  _DWORD v47[2]; // [rsp+30h] [rbp-28h] BYREF
  LPVOID *v48; // [rsp+38h] [rbp-20h]
  int v49; // [rsp+40h] [rbp-18h] BYREF
  int v50; // [rsp+44h] [rbp-14h]
  MemoryPage *v51; // [rsp+48h] [rbp-10h]
  __int64 NumberOfBytesRead; // [rsp+B0h] [rbp+58h] BYREF

  v4 = a4;
  v6 = a2;
  if ( !a3 )
  {
    MemLogObject = GetMemLogObject();
    LastError = 87;
    CMemoryLog::Write(MemLogObject, 87);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids, 87);
    }
    return LastError;
  }
  *((_DWORD *)this + 9) = GetTickCount();
  v8 = *((_QWORD *)this + 8);
  for ( i = 0; i < (unsigned int)((*((_QWORD *)this + 9) - v8) >> 4); ++i )
  {
    v10 = 16LL * i;
    if ( *(_DWORD *)(v10 + v8) == (_DWORD)v6 )
    {
      v49 = *(_DWORD *)(v10 + v8);
      v11 = *(MemoryPage **)(v10 + v8 + 8);
      v51 = v11;
      v50 = *(_DWORD *)(v10 + v8 + 4);
      if ( v11 )
      {
        if ( *(_DWORD *)v11 != 1313820496
          || *((_DWORD *)v11 + 1) != 1347374926
          || (unsigned int)(*((_DWORD *)v11 + 2) - 1) > 0xFFF )
        {
          DebugBreak();
        }
        _InterlockedIncrement((volatile signed __int32 *)v11 + 2);
      }
      if ( !g_bPerformingVerify && i > *((_DWORD *)this + 4) )
      {
        std::vector<SCachePage,wbem_allocator<SCachePage>>::erase(
          (__int64)this + 64,
          &NumberOfBytesRead,
          v10 + *((_QWORD *)this + 8));
        std::vector<SCachePage,wbem_allocator<SCachePage>>::_Insert_n(
          (__int64 *)this + 8,
          &NumberOfBytesRead,
          *((_QWORD *)this + 8),
          v13,
          (struct SCachePage *)&v49);
        v11 = v51;
      }
      *a3 = v11;
      if ( *(_DWORD *)v11 != 1313820496
        || *((_DWORD *)v11 + 1) != 1347374926
        || (unsigned int)(*((_DWORD *)v11 + 2) - 1) > 0xFFF )
      {
        DebugBreak();
      }
      _InterlockedIncrement((volatile signed __int32 *)v11 + 2);
      ++*((_DWORD *)this + 10);
      if ( *(_DWORD *)v11 != 1313820496
        || *((_DWORD *)v11 + 1) != 1347374926
        || (unsigned int)(*((_DWORD *)v11 + 2) - 1) > 0xFFF )
      {
        DebugBreak();
      }
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v11 + 2, 0xFFFFFFFF) == 1 )
        CWin32DefaultArena::WbemMemFree(v11);
      return 0;
    }
  }
  v14 = *((_QWORD *)this + 11);
  v15 = (*((_QWORD *)this + 12) - v14) >> 4;
  for ( j = 0; j < (unsigned int)v15; ++j )
  {
    v17 = 16LL * j;
    if ( *(_DWORD *)(v17 + v14) == (_DWORD)v6 )
    {
      v49 = *(_DWORD *)(v17 + v14);
      v32 = *(MemoryPage **)(v17 + v14 + 8);
      v51 = v32;
      v50 = *(_DWORD *)(v17 + v14 + 4);
      if ( v32 )
        MemoryPage::AddRef(v32);
      if ( !g_bPerformingVerify && j > *((_DWORD *)this + 5) )
      {
        std::vector<SCachePage,wbem_allocator<SCachePage>>::erase(
          (__int64)this + 88,
          &NumberOfBytesRead,
          v17 + *((_QWORD *)this + 11));
        std::vector<SCachePage,wbem_allocator<SCachePage>>::_Insert_n(
          (__int64 *)this + 11,
          &NumberOfBytesRead,
          *((_QWORD *)this + 11),
          v35,
          (struct SCachePage *)&v49);
        v32 = v51;
      }
      *a3 = v32;
      MemoryPage::AddRef(v32);
      ++*((_DWORD *)this + 10);
      if ( v32 )
      {
        v33 = v32;
LABEL_56:
        MemoryPage::Release(v33);
        return 0;
      }
      return 0;
    }
  }
  v47[0] = v6;
  v47[1] = v4;
  v48 = 0;
  ++*((_DWORD *)this + 11);
  v18 = (void *)*((_QWORD *)this + 7);
  Page = (LPVOID *)MemoryPage::AllocatePage(v15);
  if ( !Page )
  {
    v39 = GetMemLogObject();
    LastError = 14;
    CMemoryLog::Write(v39, 14);
    v40 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_102;
    }
    v41 = 39;
    goto LABEL_101;
  }
  if ( SetFilePointerEx(v18, (LARGE_INTEGER)(v6 << 13), 0, 0) )
  {
    LODWORD(NumberOfBytesRead) = 0;
    if ( ReadFile(v18, Page[2], 0x2000u, (LPDWORD)&NumberOfBytesRead, 0) && (_DWORD)NumberOfBytesRead == 0x2000 )
    {
      v20 = Page;
      goto LABEL_38;
    }
    GetLastError();
    MemoryPage::Release((MemoryPage *)Page);
    v45 = GetMemLogObject();
    LastError = 87;
    CMemoryLog::Write(v45, 87);
    v40 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v41 = 40;
LABEL_101:
      WPP_SF_d(*((_QWORD *)v40 + 2), v41, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids, LastError);
    }
LABEL_102:
    v46 = GetMemLogObject();
    CMemoryLog::Write(v46, LastError);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids, LastError);
    }
    SCachePage::~SCachePage((SCachePage *)v47);
    return LastError;
  }
  v20 = 0;
  MemoryPage::Release((MemoryPage *)Page);
  LastError = GetLastError();
  if ( LastError )
    goto LABEL_102;
LABEL_38:
  v48 = v20;
  v21 = (_QWORD *)*((_QWORD *)this + 14);
  v22 = 0;
  v23 = v21[41];
  if ( (unsigned int)v4 >= -1431655765 * (unsigned int)((v21[42] - v23) >> 3)
    || (v26 = (int *)(v23 + 24 * v4), *v26 >= 0)
    || (*v26 & 0x3FFFFFFF) != (_DWORD)v6 )
  {
    v24 = v21[28];
    if ( (unsigned int)v4 >= -1431655765 * (unsigned int)((v21[29] - v24) >> 3) )
      goto LABEL_81;
    v25 = *(_DWORD *)(v24 + 24 * v4);
    if ( (v25 & 0x40000000) != 0 && (v25 & 0x3FFFFFFF) == (_DWORD)v6 )
      v22 = (int *)(v24 + 24 * v4);
    v26 = v22;
    if ( v25 == (_DWORD)v6 )
      v26 = (int *)(v24 + 24 * v4);
    if ( !v26 )
LABEL_81:
      v26 = 0;
  }
  v27 = ~(unsigned int)CreateCRC32((const unsigned __int8 *)v20[2]);
  *((_DWORD *)v20 + 7) = v27;
  if ( v27 != v26[1] )
  {
    CRepositoryCorruption::SetRepositoryCorrupted(3, 0, 0);
    v36 = GetMemLogObject();
    CMemoryLog::Write(v36, 1358);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids, 1358);
    }
    SCachePage::~SCachePage((SCachePage *)v47);
    return 1358;
  }
  v29 = (__int64 *)((char *)this + 64);
  if ( g_bPerformingVerify )
  {
    v30 = *((_QWORD *)this + 9);
    if ( (unsigned __int64)v47 >= v30 || *v29 > (unsigned __int64)v47 )
    {
      if ( v30 == *((_QWORD *)this + 10) )
        std::vector<SCachePage,wbem_allocator<SCachePage>>::_Reserve((__int64 *)this + 8);
      v31 = (const struct SCachePage *)v47;
    }
    else
    {
      v42 = (unsigned __int64)v47 - *v29;
      if ( v30 == *((_QWORD *)this + 10) )
        std::vector<SCachePage,wbem_allocator<SCachePage>>::_Reserve((__int64 *)this + 8);
      v31 = (const struct SCachePage *)(*v29 + (v42 & 0xFFFFFFFFFFFFFFF0uLL));
    }
    SCachePage::SCachePage(*((SCachePage **)this + 9), v31);
    *((_QWORD *)this + 9) += 16LL;
  }
  else
  {
    std::vector<SCachePage,wbem_allocator<SCachePage>>::_Insert_n(
      (__int64 *)this + 8,
      &NumberOfBytesRead,
      *v29,
      v28,
      (struct SCachePage *)v47);
    v20 = v48;
  }
  v34 = CPageCache::Spill(this);
  if ( v34 )
  {
    v43 = (char *)this + 64;
    if ( g_bPerformingVerify )
      std::vector<SCachePage,wbem_allocator<SCachePage>>::pop_back(v43);
    else
      std::vector<SCachePage,wbem_allocator<SCachePage>>::erase((__int64)v43, &NumberOfBytesRead, *v29);
    v44 = GetMemLogObject();
    CMemoryLog::Write(v44, v34);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids, v34);
    }
    SCachePage::~SCachePage((SCachePage *)v47);
    return v34;
  }
  *a3 = (struct MemoryPage *)v20;
  MemoryPage::AddRef((MemoryPage *)v20);
  if ( v20 )
  {
    v33 = (MemoryPage *)v20;
    goto LABEL_56;
  }
  return 0;
}

```

## disassembly

```asm
0x18000e240  push    rbp
0x18000e242  push    rbx
0x18000e243  push    rsi
0x18000e244  push    rdi
0x18000e245  push    r12
0x18000e247  push    r13
0x18000e249  push    r14
0x18000e24b  push    r15
0x18000e24d  mov     rbp, rsp
0x18000e250  sub     rsp, 58h
0x18000e254  mov     r13d, r9d
0x18000e257  mov     r15, r8
0x18000e25a  mov     edi, edx
0x18000e25c  mov     r14, rcx
0x18000e25f  test    r8, r8
0x18000e262  jz      loc_18000E6CD
0x18000e268  call    cs:__imp_GetTickCount
0x18000e26e  mov     [r14+24h], eax
0x18000e272  mov     rdx, [r14+40h]
0x18000e276  mov     rcx, [r14+48h]
0x18000e27a  sub     rcx, rdx
0x18000e27d  sar     rcx, 4
0x18000e281  xor     esi, esi
0x18000e283  cmp     esi, ecx
0x18000e285  jnb     loc_18000E3A6
0x18000e28b  mov     ebx, esi
0x18000e28d  shl     rbx, 4
0x18000e291  mov     eax, [rbx+rdx]
0x18000e294  cmp     eax, edi
0x18000e296  jz      short loc_18000E29C
0x18000e298  inc     esi
0x18000e29a  jmp     short loc_18000E283
0x18000e29c  mov     [rbp+var_18], eax
0x18000e29f  mov     rdi, [rbx+rdx+8]
0x18000e2a4  mov     [rbp+var_10], rdi
0x18000e2a8  mov     eax, [rbx+rdx+4]
0x18000e2ac  mov     [rbp+var_14], eax
0x18000e2af  test    rdi, rdi
0x18000e2b2  jz      short loc_18000E2C6
0x18000e2b4  cmp     dword ptr [rdi], 4E4F4F50h
0x18000e2ba  jz      short loc_18000E320
0x18000e2bc  call    cs:__imp_DebugBreak
0x18000e2c2  lock inc dword ptr [rdi+8]
0x18000e2c6  cmp     cs:?g_bPerformingVerify@@3_NA, 0; bool g_bPerformingVerify
0x18000e2cd  jz      loc_18000E365
0x18000e2d3  mov     [r15], rdi
0x18000e2d6  cmp     dword ptr [rdi], 4E4F4F50h
0x18000e2dc  jz      short loc_18000E337
0x18000e2de  call    cs:__imp_DebugBreak
0x18000e2e4  lock inc dword ptr [rdi+8]
0x18000e2e8  inc     dword ptr [r14+28h]
0x18000e2ec  cmp     dword ptr [rdi], 4E4F4F50h
0x18000e2f2  jz      short loc_18000E34E
0x18000e2f4  call    cs:__imp_DebugBreak
0x18000e2fa  mov     eax, 0FFFFFFFFh
0x18000e2ff  lock xadd [rdi+8], eax
0x18000e304  cmp     eax, 1
0x18000e307  jz      loc_18000E686
0x18000e30d  xor     eax, eax
0x18000e30f  add     rsp, 58h
0x18000e313  pop     r15
0x18000e315  pop     r14
0x18000e317  pop     r13
0x18000e319  pop     r12
0x18000e31b  pop     rdi
0x18000e31c  pop     rsi
0x18000e31d  pop     rbx
0x18000e31e  pop     rbp
0x18000e31f  retn
0x18000e320  cmp     dword ptr [rdi+4], 504F4F4Eh
0x18000e327  jnz     short loc_18000E2BC
0x18000e329  mov     eax, [rdi+8]
0x18000e32c  dec     eax
0x18000e32e  cmp     eax, 0FFFh
0x18000e333  jbe     short loc_18000E2C2
0x18000e335  jmp     short loc_18000E2BC
0x18000e337  cmp     dword ptr [rdi+4], 504F4F4Eh
0x18000e33e  jnz     short loc_18000E2DE
0x18000e340  mov     eax, [rdi+8]
0x18000e343  dec     eax
0x18000e345  cmp     eax, 0FFFh
0x18000e34a  jbe     short loc_18000E2E4
0x18000e34c  jmp     short loc_18000E2DE
0x18000e34e  cmp     dword ptr [rdi+4], 504F4F4Eh
0x18000e355  jnz     short loc_18000E2F4
0x18000e357  mov     eax, [rdi+8]
0x18000e35a  dec     eax
0x18000e35c  cmp     eax, 0FFFh
0x18000e361  jbe     short loc_18000E2FA
0x18000e363  jmp     short loc_18000E2F4
0x18000e365  cmp     esi, [r14+10h]
0x18000e369  jbe     loc_18000E2D3
0x18000e36f  mov     r8, [r14+40h]
0x18000e373  add     r8, rbx
0x18000e376  lea     rdx, [rbp+NumberOfBytesRead]
0x18000e37a  lea     rcx, [r14+40h]
0x18000e37e  call    ?erase@?$vector@USCachePage@@V?$wbem_allocator@USCachePage@@@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@USCachePage@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@USCachePage@@@std@@@std@@@2@@Z; std::vector<SCachePage,wbem_allocator<SCachePage>>::erase(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<SCachePage>>>)
0x18000e383  lea     rax, [rbp+var_18]
0x18000e387  mov     [rsp+58h+lpOverlapped], rax; struct SCachePage *
0x18000e38c  mov     r8, [r14+40h]; int
0x18000e390  lea     rdx, [rbp+NumberOfBytesRead]; int
0x18000e394  lea     rcx, [r14+40h]; int
0x18000e398  call    ?_Insert_n@?$vector@USCachePage@@V?$wbem_allocator@USCachePage@@@@@std@@IEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@USCachePage@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@USCachePage@@@std@@@std@@@2@_KAEBUSCachePage@@@Z; std::vector<SCachePage,wbem_allocator<SCachePage>>::_Insert_n(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<SCachePage>>>,unsigned __int64,SCachePage const &)
0x18000e39d  mov     rdi, [rbp+var_10]
0x18000e3a1  jmp     loc_18000E2D3
0x18000e3a6  mov     rdx, [r14+58h]
0x18000e3aa  mov     rcx, [r14+60h]
0x18000e3ae  sub     rcx, rdx
0x18000e3b1  sar     rcx, 4; unsigned int
0x18000e3b5  xor     ebx, ebx
0x18000e3b7  cmp     ebx, ecx
0x18000e3b9  jnb     short loc_18000E3D0
0x18000e3bb  mov     esi, ebx
0x18000e3bd  shl     rsi, 4
0x18000e3c1  mov     eax, [rsi+rdx]
0x18000e3c4  cmp     eax, edi
0x18000e3c6  jz      loc_18000E532
0x18000e3cc  inc     ebx
0x18000e3ce  jmp     short loc_18000E3B7
0x18000e3d0  mov     [rbp+var_28], edi
0x18000e3d3  mov     [rbp+var_24], r13d
0x18000e3d7  mov     [rbp+var_20], 0
0x18000e3df  inc     dword ptr [r14+2Ch]
0x18000e3e3  mov     rbx, [r14+38h]
0x18000e3e7  call    ?AllocatePage@MemoryPage@@SAPEAV1@K@Z; MemoryPage::AllocatePage(ulong)
0x18000e3ec  mov     rsi, rax
0x18000e3ef  test    rax, rax
0x18000e3f2  jz      loc_18000E72B
0x18000e3f8  mov     rdx, rdi
0x18000e3fb  shl     rdx, 0Dh; liDistanceToMove
0x18000e3ff  xor     r9d, r9d; dwMoveMethod
0x18000e402  xor     r8d, r8d; lpNewFilePointer
0x18000e405  mov     rcx, rbx; hFile
0x18000e408  call    cs:__imp_SetFilePointerEx
0x18000e40e  test    eax, eax
0x18000e410  jz      loc_18000E6A7
0x18000e416  mov     dword ptr [rbp+NumberOfBytesRead], 0
0x18000e41d  mov     [rsp+58h+lpOverlapped], 0; lpOverlapped
0x18000e426  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x18000e42a  mov     r8d, 2000h; nNumberOfBytesToRead
0x18000e430  mov     rdx, [rsi+10h]; lpBuffer
0x18000e434  mov     rcx, rbx; hFile
0x18000e437  call    cs:__imp_ReadFile
0x18000e43d  test    eax, eax
0x18000e43f  jz      loc_18000E867
0x18000e445  cmp     dword ptr [rbp+NumberOfBytesRead], 2000h
0x18000e44c  jnz     loc_18000E867
0x18000e452  mov     rbx, rsi
0x18000e455  mov     [rbp+var_20], rbx
0x18000e459  mov     rdx, [r14+70h]
0x18000e45d  xor     r9d, r9d
0x18000e460  mov     r8, [rdx+148h]
0x18000e467  mov     rax, [rdx+150h]
0x18000e46e  sub     rax, r8
0x18000e471  sar     rax, 3
0x18000e475  mov     r10, 0AAAAAAAAAAAAAAABh
0x18000e47f  imul    rax, r10
0x18000e483  cmp     r13d, eax
0x18000e486  jb      loc_18000E5CD
0x18000e48c  mov     r8, [rdx+0E0h]; unsigned int
0x18000e493  mov     rax, [rdx+0E8h]
0x18000e49a  sub     rax, r8
0x18000e49d  sar     rax, 3
0x18000e4a1  imul    rax, r10
0x18000e4a5  cmp     r13d, eax
0x18000e4a8  jnb     loc_18000E776
0x18000e4ae  lea     rcx, ds:0[r13*2]
0x18000e4b6  add     rcx, r13
0x18000e4b9  lea     rdx, [r8+rcx*8]; unsigned int
0x18000e4bd  mov     ecx, [rdx]
0x18000e4bf  bt      ecx, 1Eh
0x18000e4c3  jb      loc_18000E695
0x18000e4c9  mov     rsi, r9
0x18000e4cc  cmp     ecx, edi
0x18000e4ce  cmovz   rsi, rdx
0x18000e4d2  test    rsi, rsi
0x18000e4d5  jz      loc_18000E776
0x18000e4db  mov     rcx, [rbx+10h]; unsigned __int8 *
0x18000e4df  call    ?CreateCRC32@@YAKPEBEKK@Z; CreateCRC32(uchar const *,ulong,ulong)
0x18000e4e4  not     eax
0x18000e4e6  mov     [rbx+1Ch], eax
0x18000e4e9  cmp     eax, [rsi+4]
0x18000e4ec  jnz     loc_18000E639
0x18000e4f2  lea     rsi, [r14+40h]
0x18000e4f6  cmp     cs:?g_bPerformingVerify@@3_NA, 0; bool g_bPerformingVerify
0x18000e4fd  jz      loc_18000E585
0x18000e503  mov     rax, [rsi+8]
0x18000e507  lea     rcx, [rbp+var_28]
0x18000e50b  cmp     rcx, rax
0x18000e50e  jb      loc_18000E7B1
0x18000e514  cmp     rax, [rsi+10h]
0x18000e518  jz      loc_18000E7E2
0x18000e51e  lea     rdx, [rbp+var_28]; struct SCachePage *
0x18000e522  mov     rcx, [rsi+8]; this
0x18000e526  call    ??0SCachePage@@QEAA@AEBU0@@Z; SCachePage::SCachePage(SCachePage const &)
0x18000e52b  add     qword ptr [rsi+8], 10h
0x18000e530  jmp     short loc_18000E5A1
0x18000e532  mov     [rbp+var_18], eax
0x18000e535  mov     rdi, [rsi+rdx+8]
0x18000e53a  mov     [rbp+var_10], rdi
0x18000e53e  mov     eax, [rsi+rdx+4]
0x18000e542  mov     [rbp+var_14], eax
0x18000e545  test    rdi, rdi
0x18000e548  jz      short loc_18000E553
0x18000e54a  mov     rcx, rdi; this
0x18000e54d  call    ?AddRef@MemoryPage@@QEAAJXZ; MemoryPage::AddRef(void)
0x18000e552  nop
0x18000e553  cmp     cs:?g_bPerformingVerify@@3_NA, 0; bool g_bPerformingVerify
0x18000e55a  jz      loc_18000E5F8
0x18000e560  mov     [r15], rdi
0x18000e563  mov     rcx, rdi; this
0x18000e566  call    ?AddRef@MemoryPage@@QEAAJXZ; MemoryPage::AddRef(void)
0x18000e56b  inc     dword ptr [r14+28h]
0x18000e56f  test    rdi, rdi
0x18000e572  jz      loc_18000E30D
0x18000e578  mov     rcx, rdi; this
0x18000e57b  call    ?Release@MemoryPage@@QEAAJXZ; MemoryPage::Release(void)
0x18000e580  jmp     loc_18000E30D
0x18000e585  lea     rax, [rbp+var_28]
0x18000e589  mov     [rsp+58h+lpOverlapped], rax; struct SCachePage *
0x18000e58e  mov     r8, [rsi]; int
0x18000e591  lea     rdx, [rbp+NumberOfBytesRead]; int
0x18000e595  mov     rcx, rsi; int
0x18000e598  call    ?_Insert_n@?$vector@USCachePage@@V?$wbem_allocator@USCachePage@@@@@std@@IEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@USCachePage@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@USCachePage@@@std@@@std@@@2@_KAEBUSCachePage@@@Z; std::vector<SCachePage,wbem_allocator<SCachePage>>::_Insert_n(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<SCachePage>>>,unsigned __int64,SCachePage const &)
0x18000e59d  mov     rbx, [rbp+var_20]
0x18000e5a1  mov     rcx, r14; this
0x18000e5a4  call    ?Spill@CPageCache@@QEAAKXZ; CPageCache::Spill(void)
0x18000e5a9  mov     edi, eax
0x18000e5ab  test    eax, eax
0x18000e5ad  jnz     loc_18000E7EF
0x18000e5b3  mov     [r15], rbx
0x18000e5b6  mov     rcx, rbx; this
0x18000e5b9  call    ?AddRef@MemoryPage@@QEAAJXZ; MemoryPage::AddRef(void)
0x18000e5be  nop
0x18000e5bf  test    rbx, rbx
0x18000e5c2  jz      loc_18000E30D
0x18000e5c8  mov     rcx, rbx
0x18000e5cb  jmp     short loc_18000E57B
0x18000e5cd  lea     rcx, ds:0[r13*2]
0x18000e5d5  add     rcx, r13
0x18000e5d8  lea     rsi, [r8+rcx*8]
0x18000e5dc  mov     eax, [rsi]
0x18000e5de  test    eax, eax
0x18000e5e0  jns     loc_18000E48C
0x18000e5e6  and     eax, 3FFFFFFFh
0x18000e5eb  cmp     eax, edi
0x18000e5ed  jz      loc_18000E4DB
0x18000e5f3  jmp     loc_18000E48C
0x18000e5f8  cmp     ebx, [r14+14h]
0x18000e5fc  jbe     loc_18000E560
0x18000e602  mov     r8, [r14+58h]
0x18000e606  add     r8, rsi
0x18000e609  lea     rdx, [rbp+NumberOfBytesRead]
0x18000e60d  lea     rcx, [r14+58h]
0x18000e611  call    ?erase@?$vector@USCachePage@@V?$wbem_allocator@USCachePage@@@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@USCachePage@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@USCachePage@@@std@@@std@@@2@@Z; std::vector<SCachePage,wbem_allocator<SCachePage>>::erase(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<SCachePage>>>)
0x18000e616  lea     rax, [rbp+var_18]
0x18000e61a  mov     [rsp+58h+lpOverlapped], rax; struct SCachePage *
0x18000e61f  mov     r8, [r14+58h]; int
0x18000e623  lea     rdx, [rbp+NumberOfBytesRead]; int
0x18000e627  lea     rcx, [r14+58h]; int
0x18000e62b  call    ?_Insert_n@?$vector@USCachePage@@V?$wbem_allocator@USCachePage@@@@@std@@IEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@USCachePage@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@USCachePage@@@std@@@std@@@2@_KAEBUSCachePage@@@Z; std::vector<SCachePage,wbem_allocator<SCachePage>>::_Insert_n(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<SCachePage>>>,unsigned __int64,SCachePage const &)
0x18000e630  mov     rdi, [rbp+var_10]
0x18000e634  jmp     loc_18000E560
0x18000e639  xor     r8d, r8d; unsigned int
0x18000e63c  xor     edx, edx; bool
0x18000e63e  mov     ecx, 3; int
0x18000e643  call    ?SetRepositoryCorrupted@CRepositoryCorruption@@SAJJ_NK@Z; CRepositoryCorruption::SetRepositoryCorrupted(long,bool,ulong)
0x18000e648  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000e64e  mov     edx, 54Eh
0x18000e653  mov     rcx, rax
0x18000e656  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000e65c  lea     rbx, WPP_GLOBAL_Control
0x18000e663  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e66a  cmp     rcx, rbx
0x18000e66d  jnz     loc_18000E77D
0x18000e673  lea     rcx, [rbp+var_28]; this
0x18000e677  call    ??1SCachePage@@QEAA@XZ; SCachePage::~SCachePage(void)
0x18000e67c  mov     eax, 54Eh
0x18000e681  jmp     loc_18000E30F
0x18000e686  mov     rcx, rdi
0x18000e689  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18000e68f  nop
0x18000e690  jmp     loc_18000E30D
0x18000e695  mov     eax, ecx
0x18000e697  and     eax, 3FFFFFFFh
0x18000e69c  cmp     eax, edi
0x18000e69e  cmovz   r9, rdx
0x18000e6a2  jmp     loc_18000E4C9
0x18000e6a7  xor     ebx, ebx
0x18000e6a9  mov     rcx, rsi; this
0x18000e6ac  call    ?Release@MemoryPage@@QEAAJXZ; MemoryPage::Release(void)
0x18000e6b1  call    cs:__imp_GetLastError
0x18000e6b7  mov     esi, eax
0x18000e6b9  test    eax, eax
0x18000e6bb  jz      loc_18000E455
0x18000e6c1  lea     rbx, WPP_GLOBAL_Control
0x18000e6c8  jmp     loc_18000E8C2
0x18000e6cd  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000e6d3  mov     esi, 57h ; 'W'
0x18000e6d8  mov     edx, esi
  ... truncated ...
```
