# I_PECurrentProcessComponentCheck

- ea: `0x180080700`
- end: `0x18008078f`
- name: `I_PECurrentProcessComponentCheck`
- size: `143`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18007f9c4`

## callees

- `0x180080700`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x18008071b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18008071b`
- `ntoskrnl!PsGetCurrentProcessId` at `0x18008070c`
- `ntoskrnl!PsGetCurrentProcessId` at `0x18008070c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180080775`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180080775`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180080730`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180080730`
- `ntoskrnl!ExReleaseResourceLite` at `0x180080769`
- `ntoskrnl!ExReleaseResourceLite` at `0x180080769`

## pseudocode

```c
__int64 I_PECurrentProcessComponentCheck()
{
  unsigned int v0; // ebx
  HANDLE CurrentProcessId; // rdi
  HANDLE *i; // rax

  v0 = 0;
  CurrentProcessId = PsGetCurrentProcessId();
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite(&g_HashCacheLock, 1u);
  for ( i = (HANDLE *)g_PEProcessHashBucketList; i; i = (HANDLE *)*i )
  {
    if ( i[1] == CurrentProcessId && *((_DWORD *)i + 12) && !*((_DWORD *)i + 9) )
    {
      v0 = 8;
      break;
    }
  }
  ExReleaseResourceLite(&g_HashCacheLock);
  KeLeaveCriticalRegion();
  return v0;
}

```

## disassembly

```asm
0x180080700  mov     [rsp+arg_0], rbx
0x180080705  push    rdi
0x180080706  sub     rsp, 20h
0x18008070a  xor     ebx, ebx
0x18008070c  call    cs:__imp_PsGetCurrentProcessId
0x180080713  nop     dword ptr [rax+rax+00h]
0x180080718  mov     rdi, rax
0x18008071b  call    cs:__imp_KeEnterCriticalRegion
0x180080722  nop     dword ptr [rax+rax+00h]
0x180080727  mov     dl, 1; Wait
0x180080729  lea     rcx, g_HashCacheLock; Resource
0x180080730  call    cs:__imp_ExAcquireResourceExclusiveLite
0x180080737  nop     dword ptr [rax+rax+00h]
0x18008073c  mov     rax, cs:g_PEProcessHashBucketList
0x180080743  test    rax, rax
0x180080746  jz      short loc_180080762
0x180080748  cmp     [rax+8], rdi
0x18008074c  jnz     short loc_180080758
0x18008074e  cmp     [rax+30h], ebx
0x180080751  jz      short loc_180080758
0x180080753  cmp     [rax+24h], ebx
0x180080756  jz      short loc_18008075D
0x180080758  mov     rax, [rax]
0x18008075b  jmp     short loc_180080743
0x18008075d  mov     ebx, 8
0x180080762  lea     rcx, g_HashCacheLock; Resource
0x180080769  call    cs:__imp_ExReleaseResourceLite
0x180080770  nop     dword ptr [rax+rax+00h]
0x180080775  call    cs:__imp_KeLeaveCriticalRegion
0x18008077c  nop     dword ptr [rax+rax+00h]
0x180080781  mov     eax, ebx
0x180080783  mov     rbx, [rsp+28h+arg_0]
0x180080788  add     rsp, 20h
0x18008078c  pop     rdi
0x18008078d  retn
```
