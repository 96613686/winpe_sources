# ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER(void)

- ea: `0x18000fe40`
- end: `0x18000fef6`
- name: `??1ALLOC_CACHE_HANDLER@@QEAA@XZ`
- size: `182`
- prototype: `void __fastcall(ALLOC_CACHE_HANDLER *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000fe18`

## callees

- `0x180008000`
- `0x18000fe40`
- `0x18000ff00`
- `0x18000ff70`
- `0x1800159e0`

## import_xrefs

- `msvcrt!_aligned_free` at `0x18000fe73`
- `msvcrt!_aligned_free` at `0x18000fe73`

## string_xrefs

- `0x18000fecf`: `servercommon\inetsrv\iis\iisrearc\core\common\util\acache.cxx`
- `0x18000fec4`: `ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER`
- `0x18000fee0`: `Items in look-aside lists = %u, Pending HeapFree calls = %u\n`

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
0x18000fe40  mov     [rsp+arg_0], rbx
0x18000fe45  push    rdi
0x18000fe46  sub     rsp, 40h
0x18000fe4a  cmp     dword ptr [rcx], 0
0x18000fe4d  mov     rdi, rcx
0x18000fe50  jz      short loc_18000FE64
0x18000fe52  call    ?RemoveItem@ALLOC_CACHE_HANDLER@@SAXPEAV1@@Z; ALLOC_CACHE_HANDLER::RemoveItem(ALLOC_CACHE_HANDLER *)
0x18000fe57  mov     edx, 1; int
0x18000fe5c  mov     rcx, rdi; this
0x18000fe5f  call    ?CleanupLookaside@ALLOC_CACHE_HANDLER@@QEAAXH@Z; ALLOC_CACHE_HANDLER::CleanupLookaside(int)
0x18000fe64  cmp     dword ptr [rdi+4], 0
0x18000fe68  jnz     short loc_18000FE93
0x18000fe6a  cmp     dword ptr [rdi], 0
0x18000fe6d  jz      short loc_18000FE87
0x18000fe6f  mov     rcx, [rdi+18h]; Block
0x18000fe73  call    cs:__imp__aligned_free
0x18000fe7a  nop     dword ptr [rax+rax+00h]
0x18000fe7f  mov     qword ptr [rdi+18h], 0
0x18000fe87  mov     rbx, [rsp+48h+arg_0]
0x18000fe8c  add     rsp, 40h
0x18000fe90  pop     rdi
0x18000fe91  retn
0x18000fe93  cmp     cs:?g_fTestProcess@@3HA, 0; int g_fTestProcess
0x18000fe9a  jnz     short loc_18000FE6A
0x18000fe9c  mov     eax, cs:g_dwDebugFlagsIISUtil
0x18000fea2  test    al, 3
0x18000fea4  setnz   cl
0x18000fea7  bt      eax, 18h
0x18000feab  setb    al
0x18000feae  test    al, cl
0x18000feb0  jz      short loc_18000FE6A
0x18000feb2  mov     ebx, [rdi+40h]
0x18000feb5  mov     rcx, rdi; this
0x18000feb8  call    ?QueryDepthForAllSLists@ALLOC_CACHE_HANDLER@@AEAAKXZ; ALLOC_CACHE_HANDLER::QueryDepthForAllSLists(void)
0x18000febd  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18000fec4  lea     r9, aAllocCacheHand_0; "ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDL"...
0x18000fecb  mov     [rsp+48h+var_18], ebx
0x18000fecf  lea     rdx, aServercommonIn_11; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000fed6  mov     dword ptr [rsp+48h+var_20], eax; char
0x18000feda  mov     r8d, 244h; unsigned int
0x18000fee0  lea     rax, aItemsInLookAsi; "Items in look-aside lists = %u, Pending"...
0x18000fee7  mov     [rsp+48h+var_28], rax; char *
0x18000feec  call    PuDbgPrint
0x18000fef1  jmp     loc_18000FE6A
```
