# StSecpCacheDeinitialize

- ea: `0x14000e6cc`
- end: `0x14000e7cf`
- name: `StSecpCacheDeinitialize`
- size: `259`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000d4c8`

## callees

- `0x14000dcd8`
- `0x14000e6cc`
- `0x1400122e0`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x14000e71e`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000e71e`
- `ntoskrnl!RtlEnumerateGenericTableWithoutSplaying` at `0x14000e77b`
- `ntoskrnl!RtlEnumerateGenericTableWithoutSplaying` at `0x14000e77b`
- `ntoskrnl!RtlDeleteElementGenericTable` at `0x14000e752`
- `ntoskrnl!RtlDeleteElementGenericTable` at `0x14000e752`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000e796`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000e796`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14000e6eb`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14000e6eb`

## pseudocode

```c
void StSecpCacheDeinitialize()
{
  __int64 v0; // rbx
  _QWORD *v1; // rax
  _QWORD *v2; // rdi
  PVOID RestartKey; // [rsp+30h] [rbp+8h] BYREF

  RestartKey = 0;
  if ( g_WorkItem )
  {
    FltFreeGenericWorkItem(g_WorkItem);
    g_WorkItem = 0;
  }
  if ( g_FilterObject )
    g_FilterObject = 0;
  ExAcquireFastMutex(&g_StSecKeyMutex);
  while ( 1 )
  {
    v1 = RtlEnumerateGenericTableWithoutSplaying(&g_StSecCacheGenericTable, &RestartKey);
    v2 = v1;
    if ( !v1 )
      break;
    v0 = v1[1];
    StSecpFreeNonPaged(v1[2], *((unsigned int *)v1 + 8));
    StSecpFreeNonPaged(v2[3], *((unsigned int *)v2 + 8));
    RtlDeleteElementGenericTable(&g_StSecCacheGenericTable, v2);
    StSecFree(v0);
    RestartKey = 0;
  }
  ExReleaseFastMutex(&g_StSecKeyMutex);
  if ( g_MasterKey )
  {
    StSecpFreeNonPaged(g_MasterKey, 128);
    g_MasterKey = 0;
  }
}

```

## disassembly

```asm
0x14000e6cc  mov     [rsp+arg_8], rbx
0x14000e6d1  push    rdi
0x14000e6d2  sub     rsp, 20h
0x14000e6d6  mov     rcx, cs:g_WorkItem; FltWorkItem
0x14000e6dd  mov     [rsp+28h+RestartKey], 0
0x14000e6e6  test    rcx, rcx
0x14000e6e9  jz      short loc_14000E702
0x14000e6eb  call    cs:__imp_FltFreeGenericWorkItem
0x14000e6f2  nop     dword ptr [rax+rax+00h]
0x14000e6f7  mov     cs:g_WorkItem, 0
0x14000e702  cmp     cs:g_FilterObject, 0
0x14000e70a  jz      short loc_14000E717
0x14000e70c  mov     cs:g_FilterObject, 0
0x14000e717  lea     rcx, g_StSecKeyMutex; FastMutex
0x14000e71e  call    cs:__imp_ExAcquireFastMutex
0x14000e725  nop     dword ptr [rax+rax+00h]
0x14000e72a  jmp     short loc_14000E76F
0x14000e72c  mov     edx, [rdi+20h]
0x14000e72f  mov     rcx, [rdi+10h]
0x14000e733  mov     rbx, [rdi+8]
0x14000e737  call    StSecpFreeNonPaged
0x14000e73c  mov     edx, [rdi+20h]
0x14000e73f  mov     rcx, [rdi+18h]
0x14000e743  call    StSecpFreeNonPaged
0x14000e748  mov     rdx, rdi; Buffer
0x14000e74b  lea     rcx, g_StSecCacheGenericTable; Table
0x14000e752  call    cs:__imp_RtlDeleteElementGenericTable
0x14000e759  nop     dword ptr [rax+rax+00h]
0x14000e75e  mov     rcx, rbx
0x14000e761  call    StSecFree
0x14000e766  mov     [rsp+28h+RestartKey], 0
0x14000e76f  lea     rdx, [rsp+28h+RestartKey]; RestartKey
0x14000e774  lea     rcx, g_StSecCacheGenericTable; Table
0x14000e77b  call    cs:__imp_RtlEnumerateGenericTableWithoutSplaying
0x14000e782  nop     dword ptr [rax+rax+00h]
0x14000e787  mov     rdi, rax
0x14000e78a  test    rax, rax
0x14000e78d  jnz     short loc_14000E72C
0x14000e78f  lea     rcx, g_StSecKeyMutex; FastMutex
0x14000e796  call    cs:__imp_ExReleaseFastMutex
0x14000e79d  nop     dword ptr [rax+rax+00h]
0x14000e7a2  mov     rcx, cs:g_MasterKey
0x14000e7a9  test    rcx, rcx
0x14000e7ac  jz      short loc_14000E7C3
0x14000e7ae  mov     edx, 80h
0x14000e7b3  call    StSecpFreeNonPaged
0x14000e7b8  mov     cs:g_MasterKey, 0
0x14000e7c3  mov     rbx, [rsp+28h+arg_8]
0x14000e7c8  add     rsp, 20h
0x14000e7cc  pop     rdi
0x14000e7cd  retn
```
