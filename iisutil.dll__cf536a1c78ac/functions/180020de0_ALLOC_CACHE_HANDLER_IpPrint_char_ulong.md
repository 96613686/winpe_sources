# ALLOC_CACHE_HANDLER::IpPrint(char *,ulong *)

- ea: `0x180020de0`
- end: `0x180020eaf`
- name: `?IpPrint@ALLOC_CACHE_HANDLER@@QEAAHPEADPEAK@Z`
- size: `207`
- prototype: `__int64 __fastcall(ALLOC_CACHE_HANDLER *__hidden this, char *, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x180020ec0`

## callees

- `0x1800159e0`

## import_xrefs

- `msvcrt!sprintf_s` at `0x180020e7e`
- `msvcrt!sprintf_s` at `0x180020e7e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020e29`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020e29`

## string_xrefs

- `0x180020e3d`: `[%d]ALLOC_CACHE_HANDLER[%08p]. Config:  ObjSize = %d. Concurrency=%d. Thres=%d.\n TotalObjs = %d. Calls: Alloc(%d), Free(%d). FreeEntries = %d. FillPattern = 0x%08lX.\n`

## pseudocode

```c
__int64 __fastcall ALLOC_CACHE_HANDLER::IpPrint(ALLOC_CACHE_HANDLER *this, char *a2, unsigned int *a3)
{
  int v3; // r15d
  unsigned int DepthForAllSLists; // eax
  int v6; // edi
  unsigned int v7; // ebx
  int v8; // esi
  int v9; // ebp
  int v10; // r14d
  int v11; // r12d
  DWORD CurrentThreadId; // eax

  v3 = *((_DWORD *)this + 49);
  DepthForAllSLists = ALLOC_CACHE_HANDLER::QueryDepthForAllSLists(this);
  v6 = *((_DWORD *)this + 48);
  v7 = DepthForAllSLists;
  v8 = *((_DWORD *)this + 32);
  v9 = *((_DWORD *)this + 16);
  v10 = *((_DWORD *)this + 3);
  v11 = *((_DWORD *)this + 4);
  CurrentThreadId = GetCurrentThreadId();
  *a3 = sprintf_s(
          a2,
          *a3,
          "[%d]ALLOC_CACHE_HANDLER[%08p]. Config:  ObjSize = %d. Concurrency=%d. Thres=%d.\n"
          " TotalObjs = %d. Calls: Alloc(%d), Free(%d). FreeEntries = %d. FillPattern = 0x%08lX.\n",
          CurrentThreadId,
          this,
          v11,
          1,
          v10,
          v9,
          v8,
          v6,
          v7,
          v3);
  return 1;
}

```

## disassembly

```asm
0x180020de0  mov     [rsp+arg_0], rbx
0x180020de5  mov     [rsp+arg_10], r8
0x180020dea  mov     [rsp+Buffer], rdx
0x180020def  push    rbp
0x180020df0  push    rsi
0x180020df1  push    rdi
0x180020df2  push    r12
0x180020df4  push    r13
0x180020df6  push    r14
0x180020df8  push    r15
0x180020dfa  sub     rsp, 70h
0x180020dfe  mov     r15d, [rcx+0C4h]
0x180020e05  mov     r13, rcx
0x180020e08  call    ?QueryDepthForAllSLists@ALLOC_CACHE_HANDLER@@AEAAKXZ; ALLOC_CACHE_HANDLER::QueryDepthForAllSLists(void)
0x180020e0d  mov     edi, [r13+0C0h]
0x180020e14  mov     ebx, eax
0x180020e16  mov     esi, [r13+80h]
0x180020e1d  mov     ebp, [r13+40h]
0x180020e21  mov     r14d, [r13+0Ch]
0x180020e25  mov     r12d, [r13+10h]
0x180020e29  call    cs:__imp_GetCurrentThreadId
0x180020e30  nop     dword ptr [rax+rax+00h]
0x180020e35  mov     rcx, [rsp+0A8h+arg_10]
0x180020e3d  lea     r8, aDAllocCacheHan; "[%d]ALLOC_CACHE_HANDLER[%08p]. Config: "...
0x180020e44  mov     [rsp+0A8h+var_48], r15d
0x180020e49  mov     r9d, eax
0x180020e4c  mov     [rsp+0A8h+var_50], ebx
0x180020e50  mov     ebx, 1
0x180020e55  mov     [rsp+0A8h+var_58], edi
0x180020e59  mov     edx, [rcx]; BufferCount
0x180020e5b  mov     rcx, [rsp+0A8h+Buffer]; Buffer
0x180020e63  mov     [rsp+0A8h+var_60], esi
0x180020e67  mov     [rsp+0A8h+var_68], ebp
0x180020e6b  mov     [rsp+0A8h+var_70], r14d
0x180020e70  mov     [rsp+0A8h+var_78], ebx
0x180020e74  mov     [rsp+0A8h+var_80], r12d
0x180020e79  mov     [rsp+0A8h+var_88], r13
0x180020e7e  call    cs:__imp_sprintf_s
0x180020e85  nop     dword ptr [rax+rax+00h]
0x180020e8a  mov     rcx, [rsp+0A8h+arg_10]
0x180020e92  mov     [rcx], eax
0x180020e94  mov     eax, ebx
0x180020e96  mov     rbx, [rsp+0A8h+arg_0]
0x180020e9e  add     rsp, 70h
0x180020ea2  pop     r15
0x180020ea4  pop     r14
0x180020ea6  pop     r13
0x180020ea8  pop     r12
0x180020eaa  pop     rdi
0x180020eab  pop     rsi
0x180020eac  pop     rbp
0x180020ead  retn
```
