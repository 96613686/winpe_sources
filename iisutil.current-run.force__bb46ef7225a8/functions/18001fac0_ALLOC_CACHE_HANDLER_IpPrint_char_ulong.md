# ALLOC_CACHE_HANDLER::IpPrint(char *,ulong *)

- ea: `0x18001fac0`
- end: `0x18001fb82`
- name: `?IpPrint@ALLOC_CACHE_HANDLER@@QEAAHPEADPEAK@Z`
- size: `194`
- prototype: `__int64 __fastcall(ALLOC_CACHE_HANDLER *__hidden this, char *, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x18001fb90`

## callees

- `0x180015120`

## import_xrefs

- `msvcrt!sprintf_s` at `0x18001fb58`
- `msvcrt!sprintf_s` at `0x18001fb58`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001fb09`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001fb09`

## string_xrefs

- `0x18001fb17`: `[%d]ALLOC_CACHE_HANDLER[%08p]. Config:  ObjSize = %d. Concurrency=%d. Thres=%d.\n TotalObjs = %d. Calls: Alloc(%d), Free(%d). FreeEntries = %d. FillPattern = 0x%08lX.\n`

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
0x18001fac0  mov     [rsp+arg_0], rbx
0x18001fac5  mov     [rsp+arg_10], r8
0x18001faca  mov     [rsp+Buffer], rdx
0x18001facf  push    rbp
0x18001fad0  push    rsi
0x18001fad1  push    rdi
0x18001fad2  push    r12
0x18001fad4  push    r13
0x18001fad6  push    r14
0x18001fad8  push    r15
0x18001fada  sub     rsp, 70h
0x18001fade  mov     r15d, [rcx+0C4h]
0x18001fae5  mov     r13, rcx
0x18001fae8  call    ?QueryDepthForAllSLists@ALLOC_CACHE_HANDLER@@AEAAKXZ; ALLOC_CACHE_HANDLER::QueryDepthForAllSLists(void)
0x18001faed  mov     edi, [r13+0C0h]
0x18001faf4  mov     ebx, eax
0x18001faf6  mov     esi, [r13+80h]
0x18001fafd  mov     ebp, [r13+40h]
0x18001fb01  mov     r14d, [r13+0Ch]
0x18001fb05  mov     r12d, [r13+10h]
0x18001fb09  call    cs:__imp_GetCurrentThreadId
0x18001fb0f  mov     rcx, [rsp+0A8h+arg_10]
0x18001fb17  lea     r8, aDAllocCacheHan; "[%d]ALLOC_CACHE_HANDLER[%08p]. Config: "...
0x18001fb1e  mov     [rsp+0A8h+var_48], r15d
0x18001fb23  mov     r9d, eax
0x18001fb26  mov     [rsp+0A8h+var_50], ebx
0x18001fb2a  mov     ebx, 1
0x18001fb2f  mov     [rsp+0A8h+var_58], edi
0x18001fb33  mov     edx, [rcx]; BufferCount
0x18001fb35  mov     rcx, [rsp+0A8h+Buffer]; Buffer
0x18001fb3d  mov     [rsp+0A8h+var_60], esi
0x18001fb41  mov     [rsp+0A8h+var_68], ebp
0x18001fb45  mov     [rsp+0A8h+var_70], r14d
0x18001fb4a  mov     [rsp+0A8h+var_78], ebx
0x18001fb4e  mov     [rsp+0A8h+var_80], r12d
0x18001fb53  mov     [rsp+0A8h+var_88], r13
0x18001fb58  call    cs:__imp_sprintf_s
0x18001fb5e  mov     rcx, [rsp+0A8h+arg_10]
0x18001fb66  mov     [rcx], eax
0x18001fb68  mov     eax, ebx
0x18001fb6a  mov     rbx, [rsp+0A8h+arg_0]
0x18001fb72  add     rsp, 70h
0x18001fb76  pop     r15
0x18001fb78  pop     r14
0x18001fb7a  pop     r13
0x18001fb7c  pop     r12
0x18001fb7e  pop     rdi
0x18001fb7f  pop     rsi
0x18001fb80  pop     rbp
0x18001fb81  retn
```
