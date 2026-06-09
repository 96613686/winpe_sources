# ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER(void)

- ea: `0x18000ebd0`
- end: `0x18000ec7f`
- name: `??1ALLOC_CACHE_HANDLER@@QEAA@XZ`
- size: `175`
- prototype: `void __fastcall(ALLOC_CACHE_HANDLER *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000eba4`

## callees

- `0x180007300`
- `0x18000ebd0`
- `0x18000ec90`
- `0x18000ecf0`
- `0x180015120`

## import_xrefs

- `msvcrt!_aligned_free` at `0x18000ec03`
- `msvcrt!_aligned_free` at `0x18000ec03`

## string_xrefs

- `0x18000ec58`: `servercommon\inetsrv\iis\iisrearc\core\common\util\acache.cxx`
- `0x18000ec4d`: `ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER`
- `0x18000ec69`: `Items in look-aside lists = %u, Pending HeapFree calls = %u\n`

## pseudocode

```c
void __fastcall ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER(void **this)
{
  char DepthForAllSLists; // al

  if ( *(_DWORD *)this )
  {
    ALLOC_CACHE_HANDLER::RemoveItem((struct ALLOC_CACHE_HANDLER *)this);
    ALLOC_CACHE_HANDLER::CleanupLookaside((ALLOC_CACHE_HANDLER *)this, 1);
  }
  if ( *((_DWORD *)this + 1)
    && !g_fTestProcess
    && (g_dwDebugFlagsIISUtil & 3) != 0
    && (g_dwDebugFlagsIISUtil & 0x1000000) != 0 )
  {
    DepthForAllSLists = ALLOC_CACHE_HANDLER::QueryDepthForAllSLists((ALLOC_CACHE_HANDLER *)this);
    PuDbgPrint(
      (struct _DEBUG_PRINTS *)g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\acache.cxx",
      0x244u,
      "ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER",
      "Items in look-aside lists = %u, Pending HeapFree calls = %u\n",
      DepthForAllSLists);
  }
  if ( *(_DWORD *)this )
  {
    _aligned_free(this[3]);
    this[3] = 0;
  }
}

```

## disassembly

```asm
0x18000ebd0  mov     [rsp+arg_0], rbx
0x18000ebd5  push    rdi
0x18000ebd6  sub     rsp, 40h
0x18000ebda  cmp     dword ptr [rcx], 0
0x18000ebdd  mov     rdi, rcx
0x18000ebe0  jz      short loc_18000EBF4
0x18000ebe2  call    ?RemoveItem@ALLOC_CACHE_HANDLER@@SAXPEAV1@@Z; ALLOC_CACHE_HANDLER::RemoveItem(ALLOC_CACHE_HANDLER *)
0x18000ebe7  mov     edx, 1; int
0x18000ebec  mov     rcx, rdi; this
0x18000ebef  call    ?CleanupLookaside@ALLOC_CACHE_HANDLER@@QEAAXH@Z; ALLOC_CACHE_HANDLER::CleanupLookaside(int)
0x18000ebf4  cmp     dword ptr [rdi+4], 0
0x18000ebf8  jnz     short loc_18000EC1C
0x18000ebfa  cmp     dword ptr [rdi], 0
0x18000ebfd  jz      short loc_18000EC11
0x18000ebff  mov     rcx, [rdi+18h]; Block
0x18000ec03  call    cs:__imp__aligned_free
0x18000ec09  mov     qword ptr [rdi+18h], 0
0x18000ec11  mov     rbx, [rsp+48h+arg_0]
0x18000ec16  add     rsp, 40h
0x18000ec1a  pop     rdi
0x18000ec1b  retn
0x18000ec1c  cmp     cs:?g_fTestProcess@@3HA, 0; int g_fTestProcess
0x18000ec23  jnz     short loc_18000EBFA
0x18000ec25  mov     eax, cs:g_dwDebugFlagsIISUtil
0x18000ec2b  test    al, 3
0x18000ec2d  setnz   cl
0x18000ec30  bt      eax, 18h
0x18000ec34  setb    al
0x18000ec37  test    al, cl
0x18000ec39  jz      short loc_18000EBFA
0x18000ec3b  mov     ebx, [rdi+40h]
0x18000ec3e  mov     rcx, rdi; this
0x18000ec41  call    ?QueryDepthForAllSLists@ALLOC_CACHE_HANDLER@@AEAAKXZ; ALLOC_CACHE_HANDLER::QueryDepthForAllSLists(void)
0x18000ec46  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18000ec4d  lea     r9, aAllocCacheHand_0; "ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDL"...
0x18000ec54  mov     [rsp+48h+var_18], ebx
0x18000ec58  lea     rdx, aServercommonIn_11; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000ec5f  mov     dword ptr [rsp+48h+var_20], eax; char
0x18000ec63  mov     r8d, 244h; unsigned int
0x18000ec69  lea     rax, aItemsInLookAsi; "Items in look-aside lists = %u, Pending"...
0x18000ec70  mov     [rsp+48h+var_28], rax; char *
0x18000ec75  call    PuDbgPrint
0x18000ec7a  jmp     loc_18000EBFA
```
