# I_PECurrentProcessComponentCheck

- ea: `0x180081114`
- end: `0x1800811a3`
- name: `I_PECurrentProcessComponentCheck`
- size: `143`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800803d8`

## callees

- `0x180081114`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x18008112f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18008112f`
- `ntoskrnl!PsGetCurrentProcessId` at `0x180081120`
- `ntoskrnl!PsGetCurrentProcessId` at `0x180081120`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180081189`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180081189`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180081144`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180081144`
- `ntoskrnl!ExReleaseResourceLite` at `0x18008117d`
- `ntoskrnl!ExReleaseResourceLite` at `0x18008117d`

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
0x180081114  mov     [rsp+arg_0], rbx
0x180081119  push    rdi
0x18008111a  sub     rsp, 20h
0x18008111e  xor     ebx, ebx
0x180081120  call    cs:__imp_PsGetCurrentProcessId
0x180081127  nop     dword ptr [rax+rax+00h]
0x18008112c  mov     rdi, rax
0x18008112f  call    cs:__imp_KeEnterCriticalRegion
0x180081136  nop     dword ptr [rax+rax+00h]
0x18008113b  mov     dl, 1; Wait
0x18008113d  lea     rcx, g_HashCacheLock; Resource
0x180081144  call    cs:__imp_ExAcquireResourceExclusiveLite
0x18008114b  nop     dword ptr [rax+rax+00h]
0x180081150  mov     rax, cs:g_PEProcessHashBucketList
0x180081157  test    rax, rax
0x18008115a  jz      short loc_180081176
0x18008115c  cmp     [rax+8], rdi
0x180081160  jnz     short loc_18008116C
0x180081162  cmp     [rax+30h], ebx
0x180081165  jz      short loc_18008116C
0x180081167  cmp     [rax+24h], ebx
0x18008116a  jz      short loc_180081171
0x18008116c  mov     rax, [rax]
0x18008116f  jmp     short loc_180081157
0x180081171  mov     ebx, 8
0x180081176  lea     rcx, g_HashCacheLock; Resource
0x18008117d  call    cs:__imp_ExReleaseResourceLite
0x180081184  nop     dword ptr [rax+rax+00h]
0x180081189  call    cs:__imp_KeLeaveCriticalRegion
0x180081190  nop     dword ptr [rax+rax+00h]
0x180081195  mov     eax, ebx
0x180081197  mov     rbx, [rsp+28h+arg_0]
0x18008119c  add     rsp, 20h
0x1800811a0  pop     rdi
0x1800811a1  retn
```
