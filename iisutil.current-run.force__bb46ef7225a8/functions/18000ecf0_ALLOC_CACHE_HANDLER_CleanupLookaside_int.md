# ALLOC_CACHE_HANDLER::CleanupLookaside(int)

- ea: `0x18000ecf0`
- end: `0x18000ee87`
- name: `?CleanupLookaside@ALLOC_CACHE_HANDLER@@QEAAXH@Z`
- size: `407`
- prototype: `void __fastcall(ALLOC_CACHE_HANDLER *__hidden this, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000ebd0`
- `0x18001f750`

## callees

- `0x180007300`
- `0x18000ecf0`
- `0x18001f6f8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000edbc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000edbc`
- `api-ms-win-core-interlocked-l1-1-0!QueryDepthSList` at `0x18000ed93`
- `api-ms-win-core-interlocked-l1-1-0!QueryDepthSList` at `0x18000edd4`
- `api-ms-win-core-interlocked-l1-1-0!QueryDepthSList` at `0x18000ed93`
- `api-ms-win-core-interlocked-l1-1-0!QueryDepthSList` at `0x18000edd4`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18000eda5`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18000eda5`

## string_xrefs

- `0x18000ee35`: `ALLOC_CACHE_HANDLER::CleanupLookaside`
- `0x18000ee43`: `servercommon\inetsrv\iis\iisrearc\core\common\util\acache.cxx`

## pseudocode

```c
void __fastcall ALLOC_CACHE_HANDLER::CleanupLookaside(ALLOC_CACHE_HANDLER *this, int a2)
{
  _QWORD *v3; // r12
  __int64 v4; // rax
  unsigned int v5; // r15d
  __int64 v6; // r14
  int i; // ebp
  union _SLIST_HEADER *v8; // rsi
  USHORT DepthSList; // ax
  int v10; // ebx
  int v11; // edi
  PSLIST_ENTRY v12; // rax
  USHORT v13; // ax
  __int32 v14; // eax
  _BYTE v15[16]; // [rsp+40h] [rbp-38h] BYREF
  int v16; // [rsp+88h] [rbp+10h] BYREF

  v16 = a2;
  if ( *((_DWORD *)this + 3) )
  {
    if ( a2 )
      goto LABEL_6;
    if ( ALLOC_CACHE_HANDLER::sm_fPageHeapEnabled && ALLOC_CACHE_HANDLER::sm_fHonorPageHeap )
    {
      v16 = 1;
      _InterlockedExchange((volatile __int32 *)this + 3, 0);
      goto LABEL_6;
    }
  }
  else if ( a2 )
  {
    goto LABEL_6;
  }
  if ( (g_dwDebugFlagsIISUtil & 3) != 0 && (g_dwDebugFlagsIISUtil & 0x1000000) != 0 )
    PuDbgPrint(
      (struct _DEBUG_PRINTS *)g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\acache.cxx",
      0x27Au,
      "ALLOC_CACHE_HANDLER::CleanupLookaside",
      "AllocCalls = %ld, LastAllocCount = %ld\n",
      *((_DWORD *)this + 32));
  v14 = *((_DWORD *)this + 32);
  if ( v14 != *((_DWORD *)this + 2) )
  {
    _InterlockedExchange((volatile __int32 *)this + 2, v14);
    return;
  }
LABEL_6:
  v3 = (_QWORD *)*((_QWORD *)this + 3);
  v4 = lambda_5cd0576cc4450a3357849dbab5e82274_::_lambda_5cd0576cc4450a3357849dbab5e82274_(v15, this, &v16);
  v5 = 0;
  v6 = *(_QWORD *)v4;
  for ( i = *(_DWORD *)(v4 + 8); (unsigned __int64)v5 < v3[2]; ++v5 )
  {
    v8 = (union _SLIST_HEADER *)(*v3 + v3[1] * v5);
    DepthSList = QueryDepthSList(v8);
    v10 = DepthSList;
    if ( DepthSList )
    {
      do
      {
        v11 = 0;
        do
        {
          v12 = InterlockedPopEntrySList(v8);
          if ( !v12 )
            break;
          HeapFree(ALLOC_CACHE_HANDLER::sm_hHeap, 0, v12);
          _InterlockedDecrement((volatile signed __int32 *)(v6 + 64));
          ++v11;
        }
        while ( v11 < v10 );
        if ( !i )
          break;
        v13 = QueryDepthSList(v8);
        v10 = v13;
      }
      while ( v13 );
    }
  }
}

```

## disassembly

```asm
0x18000ecf0  mov     [rsp+arg_8], edx
0x18000ecf4  push    rbx
0x18000ecf5  sub     rsp, 70h
0x18000ecf9  cmp     dword ptr [rcx+0Ch], 0
0x18000ecfd  mov     rbx, rcx
0x18000ed00  jz      loc_18000EE14
0x18000ed06  test    edx, edx
0x18000ed08  jnz     short loc_18000ED32
0x18000ed0a  cmp     cs:?sm_fPageHeapEnabled@ALLOC_CACHE_HANDLER@@0HA, edx; int ALLOC_CACHE_HANDLER::sm_fPageHeapEnabled
0x18000ed10  jz      loc_18000EE1C
0x18000ed16  cmp     cs:?sm_fHonorPageHeap@ALLOC_CACHE_HANDLER@@0HA, edx; int ALLOC_CACHE_HANDLER::sm_fHonorPageHeap
0x18000ed1c  jz      loc_18000EE1C
0x18000ed22  xor     eax, eax
0x18000ed24  mov     [rsp+78h+arg_8], 1
0x18000ed2f  xchg    eax, [rcx+0Ch]
0x18000ed32  mov     [rsp+78h+arg_0], rbp
0x18000ed3a  lea     r8, [rsp+78h+arg_8]
0x18000ed42  mov     [rsp+78h+var_18], r12
0x18000ed47  lea     rcx, [rsp+78h+var_38]
0x18000ed4c  mov     r12, [rbx+18h]
0x18000ed50  mov     rdx, rbx
0x18000ed53  mov     [rsp+78h+var_20], r14
0x18000ed58  mov     [rsp+78h+var_28], r15
0x18000ed5d  call    _lambda_5cd0576cc4450a3357849dbab5e82274____lambda_5cd0576cc4450a3357849dbab5e82274_
0x18000ed62  xor     r15d, r15d
0x18000ed65  mov     r14, [rax]
0x18000ed68  mov     ebp, [rax+8]
0x18000ed6b  cmp     [r12+10h], r15
0x18000ed70  jbe     loc_18000EDFB
0x18000ed76  mov     [rsp+78h+arg_10], rsi
0x18000ed7e  mov     [rsp+78h+var_10], rdi
0x18000ed83  mov     esi, r15d
0x18000ed86  imul    rsi, [r12+8]
0x18000ed8c  add     rsi, [r12]
0x18000ed90  mov     rcx, rsi; ListHead
0x18000ed93  call    cs:__imp_QueryDepthSList
0x18000ed99  movzx   ebx, ax
0x18000ed9c  test    ebx, ebx
0x18000ed9e  jz      short loc_18000EDE1
0x18000eda0  xor     edi, edi
0x18000eda2  mov     rcx, rsi; ListHead
0x18000eda5  call    cs:__imp_InterlockedPopEntrySList
0x18000edab  test    rax, rax
0x18000edae  jz      short loc_18000EDCD
0x18000edb0  mov     rcx, cs:?sm_hHeap@ALLOC_CACHE_HANDLER@@0PEAXEA; hHeap
0x18000edb7  mov     r8, rax; lpMem
0x18000edba  xor     edx, edx; dwFlags
0x18000edbc  call    cs:__imp_HeapFree
0x18000edc2  lock dec dword ptr [r14+40h]
0x18000edc7  inc     edi
0x18000edc9  cmp     edi, ebx
0x18000edcb  jl      short loc_18000EDA2
0x18000edcd  test    ebp, ebp
0x18000edcf  jz      short loc_18000EDE1
0x18000edd1  mov     rcx, rsi; ListHead
0x18000edd4  call    cs:__imp_QueryDepthSList
0x18000edda  movzx   ebx, ax
0x18000eddd  test    ebx, ebx
0x18000eddf  jnz     short loc_18000EDA0
0x18000ede1  inc     r15d
0x18000ede4  mov     eax, r15d
0x18000ede7  cmp     rax, [r12+10h]
0x18000edec  jb      short loc_18000ED83
0x18000edee  mov     rdi, [rsp+78h+var_10]
0x18000edf3  mov     rsi, [rsp+78h+arg_10]
0x18000edfb  mov     r14, [rsp+78h+var_20]
0x18000ee00  mov     r12, [rsp+78h+var_18]
0x18000ee05  mov     rbp, [rsp+78h+arg_0]
0x18000ee0d  mov     r15, [rsp+78h+var_28]
0x18000ee12  jmp     short loc_18000EE81
0x18000ee14  test    edx, edx
0x18000ee16  jnz     loc_18000ED32
0x18000ee1c  mov     eax, cs:g_dwDebugFlagsIISUtil
0x18000ee22  test    al, 3
0x18000ee24  setnz   cl
0x18000ee27  bt      eax, 18h
0x18000ee2b  setb    al
0x18000ee2e  test    al, cl
0x18000ee30  jz      short loc_18000EE6F
0x18000ee32  mov     eax, [rbx+8]
0x18000ee35  lea     r9, aAllocCacheHand_1; "ALLOC_CACHE_HANDLER::CleanupLookaside"
0x18000ee3c  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18000ee43  lea     rdx, aServercommonIn_11; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000ee4a  mov     [rsp+78h+var_48], eax
0x18000ee4e  mov     r8d, 27Ah; unsigned int
0x18000ee54  mov     eax, [rbx+80h]
0x18000ee5a  mov     dword ptr [rsp+78h+var_50], eax; char
0x18000ee5e  lea     rax, aAlloccallsLdLa; "AllocCalls = %ld, LastAllocCount = %ld"...
0x18000ee65  mov     [rsp+78h+var_58], rax; char *
0x18000ee6a  call    PuDbgPrint
0x18000ee6f  mov     eax, [rbx+80h]
0x18000ee75  cmp     eax, [rbx+8]
0x18000ee78  jz      loc_18000ED32
0x18000ee7e  xchg    eax, [rbx+8]
0x18000ee81  add     rsp, 70h
0x18000ee85  pop     rbx
0x18000ee86  retn
```
