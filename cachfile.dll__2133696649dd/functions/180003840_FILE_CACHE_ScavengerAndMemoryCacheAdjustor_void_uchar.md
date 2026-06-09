# FILE_CACHE::ScavengerAndMemoryCacheAdjustor(void *,uchar)

- ea: `0x180003840`
- end: `0x18000394f`
- name: `?ScavengerAndMemoryCacheAdjustor@FILE_CACHE@@CAXPEAXE@Z`
- size: `271`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180003840`
- `0x180003c32`
- `0x180003c70`
- `0x180004010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x1800038bf`
- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x1800038bf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800038ef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800038ef`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800038c9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800038c9`
- `iisutil!?DeleteIf@TREE_HASH_TABLE@@QEAAXP6AHPEAX0@Z0@Z` at `0x180003924`
- `iisutil!?DeleteIf@TREE_HASH_TABLE@@QEAAXP6AHPEAX0@Z0@Z` at `0x180003924`

## pseudocode

```c
void __fastcall FILE_CACHE::ScavengerAndMemoryCacheAdjustor(char *a1)
{
  void (__fastcall ***v2)(_QWORD, __int64, __int64); // rax
  DWORDLONG ullTotalVirtual; // rax
  unsigned int v4; // eax
  unsigned __int64 v5; // r8
  struct _MEMORYSTATUSEX Buffer; // [rsp+20h] [rbp-58h] BYREF

  if ( !_InterlockedCompareExchange(&FILE_CACHE::sm_fScavengerFired, 1, 0) )
  {
    v2 = (void (__fastcall ***)(_QWORD, __int64, __int64))(*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 96LL))(g_pGlobalInfo);
    (**v2)(v2, 2, 1);
    if ( !*((_QWORD *)a1 + 6) )
    {
      memset_0(&Buffer, 0, sizeof(Buffer));
      Buffer.dwLength = 64;
      GlobalMemoryStatusEx(&Buffer);
      EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 72));
      ullTotalVirtual = Buffer.ullTotalVirtual;
      if ( Buffer.ullAvailPhys + *((_QWORD *)a1 + 15) < Buffer.ullTotalVirtual )
        ullTotalVirtual = Buffer.ullAvailPhys + *((_QWORD *)a1 + 15);
      *((_QWORD *)a1 + 14) = ullTotalVirtual >> 1;
      LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 72));
    }
    v4 = *((_DWORD *)a1 + 36);
    if ( v4 )
    {
      v5 = 2LL * *((_QWORD *)a1 + 14);
      *((_DWORD *)a1 + 36) = v4 >> 1;
      TREE_HASH_TABLE::DeleteIf(
        (TREE_HASH_TABLE *)a1,
        (int (*)(void *, void *))FILE_CACHE::CacheFlushByHitCount,
        (void *)(unsigned int)(*((_QWORD *)a1 + 15) / v5));
    }
    FILE_CACHE::sm_fScavengerFired = 0;
  }
}

```

## disassembly

```asm
0x180003840  mov     [rsp+arg_8], rbx
0x180003845  push    rdi
0x180003846  sub     rsp, 70h
0x18000384a  mov     rax, cs:__security_cookie
0x180003851  xor     rax, rsp
0x180003854  mov     [rsp+78h+var_18], rax
0x180003859  mov     rdi, rcx
0x18000385c  mov     ebx, 1
0x180003861  xor     eax, eax
0x180003863  lock cmpxchg cs:?sm_fScavengerFired@FILE_CACHE@@0HA, ebx; int FILE_CACHE::sm_fScavengerFired
0x18000386b  jnz     loc_180003934
0x180003871  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x180003878  mov     rax, [rcx]
0x18000387b  mov     rax, [rax+60h]
0x18000387f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003884  mov     r9, rax
0x180003887  lea     edx, [rbx+1]
0x18000388a  mov     r8d, ebx
0x18000388d  mov     rcx, [rax]
0x180003890  mov     rax, [rcx]
0x180003893  mov     rcx, r9
0x180003896  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000389b  cmp     qword ptr [rdi+30h], 0
0x1800038a0  jnz     short loc_1800038F5
0x1800038a2  mov     ebx, 40h ; '@'
0x1800038a7  lea     rcx, [rsp+78h+Buffer]; void *
0x1800038ac  mov     r8d, ebx; Size
0x1800038af  xor     edx, edx; Val
0x1800038b1  call    memset_0
0x1800038b6  lea     rcx, [rsp+78h+Buffer]; lpBuffer
0x1800038bb  mov     [rsp+78h+Buffer.dwLength], ebx
0x1800038bf  call    cs:__imp_GlobalMemoryStatusEx
0x1800038c5  lea     rcx, [rdi+48h]; lpCriticalSection
0x1800038c9  call    cs:__imp_EnterCriticalSection
0x1800038cf  mov     rax, [rsp+78h+Buffer.ullTotalVirtual]
0x1800038d4  lea     rcx, [rdi+48h]; lpCriticalSection
0x1800038d8  mov     rdx, [rdi+78h]
0x1800038dc  add     rdx, [rsp+78h+Buffer.ullAvailPhys]
0x1800038e1  cmp     rdx, rax
0x1800038e4  cmovb   rax, rdx
0x1800038e8  shr     rax, 1
0x1800038eb  mov     [rdi+70h], rax
0x1800038ef  call    cs:__imp_LeaveCriticalSection
0x1800038f5  mov     eax, [rdi+90h]
0x1800038fb  test    eax, eax
0x1800038fd  jz      short loc_18000392A
0x1800038ff  mov     r8, [rdi+70h]
0x180003903  xor     edx, edx
0x180003905  shr     eax, 1
0x180003907  add     r8, r8
0x18000390a  mov     [rdi+90h], eax
0x180003910  mov     rcx, rdi
0x180003913  mov     rax, [rdi+78h]
0x180003917  div     r8
0x18000391a  lea     rdx, ?CacheFlushByHitCount@FILE_CACHE@@CAHPEAX0@Z; FILE_CACHE::CacheFlushByHitCount(void *,void *)
0x180003921  mov     r8d, eax
0x180003924  call    cs:__imp_?DeleteIf@TREE_HASH_TABLE@@QEAAXP6AHPEAX0@Z0@Z; TREE_HASH_TABLE::DeleteIf(int (*)(void *,void *),void *)
0x18000392a  mov     cs:?sm_fScavengerFired@FILE_CACHE@@0HA, 0; int FILE_CACHE::sm_fScavengerFired
0x180003934  mov     rcx, [rsp+78h+var_18]
0x180003939  xor     rcx, rsp; StackCookie
0x18000393c  call    __security_check_cookie
0x180003941  mov     rbx, [rsp+78h+arg_8]
0x180003949  add     rsp, 70h
0x18000394d  pop     rdi
0x18000394e  retn
```
