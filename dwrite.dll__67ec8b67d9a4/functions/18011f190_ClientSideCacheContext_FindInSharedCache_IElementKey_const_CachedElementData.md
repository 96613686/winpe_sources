# ClientSideCacheContext::FindInSharedCache(IElementKey const &,CachedElementData *)

- ea: `0x18011f190`
- end: `0x18011f65d`
- name: `?FindInSharedCache@ClientSideCacheContext@@AEAA_NAEBVIElementKey@@PEAUCachedElementData@@@Z`
- size: `1229`
- prototype: `bool(ClientSideCacheContext *__hidden this, const struct IElementKey *, struct CachedElementData *)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18011f0d0`

## callees

- `0x18011f190`
- `0x18011f670`
- `0x18011f978`
- `0x180154068`
- `0x180167278`
- `0x1801bdd90`
- `0x1801bddd0`
- `0x1801bde10`
- `0x1801bde80`
- `0x1801db7c4`
- `0x1801fa7e4`
- `0x180201f50`
- `0x18020c524`
- `0x1802473b0`
- `0x180249618`
- `0x180330010`

## import_xrefs

- `ntdll!NtSetInformationThread` at `0x18011f5cb`
- `ntdll!NtSetInformationThread` at `0x18011f5cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18011f5af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18011f5af`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18011f215`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18011f215`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18011f2ae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18011f608`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18011f2ae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18011f608`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18011f4b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18011f4b3`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
bool __fastcall ClientSideCacheContext::FindInSharedCache(
        ClientSideCacheContext *this,
        const struct IElementKey *a2,
        DWORD *a3)
{
  bool ElementCommon; // r14
  int v7; // ecx
  unsigned int v8; // r12d
  struct _RTL_CRITICAL_SECTION *v9; // rsi
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rcx
  PRTL_CRITICAL_SECTION_DEBUG v12; // r13
  __int64 v13; // rdx
  __int64 v14; // rax
  __int64 v15; // rbx
  __int64 v16; // rcx
  __int64 v17; // rax
  unsigned __int64 Flags; // rdx
  struct _LIST_ENTRY *Flink; // r8
  unsigned __int64 v20; // rcx
  DWORD v21; // ebx
  __int128 v22; // xmm6
  int v23; // eax
  PRTL_CRITICAL_SECTION_DEBUG v24; // rbx
  DWORD v25; // esi
  DWORD *p_ContentionCount; // r15
  __int64 v27; // rax
  struct _FILETIME v28; // r12
  HANDLE CurrentThread; // rax
  __int64 v30; // rbx
  unsigned __int64 v31; // [rsp+48h] [rbp-90h] BYREF
  __int64 v32; // [rsp+50h] [rbp-88h]
  int v33; // [rsp+58h] [rbp-80h]
  unsigned int v34; // [rsp+5Ch] [rbp-7Ch]
  LPCRITICAL_SECTION lpCriticalSection[2]; // [rsp+60h] [rbp-78h] BYREF
  struct _LIST_ENTRY *v36; // [rsp+70h] [rbp-68h] BYREF
  int v37; // [rsp+78h] [rbp-60h]
  int v38; // [rsp+7Ch] [rbp-5Ch]
  __int128 v39; // [rsp+80h] [rbp-58h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+F8h] [rbp+20h] BYREF

  if ( (*(unsigned __int8 (__fastcall **)(const struct IElementKey *))(*(_QWORD *)a2 + 16LL))(a2) )
    return 0;
  ElementCommon = 0;
  v7 = *((_DWORD *)a2 + 3);
  if ( (unsigned int)(v7 - 2) <= 1 || v7 == 9 )
  {
    v8 = 2;
    v9 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 416);
  }
  else
  {
    v8 = 3;
    v9 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 424);
  }
  lpCriticalSection[1] = v9;
  lpCriticalSection[0] = (LPCRITICAL_SECTION)((char *)this + 376);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 376));
  if ( !v9->DebugInfo )
    goto LABEL_38;
  (*(void (__fastcall **)(PRTL_CRITICAL_SECTION_DEBUG, unsigned __int64 *))(*(_QWORD *)v9->DebugInfo + 8LL))(
    v9->DebugInfo,
    &v31);
  if ( (unsigned int)v32 < 0x3C || (v31 & 3) != 0 )
    FailAsExceptionPolicy<InvalidCacheDataException>::OnOutOfRange(v31);
  if ( (*(_BYTE *)(v31 + 4) & 1) != 0 )
LABEL_38:
    (*(void (__fastcall **)(ClientSideCacheContext *, _QWORD, struct _RTL_CRITICAL_SECTION *))(*(_QWORD *)this + 128LL))(
      this,
      v8,
      v9);
  DebugInfo = v9->DebugInfo;
  if ( !v9->DebugInfo )
    goto LABEL_13;
  if ( LOBYTE(DebugInfo[1].Flags) )
    goto LABEL_13;
  ElementCommon = FindElementCommon(
                    (struct ICacheReference *)DebugInfo,
                    0,
                    *(const struct CacheHeader **)&DebugInfo[1].Type,
                    (const unsigned int *)DebugInfo[1].CriticalSection,
                    (const struct HashElement *)DebugInfo[1].ProcessLocksList.Flink,
                    DebugInfo->ProcessLocksList.Flink,
                    a2,
                    (struct CachedElementData *)a3);
  if ( !ElementCommon || !a3 )
    goto LABEL_13;
  v12 = v9->DebugInfo;
  v13 = *(_QWORD *)&v9->DebugInfo[1].EntryCount;
  if ( !v13 || (v14 = a3[1] - 1, v34 = v14, v15 = *(_QWORD *)&v12[1].Type, (unsigned int)v14 >= *(_DWORD *)(v15 + 24)) )
  {
    v30 = *(_QWORD *)&v12[1].Type;
    Exception::Exception((Exception *)&v31, -2003283961, 0);
    v32 = v30;
    LogAndThrow<InvalidCacheDataException>(&v31, 0x64726568636163LL, 89);
  }
  v16 = (unsigned int)v14;
  if ( *(_BYTE *)(v13 + v14) )
    goto LABEL_28;
  if ( *((_BYTE *)&v12[1].ProcessLocksList.Blink->Flink + (unsigned int)v14) )
  {
    *(_BYTE *)(v13 + v14) = 1;
LABEL_28:
    v24 = v9->DebugInfo;
    v25 = a3[1];
    if ( v25 == v24[12].Flags || !*(_DWORD *)(*(_QWORD *)&v24[1].Type + 36LL) )
      goto LABEL_13;
    p_ContentionCount = &v24[12].ContentionCount;
    *(_DWORD *)(&v24[2].CreatorBackTraceIndex + 2 * v24[12].ContentionCount + 1) = v25;
    LODWORD(v27) = v24[12].ContentionCount + 1;
    if ( (unsigned int)v27 < 0x80 )
      goto LABEL_31;
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v28 = SystemTimeAsFileTime;
    if ( *(_QWORD *)&SystemTimeAsFileTime - *(_QWORD *)&v24[13].Type >= 0x989680u )
    {
      (*(void (__fastcall **)(ClientSideCacheContext *, LPCRITICAL_SECTION *, _QWORD, _QWORD, WORD *))(*(_QWORD *)this + 120LL))(
        this,
        lpCriticalSection,
        *(unsigned int *)&v24[1].CreatorBackTraceIndexHigh,
        *(unsigned int *)(*(_QWORD *)&v24[1].Type + 32LL),
        &v24[2].CreatorBackTraceIndex + 1);
      *(struct _FILETIME *)&v24[13].Type = v28;
      *p_ContentionCount = 0;
      v24[12].Flags = 0;
      goto LABEL_13;
    }
    std::_Sort_unchecked<unsigned int *,std::less<void>>(
      &v24[2].CreatorBackTraceIndex + 1,
      &v24[12].ContentionCount,
      128,
      0);
    v27 = (std::unique<unsigned int *,std::equal_to<void>>(&v24[2].CreatorBackTraceIndex + 1, &v24[12].ContentionCount)
         - (__int64)(&v24[2].CreatorBackTraceIndex + 1)) >> 2;
    if ( (unsigned int)v27 <= 0x40 || (LODWORD(v27) = 64, LODWORD(v24[7].ProcessLocksList.Flink) >= v25) )
    {
LABEL_31:
      *p_ContentionCount = v27;
      v24[12].Flags = v25;
    }
    else
    {
      LODWORD(v24[7].ProcessLocksList.Flink) = v25;
      *p_ContentionCount = 64;
      v24[12].Flags = v25;
    }
LABEL_13:
    LeaveCriticalSection(lpCriticalSection[0]);
    return ElementCommon;
  }
  v17 = *(unsigned int *)(v15 + 56);
  if ( !(_DWORD)v17 )
  {
    LODWORD(v31) = -2003283961;
    CaptureStack(-2003283961, 0);
    v32 = v15;
    LogAndThrow<InvalidCacheDataException>(&v31, 0x64726568636163LL, 113);
  }
  Flags = v12->Flags;
  v31 = Flags;
  Flink = v12->ProcessLocksList.Flink;
  v36 = Flink;
  v20 = v17 + 4 * v16;
  if ( v20 > Flags || (unsigned int)Flags - v20 < 4 || (((_BYTE)v20 + (_BYTE)Flink) & 3) != 0 )
    FailAsExceptionPolicy<InvalidCacheDataException>::OnOutOfRange(Flink);
  v21 = a3[2];
  v22 = *((_OWORD *)a3 + 1);
  v33 = *(_DWORD *)((char *)&Flink->Flink + v20);
  LowMemoryPriority::LowMemoryPriority((LowMemoryPriority *)&SystemTimeAsFileTime);
  v39 = v22;
  v37 = v31;
  v38 = HIDWORD(v22);
  v23 = ((__int64 (__fastcall *)(struct _LIST_ENTRY **, __int128 *))g_elementCheckSumProcedures[v21 - 1])(&v36, &v39);
  if ( v33 == v23 )
  {
    *(_BYTE *)(v34 + *(_QWORD *)&v12[1].EntryCount) = 1;
    if ( SystemTimeAsFileTime.dwLowDateTime )
    {
      CurrentThread = GetCurrentThread();
      NtSetInformationThread(CurrentThread, ThreadPagePriority, &SystemTimeAsFileTime, 4u);
    }
    (*(void (__fastcall **)(ClientSideCacheContext *, _QWORD, PRTL_CRITICAL_SECTION_DEBUG, _QWORD))(*(_QWORD *)this
                                                                                                  + 144LL))(
      this,
      v8,
      v9->DebugInfo,
      a3[1]);
    goto LABEL_28;
  }
  LowMemoryPriority::~LowMemoryPriority((LowMemoryPriority *)&SystemTimeAsFileTime);
  LOBYTE(v9->DebugInfo[1].Flags) = 1;
  (*(void (__fastcall **)(ClientSideCacheContext *, _QWORD, PRTL_CRITICAL_SECTION_DEBUG))(*(_QWORD *)this + 136LL))(
    this,
    v8,
    v9->DebugInfo);
  LeaveCriticalSection(lpCriticalSection[0]);
  return 0;
}

```

## disassembly

```asm
0x18011f190  mov     [rsp+arg_0], rcx
0x18011f195  push    rbx
0x18011f196  push    rsi
0x18011f197  push    rdi
0x18011f198  push    r12
0x18011f19a  push    r13
0x18011f19c  push    r14
0x18011f19e  push    r15
0x18011f1a0  sub     rsp, 0A0h
0x18011f1a7  movaps  [rsp+0D8h+var_48], xmm6
0x18011f1af  mov     r15, r8
0x18011f1b2  mov     rbx, rdx
0x18011f1b5  mov     rdi, rcx
0x18011f1b8  mov     rax, [rdx]
0x18011f1bb  mov     rcx, rdx
0x18011f1be  mov     rax, [rax+10h]
0x18011f1c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011f1c7  test    al, al
0x18011f1c9  jnz     loc_18011F2E5
0x18011f1cf  xor     r14b, r14b
0x18011f1d2  mov     [rsp+0D8h+arg_8], r14b
0x18011f1da  mov     ecx, [rbx+0Ch]
0x18011f1dd  lea     eax, [rcx-2]
0x18011f1e0  cmp     eax, 1
0x18011f1e3  jbe     loc_18011F2D3
0x18011f1e9  cmp     ecx, 9
0x18011f1ec  jz      loc_18011F2D3
0x18011f1f2  mov     r12d, 3
0x18011f1f8  lea     rsi, [rdi+1A8h]
0x18011f1ff  mov     [rsp+0D8h+var_70], rsi
0x18011f204  mov     [rsp+0D8h+var_98], r12d
0x18011f209  lea     rcx, [rdi+178h]; lpCriticalSection
0x18011f210  mov     [rsp+0D8h+lpCriticalSection], rcx
0x18011f215  call    cs:__imp_EnterCriticalSection
0x18011f21b  nop
0x18011f21c  mov     rcx, [rsi]
0x18011f21f  test    rcx, rcx
0x18011f222  jz      loc_18011F53B
0x18011f228  mov     rax, [rcx]
0x18011f22b  lea     rdx, [rsp+0D8h+var_90]
0x18011f230  mov     rax, [rax+8]
0x18011f234  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011f239  mov     rcx, [rsp+0D8h+var_90]
0x18011f23e  cmp     dword ptr [rsp+0D8h+var_88], 3Ch ; '<'
0x18011f243  jb      loc_18011F59A
0x18011f249  test    cl, 3
0x18011f24c  jnz     loc_18011F59A
0x18011f252  test    byte ptr [rcx+4], 1
0x18011f256  jnz     loc_18011F53B
0x18011f25c  mov     rcx, [rsi]; struct ICacheReference *
0x18011f25f  test    rcx, rcx
0x18011f262  jz      short loc_18011F2A9
0x18011f264  cmp     byte ptr [rcx+58h], 0
0x18011f268  jnz     short loc_18011F2A9
0x18011f26a  mov     [rsp+0D8h+var_A0], r15; struct CachedElementData *
0x18011f26f  mov     [rsp+0D8h+var_A8], rbx; struct IElementKey *
0x18011f274  mov     rax, [rcx+10h]
0x18011f278  mov     [rsp+0D8h+var_B0], rax; void *
0x18011f27d  mov     rax, [rcx+40h]
0x18011f281  mov     [rsp+0D8h+var_B8], rax; struct HashElement *
0x18011f286  mov     r9, [rcx+38h]; unsigned int *
0x18011f28a  mov     r8, [rcx+30h]; struct CacheHeader *
0x18011f28e  xor     edx, edx; bool
0x18011f290  call    ?FindElementCommon@@YA_NPEAVICacheReference@@_NAEBUCacheHeader@@PEBIPEBUHashElement@@PEBXAEBVIElementKey@@PEAUCachedElementData@@@Z; FindElementCommon(ICacheReference *,bool,CacheHeader const &,uint const *,HashElement const *,void const *,IElementKey const &,CachedElementData *)
0x18011f295  movzx   r14d, al
0x18011f299  mov     [rsp+0D8h+arg_8], al
0x18011f2a0  test    al, al
0x18011f2a2  jz      short loc_18011F2A9
0x18011f2a4  test    r15, r15
0x18011f2a7  jnz     short loc_18011F2E9
0x18011f2a9  mov     rcx, [rsp+0D8h+lpCriticalSection]; lpCriticalSection
0x18011f2ae  call    cs:__imp_LeaveCriticalSection
0x18011f2b4  movzx   eax, r14b
0x18011f2b8  movaps  xmm6, [rsp+0D8h+var_48]
0x18011f2c0  add     rsp, 0A0h
0x18011f2c7  pop     r15
0x18011f2c9  pop     r14
0x18011f2cb  pop     r13
0x18011f2cd  pop     r12
0x18011f2cf  pop     rdi
0x18011f2d0  pop     rsi
0x18011f2d1  pop     rbx
0x18011f2d2  retn
0x18011f2d3  mov     r12d, 2
0x18011f2d9  lea     rsi, [rdi+1A0h]
0x18011f2e0  jmp     loc_18011F1FF
0x18011f2e5  xor     al, al
0x18011f2e7  jmp     short loc_18011F2B8
0x18011f2e9  mov     r13, [rsi]
0x18011f2ec  mov     rdx, [r13+50h]
0x18011f2f0  test    rdx, rdx
0x18011f2f3  jz      loc_18011F615
0x18011f2f9  mov     eax, [r15+4]
0x18011f2fd  dec     eax
0x18011f2ff  mov     [rsp+0D8h+var_7C], eax
0x18011f303  mov     rbx, [r13+30h]
0x18011f307  cmp     eax, [rbx+18h]
0x18011f30a  jnb     loc_18011F615
0x18011f310  mov     ecx, eax
0x18011f312  lea     r8, [rdx+rax]
0x18011f316  cmp     byte ptr [r8], 0
0x18011f31a  jnz     loc_18011F418
0x18011f320  mov     rax, [r13+48h]
0x18011f324  cmp     byte ptr [rcx+rax], 0
0x18011f328  jnz     loc_18011F59F
0x18011f32e  mov     eax, [rbx+38h]
0x18011f331  test    eax, eax
0x18011f333  jz      loc_18011F461
0x18011f339  mov     edx, [r13+28h]
0x18011f33d  mov     [rsp+0D8h+var_90], rdx
0x18011f342  mov     r8, [r13+10h]
0x18011f346  mov     [rsp+0D8h+var_68], r8
0x18011f34b  lea     rcx, [rax+rcx*4]
0x18011f34f  cmp     rcx, rdx
0x18011f352  ja      loc_18011F497
0x18011f358  mov     eax, edx
0x18011f35a  sub     rax, rcx
0x18011f35d  cmp     rax, 4
0x18011f361  jb      loc_18011F497
0x18011f367  lea     rax, [rcx+r8]
0x18011f36b  test    al, 3
0x18011f36d  jnz     loc_18011F497
0x18011f373  mov     ebx, [r15+8]
0x18011f377  movups  xmm6, xmmword ptr [r15+10h]
0x18011f37c  mov     eax, [rax]
0x18011f37e  mov     [rsp+0D8h+var_80], eax
0x18011f382  lea     rcx, [rsp+0D8h+SystemTimeAsFileTime]; this
0x18011f38a  call    ??0LowMemoryPriority@@QEAA@XZ; LowMemoryPriority::LowMemoryPriority(void)
0x18011f38f  nop
0x18011f390  movdqa  [rsp+0D8h+var_58], xmm6
0x18011f399  mov     rax, [rsp+0D8h+var_68]
0x18011f39e  mov     [rsp+0D8h+var_68], rax
0x18011f3a3  mov     rax, [rsp+0D8h+var_90]
0x18011f3a8  mov     [rsp+0D8h+var_60], eax
0x18011f3ac  mov     eax, dword ptr [rsp+0D8h+var_58+0Ch]
0x18011f3b3  mov     [rsp+0D8h+var_5C], eax
0x18011f3b7  lea     ecx, [rbx-1]
0x18011f3ba  lea     rax, ?g_elementCheckSumProcedures@@3QBQ6AIV?$CheckedPtr@$$CBEV?$FailAsExceptionPolicy@VInvalidCacheDataException@@@@I@@0@ZB; uint (*const near * const g_elementCheckSumProcedures)(CheckedPtr<uchar const,FailAsExceptionPolicy<InvalidCacheDataException>,uint>,CheckedPtr<uchar const,FailAsExceptionPolicy<InvalidCacheDataException>,uint>)
0x18011f3c1  mov     rax, ds:(?g_elementCheckSumProcedures@@3QBQ6AIV?$CheckedPtr@$$CBEV?$FailAsExceptionPolicy@VInvalidCacheDataException@@@@I@@0@ZB - 180331050h)[rax+rcx*8]; uint (*const near * const g_elementCheckSumProcedures)(CheckedPtr<uchar const,FailAsExceptionPolicy<InvalidCacheDataException>,uint>,CheckedPtr<uchar const,FailAsExceptionPolicy<InvalidCacheDataException>,uint>)
0x18011f3c5  lea     rdx, [rsp+0D8h+var_58]
0x18011f3cd  lea     rcx, [rsp+0D8h+var_68]
0x18011f3d2  call    _guard_dispatch_icall$thunk$10345483385596137414; GlyphDataElement<GlyphMetricsLayout,GlyphMetricsRasterizationParameters,GlyphMetricsRasterizationState>::ComputeCheckSum(CheckedPtr<uchar const,FailAsExceptionPolicy<InvalidCacheDataException>,uint>,CheckedPtr<uchar const,FailAsExceptionPolicy<InvalidCacheDataException>,uint>)
0x18011f3d7  cmp     [rsp+0D8h+var_80], eax
0x18011f3db  jnz     loc_18011F5D6
0x18011f3e1  mov     rax, [r13+50h]
0x18011f3e5  mov     edx, [rsp+0D8h+var_7C]
0x18011f3e9  mov     byte ptr [rdx+rax], 1
0x18011f3ed  mov     eax, [rsp+0D8h+SystemTimeAsFileTime.dwLowDateTime]
0x18011f3f4  test    eax, eax
0x18011f3f6  jnz     loc_18011F5A8
0x18011f3fc  mov     rax, [rdi]
0x18011f3ff  mov     r9d, [r15+4]
0x18011f403  mov     r8, [rsi]
0x18011f406  mov     edx, r12d
0x18011f409  mov     rcx, rdi
0x18011f40c  mov     rax, [rax+90h]
0x18011f413  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011f418  mov     rbx, [rsi]
0x18011f41b  mov     esi, [r15+4]
0x18011f41f  cmp     esi, [rbx+268h]
0x18011f425  jz      loc_18011F2A9
0x18011f42b  mov     rax, [rbx+30h]
0x18011f42f  cmp     dword ptr [rax+24h], 0
0x18011f433  jz      loc_18011F2A9
0x18011f439  lea     r15, [rbx+264h]
0x18011f440  mov     eax, [r15]
0x18011f443  mov     [rbx+rax*4+64h], esi
0x18011f447  mov     eax, [r15]
0x18011f44a  inc     eax
0x18011f44c  cmp     eax, 80h
0x18011f451  jnb     short loc_18011F49F
0x18011f453  mov     [r15], eax
0x18011f456  mov     [rbx+268h], esi
0x18011f45c  jmp     loc_18011F2A9
0x18011f461  mov     rdi, 64726568636163h
0x18011f46b  mov     dword ptr [rsp+0D8h+var_90], 88985007h
0x18011f473  xor     edx, edx; unsigned int
0x18011f475  mov     ecx, 88985007h; int
0x18011f47a  call    ?CaptureStack@@YAXJI@Z; CaptureStack(long,uint)
0x18011f47f  mov     [rsp+0D8h+var_88], rbx
0x18011f484  mov     r8d, 71h ; 'q'
0x18011f48a  mov     rdx, rdi
0x18011f48d  lea     rcx, [rsp+0D8h+var_90]
0x18011f492  call    ??$LogAndThrow@VInvalidCacheDataException@@@@YAXAEBVInvalidCacheDataException@@VEventTag@@I@Z; LogAndThrow<InvalidCacheDataException>(InvalidCacheDataException const &,EventTag,uint)
0x18011f497  mov     rcx, r8
0x18011f49a  call    ?OnOutOfRange@?$FailAsExceptionPolicy@VInvalidCacheDataException@@@@SAXPEBX@Z; FailAsExceptionPolicy<InvalidCacheDataException>::OnOutOfRange(void const *)
0x18011f49f  mov     qword ptr [rsp+0D8h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18011f4ab  lea     rcx, [rsp+0D8h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18011f4b3  call    cs:__imp_GetSystemTimeAsFileTime
0x18011f4b9  mov     r12d, [rsp+0D8h+SystemTimeAsFileTime.dwHighDateTime]
0x18011f4c1  shl     r12, 20h
0x18011f4c5  mov     eax, [rsp+0D8h+SystemTimeAsFileTime.dwLowDateTime]
0x18011f4cc  or      r12, rax
0x18011f4cf  lea     r13, [rbx+64h]
0x18011f4d3  mov     rax, r12
0x18011f4d6  sub     rax, [rbx+270h]
0x18011f4dd  cmp     rax, 989680h
0x18011f4e3  jnb     short loc_18011F558
0x18011f4e5  xor     r9d, r9d
0x18011f4e8  mov     r8d, 80h
0x18011f4ee  mov     rdx, r15
0x18011f4f1  mov     rcx, r13
0x18011f4f4  call    ??$_Sort_unchecked@PEAIU?$less@X@std@@@std@@YAXPEAI0_JU?$less@X@0@@Z; std::_Sort_unchecked<uint *,std::less<void>>(uint *,uint *,__int64,std::less<void>)
0x18011f4f9  mov     rdx, r15
0x18011f4fc  mov     rcx, r13
0x18011f4ff  call    ??$unique@PEAIU?$equal_to@X@std@@@std@@YAPEAIPEAI0U?$equal_to@X@0@@Z; std::unique<uint *,std::equal_to<void>>(uint *,uint *,std::equal_to<void>)
0x18011f504  sub     rax, r13
0x18011f507  sar     rax, 2
0x18011f50b  cmp     eax, 40h ; '@'
0x18011f50e  jbe     loc_18011F453
0x18011f514  mov     eax, 40h ; '@'
0x18011f519  cmp     [r13+0FCh], esi
0x18011f520  jnb     loc_18011F453
0x18011f526  mov     [r13+0FCh], esi
0x18011f52d  mov     [r15], eax
0x18011f530  mov     [rbx+268h], esi
0x18011f536  jmp     loc_18011F2A9
0x18011f53b  mov     rax, [rdi]
0x18011f53e  mov     r8, rsi
0x18011f541  mov     edx, r12d
0x18011f544  mov     rcx, rdi
0x18011f547  mov     rax, [rax+80h]
0x18011f54e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011f553  jmp     loc_18011F25C
0x18011f558  mov     rax, [rdi]
0x18011f55b  mov     r9, [rbx+30h]
0x18011f55f  mov     [rsp+0D8h+var_B8], r13
0x18011f564  mov     r9d, [r9+20h]
0x18011f568  mov     r8d, [rbx+5Ch]
0x18011f56c  lea     rdx, [rsp+0D8h+lpCriticalSection]
0x18011f571  mov     rcx, rdi
0x18011f574  mov     rax, [rax+78h]
0x18011f578  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011f57d  mov     [rbx+270h], r12
0x18011f584  mov     dword ptr [r15], 0
0x18011f58b  mov     dword ptr [rbx+268h], 0
0x18011f595  jmp     loc_18011F2A9
0x18011f59a  call    ?OnOutOfRange@?$FailAsExceptionPolicy@VInvalidCacheDataException@@@@SAXPEBX@Z; FailAsExceptionPolicy<InvalidCacheDataException>::OnOutOfRange(void const *)
0x18011f59f  mov     byte ptr [r8], 1
0x18011f5a3  jmp     loc_18011F418
0x18011f5a8  mov     [rsp+0D8h+SystemTimeAsFileTime.dwLowDateTime], eax
0x18011f5af  call    cs:__imp_GetCurrentThread
0x18011f5b5  mov     rcx, rax; ThreadHandle
0x18011f5b8  mov     r9d, 4; ThreadInformationLength
0x18011f5be  lea     r8, [rsp+0D8h+SystemTimeAsFileTime]; ThreadInformation
0x18011f5c6  mov     edx, 18h; ThreadInformationClass
0x18011f5cb  call    cs:__imp_NtSetInformationThread
0x18011f5d1  jmp     loc_18011F3FC
0x18011f5d6  lea     rcx, [rsp+0D8h+SystemTimeAsFileTime]; this
0x18011f5de  call    ??1LowMemoryPriority@@QEAA@XZ; LowMemoryPriority::~LowMemoryPriority(void)
0x18011f5e3  mov     rax, [rsi]
0x18011f5e6  mov     byte ptr [rax+58h], 1
0x18011f5ea  mov     rax, [rdi]
0x18011f5ed  mov     r8, [rsi]
0x18011f5f0  mov     edx, r12d
0x18011f5f3  mov     rcx, rdi
0x18011f5f6  mov     rax, [rax+88h]
0x18011f5fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011f602  nop
0x18011f603  mov     rcx, [rsp+0D8h+lpCriticalSection]; lpCriticalSection
0x18011f608  call    cs:__imp_LeaveCriticalSection
0x18011f60e  xor     al, al
0x18011f610  jmp     loc_18011F2B8
0x18011f615  mov     rdi, 64726568636163h
0x18011f61f  mov     rbx, [r13+30h]
0x18011f623  xor     r8d, r8d; unsigned int
0x18011f626  mov     edx, 88985007h; int
0x18011f62b  lea     rcx, [rsp+0D8h+var_90]; this
0x18011f630  call    ??0Exception@@IEAA@HI@Z; Exception::Exception(int,uint)
0x18011f635  mov     [rsp+0D8h+var_88], rbx
0x18011f63a  mov     r8d, 59h ; 'Y'
0x18011f640  mov     rdx, rdi
0x18011f643  lea     rcx, [rsp+0D8h+var_90]
0x18011f648  call    ??$LogAndThrow@VInvalidCacheDataException@@@@YAXAEBVInvalidCacheDataException@@VEventTag@@I@Z; LogAndThrow<InvalidCacheDataException>(InvalidCacheDataException const &,EventTag,uint)
0x18011f64e  movzx   r14d, [rsp+0D8h+arg_8]
0x18011f657  jmp     loc_18011F2A9
```
