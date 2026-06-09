# ALLOC_CACHE_HANDLER::CleanupLookaside(int)

- ea: `0x18000ff70`
- end: `0x18001012c`
- name: `?CleanupLookaside@ALLOC_CACHE_HANDLER@@QEAAXH@Z`
- size: `444`
- prototype: `void __fastcall(ALLOC_CACHE_HANDLER *__hidden this, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000fe40`
- `0x180020a30`

## callees

- `0x180008000`
- `0x18000ff70`
- `0x1800209d0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010050`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010050`
- `api-ms-win-core-interlocked-l1-1-0!QueryDepthSList` at `0x180010013`
- `api-ms-win-core-interlocked-l1-1-0!QueryDepthSList` at `0x18001006e`
- `api-ms-win-core-interlocked-l1-1-0!QueryDepthSList` at `0x180010013`
- `api-ms-win-core-interlocked-l1-1-0!QueryDepthSList` at `0x18001006e`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x180010033`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x180010033`

## string_xrefs

- `0x1800100d9`: `ALLOC_CACHE_HANDLER::CleanupLookaside`
- `0x1800100e7`: `servercommon\inetsrv\iis\iisrearc\core\common\util\acache.cxx`

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
0x18000ff70  mov     [rsp+arg_8], edx
0x18000ff74  push    rbx
0x18000ff75  sub     rsp, 70h
0x18000ff79  cmp     dword ptr [rcx+0Ch], 0
0x18000ff7d  mov     rbx, rcx
0x18000ff80  jz      loc_1800100B8
0x18000ff86  test    edx, edx
0x18000ff88  jnz     short loc_18000FFB2
0x18000ff8a  cmp     cs:?sm_fPageHeapEnabled@ALLOC_CACHE_HANDLER@@0HA, edx; int ALLOC_CACHE_HANDLER::sm_fPageHeapEnabled
0x18000ff90  jz      loc_1800100C0
0x18000ff96  cmp     cs:?sm_fHonorPageHeap@ALLOC_CACHE_HANDLER@@0HA, edx; int ALLOC_CACHE_HANDLER::sm_fHonorPageHeap
0x18000ff9c  jz      loc_1800100C0
0x18000ffa2  xor     eax, eax
0x18000ffa4  mov     [rsp+78h+arg_8], 1
0x18000ffaf  xchg    eax, [rcx+0Ch]
0x18000ffb2  mov     [rsp+78h+arg_0], rbp
0x18000ffba  lea     r8, [rsp+78h+arg_8]
0x18000ffc2  mov     [rsp+78h+var_18], r12
0x18000ffc7  lea     rcx, [rsp+78h+var_38]
0x18000ffcc  mov     r12, [rbx+18h]
0x18000ffd0  mov     rdx, rbx
0x18000ffd3  mov     [rsp+78h+var_20], r14
0x18000ffd8  mov     [rsp+78h+var_28], r15
0x18000ffdd  call    _lambda_5cd0576cc4450a3357849dbab5e82274____lambda_5cd0576cc4450a3357849dbab5e82274_
0x18000ffe2  xor     r15d, r15d
0x18000ffe5  mov     r14, [rax]
0x18000ffe8  mov     ebp, [rax+8]
0x18000ffeb  cmp     [r12+10h], r15
0x18000fff0  jbe     loc_18001009F
0x18000fff6  mov     [rsp+78h+arg_10], rsi
0x18000fffe  mov     [rsp+78h+var_10], rdi
0x180010003  mov     esi, r15d
0x180010006  imul    rsi, [r12+8]
0x18001000c  add     rsi, [r12]
0x180010010  mov     rcx, rsi; ListHead
0x180010013  call    cs:__imp_QueryDepthSList
0x18001001a  nop     dword ptr [rax+rax+00h]
0x18001001f  movzx   ebx, ax
0x180010022  test    ebx, ebx
0x180010024  jz      short loc_180010081
0x180010026  xor     edi, edi
0x180010028  nop     dword ptr [rax+rax+00000000h]
0x180010030  mov     rcx, rsi; ListHead
0x180010033  call    cs:__imp_InterlockedPopEntrySList
0x18001003a  nop     dword ptr [rax+rax+00h]
0x18001003f  test    rax, rax
0x180010042  jz      short loc_180010067
0x180010044  mov     rcx, cs:?sm_hHeap@ALLOC_CACHE_HANDLER@@0PEAXEA; hHeap
0x18001004b  mov     r8, rax; lpMem
0x18001004e  xor     edx, edx; dwFlags
0x180010050  call    cs:__imp_HeapFree
0x180010057  nop     dword ptr [rax+rax+00h]
0x18001005c  lock dec dword ptr [r14+40h]
0x180010061  inc     edi
0x180010063  cmp     edi, ebx
0x180010065  jl      short loc_180010030
0x180010067  test    ebp, ebp
0x180010069  jz      short loc_180010081
0x18001006b  mov     rcx, rsi; ListHead
0x18001006e  call    cs:__imp_QueryDepthSList
0x180010075  nop     dword ptr [rax+rax+00h]
0x18001007a  movzx   ebx, ax
0x18001007d  test    ebx, ebx
0x18001007f  jnz     short loc_180010026
0x180010081  inc     r15d
0x180010084  mov     eax, r15d
0x180010087  cmp     rax, [r12+10h]
0x18001008c  jb      loc_180010003
0x180010092  mov     rdi, [rsp+78h+var_10]
0x180010097  mov     rsi, [rsp+78h+arg_10]
0x18001009f  mov     r14, [rsp+78h+var_20]
0x1800100a4  mov     r12, [rsp+78h+var_18]
0x1800100a9  mov     rbp, [rsp+78h+arg_0]
0x1800100b1  mov     r15, [rsp+78h+var_28]
0x1800100b6  jmp     short loc_180010125
0x1800100b8  test    edx, edx
0x1800100ba  jnz     loc_18000FFB2
0x1800100c0  mov     eax, cs:g_dwDebugFlagsIISUtil
0x1800100c6  test    al, 3
0x1800100c8  setnz   cl
0x1800100cb  bt      eax, 18h
0x1800100cf  setb    al
0x1800100d2  test    al, cl
0x1800100d4  jz      short loc_180010113
0x1800100d6  mov     eax, [rbx+8]
0x1800100d9  lea     r9, aAllocCacheHand_1; "ALLOC_CACHE_HANDLER::CleanupLookaside"
0x1800100e0  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x1800100e7  lea     rdx, aServercommonIn_11; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800100ee  mov     [rsp+78h+var_48], eax
0x1800100f2  mov     r8d, 27Ah; unsigned int
0x1800100f8  mov     eax, [rbx+80h]
0x1800100fe  mov     dword ptr [rsp+78h+var_50], eax; char
0x180010102  lea     rax, aAlloccallsLdLa; "AllocCalls = %ld, LastAllocCount = %ld"...
0x180010109  mov     [rsp+78h+var_58], rax; char *
0x18001010e  call    PuDbgPrint
0x180010113  mov     eax, [rbx+80h]
0x180010119  cmp     eax, [rbx+8]
0x18001011c  jz      loc_18000FFB2
0x180010122  xchg    eax, [rbx+8]
0x180010125  add     rsp, 70h
0x180010129  pop     rbx
0x18001012a  retn
```
