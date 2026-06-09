# I_PECurrentProcessComponentCheck

- ea: `0x18007f0d4`
- end: `0x18007f163`
- name: `I_PECurrentProcessComponentCheck`
- size: `143`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18007e398`

## callees

- `0x18007f0d4`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x18007f0ef`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18007f0ef`
- `ntoskrnl!PsGetCurrentProcessId` at `0x18007f0e0`
- `ntoskrnl!PsGetCurrentProcessId` at `0x18007f0e0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18007f149`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18007f149`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18007f104`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18007f104`
- `ntoskrnl!ExReleaseResourceLite` at `0x18007f13d`
- `ntoskrnl!ExReleaseResourceLite` at `0x18007f13d`

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
0x18007f0d4  mov     [rsp+arg_0], rbx
0x18007f0d9  push    rdi
0x18007f0da  sub     rsp, 20h
0x18007f0de  xor     ebx, ebx
0x18007f0e0  call    cs:__imp_PsGetCurrentProcessId
0x18007f0e7  nop     dword ptr [rax+rax+00h]
0x18007f0ec  mov     rdi, rax
0x18007f0ef  call    cs:__imp_KeEnterCriticalRegion
0x18007f0f6  nop     dword ptr [rax+rax+00h]
0x18007f0fb  mov     dl, 1; Wait
0x18007f0fd  lea     rcx, g_HashCacheLock; Resource
0x18007f104  call    cs:__imp_ExAcquireResourceExclusiveLite
0x18007f10b  nop     dword ptr [rax+rax+00h]
0x18007f110  mov     rax, cs:g_PEProcessHashBucketList
0x18007f117  test    rax, rax
0x18007f11a  jz      short loc_18007F136
0x18007f11c  cmp     [rax+8], rdi
0x18007f120  jnz     short loc_18007F12C
0x18007f122  cmp     [rax+30h], ebx
0x18007f125  jz      short loc_18007F12C
0x18007f127  cmp     [rax+24h], ebx
0x18007f12a  jz      short loc_18007F131
0x18007f12c  mov     rax, [rax]
0x18007f12f  jmp     short loc_18007F117
0x18007f131  mov     ebx, 8
0x18007f136  lea     rcx, g_HashCacheLock; Resource
0x18007f13d  call    cs:__imp_ExReleaseResourceLite
0x18007f144  nop     dword ptr [rax+rax+00h]
0x18007f149  call    cs:__imp_KeLeaveCriticalRegion
0x18007f150  nop     dword ptr [rax+rax+00h]
0x18007f155  mov     eax, ebx
0x18007f157  mov     rbx, [rsp+28h+arg_0]
0x18007f15c  add     rsp, 20h
0x18007f160  pop     rdi
0x18007f161  retn
```
