# StSecpCacheCleanupWorkItem

- ea: `0x14000e5e0`
- end: `0x14000e6c5`
- name: `StSecpCacheCleanupWorkItem`
- size: `229`
- prototype: `void __stdcall(PFLT_GENERIC_WORKITEM FltWorkItem, PVOID FltObject, PVOID Context)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x14000dcd8`
- `0x14000e5e0`
- `0x1400122e0`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x14000e62c`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000e62c`
- `ntoskrnl!RtlEnumerateGenericTableWithoutSplaying` at `0x14000e694`
- `ntoskrnl!RtlEnumerateGenericTableWithoutSplaying` at `0x14000e694`
- `ntoskrnl!RtlDeleteElementGenericTable` at `0x14000e66b`
- `ntoskrnl!RtlDeleteElementGenericTable` at `0x14000e66b`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000e6af`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000e6af`
- `ntoskrnl!KeQueryTimeIncrement` at `0x14000e60c`
- `ntoskrnl!KeQueryTimeIncrement` at `0x14000e60c`

## pseudocode

```c
void __fastcall StSecpCacheCleanupWorkItem(PFLT_GENERIC_WORKITEM FltWorkItem, PVOID FltObject, PVOID Context)
{
  unsigned __int64 v3; // rdi
  __int64 v4; // rbx
  signed __int64 v5; // rbp
  __int64 v6; // rdi
  _QWORD *v7; // rax
  _QWORD *v8; // rsi
  PVOID RestartKey; // [rsp+68h] [rbp+20h] BYREF

  RestartKey = 0;
  v3 = 10000000LL * (unsigned int)g_CacheLifetime;
  v4 = MEMORY[0xFFFFF78000000320];
  v5 = v3 / KeQueryTimeIncrement();
  ExAcquireFastMutex(&g_StSecKeyMutex);
  while ( 1 )
  {
    v7 = RtlEnumerateGenericTableWithoutSplaying(&g_StSecCacheGenericTable, &RestartKey);
    v8 = v7;
    if ( !v7 )
      break;
    if ( v4 - *v7 > v5 )
    {
      v6 = v7[1];
      StSecpFreeNonPaged(v7[2], *((unsigned int *)v7 + 8));
      StSecpFreeNonPaged(v8[3], *((unsigned int *)v8 + 8));
      RtlDeleteElementGenericTable(&g_StSecCacheGenericTable, v8);
      StSecFree(v6);
      RestartKey = 0;
    }
  }
  ExReleaseFastMutex(&g_StSecKeyMutex);
}

```

## disassembly

```asm
0x14000e5e0  push    rbx
0x14000e5e2  push    rbp
0x14000e5e3  push    rsi
0x14000e5e4  push    rdi
0x14000e5e5  sub     rsp, 28h
0x14000e5e9  mov     eax, cs:g_CacheLifetime
0x14000e5ef  mov     rbx, 0FFFFF78000000320h
0x14000e5f9  mov     [rsp+48h+RestartKey], 0
0x14000e602  imul    rdi, rax, 989680h
0x14000e609  mov     rbx, [rbx]
0x14000e60c  call    cs:__imp_KeQueryTimeIncrement
0x14000e613  nop     dword ptr [rax+rax+00h]
0x14000e618  mov     ecx, eax
0x14000e61a  xor     edx, edx
0x14000e61c  mov     rax, rdi
0x14000e61f  div     rcx
0x14000e622  lea     rcx, g_StSecKeyMutex; FastMutex
0x14000e629  mov     rbp, rax
0x14000e62c  call    cs:__imp_ExAcquireFastMutex
0x14000e633  nop     dword ptr [rax+rax+00h]
0x14000e638  jmp     short loc_14000E688
0x14000e63a  mov     rcx, rbx
0x14000e63d  sub     rcx, [rsi]
0x14000e640  cmp     rcx, rbp
0x14000e643  jle     short loc_14000E688
0x14000e645  mov     edx, [rsi+20h]
0x14000e648  mov     rcx, [rsi+10h]
0x14000e64c  mov     rdi, [rsi+8]
0x14000e650  call    StSecpFreeNonPaged
0x14000e655  mov     edx, [rsi+20h]
0x14000e658  mov     rcx, [rsi+18h]
0x14000e65c  call    StSecpFreeNonPaged
0x14000e661  mov     rdx, rsi; Buffer
0x14000e664  lea     rcx, g_StSecCacheGenericTable; Table
0x14000e66b  call    cs:__imp_RtlDeleteElementGenericTable
0x14000e672  nop     dword ptr [rax+rax+00h]
0x14000e677  mov     rcx, rdi
0x14000e67a  call    StSecFree
0x14000e67f  mov     [rsp+48h+RestartKey], 0
0x14000e688  lea     rdx, [rsp+48h+RestartKey]; RestartKey
0x14000e68d  lea     rcx, g_StSecCacheGenericTable; Table
0x14000e694  call    cs:__imp_RtlEnumerateGenericTableWithoutSplaying
0x14000e69b  nop     dword ptr [rax+rax+00h]
0x14000e6a0  mov     rsi, rax
0x14000e6a3  test    rax, rax
0x14000e6a6  jnz     short loc_14000E63A
0x14000e6a8  lea     rcx, g_StSecKeyMutex; FastMutex
0x14000e6af  call    cs:__imp_ExReleaseFastMutex
0x14000e6b6  nop     dword ptr [rax+rax+00h]
0x14000e6bb  add     rsp, 28h
0x14000e6bf  pop     rdi
0x14000e6c0  pop     rsi
0x14000e6c1  pop     rbp
0x14000e6c2  pop     rbx
0x14000e6c3  retn
```
