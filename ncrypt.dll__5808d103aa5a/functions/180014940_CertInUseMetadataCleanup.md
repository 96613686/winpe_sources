# CertInUseMetadataCleanup

- ea: `0x180014940`
- end: `0x180014972`
- name: `CertInUseMetadataCleanup`
- size: `50`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1800147a0`

## callees

- `0x180014940`
- `0x180014978`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014966`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014966`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014958`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014958`

## pseudocode

```c
int __fastcall CertInUseMetadataCleanup(volatile __int64 *a1)
{
  void *v1; // rbx
  int result; // eax
  HANDLE ProcessHeap; // rax

  v1 = (void *)_InterlockedExchange64(a1, 0);
  result = EtwLogNCryptCertInUse((__int64)v1);
  if ( v1 )
  {
    ProcessHeap = GetProcessHeap();
    return HeapFree(ProcessHeap, 0, v1);
  }
  return result;
}

```

## disassembly

```asm
0x180014940  push    rbx
0x180014942  sub     rsp, 20h
0x180014946  xor     ebx, ebx
0x180014948  xchg    rbx, [rcx]
0x18001494b  mov     rcx, rbx
0x18001494e  call    EtwLogNCryptCertInUse
0x180014953  test    rbx, rbx
0x180014956  jz      short loc_18001496C
0x180014958  call    cs:__imp_GetProcessHeap
0x18001495e  mov     r8, rbx; lpMem
0x180014961  xor     edx, edx; dwFlags
0x180014963  mov     rcx, rax; hHeap
0x180014966  call    cs:__imp_HeapFree
0x18001496c  add     rsp, 20h
0x180014970  pop     rbx
0x180014971  retn
```
