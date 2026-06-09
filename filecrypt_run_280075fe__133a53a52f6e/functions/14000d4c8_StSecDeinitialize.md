# StSecDeinitialize

- ea: `0x14000d4c8`
- end: `0x14000d5fd`
- name: `StSecDeinitialize`
- size: `309`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000d0a0`
- `0x140014300`

## callees

- `0x14000d4c8`
- `0x14000e6cc`
- `0x1400122e0`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x14000d535`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000d58e`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000d535`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000d58e`
- `ntoskrnl!ZwClose` at `0x14000d5e5`
- `ntoskrnl!ZwClose` at `0x14000d5e5`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x14000d4e5`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x14000d5c2`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x14000d4e5`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x14000d5c2`

## pseudocode

```c
void StSecDeinitialize()
{
  __int64 v0; // rbx
  __int64 v1; // rax
  struct _UNICODE_STRING *v2; // rbx
  __int64 v3; // rax

  StSecpCacheDeinitialize();
  if ( g_HmacHashProvider )
  {
    BCryptCloseAlgorithmProvider(g_HmacHashProvider, 0);
    g_HmacHashProvider = 0;
  }
  while ( 1 )
  {
    v0 = g_StSecSecurityDescriptorCacheListHead;
    if ( (__int64 *)g_StSecSecurityDescriptorCacheListHead == &g_StSecSecurityDescriptorCacheListHead )
      break;
    if ( *(__int64 **)(g_StSecSecurityDescriptorCacheListHead + 8) != &g_StSecSecurityDescriptorCacheListHead
      || (v1 = *(_QWORD *)g_StSecSecurityDescriptorCacheListHead,
          *(_QWORD *)(*(_QWORD *)g_StSecSecurityDescriptorCacheListHead + 8LL) != g_StSecSecurityDescriptorCacheListHead) )
    {
LABEL_11:
      __fastfail(3u);
    }
    g_StSecSecurityDescriptorCacheListHead = *(_QWORD *)g_StSecSecurityDescriptorCacheListHead;
    *(_QWORD *)(v1 + 8) = &g_StSecSecurityDescriptorCacheListHead;
    RtlFreeUnicodeString((PUNICODE_STRING)(v0 + 16));
    StSecFree(*(void **)(v0 + 32));
    StSecFree(*(void **)(v0 + 40));
    StSecFree((void *)v0);
  }
  while ( 1 )
  {
    v2 = (struct _UNICODE_STRING *)g_StSecFolderPropertyCacheListHead;
    if ( (__int64 *)g_StSecFolderPropertyCacheListHead == &g_StSecFolderPropertyCacheListHead )
      break;
    if ( *(__int64 **)(g_StSecFolderPropertyCacheListHead + 8) != &g_StSecFolderPropertyCacheListHead )
      goto LABEL_11;
    v3 = *(_QWORD *)g_StSecFolderPropertyCacheListHead;
    if ( *(_QWORD *)(*(_QWORD *)g_StSecFolderPropertyCacheListHead + 8LL) != g_StSecFolderPropertyCacheListHead )
      goto LABEL_11;
    g_StSecFolderPropertyCacheListHead = *(_QWORD *)g_StSecFolderPropertyCacheListHead;
    *(_QWORD *)(v3 + 8) = &g_StSecFolderPropertyCacheListHead;
    RtlFreeUnicodeString(v2 + 1);
    StSecFree(v2[2].Buffer);
    StSecFree(v2);
  }
  if ( g_HashProvider )
  {
    BCryptCloseAlgorithmProvider(g_HashProvider, 0);
    g_HashProvider = 0;
  }
  if ( g_DebugProfileKey )
    ZwClose(g_DebugProfileKey);
}

```

## disassembly

```asm
0x14000d4c8  mov     [rsp+arg_0], rbx
0x14000d4cd  push    rdi
0x14000d4ce  sub     rsp, 20h
0x14000d4d2  call    StSecpCacheDeinitialize
0x14000d4d7  mov     rcx, cs:g_HmacHashProvider; hAlgorithm
0x14000d4de  test    rcx, rcx
0x14000d4e1  jz      short loc_14000D4FC
0x14000d4e3  xor     edx, edx; dwFlags
0x14000d4e5  call    cs:__imp_BCryptCloseAlgorithmProvider
0x14000d4ec  nop     dword ptr [rax+rax+00h]
0x14000d4f1  mov     cs:g_HmacHashProvider, 0
0x14000d4fc  lea     rdi, g_StSecSecurityDescriptorCacheListHead
0x14000d503  mov     rbx, cs:g_StSecSecurityDescriptorCacheListHead
0x14000d50a  cmp     rbx, rdi
0x14000d50d  jz      short loc_14000D55D
0x14000d50f  cmp     [rbx+8], rdi
0x14000d513  jnz     loc_14000D5AD
0x14000d519  mov     rax, [rbx]
0x14000d51c  cmp     [rax+8], rbx
0x14000d520  jnz     loc_14000D5AD
0x14000d526  mov     cs:g_StSecSecurityDescriptorCacheListHead, rax
0x14000d52d  lea     rcx, [rbx+10h]; UnicodeString
0x14000d531  mov     [rax+8], rdi
0x14000d535  call    cs:__imp_RtlFreeUnicodeString
0x14000d53c  nop     dword ptr [rax+rax+00h]
0x14000d541  mov     rcx, [rbx+20h]
0x14000d545  call    StSecFree
0x14000d54a  mov     rcx, [rbx+28h]
0x14000d54e  call    StSecFree
0x14000d553  mov     rcx, rbx
0x14000d556  call    StSecFree
0x14000d55b  jmp     short loc_14000D503
0x14000d55d  lea     rdi, g_StSecFolderPropertyCacheListHead
0x14000d564  mov     rbx, cs:g_StSecFolderPropertyCacheListHead
0x14000d56b  cmp     rbx, rdi
0x14000d56e  jz      short loc_14000D5B4
0x14000d570  cmp     [rbx+8], rdi
0x14000d574  jnz     short loc_14000D5AD
0x14000d576  mov     rax, [rbx]
0x14000d579  cmp     [rax+8], rbx
0x14000d57d  jnz     short loc_14000D5AD
0x14000d57f  mov     cs:g_StSecFolderPropertyCacheListHead, rax
0x14000d586  lea     rcx, [rbx+10h]; UnicodeString
0x14000d58a  mov     [rax+8], rdi
0x14000d58e  call    cs:__imp_RtlFreeUnicodeString
0x14000d595  nop     dword ptr [rax+rax+00h]
0x14000d59a  mov     rcx, [rbx+28h]
0x14000d59e  call    StSecFree
0x14000d5a3  mov     rcx, rbx
0x14000d5a6  call    StSecFree
0x14000d5ab  jmp     short loc_14000D564
0x14000d5ad  mov     ecx, 3
0x14000d5b2  int     29h; Win8: RtlFailFast(ecx)
0x14000d5b4  mov     rcx, cs:g_HashProvider; hAlgorithm
0x14000d5bb  test    rcx, rcx
0x14000d5be  jz      short loc_14000D5D9
0x14000d5c0  xor     edx, edx; dwFlags
0x14000d5c2  call    cs:__imp_BCryptCloseAlgorithmProvider
0x14000d5c9  nop     dword ptr [rax+rax+00h]
0x14000d5ce  mov     cs:g_HashProvider, 0
0x14000d5d9  mov     rcx, cs:g_DebugProfileKey; Handle
0x14000d5e0  test    rcx, rcx
0x14000d5e3  jz      short loc_14000D5F1
0x14000d5e5  call    cs:__imp_ZwClose
0x14000d5ec  nop     dword ptr [rax+rax+00h]
0x14000d5f1  mov     rbx, [rsp+28h+arg_0]
0x14000d5f6  add     rsp, 20h
0x14000d5fa  pop     rdi
0x14000d5fb  retn
```
