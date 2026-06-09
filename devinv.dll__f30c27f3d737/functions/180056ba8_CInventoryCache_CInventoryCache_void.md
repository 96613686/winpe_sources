# CInventoryCache::~CInventoryCache(void)

- ea: `0x180056ba8`
- end: `0x180056d01`
- name: `??1CInventoryCache@@QEAA@XZ`
- size: `345`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180047f60`
- `0x180057608`

## callees

- `0x180006210`
- `0x180006d02`
- `0x180007014`
- `0x180016598`
- `0x180016660`
- `0x1800173a0`
- `0x180056ba8`
- `0x18006041c`
- `0x180066c10`

## import_xrefs

- `WINTRUST!CryptCATAdminReleaseContext` at `0x180056c59`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x180056c59`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180056ca4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180056ca4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180056bb6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180056bb6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180056cad`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180056cad`

## string_xrefs

- `0x180056bd9`: `CInventoryCache::~CInventoryCache`
- `0x180056c01`: `CInventoryCache::~CInventoryCache`

## pseudocode

```c
void __fastcall CInventoryCache::~CInventoryCache(LPCRITICAL_SECTION lpCriticalSection)
{
  FILE *v2; // rax
  FILE *v3; // rax
  FILE *v4; // rax
  __int64 ***LockSemaphore; // rdi
  __int64 **i; // rbx
  __int64 *v7; // r14
  _QWORD **v8; // rcx
  _QWORD *v9; // rcx
  _QWORD *v10; // rbx

  EnterCriticalSection(lpCriticalSection);
  if ( lpCriticalSection[1].DebugInfo )
  {
    AslLogCallPrintf(3, "CInventoryCache::~CInventoryCache", 46, "Releasing cat admin context");
    if ( EnableDevInvStdErrLog )
    {
      v2 = o___acrt_iob_func_0(2u);
      fprintf(v2, "Info: %s, %u: ", "CInventoryCache::~CInventoryCache", 46);
      v3 = o___acrt_iob_func_0(2u);
      fprintf(v3, "Releasing cat admin context");
      v4 = o___acrt_iob_func_0(2u);
      fprintf(v4, "\n");
    }
    if ( g_DeviceMapLogFunction )
      TraceMessageCallback(0x4000000, "Releasing cat admin context");
    CryptCATAdminReleaseContext(lpCriticalSection[1].DebugInfo, 0);
  }
  if ( lpCriticalSection[1].SpinCount )
  {
    LockSemaphore = (__int64 ***)lpCriticalSection[1].LockSemaphore;
    for ( i = *LockSemaphore; i != (__int64 **)LockSemaphore; i = (__int64 **)*i )
    {
      v7 = i[3];
      if ( v7 )
      {
        CCachedFolder::~CCachedFolder((CCachedFolder *)i[3]);
        operator delete(v7);
      }
    }
    std::_Hash<stdext::_Hmap_traits<int,CCachedFolder *,stdext::hash_compare<int,std::less<int>>,std::allocator<std::pair<int const,CCachedFolder *>>,1>>::clear(&lpCriticalSection[1].OwningThread);
  }
  LeaveCriticalSection(lpCriticalSection);
  DeleteCriticalSection(lpCriticalSection);
  std::vector<CDriverPackageDetailed *>::~vector<CDriverPackageDetailed *>(&lpCriticalSection[2]);
  v8 = (_QWORD **)lpCriticalSection[1].LockSemaphore;
  *v8[1] = 0;
  v9 = *v8;
  if ( v9 )
  {
    do
    {
      v10 = (_QWORD *)*v9;
      operator delete(v9);
      v9 = v10;
    }
    while ( v10 );
  }
  operator delete(lpCriticalSection[1].LockSemaphore);
}

```

## disassembly

```asm
0x180056ba8  push    rbx
0x180056baa  push    rbp
0x180056bab  push    rsi
0x180056bac  push    rdi
0x180056bad  push    r14
0x180056baf  sub     rsp, 20h
0x180056bb3  mov     rsi, rcx
0x180056bb6  call    cs:__imp_EnterCriticalSection
0x180056bbc  cmp     qword ptr [rsi+28h], 0
0x180056bc1  jz      loc_180056C5F
0x180056bc7  lea     rdi, aReleasingCatAd; "Releasing cat admin context"
0x180056bce  mov     r9, rdi
0x180056bd1  mov     ebp, 2Eh ; '.'
0x180056bd6  mov     r8d, ebp
0x180056bd9  lea     rdx, aCinventorycach; "CInventoryCache::~CInventoryCache"
0x180056be0  lea     ecx, [rbp-2Bh]
0x180056be3  call    AslLogCallPrintf
0x180056be8  cmp     cs:EnableDevInvStdErrLog, 0
0x180056bef  jz      short loc_180056C3C
0x180056bf1  lea     ebx, [rbp-2Ch]
0x180056bf4  mov     ecx, ebx; Ix
0x180056bf6  call    _o___acrt_iob_func_0
0x180056bfb  mov     rcx, rax; Stream
0x180056bfe  mov     r9d, ebp
0x180056c01  lea     r8, aCinventorycach; "CInventoryCache::~CInventoryCache"
0x180056c08  lea     rdx, aInfoSU; "Info: %s, %u: "
0x180056c0f  call    fprintf
0x180056c14  mov     ecx, ebx; Ix
0x180056c16  call    _o___acrt_iob_func_0
0x180056c1b  mov     rcx, rax; Stream
0x180056c1e  mov     rdx, rdi; Format
0x180056c21  call    fprintf
0x180056c26  mov     ecx, ebx; Ix
0x180056c28  call    _o___acrt_iob_func_0
0x180056c2d  mov     rcx, rax; Stream
0x180056c30  lea     rdx, asc_18011EAD8; "\n"
0x180056c37  call    fprintf
0x180056c3c  cmp     cs:g_DeviceMapLogFunction, 0
0x180056c44  jz      short loc_180056C53
0x180056c46  mov     rdx, rdi
0x180056c49  mov     ecx, 4000000h
0x180056c4e  call    TraceMessageCallback
0x180056c53  xor     edx, edx; dwFlags
0x180056c55  mov     rcx, [rsi+28h]; hCatAdmin
0x180056c59  call    cs:__imp_CryptCATAdminReleaseContext
0x180056c5f  lea     rbp, [rsi+38h]
0x180056c63  cmp     qword ptr [rsi+48h], 0
0x180056c68  jz      short loc_180056CA1
0x180056c6a  mov     rdi, [rbp+8]
0x180056c6e  mov     rbx, [rdi]
0x180056c71  cmp     rbx, rdi
0x180056c74  jz      short loc_180056C99
0x180056c76  mov     r14, [rbx+18h]
0x180056c7a  test    r14, r14
0x180056c7d  jz      short loc_180056C94
0x180056c7f  mov     rcx, r14; this
0x180056c82  call    ??1CCachedFolder@@QEAA@XZ; CCachedFolder::~CCachedFolder(void)
0x180056c87  mov     edx, 80h
0x180056c8c  mov     rcx, r14; Block
0x180056c8f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180056c94  mov     rbx, [rbx]
0x180056c97  jmp     short loc_180056C71
0x180056c99  mov     rcx, rbp
0x180056c9c  call    ?clear@?$_Hash@V?$_Hmap_traits@HPEAVCCachedFolder@@V?$hash_compare@HU?$less@H@std@@@stdext@@V?$allocator@U?$pair@$$CBHPEAVCCachedFolder@@@std@@@std@@$00@stdext@@@std@@QEAAXXZ; std::_Hash<stdext::_Hmap_traits<int,CCachedFolder *,stdext::hash_compare<int,std::less<int>>,std::allocator<std::pair<int const,CCachedFolder *>>,1>>::clear(void)
0x180056ca1  mov     rcx, rsi; lpCriticalSection
0x180056ca4  call    cs:__imp_LeaveCriticalSection
0x180056caa  mov     rcx, rsi; lpCriticalSection
0x180056cad  call    cs:__imp_DeleteCriticalSection
0x180056cb3  lea     rcx, [rbp+18h]
0x180056cb7  call    ??1?$vector@PEAVCDriverPackageDetailed@@V?$allocator@PEAVCDriverPackageDetailed@@@std@@@std@@QEAA@XZ; std::vector<CDriverPackageDetailed *>::~vector<CDriverPackageDetailed *>(void)
0x180056cbc  mov     rcx, [rbp+8]
0x180056cc0  mov     rax, [rcx+8]
0x180056cc4  mov     qword ptr [rax], 0
0x180056ccb  mov     rcx, [rcx]; Block
0x180056cce  mov     edi, 20h ; ' '
0x180056cd3  test    rcx, rcx
0x180056cd6  jz      short loc_180056CEB
0x180056cd8  mov     rbx, [rcx]
0x180056cdb  mov     rdx, rdi
0x180056cde  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180056ce3  mov     rcx, rbx
0x180056ce6  test    rbx, rbx
0x180056ce9  jnz     short loc_180056CD8
0x180056ceb  mov     rdx, rdi
0x180056cee  mov     rcx, [rbp+8]; Block
0x180056cf2  add     rsp, 20h
0x180056cf6  pop     r14
0x180056cf8  pop     rdi
0x180056cf9  pop     rsi
0x180056cfa  pop     rbp
0x180056cfb  pop     rbx
0x180056cfc  jmp     ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
```
